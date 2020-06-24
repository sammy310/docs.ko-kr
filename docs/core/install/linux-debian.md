---
title: Debian에 .NET Core 설치 - .NET Core
description: Debian에 .NET Core SDK와 .NET Core 런타임을 설치하는 다양한 방법을 보여줍니다.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: c66d8e1daad4e59a766781b7117600352879b724
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602809"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-debian"></a><span data-ttu-id="9fd5a-103">Debian에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="9fd5a-103">Install .NET Core SDK or .NET Core Runtime on Debian</span></span>

<span data-ttu-id="9fd5a-104">이 문서에서는 Debian에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-104">This article describes how to install .NET Core on Debian.</span></span> <span data-ttu-id="9fd5a-105">Debian 버전의 지원이 종료되면 해당 버전에서는 .NET Core도 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-105">When a Debian version falls out of support, .NET Core is no longer supported with that version.</span></span> <span data-ttu-id="9fd5a-106">그러나, 이러한 지침은 지원되지 않는 버전에서 .NET Core를 실행하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-106">However, these instructions may help you to get .NET Core running on those versions, even though it isn't supported.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="9fd5a-107">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="9fd5a-107">Supported distributions</span></span>

<span data-ttu-id="9fd5a-108">다음 표는 현재 지원되는 .NET Core 릴리스와 지원되는 Debian 버전의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-108">The following table is a list of currently supported .NET Core releases and the versions of Debian they're supported on.</span></span> <span data-ttu-id="9fd5a-109">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 [Debian 버전이 지원 종료에 도달](https://wiki.debian.org/DebianReleases)할 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-109">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of [Debian reaches end-of-life](https://wiki.debian.org/DebianReleases).</span></span>

- <span data-ttu-id="9fd5a-110">✔️는 Debian 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-110">A ✔️ indicates that the version of Debian or .NET Core is still supported.</span></span>
- <span data-ttu-id="9fd5a-111">❌는 Debian 또는 .NET Core 버전이 해당 Debian 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-111">A ❌ indicates that the version of Debian or .NET Core isn't supported on that Debian release.</span></span>
- <span data-ttu-id="9fd5a-112">Debian 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-112">When both a version of Debian and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="9fd5a-113">Debian</span><span class="sxs-lookup"><span data-stu-id="9fd5a-113">Debian</span></span>                   | <span data-ttu-id="9fd5a-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="9fd5a-114">.NET Core 2.1</span></span> | <span data-ttu-id="9fd5a-115">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="9fd5a-115">.NET Core 3.1</span></span> | <span data-ttu-id="9fd5a-116">.NET 5 미리 보기(수동 설치만 해당)</span><span class="sxs-lookup"><span data-stu-id="9fd5a-116">.NET 5 Preview (manual install only)</span></span> |
|--------------------------|---------------|---------------|----------------|
| <span data-ttu-id="9fd5a-117">✔️ [10](#debian-10-)</span><span class="sxs-lookup"><span data-stu-id="9fd5a-117">✔️ [10](#debian-10-)</span></span>     | <span data-ttu-id="9fd5a-118">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="9fd5a-118">✔️ 2.1</span></span>        | <span data-ttu-id="9fd5a-119">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="9fd5a-119">✔️ 3.1</span></span>        | <span data-ttu-id="9fd5a-120">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="9fd5a-120">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="9fd5a-121">✔️ [9](#debian-9-)</span><span class="sxs-lookup"><span data-stu-id="9fd5a-121">✔️ [9](#debian-9-)</span></span>       | <span data-ttu-id="9fd5a-122">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="9fd5a-122">✔️ 2.1</span></span>        | <span data-ttu-id="9fd5a-123">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="9fd5a-123">✔️ 3.1</span></span>        | <span data-ttu-id="9fd5a-124">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="9fd5a-124">✔️ 5.0 Preview</span></span> |
| <span data-ttu-id="9fd5a-125">❌ [8](#debian-8-)</span><span class="sxs-lookup"><span data-stu-id="9fd5a-125">❌ [8](#debian-8-)</span></span>       | <span data-ttu-id="9fd5a-126">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="9fd5a-126">✔️ 2.1</span></span>        | <span data-ttu-id="9fd5a-127">❌ 3.1</span><span class="sxs-lookup"><span data-stu-id="9fd5a-127">❌ 3.1</span></span>        | <span data-ttu-id="9fd5a-128">❌ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="9fd5a-128">❌ 5.0 Preview</span></span> |

<span data-ttu-id="9fd5a-129">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-129">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="9fd5a-130">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-130">The downloads for these still remain published:</span></span>

- <span data-ttu-id="9fd5a-131">3.0</span><span class="sxs-lookup"><span data-stu-id="9fd5a-131">3.0</span></span>
- <span data-ttu-id="9fd5a-132">2.2</span><span class="sxs-lookup"><span data-stu-id="9fd5a-132">2.2</span></span>
- <span data-ttu-id="9fd5a-133">2.0</span><span class="sxs-lookup"><span data-stu-id="9fd5a-133">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="9fd5a-134">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="9fd5a-134">How to install other versions</span></span>

[!INCLUDE [hack-pkgname](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="debian-10-"></a><span data-ttu-id="9fd5a-135">Debian 10 ✔️</span><span class="sxs-lookup"><span data-stu-id="9fd5a-135">Debian 10 ✔️</span></span>

[!INCLUDE [linux-prep-intro-apt](includes/linux-prep-intro-apt.md)]

```bash
wget https://packages.microsoft.com/config/debian/10/packages-microsoft-prod.deb -O packages-microsoft-prod.deb
dpkg -i packages-microsoft-prod.deb
```

[!INCLUDE [linux-apt-install-31](includes/linux-install-31-apt.md)]

## <a name="debian-9-"></a><span data-ttu-id="9fd5a-136">Debian 9 ✔️</span><span class="sxs-lookup"><span data-stu-id="9fd5a-136">Debian 9 ✔️</span></span>

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

## <a name="debian-8-"></a><span data-ttu-id="9fd5a-137">Debian 8 ❌</span><span class="sxs-lookup"><span data-stu-id="9fd5a-137">Debian 8 ❌</span></span>

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

## <a name="apt-update-sdk-or-runtime"></a><span data-ttu-id="9fd5a-138">APT 업데이트 SDK 또는 런타임</span><span class="sxs-lookup"><span data-stu-id="9fd5a-138">APT update SDK or runtime</span></span>

<span data-ttu-id="9fd5a-139">.NET Core에 대한 새로운 패치 릴리스가 출시될 경우 다음 명령을 사용하면 APT를 통해 간단하게 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-139">When a new patch release is available for .NET Core, you can simply upgrade it through APT with the following commands:</span></span>

```bash
sudo apt-get update
sudo apt-get upgrade
```

## <a name="apt-troubleshooting"></a><span data-ttu-id="9fd5a-140">APT 문제 해결</span><span class="sxs-lookup"><span data-stu-id="9fd5a-140">APT troubleshooting</span></span>

<span data-ttu-id="9fd5a-141">이 섹션에서는 APT를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9fd5a-141">This section provides information on common errors you may get while using APT to install .NET Core.</span></span>

### <a name="unable-to-locate"></a><span data-ttu-id="9fd5a-142">찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="9fd5a-142">Unable to locate</span></span>

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

### <a name="failed-to-fetch"></a><span data-ttu-id="9fd5a-143">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="9fd5a-143">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-deb](includes/package-manager-failed-to-fetch-deb.md)]

## <a name="snap"></a><span data-ttu-id="9fd5a-144">Snap</span><span class="sxs-lookup"><span data-stu-id="9fd5a-144">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="9fd5a-145">종속성</span><span class="sxs-lookup"><span data-stu-id="9fd5a-145">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="9fd5a-146">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="9fd5a-146">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="9fd5a-147">수동 설치</span><span class="sxs-lookup"><span data-stu-id="9fd5a-147">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="9fd5a-148">다음 단계</span><span class="sxs-lookup"><span data-stu-id="9fd5a-148">Next steps</span></span>

- <span data-ttu-id="9fd5a-149">[자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="9fd5a-149">[Tutorial: Create a console application with .NET Core SDK using Visual Studio Code](../tutorials/with-visual-studio-code.md)</span></span>
