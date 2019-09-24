---
title: '메서드 기반 쿼리 구문 예제: 조인 (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 4fd5ed2c-b03a-4054-a3ed-3ddb380d7d9d
ms.openlocfilehash: ba6e33f98e063aab946db27b97106272c5adef63
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70783666"
---
# <a name="method-based-query-syntax-examples-join-linq-to-dataset"></a><span data-ttu-id="25deb-102">메서드 기반 쿼리 구문 예제: 조인 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="25deb-102">Method-Based Query Syntax Examples: Join (LINQ to DataSet)</span></span>
<span data-ttu-id="25deb-103">조인은 관계형 데이터베이스 테이블과 같이 서로 탐색할 수 없는 관계를 가진 데이터 소스를 대상으로 하는 쿼리에 사용되는 중요한 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-103">Joining is an important operation in queries that target data sources that have no navigable relationships to each other, such as relational database tables.</span></span> <span data-ttu-id="25deb-104">두 데이터 소스를 조인하는 것은 한 데이터 소스의 개체를 공통 특성을 공유하는 다른 데이터 소스의 개체와 연결하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-104">A join of two data sources is the association of objects in one data source with objects that share a common attribute in the other data source.</span></span> <span data-ttu-id="25deb-105">자세한 내용은 [표준 쿼리 연산자 개요 (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) 또는 [표준 쿼리 연산자 개요 (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25deb-105">For more information, see [Standard Query Operators Overview (C#)](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md) or [Standard Query Operators Overview (Visual Basic)](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md).</span></span>  
  
 <span data-ttu-id="25deb-106">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Join%2A> 메서드에서 메서드 쿼리 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-106">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Join%2A> method to query a <xref:System.Data.DataSet> using the method query syntax.</span></span>  
  
 <span data-ttu-id="25deb-107">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드](loading-data-into-a-dataset.md)하는데 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-107">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="25deb-108">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-108">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="25deb-109">이 항목의 예제에서는 다음 `using` / `Imports` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-109">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="25deb-110">자세한 내용은 [방법: Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)에서 LINQ to DataSet 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-110">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="join"></a><span data-ttu-id="25deb-111">Join</span><span class="sxs-lookup"><span data-stu-id="25deb-111">Join</span></span>  
  
### <a name="example"></a><span data-ttu-id="25deb-112">예제</span><span class="sxs-lookup"><span data-stu-id="25deb-112">Example</span></span>  
 <span data-ttu-id="25deb-113">이 예제에서는 `Contact` 및 `SalesOrderHeader` 테이블에 대한 조인을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-113">This example performs a join over the `Contact` and `SalesOrderHeader` tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinsimple_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinSimple_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinsimple_mq)]  
  
### <a name="example"></a><span data-ttu-id="25deb-114">예제</span><span class="sxs-lookup"><span data-stu-id="25deb-114">Example</span></span>  
 <span data-ttu-id="25deb-115">이 예제에서는 `Contact` 및 `SalesOrderHeader` 테이블에 대한 조인을 수행하고 연락처 ID별로 결과를 그룹화합니다.</span><span class="sxs-lookup"><span data-stu-id="25deb-115">This example performs a join over the `Contact` and `SalesOrderHeader` tables, grouping the results by contact ID.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#joinwithgroupedresults_mq)]
 [!code-vb[DP LINQ to DataSet Examples#JoinWithGroupedResults_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#joinwithgroupedresults_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="25deb-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="25deb-116">See also</span></span>

- [<span data-ttu-id="25deb-117">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="25deb-117">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="25deb-118">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="25deb-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="25deb-119">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="25deb-119">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="25deb-120">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="25deb-120">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="25deb-121">조인 샘플</span><span class="sxs-lookup"><span data-stu-id="25deb-121">Join Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=187357)
- [<span data-ttu-id="25deb-122">데이터 집합 샘플</span><span class="sxs-lookup"><span data-stu-id="25deb-122">Dataset Samples</span></span>](https://go.microsoft.com/fwlink/?LinkId=187358)
