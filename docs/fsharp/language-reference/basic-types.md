---
title: 기본 형식
description: 에 사용 되는 기본 기본 형식을 검색 합니다 F# 언어입니다.
ms.date: 07/09/2018
ms.openlocfilehash: fb9f275490cb402ff36e959774cd65450de77115
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645596"
---
# <a name="basic-types"></a><span data-ttu-id="6fb0d-103">기본 형식</span><span class="sxs-lookup"><span data-stu-id="6fb0d-103">Basic types</span></span>

<span data-ttu-id="6fb0d-104">이 항목에 정의 된 기본 유형을 나열 합니다 F# 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-104">This topic lists the basic types that are defined in the F# language.</span></span> <span data-ttu-id="6fb0d-105">이러한 유형은에서 가장 기본적인 F#, 거의 모든의 토대를 형성할 F# 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-105">These types are the most fundamental in F#, forming the basis of nearly every F# program.</span></span> <span data-ttu-id="6fb0d-106">이들은.NET 기본 형식의 상위 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-106">They are a superset of .NET primitive types.</span></span>

|<span data-ttu-id="6fb0d-107">형식</span><span class="sxs-lookup"><span data-stu-id="6fb0d-107">Type</span></span>|<span data-ttu-id="6fb0d-108">.NET 형식</span><span class="sxs-lookup"><span data-stu-id="6fb0d-108">.NET type</span></span>|<span data-ttu-id="6fb0d-109">설명</span><span class="sxs-lookup"><span data-stu-id="6fb0d-109">Description</span></span>|
|----|---------|-----------|
|`bool`|<xref:System.Boolean>|<span data-ttu-id="6fb0d-110">가능한 값은 `true`와 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-110">Possible values are `true` and `false`.</span></span>|
|`byte`|<xref:System.Byte>|<span data-ttu-id="6fb0d-111">0에서 255 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-111">Values from 0 to 255.</span></span>|
|`sbyte`|<xref:System.SByte>|<span data-ttu-id="6fb0d-112">-128에서 127 까지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-112">Values from -128 to 127.</span></span>|
|`int16`|<xref:System.Int16>|<span data-ttu-id="6fb0d-113">-32768에서 32767 까지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-113">Values from -32768 to 32767.</span></span>|
|`uint16`|<xref:System.UInt16>|<span data-ttu-id="6fb0d-114">0에서 65535 까지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-114">Values from 0 to 65535.</span></span>|
|`int`|<xref:System.Int32>|<span data-ttu-id="6fb0d-115">-2,147,483,648에서 2,147,483,647 까지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-115">Values from -2,147,483,648 to 2,147,483,647.</span></span>|
|`uint32`|<xref:System.UInt32>|<span data-ttu-id="6fb0d-116">0에서 4,294,967,295 사이의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-116">Values from 0 to 4,294,967,295.</span></span>|
|`int64`|<xref:System.Int64>|<span data-ttu-id="6fb0d-117">-9223372036854775808 때문에 9,223,372,036,854,775,807 까지의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-117">Values from -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807.</span></span>|
|`uint64`|<xref:System.UInt64>|<span data-ttu-id="6fb0d-118">0에서 18446744073709551615 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-118">Values from 0 to 18,446,744,073,709,551,615.</span></span>|
|`nativeint`|<xref:System.IntPtr>|<span data-ttu-id="6fb0d-119">부호 있는 정수로 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-119">A native pointer as a signed integer.</span></span>|
|`unativeint`|<xref:System.UIntPtr>|<span data-ttu-id="6fb0d-120">부호 없는 정수는 네이티브 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-120">A native pointer as an unsigned integer.</span></span>|
|`char`|<xref:System.Char>|<span data-ttu-id="6fb0d-121">유니코드 문자 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-121">Unicode character values.</span></span>|
|`string`|<xref:System.String>|<span data-ttu-id="6fb0d-122">유니코드 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-122">Unicode text.</span></span>|
|`decimal`|<xref:System.Decimal>|<span data-ttu-id="6fb0d-123">부동 소수점 데이터 형식에 적어도 28 개의 유효 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-123">A floating point data type that has at least 28 significant digits.</span></span>|
|`unit`|<span data-ttu-id="6fb0d-124">적용할 수 없음</span><span class="sxs-lookup"><span data-stu-id="6fb0d-124">not applicable</span></span>|<span data-ttu-id="6fb0d-125">실제 값이 없음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-125">Indicates the absence of an actual value.</span></span> <span data-ttu-id="6fb0d-126">형식에 표시 되는 정식 값 하나만 `()`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-126">The type has only one formal value, which is denoted `()`.</span></span> <span data-ttu-id="6fb0d-127">단위 값 `()`, 여기서는 값이 필요 하지만 실제 값 수 또는 적합 한 자리 표시자로 흔히 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-127">The unit value, `()`, is often used as a placeholder where a value is needed but no real value is available or makes sense.</span></span>|
|`void`|<xref:System.Void>|<span data-ttu-id="6fb0d-128">없는 형식 또는 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-128">Indicates no type or value.</span></span>|
|<span data-ttu-id="6fb0d-129">`float32`, `single`</span><span class="sxs-lookup"><span data-stu-id="6fb0d-129">`float32`, `single`</span></span>|<xref:System.Single>|<span data-ttu-id="6fb0d-130">32 비트 부동 소수점 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-130">A 32-bit floating point type.</span></span>|
|<span data-ttu-id="6fb0d-131">`float`, `double`</span><span class="sxs-lookup"><span data-stu-id="6fb0d-131">`float`, `double`</span></span>|<xref:System.Double>|<span data-ttu-id="6fb0d-132">64 비트 부동 소수점 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-132">A 64-bit floating point type.</span></span>|

> [!NOTE]
> <span data-ttu-id="6fb0d-133">사용 하 여 64 비트 정수 형식에 대해 너무 큰 정수를 사용 하 여 계산을 수행할 수 있습니다 합니다 [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-133">You can perform computations with integers too big for the 64-bit integer type by using the [bigint](https://msdn.microsoft.com/library/dc8be18d-4042-46c4-b136-2f21a84f6efa) type.</span></span> <span data-ttu-id="6fb0d-134">`bigint` 기본 형식으로 간주 되지 않습니다. 약어 `System.Numerics.BigInteger`합니다.</span><span class="sxs-lookup"><span data-stu-id="6fb0d-134">`bigint` is not considered a basic type; it is an abbreviation for `System.Numerics.BigInteger`.</span></span>

## <a name="see-also"></a><span data-ttu-id="6fb0d-135">참고자료</span><span class="sxs-lookup"><span data-stu-id="6fb0d-135">See also</span></span>

- [<span data-ttu-id="6fb0d-136">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="6fb0d-136">F# Language Reference</span></span>](index.md)
