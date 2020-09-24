---
title: 데이터를 데이터 세트에 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: c870cabc875aa0152910ce916819fb1ff1c018f7
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91166718"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="01841-102">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="01841-102">Loading Data Into a DataSet</span></span>

<span data-ttu-id="01841-103"><xref:System.Data.DataSet>LINQ to DataSet를 사용 하 여 쿼리 하려면 먼저 개체를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="01841-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="01841-104"><xref:System.Data.DataSet>은 여러 방법으로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01841-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="01841-105">예를 들어, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]를 사용하여 데이터베이스를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01841-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="01841-106">자세한 내용은 [LINQ to SQL](./sql/linq/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="01841-106">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="01841-107"><xref:System.Data.DataSet>에 데이터를 로드하는 일반적인 방법 중에는 <xref:System.Data.Common.DataAdapter> 클래스를 사용하여 데이터베이스에서 데이터를 검색하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01841-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="01841-108">다음 예에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01841-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="01841-109">예제</span><span class="sxs-lookup"><span data-stu-id="01841-109">Example</span></span>  

 <span data-ttu-id="01841-110">이 예제에서는 <xref:System.Data.Common.DataAdapter>를 사용하여 AdventureWorks 데이터베이스에서 2002년 판매 정보를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="01841-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="01841-111">을 <xref:System.Data.DataSet> 채운 후 LINQ to DataSet를 사용 하 여 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="01841-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="01841-112">이 예제의 `FillDataSet`메서드는 [LINQ to DataSet 예제](linq-to-dataset-examples.md)에서 예제 쿼리에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="01841-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="01841-113">자세한 내용은 [데이터 집합 쿼리](querying-datasets-linq-to-dataset.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="01841-113">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="01841-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="01841-114">See also</span></span>

- [<span data-ttu-id="01841-115">LINQ to DataSet 개요</span><span class="sxs-lookup"><span data-stu-id="01841-115">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="01841-116">DataSets 쿼리</span><span class="sxs-lookup"><span data-stu-id="01841-116">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="01841-117">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="01841-117">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
