---
title: Visual Studio를 사용하여 .NET Core Hello World 애플리케이션 게시
description: 게시하면 .NET Core 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.
author: BillWagner
ms.author: wiwagn
ms.date: 12/10/2019
ms.custom: vs-dotnet
ms.openlocfilehash: bdd6e28713bdece2bd144e6763bd84d719e91449
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156636"
---
# <a name="publish-your-net-core-hello-world-application-with-visual-studio"></a><span data-ttu-id="ff589-103">Visual Studio를 사용하여 .NET Core Hello World 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="ff589-103">Publish your .NET Core Hello World application with Visual Studio</span></span>

<span data-ttu-id="ff589-104">[Visual Studio에서 .NET Core를 사용하여 Hello World 애플리케이션 만들기](with-visual-studio.md)에서 Hello World 콘솔 애플리케이션을 빌드했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-104">In [Create a Hello World application with .NET Core in Visual Studio](with-visual-studio.md), you built a Hello World console application.</span></span> <span data-ttu-id="ff589-105">[Visual Studio을 사용하여 Hello World 애플리케이션 디버그](debugging-with-visual-studio.md)에서 Visual Studio 디버거를 사용하여 테스트했습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-105">In [Debug your Hello World application with Visual Studio](debugging-with-visual-studio.md), you tested it using the Visual Studio debugger.</span></span> <span data-ttu-id="ff589-106">예상대로 작동하는지 확인했으므로 다른 사용자가 실행할 수 있도록 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-106">Now that you're sure that it works as expected, you can publish it so that other users can run it.</span></span> <span data-ttu-id="ff589-107">게시하면 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-107">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="ff589-108">파일을 배포하려면 대상 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-108">To deploy the files, copy them to the target machine.</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="ff589-109">앱 게시</span><span class="sxs-lookup"><span data-stu-id="ff589-109">Publish the app</span></span>

1. <span data-ttu-id="ff589-110">Visual Studio에서 애플리케이션의 릴리스 버전을 빌드하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="ff589-111">필요한 경우 도구 모음의 빌드 구성 설정을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![릴리스 빌드가 선택된 Visual Studio 도구 모음](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="ff589-113">**HelloWorld** 프로젝트(HelloWorld 솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 메뉴에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span> <span data-ttu-id="ff589-114">(주 **빌드** 메뉴에서 **HelloWorld 게시**를 선택할 수도 있습니다.)</span><span class="sxs-lookup"><span data-stu-id="ff589-114">(You can also select **Publish HelloWorld** from the main **Build** menu.)</span></span>

   ![Visual Studio 게시 상황에 맞는 메뉴](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="ff589-116">**게시 대상 선택** 페이지에서 **폴더**를 선택한 다음 **프로필 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-116">On the **Pick a publish target** page, select **Folder**, and then select **Create Profile**.</span></span>

   ![Visual Studio에서 게시 대상 선택](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="ff589-118">**게시** 페이지에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-118">On the **Publish** page, select **Publish**.</span></span>

   ![Visual Studio 게시 창](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="ff589-120">파일 검사</span><span class="sxs-lookup"><span data-stu-id="ff589-120">Inspect the files</span></span>

<span data-ttu-id="ff589-121">게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 시스템에 .NET Core가 설치되어 있으면 게시된 애플리케이션이 .NET Core에서 지원하는 모든 플랫폼에서 실행되는 배포 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-121">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on any platform supported by .NET Core with .NET Core installed on the system.</span></span> <span data-ttu-id="ff589-122">사용자는 실행 파일을 두 번 클릭하거나 명령 프롬프트에서 `dotnet HelloWorld.dll` 명령을 실행하여 게시된 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-122">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="ff589-123">다음 단계에서는 게시 프로세스를 통해 생성된 파일을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-123">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="ff589-124">명령 프롬프트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-124">Open a command prompt.</span></span>

   <span data-ttu-id="ff589-125">명령 프롬프트를 여는 방법 중 하나는 Windows 작업 표시줄의 검색 상자에서 **명령 프롬프트**(또는 **cmd**)를 입력하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-125">One way to open a command prompt is to enter **Command Prompt** (or **cmd** for short) in the search box on the Windows taskbar.</span></span> <span data-ttu-id="ff589-126">**명령 프롬프트** 데스크톱 앱을 선택하거나 검색 결과에서 이미 선택되어 있는 경우 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-126">Select the **Command Prompt** desktop app, or press **Enter** if it's already selected in the search results.</span></span>

1. <span data-ttu-id="ff589-127">애플리케이션 프로젝트 디렉터리의 *bin\Release\netcoreapp3.1\publish* 하위 디렉터리에 게시된 애플리케이션으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-127">Navigate to the published application in the *bin\Release\netcoreapp3.1\publish* subdirectory of the application's project directory.</span></span>

   ![게시된 파일을 보여 주는 콘솔 창](media/publishing-with-visual-studio/published-files-output.png)

   <span data-ttu-id="ff589-129">그림에 표시된 것과 같이 게시된 출력에는 다음 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-129">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="ff589-130">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="ff589-130">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="ff589-131">애플리케이션의 런타임 종속성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-131">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="ff589-132">애플리케이션을 실행하는 데 필요한 .NET Core 구성 요소 및 라이브러리(애플리케이션을 포함하는 동적 연결 라이브러리 포함)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-132">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="ff589-133">자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff589-133">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="ff589-134">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="ff589-134">*HelloWorld.dll*</span></span>

         <span data-ttu-id="ff589-135">애플리케이션의 [프레임워크 종속 배포](../deploying/deploy-with-cli.md#framework-dependent-deployment)입니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-135">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="ff589-136">이 동적 연결 라이브러리를 실행하려면 명령 프롬프트에 `dotnet HelloWorld.dll`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-136">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="ff589-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="ff589-137">*HelloWorld.exe*</span></span>

         <span data-ttu-id="ff589-138">애플리케이션의 [프레임워크 종속 실행 파일](../deploying/deploy-with-cli.md#framework-dependent-executable)입니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="ff589-139">이를 실행하려면 명령 프롬프트에서 `HelloWorld.exe`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="ff589-140">*HelloWorld.pdb*(배포에 대한 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="ff589-140">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="ff589-141">디버그 기호 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-141">This is the debug symbols file.</span></span> <span data-ttu-id="ff589-142">게시된 애플리케이션 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 애플리케이션과 함께 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-142">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="ff589-143">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="ff589-143">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="ff589-144">애플리케이션의 런타임 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-144">This is the application's run-time configuration file.</span></span> <span data-ttu-id="ff589-145">애플리케이션이 실행되도록 빌드된 .NET Core의 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-145">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="ff589-146">구성 옵션을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff589-146">You can also add configuration options to it.</span></span> <span data-ttu-id="ff589-147">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff589-147">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ff589-148">추가 자료</span><span class="sxs-lookup"><span data-stu-id="ff589-148">Additional resources</span></span>

- [<span data-ttu-id="ff589-149">.NET Core 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="ff589-149">.NET Core application deployment</span></span>](../deploying/index.md)
