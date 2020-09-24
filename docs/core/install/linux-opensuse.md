---
title: openSUSE에 .NET Core 설치 - .NET Core
description: openSUSE에 .NET Core SDK와 .NET Core 런타임을 설치하는 다양한 방법을 보여줍니다.
author: adegeo
ms.author: adegeo
ms.date: 06/04/2020
ms.openlocfilehash: ccdb23ca1838d2c15c9a95b45c8505efe7a6df0e
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90539232"
---
# <a name="install-net-core-sdk-or-net-core-runtime-on-opensuse"></a><span data-ttu-id="c788a-103">openSUSE에 .NET Core SDK 또는 .NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="c788a-103">Install .NET Core SDK or .NET Core Runtime on openSUSE</span></span>

<span data-ttu-id="c788a-104">.NET Core는 openSUSE에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-104">.NET Core is supported on openSUSE.</span></span> <span data-ttu-id="c788a-105">이 문서에서는 openSUSE에 .NET Core를 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-105">This article describes how to install .NET Core on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="c788a-106">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="c788a-106">Supported distributions</span></span>

<span data-ttu-id="c788a-107">다음 표는 openSUSE 15에서 현재 지원되는 .NET Core 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-107">The following table is a list of currently supported .NET Core releases on openSUSE 15.</span></span> <span data-ttu-id="c788a-108">이러한 버전은 각 버전의 [.NET Core가 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 openSUSE 버전이 더 이상 지원되지 않을 때까지 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-108">These versions remain supported until either the version of [.NET Core reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="c788a-109">✔️는 openSUSE 또는 .NET Core 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-109">A ✔️ indicates that the version of openSUSE or .NET Core is still supported.</span></span>
- <span data-ttu-id="c788a-110">❌는 openSUSE 또는 .NET Core 버전이 해당 openSUSE 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-110">A ❌ indicates that the version of openSUSE or .NET Core isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="c788a-111">openSUSE 버전과 .NET Core 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-111">When both a version of openSUSE and a version of .NET Core have ✔️, that OS and .NET combination are supported.</span></span>

| <span data-ttu-id="c788a-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="c788a-112">openSUSE</span></span>                   | <span data-ttu-id="c788a-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="c788a-113">.NET Core 2.1</span></span> | <span data-ttu-id="c788a-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="c788a-114">.NET Core 3.1</span></span> | <span data-ttu-id="c788a-115">.NET 5 미리 보기(수동 설치만 해당)</span><span class="sxs-lookup"><span data-stu-id="c788a-115">.NET 5 Preview (manual install only)</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="c788a-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="c788a-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="c788a-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="c788a-117">✔️ 2.1</span></span>        | <span data-ttu-id="c788a-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="c788a-118">✔️ 3.1</span></span>        | <span data-ttu-id="c788a-119">✔️ 5.0 미리 보기</span><span class="sxs-lookup"><span data-stu-id="c788a-119">✔️ 5.0 Preview</span></span> |

<span data-ttu-id="c788a-120">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-120">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="c788a-121">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="c788a-122">3.0</span><span class="sxs-lookup"><span data-stu-id="c788a-122">3.0</span></span>
- <span data-ttu-id="c788a-123">2.2</span><span class="sxs-lookup"><span data-stu-id="c788a-123">2.2</span></span>
- <span data-ttu-id="c788a-124">2.0</span><span class="sxs-lookup"><span data-stu-id="c788a-124">2.0</span></span>

## <a name="how-to-install-other-versions"></a><span data-ttu-id="c788a-125">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="c788a-125">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="c788a-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="c788a-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-31](includes/linux-install-31-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="c788a-127">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c788a-127">Troubleshoot the package manager</span></span>

<span data-ttu-id="c788a-128">이 섹션에서는 패키지 관리자를 사용하여 .NET Core를 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-128">This section provides information on common errors you may get while using the package manager to install .NET Core.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="c788a-129">패키지를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="c788a-129">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="c788a-130">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="c788a-130">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="c788a-131">Snap</span><span class="sxs-lookup"><span data-stu-id="c788a-131">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="c788a-132">종속성</span><span class="sxs-lookup"><span data-stu-id="c788a-132">Dependencies</span></span>

<span data-ttu-id="c788a-133">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-133">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="c788a-134">그러나, .NET Core를 수동으로 설치하거나 자체 포함된 앱을 게시할 경우 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-134">But, if you manually install .NET Core or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="c788a-135">krb5</span><span class="sxs-lookup"><span data-stu-id="c788a-135">krb5</span></span>
- <span data-ttu-id="c788a-136">libicu</span><span class="sxs-lookup"><span data-stu-id="c788a-136">libicu</span></span>
- <span data-ttu-id="c788a-137">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="c788a-137">libopenssl1_0_0</span></span>

<span data-ttu-id="c788a-138">대상 런타임 환경의 OpenSSL 버전이 1.1 이상인 경우, **compat-openssl10**을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-138">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="c788a-139">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c788a-139">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="c788a-140">*System.Drawing.Common* 어셈블리를 사용하는 .NET Core 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-140">For .NET Core apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="c788a-141">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="c788a-141">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="c788a-142">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus*를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c788a-142">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="c788a-143">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c788a-143">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="c788a-144">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="c788a-144">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="c788a-145">수동 설치</span><span class="sxs-lookup"><span data-stu-id="c788a-145">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="c788a-146">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c788a-146">Next steps</span></span>

- <span data-ttu-id="c788a-147">[자습서: Visual Studio Code](../tutorials/with-visual-studio-code.md)를 사용하는 .NET Core SDK로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="c788a-147">[Tutorial: Create a console application with .NET Core SDK using Visual Studio Code](../tutorials/with-visual-studio-code.md)</span></span>
