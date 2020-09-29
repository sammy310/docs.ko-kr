---
title: 데이터 형식 변환(C#)
description: 변환 메서드는 입력 개체의 형식을 변경합니다. Enumerable.AsEnumerable 및 Enumerable.OfType과 같은 C#에서 LINQ 쿼리의 변환 작업을 참조하세요.
ms.date: 07/20/2015
ms.assetid: 46e5682f-77a1-4302-8f93-a2b53c408808
ms.openlocfilehash: f9e3b354fd6eeba6564067550ea3821e4946d92f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91159139"
---
# <a name="converting-data-types-c"></a><span data-ttu-id="4984e-104">데이터 형식 변환(C#)</span><span class="sxs-lookup"><span data-stu-id="4984e-104">Converting Data Types (C#)</span></span>

<span data-ttu-id="4984e-105">변환 메서드는 입력 개체의 형식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-105">Conversion methods change the type of input objects.</span></span>

 <span data-ttu-id="4984e-106">LINQ 쿼리의 변환 작업은 다양한 애플리케이션에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-106">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="4984e-107">다음은 몇 가지 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-107">Following are some examples:</span></span>

- <span data-ttu-id="4984e-108"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> 메서드는 표준 쿼리 연산자의 형식 사용자 지정 구현을 숨기는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-108">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>

- <span data-ttu-id="4984e-109"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> 메서드는 LINQ 쿼리에 대해 매개 변수가 없는 컬렉션을 사용하도록 설정하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-109">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>

- <span data-ttu-id="4984e-110"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> 메서드는 쿼리가 열거될 때까지 연기하는 대신 강제로 쿼리를 즉시 실행하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-110">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>

## <a name="methods"></a><span data-ttu-id="4984e-111">메서드</span><span class="sxs-lookup"><span data-stu-id="4984e-111">Methods</span></span>

 <span data-ttu-id="4984e-112">다음 표에는 데이터-형식 변환을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-112">The following table lists the standard query operator methods that perform data-type conversions.</span></span>

 <span data-ttu-id="4984e-113">이 표에서 이름이 "As"로 시작하는 변환 메서드는 소스 컬렉션의 정적 형식을 변경하지만 열거하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-113">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="4984e-114">이름이 "To"로 시작하는 메서드는 소스 컬렉션을 열거하고 항목을 해당하는 컬렉션 형식에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-114">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>

|<span data-ttu-id="4984e-115">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="4984e-115">Method Name</span></span>|<span data-ttu-id="4984e-116">설명</span><span class="sxs-lookup"><span data-stu-id="4984e-116">Description</span></span>|<span data-ttu-id="4984e-117">C# 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="4984e-117">C# Query Expression Syntax</span></span>|<span data-ttu-id="4984e-118">추가 정보</span><span class="sxs-lookup"><span data-stu-id="4984e-118">More Information</span></span>|
|-----------------|-----------------|---------------------------------|----------------------|
|<span data-ttu-id="4984e-119">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="4984e-119">AsEnumerable</span></span>|<span data-ttu-id="4984e-120"><xref:System.Collections.Generic.IEnumerable%601>로 형식화된 입력을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-120">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="4984e-121">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4984e-121">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4984e-122">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="4984e-122">AsQueryable</span></span>|<span data-ttu-id="4984e-123">(제네릭) <xref:System.Collections.IEnumerable>을 (제네릭) <xref:System.Linq.IQueryable>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-123">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="4984e-124">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4984e-124">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4984e-125">Cast</span><span class="sxs-lookup"><span data-stu-id="4984e-125">Cast</span></span>|<span data-ttu-id="4984e-126">컬렉션의 요소를 지정된 형식으로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-126">Casts the elements of a collection to a specified type.</span></span>|<span data-ttu-id="4984e-127">명시적 형식 범위 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-127">Use an explicitly typed range variable.</span></span> <span data-ttu-id="4984e-128">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="4984e-128">For example:</span></span><br /><br /> `from string str in words`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4984e-129">OfType</span><span class="sxs-lookup"><span data-stu-id="4984e-129">OfType</span></span>|<span data-ttu-id="4984e-130">지정된 형식으로 캐스트할 수 있는지 여부에 따라 값을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-130">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="4984e-131">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4984e-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4984e-132">ToArray</span><span class="sxs-lookup"><span data-stu-id="4984e-132">ToArray</span></span>|<span data-ttu-id="4984e-133">컬렉션을 배열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-133">Converts a collection to an array.</span></span> <span data-ttu-id="4984e-134">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-134">This method forces query execution.</span></span>|<span data-ttu-id="4984e-135">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4984e-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4984e-136">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="4984e-136">ToDictionary</span></span>|<span data-ttu-id="4984e-137">키 선택기 함수에 따라 <xref:System.Collections.Generic.Dictionary%602>에 요소를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-137">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="4984e-138">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-138">This method forces query execution.</span></span>|<span data-ttu-id="4984e-139">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4984e-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4984e-140">ToList</span><span class="sxs-lookup"><span data-stu-id="4984e-140">ToList</span></span>|<span data-ttu-id="4984e-141">컬렉션을 <xref:System.Collections.Generic.List%601>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-141">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="4984e-142">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-142">This method forces query execution.</span></span>|<span data-ttu-id="4984e-143">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4984e-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|
|<span data-ttu-id="4984e-144">ToLookup</span><span class="sxs-lookup"><span data-stu-id="4984e-144">ToLookup</span></span>|<span data-ttu-id="4984e-145">키 선택기 함수에 따라 <xref:System.Linq.Lookup%602>(일 대 다 사전)에 요소를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-145">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="4984e-146">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-146">This method forces query execution.</span></span>|<span data-ttu-id="4984e-147">해당 사항 없음.</span><span class="sxs-lookup"><span data-stu-id="4984e-147">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|

## <a name="query-expression-syntax-example"></a><span data-ttu-id="4984e-148">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="4984e-148">Query Expression Syntax Example</span></span>

<span data-ttu-id="4984e-149">다음 코드 예제에서는 명시적 형식 범위 변수를 사용하여 하위 형식에서만 사용할 수 있는 멤버에 액세스하기 전에 형식을 하위 형식으로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="4984e-149">The following code example uses an explicitly typed range variable to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>

```csharp
class Plant
{
    public string Name { get; set; }
}

class CarnivorousPlant : Plant
{
    public string TrapType { get; set; }
}

static void Cast()
{
    Plant[] plants = new Plant[] {
        new CarnivorousPlant { Name = "Venus Fly Trap", TrapType = "Snap Trap" },
        new CarnivorousPlant { Name = "Pitcher Plant", TrapType = "Pitfall Trap" },
        new CarnivorousPlant { Name = "Sundew", TrapType = "Flypaper Trap" },
        new CarnivorousPlant { Name = "Waterwheel Plant", TrapType = "Snap Trap" }
    };

    var query = from CarnivorousPlant cPlant in plants
                where cPlant.TrapType == "Snap Trap"
                select cPlant;

    foreach (Plant plant in query)
        Console.WriteLine(plant.Name);

    /* This code produces the following output:

        Venus Fly Trap
        Waterwheel Plant
    */
}
```

## <a name="see-also"></a><span data-ttu-id="4984e-150">참조</span><span class="sxs-lookup"><span data-stu-id="4984e-150">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="4984e-151">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="4984e-151">Standard Query Operators Overview (C#)</span></span>](./standard-query-operators-overview.md)
- [<span data-ttu-id="4984e-152">from 절</span><span class="sxs-lookup"><span data-stu-id="4984e-152">from clause</span></span>](../../../language-reference/keywords/from-clause.md)
- [<span data-ttu-id="4984e-153">LINQ 쿼리 식</span><span class="sxs-lookup"><span data-stu-id="4984e-153">LINQ Query Expressions</span></span>](../../../linq/index.md)
- [<span data-ttu-id="4984e-154">LINQ를 사용하여 ArrayList를 쿼리하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="4984e-154">How to query an ArrayList with LINQ (C#)</span></span>](./how-to-query-an-arraylist-with-linq.md)
