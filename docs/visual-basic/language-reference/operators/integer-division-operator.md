---
title: '\ 연산자(Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.\
- '\'
helpviewer_keywords:
- division operator [Visual Basic], integer
- integer division operator [Visual Basic]
- zero, division by zero
- arithmetic operators [Visual Basic], division
- division [Visual Basic], by zero
- backslash (\) [Visual Basic]
- '\ operator [Visual Basic]'
- integer quotient
- math operators [Visual Basic]
- quotients, integer
- truncation [Visual Basic], integer division
ms.assetid: 4b0ee347-950c-45c9-8e23-54bc85df208e
ms.openlocfilehash: 1753199e2ecf3f156b90d8c0a5cacd672397260d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "58828706"
---
# <a name="-operator-visual-basic"></a>\ 연산자(Visual Basic)
두 숫자를 나누고 정수 결과 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
expression1 \ expression2  
```  
  
## <a name="parts"></a>요소  
 `expression1`  
 필수 요소. 임의의 숫자 식입니다.  
  
 `expression2`  
 필수. 임의의 숫자 식입니다.  
  
## <a name="supported-types"></a>지원 형식  
 모든 숫자 형식, 부동 소수점 및 부호 없는 형식을 포함 하 고 `Decimal`입니다.  
  
## <a name="result"></a>결과  
 결과의 정수 몫입니다 `expression1` 나눈 `expression2`, 나머지는 버리고 정수 부분만 남긴 합니다. 이 이라고 *잘림*합니다.  
  
 결과 데이터 형식은 데이터 유형에 대 한 적절 한 숫자 형식 `expression1` 고 `expression2`입니다. "정수 산술" 표를 참조 하십시오 [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.  
  
 합니다 [/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) 나머지 소수 부분을를 유지 하는 전체 몫을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 나누기를 수행 하기 전에 Visual Basic 모든 부동 소수점 숫자 식으로 변환 하려고 `Long`합니다. 하는 경우 `Option Strict` 는 `On`, 컴파일러 오류가 발생 합니다. 경우 `Option Strict` 됩니다 `Off`, <xref:System.OverflowException> 값의 범위를 벗어난 경우 가능 합니다 [Long 데이터 형식](../../../visual-basic/language-reference/data-types/long-data-type.md)합니다. 변환할 `Long` 적용할 이기도 *은행원의 반올림*합니다. 자세한 내용은 "소수 부분이"를 참조 하세요 [형식 변환 함수](../../../visual-basic/language-reference/functions/type-conversion-functions.md)합니다.  
  
 하는 경우 `expression1` 또는 `expression2` 로 [Nothing](../../../visual-basic/language-reference/nothing.md)를 0으로 처리 됩니다.  
  
## <a name="attempted-division-by-zero"></a>0으로 나누기  
 하는 경우 `expression2` 0으로 계산 되는 `\` 연산자 throw를 <xref:System.DivideByZeroException> 예외입니다. 모든 숫자 데이터 형식의 피연산자에 대 한 마찬가지입니다.  
  
> [!NOTE]
>  합니다 `\` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `\` 정수 나누기를 수행 하는 연산자입니다. 결과 나머지 삭제는 두 피연산자의 몫을 나타내는 정수입니다.  
  
 [!code-vb[VbVbalrOperators#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#18)]  
  
 식 앞의 예제에서는 각각 2, 3, 33으로,-22의 값을 반환합니다.  
  
## <a name="see-also"></a>참고자료

- [\\= 연산자](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [/ 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
