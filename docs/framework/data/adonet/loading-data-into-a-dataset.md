---
title: 데이터를 데이터 집합에 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 26b77269b21e1b365f81746ba2df66d7df91677e
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504321"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="1e7bb-102">데이터를 데이터 집합에 로드</span><span class="sxs-lookup"><span data-stu-id="1e7bb-102">Loading Data Into a DataSet</span></span>
<span data-ttu-id="1e7bb-103"><xref:System.Data.DataSet> LINQ to DataSet 사용 하 여 쿼리할 수 전에 먼저 개체를 입력 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-103">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="1e7bb-104"><xref:System.Data.DataSet>은 여러 방법으로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-104">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1e7bb-105">예를 들어, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]를 사용하여 데이터베이스를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-105">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1e7bb-106">자세한 내용은 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-106">For more information, see [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="1e7bb-107"><xref:System.Data.DataSet>에 데이터를 로드하는 일반적인 방법 중에는 <xref:System.Data.Common.DataAdapter> 클래스를 사용하여 데이터베이스에서 데이터를 검색하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-107">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="1e7bb-108">다음 예제에서 이 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-108">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e7bb-109">예제</span><span class="sxs-lookup"><span data-stu-id="1e7bb-109">Example</span></span>  
 <span data-ttu-id="1e7bb-110">이 예제에서는 <xref:System.Data.Common.DataAdapter>를 사용하여 AdventureWorks 데이터베이스에서 2002년 판매 정보를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-110">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="1e7bb-111">이후에 <xref:System.Data.DataSet> 되었습니다 입력 쿼리를 작성할 수에 대 한 LINQ to DataSet 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-111">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="1e7bb-112">합니다 `FillDataSet` 의 예제에서는 쿼리에서이 예제의 메서드를 사용 하는 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-112">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md).</span></span> <span data-ttu-id="1e7bb-113">자세한 내용은 [데이터 집합 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1e7bb-113">For more information, see [Querying DataSets](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="1e7bb-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e7bb-114">See also</span></span>

- [<span data-ttu-id="1e7bb-115">LINQ to DataSet 개요</span><span class="sxs-lookup"><span data-stu-id="1e7bb-115">LINQ to DataSet Overview</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [<span data-ttu-id="1e7bb-116">데이터 집합 쿼리</span><span class="sxs-lookup"><span data-stu-id="1e7bb-116">Querying DataSets</span></span>](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="1e7bb-117">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="1e7bb-117">LINQ to DataSet Examples</span></span>](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
