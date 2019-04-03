---
title: Exit 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Exit
helpviewer_keywords:
- execution [Visual Basic], ending
- files [Visual Basic], closing
- programs [Visual Basic], quitting
- code, exiting
- Exit statement [Visual Basic]
- program termination
- execution [Visual Basic], stopping
ms.assetid: 760bfb32-5c3f-4bdb-a432-9a6001c92db7
ms.openlocfilehash: 1f386694bd7425ee530b9305ab684b730f9b73c8
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58832634"
---
# <a name="exit-statement-visual-basic"></a>Exit 문(Visual Basic)
프로시저 또는 블록을 종료 하 고 프로시저 호출 또는 블록 정의 다음 문으로 제어를 즉시 전달 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Exit { Do | For | Function | Property | Select | Sub | Try | While }  
```  
  
## <a name="statements"></a>문  
 `Exit Do`  
 즉시 종료는 `Do` 루프 나타나는 것입니다. 다음 문으로 계속 실행 합니다 `Loop` 문입니다. `Exit Do` 내 에서만 사용할 수는 `Do` 루프입니다. 사용 하는 경우 내에 중첩 `Do` 루프 `Exit Do` 가장 안쪽의 루프를 끝내 고 다음 더 높은 수준의 중첩 컨트롤을 이동 합니다.  
  
 `Exit For`  
 즉시 종료는 `For` 루프 나타나는 것입니다. 다음 문으로 계속 실행 합니다 `Next` 문입니다. `Exit For` 내 에서만 사용할 수는 `For`... `Next` 또는 `For Each`... `Next` 루프입니다. 사용 하는 경우 내에 중첩 `For` 루프 `Exit For` 가장 안쪽의 루프를 끝내 고 다음 더 높은 수준의 중첩 컨트롤을 이동 합니다.  
  
 `Exit Function`  
 즉시 끝내는 `Function` 나타나는 프로시저. 문 다음에 호출한 문으로 실행이 계속 되는 `Function` 프로시저입니다. `Exit Function` 내 에서만 사용할 수는 `Function` 프로시저입니다.  
  
 반환 값을 지정 하려면 앞에 줄에 함수 이름에 값을 할당할 수는 `Exit Function` 문입니다. 반환 값을 할당 하 고 하나의 문에서 함수 종료를 대신 사용할 수 있습니다 합니다 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md)합니다.  
  
 `Exit Property`  
 즉시 끝내는 `Property` 나타나는 프로시저. 호출한 문으로 실행이 계속 됩니다는 `Property` 프로시저, 즉,을 요청 하거나 설정 속성의 값을 사용 하 여 합니다. `Exit Property` 속성의 내 에서만 사용할 수 있습니다 `Get` 또는 `Set` 프로시저입니다.  
  
 반환 값을 지정 하는 `Get` 프로시저, 함수 이름 앞에 줄에서 값을 할당할 수 있습니다는 `Exit Property` 문입니다. 반환 값 및 종료를 할당 하는 `Get` 하나의 문에서 프로시저를 대신 사용할 수 있습니다는 `Return` 문.  
  
 에 `Set` 프로시저는 `Exit Property` 문과 동일는 `Return` 문.  
  
 `Exit Select`  
 즉시 끝내는 `Select Case` 나타나는 것을 차단 합니다. 다음 문으로 계속 실행 합니다 `End Select` 문입니다. `Exit Select` 내 에서만 사용할 수는 `Select Case` 문입니다.  
  
 `Exit Sub`  
 즉시 끝내는 `Sub` 나타나는 프로시저. 문 다음에 호출한 문으로 실행이 계속 되는 `Sub` 프로시저입니다. `Exit Sub` 내 에서만 사용할 수는 `Sub` 프로시저입니다.  
  
 에 `Sub` 프로시저는 `Exit Sub` 문과 동일는 `Return` 문.  
  
 `Exit Try`  
 즉시 종료 합니다 `Try` 또는 `Catch` 나타나는 것을 차단 합니다. 실행이 계속 됩니다는 `Finally` 하나, 없는 경우 또는 다음 문으로 차단를 `End Try` 문. `Exit Try` 내 에서만 사용할 수는 `Try` 또는 `Catch` 블록 내부가 아니라는 `Finally` 블록입니다.  
  
 `Exit While`  
 즉시 종료는 `While` 루프 나타나는 것입니다. 다음 문으로 계속 실행 합니다 `End While` 문입니다. `Exit While` 내 에서만 사용할 수는 `While` 루프입니다. 사용 하는 경우 내에 중첩 `While` 루프 `Exit While` 중첩된 수준이 하나 위 루프는 루프에 제어를 전송 위치 `Exit While` 발생 합니다.  
  
## <a name="remarks"></a>설명  
 혼동 하지 마십시오 `Exit` 문을 사용 하 여 `End` 문입니다. `Exit` 문의 끝을 정의 하지 않습니다.  
  
## <a name="example"></a>예제  
 루프 조건에서 다음 예제에서는 루프를 중지 때는 `index` 변수가 100을 초과 합니다. 그러나 `If` 루프에서 문을 사용 하면는 `Exit Do` 문의 인덱스 변수는 10 보다 큰 경우에 루프를 중지 합니다.  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 함수 이름에 반환 값을 할당 `myFunction`를 사용 하 여 `Exit Function` 함수에서 반환 합니다.  
  
 [!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]  
  
## <a name="example"></a>예제  
 다음 예제에서는 합니다 [Return 문이](../../../visual-basic/language-reference/statements/return-statement.md) 반환 값을 할당 하 여 함수를 종료 합니다.  
  
 [!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]  
  
## <a name="see-also"></a>참고자료

- [Continue 문](../../../visual-basic/language-reference/statements/continue-statement.md)
- [Do...Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [End 문](../../../visual-basic/language-reference/statements/end-statement.md)
- [For Each...Next 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next 문](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Function 문](../../../visual-basic/language-reference/statements/function-statement.md)
- [Return 문](../../../visual-basic/language-reference/statements/return-statement.md)
- [Stop 문](../../../visual-basic/language-reference/statements/stop-statement.md)
- [Sub 문](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Try...Catch...Finally 문](../../../visual-basic/language-reference/statements/try-catch-finally-statement.md)
