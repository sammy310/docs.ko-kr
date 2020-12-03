---
title: CentOS에 .NET 설치 - .NET
description: CentOS에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: b30aa206057107aa17fcd62e0f042f9fe3ad56dc
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031932"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-centos"></a><span data-ttu-id="d9f4b-103">CentOS에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="d9f4b-103">Install the .NET SDK or the .NET Runtime on CentOS</span></span>

<span data-ttu-id="d9f4b-104">.NET은 CentOS에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-104">.NET is supported on CentOS.</span></span> <span data-ttu-id="d9f4b-105">이 문서에서는 CentOS에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-105">This article describes how to install .NET on CentOS.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="d9f4b-106">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="d9f4b-106">Supported distributions</span></span>

<span data-ttu-id="d9f4b-107">다음 표는 CentOS 7과 CentOS 8에서 현재 지원되는 .NET 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-107">The following table is a list of currently supported .NET releases on both CentOS 7 and CentOS 8.</span></span> <span data-ttu-id="d9f4b-108">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 CentOS 버전이 더 이상 지원되지 않을 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of CentOS is no longer supported.</span></span>

- <span data-ttu-id="d9f4b-109">✔️는 CentOS 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-109">A ✔️ indicates that the version of CentOS or .NET is still supported.</span></span>
- <span data-ttu-id="d9f4b-110">❌는 CentOS 또는 .NET 버전이 해당 CentOS 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-110">A ❌ indicates that the version of CentOS or .NET isn't supported on that CentOS release.</span></span>
- <span data-ttu-id="d9f4b-111">CentOS 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-111">When both a version of CentOS and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="d9f4b-112">CentOS</span><span class="sxs-lookup"><span data-stu-id="d9f4b-112">CentOS</span></span>                   | <span data-ttu-id="d9f4b-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="d9f4b-113">.NET Core 2.1</span></span> | <span data-ttu-id="d9f4b-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="d9f4b-114">.NET Core 3.1</span></span> | <span data-ttu-id="d9f4b-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="d9f4b-115">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="d9f4b-116">✔️ [8](#centos-8-)</span><span class="sxs-lookup"><span data-stu-id="d9f4b-116">✔️ [8](#centos-8-)</span></span> | <span data-ttu-id="d9f4b-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="d9f4b-117">✔️ 2.1</span></span>        | <span data-ttu-id="d9f4b-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="d9f4b-118">✔️ 3.1</span></span>        | <span data-ttu-id="d9f4b-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="d9f4b-119">✔️ 5.0</span></span> |
| <span data-ttu-id="d9f4b-120">✔️ [7](#centos-7-)</span><span class="sxs-lookup"><span data-stu-id="d9f4b-120">✔️ [7](#centos-7-)</span></span> | <span data-ttu-id="d9f4b-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="d9f4b-121">✔️ 2.1</span></span>        | <span data-ttu-id="d9f4b-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="d9f4b-122">✔️ 3.1</span></span>        | <span data-ttu-id="d9f4b-123">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="d9f4b-123">✔️ 5.0</span></span> |

<span data-ttu-id="d9f4b-124">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-124">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="d9f4b-125">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="d9f4b-126">3.0</span><span class="sxs-lookup"><span data-stu-id="d9f4b-126">3.0</span></span>
- <span data-ttu-id="d9f4b-127">2.2</span><span class="sxs-lookup"><span data-stu-id="d9f4b-127">2.2</span></span>
- <span data-ttu-id="d9f4b-128">2.0</span><span class="sxs-lookup"><span data-stu-id="d9f4b-128">2.0</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="remove-preview-versions"></a><span data-ttu-id="d9f4b-129">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="d9f4b-129">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="d9f4b-130">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="d9f4b-130">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="centos-8-"></a><span data-ttu-id="d9f4b-131">CentOS 8 ✔️</span><span class="sxs-lookup"><span data-stu-id="d9f4b-131">CentOS 8 ✔️</span></span>

> [!TIP]
> <span data-ttu-id="d9f4b-132">.NET 5.0은 기본 패키지 리포지토리에서 아직 사용할 수 없지만 .NET Core 3.1은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-132">.NET 5.0 isn't yet available in the default package repositories, but .NET Core 3.1 is.</span></span> <span data-ttu-id="d9f4b-133">.NET Core 3.1을 설치하려면 `aspnetcore-runtime-3.1` 또는 `dotnet-sdk-3.1`과 같은 적절한 패키지에서 `dnf install` 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-133">To install .NET Core 3.1, use the `dnf install` command with the appropriate package, such as `aspnetcore-runtime-3.1` or `dotnet-sdk-3.1`.</span></span> <span data-ttu-id="d9f4b-134">다음은 .NET 5.0에 대한 지침입니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-134">The following instructions are for .NET 5.0.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/8/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="centos-7-"></a><span data-ttu-id="d9f4b-135">CentOS 7 ✔️</span><span class="sxs-lookup"><span data-stu-id="d9f4b-135">CentOS 7 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/centos/7/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-yum-install-50](includes/linux-install-50-yum.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="d9f4b-136">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="d9f4b-136">Troubleshoot the package manager</span></span>

<span data-ttu-id="d9f4b-137">이 섹션에서는 패키지 관리자를 사용하여 .NET을 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d9f4b-137">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="d9f4b-138">패키지를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="d9f4b-138">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="d9f4b-139">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="d9f4b-139">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="d9f4b-140">Snap</span><span class="sxs-lookup"><span data-stu-id="d9f4b-140">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="d9f4b-141">종속성</span><span class="sxs-lookup"><span data-stu-id="d9f4b-141">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="d9f4b-142">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="d9f4b-142">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="d9f4b-143">수동 설치</span><span class="sxs-lookup"><span data-stu-id="d9f4b-143">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="d9f4b-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d9f4b-144">Next steps</span></span>

- [<span data-ttu-id="d9f4b-145">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="d9f4b-145">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
