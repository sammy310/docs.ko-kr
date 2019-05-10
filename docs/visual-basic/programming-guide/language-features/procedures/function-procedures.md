---
title: Function 프로시저(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: 4fd24369380e5f8ccf8de939c36ba72a12dc872e
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/28/2019
ms.locfileid: "64649611"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="44aca-102">Function 프로시저(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="44aca-102">Function Procedures (Visual Basic)</span></span>
<span data-ttu-id="44aca-103">A `Function` 절차는 일련의 Visual Basic 문으로 둘러싸인 합니다 `Function` 및 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="44aca-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="44aca-104">`Function` 프로시저는 작업을 수행한 다음 호출 코드에 제어를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="44aca-105">제어를 반환 하기 호출 코드에도 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-105">When it returns control, it also returns a value to the calling code.</span></span>  
  
 <span data-ttu-id="44aca-106">후 첫 번째 실행 가능 문을 사용 하 여 프로시저를 호출할 문이 실행 될 때마다 시작 합니다 `Function` 문과 첫 번째 끝 `End Function`, `Exit Function`, 또는 `Return` 문을 발견 했습니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>  
  
 <span data-ttu-id="44aca-107">정의할 수 있습니다는 `Function` 모듈, 클래스 또는 구조체에는 프로시저입니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="44aca-108">`Public` 어디에서 나 호출할 수 있습니다 즉 기본적으로 모듈, 클래스 또는 구조체 정의 액세스 권한이 있는 응용 프로그램에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>  
  
 <span data-ttu-id="44aca-109">`Function` 프로시저 호출 코드에서 전달 되는 식, 상수, 변수 등의 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>  
  
## <a name="declaration-syntax"></a><span data-ttu-id="44aca-110">선언 구문</span><span class="sxs-lookup"><span data-stu-id="44aca-110">Declaration Syntax</span></span>  
 <span data-ttu-id="44aca-111">선언 구문이 `Function` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-111">The syntax for declaring a `Function` procedure is as follows:</span></span>  
  
```vb  
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType  
    [Statements]  
End Function  
```  
  
 <span data-ttu-id="44aca-112">합니다 *한정자* 액세스 수준 및 오버 로드, 재정의 공유 및 숨기기에 대 한 정보를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="44aca-113">자세한 내용은 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-113">For more information, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
 <span data-ttu-id="44aca-114">수행한 동일한 방식으로 각 매개 변수를 선언할 [Sub 프로시저](./sub-procedures.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>  
  
### <a name="data-type"></a><span data-ttu-id="44aca-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="44aca-115">Data Type</span></span>  
 <span data-ttu-id="44aca-116">모든 `Function` 프로시저는 데이터 형식에 각 변수와 마찬가지로 않습니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="44aca-117">이 데이터 형식을 지정 하 여는 `As` 절을 `Function` 문 및 해당 함수 호출 코드로 반환 값의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="44aca-118">다음 샘플 선언에서는이 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-118">The following sample declarations illustrate this.</span></span>  
  
```vb  
Function yesterday() As Date  
End Function  
  
Function findSqrt(ByVal radicand As Single) As Single  
End Function  
```  
  
 <span data-ttu-id="44aca-119">자세한 내용은 "파트"를 참조 하세요 [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-119">For more information, see "Parts" in [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span>  
  
## <a name="returning-values"></a><span data-ttu-id="44aca-120">반환 값</span><span class="sxs-lookup"><span data-stu-id="44aca-120">Returning Values</span></span>  
 <span data-ttu-id="44aca-121">값을 `Function` 프로시저에서 전송 하는 호출 코드에 다시 반환 값 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="44aca-122">프로시저는 두 가지 방법 중 하나에서이 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-122">The procedure returns this value in one of two ways:</span></span>  
  
- <span data-ttu-id="44aca-123">사용 된 `Return` 반환 값 및 반환을 지정 하는 문을 호출 프로그램에 즉시 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="44aca-124">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-124">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement immediately transfers control back  
    ' to the calling code and returns the value of Expression.  
    Return Expression  
End Function  
```  
  
- <span data-ttu-id="44aca-125">프로시저의 하나 이상의 문에서 함수 이름에 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="44aca-126">될 때까지 호출 프로그램에 제어를 반환 하지 않습니다는 `Exit Function` 또는 `End Function` 문이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="44aca-127">다음은 이에 대한 예입니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-127">The following example illustrates this.</span></span>  
  
```vb  
Function FunctionName [(ParameterList)] As ReturnType  
    ' The following statement does not transfer control back to the calling code.  
    FunctionName = Expression  
    ' When control returns to the calling code, Expression is the return value.  
End Function  
```  
  
 <span data-ttu-id="44aca-128">함수 이름에 반환 값을 할당 하는 장점은 만날 때까지 제어 프로시저에서 반환 하지 않는 프로그램 `Exit Function` 또는 `End Function` 문.</span><span class="sxs-lookup"><span data-stu-id="44aca-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="44aca-129">이 임시 값을 할당 하 고 필요한 경우 나중에 조정 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>  
  
 <span data-ttu-id="44aca-130">값을 반환 하는 방법에 대 한 자세한 내용은 참조 하세요. [Function 문](../../../../visual-basic/language-reference/statements/function-statement.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-130">For more information about returning values, see [Function Statement](../../../../visual-basic/language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="44aca-131">배열을 반환 하는 방법에 대 한 내용은 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-131">For information about returning arrays, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="calling-syntax"></a><span data-ttu-id="44aca-132">호출 구문</span><span class="sxs-lookup"><span data-stu-id="44aca-132">Calling Syntax</span></span>  
 <span data-ttu-id="44aca-133">호출 하는 `Function` 프로시저 이름과 인수 중 하나에 식 또는 대입문의 오른쪽을 포함 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="44aca-134">선택적 인수가 아닌 모든 인수에 대 한 값을 제공 해야 하 고 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="44aca-135">인수 없이 제공 되는 경우에 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>  
  
 <span data-ttu-id="44aca-136">에 대 한 호출에 대 한 구문을 `Function` 절차는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-136">The syntax for a call to a `Function` procedure is as follows:</span></span>  
  
 <span data-ttu-id="44aca-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="44aca-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>  
  
 <span data-ttu-id="44aca-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span><span class="sxs-lookup"><span data-stu-id="44aca-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>  
  
 <span data-ttu-id="44aca-139">호출 하는 경우는 `Function` 프로시저 필요가 없습니다 해당 반환 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="44aca-140">그렇지 않으면 함수는 모든 작업이 수행 되었는지, 되지만 반환 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="44aca-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> 이 방식 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>  
  
### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="44aca-142">선언 및 호출의 그림</span><span class="sxs-lookup"><span data-stu-id="44aca-142">Illustration of Declaration and Call</span></span>  
 <span data-ttu-id="44aca-143">다음 `Function` 프로시저 제일 긴 쪽 또는 다른 두 가지 측면에 대 한 값이 지정 된 오른쪽 삼각형의 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>  
  
 [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
 <span data-ttu-id="44aca-144">다음 예제에서는 일반적인 호출 `hypotenuse`합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-144">The following example shows a typical call to `hypotenuse`.</span></span>  
  
 [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="44aca-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="44aca-145">See also</span></span>

- [<span data-ttu-id="44aca-146">절차</span><span class="sxs-lookup"><span data-stu-id="44aca-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="44aca-147">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="44aca-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="44aca-148">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="44aca-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="44aca-149">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="44aca-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="44aca-150">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="44aca-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="44aca-151">Function 문</span><span class="sxs-lookup"><span data-stu-id="44aca-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="44aca-152">방법: 값을 반환 하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="44aca-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="44aca-153">방법: 프로시저에서 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="44aca-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="44aca-154">방법: 값을 반환 하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="44aca-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
