---
title: 프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures [Visual Basic], ParamArray arguments
- ParamArray keyword [Visual Basic], parameter arrays
- ParamArray keyword [Visual Basic], arguments and signatures
- function overloading [Visual Basic], implicit overloads for ParamArray
- ParamArray keyword [Visual Basic], signatures
- Visual Basic code, procedures
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], overloading
- parameters [Visual Basic], lists
- function overloading [Visual Basic], typeless programming
- typeless programming
- function overloading [Visual Basic], restrictions
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], overloading
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- parameter arrays [Visual Basic], overloading arguments
- Visual Basic code, parameter lists
- procedure overloading [Visual Basic], considerations
- Option Explicit statement [Visual Basic]
- restrictions [Visual Basic], overloading procedures
- procedures [Visual Basic], parameter lists
ms.assetid: a2001248-10d0-42c5-b0ce-eeedc987319f
ms.openlocfilehash: bd5b0032ca63ccb2f2cc30d72a5b3f3c7eb3c346
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "72775733"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="60b98-102">프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="60b98-102">Considerations in Overloading Procedures (Visual Basic)</span></span>
<span data-ttu-id="60b98-103">프로시저를 오버 로드 하는 경우 오버 로드 된 각 버전에 대해 다른 *서명을* 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-103">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="60b98-104">이는 일반적으로 각 버전이 서로 다른 매개 변수 목록을 지정 해야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-104">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="60b98-105">자세한 내용은 [프로시저 오버 로드](./procedure-overloading.md)에서 "다른 서명"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60b98-105">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="60b98-106">@No__t_1 프로시저를 사용 하 여 `Function` 프로시저를 오버 로드할 수 있으며, 다른 시그니처가 있는 경우 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-106">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="60b98-107">두 오버 로드는 반환 값을 가지 며 다른 오버 로드는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-107">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="60b98-108">프로시저를 오버 로드 하는 것과 동일한 방식으로 속성을 오버 로드 하 여 동일한 제한 사항을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-108">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="60b98-109">그러나 속성을 사용 하 여 프로시저를 오버 로드할 수 없으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-109">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="60b98-110">오버 로드 된 버전의 대안</span><span class="sxs-lookup"><span data-stu-id="60b98-110">Alternatives to Overloaded Versions</span></span>  
 <span data-ttu-id="60b98-111">경우에 따라 오버 로드 된 버전에 대 한 대안이 있을 수 있습니다. 특히 인수 유무는 선택 사항이 나 변수의 숫자가 가변적 일 때입니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-111">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="60b98-112">선택적 인수는 모든 언어에서 반드시 지원 되는 것은 아니며 매개 변수 배열은 Visual Basic로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-112">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="60b98-113">여러 다른 언어로 작성 된 코드에서 호출 될 수 있는 프로시저를 작성 하는 경우 오버 로드 된 버전이 가장 큰 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-113">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="60b98-114">오버 로드 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="60b98-114">Overloads and Optional Arguments</span></span>  
 <span data-ttu-id="60b98-115">호출 코드에서 하나 이상의 인수를 선택적으로 제공 하거나 생략할 수 있는 경우 여러 오버 로드 된 버전을 정의 하거나 선택적 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-115">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="60b98-116">오버 로드 된 버전을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="60b98-116">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="60b98-117">다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-117">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="60b98-118">프로시저 코드의 논리는 호출 코드에서 선택적 인수를 제공 하는지 여부에 따라 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-118">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
- <span data-ttu-id="60b98-119">프로시저 코드는 호출 코드에서 선택적 인수를 제공 했는지 여부를 안정적으로 테스트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-119">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="60b98-120">예를 들어, 호출 코드에서 제공 하지 않을 수 있는 기본 값에 대해 가능한 후보가 없는 경우이 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-120">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="60b98-121">선택적 매개 변수를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="60b98-121">When to Use Optional Parameters</span></span>  
 <span data-ttu-id="60b98-122">다음과 같은 경우 하나 이상의 선택적 매개 변수를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-122">You might prefer one or more optional parameters in the following cases:</span></span>  
  
- <span data-ttu-id="60b98-123">호출 하는 코드에서 선택적 인수를 제공 하지 않는 경우에만 필요한 작업은 매개 변수를 기본값으로 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-123">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="60b98-124">이 경우 하나 이상의 `Optional` 매개 변수를 사용 하 여 단일 버전을 정의 하는 경우 프로시저 코드가 더 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-124">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="60b98-125">자세한 내용은 [선택적 매개 변수](./optional-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60b98-125">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="60b98-126">오버 로드 및 ParamArrays</span><span class="sxs-lookup"><span data-stu-id="60b98-126">Overloads and ParamArrays</span></span>  
 <span data-ttu-id="60b98-127">호출 코드에서 다양 한 수의 인수를 전달할 수 있는 경우 여러 오버 로드 된 버전을 정의 하거나 매개 변수 배열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-127">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="60b98-128">오버 로드 된 버전을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="60b98-128">When to Use Overloaded Versions</span></span>  
 <span data-ttu-id="60b98-129">다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-129">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="60b98-130">호출 코드가 매개 변수 배열에 적은 수의 값을 더 이상 전달 하지 않는다는 것을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-130">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
- <span data-ttu-id="60b98-131">프로시저 코드의 논리는 호출 코드가 전달 하는 값의 수에 따라 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-131">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
- <span data-ttu-id="60b98-132">호출 하는 코드는 서로 다른 데이터 형식의 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-132">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="60b98-133">매개 변수 배열을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="60b98-133">When to Use a Parameter Array</span></span>  
 <span data-ttu-id="60b98-134">다음과 같은 경우에는 `ParamArray` 매개 변수를 통해 더 효율적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-134">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
- <span data-ttu-id="60b98-135">호출 코드가 매개 변수 배열에 전달할 수 있는 값의 수를 예측할 수 없으며 숫자가 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-135">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
- <span data-ttu-id="60b98-136">프로시저 논리는 호출 코드가 전달 하는 모든 값을 반복 하 여 기본적으로 모든 값에 대해 동일한 작업을 수행 하는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-136">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="60b98-137">자세한 내용은 [매개 변수 배열](./parameter-arrays.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="60b98-137">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="60b98-138">선택적 매개 변수에 대 한 암시적 오버 로드</span><span class="sxs-lookup"><span data-stu-id="60b98-138">Implicit Overloads for Optional Parameters</span></span>  
 <span data-ttu-id="60b98-139">[선택적](../../../../visual-basic/language-reference/modifiers/optional.md) 매개 변수를 사용 하는 프로시저는 두 개의 오버 로드 된 프로시저와 동일 합니다. 하나는 선택적 매개 변수를 포함 하 고 하나는 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-139">A procedure with an [Optional](../../../../visual-basic/language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="60b98-140">이러한 프로시저 중 하나에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-140">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="60b98-141">다음 선언에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-141">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="60b98-142">선택적 매개 변수를 두 개 이상 사용 하는 프로시저의 경우 앞의 예제와 비슷한 논리를 통해 도착 하는 암시적 오버 로드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-142">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="60b98-143">ParamArray 매개 변수에 대 한 암시적 오버 로드</span><span class="sxs-lookup"><span data-stu-id="60b98-143">Implicit Overloads for a ParamArray Parameter</span></span>  
 <span data-ttu-id="60b98-144">컴파일러는 다음과 같이 호출 코드가 매개 변수 배열에 전달 하는 것과는 다른 [매개 변수를](../../../../visual-basic/language-reference/modifiers/paramarray.md) 사용 하 여 오버 로드 수를 무한대로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-144">The compiler considers a procedure with a [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
- <span data-ttu-id="60b98-145">호출 코드가 `ParamArray`에 인수를 제공 하지 않는 경우에 대 한 오버 로드</span><span class="sxs-lookup"><span data-stu-id="60b98-145">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
- <span data-ttu-id="60b98-146">호출 코드가 `ParamArray` 요소 형식의 1 차원 배열을 제공할 때의 오버 로드 하나</span><span class="sxs-lookup"><span data-stu-id="60b98-146">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
- <span data-ttu-id="60b98-147">모든 양의 정수에 대해 호출 코드에서 해당 개수의 인수를 제공 하는 경우에 대 한 오버 로드 하나는 각 `ParamArray` 요소 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-147">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="60b98-148">다음 선언에서는 이러한 암시적 오버 로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-148">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="60b98-149">매개 변수 배열에 1 차원 배열을 사용 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-149">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="60b98-150">그러나 다른 암시적 오버 로드의 시그니처를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-150">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="60b98-151">다음 선언에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-151">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="60b98-152">오버 로드에 대 한 대 안으로 형식이 없는 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="60b98-152">Typeless Programming as an Alternative to Overloading</span></span>  
 <span data-ttu-id="60b98-153">호출 코드가 다른 데이터 형식을 매개 변수에 전달할 수 있게 하려는 경우 다른 방법으로는 형식이 없는 프로그래밍이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-153">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="60b98-154">[Option Strict 문](../../../../visual-basic/language-reference/statements/option-strict-statement.md) 또는 [-옵션 strict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 사용 하 여 형식 확인 스위치를 `Off`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-154">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) or the [-optionstrict](../../../../visual-basic/reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="60b98-155">그런 다음 매개 변수의 데이터 형식을 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-155">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="60b98-156">그러나이 방법은 오버 로드에 비해 다음과 같은 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-156">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
- <span data-ttu-id="60b98-157">형식이 없는 프로그래밍은 효율성이 떨어지는 실행 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-157">Typeless programming produces less efficient execution code.</span></span>  
  
- <span data-ttu-id="60b98-158">프로시저는 전달 될 것으로 예상 되는 모든 데이터 형식에 대해 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-158">The procedure must test for every data type it anticipates being passed.</span></span>  
  
- <span data-ttu-id="60b98-159">호출 하는 코드가 프로시저에서 지원 하지 않는 데이터 형식을 전달 하는 경우 컴파일러에서 오류를 알릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="60b98-159">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60b98-160">참조</span><span class="sxs-lookup"><span data-stu-id="60b98-160">See also</span></span>

- [<span data-ttu-id="60b98-161">절차</span><span class="sxs-lookup"><span data-stu-id="60b98-161">Procedures</span></span>](./index.md)
- [<span data-ttu-id="60b98-162">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="60b98-162">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="60b98-163">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="60b98-163">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="60b98-164">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="60b98-164">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="60b98-165">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="60b98-165">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="60b98-166">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="60b98-166">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="60b98-167">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="60b98-167">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="60b98-168">오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="60b98-168">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="60b98-169">오버로드</span><span class="sxs-lookup"><span data-stu-id="60b98-169">Overloads</span></span>](../../../../visual-basic/language-reference/modifiers/overloads.md)
