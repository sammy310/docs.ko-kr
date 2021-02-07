---
description: '자세한 정보: Method-Based 쿼리 구문 예제: 집계 연산자 (LINQ to DataSet)'
title: '메서드 기반 쿼리 구문 예제: 집계 연산자(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5ed5f01d-acb2-4dd4-be60-f04c2d570fa8
ms.openlocfilehash: a404cde84266d4ef8c2118dd07644b28417e159a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681606"
---
# <a name="method-based-query-syntax-examples-aggregate-operators-linq-to-dataset"></a><span data-ttu-id="6cecb-103">메서드 기반 쿼리 구문 예제: 집계 연산자(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="6cecb-103">Method-Based Query Syntax Examples: Aggregate Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="6cecb-104">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Sum%2A> 연산자에서 메서드 쿼리 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하고 데이터를 집계하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> operators to query a <xref:System.Data.DataSet> and aggregate data using method query syntax.</span></span>  
  
 <span data-ttu-id="6cecb-105">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드](loading-data-into-a-dataset.md)하는데 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-105">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="6cecb-106">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-106">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6cecb-107">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="6cecb-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="6cecb-108">자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](how-to-create-a-linq-to-dataset-project-in-vs.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6cecb-108">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="aggregate"></a><span data-ttu-id="6cecb-109">집계</span><span class="sxs-lookup"><span data-stu-id="6cecb-109">Aggregate</span></span>  
  
### <a name="example"></a><span data-ttu-id="6cecb-110">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-110">Example</span></span>  

 <span data-ttu-id="6cecb-111">이 예제에서는 <xref:System.Linq.Enumerable.Aggregate%2A> 메서드를 사용하여 `Contact` 테이블에서 맨 위쪽에 있는 5개의 연락처 정보를 가져온 다음 쉼표로 구분된 성 목록을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-111">This example uses the <xref:System.Linq.Enumerable.Aggregate%2A> method to get the first 5 contacts from the `Contact` table and build a comma-delimited list of the last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#aggregate_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Aggregate_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#aggregate_mq)]  
  
## <a name="average"></a><span data-ttu-id="6cecb-112">평균</span><span class="sxs-lookup"><span data-stu-id="6cecb-112">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="6cecb-113">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-113">Example</span></span>  

 <span data-ttu-id="6cecb-114">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 제품의 평균 가격을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-114">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-115">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-115">Example</span></span>  

 <span data-ttu-id="6cecb-116">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 스타일의 평균 제품 가격을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-116">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP LINQ to DataSet Examples#Average2_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-117">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-117">Example</span></span>  

 <span data-ttu-id="6cecb-118">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 평균 합계를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-118">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-119">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-119">Example</span></span>  

 <span data-ttu-id="6cecb-120">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 연락처 ID의 평균 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-120">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-121">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-121">Example</span></span>  

 <span data-ttu-id="6cecb-122">이 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 연락처에 대해 평균 `TotalDue`를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-122">This example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average `TotalDue` for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#AverageElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="6cecb-123">개수</span><span class="sxs-lookup"><span data-stu-id="6cecb-123">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="6cecb-124">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-124">Example</span></span>  

 <span data-ttu-id="6cecb-125">이 예제에서는 <xref:System.Linq.Enumerable.Count%2A> 메서드를 사용하여 `Product` 테이블에 있는 제품 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-125">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the `Product` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#count)]
 [!code-vb[DP LINQ to DataSet Examples#Count](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-126">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-126">Example</span></span>  

 <span data-ttu-id="6cecb-127">이 예제에서는 <xref:System.Linq.Enumerable.Count%2A> 메서드를 사용하여 연락처 ID와 각 연락처의 주문 수로 구성된 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-127">This example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countnested)]
 [!code-vb[DP LINQ to DataSet Examples#CountNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-128">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-128">Example</span></span>  

 <span data-ttu-id="6cecb-129">이 예제에서는 색으로 제품을 그룹화한 다음 <xref:System.Linq.Enumerable.Count%2A> 메서드를 사용하여 각 색 그룹의 제품 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-129">This example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP LINQ to DataSet Examples#CountGrouped](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="6cecb-130">LongCount</span><span class="sxs-lookup"><span data-stu-id="6cecb-130">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="6cecb-131">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-131">Example</span></span>  

 <span data-ttu-id="6cecb-132">이 예제에서는 연락처 수를 정수(Long)로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-132">This example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP LINQ to DataSet Examples#LongCountSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="6cecb-133">Max</span><span class="sxs-lookup"><span data-stu-id="6cecb-133">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="6cecb-134">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-134">Example</span></span>  

 <span data-ttu-id="6cecb-135">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 최대 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-135">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-136">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-136">Example</span></span>  

 <span data-ttu-id="6cecb-137">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID의 최대 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-137">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-138">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-138">Example</span></span>  

 <span data-ttu-id="6cecb-139">이 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID에 대해 최대 `TotalDue`를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-139">This example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest `TotalDue` for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MaxElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="6cecb-140">최소값</span><span class="sxs-lookup"><span data-stu-id="6cecb-140">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="6cecb-141">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-141">Example</span></span>  

 <span data-ttu-id="6cecb-142">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 최소 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-142">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinProjection_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-143">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-143">Example</span></span>  

 <span data-ttu-id="6cecb-144">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID의 최소 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-144">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-145">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-145">Example</span></span>  

 <span data-ttu-id="6cecb-146">이 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID에 대해 최소 합계를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-146">This example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP LINQ to DataSet Examples#MinElements_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="6cecb-147">합계</span><span class="sxs-lookup"><span data-stu-id="6cecb-147">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="6cecb-148">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-148">Example</span></span>  

 <span data-ttu-id="6cecb-149">이 예제에서는 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 `SalesOrderDetail` 테이블의 전체 주문 수량을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-149">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the `SalesOrderDetail` table.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumProjection_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="6cecb-150">예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-150">Example</span></span>  

 <span data-ttu-id="6cecb-151">이 예제에서는 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 각 연락처 ID의 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6cecb-151">This example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP LINQ to DataSet Examples#SumGrouped_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="6cecb-152">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cecb-152">See also</span></span>

- [<span data-ttu-id="6cecb-153">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="6cecb-153">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="6cecb-154">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="6cecb-154">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="6cecb-155">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="6cecb-155">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="6cecb-156">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6cecb-156">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
