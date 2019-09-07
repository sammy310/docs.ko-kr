---
title: '쿼리 식 구문 예제: 집계 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d729120c-4c1b-4f34-bbe9-33694fca2dde
ms.openlocfilehash: 54b5ab6fc5eac6ba522a58afa3aa3c0218e86bcf
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70397191"
---
# <a name="query-expression-syntax-examples-aggregate-operators"></a><span data-ttu-id="f962a-102">쿼리 식 구문 예제: 집계 연산자</span><span class="sxs-lookup"><span data-stu-id="f962a-102">Query Expression Syntax Examples: Aggregate Operators</span></span>
<span data-ttu-id="f962a-103">이 항목의 예제에서는 쿼리 식 구문을 사용 하 <xref:System.Linq.Enumerable.Average%2A>여 <xref:System.Linq.Enumerable.Count%2A> [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 <xref:System.Linq.Enumerable.Sum%2A> 쿼리 하는 <xref:System.Linq.Enumerable.Max%2A>,,, <xref:System.Linq.Enumerable.Min%2A>및 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Count%2A>, <xref:System.Linq.Enumerable.Max%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Sum%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="f962a-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="f962a-105">이 항목의 예제에서는 다음 `using` / `Imports` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="average"></a><span data-ttu-id="f962a-106">평균</span><span class="sxs-lookup"><span data-stu-id="f962a-106">Average</span></span>  
  
### <a name="example"></a><span data-ttu-id="f962a-107">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-107">Example</span></span>  
 <span data-ttu-id="f962a-108">다음 예제에서는 <xref:System.Linq.Enumerable.Average%2A> 메서드를 사용하여 각 스타일의 평균 제품 가격을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-108">The following example uses the <xref:System.Linq.Enumerable.Average%2A> method to find the average list price of the products of each style.</span></span>  
  
 [!code-csharp[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#average2_mq)]
 [!code-vb[DP L2E Examples#Average2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#average2_mq)]  
  
### <a name="example"></a><span data-ttu-id="f962a-109">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-109">Example</span></span>  
 <span data-ttu-id="f962a-110">다음 예제에서는 <xref:System.Linq.Enumerable.Average%2A>를 사용하여 각 연락처 ID의 평균 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-110">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the average total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averagegrouped_mq)]
 [!code-vb[DP L2E Examples#AverageGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averagegrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="f962a-111">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-111">Example</span></span>  
 <span data-ttu-id="f962a-112">다음 예제에서는 <xref:System.Linq.Enumerable.Average%2A>를 사용하여 각 연락처에서 평균 합계 값을 가지는 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-112">The following example uses <xref:System.Linq.Enumerable.Average%2A> to get the orders with the average total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#averageelements_mq)]
 [!code-vb[DP L2E Examples#AverageElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#averageelements_mq)]  
  
## <a name="count"></a><span data-ttu-id="f962a-113">개수</span><span class="sxs-lookup"><span data-stu-id="f962a-113">Count</span></span>  
  
### <a name="example"></a><span data-ttu-id="f962a-114">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-114">Example</span></span>  
 <span data-ttu-id="f962a-115">다음 예제에서는 <xref:System.Linq.Enumerable.Count%2A>를 사용하여 연락처 ID의 목록과 각 연락처의 주문 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-115">The following example uses <xref:System.Linq.Enumerable.Count%2A> to return a list of contact IDs and how many orders each has.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countnested)]
 [!code-vb[DP L2E Examples#CountNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countnested)]  
  
### <a name="example"></a><span data-ttu-id="f962a-116">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-116">Example</span></span>  
 <span data-ttu-id="f962a-117">다음 예제에서는 색으로 제품을 그룹화한 다음 <xref:System.Linq.Enumerable.Count%2A>를 사용하여 각 색 그룹의 제품 수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-117">The following example groups products by color and uses <xref:System.Linq.Enumerable.Count%2A> to return the number of products in each color group.</span></span>  
  
 [!code-csharp[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#countgrouped)]
 [!code-vb[DP L2E Examples#CountGrouped](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#countgrouped)]  
  
## <a name="max"></a><span data-ttu-id="f962a-118">최대</span><span class="sxs-lookup"><span data-stu-id="f962a-118">Max</span></span>  
  
### <a name="example"></a><span data-ttu-id="f962a-119">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-119">Example</span></span>  
 <span data-ttu-id="f962a-120">다음 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID의 최대 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-120">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxgrouped_mq)]
 [!code-vb[DP L2E Examples#MaxGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxgrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="f962a-121">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-121">Example</span></span>  
 <span data-ttu-id="f962a-122">다음 예제에서는 <xref:System.Linq.Enumerable.Max%2A> 메서드를 사용하여 각 연락처 ID에서 최대 합계 값을 가지는 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-122">The following example uses the <xref:System.Linq.Enumerable.Max%2A> method to get the orders with the largest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#maxelements_mq)]
 [!code-vb[DP L2E Examples#MaxElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#maxelements_mq)]  
  
## <a name="min"></a><span data-ttu-id="f962a-123">최소</span><span class="sxs-lookup"><span data-stu-id="f962a-123">Min</span></span>  
  
### <a name="example"></a><span data-ttu-id="f962a-124">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-124">Example</span></span>  
 <span data-ttu-id="f962a-125">다음 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처 ID의 최소 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-125">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the smallest total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#mingrouped_mq)]
 [!code-vb[DP L2E Examples#MinGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#mingrouped_mq)]  
  
### <a name="example"></a><span data-ttu-id="f962a-126">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-126">Example</span></span>  
 <span data-ttu-id="f962a-127">다음 예제에서는 <xref:System.Linq.Enumerable.Min%2A> 메서드를 사용하여 각 연락처에서 최소 합계 값을 가지는 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-127">The following example uses the <xref:System.Linq.Enumerable.Min%2A> method to get the orders with the smallest total due for each contact.</span></span>  
  
 [!code-csharp[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#minelements_mq)]
 [!code-vb[DP L2E Examples#MinElements_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#minelements_mq)]  
  
## <a name="sum"></a><span data-ttu-id="f962a-128">Sum</span><span class="sxs-lookup"><span data-stu-id="f962a-128">Sum</span></span>  
  
### <a name="example"></a><span data-ttu-id="f962a-129">예제</span><span class="sxs-lookup"><span data-stu-id="f962a-129">Example</span></span>  
 <span data-ttu-id="f962a-130">다음 예제에서는 <xref:System.Linq.Enumerable.Sum%2A> 메서드를 사용하여 각 연락처 ID의 합계를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f962a-130">The following example uses the <xref:System.Linq.Enumerable.Sum%2A> method to get the total due for each contact ID.</span></span>  
  
 [!code-csharp[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#sumgrouped_mq)]
 [!code-vb[DP L2E Examples#SumGrouped_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#sumgrouped_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="f962a-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="f962a-131">See also</span></span>

- [<span data-ttu-id="f962a-132">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="f962a-132">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
