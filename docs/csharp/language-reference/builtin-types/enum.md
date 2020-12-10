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
ms.openlocfilehash: a21bdf63247dc5fec95922de017e1d3502e08565
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599436"
---
# <a name="enumeration-types-c-reference"></a>열거형(C# 참조)

*열거형*(또는 *열거형 형식*)은 기본 [정수 숫자](integral-numeric-types.md) 형식의 명명된 상수 집합에 의해 정의되는 [값 형식](value-types.md)입니다. 열거형을 정의하려면 `enum` 키워드를 정의하고 *열거형 멤버* 의 이름을 지정합니다.

```csharp
enum Season
{
    Spring,
    Summer,
    Autumn,
    Winter
}
```

기본적으로 열거형 멤버의 연결된 상수 값은 `int` 형식입니다. 즉, 0으로 시작하고 정의 텍스트 순서에 따라 1씩 증가합니다. 다른 [정수 숫자](integral-numeric-types.md) 형식을 열거형 형식의 기본 형식으로 명시적으로 지정할 수 있습니다. 다음 예제와 같이 연결된 상수 값을 명시적으로 지정할 수도 있습니다.

```csharp
enum ErrorCode : ushort
{
    None = 0,
    Unknown = 1,
    ConnectionLost = 100,
    OutlierReading = 200
}
```

열거형 형식의 정의 내에서 메서드를 정의할 수 없습니다. 열거형 형식에 기능을 추가하려면 [확장 메서드](../../programming-guide/classes-and-structs/extension-methods.md)를 만듭니다.

0에 해당 열거형 멤버가 없는 경우에도 열거형 형식 `E`의 기본값은 식 `(E)0`에 의해 생성되는 값입니다.

열거형 형식을 사용하여 상호 배타적인 값의 집합에서의 선택 또는 선택의 조합을 나타낼 수 있습니다. 선택의 조합을 나타내려면 열거형 형식을 비트 플래그로 정의합니다.

## <a name="enumeration-types-as-bit-flags"></a>비트 플래그로서 열거형 형식

열거형 형식으로 선택의 조합을 나타내려면 개별 선택이 비트 필드가 되도록 해당 선택의 열거형 멤버를 정의합니다. 즉, 이러한 멤버의 연결된 값은 제곱이어야 합니다. 그런 다음 [비트 논리 연산자 `|` 또는 `&`](../operators/bitwise-and-shift-operators.md#enumeration-logical-operators)를 사용하여 각각 선택을 조합하거나 선택의 조합을 교차할 수 있습니다. 열거형 형식이 비트 필드를 선언한다고 표시하려면 [Flags](xref:System.FlagsAttribute) 특성을 적용합니다. 다음 예제와 같이 열거형 형식의 정의에 몇 가지 일반적인 조합을 포함할 수도 있습니다.

[!code-csharp[enum flags](snippets/shared/EnumType.cs#Flags)]

자세한 내용과 예제는 <xref:System.FlagsAttribute?displayProperty=nameWithType> API 참조 페이지 및 <xref:System.Enum?displayProperty=nameWithType> API 참조 페이지의 [비독점적 멤버 및 Flags 특성](/dotnet/api/system.enum#non-exclusive-members-and-the-flags-attribute) 섹션을 참조하세요.

## <a name="the-systemenum-type-and-enum-constraint"></a>System.Enum 형식 및 열거형 제약 조건

<xref:System.Enum?displayProperty=nameWithType> 형식은 모든 열거형 형식의 추상적 기본 클래스입니다. 이 형식은 열거형 형식 및 그 값에 대한 정보를 가져오는 여러 메서드를 제공합니다. 자세한 내용과 예제는 <xref:System.Enum?displayProperty=nameWithType> API 참조 페이지를 참조하세요.

C# 7.3부터 기본 클래스 제약 조건([열거형 제약 조건](../../programming-guide/generics/constraints-on-type-parameters.md#enum-constraints)이라고 함)에서 `System.Enum`을 사용하여 형식 매개 변수가 열거형 형식이라고 지정할 수 있습니다. 또한 열거형 형식은 형식 매개 변수가 null을 허용하지 않는 값 형식이라고 지정하는 데 사용되는 `struct` 제약 조건을 충족합니다.

## <a name="conversions"></a>변환

모든 열거형 형식에는 열거형 형식과 기본 정수 형식 간의 명시적 변환이 있습니다. 열거형 값을 기본 형식에 [캐스트](../operators/type-testing-and-cast.md#cast-expression)하는 경우, 그 결과는 열거형 멤버의 연결된 정수 값입니다.

[!code-csharp[enum conversions](snippets/shared/EnumType.cs#Conversions)]

열거형 형식에 연결된 특정 값이 포함되어 있는지 확인하려면 <xref:System.Enum.IsDefined%2A?displayProperty=nameWithType> 메서드를 사용합니다.

모든 열거형 형식에는 <xref:System.Enum?displayProperty=nameWithType> 형식의 [boxing 및 unboxing](../../programming-guide/types/boxing-and-unboxing.md) 변환이 있습니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.

- [열거형](~/_csharplang/spec/enums.md)
- [열거형 값 및 작업](~/_csharplang/spec/enums.md#enum-values-and-operations)
- [열거형 논리 연산자](~/_csharplang/spec/expressions.md#enumeration-logical-operators)
- [열거형 비교 연산자](~/_csharplang/spec/expressions.md#enumeration-comparison-operators)
- [명시적 열거형 변환](~/_csharplang/spec/conversions.md#explicit-enumeration-conversions)
- [암시적 열거형 변환](~/_csharplang/spec/conversions.md#implicit-enumeration-conversions)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [열거형 형식 문자열](../../../standard/base-types/enumeration-format-strings.md)
- [디자인 지침 - 열거형 디자인](../../../standard/design-guidelines/enum.md)
- [디자인 지침 - 열거형 명명 규칙](../../../standard/design-guidelines/names-of-classes-structs-and-interfaces.md#naming-enumerations)
- [switch 문](../keywords/switch.md)
