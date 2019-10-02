---
title: 모델 작성기 설치 방법
description: ML.NET 모델 작성기 도구를 설치하는 방법 알아보기
author: luisquintanilla
ms.author: luquinta
ms.date: 06/21/2019
ms.custom: mvc, how-to
ms.openlocfilehash: b0d45ab7807bf84b98c58e85580d5aa04d0c5f7d
ms.sourcegitcommit: 1e72e2990220b3635cebc39586828af9deb72d8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/26/2019
ms.locfileid: "71306321"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="3b452-103">ML.NET 모델 작성기 설치 방법</span><span class="sxs-lookup"><span data-stu-id="3b452-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="3b452-104">ML.NET 모델 작성기를 설치하여 .NET 애플리케이션에 기계 학습을 추가하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="3b452-105">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-105">Model Builder is currently in Preview.</span></span>

## <a name="pre-requisites"></a><span data-ttu-id="3b452-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="3b452-106">Pre-requisites</span></span>

- <span data-ttu-id="3b452-107">Visual Studio 2017 15.9.12 이상 / Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3b452-107">Visual Studio 2017 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="3b452-108">.NET Core 2.1 이상 SDK</span><span class="sxs-lookup"><span data-stu-id="3b452-108">.NET Core 2.1 or later SDK</span></span>

## <a name="limitations"></a><span data-ttu-id="3b452-109">제한 사항</span><span class="sxs-lookup"><span data-stu-id="3b452-109">Limitations</span></span>

- <span data-ttu-id="3b452-110">ML.NET 모델 작성기 확장은 현재 Windows의 Visual Studio에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-110">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="3b452-111">1GB의 학습 데이터 세트 제한</span><span class="sxs-lookup"><span data-stu-id="3b452-111">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="3b452-112">SQL 서버에는 학습을 위한 행 수가 10만개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-112">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="3b452-113">Visual Studio 2017용 Microsoft SQL Server Data Tools는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-113">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="3b452-114">설치</span><span class="sxs-lookup"><span data-stu-id="3b452-114">Install</span></span>

<span data-ttu-id="3b452-115">Visual Studio Marketplace를 통해 또는 Visual Studio 내에서 ML.NET 모델 작성기를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-115">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span> 

### <a name="visual-studio-marketplace"></a><span data-ttu-id="3b452-116">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="3b452-116">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="3b452-117">[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)에서 다운로드</span><span class="sxs-lookup"><span data-stu-id="3b452-117">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="3b452-118">프롬프트에 따라 각 Visual Studio 버전에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-118">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="3b452-119">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="3b452-119">Visual Studio 2017</span></span>

1. <span data-ttu-id="3b452-120">메뉴 모음에서 **도구** > **확장 및 업데이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-120">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 확장 관리자 대화 상자 열기](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="3b452-122">*확장 및 업데이트* 프롬프트 내에서 *Online* 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-122">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="3b452-123">검색 창에서 *ML.NET 모델 작성기*를 검색하고 결과에서 ML.NET 모델 작성기(미리 보기)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-123">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017 확장 관리자 대화 상자에서 모델 작성기 확장 검색 및 설치](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="3b452-125">프롬프트에 따라 설치를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-125">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="3b452-126">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3b452-126">Visual Studio 2019</span></span>

1. <span data-ttu-id="3b452-127">메뉴 모음에서 **확장** > **확장 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-127">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 확장 관리자 대화 상자 열기](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="3b452-129">*확장 및 업데이트* 프롬프트 내에서 *Online* 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-129">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="3b452-130">검색 창에 *ML.NET 모델 작성기*를 입력하고 ML.NET 모델 작성기(미리 보기)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-130">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019 확장 관리자 대화 상자에서 모델 작성기 확장 검색 및 설치](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="3b452-132">프롬프트에 따라 설치를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-132">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="3b452-133">제거</span><span class="sxs-lookup"><span data-stu-id="3b452-133">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="3b452-134">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="3b452-134">Visual Studio 2017</span></span>

1. <span data-ttu-id="3b452-135">메뉴 모음에서 **도구** > **확장 및 업데이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-135">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 확장 관리자 대화 상자 열기](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="3b452-137">*확장 및 업데이트* 프롬프트 내에서 *설치됨* 노드를 확장하고 *도구*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-137">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="3b452-138">도구 목록에서 ML.NET 모델 작성기(미리 보기)를 선택한 다음, *제거*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-138">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017 확장 관리자 대화 상자에서 모델 작성기 확장 검색 및 제거](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="3b452-140">프롬프트에 따라 제거를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-140">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="3b452-141">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="3b452-141">Visual Studio 2019</span></span>

1. <span data-ttu-id="3b452-142">메뉴 모음에서 **확장** > **확장 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-142">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 확장 관리자 대화 상자 열기](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="3b452-144">*확장 및 업데이트* 프롬프트 내에서 *설치됨* 노드를 확장하고 *도구*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-144">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="3b452-145">도구 목록에서 ML.NET 모델 작성기(미리 보기)를 선택한 다음, *제거*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-145">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019 확장 관리자 대화 상자에서 모델 작성기 확장 검색 및 제거](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="3b452-147">프롬프트에 따라 제거를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-147">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="3b452-148">Upgrade</span><span class="sxs-lookup"><span data-stu-id="3b452-148">Upgrade</span></span>

<span data-ttu-id="3b452-149">업그레이드 프로세스는 설치 프로세스와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-149">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="3b452-150">Visual Studio Marketplace에서 최신 버전을 다운로드하거나 Visual Studio에서 확장 관리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3b452-150">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
