---
description: 다음에 대해 자세히 알아보세요. Loop 문 (Visual Basic)
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
ms.openlocfilehash: d170074c44d1692517f6b51abd4a6b3d005941c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795185"
---
# <a name="doloop-statement-visual-basic"></a><span data-ttu-id="8a157-103">Do...Loop 문(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="8a157-103">Do...Loop Statement (Visual Basic)</span></span>

<span data-ttu-id="8a157-104">`Boolean`조건이 `True` 이거나 조건이이 될 때까지 문 블록을 반복 `True` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-104">Repeats a block of statements while a `Boolean` condition is `True` or until the condition becomes `True`.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8a157-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="8a157-105">Syntax</span></span>  
  
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
  
## <a name="parts"></a><span data-ttu-id="8a157-106">부분</span><span class="sxs-lookup"><span data-stu-id="8a157-106">Parts</span></span>  
  
|<span data-ttu-id="8a157-107">용어</span><span class="sxs-lookup"><span data-stu-id="8a157-107">Term</span></span>|<span data-ttu-id="8a157-108">정의</span><span class="sxs-lookup"><span data-stu-id="8a157-108">Definition</span></span>|  
|---|---|  
|`Do`|<span data-ttu-id="8a157-109">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="8a157-109">Required.</span></span> <span data-ttu-id="8a157-110">루프의 정의를 시작 `Do` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-110">Starts the definition of the `Do` loop.</span></span>|  
|`While`|<span data-ttu-id="8a157-111">`Until`를 사용하는 경우를 제외하고는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-111">Required unless `Until` is used.</span></span> <span data-ttu-id="8a157-112">가가 될 때까지 루프를 반복 합니다 `condition` `False` .</span><span class="sxs-lookup"><span data-stu-id="8a157-112">Repeat the loop until `condition` is `False`.</span></span>|  
|`Until`|<span data-ttu-id="8a157-113">`While`를 사용하는 경우를 제외하고는 필수입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-113">Required unless `While` is used.</span></span> <span data-ttu-id="8a157-114">가가 될 때까지 루프를 반복 합니다 `condition` `True` .</span><span class="sxs-lookup"><span data-stu-id="8a157-114">Repeat the loop until `condition` is `True`.</span></span>|  
|`condition`|<span data-ttu-id="8a157-115">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-115">Optional.</span></span> <span data-ttu-id="8a157-116">`Boolean` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-116">`Boolean` expression.</span></span> <span data-ttu-id="8a157-117">`condition`가 이면 `Nothing` Visual Basic는로 처리 `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-117">If `condition` is `Nothing`, Visual Basic treats it as `False`.</span></span>|  
|`statements`|<span data-ttu-id="8a157-118">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-118">Optional.</span></span> <span data-ttu-id="8a157-119">또는가 인 동안 반복 되는 하나 이상의 문입니다 `condition` `True` .</span><span class="sxs-lookup"><span data-stu-id="8a157-119">One or more statements that are repeated while, or until, `condition` is `True`.</span></span>|  
|`Continue Do`|<span data-ttu-id="8a157-120">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-120">Optional.</span></span> <span data-ttu-id="8a157-121">루프의 다음 반복으로 제어를 전달 `Do` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-121">Transfers control to the next iteration of the `Do` loop.</span></span>|  
|`Exit Do`|<span data-ttu-id="8a157-122">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-122">Optional.</span></span> <span data-ttu-id="8a157-123">루프 외부로 제어를 전달 `Do` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-123">Transfers control out of the `Do` loop.</span></span>|  
|`Loop`|<span data-ttu-id="8a157-124">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-124">Required.</span></span> <span data-ttu-id="8a157-125">루프의 정의를 종료 `Do` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-125">Terminates the definition of the `Do` loop.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a157-126">설명</span><span class="sxs-lookup"><span data-stu-id="8a157-126">Remarks</span></span>  

 <span data-ttu-id="8a157-127">`Do...Loop`조건을 만족할 때까지 문 집합을 무한 횟수로 반복 하려는 경우 구조를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-127">Use a `Do...Loop` structure when you want to repeat a set of statements an indefinite number of times, until a condition is satisfied.</span></span> <span data-ttu-id="8a157-128">이 문을 설정 된 횟수 만큼 반복 하려면 [For ... 다음 문을](for-next-statement.md) 일반적으로 선택 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-128">If you want to repeat the statements a set number of times, the [For...Next Statement](for-next-statement.md) is usually a better choice.</span></span>  
  
 <span data-ttu-id="8a157-129">또는 중 하나를 사용 하 여 지정할 수 있습니다 `While` `Until` `condition` .</span><span class="sxs-lookup"><span data-stu-id="8a157-129">You can use either `While` or `Until` to specify `condition`, but not both.</span></span>  
  
 <span data-ttu-id="8a157-130">`condition`루프의 시작 또는 끝에서 한 번만 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-130">You can test `condition` only one time, at either the start or the end of the loop.</span></span> <span data-ttu-id="8a157-131">루프의 시작 부분에서 테스트 하는 경우 `condition` ( `Do` 문에서) 루프가 한 번도 실행 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-131">If you test `condition` at the start of the loop (in the `Do` statement), the loop might not run even one time.</span></span> <span data-ttu-id="8a157-132">문에서 루프의 끝 부분에서 테스트 하는 경우 `Loop` 루프는 항상 한 번 이상 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-132">If you test at the end of the loop (in the `Loop` statement), the loop always runs at least one time.</span></span>  
  
 <span data-ttu-id="8a157-133">조건은 일반적으로 두 값을 비교 하 여 발생 하지만 [부울 데이터 형식](../data-types/boolean-data-type.md) 값 (또는)으로 계산 되는 모든 식일 수 있습니다 `True` `False` .</span><span class="sxs-lookup"><span data-stu-id="8a157-133">The condition usually results from a comparison of two values, but it can be any expression that evaluates to a [Boolean Data Type](../data-types/boolean-data-type.md) value (`True` or `False`).</span></span> <span data-ttu-id="8a157-134">여기에는로 변환 된 숫자 형식과 같은 다른 데이터 형식의 값이 포함 됩니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="8a157-134">This includes values of other data types, such as numeric types, that have been converted to `Boolean`.</span></span>  
  
 <span data-ttu-id="8a157-135">`Do`루프 하나를 다른 루프에 배치 하 여 루프를 중첩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-135">You can nest `Do` loops by putting one loop within another.</span></span> <span data-ttu-id="8a157-136">서로 다른 종류의 제어 구조를 중첩할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-136">You can also nest different kinds of control structures within each other.</span></span> <span data-ttu-id="8a157-137">자세한 내용은 [중첩 컨트롤 구조](../../programming-guide/language-features/control-flow/nested-control-structures.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="8a157-137">For more information, see [Nested Control Structures](../../programming-guide/language-features/control-flow/nested-control-structures.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="8a157-138">`Do...Loop`구조를 사용 하면 보다 유연성이 향상 됩니다 [. End While 문을](while-end-while-statement.md) 사용 하면가 중지 될 때 루프를 종료할 것인지 아니면 처음에가 될 때 루프를 종료할 것인지를 결정할 수 있습니다 `condition` `True` `True` .</span><span class="sxs-lookup"><span data-stu-id="8a157-138">The `Do...Loop` structure gives you more flexibility than the [While...End While Statement](while-end-while-statement.md) because it enables you to decide whether to end the loop when `condition` stops being `True` or when it first becomes `True`.</span></span> <span data-ttu-id="8a157-139">또한 `condition` 루프의 시작 또는 끝에서 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-139">It also enables you to test `condition` at either the start or the end of the loop.</span></span>  
  
## <a name="exit-do"></a><span data-ttu-id="8a157-140">종료</span><span class="sxs-lookup"><span data-stu-id="8a157-140">Exit Do</span></span>  

 <span data-ttu-id="8a157-141">[Exit Do](exit-statement.md) 문은를 종료 하는 다른 방법을 제공할 수 있습니다 `Do…Loop` .</span><span class="sxs-lookup"><span data-stu-id="8a157-141">The [Exit Do](exit-statement.md) statement can provide an alternative way to exit a `Do…Loop`.</span></span> <span data-ttu-id="8a157-142">`Exit Do` 문 다음에 오는 문으로 제어를 즉시 전달 `Loop` 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-142">`Exit Do` transfers control immediately to the statement that follows the `Loop` statement.</span></span>  
  
 <span data-ttu-id="8a157-143">`Exit Do` 는 구조체와 같이 일부 조건을 평가한 후에 사용 되는 경우가 많습니다 `If...Then...Else` .</span><span class="sxs-lookup"><span data-stu-id="8a157-143">`Exit Do` is often used after some condition is evaluated, for example in an `If...Then...Else` structure.</span></span> <span data-ttu-id="8a157-144">오류가 발생 하거나 종료 요청 등의 반복을 계속할 수 없게 하는 조건을 감지 하는 경우 루프를 종료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-144">You might want to exit a loop if you detect a condition that makes it unnecessary or impossible to continue iterating, such as an erroneous value or a termination request.</span></span> <span data-ttu-id="8a157-145">를 사용 하는 한 가지 `Exit Do` 방법은 *무한 루프* 를 발생 시킬 수 있는 조건을 테스트 하는 것입니다 .이는 무한 하거나 무한 한 횟수를 실행할 수 있는 루프입니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-145">One use of `Exit Do` is to test for a condition that could cause an *endless loop*, which is a loop that could run a large or even infinite number of times.</span></span> <span data-ttu-id="8a157-146">를 사용 하 여 루프를 이스케이프할 수 있습니다 `Exit Do` .</span><span class="sxs-lookup"><span data-stu-id="8a157-146">You can use `Exit Do` to escape the loop.</span></span>  
  
 <span data-ttu-id="8a157-147">에는 임의 개수의 문을 포함할 수 있습니다 `Exit Do` `Do…Loop` .</span><span class="sxs-lookup"><span data-stu-id="8a157-147">You can include any number of `Exit Do` statements anywhere in a `Do…Loop`.</span></span>  
  
 <span data-ttu-id="8a157-148">중첩 된 루프 내에서 사용 되는 경우 `Do` `Exit Do` 가장 안쪽의 루프와 그 다음으로 높은 중첩 수준으로 제어를 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-148">When used within nested `Do` loops, `Exit Do` transfers control out of the innermost loop and into the next higher level of nesting.</span></span>  
  
## <a name="example"></a><span data-ttu-id="8a157-149">예제</span><span class="sxs-lookup"><span data-stu-id="8a157-149">Example</span></span>  

 <span data-ttu-id="8a157-150">다음 예제에서 루프의 문은 `index` 변수가 10 보다 클 때까지 계속 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-150">In the following example, the statements in the loop continue to run until the `index` variable is greater than 10.</span></span> <span data-ttu-id="8a157-151">`Until`절이 루프의 끝에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-151">The `Until` clause is at the end of the loop.</span></span>  
  
 [!code-vb[VbVbalrStatements#131](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#131)]  
  
## <a name="example"></a><span data-ttu-id="8a157-152">예제</span><span class="sxs-lookup"><span data-stu-id="8a157-152">Example</span></span>  

 <span data-ttu-id="8a157-153">다음 예제에서는 `While` 절 대신 절을 사용 하 `Until` 고 `condition` 끝이 아닌 루프의 시작 부분에서 테스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-153">The following example uses a `While` clause instead of an `Until` clause, and `condition` is tested at the start of the loop instead of at the end.</span></span>  
  
 [!code-vb[VbVbalrStatements#132](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#132)]  
  
## <a name="example"></a><span data-ttu-id="8a157-154">예제</span><span class="sxs-lookup"><span data-stu-id="8a157-154">Example</span></span>  

 <span data-ttu-id="8a157-155">다음 예제에서는 `condition` `index` 변수가 100 보다 큰 경우 루프를 중지 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-155">In the following example, `condition` stops the loop when the `index` variable is greater than 100.</span></span> <span data-ttu-id="8a157-156">`If`그러나 루프의 문은 `Exit Do` 인덱스 변수가 10 보다 클 경우 문이 루프를 중지 하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-156">The `If` statement in the loop, however, causes the `Exit Do` statement to stop the loop when the index variable is greater than 10.</span></span>  
  
 [!code-vb[VbVbalrStatements#133](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#133)]  
  
## <a name="example"></a><span data-ttu-id="8a157-157">예제</span><span class="sxs-lookup"><span data-stu-id="8a157-157">Example</span></span>  

 <span data-ttu-id="8a157-158">다음 예에서는 텍스트 파일의 모든 줄을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-158">The following example reads all lines in a text file.</span></span> <span data-ttu-id="8a157-159"><xref:System.IO.File.OpenText%2A>메서드는 파일을 열고 <xref:System.IO.StreamReader> 문자를 읽는를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-159">The <xref:System.IO.File.OpenText%2A> method opens the file and returns a <xref:System.IO.StreamReader> that reads the characters.</span></span> <span data-ttu-id="8a157-160">조건에서 `Do...Loop` <xref:System.IO.StreamReader.Peek%2A> 의 메서드는 `StreamReader` 추가 문자가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a157-160">In the `Do...Loop` condition, the <xref:System.IO.StreamReader.Peek%2A> method of the `StreamReader` determines whether there are any additional characters.</span></span>  
  
 [!code-vb[VbVbalrStatements#134](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/class10.vb#134)]  
  
## <a name="see-also"></a><span data-ttu-id="8a157-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a157-161">See also</span></span>

- [<span data-ttu-id="8a157-162">루프 구조체</span><span class="sxs-lookup"><span data-stu-id="8a157-162">Loop Structures</span></span>](../../programming-guide/language-features/control-flow/loop-structures.md)
- [<span data-ttu-id="8a157-163">For...Next 문</span><span class="sxs-lookup"><span data-stu-id="8a157-163">For...Next Statement</span></span>](for-next-statement.md)
- [<span data-ttu-id="8a157-164">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="8a157-164">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)
- [<span data-ttu-id="8a157-165">중첩 제어 구조체</span><span class="sxs-lookup"><span data-stu-id="8a157-165">Nested Control Structures</span></span>](../../programming-guide/language-features/control-flow/nested-control-structures.md)
- [<span data-ttu-id="8a157-166">Exit 문</span><span class="sxs-lookup"><span data-stu-id="8a157-166">Exit Statement</span></span>](exit-statement.md)
- [<span data-ttu-id="8a157-167">While...End While 문</span><span class="sxs-lookup"><span data-stu-id="8a157-167">While...End While Statement</span></span>](while-end-while-statement.md)
