---
title: '자습서: Visual Studio Code를 사용하여 macOS에서 .NET Core 솔루션 만들기'
description: 이 문서에서는 Visual Studio Code를 사용하여 .NET Core 솔루션을 만드는 단계와 워크플로를 제공합니다.
ms.date: 12/19/2019
ms.openlocfilehash: f5da16d413ddc25587ff35550fe9f308dc87f4bb
ms.sourcegitcommit: 00aa62e2f469c2272a457b04e66b4cc3c97a800b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2020
ms.locfileid: "78156597"
---
# <a name="tutorial-create-a-net-core-solution-in-macos-using-visual-studio-code"></a><span data-ttu-id="a5685-103">자습서: Visual Studio Code를 사용하여 macOS에서 .NET Core 솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="a5685-103">Tutorial: Create a .NET Core solution in macOS using Visual Studio Code</span></span>

<span data-ttu-id="a5685-104">이 문서에서는 macOS용 .NET Core 솔루션을 만드는 단계와 워크플로를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-104">This document provides the steps and workflow to create a .NET Core solution for macOS.</span></span> <span data-ttu-id="a5685-105">프로젝트 및 단위 테스트를 만들고, 디버깅 도구를 사용하고, [NuGet](https://www.nuget.org/)을 통해 타사 라이브러리를 통합하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-105">Learn how to create projects, unit tests, use the debugging tools, and incorporate third-party libraries via [NuGet](https://www.nuget.org/).</span></span>

> [!NOTE]
> <span data-ttu-id="a5685-106">이 문서에서는 macOS의 [Visual Studio Code](https://code.visualstudio.com)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-106">This article uses [Visual Studio Code](https://code.visualstudio.com) on macOS.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="a5685-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="a5685-107">Prerequisites</span></span>

<span data-ttu-id="a5685-108">[.NET Core SDK](https://dotnet.microsoft.com/download)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-108">Install the [.NET Core SDK](https://dotnet.microsoft.com/download).</span></span> <span data-ttu-id="a5685-109">.NET Core SDK에는 최신 버전의 .NET Core 프레임워크 및 런타임이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-109">The .NET Core SDK includes the latest release of the .NET Core framework and runtime.</span></span>

<span data-ttu-id="a5685-110">[Visual Studio Code](https://code.visualstudio.com)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-110">Install [Visual Studio Code](https://code.visualstudio.com).</span></span> <span data-ttu-id="a5685-111">이 문서를 진행하면서 .NET Core 개발자 환경을 개선하는 Visual Studio Code 확장도 설치하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-111">During the course of this article, you also install Visual Studio Code extensions that improve the .NET Core development experience.</span></span>

<span data-ttu-id="a5685-112">Visual Studio Code 팔레트를 열려면 Visual Studio Code를 열고 <kbd>Fn</kbd>+<kbd>F1</kbd> 키를 눌러 Visual Studio Code C# 확장을 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-112">Install the Visual Studio Code C# extension by opening Visual Studio Code and pressing <kbd>Fn</kbd>+<kbd>F1</kbd> to open the Visual Studio Code palette.</span></span> <span data-ttu-id="a5685-113">**ext install**을 입력하여 확장 목록을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-113">Type **ext install** to see the list of extensions.</span></span> <span data-ttu-id="a5685-114">C# 확장을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-114">Select the C# extension.</span></span> <span data-ttu-id="a5685-115">Visual Studio Code를 다시 시작하여 확장을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-115">Restart Visual Studio Code to activate the extension.</span></span> <span data-ttu-id="a5685-116">자세한 내용은 [Visual Studio Code C# 확장 문서](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5685-116">For more information, see the [Visual Studio Code C# Extension documentation](https://github.com/OmniSharp/omnisharp-vscode/blob/master/debugger.md).</span></span>

## <a name="get-started"></a><span data-ttu-id="a5685-117">시작</span><span class="sxs-lookup"><span data-stu-id="a5685-117">Get started</span></span>

<span data-ttu-id="a5685-118">이 자습서에서는 라이브러리 프로젝트, 해당 라이브러리 프로젝트에 대한 테스트, 라이브러리를 사용하는 콘솔 애플리케이션 등 프로젝트 3개를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-118">In this tutorial, you create three projects: a library project, tests for that library project, and a console application that makes use of the library.</span></span> <span data-ttu-id="a5685-119">GitHub의 dotnet/samples 리포지토리에서 이 문서에 대한 [소스를 보거나 다운로드](https://github.com/dotnet/samples/tree/master/core/getting-started/golden)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-119">You can [view or download the source](https://github.com/dotnet/samples/tree/master/core/getting-started/golden) for this article at the dotnet/samples repository on GitHub.</span></span> <span data-ttu-id="a5685-120">다운로드 지침은 [샘플 및 자습서](../../samples-and-tutorials/index.md#viewing-and-downloading-samples)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a5685-120">For download instructions, see [Samples and Tutorials](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).</span></span>

<span data-ttu-id="a5685-121">Visual Studio Code를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-121">Start Visual Studio Code.</span></span> <span data-ttu-id="a5685-122"><kbd>Ctrl</kbd><kbd>\`</kbd> 키(역따옴표 또는 백틱 문자)를 누르거나 메뉴에서 **보기** > **터미널**을 선택하여 Visual Studio Code에서 포함된 터미널을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-122">Press <kbd>Ctrl</kbd><kbd>\`</kbd> (the backquote or backtick character) or select **View** > **Terminal** from the menu to open an embedded terminal in Visual Studio Code.</span></span> <span data-ttu-id="a5685-123">Visual Studio Code 외부에서 작업하려는 경우 탐색기 **명령 프롬프트에서 열기** 명령(macOS 또는 Linux에서는 **터미널에서 열기**)을 사용하여 외부 셸을 열 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-123">You can still open an external shell with the Explorer **Open in Command Prompt** command (**Open in Terminal** on macOS or Linux) if you prefer to work outside of Visual Studio Code.</span></span>

<span data-ttu-id="a5685-124">하나 이상의 .NET Core 프로젝트에 대한 컨테이너로 사용되는 솔루션 파일을 먼저 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-124">Begin by creating a solution file, which serves as a container for one or more .NET Core projects.</span></span> <span data-ttu-id="a5685-125">터미널에서 [`dotnet new`](../tools/dotnet-new.md) 명령을 실행하여 *golden*이라는 새 폴더에 새 솔루션 *golden.sln*을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-125">In the terminal, run the [`dotnet new`](../tools/dotnet-new.md) command to create a new solution *golden.sln* inside a new folder named *golden*:</span></span>

```dotnetcli
dotnet new sln -o golden
```

<span data-ttu-id="a5685-126">새 *golden* 폴더로 이동하고 다음 명령을 실행하여 *library* 폴더에 두 파일 *library.csproj* 및 *Class1.cs*를 생성하는 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-126">Navigate to the new *golden* folder and execute the following command to create a library project, which produces two files,*library.csproj* and *Class1.cs*, in the *library* folder:</span></span>

```dotnetcli
dotnet new classlib -o library
```

<span data-ttu-id="a5685-127">[`dotnet sln`](../tools/dotnet-sln.md) 명령을 실행하여 새로 만든 *library.csproj* 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-127">Execute the [`dotnet sln`](../tools/dotnet-sln.md) command to add the newly created *library.csproj* project to the solution:</span></span>

```dotnetcli
dotnet sln add library/library.csproj
```

<span data-ttu-id="a5685-128">*library.csproj* 파일에는 다음 정보가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-128">The *library.csproj* file contains the following information:</span></span>

```xml
<Project Sdk="Microsoft.NET.Sdk">

  <PropertyGroup>
    <TargetFramework>netstandard2.0</TargetFramework>
  </PropertyGroup>

</Project>
```

<span data-ttu-id="a5685-129">라이브러리 메서드는 JSON 형식으로 개체를 직렬화 및 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-129">Our library methods serialize and deserialize objects in JSON format.</span></span> <span data-ttu-id="a5685-130">JSON serialization 및 deserialization을 지원하려면 `Newtonsoft.Json` NuGet 패키지에 대한 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-130">To support JSON serialization and deserialization, add a reference to the `Newtonsoft.Json` NuGet package.</span></span> <span data-ttu-id="a5685-131">`dotnet add` 명령은 프로젝트에 새 항목을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-131">The `dotnet add` command adds new items to a project.</span></span> <span data-ttu-id="a5685-132">NuGet 패키지에 대한 참조를 추가하려면 [`dotnet add package`](../tools/dotnet-add-package.md) 명령을 사용하고 패키지 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-132">To add a reference to a NuGet package, use the [`dotnet add package`](../tools/dotnet-add-package.md) command and specify the name of the package:</span></span>

```dotnetcli
dotnet add library package Newtonsoft.Json
```

<span data-ttu-id="a5685-133">그러면 `Newtonsoft.Json` 및 해당 종속성이 라이브러리 프로젝트에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-133">This adds `Newtonsoft.Json` and its dependencies to the library project.</span></span> <span data-ttu-id="a5685-134">또는 *library.csproj* 파일을 수동으로 편집하고 다음 노드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-134">Alternatively, manually edit the *library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <PackageReference Include="Newtonsoft.Json" Version="12.0.2" />
</ItemGroup>
```

<span data-ttu-id="a5685-135">종속성을 복원하고 *library* 내에 *obj* 폴더를 만드는 [`dotnet restore`](../tools/dotnet-restore.md)([참고 참조](#dotnet-restore-note))를 실행합니다. 이 폴더 안에는 *project.assets.json* 파일을 비롯한 세 개의 파일이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-135">Execute [`dotnet restore`](../tools/dotnet-restore.md), ([see note](#dotnet-restore-note)) which restores dependencies and creates an *obj* folder inside *library* with three files in it, including a *project.assets.json* file:</span></span>

```dotnetcli
dotnet restore
```

<span data-ttu-id="a5685-136">*library* 폴더에서 *Class1.cs* 파일의 이름을 *Thing.cs*로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-136">In the *library* folder, rename the file *Class1.cs* to *Thing.cs*.</span></span> <span data-ttu-id="a5685-137">코드를 다음으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-137">Replace the code with the following:</span></span>

```csharp
using static Newtonsoft.Json.JsonConvert;

namespace Library
{
    public class Thing
    {
        public int Get(int left, int right) =>
            DeserializeObject<int>($"{left + right}");
    }
}
```

<span data-ttu-id="a5685-138">`Thing` 클래스에는 공용 메서드 `Get`이 포함되어 있습니다. 이 메서드는 두 숫자의 합계를 반환하지만, 이 작업을 위해 합계를 문자열로 변환한 다음 정수로 역직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-138">The `Thing` class contains one public method, `Get`, which returns the sum of two numbers but does so by converting the sum into a string and then deserializing it into an integer.</span></span> <span data-ttu-id="a5685-139">여기에는 [`using static` 지시문](../../csharp/language-reference/keywords/using-static.md), [식 본문 멤버](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), [문자열 보간](../../csharp/language-reference/tokens/interpolated.md) 등 많은 최신 C# 기능이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-139">This makes use of a number of modern C# features, such as [`using static` directives](../../csharp/language-reference/keywords/using-static.md), [expression-bodied members](../../csharp/whats-new/csharp-7.md#more-expression-bodied-members), and [string interpolation](../../csharp/language-reference/tokens/interpolated.md).</span></span>

<span data-ttu-id="a5685-140">[`dotnet build`](../tools/dotnet-build.md) 명령을 사용하여 라이브러리를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-140">Build the library with the [`dotnet build`](../tools/dotnet-build.md) command.</span></span> <span data-ttu-id="a5685-141">그러면 *golden/library/bin/Debug/netstandard1.4* 아래에 *library.dll* 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-141">This produces a *library.dll* file under *golden/library/bin/Debug/netstandard1.4*:</span></span>

```dotnetcli
dotnet build
```

## <a name="create-the-test-project"></a><span data-ttu-id="a5685-142">테스트 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="a5685-142">Create the test project</span></span>

<span data-ttu-id="a5685-143">라이브러리에 대한 테스트 프로젝트를 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-143">Build a test project for the library.</span></span> <span data-ttu-id="a5685-144">*golden* 폴더에서 새 테스트 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-144">From the *golden* folder, create a new test project:</span></span>

```dotnetcli
dotnet new xunit -o test-library
```

<span data-ttu-id="a5685-145">테스트 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-145">Add the test project to the solution:</span></span>

```dotnetcli
dotnet sln add test-library/test-library.csproj
```

<span data-ttu-id="a5685-146">컴파일러가 라이브러리 프로젝트를 찾아서 사용할 수 있도록 이전 섹션에서 만든 라이브러리에 대한 프로젝트 참조를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-146">Add a project reference the library you created in the previous section so that the compiler can find and use the library project.</span></span> <span data-ttu-id="a5685-147">[`dotnet add reference`](../tools/dotnet-add-reference.md) 명령을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-147">Use the [`dotnet add reference`](../tools/dotnet-add-reference.md) command:</span></span>

```dotnetcli
dotnet add test-library/test-library.csproj reference library/library.csproj
```

<span data-ttu-id="a5685-148">또는 *test-library.csproj* 파일을 수동으로 편집하고 다음 노드를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-148">Alternatively, manually edit the *test-library.csproj* file and add the following node:</span></span>

```xml
<ItemGroup>
  <ProjectReference Include="..\library\library.csproj" />
</ItemGroup>
```

<span data-ttu-id="a5685-149">이제 종속성이 제대로 구성되었으므로 라이브러리에 대한 테스트를 만들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-149">Now that the dependencies have been properly configured, create the tests for your library.</span></span> <span data-ttu-id="a5685-150">*UnitTest1.cs*를 열고 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-150">Open *UnitTest1.cs* and replace its contents with the following code:</span></span>

```csharp
using Library;
using Xunit;

namespace TestApp
{
    public class LibraryTests
    {
        [Fact]
        public void TestThing()
        {
            Assert.NotEqual(42, new Thing().Get(19, 23));
        }
    }
}
```

<span data-ttu-id="a5685-151">단위 테스트를 처음 만들 때는 값 42가 19+23(또는 42)과 같지 않다고 어설션하며(`Assert.NotEqual`) 이는 실패하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-151">Note that you assert the value 42 is not equal to 19+23 (or 42) when you first create the unit test (`Assert.NotEqual`), which will fail.</span></span> <span data-ttu-id="a5685-152">단위 테스트 빌드 시 중요한 단계는 테스트 논리를 확인하기 위해 처음에 한 번 실패하는 테스트를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-152">An important step in building unit tests is to create the test to fail once first to confirm its logic.</span></span>

<span data-ttu-id="a5685-153">*golden* 폴더에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-153">From the *golden* folder, execute the following commands:</span></span>

```dotnetcli
dotnet restore
dotnet test test-library/test-library.csproj
```

<span data-ttu-id="a5685-154">이러한 명령은 모든 프로젝트를 재귀적으로 찾아 종속성을 복원하고 빌드한 다음 xUnit Test Runner를 활성화하여 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-154">These commands will recursively find all projects to restore dependencies, build them, and activate the xUnit test runner to run the tests.</span></span> <span data-ttu-id="a5685-155">예상대로 단일 테스트가 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-155">The single test fails, as you expect.</span></span>

<span data-ttu-id="a5685-156">*UnitTest1.cs* 파일을 편집하고 어설션을 `Assert.NotEqual`에서 `Assert.Equal`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-156">Edit the *UnitTest1.cs* file and change the assertion from `Assert.NotEqual` to `Assert.Equal`.</span></span> <span data-ttu-id="a5685-157">*golden* 폴더에서 다음 명령을 실행하여 테스트를 다시 실행합니다. 이번에는 테스트를 통과합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-157">Execute the following command from the *golden* folder to re-run the test, which passes this time:</span></span>

```dotnetcli
dotnet test test-library/test-library.csproj
```

## <a name="create-the-console-app"></a><span data-ttu-id="a5685-158">콘솔 앱 만들기</span><span class="sxs-lookup"><span data-stu-id="a5685-158">Create the console app</span></span>

<span data-ttu-id="a5685-159">다음 단계에 따라 만든 콘솔 앱은 이전에 만든 라이브러리 프로젝트에 대한 종속성을 가지며, 실행 시 해당 라이브러리 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-159">The console app you create over the following steps takes a dependency on the library project you created earlier and calls its library method when it runs.</span></span> <span data-ttu-id="a5685-160">이 개발 패턴을 사용하면 여러 프로젝트에 재사용 가능한 라이브러리를 만드는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-160">Using this pattern of development, you see how to create reusable libraries for multiple projects.</span></span>

<span data-ttu-id="a5685-161">*golden* 폴더에서 새 콘솔 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-161">Create a new console application from the *golden* folder:</span></span>

```dotnetcli
dotnet new console -o app
```

<span data-ttu-id="a5685-162">콘솔 앱 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-162">Add the console app project to the solution:</span></span>

```dotnetcli
dotnet sln add app/app.csproj
```

<span data-ttu-id="a5685-163">`dotnet add reference` 명령을 실행하여 라이브러리에 대한 종속성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-163">Create the dependency on the library by running the `dotnet add reference` command:</span></span>

```dotnetcli
dotnet add app/app.csproj reference library/library.csproj
```

<span data-ttu-id="a5685-164">`dotnet restore`([참고 참조](#dotnet-restore-note))를 실행하여 솔루션에 있는 세 프로젝트의 종속성을 복원합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-164">Run `dotnet restore` ([see note](#dotnet-restore-note)) to restore the dependencies of the three projects in the solution.</span></span> <span data-ttu-id="a5685-165">*Program.cs*를 열고 `Main` 메서드의 내용을 다음 줄로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-165">Open *Program.cs* and replace the contents of the `Main` method with the following line:</span></span>

```csharp
WriteLine($"The answer is {new Thing().Get(19, 23)}");
```

<span data-ttu-id="a5685-166">*Program.cs* 파일의 맨 위에 두 개의 `using` 지시문을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-166">Add two `using` directives to the top of the *Program.cs* file:</span></span>

```csharp
using static System.Console;
using Library;
```

<span data-ttu-id="a5685-167">다음 `dotnet run` 명령을 실행하여 실행 파일을 실행합니다. 여기서 `dotnet run`에 대한 `-p` 옵션은 주 애플리케이션에 대한 프로젝트를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-167">Execute the following `dotnet run` command to run the executable, where the `-p` option to `dotnet run` specifies the project for the main application.</span></span> <span data-ttu-id="a5685-168">앱이 "The answer is 42" 문자열을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-168">The app produces the string "The answer is 42".</span></span>

```dotnetcli
dotnet run -p app/app.csproj
```

## <a name="debug-the-application"></a><span data-ttu-id="a5685-169">애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="a5685-169">Debug the application</span></span>

<span data-ttu-id="a5685-170">`Main` 메서드의 `WriteLine` 문에 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-170">Set a breakpoint at the `WriteLine` statement in the `Main` method.</span></span> <span data-ttu-id="a5685-171">이렇게 하려면  줄에 커서를 놓고 <kbd>Fn</kbd>+<kbd>F9</kbd> 키를 누르거나 중단점을 설정할 `WriteLine` 줄의 왼쪽 여백에서 마우스를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-171">Do this by either pressing the <kbd>Fn</kbd>+<kbd>F9</kbd> key when the cursor is over the `WriteLine` line or by clicking the mouse in the left margin on the line where you want to set the breakpoint.</span></span> <span data-ttu-id="a5685-172">코드 줄 옆의 여백에 빨간색 원이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-172">A red circle will appear in the margin next to the line of code.</span></span> <span data-ttu-id="a5685-173">중단점에 도달하면 중단점 줄이 실행되기 *전에* 코드 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-173">When the breakpoint is reached, code execution will stop *before* the breakpoint line is executed.</span></span>

<span data-ttu-id="a5685-174">Visual Studio Code 도구 모음에서 디버그 아이콘을 선택하거나, 메뉴 모음에서 **보기** > **디버그**를 선택하거나, 바로 가기 키 <kbd>&#8679;</kbd><kbd>&#8984;</kbd><kbd>D</kbd>를 사용하여 디버거 탭을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-174">Open the debugger tab by selecting the Debug icon in the Visual Studio Code toolbar, selecting **View** > **Debug** from the menu bar, or using the keyboard shortcut <kbd>&#8679;</kbd><kbd>&#8984;</kbd><kbd>D</kbd>:</span></span>

![Visual Studio Code 디버거](./media/using-on-macos/visual-studio-code-debugger.png)

<span data-ttu-id="a5685-176">디버거에서 애플리케이션을 시작하려면 재생 단추를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-176">Press the Play button to start the application under the debugger.</span></span> <span data-ttu-id="a5685-177">이 프로젝트에서 테스트 프로젝트와 애플리케이션을 모두 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-177">You've created both a test project and an application in this project.</span></span> <span data-ttu-id="a5685-178">디버거에서 어떤 프로젝트를 시작할 것인지 묻습니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-178">The debugger asks which project you want to start.</span></span> <span data-ttu-id="a5685-179">“앱” 프로젝트를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-179">Select the "app" project.</span></span> <span data-ttu-id="a5685-180">앱이 실행을 시작하고 중단점까지 실행되며, 여기서 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-180">The app begins execution and runs to the breakpoint, where it stops.</span></span> <span data-ttu-id="a5685-181">`Get` 메서드를 단계별로 실행하며 올바른 인수를 전달했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-181">Step into the `Get` method and make sure that you have passed in the correct arguments.</span></span> <span data-ttu-id="a5685-182">응답이 42인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="a5685-182">Confirm that the answer is 42.</span></span>

<a name="dotnet-restore-note"></a>
[!INCLUDE[DotNet Restore Note](~/includes/dotnet-restore-note.md)]
