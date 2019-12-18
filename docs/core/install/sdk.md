---
title: Windows, Linux 및 macOS에 .NET Core SDK 설치 - .NET Core
description: Windows, Linux 및 macOS에 .NET Core를 설치하는 방법을 알아봅니다. .NET Core 앱을 개발하는 데 필요한 종속성에 대해 알아봅니다.
author: thraka
ms.author: adegeo
ms.date: 12/04/2019
ms.custom: updateeachrelease
zone_pivot_groups: operating-systems-set-one
ms.openlocfilehash: 1f7efaedaa1a0be90f7b619f954bdf78eecafa07
ms.sourcegitcommit: 42ed59871db1f29a32b3d8e7abeb20e6eceeda7c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2019
ms.locfileid: "74999064"
---
# <a name="install-the-net-core-sdk"></a><span data-ttu-id="c61f2-104">.NET Core SDK 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-104">Install the .NET Core SDK</span></span>

<span data-ttu-id="c61f2-105">이 문서에서는 .NET Core SDK를 설치하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-105">In this article, you'll learn how to install the .NET Core SDK.</span></span> <span data-ttu-id="c61f2-106">.NET Core SDK는 .NET Core 앱과 라이브러리를 만드는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-106">The .NET Core SDK is used to create .NET Core apps and libraries.</span></span> <span data-ttu-id="c61f2-107">.NET Core 런타임은 항상 SDK와 함께 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-107">The .NET Core runtime is always installed with the SDK.</span></span>

::: zone pivot="os-windows"

## <a name="install-with-an-installer"></a><span data-ttu-id="c61f2-108">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-108">Install with an installer</span></span>

<span data-ttu-id="c61f2-109">Windows에는 .NET Core 3.1 SDK를 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-109">Windows has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="c61f2-110">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="c61f2-110">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="c61f2-111">x86(32비트) CPU</span><span class="sxs-lookup"><span data-stu-id="c61f2-111">x86 (32-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-an-installer"></a><span data-ttu-id="c61f2-112">설치 프로그램을 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-112">Install with an installer</span></span>

<span data-ttu-id="c61f2-113">macOS에는 .NET Core 3.1 SDK를 설치하는 데 사용할 수 있는 독립 실행형 설치 프로그램이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-113">macOS has standalone installers that can be used to install the .NET Core 3.1 SDK:</span></span>

- [<span data-ttu-id="c61f2-114">x64(64비트) CPU</span><span class="sxs-lookup"><span data-stu-id="c61f2-114">x64 (64-bit) CPUs</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)

::: zone-end

::: zone pivot="os-linux"

## <a name="install-with-a-package-manager"></a><span data-ttu-id="c61f2-115">패키지 관리자를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-115">Install with a package manager</span></span>

<span data-ttu-id="c61f2-116">널리 사용되는 여러 Linux 패키지 관리자를 사용하여 .NET Core SDK를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-116">You can install the .NET Core SDK with many of the common Linux package managers.</span></span> <span data-ttu-id="c61f2-117">자세한 내용은 [Linux 패키지 관리자 - .NET Core 설치](linux-package-managers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c61f2-117">For more information, see [Linux Package Manager - Install .NET Core](linux-package-managers.md).</span></span>

## <a name="download-and-manually-install"></a><span data-ttu-id="c61f2-118">다운로드 및 수동으로 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-118">Download and manually install</span></span>

<span data-ttu-id="c61f2-119">SDK를 추출하고 터미널에서 명령을 사용할 수 있으려면 먼저 .NET Core 이진 릴리스를 [다운로드](#all-net-core-downloads)합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-119">To extract the SDK and make the commands available at the terminal, first [download](#all-net-core-downloads) a .NET Core binary release.</span></span> <span data-ttu-id="c61f2-120">그런 다음 터미널을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-120">Then, open a terminal and run the following commands.</span></span>

```bash
mkdir -p $HOME/dotnet && tar zxf dotnet-sdk-3.1.100-linux-x64.tar.gz -C $HOME/dotnet
export DOTNET_ROOT=$HOME/dotnet
export PATH=$PATH:$HOME/dotnet
```

> [!TIP]
> <span data-ttu-id="c61f2-121">위 명령은 명령이 실행된 터미널 세션에서만 .NET SDK 명령을 사용할 수 있도록 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-121">The above commands will only make the .NET SDK commands available for the terminal session in which it was run.</span></span>
>
> <span data-ttu-id="c61f2-122">셸 프로필을 편집하여 명령을 영구적으로 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-122">You can edit your shell profile to permanently add the commands.</span></span> <span data-ttu-id="c61f2-123">몇 가지 Linux용 셸이 있으며, 각각 다른 프로필을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-123">There are a number of different shells available for Linux and each has a different profile.</span></span> <span data-ttu-id="c61f2-124">예:</span><span class="sxs-lookup"><span data-stu-id="c61f2-124">For example:</span></span>
>
> - <span data-ttu-id="c61f2-125">**Bash 셸**: *~/.bash_profile*, *~/.bashrc*</span><span class="sxs-lookup"><span data-stu-id="c61f2-125">**Bash Shell**: *~/.bash_profile*, *~/.bashrc*</span></span>
> - <span data-ttu-id="c61f2-126">**Korn 셸**: *~/.kshrc* 또는 *.profile*</span><span class="sxs-lookup"><span data-stu-id="c61f2-126">**Korn Shell**: *~/.kshrc* or *.profile*</span></span>
> - <span data-ttu-id="c61f2-127">**Z 셸**: *~/.zshrc* 또는 *.zprofile*</span><span class="sxs-lookup"><span data-stu-id="c61f2-127">**Z Shell**: *~/.zshrc* or *.zprofile*</span></span>
> 
> <span data-ttu-id="c61f2-128">셸의 적절한 소스 파일을 편집하고 기존 `PATH` 문의 끝에 `:$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-128">Edit the appropriate source file for your shell and add `:$HOME/dotnet` to the end of the existing `PATH` statement.</span></span> <span data-ttu-id="c61f2-129">포함된 `PATH` 문이 없다면 `export PATH=$PATH:$HOME/dotnet`을 사용하여 새 라인을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-129">If no `PATH` statement is included, add a new line with `export PATH=$PATH:$HOME/dotnet`.</span></span>
>
> <span data-ttu-id="c61f2-130">또한, 파일 끝에 `export DOTNET_ROOT=$HOME/dotnet`을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-130">Also, add `export DOTNET_ROOT=$HOME/dotnet` to the end of the file.</span></span>

::: zone-end

::: zone pivot="os-windows"

## <a name="install-with-visual-studio"></a><span data-ttu-id="c61f2-131">Visual Studio를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-131">Install with Visual Studio</span></span>

<span data-ttu-id="c61f2-132">Visual Studio를 사용하여 .NET Core 앱을 개발하는 경우, 다음 표에서 대상 .NET Core SDK 버전에 따라 필요한 Visual Studio의 최소 버전을 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="c61f2-132">If you're using Visual Studio to develop .NET Core apps, the following table describes the minimum required version of Visual Studio based on the target .NET Core SDK version.</span></span>

| <span data-ttu-id="c61f2-133">.NET Core SDK 버전</span><span class="sxs-lookup"><span data-stu-id="c61f2-133">.NET Core SDK version</span></span> | <span data-ttu-id="c61f2-134">Visual Studio 버전</span><span class="sxs-lookup"><span data-stu-id="c61f2-134">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="c61f2-135">3.1</span><span class="sxs-lookup"><span data-stu-id="c61f2-135">3.1</span></span>                   | <span data-ttu-id="c61f2-136">Visual Studio 2019 버전 16.4 이상</span><span class="sxs-lookup"><span data-stu-id="c61f2-136">Visual Studio 2019 version 16.4 or higher.</span></span> |
| <span data-ttu-id="c61f2-137">3.0</span><span class="sxs-lookup"><span data-stu-id="c61f2-137">3.0</span></span>                   | <span data-ttu-id="c61f2-138">Visual Studio 2019 버전 16.3 이상</span><span class="sxs-lookup"><span data-stu-id="c61f2-138">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="c61f2-139">2.2</span><span class="sxs-lookup"><span data-stu-id="c61f2-139">2.2</span></span>                   | <span data-ttu-id="c61f2-140">Visual Studio 2017 버전 15.9 이상</span><span class="sxs-lookup"><span data-stu-id="c61f2-140">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="c61f2-141">2.1</span><span class="sxs-lookup"><span data-stu-id="c61f2-141">2.1</span></span>                   | <span data-ttu-id="c61f2-142">Visual Studio 2017 버전 15.7 이상</span><span class="sxs-lookup"><span data-stu-id="c61f2-142">Visual Studio 2017 version 15.7 or higher.</span></span> |

<span data-ttu-id="c61f2-143">Visual Studio가 이미 설치되어 있다면 다음 단계에 따라 버전을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-143">If you already have Visual Studio installed, you can check your version with the following steps.</span></span>

01. <span data-ttu-id="c61f2-144">Visual Studio를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-144">Open Visual Studio.</span></span>
01. <span data-ttu-id="c61f2-145">**도움말** > **Microsoft Visual Studio 정보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-145">Select **Help** > **About Microsoft Visual Studio**.</span></span>
01. <span data-ttu-id="c61f2-146">**정보** 대화 상자에서 버전 번호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-146">Read the version number from the **About** dialog.</span></span>

<span data-ttu-id="c61f2-147">Visual Studio가 최신 .NET Core SDK 및 런타임을 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-147">Visual Studio can install the latest .NET Core SDK and runtime.</span></span>

- <span data-ttu-id="c61f2-148">[Visual Studio를 다운로드](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-148">[Download Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019).</span></span>

### <a name="select-a-workload"></a><span data-ttu-id="c61f2-149">워크로드 선택</span><span class="sxs-lookup"><span data-stu-id="c61f2-149">Select a workload</span></span>

<span data-ttu-id="c61f2-150">Visual Studio를 설치하거나 수정할 때는 빌드하려는 애플리케이션의 종류에 따라 다음 워크로드 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-150">When installing or modifying Visual Studio, select one of the following workloads, depending on the kind of application you're building:</span></span>

- <span data-ttu-id="c61f2-151">**기타 도구 세트** 섹션의 **.NET Core 플랫폼 간 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="c61f2-151">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
- <span data-ttu-id="c61f2-152">**웹 및 클라우드** 섹션의 **ASP.NET 및 웹 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="c61f2-152">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="c61f2-153">**웹 및 클라우드** 섹션의 **Azure 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="c61f2-153">The **Azure development** workload in the **Web & Cloud** section.</span></span>
- <span data-ttu-id="c61f2-154">**데스크톱 및 모바일** 섹션의 **.NET 데스크톱 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="c61f2-154">The **.NET desktop development** workload in the **Desktop & Mobile** section.</span></span>

<span data-ttu-id="c61f2-155">[![Windows Visual Studio 2019 및 .NET Core 워크로드](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c61f2-155">[![Windows Visual Studio 2019 with .NET Core workload](media/install-sdk/windows-install-visual-studio-2019.png)](media/install-sdk/windows-install-visual-studio-2019.png#lightbox)</span></span>

::: zone-end

::: zone pivot="os-macos"

## <a name="install-with-visual-studio-for-mac"></a><span data-ttu-id="c61f2-156">Mac용 Visual Studio를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-156">Install with Visual Studio for Mac</span></span>

<span data-ttu-id="c61f2-157">Mac용 Visual Studio는 **.NET Core** 워크로드가 선택된 경우 .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-157">Visual Studio for Mac installs the .NET Core SDK when the **.NET Core** workload is selected.</span></span> <span data-ttu-id="c61f2-158">macOS에서 .NET Core 개발을 시작하려면 [Mac용 Visual Studio 2019 설치](/visualstudio/mac/installation)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c61f2-158">To get started with .NET Core development on macOS, see [Install Visual Studio 2019 for Mac](/visualstudio/mac/installation).</span></span> <span data-ttu-id="c61f2-159">최신 릴리스인 .NET Core 3.1의 경우 Mac용 Visual Studio 8.4 미리 보기를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-159">For the latest release, .NET Core 3.1, you must use the Visual Studio for Mac 8.4 Preview.</span></span>

<span data-ttu-id="c61f2-160">[![macOS Mac용 Visual Studio 2019 및 .NET Core 워크로드의 특징](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="c61f2-160">[![macOS Visual Studio 2019 for Mac with .NET Core workload feature](media/install-sdk/mac-install-selection.png)](media/install-sdk/mac-install-selection.png#lightbox)</span></span>

::: zone-end

## <a name="install-alongside-visual-studio-code"></a><span data-ttu-id="c61f2-161">Visual Studio Code와 함께 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-161">Install alongside Visual Studio Code</span></span>

<span data-ttu-id="c61f2-162">Visual Studio Code는 데스크톱에서 실행되는 강력한 경량 소스 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-162">Visual Studio Code is a powerful and lightweight source code editor that runs on your desktop.</span></span> <span data-ttu-id="c61f2-163">Visual Studio Code는 Windows, macOS 및 Linux에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-163">Visual Studio Code is available for Windows, macOS, and Linux.</span></span>

<span data-ttu-id="c61f2-164">Visual Studio Code에 Visual Studio처럼 자동화된 .NET Core 설치 프로그램이 포함되지 않은 경우, 간편하게 .NET Core 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-164">While Visual Studio Code doesn't come with an automated .NET Core installer like Visual Studio does, adding .NET Core support is simple.</span></span>

01. <span data-ttu-id="c61f2-165">[Visual Studio Code를 다운로드하여 설치합니다](https://code.visualstudio.com/Download).</span><span class="sxs-lookup"><span data-stu-id="c61f2-165">[Download and install Visual Studio Code](https://code.visualstudio.com/Download).</span></span>
01. <span data-ttu-id="c61f2-166">[.NET Core SDK를 다운로드하여 설치합니다](https://dotnet.microsoft.com/download/dotnet-core).</span><span class="sxs-lookup"><span data-stu-id="c61f2-166">[Download and install the .NET Core SDK](https://dotnet.microsoft.com/download/dotnet-core).</span></span>
01. <span data-ttu-id="c61f2-167">[Visual Studio Code Marketplace에서 C# 확장을 설치합니다](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span><span class="sxs-lookup"><span data-stu-id="c61f2-167">[Install the C# extension from the Visual Studio Code marketplace](https://marketplace.visualstudio.com/items?itemName=ms-vscode.csharp).</span></span>

::: zone pivot="os-windows"

## <a name="install-with-powershell-automation"></a><span data-ttu-id="c61f2-168">PowerShell 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-168">Install with PowerShell automation</span></span>

<span data-ttu-id="c61f2-169">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 SDK의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-169">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="c61f2-170">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-170">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="c61f2-171">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 2.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-171">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="c61f2-172">.NET Core의 최신 릴리스를 설치하려면 다음 스위치와 함께 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-172">To install the current release of .NET Core, run the script with the following switch.</span></span>

```powershell
dotnet-install.ps1 -Channel Current
```

::: zone-end

::: zone pivot="os-linux,os-macos"

## <a name="install-with-bash-automation"></a><span data-ttu-id="c61f2-173">배시 자동화를 사용하여 설치</span><span class="sxs-lookup"><span data-stu-id="c61f2-173">Install with bash automation</span></span>

<span data-ttu-id="c61f2-174">[dotnet-install 스크립트](../tools/dotnet-install-script.md)는 자동화 및 SDK의 관리자가 아닌 일반 설치를 수행하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-174">The [dotnet-install scripts](../tools/dotnet-install-script.md) are used for automation and non-admin installs of the SDK.</span></span> <span data-ttu-id="c61f2-175">스크립트는 [dotnet-install 스크립트 참조 페이지](../tools/dotnet-install-script.md)에서 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-175">You can download the script from the [dotnet-install script reference page](../tools/dotnet-install-script.md).</span></span>

<span data-ttu-id="c61f2-176">스크립트는 기본적으로 최신 [LTS(장기 지원)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) 버전(.NET Core 2.1)을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-176">The script defaults to installing the latest [long term support (LTS)](https://dotnet.microsoft.com/platform/support/policy/dotnet-core) version, which is .NET Core 2.1.</span></span> <span data-ttu-id="c61f2-177">.NET Core의 최신 릴리스를 설치하려면 다음 스위치와 함께 스크립트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-177">To install the current release of .NET Core, run the script with the following switch.</span></span>

```bash
./dotnet-install.sh -c Current
```

::: zone-end

## <a name="all-net-core-downloads"></a><span data-ttu-id="c61f2-178">모든 .NET Core 다운로드</span><span class="sxs-lookup"><span data-stu-id="c61f2-178">All .NET Core downloads</span></span>

<span data-ttu-id="c61f2-179">다음 링크 중 하나를 사용하여 .NET Core를 직접 다운로드하여 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-179">You can download and install .NET Core directly with one of the following links:</span></span>

- [<span data-ttu-id="c61f2-180">.NET Core 3.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="c61f2-180">.NET Core 3.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.1)
- [<span data-ttu-id="c61f2-181">.NET Core 3.0 다운로드</span><span class="sxs-lookup"><span data-stu-id="c61f2-181">.NET Core 3.0 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/3.0)
- [<span data-ttu-id="c61f2-182">.NET Core 2.2 다운로드</span><span class="sxs-lookup"><span data-stu-id="c61f2-182">.NET Core 2.2 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.2)
- [<span data-ttu-id="c61f2-183">.NET Core 2.1 다운로드</span><span class="sxs-lookup"><span data-stu-id="c61f2-183">.NET Core 2.1 downloads</span></span>](https://dotnet.microsoft.com/download/dotnet-core/2.1)

## <a name="docker"></a><span data-ttu-id="c61f2-184">Docker</span><span class="sxs-lookup"><span data-stu-id="c61f2-184">Docker</span></span>

<span data-ttu-id="c61f2-185">컨테이너는 호스트 시스템의 나머지 부분으로부터 애플리케이션을 격리하는 경량 방식을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-185">Containers provide a lightweight way to isolate your application from the rest of the host system.</span></span> <span data-ttu-id="c61f2-186">동일한 머신에 있는 컨테이너는 커널만 공유하고 애플리케이션에 주어진 리소스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-186">Containers on the same machine share just the kernel and use resources given to your application.</span></span>

<span data-ttu-id="c61f2-187">.NET Core는 Docker 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-187">.NET Core can run in a Docker container.</span></span> <span data-ttu-id="c61f2-188">공식 .NET Core Docker 이미지는 MCR(Microsoft 컨테이너 레지스트리)에 게시되며 [Microsoft .NET Core Docker 허브 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core/)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-188">Official .NET Core Docker images are published to the Microsoft Container Registry (MCR) and are discoverable at the [Microsoft .NET Core Docker Hub repository](https://hub.docker.com/_/microsoft-dotnet-core/).</span></span> <span data-ttu-id="c61f2-189">각 리포지토리에는 사용할 수 있는 .NET(SDK 또는 Runtime)과 OS가 다양하게 조합된 이미지가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-189">Each repository contains images for different combinations of the .NET (SDK or Runtime) and OS that you can use.</span></span>

<span data-ttu-id="c61f2-190">Microsoft는 특정 시나리오를 위한 맞춤형 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-190">Microsoft provides images that are tailored for specific scenarios.</span></span> <span data-ttu-id="c61f2-191">예를 들어 [ASP.NET Core 리포지토리](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/)는 프로덕션에서 ASP.NET Core 앱을 실행하기 위해 빌드된 이미지를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c61f2-191">For example, the [ASP.NET Core repository](https://hub.docker.com/_/microsoft-dotnet-core-aspnet/) provides images that are built for running ASP.NET Core apps in production.</span></span>

<span data-ttu-id="c61f2-192">Docker 컨테이너에서 .NET Core를 사용하는 방법에 대한 자세한 내용은 [.NET 및 Docker 소개](../docker/introduction.md)와 [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md)(샘플)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c61f2-192">For more information about using .NET Core in a Docker container, see [Introduction to .NET and Docker](../docker/introduction.md) and [Samples](https://github.com/dotnet/dotnet-docker/blob/master/samples/README.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="c61f2-193">다음 단계</span><span class="sxs-lookup"><span data-stu-id="c61f2-193">Next steps</span></span>

::: zone pivot="os-windows"

- <span data-ttu-id="c61f2-194">[자습서: C# Hello World 자습서](../tutorials/with-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="c61f2-194">[Tutorial: C# Hello World tutorial](../tutorials/with-visual-studio.md).</span></span>
- <span data-ttu-id="c61f2-195">[자습서: Visual Basic Hello World 자습서](../tutorials/vb-with-visual-studio.md)</span><span class="sxs-lookup"><span data-stu-id="c61f2-195">[Tutorial: Visual Basic Hello World tutorial](../tutorials/vb-with-visual-studio.md).</span></span>
- <span data-ttu-id="c61f2-196">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="c61f2-196">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="c61f2-197">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="c61f2-197">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-macos"

- <span data-ttu-id="c61f2-198">[자습서: macOS에서 시작](../tutorials/using-on-mac-vs.md)</span><span class="sxs-lookup"><span data-stu-id="c61f2-198">[Tutorial: Get started on macOS](../tutorials/using-on-mac-vs.md).</span></span>
- <span data-ttu-id="c61f2-199">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="c61f2-199">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="c61f2-200">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="c61f2-200">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end

::: zone pivot="os-linux"

- <span data-ttu-id="c61f2-201">[자습서: Visual Studio Code를 사용하여 새 앱 만들기](../tutorials/with-visual-studio-code.md)</span><span class="sxs-lookup"><span data-stu-id="c61f2-201">[Tutorial: Create a new app with Visual Studio Code](../tutorials/with-visual-studio-code.md).</span></span>
- <span data-ttu-id="c61f2-202">[자습서: .NET Core 앱 컨테이너화](../docker/build-container.md)</span><span class="sxs-lookup"><span data-stu-id="c61f2-202">[Tutorial: Containerize a .NET Core app](../docker/build-container.md).</span></span>

::: zone-end
