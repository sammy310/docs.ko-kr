---
title: 캐스팅 및 변환
description: 에 대해 알아봅니다 하는 방법을 F# 프로그래밍 언어 다양 한 기본 형식 간의 산술 변환에 대 한 변환 연산자를 제공 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: 2a12d48106a267edfc67c9e7b3d3a7bd41d8261c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966623"
---
# <a name="casting-and-conversions-f"></a><span data-ttu-id="9f9ed-103">캐스팅 및 변환(F#)</span><span class="sxs-lookup"><span data-stu-id="9f9ed-103">Casting and Conversions (F#)</span></span>

<span data-ttu-id="9f9ed-104">이 항목의 형식 변환에 대 한 지원에 설명 합니다 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-104">This topic describes support for type conversions in F#.</span></span>

## <a name="arithmetic-types"></a><span data-ttu-id="9f9ed-105">산술 형식</span><span class="sxs-lookup"><span data-stu-id="9f9ed-105">Arithmetic Types</span></span>

<span data-ttu-id="9f9ed-106">F#정수 및 부동 소수점 형식 간에 같은 다양 한 기본 형식 간 산술 변환에 대 한 변환 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-106">F# provides conversion operators for arithmetic conversions between various primitive types, such as between integer and floating point types.</span></span> <span data-ttu-id="9f9ed-107">변환 연산자는 정수 계열 및 char 체크 및 unchecked forms; 부동 소수점 연산자 및 `enum` 변환 연산자는 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-107">The integral and char conversion operators have checked and unchecked forms; the floating point operators and the `enum` conversion operator do not.</span></span> <span data-ttu-id="9f9ed-108">검사 되지 않은 형식에 정의 된 `Microsoft.FSharp.Core.Operators` checked 형식은 정의 되어 `Microsoft.FSharp.Core.Operators.Checked`입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-108">The unchecked forms are defined in `Microsoft.FSharp.Core.Operators` and the checked forms are defined in `Microsoft.FSharp.Core.Operators.Checked`.</span></span> <span data-ttu-id="9f9ed-109">Checked 형식은 오버플로 검사 하 고 결과 값을 대상 형식 한도 초과 하는 경우 런타임 예외를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-109">The checked forms check for overflow and generate a runtime exception if the resulting value exceeds the limits of the target type.</span></span>

<span data-ttu-id="9f9ed-110">이러한 각 연산자 이름이 동일한 대상 형식의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-110">Each of these operators has the same name as the name of the destination type.</span></span> <span data-ttu-id="9f9ed-111">예를 들어, 다음 코드는 유형에 명시적으로 주석 처리를에서 `byte` 두 가지 의미를 사용 하 여 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-111">For example, in the following code, in which the types are explicitly annotated, `byte` appears with two different meanings.</span></span> <span data-ttu-id="9f9ed-112">맨 처음 발견 되는 형식이 며 두 번째 변환 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-112">The first occurrence is the type and the second is the conversion operator.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4401.fs)]

<span data-ttu-id="9f9ed-113">다음 표에서 변환 연산자에 정의 된 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-113">The following table shows conversion operators defined in F#.</span></span>

|<span data-ttu-id="9f9ed-114">연산자</span><span class="sxs-lookup"><span data-stu-id="9f9ed-114">Operator</span></span>|<span data-ttu-id="9f9ed-115">설명</span><span class="sxs-lookup"><span data-stu-id="9f9ed-115">Description</span></span>|
|--------|-----------|
|`byte`|<span data-ttu-id="9f9ed-116">8 비트 부호 없는 형식을 바이트로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-116">Convert to byte, an 8-bit unsigned type.</span></span>|
|`sbyte`|<span data-ttu-id="9f9ed-117">부호 있는 바이트로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-117">Convert to signed byte.</span></span>|
|`int16`|<span data-ttu-id="9f9ed-118">16 비트 부호 있는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-118">Convert to a 16-bit signed integer.</span></span>|
|`uint16`|<span data-ttu-id="9f9ed-119">16 비트 부호 없는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-119">Convert to a 16-bit unsigned integer.</span></span>|
|`int32, int`|<span data-ttu-id="9f9ed-120">32 비트 부호 있는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-120">Convert to a 32-bit signed integer.</span></span>|
|`uint32`|<span data-ttu-id="9f9ed-121">32 비트 부호 없는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-121">Convert to a 32-bit unsigned integer.</span></span>|
|`int64`|<span data-ttu-id="9f9ed-122">64 비트 부호 있는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-122">Convert to a 64-bit signed integer.</span></span>|
|`uint64`|<span data-ttu-id="9f9ed-123">64 비트 부호 없는 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-123">Convert to a 64-bit unsigned integer.</span></span>|
|`nativeint`|<span data-ttu-id="9f9ed-124">원시 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-124">Convert to a native integer.</span></span>|
|`unativeint`|<span data-ttu-id="9f9ed-125">부호 없는 원시 정수로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-125">Convert to an unsigned native integer.</span></span>|
|`float, double`|<span data-ttu-id="9f9ed-126">64 비트 배정밀도 IEEE 부동 소수점 숫자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-126">Convert to a 64-bit double-precision IEEE floating point number.</span></span>|
|`float32, single`|<span data-ttu-id="9f9ed-127">32 비트 정밀도 IEEE 부동 소수점 숫자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-127">Convert to a 32-bit single-precision IEEE floating point number.</span></span>|
|`decimal`|<span data-ttu-id="9f9ed-128">변환할 `System.Decimal`합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-128">Convert to `System.Decimal`.</span></span>|
|`char`|<span data-ttu-id="9f9ed-129">변환할 `System.Char`, 유니코드 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-129">Convert to `System.Char`, a Unicode character.</span></span>|
|`enum`|<span data-ttu-id="9f9ed-130">열거형된 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-130">Convert to an enumerated type.</span></span>|

<span data-ttu-id="9f9ed-131">기본 제공 기본 유형 외에도 구현 하는 형식을 사용 하 여 이러한 연산자를 사용할 수 있습니다 `op_Explicit` 또는 `op_Implicit` 적절 한 시그니처가 있는 메서드.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-131">In addition to built-in primitive types, you can use these operators with types that implement `op_Explicit` or `op_Implicit` methods with appropriate signatures.</span></span> <span data-ttu-id="9f9ed-132">예를 들어 합니다 `int` 변환 연산자는 정적 메서드를 제공 하는 모든 형식 `op_Explicit` 형식을 매개 변수로 받아서 반환 하는 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-132">For example, the `int` conversion operator works with any type that provides a static method `op_Explicit` that takes the type as a parameter and returns `int`.</span></span> <span data-ttu-id="9f9ed-133">반환 형식 메서드를 오버 로드할 수 없습니다는 일반 규칙에 특수 예외로 수에 이렇게 `op_Explicit` 고 `op_Implicit`입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-133">As a special exception to the general rule that methods cannot be overloaded by return type, you can do this for `op_Explicit` and `op_Implicit`.</span></span>

## <a name="enumerated-types"></a><span data-ttu-id="9f9ed-134">열거형된 형식</span><span class="sxs-lookup"><span data-stu-id="9f9ed-134">Enumerated Types</span></span>

<span data-ttu-id="9f9ed-135">합니다 `enum` 연산자는의 형식을 나타내는 하나의 형식 매개 변수를 사용 하는 일반 연산자는 `enum` 변환할 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-135">The `enum` operator is a generic operator that takes one type parameter that represents the type of the `enum` to convert to.</span></span> <span data-ttu-id="9f9ed-136">열거형된 형식으로 변환 하는 경우 형식 유추의 형식을 확인 하려고 합니다 `enum` 변환 하려는 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-136">When it converts to an enumerated type, type inference attempts to determine the type of the `enum` that you want to convert to.</span></span> <span data-ttu-id="9f9ed-137">다음 예에서 변수 `col1` 명시적으로 주석이 지정 되지 않지만 이후 같음 테스트에서 해당 형식이 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-137">In the following example, the variable `col1` is not explicitly annotated, but its type is inferred from the later equality test.</span></span> <span data-ttu-id="9f9ed-138">따라서 컴파일러는 변환 하는 추론할 수는 `Color` 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-138">Therefore, the compiler can deduce that you are converting to a `Color` enumeration.</span></span> <span data-ttu-id="9f9ed-139">또는 형식 주석을 제공할 수 있습니다와 마찬가지로 `col2` 다음 예제에서입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-139">Alternatively, you can supply a type annotation, as with `col2` in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4402.fs)]

<span data-ttu-id="9f9ed-140">또한 다음 코드와 같이 형식 매개 변수와 대상 열거형을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-140">You can also specify the target enumeration type explicitly as a type parameter, as in the following code:</span></span>

```fsharp
let col3 = enum<Color> 3
```

<span data-ttu-id="9f9ed-141">열거형의 내부 형식이 변환 되는 형식와 호환 하는 경우에 열거 작업 캐스팅는 note 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-141">Note that the enumeration casts work only if the underlying type of the enumeration is compatible with the type being converted.</span></span> <span data-ttu-id="9f9ed-142">다음 코드에서 변환에 실패 간의 불일치로 인해 컴파일하려면 `int32` 고 `uint32`입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-142">In the following code, the conversion fails to compile because of the mismatch between `int32` and `uint32`.</span></span>

```fsharp
// Error: types are incompatible
let col4 : Color = enum 2u
```

<span data-ttu-id="9f9ed-143">자세한 내용은 [열거형](enumerations.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-143">For more information, see [Enumerations](enumerations.md).</span></span>

## <a name="casting-object-types"></a><span data-ttu-id="9f9ed-144">개체 형식 캐스팅</span><span class="sxs-lookup"><span data-stu-id="9f9ed-144">Casting Object Types</span></span>

<span data-ttu-id="9f9ed-145">개체 계층 구조에서 형식 간의 변환은 개체 지향 프로그래밍의 기본입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-145">Conversion between types in an object hierarchy is fundamental to object-oriented programming.</span></span> <span data-ttu-id="9f9ed-146">두 가지가 기본 변환: (업 캐스트) 위로 캐스팅 및 캐스팅 (다운 캐스팅) 다운 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-146">There are two basic types of conversions: casting up (upcasting) and casting down (downcasting).</span></span> <span data-ttu-id="9f9ed-147">계층 구조 위로 캐스팅은 기본 개체 참조에 대 한 파생 된 개체 참조에서 캐스팅을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-147">Casting up a hierarchy means casting from a derived object reference to a base object reference.</span></span> <span data-ttu-id="9f9ed-148">이러한 캐스트는 기본 클래스는 파생된 클래스의 상속 계층 구조에서 정상적으로 작동 하도록 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-148">Such a cast is guaranteed to work as long as the base class is in the inheritance hierarchy of the derived class.</span></span> <span data-ttu-id="9f9ed-149">파생 된 개체 참조에 대 한 기본 개체 참조에서 계층 구조 아래로 캐스팅 개체가 실제로 올바른 대상 (파생) 형식 또는 대상 형식에서 파생 된 형식 인스턴스의 경우에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-149">Casting down a hierarchy, from a base object reference to a derived object reference, succeeds only if the object actually is an instance of the correct destination (derived) type or a type derived from the destination type.</span></span>

<span data-ttu-id="9f9ed-150">F#이러한 유형의 변환에 대 한 연산자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-150">F# provides operators for these types of conversions.</span></span> <span data-ttu-id="9f9ed-151">합니다 `:>` 연산자는 계층 구조 위로 캐스팅 및 `:?>` 연산자 계층 구조 아래로 캐스팅 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-151">The `:>` operator casts up the hierarchy, and the `:?>` operator casts down the hierarchy.</span></span>

### <a name="upcasting"></a><span data-ttu-id="9f9ed-152">업 캐스트</span><span class="sxs-lookup"><span data-stu-id="9f9ed-152">Upcasting</span></span>

<span data-ttu-id="9f9ed-153">다양 한 개체 지향 언어에서 업 캐스트는 암시적; F#에서 규칙은 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-153">In many object-oriented languages, upcasting is implicit; in F#, the rules are slightly different.</span></span> <span data-ttu-id="9f9ed-154">업 캐스트는 개체 형식에서 메서드에 인수를 전달 하는 경우 자동으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-154">Upcasting is applied automatically when you pass arguments to methods on an object type.</span></span> <span data-ttu-id="9f9ed-155">그러나 모듈의 let 바인딩 함수에 대 한 업 캐스트 하지 않는 자동으로 매개 변수 형식이 유연한 형식으로 선언 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-155">However, for let-bound functions in a module, upcasting is not automatic, unless the parameter type is declared as a flexible type.</span></span> <span data-ttu-id="9f9ed-156">자세한 내용은 [유연한 형식](flexible-Types.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-156">For more information, see [Flexible Types](flexible-Types.md).</span></span>

<span data-ttu-id="9f9ed-157">`:>` 연산자 정적 캐스팅, 즉, 컴파일 시간에 캐스트의 성공 여부를 결정 된다는 것을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-157">The `:>` operator performs a static cast, which means that the success of the cast is determined at compile time.</span></span> <span data-ttu-id="9f9ed-158">캐스트를 사용 하는 경우 `:>` 성공적으로 컴파일되면 유효한 cast 이며 런타임에 실패 가능성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-158">If a cast that uses `:>` compiles successfully, it is a valid cast and has no chance of failure at run time.</span></span>

<span data-ttu-id="9f9ed-159">사용할 수도 있습니다는 `upcast` 이러한 변환을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-159">You can also use the `upcast` operator to perform such a conversion.</span></span> <span data-ttu-id="9f9ed-160">다음 식을 지정 계층 구조로 변환을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-160">The following expression specifies a conversion up the hierarchy:</span></span>

```fsharp
upcast expression
```

<span data-ttu-id="9f9ed-161">Upcast 연산자를 사용 하면 컴파일러가 변환 하는 컨텍스트에서 형식을 유추 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-161">When you use the upcast operator, the compiler attempts to infer the type you are converting to from the context.</span></span> <span data-ttu-id="9f9ed-162">컴파일러를 대상 형식을 확인할 수 없는 경우 컴파일러는 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-162">If the compiler is unable to determine the target type, the compiler reports an error.</span></span>

### <a name="downcasting"></a><span data-ttu-id="9f9ed-163">다운 캐스팅</span><span class="sxs-lookup"><span data-stu-id="9f9ed-163">Downcasting</span></span>

<span data-ttu-id="9f9ed-164">`:?>` 연산자 동적 캐스팅을 런타임에 캐스트의 성공 여부를 결정 된다는 것을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-164">The `:?>` operator performs a dynamic cast, which means that the success of the cast is determined at run time.</span></span> <span data-ttu-id="9f9ed-165">사용 하는 캐스팅을 `:?>` 컴파일 타임에 연산자를 선택 하지 않으면 하지만 런타임 시 시도가 지정된 된 형식으로 캐스팅 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-165">A cast that uses the `:?>` operator is not checked at compile time; but at run time, an attempt is made to cast to the specified type.</span></span> <span data-ttu-id="9f9ed-166">개체가 대상 형식과 호환 이면 캐스팅에 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-166">If the object is compatible with the target type, the cast succeeds.</span></span> <span data-ttu-id="9f9ed-167">개체가 대상 형식과 호환 되지 않으면 런타임에서 발생 한 `InvalidCastException`합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-167">If the object is not compatible with the target type, the runtime raises an `InvalidCastException`.</span></span>

<span data-ttu-id="9f9ed-168">사용할 수도 있습니다는 `downcast` 동적 형식 변환을 수행 하는 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-168">You can also use the `downcast` operator to perform a dynamic type conversion.</span></span> <span data-ttu-id="9f9ed-169">다음 식을 지정 프로그램 컨텍스트에서 유추 된 형식 하위 계층으로 변환을 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-169">The following expression specifies a conversion down the hierarchy to a type that is inferred from program context:</span></span>

```fsharp
downcast expression
```

<span data-ttu-id="9f9ed-170">와 `upcast` 연산자, 컴파일러에서 컨텍스트를 특정 대상 형식을 유추할 수 없는 경우 오류를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-170">As for the `upcast` operator, if the compiler cannot infer a specific target type from the context, it reports an error.</span></span>

<span data-ttu-id="9f9ed-171">다음 코드에서는 사용 합니다 `:>` 및 `:?>` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-171">The following code illustrates the use of the `:>` and `:?>` operators.</span></span> <span data-ttu-id="9f9ed-172">코드를 보면 합니다 `:?>` 연산자를 가장 잘 알고 있을 때 변환이 성공 한다는 사실을 throw 하기 때문에 사용 됩니다 `InvalidCastException` 변환에 실패 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-172">The code illustrates that the `:?>` operator is best used when you know that conversion will succeed, because it throws `InvalidCastException` if the conversion fails.</span></span> <span data-ttu-id="9f9ed-173">변환이 성공 한다는 사실을 사용 하는 형식 테스트는 알 수 없는 경우는 `match` 식이 예외를 생성 하는 오버 헤드를 방지 하기 때문에 더 합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-173">If you do not know that a conversion will succeed, a type test that uses a `match` expression is better because it avoids the overhead of generating an exception.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4403.fs)]

<span data-ttu-id="9f9ed-174">때문에 제네릭 연산자 `downcast` 고 `upcast` 위 코드에서 인수 및 반환 형식을 결정 하는 형식 유추를 사용, 대체할 수 있습니다</span><span class="sxs-lookup"><span data-stu-id="9f9ed-174">Because generic operators `downcast` and `upcast` rely on type inference to determine the argument and return type, in the above code, you can replace</span></span>

```fsharp
let base1 = d1 :> Base1
```

<span data-ttu-id="9f9ed-175">다음 문자열로 바꾸세요.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-175">with</span></span>

```fsharp
let base1 = upcast d1
```

<span data-ttu-id="9f9ed-176">이전 코드는 인수 형식 및 반환 형식에는 `Derived1` 고 `Base1`, 각각.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-176">In the previous code, the argument type and return types are `Derived1` and `Base1`, respectively.</span></span>

<span data-ttu-id="9f9ed-177">형식 테스트에 대 한 자세한 내용은 참조 하세요. [일치 식](match-Expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9f9ed-177">For more information about type tests, see [Match Expressions](match-Expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9f9ed-178">참고자료</span><span class="sxs-lookup"><span data-stu-id="9f9ed-178">See also</span></span>

- [<span data-ttu-id="9f9ed-179">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="9f9ed-179">F# Language Reference</span></span>](index.md)
