---
title: Entity SQL과 Transact-SQL의 차이점
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 299cb9bbe90c72619cf809a8fc673fca456bd6fd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150233"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Entity SQL과 Transact-SQL의 차이점
이 항목에서는 TRANSact-SQL간의 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 차이점에 대해 설명합니다.  
  
## <a name="inheritance-and-relationships-support"></a>상속 및 관계 지원  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]은 개념적 엔터티 스키마를 직접 다루며 상속 및 관계와 같은 개념적 모델 기능을 지원합니다.  
  
 상속 작업을 할 때 상위 형식 인스턴스 컬렉션에서 하위 형식의 인스턴스를 선택하는 것이 유용할 때가 많습니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 [oftype](oftype-entity-sql.md) 연산자 (C#시퀀스의 `oftype`와 유사)는이 기능을 제공합니다.  
  
## <a name="support-for-collections"></a>컬렉션 지원  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 컬렉션을 고급 엔터티로 취급합니다. 다음은 그 예입니다.  
  
- 컬렉션 식은 `from` 절에서 유효합니다.  
  
- 하위 쿼리 `in` 및 `exists`는 모든 컬렉션을 허용하도록 일반화되었습니다.  
  
     하위 쿼리는 일종의 컬렉션입니다. `e1 in e2` 및 `exists(e)`는 이러한 작업을 수행하는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 구문입니다.  
  
- 컬렉션에 대해 `union`, `intersect`, `except` 등의 Set 작업이 수행됩니다.  
  
- 컬렉션에 조인이 수행됩니다.  
  
## <a name="support-for-expressions"></a>식 지원  
 Transact-SQL에는 하위 쿼리(테이블) 및 식(행 및 열)이 있습니다.  
  
 컬렉션 및 중첩 된 컬렉션을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 지원 하기 위해 모든 것을 식으로 만듭니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]은 Transact-SQL보다 더 구성가능하며 모든 표현식을 어디서나 사용할 수 있습니다. 쿼리 식은 항상 프로젝션된 형식의 컬렉션을 생성하며, 컬렉션 식이 허용된 곳이라면 어디서든 쿼리 식을 사용할 수 있습니다. 에서 지원되지 않는 Transact-SQL 식에 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]대한 자세한 내용은 [지원되지 않는 식을](unsupported-expressions-entity-sql.md)참조하십시오.  
  
 다음은 모두 유효한 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리입니다.  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>일관된 하위 쿼리 처리  
 테이블에 중점을 두는 Transact-SQL은 하위 쿼리의 컨텍스트 해석을 수행합니다. 예를 들어, `from` 절의 하위 쿼리는 multiset(테이블)로 간주됩니다. 하지만 동일한 하위 쿼리가 `select` 절에서 사용되면 스칼라 하위 쿼리로 간주됩니다. 마찬가지로 `in` 연산자의 왼쪽에 사용되는 하위 쿼리는 스칼라 하위 쿼리로 간주되고 오른쪽은 다중 집합 하위 쿼리로 간주됩니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 구별이 없습니다. 식은 사용되는 컨텍스트와 관계없이 일관성 있게 해석되며 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]모든 하위 쿼리를 다중 집합 하위 쿼리로 간주합니다. 하위 쿼리에서 스칼라 값이 필요한 경우, [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 컬렉션(여기서는 하위 쿼리)에 대해 작동하는 `anyelement` 연산자를 제공하여 컬렉션으로부터 singleton 값을 추출합니다.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>하위 쿼리에 대한 암시적 강제 변환 방지  
 일관된 하위 쿼리 처리의 부작용 중 하나는 하위 쿼리를 스칼라 값으로 암시적으로 변환하는 것입니다. 특히 Transact-SQL에서 단일 필드가 있는 여러 행 집합은 암시적으로 데이터 형식이 필드의 스칼라 값으로 변환됩니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 이러한 암시적 강제 변환이 지원되지 않습니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 컬렉션에서 singleton 값을 추출하도록 ANYELEMENT 연산자를 제공하며, 쿼리 식을 실행하는 중 행 래퍼가 생성되지 않도록 `select value` 절을 제공합니다.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>값 선택: 암시적 행 래퍼 방지  
 Transact-SQL 하위 쿼리의 select 절은 암시적으로 절의 항목 주위에 행 래퍼를 만듭니다. 이는 스칼라 또는 개체의 컬렉션을 만들 수 없음을 의미합니다. Transact-SQL은 하나의 필드가 있는 행 형식과 동일한 데이터 형식의 단일 값 간에 암시적 강제 변환을 허용합니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 암시적 행 생성을 건너뛰도록 `select value` 절을 제공합니다. `select value` 절 하나에는 항목 하나만 지정할 수 있습니다. 이 절을 사용하면 `select` 절의 항목 주위에 행 래퍼가 생성되지 않으며, `select value a`와 같이 원하는 모양의 컬렉션이 만들어질 수 있습니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 임의의 행을 만드는 행 생성자도 제공합니다. `select`는 다음과 같이 프로젝션의 요소를 하나 이상 가지며 필드가 있는 데이터 레코드를 생성합니다.  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>왼쪽 상관 관계 및 별칭 지정  
 Transact-SQL에서 지정된 범위의 `select` 식(같은 단일 절 `from`또는)은 동일한 범위의 앞에서 정의된 식을 참조할 수 없습니다. 일부 SQL 방언(Transact-SQL 포함)은 절에서 제한된 형식의 SQL을 `from` 지원합니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 왼쪽 상관 관계를 `from` 절에 일반화하여 일관성 있게 처리합니다. `from` 절의 식은 추가 구문을 사용할 필요 없이 동일한 절의 이전 정의(왼쪽 정의)를 참조할 수 있습니다.  
  
 또한 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 `group by` 절을 사용하는 쿼리에 추가적인 제한을 적용합니다. 이러한 쿼리에서 `select` 절 및 `having` 절의 식은 오직 별칭을 통해서만 `group by` 키를 참조할 수 있습니다. 다음 구문은 Transact-SQL에서 유효하지만 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]다음 에 있지 않습니다.  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 위와 동일한 결과를 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 얻으려면 다음 구문을 사용합니다.  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>테이블(컬렉션)의 열(속성) 참조  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 모든 열 참조는 테이블 별칭으로 정규화해야 합니다. 다음 구문(테이블의 `a` `T`유효한 열이라고 가정)은 Transact-SQL에서 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]유효하지만 에 속하지 는 않습니다.  
  
```sql  
SELECT a FROM T
```  
  
 위 구문의 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 형식은 다음과 같습니다.  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 `from` 절에서 테이블 별칭은 선택적 요소입니다. 테이블의 이름이 암시적 별칭으로 사용됩니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 다음 형식도 허용됩니다.  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a>개체 탐색  
 Transact-SQL은 테이블의 열(행)을 참조하기 위한 ". 표기법을 사용합니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 프로그래밍 언어에서 차용한 이 표기를 확장하여 개체의 속성 탐색을 지원합니다.  
  
 예를 들어, `p`가 Person 형식의 식이라면 다음은 이 사람의 주소 중 도시를 참조하는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 구문입니다.  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a>*를 지원하지 않음  
 Transact-SQL은 정규화되지 않은 * 구문을 전체 행의 별칭으로 지원하고 \* \*정규화된 구문(t)을 해당 테이블필드의 바로 가기로 지원합니다. 또한 Transact-SQL은 null을 포함하는\*특수 개수() 집계를 허용합니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 * 구문을 지원하지 않습니다. 양식의 `select * from T` SQL 쿼리를 거래하고 `select T1.* from T1, T2...` 각각 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 으로 `select value t from T as t` `select value t1 from T1 as t1, T2 as t2...`표현할 수 있습니다. 또한 이러한 구문은 상속(값 대체성)을 처리하지만, `select *` 변형은 선언된 형식의 최상위 속성으로 제한됩니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 `count(*)` 집계를 지원하지 않습니다. 대신 `count(0)`를 사용하세요.  
  
## <a name="changes-to-group-by"></a>Group By 변경  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 `group by` 키 별칭 지정을 지원합니다. `select` 절 및 `having` 절의 식은 이러한 별칭을 통해 키를 `group by` 참조해야 합니다. 예를 들어, 다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 구문을 봅니다.  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 ... 다음과 같은 거래-SQL과 동일합니다.  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a>컬렉션 기반 집계  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 두 가지 종류의 집계를 지원합니다.  
  
 컬렉션 기반 집계는 컬렉션에 대해 작동하며 집계된 결과를 생성합니다. 이는 쿼리 내의 임의의 위치에 나타날 수 있으며 `group by` 절이 필요 없습니다. 다음은 그 예입니다.  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 SQL 스타일의 집계도 지원됩니다. 다음은 그 예입니다.  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a>ORDER BY 절 사용법  
Transact-SQL은 `ORDER BY` 절을 맨 위 `SELECT .. FROM .. WHERE` 블록에서만 지정할 수 있도록 합니다. 중첩식을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] `ORDER BY` 사용할 수 있으며 쿼리의 아무 곳에나 배치할 수 있지만 중첩된 쿼리의 순서는 유지되지 않습니다.  
  
```sql  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact AS C1
        ORDER BY C1.LastName  
```  
  
```sql  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a>식별자  
 Transact-SQL에서 식별자 비교는 현재 데이터베이스의 데이터 정렬을 기반으로 합니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 식별자는 항상 대/소문자를 구분하지 않고 악센트를 구분합니다. 즉, [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 악센트 부호가 있는 문자와 악센트 부호가 없는 문자를 구분합니다. 예를 들어 'a'는 'ấ'와 같지 않습니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 나타나는 모양은 같지만 서로 다른 코드 페이지에서 가져온 문자 버전을 다른 문자로 처리합니다. 자세한 내용은 [입력 문자 집합을](input-character-set-entity-sql.md)참조하십시오.  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Entity SQL에서 사용할 수 없는 Transact-SQL 기능  
 다음 에서 Transact-SQL 기능을 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]사용할 수 없습니다.  
  
 DML  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 현재 DML 문(insert, update, delete)을 지원하지 않습니다.  
  
 DDL  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 현재 버전에서는 DDL을 지원하지 않습니다.  
  
 명령형 프로그래밍 비교  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 Transact-SQL과 달리 명령적 프로그래밍을 지원하지 않습니다. 대신 프로그래밍 언어를 사용합니다.  
  
 그룹화 함수  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 아직 CUBE, ROLLUP 및 GROUPING_SET와 같은 그룹화 함수가 지원되지 않습니다.  
  
 분석 함수  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 아직 분석 함수가 지원되지 않습니다.  
  
 기본 제공 함수, 연산자  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]는 Transact-SQL의 기본 제공 함수 및 연산자의 하위 집합을 지원합니다. 이러한 연산자와 함수는 주요 저장소 공급자에서 주로 지원합니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 공급자 매니페스트에 선언된 저장소별 함수를 사용합니다. 또한 Entity Framework를 사용하면 사용할 기본 제공 및 사용자 정의 기존 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 저장소 함수를 선언할 수 있습니다.  
  
 힌트  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 쿼리 참고의 메커니즘을 제공하지 않습니다.  
  
 쿼리 결과 일괄 처리  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 쿼리 결과 일괄 처리를 지원하지 않습니다. 예를 들어, 다음은 유효한 Transact-SQL(일괄 처리로 전송)입니다.  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 그러나 해당하는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]은 지원되지 않습니다.  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 결과 생성 쿼리 문을 명령당 하나만 지원합니다.  
  
## <a name="see-also"></a>참고 항목

- [Entity SQL 개요](entity-sql-overview.md)
- [지원되지 않는 식](unsupported-expressions-entity-sql.md)
