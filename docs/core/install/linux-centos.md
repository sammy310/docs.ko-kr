---
title: CentOS에 .NET Core 설치 - .NET Core
description: CentOS에 .NET Core SDK와 .NET Core 런타임을 설치하는 다양한 방법을 보여줍니다.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 9f4de70b4989be1d162f384518a015816a3e75a9
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324897"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-centos"></a><span data-ttu-id="abdbb-103">CentOS에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="abdbb-103">Install .NET Core SDK or .NET Core Runtime on CentOS</span></span>

<span data-ttu-id="abdbb-104">.NET Core는 CentOS에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-104">.NET Core is supported on CentOS.</span></span> <span data-ttu-id="abdbb-105">이 문서에서는 CentOS에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-105">This article describes how to install .NET Core on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="abdbb-106">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="abdbb-106">Supported distributions</span></span>

<span data-ttu-id="abdbb-107">다음 표는 CentOS 7과 CentOS 8에서 현재 지원되는 .NET Core 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-107">The following table is a list of currently supported .NET Core releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="abdbb-108">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 CentOS 버전이 더 이상 지원되지 않을 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="abdbb-109">✔️는 CentOS 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-109">A ✔️ indicates that the version of CentOS or .NET Core is still supported.</span></span>
- <span data-ttu-id="abdbb-110">❌는 CentOS 또는 .NET Core 버전이 해당 CentOS 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-110">A ❌ indicates that the version of CentOS or .NET Core isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="abdbb-111">CentOS 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-111">When both a version of CentOS and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="abdbb-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="abdbb-112">CentOS</span></span>                   | <span data-ttu-id="abdbb-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="abdbb-113">.NET Core 2.1</span></span> | <span data-ttu-id="abdbb-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="abdbb-114">.NET Core 3.1</span></span> | <span data-ttu-id="abdbb-115">.NET 5 미리 보기(수동 설치만 해당)</span><span class="sxs-lookup"><span data-stu-id="abdbb-115">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="abdbb-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="abdbb-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="abdbb-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="abdbb-117">✔️ 2.1</span></span>        | <span data-ttu-id="abdbb-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="abdbb-118">✔️ 3.1</span></span>        | <span data-ttu-id="abdbb-119">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="abdbb-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="abdbb-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="abdbb-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="abdbb-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="abdbb-121">✔️ 2.1</span></span>        | <span data-ttu-id="abdbb-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="abdbb-122">✔️ 3.1</span></span>        | <span data-ttu-id="abdbb-123">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="abdbb-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="abdbb-124">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="abdbb-125">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="abdbb-126">3.0</span><span class="sxs-lookup"><span data-stu-id="abdbb-126">3.0</span></span>
- <span data-ttu-id="abdbb-127">2.2</span><span class="sxs-lookup"><span data-stu-id="abdbb-127">2.2</span></span>
- <span data-ttu-id="abdbb-128">2.0</span><span class="sxs-lookup"><span data-stu-id="abdbb-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="abdbb-129">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="abdbb-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a><span data-ttu-id="abdbb-130">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="abdbb-130">CentOS 8 ✔️</span></span>

<span data-ttu-id="abdbb-131">.NET Core 3.1은 CentOS 8의 기본 패키지 리포지토리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-131">.NET Core 3.1 is available in the default package repositories for CentOS 8.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="abdbb-132">CentOS 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="abdbb-132">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-31](includes/linux-install-31-yum.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="abdbb-133">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="abdbb-133">Troubleshoot the package manager</span></span>

<span data-ttu-id="abdbb-134">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="abdbb-134">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="abdbb-135">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="abdbb-135">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="abdbb-136">Snap</span><span class="sxs-lookup"><span data-stu-id="abdbb-136">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="abdbb-137">종속성</span><span class="sxs-lookup"><span data-stu-id="abdbb-137">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="abdbb-138">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="abdbb-138">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="abdbb-139">수동 설치</span><span class="sxs-lookup"><span data-stu-id="abdbb-139">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="abdbb-140">다음 단계</span><span class="sxs-lookup"><span data-stu-id="abdbb-140">Next steps</span></span>

- <span data-ttu-id="abdbb-141">[자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="abdbb-141">[Tutorial: Create a console application with .NET Core SDK using Visual Studio Code](../tutorials/with-visual-studio-code.md)</span></span>
