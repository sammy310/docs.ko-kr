---
title: 연산자의 효율적 결합
ms.date: 07/20/2015
helpviewer_keywords:
- expressions [Visual Basic], parentheses
- operators [Visual Basic], associativity
- expressions [Visual Basic], operators
- operators [Visual Basic], precedence
- Visual Basic code, operators
- Visual Basic code, expressions
- operators [Visual Basic], complex expressions
- expressions [Visual Basic], complex
- parentheses [Visual Basic], complex expressions
- numeric expressions
ms.assetid: bd22340e-b5be-458b-8772-3916c02309a4
ms.openlocfilehash: 3088072646278dac13e4d483cb4f99297eaad9ca
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403474"
---
# <a name="efficient-combination-of-operators-visual-basic"></a>연산자의 효율적 결합(Visual Basic)
복잡 한 식에는 여러 연산자가 포함 될 수 있습니다. 다음은 이에 대한 예입니다.  
  
 `x = (45 * (y + z)) ^ (2 / 85) * 5 + z`  
  
 위의 예에 나와 있는 것과 같은 복잡 한 식을 만들려면 연산자 우선 순위 규칙을 철저 하 게 이해 해야 합니다. 자세한 내용은 [Visual Basic 연산자 우선 순위](../../../language-reference/operators/operator-precedence.md)를 참조 하세요.  
  
## <a name="parenthetical-expressions"></a>괄호 식  
 연산자 우선 순위에 따라 결정 되는 것과 다른 순서로 작업을 진행 하려는 경우가 종종 있습니다. 다음 예제를 살펴보십시오.  
  
 `x = z * y + 4`  
  
 앞의 예제에서는를에 곱한 `z` `y` 다음 결과를에 추가 `4` 합니다. 그러나 결과를에 곱하여를 추가 하려면 `y` `4` 괄호를 사용 하 `z` 여 일반적인 연산자 우선 순위를 재정의할 수 있습니다. 식을 괄호로 묶으면 연산자 우선 순위에 관계 없이 식이 먼저 계산 됩니다. 앞의 예제에서 더하기를 먼저 수행 하도록 하려면 다음 예제와 같이 다시 작성할 수 있습니다.  
  
 `x = z * (y + 4)`  
  
 앞의 예제에서는 `y` 및 `4` 를 추가한 다음이 합계를에 곱합니다 `z` .  
  
### <a name="nested-parenthetical-expressions"></a>중첩 된 괄호 식  
 여러 수준의 괄호에 식을 중첩 하 여 우선 순위를 추가로 재정의할 수 있습니다. 괄호 안의 가장 안쪽에 중첩 된 식은 먼저 계산 된 다음 가장 안쪽에 중첩 된 다음으로 가장 많이 중첩 된 식과 괄호 외부에 있는 식의 순서로 계산 됩니다. 다음은 이에 대한 예입니다.  
  
 `x = (z * 4) ^ (y * (z + 2))`  
  
 앞의 예제에서 `z + 2` 는 먼저 계산 된 다음 다른 괄호 식이 계산 됩니다. 더하기 또는 곱하기 보다 우선 순위가 높은 지 수는 다른 식이 괄호로 묶여 있기 때문에이 예제에서는 마지막으로 계산 됩니다.  
  
## <a name="see-also"></a>참고 항목

- [Visual Basic의 산술 연산자](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Visual Basic의 논리 및 비트 연산자](logical-and-bitwise-operators.md)
- [논리/비트 연산자(Visual Basic)](../../../language-reference/operators/logical-bitwise-operators.md)
- [부울 식](boolean-expressions.md)
- [값 비교](value-comparisons.md)
- [방법: 숫자 값 계산](how-to-calculate-numeric-values.md)
- [Visual Basic에서의 연산자 우선 순위](../../../language-reference/operators/operator-precedence.md)
