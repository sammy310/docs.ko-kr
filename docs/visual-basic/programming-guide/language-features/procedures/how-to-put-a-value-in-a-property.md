---
title: '방법: 속성 값 입력'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: c39401e5-b5fc-4439-8f31-ed640f7ce6ed
ms.openlocfilehash: ad0d0e81f94dd3dead50f21c3bd6ff580c004dd6
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346049"
---
# <a name="how-to-put-a-value-in-a-property-visual-basic"></a>방법: 속성 값 입력(Visual Basic)
속성 이름을 대입문의 왼쪽에 배치 하 여 속성에 값을 저장 합니다.  
  
 속성의 `Set` 프로시저는 값을 저장 하지만 이름으로 명시적으로 호출 하지 않습니다. 변수를 사용 하는 것 처럼 속성을 사용 합니다. Visual Basic은 속성의 프로시저에 대 한 호출을 수행 합니다.  
  
### <a name="to-store-a-value-in-a-property"></a>속성에 값을 저장 하려면  
  
1. 대입문의 왼쪽에 속성 이름을 사용 합니다.  
  
     다음 예에서는 Visual Basic `TimeOfDay` 속성의 값을 정오로 설정 하 고 암시적으로 해당 `Set` 프로시저를 호출 합니다.  
  
     [!code-vb[VbVbcnProcedures#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#11)]  
  
2. 속성이 인수를 사용 하는 경우 속성 이름에 괄호를 추가 하 여 인수 목록을 묶습니다. 인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.  
  
3. 인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다. 속성이 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.  
  
4. 대입문의 오른쪽에 생성 된 값은 속성에 저장 됩니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualBasic.DateAndTime.TimeOfDay%2A>
- [속성 프로시저](./property-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)
- [방법: 속성 만들기](./how-to-create-a-property.md)
- [방법: 액세스 수준이 혼합된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)
- [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)
- [방법: Visual Basic에서 기본 속성 선언 및 호출](./how-to-declare-and-call-a-default-property.md)
- [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)
