---
title: OVERLAPS(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 41743e89-79cb-4d7b-8a27-355b45024b61
ms.openlocfilehash: 9d909fb7efbb29619351cfc866b0f84381d0b80b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760274"
---
# <a name="overlaps-entity-sql"></a>OVERLAPS(Entity SQL)
두 컬렉션에 공통 요소가 있는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
expression OVERLAPS expression  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 다른 쿼리 식에서 반환된 컬렉션과 비교할 컬렉션을 반환하는 모든 유효한 쿼리 식입니다. 모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `expression`이어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 두 컬렉션에 공통 요소가 있으면`true` 이고, 그렇지 않으면 `false`입니다.  
  
## <a name="remarks"></a>설명  
 OVERLAPS 제공 기능적으로 다음에 해당을 합니다.  
  
 `EXISTS ( expression INTERSECT expression )`  
  
 OVERLAPS는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다. 모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다. 우선 순위에 대 한 정보를 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자를 참조 하십시오 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md)합니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 OVERLAPS 연산자를 사용하여 두 컬렉션에 공통 값이 있는지 여부를 결정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. 절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#OVERLAPS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#overlaps)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
