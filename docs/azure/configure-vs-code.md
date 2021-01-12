---
title: .NET을 사용한 Azure 개발을 위한 Visual Studio Code 구성
description: 이 문서에서는 VS Code에서 적합한 플러그인을 설치하고 구성하는 방법을 비롯해 Azure 개발을 위한 Visual Studio Code를 구성하는 방법을 안내합니다.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 65ced99befe12d137062b4ea6a59a1ccd3099e0b
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700989"
---
# <a name="configure-visual-studio-code-for-azure-development"></a><span data-ttu-id="973cd-103">Azure 개발을 위한 Visual Studio Code 구성</span><span class="sxs-lookup"><span data-stu-id="973cd-103">Configure Visual Studio Code for Azure development</span></span>

<span data-ttu-id="973cd-104">.NET 개발을 수행하거나, Angular, React, Vue와 같은 프레임워크를 사용하여 단일 페이지 애플리케이션을 빌드하거나, Python과 같은 다른 언어로 애플리케이션을 작성하기 위해 Visual Studio Code를 사용하는 경우 Azure 개발을 위한 Visual Studio Code를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-104">If you are using Visual Studio Code, whether for .NET development, for building single page applications using frameworks like Angular, React or Vue, or for writing applications in another language like Python, you will want to configure Visual Studio Code for Azure development.</span></span>

### <a name="download-visual-studio-code"></a><span data-ttu-id="973cd-105">Visual Studio Code 다운로드</span><span class="sxs-lookup"><span data-stu-id="973cd-105">Download Visual Studio Code</span></span>

<span data-ttu-id="973cd-106">Visual Studio Code가 이미 설치되어 있으면 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-106">If you already have Visual Studio Code installed, you can skip this step</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="973cd-107">Visual Studio Code 다운로드</span><span class="sxs-lookup"><span data-stu-id="973cd-107">Download Visual Studio Code</span></span>](https://code.visualstudio.com/download)

### <a name="install-the-azure-tools-extension-pack"></a><span data-ttu-id="973cd-108">Azure Tools 확장 팩 설치</span><span class="sxs-lookup"><span data-stu-id="973cd-108">Install the Azure Tools Extension Pack</span></span>

<span data-ttu-id="973cd-109">[Azure Tools 확장 팩](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack)에는 Azure App Service, Azure Functions, Azure Storage, Cosmos DB, Azure Virtual Machines 등을 사용하는 데 필요한 모든 확장이 하나의 편리한 패키지로 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-109">The [Azure Tools Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode.vscode-node-azure-pack) contains extensions for working with Azure App Service, Azure Functions, Azure Storage, Cosmos DB, and Azure Virtual Machines all in one convenient package.</span></span>

<span data-ttu-id="973cd-110">Visual Studio Code에서 확장을 설치하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-110">To install the extension from Visual Studio Code:</span></span>

1. <span data-ttu-id="973cd-111"><kbd>Ctrl+Shift+X</kbd>를 눌러 **확장** 창을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-111">Press <kbd>Ctrl+Shift+X</kbd> to open the **Extensions** window.</span></span>
1. <span data-ttu-id="973cd-112">*Azure Tools* 확장을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-112">Search for the *Azure Tools* extension.</span></span>
1. <span data-ttu-id="973cd-113">**설치** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-113">Select the **Install** button.</span></span>

![Azure Tools 확장 팩을 검색하는 확장 패널을 보여 주는 Visual Studio Code의 스크린샷](./media/visual-studio-code-azure-tools.png)

<span data-ttu-id="973cd-115">Visual Studio Code에서 확장을 설치하는 방법에 대한 자세한 내용은 Visual Studio Code 웹 사이트에서 [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)(확장 Marketplace) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="973cd-115">To learn more about installing extensions in Visual Studio Code, refer to the [Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery) document on the Visual Studio Code website.</span></span>

### <a name="sign-in-to-your-azure-account-with-azure-tools"></a><span data-ttu-id="973cd-116">Azure Tools를 사용하여 Azure 계정에 로그인</span><span class="sxs-lookup"><span data-stu-id="973cd-116">Sign in to your Azure account with Azure Tools</span></span>

<span data-ttu-id="973cd-117">왼쪽 패널에 Azure 아이콘이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-117">On the left hand panel, you'll see an Azure icon.</span></span> <span data-ttu-id="973cd-118">이 아이콘을 선택하면 Azure 서비스의 제어판이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-118">Select this icon, and a control panel for Azure services will appear.</span></span> <span data-ttu-id="973cd-119">서비스 아래에서 **Azure에 로그인...** 을 선택하여 Visual Studio Code에서 Azure Tools의 인증 프로세스를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-119">Choose **Sign in to Azure...** under any service to complete the authentication process for the Azure tools in Visual Studio Code.</span></span>

![Azure Tools로 Azure에 로그인하는 방법을 보여 주는 Visual Studio Code의 스크린샷](./media/visual-studio-code-azure-login.png)

### <a name="next-steps"></a><span data-ttu-id="973cd-121">다음 단계</span><span class="sxs-lookup"><span data-stu-id="973cd-121">Next steps</span></span>

<span data-ttu-id="973cd-122">다음으로 워크스테이션에 Azure CLI를 설치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="973cd-122">Next, you will want to install the Azure CLI on your workstation.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="973cd-123">Azure CLI 설치</span><span class="sxs-lookup"><span data-stu-id="973cd-123">Install the Azure CLI</span></span>](./install-azure-cli.md)
