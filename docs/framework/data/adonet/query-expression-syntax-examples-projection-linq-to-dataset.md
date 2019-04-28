---
title: '쿼리 식 구문 예제: 프로젝션 (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 48c9f5ed-76bf-4228-ab10-5217bbb295a3
ms.openlocfilehash: 3bd7934cef03df391c1871b8499f911a023d7d3b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61644531"
---
# <a name="query-expression-syntax-examples-projection--linq-to-dataset"></a><span data-ttu-id="134ab-102">쿼리 식 구문 예제: 프로젝션 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="134ab-102">Query Expression Syntax Examples: Projection  (LINQ to DataSet)</span></span>
<span data-ttu-id="134ab-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 및 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드에서 쿼리 식 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="134ab-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="134ab-104">합니다 `FillDataSet` 에이 예제에서 사용 하는 방법이 지정 되어 [는 DataSet에 데이터 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="134ab-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="134ab-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="134ab-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="134ab-106">이 항목의 예제에서는 다음을 사용 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="134ab-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="134ab-107">자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="134ab-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="select"></a><span data-ttu-id="134ab-108">선택</span><span class="sxs-lookup"><span data-stu-id="134ab-108">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="134ab-109">예제</span><span class="sxs-lookup"><span data-stu-id="134ab-109">Example</span></span>  
 <span data-ttu-id="134ab-110">이 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 메서드를 사용하여 `Product` 테이블의 모든 행을 반환하고 제품 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="134ab-110">This example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple1](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="134ab-111">예제</span><span class="sxs-lookup"><span data-stu-id="134ab-111">Example</span></span>  
 <span data-ttu-id="134ab-112">이 예제에서는 <xref:System.Linq.Enumerable.Select%2A>를 사용하여 제품 이름만으로 구성된 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="134ab-112">This example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectSimple2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectsimple2)]  
  
## <a name="selectmany"></a><span data-ttu-id="134ab-113">SelectMany</span><span class="sxs-lookup"><span data-stu-id="134ab-113">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="134ab-114">예제</span><span class="sxs-lookup"><span data-stu-id="134ab-114">Example</span></span>  
 <span data-ttu-id="134ab-115">이 예제에서는 `From …, …`(<xref:System.Linq.Enumerable.SelectMany%2A> 메서드와 같음)을 사용하여 `TotalDue`가 500.00보다 작은 모든 주문을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="134ab-115">This example uses `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="134ab-116">예제</span><span class="sxs-lookup"><span data-stu-id="134ab-116">Example</span></span>  
 <span data-ttu-id="134ab-117">이 예제에서는 `From …, …`(<xref:System.Linq.Enumerable.SelectMany%2A> 메서드와 같음)을 사용하여 2002년 10월 1일 이후에 작성된 모든 주문을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="134ab-117">This example uses `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyCompoundFrom2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="134ab-118">예제</span><span class="sxs-lookup"><span data-stu-id="134ab-118">Example</span></span>  
 <span data-ttu-id="134ab-119">이 예제에서는 `From …, …`(<xref:System.Linq.Enumerable.SelectMany%2A> 메서드와 같음)을 사용하여 주문 합계가 10000.00보다 큰 모든 주문을 선택하고 `From` 할당을 사용하여 합계가 두 번 요청되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="134ab-119">This example uses a `From …, …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP LINQ to DataSet Examples#SelectManyFromAssignment](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="134ab-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="134ab-120">See also</span></span>

- [<span data-ttu-id="134ab-121">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="134ab-121">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="134ab-122">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="134ab-122">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="134ab-123">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="134ab-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="134ab-124">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="134ab-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
