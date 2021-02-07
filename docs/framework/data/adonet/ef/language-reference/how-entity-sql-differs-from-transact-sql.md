---
description: '자세한 정보: Transact-sql과 Entity SQL 다른 방법'
title: Entity SQL과 Transact-SQL의 차이점
ms.date: 03/30/2017
ms.assetid: 9c9ee36d-f294-4c8b-a196-f0114c94f559
ms.openlocfilehash: 349dd64cc0e548ab0dc8d0e66e8bb14b58912d09
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696869"
---
# <a name="how-entity-sql-differs-from-transact-sql"></a><span data-ttu-id="d2a39-103">Transact-sql과 Entity SQL 다른 방법</span><span class="sxs-lookup"><span data-stu-id="d2a39-103">How Entity SQL differs from Transact-SQL</span></span>

<span data-ttu-id="d2a39-104">이 문서에서는 Entity SQL와 Transact-sql 간의 차이점을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-104">This article describes the differences between Entity SQL and Transact-SQL.</span></span>  
  
## <a name="inheritance-and-relationships-support"></a><span data-ttu-id="d2a39-105">상속 및 관계 지원</span><span class="sxs-lookup"><span data-stu-id="d2a39-105">Inheritance and Relationships Support</span></span>  

 <span data-ttu-id="d2a39-106">Entity SQL은 개념적 엔터티 스키마를 직접 사용 하며 상속 및 관계와 같은 개념적 모델 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-106">Entity SQL works directly with conceptual entity schemas and supports conceptual model features such as inheritance and relationships.</span></span>  
  
 <span data-ttu-id="d2a39-107">상속 작업을 할 때 상위 형식 인스턴스 컬렉션에서 하위 형식의 인스턴스를 선택하는 것이 유용할 때가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-107">When working with inheritance, it is often useful to select instances of a subtype from a collection of supertype instances.</span></span> <span data-ttu-id="d2a39-108">Entity SQL의 [oftype](oftype-entity-sql.md) 연산자 ( `oftype` c # 시퀀스의와 유사)는이 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-108">The [oftype](oftype-entity-sql.md) operator in Entity SQL (similar to `oftype` in C# Sequences) provides this capability.</span></span>  
  
## <a name="support-for-collections"></a><span data-ttu-id="d2a39-109">컬렉션 지원</span><span class="sxs-lookup"><span data-stu-id="d2a39-109">Support for Collections</span></span>  

 <span data-ttu-id="d2a39-110">Entity SQL는 컬렉션을 첫 번째 클래스 엔터티로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-110">Entity SQL treats collections as first-class entities.</span></span> <span data-ttu-id="d2a39-111">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="d2a39-111">For example:</span></span>  
  
- <span data-ttu-id="d2a39-112">컬렉션 식은 `from` 절에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-112">Collection expressions are valid in a `from` clause.</span></span>  
  
- <span data-ttu-id="d2a39-113">하위 쿼리 `in` 및 `exists`는 모든 컬렉션을 허용하도록 일반화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-113">`in` and `exists` subqueries have been generalized to allow any collections.</span></span>  
  
     <span data-ttu-id="d2a39-114">하위 쿼리는 일종의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-114">A subquery is one kind of collection.</span></span> <span data-ttu-id="d2a39-115">`e1 in e2` 및 `exists(e)` 는 이러한 작업을 수행 하는 Entity SQL 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-115">`e1 in e2` and `exists(e)` are the Entity SQL constructs to perform these operations.</span></span>  
  
- <span data-ttu-id="d2a39-116">컬렉션에 대해 `union`, `intersect`, `except` 등의 Set 작업이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-116">Set operations, such as `union`, `intersect`, and `except`, now operate on collections.</span></span>  
  
- <span data-ttu-id="d2a39-117">컬렉션에 조인이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-117">Joins operate on collections.</span></span>  
  
## <a name="support-for-expressions"></a><span data-ttu-id="d2a39-118">식 지원</span><span class="sxs-lookup"><span data-stu-id="d2a39-118">Support for Expressions</span></span>  

 <span data-ttu-id="d2a39-119">Transact-sql에는 하위 쿼리 (테이블)와 식 (행 및 열)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-119">Transact-SQL has subqueries (tables) and expressions (rows and columns).</span></span>  
  
 <span data-ttu-id="d2a39-120">컬렉션 및 중첩 컬렉션을 지원 하기 위해 Entity SQL 모든 것을 식으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-120">To support collections and nested collections, Entity SQL makes everything an expression.</span></span> <span data-ttu-id="d2a39-121">Entity SQL는 Transact-sql 보다 더 쉽게 구성할 수 있습니다. 모든 식은 어디에서 나 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-121">Entity SQL is more composable than Transact-SQL—every expression can be used anywhere.</span></span> <span data-ttu-id="d2a39-122">쿼리 식은 항상 프로젝션된 형식의 컬렉션을 생성하며, 컬렉션 식이 허용된 곳이라면 어디서든 쿼리 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-122">Query expressions always result in collections of the projected types and can be used anywhere a collection expression is allowed.</span></span> <span data-ttu-id="d2a39-123">Entity SQL에서 지원 되지 않는 Transact-sql 식에 대 한 자세한 내용은 [지원 되지 않는 식](unsupported-expressions-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a39-123">For information about Transact-SQL expressions that are not supported in Entity SQL, see [Unsupported Expressions](unsupported-expressions-entity-sql.md).</span></span>  
  
 <span data-ttu-id="d2a39-124">다음은 모든 유효한 Entity SQL 쿼리입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-124">The following are all valid Entity SQL queries:</span></span>  
  
```sql  
1+2 *3  
"abc"  
row(1 as a, 2 as b)  
{ 1, 3, 5}
e1 union all e2  
set(e1)  
```  
  
## <a name="uniform-treatment-of-subqueries"></a><span data-ttu-id="d2a39-125">일관된 하위 쿼리 처리</span><span class="sxs-lookup"><span data-stu-id="d2a39-125">Uniform Treatment of Subqueries</span></span>  

 <span data-ttu-id="d2a39-126">테이블에 중점을 두어 Transact-sql은 하위 쿼리의 컨텍스트 해석을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-126">Given its emphasis on tables, Transact-SQL performs contextual interpretation of subqueries.</span></span> <span data-ttu-id="d2a39-127">예를 들어, `from` 절의 하위 쿼리는 multiset(테이블)로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-127">For example, a subquery in the `from` clause is considered to be a multiset (table).</span></span> <span data-ttu-id="d2a39-128">하지만 동일한 하위 쿼리가 `select` 절에서 사용되면 스칼라 하위 쿼리로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-128">But the same subquery used in the `select` clause is considered to be a scalar subquery.</span></span> <span data-ttu-id="d2a39-129">마찬가지로 연산자의 좌 변에 사용 되는 하위 쿼리는 `in` 스칼라 하위 쿼리로 간주 되 고 오른쪽은 multiset 하위 쿼리로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-129">Similarly, a subquery used on the left side of an `in` operator is considered to be a scalar subquery, while the right side is expected to be a multiset subquery.</span></span>  
  
 <span data-ttu-id="d2a39-130">Entity SQL 이러한 차이를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-130">Entity SQL eliminates these differences.</span></span> <span data-ttu-id="d2a39-131">식은 사용되는 컨텍스트와 관계없이 일관성 있게 해석되며</span><span class="sxs-lookup"><span data-stu-id="d2a39-131">An expression has a uniform interpretation that does not depend on the context in which it is used.</span></span> <span data-ttu-id="d2a39-132">Entity SQL은 모든 하위 쿼리를 multiset 하위 쿼리로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-132">Entity SQL considers all subqueries to be multiset subqueries.</span></span> <span data-ttu-id="d2a39-133">하위 쿼리에서 스칼라 값이 필요한 경우 Entity SQL는 `anyelement` 컬렉션에서 작동 하는 연산자 (이 경우 하위 쿼리)를 제공 하 고 컬렉션에서 singleton 값을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-133">If a scalar value is desired from the subquery, Entity SQL provides the `anyelement` operator that operates on a collection (in this case, the subquery), and extracts a singleton value from the collection.</span></span>  
  
### <a name="avoiding-implicit-coercions-for-subqueries"></a><span data-ttu-id="d2a39-134">하위 쿼리에 대한 암시적 강제 변환 방지</span><span class="sxs-lookup"><span data-stu-id="d2a39-134">Avoiding Implicit Coercions for Subqueries</span></span>  

 <span data-ttu-id="d2a39-135">일관된 하위 쿼리 처리의 부작용 중 하나는 하위 쿼리를 스칼라 값으로 암시적으로 변환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-135">A related side effect of uniform treatment of subqueries is implicit conversion of subqueries to scalar values.</span></span> <span data-ttu-id="d2a39-136">특히 Transact-sql에서 단일 필드를 사용 하 여 행의 multiset은 해당 데이터 형식이 필드의 스칼라 값으로 암시적으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-136">Specifically, in Transact-SQL, a multiset of rows (with a single field) is implicitly converted into a scalar value whose data type is that of the field.</span></span>  
  
 <span data-ttu-id="d2a39-137">Entity SQL는이 암시적 강제 변환을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-137">Entity SQL does not support this implicit coercion.</span></span> <span data-ttu-id="d2a39-138">Entity SQL는 연산자를 제공 하 여 `ANYELEMENT` 컬렉션에서 singleton 값을 추출 하 고 `select value` 절을 사용 하 여 쿼리 식 중에 행 래퍼가 생성 되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-138">Entity SQL provides the `ANYELEMENT` operator to extract a singleton value from a collection, and a `select value` clause to avoid creating a row-wrapper during a query expression.</span></span>  
  
## <a name="select-value-avoiding-the-implicit-row-wrapper"></a><span data-ttu-id="d2a39-139">값 선택: 암시적 행 래퍼 방지</span><span class="sxs-lookup"><span data-stu-id="d2a39-139">Select Value: Avoiding the Implicit Row Wrapper</span></span>  

 <span data-ttu-id="d2a39-140">Transact-sql 하위 쿼리의 select 절은 절의 항목 주위에 행 래퍼를 암시적으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-140">The select clause in a Transact-SQL subquery implicitly creates a row wrapper around the items in the clause.</span></span> <span data-ttu-id="d2a39-141">이는 스칼라 또는 개체의 컬렉션을 만들 수 없음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-141">This implies that we cannot create collections of scalars or objects.</span></span> <span data-ttu-id="d2a39-142">Transact-sql을 사용 하면 `rowtype` 한 필드와 데이터 형식이 동일한 singleton 값을 사용 하는 간에 암시적 강제 변환을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-142">Transact-SQL allows an implicit coercion between a `rowtype` with one field and a singleton value of the same data type.</span></span>  
  
 <span data-ttu-id="d2a39-143">Entity SQL는 `select value` 암시적 행 생성을 건너뛰는 절을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-143">Entity SQL provides the `select value` clause to skip the implicit row construction.</span></span> <span data-ttu-id="d2a39-144">`select value` 절 하나에는 항목 하나만 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-144">Only one item may be specified in a `select value` clause.</span></span> <span data-ttu-id="d2a39-145">이러한 절을 사용 하면 절의 항목 주위에 행 래퍼가 생성 되지 않으며,와 같이 `select` 원하는 모양의 컬렉션이 생성 될 수 있습니다 `select value a` .</span><span class="sxs-lookup"><span data-stu-id="d2a39-145">When such a clause is used, no row wrapper is constructed around the items in the `select` clause, and a collection of the desired shape may be produced, for example, `select value a`.</span></span>  
  
 <span data-ttu-id="d2a39-146">또한 Entity SQL는 임의의 행을 생성 하는 행 생성자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-146">Entity SQL also provides the row constructor to construct arbitrary rows.</span></span> <span data-ttu-id="d2a39-147">`select` 프로젝션에서 하나 이상의 요소를 사용 하 고 필드가 있는 데이터 레코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-147">`select` takes one or more elements in the projection and results in a data record with fields:</span></span>  
  
 `select a, b, c`  
  
## <a name="left-correlation-and-aliasing"></a><span data-ttu-id="d2a39-148">왼쪽 상관 관계 및 별칭 지정</span><span class="sxs-lookup"><span data-stu-id="d2a39-148">Left Correlation and Aliasing</span></span>  

 <span data-ttu-id="d2a39-149">Transact-sql에서 지정 된 범위의 식 (또는와 같은 단일 절 `select` `from` )은 같은 범위에서 이전에 정의 된 식을 참조할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-149">In Transact-SQL, expressions in a given scope (a single clause like `select` or `from`) cannot reference expressions defined earlier in the same scope.</span></span> <span data-ttu-id="d2a39-150">SQL (Transact-sql 포함)의 일부 언어는 절에서 제한 된 형식을 지원 `from` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-150">Some dialects of SQL (including Transact-SQL) do support limited forms of these in the `from` clause.</span></span>  
  
 <span data-ttu-id="d2a39-151">일반화는 절에서 왼쪽 상관 관계를 Entity SQL 하 `from` 고 균일 하 게 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-151">Entity SQL generalizes left correlations in the `from` clause, and treats them uniformly.</span></span> <span data-ttu-id="d2a39-152">`from` 절의 식은 추가 구문을 사용할 필요 없이 동일한 절의 이전 정의(왼쪽 정의)를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-152">Expressions in the `from` clause can reference earlier definitions (definitions to the left) in the same clause without the need for additional syntax.</span></span>  
  
 <span data-ttu-id="d2a39-153">또한 Entity SQL 절을 포함 하는 쿼리에 추가 제한을 적용 `group by` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-153">Entity SQL also imposes additional restrictions on queries involving `group by` clauses.</span></span> <span data-ttu-id="d2a39-154">이러한 쿼리에서 `select` 절 및 `having` 절의 식은 오직 별칭을 통해서만 `group by` 키를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-154">Expressions in the `select` clause and `having` clause of such queries may only refer to the `group by` keys via their aliases.</span></span> <span data-ttu-id="d2a39-155">다음 구문은 Transact-sql에서는 유효 하지만 Entity SQL에는 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-155">The following construct is valid in Transact-SQL but are not in Entity SQL:</span></span>  
  
```sql  
SELECT t.x + t.y FROM T AS t group BY t.x + t.y
```  
  
 <span data-ttu-id="d2a39-156">Entity SQL에서이 작업을 수행 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-156">To do this in Entity SQL:</span></span>  
  
```sql  
SELET k FROM T AS t GROUP BY (t.x + t.y) AS k
```  
  
## <a name="referencing-columns-properties-of-tables-collections"></a><span data-ttu-id="d2a39-157">테이블(컬렉션)의 열(속성) 참조</span><span class="sxs-lookup"><span data-stu-id="d2a39-157">Referencing Columns (Properties) of Tables (Collections)</span></span>  

 <span data-ttu-id="d2a39-158">Entity SQL의 모든 열 참조는 테이블 별칭으로 정규화 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-158">All column references in Entity SQL must be qualified with the table alias.</span></span> <span data-ttu-id="d2a39-159">다음 구문 ( `a` 가 테이블의 유효한 열 이라고 가정)은 `T` transact-sql에서는 유효 하지만 Entity SQL에서는 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-159">The following construct (assuming that `a` is a valid column of table `T`) is valid in Transact-SQL but not in Entity SQL.</span></span>  
  
```sql  
SELECT a FROM T
```  
  
 <span data-ttu-id="d2a39-160">Entity SQL 폼은</span><span class="sxs-lookup"><span data-stu-id="d2a39-160">The Entity SQL form is</span></span>  
  
```sql  
SELECT t.a AS A FROM T AS t
```  
  
 <span data-ttu-id="d2a39-161">`from` 절에서 테이블 별칭은 선택적 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-161">The table aliases are optional in the `from` clause.</span></span> <span data-ttu-id="d2a39-162">테이블의 이름이 암시적 별칭으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-162">The name of the table is used as the implicit alias.</span></span> <span data-ttu-id="d2a39-163">Entity SQL 다음과 같은 양식도 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-163">Entity SQL allows the following form as well:</span></span>  
  
```sql  
SELET Tab.a FROM Tab
```  
  
## <a name="navigation-through-objects"></a><span data-ttu-id="d2a39-164">개체 탐색</span><span class="sxs-lookup"><span data-stu-id="d2a39-164">Navigation Through Objects</span></span>  

 <span data-ttu-id="d2a39-165">Transact-sql은 테이블의 (행)의 열을 참조 하는 데 "." 표기법을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-165">Transact-SQL uses the "." notation for referencing columns of (a row of) a table.</span></span> <span data-ttu-id="d2a39-166">Entity SQL는이 표기법 (프로그래밍 언어에서 가져온)을 확장 하 여 개체의 속성을 탐색할 수 있도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-166">Entity SQL extends this notation (borrowed from programming languages) to support navigation through properties of an object.</span></span>  
  
 <span data-ttu-id="d2a39-167">예를 들어 `p` 가 person 형식의 식인 경우 다음은이 사람의 주소 도시를 참조 하는 Entity SQL 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-167">For example, if `p` is an expression of type Person, the following is the Entity SQL syntax for referencing the city of the address of this person.</span></span>  
  
```sql  
p.Address.City
```  
  
## <a name="no-support-for-"></a><span data-ttu-id="d2a39-168">지원 안 함 \*</span><span class="sxs-lookup"><span data-stu-id="d2a39-168">No Support for \*</span></span>  

 <span data-ttu-id="d2a39-169">Transact-sql은 정규화 되지 \* 않은 구문을 전체 행의 별칭으로 지원 하 고 \* \* 해당 테이블의 필드에 대 한 바로 가기로 정규화 된 구문 (t.)을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-169">Transact-SQL supports the unqualified \* syntax as an alias for the entire row, and the qualified \* syntax (t.\*) as a shortcut for the fields of that table.</span></span> <span data-ttu-id="d2a39-170">또한 Transact-sql은 null을 포함 하는 특수 count ( \* ) 집계를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-170">In addition, Transact-SQL allows for a special count(\*) aggregate, which includes nulls.</span></span>  
  
 <span data-ttu-id="d2a39-171">Entity SQL는 \* 구문을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-171">Entity SQL does not support the \* construct.</span></span> <span data-ttu-id="d2a39-172">및 형식의 transact-sql 쿼리는 각각 및 `select * from T` `select T1.* from T1, T2...` 로 Entity SQL로 표현 될 수 있습니다 `select value t from T as t` `select value t1 from T1 as t1, T2 as t2...` .</span><span class="sxs-lookup"><span data-stu-id="d2a39-172">Transact-SQL queries of the form `select * from T` and `select T1.* from T1, T2...` can be expressed in Entity SQL as `select value t from T as t` and `select value t1 from T1 as t1, T2 as t2...`, respectively.</span></span> <span data-ttu-id="d2a39-173">또한 이러한 구문은 상속(값 대체성)을 처리하지만, `select *` 변형은 선언된 형식의 최상위 속성으로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-173">Additionally, these constructs handle inheritance (value substitutability), while the `select *` variants are restricted to top-level properties of the declared type.</span></span>  
  
 <span data-ttu-id="d2a39-174">Entity SQL는 집계를 지원 하지 않습니다 `count(*)` .</span><span class="sxs-lookup"><span data-stu-id="d2a39-174">Entity SQL does not support the `count(*)` aggregate.</span></span> <span data-ttu-id="d2a39-175">대신 `count(0)`를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a39-175">Use `count(0)` instead.</span></span>  
  
## <a name="changes-to-group-by"></a><span data-ttu-id="d2a39-176">Group By 변경</span><span class="sxs-lookup"><span data-stu-id="d2a39-176">Changes to Group By</span></span>  

 <span data-ttu-id="d2a39-177">Entity SQL는 키의 별칭을 지원 `group by` 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-177">Entity SQL supports aliasing of `group by` keys.</span></span> <span data-ttu-id="d2a39-178">`select`절 및 `having` 절의 식은 이러한 별칭을 통해 키를 참조 해야 합니다 `group by` .</span><span class="sxs-lookup"><span data-stu-id="d2a39-178">Expressions in the `select` clause and `having` clause must refer to the `group by` keys via these aliases.</span></span> <span data-ttu-id="d2a39-179">예를 들어이 Entity SQL 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-179">For example, this Entity SQL syntax:</span></span>  
  
```sql  
SELECT k1, count(t.a), sum(t.a)
FROM T AS t
GROUP BY t.b + t.c AS k1
```  
  
 <span data-ttu-id="d2a39-180">... 는 다음 Transact-sql과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-180">...is equivalent to the following Transact-SQL:</span></span>  
  
```sql  
SELECT b + c, count(*), sum(a)
FROM T
GROUP BY b + c
```  
  
## <a name="collection-based-aggregates"></a><span data-ttu-id="d2a39-181">컬렉션 기반 집계</span><span class="sxs-lookup"><span data-stu-id="d2a39-181">Collection-Based Aggregates</span></span>  

 <span data-ttu-id="d2a39-182">Entity SQL는 두 가지 종류의 집계를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-182">Entity SQL supports two kinds of aggregates.</span></span>  
  
 <span data-ttu-id="d2a39-183">컬렉션 기반 집계는 컬렉션에 대해 작동하며 집계된 결과를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-183">Collection-based aggregates operate on collections and produce the aggregated result.</span></span> <span data-ttu-id="d2a39-184">이는 쿼리 내의 임의의 위치에 나타날 수 있으며 `group by` 절이 필요 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-184">These can appear anywhere in the query, and do not require a `group by` clause.</span></span> <span data-ttu-id="d2a39-185">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="d2a39-185">For example:</span></span>  
  
```sql  
SELECT t.a AS a, count({1,2,3}) AS b FROM T AS t
```  
  
 <span data-ttu-id="d2a39-186">Entity SQL는 SQL 스타일 집계도 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-186">Entity SQL also supports SQL-style aggregates.</span></span> <span data-ttu-id="d2a39-187">다음은 그 예입니다. </span><span class="sxs-lookup"><span data-stu-id="d2a39-187">For example:</span></span>  
  
```sql  
SELECT a, sum(t.b) FROM T AS t GROUP BY t.a AS a
```  
  
## <a name="order-by-clause-usage"></a><span data-ttu-id="d2a39-188">ORDER BY 절 사용법</span><span class="sxs-lookup"><span data-stu-id="d2a39-188">ORDER BY Clause Usage</span></span>  

<span data-ttu-id="d2a39-189">Transact-sql `ORDER BY` 을 사용 하 여 절은 최상위 블록 에서만 지정할 수 있습니다 `SELECT .. FROM .. WHERE` .</span><span class="sxs-lookup"><span data-stu-id="d2a39-189">Transact-SQL allows `ORDER BY` clauses to be specified only in the topmost `SELECT .. FROM .. WHERE` block.</span></span> <span data-ttu-id="d2a39-190">Entity SQL에서 중첩 된 식을 사용할 수 있으며, `ORDER BY` 쿼리의 아무 곳에 나 배치할 수 있지만 중첩 된 쿼리의 순서 지정은 유지 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-190">In Entity SQL, you can use a nested `ORDER BY` expression and it can be placed anywhere in the query, but ordering in a nested query is not preserved.</span></span>  
  
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
  
## <a name="identifiers"></a><span data-ttu-id="d2a39-191">식별자</span><span class="sxs-lookup"><span data-stu-id="d2a39-191">Identifiers</span></span>  

 <span data-ttu-id="d2a39-192">Transact-sql에서 식별자 비교는 현재 데이터베이스의 데이터 정렬을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-192">In Transact-SQL, identifier comparison is based on the collation of the current database.</span></span> <span data-ttu-id="d2a39-193">Entity SQL에서 식별자는 항상 대/소문자를 구분 하지 않고 악센트를 구분 합니다. 즉, Entity SQL 악센트 부호가 있는 문자와 악센트 부호가 없는 문자를 구분 합니다. 예를 들어 ' a '는 ' ấ '와 같지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-193">In Entity SQL, identifiers are always case insensitive and accent sensitive (that is, Entity SQL distinguishes between accented and unaccented characters; for example, 'a' is not equal to 'ấ').</span></span> <span data-ttu-id="d2a39-194">Entity SQL는 동일 하지만 서로 다른 코드 페이지에서 가져온 문자 버전을 다른 문자로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-194">Entity SQL treats versions of letters that appear the same but are from different code pages as different characters.</span></span> <span data-ttu-id="d2a39-195">자세한 내용은 [입력 문자 집합](input-character-set-entity-sql.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d2a39-195">For more information, see [Input Character Set](input-character-set-entity-sql.md).</span></span>  
  
## <a name="transact-sql-functionality-not-available-in-entity-sql"></a><span data-ttu-id="d2a39-196">Entity SQL에서 사용할 수 없는 Transact-SQL 기능</span><span class="sxs-lookup"><span data-stu-id="d2a39-196">Transact-SQL Functionality Not Available in Entity SQL</span></span>  

 <span data-ttu-id="d2a39-197">다음 Transact-sql 기능은 Entity SQL에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-197">The following Transact-SQL functionality is not available in Entity SQL.</span></span>  
  
 <span data-ttu-id="d2a39-198">DML</span><span class="sxs-lookup"><span data-stu-id="d2a39-198">DML</span></span>  
 <span data-ttu-id="d2a39-199">현재 Entity SQL는 DML 문 (insert, update, delete)을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-199">Entity SQL currently provides no support for DML statements (insert, update, delete).</span></span>  
  
 <span data-ttu-id="d2a39-200">DDL</span><span class="sxs-lookup"><span data-stu-id="d2a39-200">DDL</span></span>  
 <span data-ttu-id="d2a39-201">Entity SQL은 현재 버전의 DDL을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-201">Entity SQL provides no support for DDL in the current version.</span></span>  
  
 <span data-ttu-id="d2a39-202">명령형 프로그래밍 비교</span><span class="sxs-lookup"><span data-stu-id="d2a39-202">Imperative Programming</span></span>  
 <span data-ttu-id="d2a39-203">Entity SQL는 Transact-sql과 달리 명령적 프로그래밍에 대 한 지원을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-203">Entity SQL provides no support for imperative programming, unlike Transact-SQL.</span></span> <span data-ttu-id="d2a39-204">대신 프로그래밍 언어를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-204">Use a programming language instead.</span></span>  
  
 <span data-ttu-id="d2a39-205">그룹화 함수</span><span class="sxs-lookup"><span data-stu-id="d2a39-205">Grouping Functions</span></span>  
 <span data-ttu-id="d2a39-206">Entity SQL는 함수 그룹화 (예: 큐브, 롤업 및 GROUPING_SET)를 아직 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-206">Entity SQL does not yet provide support for grouping functions (for example, CUBE, ROLLUP, and GROUPING_SET).</span></span>  
  
 <span data-ttu-id="d2a39-207">분석 함수</span><span class="sxs-lookup"><span data-stu-id="d2a39-207">Analytic Functions</span></span>  
 <span data-ttu-id="d2a39-208">Entity SQL는 아직 분석 함수를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-208">Entity SQL does not (yet) provide support for analytic functions.</span></span>  
  
 <span data-ttu-id="d2a39-209">기본 제공 함수, 연산자</span><span class="sxs-lookup"><span data-stu-id="d2a39-209">Built-in Functions, Operators</span></span>  
 <span data-ttu-id="d2a39-210">Entity SQL는 Transact-sql의 기본 제공 함수 및 연산자의 하위 집합을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-210">Entity SQL supports a subset of Transact-SQL's built in functions and operators.</span></span> <span data-ttu-id="d2a39-211">이러한 연산자와 함수는 주요 저장소 공급자에서 주로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-211">These operators and functions are likely to be supported by the major store providers.</span></span> <span data-ttu-id="d2a39-212">Entity SQL는 공급자 매니페스트에 선언 된 저장소 관련 함수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-212">Entity SQL uses the store-specific functions declared in a provider manifest.</span></span> <span data-ttu-id="d2a39-213">또한 Entity Framework를 사용 하 여 Entity SQL에서 사용할 수 있도록 기본 제공 및 사용자 정의 기존 저장소 함수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-213">Additionally, the Entity Framework allows you to declare built-in and user-defined existing store functions, for Entity SQL to use.</span></span>  
  
 <span data-ttu-id="d2a39-214">힌트</span><span class="sxs-lookup"><span data-stu-id="d2a39-214">Hints</span></span>  
 <span data-ttu-id="d2a39-215">Entity SQL는 쿼리 힌트에 대 한 메커니즘을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-215">Entity SQL does not provide mechanisms for query hints.</span></span>  
  
 <span data-ttu-id="d2a39-216">쿼리 결과 일괄 처리</span><span class="sxs-lookup"><span data-stu-id="d2a39-216">Batching Query Results</span></span>  
 <span data-ttu-id="d2a39-217">Entity SQL는 쿼리 결과 일괄 처리를 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-217">Entity SQL does not support batching query results.</span></span> <span data-ttu-id="d2a39-218">예를 들어 다음은 유효한 Transact-sql (일괄 처리로 보내기)입니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-218">For example, the following is valid Transact-SQL (sending as a batch):</span></span>  
  
```sql  
SELECT * FROM products;
SELECT * FROM catagories;
```  
  
 <span data-ttu-id="d2a39-219">그러나 해당 Entity SQL은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-219">However, the equivalent Entity SQL is not supported:</span></span>  
  
```sql  
SELECT value p FROM Products AS p;
SELECT value c FROM Categories AS c;
```  
  
 <span data-ttu-id="d2a39-220">Entity SQL은 명령 당 하나의 결과 생성 쿼리 문만 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="d2a39-220">Entity SQL only supports one result-producing query statement per command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2a39-221">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d2a39-221">See also</span></span>

- [<span data-ttu-id="d2a39-222">Entity SQL 개요</span><span class="sxs-lookup"><span data-stu-id="d2a39-222">Entity SQL Overview</span></span>](entity-sql-overview.md)
- [<span data-ttu-id="d2a39-223">지원되지 않는 식</span><span class="sxs-lookup"><span data-stu-id="d2a39-223">Unsupported Expressions</span></span>](unsupported-expressions-entity-sql.md)
