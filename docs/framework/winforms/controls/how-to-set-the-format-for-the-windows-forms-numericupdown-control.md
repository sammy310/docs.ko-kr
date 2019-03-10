---
title: '방법: Windows Forms NumericUpDown 컨트롤에 대 한 형식을 설정합니다'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- NumericUpDown control [Windows Forms], formatting values
- up-down controls [Windows Forms], formatting numeric values
ms.assetid: fa7c5557-6bfb-45b2-975d-8887b23b0ba0
ms.openlocfilehash: e5c387fe593082e08ad39cb4582c946ca986a79e
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/09/2019
ms.locfileid: "57713932"
---
# <a name="how-to-set-the-format-for-the-windows-forms-numericupdown-control"></a><span data-ttu-id="9a6de-102">방법: Windows Forms NumericUpDown 컨트롤에 대 한 형식을 설정합니다</span><span class="sxs-lookup"><span data-stu-id="9a6de-102">How to: Set the Format for the Windows Forms NumericUpDown Control</span></span>
<span data-ttu-id="9a6de-103">Windows Forms의 값이 표시 되는 방식을 구성할 수 있습니다 <xref:System.Windows.Forms.NumericUpDown> 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6de-103">You can configure how values are displayed in the Windows Forms <xref:System.Windows.Forms.NumericUpDown> control.</span></span> <span data-ttu-id="9a6de-104"><xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성 소수점 뒤에 얼마나 많은 숫자가 결정; 기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6de-104">The <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property determines how many numbers appear after the decimal point; the default is 0.</span></span> <span data-ttu-id="9a6de-105">합니다 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 구분 기호는 10 진수 3 자리 마다 삽입할 수 있는지 여부를 확인 하는 속성의 기본값은입니다 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6de-105">The <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property determines whether a separator will be inserted between every three decimal digits; the default is `false`.</span></span> <span data-ttu-id="9a6de-106">컨트롤 값을 표시할 수 10 진수 형식 대신 16 진수의 경우는 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성이 `true`; 기본값은 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6de-106">The control can display values in hexadecimal instead of decimal format, if the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property is set to `true`; the default is `false`.</span></span>  
  
### <a name="to-format-the-numeric-value"></a><span data-ttu-id="9a6de-107">숫자 값의 서식을 지정 하려면</span><span class="sxs-lookup"><span data-stu-id="9a6de-107">To format the numeric value</span></span>  
  
-   <span data-ttu-id="9a6de-108">10 진수 값을 설정 하 여 표시 합니다 <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> 속성을 설정 하 고는 정수를 <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> 속성을 `true` 또는 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a6de-108">Display a decimal value by setting the <xref:System.Windows.Forms.NumericUpDown.DecimalPlaces%2A> property to an integer and setting the <xref:System.Windows.Forms.NumericUpDown.ThousandsSeparator%2A> property to `true` or `false`.</span></span>  
  
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
  
     <span data-ttu-id="9a6de-109">또는</span><span class="sxs-lookup"><span data-stu-id="9a6de-109">-or-</span></span>  
  
-   <span data-ttu-id="9a6de-110">16 진수 값을 설정 하 여 표시 합니다 <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> 속성을 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6de-110">Display a hexadecimal value by setting the <xref:System.Windows.Forms.NumericUpDown.Hexadecimal%2A> property to `true`.</span></span>  
  
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
    >  <span data-ttu-id="9a6de-111">값이 16 진수도 폼에 표시 되는 경우에 모든 테스트에서 수행한는 <xref:System.Windows.Forms.NumericUpDown.Value%2A> 속성을 테스트는 해당 10 진수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a6de-111">Even if the value is displayed on the form as hexadecimal, any tests you perform on the <xref:System.Windows.Forms.NumericUpDown.Value%2A> property will be testing its decimal value.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a6de-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a6de-112">See also</span></span>
- <xref:System.Windows.Forms.NumericUpDown>
- [<span data-ttu-id="9a6de-113">NumericUpDown 컨트롤</span><span class="sxs-lookup"><span data-stu-id="9a6de-113">NumericUpDown Control</span></span>](numericupdown-control-windows-forms.md)
- [<span data-ttu-id="9a6de-114">NumericUpDown 컨트롤 개요</span><span class="sxs-lookup"><span data-stu-id="9a6de-114">NumericUpDown Control Overview</span></span>](numericupdown-control-overview-windows-forms.md)
