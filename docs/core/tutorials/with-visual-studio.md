---
title: Visual Studio를 사용하여 .NET 콘솔 애플리케이션 만들기
description: Visual Studio를 사용하여 C# 또는 Visual Basic으로 .NET 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 3986ef4083b964799be33d2876570ac4cf2082b8
ms.sourcegitcommit: 1d3af230ec30d8d061be7a887f6ba38a530c4ece
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2021
ms.locfileid: "102511855"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio"></a><span data-ttu-id="6a21a-103">자습서: Visual Studio를 사용하여 .NET 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="6a21a-103">Tutorial: Create a .NET console application using Visual Studio</span></span>

<span data-ttu-id="6a21a-104">이 자습서에서는 Visual Studio 2019에서 .NET 콘솔 애플리케이션을 만들고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-104">This tutorial shows how to create and run a .NET console application in Visual Studio 2019.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6a21a-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="6a21a-105">Prerequisites</span></span>

- <span data-ttu-id="6a21a-106">**.NET Core 플랫폼 간 개발** 워크로드가 설치된 [Visual Studio 2019 버전 16.8 이상](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019).</span><span class="sxs-lookup"><span data-stu-id="6a21a-106">[Visual Studio 2019 version 16.8 or a later version](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) with the **.NET Core cross-platform development** workload installed.</span></span> <span data-ttu-id="6a21a-107">이 워크로드를 선택하면 .NET 5.0 SDK가 자동으로 설치됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-107">The .NET 5.0 SDK is automatically installed when you select this workload.</span></span>

  <span data-ttu-id="6a21a-108">자세한 내용은 [Visual Studio로 .NET SDK 설치](../install/windows.md#install-with-visual-studio)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6a21a-108">For more information, see [Install the .NET SDK with Visual Studio](../install/windows.md#install-with-visual-studio).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="6a21a-109">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="6a21a-109">Create the app</span></span>

<span data-ttu-id="6a21a-110">“HelloWorld”라는 .NET 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-110">Create a .NET console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="6a21a-111">Visual Studio 2019를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-111">Start Visual Studio 2019.</span></span>

1. <span data-ttu-id="6a21a-112">**도구** > **옵션** > **환경** > **미리 보기 기능** 을 선택하고 **새 프로젝트에 모든 .NET Core 템플릿 표시(다시 시작해야 함)** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-112">Select **Tools** > **Options** > **Environment** > **Preview features**, and then select **Show all .NET Core templates in the New project (requires restart)**.</span></span>

   :::image type="content" source="media/with-visual-studio/dotnet-options.png" alt-text="모든 .NET 템플릿 표시 옵션":::

1. <span data-ttu-id="6a21a-114">Visual Studio를 닫았다가 다시 엽니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-114">Close and reopen Visual Studio.</span></span>

1. <span data-ttu-id="6a21a-115">시작 페이지에서 **새 프로젝트 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-115">On the start page, choose **Create a new project**.</span></span>

   :::image type="content" source="./media/with-visual-studio/start-window.png" alt-text="Visual Studio 시작 페이지에서 새 프로젝트 만들기 단추 선택":::

1. <span data-ttu-id="6a21a-117">**새 프로젝트 만들기** 페이지의 검색 상자에 **console** 을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-117">On the **Create a new project** page, enter **console** in the search box.</span></span> <span data-ttu-id="6a21a-118">다음으로 언어 목록에서 **C#** 또는 **Visual Basic** 을 선택한 다음 플랫폼 목록에서 **모든 플랫폼** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-118">Next, choose **C#** or **Visual Basic** from the language list, and then choose **All platforms** from the platform list.</span></span> <span data-ttu-id="6a21a-119">**콘솔 애플리케이션** 템플릿을 선택한 후 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-119">Choose the **Console Application** template, and then choose **Next**.</span></span>

   :::image type="content" source="./media/with-visual-studio/create-new-project.png" alt-text="필터가 선택된 새 프로젝트 만들기 창":::

   > [!TIP]
   > <span data-ttu-id="6a21a-121">.NET 템플릿이 표시되지 않으면 필요한 워크로드가 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-121">If you don't see the .NET templates, you're probably missing the required workload.</span></span> <span data-ttu-id="6a21a-122">**원하는 항목을 찾을 수 없나요?** 메시지에서 **추가 도구 및 기능 설치** 링크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-122">Under the **Not finding what you're looking for?** message, choose the **Install more tools and features** link.</span></span> <span data-ttu-id="6a21a-123">Visual Studio 설치 관리자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-123">The Visual Studio Installer opens.</span></span> <span data-ttu-id="6a21a-124">**.NET Core 플랫폼 간 개발** 워크로드가 설치되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-124">Make sure you have the **.NET Core cross-platform development** workload installed.</span></span>

1. <span data-ttu-id="6a21a-125">**새 프로젝트 구성** 대화 상자에서 **프로젝트 이름** 상자에 **HelloWorld** 를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-125">In the **Configure your new project** dialog,  enter **HelloWorld** in the **Project name** box.</span></span> <span data-ttu-id="6a21a-126">그리고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-126">Then choose **Next**.</span></span>

   :::image type="content" source="./media/with-visual-studio/configure-new-project.png" alt-text="프로젝트 이름, 위치 및 솔루션 이름 필드를 사용하여 새 프로젝트 창을 구성합니다.":::

1. <span data-ttu-id="6a21a-128">**추가 정보** 대화 상자에서 **.NET 5.0(현재)** 을 선택한 후 **만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-128">In the **Additional information** dialog, select **.NET 5.0 (Current)**, and then select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio/additional-info.png" alt-text="추가 정보 대화 상자":::

<span data-ttu-id="6a21a-130">템플릿은 간단한 "Hello World" 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="6a21a-131"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="6a21a-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="6a21a-132">콘솔 창에 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-132">in the console window.</span></span>

<span data-ttu-id="6a21a-133">템플릿 코드는 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`으로 `Program` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="6a21a-134">`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="6a21a-135">애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 *args* 배열에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-135">Any command-line arguments supplied when the application is launched are available in the *args* array.</span></span>

<span data-ttu-id="6a21a-136">사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-136">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="6a21a-137">앱 실행</span><span class="sxs-lookup"><span data-stu-id="6a21a-137">Run the app</span></span>

1. <span data-ttu-id="6a21a-138"><kbd>Ctrl</kbd>+<kbd>F5</kbd>를 눌러 디버깅 없이 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-138">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

   <span data-ttu-id="6a21a-139">콘솔 창이 열리고 "Hello World!"라는 텍스트가</span><span class="sxs-lookup"><span data-stu-id="6a21a-139">A console window opens with the text "Hello World!"</span></span> <span data-ttu-id="6a21a-140">화면에 출력되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-140">printed on the screen.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-console.png" alt-text="“Hello World 계속하려면 아무 키나 누르세요.”를 표시하는 콘솔 창":::

1. <span data-ttu-id="6a21a-142">콘솔 창을 닫으려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-142">Press any key to close the console window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="6a21a-143">앱 향상</span><span class="sxs-lookup"><span data-stu-id="6a21a-143">Enhance the app</span></span>

<span data-ttu-id="6a21a-144">사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-144">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="6a21a-145">*Program.cs* 또는 *Program.vb* 에서 다음 코드로 `Console.WriteLine`를 호출하는 줄인 `Main` 메서드의 내용을 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-145">In *Program.cs* or *Program.vb*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::
   :::code language="vb" source="./snippets/with-visual-studio/vb/Program.vb" id="MainMethod":::

   <span data-ttu-id="6a21a-146">해당 코드는 콘솔 창에 프롬프트를 표시하고 사용자가 문자열을 입력한 후 <kbd>Enter</kbd> 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-146">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>Enter</kbd> key.</span></span> <span data-ttu-id="6a21a-147">이 문자열을 `name`이라는 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-147">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="6a21a-148">또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수(Visual Basic에서는 `currentDate`)에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-148">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date` (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="6a21a-149">또한 콘솔 창에 해당 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-149">And it displays these values in the console window.</span></span> <span data-ttu-id="6a21a-150">마지막으로 콘솔 창에 프롬프트를 표시하고 <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> 메서드를 호출하여 사용자 입력을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-150">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="6a21a-151"><xref:System.Environment.NewLine>은 줄 바꿈을 나타내는 플랫폼과 언어에 독립적인 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-151"><xref:System.Environment.NewLine> is a platform-independent and language-independent way to represent a line break.</span></span> <span data-ttu-id="6a21a-152">대안은 C#의 `\n` 및 Visual Basic의 `vbCrLf`입니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-152">Alternatives are `\n` in C# and `vbCrLf` in Visual Basic.</span></span>

   <span data-ttu-id="6a21a-153">문자열 앞의 달러 기호(`$`)를 사용하면 변수 이름과 같은 식을 문자열의 중괄호 안에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-153">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="6a21a-154">식 값은 식 대신 문자열에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-154">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="6a21a-155">이 구문을 [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-155">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="6a21a-156"><kbd>Ctrl</kbd>+<kbd>F5</kbd>를 눌러 디버깅 없이 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-156">Press <kbd>Ctrl</kbd>+<kbd>F5</kbd> to run the program without debugging.</span></span>

1. <span data-ttu-id="6a21a-157">이름을 입력하고 <kbd>Enter</kbd> 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-157">Respond to the prompt by entering a name and pressing the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="./media/with-visual-studio/hello-world-update.png" alt-text="수정된 프로그램 출력이 표시된 콘솔 창":::

1. <span data-ttu-id="6a21a-159">콘솔 창을 닫으려면 아무 키나 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-159">Press any key to close the console window.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="6a21a-160">추가 리소스</span><span class="sxs-lookup"><span data-stu-id="6a21a-160">Additional resources</span></span>

- [<span data-ttu-id="6a21a-161">현재 릴리스 및 장기 지원 릴리스</span><span class="sxs-lookup"><span data-stu-id="6a21a-161">Current releases and long-term support releases</span></span>](../releases-and-support.md#net-core-and-net-5-version-lifecycles)

## <a name="next-steps"></a><span data-ttu-id="6a21a-162">다음 단계</span><span class="sxs-lookup"><span data-stu-id="6a21a-162">Next steps</span></span>

<span data-ttu-id="6a21a-163">이 자습서에서는 .NET 콘솔 애플리케이션을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-163">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="6a21a-164">다음 자습서에서는 앱을 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="6a21a-164">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="6a21a-165">Visual Studio를 사용하여 .NET 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="6a21a-165">Debug a .NET console application using Visual Studio</span></span>](debugging-with-visual-studio.md)
