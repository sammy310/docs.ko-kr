---
title: Windows, Linux 및 macOS에 .NET Core 런타임 설치 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core를 설치하는 방법을 알아봅니다. .NET Core 앱을 실행하는 데 필요한 종속성에 대해 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: c079e1856cdd370a278efc6fdfb4953059b6f2ba
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84596295"
---
# <a name="install-the-net-core-runtime"></a><span data-ttu-id="25051-104">.NET Core 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="25051-104">Install the .NET Core Runtime</span></span>

<span data-ttu-id="25051-105">이 문서에서는 .NET Core 런타임을 다운로드하고 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="25051-105">In this article, you'll learn how to download and install the .NET Core runtime.</span></span> <span data-ttu-id="25051-106">.NET Core 런타임은 .NET Core로 만든 앱을 실행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25051-106">The .NET Core runtime is used to run apps created with .NET Core.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="25051-107">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="25051-107">Install with an installer</span></span>

<span data-ttu-id="25051-108">Windows에는 .NET Core 3.1 런타임을 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-108">Windows has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="25051-109">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="25051-109">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="25051-110">x86(32비트) CPU</span><span class="sxs-lookup"><span data-stu-id="25051-110">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="25051-111">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="25051-111">Install with an installer</span></span>

<span data-ttu-id="25051-112">macOS에는 .NET Core 3.1 런타임을 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-112">macOS has standalone installers that can be used to install the .NET Core 3.1 runtime:</span></span>

- [<span data-ttu-id="25051-113">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="25051-113">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="25051-114">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="25051-114">Download and manually install</span></span>

<span data-ttu-id="25051-115">.NET Core용 macOS 설치 프로그램의 대안으로, 런타임을 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-115">As an alternative to the macOS installers for .NET Core, you can download and manually install the runtime.</span></span>

<span data-ttu-id="25051-116">런타임을 실행하고 터미널에서 사용 가능한 .NET Core CLI 명령을 사용하도록 설정하려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-116">To install the runtime and enable the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="25051-117">그런 다음 터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-117">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="25051-118">런타임이 `~/Downloads/dotnet-runtime.pkg` 파일로 다운로드되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-118">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-runtime.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-runtime.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="25051-119">Linux에 설치</span><span class="sxs-lookup"><span data-stu-id="25051-119">Install on Linux</span></span>

<span data-ttu-id="25051-120">이 문서는 곧 제거될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="25051-120">This article will be removed soon.</span></span> <span data-ttu-id="25051-121">현재 [Linux에서 .NET Core 설치](linux.md)로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-121">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="25051-122">PowerShell 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="25051-122">Install with PowerShell automation</span></span>

<span data-ttu-id="25051-123">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25051-123">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="25051-124">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-124">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="25051-125">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-125">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="25051-126">`Channel` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-126">You can choose a specific release by specifying the `Channel` switch.</span></span> <span data-ttu-id="25051-127">런타임을 설치하려면 `Runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-127">Include the `Runtime` switch to install a runtime.</span></span> <span data-ttu-id="25051-128">포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-128">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```powershell
dotnet-install.ps1 -Channel 3.1 -Runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="25051-129">위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-129">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="25051-130">ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-130">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="25051-131">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="25051-131">Download and manually install</span></span>

<span data-ttu-id="25051-132">런타임을 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-132">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="25051-133">그런 다음 `%USERPROFILE%\dotnet`와 같이 설치할 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25051-133">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="25051-134">마지막으로 다운로드한 zip 파일을 그 디렉터리로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-134">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="25051-135">기본적으로 .NET Core CLI 명령과 앱은 이런 방식으로 설치된 .NET Core를 사용하지 않으므로 명시적으로 사용을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-135">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="25051-136">이렇게 하려면 애플리케이션이 시작되는 환경 변수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-136">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="25051-137">이 방법을 사용하면 여러 버전을 별도의 위치에 설치한 다음 애플리케이션이 해당 위치를 가리키는 환경 변수를 사용하여 애플리케이션을 실행하는 데 사용해야 하는 설치 위치를 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-137">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="25051-138">이러한 환경 변수가 설정된 경우에도 .NET Core는 애플리케이션을 실행하는 데 가장 적합한 프레임워크를 선택할 때 기본 전역 설치 위치를 계속 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-138">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="25051-139">기본값은 일반적으로 설치 프로그램이 사용하는 `C:\Program Files\dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="25051-139">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="25051-140">이 환경 변수를 설정하여 사용자 지정 설치 위치만 사용하도록 런타임에 지시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-140">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="25051-141">배시 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="25051-141">Install with bash automation</span></span>

<span data-ttu-id="25051-142">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 런타임의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="25051-142">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the runtime.</span></span> <span data-ttu-id="25051-143">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-143">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="25051-144">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-144">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="25051-145">`current` 스위치를 지정하여 특정 릴리스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-145">You can choose a specific release by specifying the `current` switch.</span></span> <span data-ttu-id="25051-146">런타임을 설치하려면 `runtime` 스위치를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-146">Include the `runtime` switch to install a runtime.</span></span> <span data-ttu-id="25051-147">포함하지 않을 경우 스크립트가 [SDK](sdk.md)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-147">Otherwise, the script installs the [SDK](sdk.md).</span></span>

```bash
./dotnet-install.sh --channel 3.1 --runtime aspnetcore
```

> [!NOTE]
> <span data-ttu-id="25051-148">위 명령은 최대의 호환성을 위해 ASP.NET Core 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-148">The command above installs the ASP.NET Core runtime for maximum compatability.</span></span> <span data-ttu-id="25051-149">ASP.NET Core 런타임에는 표준 .NET Core 런타임도 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-149">The ASP.NET Core runtime also includes the standard .NET Core runtime.</span></span>

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="25051-150">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="25051-150">All .NET Core downloads</span></span>

<span data-ttu-id="25051-151">다음 링크 중 하나를 사용하여 .NET Core를 직접 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-151">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="25051-152">.NET Core 3.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="25051-152">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="25051-153">.NET Core 2.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="25051-153">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="25051-154">Docker</span><span class="sxs-lookup"><span data-stu-id="25051-154">Docker</span></span>

<span data-ttu-id="25051-155">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-155">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="25051-156">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-156">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="25051-157">.NET Core는 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-157">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="25051-158">공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-158">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="25051-159">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25051-159">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="25051-160">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-160">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="25051-161">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="25051-161">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="25051-162">Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="25051-162">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="25051-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="25051-163">Next steps</span></span>

- <span data-ttu-id="25051-164">[.NET Core가 설치되어 있는지 확인하는 방법](how-to-detect-installed-versions.md)</span><span class="sxs-lookup"><span data-stu-id="25051-164">[How to check if .NET Core is already installed](how-to-detect-installed-versions.md).</span></span>
