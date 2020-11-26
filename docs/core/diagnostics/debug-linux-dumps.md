---
title: Linux 덤프 디버그
description: 이 문서에서는 Linux 환경에서 덤프를 수집 및 분석하는 방법을 알아봅니다.
ms.date: 08/27/2020
ms.openlocfilehash: 94f923f2ec7b5fa20c2ebc9b83540094348dff03
ms.sourcegitcommit: 30e9e11dfd90112b8eec6406186ba3533f21eba1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2020
ms.locfileid: "95099148"
---
# <a name="debug-linux-dumps"></a>Linux 덤프 디버그

**이 문서의 적용 대상:** ✔️ .NET Core 3.0 SDK 이상 버전

## <a name="collect-dumps-on-linux"></a>Linux에서 덤프 수집

Linux에서 덤프를 수집하는 두 가지 권장 방법은 [`dotnet-dump`](dotnet-dump.md) 또는 [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md) 도구입니다.

### <a name="managed-dumps-with-dotnet-dump"></a>`dotnet-dump`를 사용한 관리형 덤프

[`dotnet-dump`](dotnet-dump.md) 도구는 간단하게 사용할 수 있으며 네이티브 디버거에 종속되지 않습니다. `dotnet-dump`는 기존 디버깅 도구를 사용할 수 없는 다양한 Linux 플랫폼(예: Alpine 또는 ARM32/ARM64)에서 작동합니다. 그러나 `dotnet-dump`는 관리되는 상태만 캡처하므로 네이티브 코드에서 문제를 디버그하는 데 사용할 수 없습니다. `dotnet-dump`가 수집한 덤프는 덤프가 생성된 동일한 OS 및 아키텍처를 사용하는 환경에서 분석됩니다. [`dotnet-gcdump`](dotnet-gcdump.md) 도구는 GC 힙 정보를 캡처할 뿐 아니라 Windows에서 분석할 수 있는 덤프를 생성하는 대안으로 사용할 수 있습니다.

### <a name="core-dumps-with-createdump"></a>`createdump`를 사용한 코어 덤프

관리형 전용 덤프를 만드는 `dotnet-dump`의 대안인 [`createdump`](https://github.com/dotnet/runtime/blob/master/docs/design/coreclr/botr/xplat-minidump-generation.md)는 네이티브 정보와 관리형 정보를 둘 다 포함하는 코어 덤프를 Linux에서 만들 수 있는 권장 도구입니다. gdb 또는 gcore와 같은 다른 도구를 사용하여 코어 덤프를 만들 수도 있지만, 관리형 디버깅에 필요한 상태를 놓쳐서 분석 중에 “UNKNOWN” 형식 또는 함수 이름이 생성될 수 있습니다.

`createdump` 도구는 .NET Core 런타임과 함께 설치되며 libcoreclr.so 옆에(일반적으로 “/usr/share/dotnet/shared/Microsoft.NETCore.App/[version]”에) 있습니다. 해당 도구는 프로세스 ID를 사용하여 덤프를 기본 인수로 수집하며 수집할 덤프 종류를 지정하는 선택적 매개 변수를 사용할 수도 있습니다(힙이 있는 미니덤프가 기본값임). 다음 옵션을 사용할 수 있습니다.

- **`<input-filename>`**

  변환할 입력 추적 파일입니다. 기본값은 *trace.nettrace* 입니다.

### <a name="options"></a>옵션

- **`-f|--name <output-filename>`**

  덤프를 쓸 대상 파일입니다. 기본값은 ‘/tmp/coredump.%p’입니다. 여기서 %p는 대상 프로세스의 프로세스 ID입니다.

- **`-n|--normal`**

  미니덤프를 만듭니다.

- **`-h|--withheap`**

  힙을 사용하여 미니덤프를 만듭니다(기본값).

- **`-t|--triage`**

  심사 미니덤프를 만듭니다.

- **`-u|--full`**

  전체 코어 덤프를 만듭니다.

- **`-d|--diag`**

  진단 메시지를 사용합니다.

코어 덤프를 수집하려면 `SYS_PTRACE` 기능이 있거나 sudo 또는 su를 사용하여 `createdump`를 실행해야 합니다.

## <a name="analyze-dumps-on-linux"></a>Linux에서 덤프 분석

`dotnet-dump`로 수집된 관리형 덤프와 `createdump`로 수집된 코어 덤프는 둘 다 `dotnet-dump analyze` 명령을 사용하여 `dotnet-dump` 도구로 분석할 수 있습니다. `dotnet dump`를 사용하려면 덤프를 분석하는 환경의 OS 및 아키텍처가 덤프를 캡처한 환경과 동일해야 합니다.

또는 [LLDB](https://lldb.llvm.org/)를 사용하여 Linux에서 코어 덤프를 분석할 수 있습니다. 그러면 관리형 프레임과 네이티브 프레임을 둘 다 분석할 수 있습니다. LLDB는 SOS 확장을 사용하여 관리 코드를 디버그합니다. [`dotnet-sos`](dotnet-sos.md) CLI 도구를 사용하여 관리 코드를 디버그하기 위한 [여러 유용한 명령](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md)이 포함된 SOS를 설치할 수 있습니다. .NET Core 덤프를 분석하려면 LLDB 및 SOS에는 덤프가 생성된 환경의 다음 .NET Core 이진 파일이 필요합니다.

1. libmscordaccore.so
2. libcoreclr.so
3. dotnet(앱을 시작하는 데 사용되는 호스트)

대부분의 경우 [`dotnet-symbol`](dotnet-symbol.md) 도구를 사용하여 해당 이진 파일을 다운로드할 수 있습니다. `dotnet-symbol`을 사용하여 필요한 이진 파일을 다운로드할 수 없는 경우(예를 들어 소스에서 빌드된 프라이빗 버전의 .NET Core를 사용 중인 경우) 덤프가 생성된 환경에서 위에 나열된 파일을 복사해야 할 수 있습니다. 파일이 덤프 파일 옆에 있지 않으면 LLDB/SOS 명령 `setclrpath <path>`를 사용하여 파일을 로드해야 하는 소스 경로를 설정하고 `setsymbolserver -directory <path>`를 사용하여 기호 파일을 확인할 경로를 설정할 수 있습니다.

필요한 파일을 사용할 수 있게 되면 디버그할 실행 파일로 dotnet 호스트를 지정하여 LLDB에서 덤프를 로드할 수 있습니다.

```console
lldb --core <dump-file> <host-program>
```

위 명령줄에서 `<dump-file>`은 분석할 덤프의 경로이며 `<host-program>`은 .NET Core 애플리케이션을 시작한 네이티브 프로그램입니다. 앱이 자체 포함된 경우가 아니면 해당 프로그램은 일반적으로 `dotnet` 이진 파일이며, 이 경우 dll 확장명이 없는 애플리케이션의 이름입니다.

LLDB가 시작되면 `setsymbolserver` 명령을 사용하여 올바른 기호 위치를 가리켜야 할 수 있습니다(Microsoft의 기호 서버 또는 `setsymbolserver -directory <path>`를 사용하여 로컬 경로를 지정하려면 `setsymbolserver -ms`). 네이티브 기호는 `loadsymbols`를 실행하여 로드할 수 있습니다. 이제 [SOS 명령](https://github.com/dotnet/diagnostics/blob/master/documentation/sos-debugging-extension.md)을 사용하여 덤프를 분석할 수 있습니다.

## <a name="see-also"></a>참고 항목

- SOS 확장 설치에 대한 자세한 내용은 [dotnet-sos](dotnet-sos.md)를 참조하세요.
- 기호 다운로드 도구 설치 및 사용에 대한 자세한 내용은 [dotnet-symbol](dotnet-symbol.md)을 참조하세요.
- 유용한 FAQ를 포함하여 디버깅에 대한 자세한 내용은 [.NET Core 진단 리포지토리](https://github.com/dotnet/diagnostics/blob/master/documentation/)를 참조하세요.
- Linux 또는 Mac에 LLDB를 설치하는 방법에 관한 지침은 [LLDB 설치](https://github.com/dotnet/diagnostics/blob/master/documentation/sos.md#getting-lldb)를 참조하세요.
