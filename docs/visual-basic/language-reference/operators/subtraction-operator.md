---
title: '- 연산자 (Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.Negate
- vb.-
helpviewer_keywords:
- operator [Visual Basic]
- operators [Visual Basic], subtraction
- operators [Visual Basic], difference
- negation operator [Visual Basic]
- operators [Visual Basic], arithmetic
- subtraction operator [Visual Basic], syntax
- arithmetic operators [Visual Basic], subtraction
- difference operator [Visual Basic]
- math operators [Visual Basic]
- operators [Visual Basic], negation
- minus operator [Visual Basic]
ms.assetid: bff2c368-662d-4c92-ac87-1d9bdfd3426a
ms.openlocfilehash: 1a5c47a2f1bc8a8b9e1b0263b90006a0e58e17bb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62013480"
---
# <a name="--operator-visual-basic"></a>- 연산자(Visual Basic)
두 숫자 식 또는 숫자 식의 음수 값 간의 차이 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
      expression1 – expression2  
- or -  
– expression1  
```  
  
## <a name="parts"></a>요소  
 `expression1`  
 필수 요소. 임의의 숫자 식입니다.  
  
 `expression2`  
 필수 하지 않는 경우는 `–` 연산자가 음수 값을 계산 합니다. 임의의 숫자 식입니다.  
  
## <a name="result"></a>결과  
 결과 차이점은 `expression1` 하 고 `expression2`, 또는의 부정된 값 `expression1`합니다.  
  
 결과 데이터 형식은 데이터 유형에 대 한 적절 한 숫자 형식 `expression1` 고 `expression2`입니다. "정수 산술" 표를 참조 하십시오 [연산자 결과의 데이터 형식](../../../visual-basic/language-reference/operators/data-types-of-operator-results.md)합니다.  
  
## <a name="supported-types"></a>지원 형식  
 모든 숫자 형식. 여기에 부동 소수점 및 부호 없는 형식 및 `Decimal`합니다.  
  
## <a name="remarks"></a>설명  
 이전에 표시 된 구문에 나오는 첫 번째 사용 합니다 `–` 연산자가 합니다 *이진* 두 숫자 식의 차이점에 대해 빼기 산술 연산자.  
  
 이전에 표시 된 구문에 표시 된 두 번째 사용에서 합니다 `–` 연산자가는 *단항* 부정 연산자 식의 음수 값입니다. 부호를 반대로 하는 부정은 이런 점에서 `expression1` 결과 양수 경우 `expression1` 음수입니다.  
  
 두 식이 [아무](../../../visual-basic/language-reference/nothing.md), `–` 연산자 0으로 처리 합니다.  
  
> [!NOTE]
>  합니다 `–` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `–` 연산자가 두 숫자 간의 차이 반환 하 고 계산 및 숫자를 부정 합니다.  
  
 [!code-vb[VbVbalrOperators#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#10)]  
  
 이러한 문 실행 한 후 다음 `binaryResult` 124.45 포함 및 `unaryResult` –334.90을 포함 합니다.  
  
## <a name="see-also"></a>참고자료

- [-= 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-assignment-operator.md)
- [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic의 산술 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators.md)
