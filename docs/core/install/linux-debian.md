---
title: Debian에 .NET Core 설치 - .NET Core
description: Debian에 .NET Core SDK와 .NET Core 런타임을 설치하는 다양한 방법을 보여줍니다.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: 68a3e848b3d80806e875dfb2fb7e2cbf223f8ad5
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619496"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a><span data-ttu-id="a2a44-103">Debian에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="a2a44-103">Install .NET Core SDK or .NET Core Runtime on Debian</span></span>

<span data-ttu-id="a2a44-104">이 문서에서는 Debian에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-104">This article describes how to install .NET Core on Debian.</span></span> <span data-ttu-id="a2a44-105">Debian 버전의 지원이 종료되면 해당 버전에서는 .NET Core도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-105">When a Debian version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="a2a44-106">그러나, 이러한 지침은 지원되지 않는 버전에서 .NET Core를 실행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="a2a44-107">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="a2a44-107">Supported distributions</span></span>

<span data-ttu-id="a2a44-108">다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 Debian 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-108">The following table is a list of currently supported .NET Core releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="a2a44-109">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Debian 버전이 지원 종료에 도달](https://wiki.debian.org/DebianReleases)할 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-109">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="a2a44-110">✔️는 Debian 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-110">A ✔️ indicates that the version of Debian or .NET Core is still supported.</span></span>
- <span data-ttu-id="a2a44-111">❌는 Debian 또는 .NET Core 버전이 해당 Debian 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-111">A ❌ indicates that the version of Debian or .NET Core isn't supported on that Debian release.</span></span>
- <span data-ttu-id="a2a44-112">Debian 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-112">When both a version of Debian and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="a2a44-113">Debian</span><span class="sxs-lookup"><span data-stu-id="a2a44-113">Debian</span></span>                   | <span data-ttu-id="a2a44-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="a2a44-114">.NET Core 2.1</span></span> | <span data-ttu-id="a2a44-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="a2a44-115">.NET Core 3.1</span></span> | <span data-ttu-id="a2a44-116">.NET 5 미리 보기(수동 설치만 해당)</span><span class="sxs-lookup"><span data-stu-id="a2a44-116">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="a2a44-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="a2a44-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="a2a44-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="a2a44-118">✔️ 2.1</span></span>        | <span data-ttu-id="a2a44-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="a2a44-119">✔️ 3.1</span></span>        | <span data-ttu-id="a2a44-120">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="a2a44-120">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="a2a44-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="a2a44-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="a2a44-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="a2a44-122">✔️ 2.1</span></span>        | <span data-ttu-id="a2a44-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="a2a44-123">✔️ 3.1</span></span>        | <span data-ttu-id="a2a44-124">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="a2a44-124">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="a2a44-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="a2a44-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="a2a44-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="a2a44-126">✔️ 2.1</span></span>        | <span data-ttu-id="a2a44-127">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="a2a44-127">❌ 3.1</span></span>        | <span data-ttu-id="a2a44-128">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="a2a44-128">❌ 5.0 Preview</span></span> |

<span data-ttu-id="a2a44-129">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-129">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="a2a44-130">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="a2a44-131">3.0</span><span class="sxs-lookup"><span data-stu-id="a2a44-131">3.0</span></span>
- <span data-ttu-id="a2a44-132">2.2</span><span class="sxs-lookup"><span data-stu-id="a2a44-132">2.2</span></span>
- <span data-ttu-id="a2a44-133">2.0</span><span class="sxs-lookup"><span data-stu-id="a2a44-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="a2a44-134">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="a2a44-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="a2a44-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="a2a44-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="a2a44-136">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="a2a44-136">Debian 9 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/9/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-8-"></a><span data-ttu-id="a2a44-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="a2a44-137">Debian 8 ❌</span></span>

[!INCLUDE [linux-not-supported](includes/linux-not-supported-debian.md)]

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/8/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
```

[!INCLUDE [linux-apt-install-21](includes/linux-install-21-apt.md)]

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="a2a44-138">APT 업데이트 SDK 또는 런타임</span><span class="sxs-lookup"><span data-stu-id="a2a44-138">APT update SDK or runtime</span></span>

<span data-ttu-id="a2a44-139">.NET Core에 대한 새로운 패치 릴리스가 출시될 경우 다음 명령을 사용하면 APT를 통해 간단하게 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-139">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="a2a44-140">APT 문제 해결</span><span class="sxs-lookup"><span data-stu-id="a2a44-140">APT troubleshooting</span></span>

<span data-ttu-id="a2a44-141">이 섹션에서는 APT를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-141">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="a2a44-142">찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="a2a44-142">Unable to locate</span></span>

[!INCLUDE [package-manager-failed-to-find-deb](includes/package-manager-failed-to-find-deb.md)]

```bash
sudo apt-get install -y gpg
wget -O - https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor -o microsoft.asc.gpg
sudo mv microsoft.asc.gpg /etc/apt/trusted.gpg.d/
wget https://packages.microsoft.com/config/debian/{os-version}/prod.list
sudo mv prod.list /etc/apt/sources.list.d/microsoft-prod.list
sudo chown root:root /etc/apt/trusted.gpg.d/microsoft.asc.gpg
sudo chown root:root /etc/apt/sources.list.d/microsoft-prod.list
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y {dotnet-package}
```

### <a name="failed-to-fetch"></a><span data-ttu-id="a2a44-143">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="a2a44-143">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="a2a44-144">Snap</span><span class="sxs-lookup"><span data-stu-id="a2a44-144">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="a2a44-145">종속성</span><span class="sxs-lookup"><span data-stu-id="a2a44-145">Dependencies</span></span>

<span data-ttu-id="a2a44-146">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-146">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="a2a44-147">그러나, .NET Core를 수동으로 설치하거나 자체 포함된 앱을 게시할 경우 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-147">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="a2a44-148">libc6</span><span class="sxs-lookup"><span data-stu-id="a2a44-148">libc6</span></span>
- <span data-ttu-id="a2a44-149">libgcc1</span><span class="sxs-lookup"><span data-stu-id="a2a44-149">libgcc1</span></span>
- <span data-ttu-id="a2a44-150">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="a2a44-150">libgssapi-krb5-2</span></span>
- <span data-ttu-id="a2a44-151">libicu52(8.x용)</span><span class="sxs-lookup"><span data-stu-id="a2a44-151">libicu52 (for 8.x)</span></span>
- <span data-ttu-id="a2a44-152">libicu57(9.x용)</span><span class="sxs-lookup"><span data-stu-id="a2a44-152">libicu57 (for 9.x)</span></span>
- <span data-ttu-id="a2a44-153">libicu63(10.x용)</span><span class="sxs-lookup"><span data-stu-id="a2a44-153">libicu63 (for 10.x)</span></span>
- <span data-ttu-id="a2a44-154">libicu67(11.x용)</span><span class="sxs-lookup"><span data-stu-id="a2a44-154">libicu67 (for 11.x)</span></span>
- <span data-ttu-id="a2a44-155">libssl1.0.0(8.x용)</span><span class="sxs-lookup"><span data-stu-id="a2a44-155">libssl1.0.0 (for 8.x)</span></span>
- <span data-ttu-id="a2a44-156">libssl1.1(9.x~11.x용)</span><span class="sxs-lookup"><span data-stu-id="a2a44-156">libssl1.1 (for 9.x-11.x)</span></span>
- <span data-ttu-id="a2a44-157">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="a2a44-157">libstdc++6</span></span>
- <span data-ttu-id="a2a44-158">zlib1g</span><span class="sxs-lookup"><span data-stu-id="a2a44-158">zlib1g</span></span>

<span data-ttu-id="a2a44-159">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-159">For .NET Core apps that use the *System.Drawing.Common* assembly, you also need the following dependency:</span></span>

- <span data-ttu-id="a2a44-160">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="a2a44-160">libgdiplus (version 6.0.1 or later)</span></span>

  > [!WARNING]
  > <span data-ttu-id="a2a44-161">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus*를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a2a44-161">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="a2a44-162">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a2a44-162">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="a2a44-163">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="a2a44-163">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="a2a44-164">수동 설치</span><span class="sxs-lookup"><span data-stu-id="a2a44-164">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="a2a44-165">다음 단계</span><span class="sxs-lookup"><span data-stu-id="a2a44-165">Next steps</span></span>

- <span data-ttu-id="a2a44-166">[자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="a2a44-166">[Tutorial: Create a console application with .NET Core SDK using Visual Studio Code](../tutorials/with-visual-studio-code.md)</span></span>
