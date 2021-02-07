---
description: '자세한 정보: 형식 변환 함수 (Visual Basic)'
title: 형식 변환 함수
ms.date: 10/24/2018
f1_keywords:
- vb.CUShort
- vb.csng
- vb.CDate
- CByte
- CSng
- vb.CDec
- CBool
- CStr
- vb.CULng
- CDec
- CVErr
- CDbl
- CShort
- vb.CObj
- vb.CVErr
- CULng
- vb.cdbl
- vb.cbool
- CObj
- CDate
- CLng
- vb.cstr
- vb.cbyte
- vb.clng
- vb.CChar
- CUShort
- vb.CUInt
- vb.cint
- vb.CShort
- CInt
- CUInt
- CChar
helpviewer_keywords:
- CDate function
- CByte function
- Integer data type [Visual Basic], converting
- string conversion [Visual Basic], conversion functions
- fractions
- data types [Visual Basic], converting
- text, converting
- CDec function
- Char data type [Visual Basic], converting
- type conversion [Visual Basic], functions for
- Single data type [Visual Basic], converting
- numbers [Visual Basic], rounding
- rounding numbers [Visual Basic], type conversion
- CUShort function
- Long data type [Visual Basic], converting
- return values [Visual Basic], data types
- single-precision numbers [Visual Basic], converting
- data type conversion [Visual Basic], functions for
- CStr function
- times [Visual Basic], converting
- CSng function
- conversions [Visual Basic], type conversion functions
- CBool function
- CDbl function
- CUInt function
- Currency data type [Visual Basic], conversion functions
- numbers [Visual Basic], converting
- Double data type [Visual Basic], converting
- CLng function
- CSByte function
- double-precision numbers
- Decimal data type [Visual Basic], converting
- Boolean data type [Visual Basic], converting
- integers [Visual Basic], type conversion functions
- dates [Visual Basic], converting
- CULng function
- CInt function
- Date data type [Visual Basic], converting
- Byte data type [Visual Basic], converting
- String data type [Visual Basic], converting
- CChar function
- banker's rounding
- Short data type [Visual Basic], converting
- rounding numbers [Visual Basic], banker's rounding
- type conversion [Visual Basic], Visual Basic vs. .NET Framework
ms.assetid: d9d8d165-f967-44ff-a6cd-598e4740a99e
ms.openlocfilehash: c2e701b522bbeb32f4f6f448acd78e09b0616f46
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99731086"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="3f9f0-103">형식 변환 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3f9f0-103">Type Conversion Functions (Visual Basic)</span></span>

<span data-ttu-id="3f9f0-104">이러한 함수는 인라인으로 컴파일됩니다. 즉, 변환 코드는 식을 계산 하는 코드의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-104">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="3f9f0-105">변환을 수행 하는 프로시저에 대 한 호출이 없을 수도 있으므로 성능이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-105">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="3f9f0-106">각 함수는 식을 특정 데이터 형식으로 강제 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-106">Each function coerces an expression to a specific data type.</span></span>

## <a name="syntax"></a><span data-ttu-id="3f9f0-107">Syntax</span><span class="sxs-lookup"><span data-stu-id="3f9f0-107">Syntax</span></span>

```vb
CBool(expression)
CByte(expression)
CChar(expression)
CDate(expression)
CDbl(expression)
CDec(expression)
CInt(expression)
CLng(expression)
CObj(expression)
CSByte(expression)
CShort(expression)
CSng(expression)
CStr(expression)
CUInt(expression)
CULng(expression)
CUShort(expression)
```

## <a name="part"></a><span data-ttu-id="3f9f0-108">파트</span><span class="sxs-lookup"><span data-stu-id="3f9f0-108">Part</span></span>

`expression`  
<span data-ttu-id="3f9f0-109">필수 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-109">Required.</span></span> <span data-ttu-id="3f9f0-110">원본 데이터 형식의 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-110">Any expression of the source data type.</span></span>

## <a name="return-value-data-type"></a><span data-ttu-id="3f9f0-111">반환 값 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-111">Return Value Data Type</span></span>

<span data-ttu-id="3f9f0-112">함수 이름은 다음 표에 나와 있는 것 처럼 반환 되는 값의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-112">The function name determines the data type of the value it returns, as shown in the following table.</span></span>

|<span data-ttu-id="3f9f0-113">함수 이름</span><span class="sxs-lookup"><span data-stu-id="3f9f0-113">Function name</span></span>|<span data-ttu-id="3f9f0-114">반환 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-114">Return data type</span></span>|<span data-ttu-id="3f9f0-115">인수의 범위 `expression`</span><span class="sxs-lookup"><span data-stu-id="3f9f0-115">Range for `expression` argument</span></span>|
|-------------------|----------------------|-------------------------------------|
|`CBool`|[<span data-ttu-id="3f9f0-116">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-116">Boolean Data Type</span></span>](../data-types/boolean-data-type.md)|<span data-ttu-id="3f9f0-117">모든 유효한 `Char` `String` 식 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-117">Any valid `Char` or `String` or numeric expression.</span></span>|
|`CByte`|[<span data-ttu-id="3f9f0-118">Byte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-118">Byte Data Type</span></span>](../data-types/byte-data-type.md)|<span data-ttu-id="3f9f0-119"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) ~ <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (부호 없음). 소수 부분을 반올림 합니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="3f9f0-119"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="3f9f0-120">Visual Basic 15.8부터 Visual Basic 함수를 사용 하 여 부동 소수점에서 바이트 변환의 성능을 최적화 합니다 `CByte` . 자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-120">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="3f9f0-121">예는 [CInt 예제](#cint-example) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-121">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CChar`|[<span data-ttu-id="3f9f0-122">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-122">Char Data Type</span></span>](../data-types/char-data-type.md)|<span data-ttu-id="3f9f0-123">모든 유효한 `Char` 또는 `String` 식입니다 .의 첫 번째 문자만 `String` 변환 됩니다. 값은 0에서 65535 (부호 없음) 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-123">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|
|`CDate`|[<span data-ttu-id="3f9f0-124">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-124">Date Data Type</span></span>](../data-types/date-data-type.md)|<span data-ttu-id="3f9f0-125">날짜 및 시간에 대 한 유효한 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-125">Any valid representation of a date and time.</span></span>|
|`CDbl`|[<span data-ttu-id="3f9f0-126">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-126">Double Data Type</span></span>](../data-types/double-data-type.md)|<span data-ttu-id="3f9f0-127">-1.79769313486231570 e + 308 ~-4.94065645841246544 E-324 (음수 값의 경우) 4.94065645841246544 e-324 ~ 1.79769313486231570 E + 308 (양수 값)</span><span class="sxs-lookup"><span data-stu-id="3f9f0-127">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|
|`CDec`|[<span data-ttu-id="3f9f0-128">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-128">Decimal Data Type</span></span>](../data-types/decimal-data-type.md)|<span data-ttu-id="3f9f0-129">0으로 크기가 조정 된 숫자, 즉 소수 자릿수가 없는 숫자의 경우 +/-79228162514264337593543950335입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-129">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="3f9f0-130">28 자리의 소수 자릿수가 포함 된 숫자의 경우 범위는 +/-7.9228162514264337593543950335입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-130">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="3f9f0-131">0이 아닌 가장 작은 숫자는 0.0000000000000000000000000001 (+/-1E-28)입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-131">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|
|`CInt`|[<span data-ttu-id="3f9f0-132">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-132">Integer Data Type</span></span>](../data-types/integer-data-type.md)|<span data-ttu-id="3f9f0-133"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2147483648) ~ <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2147483647). 소수 부분은 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="3f9f0-133"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="3f9f0-134">Visual Basic 15.8부터 Visual Basic 함수를 사용 하 여 부동 소수점에서 정수로의 성능을 최적화 합니다 `CInt` . 자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-134">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="3f9f0-135">예는 [CInt 예제](#cint-example) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-135">See the [CInt Example](#cint-example) section for an example.</span></span> |
|`CLng`|[<span data-ttu-id="3f9f0-136">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-136">Long Data Type</span></span>](../data-types/long-data-type.md)|<span data-ttu-id="3f9f0-137"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9223372036854775808) ~ <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9223372036854775807); 소수 부분은 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="3f9f0-137"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="3f9f0-138">Visual Basic Visual Basic 15.8부터 함수를 사용 하 여 부동 소수점에서 64 비트 정수 변환의 성능을 최적화할 수 `CLng` 있습니다. 자세한 내용은 [설명](#remarks) 부분을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-138">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="3f9f0-139">예는 [CInt 예제](#cint-example) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-139">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CObj`|[<span data-ttu-id="3f9f0-140">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="3f9f0-140">Object Data Type</span></span>](../data-types/object-data-type.md)|<span data-ttu-id="3f9f0-141">유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-141">Any valid expression.</span></span>|
|`CSByte`|[<span data-ttu-id="3f9f0-142">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-142">SByte Data Type</span></span>](../data-types/sbyte-data-type.md)|<span data-ttu-id="3f9f0-143"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) ~ <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127). 소수 부분은 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="3f9f0-143"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="3f9f0-144">Visual Basic 15.8부터 Visual Basic 함수를 사용 하 여 부동 소수점에서 부호 있는 바이트 변환의 성능을 최적화 합니다 `CSByte` . 자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-144">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="3f9f0-145">예는 [CInt 예제](#cint-example) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-145">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CShort`|[<span data-ttu-id="3f9f0-146">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-146">Short Data Type</span></span>](../data-types/short-data-type.md)|<span data-ttu-id="3f9f0-147"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32768) ~ <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32767). 소수 부분은 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="3f9f0-147"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="3f9f0-148">Visual Basic Visual Basic 15.8부터 함수를 사용 하 여 부동 소수점에서 16 비트 정수 변환의 성능을 최적화 합니다 `CShort` . 자세한 내용은 [설명](#remarks) 부분을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-148">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="3f9f0-149">예는 [CInt 예제](#cint-example) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-149">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CSng`|[<span data-ttu-id="3f9f0-150">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-150">Single Data Type</span></span>](../data-types/single-data-type.md)|<span data-ttu-id="3f9f0-151">-3.402823 e + 38 ~-1.401298 E-45 (음수 값의 경우) 1.401298 e-45부터 3.402823 E + 38 까지의 양수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-151">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|
|`CStr`|[<span data-ttu-id="3f9f0-152">문자열 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-152">String Data Type</span></span>](../data-types/string-data-type.md)|<span data-ttu-id="3f9f0-153">에 대 한 `CStr` 는 인수에 따라를 반환 `expression` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-153">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="3f9f0-154">[CStr 함수의 반환 값을](return-values-for-the-cstr-function.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-154">See [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>|
|`CUInt`|[<span data-ttu-id="3f9f0-155">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-155">UInteger Data Type</span></span>](../data-types/uinteger-data-type.md)|<span data-ttu-id="3f9f0-156"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) ~ <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4294967295) (부호 없음). 소수 부분을 반올림 합니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="3f9f0-156"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="3f9f0-157">Visual Basic Visual Basic 15.8부터 함수를 사용 하 여 부동 소수점에서 부호 없는 정수 변환의 성능을 최적화 합니다 `CUInt` . 자세한 내용은 [설명](#remarks) 부분을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-157">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="3f9f0-158">예는 [CInt 예제](#cint-example) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-158">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CULng`|[<span data-ttu-id="3f9f0-159">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-159">ULong Data Type</span></span>](../data-types/ulong-data-type.md)|<span data-ttu-id="3f9f0-160"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) ~ <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (부호 없음). 소수 부분을 반올림 합니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="3f9f0-160"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="3f9f0-161">Visual Basic 15.8부터 Visual Basic 함수를 사용 하 여 부동 소수점에서 부호 없는 long 정수 변환의 성능을 최적화 합니다 `CULng` . 자세한 내용은 [설명](#remarks) 부분을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-161">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="3f9f0-162">예는 [CInt 예제](#cint-example) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-162">See the [CInt Example](#cint-example) section for an example.</span></span>|
|`CUShort`|[<span data-ttu-id="3f9f0-163">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="3f9f0-163">UShort Data Type</span></span>](../data-types/ushort-data-type.md)|<span data-ttu-id="3f9f0-164"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) ~ <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65535) (부호 없음). 소수 부분을 반올림 합니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="3f9f0-164"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="3f9f0-165">Visual Basic Visual Basic 15.8부터 함수를 사용 하 여 부동 소수점을 부호 없는 16 비트 정수 변환으로 최적화 합니다. `CUShort` 자세한 내용은 [설명](#remarks) 부분을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-165">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="3f9f0-166">예는 [CInt 예제](#cint-example) 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-166">See the [CInt Example](#cint-example) section for an example.</span></span>|

<span data-ttu-id="3f9f0-167"><sup>1</sup> 소수 부분에는 *은행원의 반올림* 이라고 하는 특수 한 형식의 반올림이 적용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-167"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="3f9f0-168">자세한 내용은 "주의"를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-168">See "Remarks" for more information.</span></span>

## <a name="remarks"></a><span data-ttu-id="3f9f0-169">설명</span><span class="sxs-lookup"><span data-stu-id="3f9f0-169">Remarks</span></span>

<span data-ttu-id="3f9f0-170">규칙으로, `ToString()` <xref:System.Convert> 클래스 또는 개별 형식 구조체 또는 클래스에서와 같은 .NET Framework 메서드에 기본 설정으로 Visual Basic 형식 변환 함수를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-170">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="3f9f0-171">Visual Basic 함수는 Visual Basic 코드와의 최적의 상호 작용을 위해 디자인 되었으며 소스 코드를 더 짧고 읽기 쉽게 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-171">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="3f9f0-172">또한 .NET Framework 변환 메서드는 Visual Basic 함수와 동일한 결과를 생성 하지 않습니다 (예:를로 변환 하는 경우) `Boolean` `Integer` .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-172">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="3f9f0-173">자세한 내용은 [데이터 형식 문제 해결](../../programming-guide/language-features/data-types/troubleshooting-data-types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-173">For more information, see [Troubleshooting Data Types](../../programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>

<span data-ttu-id="3f9f0-174">Visual Basic 15.8부터, <xref:System.Single> <xref:System.Double> 다음 메서드에서 반환 하는 또는 값을 정수 변환 함수 (,,,,,, `CByte` `CShort` `CInt` `CLng` `CSByte` `CUShort` `CUInt` , `CULng` ) 중 하나에 전달 하는 경우 부동 소수점-정수 변환의 성능이 최적화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-174">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Fix(System.Single)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Double)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Object)?displayProperty=nameWithType>
- <xref:Microsoft.VisualBasic.Conversion.Int(System.Single)?displayProperty=nameWithType>
- <xref:System.Math.Ceiling(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Floor(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Round(System.Double)?displayProperty=nameWithType>
- <xref:System.Math.Truncate(System.Double)?displayProperty=nameWithType>

<span data-ttu-id="3f9f0-175">이러한 최적화를 통해 많은 수의 정수 변환을 수행 하는 코드를 신속 하 게 2 배까지 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-175">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="3f9f0-176">다음 예제에서는 이러한 최적화 된 부동 소수점-정수 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-176">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="3f9f0-177">동작</span><span class="sxs-lookup"><span data-stu-id="3f9f0-177">Behavior</span></span>

- <span data-ttu-id="3f9f0-178">**형.**</span><span class="sxs-lookup"><span data-stu-id="3f9f0-178">**Coercion.**</span></span> <span data-ttu-id="3f9f0-179">일반적으로 데이터 형식 변환 함수를 사용 하 여 작업 결과를 기본 데이터 형식이 아닌 특정 데이터 형식으로 강제 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-179">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="3f9f0-180">예를 들어,를 사용 `CDec` 하 여 단일 전체 자릿수, 배정밀도 또는 정수 연산이 일반적으로 발생 하는 경우 decimal 산술 연산을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-180">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>

- <span data-ttu-id="3f9f0-181">**변환에 실패 했습니다.**</span><span class="sxs-lookup"><span data-stu-id="3f9f0-181">**Failed Conversions.**</span></span> <span data-ttu-id="3f9f0-182">`expression`함수로 전달 된이 변환 될 데이터 형식의 범위를 벗어나면이 <xref:System.OverflowException> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-182">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>

- <span data-ttu-id="3f9f0-183">**소수 부분.**</span><span class="sxs-lookup"><span data-stu-id="3f9f0-183">**Fractional Parts.**</span></span> <span data-ttu-id="3f9f0-184">비정 수 값을 정수 계열 형식으로 변환 하는 경우 정수 변환 함수 ( `CByte` , `CInt` , `CLng` , `CSByte` ,,, `CShort` `CUInt` `CULng` 및 `CUShort` )는 소수 부분을 제거 하 고 값을 가장 가까운 정수로 반올림 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-184">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>

     <span data-ttu-id="3f9f0-185">소수 부분이 정확히 0.5 인 경우 정수 변환 함수는 해당 정수를 가장 가까운 짝수로 반올림 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-185">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="3f9f0-186">예를 들어 0.5는 0으로 반올림 되 고 1.5 및 2.5는 모두 2로 반올림 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-186">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="3f9f0-187">이를 *은행원의 반올림* 이라고 하며, 이러한 숫자를 여러 개 더하는 경우 누적 될 수 있는 바이어스를 보정 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-187">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>

     <span data-ttu-id="3f9f0-188">`CInt` 및는 `CLng` <xref:Microsoft.VisualBasic.Conversion.Int%2A> <xref:Microsoft.VisualBasic.Conversion.Fix%2A> 숫자의 소수 부분을 반올림 하지 않고 잘라내는 및 함수와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-188">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="3f9f0-189">또한 `Fix` 및 `Int` 은 전달 하는 것과 동일한 데이터 형식의 값을 항상 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-189">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>

- <span data-ttu-id="3f9f0-190">**날짜/시간 변환입니다.**</span><span class="sxs-lookup"><span data-stu-id="3f9f0-190">**Date/Time Conversions.**</span></span> <span data-ttu-id="3f9f0-191">함수를 사용 <xref:Microsoft.VisualBasic.Information.IsDate%2A> 하 여 값을 날짜 및 시간으로 변환할 수 있는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-191">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="3f9f0-192">`CDate` 는 날짜 리터럴과 시간 리터럴을 인식 하지만 숫자 값은 인식 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-192">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="3f9f0-193">Visual Basic 6.0 `Date` 값을 `Date` Visual Basic 2005 이상 버전의 값으로 변환 하려면 메서드를 사용할 수 있습니다 <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-193">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>

- <span data-ttu-id="3f9f0-194">**중립 날짜/시간 값입니다.**</span><span class="sxs-lookup"><span data-stu-id="3f9f0-194">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="3f9f0-195">[날짜 데이터 형식](../data-types/date-data-type.md) 에는 항상 날짜 및 시간 정보가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-195">The [Date Data Type](../data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="3f9f0-196">형식 변환의 목적을 위해 Visual Basic은 1/1/0001 (1 년 1 월 1 일)을 날짜의 *중립 값* 으로 간주 하 고 00:00:00 (자정)을 시간에 대 한 중립 값으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-196">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="3f9f0-197">값을 문자열로 변환 하는 경우 `Date` `CStr` 은 결과 문자열에 중립 값을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-197">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="3f9f0-198">예를 들어 문자열로 변환 하는 경우 `#January 1, 0001 9:30:00#` 결과는 "9:30:00 AM"이 고 날짜 정보는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-198">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="3f9f0-199">그러나 날짜 정보는 여전히 원래 값에 존재 `Date` 하며 함수 등의 함수를 사용 하 여 복구할 수 있습니다 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-199">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>

- <span data-ttu-id="3f9f0-200">**문화권 민감도.**</span><span class="sxs-lookup"><span data-stu-id="3f9f0-200">**Culture Sensitivity.**</span></span> <span data-ttu-id="3f9f0-201">문자열을 포함 하는 형식 변환 함수는 응용 프로그램의 현재 문화권 설정에 따라 변환을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-201">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="3f9f0-202">예를 들어는 `CDate` 시스템의 로캘 설정에 따라 날짜 형식을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-202">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="3f9f0-203">요일, 월 및 연도를 로캘의 올바른 순서로 제공 해야 합니다. 그렇지 않으면 날짜가 올바르게 해석 되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-203">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="3f9f0-204">"수요일"과 같이 요일 문자열이 포함 된 경우에는 자세한 날짜 형식을 인식할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-204">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>

     <span data-ttu-id="3f9f0-205">로캘에서 지정 된 값 이외의 형식으로 값의 문자열 표현으로 변환 해야 하는 경우에는 Visual Basic 형식 변환 함수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-205">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="3f9f0-206">이렇게 하려면 `ToString(IFormatProvider)` `Parse(String, IFormatProvider)` 해당 값 형식의 및 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-206">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="3f9f0-207">예를 들어 문자열을로 변환 하는 경우를 사용 하 <xref:System.Double.Parse%2A?displayProperty=nameWithType> `Double` 고 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을 문자열로 변환할 때를 사용 `Double` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-207">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>

## <a name="ctype-function"></a><span data-ttu-id="3f9f0-208">CType Function</span><span class="sxs-lookup"><span data-stu-id="3f9f0-208">CType Function</span></span>

<span data-ttu-id="3f9f0-209">[CType 함수](ctype-function.md) 는 두 번째 인수인를 사용 하 `typename` 고 `expression` 로 강제 `typename` `typename` 변환 합니다. 여기서은 유효한 변환이 있는 모든 데이터 형식, 구조체, 클래스 또는 인터페이스 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-209">The [CType Function](ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>

<span data-ttu-id="3f9f0-210">를 `CType` 다른 형식 변환 키워드와 비교 하려면 [DirectCast Operator](../operators/directcast-operator.md) 및 [TryCast operator](../operators/trycast-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-210">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../operators/directcast-operator.md) and [TryCast Operator](../operators/trycast-operator.md).</span></span>

## <a name="cbool-example"></a><span data-ttu-id="3f9f0-211">CBool 예</span><span class="sxs-lookup"><span data-stu-id="3f9f0-211">CBool Example</span></span>

<span data-ttu-id="3f9f0-212">다음 예에서는 함수를 사용 하 여 `CBool` 식을 값으로 변환 합니다 `Boolean` .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-212">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="3f9f0-213">식이 0이 아닌 값으로 계산 되는 경우는를 `CBool` 반환 하 `True` 고, 그렇지 않으면를 반환 `False` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-213">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>

[!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]

## <a name="cbyte-example"></a><span data-ttu-id="3f9f0-214">CByte 예제</span><span class="sxs-lookup"><span data-stu-id="3f9f0-214">CByte Example</span></span>

<span data-ttu-id="3f9f0-215">다음 예에서는 함수를 사용 하 여 `CByte` 식을로 변환 합니다 `Byte` .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-215">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>

[!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]

## <a name="cchar-example"></a><span data-ttu-id="3f9f0-216">CChar 예</span><span class="sxs-lookup"><span data-stu-id="3f9f0-216">CChar Example</span></span>

<span data-ttu-id="3f9f0-217">다음 예에서는 함수를 사용 하 여 `CChar` 식의 첫 번째 문자를 형식으로 변환 합니다 `String` `Char` .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-217">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>

[!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]

<span data-ttu-id="3f9f0-218">에 대 한 입력 인수는 `CChar` 데이터 형식 또는 이어야 합니다 `Char` `String` .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-218">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="3f9f0-219">`CChar`숫자 데이터 형식을 허용 하지 않으므로를 사용 하 여 숫자를 문자로 변환할 수는 없습니다 `CChar` .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-219">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="3f9f0-220">다음 예제에서는 코드 포인트 (문자 코드)를 나타내는 숫자를 가져와 해당 문자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-220">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="3f9f0-221">함수를 사용 하 여 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> 숫자 문자열을 가져오고, `CInt` 문자열을 형식으로 변환 하 고, 숫자를 `Integer` `ChrW` 형식으로 변환 `Char` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-221">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>

[!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]

## <a name="cdate-example"></a><span data-ttu-id="3f9f0-222">CDate 예</span><span class="sxs-lookup"><span data-stu-id="3f9f0-222">CDate Example</span></span>

<span data-ttu-id="3f9f0-223">다음 예에서는 함수를 사용 하 여 `CDate` 문자열을 값으로 변환 합니다 `Date` .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-223">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="3f9f0-224">일반적으로 날짜와 시간을 문자열로 하드 코딩 하는 것은 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-224">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="3f9f0-225">대신 #Feb 12, 1969 # 및 #4:45:23 PM #과 같은 날짜 리터럴과 시간 리터럴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-225">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>

[!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]

## <a name="cdbl-example"></a><span data-ttu-id="3f9f0-226">CDbl 예</span><span class="sxs-lookup"><span data-stu-id="3f9f0-226">CDbl Example</span></span>

[!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]

## <a name="cdec-example"></a><span data-ttu-id="3f9f0-227">CDec 예</span><span class="sxs-lookup"><span data-stu-id="3f9f0-227">CDec Example</span></span>

<span data-ttu-id="3f9f0-228">다음 예에서는 함수를 사용 하 여 `CDec` 숫자 값을로 변환 `Decimal` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-228">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>

[!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]

## <a name="cint-example"></a><span data-ttu-id="3f9f0-229">CInt 예</span><span class="sxs-lookup"><span data-stu-id="3f9f0-229">CInt Example</span></span>

<span data-ttu-id="3f9f0-230">다음 예에서는 함수를 사용 하 여 `CInt` 값을로 변환 `Integer` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-230">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>

[!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]

## <a name="clng-example"></a><span data-ttu-id="3f9f0-231">CLng 예제</span><span class="sxs-lookup"><span data-stu-id="3f9f0-231">CLng Example</span></span>

<span data-ttu-id="3f9f0-232">다음 예에서는 함수를 사용 하 여 `CLng` 값을로 변환 `Long` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-232">The following example uses the `CLng` function to convert values to `Long`.</span></span>

[!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]

## <a name="cobj-example"></a><span data-ttu-id="3f9f0-233">CObj 예제</span><span class="sxs-lookup"><span data-stu-id="3f9f0-233">CObj Example</span></span>

<span data-ttu-id="3f9f0-234">다음 예에서는 함수를 사용 하 여 `CObj` 숫자 값을로 변환 `Object` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-234">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="3f9f0-235">`Object`변수 자체는 할당 된 값을 가리키는 4 바이트 포인터만 포함 `Double` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-235">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>

[!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]

## <a name="csbyte-example"></a><span data-ttu-id="3f9f0-236">CSByte 예제</span><span class="sxs-lookup"><span data-stu-id="3f9f0-236">CSByte Example</span></span>

<span data-ttu-id="3f9f0-237">다음 예에서는 함수를 사용 하 여 `CSByte` 숫자 값을로 변환 `SByte` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-237">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>

[!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]

## <a name="cshort-example"></a><span data-ttu-id="3f9f0-238">CShort 예제</span><span class="sxs-lookup"><span data-stu-id="3f9f0-238">CShort Example</span></span>

<span data-ttu-id="3f9f0-239">다음 예에서는 함수를 사용 하 여 `CShort` 숫자 값을로 변환 `Short` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-239">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>

[!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]

## <a name="csng-example"></a><span data-ttu-id="3f9f0-240">CSng 예제</span><span class="sxs-lookup"><span data-stu-id="3f9f0-240">CSng Example</span></span>

<span data-ttu-id="3f9f0-241">다음 예에서는 함수를 사용 하 여 `CSng` 값을로 변환 `Single` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-241">The following example uses the `CSng` function to convert values to `Single`.</span></span>

[!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]

## <a name="cstr-example"></a><span data-ttu-id="3f9f0-242">CStr 예</span><span class="sxs-lookup"><span data-stu-id="3f9f0-242">CStr Example</span></span>

<span data-ttu-id="3f9f0-243">다음 예에서는 함수를 사용 하 여 `CStr` 숫자 값을로 변환 `String` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-243">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>

[!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]

<span data-ttu-id="3f9f0-244">다음 예에서는 함수를 사용 하 여 값 `CStr` 을 값으로 변환 합니다 `Date` `String` .</span><span class="sxs-lookup"><span data-stu-id="3f9f0-244">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>

[!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]

<span data-ttu-id="3f9f0-245">`CStr` 는 항상 `Date` 현재 로캘의 표준 약식 형식으로 값을 렌더링 합니다 (예: "6/15/2003 4:35:47 PM").</span><span class="sxs-lookup"><span data-stu-id="3f9f0-245">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="3f9f0-246">그러나는 `CStr` 시간에 대 한 날짜와 00:00:00의 *중립 값* 1/1/0001을 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-246">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>

<span data-ttu-id="3f9f0-247">에서 반환 하는 값에 대 한 자세한 `CStr` 내용은 [CStr 함수의 반환 값](return-values-for-the-cstr-function.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-247">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](return-values-for-the-cstr-function.md).</span></span>

## <a name="cuint-example"></a><span data-ttu-id="3f9f0-248">Uint 예제</span><span class="sxs-lookup"><span data-stu-id="3f9f0-248">CUInt Example</span></span>

<span data-ttu-id="3f9f0-249">다음 예에서는 함수를 사용 하 여 `CUInt` 숫자 값을로 변환 `UInteger` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-249">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>

[!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]

## <a name="culng-example"></a><span data-ttu-id="3f9f0-250">CULng 예제</span><span class="sxs-lookup"><span data-stu-id="3f9f0-250">CULng Example</span></span>

<span data-ttu-id="3f9f0-251">다음 예에서는 함수를 사용 하 여 `CULng` 숫자 값을로 변환 `ULong` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-251">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>

[!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]

## <a name="cushort-example"></a><span data-ttu-id="3f9f0-252">CUShort 예제</span><span class="sxs-lookup"><span data-stu-id="3f9f0-252">CUShort Example</span></span>

<span data-ttu-id="3f9f0-253">다음 예에서는 함수를 사용 하 여 `CUShort` 숫자 값을로 변환 `UShort` 합니다.</span><span class="sxs-lookup"><span data-stu-id="3f9f0-253">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>

[!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]

## <a name="see-also"></a><span data-ttu-id="3f9f0-254">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3f9f0-254">See also</span></span>

- <xref:Microsoft.VisualBasic.Strings.Asc%2A>
- <xref:Microsoft.VisualBasic.Strings.AscW%2A>
- <xref:Microsoft.VisualBasic.Strings.Chr%2A>
- <xref:Microsoft.VisualBasic.Strings.ChrW%2A>
- <xref:Microsoft.VisualBasic.Conversion.Int%2A>
- <xref:Microsoft.VisualBasic.Conversion.Fix%2A>
- <xref:Microsoft.VisualBasic.Strings.Format%2A>
- <xref:Microsoft.VisualBasic.Conversion.Hex%2A>
- <xref:Microsoft.VisualBasic.Conversion.Oct%2A>
- <xref:Microsoft.VisualBasic.Conversion.Str%2A>
- <xref:Microsoft.VisualBasic.Conversion.Val%2A>
- [<span data-ttu-id="3f9f0-255">변환 함수</span><span class="sxs-lookup"><span data-stu-id="3f9f0-255">Conversion Functions</span></span>](conversion-functions.md)
- [<span data-ttu-id="3f9f0-256">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="3f9f0-256">Type Conversions in Visual Basic</span></span>](../../programming-guide/language-features/data-types/type-conversions.md)
