---
title: ISOF(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 5b2b0d34-d0a7-4bcd-baf2-58aa8456d00b
ms.openlocfilehash: 097d6e7d452ee62a2c8934d2c5fcfdddbeaffc73
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61772374"
---
# <a name="isof-entity-sql"></a>ISOF(Entity SQL)
식의 형식이 지정된 형식 또는 그 하위 형식인지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
expression IS [ NOT ] OF ( [ ONLY ] type )  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 형식을 결정할 수 있는 모든 유효한 쿼리 식입니다.  
  
 NOT  
 IS OF의 EDM.Boolean 결과를 부정합니다.  
  
 ONLY  
 `true`이 `expression` 형식이며 그 하위 형식이 아닌 경우에만 IS OF가 `type`를 반환하도록 지정합니다.  
  
 `type`  
 `expression`을 테스트할 형식입니다. 형식은 네임스페이스로 한정되어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true`이 T 형식이며 T가 기본 형식이거나 `expression`의 파생 형식인 경우 `type`이고, `expression`이 런타임에 null인 경우 null이며, 그 이외의 경우 `false`입니다.  
  
## <a name="remarks"></a>설명  
 식을 `expression IS NOT OF (type)` 하 고 `expression IS NOT OF (ONLY type)` 하는 구문은 동일 `NOT (expression IS OF (type))` 및 `NOT (expression IS OF (ONLY type))`각각.  
  
 다음 표에서는 일반 패턴 및 비교적 특수한 패턴에 대한 `IS OF` 연산자의 동작을 보여 줍니다. 공급자 호출 이전에 모든 예외가 클라이언트 측에서 throw됩니다.  
  
|무늬|동작|  
|-------------|--------------|  
|null IS OF(EntityType)|Throw|  
|null IS OF(ComplexType)|Throw|  
|null IS OF(RowType)|Throw|  
|TREAT(null AS EntityType) IS OF(EntityType)|DBNull 반환|  
|TREAT(null AS ComplexType) IS OF(ComplexType)|Throw|  
|TREAT(null AS RowType) IS OF(RowType)|Throw|  
|EntityType IS OF(EntityType)|true/false 반환|  
|ComplexType IS OF(ComplexType)|Throw|  
|RowType IS OF(RowType)|Throw|  
  
## <a name="example"></a>예제  
 다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에서는 IS OF 연산자를 사용하여 쿼리 식의 형식을 결정한 다음 TREAT 연산자를 사용하여 Course 형식의 개체를 OnsiteCourse 형식의 개체 컬렉션으로 변환합니다. 쿼리는 [School 모델](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/bb896300(v=vs.100))을 기반으로 합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#TREAT_ISOF](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#treat_isof)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
