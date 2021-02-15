---
description: '자세한 정보: 매개 변수 배열 (Visual Basic)'
title: 매개 변수 배열
ms.date: 07/20/2015
helpviewer_keywords:
- parameter arrays [Visual Basic], about parameter arrays
- ParamArray keyword [Visual Basic], parameter arrays
- Visual Basic code, procedures
- parameters [Visual Basic], parameter arrays
- arguments [Visual Basic], parameter arrays
- procedures [Visual Basic], indefinite number of argument values
- arrays [Visual Basic], parameter arrays
ms.assetid: c43edfae-9114-4096-9ebc-8c5c957a1067
ms.openlocfilehash: e71524d9d62f0ece3a8310934eba15e9db16aaa1
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100427585"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="29ad0-103">매개 변수 배열(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="29ad0-103">Parameter Arrays (Visual Basic)</span></span>

<span data-ttu-id="29ad0-104">일반적으로 프로시저 선언에서 지정 하는 것 보다 더 많은 인수를 사용 하 여 프로시저를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-104">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="29ad0-105">무제한 개수의 인수가 필요한 경우 프로시저에서 매개 변수에 대 한 값 배열을 허용할 수 있도록 *매개 변수 배열을* 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-105">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="29ad0-106">프로시저를 정의할 때 매개 변수 배열의 요소 수를 몰라도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-106">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="29ad0-107">배열 크기는 프로시저를 호출할 때마다 개별적으로 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-107">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="29ad0-108">ParamArray 선언</span><span class="sxs-lookup"><span data-stu-id="29ad0-108">Declaring a ParamArray</span></span>  

 <span data-ttu-id="29ad0-109">[ParamArray](../../../language-reference/modifiers/paramarray.md) 키워드를 사용 하 여 매개 변수 목록에서 매개 변수 배열을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-109">You use the [ParamArray](../../../language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="29ad0-110">다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-110">The following rules apply:</span></span>  
  
- <span data-ttu-id="29ad0-111">프로시저는 하나의 매개 변수 배열만 정의할 수 있으며 프로시저 정의에서 마지막 매개 변수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-111">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
- <span data-ttu-id="29ad0-112">매개 변수 배열은 값으로 전달 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-112">The parameter array must be passed by value.</span></span> <span data-ttu-id="29ad0-113">프로시저 정의에 [ByVal](../../../language-reference/modifiers/byval.md) 키워드를 명시적으로 포함 하는 것이 좋은 프로그래밍 습관입니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-113">It is good programming practice to explicitly include the [ByVal](../../../language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
- <span data-ttu-id="29ad0-114">매개 변수 배열은 자동으로 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-114">The parameter array is automatically optional.</span></span> <span data-ttu-id="29ad0-115">기본값은 매개 변수 배열의 요소 형식에 대 한 빈 1 차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-115">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
- <span data-ttu-id="29ad0-116">매개 변수 배열 앞의 모든 매개 변수는 필수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-116">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="29ad0-117">매개 변수 배열은 유일한 선택적 매개 변수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-117">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="29ad0-118">ParamArray 호출</span><span class="sxs-lookup"><span data-stu-id="29ad0-118">Calling a ParamArray</span></span>  

 <span data-ttu-id="29ad0-119">매개 변수 배열을 정의 하는 프로시저를 호출 하는 경우 다음 중 한 가지 방법으로 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-119">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
- <span data-ttu-id="29ad0-120">아무 작업도 수행 하지 않습니다. 즉, [ParamArray](../../../language-reference/modifiers/paramarray.md) 인수를 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-120">Nothing — that is, you can omit the [ParamArray](../../../language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="29ad0-121">이 경우 빈 배열이 프로시저에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-121">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="29ad0-122">[Nothing](../../../language-reference/nothing.md) 키워드를 명시적으로 전달 하면 null 배열이 프로시저에 전달 되 고 호출 된 프로시저에서이 조건을 확인 하지 않는 경우 NullReferenceException이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-122">If you explicitly pass the [Nothing](../../../language-reference/nothing.md) keyword, a null array is passed to the procedure and may result in a NullReferenceException if the called procedure does not check for this condition.</span></span>
  
- <span data-ttu-id="29ad0-123">쉼표로 구분 된 임의 개수의 인수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-123">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="29ad0-124">각 인수의 데이터 형식은 요소 형식으로 암시적으로 변환할 수 있어야 합니다 `ParamArray` .</span><span class="sxs-lookup"><span data-stu-id="29ad0-124">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
- <span data-ttu-id="29ad0-125">매개 변수 배열의 요소 형식과 동일한 요소 형식의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-125">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="29ad0-126">모든 경우에서 프로시저 내의 코드는 매개 변수 배열을 데이터 형식과 동일한 데이터 형식의 요소가 포함 된 1 차원 배열로 처리 합니다 `ParamArray` .</span><span class="sxs-lookup"><span data-stu-id="29ad0-126">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="29ad0-127">무한정 클 수 있는 배열을 처리할 때마다 응용 프로그램의 내부 용량을 overrunning 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-127">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="29ad0-128">매개 변수 배열을 허용 하는 경우 호출 코드에서 전달 된 배열의 크기를 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-128">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="29ad0-129">응용 프로그램에 너무 클 경우 적절 한 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-129">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="29ad0-130">자세한 내용은 [배열](../arrays/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="29ad0-130">For more information, see [Arrays](../arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="29ad0-131">예</span><span class="sxs-lookup"><span data-stu-id="29ad0-131">Example</span></span>  

 <span data-ttu-id="29ad0-132">다음 예제에서는 함수를 정의 하 고 호출 합니다 `calcSum` .</span><span class="sxs-lookup"><span data-stu-id="29ad0-132">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="29ad0-133">`ParamArray`매개 변수에 대 한 한정자를 `args` 사용 하면 함수에서 다양 한 수의 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-133">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="29ad0-134">다음 예제에서는 매개 변수 배열을 사용 하 여 프로시저를 정의 하 고 매개 변수 배열에 전달 된 모든 배열 요소의 값을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="29ad0-134">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="29ad0-135">추가 정보</span><span class="sxs-lookup"><span data-stu-id="29ad0-135">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="29ad0-136">절차</span><span class="sxs-lookup"><span data-stu-id="29ad0-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="29ad0-137">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="29ad0-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="29ad0-138">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="29ad0-138">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="29ad0-139">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="29ad0-139">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="29ad0-140">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="29ad0-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="29ad0-141">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="29ad0-141">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="29ad0-142">배열</span><span class="sxs-lookup"><span data-stu-id="29ad0-142">Arrays</span></span>](../arrays/index.md)
- [<span data-ttu-id="29ad0-143">선택 사항</span><span class="sxs-lookup"><span data-stu-id="29ad0-143">Optional</span></span>](../../../language-reference/modifiers/optional.md)
