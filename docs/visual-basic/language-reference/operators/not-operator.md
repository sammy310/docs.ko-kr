---
title: Not 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Not
helpviewer_keywords:
- Boolean expressions, negating
- operators [Visual Basic], bitwise
- negation operator [Visual Basic]
- inverse bit values in variables [Visual Basic]
- bitwise operators [Visual Basic], NOT operator
- bitwise comparison [Visual Basic]
- Not operator [Visual Basic]
- logical negation
- operators [Visual Basic], negation
ms.assetid: 8f2ea83c-d2ed-480a-a474-3042a1cad9b5
ms.openlocfilehash: 4e54fdca9123ad5595eb9a8c5e2ac5bc303a8f6a
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58824215"
---
# <a name="not-operator-visual-basic"></a>Not 연산자(Visual Basic)
논리 부정 연산을 수행 하는 `Boolean` 식 또는 숫자 식에 비트 부정을 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
result = Not expression  
```  
  
## <a name="parts"></a>요소  
 `result`  
 필수 요소. 모든 `Boolean` 또는 숫자 식입니다.  
  
 `expression`  
 필수. 모든 `Boolean` 또는 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 에 대 한 `Boolean` 식에 다음 표에서 설명 하는 방법을 `result` 결정 됩니다.  
  
|경우 `expression` 됩니다|변수의 `result` 는|  
|------------------------|------------------------------|  
|`True`|`False`|  
|`False`|`True`|  
  
 숫자 식에 대 한 합니다 `Not` 연산자는 숫자 식의 비트 값을 반전 하 고의 해당 비트를 설정 `result` 다음 표에 따라 합니다.  
  
|경우에 비트 `expression` 됩니다|비트 `result` 됩니다|  
|-------------------------------|----------------------------|  
|1|0|  
|0|1|  
  
> [!NOTE]
>  논리 및 비트 연산자는 산술 및 관계형 연산자 보다 우선 순위가, 모든 비트 연산은 정확 하 게 실행 되도록 괄호로 묶어야 합니다.  
  
## <a name="data-types"></a>데이터 형식  
 데이터 형식의 결과 부울 부정, `Boolean`합니다. 비트 부정 결과 데이터 형식이 동일와 `expression`합니다. 그러나 식이 `Decimal`, 결과 `Long`합니다.  
  
## <a name="overloading"></a>오버로딩  
 합니다 `Not` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우. 이 연산자를 사용 하 여 이러한 클래스나 구조체에는 코드를 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예제에서는 합니다 `Not` 의 논리 부정 연산을 수행 하는 연산자는 `Boolean` 식입니다. 결과 `Boolean` 역순으로 식의 값을 나타내는 값입니다.  
  
 [!code-vb[VbVbalrOperators#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#33)]  
  
 앞의 예제 결과 생성 `False` 고 `True`, 각각.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Not` 연산자는 숫자 식의 개별 비트 논리 부정 연산을 수행 합니다. 결과 패턴의 비트가 부호 비트를 포함 하 여 피연산자 패턴에 해당 비트의 반대입니다.  
  
 [!code-vb[VbVbalrOperators#34](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#34)]  
  
 앞의 예제는 각각 – 11 고 –9,-7, 결과 생성합니다.  
  
## <a name="see-also"></a>참고자료

- [논리/비트 연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/logical-bitwise-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [Visual Basic의 논리 및 비트 연산자](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
