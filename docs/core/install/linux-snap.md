---
title: Snap을 사용하여 Linux에 .NET 설치 - .NET
description: Snap을 사용하여 Linux에 .NET SDK 또는 .NET 런타임을 설치하는 방법을 보여 줍니다.
author: adegeo
ms.author: adegeo
ms.date: 01/06/2021
ms.openlocfilehash: 0d91f5049c92df240e2c3e26bc67952abe17fedc
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190101"
---
# <a name="install-the-net-sdk-or-the-net-runtime-with-snap"></a><span data-ttu-id="08f88-103">Snap을 사용하여 .NET SDK 또는 .NET 런타임 설치</span><span class="sxs-lookup"><span data-stu-id="08f88-103">Install the .NET SDK or the .NET Runtime with Snap</span></span>

<span data-ttu-id="08f88-104">Snap 패키지를 사용하여 .NET SDK 또는 .NET 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-104">Use a Snap package to install the .NET SDK or .NET Runtime.</span></span> <span data-ttu-id="08f88-105">Snap은 Linux 배포에 기본 제공되는 패키지 관리자의 좋은 대안입니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-105">Snaps are a great alternative to the package manager built into your Linux distribution.</span></span> <span data-ttu-id="08f88-106">이 문서에서는 [Snap](https://snapcraft.io/dotnet-sdk)을 통해 .NET을 설치하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-106">This article describes how to install .NET through [Snap](https://snapcraft.io/dotnet-sdk).</span></span>

<span data-ttu-id="08f88-107">Snap은 다양한 Linux 배포판에서 수정하지 않고도 작동하는 앱의 번들이자 종속성입니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-107">A snap is a bundle of an app and its dependencies that works without modification across many different Linux distributions.</span></span> <span data-ttu-id="08f88-108">Snap은 Snap 스토어에서 검색해서 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-108">Snaps are discoverable and installable from the Snap Store.</span></span> <span data-ttu-id="08f88-109">Snap에 대한 자세한 내용은 [Snap 시작하기](https://snapcraft.io/docs/getting-started)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08f88-109">For more information about Snap, see [Getting started with Snap](https://snapcraft.io/docs/getting-started).</span></span>

> [!CAUTION]
> <span data-ttu-id="08f88-110">Snap 패키지는 Windows 10의 WSL2에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-110">Snap packages aren't supported in WSL2 on Windows 10.</span></span> <span data-ttu-id="08f88-111">이에 대한 대안으로, 특정 WSL2 배포를 위해 [`dotnet-install` 스크립트](linux-scripted-manual.md#scripted-install) 또는 패키지 관리자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-111">As an alternative, use the [`dotnet-install` script](linux-scripted-manual.md#scripted-install) or the package manager for the particular WSL2 distribution.</span></span> <span data-ttu-id="08f88-112">권장되지는 않지만 [snapcraft 포럼에서 지원되지 않는 해결 방법](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033)을 사용하여 Snap을 사용하도록 설정해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-112">It's not recommended but you can try to enable snap with an [unsupported workaround from the snapcraft forums](https://forum.snapcraft.io/t/running-snaps-on-wsl2-insiders-only-for-now/13033).</span></span>

## <a name="net-releases"></a><span data-ttu-id="08f88-113">.NET 릴리스</span><span class="sxs-lookup"><span data-stu-id="08f88-113">.NET releases</span></span>

<span data-ttu-id="08f88-114">✔️ 지원되는 버전의 .NET SDK만 Snap을 통해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-114">Only ✔️ supported versions of .NET SDK are available through Snap.</span></span> <span data-ttu-id="08f88-115">버전 2.1부터 Snap을 통해 모든 버전의 .NET 런타임을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-115">All versions of the .NET Runtime are available through snap starting with version 2.1.</span></span> <span data-ttu-id="08f88-116">다음 표에는 .NET 및 .NET Core 릴리스가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-116">The following table lists the .NET (and .NET Core) releases:</span></span>

| <span data-ttu-id="08f88-117">✔️ 지원됨</span><span class="sxs-lookup"><span data-stu-id="08f88-117">✔️ Supported</span></span> | <span data-ttu-id="08f88-118">❌ 지원 안 됨</span><span class="sxs-lookup"><span data-stu-id="08f88-118">❌ Unsupported</span></span> |
|-------------|---------------|
| <span data-ttu-id="08f88-119">5.0</span><span class="sxs-lookup"><span data-stu-id="08f88-119">5.0</span></span>         | <span data-ttu-id="08f88-120">3.0</span><span class="sxs-lookup"><span data-stu-id="08f88-120">3.0</span></span>           |
| <span data-ttu-id="08f88-121">3.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="08f88-121">3.1 (LTS)</span></span>   | <span data-ttu-id="08f88-122">2.2</span><span class="sxs-lookup"><span data-stu-id="08f88-122">2.2</span></span>           |
| <span data-ttu-id="08f88-123">2.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="08f88-123">2.1 (LTS)</span></span>   | <span data-ttu-id="08f88-124">2.0</span><span class="sxs-lookup"><span data-stu-id="08f88-124">2.0</span></span>           |
|             | <span data-ttu-id="08f88-125">1.1</span><span class="sxs-lookup"><span data-stu-id="08f88-125">1.1</span></span>           |
|             | <span data-ttu-id="08f88-126">1.0</span><span class="sxs-lookup"><span data-stu-id="08f88-126">1.0</span></span>           |

<span data-ttu-id="08f88-127">.NET 릴리스의 수명 주기에 대한 자세한 내용은 [.NET Core 및 .NET 5 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="08f88-127">For more information about the life cycle of .NET releases, see [.NET Core and .NET 5 Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core).</span></span>

## <a name="sdk-or-runtime"></a><span data-ttu-id="08f88-128">SDK 또는 런타임</span><span class="sxs-lookup"><span data-stu-id="08f88-128">SDK or Runtime</span></span>

[!INCLUDE [linux-intro-sdk-vs-runtime](includes/linux-intro-sdk-vs-runtime.md)]

## <a name="install-the-sdk"></a><span data-ttu-id="08f88-129">SDK 설치</span><span class="sxs-lookup"><span data-stu-id="08f88-129">Install the SDK</span></span>

<span data-ttu-id="08f88-130">.NET SDK용 Snap 패키지는 모두 동일한 식별자 `dotnet-sdk`로 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-130">Snap packages for the .NET SDK are all published under the same identifier: `dotnet-sdk`.</span></span> <span data-ttu-id="08f88-131">특정 버전의 SDK는 채널을 지정하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-131">A specific version of the SDK can be installed by specifying the channel.</span></span> <span data-ttu-id="08f88-132">SDK에는 해당 런타임이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-132">The SDK includes the corresponding runtime.</span></span> <span data-ttu-id="08f88-133">다음 표에서는 채널 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-133">The following table lists the channels:</span></span>

| <span data-ttu-id="08f88-134">.NET 버전</span><span class="sxs-lookup"><span data-stu-id="08f88-134">.NET version</span></span> | <span data-ttu-id="08f88-135">Snap 패키지 또는 채널</span><span class="sxs-lookup"><span data-stu-id="08f88-135">Snap package or channel</span></span>  |
|--------------|--------------------------|
| <span data-ttu-id="08f88-136">5.0</span><span class="sxs-lookup"><span data-stu-id="08f88-136">5.0</span></span>          | <span data-ttu-id="08f88-137">`5.0` 또는 `latest/stable`</span><span class="sxs-lookup"><span data-stu-id="08f88-137">`5.0` or `latest/stable`</span></span> |
| <span data-ttu-id="08f88-138">3.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="08f88-138">3.1 (LTS)</span></span>    | <span data-ttu-id="08f88-139">`3.1` 또는 `lts/stable`</span><span class="sxs-lookup"><span data-stu-id="08f88-139">`3.1` or `lts/stable`</span></span>    |
| <span data-ttu-id="08f88-140">2.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="08f88-140">2.1 (LTS)</span></span>    | `2.1`                    |

<span data-ttu-id="08f88-141">`snap install` 명령을 사용하여 .NET SDK 스냅 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-141">Use the `snap install` command to install a .NET SDK snap package.</span></span> <span data-ttu-id="08f88-142">`--channel` 매개 변수를 사용하여 설치할 버전을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-142">Use the `--channel` parameter to indicate which version to install.</span></span> <span data-ttu-id="08f88-143">이 매개 변수를 생략하면 `latest/stable`이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-143">If this parameter is omitted, `latest/stable` is used.</span></span> <span data-ttu-id="08f88-144">이 예에서는 `5.0`이 지정되었습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-144">In this example, `5.0` is specified:</span></span>

```bash
sudo snap install dotnet-sdk --classic --channel=5.0
```

<span data-ttu-id="08f88-145">다음으로 `snap alias` 명령을 사용하여 시스템에 `dotnet` 명령을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-145">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="08f88-146">이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-146">This command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="08f88-147">원하는 `{alias}` 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-147">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="08f88-148">예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-sdk.dotnet dotnet50`).</span><span class="sxs-lookup"><span data-stu-id="08f88-148">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-sdk.dotnet dotnet50`.</span></span> <span data-ttu-id="08f88-149">`dotnet50` 명령을 사용할 경우 이 특정 버전의 .NET를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-149">When you use the command `dotnet50`, you'll invoke this specific version of .NET.</span></span> <span data-ttu-id="08f88-150">그러나 다른 별칭을 선택할 경우 `dotnet` 명령이 사용될 것으로 예상하는 대부분의 자습서 및 예제와 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-150">But choosing a different alias is incompatible with most tutorials and examples as they expect a `dotnet` command to be used.</span></span>

## <a name="install-the-runtime"></a><span data-ttu-id="08f88-151">런타임 설치</span><span class="sxs-lookup"><span data-stu-id="08f88-151">Install the runtime</span></span>

<span data-ttu-id="08f88-152">.NET 런타임용 Snap 패키지는 각각 자체 패키지 식별자로 게시됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-152">Snap packages for the .NET Runtime are each published under their own package identifier.</span></span> <span data-ttu-id="08f88-153">다음 표에는 패키지 식별자가 나열되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-153">The following table lists the package identifiers:</span></span>

| <span data-ttu-id="08f88-154">.NET 버전</span><span class="sxs-lookup"><span data-stu-id="08f88-154">.NET version</span></span>      | <span data-ttu-id="08f88-155">맞춤 패키지</span><span class="sxs-lookup"><span data-stu-id="08f88-155">Snap package</span></span>        |
|-------------------|---------------------|
| <span data-ttu-id="08f88-156">5.0</span><span class="sxs-lookup"><span data-stu-id="08f88-156">5.0</span></span>               | `dotnet-runtime-50` |
| <span data-ttu-id="08f88-157">3.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="08f88-157">3.1 (LTS)</span></span>         | `dotnet-runtime-31` |
| <span data-ttu-id="08f88-158">3.0</span><span class="sxs-lookup"><span data-stu-id="08f88-158">3.0</span></span>               | `dotnet-runtime-30` |
| <span data-ttu-id="08f88-159">2.2</span><span class="sxs-lookup"><span data-stu-id="08f88-159">2.2</span></span>               | `dotnet-runtime-22` |
| <span data-ttu-id="08f88-160">2.1(LTS)</span><span class="sxs-lookup"><span data-stu-id="08f88-160">2.1 (LTS)</span></span>         | `dotnet-runtime-21` |

<span data-ttu-id="08f88-161">`snap install` 명령을 사용하여 .NET 런타임 스냅 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-161">Use the `snap install` command to install a .NET Runtime snap package.</span></span> <span data-ttu-id="08f88-162">이 예제에서는 .NET 5.0이 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-162">In this example, .NET 5.0 is installed:</span></span>

```bash
sudo snap install dotnet-runtime-50 --classic
```

<span data-ttu-id="08f88-163">다음으로 `snap alias` 명령을 사용하여 시스템에 `dotnet` 명령을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-163">Next, register the `dotnet` command for the system with the `snap alias` command:</span></span>

```bash
sudo snap alias dotnet-runtime-50.dotnet dotnet
```

<span data-ttu-id="08f88-164">이 명령의 형식은 `sudo snap alias {package}.{command} {alias}`로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-164">The command is formatted as: `sudo snap alias {package}.{command} {alias}`.</span></span> <span data-ttu-id="08f88-165">원하는 `{alias}` 이름을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-165">You can choose any `{alias}` name you would like.</span></span> <span data-ttu-id="08f88-166">예를 들어, Snap으로 설치한 특정 버전 뒤에 명령 이름을 지정할 수 있습니다(예: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`).</span><span class="sxs-lookup"><span data-stu-id="08f88-166">For example, you could name the command after the specific version installed by snap: `sudo snap alias dotnet-runtime-50.dotnet dotnet50`.</span></span> <span data-ttu-id="08f88-167">`dotnet50` 명령을 사용할 경우 특정 버전의 .NET이 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-167">When you use the command `dotnet50`, you'll invoke a specific version of .NET.</span></span> <span data-ttu-id="08f88-168">그러나 다른 별칭을 선택할 경우 `dotnet` 명령이 사용 가능할 것으로 예상하는 대부분의 자습서 및 예제와 호환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-168">But choosing a different alias is incompatible with most tutorials and examples as they expect a `dotnet` command to be available.</span></span>

## <a name="export-the-install-location"></a><span data-ttu-id="08f88-169">설치 위치 내보내기</span><span class="sxs-lookup"><span data-stu-id="08f88-169">Export the install location</span></span>

<span data-ttu-id="08f88-170">`DOTNET_ROOT` 환경 변수는 도구에서 .NET이 설치된 위치를 확인하는 데 자주 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-170">The `DOTNET_ROOT` environment variable is often used by tools to determine where .NET is installed.</span></span> <span data-ttu-id="08f88-171">.NET이 Snap을 통해 설치되면 이 환경 변수는 구성되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-171">When .NET is installed through Snap, this environment variable isn't configured.</span></span> <span data-ttu-id="08f88-172">프로필에서 *DOTNET_ROOT* 환경 변수를 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-172">You should configure the *DOTNET_ROOT* environment variable in your profile.</span></span> <span data-ttu-id="08f88-173">스냅 경로는 `/snap/{package}/current` 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-173">The path to the snap uses the following format: `/snap/{package}/current`.</span></span> <span data-ttu-id="08f88-174">예를 들어 `dotnet-sdk` 스냅을 설치한 경우 다음 명령을 사용하여 환경 변수를 .NET이 있는 위치로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-174">For example, if you installed the `dotnet-sdk` snap, use the following command to set the environment variable to where .NET is located:</span></span>

```bash
export DOTNET_ROOT=/snap/dotnet-sdk/current
```

> [!TIP]
> <span data-ttu-id="08f88-175">앞의 `export` 명령은 실행된 터미널 세션에 대한 환경 변수만 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-175">The preceding `export` command only sets the environment variable for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="08f88-176">셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-176">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="08f88-177">몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-177">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="08f88-178">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="08f88-178">For example:</span></span>
>
> - <span data-ttu-id="08f88-179">**Bash 셸**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="08f88-179">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="08f88-180">**Korn 셸**: *~/.kshrc* 또는 *.profile*</span><span class="sxs-lookup"><span data-stu-id="08f88-180">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="08f88-181">**Z 셸**: *~/.zshrc* 또는 *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="08f88-181">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
>
> <span data-ttu-id="08f88-182">셸에 적절한 원본 파일을 편집하고 `export DOTNET_ROOT=/snap/dotnet-sdk/current`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-182">Edit the appropriate source file for your shell and add `export DOTNET_ROOT=/snap/dotnet-sdk/current`.</span></span>

## <a name="tlsssl-certificate-errors"></a><span data-ttu-id="08f88-183">TLS/SSL 인증서 오류</span><span class="sxs-lookup"><span data-stu-id="08f88-183">TLS/SSL Certificate errors</span></span>

<span data-ttu-id="08f88-184">Snap을 통해 .NET이 설치될 경우, 일부 배포판에서는 .NET TLS/SSL 인증서가 발견되지 않을 수 있으며 `restore` 도중에 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-184">When .NET is installed through Snap, it's possible that on some distros the .NET TLS/SSL certificates may not be found and you may receive an error during `restore`:</span></span>

```bash
Processing post-creation actions...
Running 'dotnet restore' on /home/myhome/test/test.csproj...
  Restoring packages for /home/myhome/test/test.csproj...
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error : Unable to load the service index for source https://api.nuget.org/v3/index.json. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The SSL connection could not be established, see inner exception. [/home/myhome/test/test.csproj]
/snap/dotnet-sdk/27/sdk/2.2.103/NuGet.targets(114,5): error :   The remote certificate is invalid according to the validation procedure. [/home/myhome/test/test.csproj]
```

<span data-ttu-id="08f88-185">이 문제를 해결하려면 다음과 같은 몇 가지 환경 변수를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-185">To resolve this problem, set a few environment variables:</span></span>

```bash
export SSL_CERT_FILE=[path-to-certificate-file]
export SSL_CERT_DIR=/dev/null
```

<span data-ttu-id="08f88-186">인증서 위치는 배포판에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-186">The certificate location will vary by distro.</span></span> <span data-ttu-id="08f88-187">문제가 발생한 배포판의 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="08f88-187">Here are the locations for the distros where the issue has been experienced.</span></span>

| <span data-ttu-id="08f88-188">배포</span><span class="sxs-lookup"><span data-stu-id="08f88-188">Distribution</span></span> | <span data-ttu-id="08f88-189">위치</span><span class="sxs-lookup"><span data-stu-id="08f88-189">Location</span></span>                                            |
|--------------|-----------------------------------------------------|
| <span data-ttu-id="08f88-190">**Fedora**</span><span class="sxs-lookup"><span data-stu-id="08f88-190">**Fedora**</span></span>   | `/etc/pki/ca-trust/extracted/pem/tls-ca-bundle.pem` |
| <span data-ttu-id="08f88-191">**OpenSUSE**</span><span class="sxs-lookup"><span data-stu-id="08f88-191">**OpenSUSE**</span></span> | `/etc/ssl/ca-bundle.pem`                            |
| <span data-ttu-id="08f88-192">**Solus**</span><span class="sxs-lookup"><span data-stu-id="08f88-192">**Solus**</span></span>    | `/etc/ssl/certs/ca-certificates.crt`                |

## <a name="next-steps"></a><span data-ttu-id="08f88-193">다음 단계</span><span class="sxs-lookup"><span data-stu-id="08f88-193">Next steps</span></span>

- [<span data-ttu-id="08f88-194">.NET CLI에 대해 탭 완성 기능을 사용하도록 설정하는 방법</span><span class="sxs-lookup"><span data-stu-id="08f88-194">How to enable TAB completion for the .NET CLI</span></span>](../tools/enable-tab-autocomplete.md)
- [<span data-ttu-id="08f88-195">자습서: Visual Studio Code를 사용하여 .NET SDK에서 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="08f88-195">Tutorial: Create a console application with .NET SDK using Visual Studio Code</span></span>](../tutorials/with-visual-studio-code.md)
