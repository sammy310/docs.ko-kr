---
title: 다중 창 사용자 인터페이스 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- SplitContainer control [Windows Forms], examples
- ListView control [Windows Forms], examples
- RichTextBox control [Windows Forms], examples
- Panel control [Windows Forms], examples
- TreeView control [Windows Forms], examples
- Splitter control [Windows Forms], examples
ms.assetid: e79f6bcc-3740-4d1e-b46a-c5594d9b7327
ms.openlocfilehash: 4b168a6d566e20814d4403f90e157d80efe3bf12
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731342"
---
# <a name="how-to-create-a-multipane-user-interface-with-windows-forms"></a><span data-ttu-id="4fc51-102">방법: Windows Forms으로 다중 창 사용자 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="4fc51-102">How to: Create a Multipane User Interface with Windows Forms</span></span>
<span data-ttu-id="4fc51-103">다음 절차에서는 **폴더** 목록, **메시지** 창 및 **미리 보기** 창을 사용 하 여 Microsoft Outlook에서 사용 되는 것과 유사한 다중 창 사용자 인터페이스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-103">In the following procedure, you will create a multipane user interface that is similar to the one used in Microsoft Outlook, with a **Folder** list, a **Messages** pane, and a **Preview** pane.</span></span> <span data-ttu-id="4fc51-104">이러한 정렬은 폼을 사용 하 여 도킹 컨트롤을 통해 주로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-104">This arrangement is achieved chiefly through docking controls with the form.</span></span>  
  
 <span data-ttu-id="4fc51-105">컨트롤을 도킹할 때 컨트롤이 고정 되는 부모 컨테이너의 가장자리를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-105">When you dock a control, you determine which edge of the parent container a control is fastened to.</span></span> <span data-ttu-id="4fc51-106">따라서 <xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성을 <xref:System.Windows.Forms.DockStyle.Right>로 설정 하면 컨트롤의 오른쪽 가장자리가 부모 컨트롤의 오른쪽 가장자리에 도킹 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-106">Thus, if you set the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property to <xref:System.Windows.Forms.DockStyle.Right>, the right edge of the control will be docked to the right edge of its parent control.</span></span> <span data-ttu-id="4fc51-107">또한 컨트롤의 도킹 된 가장자리는 컨테이너 컨트롤의 크기에 맞게 조정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-107">Additionally, the docked edge of the control is resized to match that of its container control.</span></span> <span data-ttu-id="4fc51-108"><xref:System.Windows.Forms.SplitContainer.Dock%2A> 속성의 작동 방식에 대 한 자세한 내용은 [방법: Windows Forms에 컨트롤 도킹](how-to-dock-controls-on-windows-forms.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4fc51-108">For more information about how the <xref:System.Windows.Forms.SplitContainer.Dock%2A> property works, see [How to: Dock Controls on Windows Forms](how-to-dock-controls-on-windows-forms.md).</span></span>  
  
 <span data-ttu-id="4fc51-109">이 절차에서는 응용 프로그램이 Microsoft Outlook을 모방 하는 기능을 추가 하는 것이 아니라 폼의 <xref:System.Windows.Forms.SplitContainer> 및 기타 컨트롤을 정렬 하는 방법을 집중적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-109">This procedure focuses on arranging the <xref:System.Windows.Forms.SplitContainer> and the other controls on the form, not on adding functionality to make the application mimic Microsoft Outlook.</span></span>  
  
 <span data-ttu-id="4fc51-110">이 사용자 인터페이스를 만들려면 왼쪽 패널에서 <xref:System.Windows.Forms.TreeView> 컨트롤을 포함 하는 <xref:System.Windows.Forms.SplitContainer> 컨트롤 내에 모든 컨트롤을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-110">To create this user interface, you place all the controls within a <xref:System.Windows.Forms.SplitContainer> control, which contains a <xref:System.Windows.Forms.TreeView> control in the left-hand panel.</span></span> <span data-ttu-id="4fc51-111"><xref:System.Windows.Forms.SplitContainer> 컨트롤의 오른쪽 패널에는 <xref:System.Windows.Forms.RichTextBox> 컨트롤 위에 <xref:System.Windows.Forms.ListView> 컨트롤을 포함 하는 두 번째 <xref:System.Windows.Forms.SplitContainer> 컨트롤이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-111">The right-hand panel of the <xref:System.Windows.Forms.SplitContainer> control contains a second <xref:System.Windows.Forms.SplitContainer> control with a <xref:System.Windows.Forms.ListView> control above a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="4fc51-112">이러한 <xref:System.Windows.Forms.SplitContainer> 컨트롤은 폼에서 다른 컨트롤의 크기를 독립적으로 조정할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-112">These <xref:System.Windows.Forms.SplitContainer> controls enable independent resizing of the other controls on the form.</span></span> <span data-ttu-id="4fc51-113">사용자 고유의 사용자 지정 사용자 인터페이스를 만들 수 있도록이 절차의 기술을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-113">You can adapt the techniques in this procedure to craft custom user interfaces of your own.</span></span>  
  
### <a name="to-create-an-outlook-style-user-interface-programmatically"></a><span data-ttu-id="4fc51-114">프로그래밍 방식으로 Outlook 스타일 사용자 인터페이스를 만들려면</span><span class="sxs-lookup"><span data-stu-id="4fc51-114">To create an Outlook-style user interface programmatically</span></span>  
  
1. <span data-ttu-id="4fc51-115">폼 내에서 사용자 인터페이스를 구성 하는 각 컨트롤을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-115">Within a form, declare each control that comprises your user interface.</span></span> <span data-ttu-id="4fc51-116">이 예에서는 <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>및 <xref:System.Windows.Forms.RichTextBox> 컨트롤을 사용 하 여 Microsoft Outlook 사용자 인터페이스를 모방 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-116">For this example, use the <xref:System.Windows.Forms.TreeView>, <xref:System.Windows.Forms.ListView>, <xref:System.Windows.Forms.SplitContainer>, and <xref:System.Windows.Forms.RichTextBox> controls to mimic the Microsoft Outlook user interface.</span></span>  
  
    ```vb  
    Private WithEvents treeView1 As System.Windows.Forms.TreeView  
    Private WithEvents listView1 As System.Windows.Forms.ListView  
    Private WithEvents richTextBox1 As System.Windows.Forms.RichTextBox  
    Private WithEvents splitContainer1 As _  
        System.Windows.Forms.SplitContainer  
    Private WithEvents splitContainer2 As _  
        System.Windows.Forms.SplitContainer  
    ```  
  
    ```csharp  
    private System.Windows.Forms.TreeView treeView1;  
    private System.Windows.Forms.ListView listView1;  
    private System.Windows.Forms.RichTextBox richTextBox1;  
    private System.Windows.Forms. SplitContainer splitContainer2;  
    private System.Windows.Forms. SplitContainer splitContainer1;  
    ```  
  
2. <span data-ttu-id="4fc51-117">사용자 인터페이스를 정의 하는 프로시저를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-117">Create a procedure that defines your user interface.</span></span> <span data-ttu-id="4fc51-118">다음 코드는 폼이 Microsoft Outlook의 사용자 인터페이스와 비슷하게 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-118">The following code sets the properties so that the form will resemble the user interface in Microsoft Outlook.</span></span> <span data-ttu-id="4fc51-119">그러나 다른 컨트롤을 사용 하거나 다르게 도킹 하면 유연 하 게 다른 사용자 인터페이스를 쉽게 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-119">However, by using other controls or docking them differently, it is just as easy to create other user interfaces that are equally flexible.</span></span>  
  
    ```vb  
    Public Sub CreateOutlookUI()  
        ' Create an instance of each control being used.  
        Me.components = New System.ComponentModel.Container()  
        Me.treeView1 = New System.Windows.Forms.TreeView()  
        Me.listView1 = New System.Windows.Forms.ListView()  
        Me.richTextBox1 = New System.Windows.Forms.RichTextBox()  
        Me.splitContainer1 = New System.Windows.Forms.SplitContainer()  
        Me.splitContainer2= New System.Windows.Forms. SplitContainer()  
  
        ' Should you develop this into a working application,  
        ' use the AddHandler method to hook up event procedures here.  
  
        ' Set properties of TreeView control.  
        ' Use the With statement to avoid repetitive code.  
        With Me.treeView1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 0  
            .Nodes.Add("treeView")  
        End With  
  
    ' Set properties of ListView control.  
       With Me.listView1  
          .Dock = System.Windows.Forms.DockStyle.Top  
          .TabIndex = 2  
          .Items.Add("listView")  
       End With  
  
    ' Set properties of RichTextBox control.  
       With Me.richTextBox1  
          .Dock = System.Windows.Forms.DockStyle.Fill  
          .TabIndex = 3  
          .Text = "richTextBox1"  
       End With  
  
        ' Set properties of the first SplitContainer control.  
        With Me.splitContainer1  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 1  
            .SplitterWidth = 4  
            .SplitterDistance = 150  
            .Orientation = Orientation.Horizontal  
            .Panel1.Controls.Add(Me.listView1)  
            .Panel2.Controls.Add(Me.richTextBox1)  
    End With  
  
        ' Set properties of the second SplitContainer control.  
        With Me.splitContainer2  
            .Dock = System.Windows.Forms.DockStyle.Fill  
            .TabIndex = 4  
            .SplitterWidth = 4  
            .SplitterDistance = 100  
            .Panel1.Controls.Add(Me.treeView1)  
            .Panel2.Controls.Add(Me.SplitContainer1)  
    End With  
  
    ' Add the main SplitContainer control to the form.  
        Me.Controls.Add(Me.splitContainer2)  
        Me.Text = "Intricate UI Example"  
    End Sub  
    ```  
  
    ```csharp  
    public void createOutlookUI()  
    {  
        // Create an instance of each control being used.  
        treeView1 = new System.Windows.Forms.TreeView();  
        listView1 = new System.Windows.Forms.ListView();  
        richTextBox1 = new System.Windows.Forms.RichTextBox();  
        splitContainer2 = new System.Windows.Forms.SplitContainer();  
        splitContainer1 = new System.Windows.Forms.SplitContainer();  
  
        // Insert code here to hook up event methods.  
  
        // Set properties of TreeView control.  
        treeView1.Dock = System.Windows.Forms.DockStyle.Fill;  
        treeView1.TabIndex = 0;  
        treeView1.Nodes.Add("treeView");  
  
        // Set properties of ListView control.  
        listView1.Dock = System.Windows.Forms.DockStyle.Top;  
        listView1.TabIndex = 2;  
        listView1.Items.Add("listView");  
  
        // Set properties of RichTextBox control.  
        richTextBox1.Dock = System.Windows.Forms.DockStyle.Fill;  
        richTextBox1.TabIndex = 3;  
        richTextBox1.Text = "richTextBox1";  
  
        // Set properties of first SplitContainer control.  
        splitContainer1.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 1;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 150;  
        splitContainer2.Orientation = Orientation.Horizontal;  
        splitContainer2.Panel1.Controls.Add(this.listView1);  
        splitContainer2.Panel1.Controls.Add(this.richTextBox1);  
  
        // Set properties of second SplitContainer control.  
        splitContainer2.Dock = System.Windows.Forms.DockStyle.Fill;  
        splitContainer2.TabIndex = 4;  
        splitContainer2.SplitterWidth = 4;  
        splitContainer2.SplitterDistance = 100;  
        splitContainer2.Panel1.Controls.Add(this.treeView1);  
        splitContainer2.Panel1.Controls.Add(this.splitContainer1);  
  
        // Add the main SplitContainer control to the form.  
        this.Controls.Add(this.splitContainer2);  
        this.Text = "Intricate UI Example";  
    }  
    ```  
  
3. <span data-ttu-id="4fc51-120">Visual Basic에서 방금 만든 프로시저에 대 한 호출을 `New()` 프로시저에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-120">In Visual Basic, add a call to the procedure you just created in the `New()` procedure.</span></span> <span data-ttu-id="4fc51-121">시각적 개체 C#에서 form 클래스의 생성자에 다음 코드 줄을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc51-121">In Visual C#, add this line of code to the constructor for the form class.</span></span>  
  
    ```vb  
    ' Add this to the New procedure.  
    CreateOutlookUI()  
    ```  
  
    ```csharp  
    // Add this to the form class's constructor.  
    createOutlookUI();  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="4fc51-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4fc51-122">See also</span></span>

- <xref:System.Windows.Forms.SplitContainer>
- [<span data-ttu-id="4fc51-123">SplitContainer 컨트롤</span><span class="sxs-lookup"><span data-stu-id="4fc51-123">SplitContainer Control</span></span>](splitcontainer-control-windows-forms.md)
- [<span data-ttu-id="4fc51-124">방법: 디자이너를 사용하여 Windows Forms으로 다중 창 사용자 인터페이스 만들기</span><span class="sxs-lookup"><span data-stu-id="4fc51-124">How to: Create a Multipane User Interface with Windows Forms Using the Designer</span></span>](create-a-multipane-user-interface-with-wf-using-the-designer.md)
