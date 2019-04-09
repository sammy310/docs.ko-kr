---
title: '메서드 기반 쿼리 구문 예제: 변환 연산자(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a084c16b-9b55-4690-aefd-f8e0810a92c3
ms.openlocfilehash: e50707155d509b8300966cbba8ee885492e5b815
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59108643"
---
# <a name="method-based-query-syntax-examples-conversion-operators-linq-to-dataset"></a><span data-ttu-id="28db3-102">메서드 기반 쿼리 구문 예제: 변환 연산자(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="28db3-102">Method-Based Query Syntax Examples: Conversion Operators (LINQ to DataSet)</span></span>
<span data-ttu-id="28db3-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> 및 <xref:System.Linq.Enumerable.ToList%2A> 메서드를 사용하여 쿼리 식을 즉시 실행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="28db3-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A>, and <xref:System.Linq.Enumerable.ToList%2A> methods to immediately execute a query expression.</span></span>  
  
 <span data-ttu-id="28db3-104">합니다 `FillDataSet` 에이 예제에서 사용 하는 방법이 지정 되어 [는 DataSet에 데이터 로드](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="28db3-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="28db3-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="28db3-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="28db3-106">이 항목의 예제에서는 다음을 사용 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="28db3-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="28db3-107">자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="28db3-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](../../../../docs/framework/data/adonet/how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="toarray"></a><span data-ttu-id="28db3-108">ToArray</span><span class="sxs-lookup"><span data-stu-id="28db3-108">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="28db3-109">예제</span><span class="sxs-lookup"><span data-stu-id="28db3-109">Example</span></span>  
 <span data-ttu-id="28db3-110">이 예제에서는 <xref:System.Linq.Enumerable.ToArray%2A> 메서드로 시퀀스를 즉시 계산하여 배열에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="28db3-110">This example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#toarray)]
 [!code-vb[DP LINQ to DataSet Examples#ToArray](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="28db3-111">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="28db3-111">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="28db3-112">예제</span><span class="sxs-lookup"><span data-stu-id="28db3-112">Example</span></span>  
 <span data-ttu-id="28db3-113">이 예제에서는 <xref:System.Linq.Enumerable.ToDictionary%2A> 메서드로 시퀀스 및 관련 키 식을 즉시 계산하여 사전에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="28db3-113">This example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP LINQ to DataSet Examples#ToDictionary](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="28db3-114">ToList</span><span class="sxs-lookup"><span data-stu-id="28db3-114">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="28db3-115">예제</span><span class="sxs-lookup"><span data-stu-id="28db3-115">Example</span></span>  
 <span data-ttu-id="28db3-116">이 예제에서는 <xref:System.Linq.Enumerable.ToList%2A> 메서드로 시퀀스를 즉시 계산하여 <xref:System.Collections.Generic.List%601>에 넣습니다. 여기서 `T`는 <xref:System.Data.DataRow> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="28db3-116">This example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#tolist)]
 [!code-vb[DP LINQ to DataSet Examples#ToList](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="28db3-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="28db3-117">See also</span></span>

- [<span data-ttu-id="28db3-118">데이터를 데이터 집합에 로드</span><span class="sxs-lookup"><span data-stu-id="28db3-118">Loading Data Into a DataSet</span></span>](../../../../docs/framework/data/adonet/loading-data-into-a-dataset.md)
- [<span data-ttu-id="28db3-119">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="28db3-119">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
- [<span data-ttu-id="28db3-120">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="28db3-120">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="28db3-121">표준 쿼리 연산자 개요 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="28db3-121">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
