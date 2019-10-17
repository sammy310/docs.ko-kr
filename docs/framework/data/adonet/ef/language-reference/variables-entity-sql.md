---
title: 변수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: bb8e6ebe81dacc7ec0f45fdde65b9c18cfd76789
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319195"
---
# <a name="variables-entity-sql"></a>변수(Entity SQL)
## <a name="variable"></a>변수  
 변수 식은 현재 범위에 정의된 명명된 식에 대한 참조입니다. 변수 참조는 [식별자](identifiers-entity-sql.md)에 정의 된 유효한 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식별자 여야 합니다.  
  
 다음 예제에서는 식에서 변수 사용을 보여 줍니다. FROM 절의 `c`는 변수 정의입니다. SELECT 절의 `c` 사용은 변수 참조를 나타냅니다.  
  
```sql  
select c   
from LOB.customers as c  
```  
  
## <a name="see-also"></a>참조

- [식별자](identifiers-entity-sql.md)
- [매개 변수](parameters-entity-sql.md)
- [Entity SQL 개요](entity-sql-overview.md)
