---
title: '*= 연산자'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: b06ebcb4f4100a0621f52a769543c0fb24fbb4bf
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401500"
---
# <a name="-operator-visual-basic"></a>*= 연산자(Visual Basic)
변수 또는 속성의 값을 식의 값과 곱하고 결과를 변수 또는 속성에 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a>부분  
 `variableorproperty`  
 필수 요소. 임의의 숫자 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 임의의 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 연산자의 좌 변에 있는 요소는 `*=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다. 변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.  
  
 연산자는 먼저 연산자의 오른쪽에 있는 `*=` 식의 값을 연산자의 왼쪽에 있는 변수 또는 속성 값으로 곱합니다 (연산자의 왼쪽에 있는). 그런 다음 연산자는 해당 작업의 결과를 변수나 속성에 할당 합니다.  
  
## <a name="overloading"></a>오버로딩  
 [* 연산자](multiplication-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다. 연산자를 오버 로드 하면 `*` 연산자의 동작에 영향을 줍니다 `*=` . `*=`오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 다시 `*` 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예에서는 연산자를 사용 하 여 `*=` 한 `Integer` 변수를 두 번째 변수에 곱하고 결과를 첫 번째 변수에 할당 합니다.  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a>참고 항목

- [* 연산자](multiplication-operator.md)
- [할당 연산자](assignment-operators.md)
- [산술 연산자](arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [문](../../programming-guide/language-features/statements.md)
