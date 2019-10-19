---
title: While...End While 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: 5da05835998b2e9ef9aeefe5b00faf9e1ecb9ce2
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582267"
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While 문(Visual Basic)
지정 된 조건이 `True` 된 경우 일련의 문을 실행 합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a>요소  
  
|용어|정의|  
|---|---|  
|`condition`|필수 요소. `Boolean` 식입니다. @No__t_0 `Nothing` 경우 Visual Basic는이를 `False`로 처리 합니다.|  
|`statements`|(선택 사항) @No__t_0 다음에 오는 하나 이상의 문 `condition` `True` 때마다 실행 됩니다.|  
|`Continue While`|(선택 사항) @No__t_0 블록의 다음 반복으로 제어를 전달 합니다.|  
|`Exit While`|(선택 사항) @No__t_0 블록 밖으로 제어를 전송 합니다.|  
|`End While`|필수 요소. `While` 블록의 정의를 종료합니다.|  
  
## <a name="remarks"></a>주의  
 조건이 `True` 상태로 유지 되는 한 문 집합을 무한 횟수로 반복 하려는 경우 `While...End While` 구조를 사용 합니다. 조건을 테스트 하는 위치 또는 테스트 결과를 보다 유연 하 게 하려는 경우 다음을 수행 하는 것이 좋습니다. [ Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md). 이 문을 설정 된 횟수 만큼 반복 하려면 [For ... 다음 문을](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 선택 하는 것이 좋습니다.  
  
> [!NOTE]
> @No__t_0 키워드는 다음에도 사용 됩니다 [. Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md), [Skip while 절](../../../visual-basic/language-reference/queries/skip-while-clause.md) 및 [Take while 절](../../../visual-basic/language-reference/queries/take-while-clause.md)  
  
 @No__t_0 `True` 되는 경우 `End While` 문이 발생할 때까지 모든 `statements` 실행 됩니다. 그러면 컨트롤이 `While` 문으로 반환 되 고 `condition`가 다시 선택 됩니다. @No__t_0 아직 `True` 되 면 프로세스가 반복 됩니다. @No__t_0 경우 `End While` 문 다음에 오는 문으로 제어가 전달 됩니다.  
  
 @No__t_0 문은 루프를 시작 하기 전에 항상 조건을 확인 합니다. 조건이 `True` 상태로 유지 되는 동안 반복이 계속 됩니다. 루프를 처음 입력할 때 `condition` `False` 경우 한 번도 실행 되지 않습니다.  
  
 @No__t_0은 일반적으로 두 값을 비교 하 여 발생 하지만 [부울 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`)으로 계산 되는 모든 식일 수 있습니다. 이 식에는 `Boolean`로 변환 된 숫자 형식과 같은 다른 데이터 형식의 값이 포함 될 수 있습니다.  
  
 루프 하나를 다른 루프에 배치 하 여 `While` 루프를 중첩할 수 있습니다. 서로 다른 종류의 제어 구조를 중첩할 수도 있습니다. 자세한 내용은 [중첩 컨트롤 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.  
  
## <a name="exit-while"></a>종료 중  
 [Exit While](../../../visual-basic/language-reference/statements/exit-statement.md) 문은 `While` 루프를 종료 하는 다른 방법을 제공할 수 있습니다. `Exit While`은 `End While` 문 다음에 오는 문으로 제어를 즉시 전송 합니다.  
  
 일반적으로 일부 조건을 평가한 후에 `Exit While`를 사용 합니다 (예: `If...Then...Else` 구조체). 오류가 발생 하거나 종료 요청 등의 반복을 계속할 수 없게 하는 조건을 감지 하는 경우 루프를 종료할 수 있습니다. *무한 루프*를 발생 시킬 수 있는 조건에 대해 테스트 하는 경우 `Exit While`를 사용할 수 있습니다 .이 루프는 매우 크거나 무한 한 횟수를 실행할 수 있습니다. 그런 다음 `Exit While`를 사용 하 여 루프를 이스케이프할 수 있습니다.  
  
 @No__t_1 루프의 어디에 든 원하는 수의 `Exit While` 문을 넣을 수 있습니다.  
  
 중첩 된 `While` 루프 내에서 사용 하는 경우 `Exit While`는 가장 안쪽의 루프와 그 다음으로 높은 중첩 수준으로 제어를 전송 합니다.  
  
 @No__t_0 문은 즉시 루프의 다음 반복으로 제어를 전달 합니다. 자세한 내용은 [Continue 문](../../../visual-basic/language-reference/statements/continue-statement.md)을 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 예에서는 `index` 변수가 10 보다 클 때까지 루프의 문이 계속 실행 됩니다.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>예제  
 다음 예에서는 `Continue While` 및 `Exit While` 문을 사용 하는 방법을 보여 줍니다.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>예제  
 다음 예에서는 텍스트 파일의 모든 줄을 읽습니다. @No__t_0 메서드는 파일을 열고 문자를 읽는 <xref:System.IO.StreamReader>을 반환 합니다. @No__t_0 조건에서 `StreamReader`의 <xref:System.IO.StreamReader.Peek%2A> 메서드는 파일에 추가 문자가 포함 되어 있는지 여부를 확인 합니다.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>참조

- [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Continue 문](../../../visual-basic/language-reference/statements/continue-statement.md)
