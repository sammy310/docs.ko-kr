---
title: '&amp; 연산자'
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
ms.openlocfilehash: d778c0c99d6d074fe8b73aaf3660074643e7e136
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84371611"
---
# <a name="amp-operator-visual-basic"></a>&amp; 연산자 (Visual Basic)
두 식의 문자열 연결을 생성 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
result = expression1 & expression2  
```  
  
## <a name="parts"></a>부분  
 `result`  
 필수 요소. Any `String` 또는 `Object` variable.  
  
 `expression1`  
 필수 요소. 로 확대 되는 데이터 형식을 사용 하는 모든 식 `String` 입니다.  
  
 `expression2`  
 필수 요소. 로 확대 되는 데이터 형식을 사용 하는 모든 식 `String` 입니다.  
  
## <a name="remarks"></a>설명  
 또는의 데이터 형식이 `expression1` `expression2` 이 아닌로 확대 된 경우로 `String` `String` 변환 됩니다 `String` . 데이터 형식 중 하나가로 확장 되지 않는 경우 `String` 컴파일러에서 오류를 생성 합니다.  
  
 의 데이터 형식이 `result` 인 경우 `String` 하나 또는 두 식이 모두 [Nothing](../nothing.md) 으로 평가 되거나 값이 인 경우 <xref:System.DBNull.Value?displayProperty=nameWithType> 값이 "" 인 문자열로 처리 됩니다.  
  
> [!NOTE]
> `&`연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
> [!NOTE]
> 앰퍼샌드 (&) 문자를 사용 하 여 변수를 형식으로 식별할 수도 있습니다 `Long` . 자세한 내용은 [형식 문자](../../programming-guide/language-features/data-types/type-characters.md)를 참조 하십시오.  
  
## <a name="example"></a>예제  
 이 예에서는 연산자를 사용 `&` 하 여 문자열을 연결 합니다. 결과는 두 문자열 피연산자의 연결을 나타내는 문자열 값입니다.  
  
 [!code-vb[VbVbalrOperators#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#2)]  
  
## <a name="see-also"></a>참고 항목

- [&= 연산자](and-assignment-operator.md)
- [연결 연산자](concatenation-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [Visual Basic의 연결 연산자](../../programming-guide/language-features/operators-and-expressions/concatenation-operators.md)
