---
description: '자세히 알아보기: Select ... Case 문 (Visual Basic)'
title: Select...Case 문
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
ms.openlocfilehash: 4f8edecd0a0b1afd59e182a372e308c3829a9b93
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741135"
---
# <a name="selectcase-statement-visual-basic"></a><span data-ttu-id="48140-103">Select...Case 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="48140-103">Select...Case Statement (Visual Basic)</span></span>

<span data-ttu-id="48140-104">식의 값에 따라 여러 문 그룹 중 하나를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="48140-104">Runs one of several groups of statements, depending on the value of an expression.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48140-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="48140-105">Syntax</span></span>  
  
```vb  
Select [ Case ] testexpression  
    [ Case expressionlist  
        [ statements ] ]  
    [ Case Else  
        [ elsestatements ] ]  
End Select  
```  
  
## <a name="parts"></a><span data-ttu-id="48140-106">부분</span><span class="sxs-lookup"><span data-stu-id="48140-106">Parts</span></span>  
  
|<span data-ttu-id="48140-107">용어</span><span class="sxs-lookup"><span data-stu-id="48140-107">Term</span></span>|<span data-ttu-id="48140-108">정의</span><span class="sxs-lookup"><span data-stu-id="48140-108">Definition</span></span>|  
|---|---|  
|`testexpression`|<span data-ttu-id="48140-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="48140-109">Required.</span></span> <span data-ttu-id="48140-110">식</span><span class="sxs-lookup"><span data-stu-id="48140-110">Expression.</span></span> <span data-ttu-id="48140-111">는 기본 데이터 형식 (,,,,,,,,,,,,,, `Boolean` `Byte` `Char` `Date` `Double` `Decimal` `Integer` `Long` `Object` `SByte` `Short` `Single` `String` `UInteger` `ULong` 및 `UShort` ) 중 하나로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="48140-111">Must evaluate to one of the elementary data types (`Boolean`, `Byte`, `Char`, `Date`, `Double`, `Decimal`, `Integer`, `Long`, `Object`, `SByte`, `Short`, `Single`, `String`, `UInteger`, `ULong`, and `UShort`).</span></span>|  
|`expressionlist`|<span data-ttu-id="48140-112">`Case`문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="48140-112">Required in a `Case` statement.</span></span> <span data-ttu-id="48140-113">에 대해 일치 하는 값을 나타내는 식 절의 목록입니다 `testexpression` .</span><span class="sxs-lookup"><span data-stu-id="48140-113">List of expression clauses representing match values for `testexpression`.</span></span> <span data-ttu-id="48140-114">여러 식 절은 쉼표로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48140-114">Multiple expression clauses are separated by commas.</span></span> <span data-ttu-id="48140-115">각 절은 다음 형식 중 하나를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-115">Each clause can take one of the following forms:</span></span><br /><br /> <span data-ttu-id="48140-116">-   *expression1* `To` *식 2*</span><span class="sxs-lookup"><span data-stu-id="48140-116">-   *expression1* `To` *expression2*</span></span><br /><span data-ttu-id="48140-117">-[ `Is` ] *comparisonoperator.equals* *식*</span><span class="sxs-lookup"><span data-stu-id="48140-117">-   [ `Is` ] *comparisonoperator* *expression*</span></span><br /><span data-ttu-id="48140-118">-   *식*</span><span class="sxs-lookup"><span data-stu-id="48140-118">-   *expression*</span></span><br /><br /> <span data-ttu-id="48140-119">키워드를 사용 `To` 하 여에 대 한 일치 값 범위의 경계를 지정 `testexpression` 합니다.</span><span class="sxs-lookup"><span data-stu-id="48140-119">Use the `To` keyword to specify the boundaries of a range of match values for `testexpression`.</span></span> <span data-ttu-id="48140-120">값은 `expression1` 의 값 보다 작거나 같아야 합니다 `expression2` .</span><span class="sxs-lookup"><span data-stu-id="48140-120">The value of `expression1` must be less than or equal to the value of `expression2`.</span></span><br /><br /> <span data-ttu-id="48140-121">`Is`비교 연산자 (,,,, 또는)와 함께 키워드를 사용 `=` `<>` 하 여 `<` `<=` `>` `>=` 에 대 한 일치 값에 대 한 제한을 지정 `testexpression` 합니다.</span><span class="sxs-lookup"><span data-stu-id="48140-121">Use the `Is` keyword with a comparison operator (`=`, `<>`, `<`, `<=`, `>`, or `>=`) to specify a restriction on the match values for `testexpression`.</span></span> <span data-ttu-id="48140-122">키워드를 `Is` 제공 하지 않으면 *comparisonoperator.equals* 앞에 자동으로 삽입 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48140-122">If the `Is` keyword is not supplied, it is automatically inserted before *comparisonoperator*.</span></span><br /><br /> <span data-ttu-id="48140-123">만 지정 하는 폼은 `expression` `Is` *comparisonoperator.equals* 가 등호 () 인 특수 한 경우로 취급 됩니다 `=` .</span><span class="sxs-lookup"><span data-stu-id="48140-123">The form specifying only `expression` is treated as a special case of the `Is` form where *comparisonoperator* is the equal sign (`=`).</span></span> <span data-ttu-id="48140-124">이 폼은로 평가 됩니다 `testexpression`  =  `expression` .</span><span class="sxs-lookup"><span data-stu-id="48140-124">This form is evaluated as `testexpression` = `expression`.</span></span><br /><br /> <span data-ttu-id="48140-125">의 식은 `expressionlist` 의 형식으로 암시적으로 변환 가능 하 고 해당가 사용 되는 `testexpression` `comparisonoperator` 두 가지 형식에 적합 한 경우의 모든 데이터 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-125">The expressions in `expressionlist` can be of any data type, provided they are implicitly convertible to the type of `testexpression` and the appropriate `comparisonoperator` is valid for the two types it is being used with.</span></span>|  
|`statements`|<span data-ttu-id="48140-126">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="48140-126">Optional.</span></span> <span data-ttu-id="48140-127">`Case`가 `testexpression` 에서 절과 일치 하는 경우이 실행 되는 하나 이상의 문입니다 `expressionlist` .</span><span class="sxs-lookup"><span data-stu-id="48140-127">One or more statements following `Case` that run if `testexpression` matches any clause in `expressionlist`.</span></span>|  
|`elsestatements`|<span data-ttu-id="48140-128">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="48140-128">Optional.</span></span> <span data-ttu-id="48140-129">`Case Else`가 문의에 있는 절과 일치 하지 않는 경우 실행 되는 다음 문이 하나 이상 `testexpression` `expressionlist` `Case` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-129">One or more statements following `Case Else` that run if `testexpression` does not match any clause in the `expressionlist` of any of the `Case` statements.</span></span>|  
|`End Select`|<span data-ttu-id="48140-130">... 생성의 정의를 종료 합니다. `Select` `Case`</span><span class="sxs-lookup"><span data-stu-id="48140-130">Terminates the definition of the `Select`...`Case` construction.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="48140-131">설명</span><span class="sxs-lookup"><span data-stu-id="48140-131">Remarks</span></span>  

 <span data-ttu-id="48140-132">`testexpression`가 절과 일치 하면 `Case` `expressionlist` 해당 문 다음에 오는 문이 `Case` 다음 `Case` , `Case Else` 또는 `End Select` 문으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48140-132">If `testexpression` matches any `Case` `expressionlist` clause, the statements following that `Case` statement run up to the next `Case`, `Case Else`, or `End Select` statement.</span></span> <span data-ttu-id="48140-133">그런 다음 제어가 다음 문으로 전달 `End Select` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48140-133">Control then passes to the statement following `End Select`.</span></span> <span data-ttu-id="48140-134">가 둘 `testexpression` `expressionlist` 이상의 절에 있는 절과 일치 하면 `Case` 첫 번째 일치 항목 다음에 오는 문만 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48140-134">If `testexpression` matches an `expressionlist` clause in more than one `Case` clause, only the statements following the first match run.</span></span>  
  
 <span data-ttu-id="48140-135">`Case Else`문은 `elsestatements` `testexpression` 다른 문의와 절 사이에 일치 하는 항목이 없는 경우 실행할를 소개 하는 데 사용 됩니다 `expressionlist` `Case` .</span><span class="sxs-lookup"><span data-stu-id="48140-135">The `Case Else` statement is used to introduce the `elsestatements` to run if no match is found between the `testexpression` and an `expressionlist` clause in any of the other `Case` statements.</span></span> <span data-ttu-id="48140-136">반드시 필요한 것은 아니지만 생성에 문을 포함 하 여 예측할 수 없는 값을 처리 하는 것이 좋습니다 `Case Else` `Select Case` `testexpression` .</span><span class="sxs-lookup"><span data-stu-id="48140-136">Although not required, it is a good idea to have a `Case Else` statement in your `Select Case` construction to handle unforeseen `testexpression` values.</span></span> <span data-ttu-id="48140-137">일치 하 `Case` `expressionlist` 는 절 `testexpression` 이 없고 문이 없으면 `Case Else` 다음 문으로 제어가 전달 됩니다 `End Select` .</span><span class="sxs-lookup"><span data-stu-id="48140-137">If no `Case` `expressionlist` clause matches `testexpression` and there is no `Case Else` statement, control passes to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="48140-138">각 절에서 여러 식이나 범위를 사용할 수 있습니다 `Case` .</span><span class="sxs-lookup"><span data-stu-id="48140-138">You can use multiple expressions or ranges in each `Case` clause.</span></span> <span data-ttu-id="48140-139">예를 들어 다음 줄은 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="48140-139">For example, the following line is valid.</span></span>  
  
 `Case 1 To 4, 7 To 9, 11, 13, Is > maxNumber`  
  
> [!NOTE]
> <span data-ttu-id="48140-140">`Is`및 문에 사용 되는 키워드는 `Case` `Case Else` 개체 참조 비교에 사용 되는 [is 연산자](../operators/is-operator.md)와 동일 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-140">The `Is` keyword used in the `Case` and `Case Else` statements is not the same as the [Is Operator](../operators/is-operator.md), which is used for object reference comparison.</span></span>  
  
 <span data-ttu-id="48140-141">문자 문자열에 대해 범위와 여러 식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-141">You can specify ranges and multiple expressions for character strings.</span></span> <span data-ttu-id="48140-142">다음 예에서는 `Case` "사과"와 정확히 같은 문자열을 검색 하 고, "너트"와 "수프" 사이의 값을 알파벳 순서로 포함 하거나,의 현재 값과 정확히 같은 값을 포함 합니다 `testItem` .</span><span class="sxs-lookup"><span data-stu-id="48140-142">In the following example, `Case` matches any string that is exactly equal to "apples", has a value between "nuts" and "soup" in alphabetical order, or contains the exact same value as the current value of `testItem`.</span></span>  
  
 `Case "apples", "nuts" To "soup", testItem`  
  
 <span data-ttu-id="48140-143">의 설정은 `Option Compare` 문자열 비교에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-143">The setting of `Option Compare` can affect string comparisons.</span></span> <span data-ttu-id="48140-144">에서 `Option Compare Text` "사과" 및 "사과" 문자열은 동일한 것으로 간주 되지만 `Option Compare Binary` 에서는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-144">Under `Option Compare Text`, the strings "Apples" and "apples" compare as equal, but under `Option Compare Binary`, they do not.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="48140-145">`Case`여러 절이 있는 문은 단락 이라는 동작을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-145">A `Case` statement with multiple clauses can exhibit behavior known as *short-circuiting*.</span></span> <span data-ttu-id="48140-146">Visual Basic는 절을 왼쪽에서 오른쪽으로 계산 하 고, 일치 하는을 생성 하는 경우 `testexpression` 나머지 절은 계산 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-146">Visual Basic evaluates the clauses from left to right, and if one produces a match with `testexpression`, the remaining clauses are not evaluated.</span></span> <span data-ttu-id="48140-147">단락을 통해 성능을 향상 시킬 수 있지만의 모든 식이 계산 될 것으로 예상 되는 경우 예기치 않은 결과가 발생할 수 있습니다 `expressionlist` .</span><span class="sxs-lookup"><span data-stu-id="48140-147">Short-circuiting can improve performance, but it can produce unexpected results if you are expecting every expression in `expressionlist` to be evaluated.</span></span> <span data-ttu-id="48140-148">단락에 대 한 자세한 내용은 [부울 식](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="48140-148">For more information on short-circuiting, see [Boolean Expressions](../../programming-guide/language-features/operators-and-expressions/boolean-expressions.md).</span></span>  
  
 <span data-ttu-id="48140-149">`Case`또는 문 블록 내의 코드에서 `Case Else` 블록의 문을 더 이상 실행할 필요가 없는 경우 문을 사용 하 여 블록을 종료할 수 있습니다 `Exit Select` .</span><span class="sxs-lookup"><span data-stu-id="48140-149">If the code within a `Case` or `Case Else` statement block does not need to run any more of the statements in the block, it can exit the block by using the `Exit Select` statement.</span></span> <span data-ttu-id="48140-150">그러면 다음 문으로 제어가 즉시 전송 `End Select` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48140-150">This transfers control immediately to the statement following `End Select`.</span></span>  
  
 <span data-ttu-id="48140-151">`Select Case` 구조는 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48140-151">`Select Case` constructions can be nested.</span></span> <span data-ttu-id="48140-152">중첩 된 각 `Select Case` 생성에는 일치 하는 문이 있어야 `End Select` 하며 중첩 된 `Case` `Case Else` 외부 생성의 단일 또는 문 블록 내에 완전히 포함 되어야 합니다 `Select Case` .</span><span class="sxs-lookup"><span data-stu-id="48140-152">Each nested `Select Case` construction must have a matching `End Select` statement and must be completely contained within a single `Case` or `Case Else` statement block of the outer `Select Case` construction within which it is nested.</span></span>  
  
## <a name="example"></a><span data-ttu-id="48140-153">예제</span><span class="sxs-lookup"><span data-stu-id="48140-153">Example</span></span>  

 <span data-ttu-id="48140-154">다음 예에서는 생성을 사용 하 여 `Select Case` 변수 값에 해당 하는 줄을 작성 합니다 `number` .</span><span class="sxs-lookup"><span data-stu-id="48140-154">The following example uses a `Select Case` construction to write a line corresponding to the value of the variable `number`.</span></span> <span data-ttu-id="48140-155">두 번째 `Case` 문에는의 현재 값과 일치 하는 값이 포함 되어 `number` 있으므로 "Between 6 ~ 8" (포함)를 쓰는 문이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48140-155">The second `Case` statement contains the value that matches the current value of `number`, so the statement that writes "Between 6 and 8, inclusive" runs.</span></span>  
  
 [!code-vb[VbVbalrStatements#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#54)]  
  
## <a name="see-also"></a><span data-ttu-id="48140-156">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48140-156">See also</span></span>

- <xref:Microsoft.VisualBasic.Interaction.Choose%2A>
- [<span data-ttu-id="48140-157">End 문</span><span class="sxs-lookup"><span data-stu-id="48140-157">End Statement</span></span>](end-statement.md)
- [<span data-ttu-id="48140-158">If...Then...Else 문</span><span class="sxs-lookup"><span data-stu-id="48140-158">If...Then...Else Statement</span></span>](if-then-else-statement.md)
- [<span data-ttu-id="48140-159">Option Compare 문</span><span class="sxs-lookup"><span data-stu-id="48140-159">Option Compare Statement</span></span>](option-compare-statement.md)
- [<span data-ttu-id="48140-160">Exit 문</span><span class="sxs-lookup"><span data-stu-id="48140-160">Exit Statement</span></span>](exit-statement.md)
