---
title: .NET을 사용한 Azure 개발을 위한 Visual Studio 구성
description: 이 문서에서는 적합한 워크로드를 설치하고 Visual Studio를 Azure 계정에 연결하는 방법을 비롯해 Azure 개발을 위한 Visual Studio를 구성하는 방법을 안내합니다.
ms.date: 11/30/2020
ms.topic: conceptual
ms.custom: devx-track-dotnet
ms.author: daberry
author: daberry
ms.openlocfilehash: 986469bd07657d968045465803047dc21d76dd62
ms.sourcegitcommit: 3d6d6595a03915f617349781f455f838a44b0f44
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2020
ms.locfileid: "97700994"
---
# <a name="configure-visual-studio-for-azure-development-with-net"></a><span data-ttu-id="83735-103">.NET을 사용한 Azure 개발을 위한 Visual Studio 구성</span><span class="sxs-lookup"><span data-stu-id="83735-103">Configure Visual Studio for Azure development with .NET</span></span>

<span data-ttu-id="83735-104">Visual Studio에는 Azure에서 애플리케이션을 개발하고 배포하는 데 도움이 되는 도구가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83735-104">Visual Studio includes tooling to help with the development and deployment of applications on Azure.</span></span>  <span data-ttu-id="83735-105">이 가이드는 Azure 개발을 위해 Visual Studio가 올바로 구성되었는지 확인하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="83735-105">This guide will help you make sure that you have Visual Studio properly configured for Azure development.</span></span>

### <a name="download-visual-studio-2019"></a><span data-ttu-id="83735-106">Visual Studio 2019 다운로드</span><span class="sxs-lookup"><span data-stu-id="83735-106">Download Visual Studio 2019</span></span>

<span data-ttu-id="83735-107">Visual Studio 2019를 이미 설치한 경우 이 단계를 건너뛸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83735-107">If you already have Visual Studio 2019 installed, you can skip this step.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="83735-108">Visual Studio 2019 다운로드</span><span class="sxs-lookup"><span data-stu-id="83735-108">Download Visual Studio 2019</span></span>](https://www.visualstudio.com/downloads/)

### <a name="install-azure-workloads"></a><span data-ttu-id="83735-109">Azure 워크로드 설치</span><span class="sxs-lookup"><span data-stu-id="83735-109">Install Azure workloads</span></span>

<span data-ttu-id="83735-110">**Visual Studio 설치 관리자** 를 시작하고 **Azure 개발** 과 **ASP.NET 및 웹 개발** 워크로드가 설치되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="83735-110">Launch the **Visual Studio Installer** and validate that you have the workloads **Azure development** and **ASP.NET and web development** are installed.</span></span>  <span data-ttu-id="83735-111">이러한 워크로드 중 하나를 설치하지 않은 경우 해당 워크로드를 선택하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="83735-111">If either of these workloads is not installed, select these workloads to install them.</span></span>

![선택한 Azure 개발과 ASP.NET 및 웹 개발 워크로드를 보여 주는 Visual Studio 설치 관리자의 스크린샷](./media/visual-studio-installer-azure-development.png)

### <a name="authenticate-visual-studio-with-azure"></a><span data-ttu-id="83735-113">Azure를 사용하여 Visual Studio 인증</span><span class="sxs-lookup"><span data-stu-id="83735-113">Authenticate Visual Studio with Azure</span></span>

<span data-ttu-id="83735-114">Visual Studio를 통해 앱을 디버그하는 경우 Visual Studio에서 Azure 계정을 사용하여 Azure 리소스를 인증하고 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83735-114">When debugging apps through Visual Studio, Visual Studio can use your Azure account to authenticate and access Azure Resources with.</span></span>  <span data-ttu-id="83735-115">이 계정은 Visual Studio에서 Azure로 직접 앱을 게시할 때에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="83735-115">This account is also used when you publish apps directly from Visual Studio to Azure.</span></span>

<span data-ttu-id="83735-116">Visual Studio에서 Azure 계정을 인증하려면 **도구** > **옵션** 메뉴를 선택하여 **옵션** 대화 상자를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="83735-116">To authenticate your Azure account from Visual Studio, select the **Tools** > **Options** menu to launch the **Options** dialog.</span></span> <span data-ttu-id="83735-117">`Azure Service Authentication` 옵션으로 이동하여 Azure 계정으로 로그인합니다.</span><span class="sxs-lookup"><span data-stu-id="83735-117">Navigate to the `Azure Service Authentication` options and sign in using your Azure account.</span></span>

![Azure 로그인을 보여 주는 Visual Studio 옵션 대화 상자의 스크린샷](./media/visual-studio-azure-login-dialog.png)

### <a name="next-steps"></a><span data-ttu-id="83735-119">다음 단계</span><span class="sxs-lookup"><span data-stu-id="83735-119">Next steps</span></span>

<span data-ttu-id="83735-120">.NET이나 다른 언어의 개발에 [Visual Studio Code](https://code.visualstudio.com/)도 사용하는 [Azure 개발을 위한 Visual Studio Code 구성](./configure-vs-code.md)도 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="83735-120">If you also use [Visual Studio Code](https://code.visualstudio.com/) for development in .NET or any other language, you should also [configure Visual Studio Code for Azure development](./configure-vs-code.md).</span></span> <span data-ttu-id="83735-121">그러지 않으면 [Azure CLI 설치](./install-azure-cli.md)로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="83735-121">Otherwise, proceed to [Installing the Azure CLI](./install-azure-cli.md).</span></span>
