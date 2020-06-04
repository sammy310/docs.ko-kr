---
title: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 디버그
description: Visual Studio를 사용하여 .NET Core 콘솔 앱을 디버그하는 방법을 알아봅니다.
ms.date: 05/20/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4bd2a8a0e4b3cea55e209306dd3788552e4b61f3
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84005416"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="f5b36-103">자습서: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="f5b36-103">Tutorial: Debug a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="f5b36-104">이 자습서에서는 Visual Studio에서 사용할 수 있는 디버깅 도구를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="f5b36-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="f5b36-105">Prerequisites</span></span>

- <span data-ttu-id="f5b36-106">이 자습서는 [Visual Studio 2019에서 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)에서 만든 콘솔 앱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-106">This tutorial works with the console app that you create in [Create a .NET Core console application in Visual Studio 2019](with-visual-studio.md).</span></span>

## <a name="debug-build-configuration"></a><span data-ttu-id="f5b36-107">디버그 빌드 구성</span><span class="sxs-lookup"><span data-stu-id="f5b36-107">Debug build configuration</span></span>

<span data-ttu-id="f5b36-108">*디버그* 및 *릴리스*는 Visual Studio의 기본 빌드 구성 중 두 개입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-108">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="f5b36-109">현재 빌드 구성은 도구 모음에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-109">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="f5b36-110">다음 도구 모음 그림은 Visual Studio가 앱의 디버그 버전을 컴파일하도록 구성되어 있음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-110">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

![디버그가 강조 표시된 Visual Studio 도구 모음](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

<span data-ttu-id="f5b36-112">앱의 디버그 버전을 실행하여 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-112">Begin by running the Debug version of the app.</span></span> <span data-ttu-id="f5b36-113">디버그 빌드 구성은 대부분의 컴파일러 최적화를 끄고 빌드 프로세스 중 보다 다양한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-113">The Debug build configuration turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="f5b36-114">중단점 설정</span><span class="sxs-lookup"><span data-stu-id="f5b36-114">Set a breakpoint</span></span>

<!-- markdownlint-disable MD025 -->

1. <span data-ttu-id="f5b36-115">이름, 날짜, 시간을 표시하는 줄에서 코드 창 왼쪽 여백을 클릭하여 해당 줄에 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-115">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="f5b36-116">중단점을 설정하는 또 다른 방법은 코드 줄에 커서를 배치한 다음 **F9** 키를 누르거나 메뉴 모음에서 **디버그** > **중단점 설정/해제**를 선택하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-116">Another way to set a breakpoint is by placing the cursor in the line of code and then pressing **F9** or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="f5b36-117">중단점은 중단점이 설정된 줄이 실행되기 *전에* 애플리케이션 실행을 일시적으로 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-117">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="f5b36-118">다음 이미지에서 볼 수 있듯이 Visual Studio는 중단점이 설정된 줄을 강조 표시하고 왼쪽 여백에 빨간 점을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-118">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   ![중단점이 설정된 Visual Studio 프로그램 창](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="f5b36-120">도구 모음에서 녹색 화살표가 있는 **HelloWorld** 단추를 선택하여 디버그 모드에서 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-120">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar.</span></span> <span data-ttu-id="f5b36-121">디버깅을 시작하는 다른 방법은 **F5** 키를 누르거나 **디버그** > **디버깅 시작**을 선택하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-121">Other ways to start debugging are by pressing **F5** or by choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="f5b36-122">프로그램 이름을 입력하라는 메시지가 표시되면 콘솔 창에 문자열을 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-122">Enter a string in the console window when the program prompts for a name, and then press **Enter**.</span></span>

1. <span data-ttu-id="f5b36-123">중단점에 도달할 때와 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-123">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="f5b36-124">**지역** 창에는 현재 실행 중인 메서드에 정의된 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-124">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Visual Studio의 중단점 스크린샷](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. <span data-ttu-id="f5b36-126">**직접 실행 창**에서는 디버그하는 애플리케이션을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-126">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="f5b36-127">대화형으로 변수 값을 변경하여 프로그램에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-127">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="f5b36-128">**직접 실행 창**이 표시되지 않는 경우 **디버그** > **창** > **직접 실행**을 선택하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-128">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="f5b36-129">**직접 실행 창**에 `name = "Gracie"`를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-129">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="f5b36-130">**직접 실행 창**에 `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()`를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-130">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="f5b36-131">**직접 실행 창**에는 문자열 변수의 값과 <xref:System.DateTime> 값의 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-131">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="f5b36-132">또한 변수 값이 **지역** 창에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-132">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Visual Studio 2019의 지역 및 직접 실행 창](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="f5b36-134">도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-134">Continue program execution by selecting the **Continue** button in the toolbar.</span></span> <span data-ttu-id="f5b36-135">계속하는 또 다른 방법은 **디버그** > **계속**을 선택하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-135">Another way to continue is by choosing **Debug** > **Continue**.</span></span>

   <span data-ttu-id="f5b36-136">콘솔 창에 표시되는 값은 **직접 실행 창**에서 변경한 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-136">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![입력한 값을 보여주는 콘솔 창](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="f5b36-138">아무 키나 눌러 애플리케이션을 종료하고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-138">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="f5b36-139">조건부 중단점 설정</span><span class="sxs-lookup"><span data-stu-id="f5b36-139">Set a conditional breakpoint</span></span>

<span data-ttu-id="f5b36-140">프로그램은 사용자가 입력하는 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-140">The program displays the string that the user enters.</span></span> <span data-ttu-id="f5b36-141">사용자가 아무 값도 입력하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="f5b36-141">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="f5b36-142">하나 이상의 조건이 충족될 경우 프로그램 실행을 중단하는 유용한 디버깅 기능인 *조건부 중단점*을 사용하여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-142">You can test this with a useful debugging feature called a *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="f5b36-143">조건부 중단점을 설정하고 사용자가 문자열을 입력하지 못한 경우에 발생하는 상황을 테스트하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-143">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

1. <span data-ttu-id="f5b36-144">중단점을 나타내는 빨간색 점을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-144">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="f5b36-145">상황에 맞는 메뉴에서 **조건**을 선택하여 **중단점 설정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-145">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="f5b36-146">아직 선택하지 않은 경우 **조건** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-146">Select the box for **Conditions** if it's not already selected.</span></span>

   ![중단점 설정 패널을 보여 주는 편집기 - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="f5b36-148">**조건식**의 경우 `x`가 5인지 테스트하는 예제 코드를 보여 주는 필드에 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-148">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="f5b36-149">사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-149">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="f5b36-150">디버거는 중단점이 적중될 때마다 `String.IsNullOrEmpty(name)` 메서드를 호출하고, 메서드 호출이 `true`를 반환하는 경우에만 이 줄에서 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-150">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="f5b36-151">조건식 대신 문이 실행되기 전에 프로그램 실행을 중단하는 적중 횟수 또는 스레드 식별자, 프로세스 이름 또는 스레드 이름과 같은 특성을 기준으로 프로그램 실행을 중단하는 필터 조건을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-151">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="f5b36-152">**닫기**를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-152">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="f5b36-153">**F5** 키를 눌러 디버깅으로 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-153">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="f5b36-154">콘솔 창에 이름을 입력하라는 메시지가 나타나면 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-154">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="f5b36-155">`name`이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>이라는 지정한 조건이 충족되었으므로 중단점에 도달한 후 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-155">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="f5b36-156">**지역** 창을 선택합니다. 이 창에는 현재 실행 중인 메서드에 로컬인 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-156">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="f5b36-157">이 경우 `Main`은 현재 실행 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-157">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="f5b36-158">`name` 변수의 값은 `""` 또는 <xref:System.String.Empty?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-158">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="f5b36-159">**직접 실행 창**에 다음 문을 입력하고 **Enter**를 눌러 값이 빈 문자열인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-159">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="f5b36-160">결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-160">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="f5b36-161">물음표는 직접 실행 창에서 [식을 계산](/visualstudio/ide/reference/immediate-window#enter-commands)하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-161">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   ![문이 실행된 후 true 값을 반환하는 직접 실행 창 - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="f5b36-163">도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-163">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="f5b36-164">아무 키나 눌러 콘솔 창을 닫고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-164">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="f5b36-165">코드 창 왼쪽 여백에 있는 점을 클릭하여 중단점을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-165">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="f5b36-166">중단점을 지우는 또 다른 방법은 코드 줄이 선택되어 있는 동안 **디버그 > 중단점 설정/해제**를 선택하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-166">Another way to clear a breakpoint is by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="f5b36-167">단계별 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="f5b36-167">Step through a program</span></span>

<span data-ttu-id="f5b36-168">Visual Studio에서 프로그램을 한 줄씩 단계별로 실행하고 해당 실행을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-168">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="f5b36-169">일반적으로 중단점을 설정하고 프로그램 코드 일부의 프로그램 흐름을 따라가면서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-169">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="f5b36-170">여기서는 프로그램이 작으므로 전체 프로그램을 단계별로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-170">Since your program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="f5b36-171">**디버그** > **한 단계씩 코드 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-171">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="f5b36-172">한 번에 하나의 문을 디버그하는 또 다른 방법은 **F11** 키를 누르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-172">Another way to debug one statement at a time is by pressing **F11**.</span></span>

   <span data-ttu-id="f5b36-173">Visual Studio에서 다음에 실행될 줄을 강조 표시하고 옆에 화살표를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-173">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="f5b36-174">C#</span><span class="sxs-lookup"><span data-stu-id="f5b36-174">C#</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 - C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="f5b36-176">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5b36-176">Visual Basic</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="f5b36-178">이 시점에서 **지역** 창에는 `args` 배열이 비어 있다고 표시되고, `name` 및 `date`에는 기본값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-178">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="f5b36-179">또한 Visual Studio에서는 빈 콘솔 창이 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-179">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="f5b36-180">**F11** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-180">Press **F11**.</span></span> <span data-ttu-id="f5b36-181">이제 Visual Studio에서 다음에 실행될 줄을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-181">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="f5b36-182">**지역** 창은 변경되지 않으며, 콘솔 창은 계속 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-182">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="f5b36-183">C#</span><span class="sxs-lookup"><span data-stu-id="f5b36-183">C#</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 소스 - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

   <span data-ttu-id="f5b36-185">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f5b36-185">Visual Basic</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 소스 - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="f5b36-187">**F11** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-187">Press **F11**.</span></span> <span data-ttu-id="f5b36-188">Visual Studio는 `name` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-188">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="f5b36-189">**지역** 창에서는 `name`이 `null`로 표시되고 콘솔 창에서는 문자열 "What is your name?"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-189">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="f5b36-190">콘솔 창에 문자열을 입력하고 **Enter** 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-190">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="f5b36-191">콘솔은 응답하지 않게 되고 입력한 문자열이 콘솔 창에 표시되지 않지만 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드는 사용자의 입력을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-191">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="f5b36-192">**F11** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-192">Press **F11**.</span></span> <span data-ttu-id="f5b36-193">Visual Studio는 `date` 변수 할당(Visual Basic에서는 `currentDate`)을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-193">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="f5b36-194">**지역** 창에는 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드 호출에 의해 반환된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-194">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f5b36-195">콘솔 창에는 프롬프트에 입력한 문자열도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-195">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="f5b36-196">**F11** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-196">Press **F11**.</span></span> <span data-ttu-id="f5b36-197">**지역** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성에 따라 할당된 이후의 `date` 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-197">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="f5b36-198">콘솔 창은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-198">The console window is unchanged.</span></span>

1. <span data-ttu-id="f5b36-199">**F11** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-199">Press **F11**.</span></span> <span data-ttu-id="f5b36-200">Visual Studio에서 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-200">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="f5b36-201">콘솔 창에는 서식이 지정된 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-201">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="f5b36-202">**디버그** > **프로시저 나가기**를 선택합니다. 단계별 실행을 중지하는 또 다른 방법은 **Shift**+**F11** 키를 누르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-202">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing **Shift**+**F11**.</span></span>

   <span data-ttu-id="f5b36-203">콘솔 창은 메시지를 표시하고 사용자가 키를 누르기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-203">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="f5b36-204">아무 키나 눌러 콘솔 창을 닫고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-204">Press any key to close the console window and stop debugging.</span></span>

## <a name="build-a-release-version"></a><span data-ttu-id="f5b36-205">릴리스 버전 빌드</span><span class="sxs-lookup"><span data-stu-id="f5b36-205">Build a Release version</span></span>

<span data-ttu-id="f5b36-206">애플리케이션의 디버그 버전을 테스트한 후에는 릴리스 버전을 컴파일하고 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-206">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="f5b36-207">릴리스 버전에는 애플리케이션의 동작에 부정적인 영향을 줄 수 있는 컴파일러 최적화가 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-207">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="f5b36-208">예를 들어 성능 향상을 위해 설계된 컴파일러 최적화는 다중 스레드 애플리케이션에서 경합 상태를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-208">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="f5b36-209">콘솔 애플리케이션의 릴리스 버전을 빌드하고 테스트하려면 도구 모음에서 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-209">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![디버그가 강조 표시된 기본 Visual Studio 도구 모음](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="f5b36-211">**F5** 키를 누르거나 **빌드** 메뉴에서 **솔루션 빌드**를 선택하면 Visual Studio에서 애플리케이션의 릴리스 버전을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-211">When you press **F5** or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="f5b36-212">디버그 버전처럼 릴리스 버전을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-212">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f5b36-213">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f5b36-213">Next steps</span></span>

<span data-ttu-id="f5b36-214">이 자습서에서는 Visual Studio 디버깅 도구를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-214">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="f5b36-215">다음 자습서에서는 앱의 배포 가능 버전을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="f5b36-215">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="f5b36-216">Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="f5b36-216">Publish a .NET Core console application with Visual Studio</span></span>](publishing-with-visual-studio.md)
