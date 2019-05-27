---
title: '방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- text boxes [Windows Forms], displaying Web links
- examples [Windows Forms], text boxes
- RichTextBox control [Windows Forms], linking to Web pages
ms.assetid: 95089a37-a202-4f7a-94ee-6ee312908851
ms.openlocfilehash: 05d9ad4766584b59cca7c31f49b737d4696a9921
ms.sourcegitcommit: 7e129d879ddb42a8b4334eee35727afe3d437952
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66053534"
---
# <a name="how-to-display-web-style-links-with-the-windows-forms-richtextbox-control"></a>방법: Windows Forms RichTextBox 컨트롤을 사용하여 웹 스타일 링크 표시
Windows Forms <xref:System.Windows.Forms.RichTextBox> 제어와 색이 지정 된 밑줄 웹 링크를 표시할 수 있습니다. 브라우저 창에 링크를 클릭할 때 링크 텍스트에 지정 된 웹 사이트를 표시 하는 코드를 작성할 수 있습니다.  
  
### <a name="to-link-to-a-web-page-with-the-richtextbox-control"></a>RichTextBox 컨트롤을 사용 하 여 웹 페이지에 연결 하려면  
  
1. 설정 된 <xref:System.Windows.Forms.RichTextBox.Text%2A> 속성을 유효한 URL이 포함 된 문자열 (예를 들어, "http://www.microsoft.com/").  
  
2. 있는지 확인 합니다 <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A> 속성이 `true` (기본값).  
  
3. 새 전역 인스턴스를 만들고는 <xref:System.Diagnostics.Process> 개체입니다.  
  
4. 에 대 한 이벤트 처리기를 작성 합니다 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 브라우저에 원하는 텍스트를 전송 하는 이벤트입니다.  
  
     아래 예제에서는 <xref:System.Windows.Forms.RichTextBox.LinkClicked> 이벤트에 지정 된 URL Internet Explorer의 인스턴스를 열고는 <xref:System.Windows.Forms.RichTextBox.Text%2A> 의 속성은 <xref:System.Windows.Forms.RichTextBox> 컨트롤. 이 예에서는 가정 된 폼을 <xref:System.Windows.Forms.RichTextBox> 제어 합니다.  
  
    > [!IMPORTANT]
    >  호출에는 <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType> 메서드를 접하게 되는 <xref:System.Security.SecurityException> 권한 부족으로 인해 부분 신뢰 컨텍스트에서 코드를 실행 하는 경우 예외. 자세한 내용은 [코드 액세스 보안 기본 사항](../../misc/code-access-security-basics.md)을 참조하세요.  
  
    ```vb  
    Public p As New System.Diagnostics.Process  
    Private Sub RichTextBox1_LinkClicked _  
       (ByVal sender As Object, ByVal e As _  
       System.Windows.Forms.LinkClickedEventArgs) _  
       Handles RichTextBox1.LinkClicked  
          ' Call Process.Start method to open a browser  
          ' with link text as URL.  
          p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText)  
    End Sub  
    ```  
  
    ```csharp  
    public System.Diagnostics.Process p = new System.Diagnostics.Process();  
  
    private void richTextBox1_LinkClicked(object sender,   
    System.Windows.Forms.LinkClickedEventArgs e)  
    {  
       // Call Process.Start method to open a browser  
       // with link text as URL.  
       p = System.Diagnostics.Process.Start("IExplore.exe", e.LinkText);  
    }  
    ```  
  
    ```cpp  
    public:  
       System::Diagnostics::Process ^ p;  
  
    private:  
       void richTextBox1_LinkClicked(System::Object ^  sender,  
          System::Windows::Forms::LinkClickedEventArgs ^  e)  
       {  
          // Call Process.Start method to open a browser  
          // with link text as URL.  
          p = System::Diagnostics::Process::Start("IExplore.exe",  
             e->LinkText);  
       }  
    ```  
  
     (Visual C++) 프로세스를 초기화 해야 `p`, 폼의 생성자에서 다음 문을 포함 하 여 수행할 수 있습니다.  
  
    ```cpp  
    p = gcnew System::Diagnostics::Process();  
    ```  
  
     (Visual C#, Visual C++) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.  
  
    ```csharp  
    this.richTextBox1.LinkClicked += new   
       System.Windows.Forms.LinkClickedEventHandler  
       (this.richTextBox1_LinkClicked);  
    ```  
  
    ```cpp  
    this->richTextBox1->LinkClicked += gcnew  
       System::Windows::Forms::LinkClickedEventHandler  
       (this, &Form1::richTextBox1_LinkClicked);  
    ```  
  
     즉시 작업을 마친 후 만든 프로세스를 중지 하는 것이 반드시 합니다. 위에 나오는 코드를 참조 하는 프로세스를 중지 하는 코드 다음과 같습니다.  
  
    ```vb  
    Public Sub StopWebProcess()  
       p.Kill()  
    End Sub  
    ```  
  
    ```csharp  
    public void StopWebProcess()  
    {  
       p.Kill();  
    }  
    ```  
  
    ```cpp  
    public: void StopWebProcess()  
    {  
       p->Kill();  
    }  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.RichTextBox.DetectUrls%2A>
- <xref:System.Windows.Forms.RichTextBox.LinkClicked>
- <xref:System.Windows.Forms.RichTextBox>
- [RichTextBox 컨트롤](richtextbox-control-windows-forms.md)
- [Windows Forms에 사용할 수 있는 컨트롤](controls-to-use-on-windows-forms.md)
