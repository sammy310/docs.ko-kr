---
title: Do...Loop 문
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
ms.openlocfilehash: 9384cbb355189be448fa4b8d274721b4a7ca6a20
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351250"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="6ba2d-102">Do...Loop 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6ba2d-102">Do...Loop Statement (Visual Basic)</span></span>
<span data-ttu-id="6ba2d-103">`Boolean` 조건이 `True` 되거나 조건이 `True`상태가 될 때까지 문 블록을 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-103">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6ba2d-104">구문</span><span class="sxs-lookup"><span data-stu-id="6ba2d-104">Syntax</span></span>  
  
```vb  
Do { While | Until } condition  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop  
' -or-  
Do  
    [ statements ]  
    [ Continue Do ]  
    [ statements ]  
    [ Exit Do ]  
    [ statements ]  
Loop { While | Until } condition  
```  
  
## <a name="parts"></a><span data-ttu-id="6ba2d-105">요소</span><span class="sxs-lookup"><span data-stu-id="6ba2d-105">Parts</span></span>  
  
|<span data-ttu-id="6ba2d-106">용어</span><span class="sxs-lookup"><span data-stu-id="6ba2d-106">Term</span></span>|<span data-ttu-id="6ba2d-107">정의</span><span class="sxs-lookup"><span data-stu-id="6ba2d-107">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="6ba2d-108">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-108">Required.</span></span> <span data-ttu-id="6ba2d-109">`Do` 루프의 정의를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-109">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="6ba2d-110">`Until`를 사용하는 경우를 제외하고는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-110">Required unless `Until` is used.</span></span> <span data-ttu-id="6ba2d-111">`condition` `False`될 때까지 루프를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-111">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="6ba2d-112">`While`를 사용하는 경우를 제외하고는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-112">Required unless `While` is used.</span></span> <span data-ttu-id="6ba2d-113">`condition` `True`될 때까지 루프를 반복 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-113">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="6ba2d-114">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="6ba2d-114">Optional.</span></span> <span data-ttu-id="6ba2d-115">`Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-115">`Boolean` expression.</span></span> <span data-ttu-id="6ba2d-116">`condition` `Nothing`경우 Visual Basic는이를 `False`로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-116">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="6ba2d-117">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="6ba2d-117">Optional.</span></span> <span data-ttu-id="6ba2d-118">또는 `True``condition` 될 때까지 반복 되는 하나 이상의 문입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-118">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="6ba2d-119">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="6ba2d-119">Optional.</span></span> <span data-ttu-id="6ba2d-120">`Do` 루프의 다음 반복으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-120">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="6ba2d-121">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="6ba2d-121">Optional.</span></span> <span data-ttu-id="6ba2d-122">`Do` 루프에서 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-122">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="6ba2d-123">필수입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-123">Required.</span></span> <span data-ttu-id="6ba2d-124">`Do` 루프의 정의를 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-124">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6ba2d-125">주의</span><span class="sxs-lookup"><span data-stu-id="6ba2d-125">Remarks</span></span>  
 <span data-ttu-id="6ba2d-126">조건을 만족할 때까지 문 집합을 무한 횟수로 반복 하려는 경우 `Do...Loop` 구조를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-126">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="6ba2d-127">이 문을 설정 된 횟수 만큼 반복 하려면 [For ... 다음 문을](../../../visual-basic/language-reference/statements/for-next-statement.md) 일반적으로 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-127">If you want to repeat the statements a set number of times, the [For...Next Statement](../../../visual-basic/language-reference/statements/for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="6ba2d-128">`While` 또는 `Until`를 사용 하 여 `condition`를 지정할 수 있지만 둘 다 지정할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-128">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="6ba2d-129">루프의 시작 또는 끝에서 한 번만 `condition` 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-129">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="6ba2d-130">루프의 시작 부분에서 `condition`를 테스트 하는 경우 (`Do` 문에서) 루프가 한 번도 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-130">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="6ba2d-131">루프의 끝 부분에서 테스트 하는 경우 (`Loop` 문에서) 루프는 항상 한 번 이상 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-131">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="6ba2d-132">이 조건은 일반적으로 두 값을 비교 하 여 발생 하지만 [부울 데이터 형식](../../../visual-basic/language-reference/data-types/boolean-data-type.md) 값 (`True` 또는 `False`)으로 계산 되는 모든 식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-132">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../../../visual-basic/language-reference/data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="6ba2d-133">여기에는 `Boolean`로 변환 된 숫자 형식과 같은 다른 데이터 형식의 값이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-133">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="6ba2d-134">루프 하나를 다른 루프에 배치 하 여 `Do` 루프를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-134">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="6ba2d-135">서로 다른 종류의 제어 구조를 중첩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-135">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="6ba2d-136">자세한 내용은 [중첩 컨트롤 구조](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-136">For more information, see [Nested Control Structures](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6ba2d-137">`Do...Loop` 구조를 사용 하면 보다 유연성이 향상 됩니다 [. End While 문을](../../../visual-basic/language-reference/statements/while-end-while-statement.md) 사용 하면 `condition` `True` 중지 될 때 또는 처음 `True`될 때 루프를 종료할 것인지 여부를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-137">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](../../../visual-basic/language-reference/statements/while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="6ba2d-138">또한 루프의 시작 또는 끝 부분에서 `condition` 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-138">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="6ba2d-139">종료</span><span class="sxs-lookup"><span data-stu-id="6ba2d-139">Exit Do</span></span>  
 <span data-ttu-id="6ba2d-140">[Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) 문은 `Do…Loop`를 종료 하는 다른 방법을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-140">The [Exit Do](../../../visual-basic/language-reference/statements/exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="6ba2d-141">`Exit Do`는 `Loop` 문 다음에 오는 문으로 제어를 즉시 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-141">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="6ba2d-142">`Exit Do`는 일부 조건이 계산 된 후 (예: `If...Then...Else` 구조체) 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-142">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="6ba2d-143">오류가 발생 하거나 종료 요청 등의 반복을 계속할 수 없게 하는 조건을 감지 하는 경우 루프를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-143">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="6ba2d-144">`Exit Do` 사용 하는 한 가지 방법은 무한 하거나 무한 한 횟수를 실행할 수 있는 루프 인 *무한 루프*를 발생 시킬 수 있는 조건을 테스트 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-144">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="6ba2d-145">`Exit Do`를 사용 하 여 루프를 이스케이프할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-145">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="6ba2d-146">`Do…Loop`어디에 든 원하는 수의 `Exit Do` 문을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-146">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="6ba2d-147">중첩 된 `Do` 루프 내에서 사용 하는 경우 `Exit Do`는 가장 안쪽의 루프와 그 다음으로 높은 중첩 수준으로 제어를 전송 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-147">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="6ba2d-148">예제</span><span class="sxs-lookup"><span data-stu-id="6ba2d-148">Example</span></span>  
 <span data-ttu-id="6ba2d-149">다음 예에서는 `index` 변수가 10 보다 클 때까지 루프의 문이 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-149">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="6ba2d-150">`Until` 절은 루프의 끝에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-150">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="6ba2d-151">예제</span><span class="sxs-lookup"><span data-stu-id="6ba2d-151">Example</span></span>  
 <span data-ttu-id="6ba2d-152">다음 예제에서는 `Until` 절 대신 `While` 절을 사용 하 고 `condition`는 끝이 아닌 루프의 시작 부분에서 테스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-152">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="6ba2d-153">예제</span><span class="sxs-lookup"><span data-stu-id="6ba2d-153">Example</span></span>  
 <span data-ttu-id="6ba2d-154">다음 예제에서 `condition` `index` 변수가 100 보다 큰 경우 루프를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-154">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="6ba2d-155">그러나 루프의 `If` 문은 인덱스 변수가 10 보다 클 때 `Exit Do` 문이 루프를 중지 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-155">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="6ba2d-156">예제</span><span class="sxs-lookup"><span data-stu-id="6ba2d-156">Example</span></span>  
 <span data-ttu-id="6ba2d-157">다음 예에서는 텍스트 파일의 모든 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-157">The following example reads all lines in a text file.</span></span> <span data-ttu-id="6ba2d-158"><xref:System.IO.File.OpenText%2A> 메서드는 파일을 열고 문자를 읽는 <xref:System.IO.StreamReader>을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-158">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="6ba2d-159">`Do...Loop` 조건에서 `StreamReader`의 <xref:System.IO.StreamReader.Peek%2A> 메서드는 추가 문자가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6ba2d-159">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="6ba2d-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6ba2d-160">See also</span></span>

- [<span data-ttu-id="6ba2d-161">루프 구조</span><span class="sxs-lookup"><span data-stu-id="6ba2d-161">Loop Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="6ba2d-162">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="6ba2d-162">For...Next Statement</span></span>](../../../visual-basic/language-reference/statements/for-next-statement.md)
- [<span data-ttu-id="6ba2d-163">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="6ba2d-163">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)
- [<span data-ttu-id="6ba2d-164">중첩 제어 구조</span><span class="sxs-lookup"><span data-stu-id="6ba2d-164">Nested Control Structures</span></span>](../../../visual-basic/programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="6ba2d-165">Exit 문</span><span class="sxs-lookup"><span data-stu-id="6ba2d-165">Exit Statement</span></span>](../../../visual-basic/language-reference/statements/exit-statement.md)
- [<span data-ttu-id="6ba2d-166">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="6ba2d-166">While...End While Statement</span></span>](../../../visual-basic/language-reference/statements/while-end-while-statement.md)
