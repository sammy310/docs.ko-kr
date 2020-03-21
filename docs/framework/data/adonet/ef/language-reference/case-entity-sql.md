---
title: CASE(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 26a47873-e87d-4ba2-9e2c-3787c21efe89
ms.openlocfilehash: 58b21d3be8e13a0a2204a4fd6d355f734207c509
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150469"
---
# <a name="case-entity-sql"></a>CASE(Entity SQL)
`Boolean` 식 집합을 계산하여 결과를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```csharp  
CASE  
     WHEN Boolean_expression THEN result_expression
    [ ...n ]
     [
    ELSE else_result_expression
     ]
END  
```  
  
## <a name="arguments"></a>인수  
 `n`  
 여러 WHEN `Boolean_expression` THEN `result_expression` 절을 사용할 수 있음을 나타내는 자리 표시자입니다.  
  
 THEN `result_expression`  
 `Boolean_expression` 이 `true`인 경우에 반환되는 식입니다. `result expression` 은 유효한 식입니다.  
  
 ELSE `else_result_expression`  
 `true`인 비교 연산이 없는 경우 반환되는 식입니다. 이 인수가 생략되고 `true`인 비교 연산이 없는 경우 CASE는 null을 반환합니다. `else_result_expression` 은 유효한 식입니다. `else_result_expression` 과 `result_expression` 의 데이터 형식은 동일하거나 암시적으로 변환되어야 합니다.  
  
 WHEN `Boolean_expression`  
 검색된 CASE 형식을 사용할 때 계산되는 `Boolean` 식입니다. `Boolean_expression` 은 유효한 `Boolean` 식입니다.  
  
## <a name="return-value"></a>Return Value  
 `result_expression` 과 선택적 요소인 `else_result_expression`의 형식 집합에서 우선 순위가 가장 높은 형식을 반환합니다.  
  
## <a name="remarks"></a>설명  
 대/소문자 식은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] Transact-SQL 대/소문자 식과 유사합니다. CASE 식을 사용하면 적절한 결과를 생성하는 식을 결정하는 일련의 조건 테스트를 만들 수 있습니다. 이러한 CASE 식 형식은 하나 이상으로 구성된 일련의 `Boolean` 식에 적용되어 올바른 결과 식을 결정합니다.  
  
 CASE 함수는 지정된 순서대로 각 WHEN 절에 대해 `Boolean_expression` 을 계산한 다음 `result_expression` 인 첫 번째 `Boolean_expression` 의 `true`을 반환합니다. 나머지 식은 계산되지 않습니다. `Boolean_expression` 인 `true`이 없으면 ELSE 절이 지정된 경우 데이터베이스 엔진에서 `else_result_expression` 을 반환하고 ELSE 절이 지정되지 않은 경우 null 값을 반환합니다.  
  
 CASE 문은 multiset을 반환할 수 없습니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 결과를 결정하기 위해 CASE 식을 사용하여 일련의 `Boolean` 식을 계산합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [방법: PrimitiveType 결과를 반환하는 쿼리 실행의 절차를 따릅니다.](../how-to-execute-a-query-that-returns-primitivetype-results.md)  
  
2. 다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#CASE_WHEN_THEN_ELSE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#case_when_then_else)]  
  
## <a name="see-also"></a>참고 항목

- [THEN](then-entity-sql.md)
- [선택](select-entity-sql.md)
- [엔터티 SQL 참조](entity-sql-reference.md)
