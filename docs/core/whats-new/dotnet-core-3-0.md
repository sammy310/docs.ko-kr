---
title: .NET Core 3.0의 새로운 기능
description: .NET Core 3.0에 있는 새로운 기능에 대해 알아봅니다.
dev_langs:
- csharp
author: thraka
ms.author: adegeo
ms.date: 10/22/2019
ms.openlocfilehash: 4bf1c4826273535bfe824828f0fad96998b29483
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742595"
---
# <a name="whats-new-in-net-core-30"></a>.NET Core 3.0의 새로운 기능

이 문서에서는 .NET Core 3.0의 새로운 기능을 설명합니다. 가장 중요한 개선 사항 중 하나는 Windows 데스크톱 애플리케이션에 대한 지원(Windows만 해당)입니다. .NET Core 3.0 SDK 구성 요소 Windows 데스크톱을 사용하여 Windows Forms 및 Windows Presentation Foundation(WPF) 애플리케이션을 포트할 수 있습니다. 분명히 말하지만, Windows 데스크톱 구성 요소는 Windows에서만 지원되고 포함됩니다. 자세한 내용은 이 문서 후반부의 [Windows 데스크톱](#windows-desktop) 섹션을 참조하세요.

.NET Core 3.0에서는 C# 8.0에 대한 지원이 추가되었습니다. [Visual Studio 2019 버전 16.3](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) 이상, [Mac용 Visual Studio 8.3](/visualstudio/mac/install-preview) 이상 또는 [Visual Studio Code](https://code.visualstudio.com/)를 최신 **C# 확장**과 함께 사용하는 것이 좋습니다.

Windows, macOS 또는 Linux에서 지금 바로 [.NET Core 3.0을 다운로드하여 시작](https://aka.ms/netcore3download)하세요.

릴리스에 대한 자세한 내용은 [.NET Core 3.0 알림](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-0/)을 참조하세요.

.NET Core RC1은 Microsoft에서 프로덕션용으로 간주되었으며 완전히 지원되었습니다. 미리 보기 릴리스를 사용하는 경우, 계속 지원을 받으려면 RTM 버전으로 이동해야 합니다.

## <a name="language-improvements-c-80"></a>언어 향상 C# 8.0

[Null 허용 참조 형식](../../csharp/tutorials/nullable-reference-types.md) 기능,[ 비동기 스트림](../../csharp/tutorials/generate-consume-asynchronous-stream.md), [추가 패턴](../../csharp/tutorials/pattern-matching.md) 등을 포함하는 C# 8.0도 이 릴리스의 일부입니다. C# 8.0 기능에 대한 자세한 내용은 [C# 8.0의 새로운 기능](../../csharp/whats-new/csharp-8.md)을 참조하세요.

아래에 설명된 다음 API 기능을 지원하기 위해 언어 향상 기능이 추가되었습니다.

- [범위 및 인덱스](#ranges-and-indices)
- [비동기 스트림](#async-streams)

## <a name="net-standard-21"></a>.NET Standard 2.1

.NET Core 3.0에서는 **.NET Standard 2.1**을 구현합니다. 하지만 기본 `dotnet new classlib` 템플릿은 여전히 **.NET Standard 2.0**을 대상으로 하는 프로젝트를 생성합니다. **.NET 표준 2.1**을 대상으로 지정하려면 프로젝트 파일을 편집하고 `TargetFramework` 속성을 `netstandard2.1`로 변경하세요.

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.1</TargetFramework>
  </PropertyGroup>

</Project>
```

Visual Studio를 사용하고 있는 경우 Visual Studio 2017은 **.NET Standard 2.1** 또는 **.NET Core 3.0**을 지원하지 않으므로 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)가 필요합니다.

## <a name="compiledeploy"></a>컴파일/배포

### <a name="default-executables"></a>기본 실행 파일

이제 .NET Core에서 기본적으로 [프레임워크 종속 실행 파일](../deploying/index.md#framework-dependent-executables-fde)을 빌드합니다. 이는 전역적으로 설치된 .NET Core 버전을 사용하는 애플리케이션을 위한 새로운 동작입니다. 지금까지는 [자체 포함 배포](../deploying/index.md#self-contained-deployments-scd)만 실행 파일을 생성했습니다.

사용 중인 SDK의 환경 및 플랫폼과 일치하는 경우 `dotnet build` 또는 `dotnet publish` 중에 실행 파일이 생성됩니다. 다른 네이티브 실행 파일과 마찬가지로 이러한 실행 파일에서도 다음과 같은 동일한 기능을 예상할 수 있습니다.

- 실행 파일을 두 번 클릭할 수 있습니다.
- Windows의 `myapp.exe`, Linux 및 macOS의 `./myapp`과 같은 애플리케이션을 명령 프롬프트에서 직접 시작할 수 있습니다.

### <a name="single-file-executables"></a>단일 실행 파일

`dotnet publish` 명령은 플랫폼별 단일 실행 파일로 앱 패키징을 지원합니다. 실행 파일은 자동 압축 풀기 파일이며 앱을 실행하는 데 필요한 모든 종속 항목(네이티브 포함)을 포함하고 있습니다. 앱을 처음 실행하면 애플리케이션은 앱 이름과 빌드 식별자에 기반하여 디렉터리로 압축이 풀립니다. 해당 애플리케이션을 다시 실행하면 시작이 빨라집니다. 새 버전을 사용한 경우가 아니라면 두 번째에는 애플리케이션의 압축을 풀 필요가 없습니다.

단일 실행 파일을 게시하려면 `dotnet publish` 명령을 사용하여 프로젝트 또는 명령줄에 `PublishSingleFile`을 설정합니다.

```xml
<PropertyGroup>
  <RuntimeIdentifier>win10-x64</RuntimeIdentifier>
  <PublishSingleFile>true</PublishSingleFile>
</PropertyGroup>
```

또는

```dotnetcli
dotnet publish -r win10-x64 -p:PublishSingleFile=true
```

단일 파일 게시에 대한 자세한 내용은 [단일 파일 번들러 설계 문서](https://github.com/dotnet/designs/blob/master/accepted/single-file/design.md)를 참조하세요.

### <a name="assembly-linking"></a>어셈블리 연결

.NET Core SDK 3.0에는 IL을 분석하고 사용되지 않는 어셈블리를 잘라내어 앱의 크기를 줄일 수 있는 도구가 포함되어 있습니다.

자체 포함 앱에는 호스트 컴퓨터에 .NET을 설치하지 않고도 코드를 실행하는 데 필요한 모든 요소가 포함됩니다. 그러나 앱을 실행하는 데 프레임워크의 작은 하위 집합만 필요한 경우가 많으므로 사용되지 않는 다른 라이브러리를 제거할 수 있습니다.

이제 .NET Core에 [IL 링커](https://github.com/mono/linker) 도구를 사용하여 앱의 IL을 검사하는 설정이 포함되어 있습니다. 이 도구는 필요한 코드를 검색한 다음, 사용되지 않는 라이브러리를 자릅니다. 이 도구를 통해 일부 앱의 배포 크기를 훨씬 줄일 수 있습니다.

이 도구를 사용하려면 프로젝트에서 `<PublishTrimmed>` 설정을 추가하고 자체 포함 앱을 게시합니다.

```xml
<PropertyGroup>
  <PublishTrimmed>true</PublishTrimmed>
</PropertyGroup>
```

```dotnetcli
dotnet publish -r <rid> -c Release
```

예를 들어 포함된 기본 “hello world” 새 콘솔 프로젝트 템플릿은 게시될 때 크기가 약 70MB입니다. `<PublishTrimmed>`를 사용하면 크기가 약 30MB로 줄어듭니다.

잘라낼 때 리플렉션이나 관련된 동적 기능을 사용하는 애플리케이션 또는 프레임워크 (ASP.NET Core, WPF 등)가 중단되는 경우가 많다는 것을 고려해야 합니다. 이러한 중단은 링커에서 이 동적 동작을 알지 못하고 리플렉션에 필요한 프레임워크 유형을 확인할 수 없기 때문에 발생합니다. 이 시나리오를 인식하도록 IL 링커 도구를 구성할 수 있습니다.

무엇보다도, 잘라낸 후 앱을 테스트해야 합니다.

IL 링커 도구에 대한 자세한 내용은 [문서](https://aka.ms/dotnet-illink)또는 [mono/linker]( https://github.com/mono/linker) 리포지토리를 참조하세요.

### <a name="tiered-compilation"></a>계층화된 컴파일

[계층화된 컴파일](https://github.com/dotnet/runtime/blob/master/docs/design/features/tiered-compilation-guide.md)(TC)은 .NET Core 3.0에서 기본적으로 켜져 있습니다. 런타임 시 JIT(Just-In-Time) 컴파일러를 더욱 유연하게 사용하여 성능을 개선할 수 있도록 하는 기능입니다.

계층화된 컴파일의 주요 혜택은 품질은 낮지만 빠른 계층의 (재)JIT 메서드 또는 품질은 높지만 느린 계층의 (재)JIT 메서드의 두 가지 방법을 제공하는 것입니다. 품질은 메서드가 얼마나 제대로 최적화되었는지를 나타냅니다. TC는 시작에서 정적인 상태까지 다양한 실행 단계를 거치므로 애플리케이션의 성능을 개선하는 데 도움이 됩니다. 계층화된 컴파일을 사용하지 않도록 설정하는 경우 모든 메서드는 시작 성능보다 정적인 상태 성능에 편향된 단일 방식으로 컴파일됩니다.

TC를 사용하도록 설정하면 앱이 시작될 때 메서드 컴파일에 다음과 같은 동작이 적용됩니다.

- 메서드에 Ahead Of Time 컴파일 코드([ReadyToRun](#readytorun-images))가 있는 경우 사전 생성된 코드가 사용됩니다.
- 그렇지 않으면 메서드가 JIT 컴파일됩니다. 일반적으로 이 메서드는 값 형식의 제네릭입니다.
  - *빠른 JIT*은 품질이 더 낮거나 덜 최적화된 코드를 더욱 빠르게 생성합니다. .NET Core 3.0에서 빠른 JIT는 루프를 포함하지 않은 메서드에 기본적으로 사용하도록 설정되며, 시작하는 동안 사용하는 것이 좋습니다.
  - 완전히 최적화된 JIT는 품질이 더 높거나 더 최적화된 코드를 더욱 느리게 생성합니다. 빠른 JIT를 사용하지 않는 메서드의 경우(예: 메서드가 <xref:System.Runtime.CompilerServices.MethodImplOptions.AggressiveOptimization?displayProperty=nameWithType>(으)로 특성이 지정된 경우) 완전히 최적화된 JIT가 사용됩니다.

자주 호출되는 메서드의 경우 Just-In-Time 컴파일러는 결과적으로 백그라운드에서 완전히 최적화된 코드를 만듭니다. 그런 다음, 최적화된 코드는 해당 메서드에 대해 미리 컴파일된 코드를 대체합니다.

빠른 JIT에 의해 생성된 코드는 실행 속도가 저하되거나, 더 많은 메모리를 할당하거나, 더 많은 스택 공간을 사용할 수 있습니다. 이슈가 있는 경우 프로젝트 파일에서 이 MSBuild 속성을 사용하여 빠른 JIT를 사용하지 않도록 설정할 수 있습니다.

```xml
<PropertyGroup>
  <TieredCompilationQuickJit>false</TieredCompilationQuickJit>
</PropertyGroup>
```

TC를 완전히 사용하지 않도록 설정하려면 프로젝트 파일에서 이 MSBuild 속성을 사용합니다.

```xml
<PropertyGroup>
  <TieredCompilation>false</TieredCompilation>
</PropertyGroup>
```

> [!TIP]
> 프로젝트 파일에서 이러한 설정을 변경하는 경우 새 설정이 반영되도록 클린 빌드(`obj` 및 `bin` 디렉터리를 삭제한 후 다시 빌드)를 수행해야 할 수 있습니다.

런타임에 컴파일을 구성하는 방법에 대한 자세한 내용은 [컴파일을 위한 런타임 구성 옵션](../run-time-config/compilation.md)를 참조하세요.

### <a name="readytorun-images"></a>ReadyToRun 이미지

R2R(ReadyToRun) 형식으로 애플리케이션 어셈블리를 컴파일하면 .NET Core 애플리케이의 시작 시간을 향상할 수 있습니다. R2R은 AOT(Ahead-Of-Time) 컴파일 양식입니다.

R2R 이진 파일은 애플리케이션이 로드될 때 JIT(Just-In-Time) 컴파일러에서 수행해야 하는 작업량을 줄여 시작 성능을 향상합니다. 이진 파일에는 JIT에서 생성되는 코드와 비슷한 네이티브 코드가 포함되어 있습니다. 그러나 R2R 이진 파일은 일부 시나리오에서 필요한 IL(중간 언어) 코드와 동일한 코드의 네이티브 버전을 모두 포함하므로 크기가 더 큽니다. R2R은 Linux x64 또는 Windows x64와 같은 특정 런타임 환경(RID)을 대상으로 하는 자체 포함 앱을 게시하는 경우에만 사용할 수 있습니다.

프로젝트를 ReadyToRun으로 컴파일하려면 다음을 수행합니다.

01. 프로젝트에 `<PublishReadyToRun>` 설정 추가:

    ```xml
    <PropertyGroup>
      <PublishReadyToRun>true</PublishReadyToRun>
    </PropertyGroup>
    ```

01. 자체 포함 앱을 게시합니다. 예를 들어 이 명령은 Windows 64비트 버전용 자체 포함 앱을 만듭니다.

    ```dotnetcli
    dotnet publish -c Release -r win-x64 --self-contained
    ```

#### <a name="cross-platformarchitecture-restrictions"></a>교차 플랫폼/아키텍처 제한 사항

현재 ReadyToRun 컴파일러는 교차 대상 지정을 지원하지 않습니다. 지정된 대상에서 컴파일해야 합니다. 예를 들어 Windows x64용 R2R 이미지를 만들려는 경우 해당 환경에서 게시 명령을 실행해야 합니다.

교차 대상 지정 예외:

- Windows x64를 사용하여 Windows ARM32, ARM64 및 x86 이미지를 컴파일할 수 있습니다.
- Windows x86을 사용하여 Windows ARM32 이미지를 컴파일할 수 있습니다.
- Linux X64를 사용하여 Linux ARM32 및 ARM64 이미지를 컴파일할 수 있습니다.

## <a name="runtimesdk"></a>런타임/SDK

### <a name="major-version-roll-forward"></a>주 버전 롤포워드

.NET Core 3.0은 애플리케이션을 .NET Core의 최신 주 버전으로 롤포워드할 수 있는 옵트인(opt-in) 기능을 소개합니다. 또한, 롤포워드가 애플리케이션에 적용되는 방식을 제어하기 위해 새 설정이 추가되었습니다. 이 설정은 다음과 같은 방법으로 구성할 수 있습니다.

- 프로젝트 파일 속성: `RollForward`
- 런타임 구성 파일 속성: `rollForward`
- 환경 변수: `DOTNET_ROLL_FORWARD`
- 명령줄 인수: `--roll-forward`

다음 값 하나를 지정해야 합니다. 설정을 생략하면 **Minor**가 기본값입니다.

- **LatestPatch**\
가장 높은 패치 버전으로 롤포워드합니다. 부 버전 롤포워드를 사용하지 않도록 설정합니다.
- **Minor**\
요청된 부 버전이 없을 경우 가장 낮은 높은 부 버전으로 롤포워드합니다. 요청된 부 버전이 있다면 **LatestPatch** 정책이 사용됩니다.
- **Major**\
요청된 주 버전이 없을 경우 가장 낮은 높은 주 버전으로 롤포워드합니다. 요청된 주 버전이 있다면 **Minor** 정책이 사용됩니다.
- **LatestMinor**\
요청된 부 버전이 있는 경우에도 가장 높은 부 버전으로 롤포워드합니다. 구성 요소 호스팅 시나리오를 위한 것입니다.
- **LatestMajor**\
요청된 주 버전이 있는 경우에도 가장 높은 주, 가장 높은 부 버전으로 롤포워드합니다. 구성 요소 호스팅 시나리오를 위한 것입니다.
- **Disable**\
롤포워드하지 않습니다. 지정된 버전에만 바인딩합니다. 이 정책은 최신 패치를 롤포워드할 수 있는 기능을 사용하지 않도록 설정하므로 일반 용도에는 좋지 않습니다. 이 값은 테스트용으로만 사용하는 것이 좋습니다.

**Disable** 설정 이외에도 모든 설정에서 사용 가능한 가장 높은 패치 버전을 사용합니다.

### <a name="build-copies-dependencies"></a>빌드 복사본 종속성

`dotnet build` 명령은 이제 애플리케이션에 대한 NuGet 종속성을 NuGet 캐시에서 빌드 출력 폴더로 복사합니다. 이전에는 종속성이 `dotnet publish` 중에만 복사되었습니다.

연결, Razor 페이지 게시 등 여전히 게시해야 하는 일부 작업이 있습니다.

### <a name="local-tools"></a>로컬 도구

.NET core 3.0에서는 로컬 도구를 소개합니다. 로컬 도구는 [전역 도구](../tools/global-tools.md)와 유사하지만 디스크의 특정 위치와 연결됩니다. 로컬 도구는 전역적으로 사용할 수 없으며 NuGet 패키지로 배포됩니다.

> [!WARNING]
> .NET Core 3.0 미리 보기 1에서 `dotnet tool restore` 또는 `dotnet tool install` 삭제와 같은 현지 도구를 사용했다면 로컬 도구 캐시 폴더를 삭제하세요. 그렇지 않으면 로컬 도구는 모든 최신 릴리스에서 작동하지 않습니다. 이 폴더의 위치는 다음과 같습니다.
>
> macOS, Linux: `rm -r $HOME/.dotnet/toolResolverCache`
>
> Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`

로컬 도구는 현재 디렉터리에 있는 매니페스트 파일 이름 `dotnet-tools.json`을 사용합니다. 이 매니페스트 파일은 해당 폴더 및 그 아래에서 사용할 수 있는 도구를 정의합니다. 코드를 사용하는 누구나 동일한 도구를 복구하고 사용할 수 있도록 코드로 매니페스트 파일을 배포할 수 있습니다.

전역 도구와 로컬 도구 둘 다, 호환되는 버전의 런타임이 필요합니다. 현재 NuGet.org의 많은 도구는 .NET Core 런타임 2.1을 대상으로 합니다. 이러한 도구를 전역 또는 로컬로 설치하려면 여전히 [NET Core 2.1 런타임](https://dotnet.microsoft.com/download/dotnet-core/2.1)을 설치해야 합니다.

### <a name="smaller-garbage-collection-heap-sizes"></a>더 작은 가비지 수집 힙 크기

가비지 수집기의 기본 힙 크기가 감소되어 .NET Core에서 사용되는 메모리가 줄어듭니다. 이러한 변화는 최신 프로세서 캐시 크기의 생성 0 할당 예산과 부합됩니다.

### <a name="garbage-collection-large-page-support"></a>가비지 수집 Large Page 지원

Large Page(또는 Linux Huge Page)는 운영 체제가 이러한 큰 페이지를 요청하는 애플리케이션의 성능을 개선하기 위해 네이티브 페이지 크기(보통 4K)보다 더 큰 메모리 영역을 구축할 수 있는 기능입니다.

이제 가비지 수집기는 Windows에서 큰 페이지를 할당하기 위해 선택할 수 있는 옵트인(opt-in) 기능으로 **GCLargePages** 설정을 사용하여 구성할 수 있습니다.

## <a name="windows-desktop--com"></a>Windows 데스크톱 및 COM

### <a name="net-core-sdk-windows-installer"></a>.NET Core SDK Windows Installer

Windows용 MSI 설치 관리자는 .NET Core 3.0부터 변경되었습니다. 이제 SDK 설치 관리자는 준비된 SDK 기반 밴드 릴리스를 하려고 합니다. 기능 밴드는 번호 버전의 *패치* 섹션에서 *수백 개*의 그룹에 정의되어 있습니다. 예를 들어, **3.0._101_** 및 **3.0._201_** 은 두 가지 기능 밴드의 버전이며, **3.0._101_** 및 **3.0._199_** 는 동일한 기능 밴드에 있습니다. 그리고 .NET Core SDK **3.0._101_** 이 설치되어 있는 경우 .NET Core SDK**3.0._100_** 은 머신에서 제거됩니다. .NET Core SDK **3.0._200_** 이 동일한 머신에 설치되어 있는 경우 .NET Core SDK **3.0._101_** 은 제거되지 않습니다.

버전 관리에 대한 자세한 내용은 [.NET Core의 버전 관리 방법](../versions/index.md)을 참조하세요.

### <a name="windows-desktop"></a>Windows 바탕 화면

.NET Core 3.0은 Windows Presentation Foundation(WPF) 및 Windows Forms를 사용하여 Windows 데스크톱 애플리케이션을 지원합니다. 이러한 프레임워크는 [XAML 아일랜드](/windows/uwp/xaml-platform/xaml-host-controls)를 통해 Windows UI XAML 라이브러리(WinUI)의 최신 컨트롤 및 Fluent 스타일을 사용하는 것도 지원합니다.

Windows 데스크톱 구성 요소는 Windows .NET Core 3.0 SDK의 일부입니다.

다음 `dotnet` 명령을 사용하여 새 WPF 또는 Windows Forms 앱을 만들 수 있습니다.

```dotnetcli
dotnet new wpf
dotnet new winforms
```

Visual Studio 2019에는 .NET Core 3.0 Windows Forms 및 WPF용 **새 프로젝트** 템플릿이 추가됩니다.

기존 .NET Framework 애플리케이션을 포트하는 방법에 대한 자세한 내용은 [WPF 프로젝트 포트](../../desktop-wpf/migration/convert-project-from-net-framework.md) 및 [Windows Forms 프로젝트 포트](../porting/winforms.md)를 참조하세요.

#### <a name="winforms-high-dpi"></a>WinForms의 높은 DPI

.NET Core Windows Forms 애플리케이션은 <xref:System.Windows.Forms.Application.SetHighDpiMode(System.Windows.Forms.HighDpiMode)?displayProperty=nameWithType>을(를) 사용하여 높은 DPI 모드를 설정할 수 있습니다. `SetHighDpiMode` 메서드는 해당 설정이 `Application.Run` 전에 `App.Manifest` 또는 P/Invoke와 같은 다른 수단으로 설정된 경우가 아니라면 해당하는 높은 DPI 모드를 설정합니다.

<xref:System.Windows.Forms.HighDpiMode?displayProperty=nameWithType> 열거형으로 표현되는 가능한 `highDpiMode` 값은 다음과 같습니다.

- `DpiUnaware`
- `SystemAware`
- `PerMonitor`
- `PerMonitorV2`
- `DpiUnawareGdiScaled`

높은 DPI 모드에 대한 자세한 내용은 [Windows에서 높은 DPI 데스크톱 애플리케이션 개발](/windows/desktop/hidpi/high-dpi-desktop-application-development-on-windows)을 참조하세요.

### <a name="create-com-components"></a>COM 구성 요소 생성

Windows에서 이제는 COM 호출 가능 관리형 구성 요소를 생성할 수 있습니다. 이 기능은 COM 추가 기능 모델을 통해 .NET Core를 사용할 뿐만 아니라 .NET Framework에 패리티를 제공하는 데 중요합니다.

*mscoree.dll*이 COM 서버처럼 사용되는 .NET Framework와는 달리, .NET Core는 COM 구성 요소 빌드 시 네이티브 시작 관리자 dll을 *bin* 디렉터리에 추가합니다.

COM 구성 요소를 만들고 사용하는 방법에 대한 예는 [COM 데모](https://github.com/dotnet/samples/tree/master/core/extensions/COMServerDemo)를 참조하세요.

### <a name="windows-native-interop"></a>Windows 네이티브 Interop

Windows는 플랫 C API, COM 및 WinRT의 형태로 다양한 네이티브 API를 제공합니다. .NET Core에서는 **P/Invoke**를 지원하지만, .NET Core 3.0은 **CoCreate COM API** 및 **Activate WinRT API**에 대한 기능을 추가합니다. 코드 예제는 [Excel 데모](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)를 참조하세요.

### <a name="msix-deployment"></a>MSIX 배포

[MSIX](https://docs.microsoft.com/windows/msix/)는 새로운 Windows 애플리케이션 패키지 형식입니다. Windows 10에 .NET Core 3.0 데스크톱 애플리케이션을 배포하는 데 사용할 수 있습니다.

Visual Studio 2019에 제공되는 [Windows 애플리케이션 패키징 프로젝트](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)를 사용하면 [자체 포함](../deploying/index.md#self-contained-deployments-scd) .NET Core 애플리케이션을 사용하여 MSIX 패키지를 만들 수 있습니다.

NET Core 프로젝트 파일은 `<RuntimeIdentifiers>` 속성에 지원되는 런타임을 지정해야 합니다.

```xml
<RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
```

## <a name="linux-improvements"></a>Linux 기능 향상

### <a name="serialport-for-linux"></a>Linux용 SerialPort

.NET Core 3.0은 Linux에서 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>에 대한 기본 지원을 제공합니다.

이전에는 .NET Core가 Windows에서만 `SerialPort` 사용을 지원했습니다.

Linux의 제한적 직렬 포트 지원에 대한 자세한 내용은 [GitHub 이슈 #33146](https://github.com/dotnet/corefx/issues/33146)을 참조하세요.

### <a name="docker-and-cgroup-memory-limits"></a>Docker 및 cgroup 메모리 한도

Docker를 사용하여 Linux에서 .NET Core 3.0을 실행하면 cgroup 메모리 한도에 훨씬 더 효과적입니다. 메모리 한도가 있는 Docker 컨테이너를 실행하면(`docker run -m` 사용) .NET Core 동작 방식이 바뀝니다.

- 기본 가비지 수집기(GC) 힙 크기: 최대 20mb 또는 컨테이너에서 75%의 메모리 한도
- 명시적 크기는 절대수 또는 cgroup 한도의 비율로 설정할 수 있습니다.
- GC 힙당 최소 예약된 세그먼트 크기는 16mb입니다. 이 크기는 머신에서 생성된 힙 수를 줄여 줍니다.

### <a name="gpio-support-for-raspberry-pi"></a>Raspberry Pi에 대한 GPIO 지원

GPIO 프로그래밍에 사용할 수 있는 두 개의 패키지가 NuGet에 릴리스되었습니다.

- [System.Device.Gpio](https://www.nuget.org/packages/System.Device.Gpio)
- [Iot.Device.Bindings](https://www.nuget.org/packages/Iot.Device.Bindings)

GPIO 패키지에는 *GPIO*, *SPI*, *I2C* 및 *PWM*디바이스용 API가 포함됩니다. IoT 바인딩 패키지에 디바이스 바인딩이 포함되어 있습니다. 자세한 내용은 [디바이스 GitHub 리포지토리](https://github.com/dotnet/iot/blob/master/src/devices/)를 참조하세요.

### <a name="arm64-linux-support"></a>ARM64 Linux 지원

.NET Core 3.0에서는 Linux용 ARM64에 대한 지원이 추가되었습니다. ARM64는 현재 IoT 시나리오에서 주로 사용됩니다. 자세한 내용은 [.NET Core ARM64 상태](https://github.com/dotnet/announcements/issues/82)를 참조하세요.

[ARM64의 .NET Core에 대한 Docker 이미지](https://hub.docker.com/r/microsoft/dotnet/)를 Alpine, Debian 및 Ubuntu에 사용할 수 있습니다.

> [!NOTE]
> **ARM64** Windows 지원은 아직 사용할 수 없습니다.

## <a name="security"></a>보안

### <a name="tls-13--openssl-111-on-linux"></a>Linux의 TLS 1.3 및 OpenSSL 1.1.1

이제 .NET Core는 지정된 환경에서 사용 가능한 경우 [OpenSSL 1.1.1의 TLS 1.3 지원](https://www.openssl.org/blog/blog/2018/09/11/release111/)을 이용합니다. TLS 1.3:

- 클라이언트와 서버 간에 필요한 왕복 횟수가 감소하여 연결 시간이 향상됩니다.
- 더 이상 사용하지 않고 안전하지 않은 암호화 알고리즘을 제거하므로 보안이 향상됩니다.

사용 가능한 경우 .NET Core 3.0은 Linux 시스템에서 **OpenSSL 1.1.1**, **OpenSSL 1.1.0** 또는 **OpenSSL 1.0.2**를 사용합니다. **OpenSSL 1.1.1**이 사용 가능한 경우 <xref:System.Net.Security.SslStream?displayProperty=nameWithType> 및 <xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 형식은 **TLS 1.3**을 사용합니다(클라이언트와 서버 둘 다 **TLS 1.3**을 지원한다고 가정).

> [!IMPORTANT]
> Windows 및 macOS에서는 아직 **TLS 1.3**을 지원하지 않습니다. 지원이 제공되면 .NET Core 3.0은 이러한 운영 체제에서 **TLS 1.3**을 지원합니다.

다음 C# 8.0 예제는 <https://www.cloudflare.com>에 연결하는 Ubuntu 18.10의 .NET Core 3.0을 보여 줍니다.

[!code-csharp[TLSExample](~/samples/snippets/core/whats-new/whats-new-in-30/cs/TLS.cs#TLS)]

### <a name="cryptography-ciphers"></a>암호화 암호

.NET 3.0은 각각 <xref:System.Security.Cryptography.AesGcm?displayProperty=nameWithType> 및 <xref:System.Security.Cryptography.AesCcm?displayProperty=nameWithType>으로 구현된 **AES-GCM** 및 **AES-CCM** 암호에 대한 지원을 추가했습니다. 이러한 알고리즘은 둘 다 [AEAD(Authenticated Encryption with Association Data) 알고리즘](https://en.wikipedia.org/wiki/Authenticated_encryption)입니다.

다음 코드는 `AesGcm` 암호를 사용하여 임의 데이터를 암호화하고 암호를 해독하는 방법을 보여 줍니다.

[!code-csharp[AesGcm](~/samples/snippets/core/whats-new/whats-new-in-30/cs/Cipher.cs#AesGcm)]

### <a name="cryptographic-key-importexport"></a>암호화 키 가져오기/내보내기

.NET Core 3.0은 표준 형식에서 비대칭 퍼블릭 키와 프라이빗 키를 가져오고 내보낼 수 있도록 지원합니다. X.509 인증서를 사용할 필요가 없습니다.

모든 키 형식(*RSA*, *DSA*, *ECDsa* 및 *ECDiffieHellman*)에서 다음 형식을 지원합니다.

- **공개 키**
  - X.509 SubjectPublicKeyInfo

- **프라이빗 키**
  - PKCS#8 PrivateKeyInfo
  - PKCS#8 EncryptedPrivateKeyInfo

RSA 키는 다음도 지원합니다.

- **공개 키**
  - PKCS#1 RSAPublicKey

- **프라이빗 키**
  - PKCS#1 RSAPrivateKey

내보내기 메서드는 DER로 인코드된 이진 데이터를 생성하고, 가져오기 메서드도 동일한 동작을 예상합니다. 키가 텍스트에 편리한 PEM 형식으로 저장된 경우 호출자는 가져오기 메서드를 호출하기 전에 콘텐츠를 base64로 디코드해야 합니다.

[!code-csharp[RSA](~/samples/snippets/core/whats-new/whats-new-in-30/cs/RSA.cs#Rsa)]

**PKCS#8** 파일은 <xref:System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo?displayProperty=nameWithType>로 검사하고 **PFX/PKCS#12** 파일은 <xref:System.Security.Cryptography.Pkcs.Pkcs12Info?displayProperty=nameWithType>로 검사할 수 있습니다. **PFX/PKCS#12** 파일은 <xref:System.Security.Cryptography.Pkcs.Pkcs12Builder?displayProperty=nameWithType>로 조작할 수 있습니다.

## <a name="net-core-30-api-changes"></a>.NET Core 3.0 API 변경 내용

### <a name="ranges-and-indices"></a>범위 및 인덱스

새 <xref:System.Index?displayProperty=nameWithType> 형식을 인덱싱에 사용할 수 있습니다. 시작부터 계산되는 `int`의 인덱스를 만들거나, 접두사 `^` 연산자(C#)를 사용하여 끝부터 계산되는 인덱스를 만들 수 있습니다.

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

시작 인덱스와 끝 인덱스의 두 `Index` 값으로 구성되고 `x..y` 범위 식(C#)으로 작성할 수 있는 <xref:System.Range?displayProperty=nameWithType> 유형도 있습니다. 그런 다음, 조각을 생성하는 `Range`로 인덱싱할 수 있습니다.

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

자세한 내용은 [범위 및 인덱스 자습서](../../csharp/tutorials/ranges-indexes.md)를 참조하세요.

### <a name="async-streams"></a>비동기 스트림

<xref:System.Collections.Generic.IAsyncEnumerable%601> 형식은 <xref:System.Collections.Generic.IEnumerable%601>의 새로운 비동기 버전입니다. 이 언어를 사용하면 `IAsyncEnumerable<T>`을 통해 `await foreach`를 수행하여 요소를 사용하고 `yield return`을 사용하여 요소를 생성할 수 있습니다.

다음 예제에서는 비동기 스트림의 생성 및 사용을 둘 다 보여 줍니다. `foreach` 문은 비동기이며, `yield return`을 사용하여 호출자에 대한 비동기 스트림을 생성합니다. 이 패턴(`yield return` 사용)은 비동기 스트림 생성을 위한 권장 모델입니다.

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

`await foreach`를 수행할 수 있을 뿐 아니라, 비동기 반복기(예: `await` 및 `yield`가 둘 다 가능한 `IAsyncEnumerable/IAsyncEnumerator`를 반환하는 반복기)를 만들 수도 있습니다. 삭제해야 하는 개체의 경우 `Stream` 및 `Timer`와 같은 다양한 BCL 유형이 구현하는 `IAsyncDisposable`을 사용할 수 있습니다.

자세한 내용은 [비동기 스트림 자습서](../../csharp/tutorials/generate-consume-asynchronous-stream.md)를 참조하세요.

### <a name="ieee-floating-point"></a>IEEE 부동 소수점

부동 소수점 API는 [IEEE 754-2008 개정판](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)을 준수하도록 업데이트되고 있습니다. 이러한 변경의 목표는 **필요한** 모든 작업을 노출하고 이 작업이 IEEE 사양을 준수하는지 확인하는 것입니다. 부동 소수점 개선 사항에 대한 자세한 내용은 [.NET Core 3.0에서 부동 소수점 구문 분석 및 서식 지정 개선 사항](https://devblogs.microsoft.com/dotnet/floating-point-parsing-and-formatting-improvements-in-net-core-3-0/)을 참조하세요.

구문 분석 및 서식 지정 개선 사항:

- 모든 길이의 입력을 올바르게 구문 분석하고 반올림합니다.
- 음수 0을 올바르게 구문 분석하고 형식을 지정합니다.
- 대/소문자를 구분하지 않는 검사를 수행하여 `Infinity`와 `NaN`을 올바르게 구문 분석하고, 적용 가능한 경우 선행 `+` 옵션을 허용합니다.

새 <xref:System.Math?displayProperty=nameWithType> API의 구성 내용:

- <xref:System.Math.BitIncrement(System.Double)> 및 <xref:System.Math.BitDecrement(System.Double)>\
`nextUp` 및 `nextDown` IEEE 연산에 해당합니다. 입력보다 크거나 작은 값을 각각 비교하는 최소 부동 소수점 숫자를 반환합니다. 예를 들어 `Math.BitIncrement(0.0)`는 `double.Epsilon`을 반환합니다.

- <xref:System.Math.MaxMagnitude(System.Double,System.Double)> 및 <xref:System.Math.MinMagnitude(System.Double,System.Double)>\
`maxNumMag` 및 `minNumMag` IEEE 연산에 해당하며 두 입력의 규모 중 더 크거나 작은 값을 반환합니다. 예를 들어 `Math.MaxMagnitude(2.0, -3.0)`는 `-3.0`을 반환합니다.

- <xref:System.Math.ILogB(System.Double)>\
`logB` IEEE 연산에 해당하며 정수값을 반환하고, 입력 매개 변수의 정수 이진 로그를 반환합니다. 이 메서드는 `floor(log2(x))`와 사실상 동일하지만 반올림 오류를 최소화하면서 수행됩니다.

- <xref:System.Math.ScaleB(System.Double,System.Int32)>\
정수 값을 취하는 `scaleB` IEEE 연산에 해당하며 사실상 `x * pow(2, n)`을 반환하지만 반올림 오류를 최소화하면서 수행됩니다.

- <xref:System.Math.Log2(System.Double)>\
`log2` IEEE 연산에 해당하며, 기본-2 로그를 반환합니다. 반올림 오류를 최소화합니다.

- <xref:System.Math.FusedMultiplyAdd(System.Double,System.Double,System.Double)>\
`fma` IEEE 연산에 해당하며, 단일 곱셈 누산기(fused multiply add) 계산을 수행합니다. 다시 말해, `(x * y) + z`을(를) 단일 연산으로 수행하기 때문에 반올림 오류가 최소화됩니다. 예를 들어 `FusedMultiplyAdd(1e308, 2.0, -1e308)`는 `1e308`을 반환합니다. 일반 `(1e308 * 2.0) - 1e308`은 `double.PositiveInfinity`를 반환합니다.

- <xref:System.Math.CopySign(System.Double,System.Double)>\
`copySign` IEEE 연산에 해당하며, `x`의 값을 반환하지만 `y`의 부호를 반환합니다.

### <a name="net-platform-dependent-intrinsics"></a>.NET 플랫폼 종속 내장 함수

**SIMD** 또는 **비트 조작 명령어** 세트와 같은 특정 perf-oriented CPU 명령어에 대한 액세스를 허용하는 API가 추가되었습니다. 이러한 명령어를 사용하면 특정 시나리오(효율적인 데이터 병렬 처리)에서 성능을 크게 향상시킬 수 있습니다.

적절한 경우 .NET 라이브러리는 성능을 개선하기 위해 이러한 명령을 사용하기 시작했습니다.

자세한 내용은 [.NET 플랫폼 종속 내장 함수](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)를 참조하세요.

### <a name="improved-net-core-version-apis"></a>향상된 .NET Core Version API

.NET Core 3.0부터 .NET Core에 제공된 버전 API가 이제 사용자가 예상하는 정보를 반환합니다. 예:

```csharp
System.Console.WriteLine($"Environment.Version: {System.Environment.Version}");

// Old result
//   Environment.Version: 4.0.30319.42000
//
// New result
//   Environment.Version: 3.0.0
```

```csharp
System.Console.WriteLine($"RuntimeInformation.FrameworkDescription: {System.Runtime.InteropServices.RuntimeInformation.FrameworkDescription}");

// Old result
//   RuntimeInformation.FrameworkDescription: .NET Core 4.6.27415.71
//
// New result (notice the value includes any preview release information)
//   RuntimeInformation.FrameworkDescription: .NET Core 3.0.0-preview4-27615-11
```

> [!WARNING]
> 주요 변경 내용. 버전 관리 체계 변경되었기 때문에 엄밀히 따지면 주요 변경 내용입니다.

### <a name="fast-built-in-json-support"></a>빠른 기본 제공 JSON 지원

.NET 사용자는 [Newtonsoft.Json](https://www.newtonsoft.com/json) 및 여전히 유용한 기타 인기 있는 JSON 라이브러리를 많이 사용해 왔습니다. `Newtonsoft.Json`은 내부적으로 UTF-16인 .NET 문자열을 기본 데이터 형식으로 사용합니다.

새로운 기본 제공 JSON 지원은 고성능, 낮은 할당이며 UTF-8로 인코딩된 JSON 텍스트와 함께 작동합니다. <xref:System.Text.Json> 네임스페이스 및 형식에 대한 자세한 내용은 다음 문서를 참조하세요.

* [.NET의 JSON serialization - 개요](../../standard/serialization/system-text-json-overview.md)
* [.NET에서 JSON을 직렬화 및 역직렬화하는 방법](../../standard/serialization/system-text-json-how-to.md)
* [Newtonsoft.json에서 System.Text.Json으로 마이그레이션하는 방법](../../standard/serialization/system-text-json-migrate-from-newtonsoft-how-to.md)

### <a name="http2-support"></a>HTTP/2 지원

<xref:System.Net.Http.HttpClient?displayProperty=nameWithType> 형식은 HTTP/2 프로토콜을 지원합니다. HTTP/2를 사용할 수 있는 경우 TLS/ALPN을 통해 HTTP 프로토콜 버전이 협상되며, 서버에서 사용하기로 선택하면 HTTP/2가 사용됩니다.

기본 프로토콜은 여전히 HTTP/1.1이지만, 두 가지 방법으로 HTTP/2를 사용할 수 있습니다. 첫째, HTTP/2를 사용하도록 HTTP 요청 메시지를 설정할 수 있습니다.

[!code-csharp[Http2Request](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Request)]

둘째, 기본적으로 HTTP/2를 사용하도록 <xref:System.Net.Http.HttpClient>를 변경할 수 있습니다.

[!code-csharp[Http2Client](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#Client)]

애플리케이션 개발 중에 암호화되지 않은 연결을 사용하려는 경우가 많습니다. 대상 엔드포인트에서 HTTP/2를 사용할 것을 알고 있으면, HTTP/2에 대해 암호화되지 않은 연결을 켤 수 있습니다. `DOTNET_SYSTEM_NET_HTTP_SOCKETSHTTPHANDLER_HTTP2UNENCRYPTEDSUPPORT` 환경 변수를 `1` 로 설정하거나 앱 컨텍스트에서 사용하도록 설정하면 됩니다.

[!code-csharp[Http2Context](~/samples/snippets/core/whats-new/whats-new-in-30/cs/http.cs#AppContext)]

## <a name="next-steps"></a>다음 단계

- [.NET Core 2.2 및 3.0 간의 호환성이 손상되는 변경 검토](../compatibility/2.2-3.0.md)
- [Windows Forms 앱용 .NET Core 3.0의 주요 변경 사항을 검토합니다.](../compatibility/winforms.md#net-core-30)
