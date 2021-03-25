---
description: C#의 기본 제공 숫자 형식 간 암시적 및 명시적 변환에 대해 알아봅니다.
title: 기본 제공 숫자 변환 - C# 참조
ms.date: 03/17/2021
helpviewer_keywords:
- implicit numeric conversions [C#]
- explicit numeric conversion [C#]
- numeric conversions [C#], implicit
- numeric conversions [C#], explicit
- conversions [C#], implicit numeric
- conversions [C#], explicit numeric
ms.openlocfilehash: 5ff0289f5365a7d3d334dd0130b3b0efcdf34c60
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759692"
---
# <a name="built-in-numeric-conversions-c-reference"></a>기본 제공 숫자 변환(C# 참조)

C#에서는 [정수](integral-numeric-types.md) 및 [부동 소수점](floating-point-numeric-types.md) 숫자 형식 집합을 제공합니다. 두 숫자 형식 간에는 암시적 또는 명시적 변환이 있습니다. 명시적 변환을 수행하려면 [캐스트 식](../operators/type-testing-and-cast.md#cast-expression) 사용해야 합니다.

## <a name="implicit-numeric-conversions"></a>암시적 숫자 변환

다음 표에서는 기본 제공 숫자 형식 간의 미리 정의된 암시적 숫자 변환을 보여 줍니다.

|시작|대상|
|----------|--------|
|[sbyte](integral-numeric-types.md)|`short`, `int`, `long`, `float`, `double`, `decimal` 또는 `nint`|
|[byte](integral-numeric-types.md)|`short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `decimal`, `nint` 또는 `nuint`|
|[short](integral-numeric-types.md)|`int`, `long`, `float`, `double` 또는 `decimal` 또는 `nint`|
|[ushort](integral-numeric-types.md)|`int`, `uint`, `long`, `ulong`, `float`, `double` 또는 `decimal`, `nint` 또는 `nuint`|
|[int](integral-numeric-types.md)|`long`, `float`, `double` 또는 `decimal`, `nint`|
|[uint](integral-numeric-types.md)|`long`, `ulong`, `float`, `double` 또는 `decimal` 또는 `nuint`|
|[long](integral-numeric-types.md)|`float`, `double`또는 `decimal`|
|[ulong](integral-numeric-types.md)|`float`, `double`또는 `decimal`|
|[float](floating-point-numeric-types.md)|`double`|
|[nint](nint-nuint.md)|`long`, `float`, `double` 또는 `decimal`|
|[nuint](nint-nuint.md)|`ulong`, `float`, `double` 또는 `decimal`|

> [!NOTE]
> `int`, `uint`, `long`, `ulong`, `nint` 또는 `nuint`에서 `float`로 암시적으로 변환하거나 `long`, `ulong`, `nint` 또는 `nuint`에서 `double`로 암시적으로 변환하는 경우 정밀도가 손실될 수도 있지만, 자릿수 손실은 없습니다. 다른 암시적 숫자 변환 시에는 정보 손실이 없습니다.

다음 사항에도 유의하세요.

- [정수 숫자 형식](integral-numeric-types.md)을 [부동 소수점 숫자 형식](floating-point-numeric-types.md)으로 암시적으로 변환할 수 있습니다.

- `byte` 및 `sbyte` 형식으로의 암시적 변환은 없습니다. `double` 및 `decimal` 형식에서 암시적 변환은 없습니다.

- `decimal` 형식과 `float` 또는 `double` 형식 간의 암시적 변환은 없습니다.

- 대상 형식의 범위 내에 있는 경우 `int` 형식의 상수 식 값(예: 정수 리터럴로 표시된 값)을 `sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong`, `nint` 또는 `nuint`으로 암시적으로 변환할 수 있습니다.

  ```csharp
  byte a = 13;
  byte b = 300;  // CS0031: Constant value '300' cannot be converted to a 'byte'
  ```

  위 예제에서 볼 수 있듯이, 상수 값이 대상 형식의 범위 내에 있지 않으면 컴파일러 오류 [CS0031](../../misc/cs0031.md)이 발생합니다.

## <a name="explicit-numeric-conversions"></a>명시적 숫자 변환

다음 표에서는 [암시적 변환](#implicit-numeric-conversions)이 없는 기본 제공 숫자 형식 간의 미리 정의된 명시적 변환을 보여 줍니다.

|시작|대상|
|----------|--------|
|[sbyte](integral-numeric-types.md)|`byte`, `ushort`, `uint` 또는 `ulong` 또는 `nuint`|
|[byte](integral-numeric-types.md)|`sbyte`|
|[short](integral-numeric-types.md)|`sbyte`, `byte`, `ushort`, `uint`, `ulong` 또는 `nuint`|
|[ushort](integral-numeric-types.md)|`sbyte`, `byte`또는 `short`|
|[int](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `uint`, `ulong` 또는 `nuint`|
|[uint](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort` 또는 `int`|
|[long](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong`, `nint` 또는 `nuint`|
|[ulong](integral-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `nint` 또는 `nuint`|
|[float](floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `decimal`, `nint` 또는 `nuint`|
|[double](floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `decimal`, `nint` 또는 `nuint`|
|[decimal](floating-point-numeric-types.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long`, `ulong`, `float`, `double`, `nint` 또는 `nuint`|
|[nint](nint-nuint.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `ulong` 또는 `nuint`|
|[nuint](nint-nuint.md)|`sbyte`, `byte`, `short`, `ushort`, `int`, `uint`, `long` 또는 `nint`|

> [!NOTE]
> 명시적 숫자 변환으로 인해 데이터가 손실되거나 예외(일반적으로 <xref:System.OverflowException>)가 throw될 수 있습니다.

다음 사항에도 유의하세요.

- 정수 형식의 값을 다른 정수 형식으로 변환하면 결과는 오버플로 [검사 컨텍스트](../keywords/checked-and-unchecked.md)에 따라 달라집니다. 확인된 컨텍스트에서 소스 값이 대상 형식의 범위 내에 있으면 변환이 성공합니다. 그렇지 않으면 <xref:System.OverflowException>이 throw됩니다. 확인되지 않은 컨텍스트에서 변환은 항상 성공하고 다음과 같이 진행됩니다.

  - 소스 형식이 대상 형식보다 큰 경우 소스 값은 가장 중요한 비트인 해당 "extra"를 삭제함으로써 잘립니다. 그런 다음, 결과는 대상 형식의 값으로 처리됩니다.

  - 소스 형식이 대상 형식보다 작은 경우 소스 값이 대상 형식과 크기가 같도록 부호 확장 또는 0 확장됩니다. 부호 확장은 소스 형식이 서명된 경우 사용되며, 소스 형식이 서명되지 않은 경우 0 확장이 사용됩니다. 그런 다음, 결과는 대상 형식의 값으로 처리됩니다.

  - 소스 형식이 대상 형식과 동일한 크기인 경우 소스 값은 대상 형식의 값으로 처리됩니다.

- `decimal` 값을 정수 형식으로 변환하면, 이 값은 0을 향한 방향으로 가장 가까운 정수값으로 반올림됩니다. 결과 정수 값이 대상 형식 범위에서 벗어났을 경우 <xref:System.OverflowException>이 throw됩니다.

- `double` 또는 `float` 값을 정수 형식으로 변환하면, 이 값은 0을 향한 방향으로 가장 가까운 정수값으로 반올림됩니다. 결과 정수 값이 대상 형식 범위에서 벗어났을 경우 결과는 오버플로 [검사 컨텍스트](../keywords/checked-and-unchecked.md)에 따라 달라집니다. Checked 컨텍스트에서는 <xref:System.OverflowException>이 throw됩니다. 반면 Unchecked 컨텍스트에서 결과는 지정되지 않은 대상 형식 값이 됩니다.

- `double`을 `float`로 변환할 경우 `double` 값을 가장 가까운 `float` 값으로 반올림합니다. `double` 값이 너무 크거나 작아서 `float` 형식에 맞지 않는 경우 결과 값은 0 또는 무한대가 됩니다.

- `float` 또는 `double`을 `decimal`로 변환할 경우 소스 값을 `decimal` 표현으로 변환한 다음 필요한 경우 가장 가까운 소수점 이하 28번째 자리로 반올림합니다. 소스 값에 따라 다음 결과 중 하나가 발생할 수 있습니다.

  - 소스 값이 너무 작아서 `decimal`로 나타낼 수 없을 경우 결과 값은 0이 됩니다.

  - 소스 값이 NaN(숫자가 아님), 무한대 또는 너무 커서 `decimal`로 나타낼 수 없을 경우 <xref:System.OverflowException>을 throw합니다.

- `decimal`을 `float` 또는 `double`로 변환하는 경우 소스 값이 각각 가장 가까운 `float` 또는 `double` 값으로 반올림됩니다.

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 다음 섹션을 참조하세요.

- [암시적 숫자 변환](~/_csharplang/spec/conversions.md#implicit-numeric-conversions)
- [명시적 숫자 변환](~/_csharplang/spec/conversions.md#explicit-numeric-conversions)

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [캐스팅 및 형식 변환](../../programming-guide/types/casting-and-type-conversions.md)
