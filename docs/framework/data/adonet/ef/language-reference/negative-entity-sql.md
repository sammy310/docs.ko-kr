---
title: '- 양수 (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 7716b9115587a873531be9c14b7da93c7a148ed8
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319532"
---
# <a name="--negative-entity-sql"></a>- (부정)(Entity SQL)
숫자 식의 음수 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
- expression  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 숫자 데이터 형식의 유효한 식입니다.  
  
## <a name="result-types"></a>결과 형식  
 `expression`의 데이터 형식입니다.  
  
## <a name="remarks"></a>주의  
 `expression` 이 부호 없는 형식이면 결과 형식은 `expression`의 형식과 가장 밀접하게 관련된 부호 있는 형식이 됩니다. `expression` 이 Byte 형식이면 Int16 형식의 값이 반환됩니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 - 산술 연산자를 사용하여 숫자 식의 음수 값을 반환합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#NEGATIVE](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#negative)]  
  
## <a name="see-also"></a>참조

- [엔터티 SQL 참조](entity-sql-reference.md)
