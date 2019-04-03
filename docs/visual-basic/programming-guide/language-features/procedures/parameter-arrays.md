---
title: 매개 변수 배열(Visual Basic)
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
ms.openlocfilehash: 8ea4c77056701b8f61c1ed5a53cf20d98ae913bc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58834167"
---
# <a name="parameter-arrays-visual-basic"></a><span data-ttu-id="414f0-102">매개 변수 배열(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="414f0-102">Parameter Arrays (Visual Basic)</span></span>
<span data-ttu-id="414f0-103">일반적으로 프로시저 선언에 지정 하는 보다 많은 인수를 사용 하 여 프로시저를 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-103">Usually, you cannot call a procedure with more arguments than the procedure declaration specifies.</span></span> <span data-ttu-id="414f0-104">불특정 개수의 인수를 해야 하는 경우 선언 수를 *매개 변수 배열*, 프로시저 매개 변수에 대해 값의 배열에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-104">When you need an indefinite number of arguments, you can declare a *parameter array*, which allows a procedure to accept an array of values for a parameter.</span></span> <span data-ttu-id="414f0-105">프로시저를 정의 하는 경우 매개 변수 배열의 요소 수를 알 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-105">You do not have to know the number of elements in the parameter array when you define the procedure.</span></span> <span data-ttu-id="414f0-106">배열 크기는 개별적으로 각 프로시저를 호출 하 여 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-106">The array size is determined individually by each call to the procedure.</span></span>  
  
## <a name="declaring-a-paramarray"></a><span data-ttu-id="414f0-107">ParamArray 선언</span><span class="sxs-lookup"><span data-stu-id="414f0-107">Declaring a ParamArray</span></span>  
 <span data-ttu-id="414f0-108">사용 된 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 매개 변수 목록의 매개 변수 배열을 나타내는 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-108">You use the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) keyword to denote a parameter array in the parameter list.</span></span> <span data-ttu-id="414f0-109">이 때 적용되는 규칙은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-109">The following rules apply:</span></span>  
  
-   <span data-ttu-id="414f0-110">프로시저 매개 변수 배열을 하나만 정의 하 고 프로시저 정의의 마지막 매개 변수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-110">A procedure can define only one parameter array, and it must be the last parameter in the procedure definition.</span></span>  
  
-   <span data-ttu-id="414f0-111">매개 변수 배열의 값으로 전달 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-111">The parameter array must be passed by value.</span></span> <span data-ttu-id="414f0-112">바람직한 프로그래밍 습관을 명시적으로 포함 하는 것은 [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) 프로시저 정의에서 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-112">It is good programming practice to explicitly include the [ByVal](../../../../visual-basic/language-reference/modifiers/byval.md) keyword in the procedure definition.</span></span>  
  
-   <span data-ttu-id="414f0-113">매개 변수 배열은 자동으로 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-113">The parameter array is automatically optional.</span></span> <span data-ttu-id="414f0-114">기본값은 빈 1 차원 배열 매개 변수 배열의 요소 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-114">Its default value is an empty one-dimensional array of the parameter array's element type.</span></span>  
  
-   <span data-ttu-id="414f0-115">모든 매개 변수 배열 앞에 오는 매개 변수는 필수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-115">All parameters preceding the parameter array must be required.</span></span> <span data-ttu-id="414f0-116">매개 변수 배열에만 선택적 매개 변수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-116">The parameter array must be the only optional parameter.</span></span>  
  
## <a name="calling-a-paramarray"></a><span data-ttu-id="414f0-117">ParamArray를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-117">Calling a ParamArray</span></span>  
 <span data-ttu-id="414f0-118">매개 변수 배열을 정의 하는 프로시저를 호출 하는 경우에 다음 방법 중 하나에 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-118">When you call a procedure that defines a parameter array, you can supply the argument in any one of the following ways:</span></span>  
  
-   <span data-ttu-id="414f0-119">Nothing-이므로 생략할 수 있습니다 합니다 [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-119">Nothing — that is, you can omit the [ParamArray](../../../../visual-basic/language-reference/modifiers/paramarray.md) argument.</span></span> <span data-ttu-id="414f0-120">이 경우 빈 배열은 프로시저에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-120">In this case, an empty array is passed to the procedure.</span></span> <span data-ttu-id="414f0-121">전달할 수도 있습니다는 [Nothing](../../../../visual-basic/language-reference/nothing.md) 키워드를 결과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-121">You can also pass the [Nothing](../../../../visual-basic/language-reference/nothing.md) keyword, with the same effect.</span></span>  
  
-   <span data-ttu-id="414f0-122">임의 개수의 인수를 쉼표로 구분 된 목록.</span><span class="sxs-lookup"><span data-stu-id="414f0-122">A list of an arbitrary number of arguments, separated by commas.</span></span> <span data-ttu-id="414f0-123">각 인수의 데이터 형식을 암시적으로 변환할 수 있어야 합니다 `ParamArray` 요소 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-123">The data type of each argument must be implicitly convertible to the `ParamArray` element type.</span></span>  
  
-   <span data-ttu-id="414f0-124">매개 변수 배열의 요소 형식과 동일한 요소 형식의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-124">An array with the same element type as the parameter array's element type.</span></span>  
  
 <span data-ttu-id="414f0-125">동일한 데이터 형식의 요소를 사용 하 여 1 차원 배열로 프로시저 내에서 코드 처리 매개 변수 배열의 모든 경우에는 `ParamArray` 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-125">In all cases, the code within the procedure treats the parameter array as a one-dimensional array with elements of the same data type as the `ParamArray` data type.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="414f0-126">무한정 커질 수 있는 배열을 사용 하 여 처리할 때마다 응용 프로그램의 일부 내부 용량 오버런이 위험이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-126">Whenever you deal with an array which can be indefinitely large, there is a risk of overrunning some internal capacity of your application.</span></span> <span data-ttu-id="414f0-127">매개 변수 배열에 동의 하는 경우 호출 코드에서 전달 된 배열 크기에 대 한 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-127">If you accept a parameter array, you should test for the size of the array that the calling code passed to it.</span></span> <span data-ttu-id="414f0-128">응용 프로그램에 비해 너무 큰 경우 적절 한 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-128">Take appropriate steps if it is too large for your application.</span></span> <span data-ttu-id="414f0-129">자세한 내용은 [배열](../../../../visual-basic/programming-guide/language-features/arrays/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-129">For more information, see [Arrays](../../../../visual-basic/programming-guide/language-features/arrays/index.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="414f0-130">예제</span><span class="sxs-lookup"><span data-stu-id="414f0-130">Example</span></span>  
 <span data-ttu-id="414f0-131">다음 예제에서는 정의 하 고 함수를 호출 `calcSum`합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-131">The following example defines and calls the function `calcSum`.</span></span> <span data-ttu-id="414f0-132">합니다 `ParamArray` 매개 변수 한정자 `args` 가변 개수의 인수를 수락 하는 함수를 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-132">The `ParamArray` modifier for the parameter `args` enables the function to accept a variable number of arguments.</span></span>  
  
 [!code-vb[VbVbalrStatements#26](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#26)]  
  
 <span data-ttu-id="414f0-133">다음 예제에서는 매개 변수 배열에 있는 프로시저를 정의 하 고 매개 변수 배열에 전달 되는 모든 배열 요소 값을 출력 합니다.</span><span class="sxs-lookup"><span data-stu-id="414f0-133">The following example defines a procedure with a parameter array, and outputs the values of all the array elements passed to the parameter array.</span></span>  
  
 [!code-vb[VbVbcnProcedures#48](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#48)]  
  
 [!code-vb[VbVbcnProcedures#49](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#49)]  
  
## <a name="see-also"></a><span data-ttu-id="414f0-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="414f0-134">See also</span></span>

- <xref:Microsoft.VisualBasic.Information.UBound%2A>
- [<span data-ttu-id="414f0-135">절차</span><span class="sxs-lookup"><span data-stu-id="414f0-135">Procedures</span></span>](./index.md)
- [<span data-ttu-id="414f0-136">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="414f0-136">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="414f0-137">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="414f0-137">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="414f0-138">위치 및 이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="414f0-138">Passing Arguments by Position and by Name</span></span>](./passing-arguments-by-position-and-by-name.md)
- [<span data-ttu-id="414f0-139">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="414f0-139">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="414f0-140">프로시저 오버로딩</span><span class="sxs-lookup"><span data-stu-id="414f0-140">Procedure Overloading</span></span>](./procedure-overloading.md)
- [<span data-ttu-id="414f0-141">배열</span><span class="sxs-lookup"><span data-stu-id="414f0-141">Arrays</span></span>](../../../../visual-basic/programming-guide/language-features/arrays/index.md)
- [<span data-ttu-id="414f0-142">선택 사항</span><span class="sxs-lookup"><span data-stu-id="414f0-142">Optional</span></span>](../../../../visual-basic/language-reference/modifiers/optional.md)
