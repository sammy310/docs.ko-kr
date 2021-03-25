---
title: Visual Studio Code를 사용하여 .NET 콘솔 애플리케이션 만들기
description: Visual Studio Code와 .NET CLI를 사용하여 .NET 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
ms.date: 11/17/2020
ms.openlocfilehash: 51e5a897985af7576de03659efdd8520cb8e58e6
ms.sourcegitcommit: 1d3af230ec30d8d061be7a887f6ba38a530c4ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511868"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-code"></a><span data-ttu-id="b9c15-103">자습서: Visual Studio Code를 사용하여 .NET 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="b9c15-103">Tutorial: Create a .NET console application using Visual Studio Code</span></span>

<span data-ttu-id="b9c15-104">이 자습서에서는 Visual Studio Code와 .NET CLI를 사용하여 .NET 콘솔 애플리케이션을 만들고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-104">This tutorial shows how to create and run a .NET console application by using Visual Studio Code and the .NET CLI.</span></span> <span data-ttu-id="b9c15-105">프로젝트 만들기, 컴파일, 실행과 같은 프로젝트 작업은 .NET CLI를 사용하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-105">Project tasks, such as creating, compiling, and running a project are done by using the .NET CLI.</span></span> <span data-ttu-id="b9c15-106">원할 경우, 다른 코드 편집기를 사용하여 이 자습서를 따르고 터미널에서 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-106">You can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b9c15-107">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9c15-107">Prerequisites</span></span>

1. <span data-ttu-id="b9c15-108">[C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)이 설치된 [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="b9c15-108">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="b9c15-109">Visual Studio Code에 확장을 설치하는 방법에 대한 자세한 내용은 [VS Code 확장 Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9c15-109">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="b9c15-110">[.NET 5.0 SDK 이상](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="b9c15-110">The [.NET 5.0 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="b9c15-111">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="b9c15-111">Create the app</span></span>

<span data-ttu-id="b9c15-112">“HelloWorld”라는 .NET 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-112">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="b9c15-113">Visual Studio Code를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-113">Start Visual Studio Code.</span></span>

1. <span data-ttu-id="b9c15-114">주 메뉴에서 **파일** > **폴더 열기**(macOS에서는 **파일** > **열기...** )를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-114">Select **File** > **Open Folder** (**File** > **Open...** on macOS) from the main menu.</span></span>

1. <span data-ttu-id="b9c15-115">**폴더 열기** 대화 상자에서 *HelloWorld* 폴더를 만들고 **폴더 선택**(macOS에서는 **열기**)을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-115">In the **Open Folder** dialog, create a *HelloWorld* folder and click **Select Folder** (**Open** on macOS).</span></span>

   <span data-ttu-id="b9c15-116">기본적으로 폴더 이름은 프로젝트 이름 및 네임스페이스 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-116">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="b9c15-117">프로젝트 네임스페이스가 `HelloWorld`라고 가정하는 코드를 자습서의 뒷부분에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-117">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

1. <span data-ttu-id="b9c15-118">주 메뉴에서 **보기** > **터미널** 을 선택하여 Visual Studio Code에서 **터미널** 을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-118">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

   <span data-ttu-id="b9c15-119">*HelloWorld* 폴더에서 명령 프롬프트와 함께 **터미널** 이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-119">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

1. <span data-ttu-id="b9c15-120">**터미널** 에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-120">In the **Terminal**, enter the following command:</span></span>

   ```dotnetcli
   dotnet new console
   ```

<span data-ttu-id="b9c15-121">템플릿은 간단한 "Hello World" 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-121">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="b9c15-122"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 콘솔 창에 “:::no-loc text="Hello World!":::”를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-122">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display ":::no-loc text="Hello World!":::" in the console window.</span></span>

<span data-ttu-id="b9c15-123">템플릿 코드는 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`으로 `Program` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-123">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

```csharp
using System;

namespace HelloWorld
{
    class Program
    {
        static void Main(string[] args)
        {
            Console.WriteLine("Hello World!");
        }
    }
}
```

<span data-ttu-id="b9c15-124">`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-124">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="b9c15-125">애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 *args* 배열에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-125">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="b9c15-126">앱 실행</span><span class="sxs-lookup"><span data-stu-id="b9c15-126">Run the app</span></span>

<span data-ttu-id="b9c15-127">**터미널** 에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-127">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="b9c15-128">프로그램이 "Hello World!"를 표시하고</span><span class="sxs-lookup"><span data-stu-id="b9c15-128">The program displays "Hello World!"</span></span> <span data-ttu-id="b9c15-129">종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-129">and ends.</span></span>

![dotnet run 명령](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="b9c15-131">앱 향상</span><span class="sxs-lookup"><span data-stu-id="b9c15-131">Enhance the app</span></span>

<span data-ttu-id="b9c15-132">사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-132">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="b9c15-133">*Program.cs* 를 클릭하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-133">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="b9c15-134">Visual Studio Code에서 C# 파일을 처음 열면 [OmniSharp](https://www.omnisharp.net/)에서 편집기가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-134">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Program.cs 파일 열기](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="b9c15-136">Visual Studio Code가 앱을 빌드하고 디버그하기 위해 누락된 자산을 추가하라는 메시지를 표시하면 **예** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-136">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![누락된 자산에 대한 프롬프트](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="b9c15-138">*Program.cs* 에서 `Console.WriteLine`을 호출하는 줄인 `Main` 메서드의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-138">Replace the contents of the `Main` method in *Program.cs*, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="b9c15-139">해당 코드는 콘솔 창에 프롬프트를 표시하고 사용자가 문자열을 입력한 후 <kbd>Enter</kbd> 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-139">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="b9c15-140">이 문자열을 `name`이라는 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-140">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="b9c15-141">또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-141">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="b9c15-142">또한 콘솔 창에 해당 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-142">And it displays these values in the console window.</span></span> <span data-ttu-id="b9c15-143">마지막으로 콘솔 창에 프롬프트를 표시하고 <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> 메서드를 호출하여 사용자 입력을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-143">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="b9c15-144"><xref:System.Environment.NewLine>은 줄 바꿈을 나타내는 플랫폼과 언어에 독립적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-144"><xref:System.Environment.NewLine> is a platform-independent and language-independent way to represent a line break.</span></span> <span data-ttu-id="b9c15-145">대안은 C#의 `\n` 및 Visual Basic의 `vbCrLf`입니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-145">Alternatives are `\n` in C# and `vbCrLf` in Visual Basic.</span></span>

   <span data-ttu-id="b9c15-146">문자열 앞의 달러 기호(`$`)를 사용하면 변수 이름과 같은 식을 문자열의 중괄호 안에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-146">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="b9c15-147">식 값은 식 대신 문자열에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-147">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="b9c15-148">이 구문을 [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-148">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="b9c15-149">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-149">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="b9c15-150">Visual Studio Code에서는 변경 내용을 명시적으로 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-150">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="b9c15-151">Visual Studio와 달리 애플리케이션을 빌드 및 실행할 때 파일 변경 내용이 자동으로 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-151">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="b9c15-152">프로그램을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-152">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="b9c15-153">이름을 입력하고 <kbd>Enter</kbd> 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-153">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="수정된 프로그램 출력이 표시된 터미널 창":::

1. <span data-ttu-id="b9c15-155">아무 키나 눌러 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-155">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b9c15-156">추가 자료</span><span class="sxs-lookup"><span data-stu-id="b9c15-156">Additional resources</span></span>

- [<span data-ttu-id="b9c15-157">Visual Studio Code 설치</span><span class="sxs-lookup"><span data-stu-id="b9c15-157">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a><span data-ttu-id="b9c15-158">다음 단계</span><span class="sxs-lookup"><span data-stu-id="b9c15-158">Next steps</span></span>

<span data-ttu-id="b9c15-159">이 자습서에서는 .NET 콘솔 애플리케이션을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-159">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="b9c15-160">다음 자습서에서는 앱을 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="b9c15-160">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="b9c15-161">Visual Studio Code를 사용하여 .NET 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="b9c15-161">Debug a .NET console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
