---
description: '자세히 알아보기: 방법: 값을 반환 하는 프로시저 호출 (Visual Basic)'
title: '방법: 값을 반환하는 프로시저 호출'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure calls [Visual Basic], returning values
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], returning a value
ms.assetid: a445127b-0f5f-465a-98fb-3e514b93d115
ms.openlocfilehash: 74c7b6c9340537088ac631fc47f9ebf7b1a203cb
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100466746"
---
# <a name="how-to-call-a-procedure-that-returns-a-value-visual-basic"></a>방법: 값을 반환하는 프로시저 호출(Visual Basic)

`Function`프로시저는 호출 코드에 값을 반환 합니다. 해당 이름과 인수를 대입문의 오른쪽에 포함 하거나 식에 포함 하 여 호출 합니다.  
  
### <a name="to-call-a-function-procedure-within-an-expression"></a>식 내에서 함수 프로시저를 호출 하려면  
  
1. `Function`변수를 사용 하는 것과 동일한 방식으로 프로시저 이름을 사용 합니다. `Function`식에서 변수나 상수를 사용할 수 있는 모든 곳에서 프로시저 호출을 사용할 수 있습니다.  
  
2. 프로시저 이름에 괄호를 추가 하 여 인수 목록을 묶습니다. 인수가 없으면 선택적으로 괄호를 생략할 수 있습니다. 그러나 괄호를 사용 하면 코드를 더 쉽게 읽을 수 있습니다.  
  
3. 인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다. 프로시저에서 해당 하는 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 `Function` 합니다.  
  
     또는 하나 이상의 인수를 이름으로 전달할 수 있습니다. 자세한 내용은 [위치 및 이름으로 인수 전달](./passing-arguments-by-position-and-by-name.md)을 참조 하세요.  
  
4. 프로시저에서 반환 된 값은 변수 또는 상수 값과 마찬가지로 식에 참여 합니다.  
  
### <a name="to-call-a-function-procedure-in-an-assignment-statement"></a>대입문에서 함수 프로시저를 호출 하려면  
  
1. `Function`대입문에 등호 () 기호를 사용 하 여 프로시저 이름을 사용 `=` 합니다.  
  
2. 프로시저 이름에 괄호를 추가 하 여 인수 목록을 묶습니다. 인수가 없으면 선택적으로 괄호를 생략할 수 있습니다. 그러나 괄호를 사용 하면 코드를 더 쉽게 읽을 수 있습니다.  
  
3. 인수 목록에서 인수를 쉼표로 구분 하 여 괄호 안에 넣습니다. `Function`이름을 기준으로 전달 하는 경우를 제외 하 고 프로시저에서 해당 매개 변수를 정의 하는 순서와 동일한 순서로 인수를 제공 해야 합니다.  
  
4. 프로시저에서 반환 된 값은 대입문의 왼쪽에 있는 변수 또는 속성에 저장 됩니다.  
  
## <a name="example"></a>예  

 다음 예에서는 Visual Basic를 호출 <xref:Microsoft.VisualBasic.Interaction.Environ%2A> 하 여 운영 체제 환경 변수의 값을 검색 합니다. 첫 번째 줄은 `Environ` 식 내에서를 호출 하 고 두 번째 줄은 대입문에서 호출 합니다. `Environ` 변수 이름을 유일한 인수로 사용 합니다. 이 메서드는 호출 코드에 변수의 값을 반환 합니다.  
  
 [!code-vb[VbVbcnProcedures#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#7)]  
  
## <a name="see-also"></a>추가 정보

- [함수 프로시저](./function-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Function 문](../../../language-reference/statements/function-statement.md)
- [방법: 값을 반환하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md)
- [방법: 프로시저에서 값 반환](./how-to-return-a-value-from-a-procedure.md)
- [방법: 값을 반환하지 않는 프로시저 호출](./how-to-call-a-procedure-that-does-not-return-a-value.md)
