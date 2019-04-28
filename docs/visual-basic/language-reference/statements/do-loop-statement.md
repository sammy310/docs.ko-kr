---
title: Do...Loop 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Do
- vb.Loop
- vb.Until
helpviewer_keywords:
- conditional statements [Visual Basic], Do�Loop
- while statement [Visual Basic], Do...Loop
- execution [Visual Basic], conditional
- Do loops
- Until keyword [Visual Basic], Do...Loop statement
- Do...Loop statement
- instructions, repeating
- Do statement [Visual Basic]
- Exit statement [Visual Basic], in Do...Loop statements
- loop structures [Visual Basic], Do�Loop statements
- do-while statements [Visual Basic]
- loops, exiting
- Loop keyword [Visual Basic], Do...Loop statement
ms.assetid: 892f9096-b3e2-4aee-834d-83bc4e2c379d
ms.openlocfilehash: 3ff3d67f38f510b798da3e470de066cff1e98f29
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61638777"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="77973-102">Do...Loop 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="77973-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="77973-103">반복 하는 동안 문 블록을 한 `Boolean` 조건은 `True` 조건이 있을 때까지 또는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77973-104">구문</span><span class="sxs-lookup"><span data-stu-id="77973-104">Syntax</span></span>  
  
```  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
-or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="77973-105">요소</span><span class="sxs-lookup"><span data-stu-id="77973-105">Parts</span></span>  
  
|<span data-ttu-id="77973-106">용어</span><span class="sxs-lookup"><span data-stu-id="77973-106">Term</span></span>|<span data-ttu-id="77973-107">정의</span><span class="sxs-lookup"><span data-stu-id="77973-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="77973-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="77973-108">Required.</span></span> <span data-ttu-id="77973-109">정의의 시작을 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="77973-110">`Until`를 사용하는 경우를 제외하고는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-110">Required unless `Until` is used.</span></span> <span data-ttu-id="77973-111">될 때까지 루프 반복 `condition` 는 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="77973-112">`While`를 사용하는 경우를 제외하고는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-112">Required unless `While` is used.</span></span> <span data-ttu-id="77973-113">될 때까지 루프 반복 `condition` 는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="77973-114">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-114">Optional.</span></span> <span data-ttu-id="77973-115">`Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-115">`Boolean` expression.</span></span> <span data-ttu-id="77973-116">하는 경우 `condition` 됩니다 `Nothing`, Visual Basic로 처리 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="77973-117">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-117">Optional.</span></span> <span data-ttu-id="77973-118">While 또는 until 반복 되는 하나 이상의 문을 `condition` 는 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="77973-119">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-119">Optional.</span></span> <span data-ttu-id="77973-120">다음 반복으로 제어를 전송 합니다 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="77973-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-121">Optional.</span></span> <span data-ttu-id="77973-122">밖으로 제어를 전송 합니다 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="77973-123">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="77973-123">Required.</span></span> <span data-ttu-id="77973-124">정의 종료 합니다 `Do` 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77973-125">설명</span><span class="sxs-lookup"><span data-stu-id="77973-125">Remarks</span></span>  
 <span data-ttu-id="77973-126">사용 하 여를 `Do...Loop` 무한히 횟수: 조건이 충족 될 때까지 문 집합을 반복 하려는 경우 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="77973-127">문을 횟수 만큼 반복 하려는 경우는 [에 대 한 중... 다음 문을](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="77973-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="77973-128">사용할 수 있습니다 `While` 또는 `Until` 되도록 `condition`, 하지만 둘 다.</span><span class="sxs-lookup"><span data-stu-id="77973-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="77973-129">테스트할 수 있습니다 `condition` 시작 또는 루프의 끝에만 한 번입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="77973-130">테스트 하는 경우 `condition` 루프의 시작 부분에 (에 `Do` 문), 루프도 한 번 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77973-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="77973-131">루프의 끝에 테스트 하는 경우 (에 `Loop` 문), 루프는 항상 한 번 이상 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="77973-132">계산 되는 식일 수 있지만 조건 두 값의 비교에서 일반적으로 결과 [Boolean 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`).</span><span class="sxs-lookup"><span data-stu-id="77973-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="77973-133">여기에 값을 변환 된 숫자 형식과 같은 다른 데이터 형식의 `Boolean`합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="77973-134">중첩할 수 있습니다 `Do` 루프 내에서 다른 한 루프를 배치 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="77973-135">또한 다른 종류의 서로 다른 제어 구조를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77973-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="77973-136">자세한 내용은 [중첩 제어 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="77973-137">합니다 `Do...Loop` 구조 보다 더 많은 유연성을 제공 합니다 [하는 동안... End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 루프를 종료 여부를 결정할 수 있기 때문에 때 `condition` 더 이상 `True` 되거나 조건이 먼저 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="77973-138">테스트할 수도 있습니다 `condition` 루프의 끝 또는 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="77973-139">종료 안 함</span><span class="sxs-lookup"><span data-stu-id="77973-139">Exit Do</span></span>  
 <span data-ttu-id="77973-140">합니다 [종료 수행](../../../visual-basic/language-reference/statements/exit-statement.md) 문을 종료 하는 대체 방법을 제공할 수는 `Do…Loop`합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="77973-141">`Exit Do` 바로 뒤에 오는 문으로 제어를 전송 합니다 `Loop` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="77973-142">`Exit Do` 예를 몇 가지 조건을 계산 된 후에 자주 사용 됩니다는 `If...Then...Else` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="77973-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="77973-143">불필요 하거나 잘못 된 값 또는 종료 요청과 같은 반복을 계속할 수 있도록 하는 조건이 발견 되 면 루프를 종료 하려는 경우.</span><span class="sxs-lookup"><span data-stu-id="77973-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="77973-144">용도 중 하나 `Exit Do` 일으킬 수 있는 조건을 테스트 하는 *무한 루프*도 무한히 여러 번 실행 될 수 있는 루프는.</span><span class="sxs-lookup"><span data-stu-id="77973-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="77973-145">사용할 수 있습니다 `Exit Do` 루프를 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="77973-146">개수에 관계 없이 포함할 수 있습니다 `Exit Do` 어디서 나 문에서 `Do…Loop`합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="77973-147">사용 하는 경우 내에 중첩 `Do` 루프 `Exit Do` 다음 상위 수준의 중첩 및 가장 안쪽의 루프 밖으로 제어를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="77973-148">예제</span><span class="sxs-lookup"><span data-stu-id="77973-148">Example</span></span>  
 <span data-ttu-id="77973-149">다음 예제에서는 루프에서 문을 계속 실행 될 때까지 `index` 변수 10 보다 큽니다.</span><span class="sxs-lookup"><span data-stu-id="77973-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="77973-150">`Until` 루프의 끝에 절이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="77973-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="77973-151">예제</span><span class="sxs-lookup"><span data-stu-id="77973-151">Example</span></span>  
 <span data-ttu-id="77973-152">다음 예에서는 `While` 절 대신는 `Until` 절 및 `condition` 끝 대신 루프의 시작 부분에서 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="77973-153">예제</span><span class="sxs-lookup"><span data-stu-id="77973-153">Example</span></span>  
 <span data-ttu-id="77973-154">다음 예에서 `condition` 루프를 중지 때는 `index` 변수가 100을 초과 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="77973-155">그러나 `If` 루프에서 문을 사용 하면는 `Exit Do` 문의 인덱스 변수는 10 보다 큰 경우에 루프를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="77973-156">예제</span><span class="sxs-lookup"><span data-stu-id="77973-156">Example</span></span>  
 <span data-ttu-id="77973-157">다음 예제에서는 텍스트 파일에 모든 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="77973-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="77973-158"><xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 반환을 <xref:System.IO.StreamReader> 문자를 읽고 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="77973-159">에 `Do...Loop` 조건을 <xref:System.IO.StreamReader.Peek%2A> 메서드는 `StreamReader` 추가 문자가 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="77973-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="77973-160">참고자료</span><span class="sxs-lookup"><span data-stu-id="77973-160">See also</span></span>

- [<span data-ttu-id="77973-161">루프 구조</span><span class="sxs-lookup"><span data-stu-id="77973-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="77973-162">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="77973-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="77973-163">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="77973-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="77973-164">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="77973-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="77973-165">Exit 문</span><span class="sxs-lookup"><span data-stu-id="77973-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="77973-166">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="77973-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
