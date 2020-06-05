---
title: 위치 및 이름으로 인수 전달
ms.date: 02/01/2018
helpviewer_keywords:
- arguments [Visual Basic], passing by name
- procedures [Visual Basic], arguments
- := passing arguments
- procedure arguments
- Visual Basic code, procedures
- named arguments [Visual Basic], passing arguments
- arguments [Visual Basic], passing by position
- Function procedures [Visual Basic], passing arguments
- named parameters [Visual Basic], passing arguments
- named arguments
- passing parameters [Visual Basic], named parameter arguments
- passing parameters [Visual Basic], by position
- procedures [Visual Basic], calling
- named parameters
- Sub procedures [Visual Basic], passing arguments
- argument passing
- passing parameters [Visual Basic], by name
- argument passing [Visual Basic], by position
- arguments [Visual Basic], listing by name
ms.assetid: 1ad7358f-1da9-48da-a95b-f3c7ed41eff3
ms.openlocfilehash: 686b64977f086c8128e56298a0ed8c5aa0c51efa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84364034"
---
# <a name="passing-arguments-by-position-and-by-name-visual-basic"></a><span data-ttu-id="7b968-102">위치 및 이름으로 인수 전달(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7b968-102">Passing Arguments by Position and by Name (Visual Basic)</span></span>

<span data-ttu-id="7b968-103">또는 프로시저를 호출 하는 경우 `Sub` `Function` 프로시저 정의에 표시 되는 순서 대로 *위치를 기준으로* 인수를 전달 하거나 위치에 관계 없이 *이름을*사용 하 여 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-103">When you call a `Sub` or `Function` procedure, you can pass arguments *by position* — in the order in which they appear in the procedure's definition — or you can pass them *by name*, without regard to position.</span></span>

<span data-ttu-id="7b968-104">이름으로 인수를 전달 하는 경우 인수의 선언 된 이름, 콜론 및 등호 ( `:=` ), 인수 값을 차례로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-104">When you pass an argument by name, you specify the argument's declared name followed by a colon and an equal sign (`:=`), followed by the argument value.</span></span> <span data-ttu-id="7b968-105">순서에 관계 없이 명명 된 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-105">You can supply named arguments in any order.</span></span>

<span data-ttu-id="7b968-106">예를 들어 다음 `Sub` 절차에서는 세 가지 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-106">For example, the following `Sub` procedure takes three arguments:</span></span>

[!code-vb[SampleProcedure](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#1)]

<span data-ttu-id="7b968-107">이 프로시저를 호출 하는 경우 인수를 이름으로 지정 하거나 둘의 조합을 사용 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-107">When you call this procedure, you can supply the arguments by position, by name, or by using a mixture of both.</span></span>

## <a name="passing-arguments-by-position"></a><span data-ttu-id="7b968-108">위치로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="7b968-108">Passing Arguments by Position</span></span>

<span data-ttu-id="7b968-109">`Display`다음 예제와 같이 위치에 의해 전달 되 고 쉼표로 구분 된 인수를 사용 하 여 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-109">You can call the `Display` method with its arguments passed by position and delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#2)]

<span data-ttu-id="7b968-110">위치 인수 목록에서 선택적 인수를 생략 하는 경우에는 쉼표를 사용 하 여 위치를 유지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-110">If you omit an optional argument in a positional argument list, you must hold its place with a comma.</span></span> <span data-ttu-id="7b968-111">다음 예제에서는 `Display` 인수를 사용 하지 않고 메서드를 호출 합니다 `age` .</span><span class="sxs-lookup"><span data-stu-id="7b968-111">The following example calls the `Display` method without the `age` argument:</span></span>

[!code-vb[ByPositionWithOptionalArgument](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#3)]

## <a name="passing-arguments-by-name"></a><span data-ttu-id="7b968-112">이름으로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="7b968-112">Passing Arguments by Name</span></span>

<span data-ttu-id="7b968-113">또는 `Display` 다음 예제와 같이 쉼표로 구분 된 이름으로 전달 된 인수를 사용 하 여를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-113">Alternatively, you can call `Display` with the arguments passed by name, also delimited by commas, as shown in the following example:</span></span>

[!code-vb[ByName](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#4)]

<span data-ttu-id="7b968-114">이러한 방법으로 인수를 전달 하는 것은 둘 이상의 선택적 인수가 있는 프로시저를 호출할 때 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-114">Passing arguments by name in this way is especially useful when you call a procedure that has more than one optional argument.</span></span> <span data-ttu-id="7b968-115">이름으로 인수를 제공 하는 경우 연속 쉼표를 사용 하 여 누락 된 위치 인수를 나타낼 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-115">If you supply arguments by name, you do not have to use consecutive commas to denote missing positional arguments.</span></span> <span data-ttu-id="7b968-116">인수를 이름으로 전달 하면 전달 하는 인수와 생략 한 인수를 쉽게 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-116">Passing arguments by name also makes it easier to keep track of which arguments you are passing and which ones you are omitting.</span></span>

## <a name="mixing-arguments-by-position-and-by-name"></a><span data-ttu-id="7b968-117">위치 및 이름으로 인수 혼합</span><span class="sxs-lookup"><span data-stu-id="7b968-117">Mixing Arguments by Position and by Name</span></span>

<span data-ttu-id="7b968-118">다음 예제와 같이 단일 프로시저 호출에서 위치 및 이름으로 인수를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-118">You can supply arguments both by position and by name in a single procedure call, as shown in the following example:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#5)]

<span data-ttu-id="7b968-119">앞의 예제에서 `age` `birth` 는 이름으로 전달 되기 때문에 생략 된 인수의 자리를 유지 하기 위해 추가 쉼표가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-119">In the preceding example, no extra comma is necessary to hold the place of the omitted `age` argument, since `birth` is passed by name.</span></span>

<span data-ttu-id="7b968-120">15.5 이전의 Visual Basic 버전에서는 위치와 이름을 혼합 하 여 인수를 제공 하면 모두 위치 인수가 먼저와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-120">In versions of Visual Basic before 15.5, when you supply arguments by a mixture of position and name, the positional arguments must all come first.</span></span> <span data-ttu-id="7b968-121">이름으로 인수를 제공한 후에는 모든 나머지 인수를 이름으로 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-121">Once you supply an argument by name, any remaining arguments must all be passed by name.</span></span>  <span data-ttu-id="7b968-122">예를 들어, 메서드에 대 한 다음 호출에서 `Display` 컴파일러 오류 [BC30241: 명명 된 인수가 필요](../../../misc/bc30241.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-122">For example, the following call to the `Display` method displays compiler error [BC30241: Named argument expected](../../../misc/bc30241.md).</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#6)]

<span data-ttu-id="7b968-123">Visual Basic 15.5부터 끝 위치 인수가 올바른 위치에 있는 경우 위치 인수는 명명 된 인수 뒤에 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-123">Starting with Visual Basic 15.5, positional arguments can follow named arguments if the ending positional arguments are in the correct position.</span></span> <span data-ttu-id="7b968-124">Visual Basic 15.5에서 컴파일된 경우 메서드에 대 한 이전 호출이 `Display` 성공적으로 컴파일되고 더 이상 컴파일러 오류 [BC30241](../../../misc/bc30241.md)생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-124">If compiled under Visual Basic 15.5, the previous call to the `Display` method compiles successfully and no longer generates compiler error [BC30241](../../../misc/bc30241.md).</span></span>

<span data-ttu-id="7b968-125">명명 된 인수와 위치 인수를 순서 대로 혼합 하 고 일치 시키는이 기능은 명명 된 인수를 사용 하 여 코드를 보다 읽기 쉽게 만드는 경우에 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-125">This ability to mix and match named and positional arguments in any order is particularly useful when you want to use a named argument to make your code more readable.</span></span> <span data-ttu-id="7b968-126">예를 들어, 다음 `Person` 클래스 생성자에는 형식의 인수가 두 개 필요 `Person` 합니다. 둘 다 일 수 있습니다 `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="7b968-126">For example, the following `Person` class constructor requires two arguments of type `Person`, both of which can be `Nothing`.</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#7)]

<span data-ttu-id="7b968-127">명명 된 인수와 위치 인수를 함께 사용 하면 `father` 및 인수의 값이 인 경우 코드의 의도를 명확 하 게 만들 수 있습니다 `mother` `Nothing` .</span><span class="sxs-lookup"><span data-stu-id="7b968-127">Using mixed named and positional arguments helps to make the intent of the code clear when the value of the `father` and `mother` arguments is `Nothing`:</span></span>

[!code-vb[ByNameAndPosition](../../../../../samples/snippets/visualbasic/programming-guide/language-features/passing-named-arguments/module1.vb#8)]

<span data-ttu-id="7b968-128">명명 된 인수를 사용 하 여 위치 인수를 따르려면 Visual Basic 프로젝트 (.vbproj) 파일에 다음 요소를 추가 해야 합니다 \* .</span><span class="sxs-lookup"><span data-stu-id="7b968-128">To follow positional arguments with named arguments, you must add the following element to your Visual Basic project (\*.vbproj) file:</span></span>

```xml
<PropertyGroup>
  <LangVersion>15.5</LangVersion>
</PropertyGroup>
```

<span data-ttu-id="7b968-129">자세한 내용은 [Visual Basic 언어 버전 설정](../../../language-reference/configure-language-version.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="7b968-129">For more information see [setting the Visual Basic language version](../../../language-reference/configure-language-version.md).</span></span>

## <a name="restrictions-on-supplying-arguments-by-name"></a><span data-ttu-id="7b968-130">이름으로 인수를 제공 하는 경우의 제한 사항</span><span class="sxs-lookup"><span data-stu-id="7b968-130">Restrictions on Supplying Arguments by Name</span></span>

<span data-ttu-id="7b968-131">필요한 인수가 입력 되지 않도록 하려면 인수를 이름으로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-131">You cannot pass arguments by name to avoid entering required arguments.</span></span> <span data-ttu-id="7b968-132">선택적 인수만 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-132">You can omit only the optional arguments.</span></span>

<span data-ttu-id="7b968-133">매개 변수 배열을 이름으로 전달할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-133">You cannot pass a parameter array by name.</span></span> <span data-ttu-id="7b968-134">이는 프로시저를 호출할 때 매개 변수 배열에 대해 쉼표로 구분 된 인수를 무제한으로 제공 하 고, 컴파일러는 단일 이름에 둘 이상의 인수를 연결할 수 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7b968-134">This is because when you call the procedure, you supply an indefinite number of comma-separated arguments for the parameter array, and the compiler cannot associate more than one argument with a single name.</span></span>

## <a name="see-also"></a><span data-ttu-id="7b968-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7b968-135">See also</span></span>

- [<span data-ttu-id="7b968-136">절차</span><span class="sxs-lookup"><span data-stu-id="7b968-136">Procedures</span></span>](./index.md)
- [<span data-ttu-id="7b968-137">프로시저 매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="7b968-137">Procedure Parameters and Arguments</span></span>](./procedure-parameters-and-arguments.md)
- [<span data-ttu-id="7b968-138">방법: 프로시저에 인수 전달</span><span class="sxs-lookup"><span data-stu-id="7b968-138">How to: Pass Arguments to a Procedure</span></span>](./how-to-pass-arguments-to-a-procedure.md)
- [<span data-ttu-id="7b968-139">값 또는 참조로 인수 전달</span><span class="sxs-lookup"><span data-stu-id="7b968-139">Passing Arguments by Value and by Reference</span></span>](./passing-arguments-by-value-and-by-reference.md)
- [<span data-ttu-id="7b968-140">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="7b968-140">Optional Parameters</span></span>](./optional-parameters.md)
- [<span data-ttu-id="7b968-141">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="7b968-141">Parameter Arrays</span></span>](./parameter-arrays.md)
- [<span data-ttu-id="7b968-142">선택 사항</span><span class="sxs-lookup"><span data-stu-id="7b968-142">Optional</span></span>](../../../language-reference/modifiers/optional.md)
- [<span data-ttu-id="7b968-143">ParamArray</span><span class="sxs-lookup"><span data-stu-id="7b968-143">ParamArray</span></span>](../../../language-reference/modifiers/paramarray.md)
