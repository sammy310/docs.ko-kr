---
title: Windows, Linux 및 macOS에 .NET Core SDK 설치 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core를 설치하는 방법을 알아봅니다. .NET Core 앱을 개발하는 데 필요한 종속성에 대해 알아봅니다.
author: adegeo
ms.author: adegeo
ms.date: 05/04/2020
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: a11d1eb3bae6affaa548407cbd68c166a30e99da
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85324667"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="10fca-104">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="10fca-105">이 문서에서는 .NET Core SDK를 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="10fca-106">.NET Core SDK는 .NET Core 앱과 라이브러리를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="10fca-107">.NET Core 런타임은 항상 SDK와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="10fca-108">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-108">Install with an installer</span></span>

<span data-ttu-id="10fca-109">Windows에는 .NET Core 3.1 SDK를 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="10fca-110">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="10fca-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="10fca-111">x86(32비트) CPU</span><span class="sxs-lookup"><span data-stu-id="10fca-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="10fca-112">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-112">Install with an installer</span></span>

<span data-ttu-id="10fca-113">macOS에는 .NET Core 3.1 SDK를 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="10fca-114">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="10fca-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

## <a name="download-and-manually-install"></a><span data-ttu-id="10fca-115">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-115">Download and manually install</span></span>

<span data-ttu-id="10fca-116">.NET Core용 macOS 설치 프로그램의 대안으로, SDK를 다운로드하여 수동으로 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-116">As an alternative to the macOS installers for .NET Core, you can download and manually install the SDK.</span></span>

<span data-ttu-id="10fca-117">SDK를 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-117">To extract the SDK and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="10fca-118">그런 다음 터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-118">Then, open a terminal and run the following commands.</span></span> <span data-ttu-id="10fca-119">런타임이 `~/Downloads/dotnet-sdk.pkg` 파일로 다운로드되었다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-119">It's assumed the runtime is downloaded to the `~/Downloads/dotnet-sdk.pkg` file.</span></span>

```bash
mkdir -p $HOME/dotnet
sudo installer -pkg ~/Downloads/dotnet-sdk.pkg -target $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

::: zone-end

::: zone pivot="os-linux"

## <a name="install-on-linux"></a><span data-ttu-id="10fca-120">Linux에 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-120">Install on Linux</span></span>

<span data-ttu-id="10fca-121">이 문서는 곧 제거될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-121">This article will be removed soon.</span></span> <span data-ttu-id="10fca-122">현재 [Linux에서 .NET Core 설치](linux.md)로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-122">It is currently replaced by [Install .NET Core on Linux](linux.md).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="10fca-123">Visual Studio를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-123">Install with Visual Studio</span></span>

<span data-ttu-id="10fca-124">Visual Studio를 사용하여 .NET Core 앱을 개발하는 경우, 다음 표에서 대상 .NET Core SDK 버전에 따라 필요한 Visual Studio의 최소 버전을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="10fca-124">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="10fca-125">.NET Core SDK 버전</span><span class="sxs-lookup"><span data-stu-id="10fca-125">.NET Core SDK version</span></span> | <span data-ttu-id="10fca-126">Visual Studio 버전</span><span class="sxs-lookup"><span data-stu-id="10fca-126">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="10fca-127">3.1</span><span class="sxs-lookup"><span data-stu-id="10fca-127">3.1</span></span>                   | <span data-ttu-id="10fca-128">Visual Studio 2019 버전 16.4 이상</span><span class="sxs-lookup"><span data-stu-id="10fca-128">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="10fca-129">3.0</span><span class="sxs-lookup"><span data-stu-id="10fca-129">3.0</span></span>                   | <span data-ttu-id="10fca-130">Visual Studio 2019 버전 16.3 이상</span><span class="sxs-lookup"><span data-stu-id="10fca-130">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="10fca-131">2.2</span><span class="sxs-lookup"><span data-stu-id="10fca-131">2.2</span></span>                   | <span data-ttu-id="10fca-132">Visual Studio 2017 버전 15.9 이상</span><span class="sxs-lookup"><span data-stu-id="10fca-132">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="10fca-133">2.1</span><span class="sxs-lookup"><span data-stu-id="10fca-133">2.1</span></span>                   | <span data-ttu-id="10fca-134">Visual Studio 2017 버전 15.7 이상</span><span class="sxs-lookup"><span data-stu-id="10fca-134">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="10fca-135">Visual Studio가 이미 설치되어 있다면 다음 단계에 따라 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-135">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="10fca-136">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-136">Open Visual Studio.</span></span>
01. <span data-ttu-id="10fca-137">**도움말** > **Microsoft Visual Studio 정보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-137">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="10fca-138">**정보** 대화 상자에서 버전 번호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-138">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="10fca-139">Visual Studio가 최신 .NET Core SDK 및 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-139">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="10fca-140">[Visual Studio를 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-140">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="10fca-141">워크로드 선택</span><span class="sxs-lookup"><span data-stu-id="10fca-141">Select a workload</span></span>

<span data-ttu-id="10fca-142">Visual Studio를 설치하거나 수정할 때는 빌드하려는 애플리케이션의 종류에 따라 다음 워크로드 중 하나 이상을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-142">When installing or modifying Visual Studio, select one or more of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="10fca-143">**기타 도구 세트** 섹션의 **.NET Core 플랫폼 간 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="10fca-143">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="10fca-144">**웹 및 클라우드** 섹션의 **ASP.NET 및 웹 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="10fca-144">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="10fca-145">**웹 및 클라우드** 섹션의 **Azure 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="10fca-145">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="10fca-146">**데스크톱 및 모바일** 섹션의 **.NET 데스크톱 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="10fca-146">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="10fca-147">[![Windows Visual Studio 2019 및 .NET Core 워크로드](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="10fca-147">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="10fca-148">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-148">Download and manually install</span></span>

<span data-ttu-id="10fca-149">런타임을 추출하고 터미널에서 .NET Core CLI 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-149">To extract the runtime and make the .NET Core CLI commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="10fca-150">그런 다음 `%USERPROFILE%\dotnet`와 같이 설치할 디렉터리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-150">Then, create a directory to install to, for example `%USERPROFILE%\dotnet`.</span></span> <span data-ttu-id="10fca-151">마지막으로 다운로드한 zip 파일을 그 디렉터리로 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-151">Finally, extract the downloaded zip file into that directory.</span></span>

<span data-ttu-id="10fca-152">기본적으로 .NET Core CLI 명령과 앱은 이런 방식으로 설치된 .NET Core를 사용하지 않으므로 명시적으로 사용을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-152">By default, .NET Core CLI commands and apps won't use .NET Core installed in this way and you must explicitly choose to use it.</span></span> <span data-ttu-id="10fca-153">이렇게 하려면 애플리케이션이 시작되는 환경 변수를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-153">To do so, change the environment variables with which an application is started:</span></span>

```console
set DOTNET_ROOT=%USERPROFILE%\dotnet
set PATH=%USERPROFILE%\dotnet;%PATH%
```

<span data-ttu-id="10fca-154">이 방법을 사용하면 여러 버전을 별도의 위치에 설치한 다음 애플리케이션이 해당 위치를 가리키는 환경 변수를 사용하여 애플리케이션을 실행하는 데 사용해야 하는 설치 위치를 명시적으로 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-154">This approach lets you install multiple versions into separate locations, then explicitly choose which install location an application should use by running the application with environment variables pointing at that location.</span></span>

<span data-ttu-id="10fca-155">이러한 환경 변수가 설정된 경우에도 .NET Core는 애플리케이션을 실행하는 데 가장 적합한 프레임워크를 선택할 때 기본 전역 설치 위치를 계속 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-155">Even when these environment variables are set, .NET Core still considers the default global install location when selecting the best framework for running the application.</span></span> <span data-ttu-id="10fca-156">기본값은 일반적으로 설치 프로그램이 사용하는 `C:\Program Files\dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-156">The default is typically `C:\Program Files\dotnet`, which the installers use.</span></span> <span data-ttu-id="10fca-157">이 환경 변수를 설정하여 사용자 지정 설치 위치만 사용하도록 런타임에 지시할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-157">You can instruct the runtime to only use the custom install location by setting this environment variable as well:</span></span>

```console
set DOTNET_MULTILEVEL_LOOKUP=0
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="10fca-158">Mac용 Visual Studio를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-158">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="10fca-159">Mac용 Visual Studio는 **.NET Core** 워크로드가 선택된 경우 .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-159">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="10fca-160">macOS에서 .NET Core 개발을 시작하려면 [Mac용 Visual Studio 2019 설치](/visualstudio/mac/installation)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10fca-160">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="10fca-161">최신 릴리스인 .NET Core 3.1의 경우 Mac용 Visual Studio 8.4 미리 보기를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-161">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="10fca-162">[![macOS Mac용 Visual Studio 2019 및 .NET Core 워크로드의 특징](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="10fca-162">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-windows,os-macos"

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="10fca-163">Visual Studio Code와 함께 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-163">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="10fca-164">Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-164">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="10fca-165">Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-165">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="10fca-166">Visual Studio Code에 Visual Studio처럼 자동화된 .NET Core 설치 프로그램이 포함되지 않은 경우, 간편하게 .NET Core 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-166">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="10fca-167">[Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="10fca-167">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="10fca-168">[.NET Core SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="10fca-168">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="10fca-169">[Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span><span class="sxs-lookup"><span data-stu-id="10fca-169">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp).</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="10fca-170">PowerShell 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-170">Install with PowerShell automation</span></span>

<span data-ttu-id="10fca-171">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 SDK의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-171">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="10fca-172">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-172">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="10fca-173">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-173">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="10fca-174">.NET Core의 최신 릴리스를 설치하려면 다음 스위치와 함께 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-174">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="10fca-175">배시 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="10fca-175">Install with bash automation</span></span>

<span data-ttu-id="10fca-176">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 SDK의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-176">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="10fca-177">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-177">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="10fca-178">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 3.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-178">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 3.1.</span></span> <span data-ttu-id="10fca-179">.NET Core의 최신 릴리스를 설치하려면 다음 스위치와 함께 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-179">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="10fca-180">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="10fca-180">All .NET Core downloads</span></span>

<span data-ttu-id="10fca-181">다음 링크 중 하나를 사용하여 .NET Core를 직접 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-181">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="10fca-182">.NET Core 3.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="10fca-182">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="10fca-183">.NET Core 3.0 다운로드</span><span class="sxs-lookup"><span data-stu-id="10fca-183">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="10fca-184">.NET Core 2.2 다운로드</span><span class="sxs-lookup"><span data-stu-id="10fca-184">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="10fca-185">.NET Core 2.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="10fca-185">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="10fca-186">Docker</span><span class="sxs-lookup"><span data-stu-id="10fca-186">Docker</span></span>

<span data-ttu-id="10fca-187">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-187">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="10fca-188">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-188">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="10fca-189">.NET Core는 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-189">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="10fca-190">공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-190">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="10fca-191">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-191">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="10fca-192">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-192">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="10fca-193">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="10fca-193">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="10fca-194">Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="10fca-194">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="10fca-195">다음 단계</span><span class="sxs-lookup"><span data-stu-id="10fca-195">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="10fca-196">[자습서: Hello World 자습서](../tutorials/with-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="10fca-196">[Tutorial: Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="10fca-197">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="10fca-197">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="10fca-198">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="10fca-198">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="10fca-199">[macOS Catalina 공증 관련 사항](macos-notarization-issues.md)</span><span class="sxs-lookup"><span data-stu-id="10fca-199">[Working with macOS Catalina notarization](macos-notarization-issues.md).</span></span>
- <span data-ttu-id="10fca-200">[자습서: macOS에서 시작](../tutorials/using-on-mac-vs.md)</span><span class="sxs-lookup"><span data-stu-id="10fca-200">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="10fca-201">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="10fca-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="10fca-202">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="10fca-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="10fca-203">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="10fca-203">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="10fca-204">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="10fca-204">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
