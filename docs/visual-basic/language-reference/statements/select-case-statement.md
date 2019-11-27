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
ms.openlocfilehash: 4dddfe5fbf7092c911291ffc6841e76f8c2748e9
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352824"
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
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`testexpression`|필수 요소. 식. 는 기본 데이터 형식 (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`) 중 하나로 계산 되어야 합니다.`ULong``UShort`|  
|`expressionlist`|`Case` 문에 필요 합니다. `testexpression`에 대해 일치 하는 값을 나타내는 식 절의 목록입니다. 여러 식 절은 쉼표로 구분 됩니다. 각 절은 다음 형식 중 하나를 사용할 수 있습니다.<br /><br /> -   *expression1* `To` *식 2*<br />-[`Is`] *comparisonoperator.equals* *식*<br />-   *식*<br /><br /> `To` 키워드를 사용 하 여 `testexpression`에 대 한 일치 값 범위의 경계를 지정 합니다. `expression1` 값은 `expression2`값 보다 작거나 같아야 합니다.<br /><br /> 비교 연산자 (`=`, `<>`, `<`, `<=`, `>`또는 `>=`)와 함께 `Is` 키워드를 사용 하 여 `testexpression`에 대 한 일치 값에 대 한 제한을 지정 합니다. `Is` 키워드를 제공 하지 않으면 *comparisonoperator.equals*앞에 자동으로 삽입 됩니다.<br /><br /> `expression`만 지정 하는 양식은 `Is` 형식의 특수 한 경우로 처리 됩니다. 여기서 *comparisonoperator.equals* 는 등호 (`=`)입니다. 이 양식은 `expression` = `testexpression`으로 평가 됩니다.<br /><br /> `expressionlist`의 식은 모든 데이터 형식일 수 있습니다 .이 경우에는 `testexpression` 형식으로 암시적으로 변환할 수 있고 적절 한 `comparisonoperator`는 사용 되는 두 형식에 유효 합니다.|  
|`statements`|선택 사항입니다. `testexpression`에서 `expressionlist`절과 일치 하는 경우 실행 되는 `Case` 다음 문이 하나 이상 있습니다.|  
|`elsestatements`|선택 사항입니다. `testexpression` `Case Else` 뒤에 나오는 하나 이상의 문은 `Case` 문의 `expressionlist`에 있는 절과 일치 하지 않는 경우에 실행 됩니다.|  
|`End Select`|`Select`...`Case` 생성의 정의를 종료 합니다.|  
  
## <a name="remarks"></a>설명  
 `testexpression` `Case` `expressionlist` 절과 일치 하는 경우 해당 `Case` 문을 따라 오는 문은 다음 `Case`, `Case Else`또는 `End Select` 문으로 실행 됩니다. 그런 다음 `End Select`다음 문으로 제어가 전달 됩니다. `testexpression` 둘 이상의 `Case` 절에서 `expressionlist` 절과 일치 하는 경우 첫 번째 일치 항목 다음에 오는 문만 실행 됩니다.  
  
 `Case Else` 문은 다른 `Case` 문의 `testexpression`와 `expressionlist` 절 사이에 일치 하는 항목이 없는 경우 실행할 `elsestatements`를 소개 하는 데 사용 됩니다. 필수는 아니지만 `Select Case` 생성에 `Case Else` 문을 생성 하 여 예측할 수 없는 `testexpression` 값을 처리 하는 것이 좋습니다. `testexpression`와 일치 하는 `Case` `expressionlist` 절이 없는 경우 `Case Else` 문이 없으면 `End Select`다음 문으로 제어가 전달 됩니다.  
  
 각 `Case` 절에서 여러 식이나 범위를 사용할 수 있습니다. 예를 들어 다음 줄은 유효 합니다.  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> `Case` 및 `Case Else` 문에 사용 되는 `Is` 키워드는 개체 참조 비교에 사용 되는 [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)와 동일 하지 않습니다.  
  
 문자 문자열에 대해 범위와 여러 식을 지정할 수 있습니다. 다음 예에서는 "사과"와 정확 하 게 일치 하는 문자열을 `Case` 하 고, "너트"와 "수프" 사이의 값을 알파벳 순서로 포함 하거나, `testItem`의 현재 값과 정확히 같은 값을 포함 합니다.  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 `Option Compare` 설정은 문자열 비교에 영향을 줄 수 있습니다. `Option Compare Text`에서 "사과" 및 "사과" 문자열은 동일 하 게 비교 되지만 `Option Compare Binary`는 그렇지 않습니다.  
  
> [!NOTE]
> 여러 절이 있는 `Case` *문은 단락 이라는*동작을 나타낼 수 있습니다. Visual Basic는 절을 왼쪽에서 오른쪽으로 계산 하 고, `testexpression`와 일치 하는 항목을 생성 하는 경우 나머지 절은 계산 되지 않습니다. 단기는 성능을 향상 시킬 수 있지만 `expressionlist`의 모든 식이 계산 될 것으로 예상 되는 경우 예기치 않은 결과를 생성할 수 있습니다. 단락에 대 한 자세한 내용은 [부울 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)을 참조 하세요.  
  
 `Case` 또는 `Case Else` 문 블록 내의 코드에서 블록의 문을 더 이상 실행할 필요가 없는 경우 `Exit Select` 문을 사용 하 여 블록을 종료할 수 있습니다. 그러면 `End Select`다음에 오는 문으로 제어가 즉시 전송 됩니다.  
  
 `Select Case` 구문은 중첩 될 수 있습니다. 중첩 된 각 `Select Case` 구문은 일치 하는 `End Select` 문을 포함 해야 하며 중첩 된 외부 `Select Case` 생성의 단일 `Case` 또는 `Case Else` 문 블록 내에 완전히 포함 되어야 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `Select Case` 생성을 사용 하 여 `number`변수 값에 해당 하는 줄을 작성 합니다. 두 번째 `Case` 문에는 `number`의 현재 값과 일치 하는 값이 포함 되어 있으므로 "Between 6 ~ 8" (포함)를 쓰는 문이 실행 됩니다.  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [End 문](../../../visual-basic/language-reference/statements/end-statement.md)
- [If...Then...Else 문](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [Option Compare 문](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)
