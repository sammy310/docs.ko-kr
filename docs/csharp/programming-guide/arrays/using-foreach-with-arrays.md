---
title: 배열에 foreach 사용 - C# 프로그래밍 가이드
ms.date: 05/23/2018
helpviewer_keywords:
- arrays [C#], foreach
- foreach statement [C#], using with arrays
ms.assetid: 5f2da2a9-1f56-4de5-94cc-e07f4f7a0244
ms.openlocfilehash: bb121b0f5d990ef6e596b34a45606e2abde6811a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75705680"
---
# <a name="using-foreach-with-arrays-c-programming-guide"></a><span data-ttu-id="1b508-102">배열에 foreach 사용(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="1b508-102">Using foreach with arrays (C# Programming Guide)</span></span>

<span data-ttu-id="1b508-103">[foreach](../../language-reference/keywords/foreach-in.md) 문은 배열의 요소를 반복하는 단순하고 깔끔한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="1b508-103">The [foreach](../../language-reference/keywords/foreach-in.md) statement provides a simple, clean way to iterate through the elements of an array.</span></span>

<span data-ttu-id="1b508-104">1차원 배열의 경우 `foreach` 문은 인덱스 0으로 시작하고 인덱스 `Length - 1`로 끝나는 늘어나는 인덱스 순서로 요소를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1b508-104">For single-dimensional arrays, the `foreach` statement processes elements in increasing index order, starting with index 0 and ending with index `Length - 1`:</span></span>

 [!code-csharp[csProgGuideArrays#28](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#28)]

<span data-ttu-id="1b508-105">다차원 배열의 경우 요소는 가장 오른쪽 차원의 인덱스가 먼저 증가한 이후, 다음 왼쪽 차원의 인덱스, 그다음 왼쪽 차원의 인덱스가 증가하는 방식으로 트래버스됩니다.</span><span class="sxs-lookup"><span data-stu-id="1b508-105">For multi-dimensional arrays, elements are traversed such that the indices of the rightmost dimension are increased first, then the next left dimension, and so on to the left:</span></span>

 [!code-csharp[csProgGuideArrays#29](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideArrays/CS/Arrays.cs#29)]

<span data-ttu-id="1b508-106">그러나 다차원 배열에서 중첩 [for](../../language-reference/keywords/for.md) 루프를 사용하면 배열 요소를 처리하는 순서를 더 강력하게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1b508-106">However, with multidimensional arrays, using a nested [for](../../language-reference/keywords/for.md) loop gives you more control over the order in which to process the array elements.</span></span>

## <a name="see-also"></a><span data-ttu-id="1b508-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1b508-107">See also</span></span>

- <xref:System.Array>
- [<span data-ttu-id="1b508-108">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1b508-108">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="1b508-109">배열</span><span class="sxs-lookup"><span data-stu-id="1b508-109">Arrays</span></span>](index.md)
- [<span data-ttu-id="1b508-110">1차원 배열</span><span class="sxs-lookup"><span data-stu-id="1b508-110">Single-Dimensional Arrays</span></span>](single-dimensional-arrays.md)
- [<span data-ttu-id="1b508-111">다차원 배열</span><span class="sxs-lookup"><span data-stu-id="1b508-111">Multidimensional Arrays</span></span>](multidimensional-arrays.md)
- [<span data-ttu-id="1b508-112">가변 배열</span><span class="sxs-lookup"><span data-stu-id="1b508-112">Jagged Arrays</span></span>](jagged-arrays.md)
