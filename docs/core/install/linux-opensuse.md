---
title: openSUSE에 .NET Core 설치 - .NET Core
description: openSUSE에 .NET Core SDK와 .NET Core 런타임을 설치하는 다양한 방법을 보여줍니다.
author: thraka
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: a642cee9ae78f81cd671d8745d5ce241be6a3b69
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602803"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="92a86-103">openSUSE에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="92a86-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="92a86-104">.NET Core는 openSUSE에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="92a86-105">이 문서에서는 openSUSE에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="92a86-106">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="92a86-106">Supported distributions</span></span>

<span data-ttu-id="92a86-107">다음 표는 openSUSE 15에서 현재 지원되는 .NET Core 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="92a86-108">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 openSUSE 버전이 더 이상 지원되지 않을 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="92a86-109">✔️는 openSUSE 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="92a86-110">❌는 openSUSE 또는 .NET Core 버전이 해당 openSUSE 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="92a86-111">openSUSE 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="92a86-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="92a86-112">openSUSE</span></span>                   | <span data-ttu-id="92a86-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="92a86-113">.NET Core 2.1</span></span> | <span data-ttu-id="92a86-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="92a86-114">.NET Core 3.1</span></span> | <span data-ttu-id="92a86-115">.NET 5 미리 보기(수동 설치만 해당)</span><span class="sxs-lookup"><span data-stu-id="92a86-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="92a86-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="92a86-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="92a86-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="92a86-117">✔️ 2.1</span></span>        | <span data-ttu-id="92a86-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="92a86-118">✔️ 3.1</span></span>        | <span data-ttu-id="92a86-119">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="92a86-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="92a86-120">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="92a86-121">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="92a86-122">3.0</span><span class="sxs-lookup"><span data-stu-id="92a86-122">3.0</span></span>
- <span data-ttu-id="92a86-123">2.2</span><span class="sxs-lookup"><span data-stu-id="92a86-123">2.2</span></span>
- <span data-ttu-id="92a86-124">2.0</span><span class="sxs-lookup"><span data-stu-id="92a86-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="92a86-125">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="92a86-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="92a86-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="92a86-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="92a86-127">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="92a86-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="92a86-128">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="92a86-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="92a86-129">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="92a86-129">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="92a86-130">Snap</span><span class="sxs-lookup"><span data-stu-id="92a86-130">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="92a86-131">종속성</span><span class="sxs-lookup"><span data-stu-id="92a86-131">Dependencies</span></span>

[!INCLUDE [linux-install-dependencies](includes/linux-install-dependencies.md)]

## <a name="scripted-install"></a><span data-ttu-id="92a86-132">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="92a86-132">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="92a86-133">수동 설치</span><span class="sxs-lookup"><span data-stu-id="92a86-133">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="92a86-134">다음 단계</span><span class="sxs-lookup"><span data-stu-id="92a86-134">Next steps</span></span>

- <span data-ttu-id="92a86-135">[자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="92a86-135">[Tutorial: Create a console application with .NET Core SDK using Visual Studio Code](../tutorials/with-visual-studio-code.md)</span></span>
