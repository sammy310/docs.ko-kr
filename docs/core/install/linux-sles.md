---
title: SLES에 .NET Core 설치 - .NET Core
description: SLES에 .NET Core SDK와 .NET Core 런타임을 설치하는 다양한 방법을 보여줍니다.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 9816e1f0253be58dc04c1302f334a7ea0b810810
ms.sourcegitcommit: 5fd4696a3e5791b2a8c449ccffda87f2cc2d4894
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/15/2020
ms.locfileid: "84768402"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-sles"></a><span data-ttu-id="85328-103">SLES에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="85328-103">Install .NET Core SDK or .NET Core Runtime on SLES</span></span>

<span data-ttu-id="85328-104">.NET Core는 SLES에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85328-104">.NET Core is supported on SLES.</span></span> <span data-ttu-id="85328-105">이 문서에서는 SLES에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="85328-105">This article describes how to install .NET Core on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="85328-106">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="85328-106">Supported distributions</span></span>

<span data-ttu-id="85328-107">다음 표는 SLES 12 SP2와 SLES 15에서 현재 지원되는 .NET Core 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="85328-107">The following table is a list of currently supported .NET Core releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="85328-108">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 SLES 버전이 더 이상 지원되지 않을 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85328-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="85328-109">✔️는 SLES 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85328-109">A ✔️ indicates that the version of SLES or .NET Core is still supported.</span></span>
- <span data-ttu-id="85328-110">❌는 SLES 또는 .NET Core 버전이 해당 SLES 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="85328-110">A ❌ indicates that the version of SLES or .NET Core isn't supported on that SLES release.</span></span>
- <span data-ttu-id="85328-111">SLES 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85328-111">When both a version of SLES and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="85328-112">SLES</span><span class="sxs-lookup"><span data-stu-id="85328-112">SLES</span></span>                   | <span data-ttu-id="85328-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="85328-113">.NET Core 2.1</span></span> | <span data-ttu-id="85328-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="85328-114">.NET Core 3.1</span></span> | <span data-ttu-id="85328-115">.NET 5 미리 보기(수동 설치만 해당)</span><span class="sxs-lookup"><span data-stu-id="85328-115">.NET 5 Preview (manual install only)</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="85328-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="85328-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="85328-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="85328-117">✔️ 2.1</span></span>        | <span data-ttu-id="85328-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="85328-118">✔️ 3.1</span></span>        | <span data-ttu-id="85328-119">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="85328-119">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="85328-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="85328-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="85328-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="85328-121">✔️ 2.1</span></span>        | <span data-ttu-id="85328-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="85328-122">✔️ 3.1</span></span>        | <span data-ttu-id="85328-123">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="85328-123">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="85328-124">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85328-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="85328-125">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="85328-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="85328-126">3.0</span><span class="sxs-lookup"><span data-stu-id="85328-126">3.0</span></span>
- <span data-ttu-id="85328-127">2.2</span><span class="sxs-lookup"><span data-stu-id="85328-127">2.2</span></span>
- <span data-ttu-id="85328-128">2.0</span><span class="sxs-lookup"><span data-stu-id="85328-128">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="85328-129">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="85328-129">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="sles-15-"></a><span data-ttu-id="85328-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="85328-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="85328-131">현재 SLES 15 Microsoft 리포지토리 설치 패키지는 *microsoft-prod.repo* 파일을 잘못된 디렉터리에 설치하므로 zypper가 .NET Core 패키지를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85328-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET Core packages.</span></span> <span data-ttu-id="85328-132">이 문제를 해결하려면 올바른 디렉터리에 symlink를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85328-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="85328-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="85328-133">SLES 12 ✔️</span></span>

<span data-ttu-id="85328-134">.NET Core에는 SLES 12 제품군에 대한 최소 요건으로 SP2가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85328-134">.NET Core requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="85328-135">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="85328-135">Troubleshoot the package manager</span></span>

<span data-ttu-id="85328-136">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85328-136">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="85328-137">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="85328-137">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="85328-138">종속성</span><span class="sxs-lookup"><span data-stu-id="85328-138">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="85328-139">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="85328-139">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="85328-140">수동 설치</span><span class="sxs-lookup"><span data-stu-id="85328-140">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="85328-141">다음 단계</span><span class="sxs-lookup"><span data-stu-id="85328-141">Next steps</span></span>

- <span data-ttu-id="85328-142">[자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="85328-142">[Tutorial: Create a console application with .NET Core SDK using Visual Studio Code](../tutorials/with-visual-studio-code.md)</span></span>
