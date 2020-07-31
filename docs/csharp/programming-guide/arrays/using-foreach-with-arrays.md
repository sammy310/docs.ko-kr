---
title: 배열에 foreach 사용 - C# 프로그래밍 가이드
description: C#의 foreach 문은 배열의 요소 반복합니다. 1차원 배열의 경우 foreach는 늘어나는 인덱스 순서로 요소를 처리합니다.
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: d924a3ef3351cbb30b809a1542f35314ee721852
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474542"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="ce0d1-104">배열에 foreach 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="ce0d1-104">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="ce0d1-105">[foreach](../../language-reference/keywords/foreach-in.md) 문은 배열의 요소를 반복하는 단순하고 깔끔한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0d1-105">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="ce0d1-106">1차원 배열의 경우 `foreach` 문은 인덱스 0으로 시작하고 인덱스 `Length - 1`로 끝나는 늘어나는 인덱스 순서로 요소를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ce0d1-106">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="ce0d1-107">다차원 배열의 경우 요소는 가장 오른쪽 차원의 인덱스가 먼저 증가한 이후, 다음 왼쪽 차원의 인덱스, 그다음 왼쪽 차원의 인덱스가 증가하는 방식으로 트래버스됩니다.</span><span class="sxs-lookup"><span data-stu-id="ce0d1-107">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="ce0d1-108">그러나 다차원 배열에서 중첩 [for](../../language-reference/keywords/for.md) 루프를 사용하면 배열 요소를 처리하는 순서를 더 강력하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ce0d1-108">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="ce0d1-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce0d1-109">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="ce0d1-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ce0d1-110">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="ce0d1-111">배열</span><span class="sxs-lookup"><span data-stu-id="ce0d1-111">Arrays</span></span>](index.md)
- [<span data-ttu-id="ce0d1-112">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="ce0d1-112">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="ce0d1-113">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="ce0d1-113">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="ce0d1-114">가변 배열</span><span class="sxs-lookup"><span data-stu-id="ce0d1-114">Jagged Arrays</span></span>](jagged-arrays.md)
