---
title: 이벤트 처리기 개요(Windows Forms)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms, event handling
- event handling [Windows Forms], Windows Forms
- event handlers [Windows Forms], about event handlers
ms.assetid: 228112e1-1711-42ee-8ffa-ff3555bffe66
ms.openlocfilehash: 05acbfaf427060d015c2445360a7d73ebe97d070
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186084"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="6eee4-102">이벤트 처리기 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="6eee4-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="6eee4-103">이벤트 처리기는 이벤트에 바인딩된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="6eee4-104">이벤트가 발생 하면 이벤트 처리기 내의 코드가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="6eee4-105">각 이벤트 처리기는 이벤트를 제대로 처리할 수 있도록 하는 두 개의 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="6eee4-106">다음 예제에서는 이벤트 처리기를 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
```vb  
Private Sub button1_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles button1.Click  
  
End Sub  
```  
  
```csharp  
private void button1_Click(object sender, System.EventArgs e)   
{  
  
}  
```  
  
```cpp  
private:  
  void button1_Click(System::Object ^ sender,  
    System::EventArgs ^ e)  
  {  
  
  }  
```  
  
 <span data-ttu-id="6eee4-107">첫 번째 매개 변수를`sender`, 이벤트를 발생 시킨 개체에 대 한 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="6eee4-108">두 번째 매개 변수를 `e`, 위의 예에서 특정 개체를 전달 처리 되는 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="6eee4-109">개체의 속성 (및 경우에 따라 해당 메서드)를 참조 하 여 마우스 이벤트 또는 끌어서 놓기 이벤트에서 전송 되는 데이터에 대 한 마우스의 위치와 같은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="6eee4-110">일반적으로 각 이벤트는 두 번째 매개 변수에 대 한 다른 이벤트 개체 유형 사용 하 여 이벤트 처리기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="6eee4-111">에 대 한 것과 같은 일부 이벤트 처리기를 <xref:System.Windows.Forms.Control.MouseDown> 고 <xref:System.Windows.Forms.Control.MouseUp> 이벤트 형식이 같은 개체는 두 번째 매개 변수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="6eee4-112">이러한 종류의 이벤트에 대 한 두 이벤트를 처리 하는 동일한 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="6eee4-113">또한 다른 컨트롤에 대해 동일한 이벤트를 처리 하려면 동일한 이벤트 처리기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="6eee4-114">예를 들어, 그룹에 있는 경우 <xref:System.Windows.Forms.RadioButton> 폼에서 컨트롤에 대 한 단일 이벤트 처리기를 만들 수 있습니다 합니다 <xref:System.Windows.Forms.Control.Click> 이벤트 각 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트를 단일 이벤트 처리기를 바인딩할 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="6eee4-115">자세한 내용은 [방법: Windows Forms에서 단일 이벤트 처리기에 여러 이벤트 연결](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="6eee4-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6eee4-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="6eee4-116">See also</span></span>

- [<span data-ttu-id="6eee4-117">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="6eee4-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="6eee4-118">이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="6eee4-118">Events Overview</span></span>](events-overview-windows-forms.md)
