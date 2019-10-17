---
title: '- 빼는 (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: bc4327f9-09c0-438f-a008-927c5c478040
ms.openlocfilehash: fe9152100bddac86f3fb7fae1ab3c0b81ae58418
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72319321"
---
# <a name="--subtract-entity-sql"></a>- (빼기)(Entity SQL)
두 숫자를 뺍니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
expression - expression  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 숫자 데이터 형식의 유효한 식입니다.  
  
## <a name="result-types"></a>결과 형식  
 두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다. 암시적 형식 승격에 대 한 자세한 내용은 [형식 시스템](type-system-entity-sql.md)을 참조 하세요.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 - 산술 연산자를 사용하여 두 숫자를 뺍니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#SUBTRACT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#subtract)]  
  
## <a name="see-also"></a>참조

- [엔터티 SQL 참조](entity-sql-reference.md)
