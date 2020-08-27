---
title: Visual Studio를 사용하여 .NET Core 앱 배포
description: Visual Studio를 사용하여 .NET Core 앱을 배포하는 방법을 알아봅니다.
ms.date: 09/03/2018
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 73eee58a3d11f2f898a6d57cb282ccf4e802cdca
ms.sourcegitcommit: c4a15c6c4ecbb8a46ad4e67d9b3ab9b8b031d849
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/20/2020
ms.locfileid: "88656601"
---
# <a name="deploy-net-core-apps-with-visual-studio"></a><span data-ttu-id="a4f6c-103">Visual Studio를 사용하여 .NET Core 앱 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-103">Deploy .NET Core apps with Visual Studio</span></span>

<span data-ttu-id="a4f6c-104">.NET Core 애플리케이션은 애플리케이션 이진을 포함하지만 대상 시스템에 .NET Core가 있는지 여부에 따라 달라지는 *프레임워크 종속 배포* 또는 애플리케이션과 .NET Core 이진을 모두 포함하는 *자체 포함 배포*로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-104">You can deploy a .NET Core application either as a *framework-dependent deployment*, which includes your application binaries but depends on the presence of .NET Core on the target system, or as a *self-contained deployment*, which includes both your application and .NET Core binaries.</span></span> <span data-ttu-id="a4f6c-105">.NET Core 애플리케이션 배포 개요는 [.NET Core 애플리케이션 배포](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-105">For an overview of .NET Core application deployment, see [.NET Core Application Deployment](index.md).</span></span>

<span data-ttu-id="a4f6c-106">다음 섹션에서는 Microsoft Visual Studio를 사용하여 다음과 같은 종류의 배포를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-106">The following sections show how to use Microsoft Visual Studio to create the following kinds of deployments:</span></span>

- <span data-ttu-id="a4f6c-107">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-107">Framework-dependent deployment</span></span>
- <span data-ttu-id="a4f6c-108">타사 종속성이 있는 프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-108">Framework-dependent deployment with third-party dependencies</span></span>
- <span data-ttu-id="a4f6c-109">자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-109">Self-contained deployment</span></span>
- <span data-ttu-id="a4f6c-110">타사 종속성이 있는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-110">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="a4f6c-111">Visual Studio를 사용하여 .NET Core 애플리케이션을 개발하는 방법에 대한 자세한 내용은 [.NET Core 종속성 및 요구 사항](../install/dependencies.md?pivots=os-windows)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-111">For information on using Visual Studio to develop .NET Core applications, see [.NET Core dependencies and requirements](../install/dependencies.md?pivots=os-windows).</span></span>

## <a name="framework-dependent-deployment"></a><span data-ttu-id="a4f6c-112">프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-112">Framework-dependent deployment</span></span>

<span data-ttu-id="a4f6c-113">타사 종속성이 없는 프레임워크 종속 배포에는 앱의 빌드, 테스트 및 게시만 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-113">Deploying a framework-dependent deployment with no third-party dependencies simply involves building, testing, and publishing the app.</span></span> <span data-ttu-id="a4f6c-114">C#으로 작성된 간단한 예제에서는 이 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-114">A simple example written in C# illustrates the process.</span></span>

1. <span data-ttu-id="a4f6c-115">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-115">Create the project.</span></span>

   <span data-ttu-id="a4f6c-116">**파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-116">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="a4f6c-117">**새 프로젝트** 대화 상자에서 **설치된** 프로젝트 형식 창에서 언어(C# 또는 Visual Basic)의 프로젝트 범주를 확장하고 **.NET Core**를 선택한 다음, 가운데 창에 있는 **콘솔 앱(.NET Core)** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-117">In the **New Project** dialog, expand your language's (C# or Visual Basic) project categories in the **Installed** project types pane, choose **.NET Core**, and then select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="a4f6c-118">**이름** 텍스트 상자에 "FDD" 등의 프로젝트 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-118">Enter a project name, such as "FDD", in the **Name** text box.</span></span> <span data-ttu-id="a4f6c-119">**확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-119">Select the **OK** button.</span></span>

1. <span data-ttu-id="a4f6c-120">애플리케이션의 소스 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-120">Add the application's source code.</span></span>

   <span data-ttu-id="a4f6c-121">편집기에서 *Program.cs* 또는 *Program.vb* 파일을 열고 자동 생성된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-121">Open the *Program.cs* or *Program.vb* file in the editor and replace the autogenerated code with the following code.</span></span> <span data-ttu-id="a4f6c-122">텍스트를 입력하라는 메시지가 표시된 다음 사용자가 입력한 개별 단어가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-122">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="a4f6c-123">정규식 `\w+`를 사용하여 입력 테스트의 단어를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-123">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](./snippets/deploy-with-vs/csharp/deployment-example.cs)]
   [!code-vb[deployment#1](./snippets/deploy-with-vs/vb/deployment-example.vb)]

1. <span data-ttu-id="a4f6c-124">앱의 디버그 빌드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-124">Create a Debug build of your app.</span></span>

   <span data-ttu-id="a4f6c-125">**빌드** > **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-125">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="a4f6c-126">**디버그** > **디버깅 시작**을 선택하여 애플리케이션의 디버그 빌드를 컴파일하고 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-126">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="a4f6c-127">앱을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-127">Deploy your app.</span></span>

   <span data-ttu-id="a4f6c-128">프로그램을 디버그하고 테스트한 후에는 앱과 함께 배포할 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-128">After you've debugged and tested the program, create the files to be deployed with your app.</span></span> <span data-ttu-id="a4f6c-129">Visual Studio에서 게시하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-129">To publish from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="a4f6c-130">도구 모음에서 솔루션 구성을 **디버그**에서 **릴리스**로 변경하여 앱의 릴리스(디버그 아님) 버전을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-130">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="a4f6c-131">**솔루션 탐색기**에서 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-131">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

      1. <span data-ttu-id="a4f6c-132">**게시** 탭에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-132">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="a4f6c-133">Visual Studio에서 애플리케이션을 구성하는 파일을 로컬 파일 시스템에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-133">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="a4f6c-134">이제 **게시** 탭에 단일 프로필 **FolderProfile**이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-134">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="a4f6c-135">프로필의 구성 설정이 탭의 **요약** 섹션에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-135">The profile's configuration settings are shown in the **Summary** section of the tab.</span></span>

   <span data-ttu-id="a4f6c-136">결과 파일은 프로젝트 *.\bin\release\netcoreapp2.1* 하위 디렉터리의 하위 디렉터리에 있는 Windows의 경우에는 `Publish`, Unix 시스템의 경우에는 `publish`이라는 디렉터리에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-136">The resulting files are placed in a directory named `Publish` on Windows and `publish` on Unix systems that is in a subdirectory of your project's *.\bin\release\netcoreapp2.1* subdirectory.</span></span>

<span data-ttu-id="a4f6c-137">게시 프로세스에서는 애플리케이션의 파일과 함께 앱에 대한 디버깅 정보를 포함하는 프로그램 데이터베이스(.pdb) 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-137">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="a4f6c-138">이 파일은 주로 예외 디버그에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-138">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="a4f6c-139">애플리케이션 파일과 함께 패키지하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-139">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="a4f6c-140">하지만 앱의 릴리스 빌드를 디버그하려는 경우 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-140">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="a4f6c-141">애플리케이션 파일의 전체 집합을 원하는 방식으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-141">Deploy the complete set of application files in any way you like.</span></span> <span data-ttu-id="a4f6c-142">예를 들어 Zip 파일로 패키지하거나, 간단한 `copy` 명령을 사용하거나, 선택한 설치 패키지와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-142">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span> <span data-ttu-id="a4f6c-143">설치되고 나면 사용자가 `dotnet` 명령을 사용하고 `dotnet fdd.dll` 등의 애플리케이션 파일 이름을 제공하여 애플리케이션을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-143">Once installed, users can then execute your application by using the `dotnet` command and providing the application filename, such as `dotnet fdd.dll`.</span></span>

<span data-ttu-id="a4f6c-144">설치 관리자는 애플리케이션 이진 외에도 공유 프레임워크 설치 관리자를 번들로 제공하거나 애플리케이션 설치의 일부로 필수 조건을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-144">In addition to the application binaries, your installer should also either bundle the shared framework installer or check for it as a prerequisite as part of the application installation.</span></span>  <span data-ttu-id="a4f6c-145">공유 프레임워크 설치는 시스템 수준이므로 관리자/루트 액세스 권한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-145">Installation of the shared framework requires Administrator/root access since it is machine-wide.</span></span>

## <a name="framework-dependent-deployment-with-third-party-dependencies"></a><span data-ttu-id="a4f6c-146">타사 종속성이 있는 프레임워크 종속 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-146">Framework-dependent deployment with third-party dependencies</span></span>

<span data-ttu-id="a4f6c-147">하나 이상의 타사 종속성이 있는 프레임워크 종속 배포를 배포하려면 프로젝트에서 모든 종속성을 사용할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-147">Deploying a framework-dependent deployment with one or more third-party dependencies requires that any dependencies be available to your project.</span></span> <span data-ttu-id="a4f6c-148">다음 추가 단계를 수행해야 앱을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-148">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="a4f6c-149">**NuGet 패키지 관리자**를 사용하여 NuGet 패키지에 대한 참조를 프로젝트에 추가하고, 시스템에서 패키지를 사용할 수 없는 경우 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-149">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="a4f6c-150">패키지 관리자를 열려면 **도구** > **NuGet 패키지 관리자** > **솔루션용 NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-150">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="a4f6c-151">타사 종속성(예: `Newtonsoft.Json`)이 시스템에 설치되어 있는지 확인하고 그렇지 않은 경우 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-151">Confirm that your third-party dependencies (for example, `Newtonsoft.Json`) are installed on your system and, if they aren't, install them.</span></span> <span data-ttu-id="a4f6c-152">**설치됨** 탭에 시스템에 설치된 NuGet 패키지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-152">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="a4f6c-153">`Newtonsoft.Json`이 탭에 표시되지 않는 경우 **찾아보기** 탭을 선택하고 검색 상자에 "Newtonsoft.Json"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-153">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="a4f6c-154">`Newtonsoft.Json`을 선택하고 오른쪽 창에서 해당 프로젝트를 선택한 후 **설치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-154">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="a4f6c-155">`Newtonsoft.Json`이 시스템에 이미 설치되어 있는 경우 **솔루션용 패키지 관리** 탭의 오른쪽 창에서 해당 프로젝트를 선택하여 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-155">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="a4f6c-156">타사 종속성이 있는 프레임워크 종속 배포는 타사 종속성만큼만 이식 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-156">A framework-dependent deployment with third-party dependencies is only as portable as its third-party dependencies.</span></span> <span data-ttu-id="a4f6c-157">예를 들어 타사 라이브러리에서 macOS를 지원하는 경우 Windows 시스템에 앱을 이식할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-157">For example, if a third-party library only supports macOS, the app isn't portable to Windows systems.</span></span> <span data-ttu-id="a4f6c-158">이러한 현상은 타사 종속성 자체가 네이티브 코드에 종속된 경우에 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-158">This happens if the third-party dependency itself depends on native code.</span></span> <span data-ttu-id="a4f6c-159">관련된 좋은 예로 [libuv](https://github.com/libuv/libuv)에 대한 기본 종속성이 필요한 [Kestrel 서버](/aspnet/core/fundamentals/servers/kestrel)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-159">A good example of this is [Kestrel server](/aspnet/core/fundamentals/servers/kestrel), which requires a native dependency on [libuv](https://github.com/libuv/libuv).</span></span> <span data-ttu-id="a4f6c-160">이런 종류의 타사 종속성이 있는 애플리케이션에 대해 FDD를 만들면 게시된 출력에는 기본 종속성에서 지원하고 NuGet 패키지에 있는 각 [RID(런타임 식별자)](../rid-catalog.md)에 대한 폴더가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-160">When an FDD is created for an application with this kind of third-party dependency, the published output contains a folder for each [Runtime Identifier (RID)](../rid-catalog.md) that the native dependency supports (and that exists in its NuGet package).</span></span>

## <a name="self-contained-deployment-without-third-party-dependencies"></a><a name="simpleSelf"></a> <span data-ttu-id="a4f6c-161">타사 종속성이 없는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-161">Self-contained deployment without third-party dependencies</span></span>

<span data-ttu-id="a4f6c-162">타사 종속성이 없는 자체 포함 배포에는 프로젝트 만들기, *csproj* 파일 수정, 앱 빌드, 테스트 및 게시가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-162">Deploying a self-contained deployment with no third-party dependencies involves creating the project, modifying the *csproj* file, building, testing, and publishing the app.</span></span> <span data-ttu-id="a4f6c-163">C#으로 작성된 간단한 예제에서는 이 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-163">A simple example written in C# illustrates the process.</span></span> <span data-ttu-id="a4f6c-164">프레임워크 종속 배포와 마찬가지로 프로젝트를 생성, 코딩 및 테스트하는 것으로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-164">You begin by creating, coding, and testing your project just as you would a framework-dependent deployment:</span></span>

1. <span data-ttu-id="a4f6c-165">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-165">Create the project.</span></span>

   <span data-ttu-id="a4f6c-166">**파일** > **새로 만들기** > **프로젝트**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-166">Select **File** > **New** > **Project**.</span></span> <span data-ttu-id="a4f6c-167">**새 프로젝트** 대화 상자에서 **설치된** 프로젝트 형식 창에서 언어(C# 또는 Visual Basic)의 프로젝트 범주를 확장하고 **.NET Core**를 선택한 다음, 가운데 창에 있는 **콘솔 앱(.NET Core)** 템플릿을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-167">In the **New Project** dialog, expand your language's (C# or Visual Basic) project categories in the **Installed** project types pane, choose **.NET Core**, and then select the **Console App (.NET Core)** template in the center pane.</span></span> <span data-ttu-id="a4f6c-168">**이름** 텍스트 상자에 "SCD" 등의 프로젝트 이름을 입력하고 **확인** 단추를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-168">Enter a project name, such as "SCD", in the **Name** text box, and select the **OK** button.</span></span>

1. <span data-ttu-id="a4f6c-169">애플리케이션의 소스 코드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-169">Add the application's source code.</span></span>

   <span data-ttu-id="a4f6c-170">편집기에서 *Program.cs* 또는 *Program.vb* 파일을 열고 자동 생성된 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-170">Open the *Program.cs* or *Program.vb* file in your editor, and replace the autogenerated code with the following code.</span></span> <span data-ttu-id="a4f6c-171">텍스트를 입력하라는 메시지가 표시된 다음 사용자가 입력한 개별 단어가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-171">It prompts the user to enter text and displays the individual words entered by the user.</span></span> <span data-ttu-id="a4f6c-172">정규식 `\w+`를 사용하여 입력 테스트의 단어를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-172">It uses the regular expression `\w+` to separate the words in the input text.</span></span>

   [!code-csharp[deployment#1](./snippets/deploy-with-vs/csharp/deployment-example.cs)]
   [!code-vb[deployment#1](./snippets/deploy-with-vs/vb/deployment-example.vb)]

1. <span data-ttu-id="a4f6c-173">세계화 고정 모드를 사용할 것인지 여부를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-173">Determine whether you want to use globalization invariant mode.</span></span>

   <span data-ttu-id="a4f6c-174">특히 앱이 Linux를 대상으로 하는 경우 [세계화 고정 모드](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md)를 활용하여 배포의 총 크기를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-174">Particularly if your app targets Linux, you can reduce the total size of your deployment by taking advantage of [globalization invariant mode](https://github.com/dotnet/runtime/blob/master/docs/design/features/globalization-invariant-mode.md).</span></span> <span data-ttu-id="a4f6c-175">세계화 고정 모드는 전역적으로 인식되지 않는 서식 지정 규칙, 대/소문자 규칙 및 문자열 비교와 [고정 문화권](xref:System.Globalization.CultureInfo.InvariantCulture)의 정렬 순서를 사용할 수 있는 애플리케이션에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-175">Globalization invariant mode is useful for applications that are not globally aware and that can use the formatting conventions, casing conventions, and string comparison and sort order of the [invariant culture](xref:System.Globalization.CultureInfo.InvariantCulture).</span></span>

   <span data-ttu-id="a4f6c-176">고정 모드를 사용하려면 **솔루션 탐색기**에서 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **SCD.csproj 편집** 또는 **SCD.vbproj 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-176">To enable invariant mode, right-click on your project (not the solution) in **Solution Explorer**, and select **Edit SCD.csproj** or **Edit SCD.vbproj**.</span></span> <span data-ttu-id="a4f6c-177">그런 다음, 강조 표시된 다음 줄을 파일에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-177">Then add the following highlighted lines to the file:</span></span>

   [!code-xml[globalization-invariant-mode](./snippets/deploy-with-vs/xml/invariant.csproj?highlight=7-9)]

1. <span data-ttu-id="a4f6c-178">애플리케이션의 디버그 빌드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-178">Create a Debug build of your application.</span></span>

   <span data-ttu-id="a4f6c-179">**빌드** > **솔루션 빌드**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-179">Select **Build** > **Build Solution**.</span></span> <span data-ttu-id="a4f6c-180">**디버그** > **디버깅 시작**을 선택하여 애플리케이션의 디버그 빌드를 컴파일하고 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-180">You can also compile and run the Debug build of your application by selecting **Debug** > **Start Debugging**.</span></span> <span data-ttu-id="a4f6c-181">이 디버깅 단계를 통해 애플리케이션이 호스트 플랫폼에서 실행될 때 발생하는 문제를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-181">This debugging step lets you identify problems with your application when it's running on your host platform.</span></span> <span data-ttu-id="a4f6c-182">여전히 각 대상 플랫폼에서 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-182">You still will have to test it on each of your target platforms.</span></span>

   <span data-ttu-id="a4f6c-183">세계화 고정 모드를 사용하도록 설정한 경우, 특히 문화권 중요 데이터의 부재가 애플리케이션에 적합한지 여부를 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-183">If you've enabled globalization invariant mode, be particularly sure to test whether the absence of culture-sensitive data is suitable for your application.</span></span>

<span data-ttu-id="a4f6c-184">디버깅이 완료되면 자체 포함 배포를 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-184">Once you've finished debugging, you can publish your self-contained deployment:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="visual-studio-156-and-earlier"></a>[<span data-ttu-id="a4f6c-185">Visual Studio 15.6 및 이전 버전</span><span class="sxs-lookup"><span data-stu-id="a4f6c-185">Visual Studio 15.6 and earlier</span></span>](#tab/vs156)

<span data-ttu-id="a4f6c-186">프로그램을 디버그하고 테스트한 후에는 각 대상 플랫폼에 대해 앱과 함께 배포할 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-186">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

<span data-ttu-id="a4f6c-187">Visual Studio에서 앱을 게시하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-187">To publish your app from Visual Studio, do the following:</span></span>

1. <span data-ttu-id="a4f6c-188">앱의 대상 플랫폼을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-188">Define the platforms that your app will target.</span></span>

   1. <span data-ttu-id="a4f6c-189">**솔루션 탐색기**에서 해당 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **SCD.csproj 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-189">Right-click on your project (not the solution) in **Solution Explorer** and select **Edit SCD.csproj**.</span></span>

   1. <span data-ttu-id="a4f6c-190">*csproj* 파일의 `<PropertyGroup>` 섹션에서 앱의 대상 플랫폼을 정의하는 `<RuntimeIdentifiers>` 태그를 만들고 각 대상 플랫폼의 RID(런타임 식별자)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-190">Create a `<RuntimeIdentifiers>` tag in the `<PropertyGroup>` section of your *csproj* file that defines the platforms your app targets, and specify the runtime identifier (RID) of each platform that you target.</span></span> <span data-ttu-id="a4f6c-191">RID를 구분하려면 세미콜론도 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-191">You also need to add a semicolon to separate the RIDs.</span></span> <span data-ttu-id="a4f6c-192">런타임 식별자 목록은 [런타임 식별자 카탈로그](../rid-catalog.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-192">See [Runtime identifier catalog](../rid-catalog.md) for a list of runtime identifiers.</span></span>

   <span data-ttu-id="a4f6c-193">예를 들어 다음 예에서는 앱이 64비트 Windows 10 운영 체제 및 64비트 OS X 버전 10.11 운영 체제에서 실행됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-193">For example, the following example indicates that the app runs on 64-bit Windows 10 operating systems and the 64-bit OS X Version 10.11 operating system.</span></span>

   ```xml
   <PropertyGroup>
      <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
   </PropertyGroup>
   ```

   <span data-ttu-id="a4f6c-194">`<RuntimeIdentifiers>` 요소는 *csproj* 파일에 있는 `<PropertyGroup>`으로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-194">The `<RuntimeIdentifiers>` element can go into any `<PropertyGroup>` that you have in your *csproj* file.</span></span> <span data-ttu-id="a4f6c-195">전체 샘플 *csproj* 파일은 이 섹션의 뒷부분에 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-195">A complete sample *csproj* file appears later in this section.</span></span>

1. <span data-ttu-id="a4f6c-196">앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-196">Publish your app.</span></span>

   <span data-ttu-id="a4f6c-197">프로그램을 디버그하고 테스트한 후에는 각 대상 플랫폼에 대해 앱과 함께 배포할 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-197">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span>

   <span data-ttu-id="a4f6c-198">Visual Studio에서 앱을 게시하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-198">To publish your app from Visual Studio, do the following:</span></span>

      1. <span data-ttu-id="a4f6c-199">도구 모음에서 솔루션 구성을 **디버그**에서 **릴리스**로 변경하여 앱의 릴리스(디버그 아님) 버전을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-199">Change the solution configuration from **Debug** to **Release** on the toolbar to build a Release (rather than a Debug) version of your app.</span></span>

      1. <span data-ttu-id="a4f6c-200">**솔루션 탐색기**에서 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-200">Right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

      1. <span data-ttu-id="a4f6c-201">**게시** 탭에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-201">In the **Publish** tab, select **Publish**.</span></span> <span data-ttu-id="a4f6c-202">Visual Studio에서 애플리케이션을 구성하는 파일을 로컬 파일 시스템에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-202">Visual Studio writes the files that comprise your application to the local file system.</span></span>

      1. <span data-ttu-id="a4f6c-203">이제 **게시** 탭에 단일 프로필 **FolderProfile**이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-203">The **Publish** tab now shows a single profile, **FolderProfile**.</span></span> <span data-ttu-id="a4f6c-204">프로필의 구성 설정이 탭의 **요약** 섹션에 표시됩니다. **대상 런타임**은 게시된 런타임을 식별하고, **대상 위치**는 자체 포함 배포의 파일이 작성된 위치를 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-204">The profile's configuration settings are shown in the **Summary** section of the tab. **Target Runtime** identifies which runtime has been published, and **Target Location** identifies where the files for the self-contained deployment were written.</span></span>

      1. <span data-ttu-id="a4f6c-205">Visual Studio는 기본적으로 게시된 모든 파일을 단일 디렉터리에 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-205">Visual Studio by default writes all published files to a single directory.</span></span> <span data-ttu-id="a4f6c-206">편의상, 각 대상 런타임에 대해 별도 프로필을 만들고 게시된 파일을 플랫폼별 디렉터리에 배치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-206">For convenience, it's best to create separate profiles for each target runtime and to place published files in a platform-specific directory.</span></span> <span data-ttu-id="a4f6c-207">이렇게 하려면 각 대상 플랫폼에 대해 별도 게시 프로필을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-207">This involves creating a separate publishing profile for each target platform.</span></span> <span data-ttu-id="a4f6c-208">따라서 이제 다음을 수행하여 각 플랫폼용 애플리케이션을 다시 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-208">So now rebuild the application for each platform by doing the following:</span></span>

         1. <span data-ttu-id="a4f6c-209">**게시** 대화 상자에서 **새 프로필 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-209">Select **Create new profile** in the **Publish** dialog.</span></span>

         1. <span data-ttu-id="a4f6c-210">**게시 대상 선택** 대화 상자에서 **폴더 선택** 위치를 *bin\Release\PublishOutput\win10-x64*로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-210">In the **Pick a publish target** dialog, change the **Choose a folder** location to *bin\Release\PublishOutput\win10-x64*.</span></span> <span data-ttu-id="a4f6c-211">**확인**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-211">Select **OK**.</span></span>

         1. <span data-ttu-id="a4f6c-212">프로필 목록에서 새 프로필(**FolderProfile1**)을 선택하고, **대상 런타임**이 `win10-x64`인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-212">Select the new profile (**FolderProfile1**) in the list of profiles, and make sure that the **Target Runtime** is `win10-x64`.</span></span> <span data-ttu-id="a4f6c-213">아닌 경우 **설정**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-213">If it isn't, select **Settings**.</span></span> <span data-ttu-id="a4f6c-214">**프로필 설정** 대화 상자에서 **대상 런타임**을 `win10-x64`로 변경하고 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-214">In the **Profile Settings** dialog, change the **Target Runtime** to `win10-x64` and select **Save**.</span></span> <span data-ttu-id="a4f6c-215">그렇지 않으면 **취소**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-215">Otherwise, select **Cancel**.</span></span>

         1. <span data-ttu-id="a4f6c-216">**게시**를 선택하여 64비트 Windows 10 플랫폼용 앱을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-216">Select **Publish** to publish your app for 64-bit Windows 10 platforms.</span></span>

         1. <span data-ttu-id="a4f6c-217">앞의 단계를 다시 수행하여 `osx.10.11-x64` 플랫폼용 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-217">Follow the previous steps again to create a profile for the `osx.10.11-x64` platform.</span></span> <span data-ttu-id="a4f6c-218">**대상 위치**는 *bin\Release\PublishOutput\osx.10.11-x64*이고, **대상 런타임**은 `osx.10.11-x64`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-218">The **Target Location** is *bin\Release\PublishOutput\osx.10.11-x64*, and the **Target Runtime** is `osx.10.11-x64`.</span></span> <span data-ttu-id="a4f6c-219">Visual Studio에서 이 프로필에 할당하는 이름은 **FolderProfile2**입니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-219">The name that Visual Studio assigns to this profile is **FolderProfile2**.</span></span>

      <span data-ttu-id="a4f6c-220">각 대상 위치에는 앱을 시작하는 데 필요한 전체 파일 집합(앱 파일 및 모든 .NET Core 파일)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-220">Each target location contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="a4f6c-221">게시 프로세스에서는 애플리케이션의 파일과 함께 앱에 대한 디버깅 정보를 포함하는 프로그램 데이터베이스(.pdb) 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-221">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="a4f6c-222">이 파일은 주로 예외 디버그에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-222">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="a4f6c-223">애플리케이션 파일과 함께 패키지하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-223">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="a4f6c-224">하지만 앱의 릴리스 빌드를 디버그하려는 경우 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-224">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="a4f6c-225">게시된 파일을 원하는 방식으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-225">Deploy the published files in any way you like.</span></span> <span data-ttu-id="a4f6c-226">예를 들어 Zip 파일로 패키지하거나, 간단한 `copy` 명령을 사용하거나, 선택한 설치 패키지와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-226">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="a4f6c-227">다음은 이 프로젝트에 대한 전체 *csproj* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-227">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
</Project>
```

# <a name="visual-studio-157-and-later"></a>[<span data-ttu-id="a4f6c-228">Visual Studio 15.7 이상</span><span class="sxs-lookup"><span data-stu-id="a4f6c-228">Visual Studio 15.7 and later</span></span>](#tab/vs157)

<span data-ttu-id="a4f6c-229">프로그램을 디버그하고 테스트한 후에는 각 대상 플랫폼에 대해 앱과 함께 배포할 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-229">After you've debugged and tested the program, create the files to be deployed with your app for each platform that it targets.</span></span> <span data-ttu-id="a4f6c-230">이렇게 하려면 각 대상 플랫폼에 대해 별도의 프로필을 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-230">This involves creating a separate profile for each target platform.</span></span>

<span data-ttu-id="a4f6c-231">애플리케이션이 대상으로 하는 각 플랫폼에 대해 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-231">For each platform that your application targets, do the following:</span></span>

1. <span data-ttu-id="a4f6c-232">대상 플랫폼에 대한 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-232">Create a profile for your target platform.</span></span>

   <span data-ttu-id="a4f6c-233">이것이 첫 번째 프로필인 경우 **솔루션 탐색기**에서 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-233">If this is the first profile you've created, right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

   <span data-ttu-id="a4f6c-234">프로필을 이미 만든 경우 프로젝트를 마우스 오른쪽 단추로 클릭하여 **게시** 대화 상자를 엽니다(아직 열려 있지 않은 경우).</span><span class="sxs-lookup"><span data-stu-id="a4f6c-234">If you've already created a profile, right-click on the project to open the **Publish** dialog if it isn't already open.</span></span> <span data-ttu-id="a4f6c-235">그런 다음, **새 프로필**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-235">Then select **New Profile**.</span></span>

   <span data-ttu-id="a4f6c-236">**게시 대상 선택** 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-236">The **Pick a Publish Target** dialog box opens.</span></span>

1. <span data-ttu-id="a4f6c-237">Visual Studio에서 애플리케이션을 게시하는 위치를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-237">Select the location where Visual Studio publishes your application.</span></span>

   <span data-ttu-id="a4f6c-238">단일 플랫폼에만 게시하는 경우 **폴더 선택** 텍스트 상자의 기본값을 적용합니다. 이렇게 하면 애플리케이션의 프레임워크 종속 배포를 *\<project-directory>\bin\Release\netcoreapp2.1\publish* 디렉터리에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-238">If you're only publishing to a single platform, you can accept the default value in the **Choose a folder** text box; this publishes the framework-dependent deployment of your application to the *\<project-directory>\bin\Release\netcoreapp2.1\publish* directory.</span></span>

   <span data-ttu-id="a4f6c-239">둘 이상의 플랫폼에 게시하는 경우 대상 플랫폼을 식별하는 문자열을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-239">If you're publishing to more than one platform, append a string that identifies the target platform.</span></span> <span data-ttu-id="a4f6c-240">예를 들어, 파일 경로에 “linux” 문자열을 추가하면 Visual Studio는 애플리케이션의 프레임워크 종속 배포를 *\<project-directory>\bin\Release\netcoreapp2.1\publish\linux* 디렉터리에 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-240">For example, if you append the string "linux" to the file path, Visual Studio publishes the framework-dependent deployment of your application to the *\<project-directory>\bin\Release\netcoreapp2.1\publish\linux* directory.</span></span>

1. <span data-ttu-id="a4f6c-241">**게시** 단추 옆에 있는 드롭다운 목록 아이콘을 선택하고 **프로필 만들기**를 선택하여 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-241">Create the profile by selecting the drop-down list icon next to the **Publish** button and selecting **Create Profile**.</span></span> <span data-ttu-id="a4f6c-242">그런 다음, **프로필 만들기** 단추를 선택하여 프로필을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-242">Then select the **Create Profile** button to create the profile.</span></span>

1. <span data-ttu-id="a4f6c-243">자체 포함 배포를 게시 중임을 나타내고 앱이 대상으로 하는 플랫폼을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-243">Indicate that you are publishing a self-contained deployment and define a platform that your app will target.</span></span>

   1. <span data-ttu-id="a4f6c-244">**게시** 대화 상자에서 **구성** 링크를 선택하여 **프로필 설정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-244">In the **Publish** dialog, select the **Configure** link to open the **Profile Settings** dialog.</span></span>

   1. <span data-ttu-id="a4f6c-245">**배포 모드** 목록 상자에서 **자체 포함**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-245">Select **Self-contained** in the **Deployment Mode** list box.</span></span>

   1. <span data-ttu-id="a4f6c-246">**대상 런타임** 목록 상자에서 애플리케이션이 대상으로 하는 플랫폼 중 하나를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-246">In the **Target Runtime** list box, select one of the platforms that your application targets.</span></span>

   1. <span data-ttu-id="a4f6c-247">**저장**을 선택하여 변경 내용을 적용하고 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-247">Select **Save** to accept your changes and close the dialog.</span></span>

1. <span data-ttu-id="a4f6c-248">프로필 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-248">Name your profile.</span></span>

   1. <span data-ttu-id="a4f6c-249">**작업** > **프로필 이름 바꾸기**를 선택하여 프로필 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-249">Select **Actions** > **Rename Profile** to name your profile.</span></span>

   2. <span data-ttu-id="a4f6c-250">프로필에 대상 플랫폼을 식별하는 이름을 할당한 다음, \**저장*을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-250">Assign your profile a name that identifies the target platform, then select \**Save*.</span></span>

<span data-ttu-id="a4f6c-251">이 단계를 반복하여 애플리케이션이 대상으로 하는 추가 대상 플랫폼을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-251">Repeat these steps to define any additional target platforms that your application targets.</span></span>

<span data-ttu-id="a4f6c-252">프로필을 구성했으므로 이제 앱을 게시할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-252">You've configured your profiles and are now ready to publish your app.</span></span> <span data-ttu-id="a4f6c-253">가상 하드 디스크 파일에 대한 중요 정보를 제공하려면</span><span class="sxs-lookup"><span data-stu-id="a4f6c-253">To do this:</span></span>

   1. <span data-ttu-id="a4f6c-254">**게시** 창이 현재 열려 있지 않은 경우 **솔루션 탐색기**에서 프로젝트(솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-254">If the **Publish** window isn't currently open, right-click on the project (not the solution) in **Solution Explorer** and select **Publish**.</span></span>

   2. <span data-ttu-id="a4f6c-255">게시할 프로필을 선택한 다음, **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-255">Select the profile that you'd like to publish, then select **Publish**.</span></span> <span data-ttu-id="a4f6c-256">게시할 각 프로필에 대해 이 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-256">Do this for each profile to be published.</span></span>

   <span data-ttu-id="a4f6c-257">각 대상 위치(예제의 경우 bin\release\netcoreapp2.1\publish\\*profile-name*에는 앱을 시작하는 데 필요한 전체 파일 집합(앱 파일 및 모든 .NET Core 파일)이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-257">Each target location (in the case of our example, bin\release\netcoreapp2.1\publish\\*profile-name* contains the complete set of files (both your app files and all .NET Core files) needed to launch your app.</span></span>

<span data-ttu-id="a4f6c-258">게시 프로세스에서는 애플리케이션의 파일과 함께 앱에 대한 디버깅 정보를 포함하는 프로그램 데이터베이스(.pdb) 파일을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-258">Along with your application's files, the publishing process emits a program database (.pdb) file that contains debugging information about your app.</span></span> <span data-ttu-id="a4f6c-259">이 파일은 주로 예외 디버그에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-259">The file is useful primarily for debugging exceptions.</span></span> <span data-ttu-id="a4f6c-260">애플리케이션 파일과 함께 패키지하지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-260">You can choose not to package it with your application's files.</span></span> <span data-ttu-id="a4f6c-261">하지만 앱의 릴리스 빌드를 디버그하려는 경우 파일을 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-261">You should, however, save it in the event that you want to debug the Release build of your app.</span></span>

<span data-ttu-id="a4f6c-262">게시된 파일을 원하는 방식으로 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-262">Deploy the published files in any way you like.</span></span> <span data-ttu-id="a4f6c-263">예를 들어 Zip 파일로 패키지하거나, 간단한 `copy` 명령을 사용하거나, 선택한 설치 패키지와 함께 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-263">For example, you can package them in a Zip file, use a simple `copy` command, or deploy them with any installation package of your choice.</span></span>

<span data-ttu-id="a4f6c-264">다음은 이 프로젝트에 대한 전체 *csproj* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-264">The following is the complete *csproj* file for this project.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="a4f6c-265">또한 Visual Studio는 대상으로 하는 각 플랫폼에 대해 별도의 게시 프로필(\*.pubxml)을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-265">In addition, Visual Studio creates a separate publishing profile (\*.pubxml) for each platform that you target.</span></span> <span data-ttu-id="a4f6c-266">예를 들어, linux 프로필(linux.pubxml)의 파일은 다음과 같이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-266">For example, the file for our linux profile (linux.pubxml) appears as follows:</span></span>

```xml
<?xml version="1.0" encoding="utf-8"?>
<!--
https://go.microsoft.com/fwlink/?LinkID=208121.
-->
<Project ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <PublishProtocol>FileSystem</PublishProtocol>
    <Configuration>Release</Configuration>
    <Platform>Any CPU</Platform>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <PublishDir>bin\Release\netcoreapp2.1\publish\linux</PublishDir>
    <RuntimeIdentifier>win-x86</RuntimeIdentifier>
    <SelfContained>true</SelfContained>
    <_IsPortable>false</_IsPortable>
  </PropertyGroup>
</Project>
```

---

## <a name="self-contained-deployment-with-third-party-dependencies"></a><span data-ttu-id="a4f6c-267">타사 종속성이 있는 자체 포함 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-267">Self-contained deployment with third-party dependencies</span></span>

<span data-ttu-id="a4f6c-268">하나 이상의 타사 종속성이 있는 자체 포함 배포에는 종속성 추가가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-268">Deploying a self-contained deployment with one or more third-party dependencies involves adding the dependencies.</span></span> <span data-ttu-id="a4f6c-269">다음 추가 단계를 수행해야 앱을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-269">The following additional steps are required before you can build your app:</span></span>

1. <span data-ttu-id="a4f6c-270">**NuGet 패키지 관리자**를 사용하여 NuGet 패키지에 대한 참조를 프로젝트에 추가하고, 시스템에서 패키지를 사용할 수 없는 경우 패키지를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-270">Use the **NuGet Package Manager** to add a reference to a NuGet package to your project; and if the package is not already available on your system, install it.</span></span> <span data-ttu-id="a4f6c-271">패키지 관리자를 열려면 **도구** > **NuGet 패키지 관리자** > **솔루션용 NuGet 패키지 관리**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-271">To open the package manager, select **Tools** > **NuGet Package Manager** > **Manage NuGet Packages for Solution**.</span></span>

1. <span data-ttu-id="a4f6c-272">타사 종속성(예: `Newtonsoft.Json`)이 시스템에 설치되어 있는지 확인하고 그렇지 않은 경우 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-272">Confirm that your third-party dependencies (for example, `Newtonsoft.Json`) are installed on your system and, if they aren't, install them.</span></span> <span data-ttu-id="a4f6c-273">**설치됨** 탭에 시스템에 설치된 NuGet 패키지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-273">The **Installed** tab lists NuGet packages installed on your system.</span></span> <span data-ttu-id="a4f6c-274">`Newtonsoft.Json`이 탭에 표시되지 않는 경우 **찾아보기** 탭을 선택하고 검색 상자에 "Newtonsoft.Json"을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-274">If `Newtonsoft.Json` is not listed there, select the **Browse** tab and enter "Newtonsoft.Json" in the search box.</span></span> <span data-ttu-id="a4f6c-275">`Newtonsoft.Json`을 선택하고 오른쪽 창에서 해당 프로젝트를 선택한 후 **설치**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-275">Select `Newtonsoft.Json` and, in the right pane, select your project before selecting **Install**.</span></span>

1. <span data-ttu-id="a4f6c-276">`Newtonsoft.Json`이 시스템에 이미 설치되어 있는 경우 **솔루션용 패키지 관리** 탭의 오른쪽 창에서 해당 프로젝트를 선택하여 프로젝트에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-276">If `Newtonsoft.Json` is already installed on your system, add it to your project by selecting your project in the right pane of the **Manage Packages for Solution** tab.</span></span>

<span data-ttu-id="a4f6c-277">다음은 이 프로젝트에 대한 전체 *csproj* 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-277">The following is the complete *csproj* file for this project:</span></span>

# <a name="visual-studio-156-and-earlier"></a>[<span data-ttu-id="a4f6c-278">Visual Studio 15.6 및 이전 버전</span><span class="sxs-lookup"><span data-stu-id="a4f6c-278">Visual Studio 15.6 and earlier</span></span>](#tab/vs156)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
    <RuntimeIdentifiers>win10-x64;osx.10.11-x64</RuntimeIdentifiers>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

# <a name="visual-studio-157-and-later"></a>[<span data-ttu-id="a4f6c-279">Visual Studio 15.7 이상</span><span class="sxs-lookup"><span data-stu-id="a4f6c-279">Visual Studio 15.7 and later</span></span>](#tab/vs157)

```xml
<Project Sdk="Microsoft.NET.Sdk">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>
  </PropertyGroup>
  <ItemGroup>
    <PackageReference Include="Newtonsoft.Json" Version="10.0.2" />
  </ItemGroup>
</Project>
```

---

<span data-ttu-id="a4f6c-280">애플리케이션을 배포하면 앱에서 사용된 타사 종속성도 애플리케이션 파일에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-280">When you deploy your application, any third-party dependencies used in your app are also contained with your application files.</span></span> <span data-ttu-id="a4f6c-281">타사 라이브러리는 앱이 실행되는 시스템에 없어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-281">Third-party libraries aren't required on the system on which the app is running.</span></span>

<span data-ttu-id="a4f6c-282">타사 라이브러리가 있는 자체 포함 배포는 해당 라이브러리에서 지원하는 플랫폼에만 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-282">You can only deploy a self-contained deployment with a third-party library to platforms supported by that library.</span></span> <span data-ttu-id="a4f6c-283">이 배포는 기본 종속성과 함께 타사 종속성이 있는 프레임워크 종속 배포와 유사하며, 이전에 설치되지 않은 경우 대상 플랫폼에는 기본 종속성이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a4f6c-283">This is similar to having third-party dependencies with native dependencies in your framework-dependent deployment, where the native dependencies won't exist on the target platform unless they were previously installed there.</span></span>

## <a name="see-also"></a><span data-ttu-id="a4f6c-284">참조</span><span class="sxs-lookup"><span data-stu-id="a4f6c-284">See also</span></span>

- [<span data-ttu-id="a4f6c-285">.NET Core 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="a4f6c-285">.NET Core Application Deployment</span></span>](index.md)
- [<span data-ttu-id="a4f6c-286">.NET Core RID(런타임 식별자) 카탈로그</span><span class="sxs-lookup"><span data-stu-id="a4f6c-286">.NET Core Runtime Identifier (RID) catalog</span></span>](../rid-catalog.md)
