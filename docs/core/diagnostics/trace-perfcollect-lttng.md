---
title: PerfCollect를 사용하여 .NET 애플리케이션 추적
description: .NET에서 perfcollect를 사용하여 추적을 수집하는 과정을 안내하는 자습서입니다.
ms.topic: tutorial
ms.date: 10/23/2020
ms.openlocfilehash: 376c957833924a9991e574557671ea3c8503d7c2
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507243"
---
# <a name="trace-net-applications-with-perfcollect"></a>PerfCollect를 사용하여 .NET 애플리케이션 추적

**이 문서의 적용 대상:** ✔️ .NET Core 2.1 SDK 이상 버전

Linux에서 성능 문제가 발생하는 경우 `perfcollect`로 추적을 수집하면 성능 문제 발생 시 머신에서 발생한 상황에 대한 자세한 정보를 수집할 수 있습니다.

`perfcollect`는 [LTTng(Linux Tracing Tookit-Next Generation)](https://lttng.org)를 활용하여 런타임이나 모든 [EventSource](xref:System.Diagnostics.Tracing.EventListener)에서 기록된 이벤트를 수집할 뿐만 아니라 [perf](https://perf.wiki.kernel.org/)를 활용하여 대상 프로세스의 CPU 샘플을 수집하는 bash 스크립트입니다.

## <a name="prepare-your-machine"></a>머신 준비

`perfcollect`로 성능 추적을 수집할 머신을 준비하려면 다음 단계를 수행합니다.

> [!NOTE]
> 컨테이너 환경에 있는 경우 컨테이너에 `SYS_ADMIN` 기능이 있어야 합니다. PerfCollect를 사용하여 컨테이너 내 애플리케이션 추적에 대한 자세한 내용은 [컨테이너에서 진단 수집](./diagnostics-in-containers.md)을 참조하세요.

1. `perfcollect`를 다운로드합니다.

    > ```bash
    > curl -OL https://aka.ms/perfcollect
    > ```

2. 스크립트를 실행 가능하도록 설정합니다.

    > ```bash
    > chmod +x perfcollect
    > ```

3. 추적 필수 구성 요소인 실제 추적 라이브러리를 설치합니다.

    > ```bash
    > sudo ./perfcollect install
    > ```

    그러면 다음과 같은 필수 구성 요소가 머신에 설치됩니다.

    1. `perf`: Linux 성능 이벤트 하위 시스템과 수반되는 사용자 모드 컬렉션/뷰어 애플리케이션입니다. `perf`는 Linux 커널 소스의 일부이지만 보통 기본적으로 설치되지는 않습니다.

    2. `LTTng`: CoreCLR에서 런타임에 내보낸 이벤트 데이터를 캡처하는 데 사용됩니다. 그런 다음, 이 데이터를 사용하여 GC, JIT, 스레드 풀과 같은 다양한 런타임 구성 요소의 동작을 분석합니다.

최신 버전의 .NET Core 및 Linux perf 도구는 프레임워크 코드의 메서드 이름 자동 확인을 지원합니다. .NET Core 3.1 이전 버전을 사용하는 경우 추가 단계가 필요합니다. 자세한 내용은 [프레임워크 기호 확인](#resolve-framework-symbols)을 참조하세요.

네이티브 런타임 DLL(예: libcoreclr.so)의 메서드 이름을 확인하기 위해 `perfcollect`는 데이터를 변환할 때 기호를 확인하지만 이러한 이진에 대한 기호가 있는 경우에만 확인합니다. 자세한 내용은 [네이티브 런타임에 대한 기호 가져오기](#get-symbols-for-the-native-runtime) 섹션을 참조하세요.

## <a name="collect-a-trace"></a>추적 수집

1. 두 개의 셸을 사용할 수 있습니다. 하나는 추적을 제어하는 데 사용되어 **[Trace]** 라고 하고 하나는 애플리케이션을 실행하는 데 사용되어 **[App]** 이라고 합니다.

2. **[Trace]** 컬렉션을 시작합니다.

    > ```bash
    > sudo ./perfcollect collect sampleTrace
    > ```

    예상 출력:

    > ```bash
    > Collection started.  Press CTRL+C to stop.
    > ```

3. **[App]** 다음 환경 변수를 사용하여 애플리케이션 셸을 설정합니다. 따라서 CoreCLR의 구성 추적을 사용할 수 있습니다.

    > ```bash
    > export COMPlus_PerfMapEnabled=1
    > export COMPlus_EnableEventLog=1
    > ```

4. **[App]** 앱을 실행합니다. 성능 문제를 캡처하기 위해 실행해야 하는 한 앱이 실행되도록 합니다. 조사하려는 성능 문제가 발생하는 기간을 충분히 캡처할 수 있다면 정확한 길이는 짧을 수 있습니다.

    > ```bash
    > dotnet run
    > ```

5. **[Trace]** 컬렉션을 중지합니다. Ctrl+C를 누릅니다.

    > ```bash
    > ^C
    > ...STOPPED.
    >
    > Starting post-processing. This may take some time.
    >
    > Generating native image symbol files
    > ...SKIPPED
    > Saving native symbols
    > ...FINISHED
    > Exporting perf.data file
    > ...FINISHED
    > Compressing trace files
    > ...FINISHED
    > Cleaning up artifacts
    > ...FINISHED
    >
    > Trace saved to sampleTrace.trace.zip
    > ```

    이제 압축된 추적 파일이 현재 작업 디렉터리에 저장됩니다.

## <a name="view-a-trace"></a>추적 보기

수집된 추적을 볼 수 있는 여러 가지 옵션이 있습니다. 추적은 Windows에서 [PerfView](https://aka.ms/perfview)를 사용하여 가장 잘 볼 수 있지만 `PerfCollect` 자체나 `TraceCompass`를 사용하여 Linux에서 직접 볼 수 있습니다.

### <a name="use-perfcollect-to-view-the-trace-file"></a>PerfCollect를 사용하여 추적 파일 보기

PerfCollect 자체를 사용하여 수집한 추적을 볼 수 있습니다. 이렇게 하려면 다음 명령을 실행합니다.

```bash
./perfcollect view sampleTrace.trace.zip
```

기본적으로 `perf`를 사용하여 애플리케이션의 CPU 추적을 표시합니다.

`LTTng`를 통해 수집된 이벤트를 확인하려면 `-viewer lttng` 플래그를 전달하여 개별 이벤트를 확인하면 됩니다.

```bash
./perfcollect view sampleTrace.trace.zip -viewer lttng
```

그러면 `babeltrace` 뷰어를 사용하여 이벤트 페이로드를 출력합니다.

```bash
# [01:02:18.189217659] (+0.020132603) ubuntu-xenial DotNETRuntime:ExceptionThrown_V1: { cpu_id = 0 }, { ExceptionType = "System.Exception", ExceptionMessage = "An exception happened", ExceptionEIP = 139875671834775, ExceptionHRESULT = 2148734208, ExceptionFlags = 16, ClrInstanceID = 0 }
# [01:02:18.189250227] (+0.020165171) ubuntu-xenial DotNETRuntime:ExceptionCatchStart: { cpu_id = 0 }, { EntryEIP = 139873639728404, MethodID = 139873626968120, MethodName = "void [helloworld] helloworld.Program::Main(string[])", ClrInstanceID = 0 }
```

### <a name="use-perfview-to-open-the-trace-file"></a>PerfView를 사용하여 추적 파일 열기

CPU 샘플과 이벤트의 집계 뷰를 보려면 Windows 머신에서 `PerfView`를 사용할 수 있습니다.

1. Linux에서 Windows 머신으로 trace.zip 파일을 복사합니다.

2. <https://aka.ms/perfview>에서 PerfView를 다운로드합니다.

3. PerfView.exe 실행

    > ```cmd
    > PerfView.exe <path to trace.zip file>
    > ```

PerfView는 추적 파일에 포함된 데이터에 따라 지원되는 보기 목록을 표시합니다.

- CPU를 조사하려면 **CPU 스택** 을 선택합니다.

- 자세한 GC 정보를 보려면 **GCStats** 를 선택합니다.

- 프로세스/모듈/메서드별 JIT 정보를 보려면 **JITStats** 를 선택합니다.

- 필요한 정보에 대한 보기가 없는 경우 원시 이벤트 보기에서 이벤트를 검색해 볼 수 있습니다.  **이벤트** 를 선택합니다.

PerfView에서 보기를 해석하는 방법에 대한 자세한 내용은 보기 자체의 도움말 링크를 참조하거나 PerfView의 주 창에서 **도움말-> 사용자 가이드** 를 선택합니다.

### <a name="use-tracecompass-to-open-the-trace-file"></a>TraceCompass를 사용하여 추적 파일 열기

[Eclipse TraceCompass](https://www.eclipse.org/tracecompass/)는 추적을 보는 데 사용할 수 있는 또 다른 옵션입니다. `TraceCompass`는 Linux 머신에서도 작동하므로 추적을 Windows 머신으로 이동할 필요가 없습니다. `TraceCompass`를 사용하여 추적 파일을 열려면 파일의 압축을 풀어야 합니다.

```bash
unzip myTrace.trace.zip
```

`perfcollect`는 수집된 LTTng 추적을 CTF 파일 형식으로 `lttngTrace`의 하위 디렉터리에 저장합니다. 특히 CTF 파일은 `lttngTrace/auto-20201025-101230\ust\uid\1000\64-bit\` 같은 디렉터리에 배치됩니다.

`TraceCompass`에서 `File -> Open Trace`를 선택하고 `metadata` 파일을 선택하여 CTF 추적 파일을 엽니다.

자세한 내용은 [`TraceCompass` 설명서](https://www.eclipse.org/tracecompass/)를 참조하세요.

## <a name="resolve-framework-symbols"></a>프레임워크 기호 확인

프레임워크 기호는 추적이 수집될 때 수동으로 생성해야 합니다. 프레임워크는 앱 코드가 Just-In-Time 컴파일되는 동안 미리 컴파일되기 때문에 프레임워크 기호는 앱 수준 기호와 다릅니다. 네이티브 코드로 미리 컴파일된 프레임워크 코드의 경우 네이티브 코드에서 메서드 이름으로의 매핑을 생성하는 방법을 알고 있는 `crossgen`을 호출해야 합니다.

`perfcollect`는 대부분의 세부 정보를 자동으로 처리할 수 있지만 `crossgen`을 사용할 수 있어야 합니다. 기본적으로 .NET 배포와 함께 설치되지 않습니다. `crossgen`이 없는 경우 `perfcollect`는 경고를 표시하고 이러한 지침을 참조하도록 합니다. 이러한 문제를 해결하려면 사용 중인 런타임에 올바른 버전의 crossgen을 정확하게 페치해야 합니다. crossgen 도구를 .NET 런타임 DLL과 같은 디렉터리(예: libcoreclr.so)에 배치하면 `perfcollect`에서 찾아 추적 파일에 프레임워크 기호를 추가할 수 있습니다.

일반적으로 .NET 애플리케이션을 만들 때 직접 작성한 코드에 대한 DLL만 생성하고 나머지에는 런타임의 공유 복사본을 사용합니다.   그러나 애플리케이션의 ‘자체 포함’ 버전을 생성할 수도 있으며 여기에는 모든 런타임 DLL이 포함됩니다. `crossgen`은 자체 포함 앱을 만드는 데 사용되는 NuGet 패키지의 일부이므로 애플리케이션의 자체 포함 패키지를 만들면 올바른 버전의 `crossgen`을 가져올 수 있습니다.

예를 들면 다음과 같습니다.

   >```bash
   > mkdir helloWorld
   > cd helloWorld
   > dotnet new console
   > dotnet publish --self-contained -r linux-x64
   >```

그러면 새 Hello World 애플리케이션이 만들어지고 자체 포함 앱으로 빌드됩니다.

자체 포함 애플리케이션을 만드는 부작용으로 dotnet 도구는 runtime.linux-x64.microsoft.netcore.app이라는 NuGet 패키지를 다운로드하여 ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/VERSION 디렉터리에 저장합니다. 여기서 VERSION은 .NET Core 런타임의 버전 번호입니다(예: 2.1.0). 그 아래에 도구 디렉터리가 있고 이 디렉터리 내에 필요한 crossgen 도구가 있습니다. .NET Core 3.0부터는 패키지 위치가 ~/.nuget/packages/microsoft.netcore.app.runtime.linux-x64/VERSION입니다.

`crossgen` 도구는 실제로 애플리케이션에서 사용하는 런타임 옆에 배치해야 합니다. 일반적으로 앱은 /usr/share/dotnet/shared/Microsoft.NETCore.App/VERSION에 설치되는 .NET Core의 공유 버전을 사용합니다. 여기서 VERSION은 .NET 런타임의 버전 번호입니다. 이 위치는 공유 위치이므로 수정하려면 슈퍼 사용자여야 합니다. VERSION이 2.1.0인 경우 `crossgen`을 업데이트하는 명령은 다음과 같습니다.

   >```bash
   > sudo bash
   > cp ~/.nuget/packages/runtime.linux-x64.microsoft.netcore.app/2.1.0/tools/crossgen /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
   >```

작업이 완료되면 `perfcollect`에서 crossgen을 사용하여 프레임워크 기호를 포함합니다. `perfcollect`에서 발생하던 경고가 해결됩니다. 런타임을 업데이트할 때까지 머신당 한 번만 수행해야 합니다.

### <a name="alternative-turn-off-use-of-precompiled-code"></a>다른 방법: 미리 컴파일된 코드 사용 해제

.NET 런타임을 업데이트하여 `crossgen`을 추가하는 기능이 없거나 여러 이유로 위의 절차가 작동하지 않는 경우 또 다른 방법으로 프레임워크 기호를 가져올 수 있습니다. 미리 컴파일된 프레임워크 코드를 사용하지 않도록 런타임에 지시할 수 있습니다. 그러면 코드가 Just-In-Time 컴파일되고 `crossgen`이 필요하지 않습니다.

> [!NOTE]
> 이 방법을 선택하면 애플리케이션의 시작 시간이 길어질 수 있습니다.

이렇게 하려면 다음 환경 변수를 추가할 수 있습니다.

```bash
export COMPlus_ZapDisable=1
```

이렇게 변경하면 모든 .NET 코드에 대한 기호를 가져와야 합니다.

## <a name="get-symbols-for-the-native-runtime"></a>네이티브 런타임에 대한 기호 가져오기

대체로 개발자는 직접 작성한 코드에 관심이 있으며, 이러한 코드는 기본적으로 `perfcollect`에서 확인됩니다. 경우에 따라 .NET DLL 내부의 진행 상황(마지막 섹션에서 다루는 내용)을 확인하는 것이 유용하지만, 경우에 따라서는 네이티브 런타임 DLL(일반적으로 libcoreclr.so)의 진행 상황이 흥미롭습니다.  `perfcollect`는 데이터를 변환할 때 이러한 기호를 확인하지만 이러한 네이티브 DLL에 대한 기호가 있고 대상 라이브러리 옆에 있을 때만 확인합니다.

[dotnet-symbol](https://github.com/dotnet/symstore/blob/master/src/dotnet-symbol/README.md#symbol-downloader-dotnet-cli-extension)이라는 전역 명령이 있어 이 작업을 수행합니다. dotnet-symbol을 사용하여 네이티브 런타임 기호를 가져오려면 다음을 수행합니다.

1. `dotnet-symbol` 설치:

    ```bash
    dotnet tool install -g dotnet-symbol
    ```

2. 기호를 다운로드합니다. 설치한 .NET Core 런타임 버전이 2.1.0인 경우 이 작업을 수행하는 명령은 다음과 같습니다.

    ```bash
    mkdir mySymbols
    dotnet symbol --symbols --output mySymbols  /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0/lib*.so
    ```

3. 기호를 올바른 위치에 복사합니다.

    ```bash
    sudo cp mySymbols/* /usr/share/dotnet/shared/Microsoft.NETCore.App/2.1.0
    ```

    적절한 디렉터리에 대한 쓰기 권한이 없어 이 작업을 수행할 수 없는 경우 `perf buildid-cache`를 사용하여 기호를 추가할 수 있습니다.

그러면 `perfcollect`를 실행할 때 네이티브 dll의 기호 이름을 가져와야 합니다.

## <a name="collect-in-a-docker-container"></a>Docker 컨테이너에서 수집

컨테이너 환경에서 `perfcollect`를 사용하는 방법에 대한 자세한 내용은 [컨테이너에서 진단 수집](./diagnostics-in-containers.md)을 참조하세요.
