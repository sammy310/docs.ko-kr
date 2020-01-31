---
title: Function 프로시저
ms.date: 07/20/2015
helpviewer_keywords:
- Function procedures
- return values [Visual Basic], function procedures
- Visual Basic code, procedures
- procedures [Visual Basic], calling
- procedures [Visual Basic], Function procedures
- syntax [Visual Basic], function procedures
ms.assetid: 1b9f632c-553b-4cb6-920a-ded117ead8c0
ms.openlocfilehash: d7a0293e2ec520c2278f67156be56315d1def2b5
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76780089"
---
# <a name="function-procedures-visual-basic"></a><span data-ttu-id="fac7d-102">함수 프로시저 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="fac7d-102">Function procedures (Visual Basic)</span></span>

<span data-ttu-id="fac7d-103">`Function` 프로시저는 `Function` 및 `End Function` 문으로 묶인 일련의 Visual Basic 문입니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-103">A `Function` procedure is a series of Visual Basic statements enclosed by the `Function` and `End Function` statements.</span></span> <span data-ttu-id="fac7d-104">`Function` 프로시저는 작업을 수행 하 고 컨트롤을 호출 코드에 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-104">The `Function` procedure performs a task and then returns control to the calling code.</span></span> <span data-ttu-id="fac7d-105">제어를 반환할 때 호출 코드에도 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-105">When it returns control, it also returns a value to the calling code.</span></span>

<span data-ttu-id="fac7d-106">프로시저가 호출 될 때마다 문이 실행 되 고, `Function` 문 뒤의 첫 번째 실행 가능 문으로 시작 하 여 첫 번째 `End Function`, `Exit Function`또는 `Return` 문으로 끝납니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-106">Each time the procedure is called, its statements run, starting with the first executable statement after the `Function` statement and ending with the first `End Function`, `Exit Function`, or `Return` statement encountered.</span></span>

<span data-ttu-id="fac7d-107">모듈, 클래스 또는 구조체에서 `Function` 프로시저를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-107">You can define a `Function` procedure in a module, class, or structure.</span></span> <span data-ttu-id="fac7d-108">기본적으로 `Public` 됩니다. 즉, 응용 프로그램에서 정의 된 모듈, 클래스 또는 구조체에 대 한 액세스 권한이 있는 어디에서 나 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-108">It is `Public` by default, which means you can call it from anywhere in your application that has access to the module, class, or structure in which you defined it.</span></span>

<span data-ttu-id="fac7d-109">`Function` 프로시저는 호출 코드를 통해 전달 되는 상수, 변수 또는 식과 같은 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-109">A `Function` procedure can take arguments, such as constants, variables, or expressions, which are passed to it by the calling code.</span></span>

## <a name="declaration-syntax"></a><span data-ttu-id="fac7d-110">선언 구문</span><span class="sxs-lookup"><span data-stu-id="fac7d-110">Declaration syntax</span></span>

<span data-ttu-id="fac7d-111">`Function` 프로시저를 선언 하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-111">The syntax for declaring a `Function` procedure is as follows:</span></span>

```vb
[Modifiers] Function FunctionName [(ParameterList)] As ReturnType
    [Statements]
End Function
```

<span data-ttu-id="fac7d-112">*한정자* 는 오버 로드, 재정의, 공유 및 숨김과 관련 된 정보 및 액세스 수준을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-112">The *modifiers* can specify access level and information regarding overloading, overriding, sharing, and shadowing.</span></span> <span data-ttu-id="fac7d-113">자세한 내용은 [Function 문](../../../language-reference/statements/function-statement.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fac7d-113">For more information, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

<span data-ttu-id="fac7d-114">[하위 프로시저](./sub-procedures.md)와 동일한 방식으로 각 매개 변수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-114">You declare each parameter the same way you do for [Sub Procedures](./sub-procedures.md).</span></span>

### <a name="data-type"></a><span data-ttu-id="fac7d-115">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="fac7d-115">Data type</span></span>

<span data-ttu-id="fac7d-116">모든 `Function` 프로시저에는 모든 변수와 마찬가지로 데이터 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-116">Every `Function` procedure has a data type, just as every variable does.</span></span> <span data-ttu-id="fac7d-117">이 데이터 형식은 `Function` 문에서 `As` 절에 의해 지정 되며 함수가 호출 코드에 반환 하는 값의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-117">This data type is specified by the `As` clause in the `Function` statement, and it determines the data type of the value the function returns to the calling code.</span></span> <span data-ttu-id="fac7d-118">다음 샘플 선언에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-118">The following sample declarations illustrate this.</span></span>

```vb
Function Yesterday() As Date
End Function

Function FindSqrt(radicand As Single) As Single
End Function
```

<span data-ttu-id="fac7d-119">자세한 내용은 [함수 문의](../../../language-reference/statements/function-statement.md)"Parts"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fac7d-119">For more information, see "Parts" in [Function Statement](../../../language-reference/statements/function-statement.md).</span></span>

### <a name="returning-values"></a><span data-ttu-id="fac7d-120">값 반환</span><span class="sxs-lookup"><span data-stu-id="fac7d-120">Returning values</span></span>

<span data-ttu-id="fac7d-121">`Function` 프로시저에서 호출 하는 코드로 다시 전송 하는 값을 해당 반환 값 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-121">The value a `Function` procedure sends back to the calling code is called its return value.</span></span> <span data-ttu-id="fac7d-122">이 프로시저는 다음 두 가지 방법 중 하나로이 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-122">The procedure returns this value in one of two ways:</span></span>

- <span data-ttu-id="fac7d-123">`Return` 문을 사용 하 여 반환 값을 지정 하 고 제어를 호출 프로그램에 즉시 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-123">It uses the `Return` statement to specify the return value, and returns control immediately to the calling program.</span></span> <span data-ttu-id="fac7d-124">다음 예제에서는 이것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-124">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement immediately transfers control back
      ' to the calling code and returns the value of Expression.
      Return Expression
  End Function
  ```

- <span data-ttu-id="fac7d-125">프로시저의 하나 이상의 문에서 고유한 함수 이름에 값을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-125">It assigns a value to its own function name in one or more statements of the procedure.</span></span> <span data-ttu-id="fac7d-126">컨트롤은 `Exit Function` 또는 `End Function` 문을 실행할 때까지 호출 프로그램으로 반환 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-126">Control does not return to the calling program until an `Exit Function` or `End Function` statement is executed.</span></span> <span data-ttu-id="fac7d-127">다음 예제에서는 이것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-127">The following example illustrates this.</span></span>

  ```vb
  Function FunctionName [(ParameterList)] As ReturnType
      ' The following statement does not transfer control back to the calling code.
      FunctionName = Expression
      ' When control returns to the calling code, Expression is the return value.
  End Function
  ```

<span data-ttu-id="fac7d-128">함수 이름에 반환 값을 할당 하는 장점은 컨트롤이 `Exit Function` 또는 `End Function` 문을 발견할 때까지 프로시저에서 반환 되지 않는다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-128">The advantage of assigning the return value to the function name is that control does not return from the procedure until it encounters an `Exit Function` or `End Function` statement.</span></span> <span data-ttu-id="fac7d-129">이렇게 하면 예비 값을 할당 하 고 필요한 경우 나중에 해당 값을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-129">This allows you to assign a preliminary value and adjust it later if necessary.</span></span>

<span data-ttu-id="fac7d-130">값 반환에 대 한 자세한 내용은 [Function 문](../../../language-reference/statements/function-statement.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="fac7d-130">For more information about returning values, see [Function Statement](../../../language-reference/statements/function-statement.md).</span></span> <span data-ttu-id="fac7d-131">배열을 반환 하는 방법에 대 한 자세한 내용은 [배열](../arrays/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="fac7d-131">For information about returning arrays, see [Arrays](../arrays/index.md).</span></span>

## <a name="calling-syntax"></a><span data-ttu-id="fac7d-132">호출 구문</span><span class="sxs-lookup"><span data-stu-id="fac7d-132">Calling syntax</span></span>

<span data-ttu-id="fac7d-133">대입문의 오른쪽에 이름 및 인수를 포함 하 여 `Function` 프로시저를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-133">You invoke a `Function` procedure by including its name and arguments either on the right side of an assignment statement or in an expression.</span></span> <span data-ttu-id="fac7d-134">선택 사항이 아닌 모든 인수에 대 한 값을 제공 해야 하며 인수 목록을 괄호로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-134">You must provide values for all arguments that are not optional, and you must enclose the argument list in parentheses.</span></span> <span data-ttu-id="fac7d-135">인수를 제공 하지 않으면 필요에 따라 괄호를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-135">If no arguments are supplied, you can optionally omit the parentheses.</span></span>

<span data-ttu-id="fac7d-136">`Function` 프로시저에 대 한 호출 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-136">The syntax for a call to a `Function` procedure is as follows.</span></span>

<span data-ttu-id="fac7d-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span><span class="sxs-lookup"><span data-stu-id="fac7d-137">*lvalue*  `=`  *functionname* `[(` *argumentlist* `)]`</span></span>

<span data-ttu-id="fac7d-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span><span class="sxs-lookup"><span data-stu-id="fac7d-138">`If ((` *functionname* `[(` *argumentlist* `)] / 3) <=`  *expression* `) Then`</span></span>

<span data-ttu-id="fac7d-139">`Function` 프로시저를 호출 하는 경우에는 반환 값을 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-139">When you call a `Function` procedure, you do not have to use its return value.</span></span> <span data-ttu-id="fac7d-140">그렇지 않으면 함수의 모든 동작이 수행 되지만 반환 값은 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-140">If you do not, all the actions of the function are performed, but the return value is ignored.</span></span> <span data-ttu-id="fac7d-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A>는 이러한 방식으로 호출 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-141"><xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> is often called in this manner.</span></span>

### <a name="illustration-of-declaration-and-call"></a><span data-ttu-id="fac7d-142">선언 및 호출에 대 한 그림</span><span class="sxs-lookup"><span data-stu-id="fac7d-142">Illustration of declaration and call</span></span>

<span data-ttu-id="fac7d-143">다음 `Function` 프로시저는 다른 두 변의 값을 고려 하 여 오른쪽 삼각형의 가장 긴 쪽 또는 빗변을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-143">The following `Function` procedure calculates the longest side, or hypotenuse, of a right triangle, given the values for the other two sides.</span></span>

[!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]

<span data-ttu-id="fac7d-144">다음 예제에서는 `hypotenuse`에 대 한 일반적인 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fac7d-144">The following example shows a typical call to `hypotenuse`.</span></span>

[!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]

## <a name="see-also"></a><span data-ttu-id="fac7d-145">참조</span><span class="sxs-lookup"><span data-stu-id="fac7d-145">See also</span></span>

- [<span data-ttu-id="fac7d-146">절차</span><span class="sxs-lookup"><span data-stu-id="fac7d-146">Procedures</span></span>](./index.md)
- [<span data-ttu-id="fac7d-147">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="fac7d-147">Sub Procedures</span></span>](./sub-procedures.md)
- [<span data-ttu-id="fac7d-148">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="fac7d-148">Property Procedures</span></span>](./property-procedures.md)
- [<span data-ttu-id="fac7d-149">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="fac7d-149">Operator Procedures</span></span>](./operator-procedures.md)
- [<span data-ttu-id="fac7d-150">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="fac7d-150">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="fac7d-151">Function 문</span><span class="sxs-lookup"><span data-stu-id="fac7d-151">Function Statement</span></span>](../../../../visual-basic/language-reference/statements/function-statement.md)
- [<span data-ttu-id="fac7d-152">방법: 값을 반환하는 프로시저 만들기</span><span class="sxs-lookup"><span data-stu-id="fac7d-152">How to: Create a Procedure that Returns a Value</span></span>](./how-to-create-a-procedure-that-returns-a-value.md)
- [<span data-ttu-id="fac7d-153">방법: 프로시저에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="fac7d-153">How to: Return a Value from a Procedure</span></span>](./how-to-return-a-value-from-a-procedure.md)
- [<span data-ttu-id="fac7d-154">방법: 값을 반환하는 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="fac7d-154">How to: Call a Procedure That Returns a Value</span></span>](./how-to-call-a-procedure-that-returns-a-value.md)
