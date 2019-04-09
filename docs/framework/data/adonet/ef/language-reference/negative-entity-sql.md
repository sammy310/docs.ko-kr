---
title: '- (음수) (Entity SQL)'
ms.date: 03/30/2017
ms.assetid: 208e54ef-4741-4ec5-89d6-6ff700863cb0
ms.openlocfilehash: 343f53b2a6fc54a5be6f8673348384567b48262b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59102845"
---
# <a name="--negative-entity-sql"></a>- (부정)(Entity SQL)
숫자 식의 음수 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
- expression  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 숫자 데이터 형식의 유효한 식입니다.  
  
## <a name="result-types"></a>결과 형식  
 `expression`의 데이터 형식입니다.  
  
## <a name="remarks"></a>설명  
 `expression` 이 부호 없는 형식이면 결과 형식은 `expression`의 형식과 가장 밀접하게 관련된 부호 있는 형식이 됩니다. `expression` 이 Byte 형식이면 Int16 형식의 값이 반환됩니다.  
  
## <a name="example"></a>예제  
 다음 Entity SQL 쿼리에서는 - 산술 연산자를 사용하여 숫자 식의 음수 값을 반환합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1.  절차에 따라 [방법: StructuralType 결과 반환 하는 쿼리 실행](../../../../../../docs/framework/data/adonet/ef/how-to-execute-a-query-that-returns-structuraltype-results.md)합니다.  
  
2.  다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#NEGATIVE](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#negative)]  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
