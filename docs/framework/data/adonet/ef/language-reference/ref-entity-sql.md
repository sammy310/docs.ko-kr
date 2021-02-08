---
description: '자세히 알아보기: 참조 (Entity SQL)'
title: REF(Entity SQL)
ms.date: 03/30/2017
ms.assetid: c5f4cb35-69e9-44cc-b63b-ee38922bbda1
ms.openlocfilehash: 05f87ce8027e8e095722eb13d39f3f13d56f6faa
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802062"
---
# <a name="ref-entity-sql"></a>REF(Entity SQL)

엔터티 인스턴스에 대한 참조를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
REF( expression )
```  
  
## <a name="arguments"></a>인수  

 `expression`  
 엔터티 형식의 인스턴스를 생성하는 모든 유효한 식입니다.  
  
## <a name="return-value"></a>Return Value  

 지정한 엔터티 인스턴스에 대한 참조입니다.  
  
## <a name="remarks"></a>설명  

 엔터티 참조는 엔터티 키와 엔터티 집합 이름으로 구성됩니다. 여러 엔터티 집합이 같은 엔터티 형식을 기반으로 할 수 있으므로 특정 엔터티 키가 여러 엔터티 집합에 나타날 수 있습니다. 하지만 엔터티 참조는 항상 고유합니다. 입력 식이 보관된 엔터티를 나타내는 경우 이 엔터티에 대한 참조가 반환됩니다. 입력 식이 보관된 엔터티가 아닌 경우 Null 참조가 반환됩니다.  
  
 속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스하면 해당 참조가 자동으로 역참조됩니다.  
  
## <a name="example"></a>예제  

 다음 Entity SQL 쿼리는 REF 연산자를 사용하여 입력 엔터티 인수에 대한 참조를 반환합니다. 속성 추출 연산자(.)를 사용하여 Product 엔터티의 속성에 액세스하고 있으므로 같은 쿼리에서 참조를 역참조합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [방법: PrimitiveType 결과를 반환 하는 쿼리 실행](../how-to-execute-a-query-that-returns-primitivetype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecutePrimitiveTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-sql[DP EntityServices Concepts#REF](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#ref)]  
  
## <a name="see-also"></a>참고 항목

- [DEREF](deref-entity-sql.md)
- [CREATEREF](createref-entity-sql.md)
- [KEY](key-entity-sql.md)
- [엔터티 SQL 참조](entity-sql-reference.md)
- [형식 정의](type-definitions-entity-sql.md)
