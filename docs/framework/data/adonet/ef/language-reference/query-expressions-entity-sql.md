---
description: '자세한 정보: 쿼리 식 (Entity SQL)'
title: 쿼리 식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 218e7db0e812bd43a92d3145bc4bf96244ef6a3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696037"
---
# <a name="query-expressions-entity-sql"></a>쿼리 식(Entity SQL)

쿼리 식은 다양한 쿼리 연산자를 단일 구문에 결합합니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 는 [리터럴](literals-entity-sql.md), [매개 변수](parameters-entity-sql.md), [변수](variables-entity-sql.md), 연산자, [함수](functions-entity-sql.md), 집합 연산자 등을 비롯 한 다양 한 종류의 식을 제공 합니다. 자세한 내용은 [Entity SQL 참조](entity-sql-reference.md)를 참조 하세요.  
  
## <a name="clauses"></a>절  

 쿼리 식은 개체 컬렉션에 연속적인 연산을 적용하는 일련의 절로 구성되어 있으며, [Select](select-entity-sql.md), [FROM](from-entity-sql.md), [WHERE](where-entity-sql.md), [GROUP by](group-by-entity-sql.md), [HAVING](having-entity-sql.md)및 [ORDER BY](order-by-entity-sql.md)표준의 SQL select 문에 있는 동일한 절을 기반으로 합니다.  
  
## <a name="scope"></a>Scope  

 FROM 절에 정의된 이름이 나타나는 순서대로 왼쪽에서 오른쪽 순으로 FROM 범위에 제공됩니다. JOIN 목록에서 식은 목록에서 앞쪽에 정의된 이름을 참조할 수 있습니다. FROM 절에서 식별된 요소의 공용 속성은 FROM 범위에 추가되지 않으며 항상 정규화된 별칭 이름을 통해 참조해야 합니다. 일반적으로 select 식의 모든 부분은 FROM 범위 내에 있는 것으로 간주됩니다.  
  
## <a name="see-also"></a>참고 항목

- [엔터티 SQL 참조](entity-sql-reference.md)
