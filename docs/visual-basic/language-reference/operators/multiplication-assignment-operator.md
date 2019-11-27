---
title: '*= 연산자'
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
ms.openlocfilehash: 4b60fa44a92bff683e13f850da025d7fe753618d
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349780"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="243df-102">\*= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="243df-102">\*= Operator (Visual Basic)</span></span>
<span data-ttu-id="243df-103">변수 또는 속성의 값을 식의 값과 곱하고 결과를 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="243df-103">Multiplies the value of a variable or property by the value of an expression and assigns the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="243df-104">구문</span><span class="sxs-lookup"><span data-stu-id="243df-104">Syntax</span></span>  
  
```vb  
variableorproperty *= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="243df-105">요소</span><span class="sxs-lookup"><span data-stu-id="243df-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="243df-106">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="243df-106">Required.</span></span> <span data-ttu-id="243df-107">임의의 숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="243df-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="243df-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="243df-108">Required.</span></span> <span data-ttu-id="243df-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="243df-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="243df-110">설명</span><span class="sxs-lookup"><span data-stu-id="243df-110">Remarks</span></span>  
 <span data-ttu-id="243df-111">`*=` 연산자의 좌 변에 있는 요소는 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="243df-111">The element on the left side of the `*=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="243df-112">변수 또는 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="243df-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="243df-113">`*=` 연산자는 먼저 연산자의 오른쪽에 있는 식의 값을 연산자의 왼쪽에 있는 변수나 속성의 값으로 곱합니다 (연산자의 왼쪽에 있는).</span><span class="sxs-lookup"><span data-stu-id="243df-113">The `*=` operator first multiplies the value of the expression (on the right-hand side of the operator) by the value of the variable or property (on the left-hand side of the operator).</span></span> <span data-ttu-id="243df-114">그런 다음 연산자는 해당 작업의 결과를 변수나 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="243df-114">The operator then assigns the result of that operation to the variable or property.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="243df-115">오버로드</span><span class="sxs-lookup"><span data-stu-id="243df-115">Overloading</span></span>  
 <span data-ttu-id="243df-116">[\* 연산자](../../../visual-basic/language-reference/operators/multiplication-operator.md) 를 *오버 로드할*수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체에서 해당 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="243df-116">The [\* Operator](../../../visual-basic/language-reference/operators/multiplication-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="243df-117">`*` 연산자를 오버 로드 하면 `*=` 연산자의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="243df-117">Overloading the `*` operator affects the behavior of the `*=` operator.</span></span> <span data-ttu-id="243df-118">코드에서 `*`오버 로드 하는 클래스 또는 구조체에 `*=`를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="243df-118">If your code uses `*=` on a class or structure that overloads `*`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="243df-119">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="243df-119">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="243df-120">예제</span><span class="sxs-lookup"><span data-stu-id="243df-120">Example</span></span>  
 <span data-ttu-id="243df-121">다음 예에서는 `*=` 연산자를 사용 하 여 한 `Integer` 변수를 두 번째 변수에 곱하고 결과를 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="243df-121">The following example uses the `*=` operator to multiply one `Integer` variable by a second and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#5)]  
  
## <a name="see-also"></a><span data-ttu-id="243df-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="243df-122">See also</span></span>

- [<span data-ttu-id="243df-123">\* 연산자</span><span class="sxs-lookup"><span data-stu-id="243df-123">\* Operator</span></span>](../../../visual-basic/language-reference/operators/multiplication-operator.md)
- [<span data-ttu-id="243df-124">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="243df-124">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="243df-125">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="243df-125">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="243df-126">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="243df-126">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="243df-127">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="243df-127">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="243df-128">문</span><span class="sxs-lookup"><span data-stu-id="243df-128">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
