---
title: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 디버그
description: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 앱을 디버그하는 방법을 알아봅니다.
ms.date: 06/08/2020
ms.openlocfilehash: 4941605923a9897d481aca4ec31408ab62e873f3
ms.sourcegitcommit: 1cbd77da54405ea7dba343ac0334fb03237d25d2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/11/2020
ms.locfileid: "84713486"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-for-mac"></a><span data-ttu-id="bf451-103">자습서: Mac용 Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="bf451-103">Tutorial: Debug a .NET Core console application using Visual Studio for Mac</span></span>

<span data-ttu-id="bf451-104">이 자습서에서는 Mac용 Visual Studio에서 사용할 수 있는 디버깅 도구를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-104">This tutorial introduces the debugging tools available in Visual Studio for Mac.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="bf451-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="bf451-105">Prerequisites</span></span>

- <span data-ttu-id="bf451-106">이 자습서는 [Mac용 Visual Studio에서 .NET Core 콘솔 애플리케이션 만들기](using-on-mac-vs.md)에서 만든 콘솔 앱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio for Mac](using-on-mac-vs.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="bf451-107">디버그 빌드 구성 사용</span><span class="sxs-lookup"><span data-stu-id="bf451-107">Use Debug build configuration</span></span>

<span data-ttu-id="bf451-108">디버그 및 릴리스는 Visual Studio의 기본 빌드 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-108">*Debug* and *Release* are Visual Studio's built-in build configurations.</span></span> <span data-ttu-id="bf451-109">디버그 빌드 구성은 디버깅에 사용하고, 릴리스 구성은 최종 릴리스 배포에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="bf451-110">디버그 구성에서 프로그램은 완전히 기호화된 디버그 정보를 사용하여 컴파일되며 최적화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="bf451-111">최적화하면 소스 코드와 생성된 명령 간의 관계가 복잡해지므로 디버깅이 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="bf451-112">프로그램의 릴리스 구성은 완전히 최적화되고, 기호화된 디버그 정보를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

<span data-ttu-id="bf451-113">기본적으로 Visual Studio는 디버그 빌드 구성을 사용하므로 디버깅 전에 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-113">By default, Visual Studio uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="bf451-114">Mac용 Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-114">Start Visual Studio for Mac.</span></span>

1. <span data-ttu-id="bf451-115">[Mac용 Visual Studio에서 .NET Core 콘솔 애플리케이션 만들기](using-on-mac-vs.md)에서 만든 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-115">Open the project that you created in [Create a .NET Core console application in Visual Studio for Mac](using-on-mac-vs.md).</span></span>

   <span data-ttu-id="bf451-116">현재 빌드 구성은 도구 모음에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-116">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="bf451-117">다음 도구 모음 그림은 Visual Studio가 앱의 디버그 버전을 컴파일하도록 구성되어 있음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-117">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-debug.png" alt-text="디버그가 강조 표시된 Visual Studio 도구 모음":::

## <a name="set-a-breakpoint"></a><span data-ttu-id="bf451-119">중단점 설정</span><span class="sxs-lookup"><span data-stu-id="bf451-119">Set a breakpoint</span></span>

<span data-ttu-id="bf451-120">중단점은 중단점이 설정된 줄이 실행되기 전에 애플리케이션 실행을 일시적으로 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-120">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="bf451-121">이름, 날짜, 시간을 표시하는 줄에 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-121">Set a breakpoint on the line that displays the name, date, and time.</span></span> <span data-ttu-id="bf451-122">이렇게 하려면 코드 줄에 커서를 올려 놓고 <kbd>⌘</kbd><kbd>\\</kbd>(<kbd>command</kbd>+<kbd>\\</kbd>)를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-122">To do that, place the cursor in the line of code and press <kbd>⌘</kbd><kbd>\\</kbd> (<kbd>command</kbd>+<kbd>\\</kbd>).</span></span> <span data-ttu-id="bf451-123">메뉴에서 **실행** > **중단점 설정/해제**를 선택해도 중단점을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-123">Another way to set a breakpoint is by selecting **Run** > **Toggle Breakpoint** from the menu.</span></span>

   <span data-ttu-id="bf451-124">Visual Studio는 중단점이 설정된 줄을 강조 표시하고 왼쪽 여백에 빨간 점을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-124">Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/set-breakpoint-in-editor.png" alt-text="중단점이 설정된 Visual Studio 프로그램 창":::

1. <span data-ttu-id="bf451-126"><kbd>⌘</kbd><kbd>↵</kbd>(<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 디버깅 모드에서 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-126">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start the program in debugging mode.</span></span> <span data-ttu-id="bf451-127">메뉴에서 **실행** > **디버깅 시작**을 선택해도 디버깅을 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-127">Another way to start debugging is by choosing **Run** > **Start Debugging** from the menu.</span></span>

1. <span data-ttu-id="bf451-128">프로그램 이름을 입력하라는 메시지가 표시되면 터미널 창에 문자열을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-128">Enter a string in the terminal window when the program prompts for a name, and then press <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="bf451-129">중단점에 도달할 때와 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-129">Program execution stops when it reaches the breakpoint, before the `Console.WriteLine` method executes.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-hit.png" alt-text="Visual Studio의 중단점 스크린샷":::

## <a name="use-the-immediate-window"></a><span data-ttu-id="bf451-131">즉시 실행 창 사용</span><span class="sxs-lookup"><span data-stu-id="bf451-131">Use the Immediate window</span></span>

<span data-ttu-id="bf451-132">**직접 실행 창**에서는 디버그하는 애플리케이션을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-132">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="bf451-133">대화형으로 변수 값을 변경하여 프로그램에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-133">You can interactively change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="bf451-134">**직접 실행 창**이 표시되지 않는 경우 **보기** > **디버그 패드** > **직접 실행**을 선택하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-134">If the **Immediate** window is not visible, display it by choosing **View** > **Debug Pads** > **Immediate**.</span></span>

1. <span data-ttu-id="bf451-135">**직접 실행 창**에 `name = "Gracie"`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-135">Enter `name = "Gracie"` in the **Immediate** window and press <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="bf451-136">**직접 실행 창**에 `date = date.AddDays(1)`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-136">Enter `date = date.AddDays(1)` in the **Immediate** window and press <kbd>enter</kbd>.</span></span>

   <span data-ttu-id="bf451-137">**직접 실행 창**에는 문자열 변수의 새로운 값과 <xref:System.DateTime> 값의 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-137">The **Immediate** window displays the new value of the string variable and the properties of the <xref:System.DateTime> value.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window.png" alt-text="Visual Studio의 직접 실행 창":::

   <span data-ttu-id="bf451-139">**지역** 창에는 현재 실행 중인 메서드에 정의된 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-139">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span> <span data-ttu-id="bf451-140">방금 변경한 변수 값이 **로컬** 창에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-140">The values of the variables that you just changed are updated in the **Locals** window.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/locals-window.png" alt-text="Visual Studio의 로컬 창":::

1. <span data-ttu-id="bf451-142"><kbd>⌘</kbd><kbd>↵</kbd>(<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 디버깅을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-142">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to continue debugging.</span></span>

   <span data-ttu-id="bf451-143">터미널에 표시되는 값은 **직접 실행 창**에서 변경한 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-143">The values displayed in the terminal correspond to the changes you made in the **Immediate** window.</span></span>

   <span data-ttu-id="bf451-144">터미널이 표시되지 않을 경우 하단의 탐색 막대에서 **Terminal - HelloWorld**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-144">If you don't see the Terminal, select **Terminal - HelloWorld** in the bottom navigation bar.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/terminal-hello-world.png" alt-text="하단 탐색 막대의 Terminal - Hello World":::

1. <span data-ttu-id="bf451-146">아무 키나 눌러 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-146">Press any key to exit the program.</span></span>

1. <span data-ttu-id="bf451-147">터미널 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-147">Close the terminal window.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="bf451-148">조건부 중단점 설정</span><span class="sxs-lookup"><span data-stu-id="bf451-148">Set a conditional breakpoint</span></span>

<span data-ttu-id="bf451-149">프로그램은 사용자가 입력하는 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-149">The program displays a string that the user enters.</span></span> <span data-ttu-id="bf451-150">사용자가 아무 값도 입력하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="bf451-150">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="bf451-151">*조건부 중단점*이라는 유용한 디버깅 기능을 사용하여 이를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-151">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="bf451-152"><kbd>ctrl</kbd> 키를 누른 상태에서 중단점을 나타내는 빨간색 점을 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-152"><kbd>ctrl</kbd>-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="bf451-153">상황에 맞는 메뉴에서 **중단점 편집**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-153">In the context menu, select **Edit Breakpoint**.</span></span>

1. <span data-ttu-id="bf451-154">**중단점 편집** 대화 상자에서 **그리고 다음 조건이 true임** 아래에 있는 필드에 다음과 같은 코드를 입력한 후 **적용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-154">In the **Edit Breakpoint** dialog, enter the following code in the field that follows **And the following condition is true**, and select **Apply**.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-mac/breakpoint-settings.png" alt-text="중단점 설정 패널을 보여 주는 편집기":::

   <span data-ttu-id="bf451-156">디버거는 중단점이 적중될 때마다 `String.IsNullOrEmpty(name)` 메서드를 호출하고, 메서드 호출이 `true`를 반환하는 경우에만 이 줄에서 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-156">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="bf451-157">조건식 대신 문이 지정된 횟수만큼 실행되기 전에 프로그램 실행을 중단하는 적중 횟수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-157">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span>

1. <span data-ttu-id="bf451-158"><kbd>⌘</kbd><kbd>↵</kbd>(<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 디버깅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-158">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start debugging.</span></span>

1. <span data-ttu-id="bf451-159">이름을 입력하라는 메시지가 나타나면 터미널 창에서 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-159">In the terminal window, press <kbd>enter</kbd> when prompted to enter your name.</span></span>

   <span data-ttu-id="bf451-160">`name`이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>이라는 지정한 조건이 충족되었으므로 중단점에 도달하면 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-160">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint.</span></span>

1. <span data-ttu-id="bf451-161">**지역** 창을 선택합니다. 이 창에는 현재 실행 중인 메서드에 로컬인 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-161">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="bf451-162">이 경우 `Main`은 현재 실행 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-162">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="bf451-163">`name` 변수의 값은 `""`, 즉 <xref:System.String.Empty?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-163">Observe that the value of the `name` variable is `""`, that is, <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="bf451-164">**직접 실행 창**에 `name` 변수 이름을 입력하고 <kbd>Enter</kbd> 키를 눌러 값이 빈 문자열인지 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-164">You can also see that the value is an empty string by entering the `name` variable name in the **Immediate** window and pressing <kbd>enter</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/immediate-window-output.png" alt-text="이름이 빈 문자열임을 보여주는 직접 실행 창":::

1. <span data-ttu-id="bf451-166"><kbd>⌘</kbd><kbd>↵</kbd>(<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 디버깅을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-166">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to continue debugging.</span></span>

1. <span data-ttu-id="bf451-167">터미널 창에서 아무 키나 눌러서 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-167">In the terminal window, press any key to exit the program.</span></span>

1. <span data-ttu-id="bf451-168">터미널 창을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-168">Close the terminal window.</span></span>

1. <span data-ttu-id="bf451-169">코드 창 왼쪽 여백에 있는 빨간 점을 클릭하여 중단점을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-169">Clear the breakpoint by clicking on the red dot in the left margin of the code window.</span></span> <span data-ttu-id="bf451-170">중단점을 지우는 또 다른 방법은 코드 줄이 선택되어 있는 동안 **실행 > 중단점 설정/해제**를 선택하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-170">Another way to clear a breakpoint is by choosing **Run > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="bf451-171">단계별 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="bf451-171">Step through a program</span></span>

<span data-ttu-id="bf451-172">Visual Studio에서 프로그램을 한 줄씩 단계별로 실행하고 해당 실행을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-172">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="bf451-173">일반적으로 중단점을 설정하고 프로그램 코드 일부의 프로그램 흐름을 따라가면서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-173">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="bf451-174">이 프로그램은 작으므로 전체 프로그램을 단계별로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-174">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="bf451-175">`Main` 메서드의 시작을 표시하는 중괄호에서 중단점을 설정합니다(<kbd>command</kbd>+<kbd>\\</kbd> 누르기).</span><span class="sxs-lookup"><span data-stu-id="bf451-175">Set a breakpoint on the curly brace that marks the start of the `Main` method (press <kbd>command</kbd>+<kbd>\\</kbd>).</span></span>

1. <span data-ttu-id="bf451-176"><kbd>⌘</kbd><kbd>↵</kbd>(<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 디버깅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-176">Press <kbd>⌘</kbd><kbd>↵</kbd> (<kbd>command</kbd>+<kbd>enter</kbd>) to start debugging.</span></span>

   <span data-ttu-id="bf451-177">Visual Studio는 중단점이 있는 줄에서 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-177">Visual Studio stops on the line with the breakpoint.</span></span>

1. <span data-ttu-id="bf451-178"><kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>)를 누르거나 **실행** > **한 단계씩 코드 실행**을 선택하여 한 줄씩 진행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-178">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>) or select **Run** > **Step Into** to advance one line.</span></span>

   <span data-ttu-id="bf451-179">Visual Studio에서 다음에 실행될 줄을 강조 표시하고 옆에 화살표를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-179">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/step-into-method.png" alt-text="Visual Studio 한 단계씩 코드 실행 메서드":::

   <span data-ttu-id="bf451-181">이 시점에서 **지역** 창에는 `args` 배열이 비어 있다고 표시되고, `name` 및 `date`에는 기본값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-181">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="bf451-182">또한 Visual Studio에서는 빈 터미널이 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-182">In addition, Visual Studio has opened a blank terminal.</span></span>

1. <span data-ttu-id="bf451-183"><kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>)를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-183">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="bf451-184">Visual Studio는 `name` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-184">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="bf451-185">**로컬** 창에서는 `name`이 `null`로 표시되고 터미널에서는 문자열 "What is your name?"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-185">The **Locals** window shows that `name` is `null`, and the terminal displays the string "What is your name?".</span></span>

1. <span data-ttu-id="bf451-186">콘솔 창에 문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-186">Respond to the prompt by entering a string in the console window and pressing <kbd>enter</kbd>.</span></span>

1. <span data-ttu-id="bf451-187"><kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>)를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-187">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="bf451-188">Visual Studio는 `date` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-188">Visual Studio highlights the statement that includes the `date` variable assignment.</span></span> <span data-ttu-id="bf451-189">**지역** 창에는 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드 호출에 의해 반환된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-189">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bf451-190">터미널에는 프롬프트에 입력한 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-190">The terminal displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="bf451-191"><kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>)를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-191">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="bf451-192">**지역** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성에 따라 할당된 이후의 `date` 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-192">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="bf451-193">터미널은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-193">The terminal is unchanged.</span></span>

1. <span data-ttu-id="bf451-194"><kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd>(<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>)를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-194">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>I</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>I</kbd>).</span></span>

   <span data-ttu-id="bf451-195">Visual Studio에서 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-195">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="bf451-196">터미널에는 서식이 지정된 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-196">The terminal displays the formatted string.</span></span>

1. <span data-ttu-id="bf451-197"><kbd>⇧</kbd><kbd>⌘</kbd><kbd>U</kbd>(<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>U</kbd>)를 누르거나 **실행** > **프로시저 나가기**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-197">Press <kbd>⇧</kbd><kbd>⌘</kbd><kbd>U</kbd> (<kbd>shift</kbd>+<kbd>command</kbd>+<kbd>U</kbd>) or select **Run** > **Step Out**.</span></span>

   <span data-ttu-id="bf451-198">터미널은 메시지를 표시하고 사용자가 키를 누르기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-198">The terminal displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="bf451-199">아무 키나 눌러 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-199">Press any key to exit the program.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="bf451-200">릴리스 빌드 구성 사용</span><span class="sxs-lookup"><span data-stu-id="bf451-200">Use Release build configuration</span></span>

<span data-ttu-id="bf451-201">애플리케이션의 디버그 버전을 테스트한 후에는 릴리스 버전을 컴파일하고 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-201">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="bf451-202">릴리스 버전에는 애플리케이션의 동작에 부정적인 영향을 줄 수 있는 컴파일러 최적화가 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-202">The Release version incorporates compiler optimizations that can negatively affect the behavior of an application.</span></span> <span data-ttu-id="bf451-203">예를 들어 성능 향상을 위해 설계된 컴파일러 최적화는 다중 스레드 애플리케이션에서 경합 상태를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-203">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="bf451-204">콘솔 애플리케이션의 릴리스 버전을 빌드하고 테스트하려면 다음 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-204">To build and test the Release version of the console application, do the following steps:</span></span>

1. <span data-ttu-id="bf451-205">도구 모음의 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-205">Change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-mac/visual-studio-toolbar-release.png" alt-text="디버그가 강조 표시된 기본 Visual Studio 도구 모음":::

1. <span data-ttu-id="bf451-207"><kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>)를 눌러 디버그 없이 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-207">Press <kbd>⌥</kbd><kbd>⌘</kbd><kbd>↵</kbd> (<kbd>option</kbd>+<kbd>command</kbd>+<kbd>enter</kbd>) to run without debugging.</span></span>

## <a name="next-steps"></a><span data-ttu-id="bf451-208">다음 단계</span><span class="sxs-lookup"><span data-stu-id="bf451-208">Next steps</span></span>

<span data-ttu-id="bf451-209">이 자습서에서는 Visual Studio 디버깅 도구를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-209">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="bf451-210">다음 자습서에서는 앱의 배포 가능 버전을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="bf451-210">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="bf451-211">Mac용 Visual Studio로 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="bf451-211">Publish a .NET Core console application with Visual Studio for Mac</span></span>](publishing-with-visual-studio-mac.md)
