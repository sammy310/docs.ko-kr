---
title: '방법: 람다 식 만들기'
ms.date: 07/20/2015
helpviewer_keywords:
- lambda expressions [Visual Basic]
- expressions [Visual Basic], lambda
ms.assetid: 3279bd5c-80f7-410a-a7ba-f7085ed36aa5
ms.openlocfilehash: cc2de38f7375848d104edff6f419656d9caa9cb2
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071926"
---
# <a name="how-to-create-a-lambda-expression-visual-basic"></a><span data-ttu-id="d86cc-102">방법: 람다 식 만들기(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d86cc-102">How to: Create a Lambda Expression (Visual Basic)</span></span>

<span data-ttu-id="d86cc-103">*람다 식은* 이름이 없는 함수 또는 서브루틴입니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-103">A *lambda expression* is a function or subroutine that does not have a name.</span></span> <span data-ttu-id="d86cc-104">람다 식은 대리자 형식이 유효한 모든 위치에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-104">A lambda expression can be used wherever a delegate type is valid.</span></span>  
  
### <a name="to-create-a-single-line-lambda-expression-function"></a><span data-ttu-id="d86cc-105">한 줄로 된 람다 식 함수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d86cc-105">To create a single-line lambda expression function</span></span>  
  
1. <span data-ttu-id="d86cc-106">대리자 형식을 사용할 수 있는 경우 `Function` 다음 예제와 같이 키워드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-106">In any situation where a delegate type could be used, type the keyword `Function`, as in the following example:</span></span>  
  
     <span data-ttu-id="d86cc-107">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="d86cc-107">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="d86cc-108">괄호 안에 바로 뒤에 `Function` 함수 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-108">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="d86cc-109">뒤에 이름을 지정 하지 않습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="d86cc-109">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="d86cc-110">`Dim add1 = Function`   `(num As Integer)`</span><span class="sxs-lookup"><span data-stu-id="d86cc-110">`Dim add1 = Function`   `(num As Integer)`</span></span>  
  
3. <span data-ttu-id="d86cc-111">매개 변수 목록 다음에 함수 본문으로 단일 식을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-111">Following the parameter list, type a single expression as the body of the function.</span></span> <span data-ttu-id="d86cc-112">식이 계산 되는 값은 함수에서 반환 하는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-112">The value that the expression evaluates to is the value returned by the function.</span></span> <span data-ttu-id="d86cc-113">`As`반환 형식을 지정 하는 데는 절을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-113">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#1)]  
  
     <span data-ttu-id="d86cc-114">정수 인수를 전달 하 여 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-114">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#2)]  
  
4. <span data-ttu-id="d86cc-115">또는 다음 예제를 통해 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-115">Alternatively, the same result is accomplished by the following example:</span></span>  
  
     [!code-vb[VbVbalrLambdas#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#3)]  
  
### <a name="to-create-a-single-line-lambda-expression-subroutine"></a><span data-ttu-id="d86cc-116">한 줄로 된 람다 식 서브루틴을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d86cc-116">To create a single-line lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="d86cc-117">대리자 형식을 사용할 수 있는 경우 `Sub` 다음 예제와 같이 키워드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-117">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="d86cc-118">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="d86cc-118">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="d86cc-119">괄호 안에 `Sub` 서브루틴의 매개 변수를 직접 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-119">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="d86cc-120">뒤에 이름을 지정 하지 않습니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="d86cc-120">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="d86cc-121">`Dim add1 = Sub`   `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="d86cc-121">`Dim add1 = Sub`   `(msg As String)`</span></span>  
  
3. <span data-ttu-id="d86cc-122">매개 변수 목록 다음에 단일 문을 서브루틴의 본문으로 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-122">Following the parameter list, type a single statement as the body of the subroutine.</span></span>  
  
     [!code-vb[VbVbalrLambdas#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#17)]  
  
     <span data-ttu-id="d86cc-123">문자열 인수를 전달 하 여 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-123">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#18)]  
  
### <a name="to-create-a-multiline-lambda-expression-function"></a><span data-ttu-id="d86cc-124">여러 줄 람다 식 함수를 만들려면</span><span class="sxs-lookup"><span data-stu-id="d86cc-124">To create a multiline lambda expression function</span></span>  
  
1. <span data-ttu-id="d86cc-125">대리자 형식을 사용할 수 있는 경우 `Function` 다음 예제와 같이 키워드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-125">In any situation where a delegate type could be used, type the keyword `Function`, as shown in the following example.</span></span>  
  
     <span data-ttu-id="d86cc-126">`Dim add1 =`   `Function`</span><span class="sxs-lookup"><span data-stu-id="d86cc-126">`Dim add1 =`   `Function`</span></span>  
  
2. <span data-ttu-id="d86cc-127">괄호 안에 바로 뒤에 `Function` 함수 매개 변수를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-127">In parentheses, directly after `Function`, type the parameters of the function.</span></span> <span data-ttu-id="d86cc-128">뒤에 이름을 지정 하지 않습니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="d86cc-128">Notice that you do not specify a name after `Function`.</span></span>  
  
     <span data-ttu-id="d86cc-129">`Dim add1 = Function`   `(index As Integer)`</span><span class="sxs-lookup"><span data-stu-id="d86cc-129">`Dim add1 = Function`   `(index As Integer)`</span></span>  
  
3. <span data-ttu-id="d86cc-130">Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-130">Press ENTER.</span></span> <span data-ttu-id="d86cc-131">`End Function`문이 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-131">The `End Function` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="d86cc-132">함수 본문 내에서 다음 코드를 추가 하 여 식을 만들고 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-132">Within the body of the function, add the following code to create an expression and return the value.</span></span> <span data-ttu-id="d86cc-133">`As`반환 형식을 지정 하는 데는 절을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-133">You do not use an `As` clause to specify the return type.</span></span>  
  
     [!code-vb[VbVbalrLambdas#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#19)]  
  
     <span data-ttu-id="d86cc-134">정수 인수를 전달 하 여 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-134">You call the lambda expression by passing in an integer argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#20)]  
  
### <a name="to-create-a-multiline-lambda-expression-subroutine"></a><span data-ttu-id="d86cc-135">여러 줄 람다 식 서브루틴을 만들려면</span><span class="sxs-lookup"><span data-stu-id="d86cc-135">To create a multiline lambda expression subroutine</span></span>  
  
1. <span data-ttu-id="d86cc-136">대리자 형식을 사용할 수 있는 경우 `Sub` 다음 예제와 같이 키워드를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-136">In any situation where a delegate type could be used, type the keyword `Sub`, as shown in the following example:</span></span>  
  
     <span data-ttu-id="d86cc-137">`Dim add1 =`   `Sub`</span><span class="sxs-lookup"><span data-stu-id="d86cc-137">`Dim add1 =`   `Sub`</span></span>  
  
2. <span data-ttu-id="d86cc-138">괄호 안에 `Sub` 서브루틴의 매개 변수를 직접 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-138">In parentheses, directly after `Sub`, type the parameters of the subroutine.</span></span> <span data-ttu-id="d86cc-139">뒤에 이름을 지정 하지 않습니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="d86cc-139">Notice that you do not specify a name after `Sub`.</span></span>  
  
     <span data-ttu-id="d86cc-140">`Dim add1 = Sub`  `(msg As String)`</span><span class="sxs-lookup"><span data-stu-id="d86cc-140">`Dim add1 = Sub`  `(msg As String)`</span></span>  
  
3. <span data-ttu-id="d86cc-141">Enter 키를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-141">Press ENTER.</span></span> <span data-ttu-id="d86cc-142">`End Sub`문이 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-142">The `End Sub` statement is automatically added.</span></span>  
  
4. <span data-ttu-id="d86cc-143">함수 본문 내에서 서브루틴이 호출 될 때 실행할 다음 코드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-143">Within the body of the function, add the following code to execute when the subroutine is invoked.</span></span>  
  
     [!code-vb[VbVbalrLambdas#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#21)]  
  
     <span data-ttu-id="d86cc-144">문자열 인수를 전달 하 여 람다 식을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-144">You call the lambda expression by passing in a string argument.</span></span>  
  
     [!code-vb[VbVbalrLambdas#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class1.vb#22)]  
  
## <a name="example"></a><span data-ttu-id="d86cc-145">예제</span><span class="sxs-lookup"><span data-stu-id="d86cc-145">Example</span></span>  

 <span data-ttu-id="d86cc-146">람다 식의 일반적인 용도는 형식이 인 매개 변수에 대 한 인수로 전달 될 수 있는 함수를 정의 하는 것입니다 `Delegate` .</span><span class="sxs-lookup"><span data-stu-id="d86cc-146">A common use of lambda expressions is to define a function that can be passed in as the argument for a parameter whose type is `Delegate`.</span></span> <span data-ttu-id="d86cc-147">다음 예제에서 <xref:System.Diagnostics.Process.GetProcesses%2A> 메서드는 로컬 컴퓨터에서 실행 되는 프로세스의 배열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-147">In the following example, the <xref:System.Diagnostics.Process.GetProcesses%2A> method returns an array of the processes running on the local computer.</span></span> <span data-ttu-id="d86cc-148"><xref:System.Linq.Enumerable.Where%2A>클래스의 메서드는 <xref:System.Linq.Enumerable> 대리자를 인수로 사용 해야 `Boolean` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-148">The <xref:System.Linq.Enumerable.Where%2A> method from the <xref:System.Linq.Enumerable> class requires a `Boolean` delegate as its argument.</span></span> <span data-ttu-id="d86cc-149">예제의 람다 식이이 목적에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-149">The lambda expression in the example is used for that purpose.</span></span> <span data-ttu-id="d86cc-150">`True`스레드를 하나만 포함 하 고에서 선택한 각 프로세스에 대해를 반환 `filteredList` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-150">It returns `True` for each process that has only one thread, and those are selected in `filteredList`.</span></span>  
  
 [!code-vb[VbVbalrLambdas#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class4.vb#10)]  
  
 <span data-ttu-id="d86cc-151">이전 예제는 LINQ (통합 언어 쿼리) 구문으로 작성 된 다음 코드와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d86cc-151">The previous example is equivalent to the following code, which is written in Language-Integrated Query (LINQ) syntax:</span></span>  
  
 [!code-vb[VbVbalrLambdas#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrLambdas/VB/Class5.vb#11)]  
  
## <a name="see-also"></a><span data-ttu-id="d86cc-152">참조</span><span class="sxs-lookup"><span data-stu-id="d86cc-152">See also</span></span>

- <xref:System.Linq.Enumerable>
- [<span data-ttu-id="d86cc-153">람다 식</span><span class="sxs-lookup"><span data-stu-id="d86cc-153">Lambda Expressions</span></span>](./lambda-expressions.md)
- [<span data-ttu-id="d86cc-154">Function 문</span><span class="sxs-lookup"><span data-stu-id="d86cc-154">Function Statement</span></span>](../../../language-reference/statements/function-statement.md)
- [<span data-ttu-id="d86cc-155">Sub 문</span><span class="sxs-lookup"><span data-stu-id="d86cc-155">Sub Statement</span></span>](../../../language-reference/statements/sub-statement.md)
- [<span data-ttu-id="d86cc-156">대리자</span><span class="sxs-lookup"><span data-stu-id="d86cc-156">Delegates</span></span>](../delegates/index.md)
- [<span data-ttu-id="d86cc-157">방법: Visual Basic에서 프로시저에 다른 프로시저 전달</span><span class="sxs-lookup"><span data-stu-id="d86cc-157">How to: Pass Procedures to Another Procedure in Visual Basic</span></span>](../delegates/how-to-pass-procedures-to-another-procedure.md)
- [<span data-ttu-id="d86cc-158">Delegate 문</span><span class="sxs-lookup"><span data-stu-id="d86cc-158">Delegate Statement</span></span>](../../../language-reference/statements/delegate-statement.md)
- [<span data-ttu-id="d86cc-159">Visual Basic의 LINQ 소개</span><span class="sxs-lookup"><span data-stu-id="d86cc-159">Introduction to LINQ in Visual Basic</span></span>](../linq/introduction-to-linq.md)
