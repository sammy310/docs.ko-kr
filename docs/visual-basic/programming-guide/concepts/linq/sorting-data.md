---
description: '자세한 정보: 데이터 정렬 (Visual Basic)'
title: 데이터 정렬
ms.date: 07/20/2015
ms.assetid: 6f81065c-0c89-4bf3-a6d8-442273f8810e
ms.openlocfilehash: 83e05b2af1b3421d004a87630cd5df43f2a21ae4
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100468553"
---
# <a name="sorting-data-visual-basic"></a><span data-ttu-id="68a36-103">데이터 정렬 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a36-103">Sorting Data (Visual Basic)</span></span>

<span data-ttu-id="68a36-104">정렬 작업은 하나 이상의 특성을 기준으로 시퀀스의 요소를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-104">A sorting operation orders the elements of a sequence based on one or more attributes.</span></span> <span data-ttu-id="68a36-105">첫 번째 정렬 기준은 요소에 대해 기본 정렬을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-105">The first sort criterion performs a primary sort on the elements.</span></span> <span data-ttu-id="68a36-106">두 번째 정렬 기준을 지정하면 각 기본 정렬 그룹 내의 요소를 정렬할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-106">By specifying a second sort criterion, you can sort the elements within each primary sort group.</span></span>

<span data-ttu-id="68a36-107">다음 그림은 문자 시퀀스에 대한 사전순 정렬 작업의 결과를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-107">The following illustration shows the results of an alphabetical sort operation on a sequence of characters.</span></span>

![사전순 정렬 작업을 보여 주는 그래픽입니다.](./media/sorting-data/alphabetical-sort-operation.png)

<span data-ttu-id="68a36-109">다음 섹션에는 데이터를 정렬하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-109">The standard query operator methods that sort data are listed in the following section.</span></span>

## <a name="methods"></a><span data-ttu-id="68a36-110">메서드</span><span class="sxs-lookup"><span data-stu-id="68a36-110">Methods</span></span>

|<span data-ttu-id="68a36-111">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="68a36-111">Method Name</span></span>|<span data-ttu-id="68a36-112">설명</span><span class="sxs-lookup"><span data-stu-id="68a36-112">Description</span></span>|<span data-ttu-id="68a36-113">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="68a36-113">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="68a36-114">추가 정보</span><span class="sxs-lookup"><span data-stu-id="68a36-114">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="68a36-115">OrderBy</span><span class="sxs-lookup"><span data-stu-id="68a36-115">OrderBy</span></span>|<span data-ttu-id="68a36-116">값을 오름차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-116">Sorts values in ascending order.</span></span>|`Order By`|<xref:System.Linq.Enumerable.OrderBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="68a36-117">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="68a36-117">OrderByDescending</span></span>|<span data-ttu-id="68a36-118">값을 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-118">Sorts values in descending order.</span></span>|`Order By … Descending`|<xref:System.Linq.Enumerable.OrderByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OrderByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="68a36-119">ThenBy</span><span class="sxs-lookup"><span data-stu-id="68a36-119">ThenBy</span></span>|<span data-ttu-id="68a36-120">2차 정렬을 오름차순으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-120">Performs a secondary sort in ascending order.</span></span>|`Order By …, …`|<xref:System.Linq.Enumerable.ThenBy%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenBy%2A?displayProperty=nameWithType>|
|<span data-ttu-id="68a36-121">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="68a36-121">ThenByDescending</span></span>|<span data-ttu-id="68a36-122">2차 정렬을 내림차순으로 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-122">Performs a secondary sort in descending order.</span></span>|`Order By …, … Descending`|<xref:System.Linq.Enumerable.ThenByDescending%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.ThenByDescending%2A?displayProperty=nameWithType>|
|<span data-ttu-id="68a36-123">Reverse</span><span class="sxs-lookup"><span data-stu-id="68a36-123">Reverse</span></span>|<span data-ttu-id="68a36-124">컬렉션에서 요소의 순서를 반대로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-124">Reverses the order of the elements in a collection.</span></span>|<span data-ttu-id="68a36-125">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="68a36-125">Not applicable.</span></span>|<xref:System.Linq.Enumerable.Reverse%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Reverse%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-examples"></a><span data-ttu-id="68a36-126">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="68a36-126">Query Expression Syntax Examples</span></span>

### <a name="primary-sort-examples"></a><span data-ttu-id="68a36-127">1차 정렬 예제</span><span class="sxs-lookup"><span data-stu-id="68a36-127">Primary Sort Examples</span></span>

#### <a name="primary-ascending-sort"></a><span data-ttu-id="68a36-128">1차 오름차순 정렬</span><span class="sxs-lookup"><span data-stu-id="68a36-128">Primary Ascending Sort</span></span>

<span data-ttu-id="68a36-129">다음 예제에서는 LINQ 쿼리에 `Order By` 절을 사용하여 배열의 문자열을 문자열 길이의 오름차순으로 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-129">The following example demonstrates how to use the `Order By` clause in a LINQ query to sort the strings in an array by string length, in ascending order.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' fox
' quick
' brown
' jumps
```

#### <a name="primary-descending-sort"></a><span data-ttu-id="68a36-130">1차 내림차순 정렬</span><span class="sxs-lookup"><span data-stu-id="68a36-130">Primary Descending Sort</span></span>

<span data-ttu-id="68a36-131">다음 예제에서는 LINQ 쿼리에 `Order By Descending` 절을 사용하여 문자열을 첫 글자의 내림차순으로 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-131">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to sort the strings by their first letter, in descending order.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' the
' quick
' jumps
' fox
' brown
```

### <a name="secondary-sort-examples"></a><span data-ttu-id="68a36-132">2차 정렬 예제</span><span class="sxs-lookup"><span data-stu-id="68a36-132">Secondary Sort Examples</span></span>

#### <a name="secondary-ascending-sort"></a><span data-ttu-id="68a36-133">2차 오름차순 정렬</span><span class="sxs-lookup"><span data-stu-id="68a36-133">Secondary Ascending Sort</span></span>

<span data-ttu-id="68a36-134">다음 예제에서는 LINQ 쿼리에 `Order By` 절을 사용하여 배열의 문자열에 대해 1차 및 2차 정렬을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-134">The following example demonstrates how to use the `Order By` clause in a LINQ query to perform a primary and secondary sort of the strings in an array.</span></span> <span data-ttu-id="68a36-135">문자열은 길이의 오름차순으로 1차 정렬된 다음 문자열 첫 글자의 오름차순으로 2차 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-135">The strings are sorted primarily by length and secondarily by the first letter of the string, both in ascending order.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1)
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' brown
' jumps
' quick
```

#### <a name="secondary-descending-sort"></a><span data-ttu-id="68a36-136">2차 내림차순 정렬</span><span class="sxs-lookup"><span data-stu-id="68a36-136">Secondary Descending Sort</span></span>

<span data-ttu-id="68a36-137">다음 예제에서는 LINQ 쿼리에 `Order By Descending` 절을 사용하여 1차 정렬을 오름차순으로 수행한 다음 2차 정렬을 내림차순으로 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-137">The next example demonstrates how to use the `Order By Descending` clause in a LINQ query to perform a primary sort, in ascending order, and a secondary sort, in descending order.</span></span> <span data-ttu-id="68a36-138">문자열은 길이순으로 1차 정렬된 다음 문자열 첫 글자순으로 2차 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a36-138">The strings are sorted primarily by length and secondarily by the first letter of the string.</span></span>

```vb
Dim words = {"the", "quick", "brown", "fox", "jumps"}

Dim sortQuery = From word In words
                Order By word.Length, word.Substring(0, 1) Descending
                Select word

Dim sb As New System.Text.StringBuilder()
For Each str As String In sortQuery
    sb.AppendLine(str)
Next

' Display the results.
MsgBox(sb.ToString())

' This code produces the following output:

' fox
' the
' quick
' jumps
' brown
```

## <a name="see-also"></a><span data-ttu-id="68a36-139">참조</span><span class="sxs-lookup"><span data-stu-id="68a36-139">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="68a36-140">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a36-140">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="68a36-141">Order By 절</span><span class="sxs-lookup"><span data-stu-id="68a36-141">Order By Clause</span></span>](../../../language-reference/queries/order-by-clause.md)
- [<span data-ttu-id="68a36-142">방법: 쿼리 결과 정렬</span><span class="sxs-lookup"><span data-stu-id="68a36-142">How to: Sort Query Results</span></span>](../../language-features/linq/how-to-sort-query-results-by-using-linq.md)
- [<span data-ttu-id="68a36-143">방법: 단어 또는 필드에 따라 텍스트 데이터 정렬 또는 필터링(LINQ)(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="68a36-143">How to: Sort or Filter Text Data by Any Word or Field (LINQ) (Visual Basic)</span></span>](how-to-sort-or-filter-text-data-by-any-word-or-field-linq.md)
