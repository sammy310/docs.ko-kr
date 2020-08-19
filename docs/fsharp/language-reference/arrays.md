---
title: 배열
description: 'F # 프로그래밍 언어에서 배열을 만들고 사용 하는 방법에 대해 알아봅니다.'
ms.date: 08/13/2020
ms.openlocfilehash: 37f781ccd2c7bc2ca2c7b93bda53bbb3ea93b504
ms.sourcegitcommit: cbb19e56d48cf88375d35d0c27554d4722761e0d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2020
ms.locfileid: "88608504"
---
# <a name="arrays"></a><span data-ttu-id="da575-103">배열</span><span class="sxs-lookup"><span data-stu-id="da575-103">Arrays</span></span>

<span data-ttu-id="da575-104">배열은 동일한 형식의 연속 데이터 요소에 대 한 고정 크기의 변경 가능한 컬렉션으로, 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-104">Arrays are fixed-size, zero-based, mutable collections of consecutive data elements that are all of the same type.</span></span>

## <a name="create-arrays"></a><span data-ttu-id="da575-105">배열 만들기</span><span class="sxs-lookup"><span data-stu-id="da575-105">Create arrays</span></span>

<span data-ttu-id="da575-106">여러 가지 방법으로 배열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-106">You can create arrays in several ways.</span></span> <span data-ttu-id="da575-107">다음 예제와 같이 및 사이에 연속 값을 나열 `[|` 하 `|]` 고 세미콜론으로 구분 하 여 작은 배열을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-107">You can create a small array by listing consecutive values between `[|` and `|]` and separated by semicolons, as shown in the following examples.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet1.fs)]

<span data-ttu-id="da575-108">각 요소를 별도의 줄에 배치할 수도 있습니다 .이 경우 세미콜론 구분 기호는 선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="da575-108">You can also put each element on a separate line, in which case the semicolon separator is optional.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet2.fs)]

<span data-ttu-id="da575-109">배열 요소의 형식은 사용 된 리터럴에서 유추 되며 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-109">The type of the array elements is inferred from the literals used and must be consistent.</span></span> <span data-ttu-id="da575-110">다음 코드는 1.0가 float이 고 2와 3이 정수 이므로 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-110">The following code causes an error because 1.0 is a float and 2 and 3 are integers.</span></span>

```fsharp
// Causes an error.
// let array2 = [| 1.0; 2; 3 |]
```

<span data-ttu-id="da575-111">시퀀스 식을 사용 하 여 배열을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-111">You can also use sequence expressions to create arrays.</span></span> <span data-ttu-id="da575-112">다음은 1에서 10 사이의 정수 제곱 배열을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="da575-112">Following is an example that creates an array of squares of integers from 1 to 10.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet3.fs)]

<span data-ttu-id="da575-113">모든 요소가 0으로 초기화 되는 배열을 만들려면를 사용 `Array.zeroCreate` 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-113">To create an array in which all the elements are initialized to zero, use `Array.zeroCreate`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet4.fs)]

## <a name="access-elements"></a><span data-ttu-id="da575-114">액세스 요소</span><span class="sxs-lookup"><span data-stu-id="da575-114">Access elements</span></span>

<span data-ttu-id="da575-115">점 연산자 ( `.` )와 대괄호 (및)를 사용 하 여 배열 요소에 액세스할 수 있습니다 `[` `]` .</span><span class="sxs-lookup"><span data-stu-id="da575-115">You can access array elements by using a dot operator (`.`) and brackets (`[` and `]`).</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet5.fs)]

<span data-ttu-id="da575-116">배열 인덱스는 0부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-116">Array indexes start at 0.</span></span>

<span data-ttu-id="da575-117">배열의 하위 범위를 지정 하는 데 사용할 수 있는 조각 표기법을 사용 하 여 배열 요소에 액세스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-117">You can also access array elements by using slice notation, which enables you to specify a subrange of the array.</span></span> <span data-ttu-id="da575-118">조각 표기법의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-118">Examples of slice notation follow.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet51.fs)]

<span data-ttu-id="da575-119">조각 표기법을 사용 하면 배열의 새 복사본이 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="da575-119">When slice notation is used, a new copy of the array is created.</span></span>

## <a name="array-types-and-modules"></a><span data-ttu-id="da575-120">배열 형식 및 모듈</span><span class="sxs-lookup"><span data-stu-id="da575-120">Array types and modules</span></span>

<span data-ttu-id="da575-121">모든 F # 배열의 형식은 .NET Framework 형식입니다 <xref:System.Array?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="da575-121">The type of all F# arrays is the .NET Framework type <xref:System.Array?displayProperty=nameWithType>.</span></span> <span data-ttu-id="da575-122">따라서 F # 배열은에서 사용할 수 있는 모든 기능을 지원 <xref:System.Array?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-122">Therefore, F# arrays support all the functionality available in <xref:System.Array?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="da575-123">[ `Array` 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) 은 1 차원 배열에 대 한 작업을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-123">The [`Array` module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html) supports operations on one-dimensional arrays.</span></span> <span data-ttu-id="da575-124">모듈 `Array2D` , 및에는 `Array3D` `Array4D` 각각 2, 3 및 4 차원 배열에 대 한 작업을 지 원하는 함수가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-124">The modules `Array2D`, `Array3D`, and `Array4D` contain functions that support operations on arrays of two, three, and four dimensions, respectively.</span></span> <span data-ttu-id="da575-125">을 사용 하 여 4 보다 큰 차수 배열을 만들 수 있습니다 <xref:System.Array?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="da575-125">You can create arrays of rank greater than four by using <xref:System.Array?displayProperty=nameWithType>.</span></span>

### <a name="simple-functions"></a><span data-ttu-id="da575-126">간단한 함수</span><span class="sxs-lookup"><span data-stu-id="da575-126">Simple functions</span></span>

<span data-ttu-id="da575-127">[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="da575-127">[`Array.get`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#get) gets an element.</span></span> <span data-ttu-id="da575-128">[`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) 배열의 길이를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-128">[`Array.length`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#length) gives the length of an array.</span></span> <span data-ttu-id="da575-129">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) 요소를 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-129">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) sets an element to a specified value.</span></span> <span data-ttu-id="da575-130">다음 코드 예제에서는 이러한 함수를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-130">The following code example illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet9.fs)]

<span data-ttu-id="da575-131">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-131">The output is as follows.</span></span>

```console
0 1 2 3 4 5 6 7 8 9
```

### <a name="functions-that-create-arrays"></a><span data-ttu-id="da575-132">배열을 만드는 함수</span><span class="sxs-lookup"><span data-stu-id="da575-132">Functions that create arrays</span></span>

<span data-ttu-id="da575-133">여러 함수는 기존 배열을 요구 하지 않고 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-133">Several functions create arrays without requiring an existing array.</span></span> <span data-ttu-id="da575-134">[`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) 요소가 포함 되지 않은 새 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-134">[`Array.empty`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#empty) creates a new array that does not contain any elements.</span></span> <span data-ttu-id="da575-135">[`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) 지정 된 크기의 배열을 만들고 모든 요소를 제공 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-135">[`Array.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#create) creates an array of a specified size and sets all the elements to provided values.</span></span> <span data-ttu-id="da575-136">[`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) 지정 된 차원과 요소를 생성 하는 함수를 지정 하 여 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-136">[`Array.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#init) creates an array, given a dimension and a function to generate the elements.</span></span> <span data-ttu-id="da575-137">[`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) 모든 요소가 배열의 형식에 대해 0 값으로 초기화 되는 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-137">[`Array.zeroCreate`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zeroCreate) creates an array in which all the elements are initialized to the zero value for the array's type.</span></span> <span data-ttu-id="da575-138">다음 코드에서는 이러한 함수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-138">The following code demonstrates these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet91.fs)]

<span data-ttu-id="da575-139">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-139">The output is as follows.</span></span>

```console
Length of empty array: 0
Area of floats set to 5.0: [|5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0; 5.0|]
Array of squares: [|0; 1; 4; 9; 16; 25; 36; 49; 64; 81|]
```

<span data-ttu-id="da575-140">[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) 기존 배열에서 복사 된 요소를 포함 하는 새 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-140">[`Array.copy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#copy) creates a new array that contains elements that are copied from an existing array.</span></span> <span data-ttu-id="da575-141">복사본은 단순 복사본입니다. 즉, 요소 형식이 참조 형식이 면 참조만 복사 되 고 기본 개체는 복사 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-141">Note that the copy is a shallow copy, which means that if the element type is a reference type, only the reference is copied, not the underlying object.</span></span> <span data-ttu-id="da575-142">다음 코드 예제에서는 그 구체적인 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-142">The following code example illustrates this.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet11.fs)]

<span data-ttu-id="da575-143">위의 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-143">The output of the preceding code is as follows:</span></span>

```console
[|Test1; Test2; |]
[|; Test2; |]
```

<span data-ttu-id="da575-144">`Test1`새 요소를 만드는 작업은에서 참조를 덮어쓰므로 `firstArray` 에서 여전히에 있는 빈 문자열에 대 한 원래 참조에는 영향을 주지 않기 때문에이 문자열은 첫 번째 배열에만 나타납니다 `secondArray` .</span><span class="sxs-lookup"><span data-stu-id="da575-144">The string `Test1` appears only in the first array because the operation of creating a new element overwrites the reference in `firstArray` but does not affect the original reference to an empty string that is still present in `secondArray`.</span></span> <span data-ttu-id="da575-145">`Test2` `Insert` 형식에 대 한 작업이 <xref:System.Text.StringBuilder?displayProperty=nameWithType> 두 배열에서 참조 되는 기본 개체에 영향을 주기 때문에 두 배열에 문자열이 모두 표시 됩니다 <xref:System.Text.StringBuilder?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="da575-145">The string `Test2` appears in both arrays because the `Insert` operation on the <xref:System.Text.StringBuilder?displayProperty=nameWithType> type affects the underlying <xref:System.Text.StringBuilder?displayProperty=nameWithType> object, which is referenced in both arrays.</span></span>

<span data-ttu-id="da575-146">[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) 배열의 하위 범위에서 새 배열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-146">[`Array.sub`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sub) generates a new array from a subrange of an array.</span></span> <span data-ttu-id="da575-147">시작 인덱스 및 길이를 제공 하 여 하위 범위를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-147">You specify the subrange by providing the starting index and the length.</span></span> <span data-ttu-id="da575-148">다음 코드는 `Array.sub`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-148">The following code demonstrates the use of `Array.sub`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet12.fs)]

<span data-ttu-id="da575-149">출력은 하위 배열을 요소 5에서 시작 하 고 10 개의 요소를 포함 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-149">The output shows that the subarray starts at element 5 and contains 10 elements.</span></span>

```console
[|5; 6; 7; 8; 9; 10; 11; 12; 13; 14|]
```

<span data-ttu-id="da575-150">[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) 두 개의 기존 배열을 결합 하 여 새 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-150">[`Array.append`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#append) creates a new array by combining two existing arrays.</span></span>

<span data-ttu-id="da575-151">다음 코드에서는 **배열. append**를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-151">The following code demonstrates **Array.append**.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet13.fs)]

<span data-ttu-id="da575-152">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-152">The output of the preceding code is as follows.</span></span>

```console
[|1; 2; 3; 4; 5; 6|]
```

<span data-ttu-id="da575-153">[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) 새 배열에 포함할 배열의 요소를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-153">[`Array.choose`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#choose) selects elements of an array to include in a new array.</span></span> <span data-ttu-id="da575-154">다음 코드에서는을 보여 줍니다 `Array.choose` .</span><span class="sxs-lookup"><span data-stu-id="da575-154">The following code demonstrates `Array.choose`.</span></span> <span data-ttu-id="da575-155">배열의 요소 형식은 옵션 형식에서 반환 되는 값의 형식과 일치할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-155">Note that the element type of the array does not have to match the type of the value returned in the option type.</span></span> <span data-ttu-id="da575-156">이 예제에서 요소 형식은이 `int` 고 옵션은 다항식 함수의 결과인 `elem*elem - 1` 부동 소수점 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="da575-156">In this example, the element type is `int` and the option is the result of a polynomial function, `elem*elem - 1`, as a floating point number.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet14.fs)]

<span data-ttu-id="da575-157">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-157">The output of the preceding code is as follows.</span></span>

```console
[|3.0; 15.0; 35.0; 63.0; 99.0|]
```

<span data-ttu-id="da575-158">[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) 기존 배열의 각 배열 요소에 대해 지정 된 함수를 실행 한 다음 함수에 의해 생성 된 요소를 수집 하 여 새 배열로 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-158">[`Array.collect`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#collect) runs a specified function on each array element of an existing array and then collects the elements generated by the function and combines them into a new array.</span></span> <span data-ttu-id="da575-159">다음 코드에서는을 보여 줍니다 `Array.collect` .</span><span class="sxs-lookup"><span data-stu-id="da575-159">The following code demonstrates `Array.collect`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet15.fs)]

<span data-ttu-id="da575-160">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-160">The output of the preceding code is as follows.</span></span>

```console
[|0; 1; 0; 1; 2; 3; 4; 5; 0; 1; 2; 3; 4; 5; 6; 7; 8; 9; 10|]
```

<span data-ttu-id="da575-161">[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) 배열의 시퀀스를 사용 하 여 단일 배열로 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-161">[`Array.concat`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#concat) takes a sequence of arrays and combines them into a single array.</span></span> <span data-ttu-id="da575-162">다음 코드에서는을 보여 줍니다 `Array.concat` .</span><span class="sxs-lookup"><span data-stu-id="da575-162">The following code demonstrates `Array.concat`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet16.fs)]

<span data-ttu-id="da575-163">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-163">The output of the preceding code is as follows.</span></span>

```console
[|(1, 1, 1); (1, 2, 2); (1, 3, 3); (2, 1, 2); (2, 2, 4); (2, 3, 6); (3, 1, 3);
(3, 2, 6); (3, 3, 9)|]
```

<span data-ttu-id="da575-164">[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) 부울 조건 함수를 사용 하 고 조건이 true 인 입력 배열의 요소만 포함 하는 새 배열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-164">[`Array.filter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#filter) takes a Boolean condition function and generates a new array that contains only those elements from the input array for which the condition is true.</span></span> <span data-ttu-id="da575-165">다음 코드에서는을 보여 줍니다 `Array.filter` .</span><span class="sxs-lookup"><span data-stu-id="da575-165">The following code demonstrates `Array.filter`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet17.fs)]

<span data-ttu-id="da575-166">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-166">The output of the preceding code is as follows.</span></span>

```console
[|2; 4; 6; 8; 10|]
```

<span data-ttu-id="da575-167">[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) 기존 배열의 순서를 반대로 하 여 새 배열을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-167">[`Array.rev`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#rev) generates a new array by reversing the order of an existing array.</span></span> <span data-ttu-id="da575-168">다음 코드에서는을 보여 줍니다 `Array.rev` .</span><span class="sxs-lookup"><span data-stu-id="da575-168">The following code demonstrates `Array.rev`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet18.fs)]

<span data-ttu-id="da575-169">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-169">The output of the preceding code is as follows.</span></span>

```console
"Hello world!"
```

<span data-ttu-id="da575-170">다음 예제와 같이 파이프라인 연산자 ()를 사용 하 여 배열을 변환 하는 배열 모듈의 함수를 쉽게 결합할 수 있습니다 `|>` .</span><span class="sxs-lookup"><span data-stu-id="da575-170">You can easily combine functions in the array module that transform arrays by using the pipeline operator (`|>`), as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet19.fs)]

<span data-ttu-id="da575-171">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-171">The output is</span></span>

```console
[|100; 36; 16; 4|]
```

### <a name="multidimensional-arrays"></a><span data-ttu-id="da575-172">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="da575-172">Multidimensional arrays</span></span>

<span data-ttu-id="da575-173">다차원 배열을 만들 수 있지만 다차원 배열 리터럴을 작성 하기 위한 구문이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-173">A multidimensional array can be created, but there is no syntax for writing a multidimensional array literal.</span></span> <span data-ttu-id="da575-174">연산자를 사용 [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) 하 여 배열 요소의 시퀀스 시퀀스에서 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-174">Use the operator [`array2D`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html) to create an array from a sequence of sequences of array elements.</span></span> <span data-ttu-id="da575-175">시퀀스는 배열 또는 목록 리터럴일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-175">The sequences can be array or list literals.</span></span> <span data-ttu-id="da575-176">예를 들어 다음 코드는 2 차원 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-176">For example, the following code creates a two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet20.fs)]

<span data-ttu-id="da575-177">또한 함수를 사용 하 여 [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) 두 차원의 배열을 초기화할 수 있으며, 3 개 차원 및 4 차원 배열에도 유사한 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-177">You can also use the function [`Array2D.init`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#init) to initialize arrays of two dimensions, and similar functions are available for arrays of three and four dimensions.</span></span> <span data-ttu-id="da575-178">이러한 함수는 요소를 만드는 데 사용 되는 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-178">These functions take a function that is used to create the elements.</span></span> <span data-ttu-id="da575-179">함수를 지정 하는 대신 초기 값으로 설정 된 요소를 포함 하는 2 차원 배열을 만들려면 [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) 최대 4 차원 배열에도 사용할 수 있는 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-179">To create a two-dimensional array that contains elements set to an initial value instead of specifying a function, use the [`Array2D.create`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-array2dmodule.html#create) function, which is also available for arrays up to four dimensions.</span></span> <span data-ttu-id="da575-180">다음 코드 예제에서는 먼저 원하는 요소를 포함 하는 배열 배열을 만든 다음를 사용 하 여 `Array2D.init` 원하는 2 차원 배열을 생성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-180">The following code example first shows how to create an array of arrays that contain the desired elements, and then uses `Array2D.init` to generate the desired two-dimensional array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet21.fs)]

<span data-ttu-id="da575-181">배열 인덱싱 및 조각화 구문은 차수가 4 인 배열에 대해 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-181">Array indexing and slicing syntax is supported for arrays up to rank 4.</span></span> <span data-ttu-id="da575-182">여러 차원에서 인덱스를 지정 하는 경우 다음 코드 예제에 나와 있는 것 처럼 쉼표를 사용 하 여 인덱스를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-182">When you specify an index in multiple dimensions, you use commas to separate the indexes, as illustrated in the following code example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet22.fs)]

<span data-ttu-id="da575-183">2 차원 배열의 형식은 `<type>[,]` (예:,)로 작성 되 `int[,]` `double[,]` 고 3 차원 배열의 형식은로 작성 되며, `<type>[,,]` 더 큰 차원의 배열에 대해서는로 작성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-183">The type of a two-dimensional array is written out as `<type>[,]` (for example, `int[,]`, `double[,]`), and the type of a three-dimensional array is written as `<type>[,,]`, and so on for arrays of higher dimensions.</span></span>

<span data-ttu-id="da575-184">다차원 배열에는 1 차원 배열에 사용할 수 있는 함수의 하위 집합만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-184">Only a subset of the functions available for one-dimensional arrays is also available for multidimensional arrays.</span></span>

### <a name="array-slicing-and-multidimensional-arrays"></a><span data-ttu-id="da575-185">배열 조각화 및 다차원 배열</span><span class="sxs-lookup"><span data-stu-id="da575-185">Array slicing and multidimensional arrays</span></span>

<span data-ttu-id="da575-186">2 차원 배열 (행렬)에서 범위를 지정 하 고 와일드 카드 () 문자를 사용 하 여 하위 행렬을 추출 하 여 `*` 전체 행 또는 열을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-186">In a two-dimensional array (a matrix), you can extract a sub-matrix by specifying ranges and using a wildcard (`*`) character to specify whole rows or columns.</span></span>

```fsharp
// Get rows 1 to N from an NxM matrix (returns a matrix):
matrix.[1.., *]

// Get rows 1 to 3 from a matrix (returns a matrix):
matrix.[1..3, *]

// Get columns 1 to 3 from a matrix (returns a matrix):
matrix.[*, 1..3]

// Get a 3x3 submatrix:
matrix.[1..3, 1..3]
```

<span data-ttu-id="da575-187">다차원 배열을 같거나 낮은 차원의 subarrays으로 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-187">You can decompose a multidimensional array into subarrays of the same or lower dimension.</span></span> <span data-ttu-id="da575-188">예를 들어 단일 행 또는 열을 지정 하 여 행렬에서 벡터를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-188">For example, you can obtain a vector from a matrix by specifying a single row or column.</span></span>

```fsharp
// Get row 3 from a matrix as a vector:
matrix.[3, *]

// Get column 3 from a matrix as a vector:
matrix.[*, 3]
```

<span data-ttu-id="da575-189">요소 액세스 연산자 및 오버 로드 된 메서드를 구현 하는 형식에 대해이 조각화 구문을 사용할 수 있습니다 `GetSlice` .</span><span class="sxs-lookup"><span data-stu-id="da575-189">You can use this slicing syntax for types that implement the element access operators and overloaded `GetSlice` methods.</span></span> <span data-ttu-id="da575-190">예를 들어 다음 코드는 F # 2D 배열을 래핑하고 항목 속성을 구현 하 여 배열 인덱싱에 대 한 지원을 제공 하 고 세 가지 버전의를 구현 하는 행렬 유형을 만듭니다 `GetSlice` .</span><span class="sxs-lookup"><span data-stu-id="da575-190">For example, the following code creates a Matrix type that wraps the F# 2D array, implements an Item property to provide support for array indexing, and implements three versions of `GetSlice`.</span></span> <span data-ttu-id="da575-191">이 코드를 행렬 형식에 대 한 템플릿으로 사용할 수 있는 경우이 단원에서 설명 하는 모든 조각 작업을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-191">If you can use this code as a template for your matrix types, you can use all the slicing operations that this section describes.</span></span>

```fsharp
type Matrix<'T>(N: int, M: int) =
    let internalArray = Array2D.zeroCreate<'T> N M

    member this.Item
        with get(a: int, b: int) = internalArray.[a, b]
        and set(a: int, b: int) (value:'T) = internalArray.[a, b] <- value

    member this.GetSlice(rowStart: int option, rowFinish : int option, colStart: int option, colFinish : int option) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[rowStart..rowFinish, colStart..colFinish]

    member this.GetSlice(row: int, colStart: int option, colFinish: int option) =
        let colStart =
            match colStart with
            | Some(v) -> v
            | None -> 0
        let colFinish =
            match colFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(1) - 1
        internalArray.[row, colStart..colFinish]

    member this.GetSlice(rowStart: int option, rowFinish: int option, col: int) =
        let rowStart =
            match rowStart with
            | Some(v) -> v
            | None -> 0
        let rowFinish =
            match rowFinish with
            | Some(v) -> v
            | None -> internalArray.GetLength(0) - 1
        internalArray.[rowStart..rowFinish, col]

module test =
    let generateTestMatrix x y =
        let matrix = new Matrix<float>(3, 3)
        for i in 0..2 do
            for j in 0..2 do
                matrix.[i, j] <- float(i) * x - float(j) * y
        matrix

    let test1 = generateTestMatrix 2.3 1.1
    let submatrix = test1.[0..1, 0..1]
    printfn "%A" submatrix

    let firstRow = test1.[0,*]
    let secondRow = test1.[1,*]
    let firstCol = test1.[*,0]
    printfn "%A" firstCol
```

### <a name="boolean-functions-on-arrays"></a><span data-ttu-id="da575-192">배열의 부울 함수</span><span class="sxs-lookup"><span data-stu-id="da575-192">Boolean functions on arrays</span></span>

<span data-ttu-id="da575-193">[`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) 각각 하나 또는 두 배열의 함수 및 테스트 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="da575-193">The functions [`Array.exists`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists) and [`Array.exists2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#exists2) test elements in either one or two arrays, respectively.</span></span> <span data-ttu-id="da575-194">이러한 함수는 테스트 함수를 사용 하 고 `true` `Array.exists2` 조건을 충족 하는 요소 또는에 대 한 요소 쌍이 있는 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-194">These functions take a test function and return `true` if there is an element (or element pair for `Array.exists2`) that satisfies the condition.</span></span>

<span data-ttu-id="da575-195">다음 코드에서는 및를 사용 하는 방법을 보여 줍니다 `Array.exists` `Array.exists2` .</span><span class="sxs-lookup"><span data-stu-id="da575-195">The following code demonstrates the use of `Array.exists` and `Array.exists2`.</span></span> <span data-ttu-id="da575-196">이러한 예제에서는 인수 중 하나 (이 경우에는 함수 인수)만 적용 하 여 새 함수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-196">In these examples, new functions are created by applying only one of the arguments, in these cases, the function argument.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet23.fs)]

<span data-ttu-id="da575-197">위의 코드는 다음과 같이 출력 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-197">The output of the preceding code is as follows.</span></span>

```console
true
false
false
true
```

<span data-ttu-id="da575-198">마찬가지로 함수는 [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) 배열을 테스트 하 여 모든 요소가 부울 조건을 충족 하는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-198">Similarly, the function [`Array.forall`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall) tests an array to determine whether every element satisfies a Boolean condition.</span></span> <span data-ttu-id="da575-199">[`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2)동일한 길이의 두 배열의 요소를 포함 하는 부울 함수를 사용 하 여 변형이 동일한 작업을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-199">The variation [`Array.forall2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#forall2) does the same thing by using a Boolean function that involves elements of two arrays of equal length.</span></span> <span data-ttu-id="da575-200">다음 코드에서는 이러한 함수를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-200">The following code illustrates the use of these functions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet24.fs)]

<span data-ttu-id="da575-201">이러한 예제에 대 한 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-201">The output for these examples is as follows.</span></span>

```console
false
true
true
false
```

### <a name="search-arrays"></a><span data-ttu-id="da575-202">검색 배열</span><span class="sxs-lookup"><span data-stu-id="da575-202">Search arrays</span></span>

<span data-ttu-id="da575-203">[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) 부울 함수를 사용 하 여 함수가 반환 하는 첫 번째 요소를 반환 `true` 하거나 <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> 조건을 충족 하는 요소가 없는 경우을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="da575-203">[`Array.find`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#find) takes a Boolean function and returns the first element for which the function returns `true`, or raises a <xref:System.Collections.Generic.KeyNotFoundException?displayProperty=nameWithType> if no element that satisfies the condition is found.</span></span> <span data-ttu-id="da575-204">[`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) 는 `Array.find` 요소 자체 대신 요소의 인덱스를 반환 한다는 점을 제외 하 고와 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-204">[`Array.findIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#findIndex) is like `Array.find`, except that it returns the index of the element instead of the element itself.</span></span>

<span data-ttu-id="da575-205">다음 코드에서는 및를 사용 하 여 `Array.find` `Array.findIndex` 완전 한 정사각형과 완전 한 큐브인 숫자를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-205">The following code uses `Array.find` and `Array.findIndex` to locate a number that is both a perfect square and perfect cube.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet25.fs)]

<span data-ttu-id="da575-206">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-206">The output is as follows.</span></span>

```console
The first element that is both a square and a cube is 64 and its index is 62.
```

<span data-ttu-id="da575-207">[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) 는 `Array.find` 결과가 옵션 형식 이라는 점을 제외 하 고는와 유사 하며, `None` 요소를 찾을 수 없는 경우를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-207">[`Array.tryFind`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFind) is like `Array.find`, except that its result is an option type, and it returns `None` if no element is found.</span></span> <span data-ttu-id="da575-208">`Array.tryFind``Array.find`일치 하는 요소가 배열에 있는지 여부를 알 수 없는 경우 대신를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-208">`Array.tryFind` should be used instead of `Array.find` when you do not know whether a matching element is in the array.</span></span> <span data-ttu-id="da575-209">마찬가지로 [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) `Array.findIndex` 옵션 유형이 반환 값 이라는 점을 제외 하 고는와 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-209">Similarly, [`Array.tryFindIndex`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryFindIndex) is like `Array.findIndex` except that the option type is the return value.</span></span> <span data-ttu-id="da575-210">요소를 찾을 수 없는 경우 옵션은 `None` 입니다.</span><span class="sxs-lookup"><span data-stu-id="da575-210">If no element is found, the option is `None`.</span></span>

<span data-ttu-id="da575-211">다음 코드는 `Array.tryFind`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-211">The following code demonstrates the use of `Array.tryFind`.</span></span> <span data-ttu-id="da575-212">이 코드는 이전 코드에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="da575-212">This code depends on the previous code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet26.fs)]

<span data-ttu-id="da575-213">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-213">The output is as follows.</span></span>

```console
Found an element: 1
Found an element: 729
Failed to find a matching element.
```

<span data-ttu-id="da575-214">[`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick)요소를 찾을 뿐만 아니라 요소를 변환 해야 하는 경우에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-214">Use [`Array.tryPick`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#tryPick) when you need to transform an element in addition to finding it.</span></span> <span data-ttu-id="da575-215">결과는 함수에서 변환 된 요소를 옵션 값으로 반환 하는 첫 번째 요소 이거나, `None` 이러한 요소가 없는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="da575-215">The result is the first element for which the function returns the transformed element as an option value, or `None` if no such element is found.</span></span>

<span data-ttu-id="da575-216">다음 코드는 `Array.tryPick`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="da575-216">The following code shows the use of `Array.tryPick`.</span></span> <span data-ttu-id="da575-217">이 경우 람다 식 대신 코드를 단순화 하기 위해 몇 가지 로컬 도우미 함수가 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="da575-217">In this case, instead of a lambda expression, several local helper functions are defined to simplify the code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet27.fs)]

<span data-ttu-id="da575-218">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-218">The output is as follows.</span></span>

```console
Found an element 1 with square root 1 and cube root 1.
Found an element 64 with square root 8 and cube root 4.
Found an element 729 with square root 27 and cube root 9.
Found an element 4096 with square root 64 and cube root 16.
Did not find an element that is both a perfect square and a perfect cube.
```

### <a name="perform-computations-on-arrays"></a><span data-ttu-id="da575-219">배열에서 계산 수행</span><span class="sxs-lookup"><span data-stu-id="da575-219">Perform computations on arrays</span></span>

<span data-ttu-id="da575-220">[`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average)함수는 배열의 각 요소에 대 한 평균을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-220">The [`Array.average`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#average) function returns the average of each element in an array.</span></span> <span data-ttu-id="da575-221">정수로 정확히 나누기를 지 원하는 요소 형식으로 제한 됩니다. 여기에는 부동 소수점 형식이 포함 되지만 정수 계열 형식은 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-221">It is limited to element types that support exact division by an integer, which includes floating point types but not integral types.</span></span> <span data-ttu-id="da575-222">[`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy)함수는 각 요소에 대해 함수를 호출한 결과의 평균을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-222">The [`Array.averageBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#averageBy) function returns the average of the results of calling a function on each element.</span></span> <span data-ttu-id="da575-223">정수 계열 형식의 배열에 대해를 사용 하 `Array.averageBy` 고 함수에서 각 요소를 계산에 대 한 부동 소수점 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-223">For an array of integral type, you can use `Array.averageBy` and have the function convert each element to a floating point type for the computation.</span></span>

<span data-ttu-id="da575-224">[`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) 요소 형식이 지 원하는 경우 또는를 사용 하 여 maximum 또는 minimum 요소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="da575-224">Use [`Array.max`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#max) or [`Array.min`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#min) to get the maximum or minimum element, if the element type supports it.</span></span> <span data-ttu-id="da575-225">마찬가지로 [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) 및 [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) 는 비교를 지 원하는 형식으로 변환 하는 등의 방법으로 함수를 먼저 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-225">Similarly, [`Array.maxBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#maxBy) and [`Array.minBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#minBy) allow a function to be executed first, perhaps to transform to a type that supports comparison.</span></span>

<span data-ttu-id="da575-226">[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) 배열의 요소를 추가 하 고 [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) 각 요소에 대해 함수를 호출 하 고 결과를 함께 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-226">[`Array.sum`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sum) adds the elements of an array, and [`Array.sumBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sumBy) calls a function on each element and adds the results together.</span></span>

<span data-ttu-id="da575-227">반환 값을 저장 하지 않고 배열의 각 요소에 대해 함수를 실행 하려면를 사용 [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter) 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-227">To execute a function on each element in an array without storing the return values, use [`Array.iter`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter).</span></span> <span data-ttu-id="da575-228">길이가 같은 두 배열이 포함 된 함수의 경우를 사용 [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2) 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-228">For a function involving two arrays of equal length, use [`Array.iter2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iter2).</span></span> <span data-ttu-id="da575-229">함수의 결과 배열을 유지 해야 하는 경우에 [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2) 는 한 번에 두 배열에 대해 작동 하는 또는를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-229">If you also need to keep an array of the results of the function, use [`Array.map`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map) or [`Array.map2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#map2), which operates on two arrays at a time.</span></span>

<span data-ttu-id="da575-230">변형을 사용 하 여 [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) 요소의 인덱스를 계산에 포함 시킬 수 있습니다. 및의 경우에도 [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) 마찬가지입니다. [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2)</span><span class="sxs-lookup"><span data-stu-id="da575-230">The variations [`Array.iteri`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri) and [`Array.iteri2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#iteri2) allow the index of the element to be involved in the computation; the same is true for [`Array.mapi`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi) and [`Array.mapi2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#mapi2).</span></span>

<span data-ttu-id="da575-231">,, [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold) ,, 및 함수는 [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack) [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce) [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack) [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan) [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) 배열의 모든 요소를 포함 하는를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-231">The functions [`Array.fold`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold), [`Array.foldBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack), [`Array.reduce`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduce), [`Array.reduceBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#reduceBack), [`Array.scan`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scan), and [`Array.scanBack`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#scanBack) execute algorithms that involve all the elements of an array.</span></span> <span data-ttu-id="da575-232">마찬가지로, 변형이 [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) [`Array.foldBack2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack2) 두 배열에 대해 계산을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-232">Similarly, the variations [`Array.fold2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fold2) and [`Array.foldBack2`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#foldBack2) perform computations on two arrays.</span></span>

<span data-ttu-id="da575-233">계산을 수행 하는 이러한 함수는 [목록 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html)에 있는 동일한 이름의 함수에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-233">These functions for performing computations correspond to the functions of the same name in the [List module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-listmodule.html).</span></span> <span data-ttu-id="da575-234">사용 예제는 [목록](lists.md)을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="da575-234">For usage examples, see [Lists](lists.md).</span></span>

### <a name="modify-arrays"></a><span data-ttu-id="da575-235">배열 수정</span><span class="sxs-lookup"><span data-stu-id="da575-235">Modify arrays</span></span>

<span data-ttu-id="da575-236">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) 요소를 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-236">[`Array.set`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#set) sets an element to a specified value.</span></span> <span data-ttu-id="da575-237">[`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) 배열의 요소 범위를 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-237">[`Array.fill`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#fill) sets a range of elements in an array to a specified value.</span></span> <span data-ttu-id="da575-238">다음 코드에서는의 예제를 제공 합니다 `Array.fill` .</span><span class="sxs-lookup"><span data-stu-id="da575-238">The following code provides an example of `Array.fill`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/arrays/snippet28.fs)]

<span data-ttu-id="da575-239">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-239">The output is as follows.</span></span>

```console
[|1; 2; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 0; 23; 24; 25|]
```

<span data-ttu-id="da575-240">[`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit)를 사용 하 여 한 배열의 하위 섹션을 다른 배열로 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-240">You can use [`Array.blit`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#blit) to copy a subsection of one array to another array.</span></span>

### <a name="convert-to-and-from-other-types"></a><span data-ttu-id="da575-241">다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="da575-241">Convert to and from other types</span></span>

<span data-ttu-id="da575-242">[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) 목록에서 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-242">[`Array.ofList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofList) creates an array from a list.</span></span> <span data-ttu-id="da575-243">[`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) 시퀀스에서 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="da575-243">[`Array.ofSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#ofSeq) creates an array from a sequence.</span></span> <span data-ttu-id="da575-244">[`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) 및 [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) 는 배열 형식에서 이러한 다른 컬렉션 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-244">[`Array.toList`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toList) and [`Array.toSeq`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#toSeq) convert to these other collection types from the array type.</span></span>

### <a name="sort-arrays"></a><span data-ttu-id="da575-245">배열 정렬</span><span class="sxs-lookup"><span data-stu-id="da575-245">Sort arrays</span></span>

<span data-ttu-id="da575-246">[`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort)제네릭 비교 함수를 사용 하 여 배열을 정렬 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-246">Use [`Array.sort`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sort) to sort an array by using the generic comparison function.</span></span> <span data-ttu-id="da575-247">키 [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) 에 대 한 제네릭 비교 함수를 사용 하 여 정렬 하려면 *키*라고 하는 값을 생성 하는 함수를 지정 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-247">Use [`Array.sortBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortBy) to specify a function that generates a value, referred to as a *key*, to sort by using the generic comparison function on the key.</span></span> <span data-ttu-id="da575-248">[`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith)사용자 지정 비교 함수를 제공 하려는 경우를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-248">Use [`Array.sortWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortWith) if you want to provide a custom comparison function.</span></span> <span data-ttu-id="da575-249">`Array.sort`, `Array.sortBy` 및는 `Array.sortWith` 모두 정렬 된 배열을 새 배열로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-249">`Array.sort`, `Array.sortBy`, and `Array.sortWith` all return the sorted array as a new array.</span></span> <span data-ttu-id="da575-250">[`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace), 및 변형은 [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy) [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) 새 배열을 반환 하는 대신 기존 배열을 수정 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-250">The variations [`Array.sortInPlace`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlace), [`Array.sortInPlaceBy`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceBy), and [`Array.sortInPlaceWith`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#sortInPlaceWith) modify the existing array instead of returning a new one.</span></span>

### <a name="arrays-and-tuples"></a><span data-ttu-id="da575-251">배열 및 튜플</span><span class="sxs-lookup"><span data-stu-id="da575-251">Arrays and tuples</span></span>

<span data-ttu-id="da575-252">함수 [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) 및는 [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) 튜플 쌍의 배열을 배열의 튜플로 변환 하 고 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="da575-252">The functions [`Array.zip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip) and [`Array.unzip`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip) convert arrays of tuple pairs to tuples of arrays and vice versa.</span></span> <span data-ttu-id="da575-253">[`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) 및는 세 개의 요소로 된 튜플 [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) 또는 세 개의 배열로 된 튜플로 작업 한다는 점을 제외 하 고는 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="da575-253">[`Array.zip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#zip3) and [`Array.unzip3`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule.html#unzip3) are similar except that they work with tuples of three elements or tuples of three arrays.</span></span>

## <a name="parallel-computations-on-arrays"></a><span data-ttu-id="da575-254">배열에 대 한 병렬 계산</span><span class="sxs-lookup"><span data-stu-id="da575-254">Parallel computations on arrays</span></span>

<span data-ttu-id="da575-255">모듈에는 [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) 배열에 대 한 병렬 계산을 수행 하는 함수가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-255">The module [`Array.Parallel`](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-arraymodule-parallel.html) contains functions for performing parallel computations on arrays.</span></span> <span data-ttu-id="da575-256">버전 4 이전 버전의 .NET Framework를 대상으로 하는 응용 프로그램에서는이 모듈을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da575-256">This module is not available in applications that target versions of the .NET Framework prior to version 4.</span></span>

## <a name="see-also"></a><span data-ttu-id="da575-257">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da575-257">See also</span></span>

- [<span data-ttu-id="da575-258">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="da575-258">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="da575-259">F# 형식</span><span class="sxs-lookup"><span data-stu-id="da575-259">F# Types</span></span>](fsharp-types.md)
