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
ms.openlocfilehash: 7e25f25677fa684427bdaf00cea73916ffbad655
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58818620"
---
# <a name="and-operator-visual-basic"></a>And 연산자(Visual Basic)
두 논리 결합을 수행 `Boolean` 식이나 두 숫자 식에 비트 결합 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = expression1 And expression2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다. 부울 비교를 위해 `result` 는 두 개의 논리 결합을 `Boolean` 값입니다. 비트 연산의 경우 `result` 는 두 숫자 비트 패턴의 비트 결합을 나타내는 숫자 값입니다.  
  
 `expression1`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다.  
  
 `expression2`  
 필수. 모든 `Boolean` 또는 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 부울 비교를 위해 `result` 됩니다 `True` 두 경우에 `expression1` 및 `expression2` 평가 `True`합니다. 다음 표에서 설명 하는 방법을 `result` 결정 됩니다.  
  
|경우 `expression1` 됩니다|및 `expression2` 됩니다|변수의 `result` 는|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|`True`|`False`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
>  부울 비교의 경우에 `And` 연산자에는 항상 프로시저 호출을 포함할 수 있는 두 식을 계산 합니다. 합니다 [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md) 수행 *단락 (short-circuiting)*, 즉 `expression1` 됩니다 `False`, 다음 `expression2` 평가 되지 않습니다.  
  
 숫자 값을 적용할 때 합니다 `And` 연산자 두 숫자 식의 동일한 위치의 비트 비트 비교를 수행 하 고 해당 비트를 설정 `result` 다음 표에 따라 합니다.  
  
|경우에 비트 `expression1` 됩니다|비트 `expression2` 됩니다|비트 `result` 됩니다|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|0|  
|0|1|0|  
|0|0|0|  
  
> [!NOTE]
>  논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산의 정확한 결과 보장 하도록 괄호로 묶어야 합니다.  
  
## <a name="data-types"></a>데이터 형식  
 피연산자 하나 구성 하는 경우 `Boolean` Visual Basic 변환 식과 하나의 숫자 식의 `Boolean` 식을 숫자 값 (– 1 `True` 0에 대 한 `False`) 비트 연산을 수행 하 고 합니다.  
  
 데이터 형식의 결과 부울 비교를 위해 `Boolean`합니다. 결과 데이터 형식은 데이터 유형에 대 한 적절 한 숫자 형식에서 비트 비교 `expression1` 고 `expression2`입니다. "관계 및 비트 비교" 표를 참조 하세요 [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.  
  
> [!NOTE]
>  합니다 `And` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `And` 두 식에 논리 결합을 수행 하는 연산자입니다. 결과 `Boolean` 식을 모두 있는지 여부를 나타내는 값 `True`합니다.  
  
 [!code-vb[VbVbalrOperators#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#22)]  
  
 앞의 예제 결과 생성 `True` 고 `False`, 각각.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `And` 두 숫자 식의 개별 비트에 논리 결합을 수행 하는 연산자입니다. 피연산자의 해당 비트가 모두 1로 설정 하는 경우 결과 패턴의 비트가 설정 됩니다.  
  
 [!code-vb[VbVbalrOperators#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#23)]  
  
 앞의 예제는 각각 8, 2 및 0의 결과 생성합니다.  
  
## <a name="see-also"></a>참고자료

- [논리/비트 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [AndAlso 연산자](../../../visual-basic/language-reference/operators/andalso-operator.md)
- [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
