---
description: 자세히 알아보기:에서 (Entity SQL)
title: IN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: 234ed15430e44d12d4ca7c98fcb4a7bc03d117f9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99748598"
---
# <a name="in-entity-sql"></a>IN(Entity SQL)

컬렉션에 일치하는 값이 있는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>인수  

 `value`  
 일치시킬 값을 반환하는 모든 유효한 식입니다.  
  
 [NOT]  
 IN의 `Boolean` 결과를 부정하도록 지정합니다.  
  
 `expression`  
 일치 여부를 테스트할 컬렉션을 반환하는 모든 유효한 식입니다. 모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `value`이어야 합니다.  
  
## <a name="return-value"></a>Return Value  

 값이 컬렉션에 있으면 `true`이고, 값 또는 컬렉션이 null이면 null이고, 그렇지 않으면 `false`입니다. NOT IN을 사용하면 IN의 결과가 부정됩니다.  
  
## <a name="example"></a>예제  

 다음 Entity SQL 쿼리에서는 IN 연산자를 사용하여 컬렉션에 일치하는 값이 있는지 여부를 결정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#IN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#in)]  
  
## <a name="see-also"></a>참고 항목

- [엔터티 SQL 참조](entity-sql-reference.md)
