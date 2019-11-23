---
title: ^= 연산자
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: fe5e8fc2b64b9e7c33483612071d338a0ee22768
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74331304"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="2df2b-102">^= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2df2b-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="2df2b-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="2df2b-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2df2b-104">구문</span><span class="sxs-lookup"><span data-stu-id="2df2b-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="2df2b-105">요소</span><span class="sxs-lookup"><span data-stu-id="2df2b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="2df2b-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2df2b-106">Required.</span></span> <span data-ttu-id="2df2b-107">Any numeric variable or property.</span><span class="sxs-lookup"><span data-stu-id="2df2b-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="2df2b-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="2df2b-108">Required.</span></span> <span data-ttu-id="2df2b-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2df2b-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2df2b-110">주의</span><span class="sxs-lookup"><span data-stu-id="2df2b-110">Remarks</span></span>  
 <span data-ttu-id="2df2b-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span><span class="sxs-lookup"><span data-stu-id="2df2b-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="2df2b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="2df2b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="2df2b-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span><span class="sxs-lookup"><span data-stu-id="2df2b-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="2df2b-114">The operator then assigns the result of that operation back to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="2df2b-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="2df2b-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span><span class="sxs-lookup"><span data-stu-id="2df2b-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="2df2b-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span><span class="sxs-lookup"><span data-stu-id="2df2b-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="2df2b-117">The value of `expression` can be fractional, negative, or both.</span><span class="sxs-lookup"><span data-stu-id="2df2b-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="2df2b-118">오버로딩</span><span class="sxs-lookup"><span data-stu-id="2df2b-118">Overloading</span></span>  
 <span data-ttu-id="2df2b-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="2df2b-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="2df2b-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span><span class="sxs-lookup"><span data-stu-id="2df2b-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="2df2b-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="2df2b-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="2df2b-122">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2df2b-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="2df2b-123">예제</span><span class="sxs-lookup"><span data-stu-id="2df2b-123">Example</span></span>  
 <span data-ttu-id="2df2b-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span><span class="sxs-lookup"><span data-stu-id="2df2b-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="2df2b-125">참조</span><span class="sxs-lookup"><span data-stu-id="2df2b-125">See also</span></span>

- [<span data-ttu-id="2df2b-126">^ 연산자</span><span class="sxs-lookup"><span data-stu-id="2df2b-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [<span data-ttu-id="2df2b-127">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="2df2b-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="2df2b-128">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="2df2b-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="2df2b-129">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="2df2b-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="2df2b-130">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="2df2b-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="2df2b-131">문</span><span class="sxs-lookup"><span data-stu-id="2df2b-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
