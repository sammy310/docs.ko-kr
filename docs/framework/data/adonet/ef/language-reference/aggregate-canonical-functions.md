---
description: '자세한 정보: 집계 정식 함수'
title: 집계 정식 함수
ms.date: 03/30/2017
ms.assetid: 3bcff826-ca90-41b3-a791-04d6ff0e5085
ms.openlocfilehash: e26888ac15553a592f7d2cb9b1a0941161115615
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99697298"
---
# <a name="aggregate-canonical-functions"></a><span data-ttu-id="bd3f1-103">집계 정식 함수</span><span class="sxs-lookup"><span data-stu-id="bd3f1-103">Aggregate Canonical Functions</span></span>

<span data-ttu-id="bd3f1-104">집계는 일련의 입력 값을 단일 값으로 줄이는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-104">Aggregates are expressions that reduce a series of input values into, for example, a single value.</span></span> <span data-ttu-id="bd3f1-105">집계는 일반적으로 SELECT 식의 GROUP BY 절과 함께 사용되며 사용할 수 있는 위치에 대한 제약 조건이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-105">Aggregates are normally used in conjunction with the GROUP BY clause of the SELECT expression, and there are constraints on where they can be used.</span></span>

## <a name="aggregate-entity-sql-canonical-functions"></a><span data-ttu-id="bd3f1-106">집계 Entity SQL 정식 함수</span><span class="sxs-lookup"><span data-stu-id="bd3f1-106">Aggregate Entity SQL canonical functions</span></span>

<span data-ttu-id="bd3f1-107">다음은 집계 Entity SQL 정식 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-107">The following are the aggregate Entity SQL canonical functions.</span></span>

### <a name="avgexpression"></a><span data-ttu-id="bd3f1-108">Avg(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-108">Avg(expression)</span></span>

<span data-ttu-id="bd3f1-109">null이 아닌 값의 평균을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-109">Returns the average of the non-null values.</span></span>

<span data-ttu-id="bd3f1-110">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-110">**Arguments**</span></span>

<span data-ttu-id="bd3f1-111">`Int32`, `Int64`, `Double` 및 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-111">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="bd3f1-112">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-112">**Return Value**</span></span>

<span data-ttu-id="bd3f1-113">의 형식 `expression` 이거나, `null` 모든 입력 값이 값인 경우입니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="bd3f1-113">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="bd3f1-114">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-114">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_avg)]
[!code-sql[DP EntityServices Concepts#EDM_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_avg)]

### <a name="bigcountexpression"></a><span data-ttu-id="bd3f1-115">BigCount(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-115">BigCount(expression)</span></span>

<span data-ttu-id="bd3f1-116">null 값과 중복 값을 비롯한 집계의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-116">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="bd3f1-117">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-117">**Arguments**</span></span>

<span data-ttu-id="bd3f1-118">모든 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-118">Any type.</span></span>

<span data-ttu-id="bd3f1-119">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-119">**Return Value**</span></span>

<span data-ttu-id="bd3f1-120">`Int64`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-120">An `Int64`.</span></span>

<span data-ttu-id="bd3f1-121">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-121">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_bigcount)]
[!code-sql[DP EntityServices Concepts#EDM_BIGCOUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_bigcount)]

### <a name="countexpression"></a><span data-ttu-id="bd3f1-122">Count(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-122">Count(expression)</span></span>

<span data-ttu-id="bd3f1-123">null 값과 중복 값을 비롯한 집계의 크기를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-123">Returns the size of the aggregate including null and duplicate values.</span></span>

<span data-ttu-id="bd3f1-124">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-124">**Arguments**</span></span>

<span data-ttu-id="bd3f1-125">모든 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-125">Any type.</span></span>

<span data-ttu-id="bd3f1-126">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-126">**Return Value**</span></span>

<span data-ttu-id="bd3f1-127">`Int32`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-127">An `Int32`.</span></span>

<span data-ttu-id="bd3f1-128">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-128">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_count)]
[!code-sql[DP EntityServices Concepts#EDM_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_count)]

### <a name="maxexpression"></a><span data-ttu-id="bd3f1-129">Max(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-129">Max(expression)</span></span>

<span data-ttu-id="bd3f1-130">null이 아닌 값의 최대값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-130">Returns the maximum of the non-null values.</span></span>

<span data-ttu-id="bd3f1-131">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-131">**Arguments**</span></span>

<span data-ttu-id="bd3f1-132">`Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-132">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="bd3f1-133">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-133">**Return Value**</span></span>

<span data-ttu-id="bd3f1-134">의 형식 `expression` 이거나, `null` 모든 입력 값이 값인 경우입니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="bd3f1-134">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="bd3f1-135">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-135">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_max)]
[!code-sql[DP EntityServices Concepts#EDM_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_max)]

### <a name="minexpression"></a><span data-ttu-id="bd3f1-136">Min(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-136">Min(expression)</span></span>

<span data-ttu-id="bd3f1-137">null이 아닌 값의 최소값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-137">Returns the minimum of the non-null values.</span></span>

<span data-ttu-id="bd3f1-138">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-138">**Arguments**</span></span>

<span data-ttu-id="bd3f1-139">`Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-139">A `Byte`, `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, `Decimal`, `DateTime`, `DateTimeOffset`, `Time`, `String`, `Binary`.</span></span>

<span data-ttu-id="bd3f1-140">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-140">**Return Value**</span></span>

<span data-ttu-id="bd3f1-141">의 형식 `expression` 이거나, `null` 모든 입력 값이 값인 경우입니다 `null` .</span><span class="sxs-lookup"><span data-stu-id="bd3f1-141">The type of `expression`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="bd3f1-142">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-142">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_min)]
[!code-sql[DP EntityServices Concepts#EDM_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_min)]

### <a name="stdevexpression"></a><span data-ttu-id="bd3f1-143">StDev(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-143">StDev(expression)</span></span>

<span data-ttu-id="bd3f1-144">null이 아닌 값의 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-144">Returns the standard deviation of the non-null values.</span></span>

<span data-ttu-id="bd3f1-145">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-145">**Arguments**</span></span>

<span data-ttu-id="bd3f1-146">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-146">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="bd3f1-147">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-147">**Return Value**</span></span>

<span data-ttu-id="bd3f1-148">`Double`</span><span class="sxs-lookup"><span data-stu-id="bd3f1-148">A `Double`.</span></span> <span data-ttu-id="bd3f1-149">모든 입력 값이 `Null` 값인 경우 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-149">`Null`, if all input values are `null` values.</span></span>

<span data-ttu-id="bd3f1-150">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-150">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdev)]
[!code-sql[DP EntityServices Concepts#EDM_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdev)]

### <a name="stdevpexpression"></a><span data-ttu-id="bd3f1-151">StDevP(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-151">StDevP(expression)</span></span>

<span data-ttu-id="bd3f1-152">모든 값의 모집단에 대한 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-152">Returns the standard deviation for the population of all values.</span></span>

<span data-ttu-id="bd3f1-153">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-153">**Arguments**</span></span>

<span data-ttu-id="bd3f1-154">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-154">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="bd3f1-155">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-155">**Return Value**</span></span>

<span data-ttu-id="bd3f1-156">`Double`이거나, `null` 모든 입력 값이 값 이면 `null` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-156">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="bd3f1-157">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-157">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_stdevp)]
[!code-sql[DP EntityServices Concepts#EDM_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_stdevp)]

### <a name="sumexpression"></a><span data-ttu-id="bd3f1-158">Sum(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-158">Sum(expression)</span></span>

<span data-ttu-id="bd3f1-159">null이 아닌 값의 합계를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-159">Returns the sum of the non-null values.</span></span>

<span data-ttu-id="bd3f1-160">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-160">**Arguments**</span></span>

<span data-ttu-id="bd3f1-161">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-161">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="bd3f1-162">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-162">**Return Value**</span></span>

<span data-ttu-id="bd3f1-163">`Double`이거나, `null` 모든 입력 값이 값 이면 `null` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-163">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="bd3f1-164">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-164">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_sum)]
[!code-sql[DP EntityServices Concepts#EDM_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_sum)]

### <a name="varexpression"></a><span data-ttu-id="bd3f1-165">Var(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-165">Var(expression)</span></span>

<span data-ttu-id="bd3f1-166">null이 아닌 모든 값의 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-166">Returns the variance of all non-null values.</span></span>

<span data-ttu-id="bd3f1-167">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-167">**Arguments**</span></span>

<span data-ttu-id="bd3f1-168">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-168">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="bd3f1-169">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-169">**Return Value**</span></span>

<span data-ttu-id="bd3f1-170">`Double`이거나, `null` 모든 입력 값이 값 이면 `null` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-170">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="bd3f1-171">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-171">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_var)]
[!code-sql[DP EntityServices Concepts#EDM_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_var)]

### <a name="varpexpression"></a><span data-ttu-id="bd3f1-172">VarP(expression)</span><span class="sxs-lookup"><span data-stu-id="bd3f1-172">VarP(expression)</span></span>

<span data-ttu-id="bd3f1-173">null이 아닌 모든 값의 모집단에 대한 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-173">Returns the variance for the population of all non-null values.</span></span>

<span data-ttu-id="bd3f1-174">**인수**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-174">**Arguments**</span></span>

<span data-ttu-id="bd3f1-175">`Int32`, `Int64`, `Double`, `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-175">An `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="bd3f1-176">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-176">**Return Value**</span></span>

<span data-ttu-id="bd3f1-177">`Double`이거나, `null` 모든 입력 값이 값 이면 `null` 입니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-177">A `Double`, or `null` if all input values are `null` values.</span></span>

<span data-ttu-id="bd3f1-178">**예제**</span><span class="sxs-lookup"><span data-stu-id="bd3f1-178">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_varp)]
[!code-sql[DP EntityServices Concepts#EDM_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_varp)]

<span data-ttu-id="bd3f1-179">동일한 기능을 Microsoft SQL 클라이언트 관리 공급자에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-179">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="bd3f1-180">자세한 내용은 [Entity Framework 함수에 대 한 SqlClient](../sqlclient-for-ef-functions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-180">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>

## <a name="collection-based-aggregates"></a><span data-ttu-id="bd3f1-181">컬렉션 기반 집계</span><span class="sxs-lookup"><span data-stu-id="bd3f1-181">Collection-based aggregates</span></span>

<span data-ttu-id="bd3f1-182">컬렉션 기반 집계(컬렉션 함수)는 컬렉션에 대해 작업을 수행하고 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-182">Collection-based aggregates (collection functions) operate on collections and return a value.</span></span> <span data-ttu-id="bd3f1-183">예를 들어 ORDERS가 모든 주문의 컬렉션인 경우 다음 식을 사용 하 여 가장 빠른 운송 날짜를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-183">For example if ORDERS is a collection of all orders, you can calculate the earliest ship date with the following expression:</span></span>

```sql
min(select value o.ShipDate from LOB.Orders as o)
```

<span data-ttu-id="bd3f1-184">컬렉션 기반 집계 내의 식은 현재 앰비언트 이름 결정 범위 내에서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-184">Expressions inside collection-based aggregates are evaluated within the current ambient name-resolution scope.</span></span>

## <a name="group-based-aggregates"></a><span data-ttu-id="bd3f1-185">그룹 기반 집계</span><span class="sxs-lookup"><span data-stu-id="bd3f1-185">Group-based aggregates</span></span>

<span data-ttu-id="bd3f1-186">그룹 기반 집계는 GROUP BY 절에 정의된 대로 그룹에 대해 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-186">Group-based aggregates are calculated over a group as defined by the GROUP BY clause.</span></span> <span data-ttu-id="bd3f1-187">결과의 각 그룹별로 각 그룹의 요소를 집계 계산에 대한 입력으로 사용하여 개별 집계가 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-187">For each group in the result, a separate aggregate is calculated by using the elements in each group as input to the aggregate calculation.</span></span> <span data-ttu-id="bd3f1-188">SELECT 식에 GROUP BY 절이 사용되는 경우에는 식 이름, 집계 또는 상수를 그룹화하는 식만 프로젝션 또는 ORDER BY 절에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-188">When a group-by clause is used in a select expression, only grouping expression names, aggregates, or constant expressions can be present in the projection or order-by clause.</span></span>

<span data-ttu-id="bd3f1-189">다음 예제에서는 각 제품에 대해 주문된 평균 수량을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-189">The following example calculates the average quantity ordered for each product:</span></span>

```sql
select p, avg(ol.Quantity) from LOB.OrderLines as ol
  group by ol.Product as p
```

<span data-ttu-id="bd3f1-190">SELECT 식에서 group by 절을 명시적으로 사용 하지 않고 그룹 기반 집계가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-190">It's possible to have a group-based aggregate without an explicit group-by clause in the SELECT expression.</span></span> <span data-ttu-id="bd3f1-191">이 경우 모든 요소는 단일 그룹으로 처리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-191">In this case, all elements are treated as a single group.</span></span> <span data-ttu-id="bd3f1-192">이는 상수를 기준으로 그룹화를 지정 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-192">This is equivalent of specifying a grouping based on a constant.</span></span> <span data-ttu-id="bd3f1-193">예를 들어, 다음 식을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-193">Take, for example, the following expression:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol
```

<span data-ttu-id="bd3f1-194">이 식은 다음 식과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-194">This is equivalent to the following:</span></span>

```sql
select avg(ol.Quantity) from LOB.OrderLines as ol group by 1
```

<span data-ttu-id="bd3f1-195">그룹 기반 집계 내의 식은 WHERE 절 식에 표시되는 이름 확인 범위 내에서 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-195">Expressions inside the group-based aggregate are evaluated within the name-resolution scope that would be visible to the WHERE clause expression.</span></span>

<span data-ttu-id="bd3f1-196">Transact-sql에서와 마찬가지로 그룹 기반 집계도 ALL 또는 DISTINCT 한정자를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-196">As in Transact-SQL, group-based aggregates can also specify an ALL or DISTINCT modifier.</span></span> <span data-ttu-id="bd3f1-197">DISTINCT 한정자를 지정하면 집계가 계산되기 전에 집계 입력 컬렉션에서 중복 항목이 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-197">If the DISTINCT modifier is specified, duplicates are eliminated from the aggregate input collection, before the aggregate is computed.</span></span> <span data-ttu-id="bd3f1-198">ALL 한정자를 지정하거나 어떠한 한정자도 지정하지 않으면 중복 항목이 제거되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bd3f1-198">If the ALL modifier is specified (or if no modifier is specified), no duplicate elimination is performed.</span></span>

## <a name="see-also"></a><span data-ttu-id="bd3f1-199">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd3f1-199">See also</span></span>

- [<span data-ttu-id="bd3f1-200">정식 함수</span><span class="sxs-lookup"><span data-stu-id="bd3f1-200">Canonical Functions</span></span>](canonical-functions.md)
