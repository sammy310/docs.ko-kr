---
description: '다음에 대 한 자세한 정보: >= (크거나 같음) (Entity SQL)'
title: '>=(보다 크거나 같음)(Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 70780ac4-0123-4da8-b731-8af856daffe3
ms.openlocfilehash: d05685123e3262a2d2ae01553c7c5334a7e53c40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786279"
---
# <a name="-greater-than-or-equal-to-entity-sql"></a>>= (크거나 같음) (Entity SQL)

두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같은지 여부를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
expression >= expression  
```  
  
## <a name="arguments"></a>인수  

 `expression`  
 유효한 식입니다. 두 식은 모두 암시적으로 변환 가능한 데이터 형식이어야 합니다.  
  
## <a name="result-types"></a>결과 형식  

 왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같으면`true` 이고, 그렇지 않으면 `false`입니다.  
  
## <a name="example"></a>예제  

 다음 Entity SQL 쿼리는 >= 비교 연산자를 통해 두 식을 비교하여 왼쪽 식의 값이 오른쪽 식의 값보다 크거나 같은지 여부를 결정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#GREATER_OR_EQUALS](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#greater_or_equals)]  
  
## <a name="see-also"></a>참고 항목

- [엔터티 SQL 참조](entity-sql-reference.md)
