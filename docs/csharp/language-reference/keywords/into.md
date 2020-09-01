---
description: into - C# 참조
title: into - C# 참조
ms.date: 07/20/2015
f1_keywords:
- into_CSharpKeyword
- into
helpviewer_keywords:
- into keyword [C#]
ms.assetid: 81ec62c1-f0b1-4755-8a31-959876e77f65
ms.openlocfilehash: 4712a6906195c5d8bc09c7b734dba0df4d2b08c8
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134525"
---
# <a name="into-c-reference"></a><span data-ttu-id="5e672-103">into(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="5e672-103">into (C# Reference)</span></span>

<span data-ttu-id="5e672-104">`into` 상황별 키워드를 사용하여 [group](group-clause.md), [join](join-clause.md), [select](select-clause.md) 절의 결과를 새 식별자에 저장하기 위한 임시 식별자를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e672-104">The `into` contextual keyword can be used to create a temporary identifier to store the results of a [group](group-clause.md), [join](join-clause.md) or [select](select-clause.md) clause into a new identifier.</span></span> <span data-ttu-id="5e672-105">이 식별자 자체는 추가 쿼리 명령의 생성기일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e672-105">This identifier can itself be a generator for additional query commands.</span></span> <span data-ttu-id="5e672-106">`group` 또는 `select` 절에 사용할 경우 새 식별자의 사용을 *연속*이라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="5e672-106">When used in a `group` or `select` clause, the use of the new identifier is sometimes referred to as a *continuation*.</span></span>

## <a name="example"></a><span data-ttu-id="5e672-107">예제</span><span class="sxs-lookup"><span data-stu-id="5e672-107">Example</span></span>

<span data-ttu-id="5e672-108">다음 예제에서는 `into` 키워드를 사용하여 임시 식별자 `fruitGroup`을 활성화하는 방법을 보여 줍니다. 이 식별자는 `IGrouping`의 유추된 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="5e672-108">The following example shows the use of the `into` keyword to enable a temporary identifier `fruitGroup` which has an inferred type of `IGrouping`.</span></span> <span data-ttu-id="5e672-109">식별자를 사용하여 각 그룹에서 <xref:System.Linq.Enumerable.Count%2A> 메서드를 호출하고 둘 이상의 단어를 포함하는 그룹만 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5e672-109">By using the identifier, you can invoke the <xref:System.Linq.Enumerable.Count%2A> method on each group and select only those groups that contain two or more words.</span></span>

[!code-csharp[cscsrefQueryKeywords#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Into.cs#18)]

<span data-ttu-id="5e672-110">각 그룹에서 추가 쿼리 작업을 수행하려는 경우에만 `group` 절에 `into`를 사용하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5e672-110">The use of `into` in a `group` clause is only necessary when you want to perform additional query operations on each group.</span></span> <span data-ttu-id="5e672-111">자세한 내용은 [group 절](group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e672-111">For more information, see [group clause](group-clause.md).</span></span>

<span data-ttu-id="5e672-112">`join` 절에 `into`를 사용하는 방법의 예는 [join 절](join-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5e672-112">For an example of the use of `into` in a `join` clause, see [join clause](join-clause.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e672-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5e672-113">See also</span></span>

- [<span data-ttu-id="5e672-114">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="5e672-114">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="5e672-115">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="5e672-115">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="5e672-116">group 절</span><span class="sxs-lookup"><span data-stu-id="5e672-116">group clause</span></span>](group-clause.md)
