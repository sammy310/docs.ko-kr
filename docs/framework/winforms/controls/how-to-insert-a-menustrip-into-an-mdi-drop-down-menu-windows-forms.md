---
title: '방법: MDI 드롭다운 메뉴에 MenuStrip 삽입'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MenuStrip control [Windows Forms], inserting
- MenuStrip control [Windows Forms], merging
- MDI [Windows Forms], merging menu items
ms.assetid: 0fad444e-26d9-49af-8860-044d9c10d608
ms.openlocfilehash: 6e189dd159c48b5779679d0563fab85e9b848992
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76736409"
---
# <a name="how-to-insert-a-menustrip-into-an-mdi-drop-down-menu-windows-forms"></a><span data-ttu-id="57c34-102">방법: MDI 드롭다운 메뉴에 MenuStrip 삽입(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="57c34-102">How to: Insert a MenuStrip into an MDI Drop-Down Menu (Windows Forms)</span></span>
<span data-ttu-id="57c34-103">일부 애플리케이션에서는 MDI(다중 문서 인터페이스) 자식 창의 종류가 MDI 부모 창과 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-103">In some applications, the kind of a multiple-document interface (MDI) child window can be different from the MDI parent window.</span></span> <span data-ttu-id="57c34-104">예를 들어 MDI 부모는 스프레드시트이고 MDI 자식은 차트일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-104">For example, the MDI parent might be a spreadsheet, and the MDI child might be a chart.</span></span> <span data-ttu-id="57c34-105">이 경우 다른 종류의 MDI 자식 창이 활성화될 때 MDI 부모 메뉴의 내용을 MDI 자식 메뉴의 내용으로 업데이트하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-105">In that case, you want to update the contents of the MDI parent's menu with the contents of the MDI child's menu as MDI child windows of different kinds are activated.</span></span>  
  
 <span data-ttu-id="57c34-106">다음 절차에서는 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 사용 하 여 MDI 자식 메뉴의 메뉴 항목 그룹을 MDI 부모 메뉴의 드롭다운 부분에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-106">The following procedure uses the <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>, and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties to insert a group of menu items from the MDI child menu into the drop-down part of the MDI parent menu.</span></span> <span data-ttu-id="57c34-107">MDI 자식 창을 닫으면 MDI 부모에서 삽입 된 메뉴 항목이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-107">Closing the MDI child window removes the inserted menu items from the MDI parent.</span></span>  
  
### <a name="to-insert-a-menustrip-into-an-mdi-drop-down-menu"></a><span data-ttu-id="57c34-108">MDI 드롭다운 메뉴에 MenuStrip을 삽입 하려면</span><span class="sxs-lookup"><span data-stu-id="57c34-108">To insert a MenuStrip into an MDI drop-down menu</span></span>  
  
1. <span data-ttu-id="57c34-109">폼을 만들고 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-109">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="57c34-110">`Form1`에 <xref:System.Windows.Forms.MenuStrip>을 추가하고 <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-110">Add a <xref:System.Windows.Forms.MenuStrip> to `Form1` and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the <xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
3. <span data-ttu-id="57c34-111">`Form1`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-111">Add a top-level menu item to the `Form1`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.Control.Text%2A> property to `&File`.</span></span>  
  
4. <span data-ttu-id="57c34-112">`&File` 메뉴 항목에 세 개의 하위 메뉴 항목을 추가 하 고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`, `&Import from`및 `E&xit`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-112">Add three submenu items to the `&File` menu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Open`, `&Import from`, and `E&xit`.</span></span>  
  
5. <span data-ttu-id="57c34-113">`&Import from` 하위 메뉴 항목에 두 개의 하위 메뉴 항목을 추가 하 고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Word` 및 `&Excel`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-113">Add two submenu items to the `&Import from` submenu item and set their <xref:System.Windows.Forms.ToolStripItem.Text%2A> properties to `&Word` and `&Excel`.</span></span>  
  
6. <span data-ttu-id="57c34-114">프로젝트에 폼을 추가하고, 폼에 <xref:System.Windows.Forms.MenuStrip>을 추가한 다음 `Form2`<xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-114">Add a form to the project, add a <xref:System.Windows.Forms.MenuStrip> to the form, and set the <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A> property of the `Form2`<xref:System.Windows.Forms.MenuStrip> to `true`.</span></span>  
  
7. <span data-ttu-id="57c34-115">`Form2`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&File`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-115">Add a top-level menu item to the `Form2`<xref:System.Windows.Forms.MenuStrip> and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&File`.</span></span>  
  
8. <span data-ttu-id="57c34-116">`Form2`의 `&File` 메뉴에 하위 메뉴 항목을 추가 하 여 <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`및 또 다른 <xref:System.Windows.Forms.ToolStripSeparator>순서로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-116">Add submenu items to the `&File` menu of `Form2` in the following order: a <xref:System.Windows.Forms.ToolStripSeparator>, `&Save`, `Save and &Close`, and another <xref:System.Windows.Forms.ToolStripSeparator>.</span></span>  
  
9. <span data-ttu-id="57c34-117">다음 표와 같이 `Form2` 메뉴 항목의 <xref:System.Windows.Forms.MergeAction> 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-117">Set the <xref:System.Windows.Forms.MergeAction> and <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> properties of the `Form2` menu items as shown in the following table.</span></span>  
  
    |<span data-ttu-id="57c34-118">Form2 메뉴 항목</span><span class="sxs-lookup"><span data-stu-id="57c34-118">Form2 menu item</span></span>|<span data-ttu-id="57c34-119">MergeAction 값</span><span class="sxs-lookup"><span data-stu-id="57c34-119">MergeAction value</span></span>|<span data-ttu-id="57c34-120">MergeIndex 값</span><span class="sxs-lookup"><span data-stu-id="57c34-120">MergeIndex value</span></span>|  
    |---------------------|-----------------------|----------------------|  
    |<span data-ttu-id="57c34-121">File</span><span class="sxs-lookup"><span data-stu-id="57c34-121">File</span></span>|<span data-ttu-id="57c34-122">MatchOnly</span><span class="sxs-lookup"><span data-stu-id="57c34-122">MatchOnly</span></span>|<span data-ttu-id="57c34-123">-1</span><span class="sxs-lookup"><span data-stu-id="57c34-123">-1</span></span>|  
    |<span data-ttu-id="57c34-124">구분 기호</span><span class="sxs-lookup"><span data-stu-id="57c34-124">Separator</span></span>|<span data-ttu-id="57c34-125">Insert</span><span class="sxs-lookup"><span data-stu-id="57c34-125">Insert</span></span>|<span data-ttu-id="57c34-126">2</span><span class="sxs-lookup"><span data-stu-id="57c34-126">2</span></span>|  
    |<span data-ttu-id="57c34-127">저장</span><span class="sxs-lookup"><span data-stu-id="57c34-127">Save</span></span>|<span data-ttu-id="57c34-128">Insert</span><span class="sxs-lookup"><span data-stu-id="57c34-128">Insert</span></span>|<span data-ttu-id="57c34-129">3</span><span class="sxs-lookup"><span data-stu-id="57c34-129">3</span></span>|  
    |<span data-ttu-id="57c34-130">저장 후 닫기</span><span class="sxs-lookup"><span data-stu-id="57c34-130">Save and Close</span></span>|<span data-ttu-id="57c34-131">Insert</span><span class="sxs-lookup"><span data-stu-id="57c34-131">Insert</span></span>|<span data-ttu-id="57c34-132">4</span><span class="sxs-lookup"><span data-stu-id="57c34-132">4</span></span>|  
    |<span data-ttu-id="57c34-133">구분 기호</span><span class="sxs-lookup"><span data-stu-id="57c34-133">Separator</span></span>|<span data-ttu-id="57c34-134">Insert</span><span class="sxs-lookup"><span data-stu-id="57c34-134">Insert</span></span>|<span data-ttu-id="57c34-135">5</span><span class="sxs-lookup"><span data-stu-id="57c34-135">5</span></span>|  
  
10. <span data-ttu-id="57c34-136">`&Open`<xref:System.Windows.Forms.ToolStripMenuItem>의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-136">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
11. <span data-ttu-id="57c34-137">이벤트 처리기 내에서 다음 코드 예제와 비슷한 코드를 삽입하여 `Form2`의 새 인스턴스를 만들고 `Form1`의 MDI 자식으로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-137">Within the event handler, insert code similar to the following code example to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, _  
    ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void openToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
12. <span data-ttu-id="57c34-138">`&Open`<xref:System.Windows.Forms.ToolStripMenuItem>에 다음 코드 예제와 비슷한 코드를 배치하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-138">Place code similar to the following code example in the `&Open`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="57c34-139">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="57c34-139">Compiling the Code</span></span>  
 <span data-ttu-id="57c34-140">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="57c34-140">This example requires:</span></span>  
  
- <span data-ttu-id="57c34-141">`Form1` 및 `Form2`라는 두 개의 <xref:System.Windows.Forms.Form> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="57c34-141">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="57c34-142">`menuStrip1`이라는 `Form1`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 및 `menuStrip2`라는 `Form2`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="57c34-142">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="57c34-143"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="57c34-143">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57c34-144">참조</span><span class="sxs-lookup"><span data-stu-id="57c34-144">See also</span></span>

- [<span data-ttu-id="57c34-145">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="57c34-145">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="57c34-146">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="57c34-146">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="57c34-147">MenuStrip 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="57c34-147">MenuStrip Control Overview</span></span>](menustrip-control-overview-windows-forms.md)
