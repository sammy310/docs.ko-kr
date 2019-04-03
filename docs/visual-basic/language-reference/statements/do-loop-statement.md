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
ms.openlocfilehash: 3ff3d67f38f510b798da3e470de066cff1e98f29
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58826043"
---
# <a name="doloop-statement-visual-basic"></a>Do...Loop 문(Visual Basic)
반복 하는 동안 문 블록을 한 `Boolean` 조건은 `True` 조건이 있을 때까지 또는 `True`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
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
|`Do`|필수 요소. 정의의 시작을 `Do` 루프입니다.|  
|`While`|`Until`를 사용하는 경우를 제외하고는 필수입니다. 될 때까지 루프 반복 `condition` 는 `False`합니다.|  
|`Until`|`While`를 사용하는 경우를 제외하고는 필수입니다. 될 때까지 루프 반복 `condition` 는 `True`합니다.|  
|`condition`|선택 사항입니다. `Boolean` 식입니다. 하는 경우 `condition` 됩니다 `Nothing`, Visual Basic로 처리 `False`합니다.|  
|`statements`|선택 사항입니다. While 또는 until 반복 되는 하나 이상의 문을 `condition` 는 `True`합니다.|  
|`Continue Do`|선택 사항입니다. 다음 반복으로 제어를 전송 합니다 `Do` 루프입니다.|  
|`Exit Do`|선택 사항입니다. 밖으로 제어를 전송 합니다 `Do` 루프입니다.|  
|`Loop`|필수 요소. 정의 종료 합니다 `Do` 루프입니다.|  
  
## <a name="remarks"></a>설명  
 사용 하 여를 `Do...Loop` 무한히 횟수: 조건이 충족 될 때까지 문 집합을 반복 하려는 경우 구조체입니다. 문을 횟수 만큼 반복 하려는 경우는 [에 대 한 중... 다음 문을](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 것이 좋습니다.  
  
 사용할 수 있습니다 `While` 또는 `Until` 되도록 `condition`, 하지만 둘 다.  
  
 테스트할 수 있습니다 `condition` 시작 또는 루프의 끝에만 한 번입니다. 테스트 하는 경우 `condition` 루프의 시작 부분에 (에 `Do` 문), 루프도 한 번 실행 되지 않을 수 있습니다. 루프의 끝에 테스트 하는 경우 (에 `Loop` 문), 루프는 항상 한 번 이상 실행 합니다.  
  
 계산 되는 식일 수 있지만 조건 두 값의 비교에서 일반적으로 결과 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`). 여기에 값을 변환 된 숫자 형식과 같은 다른 데이터 형식의 `Boolean`합니다.  
  
 중첩할 수 있습니다 `Do` 루프 내에서 다른 한 루프를 배치 하 여 합니다. 또한 다른 종류의 서로 다른 제어 구조를 중첩할 수 있습니다. 자세한 내용은 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.  
  
> [!NOTE]
>  합니다 `Do...Loop` 구조 보다 더 많은 유연성을 제공 합니다 [하는 동안... End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 루프를 종료 여부를 결정할 수 있기 때문에 때 `condition` 더 이상 `True` 되거나 조건이 먼저 `True`합니다. 테스트할 수도 있습니다 `condition` 루프의 끝 또는 시작 합니다.  
  
## <a name="exit-do"></a>종료 안 함  
 합니다 [종료 수행](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 종료 하는 대체 방법을 제공할 수는 `Do…Loop`합니다. `Exit Do` 바로 뒤에 오는 문으로 제어를 전송 합니다 `Loop` 문입니다.  
  
 `Exit Do` 예를 몇 가지 조건을 계산 된 후에 자주 사용 됩니다는 `If...Then...Else` 구조입니다. 불필요 하거나 잘못 된 값 또는 종료 요청과 같은 반복을 계속할 수 있도록 하는 조건이 발견 되 면 루프를 종료 하려는 경우. 용도 중 하나 `Exit Do` 일으킬 수 있는 조건을 테스트 하는 *무한 루프*도 무한히 여러 번 실행 될 수 있는 루프는. 사용할 수 있습니다 `Exit Do` 루프를 이스케이프 합니다.  
  
 개수에 관계 없이 포함할 수 있습니다 `Exit Do` 어디서 나 문에서 `Do…Loop`합니다.  
  
 사용 하는 경우 내에 중첩 `Do` 루프 `Exit Do` 다음 상위 수준의 중첩 및 가장 안쪽의 루프 밖으로 제어를 전송 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 루프에서 문을 계속 실행 될 때까지 `index` 변수 10 보다 큽니다. `Until` 루프의 끝에 절이 있습니다.  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a>예제  
 다음 예에서는 `While` 절 대신는 `Until` 절 및 `condition` 끝 대신 루프의 시작 부분에서 테스트 합니다.  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a>예제  
 다음 예에서 `condition` 루프를 중지 때는 `index` 변수가 100을 초과 합니다. 그러나 `If` 루프에서 문을 사용 하면는 `Exit Do` 문의 인덱스 변수는 10 보다 큰 경우에 루프를 중지 합니다.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 텍스트 파일에 모든 줄을 읽습니다. <xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 반환을 <xref:System.IO.StreamReader> 문자를 읽고 있는 합니다. 에 `Do...Loop` 조건을 <xref:System.IO.StreamReader.Peek%2A> 메서드는 `StreamReader` 추가 문자가 있는지 여부를 결정 합니다.  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a>참고자료

- [루프 구조](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [Exit 문](../../../visual-basic/language-reference/statements/exit-statement.md)
- [While...End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
