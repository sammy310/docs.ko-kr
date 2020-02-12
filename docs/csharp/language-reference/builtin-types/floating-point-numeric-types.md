---
title: 부동 소수점 숫자 형식 - C# 참조
description: 기본 제공 C# 부동 소수점 형식의 개요
ms.date: 10/22/2019
f1_keywords:
- float
- float_CSharpKeyword
- double
- double_CSharpKeyword
- decimal_CSharpKeyword
- decimal
helpviewer_keywords:
- floating-point numbers [C#]
- ranges of floating-point types [C#]
- size of floating-point types [C#]
- types [C#], floating-point types
- float keyword [C#]
- floating-point numbers [C#], float keyword
- double data type [C#]
- decimal keyword [C#]
ms.openlocfilehash: 9c8b11f9337ee9de90f2d4d96b5be162713bfcbd
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/09/2020
ms.locfileid: "77093216"
---
# <a name="floating-point-numeric-types-c-reference"></a>부동 소수점 숫자 형식(C# 참조)

*부동 소수점 숫자 형식*은 실수를 나타냅니다. 모든 부동 소수점 숫자 형식은 [값 형식](value-types.md)입니다. 이것은 [기본 형식](value-types.md#built-in-value-types)이기도 하며, [리터럴](#real-literals)로 초기화할 수 있습니다. 모든 부동 소수점 숫자 형식은 [산술](../operators/arithmetic-operators.md), [비교](../operators/comparison-operators.md) 및 [같음](../operators/equality-operators.md) 연산자를 지원합니다.

## <a name="characteristics-of-the-floating-point-types"></a>부동 소수점 형식의 특성

C#은 다음과 같은 미리 정의된 부동 소수점 형식을 지원합니다.
  
|C# 형식/키워드|근사 범위|전체 자릿수|Size|.NET 형식|
|----------|-----------------------|---------------|--------------|--------------|
|`float`|±1.5 x 10<sup>−45</sup> ~ ±3.4 x 10<sup>38</sup>|~6-9개 자릿수|4바이트|<xref:System.Single?displayProperty=nameWithType>|
|`double`|±5.0 × 10<sup>−324</sup> ~ ±1.7 × 10<sup>308</sup>|~15-17개 자릿수|8바이트|<xref:System.Double?displayProperty=nameWithType>|
|`decimal`|±1.0 x 10<sup>-28</sup> ~ ±7.9228 x 10<sup>28</sup>|28-29개의 자릿수|16바이트|<xref:System.Decimal?displayProperty=nameWithType>|

이전 표에서 맨 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다. 서로 교환하여 사용할 수 있습니다. 예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.

```csharp
double a = 12.3;
System.Double b = 12.3;
```

각 부동 소수점 형식의 기본값은 `0`입니다. 각 부동 소수점 형식에는 해당 형식의 최소 및 최대 유한값을 제공하는 `MinValue` 및 `MaxValue` 상수가 있습니다. 또한 `float` 및 `double` 형식은 숫자가 아닌 무한 값을 나타내는 상수를 제공합니다. 예를 들어 `double` 형식은 <xref:System.Double.NaN?displayProperty=nameWithType>, <xref:System.Double.NegativeInfinity?displayProperty=nameWithType> 및 <xref:System.Double.PositiveInfinity?displayProperty=nameWithType>와 같은 상수를 제공합니다.

`decimal` 형식은 `float` 및 `double`보다 정밀도가 높고 범위가 작으므로 재무 및 통화 계산에 적합합니다.

식에서 [정수](integral-numeric-types.md) 형식과 부동 소수점 형식을 혼합할 수 있습니다. 이 경우 정수 형식이 부동 소수점 형식으로 변환됩니다. 식의 계산은 다음 규칙에 따라 수행됩니다.

- 부동 소수점 형식 중 하나가 `double`인 경우 식은 관계형 및 같음에 대한 비교에서 `double` 또는 [bool](bool.md)로 계산됩니다.
- 식에 `double` 형식이 없는 경우 식은 같음에 대한 관계형 또는 비교에서 `float` 또는 [bool](bool.md)로 계산됩니다.

부동 소수점 식에는 다음과 같은 값 집합이 포함될 수 있습니다.

- 양수 및 음수 0
- 양수 및 음수 무한대
- NaN(Not-a-Number) 값
- 한정된 0이 아닌 값의 집합

이러한 값에 대한 자세한 내용은 [IEEE](https://www.ieee.org) 웹 사이트에서 제공되는 이진 부동 소수점 연산에 대한 IEEE 표준을 참조하세요.

[표준 숫자 서식 문자열](../../../standard/base-types/standard-numeric-format-strings.md) 또는 [사용자 지정 숫자 서식 문자열](../../../standard/base-types/custom-numeric-format-strings.md)을 사용하여 부동 소수점 값의 형식을 지정할 수 있습니다.

## <a name="real-literals"></a>real 리터럴

real 리터럴의 형식은 접미사로 다음과 같이 결정됩니다.

- 접미사가 없거나 `d` 또는 `D` 접미사가 있는 리터럴은 `double` 형식입니다.
- `f` 또는 `F` 접미사가 있는 리터럴은 `float` 형식입니다.
- `m` 또는 `M` 접미사가 있는 리터럴은 `decimal` 형식입니다.

다음 코드에서는 각 예제를 보여 줍니다.

```csharp
double d = 3D;
d = 4d;
d = 3.934_001;

float f = 3_000.5F;
f = 5.4f;

decimal myMoney = 3_000.5m;
myMoney = 400.75M;
```

앞의 예제에서는 C# 7.0부터 지원되는 *숫자 구분 기호*인 `_`를 사용하는 방법도 보여 줍니다. 모든 종류의 숫자 리터럴에서 숫자 구분 기호를 사용할 수 있습니다.

또한 다음 예제와 같이 과학적 표기법을 사용하여 real 리터럴의 지수 부분을 지정할 수도 있습니다.

```csharp-interactive
double d = 0.42e2;
Console.WriteLine(d);  // output 42;

float f = 134.45E-2f;
Console.WriteLine(f);  // output: 1.3445

decimal m = 1.5E6m;
Console.WriteLine(m);  // output: 1500000
```

## <a name="conversions"></a>변환

부동 소수점 숫자 형식 간의 암시적 변환은 `float`에서 `double`로의 암시적 변환 하나뿐입니다. 그러나 [명시적 캐스트](../operators/type-testing-and-cast.md#cast-operator-)를 사용하여 부동 소수점 형식을 다른 부동 소수점 형식으로 변환할 수 있습니다. 자세한 내용은 [기본 제공 숫자 변환](numeric-conversions.md)을 참조하세요.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.

- [부동 소수점 형식](~/_csharplang/spec/types.md#floating-point-types)
- [10진 형식](~/_csharplang/spec/types.md#the-decimal-type)
- [real 리터럴](~/_csharplang/spec/lexical-structure.md#real-literals)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [값 형식](value-types.md)
- [정수 형식](integral-numeric-types.md)
- [표준 숫자 형식 문자열](../../../standard/base-types/standard-numeric-format-strings.md)
- [.NET의 숫자](../../../standard/numerics.md)
- <xref:System.Numerics.Complex?displayProperty=nameWithType>
