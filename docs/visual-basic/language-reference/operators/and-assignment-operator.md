---
title: '&amp;= 연산자'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: 8668bfcbf32bb34b422efe8116bbd12a2d80b1d4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350262"
---
# <a name="amp-operator-visual-basic"></a>&amp;= 연산자 (Visual Basic)
`String` 식을 `String` 변수 또는 속성에 연결 하 고 결과를 변수 또는 속성에 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. 모든 `String` 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 임의의 `String` 식입니다.  
  
## <a name="remarks"></a>설명  
 `&=` 연산자의 좌 변에 있는 요소는 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다. 변수 또는 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)일 수 없습니다. `&=` 연산자는 오른쪽의 `String` 식을 왼쪽에 있는 `String` 변수 또는 속성에 연결 하 고 그 왼쪽에 있는 변수나 속성에 결과를 할당 합니다.  
  
## <a name="overloading"></a>오버로드  
 [& 연산자](../../../visual-basic/language-reference/operators/concatenation-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다. `&` 연산자를 오버 로드 하면 `&=` 연산자의 동작에 영향을 줍니다. 코드에서 `&`오버 로드 하는 클래스 또는 구조체에 `&=`를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예에서는 `&=` 연산자를 사용 하 여 두 개의 `String` 변수를 연결 하 고 결과를 첫 번째 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>참고자료

- [& 연산자](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [+= 연산자](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [연결 연산자](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [문](../../../visual-basic/programming-guide/language-features/statements.md)
