---
title: Windows Forms apps에서 인쇄 미리 보기 표시
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print preview [Windows Forms], displaying
- printing [Windows Forms], print preview
- examples [Windows Forms], print preview
ms.assetid: e394134c-0886-4517-bd8d-edc4a3749eb5
ms.openlocfilehash: ac02339ad86e491cd047dcd4b0c8841374b3bb2e
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76745574"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="50a13-102">방법: Windows Forms 애플리케이션에서 인쇄 미리 보기 표시</span><span class="sxs-lookup"><span data-stu-id="50a13-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="50a13-103"><xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤을 사용 하면 문서를 인쇄 하기 전에 사용자가 문서를 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="50a13-104">이렇게 하려면 <xref:System.Drawing.Printing.PrintDocument> 클래스의 인스턴스를 지정 해야 합니다. 인쇄할 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="50a13-105"><xref:System.Drawing.Printing.PrintDocument> 구성 요소에서 인쇄 미리 보기를 사용 하는 방법에 대 한 자세한 내용은 [방법: 인쇄 미리 보기를 사용 하 여 Windows Forms에 인쇄](../advanced/how-to-print-in-windows-forms-using-print-preview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="50a13-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="50a13-106">런타임에 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤을 사용 하려면 로컬 또는 네트워크를 통해 컴퓨터에 설치 된 프린터가 있어야 합니다 .이는 <xref:System.Windows.Forms.PrintPreviewDialog> 구성 요소가 인쇄 될 때 표시 되는 방법을 결정 하는 방법 중 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="50a13-107"><xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 <xref:System.Drawing.Printing.PrinterSettings> 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="50a13-108">또한 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤은 <xref:System.Windows.Forms.PrintPreviewDialog> 구성 요소가 수행 하는 것 처럼 <xref:System.Drawing.Printing.PageSettings> 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="50a13-109"><xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> 속성에 지정 된 인쇄 문서는 <xref:System.Drawing.Printing.PrinterSettings> 및 <xref:System.Drawing.Printing.PageSettings> 클래스의 인스턴스를 참조 하며, 이러한 클래스는 미리 보기 창에서 문서를 렌더링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="50a13-110">PrintPreviewDialog 컨트롤을 사용 하 여 페이지를 보려면</span><span class="sxs-lookup"><span data-stu-id="50a13-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="50a13-111"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 대화 상자를 표시하고, 사용할 <xref:System.Drawing.Printing.PrintDocument> 를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="50a13-112">다음 코드 예제에서 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 인스턴스를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="50a13-113">인쇄 문서는 <xref:System.Windows.Forms.PrintDialog.Document%2A> 속성에서 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="50a13-114">아래 예제에서는 인쇄 문서를 지정 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="50a13-115">이 예제에서는 폼에 <xref:System.Windows.Forms.Button> 컨트롤, `myDocument`이라는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 및 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
    ```vb  
    Private Sub Button1_Click(ByVal sender As System.Object, _  
       ByVal e As System.EventArgs) Handles Button1.Click  
       ' The print document 'myDocument' used below  
       ' is merely for an example.  
       ' You will have to specify your own print document.  
       PrintPreviewDialog1.Document = myDocument  
       PrintPreviewDialog1.ShowDialog()  
    End Sub  
    ```  
  
    ```csharp  
    private void button1_Click(object sender, System.EventArgs e)  
    {  
       // The print document 'myDocument' used below  
       // is merely for an example.  
       // You will have to specify your own print document.  
       printPreviewDialog1.Document = myDocument;  
       printPreviewDialog1.ShowDialog();  
    }  
    ```  
  
    ```cpp  
    private:  
       void button1_Click(System::Object ^ sender,  
          System::EventArgs ^ e)  
       {  
          // The print document 'myDocument' used below  
          // is merely for an example.  
          // You will have to specify your own print document.  
          printPreviewDialog1->Document = myDocument;  
          printPreviewDialog1->ShowDialog();  
       }  
    ```  
  
     <span data-ttu-id="50a13-116">(시각적 C#개체, C++시각적 개체) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="50a13-116">(Visual C#, Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="50a13-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="50a13-117">See also</span></span>

- [<span data-ttu-id="50a13-118">PrintDocument 구성 요소</span><span class="sxs-lookup"><span data-stu-id="50a13-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="50a13-119">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="50a13-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="50a13-120">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="50a13-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="50a13-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="50a13-121">Windows Forms</span></span>](../index.md)
