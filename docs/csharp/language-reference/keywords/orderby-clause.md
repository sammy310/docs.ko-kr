---
title: orderby 절 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 09a745fe3da3a5acb71972b9cf56391774c7016a
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422647"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="dab68-102">orderby 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dab68-102">orderby clause (C# Reference)</span></span>

<span data-ttu-id="dab68-103">쿼리 식에서 `orderby` 절은 반환된 시퀀스 또는 하위 시퀀스(그룹)가 오름차순이나 내림차순으로 정렬되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-103">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="dab68-104">하나 이상의 보조 정렬 작업을 수행하기 위해 여러 키를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-104">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="dab68-105">정렬은 요소 형식에 대한 기본 비교자에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-105">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="dab68-106">기본 정렬 순서는 오름차순입니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-106">The default sort order is ascending.</span></span> <span data-ttu-id="dab68-107">사용자 지정 비교자를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-107">You can also specify a custom comparer.</span></span> <span data-ttu-id="dab68-108">그러나 메서드 기반 구문을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-108">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="dab68-109">자세한 내용은 [데이터 정렬](../../programming-guide/concepts/linq/sorting-data.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dab68-109">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="dab68-110">예</span><span class="sxs-lookup"><span data-stu-id="dab68-110">Example</span></span>

<span data-ttu-id="dab68-111">다음 예제에서 첫 번째 쿼리는 A부터 시작하여 사전순으로 단어를 정렬하고, 두 번째 쿼리는 동일한 단어를 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-111">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="dab68-112">`ascending` 키워드는 기본 정렬 값이며 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-112">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="dab68-113">예</span><span class="sxs-lookup"><span data-stu-id="dab68-113">Example</span></span>

<span data-ttu-id="dab68-114">다음 예제에서는 학생의 성을 기준으로 1차 정렬을 수행한 다음 이름을 기준으로 2차 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-114">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="dab68-115">설명</span><span class="sxs-lookup"><span data-stu-id="dab68-115">Remarks</span></span>

<span data-ttu-id="dab68-116">컴파일 시간에 `orderby` 절은 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-116">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="dab68-117">`orderby` 절의 여러 키는 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="dab68-117">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="dab68-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dab68-118">See also</span></span>

- [<span data-ttu-id="dab68-119">C# 참조</span><span class="sxs-lookup"><span data-stu-id="dab68-119">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dab68-120">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="dab68-120">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="dab68-121">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="dab68-121">Language Integrated Query (LINQ)</span></span>](../../linq/index.md)
- [<span data-ttu-id="dab68-122">group 절</span><span class="sxs-lookup"><span data-stu-id="dab68-122">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="dab68-123">C#에서 LINQ 시작</span><span class="sxs-lookup"><span data-stu-id="dab68-123">Getting Started with LINQ in C#</span></span>](/dotnet/csharp/programming-guide/concepts/linq/)
