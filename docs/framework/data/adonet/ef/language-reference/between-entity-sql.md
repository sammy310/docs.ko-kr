---
title: BETWEEN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 4dcdd754-ae01-4e78-bf28-8a117fb2b73e
ms.openlocfilehash: 2c411fd7fcac9d98323d5fcfb1874f98bc664991
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59225263"
---
# <a name="between-entity-sql"></a>BETWEEN(Entity SQL)
식의 결과 값이 지정된 범위에 속하는지 여부를 결정합니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] BETWEEN 식의 기능은 Transact-SQL BETWEEN 식의 기능과 동일합니다.  
  
## <a name="syntax"></a>구문  
  
```  
expression [ NOT ] BETWEEN begin_expression AND end_expression    
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 `begin_expression`과 `end_expression`으로 정의된 범위 내에서 테스트할 모든 유효한 식입니다. `expression` 두 가지 모두 동일한 형식 이어야 합니다 `begin_expression` 고 `end_expression`입니다.  
  
 `begin_expression`  
 모든 유효한 식입니다. `begin_expression` 두 가지 모두 동일한 형식 이어야 합니다 `expression` 고 `end_expression`입니다. `begin_expression` 해야 미만 `end_expression`, 그렇지 않으면 반환 값이 무효화 됩니다.  
  
 `end_expression`  
 모든 유효한 식입니다. `end_expression` 두 가지 모두 동일한 형식 이어야 합니다 `expression` 고 `begin_expression`입니다.  
  
 NOT  
 BETWEEN의 결과를 무효화하도록 지정합니다.  
  
 AND  
 `expression`이 `begin_expression`과 `end_expression` 범위 내에 있어야 함을 나타내는 자리 표시자 역할을 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 하는 경우 `expression` 범위 사이 `begin_expression` 하 고 `end_expression`이 고, 그렇지 않으면 `false`합니다. `null` 경우에 반환 됩니다 `expression` 됩니다 `null` 이거나 `begin_expression` 또는 `end_expression` 는 `null`.  
  
## <a name="remarks"></a>설명  
 배타적 범위를 지정 하려면 BETWEEN 대신 보다 큼 (>) 및 미만 (<) 연산자를 사용 합니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 BETWEEN 연산자를 사용하여 식의 결과 값이 지정된 범위에 속하는지 여부를 결정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#BETWEEN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#between)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
