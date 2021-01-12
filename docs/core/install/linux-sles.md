---
title: SLES에 .NET 설치 - .NET
description: SLES에 .NET SDK 및 .NET 런타임을 설치하는 다양한 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 80da69616dd1507b809ef56d439645d569a6a805
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970787"
---
# <a name="install-the-net-sdk-or-the-net-runtime-on-sles"></a><span data-ttu-id="13846-103">SLES에 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="13846-103">Install the .NET SDK or the .NET Runtime on SLES</span></span>

<span data-ttu-id="13846-104">.NET은 SLES에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="13846-104">.NET is supported on SLES.</span></span> <span data-ttu-id="13846-105">이 문서에서는 SLES에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="13846-105">This article describes how to install .NET on SLES.</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="supported-distributions"></a><span data-ttu-id="13846-106">지원되는 배포</span><span class="sxs-lookup"><span data-stu-id="13846-106">Supported distributions</span></span>

<span data-ttu-id="13846-107">다음 표는 SLES 12 SP2와 SLES 15에서 현재 지원되는 .NET 릴리스의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="13846-107">The following table is a list of currently supported .NET releases on both SLES 12 SP2 and SLES 15.</span></span> <span data-ttu-id="13846-108">이러한 버전은 [.NET 버전이 지원 종료에 도달](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)하거나 SLES 버전이 더 이상 지원되지 않을 때까지 계속 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="13846-108">These versions remain supported until either the version of [.NET reaches end-of-support](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) or the version of SLES is no longer supported.</span></span>

- <span data-ttu-id="13846-109">✔️는 SLES 또는 .NET 버전이 계속 지원됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13846-109">A ✔️ indicates that the version of SLES or .NET is still supported.</span></span>
- <span data-ttu-id="13846-110">❌는 SLES 또는 .NET 버전이 해당 SLES 릴리스에서 지원되지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="13846-110">A ❌ indicates that the version of SLES or .NET isn't supported on that SLES release.</span></span>
- <span data-ttu-id="13846-111">SLES 버전과 .NET 버전 모두에 ✔가 있으면 해당 OS와 .NET 조합은 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="13846-111">When both a version of SLES and a version of .NET have ✔️, that OS and .NET combination is supported.</span></span>

| <span data-ttu-id="13846-112">SLES</span><span class="sxs-lookup"><span data-stu-id="13846-112">SLES</span></span>                   | <span data-ttu-id="13846-113">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="13846-113">.NET Core 2.1</span></span> | <span data-ttu-id="13846-114">.NET Core 3.1</span><span class="sxs-lookup"><span data-stu-id="13846-114">.NET Core 3.1</span></span> | <span data-ttu-id="13846-115">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="13846-115">.NET 5.0</span></span> |
|------------------------|---------------|---------------|----------------|
| <span data-ttu-id="13846-116">✔️ [15](#sles-15-)</span><span class="sxs-lookup"><span data-stu-id="13846-116">✔️ [15](#sles-15-)</span></span>     | <span data-ttu-id="13846-117">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="13846-117">✔️ 2.1</span></span>        | <span data-ttu-id="13846-118">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="13846-118">✔️ 3.1</span></span>        | <span data-ttu-id="13846-119">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="13846-119">✔️ 5.0</span></span> |
| <span data-ttu-id="13846-120">✔️ [12 SP2](#sles-12-)</span><span class="sxs-lookup"><span data-stu-id="13846-120">✔️ [12 SP2](#sles-12-)</span></span> | <span data-ttu-id="13846-121">✔️ 2.1</span><span class="sxs-lookup"><span data-stu-id="13846-121">✔️ 2.1</span></span>        | <span data-ttu-id="13846-122">✔️ 3.1</span><span class="sxs-lookup"><span data-stu-id="13846-122">✔️ 3.1</span></span>        | <span data-ttu-id="13846-123">✔️ 5.0</span><span class="sxs-lookup"><span data-stu-id="13846-123">✔️ 5.0</span></span> |

<span data-ttu-id="13846-124">다음 .NET Core 버전은 더 이상 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13846-124">The following versions of .NET Core are no longer supported.</span></span> <span data-ttu-id="13846-125">이러한 버전의 다운로드는 여전히 게시된 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="13846-125">The downloads for these still remain published:</span></span>

- <span data-ttu-id="13846-126">3.0</span><span class="sxs-lookup"><span data-stu-id="13846-126">3.0</span></span>
- <span data-ttu-id="13846-127">2.2</span><span class="sxs-lookup"><span data-stu-id="13846-127">2.2</span></span>
- <span data-ttu-id="13846-128">2.0</span><span class="sxs-lookup"><span data-stu-id="13846-128">2.0</span></span>

## <a name="remove-preview-versions"></a><span data-ttu-id="13846-129">미리 보기 버전 제거</span><span class="sxs-lookup"><span data-stu-id="13846-129">Remove preview versions</span></span>

[!INCLUDE [package-manager uninstall notice](./includes/linux-uninstall-preview-info.md)]

## <a name="sles-15-"></a><span data-ttu-id="13846-130">SLES 15 ✔️</span><span class="sxs-lookup"><span data-stu-id="13846-130">SLES 15 ✔️</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/15/packages-microsoft-prod.rpm
```

<span data-ttu-id="13846-131">현재 SLES 15 Microsoft 리포지토리 설치 패키지는 *microsoft-prod.repo* 파일을 잘못된 디렉터리에 설치하므로 zypper가 .NET 패키지를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="13846-131">Currently, the SLES 15 Microsoft repository setup package installs the *microsoft-prod.repo* file to the wrong directory, preventing zypper from finding the .NET packages.</span></span> <span data-ttu-id="13846-132">이 문제를 해결하려면 올바른 디렉터리에 symlink를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="13846-132">To fix this problem, create a symlink in the correct directory.</span></span>

```bash
sudo ln -s /etc/yum.repos.d/microsoft-prod.repo /etc/zypp/repos.d/microsoft-prod.repo
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="sles-12-"></a><span data-ttu-id="13846-133">SLES 12 ✔️</span><span class="sxs-lookup"><span data-stu-id="13846-133">SLES 12 ✔️</span></span>

<span data-ttu-id="13846-134">.NET에는 SLES 12 제품군에 대한 최소 요건으로 SP2가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="13846-134">.NET requires SP2 as a minimum for the SLES 12 family.</span></span>

[!INCLUDE [linux-prep-intro-generic](includes/linux-prep-intro-generic.md)]

```bash
sudo rpm -Uvh https://packages.microsoft.com/config/sles/12/packages-microsoft-prod.rpm
```

[!INCLUDE [linux-zyp-install-50](includes/linux-install-50-zyp.md)]

## <a name="how-to-install-other-versions"></a><span data-ttu-id="13846-135">다른 버전을 설치하는 방법</span><span class="sxs-lookup"><span data-stu-id="13846-135">How to install other versions</span></span>

[!INCLUDE [package-manager-switcher](./includes/package-manager-heading-hack-pkgname.md)]

## <a name="troubleshoot-the-package-manager"></a><span data-ttu-id="13846-136">패키지 관리자 문제 해결</span><span class="sxs-lookup"><span data-stu-id="13846-136">Troubleshoot the package manager</span></span>

<span data-ttu-id="13846-137">이 섹션에서는 패키지 관리자를 사용하여 .NET을 설치할 때 발생할 수 있는 일반적인 오류에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="13846-137">This section provides information on common errors you may get while using the package manager to install .NET.</span></span>

### <a name="failed-to-fetch"></a><span data-ttu-id="13846-138">가져오지 못함</span><span class="sxs-lookup"><span data-stu-id="13846-138">Failed to fetch</span></span>

[!INCLUDE [package-manager-failed-to-fetch-rpm](includes/package-manager-failed-to-fetch-rpm.md)]

## <a name="dependencies"></a><span data-ttu-id="13846-139">종속성</span><span class="sxs-lookup"><span data-stu-id="13846-139">Dependencies</span></span>

<span data-ttu-id="13846-140">패키지 관리자를 설치할 때 이러한 라이브러리가 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="13846-140">When you install with a package manager, these libraries are installed for you.</span></span> <span data-ttu-id="13846-141">그러나 .NET을 수동으로 설치하거나 자체 포함 앱을 게시할 경우 이러한 라이브러리가 설치되어 있는지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13846-141">But, if you manually install .NET or you publish a self-contained app, you'll need to make sure these libraries are installed:</span></span>

- <span data-ttu-id="13846-142">krb5</span><span class="sxs-lookup"><span data-stu-id="13846-142">krb5</span></span>
- <span data-ttu-id="13846-143">libicu</span><span class="sxs-lookup"><span data-stu-id="13846-143">libicu</span></span>
- <span data-ttu-id="13846-144">libopenssl1_1</span><span class="sxs-lookup"><span data-stu-id="13846-144">libopenssl1_1</span></span>

<span data-ttu-id="13846-145">대상 런타임 환경의 OpenSSL 버전이 1.1 이상인 경우, **compat-openssl10** 을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13846-145">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

<span data-ttu-id="13846-146">종속성에 대한 자세한 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13846-146">For more information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

<span data-ttu-id="13846-147">*System.Drawing.Common* 어셈블리를 사용하는 .NET 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="13846-147">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="13846-148">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="13846-148">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="13846-149">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus* 를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13846-149">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="13846-150">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="13846-150">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="next-steps"></a><span data-ttu-id="13846-151">다음 단계</span><span class="sxs-lookup"><span data-stu-id="13846-151">Next steps</span></span>

- [<span data-ttu-id="13846-152">.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="13846-152">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="13846-153">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="13846-153">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
