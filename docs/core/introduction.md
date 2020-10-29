---
title: .NET 소개 및 개요
description: 다양한 종류의 앱을 빌드하기 위한 무료 오픈 소스 개발 플랫폼인 .NET에 대해 알아봅니다.
author: tdykstra
ms.date: 09/28/2020
ms.custom: updateeachrelease
ms.openlocfilehash: d008fbeabf58a3dddf1ee96fc655b6a685f8edfd
ms.sourcegitcommit: 67ebdb695fd017d79d9f1f7f35d145042d5a37f7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/20/2020
ms.locfileid: "92223582"
---
# <a name="introduction-to-net"></a>.NET 소개

.NET은 다음과 같은 다양한 종류의 앱을 빌드하기 위한 무료 오픈 소스 개발 플랫폼입니다.

* [웹앱, Web API, 마이크로 서비스](/aspnet/core/introduction-to-aspnet-core#recommended-learning-path)
* [클라우드의 서버리스 함수](/azure/azure-functions/functions-create-first-function-vs-code?pivots=programming-language-csharp)
* [클라우드 네이티브 앱](../architecture/cloud-native/index.md)
* [모바일 앱](https://dotnet.microsoft.com/learn/xamarin/hello-world-tutorial/intro)
* 데스크톱 앱
  * [Windows WPF](/dotnet/desktop/wpf/)
  * [Windows Forms](/dotnet/desktop/winforms/)
  * [UWP(유니버설 Windows 플랫폼)](/windows/uwp/get-started/create-a-hello-world-app-xaml-universal)
* [게임](https://dotnet.microsoft.com/learn/games/unity-tutorial/intro)
* [IoT(사물 인터넷)](https://dotnet.microsoft.com/apps/iot)
* [기계 학습](../machine-learning/index.yml)
* [콘솔 앱](tutorials/with-visual-studio-code.md)
* [Windows 서비스](/aspnet/core/host-and-deploy/windows-service)

[클래스 라이브러리](../standard/class-libraries.md)를 사용하여 다양한 앱과 앱 유형 간에 기능을 공유합니다.

.NET을 사용하면 빌드하는 앱 유형과 관계없이 코드 및 프로젝트 파일의 모양과 느낌이 같습니다. 각 앱에서 동일한 런타임, API, 언어 기능에 액세스할 수 있습니다.

## <a name="cross-platform"></a>플랫폼 간

다음을 포함하여 다양한 운영 체제용 .NET 앱을 만들 수 있습니다.

* Windows
* macOS
* Linux
* Android
* iOS
* tvOS
* watchOS

지원되는 프로세서 아키텍처는 다음과 같습니다.

* X64
* x86
* ARM32
* ARM64

.NET을 사용하면 운영 체제 API와 같은 플랫폼별 기능을 사용할 수 있습니다. 예를 들어 Windows의 Windows Forms 및 WPF, Xamarin과 각 모바일 플랫폼 간의 기본 바인딩 등이 있습니다.

자세한 내용은 [지원되는 OS 수명 주기 정책](https://github.com/dotnet/core/blob/master/os-lifecycle-policy.md) 및 [.NET RID 카탈로그](rid-catalog.md)를 참조하세요.

## <a name="open-source"></a>오픈 소스

.NET은 [MIT 및 Apache 2 라이선스](https://github.com/dotnet/runtime/blob/master/LICENSE.TXT)를 사용하는 오픈 소스입니다. .NET은 [.NET Foundation](https://dotnetfoundation.org/) 프로젝트 중 하나입니다.

자세한 내용은 [GitHub.com의 프로젝트 리포지토리 목록](https://github.com/dotnet/core/blob/master/Documentation/core-repos.md)을 참조하세요.

## <a name="support"></a>지원

Microsoft는 Windows, macOS, Linux에서 .NET을 지원합니다. 매달 둘째 화요일에 정기적으로 보안 및 품질이 업데이트됩니다.

Microsoft .NET 이진 배포는 Microsoft에서 유지 관리하는 Azure 서버에서 빌드 및 테스트되고 Microsoft 엔지니어링 및 보안 방식을 따릅니다.

[Red Hat은 RHEL(Red Hat Enterprise Linux)에서 .NET을 지원](https://developers.redhat.com/topics/dotnet/)합니다. Red Hat 및 Microsoft는 협력하여 RHEL에서 .NET Core가 잘 작동하도록 합니다.

[Tizen은 Tizen 플랫폼에서 .NET을 지원](https://developer.tizen.org/development/training/.net-application)합니다.

자세한 내용은 [.NET Core 및 .NET 5 릴리스 및 지원](releases-and-support.md)을 참조하세요.

## <a name="tools-and-productivity"></a>도구 및 생산성

.NET을 사용하면 다양한 언어, IDE(통합 개발 환경), 기타 도구를 선택할 수 있습니다.

### <a name="programming-languages"></a>프로그래밍 언어

.NET은 다음 세 가지 프로그래밍 언어를 지원합니다.

* [C#](../csharp/index.yml)

  C#(“씨샵”이라고 발음합니다.)은 형식이 안전한 최신 개체 지향 프로그래밍 언어입니다. C#은 C 언어 제품군에서 시작되었으며 C, C++, Java 및 JavaScript 프로그래머에게 친숙할 것입니다.

* [F#](../fsharp/index.yml)

  F# 언어는 함수형, 개체 지향 그리고 명령형의 프로그래밍 모델을 지원합니다.

* [Visual Basic](../visual-basic/index.yml)

  .NET 언어 중에서 Visual Basic 구문이 일반적인 인간 언어와 가장 유사하여 쉽게 배울 수 있습니다. Microsoft에서 새로운 기능을 적극적으로 개발하고 있는 C# 및 F#과 달리 Visual Basic 언어는 안정적입니다. 웹앱에서는 Visual Basic이 지원되지 않지만 Web API에서는 지원됩니다.

다음은 .NET 언어에서 지원하는 몇 가지 기능입니다.

* [형식 안전성](../standard/base-types/common-type-system.md)
* 형식 유추 - [C#](../csharp/programming-guide/types/index.md#specifying-types-in-variable-declarations), [F#](../fsharp/language-reference/type-inference.md), [Visual Basic](../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
* [제네릭 형식](../standard/generics.md)
* [대리자](../standard/delegates-lambdas.md)
* [람다](../standard/delegates-lambdas.md)
* [이벤트](../standard/events/index.md)
* [예외](../standard/exceptions/index.md)
* [특성](../standard/attributes/index.md)
* [비동기 코드](../standard/async.md)
* [병렬 프로그래밍](../standard/parallel-programming/index.md)
* [코드 분석기](../fundamentals/code-analysis/overview.md)

### <a name="ides"></a>IDE

.NET 통합 개발 환경에는 다음이 포함됩니다.

* [Visual Studio](https://visualstudio.microsoft.com/vs/)

  Windows에서만 실행됩니다. .NET에서 실행되도록 설계된 다양한 기본 제공 기능이 있습니다. Community 버전은 학생, 오픈 소스 기여자, 개인에게 무료로 제공됩니다.

* [Visual Studio Code](https://code.visualstudio.com/)

  Windows, macOS 및 Linux에서 실행됩니다. 무료 및 오픈 소스. .NET 언어를 사용하기 위한 확장이 제공됩니다.

* [Mac용 Visual Studio](https://visualstudio.microsoft.com/vs/mac/)

  macOS에서만 실행됩니다. iOS, Android, 웹용 .NET 앱과 게임을 개발하는 데 사용됩니다.

* [GitHub Codespaces](https://github.com/features/codespaces)

  현재 베타 버전으로 제공되는 온라인 Visual Studio Code 환경입니다.

### <a name="sdk-and-runtimes"></a>SDK 및 런타임

[.NET SDK](sdk.md)는 .NET 애플리케이션을 개발하고 실행하기 위한 라이브러리 및 도구 세트입니다.

[.NET을 다운로드](https://dotnet.microsoft.com/download/dotnet-core/)할 때 .NET 런타임 또는 ASP.NET Core 런타임과 같은 ‘런타임’이나 SDK를 선택할 수 있습니다. .NET 앱을 실행하기 위해 준비할 머신에 런타임을 설치합니다. 개발에 사용할 머신에 SDK를 설치합니다. SDK를 다운로드할 때 런타임도 자동으로 가져옵니다.

SDK 다운로드에는 다음 구성 요소가 포함되어 있습니다.

* [.NET CLI](tools/index.md). 로컬 개발 및 연속 통합 스크립트에 사용할 수 있는 명령줄 도구입니다.
* `dotnet` [드라이버](tools/index.md#driver). 프레임워크 종속 앱을 실행하는 CLI 명령입니다.
* [Roslyn](https://github.com/dotnet/roslyn) 및 [F#](https://github.com/microsoft/visualfsharp) 프로그래밍 언어 컴파일러
* [MSBuild](/visualstudio/msbuild/msbuild) 빌드 엔진
* [.NET 런타임](#clr). 형식 시스템, 어셈블리 로드, 가비지 수집기, 네이티브 interop, 기타 기본 서비스를 제공합니다.
* [런타임 라이브러리](#runtime-libraries). 기본 데이터 형식과 기본 유틸리티를 제공합니다.
* ASP.NET Core 런타임. 웹앱, IoT 앱, 모바일 백 엔드 등의 인터넷 연결 앱에 대한 기본 서비스를 제공합니다.
* 데스크톱 런타임. Windows Forms, WPF 등의 Windows 데스크톱 앱에 대한 기본 서비스를 제공합니다.

자세한 내용은 다음 자료를 참조하세요.

* [.NET SDK 개요](sdk.md)
* [.NET CLI 개요](tools/index.md)
* [dotnet 명령](tools/dotnet.md)

### <a name="project-system-and-msbuild"></a>프로젝트 시스템 및 MSBuild

.NET 앱은 [MSBuild](/visualstudio/msbuild/msbuild)를 사용하여 소스 코드에서 빌드됩니다. 프로젝트 파일( *.csproj* , *.fsproj* 또는 *.vbproj* )은 코드를 컴파일, 압축, 게시해야 하는 [대상](/visualstudio/msbuild/msbuild-targets) 및 관련 [작업](/visualstudio/msbuild/msbuild-tasks)을 지정합니다. 표준 대상 및 작업 컬렉션을 참조하는 SDK 식별자가 있습니다. 식별자를 사용하면 프로젝트 파일을 작고 작업하기 쉽게 유지할 수 있습니다. 예를 들어 콘솔 앱의 프로젝트 파일은 다음과 같습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

그리고 웹앱의 프로젝트 파일은 다음과 같습니다.

```xml
<Project Sdk="Microsoft.NET.Sdk.Web">
  <PropertyGroup>
    <TargetFramework>net5.0</TargetFramework>
  </PropertyGroup>
</Project>
```

예제에서 `Project` 요소의 `Sdk` 특성은 프로젝트를 빌드하는 MSBuild 대상 및 작업 세트를 지정합니다.  `TargetFramework` 요소는 앱이 종속되는 .NET 버전을 지정합니다. 프로젝트 파일을 편집하여 프로젝트와 관련된 대상 및 작업을 더 추가할 수 있습니다.

자세한 내용은 [.NET 프로젝트 SDK 개요](project-sdk/overview.md) 및 [대상 프레임워크](../standard/frameworks.md)를 참조하세요.

### <a name="cicd"></a>CI/CD

MSBuild 및 .NET CLI는 다음과 같은 다양한 연속 통합 도구 및 환경에서 사용할 수 있습니다.

* [GitHub Actions](https://github.com/features/actions)
* [Azure DevOps](/azure/devops/user-guide/what-is-azure-devops)
* [CAKE](https://cakebuild.net/)
* [FAKE](https://fake.build/)

자세한 내용은 [CI(연속 통합)에서 .NET SDK 및 도구 사용](tools/using-ci-with-cli.md)을 참조하세요.

### <a name="nuget"></a>NuGet

[NuGet](/nuget/what-is-nuget)은 .NET용으로 설계된 오픈 소스 패키지 관리자입니다. NuGet 패키지는 컴파일된 코드(DLL), 해당 코드와 관련된 기타 파일, 패키지 버전 번호 등의 정보를 포함하는 설명적 매니페스트가 포함된 *.zip* 파일로, `.nupkg` 확장명을 사용합니다. 공유할 코드가 있는 개발자는 패키지를 만들어 [nuget.org](https://nuget.org) 또는 프라이빗 호스트에 게시합니다. 공유 코드를 사용하려는 개발자는 프로젝트에 패키지를 추가하며, 패키지를 통해 노출된 API를 프로젝트 코드에서 호출할 수 있습니다.

자세한 내용은 [NuGet 설명서](/nuget/)를 참조하세요.

### <a name="net-interactive"></a>.NET Interactive

.NET Interactive는 사용자가 웹, Markdown, Notebook을 포괄하는 대화형 환경을 만들 수 있도록 하는 CLI 도구 및 API 그룹입니다.

자세한 내용은 다음 자료를 참조하세요.

* [브라우저 내부 .NET 자습서](https://dotnet.microsoft.com/learn/dotnet/in-browser-tutorial/1)
* [머신에서 Jupyter와 함께 .NET Notebook 사용](https://github.com/dotnet/interactive/blob/main/docs/NotebooksLocalExperience.md)
* [.NET Interactive 설명서](https://github.com/dotnet/interactive/blob/main/docs/README.md)

## <a name="execution-models"></a>실행 모델

.NET 앱은 CLR(공용 언어 런타임)이라고도 하는 런타임 환경에서 [관리 코드](../standard/managed-code.md)를 실행합니다.

### <a name="clr"></a>CLR

.NET [CLR](../standard/clr.md)은 Windows, macOS, Linux 지원을 포함하는 플랫폼 간 런타임입니다. CLR은 메모리 할당 및 관리를 처리합니다. 또한 CLR은 앱을 실행할 뿐만 아니라 JIT(Just-In-Time) 컴파일러를 사용하여 코드를 생성하고 컴파일하는 가상 머신입니다.

자세한 내용은 [CLR(공용 언어 런타임) 개요](../standard/clr.md)를 참조하세요.

### <a name="jit-compiler-and-il"></a>JIT 컴파일러 및 IL

C#과 같은 상위 수준 .NET 언어가 IL(중간 언어)이라는 하드웨어 독립 명령 집합으로 컴파일됩니다. 앱이 실행되면 JIT 컴파일러가 IL을 프로세서에서 인식하는 머신 코드로 변환합니다. JIT 컴파일은 코드를 실행할 머신과 동일한 머신에서 수행됩니다.

애플리케이션을 실행하는 동안 JIT 컴파일이 수행되므로 컴파일 시간은 실행 시간에 포함됩니다. 따라서 JIT 컴파일러는 결과 코드가 생성할 수 있는 시간 단축과 코드 최적화에 소요된 시간의 균형을 맞춰야 합니다. 그러나 JIT 컴파일러는 실제 하드웨어를 인식하므로 개발자가 플랫폼마다 다른 구현을 제공하지 않아도 됩니다.

.NET JIT 컴파일러는 ‘계층화된 컴파일’을 수행할 수 있으므로 런타임에 개별 메서드를 다시 컴파일할 수 있습니다. 이 기능을 사용하면 빠르게 컴파일하는 동시에 자주 사용하는 메서드를 위해 높은 수준으로 튜닝된 버전의 코드를 생성할 수 있습니다.

자세한 내용은 [관리형 실행 프로세스](../standard/managed-execution-process.md) 및 [계층화된 컴파일](whats-new/dotnet-core-3-0.md#tiered-compilation)을 참조하세요.

### <a name="aot-compiler"></a>AOT 컴파일러

대부분의 .NET 워크로드에 사용되는 기본 환경은 JIT 컴파일러이지만 .NET은 다음 두 가지 형식의 AOT(사전) 컴파일을 제공합니다.

* 일부 시나리오에서는 100% AOT 컴파일이 필요합니다. 예를 들어 [iOS](/xamarin/ios/) 등이 있습니다.
* 대부분의 앱 코드는 AOT로 컴파일되지만 일부 코드가 JIT로 컴파일되는 시나리오도 있습니다. 일부 코드 패턴은 AOT에 적합하지 않습니다(예: 제네릭). 해당 형식의 AOT 컴파일 예로 [즉시 실행 가능한](whats-new/dotnet-core-3-0.md#readytorun-images) 게시 옵션이 있습니다. 이 형식의 AOT는 AOT의 단점 없이 혜택만 제공합니다.

### <a name="automatic-memory-management"></a>자동 메모리 관리

GC(‘가비지 수집기’)는 애플리케이션의 메모리 할당 및 해제를 관리합니다. 코드에서 새 개체를 만들 때마다 CLR은 [관리되는 힙](../standard/garbage-collection/fundamentals.md#the-managed-heap)에서 개체의 메모리를 할당합니다. 관리되는 힙에서 주소 공간을 사용할 수 있다면 런타임은 계속해서 새 개체에 공간을 할당합니다. 사용 가능한 주소 공간이 부족하면 GC는 관리되는 힙에서 애플리케이션이 더 이상 사용하지 않는 개체를 확인한 다음, 해당 메모리를 회수합니다.

GC는 ‘메모리 안전성’ 유지에 도움이 되는 CLR 서비스 중 하나입니다. 프로그램이 할당된 메모리만 액세스하면 메모리가 안전합니다. 예를 들어 런타임은 앱이 배열의 범위를 넘어 할당되지 않은 메모리를 액세스하지 못하도록 합니다.

자세한 내용은 [자동 메모리 관리](../standard/automatic-memory-management.md) 및 [가비지 수집의 기본 사항](../standard/garbage-collection/fundamentals.md)을 참조하세요.

### <a name="working-with-unmanaged-resources"></a>관리되지 않는 리소스로 작업하기

코드에서 ‘비관리형 리소스’를 참조해야 하는 경우도 있습니다. 관리되지 않는 리소스는 .NET 런타임에서 자동 유지 관리되지 않는 리소스입니다. 예를 들어, 파일 핸들은 관리되지 않는 리소스입니다. <xref:System.IO.FileStream> 개체는 관리되는 개체이지만, 관리되지 않는 파일 핸들을 참조합니다. <xref:System.IO.FileStream> 사용을 마쳤으면 파일 핸들을 명시적으로 해제해야 합니다.

.NET에서는 관리되지 않는 리소스를 참조하는 개체가 <xref:System.IDisposable> 인터페이스를 구현합니다. 개체 사용을 마치면 관리되지 않는 모든 리소스 릴리스를 담당하는 개체의 <xref:System.IDisposable.Dispose> 메서드를 호출합니다. .NET 언어는 `Dispose` 메서드가 호출되도록 하는 편리한 `using` 문([C#](../csharp/language-reference/keywords/using.md), [F#](../fsharp/language-reference/resource-management-the-use-keyword.md), [VB](../visual-basic/language-reference/statements/using-statement.md))을 제공합니다.

자세한 내용은 [비관리형 리소스 정리](../standard/garbage-collection/unmanaged.md)를 참조하세요.

## <a name="deployment-models"></a>배포 모델

.NET 앱은 다음 두 가지 모드로 게시할 수 있습니다.

* 앱을 ‘자체 포함’으로 게시하면 .NET [런타임](#sdk-and-runtimes) 및 [라이브러리](#runtime-libraries)와 애플리케이션 및 해당 종속성을 포함하는 실행 파일이 생성됩니다. 애플리케이션 사용자는 .NET 런타임이 설치되지 않은 머신에서 실행 파일을 실행할 수 있습니다. 자체 포함 앱은 플랫폼마다 다르며, 필요에 따라 [AOT 컴파일](#aot-compiler) 형식으로 게시할 수 있습니다.

* 앱을 ‘프레임워크 종속’으로 게시하면 애플리케이션 자체와 해당 종속성만 포함하는 이진 파일( *.dll* 파일)과 실행 파일이 생성됩니다. 애플리케이션 사용자가 .NET [런타임](#sdk-and-runtimes)을 별도로 설치해야 합니다. 실행 파일은 플랫폼마다 다르지만 프레임워크 종속 애플리케이션의 *.dll* 파일은 플랫폼 간에 공유됩니다.

  여러 버전의 런타임을 병렬 설치하여 각기 다른 버전의 런타임을 대상으로 하는 프레임워크 종속 앱을 실행할 수 있습니다. 자세한 내용은 [대상 프레임워크](../standard/frameworks.md)를 참조하세요.

실행 파일은 [RID(런타임 식별자)](rid-catalog.md)로 지정한 특정 대상 플랫폼용으로 생성됩니다.

자세한 내용은 [.NET 애플리케이션 게시 개요](deploying/index.md) 및 [.NET 및 Docker 소개](docker/introduction.md)를 참조하세요.

## <a name="runtime-libraries"></a>런타임 라이브러리.

.NET에는 광범위한 표준 클래스 라이브러리 세트가 있습니다. 핵심 집합을 BCL(기본 클래스 라이브러리)이라고 하고, 전체 집합을 런타임 라이브러리 또는 프레임워크 라이브러리라고 합니다. 라이브러리는 다양한 범용 및 워크로드별 형식과 유틸리티 기능의 구현을 제공합니다.

다음은 런타임 라이브러리에 정의된 형식의 몇 가지 예입니다.

* 기본 형식(예: <xref:System.Boolean?displayProperty=nameWithType> 및 <xref:System.Int32?displayProperty=nameWithType>).
* <xref:System.Collections.Generic.List%601?displayProperty=nameWithType> 및 <xref:System.Collections.Generic.Dictionary%602?displayProperty=nameWithType>과 같은 컬렉션
* 데이터 형식(예: <xref:System.Data.DataSet?displayProperty=nameWithType> 및 <xref:System.Data.DataTable?displayProperty=nameWithType>)
* 네트워크 유틸리티 형식(예: <xref:System.Net.Http.HttpClient?displayProperty=nameWithType>)
* [파일 및 스트림 I/O](../standard/io/index.md) 유틸리티 형식(예: <xref:System.IO.FileStream?displayProperty=nameWithType> 및 <xref:System.IO.TextWriter?displayProperty=nameWithType>)
* [Serialization](../standard/serialization/index.md) 유틸리티 형식(예: <xref:System.Text.Json.JsonSerializer?displayProperty=nameWithType> 및 <xref:System.Xml.Serialization.XmlSerializer?displayProperty=nameWithType>)
* <xref:System.Span%601?displayProperty=nameWithType>, <xref:System.Numerics.Vector?displayProperty=nameWithType> 및 [Pipelines](../standard/io/pipelines.md)와 같은 고성능 형식

자세한 내용은 [프레임워크 라이브러리](../standard/framework-libraries.md) 및 [라이브러리의 소스 코드 ](https://github.com/dotnet/runtime/tree/master/src/libraries)를 참조하세요.

## <a name="microsoftextensions-libraries"></a>Microsoft.Extensions 라이브러리

자주 사용하는 일부 애플리케이션 기능의 라이브러리는 런타임 라이브러리에 포함되지 않고 다음과 같은 NuGet 패키지로 제공됩니다.

| NuGet 패키지 | 설명서 |
|---------|---------|
| [Microsoft.Extensions.Hosting](https://www.nuget.org/packages/Microsoft.Extensions.Hosting) | [애플리케이션 수명 관리(일반 호스트)](extensions/generic-host.md) |
| [Microsoft.Extensions.DependencyInjection](https://www.nuget.org/packages/Microsoft.Extensions.DependencyInjection) | [DI(종속성 주입)](extensions/dependency-injection.md)
| [Microsoft.Extensions.Configuration](https://www.nuget.org/packages/Microsoft.Extensions.Configuration) | [Configuration](extensions/configuration.md) |
| [Microsoft.Extensions.Logging](https://www.nuget.org/packages/Microsoft.Extensions.Logging) | [Logging](extensions/logging.md) |
| [Microsoft.Extensions.Options](https://www.nuget.org/packages/Microsoft.Extensions.Options) | [옵션 패턴](extensions/options.md) |

자세한 내용은 [GitHub의 dotnet/extensions 리포지토리](https://github.com/dotnet/extensions)를 참조하세요.

## <a name="data-access"></a>데이터 액세스

.NET은 ORM(개체/관계형 매퍼) 및 코드로 SQL 쿼리를 작성하는 방법을 제공합니다.

### <a name="entity-framework-core"></a>Entity Framework Core

EF(Entity Framework) Core는 ORM으로 사용할 수 있는 [오픈 소스](https://github.com/aspnet/EntityFrameworkCore) 플랫폼 간 데이터 액세스 기술입니다. EF Core를 사용하면 코드에서 .NET 개체를 참조하여 데이터베이스 작업을 수행할 수 있습니다. 그러면 작성하고 테스트해야 하는 데이터 액세스 코드 양이 줄어듭니다. EF Core는 많은 데이터베이스 엔진을 지원합니다.

자세한 내용은 [Entity Framework Core](/ef/core/) 및 [데이터베이스 공급자](/ef/core/providers/)를 참조하세요.

### <a name="linq"></a>LINQ

LINQ(Language-Integrated Query)를 사용하면 데이터에서 실행할 선언적 코드를 작성할 수 있습니다. 데이터는 다양한 형식(예: 메모리 내 개체, SQL 데이터베이스 또는 XML 문서)일 수 있지만 작성하는 LINQ 코드는 일반적으로 각 데이터 소스마다 다르게 표시되지 않습니다.

자세한 내용은 [LINQ(Language-Integrated Query) 개요](../standard/linq/index.md)를 참조하세요.

## <a name="net-terminology"></a>.NET 용어

.NET 설명서를 이해하려면 일부 용어의 사용이 시간에 따라 어떻게 변경되었는지 살펴보는 것이 도움이 될 수 있습니다.

### <a name="net-core-and-net-5"></a>.NET Core 및 .NET 5

2002년에 Microsoft는 Windows 앱을 만들기 위한 개발 플랫폼인 [.NET Framework](../framework/get-started/overview.md)를 릴리스했습니다. 현재 .NET Framework는 버전 4.8이며, 여전히 [Microsoft에서 지원](https://dotnet.microsoft.com/platform/support/policy/dotnet-framework)되고 있습니다.

2014년에 Microsoft는 .NET Framework의 플랫폼 간 오픈 소스 후속 프로그램 개발을 시작했습니다. 이 새로운 .NET 구현은 버전 3.1까지 .NET Core로 명명되었습니다. .NET Core 3.1 이후의 다음 버전은 .NET 5.0이며, 현재 미리 보기로 제공되고 있습니다. 이 .NET 구현과 .NET Framework 4.8의 혼동을 피하기 위해 버전 번호 4는 건너뛰었습니다. 이제 .NET의 기본 구현이 되었음을 명확하게 나타내기 위해 “Core”라는 이름이 삭제되었습니다.

이 문서는 .NET 5에 대해 설명하지만, 여전히 “.NET Core” 또는 “.NET Framework” 참조가 포함된 .NET 5 설명서가 많습니다. 또한 [ASP.NET Core](/aspnet/core/) 및 [Entity Framework Core](/ef/core/) 이름에는 “Core”가 그대로 남아 있습니다.

설명서에서 .NET Standard라는 이름을 사용하는 경우도 있습니다. [.NET Standard](../standard/net-standard.md)는 여러 .NET 구현의 클래스 라이브러리를 개발할 수 있도록 하는 API 사양입니다.

자세한 내용은 [.NET 아키텍처 구성 요소](../standard/components.md)를 참조하세요.

### <a name="overloaded-terms"></a>오버로드된 용어

.NET의 일부 용어는 컨텍스트에 따라 동일한 단어가 서로 다른 방식으로 사용되므로 혼동될 수 있습니다. 몇 가지 대표적인 경우는 다음과 같습니다.

* **런타임**

  |Context  |“런타임” 의미 |
  |---------|---------|
  | [CLR(공용 언어 런타임)](#clr)| 관리되는 프로그램의 실행 환경입니다. OS는 런타임 환경의 일부지만 .NET 런타임의 일부는 아닙니다. |
  | [.NET 다운로드 페이지의 .NET 런타임](https://dotnet.microsoft.com/download/dotnet-core) | [프레임워크 종속](#deployment-models) 앱 실행을 지원하는 [CLR](#clr) 및 [런타임 라이브러리](#runtime-libraries)입니다. 페이지에서 ASP.NET Core 서버 앱과 Windows 데스크톱 앱의 런타임을 선택할 수도 있습니다. |
  | [RID(런타임 식별자)](rid-catalog.md) | .NET 앱이 실행되는 OS 플랫폼 및 CPU 아키텍처입니다. 예를 들어: Windows x64, Linux x64 |

* **프레임워크**

  |Context  | “프레임워크” 의미 |
  |---------|---------------------|
  | .NET Framework | Windows 전용인 원래 .NET 구현입니다. “Framework”가 대문자로 시작합니다. |
  | 대상 프레임워크(target framework) | .NET 앱이나 라이브러리에서 사용하는 API 컬렉션입니다. 예: .NET Core 3.1, .NET Standard 2.0 |
  | TFM(대상 프레임워크 모니커)  | TFM은 .NET 앱 또는 라이브러리의 대상 프레임워크를 지정하기 위한 표준화된 토큰 형식입니다. 예: .NET Framework 4.6.2의 경우 `net462` |
  | 프레임워크 종속 앱 | [.NET 다운로드 페이지](https://dotnet.microsoft.com/download/dotnet-core)를 통해 런타임을 설치한 머신에서만 실행할 수 있는 앱입니다. 이때 사용된 “프레임워크”는 .NET 다운로드 페이지에서 다운로드하는 “런타임”과 동일합니다. |

* **SDK**

  |Context  | “SDK” 의미 |
  |---------|---------------|
  | [.NET 다운로드 페이지의 SDK](#sdk-and-runtimes)  | .NET 앱을 개발하고 실행하기 위해 다운로드하여 설치하는 도구 및 라이브러리 컬렉션입니다. CLI, MSBuild, .NET 런타임, 기타 구성 요소를 포함합니다.|
  | [SDK 스타일 프로젝트](#project-system-and-msbuild) | 특정 앱 유형의 프로젝트를 빌드하는 방법을 지정하는 MSBuild 대상 및 작업 세트입니다. 이 의미의 SDK는 프로젝트 파일에서 `Project` 요소의 `Sdk` 특성을 사용하여 지정합니다. |

* **platform**

  |Context  | “플랫폼” 의미 |
  |---------|--------------------|
  | 플랫폼 간 | 이 용어에서 “플랫폼”은 Windows, macOS, Linux, iOS, Android 등의 운영 체제와 운영 체제가 실행되는 하드웨어를 의미합니다. |
  | .NET 플랫폼 | 다양한 방식으로 사용됩니다. 하나의 .NET 구현을 가리키거나(예: .NET Framework 또는 .NET 5) 모든 구현을 포함하는 포괄적인 .NET 개념을 가리킬 수도 있습니다. |

.NET 용어에 대한 자세한 내용은 [.NET 용어집](../standard/glossary.md)을 참조하세요.

## <a name="advanced-scenarios"></a>고급 시나리오

다음 섹션에서는 고급 시나리오에서 유용한 .NET의 몇 가지 기능에 대해 설명합니다.

### <a name="native-interop"></a>네이티브 interop

모든 운영 체제에는 시스템 서비스를 제공하는 API(애플리케이션 프로그래밍 인터페이스)가 있습니다. .NET은 이러한 API를 호출하는 여러 가지 방법을 제공합니다.

네이티브 API와 상호 운용하는 기본 방법은 “플랫폼 호출” 또는 줄여서 P/Invoke를 사용하는 것입니다. P/Invoke는 Linux 및 Windows 플랫폼에서 지원됩니다. 상호 운용하는 Windows 전용 방법을 “COM interop”라고 하며, 관리 코드에서 [COM 구성 요소](/cpp/atl/introduction-to-com)를 사용합니다. 이 방법은 P/Invoke 인프라를 기반으로 하지만 약간 다른 방식으로 작동합니다.

자세한 내용은 [네이티브 상호 운용성](../standard/native-interop/index.md)을 참조하세요.

### <a name="unsafe-code"></a>안전하지 않은 코드

언어 지원에 따라 CLR에서는 기본 메모리에 액세스하고 `unsafe` 코드를 통해 포인터 연산을 수행할 수 있습니다. 이러한 작업은 특정 알고리즘 및 시스템 상호 운용성에 필요합니다. 강력하기는 하지만, 시스템 API와 상호 운용하거나 가장 효율적인 알고리즘을 구현하는 데 필요한 경우가 아니면 안전하지 않은 코드는 사용하지 않는 것이 좋습니다. 안전하지 않은 코드는 환경에 따라 다르게 실행될 수도 있고 가비지 수집기 및 형식 안전성의 이점을 잃을 수도 있습니다. 안전하지 않은 코드를 최대한 제한 및 중앙 집중화하고 해당 코드를 철저히 테스트하는 것이 좋습니다.

자세한 내용은 [안전하지 않은 코드 및 포인터](../csharp/programming-guide/unsafe-code-pointers/index.md)를 참조하세요.

## <a name="next-steps"></a>다음 단계

> [!div class="nextstepaction"]
> [.NET 자습서 선택](tutorials/index.md)

> [!div class="nextstepaction"]
> [브라우저에서 .NET 사용해 보기](../csharp/tutorials/intro-to-csharp/numbers-in-csharp.yml)

> [!div class="nextstepaction"]
> [C# 둘러보기](../csharp/tour-of-csharp/index.md)

> [!div class="nextstepaction"]
> [F# 둘러보기](../fsharp/tour.md)
