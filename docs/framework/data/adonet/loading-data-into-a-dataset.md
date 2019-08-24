---
title: 데이터를 데이터 세트에 로드
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
# <a name="loading-data-into-a-dataset"></a>데이터를 데이터 세트에 로드
<xref:System.Data.DataSet> LINQ to DataSet 사용 하 여 쿼리할 수 전에 먼저 개체를 입력 해야 합니다. <xref:System.Data.DataSet>은 여러 방법으로 채울 수 있습니다. 예를 들어, [!INCLUDE[vbtecdlinq](../../../../includes/vbtecdlinq-md.md)]를 사용하여 데이터베이스를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드할 수 있습니다. 자세한 내용은 [LINQ to SQL](../../../../docs/framework/data/adonet/sql/linq/index.md)을 참조하세요.  
  
 <xref:System.Data.DataSet>에 데이터를 로드하는 일반적인 방법 중에는 <xref:System.Data.Common.DataAdapter> 클래스를 사용하여 데이터베이스에서 데이터를 검색하는 방법도 있습니다. 다음 예제에서 이 방법을 보여 줍니다.  
  
## <a name="example"></a>예제  
 이 예제에서는 <xref:System.Data.Common.DataAdapter>를 사용하여 AdventureWorks 데이터베이스에서 2002년 판매 정보를 쿼리한 다음 그 결과를 <xref:System.Data.DataSet>에 로드합니다. 이후에 <xref:System.Data.DataSet> 되었습니다 입력 쿼리를 작성할 수에 대 한 LINQ to DataSet 사용 하 여 합니다. 합니다 `FillDataSet` 의 예제에서는 쿼리에서이 예제의 메서드를 사용 하는 [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)합니다. 자세한 내용은 [데이터 집합 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)합니다.  
  
 [!code-csharp[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/CS/Program.cs#filldataset)]
 [!code-vb[DP LINQ to DataSet Examples#FillDataSet](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP LINQ to DataSet Examples/VB/Module1.vb#filldataset)]  
  
## <a name="see-also"></a>참고자료

- [LINQ to DataSet 개요](../../../../docs/framework/data/adonet/linq-to-dataset-overview.md)
- [데이터 집합 쿼리](../../../../docs/framework/data/adonet/querying-datasets-linq-to-dataset.md)
- [LINQ to DataSet 예제](../../../../docs/framework/data/adonet/linq-to-dataset-examples.md)
