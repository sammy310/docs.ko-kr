---
title: '자습서: .NET 도구 만들기'
description: .NET 도구를 만드는 방법을 알아봅니다. 도구는 .NET CLI를 사용하여 설치되는 콘솔 애플리케이션입니다.
ms.topic: tutorial
ms.date: 12/14/2020
ms.openlocfilehash: dc5cf014336848ff1a3035647a386419653a083b
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633899"
---
# <a name="tutorial-create-a-net-tool-using-the-net-cli"></a><span data-ttu-id="7a78a-104">자습서: .NET CLI를 사용하여 .NET 도구 만들기</span><span class="sxs-lookup"><span data-stu-id="7a78a-104">Tutorial: Create a .NET tool using the .NET CLI</span></span>

<span data-ttu-id="7a78a-105">**이 문서의 적용 대상:**  ✔️ .NET Core 2.1 SDK 이상 버전</span><span class="sxs-lookup"><span data-stu-id="7a78a-105">**This article applies to:** ✔️ .NET Core 2.1 SDK and later versions</span></span>

<span data-ttu-id="7a78a-106">이 자습서에서는 .NET 도구를 만들고 패키지하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-106">This tutorial teaches you how to create and package a .NET tool.</span></span> <span data-ttu-id="7a78a-107">.NET CLI를 사용하면 콘솔 애플리케이션을 도구로 만들어 다른 사용자가 설치하고 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-107">The .NET CLI lets you create a console application as a tool, which others can install and run.</span></span> <span data-ttu-id="7a78a-108">.NET 도구는 .NET CLI에서 설치되는 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-108">.NET tools are NuGet packages that are installed from the .NET CLI.</span></span> <span data-ttu-id="7a78a-109">도구에 대한 자세한 내용은 [.NET 도구 개요](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a78a-109">For more information about tools, see [.NET tools overview](global-tools.md).</span></span>

<span data-ttu-id="7a78a-110">만들 도구는 메시지를 입력으로 사용하고 로봇 이미지를 만드는 텍스트 줄과 함께 메시지를 표시하는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-110">The tool that you'll create is a console application that takes a message as input and displays the message along with lines of text that create the image of a robot.</span></span>

<span data-ttu-id="7a78a-111">이는 세 가지 자습서 시리즈 중 첫 번째입니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-111">This is the first in a series of three tutorials.</span></span> <span data-ttu-id="7a78a-112">이 자습서에서는 도구를 만들고 패키지합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-112">In this tutorial, you create and package a tool.</span></span> <span data-ttu-id="7a78a-113">다음 두 자습서에서는 [도구를 전역 도구로 사용](global-tools-how-to-use.md)하고 [도구를 로컬 도구로 사용](local-tools-how-to-use.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-113">In the next two tutorials you [use the tool as a global tool](global-tools-how-to-use.md) and [use the tool as a local tool](local-tools-how-to-use.md).</span></span> <span data-ttu-id="7a78a-114">도구를 만드는 절차는 전역 도구 또는 로컬 도구로 사용하는지 여부와 관계없이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-114">The procedures for creating a tool are the same whether you use it as a global tool or as a local tool.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="7a78a-115">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="7a78a-115">Prerequisites</span></span>

- <span data-ttu-id="7a78a-116">[.NET SDK 5.0.100](https://dotnet.microsoft.com/download) 이상 버전</span><span class="sxs-lookup"><span data-stu-id="7a78a-116">[.NET SDK 5.0.100](https://dotnet.microsoft.com/download) or a later version.</span></span>

  <span data-ttu-id="7a78a-117">이 자습서에서는 .NET SDK 5.0을 사용하지만 .NET Core SDK 2.1부터 전역 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-117">This tutorial uses .NET SDK 5.0, but global tools are available starting in .NET Core SDK 2.1.</span></span> <span data-ttu-id="7a78a-118">로컬 도구는 .NET Core SDK 3.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-118">Local tools are available starting in .NET Core SDK 3.0.</span></span>

- <span data-ttu-id="7a78a-119">선택하는 텍스트 편집기 또는 코드 편집기입니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-119">A text editor or code editor of your choice.</span></span>

## <a name="create-a-project"></a><span data-ttu-id="7a78a-120">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="7a78a-120">Create a project</span></span>

1. <span data-ttu-id="7a78a-121">명령 프롬프트를 열고 *repository* 라는 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-121">Open a command prompt and create a folder named *repository*.</span></span>

1. <span data-ttu-id="7a78a-122">*repository* 폴더로 이동하여 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-122">Navigate to the *repository* folder and enter the following command:</span></span>

   ```dotnetcli
   dotnet new console -n microsoft.botsay -f net5.0
   ```

   <span data-ttu-id="7a78a-123">이 명령은 *repository* 폴더 아래에 *microsoft.botsay* 라는 새 폴더를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-123">The command creates a new folder named *microsoft.botsay* under the *repository* folder.</span></span>

   > [!NOTE]
   > <span data-ttu-id="7a78a-124">이 자습서에서는 .NET 5.0을 대상으로 하는 도구를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-124">For this tutorial you create a tool that targets .NET 5.0.</span></span> <span data-ttu-id="7a78a-125">다른 프레임워크를 대상으로 하려면 `-f|--framework` 옵션을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-125">To target a different framework, change the `-f|--framework` option.</span></span> <span data-ttu-id="7a78a-126">여러 프레임워크를 대상으로 하려면 다음 예제와 같이 프로젝트 파일에서 `TargetFramework` 요소를 `TargetFrameworks` 요소로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-126">To target multiple frameworks, change the `TargetFramework` element to a `TargetFrameworks` element in the project file, as shown in the following example:</span></span>
   >
   > ```xml
   > <Project Sdk="Microsoft.NET.Sdk">
   >   <PropertyGroup>
   >     <OutputType>Exe</OutputType>
   >     <TargetFrameworks>netcoreapp3.1;net5.0</TargetFrameworks>
   >   </PropertyGroup>
   > </Project>
   > ```

1. <span data-ttu-id="7a78a-127">*microsoft.botsay* 폴더로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-127">Navigate to the *microsoft.botsay* folder.</span></span>

   ```console
   cd microsoft.botsay
   ```

## <a name="add-the-code"></a><span data-ttu-id="7a78a-128">코드 추가</span><span class="sxs-lookup"><span data-stu-id="7a78a-128">Add the code</span></span>

1. <span data-ttu-id="7a78a-129">코드 편집기를 사용하여 `Program.cs` 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-129">Open the `Program.cs` file with your code editor.</span></span>

1. <span data-ttu-id="7a78a-130">다음 `using` 지시문을 파일의 맨 위에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-130">Add the following `using` directive to the top of the file:</span></span>

   ```csharp
   using System.Reflection;
   ```

1. <span data-ttu-id="7a78a-131">`Main` 메서드를 다음 코드로 바꿔 애플리케이션의 명령줄 인수를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-131">Replace the `Main` method with the following code to process the command-line arguments for the application.</span></span>

   ```csharp
   static void Main(string[] args)
   {
       if (args.Length == 0)
       {
           var versionString = Assembly.GetEntryAssembly()
                                   .GetCustomAttribute<AssemblyInformationalVersionAttribute>()
                                   .InformationalVersion
                                   .ToString();

           Console.WriteLine($"botsay v{versionString}");
           Console.WriteLine("-------------");
           Console.WriteLine("\nUsage:");
           Console.WriteLine("  botsay <message>");
           return;
       }

       ShowBot(string.Join(' ', args));
   }
   ```

   <span data-ttu-id="7a78a-132">인수가 전달되지 않으면 짧은 도움말 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-132">If no arguments are passed, a short help message is displayed.</span></span> <span data-ttu-id="7a78a-133">그렇지 않으면 모든 인수가 다음 단계에서 만드는 `ShowBot` 메서드를 호출하여 단일 문자열로 연결되고 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-133">Otherwise, all of the arguments are concatenated into a single string and printed by calling the `ShowBot` method that you create in the next step.</span></span>

1. <span data-ttu-id="7a78a-134">문자열 매개 변수를 사용하는 `ShowBot`이라는 새 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-134">Add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="7a78a-135">이 메서드는 텍스트 줄을 사용하여 메시지와 로봇 이미지를 출력합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-135">The method prints out the message and an image of a robot using lines of text.</span></span>

   ```csharp
   static void ShowBot(string message)
   {
       string bot = $"\n        {message}";
       bot += @"
       __________________
                         \
                          \
                             ....
                             ....'
                              ....
                           ..........
                       .............'..'..
                    ................'..'.....
                  .......'..........'..'..'....
                 ........'..........'..'..'.....
                .'....'..'..........'..'.......'.
                .'..................'...   ......
                .  ......'.........         .....
                .    _            __        ......
               ..    #            ##        ......
              ....       .                 .......
              ......  .......          ............
               ................  ......................
               ........................'................
              ......................'..'......    .......
           .........................'..'.....       .......
        ........    ..'.............'..'....      ..........
      ..'..'...      ...............'.......      ..........
     ...'......     ...... ..........  ......         .......
    ...........   .......              ........        ......
   .......        '...'.'.              '.'.'.'         ....
   .......       .....'..               ..'.....
      ..       ..........               ..'........
             ............               ..............
            .............               '..............
           ...........'..              .'.'............
          ...............              .'.'.............
         .............'..               ..'..'...........
         ...............                 .'..............
          .........                        ..............
           .....
   ";
       Console.WriteLine(bot);
   }
   ```

1. <span data-ttu-id="7a78a-136">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-136">Save your changes.</span></span>

## <a name="test-the-application"></a><span data-ttu-id="7a78a-137">애플리케이션 테스트</span><span class="sxs-lookup"><span data-stu-id="7a78a-137">Test the application</span></span>

<span data-ttu-id="7a78a-138">프로젝트를 실행하고 출력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-138">Run the project and see the output.</span></span> <span data-ttu-id="7a78a-139">다른 결과를 보려면 명령줄에서 다음 변형을 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7a78a-139">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- Hello from the bot
```

<span data-ttu-id="7a78a-140">`--` 구분 기호 뒤의 모든 인수가 애플리케이션에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-140">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="package-the-tool"></a><span data-ttu-id="7a78a-141">도구 패키징</span><span class="sxs-lookup"><span data-stu-id="7a78a-141">Package the tool</span></span>

<span data-ttu-id="7a78a-142">애플리케이션을 도구로 패키지하고 배포하려면 먼저 프로젝트 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-142">Before you can pack and distribute the application as a tool, you need to modify the project file.</span></span>

1. <span data-ttu-id="7a78a-143">*microsoft.botsay.csproj* 파일을 열고 `<PropertyGroup>` 노드 끝에 다음 세 개의 새 XML 노드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-143">Open the *microsoft.botsay.csproj* file and add three new XML nodes to the end of the `<PropertyGroup>` node:</span></span>

   ```xml
   <PackAsTool>true</PackAsTool>
   <ToolCommandName>botsay</ToolCommandName>
   <PackageOutputPath>./nupkg</PackageOutputPath>
   ```

   <span data-ttu-id="7a78a-144">`<ToolCommandName>`은 설치 후 도구를 호출할 명령을 지정하는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-144">`<ToolCommandName>` is an optional element that specifies the command that will invoke the tool after it's installed.</span></span> <span data-ttu-id="7a78a-145">이 요소를 제공하지 않으면 도구의 명령 이름은 *.csproj* 확장명이 없는 프로젝트 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-145">If this element isn't provided, the command name for the tool is the project file name without the *.csproj* extension.</span></span>

   <span data-ttu-id="7a78a-146">`<PackageOutputPath>`는 NuGet 패키지가 생성될 위치를 결정하는 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-146">`<PackageOutputPath>` is an optional element that determines where the NuGet package will be produced.</span></span> <span data-ttu-id="7a78a-147">NuGet 패키지는 .NET CLI가 도구를 설치하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-147">The NuGet package is what the .NET CLI uses to install your tool.</span></span>

   <span data-ttu-id="7a78a-148">이제 프로젝트 파일은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-148">The project file now looks like the following example:</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>

       <OutputType>Exe</OutputType>
       <TargetFramework>net5.0</TargetFramework>

       <PackAsTool>true</PackAsTool>
       <ToolCommandName>botsay</ToolCommandName>
       <PackageOutputPath>./nupkg</PackageOutputPath>

     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="7a78a-149">[dotnet pack](dotnet-pack.md) 명령을 실행하여 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-149">Create a NuGet package by running the [dotnet pack](dotnet-pack.md) command:</span></span>

   ```dotnetcli
   dotnet pack
   ```

   <span data-ttu-id="7a78a-150">*microsoft.botsay.1.0.0.nupkg* 파일은 *microsoft.botsay.csproj* 파일의 `<PackageOutputPath>` 값으로 식별되는 폴더(이 예제에서는 *./nupkg* 폴더)에 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-150">The *microsoft.botsay.1.0.0.nupkg* file is created in the folder identified by the `<PackageOutputPath>` value from the *microsoft.botsay.csproj* file, which in this example is the *./nupkg* folder.</span></span>

   <span data-ttu-id="7a78a-151">공개적으로 도구를 릴리스하려면 `https://www.nuget.org`에 업로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-151">When you want to release a tool publicly, you can upload it to `https://www.nuget.org`.</span></span> <span data-ttu-id="7a78a-152">NuGet에서 도구를 사용할 수 있게 되면 개발자는 [dotnet tool install](dotnet-tool-install.md) 명령을 사용하여 도구를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-152">Once the tool is available on NuGet, developers can install the tool by using the [dotnet tool install](dotnet-tool-install.md) command.</span></span> <span data-ttu-id="7a78a-153">이 자습서에서는 로컬 *nupkg* 폴더에서 패키지를 직접 설치하므로 NuGet에 패키지를 업로드할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-153">For this tutorial you install the package directly from the local *nupkg* folder, so there's no need to upload the package to NuGet.</span></span>

## <a name="troubleshoot"></a><span data-ttu-id="7a78a-154">문제 해결</span><span class="sxs-lookup"><span data-stu-id="7a78a-154">Troubleshoot</span></span>

<span data-ttu-id="7a78a-155">자습서를 수행하는 동안 오류 메시지가 표시되는 경우 [.NET 도구 사용 문제 해결](troubleshoot-usage-issues.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7a78a-155">If you get an error message while following the tutorial, see [Troubleshoot .NET tool usage issues](troubleshoot-usage-issues.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="7a78a-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="7a78a-156">Next steps</span></span>

<span data-ttu-id="7a78a-157">이 자습서에서는 콘솔 애플리케이션을 만들고 도구로 패키지했습니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-157">In this tutorial, you created a console application and packaged it as a tool.</span></span> <span data-ttu-id="7a78a-158">도구를 전역 도구로 사용하는 방법을 알아보려면 다음 자습서로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-158">To learn how to use the tool as a global tool, advance to the next tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7a78a-159">전역 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="7a78a-159">Install and use a global tool</span></span>](global-tools-how-to-use.md)

<span data-ttu-id="7a78a-160">원한다면 전역 도구 자습서를 건너뛰고 로컬 도구 자습서로 바로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7a78a-160">If you prefer, you can skip the global tools tutorial and go directly to the local tools tutorial.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="7a78a-161">로컬 도구 설치 및 사용</span><span class="sxs-lookup"><span data-stu-id="7a78a-161">Install and use a local tool</span></span>](local-tools-how-to-use.md)
