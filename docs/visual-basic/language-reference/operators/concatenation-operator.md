---
title: '&amp; 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.&
helpviewer_keywords:
- And (&) operator
- ampersand operator (&)
- '& operator'
- concatenation operators [Visual Basic], syntax
- strings [Visual Basic], concatenating
ms.assetid: fefc3d00-cbf1-475c-8c5e-6fb213b3f85a
ms.openlocfilehash: d387b2dfdbb3fefe357364f7b2a3dde155cbd489
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69968349"
---
# <a name="amp-operator-visual-basic"></a>&amp; 연산자 (Visual Basic)
두 식의 문자열 연결을 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. Any `String` 또는`Object` variable.  
  
 `expression1`  
 필수 요소. 로 `String`확대 되는 데이터 형식을 사용 하는 모든 식입니다.  
  
 `expression2`  
 필수 요소. 로 `String`확대 되는 데이터 형식을 사용 하는 모든 식입니다.  
  
## <a name="remarks"></a>설명  
 또는 `expression1` `String` `String`의데이터형식이이 아닌로 확대 된 경우로 변환 `String`됩니다. `expression2` 데이터 형식 중 하나가로 `String`확장 되지 않는 경우 컴파일러에서 오류를 생성 합니다.  
  
 의 `result` 데이터 형식이 인 `String`경우 하나 또는 두 식이 모두 [Nothing](../../../visual-basic/language-reference/nothing.md) 으로 평가 되거나 값 <xref:System.DBNull.Value?displayProperty=nameWithType>이 인 경우 값이 "" 인 문자열로 처리 됩니다.  
  
> [!NOTE]
> 연산자를 오버 로드할 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. `&` 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
> [!NOTE]
> 앰퍼샌드 (&) 문자를 사용 하 여 변수를 형식 `Long`으로 식별할 수도 있습니다. 자세한 내용은 [형식 문자](../../../visual-basic/programming-guide/language-features/data-types/type-characters.md)를 참조 하십시오.  
  
## <a name="example"></a>예제  
 이 예에서는 `&` 연산자를 사용 하 여 문자열을 연결 합니다. 결과는 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>참고자료

- [&= 연산자](../../../visual-basic/language-reference/operators/and-assignment-operator.md)
- [연결 연산자](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic의 연결 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
