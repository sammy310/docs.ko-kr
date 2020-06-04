---
title: Select...Case 문
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: 3dedd43f920b493a0aca9ce48460b00815e1af5c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404241"
---
# <a name="selectcase-statement-visual-basic"></a>Select...Case 문(Visual Basic)
식의 값에 따라 여러 문 그룹 중 하나를 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a>부분  
  
|용어|정의|  
|---|---|  
|`testexpression`|필수 요소. 식 는 기본 데이터 형식 (,,,,,,,,,,,,,, `Boolean` `Byte` `Char` `Date` `Double` `Decimal` `Integer` `Long` `Object` `SByte` `Short` `Single` `String` `UInteger` `ULong` 및 `UShort` ) 중 하나로 계산 되어야 합니다.|  
|`expressionlist`|`Case`문에 필요 합니다. 에 대해 일치 하는 값을 나타내는 식 절의 목록입니다 `testexpression` . 여러 식 절은 쉼표로 구분 됩니다. 각 절은 다음 형식 중 하나를 사용할 수 있습니다.<br /><br /> -   *expression1* `To` *식 2*<br />-[ `Is` ] *comparisonoperator.equals* *식*<br />-   *expression*<br /><br /> 키워드를 사용 `To` 하 여에 대 한 일치 값 범위의 경계를 지정 `testexpression` 합니다. 값은 `expression1` 의 값 보다 작거나 같아야 합니다 `expression2` .<br /><br /> `Is`비교 연산자 (,,,, 또는)와 함께 키워드를 사용 `=` `<>` 하 여 `<` `<=` `>` `>=` 에 대 한 일치 값에 대 한 제한을 지정 `testexpression` 합니다. 키워드를 `Is` 제공 하지 않으면 *comparisonoperator.equals*앞에 자동으로 삽입 됩니다.<br /><br /> 만 지정 하는 폼은 `expression` `Is` *comparisonoperator.equals* 가 등호 () 인 특수 한 경우로 취급 됩니다 `=` . 이 폼은로 평가 됩니다 `testexpression`  =  `expression` .<br /><br /> 의 식은 `expressionlist` 의 형식으로 암시적으로 변환 가능 하 고 해당가 사용 되는 `testexpression` `comparisonoperator` 두 가지 형식에 적합 한 경우의 모든 데이터 형식일 수 있습니다.|  
|`statements`|선택 사항입니다. `Case`가 `testexpression` 에서 절과 일치 하는 경우이 실행 되는 하나 이상의 문입니다 `expressionlist` .|  
|`elsestatements`|선택 사항입니다. `Case Else`가 문의에 있는 절과 일치 하지 않는 경우 실행 되는 다음 문이 하나 이상 `testexpression` `expressionlist` `Case` 있습니다.|  
|`End Select`|... 생성의 정의를 종료 합니다. `Select` `Case`|  
  
## <a name="remarks"></a>설명  
 `testexpression`가 절과 일치 하면 `Case` `expressionlist` 해당 문 다음에 오는 문이 `Case` 다음 `Case` , `Case Else` 또는 `End Select` 문으로 실행 됩니다. 그런 다음 제어가 다음 문으로 전달 `End Select` 됩니다. 가 둘 `testexpression` `expressionlist` 이상의 절에 있는 절과 일치 하면 `Case` 첫 번째 일치 항목 다음에 오는 문만 실행 됩니다.  
  
 `Case Else`문은 `elsestatements` `testexpression` 다른 문의와 절 사이에 일치 하는 항목이 없는 경우 실행할를 소개 하는 데 사용 됩니다 `expressionlist` `Case` . 반드시 필요한 것은 아니지만 생성에 문을 포함 하 여 예측할 수 없는 값을 처리 하는 것이 좋습니다 `Case Else` `Select Case` `testexpression` . 일치 하 `Case` `expressionlist` 는 절 `testexpression` 이 없고 문이 없으면 `Case Else` 다음 문으로 제어가 전달 됩니다 `End Select` .  
  
 각 절에서 여러 식이나 범위를 사용할 수 있습니다 `Case` . 예를 들어 다음 줄은 유효 합니다.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> `Is`및 문에 사용 되는 키워드는 `Case` `Case Else` 개체 참조 비교에 사용 되는 [is 연산자](../operators/is-operator.md)와 동일 하지 않습니다.  
  
 문자 문자열에 대해 범위와 여러 식을 지정할 수 있습니다. 다음 예에서는 `Case` "사과"와 정확히 같은 문자열을 검색 하 고, "너트"와 "수프" 사이의 값을 알파벳 순서로 포함 하거나,의 현재 값과 정확히 같은 값을 포함 합니다 `testItem` .  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 의 설정은 `Option Compare` 문자열 비교에 영향을 줄 수 있습니다. 에서 `Option Compare Text` "사과" 및 "사과" 문자열은 동일한 것으로 간주 되지만 `Option Compare Binary` 에서는 그렇지 않습니다.  
  
> [!NOTE]
> `Case`여러 절이 있는 문은 단락 이라는 동작을 나타낼 *short-circuiting*수 있습니다. Visual Basic는 절을 왼쪽에서 오른쪽으로 계산 하 고, 일치 하는을 생성 하는 경우 `testexpression` 나머지 절은 계산 되지 않습니다. 단락을 통해 성능을 향상 시킬 수 있지만의 모든 식이 계산 될 것으로 예상 되는 경우 예기치 않은 결과가 발생할 수 있습니다 `expressionlist` . 단락에 대 한 자세한 내용은 [부울 식](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md)을 참조 하세요.  
  
 `Case`또는 문 블록 내의 코드에서 `Case Else` 블록의 문을 더 이상 실행할 필요가 없는 경우 문을 사용 하 여 블록을 종료할 수 있습니다 `Exit Select` . 그러면 다음 문으로 제어가 즉시 전송 `End Select` 됩니다.  
  
 `Select Case`구조는 중첩 될 수 있습니다. 중첩 된 각 `Select Case` 생성에는 일치 하는 문이 있어야 `End Select` 하며 중첩 된 `Case` `Case Else` 외부 생성의 단일 또는 문 블록 내에 완전히 포함 되어야 합니다 `Select Case` .  
  
## <a name="example"></a>예제  
 다음 예에서는 생성을 사용 하 여 `Select Case` 변수 값에 해당 하는 줄을 작성 합니다 `number` . 두 번째 `Case` 문에는의 현재 값과 일치 하는 값이 포함 되어 `number` 있으므로 "Between 6 ~ 8" (포함)를 쓰는 문이 실행 됩니다.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End 문](end-statement.md)
- [If...Then...Else 문](if-then-else-statement.md)
- [Option Compare 문](option-compare-statement.md)
- [Exit 문](exit-statement.md)
