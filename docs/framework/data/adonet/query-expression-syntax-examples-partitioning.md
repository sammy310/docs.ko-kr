---
title: '쿼리 식 구문 예제: 분할(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: beb5f361-1ac8-44fb-afa1-2aacea15f166
ms.openlocfilehash: 9f907d16c78b550fbc11cc2cfad3c8249966a2f1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91189034"
---
# <a name="query-expression-syntax-examples-partitioning-linq-to-dataset"></a><span data-ttu-id="6d324-102">쿼리 식 구문 예제: 분할(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="6d324-102">Query Expression Syntax Examples: Partitioning (LINQ to DataSet)</span></span>

<span data-ttu-id="6d324-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Take%2A> 메서드에서 쿼리 식 구문을 사용하여 <xref:System.Data.DataSet>을 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d324-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A> and <xref:System.Linq.Enumerable.Take%2A> methods to query a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="6d324-104">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드](loading-data-into-a-dataset.md)하는데 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d324-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="6d324-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6d324-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="6d324-106">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="6d324-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="6d324-107">자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](how-to-create-a-linq-to-dataset-project-in-vs.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d324-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="skip"></a><span data-ttu-id="6d324-108">건너뛰기</span><span class="sxs-lookup"><span data-stu-id="6d324-108">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="6d324-109">예제</span><span class="sxs-lookup"><span data-stu-id="6d324-109">Example</span></span>  

 <span data-ttu-id="6d324-110">이 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 메서드를 사용하여 Seattle에 있는 처음 2개의 주소를 제외한 모든 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6d324-110">This example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP LINQ to DataSet Examples#SkipNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="6d324-111">Take</span><span class="sxs-lookup"><span data-stu-id="6d324-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="6d324-112">예제</span><span class="sxs-lookup"><span data-stu-id="6d324-112">Example</span></span>  

 <span data-ttu-id="6d324-113">이 예제에서는 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 Seattle에 있는 처음 3개의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6d324-113">This example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#takenested)]
 [!code-vb[DP LINQ to DataSet Examples#TakeNested](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="6d324-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6d324-114">See also</span></span>

- [<span data-ttu-id="6d324-115">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="6d324-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="6d324-116">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="6d324-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="6d324-117">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="6d324-117">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="6d324-118">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="6d324-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
