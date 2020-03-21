---
title: 이벤트 처리기 개요
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
ms.openlocfilehash: ffec8a9f8e080dec78152e62e00e2dceefbdaab0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141694"
---
# <a name="event-handlers-overview-windows-forms"></a><span data-ttu-id="b61b1-102">이벤트 처리기 개요(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="b61b1-102">Event Handlers Overview (Windows Forms)</span></span>
<span data-ttu-id="b61b1-103">이벤트 처리기는 이벤트에 바인딩된 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-103">An event handler is a method that is bound to an event.</span></span> <span data-ttu-id="b61b1-104">이벤트가 발생하면 이벤트 처리기 내의 코드가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-104">When the event is raised, the code within the event handler is executed.</span></span> <span data-ttu-id="b61b1-105">각 이벤트 처리기는 이벤트를 올바르게 처리할 수 있는 두 개의 매개 변수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-105">Each event handler provides two parameters that allow you to handle the event properly.</span></span> <span data-ttu-id="b61b1-106">다음 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대 한 이벤트 처리기를 보여 합니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-106">The following example shows an event handler for a <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event.</span></span>  
  
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
  
 <span data-ttu-id="b61b1-107">첫 번째`sender`매개 변수는 이벤트를 발생시킨 개체에 대한 참조를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-107">The first parameter,`sender`, provides a reference to the object that raised the event.</span></span> <span data-ttu-id="b61b1-108">위의 예제에서 `e`두 번째 매개 변수는 처리 중인 이벤트에 특정한 개체를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-108">The second parameter, `e`, in the example above, passes an object specific to the event that is being handled.</span></span> <span data-ttu-id="b61b1-109">개체의 속성(및 해당 메서드)을 참조하여 마우스 이벤트에 대한 마우스 위치 또는 끌어서 놓기 이벤트에서 전송되는 데이터와 같은 정보를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-109">By referencing the object's properties (and, sometimes, its methods), you can obtain information such as the location of the mouse for mouse events or data being transferred in drag-and-drop events.</span></span>  
  
 <span data-ttu-id="b61b1-110">일반적으로 각 이벤트는 두 번째 매개 변수에 대해 다른 이벤트 개체 형식을 가진 이벤트 처리기를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-110">Typically each event produces an event handler with a different event-object type for the second parameter.</span></span> <span data-ttu-id="b61b1-111"><xref:System.Windows.Forms.Control.MouseDown> 및 이벤트와 <xref:System.Windows.Forms.Control.MouseUp> 같은 일부 이벤트 처리기는 두 번째 매개 변수에 대해 동일한 개체 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-111">Some event handlers, such as those for the <xref:System.Windows.Forms.Control.MouseDown> and <xref:System.Windows.Forms.Control.MouseUp> events, have the same object type for their second parameter.</span></span> <span data-ttu-id="b61b1-112">이러한 유형의 이벤트의 경우 동일한 이벤트 처리기를 사용하여 두 이벤트를 모두 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-112">For these types of events, you can use the same event handler to handle both events.</span></span>  
  
 <span data-ttu-id="b61b1-113">동일한 이벤트 처리기를 사용하여 다른 컨트롤에 대해 동일한 이벤트를 처리할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-113">You can also use the same event handler to handle the same event for different controls.</span></span> <span data-ttu-id="b61b1-114">예를 들어 폼에 <xref:System.Windows.Forms.RadioButton> 컨트롤 그룹이 있는 경우 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 단일 이벤트 처리기를 만들고 각 <xref:System.Windows.Forms.Control.Click> 컨트롤의 이벤트가 단일 이벤트 처리기에 바인딩되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b61b1-114">For example, if you have a group of <xref:System.Windows.Forms.RadioButton> controls on a form, you could create a single event handler for the <xref:System.Windows.Forms.Control.Click> event and have each control's <xref:System.Windows.Forms.Control.Click> event bound to the single event handler.</span></span> <span data-ttu-id="b61b1-115">자세한 내용은 [Windows Forms의 단일 이벤트 처리기에 여러 이벤트를 연결하는 방법을](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b61b1-115">For more information, see [How to: Connect Multiple Events to a Single Event Handler in Windows Forms](how-to-connect-multiple-events-to-a-single-event-handler-in-windows-forms.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b61b1-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b61b1-116">See also</span></span>

- [<span data-ttu-id="b61b1-117">Windows Forms에서 이벤트 처리기 만들기</span><span class="sxs-lookup"><span data-stu-id="b61b1-117">Creating Event Handlers in Windows Forms</span></span>](creating-event-handlers-in-windows-forms.md)
- [<span data-ttu-id="b61b1-118">이벤트 개요</span><span class="sxs-lookup"><span data-stu-id="b61b1-118">Events Overview</span></span>](events-overview-windows-forms.md)
