---
title: 1차원 배열 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- single-dimensional arrays [C#]
- arrays [C#], single-dimensional
ms.assetid: 2cec1196-1de0-49d2-baf2-c607c33310e8
ms.openlocfilehash: 8f093d22da789c6df750475e47a3b4e4685c5651
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76744206"
---
# <a name="single-dimensional-arrays-c-programming-guide"></a><span data-ttu-id="ce39d-102">1차원 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ce39d-102">Single-Dimensional Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="ce39d-103">다음 예제와 같이 5개 정수의 1차원 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-103">You can declare a single-dimensional array of five integers as shown in the following example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#4)]  
  
 <span data-ttu-id="ce39d-104">이 배열에는 `array[0]` ~ `array[4]`의 요소가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-104">This array contains the elements from `array[0]` to `array[4]`.</span></span> <span data-ttu-id="ce39d-105">[new](../../language-reference/operators/new-operator.md) 연산자는 배열을 만들고 배열 요소를 기본값으로 초기화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-105">The [new](../../language-reference/operators/new-operator.md) operator is used to create the array and initialize the array elements to their default values.</span></span> <span data-ttu-id="ce39d-106">이 예제에서는 모든 배열 요소가 0으로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-106">In this example, all the array elements are initialized to zero.</span></span>  
  
 <span data-ttu-id="ce39d-107">동일한 방식으로 문자열 요소를 저장하는 배열을 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-107">An array that stores string elements can be declared in the same way.</span></span> <span data-ttu-id="ce39d-108">예:</span><span class="sxs-lookup"><span data-stu-id="ce39d-108">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#5)]  
  
## <a name="array-initialization"></a><span data-ttu-id="ce39d-109">배열 초기화</span><span class="sxs-lookup"><span data-stu-id="ce39d-109">Array Initialization</span></span>

 <span data-ttu-id="ce39d-110">선언 시 배열을 초기화할 수 있으며, 이 경우 길이 지정자가 초기화 목록에 있는 요소 수에 의해 제공되기 때문에 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-110">It is possible to initialize an array upon declaration, in which case, the length specifier is not needed because it is already supplied by the number of elements in the initialization list.</span></span> <span data-ttu-id="ce39d-111">예:</span><span class="sxs-lookup"><span data-stu-id="ce39d-111">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#6)]  
  
 <span data-ttu-id="ce39d-112">문자열 배열도 동일한 방식으로 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-112">A string array can be initialized in the same way.</span></span> <span data-ttu-id="ce39d-113">다음은 각 배열 요소가 하루의 이름으로 초기화되는 문자열 배열의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-113">The following is a declaration of a string array where each array element is initialized by a name of a day:</span></span>  
 
 ```csharp
 string[] weekDays = new string[] { "Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat" };
 ```
  
 <span data-ttu-id="ce39d-114">선언 시 배열을 초기화하면 다음 바로 가기를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-114">When you initialize an array upon declaration, you can use the following shortcuts:</span></span>  
  
 [!code-csharp[csProgGuideArrays#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#8)]  
  
 <span data-ttu-id="ce39d-115">초기화하지 않고 배열 변수를 선언할 수 있지만 이 변수에 배열을 할당할 때 `new` 연산자를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-115">It is possible to declare an array variable without initialization, but you must use the `new` operator when you assign an array to this variable.</span></span> <span data-ttu-id="ce39d-116">예:</span><span class="sxs-lookup"><span data-stu-id="ce39d-116">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#9)]  
  
 <span data-ttu-id="ce39d-117">C# 3.0에서는 암시적으로 형식화된 배열이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-117">C# 3.0 introduces implicitly typed arrays.</span></span> <span data-ttu-id="ce39d-118">자세한 내용은 [암시적으로 형식화된 배열](./implicitly-typed-arrays.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce39d-118">For more information, see [Implicitly Typed Arrays](./implicitly-typed-arrays.md).</span></span>  
  
## <a name="value-type-and-reference-type-arrays"></a><span data-ttu-id="ce39d-119">값 형식 및 참조 형식 배열</span><span class="sxs-lookup"><span data-stu-id="ce39d-119">Value Type and Reference Type Arrays</span></span>

 <span data-ttu-id="ce39d-120">다음 배열 선언을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="ce39d-120">Consider the following array declaration:</span></span>  
  
 [!code-csharp[csProgGuideArrays#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#10)]  
  
 <span data-ttu-id="ce39d-121">이 문의 결과는 `SomeType`이 값 형식인지 또는 참조 형식인지에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-121">The result of this statement depends on whether `SomeType` is a value type or a reference type.</span></span> <span data-ttu-id="ce39d-122">값 형식인 경우 이 문은 각각 `SomeType` 형식인 10개 요소의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-122">If it is a value type, the statement creates an array of 10 elements, each of which has the type `SomeType`.</span></span> <span data-ttu-id="ce39d-123">`SomeType`이 참조 형식인 경우 이 문은 각각 null 참조로 초기화된 10개 요소의 배열을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ce39d-123">If `SomeType` is a reference type, the statement creates an array of 10 elements, each of which is initialized to a null reference.</span></span>  
  
<span data-ttu-id="ce39d-124">값 형식과 참조 형식에 대한 자세한 내용은 [값 형식](../../language-reference/builtin-types/value-types.md) 및 [참조 형식](../../language-reference/keywords/reference-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce39d-124">For more information about value types and reference types, see [Value types](../../language-reference/builtin-types/value-types.md) and [Reference types](../../language-reference/keywords/reference-types.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ce39d-125">참조</span><span class="sxs-lookup"><span data-stu-id="ce39d-125">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="ce39d-126">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ce39d-126">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ce39d-127">배열</span><span class="sxs-lookup"><span data-stu-id="ce39d-127">Arrays</span></span>](./index.md)
- [<span data-ttu-id="ce39d-128">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="ce39d-128">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
- [<span data-ttu-id="ce39d-129">가변 배열</span><span class="sxs-lookup"><span data-stu-id="ce39d-129">Jagged Arrays</span></span>](./jagged-arrays.md)
