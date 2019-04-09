---
title: FLATTEN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 1a670c63-0a29-4738-80e6-101f66af05c3
ms.openlocfilehash: 76fba91f27479df19bbc4ac6e120d615a16f1d42
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59115117"
---
# <a name="flatten-entity-sql"></a>FLATTEN(Entity SQL)
여러 컬렉션의 컬렉션을 하나의 결합된 컬렉션으로 변환합니다. 새 컬렉션에는 기존 컬렉션과 동일한 요소가 모두 포함되지만 중첩 구조는 포함되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
FLATTEN ( collection )  
```  
  
## <a name="arguments"></a>인수  
 `collection`  
 하나의 컬렉션으로 결합할 여러 값 컬렉션의 컬렉션을 반환하는 유효한 식입니다.  
  
## <a name="remarks"></a>설명  
 `FLATTEN` 중 하나인는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 연산자를 설정 합니다. 모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다. 참조 [EXCEPT](../../../../../../docs/framework/data/adonet/ef/language-reference/except-entity-sql.md) 에 대 한 우선 순위 정보는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자입니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 `FLATTEN` 연산자를 사용하여 여러 컬렉션의 컬렉션을 하나의 결합된 컬렉션으로 변환합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#FLATTEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#flatten)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
