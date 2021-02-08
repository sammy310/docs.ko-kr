---
description: '자세히 알아보기: 변수 (Entity SQL)'
title: 변수(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 3eed222a-f8f6-46b6-9cd5-220cc0e4e5d8
ms.openlocfilehash: 134fee8f61c8e87a18520e6622f6a6a5cceb0076
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795042"
---
# <a name="variables-entity-sql"></a>변수(Entity SQL)

## <a name="variable"></a>변수  

 변수 식은 현재 범위에 정의된 명명된 식에 대한 참조입니다. 변수 참조는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] [식별자](identifiers-entity-sql.md)에 정의 된 대로 유효한 식별자 여야 합니다.  
  
 다음 예제에서는 식에서 변수 사용을 보여 줍니다. FROM 절의 `c`는 변수 정의입니다. SELECT 절의 `c` 사용은 변수 참조를 나타냅니다.  
  
```sql  
select c
from LOB.customers as c  
```  
  
## <a name="see-also"></a>참고 항목

- [식별자](identifiers-entity-sql.md)
- [매개 변수](parameters-entity-sql.md)
- [Entity SQL 개요](entity-sql-overview.md)
