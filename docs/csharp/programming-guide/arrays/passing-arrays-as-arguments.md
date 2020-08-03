---
title: 배열을 인수로 전달 - C# 프로그래밍 가이드
description: C#의 배열을 메서드 매개 변수에 인수로 전달할 수 있습니다. 배열은 참조 형식이므로 메서드를 통해 요소 값을 변경할 수 있습니다.
ms.date: 07/05/2018
helpviewer_keywords:
- arrays [C#], passing as arguments
ms.assetid: f3a0971e-c87c-4a1f-8262-bc0a3b712772
ms.openlocfilehash: 68f174421e56e2cf082fe670f93c4f6627d7c17b
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474633"
---
# <a name="passing-arrays-as-arguments-c-programming-guide"></a><span data-ttu-id="04588-104">배열을 인수로 전달(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="04588-104">Passing arrays as arguments (C# Programming Guide)</span></span>

<span data-ttu-id="04588-105">배열을 메서드 매개 변수에 인수로 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04588-105">Arrays can be passed as arguments to method parameters.</span></span> <span data-ttu-id="04588-106">배열은 참조 형식이므로 메서드를 통해 요소 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04588-106">Because arrays are reference types, the method can change the value of the elements.</span></span>

## <a name="passing-single-dimensional-arrays-as-arguments"></a><span data-ttu-id="04588-107">1차원 배열을 인수로 전달</span><span class="sxs-lookup"><span data-stu-id="04588-107">Passing single-dimensional arrays as arguments</span></span>

<span data-ttu-id="04588-108">초기화된 1차원 배열을 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04588-108">You can pass an initialized single-dimensional array to a method.</span></span> <span data-ttu-id="04588-109">예를 들어 다음 문은 인쇄 메서드에 배열을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="04588-109">For example, the following statement sends an array to a print method.</span></span>

[!code-csharp[csProgGuideArrays#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#34)]

<span data-ttu-id="04588-110">다음 코드는 인쇄 메서드의 부분 구현을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04588-110">The following code shows a partial implementation of the print method.</span></span>

[!code-csharp[csProgGuideArrays#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#33)]

<span data-ttu-id="04588-111">다음 예제와 같이 한 단계로 새 배열을 초기화하고 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04588-111">You can initialize and pass a new array in one step, as is shown in the following example.</span></span>

[!code-csharp[CsProgGuideArrays#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#35)]

### <a name="example"></a><span data-ttu-id="04588-112">예제</span><span class="sxs-lookup"><span data-stu-id="04588-112">Example</span></span>

<span data-ttu-id="04588-113">다음 예제에서는 문자열 배열이 초기화되고 문자열에 대한 `DisplayArray` 메서드에 인수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="04588-113">In the following example, an array of strings is initialized and passed as an argument to a `DisplayArray` method for strings.</span></span> <span data-ttu-id="04588-114">메서드가 배열 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="04588-114">The method displays the elements of the array.</span></span> <span data-ttu-id="04588-115">다음으로 `ChangeArray` 메서드는 배열 요소를 반대로 전환한 다음, `ChangeArrayElements` 메서드는 배열의 처음 세 요소를 수정합니다.</span><span class="sxs-lookup"><span data-stu-id="04588-115">Next, the `ChangeArray` method reverses the array elements, and then the `ChangeArrayElements` method modifies the first three elements of the array.</span></span> <span data-ttu-id="04588-116">각 메서드가 반환된 후 `DisplayArray` 메서드는 배열을 값으로 전달해도 배열 요소가 변경되지 않는다는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="04588-116">After each method returns, the `DisplayArray` method shows that passing an array by value doesn't prevent changes to the array elements.</span></span>

[!code-csharp[csProgGuideArrays#30](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/ArrayExample.cs)]

## <a name="passing-multidimensional-arrays-as-arguments"></a><span data-ttu-id="04588-117">다차원 배열을 인수로 전달</span><span class="sxs-lookup"><span data-stu-id="04588-117">Passing multidimensional arrays as arguments</span></span>

<span data-ttu-id="04588-118">초기화된 다차원 배열을 1차원 배열 전달과 동일한 방식으로 메서드에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="04588-118">You pass an initialized multidimensional array to a method in the same way that you pass a one-dimensional array.</span></span>

[!code-csharp[csProgGuideArrays#41](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#41)]

<span data-ttu-id="04588-119">다음 코드는 2차원 배열을 해당 인수로 허용하는 인쇄 메서드의 부분 선언을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="04588-119">The following code shows a partial declaration of a print method that accepts a two-dimensional array as its argument.</span></span>

[!code-csharp[csProgGuideArrays#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#36)]

<span data-ttu-id="04588-120">다음 예제와 같이 한 단계로 새 배열을 초기화하고 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="04588-120">You can initialize and pass a new array in one step, as is shown in the following example:</span></span>

[!code-csharp[csProgGuideArrays#32](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#32)]

### <a name="example"></a><span data-ttu-id="04588-121">예제</span><span class="sxs-lookup"><span data-stu-id="04588-121">Example</span></span>

<span data-ttu-id="04588-122">다음 예제에서는 정수의 2차원 배열이 초기화되고 `Print2DArray` 메서드에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="04588-122">In the following example, a two-dimensional array of integers is initialized and passed to the `Print2DArray` method.</span></span> <span data-ttu-id="04588-123">메서드가 배열 요소를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="04588-123">The method displays the elements of the array.</span></span>

[!code-csharp[csProgGuideArrays#31](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#31)]

## <a name="see-also"></a><span data-ttu-id="04588-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="04588-124">See also</span></span>

- [<span data-ttu-id="04588-125">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="04588-125">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="04588-126">배열</span><span class="sxs-lookup"><span data-stu-id="04588-126">Arrays</span></span>](index.md)
- [<span data-ttu-id="04588-127">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="04588-127">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="04588-128">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="04588-128">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="04588-129">가변 배열</span><span class="sxs-lookup"><span data-stu-id="04588-129">Jagged Arrays</span></span>](jagged-arrays.md)
