---
description: '자세한 정보: Visual Basic에서 이벤트 처리기를 호출 하는 방법'
title: 이벤트 처리기를 호출 하는 방법
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
no-loc:
- WithEvents
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 7e65b36d392211be533bb4881658b1cdb8057d5d
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476256"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>Visual Basic에서 이벤트 처리기를 호출 하는 방법

*이벤트* 는 일부 프로그램 구성 요소에서 인식 하 고 응답 하는 코드를 작성할 수 있는 마우스 클릭 또는 신용 한도 초과와 같은 작업 또는 발생입니다. 이벤트 *처리기* 는 이벤트에 응답 하기 위해 작성 하는 코드입니다.

Visual Basic 이벤트 처리기는 `Sub` 프로시저입니다. 그러나 일반적으로 다른 프로시저와 동일한 방식으로 호출 하지는 않습니다 `Sub` . 대신 프로시저를 이벤트 처리기로 식별 합니다. [`Handles`](../../../language-reference/statements/handles-clause.md)절과 [`WithEvents`](../../../language-reference/modifiers/withevents.md) 변수를 사용 하거나 [AddHandler 문을](../../../language-reference/statements/addhandler-statement.md)사용 하 여이 작업을 수행할 수 있습니다. `Handles`Visual Basic에서 이벤트 처리기를 선언 하는 기본 방법은 절을 사용 하는 것입니다. IDE (통합 개발 환경)에서 프로그래밍할 때 디자이너에서 이벤트 처리기를 작성 하는 방법입니다. `AddHandler`문은 런타임에 이벤트를 동적으로 발생 시키는 데 적합 합니다.

이벤트가 발생할 때 Visual Basic는 이벤트 처리기 프로시저를 자동으로 호출 합니다. 이벤트에 액세스할 수 있는 모든 코드는 [RaiseEvent 문을](../../../language-reference/statements/raiseevent-statement.md)실행 하 여 발생 시킬 수 있습니다.

둘 이상의 이벤트 처리기를 동일한 이벤트와 연결할 수 있습니다. 경우에 따라 이벤트에서 처리기를 분리할 수 있습니다. 자세한 내용은 [이벤트](../events/index.md)를 참조하세요.

## <a name="call-an-event-handler-using-no-loc-texthandles-and-withevents"></a>및를 사용 하 여 이벤트 처리기 호출 :::no-loc text="Handles":::WithEvents

1. 이벤트가 [이벤트 문으로](../../../language-reference/statements/event-statement.md)선언 되었는지 확인 합니다.

2. 키워드를 사용 하 여 모듈 또는 클래스 수준에서 개체 변수를 선언 [`WithEvents`](../../../language-reference/modifiers/withevents.md) 합니다. `As`이 변수에 대 한 절은 이벤트를 발생 시키는 클래스를 지정 해야 합니다.

3. 이벤트 처리 프로시저 선언에서 `Sub` [`Handles`](../../../language-reference/statements/handles-clause.md) 변수와 이벤트 이름을 지정 하는 절을 추가 합니다 `WithEvents` .

4. 이벤트가 발생할 때 Visual Basic는 프로시저를 자동으로 호출 `Sub` 합니다. 코드에서 문을 사용 하 여 이벤트를 발생 시킬 수 있습니다 `RaiseEvent` .

    다음 예제에서는 이벤트를 정의 하 고 `WithEvents` 이벤트를 발생 시키는 클래스를 참조 하는 변수를 정의 합니다. 이벤트 처리 프로시저는 `Sub` 절을 사용 하 여 처리 하는 `Handles` 클래스 및 이벤트를 지정 합니다.

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="4":::

## <a name="call-an-event-handler-using-addhandler"></a>AddHandler를 사용 하 여 이벤트 처리기 호출

1. 이벤트가 문으로 선언 되었는지 확인 `Event` 합니다.

2. 이벤트 처리 프로시저를 이벤트와 동적으로 연결 하려면 [AddHandler 문을](../../../language-reference/statements/addhandler-statement.md) 실행 `Sub` 합니다.

3. 이벤트가 발생할 때 Visual Basic는 프로시저를 자동으로 호출 `Sub` 합니다. 코드에서 문을 사용 하 여 이벤트를 발생 시킬 수 있습니다 `RaiseEvent` .

    다음 예에서는 생성자에서 [AddHandler 문을](../../../language-reference/statements/addhandler-statement.md) 사용 하 여 `OnFormClosing` 프로시저를에 대 한 이벤트 처리기와 연결 합니다 <xref:System.Windows.Forms.Form.FormClosing> .

    :::code language="vb" source="snippets/how-to-call-an-event-handler/SpecialForm.vb" id="5":::

    [RemoveHandler 문을](../../../language-reference/statements/removehandler-statement.md)실행 하 여 이벤트에서 이벤트 처리기를 분리할 수 있습니다.

## <a name="see-also"></a>추가 정보

- [절차](index.md)
- [하위 프로시저](sub-procedures.md)
- [Sub 문](../../../language-reference/statements/sub-statement.md)
- [AddressOf 연산자](../../../language-reference/operators/addressof-operator.md)
- [방법: 프로시저 만들기](how-to-create-a-procedure.md)
- [방법: 값을 반환하지 않는 프로시저 호출](how-to-call-a-procedure-that-does-not-return-a-value.md)
