---
title: /= 연산자
ms.date: 07/20/2015
f1_keywords:
- vb./=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- /= operator [Visual Basic]
- operator /=
- compound assignment statements [Visual Basic]
ms.assetid: a1e22d0e-8380-4761-9da1-84fb51c34821
ms.openlocfilehash: a8a031e968df90496a4e263ae78d47045ccdc923
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331042"
---
# <a name="-operator-visual-basic"></a>/= 연산자(Visual Basic)
Divides the value of a variable or property by the value of an expression and assigns the floating-point result to the variable or property.  
  
## <a name="syntax"></a>구문  
  
```vb  
variableorproperty /= expression  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. Any numeric variable or property.  
  
 `expression`  
 필수 요소. 임의의 숫자 식입니다.  
  
## <a name="remarks"></a>주의  
 The element on the left side of the `/=` operator can be a simple scalar variable, a property, or an element of an array. The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 The `/=` operator first divides the value of the variable or property (on the left-hand side of the operator) by the value of the expression (on the right-hand side of the operator). The operator then assigns the floating-point result of that operation to the variable or property.  
  
 This statement assigns a `Double` value to the variable or property on the left. If `Option Strict` is `On`, `variableorproperty` must be a `Double`. If `Option Strict` is `Off`, Visual Basic performs an implicit conversion and assigns the resulting value to `variableorproperty`, with a possible error at run time. For more information, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md) and [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).  
  
## <a name="overloading"></a>오버로딩  
 The [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure. Overloading the `/` operator affects the behavior of the `/=` operator. If your code uses `/=` on a class or structure that overloads `/`, be sure you understand its redefined behavior. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 The following example uses the `/=` operator to divide one `Integer` variable by a second and assign the quotient to the first variable.  
  
 [!code-vb[VbVbalrOperators#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>참조

- [/ Operator (Visual Basic)](../../../visual-basic/language-reference/operators/floating-point-division-operator.md)
- [\\= Operator](../../../visual-basic/language-reference/operators/integer-division-assignment-operator.md)
- [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [산술 연산자](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [문](../../../visual-basic/programming-guide/language-features/statements.md)
