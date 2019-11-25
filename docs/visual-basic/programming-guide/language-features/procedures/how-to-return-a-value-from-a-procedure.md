---
title: '방법: 프로시저에서 값 반환'
ms.date: 07/20/2015
helpviewer_keywords:
- Visual Basic code, procedures
- procedures [Visual Basic], returning from
- procedures [Visual Basic], returning a value
ms.assetid: 4bcc4724-2b4e-4df8-9b4b-16054607f87d
ms.openlocfilehash: 1371e4ed0ff28f9caf56eabf2a1bb9290edbe75c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346022"
---
# <a name="how-to-return-a-value-from-a-procedure-visual-basic"></a>방법: 프로시저에서 값 반환(Visual Basic)
A `Function` procedure returns a value to the calling code either by executing a `Return` statement or by encountering an `Exit Function` or `End Function` statement.  
  
### <a name="to-return-a-value-using-the-return-statement"></a>To return a value using the Return statement  
  
1. Put a `Return` statement at the point where the procedure's task is completed.  
  
2. Follow the `Return` keyword with an expression that yields the value you want to return to the calling code.  
  
3. 동일한 프로시저에 `Return` 문을 둘 이상 사용할 수 있습니다.  
  
     The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, and returns it to the calling code.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     The following example shows a typical call to `hypotenuse`, which stores the returned value.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
### <a name="to-return-a-value-using-exit-function-or-end-function"></a>To return a value using Exit Function or End Function  
  
1. In at least one place in the `Function` procedure, assign a value to the procedure's name.  
  
2. When you execute an `Exit Function` or `End Function` statement, Visual Basic returns the value most recently assigned to the procedure's name.  
  
3. 동일한 프로시저에 `Exit Function` 문을 둘 이상 사용할 수 있으며, `Return` 및 `Exit Function` 문을 혼합할 수도 있습니다.  
  
4. You can have only one `End Function` statement in a `Function` procedure.  
  
     For more information and an example, see "Return Value" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).  
  
## <a name="see-also"></a>참조

- [절차](./index.md)
- [Sub 프로시저](./sub-procedures.md)
- [속성 프로시저](./property-procedures.md)
- [연산자 프로시저](./operator-procedures.md)
- [프로시저 매개 변수 및 인수](./procedure-parameters-and-arguments.md)
- [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Return 문](../../../../visual-basic/language-reference/statements/return-statement.md)
- [방법: 값을 반환하는 프로시저 만들기](./how-to-create-a-procedure-that-returns-a-value.md)
- [방법: 값을 반환하는 프로시저 호출](./how-to-call-a-procedure-that-returns-a-value.md)
