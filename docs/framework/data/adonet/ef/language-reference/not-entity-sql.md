---
title: '! (NOT)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 0eb9be9ed4cbce45a51d15eea68e9fb1a26f0107
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191842"
---
# <a name="-not-entity-sql"></a>! (NOT)(Entity SQL)

`Boolean` 식을 부정합니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
NOT boolean_expression  
-- or  
! boolean_expression  
```
  
## <a name="arguments"></a>인수  

 `boolean_expression`  
 부울을 반환하는 모든 유효한 식입니다.  
  
## <a name="remarks"></a>설명  

 느낌표(!)는 NOT 연산자와 같은 기능을 합니다.  
  
## <a name="example"></a>예제  

 다음 Entity SQL 쿼리에서는 NOT 연산자를 사용하여 `Boolean` 식을 부정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a>참고 항목

- [엔터티 SQL 참조](entity-sql-reference.md)
