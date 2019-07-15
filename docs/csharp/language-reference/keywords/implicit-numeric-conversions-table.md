---
title: 암시적 숫자 변환 표 - C# 참조
ms.custom: seodec18
ms.date: 09/05/2018
helpviewer_keywords:
- conversions [C#], implicit numeric
- implicit numeric conversions [C#]
- numeric conversions [C#], implicit
- types [C#], implicit numeric conversions
ms.assetid: 72eb5a94-0491-48bf-8032-d7ebfdfeb8d8
ms.openlocfilehash: 516505ccacfd2a8a5c275b0de033e1316fa06d3a
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661330"
---
# <a name="implicit-numeric-conversions-table-c-reference"></a><span data-ttu-id="b627c-102">암시적 숫자 변환 표(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="b627c-102">Implicit numeric conversions table (C# Reference)</span></span>

<span data-ttu-id="b627c-103">다음 표에서는 .NET 숫자 형식 간의 미리 정의된 암시적 숫자 변환을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-103">The following table shows the predefined implicit conversions between .NET numeric types.</span></span>
  
|<span data-ttu-id="b627c-104">시작</span><span class="sxs-lookup"><span data-stu-id="b627c-104">From</span></span>|<span data-ttu-id="b627c-105">대상</span><span class="sxs-lookup"><span data-stu-id="b627c-105">To</span></span>|  
|----------|--------|  
|[<span data-ttu-id="b627c-106">sbyte</span><span class="sxs-lookup"><span data-stu-id="b627c-106">sbyte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="b627c-107">`short`, `int`, `long`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="b627c-107">`short`, `int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="b627c-108">byte</span><span class="sxs-lookup"><span data-stu-id="b627c-108">byte</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="b627c-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="b627c-109">`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="b627c-110">char</span><span class="sxs-lookup"><span data-stu-id="b627c-110">char</span></span>](char.md)|<span data-ttu-id="b627c-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="b627c-111">`ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="b627c-112">short</span><span class="sxs-lookup"><span data-stu-id="b627c-112">short</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="b627c-113">`int`, `long`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="b627c-113">`int`, `long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="b627c-114">ushort</span><span class="sxs-lookup"><span data-stu-id="b627c-114">ushort</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="b627c-115">`int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="b627c-115">`int`, `uint`, `long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="b627c-116">int</span><span class="sxs-lookup"><span data-stu-id="b627c-116">int</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="b627c-117">`long`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="b627c-117">`long`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="b627c-118">uint</span><span class="sxs-lookup"><span data-stu-id="b627c-118">uint</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="b627c-119">`long`, `ulong`, `float`, `double` 또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="b627c-119">`long`, `ulong`, `float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="b627c-120">long</span><span class="sxs-lookup"><span data-stu-id="b627c-120">long</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="b627c-121">`float`, `double`또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="b627c-121">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="b627c-122">ulong</span><span class="sxs-lookup"><span data-stu-id="b627c-122">ulong</span></span>](../builtin-types/integral-numeric-types.md)|<span data-ttu-id="b627c-123">`float`, `double`또는 `decimal`</span><span class="sxs-lookup"><span data-stu-id="b627c-123">`float`, `double`, or `decimal`</span></span>|  
|[<span data-ttu-id="b627c-124">float</span><span class="sxs-lookup"><span data-stu-id="b627c-124">float</span></span>](../builtin-types/floating-point-numeric-types.md)|`double`|  
  
## <a name="remarks"></a><span data-ttu-id="b627c-125">설명</span><span class="sxs-lookup"><span data-stu-id="b627c-125">Remarks</span></span>  

- <span data-ttu-id="b627c-126">모든 [정수 형식](../builtin-types/integral-numeric-types.md)은 암시적으로 모든 [부동 소수점 형식](../builtin-types/floating-point-numeric-types.md)으로 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-126">Any [integral type](../builtin-types/integral-numeric-types.md) is implicitly convertible to any [floating-point type](../builtin-types/floating-point-numeric-types.md).</span></span>

- <span data-ttu-id="b627c-127">`int`, `uint`, `long` 또는 `ulong`에서 `float`로 변환하고 `long` 또는 `ulong`에서 `double`로 변환하는 동안 전체 자릿수가 손실될 수도 있지만 크기는 손실되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-127">Precision but not magnitude might be lost in the conversions from `int`, `uint`, `long`, or `ulong` to `float` and from `long` or `ulong` to `double`.</span></span>  
  
- <span data-ttu-id="b627c-128">`char`, `byte` 및 `sbyte` 형식으로 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-128">There are no implicit conversions to the `char`, `byte`, and `sbyte` types.</span></span>  

- <span data-ttu-id="b627c-129">`double` 및 `decimal` 형식에서 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-129">There are no implicit conversions from the `double` and `decimal` types.</span></span>
  
- <span data-ttu-id="b627c-130">`decimal` 형식과 `float` 또는 `double` 형식 간의 암시적 변환은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-130">There are no implicit conversions between the `decimal` type and the `float` or `double` types.</span></span>  
  
- <span data-ttu-id="b627c-131">형식 `int`의 상수 식 값(예: 정수 리터럴로 표시되는 값)은 대상 형식 범위 내에 있는 `sbyte`, `byte`, `short`, `ushort`, `uint` 또는 `ulong`으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b627c-131">A value of a constant expression of type `int` (for example, a value represented by an integral literal) can be converted to `sbyte`, `byte`, `short`, `ushort`, `uint`, or `ulong`, provided it's within the range of the destination type:</span></span>

  ```csharp
  byte a = 13;    // Compiles
  byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

<span data-ttu-id="b627c-132">암시적 변환에 대한 자세한 내용은 [C# 언어 사양](../language-specification/index.md)의 [암시적 변환](~/_csharplang/spec/conversions.md#implicit-conversions) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b627c-132">For more information about implicit conversions, see the [Implicit conversions](~/_csharplang/spec/conversions.md#implicit-conversions) section of the [C# language specification](../language-specification/index.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b627c-133">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b627c-133">See also</span></span>

- [<span data-ttu-id="b627c-134">C# 참조</span><span class="sxs-lookup"><span data-stu-id="b627c-134">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="b627c-135">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="b627c-135">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="b627c-136">정수 형식</span><span class="sxs-lookup"><span data-stu-id="b627c-136">Integral types</span></span>](../builtin-types/integral-numeric-types.md)
- [<span data-ttu-id="b627c-137">부동 소수점 형식 표</span><span class="sxs-lookup"><span data-stu-id="b627c-137">Floating-point types table</span></span>](../builtin-types/floating-point-numeric-types.md)
- [<span data-ttu-id="b627c-138">기본 제공 형식 표</span><span class="sxs-lookup"><span data-stu-id="b627c-138">Built-in types table</span></span>](built-in-types-table.md)
- [<span data-ttu-id="b627c-139">명시적 숫자 변환 표</span><span class="sxs-lookup"><span data-stu-id="b627c-139">Explicit numeric conversions table</span></span>](explicit-numeric-conversions-table.md)
- [<span data-ttu-id="b627c-140">캐스팅 및 형식 변환</span><span class="sxs-lookup"><span data-stu-id="b627c-140">Casting and type conversions</span></span>](../../programming-guide/types/casting-and-type-conversions.md)
