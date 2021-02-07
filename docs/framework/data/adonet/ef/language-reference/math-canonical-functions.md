---
description: '자세한 정보: 수학 정식 함수'
title: 수학 정식 함수
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: 55072099f5766d48ea3067a2e9eaa187a8b3f111
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99739367"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="b6a6f-103">수학 정식 함수</span><span class="sxs-lookup"><span data-stu-id="b6a6f-103">Math Canonical Functions</span></span>

<span data-ttu-id="b6a6f-104">Entity SQL는 다음과 같은 수학 정식 함수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-104">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="b6a6f-105">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="b6a6f-105">Abs(value)</span></span>

<span data-ttu-id="b6a6f-106">`value`의 절대값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-106">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="b6a6f-107">**인수**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-107">**Arguments**</span></span>

<span data-ttu-id="b6a6f-108">,,,,, `Int16` `Int32` `Int64` `Byte` `Single` `Double` 및 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-108">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b6a6f-109">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-109">**Return Value**</span></span>

<span data-ttu-id="b6a6f-110">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-110">The type of `value`.</span></span>

<span data-ttu-id="b6a6f-111">**예제**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-111">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="b6a6f-112">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="b6a6f-112">Ceiling(value)</span></span>

<span data-ttu-id="b6a6f-113">`value`보다 작지 않은 가장 작은 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-113">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="b6a6f-114">**인수**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-114">**Arguments**</span></span>

<span data-ttu-id="b6a6f-115">`Single`, `Double` 및 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-115">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b6a6f-116">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-116">**Return Value**</span></span>

<span data-ttu-id="b6a6f-117">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-117">The type of `value`.</span></span>

<span data-ttu-id="b6a6f-118">**예제**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-118">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="b6a6f-119">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="b6a6f-119">Floor(value)</span></span>

<span data-ttu-id="b6a6f-120">`value`보다 크지 않은 가장 큰 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-120">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="b6a6f-121">**인수**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-121">**Arguments**</span></span>

<span data-ttu-id="b6a6f-122">`Single`, `Double` 및 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-122">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b6a6f-123">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-123">**Return Value**</span></span>

<span data-ttu-id="b6a6f-124">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-124">The type of `value`.</span></span>

<span data-ttu-id="b6a6f-125">**예제**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-125">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="b6a6f-126">Power(value, exponent)</span><span class="sxs-lookup"><span data-stu-id="b6a6f-126">Power(value, exponent)</span></span>

<span data-ttu-id="b6a6f-127">지정된 `value`에 대해 지정된 `exponent`의 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-127">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="b6a6f-128">**인수**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-128">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="b6a6f-129">`Int32, Int64, Double` 또는 `Decimal`입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-129">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="b6a6f-130">`Int64`, `Double` 또는 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-130">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="b6a6f-131">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-131">**Return Value**</span></span>

<span data-ttu-id="b6a6f-132">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-132">The type of `value`.</span></span>

<span data-ttu-id="b6a6f-133">**예제**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-133">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="b6a6f-134">Round(value)</span><span class="sxs-lookup"><span data-stu-id="b6a6f-134">Round(value)</span></span>

<span data-ttu-id="b6a6f-135">`value`의 정수 부분을 가장 가까운 정수로 반올림하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-135">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="b6a6f-136">**인수**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-136">**Arguments**</span></span>

<span data-ttu-id="b6a6f-137">`Single`, `Double` 및 `Decimal` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-137">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="b6a6f-138">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-138">**Return Value**</span></span>

<span data-ttu-id="b6a6f-139">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-139">The type of `value`.</span></span>

<span data-ttu-id="b6a6f-140">**예제**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-140">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="b6a6f-141">Round(value, digits)</span><span class="sxs-lookup"><span data-stu-id="b6a6f-141">Round(value, digits)</span></span>

<span data-ttu-id="b6a6f-142">`value`를 지정된 `digits` 중 가장 가까운 숫자로 반올림하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-142">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="b6a6f-143">**인수**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-143">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="b6a6f-144">`Double` 또는 `Decimal`</span><span class="sxs-lookup"><span data-stu-id="b6a6f-144">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="b6a6f-145">`Int16` 또는 `Int32`</span><span class="sxs-lookup"><span data-stu-id="b6a6f-145">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="b6a6f-146">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-146">**Return Value**</span></span>

<span data-ttu-id="b6a6f-147">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-147">The type of `value`.</span></span>

<span data-ttu-id="b6a6f-148">**예제**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-148">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="b6a6f-149">Truncate(value, digits)</span><span class="sxs-lookup"><span data-stu-id="b6a6f-149">Truncate(value, digits)</span></span>

<span data-ttu-id="b6a6f-150">`value`를 지정된 `digits` 중 가장 가까운 숫자로 잘라 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-150">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="b6a6f-151">**인수**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-151">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="b6a6f-152">`Double` 또는 `Decimal`</span><span class="sxs-lookup"><span data-stu-id="b6a6f-152">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="b6a6f-153">`Int16` 또는 `Int32`</span><span class="sxs-lookup"><span data-stu-id="b6a6f-153">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="b6a6f-154">**Return Value**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-154">**Return Value**</span></span>

<span data-ttu-id="b6a6f-155">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-155">The type of `value`.</span></span>

<span data-ttu-id="b6a6f-156">**예제**</span><span class="sxs-lookup"><span data-stu-id="b6a6f-156">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="b6a6f-157">이러한 함수는 `null`이 입력되면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-157">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="b6a6f-158">동일한 기능을 Microsoft SQL 클라이언트 관리 공급자에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-158">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="b6a6f-159">자세한 내용은 [Entity Framework 함수에 대 한 SqlClient](../sqlclient-for-ef-functions.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6a6f-159">For more information, see [SqlClient for Entity Framework Functions](../sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6a6f-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b6a6f-160">See also</span></span>

- [<span data-ttu-id="b6a6f-161">정식 함수</span><span class="sxs-lookup"><span data-stu-id="b6a6f-161">Canonical Functions</span></span>](canonical-functions.md)
