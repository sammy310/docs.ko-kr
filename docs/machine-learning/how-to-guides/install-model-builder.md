---
title: 모델 작성기 설치 방법
description: ML.NET 모델 작성기 도구를 설치하는 방법 알아보기
author: luisquintanilla
ms.author: luquinta
ms.date: 11/21/2019
ms.custom: mvc, how-to, mlnet-tooling
ms.openlocfilehash: b944d7f6044553251132824e7e4213119e34500e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "78848654"
---
# <a name="how-to-install-mlnet-model-builder"></a><span data-ttu-id="92289-103">ML.NET 모델 작성기 설치 방법</span><span class="sxs-lookup"><span data-stu-id="92289-103">How to install ML.NET Model Builder</span></span>

<span data-ttu-id="92289-104">ML.NET 모델 작성기를 설치하여 .NET 애플리케이션에 기계 학습을 추가하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="92289-104">Learn how to install ML.NET Model Builder to add machine learning to your .NET applications.</span></span>

> [!NOTE]
> <span data-ttu-id="92289-105">모델 작성기는 현재 미리 보기로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="92289-105">Model Builder is currently in Preview.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="92289-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="92289-106">Prerequisites</span></span>

- <span data-ttu-id="92289-107">Visual Studio 2017 버전 15.9.12 이상/Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="92289-107">Visual Studio 2017 version 15.9.12 or later / Visual Studio 2019</span></span>
- <span data-ttu-id="92289-108">.NET Core 2.1 SDK 이상.</span><span class="sxs-lookup"><span data-stu-id="92289-108">.NET Core 2.1 SDK or later.</span></span>

> [!NOTE]
> <span data-ttu-id="92289-109">.NET Core 3.0 SDK는 현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92289-109">.NET Core 3.0 SDK is not currently supported.</span></span>

## <a name="limitations"></a><span data-ttu-id="92289-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="92289-110">Limitations</span></span>

- <span data-ttu-id="92289-111">ML.NET 모델 작성기 확장은 현재 Windows의 Visual Studio에서만 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-111">ML.NET Model Builder Extension currently only works on Visual Studio on Windows.</span></span>
- <span data-ttu-id="92289-112">1GB의 학습 데이터 세트 제한</span><span class="sxs-lookup"><span data-stu-id="92289-112">Training dataset limit of 1GB</span></span>
- <span data-ttu-id="92289-113">SQL 서버에는 학습을 위한 행 수가 10만개로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="92289-113">SQL Server has a limit of 100 thousand rows for training</span></span>
- <span data-ttu-id="92289-114">Visual Studio 2017용 Microsoft SQL Server Data Tools는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92289-114">Microsoft SQL Server Data Tools for Visual Studio 2017 is not supported</span></span>

## <a name="install"></a><span data-ttu-id="92289-115">설치</span><span class="sxs-lookup"><span data-stu-id="92289-115">Install</span></span>

<span data-ttu-id="92289-116">Visual Studio Marketplace를 통해 또는 Visual Studio 내에서 ML.NET 모델 작성기를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="92289-116">ML.NET Model builder can be installed either through the Visual Studio Marketplace or from within Visual Studio.</span></span>

### <a name="visual-studio-marketplace"></a><span data-ttu-id="92289-117">Visual Studio Marketplace</span><span class="sxs-lookup"><span data-stu-id="92289-117">Visual Studio Marketplace</span></span>

1. <span data-ttu-id="92289-118">[Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)에서 다운로드</span><span class="sxs-lookup"><span data-stu-id="92289-118">Download from [Visual Studio Marketplace](https://marketplace.visualstudio.com/items?itemName=MLNET.07)</span></span>
1. <span data-ttu-id="92289-119">프롬프트에 따라 각 Visual Studio 버전에 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-119">Follow prompts to install onto respective Visual Studio version</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="92289-120">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="92289-120">Visual Studio 2017</span></span>

1. <span data-ttu-id="92289-121">메뉴 모음에서 **도구** > **확장 및 업데이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-121">In the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 확장 관리자 대화 상자 열기](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="92289-123">*확장 및 업데이트* 프롬프트 내에서 *Online* 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-123">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="92289-124">검색 창에서 *ML.NET 모델 작성기*를 검색하고 결과에서 ML.NET 모델 작성기(미리 보기)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-124">In the search bar, search for *ML.NET Model Builder* and from the results, select ML.NET Model Builder (Preview)</span></span>

    ![VS2017 확장 관리자 대화 상자에서 모델 작성기 확장 검색 및 설치](./media/install-model-builder/vs2017-install-model-builder.png)

1. <span data-ttu-id="92289-126">프롬프트에 따라 설치를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-126">Follow the prompts to complete the installation</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="92289-127">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="92289-127">Visual Studio 2019</span></span>

1. <span data-ttu-id="92289-128">메뉴 모음에서 **확장** > **확장 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-128">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 확장 관리자 대화 상자 열기](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="92289-130">*확장 및 업데이트* 프롬프트 내에서 *Online* 노드를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-130">Inside the *Extension and Updates* prompt, select the *Online* node.</span></span>
1. <span data-ttu-id="92289-131">검색 창에 *ML.NET 모델 작성기*를 입력하고 ML.NET 모델 작성기(미리 보기)를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-131">Type *ML.NET Model Builder* into the search bar select ML.NET Model Builder (Preview)</span></span>

    ![VS2019 확장 관리자 대화 상자에서 모델 작성기 확장 검색 및 설치](./media/install-model-builder/vs2019-install-model-builder.png)

1. <span data-ttu-id="92289-133">프롬프트에 따라 설치를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-133">Follow the prompts to complete the installation</span></span>

## <a name="uninstall"></a><span data-ttu-id="92289-134">제거</span><span class="sxs-lookup"><span data-stu-id="92289-134">Uninstall</span></span>

### <a name="visual-studio-2017"></a><span data-ttu-id="92289-135">Visual Studio 2017</span><span class="sxs-lookup"><span data-stu-id="92289-135">Visual Studio 2017</span></span>

1. <span data-ttu-id="92289-136">메뉴 모음에서 **도구** > **확장 및 업데이트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-136">On the menu bar, select **Tools** > **Extensions and Updates**</span></span>

    ![VS2017 확장 관리자 대화 상자 열기](./media/install-model-builder/vs2017-open-extensions-manager.png)

1. <span data-ttu-id="92289-138">*확장 및 업데이트* 프롬프트 내에서 *설치됨* 노드를 확장하고 *도구*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-138">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="92289-139">도구 목록에서 ML.NET 모델 작성기(미리 보기)를 선택한 다음, *제거*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-139">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2017 확장 관리자 대화 상자에서 모델 작성기 확장 검색 및 제거](./media/install-model-builder/vs2017-uninstall-model-builder.png)

1. <span data-ttu-id="92289-141">프롬프트에 따라 제거를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-141">Follow the prompts to complete the uninstallation.</span></span>

### <a name="visual-studio-2019"></a><span data-ttu-id="92289-142">Visual Studio 2019</span><span class="sxs-lookup"><span data-stu-id="92289-142">Visual Studio 2019</span></span>

1. <span data-ttu-id="92289-143">메뉴 모음에서 **확장** > **확장 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-143">On the menu bar, select **Extensions** > **Manage Extensions**</span></span>

    ![VS2019 확장 관리자 대화 상자 열기](./media/install-model-builder/vs2019-open-extensions-manager.png)

1. <span data-ttu-id="92289-145">*확장 및 업데이트* 프롬프트 내에서 *설치됨* 노드를 확장하고 *도구*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-145">Inside the *Extension and Updates* prompt, expand the *Installed* node and select *Tools*</span></span>
1. <span data-ttu-id="92289-146">도구 목록에서 ML.NET 모델 작성기(미리 보기)를 선택한 다음, *제거*를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-146">Select ML.NET Model Builder (Preview) from the list of tools and then, select *Uninstall*</span></span>

    ![VS2019 확장 관리자 대화 상자에서 모델 작성기 확장 검색 및 제거](./media/install-model-builder/vs2019-uninstall-model-builder.png)

1. <span data-ttu-id="92289-148">프롬프트에 따라 제거를 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-148">Follow the prompts to complete the uninstallation.</span></span>

## <a name="upgrade"></a><span data-ttu-id="92289-149">Upgrade</span><span class="sxs-lookup"><span data-stu-id="92289-149">Upgrade</span></span>

<span data-ttu-id="92289-150">업그레이드 프로세스는 설치 프로세스와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-150">The upgrade process is similar to the installation process.</span></span> <span data-ttu-id="92289-151">Visual Studio Marketplace에서 최신 버전을 다운로드하거나 Visual Studio에서 확장 관리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="92289-151">Either download the latest version from Visual Studio Marketplace or use the Extensions Manager in Visual Studio.</span></span>
