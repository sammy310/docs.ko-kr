---
title: 암시적 변환과 명시적 변환(Visual Basic)
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
ms.openlocfilehash: 82ff710629089cd14c7e982b4afa4301d0790811
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62008258"
---
# <a name="implicit-and-explicit-conversions-visual-basic"></a><span data-ttu-id="718f4-102">암시적 변환과 명시적 변환(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="718f4-102">Implicit and Explicit Conversions (Visual Basic)</span></span>
<span data-ttu-id="718f4-103">*암시적 변환* 소스 코드의 특수 구문이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-103">An *implicit conversion* does not require any special syntax in the source code.</span></span> <span data-ttu-id="718f4-104">다음 예제에서는 Visual Basic 암시적으로 변환 된 값 `k` 단 정밀도 부동 소수점 값에 할당 하기 전에 `q`입니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-104">In the following example, Visual Basic implicitly converts the value of `k` to a single-precision floating-point value before assigning it to `q`.</span></span>  
  
```  
Dim k As Integer  
Dim q As Double  
' Integer widens to Double, so you can do this with Option Strict On.  
k = 432  
q = k  
```  
  
 <span data-ttu-id="718f4-105">*명시적 변환* 형식 변환 키워드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-105">An *explicit conversion* uses a type conversion keyword.</span></span> <span data-ttu-id="718f4-106">Visual Basic에서는 이러한는 여러 키워드를 원하는 데이터 형식에 대 한 괄호 안에 식을 강제 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-106">Visual Basic provides several such keywords, which coerce an expression in parentheses to the desired data type.</span></span> <span data-ttu-id="718f4-107">이러한 키워드는 함수 처럼 동작 하지만 함수 호출을 사용 하 여 보다 약간 더 빠르게 실행 이므로 컴파일러 코드 인라인을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-107">These keywords act like functions, but the compiler generates the code inline, so execution is slightly faster than with a function call.</span></span>  
  
 <span data-ttu-id="718f4-108">앞의 예제에서의 다음 확장에는 `CInt` 키워드의 값을 변환 `q` 에 할당 하기 전에 정수 돌아가기 `k`합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-108">In the following extension of the preceding example, the `CInt` keyword converts the value of `q` back to an integer before assigning it to `k`.</span></span>  
  
```  
' q had been assigned the value 432 from k.  
q = Math.Sqrt(q)  
k = CInt(q)  
' k now has the value 21 (rounded square root of 432).  
```  
  
## <a name="conversion-keywords"></a><span data-ttu-id="718f4-109">변환 키워드</span><span class="sxs-lookup"><span data-stu-id="718f4-109">Conversion Keywords</span></span>  
 <span data-ttu-id="718f4-110">다음 표에서 사용할 수 있는 변환 키워드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-110">The following table shows the available conversion keywords.</span></span>  
  
|<span data-ttu-id="718f4-111">형식 변환 키워드</span><span class="sxs-lookup"><span data-stu-id="718f4-111">Type conversion keyword</span></span>|<span data-ttu-id="718f4-112">식 데이터 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-112">Converts an expression to data type</span></span>|<span data-ttu-id="718f4-113">변환할 식의 허용 되는 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-113">Allowable data types of expression to be converted</span></span>|  
|---|---|---|  
|`CBool`|[<span data-ttu-id="718f4-114">Boolean 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-114">Boolean Data Type</span></span>](../../../../visual-basic/language-reference/data-types/boolean-data-type.md)|<span data-ttu-id="718f4-115">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-115">Any numeric type (including `Byte`, `SByte`, and enumerated types), `String`, `Object`</span></span>|  
|`CByte`|[<span data-ttu-id="718f4-116">Byte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-116">Byte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/byte-data-type.md)|<span data-ttu-id="718f4-117">모든 숫자 유형 (포함 `SByte` 열거 형식 및), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-117">Any numeric type (including `SByte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CChar`|[<span data-ttu-id="718f4-118">Char 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-118">Char Data Type</span></span>](../../../../visual-basic/language-reference/data-types/char-data-type.md)|<span data-ttu-id="718f4-119">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-119">`String`, `Object`</span></span>|  
|`CDate`|[<span data-ttu-id="718f4-120">Date 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-120">Date Data Type</span></span>](../../../../visual-basic/language-reference/data-types/date-data-type.md)|<span data-ttu-id="718f4-121">`String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-121">`String`, `Object`</span></span>|  
|`CDbl`|[<span data-ttu-id="718f4-122">Double 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-122">Double Data Type</span></span>](../../../../visual-basic/language-reference/data-types/double-data-type.md)|<span data-ttu-id="718f4-123">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-123">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CDec`|[<span data-ttu-id="718f4-124">Decimal 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-124">Decimal Data Type</span></span>](../../../../visual-basic/language-reference/data-types/decimal-data-type.md)|<span data-ttu-id="718f4-125">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-125">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CInt`|[<span data-ttu-id="718f4-126">Integer 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-126">Integer Data Type</span></span>](../../../../visual-basic/language-reference/data-types/integer-data-type.md)|<span data-ttu-id="718f4-127">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-127">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CLng`|[<span data-ttu-id="718f4-128">Long 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-128">Long Data Type</span></span>](../../../../visual-basic/language-reference/data-types/long-data-type.md)|<span data-ttu-id="718f4-129">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-129">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CObj`|[<span data-ttu-id="718f4-130">Object 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-130">Object Data Type</span></span>](../../../../visual-basic/language-reference/data-types/object-data-type.md)|<span data-ttu-id="718f4-131">모든 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-131">Any type</span></span>|  
|`CSByte`|[<span data-ttu-id="718f4-132">SByte 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-132">SByte Data Type</span></span>](../../../../visual-basic/language-reference/data-types/sbyte-data-type.md)|<span data-ttu-id="718f4-133">모든 숫자 유형 (포함 `Byte` 열거 형식 및), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-133">Any numeric type (including `Byte` and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CShort`|[<span data-ttu-id="718f4-134">Short 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-134">Short Data Type</span></span>](../../../../visual-basic/language-reference/data-types/short-data-type.md)|<span data-ttu-id="718f4-135">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-135">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CSng`|[<span data-ttu-id="718f4-136">Single 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-136">Single Data Type</span></span>](../../../../visual-basic/language-reference/data-types/single-data-type.md)|<span data-ttu-id="718f4-137">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-137">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CStr`|[<span data-ttu-id="718f4-138">String 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-138">String Data Type</span></span>](../../../../visual-basic/language-reference/data-types/string-data-type.md)|<span data-ttu-id="718f4-139">모든 숫자 유형 (포함 하 여 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `Char`, `Char` 배열 `Date`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-139">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `Char`, `Char` array, `Date`, `Object`</span></span>|  
|`CType`|<span data-ttu-id="718f4-140">쉼표를 다음 지정 된 형식 (`,`)</span><span class="sxs-lookup"><span data-stu-id="718f4-140">Type specified following the comma (`,`)</span></span>|<span data-ttu-id="718f4-141">변환 하는 경우는 *기본 데이터 형식* 해당 변환 키워드에 허용 된 대로 형식을 동일한 (기본 형식의 배열을 포함)</span><span class="sxs-lookup"><span data-stu-id="718f4-141">When converting to an *elementary data type* (including an array of an elementary type), the same types as allowed for the corresponding conversion keyword</span></span><br /><br /> <span data-ttu-id="718f4-142">변환 하는 경우는 *복합 데이터 형식을*를 구현 하는 인터페이스 및 상속 된 클래스</span><span class="sxs-lookup"><span data-stu-id="718f4-142">When converting to a *composite data type*, the interfaces it implements and the classes from which it inherits</span></span><br /><br /> <span data-ttu-id="718f4-143">가 오버 로드는 클래스 또는 구조체를 변환할 때 `CType`, 해당 클래스 또는 구조체</span><span class="sxs-lookup"><span data-stu-id="718f4-143">When converting to a class or structure on which you have overloaded `CType`, that class or structure</span></span>|  
|`CUInt`|[<span data-ttu-id="718f4-144">UInteger 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-144">UInteger Data Type</span></span>](../../../../visual-basic/language-reference/data-types/uinteger-data-type.md)|<span data-ttu-id="718f4-145">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-145">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CULng`|[<span data-ttu-id="718f4-146">ULong 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-146">ULong Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ulong-data-type.md)|<span data-ttu-id="718f4-147">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-147">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
|`CUShort`|[<span data-ttu-id="718f4-148">UShort 데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-148">UShort Data Type</span></span>](../../../../visual-basic/language-reference/data-types/ushort-data-type.md)|<span data-ttu-id="718f4-149">모든 숫자 유형 (포함 `Byte`, `SByte`, 및 열거 형식), `Boolean`, `String`, `Object`</span><span class="sxs-lookup"><span data-stu-id="718f4-149">Any numeric type (including `Byte`, `SByte`, and enumerated types), `Boolean`, `String`, `Object`</span></span>|  
  
## <a name="the-ctype-function"></a><span data-ttu-id="718f4-150">CType 함수</span><span class="sxs-lookup"><span data-stu-id="718f4-150">The CType Function</span></span>  
 <span data-ttu-id="718f4-151">합니다 [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) 두 인수에 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-151">The [CType Function](../../../../visual-basic/language-reference/functions/ctype-function.md) operates on two arguments.</span></span> <span data-ttu-id="718f4-152">첫 번째 변환할 식이고 두 번째는 대상 데이터 형식 또는 개체 클래스.</span><span class="sxs-lookup"><span data-stu-id="718f4-152">The first is the expression to be converted, and the second is the destination data type or object class.</span></span> <span data-ttu-id="718f4-153">첫 번째 인수 형식이 아닌 식 이어야 합니다 하는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-153">Note that the first argument must be an expression, not a type.</span></span>  
  
 <span data-ttu-id="718f4-154">`CType` *인라인 함수*변환 하면 컴파일된 코드 즉, 종종 함수를 생성 하지 않고 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-154">`CType` is an *inline function*, meaning the compiled code makes the conversion, often without generating a function call.</span></span> <span data-ttu-id="718f4-155">이 성능을 향상 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-155">This improves performance.</span></span>  
  
 <span data-ttu-id="718f4-156">에 대 한 비교 `CType` 다른 형식 변환 키워드를 사용 하 여 볼 [DirectCast 연산자](../../../../visual-basic/language-reference/operators/directcast-operator.md) 하 고 [TryCast 연산자](../../../../visual-basic/language-reference/operators/trycast-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-156">For a comparison of `CType` with the other type conversion keywords, see [DirectCast Operator](../../../../visual-basic/language-reference/operators/directcast-operator.md) and [TryCast Operator](../../../../visual-basic/language-reference/operators/trycast-operator.md).</span></span>  
  
### <a name="elementary-types"></a><span data-ttu-id="718f4-157">기본 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-157">Elementary Types</span></span>  
 <span data-ttu-id="718f4-158">다음 예에서는 `CType`의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-158">The following example demonstrates the use of `CType`.</span></span>  
  
```  
k = CType(q, Integer)  
' The following statement coerces w to the specific object class Label.  
f = CType(w, Label)  
```  
  
### <a name="composite-types"></a><span data-ttu-id="718f4-159">복합 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-159">Composite Types</span></span>  
 <span data-ttu-id="718f4-160">사용할 수 있습니다 `CType` 값 복합 데이터 형식을 기본 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-160">You can use `CType` to convert values to composite data types as well as to elementary types.</span></span> <span data-ttu-id="718f4-161">개체 클래스를 다음 예제와 같이 해당 인터페이스 중 하나의 형식으로 강제 변환에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-161">You can also use it to coerce an object class to the type of one of its interfaces, as in the following example.</span></span>  
  
```  
' Assume class cZone implements interface iZone.  
Dim h As Object  
' The first argument to CType must be an expression, not a type.  
Dim cZ As cZone  
' The following statement coerces a cZone object to its interface iZone.  
h = CType(cZ, iZone)  
```  
  
### <a name="array-types"></a><span data-ttu-id="718f4-162">배열 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-162">Array Types</span></span>  
 <span data-ttu-id="718f4-163">`CType` 다음 예제와 같이 배열 데이터 형식에서 변환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-163">`CType` can also convert array data types, as in the following example.</span></span>  
  
```  
Dim v() As classV  
Dim obArray() As Object  
' Assume some object array has been assigned to obArray.  
' Check for run-time type compatibility.  
If TypeOf obArray Is classV()  
    ' obArray can be converted to classV.  
    v = CType(obArray, classV())  
End If  
```  
  
 <span data-ttu-id="718f4-164">자세한 내용 및 예제를 참조 하세요 [배열 변환](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-164">For more information and an example, see [Array Conversions](../../../../visual-basic/programming-guide/language-features/data-types/array-conversions.md).</span></span>  
  
### <a name="types-defining-ctype"></a><span data-ttu-id="718f4-165">CType 정의 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-165">Types Defining CType</span></span>  
 <span data-ttu-id="718f4-166">정의할 수 있습니다 `CType` 클래스 또는 구조체 정의에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-166">You can define `CType` on a class or structure you have defined.</span></span> <span data-ttu-id="718f4-167">이 클래스 또는 구조체의 형식에서 값을 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-167">This allows you to convert values to and from the type of your class or structure.</span></span> <span data-ttu-id="718f4-168">자세한 내용 및 예제를 참조 하세요. [방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-168">For more information and an example, see [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="718f4-169">변환 키워드를 사용 하 여 사용 되는 값은 대상 데이터 형식에 대해 유효 해야 합니다. 그렇지 않으면 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-169">Values used with a conversion keyword must be valid for the destination data type, or an error occurs.</span></span> <span data-ttu-id="718f4-170">예를 들어, 변환 하려는 경우는 `Long` 에 `Integer`의 값을 `Long` 의 유효한 범위 내에 있어야는 `Integer` 데이터 형식.</span><span class="sxs-lookup"><span data-stu-id="718f4-170">For example, if you attempt to convert a `Long` to an `Integer`, the value of the `Long` must be within the valid range for the `Integer` data type.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="718f4-171">지정 `CType` 원본 유형을 대상 형식에서 파생 되지 않습니다 하는 경우 런타임 시 다른 실패 한 클래스 형식에서 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-171">Specifying `CType` to convert from one class type to another fails at run time if the source type does not derive from the destination type.</span></span> <span data-ttu-id="718f4-172">이러한 오류를 throw 한 <xref:System.InvalidCastException> 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-172">Such a failure throws an <xref:System.InvalidCastException> exception.</span></span>  
  
 <span data-ttu-id="718f4-173">그러나 형식 중 하나를 구조체 또는 클래스를 정의한 경우 및 정의 하는 경우 `CType` 해당 구조체 또는 클래스에는 변환의 요구 사항을 충족 하는 경우 성공할 수 여 `CType`합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-173">However, if one of the types is a structure or class you have defined, and if you have defined `CType` on that structure or class, a conversion can succeed if it satisfies the requirements of your `CType`.</span></span> <span data-ttu-id="718f4-174">[방법: 변환 연산자 정의](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-174">See [How to: Define a Conversion Operator](../../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md).</span></span>  
  
 <span data-ttu-id="718f4-175">명시적 변환을 수행 라고도 *캐스팅* 지정 된 데이터 형식 또는 개체 클래스에는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="718f4-175">Performing an explicit conversion is also known as *casting* an expression to a given data type or object class.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="718f4-176">참고자료</span><span class="sxs-lookup"><span data-stu-id="718f4-176">See also</span></span>

- [<span data-ttu-id="718f4-177">Visual Basic의 형식 변환</span><span class="sxs-lookup"><span data-stu-id="718f4-177">Type Conversions in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
- [<span data-ttu-id="718f4-178">문자열과 다른 형식 사이의 변환</span><span class="sxs-lookup"><span data-stu-id="718f4-178">Conversions Between Strings and Other Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/conversions-between-strings-and-other-types.md)
- [<span data-ttu-id="718f4-179">방법: Visual Basic에서 다른 형식으로 변환할 개체</span><span class="sxs-lookup"><span data-stu-id="718f4-179">How to: Convert an Object to Another Type in Visual Basic</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/how-to-convert-an-object-to-another-type.md)
- [<span data-ttu-id="718f4-180">구조체</span><span class="sxs-lookup"><span data-stu-id="718f4-180">Structures</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [<span data-ttu-id="718f4-181">데이터 형식</span><span class="sxs-lookup"><span data-stu-id="718f4-181">Data Types</span></span>](../../../../visual-basic/language-reference/data-types/index.md)
- [<span data-ttu-id="718f4-182">형식 변환 함수</span><span class="sxs-lookup"><span data-stu-id="718f4-182">Type Conversion Functions</span></span>](../../../../visual-basic/language-reference/functions/type-conversion-functions.md)
- [<span data-ttu-id="718f4-183">데이터 형식 문제 해결</span><span class="sxs-lookup"><span data-stu-id="718f4-183">Troubleshooting Data Types</span></span>](../../../../visual-basic/programming-guide/language-features/data-types/troubleshooting-data-types.md)
