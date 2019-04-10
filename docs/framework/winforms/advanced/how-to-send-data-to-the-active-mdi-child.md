---
title: '방법: 활성 MDI 자식으로 데이터 보내기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- child forms
- MDI [Windows Forms], sending data to forms
- Clipboard [Windows Forms], pasting
- Clipboard [Windows Forms], getting data from
ms.assetid: 1047d2fe-1235-46db-aad9-563aea1d743b
ms.openlocfilehash: 0ffe87d55f7325f77bd33bdbf5d5fbab9f321f93
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59203329"
---
# <a name="how-to-send-data-to-the-active-mdi-child"></a>방법: 활성 MDI 자식으로 데이터 보내기
컨텍스트 내에서 종종 [다중 문서 MDI (인터페이스) 응용 프로그램](multiple-document-interface-mdi-applications.md), 사용자 데이터를 클립보드에서 MDI 응용 프로그램에 붙여 넣는 같은 활성 자식 창에 데이터를 전송 해야 합니다.  
  
> [!NOTE]
>  자식 창에 포커스가 확인 하 고 해당 콘텐츠를 클립보드에 전송 하는 방법에 대 한 내용은 [활성 MDI 자식 확인](how-to-determine-the-active-mdi-child.md)합니다.  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a>클립보드에서 활성 MDI 자식 창에 데이터를 보내도록  
  
1.  메서드를 활성 자식 폼의 활성 컨트롤을 클립보드에 텍스트를 복사 합니다.  
  
    > [!NOTE]
    >  이 예제에서는 가정 MDI 부모 폼 (`Form1`) 포함 된 하나 이상의 MDI 자식 창에 있는 <xref:System.Windows.Forms.RichTextBox> 제어 합니다. 자세한 내용은 [MDI 부모 폼 만들기](how-to-create-mdi-parent-forms.md)합니다.  
  
    ```vb  
    Public Sub mniPaste_Click(ByVal sender As Object, _  
       ByVal e As System.EventArgs) Handles mniPaste.Click  
  
       ' Determine the active child form.  
       Dim activeChild As Form = Me.ParentForm.ActiveMDIChild  
  
       ' If there is an active child form, find the active control, which  
       ' in this example should be a RichTextBox.  
       If (Not activeChild Is Nothing) Then  
          Try  
             Dim theBox As RichTextBox = Ctype(activeChild.ActiveControl, RichTextBox)  
             If (Not theBox Is Nothing) Then  
                ' Create a new instance of the DataObject interface.  
                Dim data As IDataObject = Clipboard.GetDataObject()  
                ' If the data is text, then set the text of the   
                ' RichTextBox to the text in the clipboard.  
                If (data.GetDataPresent(DataFormats.Text)) Then  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString()  
                End If  
             End If  
          Catch  
             MessageBox.Show("You need to select a RichTextBox.")  
          End Try  
       End If  
    End Sub  
    ```  
  
    ```csharp  
    protected void mniPaste_Click (object sender, System.EventArgs e)  
    {  
      // Determine the active child form.  
       Form activeChild = this.ParentForm.ActiveMdiChild;  
  
       // If there is an active child form, find the active control, which  
       // in this example should be a RichTextBox.  
       if (activeChild != null)  
       {  
          try   
          {  
             RichTextBox theBox = (RichTextBox)activeChild.ActiveControl;  
             if (theBox != null)  
             {  
                // Create a new instance of the DataObject interface.  
                IDataObject data = Clipboard.GetDataObject();  
                // If the data is text, then set the text of the   
                // RichTextBox to the text in the clipboard.  
                if (data.GetDataPresent(DataFormats.Text))  
                {  
                   theBox.SelectedText = data.GetData(DataFormats.Text).ToString();                 
                }  
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

- [MDI 애플리케이션](multiple-document-interface-mdi-applications.md)
- [방법: MDI 부모 양식 만들기](how-to-create-mdi-parent-forms.md)
- [방법: MDI 자식 양식 만들기](how-to-create-mdi-child-forms.md)
- [방법: 활성 MDI 자식 확인](how-to-determine-the-active-mdi-child.md)
- [방법: MDI 자식 양식 정렬](how-to-arrange-mdi-child-forms.md)
