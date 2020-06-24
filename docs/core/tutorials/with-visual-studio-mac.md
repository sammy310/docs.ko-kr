---
title: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 만들기
description: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션을 만드는 방법을 알아봅니다.
ms.date: 06/02/2020
ms.openlocfilehash: 57f16e510270b7256b285493b1f978101fc11804
ms.sourcegitcommit: f6350c2c542e6edd52d7e9d6667b96d85d810e67
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2020
ms.locfileid: "84717525"
---
# <a name="tutorial-create-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="43631-103">자습서: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 만들기</span><span class="sxs-lookup"><span data-stu-id="43631-103">Tutorial: Create a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="43631-104">이 자습서에서는 Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션을 만들고 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="43631-104">This tutorial shows how to create and run a .NET Core console application using Visual Studio for Mac.</span></span>

> [!NOTE]
> <span data-ttu-id="43631-105">사용자 의견은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-105">Your feedback is highly valued.</span></span> <span data-ttu-id="43631-106">Mac용 Visual Studio의 개발 팀에 다음 두 가지 방법으로 의견을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43631-106">There are two ways you can provide feedback to the development team on Visual Studio for Mac:</span></span>
>
> * <span data-ttu-id="43631-107">Mac용 Visual Studio의 메뉴에서 **도움말** > **문제 보고**를 선택하거나 시작 화면에서 **문제 보고**를 선택하면 버그 보고서를 작성하기 위한 창이 열립니다.</span><span class="sxs-lookup"><span data-stu-id="43631-107">In Visual Studio for Mac, select **Help** > **Report a Problem** from the menu or **Report a Problem** from the Welcome screen, which will open a window for filing a bug report.</span></span> <span data-ttu-id="43631-108">[Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html)(개발자 커뮤니티) 포털에서 의견을 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43631-108">You can track your feedback in the [Developer Community](https://developercommunity.visualstudio.com/spaces/8/index.html) portal.</span></span>
> * <span data-ttu-id="43631-109">제안하려면 메뉴에서 **도움말** > **제안하기**를 선택하거나 시작 화면에서 **제안하기**를 선택합니다. 그러면 [Mac용 Visual Studio Developer Community 웹 페이지](https://developercommunity.visualstudio.com/content/idea/post.html?space=41)로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="43631-109">To make a suggestion, select **Help** > **Provide a Suggestion** from the menu or **Provide a Suggestion** from the Welcome screen, which will take you to the [Visual Studio for Mac Developer Community webpage](https://developercommunity.visualstudio.com/content/idea/post.html?space=41).</span></span>

## <a name="prerequisites"></a><span data-ttu-id="43631-110">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="43631-110">Prerequisites</span></span>

* <span data-ttu-id="43631-111">[Mac용 Visual Studio 버전 8.6 이상](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span><span class="sxs-lookup"><span data-stu-id="43631-111">[Visual Studio for Mac version 8.6 or later](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link).</span></span> <span data-ttu-id="43631-112">.NET Core 설치 옵션을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-112">Select the option to install .NET Core.</span></span> <span data-ttu-id="43631-113">Xamarin의 설치는 .NET Core 개발에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="43631-113">Installing Xamarin is optional for .NET Core development.</span></span> <span data-ttu-id="43631-114">자세한 내용은 다음 자료를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="43631-114">For more information, see the following resources:</span></span>

  * <span data-ttu-id="43631-115">[자습서: Mac용 Visual Studio](/visualstudio/mac/installation)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-115">[Tutorial: Install Visual Studio for Mac](/visualstudio/mac/installation).</span></span>
  * <span data-ttu-id="43631-116">[지원되는 macOS 버전](../install/dependencies.md?pivots=os-macos).</span><span class="sxs-lookup"><span data-stu-id="43631-116">[Supported macOS versions](../install/dependencies.md?pivots=os-macos).</span></span>
  * <span data-ttu-id="43631-117">[Mac용 Visual Studio에서 지원되는 .NET Core 버전](/visualstudio/mac/net-core-support).</span><span class="sxs-lookup"><span data-stu-id="43631-117">[.NET Core versions supported by Visual Studio for Mac](/visualstudio/mac/net-core-support).</span></span>

## <a name="create-the-app"></a><span data-ttu-id="43631-118">앱 만들기</span><span class="sxs-lookup"><span data-stu-id="43631-118">Create the app</span></span>

<span data-ttu-id="43631-119">"HelloWorld"라는 .NET Core 콘솔 앱 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="43631-119">Create a .NET Core console app project named "HelloWorld".</span></span>

1. <span data-ttu-id="43631-120">Mac용 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-120">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="43631-121">시작 창에서 **새로 만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-121">Select **New** in the start window.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-project.png" alt-text="Mac용 Visual Studio 시작 화면의 새로 만들기 버튼":::

1. <span data-ttu-id="43631-123">**새 프로젝트** 대화 상자에서 **웹 및 콘솔** 노드 아래에서 **앱**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-123">In the **New Project** dialog, select **App** under the **Web and Console** node.</span></span> <span data-ttu-id="43631-124">**콘솔 애플리케이션** 템플릿을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-124">Select the **Console Application** template, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-dialog.png" alt-text="새 프로젝트 템플릿 목록":::

1. <span data-ttu-id="43631-126">**새 콘솔 애플리케이션 구성** 대화 상자의 **대상 프레임워크** 드롭다운에서 **.NET Core 3.1**을 선택하고 **다음**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-126">In the **Target Framework** drop-down of the **Configure your new Console Application** dialog, select **.NET Core 3.1**, and select **Next**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/target-framework.png" alt-text="대상 프레임워크 선택":::

1. <span data-ttu-id="43631-128">**프로젝트 이름**으로 "HelloWorld"를 입력하고 **만들기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-128">Type "HelloWorld" for the **Project Name**, and select **Create**.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-new-options.png" alt-text="새 콘솔 애플리케이션 대화 상자 구성":::

<span data-ttu-id="43631-130">템플릿은 간단한 "Hello World" 애플리케이션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="43631-130">The template creates a simple "Hello World" application.</span></span> <span data-ttu-id="43631-131"><xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> 메서드를 호출하여 "Hello World!"를</span><span class="sxs-lookup"><span data-stu-id="43631-131">It calls the <xref:System.Console.WriteLine(System.String)?displayProperty=nameWithType> method to display "Hello World!"</span></span> <span data-ttu-id="43631-132">터미널 창에서 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-132">in the terminal window.</span></span>

<span data-ttu-id="43631-133">템플릿 코드는 <xref:System.String> 배열을 인수로 사용하는 단일 메서드 `Main`으로 `Program` 클래스를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-133">The template code defines a class, `Program`, with a single method, `Main`, that takes a <xref:System.String> array as an argument:</span></span>

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

<span data-ttu-id="43631-134">`Main`은 애플리케이션 진입점으로, 애플리케이션을 시작할 때 런타임에 의해 자동으로 호출되는 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="43631-134">`Main` is the application entry point, the method that's called automatically by the runtime when it launches the application.</span></span> <span data-ttu-id="43631-135">애플리케이션이 시작될 때 제공되는 모든 명령줄 인수는 `args` 배열에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43631-135">Any command-line arguments supplied when the application is launched are available in the `args` array.</span></span>

## <a name="run-the-app"></a><span data-ttu-id="43631-136">앱 실행</span><span class="sxs-lookup"><span data-stu-id="43631-136">Run the app</span></span>

1. <span data-ttu-id="43631-137"><kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 디버그 없이 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-137">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app without debugging.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/visual-studio-mac-output.png" alt-text="Hello World!가 표시된 터미널":::

1. <span data-ttu-id="43631-139">**터미널** 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="43631-139">Close the **Terminal** window.</span></span>

## <a name="enhance-the-app"></a><span data-ttu-id="43631-140">앱 향상</span><span class="sxs-lookup"><span data-stu-id="43631-140">Enhance the app</span></span>

<span data-ttu-id="43631-141">사용자에게 이름을 입력하라는 메시지를 표시한 다음 사용자 이름을 날짜 및 시간과 함께 표시하도록 애플리케이션을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-141">Enhance the application to prompt the user for their name and display it along with the date and time.</span></span>

1. <span data-ttu-id="43631-142">*Program.cs*에서 `Console.WriteLine`을 호출하는 줄인 `Main` 메서드의 내용을 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="43631-142">In *Program.cs*, replace the contents of the `Main` method, which is the line that calls `Console.WriteLine`, with the following code:</span></span>

   :::code language="csharp" source="./snippets/with-visual-studio/csharp/Program.cs" id="1":::

   <span data-ttu-id="43631-143">이 코드는 "What is your name?"을</span><span class="sxs-lookup"><span data-stu-id="43631-143">This code displays "What is your name?"</span></span> <span data-ttu-id="43631-144">콘솔 창에 표시하고 사용자가 문자열을 입력한 후 <kbd>Enter</kbd> 키를 누를 때까지 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="43631-144">in the console window and waits until the user enters a string followed by the <kbd>enter</kbd> key.</span></span> <span data-ttu-id="43631-145">이 문자열을 `name`이라는 변수에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-145">It stores this string in a variable named `name`.</span></span> <span data-ttu-id="43631-146">또한 현재 현지 시간을 포함하는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성 값을 검색한 후 `date`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-146">It also retrieves the value of the <xref:System.DateTime.Now?displayProperty=nameWithType> property, which contains the current local time, and assigns it to a variable named `date`.</span></span> <span data-ttu-id="43631-147">마지막으로 콘솔 창에 이러한 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-147">Finally, it displays these values in the console window.</span></span>

   <span data-ttu-id="43631-148">`\n`은 줄 바꿈 문자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="43631-148">The `\n` represents a newline character.</span></span>

   <span data-ttu-id="43631-149">문자열 앞의 달러 기호(`$`)를 사용하면 변수 이름과 같은 식을 문자열의 중괄호 안에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="43631-149">The dollar sign (`$`) in front of a string lets you put expressions such as variable names in curly braces in the string.</span></span> <span data-ttu-id="43631-150">식 값은 식 대신 문자열에 삽입됩니다.</span><span class="sxs-lookup"><span data-stu-id="43631-150">The expression value is inserted into the string in place of the expression.</span></span> <span data-ttu-id="43631-151">이 구문을 [보간된 문자열](../../csharp/language-reference/tokens/interpolated.md)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-151">This syntax is referred to as [interpolated strings](../../csharp/language-reference/tokens/interpolated.md).</span></span>

1. <span data-ttu-id="43631-152"><kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 앱을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-152">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run the app.</span></span>

1. <span data-ttu-id="43631-153">이름을 입력하고 <kbd>Enter</kbd>를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-153">Respond to the prompt by entering a name and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/with-visual-studio-mac/hello-world-update.png" alt-text="수정된 프로그램 출력이 표시된 터미널":::

1. <span data-ttu-id="43631-155">터미널을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="43631-155">Close the terminal.</span></span>

## <a name="next-steps"></a><span data-ttu-id="43631-156">다음 단계</span><span class="sxs-lookup"><span data-stu-id="43631-156">Next steps</span></span>

<span data-ttu-id="43631-157">이 자습서에서는 .NET Core 콘솔 애플리케이션을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="43631-157">In this tutorial, you created a .NET Core console application.</span></span> <span data-ttu-id="43631-158">다음 자습서에서는 앱을 디버그합니다.</span><span class="sxs-lookup"><span data-stu-id="43631-158">In the next tutorial, you debug the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="43631-159">Visual Studio에서 .NET Core 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="43631-159">Debug a .NET Core console application in Visual Studio</span></span>](debugging-with-visual-studio-mac.md)
