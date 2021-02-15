---
description: '자세한 정보: 방법: 값 변경에 대해 프로시저 인수 보호 (Visual Basic)'
title: '방법: 값 변경으로부터 프로시저 인수 보호'
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
- procedures [Visual Basic], calling
- arguments [Visual Basic], ByRef
- arguments [Visual Basic], changing value
ms.assetid: d2b7c766-ce16-4d2c-8d79-3fc0e7ba2227
ms.openlocfilehash: 2e47a584632f124a001617770aeae5104ef20abe
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100476217"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="9f013-103">방법: 값 변경에 대해 프로시저 인수 보호(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9f013-103">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>

<span data-ttu-id="9f013-104">프로시저에서 매개 변수를 [ByRef](../../../language-reference/modifiers/byref.md)로 선언 하는 경우 Visual Basic은 호출 코드에서 인수를 기반으로 하는 프로그래밍 요소에 대 한 직접 참조를 프로시저 코드에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-104">If a procedure declares a parameter as [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="9f013-105">이렇게 하면 프로시저에서 호출 코드의 내부 인수 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-105">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="9f013-106">경우에 따라 호출 코드가 이러한 변경을 방지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-106">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="9f013-107">프로시저에서 해당 하는 매개 변수 [ByVal](../../../language-reference/modifiers/byval.md) 을 선언 하 여 인수를 변경 으로부터 항상 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-107">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="9f013-108">일부 경우에는 지정 된 인수를 변경할 수 있지만 다른 경우에는 변경할 수 없는 경우에는 해당 인수를 선언 `ByRef` 하 고 호출 코드가 각 호출에서 전달 메커니즘을 결정 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-108">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="9f013-109">이를 위해 해당 인수를 괄호로 묶어 값으로 전달 하거나, 참조로 전달 하기 위해 괄호로 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-109">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="9f013-110">자세한 내용은 [방법: 인수를 값으로 전달](./how-to-force-an-argument-to-be-passed-by-value.md)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f013-110">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="9f013-111">예</span><span class="sxs-lookup"><span data-stu-id="9f013-111">Example</span></span>  

 <span data-ttu-id="9f013-112">다음 예제에서는 배열 변수를 사용 하 고 해당 요소에 대해 작동 하는 두 개의 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-112">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="9f013-113">`increase`프로시저는 각 요소에 하나씩만 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-113">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="9f013-114">`replace`프로시저는 매개 변수에 새 배열을 할당 한 `a()` 다음 각 요소에 하나를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-114">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="9f013-115">그러나 다시 할당 해도 호출 코드의 기본 배열 변수에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-115">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="9f013-116">첫 번째 `MsgBox` 호출은 "증가 (n): 11, 21, 31, 41"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-116">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="9f013-117">배열은 `n` 참조 형식 이므로는 `increase` 전달 메커니즘이 인 경우에도 해당 멤버를 변경할 수 있습니다 `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="9f013-117">Because the array `n` is a reference type, `increase` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="9f013-118">두 번째 `MsgBox` 호출은 "Replace After (n): 11, 21, 31, 41"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-118">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="9f013-119">가 전달 되기 때문에는 `n` `ByVal` `replace` `n` 새 배열을 할당 하 여 호출 코드에서 변수를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-119">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="9f013-120">에서 `replace` 새 배열 인스턴스를 만들고 `k` 지역 변수에 할당 하면 `a` 호출 코드에서 전달 하는 참조가 손실 `n` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-120">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="9f013-121">의 멤버를 변경 하면 `a` 로컬 배열에만 영향을 `k` 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-121">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="9f013-122">따라서은 `replace` 호출 코드에서 배열 값을 증가 `n` 시 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-122">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="9f013-123">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="9f013-123">Compile the code</span></span>  

 <span data-ttu-id="9f013-124">Visual Basic의 기본값은 인수를 값으로 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-124">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="9f013-125">그러나 선언 된 모든 매개 변수와 함께 [ByVal](../../../language-reference/modifiers/byval.md) 또는 [ByRef](../../../language-reference/modifiers/byref.md) 키워드를 포함 하는 것이 좋은 프로그래밍 습관입니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-125">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="9f013-126">이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f013-126">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f013-127">추가 정보</span><span class="sxs-lookup"><span data-stu-id="9f013-127">See also</span></span>

- [<span data-ttu-id="9f013-128">절차</span><span class="sxs-lookup"><span data-stu-id="9f013-128">Procedures</span></span>](./index.md)
- [<span data-ttu-id="9f013-129">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="9f013-129">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="9f013-130">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="9f013-130">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="9f013-131">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="9f013-131">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="9f013-132">수정할 수 있는 인수와 수정할 수 없는 인수의 차이점</span><span class="sxs-lookup"><span data-stu-id="9f013-132">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="9f013-133">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="9f013-133">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="9f013-134">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="9f013-134">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="9f013-135">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="9f013-135">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="9f013-136">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="9f013-136">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="9f013-137">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="9f013-137">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
