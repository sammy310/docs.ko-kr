---
title: 목록
description: '동일한 형식의 변경 되지 않은 순서가 지정 된 일련의 요소에 대 한 F # 목록에 대해 알아봅니다.'
ms.date: 08/13/2020
ms.openlocfilehash: 16d7195039d25cf63630f5cc3be6563b1bf45c44
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88559169"
---
# <a name="lists"></a><span data-ttu-id="cbbcb-103">목록</span><span class="sxs-lookup"><span data-stu-id="cbbcb-103">Lists</span></span>

<span data-ttu-id="cbbcb-104">F#의 목록은 순서가 지정되고 변경할 수 없는 일련의 동일 형식 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-104">A list in F# is an ordered, immutable series of elements of the same type.</span></span> <span data-ttu-id="cbbcb-105">목록에 대 한 기본 작업을 수행 하려면 [목록 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)의 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-105">To perform basic operations on lists, use the functions in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="creating-and-initializing-lists"></a><span data-ttu-id="cbbcb-106">목록 만들기 및 초기화</span><span class="sxs-lookup"><span data-stu-id="cbbcb-106">Creating and Initializing Lists</span></span>

<span data-ttu-id="cbbcb-107">아래 코드 줄에 나와 있는 것처럼 세미콜론으로 구분되고 대괄호로 묶인 요소를 명시적으로 목록 처리하여 목록을 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-107">You can define a list by explicitly listing out the elements, separated by semicolons and enclosed in square brackets, as shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1301.fs)]

<span data-ttu-id="cbbcb-108">요소 간에 줄 바꿈을 삽입하고 필요에 따라 세미콜론을 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-108">You can also put line breaks between elements, in which case the semicolons are optional.</span></span> <span data-ttu-id="cbbcb-109">요소 초기화 식이 더 길거나 각 요소에 대해 주석을 추가하려는 경우에는 이 두 번째 구문을 사용하면 코드를 더 쉽게 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-109">The latter syntax can result in more readable code when the element initialization expressions are longer, or when you want to include a comment for each element.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13011.fs)]

<span data-ttu-id="cbbcb-110">일반적으로 모든 목록 요소는 같은 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-110">Normally, all list elements must be the same type.</span></span> <span data-ttu-id="cbbcb-111">단, 요소가 기본 형식으로 지정된 목록에는 파생 형식 요소를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-111">An exception is that a list in which the elements are specified to be a base type can have elements that are derived types.</span></span> <span data-ttu-id="cbbcb-112">그러므로 `Button` 및 `CheckBox`가 모두 `Control`에서 파생되는 아래 코드는 정상적으로 사용 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-112">Thus the following is acceptable, because both `Button` and `CheckBox` derive from `Control`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13012.fs)]

<span data-ttu-id="cbbcb-113">아래 코드에 나와 있는 것처럼 범위 연산자(`..`)로 구분된 정수로 표시되는 범위를 사용하여 목록 요소를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-113">You can also define list elements by using a range indicated by integers separated by the range operator (`..`), as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1302.fs)]

<span data-ttu-id="cbbcb-114">빈 목록은 안에 아무 내용이 없는 대괄호 쌍으로 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-114">An empty list is specified by a pair of square brackets with nothing in between them.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1304.fs)]

<span data-ttu-id="cbbcb-115">시퀀스 식을 사용하여 목록을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-115">You can also use a sequence expression to create a list.</span></span> <span data-ttu-id="cbbcb-116">자세한 내용은 [시퀀스 식](sequences.md#sequence-expressions) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-116">See [Sequence Expressions](sequences.md#sequence-expressions) for more information.</span></span> <span data-ttu-id="cbbcb-117">예를 들어 다음 코드는 정수 1~10의 제곱 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-117">For example, the following code creates a list of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1303.fs)]

## <a name="operators-for-working-with-lists"></a><span data-ttu-id="cbbcb-118">목록 사용을 위한 연산자</span><span class="sxs-lookup"><span data-stu-id="cbbcb-118">Operators for Working with Lists</span></span>

<span data-ttu-id="cbbcb-119">`::`(cons) 연산자를 사용하여 목록에 요소를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-119">You can attach elements to a list by using the `::` (cons) operator.</span></span> <span data-ttu-id="cbbcb-120">`list1`이 `[2; 3; 4]`이면 다음 코드는 `list2`를 `[100; 2; 3; 4]`로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-120">If `list1` is `[2; 3; 4]`, the following code creates `list2` as `[100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1305.fs)]

<span data-ttu-id="cbbcb-121">다음 코드와 같이 `@` 연산자를 사용하여 호환 형식을 포함하는 목록을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-121">You can concatenate lists that have compatible types by using the `@` operator, as in the following code.</span></span> <span data-ttu-id="cbbcb-122">`list1`이 `[2; 3; 4]`이고 `list2`가 `[100; 2; 3; 4]`이면 다음 코드는 `list3`을 `[2; 3; 4; 100; 2; 3; 4]`로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-122">If `list1` is `[2; 3; 4]` and `list2` is `[100; 2; 3; 4]`, this code creates `list3` as `[2; 3; 4; 100; 2; 3; 4]`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1306.fs)]

<span data-ttu-id="cbbcb-123">목록에서 작업을 수행 하는 함수는 [목록 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-123">Functions for performing operations on lists are available in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

<span data-ttu-id="cbbcb-124">F#의 목록은 변경이 불가능하므로 수정 작업을 수행하면 기존 목록이 수정되는 대신 새 목록이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-124">Because lists in F# are immutable, any modifying operations generate new lists instead of modifying existing lists.</span></span>

<span data-ttu-id="cbbcb-125">F #의 목록은 단일 연결 된 목록으로 구현 됩니다. 즉, 목록의 헤드에만 액세스 하는 작업은 O (1)이 고 요소 액세스는 O (*n*)입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-125">Lists in F# are implemented as singly linked lists, which means that operations that access only the head of the list are O(1), and element access is O(*n*).</span></span>

## <a name="properties"></a><span data-ttu-id="cbbcb-126">속성</span><span class="sxs-lookup"><span data-stu-id="cbbcb-126">Properties</span></span>

<span data-ttu-id="cbbcb-127">목록 형식이 지원하는 속성은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-127">The list type supports the following properties:</span></span>

|<span data-ttu-id="cbbcb-128">속성</span><span class="sxs-lookup"><span data-stu-id="cbbcb-128">Property</span></span>|<span data-ttu-id="cbbcb-129">Type</span><span class="sxs-lookup"><span data-stu-id="cbbcb-129">Type</span></span>|<span data-ttu-id="cbbcb-130">Description</span><span class="sxs-lookup"><span data-stu-id="cbbcb-130">Description</span></span>|
|--------|----|-----------|
|[<span data-ttu-id="cbbcb-131">사장</span><span class="sxs-lookup"><span data-stu-id="cbbcb-131">Head</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head)|`'T`|<span data-ttu-id="cbbcb-132">첫 번째 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-132">The first element.</span></span>|
|[<span data-ttu-id="cbbcb-133">비어 있음</span><span class="sxs-lookup"><span data-stu-id="cbbcb-133">Empty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Empty)|`'T list`|<span data-ttu-id="cbbcb-134">해당 형식의 빈 목록을 반환하는 정적 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-134">A static property that returns an empty list of the appropriate type.</span></span>|
|[<span data-ttu-id="cbbcb-135">IsEmpty</span><span class="sxs-lookup"><span data-stu-id="cbbcb-135">IsEmpty</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#IsEmpty)|`bool`|<span data-ttu-id="cbbcb-136">목록에 요소가 없으면 `true`입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-136">`true` if the list has no elements.</span></span>|
|[<span data-ttu-id="cbbcb-137">항목</span><span class="sxs-lookup"><span data-stu-id="cbbcb-137">Item</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Item)|`'T`|<span data-ttu-id="cbbcb-138">지정한 인덱스에 있는 요소로서 0부터 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-138">The element at the specified index (zero-based).</span></span>|
|[<span data-ttu-id="cbbcb-139">길이</span><span class="sxs-lookup"><span data-stu-id="cbbcb-139">Length</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Length)|`int`|<span data-ttu-id="cbbcb-140">요소의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-140">The number of elements.</span></span>|
|[<span data-ttu-id="cbbcb-141">Tail</span><span class="sxs-lookup"><span data-stu-id="cbbcb-141">Tail</span></span>](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail)|`'T list`|<span data-ttu-id="cbbcb-142">첫 번째 요소가 없는 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-142">The list without the first element.</span></span>|

<span data-ttu-id="cbbcb-143">이러한 속성을 사용하는 몇 가지 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-143">Following are some examples of using these properties.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1307.fs)]

## <a name="using-lists"></a><span data-ttu-id="cbbcb-144">목록 사용</span><span class="sxs-lookup"><span data-stu-id="cbbcb-144">Using Lists</span></span>

<span data-ttu-id="cbbcb-145">목록을 사용하여 프로그래밍할 때는 적은 양의 코드만으로도 복잡한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-145">Programming with lists enables you to perform complex operations with a small amount of code.</span></span> <span data-ttu-id="cbbcb-146">이 섹션에서는 기능적인 프로그래밍에 중요한 일반적인 목록 관련 작업에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-146">This section describes common operations on lists that are important to functional programming.</span></span>

### <a name="recursion-with-lists"></a><span data-ttu-id="cbbcb-147">목록을 사용한 재귀</span><span class="sxs-lookup"><span data-stu-id="cbbcb-147">Recursion with Lists</span></span>

<span data-ttu-id="cbbcb-148">목록을 고유한 방식으로 재귀 프로그래밍 기술에 맞게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-148">Lists are uniquely suited to recursive programming techniques.</span></span> <span data-ttu-id="cbbcb-149">목록의 모든 요소에 대해 수행해야 하는 작업을 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-149">Consider an operation that must be performed on every element of a list.</span></span> <span data-ttu-id="cbbcb-150">목록 헤드에 대해 작업을 수행한 다음 목록 꼬리(첫 번째 요소를 제외한 원래 목록으로 구성되는 더 작은 목록)를 다음 재귀 수준으로 다시 전달하는 재귀적인 방식으로 이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-150">You can do this recursively by operating on the head of the list and then passing the tail of the list, which is a smaller list that consists of the original list without the first element, back again to the next level of recursion.</span></span>

<span data-ttu-id="cbbcb-151">이러한 재귀 함수를 작성하려면 패턴 일치에서 cons 연산자(`::`)를 사용합니다. 그러면 목록 헤드를 꼬리에서 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-151">To write such a recursive function, you use the cons operator (`::`) in pattern matching, which enables you to separate the head of a list from the tail.</span></span>

<span data-ttu-id="cbbcb-152">다음 코드 예제에서는 패턴 일치를 사용하여 목록에 대해 작업을 수행하는 재귀 함수를 구현하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-152">The following code example shows how to use pattern matching to implement a recursive function that performs operations on a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13071.fs)]

<span data-ttu-id="cbbcb-153">위의 코드는 작은 목록에서는 효율적으로 작동하지만 큰 목록에서는 스택이 오버플로될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-153">The previous code works well for small lists, but for larger lists, it could overflow the stack.</span></span> <span data-ttu-id="cbbcb-154">위의 코드보다 개선된 다음 코드에서는 재귀 함수 사용을 위한 표준 기술인 누적기 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-154">The following code improves on this code by using an accumulator argument, a standard technique for working with recursive functions.</span></span> <span data-ttu-id="cbbcb-155">누적기 인수를 사용하면 함수 꼬리가 재귀적으로 적용되므로 스택 공간이 절약됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-155">The use of the accumulator argument makes the function tail recursive, which saves stack space.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet13072.fs)]

<span data-ttu-id="cbbcb-156">`RemoveAllMultiples` 함수는 목록 두 개를 사용하는 재귀 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-156">The function `RemoveAllMultiples` is a recursive function that takes two lists.</span></span> <span data-ttu-id="cbbcb-157">첫 번째 목록은 배수를 제거할 숫자를 포함하며 두 번째 목록은 숫자를 제거할 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-157">The first list contains the numbers whose multiples will be removed, and the second list is the list from which to remove the numbers.</span></span> <span data-ttu-id="cbbcb-158">다음 예의 코드에서는 이 재귀 함수를 사용하여 목록에서 소수가 아닌 숫자를 모두 삭제해 소수만 포함된 목록을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-158">The code in the following example uses this recursive function to eliminate all the non-prime numbers from a list, leaving a list of prime numbers as the result.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1308.fs)]

<span data-ttu-id="cbbcb-159">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-159">The output is as follows:</span></span>

```console
Primes Up To 100:
[2; 3; 5; 7; 11; 13; 17; 19; 23; 29; 31; 37; 41; 43; 47; 53; 59; 61; 67; 71; 73; 79; 83; 89; 97]
```

## <a name="module-functions"></a><span data-ttu-id="cbbcb-160">모듈 함수</span><span class="sxs-lookup"><span data-stu-id="cbbcb-160">Module Functions</span></span>

<span data-ttu-id="cbbcb-161">[목록 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) 은 목록의 요소에 액세스 하는 함수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-161">The [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html) provides functions that access the elements of a list.</span></span> <span data-ttu-id="cbbcb-162">가장 빠르고 쉽게 액세스할 수 있는 요소는 헤드 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-162">The head element is the fastest and easiest to access.</span></span> <span data-ttu-id="cbbcb-163">속성 [head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) 또는 모듈 함수 [List. head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-163">Use the property [Head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Head) or the module function [List.head](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#head).</span></span> <span data-ttu-id="cbbcb-164">[Tail 속성 또는](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) [list. tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) 함수를 사용 하 여 목록의 꼬리 부분에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-164">You can access the tail of a list by using the [Tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-list-1.html#Tail) property or the [List.tail](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tail) function.</span></span> <span data-ttu-id="cbbcb-165">인덱스를 기준으로 요소를 찾으려면 [List. n a n](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-165">To find an element by index, use the [List.nth](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#nth) function.</span></span> <span data-ttu-id="cbbcb-166">`List.nth`는 목록을 트래버스하므로</span><span class="sxs-lookup"><span data-stu-id="cbbcb-166">`List.nth` traverses the list.</span></span> <span data-ttu-id="cbbcb-167">따라서 O (*n*)입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-167">Therefore, it is O(*n*).</span></span> <span data-ttu-id="cbbcb-168">코드에서 `List.nth`를 자주 사용하는 경우 목록 대신 배열을 사용해볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-168">If your code uses `List.nth` frequently, you might want to consider using an array instead of a list.</span></span> <span data-ttu-id="cbbcb-169">배열의 요소 액세스는 O(1)입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-169">Element access in arrays is O(1).</span></span>

### <a name="boolean-operations-on-lists"></a><span data-ttu-id="cbbcb-170">목록에 대한 부울 작업</span><span class="sxs-lookup"><span data-stu-id="cbbcb-170">Boolean Operations on Lists</span></span>

<span data-ttu-id="cbbcb-171">[IsEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) 함수는 목록에 요소가 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-171">The [List.isEmpty](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#isEmpty) function determines whether a list has any elements.</span></span>

<span data-ttu-id="cbbcb-172">[Exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) 함수는 목록 요소에 부울 테스트를 적용 하 고, `true` 어떤 요소가 테스트를 충족 하는지 여부를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-172">The [List.exists](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists) function applies a Boolean test to elements of a list and returns `true` if any element satisfies the test.</span></span> <span data-ttu-id="cbbcb-173">[Array.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) 는 유사 하지만 두 목록에서 연속 되는 요소 쌍에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-173">[List.exists2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#exists2) is similar but operates on successive pairs of elements in two lists.</span></span>

<span data-ttu-id="cbbcb-174">다음 코드는 `List.exists`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-174">The following code demonstrates the use of `List.exists`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet1.fs)]

<span data-ttu-id="cbbcb-175">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-175">The output is as follows:</span></span>

```console
For list [0; 1; 2; 3], contains zero is true
```

<span data-ttu-id="cbbcb-176">다음 예에서는 `List.exists2`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-176">The following example demonstrates the use of `List.exists2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet2.fs)]

<span data-ttu-id="cbbcb-177">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-177">The output is as follows:</span></span>

```console
Lists [1; 2; 3; 4; 5] and [5; 4; 3; 2; 1] have at least one equal element at the same position.
```

<span data-ttu-id="cbbcb-178">목록의 모든 요소가 조건을 충족 하는지 여부를 테스트 하려는 경우 forall를 사용할 수 있습니다 [.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall)</span><span class="sxs-lookup"><span data-stu-id="cbbcb-178">You can use [List.forall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall) if you want to test whether all the elements of a list meet a condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet3.fs)]

<span data-ttu-id="cbbcb-179">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-179">The output is as follows:</span></span>

```console
true
false
```

<span data-ttu-id="cbbcb-180">마찬가지로 [list.forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) 는 두 목록의 해당 위치에 있는 모든 요소가 각 요소 쌍을 포함 하는 부울 식을 만족 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-180">Similarly, [List.forall2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#forall2) determines whether all elements in the corresponding positions in two lists satisfy a Boolean expression that involves each pair of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet4.fs)]

<span data-ttu-id="cbbcb-181">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-181">The output is as follows:</span></span>

```console
true
false
```

### <a name="sort-operations-on-lists"></a><span data-ttu-id="cbbcb-182">목록에 대한 정렬 작업</span><span class="sxs-lookup"><span data-stu-id="cbbcb-182">Sort Operations on Lists</span></span>

<span data-ttu-id="cbbcb-183">[List. sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy)및 lists는 함수 정렬 목록을 [사용](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-183">The [List.sort](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sort), [List.sortBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortBy), and [List.sortWith](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sortWith) functions sort lists.</span></span> <span data-ttu-id="cbbcb-184">정렬 함수는 이 세 함수 중 사용할 함수를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-184">The sorting function determines which of these three functions to use.</span></span> <span data-ttu-id="cbbcb-185">`List.sort`는 기본 제네릭 비교를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-185">`List.sort` uses default generic comparison.</span></span> <span data-ttu-id="cbbcb-186">제네릭 비교에서는 제네릭 비교 함수를 기반으로 전역 연산자를 사용해 값을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-186">Generic comparison uses global operators based on the generic compare function to compare values.</span></span> <span data-ttu-id="cbbcb-187">이 함수는 단순한 숫자 형식, 튜플, 레코드, 구분된 공용 구조체, 목록, 배열, 그리고 `System.IComparable`을 구현하는 모든 형식과 같은 광범위한 요소 형식에서 효율적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-187">It works efficiently with a wide variety of element types, such as simple numeric types, tuples, records, discriminated unions, lists, arrays, and any type that implements `System.IComparable`.</span></span> <span data-ttu-id="cbbcb-188">`System.IComparable`을 구현하는 형식의 경우 제네릭 비교에서는 `System.IComparable.CompareTo()` 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-188">For types that implement `System.IComparable`, generic comparison uses the `System.IComparable.CompareTo()` function.</span></span> <span data-ttu-id="cbbcb-189">제네릭 비교는 문자열에도 작동하지만 이 경우에는 문화권과 독립적인 정렬 순서를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-189">Generic comparison also works with strings, but uses a culture-independent sorting order.</span></span> <span data-ttu-id="cbbcb-190">함수 형식 등의 지원되지 않는 형식에는 제네릭 비교를 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-190">Generic comparison should not be used on unsupported types, such as function types.</span></span> <span data-ttu-id="cbbcb-191">또한 기본 제네릭 비교의 성능은 작은 구조의 형식에서 가장 우수합니다. 자주 비교하고 정렬해야 하는 큰 구조의 형식에 대해서는 `System.IComparable`을 구현하고 효율적인 `System.IComparable.CompareTo()` 메서드 구현을 제공하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-191">Also, the performance of the default generic comparison is best for small structured types; for larger structured types that need to be compared and sorted frequently, consider implementing `System.IComparable` and providing an efficient implementation of the `System.IComparable.CompareTo()` method.</span></span>

<span data-ttu-id="cbbcb-192">`List.sortBy`는 정렬 기준으로 사용되는 값을 반환하는 함수를 사용하며 `List.sortWith`는 비교 함수를 인수로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-192">`List.sortBy` takes a function that returns a value that is used as the sort criterion, and `List.sortWith` takes a comparison function as an argument.</span></span> <span data-ttu-id="cbbcb-193">비교를 지원하지 않는 형식으로 작업 중이거나 비교 시 문화권 인식 문자열과 같이 보다 복잡한 비교 의미 체계를 사용할 때는 이 두 함수가 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-193">These latter two functions are useful when you are working with types that do not support comparison, or when the comparison requires more complex comparison semantics, as in the case of culture-aware strings.</span></span>

<span data-ttu-id="cbbcb-194">다음 예에서는 `List.sort`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-194">The following example demonstrates the use of `List.sort`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet5.fs)]

<span data-ttu-id="cbbcb-195">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-195">The output is as follows:</span></span>

```console
[-2; 1; 4; 5; 8]
```

<span data-ttu-id="cbbcb-196">다음 예에서는 `List.sortBy`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-196">The following example demonstrates the use of `List.sortBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet6.fs)]

<span data-ttu-id="cbbcb-197">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-197">The output is as follows:</span></span>

```console
[1; -2; 4; 5; 8]
```

<span data-ttu-id="cbbcb-198">다음 예에서는 `List.sortWith`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-198">The next example demonstrates the use of `List.sortWith`.</span></span> <span data-ttu-id="cbbcb-199">이 예에서는 사용자 지정 비교 함수 `compareWidgets`를 사용하여 먼저 사용자 지정 형식의 한 필드를 비교한 다음 첫 필드의 값이 같으면 다른 필드를 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-199">In this example, the custom comparison function `compareWidgets` is used to first compare one field of a custom type, and then another when the values of the first field are equal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet7.fs)]

<span data-ttu-id="cbbcb-200">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-200">The output is as follows:</span></span>

```console
[{ID = 92;
Rev = 1;}; {ID = 92;
Rev = 1;}; {ID = 100;
Rev = 2;}; {ID = 100;
Rev = 5;}; {ID = 110;
Rev = 1;}]
```

### <a name="search-operations-on-lists"></a><span data-ttu-id="cbbcb-201">목록에 대한 검색 작업</span><span class="sxs-lookup"><span data-stu-id="cbbcb-201">Search Operations on Lists</span></span>

<span data-ttu-id="cbbcb-202">목록에는 다양한 검색 작업이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-202">Numerous search operations are supported for lists.</span></span> <span data-ttu-id="cbbcb-203">가장 간단한 [List. find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find)를 사용 하면 지정 된 조건과 일치 하는 첫 번째 요소를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-203">The simplest, [List.find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#find), enables you to find the first element that matches a given condition.</span></span>

<span data-ttu-id="cbbcb-204">다음 코드 예제에서는 `List.find`를 사용하여 목록에서 5로 나눌 수 있는 첫 번째 숫자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-204">The following code example demonstrates the use of `List.find` to find the first number that is divisible by 5 in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet8.fs)]

<span data-ttu-id="cbbcb-205">해당 결과는 5입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-205">The result is 5.</span></span>

<span data-ttu-id="cbbcb-206">요소를 먼저 변환 해야 하는 경우에는 옵션을 반환 하는 함수를 사용 하 고 첫 번째 옵션 값을 검색 하는 [pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick)를 호출 `Some(x)` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-206">If the elements must be transformed first, call [List.pick](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#pick), which takes a function that returns an option, and looks for the first option value that is `Some(x)`.</span></span> <span data-ttu-id="cbbcb-207">`List.pick`은 요소를 반환하는 대신 `x` 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-207">Instead of returning the element, `List.pick` returns the result `x`.</span></span> <span data-ttu-id="cbbcb-208">일치하는 요소가 없으면 `List.pick`은 `System.Collections.Generic.KeyNotFoundException`을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-208">If no matching element is found, `List.pick` throws `System.Collections.Generic.KeyNotFoundException`.</span></span> <span data-ttu-id="cbbcb-209">다음 코드는 `List.pick`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-209">The following code shows the use of `List.pick`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet9.fs)]

<span data-ttu-id="cbbcb-210">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-210">The output is as follows:</span></span>

```console
"b"
```

<span data-ttu-id="cbbcb-211">다른 검색 작업 그룹인 [\Find](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) 및 관련 함수는 옵션 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-211">Another group of search operations, [List.tryFind](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFind) and related functions, return an option value.</span></span> <span data-ttu-id="cbbcb-212">`List.tryFind` 함수는 조건을 만족하는 목록의 첫 번째 요소가 있으면 해당 요소를 반환하고 요소가 없으면 옵션 값 `None`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-212">The `List.tryFind` function returns the first element of a list that satisfies a condition if such an element exists, but the option value `None` if not.</span></span> <span data-ttu-id="cbbcb-213">변형 [목록. tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) 는 요소 자체가 아닌 요소 (있는 경우)의 인덱스를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-213">The variation [List.tryFindIndex](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#tryFindIndex) returns the index of the element, if one is found, rather than the element itself.</span></span> <span data-ttu-id="cbbcb-214">다음 코드에서는 이러한 함수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-214">These functions are illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet10.fs)]

<span data-ttu-id="cbbcb-215">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-215">The output is as follows:</span></span>

```console
The first even value is 22.
The first even value is at position 8.
```

### <a name="arithmetic-operations-on-lists"></a><span data-ttu-id="cbbcb-216">목록에 대한 산술 연산</span><span class="sxs-lookup"><span data-stu-id="cbbcb-216">Arithmetic Operations on Lists</span></span>

<span data-ttu-id="cbbcb-217">합계 및 평균과 같은 일반적인 산술 연산은 [목록 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-217">Common arithmetic operations such as sum and average are built into the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span> <span data-ttu-id="cbbcb-218">[List. sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum)을 사용 하려면 목록 요소 형식이 연산자를 지원 하 `+` 고 값이 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-218">To work with [List.sum](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sum), the list element type must support the `+` operator and have a zero value.</span></span> <span data-ttu-id="cbbcb-219">모든 기본 제공 연산 형식은 이러한 조건을 만족합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-219">All built-in arithmetic types satisfy these conditions.</span></span> <span data-ttu-id="cbbcb-220">[Average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average)를 사용 하 여 작업 하려면 요소 형식이 나머지 없이 나누기를 지원 해야 합니다 .이는 정수 형식을 제외 하지만 부동 소수점 형식을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-220">To work with [List.average](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#average), the element type must support division without a remainder, which excludes integral types but allows for floating point types.</span></span> <span data-ttu-id="cbbcb-221">[List. sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) 및 [array.averageby](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) 함수는 함수를 매개 변수로 사용 하며,이 함수의 결과는 합계 또는 평균 값을 계산 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-221">The [List.sumBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#sumBy) and [List.averageBy](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#averageBy) functions take a function as a parameter, and this function's results are used to calculate the values for the sum or average.</span></span>

<span data-ttu-id="cbbcb-222">다음 코드는 `List.sum`, `List.sumBy` 및 `List.average`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-222">The following code demonstrates the use of `List.sum`, `List.sumBy`, and `List.average`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet11.fs)]

<span data-ttu-id="cbbcb-223">출력은 `1.000000`입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-223">The output is `1.000000`.</span></span>

<span data-ttu-id="cbbcb-224">다음 코드는 `List.averageBy`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-224">The following code shows the use of `List.averageBy`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet12.fs)]

<span data-ttu-id="cbbcb-225">출력은 `5.5`입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-225">The output is `5.5`.</span></span>

### <a name="lists-and-tuples"></a><span data-ttu-id="cbbcb-226">목록 및 튜플</span><span class="sxs-lookup"><span data-stu-id="cbbcb-226">Lists and Tuples</span></span>

<span data-ttu-id="cbbcb-227">튜플을 포함하는 목록은 zip 및 unzip 함수를 통해 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-227">Lists that contain tuples can be manipulated by zip and unzip functions.</span></span> <span data-ttu-id="cbbcb-228">이러한 함수는 단일 값의 두 목록을 튜플 목록 하나로 결합하거나 튜플 목록 하나를 단일 값의 두 목록으로 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-228">These functions combine two lists of single values into one list of tuples or separate one list of tuples into two lists of single values.</span></span> <span data-ttu-id="cbbcb-229">가장 간단한 [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) 함수는 단일 요소 목록 두 개를 사용 하 여 단일 튜플 쌍 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-229">The simplest [List.zip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip) function takes two lists of single elements and produces a single list of tuple pairs.</span></span> <span data-ttu-id="cbbcb-230">다른 버전인 [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3)은 단일 요소 목록 세 개를 사용 하 여 세 개의 요소가 포함 된 단일 튜플 목록을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-230">Another version, [List.zip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#zip3), takes three lists of single elements and produces a single list of tuples that have three elements.</span></span> <span data-ttu-id="cbbcb-231">다음 코드 예제에서는 `List.zip`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-231">The following code example demonstrates the use of `List.zip`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet13.fs)]

<span data-ttu-id="cbbcb-232">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-232">The output is as follows:</span></span>

```console
[(1, -1); (2, -2); (3; -3)]
```

<span data-ttu-id="cbbcb-233">다음 코드 예제에서는 `List.zip3`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-233">The following code example demonstrates the use of `List.zip3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet14.fs)]

<span data-ttu-id="cbbcb-234">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-234">The output is as follows:</span></span>

```console
[(1, -1, 0); (2, -2, 0); (3, -3, 0)]
```

<span data-ttu-id="cbbcb-235">해당 하는 압축 풀기 버전 (list.unzip3 및 [목록](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3))은 튜플에 있는 튜플 및 반환 목록 목록을 사용 합니다. 여기서 첫 번째 목록에는 각 튜플의 첫 번째 요소를 포함 하 고 두 번째 목록에는 각 튜플의 두 번째 요소가 포함 [됩니다.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip)</span><span class="sxs-lookup"><span data-stu-id="cbbcb-235">The corresponding unzip versions, [List.unzip](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip) and [List.unzip3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#unzip3), take lists of tuples and return lists in a tuple, where the first list contains all the elements that were first in each tuple, and the second list contains the second element of each tuple, and so on.</span></span>

<span data-ttu-id="cbbcb-236">다음 코드 예제에서는 [List. 압축](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21)해제를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-236">The following code example demonstrates the use of [List.unzip](https://msdn.microsoft.com/library/639db80c-41b5-45bb-a6b4-1eaa04d61d21).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet15.fs)]

<span data-ttu-id="cbbcb-237">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-237">The output is as follows:</span></span>

```console
([1; 3], [2; 4])
[1; 3] [2; 4]
```

<span data-ttu-id="cbbcb-238">다음 코드 예제에서는 [list.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4)를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-238">The following code example demonstrates the use of [List.unzip3](https://msdn.microsoft.com/library/43078c77-32ec-4342-85b3-c31ccf984db4).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet16.fs)]

<span data-ttu-id="cbbcb-239">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-239">The output is as follows:</span></span>

```console
([1; 4], [2; 5], [3; 6])
```

### <a name="operating-on-list-elements"></a><span data-ttu-id="cbbcb-240">목록 요소에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="cbbcb-240">Operating on List Elements</span></span>

<span data-ttu-id="cbbcb-241">F#에서는 목록 요소에 대한 여러 작업을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-241">F# supports a variety of operations on list elements.</span></span> <span data-ttu-id="cbbcb-242">가장 간단한 방법은 목록의 모든 요소에 대해 함수를 호출할 수 있도록 하는 [iter입니다.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter)</span><span class="sxs-lookup"><span data-stu-id="cbbcb-242">The simplest is [List.iter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter), which enables you to call a function on every element of a list.</span></span> <span data-ttu-id="cbbcb-243">[List.iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2)를 사용 하면 두 목록의 요소에 대 한 작업을 수행할 수 있습니다 [. list.iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri)는 `List.iter` 각 요소의 인덱스가 각 요소에 대해 호출 되는 함수에 인수로 전달 되는 것을 제외 하 고 및의 기능과의 조합 인 [list.iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2)를 사용 하는 것을 제외 하 고 `List.iter2` `List.iteri` 와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-243">Variations include [List.iter2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iter2), which enables you to perform an operation on elements of two lists, [List.iteri](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri), which is like `List.iter` except that the index of each element is passed as an argument to the function that is called for each element, and [List.iteri2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#iteri2), which is a combination of the functionality of `List.iter2` and `List.iteri`.</span></span> <span data-ttu-id="cbbcb-244">다음 코드 예제에서는 이러한 함수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-244">The following code example illustrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet17.fs)]

<span data-ttu-id="cbbcb-245">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-245">The output is as follows:</span></span>

```console
List.iter: element is 1
List.iter: element is 2
List.iter: element is 3
List.iteri: element 0 is 1
List.iteri: element 1 is 2
List.iteri: element 2 is 3
List.iter2: elements are 1 4
List.iter2: elements are 2 5
List.iter2: elements are 3 6
List.iteri2: element 0 of list1 is 1; element 0 of list2 is 4
List.iteri2: element 1 of list1 is 2; element 1 of list2 is 5
List.iteri2: element 2 of list1 is 3; element 2 of list2 is 6
```

<span data-ttu-id="cbbcb-246">자주 사용 되는 또 다른 함수는 목록 요소를 변환 하는 [목록입니다. map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map)을 사용 하면 목록의 각 요소에 함수를 적용 하 고 모든 결과를 새 목록에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-246">Another frequently used function that transforms list elements is [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map), which enables you to apply a function to each element of a list and put all the results into a new list.</span></span> <span data-ttu-id="cbbcb-247">[Array.map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) 및 [list.map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) 는 여러 목록을 사용 하는 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-247">[List.map2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map2) and [List.map3](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map3) are variations that take multiple lists.</span></span> <span data-ttu-id="cbbcb-248">[Array.mapi2 및 list.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2)를 사용할 수도 [있습니다. 요소](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) 외에도 함수는 각 요소의 인덱스를 전달 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-248">You can also use [List.mapi](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi) and [List.mapi2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#mapi2), if, in addition to the element, the function needs to be passed the index of each element.</span></span> <span data-ttu-id="cbbcb-249">`List.mapi2`와 `List.mapi`의 차이점은 `List.mapi2`의 경우 목록 두 개를 사용한다는 것뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-249">The only difference between `List.mapi2` and `List.mapi` is that `List.mapi2` works with two lists.</span></span> <span data-ttu-id="cbbcb-250">다음 예에서는 [map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-250">The following example illustrates [List.map](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#map).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet18.fs)]

<span data-ttu-id="cbbcb-251">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-251">The output is as follows:</span></span>

```console
[2; 3; 4]
```

<span data-ttu-id="cbbcb-252">다음 예제에서는 `List.map2`의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-252">The following example shows the use of `List.map2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet19.fs)]

<span data-ttu-id="cbbcb-253">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-253">The output is as follows:</span></span>

```console
[5; 7; 9]
```

<span data-ttu-id="cbbcb-254">다음 예제에서는 `List.map3`의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-254">The following example shows the use of `List.map3`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet20.fs)]

<span data-ttu-id="cbbcb-255">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-255">The output is as follows:</span></span>

```console
[7; 10; 13]
```

<span data-ttu-id="cbbcb-256">다음 예제에서는 `List.mapi`의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-256">The following example shows the use of `List.mapi`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet21.fs)]

<span data-ttu-id="cbbcb-257">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-257">The output is as follows:</span></span>

```console
[1; 3; 5]
```

<span data-ttu-id="cbbcb-258">다음 예제에서는 `List.mapi2`의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-258">The following example shows the use of `List.mapi2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet22.fs)]

<span data-ttu-id="cbbcb-259">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-259">The output is as follows:</span></span>

```console
[0; 7; 18]
```

<span data-ttu-id="cbbcb-260">Lists [는와 유사 합니다.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) `List.map` 단, 각 요소는 목록을 생성 하 고 이러한 모든 목록은 최종 목록에 연결 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-260">[List.collect](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#collect) is like `List.map`, except that each element produces a list and all these lists are concatenated into a final list.</span></span> <span data-ttu-id="cbbcb-261">다음 코드에서는 목록의 각 요소가 숫자 3개를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-261">In the following code, each element of the list generates three numbers.</span></span> <span data-ttu-id="cbbcb-262">이러한 숫자는 모두 목록 하나에 수집됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-262">These are all collected into one list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet23.fs)]

<span data-ttu-id="cbbcb-263">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-263">The output is as follows:</span></span>

```console
[1; 2; 3; 2; 4; 6; 3; 6; 9]
```

<span data-ttu-id="cbbcb-264">부울 조건을 사용 하 고 지정 된 조건을 충족 하는 요소로만 구성 된 새 목록을 생성 하는 [list. filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter)를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-264">You can also use [List.filter](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#filter), which takes a Boolean condition and produces a new list that consists only of elements that satisfy the given condition.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet24.fs)]

<span data-ttu-id="cbbcb-265">그러면 `[2; 4; 6]` 목록이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-265">The resulting list is `[2; 4; 6]`.</span></span>

<span data-ttu-id="cbbcb-266">지도와 필터 [목록의 조합입니다 .를 선택](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) 하면 요소를 동시에 변환 하 고 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-266">A combination of map and filter, [List.choose](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#choose) enables you to transform and select elements at the same time.</span></span> <span data-ttu-id="cbbcb-267">`List.choose`는 목록의 각 요소에 대한 옵션을 반환하는 함수를 적용하고, 함수가 옵션 값 `Some`을 반환하면 요소에 대해 새 결과 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-267">`List.choose` applies a function that returns an option to each element of a list, and returns a new list of the results for elements when the function returns the option value `Some`.</span></span>

<span data-ttu-id="cbbcb-268">다음 코드는 `List.choose`를 사용하여 단어 목록에서 대문자로 표기된 단어를 선택하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-268">The following code demonstrates the use of `List.choose` to select capitalized words out of a list of words.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet25.fs)]

<span data-ttu-id="cbbcb-269">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-269">The output is as follows:</span></span>

```console
["Rome's"; "Bob's"]
```

### <a name="operating-on-multiple-lists"></a><span data-ttu-id="cbbcb-270">여러 목록에 대한 작업</span><span class="sxs-lookup"><span data-stu-id="cbbcb-270">Operating on Multiple Lists</span></span>

<span data-ttu-id="cbbcb-271">여러 목록을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-271">Lists can be joined together.</span></span> <span data-ttu-id="cbbcb-272">두 목록을 하나로 조인 하려면 [List. append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-272">To join two lists into one, use [List.append](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#append).</span></span> <span data-ttu-id="cbbcb-273">세 개 이상의 목록을 조인 하려면 [concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-273">To join more than two lists, use [List.concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#concat).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet26.fs)]

### <a name="fold-and-scan-operations"></a><span data-ttu-id="cbbcb-274">접기 및 검사 작업</span><span class="sxs-lookup"><span data-stu-id="cbbcb-274">Fold and Scan Operations</span></span>

<span data-ttu-id="cbbcb-275">모든 목록 요소가 상호 종속되어야 하는 목록 작업도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-275">Some list operations involve interdependencies between all of the list elements.</span></span> <span data-ttu-id="cbbcb-276">접기 및 검사 작업은 `List.iter` `List.map` 각 요소에서 함수를 호출 하는 및와 유사 하지만 이러한 연산은 계산을 통해 정보를 전달 하는 *누적기* 라는 추가 매개 변수를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-276">The fold and scan operations are like `List.iter` and `List.map` in that you invoke a function on each element, but these operations provide an additional parameter called the *accumulator* that carries information through the computation.</span></span>

<span data-ttu-id="cbbcb-277">목록에 대해 계산을 수행하려면 `List.fold`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-277">Use `List.fold` to perform a calculation on a list.</span></span>

<span data-ttu-id="cbbcb-278">다음 코드 예제에서는 [List. 접기](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) 를 사용 하 여 다양 한 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-278">The following code example demonstrates the use of [List.fold](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold) to perform various operations.</span></span>

<span data-ttu-id="cbbcb-279">이 함수는 목록을 트래버스합니다. 누적기 `acc`는 계산이 진행되면서 전달되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-279">The list is traversed; the accumulator `acc` is a value that is passed along as the calculation proceeds.</span></span> <span data-ttu-id="cbbcb-280">첫 번째 인수는 누적기와 목록 요소를 사용하여 해당 목록 요소에 대한 계산의 중간 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-280">The first argument takes the accumulator and the list element, and returns the interim result of the calculation for that list element.</span></span> <span data-ttu-id="cbbcb-281">두 번째 인수는 누적기의 초기 값입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-281">The second argument is the initial value of the accumulator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet27.fs)]

<span data-ttu-id="cbbcb-282">이러한 함수 중 함수 이름에 숫자가 있는 버전은 둘 이상의 목록에 대해 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-282">The versions of these functions that have a digit in the function name operate on more than one list.</span></span> <span data-ttu-id="cbbcb-283">예를 들어 [list.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) 는 두 개의 목록에서 계산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-283">For example, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) performs computations on two lists.</span></span>

<span data-ttu-id="cbbcb-284">다음 예에서는 `List.fold2`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-284">The following example demonstrates the use of `List.fold2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet28.fs)]

<span data-ttu-id="cbbcb-285">`List.fold` 및 [List. scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) 은 `List.fold` 추가 매개 변수의 최종 값을 반환 하지만 `List.scan` 추가 매개 변수의 최종 값과 함께 중간 값의 목록을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-285">`List.fold` and [List.scan](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#scan) differ in that `List.fold` returns the final value of the extra parameter, but `List.scan` returns the list of the intermediate values (along with the final value) of the extra parameter.</span></span>

<span data-ttu-id="cbbcb-286">이러한 각 함수에는 목록이 트래버스 되는 순서와 인수의 순서와 다른 역방향 변형 (예: [foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack))이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-286">Each of these functions includes a reverse variation, for example, [List.foldBack](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack), which differs in the order in which the list is traversed and the order of the arguments.</span></span> <span data-ttu-id="cbbcb-287">또한 `List.fold` 및에 `List.foldBack` 는 동일한 길이의 두 목록을 사용 하는 [list.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) 및 [array.foldback2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2)변형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-287">Also, `List.fold` and `List.foldBack` have variations, [List.fold2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#fold2) and [List.foldBack2](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#foldBack2), that take two lists of equal length.</span></span> <span data-ttu-id="cbbcb-288">각 요소에 대해 실행되는 함수는 두 목록의 해당 요소를 사용하여 일부 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-288">The function that executes on each element can use corresponding elements of both lists to perform some action.</span></span> <span data-ttu-id="cbbcb-289">다음 예에서와 같이 두 목록의 요소 형식은 다를 수 있습니다. 여기서 한 목록은 은행 계좌의 거래 금액을 포함하고 다른 목록은 거래 형식(입금 또는 출금)을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-289">The element types of the two lists can be different, as in the following example, in which one list contains transaction amounts for a bank account, and the other list contains the type of transaction: deposit or withdrawal.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet29.fs)]

<span data-ttu-id="cbbcb-290">합계와 같은 계산의 경우 `List.fold` 및 `List.foldBack`을 사용해도 결과는 동일합니다. 트래버스 순서에 따라 결과가 달라지지 않기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-290">For a calculation like summation, `List.fold` and `List.foldBack` have the same effect because the result does not depend on the order of traversal.</span></span> <span data-ttu-id="cbbcb-291">다음 예에서는 `List.foldBack`을 사용하여 목록에 요소를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-291">In the following example, `List.foldBack` is used to add the elements in a list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet30.fs)]

<span data-ttu-id="cbbcb-292">다음 예에서는 은행 계좌 예로 다시 돌아옵니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-292">The following example returns to the bank account example.</span></span> <span data-ttu-id="cbbcb-293">이번에는 새로운 거래 형식인 이자 계산을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-293">This time a new transaction type is added: an interest calculation.</span></span> <span data-ttu-id="cbbcb-294">따라서 최종 잔액은 거래 순서에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-294">The ending balance now depends on the order of transactions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet34.fs)]

<span data-ttu-id="cbbcb-295">함수 [목록입니다.](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) 는 별도의 누적기를 전달 하는 `List.fold` `List.scan` 대신 `List.reduce` 요소 형식의 두 인수를 사용 하는 함수를 사용 하 고, 이러한 인수 중 하나가 누적기의 역할을 하 여 계산의 중간 결과를 저장 한다는 점을 제외 하면 및와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-295">The function [List.reduce](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#reduce) is somewhat like `List.fold` and `List.scan`, except that instead of passing around a separate accumulator, `List.reduce` takes a function that takes two arguments of the element type instead of just one, and one of those arguments acts as the accumulator, meaning that it stores the intermediate result of the computation.</span></span> <span data-ttu-id="cbbcb-296">`List.reduce`는 먼저 처음 두 목록 요소에 대해 실행된 후 해당 작업의 결과를 다음 요소와 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-296">`List.reduce` starts by operating on the first two list elements, and then uses the result of the operation along with the next element.</span></span> <span data-ttu-id="cbbcb-297">고유한 형식이 지정된 별도의 누적기가 없으므로 `List.reduce`는 누적기와 요소 형식이 같을 때만 `List.fold` 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-297">Because there is not a separate accumulator that has its own type, `List.reduce` can be used in place of `List.fold` only when the accumulator and the element type have the same type.</span></span> <span data-ttu-id="cbbcb-298">다음 코드는 `List.reduce`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-298">The following code demonstrates the use of `List.reduce`.</span></span> <span data-ttu-id="cbbcb-299">제공된 목록에 요소가 없으면 `List.reduce`는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-299">`List.reduce` throws an exception if the list provided has no elements.</span></span>

<span data-ttu-id="cbbcb-300">다음 코드에서는 첫 번째 람다 식 호출에 인수 2와 4가 사용되며 결과로 6이 반환됩니다. 그 다음 호출에는 인수 6과 10이 사용되며 결과로 16이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-300">In the following code, the first call to the lambda expression is given the arguments 2 and 4, and returns 6, and the next call is given the arguments 6 and 10, so the result is 16.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lists/snippet33.fs)]

### <a name="converting-between-lists-and-other-collection-types"></a><span data-ttu-id="cbbcb-301">목록과 기타 컬렉션 형식 간 변환</span><span class="sxs-lookup"><span data-stu-id="cbbcb-301">Converting Between Lists and Other Collection Types</span></span>

<span data-ttu-id="cbbcb-302">`List` 모듈은 시퀀스와 배열 간 변환을 위한 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-302">The `List` module provides functions for converting to and from both sequences and arrays.</span></span> <span data-ttu-id="cbbcb-303">시퀀스에서 또는 시퀀스로 변환 하려면 [list. toseq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) 또는 [List. ofseq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-303">To convert to or from a sequence, use [List.toSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toSeq) or [List.ofSeq](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofSeq).</span></span> <span data-ttu-id="cbbcb-304">배열과 변환 하려면 [list. toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) 또는 [List. ofarray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-304">To convert to or from an array, use [List.toArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#toArray) or [List.ofArray](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html#ofArray).</span></span>

### <a name="additional-operations"></a><span data-ttu-id="cbbcb-305">추가 작업</span><span class="sxs-lookup"><span data-stu-id="cbbcb-305">Additional Operations</span></span>

<span data-ttu-id="cbbcb-306">목록의 추가 작업에 대 한 자세한 내용은 라이브러리 참조 항목 [목록 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cbbcb-306">For information about additional operations on lists, see the library reference topic [List Module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span>

## <a name="see-also"></a><span data-ttu-id="cbbcb-307">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cbbcb-307">See also</span></span>

- [<span data-ttu-id="cbbcb-308">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="cbbcb-308">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="cbbcb-309">F# 형식</span><span class="sxs-lookup"><span data-stu-id="cbbcb-309">F# Types</span></span>](fsharp-types.md)
- [<span data-ttu-id="cbbcb-310">시퀀스</span><span class="sxs-lookup"><span data-stu-id="cbbcb-310">Sequences</span></span>](sequences.md)
- [<span data-ttu-id="cbbcb-311">배열</span><span class="sxs-lookup"><span data-stu-id="cbbcb-311">Arrays</span></span>](arrays.md)
- [<span data-ttu-id="cbbcb-312">옵션</span><span class="sxs-lookup"><span data-stu-id="cbbcb-312">Options</span></span>](options.md)
