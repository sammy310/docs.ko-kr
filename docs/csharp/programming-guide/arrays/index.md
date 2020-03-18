---
title: 배열 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- arrays [C#]
- C# language, arrays
ms.assetid: bb79bdde-e570-4c30-adb0-1dd5759ae041
ms.openlocfilehash: bbabc84c144e5b3415c19f346b890782e251662c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2020
ms.locfileid: "75715049"
---
# <a name="arrays-c-programming-guide"></a><span data-ttu-id="4a3e8-102">배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="4a3e8-102">Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="4a3e8-103">배열 데이터 구조에 형식이 동일한 변수를 여러 개 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-103">You can store multiple variables of the same type in an array data structure.</span></span> <span data-ttu-id="4a3e8-104">요소의 형식을 지정하여 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-104">You declare an array by specifying the type of its elements.</span></span> <span data-ttu-id="4a3e8-105">배열이 모든 형식의 요소를 저장하도록 하려는 경우 `object`를 해당 형식으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-105">If you want the array to store elements of any type, you can specify `object` as its type.</span></span> <span data-ttu-id="4a3e8-106">C#의 통합 형식 시스템에서 사용자 정의 및 미리 정의된 참조 형식과 값 형식을 비롯한 모든 형식은 직접 또는 간접적으로 <xref:System.Object>에서 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-106">In the unified type system of C#, all types, predefined and user-defined, reference types and value types, inherit directly or indirectly from <xref:System.Object>.</span></span>

```csharp
type[] arrayName;
```

## <a name="example"></a><span data-ttu-id="4a3e8-107">예제</span><span class="sxs-lookup"><span data-stu-id="4a3e8-107">Example</span></span>

<span data-ttu-id="4a3e8-108">다음 예제에서는 단일 차원, 다차원 및 가변 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-108">The following example creates single-dimensional, multidimensional, and jagged arrays:</span></span>

[!code-csharp[csProgGuideArrays#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#1)]

## <a name="array-overview"></a><span data-ttu-id="4a3e8-109">배열 개요</span><span class="sxs-lookup"><span data-stu-id="4a3e8-109">Array overview</span></span>

<span data-ttu-id="4a3e8-110">배열에는 다음과 같은 속성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-110">An array has the following properties:</span></span>

- <span data-ttu-id="4a3e8-111">배열은 [단일 차원](single-dimensional-arrays.md), [다차원](multidimensional-arrays.md) 또는 [가변](jagged-arrays.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-111">An array can be [Single-Dimensional](single-dimensional-arrays.md), [Multidimensional](multidimensional-arrays.md) or [Jagged](jagged-arrays.md).</span></span>
- <span data-ttu-id="4a3e8-112">차원 수와 각 차원의 길이는 배열 인스턴스를 만들 때 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-112">The number of dimensions and the length of each dimension are established when the array instance is created.</span></span> <span data-ttu-id="4a3e8-113">이러한 값은 인스턴스의 수명 동안 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-113">These values can't be changed during the lifetime of the instance.</span></span>
- <span data-ttu-id="4a3e8-114">숫자 배열 요소의 기본값은 0으로 설정되고, 참조 요소는 null로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-114">The default values of numeric array elements are set to zero, and reference elements are set to null.</span></span>
- <span data-ttu-id="4a3e8-115">가변 배열은 여러 배열로 구성되어 있기 때문에 해당 요소가 참조 형식이며, `null`로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-115">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>
- <span data-ttu-id="4a3e8-116">배열은 0으로 인덱싱됩니다. `n` 요소는 `0`부터 `n-1`로 인덱싱됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-116">Arrays are zero indexed: an array with `n` elements is indexed from `0` to `n-1`.</span></span>
- <span data-ttu-id="4a3e8-117">배열 요소 형식은 배열 형식을 비롯한 어떤 형식도 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-117">Array elements can be of any type, including an array type.</span></span>
- <span data-ttu-id="4a3e8-118">배열 형식은 [ 추상 기본 형식에서 파생된 ](../../language-reference/keywords/reference-types.md)참조 형식<xref:System.Array>입니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-118">Array types are [reference types](../../language-reference/keywords/reference-types.md) derived from the abstract base type <xref:System.Array>.</span></span> <span data-ttu-id="4a3e8-119">이 형식은 <xref:System.Collections.IEnumerable> 및 <xref:System.Collections.Generic.IEnumerable%601>을 구현하므로 C#의 모든 배열에서 [foreach](../../language-reference/keywords/foreach-in.md) 반복을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a3e8-119">Since this type implements <xref:System.Collections.IEnumerable> and <xref:System.Collections.Generic.IEnumerable%601>, you can use [foreach](../../language-reference/keywords/foreach-in.md) iteration on all arrays in C#.</span></span>

## <a name="related-sections"></a><span data-ttu-id="4a3e8-120">관련 단원</span><span class="sxs-lookup"><span data-stu-id="4a3e8-120">Related sections</span></span>

- [<span data-ttu-id="4a3e8-121">개체로 사용되는 배열</span><span class="sxs-lookup"><span data-stu-id="4a3e8-121">Arrays as Objects</span></span>](arrays-as-objects.md)
- [<span data-ttu-id="4a3e8-122">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="4a3e8-122">Using foreach with Arrays</span></span>](using-foreach-with-arrays.md)
- [<span data-ttu-id="4a3e8-123">인수로 배열 전달</span><span class="sxs-lookup"><span data-stu-id="4a3e8-123">Passing Arrays as Arguments</span></span>](passing-arrays-as-arguments.md)

## <a name="c-language-specification"></a><span data-ttu-id="4a3e8-124">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4a3e8-124">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="4a3e8-125">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a3e8-125">See also</span></span>

- [<span data-ttu-id="4a3e8-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4a3e8-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="4a3e8-127">컬렉션</span><span class="sxs-lookup"><span data-stu-id="4a3e8-127">Collections</span></span>](../concepts/collections.md)
