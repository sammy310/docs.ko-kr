---
description: '자세히 알아보기: ORDER BY (Entity SQL)'
title: ORDER BY(Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: 092850e864ae95d50b615839265041a7e32b39a9
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696323"
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="297d1-103">ORDER BY(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="297d1-103">ORDER BY (Entity SQL)</span></span>

<span data-ttu-id="297d1-104">SELECT 문에서 반환되는 개체에 적용하는 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-104">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="297d1-105">구문</span><span class="sxs-lookup"><span data-stu-id="297d1-105">Syntax</span></span>  
  
```sql  
[ ORDER BY
   {  
      order_by_expression [SKIP n] [LIMIT n]  
      [ COLLATE collation_name ]  
      [ ASC | DESC ]  
   }  
   [ ,…n ]
]  
```  
  
## <a name="arguments"></a><span data-ttu-id="297d1-106">인수</span><span class="sxs-lookup"><span data-stu-id="297d1-106">Arguments</span></span>  

 `order_by_expression`  
 <span data-ttu-id="297d1-107">정렬 기준이 될 속성을 지정하는 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-107">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="297d1-108">여러 정렬 식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-108">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="297d1-109">ORDER BY 절에서 정렬 식의 시퀀스에 따라 정렬된 결과 집합의 구조가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-109">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="297d1-110">COLLATE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="297d1-110">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="297d1-111">`collation_name`에 지정된 데이터 정렬에 따라 ORDER BY 연산을 수행해야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-111">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="297d1-112">COLLATE는 문자열 식에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-112">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="297d1-113">ASC</span><span class="sxs-lookup"><span data-stu-id="297d1-113">ASC</span></span>  
 <span data-ttu-id="297d1-114">지정된 속성에서 값이 오름차순으로, 즉 가장 작은 값에서 가장 큰 값으로 정렬되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-114">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="297d1-115">기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-115">This is the default.</span></span>  
  
 <span data-ttu-id="297d1-116">DESC</span><span class="sxs-lookup"><span data-stu-id="297d1-116">DESC</span></span>  
 <span data-ttu-id="297d1-117">지정된 속성에서 값이 내림차순으로, 즉 가장 큰 값에서 가장 작은 값으로 정렬되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-117">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="297d1-118">LIMIT `n`</span><span class="sxs-lookup"><span data-stu-id="297d1-118">LIMIT `n`</span></span>  
 <span data-ttu-id="297d1-119">처음 `n` 개 항목만 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-119">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="297d1-120">SKIP `n`</span><span class="sxs-lookup"><span data-stu-id="297d1-120">SKIP `n`</span></span>  
 <span data-ttu-id="297d1-121">처음 `n` 개 항목을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-121">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="297d1-122">설명</span><span class="sxs-lookup"><span data-stu-id="297d1-122">Remarks</span></span>  

 <span data-ttu-id="297d1-123">ORDER BY 절은 SELECT 절의 결과에 논리적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-123">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="297d1-124">ORDER BY 절은 별칭을 사용하여 선택 목록 내 항목을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-124">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="297d1-125">ORDER BY 절은 현재 범위 내에 있는 다른 변수도 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-125">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="297d1-126">하지만, DISTINCT 한정자를 사용하여 SELECT 절이 지정된 경우 ORDER BY 절은 SELECT 절의 별칭만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-126">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="297d1-127">ORDER BY 절의 모든 식은 같지 않음 정렬(예: 보다 작음, 보다 큼)을 비교할 수 있는 형식으로 계산되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-127">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="297d1-128">이런 형식은 일반적으로 숫자, 문자열, 날짜와 같은 스칼라 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-128">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="297d1-129">비교 가능한 형식의 RowType도 순서를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-129">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="297d1-130">최상위 프로젝션에 대해서가 아니라 정렬된 집합에 대해 코드가 반복되는 경우 출력에 순서가 유지되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-130">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  

<span data-ttu-id="297d1-131">다음 샘플에서는 순서가 유지 되도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-131">In the following sample, order is guaranteed to be preserved:</span></span>

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="297d1-132">다음 쿼리에서 중첩 쿼리의 순서는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-132">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="297d1-133">정렬된 UNION, UNION ALL, EXCEPT 또는 INTERSECT 연산을 얻으려면 다음 패턴을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="297d1-133">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```sql  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="297d1-134">제한된 키워드</span><span class="sxs-lookup"><span data-stu-id="297d1-134">Restricted keywords</span></span>  

 <span data-ttu-id="297d1-135">다음 키워드를 `ORDER BY` 절에서 사용할 때는 따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-135">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
- <span data-ttu-id="297d1-136">CROSS</span><span class="sxs-lookup"><span data-stu-id="297d1-136">CROSS</span></span>  
  
- <span data-ttu-id="297d1-137">FULL</span><span class="sxs-lookup"><span data-stu-id="297d1-137">FULL</span></span>  
  
- <span data-ttu-id="297d1-138">KEY</span><span class="sxs-lookup"><span data-stu-id="297d1-138">KEY</span></span>  
  
- <span data-ttu-id="297d1-139">LEFT</span><span class="sxs-lookup"><span data-stu-id="297d1-139">LEFT</span></span>  
  
- <span data-ttu-id="297d1-140">ORDER</span><span class="sxs-lookup"><span data-stu-id="297d1-140">ORDER</span></span>  
  
- <span data-ttu-id="297d1-141">OUTER</span><span class="sxs-lookup"><span data-stu-id="297d1-141">OUTER</span></span>  
  
- <span data-ttu-id="297d1-142">RIGHT</span><span class="sxs-lookup"><span data-stu-id="297d1-142">RIGHT</span></span>  
  
- <span data-ttu-id="297d1-143">ROW</span><span class="sxs-lookup"><span data-stu-id="297d1-143">ROW</span></span>  
  
- <span data-ttu-id="297d1-144">값</span><span class="sxs-lookup"><span data-stu-id="297d1-144">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="297d1-145">중첩 쿼리 순서</span><span class="sxs-lookup"><span data-stu-id="297d1-145">Ordering Nested Queries</span></span>  

 <span data-ttu-id="297d1-146">Entity Framework에서 중첩된 식은 쿼리 내 임의의 위치에 올 수 있습니다. 중첩 쿼리의 순서는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-146">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  

<span data-ttu-id="297d1-147">다음 쿼리는 성을 기준으로 결과를 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-147">The following query will order the results by the last name:</span></span>  

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="297d1-148">다음 쿼리에서 중첩 쿼리의 순서는 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-148">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="297d1-149">예제</span><span class="sxs-lookup"><span data-stu-id="297d1-149">Example</span></span>  

 <span data-ttu-id="297d1-150">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리는 ORDER BY 연산자를 사용하여 SELECT 문에서 반환되는 개체에 적용하는 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-150">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="297d1-151">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-151">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="297d1-152">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="297d1-152">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="297d1-153">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-153">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="297d1-154">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="297d1-154">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ORDERBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="297d1-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="297d1-155">See also</span></span>

- [<span data-ttu-id="297d1-156">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="297d1-156">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="297d1-157">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="297d1-157">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="297d1-158">킵</span><span class="sxs-lookup"><span data-stu-id="297d1-158">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="297d1-159">제한</span><span class="sxs-lookup"><span data-stu-id="297d1-159">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="297d1-160">맨 위로 이동</span><span class="sxs-lookup"><span data-stu-id="297d1-160">TOP</span></span>](top-entity-sql.md)
