---
title: Do...Loop 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: eff5239e07ca27f40ece5af68f46c491be91cf09
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583438"
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop 문(Visual Basic)
@No__t_0 조건이 `True` 되거나 조건이 `True` 상태가 될 때까지 문 블록을 반복 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`Do`|필수 요소. @No__t_0 루프의 정의를 시작 합니다.|  
|`While`|`Until`를 사용하는 경우를 제외하고는 필수입니다. @No__t_0 `False` 될 때까지 루프를 반복 합니다.|  
|`Until`|`While`를 사용하는 경우를 제외하고는 필수입니다. @No__t_0 `True` 될 때까지 루프를 반복 합니다.|  
|`condition`|(선택 사항) `Boolean` 식입니다. @No__t_0 `Nothing` 경우 Visual Basic는이를 `False`로 처리 합니다.|  
|`statements`|(선택 사항) 또는 `True` `condition` 될 때까지 반복 되는 하나 이상의 문입니다.|  
|`Continue Do`|(선택 사항) @No__t_0 루프의 다음 반복으로 제어를 전달 합니다.|  
|`Exit Do`|(선택 사항) @No__t_0 루프에서 제어를 전달 합니다.|  
|`Loop`|필수 요소. @No__t_0 루프의 정의를 종료 합니다.|  
  
## <a name="remarks"></a>주의  
 조건을 만족할 때까지 문 집합을 무한 횟수로 반복 하려는 경우 `Do...Loop` 구조를 사용 합니다. 이 문을 설정 된 횟수 만큼 반복 하려면 [For ... 다음 문을](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 선택 하는 것이 좋습니다.  
  
 @No__t_0 또는 `Until`를 사용 하 여 `condition`를 지정할 수 있지만 둘 다 지정할 수는 없습니다.  
  
 루프의 시작 또는 끝에서 한 번만 `condition` 테스트할 수 있습니다. 루프의 시작 부분에서 `condition`를 테스트 하는 경우 (`Do` 문에서) 루프가 한 번도 실행 되지 않을 수 있습니다. 루프의 끝 부분에서 테스트 하는 경우 (`Loop` 문에서) 루프는 항상 한 번 이상 실행 됩니다.  
  
 이 조건은 일반적으로 두 값을 비교 하 여 발생 하지만 [부울 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`)으로 계산 되는 모든 식일 수 있습니다. 여기에는 `Boolean`로 변환 된 숫자 형식과 같은 다른 데이터 형식의 값이 포함 됩니다.  
  
 루프 하나를 다른 루프에 배치 하 여 `Do` 루프를 중첩할 수 있습니다. 서로 다른 종류의 제어 구조를 중첩할 수도 있습니다. 자세한 내용은 [중첩 컨트롤 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.  
  
> [!NOTE]
> @No__t_0 구조를 사용 하면 보다 유연성이 향상 됩니다 [. End While 문을](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 사용 하면 `condition` `True` 중지 될 때 또는 처음 `True` 될 때 루프를 종료할 것인지 여부를 결정할 수 있습니다. 또한 루프의 시작 또는 끝 부분에서 `condition` 테스트할 수 있습니다.  
  
## <a name="exit-do"></a>종료  
 [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) 문은 `Do…Loop`를 종료 하는 다른 방법을 제공할 수 있습니다. `Exit Do`는 `Loop` 문 다음에 오는 문으로 제어를 즉시 전송 합니다.  
  
 `Exit Do`는 일부 조건이 계산 된 후 (예: `If...Then...Else` 구조체) 사용 됩니다. 오류가 발생 하거나 종료 요청 등의 반복을 계속할 수 없게 하는 조건을 감지 하는 경우 루프를 종료할 수 있습니다. @No__t_0 사용 하는 한 가지 방법은 무한 하거나 무한 한 횟수를 실행할 수 있는 루프 인 *무한 루프*를 발생 시킬 수 있는 조건을 테스트 하는 것입니다. @No__t_0를 사용 하 여 루프를 이스케이프할 수 있습니다.  
  
 @No__t_1 어디에 든 원하는 수의 `Exit Do` 문을 포함할 수 있습니다.  
  
 중첩 된 `Do` 루프 내에서 사용 하는 경우 `Exit Do`는 가장 안쪽의 루프와 그 다음으로 높은 중첩 수준으로 제어를 전송 합니다.  
  
## <a name="example"></a>예제  
 다음 예에서는 `index` 변수가 10 보다 클 때까지 루프의 문이 계속 실행 됩니다. @No__t_0 절은 루프의 끝에 있습니다.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Until` 절 대신 `While` 절을 사용 하 고 `condition`는 끝이 아닌 루프의 시작 부분에서 테스트 됩니다.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>예제  
 다음 예제에서 `condition` `index` 변수가 100 보다 큰 경우 루프를 중지 합니다. 그러나 루프의 `If` 문은 인덱스 변수가 10 보다 클 때 `Exit Do` 문이 루프를 중지 하도록 합니다.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>예제  
 다음 예에서는 텍스트 파일의 모든 줄을 읽습니다. @No__t_0 메서드는 파일을 열고 문자를 읽는 <xref:System.IO.StreamReader>을 반환 합니다. @No__t_0 조건에서 `StreamReader`의 <xref:System.IO.StreamReader.Peek%2A> 메서드는 추가 문자가 있는지 여부를 확인 합니다.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>참조

- [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)
- [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
