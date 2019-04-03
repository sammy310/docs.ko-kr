---
title: '*= 연산자(Visual Basic)'
ms.date: 07/20/2015
f1_keywords:
- vb.*=
helpviewer_keywords:
- operator *=
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- '*= operator [Visual Basic]'
- compound assignment statements [Visual Basic]
ms.assetid: 96c86509-6eb8-4682-8226-3852e049376f
ms.openlocfilehash: 7c009a6b3acfe1528a2c34ed1e10735ac86507e6
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839316"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="a0151-102">\*= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a0151-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="a0151-103">식의 값으로 변수 또는 속성의 값을 곱한 변수 또는 속성에 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a0151-104">구문</span><span class="sxs-lookup"><span data-stu-id="a0151-104">Syntax</span></span>  
  
```  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="a0151-105">요소</span><span class="sxs-lookup"><span data-stu-id="a0151-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="a0151-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a0151-106">Required.</span></span> <span data-ttu-id="a0151-107">숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="a0151-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a0151-108">Required.</span></span> <span data-ttu-id="a0151-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a0151-110">설명</span><span class="sxs-lookup"><span data-stu-id="a0151-110">Remarks</span></span>  
 <span data-ttu-id="a0151-111">왼쪽된에 있는 요소는 `*=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="a0151-112">변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="a0151-113">`*=` 먼저 연산자는 변수 또는 속성 (연산자의 왼쪽)의 값에 따라 (연산자의 오른쪽에 있는)에 있는 식의 값을 곱합니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="a0151-114">연산자는 다음 변수 또는 속성에 해당 작업의 결과 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="a0151-115">오버로딩</span><span class="sxs-lookup"><span data-stu-id="a0151-115">Overloading</span></span>  
 <span data-ttu-id="a0151-116">합니다 [\* 연산자](../../../visual-basic/language-reference/operators/multiplication-operator.md) 될 수 있습니다 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="a0151-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="a0151-117">오버 로드 된 `*` 연산자의 동작에 영향을 줍니다는 `*=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="a0151-118">코드를 사용 하는 경우 `*=` 클래스나 구조체에 오버 로드에서 `*`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="a0151-119">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a0151-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a0151-120">예제</span><span class="sxs-lookup"><span data-stu-id="a0151-120">Example</span></span>  
 <span data-ttu-id="a0151-121">다음 예제에서는 합니다 `*=` 하나를 곱할 연산자 `Integer` 할당 첫 번째 변수에 결과 두 번째 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="a0151-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="a0151-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="a0151-122">See also</span></span>

- [<span data-ttu-id="a0151-123">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="a0151-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="a0151-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="a0151-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="a0151-125">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="a0151-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="a0151-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="a0151-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="a0151-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="a0151-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="a0151-128">문(C++)</span><span class="sxs-lookup"><span data-stu-id="a0151-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
