---
title: RaiseEvent 문
ms.date: 07/20/2015
f1_keywords:
- vb.RaiseEventMethod
- vb.RaiseEvent
- RaiseEvent
helpviewer_keywords:
- raising events [Visual Basic], RaiseEvent statement
- RaiseEvent statement [Visual Basic]
- event handlers, connecting events to
ms.assetid: f82e380a-1e6b-4047-bea8-c853f4d2c742
ms.openlocfilehash: e04f2bbaf57789f0bdaa07c1ebd68b22e3ae6178
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333054"
---
# <a name="raiseevent-statement"></a>RaiseEvent 문
Triggers an event declared at module level within a class, form, or document.  
  
## <a name="syntax"></a>구문  
  
```vb  
RaiseEvent eventname[( argumentlist )]  
```  
  
## <a name="parts"></a>요소  
 `eventname`  
 필수 요소. Name of the event to trigger.  
  
 `argumentlist`  
 (선택 사항) Comma-delimited list of variables, arrays, or expressions. The `argumentlist` argument must be enclosed by parentheses. If there are no arguments, the parentheses must be omitted.  
  
## <a name="remarks"></a>주의  
 The required `eventname` is the name of an event declared within the module. It follows Visual Basic variable naming conventions.  
  
 If the event has not been declared within the module in which it is raised, an error occurs. The following code fragment illustrates an event declaration and a procedure in which the event is raised.  
  
 [!code-vb[VbVbalrEvents#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#37)]  
  
 You cannot use `RaiseEvent` to raise events that are not explicitly declared in the module. For example, all forms inherit a <xref:System.Windows.Forms.Control.Click> event from <xref:System.Windows.Forms.Form?displayProperty=nameWithType>, it cannot be raised using `RaiseEvent` in a derived form. If you declare a `Click` event in the form module, it shadows the form's own <xref:System.Windows.Forms.Control.Click> event. You can still invoke the form's <xref:System.Windows.Forms.Control.Click> event by calling the <xref:System.Windows.Forms.Control.OnClick%2A> method.  
  
 By default, an event defined in Visual Basic raises its event handlers in the order that the connections are established. Because events can have `ByRef` parameters, a process that connects late may receive parameters that have been changed by an earlier event handler. After the event handlers execute, control is returned to the subroutine that raised the event.  
  
> [!NOTE]
> Non-shared events should not be raised within the constructor of the class in which they are declared. Although such events do not cause run-time errors, they may fail to be caught by associated event handlers. Use the `Shared` modifier to create a shared event if you need to raise an event from a constructor.  
  
> [!NOTE]
> You can change the default behavior of events by defining a custom event. For custom events, the `RaiseEvent` statement invokes the event's `RaiseEvent` accessor. For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>예제  
 다음 예제에서는 이벤트를 사용하여 10초부터 0초까지 카운트 다운합니다. The code illustrates several of the event-related methods, properties, and statements, including the `RaiseEvent` statement.  
  
 이벤트를 발생시키는 클래스는 이벤트 소스이고 이벤트를 처리하는 메서드는 이벤트 처리기입니다. 이벤트 소스는 생성되는 이벤트에 대해 여러 개의 처리기를 사용할 수 있습니다. 클래스에서 이벤트를 발생시키면 해당 이벤트는 개체의 해당 인스턴스에 대해 이벤트를 처리하도록 선택한 모든 클래스에서 발생됩니다.  
  
 또한 이 예제에서는 단추(`Button1`)와 텍스트 상자(`TextBox1`)가 있는 폼(`Form1`)을 사용합니다. 단추를 클릭하면 첫 번째 텍스트 상자에 10초부터 0초까지의 카운트 다운이 표시됩니다. 전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.  
  
 `Form1`에 대한 코드는 폼의 초기 상태 및 최종 상태를 지정합니다. 또한 이벤트가 발생될 때 실행될 코드도 포함됩니다.  
  
 To use this example, open a new Windows Application project, add a button named `Button1` and a text box named `TextBox1` to the main form, named `Form1`. Then right-click the form and click **View Code** to open the Code Editor.  
  
 Add a `WithEvents` variable to the declarations section of the `Form1` class.  
  
 [!code-vb[VbVbalrEvents#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#14)]  
  
## <a name="example"></a>예제  
 `Form1`에 대한 코드에 다음 코드를 추가합니다. Replace any duplicate procedures that may exist, such as `Form_Load`, or `Button_Click`.  
  
 [!code-vb[VbVbalrEvents#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#15)]  
  
 Press F5 to run the preceding example, and click the button labeled **Start**. 첫 번째 텍스트 상자에서 초를 카운트 다운하기 시작합니다. 전체 시간(10초)이 경과되면 첫 번째 텍스트 상자에 "Done"이 표시됩니다.  
  
> [!NOTE]
> The `My.Application.DoEvents` method does not process events in exactly the same way as the form does. To allow the form to handle the events directly, you can use multithreading. For more information, see [Managed Threading](../../../standard/threading/index.md).  
  
## <a name="see-also"></a>참조

- [이벤트](../../../visual-basic/programming-guide/language-features/events/index.md)
- [Event 문](../../../visual-basic/language-reference/statements/event-statement.md)
- [AddHandler 문](../../../visual-basic/language-reference/statements/addhandler-statement.md)
- [RemoveHandler 문](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
