---
title: ISNULL(Entity SQL)
ms.date: 03/30/2017
ms.assetid: dc7a0173-3664-4c90-a57b-5cbb0a8ed7ee
ms.openlocfilehash: 3360ad4ca7306a8cc1b7d6948204f825ff9a93c6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203620"
---
# <a name="isnull-entity-sql"></a>ISNULL(Entity SQL)

쿼리 식이 null인지 여부를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
expression IS [ NOT ] NULL  
```  
  
## <a name="arguments"></a>인수  

 `expression`  
 모든 유효한 쿼리 식입니다. 컬렉션이거나, 컬렉션 멤버를 포함하거나, 컬렉션 형식 속성을 가진 레코드 형식일 수 없습니다.  
  
 NOT  
 IS NULL의 EDM 부울 결과를 부정합니다.  
  
## <a name="return-value"></a>반환 값  

 `true`이 null을 반환하면 `expression`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="remarks"></a>설명  

 외부 조인의 요소가 null인지 여부를 확인하려면 `IS NULL`을 사용합니다.  
  
```sql  
select c
      from LOB.Customers as c left outer join LOB.Orders as o
                              on c.ID = o.CustomerID
      where o is not null and o.OrderQuantity = @x  
```  
  
 멤버에 실제 값이 있는지 여부를 확인하려면 `IS NULL`을 사용합니다.  
  
```sql  
select c from LOB.Customer as c where c.DOB is not null  
```  
  
 다음 표에서는 일부 패턴에 대한 `IS NULL`의 동작을 보여 줍니다. 공급자 호출 이전에 모든 예외가 클라이언트 측에서 throw됩니다.  
  
|무늬|동작|  
|-------------|--------------|  
|null IS NULL|`true`를 반환합니다.|  
|TREAT (null AS EntityType) IS NULL|`true`를 반환합니다.|  
|TREAT (null AS ComplexType) IS NULL|오류를 throw합니다.|  
|TREAT (null AS RowType) IS NULL|오류를 throw합니다.|  
|EntityType IS NULL|`true` 또는 `false`을 반환합니다.|  
|ComplexType IS NULL|오류를 throw합니다.|  
|RowType IS NULL|오류를 throw합니다.|  
  
## <a name="example"></a>예제  

 다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 IS NOT NULL 연산자를 사용하여 쿼리 식이 null이 아닌지 여부를 확인합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#ISNULL](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#isnull)]  
  
## <a name="see-also"></a>참고 항목

- [엔터티 SQL 참조](entity-sql-reference.md)
