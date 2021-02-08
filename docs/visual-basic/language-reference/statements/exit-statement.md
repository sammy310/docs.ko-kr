---
description: '자세한 정보: Exit 문 (Visual Basic)'
title: Exit 문
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
ms.openlocfilehash: 54af7fbf908dbad829cf6f08bf442dfe85e35610
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769129"
---
# <a name="exit-statement-visual-basic"></a>Exit 문 (Visual Basic)

프로시저 또는 블록을 종료 하 고 프로시저 호출 또는 블록 정의 다음에 오는 문으로 제어를 즉시 전달 합니다.

## <a name="syntax"></a>Syntax

```vb
Exit { Do | For | Function | Property | Select | Sub | Try | While }
```

## <a name="statements"></a>문

 `Exit Do`  
 표시 되는 루프를 즉시 종료 `Do` 합니다. 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `Loop` . `Exit Do` 루프 내 에서만 사용할 수 있습니다 `Do` . 중첩 된 루프 내에서 사용 되는 경우 `Do` `Exit Do` 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.

 `Exit For`  
 표시 되는 루프를 즉시 종료 `For` 합니다. 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `Next` . `Exit For` ... `For` `Next` 또는 `For Each` ... `Next` 루프 내 에서만 사용할 수 있습니다. 중첩 된 루프 내에서 사용 되는 경우 `For` `Exit For` 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.

 `Exit Function`  
 표시 되는 프로시저를 즉시 종료 `Function` 합니다. 프로시저를 호출한 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `Function` . `Exit Function` 프로시저 내 에서만 사용할 수 있습니다 `Function` .

 반환 값을 지정 하기 위해 문 앞의 줄에서 함수 이름에 값을 할당할 수 있습니다 `Exit Function` . 반환 값을 할당 하 고 한 문에서 함수를 종료 하려면 [Return 문을](return-statement.md)대신 사용할 수 있습니다.

 `Exit Property`  
 표시 되는 프로시저를 즉시 종료 `Property` 합니다. 프로시저를 호출한 문 즉 `Property` , 속성의 값을 요청 하거나 설정 하는 문을 사용 하 여 실행이 계속 됩니다. `Exit Property` 속성의 또는 프로시저 내 에서만 사용할 수 `Get` 있습니다 `Set` .

 프로시저에서 반환 값을 지정 하려면 `Get` 문 앞의 줄에서 함수 이름에 값을 할당할 수 있습니다 `Exit Property` . 반환 값을 할당 하 고 `Get` 한 문에서 프로시저를 종료 하려면 문을 대신 사용할 수 있습니다 `Return` .

 프로시저에서 `Set` `Exit Property` 문은 문과 동일 합니다 `Return` .

 `Exit Select`  
 표시 되는 블록을 즉시 종료 `Select Case` 합니다. 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `End Select` . `Exit Select` 문 내 에서만 사용할 수 있습니다 `Select Case` .

 `Exit Sub`  
 표시 되는 프로시저를 즉시 종료 `Sub` 합니다. 프로시저를 호출한 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `Sub` . `Exit Sub` 프로시저 내 에서만 사용할 수 있습니다 `Sub` .

 프로시저에서 `Sub` `Exit Sub` 문은 문과 동일 합니다 `Return` .

 `Exit Try`  
 `Try`가 표시 되는 또는 블록을 즉시 종료 `Catch` 합니다. 블록 (있는 `Finally` 경우) 또는 문 뒤의 문이 있는 경우 실행이 계속 됩니다 `End Try` . `Exit Try` 는 `Try` `Catch` 블록 내부가 아니라 또는 블록 내부 에서만 사용할 수 있습니다 `Finally` .

 `Exit While`  
 표시 되는 루프를 즉시 종료 `While` 합니다. 문 다음에 오는 문을 사용 하 여 실행이 계속 됩니다 `End While` . `Exit While` 루프 내 에서만 사용할 수 있습니다 `While` . 중첩 된 루프 내에서 사용 되는 경우이 발생 하는 `While` `Exit While` 루프 위에 중첩 된 한 수준으로 제어를 전달 `Exit While` 합니다.

## <a name="remarks"></a>설명

문을 문과 혼동 하지 마십시오 `Exit` `End` . `Exit` 는 문의 끝을 정의 하지 않습니다.

## <a name="example"></a>예제

다음 예제에서 루프 조건은 `index` 변수가 100 보다 큰 경우 루프를 중지 합니다. `If`그러나 루프의 문은 `Exit Do` 인덱스 변수가 10 보다 클 경우 문이 루프를 중지 하도록 합니다.

[!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]

## <a name="example"></a>예제

다음 예에서는 함수 이름에 반환 값을 할당 한 `myFunction` 다음를 사용 하 여 `Exit Function` 함수에서를 반환 합니다.

[!code-vb[VbVbalrStatements#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#23)]

## <a name="example"></a>예제

다음 예에서는 [Return 문을](return-statement.md) 사용 하 여 반환 값을 할당 하 고 함수를 종료 합니다.

[!code-vb[VbVbalrStatements#24](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#24)]

## <a name="see-also"></a>참고 항목

- [Continue 문](continue-statement.md)
- [Do...Loop 문](do-loop-statement.md)
- [End 문](end-statement.md)
- [For Each...Next 문](for-each-next-statement.md)
- [For...Next 문](for-next-statement.md)
- [Function 문](function-statement.md)
- [Return 문](return-statement.md)
- [Stop 문](stop-statement.md)
- [Sub 문](sub-statement.md)
- [Try...Catch...Finally 문](try-catch-finally-statement.md)
