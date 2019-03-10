---
title: '방법: 런타임에 PrintDialog에서 사용자 입력 캡처'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print options [Windows Forms], changing at run time
- printing [Windows Forms], options
- print options
- run time [Windows Forms], changing print options
ms.assetid: 438501d8-9a70-4fb3-aae6-e46579aba0c6
ms.openlocfilehash: 69a3632ddb4d68f5a916f5ffca020630abe1bd68
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57707336"
---
# <a name="how-to-capture-user-input-from-a-printdialog-at-run-time"></a><span data-ttu-id="a8f46-102">방법: 런타임에 PrintDialog에서 사용자 입력 캡처</span><span class="sxs-lookup"><span data-stu-id="a8f46-102">How to: Capture User Input from a PrintDialog at Run Time</span></span>
<span data-ttu-id="a8f46-103">디자인 타임에 인쇄 관련 옵션을 설정할 수 있지만 가능성이 가장 높은 사용자의 선택으로 인해 런타임에 이러한 옵션을 변경 하려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a8f46-103">While you can set options related to printing at design time, you will sometimes want to change these options at run time, most likely because of choices made by the user.</span></span> <span data-ttu-id="a8f46-104">사용 하 여 문서를 인쇄 하는 것에 대 한 사용자 입력을 캡처할 수 있습니다 합니다 <xref:System.Windows.Forms.PrintDialog> 하며 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f46-104">You can capture user input for printing a document using the <xref:System.Windows.Forms.PrintDialog> and the <xref:System.Drawing.Printing.PrintDocument> components.</span></span>  
  
### <a name="to-change-print-options-programmatically"></a><span data-ttu-id="a8f46-105">인쇄 옵션을 프로그래밍 방식으로 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="a8f46-105">To change print options programmatically</span></span>  
  
1.  <span data-ttu-id="a8f46-106">추가 된 <xref:System.Windows.Forms.PrintDialog> 및 <xref:System.Drawing.Printing.PrintDocument> 폼에 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f46-106">Add a <xref:System.Windows.Forms.PrintDialog> and a <xref:System.Drawing.Printing.PrintDocument> component to your form.</span></span>  
  
2.  <span data-ttu-id="a8f46-107">설정 합니다 <xref:System.Windows.Forms.PrintDialog.Document%2A> 의 속성을 <xref:System.Windows.Forms.PrintDialog> 에 <xref:System.Drawing.Printing.PrintDocument> 폼에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a8f46-107">Set the <xref:System.Windows.Forms.PrintDialog.Document%2A> property of the <xref:System.Windows.Forms.PrintDialog> to the <xref:System.Drawing.Printing.PrintDocument> added to the form.</span></span>  
  
    ```vb  
    PrintDialog1.Document = PrintDocument1  
    ```  
  
    ```csharp  
    printDialog1.Document = PrintDocument1;  
    ```  
  
    ```cpp  
    printDialog1->Document = PrintDocument1;  
    ```  
  
3.  <span data-ttu-id="a8f46-108">표시 된 <xref:System.Windows.Forms.PrintDialog> 를 사용 하 여 구성 요소는 <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> 메서드.</span><span class="sxs-lookup"><span data-stu-id="a8f46-108">Display the <xref:System.Windows.Forms.PrintDialog> component by using the <xref:System.Windows.Forms.CommonDialog.ShowDialog%2A> method.</span></span>  
  
    ```vb  
    PrintDialog1.ShowDialog()  
    ```  
  
    ```csharp  
    printDialog1.ShowDialog();  
    ```  
  
    ```cpp  
    printDialog1->ShowDialog();  
    ```  
  
4.  <span data-ttu-id="a8f46-109">사용자의 인쇄 선택 대화 상자에서 복사할 수는 <xref:System.Drawing.Printing.PrinterSettings> 의 속성을 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="a8f46-109">The user's printing choices from the dialog will be copied to the <xref:System.Drawing.Printing.PrinterSettings> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a8f46-110">참고자료</span><span class="sxs-lookup"><span data-stu-id="a8f46-110">See also</span></span>
- [<span data-ttu-id="a8f46-111">방법: Windows Forms에서 다중 페이지 텍스트 파일 인쇄</span><span class="sxs-lookup"><span data-stu-id="a8f46-111">How to: Print a Multi-Page Text File in Windows Forms</span></span>](how-to-print-a-multi-page-text-file-in-windows-forms.md)
- [<span data-ttu-id="a8f46-112">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="a8f46-112">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
