---
title: 수학 정식 함수
ms.date: 03/30/2017
ms.assetid: 6f6cddc6-b561-4ebe-84b6-841ef5b4113b
ms.openlocfilehash: f575785bb198251ef50ba3563e736946253c9526
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61760638"
---
# <a name="math-canonical-functions"></a><span data-ttu-id="94c3f-102">수학 정식 함수</span><span class="sxs-lookup"><span data-stu-id="94c3f-102">Math Canonical Functions</span></span>

<span data-ttu-id="94c3f-103">Entity SQL 수학 정식 함수를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-103">Entity SQL includes the following math canonical functions:</span></span>
  
## <a name="absvalue"></a><span data-ttu-id="94c3f-104">Abs(value)</span><span class="sxs-lookup"><span data-stu-id="94c3f-104">Abs(value)</span></span>

<span data-ttu-id="94c3f-105">`value`의 절대값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-105">Returns the absolute value of `value`.</span></span>

<span data-ttu-id="94c3f-106">**인수**</span><span class="sxs-lookup"><span data-stu-id="94c3f-106">**Arguments**</span></span>

<span data-ttu-id="94c3f-107">`Int16`, `Int32`를 `Int64`, `Byte`를 `Single`를 `Double`, 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-107">An `Int16`, `Int32`, `Int64`, `Byte`, `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="94c3f-108">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="94c3f-108">**Return Value**</span></span>

<span data-ttu-id="94c3f-109">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-109">The type of `value`.</span></span>

<span data-ttu-id="94c3f-110">**예제**</span><span class="sxs-lookup"><span data-stu-id="94c3f-110">**Example**</span></span>

`Abs(-2)`

## <a name="ceilingvalue"></a><span data-ttu-id="94c3f-111">Ceiling(value)</span><span class="sxs-lookup"><span data-stu-id="94c3f-111">Ceiling(value)</span></span>

<span data-ttu-id="94c3f-112">`value`보다 작지 않은 가장 작은 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-112">Returns the smallest integer that is not less than `value`.</span></span>

<span data-ttu-id="94c3f-113">**인수**</span><span class="sxs-lookup"><span data-stu-id="94c3f-113">**Arguments**</span></span>

<span data-ttu-id="94c3f-114">A `Single`, `Double`, 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-114">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="94c3f-115">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="94c3f-115">**Return Value**</span></span>

<span data-ttu-id="94c3f-116">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-116">The type of `value`.</span></span>

<span data-ttu-id="94c3f-117">**예제**</span><span class="sxs-lookup"><span data-stu-id="94c3f-117">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_ceiling)]
[!code-sql[DP EntityServices Concepts#EDM_CEILING](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_ceiling)]

## <a name="floorvalue"></a><span data-ttu-id="94c3f-118">Floor(value)</span><span class="sxs-lookup"><span data-stu-id="94c3f-118">Floor(value)</span></span>

<span data-ttu-id="94c3f-119">`value`보다 크지 않은 가장 큰 정수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-119">Returns the largest integer that is not greater than `value`.</span></span>

<span data-ttu-id="94c3f-120">**인수**</span><span class="sxs-lookup"><span data-stu-id="94c3f-120">**Arguments**</span></span>

<span data-ttu-id="94c3f-121">A `Single`, `Double`, 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-121">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="94c3f-122">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="94c3f-122">**Return Value**</span></span>

<span data-ttu-id="94c3f-123">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-123">The type of `value`.</span></span>

<span data-ttu-id="94c3f-124">**예제**</span><span class="sxs-lookup"><span data-stu-id="94c3f-124">**Example**</span></span>

[!code-csharp[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/csharp/VS_Snippets_Data/dp entityservices concepts/cs/entitysql.cs#edm_floor)]
[!code-sql[DP EntityServices Concepts#EDM_FLOOR](~/samples/snippets/tsql/VS_Snippets_Data/dp entityservices concepts/tsql/entitysql.sql#edm_floor)]

## <a name="powervalue-exponent"></a><span data-ttu-id="94c3f-125">Power(value, exponent)</span><span class="sxs-lookup"><span data-stu-id="94c3f-125">Power(value, exponent)</span></span>

<span data-ttu-id="94c3f-126">지정된 `value`에 대해 지정된 `exponent`의 결과를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-126">Returns the result of the specified `value` to the specified `exponent`.</span></span>

<span data-ttu-id="94c3f-127">**인수**</span><span class="sxs-lookup"><span data-stu-id="94c3f-127">**Arguments**</span></span>

|  |  |
|--|--|
|`value` | <span data-ttu-id="94c3f-128">`Int32, Int64, Double`, 또는 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-128">An `Int32, Int64, Double`, or `Decimal`.</span></span> |
|`exponent` | <span data-ttu-id="94c3f-129">`Int64`하십시오 `Double`, 또는 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-129">An `Int64`, `Double`, or `Decimal`.</span></span> |

<span data-ttu-id="94c3f-130">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="94c3f-130">**Return Value**</span></span>

<span data-ttu-id="94c3f-131">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-131">The type of `value`.</span></span>

<span data-ttu-id="94c3f-132">**예제**</span><span class="sxs-lookup"><span data-stu-id="94c3f-132">**Example**</span></span>

`Power(748.58,2)`

## <a name="roundvalue"></a><span data-ttu-id="94c3f-133">Round(value)</span><span class="sxs-lookup"><span data-stu-id="94c3f-133">Round(value)</span></span>

<span data-ttu-id="94c3f-134">`value`의 정수 부분을 가장 가까운 정수로 반올림하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-134">Returns the integer portion of `value`, rounded to the nearest integer.</span></span>

<span data-ttu-id="94c3f-135">**인수**</span><span class="sxs-lookup"><span data-stu-id="94c3f-135">**Arguments**</span></span>

<span data-ttu-id="94c3f-136">A `Single`, `Double`, 및 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-136">A `Single`, `Double`, and `Decimal`.</span></span>

<span data-ttu-id="94c3f-137">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="94c3f-137">**Return Value**</span></span>

<span data-ttu-id="94c3f-138">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-138">The type of `value`.</span></span>

<span data-ttu-id="94c3f-139">**예제**</span><span class="sxs-lookup"><span data-stu-id="94c3f-139">**Example**</span></span>

`Round(748.58)`

## <a name="roundvalue-digits"></a><span data-ttu-id="94c3f-140">Round(value, digits)</span><span class="sxs-lookup"><span data-stu-id="94c3f-140">Round(value, digits)</span></span>

<span data-ttu-id="94c3f-141">`value`를 지정된 `digits` 중 가장 가까운 숫자로 반올림하여 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-141">Returns the `value`, rounded to the nearest specified `digits`.</span></span>

<span data-ttu-id="94c3f-142">**인수**</span><span class="sxs-lookup"><span data-stu-id="94c3f-142">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="94c3f-143">`Double` 또는 `Decimal`</span><span class="sxs-lookup"><span data-stu-id="94c3f-143">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="94c3f-144">`Int16` 또는 `Int32`</span><span class="sxs-lookup"><span data-stu-id="94c3f-144">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="94c3f-145">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="94c3f-145">**Return Value**</span></span>

<span data-ttu-id="94c3f-146">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-146">The type of `value`.</span></span>

<span data-ttu-id="94c3f-147">**예제**</span><span class="sxs-lookup"><span data-stu-id="94c3f-147">**Example**</span></span>

`Round(748.58,1)`

## <a name="truncatevalue-digits"></a><span data-ttu-id="94c3f-148">Truncate(value, digits)</span><span class="sxs-lookup"><span data-stu-id="94c3f-148">Truncate(value, digits)</span></span>

<span data-ttu-id="94c3f-149">`value`를 지정된 `digits` 중 가장 가까운 숫자로 잘라 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-149">Returns the `value`, truncated to the nearest specified `digits`.</span></span>

<span data-ttu-id="94c3f-150">**인수**</span><span class="sxs-lookup"><span data-stu-id="94c3f-150">**Arguments**</span></span>

|  |  |
|--|--|
|`value`|<span data-ttu-id="94c3f-151">`Double` 또는 `Decimal`</span><span class="sxs-lookup"><span data-stu-id="94c3f-151">`Double` or `Decimal`.</span></span>|
|`digits`|<span data-ttu-id="94c3f-152">`Int16` 또는 `Int32`</span><span class="sxs-lookup"><span data-stu-id="94c3f-152">`Int16` or `Int32`.</span></span>|

<span data-ttu-id="94c3f-153">**반환 값**</span><span class="sxs-lookup"><span data-stu-id="94c3f-153">**Return Value**</span></span>

<span data-ttu-id="94c3f-154">`value`의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-154">The type of `value`.</span></span>

<span data-ttu-id="94c3f-155">**예제**</span><span class="sxs-lookup"><span data-stu-id="94c3f-155">**Example**</span></span>

`Truncate(748.58,1)`  
  
 <span data-ttu-id="94c3f-156">이러한 함수는 `null`이 입력되면 `null`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-156">These functions will return `null` if given `null` input.</span></span>  
  
 <span data-ttu-id="94c3f-157">동일한 기능을 Microsoft SQL 클라이언트 관리 공급자에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-157">Equivalent functionality is available in the Microsoft SQL Client Managed Provider.</span></span> <span data-ttu-id="94c3f-158">자세한 내용은 [Entity Framework 함수에 대 한 SqlClient](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="94c3f-158">For more information, see [SqlClient for Entity Framework Functions](../../../../../../docs/framework/data/adonet/ef/sqlclient-for-ef-functions.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94c3f-159">참고자료</span><span class="sxs-lookup"><span data-stu-id="94c3f-159">See also</span></span>

- [<span data-ttu-id="94c3f-160">정식 함수</span><span class="sxs-lookup"><span data-stu-id="94c3f-160">Canonical Functions</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/canonical-functions.md)
