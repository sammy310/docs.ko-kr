---
title: LinkLabel 컨트롤을 사용 하 여 개체 또는 웹 페이지에 연결
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
ms.openlocfilehash: 1669a9d6aba39b02d228c735701ca4e31c8f8291
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745213"
---
# <a name="how-to-link-to-an-object-or-web-page-with-the-windows-forms-linklabel-control"></a><span data-ttu-id="1ca4d-102">방법: Windows Forms LinkLabel 컨트롤을 사용하여 개체 또는 웹 페이지에 연결</span><span class="sxs-lookup"><span data-stu-id="1ca4d-102">How to: Link to an Object or Web Page with the Windows Forms LinkLabel Control</span></span>

<span data-ttu-id="1ca4d-103">Windows Forms <xref:System.Windows.Forms.LinkLabel> 컨트롤을 사용 하 여 폼에 웹 스타일 링크를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-103">The Windows Forms <xref:System.Windows.Forms.LinkLabel> control allows you to create Web-style links on your form.</span></span> <span data-ttu-id="1ca4d-104">링크를 클릭 하면 링크를 방문한 것을 나타내도록 색을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-104">When the link is clicked, you can change its color to indicate the link has been visited.</span></span> <span data-ttu-id="1ca4d-105">색 변경에 대 한 자세한 내용은 [방법: Windows Forms LinkLabel 컨트롤의 모양 변경](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-105">For more information on changing the color, see [How to: Change the Appearance of the Windows Forms LinkLabel Control](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md).</span></span>

## <a name="linking-to-another-form"></a><span data-ttu-id="1ca4d-106">다른 폼에 연결</span><span class="sxs-lookup"><span data-stu-id="1ca4d-106">Linking to Another Form</span></span>

#### <a name="to-link-to-another-form-with-a-linklabel-control"></a><span data-ttu-id="1ca4d-107">LinkLabel 컨트롤을 사용 하 여 다른 폼에 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="1ca4d-107">To link to another form with a LinkLabel control</span></span>

1. <span data-ttu-id="1ca4d-108"><xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절 한 캡션으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-108">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="1ca4d-109"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 설정 하 여 링크로 표시 될 캡션의 부분을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-109">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span> <span data-ttu-id="1ca4d-110">표시 되는 방법은 링크 레이블의 모양 관련 속성에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-110">How it is indicated depends on the appearance-related properties of the link label.</span></span> <span data-ttu-id="1ca4d-111"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 값은 두 개의 숫자, 시작 문자 위치 및 문자 수를 포함 하는 <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 개체로 표현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-111">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> value is represented by a <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> object containing two numbers, the starting character position and the number of characters.</span></span> <span data-ttu-id="1ca4d-112"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성은 다음과 같은 방법으로 속성 창 또는 코드에서 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-112">The <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property can be set in the Properties window or in code in a manner similar to the following:</span></span>

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

3. <span data-ttu-id="1ca4d-113"><xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기에서 <xref:System.Windows.Forms.Form.Show%2A> 메서드를 호출 하 여 프로젝트에서 다른 폼을 열고 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-113">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, invoke the <xref:System.Windows.Forms.Form.Show%2A> method to open another form in the project, and set the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1ca4d-114"><xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> 클래스의 인스턴스는 클릭 한 <xref:System.Windows.Forms.LinkLabel> 컨트롤에 대 한 참조를 전달 하므로 `sender` 개체를 캐스팅할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-114">An instance of the <xref:System.Windows.Forms.LinkLabelLinkClickedEventArgs> class carries a reference to the <xref:System.Windows.Forms.LinkLabel> control that was clicked, so there is no need to cast the `sender` object.</span></span>

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

## <a name="linking-to-a-web-page"></a><span data-ttu-id="1ca4d-115">웹 페이지에 연결</span><span class="sxs-lookup"><span data-stu-id="1ca4d-115">Linking to a Web Page</span></span>

<span data-ttu-id="1ca4d-116"><xref:System.Windows.Forms.LinkLabel> 컨트롤은 기본 브라우저를 사용 하 여 웹 페이지를 표시 하는 데에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-116">The <xref:System.Windows.Forms.LinkLabel> control can also be used to display a Web page with the default browser.</span></span>

#### <a name="to-start-internet-explorer-and-link-to-a-web-page-with-a-linklabel-control"></a><span data-ttu-id="1ca4d-117">Internet Explorer를 시작 하 고 LinkLabel 컨트롤을 사용 하 여 웹 페이지에 연결 하려면</span><span class="sxs-lookup"><span data-stu-id="1ca4d-117">To start Internet Explorer and link to a Web page with a LinkLabel control</span></span>

1. <span data-ttu-id="1ca4d-118"><xref:System.Windows.Forms.LinkLabel.Text%2A> 속성을 적절 한 캡션으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-118">Set the <xref:System.Windows.Forms.LinkLabel.Text%2A> property to an appropriate caption.</span></span>

2. <span data-ttu-id="1ca4d-119"><xref:System.Windows.Forms.LinkLabel.LinkArea%2A> 속성을 설정 하 여 링크로 표시 될 캡션의 부분을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-119">Set the <xref:System.Windows.Forms.LinkLabel.LinkArea%2A> property to determine which part of the caption will be indicated as a link.</span></span>

3. <span data-ttu-id="1ca4d-120"><xref:System.Windows.Forms.LinkLabel.LinkClicked> 이벤트 처리기에서 예외 처리 블록의 가운데에 <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> 속성을 `true`로 설정 하 고 <xref:System.Diagnostics.Process.Start%2A> 메서드를 사용 하 여 URL로 기본 브라우저를 시작 하는 두 번째 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-120">In the <xref:System.Windows.Forms.LinkLabel.LinkClicked> event handler, in the midst of an exception-handling block, call a second procedure that sets the <xref:System.Windows.Forms.LinkLabel.LinkVisited%2A> property to `true` and uses the <xref:System.Diagnostics.Process.Start%2A> method to start the default browser with a URL.</span></span> <span data-ttu-id="1ca4d-121"><xref:System.Diagnostics.Process.Start%2A> 메서드를 사용 하려면 <xref:System.Diagnostics?displayProperty=nameWithType> 네임 스페이스에 대 한 참조를 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-121">To use the <xref:System.Diagnostics.Process.Start%2A> method you need to add a reference to the <xref:System.Diagnostics?displayProperty=nameWithType> namespace.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1ca4d-122">아래 코드를 공유 드라이브 등의 부분 신뢰 환경에서 실행 하는 경우 `VisitLink` 메서드가 호출 될 때 JIT 컴파일러가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-122">If the code below is run in a partial-trust environment (such as on a shared drive), the JIT compiler fails when the `VisitLink` method is called.</span></span> <span data-ttu-id="1ca4d-123">`System.Diagnostics.Process.Start` 문으로 인해 링크 요청이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-123">The `System.Diagnostics.Process.Start` statement causes a link demand that fails.</span></span> <span data-ttu-id="1ca4d-124">다음 코드는 `VisitLink` 메서드가 호출 될 때 예외를 catch 하 여 JIT 컴파일러에 오류가 발생 하는 경우 오류를 정상적으로 처리 하는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ca4d-124">By catching the exception when the `VisitLink` method is called, the code below ensures that if the JIT compiler fails, the error is handled gracefully.</span></span>

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

## <a name="see-also"></a><span data-ttu-id="1ca4d-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1ca4d-125">See also</span></span>

- <xref:System.Diagnostics.Process.Start%2A?displayProperty=nameWithType>
- [<span data-ttu-id="1ca4d-126">LinkLabel 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="1ca4d-126">LinkLabel Control Overview</span></span>](linklabel-control-overview-windows-forms.md)
- [<span data-ttu-id="1ca4d-127">방법: Windows Forms LinkLabel 컨트롤의 모양 변경</span><span class="sxs-lookup"><span data-stu-id="1ca4d-127">How to: Change the Appearance of the Windows Forms LinkLabel Control</span></span>](how-to-change-the-appearance-of-the-windows-forms-linklabel-control.md)
- [<span data-ttu-id="1ca4d-128">LinkLabel 컨트롤</span><span class="sxs-lookup"><span data-stu-id="1ca4d-128">LinkLabel Control</span></span>](linklabel-control-windows-forms.md)
