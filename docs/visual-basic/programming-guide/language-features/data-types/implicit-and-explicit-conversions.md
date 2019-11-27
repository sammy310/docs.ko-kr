---
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
ms.openlocfilehash: b7215933cec89b7023f08e8996a283b39b3a3c83
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346366"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="51c14-102">암시적 변환과 명시적 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="51c14-102">Implicit and Explicit Conversions (Visual Basic)</span></span>

<span data-ttu-id="51c14-103">*암시적 변환* 에는 소스 코드에 특별 한 구문이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="51c14-104">다음 예제에서 Visual Basic는 `q`에 할당 하기 전에 `k`의 값을 단 정밀도 부동 소수점 값으로 암시적으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>

```vb
Dim k As Integer
Dim q As Double
' Integer widens to Double, so you can do this with Option Strict On.
k = 432
q = k
```

<span data-ttu-id="51c14-105">*명시적 변환은* 형식 변환 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="51c14-106">Visual Basic는 괄호 안의 식을 원하는 데이터 형식으로 강제 변환 하는 몇 가지 키워드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="51c14-107">이러한 키워드는 함수 처럼 동작 하지만 컴파일러가 코드를 인라인으로 생성 하므로 함수 호출을 사용 하는 것 보다 약간 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>

<span data-ttu-id="51c14-108">앞의 예제에서 다음과 같은 확장에서 `CInt` 키워드는 `q` 값을 `k`에 할당 하기 전에 다시 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>

```vb
' q had been assigned the value 432 from k.
q = Math.Sqrt(q)
k = CInt(q)
' k now has the value 21 (rounded square root of 432).
```

## <a name="conversion-keywords"></a><span data-ttu-id="51c14-109">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="51c14-109">Conversion Keywords</span></span>

<span data-ttu-id="51c14-110">다음 표에서는 사용 가능한 변환 키워드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-110">The following table shows the available conversion keywords.</span></span>

|<span data-ttu-id="51c14-111">형식 변환 키워드</span><span class="sxs-lookup"><span data-stu-id="51c14-111">Type conversion keyword</span></span>|<span data-ttu-id="51c14-112">식을 데이터 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-112">Converts an expression to data type</span></span>|<span data-ttu-id="51c14-113">변환할 수 있는 식의 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-113">Allowable data types of expression to be converted</span></span>|
|---|---|---|
|`CBool`|[<span data-ttu-id="51c14-114">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="51c14-115">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|
|`CByte`|[<span data-ttu-id="51c14-116">Byte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="51c14-117">모든 숫자 형식 (`SByte` 및 열거형 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CChar`|[<span data-ttu-id="51c14-118">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="51c14-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-119">`String`, `Object`</span></span>|
|`CDate`|[<span data-ttu-id="51c14-120">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="51c14-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-121">`String`, `Object`</span></span>|
|`CDbl`|[<span data-ttu-id="51c14-122">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="51c14-123">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CDec`|[<span data-ttu-id="51c14-124">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="51c14-125">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CInt`|[<span data-ttu-id="51c14-126">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="51c14-127">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CLng`|[<span data-ttu-id="51c14-128">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="51c14-129">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CObj`|[<span data-ttu-id="51c14-130">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="51c14-131">모든 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-131">Any type</span></span>|
|`CSByte`|[<span data-ttu-id="51c14-132">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="51c14-133">모든 숫자 형식 (`Byte` 및 열거형 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CShort`|[<span data-ttu-id="51c14-134">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="51c14-135">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CSng`|[<span data-ttu-id="51c14-136">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="51c14-137">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CStr`|[<span data-ttu-id="51c14-138">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="51c14-139">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `Char`, `Char` 배열, `Date`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|
|`CType`|<span data-ttu-id="51c14-140">쉼표 (`,`) 뒤에 지정 된 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="51c14-141">기본 *데이터 형식* (기본 형식의 배열 포함)으로 변환 하는 경우 해당 변환 키워드에 대해 허용 되는 것과 동일한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="51c14-142">*복합 데이터 형식*으로 변환 하는 경우, 구현 하는 인터페이스 및 해당 형식이 상속 하는 클래스</span><span class="sxs-lookup"><span data-stu-id="51c14-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="51c14-143">`CType`오버 로드 된 클래스 또는 구조체로 변환 하는 경우 해당 클래스 또는 구조체는</span><span class="sxs-lookup"><span data-stu-id="51c14-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|
|`CUInt`|[<span data-ttu-id="51c14-144">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="51c14-145">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CULng`|[<span data-ttu-id="51c14-146">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="51c14-147">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|
|`CUShort`|[<span data-ttu-id="51c14-148">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="51c14-149">모든 숫자 형식 (`Byte`, `SByte`및 열거 형식 포함), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="51c14-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|

## <a name="the-ctype-function"></a><span data-ttu-id="51c14-150">CType 함수</span><span class="sxs-lookup"><span data-stu-id="51c14-150">The CType Function</span></span>

<span data-ttu-id="51c14-151">[CType 함수](../../../../visual-basic/language-reference/functions/ctype-function.md) 는 두 인수에 대해 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="51c14-152">첫 번째는 변환할 식이고 두 번째는 대상 데이터 형식 또는 개체 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="51c14-153">첫 번째 인수는 형식이 아니라 식 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-153">Note that the first argument must be an expression, not a type.</span></span>

<span data-ttu-id="51c14-154">`CType`는 *인라인 함수*입니다. 즉, 컴파일 코드에서 함수 호출을 생성 하지 않고 변환을 수행 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="51c14-155">이렇게 하면 성능이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-155">This improves performance.</span></span>

<span data-ttu-id="51c14-156">다른 형식 변환 키워드와 `CType`를 비교 하려면 [DirectCast operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) 및 [TryCast operator](../../../../visual-basic/language-reference/operators/trycast-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51c14-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>

### <a name="elementary-types"></a><span data-ttu-id="51c14-157">기본 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-157">Elementary Types</span></span>

<span data-ttu-id="51c14-158">다음 예에서는 `CType`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-158">The following example demonstrates the use of `CType`.</span></span>

```vb
k = CType(q, Integer)
' The following statement coerces w to the specific object class Label.
f = CType(w, Label)
```

### <a name="composite-types"></a><span data-ttu-id="51c14-159">복합 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-159">Composite Types</span></span>

<span data-ttu-id="51c14-160">`CType`를 사용 하 여 값을 복합 데이터 형식 및 기본 형식으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="51c14-161">다음 예제와 같이이를 사용 하 여 개체 클래스를 해당 인터페이스 중 하나의 형식으로 강제 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>

```vb
' Assume class cZone implements interface iZone.
Dim h As Object
' The first argument to CType must be an expression, not a type.
Dim cZ As cZone
' The following statement coerces a cZone object to its interface iZone.
h = CType(cZ, iZone)
```

### <a name="array-types"></a><span data-ttu-id="51c14-162">배열 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-162">Array Types</span></span>

<span data-ttu-id="51c14-163">다음 예제와 같이 `CType` 배열 데이터 형식을 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-163">`CType` can also convert array data types, as in the following example.</span></span>

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

<span data-ttu-id="51c14-164">자세한 내용 및 예제는 [배열 변환](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51c14-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>

### <a name="types-defining-ctype"></a><span data-ttu-id="51c14-165">CType을 정의 하는 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-165">Types Defining CType</span></span>

<span data-ttu-id="51c14-166">정의한 클래스 또는 구조체에 대 한 `CType`를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="51c14-167">이를 통해 클래스 또는 구조체의 형식으로 값을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="51c14-168">자세한 내용 및 예제는 [방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51c14-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>

> [!NOTE]
> <span data-ttu-id="51c14-169">변환 키워드와 함께 사용 되는 값은 대상 데이터 형식에 대해 유효 해야 합니다. 그렇지 않으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="51c14-170">예를 들어 `Long` `Integer`으로 변환 하려는 경우 `Long` 값은 `Integer` 데이터 형식에 대 한 유효한 범위 내에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>

> [!CAUTION]
> <span data-ttu-id="51c14-171">소스 형식이 대상 형식에서 파생 되지 않은 경우 런타임에 한 클래스 형식에서 다른 클래스 형식으로 변환 하는 `CType`를 지정 하면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="51c14-172">이러한 오류는 <xref:System.InvalidCastException> 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>

<span data-ttu-id="51c14-173">그러나 형식 중 하나가 정의 된 구조체 또는 클래스이 고 해당 구조체 또는 클래스에서 `CType`를 정의한 경우에는 `CType`요구 사항을 충족 하는 경우 변환이 성공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="51c14-174">[방법: 변환 연산자 정의를](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="51c14-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>

<span data-ttu-id="51c14-175">명시적 변환을 수행 하는 것은 지정 된 데이터 형식 또는 개체 클래스로 식을 *캐스팅* 하는 것으로 알려져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="51c14-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>

## <a name="see-also"></a><span data-ttu-id="51c14-176">참고 항목</span><span class="sxs-lookup"><span data-stu-id="51c14-176">See also</span></span>

- [<span data-ttu-id="51c14-177">Visual Basic 형식 변환</span><span class="sxs-lookup"><span data-stu-id="51c14-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="51c14-178">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="51c14-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="51c14-179">방법: Visual Basic에서 개체를 다른 형식으로 변환</span><span class="sxs-lookup"><span data-stu-id="51c14-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="51c14-180">구조체</span><span class="sxs-lookup"><span data-stu-id="51c14-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="51c14-181">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="51c14-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="51c14-182">CString</span><span class="sxs-lookup"><span data-stu-id="51c14-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="51c14-183">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="51c14-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
