---
title: '&amp;&amp; (및) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: e7d24213-471d-4807-b85e-570375df89b5
ms.openlocfilehash: be6e7120e6c19714f151aa38a8b9a1355de29d1a
ms.sourcegitcommit: ad800f019ac976cb669e635fb0ea49db740e6890
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/29/2019
ms.locfileid: "73039958"
---
# <a name="ampamp-and-entity-sql"></a>&amp;&amp; (및) (Entity SQL)
두 식이 `true` 이면 `true`를 반환하고, 그렇지 않으면 `false` 또는 `NULL`을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```csharp  
boolean_expression AND boolean_expression
```
 
or  

```csharp
boolean_expression && boolean_expression  
```  
  
## <a name="arguments"></a>인수  
 `boolean_expression`  
 부울을 반환하는 모든 유효한 식입니다.  
  
## <a name="remarks"></a>주의  
 이중 앰퍼샌드(&&)는 AND 연산자와 같은 기능을 합니다.  
  
 다음 표에서는 가능한 입력 값과 반환 형식을 보여 줍니다.  
  
||`TRUE`|`FALSE`|`NULL`|  
|-|------------|-------------|------------|  
|`TRUE`|true|false|NULL|  
|`FALSE`|false|false|false|  
|`NULL`|NULL|false|NULL|  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 AND 연산자를 사용하는 방법을 보여 줍니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#AND](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#and)]  
  
## <a name="see-also"></a>참조

- [엔터티 SQL 참조](entity-sql-reference.md)
