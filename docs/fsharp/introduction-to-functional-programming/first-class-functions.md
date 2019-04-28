---
title: 일급 함수
description: 첫 번째 클래스 함수 및의 함수형 프로그래밍에 대 한 중요 한 됩니다 하는 방법에 대해 알아봅니다 F#입니다.
ms.date: 10/29/2018
ms.openlocfilehash: 505ad686614b53d779cb617fc04ac74c2a88b31b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772764"
---
# <a name="first-class-functions"></a><span data-ttu-id="c051c-103">일급 함수</span><span class="sxs-lookup"><span data-stu-id="c051c-103">First-class functions</span></span>

<span data-ttu-id="c051c-104">함수형 프로그래밍 언어의 대표적인 특징은 함수 최상위 상태를 상승 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-104">A defining characteristic of functional programming languages is the elevation of functions to first-class status.</span></span> <span data-ttu-id="c051c-105">모든 다른 기본 제공 형식의 값을 사용 하 여 수행할를 비교할 수 있는 수준의 노력을 사용 하 여 이렇게 할 수는 함수를 사용 하 여 할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-105">You should be able to do with a function whatever you can do with values of the other built-in types, and be able to do so with a comparable degree of effort.</span></span>

<span data-ttu-id="c051c-106">일반적인 측정값 최고 수준의 상태는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-106">Typical measures of first-class status include the following:</span></span>

- <span data-ttu-id="c051c-107">식별자에 함수를 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-107">Can you bind functions to identifiers?</span></span> <span data-ttu-id="c051c-108">즉, 있습니다 수 이름을?</span><span class="sxs-lookup"><span data-stu-id="c051c-108">That is, can you give them names?</span></span>

- <span data-ttu-id="c051c-109">저장할 수 있습니다 하 데이터 구조체에는 함수 같은 목록의?</span><span class="sxs-lookup"><span data-stu-id="c051c-109">Can you store functions in data structures, such as in a list?</span></span>

- <span data-ttu-id="c051c-110">함수 호출에서 인수로 서 함수를 전달할 수 있습니다?</span><span class="sxs-lookup"><span data-stu-id="c051c-110">Can you pass a function as an argument in a function call?</span></span>

- <span data-ttu-id="c051c-111">함수 호출에서 함수를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-111">Can you return a function from a function call?</span></span>

<span data-ttu-id="c051c-112">마지막 두 측정값 정의 일명 *고차 operations* 또는 *고차 함수*합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-112">The last two measures define what are known as *higher-order operations* or *higher-order functions*.</span></span> <span data-ttu-id="c051c-113">고차 함수는 함수를 인수로 수락 하 고 함수 호출의 값으로 함수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-113">Higher-order functions accept functions as arguments and return functions as the value of function calls.</span></span> <span data-ttu-id="c051c-114">이러한 작업에는 매핑 함수 및 함수 조합으로 함수형 프로그래밍의 핵심적 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-114">These operations support such mainstays of functional programming as mapping functions and composition of functions.</span></span>

## <a name="give-the-value-a-name"></a><span data-ttu-id="c051c-115">값 이름을</span><span class="sxs-lookup"><span data-stu-id="c051c-115">Give the Value a Name</span></span>

<span data-ttu-id="c051c-116">함수는 첫 번째 클래스 값 이면 해야 이름을 할 것 처럼 정수, 문자열 및 다른 기본 제공 형식 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-116">If a function is a first-class value, you must be able to name it, just as you can name integers, strings, and other built-in types.</span></span> <span data-ttu-id="c051c-117">이 식별자 값에 바인딩 함수형 프로그래밍 문서에서 참조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-117">This is referred to in functional programming literature as binding an identifier to a value.</span></span> <span data-ttu-id="c051c-118">F#사용 하 여 [ `let` 바인딩을](../language-reference/functions/let-bindings.md) 이름 값에 바인딩할: `let <identifier> = <value>`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-118">F# uses [`let` bindings](../language-reference/functions/let-bindings.md) to bind names to values: `let <identifier> = <value>`.</span></span> <span data-ttu-id="c051c-119">다음 코드는 두 가지 예제를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-119">The following code shows two examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet20.fs)]

<span data-ttu-id="c051c-120">쉽게 함수를 이름을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-120">You can name a function just as easily.</span></span> <span data-ttu-id="c051c-121">다음 예제에서는 명명 된 함수를 정의 `squareIt` 식별자를 바인딩하여 `squareIt` 에 [람다 식](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span><span class="sxs-lookup"><span data-stu-id="c051c-121">The following example defines a function named `squareIt` by binding the identifier `squareIt` to the [lambda expression](../language-reference/functions/lambda-expressions-the-fun-keyword.md) `fun n -> n * n`.</span></span> <span data-ttu-id="c051c-122">함수 `squareIt` 하나의 매개 변수가 `n`, 해당 매개 변수의 사각형을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-122">Function `squareIt` has one parameter, `n`, and it returns the square of that parameter.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

<span data-ttu-id="c051c-123">F#다음 기능을 제공 더 간결한 구문을 입력으로 동일한 결과 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-123">F# provides the following more concise syntax to achieve the same result with less typing.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet22.fs)]

<span data-ttu-id="c051c-124">주로 나오는 예제에서는 첫 번째 스타일을 사용 하 여 `let <function-name> = <lambda-expression>`, 함수 선언 및 다른 유형의 값 선언 간의 유사성을 강조 하기.</span><span class="sxs-lookup"><span data-stu-id="c051c-124">The examples that follow mostly use the first style, `let <function-name> = <lambda-expression>`, to emphasize the similarities between the declaration of functions and the declaration of other types of values.</span></span> <span data-ttu-id="c051c-125">그러나 모든 명명 된 함수 간결한 구문을 사용 하 여 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-125">However, all the named functions can also be written with the concise syntax.</span></span> <span data-ttu-id="c051c-126">일부 예제에서는 두 가지 방식으로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-126">Some of the examples are written in both ways.</span></span>

## <a name="store-the-value-in-a-data-structure"></a><span data-ttu-id="c051c-127">데이터 구조에서 값을 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-127">Store the Value in a Data Structure</span></span>

<span data-ttu-id="c051c-128">데이터 구조에는 첫 번째 클래스 값을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-128">A first-class value can be stored in a data structure.</span></span> <span data-ttu-id="c051c-129">다음 코드는 튜플 목록에 값을 저장 하는 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-129">The following code shows examples that store values in lists and in tuples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet23.fs)]

<span data-ttu-id="c051c-130">튜플에 저장 된 함수 이름을 않습니다 함수로 계산 실제로 있는지를 확인 하려면 다음 예제에서는 합니다 `fst` 하 고 `snd` 튜플 로부터 첫 번째 및 두 번째 요소를 추출 하는 연산자 `funAndArgTuple`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-130">To verify that a function name stored in a tuple does in fact evaluate to a function, the following example uses the `fst` and `snd` operators to extract the first and second elements from tuple `funAndArgTuple`.</span></span> <span data-ttu-id="c051c-131">튜플의 첫 번째 요소는 `squareIt` 이 고 두 번째 요소는 `num`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-131">The first element in the tuple is `squareIt` and the second element is `num`.</span></span> <span data-ttu-id="c051c-132">식별자 `num` 정수로 10에 대 한 유효한 인수 앞의 예제에서 바인딩되는 `squareIt` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-132">Identifier `num` is bound in a previous example to integer 10, a valid argument for the `squareIt` function.</span></span> <span data-ttu-id="c051c-133">두 번째 식 튜플의 두 번째 요소 튜플의 첫 번째 요소에 적용: `squareIt num`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-133">The second expression applies the first element in the tuple to the second element in the tuple: `squareIt num`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet24.fs)]

<span data-ttu-id="c051c-134">마찬가지로, 식별자로 `num` 정수 10 수 식별자 수 있으므로 서로 교대로 사용 `squareIt` 람다 식 및 `fun n -> n * n`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-134">Similarly, just as identifier `num` and integer 10 can be used interchangeably, so can identifier `squareIt` and lambda expression `fun n -> n * n`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet25.fs)]

## <a name="pass-the-value-as-an-argument"></a><span data-ttu-id="c051c-135">값을 인수로 전달</span><span class="sxs-lookup"><span data-stu-id="c051c-135">Pass the Value as an Argument</span></span>

<span data-ttu-id="c051c-136">값에 최상위 상태 언어의 경우 함수에 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-136">If a value has first-class status in a language, you can pass it as an argument to a function.</span></span> <span data-ttu-id="c051c-137">예를 들어, 정수 및 문자열 인수로 전달에 공통적으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-137">For example, it is common to pass integers and strings as arguments.</span></span> <span data-ttu-id="c051c-138">다음 코드에서는 정수 및 문자열에 인수로 전달 된 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-138">The following code shows integers and strings passed as arguments in F#.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet26.fs)]

<span data-ttu-id="c051c-139">함수는 최상위 상태에 있는 경우에 동일한 방식으로 인수로 전달할 수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-139">If functions have first-class status, you must be able to pass them as arguments in the same way.</span></span> <span data-ttu-id="c051c-140">고차 함수의 첫 번째 특징에 유의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-140">Remember that this is the first characteristic of higher-order functions.</span></span>

<span data-ttu-id="c051c-141">다음 예제에서는 작동 `applyIt` 두 개의 매개 변수가 `op` 고 `arg`입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-141">In the following example, function `applyIt` has two parameters, `op` and `arg`.</span></span> <span data-ttu-id="c051c-142">에 대 한 하나의 매개 변수가 있는 함수에 전송 하는 경우 `op` 및 함수에 대 한 적절 한 인수로 `arg`, 함수를 적용 한 결과 반환 합니다. `op` 하려면 `arg`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-142">If you send in a function that has one parameter for `op` and an appropriate argument for the function to `arg`, the function returns the result of applying `op` to `arg`.</span></span> <span data-ttu-id="c051c-143">다음 예제에서는 정수 인수 및 함수 인수는 동일한 방법으로 전송 됩니다 해당 이름을 사용 하 여.</span><span class="sxs-lookup"><span data-stu-id="c051c-143">In the following example, both the function argument and the integer argument are sent in the same way, by using their names.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet27.fs)]

<span data-ttu-id="c051c-144">다른 함수에 인수로 맵 또는 필터 작업 같은 함수형 프로그래밍 언어에서 일반적인 추상화의 기반이 되는 함수를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-144">The ability to send a function as an argument to another function underlies common abstractions in functional programming languages, such as map or filter operations.</span></span> <span data-ttu-id="c051c-145">예를 들어 맵 작업에는 목록을 단계별로 각 요소에 작업을 수행 하 고 다음 결과의 목록을 반환 하는 함수에서 공유 하는 계산을 캡처하는 고차 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-145">A map operation, for example, is a higher-order function that captures the computation shared by functions that step through a list, do something to each element, and then return a list of the results.</span></span> <span data-ttu-id="c051c-146">정수 목록의 각 요소를 증가 시킬 각 요소인 정사각형 또는 문자열 목록의 각 요소를 대문자로 변경 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-146">You might want to increment each element in a list of integers, or to square each element, or to change each element in a list of strings to uppercase.</span></span> <span data-ttu-id="c051c-147">계산의 오류가 발생 하기 쉬운 부분 재귀 프로세스 목록을 통해 해당 단계 이며 반환할 결과의 목록을 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-147">The error-prone part of the computation is the recursive process that steps through the list and builds a list of the results to return.</span></span> <span data-ttu-id="c051c-148">일부는 매핑 함수에 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-148">That part is captured in the mapping function.</span></span> <span data-ttu-id="c051c-149">특정 응용 프로그램 작성 해야 모든는 개별적으로 목록의 각 요소에 적용 하려는 하는 함수 (추가, 제곱 대/소문자 바꾸기).</span><span class="sxs-lookup"><span data-stu-id="c051c-149">All you have to write for a particular application is the function that you want to apply to each list element individually (adding, squaring, changing case).</span></span> <span data-ttu-id="c051c-150">함수를 보내 인수로 하도록 매핑 함수 처럼 `squareIt` 보낼 `applyIt` 이전 예제에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-150">That function is sent as an argument to the mapping function, just as `squareIt` is sent to `applyIt` in the previous example.</span></span>

<span data-ttu-id="c051c-151">F#같은 대부분의 컬렉션 형식에 대 한 지도 메서드를 제공 [나열](../language-reference/lists.md)를 [배열을](../language-reference/arrays.md), 및 [시퀀스](../language-reference/sequences.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-151">F# provides map methods for most collection types, including [lists](../language-reference/lists.md), [arrays](../language-reference/arrays.md), and [sequences](../language-reference/sequences.md).</span></span> <span data-ttu-id="c051c-152">다음 예제에서는 목록을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-152">The following examples use lists.</span></span> <span data-ttu-id="c051c-153">구문은 `List.map <the function> <the list>`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-153">The syntax is `List.map <the function> <the list>`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet28.fs)]

<span data-ttu-id="c051c-154">자세한 내용은 [나열](../language-reference/lists.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-154">For more information, see [Lists](../language-reference/lists.md).</span></span>

## <a name="return-the-value-from-a-function-call"></a><span data-ttu-id="c051c-155">함수 호출에서 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-155">Return the Value from a Function Call</span></span>

<span data-ttu-id="c051c-156">마지막으로, 함수 언어에서 최고 수준의 상태 있으면 해야 함수 호출의 값으로 반환할 수 정수 및 문자열과 같은 다른 형식의 경우 반환 되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-156">Finally, if a function has first-class status in a language, you must be able to return it as the value of a function call, just as you return other types, such as integers and strings.</span></span>

<span data-ttu-id="c051c-157">다음 함수 호출은 정수를 반환 하 고 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-157">The following function calls return integers and display them.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet29.fs)]

<span data-ttu-id="c051c-158">다음 함수 호출은 문자열을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-158">The following function call returns a string.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet30.fs)]

<span data-ttu-id="c051c-159">부울 값을 반환 하는 다음 함수 호출을 인라인을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-159">The following function call, declared inline, returns a Boolean value.</span></span> <span data-ttu-id="c051c-160">표시 되는 값은 `True`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-160">The value displayed is `True`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet31.fs)]

<span data-ttu-id="c051c-161">함수 호출의 값으로 함수를 반환 하는 기능은 고차 함수의 두 번째 특징입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-161">The ability to return a function as the value of a function call is the second characteristic of higher-order functions.</span></span> <span data-ttu-id="c051c-162">다음 예에서 `checkFor` 인수 하나를 사용 하는 함수 정의 됩니다. `item`, 해당 값으로 새 함수를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-162">In the following example, `checkFor` is defined to be a function that takes one argument, `item`, and returns a new function as its value.</span></span> <span data-ttu-id="c051c-163">반환 된 함수는 목록을 인수로 `lst`, 검색 `item` 에서 `lst`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-163">The returned function takes a list as its argument, `lst`, and searches for `item` in `lst`.</span></span> <span data-ttu-id="c051c-164">하는 경우 `item` 가 있으면 반환 `true`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-164">If `item` is present, the function returns `true`.</span></span> <span data-ttu-id="c051c-165">하는 경우 `item` 가 없으면 반환 `false`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-165">If `item` is not present, the function returns `false`.</span></span> <span data-ttu-id="c051c-166">이전 섹션에서와 같이 다음 코드에서는 제공 된 목록 함수 [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8)를 목록을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-166">As in the previous section, the following code uses a provided list function, [List.exists](https://msdn.microsoft.com/library/15a3ebd5-98f0-44c0-8220-7dedec3e68a8), to search the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="c051c-167">다음 코드에서는 `checkFor` 목록에서 하나의 인수, 목록 및 7에 대 한 검색을 사용 하는 새 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-167">The following code uses `checkFor` to create a new function that takes one argument, a list, and searches for 7 in the list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet33.fs)]

<span data-ttu-id="c051c-168">다음 예제에서는 최상위 상태에서 함수의 F# 함수를 선언 하 `compose`, 컴퍼지션 두 함수 인수를 반환 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-168">The following example uses the first-class status of functions in F# to declare a function, `compose`, that returns a composition of two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet34.fs)]

> [!NOTE]
> <span data-ttu-id="c051c-169">더 짧게 버전인 다음 섹션인 "Curried 함수입니다."을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c051c-169">For an even shorter version, see the following section, "Curried Functions."</span></span>

<span data-ttu-id="c051c-170">다음 코드는 두 함수에 대 한 인수로 보냅니다 `compose`모두 동일한 형식의 단일 인수를 사용 하는 중입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-170">The following code sends two functions as arguments to `compose`, both of which take a single argument of the same type.</span></span> <span data-ttu-id="c051c-171">반환 값은 두 개의 함수 인수의 혼합 된 새 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-171">The return value is a new function that is a composition of the two function arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet35.fs)]

> [!NOTE]
> <span data-ttu-id="c051c-172">F#두 연산자를 제공 `<<` 및 `>>`를 구성 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-172">F# provides two operators, `<<` and `>>`, that compose functions.</span></span> <span data-ttu-id="c051c-173">예를 들어 `let squareAndDouble2 = doubleIt << squareIt` 같습니다 `let squareAndDouble = compose doubleIt squareIt` 이전 예제에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-173">For example, `let squareAndDouble2 = doubleIt << squareIt` is equivalent to `let squareAndDouble = compose doubleIt squareIt` in the previous example.</span></span>

<span data-ttu-id="c051c-174">함수 호출의 값으로 함수를 반환 하는 다음 예제에서는 간단한 맞추기 게임을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-174">The following example of returning a function as the value of a function call creates a simple guessing game.</span></span> <span data-ttu-id="c051c-175">게임을 만들려면 호출 `makeGame` 값을 사용 하 여 다른 사람이 추측 하기 원하는 전송에 대 한 `target`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-175">To create a game, call `makeGame` with the value that you want someone to guess sent in for `target`.</span></span> <span data-ttu-id="c051c-176">함수에서 반환 값 `makeGame` 는 하나의 인수 (추측) 및 추측이 올바른지 여부를 보고 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-176">The return value from function `makeGame` is a function that takes one argument (the guess) and reports whether the guess is correct.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet36.fs)]

<span data-ttu-id="c051c-177">다음 코드 호출 `makeGame`에 값을 전송 `7` 에 대 한 `target`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-177">The following code calls `makeGame`, sending the value `7` for `target`.</span></span> <span data-ttu-id="c051c-178">식별자 `playGame` 반환 된 람다 식에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-178">Identifier `playGame` is bound to the returned lambda expression.</span></span> <span data-ttu-id="c051c-179">따라서 `playGame` 에 대 한 값을 하나의 인수로 사용 하는 함수는 `guess`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-179">Therefore, `playGame` is a function that takes as its one argument a value for `guess`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet37.fs)]

## <a name="curried-functions"></a><span data-ttu-id="c051c-180">커리 된 함수</span><span class="sxs-lookup"><span data-stu-id="c051c-180">Curried Functions</span></span>

<span data-ttu-id="c051c-181">암시적의 활용 하 여 더 간결 하 게 작성할 수 다양 한 이전 섹션에서 예제 *커리* 에서 F# 함수 선언이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-181">Many of the examples in the previous section can be written more concisely by taking advantage of the implicit *currying* in F# function declarations.</span></span> <span data-ttu-id="c051c-182">(Currying) 각각에 단일 매개 변수가 포함 된 함수의 계열로 둘 이상의 매개 변수가 있는 함수를 변환 하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-182">Currying is a process that transforms a function that has more than one parameter into a series of embedded functions, each of which has a single parameter.</span></span> <span data-ttu-id="c051c-183">F#를 둘 이상의 매개 변수가 있는 함수는 본질적으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-183">In F#, functions that have more than one parameter are inherently curried.</span></span> <span data-ttu-id="c051c-184">예를 들어 `compose` 이전 섹션에서 작성할 수 있습니다 다음 간결한 스타일에서 세 개의 매개 변수를 사용 하 여 표시 된 것과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-184">For example, `compose` from the previous section can be written as shown in the following concise style, with three parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet38.fs)]

<span data-ttu-id="c051c-185">그러나 결과 함수에 표시 된 대로 다른 함수의 매개 변수 하나를 반환 하는 하나의 매개 변수는 함수를 반환 하는 하나의 매개 변수의 `compose4curried`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-185">However, the result is a function of one parameter that returns a function of one parameter that in turn returns another function of one parameter, as shown in `compose4curried`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet39.fs)]

<span data-ttu-id="c051c-186">여러 가지 방법으로이 함수에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-186">You can access this function in several ways.</span></span> <span data-ttu-id="c051c-187">다음 예에서는 각각 반환 하 고 18를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-187">Each of the following examples returns and displays 18.</span></span> <span data-ttu-id="c051c-188">바꿀 수 있습니다 `compose4` 사용 하 여 `compose4curried` 의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-188">You can replace `compose4` with `compose4curried` in any of the examples.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet40.fs)]

<span data-ttu-id="c051c-189">이전과 여전히 작동 하는지 확인 하려면 원래 테스트 사례를 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-189">To verify that the function still works as it did before, try the original test cases again.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet41.fs)]

> [!NOTE]
> <span data-ttu-id="c051c-190">튜플에 매개 변수를 포함 하 여 (currying)을 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-190">You can restrict currying by enclosing parameters in tuples.</span></span> <span data-ttu-id="c051c-191">자세한 내용은 "매개 변수 패턴"를 참조 하세요 [매개 변수 및 인수](../language-reference/parameters-and-arguments.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-191">For more information, see "Parameter Patterns" in [Parameters and Arguments](../language-reference/parameters-and-arguments.md).</span></span>

<span data-ttu-id="c051c-192">다음 예제에서는 암시적 (currying)의 짧은 버전 쓸 `makeGame`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-192">The following example uses implicit currying to write a shorter version of `makeGame`.</span></span> <span data-ttu-id="c051c-193">하는 방법의 세부 정보 `makeGame` 생성 및 반환 된 `game` 함수는이 형식으로 명시적 덜 있지만 결과 동일 원래 테스트 사례를 사용 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-193">The details of how `makeGame` constructs and returns the `game` function are less explicit in this format, but you can verify by using the original test cases that the result is the same.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet42.fs)]

<span data-ttu-id="c051c-194">(Currying) 하는 방법에 대 한 자세한 내용은 "응용 프로그램의 인수 부분"를 참조 하세요 [함수](../language-reference/functions/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-194">For more information about currying, see "Partial Application of Arguments" in [Functions](../language-reference/functions/index.md).</span></span>

## <a name="identifier-and-function-definition-are-interchangeable"></a><span data-ttu-id="c051c-195">식별자 및 함수는 서로 바꿔 사용할 수</span><span class="sxs-lookup"><span data-stu-id="c051c-195">Identifier and Function Definition Are Interchangeable</span></span>

<span data-ttu-id="c051c-196">변수 이름 `num` 이전 예제에서는 정수, 10으로 계산 되 고 것은 놀라운 된 `num` 은 유효한 10도 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-196">The variable name `num` in the previous examples evaluates to the integer 10, and it is no surprise that where `num` is valid, 10 is also valid.</span></span> <span data-ttu-id="c051c-197">함수 식별자 및 해당 값의 마찬가지입니다: 함수 이름을 사용할 수 있습니다 원격가 바인딩되는 람다 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-197">The same is true of function identifiers and their values: anywhere the name of the function can be used, the lambda expression to which it is bound can be used.</span></span>

<span data-ttu-id="c051c-198">다음 예제에서는 정의 `Boolean` 함수 호출 `isNegative`, 다음 함수의 이름과 함수 정의 같은 의미로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-198">The following example defines a `Boolean` function called `isNegative`, and then uses the name of the function and the definition of the function interchangeably.</span></span> <span data-ttu-id="c051c-199">다음 세 가지 예제 모두 반환 하 여 표시 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-199">The next three examples all return and display `False`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet43.fs)]

<span data-ttu-id="c051c-200">한 단계 추가, 값을 대체 하는 `applyIt` 에 대 한에 바인딩되어 `applyIt`합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-200">To take it one step further, substitute the value that `applyIt` is bound to for `applyIt`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet44.fs)]

## <a name="functions-are-first-class-values-in-f"></a><span data-ttu-id="c051c-201">함수는 f #의 첫 번째 클래스 값\#</span><span class="sxs-lookup"><span data-stu-id="c051c-201">Functions Are First-Class Values in F\#</span></span>

<span data-ttu-id="c051c-202">이전 섹션의 예제에서 함수를 보여 줍니다. F# 에서 첫 번째 클래스 값에 대 한 조건을 충족 F#:</span><span class="sxs-lookup"><span data-stu-id="c051c-202">The examples in the previous sections demonstrate that functions in F# satisfy the criteria for being first-class values in F#:</span></span>

- <span data-ttu-id="c051c-203">함수 정의에 식별자를 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-203">You can bind an identifier to a function definition.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet21.fs)]

- <span data-ttu-id="c051c-204">데이터 구조에 함수를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-204">You can store a function in a data structure.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet45.fs)]

- <span data-ttu-id="c051c-205">함수를 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-205">You can pass a function as an argument.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet46.fs)]

- <span data-ttu-id="c051c-206">함수 호출의 값으로 함수를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-206">You can return a function as the value of a function call.</span></span>
[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet32.fs)]

<span data-ttu-id="c051c-207">에 대 한 자세한 내용은 F#를 참조 합니다 [ F# 언어 참조](../language-reference/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-207">For more information about F#, see the [F# Language Reference](../language-reference/index.md).</span></span>

## <a name="example"></a><span data-ttu-id="c051c-208">예제</span><span class="sxs-lookup"><span data-stu-id="c051c-208">Example</span></span>

### <a name="description"></a><span data-ttu-id="c051c-209">설명</span><span class="sxs-lookup"><span data-stu-id="c051c-209">Description</span></span>

<span data-ttu-id="c051c-210">다음 코드는이 항목의 모든 예제를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c051c-210">The following code contains all the examples in this topic.</span></span>

### <a name="code"></a><span data-ttu-id="c051c-211">코드</span><span class="sxs-lookup"><span data-stu-id="c051c-211">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/contour/snippet47.fs)]

## <a name="see-also"></a><span data-ttu-id="c051c-212">참고자료</span><span class="sxs-lookup"><span data-stu-id="c051c-212">See also</span></span>

- [<span data-ttu-id="c051c-213">목록</span><span class="sxs-lookup"><span data-stu-id="c051c-213">Lists</span></span>](../language-reference/lists.md)
- [<span data-ttu-id="c051c-214">튜플</span><span class="sxs-lookup"><span data-stu-id="c051c-214">Tuples</span></span>](../language-reference/tuples.md)
- [<span data-ttu-id="c051c-215">함수</span><span class="sxs-lookup"><span data-stu-id="c051c-215">Functions</span></span>](../language-reference/functions/index.md)
- [<span data-ttu-id="c051c-216">`let` Bindings</span><span class="sxs-lookup"><span data-stu-id="c051c-216">`let` Bindings</span></span>](../language-reference/functions/let-bindings.md)
- [<span data-ttu-id="c051c-217">람다 식: `fun` 키워드</span><span class="sxs-lookup"><span data-stu-id="c051c-217">Lambda Expressions: The `fun` Keyword</span></span>](../language-reference/functions/lambda-expressions-the-fun-keyword.md)
