---
title: '방법: 지연 콘텐츠 해제'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: f68db5a5a0092fc4cf37746f2a4dc81e40ee4a9d
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69938685"
---
# <a name="how-to-turn-off-deferred-loading"></a>방법: 지연 콘텐츠 해제
<xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제할 수 있습니다. 자세한 내용은 [지연 된 로드 및 즉시 로드](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)를 참조 하세요.  
  
> [!NOTE]
> 개체 추적이 해제되면 지연된 로드는 암시적으로 해제된 것입니다. 자세한 내용은 [방법: 정보를 읽기](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)전용으로 검색 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제하는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>참고자료

- [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [데이터베이스 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
