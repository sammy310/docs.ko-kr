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
ms.openlocfilehash: 57491faa10c182630d41565ba236d65e393929b3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182541"
---
# <a name="how-to-determine-the-active-mdi-child"></a>방법: 활성 MDI 자식 확인
경우에 따라 현재 활성 자식 양식에 중점을 둔 컨트롤에서 작동하는 명령을 제공하려고 합니다. 예를 들어 자식 양식의 텍스트 상자에서 선택한 텍스트를 클립보드에 복사한다고 가정합니다. 표준 편집 메뉴의 복사 메뉴 항목 <xref:System.Windows.Forms.Control.Click> 의 이벤트를 사용하여 선택한 텍스트를 클립보드에 복사하는 프로시저를 만듭니다.  
  
 MDI 응용 프로그램에는 동일한 자식 양식의 많은 인스턴스가 있을 수 있으므로 프로시저는 사용할 양식을 알아야 합니다. 올바른 양식을 지정하려면 포커스가 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 있거나 가장 최근에 활성 상태인 자식 양식을 반환하는 속성을 사용합니다.  
  
 양식에 여러 컨트롤이 있는 경우 활성 컨트롤을 지정해야 합니다. 속성과 <xref:System.Windows.Forms.Form.ActiveMdiChild%2A> 마찬가지로 <xref:System.Windows.Forms.ContainerControl.ActiveControl%2A> 속성은 활성 자식 양식에 포커스를 두고 컨트롤을 반환합니다. 아래 절차에서는 자식 양식 메뉴, MDI 양식의 메뉴 또는 도구 모음 단추에서 호출할 수 있는 복사 절차를 보여 줍니다.  
  
### <a name="to-determine-the-active-mdi-child-to-copy-its-text-to-the-clipboard"></a>활성 MDI 자식을 확인하려면(해당 텍스트를 클립보드에 복사)  
  
1. 메서드 내에서 활성 자식 양식의 활성 컨트롤의 텍스트를 클립보드에 복사합니다.  
  
    > [!NOTE]
    > 이 예제에서는 컨트롤을 포함하는 하나`Form1`이상의 MDI 자식 창이 있는 <xref:System.Windows.Forms.RichTextBox> MDI 상위 양식()이 있다고 가정합니다. 자세한 내용은 [MDI 상위 양식 만들기](how-to-create-mdi-parent-forms.md)를 참조하십시오.  
  
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
  
## <a name="see-also"></a>참고 항목

- [MDI(다중 문서 인터페이스) 애플리케이션](multiple-document-interface-mdi-applications.md)
- [방법: MDI 상위 폼 만들기](how-to-create-mdi-parent-forms.md)
- [방법: MDI 자식 폼 만들기](how-to-create-mdi-child-forms.md)
- [방법: 활성 MDI 자식으로 데이터 전송](how-to-send-data-to-the-active-mdi-child.md)
- [방법: MDI 자식 양식 정렬](how-to-arrange-mdi-child-forms.md)
