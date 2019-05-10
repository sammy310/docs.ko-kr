---
title: 값 및 참조로 인수 전달(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: eb2260c6547d4f1cd7d9c23445ac38ac600e3535
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64638862"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="04fe8-102">값 및 참조로 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="04fe8-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="04fe8-103">Visual Basic의 프로시저에 인수를 전달할 수 있습니다 *값별로* 하거나 *참조별*합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-103">In Visual Basic, you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="04fe8-104">이 *전달 메커니즘*, 프로시저가 호출 코드에서 인수를 기본 프로그래밍 요소를 수정할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="04fe8-105">프로시저 선언을 지정 하 여 각 매개 변수의 전달 메커니즘을 결정 합니다 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 하거나 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="04fe8-106">차이점</span><span class="sxs-lookup"><span data-stu-id="04fe8-106">Distinctions</span></span>  
 <span data-ttu-id="04fe8-107">프로시저에 인수로 전달할 경우 서로 상호 작용 하는 몇 가지 다른 차이점 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
- <span data-ttu-id="04fe8-108">기본 프로그래밍 요소를 수정할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="04fe8-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="04fe8-109">인수 자체를 수정할 수 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="04fe8-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="04fe8-110">값별 또는 참조별 인수가 전달 되 고 있는지 여부</span><span class="sxs-lookup"><span data-stu-id="04fe8-110">Whether the argument is being passed by value or by reference</span></span>  
  
- <span data-ttu-id="04fe8-111">값 형식 또는 참조 형식 인수 데이터 형식 인지</span><span class="sxs-lookup"><span data-stu-id="04fe8-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="04fe8-112">자세한 내용은 참조 하세요. [수정할 간의 차이점 및 수정할 수 없는 인수](./differences-between-modifiable-and-nonmodifiable-arguments.md) 하 고 [차이 간의 값과 By Reference 인수를 전달](./differences-between-passing-an-argument-by-value-and-by-reference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="04fe8-113">전달 메커니즘의 선택</span><span class="sxs-lookup"><span data-stu-id="04fe8-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="04fe8-114">각 인수에 대해 신중 하 게 전달 메커니즘을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
- <span data-ttu-id="04fe8-115">**보호**합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-115">**Protection**.</span></span> <span data-ttu-id="04fe8-116">두 전달 메커니즘 중 하나를 선택할 가장 중요 한 조건을 변경 하려면 변수를 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="04fe8-117">인수를 전달 하는 장점은 `ByRef` 프로시저 해당 인수를 통해 호출 코드에 값을 반환할 수 있다는입니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="04fe8-118">인수를 전달 하는 장점은 `ByVal` 프로시저에 의해 변경 되는 변수를 보호 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
- <span data-ttu-id="04fe8-119">**성능**합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-119">**Performance**.</span></span> <span data-ttu-id="04fe8-120">전달 메커니즘 코드의 성능에 영향을 줄 수 있습니다, 있지만 차이 일반적으로 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="04fe8-121">이 한 가지 예외는 전달 되는 값 형식 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="04fe8-122">이 경우 Visual Basic 인수의 전체 데이터 콘텐츠를 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-122">In this case, Visual Basic copies the entire data contents of the argument.</span></span> <span data-ttu-id="04fe8-123">따라서 구조체와 같은 큰 값 형식의 경우이 더 효율적일 수 있습니다 전달 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="04fe8-124">참조 형식에 대 한 데이터에 대 한 포인터만 복사 (4 바이트 32 비트 플랫폼에서는 64 비트 플랫폼에서 8 바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="04fe8-125">따라서 형식의 인수를 전달할 수 있습니다 `String` 또는 `Object` 성능 영향을 주지 않고 값으로.</span><span class="sxs-lookup"><span data-stu-id="04fe8-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="04fe8-126">전달 메커니즘 확인</span><span class="sxs-lookup"><span data-stu-id="04fe8-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="04fe8-127">프로시저 선언 각 매개 변수의 전달 메커니즘을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="04fe8-128">호출 코드를 재정의할 수 없습니다는 `ByVal` 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="04fe8-129">매개 변수를 사용 하 여 선언 되 면 `ByRef`, 코드를 호출 하는 메커니즘을 강제로 실행할 수 있습니다 `ByVal` 호출에서 괄호 안에 인수 이름을 포함 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="04fe8-130">자세한 내용은 [방법: 값으로 전달 될 인수가](./how-to-force-an-argument-to-be-passed-by-value.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="04fe8-131">Visual Basic의 기본값인 값으로 인수 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-131">The default in Visual Basic is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="04fe8-132">값으로 인수를 전달 하는 경우</span><span class="sxs-lookup"><span data-stu-id="04fe8-132">When to Pass an Argument by Value</span></span>  
  
- <span data-ttu-id="04fe8-133">호출 코드 요소가 인수의 기반이 되는 요소를 수정할 수 없는 경우 해당 매개 변수를 선언 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="04fe8-134">코드 없이 수정할 수 없는 요소의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-134">No code can change the value of a nonmodifiable element.</span></span>  
  
- <span data-ttu-id="04fe8-135">기본 요소는 수정할 수 있지만 해당 값을 변경할 수 하는 절차를 원하지 않는 경우 매개 변수를 선언 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="04fe8-136">호출 코드에만 값으로 전달 수정할 수 있는 요소의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="04fe8-137">참조로 인수를 전달 하는 경우</span><span class="sxs-lookup"><span data-stu-id="04fe8-137">When to Pass an Argument by Reference</span></span>  
  
- <span data-ttu-id="04fe8-138">프로시저에 호출 코드의 내부 요소를 변경 해야 하는 경우 해당 매개 변수를 선언 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
- <span data-ttu-id="04fe8-139">호출 코드에서 기본 요소를 변경 하는 절차에 따라 올바른 코드를 실행 하는 경우 매개 변수를 선언 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="04fe8-140">값으로 전달 하는 경우 또는 호출 코드에서 재정의 하는 경우는 `ByRef` 인수를 괄호로 묶어 전달 메커니즘 프로시저 호출에 예기치 않은 결과가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="04fe8-141">예제</span><span class="sxs-lookup"><span data-stu-id="04fe8-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="04fe8-142">설명</span><span class="sxs-lookup"><span data-stu-id="04fe8-142">Description</span></span>  
 <span data-ttu-id="04fe8-143">다음 예제에서는 값으로 인수를 전달 하는 경우 및 참조로 전달 하는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="04fe8-144">프로시저 `Calculate` 둘 다 포함 된 `ByVal` 및 `ByRef` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="04fe8-145">이자율을 지정 `rate`, 및 금액 합계 `debt`, 프로시저의 작업에 대 한 새 값을 계산 하는 것 `debt` 이자의 원래 값에 적용 한 결과인 `debt`.</span><span class="sxs-lookup"><span data-stu-id="04fe8-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="04fe8-146">때문에 `debt` 되는 `ByRef` 매개 변수를 새 합계에 해당 하는 호출 코드에서 인수 값에 반영 됩니다 `debt`합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="04fe8-147">매개 변수 `rate` 되는 `ByVal` 매개 변수 때문에 `Calculate` 해당 값을 변경 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04fe8-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="04fe8-148">코드</span><span class="sxs-lookup"><span data-stu-id="04fe8-148">Code</span></span>  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="04fe8-149">참고자료</span><span class="sxs-lookup"><span data-stu-id="04fe8-149">See also</span></span>

- [<span data-ttu-id="04fe8-150">절차</span><span class="sxs-lookup"><span data-stu-id="04fe8-150">Procedures</span></span>](./index.md)
- [<span data-ttu-id="04fe8-151">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="04fe8-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="04fe8-152">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="04fe8-152">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="04fe8-153">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="04fe8-153">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="04fe8-154">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="04fe8-154">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="04fe8-155">방법: 인수가 값으로 전달 되도록 설정</span><span class="sxs-lookup"><span data-stu-id="04fe8-155">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="04fe8-156">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="04fe8-156">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="04fe8-157">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="04fe8-157">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
