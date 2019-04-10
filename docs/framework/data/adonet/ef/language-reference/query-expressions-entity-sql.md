---
title: 쿼리 식(Entity SQL)
ms.date: 03/30/2017
ms.assetid: c36f327b-e230-48d4-bbd5-78dc6478c447
ms.openlocfilehash: 5f89028b9c501dd840f1dc9445418e4757967db8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59146915"
---
# <a name="query-expressions-entity-sql"></a>쿼리 식(Entity SQL)
쿼리 식은 다양한 쿼리 연산자를 단일 구문에 결합합니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 식에서 다음을 비롯 한 다양 한 종류를 제공 합니다. [리터럴](../../../../../../docs/framework/data/adonet/ef/language-reference/literals-entity-sql.md), [매개 변수](../../../../../../docs/framework/data/adonet/ef/language-reference/parameters-entity-sql.md), [변수](../../../../../../docs/framework/data/adonet/ef/language-reference/variables-entity-sql.md), 연산자 [함수](../../../../../../docs/framework/data/adonet/ef/language-reference/functions-entity-sql.md)집합 연산자, 및 등입니다. 자세한 내용은 [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)합니다.  
  
## <a name="clauses"></a>절  
 쿼리 식은 개체 컬렉션에 연속적인 연산을 적용하는 일련의 절로 구성되어 있으며, 표준 SQL select 문에서와 동일한 절인 [선택](../../../../../../docs/framework/data/adonet/ef/language-reference/select-entity-sql.md), [FROM](../../../../../../docs/framework/data/adonet/ef/language-reference/from-entity-sql.md), [여기서](../../../../../../docs/framework/data/adonet/ef/language-reference/where-entity-sql.md)를 [그룹화](../../../../../../docs/framework/data/adonet/ef/language-reference/group-by-entity-sql.md)를 [HAVING](../../../../../../docs/framework/data/adonet/ef/language-reference/having-entity-sql.md), 및 [ORDER BY](../../../../../../docs/framework/data/adonet/ef/language-reference/order-by-entity-sql.md)합니다.  
  
## <a name="scope"></a>범위  
 FROM 절에 정의된 이름이 나타나는 순서대로 왼쪽에서 오른쪽 순으로 FROM 범위에 제공됩니다. JOIN 목록에서 식은 목록에서 앞쪽에 정의된 이름을 참조할 수 있습니다. FROM 절에서 식별된 요소의 공용 속성은 FROM 범위에 추가되지 않으며 항상 정규화된 별칭 이름을 통해 참조해야 합니다. 일반적으로 select 식의 모든 부분은 FROM 범위 내에 있는 것으로 간주됩니다.  
  
## <a name="see-also"></a>참고자료

- [엔터티 SQL 참조](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-reference.md)
