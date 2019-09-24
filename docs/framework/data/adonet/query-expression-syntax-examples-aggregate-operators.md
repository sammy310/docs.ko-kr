---
title: '쿼리 식 구문 예제: 집계 연산자 (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 85dafa07-e102-46e7-ab78-37bf06f257a6
ms.openlocfilehash: 44e38a53823cb52040a612d4762e33283f90e1d1
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794521"
---
# <a name="query-expression-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="affa4-102">쿼리 식 구문 예제: 집계 연산자 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="affa4-102">Query Expression Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="affa4-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Sum%2A> 메서드에서 쿼리 식 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하고 데이터를 집계하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query a <xref:System.Data.DataSet> and aggregate data using query expression syntax.</span></span>  
  
 <span data-ttu-id="affa4-104">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드하는데 지정됩니다](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="affa4-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="affa4-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="affa4-106">이 항목의 예제에서는 다음 `using` / `Imports` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="affa4-107">자세한 내용은 [방법: Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)에서 LINQ to DataSet 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="average"></a><span data-ttu-id="affa4-108">평균</span><span class="sxs-lookup"><span data-stu-id="affa4-108">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="affa4-109">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-109">Example</span></span>  
 <span data-ttu-id="affa4-110">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 스타일의 평균 제품 가격을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-110">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="affa4-111">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-111">Example</span></span>  
 <span data-ttu-id="affa4-112">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A>를 사용하여 각 연락처 ID의 평균 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-112">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="affa4-113">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-113">Example</span></span>  
 <span data-ttu-id="affa4-114">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A>를 사용하여 각 연락처의 평균 `TotalDue`를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-114">This example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="affa4-115">개수</span><span class="sxs-lookup"><span data-stu-id="affa4-115">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="affa4-116">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-116">Example</span></span>  
 <span data-ttu-id="affa4-117">이 예제에서는 <xref:System.Linq.Enumerable.Count%2A>를 사용하여 연락처 ID와 각 연락처의 주문 수로 구성된 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-117">This example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="affa4-118">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-118">Example</span></span>  
 <span data-ttu-id="affa4-119">이 예제에서는 색으로 제품을 그룹화한 다음 <xref:System.Linq.Enumerable.Count%2A>를 사용하여 각 색 그룹의 제품 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-119">This example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="affa4-120">최대</span><span class="sxs-lookup"><span data-stu-id="affa4-120">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="affa4-121">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-121">Example</span></span>  
 <span data-ttu-id="affa4-122">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID의 최대 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-122">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="affa4-123">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-123">Example</span></span>  
 <span data-ttu-id="affa4-124">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID에 대해 최대 `TotalDue`를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-124">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="affa4-125">최소</span><span class="sxs-lookup"><span data-stu-id="affa4-125">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="affa4-126">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-126">Example</span></span>  
 <span data-ttu-id="affa4-127">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID의 최소 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-127">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="affa4-128">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-128">Example</span></span>  
 <span data-ttu-id="affa4-129">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID에 대해 최소 합계를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-129">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="affa4-130">Sum</span><span class="sxs-lookup"><span data-stu-id="affa4-130">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="affa4-131">예제</span><span class="sxs-lookup"><span data-stu-id="affa4-131">Example</span></span>  
 <span data-ttu-id="affa4-132">이 예제에서는 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 각 연락처 ID의 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="affa4-132">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="affa4-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="affa4-133">See also</span></span>

- [<span data-ttu-id="affa4-134">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="affa4-134">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="affa4-135">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="affa4-135">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="affa4-136">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="affa4-136">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="affa4-137">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="affa4-137">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
