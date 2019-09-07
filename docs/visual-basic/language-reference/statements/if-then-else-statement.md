---
title: If...Then...Else 문(Visual Basic)
ms.date: 04/16/2018
f1_keywords:
- vb.ElseIf
- vb.Then
- vb.If
- vb.EndIf
helpviewer_keywords:
- ElseIf statement [Visual Basic], If...Then...Else
- Then statement [Visual Basic], If...Then...Else
- control flow [Visual Basic], branching
- execution [Visual Basic], conditional
- TypeOf...Is expression, and If...Then...Else statements
- If...Then...Else statements
- If statement [Visual Basic], If...Then...Else
- If statement [Visual Basic]
- Is operator [Visual Basic], in If...Then...Else statements
- If Operator [Visual Basic]
- branching [Visual Basic], conditional
- If function [Visual Basic], and If...Then...Else statements
- Else statement [Visual Basic]
ms.assetid: 790068a2-1307-4e28-8a72-be5ebda099e9
ms.openlocfilehash: db81a1c41809b563d5f9d0777c3feb064c5e540b
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400708"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="a814c-102">If...Then...Else 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a814c-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="a814c-103">식의 값에 따라 문 그룹을 조건부로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="a814c-104">구문</span><span class="sxs-lookup"><span data-stu-id="a814c-104">Syntax</span></span>

```vb
' Multiline syntax:
If condition [ Then ]
    [ statements ]
[ ElseIf elseifcondition [ Then ]
    [ elseifstatements ] ]
[ Else
    [ elsestatements ] ]
End If

' Single-line syntax:
If condition Then [ statements ] [ Else [ elsestatements ] ]
```

## <a name="quick-links-to-example-code"></a><span data-ttu-id="a814c-105">예제 코드에 대 한 빠른 링크</span><span class="sxs-lookup"><span data-stu-id="a814c-105">Quick links to example code</span></span>

<span data-ttu-id="a814c-106">이 문서에는 `If`다음을 사용 하는 방법을 보여 주는 몇 가지 예가 포함 되어 있습니다. `Then`... `Else` 문:</span><span class="sxs-lookup"><span data-stu-id="a814c-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="a814c-107">여러 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="a814c-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="a814c-108">중첩 구문 예제</span><span class="sxs-lookup"><span data-stu-id="a814c-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="a814c-109">한 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="a814c-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="a814c-110">요소</span><span class="sxs-lookup"><span data-stu-id="a814c-110">Parts</span></span>

`condition` \
<span data-ttu-id="a814c-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a814c-111">Required.</span></span> <span data-ttu-id="a814c-112">식.</span><span class="sxs-lookup"><span data-stu-id="a814c-112">Expression.</span></span> <span data-ttu-id="a814c-113">는 `True` `Boolean`또는 `False`로 계산 하거나 암시적으로로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="a814c-114">식이 [Nothing](../../../visual-basic/language-reference/nothing.md)으로 계산 되 `False`는 null을 [허용](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` 하는 변수인 경우 조건은 식이 인 것 처럼 처리 되 고 `ElseIf` 블록이 있는 경우에는 블록을 평가 하 고 `Else` 블록은 다음과 같이 처리 됩니다. 존재 하는 경우 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-114">If the expression is a [Nullable](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../../../visual-basic/language-reference/nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="a814c-115">한 줄 구문에 필요 합니다. 여러 줄 구문에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="a814c-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-116">Optional.</span></span> <span data-ttu-id="a814c-117">뒤 `If`에 하나 이상의 문이 있습니다. `Then` 가 `condition` 로 평가`True`되는 경우 실행 되는입니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="a814c-118">가 있는 `ElseIf` 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="a814c-119">식.</span><span class="sxs-lookup"><span data-stu-id="a814c-119">Expression.</span></span> <span data-ttu-id="a814c-120">는 `True` `Boolean`또는 `False`로 계산 하거나 암시적으로로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="a814c-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-121">Optional.</span></span> <span data-ttu-id="a814c-122">뒤 `ElseIf`에 하나 이상의 문이 있습니다. `Then` 가 `elseifcondition` 로 평가`True`되는 경우 실행 되는입니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="a814c-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-123">Optional.</span></span> <span data-ttu-id="a814c-124">이전 `condition` 또는 `elseifcondition` 식이 로`True`계산 되지 않는 경우 실행 되는 하나 이상의 문입니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="a814c-125">여러 줄 버전의 `If`를 종료 합니다. `Then`... `Else` 블록.</span><span class="sxs-lookup"><span data-stu-id="a814c-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="a814c-126">설명</span><span class="sxs-lookup"><span data-stu-id="a814c-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="a814c-127">여러 줄 구문</span><span class="sxs-lookup"><span data-stu-id="a814c-127">Multiline syntax</span></span>

<span data-ttu-id="a814c-128">`If`... `Then`... 문이 발견 되 면가 테스트 됩니다. `condition` `Else`</span><span class="sxs-lookup"><span data-stu-id="a814c-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="a814c-129">`condition` 가 이면`True`다음 문이`Then` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="a814c-130">`condition` 가 이면`False`각 문(있는`ElseIf` 경우)이 순서 대로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="a814c-131">가 발견 되 면 연결 `ElseIf` 된 바로 다음에 오는 문이 실행 됩니다. `True` `elseifcondition`</span><span class="sxs-lookup"><span data-stu-id="a814c-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="a814c-132">가로 `elseifcondition` `True`계산 되지 `Else` 않거나 문이 없으면 다음 문이 실행 됩니다. `ElseIf`</span><span class="sxs-lookup"><span data-stu-id="a814c-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="a814c-133">`Then`, 또는 `ElseIf` `End If`다음에 오는 문을 실행 한 후에는 다음 문을 사용 하 여 실행이 계속 됩니다. `Else`</span><span class="sxs-lookup"><span data-stu-id="a814c-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="a814c-134">`ElseIf` And`Else` 절은 모두 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="a814c-135">원하는 수 `ElseIf` `If`의 절을 원하는 개수 만큼 포함할 수 있습니다. `Then`... 문 이지만 절 뒤 `Else` 에는 절이 나타나지 않습니다 `ElseIf`. `Else`</span><span class="sxs-lookup"><span data-stu-id="a814c-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="a814c-136">`If`... `Then`... `Else` 문은 서로 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="a814c-137">여러 줄 구문 `If` 에서 문은 첫째 줄에서 유일한 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="a814c-138">`ElseIf`, 및문은`End If` 줄 레이블 앞에만 올 수 있습니다. `Else`</span><span class="sxs-lookup"><span data-stu-id="a814c-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="a814c-139">`If`... `Then`... 블록은 `End If` 문으로 끝나야 합니다. `Else`</span><span class="sxs-lookup"><span data-stu-id="a814c-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="a814c-140">[Select ... Case 문은](../../../visual-basic/language-reference/statements/select-case-statement.md) 가능한 값이 여러 개 있는 단일 식을 평가할 때 더 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-140">The [Select...Case Statement](../../../visual-basic/language-reference/statements/select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="a814c-141">한 줄 구문</span><span class="sxs-lookup"><span data-stu-id="a814c-141">Single-Line syntax</span></span>

<span data-ttu-id="a814c-142">True 인 경우 코드를 실행 하는 단일 조건에 대해 한 줄 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="a814c-143">그러나 여러 줄로 구성 된 구문은 더 많은 구조와 유연성을 제공 하며 읽기, 유지 관리 및 디버깅 하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="a814c-144">`Then` 키워드 다음에 나오는 항목을 검사 하 여 문이 한 줄 `If`인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="a814c-145">주석이 아닌 다른 항목이 같은 줄 `Then` 에 표시 되는 경우이 문은 한 줄 `If` 로 된 문으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="a814c-146">가 없으면 여러 줄 `If`의 시작 이어야 합니다. `Then` `Then`... `Else`.</span><span class="sxs-lookup"><span data-stu-id="a814c-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="a814c-147">한 줄 구문에서 다음의 `If`결과로 실행 되는 문이 여러 개 있을 수 있습니다. `Then` 결정.</span><span class="sxs-lookup"><span data-stu-id="a814c-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="a814c-148">모든 문은 같은 줄에 있고 콜론으로 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="a814c-149">여러 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="a814c-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="a814c-150">다음 예제에서는 ...의 여러 줄로 된 `If`구문을 사용 하는 방법을 보여 줍니다. `Then`... `Else` 문.</span><span class="sxs-lookup"><span data-stu-id="a814c-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="a814c-151">중첩 구문 예제</span><span class="sxs-lookup"><span data-stu-id="a814c-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="a814c-152">다음 예제에는 중첩 `If`된 ... `Then`... `Else` 문.</span><span class="sxs-lookup"><span data-stu-id="a814c-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="a814c-153">한 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="a814c-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="a814c-154">다음 예제에서는 한 줄의 구문을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a814c-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="a814c-155">참고자료</span><span class="sxs-lookup"><span data-stu-id="a814c-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="a814c-156">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="a814c-156">#If...Then...#Else Directives</span></span>](../../../visual-basic/language-reference/directives/if-then-else-directives.md)
- [<span data-ttu-id="a814c-157">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="a814c-157">Select...Case Statement</span></span>](../../../visual-basic/language-reference/statements/select-case-statement.md)
- [<span data-ttu-id="a814c-158">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="a814c-158">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="a814c-159">판단 구조</span><span class="sxs-lookup"><span data-stu-id="a814c-159">Decision Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="a814c-160">Visual Basic 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="a814c-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="a814c-161">If 연산자</span><span class="sxs-lookup"><span data-stu-id="a814c-161">If Operator</span></span>](../../../visual-basic/language-reference/operators/if-operator.md)
