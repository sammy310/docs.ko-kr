---
title: 정수 숫자 형식 - C# 참조
description: 각 정수 숫자 형식에 대한 범위, 스토리지 크기 및 용도에 대해 알아봅니다.
ms.date: 10/18/2019
f1_keywords:
- byte
- byte_CSharpKeyword
- sbyte_CSharpKeyword
- sbyte
- short
- short_CSharpKeyword
- ushort
- ushort_CSharpKeyword
- int_CSharpKeyword
- int
- uint
- uint_CSharpKeyword
- long_CSharpKeyword
- long
- ulong_CSharpKeyword
- ulong
helpviewer_keywords:
- integral types, C#
- Visual C#, integral types
- types [C#], integral types
- ranges of integral types [C#]
- byte keyword [C#]
- sbyte keyword [C#]
- short keyword [C#]
- ushort keyword [C#]
- int keyword [C#]
- uint keyword [C#]
- long keyword [C#]
- ulong keyword [C#]
ms.openlocfilehash: 3d4f3164d67a000123417619f3be6be455d5ab87
ms.sourcegitcommit: 1f12db2d852d05bed8c53845f0b5a57a762979c8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2019
ms.locfileid: "72579190"
---
# <a name="integral-numeric-types--c-reference"></a>정수 숫자 형식(C# 참조)

**정수 숫자 형식**은 **단순 형식**의 하위 집합이며 [*리터럴*](#integer-literals)을 사용하여 초기화할 수 있습니다. 모든 정수 형식도 값 형식입니다. 모든 정수 숫자 형식은 [산술](../operators/arithmetic-operators.md), [비트 논리](../operators/bitwise-and-shift-operators.md), [비교](../operators/comparison-operators.md) 및 [같음](../operators/equality-operators.md) 연산자를 지원합니다.

## <a name="characteristics-of-the-integral-types"></a>정수 형식의 특성

C#은 다음과 같은 미리 정의된 정수 형식을 지원합니다.

|C# 형식/키워드|범위|Size|.NET 형식|
|----------|-----------|----------|-------------|
|`sbyte`|-128 ~ 127|부호 있는 8비트 정수|<xref:System.SByte?displayProperty=nameWithType>|
|`byte`|0 ~ 255|부호 없는 8비트 정수|<xref:System.Byte?displayProperty=nameWithType>|
|`short`|–32,768 ~ 32,767|부호 있는 16비트 정수|<xref:System.Int16?displayProperty=nameWithType>|
|`ushort`|0 ~ 65,535|부호 없는 16비트 정수|<xref:System.UInt16?displayProperty=nameWithType>|
|`int`|–2,147,483,648 ~ 2,147,483,647|부호 있는 32비트 정수|<xref:System.Int32?displayProperty=nameWithType>|
|`uint`|0 ~ 4,294,967,295|부호 없는 32비트 정수|<xref:System.UInt32?displayProperty=nameWithType>|
|`long`|–9,223,372,036,854,775,808 ~ 9,223,372,036,854,775,807|부호 있는 64비트 정수|<xref:System.Int64?displayProperty=nameWithType>|
|`ulong`|0 ~ 18,446,744,073,709,551,615|부호 없는 64비트 정수|<xref:System.UInt64?displayProperty=nameWithType>|

이전 표에서 맨 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다. 서로 교환하여 사용할 수 있습니다. 예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.

```csharp
int a = 123;
System.Int32 b = 123;
```

각 정수 형식의 기본값은 `0`입니다. 각 정수 형식에는 해당 형식의 최솟값과 최댓값을 제공하는 `MinValue` 및 `MaxValue` 상수가 있습니다.

<xref:System.Numerics.BigInteger?displayProperty=nameWithType> 구조체를 사용하여 상한 또는 하한이 없는 부호 있는 정수를 나타냅니다.

## <a name="integer-literals"></a>정수 리터럴

정수 리터럴은 다음 형식일 수 있습니다.

- *10진*: 접두사가 없음
- *16진수*: `0x` 또는 `0X` 접두사 사용
- *이진*: `0b` 또는 `0B` 접두사 사용(C# 7.0 및 이후 버전에서 가능)

다음 코드에서는 각 예제를 보여 줍니다.

```csharp
var decimalLiteral = 42;
var hexLiteral = 0x2A;
var binaryLiteral = 0b_0010_1010;
```

앞의 예제에서는 C# 7.0부터 지원되는 *숫자 구분 기호*인 `_`를 사용하는 방법도 보여 줍니다. 모든 종류의 숫자 리터럴에서 숫자 구분 기호를 사용할 수 있습니다.

정수 리터럴의 형식은 접미사로 다음과 같이 결정됩니다.

- 리터럴에 접미사가 없는 경우 해당 형식은 값이 표현될 수 있는 `int`, `uint`, `long`, `ulong` 형식 중 첫 번째 형식입니다.
- 리터럴에 접미사가 `U` 또는 `u`인 경우 해당 형식은 값이 표현될 수 있는 `uint`, `ulong` 형식 중 첫 번째 형식입니다.
- 리터럴에 접미사가 `L` 또는 `l`인 경우 해당 형식은 값이 표현될 수 있는 `long`, `ulong` 형식 중 첫 번째 형식입니다.

  > [!NOTE]
  > 소문자 `l`를 접미사로 사용할 수 있습니다. 그러나 이렇게 하면 문자 `l` 및 숫자 `1`을 혼동하기 쉬우므로 컴파일러 경고가 생성됩니다. 쉽게 구별할 수 있도록 `L`을 사용합니다.

- 리터럴의 접미사가 `UL`, `Ul`, `uL`, `ul`, `LU`, `Lu`, `lU` 또는 `lu`이면 해당 형식은 `ulong`입니다.

정수 리터럴로 표시되는 값이 <xref:System.UInt64.MaxValue?displayProperty=nameWithType>를 초과하면 컴파일 오류 [CS1021](../../misc/cs1021.md)이 발생합니다.

정수 리터럴로 표시되는 값은 결정된 리터럴 형식보다 범위가 작은 유형으로 암시적으로 변환될 수 있습니다. 이는 값이 대상 형식의 범위 내에 있을 때 가능합니다.

```csharp
byte a = 17;
byte b = 300;   // CS0031: Constant value '300' cannot be converted to a 'byte'
```

앞의 예제에서 볼 수 있듯이 리터럴 값이 대상 형식의 범위 내에 있지 않으면 컴파일러 오류 [CS0031](../../misc/cs0031.md)이 발생합니다.

캐스트를 사용하여 정수 리터럴로 표시되는 값을 결정된 리터럴 형식 이외의 형식으로 변환할 수도 있습니다.

```csharp
var signedByte = (sbyte)42;
var longVariable = (long)42;
```

## <a name="conversions"></a>변환

대상 유형에는 소스 유형의 모든 값을 저장할 수 있는 두 개의 정수 유형 간에 암시적 변환(*확대 변환*이라고 함)이 있습니다. 예를 들어 `int` 값의 범위가 `long`의 적절한 하위 집합이기 때문에 `int`에서 `long`으로의 암시적 변환이 있습니다. 더 작은 부호 없는 정수 형식에서 더 큰 부호 있는 정수 형식으로 암시적 변환이 있습니다. 정수 형식에서 부동 소수점 형식으로 변환하는 암시적 변환도 있습니다.  부호 있는 정수 형식에서 부호 없는 정수 형식으로 변환하는 암시적 변환은 없습니다.

암시적 변환이 소스 유형에서 대상 유형으로 정의되지 않은 경우 명시적 캐스트를 사용하여 하나의 정수 형식을 다른 정수 형식으로 변환해야 합니다. 이를 *축소 변환*이라고 합니다. 변환이 데이터 손실을 초래할 수 있기 때문에 명시적인 사례가 필요합니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.

- [정수 형식](~/_csharplang/spec/types.md#integral-types)
- [정수 리터럴](~/_csharplang/spec/lexical-structure.md#integer-literals)

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [부동 소수점 형식](floating-point-numeric-types.md)
- [기본값 표](../keywords/default-values-table.md)
- [숫자 결과 형식 지정 표](../keywords/formatting-numeric-results-table.md)
- [기본 제공 형식 표](../keywords/built-in-types-table.md)
- [.NET의 숫자](../../../standard/numerics.md)
