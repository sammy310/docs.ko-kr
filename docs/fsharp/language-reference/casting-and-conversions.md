---
title: 캐스팅 및 변환
description: 프로그래밍 언어에서 F# 다양 한 기본 형식 간의 산술 변환에 대 한 변환 연산자를 제공 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: ee4df588caabf58c7b9e18961e217ef8f15fcf93
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630428"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="058cd-103">캐스팅 및 변환(F#)</span><span class="sxs-lookup"><span data-stu-id="058cd-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="058cd-104">이 항목에서는의 F#형식 변환에 대 한 지원에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="058cd-105">산술 형식</span><span class="sxs-lookup"><span data-stu-id="058cd-105">Arithmetic Types</span></span>

<span data-ttu-id="058cd-106">F#정수 및 부동 소수점 형식 등 다양 한 기본 형식 간의 산술 변환을 위한 변환 연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="058cd-107">정수 및 문자 변환 연산자에는 checked 및 unchecked 형식이 있습니다. 부동 소수점 연산자와 `enum` 변환 연산자는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="058cd-108">선택 하지 않은 폼은에 `Microsoft.FSharp.Core.Operators` 정의 되 고 선택 된 폼은 `Microsoft.FSharp.Core.Operators.Checked`에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="058cd-109">결과 값이 대상 형식의 제한을 초과 하는 경우 확인 된 폼에서 오버플로를 확인 하 고 런타임 예외를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="058cd-110">이러한 각 연산자는 대상 형식의 이름과 동일한 이름을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="058cd-111">예를 들어 형식에 명시적으로 주석을 추가 `byte` 하는 다음 코드에서는 두 가지 의미를 사용 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="058cd-112">첫 번째 항목은 형식이 고 두 번째 항목은 변환 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="058cd-113">다음 표에서는에 F#정의 된 변환 연산자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="058cd-114">연산자</span><span class="sxs-lookup"><span data-stu-id="058cd-114">Operator</span></span>|<span data-ttu-id="058cd-115">Description</span><span class="sxs-lookup"><span data-stu-id="058cd-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="058cd-116">부호 없는 8 비트 형식인 바이트로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="058cd-117">부호 있는 바이트로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="058cd-118">부호 있는 16 비트 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="058cd-119">부호 없는 16 비트 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="058cd-120">32 비트 부호 있는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="058cd-121">32 비트 부호 없는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="058cd-122">64 비트 부호 있는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="058cd-123">64 비트 부호 없는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="058cd-124">네이티브 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="058cd-125">부호 없는 네이티브 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="058cd-126">64 비트 배정밀도 IEEE 부동 소수점 숫자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="058cd-127">32 비트 단 정밀도 IEEE 부동 소수점 숫자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="058cd-128">을로 `System.Decimal`변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="058cd-129">`System.Char`을 유니코드 문자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="058cd-130">열거형 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="058cd-131">기본 제공 기본 형식 외에도 이러한 연산자를 적절 한 서명이 있는 또는 `op_Explicit` `op_Implicit` 메서드를 구현 하는 형식과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="058cd-132">예를 들어 변환 `int` 연산자는 형식을 매개 변수로 사용 하 고를 반환 `int`하 `op_Explicit` 는 정적 메서드를 제공 하는 모든 형식에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="058cd-133">반환 형식으로 메서드를 오버 로드할 수 없다는 일반적인 규칙에 대 한 특별 한 예외로, 및 `op_Explicit` `op_Implicit`에 대해이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="058cd-134">열거 형식</span><span class="sxs-lookup"><span data-stu-id="058cd-134">Enumerated Types</span></span>

<span data-ttu-id="058cd-135">연산자는 변환할 `enum` 의 형식을 나타내는 하나의 형식 매개 변수를 사용 하는 제네릭 연산자입니다. `enum`</span><span class="sxs-lookup"><span data-stu-id="058cd-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="058cd-136">열거형 형식으로 변환 하는 경우 형식 유추는 변환 하려는의 형식을 `enum` 결정 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="058cd-137">다음 예제에서 변수 `col1` 는 명시적으로 주석이 추가 되지 않지만 해당 형식은 이후 같음 테스트에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="058cd-138">따라서 컴파일러가 `Color` 열거형으로 변환 하는 것으로 추론할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="058cd-139">또는 다음 예제와 `col2` 같이 형식 주석을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="058cd-140">다음 코드와 같이 명시적으로 대상 열거 형식을 형식 매개 변수로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="058cd-141">열거형은 열거형의 내부 형식이 변환 중인 형식과 호환 되는 경우에만 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="058cd-142">다음 코드에서는 `int32` 와 `uint32`가 일치 하지 않기 때문에 변환이 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="058cd-143">자세한 내용은 [열거형](enumerations.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="058cd-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="058cd-144">개체 형식 캐스팅</span><span class="sxs-lookup"><span data-stu-id="058cd-144">Casting Object Types</span></span>

<span data-ttu-id="058cd-145">개체 계층 구조에서 형식 간의 변환은 개체 지향 프로그래밍의 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="058cd-146">변환에는 두 가지 기본 형식 (업캐스팅)과 캐스팅 (좋기는)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="058cd-147">계층을 위로 캐스팅 하는 것은 파생 된 개체 참조에서 기본 개체 참조로 캐스팅 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="058cd-148">이러한 캐스트는 기본 클래스가 파생 클래스의 상속 계층 구조에 있는 한 작동 하도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="058cd-149">계층에서 파생 된 개체 참조에 대 한 기본 개체 참조로 캐스팅 하는 것은 개체가 실제로 올바른 대상 (파생 된 대상) 형식의 인스턴스이거나 대상 형식에서 파생 된 형식인 경우에만 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="058cd-150">F#이러한 변환 형식에 대 한 연산자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="058cd-151">연산자 `:>` 는 계층을 위로 캐스팅 하 고 연산자 `:?>` 는 계층 구조를 아래로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="058cd-152">업캐스팅</span><span class="sxs-lookup"><span data-stu-id="058cd-152">Upcasting</span></span>

<span data-ttu-id="058cd-153">많은 개체 지향 언어에서 업캐스팅는 암시적입니다. 에서 F#규칙은 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="058cd-154">업캐스팅는 개체 형식에 대 한 메서드에 인수를 전달 하면 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="058cd-155">그러나 모듈의 let 바인딩 함수의 경우 업캐스팅는 매개 변수 형식이 유연한 형식으로 선언 되지 않는 한 자동이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="058cd-156">자세한 내용은 [유연한 형식](flexible-Types.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="058cd-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="058cd-157">연산자 `:>` 는 정적 캐스트를 수행 합니다. 즉, 캐스트의 성공은 컴파일 시간에 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="058cd-158">에서 사용 `:>` 하는 캐스팅이 성공적으로 컴파일되면 유효한 캐스트 이며 런타임에 오류가 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="058cd-159">`upcast` 연산자를 사용 하 여 이러한 변환을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="058cd-160">다음 식에서는 계층 구조를 변환 하는 방법을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="058cd-161">업 캐스트 연산자를 사용 하는 경우 컴파일러는 컨텍스트에서 변환 하는 형식을 유추 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="058cd-162">컴파일러가 대상 형식을 확인할 수 없는 경우 컴파일러에서 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="058cd-163">다운 캐스팅</span><span class="sxs-lookup"><span data-stu-id="058cd-163">Downcasting</span></span>

<span data-ttu-id="058cd-164">연산자 `:?>` 는 동적 캐스트를 수행 합니다. 즉, 캐스트의 성공은 런타임에 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="058cd-165">연산자를 `:?>` 사용 하는 캐스트는 컴파일 시간에 검사 되지 않지만 런타임에는 지정 된 형식으로 캐스팅 하려고 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="058cd-166">개체가 대상 형식과 호환 되 면 캐스팅이 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="058cd-167">개체가 대상 형식과 호환 되지 않는 경우 런타임은을 발생 시킵니다 `InvalidCastException`.</span><span class="sxs-lookup"><span data-stu-id="058cd-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="058cd-168">`downcast` 연산자를 사용 하 여 동적 형식 변환을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="058cd-169">다음 식에서는 프로그램 컨텍스트에서 유추 되는 형식에 대 한 계층 구조를 아래로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="058cd-170">`upcast` 연산자의 경우와 마찬가지로 컴파일러가 컨텍스트에서 특정 대상 형식을 유추할 수 없는 경우 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="058cd-171">다음 코드에서는 `:>` 및 `:?>` 연산자를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="058cd-172">이 코드는 변환이 실패할 `:?>` 경우 throw `InvalidCastException` 되기 때문에 변환이 성공 하는 것을 알고 있는 경우 연산자를 사용 하는 것을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="058cd-173">변환이 성공 하는 것이 확실 하지 않은 경우 `match` 식을 사용 하는 형식 테스트는 예외를 생성 하는 오버 헤드를 방지 하기 때문에 더 나은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="058cd-174">제네릭 연산자 `downcast` 및는 `upcast` 형식 유추를 사용 하 여 인수와 반환 형식을 결정 하기 때문에 위의 코드에서 다음을 바꿀 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="058cd-175">다음 문자열로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="058cd-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="058cd-176">이전 코드에서 인수 형식 및 반환 형식은 `Derived1` 각각 및 `Base1`입니다.</span><span class="sxs-lookup"><span data-stu-id="058cd-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="058cd-177">형식 테스트에 대 한 자세한 내용은 [일치 식](match-Expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="058cd-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="058cd-178">참고자료</span><span class="sxs-lookup"><span data-stu-id="058cd-178">See also</span></span>

- [<span data-ttu-id="058cd-179">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="058cd-179">F# Language Reference</span></span>](index.md)
