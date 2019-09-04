---
title: EXISTS(Entity SQL)
ms.date: 03/30/2017
ms.assetid: d28ead43-4afb-4bdc-af64-efd2e05005d7
ms.openlocfilehash: 20e18bf536f2b89eca9515b3c5dca7ca7fbd6fe5
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70250986"
---
# <a name="exists-entity-sql"></a>EXISTS(Entity SQL)
컬렉션이 비어 있는지 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[NOT] EXISTS ( expression )  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 컬렉션을 반환하는 모든 유효한 식입니다.  
  
 NOT  
 EXISTS의 결과를 부정하도록 지정합니다.  
  
## <a name="return-value"></a>반환 값  
 컬렉션이 비어 있지 않으면 `true`이고 비어 있으면 `false`입니다.  
  
## <a name="remarks"></a>설명  
 EXISTS는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자 중 하나입니다. 모든 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자는 왼쪽에서 오른쪽으로 계산됩니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 집합 연산자의 우선 순위에 대 한 자세한 내용은 [EXCEPT](except-entity-sql.md)를 참조 하십시오.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 EXISTS 연산자를 사용하여 컬렉션이 비어 있는지 확인합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [방법: StructuralType 결과](../how-to-execute-a-query-that-returns-structuraltype-results.md)를 반환 하는 쿼리를 실행 합니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#EXISTS](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#exists)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](entity-sql-reference.md)
