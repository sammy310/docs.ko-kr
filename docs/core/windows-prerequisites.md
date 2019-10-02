---
title: Windows에서 .NET Core의 필수 구성 요소
description: Windows 컴퓨터에서 .NET Core 애플리케이션을 개발 및 실행하기 위해 필요한 종속성이 무엇인지 살펴보세요.
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: b1557e6910cb6d0b6d7e2b3ce2aec97d3715fec7
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591667"
---
# <a name="prerequisites-for-net-core-on-windows"></a><span data-ttu-id="b88e2-103">Windows에서 .NET Core의 필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b88e2-103">Prerequisites for .NET Core on Windows</span></span>

<span data-ttu-id="b88e2-104">이 문서에서는 Windows에서 .NET Core 애플리케이션을 실행하도록 지원되는 OS 버전을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-104">This article shows the supported OS versions in order to run .NET Core applications on Windows.</span></span> <span data-ttu-id="b88e2-105">다음에 나오는 지원되는 OS 버전 및 종속성은 Windows에서 .NET Core 앱을 개발하기 위한 세 가지 방법에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-105">The supported OS versions and dependencies that follow apply to the three ways of developing .NET Core apps on Windows:</span></span>

* [<span data-ttu-id="b88e2-106">명령줄</span><span class="sxs-lookup"><span data-stu-id="b88e2-106">Command line</span></span>](./tutorials/using-with-xplat-cli.md)
* [<span data-ttu-id="b88e2-107">Visual Studio</span><span class="sxs-lookup"><span data-stu-id="b88e2-107">Visual Studio</span></span>](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [<span data-ttu-id="b88e2-108">Visual Studio Code</span><span class="sxs-lookup"><span data-stu-id="b88e2-108">Visual Studio Code</span></span>](https://code.visualstudio.com/)

<span data-ttu-id="b88e2-109">또한 Windows에서 Visual Studio를 사용하여 개발하는 경우, [Visual Studio를 사용하여 .NET Core 앱을 개발하기 위한 필수 조건](#prerequisites-to-develop-net-core-apps-with-visual-studio) 섹션에서 .NET Core 개발에 지원되는 최소 버전에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-109">Also, if you're developing on Windows using Visual Studio, the [Prerequisites to develop .NET Core apps with Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio) section goes in more detail about minimum versions supported for .NET Core development.</span></span>

## <a name="net-core-supported-operating-systems"></a><span data-ttu-id="b88e2-110">.NET Core 지원 운영 체제</span><span class="sxs-lookup"><span data-stu-id="b88e2-110">.NET Core supported operating systems</span></span>

<span data-ttu-id="b88e2-111">다음 문서에는 버전별 .NET Core 지원 운영 체제의 전체 목록이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-111">The following articles have a complete list of .NET Core supported operating systems per version:</span></span>

* [<span data-ttu-id="b88e2-112">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b88e2-112">.NET Core 3.0</span></span>](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [<span data-ttu-id="b88e2-113">.NET Core 2.2</span><span class="sxs-lookup"><span data-stu-id="b88e2-113">.NET Core 2.2</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [<span data-ttu-id="b88e2-114">.NET Core 2.1</span><span class="sxs-lookup"><span data-stu-id="b88e2-114">.NET Core 2.1</span></span>](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

<span data-ttu-id="b88e2-115">다운로드 링크 및 자세한 내용은 최신 버전 다운로드의 경우 [.NET 다운로드](https://dotnet.microsoft.com/download)를 참조하고, 이전 버전의 경우 [.NET 다운로드 보관](https://dotnet.microsoft.com/download/archives#dotnet-core)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b88e2-115">For download links and more information, see [.NET downloads](https://dotnet.microsoft.com/download) to download the latest version or [.NET downloads archive](https://dotnet.microsoft.com/download/archives#dotnet-core) for older versions.</span></span>

## <a name="net-core-dependencies"></a><span data-ttu-id="b88e2-116">.NET Core 종속성</span><span class="sxs-lookup"><span data-stu-id="b88e2-116">.NET Core dependencies</span></span>

<span data-ttu-id="b88e2-117">다음과 같은 경우에는 [Microsoft Visual C++ 2015 재배포 가능 패키지 업데이트 3](https://www.microsoft.com/download/details.aspx?id=52685)을 수동으로 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-117">[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) must be manually installed when:</span></span>

* <span data-ttu-id="b88e2-118">[설치 관리자 스크립트](./tools/dotnet-install-script.md)를 사용하여 .NET Core 설치.</span><span class="sxs-lookup"><span data-stu-id="b88e2-118">Installing .NET Core with the [installer script](./tools/dotnet-install-script.md).</span></span>
* <span data-ttu-id="b88e2-119">자체 포함된 .NET Core 애플리케이션 배포.</span><span class="sxs-lookup"><span data-stu-id="b88e2-119">Deploying a self-contained .NET Core application.</span></span>
* <span data-ttu-id="b88e2-120">원본에서 제품 빌드.</span><span class="sxs-lookup"><span data-stu-id="b88e2-120">Building the product from source.</span></span>
* <span data-ttu-id="b88e2-121">*.zip* 파일을 통해 .NET Core 설치.</span><span class="sxs-lookup"><span data-stu-id="b88e2-121">Installing .NET Core via a *.zip* file.</span></span> <span data-ttu-id="b88e2-122">여기에는 빌드/CI/CD 서버가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-122">This can include build/CI/CD servers.</span></span>

> [!NOTE]
> <span data-ttu-id="b88e2-123">**Windows 8.1 이전 버전 또는 Windows Server 2012 R2 이전 버전의 경우:**</span><span class="sxs-lookup"><span data-stu-id="b88e2-123">**For Windows 8.1 and earlier versions, or Windows Server 2012 R2 and earlier versions:**</span></span>
>
> <span data-ttu-id="b88e2-124">설치된 Windows가 최신 버전이며 Windows 업데이트를 통해 설치할 수 있는 [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows)이 포함되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b88e2-124">Make sure that your Windows installation is up-to-date and includes [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), which can be installed through Windows Update.</span></span> <span data-ttu-id="b88e2-125">이 업데이트를 설치하지 않는 경우 .NET Core 애플리케이션을 시작할 때 `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`과 같은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-125">If you don't have this update installed, you'll see an error like the following when you launch a .NET Core application: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`</span></span>
>
> <span data-ttu-id="b88e2-126">**Windows 7 또는 Windows Server 2008 R2의 경우:**</span><span class="sxs-lookup"><span data-stu-id="b88e2-126">**For Windows 7 or Windows Server 2008 R2:**</span></span>
>
> <span data-ttu-id="b88e2-127">KB2999226 외에 [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot)도 설치되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="b88e2-127">In addition to KB2999226, make sure you also have [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot) installed.</span></span> <span data-ttu-id="b88e2-128">이 업데이트를 설치하지 않는 경우 .NET Core 애플리케이션을 시작할 때 `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`와 같은 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-128">If you don't have this update installed, you'll see an error similar to the following when you launch a .NET Core application: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.</span></span>

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a><span data-ttu-id="b88e2-129">Visual Studio를 사용하여 .NET Core 앱을 개발하기 위한 필수 조건</span><span class="sxs-lookup"><span data-stu-id="b88e2-129">Prerequisites to develop .NET Core apps with Visual Studio</span></span>
    
<span data-ttu-id="b88e2-130">임의 편집기로 .NET Core SDK를 사용하여 .NET Core 애플리케이션을 개발할 수 있지만, Visual Studio 2017 이상 버전에서는 Windows용 .NET Core 앱에 대한 통합 개발 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-130">Even though you can use any editor to develop .NET Core applications using the .NET Core SDK, Visual Studio 2017 and later versions provide an integrated development environment for .NET Core apps on Windows.</span></span>

<a name="vs-mapping"></a>

<span data-ttu-id="b88e2-131">.NET Core 버전마다 최소 버전의 Visual Studio가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-131">Each .NET Core version has a minimum version of Visual Studio required.</span></span> <span data-ttu-id="b88e2-132">Visual Studio 버전을 확인하려면</span><span class="sxs-lookup"><span data-stu-id="b88e2-132">To verify your Visual Studio version:</span></span>

* <span data-ttu-id="b88e2-133">**도움말** 메뉴에서 **Microsoft Visual Studio 정보**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-133">On the **Help** menu, choose **About Microsoft Visual Studio**.</span></span>
* <span data-ttu-id="b88e2-134">**Microsoft Visual Studio 정보** 대화 상자에서 버전 번호를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-134">In the **About Microsoft Visual Studio** dialog, verify the version number.</span></span>

<span data-ttu-id="b88e2-135">다음 표에는 각 SDK의 최소 버전이 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-135">The following table lists the minimum version for each SDK:</span></span>

| <span data-ttu-id="b88e2-136">.NET Core SDK 버전</span><span class="sxs-lookup"><span data-stu-id="b88e2-136">.NET Core SDK version</span></span> | <span data-ttu-id="b88e2-137">Visual Studio 버전</span><span class="sxs-lookup"><span data-stu-id="b88e2-137">Visual Studio version</span></span>                      |
| --------------------- | ------------------------------------------ |
| <span data-ttu-id="b88e2-138">3.0</span><span class="sxs-lookup"><span data-stu-id="b88e2-138">3.0</span></span>                   | <span data-ttu-id="b88e2-139">Visual Studio 2019 버전 16.3 이상</span><span class="sxs-lookup"><span data-stu-id="b88e2-139">Visual Studio 2019 version 16.3 or higher.</span></span> |
| <span data-ttu-id="b88e2-140">2.2</span><span class="sxs-lookup"><span data-stu-id="b88e2-140">2.2</span></span>                   | <span data-ttu-id="b88e2-141">Visual Studio 2017 버전 15.9 이상</span><span class="sxs-lookup"><span data-stu-id="b88e2-141">Visual Studio 2017 version 15.9 or higher.</span></span> |
| <span data-ttu-id="b88e2-142">2.1</span><span class="sxs-lookup"><span data-stu-id="b88e2-142">2.1</span></span>                   | <span data-ttu-id="b88e2-143">Visual Studio 2017 버전 15.7 이상</span><span class="sxs-lookup"><span data-stu-id="b88e2-143">Visual Studio 2017 version 15.7 or higher.</span></span> |
| <span data-ttu-id="b88e2-144">1.x</span><span class="sxs-lookup"><span data-stu-id="b88e2-144">1.x</span></span>                   | <span data-ttu-id="b88e2-145">Visual Studio 2017 버전 15.0 이상</span><span class="sxs-lookup"><span data-stu-id="b88e2-145">Visual Studio 2017 version 15.0 or higher.</span></span> |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[<span data-ttu-id="b88e2-146">.NET Core 3.0</span><span class="sxs-lookup"><span data-stu-id="b88e2-146">.NET Core 3.0</span></span>](#tab/netcore30)

<span data-ttu-id="b88e2-147">Visual Studio 2019에서 .NET Core 3.0 SDK를 사용하여 .NET Core 앱을 개발하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-147">To develop .NET Core apps in Visual Studio 2019 using the .NET Core 3.0 SDK:</span></span>

* <span data-ttu-id="b88e2-148">[Visual Studio 2019 버전 16.3 이상을 다운로드하여 설치](/visualstudio/install/install-visual-studio)하고, 빌드하는 애플리케이션 종류에 따라 .NET Core SDK를 포함하는 다음 워크로드 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-148">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) and select one of the following workloads that includes the .NET Core SDK, depending on the kind of application you're building:</span></span>

  * <span data-ttu-id="b88e2-149">**기타 도구 세트** 섹션의 **.NET Core 플랫폼 간 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="b88e2-149">The **.NET Core cross-platform development** workload in the **Other Toolsets** section.</span></span>
  * <span data-ttu-id="b88e2-150">**웹 및 클라우드** 섹션의 **ASP.NET 및 웹 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="b88e2-150">The **ASP.NET and web development** workload in the **Web & Cloud** section.</span></span>
  * <span data-ttu-id="b88e2-151">**Windows** 섹션의 **.NET 데스크톱 개발** 워크로드</span><span class="sxs-lookup"><span data-stu-id="b88e2-151">The **NET desktop development** workload in the **Windows** section.</span></span>

<span data-ttu-id="b88e2-152">다음 이미지는 Visual Studio UI에서 선택된 **.NET Core 플랫폼 간 개발** 워크로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-152">The following image shows the **.NET Core cross-platform development** workload selected in the Visual Studio UI:</span></span>

![“.NET Core 플랫폼 간 개발” 워크로드가 선택된 Visual Studio 2019 설치 스크린샷](./media/windows-prerequisites/vs-2019-workloads.jpg)

<span data-ttu-id="b88e2-154">Visual Studio 2019 16.3에서는 이러한 워크로드 중 하나가 설치된 후 기본적으로 .NET Core 3.0 SDK를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-154">Visual Studio 2019 16.3 uses .NET Core 3.0 SDK by default after any of these workloads are installed.</span></span>

<span data-ttu-id="b88e2-155">기존 프로젝트에서 최신 .NET Core 런타임을 사용하려면, 다음 지침에 따라 기존 .NET Core 프로젝트의 대상을 .NET Core 3.0으로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-155">If you want your existing projects to use the latest .NET Core runtime, retarget each existing .NET Core project to .NET Core 3.0 using the following instructions:</span></span>

* <span data-ttu-id="b88e2-156">**프로젝트** 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-156">On the **Project** menu, choose **Properties**.</span></span>
* <span data-ttu-id="b88e2-157">**대상 프레임워크** 선택 메뉴에서 값을 **.NET Core 3.0**으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-157">In the **Target framework** selection menu, set the value to **.NET Core 3.0**.</span></span>

![“.NET Core 3.0” 대상 프레임워크 메뉴 항목이 선택된 Visual Studio 2019 애플리케이션 프로젝트 속성 스크린샷](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

<span data-ttu-id="b88e2-159">.NET Core 3.0 SDK를 사용하여 Visual Studio를 구성한 후에는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-159">Once you have Visual Studio configured with .NET Core 3.0 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="b88e2-160">기존 .NET Core 1.x 및 2.x 프로젝트를 열고, 빌드하고, 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-160">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="b88e2-161">.NET Core 1.x 및 2.x 프로젝트의 대상을 .NET Core 3.0으로 변경하고 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-161">Retarget .NET Core 1.x and 2.x projects to .NET Core 3.0, build, and run.</span></span>
* <span data-ttu-id="b88e2-162">새로운 .NET Core 3.0 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-162">Create new .NET Core 3.0 projects.</span></span>

# <a name="net-core-2xtabnetcore2x"></a>[<span data-ttu-id="b88e2-163">.NET Core 2.x</span><span class="sxs-lookup"><span data-stu-id="b88e2-163">.NET Core 2.x</span></span>](#tab/netcore2x)

<span data-ttu-id="b88e2-164">Visual Studio 2017에서 .NET Core 2.2 SDK를 사용하여 .NET Core 앱을 개발하려면</span><span class="sxs-lookup"><span data-stu-id="b88e2-164">To develop .NET Core apps in Visual Studio 2017 using the .NET Core 2.2 SDK:</span></span>

* <span data-ttu-id="b88e2-165">**기타 도구 세트** 섹션에서 **.NET Core 플랫폼 간 개발** 워크로드를 선택하고 [Visual Studio 2019 버전 16.3 이상을 다운로드하여 설치](/visualstudio/install/install-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-165">[Download and install Visual Studio 2019 version 16.3 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>
* <span data-ttu-id="b88e2-166">**기타 도구 집합** 섹션에서 **.NET Core 플랫폼 간 개발** 워크로드를 선택하고 [Visual Studio 2017 버전 15.9.0 이상을 다운로드하여 설치](/visualstudio/install/install-visual-studio)합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-166">[Download and install Visual Studio 2017 version 15.9.0 or higher](/visualstudio/install/install-visual-studio) with the **.NET Core cross-platform development** workload (in the **Other Toolsets** section) selected.</span></span>

![".NET Core 플랫폼 간 개발" 워크플로가 선택된 Visual Studio 2017 설치 스크린샷](./media/windows-prerequisites/vs-2017-workloads.jpg)

<span data-ttu-id="b88e2-168">**.NET Core 플랫폼 간 개발** 도구 집합이 설치된 후 Visual Studio에서는 일반적으로 이전 버전의 .NET Core SDK를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-168">After the **.NET Core cross-platform development** toolset is installed, Visual Studio usually installs a previous version of the .NET Core SDK.</span></span>
<span data-ttu-id="b88e2-169">예를 들어 Visual Studio 2017 15.9에서는 워크로드가 설치된 후 기본적으로 .NET Core 2.1 SDK를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-169">For example, Visual Studio 2017 15.9 uses .NET Core 2.1 SDK by default after the workload is installed.</span></span>

<span data-ttu-id="b88e2-170">.NET Core 2.2 SDK를 사용하도록 Visual Studio를 업데이트하려면</span><span class="sxs-lookup"><span data-stu-id="b88e2-170">To update Visual Studio to use .NET Core 2.2 SDK:</span></span>

 1. <span data-ttu-id="b88e2-171">[.NET Core 2.2 SDK](https://dotnet.microsoft.com/download)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-171">Install the [.NET Core 2.2 SDK](https://dotnet.microsoft.com/download).</span></span>

 1. <span data-ttu-id="b88e2-172">프로젝트에서 최신 .NET Core 런타임을 사용하려면, 다음 지침에 따라 기존 또는 새 .NET Core 프로젝트의 대상을 각각 .NET Core 2.2로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-172">If you want your project to use the latest .NET Core runtime, retarget each existing or new .NET Core project to .NET Core 2.2 using the following instructions:</span></span>

    * <span data-ttu-id="b88e2-173">**프로젝트** 메뉴에서 **속성**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-173">On the **Project** menu, choose **Properties**.</span></span>
    * <span data-ttu-id="b88e2-174">**대상 프레임워크** 선택 메뉴에서 값을 **.NET Core 2.2**로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-174">In the **Target framework** selection menu, set the value to **.NET Core 2.2**.</span></span>

![“.NET Core 2.2” 대상 프레임워크 메뉴 항목이 선택된 Visual Studio 2017 애플리케이션 프로젝트 속성 스크린샷](./media/windows-prerequisites/targeting-dotnet-core.jpg)

<span data-ttu-id="b88e2-176">.NET Core 2.2 SDK를 사용하여 Visual Studio를 구성한 후에는 다음 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-176">Once you have Visual Studio configured with .NET Core 2.2 SDK, you can do the following actions:</span></span>

* <span data-ttu-id="b88e2-177">기존 .NET Core 1.x 및 2.x 프로젝트를 열고, 빌드하고, 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-177">Open, build, and run existing .NET Core 1.x and 2.x projects.</span></span>
* <span data-ttu-id="b88e2-178">.NET Core 1.x 및 2.x 프로젝트의 대상을 .NET Core 2.2로 변경하고 빌드 및 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-178">Retarget .NET Core 1.x and 2.x projects to .NET Core 2.2, build, and run.</span></span>
* <span data-ttu-id="b88e2-179">새로운 .NET Core 2.2 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b88e2-179">Create new .NET Core 2.2 projects.</span></span>

---
