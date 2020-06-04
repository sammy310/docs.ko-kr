---
title: Visual Studio에서 .NET Core를 사용하여 콘솔 애플리케이션 만들기
description: Visual Studio를 사용하여 C# 또는 Visual Basic으로 .NET Core 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
author: BillWagner
ms.author: wiwagn
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 9c3456cd8c940e53e8a70c1d3a7c3b09de77c21d
ms.sourcegitcommit: 71b8f5a2108a0f1a4ef1d8d75c5b3e129ec5ca1e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2020
ms.locfileid: "84201591"
---
# <a name="tutorial-create-a-net-core-console-application-in-visual-studio-2019"></a><span data-ttu-id="1641b-103">자습서: Visual Studio 2019에서 .NET Core 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="1641b-103">Tutorial: Create a .NET Core console application in Visual Studio 2019</span></span>

<span data-ttu-id="1641b-104">이 자습서에서는 Visual Studio 2019에서 .NET Core 콘솔 애플리케이션을 만들고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-104">This tutorial shows how to create and run a .NET Core console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="1641b-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="1641b-105">Prerequisites</span></span>

- <span data-ttu-id="1641b-106">**.NET Core 플랫폼 간 개발** 워크로드가 설치된 [Visual Studio 2019 버전 16.6 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="1641b-106">[Visual Studio 2019 version 16.6 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="1641b-107">이 워크로드를 선택하면 .NET Core 3.1 SDK가 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-107">The .NET Core 3.1 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="1641b-108">자세한 내용은 [.NET Core SDK 설치](../install/sdk.md?pivots=os-windows) 문서의 [Visual Studio를 사용하여 설치](../install/sdk.md?pivots=os-windows#install-with-visual-studio) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1641b-108">For more information, see the [Install with Visual Studio](../install/sdk.md?pivots=os-windows#install-with-visual-studio) section on the [Install the .NET Core SDK](../install/sdk.md?pivots=os-windows) article.</span></span>

## <a name="create-the-app"></a><span data-ttu-id="1641b-109">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="1641b-109">Create the app</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="1641b-110">Visual Studio 2019를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-110">Open Visual Studio 2019.</span></span>

1. <span data-ttu-id="1641b-111">“HelloWorld”라는 새로운 .NET Core 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-111">Create a new .NET Core console app project named "HelloWorld".</span></span>

   1. <span data-ttu-id="1641b-112">시작 페이지에서 **새 프로젝트 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-112">On the start page, choose **Create a new project**.</span></span>

      ![Visual Studio 시작 페이지에서 새 프로젝트 만들기 단추 선택](./media/with-visual-studio/start-window.png)

   1. <span data-ttu-id="1641b-114">**새 프로젝트 만들기** 페이지의 검색 상자에 **console**을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-114">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="1641b-115">다음으로 언어 목록에서 **C#** 또는 **Visual Basic**을 선택한 다음 플랫폼 목록에서 **모든 플랫폼**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-115">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="1641b-116">**콘솔 앱(.NET Core)** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-116">Choose the **Console App (.NET Core)** template, and then choose **Next**.</span></span>

      ![필터가 선택된 새 프로젝트 만들기 창](./media/with-visual-studio/create-new-project.png)

      > [!TIP]
      > <span data-ttu-id="1641b-118">.NET Core 템플릿이 표시되지 않으면 필요한 워크로드가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-118">If you don't see the .NET Core templates, you're probably missing the required workload.</span></span> <span data-ttu-id="1641b-119">**원하는 항목을 찾을 수 없나요?** 메시지에서 **추가 도구 및 기능 설치** 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-119">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="1641b-120">Visual Studio 설치 관리자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-120">The Visual Studio Installer opens.</span></span> <span data-ttu-id="1641b-121">**.NET Core 플랫폼 간 개발** 워크로드가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-121">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

   1. <span data-ttu-id="1641b-122">**새 프로젝트 구성** 페이지에서 **프로젝트 이름** 상자에 **HelloWorld**를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-122">On the **Configure your new project** page,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="1641b-123">그런 다음, **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-123">Then choose **Create**.</span></span>

      ![프로젝트 이름, 위치 및 솔루션 이름 필드를 사용하여 새 프로젝트 창을 구성합니다.](./media/with-visual-studio/configure-new-project.png)

   <span data-ttu-id="1641b-125">.NET Core용 콘솔 애플리케이션 템플릿은 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`으로 `Program` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-125">The Console Application template for .NET Core defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument.</span></span> <span data-ttu-id="1641b-126">`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-126">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="1641b-127">애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 *args* 배열에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-127">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

   <span data-ttu-id="1641b-128">사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-128">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

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

   ```vb
   Imports System

   Module Program
       Sub Main(args As String())
           Console.WriteLine("Hello World!")
       End Sub
   End Module
   ```

   <span data-ttu-id="1641b-129">템플릿은 간단한 "Hello World" 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-129">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="1641b-130"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="1641b-130">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="1641b-131">콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-131">in the console window.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="1641b-132">앱 실행</span><span class="sxs-lookup"><span data-stu-id="1641b-132">Run the app</span></span>

1. <span data-ttu-id="1641b-133">프로그램을 실행하려면 도구 모음에서 **HelloWorld**를 선택하거나 **F5**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-133">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

   ![HelloWorld 실행 단추가 선택된 Visual Studio 도구 모음](./media/with-visual-studio/run-program.png)

   <span data-ttu-id="1641b-135">콘솔 창이 열리고 "Hello World!"라는 텍스트가</span><span class="sxs-lookup"><span data-stu-id="1641b-135">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="1641b-136">화면에 표시되며 일부 Visual Studio 디버그 정보도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-136">printed on the screen and some Visual Studio debug information.</span></span>

   ![“Hello World 계속하려면 아무 키나 누르세요.”를 표시하는 콘솔 창](./media/with-visual-studio/hello-world-console.png)

1. <span data-ttu-id="1641b-138">콘솔 창을 닫으려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-138">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="1641b-139">앱 향상</span><span class="sxs-lookup"><span data-stu-id="1641b-139">Enhance the app</span></span>

<span data-ttu-id="1641b-140">사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-140">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span> <span data-ttu-id="1641b-141">다음 지침에 따라 앱을 수정하고 다시 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-141">The following instructions modify the app and run it again:</span></span>

1. <span data-ttu-id="1641b-142">현재 `Console.WriteLine`을 호출하는 줄인 `Main` 메서드의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-142">Replace the contents of the `Main` method, which is currently just the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="Snippet1":::

   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="Snippet1":::

   <span data-ttu-id="1641b-143">이 코드는 "What is your name?"을</span><span class="sxs-lookup"><span data-stu-id="1641b-143">This code displays "What is your name?"</span></span> <span data-ttu-id="1641b-144">콘솔 창에 표시하고 사용자가 문자열을 입력한 후 Enter 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-144">in the console window and waits until the user enters a string followed by the Enter key.</span></span> <span data-ttu-id="1641b-145">이 문자열을 `name`이라는 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="1641b-146">또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수(Visual Basic에서는 `currentDate`)에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="1641b-147">마지막으로 콘솔 창에 이러한 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="1641b-148">`\n`(Visual Basic에서는 `vbCrLf`)은 줄 바꿈 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-148">The `\n` (`vbCrLf` in Visual Basic) represents a newline character.</span></span>

   <span data-ttu-id="1641b-149">문자열 앞의 달러 기호(`$`)를 사용하면 변수 이름과 같은 식을 문자열의 중괄호 안에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="1641b-150">식 값은 식 대신 문자열에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="1641b-151">이 구문을 [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="1641b-152">프로그램을 실행하려면 도구 모음에서 **HelloWorld**를 선택하거나 **F5**를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-152">To run the program, choose **HelloWorld** on the toolbar, or press **F5**.</span></span>

1. <span data-ttu-id="1641b-153">이름을 입력하고 **Enter** 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-153">Respond to the prompt by entering a name and pressing the **Enter** key.</span></span>

   ![수정된 프로그램 출력이 표시된 콘솔 창](./media/with-visual-studio/hello-world-update.png)

1. <span data-ttu-id="1641b-155">콘솔 창을 닫으려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-155">Press any key to close the console window.</span></span>

## <a name="next-steps"></a><span data-ttu-id="1641b-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="1641b-156">Next steps</span></span>

<span data-ttu-id="1641b-157">이 자습서에서는 .NET Core 애플리케이션을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-157">In this tutorial, you created a .NET Core application.</span></span> <span data-ttu-id="1641b-158">다음 자습서에서는 앱을 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="1641b-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="1641b-159">Visual Studio에서 .NET Core 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="1641b-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio.md)
