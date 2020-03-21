---
title: Entity SQL 빠른 참조
ms.date: 03/30/2017
ms.assetid: e53dad9e-5e83-426e-abb4-be3e78e3d6dc
ms.openlocfilehash: fc7cf8f8f692f9dc4230569d5f575b6d5fad19fa
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150352"
---
# <a name="entity-sql-quick-reference"></a>Entity SQL 빠른 참조
이 항목에서는 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리에 대한 빠른 참조를 제공합니다. 이 항목의 쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.  
  
## <a name="literals"></a>리터럴  
  
### <a name="string"></a>String  
 유니코드 문자열 리터럴과 유니코드가 아닌 문자열 리터럴이 있습니다. 유니코드 문자열은 N으로 준비됩니다. 예를 들어, `N'hello'`.  
  
 다음은 비유니코드 문자열 리터럴의 예제입니다.  
  
```sql  
'hello'  
--same as  
"hello"  
```  
  
 출력:  
  
|값|  
|-----------|  
|hello|  
  
### <a name="datetime"></a>DateTime  
 DateTime 리터럴에서는 날짜와 시간 부분 모두 필수 요소입니다. 기본값은 없습니다.  
  
 예제:  
  
```sql  
DATETIME '2006-12-25 01:01:00.000'
--same as  
DATETIME '2006-12-25 01:01'  
```  
  
 출력:  
  
|값|  
|-----------|  
|12/25/2006 1:01:00 AM|  
  
### <a name="integer"></a>정수  
 Integer 리터럴은 Int32(123), UInt32(123U), Int64(123L) 및 UInt64(123UL) 형식일 수 있습니다.  
  
 예제:  
  
```sql  
--a collection of integers  
{1, 2, 3}  
```  
  
 출력:  
  
|값|  
|-----------|  
|1|  
|2|  
|3|  
  
### <a name="other"></a>기타  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 지원되는 기타 리터럴은 Guid, Binary, Float/Double, Decimal, `null` 등입니다. [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서 Null 리터럴은 개념적 모델의 다른 모든 형식과 호환 가능한 것으로 간주됩니다.  
  
## <a name="type-constructors"></a>형식 생성자  
  
### <a name="row"></a>ROW  
 [ROW는](row-entity-sql.md) 다음과 같이 구조적으로 구조적으로 형식이 되는 익명(레코드) 값을 구성합니다.`ROW(1 AS myNumber, ‘Name’ AS myName).`  
  
 예제:  
  
```sql  
SELECT VALUE row (product.ProductID AS ProductID, product.Name
    AS ProductName) FROM AdventureWorksEntities.Product AS product
```  
  
 출력:  
  
|ProductID|속성|  
|---------------|----------|  
|1|Adjustable Race|  
|879|All-Purpose Bike Stand|  
|712|AWC Logo Cap|  
|...|...|  
  
### <a name="multiset"></a>MULTISET  
 [MULTISET은](multiset-entity-sql.md) 다음과 같은 컬렉션을 생성합니다.  
  
 `MULTISET(1,2,2,3)` `--same as`-`{1,2,2,3}.`  
  
 예제:  
  
```sql  
SELECT VALUE product FROM AdventureWorksEntities.Product AS product WHERE product.ListPrice IN MultiSet (125, 300)  
```  
  
 출력:  
  
|ProductID|속성|ProductNumber|…|  
|---------------|----------|-------------------|-------|  
|842|Touring-Panniers, Large|PA-T100|…|  
  
### <a name="object"></a>Object  
 [명명된 유형 생성자 생성자(예:](named-type-constructor-entity-sql.md) `person("abc", 12)`사용자 정의 개체)  
  
 예제:  
  
```sql  
SELECT VALUE AdventureWorksModel.SalesOrderDetail (o.SalesOrderDetailID, o.CarrierTrackingNumber, o.OrderQty,
o.ProductID, o.SpecialOfferID, o.UnitPrice, o.UnitPriceDiscount,
o.rowguid, o.ModifiedDate) FROM AdventureWorksEntities.SalesOrderDetail
AS o  
```  
  
 출력:  
  
|SalesOrderDetailID|CarrierTrackingNumber|OrderQty|ProductID|...|  
|------------------------|---------------------------|--------------|---------------|---------|  
|1|4911-403C-98|1|776|...|  
|2|4911-403C-98|3|777|...|  
|...|...|...|...|...|  
  
## <a name="references"></a>참조  
  
### <a name="ref"></a>REF  
 [REF는](ref-entity-sql.md) 엔터티 유형 인스턴스에 대한 참조를 만듭니다. 예를 들어, 다음 쿼리는 주문 엔터티 집합의 개별 주문 엔터티에 대한 참조를 반환합니다.  
  
```sql  
SELECT REF(o) AS OrderID FROM Orders AS o  
```  
  
 출력:  
  
|값|  
|-----------|  
|1|  
|2|  
|3|  
|...|  
  
 다음 예제에서는 속성 추출 연산자(.)를 사용하여 엔터티의 속성에 액세스합니다. 속성 추출 연산자가 사용되면 해당 참조가 자동으로 역참조됩니다.  
  
 예제:  
  
```sql  
SELECT VALUE REF(p).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 출력:  
  
|값|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="deref"></a>DEREF  
 [DEREF는](deref-entity-sql.md) 참조 값을 참조하고 해당 참조의 결과를 생성합니다. 예를 들어, `SELECT DEREF(o2.r) FROM (SELECT REF(o) AS r FROM LOB.Orders AS o) AS o2` 쿼리는 Orders 엔터티 집합의 개별 Order별로 Order 엔터티를 생성합니다.  
  
 예제:  
  
```sql  
SELECT VALUE DEREF(REF(p)).Name FROM
    AdventureWorksEntities.Product AS p
```  
  
 출력:  
  
|값|  
|-----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="createref-and-key"></a>CREATEREF 및 KEY  
 [CREATEREF는](createref-entity-sql.md) 키를 전달하는 참조를 만듭니다. [KEY는](key-entity-sql.md) 형식 참조를 통해 식의 키 부분을 추출합니다.  
  
 예제:  
  
```sql  
SELECT VALUE Key(CreateRef(AdventureWorksEntities.Product, row(p.ProductID)))
    FROM AdventureWorksEntities.Product AS p
```  
  
 출력:  
  
|ProductID|  
|---------------|  
|980|  
|365|  
|771|  
|...|  
  
## <a name="functions"></a>Functions  
  
### <a name="canonical"></a>Canonical  
 [표준 함수의](canonical-functions.md) 네임스페이스는 `Edm.Length("string")`에서와 같이 Edm입니다. 정식 함수와 이름이 같은 함수가 포함된 다른 네임스페이스를 가져오지 않는 한, 네임스페이스를 지정할 필요가 없습니다. 두 네임스페이스의 함수가 동일한 경우 사용자는 전체 이름을 지정해야 합니다.  
  
 예제:  
  
```sql  
SELECT Length(c. FirstName) AS NameLen FROM
    AdventureWorksEntities.Contact AS c
    WHERE c.ContactID BETWEEN 10 AND 12  
```  
  
 출력:  
  
|NameLen|  
|-------------|  
|6|  
|6|  
|5|  
  
### <a name="microsoft-provider-specific"></a>Microsoft 공급자 특정  
 [Microsoft 공급자별 함수는](../sqlclient-for-ef-functions.md) 네임스페이스에 `SqlServer` 있습니다.  
  
 예제:  
  
```sql  
SELECT SqlServer.LEN(c.EmailAddress) AS EmailLen FROM
    AdventureWorksEntities.Contact AS c WHERE
    c.ContactID BETWEEN 10 AND 12  
```  
  
 출력:  
  
|EmailLen|  
|--------------|  
|27|  
|27|  
|26|  
  
## <a name="namespaces"></a>네임스페이스  
 [using는](using-entity-sql.md) 쿼리 식에 사용되는 네임스페이스를 지정합니다.  
  
 예제:  
  
```sql  
using SqlServer; LOWER('AA');  
```  
  
 출력:  
  
|값|  
|-----------|  
|aa|  
  
## <a name="paging"></a>Paging  
 페이징은 [ORDER BY](order-by-entity-sql.md) 절에 [SKIP](skip-entity-sql.md) 및 [LIMIT](limit-entity-sql.md) 하위 절을 선언하여 표현할 수 있습니다.  
  
 예제:  
  
```sql  
SELECT c.ContactID as ID, c.LastName AS Name FROM
    AdventureWorks.Contact AS c ORDER BY c.ContactID SKIP 9 LIMIT 3;  
```  
  
 출력:  
  
|ID|속성|  
|--------|----------|  
|10|Adina|  
|11|Agcaoili|  
|12|Aguilar|  
  
## <a name="grouping"></a>Grouping(그룹화)  
 [GROUPING BY는](group-by-entity-sql.md) [쿼리(SELECT)](select-entity-sql.md)식에 의해 반환되는 개체를 배치할 그룹을 지정합니다.  
  
 예제:  
  
```sql  
SELECT VALUE name FROM AdventureWorksEntities.Product AS P
    GROUP BY P.Name HAVING MAX(P.ListPrice) > 5  
```  
  
 출력:  
  
|name|  
|----------|  
|LL Mountain Seat Assembly|  
|ML Mountain Seat Assembly|  
|HL Mountain Seat Assembly|  
|...|  
  
## <a name="navigation"></a>탐색  
 관계 탐색 연산자를 사용하여 엔터티 간의(시작 End에서 끝 End) 관계를 탐색할 수 있습니다. [NAVIGATE는](navigate-entity-sql.md) 네임스페이스 \<> 정규화된 관계 유형을 취합니다. \<관계 유형 이름>. 행간 끝의 카디널리티가 1이면 탐색은 참조\<T> 반환합니다. 끝까지의 카디널리티가 n이면 참조\<T>><컬렉션이 반환됩니다.  
  
 예제:  
  
```sql  
SELECT a.AddressID, (SELECT VALUE DEREF(v) FROM
    NAVIGATE(a, AdventureWorksModel.FK_SalesOrderHeader_Address_BillToAddressID) AS v)
    FROM AdventureWorksEntities.Address AS a  
```  
  
 출력:  
  
|AddressID|  
|---------------|  
|1|  
|2|  
|3|  
|...|  
  
## <a name="select-value-and-select"></a>SELECT VALUE 및 SELECT  
  
### <a name="select-value"></a>SELECT VALUE  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 암시적 행 생성을 건너뛰도록 SELECT VALUE 절을 제공합니다. SELECT VALUE 절 하나에는 항목 하나만 지정할 수 있습니다. 이러한 절을 사용하면 SELECT 절의 항목 주위에 행 래퍼가 생성되지 않으며 원하는 셰이프 컬렉션(예: `SELECT VALUE a`)을 생성할 수 있습니다.  
  
 예제:  
  
```sql  
SELECT VALUE p.Name FROM AdventureWorksEntities.Product AS p
```  
  
 출력:  
  
|속성|  
|----------|  
|Adjustable Race|  
|All-Purpose Bike Stand|  
|AWC Logo Cap|  
|...|  
  
### <a name="select"></a>SELECT  
 [!INCLUDE[esql](../../../../../../includes/esql-md.md)]에서는 임의의 행을 만드는 행 생성자도 제공합니다. SELECT는 `SELECT a, b, c`와 같이 프로젝션의 요소를 하나 이상 사용하며 필드가 있는 데이터 레코드를 생성합니다.  
  
 예제:  
  
 SELECT p.Name, p.ProductID FROM AdventureWorksEntities.Product as p 출력:  
  
|속성|ProductID|  
|----------|---------------|  
|Adjustable Race|1|  
|All-Purpose Bike Stand|879|  
|AWC Logo Cap|712|  
|...|...|  
  
## <a name="case-expression"></a>CASE 식  
 [CASE 식은](case-entity-sql.md) 부울 식 집합을 평가하여 결과를 결정합니다.  
  
 예제:  
  
```sql  
CASE WHEN AVG({25,12,11}) < 100 THEN TRUE ELSE FALSE END  
```  
  
 출력:  
  
|값|  
|-----------|  
|TRUE|  
  
## <a name="see-also"></a>참고 항목

- [엔터티 SQL 참조](entity-sql-reference.md)
- [Entity SQL 개요](entity-sql-overview.md)
