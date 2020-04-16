---
title: Azure .NET 및 .NET Core 개발자용 도구
description: Windows, Linux 및 Mac 환경에서 Azure .NET 라이브러리를 사용하여 시작하는 도구를 가져옵니다.
ms.date: 10/01/2018
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: 1c6370e4b3e5e6e901ba6ef56c65d794f3da5abe
ms.sourcegitcommit: 34dc3c0d0d0a1cc418abff259d9daa8078d00b81
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2020
ms.locfileid: "81433165"
---
# <a name="tools-for-net-and-net-core-azure-developers"></a>.NET 및 .NET Core Azure 개발자용 도구

## <a name="sdk-downloads"></a>SDK 다운로드

.NET에 대한 Azure 라이브러리는 [NuGet 패키지로 구현됩니다.](https://www.nuget.org/packages?q=windowsazureofficial) Azure 서비스로 구성된 설치 지침은 [API 참조를](/dotnet/api/overview/azure/?view=azure-dotnet) 참조하십시오.

## <a name="development-tools"></a>개발 도구

Visual Studio에는 많은 Azure 서비스에 대한 도구가 내장되어 있습니다. 일부 Azure 서비스에는 [Azure 저장소 탐색기와](https://azure.microsoft.com/features/storage-explorer/)같은 추가 도구 또는 에뮬레이터가 있습니다. 필요한 경우 Azure 서비스에 대한 설명서를 참조하십시오.

이 지침은 운영 체제에 권장되는 시작 개발 환경을 설치합니다.

## <a name="windows"></a>[Windows](#tab/windows)

Visual Studio 버전 2017 이상Azure 개발에 대 한 기본 제공 지원. 아래 단계는 Visual Studio에서 Azure 개발 지원을 사용하도록 설정하는 것을 설명합니다.

Visual Studio 2015 및 이전 의 경우 <a href="vs2015-install.md">다음 지침을 따르십시오.</a>

### <a name="step-1-download-visual-studio-2019"></a>1단계: 비주얼 스튜디오 2019 다운로드

Visual Studio 2019가 이미 설치되어 있는 경우 이 단계를 건너뛸 수 있습니다.

> [!div class="nextstepaction"]
> [Visual Studio 2019 다운로드](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>2단계: 두 개의 Azure 워크로드 설치

Visual Studio 설치 관리자에서 Visual Studio를 설치하거나 기존 설치를 수정합니다. *Azure 개발* 및 *ASP.NET 및 웹 개발* 워크로드가 선택되어 있는지 확인합니다.

### <a name="step-3-develop-with-net-on-azure"></a>3단계: Azure에서 .NET을 사용하여 개발

[Azure App Service에서 첫 ASP.NET Core 웹 앱 배포](https://docs.microsoft.com/azure/app-service-web/app-service-web-get-started-dotnet)로 시작합니다.

## <a name="macos"></a>[macOS](#tab/macos)

Mac용 Visual Studio에는 Azure 개발에 필요한 모든 것이 있습니다.

### <a name="step-1-download-visual-studio-for-mac"></a>1단계: Mac용 Visual Studio 다운로드

> [!div class="nextstepaction"]
> [Mac용 Visual Studio 다운로드](https://www.visualstudio.com/vs/visual-studio-mac/)

설치 하는 동안 Azure 도구는 기본적으로 선택 됩니다.

## <a name="linux"></a>[Linux](#tab/linux)

Visual Studio Code에는 Linux에서 Azure 개발에 필요한 모든 것이 있습니다.

### <a name="step-1-download-the-net-core-sdk"></a>1 단계: .NET Core SDK 다운로드

.NET Core 앱용 SDK 및 명령줄 도구입니다.

> [!div class="nextstepaction"]
> [.NET Core SDK 다운로드](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a>2단계: Visual Studio Code

모든 운영 체제에서.NET Core 앱 편집 및 디버그: Windows, Mac, Linux

> [!div class="nextstepaction"]
> [Visual Studio Code 다운로드](https://code.visualstudio.com)

---
