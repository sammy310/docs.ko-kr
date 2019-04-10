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
ms.openlocfilehash: 571af49cdf82b876cfb72a7c7636874c8d155fb7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213938"
---
# <a name="how-to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="5465f-102">방법: 누른 보조 키 확인</span><span class="sxs-lookup"><span data-stu-id="5465f-102">How to: Determine Which Modifier Key Was Pressed</span></span>
<span data-ttu-id="5465f-103">사용자의 키 입력을 허용 하는 응용 프로그램을 만들면 SHIFT, ALT 및 CTRL 키 등 보조키 모니터링할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-103">When you create an application that accepts the user's keystrokes, you may also want to monitor for modifier keys such as the SHIFT, ALT, and CTRL keys.</span></span> <span data-ttu-id="5465f-104">보조 키를 누르면 조합 하 여 마우스 클릭 또는 다른 키를 사용 하 여, 응용 프로그램이 적절 하 게 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-104">When a modifier key is pressed in combination with other keys, or with mouse clicks, your application can respond appropriately.</span></span> <span data-ttu-id="5465f-105">예를 들어, "s"을 화면에 표시할 문자 S를 누르면 단순히 발생할 수 있습니다 하지만 키 CTRL + S를 누르면 현재 문서를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-105">For example, if the letter S is pressed, this may simply cause an "s" to appear on the screen, but if the keys CTRL+S are pressed, the current document may be saved.</span></span> <span data-ttu-id="5465f-106">처리 하는 경우는 <xref:System.Windows.Forms.Control.KeyDown> 이벤트를 <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> 의 속성은 <xref:System.Windows.Forms.KeyEventArgs> 수신 처리기 이벤트에 의해 보조 키를 누르면을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-106">If you handle the <xref:System.Windows.Forms.Control.KeyDown> event, the <xref:System.Windows.Forms.KeyEventArgs.Modifiers%2A> property of the <xref:System.Windows.Forms.KeyEventArgs> received by the event handler specifies which modifier keys are pressed.</span></span> <span data-ttu-id="5465f-107">또는 합니다 <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> 속성의 <xref:System.Windows.Forms.KeyEventArgs> 비트 OR 연산자와 결합 된 모든 한정자 키도 누른는 문자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-107">Alternatively, the <xref:System.Windows.Forms.KeyEventArgs.KeyData%2A> property of <xref:System.Windows.Forms.KeyEventArgs> specifies the character that was pressed as well as any modifier keys combined with a bitwise OR.</span></span> <span data-ttu-id="5465f-108">그러나 처리 하는 경우는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트 또는 마우스 이벤트를 이벤트 처리기는이 정보를 수신 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-108">However, if you are handling the <xref:System.Windows.Forms.Control.KeyPress> event or a mouse event, the event handler does not receive this information.</span></span> <span data-ttu-id="5465f-109">이 경우 사용 해야 합니다는 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 의 속성을 <xref:System.Windows.Forms.Control> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-109">In this case, you must use the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property of the <xref:System.Windows.Forms.Control> class.</span></span> <span data-ttu-id="5465f-110">적절 한 비트 AND를 수행 해야 하 든에서 <xref:System.Windows.Forms.Keys> 값과는 테스트할 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-110">In either case, you must perform a bitwise AND of the appropriate <xref:System.Windows.Forms.Keys> value and the value you are testing.</span></span> <span data-ttu-id="5465f-111"><xref:System.Windows.Forms.Keys> 열거형 변형을 한정자, 각 키의 비트를 수행 하는 중요 한 이므로 및 올바른 값으로 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-111">The <xref:System.Windows.Forms.Keys> enumeration offers variations of each modifier key, so it is important that you perform the bitwise AND with the correct value.</span></span> <span data-ttu-id="5465f-112">SHIFT 키를 나타내는 예를 들어 <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> 하 고 <xref:System.Windows.Forms.Keys.LShiftKey> SHIFT 테스트의 한정자 키가 올바른 값 <xref:System.Windows.Forms.Keys.Shift>합니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-112">For example, the SHIFT key is represented by <xref:System.Windows.Forms.Keys.Shift>, <xref:System.Windows.Forms.Keys.ShiftKey>, <xref:System.Windows.Forms.Keys.RShiftKey> and <xref:System.Windows.Forms.Keys.LShiftKey> The correct value to test SHIFT as a modifier key is <xref:System.Windows.Forms.Keys.Shift>.</span></span> <span data-ttu-id="5465f-113">마찬가지로, 한정자로 CTRL 및 alt 키에 대 한 테스트를 사용 해야 합니다 <xref:System.Windows.Forms.Keys.Control> 고 <xref:System.Windows.Forms.Keys.Alt> 값을 각각.</span><span class="sxs-lookup"><span data-stu-id="5465f-113">Similarly, to test for CTRL and ALT as modifiers you should use the <xref:System.Windows.Forms.Keys.Control> and <xref:System.Windows.Forms.Keys.Alt> values, respectively.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="5465f-114">Visual Basic 프로그래머를 통해 키 정보에 액세스할 수도 있습니다는 <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> 속성</span><span class="sxs-lookup"><span data-stu-id="5465f-114">Visual Basic programmers can also access key information through the <xref:Microsoft.VisualBasic.Devices.Computer.Keyboard%2A> property</span></span>  
  
### <a name="to-determine-which-modifier-key-was-pressed"></a><span data-ttu-id="5465f-115">보조키를 눌렀는지 확인 하려면</span><span class="sxs-lookup"><span data-stu-id="5465f-115">To determine which modifier key was pressed</span></span>  
  
-   <span data-ttu-id="5465f-116">비트를 사용 하 여 `AND` 연산자는 <xref:System.Windows.Forms.Control.ModifierKeys%2A> 속성과 값을 <xref:System.Windows.Forms.Keys> 특정 보조키를 눌렀는지 여부를 결정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-116">Use the bitwise `AND` operator with the <xref:System.Windows.Forms.Control.ModifierKeys%2A> property and a value of the <xref:System.Windows.Forms.Keys> enumeration to determine whether a particular modifier key is pressed.</span></span> <span data-ttu-id="5465f-117">다음 코드 예제 내에서 SHIFT 키를 눌렀는지 여부를 확인 하는 방법을 보여 줍니다는 <xref:System.Windows.Forms.Control.KeyPress> 이벤트 처리기입니다.</span><span class="sxs-lookup"><span data-stu-id="5465f-117">The following code example shows how to determine whether the SHIFT key is pressed within a <xref:System.Windows.Forms.Control.KeyPress> event handler.</span></span>  
  
     [!code-cpp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/cpp/form1.cpp#5)]
     [!code-csharp[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/CS/form1.cs#5)]
     [!code-vb[System.Windows.Forms.DetermineModifierKey#5](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.DetermineModifierKey/VB/form1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="5465f-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="5465f-118">See also</span></span>

- <xref:System.Windows.Forms.Keys>
- <xref:System.Windows.Forms.Control.ModifierKeys%2A>
- [<span data-ttu-id="5465f-119">Windows Forms 응용 프로그램의 키보드 입력</span><span class="sxs-lookup"><span data-stu-id="5465f-119">Keyboard Input in a Windows Forms Application</span></span>](keyboard-input-in-a-windows-forms-application.md)
- [<span data-ttu-id="5465f-120">방법: Visual Basic의 경우 CapsLock 켜져 확인</span><span class="sxs-lookup"><span data-stu-id="5465f-120">How to: Determine If CapsLock is On in Visual Basic</span></span>](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9c9d1fz9(v=vs.100))
