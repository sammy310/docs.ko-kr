---
title: SET(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 28b4deac-c7e4-4f09-b428-4d352ef2dc94
ms.openlocfilehash: 9d4cdeac317509fd61741a19276a6764a1c2bfce
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319350"
---
# <a name="set-entity-sql"></a>SET(Entity SQL)
SET 식은 중복 요소가 모두 제거된 새 컬렉션을 생성하여 개체 컬렉션을 집합으로 변환하는 데 사용됩니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
SET ( expression )  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 컬렉션을 반환하는 모든 유효한 쿼리 식입니다.  
  
## <a name="remarks"></a>주의  
 집합 식 `SET(c)` 는 다음 select 문과 논리적으로 같습니다.  
  
```sql  
SELECT VALUE DISTINCT c FROM c  
```  
  
 `SET` 는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다. 모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다. @No__t_1 집합 연산자의 우선 순위 정보는 [예외](except-entity-sql.md) 를 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 SET 식을 사용하여 개체의 컬렉션을 집합으로 변환합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [방법: PrimitiveType 결과를 반환 하는 쿼리 실행](../how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#SET](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#set)]  
  
## <a name="see-also"></a>참조

- [엔터티 SQL 참조](entity-sql-reference.md)
