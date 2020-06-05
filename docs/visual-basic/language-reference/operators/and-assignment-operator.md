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
ms.openlocfilehash: db42f7be7225b866eacf5b73066754e91cd1a0f7
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371988"
---
# <a name="amp-operator-visual-basic"></a>&amp;= 연산자(Visual Basic)
`String`변수 또는 속성에 식을 연결 하 `String` 고 결과를 변수 또는 속성에 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a>부분  
 `variableorproperty`  
 필수 요소. `String`변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 임의의 `String` 식입니다.  
  
## <a name="remarks"></a>설명  
 연산자의 좌 변에 있는 요소는 `&=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다. 변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다. `&=`연산자는 `String` 오른쪽의 식을 `String` 왼쪽에 있는 변수나 속성에 연결 하 고 결과를 왼쪽에 있는 변수나 속성에 할당 합니다.  
  
## <a name="overloading"></a>오버로딩  
 [& 연산자](concatenation-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다. 연산자를 오버 로드 하면 `&` 연산자의 동작에 영향을 줍니다 `&=` . `&=`오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 다시 `&` 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예에서는 연산자를 사용 하 여 `&=` 두 변수를 연결 하 `String` 고 결과를 첫 번째 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a>참고 항목

- [& 연산자](concatenation-operator.md)
- [+ = 연산자](addition-assignment-operator.md)
- [할당 연산자](assignment-operators.md)
- [연결 연산자](concatenation-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [문](../../programming-guide/language-features/statements.md)
