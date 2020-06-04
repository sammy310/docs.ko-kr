---
title: Visual Studio를 사용하여 .NET Core Hello World 애플리케이션 게시
description: 게시하면 .NET Core 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e4ef8c12f3e52faa7cf09058a98abae65b0dcfce
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005111"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a><span data-ttu-id="36449-103">자습서: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="36449-103">Tutorial: Publish a .NET Core console application with Visual Studio</span></span>

<span data-ttu-id="36449-104">이 자습서에서는 다른 사용자가 실행할 수 있도록 콘솔 앱을 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="36449-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="36449-105">게시하면 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="36449-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="36449-106">파일을 배포하려면 대상 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="36449-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="36449-107">Prerequisites</span></span>

- <span data-ttu-id="36449-108">이 자습서는 [Visual Studio 2019에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)에서 만든 콘솔 앱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36449-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="36449-109">앱 게시</span><span class="sxs-lookup"><span data-stu-id="36449-109">Publish the app</span></span>

1. <span data-ttu-id="36449-110">Visual Studio에서 애플리케이션의 릴리스 버전을 빌드하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="36449-111">필요한 경우 도구 모음의 빌드 구성 설정을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![릴리스 빌드가 선택된 Visual Studio 도구 모음](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="36449-113">**HelloWorld** 프로젝트(HelloWorld 솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 메뉴에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Visual Studio 게시 상황에 맞는 메뉴](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="36449-115">**게시** 페이지의 **대상** 탭에서 **폴더**를 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-115">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Visual Studio에서 게시 대상 선택](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="36449-117">**게시** 페이지의 **위치** 탭에서 **마침**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-117">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Visual Studio 게시 페이지 위치 탭](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="36449-119">**게시** 창의 **게시** 탭에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-119">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Visual Studio 게시 창](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="36449-121">파일 검사</span><span class="sxs-lookup"><span data-stu-id="36449-121">Inspect the files</span></span>

<span data-ttu-id="36449-122">게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 .NET Core 런타임이 설치된 컴퓨터에서 게시된 애플리케이션이 실행되는 배포 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="36449-122">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="36449-123">사용자는 실행 파일을 두 번 클릭하거나 명령 프롬프트에서 `dotnet HelloWorld.dll` 명령을 실행하여 게시된 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36449-123">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="36449-124">다음 단계에서는 게시 프로세스를 통해 생성된 파일을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="36449-124">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="36449-125">**솔루션 탐색기**에서 **모든 파일 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-125">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="36449-126">프로젝트 폴더에서 *bin/Release/netcoreapp3.1/publish*를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-126">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="게시된 파일을 보여 주는 솔루션 탐색기":::

   <span data-ttu-id="36449-128">그림에 표시된 것과 같이 게시된 출력에는 다음 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36449-128">As the image shows, the published output includes the following files:</span></span>

      * <span data-ttu-id="36449-129">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="36449-129">*HelloWorld.deps.json*</span></span>

         <span data-ttu-id="36449-130">애플리케이션의 런타임 종속성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="36449-130">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="36449-131">애플리케이션을 실행하는 데 필요한 .NET Core 구성 요소 및 라이브러리(애플리케이션을 포함하는 동적 연결 라이브러리 포함)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-131">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="36449-132">자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36449-132">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

      * <span data-ttu-id="36449-133">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="36449-133">*HelloWorld.dll*</span></span>

         <span data-ttu-id="36449-134">애플리케이션의 [프레임워크 종속 배포](../deploying/deploy-with-cli.md#framework-dependent-deployment)입니다.</span><span class="sxs-lookup"><span data-stu-id="36449-134">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="36449-135">이 동적 연결 라이브러리를 실행하려면 명령 프롬프트에 `dotnet HelloWorld.dll`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-135">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span>

      * <span data-ttu-id="36449-136">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="36449-136">*HelloWorld.exe*</span></span>

         <span data-ttu-id="36449-137">애플리케이션의 [프레임워크 종속 실행 파일](../deploying/deploy-with-cli.md#framework-dependent-executable)입니다.</span><span class="sxs-lookup"><span data-stu-id="36449-137">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="36449-138">이를 실행하려면 명령 프롬프트에서 `HelloWorld.exe`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-138">To run it, enter `HelloWorld.exe` at a command prompt.</span></span>

      * <span data-ttu-id="36449-139">*HelloWorld.pdb*(배포에 대한 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="36449-139">*HelloWorld.pdb* (optional for deployment)</span></span>

         <span data-ttu-id="36449-140">디버그 기호 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="36449-140">This is the debug symbols file.</span></span> <span data-ttu-id="36449-141">게시된 애플리케이션 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 애플리케이션과 함께 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36449-141">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

      * <span data-ttu-id="36449-142">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="36449-142">*HelloWorld.runtimeconfig.json*</span></span>

         <span data-ttu-id="36449-143">애플리케이션의 런타임 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="36449-143">This is the application's run-time configuration file.</span></span> <span data-ttu-id="36449-144">애플리케이션이 실행되도록 빌드된 .NET Core의 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-144">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="36449-145">구성 옵션을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36449-145">You can also add configuration options to it.</span></span> <span data-ttu-id="36449-146">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="36449-146">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="36449-147">게시된 앱 실행</span><span class="sxs-lookup"><span data-stu-id="36449-147">Run the published app</span></span>

1. <span data-ttu-id="36449-148">**솔루션 탐색기**에서 *publish* 폴더를 마우스 오른쪽 단추로 클릭하고 **전체 경로 복사**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-148">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="36449-149">명령 프롬프트를 열고 *publish* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-149">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="36449-150">`cd`를 입력한 다음 전체 경로를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="36449-150">Enter `cd` and then paste the full path.</span></span> <span data-ttu-id="36449-151">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="36449-151">For example:</span></span>

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="36449-152">실행 파일을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-152">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="36449-153">`HelloWorld.exe`를 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="36449-153">Enter `HelloWorld.exe` and press Enter.</span></span>

   1. <span data-ttu-id="36449-154">프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-154">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="36449-155">`dotnet` 명령을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-155">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="36449-156">`dotnet HelloWorld.dll`을 입력하고 Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="36449-156">Enter `dotnet HelloWorld.dll` and press Enter.</span></span>

   1. <span data-ttu-id="36449-157">프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="36449-157">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="36449-158">추가 자료</span><span class="sxs-lookup"><span data-stu-id="36449-158">Additional resources</span></span>

- [<span data-ttu-id="36449-159">.NET Core 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="36449-159">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="36449-160">다음 단계</span><span class="sxs-lookup"><span data-stu-id="36449-160">Next steps</span></span>

<span data-ttu-id="36449-161">이 자습서에서는 콘솔 앱을 게시했습니다.</span><span class="sxs-lookup"><span data-stu-id="36449-161">In this tutorial, you published a console app.</span></span> <span data-ttu-id="36449-162">다음 자습서에서는 클래스 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="36449-162">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="36449-163">Visual Studio에서 .NET Standard 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="36449-163">Create a .NET Standard library in Visual Studio</span></span>](library-with-visual-studio.md)
