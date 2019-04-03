---
title: 형식 변환 함수(Visual Basic)
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
ms.openlocfilehash: 2b750f41343a4a68e29af6055815efd1e6470252
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58816267"
---
# <a name="type-conversion-functions-visual-basic"></a><span data-ttu-id="06f22-102">형식 변환 함수(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="06f22-102">Type Conversion Functions (Visual Basic)</span></span>
<span data-ttu-id="06f22-103">이러한 함수는 변환 코드가 식을 계산 하는 코드의 일부인 즉 인라인으로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-103">These functions are compiled inline, meaning the conversion code is part of the code that evaluates the expression.</span></span> <span data-ttu-id="06f22-104">때때로 성능을 향상 시키는 변환을 수행 하는 프로시저에 대 한 호출이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-104">Sometimes there is no call to a procedure to accomplish the conversion, which improves performance.</span></span> <span data-ttu-id="06f22-105">각 함수는 식에서 특정 데이터 형식으로 강제 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-105">Each function coerces an expression to a specific data type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06f22-106">구문</span><span class="sxs-lookup"><span data-stu-id="06f22-106">Syntax</span></span>  
  
```  
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
  
## <a name="part"></a><span data-ttu-id="06f22-107">파트</span><span class="sxs-lookup"><span data-stu-id="06f22-107">Part</span></span>  
 `expression`  
 <span data-ttu-id="06f22-108">필수 요소.</span><span class="sxs-lookup"><span data-stu-id="06f22-108">Required.</span></span> <span data-ttu-id="06f22-109">원본 데이터 형식의 모든 식입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-109">Any expression of the source data type.</span></span>  
  
## <a name="return-value-data-type"></a><span data-ttu-id="06f22-110">반환 값 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-110">Return Value Data Type</span></span>  
 <span data-ttu-id="06f22-111">함수 이름은 다음 표에 나와 있는 것 처럼 반환 하는 값의 데이터 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-111">The function name determines the data type of the value it returns, as shown in the following table.</span></span>  
  
|<span data-ttu-id="06f22-112">함수 이름</span><span class="sxs-lookup"><span data-stu-id="06f22-112">Function name</span></span>|<span data-ttu-id="06f22-113">반환 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-113">Return data type</span></span>|<span data-ttu-id="06f22-114">에 대 한 범위 `expression` 인수</span><span class="sxs-lookup"><span data-stu-id="06f22-114">Range for `expression` argument</span></span>|  
|-------------------|----------------------|-------------------------------------|  
|`CBool`|[<span data-ttu-id="06f22-115">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-115">Boolean Data Type</span></span>](../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="06f22-116">유효한 `Char` 또는 `String` 또는 숫자 식입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-116">Any valid `Char` or `String` or numeric expression.</span></span>|  
|`CByte`|[<span data-ttu-id="06f22-117">Byte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-117">Byte Data Type</span></span>](../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="06f22-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0)를 통해 <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (부호 없음); 소수 부분이 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="06f22-118"><xref:System.Byte.MinValue?displayProperty=nameWithType> (0) through <xref:System.Byte.MaxValue?displayProperty=nameWithType> (255) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="06f22-119">Visual Basic 15.8부터 Visual Basic을 사용한 바이트 변환 하는 부동 소수점의 성능을 최적화 합니다 `CByte` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-119">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to byte conversion with the `CByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="06f22-120">참조를 [CInt 예제](#cint-example) 섹션 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-120">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CChar`|[<span data-ttu-id="06f22-121">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-121">Char Data Type</span></span>](../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="06f22-122">유효한 `Char` 또는 `String` 식;의 첫 번째 문자만 `String` 변환 됩니다; 값 0 ~ 65535 (부호 없음) 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-122">Any valid `Char` or `String` expression; only first character of a `String` is converted; value can be 0 through 65535 (unsigned).</span></span>|  
|`CDate`|[<span data-ttu-id="06f22-123">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-123">Date Data Type</span></span>](../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="06f22-124">시간과 날짜의 모든 유효한 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-124">Any valid representation of a date and time.</span></span>|  
|`CDbl`|[<span data-ttu-id="06f22-125">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-125">Double Data Type</span></span>](../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="06f22-126">-1.79769313486231570 + 308에서-4.94065645841246544E-324 음수 값이 있습니다. 4.94065645841246544E-324 1.79769313486231570 e + 308 양수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-126">-1.79769313486231570E+308 through -4.94065645841246544E-324 for negative values; 4.94065645841246544E-324 through 1.79769313486231570E+308 for positive values.</span></span>|  
|`CDec`|[<span data-ttu-id="06f22-127">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-127">Decimal Data Type</span></span>](../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="06f22-128">+ /-79228162514264337593543950335-즉, 소수 자릿수가 없는 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-128">+/-79,228,162,514,264,337,593,543,950,335 for zero-scaled numbers, that is, numbers with no decimal places.</span></span> <span data-ttu-id="06f22-129">소수 자릿수가 28 숫자 범위는 + /-7.9228162514264337593543950335 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-129">For numbers with 28 decimal places, the range is +/-7.9228162514264337593543950335.</span></span> <span data-ttu-id="06f22-130">가장 작은 가능한 0이 아닌 숫자는 0.0000000000000000000000000001 (+ 1E-28).</span><span class="sxs-lookup"><span data-stu-id="06f22-130">The smallest possible non-zero number is 0.0000000000000000000000000001 (+/-1E-28).</span></span>|  
|`CInt`|[<span data-ttu-id="06f22-131">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-131">Integer Data Type</span></span>](../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="06f22-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2147483648)부터 <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2147483647); 소수 부분이 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="06f22-132"><xref:System.Int32.MinValue?displayProperty=nameWithType> (-2,147,483,648) through <xref:System.Int32.MaxValue?displayProperty=nameWithType> (2,147,483,647); fractional parts are rounded.<sup>1</sup></span></span> <br/><br/><span data-ttu-id="06f22-133">Visual Basic 15.8부터 Visual Basic을 사용 하 여 정수 변환 부동 소수점의 성능을 최적화 합니다 `CInt` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-133">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to integer conversion with the `CInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="06f22-134">참조를 [CInt 예제](#cint-example) 섹션 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-134">See the [CInt Example](#cint-example) section for an example.</span></span> |  
|`CLng`|[<span data-ttu-id="06f22-135">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-135">Long Data Type</span></span>](../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="06f22-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9223372036854775808)부터 <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9223372036854775807); 소수 부분이 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="06f22-136"><xref:System.Int64.MinValue?displayProperty=nameWithType> (-9,223,372,036,854,775,808) through <xref:System.Int64.MaxValue?displayProperty=nameWithType> (9,223,372,036,854,775,807); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="06f22-137">Visual Basic 15.8부터 Visual Basic을 사용 하 여 64 비트 정수로 변환 하는 부동 소수점의 성능을 최적화 합니다 `CLng` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-137">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 64-bit integer conversion with the `CLng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="06f22-138">참조를 [CInt 예제](#cint-example) 섹션 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-138">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CObj`|[<span data-ttu-id="06f22-139">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-139">Object Data Type</span></span>](../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="06f22-140">모든 유효한 식입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-140">Any valid expression.</span></span>|  
|`CSByte`|[<span data-ttu-id="06f22-141">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-141">SByte Data Type</span></span>](../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="06f22-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128)를 통해 <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); 소수 부분이 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="06f22-142"><xref:System.SByte.MinValue?displayProperty=nameWithType> (-128) through <xref:System.SByte.MaxValue?displayProperty=nameWithType> (127); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="06f22-143">Visual Basic 15.8부터 Visual Basic을 사용 하 여 부호 있는 바이트 변환 부동 소수점의 성능을 최적화 합니다 `CSByte` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-143">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to signed byte conversion with the `CSByte` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="06f22-144">참조를 [CInt 예제](#cint-example) 섹션 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-144">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CShort`|[<span data-ttu-id="06f22-145">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-145">Short Data Type</span></span>](../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="06f22-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32768)부터 <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32767); 소수 부분이 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="06f22-146"><xref:System.Int16.MinValue?displayProperty=nameWithType> (-32,768) through <xref:System.Int16.MaxValue?displayProperty=nameWithType> (32,767); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="06f22-147">Visual Basic 15.8부터 Visual Basic을 사용 하 여 16 비트 정수로 변환 하는 부동 소수점의 성능을 최적화 합니다 `CShort` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-147">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to 16-bit integer conversion with the `CShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="06f22-148">참조를 [CInt 예제](#cint-example) 섹션 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-148">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CSng`|[<span data-ttu-id="06f22-149">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-149">Single Data Type</span></span>](../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="06f22-150">-3.402823E + 38에서-1.401298E-45 음수 값이 있습니다. 1.401298E-45 3.402823E + 38 양수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-150">-3.402823E+38 through -1.401298E-45 for negative values; 1.401298E-45 through 3.402823E+38 for positive values.</span></span>|  
|`CStr`|[<span data-ttu-id="06f22-151">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-151">String Data Type</span></span>](../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="06f22-152">에 대 한 반환 `CStr` 종속 된 `expression` 인수입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-152">Returns for `CStr` depend on the `expression` argument.</span></span> <span data-ttu-id="06f22-153">참조 [CStr 함수의 반환 값](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-153">See [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>|  
|`CUInt`|[<span data-ttu-id="06f22-154">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-154">UInteger Data Type</span></span>](../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="06f22-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0)를 통해 <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4294967295) (부호 없음); 소수 부분이 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="06f22-155"><xref:System.UInt32.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt32.MaxValue?displayProperty=nameWithType> (4,294,967,295) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="06f22-156">Visual Basic 15.8부터 Visual Basic을 사용 하 여 부호 없는 정수로 변환 하는 부동 소수점의 성능을 최적화 합니다 `CUInt` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-156">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned integer conversion with the `CUInt` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="06f22-157">참조를 [CInt 예제](#cint-example) 섹션 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-157">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CULng`|[<span data-ttu-id="06f22-158">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-158">ULong Data Type</span></span>](../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="06f22-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0)를 통해 <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18446744073709551615) (부호 없음); 소수 부분이 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="06f22-159"><xref:System.UInt64.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt64.MaxValue?displayProperty=nameWithType> (18,446,744,073,709,551,615) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="06f22-160">Visual Basic 15.8부터 Visual Basic을 사용 하 여 부호 없는 정수 (long) 변환 부동 소수점의 성능을 최적화 합니다 `CULng` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-160">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned long integer conversion with the `CULng` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="06f22-161">참조를 [CInt 예제](#cint-example) 섹션 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-161">See the [CInt Example](#cint-example) section for an example.</span></span>|  
|`CUShort`|[<span data-ttu-id="06f22-162">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="06f22-162">UShort Data Type</span></span>](../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="06f22-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0)를 통해 <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (부호 없음); 소수 부분이 반올림 됩니다.<sup> 1</sup></span><span class="sxs-lookup"><span data-stu-id="06f22-163"><xref:System.UInt16.MinValue?displayProperty=nameWithType> (0) through <xref:System.UInt16.MaxValue?displayProperty=nameWithType> (65,535) (unsigned); fractional parts are rounded.<sup>1</sup></span></span><br/><br/><span data-ttu-id="06f22-164">Visual Basic 15.8부터 Visual Basic을 사용 하 여 부호 없는 16 비트 정수로 변환 하는 부동 소수점의 성능을 최적화 합니다 `CUShort` 함수를 참조 하세요 합니다 [주의](#remarks) 자세한 내용은 섹션입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-164">Starting with Visual Basic 15.8, Visual Basic optimizes the performance of floating-point to unsigned 16-bit integer conversion with the `CUShort` function; see the [Remarks](#remarks) section for more information.</span></span> <span data-ttu-id="06f22-165">참조를 [CInt 예제](#cint-example) 섹션 예입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-165">See the [CInt Example](#cint-example) section for an example.</span></span>|  
  
 <span data-ttu-id="06f22-166"><sup>1</sup> 소수 부분이 호출 반올림 하는 특수 한 유형의 대상이 될 수 있습니다 *은행원의 반올림*합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-166"><sup>1</sup> Fractional parts can be subject to a special type of rounding called *banker's rounding*.</span></span> <span data-ttu-id="06f22-167">자세한 내용은 "주의"를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="06f22-167">See "Remarks" for more information.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="06f22-168">설명</span><span class="sxs-lookup"><span data-stu-id="06f22-168">Remarks</span></span>  
 <span data-ttu-id="06f22-169">일반적으로 사용 해야는 Visual Basic 형식 변환 함수는.NET Framework 메서드 보다 우선적으로 같은 `ToString()`하거나에서 <xref:System.Convert> 클래스 또는 개별 형식 구조체 또는 클래스에서.</span><span class="sxs-lookup"><span data-stu-id="06f22-169">As a rule, you should use the Visual Basic type conversion functions in preference to the .NET Framework methods such as `ToString()`, either on the <xref:System.Convert> class or on an individual type structure or class.</span></span> <span data-ttu-id="06f22-170">Visual Basic 함수는 Visual Basic 코드를 사용 하 여 최적의 상호 작용을 위해 설계 되었습니다 및 더 간결 하 고 읽기 쉽게 소스 코드 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-170">The Visual Basic functions are designed for optimal interaction with Visual Basic code, and they also make your source code shorter and easier to read.</span></span> <span data-ttu-id="06f22-171">또한.NET Framework 변환 메서드를 생성 하지 않을 경우 Visual Basic 함수 예를 들어 변환 하는 경우와 동일한 결과 `Boolean` 에 `Integer`입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-171">In addition, the .NET Framework conversion methods do not always produce the same results as the Visual Basic functions, for example when converting `Boolean` to `Integer`.</span></span> <span data-ttu-id="06f22-172">자세한 내용은 [데이터 형식 문제 해결](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-172">For more information, see [Troubleshooting Data Types](../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md).</span></span>  


<span data-ttu-id="06f22-173">Visual Basic 15.8부터 부동으로 소수점을 정수로 변환의 성능을 최적화 된 전달 하는 경우는 <xref:System.Single> 또는 <xref:System.Double> 정수 변환 함수 중 하나에 다음과 같은 방법으로 반환 되는 값 (`CByte`합니다 `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span><span class="sxs-lookup"><span data-stu-id="06f22-173">Starting with Visual Basic 15.8, the performance of floating-point-to-integer conversion is optimized when you pass the <xref:System.Single> or <xref:System.Double> value returned by the following methods to one of the integer conversion functions (`CByte`, `CShort`, `CInt`, `CLng`, `CSByte`, `CUShort`, `CUInt`, `CULng`):</span></span>

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

<span data-ttu-id="06f22-174">이 최적화는 많은 수의 정수 변환 실행할 배 더 빠르게 수행 하는 코드를 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-174">This optimization allows code that does a large number of integer conversions to run up to twice as fast.</span></span> <span data-ttu-id="06f22-175">다음 예제에서는 이러한 최적화 부동으로 소수점을 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-175">The following example illustrates these optimized floating-point-to-integer conversions:</span></span>

```vb
Dim s As Single = 173.7619
Dim d As Double = s 

Dim i1 As Integer = CInt(Fix(s))               ' Result: 173
Dim b1 As Byte = CByte(Int(d))                 ' Result: 173
Dim s1 AS Short = CShort(Math.Truncate(s))     ' Result: 173
Dim i2 As Integer = CInt(Math.Ceiling(d))      ' Result: 174
Dim i3 As Integer = CInt(Math.Round(s))        ' Result: 174
```

## <a name="behavior"></a><span data-ttu-id="06f22-176">동작</span><span class="sxs-lookup"><span data-stu-id="06f22-176">Behavior</span></span>  
  
-   <span data-ttu-id="06f22-177">**강제 변환 합니다.**</span><span class="sxs-lookup"><span data-stu-id="06f22-177">**Coercion.**</span></span> <span data-ttu-id="06f22-178">일반적으로 기본 데이터 형식 보다는 특정 데이터 형식 작업의 결과 강제 하는 데이터 형식 변환 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-178">In general, you can use the data type conversion functions to coerce the result of an operation to a particular data type rather than the default data type.</span></span> <span data-ttu-id="06f22-179">사용 예를 들어 `CDec` 10 진수 연산을 경우는 단 정밀도, 배정밀도 정수 산술 연산은 일반적으로 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-179">For example, use `CDec` to force decimal arithmetic in cases where single-precision, double-precision, or integer arithmetic would normally take place.</span></span>  
  
-   <span data-ttu-id="06f22-180">**변환 실패입니다.**</span><span class="sxs-lookup"><span data-stu-id="06f22-180">**Failed Conversions.**</span></span> <span data-ttu-id="06f22-181">경우는 `expression` 함수에 전달 되는 데이터 형식의 범위를 벗어난 하는 변환할는 <xref:System.OverflowException> 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-181">If the `expression` passed to the function is outside the range of the data type to which it is to be converted, an <xref:System.OverflowException> occurs.</span></span>  
  
-   <span data-ttu-id="06f22-182">**소수 부분입니다.**</span><span class="sxs-lookup"><span data-stu-id="06f22-182">**Fractional Parts.**</span></span> <span data-ttu-id="06f22-183">정수가 아닌 값을 정수 계열 변환 하는 경우 입력에서 정수 변환 함수 (`CByte`, `CInt`, `CLng`, `CSByte`를 `CShort`를 `CUInt`, `CULng`, 및 `CUShort`) 제거 합니다 소수 부분 및 값을 가장 가까운 정수로 반올림 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-183">When you convert a nonintegral value to an integral type, the integer conversion functions (`CByte`, `CInt`, `CLng`, `CSByte`, `CShort`, `CUInt`, `CULng`, and `CUShort`) remove the fractional part and round the value to the closest integer.</span></span>  
  
     <span data-ttu-id="06f22-184">소수 부분이 정확 하 게 하는 경우 0.5 정수 변환 함수를 반올림 하는 가장 근사한 짝수 정수로 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-184">If the fractional part is exactly 0.5, the integer conversion functions round it to the nearest even integer.</span></span> <span data-ttu-id="06f22-185">예를 들어 0.5 0 및 1.5와 2.5는 2로 반올림으로 반올림 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-185">For example, 0.5 rounds to 0, and 1.5 and 2.5 both round to 2.</span></span> <span data-ttu-id="06f22-186">이 라고도 *은행원의 반올림*, 및 이러한 많은 숫자를 함께 추가 하는 경우 누적 될 수 있습니다를 보완 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-186">This is sometimes called *banker's rounding*, and its purpose is to compensate for a bias that could accumulate when adding many such numbers together.</span></span>  
  
     <span data-ttu-id="06f22-187">`CInt` 및 `CLng` 에서 다를 <xref:Microsoft.VisualBasic.Conversion.Int%2A> 및 <xref:Microsoft.VisualBasic.Conversion.Fix%2A> 함수는 숫자의 소수 부분을 반올림 하는 것이 아니라, truncate입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-187">`CInt` and `CLng` differ from the <xref:Microsoft.VisualBasic.Conversion.Int%2A> and <xref:Microsoft.VisualBasic.Conversion.Fix%2A> functions, which truncate, rather than round, the fractional part of a number.</span></span> <span data-ttu-id="06f22-188">또한 `Fix` 고 `Int` 에 통과할 때 항상 동일한 데이터 형식의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-188">Also, `Fix` and `Int` always return a value of the same data type as you pass in.</span></span>  
  
-   <span data-ttu-id="06f22-189">**변환 날짜/시간입니다.**</span><span class="sxs-lookup"><span data-stu-id="06f22-189">**Date/Time Conversions.**</span></span> <span data-ttu-id="06f22-190">사용 된 <xref:Microsoft.VisualBasic.Information.IsDate%2A> 날짜 및 시간 값을 변환할 수 있는지를 결정 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-190">Use the <xref:Microsoft.VisualBasic.Information.IsDate%2A> function to determine if a value can be converted to a date and time.</span></span> <span data-ttu-id="06f22-191">`CDate` 리터럴 날짜 및 시간 리터럴 하지만 숫자가 아닌 값을 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-191">`CDate` recognizes date literals and time literals but not numeric values.</span></span> <span data-ttu-id="06f22-192">Visual Basic 6.0을 변환할 `Date` 값을 `Date` Visual Basic 2005의에서 값 또는 이상 버전을 사용할 수는 <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> 메서드.</span><span class="sxs-lookup"><span data-stu-id="06f22-192">To convert a Visual Basic 6.0 `Date` value to a `Date` value in Visual Basic 2005 or later versions, you can use the <xref:System.DateTime.FromOADate%2A?displayProperty=nameWithType> method.</span></span>  
  
-   <span data-ttu-id="06f22-193">**중립 날짜/시간 값입니다.**</span><span class="sxs-lookup"><span data-stu-id="06f22-193">**Neutral Date/Time Values.**</span></span> <span data-ttu-id="06f22-194">합니다 [날짜 데이터 형식](../../../visual-basic/language-reference/data-types/date-data-type.md) 항상 날짜 및 시간 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-194">The [Date Data Type](../../../visual-basic/language-reference/data-types/date-data-type.md) always contains both date and time information.</span></span> <span data-ttu-id="06f22-195">형식 변환 목적으로, Visual Basic은 간주 1/1/0001 (1 년 1 월 1 일) 수를 *중립 값* 시간에 대 한 중립 값으로 날짜 및 00시: 00 (자정)에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-195">For purposes of type conversion, Visual Basic considers 1/1/0001 (January 1 of the year 1) to be a *neutral value* for the date, and 00:00:00 (midnight) to be a neutral value for the time.</span></span> <span data-ttu-id="06f22-196">변환 하는 경우는 `Date` 값을 문자열로 `CStr` 기본값이 결과 문자열에 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-196">If you convert a `Date` value to a string, `CStr` does not include neutral values in the resulting string.</span></span> <span data-ttu-id="06f22-197">예를 들어, 변환 하는 경우 `#January 1, 0001 9:30:00#` 문자열로 결과 "오전 9시 30분: 00"은 날짜 정보를 표시 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-197">For example, if you convert `#January 1, 0001 9:30:00#` to a string, the result is "9:30:00 AM"; the date information is suppressed.</span></span> <span data-ttu-id="06f22-198">그러나 날짜 정보는 여전히 원래 `Date` 값과 같은 함수를 사용 하 여 복구할 수 있습니다 <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-198">However, the date information is still present in the original `Date` value and can be recovered with functions such as <xref:Microsoft.VisualBasic.DateAndTime.DatePart%2A> function.</span></span>  
  
-   <span data-ttu-id="06f22-199">**문화권 구분 합니다.**</span><span class="sxs-lookup"><span data-stu-id="06f22-199">**Culture Sensitivity.**</span></span> <span data-ttu-id="06f22-200">응용 프로그램에 대 한 현재 문화권 설정에 따라 변환을 수행 하는 문자열을 포함 하는 형식 변환 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-200">The type conversion functions involving strings perform conversions based on the current culture settings for the application.</span></span> <span data-ttu-id="06f22-201">예를 들어 `CDate` 시스템의 로캘 설정에 따라 날짜 형식을 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-201">For example, `CDate` recognizes date formats according to the locale setting of your system.</span></span> <span data-ttu-id="06f22-202">일, 월 및 연도 로캘에 대 한 올바른 순서로 제공 해야 합니다 또는 날짜를 올바르게 해석 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-202">You must provide the day, month, and year in the correct order for your locale, or the date might not be interpreted correctly.</span></span> <span data-ttu-id="06f22-203">자세한 날짜 형식은 "Wednesday" 등의 주 날짜 문자열을 포함 하는 경우 인식 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-203">A long date format is not recognized if it contains a day-of-the-week string, such as "Wednesday".</span></span>  
  
     <span data-ttu-id="06f22-204">로캘에 지정 된 것과 다른 형식으로 값의 문자열 표현에서 변환 해야 할 경우 Visual Basic 형식 변환 함수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-204">If you need to convert to or from a string representation of a value in a format other than the one specified by your locale, you cannot use the Visual Basic type conversion functions.</span></span> <span data-ttu-id="06f22-205">이 위해 사용 합니다 `ToString(IFormatProvider)` 및 `Parse(String, IFormatProvider)` 메서드는 값의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-205">To do this, use the `ToString(IFormatProvider)` and `Parse(String, IFormatProvider)` methods of that value's type.</span></span> <span data-ttu-id="06f22-206">사용 예를 들어 <xref:System.Double.Parse%2A?displayProperty=nameWithType> 문자열을 변환 하는 경우는 `Double`를 사용 하 여 <xref:System.Double.ToString%2A?displayProperty=nameWithType> 형식의 값을 변환 하는 경우 `Double` 문자열로 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-206">For example, use <xref:System.Double.Parse%2A?displayProperty=nameWithType> when converting a string to a `Double`, and use <xref:System.Double.ToString%2A?displayProperty=nameWithType> when converting a value of type `Double` to a string.</span></span>  
  
## <a name="ctype-function"></a><span data-ttu-id="06f22-207">CType Function</span><span class="sxs-lookup"><span data-stu-id="06f22-207">CType Function</span></span>  
 <span data-ttu-id="06f22-208">[CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) 두 번째 인수 `typename`, 강제 변환 하 고 `expression` 에 `typename`여기서 `typename` 데이터 형식, 구조체, 클래스 또는 인터페이스를 있을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-208">The [CType Function](../../../visual-basic/language-reference/functions/ctype-function.md) takes a second argument, `typename`, and coerces `expression` to `typename`, where `typename` can be any data type, structure, class, or interface to which there exists a valid conversion.</span></span>  
  
 <span data-ttu-id="06f22-209">에 대 한 비교 `CType` 다른 형식 변환 키워드를 사용 하 여 볼 [DirectCast 연산자](../../../visual-basic/language-reference/operators/directcast-operator.md) 하 고 [TryCast 연산자](../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-209">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
## <a name="cbool-example"></a><span data-ttu-id="06f22-210">CBool 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-210">CBool Example</span></span>  
 <span data-ttu-id="06f22-211">다음 예제에서는 합니다 `CBool` 함수 식을 변환할 `Boolean` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-211">The following example uses the `CBool` function to convert expressions to `Boolean` values.</span></span> <span data-ttu-id="06f22-212">식이 0이 아닌 값으로 계산 될 경우 `CBool` 반환 `True`이 고, 그렇지 않으면 반환 `False`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-212">If an expression evaluates to a nonzero value, `CBool` returns `True`; otherwise, it returns `False`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#1)]  
  
## <a name="cbyte-example"></a><span data-ttu-id="06f22-213">CByte 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-213">CByte Example</span></span>  
 <span data-ttu-id="06f22-214">다음 예제에서는 합니다 `CByte` 식을 변환 하는 함수를 `Byte`입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-214">The following example uses the `CByte` function to convert an expression to a `Byte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#2)]  
  
## <a name="cchar-example"></a><span data-ttu-id="06f22-215">CChar 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-215">CChar Example</span></span>  
 <span data-ttu-id="06f22-216">다음 예제에서는 합니다 `CChar` 의 첫 번째 문자를 변환 하는 함수를 `String` 식을 `Char` 형식.</span><span class="sxs-lookup"><span data-stu-id="06f22-216">The following example uses the `CChar` function to convert the first character of a `String` expression to a `Char` type.</span></span>  
  
 [!code-vb[VbVbalrFunctions#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#3)]  
  
 <span data-ttu-id="06f22-217">입력된 인수 `CChar` 데이터 형식 이어야 합니다 `Char` 또는 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-217">The input argument to `CChar` must be of data type `Char` or `String`.</span></span> <span data-ttu-id="06f22-218">사용할 수 없습니다 `CChar` 때문에 숫자를 문자로 변환할 `CChar` 숫자 데이터 형식을 허용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-218">You cannot use `CChar` to convert a number to a character, because `CChar` cannot accept a numeric data type.</span></span> <span data-ttu-id="06f22-219">다음 예제에서는 코드 포인트 (문자 코드)를 나타내는 숫자를 가져오고 해당 문자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-219">The following example obtains a number representing a code point (character code) and converts it to the corresponding character.</span></span> <span data-ttu-id="06f22-220">사용 하 여는 <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> 숫자의 문자열을 가져올 함수 `CInt` 형식으로 문자열을 변환할 `Integer`, 및 `ChrW` 숫자 형식으로 변환 `Char`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-220">It uses the <xref:Microsoft.VisualBasic.Interaction.InputBox%2A> function to obtain the string of digits, `CInt` to convert the string to type `Integer`, and `ChrW` to convert the number to type `Char`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#4)]  
  
## <a name="cdate-example"></a><span data-ttu-id="06f22-221">CDate 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-221">CDate Example</span></span>  
 <span data-ttu-id="06f22-222">다음 예제에서는 합니다 `CDate` 문자열을 변환 하는 함수 `Date` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-222">The following example uses the `CDate` function to convert strings to `Date` values.</span></span> <span data-ttu-id="06f22-223">일반적으로 하드 코딩 된 날짜 및 시간 문자열 (이 예제 에서처럼)으로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-223">In general, hard-coding dates and times as strings (as shown in this example) is not recommended.</span></span> <span data-ttu-id="06f22-224">날짜 리터럴과 #Feb 12, 1969 # 등의 시간 리터럴을 사용 하 여 및 # 4시 45분: 23 PM #를 대신 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-224">Use date literals and time literals, such as #Feb 12, 1969# and #4:45:23 PM#, instead.</span></span>  
  
 [!code-vb[VbVbalrFunctions#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#5)]  
  
## <a name="cdbl-example"></a><span data-ttu-id="06f22-225">CDbl 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-225">CDbl Example</span></span>  
 [!code-vb[VbVbalrFunctions#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#6)]  
  
## <a name="cdec-example"></a><span data-ttu-id="06f22-226">CDec 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-226">CDec Example</span></span>  
 <span data-ttu-id="06f22-227">다음 예제에서는 합니다 `CDec` 숫자 값으로 변환 하는 함수 `Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-227">The following example uses the `CDec` function to convert a numeric value to `Decimal`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#7)]  
  
## <a name="cint-example"></a><span data-ttu-id="06f22-228">CInt 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-228">CInt Example</span></span>  
 <span data-ttu-id="06f22-229">다음 예제에서는 합니다 `CInt` 함수에 값을 변환할 `Integer`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-229">The following example uses the `CInt` function to convert a value to `Integer`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#8)]  

## <a name="clng-example"></a><span data-ttu-id="06f22-230">CLng 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-230">CLng Example</span></span>
 <span data-ttu-id="06f22-231">다음 예제에서는 합니다 `CLng` 값을 변환 하는 함수 `Long`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-231">The following example uses the `CLng` function to convert values to `Long`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#9)]  
  
## <a name="cobj-example"></a><span data-ttu-id="06f22-232">CObj 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-232">CObj Example</span></span>  
 <span data-ttu-id="06f22-233">다음 예제에서는 합니다 `CObj` 숫자 값으로 변환 하는 함수 `Object`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-233">The following example uses the `CObj` function to convert a numeric value to `Object`.</span></span> <span data-ttu-id="06f22-234">`Object` 변수 자체에 4 바이트 포인터를 가리키는 포함 된 `Double` 값이 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-234">The `Object` variable itself contains only a four-byte pointer, which points to the `Double` value assigned to it.</span></span>  
  
 [!code-vb[VbVbalrFunctions#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#10)]  
  
## <a name="csbyte-example"></a><span data-ttu-id="06f22-235">CSByte 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-235">CSByte Example</span></span>  
 <span data-ttu-id="06f22-236">다음 예제에서는 합니다 `CSByte` 숫자 값으로 변환 하는 함수 `SByte`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-236">The following example uses the `CSByte` function to convert a numeric value to `SByte`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#11](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#11)]  
  
## <a name="cshort-example"></a><span data-ttu-id="06f22-237">CShort 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-237">CShort Example</span></span>  
 <span data-ttu-id="06f22-238">다음 예제에서는 합니다 `CShort` 숫자 값으로 변환 하는 함수 `Short`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-238">The following example uses the `CShort` function to convert a numeric value to `Short`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#12)]  
  
## <a name="csng-example"></a><span data-ttu-id="06f22-239">CSng 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-239">CSng Example</span></span>  
 <span data-ttu-id="06f22-240">다음 예제에서는 합니다 `CSng` 값을 변환 하는 함수 `Single`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-240">The following example uses the `CSng` function to convert values to `Single`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#13)]  
  
## <a name="cstr-example"></a><span data-ttu-id="06f22-241">CStr 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-241">CStr Example</span></span>  
 <span data-ttu-id="06f22-242">다음 예제에서는 합니다 `CStr` 숫자 값으로 변환 하는 함수 `String`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-242">The following example uses the `CStr` function to convert a numeric value to `String`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#14)]  
  
 <span data-ttu-id="06f22-243">다음 예제에서는 합니다 `CStr` 변환할 함수 `Date` 값을 `String` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-243">The following example uses the `CStr` function to convert `Date` values to `String` values.</span></span>  
  
 [!code-vb[VbVbalrFunctions#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#15)]  
  
 <span data-ttu-id="06f22-244">`CStr` 항상 렌더링을 `Date` 예를 들어, 현재 로캘에 대 한 표준 짧은 형식으로 값 "2003 년 6 월 15 오후 4시 35분: 47"입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-244">`CStr` always renders a `Date` value in the standard short format for the current locale, for example, "6/15/2003 4:35:47 PM".</span></span> <span data-ttu-id="06f22-245">그러나 `CStr` 를 표시 하지 않습니다 합니다 *중립 값* 1/1/0001의 날짜와 시간에 대 한 00시: 00입니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-245">However, `CStr` suppresses the *neutral values* of 1/1/0001 for the date and 00:00:00 for the time.</span></span>  
  
 <span data-ttu-id="06f22-246">반환 값에 대 한 자세한 `CStr`를 참조 하세요 [CStr 함수의 반환 값](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-246">For more detail on the values returned by `CStr`, see [Return Values for the CStr Function](../../../visual-basic/language-reference/functions/return-values-for-the-cstr-function.md).</span></span>  
  
## <a name="cuint-example"></a><span data-ttu-id="06f22-247">CUInt 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-247">CUInt Example</span></span>  
 <span data-ttu-id="06f22-248">다음 예제에서는 합니다 `CUInt` 숫자 값으로 변환 하는 함수 `UInteger`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-248">The following example uses the `CUInt` function to convert a numeric value to `UInteger`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#16)]  
  
## <a name="culng-example"></a><span data-ttu-id="06f22-249">CULng 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-249">CULng Example</span></span>  
 <span data-ttu-id="06f22-250">다음 예제에서는 합니다 `CULng` 숫자 값으로 변환 하는 함수 `ULong`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-250">The following example uses the `CULng` function to convert a numeric value to `ULong`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#17)]  
  
## <a name="cushort-example"></a><span data-ttu-id="06f22-251">CUShort 예제</span><span class="sxs-lookup"><span data-stu-id="06f22-251">CUShort Example</span></span>  
 <span data-ttu-id="06f22-252">다음 예제에서는 합니다 `CUShort` 숫자 값으로 변환 하는 함수 `UShort`합니다.</span><span class="sxs-lookup"><span data-stu-id="06f22-252">The following example uses the `CUShort` function to convert a numeric value to `UShort`.</span></span>  
  
 [!code-vb[VbVbalrFunctions#18](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrFunctions/VB/Class1.vb#18)]  
  
## <a name="see-also"></a><span data-ttu-id="06f22-253">참고자료</span><span class="sxs-lookup"><span data-stu-id="06f22-253">See also</span></span>

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
- [<span data-ttu-id="06f22-254">변환 함수</span><span class="sxs-lookup"><span data-stu-id="06f22-254">Conversion Functions</span></span>](../../../visual-basic/language-reference/functions/conversion-functions.md)
- [<span data-ttu-id="06f22-255">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="06f22-255">Type Conversions in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
