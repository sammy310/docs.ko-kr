---
description: '자세한 정보: End <keyword> 문 (Visual Basic)'
title: End <keyword> 문
ms.date: 07/20/2015
f1_keywords:
- vb.EndDefinition
helpviewer_keywords:
- End keyword [Visual Basic]
ms.assetid: 42d6e088-ab0f-4cda-88e8-fdce3e5fcf4f
ms.openlocfilehash: ba21d4ba68a054d77d4f29307d49ed8e82bb6b50
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769197"
---
# <a name="end-keyword-statement-visual-basic"></a>End \<keyword> 문(Visual Basic)

추가 키워드가 뒤에 나오면는 해당 키워드에 의해 도입 된 문 블록의 정의를 종료 합니다.

## <a name="syntax"></a>Syntax

```vb
End AddHandler
End Class
End Enum
End Event
End Function
End Get
End If
End Interface
End Module
End Namespace
End Operator
End Property
End RaiseEvent  
End RemoveHandler  
End Select
End Set
End Structure
End Sub
End SyncLock
End Try
End While
End With  
```  
  
## <a name="parts"></a>부분

|파트|설명|
|---|---|
|`End`|필수 사항입니다. 프로그래밍 요소의 정의를 종료 합니다.|
|`AddHandler`|`AddHandler` `AddHandler` 사용자 지정 [이벤트 문에서](event-statement.md)일치 하는 문에 의해 시작 된 접근자를 종료 하는 데 필요 합니다.|
|`Class`|일치 하는 [Class 문에](class-statement.md)의해 시작 된 클래스 정의를 종료 하는 데 필요 합니다.|
|`Enum`|일치 하는 [열거형 문에](enum-statement.md)의해 시작 된 열거형 정의를 종료 하는 데 필요 합니다.|
|`Event`|`Custom`일치 하는 [이벤트 문에서](event-statement.md)시작한 이벤트 정의를 종료 하는 데 필요 합니다.|  
|`Function`|일치 하는 `Function` [함수 문에](function-statement.md)의해 시작 된 프로시저 정의를 종료 하는 데 필요 합니다. 실행 시 문이 발견 `End Function` 되 면 컨트롤이 호출 코드로 반환 됩니다.|
|`Get`|`Property`일치 하는 [Get 문에](get-statement.md)의해 시작 된 프로시저 정의를 종료 하는 데 필요 합니다. 실행 시 문이 발생 하면 `End Get` 속성 값을 요청 하는 문으로 제어가 반환 됩니다.|
|`If`|을 (를) 종료 `If` 하는 `Then` 데 필요 합니다. ...`Else` 일치 하는 문에 의해 시작 된 블록 정의 `If` 입니다. 다음 [을 참조 하세요. 그런 다음 ... Else 문](if-then-else-statement.md).|
|`Interface`|일치 하는 [인터페이스 문에](interface-statement.md)의해 시작 된 인터페이스 정의를 종료 하는 데 필요 합니다.|
|`Module`|일치 하는 [Module 문에](module-statement.md)의해 시작 된 모듈 정의를 종료 하는 데 필요 합니다.|
|`Namespace`|일치 하는 [네임 스페이스 문에](namespace-statement.md)의해 시작 된 네임 스페이스 정의를 종료 하는 데 필요 합니다.|
|`Operator`|일치 하는 [Operator 문에](operator-statement.md)의해 시작 된 연산자 정의를 종료 하는 데 필요 합니다.|
|`Property`|일치 하는 [속성 문에](property-statement.md)의해 시작 된 속성 정의를 종료 하는 데 필요 합니다.|
|`RaiseEvent`|`RaiseEvent` `RaiseEvent` 사용자 지정 [이벤트 문에서](event-statement.md)일치 하는 문에 의해 시작 된 접근자를 종료 하는 데 필요 합니다.|
|`RemoveHandler`|`RemoveHandler` `RemoveHandler` 사용자 지정 [이벤트 문에서](event-statement.md)일치 하는 문에 의해 시작 된 접근자를 종료 하는 데 필요 합니다.|
|`Select`|일치 하는 `Select` `Case` 문에 의해 시작 된 ... 블록 정의를 종료 하는 데 필요 합니다. `Select` Select ...를 참조 하세요. [ Case 문](select-case-statement.md).  
|`Set`|일치 하는 `Property` [Set 문에](set-statement.md)의해 시작 된 프로시저 정의를 종료 하는 데 필요 합니다. 실행 시 문이 발생 하면 `End Set` 컨트롤에서 속성 값을 설정 하는 문으로 돌아갑니다.  
|`Structure`|일치 하는 [Structure 문에](structure-statement.md)의해 시작 된 구조 정의를 종료 하는 데 필요 합니다.  
|`Sub`|일치 하는 `Sub` [Sub 문에](sub-statement.md)의해 시작 된 프로시저 정의를 종료 하는 데 필요 합니다. 실행 시 문이 발견 `End Sub` 되 면 컨트롤이 호출 코드로 반환 됩니다.  
|`SyncLock`|일치 하는 문에 의해 시작 된 블록 정의를 종료 하는 데 필요 `SyncLock` `SyncLock` 합니다. [SyncLock 문](synclock-statement.md)을 참조 하세요.  
|`Try`|을 (를) 종료 `Try` 하는 `Catch` 데 필요 합니다. ...`Finally` 일치 하는 문에 의해 시작 된 블록 정의 `Try` 입니다. [Try ... Catch ... Finally 문](try-catch-finally-statement.md).  
|`While`|일치 하는 문에 의해 시작 된 루프 정의를 종료 하는 데 필요 `While` `While` 합니다. 잠시 보기 ... [ End While 문](while-end-while-statement.md)입니다.  
|`With`| 일치 하는 문에 의해 시작 된 블록 정의를 종료 하는 데 필요 `With` `With` 합니다. 다음 [으로 보기 ... End With 문](with-end-with-statement.md)  
|||
  
## <a name="directives"></a>지시문

숫자 기호 () 뒤에 오는 `#` `End` 키워드는 해당 지시문에 의해 도입 된 전처리 블록을 종료 합니다.  

```vb
#End ExternalSource
#End If
#End Region
```

|파트|설명|
|---|---|
|`#End`|필수 사항입니다. 전처리 블록의 정의를 종료 합니다.|
|`ExternalSource`|일치 하는 [#ExternalSource 지시문](../directives/externalsource-directive.md)에 의해 시작 되는 외부 소스 블록을 종료 하는 데 필요 합니다.|
|`If`|일치 하는 지시문에 의해 시작 된 조건부 컴파일 블록을 종료 하는 데 필요 `#If` 합니다. #If를 참조 하세요. [ Then ... #Else 지시문](../directives/if-then-else-directives.md).|
|`Region`|일치 하는 [#Region 지시문](../directives/region-directive.md)에 의해 시작 된 소스 영역 블록을 종료 하는 데 필요 합니다.|
|||

## <a name="remarks"></a>설명

[End 문은](end-statement.md)추가 키워드가 없으면 실행을 즉시 종료 합니다.

## <a name="smart-device-developer-notes"></a>스마트 디바이스 개발자 노트  

`End`추가 키워드가 없는 문은 지원 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목

- [End 문](end-statement.md)
