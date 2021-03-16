---
title: dotnet 설치 스크립트
description: .NET SDK 및 공유 런타임을 설치하는 dotnet-install 스크립트에 대해 알아봅니다.
ms.date: 09/22/2020
ms.openlocfilehash: 51482ca70d08d86e02a493f1da49b056fed8d11c
ms.sourcegitcommit: bdbf6472de867a0a11aaa5b9384a2506c24f27d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "102206689"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="e6294-103">dotnet-install 스크립트 참조</span><span class="sxs-lookup"><span data-stu-id="e6294-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="e6294-104">이름</span><span class="sxs-lookup"><span data-stu-id="e6294-104">Name</span></span>

<span data-ttu-id="e6294-105">`dotnet-install.ps1` | `dotnet-install.sh` - .NET SDK 및 공유 런타임을 설치하는 데 사용되는 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET SDK and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="e6294-106">개요</span><span class="sxs-lookup"><span data-stu-id="e6294-106">Synopsis</span></span>

<span data-ttu-id="e6294-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="e6294-107">Windows:</span></span>

```powershell
dotnet-install.ps1 [-Architecture <ARCHITECTURE>] [-AzureFeed]
    [-Channel <CHANNEL>] [-DryRun] [-FeedCredential]
    [-InstallDir <DIRECTORY>] [-JSonFile <JSONFILE>]
    [-NoCdn] [-NoPath] [-ProxyAddress] [-ProxyBypassList <LIST_OF_URLS>]
    [-ProxyUseDefaultCredentials] [-Runtime <RUNTIME>]
    [-SkipNonVersionedFiles] [-UncachedFeed] [-Verbose]
    [-Version <VERSION>]

Get-Help ./dotnet-install.ps1
```

<span data-ttu-id="e6294-108">Linux/macOS:</span><span class="sxs-lookup"><span data-stu-id="e6294-108">Linux/macOS:</span></span>

```bash
dotnet-install.sh  [--architecture <ARCHITECTURE>] [--azure-feed]
    [--channel <CHANNEL>] [--dry-run] [--feed-credential]
    [--install-dir <DIRECTORY>] [--jsonfile <JSONFILE>]
    [--no-cdn] [--no-path] [--runtime <RUNTIME>] [--runtime-id <RID>]
    [--skip-non-versioned-files] [--uncached-feed] [--verbose]
    [--version <VERSION>]

dotnet-install.sh --help
```

<span data-ttu-id="e6294-109">또한 bash 스크립트는 PowerShell 스위치를 읽으므로 Linux/macOS 시스템에서 스크립트와 함께 PowerShell 스위치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-109">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

## <a name="description"></a><span data-ttu-id="e6294-110">설명</span><span class="sxs-lookup"><span data-stu-id="e6294-110">Description</span></span>

<span data-ttu-id="e6294-111">`dotnet-install` 스크립트는 .NET CLI 및 공유 런타임을 포함하는 .NET SDK의 비관리자 설치를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-111">The `dotnet-install` scripts perform a non-admin installation of the .NET SDK, which includes the .NET CLI and the shared runtime.</span></span> <span data-ttu-id="e6294-112">다음과 같은 두 가지 스크립트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-112">There are two scripts:</span></span>

* <span data-ttu-id="e6294-113">Windows에서 작동하는 PowerShell 스크립트</span><span class="sxs-lookup"><span data-stu-id="e6294-113">A PowerShell script that works on Windows.</span></span>
* <span data-ttu-id="e6294-114">Linux/macOS에서 작동하는 bash 스크립트</span><span class="sxs-lookup"><span data-stu-id="e6294-114">A bash script that works on Linux/macOS.</span></span>

> [!NOTE]
> <span data-ttu-id="e6294-115">.NET은 원격 분석 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-115">.NET collects telemetry data.</span></span> <span data-ttu-id="e6294-116">옵트아웃하는 방법에 관한 자세한 내용은 [.NET SDK 원격 분석](telemetry.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6294-116">To learn more and how to opt out, see [.NET SDK telemetry](telemetry.md).</span></span>

### <a name="purpose"></a><span data-ttu-id="e6294-117">용도</span><span class="sxs-lookup"><span data-stu-id="e6294-117">Purpose</span></span>

 <span data-ttu-id="e6294-118">이 스크립트는 다음과 같은 CI(연속 통합) 시나리오에 사용하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-118">The intended use of the scripts is for Continuous Integration (CI) scenarios, where:</span></span>

* <span data-ttu-id="e6294-119">사용자 조작 및 관리자 권한 없이 SDK를 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-119">The SDK needs to be installed without user interaction and without admin rights.</span></span>
* <span data-ttu-id="e6294-120">SDK 설치를 여러 CI 실행 간에 유지할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-120">The SDK installation doesn't need to persist across multiple CI runs.</span></span>

  <span data-ttu-id="e6294-121">일반적인 이벤트 시퀀스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-121">The typical sequence of events:</span></span>
  * <span data-ttu-id="e6294-122">CI가 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-122">CI is triggered.</span></span>
  * <span data-ttu-id="e6294-123">CI에서 이러한 스크립트 중 하나를 사용하여 SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-123">CI installs the SDK using one of these scripts.</span></span>
  * <span data-ttu-id="e6294-124">CI에서 작업을 완료하고 SDK 설치를 비롯해 임시 데이터를 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-124">CI finishes its work and clears temporary data including the SDK installation.</span></span>

<span data-ttu-id="e6294-125">개발 환경을 설정하거나 앱을 실행하려면 이러한 스크립트가 아니라 설치 관리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-125">To set up a development environment or to run apps, use the installers rather than these scripts.</span></span>

### <a name="recommended-version"></a><span data-ttu-id="e6294-126">추천 버전</span><span class="sxs-lookup"><span data-stu-id="e6294-126">Recommended version</span></span>

<span data-ttu-id="e6294-127">안정적인 버전의 스크립트를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-127">We recommend that you use the stable version of the scripts:</span></span>

- <span data-ttu-id="e6294-128">Bash(Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span><span class="sxs-lookup"><span data-stu-id="e6294-128">Bash (Linux/macOS): <https://dot.net/v1/dotnet-install.sh></span></span>
- <span data-ttu-id="e6294-129">PowerShell(Windows): <https://dot.net/v1/dotnet-install.ps1></span><span class="sxs-lookup"><span data-stu-id="e6294-129">PowerShell (Windows): <https://dot.net/v1/dotnet-install.ps1></span></span>

### <a name="script-behavior"></a><span data-ttu-id="e6294-130">스크립트 동작</span><span class="sxs-lookup"><span data-stu-id="e6294-130">Script behavior</span></span>

<span data-ttu-id="e6294-131">두 스크립트의 동작은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-131">Both scripts have the same behavior.</span></span> <span data-ttu-id="e6294-132">스크립트는 CLI 빌드 저장 위치에서 ZIP/tarball 파일을 다운로드하여 기본 위치나 `-InstallDir|--install-dir`로 지정한 위치에 설치를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-132">They download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span>

<span data-ttu-id="e6294-133">기본적으로 설치 스크립트는 SDK를 다운로드하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-133">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="e6294-134">공유 런타임만 가져오려는 경우 `-Runtime|--runtime` 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-134">If you wish to only obtain the shared runtime, specify the `-Runtime|--runtime` argument.</span></span>

<span data-ttu-id="e6294-135">기본적으로 스크립트는 현재 세션에 대한 $PATH에 설치 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-135">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="e6294-136">`-NoPath|--no-path` 인수를 지정하여 이 기본 동작을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-136">Override this default behavior by specifying the `-NoPath|--no-path` argument.</span></span> <span data-ttu-id="e6294-137">스크립트는 `DOTNET_ROOT` 환경 변수를 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-137">The script doesn't set the `DOTNET_ROOT` environment variable.</span></span>

<span data-ttu-id="e6294-138">스크립트를 실행하기 전에 필요한 모든 [종속성](../install/windows.md#dependencies)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="e6294-138">Before running the script, install the required [dependencies](../install/windows.md#dependencies).</span></span>

<span data-ttu-id="e6294-139">`-Version|--version` 인수를 사용하여 특정 버전을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-139">You can install a specific version using the `-Version|--version` argument.</span></span> <span data-ttu-id="e6294-140">버전은 `2.1.0`과 같이 세 부분으로 구성된 버전 번호로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-140">The version must be specified as a three-part version number, such as `2.1.0`.</span></span> <span data-ttu-id="e6294-141">버전을 지정하지 않은 경우 스크립트는 `latest` 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-141">If the version isn't specified, the script installs the `latest` version.</span></span>

<span data-ttu-id="e6294-142">설치 스크립트는 Windows에서 레지스트리를 업데이트하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-142">The install scripts do not update the registry on Windows.</span></span> <span data-ttu-id="e6294-143">단지 압축된 이진 파일을 다운로드하여 폴더에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-143">They just download the zipped binaries and copy them to a folder.</span></span> <span data-ttu-id="e6294-144">레지스트리 키 값을 업데이트하려면 .NET 설치 관리자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-144">If you want registry key values to be updated, use the .NET installers.</span></span>

## <a name="options"></a><span data-ttu-id="e6294-145">옵션</span><span class="sxs-lookup"><span data-stu-id="e6294-145">Options</span></span>

- **`-Architecture|--architecture <ARCHITECTURE>`**

  <span data-ttu-id="e6294-146">설치할 .NET 이진 파일의 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-146">Architecture of the .NET binaries to install.</span></span> <span data-ttu-id="e6294-147">가능한 값은 `<auto>`, `amd64`, `x64`, `x86`, `arm64` 및 `arm`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-147">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="e6294-148">기본값은 현재 실행 중인 OS 아키텍처를 나타내는 `<auto>`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-148">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-AzureFeed|--azure-feed`**

  <span data-ttu-id="e6294-149">설치 관리자에 대한 Azure 피드의 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-149">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="e6294-150">이 값은 변경하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-150">We recommended that you don't change this value.</span></span> <span data-ttu-id="e6294-151">기본값은 `https://dotnetcli.azureedge.net/dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-151">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-Channel|--channel <CHANNEL>`**

  <span data-ttu-id="e6294-152">설치에 대한 소스 채널을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-152">Specifies the source channel for the installation.</span></span> <span data-ttu-id="e6294-153">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-153">The possible values are:</span></span>

  - <span data-ttu-id="e6294-154">`Current` - 최신 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-154">`Current` - Most current release.</span></span>
  - <span data-ttu-id="e6294-155">`LTS` - 장기 지원 채널(지원되는 최신 릴리스)입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-155">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="e6294-156">특정 릴리스를 나타내는 X.Y 형식의 두 부분으로 된 버전입니다(예: `2.1` 또는 `3.0`).</span><span class="sxs-lookup"><span data-stu-id="e6294-156">Two-part version in X.Y format representing a specific release (for example, `2.1` or `3.0`).</span></span>
  - <span data-ttu-id="e6294-157">예를 들어 분기 이름은 `release/3.1.1xx` 또는 `master`(야간 릴리스의 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-157">Branch name: for example, `release/3.1.1xx` or `master` (for nightly releases).</span></span> <span data-ttu-id="e6294-158">미리 보기 채널에서 버전을 설치하려면 이 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-158">Use this option to install a version from a preview channel.</span></span> <span data-ttu-id="e6294-159">[설치 관리자 및 이진 파일](https://github.com/dotnet/core-sdk#installers-and-binaries)에 나열된 채널 이름을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-159">Use the name of the channel as listed in [Installers and Binaries](https://github.com/dotnet/core-sdk#installers-and-binaries).</span></span>

  <span data-ttu-id="e6294-160">기본값은 `LTS`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-160">The default value is `LTS`.</span></span> <span data-ttu-id="e6294-161">.NET 지원 채널에 대한 자세한 내용은 [.NET 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e6294-161">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-DryRun|--dry-run`**

  <span data-ttu-id="e6294-162">설정하면 스크립트에서 설치를 수행하지는 않지만,</span><span class="sxs-lookup"><span data-stu-id="e6294-162">If set, the script won't perform the installation.</span></span> <span data-ttu-id="e6294-163">대신 현재 요청된 버전의 .NET CLI를 일관되게 설치하기 위해 사용할 명령줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-163">Instead, it displays what command line to use to consistently install the currently requested version of the .NET CLI.</span></span> <span data-ttu-id="e6294-164">예를 들어 `latest` 버전을 지정하면 빌드 스크립트에서 이 명령을 결정적으로 사용할 수 있도록 특정 버전에 대한 링크를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-164">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="e6294-165">또한 직접 설치하거나 다운로드하는 것을 선호하는 경우 이진 파일 위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-165">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-FeedCredential|--feed-credential`**

  <span data-ttu-id="e6294-166">Azure 피드에 추가할 쿼리 문자열로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-166">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="e6294-167">public이 아닌 Blob 스토리지 계정을 사용하도록 URL을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-167">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`--help`**

  <span data-ttu-id="e6294-168">스크립트에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-168">Prints out help for the script.</span></span> <span data-ttu-id="e6294-169">Bash 스크립트에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-169">Applies only to bash script.</span></span> <span data-ttu-id="e6294-170">PowerShell의 경우 `Get-Help ./dotnet-install.ps1`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-170">For PowerShell, use `Get-Help ./dotnet-install.ps1`.</span></span>

- **`-InstallDir|--install-dir <DIRECTORY>`**

  <span data-ttu-id="e6294-171">설치 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-171">Specifies the installation path.</span></span> <span data-ttu-id="e6294-172">디렉터리가 없을 경우 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-172">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="e6294-173">기본값은 *%LocalAppData%\Microsoft\dotnet*(Windows) 또는 */usr/share/dotnet*(Linux/macOS)입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-173">The default value is *%LocalAppData%\Microsoft\dotnet* on Windows and */usr/share/dotnet* on Linux/macOS.</span></span> <span data-ttu-id="e6294-174">이진 파일은 이 디렉터리에 바로 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-174">Binaries are placed directly in this directory.</span></span>

- **`-JSonFile|--jsonfile <JSONFILE>`**

  <span data-ttu-id="e6294-175">SDK 버전을 확인하는 데 사용되는 [global.json](global-json.md) 파일의 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-175">Specifies a path to a [global.json](global-json.md) file that will be used to determine the SDK version.</span></span> <span data-ttu-id="e6294-176">*global.json* 파일에 `sdk:version`의 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-176">The *global.json* file must have a value for `sdk:version`.</span></span>

- **`-NoCdn|--no-cdn`**

  <span data-ttu-id="e6294-177">[Azure CDN(Content Delivery Network)](/azure/cdn/cdn-overview)에서 다운로드할 수 없도록 설정하고 캐시되지 않은 피드를 바로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-177">Disables downloading from the [Azure Content Delivery Network (CDN)](/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-NoPath|--no-path`**

  <span data-ttu-id="e6294-178">설정하면 설치 폴더를 현재 세션의 경로로 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-178">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="e6294-179">기본적으로 스크립트는 PATH를 수정하므로 설치 후 바로 .NET CLI를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-179">By default, the script modifies the PATH, which makes the .NET CLI available immediately after install.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="e6294-180">설정된 경우 설치 관리자에서 웹 요청을 만들 때 프록시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-180">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="e6294-181">(Windows에만 유효함)</span><span class="sxs-lookup"><span data-stu-id="e6294-181">(Only valid for Windows.)</span></span>

- **`-ProxyBypassList <LIST_OF_URLS>`**

  <span data-ttu-id="e6294-182">`ProxyAddress`를 사용하여 설정하는 경우 프록시를 우회하는 쉼표로 구분된 URL 목록을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-182">If set with `ProxyAddress`, provides a list of comma-separated urls that will bypass the proxy.</span></span> <span data-ttu-id="e6294-183">(Windows에만 유효함)</span><span class="sxs-lookup"><span data-stu-id="e6294-183">(Only valid for Windows.)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="e6294-184">설정하면 설치 관리자가 프록시 주소를 사용할 때 현재 사용자의 자격 증명을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-184">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="e6294-185">(Windows에만 유효함)</span><span class="sxs-lookup"><span data-stu-id="e6294-185">(Only valid for Windows.)</span></span>

- **`-Runtime|--runtime <RUNTIME>`**

  <span data-ttu-id="e6294-186">전체 SDK가 아닌 공유 런타임만 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-186">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="e6294-187">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-187">The possible values are:</span></span>

  - <span data-ttu-id="e6294-188">`dotnet` - `Microsoft.NETCore.App` 공유 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-188">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="e6294-189">`aspnetcore` - `Microsoft.AspNetCore.App` 공유 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-189">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>
  - <span data-ttu-id="e6294-190">`windowsdesktop` - `Microsoft.WindowsDesktop.App` 공유 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-190">`windowsdesktop` - the `Microsoft.WindowsDesktop.App` shared runtime.</span></span>

- <span data-ttu-id="e6294-191">**`--runtime-id <RID>` [사용되지 않음]**</span><span class="sxs-lookup"><span data-stu-id="e6294-191">**`--runtime-id <RID>` [Deprecated]**</span></span>

  <span data-ttu-id="e6294-192">도구가 설치되는 [런타임 식별자](../rid-catalog.md)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-192">Specifies the [runtime identifier](../rid-catalog.md) for which the tools are being installed.</span></span> <span data-ttu-id="e6294-193">휴대용 Linux에 `linux-x64`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-193">Use `linux-x64` for portable Linux.</span></span> <span data-ttu-id="e6294-194">Linux/macOS 및 .NET Core 2.1 이전 버전에서만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-194">(Only valid for Linux/macOS and for versions earlier than .NET Core 2.1.)</span></span>

  **`--os <OPERATING_SYSTEM>`**

  <span data-ttu-id="e6294-195">도구를 설치할 운영 체제를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-195">Specifies the operating system for which the tools are being installed.</span></span> <span data-ttu-id="e6294-196">가능한 값은 `osx`, `linux`, `linux-musl`, `freebsd`, `rhel.6`입니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-196">Possible values are: `osx`, `linux`, `linux-musl`, `freebsd`, `rhel.6`.</span></span> <span data-ttu-id="e6294-197">.NET Core 2.1 이상에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-197">(Valid for .NET Core 2.1 and later.)</span></span>

  <span data-ttu-id="e6294-198">매개 변수는 선택 사항이며 스크립트로 검색된 운영 체제를 재정의해야 하는 경우에만 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-198">The parameter is optional and should only be used when it's required to override the operating system that is detected by the script.</span></span>

- **`-SharedRuntime|--shared-runtime`**

  > [!NOTE]
  > <span data-ttu-id="e6294-199">이 매개 변수는 더 이상 사용되지 않으며 스크립트의 이후 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-199">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="e6294-200">대신 `-Runtime|--runtime` 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-200">The recommended alternative is the `-Runtime|--runtime` option.</span></span>

  <span data-ttu-id="e6294-201">전체 SDK가 아니라 공유 런타임 비트만 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-201">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="e6294-202">이 옵션은 `-Runtime|--runtime dotnet`을 지정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-202">This option is equivalent to specifying `-Runtime|--runtime dotnet`.</span></span>

- **`-SkipNonVersionedFiles|--skip-non-versioned-files`**

  <span data-ttu-id="e6294-203">*dotnet.exe* 와 같은 버전이 없는 파일이 있을 경우 해당 파일의 설치를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-203">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-UncachedFeed|--uncached-feed`**

  <span data-ttu-id="e6294-204">이 설치 관리자가 사용하는 캐시되지 않은 피드의 URL을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-204">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="e6294-205">이 값은 변경하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-205">We recommended that you don't change this value.</span></span>

- **`-Verbose|--verbose`**

  <span data-ttu-id="e6294-206">진단 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-206">Displays diagnostics information.</span></span>

- **`-Version|--version <VERSION>`**

  <span data-ttu-id="e6294-207">특정 빌드 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-207">Represents a specific build version.</span></span> <span data-ttu-id="e6294-208">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-208">The possible values are:</span></span>

  - <span data-ttu-id="e6294-209">`latest` - 채널의 최신 빌드입니다(`-Channel` 옵션과 함께 사용됨).</span><span class="sxs-lookup"><span data-stu-id="e6294-209">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="e6294-210">특정 빌드 버전을 나타내는 X.Y.Z 형식의 세 부분으로 구성된 버전이며 `-Channel` 옵션을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-210">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="e6294-211">예를 들어 `2.0.0-preview2-006120`을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e6294-211">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="e6294-212">지정하지 않으면 `-Version`은 기본값인 `latest`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-212">If not specified, `-Version` defaults to `latest`.</span></span>

## <a name="examples"></a><span data-ttu-id="e6294-213">예</span><span class="sxs-lookup"><span data-stu-id="e6294-213">Examples</span></span>

- <span data-ttu-id="e6294-214">기본 위치에 최신 LTS(장기 지원) 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-214">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="e6294-215">Windows:</span><span class="sxs-lookup"><span data-stu-id="e6294-215">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="e6294-216">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="e6294-216">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="e6294-217">3\.1 채널에서 지정된 위치에 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-217">Install the latest version from 3.1 channel to the specified location:</span></span>

  <span data-ttu-id="e6294-218">Windows:</span><span class="sxs-lookup"><span data-stu-id="e6294-218">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 3.1 -InstallDir C:\cli
  ```

  <span data-ttu-id="e6294-219">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="e6294-219">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 3.1 --install-dir ~/cli
  ```

- <span data-ttu-id="e6294-220">3\.0.0 버전의 공유 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-220">Install the 3.0.0 version of the shared runtime:</span></span>

  <span data-ttu-id="e6294-221">Windows:</span><span class="sxs-lookup"><span data-stu-id="e6294-221">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 3.0.0
  ```

  <span data-ttu-id="e6294-222">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="e6294-222">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 3.0.0
  ```

- <span data-ttu-id="e6294-223">스크립트를 얻어 회사 프록시 뒤에 2.1.2 버전을 설치합니다(Windows에만 해당).</span><span class="sxs-lookup"><span data-stu-id="e6294-223">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="e6294-224">스크립트 가져와서 .NET CLI one-liner 예제를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="e6294-224">Obtain script and install .NET CLI one-liner examples:</span></span>

  <span data-ttu-id="e6294-225">Windows:</span><span class="sxs-lookup"><span data-stu-id="e6294-225">Windows:</span></span>

  ```powershell
  # Run a separate PowerShell process because the script calls exit, so it will end the current PowerShell session.
  &powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="e6294-226">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="e6294-226">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="e6294-227">참조</span><span class="sxs-lookup"><span data-stu-id="e6294-227">See also</span></span>

- [<span data-ttu-id="e6294-228">.NET 릴리스</span><span class="sxs-lookup"><span data-stu-id="e6294-228">.NET releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="e6294-229">.NET 런타임 및 SDK 다운로드 아카이브</span><span class="sxs-lookup"><span data-stu-id="e6294-229">.NET Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
