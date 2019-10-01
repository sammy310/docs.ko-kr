---
title: -= 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.-=
helpviewer_keywords:
- -= operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- operator -=
- compound assignment statements [Visual Basic]
ms.assetid: 5ead0c37-ae50-48f7-8435-8e341d81cae1
ms.openlocfilehash: f857c8bf2f89120e047c49674ce9e8a3bff22f7d
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71701311"
---
# <a name="--operator-visual-basic"></a><span data-ttu-id="93658-102">-= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93658-102">-= Operator (Visual Basic)</span></span>
<span data-ttu-id="93658-103">변수 또는 속성 값에서 식의 값을 빼고 결과를 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="93658-103">Subtracts the value of an expression from the value of a variable or property and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93658-104">구문</span><span class="sxs-lookup"><span data-stu-id="93658-104">Syntax</span></span>  
  
```vb  
variableorproperty -= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="93658-105">요소</span><span class="sxs-lookup"><span data-stu-id="93658-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="93658-106">필수.</span><span class="sxs-lookup"><span data-stu-id="93658-106">Required.</span></span> <span data-ttu-id="93658-107">임의의 숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="93658-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="93658-108">필수.</span><span class="sxs-lookup"><span data-stu-id="93658-108">Required.</span></span> <span data-ttu-id="93658-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="93658-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="93658-110">설명</span><span class="sxs-lookup"><span data-stu-id="93658-110">Remarks</span></span>  
 <span data-ttu-id="93658-111">@No__t-0 연산자의 좌 변에 있는 요소는 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93658-111">The element on the left side of the `-=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="93658-112">변수 또는 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="93658-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="93658-113">@No__t-0 연산자는 먼저 연산자의 오른쪽에 있는 식의 값을 연산자의 왼쪽에 있는 변수 또는 속성의 값에서 뺍니다.</span><span class="sxs-lookup"><span data-stu-id="93658-113">The `-=` operator first subtracts the value of the expression (on the right-hand side of the operator) from the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="93658-114">그런 다음 연산자는 해당 작업의 결과를 변수나 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="93658-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="93658-115">오버로딩</span><span class="sxs-lookup"><span data-stu-id="93658-115">Overloading</span></span>  
 <span data-ttu-id="93658-116">[-연산자 (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93658-116">The [- Operator (Visual Basic)](../../../visual-basic/language-reference/operators/subtraction-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="93658-117">@No__t-0 연산자를 오버 로드 하면 `-=` 연산자의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93658-117">Overloading the `-` operator affects the behavior of the `-=` operator.</span></span> <span data-ttu-id="93658-118">코드에서-1 @no__t 오버 로드 하는 클래스 또는 구조체에 `-=`을 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93658-118">If your code uses `-=` on a class or structure that overloads `-`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="93658-119">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93658-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="93658-120">예제</span><span class="sxs-lookup"><span data-stu-id="93658-120">Example</span></span>  
 <span data-ttu-id="93658-121">다음 예에서는 `-=` 연산자를 사용 하 여 다른 `Integer` 변수를 빼고 결과를 후자 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="93658-121">The following example uses the `-=` operator to subtract one `Integer` variable from another and assign the result to the latter variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="93658-122">참조</span><span class="sxs-lookup"><span data-stu-id="93658-122">See also</span></span>

- [<span data-ttu-id="93658-123">-연산자 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="93658-123">- Operator (Visual Basic)</span></span>](../../../visual-basic/language-reference/operators/subtraction-operator.md)
- [<span data-ttu-id="93658-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="93658-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="93658-125">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="93658-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="93658-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="93658-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="93658-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="93658-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="93658-128">문(C++)</span><span class="sxs-lookup"><span data-stu-id="93658-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
