---
title: '쿼리 식 구문 예제: 조인 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 343e8dda-70b2-409d-9334-ce9a880c3cea
ms.openlocfilehash: 422179171819f1a78a33f93545c92547830ab5fb
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90543643"
---
# <a name="query-expression-syntax-examples-join-operators"></a><span data-ttu-id="37229-102">쿼리 식 구문 예제: 조인 연산자</span><span class="sxs-lookup"><span data-stu-id="37229-102">Query Expression Syntax Examples: Join Operators</span></span>
<span data-ttu-id="37229-103">조인은 관계형 데이터베이스 테이블과 같이 서로 탐색할 수 없는 관계를 가진 데이터 소스를 대상으로 하는 쿼리에 사용되는 중요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="37229-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="37229-104">두 데이터 소스를 조인하는 것은 한 데이터 소스의 개체를 공통 특성을 공유하는 다른 데이터 소스의 개체와 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="37229-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="37229-105">자세한 내용은 [표준 쿼리 연산자 개요](/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="37229-105">For more information, see [Standard Query Operators Overview](/previous-versions/visualstudio/visual-studio-2013/bb397896(v=vs.120)).</span></span>  
  
 <span data-ttu-id="37229-106">이 항목의 예제에서는 <xref:System.Linq.Enumerable.GroupJoin%2A> <xref:System.Linq.Enumerable.Join%2A> 쿼리 식 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하기 위해 및 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="37229-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="37229-107">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="37229-107">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="37229-108">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="37229-108">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="groupjoin"></a><span data-ttu-id="37229-109">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="37229-109">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="37229-110">예제</span><span class="sxs-lookup"><span data-stu-id="37229-110">Example</span></span>  
 <span data-ttu-id="37229-111">다음 예제에서는 SalesOrderHeader 및 SalesOrderDetail 테이블에 대해 <xref:System.Linq.Enumerable.GroupJoin%2A>을 수행하여 고객별 주문 수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="37229-111">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the SalesOrderHeader and SalesOrderDetail tables to find the number of orders per customer.</span></span> <span data-ttu-id="37229-112">그룹 조인은 다른 데이터 소스에 관계가 있는 요소가 없더라도 첫 번째(왼쪽) 데이터 소스의 각 요소를 반환하는 왼쪽 우선 외부 조인과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="37229-112">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP L2E Examples#GroupJoin2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="37229-113">예제</span><span class="sxs-lookup"><span data-stu-id="37229-113">Example</span></span>  
 <span data-ttu-id="37229-114">다음 예제에서는 Contact 및 SalesOrderHeader 테이블에 대해 <xref:System.Linq.Enumerable.GroupJoin%2A>을 수행하여 연락처별 주문 수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="37229-114">The following example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the Contact and SalesOrderHeader tables to find the number of orders per contact.</span></span> <span data-ttu-id="37229-115">연락처별로 주문 횟수와 ID가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="37229-115">The order count and IDs for each contact are displayed.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP L2E Examples#GroupJoin](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="37229-116">Join</span><span class="sxs-lookup"><span data-stu-id="37229-116">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="37229-117">예제</span><span class="sxs-lookup"><span data-stu-id="37229-117">Example</span></span>  
 <span data-ttu-id="37229-118">다음 예제에서는 SalesOrderHeader 및 SalesOrderDetail 테이블에 대해 조인을 수행하여 8월의 온라인 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="37229-118">The following example performs a join over the SalesOrderHeader and SalesOrderDetail tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP L2E Examples#Join](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#join)]
 [!code-vb[DP L2E Examples#Join](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="37229-119">참조</span><span class="sxs-lookup"><span data-stu-id="37229-119">See also</span></span>

- [<span data-ttu-id="37229-120">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="37229-120">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
