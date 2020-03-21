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
ms.openlocfilehash: 62f67002bfbaf46e73bae06fdaff26efde865c06
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182594"
---
# <a name="how-to-complete-windows-forms-print-jobs"></a>방법: Windows Forms 인쇄 작업 완료
종종 워드 프로세서 및 인쇄와 관련된 기타 응용 프로그램은 인쇄 작업이 완료되었다는 메시지를 사용자에게 표시하는 옵션을 제공합니다. <xref:System.Drawing.Printing.PrintDocument> 구성 요소의 <xref:System.Drawing.Printing.PrintDocument.EndPrint> 이벤트를 처리 하여 Windows Forms에서 이 기능을 제공할 수 있습니다.  
  
 다음 절차에서는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소가 있는 Windows 기반 응용 프로그램을 만들어야 합니다. 구성 요소를 사용하여 Windows Forms에서 인쇄하는 방법에 대한 자세한 내용은 [표준 Windows 양식 인쇄 작업 만들기](how-to-create-standard-windows-forms-print-jobs.md)를 참조하십시오. <xref:System.Drawing.Printing.PrintDocument>  
  
### <a name="to-complete-a-print-job"></a>인쇄 작업을 완료하려면  
  
1. 구성 <xref:System.Drawing.Printing.PrintDocument.DocumentName%2A> 요소의 <xref:System.Drawing.Printing.PrintDocument> 속성을 설정합니다.  
  
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
  
     다음 코드 예제에서는 문서 인쇄가 완료되었음을 나타내는 메시지 상자가 표시됩니다.  
  
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
  
     (비주얼 C# 및 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
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
