---
title: '|| (OR) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 8e649648-eb9a-4380-9d74-36e62260628c
ms.openlocfilehash: 6437b17fe1c1277701f06988ef6c02f4caf70e62
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319463"
---
# <a name="-or-entity-sql"></a>|| (OR) (Entity SQL)
두 `Boolean` 식을 결합합니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
boolean_expression OR boolean_expression  
-- or   
boolean_expression || boolean_expression  
```  
  
## <a name="arguments"></a>인수  
 `boolean_expression`  
 `Boolean`을 반환하는 유효한 식입니다.  
  
## <a name="return-value"></a>반환 값  
 조건 중 하나가`true` 이면 `true`이고 그렇지 않으면 `false`입니다.  
  
## <a name="remarks"></a>주의  
 OR는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 논리 연산자로 두 조건을 결합할 때 사용됩니다. 한 문에 논리 연산자를 둘 이상 사용하는 경우 OR 연산자가 AND 연산자 다음에 계산됩니다. 그러나 괄호를 사용하면 계산 순서를 변경할 수 있습니다.  
  
 이중 세로 막대 (&#124;&#124;)에는 OR 연산자와 동일한 기능이 있습니다.  
  
 다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|true|true|  
|`FALSE`|true|false|NULL|  
|`NULL`|true|NULL|NULL|  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 OR 연산자를 사용하여 두 `Boolean` 식을 결합합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts 2#OR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#or)]  
  
## <a name="see-also"></a>참조

- [엔터티 SQL 참조](entity-sql-reference.md)
