---
description: C#의 기본 제공 숫자 형식 간 암시적 및 명시적 변환에 대해 알아봅니다.
title: 기본 제공 숫자 변환 - C# 참조
ms.date: 03/17/2021
helpviewer_keywords:
- implicit numeric conversions [C#]
- explicit numeric conversion [C#]
- numeric conversions [C#], implicit
- numeric conversions [C#], explicit
- conversions [C#], implicit numeric
- conversions [C#], explicit numeric
ms.openlocfilehash: 5ff0289f5365a7d3d334dd0130b3b0efcdf34c60
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759692"
---
# <a name="built-in-numeric-conversions-c-reference"></a><span data-ttu-id="bdb0b-103">기본 제공 숫자 변환(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="bdb0b-103">Built-in numeric conversions (C# reference)</span></span>

<span data-ttu-id="bdb0b-104">C#에서는 [정수](integral-numeric-types.md) 및 [부동 소수점](floating-point-numeric-types.md) 숫자 형식 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-104">C# provides a set of [integral](integral-numeric-types.md) and [floating-point](floating-point-numeric-types.md) numeric types.</span></span> <span data-ttu-id="bdb0b-105">두 숫자 형식 간에는 암시적 또는 명시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-105">There exists a conversion between any two numeric types, either implicit or explicit.</span></span> <span data-ttu-id="bdb0b-106">명시적 변환을 수행하려면 [캐스트 식](../operators/type-testing-and-cast.md#cast-expression) 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-106">You must use a [cast expression](../operators/type-testing-and-cast.md#cast-expression) to perform an explicit conversion.</span></span>

## <a name="implicit-numeric-conversions"></a><span data-ttu-id="bdb0b-107">암시적 숫자 변환</span><span class="sxs-lookup"><span data-stu-id="bdb0b-107">Implicit numeric conversions</span></span>

<span data-ttu-id="bdb0b-108">다음 표에서는 기본 제공 숫자 형식 간의 미리 정의된 암시적 숫자 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-108">The following table shows the predefined implicit conversions between the built-in numeric types:</span></span>

|<span data-ttu-id="bdb0b-109">시작</span><span class="sxs-lookup"><span data-stu-id="bdb0b-109">From</span></span>|<span data-ttu-id="bdb0b-110">대상</span><span class="sxs-lookup"><span data-stu-id="bdb0b-110">To</span></span>|
|----------|--------|
|[<span data-ttu-id="bdb0b-111">sbyte</span><span class="sxs-lookup"><span data-stu-id="bdb0b-111">sbyte</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-112">`short`, `int`, `long`, `float`, `double`, `decimal` 또는 `nint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-112">`short`, `int`, `long`, `float`, `double`, `decimal`, or `nint`</span></span>|
|[<span data-ttu-id="bdb0b-113">byte</span><span class="sxs-lookup"><span data-stu-id="bdb0b-113">byte</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-114">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `nint` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-114">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `nint`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-115">short</span><span class="sxs-lookup"><span data-stu-id="bdb0b-115">short</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-116">`int`, `long`, `float`, `double` 또는 `decimal` 또는 `nint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-116">`int`, `long`, `float`, `double`, or `decimal`, or `nint`</span></span>|
|[<span data-ttu-id="bdb0b-117">ushort</span><span class="sxs-lookup"><span data-stu-id="bdb0b-117">ushort</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-118">`int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`, `nint` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-118">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`, `nint`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-119">int</span><span class="sxs-lookup"><span data-stu-id="bdb0b-119">int</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-120">`long`, `float`, `double` 또는 `decimal`, `nint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-120">`long`, `float`, `double`, or `decimal`, `nint`</span></span>|
|[<span data-ttu-id="bdb0b-121">uint</span><span class="sxs-lookup"><span data-stu-id="bdb0b-121">uint</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-122">`long`, `ulong`, `float`, `double` 또는 `decimal` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-122">`long`, `ulong`, `float`, `double`, or `decimal`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-123">long</span><span class="sxs-lookup"><span data-stu-id="bdb0b-123">long</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-124">`float`, `double`또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-124">`float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="bdb0b-125">ulong</span><span class="sxs-lookup"><span data-stu-id="bdb0b-125">ulong</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-126">`float`, `double`또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-126">`float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="bdb0b-127">float</span><span class="sxs-lookup"><span data-stu-id="bdb0b-127">float</span></span>](floating-point-numeric-types.md)|`double`|
|[<span data-ttu-id="bdb0b-128">nint</span><span class="sxs-lookup"><span data-stu-id="bdb0b-128">nint</span></span>](nint-nuint.md)|<span data-ttu-id="bdb0b-129">`long`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-129">`long`, `float`, `double`, or `decimal`</span></span>|
|[<span data-ttu-id="bdb0b-130">nuint</span><span class="sxs-lookup"><span data-stu-id="bdb0b-130">nuint</span></span>](nint-nuint.md)|<span data-ttu-id="bdb0b-131">`ulong`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-131">`ulong`, `float`, `double`, or `decimal`</span></span>|

> [!NOTE]
> <span data-ttu-id="bdb0b-132">`int`, `uint`, `long`, `ulong`, `nint` 또는 `nuint`에서 `float`로 암시적으로 변환하거나 `long`, `ulong`, `nint` 또는 `nuint`에서 `double`로 암시적으로 변환하는 경우 정밀도가 손실될 수도 있지만, 자릿수 손실은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-132">The implicit conversions from `int`, `uint`, `long`, `ulong`, `nint`, or `nuint` to `float` and from `long`, `ulong`, `nint`, or `nuint` to `double` may cause a loss of precision, but never a loss of an order of magnitude.</span></span> <span data-ttu-id="bdb0b-133">다른 암시적 숫자 변환 시에는 정보 손실이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-133">The other implicit numeric conversions never lose any information.</span></span>

<span data-ttu-id="bdb0b-134">다음 사항에도 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-134">Also note that</span></span>

- <span data-ttu-id="bdb0b-135">[정수 숫자 형식](integral-numeric-types.md)을 [부동 소수점 숫자 형식](floating-point-numeric-types.md)으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-135">Any [integral numeric type](integral-numeric-types.md) is implicitly convertible to any [floating-point numeric type](floating-point-numeric-types.md).</span></span>

- <span data-ttu-id="bdb0b-136">`byte` 및 `sbyte` 형식으로의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-136">There are no implicit conversions to the `byte` and `sbyte` types.</span></span> <span data-ttu-id="bdb0b-137">`double` 및 `decimal` 형식에서 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-137">There are no implicit conversions from the `double` and `decimal` types.</span></span>

- <span data-ttu-id="bdb0b-138">`decimal` 형식과 `float` 또는 `double` 형식 간의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-138">There are no implicit conversions between the `decimal` type and the `float` or `double` types.</span></span>

- <span data-ttu-id="bdb0b-139">대상 형식의 범위 내에 있는 경우 `int` 형식의 상수 식 값(예: 정수 리터럴로 표시된 값)을 `sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`, `nint` 또는 `nuint`으로 암시적으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-139">A value of a constant expression of type `int` (for example, a value represented by an integer literal) can be implicitly converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`, `nint`, or `nuint`, if it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;
  byte b = 300;  // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

  <span data-ttu-id="bdb0b-140">위 예제에서 볼 수 있듯이, 상수 값이 대상 형식의 범위 내에 있지 않으면 컴파일러 오류 [CS0031](../../misc/cs0031.md)이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-140">As the preceding example shows, if the constant value is not within the range of the destination type, a compiler error [CS0031](../../misc/cs0031.md) occurs.</span></span>

## <a name="explicit-numeric-conversions"></a><span data-ttu-id="bdb0b-141">명시적 숫자 변환</span><span class="sxs-lookup"><span data-stu-id="bdb0b-141">Explicit numeric conversions</span></span>

<span data-ttu-id="bdb0b-142">다음 표에서는 [암시적 변환](#implicit-numeric-conversions)이 없는 기본 제공 숫자 형식 간의 미리 정의된 명시적 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-142">The following table shows the predefined explicit conversions between the built-in numeric types for which there is no [implicit conversion](#implicit-numeric-conversions):</span></span>

|<span data-ttu-id="bdb0b-143">시작</span><span class="sxs-lookup"><span data-stu-id="bdb0b-143">From</span></span>|<span data-ttu-id="bdb0b-144">대상</span><span class="sxs-lookup"><span data-stu-id="bdb0b-144">To</span></span>|
|----------|--------|
|[<span data-ttu-id="bdb0b-145">sbyte</span><span class="sxs-lookup"><span data-stu-id="bdb0b-145">sbyte</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-146">`byte`, `ushort`, `uint` 또는 `ulong` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-146">`byte`, `ushort`, `uint`, or `ulong`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-147">byte</span><span class="sxs-lookup"><span data-stu-id="bdb0b-147">byte</span></span>](integral-numeric-types.md)|`sbyte`|
|[<span data-ttu-id="bdb0b-148">short</span><span class="sxs-lookup"><span data-stu-id="bdb0b-148">short</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-149">`sbyte`, `byte`, `ushort`, `uint`, `ulong` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-149">`sbyte`, `byte`, `ushort`, `uint`, `ulong`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-150">ushort</span><span class="sxs-lookup"><span data-stu-id="bdb0b-150">ushort</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-151">`sbyte`, `byte`또는 `short`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-151">`sbyte`, `byte`, or `short`</span></span>|
|[<span data-ttu-id="bdb0b-152">int</span><span class="sxs-lookup"><span data-stu-id="bdb0b-152">int</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-153">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-153">`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-154">uint</span><span class="sxs-lookup"><span data-stu-id="bdb0b-154">uint</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-155">`sbyte`, `byte`, `short`, `ushort` 또는 `int`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-155">`sbyte`, `byte`, `short`, `ushort`, or `int`</span></span>|
|[<span data-ttu-id="bdb0b-156">long</span><span class="sxs-lookup"><span data-stu-id="bdb0b-156">long</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-157">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, `nint` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-157">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, `nint`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-158">ulong</span><span class="sxs-lookup"><span data-stu-id="bdb0b-158">ulong</span></span>](integral-numeric-types.md)|<span data-ttu-id="bdb0b-159">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `nint` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-159">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `nint`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-160">float</span><span class="sxs-lookup"><span data-stu-id="bdb0b-160">float</span></span>](floating-point-numeric-types.md)|<span data-ttu-id="bdb0b-161">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `decimal`, `nint` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-161">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `decimal`, `nint`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-162">double</span><span class="sxs-lookup"><span data-stu-id="bdb0b-162">double</span></span>](floating-point-numeric-types.md)|<span data-ttu-id="bdb0b-163">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `decimal`, `nint` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-163">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `decimal`, `nint`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-164">decimal</span><span class="sxs-lookup"><span data-stu-id="bdb0b-164">decimal</span></span>](floating-point-numeric-types.md)|<span data-ttu-id="bdb0b-165">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `nint` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-165">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `nint`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-166">nint</span><span class="sxs-lookup"><span data-stu-id="bdb0b-166">nint</span></span>](nint-nuint.md)|<span data-ttu-id="bdb0b-167">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` 또는 `nuint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-167">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, or `nuint`</span></span>|
|[<span data-ttu-id="bdb0b-168">nuint</span><span class="sxs-lookup"><span data-stu-id="bdb0b-168">nuint</span></span>](nint-nuint.md)|<span data-ttu-id="bdb0b-169">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` 또는 `nint`</span><span class="sxs-lookup"><span data-stu-id="bdb0b-169">`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, or `nint`</span></span>|

> [!NOTE]
> <span data-ttu-id="bdb0b-170">명시적 숫자 변환으로 인해 데이터가 손실되거나 예외(일반적으로 <xref:System.OverflowException>)가 throw될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-170">An explicit numeric conversion might result in data loss or throw an exception, typically an <xref:System.OverflowException>.</span></span>

<span data-ttu-id="bdb0b-171">다음 사항에도 유의하세요.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-171">Also note that</span></span>

- <span data-ttu-id="bdb0b-172">정수 형식의 값을 다른 정수 형식으로 변환하면 결과는 오버플로 [검사 컨텍스트](../keywords/checked-and-unchecked.md)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-172">When you convert a value of an integral type to another integral type, the result depends on the overflow [checking context](../keywords/checked-and-unchecked.md).</span></span> <span data-ttu-id="bdb0b-173">확인된 컨텍스트에서 소스 값이 대상 형식의 범위 내에 있으면 변환이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-173">In a checked context, the conversion succeeds if the source value is within the range of the destination type.</span></span> <span data-ttu-id="bdb0b-174">그렇지 않으면 <xref:System.OverflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-174">Otherwise, an <xref:System.OverflowException> is thrown.</span></span> <span data-ttu-id="bdb0b-175">확인되지 않은 컨텍스트에서 변환은 항상 성공하고 다음과 같이 진행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-175">In an unchecked context, the conversion always succeeds, and proceeds as follows:</span></span>

  - <span data-ttu-id="bdb0b-176">소스 형식이 대상 형식보다 큰 경우 소스 값은 가장 중요한 비트인 해당 "extra"를 삭제함으로써 잘립니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-176">If the source type is larger than the destination type, then the source value is truncated by discarding its "extra" most significant bits.</span></span> <span data-ttu-id="bdb0b-177">그런 다음, 결과는 대상 형식의 값으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-177">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="bdb0b-178">소스 형식이 대상 형식보다 작은 경우 소스 값이 대상 형식과 크기가 같도록 부호 확장 또는 0 확장됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-178">If the source type is smaller than the destination type, then the source value is either sign-extended or zero-extended so that it's of the same size as the destination type.</span></span> <span data-ttu-id="bdb0b-179">부호 확장은 소스 형식이 서명된 경우 사용되며, 소스 형식이 서명되지 않은 경우 0 확장이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-179">Sign-extension is used if the source type is signed; zero-extension is used if the source type is unsigned.</span></span> <span data-ttu-id="bdb0b-180">그런 다음, 결과는 대상 형식의 값으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-180">The result is then treated as a value of the destination type.</span></span>

  - <span data-ttu-id="bdb0b-181">소스 형식이 대상 형식과 동일한 크기인 경우 소스 값은 대상 형식의 값으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-181">If the source type is the same size as the destination type, then the source value is treated as a value of the destination type.</span></span>

- <span data-ttu-id="bdb0b-182">`decimal` 값을 정수 형식으로 변환하면, 이 값은 0을 향한 방향으로 가장 가까운 정수값으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-182">When you convert a `decimal` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="bdb0b-183">결과 정수 값이 대상 형식 범위에서 벗어났을 경우 <xref:System.OverflowException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-183">If the resulting integral value is outside the range of the destination type, an <xref:System.OverflowException> is thrown.</span></span>

- <span data-ttu-id="bdb0b-184">`double` 또는 `float` 값을 정수 형식으로 변환하면, 이 값은 0을 향한 방향으로 가장 가까운 정수값으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-184">When you convert a `double` or `float` value to an integral type, this value is rounded towards zero to the nearest integral value.</span></span> <span data-ttu-id="bdb0b-185">결과 정수 값이 대상 형식 범위에서 벗어났을 경우 결과는 오버플로 [검사 컨텍스트](../keywords/checked-and-unchecked.md)에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-185">If the resulting integral value is outside the range of the destination type, the result depends on the overflow [checking context](../keywords/checked-and-unchecked.md).</span></span> <span data-ttu-id="bdb0b-186">Checked 컨텍스트에서는 <xref:System.OverflowException>이 throw됩니다. 반면 Unchecked 컨텍스트에서 결과는 지정되지 않은 대상 형식 값이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-186">In a checked context, an <xref:System.OverflowException> is thrown, while in an unchecked context, the result is an unspecified value of the destination type.</span></span>

- <span data-ttu-id="bdb0b-187">`double`을 `float`로 변환할 경우 `double` 값을 가장 가까운 `float` 값으로 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-187">When you convert `double` to `float`, the `double` value is rounded to the nearest `float` value.</span></span> <span data-ttu-id="bdb0b-188">`double` 값이 너무 크거나 작아서 `float` 형식에 맞지 않는 경우 결과 값은 0 또는 무한대가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-188">If the `double` value is too small or too large to fit into the `float` type, the result is zero or infinity.</span></span>

- <span data-ttu-id="bdb0b-189">`float` 또는 `double`을 `decimal`로 변환할 경우 소스 값을 `decimal` 표현으로 변환한 다음 필요한 경우 가장 가까운 소수점 이하 28번째 자리로 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-189">When you convert `float` or `double` to `decimal`, the source value is converted to `decimal` representation and rounded to the nearest number after the 28th decimal place if required.</span></span> <span data-ttu-id="bdb0b-190">소스 값에 따라 다음 결과 중 하나가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-190">Depending on the value of the source value, one of the following results may occur:</span></span>

  - <span data-ttu-id="bdb0b-191">소스 값이 너무 작아서 `decimal`로 나타낼 수 없을 경우 결과 값은 0이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-191">If the source value is too small to be represented as a `decimal`, the result becomes zero.</span></span>

  - <span data-ttu-id="bdb0b-192">소스 값이 NaN(숫자가 아님), 무한대 또는 너무 커서 `decimal`로 나타낼 수 없을 경우 <xref:System.OverflowException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-192">If the source value is NaN (not a number), infinity, or too large to be represented as a `decimal`, an <xref:System.OverflowException> is thrown.</span></span>

- <span data-ttu-id="bdb0b-193">`decimal`을 `float` 또는 `double`로 변환하는 경우 소스 값이 각각 가장 가까운 `float` 또는 `double` 값으로 반올림됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-193">When you convert `decimal` to `float` or `double`, the source value is rounded to the nearest `float` or `double` value, respectively.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="bdb0b-194">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="bdb0b-194">C# language specification</span></span>

<span data-ttu-id="bdb0b-195">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bdb0b-195">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="bdb0b-196">암시적 숫자 변환</span><span class="sxs-lookup"><span data-stu-id="bdb0b-196">Implicit numeric conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-numeric-conversions)
- [<span data-ttu-id="bdb0b-197">명시적 숫자 변환</span><span class="sxs-lookup"><span data-stu-id="bdb0b-197">Explicit numeric conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-numeric-conversions)

## <a name="see-also"></a><span data-ttu-id="bdb0b-198">참조</span><span class="sxs-lookup"><span data-stu-id="bdb0b-198">See also</span></span>

- [<span data-ttu-id="bdb0b-199">C# 참조</span><span class="sxs-lookup"><span data-stu-id="bdb0b-199">C# reference</span></span>](../index.md)
- [<span data-ttu-id="bdb0b-200">캐스팅 및 형식 변환</span><span class="sxs-lookup"><span data-stu-id="bdb0b-200">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
