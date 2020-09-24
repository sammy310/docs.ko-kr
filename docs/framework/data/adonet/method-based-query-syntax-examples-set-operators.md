---
title: '메서드 기반 쿼리 구문 예제: 집합 연산자(LINQ to DataSet)'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fa93af15-28af-4b5e-846b-897308410edb
ms.openlocfilehash: f91d009e66f1f0da25e508994040d7e9f80fc681
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91147868"
---
# <a name="method-based-query-syntax-examples-set-operators-linq-to-dataset"></a><span data-ttu-id="e3a14-102">메서드 기반 쿼리 구문 예제: 집합 연산자(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="e3a14-102">Method-Based Query Syntax Examples: Set Operators (LINQ to DataSet)</span></span>

<span data-ttu-id="e3a14-103">이 항목의 예제에서는,, 및 연산자를 사용 하 여 <xref:System.Linq.Enumerable.Distinct%2A> <xref:System.Linq.Enumerable.Except%2A> <xref:System.Linq.Enumerable.Intersect%2A> <xref:System.Linq.Enumerable.Union%2A> 데이터 행 집합에 대해 값 기반 비교 연산을 수행[ 하는 방법을 보여 줍니다. 데이터 집합에 데이터를 로드 하는](loading-data-into-a-dataset.md) 방법에 대 한 자세한 내용은 [datarow 비교](comparing-datarows-linq-to-dataset.md) 를 참조 하세요 <xref:System.Data.DataRowComparer> .</span><span class="sxs-lookup"><span data-stu-id="e3a14-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Except%2A>, <xref:System.Linq.Enumerable.Intersect%2A>, and <xref:System.Linq.Enumerable.Union%2A> operators to perform value-based comparison operations on sets of data rows.[Loading Data Into a DataSet](loading-data-into-a-dataset.md) See [Comparing DataRows](comparing-datarows-linq-to-dataset.md) for more information on <xref:System.Data.DataRowComparer>.</span></span>  
  
 <span data-ttu-id="e3a14-104">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드](loading-data-into-a-dataset.md)하는데 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e3a14-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="e3a14-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a14-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e3a14-106">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="e3a14-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="e3a14-107">자세한 내용은 [방법: Visual Studio에서 LINQ to DataSet 프로젝트 만들기](how-to-create-a-linq-to-dataset-project-in-vs.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e3a14-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="distinct"></a><span data-ttu-id="e3a14-108">Distinct</span><span class="sxs-lookup"><span data-stu-id="e3a14-108">Distinct</span></span>  
  
### <a name="example"></a><span data-ttu-id="e3a14-109">예제</span><span class="sxs-lookup"><span data-stu-id="e3a14-109">Example</span></span>  

 <span data-ttu-id="e3a14-110">이 예제에서는 <xref:System.Linq.Enumerable.Distinct%2A> 메서드를 사용하여 시퀀스의 중복 요소를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a14-110">This example uses the <xref:System.Linq.Enumerable.Distinct%2A> method to remove duplicate elements in a sequence.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#distinctrows)]
 [!code-vb[DP LINQ to DataSet Examples#DistinctRows](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#distinctrows)]  
  
## <a name="except"></a><span data-ttu-id="e3a14-111">Except</span><span class="sxs-lookup"><span data-stu-id="e3a14-111">Except</span></span>  
  
### <a name="example"></a><span data-ttu-id="e3a14-112">예제</span><span class="sxs-lookup"><span data-stu-id="e3a14-112">Example</span></span>  

 <span data-ttu-id="e3a14-113">이 예제에서는 <xref:System.Linq.Enumerable.Except%2A> 메서드를 사용하여 첫 번째 테이블에만 있고 두 번째 테이블에는 없는 연락처를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a14-113">This example uses the <xref:System.Linq.Enumerable.Except%2A> method to return contacts that appear in the first table but not in the second.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#except2)]
 [!code-vb[DP LINQ to DataSet Examples#Except2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#except2)]  
  
## <a name="intersect"></a><span data-ttu-id="e3a14-114">Intersect</span><span class="sxs-lookup"><span data-stu-id="e3a14-114">Intersect</span></span>  
  
### <a name="example"></a><span data-ttu-id="e3a14-115">예제</span><span class="sxs-lookup"><span data-stu-id="e3a14-115">Example</span></span>  

 <span data-ttu-id="e3a14-116">이 예제에서는 <xref:System.Linq.Enumerable.Intersect%2A> 메서드를 사용하여 두 테이블 모두에 있는 연락처를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a14-116">This example uses the <xref:System.Linq.Enumerable.Intersect%2A> method to return contacts that appear in both tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#intersect2)]
 [!code-vb[DP LINQ to DataSet Examples#Intersect2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#intersect2)]  
  
## <a name="union"></a><span data-ttu-id="e3a14-117">Union</span><span class="sxs-lookup"><span data-stu-id="e3a14-117">Union</span></span>  
  
### <a name="example"></a><span data-ttu-id="e3a14-118">예제</span><span class="sxs-lookup"><span data-stu-id="e3a14-118">Example</span></span>  

 <span data-ttu-id="e3a14-119">이 예제에서는 <xref:System.Linq.Enumerable.Union%2A> 메서드를 사용하여 두 테이블 중 한 테이블에만 있는 고유 연락처를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="e3a14-119">This example uses the <xref:System.Linq.Enumerable.Union%2A> method to return unique contacts from either of the two tables.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#union2)]
 [!code-vb[DP LINQ to DataSet Examples#Union2](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#union2)]  
  
## <a name="see-also"></a><span data-ttu-id="e3a14-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e3a14-120">See also</span></span>

- [<span data-ttu-id="e3a14-121">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="e3a14-121">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="e3a14-122">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="e3a14-122">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
- [<span data-ttu-id="e3a14-123">표준 쿼리 연산자 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="e3a14-123">Standard Query Operators Overview (C#)</span></span>](../../../csharp/programming-guide/concepts/linq/standard-query-operators-overview.md)
- [<span data-ttu-id="e3a14-124">표준 쿼리 연산자 개요(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="e3a14-124">Standard Query Operators Overview (Visual Basic)</span></span>](../../../visual-basic/programming-guide/concepts/linq/standard-query-operators-overview.md)
