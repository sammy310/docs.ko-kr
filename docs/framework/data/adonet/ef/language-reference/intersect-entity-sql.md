---
title: INTERSECT(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 93c6fe33-f341-4b52-911e-adf503891951
ms.openlocfilehash: dc7338d176302b8683d541ab0dc715dd8d149c6f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319774"
---
# <a name="intersect-entity-sql"></a>INTERSECT(Entity SQL)
INTERSECT 피연산자의 왼쪽과 오른쪽에 있는 두 쿼리 식에서 반환된 고유한 값의 컬렉션을 반환합니다. 모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
expression INTERSECT expression  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 다른 쿼리 식에서 반환된 컬렉션과 비교할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.  
  
## <a name="return-value"></a>반환 값  
 형식이 같거나 기본 형식 또는 파생 형식이 `expression`인 컬렉션입니다.  
  
## <a name="remarks"></a>주의  
 INTERSECT는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다. 모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다. @No__t_0 집합 연산자의 우선 순위에 대 한 자세한 내용은 [EXCEPT](except-entity-sql.md)를 참조 하십시오.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 INTERSECT 연산자를 사용하여 INTERSECT 피연산자의 왼쪽과 오른쪽에 있는 두 쿼리 식에서 반환된 고유한 값의 컬렉션을 반환합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#INTERSECT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#intersect)]  
  
## <a name="see-also"></a>참조

- [엔터티 SQL 참조](entity-sql-reference.md)
