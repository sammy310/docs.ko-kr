---
title: OpenSUSE에 .NET 설치 - .NET
description: openSUSE에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 7a519f19f708e1f12af1e9715bad4f38a607f9c3
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970813"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-opensuse"></a><span data-ttu-id="5b316-103">openSUSE에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="5b316-103">Install the .NET SDK or the .NET Runtime on openSUSE</span></span>

<span data-ttu-id="5b316-104">.NET은 openSUSE에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-104">.NET is supported on openSUSE.</span></span> <span data-ttu-id="5b316-105">이 문서에서는 openSUSE에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-105">This article describes how to install .NET on openSUSE.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

## <a name="supported-distributions"></a><span data-ttu-id="5b316-106">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="5b316-106">Supported distributions</span></span>

<span data-ttu-id="5b316-107">다음 표는 openSUSE 15에서 현재 지원되는 .NET 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-107">The following table is a list of currently supported .NET releases on openSUSE 15.</span></span> <span data-ttu-id="5b316-108">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 openSUSE 버전이 더 이상 지원되지 않을 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of openSUSE is no longer supported.</span></span>

- <span data-ttu-id="5b316-109">✔️는 openSUSE 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-109">A ✔️ indicates that the version of openSUSE or .NET is still supported.</span></span>
- <span data-ttu-id="5b316-110">❌는 openSUSE 또는 .NET 버전이 해당 openSUSE 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-110">A ❌ indicates that the version of openSUSE or .NET isn't supported on that openSUSE release.</span></span>
- <span data-ttu-id="5b316-111">openSUSE 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-111">When both a version of openSUSE and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="5b316-112">openSUSE</span><span class="sxs-lookup"><span data-stu-id="5b316-112">openSUSE</span></span>                   | <span data-ttu-id="5b316-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="5b316-113">.NET Core 2.1</span></span> | <span data-ttu-id="5b316-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="5b316-114">.NET Core 3.1</span></span> | <span data-ttu-id="5b316-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="5b316-115">.NET 5.0</span></span> |
|----------------------------|---------------|---------------|----------------|
| <span data-ttu-id="5b316-116">✔️ [15](#opensuse-15-)</span><span class="sxs-lookup"><span data-stu-id="5b316-116">✔️ [15](#opensuse-15-)</span></span>     | <span data-ttu-id="5b316-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="5b316-117">✔️ 2.1</span></span>        | <span data-ttu-id="5b316-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="5b316-118">✔️ 3.1</span></span>        | <span data-ttu-id="5b316-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="5b316-119">✔️ 5.0</span></span> |

<span data-ttu-id="5b316-120">다음 .NET 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-120">The following versions of .NET are no longer supported.</span></span> <span data-ttu-id="5b316-121">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-121">The downloads for these still remain published:</span></span>

- <span data-ttu-id="5b316-122">3.0</span><span class="sxs-lookup"><span data-stu-id="5b316-122">3.0</span></span>
- <span data-ttu-id="5b316-123">2.2</span><span class="sxs-lookup"><span data-stu-id="5b316-123">2.2</span></span>
- <span data-ttu-id="5b316-124">2.0</span><span class="sxs-lookup"><span data-stu-id="5b316-124">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="5b316-125">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="5b316-125">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="opensuse-15-"></a><span data-ttu-id="5b316-126">openSUSE 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="5b316-126">openSUSE 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo zypper install libicu
sudo rpm --import https://packages.microsoft.com/keys/microsoft.asc
wget https://packages.microsoft.com/config/opensuse/15/prod.repo
sudo mv prod.repo /etc/zypp/repos.d/microsoft-prod.repo
sudo chown root:root /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="5b316-127">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="5b316-127">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="5b316-128">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5b316-128">Troubleshoot the package manager</span></span>

<span data-ttu-id="5b316-129">이 섹션에서는 패키지 관리자를 사용하여 .NET을 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-129">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="unable-to-find-package"></a><span data-ttu-id="5b316-130">패키지를 찾을 수 없음</span><span class="sxs-lookup"><span data-stu-id="5b316-130">Unable to find package</span></span>

[!INCLUDE [linux-install-package-manager-x64-vs-arm](includes/linux-install-package-manager-x64-vs-arm.md)]

### <a name="failed-to-fetch"></a><span data-ttu-id="5b316-131">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="5b316-131">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="5b316-132">종속성</span><span class="sxs-lookup"><span data-stu-id="5b316-132">Dependencies</span></span>

<span data-ttu-id="5b316-133">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-133">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="5b316-134">그러나 .NET을 수동으로 설치하거나 자체 포함 앱을 게시할 경우 이러한 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-134">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="5b316-135">krb5</span><span class="sxs-lookup"><span data-stu-id="5b316-135">krb5</span></span>
- <span data-ttu-id="5b316-136">libicu</span><span class="sxs-lookup"><span data-stu-id="5b316-136">libicu</span></span>
- <span data-ttu-id="5b316-137">libopenssl1_0_0</span><span class="sxs-lookup"><span data-stu-id="5b316-137">libopenssl1_0_0</span></span>

<span data-ttu-id="5b316-138">대상 런타임 환경의 OpenSSL 버전이 1.1 이상인 경우, **compat-openssl10** 을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-138">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="5b316-139">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b316-139">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="5b316-140">*System.Drawing.Common* 어셈블리를 사용하는 .NET 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-140">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="5b316-141">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="5b316-141">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="5b316-142">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus* 를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b316-142">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="5b316-143">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b316-143">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="5b316-144">다음 단계</span><span class="sxs-lookup"><span data-stu-id="5b316-144">Next steps</span></span>

- [<span data-ttu-id="5b316-145">.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="5b316-145">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="5b316-146">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="5b316-146">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
