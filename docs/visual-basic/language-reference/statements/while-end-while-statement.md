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
ms.openlocfilehash: 00ca0ad24231128b25a988921386d6bd3265e9a0
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58843713"
---
# <a name="whileend-while-statement-visual-basic"></a>While...End While 문(Visual Basic)
지정된 된 조건과 일련의 문 실행 `True`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
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
|`condition`|필수 요소. `Boolean` 식입니다. 하는 경우 `condition` 됩니다 `Nothing`, Visual Basic로 처리 `False`합니다.|  
|`statements`|선택 사항입니다. 하나 이상의 문 다음 `While`는 실행 될 때마다 `condition` 는 `True`합니다.|  
|`Continue While`|선택 사항입니다. 다음 반복으로 제어를 전송 합니다 `While` 블록입니다.|  
|`Exit While`|선택 사항입니다. 밖으로 제어를 전송 합니다 `While` 블록입니다.|  
|`End While`|필수 요소. `While` 블록의 정의를 종료합니다.|  
  
## <a name="remarks"></a>설명  
 사용 된 `While...End While` 조건이으로 문을 횟수 무한히 반복 하려는 경우 구조체 `True`. 조건을 테스트 하는 위치 또는 결과 항목을 사용 하 여 더 많은 유연성이 것을 선호할 수에 대 한 테스트 하려는 경우는 [수행 하는 중... 문이 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md)합니다. 문을 횟수 만큼 반복 하려는 경우는 [에 대 한 중... 다음 문을](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 것이 좋습니다.  
  
> [!NOTE]
>  `While` 키워드에도 사용 되는 [수행 하는 중... 문이 루프](../../../visual-basic/language-reference/statements/do-loop-statement.md)는 [Skip While 절](../../../visual-basic/language-reference/queries/skip-while-clause.md) 하며 [Take While 절](../../../visual-basic/language-reference/queries/take-while-clause.md)합니다.  
  
 경우 `condition` 됩니다 `True`모든의 `statements` 될 때까지 실행을 `End While` 문이. 제어를 반환 합니다는 `While` 문 및 `condition` 를 다시 확인 합니다. 하는 경우 `condition` 여전히 `True`, 프로세스를 반복 합니다. 있을 경우 `False`, 제어가 전달 뒤에 오는 문에 `End While` 문.  
  
 `While` 문은 항상 루프를 시작 하기 전에 조건을 확인 합니다. 조건이 동안 계속 반복 `True`합니다. 하는 경우 `condition` 는 `False` 루프를 처음 입력할 때 실행 되는 한 번도 합니다.  
  
 합니다 `condition` 일반적으로 두 값의 비교 결과로 계산 되는 식일 수는 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`). 이 식은에 변환 된 숫자 형식과 같은 다른 데이터 형식의 값을 포함할 수 있습니다 `Boolean`합니다.  
  
 중첩할 수 있습니다 `While` 루프 내에서 다른 한 루프를 배치 하 여 합니다. 또한 다른 종류의 내부에 다른 제어 구조를 중첩할 수 있습니다. 자세한 내용은 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.  
  
## <a name="exit-while"></a>종료 하는 동안  
 합니다 [종료 하는 동안](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 종료 하는 또 다른 방법은 제공할 수는 `While` 루프입니다. `Exit While` 바로 뒤에 오는 문으로 제어를 전송 합니다 `End While` 문입니다.  
  
 일반적으로 사용 `Exit While` 상황에서 계산 된 후 (예는 `If...Then...Else` 구조). 불필요 하거나 잘못 된 값 또는 종료 요청과 같은 반복을 계속할 수 있도록 하는 조건이 발견 되 면 루프를 종료 하려는 경우. 사용할 수 있습니다 `Exit While` 일으킬 수 있는 조건을 테스트 하는 경우는 *무한 루프*, 매우 큰 또는 무한도 가능 횟수에 실행 될 수 있는 루프는 합니다. 사용할 수 있습니다 `Exit While` 루프를 이스케이프 합니다.  
  
 개수에 관계 없이 배치할 수 있습니다 `Exit While` 어디서 나 문에서 `While` 루프입니다.  
  
 사용 하는 경우 내에 중첩 `While` 루프 `Exit While` 다음 상위 수준의 중첩 및 가장 안쪽의 루프 밖으로 제어를 전송 합니다.  
  
 `Continue While` 문 루프의 다음 반복으로 즉시 제어를 전송 합니다. 자세한 내용은 [Continue 문은](../../../visual-basic/language-reference/statements/continue-statement.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 루프에서 문을 계속 실행 될 때까지 `index` 변수 10 보다 큽니다.  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a>예제  
 다음 예제를 사용 합니다 `Continue While` 및 `Exit While` 문입니다.  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 텍스트 파일에 모든 줄을 읽습니다. <xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 반환을 <xref:System.IO.StreamReader> 문자를 읽고 있는 합니다. 에 `While` 조건을 <xref:System.IO.StreamReader.Peek%2A> 메서드의 `StreamReader` 파일에 추가 문자가 포함 되어 있는지 여부를 결정 합니다.  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a>참고자료

- [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)
- [Continue 문](../../../visual-basic/language-reference/statements/continue-statement.md)
