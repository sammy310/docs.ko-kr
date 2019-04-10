---
title: '방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- examples [Windows Forms], LinkLabel control
- Windows Forms, linking to objects
- Web page link control
- linking [Windows Forms], to other forms
- Windows Forms, linking to Web pages
- links [Windows Forms], to other forms
- LinkLabel control [Windows Forms], linking to object or Web page
- LinkLabel control [Windows Forms], examples
ms.assetid: 6c91c975-3cb7-4504-82f0-fc6255f8fb85
ms.openlocfilehash: 49d53e068ea35b663affac79f689a8688763fac2
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59222733"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a>방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결
Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤을 사용 하면 폼의 웹 스타일 링크를 만들 수 있습니다. 링크를 클릭할 때 링크를 방문한 나타내기 위해 색을 변경할 수 있습니다. 색 변경에 대 한 자세한 내용은 참조 하세요. [방법: Windows Forms LinkLabel 컨트롤의 모양을 변경](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)합니다.  
  
## <a name="linking-to-another-form"></a>다른 폼에 링크  
  
#### <a name="to-link-to-another-form-with-a-linklabel-control"></a>LinkLabel 컨트롤을 사용 하 여 다른 형식으로 연결 하려면  
  
1.  설정 된 <xref:System.Windows.Forms.LinkLabel.Text%2A> 을 적절 한 캡션에 속성입니다.  
  
2.  설정 된 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 캡션의 어느 부분을 링크로 표시 됩니다. 표시 되는 링크 레이블의 모양과 관련 된 속성에 따라 달라 집니다. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 나타내는 값을 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 두 숫자, 시작 문자 위치와 문자 개수를 포함 하는 개체입니다. <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성 창에서 또는 코드에서 다음과 유사한 방식으로 속성을 설정할 수 있습니다.  
  
    ```vb  
    ' In this code example, the link area has been set to begin  
    ' at the first character and extend for eight characters.  
    ' You may need to modify this based on the text entered in Step 1.  
    LinkLabel1.LinkArea = New LinkArea(0, 8)  
    ```  
  
    ```csharp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1.LinkArea = new LinkArea(0,8);  
    ```  
  
    ```cpp  
    // In this code example, the link area has been set to begin  
    // at the first character and extend for eight characters.  
    // You may need to modify this based on the text entered in Step 1.  
    linkLabel1->LinkArea = LinkArea(0,8);  
    ```  
  
3.  <xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기를 호출 합니다 <xref:System.Windows.Forms.Form.Show%2A> 프로젝트에서 다른 폼을 열고 설정 하는 메서드를 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`합니다.  
  
    > [!NOTE]
    >  인스턴스를 <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> 클래스에 대 한 참조를 전달 합니다 <xref:System.Windows.Forms.LinkLabel> 캐스팅 하지 않아도 되므로 클릭 한 컨트롤을 `sender` 개체.  
  
    ```vb  
    Protected Sub LinkLabel1_LinkClicked(ByVal Sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       ' Show another form.  
       Dim f2 As New Form()  
       f2.Show  
       LinkLabel1.LinkVisited = True  
    End Sub  
    ```  
  
    ```csharp  
    protected void linkLabel1_LinkClicked(object sender, System. Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       // Show another form.  
       Form f2 = new Form();  
       f2.Show();  
       linkLabel1.LinkVisited = true;  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          // Show another form.  
          Form ^ f2 = new Form();  
          f2->Show();  
          linkLabel1->LinkVisited = true;  
       }  
    ```  
  
## <a name="linking-to-a-web-page"></a>웹 페이지에 연결  
 <xref:System.Windows.Forms.LinkLabel> 컨트롤 기본 브라우저를 사용 하 여 웹 페이지를 표시 하려면 사용할 수도 있습니다.  
  
#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a>LinkLabel 컨트롤을 사용 하 여 웹 페이지 링크와 Internet Explorer를 시작 하려면  
  
1.  설정 된 <xref:System.Windows.Forms.LinkLabel.Text%2A> 을 적절 한 캡션에 속성입니다.  
  
2.  설정 된 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 캡션의 어느 부분을 링크로 표시 됩니다.  
  
3.  에 <xref:System.Windows.Forms.LinkLabel.LinkClicked> 설정 하는 두 번째 프로시저를 호출 하는 이벤트 처리기는 예외 처리 블록 도중를 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true` 사용 하는 <xref:System.Diagnostics.Process.Start%2A> URL을 사용 하 여 기본 브라우저를 시작 하는 방법. 사용 하는 <xref:System.Diagnostics.Process.Start%2A> 에 대 한 참조를 추가 해야 하는 메서드를 <xref:System.Diagnostics?displayProperty=nameWithType> 네임 스페이스입니다.  
  
    > [!IMPORTANT]
    >  아래 코드는 부분 신뢰 환경에서 실행 됩니다 (같은 공유 드라이브에) 때 JIT 컴파일러가 실패는 `VisitLink` 메서드가 호출 됩니다. `System.Diagnostics.Process.Start` 문이 실패 하는 링크 요청 다시 발생 합니다. 예외를 catch 하 여 때는 `VisitLink` 메서드가 호출 되 면 아래 코드를 JIT 컴파일러에 실패 하면 오류를 정상적으로 처리를 보장 합니다.  
  
    ```vb  
    Private Sub LinkLabel1_LinkClicked(ByVal sender As System.Object, _  
       ByVal e As System.Windows.Forms.LinkLabelLinkClickedEventArgs) _  
       Handles LinkLabel1.LinkClicked  
       Try  
          VisitLink()  
       Catch ex As Exception  
          ' The error message  
          MessageBox.Show("Unable to open link that was clicked.")  
       End Try  
    End Sub  
  
    Sub VisitLink()  
       ' Change the color of the link text by setting LinkVisited   
       ' to True.  
       LinkLabel1.LinkVisited = True  
       ' Call the Process.Start method to open the default browser   
       ' with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com")  
    End Sub  
    ```  
  
    ```csharp  
    private void linkLabel1_LinkClicked(object sender, System.Windows.Forms.LinkLabelLinkClickedEventArgs e)  
    {  
       try  
       {  
          VisitLink();  
       }  
       catch (Exception ex )  
       {  
          MessageBox.Show("Unable to open link that was clicked.");  
       }  
    }  
  
    private void VisitLink()  
    {  
       // Change the color of the link text by setting LinkVisited   
       // to true.  
       linkLabel1.LinkVisited = true;  
       //Call the Process.Start method to open the default browser   
       //with a URL:  
       System.Diagnostics.Process.Start("http://www.microsoft.com");  
    }  
    ```  
  
    ```cpp  
    private:  
       void linkLabel1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkLabelLinkClickedEventArgs ^  e)  
       {  
          try  
          {  
             VisitLink();  
          }  
          catch (Exception ^ ex)  
          {  
             MessageBox::Show("Unable to open link that was clicked.");  
          }  
       }  
    private:  
       void VisitLink()  
       {  
          // Change the color of the link text by setting LinkVisited   
          // to true.  
          linkLabel1->LinkVisited = true;  
          // Call the Process.Start method to open the default browser   
          // with a URL:  
          System::Diagnostics::Process::Start("http://www.microsoft.com");  
       }  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [LinkLabel 컨트롤 개요](linklabel-control-overview-windows-forms.md)
- [방법: Windows Forms LinkLabel 컨트롤의 모양 변경](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [LinkLabel 컨트롤](linklabel-control-windows-forms.md)
