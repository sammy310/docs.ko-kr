---
title: 명시적 숫자 변환 표 - C# 참조
ms.custom: seodec18
ms.date: 09/06/2018
helpviewer_keywords:
- conversions [C#], explicit numeric
- numeric conversions [C#], explicit
- explicit numeric conversion [C#]
- numeric data types [C#]
- types [C#], explicit numeric conversions
- type conversion [C#], explicit numeric
ms.assetid: f3bb9e76-6b92-4df7-bc36-f866c24e1dfd
ms.openlocfilehash: 24f7401538eb1eeb675e6c3de265688780d6b91a
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67424204"
---
# <a name="explicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="5376a-102">명시적 숫자 변환 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="5376a-102">Explicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="5376a-103">다음 표에서는 [암시적 변환](implicit-numeric-conversions-table.md)이 없는 .NET 숫자 형식 간의 미리 정의된 명시적 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-103">The following table shows the predefined explicit conversions between .NET numeric types for which there is no [implicit conversion](implicit-numeric-conversions-table.md).</span></span>

|<span data-ttu-id="5376a-104">시작</span><span class="sxs-lookup"><span data-stu-id="5376a-104">From</span></span>|<span data-ttu-id="5376a-105">대상</span><span class="sxs-lookup"><span data-stu-id="5376a-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="5376a-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="5376a-106">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="5376a-107">`byte`, `ushort`, `uint`, `ulong` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="5376a-107">`byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="5376a-108">byte</span><span class="sxs-lookup"><span data-stu-id="5376a-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="5376a-109">`sbyte` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="5376a-109">`sbyte` or `char`</span></span>|  
|[<span data-ttu-id="5376a-110">short</span><span class="sxs-lookup"><span data-stu-id="5376a-110">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="5376a-111">`sbyte`, `byte`, `ushort`, `uint`, `ulong` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="5376a-111">`sbyte`, `byte`, `ushort`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="5376a-112">ushort</span><span class="sxs-lookup"><span data-stu-id="5376a-112">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="5376a-113">`sbyte`, `byte`, `short` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="5376a-113">`sbyte`, `byte`, `short`, or `char`</span></span>|  
|[<span data-ttu-id="5376a-114">int</span><span class="sxs-lookup"><span data-stu-id="5376a-114">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="5376a-115">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="5376a-115">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`,or `char`</span></span>|  
|[<span data-ttu-id="5376a-116">uint</span><span class="sxs-lookup"><span data-stu-id="5376a-116">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="5376a-117">`sbyte`, `byte`, `short`, `ushort`, `int` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="5376a-117">`sbyte`, `byte`, `short`, `ushort`, `int`, or `char`</span></span>|  
|[<span data-ttu-id="5376a-118">long</span><span class="sxs-lookup"><span data-stu-id="5376a-118">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="5376a-119">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="5376a-119">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, or `char`</span></span>|  
|[<span data-ttu-id="5376a-120">ulong</span><span class="sxs-lookup"><span data-stu-id="5376a-120">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="5376a-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` 또는 `char`</span><span class="sxs-lookup"><span data-stu-id="5376a-121">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, or `char`</span></span>|  
|[<span data-ttu-id="5376a-122">char</span><span class="sxs-lookup"><span data-stu-id="5376a-122">char</span></span>](char.md)|<span data-ttu-id="5376a-123">`sbyte`, `byte`또는 `short`</span><span class="sxs-lookup"><span data-stu-id="5376a-123">`sbyte`, `byte`, or `short`</span></span>|  
|[<span data-ttu-id="5376a-124">float</span><span class="sxs-lookup"><span data-stu-id="5376a-124">float</span></span>](float.md)|<span data-ttu-id="5376a-125">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="5376a-125">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`,or `decimal`</span></span>|  
|[<span data-ttu-id="5376a-126">double</span><span class="sxs-lookup"><span data-stu-id="5376a-126">double</span></span>](double.md)|<span data-ttu-id="5376a-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="5376a-127">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`,or `decimal`</span></span>|  
|[<span data-ttu-id="5376a-128">decimal</span><span class="sxs-lookup"><span data-stu-id="5376a-128">decimal</span></span>](decimal.md)|<span data-ttu-id="5376a-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float` 또는 `double`</span><span class="sxs-lookup"><span data-stu-id="5376a-129">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `char`, `float`, or `double`</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5376a-130">설명</span><span class="sxs-lookup"><span data-stu-id="5376a-130">Remarks</span></span>  
  
- <span data-ttu-id="5376a-131">명시적 숫자 변환으로 인해 자릿수 손실 또는 예외(일반적으로 <xref:System.OverflowException>)가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-131">The explicit numeric conversion may cause loss of precision or result in throwing an exception, typically an <xref:System.OverflowException>.</span></span>  

- <span data-ttu-id="5376a-132">정수 형식의 값을 다른 정수 형식으로 변환하면 결과는 오버플로 [검사 컨텍스트](checked-and-unchecked.md)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-132">When you convert a value of an integral type to another integral type, the result depends on the overflow [checking context](checked-and-unchecked.md).</span></span> <span data-ttu-id="5376a-133">확인된 컨텍스트에서 소스 값이 대상 형식의 범위 내에 있으면 변환이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-133">In a checked context, the conversion succeeds if the source value is within the range of the destination type.</span></span> <span data-ttu-id="5376a-134">그렇지 않으면 <xref:System.OverflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-134">Otherwise, an <xref:System.OverflowException> is thrown.</span></span> <span data-ttu-id="5376a-135">확인되지 않은 컨텍스트에서 변환은 항상 성공하고 다음과 같이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-135">In an unchecked context, the conversion always succeeds, and proceeds as follows:</span></span>

  - <span data-ttu-id="5376a-136">소스 형식이 대상 형식보다 큰 경우 소스 값은 가장 중요한 비트인 해당 "extra"를 삭제함으로써 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-136">If the source type is larger than the destination type, then the source value is truncated by discarding its "extra" most significant bits.</span></span> <span data-ttu-id="5376a-137">그런 다음, 결과는 대상 형식의 값으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-137">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="5376a-138">소스 형식이 대상 형식보다 작은 경우 소스 값은 대상 형식과 크기가 같도록 부호 확장 또는 0 확장 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-138">If the source type is smaller than the destination type, then the source value is either sign-extended or zero-extended so that it is the same size as the destination type.</span></span> <span data-ttu-id="5376a-139">부호 확장은 소스 형식이 서명된 경우 사용되며, 소스 형식이 서명되지 않은 경우 0 확장이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-139">Sign-extension is used if the source type is signed; zero-extension is used if the source type is unsigned.</span></span> <span data-ttu-id="5376a-140">그런 다음, 결과는 대상 형식의 값으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-140">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="5376a-141">소스 형식이 대상 형식과 동일한 크기인 경우 소스 값은 대상 형식의 값으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-141">If the source type is the same size as the destination type, then the source value is treated as a value of the destination type.</span></span>
  
- <span data-ttu-id="5376a-142">`decimal` 값을 정수 형식으로 변환하면, 이 값은 0을 향한 방향으로 가장 가까운 정수값으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-142">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="5376a-143">결과 정수 값이 대상 형식 범위에서 벗어났을 경우 <xref:System.OverflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-143">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>  
  
- <span data-ttu-id="5376a-144">`double` 또는 `float` 값을 정수 형식으로 변환하면, 이 값은 0을 향한 방향으로 가장 가까운 정수값으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-144">When you convert a `double` or `float` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="5376a-145">결과 정수 값이 대상 형식 범위에서 벗어났을 경우 결과는 오버플로 [검사 컨텍스트](checked-and-unchecked.md)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-145">If the resulting integral value is outside the range of the destination type, the result depends on the overflow [checking context](checked-and-unchecked.md).</span></span> <span data-ttu-id="5376a-146">Checked 컨텍스트에서는 <xref:System.OverflowException>이 throw됩니다. 반면 Unchecked 컨텍스트에서 결과는 지정되지 않은 대상 형식 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-146">In a checked context, an <xref:System.OverflowException> is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>  
  
- <span data-ttu-id="5376a-147">`double`을 `float`로 변환할 경우 `double` 값을 가장 가까운 `float` 값으로 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-147">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="5376a-148">`double` 값이 너무 크거나 작아서 대상 형식에 맞출 수 없을 경우 결과 값은 0 또는 무한대가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-148">If the `double` value is too small or too large to fit into the destination type, the result will be zero or infinity.</span></span>  
  
- <span data-ttu-id="5376a-149">`float` 또는 `double`을 `decimal`로 변환할 경우 소스 값을 `decimal` 표현으로 변환한 다음 필요한 경우 가장 가까운 소수점 이하 28번째 자리로 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-149">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="5376a-150">소스 값에 따라 다음 결과 중 하나가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-150">Depending on the value of the source value, one of the following results may occur:</span></span>  

  - <span data-ttu-id="5376a-151">소스 값이 너무 작아서 `decimal`로 나타낼 수 없을 경우 결과 값은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-151">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>  

  - <span data-ttu-id="5376a-152">소스 값이 NaN(숫자가 아님), 무한대 또는 너무 커서 `decimal`로 나타낼 수 없을 경우 <xref:System.OverflowException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-152">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an <xref:System.OverflowException> is thrown.</span></span>  
  
- <span data-ttu-id="5376a-153">`decimal`을 `float` 또는 `double`로 변환할 경우 `decimal` 값을 가장 가까운 `double` 또는 `float` 값으로 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="5376a-153">When you convert `decimal` to `float` or `double`, the `decimal` value is rounded to the nearest `double` or `float` value.</span></span>  
  
 <span data-ttu-id="5376a-154">명시적 변환에 대한 자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [명시적 변환](~/_csharplang/spec/conversions.md#explicit-conversions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5376a-154">For more information about explicit conversions, see the [Explicit conversions](~/_csharplang/spec/conversions.md#explicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="5376a-155">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5376a-155">See also</span></span>

- [<span data-ttu-id="5376a-156">C# 참조</span><span class="sxs-lookup"><span data-stu-id="5376a-156">C# reference</span></span>](../index.md)
- [<span data-ttu-id="5376a-157">캐스팅 및 형식 변환</span><span class="sxs-lookup"><span data-stu-id="5376a-157">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
- [<span data-ttu-id="5376a-158">() 연산자</span><span class="sxs-lookup"><span data-stu-id="5376a-158">() operator</span></span>](../operators/type-testing-and-conversion-operators.md#cast-operator-)
- [<span data-ttu-id="5376a-159">정수 형식</span><span class="sxs-lookup"><span data-stu-id="5376a-159">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="5376a-160">부동 소수점 형식 표</span><span class="sxs-lookup"><span data-stu-id="5376a-160">Floating-point types table</span></span>](floating-point-types-table.md)
- [<span data-ttu-id="5376a-161">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="5376a-161">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="5376a-162">암시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="5376a-162">Implicit numeric conversions table</span></span>](implicit-numeric-conversions-table.md)
