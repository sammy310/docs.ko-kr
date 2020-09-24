---
title: '쿼리 식 구문 예제: 순서 지정'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: bcbc9625-7cf7-476e-85d2-058f12682f54
ms.openlocfilehash: ed03fc248ed48f56998bc27f7e880b1e8aa443d2
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156786"
---
# <a name="query-expression-syntax-examples-ordering"></a><span data-ttu-id="93812-102">쿼리 식 구문 예제: 순서 지정</span><span class="sxs-lookup"><span data-stu-id="93812-102">Query Expression Syntax Examples: Ordering</span></span>

<span data-ttu-id="93812-103">이 항목의 예제에서는 `OrderBy` `OrderByDescending` 쿼리 식 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하기 위해 및 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="93812-103">The examples in this topic demonstrate how to use the `OrderBy` and `OrderByDescending` methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="93812-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="93812-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="93812-105">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="93812-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="orderby"></a><span data-ttu-id="93812-106">OrderBy</span><span class="sxs-lookup"><span data-stu-id="93812-106">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="93812-107">예제</span><span class="sxs-lookup"><span data-stu-id="93812-107">Example</span></span>  

 <span data-ttu-id="93812-108">다음 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>를 사용하여 성을 기준으로 정렬된 연락처 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="93812-108">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to return a list of contacts ordered by last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple1)]
 [!code-vb[DP L2E Examples#OrderBySimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple1)]  
  
### <a name="example"></a><span data-ttu-id="93812-109">예제</span><span class="sxs-lookup"><span data-stu-id="93812-109">Example</span></span>  

 <span data-ttu-id="93812-110">다음 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>를 사용하여 성의 길이를 기준으로 연락처 목록을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="93812-110">The following example uses <xref:System.Linq.Enumerable.OrderBy%2A> to sort a list of contacts by length of last name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbysimple2)]
 [!code-vb[DP L2E Examples#OrderBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbysimple2)]  
  
## <a name="orderbydescending"></a><span data-ttu-id="93812-111">OrderByDescending</span><span class="sxs-lookup"><span data-stu-id="93812-111">OrderByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="93812-112">예제</span><span class="sxs-lookup"><span data-stu-id="93812-112">Example</span></span>  

 <span data-ttu-id="93812-113">다음 예제에서는 `orderby… descending` 메서드와 같은 `Order By … Descending`(Visual Basic에서는 <xref:System.Linq.Enumerable.OrderByDescending%2A>)을 사용하여 가격 목록을 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="93812-113">The following example uses `orderby… descending` (`Order By … Descending` in Visual Basic), which is equivalent to the <xref:System.Linq.Enumerable.OrderByDescending%2A> method, to sort the price list from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbydescendingsimple1)]
 [!code-vb[DP L2E Examples#OrderByDescendingSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbydescendingsimple1)]  
  
## <a name="thenby"></a><span data-ttu-id="93812-114">ThenBy</span><span class="sxs-lookup"><span data-stu-id="93812-114">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="93812-115">예제</span><span class="sxs-lookup"><span data-stu-id="93812-115">Example</span></span>  

 <span data-ttu-id="93812-116">다음 예제에서는 <xref:System.Linq.Queryable.OrderBy%2A> 및 <xref:System.Linq.Queryable.ThenBy%2A>를 사용하여 성을 기준으로 정렬한 다음 이름을 기준으로 다시 정렬한 연락처 목록을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="93812-116">The following example uses <xref:System.Linq.Queryable.OrderBy%2A> and <xref:System.Linq.Queryable.ThenBy%2A> to return a list of contacts ordered by last name and then by first name.</span></span>  
  
 [!code-csharp[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#orderbythenby)]
 [!code-vb[DP L2E Examples#OrderByThenBy](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#orderbythenby)]  
  
## <a name="thenbydescending"></a><span data-ttu-id="93812-117">ThenByDescending</span><span class="sxs-lookup"><span data-stu-id="93812-117">ThenByDescending</span></span>  
  
### <a name="example"></a><span data-ttu-id="93812-118">예제</span><span class="sxs-lookup"><span data-stu-id="93812-118">Example</span></span>  

 <span data-ttu-id="93812-119">다음 예제에서는 `OrderBy… Descending` 메서드와 같은 <xref:System.Linq.Enumerable.ThenByDescending%2A>을 사용하여 이름과 가격을 각각 1차 및 2차 정렬 기준으로 삼아 내림차순으로 제품 목록을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="93812-119">The following example uses `OrderBy… Descending`, which is equivalent to the <xref:System.Linq.Enumerable.ThenByDescending%2A> method, to sort a list of products, first by name and then by list price from highest to lowest.</span></span>  
  
 [!code-csharp[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#thenbydescendingsimple)]
 [!code-vb[DP L2E Examples#ThenByDescendingSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#thenbydescendingsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="93812-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93812-120">See also</span></span>

- [<span data-ttu-id="93812-121">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="93812-121">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
