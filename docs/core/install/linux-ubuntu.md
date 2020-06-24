---
title: Ubuntu에 .NET Core 설치 - .NET Core
description: Ubuntu에 .NET Core SDK와 .NET Core 런타임을 설치하는 다양한 방법을 보여줍니다.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 7045d4d1c3585ba6d26c55ded4653775c9413841
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602725"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-ubuntu"></a><span data-ttu-id="57299-103">Ubuntu에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="57299-103">Install .NET Core SDK or .NET Core Runtime on Ubuntu</span></span>

<span data-ttu-id="57299-104">.NET Core는 Ubuntu에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="57299-104">.NET Core is supported on Ubuntu.</span></span> <span data-ttu-id="57299-105">이 문서에서는 Ubuntu에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="57299-105">This article describes how to install .NET Core on Ubuntu.</span></span> <span data-ttu-id="57299-106">Ubuntu 버전의 지원이 종료되면 해당 버전에서는 .NET Core도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57299-106">When an Ubuntu version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="57299-107">그러나, 이러한 지침은 지원되지 않는 버전에서 .NET Core를 실행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57299-107">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="57299-108">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="57299-108">Supported distributions</span></span>

<span data-ttu-id="57299-109">다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 Ubuntu 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="57299-109">The following table is a list of currently supported .NET Core releases and the versions of Ubuntu they're supported on.</span></span> <span data-ttu-id="57299-110">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Ubuntu 버전이 지원 종료에 도달](https://wiki.ubuntu.com/Releases)할 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="57299-110">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Ubuntu reaches end-of-life](https://wiki.ubuntu.com/Releases).</span></span>

- <span data-ttu-id="57299-111">✔️는 Ubuntu 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="57299-111">A ✔️ indicates that the version of Ubuntu or .NET Core is still supported.</span></span>
- <span data-ttu-id="57299-112">❌는 Ubuntu 또는 .NET Core 버전이 해당 Ubuntu 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="57299-112">A ❌ indicates that the version of Ubuntu or .NET Core isn't supported on that Ubuntu release.</span></span>
- <span data-ttu-id="57299-113">Ubuntu 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="57299-113">When both a version of Ubuntu and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="57299-114">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="57299-114">Ubuntu</span></span>                   | <span data-ttu-id="57299-115">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-115">.NET Core 2.1</span></span> | <span data-ttu-id="57299-116">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-116">.NET Core 3.1</span></span> | <span data-ttu-id="57299-117">.NET 5 미리 보기(수동 설치만 해당)</span><span class="sxs-lookup"><span data-stu-id="57299-117">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="57299-118">✔️ [20.04(LTS)](#2004-)</span><span class="sxs-lookup"><span data-stu-id="57299-118">✔️ [20.04 (LTS)](#2004-)</span></span> | <span data-ttu-id="57299-119">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-119">✔️ 2.1</span></span>        | <span data-ttu-id="57299-120">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-120">✔️ 3.1</span></span>        | <span data-ttu-id="57299-121">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="57299-121">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="57299-122">✔️ [19.10](#1910-)</span><span class="sxs-lookup"><span data-stu-id="57299-122">✔️ [19.10](#1910-)</span></span>       | <span data-ttu-id="57299-123">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-123">✔️ 2.1</span></span>        | <span data-ttu-id="57299-124">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-124">✔️ 3.1</span></span>        | <span data-ttu-id="57299-125">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="57299-125">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="57299-126">❌ [19.04](#1904-)</span><span class="sxs-lookup"><span data-stu-id="57299-126">❌ [19.04](#1904-)</span></span>       | <span data-ttu-id="57299-127">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-127">✔️ 2.1</span></span>        | <span data-ttu-id="57299-128">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-128">✔️ 3.1</span></span>        | <span data-ttu-id="57299-129">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="57299-129">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="57299-130">❌ [18.10](#1810-)</span><span class="sxs-lookup"><span data-stu-id="57299-130">❌ [18.10](#1810-)</span></span>       | <span data-ttu-id="57299-131">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-131">✔️ 2.1</span></span>        | <span data-ttu-id="57299-132">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-132">❌ 3.1</span></span>        | <span data-ttu-id="57299-133">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="57299-133">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="57299-134">✔️ [18.04(LTS)](#1804-)</span><span class="sxs-lookup"><span data-stu-id="57299-134">✔️ [18.04 (LTS)](#1804-)</span></span> | <span data-ttu-id="57299-135">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-135">✔️ 2.1</span></span>        | <span data-ttu-id="57299-136">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-136">✔️ 3.1</span></span>        | <span data-ttu-id="57299-137">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="57299-137">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="57299-138">❌ [17.10](#1710-)</span><span class="sxs-lookup"><span data-stu-id="57299-138">❌ [17.10](#1710-)</span></span>       | <span data-ttu-id="57299-139">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-139">✔️ 2.1</span></span>        | <span data-ttu-id="57299-140">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-140">❌ 3.1</span></span>        | <span data-ttu-id="57299-141">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="57299-141">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="57299-142">❌ [17.04](#1704-)</span><span class="sxs-lookup"><span data-stu-id="57299-142">❌ [17.04](#1704-)</span></span>       | <span data-ttu-id="57299-143">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-143">✔️ 2.1</span></span>        | <span data-ttu-id="57299-144">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-144">❌ 3.1</span></span>        | <span data-ttu-id="57299-145">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="57299-145">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="57299-146">❌ [16.10](#1610-)</span><span class="sxs-lookup"><span data-stu-id="57299-146">❌ [16.10](#1610-)</span></span>       | <span data-ttu-id="57299-147">❌ 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-147">❌ 2.1</span></span>        | <span data-ttu-id="57299-148">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-148">❌ 3.1</span></span>        | <span data-ttu-id="57299-149">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="57299-149">❌ 5.0 Preview</span></span> |
| <span data-ttu-id="57299-150">✔️ [16.04(LTS)](#1604-)</span><span class="sxs-lookup"><span data-stu-id="57299-150">✔️ [16.04 (LTS)](#1604-)</span></span> | <span data-ttu-id="57299-151">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="57299-151">✔️ 2.1</span></span>        | <span data-ttu-id="57299-152">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="57299-152">✔️ 3.1</span></span>        | <span data-ttu-id="57299-153">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="57299-153">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="57299-154">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="57299-154">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="57299-155">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="57299-155">The downloads for these still remain published:</span></span>

- <span data-ttu-id="57299-156">3.0</span><span class="sxs-lookup"><span data-stu-id="57299-156">3.0</span></span>
- <span data-ttu-id="57299-157">2.2</span><span class="sxs-lookup"><span data-stu-id="57299-157">2.2</span></span>
- <span data-ttu-id="57299-158">2.0</span><span class="sxs-lookup"><span data-stu-id="57299-158">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="57299-159">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="57299-159">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="2004-"></a><span data-ttu-id="57299-160">20.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="57299-160">20.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1910-"></a><span data-ttu-id="57299-161">19.10 ✔️</span><span class="sxs-lookup"><span data-stu-id="57299-161">19.10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1904-"></a><span data-ttu-id="57299-162">19.04 ❌</span><span class="sxs-lookup"><span data-stu-id="57299-162">19.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/19.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1810-"></a><span data-ttu-id="57299-163">18.10 ❌</span><span class="sxs-lookup"><span data-stu-id="57299-163">18.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1804-"></a><span data-ttu-id="57299-164">18.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="57299-164">18.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/18.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="1710-"></a><span data-ttu-id="57299-165">17.10 ❌</span><span class="sxs-lookup"><span data-stu-id="57299-165">17.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1704-"></a><span data-ttu-id="57299-166">17.04 ❌</span><span class="sxs-lookup"><span data-stu-id="57299-166">17.04 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/17.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1610-"></a><span data-ttu-id="57299-167">16.10 ❌</span><span class="sxs-lookup"><span data-stu-id="57299-167">16.10 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-ubuntu.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="1604-"></a><span data-ttu-id="57299-168">16.04 ✔️</span><span class="sxs-lookup"><span data-stu-id="57299-168">16.04 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/ubuntu/16.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
sudo dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="57299-169">APT 업데이트 SDK 또는 런타임</span><span class="sxs-lookup"><span data-stu-id="57299-169">APT update SDK or runtime</span></span>

<span data-ttu-id="57299-170">.NET Core에 대한 새로운 패치 릴리스가 출시될 경우 다음 명령을 사용하면 APT를 통해 간단하게 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57299-170">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="57299-171">APT 문제 해결</span><span class="sxs-lookup"><span data-stu-id="57299-171">APT troubleshooting</span></span>

<span data-ttu-id="57299-172">이 섹션에서는 APT를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="57299-172">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="57299-173">찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="57299-173">Unable to locate</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="57299-174">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="57299-174">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="57299-175">Snap</span><span class="sxs-lookup"><span data-stu-id="57299-175">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="57299-176">종속성</span><span class="sxs-lookup"><span data-stu-id="57299-176">Dependencies</span></span>

<span data-ttu-id="57299-177">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="57299-177">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="57299-178">그러나, .NET Core를 수동으로 설치하거나 자체 포함된 앱을 게시할 경우 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57299-178">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="57299-179">liblttng-ust0</span><span class="sxs-lookup"><span data-stu-id="57299-179">liblttng-ust0</span></span>
- <span data-ttu-id="57299-180">libcurl3(14.x 및 16.x용)</span><span class="sxs-lookup"><span data-stu-id="57299-180">libcurl3 (for 14.x and 16.x)</span></span>
- <span data-ttu-id="57299-181">libcurl4(18.x용)</span><span class="sxs-lookup"><span data-stu-id="57299-181">libcurl4 (for 18.x)</span></span>
- <span data-ttu-id="57299-182">libssl1.0.0</span><span class="sxs-lookup"><span data-stu-id="57299-182">libssl1.0.0</span></span>
- <span data-ttu-id="57299-183">libkrb5-3</span><span class="sxs-lookup"><span data-stu-id="57299-183">libkrb5-3</span></span>
- <span data-ttu-id="57299-184">zlib1g</span><span class="sxs-lookup"><span data-stu-id="57299-184">zlib1g</span></span>
- <span data-ttu-id="57299-185">libicu52(14.x용)</span><span class="sxs-lookup"><span data-stu-id="57299-185">libicu52 (for 14.x)</span></span>
- <span data-ttu-id="57299-186">libicu55(16.x용)</span><span class="sxs-lookup"><span data-stu-id="57299-186">libicu55 (for 16.x)</span></span>
- <span data-ttu-id="57299-187">libicu57(17.x용)</span><span class="sxs-lookup"><span data-stu-id="57299-187">libicu57 (for 17.x)</span></span>
- <span data-ttu-id="57299-188">libicu60(18.x용)</span><span class="sxs-lookup"><span data-stu-id="57299-188">libicu60 (for 18.x)</span></span>

<span data-ttu-id="57299-189">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="57299-189">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="57299-190">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="57299-190">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="57299-191">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus*를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57299-191">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="57299-192">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="57299-192">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="57299-193">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="57299-193">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="57299-194">수동 설치</span><span class="sxs-lookup"><span data-stu-id="57299-194">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="57299-195">다음 단계</span><span class="sxs-lookup"><span data-stu-id="57299-195">Next steps</span></span>

- <span data-ttu-id="57299-196">[자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="57299-196">[Tutorial: Create a console application with .NET Core SDK using Visual Studio Code](../tutorials/with-visual-studio-code.md)</span></span>
