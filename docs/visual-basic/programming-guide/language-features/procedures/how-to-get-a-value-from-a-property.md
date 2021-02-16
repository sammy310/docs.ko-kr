---
description: '자세한 정보: 방법: 속성에서 값 가져오기 (Visual Basic)'
title: '방법: 속성에서 값 가져오기'
ms.date: 07/20/2015
helpviewer_keywords:
- property values [Visual Basic]
- Visual Basic code, procedures
- values [Visual Basic], properties
- Visual Basic code, properties
- properties [Visual Basic], values
ms.assetid: 3954423e-6ab7-4a4c-b55c-a8d27be47891
ms.openlocfilehash: 5626ad1a248c3bb51e0f80076628c8108e424186
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427598"
---
# <a name="how-to-get-a-value-from-a-property-visual-basic"></a>방법: 속성에서 값 가져오기(Visual Basic)

식에 속성 이름을 포함 하 여 속성의 값을 검색 합니다.  
  
 속성의 `Get` 프로시저에서 값을 검색 하지만 이름으로 명시적으로 호출 하지 않습니다. 변수를 사용 하는 것 처럼 속성을 사용 합니다. Visual Basic은 속성의 프로시저에 대 한 호출을 수행 합니다.  
  
### <a name="to-retrieve-a-value-from-a-property"></a>속성에서 값을 검색 하려면  
  
1. 변수 이름을 사용 하는 것과 동일한 방식으로 식에 속성 이름을 사용 합니다. 변수나 상수를 사용할 수 있는 모든 위치에서 속성을 사용할 수 있습니다.  
  
     또는  
  
     대입문에 등호 () 기호를 사용 하 여 속성 이름을 사용 `=` 합니다.  
  
     다음 예제에서는 `Now` 해당 프로시저를 암시적으로 호출 하 여 Visual Basic 속성의 값을 읽습니다 `Get` .  
  
     [!code-vb[VbVbalrDateProperties#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDateProperties/VB/Module1.vb#4)]  
  
2. 속성이 인수를 사용 하는 경우 속성 이름에 괄호를 추가 하 여 인수 목록을 묶습니다. 인수가 없으면 선택적으로 괄호를 생략할 수 있습니다.  
  
3. 인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다. 속성이 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.  
  
 속성의 값은 변수 또는 상수와 마찬가지로 식에 참여 하거나 대입문의 왼쪽에 있는 변수나 속성에 저장 됩니다.  
  
## <a name="see-also"></a>추가 정보

- [절차](./index.md)
- [속성 프로시저](./property-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Property Statement](../../../language-reference/statements/property-statement.md)
- [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)
- [방법: 속성 만들기](./how-to-create-a-property.md)
- [방법: 액세스 수준이 혼합된 속성 선언](./how-to-declare-a-property-with-mixed-access-levels.md)
- [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)
- [방법: Visual Basic에서 기본 속성 선언 및 호출](./how-to-declare-and-call-a-default-property.md)
- [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)
