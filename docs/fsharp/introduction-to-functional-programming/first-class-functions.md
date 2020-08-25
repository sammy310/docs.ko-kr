---
title: 첫 번째 클래스 함수
description: '첫 번째 클래스 함수와 F #의 함수형 프로그래밍에 중요 한 기능에 대해 알아봅니다.'
ms.date: 10/29/2018
ms.openlocfilehash: 1dc8eae1655187282f05bf4e9501ecc8a17deba8
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88810913"
---
# <a name="first-class-functions"></a><span data-ttu-id="cc0de-103">첫 번째 클래스 함수</span><span class="sxs-lookup"><span data-stu-id="cc0de-103">First-class functions</span></span>

<span data-ttu-id="cc0de-104">함수형 프로그래밍 언어의 특성을 정의 하는 것은 함수를 첫 번째 클래스 상태로 승격 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-104">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="cc0de-105">다른 기본 제공 형식의 값으로 수행할 수 있는 함수를 사용 하 여이 작업을 수행할 수 있어야 하 고, 비슷한 노력으로이 작업을 수행할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-105">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="cc0de-106">첫 번째 클래스 상태의 일반적인 측정값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-106">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="cc0de-107">함수를 식별자에 바인딩할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="cc0de-107">Can you bind functions to identifiers?</span></span> <span data-ttu-id="cc0de-108">즉, 이름을 지정할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="cc0de-108">That is, can you give them names?</span></span>

- <span data-ttu-id="cc0de-109">함수를 데이터 구조 (예: 목록)에 저장할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="cc0de-109">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="cc0de-110">함수 호출에서 함수를 인수로 전달할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="cc0de-110">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="cc0de-111">함수 호출에서 함수를 반환할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="cc0de-111">Can you return a function from a function call?</span></span>

<span data-ttu-id="cc0de-112">마지막 두 측정값은 *고차 작업* 또는 *고차 함수*라고 하는 항목을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-112">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="cc0de-113">고차 함수는 함수를 인수로 받아들이고 함수 호출 값으로 함수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-113">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="cc0de-114">이러한 작업은 함수를 매핑하고 함수를 구성 하는 등의 함수형 프로그래밍 개체인 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-114">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>

## <a name="give-the-value-a-name"></a><span data-ttu-id="cc0de-115">값에 이름을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-115">Give the Value a Name</span></span>

<span data-ttu-id="cc0de-116">함수가 첫 번째 클래스 값 이면 정수, 문자열 및 기타 기본 제공 형식의 이름을 지정할 때와 마찬가지로 이름을 지정할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-116">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="cc0de-117">이는 함수 프로그래밍 자료에서 값에 식별자를 바인딩하는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-117">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="cc0de-118">F #은 [ `let` 바인딩을](../language-reference/functions/let-bindings.md) 사용 하 여 이름을 값에 `let <identifier> = <value>` 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-118">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="cc0de-119">다음 코드에서는 두 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-119">The following code shows two examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="cc0de-120">함수 이름을 쉽게 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-120">You can name a function just as easily.</span></span> <span data-ttu-id="cc0de-121">다음 예제에서는 `squareIt` 식별자를 `squareIt` [람다 식](../language-reference/functions/lambda-expressions-the-fun-keyword.md) 에 바인딩하여 이라는 함수를 정의 합니다 `fun n -> n * n` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-121">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="cc0de-122">함수는 `squareIt` 하나의 매개 변수를 포함 `n` 하며 해당 매개 변수의 제곱을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-122">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="cc0de-123">F #은 다음과 같은 더 간결한 구문을 제공 하 여 입력이 적고 동일한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-123">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="cc0de-124">다음에 나오는 예제에서는 대개 첫 번째 스타일을 사용 `let <function-name> = <lambda-expression>` 하 여 함수 선언과 다른 형식의 값 선언 간의 유사성을 강조 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-124">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="cc0de-125">그러나 모든 명명 된 함수를 간결한 구문으로 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-125">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="cc0de-126">일부 예제는 두 가지 방법으로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-126">Some of the examples are written in both ways.</span></span>

## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="cc0de-127">데이터 구조에 값 저장</span><span class="sxs-lookup"><span data-stu-id="cc0de-127">Store the Value in a Data Structure</span></span>

<span data-ttu-id="cc0de-128">데이터 구조에는 첫 번째 클래스 값을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-128">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="cc0de-129">다음 코드에서는 목록 및 튜플에 값을 저장 하는 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-129">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="cc0de-130">튜플에 저장 된 함수 이름이 실제로 함수를 계산 하는지 확인 하기 위해 다음 예제에서는 및 연산자를 사용 하 여 `fst` `snd` 튜플의 첫 번째와 두 번째 요소를 추출 합니다 `funAndArgTuple` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-130">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="cc0de-131">튜플의 첫 번째 요소는이 `squareIt` 고 두 번째 요소는 `num` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-131">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="cc0de-132">식별자 `num` 는 이전 예제에서 함수에 대 한 유효한 인수인 정수 10에 바인딩됩니다 `squareIt` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-132">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="cc0de-133">두 번째 식은 튜플의 첫 번째 요소를 튜플의 두 번째 요소에 적용 `squareIt num` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-133">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="cc0de-134">마찬가지로 식별자와 `num` 정수 10은 서로 바꿔 사용할 수 있으므로 식별자 `squareIt` 와 람다 식을 사용할 수 있습니다 `fun n -> n * n` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-134">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="cc0de-135">값을 인수로 전달 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-135">Pass the Value as an Argument</span></span>

<span data-ttu-id="cc0de-136">값이 언어의 첫 번째 클래스 상태 이면 해당 값을 함수에 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-136">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="cc0de-137">예를 들어 정수 및 문자열을 인수로 전달 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-137">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="cc0de-138">다음 코드에서는 F #에서 인수로 전달 된 정수 및 문자열을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-138">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="cc0de-139">함수에 최고 수준의 상태가 있는 경우 동일한 방식으로 해당 함수를 인수로 전달할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-139">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="cc0de-140">이는 고차 함수의 첫 번째 특징입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-140">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="cc0de-141">다음 예제에서 함수에는 `applyIt` 및 라는 두 개의 매개 변수가 있습니다 `op` `arg` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-141">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="cc0de-142">에 대 한 매개 변수 하나를 포함 하는 함수 `op` 및에 함수에 대 한 적절 한 인수를 보내면 `arg` 함수는에 적용 된 결과를 반환 합니다 `op` `arg` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-142">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="cc0de-143">다음 예제에서 함수 인수와 정수 인수는 모두 해당 이름을 사용 하 여 동일한 방식으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-143">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="cc0de-144">함수를 다른 함수에 인수로 보내는 기능은 맵 또는 필터 작업과 같은 함수형 프로그래밍 언어의 일반적인 추상화를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-144">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="cc0de-145">예를 들어, 맵 작업은 목록을 단계별로 실행 하는 함수에서 공유 하는 계산을 캡처하고 각 요소에 대 한 작업을 수행한 다음 결과 목록을 반환 하는 고차 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-145">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="cc0de-146">정수 목록의 각 요소를 증가 시키거나 각 요소를 제곱 하거나 문자열 목록의 각 요소를 대문자로 변경 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-146">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="cc0de-147">오류의 발생 가능성이 가장 많은 부분은 목록을 단계별로 안내 하 고 반환할 결과 목록을 작성 하는 재귀 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-147">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="cc0de-148">이 부분은 매핑 함수에서 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-148">That part is captured in the mapping function.</span></span> <span data-ttu-id="cc0de-149">특정 응용 프로그램에 대 한 모든 쓰기는 각 목록 요소에 개별적으로 적용 하는 함수입니다 (대/소문자를 추가, 제곱, 변경).</span><span class="sxs-lookup"><span data-stu-id="cc0de-149">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="cc0de-150">이 함수는 `squareIt` 이전 예제의로 전송 되는 것과 마찬가지로 매핑 함수에 인수로 전송 됩니다 `applyIt` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-150">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="cc0de-151">F #은 [목록](../language-reference/lists.md), [배열](../language-reference/arrays.md)및 [시퀀스](../language-reference/sequences.md)를 비롯 한 대부분의 컬렉션 형식에 대 한 맵 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-151">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="cc0de-152">다음 예에서는 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-152">The following examples use lists.</span></span> <span data-ttu-id="cc0de-153">구문은 `List.map <the function> <the list>`입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-153">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="cc0de-154">자세한 내용은 [목록](../language-reference/lists.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="cc0de-154">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="cc0de-155">함수 호출에서 값 반환</span><span class="sxs-lookup"><span data-stu-id="cc0de-155">Return the Value from a Function Call</span></span>

<span data-ttu-id="cc0de-156">마지막으로 함수에 언어의 첫 번째 클래스 상태가 있는 경우 정수 및 문자열과 같은 다른 형식을 반환 하는 것 처럼 함수 호출의 값으로이를 반환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-156">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="cc0de-157">다음 함수는 반환 정수를 호출 하 고 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-157">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="cc0de-158">다음 함수 호출은 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-158">The following function call returns a string.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="cc0de-159">인라인으로 선언 된 다음 함수 호출은 부울 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-159">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="cc0de-160">표시 되는 값은 `True` 입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-160">The value displayed is `True`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="cc0de-161">함수 호출의 값으로 함수를 반환 하는 기능은 고차 함수의 두 번째 특징입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-161">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="cc0de-162">다음 예제에서 `checkFor` 는 하나의 인수를 사용 하 `item` 고 새 함수를 해당 값으로 반환 하는 함수로 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-162">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="cc0de-163">반환 된 함수는 목록을 인수로 사용 하 `lst` 고에서을 검색 `item` `lst` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-163">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="cc0de-164">`item`이 있으면이 함수는를 반환 `true` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-164">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="cc0de-165">`item`가 없으면이 함수는를 반환 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-165">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="cc0de-166">이전 단원에서와 같이 다음 코드는 제공 된 목록 함수인 [list. exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists)를 사용 하 여 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-166">As in the previous section, the following code uses a provided list function, [List.exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists), to search the list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="cc0de-167">다음 코드에서는를 사용 하 여 `checkFor` 하나의 인수를 사용 하 고 목록에서 7을 검색 하는 새 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-167">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="cc0de-168">다음 예제에서는 F #의 함수에 대 한 첫 번째 클래스 상태를 사용 하 여 `compose` 두 함수 인수의 컴퍼지션을 반환 하는 함수를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-168">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> <span data-ttu-id="cc0de-169">더 짧은 버전의 경우 "커리 된 함수" 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc0de-169">For an even shorter version, see the following section, "Curried Functions."</span></span>

<span data-ttu-id="cc0de-170">다음 코드에서는 두 개의 함수를에 인수로 보내고 `compose` , 둘 다 동일한 형식의 단일 인수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-170">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="cc0de-171">반환 값은 두 함수 인수의 컴퍼지션 인 새 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-171">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> <span data-ttu-id="cc0de-172">F #에서는 `<<` 함수를 구성 하는와 라는 두 개의 연산자를 제공 `>>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-172">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="cc0de-173">예를 들어 `let squareAndDouble2 = doubleIt << squareIt` 는 `let squareAndDouble = compose doubleIt squareIt` 이전 예제에서와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-173">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="cc0de-174">함수 호출의 값으로 함수를 반환 하는 다음 예제에서는 간단한 추측 게임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-174">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="cc0de-175">게임을 만들려면 `makeGame` 다른 사람이 추측 하려는 값을 사용 하 여를 호출 `target` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-175">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="cc0de-176">함수의 반환 값은 `makeGame` 한 인수 (추측)를 사용 하 여 guess가 정확한 지 여부를 보고 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-176">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="cc0de-177">다음 코드는를 호출 `makeGame` 하 여 `7` 에 대 한 값을 보냅니다 `target` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-177">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="cc0de-178">식별자 `playGame` 가 반환 된 람다 식에 바인딩되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-178">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="cc0de-179">따라서 `playGame` 는 하나의 인수를에 대 한 값으로 사용 하는 함수입니다 `guess` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-179">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a><span data-ttu-id="cc0de-180">커리 함수</span><span class="sxs-lookup"><span data-stu-id="cc0de-180">Curried Functions</span></span>

<span data-ttu-id="cc0de-181">F # 함수 선언에서 암시적 *currying* 를 활용 하면 이전 섹션의 많은 예제를 더 간결 하 게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-181">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="cc0de-182">Currying는 둘 이상의 매개 변수를 포함 하는 함수를 일련의 포함 된 함수로 변환 하는 프로세스입니다. 각 함수에는 단일 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-182">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="cc0de-183">F #에서 두 개 이상의 매개 변수가 있는 함수는 기본적으로 커리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-183">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="cc0de-184">예를 들어 `compose` 이전 섹션에서는 다음의 간결한 스타일과 같이 세 개의 매개 변수를 사용 하 여 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-184">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="cc0de-185">그러나 결과는에 표시 된 것과 같이 한 매개 변수의 다른 함수를 반환 하는 하나의 매개 변수 함수를 반환 하는 하나의 매개 변수에 대 한 함수입니다 `compose4curried` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-185">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="cc0de-186">이 함수는 여러 가지 방법으로 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-186">You can access this function in several ways.</span></span> <span data-ttu-id="cc0de-187">다음의 각 예에서는를 반환 하 고 18을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-187">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="cc0de-188">`compose4`모든 예제에서을로 바꿀 수 있습니다 `compose4curried` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-188">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="cc0de-189">함수가 이전과 동일 하 게 작동 하는지 확인 하려면 원래 테스트 사례를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-189">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> <span data-ttu-id="cc0de-190">튜플에 매개 변수를 포함 하 여 currying를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-190">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="cc0de-191">자세한 내용은 [매개 변수 및 인수](../language-reference/parameters-and-arguments.md)에서 "매개 변수 패턴"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc0de-191">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="cc0de-192">다음 예제에서는 암시적 currying를 사용 하 여 더 짧은 버전의를 작성 `makeGame` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-192">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="cc0de-193">함수를 생성 하 고 반환 하는 방법에 대 한 세부 정보는 `makeGame` `game` 이 형식에서 더 명확 하지 않지만 원래 테스트 사례를 사용 하 여 결과가 동일한 지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-193">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="cc0de-194">Currying에 대 한 자세한 내용은 [함수](../language-reference/functions/index.md)에서 "인수 부분 적용"을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc0de-194">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>

## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="cc0de-195">식별자 및 함수 정의는 서로 바꿔 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-195">Identifier and Function Definition Are Interchangeable</span></span>

<span data-ttu-id="cc0de-196">`num`이전 예의 변수 이름은 정수 10으로 계산 되며, `num` 가 유효한 경우 10도 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-196">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="cc0de-197">함수 식별자와 해당 값의 경우에도 마찬가지입니다. 함수 이름을 사용할 수 있는 모든 위치에서는 바인딩되는 람다 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-197">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="cc0de-198">다음 예제에서는 `Boolean` 라는 함수를 정의한 `isNegative` 다음 함수 이름과 함수 정의를 서로 바꿔 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-198">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="cc0de-199">다음 세 가지 예제는 모두를 반환 하 고 표시 `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-199">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="cc0de-200">한 단계 더 수행 하려면에 대해 바인딩되는 값을 대체 합니다 `applyIt` `applyIt` .</span><span class="sxs-lookup"><span data-stu-id="cc0de-200">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="cc0de-201">함수는 F의 First 클래스 값입니다.\#</span><span class="sxs-lookup"><span data-stu-id="cc0de-201">Functions Are First-Class Values in F\#</span></span>

<span data-ttu-id="cc0de-202">이전 섹션의 예제에서는 f #의 함수가 F #의 첫 번째 클래스 값에 대 한 조건을 충족 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-202">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="cc0de-203">식별자를 함수 정의에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-203">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="cc0de-204">데이터 구조에 함수를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-204">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="cc0de-205">함수를 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-205">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="cc0de-206">함수를 함수 호출의 값으로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-206">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="cc0de-207">F #에 대 한 자세한 내용은 [f # 언어 참조](../language-reference/index.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cc0de-207">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="cc0de-208">예제</span><span class="sxs-lookup"><span data-stu-id="cc0de-208">Example</span></span>

### <a name="description"></a><span data-ttu-id="cc0de-209">Description</span><span class="sxs-lookup"><span data-stu-id="cc0de-209">Description</span></span>

<span data-ttu-id="cc0de-210">다음 코드는이 항목의 모든 예제를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc0de-210">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="cc0de-211">코드</span><span class="sxs-lookup"><span data-stu-id="cc0de-211">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a><span data-ttu-id="cc0de-212">참조</span><span class="sxs-lookup"><span data-stu-id="cc0de-212">See also</span></span>

- [<span data-ttu-id="cc0de-213">목록</span><span class="sxs-lookup"><span data-stu-id="cc0de-213">Lists</span></span>](../language-reference/lists.md)
- [<span data-ttu-id="cc0de-214">튜플</span><span class="sxs-lookup"><span data-stu-id="cc0de-214">Tuples</span></span>](../language-reference/tuples.md)
- [<span data-ttu-id="cc0de-215">함수</span><span class="sxs-lookup"><span data-stu-id="cc0de-215">Functions</span></span>](../language-reference/functions/index.md)
- [<span data-ttu-id="cc0de-216">`let` 바인딩하</span><span class="sxs-lookup"><span data-stu-id="cc0de-216">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)
- [<span data-ttu-id="cc0de-217">람다 식: `fun` 키워드</span><span class="sxs-lookup"><span data-stu-id="cc0de-217">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
