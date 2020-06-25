---
title: '연습: 끌어서 놓기 작업 수행'
description: System.windows.dragdrop.dragenter>, System.windows.dragdrop.dragleave> 및 DragDrop 이벤트를 비롯 한 일련의 이벤트를 처리 하 여 Windows Forms에서 끌어서 놓기 작업을 수행 하는 방법을 알아봅니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Windows Forms, drag and drop operations
- drag and drop [Windows Forms], Windows Forms
ms.assetid: eb66f6bf-4a7d-4c2d-b276-40fefb2d3b6c
ms.openlocfilehash: 83bfda875e2fdec3981bbcb8f8f7be00db342440
ms.sourcegitcommit: dc2feef0794cf41dbac1451a13b8183258566c0e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/24/2020
ms.locfileid: "85325815"
---
# <a name="walkthrough-performing-a-drag-and-drop-operation-in-windows-forms"></a><span data-ttu-id="8d9f5-103">연습: Windows Forms에서 끌어서 놓기 작업 수행</span><span class="sxs-lookup"><span data-stu-id="8d9f5-103">Walkthrough: Performing a Drag-and-Drop Operation in Windows Forms</span></span>
<span data-ttu-id="8d9f5-104">Windows 기반 응용 프로그램 내에서 끌어서 놓기 작업을 수행 하려면 일련의 이벤트, 특히 <xref:System.Windows.Forms.Control.DragEnter> , 및 이벤트를 처리 해야 합니다 <xref:System.Windows.Forms.Control.DragLeave> <xref:System.Windows.Forms.Control.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="8d9f5-104">To perform drag-and-drop operations within Windows-based applications you must handle a series of events, most notably the <xref:System.Windows.Forms.Control.DragEnter>, <xref:System.Windows.Forms.Control.DragLeave>, and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span> <span data-ttu-id="8d9f5-105">이러한 이벤트의 이벤트 인수에서 제공하는 정보를 사용하면 끌어서 놓기 작업을 쉽게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-105">By working with the information available in the event arguments of these events, you can easily facilitate drag-and-drop operations.</span></span>  
  
## <a name="dragging-data"></a><span data-ttu-id="8d9f5-106">데이터 끌기</span><span class="sxs-lookup"><span data-stu-id="8d9f5-106">Dragging Data</span></span>  
 <span data-ttu-id="8d9f5-107">모든 끌어서 놓기 작업은 끌기에서 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-107">All drag-and-drop operations begin with dragging.</span></span> <span data-ttu-id="8d9f5-108">끌기를 시작할 때 데이터를 수집할 수 있도록 하는 기능을 메서드에서 구현할 수 <xref:System.Windows.Forms.Control.DoDragDrop%2A> 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-108">The functionality to enable data to be collected when dragging begins is implemented in the <xref:System.Windows.Forms.Control.DoDragDrop%2A> method.</span></span>  
  
 <span data-ttu-id="8d9f5-109">다음 예제에서는 <xref:System.Windows.Forms.Control.MouseDown> 가장 직관적 이기 때문에 끌기 작업을 시작 하는 데 사용 됩니다. 대부분의 끌어서 놓기 작업은 마우스 단추를 누른 상태로 시작 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-109">In the following example, the <xref:System.Windows.Forms.Control.MouseDown> event is used to start the drag operation because it is the most intuitive (most drag-and-drop actions begin with the mouse button being depressed).</span></span> <span data-ttu-id="8d9f5-110">그러나 모든 이벤트는 끌어서 놓기 프로시저를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-110">However, remember that any event could be used to initiate a drag-and-drop procedure.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8d9f5-111">특정 컨트롤에는 사용자 지정 끌기 관련 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-111">Certain controls have custom drag-specific events.</span></span> <span data-ttu-id="8d9f5-112">예를 들어 <xref:System.Windows.Forms.ListView> 및 컨트롤에는 <xref:System.Windows.Forms.TreeView> <xref:System.Windows.Forms.TreeView.ItemDrag> 이벤트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-112">The <xref:System.Windows.Forms.ListView> and <xref:System.Windows.Forms.TreeView> controls, for example, have an <xref:System.Windows.Forms.TreeView.ItemDrag> event.</span></span>  
  
#### <a name="to-start-a-drag-operation"></a><span data-ttu-id="8d9f5-113">끌기 작업을 시작하려면</span><span class="sxs-lookup"><span data-stu-id="8d9f5-113">To start a drag operation</span></span>  
  
1. <span data-ttu-id="8d9f5-114"><xref:System.Windows.Forms.Control.MouseDown>끌기가 시작 되는 컨트롤에 대 한 이벤트에서 메서드를 사용 `DoDragDrop` 하 여 끌어올 데이터를 설정 하 고 허용 되는 끌기 효과를 갖게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-114">In the <xref:System.Windows.Forms.Control.MouseDown> event for the control where the drag will begin, use the `DoDragDrop` method to set the data to be dragged and the allowed effect dragging will have.</span></span> <span data-ttu-id="8d9f5-115">자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Data%2A> 및 <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-115">For more information, see <xref:System.Windows.Forms.DragEventArgs.Data%2A> and <xref:System.Windows.Forms.DragEventArgs.AllowedEffect%2A>.</span></span>  
  
     <span data-ttu-id="8d9f5-116">다음 예제에서는 끌기 작업을 시작하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-116">The following example shows how to initiate a drag operation.</span></span> <span data-ttu-id="8d9f5-117">끌기가 시작 되는 컨트롤은 컨트롤이 고 <xref:System.Windows.Forms.Button> , 끌고 있는 데이터는 <xref:System.Windows.Forms.Control.Text%2A> 컨트롤의 속성을 나타내는 문자열이 <xref:System.Windows.Forms.Button> 고, 허용 되는 효과는 복사 또는 이동 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-117">The control where the drag begins is a <xref:System.Windows.Forms.Button> control, the data being dragged is the string representing the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control, and the allowed effects are either copying or moving.</span></span>  
  
    ```vb  
    Private Sub Button1_MouseDown(ByVal sender As Object, ByVal e As System.Windows.Forms.MouseEventArgs) Handles Button1.MouseDown  
       Button1.DoDragDrop(Button1.Text, DragDropEffects.Copy Or DragDropEffects.Move)  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_MouseDown(object sender,
    System.Windows.Forms.MouseEventArgs e)  
    {  
       button1.DoDragDrop(button1.Text, DragDropEffects.Copy |
          DragDropEffects.Move);  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="8d9f5-118">모든 데이터를 메서드에서 매개 변수로 사용할 수 있습니다 `DoDragDrop` . 위의 예제에서 <xref:System.Windows.Forms.Control.Text%2A> <xref:System.Windows.Forms.Button> 속성은 컨트롤에서 끌고 있는 위치와 관련 되어 있으므로 값을 하드 코딩 하거나 데이터 집합에서 데이터를 검색 하는 대신 컨트롤의 속성을 사용 했습니다 <xref:System.Windows.Forms.Button> .</span><span class="sxs-lookup"><span data-stu-id="8d9f5-118">Any data can be used as a parameter in the `DoDragDrop` method; in the example above, the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.Button> control was used (rather than hard-coding a value or retrieving data from a dataset) because the property was related to the location being dragged from (the <xref:System.Windows.Forms.Button> control).</span></span> <span data-ttu-id="8d9f5-119">끌어서 놓기 작업을 Windows 기반 애플리케이션에 통합할 때 이 점을 명심해 주세요.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-119">Keep this in mind as you incorporate drag-and-drop operations into your Windows-based applications.</span></span>  
  
 <span data-ttu-id="8d9f5-120">끌기 작업이 적용 되는 동안 <xref:System.Windows.Forms.Control.QueryContinueDrag> 시스템의 "권한 요청"을 통해 끌기 작업을 계속 하는 이벤트를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-120">While a drag operation is in effect, you can handle the <xref:System.Windows.Forms.Control.QueryContinueDrag> event, which "asks permission" of the system to continue the drag operation.</span></span> <span data-ttu-id="8d9f5-121">이 메서드를 처리할 때 <xref:System.Windows.Forms.TreeNode> <xref:System.Windows.Forms.TreeView> 커서를 커서를 가져갈 때 컨트롤의를 확장 하는 것과 같이 끌기 작업에 영향을 주는 메서드를 호출 하는 것도 적절 한 지점입니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-121">When handling this method, it is also the appropriate point for you to call methods that will have an effect on the drag operation, such as expanding a <xref:System.Windows.Forms.TreeNode> in a <xref:System.Windows.Forms.TreeView> control when the cursor hovers over it.</span></span>  
  
## <a name="dropping-data"></a><span data-ttu-id="8d9f5-122">데이터 놓기</span><span class="sxs-lookup"><span data-stu-id="8d9f5-122">Dropping Data</span></span>  
 <span data-ttu-id="8d9f5-123">Windows Form 또는 컨트롤의 위치에서 데이터를 끌기 시작하면 당연히 다른 위치에 놓으려고 할 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-123">Once you have begun dragging data from a location on a Windows Form or control, you will naturally want to drop it somewhere.</span></span> <span data-ttu-id="8d9f5-124">데이터를 놓도록 올바르게 구성된 양식이나 컨트롤의 영역 위에서 움직이면 커서가 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-124">The cursor will change when it crosses an area of a form or control that is correctly configured for dropping data.</span></span> <span data-ttu-id="8d9f5-125">속성을 설정 <xref:System.Windows.Forms.Control.AllowDrop%2A> 하 고 및 이벤트를 처리 하 여 삭제 된 데이터를 허용 하도록 Windows Form 또는 컨트롤 내에서 영역을 만들 수 있습니다 <xref:System.Windows.Forms.Control.DragEnter> <xref:System.Windows.Forms.Control.DragDrop> .</span><span class="sxs-lookup"><span data-stu-id="8d9f5-125">Any area within a Windows Form or control can be made to accept dropped data by setting the <xref:System.Windows.Forms.Control.AllowDrop%2A> property and handling the <xref:System.Windows.Forms.Control.DragEnter> and <xref:System.Windows.Forms.Control.DragDrop> events.</span></span>  
  
#### <a name="to-perform-a-drop"></a><span data-ttu-id="8d9f5-126">놓기 작업을 수행하려면</span><span class="sxs-lookup"><span data-stu-id="8d9f5-126">To perform a drop</span></span>  
  
1. <span data-ttu-id="8d9f5-127">속성을 <xref:System.Windows.Forms.Control.AllowDrop%2A> true로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-127">Set the <xref:System.Windows.Forms.Control.AllowDrop%2A> property to true.</span></span>  
  
2. <span data-ttu-id="8d9f5-128">`DragEnter`놓기 작업이 발생 하는 컨트롤에 대 한 이벤트에서 끌고 있는 데이터가 허용 되는 형식 (이 경우) 인지 확인 <xref:System.Windows.Forms.Control.Text%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-128">In the `DragEnter` event for the control where the drop will occur, ensure that the data being dragged is of an acceptable type (in this case, <xref:System.Windows.Forms.Control.Text%2A>).</span></span> <span data-ttu-id="8d9f5-129">그런 다음 코드에서 열거형의 값에 대 한 drop이 발생할 때 발생 하는 효과를 설정 합니다 <xref:System.Windows.Forms.DragDropEffects> .</span><span class="sxs-lookup"><span data-stu-id="8d9f5-129">The code then sets the effect that will happen when the drop occurs to a value in the <xref:System.Windows.Forms.DragDropEffects> enumeration.</span></span> <span data-ttu-id="8d9f5-130">자세한 내용은 <xref:System.Windows.Forms.DragEventArgs.Effect%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-130">For more information, see <xref:System.Windows.Forms.DragEventArgs.Effect%2A>.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragEnter(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragEnter  
       If (e.Data.GetDataPresent(DataFormats.Text)) Then  
         e.Effect = DragDropEffects.Copy  
       Else  
         e.Effect = DragDropEffects.None  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragEnter(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       if (e.Data.GetDataPresent(DataFormats.Text))
          e.Effect = DragDropEffects.Copy;  
       else  
          e.Effect = DragDropEffects.None;  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="8d9f5-131">사용자 고유의 <xref:System.Windows.Forms.DataFormats> 개체를 <xref:System.Object> 메서드의 매개 변수로 지정 하 여 직접 정의할 수 있습니다 <xref:System.Windows.Forms.DataObject.SetData%2A> .</span><span class="sxs-lookup"><span data-stu-id="8d9f5-131">You can define your own <xref:System.Windows.Forms.DataFormats> by specifying your own object as the <xref:System.Object> parameter of the <xref:System.Windows.Forms.DataObject.SetData%2A> method.</span></span> <span data-ttu-id="8d9f5-132">이 작업을 수행할 때 지정된 개체는 직렬화(serialize)할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-132">Be sure, when doing this, that the object specified is serializable.</span></span> <span data-ttu-id="8d9f5-133">자세한 내용은 <xref:System.Runtime.Serialization.ISerializable>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-133">For more information, see <xref:System.Runtime.Serialization.ISerializable>.</span></span>  
  
3. <span data-ttu-id="8d9f5-134"><xref:System.Windows.Forms.Control.DragDrop>놓기 작업이 발생 하는 컨트롤에 대 한 이벤트에서 메서드를 사용 <xref:System.Windows.Forms.DataObject.GetData%2A> 하 여 끌고 있는 데이터를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-134">In the <xref:System.Windows.Forms.Control.DragDrop> event for the control where the drop will occur, use the <xref:System.Windows.Forms.DataObject.GetData%2A> method to retrieve the data being dragged.</span></span> <span data-ttu-id="8d9f5-135">자세한 내용은 <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-135">For more information, see <xref:System.Security.Cryptography.Xml.DataObject.Data%2A>.</span></span>  
  
     <span data-ttu-id="8d9f5-136">아래 예제에서 <xref:System.Windows.Forms.TextBox> 컨트롤은 놓기가 발생 하는 위치로 끌고 있는 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-136">In the example below, a <xref:System.Windows.Forms.TextBox> control is the control being dragged to (where the drop will occur).</span></span> <span data-ttu-id="8d9f5-137">이 코드는 <xref:System.Windows.Forms.Control.Text%2A> 컨트롤의 속성을 <xref:System.Windows.Forms.TextBox> 끌고 있는 데이터와 동일 하 게 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-137">The code sets the <xref:System.Windows.Forms.Control.Text%2A> property of the <xref:System.Windows.Forms.TextBox> control equal to the data being dragged.</span></span>  
  
    ```vb  
    Private Sub TextBox1_DragDrop(ByVal sender As Object, ByVal e As System.Windows.Forms.DragEventArgs) Handles TextBox1.DragDrop  
       TextBox1.Text = e.Data.GetData(DataFormats.Text).ToString  
    End Sub  
    ```  
  
    ```csharp  
    private void textBox1_DragDrop(object sender,
    System.Windows.Forms.DragEventArgs e)  
    {  
       textBox1.Text = e.Data.GetData(DataFormats.Text).ToString();  
    }  
    ```  
  
    > [!NOTE]
    > <span data-ttu-id="8d9f5-138">또한 속성을 사용 하 여 작업을 수행할 수 있습니다 <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> . 이렇게 하면 끌어서 놓기 작업 중에 눌린 키에 따라 특정 효과가 발생 합니다. 예를 들어 CTRL 키를 누를 때 끌어온 데이터를 복사 하는 것이 표준입니다.</span><span class="sxs-lookup"><span data-stu-id="8d9f5-138">Additionally, you can work with the <xref:System.Windows.Forms.DragEventArgs.KeyState%2A> property, so that, depending on keys depressed during the drag-and-drop operation, certain effects occur (for example, it is standard to copy the dragged data when the CTRL key is pressed).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d9f5-139">참조</span><span class="sxs-lookup"><span data-stu-id="8d9f5-139">See also</span></span>

- [<span data-ttu-id="8d9f5-140">방법: 클립보드에 데이터 추가</span><span class="sxs-lookup"><span data-stu-id="8d9f5-140">How to: Add Data to the Clipboard</span></span>](how-to-add-data-to-the-clipboard.md)
- [<span data-ttu-id="8d9f5-141">방법: 클립보드에서 데이터 검색</span><span class="sxs-lookup"><span data-stu-id="8d9f5-141">How to: Retrieve Data from the Clipboard</span></span>](how-to-retrieve-data-from-the-clipboard.md)
- [<span data-ttu-id="8d9f5-142">끌어서 놓기 작업 및 클립보드 지원</span><span class="sxs-lookup"><span data-stu-id="8d9f5-142">Drag-and-Drop Operations and Clipboard Support</span></span>](drag-and-drop-operations-and-clipboard-support.md)
