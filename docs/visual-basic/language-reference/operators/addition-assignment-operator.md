---
title: += 연산자(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.+=
helpviewer_keywords:
- += operator [Visual Basic]
- assignment statements [Visual Basic], compound
- statements [Visual Basic], compound assignment
- += operator [Visual Basic], appending strings
- compound assignment statements [Visual Basic]
ms.assetid: d3e959f4-85d4-4e47-87c4-77b62335a5b3
ms.openlocfilehash: 4b8f36397d0f52866ebe9fa188d6b163364aeffc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61608335"
---
# <a name="-operator-visual-basic"></a><span data-ttu-id="f10c6-102">+= 연산자(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f10c6-102">+= Operator (Visual Basic)</span></span>
<span data-ttu-id="f10c6-103">숫자 변수 또는 속성의 값에 숫자 식의 값을 추가 하 고 그 결과 변수 또는 속성에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-103">Adds the value of a numeric expression to the value of a numeric variable or property and assigns the result to the variable or property.</span></span> <span data-ttu-id="f10c6-104">연결을 사용할 수도 있습니다는 `String` 식을 `String` 변수 또는 속성 및 변수 또는 속성에 결과 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-104">Can also be used to concatenate a `String` expression to a `String` variable or property and assign the result to the variable or property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f10c6-105">구문</span><span class="sxs-lookup"><span data-stu-id="f10c6-105">Syntax</span></span>  
  
```  
variableorproperty += expression  
```  
  
## <a name="parts"></a><span data-ttu-id="f10c6-106">요소</span><span class="sxs-lookup"><span data-stu-id="f10c6-106">Parts</span></span>  
 `variableorproperty`  
 <span data-ttu-id="f10c6-107">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f10c6-107">Required.</span></span> <span data-ttu-id="f10c6-108">모든 숫자 또는 `String` 변수 또는 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-108">Any numeric or `String` variable or property.</span></span>  
  
 `expression`  
 <span data-ttu-id="f10c6-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="f10c6-109">Required.</span></span> <span data-ttu-id="f10c6-110">모든 숫자 또는 `String` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-110">Any numeric or `String` expression.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f10c6-111">설명</span><span class="sxs-lookup"><span data-stu-id="f10c6-111">Remarks</span></span>  
 <span data-ttu-id="f10c6-112">왼쪽된에 있는 요소는 `+=` 연산자는 간단한 스칼라 변수, 속성 또는 배열의 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-112">The element on the left side of the `+=` operator can be a simple scalar variable, a property, or an element of an array.</span></span> <span data-ttu-id="f10c6-113">변수 또는 속성 일 수 없습니다 [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-113">The variable or property cannot be [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md).</span></span>  
  
 <span data-ttu-id="f10c6-114">`+=` 연산자는 변수 또는 속성의 왼쪽에서 오른쪽에 값을 추가 하 고 결과를 변수나 속성 왼쪽에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-114">The `+=` operator adds the value on its right to the variable or property on its left, and assigns the result to the variable or property on its left.</span></span> <span data-ttu-id="f10c6-115">`+=` 연결할 연산자 사용할 수도 있습니다는 `String` 는 오른쪽에 식이 `String` 변수 또는 결과 변수에 할당의 왼쪽에는 속성 또는 왼쪽의 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-115">The `+=` operator can also be used to concatenate the `String` expression on its right to the `String` variable or property on its left, and assign the result to the variable or property on its left.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f10c6-116">사용 하는 경우는 `+=` 연산자, 더하기 또는 문자열 연결 발생할 지 여부를 확인 하려면 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-116">When you use the `+=` operator, you might not be able to determine whether addition or string concatenation will occur.</span></span> <span data-ttu-id="f10c6-117">사용 된 `&=` 모호성을 제거 하 고 자동 문서화 코드를 제공 하도록 연결에 대 한 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-117">Use the `&=` operator for concatenation to eliminate ambiguity and to provide self-documenting code.</span></span>  
  
 <span data-ttu-id="f10c6-118">이 할당 연산자는 암시적으로 컴파일 환경에서 엄격한 의미 체계를 적용 하는 경우 변환 형식을 확장을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-118">This assignment operator implicitly performs widening but not narrowing conversions if the compilation environment enforces strict semantics.</span></span> <span data-ttu-id="f10c6-119">이러한 변환에 대 한 자세한 내용은 참조 하세요. [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-119">For more information on these conversions, see [Widening and Narrowing Conversions](../../../visual-basic/programming-guide/language-features/data-types/widening-and-narrowing-conversions.md).</span></span> <span data-ttu-id="f10c6-120">엄격한 및 관대 한 의미 체계에 대 한 자세한 내용은 참조 하세요. [Option Strict 문](../../../visual-basic/language-reference/statements/option-strict-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-120">For more information on strict and permissive semantics, see [Option Strict Statement](../../../visual-basic/language-reference/statements/option-strict-statement.md).</span></span>  
  
 <span data-ttu-id="f10c6-121">관대 한 의미 체계에 허용 합니다 `+=` 다양 한 문자열 및 숫자 변환에서 수행 하는 동일한를 암시적으로 수행 하는 연산자는 `+` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-121">If permissive semantics are allowed, the `+=` operator implicitly performs a variety of string and numeric conversions identical to those performed by the `+` operator.</span></span> <span data-ttu-id="f10c6-122">이러한 변환에 대 한 내용은 참조 하세요 [+ 연산자](../../../visual-basic/language-reference/operators/addition-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-122">For details on these conversions, see [+ Operator](../../../visual-basic/language-reference/operators/addition-operator.md).</span></span>  
  
## <a name="overloading"></a><span data-ttu-id="f10c6-123">오버로딩</span><span class="sxs-lookup"><span data-stu-id="f10c6-123">Overloading</span></span>  
 <span data-ttu-id="f10c6-124">합니다 `+` 연산자 *오버 로드 된*, 클래스 또는 구조체 수 할 동작 피연산자에 해당 클래스 또는 구조체 형식의 경우.</span><span class="sxs-lookup"><span data-stu-id="f10c6-124">The `+` operator can be *overloaded*, which means that a class or structure can redefine its behavior when an operand has the type of that class or structure.</span></span> <span data-ttu-id="f10c6-125">오버 로드 된 `+` 연산자의 동작에 영향을 줍니다는 `+=` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-125">Overloading the `+` operator affects the behavior of the `+=` operator.</span></span> <span data-ttu-id="f10c6-126">코드를 사용 하는 경우 `+=` 클래스나 구조체에 오버 로드에서 `+`, 다시 정의 된 동작을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-126">If your code uses `+=` on a class or structure that overloads `+`, be sure you understand its redefined behavior.</span></span> <span data-ttu-id="f10c6-127">자세한 내용은 [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f10c6-127">For more information, see [Operator Procedures](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="f10c6-128">예제</span><span class="sxs-lookup"><span data-stu-id="f10c6-128">Example</span></span>  
 <span data-ttu-id="f10c6-129">다음 예제에서는 `+=` 다른 하나의 변수 값을 결합 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-129">The following example uses the `+=` operator to combine the value of one variable with another.</span></span> <span data-ttu-id="f10c6-130">첫 번째 부분에서는 `+=` 다른 하나의 값을 추가 하려면 숫자 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-130">The first part uses `+=` with numeric variables to add one value to another.</span></span> <span data-ttu-id="f10c6-131">두 번째 부분에서는 `+=` 사용 하 여 `String` 다른 하나의 값을 연결 하는 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-131">The second part uses `+=` with `String` variables to concatenate one value with another.</span></span> <span data-ttu-id="f10c6-132">두 경우 모두 결과 첫 번째 변수에 할당 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-132">In both cases, the result is assigned to the first variable.</span></span>  
  
 [!code-vb[VbVbalrOperators#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#7)]  
  
 [!code-vb[VbVbalrOperators#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOperators/VB/Class1.vb#8)]  
  
 <span data-ttu-id="f10c6-133">변수의 `num1` 의 값과 13, 이제는 `str1` 은 "103"입니다.</span><span class="sxs-lookup"><span data-stu-id="f10c6-133">The value of `num1` is now 13, and the value of `str1` is now "103".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f10c6-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="f10c6-134">See also</span></span>

- [<span data-ttu-id="f10c6-135">+ 연산자</span><span class="sxs-lookup"><span data-stu-id="f10c6-135">+ Operator</span></span>](../../../visual-basic/language-reference/operators/addition-operator.md)
- [<span data-ttu-id="f10c6-136">할당 연산자</span><span class="sxs-lookup"><span data-stu-id="f10c6-136">Assignment Operators</span></span>](../../../visual-basic/language-reference/operators/assignment-operators.md)
- [<span data-ttu-id="f10c6-137">산술 연산자</span><span class="sxs-lookup"><span data-stu-id="f10c6-137">Arithmetic Operators</span></span>](../../../visual-basic/language-reference/operators/arithmetic-operators.md)
- [<span data-ttu-id="f10c6-138">연결 연산자</span><span class="sxs-lookup"><span data-stu-id="f10c6-138">Concatenation Operators</span></span>](../../../visual-basic/language-reference/operators/concatenation-operators.md)
- [<span data-ttu-id="f10c6-139">Visual Basic에서의 연산자 우선 순위</span><span class="sxs-lookup"><span data-stu-id="f10c6-139">Operator Precedence in Visual Basic</span></span>](../../../visual-basic/language-reference/operators/operator-precedence.md)
- [<span data-ttu-id="f10c6-140">기능별 연산자 목록</span><span class="sxs-lookup"><span data-stu-id="f10c6-140">Operators Listed by Functionality</span></span>](../../../visual-basic/language-reference/operators/operators-listed-by-functionality.md)
- [<span data-ttu-id="f10c6-141">문(C++)</span><span class="sxs-lookup"><span data-stu-id="f10c6-141">Statements</span></span>](../../../visual-basic/programming-guide/language-features/statements.md)
