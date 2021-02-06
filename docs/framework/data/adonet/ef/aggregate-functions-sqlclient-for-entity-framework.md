---
description: '자세한 정보: 집계 함수 (Entity Framework의 SqlClient)'
title: 집계 함수(Entity Framework용 SqlClient)
ms.date: 03/30/2017
ms.assetid: 03303f01-b591-4efc-9875-f9c608edff0b
ms.openlocfilehash: b9f1ff8c75fc09de7532b459090b0b5cd1d47262
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99651082"
---
# <a name="aggregate-functions-sqlclient-for-entity-framework"></a><span data-ttu-id="76729-103">집계 함수(Entity Framework용 SqlClient)</span><span class="sxs-lookup"><span data-stu-id="76729-103">Aggregate Functions (SqlClient for Entity Framework)</span></span>

<span data-ttu-id="76729-104">.NET Framework Data Provider for SQL Server(SqlClient)에서는 집계 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-104">The .NET Framework Data Provider for SQL Server (SqlClient) provides aggregate functions.</span></span> <span data-ttu-id="76729-105">집계 함수는 입력 값 집합에 대해 계산을 수행하여 하나의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-105">Aggregate functions perform calculations on a set of input values and return a value.</span></span> <span data-ttu-id="76729-106">이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76729-106">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="76729-107">공급자의 네임스페이스 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="76729-107">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span>  
  
 <span data-ttu-id="76729-108">다음은 SqlClient 집계 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-108">The following are the SqlClient aggregate functions.</span></span>  

## <a name="avgexpression"></a><span data-ttu-id="76729-109">AVG (expression)</span><span class="sxs-lookup"><span data-stu-id="76729-109">AVG(expression)</span></span>

<span data-ttu-id="76729-110">컬렉션에 포함된 값의 평균을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-110">Returns the average of the values in a collection.</span></span> <span data-ttu-id="76729-111">Null 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="76729-111">Null values are ignored.</span></span>

<span data-ttu-id="76729-112">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-112">**Arguments**</span></span>

<span data-ttu-id="76729-113">`Int32`, `Int64`, `Double` 및 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-113">An `Int32`, `Int64`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="76729-114">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-114">**Return Value**</span></span>

<span data-ttu-id="76729-115">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-115">The type of `expression`.</span></span>

<span data-ttu-id="76729-116">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-116">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_AVG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_avg)]

## <a name="checksum_aggcollection"></a><span data-ttu-id="76729-117">CHECKSUM_AGG (컬렉션)</span><span class="sxs-lookup"><span data-stu-id="76729-117">CHECKSUM_AGG(collection)</span></span>

 <span data-ttu-id="76729-118">컬렉션에 있는 값의 체크섬을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-118">Returns the checksum of the values in a collection.</span></span> <span data-ttu-id="76729-119">Null 값은 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="76729-119">Null values are ignored.</span></span>

 <span data-ttu-id="76729-120">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-120">**Arguments**</span></span>

 <span data-ttu-id="76729-121">컬렉션 ( `Int32` )입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-121">A Collection(`Int32`).</span></span>

 <span data-ttu-id="76729-122">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-122">**Return Value**</span></span>

 <span data-ttu-id="76729-123">`Int32`입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-123">An `Int32`.</span></span>

 <span data-ttu-id="76729-124">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-124">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CHECKSUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_checksum)]

## <a name="countexpression"></a><span data-ttu-id="76729-125">COUNT (식)</span><span class="sxs-lookup"><span data-stu-id="76729-125">COUNT(expression)</span></span>

<span data-ttu-id="76729-126">컬렉션의 항목 수를 `Int32`로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-126">Returns the number of items in a collection as an `Int32`.</span></span>

<span data-ttu-id="76729-127">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-127">**Arguments**</span></span>

<span data-ttu-id="76729-128">컬렉션입니다 \<T> . 여기서 T는 다음 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-128">A Collection\<T>, where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="76729-129">`Guid` (SQL Server 2000에서 반환 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="76729-129">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="76729-130">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-130">**Return Value**</span></span>

<span data-ttu-id="76729-131">`Int32`입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-131">An `Int32`.</span></span>

<span data-ttu-id="76729-132">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-132">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNT](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_count)]

## <a name="count_bigexpression"></a><span data-ttu-id="76729-133">COUNT_BIG (식)</span><span class="sxs-lookup"><span data-stu-id="76729-133">COUNT_BIG(expression)</span></span>

<span data-ttu-id="76729-134">컬렉션의 항목 수를 `bigint`로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-134">Returns the number of items in a collection as a `bigint`.</span></span>

 <span data-ttu-id="76729-135">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-135">**Arguments**</span></span>

 <span data-ttu-id="76729-136">컬렉션 (T) 이며, 여기서 T는 다음 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-136">A Collection(T), where T is one of the following types:</span></span>

 |   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`|<span data-ttu-id="76729-137">`Guid` (SQL Server 2000에서 반환 되지 않음)</span><span class="sxs-lookup"><span data-stu-id="76729-137">`Guid` (not returned in SQL Server 2000)</span></span>|

<span data-ttu-id="76729-138">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-138">**Return Value**</span></span>

<span data-ttu-id="76729-139">`Int64`입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-139">An `Int64`.</span></span>

<span data-ttu-id="76729-140">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-140">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_COUNTBIG](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_countbig)]

## <a name="maxexpression"></a><span data-ttu-id="76729-141">MAX (expression)</span><span class="sxs-lookup"><span data-stu-id="76729-141">MAX(expression)</span></span>

<span data-ttu-id="76729-142">컬렉션의 최대값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-142">Returns the maximum value the collection.</span></span>

<span data-ttu-id="76729-143">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-143">**Arguments**</span></span>

<span data-ttu-id="76729-144">컬렉션 (T) 이며, 여기서 T는 다음 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-144">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="76729-145">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-145">**Return Value**</span></span>

<span data-ttu-id="76729-146">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-146">The type of `expression`.</span></span>

<span data-ttu-id="76729-147">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-147">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MAX](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_max)]

## <a name="minexpression"></a><span data-ttu-id="76729-148">MIN (expression)</span><span class="sxs-lookup"><span data-stu-id="76729-148">MIN(expression)</span></span>

<span data-ttu-id="76729-149">컬렉션의 최소값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-149">Returns the minimum value in a collection.</span></span>

<span data-ttu-id="76729-150">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-150">**Arguments**</span></span>

<span data-ttu-id="76729-151">컬렉션 (T) 이며, 여기서 T는 다음 형식 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-151">A Collection(T), where T is one of the following types:</span></span>

|   |   |   |   |
|---|---|---|---|
|`Boolean`|`Double`|`DateTime`|`DateTimeOffset`|
|`Time`|`String`|`Binary`||

<span data-ttu-id="76729-152">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-152">**Return Value**</span></span>

<span data-ttu-id="76729-153">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-153">The type of `expression`.</span></span>

<span data-ttu-id="76729-154">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-154">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_MIN](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_min)]

## <a name="stdevexpression"></a><span data-ttu-id="76729-155">STDEV (식)</span><span class="sxs-lookup"><span data-stu-id="76729-155">STDEV(expression)</span></span>

<span data-ttu-id="76729-156">지정한 식의 모든 값에 대한 통계적 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-156">Returns the statistical standard deviation of all values in the specified expression.</span></span>

<span data-ttu-id="76729-157">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-157">**Arguments**</span></span>

<span data-ttu-id="76729-158">컬렉션 ( `Double` )입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-158">A Collection(`Double`).</span></span>

<span data-ttu-id="76729-159">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-159">**Return Value**</span></span>

<span data-ttu-id="76729-160">`Double`</span><span class="sxs-lookup"><span data-stu-id="76729-160">A `Double`.</span></span>

<span data-ttu-id="76729-161">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-161">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEV](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdev)]

## <a name="stdevpexpression"></a><span data-ttu-id="76729-162">STDEVP (식)</span><span class="sxs-lookup"><span data-stu-id="76729-162">STDEVP(expression)</span></span>

<span data-ttu-id="76729-163">지정한 식에 있는 모든 값의 모집단에 대한 통계적 표준 편차를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-163">Returns the statistical standard deviation for the population for all values in the specified expression.</span></span>

<span data-ttu-id="76729-164">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-164">**Arguments**</span></span>

<span data-ttu-id="76729-165">컬렉션 ( `Double` )입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-165">A Collection(`Double`).</span></span>

<span data-ttu-id="76729-166">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-166">**Return Value**</span></span>

<span data-ttu-id="76729-167">`Double`</span><span class="sxs-lookup"><span data-stu-id="76729-167">A `Double`.</span></span>

<span data-ttu-id="76729-168">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-168">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_STDEVP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_stdevp)]

## <a name="sumexpression"></a><span data-ttu-id="76729-169">합계 (식)</span><span class="sxs-lookup"><span data-stu-id="76729-169">SUM(expression)</span></span>

<span data-ttu-id="76729-170">컬렉션에 있는 모든 값의 합계를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-170">Returns the sum of all the values in the collection.</span></span>

<span data-ttu-id="76729-171">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-171">**Arguments**</span></span>

<span data-ttu-id="76729-172">컬렉션 (T) 이며, 여기서 T는 `Int32` , `Int64` , `Double` , 형식 중 하나 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-172">A Collection(T) where T is one of the following types: `Int32`, `Int64`, `Double`, `Decimal`.</span></span>

<span data-ttu-id="76729-173">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-173">**Return Value**</span></span>

<span data-ttu-id="76729-174">`expression`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-174">The type of `expression`.</span></span>

<span data-ttu-id="76729-175">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-175">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_SUM](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_sum)]

## <a name="varexpression"></a><span data-ttu-id="76729-176">VAR (expression)</span><span class="sxs-lookup"><span data-stu-id="76729-176">VAR(expression)</span></span>

<span data-ttu-id="76729-177">지정한 식에 있는 모든 값의 통계적 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-177">Returns the statistical variance of all values in the specified expression.</span></span>

<span data-ttu-id="76729-178">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-178">**Arguments**</span></span>

<span data-ttu-id="76729-179">컬렉션 ( `Double` )입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-179">A Collection(`Double`).</span></span>

<span data-ttu-id="76729-180">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-180">**Return Value**</span></span>

<span data-ttu-id="76729-181">`Double`</span><span class="sxs-lookup"><span data-stu-id="76729-181">A `Double`.</span></span>

<span data-ttu-id="76729-182">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-182">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VAR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_var)]

## <a name="varpexpression"></a><span data-ttu-id="76729-183">VARP (식)</span><span class="sxs-lookup"><span data-stu-id="76729-183">VARP(expression)</span></span>

<span data-ttu-id="76729-184">지정한 식에 있는 모든 값의 모집단에 대한 통계적 분산을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="76729-184">Returns the statistical variance for the population for all values in the specified expression.</span></span>

<span data-ttu-id="76729-185">**인수**</span><span class="sxs-lookup"><span data-stu-id="76729-185">**Arguments**</span></span>

<span data-ttu-id="76729-186">컬렉션 ( `Double` )입니다.</span><span class="sxs-lookup"><span data-stu-id="76729-186">A Collection(`Double`).</span></span>

<span data-ttu-id="76729-187">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="76729-187">**Return Value**</span></span>

<span data-ttu-id="76729-188">`Double`</span><span class="sxs-lookup"><span data-stu-id="76729-188">A `Double`.</span></span>

<span data-ttu-id="76729-189">**예제**</span><span class="sxs-lookup"><span data-stu-id="76729-189">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_VARP](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_varp)]
  
## <a name="see-also"></a><span data-ttu-id="76729-190">참고 항목</span><span class="sxs-lookup"><span data-stu-id="76729-190">See also</span></span>

- [<span data-ttu-id="76729-191">집계 함수(Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="76729-191">Aggregate Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/aggregate-functions-transact-sql)
- [<span data-ttu-id="76729-192">Entity SQL 언어</span><span class="sxs-lookup"><span data-stu-id="76729-192">Entity SQL Language</span></span>](./language-reference/entity-sql-language.md)
- [<span data-ttu-id="76729-193">집계 정식 함수</span><span class="sxs-lookup"><span data-stu-id="76729-193">Aggregate Canonical Functions</span></span>](./language-reference/aggregate-canonical-functions.md)
