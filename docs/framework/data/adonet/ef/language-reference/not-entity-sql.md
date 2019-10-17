---
title: '! (NOT)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: a1447a34-df06-4393-93c3-0612ebd41abc
ms.openlocfilehash: 7755219c5238f78e59332c508643fe2ae1f5096f
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319525"
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
  
## <a name="remarks"></a>주의  
 느낌표(!)는 NOT 연산자와 같은 기능을 합니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 NOT 연산자를 사용하여 `Boolean` 식을 부정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#NOT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#not)]  
  
## <a name="see-also"></a>참조

- [엔터티 SQL 참조](entity-sql-reference.md)
