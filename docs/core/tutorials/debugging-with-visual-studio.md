---
title: Visual Studio를 사용하여 Hello World .NET Core 애플리케이션 디버그
description: Visual Studio에서 C# 또는 Visual Basic으로 작성된 Hello World 앱을 디버그하는 방법을 알아봅니다.
ms.date: 12/05/2019
ms.custom: vs-dotnet
ms.openlocfilehash: b2ee1401fc89f990c5f930d80d1a510a117e63a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "78156675"
---
# <a name="debug-your-c-or-visual-basic-net-core-hello-world-application-using-visual-studio"></a><span data-ttu-id="ffc84-103">Visual Studio 2017을 사용하여 C# 또는 Visual Basic .NET Core Hello World 애플리케이션 디버그</span><span class="sxs-lookup"><span data-stu-id="ffc84-103">Debug your C# or Visual Basic .NET Core Hello World application using Visual Studio</span></span>

<span data-ttu-id="ffc84-104">지금까지 [Visual Studio 2019에서 첫 번째 .NET Core 콘솔 애플리케이션 만들기](with-visual-studio.md)의 단계에 따라 간단한 콘솔 애플리케이션을 만들고 실행했습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-104">So far, you've followed the steps in [Create your first .NET Core console application in Visual Studio 2019](with-visual-studio.md) to create and run a simple console application.</span></span> <span data-ttu-id="ffc84-105">애플리케이션을 작성하고 컴파일했으면 테스트를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-105">Once you've written and compiled your application, you can begin testing it.</span></span> <span data-ttu-id="ffc84-106">Visual Studio에는 애플리케이션을 문제를 해결하는 데 사용할 수 있는 포괄적인 디버깅 도구 집합이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-106">Visual Studio includes a comprehensive set of debugging tools that you can use to troubleshoot your application.</span></span>

## <a name="debug-build-configuration"></a><span data-ttu-id="ffc84-107">디버그 빌드 구성</span><span class="sxs-lookup"><span data-stu-id="ffc84-107">Debug build configuration</span></span>

<span data-ttu-id="ffc84-108">*디버그* 및 *릴리스*는 Visual Studio의 기본 빌드 구성 중 두 개입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-108">*Debug* and *Release* are two of Visual Studio's default build configurations.</span></span> <span data-ttu-id="ffc84-109">현재 빌드 구성은 도구 모음에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-109">The current build configuration is shown on the toolbar.</span></span> <span data-ttu-id="ffc84-110">다음 도구 모음 그림은 Visual Studio가 앱의 디버그 버전을 컴파일하도록 구성되어 있음을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-110">The following toolbar image shows that Visual Studio is configured to compile the Debug version of the app:</span></span>

![디버그가 강조 표시된 Visual Studio 도구 모음](./media/debugging-with-visual-studio/visual-studio-toolbar-debug.png)

<span data-ttu-id="ffc84-112">앱의 디버그 버전을 실행하여 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-112">Begin by running the Debug version of your app.</span></span> <span data-ttu-id="ffc84-113">디버그 빌드 구성은 대부분의 컴파일러 최적화를 끄고 빌드 프로세스 중 보다 다양한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-113">The Debug build configuration turns off most compiler optimizations and provides richer information during the build process.</span></span>

## <a name="set-a-breakpoint"></a><span data-ttu-id="ffc84-114">중단점 설정</span><span class="sxs-lookup"><span data-stu-id="ffc84-114">Set a breakpoint</span></span>

<span data-ttu-id="ffc84-115">프로그램을 실행하고 몇 가지 디버깅 기능을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-115">Run your program and try a few debugging features:</span></span>

<!-- markdownlint-disable MD025 -->

# <a name="c"></a>[<span data-ttu-id="ffc84-116">C#</span><span class="sxs-lookup"><span data-stu-id="ffc84-116">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="ffc84-117">줄의 코드 창에 있는 왼쪽 여백을 클릭하여 `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");`을 읽는 줄에 *중단점*을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-117">Set a *breakpoint* on the line that reads `Console.WriteLine($"\nHello, {name}, on {date:d} at {date:t}!");` by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="ffc84-118">코드 줄에 캐럿을 배치하고 **F9**를 누르거나 메뉴 모음에서 **디버그** > **중단점 설정/해제**를 선택하여 중단점을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-118">You can also set a breakpoint by placing the caret in the line of code and then pressing **F9** or choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="ffc84-119">중단점은 중단점이 설정된 줄이 실행되기 *전에* 애플리케이션 실행을 일시적으로 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-119">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="ffc84-120">다음 이미지에서 볼 수 있듯이 Visual Studio에서는 중단점이 설정된 줄을 강조 표시하고 왼쪽 여백에 빨간색 원을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-120">As the following image shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![중단점이 설정된 Visual Studio 프로그램 창](./media/debugging-with-visual-studio/set-breakpoint-in-editor.png)

1. <span data-ttu-id="ffc84-122">도구 모음에서 녹색 화살표가 있는 **HelloWorld** 단추를 선택하거나 **F5** 키를 누르거나 **디버그** > **디버깅 시작**을 선택하여 프로그램을 디버그 모드에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-122">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing **F5**, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="ffc84-123">프로그램 이름을 입력하라는 메시지가 표시되면 콘솔 창에 문자열을 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-123">Enter a string in the console window when the program prompts for a name, and then press **Enter**.</span></span>

1. <span data-ttu-id="ffc84-124">중단점에 도달할 때와 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-124">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="ffc84-125">**지역** 창에는 현재 실행 중인 메서드에 정의된 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-125">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

   ![Visual Studio의 중단점 스크린샷](./media/debugging-with-visual-studio/breakpoint-hit.png)

1. <span data-ttu-id="ffc84-127">**직접 실행 창**에서는 디버그하는 애플리케이션을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-127">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="ffc84-128">대화형으로 변수 값을 변경하여 프로그램에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-128">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="ffc84-129">**직접 실행 창**이 표시되지 않는 경우 **디버그** > **창** > **직접 실행**을 선택하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-129">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="ffc84-130">**직접 실행 창**에 `name = "Gracie"`를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-130">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="ffc84-131">**직접 실행 창**에 `date = DateTime.Parse("11/16/2019 5:25 PM")`를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-131">Enter `date = DateTime.Parse("11/16/2019 5:25 PM")` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="ffc84-132">**직접 실행 창**에는 문자열 변수의 값과 <xref:System.DateTime> 값의 속성이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-132">The **Immediate** window displays the value of the string variable and the properties of the <xref:System.DateTime> value.</span></span> <span data-ttu-id="ffc84-133">또한 변수 값이 **지역** 창에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-133">In addition, the values of the variables are updated in the **Locals** window.</span></span>

   ![Visual Studio 2019의 지역 및 직접 실행 창](./media/debugging-with-visual-studio/locals-immediate-window.png)

1. <span data-ttu-id="ffc84-135">도구 모음에서 **계속** 단추를 선택하거나 **디버그** > **계속**을 선택하여 프로그램을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-135">Continue program execution by selecting the **Continue** button in the toolbar or by selecting **Debug** > **Continue**.</span></span> <span data-ttu-id="ffc84-136">콘솔 창에 표시되는 값은 **직접 실행 창**에서 변경한 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-136">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![입력한 값을 보여주는 콘솔 창](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="ffc84-138">아무 키나 눌러 애플리케이션을 종료하고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-138">Press any key to exit the application and stop debugging.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="ffc84-139">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ffc84-139">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="ffc84-140">줄의 코드 창에 있는 왼쪽 여백을 클릭하여 `Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")`을 읽는 줄에 *중단점*을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-140">Set a *breakpoint* on the line that reads `Console.WriteLine($"{vbCrLf}Hello, {name}, on {currentDate:d} at {currentDate:t}!")` by clicking in the left margin of the code window on that line.</span></span> <span data-ttu-id="ffc84-141">코드 줄에 캐럿을 배치하고 메뉴 모음에서 **디버그** > **중단점 설정/해제**를 선택하여 중단점을 설정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-141">You can also set a breakpoint by placing the caret on the desired line and then choosing **Debug** > **Toggle Breakpoint** from the menu bar.</span></span>

   <span data-ttu-id="ffc84-142">중단점은 중단점이 설정된 줄이 실행되기 *전에* 애플리케이션 실행을 일시적으로 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-142">A breakpoint temporarily interrupts the execution of the application *before* the line with the breakpoint is executed.</span></span>

   <span data-ttu-id="ffc84-143">다음 그림에서 볼 수 있듯이 Visual Studio에서는 중단점이 설정된 줄을 강조 표시하고 왼쪽 여백에 빨간색 원을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-143">As the following figure shows, Visual Studio indicates the line on which the breakpoint is set by highlighting it and displaying a red circle in its left margin.</span></span>

   ![중단점이 설정된 Visual Studio 프로그램 창](./media/debugging-with-visual-studio/vb/set-breakpoint-in-editor.png)

1. <span data-ttu-id="ffc84-145">도구 모음에서 녹색 화살표가 있는 **HelloWorld** 단추를 선택하거나 **F5** 키를 누르거나 **디버그** > **디버깅 시작**을 선택하여 프로그램을 디버그 모드에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-145">Run the program in Debug mode by selecting the **HelloWorld** button with the green arrow on the toolbar, pressing **F5**, or choosing **Debug** > **Start Debugging**.</span></span>

1. <span data-ttu-id="ffc84-146">프로그램 이름을 입력하라는 메시지가 표시되면 콘솔 창에 문자열을 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-146">Enter a string in the console window when the program prompts for a name and press **Enter**.</span></span>

1. <span data-ttu-id="ffc84-147">중단점에 도달할 때와 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-147">Program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span> <span data-ttu-id="ffc84-148">**지역** 창에는 현재 실행 중인 메서드에 정의된 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-148">The **Locals** window displays the values of variables that are defined in the currently executing method.</span></span>

1. <span data-ttu-id="ffc84-149">**직접 실행 창**에서는 디버그하는 애플리케이션을 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-149">The **Immediate** window lets you interact with the application you're debugging.</span></span> <span data-ttu-id="ffc84-150">대화형으로 변수 값을 변경하여 프로그램에 미치는 영향을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-150">You can interactively change the value of variables to see how it affects your program.</span></span>

   1. <span data-ttu-id="ffc84-151">**직접 실행 창**이 표시되지 않는 경우 **디버그** > **창** > **직접 실행**을 선택하여 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-151">If the **Immediate** window is not visible, display it by choosing **Debug** > **Windows** > **Immediate**.</span></span>

   1. <span data-ttu-id="ffc84-152">**직접 실행 창**에 `name = "Gracie"`를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-152">Enter `name = "Gracie"` in the **Immediate** window and press the **Enter** key.</span></span>

   1. <span data-ttu-id="ffc84-153">**직접 실행 창**에 `date = DateTime.Parse("11/16/2019 5:25 PM")`를 입력하고 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-153">Enter `date = DateTime.Parse("11/16/2019 5:25 PM")` in the **Immediate** window and press the **Enter** key.</span></span>

   <span data-ttu-id="ffc84-154">변수 값이 **지역** 창에서 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-154">The values of the variables are updated in the **Locals** window.</span></span>

1. <span data-ttu-id="ffc84-155">도구 모음에서 **계속** 단추를 선택하거나 **디버그** > **계속** 메뉴 항목을 선택하여 프로그램을 계속 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-155">Continue program execution by selecting the **Continue** button in the toolbar or by selecting the **Debug** > **Continue** menu item.</span></span> <span data-ttu-id="ffc84-156">콘솔 창에 표시되는 값은 **직접 실행 창**에서 변경한 값과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-156">The values displayed in the console window correspond to the changes you made in the **Immediate** window.</span></span>

   ![입력한 값을 보여주는 콘솔 창](./media/debugging-with-visual-studio/console-window.png)

1. <span data-ttu-id="ffc84-158">아무 키나 눌러 애플리케이션을 종료하고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-158">Press any key to exit the application and stop debugging.</span></span>

---

## <a name="set-a-conditional-breakpoint"></a><span data-ttu-id="ffc84-159">조건부 중단점 설정</span><span class="sxs-lookup"><span data-stu-id="ffc84-159">Set a conditional breakpoint</span></span>

<span data-ttu-id="ffc84-160">프로그램은 사용자가 입력하는 문자열을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-160">Your program displays the string that the user enters.</span></span> <span data-ttu-id="ffc84-161">사용자가 아무 값도 입력하지 않으면 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="ffc84-161">What happens if the user doesn't enter anything?</span></span> <span data-ttu-id="ffc84-162">하나 이상의 조건이 충족될 경우 프로그램 실행을 중단하는 유용한 디버깅 기능인 *조건부 중단점*을 사용하여 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-162">You can test this with a useful debugging feature called a *conditional breakpoint*, which breaks program execution when one or more conditions are met.</span></span>

<span data-ttu-id="ffc84-163">조건부 중단점을 설정하고 사용자가 문자열을 입력하지 못한 경우에 발생하는 상황을 테스트하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-163">To set a conditional breakpoint and test what happens when the user fails to enter a string, do the following:</span></span>

# <a name="c"></a>[<span data-ttu-id="ffc84-164">C#</span><span class="sxs-lookup"><span data-stu-id="ffc84-164">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="ffc84-165">중단점을 나타내는 빨간색 점을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-165">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="ffc84-166">상황에 맞는 메뉴에서 **조건**을 선택하여 **중단점 설정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-166">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="ffc84-167">아직 선택하지 않은 경우 **조건** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-167">Check the box for **Conditions** if it's not already selected.</span></span>

   ![중단점 설정 패널을 보여 주는 편집기 - C#](./media/debugging-with-visual-studio/breakpoint-settings.png)

1. <span data-ttu-id="ffc84-169">**조건식**에서 “e.g. x == 5”를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-169">For the **Conditional Expression**, replace "e.g. x == 5" with the following:</span></span>

   ```csharp
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="ffc84-170">`name`에 값이 할당되지 않았거나 해당 값이 빈 문자열("")이기 때문에 `String.IsNullOrEmpty(name)` 메서드 호출이 `true`인 코드 조건을 테스트하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-170">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `true` either because `name` has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="ffc84-171">조건식 대신 문이 실행되기 전에 프로그램 실행을 중단하는 *적중 횟수* 또는 스레드 식별자, 프로세스 이름 또는 스레드 이름과 같은 특성을 기준으로 프로그램 실행을 중단하는 *필터 조건*을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-171">Instead of a conditional expression, you can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="ffc84-172">**닫기**를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-172">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="ffc84-173">**F5** 키를 눌러 디버깅으로 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-173">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="ffc84-174">콘솔 창에 이름을 입력하라는 메시지가 나타나면 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-174">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="ffc84-175">`name`이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>이라는 지정한 조건이 충족되었으므로 중단점에 도달한 후 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-175">Because the condition you specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="ffc84-176">**지역** 창을 선택합니다. 이 창에는 현재 실행 중인 메서드에 로컬인 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-176">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="ffc84-177">이 경우 `Main`은 현재 실행 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-177">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="ffc84-178">`name` 변수의 값은 `""` 또는 <xref:System.String.Empty?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-178">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="ffc84-179">**직접 실행 창**에 다음 문을 입력하고 **Enter**를 눌러 값이 빈 문자열인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-179">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="ffc84-180">결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-180">The result is `true`.</span></span>

   ```csharp
   ? name == String.Empty
   ```

   ![문이 실행된 후 true 값을 반환하는 직접 실행 창 - C#](./media/debugging-with-visual-studio/immediate-window-output.png)

1. <span data-ttu-id="ffc84-182">도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-182">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="ffc84-183">아무 키나 눌러 콘솔 창을 닫고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-183">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="ffc84-184">코드 줄을 선택한 사이 코드 창 왼쪽 여백에 있는 점을 클릭하거나 행을 선택하고 **디버그 > 중단점 설정/해제**를 선택하여 중단점을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-184">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing **Debug > Toggle Breakpoint** while the line of code is selected.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="ffc84-185">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ffc84-185">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="ffc84-186">중단점을 나타내는 빨간색 점을 마우스 오른쪽 단추로 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-186">Right-click on the red dot that represents the breakpoint.</span></span> <span data-ttu-id="ffc84-187">상황에 맞는 메뉴에서 **조건**을 선택하여 **중단점 설정** 대화 상자를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-187">On the context menu, select **Conditions** to open the **Breakpoint Settings** dialog.</span></span> <span data-ttu-id="ffc84-188">**조건** 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-188">Check the box for **Conditions**.</span></span>

   ![중단점 설정 패널을 보여 주는 편집기 - Visual Basic](./media/debugging-with-visual-studio/vb-breakpointsettings.png)

1. <span data-ttu-id="ffc84-190">**조건식**에서 “e.g. x = 5”를 다음 코드로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-190">For the **Conditional Expression** replace "e.g. x = 5" with the following:</span></span>

   ```vb
   String.IsNullOrEmpty(name)
   ```

   <span data-ttu-id="ffc84-191">`name`에 값이 할당되지 않았거나 해당 값이 빈 문자열("")이기 때문에 `String.IsNullOrEmpty(name)` 메서드 호출이 `true`인 코드 조건을 테스트하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-191">You're testing for a code condition, that the `String.IsNullOrEmpty(name)` method call is `true` either because `name` has not been assigned a value or because its value is an empty string ("").</span></span> <span data-ttu-id="ffc84-192">조건식 대신 문이 실행되기 전에 프로그램 실행을 중단하는 *적중 횟수* 또는 스레드 식별자, 프로세스 이름 또는 스레드 이름과 같은 특성을 기준으로 프로그램 실행을 중단하는 *필터 조건*을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-192">Instead of a conditional expression, you can also specify a *hit count*, which interrupts program execution before a statement is executed a specified number of times, or a *filter condition*, which interrupts program execution based on such attributes as a thread identifier, process name, or thread name.</span></span>

1. <span data-ttu-id="ffc84-193">**닫기**를 선택하여 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-193">Select **Close** to close the dialog.</span></span>

1. <span data-ttu-id="ffc84-194">**F5** 키를 눌러 디버깅으로 프로그램을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-194">Start the program with debugging by pressing **F5**.</span></span>

1. <span data-ttu-id="ffc84-195">콘솔 창에 이름을 입력하라는 메시지가 나타나면 **Enter** 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-195">In the console window, press the **Enter** key when prompted to enter your name.</span></span>

1. <span data-ttu-id="ffc84-196">`name`이 `null` 또는 <xref:System.String.Empty?displayProperty=nameWithType>이라는 지정한 조건이 충족되었으므로 중단점에 도달한 후 `Console.WriteLine` 메서드가 실행되기 전에 프로그램 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-196">Because the condition you specified, `name` is either `null` or <xref:System.String.Empty?displayProperty=nameWithType>, has been satisfied, program execution stops when it reaches the breakpoint and before the `Console.WriteLine` method executes.</span></span>

1. <span data-ttu-id="ffc84-197">**지역** 창을 선택합니다. 이 창에는 현재 실행 중인 메서드에 로컬인 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-197">Select the **Locals** window, which shows the values of variables that are local to the currently executing method.</span></span> <span data-ttu-id="ffc84-198">이 경우 `Main`은 현재 실행 중인 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-198">In this case, `Main` is the currently executing method.</span></span> <span data-ttu-id="ffc84-199">`name` 변수의 값은 `""` 또는 <xref:System.String.Empty?displayProperty=nameWithType>입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-199">Observe that the value of the `name` variable is `""`, or <xref:System.String.Empty?displayProperty=nameWithType>.</span></span>

1. <span data-ttu-id="ffc84-200">**직접 실행 창**에 다음 문을 입력하고 **Enter**를 눌러 값이 빈 문자열인지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-200">Confirm the value is an empty string by entering the following statement in the **Immediate** window and pressing **Enter**.</span></span> <span data-ttu-id="ffc84-201">결과는 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-201">The result is `true`.</span></span>

   ```vb
   ? String.IsNullOrEmpty(name)
   ```

   ![문이 실행된 후 true 값을 반환하는 직접 실행 창 - Visual Basic](./media/debugging-with-visual-studio/vb/immediate-window-output.png)

1. <span data-ttu-id="ffc84-203">도구 모음에서 **계속** 단추를 선택하여 프로그램 실행을 계속합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-203">Select the **Continue** button on the toolbar to continue program execution.</span></span>

1. <span data-ttu-id="ffc84-204">아무 키나 눌러 콘솔 창을 닫고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-204">Press any key to close the console window and stop debugging.</span></span>

1. <span data-ttu-id="ffc84-205">코드 창 왼쪽 여백에 있는 점을 클릭하거나 행을 선택하고 **디버그 > 중단점 설정/해제** 메뉴 항목을 선택하여 중단점을 지웁니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-205">Clear the breakpoint by clicking on the dot in the left margin of the code window or by choosing the **Debug > Toggle Breakpoint** menu item with the row selected.</span></span>

---
## <a name="step-through-a-program"></a><span data-ttu-id="ffc84-206">단계별 프로그램 실행</span><span class="sxs-lookup"><span data-stu-id="ffc84-206">Step through a program</span></span>

<span data-ttu-id="ffc84-207">Visual Studio에서 프로그램을 한 줄씩 단계별로 실행하고 해당 실행을 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-207">Visual Studio also allows you to step line by line through a program and monitor its execution.</span></span> <span data-ttu-id="ffc84-208">일반적으로 중단점을 설정하고 이 기능을 사용하여 프로그램 코드 일부의 프로그램 흐름을 따라가면서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-208">Ordinarily, you'd set a breakpoint and use this feature to follow program flow through a small part of your program code.</span></span> <span data-ttu-id="ffc84-209">여기서는 프로그램이 작으므로 전체 프로그램을 단계별로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-209">Since your program is small, you can step through the entire program:</span></span>

# <a name="c"></a>[<span data-ttu-id="ffc84-210">C#</span><span class="sxs-lookup"><span data-stu-id="ffc84-210">C#</span></span>](#tab/csharp)

1. <span data-ttu-id="ffc84-211">메뉴 모음에서 **디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-211">On the menu bar, choose **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-212">Visual Studio에서 다음에 실행될 줄을 강조 표시하고 옆에 화살표를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-212">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 - C#](./media/debugging-with-visual-studio/step-into-method.png)

   <span data-ttu-id="ffc84-214">이때 **지역** 창에는 현재 프로그램에서 단일 변수인 `args`만 정의되었다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-214">At this point, the **Locals** window shows that your program has defined only one variable, `args`.</span></span> <span data-ttu-id="ffc84-215">프로그램에 명령줄 인수를 전달하지 않았으므로 해당 값은 빈 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-215">Because you haven't passed any command-line arguments to the program, its value is an empty string array.</span></span> <span data-ttu-id="ffc84-216">또한 Visual Studio에서는 빈 콘솔 창이 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-216">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="ffc84-217">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-217">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-218">이제 Visual Studio에서 다음에 실행될 줄을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-218">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="ffc84-219">이미지에서 볼 수 있듯이 마지막 문과 이 문 사이의 코드를 실행하는 데는 1밀리초 미만이 소요되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-219">As the image shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="ffc84-220">`args`가 선언된 유일한 변수이며 콘솔 창은 여전히 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-220">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 소스 - C#](./media/debugging-with-visual-studio/step-into-source-method.png)

1. <span data-ttu-id="ffc84-222">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-222">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-223">Visual Studio는 `name` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-223">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="ffc84-224">**지역** 창에서는 `name`이 `null`로 표시되고 콘솔 창에서는 문자열 "What is your name?"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-224">The **Locals** window shows that `name` is `null`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="ffc84-225">콘솔 창에 문자열을 입력하고 **Enter** 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-225">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="ffc84-226">콘솔은 응답하지 않게 되고 입력한 문자열이 콘솔 창에 표시되지 않지만 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드는 사용자의 입력을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-226">The console is unresponsive, and the string you entered isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="ffc84-227">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-227">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-228">Visual Studio는 `date` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-228">Visual Studio highlights the statement that includes the `date` variable assignment.</span></span> <span data-ttu-id="ffc84-229">**지역** 창에는 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드 호출에 의해 반환된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-229">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ffc84-230">콘솔 창에는 프롬프트에 입력한 문자열도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-230">The console window also displays the string you entered at the prompt.</span></span>

1. <span data-ttu-id="ffc84-231">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-231">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-232">**지역** 창에는 <xref:System.DateTime.Now?displayProperty=nameWithType> 속성에 따라 할당된 이후의 `date` 변수 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-232">The **Locals** window shows the value of the `date` variable after the assignment from the <xref:System.DateTime.Now?displayProperty=nameWithType> property.</span></span> <span data-ttu-id="ffc84-233">콘솔 창은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-233">The console window is unchanged.</span></span>

1. <span data-ttu-id="ffc84-234">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-234">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-235">Visual Studio에서 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-235">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ffc84-236">콘솔 창에는 서식이 지정된 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-236">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="ffc84-237">**디버그** > **프로시저 나가기**를 선택하거나 **Shift**+**F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-237">Select **Debug** > **Step Out** or press **Shift**+**F11**.</span></span> <span data-ttu-id="ffc84-238">이렇게 하면 단계별 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-238">This stops step-by-step execution.</span></span> <span data-ttu-id="ffc84-239">콘솔 창은 메시지를 표시하고 사용자가 키를 누르기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-239">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="ffc84-240">아무 키나 눌러 콘솔 창을 닫고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-240">Press any key to close the console window and stop debugging.</span></span>

# <a name="visual-basic"></a>[<span data-ttu-id="ffc84-241">Visual Basic</span><span class="sxs-lookup"><span data-stu-id="ffc84-241">Visual Basic</span></span>](#tab/vb)

1. <span data-ttu-id="ffc84-242">메뉴 모음에서 **디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-242">On the menu bar, choose **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-243">Visual Studio에서 다음에 실행될 줄을 강조 표시하고 옆에 화살표를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-243">Visual Studio highlights and displays an arrow beside the next line of execution.</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-method.png)

   <span data-ttu-id="ffc84-245">이때 **지역** 창에는 현재 프로그램에서 단일 변수인 `args`만 정의되었다고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-245">At this point, the **Locals** window shows that your program has defined only one variable, `args`.</span></span> <span data-ttu-id="ffc84-246">프로그램에 명령줄 인수를 전달하지 않았으므로 해당 값은 빈 문자열 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-246">Because you haven't passed any command-line arguments to the program, its value is an empty string array.</span></span> <span data-ttu-id="ffc84-247">또한 Visual Studio에서는 빈 콘솔 창이 열려 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-247">In addition, Visual Studio has opened a blank console window.</span></span>

1. <span data-ttu-id="ffc84-248">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-248">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-249">이제 Visual Studio에서 다음에 실행될 줄을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-249">Visual Studio now highlights the next line of execution.</span></span> <span data-ttu-id="ffc84-250">그림에서 볼 수 있듯이 마지막 문과 이 문 사이의 코드를 실행하는 데는 1밀리초 미만이 소요되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-250">As the figure shows, it has taken less than one millisecond to execute the code between the last statement and this one.</span></span> <span data-ttu-id="ffc84-251">`args`가 선언된 유일한 변수이며 콘솔 창은 여전히 비어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-251">`args` remains the only declared variable, and the console window remains blank.</span></span>

   ![Visual Studio 한 단계씩 코드 실행 메서드 소스 - Visual Basic](./media/debugging-with-visual-studio/vb-step-into-source-method.png)

1. <span data-ttu-id="ffc84-253">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-253">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-254">Visual Studio는 `name` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-254">Visual Studio highlights the statement that includes the `name` variable assignment.</span></span> <span data-ttu-id="ffc84-255">**지역** 창에서는 `name`이 `Nothing`로 표시되고 콘솔 창에서는 문자열 "What is your name?"이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-255">The **Locals** window shows that `name` is `Nothing`, and the console window displays the string "What is your name?".</span></span>

1. <span data-ttu-id="ffc84-256">콘솔 창에 문자열을 입력하고 **Enter** 키를 눌러 프롬프트에 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-256">Respond to the prompt by entering a string in the console window and pressing **Enter**.</span></span> <span data-ttu-id="ffc84-257">콘솔은 응답하지 않게 되고 입력한 문자열이 콘솔 창에 표시되지 않지만 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드는 사용자의 입력을 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-257">The console is unresponsive, and the string you enter isn't displayed in the console window, but the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method will nevertheless capture your input.</span></span>

1. <span data-ttu-id="ffc84-258">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-258">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-259">Visual Studio는 `currentDate` 변수 할당을 포함하는 문을 강조 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-259">Visual Studio highlights the statement that includes the `currentDate` variable assignment.</span></span> <span data-ttu-id="ffc84-260">**지역** 창에는 <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> 메서드 호출에 의해 반환된 값이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-260">The **Locals** window shows the value returned by the call to the <xref:System.Console.ReadLine%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ffc84-261">콘솔 창에는 콘솔이 입력을 요구할 때 입력된 문자열도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-261">The console window also displays the string entered when the console prompted for input.</span></span>

1. <span data-ttu-id="ffc84-262">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-262">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-263">콘솔 창은 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-263">The console window is unchanged.</span></span>

1. <span data-ttu-id="ffc84-264">**디버그** > **한 단계씩 코드 실행**을 선택하거나 **F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-264">Select **Debug** > **Step Into** or press **F11**.</span></span> <span data-ttu-id="ffc84-265">Visual Studio에서 <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-265">Visual Studio calls the <xref:System.Console.WriteLine(System.String,System.Object,System.Object)?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="ffc84-266">콘솔 창에는 서식이 지정된 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-266">The console window displays the formatted string.</span></span>

1. <span data-ttu-id="ffc84-267">**디버그** > **프로시저 나가기**를 선택하거나 **Shift**+**F11**을 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-267">Select **Debug** > **Step Out** or press **Shift**+**F11**.</span></span> <span data-ttu-id="ffc84-268">이렇게 하면 단계별 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-268">This stops step-by-step execution.</span></span> <span data-ttu-id="ffc84-269">콘솔 창은 메시지를 표시하고 사용자가 키를 누르기를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-269">The console window displays a message and waits for you to press a key.</span></span>

1. <span data-ttu-id="ffc84-270">아무 키나 눌러 콘솔 창을 닫고 디버깅을 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-270">Press any key to close the console window and stop debugging.</span></span>

---

## <a name="build-a-release-version"></a><span data-ttu-id="ffc84-271">릴리스 버전 빌드</span><span class="sxs-lookup"><span data-stu-id="ffc84-271">Build a Release version</span></span>

<span data-ttu-id="ffc84-272">애플리케이션의 디버그 버전을 테스트한 후에는 릴리스 버전을 컴파일하고 테스트해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-272">Once you've tested the Debug version of your application, you should also compile and test the Release version.</span></span> <span data-ttu-id="ffc84-273">릴리스 버전에는 애플리케이션의 동작에 부정적인 영향을 줄 수 있는 컴파일러 최적화가 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-273">The Release version incorporates compiler optimizations that can sometimes negatively affect the behavior of an application.</span></span> <span data-ttu-id="ffc84-274">예를 들어 성능 향상을 위해 설계된 컴파일러 최적화는 다중 스레드 애플리케이션에서 경합 상태를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-274">For example, compiler optimizations that are designed to improve performance can create race conditions in multithreaded applications.</span></span>

<span data-ttu-id="ffc84-275">콘솔 애플리케이션의 릴리스 버전을 빌드하고 테스트하려면 도구 모음에서 빌드 구성을 **디버그**에서 **릴리스**로 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-275">To build and test the Release version of your console application, change the build configuration on the toolbar from **Debug** to **Release**.</span></span>

![디버그가 강조 표시된 기본 Visual Studio 도구 모음](./media/debugging-with-visual-studio/visual-studio-toolbar-release.png)

<span data-ttu-id="ffc84-277">**F5** 키를 누르거나 **빌드** 메뉴에서 **솔루션 빌드**를 선택하면 Visual Studio에서 애플리케이션의 릴리스 버전을 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-277">When you press **F5** or choose **Build Solution** from the **Build** menu, Visual Studio compiles the Release version of the application.</span></span> <span data-ttu-id="ffc84-278">디버그 버전처럼 릴리스 버전을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-278">You can test it as you did the Debug version.</span></span>

## <a name="next-steps"></a><span data-ttu-id="ffc84-279">다음 단계</span><span class="sxs-lookup"><span data-stu-id="ffc84-279">Next steps</span></span>

<span data-ttu-id="ffc84-280">애플리케이션 디버그를 마친 후의 다음 단계는 배포 가능한 앱 버전을 게시하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ffc84-280">Once you've debugged your application, the next step is to publish a deployable version of the app.</span></span> <span data-ttu-id="ffc84-281">이 작업을 수행하는 방법에 대한 자세한 내용은 [Visual Studio를 사용하여 .NET Core Hello World 애플리케이션 게시](publishing-with-visual-studio.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ffc84-281">For information on how to do this, see [Publish your .NET Core Hello World application with Visual Studio](publishing-with-visual-studio.md).</span></span>
