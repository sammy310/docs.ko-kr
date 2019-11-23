---
title: <<= 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.<<=
helpviewer_keywords:
- operator <<=
- assignment statements [Visual Basic], compound
- <<= operator [Visual Basic]
- statements [Visual Basic], compound assignment
- operator<<=
- compound assignment statements [Visual Basic]
ms.assetid: 8ad26613-faff-4e2f-89ee-63feee33bfda
ms.openlocfilehash: cc89e0dadc7148b21e695a53a2e746a00ed66441
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350950"
---
# <a name="-operator-visual-basic"></a>\<\<= Operator (Visual Basic)
Performs an arithmetic left shift on the value of a variable or property and assigns the result back to the variable or property.  
  
## <a name="syntax"></a>구문  
  
```vb  
variableorproperty <<= amount  
```  
  
## <a name="parts"></a>요소  
 `variableorproperty`  
 필수 요소. Variable or property of an integral type (`SByte`, `Byte`, `Short`, `UShort`, `Integer`, `UInteger`, `Long`, or `ULong`).  
  
 `amount`  
 필수 요소. Numeric expression of a data type that widens to `Integer`.  
  
## <a name="remarks"></a>주의  
 The element on the left side of the `<<=` operator can be a simple scalar variable, a property, or an element of an array. The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).  
  
 The `<<=` operator first performs an arithmetic left shift on the value of the variable or property. The operator then assigns the result of that operation back to that variable or property.  
  
 Arithmetic shifts are not circular, which means the bits shifted off one end of the result are not reintroduced at the other end. In an arithmetic left shift, the bits shifted beyond the range of the result data type are discarded, and the bit positions vacated on the right are set to zero.  
  
## <a name="overloading"></a>오버로딩  
 The [<< Operator](../../../visual-basic/language-reference/operators/left-shift-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure. Overloading the `<<` operator affects the behavior of the `<<=` operator. If your code uses `<<=` on a class or structure that overloads `<<`, be sure you understand its redefined behavior. 자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.  
  
## <a name="example"></a>예제  
 The following example uses the `<<=` operator to shift the bit pattern of an `Integer` variable left by the specified amount and assign the result to the variable.  
  
 [!code-vb[VbVbalrOperators#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#13)]  
  
## <a name="see-also"></a>참조

- [<< 연산자](../../../visual-basic/language-reference/operators/left-shift-operator.md)
- [할당 연산자](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [비트 시프트 연산자](../../../visual-basic/language-reference/operators/bit-shift-operators.md)
- [Visual Basic에서의 연산자 우선 순위](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [기능별 연산자 목록](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [문](../../../visual-basic/programming-guide/language-features/statements.md)
