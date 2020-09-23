---
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
ms.openlocfilehash: 84eadf3d364b69120221d80e464b1175b1602e13
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071484"
---
# <a name="how-to-protect-a-procedure-argument-against-value-changes-visual-basic"></a><span data-ttu-id="5577b-102">방법: 값 변경에 대해 프로시저 인수 보호(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5577b-102">How to: Protect a Procedure Argument Against Value Changes (Visual Basic)</span></span>

<span data-ttu-id="5577b-103">프로시저에서 매개 변수를 [ByRef](../../../language-reference/modifiers/byref.md)로 선언 하는 경우 Visual Basic은 호출 코드에서 인수를 기반으로 하는 프로그래밍 요소에 대 한 직접 참조를 프로시저 코드에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-103">If a procedure declares a parameter as [ByRef](../../../language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span> <span data-ttu-id="5577b-104">이렇게 하면 프로시저에서 호출 코드의 내부 인수 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-104">This permits the procedure to change the value underlying the argument in the calling code.</span></span> <span data-ttu-id="5577b-105">경우에 따라 호출 코드가 이러한 변경을 방지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-105">In some cases the calling code might want to protect against such a change.</span></span>  
  
 <span data-ttu-id="5577b-106">프로시저에서 해당 하는 매개 변수 [ByVal](../../../language-reference/modifiers/byval.md) 을 선언 하 여 인수를 변경 으로부터 항상 보호할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-106">You can always protect an argument from change by declaring the corresponding parameter [ByVal](../../../language-reference/modifiers/byval.md) in the procedure.</span></span> <span data-ttu-id="5577b-107">일부 경우에는 지정 된 인수를 변경할 수 있지만 다른 경우에는 변경할 수 없는 경우에는 해당 인수를 선언 `ByRef` 하 고 호출 코드가 각 호출에서 전달 메커니즘을 결정 하도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-107">If you want to be able to change a given argument in some cases but not others, you can declare it `ByRef` and let the calling code determine the passing mechanism in each call.</span></span> <span data-ttu-id="5577b-108">이를 위해 해당 인수를 괄호로 묶어 값으로 전달 하거나, 참조로 전달 하기 위해 괄호로 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-108">It does this by enclosing the corresponding argument in parentheses to pass it by value, or not enclosing it in parentheses to pass it by reference.</span></span> <span data-ttu-id="5577b-109">자세한 내용은 [방법: 인수를 값으로 전달](./how-to-force-an-argument-to-be-passed-by-value.md)하는 방법을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5577b-109">For more information, see [How to: Force an Argument to Be Passed by Value](./how-to-force-an-argument-to-be-passed-by-value.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="5577b-110">예제</span><span class="sxs-lookup"><span data-stu-id="5577b-110">Example</span></span>  

 <span data-ttu-id="5577b-111">다음 예제에서는 배열 변수를 사용 하 고 해당 요소에 대해 작동 하는 두 개의 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-111">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="5577b-112">`increase`프로시저는 각 요소에 하나씩만 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-112">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="5577b-113">`replace`프로시저는 매개 변수에 새 배열을 할당 한 `a()` 다음 각 요소에 하나를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-113">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="5577b-114">그러나 다시 할당 해도 호출 코드의 기본 배열 변수에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-114">However, the reassignment does not affect the underlying array variable in the calling code.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="5577b-115">첫 번째 `MsgBox` 호출은 "증가 (n): 11, 21, 31, 41"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-115">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="5577b-116">배열은 `n` 참조 형식 이므로는 `increase` 전달 메커니즘이 인 경우에도 해당 멤버를 변경할 수 있습니다 `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="5577b-116">Because the array `n` is a reference type, `increase` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="5577b-117">두 번째 `MsgBox` 호출은 "Replace After (n): 11, 21, 31, 41"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-117">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="5577b-118">가 전달 되기 때문에는 `n` `ByVal` `replace` `n` 새 배열을 할당 하 여 호출 코드에서 변수를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-118">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` in the calling code by assigning a new array to it.</span></span> <span data-ttu-id="5577b-119">에서 `replace` 새 배열 인스턴스를 만들고 `k` 지역 변수에 할당 하면 `a` 호출 코드에서 전달 하는 참조가 손실 `n` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-119">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="5577b-120">의 멤버를 변경 하면 `a` 로컬 배열에만 영향을 `k` 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-120">When it changes the members of `a`, only the local array `k` is affected.</span></span> <span data-ttu-id="5577b-121">따라서은 `replace` 호출 코드에서 배열 값을 증가 `n` 시 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-121">Therefore, `replace` does not increment the values of array `n` in the calling code.</span></span>  
  
## <a name="compile-the-code"></a><span data-ttu-id="5577b-122">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="5577b-122">Compile the code</span></span>  

 <span data-ttu-id="5577b-123">Visual Basic의 기본값은 인수를 값으로 전달 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-123">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="5577b-124">그러나 선언 된 모든 매개 변수와 함께 [ByVal](../../../language-reference/modifiers/byval.md) 또는 [ByRef](../../../language-reference/modifiers/byref.md) 키워드를 포함 하는 것이 좋은 프로그래밍 습관입니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-124">However, it is good programming practice to include either the [ByVal](../../../language-reference/modifiers/byval.md) or [ByRef](../../../language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="5577b-125">이렇게 하면 코드를 보다 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5577b-125">This makes your code easier to read.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5577b-126">참조</span><span class="sxs-lookup"><span data-stu-id="5577b-126">See also</span></span>

- [<span data-ttu-id="5577b-127">절차</span><span class="sxs-lookup"><span data-stu-id="5577b-127">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5577b-128">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="5577b-128">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5577b-129">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="5577b-129">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="5577b-130">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="5577b-130">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="5577b-131">수정할 수 있는 인수와 수정할 수 없는 인수의 차이점</span><span class="sxs-lookup"><span data-stu-id="5577b-131">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="5577b-132">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="5577b-132">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="5577b-133">방법: 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="5577b-133">How to: Change the Value of a Procedure Argument</span></span>](./how-to-change-the-value-of-a-procedure-argument.md)
- [<span data-ttu-id="5577b-134">방법: 인수가 값으로 전달되도록 설정</span><span class="sxs-lookup"><span data-stu-id="5577b-134">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="5577b-135">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="5577b-135">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="5577b-136">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="5577b-136">Value Types and Reference Types</span></span>](../data-types/value-types-and-reference-types.md)
