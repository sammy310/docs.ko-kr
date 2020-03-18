---
title: 중첩 그룹 만들기(C#의 LINQ)
description: C#에서 LINQ 쿼리 식에서 중첩된 그룹을 만드는 방법에 대해 알아봅니다.
ms.date: 12/01/2016
ms.assetid: e9f00708-362e-4d13-98c5-d77549347ba0
ms.openlocfilehash: 7d056c9e215ccc7ca24d621b64e2328bed79f22e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "61688620"
---
# <a name="create-a-nested-group"></a><span data-ttu-id="c563d-103">중첩 그룹 만들기</span><span class="sxs-lookup"><span data-stu-id="c563d-103">Create a nested group</span></span>

<span data-ttu-id="c563d-104">다음 예제에서는 LINQ 쿼리 식에서 중첩 그룹을 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c563d-104">The following example shows how to create nested groups in a LINQ query expression.</span></span> <span data-ttu-id="c563d-105">학년 또는 성적 수준에 따라 만들어진 각 그룹은 개인의 이름에 따라 하위 그룹으로 추가로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="c563d-105">Each group that is created according to student year or grade level is then further subdivided into groups based on the individuals' names.</span></span>

## <a name="example"></a><span data-ttu-id="c563d-106">예제</span><span class="sxs-lookup"><span data-stu-id="c563d-106">Example</span></span>

> [!NOTE]
> <span data-ttu-id="c563d-107">이 예제에는 [개체의 컬렉션 쿼리](query-a-collection-of-objects.md)에서 샘플 코드에 정의된 개체에 대한 참조가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="c563d-107">This example contains references to objects that are defined in the sample code in [Query a collection of objects](query-a-collection-of-objects.md).</span></span>

[!code-csharp[csProgGuideLINQ#24](~/samples/snippets/csharp/concepts/linq/how-to-create-a-nested-group_1.cs)]

<span data-ttu-id="c563d-108">중첩 그룹의 내부 요소를 반복하려면 세 개의 중첩 `foreach` 루프가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c563d-108">Note that three nested `foreach` loops are required to iterate over the inner elements of a nested group.</span></span>

## <a name="see-also"></a><span data-ttu-id="c563d-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c563d-109">See also</span></span>

- [<span data-ttu-id="c563d-110">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="c563d-110">Language Integrated Query (LINQ)</span></span>](index.md)
