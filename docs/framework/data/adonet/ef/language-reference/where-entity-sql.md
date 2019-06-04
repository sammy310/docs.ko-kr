---
title: WHERE(Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: 939d4c0ec2c30bc71b22fb65ab36644e063f97de
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66489855"
---
# <a name="where-entity-sql"></a>WHERE(Entity SQL)
WHERE 절 바로 다음에 적용 되는 [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md) 절.  
  
## <a name="syntax"></a>구문  
  
```  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>인수  
 `expression`  
 Boolean 형식입니다.  
  
## <a name="remarks"></a>설명  
 WHERE 절 TRANSACT-SQL에 대 한 설명 된 대로 동일한 의미 체계를 가집니다. WHERE 절은 원본 컬렉션의 요소를 조건 전달 요소로 제한하는 방식으로 쿼리 식에 의해 생성되는 개체를 제한합니다.  
  
```  
select c from cs as c where e  
```  
  
 식 `e`에는 부운 형식이 있어야 합니다.  
  
 WHERE 절은 FROM 절 바로 다음에, 모든 그룹화나 정렬 또는 프로젝션 이전에 적용됩니다. FROM 절에 정의된 모든 요소 이름은 WHERE 절 식에 표시됩니다.  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
- [쿼리 식](../../../../../../docs/framework/data/adonet/ef/language-reference/query-expressions-entity-sql.md)
