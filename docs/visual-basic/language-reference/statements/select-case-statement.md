---
title: Select...Case 문(Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Select
- vb.Case
helpviewer_keywords:
- Select statement [Visual Basic]
- Case statement [Visual Basic]
- Select...Case statements
- conditional statements [Visual Basic], Select Case
- control flow [Visual Basic], branching
- Else keyword [Visual Basic], in Select...Case statements
- execution [Visual Basic], conditional
- To keyword [Visual Basic], in Select...Case statements
- Select Case statement [Visual Basic], Select...Case
- Select statement [Visual Basic], Select...Case
- Is operator [Visual Basic], in Select...Case statements
- branching [Visual Basic], conditional
- Case Else statement [Visual Basic], Select...Case
- End keyword [Visual Basic], Select Case statements
- Case statement [Visual Basic], Select...Case
ms.assetid: 68877b65-5419-4bf0-a465-20cd0e4c7d44
ms.openlocfilehash: d035118febc5ea9d1ea8e5cc0145cb030626b030
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72583246"
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="a9e6b-102">Select...Case 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-102">Select...Case Statement (Visual Basic)</span></span>
<span data-ttu-id="a9e6b-103">식의 값에 따라 여러 문 그룹 중 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-103">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9e6b-104">구문</span><span class="sxs-lookup"><span data-stu-id="a9e6b-104">Syntax</span></span>  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="a9e6b-105">요소</span><span class="sxs-lookup"><span data-stu-id="a9e6b-105">Parts</span></span>  
  
|<span data-ttu-id="a9e6b-106">용어</span><span class="sxs-lookup"><span data-stu-id="a9e6b-106">Term</span></span>|<span data-ttu-id="a9e6b-107">정의</span><span class="sxs-lookup"><span data-stu-id="a9e6b-107">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="a9e6b-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-108">Required.</span></span> <span data-ttu-id="a9e6b-109">식.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-109">Expression.</span></span> <span data-ttu-id="a9e6b-110">는 기본 데이터 형식 (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, 0, 1 중 하나로 계산 되어야 합니다. , 3, 4 및 5).</span><span class="sxs-lookup"><span data-stu-id="a9e6b-110">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="a9e6b-111">@No__t_0 문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-111">Required in a `Case` statement.</span></span> <span data-ttu-id="a9e6b-112">@No__t_0에 대해 일치 하는 값을 나타내는 식 절의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-112">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="a9e6b-113">여러 식 절은 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-113">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="a9e6b-114">각 절은 다음 형식 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-114">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="a9e6b-115">-   *expression1* `To` *식 2*</span><span class="sxs-lookup"><span data-stu-id="a9e6b-115">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="a9e6b-116">-[`Is`] *comparisonoperator.equals* *식*</span><span class="sxs-lookup"><span data-stu-id="a9e6b-116">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="a9e6b-117">-   *식*</span><span class="sxs-lookup"><span data-stu-id="a9e6b-117">-   *expression*</span></span><br /><br /> <span data-ttu-id="a9e6b-118">@No__t_0 키워드를 사용 하 여 `testexpression`에 대 한 일치 값 범위의 경계를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-118">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="a9e6b-119">@No__t_0 값은 `expression2` 값 보다 작거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-119">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="a9e6b-120">비교 연산자 (`=`, `<>`, `<`, `<=`, `>` 또는 `>=`)와 함께 `Is` 키워드를 사용 하 여 `testexpression`에 대 한 일치 값에 대 한 제한을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-120">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="a9e6b-121">@No__t_0 키워드를 제공 하지 않으면 *comparisonoperator.equals*앞에 자동으로 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-121">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="a9e6b-122">@No__t_0만 지정 하는 양식은 `Is` 형식의 특수 한 경우로 처리 됩니다. 여기서 *comparisonoperator.equals* 는 등호 (`=`)입니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-122">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="a9e6b-123">이 양식은 `expression`  =  `testexpression`으로 평가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-123">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="a9e6b-124">@No__t_0의 식은 모든 데이터 형식일 수 있습니다 .이 경우에는 `testexpression` 형식으로 암시적으로 변환할 수 있고 적절 한 `comparisonoperator`는 사용 되는 두 형식에 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-124">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="a9e6b-125">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-125">Optional.</span></span> <span data-ttu-id="a9e6b-126">@No__t_1에서 `expressionlist` 절과 일치 하는 경우 실행 되는 `Case` 다음 문이 하나 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-126">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="a9e6b-127">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="a9e6b-127">Optional.</span></span> <span data-ttu-id="a9e6b-128">@No__t_1 `Case Else` 뒤에 나오는 하나 이상의 문은 `Case` 문의 `expressionlist`에 있는 절과 일치 하지 않는 경우에 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-128">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="a9e6b-129">@No__t_0의 정의를 종료 합니다. `Case` 생성</span><span class="sxs-lookup"><span data-stu-id="a9e6b-129">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9e6b-130">주의</span><span class="sxs-lookup"><span data-stu-id="a9e6b-130">Remarks</span></span>  
 <span data-ttu-id="a9e6b-131">@No__t_0 `Case` `expressionlist` 절과 일치 하는 경우 해당 `Case` 문을 따라 오는 문은 다음 `Case`, `Case Else` 또는 `End Select` 문으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-131">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="a9e6b-132">그런 다음 `End Select` 다음 문으로 제어가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-132">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="a9e6b-133">@No__t_0 둘 이상의 `Case` 절에서 `expressionlist` 절과 일치 하는 경우 첫 번째 일치 항목 다음에 오는 문만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-133">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="a9e6b-134">@No__t_0 문은 다른 `Case` 문의 `testexpression`와 `expressionlist` 절 사이에 일치 하는 항목이 없는 경우 실행할 `elsestatements`를 소개 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-134">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="a9e6b-135">필수는 아니지만 `Select Case` 생성에 `Case Else` 문을 생성 하 여 예측할 수 없는 `testexpression` 값을 처리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-135">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="a9e6b-136">@No__t_2와 일치 하는 `Case` `expressionlist` 절이 없는 경우 `Case Else` 문이 없으면 `End Select` 다음 문으로 제어가 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-136">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="a9e6b-137">각 `Case` 절에서 여러 식이나 범위를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-137">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="a9e6b-138">예를 들어 다음 줄은 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-138">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> <span data-ttu-id="a9e6b-139">@No__t_1 및 `Case Else` 문에 사용 되는 `Is` 키워드는 개체 참조 비교에 사용 되는 [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)와 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-139">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../../../visual-basic/language-reference/operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="a9e6b-140">문자 문자열에 대해 범위와 여러 식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-140">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="a9e6b-141">다음 예에서는 "사과"와 정확 하 게 일치 하는 문자열을 `Case` 하 고, "너트"와 "수프" 사이의 값을 알파벳 순서로 포함 하거나, `testItem`의 현재 값과 정확히 같은 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-141">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="a9e6b-142">@No__t_0 설정은 문자열 비교에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-142">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="a9e6b-143">@No__t_0에서 "사과" 및 "사과" 문자열은 동일 하 게 비교 되지만 `Option Compare Binary`는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-143">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a9e6b-144">여러 절이 있는 `Case` *문은 단락 이라는*동작을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-144">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="a9e6b-145">Visual Basic는 절을 왼쪽에서 오른쪽으로 계산 하 고, `testexpression`와 일치 하는 항목을 생성 하는 경우 나머지 절은 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-145">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="a9e6b-146">단기는 성능을 향상 시킬 수 있지만 `expressionlist`의 모든 식이 계산 될 것으로 예상 되는 경우 예기치 않은 결과를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-146">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="a9e6b-147">단락에 대 한 자세한 내용은 [부울 식](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-147">For more information on short-circuiting, see [Boolean Expressions](../../../visual-basic/programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="a9e6b-148">@No__t_0 또는 `Case Else` 문 블록 내의 코드에서 블록의 문을 더 이상 실행할 필요가 없는 경우 `Exit Select` 문을 사용 하 여 블록을 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-148">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="a9e6b-149">그러면 `End Select` 다음에 오는 문으로 제어가 즉시 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-149">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="a9e6b-150">`Select Case` 구문은 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-150">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="a9e6b-151">중첩 된 각 `Select Case` 구문은 일치 하는 `End Select` 문을 포함 해야 하며 중첩 된 외부 `Select Case` 생성의 단일 `Case` 또는 `Case Else` 문 블록 내에 완전히 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-151">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="a9e6b-152">예제</span><span class="sxs-lookup"><span data-stu-id="a9e6b-152">Example</span></span>  
 <span data-ttu-id="a9e6b-153">다음 예에서는 `Select Case` 생성을 사용 하 여 `number` 변수 값에 해당 하는 줄을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-153">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="a9e6b-154">두 번째 `Case` 문에는 `number`의 현재 값과 일치 하는 값이 포함 되어 있으므로 "Between 6 ~ 8" (포함)를 쓰는 문이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a9e6b-154">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a><span data-ttu-id="a9e6b-155">참조</span><span class="sxs-lookup"><span data-stu-id="a9e6b-155">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [<span data-ttu-id="a9e6b-156">End 문</span><span class="sxs-lookup"><span data-stu-id="a9e6b-156">End Statement</span></span>](../../../visual-basic/language-reference/statements/end-statement.md)
- [<span data-ttu-id="a9e6b-157">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="a9e6b-157">If...Then...Else Statement</span></span>](../../../visual-basic/language-reference/statements/if-then-else-statement.md)
- [<span data-ttu-id="a9e6b-158">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="a9e6b-158">Option Compare Statement</span></span>](../../../visual-basic/language-reference/statements/option-compare-statement.md)
- [<span data-ttu-id="a9e6b-159">Exit 문</span><span class="sxs-lookup"><span data-stu-id="a9e6b-159">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
