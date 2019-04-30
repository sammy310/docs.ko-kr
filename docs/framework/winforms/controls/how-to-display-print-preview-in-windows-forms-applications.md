---
title: '방법: Windows Forms 애플리케이션에서 인쇄 미리 보기 표시'
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
ms.openlocfilehash: 22247c941eff575f0f3e5683e46376054ba13bb5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013421"
---
# <a name="how-to-display-print-preview-in-windows-forms-applications"></a><span data-ttu-id="a0fcb-102">방법: Windows Forms 애플리케이션에서 인쇄 미리 보기 표시</span><span class="sxs-lookup"><span data-stu-id="a0fcb-102">How to: Display Print Preview in Windows Forms Applications</span></span>
<span data-ttu-id="a0fcb-103">사용할 수는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤 사용자가 인쇄 되기 전에 문서를 자주 표시할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-103">You can use the <xref:System.Windows.Forms.PrintPreviewDialog> control to enable users to display a document, often before it is to be printed.</span></span>  
  
 <span data-ttu-id="a0fcb-104">이 작업을 수행 하려면 인스턴스를 지정 해야 합니다 <xref:System.Drawing.Printing.PrintDocument> 클래스 인쇄할 문서입니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-104">To do this, you need to specify an instance of the <xref:System.Drawing.Printing.PrintDocument> class; this is the document to be printed.</span></span> <span data-ttu-id="a0fcb-105">사용 하 여 인쇄 미리 보기를 사용 하는 방법에 대 한 자세한 내용은 합니다 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 참조 [방법: 인쇄 미리 보기를 사용 하 여 Windows Forms의 인쇄](../advanced/how-to-print-in-windows-forms-using-print-preview.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-105">For more information about using print preview with the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Print in Windows Forms Using Print Preview](../advanced/how-to-print-in-windows-forms-using-print-preview.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a0fcb-106">사용 하는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤 런타임 시 사용자가 프린터가 있어야 로컬 또는 네트워크를 통해 해당 컴퓨터에 설치 되어 방법을 <xref:System.Windows.Forms.PrintPreviewDialog> 인쇄 된 문서 모양을 구성 요소를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-106">To use the <xref:System.Windows.Forms.PrintPreviewDialog> control at run time, users must have a printer installed on their computer, either locally or through a network, as this is partly how the <xref:System.Windows.Forms.PrintPreviewDialog> component determines how a document will look when printed.</span></span>  
  
 <span data-ttu-id="a0fcb-107">합니다 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤이 사용 하 여 <xref:System.Drawing.Printing.PrinterSettings> 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-107">The <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PrinterSettings> class.</span></span> <span data-ttu-id="a0fcb-108">또한 합니다 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤이 사용 하는 <xref:System.Drawing.Printing.PageSettings> 클래스 처럼는 <xref:System.Windows.Forms.PrintPreviewDialog> 구성 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-108">Additionally, the <xref:System.Windows.Forms.PrintPreviewDialog> control uses the <xref:System.Drawing.Printing.PageSettings> class, just as the <xref:System.Windows.Forms.PrintPreviewDialog> component does.</span></span> <span data-ttu-id="a0fcb-109">지정 된 인쇄 문서를 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤의 <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> 속성은 모두의 인스턴스를 참조 합니다 <xref:System.Drawing.Printing.PrinterSettings> 및 <xref:System.Drawing.Printing.PageSettings> 클래스와 이러한 미리 보기 창에서 문서를 렌더링 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-109">The print document specified in the <xref:System.Windows.Forms.PrintPreviewDialog> control's <xref:System.Windows.Forms.PrintPreviewControl.Document%2A> property refers to instances of both the <xref:System.Drawing.Printing.PrinterSettings> and <xref:System.Drawing.Printing.PageSettings> classes, and these are used to render the document in the preview window.</span></span>  
  
### <a name="to-view-pages-using-the-printpreviewdialog-control"></a><span data-ttu-id="a0fcb-110">PrintPreviewDialog 컨트롤을 사용 하 여 페이지를 보려면</span><span class="sxs-lookup"><span data-stu-id="a0fcb-110">To view pages using the PrintPreviewDialog control</span></span>  
  
- <span data-ttu-id="a0fcb-111"><xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드를 사용하여 대화 상자를 표시하고, 사용할 <xref:System.Drawing.Printing.PrintDocument> 를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-111">Use the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method to display the dialog box, specifying the <xref:System.Drawing.Printing.PrintDocument> to use.</span></span>  
  
     <span data-ttu-id="a0fcb-112">다음 코드 예제에서는 <xref:System.Windows.Forms.Button> 컨트롤의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기의 인스턴스를 열고는 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-112">In the following code example, the <xref:System.Windows.Forms.Button> control's <xref:System.Windows.Forms.Control.Click> event handler opens an instance of the <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span> <span data-ttu-id="a0fcb-113">인쇄 문서에 지정 된 된 <xref:System.Windows.Forms.PrintDialog.Document%2A> 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-113">The print document is specified in the <xref:System.Windows.Forms.PrintDialog.Document%2A> property.</span></span> <span data-ttu-id="a0fcb-114">아래 예제에서는 인쇄 문서가 지정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-114">In the example below, no print document is specified.</span></span>  
  
     <span data-ttu-id="a0fcb-115">예제에서는 폼에 필요는 <xref:System.Windows.Forms.Button> 컨트롤을 <xref:System.Drawing.Printing.PrintDocument> 라는 구성 요소 `myDocument`, 및 <xref:System.Windows.Forms.PrintPreviewDialog> 컨트롤입니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-115">The example requires that your form has a <xref:System.Windows.Forms.Button> control, a <xref:System.Drawing.Printing.PrintDocument> component named `myDocument`, and a <xref:System.Windows.Forms.PrintPreviewDialog> control.</span></span>  
  
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
  
     <span data-ttu-id="a0fcb-116">(Visual C# [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0fcb-116">(Visual C#, [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.button1.Click += new System.EventHandler(this.button1_Click);  
    ```  
  
    ```cpp  
    this->button1->Click += gcnew  
       System::EventHandler(this, &Form1::button1_Click);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="a0fcb-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="a0fcb-117">See also</span></span>

- [<span data-ttu-id="a0fcb-118">PrintDocument 구성 요소</span><span class="sxs-lookup"><span data-stu-id="a0fcb-118">PrintDocument Component</span></span>](printdocument-component-windows-forms.md)
- [<span data-ttu-id="a0fcb-119">PrintPreviewDialog 컨트롤</span><span class="sxs-lookup"><span data-stu-id="a0fcb-119">PrintPreviewDialog Control</span></span>](printpreviewdialog-control-windows-forms.md)
- [<span data-ttu-id="a0fcb-120">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="a0fcb-120">Windows Forms Print Support</span></span>](../advanced/windows-forms-print-support.md)
- [<span data-ttu-id="a0fcb-121">Windows Forms</span><span class="sxs-lookup"><span data-stu-id="a0fcb-121">Windows Forms</span></span>](../index.md)
