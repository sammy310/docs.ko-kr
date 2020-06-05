---
title: If...Then...Else 문
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
ms.openlocfilehash: 0884b71c24742286e695e720add9d00dd4bfe52b
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404591"
---
# <a name="ifthenelse-statement-visual-basic"></a><span data-ttu-id="da39a-102">If...Then...Else 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="da39a-102">If...Then...Else Statement (Visual Basic)</span></span>

<span data-ttu-id="da39a-103">식의 값에 따라 문 그룹을 조건부로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-103">Conditionally executes a group of statements, depending on the value of an expression.</span></span>

## <a name="syntax"></a><span data-ttu-id="da39a-104">구문</span><span class="sxs-lookup"><span data-stu-id="da39a-104">Syntax</span></span>

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

## <a name="quick-links-to-example-code"></a><span data-ttu-id="da39a-105">예제 코드에 대 한 빠른 링크</span><span class="sxs-lookup"><span data-stu-id="da39a-105">Quick links to example code</span></span>

<span data-ttu-id="da39a-106">이 문서 `If` 에는 `Then` 다음을 사용 하는 방법을 보여 주는 몇 가지 예가 포함 되어 있습니다. ...`Else` 선언문</span><span class="sxs-lookup"><span data-stu-id="da39a-106">This article includes several examples that illustrate uses of the `If`...`Then`...`Else` statement:</span></span>

- [<span data-ttu-id="da39a-107">여러 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="da39a-107">Multiline syntax example</span></span>](#multi-line)
- [<span data-ttu-id="da39a-108">중첩 구문 예제</span><span class="sxs-lookup"><span data-stu-id="da39a-108">Nested syntax example</span></span>](#nested)
- [<span data-ttu-id="da39a-109">한 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="da39a-109">Single-line syntax example</span></span>](#single-line)

## <a name="parts"></a><span data-ttu-id="da39a-110">부분</span><span class="sxs-lookup"><span data-stu-id="da39a-110">Parts</span></span>

`condition` \
<span data-ttu-id="da39a-111">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="da39a-111">Required.</span></span> <span data-ttu-id="da39a-112">식</span><span class="sxs-lookup"><span data-stu-id="da39a-112">Expression.</span></span> <span data-ttu-id="da39a-113">는 또는로 `True` 계산 `False` 하거나 암시적으로로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="da39a-113">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

<span data-ttu-id="da39a-114">식이 Nothing으로 계산 되는 [null을 허용](../../programming-guide/language-features/data-types/nullable-value-types.md) 하는 변수인 경우 `Boolean` 조건은 식이 인 것 처럼 처리 되 고 블록이 있는 경우에는 블록을 [Nothing](../nothing.md)평가 하 고 블록이 있으면 `False` `ElseIf` `Else` 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-114">If the expression is a [Nullable](../../programming-guide/language-features/data-types/nullable-value-types.md) `Boolean` variable that evaluates to [Nothing](../nothing.md), the condition is treated as if the expression is `False`, and the `ElseIf` blocks are evaluated if they exist, or the `Else` block is executed if it exists.</span></span>

`Then` \
<span data-ttu-id="da39a-115">한 줄 구문에 필요 합니다. 여러 줄 구문에서 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-115">Required in the single-line syntax; optional in the multiline syntax.</span></span>

`statements` \
<span data-ttu-id="da39a-116">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-116">Optional.</span></span> <span data-ttu-id="da39a-117">가 `If` `Then` 로 평가 되는 경우 실행 되는 하나 이상의 `condition` 문 ... `True`</span><span class="sxs-lookup"><span data-stu-id="da39a-117">One or more statements following `If`...`Then` that are executed if `condition` evaluates to `True`.</span></span>

`elseifcondition` \
<span data-ttu-id="da39a-118">`ElseIf`가 있는 경우 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-118">Required if `ElseIf` is present.</span></span> <span data-ttu-id="da39a-119">식</span><span class="sxs-lookup"><span data-stu-id="da39a-119">Expression.</span></span> <span data-ttu-id="da39a-120">는 또는로 `True` 계산 `False` 하거나 암시적으로로 변환할 수 있는 데이터 형식으로 계산 되어야 합니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="da39a-120">Must evaluate to `True` or `False`, or to a data type that is implicitly convertible to `Boolean`.</span></span>

`elseifstatements` \
<span data-ttu-id="da39a-121">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-121">Optional.</span></span> <span data-ttu-id="da39a-122">가 `ElseIf` `Then` 로 평가 되는 경우 실행 되는 하나 이상의 `elseifcondition` 문 ... `True`</span><span class="sxs-lookup"><span data-stu-id="da39a-122">One or more statements following `ElseIf`...`Then` that are executed if `elseifcondition` evaluates to `True`.</span></span>

`elsestatements` \
<span data-ttu-id="da39a-123">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-123">Optional.</span></span> <span data-ttu-id="da39a-124">이전 `condition` 또는 식이로 계산 되지 않는 경우 실행 되는 하나 이상의 문 `elseifcondition` `True` 입니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-124">One or more statements that are executed if no previous `condition` or `elseifcondition` expression evaluates to `True`.</span></span>

`End If` \
<span data-ttu-id="da39a-125">여러 줄 `If` 버전의 `Then` 를 종료 합니다. ...`Else` 거부.</span><span class="sxs-lookup"><span data-stu-id="da39a-125">Terminates the multiline version of `If`...`Then`...`Else` block.</span></span>

## <a name="remarks"></a><span data-ttu-id="da39a-126">설명</span><span class="sxs-lookup"><span data-stu-id="da39a-126">Remarks</span></span>

### <a name="multiline-syntax"></a><span data-ttu-id="da39a-127">여러 줄 구문</span><span class="sxs-lookup"><span data-stu-id="da39a-127">Multiline syntax</span></span>

<span data-ttu-id="da39a-128">`If`... `Then` ...`Else` 문이 발견 되 면 `condition` 가 테스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-128">When an `If`...`Then`...`Else` statement is encountered, `condition` is tested.</span></span> <span data-ttu-id="da39a-129">`condition`가 이면 `True` 다음 문이 `Then` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-129">If `condition` is `True`, the statements following `Then` are executed.</span></span> <span data-ttu-id="da39a-130">`condition`가 이면 `False` 각 `ElseIf` 문 (있는 경우)이 순서 대로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-130">If `condition` is `False`, each `ElseIf` statement (if there are any) is evaluated in order.</span></span> <span data-ttu-id="da39a-131">`True` `elseifcondition` 가 발견 되 면 연결 된 바로 다음에 오는 문이 `ElseIf` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-131">When a `True` `elseifcondition` is found, the statements immediately following the associated `ElseIf` are executed.</span></span> <span data-ttu-id="da39a-132">가 `elseifcondition` 로 계산 되지 `True` 않거나 `ElseIf` 문이 없으면 다음 문이 `Else` 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-132">If no `elseifcondition` evaluates to `True`, or if there are no `ElseIf` statements, the statements following `Else` are executed.</span></span> <span data-ttu-id="da39a-133">, 또는 다음에 오는 문을 실행 한 후에 `Then` `ElseIf` `Else` 는 다음 문을 사용 하 여 실행이 계속 `End If` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-133">After executing the statements following `Then`, `ElseIf`, or `Else`, execution continues with the statement following `End If`.</span></span>

<span data-ttu-id="da39a-134">`ElseIf`And `Else` 절은 모두 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-134">The `ElseIf` and `Else` clauses are both optional.</span></span> <span data-ttu-id="da39a-135">`ElseIf`원하는 수의 `If` `Then` 절을 원하는 개수 만큼 포함할 수 있습니다. ...`Else` 문 이지만 절 뒤에는 `ElseIf` 절이 나타나지 않습니다 `Else` .</span><span class="sxs-lookup"><span data-stu-id="da39a-135">You can have as many `ElseIf` clauses as you want in an `If`...`Then`...`Else` statement, but no `ElseIf` clause can appear after an `Else` clause.</span></span> <span data-ttu-id="da39a-136">`If`...`Then` ...`Else` 문은 서로 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-136">`If`...`Then`...`Else` statements can be nested within each other.</span></span>

<span data-ttu-id="da39a-137">여러 줄 구문에서 `If` 문은 첫째 줄에서 유일한 문 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-137">In the multiline syntax, the `If` statement must be the only statement on the first line.</span></span> <span data-ttu-id="da39a-138">`ElseIf`, `Else` 및 `End If` 문은 줄 레이블 앞에만 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-138">The `ElseIf`, `Else`, and `End If` statements can be preceded only by a line label.</span></span> <span data-ttu-id="da39a-139">... `If` `Then` ...`Else` 블록은 문으로 끝나야 합니다 `End If` .</span><span class="sxs-lookup"><span data-stu-id="da39a-139">The `If`...`Then`...`Else` block must end with an `End If` statement.</span></span>

> [!TIP]
> <span data-ttu-id="da39a-140">[Select ... Case 문은](select-case-statement.md) 가능한 값이 여러 개 있는 단일 식을 평가할 때 더 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-140">The [Select...Case Statement](select-case-statement.md) might be more useful when you evaluate a single expression that has several possible values.</span></span>

### <a name="single-line-syntax"></a><span data-ttu-id="da39a-141">한 줄 구문</span><span class="sxs-lookup"><span data-stu-id="da39a-141">Single-Line syntax</span></span>

<span data-ttu-id="da39a-142">True 인 경우 코드를 실행 하는 단일 조건에 대해 한 줄 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-142">You can use the single-line syntax for a single condition with code to execute if it's true.</span></span> <span data-ttu-id="da39a-143">그러나 여러 줄로 구성 된 구문은 더 많은 구조와 유연성을 제공 하며 읽기, 유지 관리 및 디버깅 하기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-143">However, the multiple-line syntax provides more structure and flexibility and is easier to read, maintain, and debug.</span></span>

<span data-ttu-id="da39a-144">키워드 다음에 나오는 항목을 `Then` 검사 하 여 문이 한 줄 인지 여부를 확인 `If` 합니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-144">What follows the `Then` keyword is examined to determine whether a statement is a single-line `If`.</span></span> <span data-ttu-id="da39a-145">주석이 아닌 다른 항목이 `Then` 같은 줄에 표시 되는 경우이 문은 한 줄로 된 문으로 처리 됩니다 `If` .</span><span class="sxs-lookup"><span data-stu-id="da39a-145">If anything other than a comment appears after `Then` on the same line, the statement is treated as a single-line `If` statement.</span></span> <span data-ttu-id="da39a-146">`Then`가 없으면 여러 줄 `If` `Then` 의 시작 이어야 합니다. ...`Else`.</span><span class="sxs-lookup"><span data-stu-id="da39a-146">If `Then` is absent, it must be the start of a multiple-line `If`...`Then`...`Else`.</span></span>

<span data-ttu-id="da39a-147">한 줄 구문에서 ... 결정의 결과로 여러 문을 실행할 수 있습니다. `If` `Then`</span><span class="sxs-lookup"><span data-stu-id="da39a-147">In the single-line syntax, you can have multiple statements executed as the result of an `If`...`Then` decision.</span></span> <span data-ttu-id="da39a-148">모든 문은 같은 줄에 있고 콜론으로 구분 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-148">All statements must be on the same line and be separated by colons.</span></span>

## <a name="multiline-syntax-example"></a><span data-ttu-id="da39a-149">여러 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="da39a-149">Multiline syntax example</span></span>

<a name="multi-line"></a>

<span data-ttu-id="da39a-150">다음 예제에서는 ...의 여러 줄 `If` 로 된 `Then` 구문을 사용 하는 방법을 보여 줍니다. ...`Else` 선언문.</span><span class="sxs-lookup"><span data-stu-id="da39a-150">The following example illustrates the use of the multiline syntax of the `If`...`Then`...`Else` statement.</span></span>

[!code-vb[VbVbalrStatements#101](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#101)]

## <a name="nested-syntax-example"></a><span data-ttu-id="da39a-151">중첩 구문 예제</span><span class="sxs-lookup"><span data-stu-id="da39a-151">Nested syntax example</span></span>

<a name="nested"></a>

<span data-ttu-id="da39a-152">다음 예제에 `If` 는 중첩 `Then` 된 ... ...`Else` 할당문.</span><span class="sxs-lookup"><span data-stu-id="da39a-152">The following example contains nested `If`...`Then`...`Else` statements.</span></span>

[!code-vb[VbVbalrStatements#102](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#102)]

## <a name="single-line-syntax-example"></a><span data-ttu-id="da39a-153">한 줄 구문 예제</span><span class="sxs-lookup"><span data-stu-id="da39a-153">Single-Line syntax example</span></span>

<a name="single-line"></a><span data-ttu-id="da39a-154">다음 예제에서는 한 줄의 구문을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da39a-154">The following example illustrates the use of the single-line syntax.</span></span>

[!code-vb[VbVbalrStatements#103](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class6.vb#103)]

## <a name="see-also"></a><span data-ttu-id="da39a-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da39a-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- <xref:Microsoft.VisualBasic.Interaction.Switch%2A>
- [<span data-ttu-id="da39a-156">#If...Then...#Else 지시문</span><span class="sxs-lookup"><span data-stu-id="da39a-156">#If...Then...#Else Directives</span></span>](../directives/if-then-else-directives.md)
- [<span data-ttu-id="da39a-157">Select...Case 문</span><span class="sxs-lookup"><span data-stu-id="da39a-157">Select...Case Statement</span></span>](select-case-statement.md)
- [<span data-ttu-id="da39a-158">중첩 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="da39a-158">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="da39a-159">판단 구조체</span><span class="sxs-lookup"><span data-stu-id="da39a-159">Decision Structures</span></span>](../../programming-guide/language-features/control-flow/decision-structures.md)
- [<span data-ttu-id="da39a-160">Visual Basic의 논리 및 비트 연산자</span><span class="sxs-lookup"><span data-stu-id="da39a-160">Logical and Bitwise Operators in Visual Basic</span></span>](../../programming-guide/language-features/operators-and-expressions/logical-and-bitwise-operators.md)
- [<span data-ttu-id="da39a-161">If 연산자</span><span class="sxs-lookup"><span data-stu-id="da39a-161">If Operator</span></span>](../operators/if-operator.md)
