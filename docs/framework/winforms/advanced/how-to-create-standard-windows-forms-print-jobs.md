---
title: 표준 인쇄 작업 만들기
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- printing [Windows Forms]
- printing [Windows Forms], creating print jobs
- printing [Visual Basic], in Windows applications
ms.assetid: 03342b90-9cfe-40b2-838b-b479a13c5dea
ms.openlocfilehash: 4850dc901630179cc44fefda7e25bbabcfb4725f
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76741512"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a><span data-ttu-id="04abe-102">방법: 표준 Windows Forms 인쇄 작업 만들기</span><span class="sxs-lookup"><span data-stu-id="04abe-102">How to: Create Standard Windows Forms Print Jobs</span></span>
<span data-ttu-id="04abe-103">Windows Forms의 인쇄 기초는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다. 특히 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트입니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-103">The foundation of printing in Windows Forms is the <xref:System.Drawing.Printing.PrintDocument> component—more specifically, the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span> <span data-ttu-id="04abe-104"><xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 처리 하는 코드를 작성 하 여 인쇄할 항목과 인쇄 방법을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-104">By writing code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event, you can specify what to print and how to print it.</span></span>  
  
### <a name="to-create-a-print-job"></a><span data-ttu-id="04abe-105">인쇄 작업을 만들려면</span><span class="sxs-lookup"><span data-stu-id="04abe-105">To create a print job</span></span>  
  
1. <span data-ttu-id="04abe-106"><xref:System.Drawing.Printing.PrintDocument> 구성 요소를 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="04abe-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 처리할 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-107">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event.</span></span>  
  
     <span data-ttu-id="04abe-108">사용자 고유의 인쇄 논리를 코딩 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-108">You will have to code your own printing logic.</span></span> <span data-ttu-id="04abe-109">또한 인쇄할 재질을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-109">Additionally, you will have to specify the material to be printed.</span></span>  
  
     <span data-ttu-id="04abe-110">다음 코드 예제에서는 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기에서 빨간 사각형 모양의 샘플 그래픽이 생성 되어 인쇄할 재질로 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-110">In the following code example, a sample graphic in the shape of a red rectangle is created in the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler to act as material to be printed.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillRectangle(Brushes.Red, New Rectangle(500, 500, 500, 500))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,   
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Red,   
         new Rectangle(500, 500, 500, 500));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Red,  
             Rectangle(500, 500, 500, 500));  
       }  
    ```  
  
     <span data-ttu-id="04abe-111">(시각적 C# 개체 및 C++시각적 개체) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-111">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
     <span data-ttu-id="04abe-112">또한 <xref:System.Drawing.Printing.PrintDocument.BeginPrint> 및 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 이벤트에 대 한 코드를 작성할 수 있습니다 .이 경우 인쇄 되는 페이지의 총 수를 나타내는 정수를 포함 하 여 각 페이지가 인쇄 될 때 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-112">You may also want to write code for the <xref:System.Drawing.Printing.PrintDocument.BeginPrint> and <xref:System.Drawing.Printing.PrintDocument.EndPrint> events, perhaps including an integer representing the total number of pages to print that is decremented as each page prints.</span></span>  
  
    > [!NOTE]
    > <span data-ttu-id="04abe-113">양식에 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 추가 하 여 사용자에 게 명확 하 고 효율적인 UI (사용자 인터페이스)를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-113">You can add a <xref:System.Windows.Forms.PrintDialog> component to your form to provide a clean and efficient user interface (UI) to your users.</span></span> <span data-ttu-id="04abe-114"><xref:System.Windows.Forms.PrintDialog> 구성 요소의 <xref:System.Windows.Forms.PrintDialog.Document%2A> 속성을 설정 하 여 양식에서 작업 중인 인쇄 문서와 관련 된 속성을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04abe-114">Setting the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> component enables you to set properties related to the print document you are working with on your form.</span></span> <span data-ttu-id="04abe-115"><xref:System.Windows.Forms.PrintDialog> 구성 요소에 대 한 자세한 내용은 [PrintDialog 구성 요소](../controls/printdialog-component-windows-forms.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04abe-115">For more information about the <xref:System.Windows.Forms.PrintDialog> component, see [PrintDialog Component](../controls/printdialog-component-windows-forms.md).</span></span>  
  
     <span data-ttu-id="04abe-116">프로그래밍 방식으로 인쇄 작업을 만드는 방법을 비롯 하 여 Windows Forms 인쇄 작업의 세부 정보에 대 한 자세한 내용은 <xref:System.Drawing.Printing.PrintPageEventArgs>을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="04abe-116">For more information about the specifics of Windows Forms print jobs, including how to create a print job programmatically, see <xref:System.Drawing.Printing.PrintPageEventArgs>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04abe-117">참조</span><span class="sxs-lookup"><span data-stu-id="04abe-117">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="04abe-118">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="04abe-118">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
