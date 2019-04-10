---
title: '방법: 관련 데이터 필터링'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: ec8b8f97-5d01-4f31-9b97-d1556df6a4bc
ms.openlocfilehash: 3dbedfb7065ac4b1a570a3f6cdbcdcc2177f20cf
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59218227"
---
# <a name="how-to-filter-related-data"></a>방법: 관련 데이터 필터링
<xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> 메서드를 사용하여 검색된 데이터의 양을 제한하기 위한 하위 쿼리를 지정합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서 <xref:System.Data.Linq.DataLoadOptions.AssociateWith%2A> 메서드는 `Orders`를 오늘 선적되지 되지 않은 것으로 제한합니다. 이 방법을 사용하지 않을 경우 한 개의 하위 집합만 필요한 경우에도 모든 `Orders`가 검색됩니다.  
  
 [!code-csharp[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.dataloadoptions/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.DataLoadOptions#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.dataloadoptions/vb/module1.vb#1)]  
  
## <a name="see-also"></a>참고자료

- [데이터베이스 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
