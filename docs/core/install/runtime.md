---
title: Windows, Linux 및 macOS에 .NET Core 런타임 설치 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core를 설치하는 방법을 알아봅니다. .NET Core 앱을 실행하는 데 필요한 종속성에 대해 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a41bbdf5419585f06773583dbe82ab0d84ebaa4c
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78157638"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="163df-104">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="163df-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="163df-105">이 문서에서는 .NET Core 런타임을 다운로드하고 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="163df-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="163df-106">.NET Core 런타임은 .NET Core로 만든 앱을 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="163df-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="163df-107">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="163df-107">Install with an installer</span></span>

<span data-ttu-id="163df-108">Windows에는 .NET Core 3.1 런타임을 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="163df-109">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="163df-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="163df-110">x86(32비트) CPU</span><span class="sxs-lookup"><span data-stu-id="163df-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="163df-111">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="163df-111">Install with an installer</span></span>

<span data-ttu-id="163df-112">macOS에는 .NET Core 3.1 런타임을 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="163df-113">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="163df-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="163df-114">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="163df-114">Download and manually install</span></span>

<span data-ttu-id="163df-115">.NET Core용 macOS 설치 프로그램의 대안으로, 런타임을 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="163df-116">런타임을 실행하고 터미널에서 사용 가능한 .NET Core CLI 명령을 사용하도록 설정하려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="163df-117">그런 다음 터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="163df-118">런타임이 `~/Downloads/dotnet-runtime.pkg` 파일로 다운로드되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="163df-119">패키지 관리자를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="163df-119">Install with a package manager</span></span>

<span data-ttu-id="163df-120">널리 사용되는 여러 Linux 패키지 관리자를 사용하여 .NET Core 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-120">You can install the .NET Core Runtime with many of the common Linux package managers.</span></span> <span data-ttu-id="163df-121">자세한 내용은 [Linux 패키지 관리자 - .NET Core 설치](linux-package-managers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="163df-121">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

<span data-ttu-id="163df-122">패키지 관리자를 사용한 설치는 x64 아키텍처에서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="163df-122">Installing it with a package manager is only supported on the x64 architecture.</span></span> <span data-ttu-id="163df-123">ARM과 같은 다른 아키텍처를 사용하여 .NET Core 런타임을 설치하는 경우 [다운로드 및 수동 설치](#download-and-manually-install) 섹션의 지침을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="163df-123">If you're installing the .NET Core Runtime with a different architecture, such as ARM, follow the instructions on the [Download and manually install](#download-and-manually-install) section.</span></span> <span data-ttu-id="163df-124">지원되는 아키텍처에 대한 자세한 내용은 [.NET Core 종속성 및 요구 사항](dependencies.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="163df-124">For more information about what architectures are supported, see [.NET Core dependencies and requirements](dependencies.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="163df-125">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="163df-125">Download and manually install</span></span>

<span data-ttu-id="163df-126">런타임을 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-126">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="163df-127">그런 다음 터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-127">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf aspnetcore-runtime-3.1.0-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="163df-128">이전 `export` 명령은 명령이 실행된 터미널 세션에서만 .NET Core CLI 명령을 사용할 수 있도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="163df-128">The preceding `export` commands only make the .NET Core CLI commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="163df-129">셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-129">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="163df-130">몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-130">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="163df-131">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="163df-131">For example:</span></span>
>
> - <span data-ttu-id="163df-132">**Bash 셸**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="163df-132">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="163df-133">**Korn 셸**: *~/.kshrc* 또는 *.profile*</span><span class="sxs-lookup"><span data-stu-id="163df-133">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="163df-134">**Z 셸**: *~/.zshrc* 또는 *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="163df-134">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="163df-135">셸의 적절한 소스 파일을 편집하고 기존 `PATH` 문의 끝에 `:$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-135">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="163df-136">포함된 `PATH` 문이 없다면 `export PATH=$PATH:$HOME/dotnet`을 사용하여 새 라인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-136">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="163df-137">또한, 파일 끝에 `export DOTNET_ROOT=$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-137">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

<span data-ttu-id="163df-138">이 방법을 사용하면 서로 다른 버전을 별도의 위치에 설치하고 애플리케이션에서 사용할 수 있도록 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-138">This approach lets you install different versions into separate locations and choose explicitly which one to use by which application.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="163df-139">PowerShell 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="163df-139">Install with PowerShell automation</span></span>

<span data-ttu-id="163df-140">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="163df-140">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="163df-141">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-141">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="163df-142">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-142">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="163df-143">`Channel` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-143">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="163df-144">런타임을 설치하려면 `Runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-144">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="163df-145">포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-145">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="163df-146">위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-146">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="163df-147">ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-147">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="163df-148">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="163df-148">Download and manually install</span></span>

<span data-ttu-id="163df-149">런타임을 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="163df-150">그런 다음 `%USERPROFILE%\dotnet`와 같이 설치할 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="163df-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="163df-151">마지막으로 다운로드한 zip 파일을 그 디렉터리로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="163df-152">기본적으로 .NET Core CLI 명령과 앱은 이러한 방식으로 설치된 .NET Core를 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-152">By default, .NET Core CLI commands and apps will not use .NET Core installed in this way.</span></span> <span data-ttu-id="163df-153">이를 사용하려면 명시적으로 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-153">You have to explicitly choose to use it.</span></span> <span data-ttu-id="163df-154">이렇게 하려면 애플리케이션이 시작되는 환경 변수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-154">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="163df-155">이 방법을 사용하면 여러 버전을 별도의 위치에 설치한 다음 애플리케이션이 해당 위치를 가리키는 환경 변수를 사용하여 애플리케이션을 실행하는 데 사용해야 하는 설치 위치를 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-155">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="163df-156">이러한 환경 변수가 설정된 경우에도 .NET Core는 애플리케이션을 실행하는 데 가장 적합한 프레임워크를 선택할 때 기본 전역 설치 위치를 계속 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-156">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="163df-157">기본값은 일반적으로 설치 프로그램이 사용하는 `C:\Program Files\dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="163df-157">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="163df-158">이 환경 변수를 설정하여 사용자 지정 설치 위치만 사용하도록 런타임에 지시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-158">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="163df-159">배시 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="163df-159">Install with bash automation</span></span>

<span data-ttu-id="163df-160">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="163df-160">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="163df-161">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-161">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="163df-162">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-162">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="163df-163">`current` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-163">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="163df-164">런타임을 설치하려면 `runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-164">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="163df-165">포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-165">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="163df-166">위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-166">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="163df-167">ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-167">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="163df-168">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="163df-168">All .NET Core downloads</span></span>

<span data-ttu-id="163df-169">다음 링크 중 하나를 사용하여 .NET Core를 직접 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-169">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="163df-170">.NET Core 3.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="163df-170">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="163df-171">.NET Core 3.0 다운로드</span><span class="sxs-lookup"><span data-stu-id="163df-171">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="163df-172">.NET Core 2.2 다운로드</span><span class="sxs-lookup"><span data-stu-id="163df-172">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="163df-173">.NET Core 2.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="163df-173">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="163df-174">Docker</span><span class="sxs-lookup"><span data-stu-id="163df-174">Docker</span></span>

<span data-ttu-id="163df-175">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-175">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="163df-176">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-176">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="163df-177">.NET Core는 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-177">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="163df-178">공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-178">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="163df-179">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="163df-179">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="163df-180">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-180">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="163df-181">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="163df-181">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="163df-182">Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="163df-182">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="163df-183">다음 단계</span><span class="sxs-lookup"><span data-stu-id="163df-183">Next steps</span></span>

- <span data-ttu-id="163df-184">[.NET Core가 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md)</span><span class="sxs-lookup"><span data-stu-id="163df-184">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
