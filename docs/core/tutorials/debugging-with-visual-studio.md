---
title: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 디버그
description: Visual Studio를 사용하여 .NET Core 콘솔 앱을 디버그하는 방법을 알아봅니다.
ms.date: 06/08/2020
dev_langs:
- csharp
- vb
ms.custom: vs-dotnet
ms.openlocfilehash: 4e408d5bd0976d88f368615860ac373142d0fe1e
ms.sourcegitcommit: 60dc0a11ebdd77f969f41891d5cca06335cda6a7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/27/2020
ms.locfileid: "88957227"
---
# <a name="tutorial-debug-a-net-core-console-application-using-visual-studio"></a><span data-ttu-id="d6372-103">자습서: Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="d6372-103">Tutorial: Debug a .NET Core console application using Visual Studio</span></span>

<span data-ttu-id="d6372-104">이 자습서에서는 Visual Studio에서 사용할 수 있는 디버깅 도구를 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-104">This tutorial introduces the debugging tools available in Visual Studio.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d6372-105">사전 요구 사항</span><span class="sxs-lookup"><span data-stu-id="d6372-105">Prerequisites</span></span>

- <span data-ttu-id="d6372-106">이 자습서는 [Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)에서 만든 콘솔 앱을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-106">This tutorial works with the console app that you create in [Create a .NET Core console application using Visual Studio](with-visual-studio.md).</span></span>

## <a name="use-debug-build-configuration"></a><span data-ttu-id="d6372-107">디버그 빌드 구성 사용</span><span class="sxs-lookup"><span data-stu-id="d6372-107">Use Debug build configuration</span></span>

<span data-ttu-id="d6372-108">디버그 및 릴리스는 Visual Studio의 기본 빌드 구성입니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-108">*Debug* and *Release* are Visual Studio's built-in build configurations.</span></span> <span data-ttu-id="d6372-109">디버그 빌드 구성은 디버깅에 사용하고, 릴리스 구성은 최종 릴리스 배포에 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-109">You use the Debug build configuration for debugging and the Release configuration for the final release distribution.</span></span>

<span data-ttu-id="d6372-110">디버그 구성에서 프로그램은 완전히 기호화된 디버그 정보를 사용하여 컴파일되며 최적화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-110">In the Debug configuration, a program compiles with full symbolic debug information and no optimization.</span></span> <span data-ttu-id="d6372-111">최적화하면 소스 코드와 생성된 명령 간의 관계가 복잡해지므로 디버깅이 복잡해집니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-111">Optimization complicates debugging, because the relationship between source code and generated instructions is more complex.</span></span> <span data-ttu-id="d6372-112">프로그램의 릴리스 구성은 완전히 최적화되고, 기호화된 디버그 정보를 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-112">The release configuration of a program has no symbolic debug information and is fully optimized.</span></span>

 <span data-ttu-id="d6372-113">기본적으로 Visual Studio는 디버그 빌드 구성을 사용하므로 디버깅 전에 변경할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-113">By default, Visual Studio uses the Debug build configuration, so you don't need to change it before debugging.</span></span>

1. <span data-ttu-id="d6372-114">Visual Studio를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-114">Start Visual Studio.</span></span>

1. <span data-ttu-id="d6372-115">[Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)에서 만든 프로젝트를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-115">Open the project that you created in [Create a .NET Core console application using Visual Studio](with-visual-studio.md).</span></span>

   <span data-ttu-id="d6372-116">현재 빌드 구성은 도구 모음에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-116">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="d6372-117">다음 도구 모음 그림은 Visual Studio가 앱의 디버그 버전을 컴파일하도록 구성되어 있음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-117">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

   ![디버그가 강조 표시된 Visual Studio 도구 모음](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

## <a name="set-a-breakpoint"></a><span data-ttu-id="d6372-119">중단점 설정</span><span class="sxs-lookup"><span data-stu-id="d6372-119">Set a breakpoint</span></span>

<span data-ttu-id="d6372-120">중단점은 중단점이 설정된 줄이 실행되기 전에 애플리케이션 실행을 일시적으로 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-120">A *breakpoint* temporarily interrupts the execution of the application before the line with the breakpoint is executed.</span></span>

1. <span data-ttu-id="d6372-121">이름, 날짜, 시간을 표시하는 줄에서 코드 창 왼쪽 여백을 클릭하여 해당 줄에 중단점을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-121">Set a *breakpoint* on the line that displays the name, date, and time, by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="d6372-122">왼쪽 여백은 줄 번호의 왼쪽에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-122">The left margin is to the left of the line numbers.</span></span>  <span data-ttu-id="d6372-123">중단점을 설정하는 다른 방법은 코드 줄에 커서를 배치한 다음, <kbd>F9</kbd> 키를 누르거나 메뉴 모음에서 **디버그** > **중단점 설정/해제**를 선택하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-123">Other ways to set a breakpoint are by placing the cursor in the line of code and then pressing <kbd>F9</kbd> or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="d6372-124">다음 이미지에서 볼 수 있듯이 Visual Studio는 중단점이 설정된 줄을 강조 표시하고 왼쪽 여백에 빨간 점을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-124">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red dot in the left margin.</span></span>

   ![중단점이 설정된 Visual Studio 프로그램 창](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="d6372-126"><kbd>F5</kbd>를 눌러 디버그 모드에서 프로그램을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-126">Press <kbd>F5</kbd> to run the program in Debug mode.</span></span> <span data-ttu-id="d6372-127">메뉴에서 **디버그** > **디버깅 시작**을 선택하여 디버깅을 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-127">Another way to start debugging is by choosing **Debug** > **Start Debugging** from the menu.</span></span>

1. <span data-ttu-id="d6372-128">프로그램 이름을 입력하라는 메시지가 표시되면 콘솔 창에 문자열을 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-128">Enter a string in the console window when the program prompts for a name, and then press <kbd>Enter</kbd>.</span></span>

1. <span data-ttu-id="d6372-129">중단점에 도달할 때와 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-129">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="d6372-130">**지역** 창에는 현재 실행 중인 메서드에 정의된 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-130">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Visual Studio의 중단점 스크린샷](./media/debugging-with-visual-studio/breakpoint-hit.png)

## <a name="use-the-immediate-window"></a><span data-ttu-id="d6372-132">즉시 실행 창 사용</span><span class="sxs-lookup"><span data-stu-id="d6372-132">Use the Immediate window</span></span>

<span data-ttu-id="d6372-133">**직접 실행 창**에서는 디버그하는 애플리케이션을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-133">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="d6372-134">대화형으로 변수 값을 변경하여 프로그램에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-134">You can interactively change the value of variables to see how it affects your program.</span></span>

1. <span data-ttu-id="d6372-135">**직접 실행 창**이 표시되지 않는 경우 **디버그** > **창** > **직접 실행**을 선택하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-135">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

1. <span data-ttu-id="d6372-136">**직접 실행 창**에 `name = "Gracie"`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-136">Enter `name = "Gracie"` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

1. <span data-ttu-id="d6372-137">**직접 실행 창**에 `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()`를 입력하고 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-137">Enter `date = DateTime.Parse("2019-11-16T17:25:00Z").ToUniversalTime()` in the **Immediate** window and press the <kbd>Enter</kbd> key.</span></span>

   <span data-ttu-id="d6372-138">**직접 실행 창**에는 문자열 변수의 값과 <xref:System.DateTime> 값의 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-138">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="d6372-139">또한 변수 값이 **지역** 창에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-139">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Visual Studio 2019의 지역 및 직접 실행 창](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="d6372-141"><kbd>F5</kbd>를 눌러 프로그램을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-141">Press <kbd>F5</kbd> to continue program execution.</span></span> <span data-ttu-id="d6372-142">메뉴에서 **디버그** > **계속**을 선택해서 계속할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-142">Another way to continue is by choosing **Debug** > **Continue** from the menu.</span></span>

   <span data-ttu-id="d6372-143">콘솔 창에 표시되는 값은 **직접 실행 창**에서 변경한 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-143">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![입력한 값을 보여주는 콘솔 창](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="d6372-145">아무 키나 눌러 애플리케이션을 종료하고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-145">Press any key to exit the application and stop debugging.</span></span>

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="d6372-146">조건부 중단점 설정</span><span class="sxs-lookup"><span data-stu-id="d6372-146">Set a conditional breakpoint</span></span>

<span data-ttu-id="d6372-147">프로그램은 사용자가 입력하는 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-147">The program displays the string that the user enters.</span></span> <span data-ttu-id="d6372-148">사용자가 아무 값도 입력하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="d6372-148">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="d6372-149">*조건부 중단점*이라는 유용한 디버깅 기능을 사용하여 이를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-149">You can test this with a useful debugging feature called a *conditional breakpoint*.</span></span>

1. <span data-ttu-id="d6372-150">중단점을 나타내는 빨간색 점을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-150">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="d6372-151">상황에 맞는 메뉴에서 **조건**을 선택하여 **중단점 설정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-151">In the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="d6372-152">아직 선택하지 않은 경우 **조건** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-152">Select the box for **Conditions** if it's not already selected.</span></span>

   ![중단점 설정 패널을 보여 주는 편집기 - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="d6372-154">**조건식**의 경우 `x`가 5인지 테스트하는 예제 코드를 보여 주는 필드에 다음 코드를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-154">For the **Conditional Expression**, enter the following code in the field that shows example code that tests if `x` is 5.</span></span> <span data-ttu-id="d6372-155">사용하려는 언어가 표시되지 않으면 페이지 맨 위에 있는 언어 선택기를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-155">If the language you want to use is not shown, change the language selector at the top of the page.</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="d6372-156">디버거는 중단점이 적중될 때마다 `String.IsNullOrEmpty(name)` 메서드를 호출하고, 메서드 호출이 `true`를 반환하는 경우에만 이 줄에서 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-156">Each time the breakpoint is hit, the debugger calls the `String.IsNullOrEmpty(name)` method, and it breaks on this line only if the method call returns `true`.</span></span>

   <span data-ttu-id="d6372-157">조건식 대신 문이 지정된 횟수만큼 실행되기 전에 프로그램 실행을 중단하는 적중 횟수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-157">Instead of a conditional expression, you can specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times.</span></span> <span data-ttu-id="d6372-158">필터 조건을 지정할 수도 있으며, 이렇게 하면 스레드 식별자, 프로세스 이름 또는 스레드 이름과 같은 특성을 기준으로 프로그램 실행이 중단됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-158">Another option is to specify a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="d6372-159">**닫기**를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-159">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="d6372-160"><kbd>F5</kbd> 키를 눌러 디버깅으로 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-160">Start the program with debugging by pressing <kbd>F5</kbd>.</span></span>

1. <span data-ttu-id="d6372-161">콘솔 창에 이름을 입력하라는 메시지가 나타나면 <kbd>Enter</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-161">In the console window, press the <kbd>Enter</kbd> key when prompted to enter your name.</span></span>

1. <span data-ttu-id="d6372-162">`name`이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>이라는 지정한 조건이 충족되었으므로 중단점에 도달한 후 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-162">Because the condition you specified (`name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>) has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="d6372-163">**지역** 창을 선택합니다. 이 창에는 현재 실행 중인 메서드에 로컬인 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-163">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="d6372-164">이 경우 `Main`은 현재 실행 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-164">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="d6372-165">`name` 변수의 값은 `""` 또는 <xref:System.String.Empty?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-165">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="d6372-166">**직접 실행 창**에 다음 문을 입력하고 <kbd>Enter</kbd>를 눌러 값이 빈 문자열인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-166">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="d6372-167">결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-167">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="d6372-168">물음표는 직접 실행 창에서 [식을 계산](/visualstudio/ide/reference/immediate-window#enter-commands)하도록 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-168">The question mark directs the immediate window to [evaluate an expression](/visualstudio/ide/reference/immediate-window#enter-commands).</span></span>

   ![문이 실행된 후 true 값을 반환하는 직접 실행 창 - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="d6372-170"><kbd>F5</kbd>를 눌러 프로그램을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-170">Press <kbd>F5</kbd> to continue program execution.</span></span>

1. <span data-ttu-id="d6372-171">아무 키나 눌러 콘솔 창을 닫고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-171">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="d6372-172">코드 창 왼쪽 여백에 있는 점을 클릭하여 중단점을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-172">Clear the breakpoint by clicking on the dot in the left margin of the code window.</span></span> <span data-ttu-id="d6372-173"><kbd>F9</kbd> 키를 누르거나 코드 줄이 선택된 상태로 **디버그 > 중단점 설정/해제**를 선택해도 중단점을 지울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-173">Other ways to clear a breakpoint are by pressing <kbd>F9</kbd> or choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

## <a name="step-through-a-program"></a><span data-ttu-id="d6372-174">단계별 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="d6372-174">Step through a program</span></span>

<span data-ttu-id="d6372-175">Visual Studio에서 프로그램을 한 줄씩 단계별로 실행하고 해당 실행을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-175">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="d6372-176">일반적으로 중단점을 설정하고 프로그램 코드 일부의 프로그램 흐름을 따라가면서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-176">Ordinarily, you'd set a breakpoint and follow program flow through a small part of your program code.</span></span> <span data-ttu-id="d6372-177">이 프로그램은 작으므로 전체 프로그램을 단계별로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-177">Since this program is small, you can step through the entire program.</span></span>

1. <span data-ttu-id="d6372-178">**디버그** > **한 단계씩 코드 실행**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-178">Choose **Debug** > **Step Into**.</span></span> <span data-ttu-id="d6372-179">한 번에 하나의 문을 디버그하는 또 다른 방법은 <kbd>F11</kbd> 키를 누르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-179">Another way to debug one statement at a time is by pressing <kbd>F11</kbd>.</span></span>

   <span data-ttu-id="d6372-180">Visual Studio에서 다음에 실행될 줄을 강조 표시하고 옆에 화살표를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-180">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   <span data-ttu-id="d6372-181">C#</span><span class="sxs-lookup"><span data-stu-id="d6372-181">C#</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 - C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="d6372-183">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6372-183">Visual Basic</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="d6372-185">이 시점에서 **지역** 창에는 `args` 배열이 비어 있다고 표시되고, `name` 및 `date`에는 기본값이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-185">At this point, the **Locals** window shows that the `args` array is empty, and `name` and `date` have default values.</span></span> <span data-ttu-id="d6372-186">또한 Visual Studio에서는 빈 콘솔 창이 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-186">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="d6372-187"><kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-187">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6372-188">이제 Visual Studio에서 다음에 실행될 줄을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-188">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="d6372-189">**지역** 창은 변경되지 않으며, 콘솔 창은 계속 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-189">The **Locals** window is unchanged, and the console window remains blank.</span></span>

   <span data-ttu-id="d6372-190">C#</span><span class="sxs-lookup"><span data-stu-id="d6372-190">C#</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 소스 - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

   <span data-ttu-id="d6372-192">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d6372-192">Visual Basic</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 소스 - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="d6372-194"><kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-194">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6372-195">Visual Studio는 `name` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-195">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="d6372-196">**지역** 창에서는 `name`이 `null`로 표시되고 콘솔 창에서는 문자열 "What is your name?"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-196">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="d6372-197">콘솔 창에 문자열을 입력하고 <kbd>Enter</kbd> 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-197">Respond to the prompt by entering a string in the console window and pressing <kbd>Enter</kbd>.</span></span> <span data-ttu-id="d6372-198">콘솔은 응답하지 않게 되고 입력한 문자열이 콘솔 창에 표시되지 않지만 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드는 사용자의 입력을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-198">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="d6372-199"><kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-199">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6372-200">Visual Studio는 `date` 변수 할당(Visual Basic에서는 `currentDate`)을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-200">Visual Studio highlights the statement that includes the `date` variable assignment (`currentDate` in Visual Basic).</span></span> <span data-ttu-id="d6372-201">**지역** 창에는 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드 호출에 의해 반환된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-201">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d6372-202">콘솔 창에는 프롬프트에 입력한 문자열도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-202">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="d6372-203"><kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-203">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6372-204">**지역** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성에 따라 할당된 이후의 `date` 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-204">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="d6372-205">콘솔 창은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-205">The console window is unchanged.</span></span>

1. <span data-ttu-id="d6372-206"><kbd>F11</kbd> 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-206">Press <kbd>F11</kbd>.</span></span> <span data-ttu-id="d6372-207">Visual Studio에서 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-207">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="d6372-208">콘솔 창에는 서식이 지정된 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-208">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="d6372-209">**디버그** > **프로시저 나가기**를 선택합니다. 단계별 실행을 중지하는 또 다른 방법은 <kbd>Shift</kbd>+<kbd>F11</kbd> 키를 누르는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-209">Choose **Debug** > **Step Out**. Another way to stop step-by-step execution is by pressing <kbd>Shift</kbd>+<kbd>F11</kbd>.</span></span>

   <span data-ttu-id="d6372-210">콘솔 창은 메시지를 표시하고 사용자가 키를 누르기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-210">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="d6372-211">아무 키나 눌러 콘솔 창을 닫고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-211">Press any key to close the console window and stop debugging.</span></span>

## <a name="use-release-build-configuration"></a><span data-ttu-id="d6372-212">릴리스 빌드 구성 사용</span><span class="sxs-lookup"><span data-stu-id="d6372-212">Use Release build configuration</span></span>

<span data-ttu-id="d6372-213">애플리케이션의 디버그 버전을 테스트한 후에는 릴리스 버전을 컴파일하고 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-213">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="d6372-214">릴리스 버전에는 애플리케이션의 동작에 부정적인 영향을 줄 수 있는 컴파일러 최적화가 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-214">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="d6372-215">예를 들어 성능 향상을 위해 설계된 컴파일러 최적화는 다중 스레드 애플리케이션에서 경합 상태를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-215">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="d6372-216">콘솔 애플리케이션의 릴리스 버전을 빌드하고 테스트하려면 도구 모음에서 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-216">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![디버그가 강조 표시된 기본 Visual Studio 도구 모음](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="d6372-218"><kbd>F5</kbd> 키를 누르거나 **빌드** 메뉴에서 **솔루션 빌드**를 선택하면 Visual Studio에서 애플리케이션의 릴리스 버전을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-218">When you press <kbd>F5</kbd> or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="d6372-219">디버그 버전처럼 릴리스 버전을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-219">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="d6372-220">다음 단계</span><span class="sxs-lookup"><span data-stu-id="d6372-220">Next steps</span></span>

<span data-ttu-id="d6372-221">이 자습서에서는 Visual Studio 디버깅 도구를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-221">In this tutorial, you used Visual Studio debugging tools.</span></span> <span data-ttu-id="d6372-222">다음 자습서에서는 앱의 배포 가능 버전을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="d6372-222">In the next tutorial, you publish a deployable version of the app.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="d6372-223">Visual Studio를 사용하여 .NET Core 콘솔 애플리케이션 게시</span><span class="sxs-lookup"><span data-stu-id="d6372-223">Publish a .NET Core console application using Visual Studio</span></span>](publishing-with-visual-studio.md)
