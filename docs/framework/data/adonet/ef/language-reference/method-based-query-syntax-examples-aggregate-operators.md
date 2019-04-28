---
title: '메서드 기반 쿼리 구문 예제: 집계 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 0e306067-5720-4782-9719-2286570a7e47
ms.openlocfilehash: 06609ce14edeb7e9306816b8a8d58d2212b61751
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760612"
---
# <a name="method-based-query-syntax-examples-aggregate-operators"></a><span data-ttu-id="91164-102">메서드 기반 쿼리 구문 예제: 집계 연산자</span><span class="sxs-lookup"><span data-stu-id="91164-102">Method-Based Query Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="91164-103">이 항목의 예제에 사용 하는 방법을 보여 줍니다 합니다 <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>를 <xref:System.Linq.Enumerable.Min%2A>, 및 <xref:System.Linq.Enumerable.Sum%2A> 쿼리 하는 메서드는 [AdventureWorks Sales 모델](https://archive.codeplex.com/?p=msftdbprodsamples) 메서드 기반 쿼리 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="91164-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Aggregate%2A>, <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.LongCount%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using method-based query syntax.</span></span> <span data-ttu-id="91164-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="91164-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="91164-105">이 항목의 예제에서는 다음을 사용 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="91164-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="91164-106">평균</span><span class="sxs-lookup"><span data-stu-id="91164-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="91164-107">예제</span><span class="sxs-lookup"><span data-stu-id="91164-107">Example</span></span>  
 <span data-ttu-id="91164-108">다음 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 제품의 평균 가격을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="91164-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average_mq)]
 [!code-vb[DP L2E Examples#Average_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average_mq)]  
  
### <a name="example"></a><span data-ttu-id="91164-109">예제</span><span class="sxs-lookup"><span data-stu-id="91164-109">Example</span></span>  
 <span data-ttu-id="91164-110">다음 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 스타일의 평균 제품 가격을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="91164-110">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="91164-111">예제</span><span class="sxs-lookup"><span data-stu-id="91164-111">Example</span></span>  
 <span data-ttu-id="91164-112">다음 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 평균 합계를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="91164-112">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageprojection_mq)]
 [!code-vb[DP L2E Examples#AverageProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="91164-113">예제</span><span class="sxs-lookup"><span data-stu-id="91164-113">Example</span></span>  
 <span data-ttu-id="91164-114">다음 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 연락처 ID의 평균 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-114">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="91164-115">예제</span><span class="sxs-lookup"><span data-stu-id="91164-115">Example</span></span>  
 <span data-ttu-id="91164-116">다음 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 연락처에 대해 평균 합계를 가진 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-116">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="91164-117">개수</span><span class="sxs-lookup"><span data-stu-id="91164-117">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="91164-118">예제</span><span class="sxs-lookup"><span data-stu-id="91164-118">Example</span></span>  
 <span data-ttu-id="91164-119">다음 예제에서는 <xref:System.Linq.Enumerable.Count%2A> 메서드를 사용하여 Product 테이블에 있는 제품 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="91164-119">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in the Product table.</span></span>  
  
 [!code-csharp[DP L2E Examples#Count](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#count)]
 [!code-vb[DP L2E Examples#Count](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#count)]  
  
### <a name="example"></a><span data-ttu-id="91164-120">예제</span><span class="sxs-lookup"><span data-stu-id="91164-120">Example</span></span>  
 <span data-ttu-id="91164-121">다음 예제에서는 <xref:System.Linq.Enumerable.Count%2A> 메서드를 사용하여 연락처 ID와 각 연락처의 주문 수로 구성된 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="91164-121">The following example uses the <xref:System.Linq.Enumerable.Count%2A> method to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="91164-122">예제</span><span class="sxs-lookup"><span data-stu-id="91164-122">Example</span></span>  
 <span data-ttu-id="91164-123">다음 예제에서는 색으로 제품을 그룹화한 다음 <xref:System.Linq.Enumerable.Count%2A> 메서드를 사용하여 각 색 그룹의 제품 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="91164-123">The following example groups products by color and uses the <xref:System.Linq.Enumerable.Count%2A> method to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="longcount"></a><span data-ttu-id="91164-124">LongCount</span><span class="sxs-lookup"><span data-stu-id="91164-124">LongCount</span></span>  
  
### <a name="example"></a><span data-ttu-id="91164-125">예제</span><span class="sxs-lookup"><span data-stu-id="91164-125">Example</span></span>  
 <span data-ttu-id="91164-126">다음 예제에서는 연락처 수를 정수(Long)로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-126">The following example gets the contact count as a long integer.</span></span>  
  
 [!code-csharp[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#longcountsimple)]
 [!code-vb[DP L2E Examples#LongCountSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#longcountsimple)]  
  
## <a name="max"></a><span data-ttu-id="91164-127">최대</span><span class="sxs-lookup"><span data-stu-id="91164-127">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="91164-128">예제</span><span class="sxs-lookup"><span data-stu-id="91164-128">Example</span></span>  
 <span data-ttu-id="91164-129">다음 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 최대 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-129">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxprojection_mq)]
 [!code-vb[DP L2E Examples#MaxProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="91164-130">예제</span><span class="sxs-lookup"><span data-stu-id="91164-130">Example</span></span>  
 <span data-ttu-id="91164-131">다음 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID의 최대 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-131">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="91164-132">예제</span><span class="sxs-lookup"><span data-stu-id="91164-132">Example</span></span>  
 <span data-ttu-id="91164-133">다음 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID에서 최대 합계 값을 가지는 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-133">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="91164-134">최소</span><span class="sxs-lookup"><span data-stu-id="91164-134">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="91164-135">예제</span><span class="sxs-lookup"><span data-stu-id="91164-135">Example</span></span>  
 <span data-ttu-id="91164-136">다음 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 최소 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-136">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minprojection_mq)]
 [!code-vb[DP L2E Examples#MinProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="91164-137">예제</span><span class="sxs-lookup"><span data-stu-id="91164-137">Example</span></span>  
 <span data-ttu-id="91164-138">다음 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID의 최소 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-138">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="91164-139">예제</span><span class="sxs-lookup"><span data-stu-id="91164-139">Example</span></span>  
 <span data-ttu-id="91164-140">다음 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처에서 최소 합계 값을 가지는 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-140">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="91164-141">Sum</span><span class="sxs-lookup"><span data-stu-id="91164-141">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="91164-142">예제</span><span class="sxs-lookup"><span data-stu-id="91164-142">Example</span></span>  
 <span data-ttu-id="91164-143">다음 예제에서는 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 SalesOrderDetail 테이블의 전체 주문 수량을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-143">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total number of order quantities in the SalesOrderDetail table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumprojection_mq)]
 [!code-vb[DP L2E Examples#SumProjection_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumprojection_mq)]  
  
### <a name="example"></a><span data-ttu-id="91164-144">예제</span><span class="sxs-lookup"><span data-stu-id="91164-144">Example</span></span>  
 <span data-ttu-id="91164-145">다음 예제에서는 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 각 연락처 ID의 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="91164-145">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="91164-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="91164-146">See also</span></span>

- [<span data-ttu-id="91164-147">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="91164-147">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
