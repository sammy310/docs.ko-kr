---
description: orderby 절 - C# 참조
title: orderby 절 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- orderby
- orderby_CSharpKeyword
helpviewer_keywords:
- orderby clause [C#]
- orderby keyword [C#]
ms.assetid: 21f87f48-d69d-4e95-9a52-6fec47b37e1f
ms.openlocfilehash: 2f64b45ff252c7cc02e56c465da21ccc5e861aec
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142351"
---
# <a name="orderby-clause-c-reference"></a><span data-ttu-id="f6b89-103">orderby 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f6b89-103">orderby clause (C# Reference)</span></span>

<span data-ttu-id="f6b89-104">쿼리 식에서 `orderby` 절은 반환된 시퀀스 또는 하위 시퀀스(그룹)가 오름차순이나 내림차순으로 정렬되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-104">In a query expression, the `orderby` clause causes the returned sequence or subsequence (group) to be sorted in either ascending or descending order.</span></span> <span data-ttu-id="f6b89-105">하나 이상의 보조 정렬 작업을 수행하기 위해 여러 키를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-105">Multiple keys can be specified in order to perform one or more secondary sort operations.</span></span> <span data-ttu-id="f6b89-106">정렬은 요소 형식에 대한 기본 비교자에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-106">The sorting is performed by the default comparer for the type of the element.</span></span> <span data-ttu-id="f6b89-107">기본 정렬 순서는 오름차순입니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-107">The default sort order is ascending.</span></span> <span data-ttu-id="f6b89-108">사용자 지정 비교자를 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-108">You can also specify a custom comparer.</span></span> <span data-ttu-id="f6b89-109">그러나 메서드 기반 구문을 통해서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-109">However, it is only available by using method-based syntax.</span></span> <span data-ttu-id="f6b89-110">자세한 내용은 [데이터 정렬](../../programming-guide/concepts/linq/sorting-data.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f6b89-110">For more information, see [Sorting Data](../../programming-guide/concepts/linq/sorting-data.md).</span></span>

## <a name="example"></a><span data-ttu-id="f6b89-111">예제</span><span class="sxs-lookup"><span data-stu-id="f6b89-111">Example</span></span>

<span data-ttu-id="f6b89-112">다음 예제에서 첫 번째 쿼리는 A부터 시작하여 사전순으로 단어를 정렬하고, 두 번째 쿼리는 동일한 단어를 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-112">In the following example, the first query sorts the words in alphabetical order starting from A, and second query sorts the same words in descending order.</span></span> <span data-ttu-id="f6b89-113">`ascending` 키워드는 기본 정렬 값이며 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-113">(The `ascending` keyword is the default sort value and can be omitted.)</span></span>

[!code-csharp[cscsrefQueryKeywords#20](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#20)]

## <a name="example"></a><span data-ttu-id="f6b89-114">예제</span><span class="sxs-lookup"><span data-stu-id="f6b89-114">Example</span></span>

<span data-ttu-id="f6b89-115">다음 예제에서는 학생의 성을 기준으로 1차 정렬을 수행한 다음 이름을 기준으로 2차 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-115">The following example performs a primary sort on the students' last names, and then a secondary sort on their first names.</span></span>

[!code-csharp[cscsrefQueryKeywords#22](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Orderby.cs#22)]

## <a name="remarks"></a><span data-ttu-id="f6b89-116">설명</span><span class="sxs-lookup"><span data-stu-id="f6b89-116">Remarks</span></span>

<span data-ttu-id="f6b89-117">컴파일 시간에 `orderby` 절은 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-117">At compile time, the `orderby` clause is translated to a call to the <xref:System.Linq.Enumerable.OrderBy%2A> method.</span></span> <span data-ttu-id="f6b89-118">`orderby` 절의 여러 키는 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f6b89-118">Multiple keys in the `orderby` clause translate to <xref:System.Linq.Enumerable.ThenBy%2A> method calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="f6b89-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f6b89-119">See also</span></span>

- [<span data-ttu-id="f6b89-120">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f6b89-120">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f6b89-121">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="f6b89-121">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="f6b89-122">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="f6b89-122">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="f6b89-123">group 절</span><span class="sxs-lookup"><span data-stu-id="f6b89-123">group clause</span></span>](group-clause.md)
- [<span data-ttu-id="f6b89-124">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="f6b89-124">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
