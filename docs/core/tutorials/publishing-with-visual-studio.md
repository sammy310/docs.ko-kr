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
ms.openlocfilehash: 745fb2af332afa278c78ec9baeea7230fe725c02
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241498"
---
# <a name="tutorial-publish-a-net-core-console-application-with-visual-studio"></a><span data-ttu-id="02395-103">자습서: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="02395-103">Tutorial: Publish a .NET Core console application with Visual Studio</span></span>

<span data-ttu-id="02395-104">이 자습서에서는 다른 사용자가 실행할 수 있도록 콘솔 앱을 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="02395-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="02395-105">게시하면 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="02395-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="02395-106">파일을 배포하려면 대상 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="02395-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="02395-107">Prerequisites</span></span>

- <span data-ttu-id="02395-108">이 자습서는 [Visual Studio 2019에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)에서 만든 콘솔 앱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02395-108">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="02395-109">앱 게시</span><span class="sxs-lookup"><span data-stu-id="02395-109">Publish the app</span></span>

1. <span data-ttu-id="02395-110">Visual Studio에서 애플리케이션의 릴리스 버전을 빌드하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-110">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="02395-111">필요한 경우 도구 모음의 빌드 구성 설정을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-111">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![릴리스 빌드가 선택된 Visual Studio 도구 모음](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="02395-113">**HelloWorld** 프로젝트(HelloWorld 솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 메뉴에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-113">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Visual Studio 게시 상황에 맞는 메뉴](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="02395-115">**게시** 페이지의 **대상** 탭에서 **폴더**를 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-115">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Visual Studio에서 게시 대상 선택](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="02395-117">**게시** 페이지의 **위치** 탭에서 **마침**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-117">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Visual Studio 게시 페이지 위치 탭](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="02395-119">**게시** 창의 **게시** 탭에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-119">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Visual Studio 게시 창](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="02395-121">파일 검사</span><span class="sxs-lookup"><span data-stu-id="02395-121">Inspect the files</span></span>

<span data-ttu-id="02395-122">게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 .NET Core 런타임이 설치된 컴퓨터에서 게시된 애플리케이션이 실행되는 배포 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="02395-122">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="02395-123">사용자는 실행 파일을 두 번 클릭하거나 명령 프롬프트에서 `dotnet HelloWorld.dll` 명령을 실행하여 게시된 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02395-123">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="02395-124">다음 단계에서는 게시 프로세스를 통해 생성된 파일을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="02395-124">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="02395-125">**솔루션 탐색기**에서 **모든 파일 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-125">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="02395-126">프로젝트 폴더에서 *bin/Release/netcoreapp3.1/publish*를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-126">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="게시된 파일을 보여 주는 솔루션 탐색기":::

   <span data-ttu-id="02395-128">그림에 표시된 것과 같이 게시된 출력에는 다음 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02395-128">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="02395-129">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="02395-129">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="02395-130">애플리케이션의 런타임 종속성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="02395-130">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="02395-131">애플리케이션을 실행하는 데 필요한 .NET Core 구성 요소 및 라이브러리(애플리케이션을 포함하는 동적 연결 라이브러리 포함)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-131">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="02395-132">자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02395-132">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="02395-133">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="02395-133">*HelloWorld.dll*</span></span>

      <span data-ttu-id="02395-134">애플리케이션의 [프레임워크 종속 배포](../deploying/deploy-with-cli.md#framework-dependent-deployment)입니다.</span><span class="sxs-lookup"><span data-stu-id="02395-134">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="02395-135">이 동적 연결 라이브러리를 실행하려면 명령 프롬프트에 `dotnet HelloWorld.dll`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-135">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="02395-136">앱을 실행하는 이 메서드는 .NET Core 런타임이 설치된 모든 플랫폼에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-136">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="02395-137">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="02395-137">*HelloWorld.exe*</span></span>

      <span data-ttu-id="02395-138">애플리케이션의 [프레임워크 종속 실행 파일](../deploying/deploy-with-cli.md#framework-dependent-executable)입니다.</span><span class="sxs-lookup"><span data-stu-id="02395-138">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="02395-139">이를 실행하려면 명령 프롬프트에서 `HelloWorld.exe`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-139">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="02395-140">이 파일은 운영 체제마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="02395-140">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="02395-141">*HelloWorld.pdb*(배포에 대한 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="02395-141">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="02395-142">디버그 기호 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="02395-142">This is the debug symbols file.</span></span> <span data-ttu-id="02395-143">게시된 애플리케이션 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 애플리케이션과 함께 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02395-143">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="02395-144">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="02395-144">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="02395-145">애플리케이션의 런타임 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="02395-145">This is the application's run-time configuration file.</span></span> <span data-ttu-id="02395-146">애플리케이션이 실행되도록 빌드된 .NET Core의 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-146">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="02395-147">구성 옵션을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02395-147">You can also add configuration options to it.</span></span> <span data-ttu-id="02395-148">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="02395-148">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="02395-149">게시된 앱 실행</span><span class="sxs-lookup"><span data-stu-id="02395-149">Run the published app</span></span>

1. <span data-ttu-id="02395-150">**솔루션 탐색기**에서 *publish* 폴더를 마우스 오른쪽 단추로 클릭하고 **전체 경로 복사**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-150">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="02395-151">명령 프롬프트를 열고 *publish* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-151">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="02395-152">`cd`를 입력한 다음 전체 경로를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="02395-152">Enter `cd` and then paste the full path.</span></span> <span data-ttu-id="02395-153">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="02395-153">For example:</span></span>

   ```
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="02395-154">실행 파일을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-154">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="02395-155">`HelloWorld.exe`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="02395-155">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="02395-156">프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-156">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="02395-157">`dotnet` 명령을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-157">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="02395-158">`dotnet HelloWorld.dll`을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="02395-158">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="02395-159">프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="02395-159">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="02395-160">추가 자료</span><span class="sxs-lookup"><span data-stu-id="02395-160">Additional resources</span></span>

- [<span data-ttu-id="02395-161">.NET Core 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="02395-161">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="02395-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="02395-162">Next steps</span></span>

<span data-ttu-id="02395-163">이 자습서에서는 콘솔 앱을 게시했습니다.</span><span class="sxs-lookup"><span data-stu-id="02395-163">In this tutorial, you published a console app.</span></span> <span data-ttu-id="02395-164">다음 자습서에서는 클래스 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02395-164">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="02395-165">Visual Studio에서 .NET Standard 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="02395-165">Create a .NET Standard library in Visual Studio</span></span>](library-with-visual-studio.md)
