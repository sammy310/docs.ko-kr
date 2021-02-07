---
description: '자세히 알아보기: Resume 문'
title: Resume 문
ms.date: 07/20/2015
f1_keywords:
- vb.Resume
- vb.ResumeNext
helpviewer_keywords:
- Next statement [Visual Basic], Resume
- Resume Next statement [Visual Basic]
- execution [Visual Basic], resuming
- run-time errors [Visual Basic], resuming after
- Resume statement [Visual Basic], syntax
- errors [Visual Basic], resuming after
- Error statement [Visual Basic], and Resume statement
- execution
- Resume statement [Visual Basic]
ms.assetid: e24d058b-1a5c-4274-acb9-7d295d3ea537
ms.openlocfilehash: fd3a02fc2606355d7e3a34f5c0d69eef577809de
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741187"
---
# <a name="resume-statement"></a>Resume 문

오류 처리 루틴이 완료 된 후 실행을 다시 시작 합니다.  
  
 구조화 되지 않은 예외 처리 및 및 문을 사용 하는 대신 가능한 경우 코드에서 구조적 예외 처리를 사용 하는 것이 좋습니다 `On Error` `Resume` . 자세한 내용은 [Try...Catch...Finally 문](try-catch-finally-statement.md)을 참조하세요.  
  
## <a name="syntax"></a>Syntax  
  
```vb  
Resume [ Next | line ]  
```  
  
## <a name="parts"></a>부분  

 `Resume`  
 필수 사항입니다. 오류 처리기와 동일한 프로시저에서 오류가 발생 한 경우 오류를 발생 시킨 문으로 실행이 다시 시작 됩니다. 호출 된 프로시저에서 오류가 발생 한 경우 오류 처리 루틴을 포함 하는 프로시저에서 마지막으로 호출한 문에서 실행이 다시 시작 됩니다.  
  
 `Next`  
 선택 사항입니다. 오류 처리기와 동일한 프로시저에서 오류가 발생 한 경우 오류가 발생 한 문 바로 다음에 오는 문으로 실행이 다시 시작 됩니다. 호출 된 프로시저에서 오류가 발생 한 경우 오류 처리 루틴 (문)을 포함 하는 프로시저에서 마지막으로 호출한 문 바로 다음 문으로 실행이 다시 시작 `On Error Resume Next` 됩니다.  
  
 `line`  
 선택 사항입니다. 필수 인수에 지정 된 줄에서 실행이 다시 시작 `line` 됩니다. `line`인수는 줄 레이블 또는 줄 번호 이며 오류 처리기와 같은 프로시저에 있어야 합니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
> 구조화 되지 않은 예외 처리 및 및 문을 사용 하는 대신 가능한 경우 코드에서 구조적 예외 처리를 사용 하는 것이 좋습니다 `On Error` `Resume` . 자세한 내용은 [Try...Catch...Finally 문](try-catch-finally-statement.md)을 참조하세요.  
  
 `Resume`오류 처리 루틴이 아닌 다른 위치에서 문을 사용 하는 경우 오류가 발생 합니다.  
  
 문은 `Resume` 문을 포함 하는 프로시저에서 사용할 수 없습니다 `Try...Catch...Finally` .  
  
## <a name="example"></a>예제  

 이 예에서는 문을 사용 하 여 `Resume` 프로시저에서 오류 처리를 종료 한 다음 오류를 발생 시킨 문으로 실행을 다시 시작 합니다. 문 사용을 보여 주기 위해 55 오류 번호가 생성 됩니다 `Resume` .  
  
 [!code-vb[VbVbalrErrorHandling#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrErrorHandling/VB/Class1.vb#16)]  
  
## <a name="requirements"></a>요구 사항  

 **네임 스페이스:** [microsoft.visualbasic](../runtime-library-members.md)  
  
 **어셈블리:** Visual Basic 런타임 라이브러리 (Microsoft.VisualBasic.dll)  
  
## <a name="see-also"></a>참고 항목

- [Try...Catch...Finally 문](try-catch-finally-statement.md)
- [Error 문](error-statement.md)
- [On Error 문](on-error-statement.md)
