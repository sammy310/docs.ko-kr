---
title: CLI를 사용하여 .NET Core 시작
description: .NET Core CLI를 사용하여 Windows, Linux 또는 macOS에서 .NET Core를 시작하는 방법을 보여 주는 단계별 자습서입니다.
author: thraka
ms.author: adegeo
ms.date: 12/05/2019
ms.technology: dotnet-cli
ms.custom: updateeachrelease
ms.openlocfilehash: fe69521a6ac88055e3e8c8502a7e19a72667dbef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78240859"
---
# <a name="get-started-with-net-core-using-the-net-core-cli"></a><span data-ttu-id="7ff7c-103">.NET Core CLI를 사용하여 .NET Core 시작하기</span><span class="sxs-lookup"><span data-stu-id="7ff7c-103">Get started with .NET Core using the .NET Core CLI</span></span>

<span data-ttu-id="7ff7c-104">이 문서에서는 .NET Core CLI를 사용하여 Windows, Linux 및 macOS에서 작동하는 .NET Core 앱 개발을 시작하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-104">This article will show you how to start developing .NET Core apps that work on Windows, Linux, and macOS using the .NET Core CLI.</span></span>

<span data-ttu-id="7ff7c-105">.NET Core CLI에 익숙하지 않은 경우 [.NET Core CLI 개요](../tools/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-105">If you're unfamiliar with the .NET Core CLI, see the [.NET Core CLI overview](../tools/index.md).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7ff7c-106">필수 구성 요소</span><span class="sxs-lookup"><span data-stu-id="7ff7c-106">Prerequisites</span></span>

- <span data-ttu-id="7ff7c-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) 이상 버전</span><span class="sxs-lookup"><span data-stu-id="7ff7c-107">[.NET Core SDK 3.1](https://dotnet.microsoft.com/download) or later versions.</span></span>
- <span data-ttu-id="7ff7c-108">선택하는 텍스트 편집기 또는 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-108">A text editor or code editor of your choice.</span></span>

## <a name="hello-console-app"></a><span data-ttu-id="7ff7c-109">Hello, 콘솔 앱!</span><span class="sxs-lookup"><span data-stu-id="7ff7c-109">Hello, Console App!</span></span>

<span data-ttu-id="7ff7c-110">GitHub의 dotnet/samples 리포지토리에서 [샘플 코드를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-110">You can [view or download the sample code](https://github.com/dotnet/samples/tree/master/core/console-apps/HelloMsBuild) from the dotnet/samples GitHub repository.</span></span> <span data-ttu-id="7ff7c-111">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-111">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="7ff7c-112">명령 프롬프트를 열고 *Hello*라는 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-112">Open a command prompt and create a folder named *Hello*.</span></span> <span data-ttu-id="7ff7c-113">만든 폴더로 이동하고 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-113">Navigate to the folder you created and type the following.</span></span>

```dotnetcli
dotnet new console
dotnet run
```

<span data-ttu-id="7ff7c-114">이제 간단한 연습을 해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-114">Let's do a quick walkthrough:</span></span>

01. `dotnet new console`

    <span data-ttu-id="7ff7c-115">[dotnet new](../tools/dotnet-new.md)는 콘솔 앱을 빌드하는 데 필요한 종속성이 있는 최신 *Hello.csproj* 프로젝트 파일입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-115">[dotnet new](../tools/dotnet-new.md) creates an up-to-date *Hello.csproj* project file with the dependencies necessary to build a console app.</span></span> <span data-ttu-id="7ff7c-116">애플리케이션에 대한 진입점을 포함하는 기본 파일인 *Program.cs*도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-116">It also creates a *Program.cs*, a basic file containing the entry point for the application.</span></span>

    <span data-ttu-id="7ff7c-117">*Hello.csproj*:</span><span class="sxs-lookup"><span data-stu-id="7ff7c-117">*Hello.csproj*:</span></span>

    [!code-xml[Hello.csproj](~/samples/snippets/core/tutorials/cli-create-console-app/HelloMsBuild/csharp/Hello.csproj)]

    <span data-ttu-id="7ff7c-118">프로젝트 파일은 종속성을 복원하고 프로그램을 빌드하는 데 필요한 모든 항목을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-118">The project file specifies everything that's needed to restore dependencies and build the program.</span></span>

    - <span data-ttu-id="7ff7c-119">`<OutputType>` 요소는 실행 파일, 즉 콘솔 애플리케이션을 빌드하고 있음을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-119">The `<OutputType>` element specifies that we're building an executable, in other words a console application.</span></span>
    - <span data-ttu-id="7ff7c-120">`<TargetFramework>` 요소는 대상으로 하는 .NET 구현을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-120">The `<TargetFramework>` element specifies what .NET implementation we're targeting.</span></span> <span data-ttu-id="7ff7c-121">고급 시나리오에서는 여러 대상 프레임워크를 지정하고 이 모든 프레임워크를 단일 작업으로 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-121">In an advanced scenario, you can specify multiple target frameworks and build to all those in a single operation.</span></span> <span data-ttu-id="7ff7c-122">이 자습서에서는 .NET Core 3.1에 대해서만 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-122">In this tutorial, we'll stick to building only for .NET Core 3.1.</span></span>

    <span data-ttu-id="7ff7c-123">*Program.cs*:</span><span class="sxs-lookup"><span data-stu-id="7ff7c-123">*Program.cs*:</span></span>

    [!code-csharp[Program.cs](~/samples/snippets/core/tutorials/cli-create-console-app/HelloMsBuild/csharp/Program.cs)]

    <span data-ttu-id="7ff7c-124">프로그램은 `using System`으로 시작됩니다. 즉, "`System` 네임스페이스의 모든 항목을 이 파일 범위로 가져옵니다".</span><span class="sxs-lookup"><span data-stu-id="7ff7c-124">The program starts by `using System`, which means "bring everything in the `System` namespace into scope for this file".</span></span> <span data-ttu-id="7ff7c-125">`System` 네임스페이스는 `Console` 클래스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-125">The `System` namespace includes the `Console` class.</span></span>

    <span data-ttu-id="7ff7c-126">그런 다음 `Hello`라는 네임스페이스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-126">We then define a namespace called `Hello`.</span></span> <span data-ttu-id="7ff7c-127">이 이름은 원하는 값으로 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-127">You can change this to anything you want.</span></span> <span data-ttu-id="7ff7c-128">`Program`이라는 클래스는 해당 네임스페이스 내에서 `Main`라는 문자열 배열을 사용하는 `args` 메서드로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-128">A class named `Program` is defined within that namespace, with a `Main` method that takes an array of strings named `args`.</span></span> <span data-ttu-id="7ff7c-129">이 배열에는 프로그램이 실행될 때 전달되는 인수 목록이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-129">This array contains the list of arguments passed in when the program is run.</span></span> <span data-ttu-id="7ff7c-130">이 상태 그대로 배열은 사용되지 않으며 프로그램은 단순히 "Hello World!"라는 텍스트를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-130">As it is, this array is not used and the program simply writes the text "Hello World!"</span></span> <span data-ttu-id="7ff7c-131">보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-131">to the console.</span></span> <span data-ttu-id="7ff7c-132">나중에 이 인수를 사용하는 코드를 변경할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-132">Later, we'll make changes to the code that will make use of this argument.</span></span>

    <span data-ttu-id="7ff7c-133">`dotnet new`는 [dotnet restore](../tools/dotnet-restore.md)를 암시적으로 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-133">`dotnet new` calls [dotnet restore](../tools/dotnet-restore.md) implicitly.</span></span> <span data-ttu-id="7ff7c-134">`dotnet restore`는 [NuGet](https://www.nuget.org/)(.NET 패키지 관리자)을 호출하여 종속성 트리를 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-134">`dotnet restore` calls into [NuGet](https://www.nuget.org/) (.NET package manager) to restore the tree of dependencies.</span></span> <span data-ttu-id="7ff7c-135">NuGet은 *Hello.csproj* 파일을 분석하고, 파일에 정의된 종속성을 다운로드하고(또는 머신의 캐시에서 종속성을 가져오고), 샘플을 컴파일 및 실행하는 데 필요한 *obj/project.assets.json* 파일을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-135">NuGet analyzes the *Hello.csproj* file, downloads the dependencies defined in the file (or grabs them from a cache on your machine), and writes the *obj/project.assets.json* file, which is necessary to compile and run the sample.</span></span>

02. `dotnet run`

    <span data-ttu-id="7ff7c-136">[dotnet run](../tools/dotnet-run.md)은 [dotnet build](../tools/dotnet-build.md)를 호출하여 빌드 대상이 빌드되었는지를 확인하고 `dotnet <assembly.dll>`을 호출하여 대상 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-136">[dotnet run](../tools/dotnet-run.md) calls [dotnet build](../tools/dotnet-build.md) to ensure that the build targets have been built, and then calls `dotnet <assembly.dll>` to run the target application.</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="7ff7c-137">다음과 같은 출력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-137">You get the following output.</span></span>

    ```console
    Hello World!
    ```

    <span data-ttu-id="7ff7c-138">또한 `dotnet build`를 실행하여 빌드 콘솔 애플리케이션을 실행하지 않고 코드를 컴파일할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-138">Alternatively, you can also run `dotnet build` to compile the code without running the build console applications.</span></span> <span data-ttu-id="7ff7c-139">그러면 프로젝트 이름에 따라 컴파일된 애플리케이션이 DLL 파일로 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-139">This results in a compiled application, as a DLL file, based on the name of the project.</span></span> <span data-ttu-id="7ff7c-140">이 경우 만들어진 파일 이름은 *Hello.dll*입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-140">In this case, the file created is named *Hello.dll*.</span></span> <span data-ttu-id="7ff7c-141">이 앱은 Windows에서 `dotnet bin\Debug\netcoreapp3.1\Hello.dll`을 사용하여 실행할 수 있습니다(비 Windows 시스템의 경우 `/` 사용).</span><span class="sxs-lookup"><span data-stu-id="7ff7c-141">This app can be run with `dotnet bin\Debug\netcoreapp3.1\Hello.dll` on Windows (use `/` for non-Windows systems).</span></span>

    ```dotnetcli
    dotnet bin\Debug\netcoreapp3.1\Hello.dll
    ```

    <span data-ttu-id="7ff7c-142">다음과 같은 출력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-142">You get the following output.</span></span>

    ```console
    Hello World!
    ```

    <span data-ttu-id="7ff7c-143">앱이 컴파일되면 운영 체제별 실행 파일이 `Hello.dll`과 함께 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-143">When the app is compiled, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="7ff7c-144">Windows에서는 `Hello.exe`, Linux 또는 macOS에서는 `hello`가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-144">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="7ff7c-145">위의 예제에서 파일은 `Hello.exe` 또는 `Hello`로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-145">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="7ff7c-146">해당 실행 파일을 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-146">You can run that executable directly.</span></span>

    ```console
    .\bin\Debug\netcoreapp3.1\Hello.exe

    Hello World!
    ```

## <a name="modify-the-program"></a><span data-ttu-id="7ff7c-147">프로그램 수정</span><span class="sxs-lookup"><span data-stu-id="7ff7c-147">Modify the program</span></span>

<span data-ttu-id="7ff7c-148">프로그램을 조금 변경해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-148">Let's change the program a bit.</span></span> <span data-ttu-id="7ff7c-149">피보나치 숫자가 흥미로우므로, 인수 사용과 함께 피보나치 숫자를 추가하여 앱을 실행하는 사람을 맞이해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-149">Fibonacci numbers are fun, so let's add that and also to use the argument to greet the person running the app.</span></span>

01. <span data-ttu-id="7ff7c-150">*Program.cs* 파일의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-150">Replace the contents of your *Program.cs*  file with the following code:</span></span>

    [!code-csharp[Fibonacci](~/samples/snippets/core/tutorials/cli-create-console-app/fibonacci-msbuild/csharp/Program.cs)]

02. <span data-ttu-id="7ff7c-151">[dotnet build](../tools/dotnet-build.md)를 실행하여 변경 내용을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-151">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

03. <span data-ttu-id="7ff7c-152">앱에 매개 변수를 전달하는 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-152">Run the program passing a parameter to the app.</span></span> <span data-ttu-id="7ff7c-153">`dotnet` 명령을 사용하여 앱을 실행하는 경우 끝부분에 `--`를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-153">When you use the `dotnet` command to run an app, add `--` to the end.</span></span> <span data-ttu-id="7ff7c-154">`--`의 오른쪽에 있는 모든 항목은 애플리케이션에 매개 변수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-154">Anything to the right of `--` will be passed as a parameter to the app.</span></span> <span data-ttu-id="7ff7c-155">다음 예제에서는 `John` 값이 앱에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-155">In the following example, the value `John` is passed to the app.</span></span>

    ```dotnetcli
    dotnet run -- John
    ```

    <span data-ttu-id="7ff7c-156">다음과 같은 출력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-156">You get the following output.</span></span>

    ```console
    Hello John!
    Fibonacci Numbers 1-15:
    1: 0
    2: 1
    3: 1
    4: 2
    5: 3
    6: 5
    7: 8
    8: 13
    9: 21
    10: 34
    11: 55
    12: 89
    13: 144
    14: 233
    15: 377
    ```

<span data-ttu-id="7ff7c-157">이것으로 끝입니다!</span><span class="sxs-lookup"><span data-stu-id="7ff7c-157">And that's it!</span></span> <span data-ttu-id="7ff7c-158">원하는 대로 *Program.cs*를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-158">You can modify *Program.cs* any way you like.</span></span>

## <a name="working-with-multiple-files"></a><span data-ttu-id="7ff7c-159">여러 파일 작업</span><span class="sxs-lookup"><span data-stu-id="7ff7c-159">Working with multiple files</span></span>

<span data-ttu-id="7ff7c-160">단일 파일은 간단한 일회용 프로그램에 적합하지만 더 복잡한 앱을 빌드하는 경우 프로젝트에 여러 코드 파일이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-160">Single files are fine for simple one-off programs, but if you're building a more complex app, you're probably going to have multiple code files on your project.</span></span> <span data-ttu-id="7ff7c-161">일부 피보나치 값을 캐시하여 이전 피보나치 예제에서 빌드하고 몇몇 재귀 기능을 추가해보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-161">Let's build off of the previous Fibonacci example by caching some Fibonacci values and add some recursive features.</span></span>

01. <span data-ttu-id="7ff7c-162">다음 코드를 사용하여 *Hello* 디렉터리 내에 *FibonacciGenerator.cs*라는 새 파일을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-162">Add a new file inside the *Hello* directory named *FibonacciGenerator.cs* with the following code:</span></span>

    [!code-csharp[Fibonacci Generator](~/samples/snippets/core/tutorials/cli-create-console-app/FibonacciBetterMsBuild/csharp/FibonacciGenerator.cs)]

02. <span data-ttu-id="7ff7c-163">다음 예제에서처럼 `Main`Program.cs*파일의* 메서드를 변경하여 새 클래스를 인스턴스화하고 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-163">Change the `Main` method in your *Program.cs* file to instantiate the new class and call its method as in the following example:</span></span>

    [!code-csharp[New Program.cs](~/samples/snippets/core/tutorials/cli-create-console-app/FibonacciBetterMsBuild/csharp/Program.cs)]

03. <span data-ttu-id="7ff7c-164">[dotnet build](../tools/dotnet-build.md)를 실행하여 변경 내용을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-164">Run [dotnet build](../tools/dotnet-build.md) to compile the changes.</span></span>

04. <span data-ttu-id="7ff7c-165">[dotnet run](../tools/dotnet-run.md)을 실행하여 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-165">Run your app by executing [dotnet run](../tools/dotnet-run.md).</span></span>

    ```dotnetcli
    dotnet run
    ```

    <span data-ttu-id="7ff7c-166">다음과 같은 출력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-166">You get the following output.</span></span>

    ```console
    0
    1
    1
    2
    3
    5
    8
    13
    21
    34
    55
    89
    144
    233
    377
    ```

## <a name="publish-your-app"></a><span data-ttu-id="7ff7c-167">앱 게시</span><span class="sxs-lookup"><span data-stu-id="7ff7c-167">Publish your app</span></span>

<span data-ttu-id="7ff7c-168">앱을 배포할 준비가 되면 [dotnet publish](../tools/dotnet-publish.md) 명령을 사용하여 _bin_debug_netcoreapp3.1\\publish\\\\에서 \\publish_ 폴더를 생성합니다(비 Windows 시스템의 경우 `/` 사용).</span><span class="sxs-lookup"><span data-stu-id="7ff7c-168">Once you're ready to distribute your app, use the [dotnet publish](../tools/dotnet-publish.md) command to generate the _publish_ folder at _bin\\debug\\netcoreapp3.1\\publish\\_ (use `/` for non-Windows systems).</span></span> <span data-ttu-id="7ff7c-169">이미 dotnet 런타임을 설치한 경우에 _publish_ 폴더의 콘텐츠를 다른 플랫폼에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-169">You can distribute the contents of the _publish_ folder to other platforms as long as they've already installed the dotnet runtime.</span></span>

```dotnetcli
dotnet publish
```

<span data-ttu-id="7ff7c-170">그러면 다음과 같은 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-170">You get output similar to the following.</span></span>

```console
Microsoft (R) Build Engine version 16.4.0+e901037fe for .NET Core
Copyright (C) Microsoft Corporation. All rights reserved.

  Restore completed in 20 ms for C:\Code\Temp\Hello\Hello.csproj.
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\Hello.dll
  Hello -> C:\Code\Temp\Hello\bin\Debug\netcoreapp3.1\publish\
```

<span data-ttu-id="7ff7c-171">위의 출력은 현재 폴더 및 운영 체제에 따라 다를 수 있지만 출력은 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-171">The output above may differ based on your current folder and operating system, but the output should be similar.</span></span>

<span data-ttu-id="7ff7c-172">[dotnet](../tools/dotnet.md) 명령으로 게시된 앱을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-172">You can run your published app with the [dotnet](../tools/dotnet.md) command:</span></span>

```dotnetcli
dotnet bin\Debug\netcoreapp3.1\publish\Hello.dll
```

<span data-ttu-id="7ff7c-173">다음과 같은 출력을 얻습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-173">You get the following output.</span></span>

```console
Hello World!
```

<span data-ttu-id="7ff7c-174">이 문서의 시작 부분에서 설명한 대로 운영 체제별 실행 파일이 `Hello.dll`과 함께 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-174">As mentioned at the start of this article, an operating system-specific executable was created along with the `Hello.dll`.</span></span> <span data-ttu-id="7ff7c-175">Windows에서는 `Hello.exe`, Linux 또는 macOS에서는 `hello`가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-175">On Windows, this would be `Hello.exe`; on Linux or macOS, this would be `hello`.</span></span> <span data-ttu-id="7ff7c-176">위의 예제에서 파일은 `Hello.exe` 또는 `Hello`로 이름이 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-176">With the example above, the file is named with `Hello.exe` or `Hello`.</span></span> <span data-ttu-id="7ff7c-177">게시된 이 실행 파일을 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-177">You can run this published executable directly.</span></span>

```console
.\bin\Debug\netcoreapp3.1\publish\Hello.exe

Hello World!
```

## <a name="conclusion"></a><span data-ttu-id="7ff7c-178">결론</span><span class="sxs-lookup"><span data-stu-id="7ff7c-178">Conclusion</span></span>

<span data-ttu-id="7ff7c-179">이것으로 끝입니다!</span><span class="sxs-lookup"><span data-stu-id="7ff7c-179">And that's it!</span></span> <span data-ttu-id="7ff7c-180">이제 여기에서 배운 기본 개념을 활용하여 고유의 프로그램을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff7c-180">Now, you can start using the basic concepts learned here to create your own programs.</span></span>

## <a name="see-also"></a><span data-ttu-id="7ff7c-181">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ff7c-181">See also</span></span>

- [<span data-ttu-id="7ff7c-182">.NET Core CLI를 사용하여 프로젝트 구성 및 테스트</span><span class="sxs-lookup"><span data-stu-id="7ff7c-182">Organizing and testing projects with the .NET Core CLI</span></span>](testing-with-cli.md)
- [<span data-ttu-id="7ff7c-183">.NET Core CLI를 사용하여 .NET Core 앱 게시</span><span class="sxs-lookup"><span data-stu-id="7ff7c-183">Publish .NET Core apps with the .NET Core CLI</span></span>](../deploying/deploy-with-cli.md)
- [<span data-ttu-id="7ff7c-184">.NET Core 애플리케이션 배포</span><span class="sxs-lookup"><span data-stu-id="7ff7c-184">.NET Core application deployment</span></span>](../deploying/index.md)
