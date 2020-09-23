---
title: '방법: 프로시저에서 값 반환'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: cbc785a07aa8a7b299508a093e08d5d0510b838a
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071380"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>방법: 프로시저에서 값 반환(Visual Basic)

`Function`프로시저는 `Return` 문을 실행 하거나 `Exit Function` 또는 문을 실행 하 여 호출 코드에 값을 반환 합니다 `End Function` .  
  
### <a name="to-return-a-value-using-the-return-statement"></a>Return 문을 사용 하 여 값을 반환 하려면  
  
1. `Return`프로시저 태스크가 완료 된 지점에 문을 배치 합니다.  
  
2. `Return`호출 코드에 반환 하려는 값을 생성 하는 식을 사용 하 여 키워드를 따릅니다.  
  
3. 동일한 프로시저에 `Return` 문을 둘 이상 사용할 수 있습니다.  
  
     다음 `Function` 프로시저는 오른쪽 삼각형의 가장 긴 변 또는 빗변을 계산 하 고 호출 코드에 반환 합니다.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     다음 예제에서는 반환 된 값을 저장 하는에 대 한 일반적인 호출을 보여 줍니다 `hypotenuse` .  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>Exit Function 또는 End 함수를 사용 하 여 값을 반환 하려면  
  
1. 프로시저의 하나 이상의 위치에서 `Function` 프로시저의 이름에 값을 할당 합니다.  
  
2. 또는 문을 실행할 때 `Exit Function` `End Function` Visual Basic은 프로시저 이름에 가장 최근에 할당 된 값을 반환 합니다.  
  
3. 동일한 프로시저에 `Exit Function` 문을 둘 이상 사용할 수 있으며, `Return` 및 `Exit Function` 문을 혼합할 수도 있습니다.  
  
4. `End Function`프로시저에는 문을 하나만 사용할 수 있습니다 `Function` .  
  
     자세한 내용 및 예제는 [함수 문의](../../../language-reference/statements/function-statement.md)"Return Value"를 참조 하십시오.  
  
## <a name="see-also"></a>참조

- [절차](./index.md)
- [하위 프로시저](./sub-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Function 문](../../../language-reference/statements/function-statement.md)
- [Return 문](../../../language-reference/statements/return-statement.md)
- [방법: 값을 반환하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md)
- [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
