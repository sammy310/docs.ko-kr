---
description: '자세한 정보: 프로시저 오버 로드 시 고려 사항 (Visual Basic)'
title: 프로시저 오버로드에서 고려해야 할 사항
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
ms.openlocfilehash: ee6dc0ce23f0706f52ac58673d37d1b72936d2bc
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100472620"
---
# <a name="considerations-in-overloading-procedures-visual-basic"></a><span data-ttu-id="5d84a-103">프로시저를 오버로드할 때 고려해야 할 사항(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5d84a-103">Considerations in Overloading Procedures (Visual Basic)</span></span>

<span data-ttu-id="5d84a-104">프로시저를 오버 로드 하는 경우 오버 로드 된 각 버전에 대해 다른 *서명을* 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-104">When you overload a procedure, you must use a different *signature* for each overloaded version.</span></span> <span data-ttu-id="5d84a-105">이는 일반적으로 각 버전이 서로 다른 매개 변수 목록을 지정 해야 함을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-105">This usually means each version must specify a different parameter list.</span></span> <span data-ttu-id="5d84a-106">자세한 내용은 [프로시저 오버 로드](./procedure-overloading.md)에서 "다른 서명"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d84a-106">For more information, see "Different Signature" in [Procedure Overloading](./procedure-overloading.md).</span></span>  
  
 <span data-ttu-id="5d84a-107">다른 서명이 있는 경우 프로시저를 프로시저에 오버 로드 `Function` 하거나 그 반대의 경우에는 프로시저를 오버 로드할 수 있습니다 `Sub` .</span><span class="sxs-lookup"><span data-stu-id="5d84a-107">You can overload a `Function` procedure with a `Sub` procedure, and vice versa, provided they have different signatures.</span></span> <span data-ttu-id="5d84a-108">두 오버 로드는 반환 값을 가지 며 다른 오버 로드는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-108">Two overloads cannot differ only in that one has a return value and the other does not.</span></span>  
  
 <span data-ttu-id="5d84a-109">프로시저를 오버 로드 하는 것과 동일한 방식으로 속성을 오버 로드 하 여 동일한 제한 사항을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-109">You can overload a property the same way you overload a procedure, and with the same restrictions.</span></span> <span data-ttu-id="5d84a-110">그러나 속성을 사용 하 여 프로시저를 오버 로드할 수 없으며 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-110">However, you cannot overload a procedure with a property, or vice versa.</span></span>  
  
## <a name="alternatives-to-overloaded-versions"></a><span data-ttu-id="5d84a-111">오버 로드 된 버전의 대안</span><span class="sxs-lookup"><span data-stu-id="5d84a-111">Alternatives to Overloaded Versions</span></span>  

 <span data-ttu-id="5d84a-112">경우에 따라 오버 로드 된 버전에 대 한 대안이 있을 수 있습니다. 특히 인수 유무는 선택 사항이 나 변수의 숫자가 가변적 일 때입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-112">You sometimes have alternatives to overloaded versions, particularly when the presence of arguments is optional or their number is variable.</span></span>  
  
 <span data-ttu-id="5d84a-113">선택적 인수는 모든 언어에서 반드시 지원 되는 것은 아니며 매개 변수 배열은 Visual Basic로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-113">Keep in mind that optional arguments are not necessarily supported by all languages, and parameter arrays are limited to Visual Basic.</span></span> <span data-ttu-id="5d84a-114">여러 다른 언어로 작성 된 코드에서 호출 될 수 있는 프로시저를 작성 하는 경우 오버 로드 된 버전이 가장 큰 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-114">If you are writing a procedure that is likely to be called from code written in any of several different languages, overloaded versions offer the greatest flexibility.</span></span>  
  
### <a name="overloads-and-optional-arguments"></a><span data-ttu-id="5d84a-115">오버 로드 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="5d84a-115">Overloads and Optional Arguments</span></span>  

 <span data-ttu-id="5d84a-116">호출 코드에서 하나 이상의 인수를 선택적으로 제공 하거나 생략할 수 있는 경우 여러 오버 로드 된 버전을 정의 하거나 선택적 매개 변수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-116">When the calling code can optionally supply or omit one or more arguments, you can define multiple overloaded versions or use optional parameters.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="5d84a-117">오버 로드 된 버전을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="5d84a-117">When to Use Overloaded Versions</span></span>  

 <span data-ttu-id="5d84a-118">다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-118">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="5d84a-119">프로시저 코드의 논리는 호출 코드에서 선택적 인수를 제공 하는지 여부에 따라 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-119">The logic in the procedure code is significantly different depending on whether the calling code supplies an optional argument or not.</span></span>  
  
- <span data-ttu-id="5d84a-120">프로시저 코드는 호출 코드에서 선택적 인수를 제공 했는지 여부를 안정적으로 테스트할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-120">The procedure code cannot reliably test whether the calling code has supplied an optional argument.</span></span> <span data-ttu-id="5d84a-121">예를 들어, 호출 코드에서 제공 하지 않을 수 있는 기본 값에 대해 가능한 후보가 없는 경우이 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-121">This is the case, for example, if there is no possible candidate for a default value that the calling code could not be expected to supply.</span></span>  
  
#### <a name="when-to-use-optional-parameters"></a><span data-ttu-id="5d84a-122">선택적 매개 변수를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="5d84a-122">When to Use Optional Parameters</span></span>  

 <span data-ttu-id="5d84a-123">다음과 같은 경우 하나 이상의 선택적 매개 변수를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-123">You might prefer one or more optional parameters in the following cases:</span></span>  
  
- <span data-ttu-id="5d84a-124">호출 하는 코드에서 선택적 인수를 제공 하지 않는 경우에만 필요한 작업은 매개 변수를 기본값으로 설정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-124">The only required action when the calling code does not supply an optional argument is to set the parameter to a default value.</span></span> <span data-ttu-id="5d84a-125">이 경우 하나 이상의 매개 변수를 사용 하 여 단일 버전을 정의 하는 경우 프로시저 코드가 더 복잡할 수 있습니다 `Optional` .</span><span class="sxs-lookup"><span data-stu-id="5d84a-125">In such a case, the procedure code can be less complicated if you define a single version with one or more `Optional` parameters.</span></span>  
  
 <span data-ttu-id="5d84a-126">자세한 내용은 [선택적 매개 변수](./optional-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d84a-126">For more information, see [Optional Parameters](./optional-parameters.md).</span></span>  
  
### <a name="overloads-and-paramarrays"></a><span data-ttu-id="5d84a-127">오버 로드 및 ParamArrays</span><span class="sxs-lookup"><span data-stu-id="5d84a-127">Overloads and ParamArrays</span></span>  

 <span data-ttu-id="5d84a-128">호출 코드에서 다양 한 수의 인수를 전달할 수 있는 경우 여러 오버 로드 된 버전을 정의 하거나 매개 변수 배열을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-128">When the calling code can pass a variable number of arguments, you can define multiple overloaded versions or use a parameter array.</span></span>  
  
#### <a name="when-to-use-overloaded-versions"></a><span data-ttu-id="5d84a-129">오버 로드 된 버전을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="5d84a-129">When to Use Overloaded Versions</span></span>  

 <span data-ttu-id="5d84a-130">다음과 같은 경우에는 일련의 오버 로드 된 버전을 정의 하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-130">You can consider defining a series of overloaded versions in the following cases:</span></span>  
  
- <span data-ttu-id="5d84a-131">호출 코드가 매개 변수 배열에 적은 수의 값을 더 이상 전달 하지 않는다는 것을 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-131">You know that the calling code never passes more than a small number of values to the parameter array.</span></span>  
  
- <span data-ttu-id="5d84a-132">프로시저 코드의 논리는 호출 코드가 전달 하는 값의 수에 따라 크게 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-132">The logic in the procedure code is significantly different depending on how many values the calling code passes.</span></span>  
  
- <span data-ttu-id="5d84a-133">호출 하는 코드는 서로 다른 데이터 형식의 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-133">The calling code can pass values of different data types.</span></span>  
  
#### <a name="when-to-use-a-parameter-array"></a><span data-ttu-id="5d84a-134">매개 변수 배열을 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="5d84a-134">When to Use a Parameter Array</span></span>  

 <span data-ttu-id="5d84a-135">`ParamArray`다음과 같은 경우에는 매개 변수를 통해 더 효율적으로 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-135">You are better served by a `ParamArray` parameter in the following cases:</span></span>  
  
- <span data-ttu-id="5d84a-136">호출 코드가 매개 변수 배열에 전달할 수 있는 값의 수를 예측할 수 없으며 숫자가 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-136">You are not able to predict how many values the calling code can pass to the parameter array, and it could be a large number.</span></span>  
  
- <span data-ttu-id="5d84a-137">프로시저 논리는 호출 코드가 전달 하는 모든 값을 반복 하 여 기본적으로 모든 값에 대해 동일한 작업을 수행 하는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-137">The procedure logic lends itself to iterating through all the values the calling code passes, performing essentially the same operations on every value.</span></span>  
  
 <span data-ttu-id="5d84a-138">자세한 내용은 [매개 변수 배열](./parameter-arrays.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="5d84a-138">For more information, see [Parameter Arrays](./parameter-arrays.md).</span></span>  
  
## <a name="implicit-overloads-for-optional-parameters"></a><span data-ttu-id="5d84a-139">선택적 매개 변수에 대 한 암시적 오버 로드</span><span class="sxs-lookup"><span data-stu-id="5d84a-139">Implicit Overloads for Optional Parameters</span></span>  

 <span data-ttu-id="5d84a-140">[선택적](../../../language-reference/modifiers/optional.md) 매개 변수를 사용 하는 프로시저는 두 개의 오버 로드 된 프로시저와 동일 합니다. 하나는 선택적 매개 변수를 포함 하 고 하나는 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-140">A procedure with an [Optional](../../../language-reference/modifiers/optional.md) parameter is equivalent to two overloaded procedures, one with the optional parameter and one without it.</span></span> <span data-ttu-id="5d84a-141">이러한 프로시저 중 하나에 해당 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-141">You cannot overload such a procedure with a parameter list corresponding to either of these.</span></span> <span data-ttu-id="5d84a-142">다음 선언에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-142">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#58](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#58)]  
  
 [!code-vb[VbVbcnProcedures#60](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#60)]  
  
 [!code-vb[VbVbcnProcedures#61](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#61)]  
  
 <span data-ttu-id="5d84a-143">선택적 매개 변수를 두 개 이상 사용 하는 프로시저의 경우 앞의 예제와 비슷한 논리를 통해 도착 하는 암시적 오버 로드 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-143">For a procedure with more than one optional parameter, there is a set of implicit overloads, arrived at by logic similar to that in the preceding example.</span></span>  
  
## <a name="implicit-overloads-for-a-paramarray-parameter"></a><span data-ttu-id="5d84a-144">ParamArray 매개 변수에 대 한 암시적 오버 로드</span><span class="sxs-lookup"><span data-stu-id="5d84a-144">Implicit Overloads for a ParamArray Parameter</span></span>  

 <span data-ttu-id="5d84a-145">컴파일러는 다음과 같이 호출 코드가 매개 변수 배열에 전달 하는 것과는 다른 [매개 변수를](../../../language-reference/modifiers/paramarray.md) 사용 하 여 오버 로드 수를 무한대로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-145">The compiler considers a procedure with a [ParamArray](../../../language-reference/modifiers/paramarray.md) parameter to have an infinite number of overloads, differing from each other in what the calling code passes to the parameter array, as follows:</span></span>  
  
- <span data-ttu-id="5d84a-146">호출 코드가에 인수를 제공 하지 않는 경우의 오버 로드 하나 `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="5d84a-146">One overload for when the calling code does not supply an argument to the `ParamArray`</span></span>  
  
- <span data-ttu-id="5d84a-147">호출 코드가 요소 형식의 1 차원 배열을 제공할 때의 오버 로드 하나 `ParamArray`</span><span class="sxs-lookup"><span data-stu-id="5d84a-147">One overload for when the calling code supplies a one-dimensional array of the `ParamArray` element type</span></span>  
  
- <span data-ttu-id="5d84a-148">모든 양의 정수에 대해 호출 코드가 해당 개수의 인수를 제공 하는 경우에 대 한 오버 로드 하나는 각 `ParamArray` 요소 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-148">For every positive integer, one overload for when the calling code supplies that number of arguments, each of the `ParamArray` element type</span></span>  
  
 <span data-ttu-id="5d84a-149">다음 선언에서는 이러한 암시적 오버 로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-149">The following declarations illustrate these implicit overloads.</span></span>  
  
 [!code-vb[VbVbcnProcedures#68](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#68)]  
  
 [!code-vb[VbVbcnProcedures#70](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#70)]  
  
 <span data-ttu-id="5d84a-150">매개 변수 배열에 1 차원 배열을 사용 하는 매개 변수 목록을 사용 하 여 이러한 프로시저를 오버 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-150">You cannot overload such a procedure with a parameter list that takes a one-dimensional array for the parameter array.</span></span> <span data-ttu-id="5d84a-151">그러나 다른 암시적 오버 로드의 시그니처를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-151">However, you can use the signatures of the other implicit overloads.</span></span> <span data-ttu-id="5d84a-152">다음 선언에서는이를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-152">The following declarations illustrate this.</span></span>  
  
 [!code-vb[VbVbcnProcedures#71](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#71)]  
  
## <a name="typeless-programming-as-an-alternative-to-overloading"></a><span data-ttu-id="5d84a-153">오버 로드에 대 한 대 안으로 형식이 없는 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="5d84a-153">Typeless Programming as an Alternative to Overloading</span></span>  

 <span data-ttu-id="5d84a-154">호출 코드가 다른 데이터 형식을 매개 변수에 전달할 수 있게 하려는 경우 다른 방법으로는 형식이 없는 프로그래밍이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-154">If you want to allow the calling code to pass different data types to a parameter, an alternative approach is typeless programming.</span></span> <span data-ttu-id="5d84a-155">`Off` [Option strict 문](../../../language-reference/statements/option-strict-statement.md) 또는 [-옵션 strict](../../../reference/command-line-compiler/optionstrict.md) 컴파일러 옵션을 사용 하 여 형식 검사 스위치를로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-155">You can set the type checking switch to `Off` with either the [Option Strict Statement](../../../language-reference/statements/option-strict-statement.md) or the [-optionstrict](../../../reference/command-line-compiler/optionstrict.md) compiler option.</span></span> <span data-ttu-id="5d84a-156">그런 다음 매개 변수의 데이터 형식을 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-156">Then you do not have to declare the parameter's data type.</span></span> <span data-ttu-id="5d84a-157">그러나이 방법은 오버 로드에 비해 다음과 같은 단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-157">However, this approach has the following disadvantages compared to overloading:</span></span>  
  
- <span data-ttu-id="5d84a-158">형식이 없는 프로그래밍은 효율성이 떨어지는 실행 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-158">Typeless programming produces less efficient execution code.</span></span>  
  
- <span data-ttu-id="5d84a-159">프로시저는 전달 될 것으로 예상 되는 모든 데이터 형식에 대해 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-159">The procedure must test for every data type it anticipates being passed.</span></span>  
  
- <span data-ttu-id="5d84a-160">호출 하는 코드가 프로시저에서 지원 하지 않는 데이터 형식을 전달 하는 경우 컴파일러에서 오류를 알릴 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5d84a-160">The compiler cannot signal an error if the calling code passes a data type that the procedure does not support.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d84a-161">추가 정보</span><span class="sxs-lookup"><span data-stu-id="5d84a-161">See also</span></span>

- [<span data-ttu-id="5d84a-162">절차</span><span class="sxs-lookup"><span data-stu-id="5d84a-162">Procedures</span></span>](./index.md)
- [<span data-ttu-id="5d84a-163">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="5d84a-163">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="5d84a-164">프로시저 문제 해결</span><span class="sxs-lookup"><span data-stu-id="5d84a-164">Troubleshooting Procedures</span></span>](./troubleshooting-procedures.md)
- [<span data-ttu-id="5d84a-165">방법: 여러 버전의 프로시저 정의</span><span class="sxs-lookup"><span data-stu-id="5d84a-165">How to: Define Multiple Versions of a Procedure</span></span>](./how-to-define-multiple-versions-of-a-procedure.md)
- [<span data-ttu-id="5d84a-166">방법: 오버로드된 프로시저 호출</span><span class="sxs-lookup"><span data-stu-id="5d84a-166">How to: Call an Overloaded Procedure</span></span>](./how-to-call-an-overloaded-procedure.md)
- [<span data-ttu-id="5d84a-167">방법: 선택적 매개 변수를 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="5d84a-167">How to: Overload a Procedure that Takes Optional Parameters</span></span>](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [<span data-ttu-id="5d84a-168">방법: 매개 변수를 무제한으로 사용하는 프로시저 오버로드</span><span class="sxs-lookup"><span data-stu-id="5d84a-168">How to: Overload a Procedure that Takes an Indefinite Number of Parameters</span></span>](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [<span data-ttu-id="5d84a-169">Overload Resolution</span><span class="sxs-lookup"><span data-stu-id="5d84a-169">Overload Resolution</span></span>](./overload-resolution.md)
- [<span data-ttu-id="5d84a-170">오버로드</span><span class="sxs-lookup"><span data-stu-id="5d84a-170">Overloads</span></span>](../../../language-reference/modifiers/overloads.md)
