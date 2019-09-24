---
title: '메서드 기반 쿼리 구문 예제: 집계 연산자 (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ed5f01d-acb2-4dd4-be60-f04c2d570fa8
ms.openlocfilehash: 348070663e414f2768b6b57d880c41d4da6c7bb2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794924"
---
# <a name="method-based-query-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="6a3d0-102">메서드 기반 쿼리 구문 예제: 집계 연산자 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="6a3d0-102">Method-Based Query Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="6a3d0-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Sum%2A> 연산자에서 메서드 쿼리 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하고 데이터를 집계하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> operators to query a <xref:System.Data.DataSet> and aggregate data using method query syntax.</span></span>  
  
 <span data-ttu-id="6a3d0-104">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드하는데 지정됩니다](loading-data-into-a-dataset.md).</span><span class="sxs-lookup"><span data-stu-id="6a3d0-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="6a3d0-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6a3d0-106">이 항목의 예제에서는 다음 `using` / `Imports` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="6a3d0-107">자세한 내용은 [방법: Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)에서 LINQ to DataSet 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="aggregate"></a><span data-ttu-id="6a3d0-108">Aggregate</span><span class="sxs-lookup"><span data-stu-id="6a3d0-108">Aggregate</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a3d0-109">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-109">Example</span></span>  
 <span data-ttu-id="6a3d0-110">이 예제에서는 <xref:System.Linq.Enumerable.Aggregate%2A> 메서드를 사용하여 `Contact` 테이블에서 맨 위쪽에 있는 5개의 연락처 정보를 가져온 다음 쉼표로 구분된 성 목록을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-110">This example uses the <xref:System.Linq.Enumerable.Aggregate%2A> method to get the first 5 contacts from the `Contact` table and build a comma-delimited list of the last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#aggregate_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#aggregate_mq)]  
  
## <a name="average"></a><span data-ttu-id="6a3d0-111">평균</span><span class="sxs-lookup"><span data-stu-id="6a3d0-111">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a3d0-112">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-112">Example</span></span>  
 <span data-ttu-id="6a3d0-113">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 제품의 평균 가격을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-113">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-114">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-114">Example</span></span>  
 <span data-ttu-id="6a3d0-115">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 스타일의 평균 제품 가격을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-115">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-116">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-116">Example</span></span>  
 <span data-ttu-id="6a3d0-117">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 평균 합계를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-117">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-118">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-118">Example</span></span>  
 <span data-ttu-id="6a3d0-119">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 연락처 ID의 평균 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-119">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-120">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-120">Example</span></span>  
 <span data-ttu-id="6a3d0-121">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 연락처에 대해 평균 `TotalDue`를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-121">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="6a3d0-122">개수</span><span class="sxs-lookup"><span data-stu-id="6a3d0-122">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a3d0-123">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-123">Example</span></span>  
 <span data-ttu-id="6a3d0-124">이 예제에서는 <xref:System.Linq.Enumerable.Count%2A> 메서드를 사용하여 `Product` 테이블에 있는 제품 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-124">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the `Product` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#count)]
 [!code-vb[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-125">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-125">Example</span></span>  
 <span data-ttu-id="6a3d0-126">이 예제에서는 <xref:System.Linq.Enumerable.Count%2A> 메서드를 사용하여 연락처 ID와 각 연락처의 주문 수로 구성된 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-126">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-127">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-127">Example</span></span>  
 <span data-ttu-id="6a3d0-128">이 예제에서는 색으로 제품을 그룹화한 다음 <xref:System.Linq.Enumerable.Count%2A> 메서드를 사용하여 각 색 그룹의 제품 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-128">This example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="6a3d0-129">LongCount</span><span class="sxs-lookup"><span data-stu-id="6a3d0-129">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a3d0-130">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-130">Example</span></span>  
 <span data-ttu-id="6a3d0-131">이 예제에서는 연락처 수를 정수(Long)로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-131">This example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="6a3d0-132">최대</span><span class="sxs-lookup"><span data-stu-id="6a3d0-132">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a3d0-133">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-133">Example</span></span>  
 <span data-ttu-id="6a3d0-134">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 최대 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-134">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-135">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-135">Example</span></span>  
 <span data-ttu-id="6a3d0-136">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID의 최대 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-136">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-137">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-137">Example</span></span>  
 <span data-ttu-id="6a3d0-138">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID에 대해 최대 `TotalDue`를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-138">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="6a3d0-139">최소</span><span class="sxs-lookup"><span data-stu-id="6a3d0-139">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a3d0-140">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-140">Example</span></span>  
 <span data-ttu-id="6a3d0-141">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 최소 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-141">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-142">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-142">Example</span></span>  
 <span data-ttu-id="6a3d0-143">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID의 최소 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-143">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-144">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-144">Example</span></span>  
 <span data-ttu-id="6a3d0-145">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID에 대해 최소 합계를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-145">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="6a3d0-146">Sum</span><span class="sxs-lookup"><span data-stu-id="6a3d0-146">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="6a3d0-147">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-147">Example</span></span>  
 <span data-ttu-id="6a3d0-148">이 예제에서는 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 `SalesOrderDetail` 테이블의 전체 주문 수량을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-148">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the `SalesOrderDetail` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="6a3d0-149">예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-149">Example</span></span>  
 <span data-ttu-id="6a3d0-150">이 예제에서는 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 각 연락처 ID의 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6a3d0-150">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="6a3d0-151">참고자료</span><span class="sxs-lookup"><span data-stu-id="6a3d0-151">See also</span></span>

- [<span data-ttu-id="6a3d0-152">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="6a3d0-152">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="6a3d0-153">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="6a3d0-153">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="6a3d0-154">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="6a3d0-154">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="6a3d0-155">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6a3d0-155">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
