---
title: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시
description: 게시하면 .NET Core 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: e0033d52ab54259ce5e4ccf2a25bf4e3d4f244de
ms.sourcegitcommit: b9122d1af21898eaba81e990c70fef46fef74a8d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/26/2020
ms.locfileid: "88867557"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="98c83-103">자습서: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="98c83-103">Tutorial: Publish a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="98c83-104">이 자습서에서는 다른 사용자가 실행할 수 있도록 콘솔 앱을 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="98c83-105">게시하면 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="98c83-106">파일을 배포하려면 대상 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="98c83-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="98c83-107">Prerequisites</span></span>

- <span data-ttu-id="98c83-108">이 자습서는 [Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)에서 만든 콘솔 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-108">This tutorial works with the console app that you create in [Create a .NET Core console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="98c83-109">앱 게시</span><span class="sxs-lookup"><span data-stu-id="98c83-109">Publish the app</span></span>

1. <span data-ttu-id="98c83-110">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-110">Start Visual Studio.</span></span>

1. <span data-ttu-id="98c83-111">[Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)에서 만든 *HelloWorld* 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-111">Open the *HelloWorld* project that you created in [Create a .NET Core console application using Visual Studio](with-visual-studio.md).</span></span>

1. <span data-ttu-id="98c83-112">Visual Studio에서 릴리스 빌드 구성을 사용 중인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-112">Make sure that Visual Studio is using the Release build configuration.</span></span> <span data-ttu-id="98c83-113">필요한 경우 도구 모음의 빌드 구성 설정을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   ![릴리스 빌드가 선택된 Visual Studio 도구 모음](media/publishing-with-visual-studio/visual-studio-toolbar-release.png)

1. <span data-ttu-id="98c83-115">**HelloWorld** 프로젝트(HelloWorld 솔루션 아님)를 마우스 오른쪽 단추로 클릭하고 메뉴에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-115">Right-click on the **HelloWorld** project (not the HelloWorld solution) and select **Publish** from the menu.</span></span>

   ![Visual Studio 게시 상황에 맞는 메뉴](media/publishing-with-visual-studio/publish-context-menu.png)

1. <span data-ttu-id="98c83-117">**게시** 페이지의 **대상** 탭에서 **폴더**를 선택한 후 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-117">On the **Target** tab of the **Publish** page, select **Folder**, and then select **Next**.</span></span>

   ![Visual Studio에서 게시 대상 선택](media/publishing-with-visual-studio/pick-publish-target.png)

1. <span data-ttu-id="98c83-119">**게시** 페이지의 **위치** 탭에서 **마침**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-119">On the **Location** tab of the **Publish** page, select **Finish**.</span></span>

   ![Visual Studio 게시 페이지 위치 탭](media/publishing-with-visual-studio/publish-page-loc-tab.png)

1. <span data-ttu-id="98c83-121">**게시** 창의 **게시** 탭에서 **게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-121">On the **Publish** tab of the **Publish** window, select **Publish**.</span></span>

   ![Visual Studio 게시 창](media/publishing-with-visual-studio/publish-page.png)

## <a name="inspect-the-files"></a><span data-ttu-id="98c83-123">파일 검사</span><span class="sxs-lookup"><span data-stu-id="98c83-123">Inspect the files</span></span>

<span data-ttu-id="98c83-124">기본적으로 게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 .NET Core 런타임이 설치된 머신에서 게시된 애플리케이션이 실행되는 배포 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-124">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="98c83-125">사용자는 실행 파일을 두 번 클릭하거나 명령 프롬프트에서 `dotnet HelloWorld.dll` 명령을 실행하여 게시된 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-125">Users can run the published app by double-clicking the executable or issuing the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="98c83-126">다음 단계에서는 게시 프로세스를 통해 생성된 파일을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-126">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="98c83-127">**솔루션 탐색기**에서 **모든 파일 표시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-127">In **Solution Explorer**, select **Show all files**.</span></span>

1. <span data-ttu-id="98c83-128">프로젝트 폴더에서 *bin/Release/netcoreapp3.1/publish*를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-128">In the project folder, expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio/published-files-output.png" alt-text="게시된 파일을 보여 주는 솔루션 탐색기":::

   <span data-ttu-id="98c83-130">그림에 표시된 것과 같이 게시된 출력에는 다음 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-130">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="98c83-131">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="98c83-131">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="98c83-132">애플리케이션의 런타임 종속성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-132">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="98c83-133">애플리케이션을 실행하는 데 필요한 .NET Core 구성 요소 및 라이브러리(애플리케이션을 포함하는 동적 연결 라이브러리 포함)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-133">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="98c83-134">자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98c83-134">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="98c83-135">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="98c83-135">*HelloWorld.dll*</span></span>

      <span data-ttu-id="98c83-136">애플리케이션의 [프레임워크 종속 배포](../deploying/deploy-with-cli.md#framework-dependent-deployment)입니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-136">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="98c83-137">이 동적 연결 라이브러리를 실행하려면 명령 프롬프트에 `dotnet HelloWorld.dll`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-137">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="98c83-138">앱을 실행하는 이 메서드는 .NET Core 런타임이 설치된 모든 플랫폼에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-138">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="98c83-139">*HelloWorld.exe*</span><span class="sxs-lookup"><span data-stu-id="98c83-139">*HelloWorld.exe*</span></span>

      <span data-ttu-id="98c83-140">애플리케이션의 [프레임워크 종속 실행 파일](../deploying/deploy-with-cli.md#framework-dependent-executable)입니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-140">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="98c83-141">이를 실행하려면 명령 프롬프트에서 `HelloWorld.exe`를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-141">To run it, enter `HelloWorld.exe` at a command prompt.</span></span> <span data-ttu-id="98c83-142">이 파일은 운영 체제마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-142">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="98c83-143">*HelloWorld.pdb*(배포에 대한 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="98c83-143">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="98c83-144">디버그 기호 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-144">This is the debug symbols file.</span></span> <span data-ttu-id="98c83-145">게시된 애플리케이션 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 애플리케이션과 함께 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-145">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="98c83-146">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="98c83-146">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="98c83-147">애플리케이션의 런타임 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-147">This is the application's run-time configuration file.</span></span> <span data-ttu-id="98c83-148">애플리케이션이 실행되도록 빌드된 .NET Core의 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-148">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="98c83-149">구성 옵션을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-149">You can also add configuration options to it.</span></span> <span data-ttu-id="98c83-150">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98c83-150">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="98c83-151">게시된 앱 실행</span><span class="sxs-lookup"><span data-stu-id="98c83-151">Run the published app</span></span>

1. <span data-ttu-id="98c83-152">**솔루션 탐색기**에서 *publish* 폴더를 마우스 오른쪽 단추로 클릭하고 **전체 경로 복사**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-152">In **Solution Explorer**, right-click the *publish* folder, and select **Copy Full Path**.</span></span>

1. <span data-ttu-id="98c83-153">명령 프롬프트를 열고 *publish* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-153">Open a command prompt and navigate to the *publish* folder.</span></span> <span data-ttu-id="98c83-154">이를 위해 `cd`를 입력한 다음 전체 경로를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-154">To do that, enter `cd` and then paste the full path.</span></span> <span data-ttu-id="98c83-155">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="98c83-155">For example:</span></span>

   ```console
   cd C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

1. <span data-ttu-id="98c83-156">실행 파일을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-156">Run the app by using the executable:</span></span>

   1. <span data-ttu-id="98c83-157">`HelloWorld.exe`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-157">Enter `HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="98c83-158">프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-158">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="98c83-159">`dotnet` 명령을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-159">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="98c83-160">`dotnet HelloWorld.dll`을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-160">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="98c83-161">프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-161">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="98c83-162">추가 자료</span><span class="sxs-lookup"><span data-stu-id="98c83-162">Additional resources</span></span>

- [<span data-ttu-id="98c83-163">.NET Core 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="98c83-163">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="98c83-164">다음 단계</span><span class="sxs-lookup"><span data-stu-id="98c83-164">Next steps</span></span>

<span data-ttu-id="98c83-165">이 자습서에서는 콘솔 앱을 게시했습니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-165">In this tutorial, you published a console app.</span></span> <span data-ttu-id="98c83-166">다음 자습서에서는 클래스 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="98c83-166">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="98c83-167">Visual Studio를 사용하여 .NET Standard 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="98c83-167">Create a .NET Standard library using Visual Studio</span></span>](library-with-visual-studio.md)
