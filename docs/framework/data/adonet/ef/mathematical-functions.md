---
title: 수학 함수
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 4512aaa2eeb3e715a1d6f7a8655912eb15162124
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79149767"
---
# <a name="mathematical-functions"></a><span data-ttu-id="125f1-102">수학 함수</span><span class="sxs-lookup"><span data-stu-id="125f1-102">Mathematical Functions</span></span>

<span data-ttu-id="125f1-103">.NET Framework Data Provider for SQL Server(SqlClient)에서는 인수로 제공된 입력 값에 대해 계산을 수행한 다음 숫자 값으로 된 결과를 반환하는 수치 연산 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-103">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="125f1-104">이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-104">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="125f1-105">공급자의 네임스페이스 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-105">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="125f1-106">다음 표는 SqlClient 수학 함수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-106">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="125f1-107">ABS(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-107">ABS(expression)</span></span>

<span data-ttu-id="125f1-108">절대 값 함수를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-108">Performs the absolute value function.</span></span>

<span data-ttu-id="125f1-109">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-109">**Arguments**</span></span>

<span data-ttu-id="125f1-110">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-110">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="125f1-111">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-111">**Return Value**</span></span>

<span data-ttu-id="125f1-112">지정한 식의 절대 값입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-112">The absolute value of the specified expression.</span></span>

<span data-ttu-id="125f1-113">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-113">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="125f1-114">ACOS(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-114">ACOS(expression)</span></span>

<span data-ttu-id="125f1-115">지정한 식의 아크코사인 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-115">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="125f1-116">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-116">**Arguments**</span></span>

<span data-ttu-id="125f1-117">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-117">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-118">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-118">**Return Value**</span></span>

<span data-ttu-id="125f1-119">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-119">A `Double`.</span></span>

<span data-ttu-id="125f1-120">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-120">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="125f1-121">아신(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-121">ASIN(expression)</span></span>

<span data-ttu-id="125f1-122">지정한 식의 아크사인 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-122">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="125f1-123">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-123">**Arguments**</span></span>

<span data-ttu-id="125f1-124">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-124">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-125">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-125">**Return Value**</span></span>

<span data-ttu-id="125f1-126">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-126">A `Double`.</span></span>

<span data-ttu-id="125f1-127">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-127">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="125f1-128">아탄(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-128">ATAN(expression)</span></span>

<span data-ttu-id="125f1-129">지정한 숫자 식의 아크탄젠트 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-129">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="125f1-130">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-130">**Arguments**</span></span>

<span data-ttu-id="125f1-131">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-131">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-132">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-132">**Return Value**</span></span>

<span data-ttu-id="125f1-133">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-133">A `Double`.</span></span>

<span data-ttu-id="125f1-134">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-134">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="125f1-135">ATN2(표현식, 표현)</span><span class="sxs-lookup"><span data-stu-id="125f1-135">ATN2(expression, expression)</span></span>

<span data-ttu-id="125f1-136">탄젠트 값이 지정한 두 숫자 식 사이에 속하는 각도를 라디안으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-136">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="125f1-137">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-137">**Arguments**</span></span>

<span data-ttu-id="125f1-138">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-138">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-139">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-139">**Return Value**</span></span>

<span data-ttu-id="125f1-140">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-140">A `Double`.</span></span>

<span data-ttu-id="125f1-141">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-141">**Example**</span></span>

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a><span data-ttu-id="125f1-142">천장(식)</span><span class="sxs-lookup"><span data-stu-id="125f1-142">CEILING(expression)</span></span>

<span data-ttu-id="125f1-143">지정한 식을 해당 식보다 크거나 같은 가장 작은 정수로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-143">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="125f1-144">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-144">**Arguments**</span></span>

<span data-ttu-id="125f1-145">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-145">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="125f1-146">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-146">**Return Value**</span></span>

<span data-ttu-id="125f1-147">을 `Int32` `Int64`, `Double`또는 `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="125f1-147">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="125f1-148">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-148">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="125f1-149">COS(식)</span><span class="sxs-lookup"><span data-stu-id="125f1-149">COS(expression)</span></span>

<span data-ttu-id="125f1-150">라디안으로 지정된 각도의 삼각 코사인을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-150">Calculates the trigonometric cosine of the specified angle in radians.</span></span>

<span data-ttu-id="125f1-151">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-151">**Arguments**</span></span>

<span data-ttu-id="125f1-152">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-152">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-153">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-153">**Return Value**</span></span>

<span data-ttu-id="125f1-154">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-154">A `Double`.</span></span>

<span data-ttu-id="125f1-155">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-155">**Example**</span></span>

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="125f1-156">COT(식)</span><span class="sxs-lookup"><span data-stu-id="125f1-156">COT(expression)</span></span>

<span data-ttu-id="125f1-157">지정된 각도의 삼각 코탄젠트를 라디안으로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-157">Calculates the trigonometric cotangent of the specified angle in radians.</span></span>

<span data-ttu-id="125f1-158">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-158">**Arguments**</span></span>

<span data-ttu-id="125f1-159">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-159">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-160">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-160">**Return Value**</span></span>

<span data-ttu-id="125f1-161">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-161">A `Double`.</span></span>

<span data-ttu-id="125f1-162">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-162">**Example**</span></span>

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="125f1-163">DEGREES(라디안)</span><span class="sxs-lookup"><span data-stu-id="125f1-163">DEGREES(radians)</span></span>

<span data-ttu-id="125f1-164">해당 각도를 도 단위로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-164">Returns the corresponding angle in degrees.</span></span>

<span data-ttu-id="125f1-165">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-165">**Arguments**</span></span>

<span data-ttu-id="125f1-166">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-166">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="125f1-167">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-167">**Return Value**</span></span>

<span data-ttu-id="125f1-168">을 `Int32` `Int64`, `Double`또는 `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="125f1-168">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="125f1-169">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-169">**Example**</span></span>

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="125f1-170">EXP(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-170">EXP(expression)</span></span>

<span data-ttu-id="125f1-171">지정한 숫자 식의 지수 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-171">Calculates the exponential value of a specified numeric expression.</span></span>

<span data-ttu-id="125f1-172">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-172">**Arguments**</span></span>

<span data-ttu-id="125f1-173">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-173">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-174">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-174">**Return Value**</span></span>

<span data-ttu-id="125f1-175">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-175">A `Double`.</span></span>

<span data-ttu-id="125f1-176">**예제 보기**`SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="125f1-176">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="125f1-177">바닥(표현)</span><span class="sxs-lookup"><span data-stu-id="125f1-177">FLOOR(expression)</span></span>

<span data-ttu-id="125f1-178">지정한 식을 해당 식보다 작거나 같은 가장 큰 정수로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-178">Converts the specified expression to the largest integer less than or equal to it.</span></span>

<span data-ttu-id="125f1-179">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-179">**Arguments**</span></span>

<span data-ttu-id="125f1-180">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-180">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-181">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-181">**Return Value**</span></span>

<span data-ttu-id="125f1-182">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-182">A `Double`.</span></span>

<span data-ttu-id="125f1-183">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-183">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="125f1-184">LOG(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-184">LOG(expression)</span></span>

<span data-ttu-id="125f1-185">지정한 `float` 식의 자연 로그를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-185">Calculates the natural logarithm of the specified `float` expression.</span></span>

<span data-ttu-id="125f1-186">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-186">**Arguments**</span></span>

<span data-ttu-id="125f1-187">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-187">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-188">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-188">**Return Value**</span></span>

<span data-ttu-id="125f1-189">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-189">A `Double`.</span></span>

<span data-ttu-id="125f1-190">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-190">**Example**</span></span>

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="125f1-191">LOG10(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-191">LOG10(expression)</span></span>

<span data-ttu-id="125f1-192">지정한 `Double` 식의 상용 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-192">Returns the base-10 logarithm of the specified `Double` expression.</span></span>

<span data-ttu-id="125f1-193">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-193">**Arguments**</span></span>

<span data-ttu-id="125f1-194">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-194">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-195">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-195">**Return Value**</span></span>

<span data-ttu-id="125f1-196">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-196">A `Double`.</span></span>

<span data-ttu-id="125f1-197">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-197">**Example**</span></span>

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="125f1-198">PI()</span><span class="sxs-lookup"><span data-stu-id="125f1-198">PI()</span></span>

<span data-ttu-id="125f1-199">파이의 상수 값을 `Double`로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-199">Returns the constant value of pi as a `Double`.</span></span>

<span data-ttu-id="125f1-200">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-200">**Return Value**</span></span>

<span data-ttu-id="125f1-201">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-201">A `Double`.</span></span>

<span data-ttu-id="125f1-202">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-202">**Example**</span></span>

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="125f1-203">전원(numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="125f1-203">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="125f1-204">지정한 숫자 식의 지정된 거듭제곱 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-204">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="125f1-205">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-205">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="125f1-206">을 `Int32` `Int64`, `Double`또는 `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="125f1-206">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="125f1-207">`Double`에 대해 계산할 거듭제곱을 나타내는 `numeric_expression`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-207">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>|

<span data-ttu-id="125f1-208">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-208">**Return Value**</span></span>

<span data-ttu-id="125f1-209">지정한 `numeric_expression`에 지정한 `power_expression`을 거듭제곱한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-209">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="125f1-210">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-210">**Example**</span></span>

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="125f1-211">라디안(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-211">RADIANS(expression)</span></span>

<span data-ttu-id="125f1-212">도를 라디안으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-212">Converts degrees to radians.</span></span>

<span data-ttu-id="125f1-213">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-213">**Arguments**</span></span>

<span data-ttu-id="125f1-214">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-214">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="125f1-215">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-215">**Return Value**</span></span>

<span data-ttu-id="125f1-216">을 `Int32` `Int64`, `Double`또는 `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="125f1-216">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="125f1-217">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-217">**Example**</span></span>

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="125f1-218">랜드([시드])</span><span class="sxs-lookup"><span data-stu-id="125f1-218">RAND([seed])</span></span>

<span data-ttu-id="125f1-219">0에서 1 사이의 임의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-219">Returns a random value from 0 through 1.</span></span>

<span data-ttu-id="125f1-220">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-220">**Arguments**</span></span>

<span data-ttu-id="125f1-221">시드 값을 으로 `Int32`.</span><span class="sxs-lookup"><span data-stu-id="125f1-221">The seed value as an `Int32`.</span></span> <span data-ttu-id="125f1-222">시드를 지정하지 않으면 SQL Server 데이터베이스 엔진에서 시드 값을 임의로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-222">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="125f1-223">지정된 초기값에 대해 반환된 결과는 항상 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-223">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="125f1-224">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-224">**Return Value**</span></span>

<span data-ttu-id="125f1-225">0에서 1 사이의 임의 `Double` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-225">A random `Double` value from 0 through 1.</span></span>

<span data-ttu-id="125f1-226">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-226">**Example**</span></span>

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="125f1-227">ROUND(numeric_expression, 길이[,기능])</span><span class="sxs-lookup"><span data-stu-id="125f1-227">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="125f1-228">숫자 식을 지정한 길이나 전체 자릿수로 반올림하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-228">Returns a numeric expression, rounded to the specified length or precision.</span></span>

<span data-ttu-id="125f1-229">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-229">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="125f1-230">을 `Int32` `Int64`, `Double`또는 `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="125f1-230">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>
|`length`| <span data-ttu-id="125f1-231">`Int32`을 반올림할 전체 자릿수를 나타내는 `numeric_expression`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-231">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="125f1-232">`length`가 양수일 경우 `numeric_expression`은 `length`에서 지정한 소수 자릿수로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-232">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="125f1-233">`length`가 음수일 경우 `numeric_expression`은 `length`에서 지정한 대로 소수점의 왼쪽에서 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-233">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="125f1-234">(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="125f1-234">Optional.</span></span> <span data-ttu-id="125f1-235">수행할 `Int32` 작업 유형을 나타내는 A입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-235">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="125f1-236">함수가 생략되거나 값이 0(기본값)이 `numeric_expression` 면 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-236">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="125f1-237">0 이외의 값을 지정하면 `numeric_expression` 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-237">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="125f1-238">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-238">**Return Value**</span></span>

<span data-ttu-id="125f1-239">지정한 `numeric_expression`에 지정한 `power_expression`을 거듭제곱한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-239">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="125f1-240">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-240">**Example**</span></span>

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="125f1-241">SIGN(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-241">SIGN(expression)</span></span>

<span data-ttu-id="125f1-242">지정된 식의 양수(+1), 영(0) 또는 음수(-1) 기호를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-242">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span>

<span data-ttu-id="125f1-243">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-243">**Arguments**</span></span>

<span data-ttu-id="125f1-244">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`</span><span class="sxs-lookup"><span data-stu-id="125f1-244">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span>

<span data-ttu-id="125f1-245">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-245">**Return Value**</span></span>

<span data-ttu-id="125f1-246">을 `Int32` `Int64`, `Double`또는 `Decimal`.</span><span class="sxs-lookup"><span data-stu-id="125f1-246">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="125f1-247">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-247">**Example**</span></span>

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="125f1-248">SIN(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-248">SIN(expression)</span></span>

<span data-ttu-id="125f1-249">라디안으로 지정한 각도의 삼각 사인을 계산하여 `Double` 식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-249">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span>

<span data-ttu-id="125f1-250">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-250">**Arguments**</span></span>

<span data-ttu-id="125f1-251">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-251">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-252">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-252">**Return Value**</span></span>

<span data-ttu-id="125f1-253">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-253">A `Double`.</span></span>

<span data-ttu-id="125f1-254">**예제 보기**`SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="125f1-254">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="125f1-255">SQRT(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-255">SQRT(expression)</span></span>

<span data-ttu-id="125f1-256">지정한 식의 제곱근을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-256">Returns the square root of the specified expression.</span></span>

<span data-ttu-id="125f1-257">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-257">**Arguments**</span></span>

<span data-ttu-id="125f1-258">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-258">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-259">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-259">**Return Value**</span></span>

<span data-ttu-id="125f1-260">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-260">A `Double`.</span></span>

<span data-ttu-id="125f1-261">**예제 보기**`SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="125f1-261">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="125f1-262">스퀘어(식)</span><span class="sxs-lookup"><span data-stu-id="125f1-262">SQUARE(expression)</span></span>

<span data-ttu-id="125f1-263">지정한 식의 제곱을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-263">Returns the square of the specified expression.</span></span>

<span data-ttu-id="125f1-264">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-264">**Arguments**</span></span>

<span data-ttu-id="125f1-265">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-265">`expression`: A `Double`.</span></span>

<span data-ttu-id="125f1-266">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-266">**Return Value**</span></span>

<span data-ttu-id="125f1-267">`Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-267">A `Double`.</span></span>

<span data-ttu-id="125f1-268">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-268">**Example**</span></span>

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="125f1-269">TAN(표현식)</span><span class="sxs-lookup"><span data-stu-id="125f1-269">TAN(expression)</span></span>

<span data-ttu-id="125f1-270">지정한 식의 탄젠트를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="125f1-270">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="125f1-271">**인수**</span><span class="sxs-lookup"><span data-stu-id="125f1-271">**Arguments**</span></span>

<span data-ttu-id="125f1-272">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="125f1-272">`expression`: `Double`</span></span>

<span data-ttu-id="125f1-273">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="125f1-273">**Return Value**</span></span>

`Double`

<span data-ttu-id="125f1-274">**예제**</span><span class="sxs-lookup"><span data-stu-id="125f1-274">**Example**</span></span>

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="125f1-275">참고 항목</span><span class="sxs-lookup"><span data-stu-id="125f1-275">See also</span></span>

- [<span data-ttu-id="125f1-276">수치 연산 함수(Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="125f1-276">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="125f1-277">Entity Framework용 SqlClient 기능</span><span class="sxs-lookup"><span data-stu-id="125f1-277">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
