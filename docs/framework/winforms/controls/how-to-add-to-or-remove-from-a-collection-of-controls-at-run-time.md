---
title: '방법: 추가 하거나 런타임 시 컨트롤 컬렉션에서 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- run time [Windows Forms], removing controls
- controls [Windows Forms], adding using collections
- controls collections
- collections [Windows Forms], adding items
- run time [Windows Forms], adding controls
- controls [Windows Forms], removing using collections
ms.assetid: 771bf895-3d5f-469b-a324-3528f343657e
ms.openlocfilehash: 6ec4e41f5a3bee6302996f21afa81f2b5eeb9568
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57720893"
---
# <a name="how-to-add-to-or-remove-from-a-collection-of-controls-at-run-time"></a><span data-ttu-id="0577b-102">방법: 추가 하거나 런타임 시 컨트롤 컬렉션에서 제거</span><span class="sxs-lookup"><span data-stu-id="0577b-102">How to: Add to or Remove from a Collection of Controls at Run Time</span></span>
<span data-ttu-id="0577b-103">응용 프로그램 개발의 일반적인 작업은에 컨트롤 추가 및 컨트롤을 양식의 컨테이너 컨트롤에서 제거 (같은 합니다 <xref:System.Windows.Forms.Panel> 또는 <xref:System.Windows.Forms.GroupBox> 컨트롤 또는 양식 자체).</span><span class="sxs-lookup"><span data-stu-id="0577b-103">Common tasks in application development are adding controls to and removing controls from any container control on your forms (such as the <xref:System.Windows.Forms.Panel> or <xref:System.Windows.Forms.GroupBox> control, or even the form itself).</span></span> <span data-ttu-id="0577b-104">디자인 타임에 컨트롤을 패널이나 그룹 상자로 직접 끌어 놓을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-104">At design time, controls can be dragged directly onto a panel or group box.</span></span> <span data-ttu-id="0577b-105">런타임 시 이러한 컨트롤은 `Controls` 컬렉션을 유지 관리하고 여기서 배치된 컨트롤을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-105">At run time, these controls maintain a `Controls` collection, which keeps track of what controls are placed on them.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0577b-106">다음 코드 예제는 안에 있는 컨트롤의 컬렉션을 유지하는 모든 컨트롤에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-106">The following code example applies to any control that maintains a collection of controls within it.</span></span>  
  
### <a name="to-add-a-control-to-a-collection-programmatically"></a><span data-ttu-id="0577b-107">프로그래밍 방식으로 컬렉션에 컨트롤을 추가하려면</span><span class="sxs-lookup"><span data-stu-id="0577b-107">To add a control to a collection programmatically</span></span>  
  
1.  <span data-ttu-id="0577b-108">추가될 컨트롤의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-108">Create an instance of the control to be added.</span></span>  
  
2.  <span data-ttu-id="0577b-109">새 컨트롤의 속성을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-109">Set properties of the new control.</span></span>  
  
3.  <span data-ttu-id="0577b-110">부모 컨트롤의 `Controls` 컬렉션에 컨트롤을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-110">Add the control to the `Controls` collection of the parent control.</span></span>  
  
     <span data-ttu-id="0577b-111">다음 코드 예제에는 인스턴스를 만드는 방법을 보여 줍니다는 <xref:System.Windows.Forms.Button> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-111">The following code example shows how to create an instance of the <xref:System.Windows.Forms.Button> control.</span></span> <span data-ttu-id="0577b-112">된 폼이 있어야 하는 <xref:System.Windows.Forms.Panel> 단추의 이벤트 처리 메서드를 만들고 컨트롤과 `NewPanelButton_Click`, 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-112">It requires a form with a <xref:System.Windows.Forms.Panel> control and that the event-handling method for the button being created, `NewPanelButton_Click`, already exists.</span></span>  
  
    ```vb  
    Public NewPanelButton As New Button()  
  
    Public Sub AddNewControl()  
       ' The Add method will accept as a parameter any object that derives  
       ' from the Control class. In this case, it is a Button control.  
       Panel1.Controls.Add(NewPanelButton)  
       ' The event handler indicated for the Click event in the code   
       ' below is used as an example. Substite the appropriate event  
       ' handler for your application.  
       AddHandler NewPanelButton.Click, AddressOf NewPanelButton_Click  
    End Sub  
    ```  
  
    ```csharp  
    public Button newPanelButton = new Button();  
  
    public void addNewControl()  
    {   
       // The Add method will accept as a parameter any object that derives  
       // from the Control class. In this case, it is a Button control.  
       panel1.Controls.Add(newPanelButton);  
       // The event handler indicated for the Click event in the code   
       // below is used as an example. Substitute the appropriate event  
       // handler for your application.  
       this.newPanelButton.Click += new System.EventHandler(this. NewPanelButton_Click);  
    }  
    ```  
  
### <a name="to-remove-controls-from-a-collection-programmatically"></a><span data-ttu-id="0577b-113">컬렉션에서 컨트롤을 프로그래밍 방식으로 제거하려면</span><span class="sxs-lookup"><span data-stu-id="0577b-113">To remove controls from a collection programmatically</span></span>  
  
1.  <span data-ttu-id="0577b-114">이벤트에서 이벤트 처리기를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-114">Remove the event handler from the event.</span></span> <span data-ttu-id="0577b-115">Visual basic에서 사용 하 여는 [RemoveHandler 문](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) 키워드; 시각적 개체에 C#를 사용 합니다 [-= 연산자 (C# 참조)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span><span class="sxs-lookup"><span data-stu-id="0577b-115">In Visual Basic, use the [RemoveHandler Statement](~/docs/visual-basic/language-reference/statements/removehandler-statement.md) keyword; in Visual C#, use the [-= Operator (C# Reference)](~/docs/csharp/language-reference/operators/subtraction-assignment-operator.md).</span></span>  
  
2.  <span data-ttu-id="0577b-116">`Remove` 메서드를 사용하여 패널의 `Controls` 컬렉션에서 원하는 컨트롤을 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-116">Use the `Remove` method to delete the desired control from the panel's `Controls` collection.</span></span>  
  
3.  <span data-ttu-id="0577b-117">호출 된 <xref:System.Windows.Forms.Control.Dispose%2A> 컨트롤에서 사용 하는 모든 리소스를 해제 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0577b-117">Call the <xref:System.Windows.Forms.Control.Dispose%2A> method to release all the resources used by the control.</span></span>  
  
    ```vb  
    Public Sub RemoveControl()  
    ' NOTE: The code below uses the instance of   
    ' the button (NewPanelButton) from the previous example.  
       If Panel1.Controls.Contains(NewPanelButton) Then  
          RemoveHandler NewPanelButton.Click, AddressOf _   
             NewPanelButton_Click  
          Panel1.Controls.Remove(NewPanelButton)  
          NewPanelButton.Dispose()  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void removeControl(object sender, System.EventArgs e)  
    {  
    // NOTE: The code below uses the instance of   
    // the button (newPanelButton) from the previous example.  
       if(panel1.Controls.Contains(newPanelButton))  
       {  
          this.newPanelButton.Click -= new System.EventHandler(this.   
             NewPanelButton_Click);  
          panel1.Controls.Remove(newPanelButton);  
          newPanelButton.Dispose();  
       }  
    }  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="0577b-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="0577b-118">See also</span></span>
- <xref:System.Windows.Forms.Panel>
- [<span data-ttu-id="0577b-119">Panel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="0577b-119">Panel Control</span></span>](panel-control-windows-forms.md)
