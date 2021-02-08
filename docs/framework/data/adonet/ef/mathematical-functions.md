---
description: '자세한 정보: 수치 연산 함수'
title: 수학 함수
ms.date: 03/30/2017
ms.assetid: b040c7cb-156d-40f2-9152-61065b18148c
ms.openlocfilehash: 6bf1f116d6d88a8a188dc31cab91fbf26bdaea36
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99795029"
---
# <a name="mathematical-functions"></a><span data-ttu-id="7c5f3-103">수학 함수</span><span class="sxs-lookup"><span data-stu-id="7c5f3-103">Mathematical Functions</span></span>

<span data-ttu-id="7c5f3-104">.NET Framework Data Provider for SQL Server(SqlClient)에서는 인수로 제공된 입력 값에 대해 계산을 수행한 다음 숫자 값으로 된 결과를 반환하는 수치 연산 함수를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-104">The .NET Framework Data Provider for SQL Server (SqlClient) provides math functions that perform calculations on input values that are provided as arguments, and return a numeric value result.</span></span> <span data-ttu-id="7c5f3-105">이 함수는 SqlClient를 사용할 때 사용 가능한 SqlServer 네임스페이스에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-105">These functions are in the SqlServer namespace, which is available when you use SqlClient.</span></span> <span data-ttu-id="7c5f3-106">공급자의 네임스페이스 속성이 있으면 특정 구문(예: 형식 및 함수)에 대해 이 공급자가 사용하는 접두사를 Entity Framework에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-106">A provider's namespace property allows the Entity Framework to discover which prefix is used by this provider for specific constructs, such as types and functions.</span></span> <span data-ttu-id="7c5f3-107">다음 표에서는 SqlClient 수치 함수에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-107">The following table describes the SqlClient math functions.</span></span>  
  
## <a name="absexpression"></a><span data-ttu-id="7c5f3-108">ABS (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-108">ABS(expression)</span></span>

<span data-ttu-id="7c5f3-109">절대 값 함수를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-109">Performs the absolute value function.</span></span>

<span data-ttu-id="7c5f3-110">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-110">**Arguments**</span></span>

<span data-ttu-id="7c5f3-111">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-111">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="7c5f3-112">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-112">**Return Value**</span></span>

<span data-ttu-id="7c5f3-113">지정한 식의 절대 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-113">The absolute value of the specified expression.</span></span>

<span data-ttu-id="7c5f3-114">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-114">**Example**</span></span>

`SqlServer.ABS(-2)`

## <a name="acosexpression"></a><span data-ttu-id="7c5f3-115">ACOS (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-115">ACOS(expression)</span></span>

<span data-ttu-id="7c5f3-116">지정한 식의 아크코사인 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-116">Returns the arccosine value of the specified expression.</span></span>

<span data-ttu-id="7c5f3-117">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-117">**Arguments**</span></span>

<span data-ttu-id="7c5f3-118">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-118">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-119">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-119">**Return Value**</span></span>

<span data-ttu-id="7c5f3-120">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-120">A `Double`.</span></span>

<span data-ttu-id="7c5f3-121">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-121">**Example**</span></span>

`SqlServer.ACOS(.9)`

## <a name="asinexpression"></a><span data-ttu-id="7c5f3-122">ASIN (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-122">ASIN(expression)</span></span>

<span data-ttu-id="7c5f3-123">지정한 식의 아크사인 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-123">Returns the arcsine value of the specified expression.</span></span>

<span data-ttu-id="7c5f3-124">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-124">**Arguments**</span></span>

<span data-ttu-id="7c5f3-125">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-125">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-126">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-126">**Return Value**</span></span>

<span data-ttu-id="7c5f3-127">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-127">A `Double`.</span></span>

<span data-ttu-id="7c5f3-128">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-128">**Example**</span></span>

`SqlServer.ASIN(.9)`

## <a name="atanexpression"></a><span data-ttu-id="7c5f3-129">ATAN (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-129">ATAN(expression)</span></span>

<span data-ttu-id="7c5f3-130">지정한 숫자 식의 아크탄젠트 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-130">Returns the arctangent value of the specified numeric expression.</span></span>

<span data-ttu-id="7c5f3-131">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-131">**Arguments**</span></span>

<span data-ttu-id="7c5f3-132">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-132">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-133">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-133">**Return Value**</span></span>

<span data-ttu-id="7c5f3-134">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-134">A `Double`.</span></span>

<span data-ttu-id="7c5f3-135">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-135">**Example**</span></span>

`SqlServer.ATAN(9)`

## <a name="atn2expression-expression"></a><span data-ttu-id="7c5f3-136">ATN2 (식, 식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-136">ATN2(expression, expression)</span></span>

<span data-ttu-id="7c5f3-137">탄젠트 값이 지정한 두 숫자 식 사이에 속하는 각도를 라디안으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-137">Returns the angle, in radians, whose tangent is between the two specified numeric expressions.</span></span>

<span data-ttu-id="7c5f3-138">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-138">**Arguments**</span></span>

<span data-ttu-id="7c5f3-139">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-139">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-140">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-140">**Return Value**</span></span>

<span data-ttu-id="7c5f3-141">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-141">A `Double`.</span></span>

<span data-ttu-id="7c5f3-142">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-142">**Example**</span></span>

`SqlServer.ATN2(9, 8)`

## <a name="ceilingexpression"></a><span data-ttu-id="7c5f3-143">상한 (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-143">CEILING(expression)</span></span>

<span data-ttu-id="7c5f3-144">지정한 식을 해당 식보다 크거나 같은 가장 작은 정수로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-144">Converts the specified expression to the smallest integer that is greater than or equal to it.</span></span>

<span data-ttu-id="7c5f3-145">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-145">**Arguments**</span></span>

<span data-ttu-id="7c5f3-146">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-146">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="7c5f3-147">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-147">**Return Value**</span></span>

<span data-ttu-id="7c5f3-148">`Int32`,, `Int64` `Double` 또는 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-148">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="7c5f3-149">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-149">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_ceiling)]

## <a name="cosexpression"></a><span data-ttu-id="7c5f3-150">COS (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-150">COS(expression)</span></span>

<span data-ttu-id="7c5f3-151">라디안으로 지정된 각도의 삼각 코사인을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-151">Calculates the trigonometric cosine of the specified angle in radians.</span></span>

<span data-ttu-id="7c5f3-152">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-152">**Arguments**</span></span>

<span data-ttu-id="7c5f3-153">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-153">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-154">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-154">**Return Value**</span></span>

<span data-ttu-id="7c5f3-155">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-155">A `Double`.</span></span>

<span data-ttu-id="7c5f3-156">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-156">**Example**</span></span>

`SqlServer.COS(45)`

## <a name="cotexpression"></a><span data-ttu-id="7c5f3-157">COT (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-157">COT(expression)</span></span>

<span data-ttu-id="7c5f3-158">지정된 각도의 삼각 코탄젠트를 라디안으로 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-158">Calculates the trigonometric cotangent of the specified angle in radians.</span></span>

<span data-ttu-id="7c5f3-159">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-159">**Arguments**</span></span>

<span data-ttu-id="7c5f3-160">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-160">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-161">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-161">**Return Value**</span></span>

<span data-ttu-id="7c5f3-162">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-162">A `Double`.</span></span>

<span data-ttu-id="7c5f3-163">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-163">**Example**</span></span>

`SqlServer.COT(60)`
  
## <a name="degreesradians"></a><span data-ttu-id="7c5f3-164">각도 (라디안)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-164">DEGREES(radians)</span></span>

<span data-ttu-id="7c5f3-165">해당 각도를 도 단위로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-165">Returns the corresponding angle in degrees.</span></span>

<span data-ttu-id="7c5f3-166">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-166">**Arguments**</span></span>

<span data-ttu-id="7c5f3-167">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-167">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="7c5f3-168">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-168">**Return Value**</span></span>

<span data-ttu-id="7c5f3-169">`Int32`,, `Int64` `Double` 또는 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-169">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="7c5f3-170">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-170">**Example**</span></span>

`SqlServer.DEGREES(3.1)`

## <a name="expexpression"></a><span data-ttu-id="7c5f3-171">EXP (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-171">EXP(expression)</span></span>

<span data-ttu-id="7c5f3-172">지정한 숫자 식의 지수 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-172">Calculates the exponential value of a specified numeric expression.</span></span>

<span data-ttu-id="7c5f3-173">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-173">**Arguments**</span></span>

<span data-ttu-id="7c5f3-174">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-174">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-175">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-175">**Return Value**</span></span>

<span data-ttu-id="7c5f3-176">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-176">A `Double`.</span></span>

<span data-ttu-id="7c5f3-177">**예**`SqlServer.EXP(1)`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-177">**Example** `SqlServer.EXP(1)`</span></span>

## <a name="floorexpression"></a><span data-ttu-id="7c5f3-178">FLOOR (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-178">FLOOR(expression)</span></span>

<span data-ttu-id="7c5f3-179">지정한 식을 해당 식보다 작거나 같은 가장 큰 정수로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-179">Converts the specified expression to the largest integer less than or equal to it.</span></span>

<span data-ttu-id="7c5f3-180">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-180">**Arguments**</span></span>

<span data-ttu-id="7c5f3-181">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-181">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-182">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-182">**Return Value**</span></span>

<span data-ttu-id="7c5f3-183">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-183">A `Double`.</span></span>

<span data-ttu-id="7c5f3-184">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-184">**Example**</span></span>

[!code-sql[DP EntityServices Concepts#SQLSERVER_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#sqlserver_floor)]

## <a name="logexpression"></a><span data-ttu-id="7c5f3-185">LOG (expression)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-185">LOG(expression)</span></span>

<span data-ttu-id="7c5f3-186">지정한 `float` 식의 자연 로그를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-186">Calculates the natural logarithm of the specified `float` expression.</span></span>

<span data-ttu-id="7c5f3-187">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-187">**Arguments**</span></span>

<span data-ttu-id="7c5f3-188">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-188">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-189">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-189">**Return Value**</span></span>

<span data-ttu-id="7c5f3-190">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-190">A `Double`.</span></span>

<span data-ttu-id="7c5f3-191">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-191">**Example**</span></span>

`SqlServer.LOG(100)`

## <a name="log10expression"></a><span data-ttu-id="7c5f3-192">LOG10 (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-192">LOG10(expression)</span></span>

<span data-ttu-id="7c5f3-193">지정한 `Double` 식의 상용 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-193">Returns the base-10 logarithm of the specified `Double` expression.</span></span>

<span data-ttu-id="7c5f3-194">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-194">**Arguments**</span></span>

<span data-ttu-id="7c5f3-195">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-195">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-196">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-196">**Return Value**</span></span>

<span data-ttu-id="7c5f3-197">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-197">A `Double`.</span></span>

<span data-ttu-id="7c5f3-198">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-198">**Example**</span></span>

`SqlServer.LOG10(100)`

## <a name="pi"></a><span data-ttu-id="7c5f3-199">PI ()</span><span class="sxs-lookup"><span data-stu-id="7c5f3-199">PI()</span></span>

<span data-ttu-id="7c5f3-200">파이의 상수 값을 `Double`로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-200">Returns the constant value of pi as a `Double`.</span></span>

<span data-ttu-id="7c5f3-201">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-201">**Return Value**</span></span>

<span data-ttu-id="7c5f3-202">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-202">A `Double`.</span></span>

<span data-ttu-id="7c5f3-203">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-203">**Example**</span></span>

`SqlServer.PI()`

## <a name="powernumeric_expression-power_expression"></a><span data-ttu-id="7c5f3-204">전원 (numeric_expression, power_expression)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-204">POWER(numeric_expression, power_expression)</span></span>

<span data-ttu-id="7c5f3-205">지정한 숫자 식의 지정된 거듭제곱 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-205">Calculates the value of a specified expression to a specified power.</span></span>

<span data-ttu-id="7c5f3-206">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-206">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="7c5f3-207">`Int32`,, `Int64` `Double` 또는 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-207">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>|
|`power_expression`| <span data-ttu-id="7c5f3-208">`Double`에 대해 계산할 거듭제곱을 나타내는 `numeric_expression`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-208">A `Double` that represents the power to which to raise the `numeric_expression`.</span></span>|

<span data-ttu-id="7c5f3-209">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-209">**Return Value**</span></span>

<span data-ttu-id="7c5f3-210">지정한 `numeric_expression`에 지정한 `power_expression`을 거듭제곱한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-210">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="7c5f3-211">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-211">**Example**</span></span>

`SqlServer.POWER(2,7)`

## <a name="radiansexpression"></a><span data-ttu-id="7c5f3-212">라디안 (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-212">RADIANS(expression)</span></span>

<span data-ttu-id="7c5f3-213">도를 라디안으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-213">Converts degrees to radians.</span></span>

<span data-ttu-id="7c5f3-214">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-214">**Arguments**</span></span>

<span data-ttu-id="7c5f3-215">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-215">`expression`: An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="7c5f3-216">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-216">**Return Value**</span></span>

<span data-ttu-id="7c5f3-217">`Int32`,, `Int64` `Double` 또는 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-217">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="7c5f3-218">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-218">**Example**</span></span>

`SqlServer.RADIANS(360.0)`

## <a name="randseed"></a><span data-ttu-id="7c5f3-219">RAND ([초기값])</span><span class="sxs-lookup"><span data-stu-id="7c5f3-219">RAND([seed])</span></span>

<span data-ttu-id="7c5f3-220">0에서 1 사이의 임의 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-220">Returns a random value from 0 through 1.</span></span>

<span data-ttu-id="7c5f3-221">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-221">**Arguments**</span></span>

<span data-ttu-id="7c5f3-222">의 초기값 `Int32` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-222">The seed value as an `Int32`.</span></span> <span data-ttu-id="7c5f3-223">시드를 지정하지 않으면 SQL Server 데이터베이스 엔진에서 시드 값을 임의로 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-223">If the seed is not specified, the SQL Server Database Engine assigns a seed value at random.</span></span> <span data-ttu-id="7c5f3-224">지정된 초기값에 대해 반환된 결과는 항상 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-224">For a specified seed value, the result returned is always the same.</span></span>

<span data-ttu-id="7c5f3-225">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-225">**Return Value**</span></span>

<span data-ttu-id="7c5f3-226">0에서 1 사이의 임의 `Double` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-226">A random `Double` value from 0 through 1.</span></span>

<span data-ttu-id="7c5f3-227">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-227">**Example**</span></span>

`SqlServer.RAND()`
  
## <a name="roundnumeric_expression-lengthfunction"></a><span data-ttu-id="7c5f3-228">ROUND (numeric_expression, length [, function])</span><span class="sxs-lookup"><span data-stu-id="7c5f3-228">ROUND(numeric_expression, length[,function])</span></span>

<span data-ttu-id="7c5f3-229">숫자 식을 지정한 길이나 전체 자릿수로 반올림하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-229">Returns a numeric expression, rounded to the specified length or precision.</span></span>

<span data-ttu-id="7c5f3-230">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-230">**Arguments**</span></span>

|  |  |
|--|--|
|`numeric_expression`| <span data-ttu-id="7c5f3-231">`Int32`,, `Int64` `Double` 또는 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-231">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>
|`length`| <span data-ttu-id="7c5f3-232">`Int32`을 반올림할 전체 자릿수를 나타내는 `numeric_expression`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-232">An `Int32` that represents the precision to which `numeric_expression` is to be rounded.</span></span> <span data-ttu-id="7c5f3-233">`length`가 양수일 경우 `numeric_expression`은 `length`에서 지정한 소수 자릿수로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-233">When `length` is a positive number, `numeric_expression` is rounded to the number of decimal positions specified by `length`.</span></span> <span data-ttu-id="7c5f3-234">`length`가 음수일 경우 `numeric_expression`은 `length`에서 지정한 대로 소수점의 왼쪽에서 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-234">When `length` is a negative number, `numeric_expression` is rounded on the left side of the decimal point, as specified by `length`.</span></span>|
|`function` | <span data-ttu-id="7c5f3-235">선택 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-235">Optional.</span></span> <span data-ttu-id="7c5f3-236">`Int32`수행할 작업의 유형을 나타내는입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-236">An `Int32` that represents the type of operation to perform.</span></span> <span data-ttu-id="7c5f3-237">함수를 생략 하거나 값이 0 (기본값) 인 경우 `numeric_expression` 는 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-237">When function is omitted or has a value of 0 (default), `numeric_expression` is rounded.</span></span> <span data-ttu-id="7c5f3-238">0이 아닌 값을 지정 하면 `numeric_expression` 이 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-238">When a value other than 0 is specified, `numeric_expression` is truncated.</span></span> |

<span data-ttu-id="7c5f3-239">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-239">**Return Value**</span></span>

<span data-ttu-id="7c5f3-240">지정한 `numeric_expression`에 지정한 `power_expression`을 거듭제곱한 값입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-240">The value of the specified `numeric_expression` to the specified `power_expression`.</span></span>

<span data-ttu-id="7c5f3-241">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-241">**Example**</span></span>

`SqlServer.ROUND(748.58, -3)`

## <a name="signexpression"></a><span data-ttu-id="7c5f3-242">SIGN (expression)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-242">SIGN(expression)</span></span>

<span data-ttu-id="7c5f3-243">지정된 식의 양수(+1), 영(0) 또는 음수(-1) 기호를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-243">Returns the positive (+1), zero (0), or negative (-1) sign of the specified expression.</span></span>

<span data-ttu-id="7c5f3-244">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-244">**Arguments**</span></span>

<span data-ttu-id="7c5f3-245">`expression`: `Int32`, `Int64`, `Double` 또는 `Decimal`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-245">`expression`: `Int32`, `Int64`, `Double`, or `Decimal`</span></span>

<span data-ttu-id="7c5f3-246">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-246">**Return Value**</span></span>

<span data-ttu-id="7c5f3-247">`Int32`,, `Int64` `Double` 또는 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-247">An `Int32`, `Int64`, `Double`, or `Decimal`.</span></span>

<span data-ttu-id="7c5f3-248">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-248">**Example**</span></span>

`SqlServer.SIGN(-10)`

## <a name="sinexpression"></a><span data-ttu-id="7c5f3-249">SIN (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-249">SIN(expression)</span></span>

<span data-ttu-id="7c5f3-250">라디안으로 지정한 각도의 삼각 사인을 계산하여 `Double` 식을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-250">Calculates the trigonometric sine of the specified angle in radians, and returns a `Double` expression.</span></span>

<span data-ttu-id="7c5f3-251">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-251">**Arguments**</span></span>

<span data-ttu-id="7c5f3-252">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-252">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-253">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-253">**Return Value**</span></span>

<span data-ttu-id="7c5f3-254">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-254">A `Double`.</span></span>

<span data-ttu-id="7c5f3-255">**예**`SqlServer.SIN(20)`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-255">**Example** `SqlServer.SIN(20)`</span></span>

## <a name="sqrtexpression"></a><span data-ttu-id="7c5f3-256">SQRT (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-256">SQRT(expression)</span></span>

<span data-ttu-id="7c5f3-257">지정한 식의 제곱근을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-257">Returns the square root of the specified expression.</span></span>

<span data-ttu-id="7c5f3-258">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-258">**Arguments**</span></span>

<span data-ttu-id="7c5f3-259">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-259">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-260">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-260">**Return Value**</span></span>

<span data-ttu-id="7c5f3-261">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-261">A `Double`.</span></span>

<span data-ttu-id="7c5f3-262">**예**`SqlServer.SQRT(3600)`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-262">**Example** `SqlServer.SQRT(3600)`</span></span>

## <a name="squareexpression"></a><span data-ttu-id="7c5f3-263">SQUARE (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-263">SQUARE(expression)</span></span>

<span data-ttu-id="7c5f3-264">지정한 식의 제곱을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-264">Returns the square of the specified expression.</span></span>

<span data-ttu-id="7c5f3-265">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-265">**Arguments**</span></span>

<span data-ttu-id="7c5f3-266">`expression`: `Double`입니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-266">`expression`: A `Double`.</span></span>

<span data-ttu-id="7c5f3-267">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-267">**Return Value**</span></span>

<span data-ttu-id="7c5f3-268">`Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-268">A `Double`.</span></span>

<span data-ttu-id="7c5f3-269">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-269">**Example**</span></span>

`SqlServer.SQUARE(25)`

## <a name="tanexpression"></a><span data-ttu-id="7c5f3-270">황갈색 (식)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-270">TAN(expression)</span></span>

<span data-ttu-id="7c5f3-271">지정한 식의 탄젠트를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7c5f3-271">Calculates the tangent of a specified expression.</span></span>

<span data-ttu-id="7c5f3-272">**인수**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-272">**Arguments**</span></span>

<span data-ttu-id="7c5f3-273">`expression`: `Double`</span><span class="sxs-lookup"><span data-stu-id="7c5f3-273">`expression`: `Double`</span></span>

<span data-ttu-id="7c5f3-274">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-274">**Return Value**</span></span>

`Double`

<span data-ttu-id="7c5f3-275">**예제**</span><span class="sxs-lookup"><span data-stu-id="7c5f3-275">**Example**</span></span>

`SqlServer.TAN(45.0)`
  
## <a name="see-also"></a><span data-ttu-id="7c5f3-276">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7c5f3-276">See also</span></span>

- [<span data-ttu-id="7c5f3-277">수치 연산 함수(Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="7c5f3-277">Mathematical Functions (Transact-SQL)</span></span>](/sql/t-sql/functions/mathematical-functions-transact-sql)
- [<span data-ttu-id="7c5f3-278">Entity Framework용 SqlClient 기능</span><span class="sxs-lookup"><span data-stu-id="7c5f3-278">SqlClient for Entity Framework Functions</span></span>](sqlclient-for-ef-functions.md)
