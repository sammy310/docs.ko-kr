---
title: += 연산자(Visual Basic)
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
ms.openlocfilehash: 4b8f36397d0f52866ebe9fa188d6b163364aeffc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58839021"
---
# <a name="-operator-visual-basic"></a>+= 연산자(Visual Basic)
숫자 변수 또는 속성의 값에 숫자 식의 값을 추가 하 고 그 결과 변수 또는 속성에 할당 합니다. 연결을 사용할 수도 있습니다는 `String` 식을 `String` 변수 또는 속성 및 변수 또는 속성에 결과 할당 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. 모든 숫자 또는 `String` 변수 또는 속성입니다.  
  
 `expression`  
 필수 요소. 모든 숫자 또는 `String` 식입니다.  
  
## <a name="remarks"></a>설명  
 왼쪽된에 있는 요소는 `+=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 수입니다. 변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.  
  
 `+=` 연산자는 변수 또는 속성의 왼쪽에서 오른쪽에 값을 추가 하 고 결과를 변수나 속성 왼쪽에 할당 합니다. `+=` 연결할 연산자 사용할 수도 있습니다는 `String` 는 오른쪽에 식이 `String` 변수 또는 결과 변수에 할당의 왼쪽에는 속성 또는 왼쪽의 속성입니다.  
  
> [!NOTE]
>  사용 하는 경우는 `+=` 연산자, 더하기 또는 문자열 연결 발생할 지 여부를 확인 하려면 못할 수 있습니다. 사용 된 `&=` 모호성을 제거 하 고 자동 문서화 코드를 제공 하도록 연결에 대 한 연산자입니다.  
  
 이 할당 연산자는 암시적으로 컴파일 환경에서 엄격한 의미 체계를 적용 하는 경우 변환 형식을 확장을 수행 합니다. 이러한 변환에 대 한 자세한 내용은 참조 하세요. [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)합니다. 엄격한 및 관대 한 의미 체계에 대 한 자세한 내용은 참조 하세요. [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.  
  
 관대 한 의미 체계에 허용 합니다 `+=` 다양 한 문자열 및 숫자 변환에서 수행 하는 동일한를 암시적으로 수행 하는 연산자는 `+` 연산자입니다. 이러한 변환에 대 한 내용은 참조 하세요 [+ 연산자](../../../visual-basic/language-reference/operators/addition-operator.md)합니다.  
  
## <a name="overloading"></a>오버로딩  
 합니다 `+` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 오버 로드 된 `+` 연산자의 동작에 영향을 줍니다는 `+=` 연산자입니다. 코드를 사용 하는 경우 `+=` 클래스나 구조체에 오버 로드에서 `+`, 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `+=` 다른 하나의 변수 값을 결합 하는 연산자입니다. 첫 번째 부분에서는 `+=` 다른 하나의 값을 추가 하려면 숫자 변수를 사용 합니다. 두 번째 부분에서는 `+=` 사용 하 여 `String` 다른 하나의 값을 연결 하는 변수입니다. 두 경우 모두 결과 첫 번째 변수에 할당 됩니다.  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 변수의 `num1` 의 값과 13, 이제는 `str1` 은 "103"입니다.  
  
## <a name="see-also"></a>참고자료

- [+ 연산자](../../../visual-basic/language-reference/operators/addition-operator.md)
- [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [연결 연산자](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [문(C++)](../../../visual-basic/programming-guide/language-features/statements.md)
