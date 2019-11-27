---
title: 값 또는 참조로 인수 전달
ms.date: 07/20/2015
helpviewer_keywords:
- ByRef keyword [Visual Basic], passing arguments by reference
- Visual Basic code, procedures
- passing arguments [Visual Basic], by value or by reference
- ByVal keyword [Visual Basic], passing arguments by value
- arguments [Visual Basic], passing by value or by reference
- argument passing [Visual Basic], by value or by reference
ms.assetid: fd8a9de6-7178-44d5-a9bf-458d4ad907c2
ms.openlocfilehash: 28e59753a35ab67b15fbc549df5bb8a3489aba5a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352601"
---
# <a name="passing-arguments-by-value-and-by-reference-visual-basic"></a><span data-ttu-id="0bb78-102">값 및 참조로 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0bb78-102">Passing Arguments by Value and by Reference (Visual Basic)</span></span>
<span data-ttu-id="0bb78-103">Visual Basic에서 인수를 *값* 또는 *참조로*프로시저에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-103">In Visual Basic, you can pass an argument to a procedure *by value* or *by reference*.</span></span> <span data-ttu-id="0bb78-104">이를 *전달 메커니즘*이라고 하며 프로시저에서 호출 코드의 인수 내부 프로그래밍 요소를 수정할 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-104">This is known as the *passing mechanism*, and it determines whether the procedure can modify the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="0bb78-105">프로시저 선언은 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드를 지정 하 여 각 매개 변수에 대 한 전달 메커니즘을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-105">The procedure declaration determines the passing mechanism for each parameter by specifying the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword.</span></span>  
  
## <a name="distinctions"></a><span data-ttu-id="0bb78-106">기준을</span><span class="sxs-lookup"><span data-stu-id="0bb78-106">Distinctions</span></span>  
 <span data-ttu-id="0bb78-107">프로시저에 인수를 전달할 때 서로 상호 작용 하는 여러 가지 차이점에 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-107">When passing an argument to a procedure, be aware of several different distinctions that interact with each other:</span></span>  
  
- <span data-ttu-id="0bb78-108">기본 프로그래밍 요소를 수정할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-108">Whether the underlying programming element is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="0bb78-109">인수 자체를 수정할 수 있는지 여부를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-109">Whether the argument itself is modifiable or nonmodifiable</span></span>  
  
- <span data-ttu-id="0bb78-110">인수가 값 또는 참조로 전달 되는지 여부</span><span class="sxs-lookup"><span data-stu-id="0bb78-110">Whether the argument is being passed by value or by reference</span></span>  
  
- <span data-ttu-id="0bb78-111">인수 데이터 형식이 값 형식 인지 또는 참조 형식 인지 여부</span><span class="sxs-lookup"><span data-stu-id="0bb78-111">Whether the argument data type is a value type or a reference type</span></span>  
  
 <span data-ttu-id="0bb78-112">자세한 내용은 [수정 가능 및 수정할](./differences-between-modifiable-and-nonmodifiable-arguments.md) 가능성이 [없는 인수와 인수를 값으로 전달할 때와 참조로 전달할](./differences-between-passing-an-argument-by-value-and-by-reference.md)때의 차이점을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bb78-112">For more information, see [Differences Between Modifiable and Nonmodifiable Arguments](./differences-between-modifiable-and-nonmodifiable-arguments.md) and [Differences Between Passing an Argument By Value and By Reference](./differences-between-passing-an-argument-by-value-and-by-reference.md).</span></span>  
  
## <a name="choice-of-passing-mechanism"></a><span data-ttu-id="0bb78-113">전달 메커니즘 선택</span><span class="sxs-lookup"><span data-stu-id="0bb78-113">Choice of Passing Mechanism</span></span>  
 <span data-ttu-id="0bb78-114">각 인수에 대해 전달 메커니즘을 신중 하 게 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-114">You should choose the passing mechanism carefully for each argument.</span></span>  
  
- <span data-ttu-id="0bb78-115">**보호**.</span><span class="sxs-lookup"><span data-stu-id="0bb78-115">**Protection**.</span></span> <span data-ttu-id="0bb78-116">두 전달 메커니즘 중에서 하나를 선택 하는 경우 가장 중요 한 기준은 변경 하는 호출 변수를 노출 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-116">In choosing between the two passing mechanisms, the most important criterion is the exposure of calling variables to change.</span></span> <span data-ttu-id="0bb78-117">인수 `ByRef` 전달의 이점은 프로시저에서 해당 인수를 통해 호출 코드에 값을 반환할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-117">The advantage of passing an argument `ByRef` is that the procedure can return a value to the calling code through that argument.</span></span> <span data-ttu-id="0bb78-118">`ByVal` 인수를 전달 하는 이점은 프로시저에 의해 변수가 변경 되지 않도록 보호 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-118">The advantage of passing an argument `ByVal` is that it protects a variable from being changed by the procedure.</span></span>  
  
- <span data-ttu-id="0bb78-119">**성능**.</span><span class="sxs-lookup"><span data-stu-id="0bb78-119">**Performance**.</span></span> <span data-ttu-id="0bb78-120">전달 메커니즘이 코드의 성능에 영향을 줄 수 있지만 차이점은 일반적으로 중요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-120">Although the passing mechanism can affect the performance of your code, the difference is usually insignificant.</span></span> <span data-ttu-id="0bb78-121">한 가지 예외는 `ByVal`전달 되는 값 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-121">One exception to this is a value type passed `ByVal`.</span></span> <span data-ttu-id="0bb78-122">이 경우 Visual Basic은 인수의 전체 데이터 내용을 복사 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-122">In this case, Visual Basic copies the entire data contents of the argument.</span></span> <span data-ttu-id="0bb78-123">따라서 구조체와 같은 많은 값 형식의 경우 `ByRef`전달 하는 것이 더 효율적일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-123">Therefore, for a large value type such as a structure, it can be more efficient to pass it `ByRef`.</span></span>  
  
     <span data-ttu-id="0bb78-124">참조 형식의 경우에는 데이터에 대 한 포인터만 복사 됩니다 (32 비트 플랫폼에서는 4 바이트, 64 비트 플랫폼에서는 8 바이트).</span><span class="sxs-lookup"><span data-stu-id="0bb78-124">For reference types, only the pointer to the data is copied (four bytes on 32-bit platforms, eight bytes on 64-bit platforms).</span></span> <span data-ttu-id="0bb78-125">따라서 저하를 사용 하지 않고 `String` 또는 `Object` 형식의 인수를 값으로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-125">Therefore, you can pass arguments of type `String` or `Object` by value without harming performance.</span></span>  
  
## <a name="determination-of-the-passing-mechanism"></a><span data-ttu-id="0bb78-126">전달 메커니즘의 결정</span><span class="sxs-lookup"><span data-stu-id="0bb78-126">Determination of the Passing Mechanism</span></span>  
 <span data-ttu-id="0bb78-127">프로시저 선언은 각 매개 변수에 대 한 전달 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-127">The procedure declaration specifies the passing mechanism for each parameter.</span></span> <span data-ttu-id="0bb78-128">호출 코드는 `ByVal` 메커니즘을 재정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-128">The calling code can't override a `ByVal` mechanism.</span></span>  
  
 <span data-ttu-id="0bb78-129">`ByRef`를 사용 하 여 매개 변수를 선언 하는 경우 호출 코드는 호출에서 인수 이름을 괄호로 묶어 `ByVal` 메커니즘을 강제로 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-129">If a parameter is declared with `ByRef`, the calling code can force the mechanism to `ByVal` by enclosing the argument name in parentheses in the call.</span></span> <span data-ttu-id="0bb78-130">자세한 내용은 [방법: 인수를 값으로 전달](./how-to-force-an-argument-to-be-passed-by-value.md)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bb78-130">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
 <span data-ttu-id="0bb78-131">Visual Basic의 기본값은 인수를 값으로 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-131">The default in Visual Basic is to pass arguments by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-value"></a><span data-ttu-id="0bb78-132">값으로 인수를 전달 하는 경우</span><span class="sxs-lookup"><span data-stu-id="0bb78-132">When to Pass an Argument by Value</span></span>  
  
- <span data-ttu-id="0bb78-133">인수의 내부 호출 코드 요소가 수정할 수 없는 요소인 경우 해당 하는 매개 변수를 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)로 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-133">If the calling code element underlying the argument is a nonmodifiable element, declare the corresponding parameter [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="0bb78-134">수정할 수 없는 요소의 값을 변경할 수 있는 코드는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-134">No code can change the value of a nonmodifiable element.</span></span>  
  
- <span data-ttu-id="0bb78-135">기본 요소를 수정할 수 있지만 프로시저에서 해당 값을 변경할 수 없도록 하려면 `ByVal`매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-135">If the underlying element is modifiable, but you do not want the procedure to be able to change its value, declare the parameter `ByVal`.</span></span> <span data-ttu-id="0bb78-136">호출 코드만 값으로 전달 되는 수정 가능한 요소의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-136">Only the calling code can change the value of a modifiable element passed by value.</span></span>  
  
## <a name="when-to-pass-an-argument-by-reference"></a><span data-ttu-id="0bb78-137">인수를 참조로 전달 하는 경우</span><span class="sxs-lookup"><span data-stu-id="0bb78-137">When to Pass an Argument by Reference</span></span>  
  
- <span data-ttu-id="0bb78-138">프로시저에서 호출 코드의 기본 요소를 변경 해야 하는 경우 해당 매개 변수 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md)를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-138">If the procedure has a genuine need to change the underlying element in the calling code, declare the corresponding parameter [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md).</span></span>  
  
- <span data-ttu-id="0bb78-139">코드를 올바르게 실행 하는 경우 호출 코드에서 기본 요소를 변경 하는 절차에 따라 `ByRef`매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-139">If the correct execution of the code depends on the procedure changing the underlying element in the calling code, declare the parameter `ByRef`.</span></span> <span data-ttu-id="0bb78-140">값으로 전달 하거나 호출 하는 코드가 인수를 괄호로 묶어 `ByRef` 전달 하는 메커니즘을 재정의 하는 경우 프로시저 호출이 예기치 않은 결과를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-140">If you pass it by value, or if the calling code overrides the `ByRef` passing mechanism by enclosing the argument in parentheses, the procedure call might produce unexpected results.</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bb78-141">예제</span><span class="sxs-lookup"><span data-stu-id="0bb78-141">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="0bb78-142">설명</span><span class="sxs-lookup"><span data-stu-id="0bb78-142">Description</span></span>  
 <span data-ttu-id="0bb78-143">다음 예제에서는 인수를 값으로 전달 하는 경우와 참조로 인수를 전달 하는 경우를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-143">The following example illustrates when to pass arguments by value and when to pass them by reference.</span></span> <span data-ttu-id="0bb78-144">프로시저 `Calculate`에 `ByVal` 및 `ByRef` 매개 변수가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-144">Procedure `Calculate` has both a `ByVal` and a `ByRef` parameter.</span></span> <span data-ttu-id="0bb78-145">이자율을 지정 하 고, `rate`하 고, `debt`금액의 합계를 제공 하는 경우 절차의 작업은 `debt`의 원래 값에 이자율을 적용 한 결과 `debt`에 대 한 새 값을 계산 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-145">Given an interest rate, `rate`, and a sum of money, `debt`, the task of the procedure is to calculate a new value for `debt` that is the result of applying the interest rate to the original value of `debt`.</span></span> <span data-ttu-id="0bb78-146">`debt`는 `ByRef` 매개 변수 이므로 새 합계는 `debt`에 해당 하는 호출 코드의 인수 값에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-146">Because `debt` is a `ByRef` parameter, the new total is reflected in the value of the argument in the calling code that corresponds to `debt`.</span></span> <span data-ttu-id="0bb78-147">`Calculate`에서 값을 변경 하면 안 되기 때문에 매개 변수 `rate` `ByVal` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="0bb78-147">Parameter `rate` is a `ByVal` parameter because `Calculate` should not change its value.</span></span>  
  
### <a name="code"></a><span data-ttu-id="0bb78-148">코드</span><span class="sxs-lookup"><span data-stu-id="0bb78-148">Code</span></span>  
 [!code-vb[VbVbcnProcedures#74](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class2.vb#74)]  
  
## <a name="see-also"></a><span data-ttu-id="0bb78-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0bb78-149">See also</span></span>

- [<span data-ttu-id="0bb78-150">절차</span><span class="sxs-lookup"><span data-stu-id="0bb78-150">Procedures</span></span>](./index.md)
- [<span data-ttu-id="0bb78-151">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="0bb78-151">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="0bb78-152">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="0bb78-152">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="0bb78-153">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="0bb78-153">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="0bb78-154">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="0bb78-154">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="0bb78-155">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="0bb78-155">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="0bb78-156">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="0bb78-156">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="0bb78-157">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="0bb78-157">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
