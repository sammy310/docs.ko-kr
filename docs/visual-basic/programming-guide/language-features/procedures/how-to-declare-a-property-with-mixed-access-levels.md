---
title: '방법: 액세스 수준이 혼합된 속성 선언'
ms.date: 07/20/2015
helpviewer_keywords:
- access levels [Visual Basic], properties
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- mixed access levels
- Visual Basic code, properties
- properties [Visual Basic], access levels
- Property statement [Visual Basic], declaring mixed access levels
ms.assetid: fdbb2d97-279a-4956-b26c-cbdfbc34915a
ms.openlocfilehash: d74e23f33fbf7d9d29ab84b9b1bd4fc08863ac48
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349692"
---
# <a name="how-to-declare-a-property-with-mixed-access-levels-visual-basic"></a>방법: 액세스 수준이 혼합된 속성 선언(Visual Basic)
속성의 `Get` 및 `Set` 프로시저에 서로 다른 액세스 수준을 설정 하려면 `Property` 문에서 보다 관대 한 수준을 사용 하 고 `Get` 또는 `Set` 문에서 더 제한적인 수준을 사용할 수 있습니다. 코드의 특정 부분에서 속성 값을 가져올 수 있도록 하 고 코드의 특정 부분에서 값을 변경할 수 있도록 하려면 속성에 대해 혼합 된 액세스 수준을 사용 합니다.  
  
 액세스 수준에 대 한 자세한 내용은 [Visual Basic의 액세스 수준](../../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)을 참조 하세요.  
  
### <a name="to-declare-a-property-with-mixed-access-levels"></a>혼합 된 액세스 수준으로 속성을 선언 하려면  
  
1. 일반적인 방법으로 속성을 선언 하 고 `Property` 문에서 덜 제한적인 액세스 수준 (예: `Public`)을 지정 합니다.  
  
2. 더 제한적인 액세스 수준 (예: `Friend`)을 지정 하는 `Get` 또는 `Set` 프로시저를 선언 합니다.  
  
3. 다른 속성 프로시저에 대 한 액세스 수준을 지정 하지 마십시오. `Property` 문에서 선언 된 액세스 수준으로 가정 합니다. 속성 프로시저 중 하나에 대해서만 액세스를 제한할 수 있습니다.  
  
     [!code-vb[VbVbcnProcedures#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#10)]  
  
     위의 예제에서 `Get` 프로시저는 속성 자체와 동일한 `Protected` 액세스를 가지 며 `Set` 프로시저에는 `Private` 액세스 권한이 있습니다. `employee`에서 파생 된 클래스는 `salary` 값을 읽을 수 있지만 `employee` 클래스만이 값을 설정할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목

- [절차](./index.md)
- [속성 프로시저](./property-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Property 문](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Visual Basic에서 속성과 변수의 차이점](./differences-between-properties-and-variables.md)
- [방법: 속성 만들기](./how-to-create-a-property.md)
- [방법: 속성 프로시저 호출](./how-to-call-a-property-procedure.md)
- [방법: Visual Basic에서 기본 속성 선언 및 호출](./how-to-declare-and-call-a-default-property.md)
- [방법: 속성 값 입력](./how-to-put-a-value-in-a-property.md)
- [방법: 속성에서 값 가져오기](./how-to-get-a-value-from-a-property.md)
