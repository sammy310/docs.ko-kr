---
title: 매개 변수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 8d618edd-0988-4ff2-8263-ce59448af7a5
ms.openlocfilehash: 759452902461e1a460b69774bb33f92bbd532ed0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177518"
---
# <a name="parameters-entity-sql"></a>매개 변수(Entity SQL)

매개 변수는 일반적으로 호스트 언어에서 사용되는 바인딩 API를 통해 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 외부에서 정의되는 변수입니다. 각 매개 변수에는 이름과 형식이 있습니다. 매개 변수 이름은 쿼리 식에서 정의되며 at(@) 기호가 접두사로 사용되므로, 쿼리에서 정의되는 속성 이름이나 다른 이름과 쉽게 구분할 수 있습니다.  
  
 호스트 언어 바인딩 API는 매개 변수 바인딩을 위한 API를 제공합니다.  
  
## <a name="example"></a>예제  
  
```sql  
SELECT c
      FROM LOB.Customers AS c
      WHERE c.Name = @name  
```  
  
## <a name="see-also"></a>참고 항목

- [엔터티 SQL 참조](entity-sql-reference.md)
- [Entity SQL 개요](entity-sql-overview.md)
