---
title: '방법: MDI 드롭다운 메뉴에서 ToolStripMenuItem 제거'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- menu items [Windows Forms], removing from MDI drop-down menus
- MenuStrip control [Windows Forms], merging
- MenuStrip control [Windows Forms], removing
- MDI [Windows Forms], merging menu items
ms.assetid: bdafe60d-82ee-45bc-97fe-eeefca6e54c1
ms.openlocfilehash: 3198195cf0991734826508aa65818505bf2038c8
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76735848"
---
# <a name="how-to-remove-a-toolstripmenuitem-from-an-mdi-drop-down-menu-windows-forms"></a>방법: MDI 드롭다운 메뉴에서 ToolStripMenuItem 제거(Windows Forms)
일부 애플리케이션에서는 MDI(다중 문서 인터페이스) 자식 창의 종류가 MDI 부모 창과 다를 수 있습니다. 예를 들어 MDI 부모는 스프레드시트이고 MDI 자식은 차트일 수 있습니다. 이 경우 다른 종류의 MDI 자식 창이 활성화될 때 MDI 부모 메뉴의 내용을 MDI 자식 메뉴의 내용으로 업데이트하려고 합니다.  
  
 다음 절차에서는 <xref:System.Windows.Forms.Form.IsMdiContainer%2A>, <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>, <xref:System.Windows.Forms.MergeAction>및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 사용 하 여 MDI 부모 메뉴의 드롭다운 부분에서 메뉴 항목을 제거 합니다. MDI 자식 창을 닫으면 제거 된 메뉴 항목이 MDI 부모 메뉴로 복원 됩니다.  
  
### <a name="to-remove-a-menustrip-from-an-mdi-drop-down-menu"></a>MDI 드롭다운 메뉴에서 MenuStrip을 제거 하려면  
  
1. 폼을 만들고 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.  
  
2. <xref:System.Windows.Forms.MenuStrip>에 `Form1`을 추가하고 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>의 <xref:System.Windows.Forms.MenuStrip> 속성을 `true`로 설정합니다.  
  
3. `Form1`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File`로 설정합니다.  
  
4. `&File` 메뉴 항목에 세 개의 하위 메뉴 항목을 추가 하 고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`, `&Import from`및 `E&xit`로 설정 합니다.  
  
5. `&Import from` 하위 메뉴 항목에 두 개의 하위 메뉴 항목을 추가 하 고 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Word` 및 `&Excel`로 설정 합니다.  
  
6. 프로젝트에 폼을 추가하고, 폼에 <xref:System.Windows.Forms.MenuStrip>을 추가한 다음 <xref:System.Windows.Forms.ToolStrip.AllowMerge%2A>`Form2`의 <xref:System.Windows.Forms.MenuStrip> 속성을 `true`로 설정합니다.  
  
7. `Form2`<xref:System.Windows.Forms.MenuStrip>에 최상위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&File`로 설정합니다.  
  
8. `Form2`의 `&File` 메뉴에 `&Import from` 하위 메뉴 항목을 추가 하 고 `&File` 메뉴에 `&Word` 하위 메뉴 항목을 추가 합니다.  
  
9. 다음 표와 같이 `Form2` 메뉴 항목의 <xref:System.Windows.Forms.MergeAction> 및 <xref:System.Windows.Forms.ToolStripItem.MergeIndex%2A> 속성을 설정 합니다.  
  
    |Form2 메뉴 항목|MergeAction 값|MergeIndex 값|  
    |---------------------|-----------------------|----------------------|  
    |파일|MatchOnly|-1|  
    |다음에서 가져오기|MatchOnly|-1|  
    |Word|제거|-1|  
  
10. `Form1`에서 `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대 한 이벤트 처리기를 만듭니다.  
  
11. 이벤트 처리기 내에서 다음 코드 예제와 비슷한 코드를 삽입 하 여 `Form2`의 새 인스턴스를 만들고 `Form1`의 MDI 자식으로 표시 합니다.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles openToolStripMenuItem.Click  
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
  
12. `&Open`<xref:System.Windows.Forms.ToolStripMenuItem>에 다음 코드 예제와 비슷한 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
    ```vb  
    Private Sub openToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles openToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.openToolStripMenuItem.Click += new _  
    System.EventHandler(this.openToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- <xref:System.Windows.Forms.Form> 및 `Form1`라는 두 개의 `Form2` 컨트롤  
  
- <xref:System.Windows.Forms.MenuStrip>이라는 `Form1`의 `menuStrip1` 컨트롤 및 <xref:System.Windows.Forms.MenuStrip>라는 `Form2`의 `menuStrip2` 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참고 항목

- [방법: MDI 상위 폼 만들기](../advanced/how-to-create-mdi-parent-forms.md)
- [방법: MDI 자식 폼 만들기](../advanced/how-to-create-mdi-child-forms.md)
- [MenuStrip 컨트롤 개요](menustrip-control-overview-windows-forms.md)
