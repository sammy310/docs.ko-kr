---
title: '&amp; = 연산자 (Visual Basic)'
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
ms.openlocfilehash: 82d791e5d66c301442c99d2cc73e3172c3e30f17
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591630"
---
# <a name="amp-operator-visual-basic"></a><span data-ttu-id="78c3b-102">&amp; = 연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="78c3b-102">&amp;= Operator (Visual Basic)</span></span>
<span data-ttu-id="78c3b-103">@No__t-0 식을 `String` 변수 또는 속성에 연결 하 고 결과를 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-103">Concatenates a `String` expression to a `String` variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="78c3b-104">구문</span><span class="sxs-lookup"><span data-stu-id="78c3b-104">Syntax</span></span>  
  
```vb  
variableorproperty &= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="78c3b-105">요소</span><span class="sxs-lookup"><span data-stu-id="78c3b-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="78c3b-106">필수.</span><span class="sxs-lookup"><span data-stu-id="78c3b-106">Required.</span></span> <span data-ttu-id="78c3b-107">모든 @no__t 0 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-107">Any `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="78c3b-108">필수.</span><span class="sxs-lookup"><span data-stu-id="78c3b-108">Required.</span></span> <span data-ttu-id="78c3b-109">임의의 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-109">Any `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="78c3b-110">설명</span><span class="sxs-lookup"><span data-stu-id="78c3b-110">Remarks</span></span>  
 <span data-ttu-id="78c3b-111">@No__t-0 연산자의 좌 변에 있는 요소는 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-111">The element on the left side of the `&=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="78c3b-112">변수 또는 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span> <span data-ttu-id="78c3b-113">@No__t-0 연산자는 오른쪽의 `String` 식을 왼쪽에 있는 `String` 변수 또는 속성에 연결 하 고 결과를 왼쪽에 있는 변수나 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-113">The `&=` operator concatenates the `String` expression on its right to the `String` variable or property on its left, and assigns the result to the variable or property on its left.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="78c3b-114">오버로딩</span><span class="sxs-lookup"><span data-stu-id="78c3b-114">Overloading</span></span>  
 <span data-ttu-id="78c3b-115">[& 연산자](../../../visual-basic/language-reference/operators/concatenation-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-115">The [& Operator](../../../visual-basic/language-reference/operators/concatenation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="78c3b-116">@No__t-0 연산자를 오버 로드 하면 `&=` 연산자의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-116">Overloading the `&` operator affects the behavior of the `&=` operator.</span></span> <span data-ttu-id="78c3b-117">코드에서-1 @no__t 오버 로드 하는 클래스 또는 구조체에 `&=`을 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-117">If your code uses `&=` on a class or structure that overloads `&`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="78c3b-118">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="78c3b-118">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="78c3b-119">예제</span><span class="sxs-lookup"><span data-stu-id="78c3b-119">Example</span></span>  
 <span data-ttu-id="78c3b-120">다음 예에서는 `&=` 연산자를 사용 하 여 두 개의 `String` 변수를 연결 하 고 결과를 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="78c3b-120">The following example uses the `&=` operator to concatenate two `String` variables and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#3)]  
  
## <a name="see-also"></a><span data-ttu-id="78c3b-121">참조</span><span class="sxs-lookup"><span data-stu-id="78c3b-121">See also</span></span>

- [<span data-ttu-id="78c3b-122">& 연산자</span><span class="sxs-lookup"><span data-stu-id="78c3b-122">& Operator</span></span>](../../../visual-basic/language-reference/operators/concatenation-operator.md)
- [<span data-ttu-id="78c3b-123">+= 연산자</span><span class="sxs-lookup"><span data-stu-id="78c3b-123">+= Operator</span></span>](../../../visual-basic/language-reference/operators/addition-assignment-operator.md)
- [<span data-ttu-id="78c3b-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="78c3b-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="78c3b-125">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="78c3b-125">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="78c3b-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="78c3b-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="78c3b-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="78c3b-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="78c3b-128">문(C++)</span><span class="sxs-lookup"><span data-stu-id="78c3b-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
