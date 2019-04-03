---
title: '방법: (Visual Basic) 프로시저 인수의 값 변경'
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
ms.openlocfilehash: 6aee795fefe36c2ad19390c0ac6d1613b2199415
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58837502"
---
# <a name="how-to-change-the-value-of-a-procedure-argument-visual-basic"></a><span data-ttu-id="c93b7-102">방법: (Visual Basic) 프로시저 인수의 값 변경</span><span class="sxs-lookup"><span data-stu-id="c93b7-102">How to: Change the Value of a Procedure Argument (Visual Basic)</span></span>
<span data-ttu-id="c93b7-103">프로시저를 호출 하는 경우 각 인수를 제공 하는 프로시저에 정의 된 매개 변수 중 하나에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-103">When you call a procedure, each argument you supply corresponds to one of the parameters defined in the procedure.</span></span> <span data-ttu-id="c93b7-104">일부 경우에 프로시저 코드 호출 코드에서 인수를 기본 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-104">In some cases, the procedure code can change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="c93b7-105">절차는 다른 경우에만 인수로의 자체 로컬 복사본을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-105">In other cases, the procedure can change only its local copy of an argument.</span></span>  
  
 <span data-ttu-id="c93b7-106">Visual Basic 전달 되는 모든 인수의 로컬 복사본을 프로시저를 호출할 때 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-106">When you call the procedure, Visual Basic makes a local copy of every argument that is passed [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md).</span></span> <span data-ttu-id="c93b7-107">각 인수에 대 한 전달 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic 프로시저 코드에 호출 코드에서 인수를 기본 프로그래밍 요소에 대 한 직접 참조를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-107">For each argument passed [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md), Visual Basic gives the procedure code a direct reference to the programming element underlying the argument in the calling code.</span></span>  
  
 <span data-ttu-id="c93b7-108">호출 코드의 내부 요소를 수정할 수 있고 인수가 전달 하는 경우 `ByRef`, 프로시저 코드 호출 코드에서 요소 값을 변경 하는 직접 참조를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-108">If the underlying element in the calling code is a modifiable element and the argument is passed `ByRef`, the procedure code can use the direct reference to change the element's value in the calling code.</span></span>  
  
## <a name="changing-the-underlying-value"></a><span data-ttu-id="c93b7-109">기본 값을 변경</span><span class="sxs-lookup"><span data-stu-id="c93b7-109">Changing the Underlying Value</span></span>  
  
#### <a name="to-change-the-underlying-value-of-a-procedure-argument-in-the-calling-code"></a><span data-ttu-id="c93b7-110">프로시저 인수를 호출 하는 코드의 기본 값을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="c93b7-110">To change the underlying value of a procedure argument in the calling code</span></span>  
  
1.  <span data-ttu-id="c93b7-111">프로시저 선언에서 지정할 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 인수에 해당 하는 매개 변수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-111">In the procedure declaration, specify [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) for the parameter corresponding to the argument.</span></span>  
  
2.  <span data-ttu-id="c93b7-112">호출 코드에서 수정할 수 있는 프로그래밍 요소를 인수로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-112">In the calling code, pass a modifiable programming element as the argument.</span></span>  
  
3.  <span data-ttu-id="c93b7-113">호출 코드에서 인수 목록의 괄호 안에 인수를 묶지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-113">In the calling code, do not enclose the argument in parentheses in the argument list.</span></span>  
  
4.  <span data-ttu-id="c93b7-114">프로시저 코드에서 매개 변수 이름을 사용 하 여 호출 하는 코드의 내부 요소에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-114">In the procedure code, use the parameter name to assign a value to the underlying element in the calling code.</span></span>  
  
 <span data-ttu-id="c93b7-115">예제를 참조 하세요 데모를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-115">See the example further down for a demonstration.</span></span>  
  
## <a name="changing-local-copies"></a><span data-ttu-id="c93b7-116">로컬 복사본을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-116">Changing Local Copies</span></span>  
 <span data-ttu-id="c93b7-117">호출 코드의 내부 요소는 요소를 수정할 수 없는 경우 또는 인수가 전달 되 면 `ByVal`, 프로시저가 호출 코드에서 해당 값을 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-117">If the underlying element in the calling code is a nonmodifiable element, or if the argument is passed `ByVal`, the procedure cannot change its value in the calling code.</span></span> <span data-ttu-id="c93b7-118">그러나 프로시저는 이러한 인수의 자체 로컬 복사본을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-118">However, the procedure can change its local copy of such an argument.</span></span>  
  
#### <a name="to-change-the-copy-of-a-procedure-argument-in-the-procedure-code"></a><span data-ttu-id="c93b7-119">프로시저 코드에서 프로시저 인수의 복사본을 변경 하려면</span><span class="sxs-lookup"><span data-stu-id="c93b7-119">To change the copy of a procedure argument in the procedure code</span></span>  
  
1.  <span data-ttu-id="c93b7-120">프로시저 선언에서 지정할 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 인수에 해당 하는 매개 변수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-120">In the procedure declaration, specify [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) for the parameter corresponding to the argument.</span></span>  
  
     <span data-ttu-id="c93b7-121">또는</span><span class="sxs-lookup"><span data-stu-id="c93b7-121">-or-</span></span>  
  
     <span data-ttu-id="c93b7-122">호출 코드에서 인수 목록의 괄호 안에 인수를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-122">In the calling code, enclose the argument in parentheses in the argument list.</span></span> <span data-ttu-id="c93b7-123">해당 매개 변수를 지정 하는 경우에 Visual Basic에서 값으로 인수를 전달 합니다. 이렇게 하면 `ByRef`합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-123">This forces Visual Basic to pass the argument by value, even if the corresponding parameter specifies `ByRef`.</span></span>  
  
2.  <span data-ttu-id="c93b7-124">프로시저 코드에서 매개 변수 이름을 사용 하 여 로컬 복사본 인수에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-124">In the procedure code, use the parameter name to assign a value to the local copy of the argument.</span></span> <span data-ttu-id="c93b7-125">호출 코드에서 기본 값이 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-125">The underlying value in the calling code is not changed.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c93b7-126">예제</span><span class="sxs-lookup"><span data-stu-id="c93b7-126">Example</span></span>  
 <span data-ttu-id="c93b7-127">다음 예제에서는 요소를 사용 하는 배열 변수를 받아 두 프로시저를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-127">The following example shows two procedures that take an array variable and operate on its elements.</span></span> <span data-ttu-id="c93b7-128">`increase` 프로시저 단순히 각 요소에 1을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-128">The `increase` procedure simply adds one to each element.</span></span> <span data-ttu-id="c93b7-129">합니다 `replace` 프로시저 매개 변수는 새 배열을 할당 `a()` 다음 각 요소에 하나를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-129">The `replace` procedure assigns a new array to the parameter `a()` and then adds one to each element.</span></span>  
  
 [!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]  
  
 [!code-vb[VbVbcnProcedures#36](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#36)]  
  
 [!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]  
  
 <span data-ttu-id="c93b7-130">첫 번째 `MsgBox` 표시 호출 "increase(n) 후: 11, 21, 31, 41".</span><span class="sxs-lookup"><span data-stu-id="c93b7-130">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="c93b7-131">때문에 배열의 `n` 참조 형식인 `replace` 전달 메커니즘이 해당 멤버를 변경할 수 있습니다 `ByVal`합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-131">Because the array `n` is a reference type, `replace` can change its members, even though the passing mechanism is `ByVal`.</span></span>  
  
 <span data-ttu-id="c93b7-132">두 번째 `MsgBox` 표시 호출 "replace(n) 후: 101, 201, 301".</span><span class="sxs-lookup"><span data-stu-id="c93b7-132">The second `MsgBox` call displays "After replace(n): 101, 201, 301".</span></span> <span data-ttu-id="c93b7-133">때문에 `n` 전달 `ByRef`, `replace` 변수를 수정할 수 `n` 호출 코드에는 새 배열에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-133">Because `n` is passed `ByRef`, `replace` can modify the variable `n` in the calling code and assign a new array to it.</span></span> <span data-ttu-id="c93b7-134">때문에 `n` 참조 형식인 `replace` 해당 멤버를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-134">Because `n` is a reference type, `replace` can also change its members.</span></span>  
  
 <span data-ttu-id="c93b7-135">호출 코드에서 변수를 수정할 프로시저를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-135">You can prevent the procedure from modifying the variable itself in the calling code.</span></span> <span data-ttu-id="c93b7-136">[방법: 값 변경에 대해 프로시저 인수 보호](./how-to-protect-a-procedure-argument-against-value-changes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-136">See [How to: Protect a Procedure Argument Against Value Changes](./how-to-protect-a-procedure-argument-against-value-changes.md).</span></span>  
  
## <a name="compiling-the-code"></a><span data-ttu-id="c93b7-137">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="c93b7-137">Compiling the Code</span></span>  
 <span data-ttu-id="c93b7-138">참조로 변수를 전달 하는 경우 사용 해야는 `ByRef` 키워드가이 메커니즘을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-138">When you pass a variable by reference, you must use the `ByRef` keyword to specify this mechanism.</span></span>  
  
 <span data-ttu-id="c93b7-139">Visual Basic의 기본값인 값으로 인수 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-139">The default in Visual Basic is to pass arguments by value.</span></span> <span data-ttu-id="c93b7-140">그러나는 것이 좋은 프로그래밍 방법 중 하나를 포함 하는 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 또는 [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) 키워드 선언 된 모든 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-140">However, it is good programming practice to include either the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) or [ByRef](../../../../visual-basic/language-reference/modifiers/byref.md) keyword with every declared parameter.</span></span> <span data-ttu-id="c93b7-141">이렇게 하면 코드를 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-141">This makes your code easier to read.</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="c93b7-142">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="c93b7-142">.NET Framework Security</span></span>  
 <span data-ttu-id="c93b7-143">호출 코드에서 인수를 기본 값을 변경 하는 절차를 허용할 위험할은 항상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-143">There is always a potential risk in allowing a procedure to change the value underlying an argument in the calling code.</span></span> <span data-ttu-id="c93b7-144">원하는이 값이 변경 되 고 사용 하기 전에 유효성을 검사할 준비가 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c93b7-144">Make sure you expect this value to be changed, and be prepared to check it for validity before using it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93b7-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="c93b7-145">See also</span></span>

- [<span data-ttu-id="c93b7-146">절차</span><span class="sxs-lookup"><span data-stu-id="c93b7-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="c93b7-147">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="c93b7-147">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="c93b7-148">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="c93b7-148">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="c93b7-149">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="c93b7-149">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="c93b7-150">수정할 수 있는 인수와 수정할 수 없는 인수 사이의 차이점</span><span class="sxs-lookup"><span data-stu-id="c93b7-150">Differences Between Modifiable and Nonmodifiable Arguments</span></span>](./differences-between-modifiable-and-nonmodifiable-arguments.md)
- [<span data-ttu-id="c93b7-151">인수를 값으로 전달할 때와 참조로 전달할 때의 차이점</span><span class="sxs-lookup"><span data-stu-id="c93b7-151">Differences Between Passing an Argument By Value and By Reference</span></span>](./differences-between-passing-an-argument-by-value-and-by-reference.md)
- [<span data-ttu-id="c93b7-152">방법: 값 변경에 대해 프로시저 인수 보호</span><span class="sxs-lookup"><span data-stu-id="c93b7-152">How to: Protect a Procedure Argument Against Value Changes</span></span>](./how-to-protect-a-procedure-argument-against-value-changes.md)
- [<span data-ttu-id="c93b7-153">방법: 인수가 값으로 전달 되도록 설정</span><span class="sxs-lookup"><span data-stu-id="c93b7-153">How to: Force an Argument to Be Passed by Value</span></span>](./how-to-force-an-argument-to-be-passed-by-value.md)
- [<span data-ttu-id="c93b7-154">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="c93b7-154">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="c93b7-155">Value Types and Reference Types</span><span class="sxs-lookup"><span data-stu-id="c93b7-155">Value Types and Reference Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/value-types-and-reference-types.md)
