---
title: 데이터 형식 변환 (Visual Basic)
ms.date: 07/20/2015
ms.assetid: 9b0cf1ab-de48-4c6e-9f00-05b40fade46e
ms.openlocfilehash: 4d0658983b5873c635d1926444293b0ddf5b0a87
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71835180"
---
# <a name="converting-data-types-visual-basic"></a><span data-ttu-id="49b15-102">데이터 형식 변환 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49b15-102">Converting Data Types (Visual Basic)</span></span>
<span data-ttu-id="49b15-103">변환 메서드는 입력 개체의 형식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-103">Conversion methods change the type of input objects.</span></span>  
  
 <span data-ttu-id="49b15-104">LINQ 쿼리의 변환 작업은 다양한 애플리케이션에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-104">Conversion operations in LINQ queries are useful in a variety of applications.</span></span> <span data-ttu-id="49b15-105">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-105">The following are some examples:</span></span>
  
- <span data-ttu-id="49b15-106"><xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> 메서드는 표준 쿼리 연산자의 형식 사용자 지정 구현을 숨기는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-106">The <xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType> method can be used to hide a type's custom implementation of a standard query operator.</span></span>  
  
- <span data-ttu-id="49b15-107"><xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> 메서드는 LINQ 쿼리에 대해 매개 변수가 없는 컬렉션을 사용하도록 설정하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-107">The <xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType> method can be used to enable non-parameterized collections for LINQ querying.</span></span>  
  
- <span data-ttu-id="49b15-108"><xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> 메서드는 쿼리가 열거될 때까지 연기하는 대신 강제로 쿼리를 즉시 실행하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-108">The <xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>, <xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>, and <xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType> methods can be used to force immediate query execution instead of deferring it until the query is enumerated.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="49b15-109">메서드</span><span class="sxs-lookup"><span data-stu-id="49b15-109">Methods</span></span>  
 <span data-ttu-id="49b15-110">다음 표에는 데이터-형식 변환을 수행하는 표준 쿼리 연산자 메서드가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-110">The following table lists the standard query operator methods that perform data-type conversions.</span></span>  
  
 <span data-ttu-id="49b15-111">이 표에서 이름이 "As"로 시작하는 변환 메서드는 소스 컬렉션의 정적 형식을 변경하지만 열거하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-111">The conversion methods in this table whose names start with "As" change the static type of the source collection but do not enumerate it.</span></span> <span data-ttu-id="49b15-112">이름이 "To"로 시작하는 메서드는 소스 컬렉션을 열거하고 항목을 해당하는 컬렉션 형식에 삽입합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-112">The methods whose names start with "To" enumerate the source collection and put the items into the corresponding collection type.</span></span>  
  
|<span data-ttu-id="49b15-113">메서드 이름</span><span class="sxs-lookup"><span data-stu-id="49b15-113">Method Name</span></span>|<span data-ttu-id="49b15-114">설명</span><span class="sxs-lookup"><span data-stu-id="49b15-114">Description</span></span>|<span data-ttu-id="49b15-115">Visual Basic 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="49b15-115">Visual Basic Query Expression Syntax</span></span>|<span data-ttu-id="49b15-116">추가 정보</span><span class="sxs-lookup"><span data-stu-id="49b15-116">More Information</span></span>|  
|-----------------|-----------------|------------------------------------------|----------------------|  
|<span data-ttu-id="49b15-117">AsEnumerable</span><span class="sxs-lookup"><span data-stu-id="49b15-117">AsEnumerable</span></span>|<span data-ttu-id="49b15-118"><xref:System.Collections.Generic.IEnumerable%601>로 형식화된 입력을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-118">Returns the input typed as <xref:System.Collections.Generic.IEnumerable%601>.</span></span>|<span data-ttu-id="49b15-119">이 오류에는 이 작업을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-119">Not applicable.</span></span>|<xref:System.Linq.Enumerable.AsEnumerable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="49b15-120">AsQueryable</span><span class="sxs-lookup"><span data-stu-id="49b15-120">AsQueryable</span></span>|<span data-ttu-id="49b15-121">(제네릭) <xref:System.Collections.IEnumerable>을 (제네릭) <xref:System.Linq.IQueryable>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-121">Converts a (generic) <xref:System.Collections.IEnumerable> to a (generic) <xref:System.Linq.IQueryable>.</span></span>|<span data-ttu-id="49b15-122">이 오류에는 이 작업을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-122">Not applicable.</span></span>|<xref:System.Linq.Queryable.AsQueryable%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="49b15-123">Cast</span><span class="sxs-lookup"><span data-stu-id="49b15-123">Cast</span></span>|<span data-ttu-id="49b15-124">컬렉션의 요소를 지정된 형식으로 캐스트합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-124">Casts the elements of a collection to a specified type.</span></span>|`From … As …`|<xref:System.Linq.Enumerable.Cast%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.Cast%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="49b15-125">OfType</span><span class="sxs-lookup"><span data-stu-id="49b15-125">OfType</span></span>|<span data-ttu-id="49b15-126">지정된 형식으로 캐스트할 수 있는지 여부에 따라 값을 필터링합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-126">Filters values, depending on their ability to be cast to a specified type.</span></span>|<span data-ttu-id="49b15-127">이 오류에는 이 작업을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-127">Not applicable.</span></span>|<xref:System.Linq.Enumerable.OfType%2A?displayProperty=nameWithType><br /><br /> <xref:System.Linq.Queryable.OfType%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="49b15-128">ToArray</span><span class="sxs-lookup"><span data-stu-id="49b15-128">ToArray</span></span>|<span data-ttu-id="49b15-129">컬렉션을 배열로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-129">Converts a collection to an array.</span></span> <span data-ttu-id="49b15-130">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-130">This method forces query execution.</span></span>|<span data-ttu-id="49b15-131">이 오류에는 이 작업을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-131">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToArray%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="49b15-132">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="49b15-132">ToDictionary</span></span>|<span data-ttu-id="49b15-133">키 선택기 함수에 따라 <xref:System.Collections.Generic.Dictionary%602>에 요소를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-133">Puts elements into a <xref:System.Collections.Generic.Dictionary%602> based on a key selector function.</span></span> <span data-ttu-id="49b15-134">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-134">This method forces query execution.</span></span>|<span data-ttu-id="49b15-135">이 오류에는 이 작업을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-135">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToDictionary%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="49b15-136">ToList</span><span class="sxs-lookup"><span data-stu-id="49b15-136">ToList</span></span>|<span data-ttu-id="49b15-137">컬렉션을 <xref:System.Collections.Generic.List%601>로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-137">Converts a collection to a <xref:System.Collections.Generic.List%601>.</span></span> <span data-ttu-id="49b15-138">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-138">This method forces query execution.</span></span>|<span data-ttu-id="49b15-139">이 오류에는 이 작업을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-139">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToList%2A?displayProperty=nameWithType>|  
|<span data-ttu-id="49b15-140">ToLookup</span><span class="sxs-lookup"><span data-stu-id="49b15-140">ToLookup</span></span>|<span data-ttu-id="49b15-141">키 선택기 함수에 따라 <xref:System.Linq.Lookup%602>(일 대 다 사전)에 요소를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-141">Puts elements into a <xref:System.Linq.Lookup%602> (a one-to-many dictionary) based on a key selector function.</span></span> <span data-ttu-id="49b15-142">이 메서드는 쿼리를 강제로 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-142">This method forces query execution.</span></span>|<span data-ttu-id="49b15-143">이 오류에는 이 작업을 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-143">Not applicable.</span></span>|<xref:System.Linq.Enumerable.ToLookup%2A?displayProperty=nameWithType>|  
  
## <a name="query-expression-syntax-example"></a><span data-ttu-id="49b15-144">쿼리 식 구문 예제</span><span class="sxs-lookup"><span data-stu-id="49b15-144">Query Expression Syntax Example</span></span>  
 <span data-ttu-id="49b15-145">다음 코드 예제에서는 `From As` 절을 사용 하 여 하위 형식에만 사용할 수 있는 멤버에 액세스 하기 전에 형식을 하위 형식으로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="49b15-145">The following code example uses the `From As` clause to cast a type to a subtype before accessing a member that is available only on the subtype.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="49b15-146">참조</span><span class="sxs-lookup"><span data-stu-id="49b15-146">See also</span></span>

- <xref:System.Linq>
- [<span data-ttu-id="49b15-147">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="49b15-147">Standard Query Operators Overview (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="49b15-148">From 절</span><span class="sxs-lookup"><span data-stu-id="49b15-148">From Clause</span></span>](../../../../visual-basic/language-reference/queries/from-clause.md)
- [<span data-ttu-id="49b15-149">방법: LINQ (Visual Basic)를 사용 하 여 ArrayList 쿼리 </span><span class="sxs-lookup"><span data-stu-id="49b15-149">How to: Query an ArrayList with LINQ (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/how-to-query-an-arraylist-with-linq.md)
