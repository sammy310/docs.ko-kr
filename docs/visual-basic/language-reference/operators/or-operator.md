---
title: Or 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.Or
helpviewer_keywords:
- Or operator [Visual Basic]
- operators [Visual Basic], bitwise
- inclusive Or operator [Visual Basic]
- bitwise operators [Visual Basic], OR operator
- Or keyword [Visual Basic]
- operators [Visual Basic], inclusive or
- operators [Visual Basic], disjunction
- bitwise comparison [Visual Basic]
- logical disjunction
- disjunction operator [Visual Basic]
ms.assetid: 41ed6905-bf3d-468a-9e3b-03c10d461891
ms.openlocfilehash: 657b2a473b23789a8ba25fbd11c6b83538fa7803
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401422"
---
# <a name="or-operator-visual-basic"></a>Or 연산자(Visual Basic)
두 식에 논리 분리를 수행 `Boolean` 하거나 두 숫자 식에 비트 분리를 수행 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
result = expression1 Or expression2  
```  
  
## <a name="parts"></a>부분  
 `result`  
 필수 요소. 임의의 `Boolean` 또는 숫자 식입니다. `Boolean`비교를 위해 `result` 는 두 값의 포함 논리 분리입니다 `Boolean` . 비트 연산의 경우 `result` 는 두 숫자 비트 패턴의 포함 비트 논리합을 나타내는 숫자 값입니다.  
  
 `expression1`  
 필수 요소. 임의의 `Boolean` 또는 숫자 식입니다.  
  
 `expression2`  
 필수 요소. 임의의 `Boolean` 또는 숫자 식입니다.  
  
## <a name="remarks"></a>설명  
 `Boolean`비교를 위해 `result` `False` 및가 모두 `expression1` `expression2` 로 계산 되는 경우에만가입니다 `False` . 다음 표에서는를 결정 하는 방법을 보여 줍니다 `result` .  
  
|`expression1`가 인 경우|및 `expression2` 가|의 값 `result` 이 인 경우|  
|-------------------------|--------------------------|------------------------------|  
|`True`|`True`|`True`|  
|`True`|`False`|`True`|  
|`False`|`True`|`True`|  
|`False`|`False`|`False`|  
  
> [!NOTE]
> 비교에서 `Boolean` `Or` 연산자는 항상 프로시저 호출을 포함 하는 두 식을 모두 계산 합니다. [OrElse 연산자](orelse-operator.md) 는 *단락*을 수행 합니다. 즉,가 이면 `expression1` 이 `True` `expression2` 계산 되지 않습니다.  
  
 비트 연산의 경우 연산자는 `Or` 두 숫자 식에서 동일 하 게 배치 된 비트의 비트 비교를 수행 하 고 다음 표에 따라의 해당 비트를 설정 합니다 `result` .  
  
|비트가 `expression1` 인 경우|그리고의 비트 `expression2` 는|`result`의 비트는|  
|--------------------------------|---------------------------------|----------------------------|  
|1|1|1|  
|1|0|1|  
|0|1|1|  
|0|0|0|  
  
> [!NOTE]
> 논리 및 비트 연산자는 다른 산술 및 관계형 연산자 보다 낮은 우선 순위를 가지 므로 정확한 실행을 위해 모든 비트 연산을 괄호로 묶어야 합니다.  
  
## <a name="data-types"></a>데이터 형식  
 피연산자가 하나의 `Boolean` 식과 하나의 숫자 식으로 구성 된 경우 Visual Basic는 `Boolean` 식을 숫자 값으로 변환 하 고 (에 대해-1의 경우 `True` `False` ) 비트 연산을 수행 합니다.  
  
 비교를 위해 `Boolean` 결과의 데이터 형식은 `Boolean` 입니다. 비트 비교의 경우 결과 데이터 형식은 및의 데이터 형식에 적합 한 숫자 형식입니다 `expression1` `expression2` . [연산자 결과의 데이터 형식](data-types-of-operator-results.md)에서 "관계형 및 비트 비교" 표를 참조 하세요.  
  
## <a name="overloading"></a>오버로딩  
 `Or`연산자를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 다시 정의할 수 있습니다. 코드가 이러한 클래스 또는 구조체에서이 연산자를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다. 자세한 내용은 [Operator Procedures](../../programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 다음 예에서는 연산자를 사용 `Or` 하 여 두 식에 대 한 포함 논리 분리를 수행 합니다. 결과는 `Boolean` 두 식 중 하나가 인지 여부를 나타내는 값입니다 `True` .  
  
 [!code-vb[VbVbalrOperators#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#35)]  
  
 앞의 예제에서는 각각, 및의 결과를 생성 `True` `True` `False` 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 연산자를 사용 `Or` 하 여 두 숫자 식의 개별 비트에 대 한 포함 논리 분리를 수행 합니다. 피연산자의 해당 비트 중 하나가 1로 설정 된 경우 결과 패턴의 비트가 설정 됩니다.  
  
 [!code-vb[VbVbalrOperators#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#36)]  
  
 앞의 예제에서는 각각 10, 14 및 14의 결과를 생성 합니다.  
  
## <a name="see-also"></a>참고 항목

- [논리/비트 연산자(Visual Basic)](logical-bitwise-operators.md)
- [Visual Basic에서의 연산자 우선 순위](operator-precedence.md)
- [기능별 연산자 목록](operators-listed-by-functionality.md)
- [OrElse 연산자](orelse-operator.md)
- [Visual Basic의 논리 및 비트 연산자](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
