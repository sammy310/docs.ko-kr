---
title: Visual Studio Code로 .NET Standard 클래스 라이브러리 만들기
description: Visual Studio Code를 사용하여 .NET Standard 클래스 라이브러리를 만드는 방법을 알아봅니다.
ms.date: 06/08/2020
ms.openlocfilehash: 966b9b0b48f67809e82d9133c523995cd97b6015
ms.sourcegitcommit: cbacb5d2cebbf044547f6af6e74a9de866800985
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/05/2020
ms.locfileid: "89495514"
---
# <a name="tutorial-create-a-net-standard-library-using-visual-studio-code"></a><span data-ttu-id="6c0e2-103">자습서: Visual Studio Code로 .NET Standard 라이브러리 만들기</span><span class="sxs-lookup"><span data-stu-id="6c0e2-103">Tutorial: Create a .NET Standard library using Visual Studio Code</span></span>

<span data-ttu-id="6c0e2-104">이 자습서에서는 단일 문자열 처리 메서드를 포함하는 간단한 유틸리티 라이브러리를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-104">In this tutorial, you create a simple utility library that contains a single string-handling method.</span></span> <span data-ttu-id="6c0e2-105"><xref:System.String> 클래스의 멤버인 것처럼 호출할 수 있도록 [확장 메서드](../../csharp/programming-guide/classes-and-structs/extension-methods.md)로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-105">You implement it as an [extension method](../../csharp/programming-guide/classes-and-structs/extension-methods.md) so that you can call it as if it were a member of the <xref:System.String> class.</span></span>

<span data-ttu-id="6c0e2-106">*클래스 라이브러리*는 애플리케이션에서 호출되는 형식 및 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-106">A *class library* defines types and methods that are called by an application.</span></span> <span data-ttu-id="6c0e2-107">.NET Standard 2.0을 대상으로 하는 클래스 라이브러리는 .NET Standard의 해당 버전을 지원하는 모든 .NET 구현에서 라이브러리를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-107">A class library that targets .NET Standard 2.0 allows your library to be called by any .NET implementation that supports that version of .NET Standard.</span></span> <span data-ttu-id="6c0e2-108">클래스 라이브러리를 마칠 때 타사 구성 요소 또는 하나 이상의 애플리케이션이 포함된 번들 구성 요소로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-108">When you finish your class library, you can distribute it as a third-party component or as a bundled component with one or more applications.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6c0e2-109">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c0e2-109">Prerequisites</span></span>

1. <span data-ttu-id="6c0e2-110">[C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)이 설치된 [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="6c0e2-110">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="6c0e2-111">Visual Studio Code에 확장을 설치하는 방법에 대한 자세한 내용은 [VS Code 확장 Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-111">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="6c0e2-112">[.NET Core 3.1 SDK 이상](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="6c0e2-112">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-a-solution"></a><span data-ttu-id="6c0e2-113">솔루션 만들기</span><span class="sxs-lookup"><span data-stu-id="6c0e2-113">Create a solution</span></span>

<span data-ttu-id="6c0e2-114">먼저 클래스 라이브러리 프로젝트를 배치할 빈 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-114">Start by creating a blank solution to put the class library project in.</span></span> <span data-ttu-id="6c0e2-115">솔루션은 하나 이상의 프로젝트에 대한 컨테이너로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-115">A solution serves as a container for one or more projects.</span></span> <span data-ttu-id="6c0e2-116">동일한 솔루션에 관련 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-116">You'll add additional, related projects to the same solution.</span></span>

1. <span data-ttu-id="6c0e2-117">Visual Studio Code를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-117">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="6c0e2-118">주 메뉴에서 **파일** > **폴더 열기** (macOS에서는 **열기...** )를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-118">Select **File** > **Open Folder** (**Open...** on macOS) from the main menu</span></span>

1. <span data-ttu-id="6c0e2-119">**폴더 열기** 대화 상자에서 *ClassLibraryProjects* 폴더를 만들고 **폴더 선택**(macOS에서는 **열기**)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-119">In the **Open Folder** dialog, create a *ClassLibraryProjects* folder and click **Select Folder** (**Open** on macOS).</span></span>

1. <span data-ttu-id="6c0e2-120">주 메뉴에서 **보기** > **터미널**을 선택하여 Visual Studio Code에서 **터미널**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-120">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="6c0e2-121">*ClassLibraryProjects* 폴더에서 명령 프롬프트와 함께 **터미널**이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-121">The **Terminal** opens with the command prompt in the *ClassLibraryProjects* folder.</span></span>

1. <span data-ttu-id="6c0e2-122">**터미널**에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-122">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new sln
   ```

   <span data-ttu-id="6c0e2-123">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-123">The terminal output looks like the following example:</span></span>

   ```output
   The template "Solution File" was created successfully.
   ```

## <a name="create-a-class-library-project"></a><span data-ttu-id="6c0e2-124">클래스 라이브러리 프로젝트 만들기</span><span class="sxs-lookup"><span data-stu-id="6c0e2-124">Create a class library project</span></span>

<span data-ttu-id="6c0e2-125">"StringLibrary"라는 새로운 .NET Standard 클래스 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-125">Add a new .NET Standard class library project named "StringLibrary" to the solution.</span></span>

1. <span data-ttu-id="6c0e2-126">터미널에서 다음 명령을 실행하여 라이브러리 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-126">In the terminal, run the following command to create the library project:</span></span>

   ```dotnetcli
   dotnet new classlib -o StringLibrary
   ```

   <span data-ttu-id="6c0e2-127">`-o` 또는 `--output` 명령은 생성된 출력을 저장할 위치를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-127">The `-o` or `--output` command specifies the location to place the generated output.</span></span>

   <span data-ttu-id="6c0e2-128">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-128">The terminal output looks like the following example:</span></span>

   ```output
   The template "Class library" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on StringLibrary\StringLibrary.csproj...
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\StringLibrary\StringLibrary.csproj (in 328 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="6c0e2-129">다음 명령을 실행하여 라이브러리 프로젝트를 솔루션에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-129">Run the following command to add the library project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="6c0e2-130">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-130">The terminal output looks like the following example:</span></span>

   ```output
   Project `StringLibrary\StringLibrary.csproj` added to the solution.
   ```

1. <span data-ttu-id="6c0e2-131">라이브러리에 올바른 버전의 .NET Standard가 대상으로 지정되었는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-131">Check to make sure that the library targets the correct version of .NET Standard.</span></span> <span data-ttu-id="6c0e2-132">**Explorer**에서 *StringLibrary/StringLibrary.csproj*를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-132">In **Explorer**, open *StringLibrary/StringLibrary.csproj*.</span></span>

   <span data-ttu-id="6c0e2-133">`TargetFramework` 요소는 프로젝트가 .NET Standard 2.0을 대상으로 함을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-133">The `TargetFramework` element shows that the project targets .NET Standard 2.0.</span></span>

   ```xml
   <Project Sdk="Microsoft.NET.Sdk">

     <PropertyGroup>
       <TargetFramework>netstandard2.0</TargetFramework>
     </PropertyGroup>

   </Project>
   ```

1. <span data-ttu-id="6c0e2-134">*Class1.cs*를 열고 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-134">Open *Class1.cs* and replace the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/StringLibrary/Class1.cs":::

   <span data-ttu-id="6c0e2-135">클래스 라이브러리 `UtilityLibraries.StringLibrary`에는 `StartsWithUpper`라는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-135">The class library, `UtilityLibraries.StringLibrary`, contains a method named `StartsWithUpper`.</span></span> <span data-ttu-id="6c0e2-136">이 메서드는 현재 문자열 인스턴스가 대문자로 시작하는지 여부를 나타내는 <xref:System.Boolean> 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-136">This method returns a <xref:System.Boolean> value that indicates whether the current string instance begins with an uppercase character.</span></span> <span data-ttu-id="6c0e2-137">유니코드 표준은 대문자와 소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-137">The Unicode standard distinguishes uppercase characters from lowercase characters.</span></span> <span data-ttu-id="6c0e2-138"><xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> 메서드는 문자가 대문자인 경우 `true`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-138">The <xref:System.Char.IsUpper(System.Char)?displayProperty=nameWithType> method returns `true` if a character is uppercase.</span></span>

1. <span data-ttu-id="6c0e2-139">파일을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-139">Save the file.</span></span>

1. <span data-ttu-id="6c0e2-140">다음 명령을 실행하여 솔루션을 빌드하고 프로젝트가 오류 없이 컴파일되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-140">Run the following command to build the solution and verify that the project compiles without error.</span></span>

   ```dotnetcli
   dotnet build
   ```

   <span data-ttu-id="6c0e2-141">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-141">The terminal output looks like the following example:</span></span>

   ```output
   Microsoft (R) Build Engine version 16.7.0+b89cb5fde for .NET
   Copyright (C) Microsoft Corporation. All rights reserved.
     Determining projects to restore...
     All projects are up-to-date for restore.
     StringLibrary -> C:\Projects\ClassLibraryProjects\StringLibrary\bin\Debug\netstandard2.0\StringLibrary.dll
   Build succeeded.
       0 Warning(s)
       0 Error(s)
   Time Elapsed 00:00:02.78
   ```

## <a name="add-a-console-app-to-the-solution"></a><span data-ttu-id="6c0e2-142">솔루션에 콘솔 앱 추가</span><span class="sxs-lookup"><span data-stu-id="6c0e2-142">Add a console app to the solution</span></span>

<span data-ttu-id="6c0e2-143">클래스 라이브러리를 사용하는 콘솔 애플리케이션을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-143">Add a console application that uses the class library.</span></span> <span data-ttu-id="6c0e2-144">이 앱은 사용자에게 문자열을 입력하라는 메시지를 표시하고 문자열이 대문자로 시작하는지 여부를 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-144">The app will prompt the user to enter a string and report whether the string begins with an uppercase character.</span></span>

1. <span data-ttu-id="6c0e2-145">터미널에서 다음 명령을 실행하여 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-145">In the terminal, run the following command to create the console app project:</span></span>

   ```dotnetcli
   dotnet new console -o ShowCase
   ```

   <span data-ttu-id="6c0e2-146">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-146">The terminal output looks like the following example:</span></span>

   ```output
   The template "Console Application" was created successfully.
   Processing post-creation actions...
   Running 'dotnet restore' on ShowCase\ShowCase.csproj...  
     Determining projects to restore...
     Restored C:\Projects\ClassLibraryProjects\ShowCase\ShowCase.csproj (in 210 ms).
   Restore succeeded.
   ```

1. <span data-ttu-id="6c0e2-147">다음 명령을 실행하여 솔루션에 콘솔 앱 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-147">Run the following command to add the console app project to the solution:</span></span>

   ```dotnetcli
   dotnet sln add ShowCase/ShowCase.csproj
   ```

   <span data-ttu-id="6c0e2-148">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-148">The terminal output looks like the following example:</span></span>

   ```output
   Project `ShowCase\ShowCase.csproj` added to the solution.
   ```

1. <span data-ttu-id="6c0e2-149">*ShowCase/Program.cs*를 열고 모든 코드를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-149">Open *ShowCase/Program.cs* and replace all of the code with the following code.</span></span>

   :::code language="csharp" source="./snippets/library-with-visual-studio/csharp/ShowCase/Program.cs":::

   <span data-ttu-id="6c0e2-150">코드는 `row` 변수를 사용하여 콘솔 창에 기록된 데이터 행 수를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-150">The code uses the `row` variable to maintain a count of the number of rows of data written to the console window.</span></span> <span data-ttu-id="6c0e2-151">25보다 크거나 같으면 코드는 콘솔 창을 지우고 사용자에게 메시지를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-151">Whenever it's greater than or equal to 25, the code clears the console window and displays a message to the user.</span></span>

   <span data-ttu-id="6c0e2-152">프로그램에서 문자열을 입력하라는 메시지를 사용자에게 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-152">The program prompts the user to enter a string.</span></span> <span data-ttu-id="6c0e2-153">문자열이 대문자로 시작하는지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-153">It indicates whether the string starts with an uppercase character.</span></span> <span data-ttu-id="6c0e2-154">사용자가 문자열을 입력하지 않고 <kbd>Enter</kbd> 키를 누르면 애플리케이션이 종료되고 콘솔 창이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-154">If the user presses the <kbd>Enter</kbd> key without entering a string, the application ends, and the console window closes.</span></span>

1. <span data-ttu-id="6c0e2-155">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-155">Save your changes.</span></span>

## <a name="add-a-project-reference"></a><span data-ttu-id="6c0e2-156">프로젝트 참조 추가</span><span class="sxs-lookup"><span data-stu-id="6c0e2-156">Add a project reference</span></span>

<span data-ttu-id="6c0e2-157">처음에는 새 콘솔 앱 프로젝트가 클래스 라이브러리에 액세스할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-157">Initially, the new console app project doesn't have access to the class library.</span></span> <span data-ttu-id="6c0e2-158">클래스 라이브러리의 메서드를 호출할 수 있도록 허용하려면 클래스 라이브러리 프로젝트에 대한 프로젝트 참조를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-158">To allow it to call methods in the class library, create a project reference to the class library project.</span></span>

1. <span data-ttu-id="6c0e2-159">다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-159">Run the following command:</span></span>

   ```dotnetcli
   dotnet add ShowCase/ShowCase.csproj reference StringLibrary/StringLibrary.csproj
   ```

   <span data-ttu-id="6c0e2-160">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-160">The terminal output looks like the following example:</span></span>

   ```output
   Reference `..\StringLibrary\StringLibrary.csproj` added to the project.
   ```

## <a name="run-the-app"></a><span data-ttu-id="6c0e2-161">앱 실행</span><span class="sxs-lookup"><span data-stu-id="6c0e2-161">Run the app</span></span>

1. <span data-ttu-id="6c0e2-162">터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-162">Run the following command in the terminal:</span></span>

   ```dotnetcli
   dotnet run --project ShowCase/ShowCase.csproj
   ```

1. <span data-ttu-id="6c0e2-163">문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프로그램을 사용해 본 다음 <kbd>Enter</kbd> 키를 눌러 끝냅니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-163">Try out the program by entering strings and pressing <kbd>Enter</kbd>, then press <kbd>Enter</kbd> to exit.</span></span>

   <span data-ttu-id="6c0e2-164">터미널 출력은 다음 예제처럼 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-164">The terminal output looks like the following example:</span></span>

   ```output
   Press <Enter> only to exit; otherwise, enter a string and press <Enter>:

   A string that starts with an uppercase letter
   Input: A string that starts with an uppercase letter
   Begins with uppercase? : Yes

   a string that starts with a lowercase letter
   Input: a string that starts with a lowercase letter
   Begins with uppercase? : No
   ```

## <a name="additional-resources"></a><span data-ttu-id="6c0e2-165">추가 자료</span><span class="sxs-lookup"><span data-stu-id="6c0e2-165">Additional resources</span></span>

* [<span data-ttu-id="6c0e2-166">.NET Core CLI를 사용하여 라이브러리 개발</span><span class="sxs-lookup"><span data-stu-id="6c0e2-166">Develop libraries with the .NET Core CLI</span></span>](libraries.md)
* <span data-ttu-id="6c0e2-167">[지원되는 .NET Standard 버전 및 플랫폼](../../standard/net-standard.md)</span><span class="sxs-lookup"><span data-stu-id="6c0e2-167">[.NET Standard versions and the platforms they support](../../standard/net-standard.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c0e2-168">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6c0e2-168">Next steps</span></span>

<span data-ttu-id="6c0e2-169">이 자습서에서는 솔루션을 만들고, 라이브러리 프로젝트를 추가하고, 라이브러리를 사용하는 콘솔 앱 프로젝트를 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-169">In this tutorial, you created a solution, added a library project, and added a console app project that uses the library.</span></span> <span data-ttu-id="6c0e2-170">다음 자습서에서는 솔루션에 단위 테스트 프로젝트를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="6c0e2-170">In the next tutorial, you add a unit test project to the solution.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6c0e2-171">Visual Studio Code에서 .NET Core로 .NET Standard 라이브러리 테스트</span><span class="sxs-lookup"><span data-stu-id="6c0e2-171">Test a .NET Standard library with .NET Core using Visual Studio Code</span></span>](testing-library-with-visual-studio-code.md)
