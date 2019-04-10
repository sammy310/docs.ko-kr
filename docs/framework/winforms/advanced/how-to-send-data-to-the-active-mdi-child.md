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
# <a name="how-to-send-data-to-the-active-mdi-child"></a><span data-ttu-id="01c13-102">방법: 활성 MDI 자식으로 데이터 보내기</span><span class="sxs-lookup"><span data-stu-id="01c13-102">How to: Send Data to the Active MDI Child</span></span>
<span data-ttu-id="01c13-103">컨텍스트 내에서 종종 [다중 문서 MDI (인터페이스) 응용 프로그램](multiple-document-interface-mdi-applications.md), 사용자 데이터를 클립보드에서 MDI 응용 프로그램에 붙여 넣는 같은 활성 자식 창에 데이터를 전송 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01c13-103">Often, within the context of [Multiple-Document Interface (MDI) Applications](multiple-document-interface-mdi-applications.md), you will need to send data to the active child window, such as when the user pastes data from the Clipboard into an MDI application.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="01c13-104">자식 창에 포커스가 확인 하 고 해당 콘텐츠를 클립보드에 전송 하는 방법에 대 한 내용은 [활성 MDI 자식 확인](how-to-determine-the-active-mdi-child.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01c13-104">For information about verifying which child window has focus and sending its contents to the Clipboard, see [Determining the Active MDI Child](how-to-determine-the-active-mdi-child.md).</span></span>  
  
### <a name="to-send-data-to-the-active-mdi-child-window-from-the-clipboard"></a><span data-ttu-id="01c13-105">클립보드에서 활성 MDI 자식 창에 데이터를 보내도록</span><span class="sxs-lookup"><span data-stu-id="01c13-105">To send data to the active MDI child window from the Clipboard</span></span>  
  
1.  <span data-ttu-id="01c13-106">메서드를 활성 자식 폼의 활성 컨트롤을 클립보드에 텍스트를 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="01c13-106">Within a method, copy the text on the Clipboard to the active control of the active child form.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="01c13-107">이 예제에서는 가정 MDI 부모 폼 (`Form1`) 포함 된 하나 이상의 MDI 자식 창에 있는 <xref:System.Windows.Forms.RichTextBox> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="01c13-107">This example assumes there is an MDI parent form (`Form1`) that has one or more MDI child windows containing a <xref:System.Windows.Forms.RichTextBox> control.</span></span> <span data-ttu-id="01c13-108">자세한 내용은 [MDI 부모 폼 만들기](how-to-create-mdi-parent-forms.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="01c13-108">For more information, see [Creating MDI Parent Forms](how-to-create-mdi-parent-forms.md).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="01c13-109">참고자료</span><span class="sxs-lookup"><span data-stu-id="01c13-109">See also</span></span>

- [<span data-ttu-id="01c13-110">MDI 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="01c13-110">Multiple-Document Interface (MDI) Applications</span></span>](multiple-document-interface-mdi-applications.md)
- [<span data-ttu-id="01c13-111">방법: MDI 부모 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="01c13-111">How to: Create MDI Parent Forms</span></span>](how-to-create-mdi-parent-forms.md)
- [<span data-ttu-id="01c13-112">방법: MDI 자식 양식 만들기</span><span class="sxs-lookup"><span data-stu-id="01c13-112">How to: Create MDI Child Forms</span></span>](how-to-create-mdi-child-forms.md)
- [<span data-ttu-id="01c13-113">방법: 활성 MDI 자식 확인</span><span class="sxs-lookup"><span data-stu-id="01c13-113">How to: Determine the Active MDI Child</span></span>](how-to-determine-the-active-mdi-child.md)
- [<span data-ttu-id="01c13-114">방법: MDI 자식 양식 정렬</span><span class="sxs-lookup"><span data-stu-id="01c13-114">How to: Arrange MDI Child Forms</span></span>](how-to-arrange-mdi-child-forms.md)
