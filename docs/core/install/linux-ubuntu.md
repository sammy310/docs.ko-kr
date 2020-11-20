---
title: Ubuntu에 .NET 설치 - .NET
description: Ubuntu에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: 419bcf3ccd011cadba8f8c64e195d7dbdbf7e241
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/11/2020
ms.locfileid: "94507030"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-ubuntu"></a><span data-ttu-id="2e89e-103">Ubuntu에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="2e89e-103">Install the .NET SDK or the .NET Runtime on Ubuntu</span></span>

<span data-ttu-id="2e89e-104">.NET은 Ubuntu에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-104">.NET is supported on Ubuntu.</span></span> <span data-ttu-id="2e89e-105">이 문서에서는 Ubuntu에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-105">This article describes how to install .NET on Ubuntu.</span></span> <span data-ttu-id="2e89e-106">Ubuntu 버전의 지원이 종료되면 해당 버전에서는 .NET도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-106">When an Ubuntu version falls out of support, .NET is no longer supported with that version.</span></span> <span data-ttu-id="2e89e-107">그러나 이러한 지침은 지원되지 않더라도 해당 버전에서 .NET을 실행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-107">However, these instructions may help you to get .NET running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="2e89e-108">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="2e89e-108">Supported distributions</span></span>

<span data-ttu-id="2e89e-109">다음 표는 현재 지원되는 .NET 릴리스와 해당 릴리스가 지원되는 Ubuntu 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-109">The following table is a list of currently supported .NET releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="2e89e-110">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Ubuntu 버전이 지원 종료에 도달](https://wiki.ubuntu.com/Releases)할 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-110">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="2e89e-111">✔️는 Ubuntu 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-111">A ✔️ indicates that the version of Ubuntu or .NET is still supported.</span></span>
- <span data-ttu-id="2e89e-112">❌는 Ubuntu 또는 .NET 버전이 해당 Ubuntu 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-112">A ❌ indicates that the version of Ubuntu or .NET isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="2e89e-113">Ubuntu 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-113">When both a version of Ubuntu and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="2e89e-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="2e89e-114">Ubuntu</span></span>                   | <span data-ttu-id="2e89e-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-115">.NET Core 2.1</span></span> | <span data-ttu-id="2e89e-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-116">.NET Core 3.1</span></span> | <span data-ttu-id="2e89e-117">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-117">.NET 5.0</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="2e89e-118">✔️ [20.10](#2010-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-118">✔️ [20.10](#2010-)</span></span>       | <span data-ttu-id="2e89e-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-119">✔️ 2.1</span></span>        | <span data-ttu-id="2e89e-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-120">✔️ 3.1</span></span>        | <span data-ttu-id="2e89e-121">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-121">✔️ 5.0</span></span> |
| <span data-ttu-id="2e89e-122">✔️ [20.04(LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-122">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="2e89e-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-123">✔️ 2.1</span></span>        | <span data-ttu-id="2e89e-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-124">✔️ 3.1</span></span>        | <span data-ttu-id="2e89e-125">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-125">✔️ 5.0</span></span> |
| <span data-ttu-id="2e89e-126">❌ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-126">❌ [19.10](#1910-)</span></span>       | <span data-ttu-id="2e89e-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-127">✔️ 2.1</span></span>        | <span data-ttu-id="2e89e-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-128">✔️ 3.1</span></span>        | <span data-ttu-id="2e89e-129">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-129">✔️ 5.0</span></span> |
| <span data-ttu-id="2e89e-130">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-130">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="2e89e-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-131">✔️ 2.1</span></span>        | <span data-ttu-id="2e89e-132">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-132">✔️ 3.1</span></span>        | <span data-ttu-id="2e89e-133">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-133">❌ 5.0</span></span> |
| <span data-ttu-id="2e89e-134">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-134">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="2e89e-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-135">✔️ 2.1</span></span>        | <span data-ttu-id="2e89e-136">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-136">❌ 3.1</span></span>        | <span data-ttu-id="2e89e-137">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-137">❌ 5.0</span></span> |
| <span data-ttu-id="2e89e-138">✔️ [18.04(LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-138">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="2e89e-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-139">✔️ 2.1</span></span>        | <span data-ttu-id="2e89e-140">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-140">✔️ 3.1</span></span>        | <span data-ttu-id="2e89e-141">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-141">✔️ 5.0</span></span> |
| <span data-ttu-id="2e89e-142">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-142">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="2e89e-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-143">✔️ 2.1</span></span>        | <span data-ttu-id="2e89e-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-144">❌ 3.1</span></span>        | <span data-ttu-id="2e89e-145">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-145">❌ 5.0</span></span> |
| <span data-ttu-id="2e89e-146">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-146">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="2e89e-147">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-147">✔️ 2.1</span></span>        | <span data-ttu-id="2e89e-148">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-148">❌ 3.1</span></span>        | <span data-ttu-id="2e89e-149">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-149">❌ 5.0</span></span> |
| <span data-ttu-id="2e89e-150">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-150">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="2e89e-151">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-151">❌ 2.1</span></span>        | <span data-ttu-id="2e89e-152">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-152">❌ 3.1</span></span>        | <span data-ttu-id="2e89e-153">❌ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-153">❌ 5.0</span></span> |
| <span data-ttu-id="2e89e-154">✔️ [16.04(LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="2e89e-154">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="2e89e-155">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-155">✔️ 2.1</span></span>        | <span data-ttu-id="2e89e-156">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="2e89e-156">✔️ 3.1</span></span>        | <span data-ttu-id="2e89e-157">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-157">✔️ 5.0</span></span> |

<span data-ttu-id="2e89e-158">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-158">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="2e89e-159">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-159">The downloads for these still remain published:</span></span>

- <span data-ttu-id="2e89e-160">3.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-160">3.0</span></span>
- <span data-ttu-id="2e89e-161">2.2</span><span class="sxs-lookup"><span data-stu-id="2e89e-161">2.2</span></span>
- <span data-ttu-id="2e89e-162">2.0</span><span class="sxs-lookup"><span data-stu-id="2e89e-162">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="2e89e-163">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="2e89e-163">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2010-"></a><span data-ttu-id="2e89e-164">20.10 ✔️</span><span class="sxs-lookup"><span data-stu-id="2e89e-164">20.10 ✔️</span></span>

<span data-ttu-id="2e89e-165">Ubuntu 20.10용 .NET 5 및 .NET Core 3.1 패키지 피드에는 현재 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-165">.NET 5 and .NET Core 3.1 package feeds for Ubuntu 20.10 currently have an issue.</span></span> <span data-ttu-id="2e89e-166">문제에 대한 자세한 내용은 [GitHub issue dotnet/core#5549](https://github.com/dotnet/core/issues/5549)(GitHub 문제 dotnet/core#5549)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e89e-166">For more information about the issue, see [GitHub issue dotnet/core#5549](https://github.com/dotnet/core/issues/5549).</span></span> <span data-ttu-id="2e89e-167">이 문서는 문제가 해결될 때 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-167">This article will be updated when the issue is resolved.</span></span>

<span data-ttu-id="2e89e-168">Ubuntu 20.10에 .NET 5 또는 .NET Core 3.1을 설치하려면 [20.04](#2004-)에 대한 지침을 따르세요.</span><span class="sxs-lookup"><span data-stu-id="2e89e-168">To install .NET 5 or .NET Core 3.1 on Ubuntu 20.10, follow the instructions for [20.04](#2004-).</span></span>

## <a name="2004-"></a><span data-ttu-id="2e89e-169">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="2e89e-169">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1910-"></a><span data-ttu-id="2e89e-170">19.10 ❌</span><span class="sxs-lookup"><span data-stu-id="2e89e-170">19.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="2e89e-171">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="2e89e-171">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="2e89e-172">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="2e89e-172">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="2e89e-173">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="2e89e-173">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="1710-"></a><span data-ttu-id="2e89e-174">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="2e89e-174">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="2e89e-175">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="2e89e-175">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="2e89e-176">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="2e89e-176">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="2e89e-177">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="2e89e-177">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-50](includes/linux-install-50-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="2e89e-178">APT 업데이트 SDK 또는 런타임</span><span class="sxs-lookup"><span data-stu-id="2e89e-178">APT update SDK or runtime</span></span>

<span data-ttu-id="2e89e-179">.NET에 대한 새로운 패치 릴리스가 출시되면 다음 명령을 사용하여 APT를 통해 간단하게 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-179">When a new patch release is available for .NET, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="2e89e-180">APT 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2e89e-180">APT troubleshooting</span></span>

<span data-ttu-id="2e89e-181">이 섹션에서는 APT를 사용하여 .NET을 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-181">This section provides information on common errors you may get while using APT to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="2e89e-182">패키지를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="2e89e-182">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="unable-to-locate--some-packages-could-not-be-installed"></a><span data-ttu-id="2e89e-183">찾을 수 없음 \\ 일부 패키지를 설치할 수 없음</span><span class="sxs-lookup"><span data-stu-id="2e89e-183">Unable to locate \\ Some packages could not be installed</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="2e89e-184">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="2e89e-184">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="2e89e-185">Snap</span><span class="sxs-lookup"><span data-stu-id="2e89e-185">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="2e89e-186">종속성</span><span class="sxs-lookup"><span data-stu-id="2e89e-186">Dependencies</span></span>

<span data-ttu-id="2e89e-187">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-187">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="2e89e-188">그러나 .NET을 수동으로 설치하거나 자체 포함 앱을 게시할 경우 이러한 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-188">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="2e89e-189">libc6</span><span class="sxs-lookup"><span data-stu-id="2e89e-189">libc6</span></span>
- <span data-ttu-id="2e89e-190">libgcc1</span><span class="sxs-lookup"><span data-stu-id="2e89e-190">libgcc1</span></span>
- <span data-ttu-id="2e89e-191">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="2e89e-191">libgssapi-krb5-2</span></span>
- <span data-ttu-id="2e89e-192">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="2e89e-192">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="2e89e-193">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="2e89e-193">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="2e89e-194">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="2e89e-194">libicu60 (for 18.x)</span></span>
- <span data-ttu-id="2e89e-195">libicu66(20.x용)</span><span class="sxs-lookup"><span data-stu-id="2e89e-195">libicu66 (for 20.x)</span></span>
- <span data-ttu-id="2e89e-196">libssl1.0.0(14.x용, 16.x용)</span><span class="sxs-lookup"><span data-stu-id="2e89e-196">libssl1.0.0 (for 14.x, 16.x)</span></span>
- <span data-ttu-id="2e89e-197">libssl1.1(18.x용, 20.x용)</span><span class="sxs-lookup"><span data-stu-id="2e89e-197">libssl1.1 (for 18.x, 20.x)</span></span>
- <span data-ttu-id="2e89e-198">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="2e89e-198">libstdc++6</span></span>
- <span data-ttu-id="2e89e-199">zlib1g</span><span class="sxs-lookup"><span data-stu-id="2e89e-199">zlib1g</span></span>

<span data-ttu-id="2e89e-200">*System.Drawing.Common* 어셈블리를 사용하는 .NET 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-200">For .NET apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="2e89e-201">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="2e89e-201">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="2e89e-202">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus* 를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2e89e-202">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="2e89e-203">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2e89e-203">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="2e89e-204">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="2e89e-204">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="2e89e-205">수동 설치</span><span class="sxs-lookup"><span data-stu-id="2e89e-205">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="2e89e-206">다음 단계</span><span class="sxs-lookup"><span data-stu-id="2e89e-206">Next steps</span></span>

- [<span data-ttu-id="2e89e-207">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="2e89e-207">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
