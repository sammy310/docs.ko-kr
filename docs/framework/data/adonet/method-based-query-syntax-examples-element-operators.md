---
title: '메서드 기반 쿼리 구문 예제: ELEMENT 연산자(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: eedf2fbd-f407-4f62-bb1a-c00eb001b1dd
ms.openlocfilehash: e43208d6ae524a1370b936d42508e9c7a7d196e5
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149509"
---
# <a name="method-based-query-syntax-examples-element-operators-linq-to-dataset"></a><span data-ttu-id="e1902-102">메서드 기반 쿼리 구문 예제: ELEMENT 연산자(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e1902-102">Method-Based Query Syntax Examples: Element Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="e1902-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.First%2A> 및 <xref:System.Linq.Enumerable.ElementAt%2A> 메서드에서 쿼리 식 구문을 사용하여 <xref:System.Data.DataRow>의 <xref:System.Data.DataSet> 요소를 쿼리하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e1902-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> and <xref:System.Linq.Enumerable.ElementAt%2A> methods to get <xref:System.Data.DataRow> elements from a <xref:System.Data.DataSet> using the query expression syntax.</span></span>  
  
 <span data-ttu-id="e1902-104">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드](loading-data-into-a-dataset.md)하는데 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e1902-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e1902-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1902-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e1902-106">이 항목의 예제에서는 다음 `using` / `Imports` 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e1902-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
[!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]

 <span data-ttu-id="e1902-107">자세한 내용은 [Visual Studio에서 LINQ에서 데이터 집합 프로젝트로 만드는 방법을](how-to-create-a-linq-to-dataset-project-in-vs.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e1902-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="elementat"></a><span data-ttu-id="e1902-108">ElementAt</span><span class="sxs-lookup"><span data-stu-id="e1902-108">ElementAt</span></span>  
  
### <a name="example"></a><span data-ttu-id="e1902-109">예제</span><span class="sxs-lookup"><span data-stu-id="e1902-109">Example</span></span>  
 <span data-ttu-id="e1902-110">이 예제에서는 <xref:System.Linq.Enumerable.ElementAt%2A> 메서드를 사용하여 `PostalCode`가 "M4B 1V7"인 다섯 번째 주소를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="e1902-110">This example uses the <xref:System.Linq.Enumerable.ElementAt%2A> method to retrieve the fifth address where `PostalCode` == "M4B 1V7".</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#elementat)]
[!code-vb[DP LINQ to DataSet Examples#ElementAt](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#elementat)]
  
## <a name="first"></a><span data-ttu-id="e1902-111">처음</span><span class="sxs-lookup"><span data-stu-id="e1902-111">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="e1902-112">예제</span><span class="sxs-lookup"><span data-stu-id="e1902-112">Example</span></span>  
 <span data-ttu-id="e1902-113">이 예제에서는 <xref:System.Linq.Enumerable.First%2A> 메서드를 사용하여 이름이 'Brooke'인 첫 번째 연락처를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e1902-113">This example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is 'Brooke'.</span></span>  
  
[!code-csharp[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#firstsimple)]
[!code-vb[DP LINQ to DataSet Examples#FirstSimple](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#firstsimple)]
  
## <a name="see-also"></a><span data-ttu-id="e1902-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e1902-114">See also</span></span>

- [<span data-ttu-id="e1902-115">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="e1902-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="e1902-116">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="e1902-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="e1902-117">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="e1902-117">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="e1902-118">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e1902-118">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
