---
title: Windows에서 .NET Core의 필수 구성 요소
description: Windows 컴퓨터에서 .NET Core 애플리케이션을 개발 및 실행하기 위해 필요한 종속성이 무엇인지 살펴보세요.
ms.custom: updateeachvsrelease
ms.date: 04/08/2019
ms.openlocfilehash: 1921ef565c2d04624009f7684e439ddba1cdf57e
ms.sourcegitcommit: 09d699aca28ae9723399bbd9d3d44aa0cbd3848d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/19/2019
ms.locfileid: "68331065"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Windows에서 .NET Core의 필수 구성 요소

이 문서에서는 Windows에서 .NET Core 애플리케이션을 실행하도록 지원되는 OS 버전을 보여 줍니다. 다음에 나오는 지원되는 OS 버전 및 종속성은 Windows에서 .NET Core 앱을 개발하기 위한 세 가지 방법에 적용됩니다.

* [명령줄](tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2017)
* [Visual Studio Code](https://code.visualstudio.com/)

또한 Windows에서 Visual Studio 2017을 사용하여 개발하는 경우 [Visual Studio 2017 사용 시의 필수 조건](#prerequisites-with-visual-studio-2017) 섹션에서 .NET Core 개발에 지원되는 최소 버전에 대해 자세히 설명합니다.

## <a name="net-core-supported-operating-systems"></a>.NET Core 지원 운영 체제

다음 문서에는 버전별 .NET Core 지원 운영 체제의 전체 목록이 있습니다.

* [.NET Core 3.0(미리 보기)](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)
* [.NET Core 1.0](https://github.com/dotnet/core/blob/master/release-notes/1.0/1.0-supported-os.md)

다운로드 링크 및 자세한 내용은 최신 버전 다운로드의 경우 [.NET 다운로드](https://dotnet.microsoft.com/download)를 참조하고, 이전 버전의 경우 [.NET 다운로드 보관](https://dotnet.microsoft.com/download/archives#dotnet-core)를 참조하세요.

## <a name="net-core-dependencies"></a>.NET Core 종속성

.NET Core 1.1 이전 버전을 Windows 10 및 Windows Server 2016보다 이전 버전의 Windows에서 실행하는 경우 Visual C++ 재배포 가능 패키지가 필요합니다. 이 종속성은 .NET Core 설치 관리자에 의해 자동으로 설치됩니다.

다음과 같은 경우에는 [Microsoft Visual C++ 2015 재배포 가능 패키지 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685)을 수동으로 설치해야 합니다.

* [설치 관리자 스크립트](./tools/dotnet-install-script.md)를 사용하여 .NET Core 설치.
* 자체 포함된 .NET Core 애플리케이션 배포.
* 원본에서 제품 빌드.
* *.zip* 파일을 통해 .NET Core 설치. 여기에는 빌드/CI/CD 서버가 포함될 수 있습니다.

> [!NOTE]
> **Windows 8.1 이전 버전 또는 Windows Server 2012 R2 이전 버전의 경우:**
>
> 설치된 Windows가 최신 버전이며 Windows 업데이트를 통해 설치할 수 있는 [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)이 포함되어 있는지 확인하세요. 이 업데이트를 설치하지 않는 경우 .NET Core 애플리케이션을 시작할 때 `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`과 같은 오류가 표시됩니다.
>
> **Windows 7 또는 Windows Server 2008 R2의 경우:**
>
> KB2999226 외에 [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)도 설치되어 있는지 확인하세요. 이 업데이트를 설치하지 않는 경우 .NET Core 애플리케이션을 시작할 때 `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`와 같은 오류가 표시됩니다.

## <a name="prerequisites-for-net-core-30-preview-3"></a>.NET Core 3.0 미리 보기 3의 필수 구성 요소

.NET Core 3.0 미리 보기 3에는 다른 버전의 .NET Core와 같은 필수 구성 요소가 있습니다. 그러나 Visual Studio를 사용하여 .NET Core 3.0 프로젝트를 만들려는 경우 [Visual Studio 2019](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019)를 사용해야 합니다. Visual Studio 2019는 충돌 없이 다른 버전의 Visual Studio와 함께 설치될 수 있습니다.

## <a name="prerequisites-with-visual-studio-2017"></a>Visual Studio 2017 필수 구성 요소
    
.NET Core SDK를 사용하여 .NET Core 애플리케이션을 개발하기 위해 원하는 편집기를 사용할 수 있습니다. Visual Studio 2017에서는 Windows 기반 .NET Core 앱에 대한 통합 개발 환경을 제공합니다.

[릴리스 정보](/visualstudio/releasenotes/vs2017-relnotes)에서 Visual Studio 2017의 변경 내용에 대해 자세히 알아볼 수 있습니다.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Visual Studio 2017에서 .NET Core 2.2 SDK를 사용하여 .NET Core 앱을 개발하려면

 1. **기타 도구 집합** 섹션에서 **.NET Core 플랫폼 간 개발** 워크로드를 선택하고 [Visual Studio 2017 버전 15.9.0 이상을 다운로드하여 설치](/visualstudio/install/install-visual-studio)합니다.

![".NET Core 플랫폼 간 개발" 워크플로가 선택된 Visual Studio 2017 설치 스크린샷](./media/windows-prerequisites/vs-2017-workloads.jpg)

**.NET Core 플랫폼 간 개발** 도구 집합이 설치된 후 Visual Studio에서는 일반적으로 이전 버전의 .NET Core SDK를 설치합니다.
예를 들어 Visual Studio 2017 15.9에서는 워크로드가 설치된 후 기본적으로 .NET Core 2.1 SDK를 사용합니다.

.NET Core 2.2 SDK를 사용하도록 Visual Studio를 업데이트하려면

 1. [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)를 설치합니다.

 1. 프로젝트에서 최신 .NET Core 런타임을 사용하려면 다음 지침에 따라 기존 또는 새 .NET Core 프로젝트의 대상을 .NET Core 2.2로 변경합니다.

    * **프로젝트** 메뉴에서 **속성**을 선택합니다.
    * **대상 프레임워크** 선택 메뉴에서 값을 **.NET Core 2.2**로 설정합니다.

![“.NET Core 2.2” 대상 프레임워크 메뉴 항목이 선택된 Visual Studio 2017 애플리케이션 프로젝트 속성 스크린샷](./media/windows-prerequisites/targeting-dotnet-core.jpg)

.NET Core 2.2 SDK를 사용하여 Visual Studio를 구성한 후에는 다음 작업을 수행할 수 있습니다.

* 기존 .NET Core 1.x 및 2.x 프로젝트를 열고, 빌드하고, 실행합니다.
* .NET Core 1.x 및 2.x 프로젝트의 대상을 .NET Core 2.2로 변경하고 빌드 및 실행합니다.
* 새로운 .NET Core 2.2 프로젝트를 만듭니다.

# <a name="net-core-1xtabnetcore1x"></a>[.NET Core 1.x](#tab/netcore1x)

Visual Studio에서 .NET Core 1.x 앱을 개발하려면 **기타 도구 집합** 섹션에서 **“.NET Core 플랫폼 간 개발”** 워크로드를 선택하고 [Visual Studio 2017을 다운로드하여 설치](/visualstudio/install/install-visual-studio)합니다.

![".NET Core 플랫폼 간 개발" 워크플로가 선택된 Visual Studio 2017 설치 스크린샷](./media/windows-prerequisites/vs-workloads.jpg)

> [!IMPORTANT]
> .NET Core 1.x 개발에 Visual Studio 2015를 사용할 수 있지만 다음 이유로 권장하지 않습니다.
  > * .NET Core 도구는 지원되지 않는 미리 보기 버전입니다.
  > * 프로젝트는 더 이상 사용되지 않는 project.json을 기반으로 작성되었습니다.
>
> 프로젝트 형식 변경에 대한 자세한 내용은 [변경 내용에 대한 대략적인 개요](./tools/cli-msbuild-architecture.md)를 참조하세요.

---

<a name="vs-mapping"></a>

> [!TIP]
> Visual Studio 버전을 확인하려면
>
> * **도움말** 메뉴에서 **Microsoft Visual Studio 정보**를 선택합니다.
> * **Microsoft Visual Studio 정보** 대화 상자에서 버전 번호를 확인합니다.
>   * .NET Core 3.0 미리 보기 3 앱의 경우 Visual Studio 2019 버전 16.0 이상.
>   * .NET Core 2.2 앱의 경우 Visual Studio 2017 버전 15.9 이상.
>   * .NET Core 2.1 앱의 경우 Visual Studio 2017 버전 15.7 이상.
>   * .NET Core 1.x 앱의 경우 Visual Studio 2017 버전 15.0 이상.
