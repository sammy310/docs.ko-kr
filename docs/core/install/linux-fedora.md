---
title: Fedora에 .NET 설치 - .NET
description: Fedora에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 02/17/2021
ms.openlocfilehash: efaad4788db2200b1a47f9b4ae2414730588c6ae
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102255761"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="2471a-103">Fedora에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="2471a-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="2471a-104">.NET은 Fedora에서 지원되며 이 문서에서는 Fedora에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-104">.NET is supported on Fedora and this article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="2471a-105">Fedora 버전의 지원이 종료되면 해당 버전에서는 .NET도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-105">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

<span data-ttu-id="2471a-106">패키지 관리자 없이 .NET을 설치하는 방법에 대한 자세한 내용은 다음 문서 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2471a-106">For more information on installing .NET without a package manager, see one of the following articles:</span></span>

- [<span data-ttu-id="2471a-107">Snap을 사용하여 .NET SDK 또는 .NET 런타임 설치.</span><span class="sxs-lookup"><span data-stu-id="2471a-107">Install the .NET SDK or the .NET Runtime with Snap.</span></span>](linux-snap.md)
- [<span data-ttu-id="2471a-108">스크립트를 사용하여 .NET SDK 또는 .NET 런타임 설치.</span><span class="sxs-lookup"><span data-stu-id="2471a-108">Install the .NET SDK or the .NET Runtime with a script.</span></span>](linux-scripted-manual.md#scripted-install)
- [<span data-ttu-id="2471a-109">수동으로 .NET SDK 또는 .NET 런타임 설치.</span><span class="sxs-lookup"><span data-stu-id="2471a-109">Install the .NET SDK or the .NET Runtime manually.</span></span>](linux-scripted-manual.md#manual-install)

## <a name="install-net-50"></a><span data-ttu-id="2471a-110">.NET 5.0 설치</span><span class="sxs-lookup"><span data-stu-id="2471a-110">Install .NET 5.0</span></span>

<span data-ttu-id="2471a-111">Fedora의 기본 패키지 리포지토리에서 사용할 수 있는 .NET의 최신 버전은 .NET 5.0입니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-111">The latest version of .NET available in the default package repositories for Fedora is .NET 5.0.</span></span>

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="install-net-core-31"></a><span data-ttu-id="2471a-112">.NET Core 3.1 설치</span><span class="sxs-lookup"><span data-stu-id="2471a-112">Install .NET Core 3.1</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="supported-distributions"></a><span data-ttu-id="2471a-113">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="2471a-113">Supported distributions</span></span>

<span data-ttu-id="2471a-114">다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Fedora 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-114">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="2471a-115">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Fedora 버전이 지원 종료에 도달](https://fedoraproject.org/wiki/End_of_life)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-115">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="2471a-116">✔️는 Fedora 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-116">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="2471a-117">❌는 Fedora 또는 .NET 버전이 해당 Fedora 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-117">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="2471a-118">Fedora 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-118">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="2471a-119">.NET 버전</span><span class="sxs-lookup"><span data-stu-id="2471a-119">.NET Version</span></span>  | <span data-ttu-id="2471a-120">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-120">Fedora 33 ✔️</span></span> | <span data-ttu-id="2471a-121">32 ✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-121">32 ✔️</span></span> | <span data-ttu-id="2471a-122">31 ❌</span><span class="sxs-lookup"><span data-stu-id="2471a-122">31 ❌</span></span> | <span data-ttu-id="2471a-123">30 ❌</span><span class="sxs-lookup"><span data-stu-id="2471a-123">30 ❌</span></span> | <span data-ttu-id="2471a-124">29 ❌</span><span class="sxs-lookup"><span data-stu-id="2471a-124">29 ❌</span></span> | <span data-ttu-id="2471a-125">28 ❌</span><span class="sxs-lookup"><span data-stu-id="2471a-125">28 ❌</span></span> | <span data-ttu-id="2471a-126">27 ❌</span><span class="sxs-lookup"><span data-stu-id="2471a-126">27 ❌</span></span> |
| ------------  | ---------: | --: | --: | --: | --: | --: | --: |
| <span data-ttu-id="2471a-127">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2471a-127">.NET 5.0</span></span>      | <span data-ttu-id="2471a-128">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-128">✔️</span></span>        | <span data-ttu-id="2471a-129">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-129">✔️</span></span> | ❌|❌ |❌ |❌  |❌ |
| <span data-ttu-id="2471a-130">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2471a-130">.NET Core 3.1</span></span> | <span data-ttu-id="2471a-131">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-131">✔️</span></span>        | <span data-ttu-id="2471a-132">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-132">✔️</span></span> | <span data-ttu-id="2471a-133">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-133">✔️</span></span>|<span data-ttu-id="2471a-134">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-134">✔️</span></span> |<span data-ttu-id="2471a-135">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-135">✔️</span></span> |❌  |❌ |
| <span data-ttu-id="2471a-136">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2471a-136">.NET Core 2.1</span></span> | <span data-ttu-id="2471a-137">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-137">✔️</span></span>        | <span data-ttu-id="2471a-138">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-138">✔️</span></span> | <span data-ttu-id="2471a-139">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-139">✔️</span></span>|<span data-ttu-id="2471a-140">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-140">✔️</span></span> |<span data-ttu-id="2471a-141">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-141">✔️</span></span> |<span data-ttu-id="2471a-142">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-142">✔️</span></span>  |<span data-ttu-id="2471a-143">✔️</span><span class="sxs-lookup"><span data-stu-id="2471a-143">✔️</span></span> |

<span data-ttu-id="2471a-144">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-144">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="2471a-145">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-145">The downloads for these still remain published:</span></span>

- <span data-ttu-id="2471a-146">3.0</span><span class="sxs-lookup"><span data-stu-id="2471a-146">3.0</span></span>
- <span data-ttu-id="2471a-147">2.2</span><span class="sxs-lookup"><span data-stu-id="2471a-147">2.2</span></span>
- <span data-ttu-id="2471a-148">2.0</span><span class="sxs-lookup"><span data-stu-id="2471a-148">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="2471a-149">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="2471a-149">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="dependencies"></a><span data-ttu-id="2471a-150">종속성</span><span class="sxs-lookup"><span data-stu-id="2471a-150">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="install-on-older-distributions"></a><span data-ttu-id="2471a-151">이전 배포판에 설치</span><span class="sxs-lookup"><span data-stu-id="2471a-151">Install on older distributions</span></span>

<span data-ttu-id="2471a-152">이전 버전의 Fedora에는 기본 패키지 리포지토리의 .NET Core가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-152">Older versions of Fedora don't contain .NET Core in the default package repositories.</span></span> <span data-ttu-id="2471a-153">[Snap](linux-snap.md) 또는 [_dotnet-install.sh_ 스크립트](linux-scripted-manual.md#scripted-install)를 통해 .NET을 설치하거나 Microsoft의 리포지토리를 사용하여 .NET을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-153">You can install .NET with [snap](linux-snap.md), through the [_dotnet-install.sh_ script](linux-scripted-manual.md#scripted-install), or use Microsoft's repository to install .NET:</span></span>

01. <span data-ttu-id="2471a-154">먼저 Microsoft 서명 키를 신뢰할 수 있는 키 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-154">First, add the Microsoft signing key to your list of trusted keys.</span></span>

    ```bash
    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    ```

02. <span data-ttu-id="2471a-155">그런 다음 Microsoft 패키지 리포지토리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-155">Next, add the Microsoft package repository.</span></span> <span data-ttu-id="2471a-156">리포지토리의 소스는 Fedora의 버전을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-156">The source of the repository is based on your version of Fedora.</span></span>

    | <span data-ttu-id="2471a-157">Fedora 버전</span><span class="sxs-lookup"><span data-stu-id="2471a-157">Fedora Version</span></span> | <span data-ttu-id="2471a-158">패키지 리포지토리</span><span class="sxs-lookup"><span data-stu-id="2471a-158">Package repository</span></span> |
    | -------------- | ------- |
    | <span data-ttu-id="2471a-159">31</span><span class="sxs-lookup"><span data-stu-id="2471a-159">31</span></span>             | `https://packages.microsoft.com/config/fedora/31/prod.repo` |
    | <span data-ttu-id="2471a-160">30</span><span class="sxs-lookup"><span data-stu-id="2471a-160">30</span></span>             | `https://packages.microsoft.com/config/fedora/30/prod.repo` |
    | <span data-ttu-id="2471a-161">29</span><span class="sxs-lookup"><span data-stu-id="2471a-161">29</span></span>             | `https://packages.microsoft.com/config/fedora/29/prod.repo` |
    | <span data-ttu-id="2471a-162">28</span><span class="sxs-lookup"><span data-stu-id="2471a-162">28</span></span>             | `https://packages.microsoft.com/config/fedora/28/prod.repo` |
    | <span data-ttu-id="2471a-163">27</span><span class="sxs-lookup"><span data-stu-id="2471a-163">27</span></span>             | `https://packages.microsoft.com/config/fedora/27/prod.repo` |

    ```bash
    sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
    ```

[!INCLUDE [linux-dnf-install-31](./includes/linux-install-31-dnf.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="2471a-164">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="2471a-164">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="2471a-165">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2471a-165">Troubleshoot the package manager</span></span>

<span data-ttu-id="2471a-166">이 섹션에서는 패키지 관리자를 사용하여 .NET 또는 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2471a-166">This section provides information on common errors you may get while using the package manager to install .NET or .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="2471a-167">패키지를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="2471a-167">Unable to find package</span></span>

<span data-ttu-id="2471a-168">패키지 관리자 없이 .NET을 설치하는 방법에 대한 자세한 내용은 다음 문서 중 하나를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2471a-168">For more information on installing .NET without a package manager, see one of the following articles:</span></span>

- [<span data-ttu-id="2471a-169">Snap을 사용하여 .NET SDK 또는 .NET 런타임 설치.</span><span class="sxs-lookup"><span data-stu-id="2471a-169">Install the .NET SDK or the .NET Runtime with Snap.</span></span>](linux-snap.md)
- [<span data-ttu-id="2471a-170">스크립트를 사용하여 .NET SDK 또는 .NET 런타임 설치.</span><span class="sxs-lookup"><span data-stu-id="2471a-170">Install the .NET SDK or the .NET Runtime with a script.</span></span>](linux-scripted-manual.md#scripted-install)
- [<span data-ttu-id="2471a-171">수동으로 .NET SDK 또는 .NET 런타임 설치.</span><span class="sxs-lookup"><span data-stu-id="2471a-171">Install the .NET SDK or the .NET Runtime manually.</span></span>](linux-scripted-manual.md#manual-install)

### <a name="failed-to-fetch"></a><span data-ttu-id="2471a-172">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="2471a-172">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="next-steps"></a><span data-ttu-id="2471a-173">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2471a-173">Next steps</span></span>

- [<span data-ttu-id="2471a-174">.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="2471a-174">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="2471a-175">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="2471a-175">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
