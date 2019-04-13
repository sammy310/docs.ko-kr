---
title: '방법: Visual Basic의 이벤트 처리기를 호출 합니다.'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- event handlers [Visual Basic], calling
- event handlers
- procedures [Visual Basic], event handlers
- procedures [Visual Basic], calling
ms.assetid: 72e18ef8-144e-40df-a1f4-066a57271e28
ms.openlocfilehash: 3690d1c2eb8ece9059b8b25b5a14bef2021bc8f6
ms.sourcegitcommit: 558d78d2a68acd4c95ef23231c8b4e4c7bac3902
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2019
ms.locfileid: "59320173"
---
# <a name="how-to-call-an-event-handler-in-visual-basic"></a>방법: Visual Basic의 이벤트 처리기를 호출 합니다.
*이벤트* 작업 또는 항목은-같은 마우스 클릭 이나 신용 한도 초과-응답 코드를 작성할 수 있는 한 일부 프로그램 구성 요소에 의해 인식 합니다. *이벤트 처리기* 이벤트에 응답을 작성 하는 코드입니다.  
  
 Visual Basic의 이벤트 처리기는는 `Sub` 프로시저입니다. 그러나 호출 하지 않으면 일반적으로 동일한 방식으로 다른 `Sub` 프로시저입니다. 대신, 이벤트 처리기로 프로시저를 식별 합니다. 이렇게 하려면 사용 하 여는 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 절 및 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 변수를 또는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md)합니다. 사용 하는 `Handles` 절은 Visual Basic의 이벤트 처리기를 선언 하는 기본 방법입니다. 이 방법은 이벤트 처리기는 통합된 개발 환경 (IDE)에서 프로그래밍할 때 디자이너에서 기록 됩니다. `AddHandler` 문을 런타임에 동적으로 이벤트를 발생 시키기에 적합 합니다.  
  
 이벤트가 발생할 때 Visual Basic에서는 이벤트 처리기 프로시저를 자동으로 호출 합니다. 이벤트에 대 한 액세스 권한이 있는 모든 코드를 사용 하면 실행 하 여 발생 하는 [RaiseEvent 문](../../../../visual-basic/language-reference/statements/raiseevent-statement.md)합니다.  
  
 동일한 이벤트를 사용 하 여 둘 이상의 이벤트 처리기를 연결할 수 있습니다. 경우에 따라 이벤트에서 처리기를 분리할 수 있습니다. 자세한 내용은 [이벤트](../../../../visual-basic/programming-guide/language-features/events/index.md)를 참조하세요.  
  
### <a name="to-call-an-event-handler-using-handles-and-withevents"></a>WithEvents 및 처리를 사용 하 여 이벤트 처리기를 호출 합니다.  
  
1. 이벤트가 사용 하 여 선언 해야는 [이벤트 연결 문으로](../../../../visual-basic/language-reference/statements/event-statement.md)합니다.  
  
2. 수준에서 사용 하 여 모듈 또는 클래스에서 개체 변수를 선언 합니다 [WithEvents](../../../../visual-basic/language-reference/modifiers/withevents.md) 키워드입니다. `As` 절이이 변수에 대 한 이벤트를 발생 시키는 클래스를 지정 해야 합니다.  
  
3. 이벤트 처리의 선언에 `Sub` 프로시저를 추가 [처리](../../../../visual-basic/language-reference/statements/handles-clause.md) 지정 하는 절을 `WithEvents` 이벤트 이름과 변수입니다.  
  
4. Visual Basic 자동으로 호출 이벤트가 발생할 때를 `Sub` 프로시저입니다. 코드에서 사용할 수는 `RaiseEvent` 문을 이벤트를 발생 합니다.  
  
     다음 예제에서는 이벤트를 정의 및 `WithEvents` 이벤트를 발생 시키는 클래스를 참조 하는 변수입니다. 이벤트 처리 `Sub` 프로시저는 `Handles` 절 클래스와 처리 하는 이벤트를 지정 합니다.  
  
     [!code-vb[VbVbcnProcedures#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#4)]  
  
### <a name="to-call-an-event-handler-using-addhandler"></a>AddHandler를 사용 하 여 이벤트 처리기를 호출 합니다.  
  
1. 이벤트가 사용 하 여 선언 해야는 `Event` 문입니다.  
  
2. 실행 프로그램 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 이벤트 처리를 동적으로 연결할 `Sub` 이벤트를 사용 하 여 프로시저입니다.  
  
3. Visual Basic 자동으로 호출 이벤트가 발생할 때를 `Sub` 프로시저입니다. 코드에서 사용할 수는 `RaiseEvent` 문을 이벤트를 발생 합니다.  
  
     다음 예제에서는 정의 `Sub` 처리 하는 절차는 <xref:System.Windows.Forms.Form.Closing> 폼의 이벤트입니다. 사용 하 여는 [AddHandler 문](../../../../visual-basic/language-reference/statements/addhandler-statement.md) 연결 하는 `catchClose` 에 대 한 이벤트 처리기로 프로시저 <xref:System.Windows.Forms.Form.Closing>합니다.  
  
     [!code-vb[VbVbcnProcedures#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#5)]  
  
     실행 하 여 이벤트에서 이벤트 처리기를 분리할 수 있습니다 합니다 [RemoveHandler 문](../../../../visual-basic/language-reference/statements/removehandler-statement.md)합니다.  
  
## <a name="see-also"></a>참고자료

- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [Sub 문](../../../../visual-basic/language-reference/statements/sub-statement.md)
- [AddressOf 연산자](../../../../visual-basic/language-reference/operators/addressof-operator.md)
- [방법: 프로시저 만들기](./how-to-create-a-procedure.md)
- [방법: 값을 반환하지 않는 프로시저 호출](./how-to-call-a-procedure-that-does-not-return-a-value.md)
