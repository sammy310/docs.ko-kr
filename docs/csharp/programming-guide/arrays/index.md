---
title: 배열 - C# 프로그래밍 가이드
description: C#의 배열 데이터 구조에 형식이 동일한 변수를 여러 개 저장합니다. 형식을 지정해 배열을 선언하거나 개체를 지정해 모든 형식을 저장합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: e302ff2e4c2488c4899c4eb99a666d2d322119ce
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474737"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="eabed-104">배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="eabed-104">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="eabed-105">배열 데이터 구조에 형식이 동일한 변수를 여러 개 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-105">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="eabed-106">요소의 형식을 지정하여 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-106">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="eabed-107">배열이 모든 형식의 요소를 저장하도록 하려는 경우 `object`를 해당 형식으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-107">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="eabed-108">C#의 통합 형식 시스템에서 모든 형식(사전 정의되거나 사용자 정의된 형식, 참조 형식, 값 형식)은 <xref:System.Object>에서 직접 또는 간접적으로 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-108">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="eabed-109">예제</span><span class="sxs-lookup"><span data-stu-id="eabed-109">Example</span></span>

<span data-ttu-id="eabed-110">다음 예제에서는 단일 차원, 다차원 및 가변 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-110">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="eabed-111">배열 개요</span><span class="sxs-lookup"><span data-stu-id="eabed-111">Array overview</span></span>

<span data-ttu-id="eabed-112">배열에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-112">An array has the following properties:</span></span>

- <span data-ttu-id="eabed-113">배열은 [단일 차원](single-dimensional-arrays.md), [다차원](multidimensional-arrays.md) 또는 [가변](jagged-arrays.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-113">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="eabed-114">차원 수와 각 차원의 길이는 배열 인스턴스를 만들 때 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-114">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="eabed-115">이러한 값은 인스턴스의 수명 동안 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-115">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="eabed-116">숫자 배열 요소의 기본값은 0으로 설정되고, 참조 요소는 null로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-116">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="eabed-117">가변 배열은 여러 배열로 구성되어 있기 때문에 해당 요소가 참조 형식이며, `null`로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="eabed-118">배열은 0으로 인덱싱됩니다. `n` 요소는 `0`부터 `n-1`로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-118">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="eabed-119">배열 요소 형식은 배열 형식을 비롯한 어떤 형식도 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-119">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="eabed-120">배열 형식은 <xref:System.Array> 추상 기본 형식에서 파생된 [참조 형식](../../language-reference/keywords/reference-types.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-120">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="eabed-121">이 형식은 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.Generic.IEnumerable%601>을 구현하므로 C#의 모든 배열에서 [foreach](../../language-reference/keywords/foreach-in.md) 반복을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eabed-121">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="eabed-122">관련 단원</span><span class="sxs-lookup"><span data-stu-id="eabed-122">Related sections</span></span>

- [<span data-ttu-id="eabed-123">개체로 사용되는 배열</span><span class="sxs-lookup"><span data-stu-id="eabed-123">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="eabed-124">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="eabed-124">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="eabed-125">인수로 배열 전달</span><span class="sxs-lookup"><span data-stu-id="eabed-125">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="eabed-126">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="eabed-126">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="eabed-127">참조</span><span class="sxs-lookup"><span data-stu-id="eabed-127">See also</span></span>

- [<span data-ttu-id="eabed-128">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="eabed-128">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="eabed-129">컬렉션</span><span class="sxs-lookup"><span data-stu-id="eabed-129">Collections</span></span>](../concepts/collections.md)
