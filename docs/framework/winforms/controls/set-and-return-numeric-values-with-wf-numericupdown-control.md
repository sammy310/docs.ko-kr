---
title: NumericUpDown 컨트롤을 사용 하 여 숫자 값 설정 및 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- numeric values [Windows Forms], Windows Forms
- Windows Forms, numeric values
- Windows Forms controls, NumericUpDown
- NumericUpDown control [Windows Forms], setting and returning values
ms.assetid: 5bd8f8cd-4c12-49ea-9cc3-2a647d064689
ms.openlocfilehash: a0b264fec9619b467c293bcb96278c4517775ac3
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743027"
---
# <a name="how-to-set-and-return-numeric-values-with-the-windows-forms-numericupdown-control"></a>방법: Windows Forms NumericUpDown 컨트롤을 사용하여 숫자 값 설정 및 반환
Windows Forms <xref:System.Windows.Forms.NumericUpDown> 컨트롤의 숫자 값은 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성에 따라 결정 됩니다. 다른 속성과 마찬가지로 컨트롤 값에 대 한 조건부 테스트를 작성할 수 있습니다. <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성이 설정 되 면 작업을 수행 하는 코드를 작성 하 여 직접 조정 하거나 <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 및 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> 메서드를 호출할 수 있습니다.  
  
### <a name="to-set-the-numeric-value"></a>숫자 값을 설정 하려면  
  
1. 코드 또는 속성 창에서 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성에 값을 할당 합니다.  
  
    ```vb  
    NumericUpDown1.Value = 55  
    ```  
  
    ```csharp  
    numericUpDown1.Value = 55;  
    ```  
  
    ```cpp  
    numericUpDown1->Value = 55;  
    ```  
  
     -또는-  
  
2. <xref:System.Windows.Forms.NumericUpDown.UpButton%2A> 또는 <xref:System.Windows.Forms.NumericUpDown.DownButton%2A> 메서드를 호출 하 여 <xref:System.Windows.Forms.NumericUpDown.Increment%2A> 속성에 지정 된 양만큼 값을 늘리거나 줄입니다.  
  
    ```vb  
    NumericUpDown1.UpButton()  
    ```  
  
    ```csharp  
    numericUpDown1.UpButton();  
    ```  
  
    ```cpp  
    numericUpDown1->UpButton();  
    ```  
  
### <a name="to-return-the-numeric-value"></a>숫자 값을 반환 하려면  
  
- 코드에서 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성에 액세스 합니다.  
  
    ```vb  
    If NumericUpDown1.Value >= 65 Then  
       MessageBox.Show("Age is: " & NumericUpDown1.Value.ToString)  
    Else  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.")  
    End If  
    ```  
  
    ```csharp  
    if(numericUpDown1.Value >= 65)  
    {  
       MessageBox.Show("Age is: " + numericUpDown1.Value.ToString());  
    }  
    else  
    {  
       MessageBox.Show("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
    ```cpp  
    if(numericUpDown1->Value >= 65)  
    {  
       MessageBox::Show(String::Concat("Age is: ",  
          numericUpDown1->Value.ToString()));  
    }  
    else  
    {  
       MessageBox::Show  
          ("The customer is ineligible for a senior citizen discount.");  
    }  
    ```  
  
## <a name="see-also"></a>참조

- <xref:System.Windows.Forms.NumericUpDown>
- <xref:System.Windows.Forms.NumericUpDown.Value%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.Increment%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.UpButton%2A?displayProperty=nameWithType>
- <xref:System.Windows.Forms.NumericUpDown.DownButton%2A?displayProperty=nameWithType>
- [NumericUpDown 컨트롤](numericupdown-control-windows-forms.md)
- [NumericUpDown 컨트롤 개요](numericupdown-control-overview-windows-forms.md)
