---
title: 프로시저 문제 해결
ms.date: 07/20/2015
helpviewer_keywords:
- troubleshooting Visual Basic, procedures
- procedures [Visual Basic], troubleshooting
- Visual Basic code, procedures
- troubleshooting procedures
- procedures [Visual Basic], about procedures
ms.assetid: 525721e8-2e02-4f75-b5d8-6b893462cf2b
ms.openlocfilehash: 8d4c4929e299efb12d283492a101c18ae794110b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352509"
---
# <a name="troubleshooting-procedures-visual-basic"></a><span data-ttu-id="e2409-102">프로시저 문제 해결 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e2409-102">Troubleshooting procedures (Visual Basic)</span></span>

<span data-ttu-id="e2409-103">이 페이지에는 프로시저 작업 시 발생할 수 있는 몇 가지 일반적인 문제가 나열 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-103">This page lists some common problems that can occur when working with procedures.</span></span>  
  
## <a name="returning-an-array-type-from-a-function-procedure"></a><span data-ttu-id="e2409-104">함수 프로시저에서 배열 형식 반환</span><span class="sxs-lookup"><span data-stu-id="e2409-104">Returning an array type from a function procedure</span></span>

<span data-ttu-id="e2409-105">`Function` 프로시저가 배열 데이터 형식을 반환 하는 경우에는 `Function` 이름을 사용 하 여 배열의 요소에 값을 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-105">If a `Function` procedure returns an array data type, you cannot use the `Function` name to store values in the elements of the array.</span></span> <span data-ttu-id="e2409-106">이 작업을 수행 하려고 하면 컴파일러가이를 `Function`에 대 한 호출로 해석 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-106">If you attempt to do this, the compiler interprets it as a call to the `Function`.</span></span> <span data-ttu-id="e2409-107">다음 예제에서는 컴파일러 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-107">The following example generates compiler errors:</span></span>
  
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

<span data-ttu-id="e2409-108">문이 잘못 된 데이터 형식의 인수 (`Integer` 배열 대신 스칼라 `Integer`)를 사용 하 여 `AllOnes`를 호출 하는 것으로 나타나기 때문에 컴파일러 오류가 발생 `AllOnes(i) = 1`.</span><span class="sxs-lookup"><span data-stu-id="e2409-108">The statement `AllOnes(i) = 1` generates a compiler error because it appears to call `AllOnes` with an argument of the wrong data type (a scalar `Integer` instead of an `Integer` array).</span></span> <span data-ttu-id="e2409-109">문이 인수 없이 `AllOnes`를 호출 하는 것으로 나타나기 때문에 컴파일러 오류가 발생 `Return AllOnes()`.</span><span class="sxs-lookup"><span data-stu-id="e2409-109">The statement `Return AllOnes()` generates a compiler error because it appears to call `AllOnes` with no argument.</span></span>  
  
 <span data-ttu-id="e2409-110">**올바른 방법:** 반환 될 배열의 요소를 수정할 수 있으려면 내부 배열을 지역 변수로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-110">**Correct approach:** To be able to modify the elements of an array that is to be returned, define an internal array as a local variable.</span></span> <span data-ttu-id="e2409-111">다음 예제는 오류 없이 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-111">The following example compiles without error:</span></span>

 [!code-vb[VbVbcnProcedures#66](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#66)]

## <a name="argument-not-modified-by-procedure-call"></a><span data-ttu-id="e2409-112">인수가 프로시저 호출에 의해 수정 되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-112">Argument not modified by procedure call</span></span>

<span data-ttu-id="e2409-113">프로시저에서 호출 코드의 인수를 기반으로 하는 프로그래밍 요소를 변경할 수 있도록 하려면이를 참조로 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-113">If you intend to allow a procedure to change a programming element underlying an argument in the calling code, you must pass it by reference.</span></span> <span data-ttu-id="e2409-114">그러나 프로시저는 값으로 전달 하는 경우에도 참조 형식 인수의 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-114">But a procedure can access the elements of a reference type argument even if you pass it by value.</span></span>

- <span data-ttu-id="e2409-115">**기본 변수**입니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-115">**Underlying variable**.</span></span> <span data-ttu-id="e2409-116">프로시저가 기본 변수 요소 자체의 값을 바꿀 수 있도록 하려면 프로시저에서 [ByRef](../../../language-reference/modifiers/byref.md)매개 변수를 선언 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-116">To allow the procedure to replace the value of the underlying variable element itself, the procedure must declare the parameter [ByRef](../../../language-reference/modifiers/byref.md).</span></span> <span data-ttu-id="e2409-117">또한 호출 하는 코드는 `ByRef` 전달 메커니즘을 재정의 하기 때문에 인수를 괄호로 묶지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-117">Also, the calling code must not enclose the argument in parentheses, because that would override the `ByRef` passing mechanism.</span></span>

- <span data-ttu-id="e2409-118">**참조 형식 요소**입니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-118">**Reference type elements**.</span></span> <span data-ttu-id="e2409-119">[ByVal](../../../language-reference/modifiers/byval.md)매개 변수를 선언 하는 경우 프로시저는 기본 변수 요소 자체를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-119">If you declare a parameter [ByVal](../../../language-reference/modifiers/byval.md), the procedure cannot modify the underlying variable element itself.</span></span> <span data-ttu-id="e2409-120">그러나 인수가 참조 형식인 경우 프로시저는 변수의 값을 바꿀 수 없더라도 가리키는 개체의 멤버를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-120">However, if the argument is a reference type, the procedure can modify the members of the object to which it points, even though it cannot replace the variable's value.</span></span> <span data-ttu-id="e2409-121">예를 들어 인수가 배열 변수인 경우 프로시저는 새 배열을 변수에 할당할 수 없지만 하나 이상의 요소를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-121">For example, if the argument is an array variable, the procedure cannot assign a new array to it, but it can change one or more of its elements.</span></span> <span data-ttu-id="e2409-122">변경 된 요소는 호출 코드의 기본 배열 변수에 반영 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-122">The changed elements are reflected in the underlying array variable in the calling code.</span></span>

<span data-ttu-id="e2409-123">다음 예제에서는 배열 변수를 값으로 사용 하 고 해당 요소에 대해 작동 하는 두 개의 프로시저를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-123">The following example defines two procedures that take an array variable by value and operate on its elements.</span></span> <span data-ttu-id="e2409-124">프로시저 `increase`는 각 요소에 하나씩만 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-124">Procedure `increase` simply adds one to each element.</span></span> <span data-ttu-id="e2409-125">프로시저 `replace` `a()` 매개 변수에 새 배열을 할당 한 다음 각 요소에 하나를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-125">Procedure `replace` assigns a new array to the parameter `a()` and then adds one to each element.</span></span> <span data-ttu-id="e2409-126">그러나 `a()` `ByVal`선언 되기 때문에 재할당은 호출 코드의 기본 배열 변수에 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-126">However, the reassignment does not affect the underlying array variable in the calling code because `a()` is declared `ByVal`.</span></span>

[!code-vb[VbVbcnProcedures#35](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#35)]

[!code-vb[VbVbcnProcedures#38](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#38)]

<span data-ttu-id="e2409-127">다음 예제에서는 `increase` 및 `replace`를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-127">The following example makes calls to `increase` and `replace`:</span></span>

[!code-vb[VbVbcnProcedures#37](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#37)]
  
<span data-ttu-id="e2409-128">첫 번째 `MsgBox` 호출은 "증가 (n): 11, 21, 31, 41"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-128">The first `MsgBox` call displays "After increase(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="e2409-129">`n`는 참조 형식이 기 때문에 `ByVal`전달 되더라도 해당 멤버를 변경할 수 `increase`.</span><span class="sxs-lookup"><span data-stu-id="e2409-129">Because `n` is a reference type, `increase` can change its members, even though it is passed `ByVal`.</span></span>

<span data-ttu-id="e2409-130">두 번째 `MsgBox` 호출은 "replace After (n): 11, 21, 31, 41"를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-130">The second `MsgBox` call displays "After replace(n): 11, 21, 31, 41".</span></span> <span data-ttu-id="e2409-131">`n` `ByVal`전달 되기 때문에 `replace`는 변수에 새 배열을 할당 하 여 `n` 변수를 수정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-131">Because `n` is passed `ByVal`, `replace` cannot modify the variable `n` by assigning a new array to it.</span></span> <span data-ttu-id="e2409-132">`replace` `k` 새 배열 인스턴스를 만들고이를 지역 변수 `a`에 할당 하면 호출 코드에서 전달 된 `n`에 대 한 참조가 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-132">When `replace` creates the new array instance `k` and assigns it to the local variable `a`, it loses the reference to `n` passed in by the calling code.</span></span> <span data-ttu-id="e2409-133">`a`멤버가 증가 하면 로컬 배열 `k`만 영향을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-133">When it increments the members of `a`, only the local array `k` is affected.</span></span>

<span data-ttu-id="e2409-134">**올바른 방법:** 기본 변수 요소 자체를 수정할 수 있으려면 참조로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-134">**Correct approach:** To be able to modify an underlying variable element itself, pass it by reference.</span></span> <span data-ttu-id="e2409-135">다음 예제에서는 호출 코드에서 한 배열을 다른 배열로 바꿀 수 있도록 하는 `replace` 선언 변경 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-135">The following example shows the change in the declaration of `replace` that allows it to replace one array with another in the calling code:</span></span>

[!code-vb[VbVbcnProcedures#64](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#64)]

## <a name="unable-to-define-an-overload"></a><span data-ttu-id="e2409-136">오버 로드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-136">Unable to define an overload</span></span>

<span data-ttu-id="e2409-137">프로시저의 오버 로드 된 버전을 정의 하려면 동일한 이름을 사용 하지만 다른 서명을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-137">If you want to define an overloaded version of a procedure, you must use the same name but a different signature.</span></span> <span data-ttu-id="e2409-138">컴파일러가 동일한 서명을 사용 하는 오버 로드의 선언과 구별할 수 없는 경우 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-138">If the compiler cannot differentiate your declaration from an overload with the same signature, it generates an error.</span></span>

<span data-ttu-id="e2409-139">프로시저의 *서명은* 프로시저 이름 및 매개 변수 목록에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-139">The *signature* of a procedure is determined by the procedure name and the parameter list.</span></span> <span data-ttu-id="e2409-140">각 오버 로드는 다른 모든 오버 로드와 동일한 이름을 가져야 하지만 시그니처의 다른 구성 요소 중 하나 이상에서 모든 오버 로드와 달라 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-140">Each overload must have the same name as all the other overloads but must differ from all of them in at least one of the other components of the signature.</span></span> <span data-ttu-id="e2409-141">자세한 내용은 [Procedure Overloading](./procedure-overloading.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2409-141">For more information, see [Procedure Overloading](./procedure-overloading.md).</span></span>

<span data-ttu-id="e2409-142">다음 항목은 매개 변수 목록과 관련 된 경우에도 프로시저 시그니처의 구성 요소가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-142">The following items, even though they pertain to the parameter list, are not components of a procedure's signature:</span></span>

- <span data-ttu-id="e2409-143">프로시저 한정자 키워드 (예: `Public`, `Shared`및 `Static`)</span><span class="sxs-lookup"><span data-stu-id="e2409-143">Procedure modifier keywords, such as `Public`, `Shared`, and `Static`.</span></span>
- <span data-ttu-id="e2409-144">매개 변수 이름.</span><span class="sxs-lookup"><span data-stu-id="e2409-144">Parameter names.</span></span>
- <span data-ttu-id="e2409-145">`ByRef` 및 `Optional`와 같은 매개 변수 한정자 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-145">Parameter modifier keywords, such as `ByRef` and `Optional`.</span></span>
- <span data-ttu-id="e2409-146">반환 값의 데이터 형식 (변환 연산자 제외)입니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-146">The data type of the return value (except for a conversion operator).</span></span>

<span data-ttu-id="e2409-147">위의 항목 중 하나 이상을 변경 하 여 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-147">You cannot overload a procedure by varying only one or more of the preceding items.</span></span>

<span data-ttu-id="e2409-148">**올바른 방법:** 프로시저 오버 로드를 정의 하려면 서명을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-148">**Correct approach:** To be able to define a procedure overload, you must vary the signature.</span></span> <span data-ttu-id="e2409-149">동일한 이름을 사용 해야 하므로 매개 변수의 개수, 순서 또는 데이터 형식을 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-149">Because you must use the same name, you must vary the number, order, or data types of the parameters.</span></span> <span data-ttu-id="e2409-150">제네릭 프로시저에서 형식 매개 변수의 수를 다르게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-150">In a generic procedure, you can vary the number of type parameters.</span></span> <span data-ttu-id="e2409-151">변환 연산자 ([CType 함수](../../../language-reference/functions/ctype-function.md))에서 반환 형식을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-151">In a conversion operator ([CType Function](../../../language-reference/functions/ctype-function.md)), you can vary the return type.</span></span>

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="e2409-152">선택적 및 ParamArray 인수를 사용 하는 오버 로드 확인</span><span class="sxs-lookup"><span data-stu-id="e2409-152">Overload resolution with Optional and ParamArray arguments</span></span>

<span data-ttu-id="e2409-153">하나 이상의 [선택적](../../../language-reference/modifiers/optional.md) 매개 변수 또는 [ParamArray](../../../language-reference/modifiers/paramarray.md) 매개 변수를 사용 하 여 프로시저를 오버 로드 하는 경우 *암시적 오버 로드*를 복제 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-153">If you are overloading a procedure with one or more [Optional](../../../language-reference/modifiers/optional.md) parameters or a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter, you must avoid duplicating any of the *implicit overloads*.</span></span> <span data-ttu-id="e2409-154">자세한 내용은 [오버 로드 절차의 고려 사항](./considerations-in-overloading-procedures.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2409-154">For information, see [Considerations in Overloading Procedures](./considerations-in-overloading-procedures.md).</span></span>

## <a name="calling-the-wrong-version-of-an-overloaded-procedure"></a><span data-ttu-id="e2409-155">잘못 된 버전의 오버 로드 된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="e2409-155">Calling the wrong version of an overloaded procedure</span></span>

<span data-ttu-id="e2409-156">프로시저에 오버 로드 된 버전이 여러 개 있는 경우 모든 매개 변수 목록을 숙지 하 고 Visual Basic 오버 로드 간의 호출을 확인 하는 방법을 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-156">If a procedure has several overloaded versions, you should be familiar with all their parameter lists and understand how Visual Basic resolves calls among the overloads.</span></span> <span data-ttu-id="e2409-157">그렇지 않으면 의도 한 오버 로드 이외의 오버 로드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-157">Otherwise you could call an overload other than the intended one.</span></span>

<span data-ttu-id="e2409-158">호출 하려는 오버 로드를 결정 한 후에는 다음 규칙을 유의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-158">When you have determined which overload you want to call, be careful to observe the following rules:</span></span>

- <span data-ttu-id="e2409-159">올바른 순서 대로 올바른 개수의 인수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-159">Supply the correct number of arguments, and in the correct order.</span></span>  
- <span data-ttu-id="e2409-160">가장 적합 한 인수는 해당 매개 변수와 정확히 동일한 데이터 형식을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-160">Ideally, your arguments should have the exact same data types as the corresponding parameters.</span></span> <span data-ttu-id="e2409-161">어떤 경우 든 각 인수의 데이터 형식이 해당 매개 변수의 데이터 형식으로 확장 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-161">In any case, the data type of each argument must widen to that of its corresponding parameter.</span></span> <span data-ttu-id="e2409-162">[Option Strict 문이](../../../language-reference/statements/option-strict-statement.md) `Off`로 설정 된 경우에도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-162">This is true even with the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) set to `Off`.</span></span> <span data-ttu-id="e2409-163">오버 로드에서 인수 목록에 대 한 축소 변환이 필요한 경우에는 해당 오버 로드를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-163">If an overload requires any narrowing conversion from your argument list, that overload is not eligible to be called.</span></span>
- <span data-ttu-id="e2409-164">확대/축소 해야 하는 인수를 제공 하는 경우 해당 데이터 형식을 해당 매개 변수 데이터 형식에 최대한 가깝게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-164">If you supply arguments that require widening, make their data types as close as possible to the corresponding parameter data types.</span></span> <span data-ttu-id="e2409-165">두 개 이상의 오버 로드가 인수 데이터 형식을 허용 하는 경우 컴파일러는 최소한의 확대를 호출 하는 오버 로드에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-165">If two or more overloads accept your argument data types, the compiler resolves your call to the overload that calls for the least amount of widening.</span></span>

<span data-ttu-id="e2409-166">인수를 준비할 때 [CType 함수](../../../language-reference/functions/ctype-function.md) 변환 키워드를 사용 하 여 데이터 형식이 일치 하지 않을 가능성을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-166">You can reduce the chance of data type mismatches by using the [CType Function](../../../language-reference/functions/ctype-function.md) conversion keyword when preparing your arguments.</span></span>

### <a name="overload-resolution-failure"></a><span data-ttu-id="e2409-167">오버 로드 확인 실패</span><span class="sxs-lookup"><span data-stu-id="e2409-167">Overload resolution failure</span></span>

<span data-ttu-id="e2409-168">오버 로드 된 프로시저를 호출 하는 경우 컴파일러는 오버 로드 중 하나를 제외 하 고 모두 제거 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-168">When you call an overloaded procedure, the compiler attempts to eliminate all but one of the overloads.</span></span> <span data-ttu-id="e2409-169">성공 하면 해당 오버 로드에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-169">If it succeeds, it resolves the call to that overload.</span></span> <span data-ttu-id="e2409-170">모든 오버 로드를 제거 하거나 적합 한 오버 로드를 단일 후보로 줄일 수 없는 경우 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-170">If it eliminates all the overloads, or if it cannot reduce the eligible overloads to a single candidate, it generates an error.</span></span>

<span data-ttu-id="e2409-171">다음 예제에서는 오버 로드 확인 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-171">The following example illustrates the overload resolution process:</span></span>

[!code-vb[VbVbcnProcedures#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#62)]

[!code-vb[VbVbcnProcedures#63](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#63)]
  
<span data-ttu-id="e2409-172">첫 번째 호출에서 컴파일러는 첫 번째 인수의 형식 (`Short`)이 해당 하는 매개 변수 (`Byte`)의 형식으로 축소 되기 때문에 첫 번째 오버 로드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-172">In the first call, the compiler eliminates the first overload because the type of the first argument (`Short`) narrows to the type of the corresponding parameter (`Byte`).</span></span> <span data-ttu-id="e2409-173">그런 다음 두 번째 오버 로드 (`Short` 및 `Single`)의 각 인수 형식이 세 번째 오버 로드 (`Integer` 및 `Single`)의 해당 형식으로 확대 되기 때문에 세 번째 오버 로드를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-173">It then eliminates the third overload because each argument type in the second overload (`Short` and `Single`) widens to the corresponding type in the third overload (`Integer` and `Single`).</span></span> <span data-ttu-id="e2409-174">두 번째 오버 로드는 더 적게 확대 해야 하므로 컴파일러에서 호출에이 오버 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-174">The second overload requires less widening, so the compiler uses it for the call.</span></span>

<span data-ttu-id="e2409-175">두 번째 호출에서 컴파일러는 축소를 기준으로 오버 로드를 제거할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-175">In the second call, the compiler cannot eliminate any of the overloads on the basis of narrowing.</span></span> <span data-ttu-id="e2409-176">첫 번째 호출에서와 같은 이유로 세 번째 오버 로드를 제거 합니다 .이는 두 번째 오버 로드를 사용 하 여 인수 형식의 확대/축소를 줄일 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-176">It eliminates the third overload for the same reason as in the first call, because it can call the second overload with less widening of the argument types.</span></span> <span data-ttu-id="e2409-177">그러나 컴파일러는 첫 번째 및 두 번째 오버 로드 사이를 확인할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-177">However, the compiler cannot resolve between the first and second overloads.</span></span> <span data-ttu-id="e2409-178">각에는 다른 정의 된 매개 변수 형식 (`Short`에는`Byte` 하 고 `Double``Single`)에는 해당 형식으로 확대 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-178">Each has one defined parameter type that widens to the corresponding type in the other (`Byte` to `Short`, but `Single` to `Double`).</span></span> <span data-ttu-id="e2409-179">따라서 컴파일러는 오버 로드 확인 오류를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-179">The compiler therefore generates an overload resolution error.</span></span>

<span data-ttu-id="e2409-180">**올바른 방법:** 모호성 없이 오버 로드 된 프로시저를 호출할 수 있으려면 [CType 함수](../../../language-reference/functions/ctype-function.md) 를 사용 하 여 인수 데이터 형식을 매개 변수 형식과 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-180">**Correct approach:** To be able to call an overloaded procedure without ambiguity, use [CType Function](../../../language-reference/functions/ctype-function.md) to match the argument data types to the parameter types.</span></span> <span data-ttu-id="e2409-181">다음 예제에서는 두 번째 오버 로드에 대 한 해결을 강제 적용 하는 `z`에 대 한 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-181">The following example shows a call to `z` that forces resolution to the second overload.</span></span>

[!code-vb[VbVbcnProcedures#65](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#65)]

### <a name="overload-resolution-with-optional-and-paramarray-arguments"></a><span data-ttu-id="e2409-182">선택적 및 ParamArray 인수를 사용 하는 오버 로드 확인</span><span class="sxs-lookup"><span data-stu-id="e2409-182">Overload resolution with Optional and ParamArray arguments</span></span>

<span data-ttu-id="e2409-183">프로시저의 두 오버 로드에 동일한 시그니처가 있는 경우, 즉 마지막 매개 변수가 하나에서 [선택적](../../../language-reference/modifiers/optional.md) 으로 선언 되는 경우를 제외 하 고, 컴파일러는 가장 일치 하는 [항목에 따라](../../../language-reference/modifiers/paramarray.md) 해당 프로시저에 대 한 호출을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2409-183">If two overloads of a procedure have identical signatures except that the last parameter is declared [Optional](../../../language-reference/modifiers/optional.md) in one and [ParamArray](../../../language-reference/modifiers/paramarray.md) in the other, the compiler resolves a call to that procedure according to the closest match.</span></span> <span data-ttu-id="e2409-184">자세한 내용은 [Overload Resolution](./overload-resolution.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e2409-184">For more information, see [Overload Resolution](./overload-resolution.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e2409-185">참고자료</span><span class="sxs-lookup"><span data-stu-id="e2409-185">See also</span></span>

- [<span data-ttu-id="e2409-186">절차</span><span class="sxs-lookup"><span data-stu-id="e2409-186">Procedures</span></span>](index.md)
- [<span data-ttu-id="e2409-187">Sub 프로시저</span><span class="sxs-lookup"><span data-stu-id="e2409-187">Sub Procedures</span></span>](sub-procedures.md)
- [<span data-ttu-id="e2409-188">Function 프로시저</span><span class="sxs-lookup"><span data-stu-id="e2409-188">Function Procedures</span></span>](function-procedures.md)
- [<span data-ttu-id="e2409-189">속성 프로시저</span><span class="sxs-lookup"><span data-stu-id="e2409-189">Property Procedures</span></span>](property-procedures.md)
- [<span data-ttu-id="e2409-190">연산자 프로시저</span><span class="sxs-lookup"><span data-stu-id="e2409-190">Operator Procedures</span></span>](operator-procedures.md)
- [<span data-ttu-id="e2409-191">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="e2409-191">Procedure Parameters and Arguments</span></span>](procedure-parameters-and-arguments.md)
- [<span data-ttu-id="e2409-192">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="e2409-192">Procedure Overloading</span></span>](procedure-overloading.md)
- [<span data-ttu-id="e2409-193">프로시저를 오버로드할 때 고려해야 할 사항</span><span class="sxs-lookup"><span data-stu-id="e2409-193">Considerations in Overloading Procedures</span></span>](considerations-in-overloading-procedures.md)
- [<span data-ttu-id="e2409-194">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="e2409-194">Overload Resolution</span></span>](overload-resolution.md)
