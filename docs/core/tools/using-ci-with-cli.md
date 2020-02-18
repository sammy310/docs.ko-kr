---
title: .NET Core SDK 및 도구를 사용한 CI(연속 통합)
description: 연속 통합을 사용하여 빌드 서버에서 .NET Core SDK 및 해당 도구를 사용하는 방법을 알아봅니다.
ms.date: 05/18/2017
ms.openlocfilehash: bdb3913cbe588377d9fbee0f1c054e682629ac96
ms.sourcegitcommit: 9c54866bcbdc49dbb981dd55be9bbd0443837aa2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2020
ms.locfileid: "77215227"
---
# <a name="using-net-core-sdk-and-tools-in-continuous-integration-ci"></a><span data-ttu-id="6bc9f-103">.NET Core SDK 및 CI(연속 통합)의 도구 사용</span><span class="sxs-lookup"><span data-stu-id="6bc9f-103">Using .NET Core SDK and tools in Continuous Integration (CI)</span></span>

<span data-ttu-id="6bc9f-104">이 문서는 .NET Core SDK 및 빌드 서버의 도구를 사용하는 방법의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-104">This document outlines using the .NET Core SDK and its tools on a build server.</span></span> <span data-ttu-id="6bc9f-105">.NET Core 도구 집합은 개발자가 명령 프롬프트에 명령을 입력할 경우 대화형으로 작동하고 CI(연속 통합) 서버에서 빌드 스크립트가 실행될 경우 자동으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-105">The .NET Core toolset works both interactively, where a developer types commands at a command prompt, and automatically, where a Continuous Integration (CI) server runs a build script.</span></span> <span data-ttu-id="6bc9f-106">명령, 옵션, 입력 및 출력은 동일하고 도구를 취득하는 방법과 앱을 빌드하기 위한 시스템만 제공하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-106">The commands, options, inputs, and outputs are the same, and the only things you supply are a way to acquire the tooling and a system to build your app.</span></span> <span data-ttu-id="6bc9f-107">이 문서에서는 빌드 스크립트를 디자인 및 구성하는 방법에 대한 권장 사항과 함께 CI용 도구 취득에 대한 시나리오에 초점을 맞춥니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-107">This document focuses on scenarios of tool acquisition for CI with recommendations on how to design and structure your build scripts.</span></span>

## <a name="installation-options-for-ci-build-servers"></a><span data-ttu-id="6bc9f-108">CI 빌드 서버에 대한 설치 옵션</span><span class="sxs-lookup"><span data-stu-id="6bc9f-108">Installation options for CI build servers</span></span>

### <a name="using-the-native-installers"></a><span data-ttu-id="6bc9f-109">기본 설치 관리자 사용</span><span class="sxs-lookup"><span data-stu-id="6bc9f-109">Using the native installers</span></span>

<span data-ttu-id="6bc9f-110">기본 설치 관리자는 macOS, Linux 및 Windows에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-110">Native installers are available for macOS, Linux, and Windows.</span></span> <span data-ttu-id="6bc9f-111">설치 관리자는 빌드 서버에 대한 관리자(sudo) 액세스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-111">The installers require admin (sudo) access to the build server.</span></span> <span data-ttu-id="6bc9f-112">기본 설치 관리자를 사용하는 장점은 기본 설치 관리자는 도구를 실행하는 데 필요한 모든 기본 종속성을 설치한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-112">The advantage of using a native installer is that it installs all of the native dependencies required for the tooling to run.</span></span> <span data-ttu-id="6bc9f-113">기본 설치 관리자는 SDK의 시스템 차원 설치를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-113">Native installers also provide a system-wide installation of the SDK.</span></span>

<span data-ttu-id="6bc9f-114">macOS 사용자는 PKG 설치 관리자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-114">macOS users should use the PKG installers.</span></span> <span data-ttu-id="6bc9f-115">Linux에서는 피드 기반 패키지 관리자를 사용하거나(Ubuntu의 경우 apt-get, CentOS의 경우 yum), 패키지 자체를 사용할 수 있습니다(DEB 또는 RPM).</span><span class="sxs-lookup"><span data-stu-id="6bc9f-115">On Linux, there's a choice of using a feed-based package manager, such as apt-get for Ubuntu or yum for CentOS, or using the packages themselves, DEB or RPM.</span></span> <span data-ttu-id="6bc9f-116">Windows에서는 MSI 설치 관리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-116">On Windows, use the MSI installer.</span></span>

<span data-ttu-id="6bc9f-117">안정적인 최신 이진 파일은 [.NET 다운로드](https://dotnet.microsoft.com/download)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-117">The latest stable binaries are found at [.NET downloads](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="6bc9f-118">안정적이지 않을 수 있는 최신 시험판 도구를 사용하려면 [dotnet/core-sdk GitHub 리포지토리](https://github.com/dotnet/core-sdk#installers-and-binaries)에 제공된 링크를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-118">If you wish to use the latest (and potentially unstable) pre-release tooling, use the links provided at the [dotnet/core-sdk GitHub repository](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span> <span data-ttu-id="6bc9f-119">Linux 배포의 경우 `tar.gz` 보관(`tarballs`라고도 함)을 사용할 수 있습니다. 보관 내의 설치 스크립트를 사용하여 .NET Core를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-119">For Linux distributions, `tar.gz` archives (also known as `tarballs`) are available; use the installation scripts within the archives to install .NET Core.</span></span>

### <a name="using-the-installer-script"></a><span data-ttu-id="6bc9f-120">설치 관리자 스크립트 사용</span><span class="sxs-lookup"><span data-stu-id="6bc9f-120">Using the installer script</span></span>

<span data-ttu-id="6bc9f-121">설치 관리자 스크립트를 사용하면 관리자가 아닌 사용자도 빌드 서버에 설치하고 도구 취득을 쉽게 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-121">Using the installer script allows for non-administrative installation on your build server and easy automation for obtaining the tooling.</span></span> <span data-ttu-id="6bc9f-122">이 스크립트는 도구를 다운로드하고 사용을 위해 기본 또는 지정된 위치로 추출하는 과정을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-122">The script takes care of downloading the tooling and extracting it into a default or specified location for use.</span></span> <span data-ttu-id="6bc9f-123">또한 설치할 도구 버전을 지정하고 전체 SDK를 설치할지, 아니면 공유 런타임만 설치할지 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-123">You can also specify a version of the tooling that you wish to install and whether you want to install the entire SDK or only the shared runtime.</span></span>

<span data-ttu-id="6bc9f-124">원하는 SDK 버전을 가져와서 설치할 수 있도록 빌드 시작 시 설치 관리자 스크립트를 실행하도록 자동화됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-124">The installer script is automated to run at the start of the build to fetch and install the desired version of the SDK.</span></span> <span data-ttu-id="6bc9f-125">*원하는 버전*이란 프로젝트에서 빌드에 필요한 SDK 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-125">The *desired version* is whatever version of the SDK your projects require to build.</span></span> <span data-ttu-id="6bc9f-126">스크립트를 사용하여 서버의 로컬 디렉터리에 SDK를 설치하고, 설치된 위치에서 도구를 실행하고 나서, 빌드한 후 정리하거나 CI 서비스에서 정리하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-126">The script allows you to install the SDK in a local directory on the server, run the tools from the installed location, and then clean up (or let the CI service clean up) after the build.</span></span> <span data-ttu-id="6bc9f-127">이렇게 하면 전체 빌드 프로세스에 캡슐화 및 격리가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-127">This provides encapsulation and isolation to your entire build process.</span></span> <span data-ttu-id="6bc9f-128">설치 스크립트 참조는 [dotnet-install](dotnet-install-script.md) 문서에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-128">The installation script reference is found in the [dotnet-install](dotnet-install-script.md) article.</span></span>

> [!NOTE]
> <span data-ttu-id="6bc9f-129">**Azure DevOps Services**</span><span class="sxs-lookup"><span data-stu-id="6bc9f-129">**Azure DevOps Services**</span></span>
>
> <span data-ttu-id="6bc9f-130">설치 관리자 스크립트를 사용할 경우 기본 종속성은 자동으로 설치되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-130">When using the installer script, native dependencies aren't installed automatically.</span></span> <span data-ttu-id="6bc9f-131">운영 체제에 기본 종속성이 없는 경우 기본 종속성을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-131">You must install the native dependencies if the operating system doesn't have them.</span></span> <span data-ttu-id="6bc9f-132">자세한 내용은 [.NET Core 종속성 및 요구 사항](../install/dependencies.md?tabs=netcore30&pivots=os-linux)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-132">For more information, see [.NET Core dependencies and requirements](../install/dependencies.md?tabs=netcore30&pivots=os-linux).</span></span>

## <a name="ci-setup-examples"></a><span data-ttu-id="6bc9f-133">CI 설치 예제</span><span class="sxs-lookup"><span data-stu-id="6bc9f-133">CI setup examples</span></span>

<span data-ttu-id="6bc9f-134">이 섹션에서는 PowerShell 또는 bash 스크립트를 사용한 수동 설치에 대해 설명하고 여러 가지 SaaS(Software as a Service) CI 솔루션을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-134">This section describes a manual setup using a PowerShell or bash script, along with a description of several software as a service (SaaS) CI solutions.</span></span> <span data-ttu-id="6bc9f-135">설명되는 SaaS CI 솔루션은 [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) 및 [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index)입니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-135">The SaaS CI solutions covered are [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).</span></span>

### <a name="manual-setup"></a><span data-ttu-id="6bc9f-136">수동 설치</span><span class="sxs-lookup"><span data-stu-id="6bc9f-136">Manual setup</span></span>

<span data-ttu-id="6bc9f-137">각 SaaS 서비스에는 빌드 프로세스를 만들고 구성하기 위한 자체적인 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-137">Each SaaS service has its own methods for creating and configuring a build process.</span></span> <span data-ttu-id="6bc9f-138">나열된 것과 다른 SaaS 솔루션을 사용하거나 미리 패키지된 지원 이외의 사용자 지정이 필요한 경우 적어도 일부 수동 구성을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-138">If you use different SaaS solution than those listed or require customization beyond the pre-packaged support, you must perform at least some manual configuration.</span></span>

<span data-ttu-id="6bc9f-139">일반적으로 수동으로 설치하려면 특정 버전의 도구(또는 최신 야간 빌드의 도구)를 취득하고 빌드 스크립트를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-139">In general, a manual setup requires you to acquire a version of the tools (or the latest nightly builds of the tools) and run your build script.</span></span> <span data-ttu-id="6bc9f-140">PowerShell 또는 bash 스크립트를 사용하여 .NET Core 명령을 오케스트레이션하거나 빌드 프로세스의 개요를 설명하는 프로젝트 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-140">You can use a PowerShell or bash script to orchestrate the .NET Core commands or use a project file that outlines the build process.</span></span> <span data-ttu-id="6bc9f-141">[오케스트레이션 섹션](#orchestrating-the-build)에서 이러한 옵션을 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-141">The [orchestration section](#orchestrating-the-build) provides more detail on these options.</span></span>

<span data-ttu-id="6bc9f-142">수동 CI 빌드 서버 설치를 수행하는 스크립트를 만든 후 이를 개발 컴퓨터에서 사용하여 테스트 목적으로 코드를 로컬에 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-142">After you create a script that performs a manual CI build server setup, use it on your dev machine to build your code locally for testing purposes.</span></span> <span data-ttu-id="6bc9f-143">스트립트가 로컬에서 제대로 실행되는지 확인한 후 스크립트를 CI 빌드 서버에 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-143">Once you confirm that the script is running well locally, deploy it to your CI build server.</span></span> <span data-ttu-id="6bc9f-144">비교적 간단한 PowerShell 스크립트는 .NET Core SDK를 취득하고 Windows 빌드 서버에 설치하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-144">A relatively simple PowerShell script demonstrates how to obtain the .NET Core SDK and install it on a Windows build server:</span></span>

```powershell
$ErrorActionPreference="Stop"
$ProgressPreference="SilentlyContinue"

# $LocalDotnet is the path to the locally-installed SDK to ensure the
#   correct version of the tools are executed.
$LocalDotnet=""
# $InstallDir and $CliVersion variables can come from options to the
#   script.
$InstallDir = "./cli-tools"
$CliVersion = "1.0.1"

# Test the path provided by $InstallDir to confirm it exists. If it
#   does, it's removed. This is not strictly required, but it's a
#   good way to reset the environment.
if (Test-Path $InstallDir)
{
    rm -Recurse $InstallDir
}
New-Item -Type "directory" -Path $InstallDir

Write-Host "Downloading the CLI installer..."

# Use the Invoke-WebRequest PowerShell cmdlet to obtain the
#   installation script and save it into the installation directory.
Invoke-WebRequest `
    -Uri "https://dot.net/v1/dotnet-install.ps1" `
    -OutFile "$InstallDir/dotnet-install.ps1"

Write-Host "Installing the CLI requested version ($CliVersion) ..."

# Install the SDK of the version specified in $CliVersion into the
#   specified location ($InstallDir).
& $InstallDir/dotnet-install.ps1 -Version $CliVersion `
    -InstallDir $InstallDir

Write-Host "Downloading and installation of the SDK is complete."

# $LocalDotnet holds the path to dotnet.exe for future use by the
#   script.
$LocalDotnet = "$InstallDir/dotnet"

# Run the build process now. Implement your build script here.
```

<span data-ttu-id="6bc9f-145">스크립트 종료 시 빌드 프로세스에 대한 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-145">You provide the implementation for your build process at the end of the script.</span></span> <span data-ttu-id="6bc9f-146">스크립트가 도구를 취득하고 나서 빌드 프로세스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-146">The script acquires the tools and then executes your build process.</span></span> <span data-ttu-id="6bc9f-147">UNIX 컴퓨터에서는 다음 bash 스크립트가 PowerShell 스크립트에 설명된 작업을 비슷한 방식으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-147">For UNIX machines, the following bash script performs the actions described in the PowerShell script in a similar manner:</span></span>

```bash
#!/bin/bash
INSTALLDIR="cli-tools"
CLI_VERSION=1.0.1
DOWNLOADER=$(which curl)
if [ -d "$INSTALLDIR" ]
then
    rm -rf "$INSTALLDIR"
fi
mkdir -p "$INSTALLDIR"
echo Downloading the CLI installer.
$DOWNLOADER https://dot.net/v1/dotnet-install.sh > "$INSTALLDIR/dotnet-install.sh"
chmod +x "$INSTALLDIR/dotnet-install.sh"
echo Installing the CLI requested version $CLI_VERSION. Please wait, installation may take a few minutes.
"$INSTALLDIR/dotnet-install.sh" --install-dir "$INSTALLDIR" --version $CLI_VERSION
if [ $? -ne 0 ]
then
    echo Download of $CLI_VERSION version of the CLI failed. Exiting now.
    exit 0
fi
echo The CLI has been installed.
LOCALDOTNET="$INSTALLDIR/dotnet"
# Run the build process now. Implement your build script here.
```

### <a name="travis-ci"></a><span data-ttu-id="6bc9f-148">Travis CI</span><span class="sxs-lookup"><span data-stu-id="6bc9f-148">Travis CI</span></span>

<span data-ttu-id="6bc9f-149">`csharp` 언어와 `dotnet` 키를 사용하여 .NET Core SDK를 설치하도록 [Travis CI](https://travis-ci.org/)를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-149">You can configure [Travis CI](https://travis-ci.org/) to install the .NET Core SDK using the `csharp` language and the `dotnet` key.</span></span> <span data-ttu-id="6bc9f-150">자세한 내용은 [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/)(C#, F# 또는 Visual Basic 프로젝트 빌드)에서 공식 Travis CI 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-150">For more information, see the official Travis CI docs on [Building a C#, F#, or Visual Basic Project](https://docs.travis-ci.com/user/languages/csharp/).</span></span> <span data-ttu-id="6bc9f-151">Travis CI 정보에 액세스할 때 커뮤니티에서 유지 관리되는 `language: csharp` 언어 식별자가 F# 및 Mono를 포함한 모든 .NET 언어에 적용된다는 것에 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-151">Note as you access the Travis CI information that the community-maintained `language: csharp` language identifier works for all .NET languages, including F#, and Mono.</span></span>

<span data-ttu-id="6bc9f-152">Travis CI는 앱에 대한 빌드 조합을 설명하기 위해 런타임, 환경 및 제외/포함의 조합을 지정하는 *빌드 행렬*에서 macOS 및 Linux 작업을 둘 다 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-152">Travis CI runs both macOS and Linux jobs in a *build matrix*, where you specify a combination of runtime, environment, and exclusions/inclusions to cover your build combinations for your app.</span></span> <span data-ttu-id="6bc9f-153">자세한 내용은 Travis CI 설명서의 [빌드 사용자 지정](https://docs.travis-ci.com/user/customizing-the-build) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-153">For more information, see the [Customizing the Build](https://docs.travis-ci.com/user/customizing-the-build) article in the Travis CI documentation.</span></span> <span data-ttu-id="6bc9f-154">MSBuild 기반 도구의 경우 LTS(1.0.x) 및 Current(1.1.x) 런타임이 패키지에 포함되므로 SDK를 설치하면 빌드에 필요한 모든 것이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-154">The MSBuild-based tools include the LTS (1.0.x) and Current (1.1.x) runtimes in the package; so by installing the SDK, you receive everything you need to build.</span></span>

### <a name="appveyor"></a><span data-ttu-id="6bc9f-155">AppVeyor</span><span class="sxs-lookup"><span data-stu-id="6bc9f-155">AppVeyor</span></span>

<span data-ttu-id="6bc9f-156">[AppVeyor](https://www.appveyor.com/)는 `Visual Studio 2017` 빌드 작업자 이미지를 사용하여 .NET Core 1.0.1 SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-156">[AppVeyor](https://www.appveyor.com/) installs the .NET Core 1.0.1 SDK with the `Visual Studio 2017` build worker image.</span></span> <span data-ttu-id="6bc9f-157">각기 다른 버전의 .NET Core SDK가 포함된 여러 빌드 이미지를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-157">Other build images with different versions of the .NET Core SDK are available.</span></span> <span data-ttu-id="6bc9f-158">자세한 내용은 [appveyor.yml 예제](https://github.com/dotnet/docs/blob/master/appveyor.yml) 및 AppVeyor 문서의 [빌드 작업자 이미지](https://www.appveyor.com/docs/build-environment/#build-worker-images) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-158">For more information, see the [appveyor.yml example](https://github.com/dotnet/docs/blob/master/appveyor.yml) and the [Build worker images](https://www.appveyor.com/docs/build-environment/#build-worker-images) article in the AppVeyor docs.</span></span>

<span data-ttu-id="6bc9f-159">.NET Core SDK 이진 파일은 설치 스크립트를 통해 하위 디렉터리로 다운로드되어 압축이 풀리고 `PATH` 환경 변수에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-159">The .NET Core SDK binaries are downloaded and unzipped in a subdirectory using the install script, and then they're added to the `PATH` environment variable.</span></span> <span data-ttu-id="6bc9f-160">빌드 행렬을 추가하여 .NET Core SDK의 여러 버전으로 통합 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-160">Add a build matrix to run integration tests with multiple versions of the .NET Core SDK:</span></span>

```yaml
environment:
  matrix:
    - CLI_VERSION: 1.0.1
    - CLI_VERSION: Latest

install:
  # See appveyor.yml example for install script
```

### <a name="azure-devops-services"></a><span data-ttu-id="6bc9f-161">Azure DevOps Services</span><span class="sxs-lookup"><span data-stu-id="6bc9f-161">Azure DevOps Services</span></span>

<span data-ttu-id="6bc9f-162">다음 방법 중 하나를 사용하여 .NET Core 프로젝트를 빌드하도록 Azure DevOps Services를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-162">Configure Azure DevOps Services to build .NET Core projects using one of these approaches:</span></span>

1. <span data-ttu-id="6bc9f-163">명령을 사용하여 [수동 설치 단계](#manual-setup)에서 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-163">Run the script from the [manual setup step](#manual-setup) using your commands.</span></span>
1. <span data-ttu-id="6bc9f-164">.NET Core 도구를 사용하도록 구성된 여러 가지 Azure DevOps Services 기본 제공 빌드 작업으로 구성된 빌드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-164">Create a build composed of several Azure DevOps Services built-in build tasks that are configured to use .NET Core tools.</span></span>

<span data-ttu-id="6bc9f-165">두 가지 솔루션 모두 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-165">Both solutions are valid.</span></span> <span data-ttu-id="6bc9f-166">수동 설치 스크립트를 사용하면 도구를 빌드의 일부로 다운로드한 후 취득하는 도구 버전을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-166">Using a manual setup script, you control the version of the tools that you receive, since you download them as part of the build.</span></span> <span data-ttu-id="6bc9f-167">빌드는 만들어야 하는 스크립트에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-167">The build is run from a script that you must create.</span></span> <span data-ttu-id="6bc9f-168">이 문서에서는 수동 옵션만 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-168">This article only covers the manual option.</span></span> <span data-ttu-id="6bc9f-169">Azure DevOps Services 빌드 작업을 사용하여 빌드를 작성하는 방법에 대한 자세한 내용은 [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-169">For more information on composing a build with Azure DevOps Services build tasks, see the [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index) documentation.</span></span>

<span data-ttu-id="6bc9f-170">Azure DevOps Services에서 수동 설치 스크립트를 사용하려면 새 빌드 정의를 만들고 빌드 단계에서 실행할 스크립트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-170">To use a manual setup script in Azure DevOps Services, create a new build definition and specify the script to run for the build step.</span></span> <span data-ttu-id="6bc9f-171">이 작업에는 Azure DevOps Services 사용자 인터페이스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-171">This is accomplished using the Azure DevOps Services user interface:</span></span>

1. <span data-ttu-id="6bc9f-172">먼저 새 빌드 정의를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-172">Start by creating a new build definition.</span></span> <span data-ttu-id="6bc9f-173">만들려는 빌드 종류를 정의하는 옵션을 제공하는 화면이 표시되면 **비어 있음** 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-173">Once you reach the screen that provides you an option to define what kind of a build you wish to create, select the **Empty** option.</span></span>

   ![빈 빌드 정의 선택](./media/using-ci-with-cli/select-empty-build-definition.png)

1. <span data-ttu-id="6bc9f-175">빌드할 리포지토리를 구성한 후 빌드 정의로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-175">After configuring the repository to build, you're directed to the build definitions.</span></span> <span data-ttu-id="6bc9f-176">**빌드 단계 추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-176">Select **Add build step**:</span></span>

   ![빌드 단계 추가](./media/using-ci-with-cli/add-build-step.png)

1. <span data-ttu-id="6bc9f-178">**작업 카탈로그**가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-178">You're presented with the **Task catalog**.</span></span> <span data-ttu-id="6bc9f-179">카탈로그에는 빌드에서 사용할 작업이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-179">The catalog contains tasks that you use in the build.</span></span> <span data-ttu-id="6bc9f-180">스크립트가 준비되면 **PowerShell: PowerShell 스크립트 실행**에 대해 추가 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-180">Since you have a script, select the **Add** button for **PowerShell: Run a PowerShell script**.</span></span>

   ![PowerShell 스크립트 단계 추가](./media/using-ci-with-cli/add-powershell-script.png)

1. <span data-ttu-id="6bc9f-182">빌드 단계를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-182">Configure the build step.</span></span> <span data-ttu-id="6bc9f-183">빌드 중인 리포지토리에서 스크립트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-183">Add the script from the repository that you're building:</span></span>

   ![실행할 PowerShell 스크립트 지정](./media/using-ci-with-cli/powershell-script-path.png)

## <a name="orchestrating-the-build"></a><span data-ttu-id="6bc9f-185">빌드 오케스트레이션</span><span class="sxs-lookup"><span data-stu-id="6bc9f-185">Orchestrating the build</span></span>

<span data-ttu-id="6bc9f-186">이 문서의 대부분은 .NET Core를 사용하여 코드를 오케스트레이션하거나 *실제로 빌드*하는 방법에 대한 설명 없이 .NET Core 도구를 취득하고 다양한 CI 서비스를 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-186">Most of this document describes how to acquire the .NET Core tools and configure various CI services without providing information on how to orchestrate, or *actually build*, your code with .NET Core.</span></span> <span data-ttu-id="6bc9f-187">빌드 프로세스를 구성하는 방법 선택은 여기에서 일반적으로 설명할 수 없는 다양한 요소에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-187">The choices on how to structure the build process depend on many factors that can't be covered in a general way here.</span></span> <span data-ttu-id="6bc9f-188">각 기술을 사용하여 빌드를 오케스트레이션하는 방법에 대한 자세한 내용은 [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/) 및 [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index)의 문서 세트에 제공된 리소스 및 샘플을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-188">For more information on orchestrating your builds with each technology, explore the resources and samples provided in the documentation sets of [Travis CI](https://travis-ci.org/), [AppVeyor](https://www.appveyor.com/), and [Azure Pipelines](https://docs.microsoft.com/azure/devops/pipelines/index).</span></span>

<span data-ttu-id="6bc9f-189">.NET Core 도구를 사용하여 .NET Core 코드에 대한 빌드 프로세스를 구성할 때 적용할 두 가지 일반적인 방법에서는 MSBuild를 직접 사용하거나 .NET Core 명령줄 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-189">Two general approaches that you take in structuring the build process for .NET Core code using the .NET Core tools are using MSBuild directly or using the .NET Core command-line commands.</span></span> <span data-ttu-id="6bc9f-190">어떤 방법을 적용해야 하는지는 방법에 대한 숙련도 및 복잡성의 절충 조건에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-190">Which approach you should take is determined by your comfort level with the approaches and trade-offs in complexity.</span></span> <span data-ttu-id="6bc9f-191">MSBuild는 빌드 프로세스를 작업 및 대상으로 표시하는 기능을 제공하지만 MSBuild 프로젝트 파일 구문 학습의 복잡성이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-191">MSBuild provides you the ability to express your build process as tasks and targets, but it comes with the added complexity of learning MSBuild project file syntax.</span></span> <span data-ttu-id="6bc9f-192">.NET Core 명령줄 도구를 사용하는 것이 더 간편하지만 `bash` 또는 PowerShell 같은 스크립팅 언어로 오케스트레이션 논리를 작성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6bc9f-192">Using the .NET Core command-line tools is perhaps simpler, but it requires you to write orchestration logic in a scripting language like `bash` or PowerShell.</span></span>

## <a name="see-also"></a><span data-ttu-id="6bc9f-193">참조</span><span class="sxs-lookup"><span data-stu-id="6bc9f-193">See also</span></span>

- [<span data-ttu-id="6bc9f-194">.NET 다운로드 - Linux</span><span class="sxs-lookup"><span data-stu-id="6bc9f-194">.NET downloads - Linux</span></span>](https://dotnet.microsoft.com/download?initial-os=linux)
