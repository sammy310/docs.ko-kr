---
title: '방법: 코드에서 마우스 및 키보드 이벤트 시뮬레이션'
description: Windows Forms에서 제공 하는 옵션을 사용 하 여 프로그래밍 방식으로 마우스 및 키보드 입력을 시뮬레이션 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboards [Windows Forms], event simulation
- user input [Windows Forms], simulating
- SendKeys [Windows Forms], using
- mouse clicks [Windows Forms], simulating
- mouse [Windows Forms], event simulation
ms.assetid: 6abcb67e-3766-4af2-9590-bf5dabd17e41
ms.openlocfilehash: 3c60533479352151ac4f28690413ebc7d8e5879d
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85619249"
---
# <a name="how-to-simulate-mouse-and-keyboard-events-in-code"></a><span data-ttu-id="2b740-103">방법: 코드에서 마우스 및 키보드 이벤트 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="2b740-103">How to: Simulate Mouse and Keyboard Events in Code</span></span>

<span data-ttu-id="2b740-104">Windows Forms는 프로그래밍 방식으로 마우스 및 키보드 입력을 시뮬레이션하기 위한 여러 가지 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-104">Windows Forms provides several options for programmatically simulating mouse and keyboard input.</span></span> <span data-ttu-id="2b740-105">이 항목에서는 이러한 옵션에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-105">This topic provides an overview of these options.</span></span>

## <a name="simulating-mouse-input"></a><span data-ttu-id="2b740-106">마우스 입력 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="2b740-106">Simulating Mouse Input</span></span>

<span data-ttu-id="2b740-107">마우스 이벤트를 시뮬레이션하는 가장 좋은 방법은 시뮬레이션하려는 마우스 이벤트를 발생시키는 `On`*EventName* 메서드를 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-107">The best way to simulate mouse events is to call the `On`*EventName* method that raises the mouse event you want to simulate.</span></span> <span data-ttu-id="2b740-108">이벤트를 발생시키는 메서드는 보호되며 컨트롤이나 폼 외부에서 액세스할 수 없기 때문에 이 옵션은 일반적으로 사용자 지정 컨트롤 및 폼 내에서만 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-108">This option is usually possible only within custom controls and forms, because the methods that raise events are protected and cannot be accessed outside the control or form.</span></span> <span data-ttu-id="2b740-109">예를 들어 다음 단계에서는 코드에서 마우스 오른쪽 단추를 클릭하여 시뮬레이션하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-109">For example, the following steps illustrate how to simulate clicking the right mouse button in code.</span></span>

#### <a name="to-programmatically-click-the-right-mouse-button"></a><span data-ttu-id="2b740-110">프로그래밍 방식으로 마우스 오른쪽 단추를 클릭하려면</span><span class="sxs-lookup"><span data-stu-id="2b740-110">To programmatically click the right mouse button</span></span>

1. <span data-ttu-id="2b740-111"><xref:System.Windows.Forms.MouseEventArgs> 속성이 <xref:System.Windows.Forms.MouseEventArgs.Button%2A> 값으로 설정된 <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> 를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-111">Create a <xref:System.Windows.Forms.MouseEventArgs> whose <xref:System.Windows.Forms.MouseEventArgs.Button%2A> property is set to the <xref:System.Windows.Forms.MouseButtons.Right?displayProperty=nameWithType> value.</span></span>

2. <span data-ttu-id="2b740-112">이 <xref:System.Windows.Forms.Control.OnMouseClick%2A> 를 인수로 사용하여 <xref:System.Windows.Forms.MouseEventArgs> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-112">Call the <xref:System.Windows.Forms.Control.OnMouseClick%2A> method with this <xref:System.Windows.Forms.MouseEventArgs> as the argument.</span></span>

<span data-ttu-id="2b740-113">사용자 지정 컨트롤에 대한 자세한 내용은 [디자인 타임에 Windows Forms 컨트롤 개발](./controls/developing-windows-forms-controls-at-design-time.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2b740-113">For more information on custom controls, see [Developing Windows Forms Controls at Design Time](./controls/developing-windows-forms-controls-at-design-time.md).</span></span>

<span data-ttu-id="2b740-114">마우스 입력을 시뮬레이션하는 다른 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-114">There are other ways to simulate mouse input.</span></span> <span data-ttu-id="2b740-115">예를 들어 일반적으로 마우스 입력을 통해 설정되는 상태를 나타내는 컨트롤 속성(예: <xref:System.Windows.Forms.CheckBox.Checked%2A> 컨트롤의 <xref:System.Windows.Forms.CheckBox> 속성)을 프로그래밍 방식으로 설정하거나 시뮬레이션하려는 이벤트에 연결된 대리자를 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-115">For example, you can programmatically set a control property that represents a state that is typically set through mouse input (such as the <xref:System.Windows.Forms.CheckBox.Checked%2A> property of the <xref:System.Windows.Forms.CheckBox> control), or you can directly call the delegate that is attached to the event you want to simulate.</span></span>

## <a name="simulating-keyboard-input"></a><span data-ttu-id="2b740-116">키보드 입력 시뮬레이션</span><span class="sxs-lookup"><span data-stu-id="2b740-116">Simulating Keyboard Input</span></span>

<span data-ttu-id="2b740-117">마우스 입력에 대해 위에서 설명한 전략을 사용하여 키보드 입력을 시뮬레이션할 수도 있지만 Windows Forms에서는 활성 애플리케이션에 키 입력을 전송하기 위한 <xref:System.Windows.Forms.SendKeys> 클래스도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-117">Although you can simulate keyboard input by using the strategies discussed above for mouse input, Windows Forms also provides the <xref:System.Windows.Forms.SendKeys> class for sending keystrokes to the active application.</span></span>

> [!CAUTION]
> <span data-ttu-id="2b740-118">다양한 키보드를 통해 전 세계에서 사용하기 위한 애플리케이션인 경우 <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> 를 사용하면 예기치 않은 결과가 발생할 수 있으며 피해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-118">If your application is intended for international use with a variety of keyboards, the use of <xref:System.Windows.Forms.SendKeys.Send%2A?displayProperty=nameWithType> could yield unpredictable results and should be avoided.</span></span>

> [!NOTE]
> <span data-ttu-id="2b740-119"><xref:System.Windows.Forms.SendKeys> 클래스는 Windows Vista에서 실행되는 애플리케이션에서 사용할 수 있도록 .NET Framework 3.0에서 업데이트되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-119">The <xref:System.Windows.Forms.SendKeys> class has been updated for the .NET Framework 3.0 to enable its use in applications that run on Windows Vista.</span></span> <span data-ttu-id="2b740-120">Windows Vista의 향상된 보안(사용자 계정 컨트롤 또는 UAC라고 함) 때문에 이전 구현이 예상대로 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-120">The enhanced security of Windows Vista (known as User Account Control or UAC) prevents the previous implementation from working as expected.</span></span>
>
> <span data-ttu-id="2b740-121"><xref:System.Windows.Forms.SendKeys> 클래스는 타이밍 문제에 취약하며, 이를 해결하기 위해 일부 개발자가 노력해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-121">The <xref:System.Windows.Forms.SendKeys> class is susceptible to timing issues, which some developers have had to work around.</span></span> <span data-ttu-id="2b740-122">업데이트된 구현도 타이밍 문제에 취약하지만 약간 더 빠르며 해결 방법에 대한 변경이 필요할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-122">The updated implementation is still susceptible to timing issues, but is slightly faster and may require changes to the workarounds.</span></span> <span data-ttu-id="2b740-123"><xref:System.Windows.Forms.SendKeys> 클래스는 먼저 이전 구현을 사용하려고 시도하며, 실패할 경우 새 구현을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-123">The <xref:System.Windows.Forms.SendKeys> class tries to use the previous implementation first, and if that fails, uses the new implementation.</span></span> <span data-ttu-id="2b740-124">따라서 <xref:System.Windows.Forms.SendKeys> 클래스는 운영 체제마다 다르게 동작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-124">As a result, the <xref:System.Windows.Forms.SendKeys> class may behave differently on different operating systems.</span></span> <span data-ttu-id="2b740-125">또한 <xref:System.Windows.Forms.SendKeys> 클래스가 새 구현을 사용하는 경우 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 메서드는 다른 프로세스로 전송된 메시지가 처리될 때까지 기다리지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-125">Additionally, when the <xref:System.Windows.Forms.SendKeys> class uses the new implementation, the <xref:System.Windows.Forms.SendKeys.SendWait%2A> method will not wait for messages to be processed when they are sent to another process.</span></span>
>
> <span data-ttu-id="2b740-126">애플리케이션이 운영 체제와 관계없이 일관된 동작에 의존하는 경우 app.config 파일에 다음 애플리케이션 설정을 추가하여 <xref:System.Windows.Forms.SendKeys> 클래스에서 새 구현을 사용하도록 강제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-126">If your application relies on consistent behavior regardless of the operating system, you can force the <xref:System.Windows.Forms.SendKeys> class to use the new implementation by adding the following application setting to your app.config file.</span></span>
>
> ```xml
> <appSettings>
>  <add key="SendKeys" value="SendInput"/>
> </appSettings>
> ```
>
> <span data-ttu-id="2b740-127"><xref:System.Windows.Forms.SendKeys> 클래스에서 이전 구현을 사용하도록 강제하려면 `"JournalHook"` 값을 대신 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-127">To force the <xref:System.Windows.Forms.SendKeys> class to use the previous implementation, use the value `"JournalHook"` instead.</span></span>

#### <a name="to-send-a-keystroke-to-the-same-application"></a><span data-ttu-id="2b740-128">동일한 애플리케이션에 키 입력을 보내려면</span><span class="sxs-lookup"><span data-stu-id="2b740-128">To send a keystroke to the same application</span></span>

1. <span data-ttu-id="2b740-129"><xref:System.Windows.Forms.SendKeys.Send%2A> 클래스의 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 또는 <xref:System.Windows.Forms.SendKeys> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-129">Call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method of the <xref:System.Windows.Forms.SendKeys> class.</span></span> <span data-ttu-id="2b740-130">애플리케이션의 활성 컨트롤이 지정된 키 입력을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-130">The specified keystrokes will be received by the active control of the application.</span></span> <span data-ttu-id="2b740-131">다음 코드 예제에서는 <xref:System.Windows.Forms.SendKeys.Send%2A> 를 사용하여 사용자가 폼의 화면을 두 번 클릭할 때 Enter 키 누름을 시뮬레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-131">The following code example uses <xref:System.Windows.Forms.SendKeys.Send%2A> to simulate pressing the ENTER key when the user double-clicks the surface of the form.</span></span> <span data-ttu-id="2b740-132">이 예제에서는 탭 인덱스가 0인 단일 <xref:System.Windows.Forms.Form> 컨트롤이 있는 <xref:System.Windows.Forms.Button> 을 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-132">This example assumes a <xref:System.Windows.Forms.Form> with a single <xref:System.Windows.Forms.Button> control that has a tab index of 0.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#10)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#10)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#10](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#10)]

#### <a name="to-send-a-keystroke-to-a-different-application"></a><span data-ttu-id="2b740-133">다른 애플리케이션에 키 입력을 보내려면</span><span class="sxs-lookup"><span data-stu-id="2b740-133">To send a keystroke to a different application</span></span>

1. <span data-ttu-id="2b740-134">키 입력을 수신할 애플리케이션 창을 활성화한 다음 <xref:System.Windows.Forms.SendKeys.Send%2A> 또는 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-134">Activate the application window that will receive the keystrokes, and then call the <xref:System.Windows.Forms.SendKeys.Send%2A> or <xref:System.Windows.Forms.SendKeys.SendWait%2A> method.</span></span> <span data-ttu-id="2b740-135">다른 애플리케이션을 활성화할 관리되는 메서드가 없으므로 네이티브 Windows 메서드를 사용하여 다른 애플리케이션에 포커스를 강제로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-135">Because there is no managed method to activate another application, you must use native Windows methods to force focus on other applications.</span></span> <span data-ttu-id="2b740-136">다음 코드 예제에서는 플랫폼 호출을 통해 `FindWindow` 및 `SetForegroundWindow` 메서드를 호출하여 계산기 애플리케이션 창을 활성화한 다음 <xref:System.Windows.Forms.SendKeys.SendWait%2A> 를 호출하여 계산기 애플리케이션에 일련의 계산을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-136">The following code example uses platform invoke to call the `FindWindow` and `SetForegroundWindow` methods to activate the Calculator application window, and then calls <xref:System.Windows.Forms.SendKeys.SendWait%2A> to issue a series of calculations to the Calculator application.</span></span>

    > [!NOTE]
    > <span data-ttu-id="2b740-137">계산기 애플리케이션을 찾는 `FindWindow` 호출의 올바른 매개 변수는 Windows 버전에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-137">The correct parameters of the `FindWindow` call that locates the Calculator application vary based on your version of Windows.</span></span>  <span data-ttu-id="2b740-138">다음 코드는 Windows 7에서 계산기 응용 프로그램을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-138">The following code finds the Calculator application on Windows 7.</span></span> <span data-ttu-id="2b740-139">Windows Vista에서 첫 번째 매개 변수를 "SciCalc"로 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-139">On Windows Vista, change the first parameter to "SciCalc".</span></span> <span data-ttu-id="2b740-140">Visual Studio에 포함된 Spy++ 도구를 사용하여 올바른 매개 변수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-140">You can use the Spy++ tool, included with Visual Studio, to determine the correct parameters.</span></span>

    [!code-cpp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#5)]
    [!code-csharp[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#5)]
    [!code-vb[System.Windows.Forms.SimulateKeyPress#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#5)]

## <a name="example"></a><span data-ttu-id="2b740-141">예제</span><span class="sxs-lookup"><span data-stu-id="2b740-141">Example</span></span>

<span data-ttu-id="2b740-142">다음 코드 예제는 이전 코드 예제에 대한 전체 애플리케이션입니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-142">The following code example is the complete application for the previous code examples.</span></span>

[!code-cpp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/cpp/form1.cpp#0)]
[!code-csharp[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/CS/form1.cs#0)]
[!code-vb[System.Windows.Forms.SimulateKeyPress#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.SimulateKeyPress/VB/form1.vb#0)]

## <a name="compiling-the-code"></a><span data-ttu-id="2b740-143">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="2b740-143">Compiling the Code</span></span>

<span data-ttu-id="2b740-144">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b740-144">This example requires:</span></span>

- <span data-ttu-id="2b740-145">System, System.Drawing 및 System.Windows.Forms 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="2b740-145">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>

## <a name="see-also"></a><span data-ttu-id="2b740-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2b740-146">See also</span></span>

- [<span data-ttu-id="2b740-147">Windows Forms에 사용자 입력</span><span class="sxs-lookup"><span data-stu-id="2b740-147">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
