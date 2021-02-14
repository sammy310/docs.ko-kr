---
description: '자세한 정보: 방법: 숫자 값 계산 (Visual Basic)'
title: '방법: 숫자 값 계산'
ms.date: 07/20/2015
helpviewer_keywords:
- operator precedence
- operators [Visual Basic]
- expressions [Visual Basic], numeric
- calculations [Visual Basic], numeric expressions
- precedence [Visual Basic], of operators
- Visual Basic code, operators
- Visual Basic code, expressions
- numeric expressions
ms.assetid: ba6bf43d-bd96-49b8-b1de-4a7797551372
ms.openlocfilehash: 35acd7b9b1732514a8fe4399b6a815dce62b2468
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100435592"
---
# <a name="how-to-calculate-numeric-values-visual-basic"></a>방법: 숫자 값 계산(Visual Basic)

숫자 식을 사용 하 여 숫자 값을 계산할 수 있습니다. *숫자 식은* 숫자 값을 나타내는 리터럴, 상수 및 변수와 해당 값에 대해 작동 하는 연산자를 포함 하는 식입니다.  
  
## <a name="calculating-numeric-values"></a>숫자 값 계산  
  
#### <a name="to-calculate-a-numeric-value"></a>숫자 값을 계산 하려면  
  
- 하나 이상의 숫자 리터럴, 상수 및 변수를 숫자 식으로 결합 합니다. 다음 예에서는 몇 가지 유효한 숫자 식을 보여 줍니다.  
  
     `93.217`  
  
     `System.Math.PI`  
  
     `counter`  
  
     `4 * (67 + i)`  
  
     처음 세 줄은 리터럴, 상수 및 변수를 보여 줍니다. 각 항목은 유효한 숫자 식 자체를 형성 합니다. 마지막 줄은 두 개의 리터럴이 있는 변수의 조합을 보여 줍니다.  
  
     숫자 식 만으로는 완전 한 Visual Basic 문을 형성 하지 않습니다. 전체 문의 일부로 식을 사용 해야 합니다.  
  
#### <a name="to-store-a-numeric-value"></a>숫자 값을 저장 하려면  
  
- 다음 예제가 보여 주는 것 처럼 대입문을 사용 하 여 숫자 식으로 표시 된 값을 변수에 할당할 수 있습니다.  
  
     [!code-vb[VbVbalrOperators#82](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#82)]  
  
     앞의 예제에서 같음 연산자 ()의 오른쪽에 있는 식의 값은 `=` `j` 연산자의 좌 변에 있는 변수에 할당 되므로 `j` 276로 계산 됩니다.  
  
     자세한 내용은 [문](../../../language-reference/statements/index.md)을 참조하십시오.  
  
## <a name="multiple-operators"></a>여러 연산자  

 숫자 식에 여러 개의 연산자가 포함 된 경우 계산 되는 순서는 연산자 우선 순위 규칙에 따라 결정 됩니다. 연산자 우선 순위 규칙을 재정의 하려면 위 예제와 같이 식을 괄호로 묶습니다. 괄호로 묶인 식이 먼저 계산 됩니다.  
  
#### <a name="to-override-normal-operator-precedence"></a>일반적인 연산자 우선 순위를 재정의 하려면  
  
- 괄호를 사용 하 여 먼저 수행 하려는 작업을 묶습니다. 다음 예에서는 동일한 피연산자와 연산자를 사용 하는 두 개의 다른 결과를 보여 줍니다.  
  
     [!code-vb[VbVbalrOperators#83](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#83)]  
  
     위의 예제에서에 대 한 계산은 `j` 먼저 더하기 연산자 ()를 수행 합니다 `+` . 괄호는 `(67 + i)` 일반적인 우선 순위를 재정의 하 고에 할당 된 값은 `j` 276 (4 시간 69)입니다. 에 대 한 계산은 `k` 일반적인 우선 순위 (이전)에서 연산자를 수행 하 `*` `+` 고에 할당 된 값은 `k` 270 (268 plus 2)입니다.  
  
     자세한 내용은 [Visual Basic 연산자 우선 순위](../../../language-reference/operators/operator-precedence.md)를 참조 하세요.  
  
## <a name="see-also"></a>추가 정보

- [연산자 및 식](index.md)
- [값 비교](value-comparisons.md)
- [문](../../../language-reference/statements/index.md)
- [Visual Basic에서의 연산자 우선 순위](../../../language-reference/operators/operator-precedence.md)
- [산술 연산자](../../../language-reference/operators/arithmetic-operators.md)
- [연산자의 효율적 결합](efficient-combination-of-operators.md)
