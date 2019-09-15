---
title: dotnet 설치 스크립트
description: .NET Core CLI 도구 및 공유 런타임을 설치하는 dotnet-install 스크립트에 대해 알아봅니다.
ms.date: 01/16/2019
ms.openlocfilehash: 867be93b5a4c66258df438ce718dabbd4ef2891c
ms.sourcegitcommit: 205b9a204742e9c77256d43ac9d94c3f82909808
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/10/2019
ms.locfileid: "70849568"
---
# <a name="dotnet-install-scripts-reference"></a><span data-ttu-id="40250-103">dotnet-install 스크립트 참조</span><span class="sxs-lookup"><span data-stu-id="40250-103">dotnet-install scripts reference</span></span>

## <a name="name"></a><span data-ttu-id="40250-104">name</span><span class="sxs-lookup"><span data-stu-id="40250-104">Name</span></span>

<span data-ttu-id="40250-105">`dotnet-install.ps1` | `dotnet-install.sh` - .NET Core CLI 도구 및 공유 런타임을 설치하는 데 사용되는 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-105">`dotnet-install.ps1` | `dotnet-install.sh` - Script used to install the .NET Core CLI tools and the shared runtime.</span></span>

## <a name="synopsis"></a><span data-ttu-id="40250-106">개요</span><span class="sxs-lookup"><span data-stu-id="40250-106">Synopsis</span></span>

<span data-ttu-id="40250-107">Windows:</span><span class="sxs-lookup"><span data-stu-id="40250-107">Windows:</span></span>

`dotnet-install.ps1 [-Channel] [-Version] [-InstallDir] [-Architecture] [-SharedRuntime] [-Runtime] [-DryRun] [-NoPath] [-Verbose] [-AzureFeed] [-UncachedFeed] [-NoCdn] [-FeedCredential] [-ProxyAddress] [-ProxyUseDefaultCredentials] [-SkipNonVersionedFiles] [-Help]`

<span data-ttu-id="40250-108">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="40250-108">macOS/Linux:</span></span>

`dotnet-install.sh [--channel] [--version] [--install-dir] [--architecture] [--runtime] [--dry-run] [--no-path] [--verbose] [--azure-feed] [--uncached-feed] [--no-cdn] [--feed-credential] [--runtime-id] [--skip-non-versioned-files] [--help]`

## <a name="description"></a><span data-ttu-id="40250-109">설명</span><span class="sxs-lookup"><span data-stu-id="40250-109">Description</span></span>

<span data-ttu-id="40250-110">`dotnet-install` 스크립트는 .NET Core CLI 도구 및 공유 런타임을 포함하는 .NET Core SDK의 비관리자 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40250-110">The `dotnet-install` scripts are used to perform a non-admin installation of the .NET Core SDK, which includes the .NET Core CLI tools and the shared runtime.</span></span>

<span data-ttu-id="40250-111">[.NET Core 기본 웹 사이트](https://dot.net)에서 호스팅되는 안정적인 버전을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-111">We recommend that you use the stable version that is hosted on [.NET Core main website](https://dot.net).</span></span> <span data-ttu-id="40250-112">스크립트에 대한 직접 경로는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-112">The direct paths to the scripts are:</span></span>

- <span data-ttu-id="40250-113"><https://dot.net/v1/dotnet-install.sh>(bash, UNIX)</span><span class="sxs-lookup"><span data-stu-id="40250-113"><https://dot.net/v1/dotnet-install.sh> (bash, UNIX)</span></span>
- <span data-ttu-id="40250-114"><https://dot.net/v1/dotnet-install.ps1>(Powershell, Windows)</span><span class="sxs-lookup"><span data-stu-id="40250-114"><https://dot.net/v1/dotnet-install.ps1> (Powershell, Windows)</span></span>

<span data-ttu-id="40250-115">이러한 스크립트의 주요 유용성은 자동화 시나리오 및 비관리자 설치입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-115">The main usefulness of these scripts is in automation scenarios and non-admin installations.</span></span> <span data-ttu-id="40250-116">두 개의 스크립트가 있습니다. 하나는 Windows에서 작동하는 PowerShell 스크립트이고, 다른 하나는 Linux/macOS에서 작동하는 bash 스크립트입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-116">There are two scripts: one is a PowerShell script that works on Windows, and the other is a bash script that works on Linux/macOS.</span></span> <span data-ttu-id="40250-117">두 스크립트의 동작은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-117">Both scripts have the same behavior.</span></span> <span data-ttu-id="40250-118">또한 bash 스크립트는 PowerShell 스위치를 읽으므로 Linux/macOS 시스템에서 스크립트와 함께 PowerShell 스위치를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-118">The bash script also reads PowerShell switches, so you can use PowerShell switches with the script on Linux/macOS systems.</span></span>

<span data-ttu-id="40250-119">설치 스크립트는 CLI 빌드 저장 위치에서 ZIP/tarball 파일을 다운로드하여 기본 위치나 `-InstallDir|--install-dir`로 지정한 위치에 설치를 계속 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-119">The installation scripts download the ZIP/tarball file from the CLI build drops and proceed to install it in either the default location or in a location specified by `-InstallDir|--install-dir`.</span></span> <span data-ttu-id="40250-120">기본적으로 설치 스크립트는 SDK를 다운로드하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-120">By default, the installation scripts download the SDK and install it.</span></span> <span data-ttu-id="40250-121">공유 런타임만 가져오려는 경우 `--runtime` 인수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-121">If you wish to only obtain the shared runtime, specify the `--runtime` argument.</span></span>

<span data-ttu-id="40250-122">기본적으로 스크립트는 현재 세션에 대한 $PATH에 설치 위치를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-122">By default, the script adds the install location to the $PATH for the current session.</span></span> <span data-ttu-id="40250-123">`--no-path` 인수를 지정하여 이 기본 동작을 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-123">Override this default behavior by specifying the `--no-path` argument.</span></span>

<span data-ttu-id="40250-124">스크립트를 실행하기 전에 필요한 모든 [종속성](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md)을 설치하세요.</span><span class="sxs-lookup"><span data-stu-id="40250-124">Before running the script, install the required [dependencies](https://github.com/dotnet/core/blob/master/Documentation/prereqs.md).</span></span>

<span data-ttu-id="40250-125">`--version` 인수를 사용하여 특정 버전을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-125">You can install a specific version using the `--version` argument.</span></span> <span data-ttu-id="40250-126">버전은 세 부분으로 구성된 버전(예: 1.0.0-13232)으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-126">The version must be specified as a three-part version (for example, 1.0.0-13232).</span></span> <span data-ttu-id="40250-127">제공하지 않으면 `latest` 버전을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-127">If not provided, it uses the `latest` version.</span></span>

## <a name="options"></a><span data-ttu-id="40250-128">옵션</span><span class="sxs-lookup"><span data-stu-id="40250-128">Options</span></span>

- **`-Channel <CHANNEL>`**

  <span data-ttu-id="40250-129">설치에 대한 소스 채널을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-129">Specifies the source channel for the installation.</span></span> <span data-ttu-id="40250-130">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-130">The possible values are:</span></span>

  - <span data-ttu-id="40250-131">`Current` - 최신 릴리스입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-131">`Current` - Most current release.</span></span>
  - <span data-ttu-id="40250-132">`LTS` - 장기 지원 채널(지원되는 최신 릴리스)입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-132">`LTS` - Long-Term Support channel (most current supported release).</span></span>
  - <span data-ttu-id="40250-133">특정 릴리스를 나타내는 X.Y 형식의 두 부분으로 된 버전입니다(예: `2.0` 또는 `1.0`).</span><span class="sxs-lookup"><span data-stu-id="40250-133">Two-part version in X.Y format representing a specific release (for example, `2.0` or `1.0`).</span></span>
  - <span data-ttu-id="40250-134">분기 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-134">Branch name.</span></span> <span data-ttu-id="40250-135">예를 들어 `release/2.0.0`, `release/2.0.0-preview2` 또는 `master`(야간 릴리스의 경우)입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-135">For example, `release/2.0.0`, `release/2.0.0-preview2`, or `master` (for nightly releases).</span></span>

  <span data-ttu-id="40250-136">기본값은 `LTS`입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-136">The default value is `LTS`.</span></span> <span data-ttu-id="40250-137">.NET 지원 채널에 대한 자세한 내용은 [.NET 지원 정책](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="40250-137">For more information on .NET support channels, see the [.NET Support Policy](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) page.</span></span>

- **`-Version <VERSION>`**

  <span data-ttu-id="40250-138">특정 빌드 버전을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="40250-138">Represents a specific build version.</span></span> <span data-ttu-id="40250-139">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-139">The possible values are:</span></span>

  - <span data-ttu-id="40250-140">`latest` - 채널의 최신 빌드입니다(`-Channel` 옵션과 함께 사용됨).</span><span class="sxs-lookup"><span data-stu-id="40250-140">`latest` - Latest build on the channel (used with the `-Channel` option).</span></span>
  - <span data-ttu-id="40250-141">`coherent` - 채널의 일관된 최신 빌드로, 안정적인 최신 패키지 조합을 사용합니다(분기 이름 `-Channel` 옵션과 함께 사용됨).</span><span class="sxs-lookup"><span data-stu-id="40250-141">`coherent` - Latest coherent build on the channel; uses the latest stable package combination (used with Branch name `-Channel` options).</span></span>
  - <span data-ttu-id="40250-142">특정 빌드 버전을 나타내는 X.Y.Z 형식의 세 부분으로 구성된 버전이며 `-Channel` 옵션을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-142">Three-part version in X.Y.Z format representing a specific build version; supersedes the `-Channel` option.</span></span> <span data-ttu-id="40250-143">예: `2.0.0-preview2-006120`</span><span class="sxs-lookup"><span data-stu-id="40250-143">For example: `2.0.0-preview2-006120`.</span></span>

  <span data-ttu-id="40250-144">지정하지 않으면 `-Version`은 기본값인 `latest`로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="40250-144">If not specified, `-Version` defaults to `latest`.</span></span>

- **`-InstallDir <DIRECTORY>`**

  <span data-ttu-id="40250-145">설치 경로를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-145">Specifies the installation path.</span></span> <span data-ttu-id="40250-146">디렉터리가 없을 경우 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="40250-146">The directory is created if it doesn't exist.</span></span> <span data-ttu-id="40250-147">기본값은 *%LocalAppData%\Microsoft\dotnet*입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-147">The default value is *%LocalAppData%\Microsoft\dotnet*.</span></span> <span data-ttu-id="40250-148">이진 파일은 이 디렉터리에 바로 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="40250-148">Binaries are placed directly in this directory.</span></span>

- **`-Architecture <ARCHITECTURE>`**

  <span data-ttu-id="40250-149">설치할 .NET Core 바이너리의 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-149">Architecture of the .NET Core binaries to install.</span></span> <span data-ttu-id="40250-150">가능한 값은 `<auto>`, `amd64`, `x64`, `x86`, `arm64` 및 `arm`입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-150">Possible values are `<auto>`, `amd64`, `x64`, `x86`, `arm64`, and `arm`.</span></span> <span data-ttu-id="40250-151">기본값은 현재 실행 중인 OS 아키텍처를 나타내는 `<auto>`입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-151">The default value is `<auto>`, which represents the currently running OS architecture.</span></span>

- **`-SharedRuntime`**

  > [!NOTE]
  > <span data-ttu-id="40250-152">이 매개 변수는 더 이상 사용되지 않으며 스크립트의 이후 버전에서 제거될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-152">This parameter is obsolete and may be removed in a future version of the script.</span></span> <span data-ttu-id="40250-153">대신 `Runtime` 옵션을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-153">The recommended alternative is the `Runtime` option.</span></span>

  <span data-ttu-id="40250-154">전체 SDK가 아니라 공유 런타임 비트만 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-154">Installs just the shared runtime bits, not the entire SDK.</span></span> <span data-ttu-id="40250-155">이는 `-Runtime dotnet`를 지정하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-155">This is equivalent to specifying `-Runtime dotnet`.</span></span>

- **`-Runtime <RUNTIME>`**

  <span data-ttu-id="40250-156">전체 SDK가 아닌 공유 런타임만 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-156">Installs just the shared runtime, not the entire SDK.</span></span> <span data-ttu-id="40250-157">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-157">The possible values are:</span></span>

  - <span data-ttu-id="40250-158">`dotnet` - `Microsoft.NETCore.App` 공유 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-158">`dotnet` - the `Microsoft.NETCore.App` shared runtime.</span></span>
  - <span data-ttu-id="40250-159">`aspnetcore` - `Microsoft.AspNetCore.App` 공유 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-159">`aspnetcore` - the `Microsoft.AspNetCore.App` shared runtime.</span></span>

- **`-DryRun`**

  <span data-ttu-id="40250-160">설정하면 스크립트에서 설치를 수행하지는 않지만,</span><span class="sxs-lookup"><span data-stu-id="40250-160">If set, the script won't perform the installation.</span></span> <span data-ttu-id="40250-161">대신 현재 요청된 버전의 .NET Core CLI를 일관되게 설치하기 위해 사용할 명령줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-161">Instead, it displays what command line to use to consistently install the currently requested version of the .NET Core CLI.</span></span> <span data-ttu-id="40250-162">예를 들어 `latest` 버전을 지정하면 빌드 스크립트에서 이 명령을 결정적으로 사용할 수 있도록 특정 버전에 대한 링크를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-162">For example, if you specify version `latest`, it displays a link with the specific version so that this command can be used deterministically in a build script.</span></span> <span data-ttu-id="40250-163">또한 직접 설치하거나 다운로드하는 것을 선호하는 경우 이진 파일 위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-163">It also displays the binary's location if you prefer to install or download it yourself.</span></span>

- **`-NoPath`**

  <span data-ttu-id="40250-164">설정하면 설치 폴더를 현재 세션의 경로로 내보내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-164">If set, the installation folder isn't exported to the path for the current session.</span></span> <span data-ttu-id="40250-165">기본적으로 스크립트는 경로를 수정하여, 설치 후 CLI 도구를 즉시 사용할 수 있게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="40250-165">By default, the script modifies the PATH, which makes the CLI tools available immediately after install.</span></span>

- **`-Verbose`**

  <span data-ttu-id="40250-166">진단 정보를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-166">Displays diagnostics information.</span></span>

- **`-AzureFeed`**

  <span data-ttu-id="40250-167">설치 관리자에 대한 Azure 피드의 URL을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-167">Specifies the URL for the Azure feed to the installer.</span></span> <span data-ttu-id="40250-168">이 값은 변경하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-168">We recommended that you don't change this value.</span></span> <span data-ttu-id="40250-169">기본값은 `https://dotnetcli.azureedge.net/dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="40250-169">The default value is `https://dotnetcli.azureedge.net/dotnet`.</span></span>

- **`-UncachedFeed`**

  <span data-ttu-id="40250-170">이 설치 관리자가 사용하는 캐시되지 않은 피드의 URL을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-170">Allows changing the URL for the uncached feed used by this installer.</span></span> <span data-ttu-id="40250-171">이 값은 변경하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-171">We recommended that you don't change this value.</span></span>

- **`-NoCdn`**

  <span data-ttu-id="40250-172">[Azure CDN(Content Delivery Network)](https://docs.microsoft.com/azure/cdn/cdn-overview)에서 다운로드할 수 없도록 설정하고 캐시되지 않은 피드를 바로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-172">Disables downloading from the [Azure Content Delivery Network (CDN)](https://docs.microsoft.com/azure/cdn/cdn-overview) and uses the uncached feed directly.</span></span>

- **`-FeedCredential`**

  <span data-ttu-id="40250-173">Azure 피드에 추가할 쿼리 문자열로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40250-173">Used as a query string to append to the Azure feed.</span></span> <span data-ttu-id="40250-174">public이 아닌 Blob 스토리지 계정을 사용하도록 URL을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40250-174">It allows changing the URL to use non-public blob storage accounts.</span></span>

- **`-ProxyAddress`**

  <span data-ttu-id="40250-175">설정된 경우 설치 관리자에서 웹 요청을 만들 때 프록시를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-175">If set, the installer uses the proxy when making web requests.</span></span> <span data-ttu-id="40250-176">(Windows에만 유효함)</span><span class="sxs-lookup"><span data-stu-id="40250-176">(Only valid for Windows)</span></span>

- **`ProxyUseDefaultCredentials`**

  <span data-ttu-id="40250-177">설정하면 설치 관리자가 프록시 주소를 사용할 때 현재 사용자의 자격 증명을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-177">If set, the installer uses the credentials of the current user when using proxy address.</span></span> <span data-ttu-id="40250-178">(Windows에만 유효함)</span><span class="sxs-lookup"><span data-stu-id="40250-178">(Only valid for Windows)</span></span>

- **`-SkipNonVersionedFiles`**

  <span data-ttu-id="40250-179">*dotnet.exe*와 같은 버전이 없는 파일이 있을 경우 해당 파일의 설치를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="40250-179">Skips installing non-versioned files, such as *dotnet.exe*, if they already exist.</span></span>

- **`-Help`**

  <span data-ttu-id="40250-180">스크립트에 대한 도움말을 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-180">Prints out help for the script.</span></span>

## <a name="examples"></a><span data-ttu-id="40250-181">예제</span><span class="sxs-lookup"><span data-stu-id="40250-181">Examples</span></span>

- <span data-ttu-id="40250-182">기본 위치에 최신 LTS(장기 지원) 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-182">Install the latest long-term supported (LTS) version to the default location:</span></span>

  <span data-ttu-id="40250-183">Windows:</span><span class="sxs-lookup"><span data-stu-id="40250-183">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel LTS
  ```

  <span data-ttu-id="40250-184">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="40250-184">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel LTS
  ```

- <span data-ttu-id="40250-185">지정된 위치에 2.0 채널의 최신 버전을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-185">Install the latest version from 2.0 channel to the specified location:</span></span>

  <span data-ttu-id="40250-186">Windows:</span><span class="sxs-lookup"><span data-stu-id="40250-186">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Channel 2.0 -InstallDir C:\cli
  ```

  <span data-ttu-id="40250-187">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="40250-187">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --channel 2.0 --install-dir ~/cli
  ```

- <span data-ttu-id="40250-188">1\.1.0 버전의 공유 런타임을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-188">Install the 1.1.0 version of the shared runtime:</span></span>

  <span data-ttu-id="40250-189">Windows:</span><span class="sxs-lookup"><span data-stu-id="40250-189">Windows:</span></span>

  ```powershell
  ./dotnet-install.ps1 -Runtime dotnet -Version 1.1.0
  ```

  <span data-ttu-id="40250-190">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="40250-190">macOS/Linux:</span></span>

  ```bash
  ./dotnet-install.sh --runtime dotnet --version 1.1.0
  ```

- <span data-ttu-id="40250-191">스크립트를 얻어 회사 프록시 뒤에 2.1.2 버전을 설치합니다(Windows에만 해당).</span><span class="sxs-lookup"><span data-stu-id="40250-191">Obtain script and install the 2.1.2 version behind a corporate proxy (Windows only):</span></span>

  ```powershell
  Invoke-WebRequest 'https://dot.net/v1/dotnet-install.ps1' -Proxy $env:HTTP_PROXY -ProxyUseDefaultCredentials -OutFile 'dotnet-install.ps1';
  ./dotnet-install.ps1 -InstallDir '~/.dotnet' -Version '2.1.2' -ProxyAddress $env:HTTP_PROXY -ProxyUseDefaultCredentials;
  ```

- <span data-ttu-id="40250-192">스크립트 가져와서 .NET Core CLI one-liner 예제를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="40250-192">Obtain script and install .NET Core CLI one-liner examples:</span></span>

  <span data-ttu-id="40250-193">Windows:</span><span class="sxs-lookup"><span data-stu-id="40250-193">Windows:</span></span>

  ```powershell
  @powershell -NoProfile -ExecutionPolicy unrestricted -Command "[Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12; &([scriptblock]::Create((Invoke-WebRequest -UseBasicParsing 'https://dot.net/v1/dotnet-install.ps1'))) <additional install-script args>"
  ```

  <span data-ttu-id="40250-194">macOS/Linux:</span><span class="sxs-lookup"><span data-stu-id="40250-194">macOS/Linux:</span></span>

  ```bash
  curl -sSL https://dot.net/v1/dotnet-install.sh | bash /dev/stdin <additional install-script args>
  ```

## <a name="see-also"></a><span data-ttu-id="40250-195">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40250-195">See also</span></span>

- [<span data-ttu-id="40250-196">.NET Core 릴리스</span><span class="sxs-lookup"><span data-stu-id="40250-196">.NET Core releases</span></span>](https://github.com/dotnet/core/releases)
- [<span data-ttu-id="40250-197">.NET Core 런타임 및 SDK 다운로드 아카이브</span><span class="sxs-lookup"><span data-stu-id="40250-197">.NET Core Runtime and SDK download archive</span></span>](https://github.com/dotnet/core/blob/master/release-notes/download-archive.md)
