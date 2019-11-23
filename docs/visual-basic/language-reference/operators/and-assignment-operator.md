---
title: '&amp;= Operator'
ms.date: 07/20/2015
f1_keywords:
- vb.&=
helpviewer_keywords:
- operator &=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '&= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 0cf262fc-1a05-419a-a503-60013f111c8a
ms.openlocfilehash: 8668bfcbf32bb34b422efe8116bbd12a2d80b1d4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350262"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="71df3-102">&amp;= Operator (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71df3-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="71df3-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span><span class="sxs-lookup"><span data-stu-id="71df3-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71df3-104">구문</span><span class="sxs-lookup"><span data-stu-id="71df3-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="71df3-105">요소</span><span class="sxs-lookup"><span data-stu-id="71df3-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="71df3-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="71df3-106">Required.</span></span> <span data-ttu-id="71df3-107">Any `String` variable or property.</span><span class="sxs-lookup"><span data-stu-id="71df3-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="71df3-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="71df3-108">Required.</span></span> <span data-ttu-id="71df3-109">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="71df3-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71df3-110">주의</span><span class="sxs-lookup"><span data-stu-id="71df3-110">Remarks</span></span>  
 <span data-ttu-id="71df3-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span><span class="sxs-lookup"><span data-stu-id="71df3-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="71df3-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span><span class="sxs-lookup"><span data-stu-id="71df3-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="71df3-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span><span class="sxs-lookup"><span data-stu-id="71df3-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="71df3-114">오버로딩</span><span class="sxs-lookup"><span data-stu-id="71df3-114">Overloading</span></span>  
 <span data-ttu-id="71df3-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span><span class="sxs-lookup"><span data-stu-id="71df3-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="71df3-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span><span class="sxs-lookup"><span data-stu-id="71df3-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="71df3-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span><span class="sxs-lookup"><span data-stu-id="71df3-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="71df3-118">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="71df3-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="71df3-119">예제</span><span class="sxs-lookup"><span data-stu-id="71df3-119">Example</span></span>  
 <span data-ttu-id="71df3-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span><span class="sxs-lookup"><span data-stu-id="71df3-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="71df3-121">참조</span><span class="sxs-lookup"><span data-stu-id="71df3-121">See also</span></span>

- [<span data-ttu-id="71df3-122">& 연산자</span><span class="sxs-lookup"><span data-stu-id="71df3-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="71df3-123">+= 연산자</span><span class="sxs-lookup"><span data-stu-id="71df3-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="71df3-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="71df3-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="71df3-125">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="71df3-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="71df3-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="71df3-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="71df3-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="71df3-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="71df3-128">문</span><span class="sxs-lookup"><span data-stu-id="71df3-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
