---
title: C#에서 LINQ 쿼리 작성하기
description: C#에서 LINQ 쿼리를 작성하는 방법을 알아봅니다.
ms.date: 12/01/2016
ms.assetid: 30703f79-cf3a-4d02-b892-c95d58a1d9ed
ms.openlocfilehash: bd7da81f2873c6a25570cab32fafecc66fd98be4
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88063447"
---
# <a name="write-linq-queries-in-c"></a><span data-ttu-id="6b3b7-103">C\#에서 LINQ 쿼리 작성하기</span><span class="sxs-lookup"><span data-stu-id="6b3b7-103">Write LINQ queries in C\#</span></span>

<span data-ttu-id="6b3b7-104">이 문서에서는 C#에서 LINQ 쿼리를 작성할 수 있는 세 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-104">This article shows the three ways in which you can write a LINQ query in C#:</span></span>

1. <span data-ttu-id="6b3b7-105">쿼리 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-105">Use query syntax.</span></span>

2. <span data-ttu-id="6b3b7-106">메서드 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-106">Use method syntax.</span></span>

3. <span data-ttu-id="6b3b7-107">쿼리 구문과 메서드 구문을 조합해서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-107">Use a combination of query syntax and method syntax.</span></span>

<span data-ttu-id="6b3b7-108">다음 예제에서는 앞서 나열한 각 방법을 사용하여 몇몇 간단한 LINQ 쿼리를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-108">The following examples demonstrate some simple LINQ queries by using each approach listed previously.</span></span> <span data-ttu-id="6b3b7-109">일반적인 규칙은 가능한 경우 항상 (1)을 사용하고, 필요할 때마다 (2) 및 (3)을 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-109">In general, the rule is to use (1) whenever possible, and use (2) and (3) whenever necessary.</span></span>

> [!NOTE]
> <span data-ttu-id="6b3b7-110">이러한 쿼리는 간단한 메모리 내 컬렉션에서 작동합니다. 그러나 기본 구문은 LINQ to Entities 및 LINQ to XML에서 사용되는 구문과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-110">These queries operate on simple in-memory collections; however, the basic syntax is identical to that used in LINQ to Entities and LINQ to XML.</span></span>

## <a name="example---query-syntax"></a><span data-ttu-id="6b3b7-111">예제 - 쿼리 구문</span><span class="sxs-lookup"><span data-stu-id="6b3b7-111">Example - Query syntax</span></span>

<span data-ttu-id="6b3b7-112">대부분의 쿼리를 작성하는 권장 방법은 *쿼리 구문*을 사용하여 *쿼리 식*을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-112">The recommended way to write most queries is to use *query syntax* to create *query expressions*.</span></span> <span data-ttu-id="6b3b7-113">다음 예제는 세 개의 쿼리 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-113">The following example shows three query expressions.</span></span> <span data-ttu-id="6b3b7-114">첫 번째 쿼리 식은 `where` 절과 함께 조건을 적용하여 결과를 필터링 또는 제한하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-114">The first query expression demonstrates how to filter or restrict results by applying conditions with a `where` clause.</span></span> <span data-ttu-id="6b3b7-115">이 식은 값이 7보다 크거나 3보다 작은 소스 시퀀스의 모든 요소를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-115">It returns all elements in the source sequence whose values are greater than 7 or less than 3.</span></span> <span data-ttu-id="6b3b7-116">두 번째 식은 반환된 결과를 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-116">The second expression demonstrates how to order the returned results.</span></span> <span data-ttu-id="6b3b7-117">세 번째 식은 키에 따라 결과를 그룹화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-117">The third expression demonstrates how to group results according to a key.</span></span> <span data-ttu-id="6b3b7-118">이 쿼리는 단어의 첫 글자를 기반으로 두 그룹을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-118">This query returns two groups based on the first letter of the word.</span></span>

[!code-csharp[csProgGuideLINQ#5](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_1.cs)]

<span data-ttu-id="6b3b7-119">쿼리의 형식은 <xref:System.Collections.Generic.IEnumerable%601>입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-119">Note that the type of the queries is <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="6b3b7-120">다음 예제와 같이 이러한 모든 쿼리는 `var`을 사용해 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-120">All of these queries could be written using `var` as shown in the following example:</span></span>

`var query = from num in numbers...`

<span data-ttu-id="6b3b7-121">이전의 각 예제에서는 `foreach` 문 또는 다른 문에서 쿼리 변수를 반복할 때까지 실제로 쿼리가 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-121">In each previous example, the queries do not actually execute until you iterate over the query variable in a `foreach` statement or other statement.</span></span> <span data-ttu-id="6b3b7-122">자세한 내용은 [LINQ 쿼리 소개](../programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-122">For more information, see [Introduction to LINQ Queries](../programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>

## <a name="example---method-syntax"></a><span data-ttu-id="6b3b7-123">예제 - 메서드 구문</span><span class="sxs-lookup"><span data-stu-id="6b3b7-123">Example - Method syntax</span></span>

<span data-ttu-id="6b3b7-124">일부 쿼리 작업은 메서드 호출로 표현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-124">Some query operations must be expressed as a method call.</span></span> <span data-ttu-id="6b3b7-125">가장 일반적인 메서드는 singleton 숫자 값을 반환하는 <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A> 등입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-125">The most common such methods are those that return singleton numeric values, such as <xref:System.Linq.Enumerable.Sum%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, <xref:System.Linq.Enumerable.Average%2A>, and so on.</span></span> <span data-ttu-id="6b3b7-126">이러한 메서드는 단일 값만 나타내며 추가 쿼리 작업의 소스로 사용할 수 없기 때문에 항상 모든 쿼리에서 마지막에 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-126">These methods must always be called last in any query because they represent only a single value and cannot serve as the source for an additional query operation.</span></span> <span data-ttu-id="6b3b7-127">다음 예제는 쿼리 식에서의 메서드 호출을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-127">The following example shows a method call in a query expression:</span></span>

[!code-csharp[csProgGuideLINQ#6](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_2.cs)]

<span data-ttu-id="6b3b7-128">메서드에 Action 또는 Func 매개 변수가 있는 경우 다음 예제와 같이 [lambda](../language-reference/operators/lambda-expressions.md) 식의 형식으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-128">If the method has Action or Func parameters, these are provided in the form of a [lambda](../language-reference/operators/lambda-expressions.md) expression, as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#7](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_3.cs)]

<span data-ttu-id="6b3b7-129">이전 쿼리에서 쿼리 #4만 즉시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-129">In the previous queries, only Query #4 executes immediately.</span></span> <span data-ttu-id="6b3b7-130">그 이유는 해당 쿼리가 제네릭 <xref:System.Collections.Generic.IEnumerable%601> 컬렉션이 아니라 단일 값을 반환하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-130">This is because it returns a single value, and not a generic <xref:System.Collections.Generic.IEnumerable%601> collection.</span></span> <span data-ttu-id="6b3b7-131">메서드 자체는 값을 계산하기 위해 `foreach`를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-131">The method itself has to use `foreach` in order to compute its value.</span></span>

<span data-ttu-id="6b3b7-132">다음 예제와 같이 [var](../language-reference/keywords/var.md)과 함께 암시적 형식을 사용하여 각각의 이전 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-132">Each of the previous queries can be written by using implicit typing with [var](../language-reference/keywords/var.md), as shown in the following example:</span></span>

[!code-csharp[csProgGuideLINQ#8](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_4.cs)]

## <a name="example---mixed-query-and-method-syntax"></a><span data-ttu-id="6b3b7-133">예제 - 혼합된 쿼리 및 메서드 구문</span><span class="sxs-lookup"><span data-stu-id="6b3b7-133">Example - Mixed query and method syntax</span></span>

<span data-ttu-id="6b3b7-134">이 예제는 쿼리 절의 결과에서 메서드 구문을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-134">This example shows how to use method syntax on the results of a query clause.</span></span> <span data-ttu-id="6b3b7-135">쿼리 식을 괄호로 묶은 다음 점 연산자를 적용하고 메서드를 호출하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-135">Just enclose the query expression in parentheses, and then apply the dot operator and call the method.</span></span> <span data-ttu-id="6b3b7-136">다음 예제에서 쿼리 #7은 값이 3과 7 사이인 숫자의 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-136">In the following example, query #7 returns a count of the numbers whose value is between 3 and 7.</span></span> <span data-ttu-id="6b3b7-137">그러나 일반적으로 두 번째 변수를 사용하여 메서드 호출의 결과를 저장하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-137">In general, however, it is better to use a second variable to store the result of the method call.</span></span> <span data-ttu-id="6b3b7-138">이렇게 하면 쿼리가 쿼리의 결과와 혼동될 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-138">In this manner, the query is less likely to be confused with the results of the query.</span></span>

[!code-csharp[csProgGuideLINQ#9](~/samples/snippets/csharp/concepts/linq/how-to-write-linq-queries_5.cs)]

<span data-ttu-id="6b3b7-139">쿼리 #7은 컬렉션이 아닌 단일 값을 반환하므로 쿼리가 즉시 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-139">Because Query #7 returns a single value and not a collection, the query executes immediately.</span></span>

<span data-ttu-id="6b3b7-140">이전 쿼리는 다음과 같이 `var`과 함께 암시적 형식을 사용하여 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-140">The previous query can be written by using implicit typing with `var`, as follows:</span></span>

```csharp
var numCount = (from num in numbers...
```

<span data-ttu-id="6b3b7-141">다음과 같이 메서드 구문에서 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-141">It can be written in method syntax as follows:</span></span>

```csharp
var numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

<span data-ttu-id="6b3b7-142">다음과 같이 명시적 형식을 사용하여 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6b3b7-142">It can be written by using explicit typing, as follows:</span></span>

```csharp
int numCount = numbers.Where(n => n < 3 || n > 7).Count();
```

## <a name="see-also"></a><span data-ttu-id="6b3b7-143">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6b3b7-143">See also</span></span>

- [<span data-ttu-id="6b3b7-144">연습: C#에서 쿼리 작성</span><span class="sxs-lookup"><span data-stu-id="6b3b7-144">Walkthrough: Writing Queries in C#</span></span>](../programming-guide/concepts/linq/walkthrough-writing-queries-linq.md)
- [<span data-ttu-id="6b3b7-145">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="6b3b7-145">Language Integrated Query (LINQ)</span></span>](index.md)
- [<span data-ttu-id="6b3b7-146">where 절</span><span class="sxs-lookup"><span data-stu-id="6b3b7-146">where clause</span></span>](../language-reference/keywords/where-clause.md)
