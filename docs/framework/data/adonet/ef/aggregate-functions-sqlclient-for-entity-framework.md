---
title: 집계 함수(Entity Framework용 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: 1fad25f2229b4fa810cf82a96dcb8c50a9de3070
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79150651"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="a4ab3-102">집계 함수(Entity Framework용 SqlClient)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-102">Aggregate Functions (SqlClient for Entity Framework)</span></span>
<span data-ttu-id="a4ab3-103">.NET Framework Data Provider for SQL Server(SqlClient)에서는 집계 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="a4ab3-104">집계 함수는 입력 값 집합에 대해 계산을 수행하여 하나의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-104">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="a4ab3-105">이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="a4ab3-106">공급자의 네임스페이스 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="a4ab3-107">다음은 SqlClient 집계 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-107">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="a4ab3-108">AVG(식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-108">AVG(expression)</span></span>

<span data-ttu-id="a4ab3-109">컬렉션에 포함된 값의 평균을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-109">Returns the average of the values in a collection.</span></span> <span data-ttu-id="a4ab3-110">Null 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-110">Null values are ignored.</span></span>

<span data-ttu-id="a4ab3-111">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-111">**Arguments**</span></span>

<span data-ttu-id="a4ab3-112">`Int32`, `Int64`, `Double` 및 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-112">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="a4ab3-113">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-113">**Return Value**</span></span>

<span data-ttu-id="a4ab3-114">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-114">The type of `expression`.</span></span>

<span data-ttu-id="a4ab3-115">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-115">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="a4ab3-116">CHECKSUM_AGG(컬렉션)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-116">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="a4ab3-117">컬렉션에 있는 값의 체크섬을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-117">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="a4ab3-118">Null 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-118">Null values are ignored.</span></span>

 <span data-ttu-id="a4ab3-119">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-119">**Arguments**</span></span>

 <span data-ttu-id="a4ab3-120">컬렉션().`Int32`</span><span class="sxs-lookup"><span data-stu-id="a4ab3-120">A Collection(`Int32`).</span></span>

 <span data-ttu-id="a4ab3-121">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-121">**Return Value**</span></span>

 <span data-ttu-id="a4ab3-122">`Int32`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-122">An `Int32`.</span></span>

 <span data-ttu-id="a4ab3-123">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-123">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="a4ab3-124">COUNT(식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-124">COUNT(expression)</span></span>

<span data-ttu-id="a4ab3-125">컬렉션의 항목 수를 `Int32`로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-125">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="a4ab3-126">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-126">**Arguments**</span></span>

<span data-ttu-id="a4ab3-127">컬렉션\<T는 다음 유형 중 하나인 컬렉션 t>.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-127">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="a4ab3-128">`Guid`(SQL Server 2000에서 반환되지 않음)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-128">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="a4ab3-129">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-129">**Return Value**</span></span>

<span data-ttu-id="a4ab3-130">`Int32`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-130">An `Int32`.</span></span>

<span data-ttu-id="a4ab3-131">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-131">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="a4ab3-132">COUNT_BIG(식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-132">COUNT_BIG(expression)</span></span>

<span data-ttu-id="a4ab3-133">컬렉션의 항목 수를 `bigint`로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-133">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="a4ab3-134">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-134">**Arguments**</span></span>

 <span data-ttu-id="a4ab3-135">T가 다음 유형 중 하나인 컬렉션(T)은 다음과 같은 유형 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-135">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="a4ab3-136">`Guid`(SQL Server 2000에서 반환되지 않음)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-136">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="a4ab3-137">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-137">**Return Value**</span></span>

<span data-ttu-id="a4ab3-138">`Int64`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-138">An `Int64`.</span></span>

<span data-ttu-id="a4ab3-139">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-139">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="a4ab3-140">MAX(표현식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-140">MAX(expression)</span></span>

<span data-ttu-id="a4ab3-141">컬렉션의 최대값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-141">Returns the maximum value the collection.</span></span>

<span data-ttu-id="a4ab3-142">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-142">**Arguments**</span></span>

<span data-ttu-id="a4ab3-143">T가 다음 유형 중 하나인 컬렉션(T)은 다음과 같은 유형 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-143">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="a4ab3-144">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-144">**Return Value**</span></span>

<span data-ttu-id="a4ab3-145">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-145">The type of `expression`.</span></span>

<span data-ttu-id="a4ab3-146">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-146">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="a4ab3-147">MIN(표현식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-147">MIN(expression)</span></span>

<span data-ttu-id="a4ab3-148">컬렉션의 최소값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-148">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="a4ab3-149">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-149">**Arguments**</span></span>

<span data-ttu-id="a4ab3-150">T가 다음 유형 중 하나인 컬렉션(T)은 다음과 같은 유형 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-150">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="a4ab3-151">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-151">**Return Value**</span></span>

<span data-ttu-id="a4ab3-152">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-152">The type of `expression`.</span></span>

<span data-ttu-id="a4ab3-153">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-153">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="a4ab3-154">STDEV(표현식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-154">STDEV(expression)</span></span>

<span data-ttu-id="a4ab3-155">지정한 식의 모든 값에 대한 통계적 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-155">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="a4ab3-156">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-156">**Arguments**</span></span>

<span data-ttu-id="a4ab3-157">컬렉션().`Double`</span><span class="sxs-lookup"><span data-stu-id="a4ab3-157">A Collection(`Double`).</span></span>

<span data-ttu-id="a4ab3-158">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-158">**Return Value**</span></span>

<span data-ttu-id="a4ab3-159">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-159">A `Double`.</span></span>

<span data-ttu-id="a4ab3-160">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-160">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="a4ab3-161">STDEVP(표현식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-161">STDEVP(expression)</span></span>

<span data-ttu-id="a4ab3-162">지정한 식에 있는 모든 값의 모집단에 대한 통계적 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-162">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="a4ab3-163">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-163">**Arguments**</span></span>

<span data-ttu-id="a4ab3-164">컬렉션().`Double`</span><span class="sxs-lookup"><span data-stu-id="a4ab3-164">A Collection(`Double`).</span></span>

<span data-ttu-id="a4ab3-165">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-165">**Return Value**</span></span>

<span data-ttu-id="a4ab3-166">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-166">A `Double`.</span></span>

<span data-ttu-id="a4ab3-167">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-167">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="a4ab3-168">SUM(표현식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-168">SUM(expression)</span></span>

<span data-ttu-id="a4ab3-169">컬렉션에 있는 모든 값의 합계를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-169">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="a4ab3-170">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-170">**Arguments**</span></span>

<span data-ttu-id="a4ab3-171">T가 다음 유형 중 하나인 컬렉션(T) `Int64` `Double`: `Decimal` `Int32`.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-171">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="a4ab3-172">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-172">**Return Value**</span></span>

<span data-ttu-id="a4ab3-173">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-173">The type of `expression`.</span></span>

<span data-ttu-id="a4ab3-174">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-174">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="a4ab3-175">VAR(표현식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-175">VAR(expression)</span></span>

<span data-ttu-id="a4ab3-176">지정한 식에 있는 모든 값의 통계적 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-176">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="a4ab3-177">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-177">**Arguments**</span></span>

<span data-ttu-id="a4ab3-178">컬렉션().`Double`</span><span class="sxs-lookup"><span data-stu-id="a4ab3-178">A Collection(`Double`).</span></span>

<span data-ttu-id="a4ab3-179">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-179">**Return Value**</span></span>

<span data-ttu-id="a4ab3-180">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-180">A `Double`.</span></span>

<span data-ttu-id="a4ab3-181">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-181">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="a4ab3-182">VARP(표현식)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-182">VARP(expression)</span></span>

<span data-ttu-id="a4ab3-183">지정한 식에 있는 모든 값의 모집단에 대한 통계적 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-183">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="a4ab3-184">**인수**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-184">**Arguments**</span></span>

<span data-ttu-id="a4ab3-185">컬렉션().`Double`</span><span class="sxs-lookup"><span data-stu-id="a4ab3-185">A Collection(`Double`).</span></span>

<span data-ttu-id="a4ab3-186">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-186">**Return Value**</span></span>

<span data-ttu-id="a4ab3-187">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="a4ab3-187">A `Double`.</span></span>

<span data-ttu-id="a4ab3-188">**예제**</span><span class="sxs-lookup"><span data-stu-id="a4ab3-188">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="a4ab3-189">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a4ab3-189">See also</span></span>

- [<span data-ttu-id="a4ab3-190">집계 함수(Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="a4ab3-190">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="a4ab3-191">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="a4ab3-191">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="a4ab3-192">집계 정식 함수</span><span class="sxs-lookup"><span data-stu-id="a4ab3-192">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
