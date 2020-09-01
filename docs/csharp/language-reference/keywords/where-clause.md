---
description: where 절 - C# 참조
title: where 절 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- whereclause_CSharpKeyword
helpviewer_keywords:
- where keyword [C#]
- where clause [C#]
ms.assetid: 7f9bf952-7744-4f91-b676-cddb55d107c3
ms.openlocfilehash: 58a8dc226bb2720b6a8251f028712a80f74e893c
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141688"
---
# <a name="where-clause-c-reference"></a><span data-ttu-id="93750-103">where 절(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="93750-103">where clause (C# Reference)</span></span>

<span data-ttu-id="93750-104">`where` 절은 데이터 소스의 어떤 요소가 쿼리 식에서 반환될지를 지정하기 위해 쿼리 식에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="93750-104">The `where` clause is used in a query expression to specify which elements from the data source will be returned in the query expression.</span></span> <span data-ttu-id="93750-105">또한 각 소스 요소(범위 변수로 참조됨)에 부울 조건(*predicate*)을 적용하고 지정된 조건이 참인 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="93750-105">It applies a Boolean condition (*predicate*) to each source element (referenced by the range variable) and returns those for which the specified condition is true.</span></span> <span data-ttu-id="93750-106">단일 쿼리 식에는 여러 `where` 절을 포함할 수 있으며 단일 절에는 여러 조건부 하위 식을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93750-106">A single query expression may contain multiple `where` clauses and a single clause may contain multiple predicate subexpressions.</span></span>

## <a name="example"></a><span data-ttu-id="93750-107">예제</span><span class="sxs-lookup"><span data-stu-id="93750-107">Example</span></span>

<span data-ttu-id="93750-108">다음 예제에서 `where` 절은 5보다 작은 숫자를 제외한 모든 숫자를 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="93750-108">In the following example, the `where` clause filters out all numbers except those that are less than five.</span></span> <span data-ttu-id="93750-109">`where` 절을 제거하면 데이터 소스의 모든 숫자가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="93750-109">If you remove the `where` clause, all numbers from the data source would be returned.</span></span> <span data-ttu-id="93750-110">`num < 5` 식은 각 요소에 적용되는 조건자입니다.</span><span class="sxs-lookup"><span data-stu-id="93750-110">The expression `num < 5` is the predicate that is applied to each element.</span></span>

[!code-csharp[cscsrefQueryKeywords#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#5)]

## <a name="example"></a><span data-ttu-id="93750-111">예제</span><span class="sxs-lookup"><span data-stu-id="93750-111">Example</span></span>

<span data-ttu-id="93750-112">단일 `where` 절 내에서 [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) 및 [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) 연산자를 사용하여 조건자를 필요한 만큼 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93750-112">Within a single `where` clause, you can specify as many predicates as necessary by using the [&&](../operators/boolean-logical-operators.md#conditional-logical-and-operator-) and [&#124;&#124;](../operators/boolean-logical-operators.md#conditional-logical-or-operator-) operators.</span></span> <span data-ttu-id="93750-113">다음 예제에서 쿼리는 5 미만의 짝수만 선택하도록 두 개의 조건자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="93750-113">In the following example, the query specifies two predicates in order to select only the even numbers that are less than five.</span></span>

[!code-csharp[cscsrefQueryKeywords#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#6)]  

## <a name="example"></a><span data-ttu-id="93750-114">예제</span><span class="sxs-lookup"><span data-stu-id="93750-114">Example</span></span>

<span data-ttu-id="93750-115">`where` 절에는 부울 값을 반환하는 메서드를 하나 이상 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93750-115">A `where` clause may contain one or more methods that return Boolean values.</span></span> <span data-ttu-id="93750-116">다음 예제에서 `where` 절은 메서드를 사용하여 범위 변수의 현재 값이 짝수인지 홀수인지를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="93750-116">In the following example, the `where` clause uses a method to determine whether the current value of the range variable is even or odd.</span></span>

[!code-csharp[cscsrefQueryKeywords#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Where.cs#7)]

## <a name="remarks"></a><span data-ttu-id="93750-117">설명</span><span class="sxs-lookup"><span data-stu-id="93750-117">Remarks</span></span>

<span data-ttu-id="93750-118">`where` 절은 필터링 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="93750-118">The `where` clause is a filtering mechanism.</span></span> <span data-ttu-id="93750-119">첫 번째 또는 마지막 절이 될 수 없다는 점을 제외하고, 쿼리 식의 거의 모든 곳에 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93750-119">It can be positioned almost anywhere in a query expression, except it cannot be the first or last clause.</span></span> <span data-ttu-id="93750-120">소스 요소를 그룹화 전에 필터링할지, 그룹화 후에 필터링할지에 따라 `where` 절은 [group](group-clause.md) 절 앞 또는 뒤에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93750-120">A `where` clause may appear either before or after a [group](group-clause.md) clause depending on whether you have to filter the source elements before or after they are grouped.</span></span>

<span data-ttu-id="93750-121">지정된 조건자가 데이터 소스의 요소에 대해 유효하지 않은 경우, 컴파일 시간 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="93750-121">If a specified predicate is not valid for the elements in the data source, a compile-time error will result.</span></span> <span data-ttu-id="93750-122">이는 LINQ에서 제공하는 강력한 형식 검사의 이점 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="93750-122">This is one benefit of the strong type-checking provided by LINQ.</span></span>

<span data-ttu-id="93750-123">컴파일 시간에 `where` 키워드는 <xref:System.Linq.Enumerable.Where%2A> 표준 쿼리 연산자 메서드에 대한 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="93750-123">At compile time the `where` keyword is converted into a call to the <xref:System.Linq.Enumerable.Where%2A> Standard Query Operator method.</span></span>

## <a name="see-also"></a><span data-ttu-id="93750-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93750-124">See also</span></span>

- [<span data-ttu-id="93750-125">쿼리 키워드(LINQ)</span><span class="sxs-lookup"><span data-stu-id="93750-125">Query Keywords (LINQ)</span></span>](query-keywords.md)
- [<span data-ttu-id="93750-126">from 절</span><span class="sxs-lookup"><span data-stu-id="93750-126">from clause</span></span>](from-clause.md)
- [<span data-ttu-id="93750-127">select 절</span><span class="sxs-lookup"><span data-stu-id="93750-127">select clause</span></span>](select-clause.md)
- [<span data-ttu-id="93750-128">데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="93750-128">Filtering Data</span></span>](../../programming-guide/concepts/linq/filtering-data.md)
- [<span data-ttu-id="93750-129">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="93750-129">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="93750-130">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="93750-130">Language Integrated Query (LINQ)</span></span>](../../programming-guide/concepts/linq/index.md)
