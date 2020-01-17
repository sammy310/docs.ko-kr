---
title: .NET Core 전역 도구를 만드는 방법
description: 전역 도구를 만드는 방법을 설명합니다. 전역 도구는 .NET Core CLI를 통해 설치되는 콘솔 애플리케이션입니다.
author: Thraka
ms.author: adegeo
ms.date: 08/22/2018
ms.openlocfilehash: 1daecf7234f02a5fe0dcf25cf7edbb0af327b8c1
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75343517"
---
# <a name="create-a-net-core-global-tool-using-the-net-core-cli"></a><span data-ttu-id="4627e-104">.NET Core CLI를 사용하여 .NET Core 전역 도구 만들기</span><span class="sxs-lookup"><span data-stu-id="4627e-104">Create a .NET Core Global Tool using the .NET Core CLI</span></span>

<span data-ttu-id="4627e-105">이 문서에서는 .NET Core 전역 도구를 만들고 패키지하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-105">This article teaches you how to create and package a .NET Core Global Tool.</span></span> <span data-ttu-id="4627e-106">.NET Core CLI를 사용하면 콘솔 애플리케이션을 다른 사용자가 쉽게 설치하고 실행할 수 있는 전역 도구로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-106">The .NET Core CLI allows you to create a console application as a Global Tool, which others can easily install and run.</span></span> <span data-ttu-id="4627e-107">.NET Core 전역 도구는 .NET Core CLI에서 설치되는 NuGet 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-107">.NET Core Global Tools are NuGet packages that are installed from the .NET Core CLI.</span></span> <span data-ttu-id="4627e-108">Global Tools에 대한 자세한 내용은 [.NET Core Global Tools 개요](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4627e-108">For more information about Global Tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

[!INCLUDE [topic-appliesto-net-core-21plus.md](../../../includes/topic-appliesto-net-core-21plus.md)]

## <a name="create-a-project"></a><span data-ttu-id="4627e-109">프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="4627e-109">Create a project</span></span>

<span data-ttu-id="4627e-110">이 문서에서는 .NET Core CLI를 사용하여 프로젝트를 만들고 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-110">This article uses the .NET Core CLI to create and manage a project.</span></span>

<span data-ttu-id="4627e-111">예제 도구는 ASCII 봇을 생성하고 메시지를 인쇄하는 콘솔 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-111">Our example tool will be a console application that generates an ASCII bot and prints a message.</span></span> <span data-ttu-id="4627e-112">먼저 새 .NET Core 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-112">First, create a new .NET Core Console Application.</span></span>

```dotnetcli
dotnet new console -o botsay
```

<span data-ttu-id="4627e-113">이전 명령에서 생성된 `botsay` 디렉터리로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-113">Navigate to the `botsay` directory created by the previous command.</span></span>

## <a name="add-the-code"></a><span data-ttu-id="4627e-114">코드 추가</span><span class="sxs-lookup"><span data-stu-id="4627e-114">Add the code</span></span>

<span data-ttu-id="4627e-115">`vim` 또는 [Visual Studio Code](https://code.visualstudio.com/)와 같은 원하는 텍스트 편집기를 사용하여 `Program.cs` 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-115">Open the `Program.cs` file with your favorite text editor, such as `vim` or [Visual Studio Code](https://code.visualstudio.com/).</span></span>

<span data-ttu-id="4627e-116">다음 `using` 지시문을 파일 맨 위에 추가하면 애플리케이션의 버전 정보를 표시하는 코드를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-116">Add the following `using` directive to the top of the file, this helps shorten the code to display the version information of the application.</span></span>

```csharp
using System.Reflection;
```

<span data-ttu-id="4627e-117">그런 다음, `Main` 메서드까지 아래로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-117">Next, move down to the `Main` method.</span></span> <span data-ttu-id="4627e-118">메서드를 다음 코드로 바꿔 애플리케이션의 명령줄 인수를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-118">Replace the method with the following code to process the command-line arguments for your application.</span></span> <span data-ttu-id="4627e-119">인수가 전달되지 않으면 짧은 도움말 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-119">If no arguments were passed, a short help message is displayed.</span></span> <span data-ttu-id="4627e-120">인수가 전달되면 모든 해당 인수가 문자열로 변환되고 봇을 통해 인쇄됩니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-120">Otherwise, all of those arguments are transformed into a string and printed with the bot.</span></span>

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

### <a name="create-the-bot"></a><span data-ttu-id="4627e-121">봇 만들기</span><span class="sxs-lookup"><span data-stu-id="4627e-121">Create the bot</span></span>

<span data-ttu-id="4627e-122">그런 다음, 문자열 매개 변수를 사용하는 `ShowBot`이라는 새 메서드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-122">Next, add a new method named `ShowBot` that takes a string parameter.</span></span> <span data-ttu-id="4627e-123">이 메서드는 메시지 및 ASCII 봇을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-123">This method prints out the message and the ASCII bot.</span></span> <span data-ttu-id="4627e-124">ASCII 봇 코드는 [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs) 샘플에서 가져왔습니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-124">The ASCII bot code was taken from the [dotnetbot](https://github.com/dotnet/core/blob/master/samples/dotnetsay/Program.cs) sample.</span></span>

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

### <a name="test-the-tool"></a><span data-ttu-id="4627e-125">도구 테스트</span><span class="sxs-lookup"><span data-stu-id="4627e-125">Test the tool</span></span>

<span data-ttu-id="4627e-126">프로젝트를 실행하고 출력을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-126">Run the project and see the output.</span></span> <span data-ttu-id="4627e-127">다른 결과를 보려면 명령줄에서 다음 변형을 시도해 보세요.</span><span class="sxs-lookup"><span data-stu-id="4627e-127">Try these variations at the command line to see different results:</span></span>

```dotnetcli
dotnet run
dotnet run -- "Hello from the bot"
dotnet run -- hello from the bot
```

<span data-ttu-id="4627e-128">`--` 구분 기호 뒤의 모든 인수가 애플리케이션에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-128">All arguments after the `--` delimiter are passed to your application.</span></span>

## <a name="set-up-the-global-tool"></a><span data-ttu-id="4627e-129">전역 도구 설정</span><span class="sxs-lookup"><span data-stu-id="4627e-129">Set up the global tool</span></span>

<span data-ttu-id="4627e-130">애플리케이션을 패키지하고 전역 도구로 배포하려면 먼저 프로젝트 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-130">Before you can pack and distribute the application as a Global Tool, you need to modify the project file.</span></span> <span data-ttu-id="4627e-131">`botsay.csproj` 파일을 열고 다음 세 개의 새 XML 노드를 `<Project><PropertyGroup>` 노드에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-131">Open the `botsay.csproj` file and add three new XML nodes to the `<Project><PropertyGroup>` node:</span></span>

- `<PackAsTool>`\
<span data-ttu-id="4627e-132">[필수] 애플리케이션이 전역 도구로 설치하도록 패키지됨을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-132">[REQUIRED] Indicates that the application will be packaged for install as a Global Tool.</span></span>

- `<ToolCommandName>`\
<span data-ttu-id="4627e-133">[선택 사항] 도구의 대체 이름입니다. 그렇지 않으면 도구의 명령 이름이 프로젝트 파일 이름 뒤에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-133">[OPTIONAL] An alternative name for the tool, otherwise the command name for the tool will be named after the project file.</span></span> <span data-ttu-id="4627e-134">패키지에 여러 도구를 포함할 수 있고, 고유하고 친숙한 이름을 선택하면 동일 패키지의 다른 도구와 구별하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-134">You can have multiple tools in a package, choosing a unique and friendly name helps differentiate from other tools in the same package.</span></span>

- `<PackageOutputPath>`\
<span data-ttu-id="4627e-135">[선택 사항] NuGet 패키지가 생성될 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-135">[OPTIONAL] Where the NuGet package will be produced.</span></span> <span data-ttu-id="4627e-136">NuGet 패키지는 .NET Core CLI 전역 도구가 도구를 설치하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-136">The NuGet package is what the .NET Core CLI Global Tools uses to install your tool.</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp2.1</TargetFramework>

    <PackAsTool>true</PackAsTool>
    <ToolCommandName>botsay</ToolCommandName>
    <PackageOutputPath>./nupkg</PackageOutputPath>

  </PropertyGroup>

</Project>
```

<span data-ttu-id="4627e-137">`<PackageOutputPath>`는 선택 사항이지만 이 예제에서는 이 항목을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-137">Even though `<PackageOutputPath>` is optional, use it in this example.</span></span> <span data-ttu-id="4627e-138">`<PackageOutputPath>./nupkg</PackageOutputPath>`를 설정했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-138">Make sure you set it: `<PackageOutputPath>./nupkg</PackageOutputPath>`.</span></span>

<span data-ttu-id="4627e-139">그런 다음, 애플리케이션용 NuGet 패키지를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-139">Next, create a NuGet package for your application.</span></span>

```dotnetcli
dotnet pack
```

<span data-ttu-id="4627e-140">`botsay.1.0.0.nupkg` 파일은 `botsay.csproj` 파일의 `<PackageOutputPath>` XML 값으로 식별되는 폴더에 생성됩니다(이 예제에서는 `./nupkg` 폴더).</span><span class="sxs-lookup"><span data-stu-id="4627e-140">The `botsay.1.0.0.nupkg` file is created in the folder identified by the `<PackageOutputPath>` XML value from the `botsay.csproj` file, which in this example is the `./nupkg` folder.</span></span> <span data-ttu-id="4627e-141">이를 사용하여 쉽게 설치 및 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-141">This makes it easy to install and test.</span></span> <span data-ttu-id="4627e-142">공개적으로 도구를 릴리스하려면 <https://www.nuget.org>에 업로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-142">When you want to release a tool publicly, upload it to <https://www.nuget.org>.</span></span> <span data-ttu-id="4627e-143">NuGet에서 도구를 사용할 수 있게 되면 개발자는 [dotnet tool install](dotnet-tool-install.md) 명령의 `--global` 옵션을 사용하여 사용자 수준의 도구 설치를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-143">Once the tool is available on NuGet, developers can perform a user-wide installation of the tool using the `--global` option of the [dotnet tool install](dotnet-tool-install.md) command.</span></span>

<span data-ttu-id="4627e-144">이제 패키지가 있으므로 해당 패키지에서 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-144">Now that you have a package, install the tool from that package:</span></span>

```dotnetcli
dotnet tool install --global --add-source ./nupkg botsay
```

<span data-ttu-id="4627e-145">`--add-source` 매개 변수는 NuGet 패키지의 추가 소스 피드로 `./nupkg` 폴더(여기서는 `<PackageOutputPath>` 폴더)를 임시로 사용하도록 .NET Core CLI에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-145">The `--add-source` parameter tells the .NET Core CLI to temporarily use the `./nupkg` folder (our `<PackageOutputPath>` folder) as an additional source feed for NuGet packages.</span></span> <span data-ttu-id="4627e-146">Global Tools를 설치하는 방법에 대한 자세한 내용은 [.NET Core Global Tools 개요](global-tools.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4627e-146">For more information about installing Global Tools, see [.NET Core Global Tools overview](global-tools.md).</span></span>

<span data-ttu-id="4627e-147">설치에 성공하면 다음 예와 같이 도구와 설치된 버전을 호출하는 데 사용되는 명령을 보여 주는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-147">If installation is successful, a message is displayed showing the command used to call the tool and the version installed, similar to the following example:</span></span>

```output
You can invoke the tool using the following command: botsay
Tool 'botsay' (version '1.0.0') was successfully installed.
```

<span data-ttu-id="4627e-148">이제 `botsay`를 입력하고 도구에서 응답을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-148">You should now be able to type `botsay` and get a response from the tool.</span></span>

> [!NOTE]
> <span data-ttu-id="4627e-149">설치에 성공했지만 `botsay` 명령을 사용할 수 없는 경우에는 새 터미널을 열고 PATH를 새로 고쳐야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-149">If the install was successful, but you cannot use the `botsay` command, you may need to open a new terminal to refresh the PATH.</span></span>

## <a name="remove-the-tool"></a><span data-ttu-id="4627e-150">도구 제거</span><span class="sxs-lookup"><span data-stu-id="4627e-150">Remove the tool</span></span>

<span data-ttu-id="4627e-151">도구를 사용한 실험을 완료하면 다음 명령을 사용하여 도구를 제거할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4627e-151">Once you're done experimenting with the tool, you can remove it with the following command:</span></span>

```dotnetcli
dotnet tool uninstall -g botsay
```
