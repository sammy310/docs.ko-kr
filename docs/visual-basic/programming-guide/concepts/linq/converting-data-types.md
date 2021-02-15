---
description: '자세한 정보: 데이터 형식 변환 (Visual Basic)'
title: 데이터 형식 변환
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 7650f5d5d6f727b7815b9dd2de8a565e27fa18d9
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100428716"
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="2b9fa-103">데이터 형식 변환 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b9fa-103">Converting Data Types (Visual Basic)</span></span>

<span data-ttu-id="2b9fa-104">변환 메서드는 입력 개체의 형식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-104">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="2b9fa-105">LINQ 쿼리의 변환 작업은 다양한 애플리케이션에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-105">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="2b9fa-106">예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-106">The following are some examples:</span></span>

- <span data-ttu-id="2b9fa-107"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> 메서드는 표준 쿼리 연산자의 형식 사용자 지정 구현을 숨기는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-107">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="2b9fa-108"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> 메서드는 LINQ 쿼리에 대해 매개 변수가 없는 컬렉션을 사용하도록 설정하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-108">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="2b9fa-109"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> 메서드는 쿼리가 열거될 때까지 연기하는 대신 강제로 쿼리를 즉시 실행하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-109">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="2b9fa-110">메서드</span><span class="sxs-lookup"><span data-stu-id="2b9fa-110">Methods</span></span>

<span data-ttu-id="2b9fa-111">다음 표에는 데이터-형식 변환을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-111">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

<span data-ttu-id="2b9fa-112">이 표에서 이름이 "As"로 시작하는 변환 메서드는 소스 컬렉션의 정적 형식을 변경하지만 열거하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-112">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="2b9fa-113">이름이 "To"로 시작하는 메서드는 소스 컬렉션을 열거하고 항목을 해당하는 컬렉션 형식에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-113">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="2b9fa-114">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="2b9fa-114">Method Name</span></span>|<span data-ttu-id="2b9fa-115">설명</span><span class="sxs-lookup"><span data-stu-id="2b9fa-115">Description</span></span>|<span data-ttu-id="2b9fa-116">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="2b9fa-116">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="2b9fa-117">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2b9fa-117">More Information</span></span>|
|-----------------|-----------------|------------------------------------------|----------------------|
|<span data-ttu-id="2b9fa-118">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="2b9fa-118">AsEnumerable</span></span>|<span data-ttu-id="2b9fa-119"><xref:System.Collections.Generic.IEnumerable%601>로 형식화된 입력을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-119">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="2b9fa-120">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-120">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="2b9fa-121">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="2b9fa-121">AsQueryable</span></span>|<span data-ttu-id="2b9fa-122">(제네릭) <xref:System.Collections.IEnumerable>을 (제네릭) <xref:System.Linq.IQueryable>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-122">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="2b9fa-123">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-123">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="2b9fa-124">Cast</span><span class="sxs-lookup"><span data-stu-id="2b9fa-124">Cast</span></span>|<span data-ttu-id="2b9fa-125">컬렉션의 요소를 지정된 형식으로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-125">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="2b9fa-126">OfType</span><span class="sxs-lookup"><span data-stu-id="2b9fa-126">OfType</span></span>|<span data-ttu-id="2b9fa-127">지정된 형식으로 캐스트할 수 있는지 여부에 따라 값을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-127">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="2b9fa-128">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-128">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="2b9fa-129">ToArray</span><span class="sxs-lookup"><span data-stu-id="2b9fa-129">ToArray</span></span>|<span data-ttu-id="2b9fa-130">컬렉션을 배열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-130">Converts a collection to an array.</span></span> <span data-ttu-id="2b9fa-131">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-131">This method forces query execution.</span></span>|<span data-ttu-id="2b9fa-132">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-132">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="2b9fa-133">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="2b9fa-133">ToDictionary</span></span>|<span data-ttu-id="2b9fa-134">키 선택기 함수에 따라 <xref:System.Collections.Generic.Dictionary%602>에 요소를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-134">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="2b9fa-135">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-135">This method forces query execution.</span></span>|<span data-ttu-id="2b9fa-136">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-136">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="2b9fa-137">ToList</span><span class="sxs-lookup"><span data-stu-id="2b9fa-137">ToList</span></span>|<span data-ttu-id="2b9fa-138">컬렉션을 <xref:System.Collections.Generic.List%601>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-138">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="2b9fa-139">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-139">This method forces query execution.</span></span>|<span data-ttu-id="2b9fa-140">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-140">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="2b9fa-141">ToLookup</span><span class="sxs-lookup"><span data-stu-id="2b9fa-141">ToLookup</span></span>|<span data-ttu-id="2b9fa-142">키 선택기 함수에 따라 <xref:System.Linq.Lookup%602>(일 대 다 사전)에 요소를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-142">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="2b9fa-143">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-143">This method forces query execution.</span></span>|<span data-ttu-id="2b9fa-144">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-144">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="2b9fa-145">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="2b9fa-145">Query Expression Syntax Example</span></span>

<span data-ttu-id="2b9fa-146">다음 코드 예제에서는 하위 형식 `From As` 에만 사용할 수 있는 멤버에 액세스 하기 전에 절을 사용 하 여 형식을 하위 형식으로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b9fa-146">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```vb
Class Plant
    Public Property Name As String
End Class

Class CarnivorousPlant
    Inherits Plant
    Public Property TrapType As String
End Class

Sub Cast()

    Dim plants() As Plant = {
        New CarnivorousPlant With {.Name = "Venus Fly Trap", .TrapType = "Snap Trap"},
        New CarnivorousPlant With {.Name = "Pitcher Plant", .TrapType = "Pitfall Trap"},
        New CarnivorousPlant With {.Name = "Sundew", .TrapType = "Flypaper Trap"},
        New CarnivorousPlant With {.Name = "Waterwheel Plant", .TrapType = "Snap Trap"}}

    Dim query = From plant As CarnivorousPlant In plants
                Where plant.TrapType = "Snap Trap"
                Select plant

    Dim sb As New System.Text.StringBuilder()
    For Each plant In query
        sb.AppendLine(plant.Name)
    Next

    ' Display the results.
    MsgBox(sb.ToString())

    ' This code produces the following output:

    ' Venus Fly Trap
    ' Waterwheel Plant

End Sub
```

## <a name="see-also"></a><span data-ttu-id="2b9fa-147">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2b9fa-147">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="2b9fa-148">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b9fa-148">Standard Query Operators Overview (Visual Basic)</span></span>](standard-query-operators-overview.md)
- [<span data-ttu-id="2b9fa-149">From 절</span><span class="sxs-lookup"><span data-stu-id="2b9fa-149">From Clause</span></span>](../../../language-reference/queries/from-clause.md)
- [<span data-ttu-id="2b9fa-150">방법: LINQ를 사용 하 여 ArrayList 쿼리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2b9fa-150">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](how-to-query-an-arraylist-with-linq.md)
