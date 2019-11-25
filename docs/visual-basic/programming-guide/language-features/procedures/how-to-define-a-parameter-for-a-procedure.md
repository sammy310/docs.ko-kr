---
title: '방법: 프로시저의 매개 변수 정의'
ms.date: 07/20/2015
helpviewer_keywords:
- procedure parameters [Visual Basic], defining data types for
- procedures [Visual Basic], parameters
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedure parameters [Visual Basic], defining
ms.assetid: 7962808d-407e-4e84-984e-43e9857c53c9
ms.openlocfilehash: 411959a7be92ea49a59558b508e992bfba8eff95
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344878"
---
# <a name="how-to-define-a-parameter-for-a-procedure-visual-basic"></a>방법: 프로시저의 매개 변수 정의(Visual Basic)
A *parameter* allows the calling code to pass a value to the procedure when it calls it. You declare each parameter for a procedure the same way you declare a variable, specifying its name and data type. You also specify the passing mechanism, and whether the parameter is optional.  
  
 For more information, see [Procedure Parameters and Arguments](./procedure-parameters-and-arguments.md).  
  
### <a name="to-define-a-procedure-parameter"></a>To define a procedure parameter  
  
1. In the procedure declaration, add the parameter name to the procedure's parameter list, separating it from other parameters by commas.  
  
2. Decide the data type of the parameter.  
  
3. Follow the parameter name with an `As` clause to specify the data type.  
  
4. Decide the passing mechanism you want for the parameter. Normally you pass a parameter by value, unless you want the procedure to be able to change its value in the calling code.  
  
5. Precede the parameter name with [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) to specify the passing mechanism. For more information, see [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).  
  
6. If the parameter is optional, precede the passing mechanism with [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) and follow the parameter data type with an equal sign (`=`) and a default value.  
  
     The following example defines the outline of a `Sub` procedure with three parameters. The first two are required and the third is optional. The parameter declarations are separated in the parameter list by commas.  
  
     [!code-vb[VbVbcnProcedures#33](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#33)]  
  
     The first parameter accepts a `customer` object, and `updateCustomer` can directly update the variable passed to `c` because the argument is passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md). The procedure cannot change the values of the last two arguments because they are passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).  
  
     If the calling code does not supply a value for the `level` parameter, Visual Basic sets it to the default value of 0.  
  
     If the type checking switch ([Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) is `Off`, the `As` clause is optional when you define a parameter. However, if any one parameter uses an `As` clause, all of them must use it. If the type checking switch is `On`, the `As` clause is required for every parameter definition.  
  
     Specifying data types for all your programming elements is known as *strong typing*. When you set `Option Strict On`, Visual Basic enforces strong typing. This is strongly recommended, for the following reasons:  
  
    - It enables IntelliSense support for your variables and parameters. This allows you to see their properties and other members as you type in your code.  
  
    - It allows the compiler to perform type checking. This helps catch statements that can fail at run time due to errors such as overflow. It also catches calls to methods on objects that do not support them.  
  
    - It results in faster execution of your code. One reason for this is that if you do not specify a data type for a programming element, the Visual Basic compiler assigns it the `Object` type. Your compiled code might have to convert back and forth between `Object` and other data types, which reduces performance.  
  
## <a name="see-also"></a>참조

- [절차](./index.md)
- [Sub 프로시저](./sub-procedures.md)
- [Function 프로시저](./function-procedures.md)
- [방법: 프로시저에 인수 전달](./how-to-pass-arguments-to-a-procedure.md)
- [값 또는 참조로 인수 전달](./passing-arguments-by-value-and-by-reference.md)
- [재귀 프로시저](./recursive-procedures.md)
- [프로시저 오버로딩](./procedure-overloading.md)
- [개체 및 클래스](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [개체 지향 프로그래밍(Visual Basic)](../../concepts/object-oriented-programming.md)
