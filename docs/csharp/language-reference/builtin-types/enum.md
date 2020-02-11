---
title: 열거형 - C# 참조
description: 선택 또는 선택의 조합을 나타내는 C# 열거형에 대해 알아봅니다
ms.date: 12/13/2019
f1_keywords:
- enum
- enum_CSharpKeyword
helpviewer_keywords:
- enum keyword [C#]
- enum type [C#]
- enumeration type [C#]
- bit flags [C#]
ms.assetid: bbeb9a0f-e9b3-41ab-b0a6-c41b1a08974c
ms.openlocfilehash: ac4dafef92bbc900d291a5b653c55ba295f1a6d6
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093229"
---
# <a name="enumeration-types-c-reference"></a><span data-ttu-id="4f99b-103">열거형(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="4f99b-103">Enumeration types (C# reference)</span></span>

<span data-ttu-id="4f99b-104">*열거형*(또는 *열거형 형식*)은 기본 [정수 숫자](integral-numeric-types.md) 형식의 명명된 상수 집합에 의해 정의되는 [값 형식](value-types.md)입니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-104">An *enumeration type* (or *enum type*) is a [value type](value-types.md) defined by a set of named constants of the underlying [integral numeric](integral-numeric-types.md) type.</span></span> <span data-ttu-id="4f99b-105">열거형을 정의하려면 `enum` 키워드를 정의하고 *열거형 멤버*의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-105">To define an enumeration type, use the `enum` keyword and specify the names of *enum members*:</span></span>

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

<span data-ttu-id="4f99b-106">기본적으로 열거형 멤버의 연결된 상수 값은 `int` 형식입니다. 즉, 0으로 시작하고 정의 텍스트 순서에 따라 1씩 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-106">By default, the associated constant values of enum members are of type `int`; they start with zero and increase by one following the definition text order.</span></span> <span data-ttu-id="4f99b-107">다른 [정수 숫자](integral-numeric-types.md) 형식을 열거형 형식의 기본 형식으로 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-107">You can explicitly specify any other [integral numeric](integral-numeric-types.md) type as an underlying type of an enumeration type.</span></span> <span data-ttu-id="4f99b-108">또한 다음 예제와 같이 연결된 상수 값을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-108">You also can explicitly specify the associated constant values, as the following example shows:</span></span>

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

<span data-ttu-id="4f99b-109">열거형 형식의 정의 내에서 메서드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-109">You cannot define a method inside the definition of an enumeration type.</span></span> <span data-ttu-id="4f99b-110">열거형 형식에 기능을 추가하려면 [확장 메서드](../../programming-guide/classes-and-structs/extension-methods.md)를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-110">To add functionality to an enumeration type, create an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

<span data-ttu-id="4f99b-111">0에 해당 열거형 멤버가 없는 경우에도 열거형 형식 `E`의 기본값은 식 `(E)0`에 의해 생성되는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-111">The default value of an enumeration type `E` is the value produced by expression `(E)0`, even if zero doesn't have the corresponding enum member.</span></span>

<span data-ttu-id="4f99b-112">열거형 형식을 사용하여 상호 배타적인 값의 집합에서의 선택 또는 선택의 조합을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-112">You use an enumeration type to represent a choice from a set of mutually exclusive values or a combination of choices.</span></span> <span data-ttu-id="4f99b-113">선택의 조합을 나타내려면 열거형 형식을 비트 플래그로 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-113">To represent a combination of choices, define an enumeration type as bit flags.</span></span>

## <a name="enumeration-types-as-bit-flags"></a><span data-ttu-id="4f99b-114">비트 플래그로서 열거형 형식</span><span class="sxs-lookup"><span data-stu-id="4f99b-114">Enumeration types as bit flags</span></span>

<span data-ttu-id="4f99b-115">열거형 형식으로 선택의 조합을 나타내려면 개별 선택이 비트 필드가 되도록 해당 선택의 열거형 멤버를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-115">If you want an enumeration type to represent a combination of choices, define enum members for those choices such that an individual choice is a bit field.</span></span> <span data-ttu-id="4f99b-116">즉, 이러한 멤버의 연결된 값은 제곱이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-116">That is, the associated values of those enum members should be the powers of two.</span></span> <span data-ttu-id="4f99b-117">그런 다음 [비트 논리 연산자 `|` 또는 `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators)를 사용하여 각각 선택을 조합하거나 선택의 조합을 교차할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-117">Then, you can use the [bitwise logical operators `|` or `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators) to combine choices or intersect combinations of choices, respectively.</span></span> <span data-ttu-id="4f99b-118">열거형 형식이 비트 필드를 선언한다고 표시하려면 [Flags](xref:System.FlagsAttribute) 특성을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-118">To indicate that an enumeration type declares bit fields, apply the [Flags](xref:System.FlagsAttribute) attribute to it.</span></span> <span data-ttu-id="4f99b-119">다음 예제에 나온 것처럼 열거형 형식의 정의에 몇 가지 일반적인 조합을 포함할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-119">As the following example shows, you also can include some typical combinations in the definition of an enumeration type.</span></span>

[!code-csharp[enum flags](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Flags)]

<span data-ttu-id="4f99b-120">자세한 내용과 예제는 <xref:System.FlagsAttribute?displayProperty=nameWithType> API 참조 페이지 및 <xref:System.Enum?displayProperty=nameWithType> API 참조 페이지의 [비독점적 멤버 및 Flags 특성](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f99b-120">For more information and examples, see the <xref:System.FlagsAttribute?displayProperty=nameWithType> API reference page and the [Non-exclusive members and the Flags attribute](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) section of the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

## <a name="the-systemenum-type-and-enum-constraint"></a><span data-ttu-id="4f99b-121">System.Enum 형식 및 열거형 제약 조건</span><span class="sxs-lookup"><span data-stu-id="4f99b-121">The System.Enum type and enum constraint</span></span>

<span data-ttu-id="4f99b-122"><xref:System.Enum?displayProperty=nameWithType> 형식은 모든 열거형 형식의 추상적 기본 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-122">The <xref:System.Enum?displayProperty=nameWithType> type is the abstract base class of all enumeration types.</span></span> <span data-ttu-id="4f99b-123">이 형식은 열거형 형식 및 그 값에 대한 정보를 가져오는 여러 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-123">It provides a number of methods to get information about an enumeration type and its values.</span></span> <span data-ttu-id="4f99b-124">자세한 내용과 예제는 <xref:System.Enum?displayProperty=nameWithType> API 참조 페이지를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f99b-124">For more information and examples, see the <xref:System.Enum?displayProperty=nameWithType> API reference page.</span></span>

<span data-ttu-id="4f99b-125">C# 7.3부터 기본 클래스 제약 조건([열거형 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)이라고 함)에서 `System.Enum`을 사용하여 형식 매개 변수가 열거형 형식이라고 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-125">Beginning with C# 7.3, you can use `System.Enum` in a base class constraint (that is known as the [enum constraint](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)) to specify that a type parameter is an enumeration type.</span></span>

## <a name="conversions"></a><span data-ttu-id="4f99b-126">변환</span><span class="sxs-lookup"><span data-stu-id="4f99b-126">Conversions</span></span>

<span data-ttu-id="4f99b-127">모든 열거형 형식에는 열거형 형식과 기본 정수 형식 간의 명시적 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-127">For any enumeration type, there exist explicit conversions between the enumeration type and its underlying integral type.</span></span> <span data-ttu-id="4f99b-128">열거형 값을 기본 형식에 [캐스트](../operators/type-testing-and-cast.md#cast-operator-)하는 경우, 그 결과는 열거형 멤버의 연결된 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-128">If you [cast](../operators/type-testing-and-cast.md#cast-operator-) an enum value to its underlying type, the result is the associated integral value of an enum member.</span></span>

[!code-csharp[enum conversions](~/samples/csharp/language-reference/builtin-types/EnumType.cs#Conversions)]

<span data-ttu-id="4f99b-129">열거형 형식에 연결된 특정 값이 포함되어 있는지 확인하려면 <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-129">Use the <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> method to determine whether an enumeration type contains an enum member with the certain associated value.</span></span>

<span data-ttu-id="4f99b-130">모든 열거형 형식에는 <xref:System.Enum?displayProperty=nameWithType> 형식의 [boxing 및 unboxing](../../programming-guide/types/boxing-and-unboxing.md) 변환이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4f99b-130">For any enumeration type, there exist [boxing and unboxing](../../programming-guide/types/boxing-and-unboxing.md) conversions to and from the <xref:System.Enum?displayProperty=nameWithType> type, respectively.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="4f99b-131">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="4f99b-131">C# language specification</span></span>

<span data-ttu-id="4f99b-132">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4f99b-132">For more information, see the following sections of the [C# language specification](~/_csharplang/spec/introduction.md):</span></span>

- [<span data-ttu-id="4f99b-133">열거형</span><span class="sxs-lookup"><span data-stu-id="4f99b-133">Enums</span></span>](~/_csharplang/spec/enums.md)
- [<span data-ttu-id="4f99b-134">열거형 값 및 작업</span><span class="sxs-lookup"><span data-stu-id="4f99b-134">Enum values and operations</span></span>](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [<span data-ttu-id="4f99b-135">열거형 논리 연산자</span><span class="sxs-lookup"><span data-stu-id="4f99b-135">Enumeration logical operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [<span data-ttu-id="4f99b-136">열거형 비교 연산자</span><span class="sxs-lookup"><span data-stu-id="4f99b-136">Enumeration comparison operators</span></span>](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [<span data-ttu-id="4f99b-137">명시적 열거형 변환</span><span class="sxs-lookup"><span data-stu-id="4f99b-137">Explicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [<span data-ttu-id="4f99b-138">암시적 열거형 변환</span><span class="sxs-lookup"><span data-stu-id="4f99b-138">Implicit enumeration conversions</span></span>](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a><span data-ttu-id="4f99b-139">참조</span><span class="sxs-lookup"><span data-stu-id="4f99b-139">See also</span></span>

- [<span data-ttu-id="4f99b-140">C# 참조</span><span class="sxs-lookup"><span data-stu-id="4f99b-140">C# reference</span></span>](../index.md)
- [<span data-ttu-id="4f99b-141">열거형 형식 문자열</span><span class="sxs-lookup"><span data-stu-id="4f99b-141">Enumeration format strings</span></span>](../../../standard/base-types/enumeration-format-strings.md)
- [<span data-ttu-id="4f99b-142">열거형 명명 규칙</span><span class="sxs-lookup"><span data-stu-id="4f99b-142">Enum naming conventions</span></span>](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [<span data-ttu-id="4f99b-143">switch 문</span><span class="sxs-lookup"><span data-stu-id="4f99b-143">switch statement</span></span>](../keywords/switch.md)
