---
title: NumericUpDown 컨트롤의 형식 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: 5ef1c801e96bef7b92e7e69dc36491144c456eeb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76742181"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="d6e66-102">방법: Windows Forms NumericUpDown 컨트롤의 형식 설정</span><span class="sxs-lookup"><span data-stu-id="d6e66-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="d6e66-103">Windows Forms <xref:System.Windows.Forms.NumericUpDown> 컨트롤에 값이 표시 되는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6e66-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="d6e66-104"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성은 소수점 뒤에 표시 되는 숫자의 수를 결정 합니다. 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e66-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="d6e66-105"><xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 속성은 10 진수 3 자리 마다 구분 기호가 삽입 되는지 여부를 결정 합니다. 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e66-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="d6e66-106"><xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성이 `true`로 설정 된 경우 컨트롤은 10 진수 형식 대신 16 진수 형식으로 값을 표시할 수 있습니다. 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="d6e66-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="d6e66-107">숫자 값의 형식을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="d6e66-107">To format the numeric value</span></span>  
  
- <span data-ttu-id="d6e66-108"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성을 정수로 설정 하 고 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 속성을 `true` 또는 `false`로 설정 하 여 10 진수 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e66-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="d6e66-109">또는</span><span class="sxs-lookup"><span data-stu-id="d6e66-109">-or-</span></span>  
  
- <span data-ttu-id="d6e66-110"><xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성을 `true`설정 하 여 16 진수 값을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e66-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    > <span data-ttu-id="d6e66-111">값이 폼에 16 진수로 표시 되는 경우에도 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성에서 수행 하는 모든 테스트는 10 진수 값을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6e66-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6e66-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d6e66-112">See also</span></span>

- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="d6e66-113">NumericUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="d6e66-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="d6e66-114">NumericUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="d6e66-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
