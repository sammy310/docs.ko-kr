---
title: And 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.And
helpviewer_keywords:
- operators [Visual Basic], bitwise
- logical conjunction
- bitwise AND operator [Visual Basic]
- conjunction operator [Visual Basic]
- And operator [Visual Basic]
- bitwise operators [Visual Basic], AND operator
- operators [Visual Basic], conjunction
- bitwise comparison [Visual Basic]
ms.assetid: 2ea711f3-439a-4c7c-9e3a-1ffe3b0d6046
ms.openlocfilehash: a1802d3a7018b1b6190ff5601eba055e16e62371
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69913165"
---
# <a name="and-operator-visual-basic"></a>And 연산자(Visual Basic)
두 `Boolean` 식에 논리 결합을 수행 하거나 두 숫자 식에 비트 결합을 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다. 부울 비교 `result` 의 경우는 두 `Boolean` 값의 논리적 결합입니다. 비트 연산의 `result` 경우는 두 숫자 비트 패턴의 비트 결합을 나타내는 숫자 값입니다.  
  
 `expression1`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다.  
  
 `expression2`  
 필수. 모든 `Boolean` 또는 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 `result` 부울 비교의 경우와 `True` 가 모두 `expression1` `expression2` 로 `True`계산 되는 경우에만가입니다. 다음 표에서는를 결정 `result` 하는 방법을 보여 줍니다.  
  
|경우 `expression1` 됩니다|및 `expression2` 됩니다|의 `result` 값이 인 경우|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> 부울 비교에서 연산자는 `And` 항상 프로시저 호출을 포함 하는 두 식을 모두 계산 합니다. [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md) 는 *단락*을 수행 합니다. `expression1` 즉, `expression2` 가 `False`이면이 계산 되지 않습니다.  
  
 숫자 값에 적용 되는 연산자 `And` 는 두 숫자 식에서 동일 하 게 배치 된 비트의 비트 비교를 수행 하 고 다음 `result` 표에 따라의 해당 비트를 설정 합니다.  
  
|비트가 `expression1` 인 경우|그리고의 `expression2` 비트는|의 `result` 비트는|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
> 논리 및 비트 연산자는 다른 산술 및 관계형 연산자 보다 낮은 우선 순위를 가지 므로 정확한 결과를 얻으려면 모든 비트 연산을 괄호로 묶어야 합니다.  
  
## <a name="data-types"></a>데이터 형식  
 피연산자가 하나의 `Boolean` 식과 하나의 숫자 식으로 구성 된 경우 Visual Basic는 `Boolean` 식을 숫자 `True` 값으로 변환 하 고 (에 대해 `False`-1의 경우) 비트 연산을 수행 합니다.  
  
 부울 비교의 경우 결과 `Boolean`의 데이터 형식은입니다. 비트 비교의 경우 결과 데이터 형식은 및 `expression1` `expression2`의 데이터 형식에 적합 한 숫자 형식입니다. [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)에서 "관계형 및 비트 비교" 표를 참조 하세요.  
  
> [!NOTE]
> 연산자를 오버 로드할 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. `And` 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예에서는 `And` 연산자를 사용 하 여 두 식에 논리 결합을 수행 합니다. 결과는 두 `True`식이 `Boolean` 모두 인지 여부를 나타내는 값입니다.  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 앞의 예제에서는 각각 및 `True` `False`의 결과를 생성 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `And` 연산자를 사용 하 여 두 숫자 식의 개별 비트에 논리 결합을 수행 합니다. 피연산자의 해당 비트가 둘 다 1로 설정 된 경우 결과 패턴의 비트가 설정 됩니다.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 앞의 예제에서는 각각 8, 2 및 0의 결과를 생성 합니다.  
  
## <a name="see-also"></a>참고자료

- [논리/비트 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Visual Basic 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
