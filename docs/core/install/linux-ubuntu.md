---
title: Ubuntu에 .NET 설치 - .NET
description: Ubuntu에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 14e5e9548d4aa09a586e2038f3e35a489ee65cd2
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970770"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a><span data-ttu-id="16dd8-103">Ubuntu에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="16dd8-103">Install the .NET SDK or the .NET Runtime on Ubuntu</span></span>

<span data-ttu-id="16dd8-104">.NET은 Ubuntu에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-104">.NET is supported on Ubuntu.</span></span> <span data-ttu-id="16dd8-105">이 문서에서는 Ubuntu에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-105">This article describes how to install .NET on Ubuntu.</span></span> <span data-ttu-id="16dd8-106">Ubuntu 버전의 지원이 종료되면 해당 버전에서는 .NET도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-106">When an Ubuntu version falls out of support, .NET is no longer supported with that version.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="16dd8-107">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="16dd8-107">Supported distributions</span></span>

<span data-ttu-id="16dd8-108">다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Ubuntu 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-108">The following table is a list of currently supported .NET releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="16dd8-109">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Ubuntu 버전이 지원 종료에 도달](https://wiki.ubuntu.com/Releases)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-109">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="16dd8-110">✔️는 Ubuntu 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-110">A ✔️ indicates that the version of Ubuntu or .NET is still supported.</span></span>
- <span data-ttu-id="16dd8-111">❌는 Ubuntu 또는 .NET 버전이 해당 Ubuntu 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-111">A ❌ indicates that the version of Ubuntu or .NET isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="16dd8-112">Ubuntu 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-112">When both a version of Ubuntu and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="16dd8-113">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="16dd8-113">Ubuntu</span></span>                   | <span data-ttu-id="16dd8-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-114">.NET Core 2.1</span></span> | <span data-ttu-id="16dd8-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-115">.NET Core 3.1</span></span> | <span data-ttu-id="16dd8-116">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-116">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="16dd8-117">✔️ [20.10](#2010-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-117">✔️ [20.10](#2010-)</span></span>       | <span data-ttu-id="16dd8-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-118">✔️ 2.1</span></span>        | <span data-ttu-id="16dd8-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-119">✔️ 3.1</span></span>        | <span data-ttu-id="16dd8-120">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-120">✔️ 5.0</span></span> |
| <span data-ttu-id="16dd8-121">✔️ [20.04(LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-121">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="16dd8-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-122">✔️ 2.1</span></span>        | <span data-ttu-id="16dd8-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-123">✔️ 3.1</span></span>        | <span data-ttu-id="16dd8-124">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-124">✔️ 5.0</span></span> |
| <span data-ttu-id="16dd8-125">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-125">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="16dd8-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-126">✔️ 2.1</span></span>        | <span data-ttu-id="16dd8-127">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-127">✔️ 3.1</span></span>        | <span data-ttu-id="16dd8-128">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-128">✔️ 5.0</span></span> |
| <span data-ttu-id="16dd8-129">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-129">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="16dd8-130">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-130">✔️ 2.1</span></span>        | <span data-ttu-id="16dd8-131">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-131">✔️ 3.1</span></span>        | <span data-ttu-id="16dd8-132">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-132">❌ 5.0</span></span> |
| <span data-ttu-id="16dd8-133">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-133">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="16dd8-134">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-134">✔️ 2.1</span></span>        | <span data-ttu-id="16dd8-135">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-135">❌ 3.1</span></span>        | <span data-ttu-id="16dd8-136">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-136">❌ 5.0</span></span> |
| <span data-ttu-id="16dd8-137">✔️ [18.04(LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-137">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="16dd8-138">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-138">✔️ 2.1</span></span>        | <span data-ttu-id="16dd8-139">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-139">✔️ 3.1</span></span>        | <span data-ttu-id="16dd8-140">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-140">✔️ 5.0</span></span> |
| <span data-ttu-id="16dd8-141">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-141">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="16dd8-142">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-142">✔️ 2.1</span></span>        | <span data-ttu-id="16dd8-143">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-143">❌ 3.1</span></span>        | <span data-ttu-id="16dd8-144">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-144">❌ 5.0</span></span> |
| <span data-ttu-id="16dd8-145">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-145">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="16dd8-146">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-146">✔️ 2.1</span></span>        | <span data-ttu-id="16dd8-147">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-147">❌ 3.1</span></span>        | <span data-ttu-id="16dd8-148">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-148">❌ 5.0</span></span> |
| <span data-ttu-id="16dd8-149">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-149">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="16dd8-150">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-150">❌ 2.1</span></span>        | <span data-ttu-id="16dd8-151">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-151">❌ 3.1</span></span>        | <span data-ttu-id="16dd8-152">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-152">❌ 5.0</span></span> |
| <span data-ttu-id="16dd8-153">✔️ [16.04(LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="16dd8-153">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="16dd8-154">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-154">✔️ 2.1</span></span>        | <span data-ttu-id="16dd8-155">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="16dd8-155">✔️ 3.1</span></span>        | <span data-ttu-id="16dd8-156">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-156">✔️ 5.0</span></span> |

<span data-ttu-id="16dd8-157">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-157">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="16dd8-158">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-158">The downloads for these still remain published:</span></span>

- <span data-ttu-id="16dd8-159">3.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-159">3.0</span></span>
- <span data-ttu-id="16dd8-160">2.2</span><span class="sxs-lookup"><span data-stu-id="16dd8-160">2.2</span></span>
- <span data-ttu-id="16dd8-161">2.0</span><span class="sxs-lookup"><span data-stu-id="16dd8-161">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="16dd8-162">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="16dd8-162">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="2010-"></a><span data-ttu-id="16dd8-163">20.10 ✔️</span><span class="sxs-lookup"><span data-stu-id="16dd8-163">20.10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="2004-"></a><span data-ttu-id="16dd8-164">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="16dd8-164">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a><span data-ttu-id="16dd8-165">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="16dd8-165">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="16dd8-166">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="16dd8-166">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="16dd8-167">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="16dd8-167">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="16dd8-168">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="16dd8-168">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a><span data-ttu-id="16dd8-169">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="16dd8-169">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="16dd8-170">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="16dd8-170">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="16dd8-171">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="16dd8-171">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="16dd8-172">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="16dd8-172">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="16dd8-173">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="16dd8-173">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="use-apt-to-update-net"></a><span data-ttu-id="16dd8-174">APT를 사용하여 .NET 업데이트</span><span class="sxs-lookup"><span data-stu-id="16dd8-174">Use APT to update .NET</span></span>

<span data-ttu-id="16dd8-175">.NET에 대한 새로운 패치 릴리스가 출시되면 다음 명령을 사용하여 APT를 통해 간단하게 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-175">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="16dd8-176">APT 문제 해결</span><span class="sxs-lookup"><span data-stu-id="16dd8-176">APT troubleshooting</span></span>

<span data-ttu-id="16dd8-177">이 섹션에서는 APT를 사용하여 .NET을 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-177">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="16dd8-178">패키지를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="16dd8-178">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="16dd8-179">찾을 수 없음 \\ 일부 패키지를 설치할 수 없음</span><span class="sxs-lookup"><span data-stu-id="16dd8-179">Unable to locate \\ Some packages could not be installed</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/ubuntu/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="16dd8-180">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="16dd8-180">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="dependencies"></a><span data-ttu-id="16dd8-181">종속성</span><span class="sxs-lookup"><span data-stu-id="16dd8-181">Dependencies</span></span>

<span data-ttu-id="16dd8-182">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-182">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="16dd8-183">그러나 .NET을 수동으로 설치하거나 자체 포함 앱을 게시할 경우 이러한 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-183">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="16dd8-184">libc6</span><span class="sxs-lookup"><span data-stu-id="16dd8-184">libc6</span></span>
- <span data-ttu-id="16dd8-185">libgcc1</span><span class="sxs-lookup"><span data-stu-id="16dd8-185">libgcc1</span></span>
- <span data-ttu-id="16dd8-186">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="16dd8-186">libgssapi-krb5-2</span></span>
- <span data-ttu-id="16dd8-187">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="16dd8-187">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="16dd8-188">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="16dd8-188">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="16dd8-189">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="16dd8-189">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="16dd8-190">libicu66(20.x용)</span><span class="sxs-lookup"><span data-stu-id="16dd8-190">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="16dd8-191">libssl1.0.0(14.x용, 16.x용)</span><span class="sxs-lookup"><span data-stu-id="16dd8-191">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="16dd8-192">libssl1.1(18.x용, 20.x용)</span><span class="sxs-lookup"><span data-stu-id="16dd8-192">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="16dd8-193">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="16dd8-193">libstdc++6</span></span>
- <span data-ttu-id="16dd8-194">zlib1g</span><span class="sxs-lookup"><span data-stu-id="16dd8-194">zlib1g</span></span>

<span data-ttu-id="16dd8-195">*System.Drawing.Common* 어셈블리를 사용하는 .NET 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-195">For .NET apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="16dd8-196">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="16dd8-196">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="16dd8-197">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus* 를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="16dd8-197">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="16dd8-198">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="16dd8-198">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="16dd8-199">다음 단계</span><span class="sxs-lookup"><span data-stu-id="16dd8-199">Next steps</span></span>

- [<span data-ttu-id="16dd8-200">.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="16dd8-200">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="16dd8-201">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="16dd8-201">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
