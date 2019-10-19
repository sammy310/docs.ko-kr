---
title: For...Next 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Step
- vb.Next
- vb.To
- vb.for
helpviewer_keywords:
- infinite loops
- Next keyword [Visual Basic], For...Next statements
- For keyword [Visual Basic], For...Next statements
- Step keyword [Visual Basic], For...Next statements
- operator overloading, For...Next statement
- To keyword [Visual Basic], For...Next statements
- endless loops
- loops, endless
- instructions, repeating
- Next statement [Visual Basic], For...Next
- For...Next statements
- loop structures [Visual Basic], For...Next
- loops, infinite
- Exit statement [Visual Basic], For...Next statements
- For statement [Visual Basic]
ms.assetid: f5fc0d51-67ce-4c36-9f09-31c9a91c94e9
ms.openlocfilehash: a60293fc837b6d12810a211892c391f24a46d4e6
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72582958"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="8dc81-102">For...Next 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8dc81-102">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="8dc81-103">지정 된 횟수 만큼 문 그룹을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-103">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="8dc81-104">구문</span><span class="sxs-lookup"><span data-stu-id="8dc81-104">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="8dc81-105">요소</span><span class="sxs-lookup"><span data-stu-id="8dc81-105">Parts</span></span>

|<span data-ttu-id="8dc81-106">파트</span><span class="sxs-lookup"><span data-stu-id="8dc81-106">Part</span></span>|<span data-ttu-id="8dc81-107">설명</span><span class="sxs-lookup"><span data-stu-id="8dc81-107">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="8dc81-108">@No__t_0 문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-108">Required in the `For` statement.</span></span> <span data-ttu-id="8dc81-109">숫자 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-109">Numeric variable.</span></span> <span data-ttu-id="8dc81-110">루프의 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-110">The control variable for the loop.</span></span> <span data-ttu-id="8dc81-111">자세한 내용은이 항목의 뒷부분에 나오는 [Counter 인수](#BKMK_Counter) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc81-111">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="8dc81-112">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8dc81-112">Optional.</span></span> <span data-ttu-id="8dc81-113">@No__t_0 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-113">Data type of `counter`.</span></span> <span data-ttu-id="8dc81-114">자세한 내용은이 항목의 뒷부분에 나오는 [Counter 인수](#BKMK_Counter) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc81-114">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="8dc81-115">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8dc81-115">Required.</span></span> <span data-ttu-id="8dc81-116">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-116">Numeric expression.</span></span> <span data-ttu-id="8dc81-117">`counter`의 초기 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-117">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="8dc81-118">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8dc81-118">Required.</span></span> <span data-ttu-id="8dc81-119">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-119">Numeric expression.</span></span> <span data-ttu-id="8dc81-120">@No__t_0 최종 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-120">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="8dc81-121">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8dc81-121">Optional.</span></span> <span data-ttu-id="8dc81-122">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-122">Numeric expression.</span></span> <span data-ttu-id="8dc81-123">루프를 통해 매번 `counter` 증가 하는 양입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-123">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="8dc81-124">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8dc81-124">Optional.</span></span> <span data-ttu-id="8dc81-125">@No__t_0와 `Next` 사이에 있는 하나 이상의 문 (지정 된 횟수 만큼 실행)</span><span class="sxs-lookup"><span data-stu-id="8dc81-125">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="8dc81-126">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8dc81-126">Optional.</span></span> <span data-ttu-id="8dc81-127">제어를 다음 루프 반복으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-127">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="8dc81-128">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8dc81-128">Optional.</span></span> <span data-ttu-id="8dc81-129">@No__t_0 루프에서 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-129">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="8dc81-130">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8dc81-130">Required.</span></span> <span data-ttu-id="8dc81-131">@No__t_0 루프의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-131">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="8dc81-132">이 문에서는 `To` 키워드를 사용 하 여 카운터 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-132">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="8dc81-133">Select ...에서이 키워드를 사용할 수도 있습니다. [ Case 문과](../../../visual-basic/language-reference/statements/select-case-statement.md) 배열 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-133">You can also use this keyword in the [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="8dc81-134">배열 선언에 대 한 자세한 내용은 [Dim 문](../../../visual-basic/language-reference/statements/dim-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8dc81-134">For more information about array declarations, see [Dim Statement](../../../visual-basic/language-reference/statements/dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="8dc81-135">간단한 예</span><span class="sxs-lookup"><span data-stu-id="8dc81-135">Simple Examples</span></span>

<span data-ttu-id="8dc81-136">@No__t_0를 사용 합니다. 일련의 문 집합을 반복 하려는 경우에 `Next` 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-136">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="8dc81-137">다음 예제에서 `index` 변수는 1 값으로 시작 하 고 루프가 반복 될 때마다 증가 하 고 `index` 값이 5에 도달 하면 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-137">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="8dc81-138">다음 예제에서 `number` 변수는 2에서 시작 하 고 루프의 각 반복에서 0.25으로 감소 하 고 `number` 값이 0에 도달 하면 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-138">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="8dc81-139">@No__t_1의 `Step` 인수는 루프가 반복 될 때마다 0.25 값을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-139">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="8dc81-140">잠시 [... End While 문](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 또는 [Do ... Loop 문은](../../../visual-basic/language-reference/statements/do-loop-statement.md) 루프에서 문을 실행 하는 횟수를 미리 알 수 없는 경우에 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-140">A [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) or [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="8dc81-141">그러나 루프를 특정 횟수 만큼 실행 하려는 경우 `For` ... `Next` 루프를 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-141">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="8dc81-142">루프를 처음 시작할 때 반복 횟수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-142">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="8dc81-143">중첩 루프</span><span class="sxs-lookup"><span data-stu-id="8dc81-143">Nesting Loops</span></span>

<span data-ttu-id="8dc81-144">루프 하나를 다른 루프에 배치 하 여 `For` 루프를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-144">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="8dc81-145">다음 예제에서는 중첩 된 `For`를 보여 줍니다. 단계 값이 다른 구조체를 `Next` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-145">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="8dc81-146">외부 루프는 루프의 모든 반복에 대 한 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-146">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="8dc81-147">내부 루프는 루프의 모든 반복에 대해 루프 카운터 변수를 감소 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-147">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="8dc81-148">루프를 중첩 하는 경우 각 루프에 고유한 `counter` 변수가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-148">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="8dc81-149">서로 다른 종류의 제어 구조를 중첩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-149">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="8dc81-150">자세한 내용은 [중첩 컨트롤 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc81-150">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="8dc81-151">종료 및 계속</span><span class="sxs-lookup"><span data-stu-id="8dc81-151">Exit For and Continue For</span></span>

<span data-ttu-id="8dc81-152">@No__t_0 문은 즉시 `For`를 끝냅니다 `Next`</span><span class="sxs-lookup"><span data-stu-id="8dc81-152">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="8dc81-153">루프를 실행 하 고 제어를 `Next` 문 다음에 오는 문으로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-153">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="8dc81-154">@No__t_0 문은 루프의 다음 반복으로 제어를 즉시 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-154">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="8dc81-155">자세한 내용은 [Continue 문](../../../visual-basic/language-reference/statements/continue-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc81-155">For more information, see [Continue Statement](../../../visual-basic/language-reference/statements/continue-statement.md).</span></span>

<span data-ttu-id="8dc81-156">다음 예에서는 `Continue For` 및 `Exit For` 문을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-156">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="8dc81-157">@No__t_1에 원하는 수의 `Exit For` 문을 넣을 수 있습니다. `Next`</span><span class="sxs-lookup"><span data-stu-id="8dc81-157">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="8dc81-158">실행.</span><span class="sxs-lookup"><span data-stu-id="8dc81-158">loop.</span></span> <span data-ttu-id="8dc81-159">중첩 된 `For` 내에서 사용 하는 경우 `Next`</span><span class="sxs-lookup"><span data-stu-id="8dc81-159">When used within nested `For`…`Next`</span></span> <span data-ttu-id="8dc81-160">루프, `Exit For` 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-160">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="8dc81-161">`Exit For`은 일부 조건을 평가한 후에 자주 사용 됩니다 (예: `If` ... `Then` ... `Else` 구조체).</span><span class="sxs-lookup"><span data-stu-id="8dc81-161">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="8dc81-162">다음 조건에 `Exit For`를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-162">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="8dc81-163">계속 반복은 불필요 하거나 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-163">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="8dc81-164">잘못 된 값 또는 종료 요청은이 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-164">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="8dc81-165">@No__t_0 ... `Catch` ... `Finally` 문이 예외를 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-165">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="8dc81-166">@No__t_1 블록의 끝에 `Exit For`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-166">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="8dc81-167">무한 하거나 무한 한 횟수를 실행 하는 루프 인 무한 루프를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-167">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="8dc81-168">이러한 조건을 감지 하면 `Exit For`를 사용 하 여 루프를 이스케이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-168">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="8dc81-169">자세한 내용은 다음 [을 참조 하세요. Loop 문](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="8dc81-169">For more information, see [Do...Loop Statement](../../../visual-basic/language-reference/statements/do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="8dc81-170">기술 구현</span><span class="sxs-lookup"><span data-stu-id="8dc81-170">Technical Implementation</span></span>

<span data-ttu-id="8dc81-171">@No__t_0 하는 경우 ... `Next` 루프가 시작 되 고 Visual Basic `start`, `end` 및 `step` 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-171">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="8dc81-172">Visual Basic는 현재이 값을 평가한 다음 `counter`에 `start`를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-172">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="8dc81-173">문 블록을 실행 하기 전에 Visual Basic `counter`를 `end`와 비교 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-173">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="8dc81-174">@No__t_0 이미 `end` 값 보다 크거나 `step`가 음수인 경우 더 작은 경우 `For` 루프가 종료 되 고 `Next` 문 다음에 오는 문으로 제어가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-174">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="8dc81-175">그렇지 않으면 문 블록이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-175">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="8dc81-176">Visual Basic에서 `Next` 문을 발견할 때마다 `step`으로 `counter` 증가 하 고 `For` 문으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-176">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="8dc81-177">다시 `end` `counter`를 비교한 다음 결과에 따라 블록을 실행 하거나 루프를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-177">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="8dc81-178">이 프로세스는 `counter` `end` 전달 되거나 `Exit For` 문이 발생할 때까지 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-178">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="8dc81-179">@No__t_0가 `end`를 전달할 때까지 루프가 중지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-179">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="8dc81-180">@No__t_0 `end`와 같으면 루프가 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-180">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="8dc81-181">블록을 실행할지 여부를 결정 하는 비교는 `step`가 양수인 경우 `end`  <=  `counter` 하 고 `counter`가 음수인 경우  >=  `end` `step` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-181">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="8dc81-182">루프 내에서 `counter` 값을 변경 하는 경우 코드를 읽고 디버그 하기가 더 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-182">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="8dc81-183">@No__t_0, `end` 또는 `step` 값을 변경 해도 루프가 처음 입력 될 때 결정 된 반복 값에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-183">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="8dc81-184">루프를 중첩 하는 경우 컴파일러는 내부 수준의 `Next` 문 앞에 있는 외부 중첩 수준의 `Next` 문을 발견 하면 오류를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-184">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="8dc81-185">그러나 컴파일러는 모든 `Next` 문에서 `counter` 지정 하는 경우에만 이러한 중복 오류를 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-185">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="8dc81-186">Step 인수</span><span class="sxs-lookup"><span data-stu-id="8dc81-186">Step Argument</span></span>

<span data-ttu-id="8dc81-187">@No__t_0의 값은 양수 또는 음수일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-187">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="8dc81-188">이 매개 변수는 다음 표에 따라 루프 처리를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-188">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="8dc81-189">**단계 값**</span><span class="sxs-lookup"><span data-stu-id="8dc81-189">**Step value**</span></span>|<span data-ttu-id="8dc81-190">**루프 실행**</span><span class="sxs-lookup"><span data-stu-id="8dc81-190">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="8dc81-191">양수 또는 0</span><span class="sxs-lookup"><span data-stu-id="8dc81-191">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="8dc81-192">음수</span><span class="sxs-lookup"><span data-stu-id="8dc81-192">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="8dc81-193">@No__t_0 기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-193">The default value of `step` is 1.</span></span>

### <a name="BKMK_Counter"></a><span data-ttu-id="8dc81-194">Counter 인수</span><span class="sxs-lookup"><span data-stu-id="8dc81-194">Counter Argument</span></span>

<span data-ttu-id="8dc81-195">다음 표에서는 `counter` 전체 `For…Next` 루프로 범위가 지정 된 새 지역 변수를 정의할 지 여부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-195">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="8dc81-196">이러한 결정은 `datatype` 있는지 여부와 `counter` 이미 정의 되어 있는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-196">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="8dc81-197">@No__t_0 제공 되나요?</span><span class="sxs-lookup"><span data-stu-id="8dc81-197">Is `datatype` present?</span></span>|<span data-ttu-id="8dc81-198">@No__t_0 이미 정의 되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="8dc81-198">Is `counter` already defined?</span></span>|<span data-ttu-id="8dc81-199">Result (`counter`에서 전체 `For...Next` 루프로 범위가 지정 된 새 지역 변수를 정의 하는지 여부)</span><span class="sxs-lookup"><span data-stu-id="8dc81-199">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="8dc81-200">아니요</span><span class="sxs-lookup"><span data-stu-id="8dc81-200">No</span></span>|<span data-ttu-id="8dc81-201">예</span><span class="sxs-lookup"><span data-stu-id="8dc81-201">Yes</span></span>|<span data-ttu-id="8dc81-202">아니요. `counter` 이미 정의 되어 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-202">No, because `counter` is already defined.</span></span> <span data-ttu-id="8dc81-203">@No__t_0 범위가 프로시저에 로컬인 경우 컴파일 타임 경고가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-203">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="8dc81-204">아니요</span><span class="sxs-lookup"><span data-stu-id="8dc81-204">No</span></span>|<span data-ttu-id="8dc81-205">아니요</span><span class="sxs-lookup"><span data-stu-id="8dc81-205">No</span></span>|<span data-ttu-id="8dc81-206">예.</span><span class="sxs-lookup"><span data-stu-id="8dc81-206">Yes.</span></span> <span data-ttu-id="8dc81-207">데이터 형식은 `start`, `end` 및 `step` 식에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-207">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="8dc81-208">형식 유추에 대 한 자세한 내용은 [Option 유추 문](../../../visual-basic/language-reference/statements/option-infer-statement.md) 및 [지역 형식 유추](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8dc81-208">For information about type inference, see [Option Infer Statement](../../../visual-basic/language-reference/statements/option-infer-statement.md) and [Local Type Inference](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="8dc81-209">예</span><span class="sxs-lookup"><span data-stu-id="8dc81-209">Yes</span></span>|<span data-ttu-id="8dc81-210">예</span><span class="sxs-lookup"><span data-stu-id="8dc81-210">Yes</span></span>|<span data-ttu-id="8dc81-211">예, 하지만 기존 `counter` 변수가 프로시저 외부에서 정의 된 경우에만 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-211">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="8dc81-212">해당 변수는 분리 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-212">That variable remains separate.</span></span> <span data-ttu-id="8dc81-213">기존 `counter` 변수의 범위가 프로시저에 로컬인 경우 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-213">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="8dc81-214">예</span><span class="sxs-lookup"><span data-stu-id="8dc81-214">Yes</span></span>|<span data-ttu-id="8dc81-215">아니요</span><span class="sxs-lookup"><span data-stu-id="8dc81-215">No</span></span>|<span data-ttu-id="8dc81-216">예.</span><span class="sxs-lookup"><span data-stu-id="8dc81-216">Yes.</span></span>|

<span data-ttu-id="8dc81-217">@No__t_0 데이터 형식은 다음 형식 중 하나 여야 하는 반복의 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-217">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="8dc81-218">@No__t_0, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single` 또는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-218">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="8dc81-219">[Enum 문을](../../../visual-basic/language-reference/statements/enum-statement.md)사용 하 여 선언 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-219">An enumeration that you declare by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

- <span data-ttu-id="8dc81-220">`Object`입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-220">An `Object`.</span></span>

- <span data-ttu-id="8dc81-221">다음 연산자를 포함 하는 `T` 형식입니다. 여기서 `B`는 `Boolean` 식에서 사용할 수 있는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-221">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="8dc81-222">@No__t_1 문에서 `counter` 변수를 선택적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-222">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="8dc81-223">이 구문은 특히 `For` 루프가 중첩 된 경우 프로그램의 가독성을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-223">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="8dc81-224">해당 `For` 문에 표시 되는 변수를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-224">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="8dc81-225">@No__t_0, `end` 및 `step` 식은 `counter` 형식으로 확대 되는 모든 데이터 형식으로 계산 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-225">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="8dc81-226">@No__t_0에 사용자 정의 형식을 사용 하는 경우 `CType` 변환 연산자를 정의 하 여 `start`, `end` 또는 `step` 형식을 `counter` 형식으로 변환 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-226">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="8dc81-227">예제</span><span class="sxs-lookup"><span data-stu-id="8dc81-227">Example</span></span>

<span data-ttu-id="8dc81-228">다음 예제에서는 제네릭 목록에서 모든 요소를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-228">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="8dc81-229">[For Each ... 다음 문](../../../visual-basic/language-reference/statements/for-each-next-statement.md)에서 예제는 `For`을 보여 줍니다. 내림차순으로 반복 되는 `Next` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-229">Instead of a [For Each...Next Statement](../../../visual-basic/language-reference/statements/for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="8dc81-230">이 예제에서는 `removeAt` 메서드로 인해 제거 된 요소 뒤의 요소가 더 낮은 인덱스 값을 갖도록 하기 때문에이 기술을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-230">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="8dc81-231">예제</span><span class="sxs-lookup"><span data-stu-id="8dc81-231">Example</span></span>

<span data-ttu-id="8dc81-232">다음 예제에서는 [Enum 문을](../../../visual-basic/language-reference/statements/enum-statement.md)사용 하 여 선언 된 열거형을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-232">The following example iterates through an enumeration that's declared by using an [Enum Statement](../../../visual-basic/language-reference/statements/enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="8dc81-233">예제</span><span class="sxs-lookup"><span data-stu-id="8dc81-233">Example</span></span>

<span data-ttu-id="8dc81-234">다음 예제에서 문 매개 변수는 `+`, `-`, `>=` 및 `<=` 연산자에 대 한 연산자 오버 로드가 있는 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8dc81-234">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="8dc81-235">참조</span><span class="sxs-lookup"><span data-stu-id="8dc81-235">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="8dc81-236">루프 구조</span><span class="sxs-lookup"><span data-stu-id="8dc81-236">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="8dc81-237">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="8dc81-237">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
- [<span data-ttu-id="8dc81-238">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="8dc81-238">Do...Loop Statement</span></span>](../../../visual-basic/language-reference/statements/do-loop-statement.md)
- [<span data-ttu-id="8dc81-239">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="8dc81-239">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="8dc81-240">Exit 문</span><span class="sxs-lookup"><span data-stu-id="8dc81-240">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="8dc81-241">컬렉션</span><span class="sxs-lookup"><span data-stu-id="8dc81-241">Collections</span></span>](../../programming-guide/concepts/collections.md)
