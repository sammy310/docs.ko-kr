---
title: Visual Studio Code를 사용하여 .NET Core로 콘솔 애플리케이션 만들기
description: Visual Studio Code와 .NET Core CLI를 사용하여 .NET Core 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
ms.date: 05/22/2020
ms.openlocfilehash: 673c4a639a2cab26261b7cdafd5d8e20acfafb94
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201699"
---
# <a name="tutorial-create-a-console-application-with-net-core-using-visual-studio-code"></a><span data-ttu-id="bb2f2-103">자습서: Visual Studio Code를 사용하여 .NET Core로 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="bb2f2-103">Tutorial: Create a console application with .NET Core using Visual Studio Code</span></span>

<span data-ttu-id="bb2f2-104">이 자습서에서는 Visual Studio Code와 .NET Core CLI를 사용하여 .NET Core 콘솔 애플리케이션을 만들고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-104">This tutorial shows how to create and run a .NET Core console application by using Visual Studio Code and the .NET Core CLI.</span></span> <span data-ttu-id="bb2f2-105">프로젝트 만들기, 컴파일, 실행과 같은 프로젝트 작업은 CLI를 사용하여 수행되므로 원하는 경우 다른 코드 편집기로 이 자습서를 수행하고 터미널에서 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-105">Project tasks, such as creating, compiling, and running a project are done by using the CLI, so you can follow this tutorial with a different code editor and run commands in a terminal if you prefer.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bb2f2-106">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bb2f2-106">Prerequisites</span></span>

1. <span data-ttu-id="bb2f2-107">[C# 확장](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp)이 설치된 [Visual Studio Code](https://code.visualstudio.com/).</span><span class="sxs-lookup"><span data-stu-id="bb2f2-107">[Visual Studio Code](https://code.visualstudio.com/) with the [C# extension](https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp) installed.</span></span> <span data-ttu-id="bb2f2-108">Visual Studio Code에 확장을 설치하는 방법에 대한 자세한 내용은 [VS Code 확장 Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-108">For information about how to install extensions on Visual Studio Code, see [VS Code Extension Marketplace](https://code.visualstudio.com/docs/editor/extension-gallery).</span></span>
2. <span data-ttu-id="bb2f2-109">[.NET Core 3.1 SDK 이상](https://dotnet.microsoft.com/download)</span><span class="sxs-lookup"><span data-stu-id="bb2f2-109">The [.NET Core 3.1 SDK or later](https://dotnet.microsoft.com/download)</span></span>

## <a name="create-the-app"></a><span data-ttu-id="bb2f2-110">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="bb2f2-110">Create the app</span></span>

1. <span data-ttu-id="bb2f2-111">Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-111">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="bb2f2-112">프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-112">Create a project.</span></span>

   1. <span data-ttu-id="bb2f2-113">주 메뉴에서 **파일** > **폴더 열기**/**열기...** 를 선택하고, *HelloWorld* 폴더를 만든 다음 **폴더 선택**/**열기**를 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-113">Select **File** > **Open Folder**/**Open...** from the main menu, create a *HelloWorld* folder, and click **Select Folder**/**Open**.</span></span>

      <span data-ttu-id="bb2f2-114">기본적으로 폴더 이름은 프로젝트 이름 및 네임스페이스 이름이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-114">The folder name becomes the project name and the namespace name by default.</span></span> <span data-ttu-id="bb2f2-115">프로젝트 네임스페이스가 `HelloWorld`라고 가정하는 코드를 자습서의 뒷부분에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-115">You'll add code later in the tutorial that assumes the project namespace is `HelloWorld`.</span></span>

   1. <span data-ttu-id="bb2f2-116">주 메뉴에서 **보기** > **터미널**을 선택하여 Visual Studio Code에서 **터미널**을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-116">Open the **Terminal** in Visual Studio Code by selecting **View** > **Terminal** from the main menu.</span></span>

      <span data-ttu-id="bb2f2-117">*HelloWorld* 폴더에서 명령 프롬프트와 함께 **터미널**이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-117">The **Terminal** opens with the command prompt in the *HelloWorld* folder.</span></span>

   1. <span data-ttu-id="bb2f2-118">**터미널**에서 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-118">In the **Terminal**, enter the following command:</span></span>

      ```dotnetcli
      dotnet new console
      ```

<span data-ttu-id="bb2f2-119">.NET Core용 콘솔 애플리케이션 템플릿은 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`으로 `Program` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-119">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="bb2f2-120">*Program.cs* 파일에는 다음 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-120">The *Program.cs* file has the following code:</span></span>

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

<span data-ttu-id="bb2f2-121">`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-121">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="bb2f2-122">애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 *args* 배열에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-122">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="bb2f2-123">템플릿은 <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 "Hello World!"를 표시하는 간단한 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-123">The template creates a simple application that calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="bb2f2-124">콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-124">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="bb2f2-125">앱 실행</span><span class="sxs-lookup"><span data-stu-id="bb2f2-125">Run the app</span></span>

<span data-ttu-id="bb2f2-126">**터미널**에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-126">Run the following command in the **Terminal**:</span></span>

```dotnetcli
dotnet run
```

<span data-ttu-id="bb2f2-127">프로그램이 "Hello World!"를 표시하고</span><span class="sxs-lookup"><span data-stu-id="bb2f2-127">The program displays "Hello World!"</span></span> <span data-ttu-id="bb2f2-128">종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-128">and ends.</span></span>

![dotnet run 명령](media/with-visual-studio-code/dotnet-run-command.png)

## <a name="enhance-the-app"></a><span data-ttu-id="bb2f2-130">앱 향상</span><span class="sxs-lookup"><span data-stu-id="bb2f2-130">Enhance the app</span></span>

<span data-ttu-id="bb2f2-131">사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-131">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="bb2f2-132">*Program.cs*를 클릭하여 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-132">Open *Program.cs* by clicking on it.</span></span>

   <span data-ttu-id="bb2f2-133">Visual Studio Code에서 C# 파일을 처음 열면 [OmniSharp](https://www.omnisharp.net/)에서 편집기가 로드됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-133">The first time you open a C# file in Visual Studio Code, [OmniSharp](https://www.omnisharp.net/) loads in the editor.</span></span>

   ![Program.cs 파일 열기](media/with-visual-studio-code/open-program-cs.png)

1. <span data-ttu-id="bb2f2-135">Visual Studio Code가 앱을 빌드하고 디버그하기 위해 누락된 자산을 추가하라는 메시지를 표시하면 **예**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-135">Select **Yes** when Visual Studio Code prompts you to add the missing assets to build and debug your app.</span></span>

   ![누락된 자산에 대한 프롬프트](media/with-visual-studio-code/missing-assets.png)

1. <span data-ttu-id="bb2f2-137">현재는 `Console.WriteLine`을 호출하는 줄에 불과한 *Program.cs*의 `Main` 메서드 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-137">Replace the contents of the `Main` method in *Program.cs*, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   <span data-ttu-id="bb2f2-138">이 코드는 "What is your name?"을</span><span class="sxs-lookup"><span data-stu-id="bb2f2-138">This code displays "What is your name?"</span></span> <span data-ttu-id="bb2f2-139">콘솔 창에 표시하고 사용자가 문자열을 입력한 후 **Enter** 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-139">in the console window and waits until the user enters a string followed by the **Enter** key.</span></span> <span data-ttu-id="bb2f2-140">이 문자열을 `name`이라는 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-140">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="bb2f2-141">또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-141">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="bb2f2-142">마지막으로 콘솔 창에 이러한 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-142">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="bb2f2-143">`\n`은 줄 바꿈 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-143">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="bb2f2-144">문자열 앞의 달러 기호(`$`)를 사용하면 변수 이름과 같은 식을 문자열의 중괄호 안에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-144">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="bb2f2-145">식 값은 식 대신 문자열에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-145">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="bb2f2-146">이 구문을 [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-146">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="bb2f2-147">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-147">Save your changes.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="bb2f2-148">Visual Studio Code에서는 변경 내용을 명시적으로 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-148">In Visual Studio Code, you have to explicitly save changes.</span></span> <span data-ttu-id="bb2f2-149">Visual Studio와 달리 애플리케이션을 빌드 및 실행할 때 파일 변경 내용이 자동으로 저장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-149">Unlike Visual Studio, file changes are not automatically saved when you build and run an app.</span></span>

1. <span data-ttu-id="bb2f2-150">프로그램을 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-150">Run the program again:</span></span>

   ```dotnetcli
   dotnet run
   ```

1. <span data-ttu-id="bb2f2-151">이름을 입력하고 **Enter** 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-151">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/run-modified-program.png" alt-text="수정된 프로그램 출력이 표시된 터미널 창":::

1. <span data-ttu-id="bb2f2-153">아무 키나 눌러 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-153">Press any key to exit the program.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="bb2f2-154">추가 자료</span><span class="sxs-lookup"><span data-stu-id="bb2f2-154">Additional resources</span></span>

- [<span data-ttu-id="bb2f2-155">Visual Studio Code 설치</span><span class="sxs-lookup"><span data-stu-id="bb2f2-155">Setting up Visual Studio Code</span></span>](https://code.visualstudio.com/docs/setup/setup-overview)

## <a name="next-steps"></a><span data-ttu-id="bb2f2-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bb2f2-156">Next steps</span></span>

<span data-ttu-id="bb2f2-157">이 자습서에서는 .NET Core 애플리케이션을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="bb2f2-158">다음 자습서에서는 앱을 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="bb2f2-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bb2f2-159">Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="bb2f2-159">Debug a .NET Core console application using Visual Studio Code</span></span>](debugging-with-visual-studio-code.md)
