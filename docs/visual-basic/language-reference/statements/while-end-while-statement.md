---
title: While...End While 문
ms.date: 07/20/2015
f1_keywords:
- vb.While
- vb.While...EndWhile
helpviewer_keywords:
- While statement [Visual Basic], While...End While
- While statement [Visual Basic]
- While...End While statements [Visual Basic]
ms.assetid: b931d1ce-e8ed-44d8-a13d-92a4f5458a1e
ms.openlocfilehash: d9eb8cb95d46e860aa127954d7b44e37991d4a13
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84391588"
---
# <a name="whileend-while-statement-visual-basic"></a><span data-ttu-id="a106b-102">While...End While 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a106b-102">While...End While Statement (Visual Basic)</span></span>
<span data-ttu-id="a106b-103">지정 된 조건이 인 동안 일련의 문을 실행 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-103">Runs a series of statements as long as a given condition is `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a106b-104">구문</span><span class="sxs-lookup"><span data-stu-id="a106b-104">Syntax</span></span>  
  
```vb  
While condition  
    [ statements ]  
    [ Continue While ]  
    [ statements ]  
    [ Exit While ]  
    [ statements ]  
End While  
```  
  
## <a name="parts"></a><span data-ttu-id="a106b-105">부분</span><span class="sxs-lookup"><span data-stu-id="a106b-105">Parts</span></span>  
  
|<span data-ttu-id="a106b-106">용어</span><span class="sxs-lookup"><span data-stu-id="a106b-106">Term</span></span>|<span data-ttu-id="a106b-107">정의</span><span class="sxs-lookup"><span data-stu-id="a106b-107">Definition</span></span>|  
|---|---|  
|`condition`|<span data-ttu-id="a106b-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a106b-108">Required.</span></span> <span data-ttu-id="a106b-109">`Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-109">`Boolean` expression.</span></span> <span data-ttu-id="a106b-110">`condition`가 이면 `Nothing` Visual Basic는로 처리 `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-110">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="a106b-111">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-111">Optional.</span></span> <span data-ttu-id="a106b-112">다음 `While` 에 실행 되는 하나 이상의 문 (가 일 때마다 실행 `condition` 됨) `True`</span><span class="sxs-lookup"><span data-stu-id="a106b-112">One or more statements following `While`, which run every time `condition` is `True`.</span></span>|  
|`Continue While`|<span data-ttu-id="a106b-113">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-113">Optional.</span></span> <span data-ttu-id="a106b-114">블록의 다음 반복으로 제어를 전달 `While` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-114">Transfers control to the next iteration of the `While` block.</span></span>|  
|`Exit While`|<span data-ttu-id="a106b-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-115">Optional.</span></span> <span data-ttu-id="a106b-116">블록 밖으로 제어를 전송 `While` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-116">Transfers control out of the `While` block.</span></span>|  
|`End While`|<span data-ttu-id="a106b-117">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="a106b-117">Required.</span></span> <span data-ttu-id="a106b-118">`While` 블록의 정의를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-118">Terminates the definition of the `While` block.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a106b-119">설명</span><span class="sxs-lookup"><span data-stu-id="a106b-119">Remarks</span></span>  
 <span data-ttu-id="a106b-120">조건이 유지 되는 한 `While...End While` 문 집합을 무한 횟수로 반복 하려는 경우 구조를 사용 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-120">Use a `While...End While` structure when you want to repeat a set of statements an indefinite number of times, as long as a condition remains `True`.</span></span> <span data-ttu-id="a106b-121">조건을 테스트 하는 위치 또는 테스트 결과를 보다 유연 하 게 하려는 경우 다음을 수행 하는 것이 좋습니다. [ Loop 문](do-loop-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a106b-121">If you want more flexibility with where you test the condition or what result you test it for, you might prefer the [Do...Loop Statement](do-loop-statement.md).</span></span> <span data-ttu-id="a106b-122">이 문을 설정 된 횟수 만큼 반복 하려면 [For ... 다음 문을](for-next-statement.md) 일반적으로 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-122">If you want to repeat the statements a set number of times, the [For...Next Statement](for-next-statement.md) is usually a better choice.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="a106b-123">키워드는 다음 `While` 에도 사용 됩니다 [. Loop 문](do-loop-statement.md), [Skip while 절](../queries/skip-while-clause.md) 및 [Take while 절](../queries/take-while-clause.md)</span><span class="sxs-lookup"><span data-stu-id="a106b-123">The `While` keyword is also used in the [Do...Loop Statement](do-loop-statement.md), the [Skip While Clause](../queries/skip-while-clause.md) and the [Take While Clause](../queries/take-while-clause.md).</span></span>  
  
 <span data-ttu-id="a106b-124">`condition`가 이면 `True` `statements` 문이 발생할 때까지 모든가 실행 됩니다 `End While` .</span><span class="sxs-lookup"><span data-stu-id="a106b-124">If `condition` is `True`, all of the `statements` run until the `End While` statement is encountered.</span></span> <span data-ttu-id="a106b-125">그런 다음 제어가 문으로 반환 `While` `condition` 되 고 다시 검사 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-125">Control then returns to the `While` statement, and `condition` is again checked.</span></span> <span data-ttu-id="a106b-126">`condition`가 여전히 이면 `True` 프로세스가 반복 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-126">If `condition` is still `True`, the process is repeated.</span></span> <span data-ttu-id="a106b-127">인 경우 `False` 제어는 문 다음에 오는 문으로 전달 `End While` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-127">If it’s `False`, control passes to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="a106b-128">`While`문은 루프를 시작 하기 전에 항상 조건을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-128">The `While` statement always checks the condition before it starts the loop.</span></span> <span data-ttu-id="a106b-129">조건이 유지 되는 동안 반복이 계속 됩니다 `True` .</span><span class="sxs-lookup"><span data-stu-id="a106b-129">Looping continues while the condition remains `True`.</span></span> <span data-ttu-id="a106b-130">`condition` `False` 루프를 처음 입력할 때가 이면 한 번도 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-130">If `condition` is `False` when you first enter the loop, it doesn’t run even once.</span></span>  
  
 <span data-ttu-id="a106b-131">는 `condition` 일반적으로 두 값을 비교 하 여 발생 하지만 [부울 데이터 형식](../data-types/boolean-data-type.md) 값 (또는)으로 계산 되는 모든 식일 수 `True` 있습니다 `False` .</span><span class="sxs-lookup"><span data-stu-id="a106b-131">The `condition` usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="a106b-132">이 식에는로 변환 된 숫자 형식과 같은 다른 데이터 형식의 값이 포함 될 수 있습니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="a106b-132">This expression can include a value of another data type, such as a numeric type, that has been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="a106b-133">`While`루프 하나를 다른 루프에 배치 하 여 루프를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-133">You can nest `While` loops by placing one loop within another.</span></span> <span data-ttu-id="a106b-134">서로 다른 종류의 제어 구조를 중첩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-134">You can also nest different kinds of control structures within one another.</span></span> <span data-ttu-id="a106b-135">자세한 내용은 [중첩 컨트롤 구조](../../programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a106b-135">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
## <a name="exit-while"></a><span data-ttu-id="a106b-136">종료 중</span><span class="sxs-lookup"><span data-stu-id="a106b-136">Exit While</span></span>  
 <span data-ttu-id="a106b-137">[Exit While](exit-statement.md) 문은 루프를 종료 하는 다른 방법을 제공할 수 있습니다 `While` .</span><span class="sxs-lookup"><span data-stu-id="a106b-137">The [Exit While](exit-statement.md) statement can provide another way to exit a `While` loop.</span></span> <span data-ttu-id="a106b-138">`Exit While`문 다음에 오는 문으로 제어를 즉시 전송 `End While` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-138">`Exit While` immediately transfers control to the statement that follows the `End While` statement.</span></span>  
  
 <span data-ttu-id="a106b-139">`Exit While`특정 조건 (예: 구조체)을 평가한 후에 일반적으로를 사용 `If...Then...Else` 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-139">You typically use `Exit While` after some condition is evaluated (for example, in an `If...Then...Else` structure).</span></span> <span data-ttu-id="a106b-140">오류가 발생 하거나 종료 요청 등의 반복을 계속할 수 없게 하는 조건을 감지 하는 경우 루프를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-140">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="a106b-141">`Exit While`매우 크거나 무한 한 번 실행 될 수 있는 루프로 *무한 루프*를 발생 시킬 수 있는 조건을 테스트할 때를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-141">You can use `Exit While` when you test for a condition that could cause an *endless loop*, which is a loop that could run an extremely large or even infinite number of times.</span></span> <span data-ttu-id="a106b-142">그런 다음를 사용 `Exit While` 하 여 루프를 이스케이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-142">You can then use `Exit While` to escape the loop.</span></span>  
  
 <span data-ttu-id="a106b-143">`Exit While`루프의 어디에 든 원하는 개수의 문을 넣을 수 있습니다 `While` .</span><span class="sxs-lookup"><span data-stu-id="a106b-143">You can place any number of `Exit While` statements anywhere in the `While` loop.</span></span>  
  
 <span data-ttu-id="a106b-144">중첩 된 루프 내에서 사용 되는 경우 `While` `Exit While` 가장 안쪽의 루프와 그 다음으로 높은 중첩 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-144">When used within nested `While` loops, `Exit While` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
 <span data-ttu-id="a106b-145">`Continue While`문은 즉시 루프의 다음 반복으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-145">The `Continue While` statement immediately transfers control to the next iteration of the loop.</span></span> <span data-ttu-id="a106b-146">자세한 내용은 [Continue 문](continue-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="a106b-146">For more information, see [Continue Statement](continue-statement.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="a106b-147">예제</span><span class="sxs-lookup"><span data-stu-id="a106b-147">Example</span></span>  
 <span data-ttu-id="a106b-148">다음 예제에서 루프의 문은 `index` 변수가 10 보다 클 때까지 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-148">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#171](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#171)]  
  
## <a name="example"></a><span data-ttu-id="a106b-149">예제</span><span class="sxs-lookup"><span data-stu-id="a106b-149">Example</span></span>  
 <span data-ttu-id="a106b-150">다음 예제에서는 및 문을 사용 하는 방법을 보여 줍니다 `Continue While` `Exit While` .</span><span class="sxs-lookup"><span data-stu-id="a106b-150">The following example illustrates the use of the `Continue While` and `Exit While` statements.</span></span>  
  
 [!code-vb[VbVbalrStatements#172](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#172)]  
  
## <a name="example"></a><span data-ttu-id="a106b-151">예제</span><span class="sxs-lookup"><span data-stu-id="a106b-151">Example</span></span>  
 <span data-ttu-id="a106b-152">다음 예에서는 텍스트 파일의 모든 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-152">The following example reads all lines in a text file.</span></span> <span data-ttu-id="a106b-153"><xref:System.IO.File.OpenText%2A>메서드는 파일을 열고 <xref:System.IO.StreamReader> 문자를 읽는를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-153">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="a106b-154">조건에서 `While` <xref:System.IO.StreamReader.Peek%2A> 의 메서드는 `StreamReader` 파일이 추가 문자를 포함 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="a106b-154">In the `While` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether the file contains additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#173](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class14.vb#173)]  
  
## <a name="see-also"></a><span data-ttu-id="a106b-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a106b-155">See also</span></span>

- [<span data-ttu-id="a106b-156">루프 구조체</span><span class="sxs-lookup"><span data-stu-id="a106b-156">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="a106b-157">Do...Loop 문</span><span class="sxs-lookup"><span data-stu-id="a106b-157">Do...Loop Statement</span></span>](do-loop-statement.md)
- [<span data-ttu-id="a106b-158">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="a106b-158">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="a106b-159">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="a106b-159">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="a106b-160">중첩 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="a106b-160">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="a106b-161">Exit 문</span><span class="sxs-lookup"><span data-stu-id="a106b-161">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="a106b-162">Continue 문</span><span class="sxs-lookup"><span data-stu-id="a106b-162">Continue Statement</span></span>](continue-statement.md)
