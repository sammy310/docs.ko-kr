---
description: '자세한 정보: 논리 및 비트 연산자 Visual Basic'
title: 논리 및 비트 연산자
ms.date: 07/20/2015
helpviewer_keywords:
- short-circuiting
- Boolean expressions
- logical operators [Visual Basic], Boolean expressions
- operators [Visual Basic], logical
- AndAlso operator [Visual Basic]
- Not operator [Visual Basic], Boolean expressions
- Xor operator [Visual Basic], Boolean expressions
- And operator [Visual Basic], logical operators
- logical operators [Visual Basic]
- expressions [Visual Basic], Boolean
- Or operator [Visual Basic], logical operators
- Visual Basic code, operators
- short-circuiting [Visual Basic], logical operators
- logical operators [Visual Basic], short-circuiting
- Visual Basic code, expressions
- logical operators [Visual Basic], binary
- OrElse operator [Visual Basic]
- logical operators [Visual Basic], unary
ms.assetid: ca474e13-567d-4b1d-a18b-301433705e57
ms.openlocfilehash: 55d9567813a9114573e1e3f70fe181cb8621b350
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472724"
---
# <a name="logical-and-bitwise-operators-in-visual-basic"></a>Visual Basic의 논리 및 비트 연산자

논리 연산자 `Boolean` 는 식을 비교 하 고 `Boolean` 결과를 반환 합니다. `And`,, `Or` `AndAlso` , `OrElse` 및 연산자는 `Xor` 두 개의 피연산자를 사용 하는 반면 *이항* 는 `Not` 단일 피연산자를 사용 하기 때문에 *단항* 연산자입니다. 이러한 연산자 중 일부는 정수 값에 대해 비트 논리적 연산을 수행할 수도 있습니다.  
  
## <a name="unary-logical-operator"></a>단항 논리 연산자  

 [Not 연산자](../../../language-reference/operators/not-operator.md) 는 식에 논리 *부정을* 수행 합니다 `Boolean` . 피연산자와 반대 되는 논리를 생성 합니다. 식이로 계산 되 면 `True` 를 반환 하 고, `Not` `False` 식이로 계산 되 면를 반환 `False` `Not` `True` 합니다. 다음은 이에 대한 예입니다.  
  
 [!code-vb[VbVbalrOperators#77](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#77)]  
  
## <a name="binary-logical-operators"></a>이항 논리 연산자  

 [And 연산자](../../../language-reference/operators/and-operator.md) 는 두 식에 논리 *결합* 을 수행 `Boolean` 합니다. 두 식이 모두로 계산 `True` 되 면를 `And` 반환 `True` 합니다. 식 중 하나 이상이로 평가 `False` 되 면를 `And` 반환 `False` 합니다.  
  
 [Or 연산자](../../../language-reference/operators/or-operator.md) 는 두 식  에 논리합  연산을 수행 합니다 `Boolean` . 두 식이 모두로 계산 `True` 되거나 모두로 계산 `True` 되 면이 `Or` 반환 `True` 됩니다. 식이로 계산 되지 않는 경우 `True` 는을 `Or` 반환 `False` 합니다.  
  
 [Xor 연산자](../../../language-reference/operators/xor-operator.md) 는 두 식에 대해 논리적 *제외* 를 수행 합니다 `Boolean` . 정확히 하나의 식이로 계산 `True` 되지만 둘 다로 계산 되지 않는 경우는를 `Xor` 반환 `True` 합니다. 두 식이 모두로 계산 `True` 되거나 모두로 계산 `False` 되는 경우는를 `Xor` 반환 `False` 합니다.  
  
 다음 예에서는 `And` , 및 연산자를 보여 줍니다 `Or` `Xor` .  
  
 [!code-vb[VbVbalrOperators#78](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#78)]  
  
## <a name="short-circuiting-logical-operations"></a>Short-Circuiting 논리 작업  

 [AndAlso 연산자](../../../language-reference/operators/andalso-operator.md) 는 `And` 두 식에서 논리적 결합도 수행 한다는 점에서 연산자와 매우 비슷합니다 `Boolean` . 둘 사이의 주요 차이점은 `AndAlso` *단락* 동작을 보여 주는 것입니다. 식의 첫 번째 식이 `AndAlso` 로 계산 되는 경우 `False` 최종 결과를 변경할 수 없고를 반환할 수 없으므로 두 번째 식이 계산 되지 않습니다 `AndAlso` `False` .  
  
 마찬가지로 [OrElse 연산자](../../../language-reference/operators/orelse-operator.md) 는 두 식에 순환이 짧은 논리 분리를 수행 `Boolean` 합니다. 식의 첫 번째 식이 `OrElse` 로 계산 되는 경우 `True` 최종 결과를 변경할 수 없고를 반환할 수 없으므로 두 번째 식이 계산 되지 않습니다 `OrElse` `True` .  
  
### <a name="short-circuiting-trade-offs"></a>Short-Circuiting Trade-Offs  

 단락을 통해 논리 연산의 결과를 변경할 수 없는 식을 계산 하지 않고 성능을 향상 시킬 수 있습니다. 그러나 해당 식에서 추가 작업을 수행 하는 경우 단락에서는 이러한 작업을 건너뜁니다. 예를 들어 식에 프로시저에 대 한 호출이 포함 된 경우 `Function` 식이 short short-circuit 경우 해당 프로시저는 호출 되지 않으며에 포함 된 추가 코드는 `Function` 실행 되지 않습니다. 따라서 함수는 가끔씩만 실행 될 수 있으며 제대로 테스트 되지 않을 수도 있습니다. 또는 프로그램 논리는의 코드에 따라 달라질 수 있습니다 `Function` .  
  
 다음 예제에서는 `And` , 및의 단락에 대 한 차이점을 보여 줍니다 `Or` .  
  
 [!code-vb[VbVbalrOperators#81](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#81)]  
  
 [!code-vb[VbVbalrOperators#80](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#80)]  
  
 [!code-vb[VbVbalrOperators#79](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#79)]  
  
 앞의 예제에서 내부의 일부 중요 한 코드는 `checkIfValid()` 호출이 단기 short-circuit 때 실행 되지 않습니다. `If` `checkIfValid()` `12 > 45` `False` 가 short 회로를 포함 하지 않기 때문에 첫 번째 문은를 반환 합니다 `And` . 두 번째 `If` 문은가를 `checkIfValid()` `12 > 45` 반환할 때 `False` `AndAlso` 두 번째 식을 short 회로 하므로를 호출 하지 않습니다. `If` `checkIfValid()` `12 < 45` `True` 이 짧은 회로를 포함 하지 않으므로 세 번째 문은를 반환 하지만를 호출 합니다 `Or` . 가를 `If` `checkIfValid()` `12 < 45` 반환 하면 `True` `OrElse` 두 번째 식을 short 회로 하므로 네 번째 문은를 호출 하지 않습니다.  
  
## <a name="bitwise-operations"></a>비트 연산  

 비트 연산은 이진 (기본 2) 형식으로 두 개의 정수 값을 평가 합니다. 해당 위치의 비트를 비교한 다음 비교에 따라 값을 할당 합니다. 다음 예에서는 연산자를 보여 줍니다 `And` .  
  
 [!code-vb[VbVbalrConcepts#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConcepts/VB/Class1.vb#2)]  
  
 앞의 예제에서는의 값을 `x` 1로 설정 합니다. 이 문제는 다음과 같은 이유로 발생 합니다.  
  
- 값은 binary로 처리 됩니다.  
  
     3 이진 형식 = 011  
  
     5 이진 형식 = 101  
  
- `And`연산자는 한 번에 하나의 이진 위치 (비트)를 비교 합니다. 지정 된 위치에 있는 두 비트가 모두 1 이면 결과의 해당 위치에 1이 배치 됩니다. 두 비트가 모두 0 인 경우 결과의 해당 위치에 0이 배치 됩니다. 위의 예제에서는 다음과 같이 작동 합니다.  
  
     011 (이진 형식의 경우 3)  
  
     101 (이진 형식의 5)  
  
     001 (이진 형식으로 된 결과)  
  
- 결과는 10 진수로 처리 됩니다. 값 001은 1의 이진 표현 이므로 `x` = 1입니다.  
  
 비교 하는 비트 `Or` 중 하나 또는 둘 다가 1 이면 결과 비트에 1이 할당 된다는 점을 제외 하 고 비트 연산은 비슷합니다. `Xor` 비교 된 비트 (둘 다) 중 정확히 하나가 1 이면 결과 비트에 1을 할당 합니다. `Not` 단일 피연산자를 사용 하 고 부호 비트를 포함 하 여 모든 비트를 반전 하 고 결과에 해당 값을 할당 합니다. 즉, 부호 있는 양수의 경우 `Not` 항상 음수 값을 반환 하 고 음수에 대해는 `Not` 항상 양수 또는 0 값을 반환 합니다.  
  
 `AndAlso`및 `OrElse` 연산자는 비트 연산을 지원 하지 않습니다.  
  
> [!NOTE]
> 비트 연산은 정수 계열 형식에 대해서만 수행할 수 있습니다. 비트 연산을 계속 하려면 부동 소수점 값을 정수 계열 형식으로 변환 해야 합니다.  
  
## <a name="see-also"></a>추가 정보

- [논리/비트 연산자(Visual Basic)](../../../language-reference/operators/logical-bitwise-operators.md)
- [부울 식](boolean-expressions.md)
- [Visual Basic의 산술 연산자](arithmetic-operators.md)
- [Comparison Operators in Visual Basic](comparison-operators.md)
- [Visual Basic의 연결 연산자](concatenation-operators.md)
- [연산자의 효율적 결합](efficient-combination-of-operators.md)
