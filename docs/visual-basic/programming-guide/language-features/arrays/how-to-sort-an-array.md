---
title: 'How to: Sort An Array'
ms.date: 07/20/2015
f1_keywords:
- Array.Sort
helpviewer_keywords:
- arrays [Visual Basic], sorting
- examples [Visual Basic], arrays
ms.assetid: 9289aeaa-9626-4698-94a7-1d1fd3702b87
ms.openlocfilehash: 3fb9af8de0fc86075fdccd64506c855c1c720660
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74351847"
---
# <a name="how-to-sort-an-array-in-visual-basic"></a><span data-ttu-id="18b25-102">How to: sort an array in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="18b25-102">How to: sort an array in Visual Basic</span></span>

<span data-ttu-id="18b25-103">This article shows an example of how to sort an array of strings in Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="18b25-103">This article shows an example of how to sort an array of strings in Visual Basic.</span></span>

## <a name="example"></a><span data-ttu-id="18b25-104">예제</span><span class="sxs-lookup"><span data-stu-id="18b25-104">Example</span></span>

<span data-ttu-id="18b25-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span><span class="sxs-lookup"><span data-stu-id="18b25-105">This example declares an array of `String` objects named `zooAnimals`, populates it, and then sorts it alphabetically:</span></span>
  
```vb
Private Sub SortAnimals()
    Dim zooAnimals(2) As String
    zooAnimals(0) = "lion"
    zooAnimals(1) = "turtle"
    zooAnimals(2) = "ostrich"
    Array.Sort(zooAnimals)
End Sub
```

## <a name="robust-programming"></a><span data-ttu-id="18b25-106">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="18b25-106">Robust programming</span></span>

<span data-ttu-id="18b25-107">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="18b25-107">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="18b25-108">Array is empty (<xref:System.ArgumentNullException> class).</span><span class="sxs-lookup"><span data-stu-id="18b25-108">Array is empty (<xref:System.ArgumentNullException> class).</span></span>
- <span data-ttu-id="18b25-109">Array is multidimensional (<xref:System.RankException> class).</span><span class="sxs-lookup"><span data-stu-id="18b25-109">Array is multidimensional (<xref:System.RankException> class).</span></span>
- <span data-ttu-id="18b25-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span><span class="sxs-lookup"><span data-stu-id="18b25-110">One or more elements of the array don't implement the <xref:System.IComparable> interface (<xref:System.InvalidOperationException> class).</span></span>

## <a name="see-also"></a><span data-ttu-id="18b25-111">참조</span><span class="sxs-lookup"><span data-stu-id="18b25-111">See also</span></span>

- <xref:System.Array.Sort%2A?displayProperty=nameWithType>
- [<span data-ttu-id="18b25-112">배열</span><span class="sxs-lookup"><span data-stu-id="18b25-112">Arrays</span></span>](index.md)
- [<span data-ttu-id="18b25-113">배열 문제 해결</span><span class="sxs-lookup"><span data-stu-id="18b25-113">Troubleshooting Arrays</span></span>](troubleshooting-arrays.md)
- [<span data-ttu-id="18b25-114">컬렉션</span><span class="sxs-lookup"><span data-stu-id="18b25-114">Collections</span></span>](../../concepts/collections.md)
- [<span data-ttu-id="18b25-115">For Each...Next 문</span><span class="sxs-lookup"><span data-stu-id="18b25-115">For Each...Next Statement</span></span>](../../../language-reference/statements/for-each-next-statement.md)
