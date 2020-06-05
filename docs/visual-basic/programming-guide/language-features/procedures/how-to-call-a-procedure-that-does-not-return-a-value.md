---
title: '방법: 값을 반환하지 않는 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
ms.assetid: 259b49a3-a3c1-4254-ba8c-73cdc4127703
ms.openlocfilehash: 514d6e576b9b782387840ae04dcefa00de876aa9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84388740"
---
# <a name="how-to-call-a-procedure-that-does-not-return-a-value-visual-basic"></a>방법: 값을 반환하지 않는 프로시저 호출(Visual Basic)
`Sub`프로시저는 호출 코드에 값을 반환 하지 않습니다. 독립형 호출 문을 사용 하 여 명시적으로 호출 합니다. 식 내에서 이름을 사용 하 여 호출할 수 없습니다.  
  
### <a name="to-call-a-sub-procedure"></a>Sub 프로시저를 호출 하려면  
  
1. 프로시저의 이름을 지정 `Sub` 합니다.  
  
2. 프로시저 이름에 괄호를 추가 하 여 인수 목록을 묶습니다. 인수가 없으면 선택적으로 괄호를 생략할 수 있습니다. 그러나 괄호를 사용 하면 코드를 더 쉽게 읽을 수 있습니다.  
  
3. 인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다. 프로시저에서 해당 하는 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 `Sub` 합니다.  
  
     다음 예제에서는 Visual Basic 함수를 호출 <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A> 하 여 응용 프로그램 창을 활성화 합니다. <xref:Microsoft.VisualBasic.Interaction.AppActivate%2A>창 제목을 유일한 인수로 사용 합니다. 호출 코드에 값을 반환 하지 않습니다. 메모장 프로세스가 실행 되 고 있지 않으면이 예제는을 throw <xref:System.ArgumentException> 합니다. `Shell` 절차에서는 애플리케이션을 지정 된 경로 가정 합니다.  
  
     [!code-vb[VbVbalrCatRef#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrCatRef/VB/Class1.vb#11)]  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.Interaction.Shell%2A>
- <xref:System.ArgumentException>
- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Sub 문](../../../language-reference/statements/sub-statement.md)
- [방법: 프로시저 만들기](./how-to-create-a-procedure.md)
- [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
- [방법: Visual Basic에서 이벤트 처리기 호출](./how-to-call-an-event-handler.md)
