---
description: 다음에 대해 자세히 알아보세요. 다음 문 (Visual Basic)
title: For...Next 문
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
ms.openlocfilehash: f26d9cb1885d9d22b96d622f44325aad64e34d1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99769080"
---
# <a name="fornext-statement-visual-basic"></a><span data-ttu-id="add56-103">For...Next 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="add56-103">For...Next Statement (Visual Basic)</span></span>

<span data-ttu-id="add56-104">지정 된 횟수 만큼 문 그룹을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-104">Repeats a group of statements a specified number of times.</span></span>

## <a name="syntax"></a><span data-ttu-id="add56-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="add56-105">Syntax</span></span>

```vb
For counter [ As datatype ] = start To end [ Step step ]
    [ statements ]
    [ Continue For ]
    [ statements ]
    [ Exit For ]
    [ statements ]
Next [ counter ]
```

## <a name="parts"></a><span data-ttu-id="add56-106">부분</span><span class="sxs-lookup"><span data-stu-id="add56-106">Parts</span></span>

|<span data-ttu-id="add56-107">파트</span><span class="sxs-lookup"><span data-stu-id="add56-107">Part</span></span>|<span data-ttu-id="add56-108">설명</span><span class="sxs-lookup"><span data-stu-id="add56-108">Description</span></span>|
|----------|-----------------|
|`counter`|<span data-ttu-id="add56-109">`For`문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-109">Required in the `For` statement.</span></span> <span data-ttu-id="add56-110">숫자 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-110">Numeric variable.</span></span> <span data-ttu-id="add56-111">루프의 제어 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-111">The control variable for the loop.</span></span> <span data-ttu-id="add56-112">자세한 내용은이 항목의 뒷부분에 나오는 [Counter 인수](#BKMK_Counter) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="add56-112">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`datatype`|<span data-ttu-id="add56-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-113">Optional.</span></span> <span data-ttu-id="add56-114">의 데이터 형식 `counter` 입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-114">Data type of `counter`.</span></span> <span data-ttu-id="add56-115">자세한 내용은이 항목의 뒷부분에 나오는 [Counter 인수](#BKMK_Counter) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="add56-115">For more information, see [Counter Argument](#BKMK_Counter) later in this topic.</span></span>|
|`start`|<span data-ttu-id="add56-116">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="add56-116">Required.</span></span> <span data-ttu-id="add56-117">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-117">Numeric expression.</span></span> <span data-ttu-id="add56-118">`counter`의 초기 값입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-118">The initial value of `counter`.</span></span>|
|`end`|<span data-ttu-id="add56-119">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="add56-119">Required.</span></span> <span data-ttu-id="add56-120">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-120">Numeric expression.</span></span> <span data-ttu-id="add56-121">의 최종 값입니다 `counter` .</span><span class="sxs-lookup"><span data-stu-id="add56-121">The final value of `counter`.</span></span>|
|`step`|<span data-ttu-id="add56-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-122">Optional.</span></span> <span data-ttu-id="add56-123">숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-123">Numeric expression.</span></span> <span data-ttu-id="add56-124">루프를 통해 매번 증가 하는 크기입니다 `counter` .</span><span class="sxs-lookup"><span data-stu-id="add56-124">The amount by which `counter` is incremented each time through the loop.</span></span>|
|`statements`|<span data-ttu-id="add56-125">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-125">Optional.</span></span> <span data-ttu-id="add56-126">`For`에서 `Next` 지정 된 횟수 만큼 실행 하는 하나 이상의 문입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-126">One or more statements between `For` and `Next` that run the specified number of times.</span></span>|
|`Continue For`|<span data-ttu-id="add56-127">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-127">Optional.</span></span> <span data-ttu-id="add56-128">제어를 다음 루프 반복으로 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-128">Transfers control to the next loop iteration.</span></span>|
|`Exit For`|<span data-ttu-id="add56-129">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-129">Optional.</span></span> <span data-ttu-id="add56-130">루프 외부로 제어를 전달 `For` 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-130">Transfers control out of the `For` loop.</span></span>|
|`Next`|<span data-ttu-id="add56-131">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-131">Required.</span></span> <span data-ttu-id="add56-132">루프의 정의를 종료 `For` 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-132">Terminates the definition of the `For` loop.</span></span>|

> [!NOTE]
> <span data-ttu-id="add56-133">`To`이 문에는 키워드를 사용 하 여 카운터의 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-133">The `To` keyword is used in this statement to specify the range for the counter.</span></span> <span data-ttu-id="add56-134">Select ...에서이 키워드를 사용할 수도 있습니다. [ Case 문과](select-case-statement.md) 배열 선언에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-134">You can also use this keyword in the [Select...Case Statement](select-case-statement.md) and in array declarations.</span></span> <span data-ttu-id="add56-135">배열 선언에 대 한 자세한 내용은 [Dim 문](dim-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="add56-135">For more information about array declarations, see [Dim Statement](dim-statement.md).</span></span>

## <a name="simple-examples"></a><span data-ttu-id="add56-136"> 간단한 예</span><span class="sxs-lookup"><span data-stu-id="add56-136">Simple Examples</span></span>

<span data-ttu-id="add56-137">`For` `Next` 설정 된 횟수 만큼 문 집합을 반복 하려면 ... 구조체를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-137">You use a `For`...`Next` structure when you want to repeat a set of statements a set number of times.</span></span>

<span data-ttu-id="add56-138">다음 예제에서 `index` 변수는 값이 1로 시작 하 고 루프가 반복 될 때마다 증가 하 고 값이 5에 도달 하면 끝납니다 `index` .</span><span class="sxs-lookup"><span data-stu-id="add56-138">In the following example, the `index` variable starts with a value of 1 and is incremented with each iteration of the loop, ending after the value of `index` reaches 5.</span></span>

[!code-vb[VbVbalrStatements#111](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#111)]

<span data-ttu-id="add56-139">다음 예제에서 `number` 변수는 2에서 시작 하 고 루프의 각 반복에서 0.25으로 감소 하 고 값이 0에 도달 하면 끝납니다 `number` .</span><span class="sxs-lookup"><span data-stu-id="add56-139">In the following example, the `number` variable starts at 2 and is reduced by 0.25 on each iteration of the loop, ending after the value of `number` reaches 0.</span></span> <span data-ttu-id="add56-140">`Step`의 인수는 `-.25` 루프가 반복 될 때마다 0.25 값을 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-140">The `Step` argument of `-.25` reduces the value by 0.25 on each iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#112](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#112)]

> [!TIP]
> <span data-ttu-id="add56-141">잠시 [... End While 문](while-end-while-statement.md) 또는 [Do ... Loop 문은](do-loop-statement.md) 루프에서 문을 실행 하는 횟수를 미리 알 수 없는 경우에 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-141">A [While...End While Statement](while-end-while-statement.md) or [Do...Loop Statement](do-loop-statement.md) works well when you don't know in advance how many times to run the statements in the loop.</span></span> <span data-ttu-id="add56-142">그러나 루프를 특정 횟수 만큼 실행 하려는 경우 `For` ... 루프를 선택 하는 `Next` 것이 더 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-142">However, when you expect to run the loop a specific number of times, a `For`...`Next` loop is a better choice.</span></span> <span data-ttu-id="add56-143">루프를 처음 시작할 때 반복 횟수를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-143">You determine the number of iterations when you first enter the loop.</span></span>

## <a name="nesting-loops"></a><span data-ttu-id="add56-144">중첩 루프</span><span class="sxs-lookup"><span data-stu-id="add56-144">Nesting Loops</span></span>

<span data-ttu-id="add56-145">`For`루프 하나를 다른 루프에 배치 하 여 루프를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-145">You can nest `For` loops by putting one loop within another.</span></span> <span data-ttu-id="add56-146">다음 예제에서는 `For` `Next` 단계 값이 다른 중첩 된 ... 구조체를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="add56-146">The following example demonstrates nested `For`...`Next` structures that have different step values.</span></span> <span data-ttu-id="add56-147">외부 루프는 루프의 모든 반복에 대 한 문자열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="add56-147">The outer loop creates a string for every iteration of the loop.</span></span> <span data-ttu-id="add56-148">내부 루프는 루프의 모든 반복에 대해 루프 카운터 변수를 감소 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="add56-148">The inner loop decrements a loop counter variable for every iteration of the loop.</span></span>

[!code-vb[VbVbalrStatements#113](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#113)]

<span data-ttu-id="add56-149">루프를 중첩할 때 각 루프에는 고유한 변수가 있어야 합니다 `counter` .</span><span class="sxs-lookup"><span data-stu-id="add56-149">When nesting loops, each loop must have a unique `counter` variable.</span></span>

<span data-ttu-id="add56-150">서로 다른 종류의 제어 구조를 중첩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-150">You can also nest different kinds control structures within each other.</span></span> <span data-ttu-id="add56-151">자세한 내용은 [중첩 컨트롤 구조](../../programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="add56-151">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>

## <a name="exit-for-and-continue-for"></a><span data-ttu-id="add56-152">종료 및 계속</span><span class="sxs-lookup"><span data-stu-id="add56-152">Exit For and Continue For</span></span>

<span data-ttu-id="add56-153">`Exit For`문이 바로 종료 `For` 됩니다.`Next`</span><span class="sxs-lookup"><span data-stu-id="add56-153">The `Exit For` statement immediately exits the `For`…`Next`</span></span> <span data-ttu-id="add56-154">루프를 실행 하 고 문 뒤의 문으로 제어를 전달 `Next` 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-154">loop and transfers control to the statement that follows the `Next` statement.</span></span>

<span data-ttu-id="add56-155">`Continue For`문은 루프의 다음 반복으로 제어를 즉시 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-155">The `Continue For` statement transfers control immediately to the next iteration of the loop.</span></span> <span data-ttu-id="add56-156">자세한 내용은 [Continue 문](continue-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="add56-156">For more information, see [Continue Statement](continue-statement.md).</span></span>

<span data-ttu-id="add56-157">다음 예제에서는 및 문을 사용 하는 방법을 보여 줍니다 `Continue For` `Exit For` .</span><span class="sxs-lookup"><span data-stu-id="add56-157">The following example illustrates the use of the `Continue For` and `Exit For` statements.</span></span>

[!code-vb[VbVbalrStatements#115](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#115)]

<span data-ttu-id="add56-158">에 원하는 수의 문을 추가할 수 있습니다. `Exit For` `For``Next`</span><span class="sxs-lookup"><span data-stu-id="add56-158">You can put any number of `Exit For` statements in a `For`…`Next`</span></span> <span data-ttu-id="add56-159">loop.</span><span class="sxs-lookup"><span data-stu-id="add56-159">loop.</span></span> <span data-ttu-id="add56-160">중첩 된 내에서 사용 하는 `For` 경우 ...`Next`</span><span class="sxs-lookup"><span data-stu-id="add56-160">When used within nested `For`…`Next`</span></span> <span data-ttu-id="add56-161">루프 `Exit For` 는 가장 안쪽의 루프를 종료 하 고 다음으로 높은 중첩 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-161">loops, `Exit For` exits the innermost loop and transfers control to the next higher level of nesting.</span></span>

<span data-ttu-id="add56-162">`Exit For` 는 일부 조건을 평가한 후에 사용 됩니다. 예 `If` `Then` 를 들어 ... ...`Else` 구조).</span><span class="sxs-lookup"><span data-stu-id="add56-162">`Exit For` is often used after you evaluate some condition (for example, in an `If`...`Then`...`Else` structure).</span></span> <span data-ttu-id="add56-163">다음 조건에 대해를 사용 하는 것이 좋습니다 `Exit For` .</span><span class="sxs-lookup"><span data-stu-id="add56-163">You might want to use `Exit For` for the following conditions:</span></span>

- <span data-ttu-id="add56-164">계속 반복은 불필요 하거나 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-164">Continuing to iterate is unnecessary or impossible.</span></span> <span data-ttu-id="add56-165">잘못 된 값 또는 종료 요청은이 조건을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-165">An erroneous value or a termination request might create this condition.</span></span>

- <span data-ttu-id="add56-166">... `Try` `Catch` ...`Finally` 문에서 예외를 catch 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-166">A `Try`...`Catch`...`Finally` statement catches an exception.</span></span> <span data-ttu-id="add56-167">`Exit For`블록의 끝에를 사용할 수 있습니다 `Finally` .</span><span class="sxs-lookup"><span data-stu-id="add56-167">You might use `Exit For` at the end of the `Finally` block.</span></span>

- <span data-ttu-id="add56-168">무한 하거나 무한 한 횟수를 실행 하는 루프 인 무한 루프를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-168">You have an endless loop, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="add56-169">이러한 조건을 감지한 경우를 사용 하 여 루프를 `Exit For` 이스케이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-169">If you detect such a condition, you can use `Exit For` to escape the loop.</span></span> <span data-ttu-id="add56-170">자세한 내용은 다음 [을 참조 하세요. Loop 문](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="add56-170">For more information, see [Do...Loop Statement](do-loop-statement.md).</span></span>

## <a name="technical-implementation"></a><span data-ttu-id="add56-171">기술 구현</span><span class="sxs-lookup"><span data-stu-id="add56-171">Technical Implementation</span></span>

<span data-ttu-id="add56-172">`For`... 루프가 시작 되 면 `Next` Visual Basic에서, 및를 `start` 계산 `end` `step` 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-172">When a `For`...`Next` loop starts, Visual Basic evaluates `start`, `end`, and `step`.</span></span> <span data-ttu-id="add56-173">Visual Basic는 현재이 값을 평가한 후 `start` 에를 할당 `counter` 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-173">Visual Basic evaluates these values only at this time and then assigns `start` to `counter`.</span></span> <span data-ttu-id="add56-174">문 블록을 실행 하기 전에 Visual Basic 비교 `counter` `end` 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-174">Before the statement block runs, Visual Basic compares `counter` to `end`.</span></span> <span data-ttu-id="add56-175">`counter`가 이미 값 보다 크거나 `end` 가 음수인 경우 더 작은 경우 `step` `For` 루프는 문 다음에 오는 문으로 종료 되 고 제어가 전달 됩니다 `Next` .</span><span class="sxs-lookup"><span data-stu-id="add56-175">If `counter` is already larger than the `end` value (or smaller if `step` is negative), the `For` loop ends and control passes to the statement that follows the `Next` statement.</span></span> <span data-ttu-id="add56-176">그렇지 않으면 문 블록이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add56-176">Otherwise, the statement block runs.</span></span>

<span data-ttu-id="add56-177">문이 발생할 때마다 Visual Basic `Next` 으로 증가 하 `counter` `step` 고 `For` 문으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="add56-177">Each time Visual Basic encounters the `Next` statement, it increments `counter` by `step` and returns to the `For` statement.</span></span> <span data-ttu-id="add56-178">다시 비교 하 `counter` 여 `end` 결과에 따라 블록을 실행 하거나 루프를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-178">Again it compares `counter` to `end`, and again it either runs the block or exits the loop, depending on the result.</span></span> <span data-ttu-id="add56-179">이 프로세스 `counter` `end` 는 성공 또는 `Exit For` 문이 발생할 때까지 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add56-179">This process continues until `counter` passes `end` or an `Exit For` statement is encountered.</span></span>

<span data-ttu-id="add56-180">루프는가 전달 될 때까지 중지 되지 않습니다 `counter` `end` .</span><span class="sxs-lookup"><span data-stu-id="add56-180">The loop doesn't stop until `counter` has passed `end`.</span></span> <span data-ttu-id="add56-181">`counter`가와 같으면 `end` 루프가 계속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add56-181">If `counter` is equal to `end`, the loop continues.</span></span> <span data-ttu-id="add56-182">블록을 실행할지 여부를 결정 하는 비교는가 `counter`  <=  `end` `step` 양수이 고 `counter`  >=  `end` `step` 가 음수인 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-182">The comparison that determines whether to run the block is `counter` <= `end` if `step` is positive and `counter` >= `end` if `step` is negative.</span></span>

<span data-ttu-id="add56-183">루프 내에서 값을 변경 하는 경우 `counter` 코드를 읽고 디버그 하는 것이 더 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-183">If you change the value of `counter` while inside a loop, your code might be more difficult to read and debug.</span></span> <span data-ttu-id="add56-184">, 또는 값을 변경 해도 `start` `end` `step` 루프가 처음 입력 될 때 결정 된 반복 값에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-184">Changing the value of `start`, `end`, or `step` doesn't affect the iteration values that were determined when the loop was first entered.</span></span>

<span data-ttu-id="add56-185">루프를 중첩 하는 경우 `Next` 내부 수준의 문 앞에 외부 중첩 수준의 문이 있으면 컴파일러가 오류를 표시 합니다 `Next` .</span><span class="sxs-lookup"><span data-stu-id="add56-185">If you nest loops, the compiler signals an error if it encounters the `Next` statement of an outer nesting level before the `Next` statement of an inner level.</span></span> <span data-ttu-id="add56-186">그러나 컴파일러는 모든 문에서를 지정 하는 경우에만 이러한 중복 오류를 감지할 수 있습니다 `counter` `Next` .</span><span class="sxs-lookup"><span data-stu-id="add56-186">However, the compiler can detect this overlapping error only if you specify `counter` in every `Next` statement.</span></span>

### <a name="step-argument"></a><span data-ttu-id="add56-187">Step 인수</span><span class="sxs-lookup"><span data-stu-id="add56-187">Step Argument</span></span>

<span data-ttu-id="add56-188">값은 `step` 양수 또는 음수일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="add56-188">The value of `step` can be either positive or negative.</span></span> <span data-ttu-id="add56-189">이 매개 변수는 다음 표에 따라 루프 처리를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-189">This parameter determines loop processing according to the following table:</span></span>

|<span data-ttu-id="add56-190">**단계 값**</span><span class="sxs-lookup"><span data-stu-id="add56-190">**Step value**</span></span>|<span data-ttu-id="add56-191">**루프 실행**</span><span class="sxs-lookup"><span data-stu-id="add56-191">**Loop executes if**</span></span>|
|--------------------|--------------------------|
|<span data-ttu-id="add56-192">양수 또는 0</span><span class="sxs-lookup"><span data-stu-id="add56-192">Positive or zero</span></span>|`counter` <= `end`|
|<span data-ttu-id="add56-193">음수</span><span class="sxs-lookup"><span data-stu-id="add56-193">Negative</span></span>|`counter` >= `end`|

<span data-ttu-id="add56-194">`step`의 기본값은 1입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-194">The default value of `step` is 1.</span></span>

### <a name="counter-argument"></a><a name="BKMK_Counter"></a> <span data-ttu-id="add56-195">Counter 인수</span><span class="sxs-lookup"><span data-stu-id="add56-195">Counter Argument</span></span>

<span data-ttu-id="add56-196">다음 표에서는가 `counter` 전체 루프로 범위가 지정 된 새 지역 변수를 정의 하는지 여부를 나타냅니다 `For…Next` .</span><span class="sxs-lookup"><span data-stu-id="add56-196">The following table indicates whether `counter` defines a new local variable that’s scoped to the entire `For…Next` loop.</span></span> <span data-ttu-id="add56-197">이러한 결정은가 있는지 여부 `datatype` 와 `counter` 가 이미 정의 되어 있는지 여부에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="add56-197">This determination depends on whether `datatype` is present and whether `counter` is already defined.</span></span>

|<span data-ttu-id="add56-198">`datatype`있나요?</span><span class="sxs-lookup"><span data-stu-id="add56-198">Is `datatype` present?</span></span>|<span data-ttu-id="add56-199">`counter`이미 정의 되어 있나요?</span><span class="sxs-lookup"><span data-stu-id="add56-199">Is `counter` already defined?</span></span>|<span data-ttu-id="add56-200">결과 ( `counter` 가 전체 루프로 범위가 지정 된 새 지역 변수를 정의 `For...Next` )</span><span class="sxs-lookup"><span data-stu-id="add56-200">Result (whether `counter` defines a new local variable that’s scoped to the entire `For...Next` loop)</span></span>|
|----------------------------|-----------------------------------|-------------------------------------------------------------------------------------------------------------|
|<span data-ttu-id="add56-201">아니요</span><span class="sxs-lookup"><span data-stu-id="add56-201">No</span></span>|<span data-ttu-id="add56-202">예</span><span class="sxs-lookup"><span data-stu-id="add56-202">Yes</span></span>|<span data-ttu-id="add56-203">`counter`는 이미 정의 되어 있으므로 아니요입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-203">No, because `counter` is already defined.</span></span> <span data-ttu-id="add56-204">의 범위가 `counter` 프로시저에 로컬인 경우 컴파일 타임 경고가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-204">If the scope of `counter` isn't local to the procedure, a compile-time warning occurs.</span></span>|
|<span data-ttu-id="add56-205">아니요</span><span class="sxs-lookup"><span data-stu-id="add56-205">No</span></span>|<span data-ttu-id="add56-206">아니요</span><span class="sxs-lookup"><span data-stu-id="add56-206">No</span></span>|<span data-ttu-id="add56-207">예.</span><span class="sxs-lookup"><span data-stu-id="add56-207">Yes.</span></span> <span data-ttu-id="add56-208">데이터 형식은 `start` , 및 식에서 유추 됩니다 `end` `step` .</span><span class="sxs-lookup"><span data-stu-id="add56-208">The data type is inferred from the `start`, `end`, and `step` expressions.</span></span> <span data-ttu-id="add56-209">형식 유추에 대 한 자세한 내용은 [Option 유추 문](option-infer-statement.md) 및 [지역 형식 유추](../../programming-guide/language-features/variables/local-type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="add56-209">For information about type inference, see [Option Infer Statement](option-infer-statement.md) and [Local Type Inference](../../programming-guide/language-features/variables/local-type-inference.md).</span></span>|
|<span data-ttu-id="add56-210">예</span><span class="sxs-lookup"><span data-stu-id="add56-210">Yes</span></span>|<span data-ttu-id="add56-211">예</span><span class="sxs-lookup"><span data-stu-id="add56-211">Yes</span></span>|<span data-ttu-id="add56-212">예, 하지만 기존 변수가 프로시저 외부에서 정의 된 경우에만 가능 `counter` 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-212">Yes, but only if the existing `counter` variable is defined outside the procedure.</span></span> <span data-ttu-id="add56-213">해당 변수는 분리 된 상태로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="add56-213">That variable remains separate.</span></span> <span data-ttu-id="add56-214">기존 `counter` 변수의 범위가 프로시저에 로컬인 경우 컴파일 타임 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-214">If the scope of the existing `counter` variable is local to the procedure, a compile-time error occurs.</span></span>|
|<span data-ttu-id="add56-215">예</span><span class="sxs-lookup"><span data-stu-id="add56-215">Yes</span></span>|<span data-ttu-id="add56-216">아니요</span><span class="sxs-lookup"><span data-stu-id="add56-216">No</span></span>|<span data-ttu-id="add56-217">예.</span><span class="sxs-lookup"><span data-stu-id="add56-217">Yes.</span></span>|

<span data-ttu-id="add56-218">의 데이터 형식은 다음 형식 중 하나 여야 하는 `counter` 반복의 유형을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-218">The data type of `counter` determines the type of the iteration, which must be one of the following types:</span></span>

- <span data-ttu-id="add56-219">,,,,,,,,, `Byte` `SByte` `UShort` `Short` `UInteger` `Integer` `ULong` `Long` `Decimal` `Single` 또는 `Double` 입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-219">A `Byte`, `SByte`, `UShort`, `Short`, `UInteger`, `Integer`, `ULong`, `Long`, `Decimal`, `Single`, or `Double`.</span></span>

- <span data-ttu-id="add56-220">[Enum 문을](enum-statement.md)사용 하 여 선언 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-220">An enumeration that you declare by using an [Enum Statement](enum-statement.md).</span></span>

- <span data-ttu-id="add56-221">`Object`입니다.</span><span class="sxs-lookup"><span data-stu-id="add56-221">An `Object`.</span></span>

- <span data-ttu-id="add56-222">`T`다음 연산자를 포함 하는 형식입니다 `B` . 여기서은 식에 사용할 수 있는 형식입니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="add56-222">A type `T` that has the following operators, where `B` is a type that can be used in a `Boolean` expression.</span></span>

  `Public Shared Operator >= (op1 As T, op2 As T) As B`

  `Public Shared Operator <= (op1 As T, op2 As T) As B`

  `Public Shared Operator - (op1 As T, op2 As T) As T`

  `Public Shared Operator + (op1 As T, op2 As T) As T`

<span data-ttu-id="add56-223">문에서 변수를 선택적으로 지정할 수 있습니다 `counter` `Next` .</span><span class="sxs-lookup"><span data-stu-id="add56-223">You can optionally specify the `counter` variable in the `Next` statement.</span></span> <span data-ttu-id="add56-224">이 구문은 특히 루프가 중첩 된 경우 프로그램의 가독성을 향상 시킵니다 `For` .</span><span class="sxs-lookup"><span data-stu-id="add56-224">This syntax improves the readability of your program, especially if you have nested `For` loops.</span></span> <span data-ttu-id="add56-225">해당 문에 표시 되는 변수를 지정 해야 합니다 `For` .</span><span class="sxs-lookup"><span data-stu-id="add56-225">You must specify the variable that appears in the corresponding `For` statement.</span></span>

<span data-ttu-id="add56-226">`start`, `end` 및 `step` 식은의 형식으로 확대 되는 모든 데이터 형식으로 계산 될 수 있습니다 `counter` .</span><span class="sxs-lookup"><span data-stu-id="add56-226">The `start`, `end`, and `step` expressions can evaluate to any data type that widens to the type of `counter`.</span></span> <span data-ttu-id="add56-227">에 사용자 정의 형식을 사용 하는 경우 `counter` 변환 연산자를 정의 하 여 `CType` `start` , 또는의 형식을 `end` `step` 의 형식으로 변환 해야 할 수 있습니다 `counter` .</span><span class="sxs-lookup"><span data-stu-id="add56-227">If you use a user-defined type for `counter`, you might have to define the `CType` conversion operator to convert the types of `start`, `end`, or `step` to the type of `counter`.</span></span>

## <a name="example"></a><span data-ttu-id="add56-228">예제</span><span class="sxs-lookup"><span data-stu-id="add56-228">Example</span></span>

<span data-ttu-id="add56-229">다음 예제에서는 제네릭 목록에서 모든 요소를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-229">The following example removes all elements from a generic list.</span></span> <span data-ttu-id="add56-230">[For Each ... 다음 문](for-each-next-statement.md)에서는 `For` `Next` 내림차순으로 반복 되는 ... 문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="add56-230">Instead of a [For Each...Next Statement](for-each-next-statement.md), the example shows a `For`...`Next` statement that iterates in descending order.</span></span> <span data-ttu-id="add56-231">이 예제에서는 `removeAt` 메서드가 제거 된 요소 뒤의 요소에서 더 낮은 인덱스 값을 사용 하기 때문에이 방법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-231">The example uses this technique because the `removeAt` method causes elements after the removed element to have a lower index value.</span></span>

[!code-vb[VbVbalrStatements#114](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#114)]

## <a name="example"></a><span data-ttu-id="add56-232">예제</span><span class="sxs-lookup"><span data-stu-id="add56-232">Example</span></span>

<span data-ttu-id="add56-233">다음 예제에서는 [Enum 문을](enum-statement.md)사용 하 여 선언 된 열거형을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-233">The following example iterates through an enumeration that's declared by using an [Enum Statement](enum-statement.md).</span></span>

[!code-vb[VbVbalrStatements#116](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#116)]

## <a name="example"></a><span data-ttu-id="add56-234">예제</span><span class="sxs-lookup"><span data-stu-id="add56-234">Example</span></span>

<span data-ttu-id="add56-235">다음 예제에서 문 매개 변수는,, 및 연산자에 대 한 연산자 오버 로드가 있는 클래스를 사용 `+` `-` `>=` `<=` 합니다.</span><span class="sxs-lookup"><span data-stu-id="add56-235">In the following example, the statement parameters use a class that has operator overloads for the `+`, `-`, `>=`, and `<=` operators.</span></span>

[!code-vb[VbVbalrStatements#117](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class7.vb#117)]

## <a name="see-also"></a><span data-ttu-id="add56-236">참고 항목</span><span class="sxs-lookup"><span data-stu-id="add56-236">See also</span></span>

- <xref:System.Collections.Generic.List%601>
- [<span data-ttu-id="add56-237">루프 구조체</span><span class="sxs-lookup"><span data-stu-id="add56-237">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="add56-238">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="add56-238">While...End While Statement</span></span>](while-end-while-statement.md)
- [<span data-ttu-id="add56-239">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="add56-239">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="add56-240">중첩 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="add56-240">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="add56-241">Exit 문</span><span class="sxs-lookup"><span data-stu-id="add56-241">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="add56-242">컬렉션</span><span class="sxs-lookup"><span data-stu-id="add56-242">Collections</span></span>](../../programming-guide/concepts/collections.md)
