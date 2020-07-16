---
title: Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 게시
description: 게시하면 .NET Core 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.
ms.date: 07/04/2020
ms.openlocfilehash: 8fd9975e8a88704b9dea45b40127c8dc03f7d09f
ms.sourcegitcommit: 0edbeb66d71b8df10fcb374cfca4d731b58ccdb2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "86051885"
---
# <a name="tutorial-publish-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="6f5e8-103">자습서: Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="6f5e8-103">Tutorial: Publish a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="6f5e8-104">이 자습서에서는 다른 사용자가 실행할 수 있도록 콘솔 앱을 게시하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-104">This tutorial shows how to publish a console app so that other users can run it.</span></span> <span data-ttu-id="6f5e8-105">게시하면 애플리케이션을 실행하는 데 필요한 파일 집합이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-105">Publishing creates the set of files that are needed to run an application.</span></span> <span data-ttu-id="6f5e8-106">파일을 배포하려면 대상 컴퓨터로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-106">To deploy the files, copy them to the target machine.</span></span>

<span data-ttu-id="6f5e8-107">.NET Core CLI는 앱을 게시하는 데 사용됩니다. 원하는 경우 이 자습서에 따라 Visual Studio Code 외의 다른 코드 편집기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-107">The .NET Core CLI is used to publish the app, so you can follow this tutorial with a code editor other than Visual Studio Code if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6f5e8-108">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6f5e8-108">Prerequisites</span></span>

- <span data-ttu-id="6f5e8-109">이 자습서는 [Visual Studio Code에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio-code.md)에서 만든 콘솔 앱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-109">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="publish-the-app"></a><span data-ttu-id="6f5e8-110">앱 게시</span><span class="sxs-lookup"><span data-stu-id="6f5e8-110">Publish the app</span></span>

1. <span data-ttu-id="6f5e8-111">Visual Studio Code를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-111">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="6f5e8-112">[Visual Studio Code에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio-code.md)에서 만든 *HelloWorld* 프로젝트 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-112">Open the *HelloWorld* project folder that you created in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="6f5e8-113">주 메뉴에서 **보기** > **터미널**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-113">Choose **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="6f5e8-114">터미널이 *HelloWorld* 폴더에서 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-114">The terminal opens in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="6f5e8-115">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-115">Run the following command:</span></span>

   ```dotnetcli
   dotnet publish --configuration Release
   ```

   <span data-ttu-id="6f5e8-116">기본 빌드 구성은 ‘디버그’이므로 이 명령은 ‘릴리스’ 빌드 구성을 지정합니다. </span><span class="sxs-lookup"><span data-stu-id="6f5e8-116">The default build configuration is *Debug*, so this command specifies the *Release* build configuration.</span></span> <span data-ttu-id="6f5e8-117">릴리스 빌드 구성의 출력은 최소한의 기호 디버그 정보를 포함하고 있으며 완전히 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-117">The output from the Release build configuration has minimal symbolic debug information and is fully optimized.</span></span>

   <span data-ttu-id="6f5e8-118">명령 출력은 다음 예제와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-118">The command output is similar to the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0+5ff7b0c9e for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.

   Determining projects to restore...
   All projects are up-to-date for restore.
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\HelloWorld.dll
   HelloWorld -> C:\Projects\HelloWorld\bin\Release\netcoreapp3.1\publish\
   ```

## <a name="inspect-the-files"></a><span data-ttu-id="6f5e8-119">파일 검사</span><span class="sxs-lookup"><span data-stu-id="6f5e8-119">Inspect the files</span></span>

<span data-ttu-id="6f5e8-120">기본적으로 게시 프로세스는 프레임워크 종속 배포를 만듭니다. 이 배포는 .NET Core 런타임이 설치된 머신에서 게시된 애플리케이션이 실행되는 배포 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-120">By default, the publishing process creates a framework-dependent deployment, which is a type of deployment where the published application runs on a machine that has the .NET Core runtime installed.</span></span> <span data-ttu-id="6f5e8-121">게시된 앱을 실행하려면 실행 파일을 사용하거나 명령 프롬프트에서 `dotnet HelloWorld.dll` 명령을 실행하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-121">To run the published app you can use the executable file or run the `dotnet HelloWorld.dll` command from a command prompt.</span></span>

<span data-ttu-id="6f5e8-122">다음 단계에서는 게시 프로세스를 통해 생성된 파일을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-122">In the following steps, you'll look at the files created by the publish process.</span></span>

1. <span data-ttu-id="6f5e8-123">왼쪽 탐색 모음에서 **Explorer**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-123">Select the **Explorer** in the left navigation bar.</span></span>

1. <span data-ttu-id="6f5e8-124">*bin/Release/netcoreapp3.1/publish*를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-124">Expand *bin/Release/netcoreapp3.1/publish*.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/published-files-output.png" alt-text="게시된 파일을 보여 주는 Explorer":::

   <span data-ttu-id="6f5e8-126">그림에 표시된 것과 같이 게시된 출력에는 다음 파일이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-126">As the image shows, the published output includes the following files:</span></span>

   * <span data-ttu-id="6f5e8-127">*HelloWorld.deps.json*</span><span class="sxs-lookup"><span data-stu-id="6f5e8-127">*HelloWorld.deps.json*</span></span>

      <span data-ttu-id="6f5e8-128">애플리케이션의 런타임 종속성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-128">This is the application's runtime dependencies file.</span></span> <span data-ttu-id="6f5e8-129">애플리케이션을 실행하는 데 필요한 .NET Core 구성 요소 및 라이브러리(애플리케이션을 포함하는 동적 연결 라이브러리 포함)를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-129">It defines the .NET Core components and the libraries (including the dynamic link library that contains your application) needed to run the app.</span></span> <span data-ttu-id="6f5e8-130">자세한 내용은 [런타임 구성 파일](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-130">For more information, see [Runtime configuration files](https://github.com/dotnet/cli/blob/85ca206d84633d658d7363894c4ea9d59e515c1a/Documentation/specs/runtime-configuration-file.md).</span></span>

   * <span data-ttu-id="6f5e8-131">*HelloWorld.dll*</span><span class="sxs-lookup"><span data-stu-id="6f5e8-131">*HelloWorld.dll*</span></span>

      <span data-ttu-id="6f5e8-132">애플리케이션의 [프레임워크 종속 배포](../deploying/deploy-with-cli.md#framework-dependent-deployment)입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-132">This is the [framework-dependent deployment](../deploying/deploy-with-cli.md#framework-dependent-deployment) version of the application.</span></span> <span data-ttu-id="6f5e8-133">이 동적 연결 라이브러리를 실행하려면 명령 프롬프트에 `dotnet HelloWorld.dll`을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-133">To execute this dynamic link library, enter `dotnet HelloWorld.dll` at a command prompt.</span></span> <span data-ttu-id="6f5e8-134">앱을 실행하는 이 메서드는 .NET Core 런타임이 설치된 모든 플랫폼에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-134">This method of running the app works on any platform that has the .NET Core runtime installed.</span></span>

   * <span data-ttu-id="6f5e8-135">*HelloWorld.exe*(Linux에서는 *HelloWorld*, macOS에서는 생성되지 않음)</span><span class="sxs-lookup"><span data-stu-id="6f5e8-135">*HelloWorld.exe* (*HelloWorld* on Linux, not created on macOS.)</span></span>

      <span data-ttu-id="6f5e8-136">애플리케이션의 [프레임워크 종속 실행 파일](../deploying/deploy-with-cli.md#framework-dependent-executable)입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-136">This is the [framework-dependent executable](../deploying/deploy-with-cli.md#framework-dependent-executable) version of the application.</span></span> <span data-ttu-id="6f5e8-137">이 파일은 운영 체제마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-137">The file is operating-system-specific.</span></span>

   * <span data-ttu-id="6f5e8-138">*HelloWorld.pdb*(배포에 대한 선택 사항)</span><span class="sxs-lookup"><span data-stu-id="6f5e8-138">*HelloWorld.pdb* (optional for deployment)</span></span>

      <span data-ttu-id="6f5e8-139">디버그 기호 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-139">This is the debug symbols file.</span></span> <span data-ttu-id="6f5e8-140">게시된 애플리케이션 버전을 디버그해야 하는 경우에는 이 파일을 저장해야 하지만 그렇지 않으면 애플리케이션과 함께 배포할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-140">You aren't required to deploy this file along with your application, although you should save it in the event that you need to debug the published version of your application.</span></span>

   * <span data-ttu-id="6f5e8-141">*HelloWorld.runtimeconfig.json*</span><span class="sxs-lookup"><span data-stu-id="6f5e8-141">*HelloWorld.runtimeconfig.json*</span></span>

      <span data-ttu-id="6f5e8-142">애플리케이션의 런타임 구성 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-142">This is the application's run-time configuration file.</span></span> <span data-ttu-id="6f5e8-143">애플리케이션이 실행되도록 빌드된 .NET Core의 버전을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-143">It identifies the version of .NET Core that your application was built to run on.</span></span> <span data-ttu-id="6f5e8-144">구성 옵션을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-144">You can also add configuration options to it.</span></span> <span data-ttu-id="6f5e8-145">자세한 내용은 [.NET Core 런타임 구성 설정](../run-time-config/index.md#runtimeconfigjson)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-145">For more information, see [.NET Core run-time configuration settings](../run-time-config/index.md#runtimeconfigjson).</span></span>

## <a name="run-the-published-app"></a><span data-ttu-id="6f5e8-146">게시된 앱 실행</span><span class="sxs-lookup"><span data-stu-id="6f5e8-146">Run the published app</span></span>

1. <span data-ttu-id="6f5e8-147">**Explorer**에서 *publish* 폴더를 마우스 오른쪽 단추로 클릭(macOS의 경우 <kbd>Ctrl</kbd> 키를 누른 상태로 클릭)하고 **터미널에서 열기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-147">In **Explorer**, right-click the *publish* folder (<kbd>Ctrl</kbd>-click on macOS), and select **Open in Terminal**.</span></span>

   :::image type="content" source="media/publishing-with-visual-studio-code/open-in-terminal.png" alt-text="터미널에서 열기를 보여 주는 상황에 맞는 메뉴":::

1. <span data-ttu-id="6f5e8-149">Windows 또는 Linux에서 실행 파일을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-149">On Windows or Linux, run the app by using the executable.</span></span>

   1. <span data-ttu-id="6f5e8-150">Windows에서 `.\HelloWorld.exe`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-150">On Windows, enter `.\HelloWorld.exe` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="6f5e8-151">Linux에서 `./HelloWorld`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-151">On Linux, enter `./HelloWorld` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="6f5e8-152">프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-152">Enter a name in response to the prompt, and press any key to exit.</span></span>

1. <span data-ttu-id="6f5e8-153">모든 플랫폼에서 [`dotnet`](../tools/dotnet.md) 명령을 사용하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-153">On any platform, run the app by using the  [`dotnet`](../tools/dotnet.md) command:</span></span>

   1. <span data-ttu-id="6f5e8-154">`dotnet HelloWorld.dll`을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-154">Enter `dotnet HelloWorld.dll` and press <kbd>Enter</kbd>.</span></span>

   1. <span data-ttu-id="6f5e8-155">프롬프트에 대한 응답으로 이름을 입력하고 아무 키나 눌러 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-155">Enter a name in response to the prompt, and press any key to exit.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6f5e8-156">추가 자료</span><span class="sxs-lookup"><span data-stu-id="6f5e8-156">Additional resources</span></span>

- [<span data-ttu-id="6f5e8-157">.NET Core 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="6f5e8-157">.NET Core application deployment</span></span>](../deploying/index.md)

## <a name="next-steps"></a><span data-ttu-id="6f5e8-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6f5e8-158">Next steps</span></span>

<span data-ttu-id="6f5e8-159">이 자습서에서는 콘솔 앱을 게시했습니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-159">In this tutorial, you published a console app.</span></span> <span data-ttu-id="6f5e8-160">다음 자습서에서는 클래스 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f5e8-160">In the next tutorial, you create a class library.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6f5e8-161">Visual Studio Code에서 .NET Standard 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="6f5e8-161">Create a .NET Standard library in Visual Studio Code</span></span>](library-with-visual-studio-code.md)
