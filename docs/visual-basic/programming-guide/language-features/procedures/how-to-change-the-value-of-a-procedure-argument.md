---
description: '자세히 알아보기: 방법: 프로시저 인수의 값 변경 (Visual Basic)'
title: '방법: 프로시저 인수의 값 변경'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], parameters
- procedure arguments
- arguments [Visual Basic], passing by reference
- Visual Basic code, procedures
- arguments [Visual Basic], ByVal
- arguments [Visual Basic], passing by value
- procedure parameters
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: 6fad2368-5da7-4c07-8bf8-0f4e65a1be67
ms.openlocfilehash: f8ccc80f7a9cb5d2b090fbc6b7f7e3423e5a1cae
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472581"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="b4779-103">방법: 프로시저 인수의 값 변경(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b4779-103">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>

<span data-ttu-id="b4779-104">프로시저를 호출할 때 사용자가 제공 하는 각 인수는 프로시저에 정의 된 매개 변수 중 하나에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-104">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="b4779-105">경우에 따라 프로시저 코드는 호출 코드에서 인수의 내부 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-105">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="b4779-106">다른 경우에는 프로시저에서 인수의 로컬 복사본만 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-106">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="b4779-107">프로시저를 호출 하면 Visual Basic는 [ByVal](../../../language-reference/modifiers/byval.md)로 전달 되는 모든 인수의 로컬 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-107">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="b4779-108">[ByRef](../../../language-reference/modifiers/byref.md)를 전달 하는 각 인수에 대해 Visual Basic은 호출 코드에서 인수를 기본으로 하는 프로그래밍 요소에 대 한 직접 참조를 프로시저 코드에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-108">For each argument passed [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="b4779-109">호출 하는 코드의 기본 요소가 수정 가능한 요소이 고 인수가 전달 되 면 `ByRef` 프로시저 코드는 직접 참조를 사용 하 여 호출 코드에서 요소의 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-109">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="b4779-110">내부 값 변경</span><span class="sxs-lookup"><span data-stu-id="b4779-110">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="b4779-111">호출 코드에서 프로시저 인수의 내부 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="b4779-111">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1. <span data-ttu-id="b4779-112">프로시저 선언에서 인수에 해당 하는 매개 변수에 대해 [ByRef](../../../language-reference/modifiers/byref.md) 를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-112">In the procedure declaration, specify [ByRef](../../../language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2. <span data-ttu-id="b4779-113">호출 코드에서 수정 가능한 프로그래밍 요소를 인수로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-113">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3. <span data-ttu-id="b4779-114">호출 코드에서 인수를 인수 목록에 괄호로 묶지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b4779-114">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4. <span data-ttu-id="b4779-115">프로시저 코드에서 매개 변수 이름을 사용 하 여 호출 코드의 기본 요소에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-115">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="b4779-116">데모를 보려면 아래 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b4779-116">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="b4779-117">로컬 복사본 변경</span><span class="sxs-lookup"><span data-stu-id="b4779-117">Changing Local Copies</span></span>  

 <span data-ttu-id="b4779-118">호출 코드의 내부 요소가 수정할 수 없는 요소 이거나 인수가 전달 된 경우 `ByVal` 프로시저는 호출 코드에서 해당 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-118">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="b4779-119">그러나 프로시저는 이러한 인수의 로컬 복사본을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-119">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="b4779-120">프로시저 코드에서 프로시저 인수의 복사본을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="b4779-120">To change the copy of a procedure argument in the procedure code</span></span>  
  
1. <span data-ttu-id="b4779-121">프로시저 선언에서 인수에 해당 하는 매개 변수에 대해 [ByVal](../../../language-reference/modifiers/byval.md) 을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-121">In the procedure declaration, specify [ByVal](../../../language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="b4779-122">또는</span><span class="sxs-lookup"><span data-stu-id="b4779-122">-or-</span></span>  
  
     <span data-ttu-id="b4779-123">호출 코드에서 인수를 인수 목록에 괄호로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-123">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="b4779-124">이렇게 하면 해당 매개 변수가를 지정 하는 경우에도 인수를 값으로 전달 Visual Basic `ByRef` .</span><span class="sxs-lookup"><span data-stu-id="b4779-124">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2. <span data-ttu-id="b4779-125">프로시저 코드에서 매개 변수 이름을 사용 하 여 인수의 로컬 복사본에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-125">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="b4779-126">호출 코드의 내부 값은 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-126">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b4779-127">예</span><span class="sxs-lookup"><span data-stu-id="b4779-127">Example</span></span>  

 <span data-ttu-id="b4779-128">다음 예제에서는 배열 변수를 사용 하 고 해당 요소에 대해 작동 하는 두 개의 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-128">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="b4779-129">`increase`프로시저는 각 요소에 하나씩만 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-129">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="b4779-130">`replace`프로시저는 매개 변수에 새 배열을 할당 한 `a()` 다음 각 요소에 하나를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-130">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="b4779-131">첫 번째 `MsgBox` 호출은 "증가 (n): 11, 21, 31, 41"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-131">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="b4779-132">배열은 `n` 참조 형식 이므로는 `replace` 전달 메커니즘이 인 경우에도 해당 멤버를 변경할 수 있습니다 `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="b4779-132">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="b4779-133">두 번째 `MsgBox` 호출은 "Replace After (n): 101, 201, 301"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-133">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="b4779-134">가 전달 되기 때문에는 `n` `ByRef` `replace` 호출 코드에서 변수를 수정 하 `n` 고 여기에 새 배열을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-134">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="b4779-135">`n`가 참조 형식이 기 때문에 `replace` 도 해당 멤버를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-135">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="b4779-136">프로시저에서 호출 코드의 변수 자체를 수정 하는 것을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-136">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="b4779-137">[방법: 값 변경에 대해 프로시저 인수 보호를](./how-to-protect-a-procedure-argument-against-value-changes.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b4779-137">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="b4779-138">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="b4779-138">Compile the code</span></span>  

 <span data-ttu-id="b4779-139">변수를 참조로 전달 하는 경우 키워드를 사용 `ByRef` 하 여이 메커니즘을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-139">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="b4779-140">Visual Basic의 기본값은 인수를 값으로 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-140">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="b4779-141">그러나 선언 된 모든 매개 변수와 함께 [ByVal](../../../language-reference/modifiers/byval.md) 또는 [ByRef](../../../language-reference/modifiers/byref.md) 키워드를 포함 하는 것이 좋은 프로그래밍 습관입니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-141">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="b4779-142">이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-142">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="b4779-143">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="b4779-143">.NET Framework Security</span></span>  

 <span data-ttu-id="b4779-144">프로시저에서 호출 코드의 인수를 기반으로 하는 값을 변경 하는 것이 항상 발생할 수 있는 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-144">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="b4779-145">이 값을 변경 하 고이 값을 사용 하기 전에 유효성 검사를 수행할 준비를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4779-145">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4779-146">추가 정보</span><span class="sxs-lookup"><span data-stu-id="b4779-146">See also</span></span>

- [<span data-ttu-id="b4779-147">절차</span><span class="sxs-lookup"><span data-stu-id="b4779-147">Procedures</span></span>](./index.md)
- [<span data-ttu-id="b4779-148">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="b4779-148">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="b4779-149">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="b4779-149">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="b4779-150">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="b4779-150">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="b4779-151">수정할 수 있는 인수와 수정할 수 없는 인수의 차이점</span><span class="sxs-lookup"><span data-stu-id="b4779-151">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="b4779-152">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="b4779-152">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="b4779-153">방법: 값 변경으로부터 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="b4779-153">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="b4779-154">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="b4779-154">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="b4779-155">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="b4779-155">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="b4779-156">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="b4779-156">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
