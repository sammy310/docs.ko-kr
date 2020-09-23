---
title: '방법: 값을 반환하는 프로시저 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 3d28162d2a2103477a20b08fc03c937de8b5a475
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071874"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>방법: 값을 반환하는 프로시저 만들기(Visual Basic)

프로시저를 사용 하 여 `Function` 호출 코드에 값을 반환 합니다.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>값을 반환 하는 프로시저를 만들려면  
  
1. 다른 프로시저 외부에서는 문을 사용 하 고 `Function` `End Function` 문을 사용 합니다.  
  
2. `Function`문에서 `Function` 키워드를 프로시저 이름으로 따르고 매개 변수 목록을 괄호로 묶습니다.  
  
3. 절을 사용 하 여 괄호를 따라 `As` 반환 된 값의 데이터 형식을 지정 합니다.  
  
4. 프로시저의 코드 문을 문과 문 사이에 `Function` 놓습니다 `End Function` .  
  
5. 문을 사용 `Return` 하 여 호출 코드에 값을 반환 합니다.  
  
     다음 `Function` 프로시저는 다른 두 변의 값을 고려 하 여 오른쪽 삼각형의 가장 긴 쪽 또는 빗변을 계산 합니다.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     다음 예제에서는에 대 한 일반적인 호출을 보여 줍니다 `hypotenuse` .  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>참조

- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Function 문](../../../language-reference/statements/function-statement.md)
- [방법: 프로시저에서 값 반환](./how-to-return-a-value-from-a-procedure.md)
- [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
