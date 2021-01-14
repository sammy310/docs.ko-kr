---
title: Fedora에 .NET 설치 - .NET
description: Fedora에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 9dd8c6264831e2a9382960be505639f1eba95151
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970826"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-fedora"></a><span data-ttu-id="a2cf8-103">Fedora에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="a2cf8-103">Install the .NET SDK or the .NET Runtime on Fedora</span></span>

<span data-ttu-id="a2cf8-104">.NET은 Fedora에서 지원되며 이 문서에서는 Fedora에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-104">.NET is supported on Fedora and this article describes how to install .NET on Fedora.</span></span> <span data-ttu-id="a2cf8-105">Fedora 버전의 지원이 종료되면 해당 버전에서는 .NET도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-105">When a Fedora version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="install-net-50"></a><span data-ttu-id="a2cf8-106">.NET 5.0 설치</span><span class="sxs-lookup"><span data-stu-id="a2cf8-106">Install .NET 5.0</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

<span data-ttu-id="a2cf8-107">**Fedora 32**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-107">**Fedora 32**</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/32/prod.repo
```

<span data-ttu-id="a2cf8-108">**Fedora 33**</span><span class="sxs-lookup"><span data-stu-id="a2cf8-108">**Fedora 33**</span></span>

```bash
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/33/prod.repo
```

[!INCLUDE [linux-dnf-install-50](includes/linux-install-50-dnf.md)]

## <a name="install-net-core-31"></a><span data-ttu-id="a2cf8-109">.NET Core 3.1 설치</span><span class="sxs-lookup"><span data-stu-id="a2cf8-109">Install .NET Core 3.1</span></span>

<span data-ttu-id="a2cf8-110">Fedora의 기본 패키지 리포지토리에서 사용할 수 있는 .NET의 최신 버전은 .NET Core 3.1입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-110">The latest version of .NET available in the default package repositories for Fedora is .NET Core 3.1.</span></span>

[!INCLUDE [linux-dnf-install-31](includes/linux-install-31-dnf.md)]

## <a name="supported-distributions"></a><span data-ttu-id="a2cf8-111">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="a2cf8-111">Supported distributions</span></span>

<span data-ttu-id="a2cf8-112">다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Fedora 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-112">The following table is a list of currently supported .NET releases and the versions of Fedora they're supported on.</span></span> <span data-ttu-id="a2cf8-113">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Fedora 버전이 지원 종료에 도달](https://fedoraproject.org/wiki/End_of_life)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-113">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Fedora reaches end-of-life](https://fedoraproject.org/wiki/End_of_life).</span></span>

- <span data-ttu-id="a2cf8-114">✔️는 Fedora 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-114">A ✔️ indicates that the version of Fedora or .NET is still supported.</span></span>
- <span data-ttu-id="a2cf8-115">❌는 Fedora 또는 .NET 버전이 해당 Fedora 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-115">A ❌ indicates that the version of Fedora or .NET isn't supported on that Fedora release.</span></span>
- <span data-ttu-id="a2cf8-116">Fedora 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-116">When both a version of Fedora and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="a2cf8-117">.NET 버전</span><span class="sxs-lookup"><span data-stu-id="a2cf8-117">.NET Version</span></span>  | <span data-ttu-id="a2cf8-118">Fedora 33 ✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-118">Fedora 33 ✔️</span></span> | <span data-ttu-id="a2cf8-119">32 ✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-119">32 ✔️</span></span> | <span data-ttu-id="a2cf8-120">31 ❌</span><span class="sxs-lookup"><span data-stu-id="a2cf8-120">31 ❌</span></span> | <span data-ttu-id="a2cf8-121">30 ❌</span><span class="sxs-lookup"><span data-stu-id="a2cf8-121">30 ❌</span></span> | <span data-ttu-id="a2cf8-122">29 ❌</span><span class="sxs-lookup"><span data-stu-id="a2cf8-122">29 ❌</span></span> | <span data-ttu-id="a2cf8-123">28 ❌</span><span class="sxs-lookup"><span data-stu-id="a2cf8-123">28 ❌</span></span> | <span data-ttu-id="a2cf8-124">27 ❌</span><span class="sxs-lookup"><span data-stu-id="a2cf8-124">27 ❌</span></span> |
| ------------  | ---------: | --: | --: | --: | --: | --: | --: |
| <span data-ttu-id="a2cf8-125">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="a2cf8-125">.NET 5.0</span></span>      | <span data-ttu-id="a2cf8-126">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-126">✔️</span></span>        | <span data-ttu-id="a2cf8-127">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-127">✔️</span></span> | ❌|❌ |❌ |❌  |❌ |
| <span data-ttu-id="a2cf8-128">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a2cf8-128">.NET Core 3.1</span></span> | <span data-ttu-id="a2cf8-129">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-129">✔️</span></span>        | <span data-ttu-id="a2cf8-130">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-130">✔️</span></span> | <span data-ttu-id="a2cf8-131">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-131">✔️</span></span>|<span data-ttu-id="a2cf8-132">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-132">✔️</span></span> |<span data-ttu-id="a2cf8-133">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-133">✔️</span></span> |❌  |❌ |
| <span data-ttu-id="a2cf8-134">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a2cf8-134">.NET Core 2.1</span></span> | <span data-ttu-id="a2cf8-135">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-135">✔️</span></span>        | <span data-ttu-id="a2cf8-136">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-136">✔️</span></span> | <span data-ttu-id="a2cf8-137">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-137">✔️</span></span>|<span data-ttu-id="a2cf8-138">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-138">✔️</span></span> |<span data-ttu-id="a2cf8-139">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-139">✔️</span></span> |<span data-ttu-id="a2cf8-140">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-140">✔️</span></span>  |<span data-ttu-id="a2cf8-141">✔️</span><span class="sxs-lookup"><span data-stu-id="a2cf8-141">✔️</span></span> |

<span data-ttu-id="a2cf8-142">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-142">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="a2cf8-143">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-143">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a2cf8-144">3.0</span><span class="sxs-lookup"><span data-stu-id="a2cf8-144">3.0</span></span>
- <span data-ttu-id="a2cf8-145">2.2</span><span class="sxs-lookup"><span data-stu-id="a2cf8-145">2.2</span></span>
- <span data-ttu-id="a2cf8-146">2.0</span><span class="sxs-lookup"><span data-stu-id="a2cf8-146">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="a2cf8-147">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="a2cf8-147">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="dependencies"></a><span data-ttu-id="a2cf8-148">종속성</span><span class="sxs-lookup"><span data-stu-id="a2cf8-148">Dependencies</span></span>

[!INCLUDE [linux-rpm-install-dependencies](includes/linux-rpm-install-dependencies.md)]

## <a name="install-on-older-distributions"></a><span data-ttu-id="a2cf8-149">이전 배포판에 설치</span><span class="sxs-lookup"><span data-stu-id="a2cf8-149">Install on older distributions</span></span>

<span data-ttu-id="a2cf8-150">이전 버전의 Fedora에는 기본 패키지 리포지토리의 .NET Core가 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-150">Older versions of Fedora don't contain .NET Core in the default package repositories.</span></span> <span data-ttu-id="a2cf8-151">[Snap](linux-snap.md) 또는 [_dotnet-install.sh_ 스크립트](linux-scripted-manual.md#scripted-install)를 통해 .NET을 설치하거나 Microsoft의 리포지토리를 사용하여 .NET을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-151">You can install .NET with [snap](linux-snap.md), through the [_dotnet-install.sh_ script](linux-scripted-manual.md#scripted-install), or use Microsoft's repository to install .NET:</span></span>

01. <span data-ttu-id="a2cf8-152">먼저 Microsoft 서명 키를 신뢰할 수 있는 키 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-152">First, add the Microsoft signing key to your list of trusted keys.</span></span>

    ```bash
    sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
    ```

02. <span data-ttu-id="a2cf8-153">그런 다음 Microsoft 패키지 리포지토리를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-153">Next, add the Microsoft package repository.</span></span> <span data-ttu-id="a2cf8-154">리포지토리의 소스는 Fedora의 버전을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-154">The source of the repository is based on your version of Fedora.</span></span>

    | <span data-ttu-id="a2cf8-155">Fedora 버전</span><span class="sxs-lookup"><span data-stu-id="a2cf8-155">Fedora Version</span></span> | <span data-ttu-id="a2cf8-156">패키지 리포지토리</span><span class="sxs-lookup"><span data-stu-id="a2cf8-156">Package repository</span></span> |
    | -------------- | ------- |
    | <span data-ttu-id="a2cf8-157">31</span><span class="sxs-lookup"><span data-stu-id="a2cf8-157">31</span></span>             | `https://packages.microsoft.com/config/fedora/31/prod.repo` |
    | <span data-ttu-id="a2cf8-158">30</span><span class="sxs-lookup"><span data-stu-id="a2cf8-158">30</span></span>             | `https://packages.microsoft.com/config/fedora/30/prod.repo` |
    | <span data-ttu-id="a2cf8-159">29</span><span class="sxs-lookup"><span data-stu-id="a2cf8-159">29</span></span>             | `https://packages.microsoft.com/config/fedora/29/prod.repo` |
    | <span data-ttu-id="a2cf8-160">28</span><span class="sxs-lookup"><span data-stu-id="a2cf8-160">28</span></span>             | `https://packages.microsoft.com/config/fedora/28/prod.repo` |
    | <span data-ttu-id="a2cf8-161">27</span><span class="sxs-lookup"><span data-stu-id="a2cf8-161">27</span></span>             | `https://packages.microsoft.com/config/fedora/27/prod.repo` |

    ```bash
    sudo wget -O /etc/yum.repos.d/microsoft-prod.repo https://packages.microsoft.com/config/fedora/31/prod.repo
    ```

[!INCLUDE [linux-dnf-install-31](./includes/linux-install-31-dnf.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a2cf8-162">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="a2cf8-162">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="a2cf8-163">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a2cf8-163">Troubleshoot the package manager</span></span>

<span data-ttu-id="a2cf8-164">이 섹션에서는 패키지 관리자를 사용하여 .NET 또는 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2cf8-164">This section provides information on common errors you may get while using the package manager to install .NET or .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="a2cf8-165">패키지를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="a2cf8-165">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="a2cf8-166">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="a2cf8-166">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="next-steps"></a><span data-ttu-id="a2cf8-167">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a2cf8-167">Next steps</span></span>

- [<span data-ttu-id="a2cf8-168">.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="a2cf8-168">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="a2cf8-169">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="a2cf8-169">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
