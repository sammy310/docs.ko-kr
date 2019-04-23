---
title: '방법: 활성 MDI 자식 확인'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Clipboard [Windows Forms], copying data to
- MDI [Windows Forms], child windows
- child forms
- MDI [Windows Forms], activating forms
- MDI [Windows Forms], locating focus
ms.assetid: 33880ec3-0207-4c2b-a616-ff140443cc0f
ms.openlocfilehash: 9b70824670b8f47a2346135cb31ad39bd55694d1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59300608"
---
# <a name="how-to-determine-the-active-mdi-child"></a>방법: 활성 MDI 자식 확인
경우에 따라 현재 활성 자식 폼에 포커스가 있는 컨트롤에서 작동 하는 명령을 제공 합니다. 예를 들어 자식 폼의 텍스트 상자에서 선택한 텍스트를 클립보드로 복사 한다고 가정 합니다. 선택한 텍스트를 사용 하 여 클립보드에 복사 하는 프로시저를 만듭니다는 <xref:System.Windows.Forms.Control.Click> 표준 편집 메뉴에서 복사 메뉴 항목의 이벤트입니다.  
  
 MDI 응용 프로그램에서 동일한 자식 폼의 여러 인스턴스를 가질 수 있으므로 프로시저 사용할 폼을 알아야 합니다. 올바른 형식을 지정 하려면 사용 된 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 포커스가 있는 또는 가장 최근에 활성화 된 자식 폼을 반환 하는 속성입니다.  
  
 양식의 여러 컨트롤에 있는 경우도 활성 컨트롤을 지정 해야 합니다. 같은 합니다 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 속성인은 <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 속성 활성 자식 폼에 포커스를 사용 하 여 컨트롤을 반환 합니다. 아래 절차를 자식 폼 메뉴의 메뉴를 MDI 폼 또는 도구 모음 단추에서 호출할 수 있는 복사 절차를 보여 줍니다.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>활성 MDI 자식 (해당 텍스트를 클립보드로 복사)를 확인 하려면  
  
1. 인 메서드 내부의 활성 자식 폼의 활성 컨트롤의 텍스트를 클립보드에 복사 합니다.  
  
    > [!NOTE]
    >  이 예제에서는 가정 MDI 부모 폼 (`Form1`) 포함 된 하나 이상의 MDI 자식 창에 있는 <xref:System.Windows.Forms.RichTextBox> 제어 합니다. 자세한 내용은 [MDI 부모 폼 만들기](how-to-create-mdi-parent-forms.md)합니다.  
  
    ```vb  
    Public Sub mniCopy_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniCopy.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Dim theBox As RichTextBox = _  
            TryCast(activeChild.ActiveControl, RichTextBox)  
  
          If (Not theBox Is Nothing) Then  
             'Put selected text on Clipboard.  
             Clipboard.SetDataObject(theBox.SelectedText)  
          Else  
             MessageBox.Show("You need to select a RichTextBox.")  
          End If  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniCopy_Click (object sender, System.EventArgs e)  
    {  
       // Determine the active child form.  
       Form activeChild = this.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {    
          try  
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Put the selected text on the Clipboard.  
                Clipboard.SetDataObject(theBox.SelectedText);  
  
             }  
          }  
          catch  
          {  
             MessageBox.Show("You need to select a RichTextBox.");  
          }  
       }  
    }  
    ```  
  
## <a name="see-also"></a>참고자료

- [MDI(다중 문서 인터페이스) 응용 프로그램](multiple-document-interface-mdi-applications.md)
- [방법: MDI 부모 폼 만들기](how-to-create-mdi-parent-forms.md)
- [방법: MDI 자식 폼 만들기](how-to-create-mdi-child-forms.md)
- [방법: 활성 MDI 자식으로 데이터 전송](how-to-send-data-to-the-active-mdi-child.md)
- [방법: MDI 자식 폼 정렬](how-to-arrange-mdi-child-forms.md)
