---
title: LinkLabel 컨트롤의 모양 변경
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- LinkLabel properties
- LinkLabel control [Windows Forms], changing appearance of links
- links [Windows Forms], changing appearance
- examples [Windows Forms], LinkLabel control
- LinkLabel control [Windows Forms], examples
ms.assetid: fdc5854f-5162-4457-8cbe-1042feb2d132
ms.openlocfilehash: 0b38722fb1647ea215c3bb8978dd3f54b300a0e0
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746623"
---
# <a name="how-to-change-the-appearance-of-the-windows-forms-linklabel-control"></a>방법: Windows Forms LinkLabel 컨트롤의 모양 변경
<xref:System.Windows.Forms.LinkLabel> 컨트롤에 표시 되는 텍스트를 다양 한 용도에 맞게 변경할 수 있습니다. 예를 들어, 텍스트를 밑줄을 사용 하 여 특정 색에 표시 되도록 설정 하 여 텍스트를 클릭할 수 있음을 사용자에 게 표시 하는 것이 일반적입니다. 사용자가 텍스트를 클릭 하면 색이 다른 색으로 변경 됩니다. 이 동작을 제어 하기 위해 <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A>, <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>, <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>, <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>및 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성의 5 가지 속성을 설정할 수 있습니다.  
  
### <a name="to-change-the-appearance-of-a-linklabel-control"></a>LinkLabel 컨트롤의 모양을 변경 하려면  
  
1. <xref:System.Windows.Forms.LinkLabel.LinkColor%2A> 및 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성을 원하는 색으로 설정 합니다.  
  
     이러한 작업은 프로그래밍 방식으로 또는 디자인 타임에 **속성** 창에서 수행할 수 있습니다.  
  
    ```vb  
    ' You can set the color using decimal values for red, green, and blue  
    LinkLabel1.LinkColor = Color.FromArgb(0, 0, 255)  
    ' Or you can set the color using defined constants  
    LinkLabel1.VisitedLinkColor = Color.Purple  
    ```  
  
    ```csharp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1.LinkColor = Color.FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1.VisitedLinkColor = Color.Purple;  
    ```  
  
    ```cpp  
    // You can set the color using decimal values for red, green, and blue  
    linkLabel1->LinkColor = Color::FromArgb(0, 0, 255);  
    // Or you can set the color using defined constants  
    linkLabel1->VisitedLinkColor = Color::Purple;  
    ```  
  
2. <xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절 한 캡션으로 설정 합니다.  
  
     이러한 작업은 프로그래밍 방식으로 또는 디자인 타임에 **속성** 창에서 수행할 수 있습니다.  
  
    ```vb  
    LinkLabel1.Text = "Click here to see more."  
    ```  
  
    ```csharp  
    linkLabel1.Text = "Click here to see more.";  
    ```  
  
    ```cpp  
    linkLabel1->Text = "Click here to see more.";  
    ```  
  
3. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 설정 하 여 링크로 표시 될 캡션의 부분을 결정 합니다.  
  
     <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 값은 두 개의 숫자, 시작 문자 위치 및 문자 수를 포함 하는 <xref:System.Windows.Forms.LinkArea> 표시 됩니다. 이러한 작업은 프로그래밍 방식으로 또는 디자인 타임에 **속성** 창에서 수행할 수 있습니다.  
  
    ```vb  
    LinkLabel1.LinkArea = new LinkArea(6,4)  
    ```  
  
    ```csharp  
    linkLabel1.LinkArea = new LinkArea(6,4);  
    ```  
  
    ```cpp  
    linkLabel1->LinkArea = LinkArea(6,4);  
    ```  
  
4. <xref:System.Windows.Forms.LinkLabel.LinkBehavior%2A> 속성을 <xref:System.Windows.Forms.LinkBehavior.AlwaysUnderline>, <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>또는 <xref:System.Windows.Forms.LinkBehavior.NeverUnderline>설정 합니다.  
  
     <xref:System.Windows.Forms.LinkBehavior.HoverUnderline>로 설정 된 경우에는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>에 의해 결정 되는 캡션의 일부가 포인터를 가져갈 때만 밑줄이 표시 됩니다.  
  
5. <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기에서 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`로 설정 합니다.  
  
     링크를 방문한 경우 일반적으로 색을 기준으로 모양을 변경 하는 것이 일반적입니다. 텍스트는 <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A> 속성에 지정 된 색으로 변경 됩니다.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked (ByVal sender As Object, _  
       ByVal e As EventArgs) Handles LinkLabel1.LinkClicked  
       ' Change the color of the link text  
       ' by setting LinkVisited to True.  
       LinkLabel1.LinkVisited = True  
       ' Then do whatever other action is appropriate  
    End Sub  
    ```  
  
    ```csharp  
    protected void LinkLabel1_LinkClicked(object sender, System.EventArgs e)  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to True.  
       linkLabel1.LinkVisited = true;  
       // Then do whatever other action is appropriate  
    }  
    ```  
  
    ```cpp  
    private:  
       System::Void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to True.  
          linkLabel1->LinkVisited = true;  
          // Then do whatever other action is appropriate  
       }  
    ```  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Windows.Forms.LinkLabel.LinkArea%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.VisitedLinkColor%2A>
- <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A>
- [LinkLabel 컨트롤 개요](linklabel-control-overview-windows-forms.md)
- [방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결](link-to-an-object-or-web-page-with-wf-linklabel-control.md)
- [LinkLabel 컨트롤](linklabel-control-windows-forms.md)
