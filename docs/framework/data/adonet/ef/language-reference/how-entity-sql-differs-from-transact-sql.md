---
title: Entity SQL과 Transact-SQL의 차이점
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 75ce0b00962526b76ea9f4b9fdfb0d1e1e564cdc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59162739"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a>Entity SQL과 Transact-SQL의 차이점
이 항목에서는 차이점을 설명 합니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 고 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]입니다.  
  
## <a name="inheritance-and-relationships-support"></a>상속 및 관계 지원  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 개념적 엔터티 스키마와 직접 작동 하 고 상속 및 관계와 같은 개념적 모델 기능을 지원 합니다.  
  
 상속 작업을 할 때 상위 형식 인스턴스 컬렉션에서 하위 형식의 인스턴스를 선택하는 것이 유용할 때가 많습니다. 합니다 [oftype](../../../../../../docs/framework/data/adonet/ef/language-reference/oftype-entity-sql.md) 연산자 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] (비슷합니다 `oftype` 에서 C# 시퀀스)이이 기능을 제공 합니다.  
  
## <a name="support-for-collections"></a>컬렉션 지원  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 컬렉션을 고급 엔터티로 처리합니다. 예를 들어:  
  
-   컬렉션 식은 `from` 절에서 유효합니다.  
  
-   `in` 및 `exists` 하위 모든 컬렉션을 허용 하도록 일반화 되었습니다.  
  
     하위 쿼리는 일종의 컬렉션입니다. `e1 in e2` 및 `exists(e)` 되는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 이러한 작업을 수행 하는 구문입니다.  
  
-   컬렉션에 대해 `union`, `intersect`, `except` 등의 Set 작업이 수행됩니다.  
  
-   컬렉션에 조인이 수행됩니다.  
  
## <a name="support-for-expressions"></a>식 지원  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 하위 쿼리 (테이블) 및 식 (행 및 열)에 있습니다.  
  
 컬렉션 및 중첩된 컬렉션을 지원 하기 위해 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 모든 식을 만듭니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 보다 더 구성 가능은 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]-어디서 나 모든 식을 사용할 수 있습니다. 쿼리 식은 항상 프로젝션된 형식의 컬렉션을 생성하며, 컬렉션 식이 허용된 곳이라면 어디서든 쿼리 식을 사용할 수 있습니다. 에 대 한 자세한 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 식에서 지원 되지 않는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]를 참조 하십시오 [지원 되지 않는 식](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)합니다.  
  
 다음은 모두 유효한 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리입니다.  
  
```  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}   
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a>일관된 하위 쿼리 처리  
 테이블을 강조하는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서는 하위 쿼리를 문맥상으로 해석합니다. 예를 들어, `from` 절의 하위 쿼리는 multiset(테이블)로 간주됩니다. 하지만 동일한 하위 쿼리가 `select` 절에서 사용되면 스칼라 하위 쿼리로 간주됩니다. 왼쪽에서 사용 되는 하위 쿼리 마찬가지로 `in` 연산자는 스칼라 하위 쿼리를 multiset 하위 쿼리로 오른쪽에 있는 것으로 예상 되지만 되도록 것으로 간주 됩니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 이러한 차이점을 제거합니다. 식은 사용되는 컨텍스트와 관계없이 일관성 있게 해석되며 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 모든 하위 쿼리를 multiset 하위 쿼리로 간주 합니다. 하위 쿼리에서 스칼라 값이 필요한 경우, [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 컬렉션(여기서는 하위 쿼리)에 대해 작동하는 `anyelement` 연산자를 제공하여 컬렉션으로부터 singleton 값을 추출합니다.  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a>하위 쿼리에 대한 암시적 강제 변환 방지  
 일관된 하위 쿼리 처리의 부작용 중 하나는 하위 쿼리를 스칼라 값으로 암시적으로 변환하는 것입니다. 즉 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서는 단일 필드를 가진 행의 multiset가 해당 필드의 데이터 형식을 갖는 스칼라 값으로 암시적으로 변환됩니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 이 암시적 강제 변환을 지원 하지 않습니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 컬렉션에서 singleton 값을 추출 하도록 ANYELEMENT 연산자를 제공 및 `select value` 절 쿼리 식 중 행 래퍼가 생성을 방지 합니다.  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a>Select Value: 암시적 행 래퍼 방지  
 Select 절에는 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 하위 쿼리 절의 항목 주위에 행 래퍼를 암시적으로 만듭니다. 이는 스칼라 또는 개체의 컬렉션을 만들 수 없음을 의미합니다. [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 단일 필드를 갖는 rowtype과 동일한 데이터 형식의 singleton 값 사이 암시적 강제 변환을 허용합니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 제공 된 `select value` 암시적 행 생성을 건너뛰도록 절. `select value` 절 하나에는 항목 하나만 지정할 수 있습니다. 이 절을 사용하면 `select` 절의 항목 주위에 행 래퍼가 생성되지 않으며, `select value a`와 같이 원하는 모양의 컬렉션이 만들어질 수 있습니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 또한 임의의 행을 만드는 행 생성자를 제공 합니다. `select` 다음과 같이 프로젝션의 요소를 하나 이상의 및 필드를 사용 하 여 데이터 레코드의 결과 사용합니다.  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a>왼쪽 상관 관계 및 별칭 지정  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서 특정 범위(`select` 또는 `from`과 같은 단일 절)의 식은 동일 범위에서 이전에 정의된 식을 참조할 수 없습니다. [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]을 비롯하여 일부 SQL 언어에서는 `from` 절에서 이를 제한된 형태로 지원합니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 왼쪽된 상관 관계를 일반화 하는 `from` 절을 균일 하 게 처리 합니다. `from` 절의 식은 추가 구문을 사용할 필요 없이 동일한 절의 이전 정의(왼쪽 정의)를 참조할 수 있습니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 추가적인 제한도 `group by` 절. 이러한 쿼리에서 `select` 절 및 `having` 절의 식은 오직 별칭을 통해서만 `group by` 키를 참조할 수 있습니다. 다음 구문은 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서 유효하지만 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 유효하지 않습니다.  
  
```  
select t.x + t.y from T as t group by t.x + t.y  
```  
  
 위와 동일한 결과를 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 얻으려면 다음 구문을 사용합니다.  
  
```  
select k from T as t group by (t.x + t.y) as k  
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a>테이블(컬렉션)의 열(속성) 참조  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]의 모든 열 참조는 테이블 별칭으로 정규화해야 합니다. 다음 구문은 (가정 `a` 은 테이블의 유효한 열 `T`)에서 유효 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 되지 않습니다 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]합니다.  
  
```  
select a from T  
```  
  
 위 구문의 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 형식은 다음과 같습니다.  
  
```  
select t.a as A from T as t  
```  
  
 `from` 절에서 테이블 별칭은 선택적 요소입니다. 테이블의 이름이 암시적 별칭으로 사용됩니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 뿐만 아니라 다음 양식의 허용합니다.  
  
```  
select Tab.a from Tab  
```  
  
## <a name="navigation-through-objects"></a>개체 탐색  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 사용 하는 "." 표기법 (행)의 열 참조 테이블입니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 개체의 속성 탐색을 지원 하기 위해 (프로그래밍 언어에서 차용한)이이 표기를 확장 합니다.  
  
 예를 들어, `p`가 Person 형식의 식이라면 다음은 이 사람의 주소 중 도시를 참조하는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 구문입니다.  
  
```  
p.Address.City   
```  
  
## <a name="no-support-for-"></a>*를 지원하지 않음  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 정규화 되지 않은 지원 * 전체 행을 지정 하 고 정규화 된 별칭으로 구문을 \* 구문 (t.\*) 해당 테이블의 필드에 대 한 바로 가기로 합니다. 또한 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 특별 한 개수에 대 한 허용 (\*) null을 포함 하는 집계 합니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 지원 하지 않습니다는 * 구문. [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 폼의 쿼리 `select * from T` 하 고 `select T1.* from T1, T2...` 표현할 수 있습니다 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 으로 `select value t from T as t` 및 `select value t1 from T1 as t1, T2 as t2...`, 각각. 또한 이러한 구문은 상속(값 대체성)을 처리하지만, `select *` 변형은 선언된 형식의 최상위 속성으로 제한됩니다.  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 지원 하지 않습니다는 `count(*)` 집계 합니다. 대신 `count(0)`를 사용하세요.  
  
## <a name="changes-to-group-by"></a>Group By 변경  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 별칭 지정을 지원 `group by` 키입니다. 식에는 `select` 절 및 `having` 절을 참조 해야 합니다는 `group by` 이러한 별칭을 통해 키입니다. 예를 들어, 다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 구문을 봅니다.  
  
```  
select k1, count(t.a), sum(t.a)  
from T as t  
group by t.b + t.c as k1  
```  
  
 위 구문은 다음 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 구문과 동일합니다.  
  
```  
select b + c, count(*), sum(a)   
from T  
group by b + c  
```  
  
## <a name="collection-based-aggregates"></a>컬렉션 기반 집계  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 두 종류의 집계를 지원합니다.  
  
 컬렉션 기반 집계는 컬렉션에 대해 작동하며 집계된 결과를 생성합니다. 이는 쿼리 내의 임의의 위치에 나타날 수 있으며 `group by` 절이 필요 없습니다. 예를 들어:  
  
```  
select t.a as a, count({1,2,3}) as b from T as t     
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 또한 SQL 스타일의 집계를 지원합니다. 예를 들어:  
  
```  
select a, sum(t.b) from T as t group by t.a as a  
```  
  
## <a name="order-by-clause-usage"></a>ORDER BY 절 사용법  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] ORDER BY 절을 맨 위의 SELECT에만 지정할 수 있습니다... FROM . WHERE 블록에서만 지정할 수 있습니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 중첩된 ORDER BY 식을 사용할 수 있으며, 이는 쿼리 내 임의의 위치에 올 수 있습니다. 그러나 중첩 쿼리 내의 순서는 유지되지 않습니다.  
  
```  
-- The following query will order the results by the last name  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  
  
```  
-- In the following query ordering of the nested query is ignored.  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="identifiers"></a>식별자  
 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]에서 식별자 비교는 현재 데이터베이스의 데이터 정렬을 기반으로 합니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 식별자는 항상 대/소문자를 구분하지 않고 악센트를 구분합니다. 즉, [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 악센트 부호가 있는 문자와 악센트 부호가 없는 문자를 구분합니다. 예를 들어 'a'는 'ấ'와 같지 않습니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 동일 하 게 표시 되지만 다른 문자로 서로 다른 코드 페이지 문자 버전을 처리 합니다. 자세한 내용은 [입력 문자 집합](../../../../../../docs/framework/data/adonet/ef/language-reference/input-character-set-entity-sql.md)합니다.  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a>Entity SQL에서 사용할 수 없는 Transact-SQL 기능  
 다음 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] 기능은 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 사용할 수 없습니다.  
  
 DML  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 에서는 현재 DML 문 지원 되지 않습니다 (삽입, 업데이트, 삭제).  
  
 DDL  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 현재 버전에서 DDL 지원은 없습니다를 제공합니다.  
  
 명령형 프로그래밍 비교  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 와 달리 명령형 프로그래밍을 지원 하지 않습니다 제공 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]합니다. 대신 프로그래밍 언어를 사용합니다.  
  
 그룹화 함수  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 그룹화 (예를 들어 CUBE, ROLLUP 및 GROUPING_SET) 함수에 대 한 지원을 아직 제공 하지 않습니다.  
  
 분석 함수  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 않습니다 (아직) 분석 함수에 대 한 지원을 제공 합니다.  
  
 기본 제공 함수, 연산자  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 하위 집합을 지원 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)]함수 및 연산자의 기본 제공 합니다. 이러한 연산자와 함수는 주요 저장소 공급자에서 주로 지원합니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 공급자 매니페스트에 선언 된 저장소별 함수를 사용 합니다. 또한 합니다 [!INCLUDE[adonet_ef](../../../../../../includes/adonet-ef-md.md)] 기본 제공 선언할 수 있으며 기존 사용자 정의 함수에 대 한 저장소 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 사용 하도록 합니다.  
  
 참고  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리 힌트에 대 한 메커니즘을 제공 하지 않습니다.  
  
 쿼리 결과 일괄 처리  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리 결과 일괄 처리를 지원 하지 않습니다. 예를 들어, 다음은 유효한 [!INCLUDE[tsql](../../../../../../includes/tsql-md.md)] (일괄 처리로 보내는):  
  
```  
select * from products;  
select * from catagories;  
```  
  
 그러나 해당하는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]은 지원되지 않습니다.  
  
```  
Select value p from Products as p;  
Select value c from Categories as c;  
```  
  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 한 결과 생성 쿼리 문을 명령 당만 지원합니다.  
  
## <a name="see-also"></a>참고자료

- [Entity SQL 개요](../../../../../../docs/framework/data/adonet/ef/language-reference/entity-sql-overview.md)
- [지원되지 않는 식](../../../../../../docs/framework/data/adonet/ef/language-reference/unsupported-expressions-entity-sql.md)
