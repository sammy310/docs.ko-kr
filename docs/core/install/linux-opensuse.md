---
title: OpenSUSE에 .NET 설치 - .NET
description: openSUSE에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 11/10/2020
ms.openlocfilehash: eb31e3109ccd40999c22a27607d48544bf117dc2
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96031867"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-opensuse"></a><span data-ttu-id="75094-103">openSUSE에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="75094-103">Install the .NET SDK or the .NET Runtime on openSUSE</span></span>

<span data-ttu-id="75094-104">.NET은 openSUSE에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="75094-104">.NET is supported on openSUSE.</span></span> <span data-ttu-id="75094-105">이 문서에서는 openSUSE에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="75094-105">This article describes how to install .NET on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="75094-106">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="75094-106">Supported distributions</span></span>

<span data-ttu-id="75094-107">다음 표는 openSUSE 15에서 현재 지원되는 .NET 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="75094-107">The following table is a list of currently supported .NET releases on openSUSE 15.</span></span> <span data-ttu-id="75094-108">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 openSUSE 버전이 더 이상 지원되지 않을 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="75094-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="75094-109">✔️는 openSUSE 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75094-109">A ✔️ indicates that the version of openSUSE or .NET is still supported.</span></span>
- <span data-ttu-id="75094-110">❌는 openSUSE 또는 .NET 버전이 해당 openSUSE 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="75094-110">A ❌ indicates that the version of openSUSE or .NET isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="75094-111">openSUSE 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="75094-111">When both a version of openSUSE and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="75094-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="75094-112">openSUSE</span></span>                   | <span data-ttu-id="75094-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="75094-113">.NET Core 2.1</span></span> | <span data-ttu-id="75094-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="75094-114">.NET Core 3.1</span></span> | <span data-ttu-id="75094-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="75094-115">.NET 5.0</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="75094-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="75094-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="75094-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="75094-117">✔️ 2.1</span></span>        | <span data-ttu-id="75094-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="75094-118">✔️ 3.1</span></span>        | <span data-ttu-id="75094-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="75094-119">✔️ 5.0</span></span> |

<span data-ttu-id="75094-120">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="75094-120">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="75094-121">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="75094-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="75094-122">3.0</span><span class="sxs-lookup"><span data-stu-id="75094-122">3.0</span></span>
- <span data-ttu-id="75094-123">2.2</span><span class="sxs-lookup"><span data-stu-id="75094-123">2.2</span></span>
- <span data-ttu-id="75094-124">2.0</span><span class="sxs-lookup"><span data-stu-id="75094-124">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="75094-125">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="75094-125">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="75094-126">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="75094-126">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="75094-127">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="75094-127">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="75094-128">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="75094-128">Troubleshoot the package manager</span></span>

<span data-ttu-id="75094-129">이 섹션에서는 패키지 관리자를 사용하여 .NET을 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="75094-129">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="75094-130">패키지를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="75094-130">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="75094-131">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="75094-131">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="snap"></a><span data-ttu-id="75094-132">Snap</span><span class="sxs-lookup"><span data-stu-id="75094-132">Snap</span></span>

[!INCLUDE [linux-install-snap](includes/linux-install-snap.md)]

## <a name="dependencies"></a><span data-ttu-id="75094-133">종속성</span><span class="sxs-lookup"><span data-stu-id="75094-133">Dependencies</span></span>

<span data-ttu-id="75094-134">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="75094-134">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="75094-135">그러나 .NET을 수동으로 설치하거나 자체 포함 앱을 게시할 경우 이러한 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75094-135">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="75094-136">krb5</span><span class="sxs-lookup"><span data-stu-id="75094-136">krb5</span></span>
- <span data-ttu-id="75094-137">libicu</span><span class="sxs-lookup"><span data-stu-id="75094-137">libicu</span></span>
- <span data-ttu-id="75094-138">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="75094-138">libopenssl1_0_0</span></span>

<span data-ttu-id="75094-139">대상 런타임 환경의 OpenSSL 버전이 1.1 이상인 경우, **compat-openssl10** 을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="75094-139">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="75094-140">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75094-140">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="75094-141">*System.Drawing.Common* 어셈블리를 사용하는 .NET 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="75094-141">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="75094-142">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="75094-142">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="75094-143">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus* 를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="75094-143">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="75094-144">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="75094-144">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="75094-145">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="75094-145">Scripted install</span></span>

[!INCLUDE [linux-install-scripted](includes/linux-install-scripted.md)]

## <a name="manual-install"></a><span data-ttu-id="75094-146">수동 설치</span><span class="sxs-lookup"><span data-stu-id="75094-146">Manual install</span></span>

[!INCLUDE [linux-install-manual](includes/linux-install-manual.md)]

## <a name="next-steps"></a><span data-ttu-id="75094-147">다음 단계</span><span class="sxs-lookup"><span data-stu-id="75094-147">Next steps</span></span>

- [<span data-ttu-id="75094-148">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="75094-148">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
