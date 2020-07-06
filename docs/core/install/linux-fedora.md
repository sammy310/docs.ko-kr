---
title: Fedora에 .NET Core 설치 - .NET Core
description: Fedora에 .NET Core SDK와 .NET Core 런타임을 설치하는 다양한 방법을 보여줍니다.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: c90c08eefa074fa139642a268f879af79d7280da
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619483"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-fedora"></a><span data-ttu-id="42640-103">Fedora에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="42640-103">Install .NET Core SDK or .NET Core Runtime on Fedora</span></span>

<span data-ttu-id="42640-104">.NET Core는 Fedora에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="42640-104">.NET Core is supported on Fedora.</span></span> <span data-ttu-id="42640-105">이 문서에서는 Fedora에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="42640-105">This article describes how to install .NET Core on Fedora.</span></span> <span data-ttu-id="42640-106">Fedora 버전의 지원이 종료되면 해당 버전에서는 .NET Core도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42640-106">When a Fedora version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="42640-107">그러나, 이러한 지침은 지원되지 않는 버전에서 .NET Core를 실행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42640-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="42640-108">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="42640-108">Supported distributions</span></span>

<span data-ttu-id="42640-109">다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 Fedora 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="42640-109">The following table is a list of currently supported .NET Core releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="42640-110">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Fedora 버전이 지원 종료에 도달](https://fedoraproject.org/wiki/End_of_life)할 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="42640-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="42640-111">✔️는 Fedora 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42640-111">A ✔️ indicates that the version of Fedora or .NET Core is still supported.</span></span>
- <span data-ttu-id="42640-112">❌는 Fedora 또는 .NET Core 버전이 해당 Fedora 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="42640-112">A ❌ indicates that the version of Fedora or .NET Core isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="42640-113">Fedora 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="42640-113">When both a version of Fedora and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="42640-114">Fedora</span><span class="sxs-lookup"><span data-stu-id="42640-114">Fedora</span></span>                   | <span data-ttu-id="42640-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="42640-115">.NET Core 2.1</span></span> | <span data-ttu-id="42640-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="42640-116">.NET Core 3.1</span></span> | <span data-ttu-id="42640-117">.NET 5 미리 보기(수동 설치만 해당)</span><span class="sxs-lookup"><span data-stu-id="42640-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="42640-118">✔️ [32](linux-fedora.md#fedora-32-)</span><span class="sxs-lookup"><span data-stu-id="42640-118">✔️ [32](linux-fedora.md#fedora-32-)</span></span> | <span data-ttu-id="42640-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="42640-119">✔️ 2.1</span></span>        | <span data-ttu-id="42640-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="42640-120">✔️ 3.1</span></span>        | <span data-ttu-id="42640-121">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="42640-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="42640-122">✔️ [31](linux-fedora.md#fedora-31-)</span><span class="sxs-lookup"><span data-stu-id="42640-122">✔️ [31](linux-fedora.md#fedora-31-)</span></span> | <span data-ttu-id="42640-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="42640-123">✔️ 2.1</span></span>        | <span data-ttu-id="42640-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="42640-124">✔️ 3.1</span></span>        | <span data-ttu-id="42640-125">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="42640-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="42640-126">❌ [30](linux-fedora.md#fedora-30-)</span><span class="sxs-lookup"><span data-stu-id="42640-126">❌ [30](linux-fedora.md#fedora-30-)</span></span> | <span data-ttu-id="42640-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="42640-127">✔️ 2.1</span></span>        | <span data-ttu-id="42640-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="42640-128">✔️ 3.1</span></span>        | <span data-ttu-id="42640-129">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="42640-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="42640-130">❌ [29](linux-fedora.md#fedora-29-)</span><span class="sxs-lookup"><span data-stu-id="42640-130">❌ [29](linux-fedora.md#fedora-29-)</span></span> | <span data-ttu-id="42640-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="42640-131">✔️ 2.1</span></span>        | <span data-ttu-id="42640-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="42640-132">✔️ 3.1</span></span>        | <span data-ttu-id="42640-133">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="42640-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="42640-134">❌ [28](linux-fedora.md#fedora-28-)</span><span class="sxs-lookup"><span data-stu-id="42640-134">❌ [28](linux-fedora.md#fedora-28-)</span></span> | <span data-ttu-id="42640-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="42640-135">✔️ 2.1</span></span>        | <span data-ttu-id="42640-136">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="42640-136">❌ 3.1</span></span>        | <span data-ttu-id="42640-137">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="42640-137">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="42640-138">❌ [27](linux-fedora.md#fedora-27-)</span><span class="sxs-lookup"><span data-stu-id="42640-138">❌ [27](linux-fedora.md#fedora-27-)</span></span> | <span data-ttu-id="42640-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="42640-139">✔️ 2.1</span></span>        | <span data-ttu-id="42640-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="42640-140">❌ 3.1</span></span>        | <span data-ttu-id="42640-141">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="42640-141">❌ 5.0 Preview</span></span> |

<span data-ttu-id="42640-142">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="42640-142">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="42640-143">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="42640-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="42640-144">3.0</span><span class="sxs-lookup"><span data-stu-id="42640-144">3.0</span></span>
- <span data-ttu-id="42640-145">2.2</span><span class="sxs-lookup"><span data-stu-id="42640-145">2.2</span></span>
- <span data-ttu-id="42640-146">2.0</span><span class="sxs-lookup"><span data-stu-id="42640-146">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="42640-147">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="42640-147">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="fedora-32-"></a><span data-ttu-id="42640-148">Fedora 32 ✔️</span><span class="sxs-lookup"><span data-stu-id="42640-148">Fedora 32 ✔️</span></span>

<span data-ttu-id="42640-149">.NET Core 3.1은 Fedora 32의 기본 패키지 리포지토리에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="42640-149">.NET Core 3.1 is available in the default package repositories for Fedora 32.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-31-"></a><span data-ttu-id="42640-150">Fedora 31 ✔️</span><span class="sxs-lookup"><span data-stu-id="42640-150">Fedora 31 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-30-"></a><span data-ttu-id="42640-151">Fedora 30 ❌</span><span class="sxs-lookup"><span data-stu-id="42640-151">Fedora 30 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/30/prod.repo
```

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="fedora-29-"></a><span data-ttu-id="42640-152">Fedora 29 ❌</span><span class="sxs-lookup"><span data-stu-id="42640-152">Fedora 29 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/29/prod.repo
```

[!INCLUDE [linux-dnf-install-30](includes/linux-install-30-dnf.md)]

## <a name="fedora-28-"></a><span data-ttu-id="42640-153">Fedora 28 ❌</span><span class="sxs-lookup"><span data-stu-id="42640-153">Fedora 28 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/28/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="fedora-27-"></a><span data-ttu-id="42640-154">Fedora 27 ❌</span><span class="sxs-lookup"><span data-stu-id="42640-154">Fedora 27 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-fedora.md)]

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/27/prod.repo
```

[!INCLUDE [linux-dnf-install-20](includes/linux-install-20-dnf.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="42640-155">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="42640-155">Troubleshoot the package manager</span></span>

<span data-ttu-id="42640-156">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="42640-156">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="42640-157">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="42640-157">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="42640-158">Snap</span><span class="sxs-lookup"><span data-stu-id="42640-158">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="42640-159">종속성</span><span class="sxs-lookup"><span data-stu-id="42640-159">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="42640-160">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="42640-160">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="42640-161">수동 설치</span><span class="sxs-lookup"><span data-stu-id="42640-161">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="42640-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="42640-162">Next steps</span></span>

- <span data-ttu-id="42640-163">[자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="42640-163">[Tutorial: Create a console application with .NET Core SDK using Visual Studio Code](../tutorials/with-visual-studio-code.md)</span></span>
