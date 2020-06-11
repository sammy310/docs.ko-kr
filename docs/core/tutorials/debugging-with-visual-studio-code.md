---
title: Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 디버그
description: Visual Studio Code를 사용하여 .NET Core 콘솔 앱을 디버그하는 방법을 알아봅니다.
ms.date: 05/26/2020
ms.openlocfilehash: 82b2798397d702aa2a50c04bf6e4d569b97e3666
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241515"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio-code"></a><span data-ttu-id="60b8b-103">자습서: Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="60b8b-103">Tutorial: Debug a .NET Core console application using Visual Studio Code</span></span>

<span data-ttu-id="60b8b-104">이 자습서에서는 .NET Core 앱 작업을 하는 데 Visual Studio Code에서 사용할 수 있는 디버깅 도구를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-104">This tutorial introduces the debugging tools available in Visual Studio Code for working with .NET Core apps.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="60b8b-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="60b8b-105">Prerequisites</span></span>

- <span data-ttu-id="60b8b-106">이 자습서는 [Visual Studio Code에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio-code.md)에서 만든 콘솔 앱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="60b8b-107">디버그 빌드 구성 사용</span><span class="sxs-lookup"><span data-stu-id="60b8b-107">Use Debug build configuration</span></span>

<span data-ttu-id="60b8b-108">‘디버그’ 및 ‘릴리스’는 .NET Core의 빌드 구성 중 두 가지입니다. </span><span class="sxs-lookup"><span data-stu-id="60b8b-108">*Debug* and *Release* are two of .NET Core's build configurations.</span></span> <span data-ttu-id="60b8b-109">디버그 빌드 구성은 디버깅에 사용하고, 릴리스 구성은 최종 릴리스 배포에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="60b8b-110">디버그 구성에서 프로그램은 완전히 기호화된 디버그 정보를 사용하여 컴파일되며 최적화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="60b8b-111">최적화하면 소스 코드와 생성된 명령 간의 관계가 복잡해지므로 디버깅이 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="60b8b-112">프로그램의 릴리스 구성은 완전히 최적화되고, 기호화된 디버그 정보를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

 <span data-ttu-id="60b8b-113">기본적으로 Visual Studio Code는 디버그 빌드 구성을 사용하므로 디버깅 전에 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-113">By default, Visual Studio Code uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="60b8b-114">중단점 설정</span><span class="sxs-lookup"><span data-stu-id="60b8b-114">Set a breakpoint</span></span>

<span data-ttu-id="60b8b-115">중단점은 중단점이 설정된 줄이 실행되기 *전에* 애플리케이션 실행을 일시적으로 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-115">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="60b8b-116">Visual Studio Code를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-116">Open Visual Studio Code.</span></span>

1. <span data-ttu-id="60b8b-117">[Visual Studio Code에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio-code.md)에서 만든 *HelloWorld* 프로젝트 폴더를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-117">Open the *HelloWorld* project folder that you created in [Create a .NET Core console application in Visual Studio Code](with-visual-studio-code.md).</span></span>

1. <span data-ttu-id="60b8b-118">*Program.cs* 파일을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-118">Open the *Program.cs* file.</span></span>

1. <span data-ttu-id="60b8b-119">이름, 날짜, 시간을 표시하는 줄에서 코드 창 왼쪽 여백을 클릭하여 ‘중단점’을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-119">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window.</span></span> <span data-ttu-id="60b8b-120">왼쪽 여백은 줄 번호의 왼쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-120">The left margin is to the left of the line numbers.</span></span> <span data-ttu-id="60b8b-121">중단점을 설정하는 또 다른 방법은 코드 줄에 커서를 배치한 다음 <kbd>F9</kbd> 키를 누르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-121">Another way to set a breakpoint is by placing the cursor in the line of code and then pressing <kbd>F9</kbd>.</span></span>

   <span data-ttu-id="60b8b-122">다음 이미지에서 볼 수 있듯이 Visual Studio Code에서는 왼쪽 여백에 빨간 점을 표시하여 중단점이 설정된 줄을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-122">As the following image shows, Visual Studio Code indicates the line on which the breakpoint is set by displaying a red dot in the left margin.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-set.png" alt-text="중단점 설정":::

## <a name="set-up-for-terminal-input"></a><span data-ttu-id="60b8b-124">터미널 입력에 대해 설정</span><span class="sxs-lookup"><span data-stu-id="60b8b-124">Set up for terminal input</span></span>

<span data-ttu-id="60b8b-125">중단점은 `Console.ReadLine` 메서드 호출 뒤에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-125">The breakpoint is located after a `Console.ReadLine` method call.</span></span> <span data-ttu-id="60b8b-126">**디버그 콘솔**은 실행 중인 프로그램에 대한 터미널 입력을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-126">The **Debug Console** doesn't accept terminal input for a running program.</span></span> <span data-ttu-id="60b8b-127">디버깅 중에 터미널 입력을 처리하기 위해 통합 터미널(Visual Studio Code 창 중 하나) 또는 외부 터미널을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-127">To handle terminal input while debugging, you can use the integrated terminal (one of the Visual Studio Code windows) or an external terminal.</span></span> <span data-ttu-id="60b8b-128">이 자습서에서는 통합 터미널을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-128">For this tutorial, you use the integrated terminal.</span></span>

1. <span data-ttu-id="60b8b-129">*.vscode/launch.json*을 엽니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-129">Open *.vscode/launch.json*.</span></span>

1. <span data-ttu-id="60b8b-130">`console` 설정을 `integratedTerminal`로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-130">Change the `console` setting to `integratedTerminal`.</span></span>

   <span data-ttu-id="60b8b-131">원본:</span><span class="sxs-lookup"><span data-stu-id="60b8b-131">From:</span></span>

   ```
   "console": "internalConsole",
   ```

   <span data-ttu-id="60b8b-132">대상:</span><span class="sxs-lookup"><span data-stu-id="60b8b-132">To:</span></span>

   ```
   "console": "integratedTerminal",
   ```

1. <span data-ttu-id="60b8b-133">변경 내용을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-133">Save your changes.</span></span>

## <a name="start-debugging"></a><span data-ttu-id="60b8b-134">디버깅 시작</span><span class="sxs-lookup"><span data-stu-id="60b8b-134">Start debugging</span></span>

1. <span data-ttu-id="60b8b-135">왼쪽 메뉴에서 디버깅 아이콘을 선택하여 디버그 보기를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-135">Open the Debug view by selecting the Debugging icon on the left side menu.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-debug-pane.png" alt-text="Visual Studio Code에서 디버그 탭 열기":::

1. <span data-ttu-id="60b8b-137">**.NET Core 시작(콘솔)** 옆에 있는 창 맨 위의 녹색 화살표를 선택하여 디버깅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-137">Start debugging by selecting the green arrow at the top of the pane, next to **.NET Core Launch (console)**.</span></span>  <span data-ttu-id="60b8b-138">디버깅을 시작하는 또 다른 방법은 <kbd>F5</kbd> 키를 누르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-138">Another way to start debugging is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/start-debugging.png" alt-text="디버깅 시작":::

1. <span data-ttu-id="60b8b-140">**터미널** 탭을 선택하여 응답을 기다리기 전에</span><span class="sxs-lookup"><span data-stu-id="60b8b-140">Select the **Terminal** tab to see the "What is your name?"</span></span> <span data-ttu-id="60b8b-141">프로그램이 표시하는 "What is your name?" 프롬프트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-141">prompt that the program displays before waiting for a response.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/select-terminal.png" alt-text="터미널 탭 선택":::

1. <span data-ttu-id="60b8b-143">이름을 묻는 프롬프트에 대한 응답으로 **터미널** 창에 문자열을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-143">Enter a string in the **Terminal** window in response to the prompt for a name, and then press <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="60b8b-144">중단점에 도달할 때와 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-144">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="60b8b-145">**변수** 창의 **지역** 섹션에는 현재 실행 중인 메서드에 정의된 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-145">The **Locals** section of the **Variables** window displays the values of variables that are defined in the currently executing method.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-hit.png" alt-text="중단점 적중, 지역 표시":::

## <a name="change-variable-values"></a><span data-ttu-id="60b8b-147">변수 값 변경</span><span class="sxs-lookup"><span data-stu-id="60b8b-147">Change variable values</span></span>

<span data-ttu-id="60b8b-148">**디버그 콘솔** 창을 통해 디버그하는 애플리케이션과 상호 작용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-148">The **Debug Console** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="60b8b-149">변수 값을 변경하여 프로그램에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-149">You can change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="60b8b-150">**디버그 콘솔** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-150">Select the **Debug Console** tab.</span></span>

1. <span data-ttu-id="60b8b-151">**디버그 콘솔** 창의 맨 아래에 있는 프롬프트에 `name = "Gracie"`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-151">Enter `name = "Gracie"` at the prompt at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/change-variable-values.png" alt-text="변수 값 변경":::

1. <span data-ttu-id="60b8b-153">**디버그 콘솔** 창의 맨 아래에 `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()`을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-153">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` at the bottom of the **Debug Console** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="60b8b-154">**변수** 창에 `name` 및 `date` 변수의 새 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-154">The **Variables** window displays the new values of the `name` and `date` variables.</span></span>

1. <span data-ttu-id="60b8b-155">도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-155">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="60b8b-156"><kbd>F5</kbd> 키를 눌러도 계속 진행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-156">Another way to continue is by pressing <kbd>F5</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/continue-debugging.png" alt-text="디버깅 계속":::

1. <span data-ttu-id="60b8b-158">**터미널** 탭을 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-158">Select the **Terminal** tab again.</span></span>

   <span data-ttu-id="60b8b-159">콘솔 창에 표시되는 값은 **디버그 콘솔**에서 변경한 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-159">The values displayed in the console window correspond to the changes you made in the **Debug Console**.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/changed-variable-values.png" alt-text="입력한 값을 보여 주는 터미널":::

1. <span data-ttu-id="60b8b-161">아무 키나 눌러 애플리케이션을 종료하고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-161">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="60b8b-162">조건부 중단점 설정</span><span class="sxs-lookup"><span data-stu-id="60b8b-162">Set a conditional breakpoint</span></span>

<span data-ttu-id="60b8b-163">프로그램은 사용자가 입력하는 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-163">The program displays the string that the user enters.</span></span> <span data-ttu-id="60b8b-164">사용자가 아무 값도 입력하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="60b8b-164">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="60b8b-165">*조건부 중단점*이라는 유용한 디버깅 기능을 사용하여 이를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-165">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="60b8b-166">중단점을 나타내는 빨간색 점을 마우스 오른쪽 단추로 클릭합니다(macOS에서는 <kbd>Ctrl</kbd>+클릭).</span><span class="sxs-lookup"><span data-stu-id="60b8b-166">Right-click (<kbd>Ctrl</kbd>+click on macOS) on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="60b8b-167">상황에 맞는 메뉴에서 **중단점 편집**을 선택하면 조건식을 입력할 수 있는 대화 상자가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-167">In the context menu, select **Edit Breakpoint** to open a dialog that lets you enter a conditional expression.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/breakpoint-context-menu.png" alt-text="중단점 상황에 맞는 메뉴":::

1. <span data-ttu-id="60b8b-169">드롭다운에서 `Expression`을 선택하고 다음 조건식을 입력한 후 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-169">Select `Expression` in the drop-down, enter the following conditional expression, and press <kbd>Enter</kbd>.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/conditional-expression.png" alt-text="조건식 입력":::

   <span data-ttu-id="60b8b-171">디버거는 중단점이 적중될 때마다 `String.IsNullOrEmpty(name)` 메서드를 호출하고, 메서드 호출이 `true`를 반환하는 경우에만 이 줄에서 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-171">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="60b8b-172">조건식 대신 문이 실행되기 전에 프로그램 실행을 중단하는 적중 횟수 또는 스레드 식별자, 프로세스 이름 또는 스레드 이름과 같은 특성을 기준으로 프로그램 실행을 중단하는 필터 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-172">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="60b8b-173"><kbd>F5</kbd> 키를 눌러 디버깅으로 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-173">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="60b8b-174">**터미널** 탭에서 이름을 입력하라는 메시지가 나타나면 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-174">In the **Terminal** tab, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

   <span data-ttu-id="60b8b-175">`name`이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>이라는 지정한 조건이 충족되었으므로 중단점에 도달한 후 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-175">Because the condition you specified (`name` is `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

   <span data-ttu-id="60b8b-176">**변수** 창에 `name` 변수 값이 `""` 또는 <xref:System.String.Empty?displayProperty=nameWithType>임이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-176">The **Variables** window shows that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="60b8b-177">**디버그 콘솔** 프롬프트에 다음 문을 입력하고 <kbd>Enter</kbd> 키를 눌러 값이 빈 문자열인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-177">Confirm the value is an empty string by entering the following statement at the **Debug Console** prompt and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="60b8b-178">결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-178">The result is `true`.</span></span>

   ```csharp
   name == String.Empty
   ```

   :::image type="content" source="media/debugging-with-visual-studio-code/expression-in-debug-console.png" alt-text="문이 실행된 후 true 값을 반환하는 디버그 콘솔":::

1. <span data-ttu-id="60b8b-180">도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-180">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="60b8b-181">**터미널** 탭을 선택하고 아무 키나 눌러 프로그램을 종료하고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-181">Select the **Terminal** tab, and press any key to exit the program and stop debugging.</span></span>

1. <span data-ttu-id="60b8b-182">코드 창 왼쪽 여백에 있는 점을 클릭하여 중단점을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-182">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="60b8b-183">중단점을 지우는 또 다른 방법은 코드 줄이 선택되어 있는 동안 <kbd>F9</kbd> 키를 누르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-183">Another way to clear a breakpoint is by pressing <kbd>F9</kbd> while the line of code is selected.</span></span>

1. <span data-ttu-id="60b8b-184">중단점 조건이 손실된다는 경고가 표시되면 **중단점 제거**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-184">If you get a warning that the breakpoint condition will be lost, select **Remove Breakpoint**.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="60b8b-185">단계별 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="60b8b-185">Step through a program</span></span>

<span data-ttu-id="60b8b-186">Visual Studio Code에서 프로그램을 한 줄씩 단계별로 실행하고 해당 실행을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-186">Visual Studio Code also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="60b8b-187">일반적으로 중단점을 설정하고 프로그램 코드 일부의 프로그램 흐름을 따라가면서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-187">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="60b8b-188">이 프로그램은 작으므로 전체 프로그램을 단계별로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-188">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="60b8b-189">`Main` 메서드의 여는 중괄호에 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-189">Set a breakpoint on the opening curly brace of the `Main` method.</span></span>

1. <span data-ttu-id="60b8b-190"><kbd>F5</kbd> 키를 눌러 디버깅을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-190">Press <kbd>F5</kbd> to start debugging.</span></span>

   <span data-ttu-id="60b8b-191">Visual Studio Code가 중단점 줄을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-191">Visual Studio Code highlights the breakpoint line.</span></span>

   <span data-ttu-id="60b8b-192">이 시점에서 **변수** 창에는 `args` 배열이 비어 있다고 표시되고, `name` 및 `date`에는 기본값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-192">At this point, the **Variables** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span>

1. <span data-ttu-id="60b8b-193">**한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-193">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-into.png" alt-text="한 단계씩 코드 실행 단추":::

   <span data-ttu-id="60b8b-195">Visual Studio Code가 다음 줄을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-195">Visual Studio Code highlights the next line.</span></span>

1. <span data-ttu-id="60b8b-196">**한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-196">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="60b8b-197">Visual Studio Code가 이름 프롬프트에 대해 `Console.WriteLine`을 실행하고 다음에 실행할 줄을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-197">Visual Studio Code executes the `Console.WriteLine` for the name prompt and highlights the next line of execution.</span></span> <span data-ttu-id="60b8b-198">다음 줄은 `name`의 `Console.ReadLine`입니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-198">The next line is the `Console.ReadLine` for the `name`.</span></span> <span data-ttu-id="60b8b-199">**변수** 창은 변경되지 않으며, **터미널** 탭에는 "What is your name?" 프롬프트가</span><span class="sxs-lookup"><span data-stu-id="60b8b-199">The **Variables** window is unchanged, and the **Terminal** tab shows the "What is your name?"</span></span> <span data-ttu-id="60b8b-200">표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-200">prompt.</span></span>

1. <span data-ttu-id="60b8b-201">**한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-201">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="60b8b-202">Visual Studio가 `name` 변수 할당을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-202">Visual Studio highlights the `name` variable assignment.</span></span> <span data-ttu-id="60b8b-203">**변수** 창에 `name`이 여전히 `null`이라고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-203">The **Variables** window shows that `name` is still `null`.</span></span>

1. <span data-ttu-id="60b8b-204">터미널 탭에 문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-204">Respond to the prompt by entering a string in the Terminal tab and pressing <kbd>Enter</kbd>.</span></span>

   <span data-ttu-id="60b8b-205">문자열을 입력하는 동안 **터미널** 탭에 문자열이 표시되지 않을 수 있지만 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드는 입력을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-205">The **Terminal** tab might not display the string you enter while you're entering it, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will capture your input.</span></span>

1. <span data-ttu-id="60b8b-206">**한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-206">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="60b8b-207">Visual Studio Code가 `date` 변수 할당을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-207">Visual Studio Code highlights the `date` variable assignment.</span></span> <span data-ttu-id="60b8b-208">**변수** 창에는 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드 호출에 의해 반환된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-208">The **Variables** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="60b8b-209">**터미널** 탭에는 프롬프트에 입력한 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-209">The **Terminal** tab displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="60b8b-210">**한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-210">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="60b8b-211">**변수** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성에 따라 할당된 이후의 `date` 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-211">The **Variables** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span>

1. <span data-ttu-id="60b8b-212">**한 단계씩 코드 실행**을 선택하거나 <kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-212">Select **Step Into** or press <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="60b8b-213">Visual Studio Code가 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-213">Visual Studio Code calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="60b8b-214">콘솔 창에는 서식이 지정된 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-214">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="60b8b-215">**프로시저 나가기**를 선택하거나 <kbd>Shift</kbd>+<kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-215">Select **Step Out** or press <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   :::image type="content" source="media/debugging-with-visual-studio-code/step-out.png" alt-text="프로시저 나가기 단추":::

1. <span data-ttu-id="60b8b-217">**터미널** 탭을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-217">Select the **Terminal** tab.</span></span>

   <span data-ttu-id="60b8b-218">터미널에 "종료하려면 아무 키나 누르세요..."가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-218">The terminal displays "Press any key to exit..."</span></span>

1. <span data-ttu-id="60b8b-219">아무 키나 눌러 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-219">Press any key to exit the program.</span></span>

## <a name="select-release-build-configuration"></a><span data-ttu-id="60b8b-220">릴리스 빌드 구성 선택</span><span class="sxs-lookup"><span data-stu-id="60b8b-220">Select Release build configuration</span></span>

<span data-ttu-id="60b8b-221">애플리케이션의 디버그 버전을 테스트한 후에는 릴리스 버전을 컴파일하고 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-221">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="60b8b-222">릴리스 버전에는 애플리케이션의 동작에 영향을 줄 수 있는 컴파일러 최적화가 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-222">The Release version incorporates compiler optimizations that can affect the behavior of an application.</span></span> <span data-ttu-id="60b8b-223">예를 들어 성능 향상을 위해 설계된 컴파일러 최적화는 다중 스레드 애플리케이션에서 경합 상태를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-223">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="60b8b-224">콘솔 애플리케이션의 릴리스 버전을 빌드하고 테스트하려면 **터미널**을 열고 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-224">To build and test the Release version of your console application, open the **Terminal** and run the following command:</span></span>

```dotnetcli
dotnet run --configuration Release
```

## <a name="additional-resources"></a><span data-ttu-id="60b8b-225">추가 자료</span><span class="sxs-lookup"><span data-stu-id="60b8b-225">Additional resources</span></span>

* [<span data-ttu-id="60b8b-226">Visual Studio Code의 디버깅</span><span class="sxs-lookup"><span data-stu-id="60b8b-226">Debugging in Visual Studio Code</span></span>](https://code.visualstudio.com/docs/editor/debugging)

## <a name="next-steps"></a><span data-ttu-id="60b8b-227">다음 단계</span><span class="sxs-lookup"><span data-stu-id="60b8b-227">Next steps</span></span>

<span data-ttu-id="60b8b-228">이 자습서에서는 Visual Studio Code 디버깅 도구를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-228">In this tutorial, you used Visual Studio Code debugging tools.</span></span> <span data-ttu-id="60b8b-229">다음 자습서에서는 앱의 배포 가능 버전을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="60b8b-229">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="60b8b-230">Visual Studio Code를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="60b8b-230">Publish a .NET Core console application with Visual Studio Code</span></span>](publishing-with-visual-studio-code.md)
