---
title: '쿼리 식 구문 예제: 요소 연산자 (LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ca392dda-16e3-45c7-8d87-12d8d4ee0578
ms.openlocfilehash: 663356ec3dc39aa3eb7e858f028fc9a8f7d27db6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59132742"
---
# <a name="query-expression-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="5f37f-102">쿼리 식 구문 예제: 요소 연산자 (LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="5f37f-102">Query Expression Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="5f37f-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.First%2A> 및 <xref:System.Linq.Enumerable.ElementAt%2A> 메서드에서 쿼리 식 구문을 사용하여 <xref:System.Data.DataRow>의 <xref:System.Data.DataSet> 요소를 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5f37f-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="5f37f-104">합니다 `FillDataSet` 에이 예제에서 사용 하는 방법이 지정 되어 [는 DataSet에 데이터 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f37f-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="5f37f-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5f37f-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="5f37f-106">이 항목의 예제에서는 다음을 사용 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="5f37f-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="5f37f-107">자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="5f37f-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="5f37f-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="5f37f-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="5f37f-109">예제</span><span class="sxs-lookup"><span data-stu-id="5f37f-109">Example</span></span>  
 <span data-ttu-id="5f37f-110">이 예제에서는 <xref:System.Linq.Enumerable.ElementAt%2A> 메서드를 사용하여 `PostalCode`가 "M4B 1V7"인 다섯 번째 주소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5f37f-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]
 [!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]  
  
## <a name="first"></a><span data-ttu-id="5f37f-111">First</span><span class="sxs-lookup"><span data-stu-id="5f37f-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="5f37f-112">예제</span><span class="sxs-lookup"><span data-stu-id="5f37f-112">Example</span></span>  
 <span data-ttu-id="5f37f-113">이 예제에서는 <xref:System.Linq.Enumerable.First%2A> 메서드를 사용하여 이름이 'Brooke'인 첫 번째 연락처를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5f37f-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="5f37f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="5f37f-114">See also</span></span>

- [<span data-ttu-id="5f37f-115">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="5f37f-115">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="5f37f-116">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="5f37f-116">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="5f37f-117">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="5f37f-117">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="5f37f-118">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5f37f-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
