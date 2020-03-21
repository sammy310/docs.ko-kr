---
title: ORDER BY(Entity SQL)
ms.date: 03/30/2017
ms.assetid: c0b61572-ecee-41eb-9d7f-74132ec8a26c
ms.openlocfilehash: 1233971b172079aa48227d0ec520068afbdf0952
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150071"
---
# <a name="order-by-entity-sql"></a><span data-ttu-id="11a16-102">ORDER BY(Entity SQL)</span><span class="sxs-lookup"><span data-stu-id="11a16-102">ORDER BY (Entity SQL)</span></span>
<span data-ttu-id="11a16-103">SELECT 문에서 반환되는 개체에 적용하는 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-103">Specifies the sort order used on objects returned in a SELECT statement.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a16-104">구문</span><span class="sxs-lookup"><span data-stu-id="11a16-104">Syntax</span></span>  
  
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
  
## <a name="arguments"></a><span data-ttu-id="11a16-105">인수</span><span class="sxs-lookup"><span data-stu-id="11a16-105">Arguments</span></span>  
 `order_by_expression`  
 <span data-ttu-id="11a16-106">정렬 기준이 될 속성을 지정하는 유효한 쿼리 식입니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-106">Any valid query expression specifying a property on which to sort.</span></span> <span data-ttu-id="11a16-107">여러 정렬 식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-107">Multiple sort expressions can be specified.</span></span> <span data-ttu-id="11a16-108">ORDER BY 절에서 정렬 식의 시퀀스에 따라 정렬된 결과 집합의 구조가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-108">The sequence of the sort expressions in the ORDER BY clause defines the organization of the sorted result set.</span></span>  
  
 <span data-ttu-id="11a16-109">COLLATE {collation_name}</span><span class="sxs-lookup"><span data-stu-id="11a16-109">COLLATE {collation_name}</span></span>  
 <span data-ttu-id="11a16-110">`collation_name`에 지정된 데이터 정렬에 따라 ORDER BY 연산을 수행해야 함을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-110">Specifies that the ORDER BY operation should be performed according to the collation specified in `collation_name`.</span></span> <span data-ttu-id="11a16-111">COLLATE는 문자열 식에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-111">COLLATE is applicable only for string expressions.</span></span>  
  
 <span data-ttu-id="11a16-112">ASC</span><span class="sxs-lookup"><span data-stu-id="11a16-112">ASC</span></span>  
 <span data-ttu-id="11a16-113">지정된 속성에서 값이 오름차순으로, 즉 가장 작은 값에서 가장 큰 값으로 정렬되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-113">Specifies that the values in the specified property should be sorted in ascending order, from lowest value to highest value.</span></span> <span data-ttu-id="11a16-114">이것이 기본값입니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-114">This is the default.</span></span>  
  
 <span data-ttu-id="11a16-115">DESC</span><span class="sxs-lookup"><span data-stu-id="11a16-115">DESC</span></span>  
 <span data-ttu-id="11a16-116">지정된 속성에서 값이 내림차순으로, 즉 가장 큰 값에서 가장 작은 값으로 정렬되도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-116">Specifies that the values in the specified property should be sorted in descending order, from highest value to lowest value.</span></span>  
  
 <span data-ttu-id="11a16-117">LIMIT `n`</span><span class="sxs-lookup"><span data-stu-id="11a16-117">LIMIT `n`</span></span>  
 <span data-ttu-id="11a16-118">처음 `n` 개 항목만 선택됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-118">Only the first `n` items will be selected.</span></span>  
  
 <span data-ttu-id="11a16-119">SKIP `n`</span><span class="sxs-lookup"><span data-stu-id="11a16-119">SKIP `n`</span></span>  
 <span data-ttu-id="11a16-120">처음 `n` 개 항목을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-120">Skips the first `n` items.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="11a16-121">설명</span><span class="sxs-lookup"><span data-stu-id="11a16-121">Remarks</span></span>  
 <span data-ttu-id="11a16-122">ORDER BY 절은 SELECT 절의 결과에 논리적으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-122">The ORDER BY clause is logically applied to the result of the SELECT clause.</span></span> <span data-ttu-id="11a16-123">ORDER BY 절은 별칭을 사용하여 선택 목록 내 항목을 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-123">The ORDER BY clause can reference items in the select list by using their aliases.</span></span> <span data-ttu-id="11a16-124">ORDER BY 절은 현재 범위 내에 있는 다른 변수도 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-124">The ORDER BY clause can also reference other variables that are currently in-scope.</span></span> <span data-ttu-id="11a16-125">하지만, DISTINCT 한정자를 사용하여 SELECT 절이 지정된 경우 ORDER BY 절은 SELECT 절의 별칭만 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-125">However, if the SELECT clause has been specified with a DISTINCT modifier, the ORDER BY clause can only reference aliases from the SELECT clause.</span></span>  
  
 `SELECT c AS c1 FROM cs AS c ORDER BY c1.e1, c.e2`  
  
 <span data-ttu-id="11a16-126">ORDER BY 절의 모든 식은 같지 않음 정렬(예: 보다 작음, 보다 큼)을 비교할 수 있는 형식으로 계산되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-126">Each expression in the ORDER BY clause must evaluate to some type that can be compared for ordered inequality (less than or greater than, and so on).</span></span> <span data-ttu-id="11a16-127">이런 형식은 일반적으로 숫자, 문자열, 날짜와 같은 스칼라 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-127">These types are generally scalar primitives such as numbers, strings, and dates.</span></span> <span data-ttu-id="11a16-128">비교 가능한 형식의 RowType도 순서를 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-128">RowTypes of comparable types are also order comparable.</span></span>  
  
 <span data-ttu-id="11a16-129">최상위 프로젝션에 대해서가 아니라 정렬된 집합에 대해 코드가 반복되는 경우 출력에 순서가 유지되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-129">If your code iterates over an ordered set, other than for a top-level projection, the output is not guaranteed to have its order preserved.</span></span>  

<span data-ttu-id="11a16-130">다음 샘플에서는 순서가 유지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-130">In the following sample, order is guaranteed to be preserved:</span></span>

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="11a16-131">다음 쿼리에서는 중첩된 쿼리의 순서가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-131">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
 <span data-ttu-id="11a16-132">정렬된 UNION, UNION ALL, EXCEPT 또는 INTERSECT 연산을 얻으려면 다음 패턴을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="11a16-132">To have an ordered UNION, UNION ALL, EXCEPT, or INTERSECT operation, use the following pattern:</span></span>  
  
```sql  
SELECT ...  
FROM ( UNION/EXCEPT/INTERSECT operation )  
ORDER BY ...  
```  
  
## <a name="restricted-keywords"></a><span data-ttu-id="11a16-133">제한된 키워드</span><span class="sxs-lookup"><span data-stu-id="11a16-133">Restricted keywords</span></span>  
 <span data-ttu-id="11a16-134">다음 키워드를 `ORDER BY` 절에서 사용할 때는 따옴표로 묶어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-134">The following keywords must be enclosed in quotation marks when used in an `ORDER BY` clause:</span></span>  
  
- <span data-ttu-id="11a16-135">CROSS</span><span class="sxs-lookup"><span data-stu-id="11a16-135">CROSS</span></span>  
  
- <span data-ttu-id="11a16-136">FULL</span><span class="sxs-lookup"><span data-stu-id="11a16-136">FULL</span></span>  
  
- <span data-ttu-id="11a16-137">KEY</span><span class="sxs-lookup"><span data-stu-id="11a16-137">KEY</span></span>  
  
- <span data-ttu-id="11a16-138">LEFT</span><span class="sxs-lookup"><span data-stu-id="11a16-138">LEFT</span></span>  
  
- <span data-ttu-id="11a16-139">ORDER</span><span class="sxs-lookup"><span data-stu-id="11a16-139">ORDER</span></span>  
  
- <span data-ttu-id="11a16-140">OUTER</span><span class="sxs-lookup"><span data-stu-id="11a16-140">OUTER</span></span>  
  
- <span data-ttu-id="11a16-141">RIGHT</span><span class="sxs-lookup"><span data-stu-id="11a16-141">RIGHT</span></span>  
  
- <span data-ttu-id="11a16-142">ROW</span><span class="sxs-lookup"><span data-stu-id="11a16-142">ROW</span></span>  
  
- <span data-ttu-id="11a16-143">값</span><span class="sxs-lookup"><span data-stu-id="11a16-143">VALUE</span></span>  
  
## <a name="ordering-nested-queries"></a><span data-ttu-id="11a16-144">중첩 쿼리 순서</span><span class="sxs-lookup"><span data-stu-id="11a16-144">Ordering Nested Queries</span></span>  
 <span data-ttu-id="11a16-145">Entity Framework에서 중첩된 식은 쿼리 내 임의의 위치에 올 수 있습니다. 중첩 쿼리의 순서는 유지되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-145">In the Entity Framework, a nested expression can be placed anywhere in the query; the order of a nested query is not preserved.</span></span>  

<span data-ttu-id="11a16-146">다음 쿼리는 성으로 결과를 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-146">The following query will order the results by the last name:</span></span>  

```sql  
SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName  
```  

<span data-ttu-id="11a16-147">다음 쿼리에서는 중첩된 쿼리의 순서가 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-147">In the following query, ordering of the nested query is ignored:</span></span>  

```sql  
SELECT C2.FirstName, C2.LastName  
    FROM (SELECT C1.FirstName, C1.LastName  
        FROM AdventureWorks.Contact as C1  
        ORDER BY C1.LastName) as C2  
```  
  
## <a name="example"></a><span data-ttu-id="11a16-148">예제</span><span class="sxs-lookup"><span data-stu-id="11a16-148">Example</span></span>  
 <span data-ttu-id="11a16-149">다음 [!INCLUDE[esql](../../../../../../includes/esql-md.md)] 쿼리는 ORDER BY 연산자를 사용하여 SELECT 문에서 반환되는 개체에 적용하는 정렬 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-149">The following [!INCLUDE[esql](../../../../../../includes/esql-md.md)] query uses the ORDER BY operator to specify the sort order used on objects returned in a SELECT statement.</span></span> <span data-ttu-id="11a16-150">쿼리는 AdventureWorks Sales 모델을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-150">The query is based on the AdventureWorks Sales Model.</span></span> <span data-ttu-id="11a16-151">이 쿼리를 컴파일하고 실행하려면 다음 단계를 수행하세요.</span><span class="sxs-lookup"><span data-stu-id="11a16-151">To compile and run this query, follow these steps:</span></span>  
  
1. <span data-ttu-id="11a16-152">[How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md)의 절차를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-152">Follow the procedure in [How to: Execute a Query that Returns StructuralType Results](../how-to-execute-a-query-that-returns-structuraltype-results.md).</span></span>  
  
2. <span data-ttu-id="11a16-153">다음 쿼리를 `ExecuteStructuralTypeQuery` 메서드에 인수로 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="11a16-153">Pass the following query as an argument to the `ExecuteStructuralTypeQuery` method:</span></span>  
  
 [!code-sql[DP EntityServices Concepts#ORDERBY](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#orderby)]  
  
## <a name="see-also"></a><span data-ttu-id="11a16-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="11a16-154">See also</span></span>

- [<span data-ttu-id="11a16-155">쿼리 표현식</span><span class="sxs-lookup"><span data-stu-id="11a16-155">Query Expressions</span></span>](query-expressions-entity-sql.md)
- [<span data-ttu-id="11a16-156">엔터티 SQL 참조</span><span class="sxs-lookup"><span data-stu-id="11a16-156">Entity SQL Reference</span></span>](entity-sql-reference.md)
- [<span data-ttu-id="11a16-157">건너뛸</span><span class="sxs-lookup"><span data-stu-id="11a16-157">SKIP</span></span>](skip-entity-sql.md)
- [<span data-ttu-id="11a16-158">제한</span><span class="sxs-lookup"><span data-stu-id="11a16-158">LIMIT</span></span>](limit-entity-sql.md)
- [<span data-ttu-id="11a16-159">맨 위로</span><span class="sxs-lookup"><span data-stu-id="11a16-159">TOP</span></span>](top-entity-sql.md)
