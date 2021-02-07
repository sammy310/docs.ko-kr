---
description: '자세한 정보: 쿼리 식 예제 (LINQ to DataSet)'
title: 쿼리 식 예제(LINQ to DataSet)
ms.date: 03/30/2017
ms.assetid: f743fbc7-faff-45e5-af1e-61577d87f0cc
ms.openlocfilehash: 1d1571a851fae685942cbdbd557b275e86e8b0d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663692"
---
# <a name="query-expression-examples-linq-to-dataset"></a><span data-ttu-id="769fc-103">쿼리 식 예제(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="769fc-103">Query Expression Examples (LINQ to DataSet)</span></span>

<span data-ttu-id="769fc-104">이 섹션에서는 표준 쿼리 연산자를 사용 하는 쿼리 식 구문에 LINQ to DataSet 프로그래밍 예제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="769fc-104">This section provides LINQ to DataSet programming examples in query expression syntax that use the standard query operators.</span></span> <span data-ttu-id="769fc-105"><xref:System.Data.DataSet>이러한 예제에서 사용 되는은 `FillDataSet` [데이터 집합에 데이터를 로드](loading-data-into-a-dataset.md)하는 데 지정 된 메서드를 사용 하 여 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="769fc-105">The <xref:System.Data.DataSet> used in these examples is populated by using the `FillDataSet` method, which is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span> <span data-ttu-id="769fc-106">자세한 내용은 [표준 쿼리 연산자 개요 (c #)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) 또는 [표준 쿼리 연산자 개요 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="769fc-106">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="769fc-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="769fc-107">In This Section</span></span>  

 [<span data-ttu-id="769fc-108">프로젝션</span><span class="sxs-lookup"><span data-stu-id="769fc-108">Projection</span></span>](query-expression-syntax-examples-projection-linq-to-dataset.md)  
 <span data-ttu-id="769fc-109">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 및 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="769fc-109">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="769fc-110">제한 사항</span><span class="sxs-lookup"><span data-stu-id="769fc-110">Restriction</span></span>](query-expression-syntax-examples-restriction-linq-to-dataset.md)  
 <span data-ttu-id="769fc-111">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Where%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="769fc-111">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Where%2A> method to query a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="769fc-112">분할</span><span class="sxs-lookup"><span data-stu-id="769fc-112">Partitioning</span></span>](query-expression-syntax-examples-partitioning.md)  
 <span data-ttu-id="769fc-113">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 분할하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="769fc-113">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> and partition the results.</span></span>  
  
 [<span data-ttu-id="769fc-114">주</span><span class="sxs-lookup"><span data-stu-id="769fc-114">Ordering</span></span>](query-expression-syntax-examples-ordering-linq-to-dataset.md)  
 <span data-ttu-id="769fc-115">이 항목의 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A> 및 <xref:System.Linq.Enumerable.ThenByDescending%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="769fc-115">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.OrderByDescending%2A>, <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenByDescending%2A> methods to query a <xref:System.Data.DataSet> and order the results.</span></span>  
  
 [<span data-ttu-id="769fc-116">요소 연산자</span><span class="sxs-lookup"><span data-stu-id="769fc-116">Element Operators</span></span>](query-expression-syntax-examples-element-operators.md)  
 <span data-ttu-id="769fc-117">이 항목의 예제에서는 <xref:System.Linq.Enumerable.First%2A> 및 <xref:System.Linq.Enumerable.ElementAt%2A> 메서드를 사용하여 <xref:System.Data.DataRow>에서 <xref:System.Data.DataSet> 요소를 가져오는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="769fc-117">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet>.</span></span>  
  
 [<span data-ttu-id="769fc-118">집계 연산자</span><span class="sxs-lookup"><span data-stu-id="769fc-118">Aggregate Operators</span></span>](query-expression-syntax-examples-aggregate-operators.md)  
 <span data-ttu-id="769fc-119">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하고 데이터를 집계하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="769fc-119">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data.</span></span>  
  
 [<span data-ttu-id="769fc-120">조인 연산자</span><span class="sxs-lookup"><span data-stu-id="769fc-120">Join Operators</span></span>](query-expression-syntax-examples-join-operators.md)  
 <span data-ttu-id="769fc-121">이 항목의 예제에서는 <xref:System.Linq.Enumerable.GroupJoin%2A> 및 <xref:System.Linq.Enumerable.Join%2A> 메서드를 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="769fc-121">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet>.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="769fc-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="769fc-122">See also</span></span>

- [<span data-ttu-id="769fc-123">메서드 기반 쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="769fc-123">Method-Based Query Examples</span></span>](method-based-query-examples-linq-to-dataset.md)
- [<span data-ttu-id="769fc-124">DataSet별 연산자 예제</span><span class="sxs-lookup"><span data-stu-id="769fc-124">DataSet-Specific Operator Examples</span></span>](dataset-specific-operator-examples-linq-to-dataset.md)
- [<span data-ttu-id="769fc-125">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="769fc-125">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
