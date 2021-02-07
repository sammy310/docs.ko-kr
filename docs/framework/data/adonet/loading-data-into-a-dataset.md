---
description: '자세히 알아보기: 데이터 집합으로 데이터 로드'
title: 데이터를 데이터 세트에 로드
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a53e5dc1-9669-49d4-828d-efa633237066
ms.openlocfilehash: 167a399d17257008e884fbcccc96de17398b8f88
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99681684"
---
# <a name="loading-data-into-a-dataset"></a><span data-ttu-id="4becd-103">데이터를 데이터 세트에 로드</span><span class="sxs-lookup"><span data-stu-id="4becd-103">Loading Data Into a DataSet</span></span>

<span data-ttu-id="4becd-104"><xref:System.Data.DataSet>LINQ to DataSet를 사용 하 여 쿼리 하려면 먼저 개체를 채워야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4becd-104">A <xref:System.Data.DataSet> object must first be populated before you can query over it with LINQ to DataSet.</span></span> <span data-ttu-id="4becd-105"><xref:System.Data.DataSet>은 여러 방법으로 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4becd-105">There are several different ways to populate the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="4becd-106">예를 들어, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]를 사용하여 데이터베이스를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4becd-106">For example, you can use [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)] to query the database and load the results into the <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="4becd-107">자세한 내용은 [LINQ to SQL](./sql/linq/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4becd-107">For more information, see [LINQ to SQL](./sql/linq/index.md).</span></span>  
  
 <span data-ttu-id="4becd-108"><xref:System.Data.DataSet>에 데이터를 로드하는 일반적인 방법 중에는 <xref:System.Data.Common.DataAdapter> 클래스를 사용하여 데이터베이스에서 데이터를 검색하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4becd-108">Another common way to load data into a <xref:System.Data.DataSet> is to use the <xref:System.Data.Common.DataAdapter> class to retrieve data from the database.</span></span> <span data-ttu-id="4becd-109">다음 예에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4becd-109">This is illustrated in the following example.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4becd-110">예제</span><span class="sxs-lookup"><span data-stu-id="4becd-110">Example</span></span>  

 <span data-ttu-id="4becd-111">이 예제에서는 <xref:System.Data.Common.DataAdapter>를 사용하여 AdventureWorks 데이터베이스에서 2002년 판매 정보를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="4becd-111">This example uses a <xref:System.Data.Common.DataAdapter> to query the AdventureWorks database for sales information from the year 2002, and loads the results into a <xref:System.Data.DataSet>.</span></span> <span data-ttu-id="4becd-112">을 <xref:System.Data.DataSet> 채운 후 LINQ to DataSet를 사용 하 여 쿼리를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4becd-112">After the <xref:System.Data.DataSet> has been populated, you can write queries against it by using LINQ to DataSet.</span></span> <span data-ttu-id="4becd-113">이 예제의 `FillDataSet`메서드는 [LINQ to DataSet 예제](linq-to-dataset-examples.md)에서 예제 쿼리에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="4becd-113">The `FillDataSet` method in this example is used in the example queries in [LINQ to DataSet Examples](linq-to-dataset-examples.md).</span></span> <span data-ttu-id="4becd-114">자세한 내용은 [데이터 집합 쿼리](querying-datasets-linq-to-dataset.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4becd-114">For more information, see [Querying DataSets](querying-datasets-linq-to-dataset.md).</span></span>  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a><span data-ttu-id="4becd-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4becd-115">See also</span></span>

- [<span data-ttu-id="4becd-116">LINQ to DataSet 개요</span><span class="sxs-lookup"><span data-stu-id="4becd-116">LINQ to DataSet Overview</span></span>](linq-to-dataset-overview.md)
- [<span data-ttu-id="4becd-117">DataSets 쿼리</span><span class="sxs-lookup"><span data-stu-id="4becd-117">Querying DataSets</span></span>](querying-datasets-linq-to-dataset.md)
- [<span data-ttu-id="4becd-118">LINQ to DataSet 예제</span><span class="sxs-lookup"><span data-stu-id="4becd-118">LINQ to DataSet Examples</span></span>](linq-to-dataset-examples.md)
