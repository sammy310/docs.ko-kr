---
description: '자세한 정보: 문제 해결 절차 (Visual Basic)'
title: 프로시저 문제 해결
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: a36e2ef9442fc0e76c9a98e83007976393e7957b
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100471151"
---
# <a name="troubleshooting-procedures-visual-basic"></a><span data-ttu-id="58129-103">프로시저 문제 해결 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="58129-103">Troubleshooting procedures (Visual Basic)</span></span>

<span data-ttu-id="58129-104">이 페이지에는 프로시저 작업 시 발생할 수 있는 몇 가지 일반적인 문제가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-104">This page lists some common problems that can occur when working with procedures.</span></span>  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a><span data-ttu-id="58129-105">함수 프로시저에서 배열 형식 반환</span><span class="sxs-lookup"><span data-stu-id="58129-105">Returning an array type from a function procedure</span></span>

<span data-ttu-id="58129-106">프로시저에서 `Function` 배열 데이터 형식을 반환 하는 경우 이름을 사용 하 여 `Function` 배열의 요소에 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-106">If a `Function` procedure returns an array data type, you cannot use the `Function` name to store values in the elements of the array.</span></span> <span data-ttu-id="58129-107">이 작업을 수행 하려고 하면 컴파일러가이를에 대 한 호출로 해석 합니다 `Function` .</span><span class="sxs-lookup"><span data-stu-id="58129-107">If you attempt to do this, the compiler interprets it as a call to the `Function`.</span></span> <span data-ttu-id="58129-108">다음 예제에서는 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-108">The following example generates compiler errors:</span></span>
  
```vb
Function AllOnes(n As Integer) As Integer()
   For i As Integer = 1 To n - 1  
      ' The following statement generates a COMPILER ERROR.  
      AllOnes(i) = 1  
   Next  

   ' The following statement generates a COMPILER ERROR.  
   Return AllOnes()  
End Function
```

<span data-ttu-id="58129-109">문은 `AllOnes(i) = 1` `AllOnes` 잘못 된 데이터 형식의 인수 (배열 대신 스칼라)를 사용 하 여를 호출 하는 것 처럼 보이지만 컴파일러 오류를 생성 `Integer` `Integer` 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-109">The statement `AllOnes(i) = 1` generates a compiler error because it appears to call `AllOnes` with an argument of the wrong data type (a scalar `Integer` instead of an `Integer` array).</span></span> <span data-ttu-id="58129-110">문은 `Return AllOnes()` 인수 없이를 호출 하는 것 처럼 보이지만 컴파일러 오류를 생성 합니다 `AllOnes` .</span><span class="sxs-lookup"><span data-stu-id="58129-110">The statement `Return AllOnes()` generates a compiler error because it appears to call `AllOnes` with no argument.</span></span>  
  
 <span data-ttu-id="58129-111">**올바른 방법:** 반환 될 배열의 요소를 수정할 수 있으려면 내부 배열을 지역 변수로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-111">**Correct approach:** To be able to modify the elements of an array that is to be returned, define an internal array as a local variable.</span></span> <span data-ttu-id="58129-112">다음 예제는 오류 없이 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="58129-112">The following example compiles without error:</span></span>

 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]

## <a name="argument-not-modified-by-procedure-call"></a><span data-ttu-id="58129-113">인수가 프로시저 호출에 의해 수정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-113">Argument not modified by procedure call</span></span>

<span data-ttu-id="58129-114">프로시저에서 호출 코드의 인수를 기반으로 하는 프로그래밍 요소를 변경할 수 있도록 하려면이를 참조로 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-114">If you intend to allow a procedure to change a programming element underlying an argument in the calling code, you must pass it by reference.</span></span> <span data-ttu-id="58129-115">그러나 프로시저는 값으로 전달 하는 경우에도 참조 형식 인수의 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-115">But a procedure can access the elements of a reference type argument even if you pass it by value.</span></span>

- <span data-ttu-id="58129-116">**기본 변수** 입니다.</span><span class="sxs-lookup"><span data-stu-id="58129-116">**Underlying variable**.</span></span> <span data-ttu-id="58129-117">프로시저가 기본 변수 요소 자체의 값을 바꿀 수 있도록 하려면 프로시저에서 [ByRef](../../../language-reference/modifiers/byref.md)매개 변수를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-117">To allow the procedure to replace the value of the underlying variable element itself, the procedure must declare the parameter [ByRef](../../../language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="58129-118">또한 호출 하는 코드는 전달 메커니즘을 재정의 하기 때문에 인수를 괄호로 묶지 않아야 합니다 `ByRef` .</span><span class="sxs-lookup"><span data-stu-id="58129-118">Also, the calling code must not enclose the argument in parentheses, because that would override the `ByRef` passing mechanism.</span></span>

- <span data-ttu-id="58129-119">**참조 형식 요소** 입니다.</span><span class="sxs-lookup"><span data-stu-id="58129-119">**Reference type elements**.</span></span> <span data-ttu-id="58129-120">[ByVal](../../../language-reference/modifiers/byval.md)매개 변수를 선언 하는 경우 프로시저는 기본 변수 요소 자체를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-120">If you declare a parameter [ByVal](../../../language-reference/modifiers/byval.md), the procedure cannot modify the underlying variable element itself.</span></span> <span data-ttu-id="58129-121">그러나 인수가 참조 형식인 경우 프로시저는 변수의 값을 바꿀 수 없더라도 가리키는 개체의 멤버를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-121">However, if the argument is a reference type, the procedure can modify the members of the object to which it points, even though it cannot replace the variable's value.</span></span> <span data-ttu-id="58129-122">예를 들어 인수가 배열 변수인 경우 프로시저는 새 배열을 변수에 할당할 수 없지만 하나 이상의 요소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-122">For example, if the argument is an array variable, the procedure cannot assign a new array to it, but it can change one or more of its elements.</span></span> <span data-ttu-id="58129-123">변경 된 요소는 호출 코드의 기본 배열 변수에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58129-123">The changed elements are reflected in the underlying array variable in the calling code.</span></span>

<span data-ttu-id="58129-124">다음 예제에서는 배열 변수를 값으로 사용 하 고 해당 요소에 대해 작동 하는 두 개의 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-124">The following example defines two procedures that take an array variable by value and operate on its elements.</span></span> <span data-ttu-id="58129-125">프로시저는 `increase` 각 요소에 하나씩만 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-125">Procedure `increase` simply adds one to each element.</span></span> <span data-ttu-id="58129-126">프로시저는 `replace` 새 배열을 매개 변수에 할당 한 `a()` 다음 각 요소에 하나를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-126">Procedure `replace` assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="58129-127">그러나가 선언 되었기 때문에 재할당은 호출 코드의 기본 배열 변수에 영향을 주지 않습니다 `a()` `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="58129-127">However, the reassignment does not affect the underlying array variable in the calling code because `a()` is declared `ByVal`.</span></span>

[!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]

[!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]

<span data-ttu-id="58129-128">다음 예제에서는 및에 대 한 호출을 수행 합니다 `increase` `replace` .</span><span class="sxs-lookup"><span data-stu-id="58129-128">The following example makes calls to `increase` and `replace`:</span></span>

[!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]
  
<span data-ttu-id="58129-129">첫 번째 `MsgBox` 호출은 "증가 (n): 11, 21, 31, 41"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-129">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="58129-130">`n`는 참조 형식이 기 때문에 `increase` 전달 된 경우에도 해당 멤버를 변경할 수 있습니다 `ByVal` .</span><span class="sxs-lookup"><span data-stu-id="58129-130">Because `n` is a reference type, `increase` can change its members, even though it is passed `ByVal`.</span></span>

<span data-ttu-id="58129-131">두 번째 `MsgBox` 호출은 "Replace After (n): 11, 21, 31, 41"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-131">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="58129-132">가 전달 되기 때문에는 `n` `ByVal` `replace` 새 배열을 할당 하 여 변수를 수정할 수 없습니다 `n` .</span><span class="sxs-lookup"><span data-stu-id="58129-132">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` by assigning a new array to it.</span></span> <span data-ttu-id="58129-133">에서 `replace` 새 배열 인스턴스를 만들고 `k` 지역 변수에 할당 하면 `a` 호출 코드에서 전달 하는 참조가 손실 `n` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58129-133">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="58129-134">의 멤버가 증가 하면 `a` 로컬 배열에만 `k` 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58129-134">When it increments the members of `a`, only the local array `k` is affected.</span></span>

<span data-ttu-id="58129-135">**올바른 방법:** 기본 변수 요소 자체를 수정할 수 있으려면 참조로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-135">**Correct approach:** To be able to modify an underlying variable element itself, pass it by reference.</span></span> <span data-ttu-id="58129-136">다음 예제에서는 `replace` 호출 코드에서 한 배열을 다른 배열로 바꿀 수 있도록 하는의 선언 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58129-136">The following example shows the change in the declaration of `replace` that allows it to replace one array with another in the calling code:</span></span>

[!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]

## <a name="unable-to-define-an-overload"></a><span data-ttu-id="58129-137">오버 로드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-137">Unable to define an overload</span></span>

<span data-ttu-id="58129-138">프로시저의 오버 로드 된 버전을 정의 하려면 동일한 이름을 사용 하지만 다른 서명을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-138">If you want to define an overloaded version of a procedure, you must use the same name but a different signature.</span></span> <span data-ttu-id="58129-139">컴파일러가 동일한 서명을 사용 하는 오버 로드의 선언과 구별할 수 없는 경우 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-139">If the compiler cannot differentiate your declaration from an overload with the same signature, it generates an error.</span></span>

<span data-ttu-id="58129-140">프로시저의 *서명은* 프로시저 이름 및 매개 변수 목록에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="58129-140">The *signature* of a procedure is determined by the procedure name and the parameter list.</span></span> <span data-ttu-id="58129-141">각 오버 로드는 다른 모든 오버 로드와 동일한 이름을 가져야 하지만 시그니처의 다른 구성 요소 중 하나 이상에서 모든 오버 로드와 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-141">Each overload must have the same name as all the other overloads but must differ from all of them in at least one of the other components of the signature.</span></span> <span data-ttu-id="58129-142">자세한 내용은 [Procedure Overloading](./procedure-overloading.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58129-142">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>

<span data-ttu-id="58129-143">다음 항목은 매개 변수 목록과 관련 된 경우에도 프로시저 시그니처의 구성 요소가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="58129-143">The following items, even though they pertain to the parameter list, are not components of a procedure's signature:</span></span>

- <span data-ttu-id="58129-144">프로시저 한정자 키워드 (예: `Public` , `Shared` 및) `Static`</span><span class="sxs-lookup"><span data-stu-id="58129-144">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`.</span></span>
- <span data-ttu-id="58129-145">매개 변수 이름.</span><span class="sxs-lookup"><span data-stu-id="58129-145">Parameter names.</span></span>
- <span data-ttu-id="58129-146">매개 변수 한정자 키워드 (예: `ByRef` 및) `Optional`</span><span class="sxs-lookup"><span data-stu-id="58129-146">Parameter modifier keywords, such as `ByRef` and `Optional`.</span></span>
- <span data-ttu-id="58129-147">반환 값의 데이터 형식 (변환 연산자 제외)입니다.</span><span class="sxs-lookup"><span data-stu-id="58129-147">The data type of the return value (except for a conversion operator).</span></span>

<span data-ttu-id="58129-148">위의 항목 중 하나 이상을 변경 하 여 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-148">You cannot overload a procedure by varying only one or more of the preceding items.</span></span>

<span data-ttu-id="58129-149">**올바른 방법:** 프로시저 오버 로드를 정의 하려면 서명을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-149">**Correct approach:** To be able to define a procedure overload, you must vary the signature.</span></span> <span data-ttu-id="58129-150">동일한 이름을 사용 해야 하므로 매개 변수의 개수, 순서 또는 데이터 형식을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-150">Because you must use the same name, you must vary the number, order, or data types of the parameters.</span></span> <span data-ttu-id="58129-151">제네릭 프로시저에서 형식 매개 변수의 수를 다르게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-151">In a generic procedure, you can vary the number of type parameters.</span></span> <span data-ttu-id="58129-152">변환 연산자 ([CType 함수](../../../language-reference/functions/ctype-function.md))에서 반환 형식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-152">In a conversion operator ([CType Function](../../../language-reference/functions/ctype-function.md)), you can vary the return type.</span></span>

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="58129-153">선택적 및 ParamArray 인수를 사용 하는 오버 로드 확인</span><span class="sxs-lookup"><span data-stu-id="58129-153">Overload resolution with Optional and ParamArray arguments</span></span>

<span data-ttu-id="58129-154">하나 이상의 [선택적](../../../language-reference/modifiers/optional.md) 매개 변수 또는 [ParamArray](../../../language-reference/modifiers/paramarray.md) 매개 변수를 사용 하 여 프로시저를 오버 로드 하는 경우 *암시적 오버 로드* 를 복제 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-154">If you are overloading a procedure with one or more [Optional](../../../language-reference/modifiers/optional.md) parameters or a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter, you must avoid duplicating any of the *implicit overloads*.</span></span> <span data-ttu-id="58129-155">자세한 내용은 [오버 로드 절차의 고려 사항](./considerations-in-overloading-procedures.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="58129-155">For information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>

## <a name="calling-the-wrong-version-of-an-overloaded-procedure"></a><span data-ttu-id="58129-156">잘못 된 버전의 오버 로드 된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="58129-156">Calling the wrong version of an overloaded procedure</span></span>

<span data-ttu-id="58129-157">프로시저에 오버 로드 된 버전이 여러 개 있는 경우 모든 매개 변수 목록을 숙지 하 고 Visual Basic 오버 로드 간의 호출을 확인 하는 방법을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-157">If a procedure has several overloaded versions, you should be familiar with all their parameter lists and understand how Visual Basic resolves calls among the overloads.</span></span> <span data-ttu-id="58129-158">그렇지 않으면 의도 한 오버 로드 이외의 오버 로드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-158">Otherwise you could call an overload other than the intended one.</span></span>

<span data-ttu-id="58129-159">호출 하려는 오버 로드를 결정 한 후에는 다음 규칙을 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-159">When you have determined which overload you want to call, be careful to observe the following rules:</span></span>

- <span data-ttu-id="58129-160">올바른 순서 대로 올바른 개수의 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-160">Supply the correct number of arguments, and in the correct order.</span></span>  
- <span data-ttu-id="58129-161">가장 적합 한 인수는 해당 매개 변수와 정확히 동일한 데이터 형식을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-161">Ideally, your arguments should have the exact same data types as the corresponding parameters.</span></span> <span data-ttu-id="58129-162">어떤 경우 든 각 인수의 데이터 형식이 해당 매개 변수의 데이터 형식으로 확장 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-162">In any case, the data type of each argument must widen to that of its corresponding parameter.</span></span> <span data-ttu-id="58129-163">[Option Strict 문이](../../../language-reference/statements/option-strict-statement.md) 로 설정 된 경우에도 마찬가지입니다 `Off` .</span><span class="sxs-lookup"><span data-stu-id="58129-163">This is true even with the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) set to `Off`.</span></span> <span data-ttu-id="58129-164">오버 로드에서 인수 목록에 대 한 축소 변환이 필요한 경우에는 해당 오버 로드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-164">If an overload requires any narrowing conversion from your argument list, that overload is not eligible to be called.</span></span>
- <span data-ttu-id="58129-165">확대/축소 해야 하는 인수를 제공 하는 경우 해당 데이터 형식을 해당 매개 변수 데이터 형식에 최대한 가깝게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="58129-165">If you supply arguments that require widening, make their data types as close as possible to the corresponding parameter data types.</span></span> <span data-ttu-id="58129-166">두 개 이상의 오버 로드가 인수 데이터 형식을 허용 하는 경우 컴파일러는 최소한의 확대를 호출 하는 오버 로드에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-166">If two or more overloads accept your argument data types, the compiler resolves your call to the overload that calls for the least amount of widening.</span></span>

<span data-ttu-id="58129-167">인수를 준비할 때 [CType 함수](../../../language-reference/functions/ctype-function.md) 변환 키워드를 사용 하 여 데이터 형식이 일치 하지 않을 가능성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-167">You can reduce the chance of data type mismatches by using the [CType Function](../../../language-reference/functions/ctype-function.md) conversion keyword when preparing your arguments.</span></span>

### <a name="overload-resolution-failure"></a><span data-ttu-id="58129-168">오버 로드 확인 실패</span><span class="sxs-lookup"><span data-stu-id="58129-168">Overload resolution failure</span></span>

<span data-ttu-id="58129-169">오버 로드 된 프로시저를 호출 하는 경우 컴파일러는 오버 로드 중 하나를 제외 하 고 모두 제거 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-169">When you call an overloaded procedure, the compiler attempts to eliminate all but one of the overloads.</span></span> <span data-ttu-id="58129-170">성공 하면 해당 오버 로드에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-170">If it succeeds, it resolves the call to that overload.</span></span> <span data-ttu-id="58129-171">모든 오버 로드를 제거 하거나 적합 한 오버 로드를 단일 후보로 줄일 수 없는 경우 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-171">If it eliminates all the overloads, or if it cannot reduce the eligible overloads to a single candidate, it generates an error.</span></span>

<span data-ttu-id="58129-172">다음 예제에서는 오버 로드 확인 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58129-172">The following example illustrates the overload resolution process:</span></span>

[!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]

[!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]
  
<span data-ttu-id="58129-173">첫 번째 호출에서 컴파일러는 첫 번째 인수 ()의 형식이 `Short` 해당 매개 변수 ()의 형식으로 축소 되기 때문에 첫 번째 오버 로드를 제거 합니다 `Byte` .</span><span class="sxs-lookup"><span data-stu-id="58129-173">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="58129-174">그런 다음 두 번째 오버 로드 (및)의 각 인수 형식이 세 번째 `Short` 오버 `Single` 로드 (및)에서 해당 형식으로 확대 되기 때문에 세 번째 오버 로드를 제거 합니다 `Integer` `Single` .</span><span class="sxs-lookup"><span data-stu-id="58129-174">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="58129-175">두 번째 오버 로드는 더 적게 확대 해야 하므로 컴파일러에서 호출에이 오버 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-175">The second overload requires less widening, so the compiler uses it for the call.</span></span>

<span data-ttu-id="58129-176">두 번째 호출에서 컴파일러는 축소를 기준으로 오버 로드를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-176">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="58129-177">첫 번째 호출에서와 같은 이유로 세 번째 오버 로드를 제거 합니다 .이는 두 번째 오버 로드를 사용 하 여 인수 형식의 확대/축소를 줄일 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="58129-177">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="58129-178">그러나 컴파일러는 첫 번째 및 두 번째 오버 로드 사이를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="58129-178">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="58129-179">각각에는 다른의 해당 형식으로 확대 되는 하나의 정의 된 매개 변수 형식이 있습니다 ( `Byte` `Short` 에서로 `Single` `Double` ).</span><span class="sxs-lookup"><span data-stu-id="58129-179">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="58129-180">따라서 컴파일러는 오버 로드 확인 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-180">The compiler therefore generates an overload resolution error.</span></span>

<span data-ttu-id="58129-181">**올바른 방법:** 모호성 없이 오버 로드 된 프로시저를 호출할 수 있으려면 [CType 함수](../../../language-reference/functions/ctype-function.md) 를 사용 하 여 인수 데이터 형식을 매개 변수 형식과 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="58129-181">**Correct approach:** To be able to call an overloaded procedure without ambiguity, use [CType Function](../../../language-reference/functions/ctype-function.md) to match the argument data types to the parameter types.</span></span> <span data-ttu-id="58129-182">다음 예제에서는 `z` 두 번째 오버 로드에 대 한 해결을 강제 하는 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="58129-182">The following example shows a call to `z` that forces resolution to the second overload.</span></span>

[!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="58129-183">선택적 및 ParamArray 인수를 사용 하는 오버 로드 확인</span><span class="sxs-lookup"><span data-stu-id="58129-183">Overload resolution with Optional and ParamArray arguments</span></span>

<span data-ttu-id="58129-184">프로시저의 두 오버 로드에 동일한 시그니처가 있는 경우, 즉 마지막 매개 변수가 하나에서 [선택적](../../../language-reference/modifiers/optional.md) 으로 선언 되는 경우를 제외 하 고, 컴파일러는 가장 일치 하는 [항목에 따라](../../../language-reference/modifiers/paramarray.md) 해당 프로시저에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="58129-184">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../language-reference/modifiers/optional.md) in one and [ParamArray](../../../language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure according to the closest match.</span></span> <span data-ttu-id="58129-185">자세한 내용은 [Overload Resolution](./overload-resolution.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="58129-185">For more information, see [Overload Resolution](./overload-resolution.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="58129-186">추가 정보</span><span class="sxs-lookup"><span data-stu-id="58129-186">See also</span></span>

- [<span data-ttu-id="58129-187">절차</span><span class="sxs-lookup"><span data-stu-id="58129-187">Procedures</span></span>](index.md)
- [<span data-ttu-id="58129-188">하위 프로시저</span><span class="sxs-lookup"><span data-stu-id="58129-188">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="58129-189">함수 프로시저</span><span class="sxs-lookup"><span data-stu-id="58129-189">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="58129-190">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="58129-190">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="58129-191">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="58129-191">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="58129-192">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="58129-192">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="58129-193">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="58129-193">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="58129-194">프로시저 오버로드에서 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="58129-194">Considerations in Overloading Procedures</span></span>](considerations-in-overloading-procedures.md)
- [<span data-ttu-id="58129-195">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="58129-195">Overload Resolution</span></span>](overload-resolution.md)
