---
title: AndAlso 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AndAlso
- AndAlso
helpviewer_keywords:
- short-circuiting
- AndAlso operator [Visual Basic]
- operators [Visual Basic], short-circuiting
- operators [Visual Basic], conjunction
- short-circuit evaluation
ms.assetid: bbc15191-b374-495b-9b8f-7b8c2f4388eb
ms.openlocfilehash: 1cb4d372d3ac228f29c6fa45f124796e5dfb6709
ms.sourcegitcommit: 83ecdf731dc1920bca31f017b1556c917aafd7a0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/12/2019
ms.locfileid: "67859893"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso 연산자(Visual Basic)
두 식에 논리 결합을 단락 (short-circuiting)를 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`result`|필수 요소. 임의의 `Boolean` 식입니다. 결과 `Boolean` 두 식의 비교의 결과입니다.|  
|`expression1`|필수 요소. 임의의 `Boolean` 식입니다.|  
|`expression2`|필수. 임의의 `Boolean` 식입니다.|  
  
## <a name="remarks"></a>설명  
 논리 연산 이라고 *단락 (short-circuiting)* 컴파일된 코드를 다른 식의 결과 따라 하나의 식의 평가 건너뛸 수 있는 경우. 작업의 최종 결과 결정 하는 계산 되는 첫 번째 식의 결과 경우 두 번째 식을 평가 하지 않아도 최종 결과 변경할 수 없습니다 때문입니다. 단락 (short-circuiting) 바이패스 된 식이 복잡 한 경우 또는 프로시저 호출이 포함 되는 경우 성능을 향상 시킬 수 있습니다.  
  
 두 식이 모두로 평가 되 면 `True`, `result` 는 `True`합니다. 다음 표에서 설명 하는 방법을 `result` 결정 됩니다.  
  
|경우 `expression1` 됩니다|및 `expression2` 됩니다|변수의 `result` 는|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(평가 되지 않음)|`False`|  
  
## <a name="data-types"></a>데이터 형식  
 `AndAlso` 연산자에 대해서만 정의 되는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)합니다. Visual Basic 변환 필요에 따라 각 피연산자 `Boolean` 식을 계산 하기 전에 합니다. Visual Basic에서 변환 하는 숫자 형식으로 결과 할당 하는 경우 `Boolean` 해당 형식에는 `False` 됩니다 `0` 하 고 `True` 됩니다 `-1`합니다.
자세한 내용은 참조 하세요. [부울 형식 변환](../data-types/boolean-data-type.md#type-conversions)
  
## <a name="overloading"></a>오버로딩  
 [및 연산자](../../../visual-basic/language-reference/operators/and-operator.md) 하며 [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md) 일 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할 해당 동작의 형식에 클래스 또는 구조입니다. 오버 로드는 `And` 하 고 `IsFalse` 연산자의 동작에 영향을 줍니다는 `AndAlso` 연산자입니다. 코드를 사용 하는 경우 `AndAlso` 클래스 또는 구조체에 오버 로드에서 `And` 및 `IsFalse`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `AndAlso` 두 식에 논리 결합을 수행 하는 연산자입니다. 결과 `Boolean` 전체 식이 있는지 여부를 나타내는 값이 true입니다. 첫 번째 식이 `False`, 두 번째는 평가 되지 않습니다.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 앞의 예제 결과 생성 `True`, `False`, 및 `False`, 각각. 계산에서 `secondCheck`, 첫 번째는 이미 이므로는 두 번째 식은 계산 되지 않습니다 `False`합니다. 그러나 두 번째 식 계산에서 계산 됩니다 `thirdCheck`합니다.  
  
## <a name="example"></a>예제  
 다음 예제와 `Function` 배열의 요소 중에서 지정 된 값을 검색 하는 프로시저입니다. 배열이 비어 있는 경우 또는 배열 길이 초과 하는 경우는 `While` 문은 검색 값을 비교 하 여 배열 요소를 테스트 하지 않습니다.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>참고자료

- [논리/비트 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [And 연산자](../../../visual-basic/language-reference/operators/and-operator.md)
- [IsFalse 연산자](../../../visual-basic/language-reference/operators/isfalse-operator.md)
- [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
