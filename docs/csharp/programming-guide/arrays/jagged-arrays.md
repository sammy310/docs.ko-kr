---
title: 가변 배열 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- jagged arrays [C#]
- arrays [C#], jagged
ms.assetid: 537c65a6-0e0a-4a00-a2b8-086f38519c70
ms.openlocfilehash: 56013f0143d5efcb31a476909cb6e92504ff0dbc
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75705706"
---
# <a name="jagged-arrays-c-programming-guide"></a><span data-ttu-id="98529-102">가변 배열(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="98529-102">Jagged Arrays (C# Programming Guide)</span></span>

<span data-ttu-id="98529-103">가변 배열의 요소에는 배열이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="98529-103">A jagged array is an array whose elements are arrays.</span></span> <span data-ttu-id="98529-104">가변 배열의 요소는 차원과 크기가 서로 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98529-104">The elements of a jagged array can be of different dimensions and sizes.</span></span> <span data-ttu-id="98529-105">가변 배열을 “배열의 배열”이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="98529-105">A jagged array is sometimes called an "array of arrays."</span></span> <span data-ttu-id="98529-106">다음 예제에서는 가변 배열을 선언, 초기화 및 액세스하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98529-106">The following examples show how to declare, initialize, and access jagged arrays.</span></span>  
  
 <span data-ttu-id="98529-107">다음은 각각 정수의 1차원 배열인 세 개의 요소를 포함하는 1차원 배열의 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="98529-107">The following is a declaration of a single-dimensional array that has three elements, each of which is a single-dimensional array of integers:</span></span>  
  
 [!code-csharp[csProgGuideArrays#19](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#19)]  
  
 <span data-ttu-id="98529-108">`jaggedArray`를 사용하려면 먼저 해당 요소를 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98529-108">Before you can use `jaggedArray`, its elements must be initialized.</span></span> <span data-ttu-id="98529-109">다음과 같이 요소를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98529-109">You can initialize the elements like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#20)]  
  
 <span data-ttu-id="98529-110">각 요소는 정수의 1차원 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="98529-110">Each of the elements is a single-dimensional array of integers.</span></span> <span data-ttu-id="98529-111">첫 번째 요소는 5개 정수의 배열이고, 두 번째 요소는 4개 정수의 배열이고, 세 번째 요소는 2개 정수의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="98529-111">The first element is an array of 5 integers, the second is an array of 4 integers, and the third is an array of 2 integers.</span></span>  
  
 <span data-ttu-id="98529-112">이니셜라이저를 사용하여 배열 요소에 값을 채울 수도 있으며, 이 경우 배열 크기가 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98529-112">It is also possible to use initializers to fill the array elements with values, in which case you do not need the array size.</span></span> <span data-ttu-id="98529-113">예:</span><span class="sxs-lookup"><span data-stu-id="98529-113">For example:</span></span>  
  
 [!code-csharp[csProgGuideArrays#21](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#21)]  
  
 <span data-ttu-id="98529-114">다음과 같이 선언 시 배열을 초기화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98529-114">You can also initialize the array upon declaration like this:</span></span>  
  
 [!code-csharp[csProgGuideArrays#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#22)]  
  
 <span data-ttu-id="98529-115">다음과 같은 약식 형태를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98529-115">You can use the following shorthand form.</span></span> <span data-ttu-id="98529-116">요소에 대한 기본 초기화가 없으므로 요소 초기화에서 `new` 연산자를 생략할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98529-116">Notice that you cannot omit the `new` operator from the elements initialization because there is no default initialization for the elements:</span></span>  
  
 [!code-csharp[csProgGuideArrays#23](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#23)]  
  
 <span data-ttu-id="98529-117">가변 배열은 여러 배열로 구성되어 있기 때문에 해당 요소가 참조 형식이며, `null`로 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="98529-117">A jagged array is an array of arrays, and therefore its elements are reference types and are initialized to `null`.</span></span>  
  
 <span data-ttu-id="98529-118">다음 예제처럼 개별 배열 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98529-118">You can access individual array elements like these examples:</span></span>  
  
 [!code-csharp[csProgGuideArrays#24](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#24)]  
  
 <span data-ttu-id="98529-119">가변 배열과 다차원 배열을 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98529-119">It is possible to mix jagged and multidimensional arrays.</span></span> <span data-ttu-id="98529-120">다음은 서로 다른 크기의 세 가지 2차원 배열 요소를 포함하는 1차원 가변 배열의 선언과 초기화입니다.</span><span class="sxs-lookup"><span data-stu-id="98529-120">The following is a declaration and initialization of a single-dimensional jagged array that contains three two-dimensional array elements of different sizes.</span></span> <span data-ttu-id="98529-121">2차원 배열에 대한 자세한 내용은 [다차원 배열](./multidimensional-arrays.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98529-121">For more information about two-dimensional arrays, see [Multidimensional Arrays](./multidimensional-arrays.md).</span></span>  
  
 [!code-csharp[csProgGuideArrays#25](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#25)]  
  
 <span data-ttu-id="98529-122">이 예제와 같이, 첫 번째 배열의 `[1,0]` 요소 값(값 `5`)을 표시하는 개별 요소에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98529-122">You can access individual elements as shown in this example, which displays the value of the element `[1,0]` of the first array (value `5`):</span></span>  
  
 [!code-csharp[csProgGuideArrays#26](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#26)]  
  
 <span data-ttu-id="98529-123">`Length` 메서드는 가변 배열에 포함된 배열 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="98529-123">The method `Length` returns the number of arrays contained in the jagged array.</span></span> <span data-ttu-id="98529-124">예를 들어 이전 배열을 선언했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="98529-124">For example, assuming you have declared the previous array, this line:</span></span>  
  
 [!code-csharp[csProgGuideArrays#27](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#27)]  
  
 <span data-ttu-id="98529-125">이 경우 위 줄은 값 3을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="98529-125">returns a value of 3.</span></span>  
  
## <a name="example"></a><span data-ttu-id="98529-126">예제</span><span class="sxs-lookup"><span data-stu-id="98529-126">Example</span></span>

 <span data-ttu-id="98529-127">이 예제에서는 요소 자체가 배열인 배열을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="98529-127">This example builds an array whose elements are themselves arrays.</span></span> <span data-ttu-id="98529-128">각 배열 요소의 크기가 서로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="98529-128">Each one of the array elements has a different size.</span></span>  
  
 [!code-csharp[csProgGuideArrays#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#18)]  
  
## <a name="see-also"></a><span data-ttu-id="98529-129">참조</span><span class="sxs-lookup"><span data-stu-id="98529-129">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="98529-130">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="98529-130">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="98529-131">배열</span><span class="sxs-lookup"><span data-stu-id="98529-131">Arrays</span></span>](./index.md)
- [<span data-ttu-id="98529-132">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="98529-132">Single-Dimensional Arrays</span></span>](./single-dimensional-arrays.md)
- [<span data-ttu-id="98529-133">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="98529-133">Multidimensional Arrays</span></span>](./multidimensional-arrays.md)
