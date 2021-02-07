---
description: '자세히 알아보기: WHERE (Entity SQL)'
title: WHERE(Entity SQL)
ms.date: 03/30/2017
ms.assetid: a8e1061e-0028-4a6f-8f19-b9f48e96c4b8
ms.openlocfilehash: e094a93927f6ac77aef772654f1d8d4fcf999cbd
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712872"
---
# <a name="where-entity-sql"></a>WHERE(Entity SQL)

WHERE 절은 [FROM](from-entity-sql.md) 절 바로 뒤에 적용 됩니다.  
  
## <a name="syntax"></a>구문  
  
```sql  
[ WHERE expression ]  
```  
  
## <a name="arguments"></a>인수  

 `expression`  
 Boolean 형식입니다.  
  
## <a name="remarks"></a>설명  

 WHERE 절에는 Transact-sql에 대해 설명한 것과 동일한 의미 체계가 있습니다. WHERE 절은 원본 컬렉션의 요소를 조건 전달 요소로 제한하는 방식으로 쿼리 식에 의해 생성되는 개체를 제한합니다.  
  
```sql  
select c from cs as c where e  
```  
  
 식 `e`에는 부운 형식이 있어야 합니다.  
  
 WHERE 절은 FROM 절 바로 다음에, 모든 그룹화나 정렬 또는 프로젝션 이전에 적용됩니다. FROM 절에 정의된 모든 요소 이름은 WHERE 절 식에 표시됩니다.  
  
## <a name="see-also"></a>참고 항목

- [엔터티 SQL 참조](entity-sql-reference.md)
- [쿼리 식](query-expressions-entity-sql.md)
