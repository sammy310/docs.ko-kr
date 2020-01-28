---
title: '방법: MenuStrip이 포함된 MDI 창 목록 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- MDI [Windows Forms], creating window lists
- MenuStrip control [Windows Forms], creating window lists
ms.assetid: 04fb414b-811f-4a83-aab6-b4a24646dec5
ms.openlocfilehash: f013c3df2ab5783a22fe2c34402dc53a328cafa2
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731013"
---
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a><span data-ttu-id="8d7ff-102">방법: MenuStrip이 포함된 MDI 창 목록 만들기(Windows Forms)</span><span class="sxs-lookup"><span data-stu-id="8d7ff-102">How to: Create an MDI Window List with MenuStrip (Windows Forms)</span></span>
<span data-ttu-id="8d7ff-103">MDI (다중 문서 인터페이스)를 사용 하 여 여러 문서를 동시에 열고 한 문서에서 다른 문서로 콘텐츠를 복사 하 여 붙여 넣을 수 있는 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-103">Use the multiple-document interface (MDI) to create applications that can open several documents at the same time and copy and paste content from one document to the other.</span></span>  
  
 <span data-ttu-id="8d7ff-104">이 절차에서는 부모 창 메뉴에서 모든 활성 자식 폼의 목록을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-104">This procedure shows you how to create a list of all the active child forms on the parent's Window menu.</span></span>  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a><span data-ttu-id="8d7ff-105">MenuStrip에서 MDI 창 목록을 만들려면</span><span class="sxs-lookup"><span data-stu-id="8d7ff-105">To create an MDI Window list on a MenuStrip</span></span>  
  
1. <span data-ttu-id="8d7ff-106">폼을 만들고 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-106">Create a form and set its <xref:System.Windows.Forms.Form.IsMdiContainer%2A> property to `true`.</span></span>  
  
2. <span data-ttu-id="8d7ff-107">폼에 <xref:System.Windows.Forms.MenuStrip>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-107">Add a <xref:System.Windows.Forms.MenuStrip> to the form.</span></span>  
  
3. <span data-ttu-id="8d7ff-108"><xref:System.Windows.Forms.MenuStrip>에 두 개의 최상위 메뉴 항목을 추가 하 고 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File` 및 `&Window`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-108">Add two top-level menu items to the <xref:System.Windows.Forms.MenuStrip> and set their <xref:System.Windows.Forms.Control.Text%2A> properties to `&File` and `&Window`.</span></span>  
  
4. <span data-ttu-id="8d7ff-109">`&File` 메뉴 항목에 하위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-109">Add a submenu item to the `&File` menu item and set its <xref:System.Windows.Forms.ToolStripItem.Text%2A> property to `&Open`.</span></span>  
  
5. <span data-ttu-id="8d7ff-110"><xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-110">Set the <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> property of the <xref:System.Windows.Forms.MenuStrip> to the `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
6. <span data-ttu-id="8d7ff-111">프로젝트에 폼을 추가 하 고 원하는 컨트롤을 다른 <xref:System.Windows.Forms.MenuStrip>추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-111">Add a form to the project and add the control you want to it, such as another <xref:System.Windows.Forms.MenuStrip>.</span></span>  
  
7. <span data-ttu-id="8d7ff-112">`&New`<xref:System.Windows.Forms.ToolStripMenuItem>의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-112">Create an event handler for the <xref:System.Windows.Forms.Control.Click> event of the `&New`<xref:System.Windows.Forms.ToolStripMenuItem>.</span></span>  
  
8. <span data-ttu-id="8d7ff-113">이벤트 처리기 내에서 다음과 비슷한 코드를 삽입 하 여 `Form2`의 새 인스턴스를 만들고 `Form1`의 MDI 자식으로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-113">Within the event handler, insert code similar to the following to create and display new instances of `Form2` as MDI children of `Form1`.</span></span>  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As _  
    System.Object, ByVal e As System.EventArgs) Handles _  
    openToolStripMenuItem.Click  
        Dim NewMDIChild As New Form2()  
        'Set the parent form of the child window.  
            NewMDIChild.MdiParent = Me  
        'Display the new form.  
            NewMDIChild.Show()  
    End Sub  
    ```  
  
    ```csharp  
    private void newToolStripMenuItem_Click(object sender, EventArgs e)  
    {  
        Form2 newMDIChild = new Form2();  
        // Set the parent form of the child window.  
            newMDIChild.MdiParent = this;  
        // Display the new form.  
            newMDIChild.Show();  
    }  
    ```  
  
9. <span data-ttu-id="8d7ff-114">`&New`<xref:System.Windows.Forms.ToolStripMenuItem>에 다음과 같은 코드를 입력 하 여 이벤트 처리기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-114">Place code like the following in the `&New`<xref:System.Windows.Forms.ToolStripMenuItem> to register the event handler.</span></span>  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="8d7ff-115">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="8d7ff-115">Compiling the Code</span></span>  
 <span data-ttu-id="8d7ff-116">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8d7ff-116">This example requires:</span></span>  
  
- <span data-ttu-id="8d7ff-117">`Form1` 및 `Form2`라는 두 개의 <xref:System.Windows.Forms.Form> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8d7ff-117">Two <xref:System.Windows.Forms.Form> controls named `Form1` and `Form2`.</span></span>  
  
- <span data-ttu-id="8d7ff-118">`menuStrip1`이라는 `Form1`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 및 `menuStrip2`라는 `Form2`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8d7ff-118">A <xref:System.Windows.Forms.MenuStrip> control on `Form1` named `menuStrip1`, and a <xref:System.Windows.Forms.MenuStrip> control on `Form2` named `menuStrip2`.</span></span>  
  
- <span data-ttu-id="8d7ff-119"><xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="8d7ff-119">References to the <xref:System?displayProperty=nameWithType> and <xref:System.Windows.Forms?displayProperty=nameWithType> assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d7ff-120">참조</span><span class="sxs-lookup"><span data-stu-id="8d7ff-120">See also</span></span>

- [<span data-ttu-id="8d7ff-121">방법: MDI 상위 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="8d7ff-121">How to: Create MDI Parent Forms</span></span>](../advanced/how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="8d7ff-122">방법: MDI 자식 폼 만들기</span><span class="sxs-lookup"><span data-stu-id="8d7ff-122">How to: Create MDI Child Forms</span></span>](../advanced/how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="8d7ff-123">MenuStrip 컨트롤</span><span class="sxs-lookup"><span data-stu-id="8d7ff-123">MenuStrip Control</span></span>](menustrip-control-windows-forms.md)
