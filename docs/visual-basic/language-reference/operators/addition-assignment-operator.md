---
title: += 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: c2ce384901a9f0207e8279a5a07a88600c875e7f
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372209"
---
# <a name="-operator-visual-basic"></a>+= 연산자(Visual Basic)
숫자 식의 값을 숫자 변수나 속성의 값에 추가 하 고 결과를 변수 또는 속성에 할당 합니다. 를 사용 하 여 `String` 변수 또는 속성에 식을 연결 하 `String` 고 결과를 변수 또는 속성에 할당할 수도 있습니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
variableorproperty += expression  
```  
  
## <a name="parts"></a>부분  
 `variableorproperty`  
 필수 요소. 임의의 숫자 또는 `String` 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 임의의 숫자 또는 `String` 식입니다.  
  
## <a name="remarks"></a>설명  
 연산자의 좌 변에 있는 요소는 `+=` 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다. 변수 또는 속성은 [ReadOnly](../modifiers/readonly.md)일 수 없습니다.  
  
 `+=`연산자는 오른쪽의 값을 왼쪽에 있는 변수나 속성에 추가 하 고 결과를 왼쪽에 있는 변수나 속성에 할당 합니다. `+=`연산자를 사용 하 여 `String` 오른쪽에 있는 식을 `String` 왼쪽에 있는 변수나 속성에 연결 하 고 그 왼쪽에 있는 변수나 속성에 결과를 할당할 수도 있습니다.  
  
> [!NOTE]
> 연산자를 사용 하는 경우 `+=` 더하기 또는 문자열 연결의 발생 여부를 확인 하지 못할 수 있습니다. 모호성을 `&=` 없애고 자체 문서화 코드를 제공 하려면 연산자를 연결에 사용 합니다.  
  
 이 할당 연산자는 컴파일 환경에서 엄격한 의미 체계를 적용 하는 경우 암시적으로 확대를 수행 하지만 축소 변환을 수행 하지 않습니다. 이러한 변환에 대 한 자세한 내용은 [확대 및 축소 변환](../../programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)을 참조 하세요. Strict 및 관대 한 의미 체계에 대 한 자세한 내용은 [Option Strict 문](../statements/option-strict-statement.md)을 참조 하세요.  
  
 관대 한 의미 체계가 허용 되는 경우 `+=` 연산자는 연산자가 수행 하는 것과 같은 다양 한 문자열 및 숫자 변환을 암시적으로 수행 합니다 `+` . 이러한 변환에 대 한 자세한 내용은 [+ 연산자](addition-operator.md)를 참조 하세요.  
  
## <a name="overloading"></a>오버로딩  
 `+`연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. 연산자를 오버 로드 하면 `+` 연산자의 동작에 영향을 줍니다 `+=` . `+=`오버 로드 하는 클래스 또는 구조체에서 코드를 사용 하는 경우 다시 `+` 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예에서는 연산자를 사용 `+=` 하 여 한 변수의 값을 다른 변수의 값과 결합 합니다. 첫 번째 부분은 숫자 변수와 함께를 사용 하 여 `+=` 한 값을 다른 값에 추가 합니다. 두 번째 부분은 변수와 함께를 사용 하 여 `+=` `String` 한 값을 다른 값과 연결 합니다. 두 경우 모두 결과는 첫 번째 변수에 할당 됩니다.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 값은 `num1` 이제 13 이며 값은 `str1` 이제 "103"입니다.  
  
## <a name="see-also"></a>참고 항목

- [+ 연산자](addition-operator.md)
- [할당 연산자](assignment-operators.md)
- [산술 연산자](arithmetic-operators.md)
- [연결 연산자](concatenation-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [문](../../programming-guide/language-features/statements.md)
