---
title: Mac용 Visual Studio를 사용하여 .NET 콘솔 애플리케이션 만들기
description: Mac용 Visual Studio를 사용하여 .NET 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
ms.date: 11/30/2020
ms.openlocfilehash: 1351b06eec32cd8d3d9d44926655405fe2246f58
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599488"
---
# <a name="tutorial-create-a-net-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="77e3c-103">자습서: Mac용 Visual Studio를 사용하여 .NET 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="77e3c-103">Tutorial: Create a .NET console application using Visual Studio for Mac</span></span>

<span data-ttu-id="77e3c-104">이 자습서에서는 Mac용 Visual Studio를 사용하여 .NET 콘솔 애플리케이션을 만들고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-104">This tutorial shows how to create and run a .NET console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="77e3c-105">사용자 의견은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-105">Your feedback is highly valued.</span></span> <span data-ttu-id="77e3c-106">Mac용 Visual Studio의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="77e3c-107">Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고** 를 선택하거나 시작 화면에서 **문제 보고** 를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="77e3c-108">[Developer Community](https://aka.ms/feedback/report?space=41)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-108">You can track your feedback in the [Developer Community](https://aka.ms/feedback/report?space=41) portal.</span></span>
> * <span data-ttu-id="77e3c-109">제안하려면 메뉴에서 **도움말** > **제안하기** 를 선택하거나 시작 화면에서 **제안하기** 를 선택합니다. 그러면 [Mac용 Visual Studio Developer Community 웹 페이지](https://aka.ms/feedback/suggest?space=41)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://aka.ms/feedback/suggest?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="77e3c-110">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="77e3c-110">Prerequisites</span></span>

* <span data-ttu-id="77e3c-111">[Mac용 Visual Studio 버전 8.8 이상](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="77e3c-111">[Visual Studio for Mac version 8.8 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="77e3c-112">.NET Core 설치 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="77e3c-113">Xamarin 설치는 .NET 개발에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-113">Installing Xamarin is optional for .NET development.</span></span> <span data-ttu-id="77e3c-114">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="77e3c-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="77e3c-115">[자습서: Mac용 Visual Studio](/visualstudio/mac/installation)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="77e3c-116">[지원되는 macOS 버전](../install/windows.md).</span><span class="sxs-lookup"><span data-stu-id="77e3c-116">[Supported macOS versions](../install/windows.md).</span></span>
  * <span data-ttu-id="77e3c-117">[Mac용 Visual Studio에서 지원되는 .NET 버전](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="77e3c-117">[.NET versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="77e3c-118">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="77e3c-118">Create the app</span></span>

1. <span data-ttu-id="77e3c-119">Mac용 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-119">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="77e3c-120">시작 창에서 **새로 만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-120">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Mac용 Visual Studio 시작 화면의 새로 만들기 버튼":::

1. <span data-ttu-id="77e3c-122">**새 프로젝트** 대화 상자에서 **웹 및 콘솔** 노드 아래에서 **앱** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-122">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="77e3c-123">**콘솔 애플리케이션** 템플릿을 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-123">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="새 프로젝트 템플릿 목록":::

1. <span data-ttu-id="77e3c-125">**새 콘솔 애플리케이션 구성** 대화 상자의 **대상 프레임워크** 드롭다운에서 **.NET 5.0** 을 선택하고 **다음** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-125">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET 5.0**, and select **Next**.</span></span>

1. <span data-ttu-id="77e3c-126">**프로젝트 이름** 으로 "HelloWorld"를 입력하고 **만들기** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-126">Type "HelloWorld" for the **Project Name**, and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="새 콘솔 애플리케이션 대화 상자 구성":::

<span data-ttu-id="77e3c-128">템플릿은 간단한 "Hello World" 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-128">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="77e3c-129"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="77e3c-129">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="77e3c-130">터미널 창에서 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-130">in the terminal window.</span></span>

<span data-ttu-id="77e3c-131">템플릿 코드는 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`으로 `Program` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-131">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="77e3c-132">`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-132">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="77e3c-133">애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 `args` 배열에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-133">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="77e3c-134">앱 실행</span><span class="sxs-lookup"><span data-stu-id="77e3c-134">Run the app</span></span>

1. <span data-ttu-id="77e3c-135"><kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 디버그 없이 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-135">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="Hello World!가 표시된 터미널":::

1. <span data-ttu-id="77e3c-137">**터미널** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-137">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="77e3c-138">앱 향상</span><span class="sxs-lookup"><span data-stu-id="77e3c-138">Enhance the app</span></span>

<span data-ttu-id="77e3c-139">사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-139">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="77e3c-140">*Program.cs* 에서 `Console.WriteLine`을 호출하는 줄인 `Main` 메서드의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-140">In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="MainMethod":::

   <span data-ttu-id="77e3c-141">해당 코드는 콘솔 창에 프롬프트를 표시하고 사용자가 문자열을 입력한 후 <kbd>Enter</kbd> 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-141">This code displays a prompt in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="77e3c-142">이 문자열을 `name`이라는 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-142">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="77e3c-143">또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-143">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="77e3c-144">또한 콘솔 창에 해당 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-144">And it displays these values in the console window.</span></span> <span data-ttu-id="77e3c-145">마지막으로 콘솔 창에 프롬프트를 표시하고 <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> 메서드를 호출하여 사용자 입력을 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-145">Finally, it displays a prompt in the console window and calls the <xref:System.Console.ReadKey(System.Boolean)?displayProperty=nameWithType> method to wait for user input.</span></span>

   <span data-ttu-id="77e3c-146">`\n`은 줄 바꿈 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-146">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="77e3c-147">문자열 앞의 달러 기호(`$`)를 사용하면 변수 이름과 같은 식을 문자열의 중괄호 안에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-147">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="77e3c-148">식 값은 식 대신 문자열에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-148">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="77e3c-149">이 구문을 [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-149">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="77e3c-150"><kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-150">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="77e3c-151">이름을 입력하고 <kbd>Enter</kbd>를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-151">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="수정된 프로그램 출력이 표시된 터미널":::

1. <span data-ttu-id="77e3c-153">터미널을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-153">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="77e3c-154">다음 단계</span><span class="sxs-lookup"><span data-stu-id="77e3c-154">Next steps</span></span>

<span data-ttu-id="77e3c-155">이 자습서에서는 .NET 콘솔 애플리케이션을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-155">In this tutorial, you created a .NET console application.</span></span> <span data-ttu-id="77e3c-156">다음 자습서에서는 앱을 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="77e3c-156">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="77e3c-157">Mac용 Visual Studio를 사용하여 .NET 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="77e3c-157">Debug a .NET console application using Visual Studio for Mac</span></span>](debugging-with-visual-studio-mac.md)
