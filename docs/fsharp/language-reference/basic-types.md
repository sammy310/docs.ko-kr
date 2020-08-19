---
title: 기본 형식
description: 'F # 언어에서 사용 되는 기본 기본 형식을 검색 합니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 659ac8424c62985affcca1741e1b2a74c9c3ee8d
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557700"
---
# <a name="basic-types"></a><span data-ttu-id="2eac6-103">기본 형식</span><span class="sxs-lookup"><span data-stu-id="2eac6-103">Basic types</span></span>

<span data-ttu-id="2eac6-104">이 항목에서는 F # 언어에 정의 된 기본 형식을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="2eac6-105">이러한 형식은 F #에서 가장 기본적인 것 이며 거의 모든 F # 프로그램의 기본을 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="2eac6-106">.NET 기본 형식의 상위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="2eac6-107">Type</span><span class="sxs-lookup"><span data-stu-id="2eac6-107">Type</span></span>|<span data-ttu-id="2eac6-108">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="2eac6-108">.NET type</span></span>|<span data-ttu-id="2eac6-109">Description</span><span class="sxs-lookup"><span data-stu-id="2eac6-109">Description</span></span>|<span data-ttu-id="2eac6-110">예제</span><span class="sxs-lookup"><span data-stu-id="2eac6-110">Example</span></span>|
|----|---------|-----------|-------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="2eac6-111">가능한 값은 `true` 및 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-111">Possible values are `true` and `false`.</span></span>|`true`/`false`|
|`byte`|<xref:System.Byte>|<span data-ttu-id="2eac6-112">0에서 255 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-112">Values from 0 to 255.</span></span>|`1uy`|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="2eac6-113">값은-128에서 127 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-113">Values from -128 to 127.</span></span>|`1y`|
|`int16`|<xref:System.Int16>|<span data-ttu-id="2eac6-114">값은-32768에서 32767 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-114">Values from -32768 to 32767.</span></span>|`1s`|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="2eac6-115">0에서 65535 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-115">Values from 0 to 65535.</span></span>|`1us`|
|`int`|<xref:System.Int32>|<span data-ttu-id="2eac6-116">값은-2147483648에서 2147483647 사이입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-116">Values from -2,147,483,648 to 2,147,483,647.</span></span>|`1`|
|`uint`|<xref:System.UInt32>|<span data-ttu-id="2eac6-117">0에서 4294967295 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-117">Values from 0 to 4,294,967,295.</span></span>|`1u`|
|`int64`|<xref:System.Int64>|<span data-ttu-id="2eac6-118">-9223372036854775808에서 9223372036854775807 까지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-118">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|`1L`|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="2eac6-119">0에서 18446744073709551615 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-119">Values from 0 to 18,446,744,073,709,551,615.</span></span>|`1UL`|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="2eac6-120">부호 있는 정수에 해당 하는 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-120">A native pointer as a signed integer.</span></span>|`nativeint 1`|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="2eac6-121">부호 없는 정수 인 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-121">A native pointer as an unsigned integer.</span></span>|`unativeint 1`|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="2eac6-122">유효 자릿수가 28 개 이상인 부동 소수점 데이터 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-122">A floating point data type that has at least 28 significant digits.</span></span>|`1.0`|
|<span data-ttu-id="2eac6-123">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="2eac6-123">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="2eac6-124">64 비트 부동 소수점 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-124">A 64-bit floating point type.</span></span>|`1.0`|
|<span data-ttu-id="2eac6-125">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="2eac6-125">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="2eac6-126">32 비트 부동 소수점 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-126">A 32-bit floating point type.</span></span>|`1.0f`|
|`char`|<xref:System.Char>|<span data-ttu-id="2eac6-127">유니코드 문자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-127">Unicode character values.</span></span>|`'c'`|
|`string`|<xref:System.String>|<span data-ttu-id="2eac6-128">유니코드 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-128">Unicode text.</span></span>|`"str"`|
|`unit`|<span data-ttu-id="2eac6-129">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="2eac6-129">not applicable</span></span>|<span data-ttu-id="2eac6-130">실제 값이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-130">Indicates the absence of an actual value.</span></span> <span data-ttu-id="2eac6-131">형식에는로 표시 되는 하나의 형식 값만 있습니다 `()` .</span><span class="sxs-lookup"><span data-stu-id="2eac6-131">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="2eac6-132">단위 값은 `()` 일반적으로 값이 필요한 자리 표시자로 사용 되지만 실제 값을 사용할 수 없거나 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-132">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|`()`|

> [!NOTE]
> <span data-ttu-id="2eac6-133">[Bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html) 형식을 사용 하 여 64 비트 정수 형식에 대해 너무 큰 정수를 사용 하 여 계산을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2eac6-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-bigint.html) type.</span></span> <span data-ttu-id="2eac6-134">`bigint` 는 기본 형식으로 간주 되지 않습니다. 의 약어입니다 `System.Numerics.BigInteger` .</span><span class="sxs-lookup"><span data-stu-id="2eac6-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="2eac6-135">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2eac6-135">See also</span></span>

- [<span data-ttu-id="2eac6-136">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="2eac6-136">F# Language Reference</span></span>](index.md)
