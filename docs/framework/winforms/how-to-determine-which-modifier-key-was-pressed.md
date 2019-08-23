---
title: '방법: 누른 보조 키 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- keyboard input
- shift keys
- events [Windows Forms], mouse
- Keys.ControlKey enumeration member
- keys [Windows Forms], control keys
- user input [Windows Forms], checking for keyboard
- keys [Windows Forms], determining last pressed
- keys [Windows Forms], shift keys
- keys [Windows Forms], modifier keys
- control keys
- keys [Windows Forms], alt keys
- alt keys
- Keys.Shift enumeration member
- events [Windows Forms], keyboard
- keyboards [Windows Forms], keyboard input
- Keys.Alt enumeration member
- modifier keys
ms.assetid: 1e184048-0ae3-4067-a200-d4ba31dbc2cb
ms.openlocfilehash: 37fa897f5a2e1c65cbd5db9189f1500e3427c920
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69964321"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="72b9b-102">방법: 누른 보조 키 확인</span><span class="sxs-lookup"><span data-stu-id="72b9b-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="72b9b-103">사용자의 키 입력을 허용 하는 응용 프로그램을 만들 때 SHIFT, ALT, CTRL 키 등 보조키를 모니터링 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="72b9b-104">보조키를 다른 키와 함께 누르거나 마우스를 클릭 하면 응용 프로그램이 적절 하 게 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="72b9b-105">예를 들어 문자 S를 누르면 "s"가 화면에 표시 될 수 있지만 CTRL + S 키를 누르면 현재 문서가 저장 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="72b9b-106"><xref:System.Windows.Forms.Control.KeyDown> 이벤트를 처리 하는 경우 이벤트 <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> 처리기에서 <xref:System.Windows.Forms.KeyEventArgs> 받은의 속성은 키를 누르는 보조키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="72b9b-107">또는의 <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> <xref:System.Windows.Forms.KeyEventArgs> 속성은 누른 문자 뿐만 아니라 비트 or로 결합 된 모든 보조키를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="72b9b-108">그러나 <xref:System.Windows.Forms.Control.KeyPress> 이벤트 또는 마우스 이벤트를 처리 하는 경우 이벤트 처리기는이 정보를 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="72b9b-109">이 경우 <xref:System.Windows.Forms.Control.ModifierKeys%2A> <xref:System.Windows.Forms.Control> 클래스의 속성을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="72b9b-110">두 경우 모두 적절 <xref:System.Windows.Forms.Keys> 한 값 및 테스트 하는 값의 비트 and를 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="72b9b-111">열거형 <xref:System.Windows.Forms.Keys> 은 각 보조키의 변형을 제공 하므로 올바른 값으로 비트 and를 수행 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="72b9b-112">예를 들어 shift 키는 <xref:System.Windows.Forms.Keys.Shift> <xref:System.Windows.Forms.Keys.RShiftKey> , <xref:System.Windows.Forms.Keys.ShiftKey>및 <xref:System.Windows.Forms.Keys.LShiftKey> 로 표시 되며 shift 키 <xref:System.Windows.Forms.Keys.Shift>를 보조키로 테스트 하는 데 올바른 값은입니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="72b9b-113">마찬가지로 CTRL 및 ALT 키를 보조키로 테스트 하려면 각각 <xref:System.Windows.Forms.Keys.Control> 및 <xref:System.Windows.Forms.Keys.Alt> 값을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-113">Similarly, to test for CTRL and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="72b9b-114">Visual Basic 프로그래머는 속성을 통해 키 정보에 <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="72b9b-115">누른 보조키를 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="72b9b-115">To determine which modifier key was pressed</span></span>  
  
- <span data-ttu-id="72b9b-116"><xref:System.Windows.Forms.Control.ModifierKeys%2A> 속성 `AND` 및 열거형값과함께비트연산자를사용하여특정보조키를눌렀는지여부를확인합니다.<xref:System.Windows.Forms.Keys></span><span class="sxs-lookup"><span data-stu-id="72b9b-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="72b9b-117">다음 코드 예제에서는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트 처리기 내에서 SHIFT 키를 눌렀는지 여부를 확인 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="72b9b-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="72b9b-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="72b9b-118">See also</span></span>

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [<span data-ttu-id="72b9b-119">Windows Forms 응용 프로그램의 키보드 입력</span><span class="sxs-lookup"><span data-stu-id="72b9b-119">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- <span data-ttu-id="72b9b-120">[방법: Visual Basic에서 CapsLock가 설정 되어 있는지 확인](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="72b9b-120">[How to: Determine If CapsLock is On in Visual Basic](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))</span></span>
