---
description: '자세한 정보: 사용 (Entity SQL)'
title: USING(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 20f58b8f-6070-4456-b7e8-5ff3d6269273
ms.openlocfilehash: 084ab56f25041377dd6a0a35dd743122f482eeba
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795055"
---
# <a name="using-entity-sql"></a>USING(Entity SQL)

쿼리 식에 사용되는 네임스페이스를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
USING [ alias = ] namespace  
```  
  
## <a name="arguments"></a>인수  

 `alias`  
 네임스페이스를 정규화하는 데 사용할 짧은 별칭을 지정합니다.  
  
 `namespace`  
 유효한 네임스페이스입니다.  
  
## <a name="example"></a>예제  

 다음 Entity SQL 쿼리에서는 USING 연산자를 사용하여 쿼리 식에 사용되는 네임스페이스를 지정합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [방법: PrimitiveType 결과를 반환 하는 쿼리 실행](../how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
```csharp
using SqlServer; RAND()  
```  
  
## <a name="see-also"></a>참고 항목

- [네임스페이스](namespaces-entity-sql.md)
- [엔터티 SQL 참조](entity-sql-reference.md)
