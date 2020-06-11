---
title: Visual Studio Code에서 .NET Standard 클래스 라이브러리 만들기
description: Visual Studio Code를 사용하여 .NET Standard 클래스 라이브러리를 만드는 방법을 알아봅니다.
ms.date: 05/29/2020
ms.openlocfilehash: 5720ac374d50ef27a07d463e57af1bd95a352d83
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84446954"
---
# <a name="tutorial-create-a-net-standard-library-in-visual-studio-code"></a><span data-ttu-id="0300b-103">자습서: Visual Studio Code에서 .NET Standard 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="0300b-103">Tutorial: Create a .NET Standard library in Visual Studio Code</span></span>

<span data-ttu-id="0300b-104">*클래스 라이브러리*는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-104">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="0300b-105">.NET Standard 2.0을 대상으로 하는 클래스 라이브러리는 .NET Standard의 해당 버전을 지원하는 모든 .NET 구현에서 라이브러리를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-105">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="0300b-106">클래스 라이브러리를 마칠 때 NuGet 패키지로 배포할지 또는 하나 이상의 애플리케이션과 함께 번들 구성 요소로 포함할지 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-106">When you finish your class library, you can decide whether you want to distribute it as a NuGet package or include it as a bundled component with one or more applications.</span></span>

> [!NOTE]
> <span data-ttu-id="0300b-107">.NET Standard 버전 및 지원되는 플랫폼 목록은 [.NET Standard](../../standard/net-standard.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0300b-107">For a list of .NET Standard versions and the platforms they support, see [.NET Standard](../../standard/net-standard.md).</span></span>

<span data-ttu-id="0300b-108">이 자습서에서는 단일 문자열 처리 메서드를 포함하는 간단한 유틸리티 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-108">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="0300b-109"><xref:System.String> 클래스의 멤버인 것처럼 호출할 수 있도록 [확장 메서드](../../csharp/programming-guide/classes-and-structs/extension-methods.md)로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-109">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="0300b-110">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="0300b-110">Prerequisites</span></span>

1. <span data-ttu-id="0300b-111">[C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)이 설치된 [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="0300b-111">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="0300b-112">Visual Studio Code에 확장을 설치하는 방법에 대한 자세한 내용은 [VS Code 확장 Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0300b-112">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="0300b-113">[.NET Core 3.1 SDK 이상](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="0300b-113">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="0300b-114">솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="0300b-114">Create a solution</span></span>

<span data-ttu-id="0300b-115">먼저 클래스 라이브러리 프로젝트를 배치할 빈 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-115">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="0300b-116">솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-116">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="0300b-117">동일한 솔루션에 관련 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-117">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="0300b-118">Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-118">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="0300b-119">주 메뉴에서 **파일** > **폴더 열기**/**열기...** 를 선택하고, *ClassLibraryProjects* 폴더를 만든 다음, **폴더 선택**/**열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-119">Select **File** > **Open Folder**/**Open...** from the main menu, create a *ClassLibraryProjects* folder, and click **Select Folder**/**Open**.</span></span>

1. <span data-ttu-id="0300b-120">주 메뉴에서 **보기** > **터미널**을 선택하여 Visual Studio Code에서 **터미널**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-120">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="0300b-121">*ClassLibraryProjects* 폴더에서 명령 프롬프트와 함께 **터미널**이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-121">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="0300b-122">**터미널**에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-122">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="0300b-123">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-123">The terminal output looks like the following example:</span></span>

   ```
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="0300b-124">클래스 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="0300b-124">Create a class library project</span></span>

<span data-ttu-id="0300b-125">"StringLibrary"라는 새로운 .NET Standard 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-125">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="0300b-126">터미널에서 다음 명령을 실행하여 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-126">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="0300b-127">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-127">The terminal output looks like the following example:</span></span>

   ```
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restore completed in 328.13 ms for C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="0300b-128">다음 명령을 실행하여 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-128">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="0300b-129">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-129">The terminal output looks like the following example:</span></span>

   ```
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="0300b-130">라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-130">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="0300b-131">**Explorer**에서 *StringLibrary/StringLibrary.csproj*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-131">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="0300b-132">`TargetFramework` 요소는 프로젝트가 .NET Standard 2.0을 대상으로 함을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-132">The `TargetFramework` element shows that the project targets .NET Standard 2.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="0300b-133">*Class1.cs*를 열고 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-133">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="0300b-134">클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-134">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="0300b-135">이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-135">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="0300b-136">유니코드 표준은 대문자와 소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-136">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="0300b-137"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-137">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="0300b-138">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-138">Save the file.</span></span>

1. <span data-ttu-id="0300b-139">다음 명령을 실행하여 솔루션을 빌드하고 프로젝트가 오류 없이 컴파일되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-139">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="0300b-140">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-140">The terminal output looks like the following example:</span></span>

   ```
   Microsoft (R) Build Engine version 16.6.0 for .NET Core
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     You are using a preview version of .NET Core. See: https://aka.ms/dotnet-core-preview
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="0300b-141">솔루션에 콘솔 앱 추가</span><span class="sxs-lookup"><span data-stu-id="0300b-141">Add a console app to the solution</span></span>

<span data-ttu-id="0300b-142">클래스 라이브러리를 사용하는 콘솔 애플리케이션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-142">Add a console application that uses the class library.</span></span> <span data-ttu-id="0300b-143">이 앱은 사용자에게 문자열을 입력하라는 메시지를 표시하고 문자열이 대문자로 시작하는지 여부를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-143">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="0300b-144">터미널에서 다음 명령을 실행하여 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-144">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="0300b-145">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-145">The terminal output looks like the following example:</span></span>

   ```
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restore completed in 210.78 ms for C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj.
   Restore succeeded.
   ```

1. <span data-ttu-id="0300b-146">다음 명령을 실행하여 솔루션에 콘솔 앱 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-146">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="0300b-147">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-147">The terminal output looks like the following example:</span></span>

   ```
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="0300b-148">처음에는 새 콘솔 앱 프로젝트가 클래스 라이브러리에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-148">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="0300b-149">클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 다음 명령을 실행하여 클래스 라이브러리 프로젝트에 대한 프로젝트 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-149">To allow it to call methods in the class library, create a project reference to the class library project by running the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/Showcase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="0300b-150">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-150">The terminal output looks like the following example:</span></span>

   ```
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

1. <span data-ttu-id="0300b-151">*ShowCase/Program.cs*를 열고 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-151">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="0300b-152">코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-152">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="0300b-153">25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-153">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="0300b-154">프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-154">The program prompts the user to enter a string.</span></span> <span data-ttu-id="0300b-155">문자열이 대문자로 시작하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-155">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="0300b-156">사용자가 문자열을 입력하지 않고 Enter 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-156">If the user presses the Enter key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="0300b-157">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-157">Save your changes.</span></span>

1. <span data-ttu-id="0300b-158">프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-158">Run the program.</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="0300b-159">문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프로그램을 사용해 본 다음 <kbd>Enter</kbd> 키를 눌러 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-159">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="0300b-160">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-160">The terminal output looks like the following example:</span></span>

   ```
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   A string that starts with a lowercase letter
   Input: A string that starts with a lowercase letter
   Begins with uppercase? : Yes
   ```

## <a name="additional-resources"></a><span data-ttu-id="0300b-161">추가 자료</span><span class="sxs-lookup"><span data-stu-id="0300b-161">Additional resources</span></span>

* [<span data-ttu-id="0300b-162">.NET Core CLI를 사용하여 라이브러리 개발</span><span class="sxs-lookup"><span data-stu-id="0300b-162">Develop libraries with the .NET Core CLI</span></span>](libraries.md)

## <a name="next-steps"></a><span data-ttu-id="0300b-163">다음 단계</span><span class="sxs-lookup"><span data-stu-id="0300b-163">Next steps</span></span>

<span data-ttu-id="0300b-164">이 자습서에서는 솔루션을 만들고, 라이브러리 프로젝트를 추가하고, 라이브러리를 사용하는 콘솔 앱 프로젝트를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-164">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="0300b-165">다음 자습서에서는 솔루션에 단위 테스트 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0300b-165">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="0300b-166">Visual Studio Code에서 .NET Core를 사용하여 .NET Standard 라이브러리 테스트</span><span class="sxs-lookup"><span data-stu-id="0300b-166">Test a .NET Standard library with .NET Core in Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
