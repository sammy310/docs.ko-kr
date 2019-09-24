---
title: DataSet별 연산자 예제(LINQ to DataSet)
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8fdd64af-6ad0-46cd-91c8-dbe26620eeb1
ms.openlocfilehash: 6a9dc82e0bb065b455c0208daaf2d28a74cd7e34
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70784207"
---
# <a name="dataset-specific-operator-examples-linq-to-dataset"></a><span data-ttu-id="8df1c-102">DataSet별 연산자 예제(LINQ to DataSet)</span><span class="sxs-lookup"><span data-stu-id="8df1c-102">DataSet-Specific Operator Examples (LINQ to DataSet)</span></span>
<span data-ttu-id="8df1c-103">이 항목의 예제에서는 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> 메서드와 <xref:System.Data.DataRowComparer> 클래스를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8df1c-103">The examples in this topic demonstrate how to use the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method and the <xref:System.Data.DataRowComparer> class.</span></span>  
  
 <span data-ttu-id="8df1c-104">이러한 예제에서 사용되는 `FillDataSet` 메서드는 [데이터집합에 데이터를 로드](loading-data-into-a-dataset.md)하는데 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="8df1c-104">The `FillDataSet` method used in these examples is specified in [Loading Data Into a DataSet](loading-data-into-a-dataset.md).</span></span>  
  
 <span data-ttu-id="8df1c-105">이 항목의 예제에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8df1c-105">The examples in this topic use the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8df1c-106">이 항목의 예제에서는 다음 `using` / `Imports` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8df1c-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP LINQ to DataSet Examples#ImportsUsing](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#importsusing)]  
  
 <span data-ttu-id="8df1c-107">자세한 내용은 [방법: Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md)에서 LINQ to DataSet 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8df1c-107">For more information, see [How to: Create a LINQ to DataSet Project In Visual Studio](how-to-create-a-linq-to-dataset-project-in-vs.md).</span></span>  
  
## <a name="copytodatatable"></a><span data-ttu-id="8df1c-108">CopyToDataTable</span><span class="sxs-lookup"><span data-stu-id="8df1c-108">CopyToDataTable</span></span>  
  
### <a name="example"></a><span data-ttu-id="8df1c-109">예제</span><span class="sxs-lookup"><span data-stu-id="8df1c-109">Example</span></span>  
 <span data-ttu-id="8df1c-110">이 예제에서는 <xref:System.Data.DataTable> 메서드를 사용하여 쿼리 결과가 있는 <xref:System.Data.DataTableExtensions.CopyToDataTable%2A>을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="8df1c-110">This example loads a <xref:System.Data.DataTable> with query results by using the <xref:System.Data.DataTableExtensions.CopyToDataTable%2A> method.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#loaddatatablewithqueryresults)]
 [!code-vb[DP LINQ to DataSet Examples#LoadDataTableWithQueryResults](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#loaddatatablewithqueryresults)]  
  
## <a name="datarowcomparer"></a><span data-ttu-id="8df1c-111">DataRowComparer</span><span class="sxs-lookup"><span data-stu-id="8df1c-111">DataRowComparer</span></span>  
  
### <a name="example"></a><span data-ttu-id="8df1c-112">예제</span><span class="sxs-lookup"><span data-stu-id="8df1c-112">Example</span></span>  
 <span data-ttu-id="8df1c-113">이 예제에서는 <xref:System.Data.DataRowComparer>를 사용하여 서로 다른 두 데이터 행을 비교합니다.</span><span class="sxs-lookup"><span data-stu-id="8df1c-113">This example compares two different data rows by using <xref:System.Data.DataRowComparer>.</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#CompareDifferentDataRows](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#comparedifferentdatarows)]  
  
## <a name="see-also"></a><span data-ttu-id="8df1c-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="8df1c-114">See also</span></span>

- [<span data-ttu-id="8df1c-115">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="8df1c-115">Loading Data Into a DataSet</span></span>](loading-data-into-a-dataset.md)
- [<span data-ttu-id="8df1c-116">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="8df1c-116">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
