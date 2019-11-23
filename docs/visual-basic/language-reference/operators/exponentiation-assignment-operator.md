---
title: ^= 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.^=
helpviewer_keywords:
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- ^= operator [Visual Basic]
- compound assignment statements [Visual Basic]
ms.assetid: 397da132-2d96-4a85-a7bc-f7c730a608c9
ms.openlocfilehash: 382e0b27c2dbf27e5acccf29f1b8d2b002cb6664
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2019
ms.locfileid: "71592230"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="bc45e-102">^= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="bc45e-102">^= Operator (Visual Basic)</span></span>
<span data-ttu-id="bc45e-103">변수나 속성의 값을 식의 거듭제곱으로 올리고 결과를 다시 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-103">Raises the value of a variable or property to the power of an expression and assigns the result back to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc45e-104">구문</span><span class="sxs-lookup"><span data-stu-id="bc45e-104">Syntax</span></span>  
  
```vb  
variableorproperty ^= expression  
```  
  
## <a name="parts"></a><span data-ttu-id="bc45e-105">요소</span><span class="sxs-lookup"><span data-stu-id="bc45e-105">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="bc45e-106">필수</span><span class="sxs-lookup"><span data-stu-id="bc45e-106">Required.</span></span> <span data-ttu-id="bc45e-107">임의의 숫자 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-107">Any numeric variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="bc45e-108">필수</span><span class="sxs-lookup"><span data-stu-id="bc45e-108">Required.</span></span> <span data-ttu-id="bc45e-109">임의의 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-109">Any numeric expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bc45e-110">주의</span><span class="sxs-lookup"><span data-stu-id="bc45e-110">Remarks</span></span>  
 <span data-ttu-id="bc45e-111">`^=` 연산자의 좌 변에 있는 요소는 간단한 스칼라 변수, 속성 또는 배열의 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-111">The element on the left side of the `^=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="bc45e-112">변수 또는 속성은 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-112">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="bc45e-113">`^=` 연산자는 먼저 연산자의 왼쪽에 있는 변수나 속성의 값을 식의 값 (연산자의 오른쪽에 있는)의 거듭제곱으로 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-113">The `^=` operator first raises the value of the variable or property (on the left-hand side of the operator) to the power of the value of the expression (on the right-hand side of the operator).</span></span> <span data-ttu-id="bc45e-114">그런 다음 연산자는 해당 작업의 결과를 변수 또는 속성에 다시 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-114">The operator then assigns the result of that operation back to the variable or property.</span></span>  
  
 <span data-ttu-id="bc45e-115">Visual Basic는 [Double 데이터 형식](../../../visual-basic/language-reference/data-types/double-data-type.md)에서 항상 지 각 연산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-115">Visual Basic always performs exponentiation in the [Double Data Type](../../../visual-basic/language-reference/data-types/double-data-type.md).</span></span> <span data-ttu-id="bc45e-116">다른 형식의 피연산자는 `Double`로 변환 되 고 결과는 항상 `Double`됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-116">Operands of any different type are converted to `Double`, and the result is always `Double`.</span></span>  
  
 <span data-ttu-id="bc45e-117">`expression`의 값은 소수 자릿수, 음수 또는 둘 다 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-117">The value of `expression` can be fractional, negative, or both.</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="bc45e-118">오버로딩</span><span class="sxs-lookup"><span data-stu-id="bc45e-118">Overloading</span></span>  
 <span data-ttu-id="bc45e-119">[^ 연산자](../../../visual-basic/language-reference/operators/exponentiation-operator.md) 는 *오버 로드*될 수 있습니다. 즉, 피연산자가 해당 클래스 또는 구조체의 형식일 때 클래스 또는 구조체의 동작을 재정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-119">The [^ Operator](../../../visual-basic/language-reference/operators/exponentiation-operator.md) can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="bc45e-120">`^` 연산자를 오버 로드 하면 `^=` 연산자의 동작에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-120">Overloading the `^` operator affects the behavior of the `^=` operator.</span></span> <span data-ttu-id="bc45e-121">코드에서 `^`오버 로드 하는 클래스 또는 구조체에 `^=`를 사용 하는 경우 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-121">If your code uses `^=` on a class or structure that overloads `^`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="bc45e-122">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc45e-122">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="bc45e-123">예제</span><span class="sxs-lookup"><span data-stu-id="bc45e-123">Example</span></span>  
 <span data-ttu-id="bc45e-124">다음 예에서는 `^=` 연산자를 사용 하 여 하나의 `Integer` 변수 값을 두 번째 변수의 거듭제곱으로 올리고 결과를 첫 번째 변수에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45e-124">The following example uses the `^=` operator to raise the value of one `Integer` variable to the power of a second variable and assign the result to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#21)]  
  
## <a name="see-also"></a><span data-ttu-id="bc45e-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bc45e-125">See also</span></span>

- [<span data-ttu-id="bc45e-126">^ 연산자</span><span class="sxs-lookup"><span data-stu-id="bc45e-126">^ Operator</span></span>](../../../visual-basic/language-reference/operators/exponentiation-operator.md)
- [<span data-ttu-id="bc45e-127">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="bc45e-127">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="bc45e-128">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="bc45e-128">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="bc45e-129">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="bc45e-129">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="bc45e-130">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="bc45e-130">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="bc45e-131">문(C++)</span><span class="sxs-lookup"><span data-stu-id="bc45e-131">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
