---
title: CentOS에 .NET 설치 - .NET
description: CentOS에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 7e73f90a1f1f7e11e592b1b074f243c9f5b32ced
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970865"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-centos"></a><span data-ttu-id="64462-103">CentOS에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="64462-103">Install the .NET SDK or the .NET Runtime on CentOS</span></span>

<span data-ttu-id="64462-104">.NET은 CentOS에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="64462-104">.NET is supported on CentOS.</span></span> <span data-ttu-id="64462-105">이 문서에서는 CentOS에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="64462-105">This article describes how to install .NET on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="64462-106">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="64462-106">Supported distributions</span></span>

<span data-ttu-id="64462-107">다음 표는 CentOS 7과 CentOS 8에서 현재 지원되는 .NET 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="64462-107">The following table is a list of currently supported .NET releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="64462-108">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 CentOS 버전이 더 이상 지원되지 않을 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="64462-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="64462-109">✔️는 CentOS 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64462-109">A ✔️ indicates that the version of CentOS or .NET is still supported.</span></span>
- <span data-ttu-id="64462-110">❌는 CentOS 또는 .NET 버전이 해당 CentOS 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="64462-110">A ❌ indicates that the version of CentOS or .NET isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="64462-111">CentOS 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="64462-111">When both a version of CentOS and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="64462-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="64462-112">CentOS</span></span>                   | <span data-ttu-id="64462-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="64462-113">.NET Core 2.1</span></span> | <span data-ttu-id="64462-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="64462-114">.NET Core 3.1</span></span> | <span data-ttu-id="64462-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="64462-115">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="64462-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="64462-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="64462-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="64462-117">✔️ 2.1</span></span>        | <span data-ttu-id="64462-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="64462-118">✔️ 3.1</span></span>        | <span data-ttu-id="64462-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="64462-119">✔️ 5.0</span></span> |
| <span data-ttu-id="64462-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="64462-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="64462-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="64462-121">✔️ 2.1</span></span>        | <span data-ttu-id="64462-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="64462-122">✔️ 3.1</span></span>        | <span data-ttu-id="64462-123">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="64462-123">✔️ 5.0</span></span> |

<span data-ttu-id="64462-124">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64462-124">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="64462-125">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="64462-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="64462-126">3.0</span><span class="sxs-lookup"><span data-stu-id="64462-126">3.0</span></span>
- <span data-ttu-id="64462-127">2.2</span><span class="sxs-lookup"><span data-stu-id="64462-127">2.2</span></span>
- <span data-ttu-id="64462-128">2.0</span><span class="sxs-lookup"><span data-stu-id="64462-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="remove-preview-versions"></a><span data-ttu-id="64462-129">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="64462-129">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="centos-8-"></a><span data-ttu-id="64462-130">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="64462-130">CentOS 8 ✔️</span></span>

<span data-ttu-id="64462-131">.NET 5.0은 CentOS 8의 기본 패키지 리포지토리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="64462-131">.NET 5.0 is available in the default package repositories for CentOS 8.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="64462-132">CentOS 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="64462-132">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-50](includes/linux-install-50-yum.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="64462-133">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="64462-133">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="64462-134">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="64462-134">Troubleshoot the package manager</span></span>

<span data-ttu-id="64462-135">이 섹션에서는 패키지 관리자를 사용하여 .NET을 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="64462-135">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="64462-136">패키지를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="64462-136">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="64462-137">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="64462-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="64462-138">종속성</span><span class="sxs-lookup"><span data-stu-id="64462-138">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="next-steps"></a><span data-ttu-id="64462-139">다음 단계</span><span class="sxs-lookup"><span data-stu-id="64462-139">Next steps</span></span>

- [<span data-ttu-id="64462-140">.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="64462-140">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="64462-141">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="64462-141">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
