---
title: '쿼리 식 구문 예제: 조인 연산자 (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: f4d86667-3392-470d-a076-5ca6cbb660f6
ms.openlocfilehash: c150cb14c567590daa7ffb2ea77893598977bdf9
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70794865"
---
# <a name="query-expression-syntax-examples-join-operators-linq-to-dataset"></a><span data-ttu-id="0a12a-102">쿼리 식 구문 예제: 조인 연산자 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="0a12a-102">Query Expression Syntax Examples: Join Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="0a12a-103">조인은 관계형 데이터베이스 테이블과 같이 서로 탐색할 수 없는 관계를 가진 데이터 소스를 대상으로 하는 쿼리에 사용되는 중요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="0a12a-104">두 데이터 소스를 조인하는 것은 한 데이터 소스의 개체를 공통 특성을 공유하는 다른 데이터 소스의 개체와 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="0a12a-105">자세한 내용은 [표준 쿼리 연산자 개요 (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) 또는 [표준 쿼리 연산자 개요 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a12a-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="0a12a-106">이 항목의 예제에서는 <xref:System.Linq.Enumerable.GroupJoin%2A> 및 <xref:System.Linq.Enumerable.Join%2A> 메서드에서 쿼리 식 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.GroupJoin%2A> and <xref:System.Linq.Enumerable.Join%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="0a12a-107">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드](loading-data-into-a-dataset.md)하는데 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="0a12a-108">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="0a12a-109">이 항목의 예제에서는 다음 `using` / `Imports` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="0a12a-110">자세한 내용은 [방법: Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)에서 LINQ to DataSet 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="groupjoin"></a><span data-ttu-id="0a12a-111">GroupJoin</span><span class="sxs-lookup"><span data-stu-id="0a12a-111">GroupJoin</span></span>  
  
### <a name="example"></a><span data-ttu-id="0a12a-112">예제</span><span class="sxs-lookup"><span data-stu-id="0a12a-112">Example</span></span>  
 <span data-ttu-id="0a12a-113">이 예제에서는 <xref:System.Linq.Enumerable.GroupJoin%2A> 및 `SalesOrderHeader` 테이블에 대해 `SalesOrderDetail`을 수행하여 고객별 주문 수를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-113">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `SalesOrderHeader` and `SalesOrderDetail` tables to find the number of orders per customer.</span></span> <span data-ttu-id="0a12a-114">그룹 조인은 다른 데이터 소스에 관계가 있는 요소가 없더라도 첫 번째(왼쪽) 데이터 소스의 각 요소를 반환하는 왼쪽 우선 외부 조인과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-114">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin2)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin2)]  
  
### <a name="example"></a><span data-ttu-id="0a12a-115">예제</span><span class="sxs-lookup"><span data-stu-id="0a12a-115">Example</span></span>  
 <span data-ttu-id="0a12a-116">이 예제에서는 <xref:System.Linq.Enumerable.GroupJoin%2A> 및 `Contact` 테이블에 대해 `SalesOrderHeader`을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-116">This example performs a <xref:System.Linq.Enumerable.GroupJoin%2A> over the `Contact` and `SalesOrderHeader` tables.</span></span> <span data-ttu-id="0a12a-117">그룹 조인은 다른 데이터 소스에 관계가 있는 요소가 없더라도 첫 번째(왼쪽) 데이터 소스의 각 요소를 반환하는 왼쪽 우선 외부 조인과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-117">A group join is the equivalent of a left outer join, which returns each element of the first (left) data source, even if no correlated elements are in the other data source.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#groupjoin)]
 [!code-vb[DP LINQ to DataSet Examples#GroupJoin](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#groupjoin)]  
  
## <a name="join"></a><span data-ttu-id="0a12a-118">Join</span><span class="sxs-lookup"><span data-stu-id="0a12a-118">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="0a12a-119">예제</span><span class="sxs-lookup"><span data-stu-id="0a12a-119">Example</span></span>  
 <span data-ttu-id="0a12a-120">이 예제에서는 `SalesOrderHeader` 및 `SalesOrderDetail` 테이블에 대해 조인을 수행하여 8월의 온라인 주문을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="0a12a-120">This example performs a join over the `SalesOrderHeader` and `SalesOrderDetail` tables to get online orders from the month of August.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#join)]
 [!code-vb[DP LINQ to DataSet Examples#Join](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#join)]  
  
## <a name="see-also"></a><span data-ttu-id="0a12a-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="0a12a-121">See also</span></span>

- [<span data-ttu-id="0a12a-122">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="0a12a-122">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="0a12a-123">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="0a12a-123">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="0a12a-124">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="0a12a-124">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="0a12a-125">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="0a12a-125">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
