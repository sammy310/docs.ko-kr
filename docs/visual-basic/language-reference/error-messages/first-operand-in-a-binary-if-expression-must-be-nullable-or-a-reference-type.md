---
title: "'If' 이항 식의 첫 번째 피연산자는 nullable이거나 참조 형식이어야 합니다."
ms.date: 07/20/2015
f1_keywords:
- bc33107
- vbc33107
helpviewer_keywords:
- BC33107
ms.assetid: 493c8899-3f6b-4471-8eb6-9284e8492768
ms.openlocfilehash: 4b520949cb59b63ea39441632dc5e2c6d000d711
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249528"
---
# <a name="first-operand-in-a-binary-if-expression-must-be-nullable-or-a-reference-type"></a>'If' 이항 식의 첫 번째 피연산자는 nullable이거나 참조 형식이어야 합니다.
식은 `If` 두 개 또는 세 개의 인수를 취할 수 있습니다. 두 개의 인수만 보낼 때 첫 번째 인수는 참조 형식 또는 nullable 값 형식이어야 합니다. 첫 번째 인수가 `Nothing`이외의 다른 것으로 평가되면 해당 값이 반환됩니다. 첫 번째 인수가 `Nothing`을 평가하는 경우 두 번째 인수가 평가되고 반환됩니다.  
  
 예를 들어 다음 코드에는 `If` 두 개의 식이 포함되는데 하나는 세 개의 인수와 두 개의 인수가 있는 식입니다. 식은 동일한 값을 계산하고 반환합니다.  
  
```vb  
' firstChoice is a nullable value type.  
Dim firstChoice? As Integer = Nothing  
Dim secondChoice As Integer = 1128  
' If expression with three arguments.  
Console.WriteLine(If(firstChoice IsNot Nothing, firstChoice, secondChoice))  
' If expression with two arguments.  
Console.WriteLine(If(firstChoice, secondChoice))  
```  
  
 다음 식으로 인해 이 오류가 발생합니다.  
  
```vb  
Dim choice1 = 4  
Dim choice2 = 5  
Dim booleanVar = True  
  
' Not valid.  
'Console.WriteLine(If(choice1 < choice2, 1))  
' Not valid.  
'Console.WriteLine(If(booleanVar, "Test returns True."))  
```  
  
 **오류 ID:** BC33107  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- 첫 번째 인수가 nullable 값 형식 또는 참조 형식이 되도록 코드를 변경할 수 `If` 없는 경우 3인수 식 또는 `If...Then...Else` 문으로 변환하는 것이 좋습니다.  
  
```vb  
Console.WriteLine(If(choice1 < choice2, 1, 2))  
Console.WriteLine(If(booleanVar, "Test returns True.", "Test returns False."))  
```  
  
## <a name="see-also"></a>참조

- [If 연산자](../../../visual-basic/language-reference/operators/if-operator.md)
- [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Nullable 값 형식](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
