---
title: IN(Entity SQL)
ms.date: 03/30/2017
ms.assetid: 51662950-ee01-4857-b7b9-311dd8515966
ms.openlocfilehash: f4fa8cbc07513321e59b93503b59af172c0a6f05
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59211324"
---
# <a name="in-entity-sql"></a>IN(Entity SQL)
컬렉션에 일치하는 값이 있는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
value [ NOT ] IN expression  
```  
  
## <a name="arguments"></a>인수  
 `value`  
 일치시킬 값을 반환하는 모든 유효한 식입니다.  
  
 [NOT]  
 IN의 `Boolean` 결과를 부정하도록 지정합니다.  
  
 `expression`  
 일치 여부를 테스트할 컬렉션을 반환하는 모든 유효한 식입니다. 모든 식은 형식이 같거나 기본 형식 또는 파생 형식이 `value`이어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 `true` 값이 컬렉션에 있으면 컬렉션 또는 null 값이 null 이면 null;입니다. 그렇지 않으면 `false`합니다. NOT IN을 사용하면 IN의 결과가 부정됩니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 IN 연산자를 사용하여 컬렉션에 일치하는 값이 있는지 여부를 결정합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#IN](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#in)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
