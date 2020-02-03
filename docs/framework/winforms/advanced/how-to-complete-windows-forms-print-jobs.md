---
title: 인쇄 작업 완료
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- print jobs [Windows Forms], completing in Windows Forms
- printing [Windows Forms], print jobs
ms.assetid: 23ec74f7-34c5-4710-82a0-ee2914518548
ms.openlocfilehash: b8ef4fa05b2107247181e82b72389f9503507135
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76746496"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>방법: Windows Forms 인쇄 작업 완료
Word 프로세서 및 인쇄와 관련 된 기타 응용 프로그램은 종종 인쇄 작업이 완료 되었음을 사용자에 게 메시지를 표시 하는 옵션을 제공 합니다. <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 이벤트를 처리 하 여 Windows Forms에서이 기능을 제공할 수 있습니다.  
  
 다음 절차를 수행 하려면 Windows 기반 응용 프로그램에서 인쇄를 사용 하도록 설정 하는 표준 방법인 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용 하 여 Windows 기반 응용 프로그램을 만들어야 합니다. <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 사용 하 여 Windows Forms를 인쇄 하는 방법에 대 한 자세한 내용은 [방법: 표준 Windows Forms 인쇄 작업 만들기](how-to-create-standard-windows-forms-print-jobs.md)를 참조 하세요.  
  
### <a name="to-complete-a-print-job"></a>인쇄 작업을 완료 하려면  
  
1. <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> 속성을 설정 합니다.  
  
    ```vb  
    PrintDocument1.DocumentName = "MyTextFile"  
    ```  
  
    ```csharp  
    printDocument1.DocumentName = "MyTextFile";  
    ```  
  
    ```cpp  
    printDocument1->DocumentName = "MyTextFile";  
    ```  
  
2. <xref:System.Drawing.Printing.PrintDocument.EndPrint> 이벤트를 처리할 코드를 작성합니다.  
  
     다음 코드 예제에서는 문서의 인쇄가 완료 되었음을 나타내는 메시지 상자가 표시 됩니다.  
  
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
  
     (시각적 C# 개체 및 C++시각적 개체) 폼의 생성자에 다음 코드를 추가 하 여 이벤트 처리기를 등록 합니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- <xref:System.Drawing.Printing.PrintDocument>
- [Windows Forms 인쇄 지원](windows-forms-print-support.md)
