---
title: Mac용 Visual Studio를 사용하여 .NET 콘솔 애플리케이션 게시
description: Mac용 Visual Studio를 사용하여 .NET 애플리케이션 실행에 필요한 파일 집합을 만드는 방법을 알아봅니다.
ms.date: 11/30/2020
ms.openlocfilehash: 88f143011b19ca8eda6610803c894e619d06a635
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599190"
---
# <a name="tutorial-publish-a-net-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="181ad-103">자습서: Mac용 Visual Studio를 사용하여 .NET 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="181ad-103">Tutorial: Publish a .NET console application using Visual Studio for Mac</span></span>

<span data-ttu-id="181ad-104">이 자습서에서는 다른 사용자가 실행할 수 있도록 콘솔 앱을 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="181ad-105">게시하면 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-105">Publishing creates the set of files that are needed to run your application.</span></span> <span data-ttu-id="181ad-106">파일을 배포하려면 대상 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-106">To deploy the files, copy them to the target machine.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="181ad-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="181ad-107">Prerequisites</span></span>

- <span data-ttu-id="181ad-108">이 자습서는 [Mac용 Visual Studio를 사용하여 .NET 콘솔 애플리케이션 만들기](with-visual-studio-mac.md)에서 만든 콘솔 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-108">This tutorial works with the console app that you create in [Create a .NET console application using Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="181ad-109">앱 게시</span><span class="sxs-lookup"><span data-stu-id="181ad-109">Publish the app</span></span>

1. <span data-ttu-id="181ad-110">Mac용 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-110">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="181ad-111">[Mac용 Visual Studio를 사용하여 .NET 콘솔 애플리케이션 만들기](with-visual-studio-mac.md)에서 만든 HelloWorld 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-111">Open the HelloWorld project that you created in [Create a .NET console application using Visual Studio for Mac](with-visual-studio-mac.md).</span></span>

1. <span data-ttu-id="181ad-112">Visual Studio에서 애플리케이션의 릴리스 버전을 빌드하고 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-112">Make sure that Visual Studio is building the Release version of your application.</span></span> <span data-ttu-id="181ad-113">필요한 경우 도구 모음의 빌드 구성 설정을 **디버그** 에서 **릴리스** 로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-113">If necessary, change the build configuration setting on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/toolbar-release.png" alt-text="릴리스 빌드가 선택된 Visual Studio 도구 모음":::

1. <span data-ttu-id="181ad-115">주 메뉴에서 **빌드** > **폴더에 게시...** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-115">From the main menu, choose **Build** > **Publish to Folder...**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-context-menu.png" alt-text="Visual Studio 게시 상황에 맞는 메뉴":::

1. <span data-ttu-id="181ad-117">**폴더에 게시** 대화 상자에서 **게시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-117">In the **Publish to Folder** dialog, select **Publish**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-to-folder-dialog.png" alt-text="Visual Studio 폴더에 게시 대화 상자":::

   <span data-ttu-id="181ad-119">게시 폴더가 열리고 만들어진 파일이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-119">The publish folder opens, showing the files that were created.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/publish-folder.png" alt-text="폴더 게시":::

1. <span data-ttu-id="181ad-121">기어 아이콘을 선택하고 상황에 맞는 메뉴에서 **경로 이름으로 "publish" 복사** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-121">Select the gear icon, and select **Copy "publish" as Pathname** from the context menu.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-mac/copy-path.png" alt-text="폴더를 게시할 경로 복사":::

## <a name="inspect-the-files"></a><span data-ttu-id="181ad-123">파일 검사</span><span class="sxs-lookup"><span data-stu-id="181ad-123">Inspect the files</span></span>

<span data-ttu-id="181ad-124">게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 .NET 런타임이 설치된 컴퓨터에서 게시된 애플리케이션이 실행되는 배포 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-124">The publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on a machine that has the .NET runtime installed.</span></span> <span data-ttu-id="181ad-125">사용자는 명령 프롬프트에서 `dotnet HelloWorld.dll` 명령을 실행하여 게시된 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-125">Users can run the published app by running the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="181ad-126">위의 그림에 표시된 것과 같이 게시된 출력에는 다음 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-126">As the preceding image shows, the published output includes the following files:</span></span>

* <span data-ttu-id="181ad-127">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="181ad-127">*HelloWorld.deps.json*</span></span>

  <span data-ttu-id="181ad-128">애플리케이션의 런타임 종속성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-128">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="181ad-129">앱을 실행하는 데 필요한 .NET 구성 요소 및 라이브러리(애플리케이션을 포함하는 동적 연결 라이브러리 포함)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-129">It defines the .NET components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="181ad-130">자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="181ad-130">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

* <span data-ttu-id="181ad-131">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="181ad-131">*HelloWorld.dll*</span></span>

   <span data-ttu-id="181ad-132">애플리케이션의 [프레임워크 종속 배포](../deploying/deploy-with-cli.md#framework-dependent-deployment)입니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-132">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="181ad-133">이 동적 연결 라이브러리를 실행하려면 명령 프롬프트에 `dotnet HelloWorld.dll`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-133">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="181ad-134">앱을 실행하는 이 메서드는 .NET 런타임이 설치된 모든 플랫폼에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-134">This method of running the app works on any platform that has the .NET runtime installed.</span></span>

* <span data-ttu-id="181ad-135">*HelloWorld.pdb*(배포에 대한 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="181ad-135">*HelloWorld.pdb* (optional for deployment)</span></span>

   <span data-ttu-id="181ad-136">디버그 기호 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-136">This is the debug symbols file.</span></span> <span data-ttu-id="181ad-137">게시된 애플리케이션 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 애플리케이션과 함께 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-137">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

* <span data-ttu-id="181ad-138">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="181ad-138">*HelloWorld.runtimeconfig.json*</span></span>

   <span data-ttu-id="181ad-139">애플리케이션의 런타임 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-139">This is the application's run-time configuration file.</span></span> <span data-ttu-id="181ad-140">애플리케이션이 실행되도록 빌드된 .NET의 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-140">It identifies the version of .NET that your application was built to run on.</span></span> <span data-ttu-id="181ad-141">구성 옵션을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-141">You can also add configuration options to it.</span></span> <span data-ttu-id="181ad-142">자세한 내용은 [.NET 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="181ad-142">For more information, see [.NET run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="181ad-143">게시된 앱 실행</span><span class="sxs-lookup"><span data-stu-id="181ad-143">Run the published app</span></span>

1. <span data-ttu-id="181ad-144">터미널을 열고 *publish* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-144">Open a terminal and navigate to the *publish* folder.</span></span> <span data-ttu-id="181ad-145">이를 위해 `cd`를 입력한 다음 앞서 복사한 경로를 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-145">To do that, enter `cd` and then paste the path that you copied earlier.</span></span> <span data-ttu-id="181ad-146">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="181ad-146">For example:</span></span>

   ```console
   cd ~/Projects/HelloWorld/HelloWorld/bin/Release/net5.0/publish/
   ```

1. <span data-ttu-id="181ad-147">`dotnet` 명령을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-147">Run the app by using the `dotnet` command:</span></span>

   1. <span data-ttu-id="181ad-148">`dotnet HelloWorld.dll`을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-148">Enter `dotnet HelloWorld.dll` and press <kbd>enter</kbd>.</span></span>

   1. <span data-ttu-id="181ad-149">프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-149">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="181ad-150">추가 자료</span><span class="sxs-lookup"><span data-stu-id="181ad-150">Additional resources</span></span>

- [<span data-ttu-id="181ad-151">.NET 응용 프로그램 배포</span><span class="sxs-lookup"><span data-stu-id="181ad-151">.NET application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="181ad-152">다음 단계</span><span class="sxs-lookup"><span data-stu-id="181ad-152">Next steps</span></span>

<span data-ttu-id="181ad-153">이 자습서에서는 콘솔 앱을 게시했습니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-153">In this tutorial, you published a console app.</span></span> <span data-ttu-id="181ad-154">다음 자습서에서는 클래스 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="181ad-154">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="181ad-155">Mac용 Visual Studio를 사용하여 .NET 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="181ad-155">Create a .NET library using Visual Studio for Mac</span></span>](library-with-visual-studio-mac.md)
