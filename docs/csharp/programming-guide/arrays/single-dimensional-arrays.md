---
title: 1차원 배열 - C# 프로그래밍 가이드
description: 배열 요소 형식과 요소 수를 지정하는 new 연산자를 사용하여 C#에서 1차원 배열을 만듭니다.
ms.date: 06/03/2020
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: ada01262d57cbfebc8bfa1a5fee0639a10db5a4b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474594"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="242d0-103">1차원 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="242d0-103">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="242d0-104">배열 요소 형식과 요소 수를 지정하는 [new](../../language-reference/operators/new-operator.md) 연산자를 사용하여 1차원 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-104">You create a single-dimensional array using the [new](../../language-reference/operators/new-operator.md) operator specifying the array element type and the number of elements.</span></span> <span data-ttu-id="242d0-105">다음 예제에서는 정수가 5개인 배열을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-105">The following example declares an array of five integers:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntDeclaration":::

<span data-ttu-id="242d0-106">이 배열에는 `array[0]` ~ `array[4]`의 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-106">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="242d0-107">배열의 요소는 기본값, 즉 정수에 대해 요소 형식 `0`으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-107">The elements of the array are initialized to the default value of the element type, `0` for integers.</span></span>

<span data-ttu-id="242d0-108">문자열 배열을 선언하는 다음 예제와 같이, 배열은 지정되는 모든 요소 형식을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-108">Arrays can store any element type you specify, such as the following example that declares an array of strings:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringDeclaration":::

## <a name="array-initialization"></a><span data-ttu-id="242d0-109">배열 초기화</span><span class="sxs-lookup"><span data-stu-id="242d0-109">Array Initialization</span></span>

<span data-ttu-id="242d0-110">배열을 선언할 때 배열의 요소를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-110">You can initialize the elements of an array when you declare the array.</span></span> <span data-ttu-id="242d0-111">길이 지정자는 초기화 목록의 요소 수에 따라 유추되므로 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-111">The length specifier isn't needed because it's inferred by the number of elements in the initialization list.</span></span> <span data-ttu-id="242d0-112">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="242d0-112">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="IntInitialization":::

<span data-ttu-id="242d0-113">다음 코드는 각 배열 요소가 요일 이름으로 초기화되는 문자열 배열의 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-113">The following code shows a declaration of a string array where each array element is initialized by a name of a day:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="StringInitialization":::
  
<span data-ttu-id="242d0-114">다음 코드와 같이 선언 시 배열을 초기화할 때 `new` 식과 배열 형식을 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-114">You can avoid the `new` expression and the array type when you initialize an array upon declaration, as shown in the following code.</span></span> <span data-ttu-id="242d0-115">이를 [암시적으로 형식화된 배열](implicitly-typed-arrays.md)이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-115">This is called an [implicitly typed array](implicitly-typed-arrays.md):</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="ShorthandInitialization":::

<span data-ttu-id="242d0-116">배열 변수를 만들지 않고 선언할 수 있지만 이 변수에 새 배열을 할당할 때는 `new` 연산자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-116">You can declare an array variable without creating it, but you must use the `new` operator when you assign a new array to this variable.</span></span> <span data-ttu-id="242d0-117">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="242d0-117">For example:</span></span>

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="DeclareAllocate":::

## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="242d0-118">값 형식 및 참조 형식 배열</span><span class="sxs-lookup"><span data-stu-id="242d0-118">Value Type and Reference Type Arrays</span></span>

<span data-ttu-id="242d0-119">다음 배열 선언을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="242d0-119">Consider the following array declaration:</span></span>  

:::code language="csharp" source="snippets/SingleDimensionArrays.cs" id="FinalInstantiation":::

<span data-ttu-id="242d0-120">이 문의 결과는 `SomeType`이 값 형식인지 또는 참조 형식인지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-120">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="242d0-121">값 형식인 경우 이 문은 각각 `SomeType` 형식인 10개 요소의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-121">If it's a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="242d0-122">`SomeType`이 참조 형식인 경우 이 문은 각각 null 참조로 초기화된 10개 요소의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-122">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span> <span data-ttu-id="242d0-123">두 인스턴스 모두에서 요소가 요소 형식에 대한 기본값으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="242d0-123">In both instances, the elements are initialized to the default value for the element type.</span></span> <span data-ttu-id="242d0-124">값 형식과 참조 형식에 대한 자세한 내용은 [값 형식](../../language-reference/builtin-types/value-types.md) 및 [참조 형식](../../language-reference/keywords/reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="242d0-124">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="242d0-125">참조</span><span class="sxs-lookup"><span data-stu-id="242d0-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="242d0-126">배열</span><span class="sxs-lookup"><span data-stu-id="242d0-126">Arrays</span></span>](./index.md)
- [<span data-ttu-id="242d0-127">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="242d0-127">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="242d0-128">가변 배열</span><span class="sxs-lookup"><span data-stu-id="242d0-128">Jagged Arrays</span></span>](./jagged-arrays.md)
