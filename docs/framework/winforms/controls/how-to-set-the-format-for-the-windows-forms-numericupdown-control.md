---
title: '방법: Windows Forms NumericUpDown 컨트롤에 대한 형식 설정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5957a44c7b07aa1b8d8df32667f023c0873ec1de
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186150"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a>방법: Windows Forms NumericUpDown 컨트롤에 대한 형식 설정
Windows Forms의 값이 표시 되는 방식을 구성할 수 있습니다 <xref:System.Windows.Forms.NumericUpDown> 제어 합니다. <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성 소수점 뒤에 얼마나 많은 숫자가 결정; 기본값은 0입니다. 합니다 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 구분 기호는 10 진수 3 자리 마다 삽입할 수 있는지 여부를 확인 하는 속성의 기본값은입니다 `false`합니다. 컨트롤 값을 표시할 수 10 진수 형식 대신 16 진수의 경우는 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성이 `true`; 기본값은 `false`합니다.  
  
### <a name="to-format-the-numeric-value"></a>숫자 값의 서식을 지정 하려면  
  
-   10 진수 값을 설정 하 여 표시 합니다 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성을 설정 하 고는 정수를 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 속성을 `true` 또는 `false`합니다.  
  
    ```vb  
    NumericUpDown1.DecimalPlaces = 2  
    NumericUpDown1.ThousandsSeparator = True  
    ```  
  
    ```csharp  
    numericUpDown1.DecimalPlaces = 2;  
    numericUpDown1.ThousandsSeparator = true;  
    ```  
  
    ```cpp  
    numericUpDown1->DecimalPlaces = 2;  
    numericUpDown1->ThousandsSeparator = true;  
    ```  
  
     또는  
  
-   16 진수 값을 설정 하 여 표시 합니다 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성을 `true`입니다.  
  
    ```vb  
    NumericUpDown1.Hexadecimal = True  
    ```  
  
    ```csharp  
    numericUpDown1.Hexadecimal = true;  
    ```  
  
    ```cpp  
    numericUpDown1->Hexadecimal = true;  
    ```  
  
    > [!NOTE]
    >  값이 16 진수도 폼에 표시 되는 경우에 모든 테스트에서 수행한는 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성을 테스트는 해당 10 진수 값입니다.  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.Forms.NumericUpDown>
- [NumericUpDown 컨트롤](numericupdown-control-windows-forms.md)
- [NumericUpDown 컨트롤 개요](numericupdown-control-overview-windows-forms.md)
