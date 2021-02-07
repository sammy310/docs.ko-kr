---
description: '자세한 정보: Method-Based 쿼리 예제 (LINQ to DataSet)'
title: 메서드 기반 쿼리 예제(LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: d340775c-7f39-4087-a290-5cbec6cfa68e
ms.openlocfilehash: 4597dee40bb3c75b6cbca946e0833672c8512c06
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739172"
---
# <a name="method-based-query-examples-linq-to-dataset"></a><span data-ttu-id="6be9d-103">메서드 기반 쿼리 예제(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="6be9d-103">Method-Based Query Examples (LINQ to DataSet)</span></span>

<span data-ttu-id="6be9d-104">이 섹션에서는 표준 쿼리 연산자를 사용 하는 메서드 기반 쿼리 구문에 LINQ to DataSet 프로그래밍 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-104">This section provides LINQ to DataSet programming examples in method-based query syntax that use the standard query operators.</span></span> <span data-ttu-id="6be9d-105"><xref:System.Data.DataSet>이러한 예제에서 사용 되는은 `FillDataSet` [데이터 집합에 데이터를 로드](loading-data-into-a-dataset.md)하는 데 지정 된 메서드를 사용 하 여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-105">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="6be9d-106">자세한 내용은 [표준 쿼리 연산자 개요 (c #)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) 또는 [표준 쿼리 연산자 개요 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6be9d-106">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6be9d-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6be9d-107">In This Section</span></span>  

 [<span data-ttu-id="6be9d-108">프로젝션</span><span class="sxs-lookup"><span data-stu-id="6be9d-108">Projection</span></span>](method-based-query-syntax-examples-projection.md)  
 <span data-ttu-id="6be9d-109">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 및 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-109">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="6be9d-110">분할</span><span class="sxs-lookup"><span data-stu-id="6be9d-110">Partitioning</span></span>](method-based-query-syntax-examples-partitioning-linq.md)  
 <span data-ttu-id="6be9d-111">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 분할하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-111">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> and partition the results.</span></span>  
  
 [<span data-ttu-id="6be9d-112">주</span><span class="sxs-lookup"><span data-stu-id="6be9d-112">Ordering</span></span>](method-based-query-syntax-examples-ordering-linq-to-dataset.md)  
 <span data-ttu-id="6be9d-113">이 항목의 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> 및 <xref:System.Linq.Enumerable.ThenByDescending%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-113">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results.</span></span>  
  
 [<span data-ttu-id="6be9d-114">세트 연산자</span><span class="sxs-lookup"><span data-stu-id="6be9d-114">Set Operators</span></span>](method-based-query-syntax-examples-set-operators.md)  
 <span data-ttu-id="6be9d-115">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A> 및 <xref:System.Linq.Enumerable.Union%2A> 연산자를 사용하여 데이터 행 집합에 대해 값 기반 비교 연산을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-115">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.</span></span>  
  
 [<span data-ttu-id="6be9d-116">변환 연산자</span><span class="sxs-lookup"><span data-stu-id="6be9d-116">Conversion Operators</span></span>](method-based-query-syntax-examples-conversion-operators.md)  
 <span data-ttu-id="6be9d-117">이 항목의 예제에서는 <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> 및 <xref:System.Linq.Enumerable.ToList%2A> 메서드를 사용하여 쿼리 식을 즉시 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-117">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 [<span data-ttu-id="6be9d-118">요소 연산자</span><span class="sxs-lookup"><span data-stu-id="6be9d-118">Element Operators</span></span>](method-based-query-syntax-examples-element-operators.md)  
 <span data-ttu-id="6be9d-119">이 항목의 예제에서는 <xref:System.Linq.Enumerable.First%2A> 및 <xref:System.Linq.Enumerable.ElementAt%2A> 메서드를 사용하여 <xref:System.Data.DataRow>에서 <xref:System.Data.DataSet> 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-119">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="6be9d-120">집계 연산자</span><span class="sxs-lookup"><span data-stu-id="6be9d-120">Aggregate Operators</span></span>](method-based-query-syntax-examples-aggregate-operators.md)  
 <span data-ttu-id="6be9d-121">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 데이터를 집계하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-121">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data.</span></span>  
  
 [<span data-ttu-id="6be9d-122">Join</span><span class="sxs-lookup"><span data-stu-id="6be9d-122">Join</span></span>](method-based-query-syntax-examples-join-linq-to-dataset.md)  
 <span data-ttu-id="6be9d-123">이 항목의 예제에서는 <xref:System.Linq.Enumerable.GroupJoin%2A> 및 <xref:System.Linq.Enumerable.Join%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6be9d-123">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6be9d-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6be9d-124">See also</span></span>

- [<span data-ttu-id="6be9d-125">쿼리 식 예제</span><span class="sxs-lookup"><span data-stu-id="6be9d-125">Query Expression Examples</span></span>](query-expression-examples-linq-to-dataset.md)
- [<span data-ttu-id="6be9d-126">DataSet별 연산자 예제</span><span class="sxs-lookup"><span data-stu-id="6be9d-126">DataSet-Specific Operator Examples</span></span>](dataset-specific-operator-examples-linq-to-dataset.md)
- [<span data-ttu-id="6be9d-127">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="6be9d-127">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
