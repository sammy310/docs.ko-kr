---
title: 크로스 테이블 쿼리(LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 6819a16f-8656-41af-a54d-dfec0cb66366
ms.openlocfilehash: 8f9a538482580134fa876866dfe394c3dfc7de2a
ms.sourcegitcommit: 7bc6887ab658550baa78f1520ea735838249345e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/03/2020
ms.locfileid: "75634887"
---
# <a name="cross-table-queries-linq-to-dataset"></a><span data-ttu-id="310cb-102">크로스 테이블 쿼리(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="310cb-102">Cross-Table Queries (LINQ to DataSet)</span></span>
<span data-ttu-id="310cb-103">단일 테이블을 쿼리 하는 것 외에도 LINQ to DataSet에서 테이블 간 쿼리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-103">In addition to querying a single table, you can also perform cross-table queries in LINQ to DataSet.</span></span> <span data-ttu-id="310cb-104">이 작업은 *조인을*사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-104">This is done by using a *join*.</span></span> <span data-ttu-id="310cb-105">조인은 한 데이터 소스의 개체를 공통 특성(예: 제품 또는 연락처 ID)을 공유하는 다른 데이터 소스의 개체와 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-105">A join is the association of objects in one data source with objects that share a common attribute in another data source, such as a product or contact ID.</span></span> <span data-ttu-id="310cb-106">개체 지향적 프로그래밍의 경우 각 개체에 다른 개체를 참조하는 멤버가 있으므로 개체 간의 관계를 탐색하기가 비교적 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-106">In object-oriented programming, relationships between objects are relatively easy to navigate because each object has a member that references another object.</span></span> <span data-ttu-id="310cb-107">그러나 외부 데이터베이스 테이블에서는 관계를 탐색하기가 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-107">In external database tables, however, navigating relationships is not as straightforward.</span></span> <span data-ttu-id="310cb-108">데이터베이스 테이블에는 기본 제공 관계가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-108">Database tables do not contain built-in relationships.</span></span> <span data-ttu-id="310cb-109">이러한 경우 조인 연산을 사용하여 각 소스의 요소를 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-109">In these cases, the join operation can be used to match elements from each source.</span></span> <span data-ttu-id="310cb-110">예를 들어 제품 정보와 판매 정보가 들어 있는 두 테이블이 있는 경우 조인 연산을 사용하여 동일한 판매 주문에 대한 판매 정보와 제품을 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-110">For example, given two tables that contain product information and sales information, you could use a join operation to match sales information and products for the same sales order.</span></span>  
  
 <span data-ttu-id="310cb-111">LINQ (통합 언어 쿼리) 프레임 워크는 <xref:System.Linq.Enumerable.Join%2A> 및 <xref:System.Linq.Enumerable.GroupJoin%2A>의 두 조인 연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-111">The Language-Integrated Query (LINQ) framework provides two join operators, <xref:System.Linq.Enumerable.Join%2A> and <xref:System.Linq.Enumerable.GroupJoin%2A>.</span></span> <span data-ttu-id="310cb-112">이러한 연산자는 키가 같은 경우에만 두 데이터 소스와 일치 하는 조인 인 *동등 조인을*수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-112">These operators perform *equi-joins*: that is, joins that match two data sources only when their keys are equal.</span></span> <span data-ttu-id="310cb-113">이와 반대로 Transact-sql은 `less than` 연산자와 같이 `equals`아닌 조인 연산자를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-113">(By contrast, Transact-SQL supports join operators other than `equals`, such as the `less than` operator.)</span></span>  
  
 <span data-ttu-id="310cb-114">관계형 데이터베이스 용어에서 <xref:System.Linq.Enumerable.Join%2A>은 내부 조인을 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-114">In relational database terms, <xref:System.Linq.Enumerable.Join%2A> implements an inner join.</span></span> <span data-ttu-id="310cb-115">내부 조인은 상대 데이터 집합에 일치하는 항목이 있는 개체만 반환되는 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-115">An inner join is a type of join in which only those objects that have a match in the opposite data set are returned.</span></span>  
  
 <span data-ttu-id="310cb-116"><xref:System.Linq.Enumerable.GroupJoin%2A> 연산자에는 관계형 데이터베이스 측면에 직접 상응 하는 기능이 없습니다. 내부 조인 및 왼쪽 우선 외부 조인의 상위 집합을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-116">The <xref:System.Linq.Enumerable.GroupJoin%2A> operators have no direct equivalent in relational database terms; they implement a superset of inner joins and left outer joins.</span></span> <span data-ttu-id="310cb-117">왼쪽 우선 외부 조인은 두 번째 컬렉션에 상관 관계가 지정 된 요소가 없더라도 첫 번째 (왼쪽) 컬렉션의 각 요소를 반환 하는 조인입니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-117">A left outer join is a join that returns each element of the first (left) collection, even if it has no correlated elements in the second collection.</span></span>  
  
 <span data-ttu-id="310cb-118">조인에 대 한 자세한 내용은 [조인 작업](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="310cb-118">For more information about joins, see [Join Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120)).</span></span>  
  
## <a name="example"></a><span data-ttu-id="310cb-119">예</span><span class="sxs-lookup"><span data-stu-id="310cb-119">Example</span></span>  
 <span data-ttu-id="310cb-120">다음 예제에서는 AdventureWorks 샘플 데이터베이스의 `SalesOrderHeader` 및 `SalesOrderDetail` 테이블에 대해 기존 방식의 조인을 수행하여 8월의 온라인 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="310cb-120">The following example performs a traditional join of the `SalesOrderHeader` and `SalesOrderDetail` tables from the AdventureWorks sample database to obtain online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="310cb-121">참조</span><span class="sxs-lookup"><span data-stu-id="310cb-121">See also</span></span>

- [<span data-ttu-id="310cb-122">데이터 세트 쿼리</span><span class="sxs-lookup"><span data-stu-id="310cb-122">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="310cb-123">단일 테이블 쿼리</span><span class="sxs-lookup"><span data-stu-id="310cb-123">Single-Table Queries</span></span>](single-table-queries-linq-to-dataset.md)
- [<span data-ttu-id="310cb-124">형식화된 데이터 세트 쿼리</span><span class="sxs-lookup"><span data-stu-id="310cb-124">Querying Typed DataSets</span></span>](querying-typed-datasets.md)
- <span data-ttu-id="310cb-125">[조인 작업](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))</span><span class="sxs-lookup"><span data-stu-id="310cb-125">[Join Operations](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/bb397908(v=vs.120))</span></span>
- [<span data-ttu-id="310cb-126">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="310cb-126">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
