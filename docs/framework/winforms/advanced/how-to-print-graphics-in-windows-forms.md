---
title: '방법: 그래픽 인쇄'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- graphics [Windows Forms], printing
- printing [Windows Forms], graphics
ms.assetid: 32b891e6-52ff-4fea-a9ff-2ce5db20a4c6
ms.openlocfilehash: 15f3a507839430ce058302e7f5abd317ef84626f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182529"
---
# <a name="how-to-print-graphics-in-windows-forms"></a><span data-ttu-id="b938d-102">방법: Windows Forms의 그래픽 인쇄</span><span class="sxs-lookup"><span data-stu-id="b938d-102">How to: Print Graphics in Windows Forms</span></span>
<span data-ttu-id="b938d-103">Windows 기반 응용 프로그램에서 그래픽을 인쇄하는 경우가 자주 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b938d-103">Frequently, you will want to print graphics in your Windows-based application.</span></span> <span data-ttu-id="b938d-104">클래스는 <xref:System.Drawing.Graphics> 화면이나 프린터와 같은 장치에 객체를 그리는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b938d-104">The <xref:System.Drawing.Graphics> class provides methods for drawing objects to a device, such as a screen or printer.</span></span>  
  
### <a name="to-print-graphics"></a><span data-ttu-id="b938d-105">그래픽을 인쇄하려면</span><span class="sxs-lookup"><span data-stu-id="b938d-105">To print graphics</span></span>  
  
1. <span data-ttu-id="b938d-106">양식에 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b938d-106">Add a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2. <span data-ttu-id="b938d-107"><xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트 처리기에서 <xref:System.Drawing.Printing.PrintPageEventArgs> 클래스의 <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> 속성을 사용하여 프린터에 인쇄할 그래픽 종류를 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="b938d-107">In the <xref:System.Drawing.Printing.PrintDocument.PrintPage> event handler, use the <xref:System.Drawing.Printing.PrintPageEventArgs.Graphics%2A> property of the <xref:System.Drawing.Printing.PrintPageEventArgs> class to instruct the printer on what kind of graphics to print.</span></span>  
  
     <span data-ttu-id="b938d-108">다음 코드 예제에서는 경계 사각형 내에서 파란색 타원을 만드는 데 사용되는 이벤트 처리기를 보여 주습니다.</span><span class="sxs-lookup"><span data-stu-id="b938d-108">The following code example shows an event handler used to create a blue ellipse within a bounding rectangle.</span></span> <span data-ttu-id="b938d-109">사각형에는 100부터 시작하여 너비가 250이고 높이가 250인 150부터 위치 및 치수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b938d-109">The rectangle has the following location and dimensions: beginning at 100, 150 with a width of 250 and a height of 250.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_PrintPage(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintPageEventArgs) Handles PrintDocument1.PrintPage  
       e.Graphics.FillEllipse(Brushes.Blue, New Rectangle(100, 150, 250, 250))  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_PrintPage(object sender,
    System.Drawing.Printing.PrintPageEventArgs e)  
    {  
       e.Graphics.FillRectangle(Brushes.Blue,
         new Rectangle(100, 150, 250, 250));  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_PrintPage(System::Object ^ sender,  
          System::Drawing::Printing::PrintPageEventArgs ^ e)  
       {  
          e->Graphics->FillRectangle(Brushes::Blue,  
             Rectangle(100, 150, 250, 250));  
       }  
    ```  
  
     <span data-ttu-id="b938d-110">(비주얼 C# 및 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b938d-110">(Visual C# and Visual C++) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.PrintPage += new  
       System.Drawing.Printing.PrintPageEventHandler  
       (this.printDocument1_PrintPage);  
    ```  
  
    ```cpp  
    this->printDocument1->PrintPage += gcnew  
       System::Drawing::Printing::PrintPageEventHandler  
       (this, &Form1::printDocument1_PrintPage);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="b938d-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b938d-111">See also</span></span>

- <xref:System.Drawing.Graphics>
- <xref:System.Drawing.Brush>
- [<span data-ttu-id="b938d-112">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="b938d-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
