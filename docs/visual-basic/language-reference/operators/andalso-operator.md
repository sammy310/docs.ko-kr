---
description: '자세한 정보: AndAlso 연산자 (Visual Basic)'
title: AndAlso 연산자
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
ms.openlocfilehash: dcf6c2685bf8f9ffee27b00543786cd3b315b327
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774267"
---
# <a name="andalso-operator-visual-basic"></a>AndAlso 연산자(Visual Basic)

두 식에 순환이 짧은 논리 결합을 수행 합니다.  
  
## <a name="syntax"></a>Syntax  
  
```vb
result = expression1 AndAlso expression2  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`result`|필수 요소. 임의의 `Boolean` 식입니다. 결과는 `Boolean` 두 식을 비교한 결과입니다.|  
|`expression1`|필수 요소. 임의의 `Boolean` 식입니다.|  
|`expression2`|필수 요소. 임의의 `Boolean` 식입니다.|  
  
## <a name="remarks"></a>설명  

 컴파일된 코드가 다른 식의 결과에 따라 한 식의 계산을 무시할 수 있는 경우 논리 연산을 *단락* 이라고 합니다. 계산 된 첫 번째 식의 결과가 작업의 최종 결과를 결정 하는 경우 최종 결과를 변경할 수 없기 때문에 두 번째 식을 계산할 필요가 없습니다. 생략 된 식이 복잡 하거나 프로시저 호출이 포함 된 경우 단락을 통해 성능을 향상 시킬 수 있습니다.  
  
 두 식이 모두로 계산 `True` `result` 되는 경우은 `True` 입니다. 다음 표에서는를 결정 하는 방법을 보여 줍니다 `result` .  
  
|`expression1`가 인 경우|및 `expression2` 가|의 값 `result` 이 인 경우|  
|---|---|---|  
|`True`|`True`|`True`|  
|`True`|`False`|`False`|  
|`False`|(평가 안 함)|`False`|  
  
## <a name="data-types"></a>데이터 형식  

 `AndAlso`연산자는 [Boolean 데이터 형식](../data-types/boolean-data-type.md)에 대해서만 정의 됩니다. Visual Basic `Boolean` 는 식을 계산 하기 전에 필요에 따라 각 피연산자를 변환 합니다. 결과를 숫자 형식에 할당 하는 경우 Visual Basic은 해당 `Boolean` 형식으로 변환 하 고가 됩니다 `False` `0` `True` `-1` .
자세한 내용은 [부울 형식 변환](../data-types/boolean-data-type.md#type-conversions)을 참조 하세요.
  
## <a name="overloading"></a>오버로딩  

 [And 연산자](and-operator.md) 와 [IsFalse 연산자](isfalse-operator.md) 를 *오버 로드할* 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다. 및 연산자를 오버 로드 하면 `And` `IsFalse` 연산자의 동작에 영향을 줍니다 `AndAlso` . `AndAlso`및를 오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 `And` 다시 `IsFalse` 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  

 다음 예에서는 연산자를 사용 `AndAlso` 하 여 두 식에 논리 결합을 수행 합니다. 결과는 `Boolean` 전체 앞쪽 식이 true 인지 여부를 나타내는 값입니다. 첫 번째 식이 인 경우 `False` 두 번째 식이 계산 되지 않습니다.  
  
 [!code-vb[VbVbalrOperators#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#24)]  
  
 앞의 예제에서는 각각, 및의 결과를 생성 `True` `False` `False` 합니다. 를 계산할 때 `secondCheck` 첫 번째 식은 이미 이므로 두 번째 식은 계산 되지 않습니다 `False` . 그러나 두 번째 식은 계산에서 계산 됩니다 `thirdCheck` .  
  
## <a name="example"></a>예제  

 다음 예제에서는 `Function` 배열 요소 중에서 지정 된 값을 검색 하는 프로시저를 보여 줍니다. 배열이 비어 있거나 배열 길이가 초과 된 경우 `While` 문은 검색 값에 대해 배열 요소를 테스트 하지 않습니다.  
  
 [!code-vb[VbVbalrOperators#25](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#25)]  
  
## <a name="see-also"></a>참고 항목

- [논리/비트 연산자(Visual Basic)](logical-bitwise-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [And 연산자](and-operator.md)
- [IsFalse 연산자](isfalse-operator.md)
- [Visual Basic의 논리 및 비트 연산자](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
