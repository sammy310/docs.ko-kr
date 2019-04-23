---
title: '방법: 지연 콘텐츠 해제'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1b84b852-3cad-41a7-8077-149a70d50c8b
ms.openlocfilehash: f82e347ecdb3c69cee3749855d1e4cb457a460f6
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59112959"
---
# <a name="how-to-turn-off-deferred-loading"></a>방법: 지연 콘텐츠 해제
<xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제할 수 있습니다. 자세한 내용은 [즉시 로드 비교 지연](../../../../../../docs/framework/data/adonet/sql/linq/deferred-versus-immediate-loading.md)합니다.  
  
> [!NOTE]
>  개체 추적이 해제되면 지연된 로드는 암시적으로 해제된 것입니다. 자세한 내용은 [방법: 읽기 전용으로 정보를 검색할](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-information-as-read-only.md)합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 <xref:System.Data.Linq.DataContext.DeferredLoadingEnabled%2A>를 `false`로 설정하여 지연된 로드를 해제하는 방법을 보여 줍니다.  
  
 [!code-csharp[DLinqQuerying#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#3)]
 [!code-vb[DLinqQuerying#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#3)]  
  
## <a name="see-also"></a>참고자료

- [쿼리 개념](../../../../../../docs/framework/data/adonet/sql/linq/query-concepts.md)
- [데이터베이스 쿼리](../../../../../../docs/framework/data/adonet/sql/linq/querying-the-database.md)
