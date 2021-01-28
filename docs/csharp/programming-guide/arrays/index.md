---
title: 배열 - C# 프로그래밍 가이드
description: C#의 배열 데이터 구조에 형식이 동일한 변수를 여러 개 저장합니다. 형식을 지정해 배열을 선언하거나 개체를 지정해 모든 형식을 저장합니다.
ms.date: 01/22/2021
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: 203d8b86da4e74d8c5397132a0ba68618eedf348
ms.sourcegitcommit: 4d5e25a46aa7cd0d29b4b9227b92987354d444c4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2021
ms.locfileid: "98794761"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="ea548-104">배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ea548-104">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="ea548-105">배열 데이터 구조에 형식이 동일한 변수를 여러 개 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-105">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="ea548-106">요소의 형식을 지정하여 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-106">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="ea548-107">배열이 모든 형식의 요소를 저장하도록 하려는 경우 `object`를 해당 형식으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-107">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="ea548-108">C#의 통합 형식 시스템에서 모든 형식(사전 정의되거나 사용자 정의된 형식, 참조 형식, 값 형식)은 <xref:System.Object>에서 직접 또는 간접적으로 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="ea548-109">예제</span><span class="sxs-lookup"><span data-stu-id="ea548-109">Example</span></span>

<span data-ttu-id="ea548-110">다음 예제에서는 단일 차원, 다차원 및 가변 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-110">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="ea548-111">배열 개요</span><span class="sxs-lookup"><span data-stu-id="ea548-111">Array overview</span></span>

<span data-ttu-id="ea548-112">배열에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-112">An array has the following properties:</span></span>

- <span data-ttu-id="ea548-113">배열은 [단일 차원](single-dimensional-arrays.md), [다차원](multidimensional-arrays.md) 또는 [가변](jagged-arrays.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-113">An array can be [single-dimensional](single-dimensional-arrays.md), [multidimensional](multidimensional-arrays.md) or [jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="ea548-114">차원 수와 각 차원의 길이는 배열 인스턴스를 만들 때 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-114">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="ea548-115">이러한 값은 인스턴스의 수명 동안 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-115">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="ea548-116">숫자 배열 요소의 기본값은 0으로 설정되고, 참조 요소는 null로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-116">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="ea548-117">가변 배열은 여러 배열로 구성되어 있기 때문에 해당 요소가 참조 형식이며, `null`로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="ea548-118">배열은 0으로 인덱싱됩니다. `n` 요소는 `0`부터 `n-1`로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-118">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="ea548-119">배열 요소 형식은 배열 형식을 비롯한 어떤 형식도 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-119">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="ea548-120">배열 형식은 <xref:System.Array> 추상 기본 형식에서 파생된 [참조 형식](../../language-reference/keywords/reference-types.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-120">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="ea548-121">이 형식은 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.Generic.IEnumerable%601>을 구현하므로 C#의 모든 배열에서 [foreach](../../language-reference/keywords/foreach-in.md) 반복을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-121">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

### <a name="arrays-as-objects"></a><span data-ttu-id="ea548-122">개체 형식 배열</span><span class="sxs-lookup"><span data-stu-id="ea548-122">Arrays as Objects</span></span>

<span data-ttu-id="ea548-123">C#의 배열은 C 및 C++와 같이 인접한 메모리의 주소 지정 가능한 영역이 아니라 실제로 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-123">In C#, arrays are actually objects, and not just addressable regions of contiguous memory as in C and C++.</span></span> <span data-ttu-id="ea548-124"><xref:System.Array>는 모든 배열 형식의 추상 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-124"><xref:System.Array> is the abstract base type of all array types.</span></span> <span data-ttu-id="ea548-125"><xref:System.Array>에 포함된 속성 및 다른 클래스 멤버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-125">You can use the properties and other class members that <xref:System.Array> has.</span></span> <span data-ttu-id="ea548-126">이러한 예로 <xref:System.Array.Length%2A> 속성을 사용하여 배열의 길이를 가져오는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-126">An example of this is using the <xref:System.Array.Length%2A> property to get the length of an array.</span></span> <span data-ttu-id="ea548-127">다음 코드에서는 `numbers` 배열의 길이(`5`)를 `lengthOfNumbers`라는 변수에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-127">The following code assigns the length of the `numbers` array, which is `5`, to a variable called `lengthOfNumbers`:</span></span>

[!code-csharp[csProgGuideArrays#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#3)]

<span data-ttu-id="ea548-128"><xref:System.Array> 클래스는 배열의 정렬, 검색 및 복사를 위한 다른 여러 유용한 메서드와 속성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-128">The <xref:System.Array> class provides many other useful methods and properties for sorting, searching, and copying arrays.</span></span> <span data-ttu-id="ea548-129">다음 예제에서는 <xref:System.Array.Rank%2A> 속성을 사용하여 배열의 차원 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="ea548-129">The following example uses the <xref:System.Array.Rank%2A> property to display the number of dimensions of an array.</span></span>

[!code-csharp[csProgGuideArrays#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#2)]

## <a name="see-also"></a><span data-ttu-id="ea548-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="ea548-130">See also</span></span>

- [<span data-ttu-id="ea548-131">단일 차원 배열 사용 방법</span><span class="sxs-lookup"><span data-stu-id="ea548-131">How to use single-dimensional arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="ea548-132">다차원 배열 사용 방법</span><span class="sxs-lookup"><span data-stu-id="ea548-132">How to use multi-dimensional arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="ea548-133">가변 배열 사용 방법</span><span class="sxs-lookup"><span data-stu-id="ea548-133">How to use jagged arrays</span></span>](jagged-arrays.md)
- [<span data-ttu-id="ea548-134">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="ea548-134">Using foreach with arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="ea548-135">인수로 배열 전달</span><span class="sxs-lookup"><span data-stu-id="ea548-135">Passing arrays as arguments</span></span>](passing-arrays-as-arguments.md)
- [<span data-ttu-id="ea548-136">암시적으로 형식화된 배열</span><span class="sxs-lookup"><span data-stu-id="ea548-136">Implicitly typed arrays</span></span>](implicitly-typed-arrays.md)
- [<span data-ttu-id="ea548-137">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ea548-137">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ea548-138">컬렉션</span><span class="sxs-lookup"><span data-stu-id="ea548-138">Collections</span></span>](../concepts/collections.md)

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]
