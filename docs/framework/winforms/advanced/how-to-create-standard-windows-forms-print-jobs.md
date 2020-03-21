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
ms.openlocfilehash: d9607de7c74132e0d7dce605b16d62c79b7dbccb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79182576"
---
# <a name="how-to-create-standard-windows-forms-print-jobs"></a>방법: 표준 Windows Forms 인쇄 작업 만들기
Windows Forms에서 인쇄의 기초는 <xref:System.Drawing.Printing.PrintDocument> 구성 요소, <xref:System.Drawing.Printing.PrintDocument.PrintPage> 즉 더 구체적으로 이벤트입니다. <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 처리하는 코드를 작성하여 인쇄할 내용과 인쇄 방법을 지정할 수 있습니다.  
  
### <a name="to-create-a-print-job"></a>인쇄 작업을 만들려면  
  
1. 양식에 <xref:System.Drawing.Printing.PrintDocument> 구성 요소를 추가합니다.  
  
2. <xref:System.Drawing.Printing.PrintDocument.PrintPage> 이벤트를 처리할 코드를 작성합니다.  
  
     사용자 고유의 인쇄 논리를 코딩해야 합니다. 또한 인쇄할 재질을 지정해야 합니다.  
  
     다음 코드 예제에서는 인쇄할 재질역할을 하기 위해 이벤트 처리기에서 빨간색 사각형 모양의 샘플 그래픽이 <xref:System.Drawing.Printing.PrintDocument.PrintPage> 만들어집니다.  
  
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
  
     (비주얼 C# 및 비주얼 C++) 양식의 생성자에서 다음 코드를 배치하여 이벤트 처리기를 등록합니다.  
  
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
  
     각 페이지가 인쇄될 때 <xref:System.Drawing.Printing.PrintDocument.BeginPrint> <xref:System.Drawing.Printing.PrintDocument.EndPrint> 감소되는 총 페이지 수를 나타내는 정수를 포함하여 이벤트 및 이벤트에 대한 코드를 작성할 수도 있습니다.  
  
    > [!NOTE]
    > 양식에 <xref:System.Windows.Forms.PrintDialog> 구성 요소를 추가하여 사용자에게 깨끗하고 효율적인 사용자 인터페이스(UI)를 제공할 수 있습니다. <xref:System.Windows.Forms.PrintDialog> 구성 요소의 <xref:System.Windows.Forms.PrintDialog.Document%2A> 속성을 설정하면 양식에서 작업중인 인쇄 문서와 관련된 속성을 설정할 수 있습니다. 구성 요소에 대한 자세한 내용은 [PrintDialog 구성 요소](../controls/printdialog-component-windows-forms.md)를 참조하십시오. <xref:System.Windows.Forms.PrintDialog>  
  
     프로그래밍 방식으로 인쇄 작업을 만드는 방법을 포함하여 Windows Forms 인쇄 작업의 세부 사항에 <xref:System.Drawing.Printing.PrintPageEventArgs>대한 자세한 내용은 을 참조하십시오.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Drawing.Printing.PrintDocument>
- [Windows Forms 인쇄 지원](windows-forms-print-support.md)
