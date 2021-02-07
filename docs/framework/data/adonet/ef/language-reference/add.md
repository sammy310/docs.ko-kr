---
description: '자세히 알아보기: + (추가)'
title: + (추가)
ms.date: 03/30/2017
ms.assetid: 51769b02-a8f7-4177-9e99-bbd10e77092c
ms.openlocfilehash: b8ec9f50b349fe971513f399b7e9984e9044cf58
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697311"
---
# <a name="-add"></a>+ (추가)

두 숫자를 더합니다.  
  
## <a name="syntax"></a>구문  
  
```csharp  
expression + expression  
```  
  
## <a name="arguments"></a>인수  

 `expression`  
 숫자 데이터 형식의 유효한 식입니다.  
  
## <a name="result-types"></a>결과 형식  

 두 인수에 대해 암시적 형식 승격을 수행한 결과 데이터 형식입니다. 암시적 형식 승격에 대 한 자세한 내용은 [형식 시스템](type-system-entity-sql.md)을 참조 하세요.  
  
## <a name="remarks"></a>설명  

 EDM.String 형식의 경우 더하기는 연결입니다.  
  
## <a name="example"></a>예제  

 다음 Entity SQL 쿼리에서는 + 산술 연산자를 사용하여 두 숫자를 더합니다. 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다. 이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.  
  
1. [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.  
  
2. 다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.  
  
 [!code-csharp[DP EntityServices Concepts 2#ADD](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts 2/cs/entitysql.cs#add)]  
  
## <a name="see-also"></a>참고 항목

- [엔터티 SQL 참조](entity-sql-reference.md)
- [개념적 모델 형식(CSDL)](/ef/ef6/modeling/designer/advanced/edmx/csdl-spec#conceptual-model-types-csdl)
