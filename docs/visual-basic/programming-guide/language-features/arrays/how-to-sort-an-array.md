---
title: '방법: Visual Basic 배열 정렬'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 467d1bcce6bda2feb5a8e59c152cb292d753e79b
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2019
ms.locfileid: "71700971"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="7c5a6-102">방법: Visual Basic 배열 정렬</span><span class="sxs-lookup"><span data-stu-id="7c5a6-102">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="7c5a6-103">이 문서에서는 Visual Basic에서 문자열 배열을 정렬 하는 방법의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-103">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="7c5a6-104">예제</span><span class="sxs-lookup"><span data-stu-id="7c5a6-104">Example</span></span>

<span data-ttu-id="7c5a6-105">이 예제에서는 `zooAnimals` 이라는 `String` 개체의 배열을 선언 하 여 채운 다음 사전순으로 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="7c5a6-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="7c5a6-106">Robust programming</span></span>

<span data-ttu-id="7c5a6-107">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-107">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="7c5a6-108">배열이 비어 있습니다 (<xref:System.ArgumentNullException> 클래스).</span><span class="sxs-lookup"><span data-stu-id="7c5a6-108">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="7c5a6-109">배열이 다차원 (<xref:System.RankException> 클래스) 인 경우</span><span class="sxs-lookup"><span data-stu-id="7c5a6-109">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="7c5a6-110">배열의 하나 이상의 요소가 <xref:System.IComparable> 인터페이스 (<xref:System.InvalidOperationException> 클래스)를 구현 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7c5a6-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="7c5a6-111">참조</span><span class="sxs-lookup"><span data-stu-id="7c5a6-111">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="7c5a6-112">배열</span><span class="sxs-lookup"><span data-stu-id="7c5a6-112">Arrays</span></span>](index.md)
- [<span data-ttu-id="7c5a6-113">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7c5a6-113">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="7c5a6-114">컬렉션</span><span class="sxs-lookup"><span data-stu-id="7c5a6-114">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="7c5a6-115">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="7c5a6-115">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
