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
# <a name="how-to-create-an-mdi-window-list-with-menustrip-windows-forms"></a>방법: MenuStrip이 포함된 MDI 창 목록 만들기(Windows Forms)
MDI (다중 문서 인터페이스)를 사용 하 여 여러 문서를 동시에 열고 한 문서에서 다른 문서로 콘텐츠를 복사 하 여 붙여 넣을 수 있는 응용 프로그램을 만듭니다.  
  
 이 절차에서는 부모 창 메뉴에서 모든 활성 자식 폼의 목록을 만드는 방법을 보여 줍니다.  
  
### <a name="to-create-an-mdi-window-list-on-a-menustrip"></a>MenuStrip에서 MDI 창 목록을 만들려면  
  
1. 폼을 만들고 해당 <xref:System.Windows.Forms.Form.IsMdiContainer%2A> 속성을 `true`로 설정합니다.  
  
2. 폼에 <xref:System.Windows.Forms.MenuStrip>를 추가합니다.  
  
3. <xref:System.Windows.Forms.MenuStrip>에 두 개의 최상위 메뉴 항목을 추가 하 고 <xref:System.Windows.Forms.Control.Text%2A> 속성을 `&File` 및 `&Window`로 설정 합니다.  
  
4. `&File` 메뉴 항목에 하위 메뉴 항목을 추가하고 해당 <xref:System.Windows.Forms.ToolStripItem.Text%2A> 속성을 `&Open`로 설정합니다.  
  
5. <xref:System.Windows.Forms.MenuStrip>의 <xref:System.Windows.Forms.MenuStrip.MdiWindowListItem%2A> 속성을 `&Window`<xref:System.Windows.Forms.ToolStripMenuItem>설정 합니다.  
  
6. 프로젝트에 폼을 추가 하 고 원하는 컨트롤을 다른 <xref:System.Windows.Forms.MenuStrip>추가 합니다.  
  
7. `&New`<xref:System.Windows.Forms.ToolStripMenuItem>의 <xref:System.Windows.Forms.Control.Click> 이벤트에 대한 이벤트 처리기를 만듭니다.  
  
8. 이벤트 처리기 내에서 다음과 비슷한 코드를 삽입 하 여 `Form2`의 새 인스턴스를 만들고 `Form1`의 MDI 자식으로 표시 합니다.  
  
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
  
9. `&New`<xref:System.Windows.Forms.ToolStripMenuItem>에 다음과 같은 코드를 입력 하 여 이벤트 처리기를 등록 합니다.  
  
    ```vb  
    Private Sub newToolStripMenuItem_Click(sender As Object, e As _  
    EventArgs) Handles newToolStripMenuItem.Click  
    ```  
  
    ```csharp  
    this.newToolStripMenuItem.Click += new System.EventHandler(this.newToolStripMenuItem_Click);  
    ```  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 이 예제에는 다음 사항이 필요합니다.  
  
- `Form1` 및 `Form2`라는 두 개의 <xref:System.Windows.Forms.Form> 컨트롤  
  
- `menuStrip1`이라는 `Form1`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤 및 `menuStrip2`라는 `Form2`의 <xref:System.Windows.Forms.MenuStrip> 컨트롤  
  
- <xref:System?displayProperty=nameWithType> 및 <xref:System.Windows.Forms?displayProperty=nameWithType> 어셈블리에 대한 참조  
  
## <a name="see-also"></a>참조

- [방법: MDI 상위 폼 만들기](../advanced/how-to-create-mdi-parent-forms.md)
- [방법: MDI 자식 폼 만들기](../advanced/how-to-create-mdi-child-forms.md)
- [MenuStrip 컨트롤](menustrip-control-windows-forms.md)
