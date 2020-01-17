---
title: 데이터 정렬(C#)
ms.date: 07/20/2015
ms.assetid: d93fa055-2f19-46d2-9898-e2aed628f1c9
ms.openlocfilehash: 8db5ab2ead0e59b8d41d83704ff237d4493155c3
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346463"
---
# <a name="sorting-data-c"></a><span data-ttu-id="484a4-102">데이터 정렬(C#)</span><span class="sxs-lookup"><span data-stu-id="484a4-102">Sorting Data (C#)</span></span>
<span data-ttu-id="484a4-103">정렬 작업은 하나 이상의 특성을 기준으로 시퀀스의 요소를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-103">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="484a4-104">첫 번째 정렬 기준은 요소에 대해 기본 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-104">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="484a4-105">두 번째 정렬 기준을 지정하면 각 기본 정렬 그룹 내의 요소를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-105">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>  
  
 <span data-ttu-id="484a4-106">다음 그림은 문자 시퀀스에 대한 사전순 정렬 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-106">The following illustration shows the results of an alphabetical sort operation on a sequence of characters:</span></span> 
  
 ![사전순 정렬 작업을 보여 주는 그래픽입니다.](./media/sorting-data/alphabetical-sort-operation.png)  
  
 <span data-ttu-id="484a4-108">다음 섹션에는 데이터를 정렬하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-108">The standard query operator methods that sort data are listed in the following section.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="484a4-109">메서드</span><span class="sxs-lookup"><span data-stu-id="484a4-109">Methods</span></span>  
  
|<span data-ttu-id="484a4-110">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="484a4-110">Method Name</span></span>|<span data-ttu-id="484a4-111">설명</span><span class="sxs-lookup"><span data-stu-id="484a4-111">Description</span></span>|<span data-ttu-id="484a4-112">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="484a4-112">C# Query Expression Syntax</span></span>|<span data-ttu-id="484a4-113">추가 정보</span><span class="sxs-lookup"><span data-stu-id="484a4-113">More Information</span></span>|  
|-----------------|-----------------|---------------------------------|----------------------|  
|<span data-ttu-id="484a4-114">OrderBy</span><span class="sxs-lookup"><span data-stu-id="484a4-114">OrderBy</span></span>|<span data-ttu-id="484a4-115">값을 오름차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-115">Sorts values in ascending order.</span></span>|`orderby`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="484a4-116">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="484a4-116">OrderByDescending</span></span>|<span data-ttu-id="484a4-117">값을 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-117">Sorts values in descending order.</span></span>|`orderby … descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="484a4-118">ThenBy</span><span class="sxs-lookup"><span data-stu-id="484a4-118">ThenBy</span></span>|<span data-ttu-id="484a4-119">2차 정렬을 오름차순으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-119">Performs a secondary sort in ascending order.</span></span>|`orderby …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="484a4-120">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="484a4-120">ThenByDescending</span></span>|<span data-ttu-id="484a4-121">2차 정렬을 내림차순으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-121">Performs a secondary sort in descending order.</span></span>|`orderby …, … descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="484a4-122">Reverse</span><span class="sxs-lookup"><span data-stu-id="484a4-122">Reverse</span></span>|<span data-ttu-id="484a4-123">컬렉션에서 요소의 순서를 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-123">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="484a4-124">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="484a4-124">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-examples"></a><span data-ttu-id="484a4-125">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="484a4-125">Query Expression Syntax Examples</span></span>  
  
### <a name="primary-sort-examples"></a><span data-ttu-id="484a4-126">1차 정렬 예제</span><span class="sxs-lookup"><span data-stu-id="484a4-126">Primary Sort Examples</span></span>  
  
#### <a name="primary-ascending-sort"></a><span data-ttu-id="484a4-127">1차 오름차순 정렬</span><span class="sxs-lookup"><span data-stu-id="484a4-127">Primary Ascending Sort</span></span>  
 <span data-ttu-id="484a4-128">다음 예제에서는 LINQ 쿼리에 `orderby` 절을 사용하여 배열의 문자열을 문자열 길이의 오름차순으로 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-128">The following example demonstrates how to use the `orderby` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    brown  
    jumps  
*/  
```  
  
#### <a name="primary-descending-sort"></a><span data-ttu-id="484a4-129">1차 내림차순 정렬</span><span class="sxs-lookup"><span data-stu-id="484a4-129">Primary Descending Sort</span></span>  
 <span data-ttu-id="484a4-130">다음 예제에서는 LINQ 쿼리에 `orderby descending` 절을 사용하여 문자열을 첫 글자의 내림차순으로 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-130">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    quick  
    jumps  
    fox  
    brown  
*/  
```  
  
### <a name="secondary-sort-examples"></a><span data-ttu-id="484a4-131">2차 정렬 예제</span><span class="sxs-lookup"><span data-stu-id="484a4-131">Secondary Sort Examples</span></span>  
  
#### <a name="secondary-ascending-sort"></a><span data-ttu-id="484a4-132">2차 오름차순 정렬</span><span class="sxs-lookup"><span data-stu-id="484a4-132">Secondary Ascending Sort</span></span>  
 <span data-ttu-id="484a4-133">다음 예제에서는 LINQ 쿼리에 `orderby` 절을 사용하여 배열의 문자열에 대해 1차 및 2차 정렬을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-133">The following example demonstrates how to use the `orderby` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="484a4-134">문자열은 길이의 오름차순으로 1차 정렬된 다음 문자열 첫 글자의 오름차순으로 2차 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-134">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1)  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    fox  
    the  
    brown  
    jumps  
    quick  
*/  
```  
  
#### <a name="secondary-descending-sort"></a><span data-ttu-id="484a4-135">2차 내림차순 정렬</span><span class="sxs-lookup"><span data-stu-id="484a4-135">Secondary Descending Sort</span></span>  
 <span data-ttu-id="484a4-136">다음 예제에서는 LINQ 쿼리에 `orderby descending` 절을 사용하여 1차 정렬을 오름차순으로 수행한 다음 2차 정렬을 내림차순으로 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-136">The next example demonstrates how to use the `orderby descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="484a4-137">문자열은 길이순으로 1차 정렬된 다음 문자열 첫 글자순으로 2차 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="484a4-137">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>  
  
```csharp  
string[] words = { "the", "quick", "brown", "fox", "jumps" };  
  
IEnumerable<string> query = from word in words  
                            orderby word.Length, word.Substring(0, 1) descending  
                            select word;  
  
foreach (string str in query)  
    Console.WriteLine(str);  
  
/* This code produces the following output:  
  
    the  
    fox  
    quick  
    jumps  
    brown  
*/  
```  
  
## <a name="see-also"></a><span data-ttu-id="484a4-138">참조</span><span class="sxs-lookup"><span data-stu-id="484a4-138">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="484a4-139">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="484a4-139">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="484a4-140">orderby 절</span><span class="sxs-lookup"><span data-stu-id="484a4-140">orderby clause</span></span>](../../../language-reference/keywords/orderby-clause.md)
- [<span data-ttu-id="484a4-141">Join 절 결과를 서순대로 정렬</span><span class="sxs-lookup"><span data-stu-id="484a4-141">Order the results of a join clause</span></span>](../../../linq/order-the-results-of-a-join-clause.md)
- [<span data-ttu-id="484a4-142">단어 또는 필드에 따라 텍스트 데이터를 정렬하거나 필터링하는 방법(LINQ)(C#)</span><span class="sxs-lookup"><span data-stu-id="484a4-142">How to sort or filter text data by any word or field (LINQ) (C#)</span></span>](./how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
