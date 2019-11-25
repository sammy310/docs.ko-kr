---
title: 상수 및 리터럴 데이터 형식
ms.date: 07/20/2015
helpviewer_keywords:
- declaring constants [Visual Basic], literal data types
- data types [Visual Basic], declaring
- constants [Visual Basic], declaring
- explicit declarations
- literals [Visual Basic], coercing data type
- declarations [Visual Basic], data types
ms.assetid: 057206d2-3a5b-40b9-b3af-57446f9b52fa
ms.openlocfilehash: 8ebecddfab0724023c269e92c1fc5534f096bf1c
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74333726"
---
# <a name="constant-and-literal-data-types-visual-basic"></a>상수 및 리터럴 데이터 형식(Visual Basic)
A literal is a value that is expressed as itself rather than as a variable's value or the result of an expression, such as the number 3 or the string "Hello". A constant is a meaningful name that takes the place of a literal and retains this same value throughout the program, as opposed to a variable, whose value may change.  
  
 When [Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) is `Off` and [Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) is `On`, you must declare all constants explicitly with a data type. In the following example, the data type of `MyByte` is explicitly declared as data type `Byte`:  
  
 [!code-vb[VbVbalrConstants#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#1)]  
  
 When `Option Infer` is `On` or `Option Strict` is `Off`, you can declare a constant without specifying a data type with an `As` clause. The compiler determines the type of the constant from the type of the expression. A numeric integer literal is cast by default to the `Integer` data type. The default data type for floating-point numbers is `Double`, and the keywords `True` and `False` specify a `Boolean` constant.  
  
## <a name="literals-and-type-coercion"></a>Literals and Type Coercion  
 In some cases, you might want to force a literal to a particular data type; for example, when assigning a particularly large integral literal value to a variable of type `Decimal`. The following example produces an error:  
  
```vb  
Dim myDecimal as Decimal  
myDecimal = 100000000000000000000   ' This causes a compiler error.  
```  
  
 The error results from the representation of the literal. The `Decimal` data type can hold a value this large, but the literal is implicitly represented as a `Long`, which cannot.  
  
 You can coerce a literal to a particular data type in two ways: by appending a type character to it, or by placing it within enclosing characters. A type character or enclosing characters must immediately precede and/or follow the literal, with no intervening space or characters of any kind.  
  
 To make the previous example work, you can append the `D` type character to the literal, which causes it to be represented as a `Decimal`:  
  
 [!code-vb[VbVbalrConstants#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#2)]  
  
 The following example demonstrates correct usage of type characters and enclosing characters:  
  
 [!code-vb[VbVbalrConstants#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrConstants/VB/Class1.vb#3)]  
  
 The following table shows the enclosing characters and type characters available in Visual Basic.  
  
|데이터 형식|Enclosing character|Appended type character|  
|---|---|---|  
|`Boolean`|(없음)|(없음)|  
|`Byte`|(없음)|(없음)|  
|`Char`|"|C|  
|`Date`|#|(없음)|  
|`Decimal`|(없음)|D or @|  
|`Double`|(없음)|R or #|  
|`Integer`|(없음)|I or %|  
|`Long`|(없음)|L or &|  
|`Short`|(없음)|S|  
|`Single`|(없음)|F or !|  
|`String`|"|(없음)|  
  
## <a name="see-also"></a>참조

- [사용자 정의 상수](../../../../visual-basic/programming-guide/language-features/constants-enums/user-defined-constants.md)
- [방법: 상수 선언](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-a-constant.md)
- [상수 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/constants-overview.md)
- [Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md)
- [Option Explicit 문](../../../../visual-basic/language-reference/statements/option-explicit-statement.md)
- [열거형 개요](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-overview.md)
- [How to: Declare an Enumeration](../../../../visual-basic/programming-guide/language-features/constants-enums/how-to-declare-enumerations.md)
- [열거형 및 이름 한정](../../../../visual-basic/programming-guide/language-features/constants-enums/enumerations-and-name-qualification.md)
- [데이터 형식](../../../../visual-basic/language-reference/data-types/index.md)
- [상수 및 열거형](../../../../visual-basic/language-reference/constants-and-enumerations.md)
