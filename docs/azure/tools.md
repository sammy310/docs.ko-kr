---
title: Azure .NET 개발자용 도구
description: Windows, Linux 및 Mac 환경에서 Azure .NET 라이브러리를 사용하여 시작하는 도구를 가져옵니다.
ms.date: 06/19/2020
ms.custom: azure-sdk-dotnet
ms.openlocfilehash: fa645b152f15550b25a3542ba0cdbb43799536b9
ms.sourcegitcommit: cb27c01a8b0b4630148374638aff4e2221f90b22
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2020
ms.locfileid: "86174855"
---
# <a name="azure-tools-for-developing-with-net"></a>.NET을 사용하여 개발하기 위한 Azure 도구

## <a name="sdk-downloads"></a>SDK 다운로드

.NET용 Azure 라이브러리는 [NuGet 패키지](https://www.nuget.org/packages?q=windowsazureofficial)로 구현됩니다. Azure 서비스에서 구성한 참조 설명서는 [API 참조](/dotnet/api/overview/azure/?view=azure-dotnet)를 참조하세요.

## <a name="development-tools"></a>개발 도구

Visual Studio에는 여러 Azure 서비스에 기본 제공되는 도구가 있습니다. 일부 Azure 서비스에는 [Azure Storage Explorer](https://azure.microsoft.com/features/storage-explorer/)와 같은 추가 도구 또는 에뮬레이터를 사용할 수 있습니다. 필요한 경우 추가 도구에 대해서는 Azure 서비스 설명서를 참조하세요.

아래에서 원하는 개발 환경을 선택합니다.

## <a name="visual-studio-on-windows"></a>[Windows의 Visual Studio](#tab/vs)

Visual Studio 버전 2017 이상에는 기본적으로 제공되는 Azure 개발 지원 기능이 있습니다. 아래 단계에서는 Visual Studio에서 Azure 개발 지원을 사용하도록 설정하는 방법을 설명합니다.

Visual Studio 2015 이하 버전의 경우 <a href="vs2015-install.md">이러한 지침을 따릅니다</a>.

### <a name="step-1-download-visual-studio-2019"></a>1단계: Visual Studio 2019 다운로드

Visual Studio 2019가 이미 설치되어 있으면 이 단계를 건너뛸 수 있습니다.

> [!div class="nextstepaction"]
> [Visual Studio 2019 다운로드](https://www.visualstudio.com/downloads/)

### <a name="step-2-install-the-two-azure-workloads"></a>2단계: 두 개의 Azure 워크로드 설치

Visual Studio 설치 관리자에서 Visual Studio를 설치하거나 기존 설치를 수정합니다. *Azure 개발*과 *ASP.NET 및 웹 개발* 워크로드가 선택되어 있는지 확인합니다.

### <a name="step-3-develop-with-net-on-azure"></a>3단계: Azure에서 .NET을 사용하여 개발

[Azure App Service에서 첫 ASP.NET Core 웹 앱 배포](/azure/app-service-web/app-service-web-get-started-dotnet)로 시작합니다.

## <a name="visual-studio-code-cross-platform"></a>[Visual Studio Code(플랫폼 간)](#tab/vscode)

Visual Studio Code에는 플랫폼 간 Azure 개발에 필요한 모든 것이 있습니다.

### <a name="step-1-download-the-net-core-sdk"></a>1단계: .NET Core SDK 다운로드

.NET Core 앱용 SDK 및 명령줄 도구입니다.

> [!div class="nextstepaction"]
> [.NET Core SDK 다운로드](https://dotnet.microsoft.com/download)

### <a name="step-2-visual-studio-code"></a>2단계: Visual Studio Code

모든 운영 체제에서 .NET Core 앱 편집 및 디버그: Windows, Mac 및 Linux.

> [!div class="nextstepaction"]
> [Visual Studio Code 다운로드](https://code.visualstudio.com)

### <a name="step-3-azure-tools-extension"></a>3단계: Azure 도구 확장

Visual Studio Code에 Azure 도구 확장을 설치합니다.

> [!div class="nextstepaction"]
> [Azure 도구 확장 설치](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)

### <a name="step-4-develop-with-net-on-azure"></a>4단계: Azure에서 .NET을 사용하여 개발

먼저 [Azure App Service on Linux에 첫 번째 ASP.NET Core 웹앱을 배포](/azure/app-service/containers/quickstart-dotnetcore)합니다.

---
