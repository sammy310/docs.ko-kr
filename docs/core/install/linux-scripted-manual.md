---
title: Linux에서 .NET 수동 설치 - .NET
description: Linux에서 패키지 관리자 없이 .NET SDK 및 .NET 런타임을 설치하는 방법을 보여 줍니다. 설치 스크립트를 사용하거나 이진 파일을 수동으로 추출합니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 5879d4d66aba8bfa00caadbe3c33d6df0d7da59a
ms.sourcegitcommit: 7ef96827b161ef3fcde75f79d839885632e26ef1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2021
ms.locfileid: "97970930"
---
# <a name="install-the-net-sdk-or-the-net-runtime-manually"></a><span data-ttu-id="23970-104">수동으로 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="23970-104">Install the .NET SDK or the .NET Runtime manually</span></span>

<span data-ttu-id="23970-105">.NET은 Linux에서 지원되며 이 문서에서는 설치 스크립트를 사용하거나 이진 파일을 추출하여 Linux에 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-105">.NET is supported on Linux and this article describes how to install .NET on Linux using the install script or by extracting the binaries.</span></span> <span data-ttu-id="23970-106">기본 제공 패키지 관리자를 지원하는 배포 목록은 [Linux에서 .NET 설치](linux.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23970-106">For a list of distributions that support the built-in package manager, see [Install .NET on Linux](linux.md).</span></span>

<span data-ttu-id="23970-107">Snap을 사용하여 .NET을 설치할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-107">You can also install .NET with snap.</span></span> <span data-ttu-id="23970-108">자세한 내용은 [Snap을 사용하여 .NET SDK 또는 .NET 런타임 설치](linux-snap.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23970-108">For more information, see [Install the .NET SDK or the .NET Runtime with Snap](linux-snap.md).</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="net-releases"></a><span data-ttu-id="23970-109">.NET 릴리스</span><span class="sxs-lookup"><span data-stu-id="23970-109">.NET releases</span></span>

<span data-ttu-id="23970-110">다음 표에는 .NET 및 .NET Core 릴리스가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-110">The following table lists the .NET (and .NET Core) releases:</span></span>

| <span data-ttu-id="23970-111">✔️ 지원됨</span><span class="sxs-lookup"><span data-stu-id="23970-111">✔️ Supported</span></span> | <span data-ttu-id="23970-112">❌ 지원 안 됨</span><span class="sxs-lookup"><span data-stu-id="23970-112">❌ Unsupported</span></span> |
|-------------|---------------|
| <span data-ttu-id="23970-113">5.0</span><span class="sxs-lookup"><span data-stu-id="23970-113">5.0</span></span>         | <span data-ttu-id="23970-114">3.0</span><span class="sxs-lookup"><span data-stu-id="23970-114">3.0</span></span>           |
| <span data-ttu-id="23970-115">3.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="23970-115">3.1 (LTS)</span></span>   | <span data-ttu-id="23970-116">2.2</span><span class="sxs-lookup"><span data-stu-id="23970-116">2.2</span></span>           |
| <span data-ttu-id="23970-117">2.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="23970-117">2.1 (LTS)</span></span>   | <span data-ttu-id="23970-118">2.0</span><span class="sxs-lookup"><span data-stu-id="23970-118">2.0</span></span>           |
|             | <span data-ttu-id="23970-119">1.1</span><span class="sxs-lookup"><span data-stu-id="23970-119">1.1</span></span>           |
|             | <span data-ttu-id="23970-120">1.0</span><span class="sxs-lookup"><span data-stu-id="23970-120">1.0</span></span>           |

<span data-ttu-id="23970-121">.NET 릴리스의 수명 주기에 대한 자세한 내용은 [.NET Core 및 .NET 5 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23970-121">For more information about the life cycle of .NET releases, see [.NET Core and .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="dependencies"></a><span data-ttu-id="23970-122">종속성</span><span class="sxs-lookup"><span data-stu-id="23970-122">Dependencies</span></span>

<span data-ttu-id="23970-123">.NET을 설치할 때 특정 종속성이 설치되지 않을 수 있습니다(예: [수동으로 설치](#manual-install)하는 경우).</span><span class="sxs-lookup"><span data-stu-id="23970-123">It's possible that when you install .NET, specific dependencies may not be installed, such as when [manually installing](#manual-install).</span></span> <span data-ttu-id="23970-124">다음 목록에서는 Microsoft에서 지원하며, 설치해야 할 수 있는 종속성이 있는 Linux 배포판에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-124">The following list details Linux distributions that are supported by Microsoft and have dependencies you may need to install.</span></span> <span data-ttu-id="23970-125">자세한 내용은 배포 페이지를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="23970-125">Check the distribution page for more information:</span></span>

- [<span data-ttu-id="23970-126">Alpine</span><span class="sxs-lookup"><span data-stu-id="23970-126">Alpine</span></span>](linux-alpine.md#dependencies)
- [<span data-ttu-id="23970-127">Debian</span><span class="sxs-lookup"><span data-stu-id="23970-127">Debian</span></span>](linux-debian.md#dependencies)
- [<span data-ttu-id="23970-128">CentOS</span><span class="sxs-lookup"><span data-stu-id="23970-128">CentOS</span></span>](linux-centos.md#dependencies)
- [<span data-ttu-id="23970-129">Fedora</span><span class="sxs-lookup"><span data-stu-id="23970-129">Fedora</span></span>](linux-fedora.md#dependencies)
- [<span data-ttu-id="23970-130">RHEL</span><span class="sxs-lookup"><span data-stu-id="23970-130">RHEL</span></span>](linux-rhel.md#dependencies)
- [<span data-ttu-id="23970-131">SLES</span><span class="sxs-lookup"><span data-stu-id="23970-131">SLES</span></span>](linux-sles.md#dependencies)
- [<span data-ttu-id="23970-132">Ubuntu</span><span class="sxs-lookup"><span data-stu-id="23970-132">Ubuntu</span></span>](linux-ubuntu.md#dependencies)

<span data-ttu-id="23970-133">종속성에 대한 일반적인 내용은 [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md)(자체 포함 Linux 앱)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23970-133">For generic information about the dependencies, see [Self-contained Linux apps](https://github.com/dotnet/core/blob/master/Documentation/self-contained-linux-apps.md).</span></span>

### <a name="rpm-dependencies"></a><span data-ttu-id="23970-134">RPM 종속성</span><span class="sxs-lookup"><span data-stu-id="23970-134">RPM dependencies</span></span>

<span data-ttu-id="23970-135">자신의 배포판이 위에 나열되지 않았으며 RPM 기반인 경우 다음 종속성이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-135">If your distribution wasn't previously listed, and is RPM-based, you may need the following dependencies:</span></span>

- <span data-ttu-id="23970-136">krb5-libs</span><span class="sxs-lookup"><span data-stu-id="23970-136">krb5-libs</span></span>
- <span data-ttu-id="23970-137">libicu</span><span class="sxs-lookup"><span data-stu-id="23970-137">libicu</span></span>
- <span data-ttu-id="23970-138">openssl-libs</span><span class="sxs-lookup"><span data-stu-id="23970-138">openssl-libs</span></span>

<span data-ttu-id="23970-139">대상 런타임 환경의 OpenSSL 버전이 1.1 이상인 경우, **compat-openssl10** 을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-139">If the target runtime environment's OpenSSL version is 1.1 or newer, you'll need to install **compat-openssl10**.</span></span>

### <a name="deb-dependencies"></a><span data-ttu-id="23970-140">DEB 종속성</span><span class="sxs-lookup"><span data-stu-id="23970-140">DEB dependencies</span></span>

<span data-ttu-id="23970-141">자신의 배포판이 위에 나열되지 않았으며 Debian 기반인 경우 다음 종속성이 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-141">If your distribution wasn't previously listed, and is debian-based, you may need the following dependencies:</span></span>

- <span data-ttu-id="23970-142">libc6</span><span class="sxs-lookup"><span data-stu-id="23970-142">libc6</span></span>
- <span data-ttu-id="23970-143">libgcc1</span><span class="sxs-lookup"><span data-stu-id="23970-143">libgcc1</span></span>
- <span data-ttu-id="23970-144">libgssapi-krb5-2</span><span class="sxs-lookup"><span data-stu-id="23970-144">libgssapi-krb5-2</span></span>
- <span data-ttu-id="23970-145">libicu67</span><span class="sxs-lookup"><span data-stu-id="23970-145">libicu67</span></span>
- <span data-ttu-id="23970-146">libssl1.1</span><span class="sxs-lookup"><span data-stu-id="23970-146">libssl1.1</span></span>
- <span data-ttu-id="23970-147">libstdc++6</span><span class="sxs-lookup"><span data-stu-id="23970-147">libstdc++6</span></span>
- <span data-ttu-id="23970-148">zlib1g</span><span class="sxs-lookup"><span data-stu-id="23970-148">zlib1g</span></span>

### <a name="common-dependencies"></a><span data-ttu-id="23970-149">일반 종속성</span><span class="sxs-lookup"><span data-stu-id="23970-149">Common dependencies</span></span>

<span data-ttu-id="23970-150">*System.Drawing.Common* 어셈블리를 사용하는 .NET 앱의 경우 다음과 같은 종속성도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-150">For .NET apps that use the *System.Drawing.Common* assembly, you'll also need the following dependency:</span></span>

- [<span data-ttu-id="23970-151">libgdiplus(버전 6.0.1 이상)</span><span class="sxs-lookup"><span data-stu-id="23970-151">libgdiplus (version 6.0.1 or later)</span></span>](https://www.mono-project.com/docs/gui/libgdiplus/)

  > [!WARNING]
  > <span data-ttu-id="23970-152">시스템에 Mono 리포지토리를 추가하여 최신 버전의 *libgdiplus* 를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-152">You can install a recent version of *libgdiplus* by adding the Mono repository to your system.</span></span> <span data-ttu-id="23970-153">자세한 내용은 <https://www.mono-project.com/download/stable/>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23970-153">For more information, see <https://www.mono-project.com/download/stable/>.</span></span>

## <a name="scripted-install"></a><span data-ttu-id="23970-154">스크립팅된 설치</span><span class="sxs-lookup"><span data-stu-id="23970-154">Scripted install</span></span>

<span data-ttu-id="23970-155">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화와 **SDK** 및 **런타임** 의 관리자 설치가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="23970-155">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the **SDK** and **Runtime**.</span></span> <span data-ttu-id="23970-156"><https://dot.net/v1/dotnet-install.sh>에서 스크립트를 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-156">You can download the script from <https://dot.net/v1/dotnet-install.sh>.</span></span>

<span data-ttu-id="23970-157">스크립트는 기본적으로 최신 SDK [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-157">The script defaults to installing the latest SDK [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="23970-158">(LTS) 버전이 아닐 수 있는 현재 릴리스를 설치하려면 `-c Current` 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-158">To install the current release, which may not be an (LTS) version, use the `-c Current` parameter.</span></span>

```bash
./dotnet-install.sh -c Current
```

<span data-ttu-id="23970-159">SDK 대신 .NET 런타임을 설치하려면 `--runtime` 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-159">To install .NET Runtime instead of the SDK, use the `--runtime` parameter.</span></span>

```bash
./dotnet-install.sh -c Current --runtime aspnetcore
```

<span data-ttu-id="23970-160">특정 버전을 지정하도록 `-c` 매개 변수를 변경하여 특정 버전을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-160">You can install a specific version by altering the `-c` parameter to indicate the specific version.</span></span> <span data-ttu-id="23970-161">다음 명령은 .NET SDK 5.0을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-161">The following command installs .NET SDK 5.0.</span></span>

```bash
./dotnet-install.sh -c 5.0
```

<span data-ttu-id="23970-162">자세한 내용은 [dotnet-install 스크립트 참조](../tools/dotnet-install-script.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="23970-162">For more information, see [dotnet-install scripts reference](../tools/dotnet-install-script.md).</span></span>

## <a name="manual-install"></a><span data-ttu-id="23970-163">수동 설치</span><span class="sxs-lookup"><span data-stu-id="23970-163">Manual install</span></span>

<!-- Note, this content is copied in macos.md. Any fixes should be applied there too, though content may be different -->

<span data-ttu-id="23970-164">패키지 관리자의 대안으로, SDK와 런타임을 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-164">As an alternative to the package managers, you can download and manually install the SDK and runtime.</span></span> <span data-ttu-id="23970-165">수동 설치는 일반적으로 연속 통합 테스트의 일부로서 사용되거나 지원되지 않는 Linux 배포판에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="23970-165">Manual install is commonly used as part of continuous integration testing or on an unsupported Linux distribution.</span></span> <span data-ttu-id="23970-166">개발자 또는 사용자의 경우 패키지 관리자를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-166">For a developer or user, it's better to use a package manager.</span></span>

<span data-ttu-id="23970-167">.NET SDK를 설치하면 해당 런타임을 설치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-167">If you install .NET SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="23970-168">먼저, 다음 사이트 중 한 곳에서 SDK 또는 런타임의 **이진** 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-168">First, download a **binary** release for either the SDK or the runtime from one of the following sites:</span></span>

- <span data-ttu-id="23970-169">✔️ [.NET 5.0 다운로드](https://dotnet.microsoft.com/download/dotnet/5.0)</span><span class="sxs-lookup"><span data-stu-id="23970-169">✔️ [.NET 5.0 downloads](https://dotnet.microsoft.com/download/dotnet/5.0)</span></span>
- <span data-ttu-id="23970-170">✔️ [.NET Core 3.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="23970-170">✔️ [.NET Core 3.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span></span>
- <span data-ttu-id="23970-171">✔️ [.NET Core 2.1 다운로드](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span><span class="sxs-lookup"><span data-stu-id="23970-171">✔️ [.NET Core 2.1 downloads](https://dotnet.microsoft.com/download/dotnet-core/2.1)</span></span>
- [<span data-ttu-id="23970-172">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="23970-172">All .NET Core downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core)

<span data-ttu-id="23970-173">그런 다음, 다운로드된 파일을 추출하고 `export` 명령을 사용하여 .NET에서 사용된 변수를 설정하고 .NET이 PATH에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-173">Next, extract the downloaded file and use the `export` command to set variables used by .NET and then ensure .NET is in PATH.</span></span>

<span data-ttu-id="23970-174">런타임을 추출하고 터미널에서 .NET CLI 명령을 사용할 수 있도록 하려면 먼저 .NET 이진 릴리스를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-174">To extract the runtime and make the .NET CLI commands available at the terminal, first download a .NET binary release.</span></span> <span data-ttu-id="23970-175">그런 다음, 터미널을 열고 파일이 저장된 디렉터리에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-175">Then, open a terminal and run the following commands from the directory where the file was saved.</span></span> <span data-ttu-id="23970-176">보관 파일 이름은 다운로드한 항목에 따라 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-176">The archive file name may be different depending on what you downloaded.</span></span>

<span data-ttu-id="23970-177">**다음 명령을 사용하여 런타임을 추출합니다.**</span><span class="sxs-lookup"><span data-stu-id="23970-177">**Use the following command to extract the runtime**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf aspnetcore-runtime-5.0.0-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

<span data-ttu-id="23970-178">**다음 명령을 사용하여 SDK를 추출합니다.**</span><span class="sxs-lookup"><span data-stu-id="23970-178">**Use the following command to extract the SDK**:</span></span>

```bash
mkdir -p "$HOME/dotnet" && tar zxf dotnet-sdk-5.0.100-linux-x64.tar.gz -C "$HOME/dotnet"
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="23970-179">이전 `export` 명령은 명령이 실행된 터미널 세션에서만 .NET CLI 명령을 사용할 수 있도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="23970-179">The preceding `export` commands only make the .NET CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="23970-180">셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-180">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="23970-181">몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-181">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="23970-182">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="23970-182">For example:</span></span>
>
> - <span data-ttu-id="23970-183">**Bash 셸**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="23970-183">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="23970-184">**Korn 셸**: *~/.kshrc* 또는 *.profile*</span><span class="sxs-lookup"><span data-stu-id="23970-184">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="23970-185">**Z 셸**: *~/.zshrc* 또는 *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="23970-185">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="23970-186">셸의 적절한 소스 파일을 편집하고 기존 `PATH` 문의 끝에 `:$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-186">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="23970-187">포함된 `PATH` 문이 없다면 `export PATH=$PATH:$HOME/dotnet`을 사용하여 새 라인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-187">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="23970-188">또한, 파일 끝에 `export DOTNET_ROOT=$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="23970-188">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="23970-189">이 방법을 사용하면 서로 다른 버전을 별도의 위치에 설치하고 애플리케이션에서 사용할 수 있도록 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="23970-189">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

## <a name="next-steps"></a><span data-ttu-id="23970-190">다음 단계</span><span class="sxs-lookup"><span data-stu-id="23970-190">Next steps</span></span>

- [<span data-ttu-id="23970-191">.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="23970-191">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="23970-192">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="23970-192">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
