---
title: '방법: Windows Forms 인쇄 작업 완료'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: 256b9a3d8842aaa4b032e67ebac9ca6a9e1ef34a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61937854"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a><span data-ttu-id="fa9db-102">방법: Windows Forms 인쇄 작업 완료</span><span class="sxs-lookup"><span data-stu-id="fa9db-102">How to: Complete Windows Forms Print Jobs</span></span>
<span data-ttu-id="fa9db-103">자주, 워드 프로세서 및 인쇄와 관련 된 기타 응용 프로그램에 인쇄 작업을 완료 되었음을 사용자에 게 메시지를 표시 하는 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9db-103">Frequently, word processors and other applications that involve printing will provide the option to display a message to users that a print job is complete.</span></span> <span data-ttu-id="fa9db-104">처리 하 여 Windows Forms 프로그램에서이 기능을 제공할 수 있습니다 합니다 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 의 이벤트는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa9db-104">You can provide this functionality in your Windows Forms by handling the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
 <span data-ttu-id="fa9db-105">다음 절차를 수행 하려면 사용 하 여 Windows 기반 응용 프로그램을 만들었다고는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소에 표준 방식의 Windows 기반 응용 프로그램에서 인쇄를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9db-105">The following procedure requires that you have created a Windows-based application with a <xref:System.Drawing.Printing.PrintDocument> component on it, which is the standard way of enabling printing from a Windows-based application.</span></span> <span data-ttu-id="fa9db-106">사용 하 여 Windows Forms에서 인쇄에 대 한 자세한 내용은 합니다 <xref:System.Drawing.Printing.PrintDocument> 구성 요소 참조 [방법: 표준 Windows Forms 인쇄 작업 만들기](how-to-create-standard-windows-forms-print-jobs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9db-106">For more information about printing from Windows Forms using the <xref:System.Drawing.Printing.PrintDocument> component, see [How to: Create Standard Windows Forms Print Jobs](how-to-create-standard-windows-forms-print-jobs.md).</span></span>  
  
### <a name="to-complete-a-print-job"></a><span data-ttu-id="fa9db-107">인쇄 작업을 완료 하려면</span><span class="sxs-lookup"><span data-stu-id="fa9db-107">To complete a print job</span></span>  
  
1. <span data-ttu-id="fa9db-108">설정 합니다 <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> 의 속성을 <xref:System.Drawing.Printing.PrintDocument> 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fa9db-108">Set the <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> property of the <xref:System.Drawing.Printing.PrintDocument> component.</span></span>  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <span data-ttu-id="fa9db-109"><xref:System.Drawing.Printing.PrintDocument.EndPrint> 이벤트를 처리할 코드를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9db-109">Write code to handle the <xref:System.Drawing.Printing.PrintDocument.EndPrint> event.</span></span>  
  
     <span data-ttu-id="fa9db-110">다음 코드 예제, 문서 인쇄를 되었음을 나타내는 메시지 상자가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fa9db-110">In the following code example, a message box is displayed, indicating that the document has finished printing.</span></span>  
  
    ```vb  
    Private Sub PrintDocument1_EndPrint(ByVal sender As Object, ByVal e As System.Drawing.Printing.PrintEventArgs) Handles PrintDocument1.EndPrint  
       MessageBox.Show(PrintDocument1.DocumentName + " has finished printing.")  
    End Sub  
    ```  
  
    ```csharp  
    private void printDocument1_EndPrint(object sender,   
    System.Drawing.Printing.PrintEventArgs e)  
    {  
       MessageBox.Show(printDocument1.DocumentName +   
          " has finished printing.");  
    }  
    ```  
  
    ```cpp  
    private:  
       void printDocument1_EndPrint(System::Object ^ sender,  
          System::Drawing::Printing::PrintEventArgs ^ e)  
       {  
          MessageBox::Show(String::Concat(printDocument1->DocumentName,  
             " has finished printing."));  
       }  
    ```  
  
     <span data-ttu-id="fa9db-111">(Visual C# 및 [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) 이벤트 처리기를 등록 하려면 폼의 생성자에 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fa9db-111">(Visual C# and [!INCLUDE[vcprvc](../../../../includes/vcprvc-md.md)]) Place the following code in the form's constructor to register the event handler.</span></span>  
  
    ```csharp  
    this.printDocument1.EndPrint += new  
       System.Drawing.Printing.PrintEventHandler  
       (this.printDocument1_EndPrint);  
    ```  
  
    ```cpp  
    this->printDocument1->EndPrint += gcnew  
       System::Drawing::Printing::PrintEventHandler  
       (this, &Form1::printDocument1_EndPrint);  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="fa9db-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="fa9db-112">See also</span></span>

- <xref:System.Drawing.Printing.PrintDocument>
- [<span data-ttu-id="fa9db-113">Windows Forms 인쇄 지원</span><span class="sxs-lookup"><span data-stu-id="fa9db-113">Windows Forms Print Support</span></span>](windows-forms-print-support.md)
