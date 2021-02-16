---
description: '자세한 정보: 암시적 변환과 명시적 변환 (Visual Basic)'
title: 암시적 변환과 명시적 변환
ms.date: 07/20/2015
helpviewer_keywords:
- conversions [Visual Basic], type
- variables [Visual Basic], changing data type
- casting
- conversions [Visual Basic], data type
- type conversion [Visual Basic], implicit conversions
- CType function [Visual Basic], conversions
- casting, data types
- data type conversion [Visual Basic], explicit
- type conversion [Visual Basic], explicit conversions
- data types [Visual Basic], casting
- conversions [Visual Basic], implicit
- explicit data type conversions [Visual Basic]
- conversions [Visual Basic]
- changing data types [Visual Basic]
- conversions [Visual Basic], explicit
- data type conversion [Visual Basic], implicit
- implicit data type conversions [Visual Basic]
ms.assetid: 77de1659-af8a-492c-967e-e7ef60ccce66
ms.openlocfilehash: 6a53c0998025cc8c19274c67d9dfe1c50a4f1373
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100483952"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="c7040-103">암시적 변환과 명시적 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c7040-103">Implicit and Explicit Conversions (Visual Basic)</span></span>

<span data-ttu-id="c7040-104">*암시적 변환* 에는 소스 코드에 특별 한 구문이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-104">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="c7040-105">다음 예제에서는 `k` 를에 할당 하기 전에 Visual Basic의 값을 단 정밀도 부동 소수점 값으로 암시적으로 변환 `q` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-105">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

<span data-ttu-id="c7040-106">*명시적 변환은* 형식 변환 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-106">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="c7040-107">Visual Basic는 괄호 안의 식을 원하는 데이터 형식으로 강제 변환 하는 몇 가지 키워드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-107">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="c7040-108">이러한 키워드는 함수 처럼 동작 하지만 컴파일러가 코드를 인라인으로 생성 하므로 함수 호출을 사용 하는 것 보다 약간 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-108">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>

<span data-ttu-id="c7040-109">위의 예에서는 다음 확장에서 `CInt` 키워드는 `q` 를에 할당 하기 전에 값을 다시 정수로 변환 `k` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-109">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a><span data-ttu-id="c7040-110">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="c7040-110">Conversion Keywords</span></span>

<span data-ttu-id="c7040-111">다음 표에서는 사용 가능한 변환 키워드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-111">The following table shows the available conversion keywords.</span></span>

|<span data-ttu-id="c7040-112">형식 변환 키워드</span><span class="sxs-lookup"><span data-stu-id="c7040-112">Type conversion keyword</span></span>|<span data-ttu-id="c7040-113">식을 데이터 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-113">Converts an expression to data type</span></span>|<span data-ttu-id="c7040-114">변환할 수 있는 식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-114">Allowable data types of expression to be converted</span></span>|
|---|---|---|
|`CBool`|[<span data-ttu-id="c7040-115">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-115">Boolean Data Type</span></span>](../../../language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="c7040-116">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-116">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|
|`CByte`|[<span data-ttu-id="c7040-117">Byte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-117">Byte Data Type</span></span>](../../../language-reference/data-types/byte-data-type.md)|<span data-ttu-id="c7040-118">모든 숫자 형식 ( `SByte` 및 열거 형식 포함), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-118">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CChar`|[<span data-ttu-id="c7040-119">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-119">Char Data Type</span></span>](../../../language-reference/data-types/char-data-type.md)|<span data-ttu-id="c7040-120">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-120">`String`, `Object`</span></span>|
|`CDate`|[<span data-ttu-id="c7040-121">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-121">Date Data Type</span></span>](../../../language-reference/data-types/date-data-type.md)|<span data-ttu-id="c7040-122">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-122">`String`, `Object`</span></span>|
|`CDbl`|[<span data-ttu-id="c7040-123">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-123">Double Data Type</span></span>](../../../language-reference/data-types/double-data-type.md)|<span data-ttu-id="c7040-124">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` ,, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-124">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CDec`|[<span data-ttu-id="c7040-125">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-125">Decimal Data Type</span></span>](../../../language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="c7040-126">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` ,, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-126">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CInt`|[<span data-ttu-id="c7040-127">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-127">Integer Data Type</span></span>](../../../language-reference/data-types/integer-data-type.md)|<span data-ttu-id="c7040-128">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` ,, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-128">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CLng`|[<span data-ttu-id="c7040-129">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-129">Long Data Type</span></span>](../../../language-reference/data-types/long-data-type.md)|<span data-ttu-id="c7040-130">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` ,, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-130">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CObj`|[<span data-ttu-id="c7040-131">Object Data Type</span><span class="sxs-lookup"><span data-stu-id="c7040-131">Object Data Type</span></span>](../../../language-reference/data-types/object-data-type.md)|<span data-ttu-id="c7040-132">모든 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-132">Any type</span></span>|
|`CSByte`|[<span data-ttu-id="c7040-133">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-133">SByte Data Type</span></span>](../../../language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="c7040-134">모든 숫자 형식 ( `Byte` 및 열거 형식 포함), `Boolean` , `String` , `Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-134">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CShort`|[<span data-ttu-id="c7040-135">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-135">Short Data Type</span></span>](../../../language-reference/data-types/short-data-type.md)|<span data-ttu-id="c7040-136">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` ,, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-136">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CSng`|[<span data-ttu-id="c7040-137">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-137">Single Data Type</span></span>](../../../language-reference/data-types/single-data-type.md)|<span data-ttu-id="c7040-138">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` ,, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-138">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CStr`|[<span data-ttu-id="c7040-139">문자열 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-139">String Data Type</span></span>](../../../language-reference/data-types/string-data-type.md)|<span data-ttu-id="c7040-140">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` , `Char` , `Char` array, `Date` , `Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-140">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|
|`CType`|<span data-ttu-id="c7040-141">쉼표 () 뒤에 지정 된 형식 `,`</span><span class="sxs-lookup"><span data-stu-id="c7040-141">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="c7040-142">기본 *데이터 형식* (기본 형식의 배열 포함)으로 변환 하는 경우 해당 변환 키워드에 대해 허용 되는 것과 동일한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-142">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="c7040-143">*복합 데이터 형식* 으로 변환 하는 경우, 구현 하는 인터페이스 및 해당 형식이 상속 하는 클래스</span><span class="sxs-lookup"><span data-stu-id="c7040-143">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="c7040-144">오버 로드 된 클래스 또는 구조체 `CType` (해당 클래스 또는 구조체)로 변환 하는 경우</span><span class="sxs-lookup"><span data-stu-id="c7040-144">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|
|`CUInt`|[<span data-ttu-id="c7040-145">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-145">UInteger Data Type</span></span>](../../../language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="c7040-146">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` ,, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-146">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CULng`|[<span data-ttu-id="c7040-147">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-147">ULong Data Type</span></span>](../../../language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="c7040-148">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` ,, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-148">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CUShort`|[<span data-ttu-id="c7040-149">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-149">UShort Data Type</span></span>](../../../language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="c7040-150">모든 숫자 형식 ( `Byte` , `SByte` , 열거형 형식 포함), `Boolean` ,, `String``Object`</span><span class="sxs-lookup"><span data-stu-id="c7040-150">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|

## <a name="the-ctype-function"></a><span data-ttu-id="c7040-151">CType 함수</span><span class="sxs-lookup"><span data-stu-id="c7040-151">The CType Function</span></span>

<span data-ttu-id="c7040-152">[CType 함수](../../../language-reference/functions/ctype-function.md) 는 두 인수에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-152">The [CType Function](../../../language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="c7040-153">첫 번째는 변환할 식이고 두 번째는 대상 데이터 형식 또는 개체 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-153">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="c7040-154">첫 번째 인수는 형식이 아니라 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-154">Note that the first argument must be an expression, not a type.</span></span>

<span data-ttu-id="c7040-155">`CType` 는 *인라인 함수* 입니다. 즉, 컴파일 코드에서 함수 호출을 생성 하지 않고 변환을 수행 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-155">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="c7040-156">이렇게 하면 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-156">This improves performance.</span></span>

<span data-ttu-id="c7040-157">를 `CType` 다른 형식 변환 키워드와 비교 하려면 [DirectCast Operator](../../../language-reference/operators/directcast-operator.md) 및 [TryCast operator](../../../language-reference/operators/trycast-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7040-157">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../language-reference/operators/trycast-operator.md).</span></span>

### <a name="elementary-types"></a><span data-ttu-id="c7040-158">기본 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-158">Elementary Types</span></span>

<span data-ttu-id="c7040-159">다음 예에서는 `CType`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-159">The following example demonstrates the use of `CType`.</span></span>

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a><span data-ttu-id="c7040-160">복합 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-160">Composite Types</span></span>

<span data-ttu-id="c7040-161">를 사용 하 여 `CType` 값을 복합 데이터 형식 및 기본 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-161">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="c7040-162">다음 예제와 같이이를 사용 하 여 개체 클래스를 해당 인터페이스 중 하나의 형식으로 강제 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-162">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a><span data-ttu-id="c7040-163">배열 유형</span><span class="sxs-lookup"><span data-stu-id="c7040-163">Array Types</span></span>

<span data-ttu-id="c7040-164">`CType` 는 다음 예제와 같이 배열 데이터 형식을 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-164">`CType` can also convert array data types, as in the following example.</span></span>

```vb
Dim v() As classV
Dim obArray() As Object
' Assume some object array has been assigned to obArray.
' Check for run-time type compatibility.
If TypeOf obArray Is classV()
    ' obArray can be converted to classV.
    v = CType(obArray, classV())
End If
```

<span data-ttu-id="c7040-165">자세한 내용 및 예제는 [배열 변환](array-conversions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7040-165">For more information and an example, see [Array Conversions](array-conversions.md).</span></span>

### <a name="types-defining-ctype"></a><span data-ttu-id="c7040-166">CType을 정의 하는 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-166">Types Defining CType</span></span>

<span data-ttu-id="c7040-167">`CType`정의한 클래스 또는 구조체를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-167">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="c7040-168">이를 통해 클래스 또는 구조체의 형식으로 값을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-168">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="c7040-169">자세한 내용 및 예제는 [방법: 변환 연산자 정의](../procedures/how-to-define-a-conversion-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7040-169">For more information and an example, see [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c7040-170">변환 키워드와 함께 사용 되는 값은 대상 데이터 형식에 대해 유효 해야 합니다. 그렇지 않으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-170">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="c7040-171">예를 들어를로 변환 하려고 하면 `Long` `Integer` 의 값이 `Long` 데이터 형식에 대 한 유효한 범위 내에 있어야 합니다 `Integer` .</span><span class="sxs-lookup"><span data-stu-id="c7040-171">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>

> [!CAUTION]
> <span data-ttu-id="c7040-172">`CType`소스 형식이 대상 형식에서 파생 되지 않은 경우 런타임에 한 클래스 형식에서 다른 형식으로 변환 하는 작업이 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-172">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="c7040-173">이러한 오류는 예외를 throw <xref:System.InvalidCastException> 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-173">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="c7040-174">그러나 형식 중 하나가 정의 된 구조체 또는 클래스이 고 `CType` 해당 구조체 또는 클래스에서를 정의한 경우의 요구 사항을 충족 하는 경우 변환이 성공할 수 있습니다 `CType` .</span><span class="sxs-lookup"><span data-stu-id="c7040-174">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="c7040-175">[방법: 변환 연산자 정의를](../procedures/how-to-define-a-conversion-operator.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c7040-175">See [How to: Define a Conversion Operator](../procedures/how-to-define-a-conversion-operator.md).</span></span>

<span data-ttu-id="c7040-176">명시적 변환을 수행 하는 것은 지정 된 데이터 형식 또는 개체 클래스로 식을 *캐스팅* 하는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7040-176">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>

## <a name="see-also"></a><span data-ttu-id="c7040-177">추가 정보</span><span class="sxs-lookup"><span data-stu-id="c7040-177">See also</span></span>

- [<span data-ttu-id="c7040-178">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="c7040-178">Type Conversions in Visual Basic</span></span>](type-conversions.md)
- [<span data-ttu-id="c7040-179">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="c7040-179">Conversions Between Strings and Other Types</span></span>](conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="c7040-180">방법: Visual Basic에서 Object를 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="c7040-180">How to: Convert an Object to Another Type in Visual Basic</span></span>](how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="c7040-181">구조체</span><span class="sxs-lookup"><span data-stu-id="c7040-181">Structures</span></span>](structures.md)
- [<span data-ttu-id="c7040-182">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="c7040-182">Data Types</span></span>](../../../language-reference/data-types/index.md)
- [<span data-ttu-id="c7040-183">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="c7040-183">Type Conversion Functions</span></span>](../../../language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="c7040-184">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="c7040-184">Troubleshooting Data Types</span></span>](troubleshooting-data-types.md)
