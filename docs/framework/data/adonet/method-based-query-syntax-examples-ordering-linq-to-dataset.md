---
description: '자세한 정보: Method-Based 쿼리 구문 예제: 정렬 (LINQ to DataSet)'
title: '메서드 기반 쿼리 구문 예제: 정렬(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8f9ce4fd-e84f-48c0-bb64-89e217236d3e
ms.openlocfilehash: d655ff52fe30a9af15245a4c9989062107bb6842
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99672662"
---
# <a name="method-based-query-syntax-examples-ordering-linq-to-dataset"></a><span data-ttu-id="55051-103">메서드 기반 쿼리 구문 예제: 정렬(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="55051-103">Method-Based Query Syntax Examples: Ordering (LINQ to DataSet)</span></span>

<span data-ttu-id="55051-104">이 항목의 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A>, <xref:System.Linq.Enumerable.Reverse%2A> 및 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드에서 메서드 쿼리 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하고 결과를 정렬하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="55051-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.OrderBy%2A>,  <xref:System.Linq.Enumerable.Reverse%2A>, and <xref:System.Linq.Enumerable.ThenBy%2A> methods to query a <xref:System.Data.DataSet> and order the results using the method query syntax.</span></span>  
  
 <span data-ttu-id="55051-105">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드](loading-data-into-a-dataset.md)하는데 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="55051-105">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="55051-106">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="55051-106">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="55051-107">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="55051-107">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="55051-108">자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](how-to-create-a-linq-to-dataset-project-in-vs.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="55051-108">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="orderby"></a><span data-ttu-id="55051-109">OrderBy</span><span class="sxs-lookup"><span data-stu-id="55051-109">OrderBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="55051-110">예제</span><span class="sxs-lookup"><span data-stu-id="55051-110">Example</span></span>  

 <span data-ttu-id="55051-111">이 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A> 메서드를 사용자 지정 비교자와 함께 사용하여 대소문자 구분 없이 성을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="55051-111">This example uses the <xref:System.Linq.Enumerable.OrderBy%2A> method with a custom comparer to do a case-insensitive sort of last names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#orderbycomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#OrderByComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#orderbycomparer_mq)]  
  
## <a name="reverse"></a><span data-ttu-id="55051-112">Reverse</span><span class="sxs-lookup"><span data-stu-id="55051-112">Reverse</span></span>  
  
### <a name="example"></a><span data-ttu-id="55051-113">예제</span><span class="sxs-lookup"><span data-stu-id="55051-113">Example</span></span>  

 <span data-ttu-id="55051-114">이 예제에서는 <xref:System.Linq.Enumerable.Reverse%2A> 메서드를 사용하여 `OrderDate`가 2002년 2월 20일 이전인 주문 목록을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="55051-114">This example uses the <xref:System.Linq.Enumerable.Reverse%2A> method to create a list of orders where `OrderDate` is earlier than Feb 20, 2002.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#reverse)]
 [!code-vb[DP LINQ to DataSet Examples#Reverse](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#reverse)]  
  
## <a name="thenby"></a><span data-ttu-id="55051-115">ThenBy</span><span class="sxs-lookup"><span data-stu-id="55051-115">ThenBy</span></span>  
  
### <a name="example"></a><span data-ttu-id="55051-116">예제</span><span class="sxs-lookup"><span data-stu-id="55051-116">Example</span></span>  

 <span data-ttu-id="55051-117">이 예제에서는 <xref:System.Linq.Enumerable.OrderBy%2A> 및 <xref:System.Linq.Enumerable.ThenBy%2A> 메서드를 사용자 지정 비교자와 함께 사용하여 먼저 가격을 기준으로 정렬한 다음 대소문자 구분 없이 제품 이름을 내림차순으로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="55051-117">This example uses <xref:System.Linq.Enumerable.OrderBy%2A> and <xref:System.Linq.Enumerable.ThenBy%2A> methods with a custom comparer to first sort by list price, and then perform a case-insensitive descending sort of the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#thenbydescendingcomparer_mq)]
 [!code-vb[DP LINQ to DataSet Examples#ThenByDescendingComparer_MQ](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#thenbydescendingcomparer_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="55051-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55051-118">See also</span></span>

- [<span data-ttu-id="55051-119">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="55051-119">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="55051-120">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="55051-120">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="55051-121">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="55051-121">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="55051-122">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="55051-122">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
