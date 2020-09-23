---
title: '방법: 속성 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- Visual Basic code, properties
- procedures [Visual Basic], calling
- properties [Visual Basic], property procedures
- procedure calls [Visual Basic], property procedures
ms.assetid: 96bc4d74-d9c3-4b7a-954d-58ac8553cd94
ms.openlocfilehash: 0b35751136937d4cee5b3ca9669b43d3fbdf71a1
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071954"
---
# <a name="how-to-call-a-property-procedure-visual-basic"></a>방법: 속성 프로시저 호출(Visual Basic)

속성에 값을 저장 하거나 값을 검색 하 여 속성 프로시저를 호출 합니다. 변수에 액세스 하는 것과 동일한 방식으로 속성에 액세스 합니다.  
  
 속성의 `Set` 프로시저는 값을 저장 하 고 해당 `Get` 프로시저는 값을 검색 합니다. 그러나 이러한 프로시저를 이름으로 명시적으로 호출 하지는 않습니다. 변수 값을 저장 하거나 검색 하는 것 처럼 대입문 또는 식에서 속성을 사용 합니다. Visual Basic은 속성의 프로시저에 대 한 호출을 수행 합니다.  
  
### <a name="to-call-a-propertys-get-procedure"></a>속성의 Get 프로시저를 호출 하려면  
  
1. 변수 이름을 사용 하는 것과 동일한 방식으로 식에 속성 이름을 사용 합니다. 변수나 상수를 사용할 수 있는 모든 위치에서 속성을 사용할 수 있습니다.  
  
     또는  
  
     대입문에 등호 () 기호를 사용 하 여 속성 이름을 사용 `=` 합니다.  
  
     다음 예제에서는 <xref:Microsoft.VisualBasic.DateAndTime.Now%2A> 해당 프로시저를 암시적으로 호출 하 여 속성의 값을 읽습니다 `Get` .  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. 속성이 인수를 사용 하는 경우 속성 이름에 괄호를 추가 하 여 인수 목록을 묶습니다. 인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.  
  
3. 인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다. 속성이 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.  
  
 속성의 값은 변수 또는 상수와 마찬가지로 식에 참여 하거나 대입문의 왼쪽에 있는 변수나 속성에 저장 됩니다.  
  
### <a name="to-call-a-propertys-set-procedure"></a>속성의 Set 프로시저를 호출 하려면  
  
1. 대입문의 왼쪽에 속성 이름을 사용 합니다.  
  
     다음 예에서는 <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A> 프로시저를 암시적으로 호출 하 여 속성의 값을 설정 합니다 `Set` .  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. 속성이 인수를 사용 하는 경우 속성 이름에 괄호를 추가 하 여 인수 목록을 묶습니다. 인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.  
  
3. 인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다. 속성이 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.  
  
 대입문의 오른쪽에 생성 된 값은 속성에 저장 됩니다.  
  
## <a name="see-also"></a>참조

- [속성 프로시저](./property-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)
- [방법: 속성 만들기](./how-to-create-a-property.md)
- [방법: 액세스 수준이 혼합된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)
- [방법: Visual Basic에서 기본 속성 선언 및 호출](./how-to-declare-and-call-a-default-property.md)
- [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)
- [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)
- [Get 문](../../../language-reference/statements/get-statement.md)
- [Set 문](../../../language-reference/statements/set-statement.md)
