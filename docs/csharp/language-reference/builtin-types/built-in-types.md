---
title: 기본 제공 형식- C# 참조
description: C# 기본 제공 값 및 참조 형식 배우기
ms.date: 03/15/2021
helpviewer_keywords:
- types [C#], built-in
- built-in C# types
ms.openlocfilehash: c2b1c736e17e55913ef1c593813717dd33efd6c3
ms.sourcegitcommit: 20b4565974d185c7716656a6c63e3cfdbdf4bf41
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/20/2021
ms.locfileid: "104759718"
---
# <a name="built-in-types-c-reference"></a>기본 제공 형식(C# 참조)

다음 표에서는 C# 기본 제공 [값](value-types.md) 형식을 나열합니다.

|C# 형식 키워드|.NET 형식|
|--------------|-------------------------|
|[`bool`](bool.md)|<xref:System.Boolean?displayProperty=nameWithType>|
|[`byte`](integral-numeric-types.md)|<xref:System.Byte?displayProperty=nameWithType>|
|[`sbyte`](integral-numeric-types.md)|<xref:System.SByte?displayProperty=nameWithType>|
|[`char`](char.md)|<xref:System.Char?displayProperty=nameWithType>|
|[`decimal`](floating-point-numeric-types.md)|<xref:System.Decimal?displayProperty=nameWithType>|
|[`double`](floating-point-numeric-types.md)|<xref:System.Double?displayProperty=nameWithType>|
|[`float`](floating-point-numeric-types.md)|<xref:System.Single?displayProperty=nameWithType>|
|[`int`](integral-numeric-types.md)|<xref:System.Int32?displayProperty=nameWithType>|
|[`uint`](integral-numeric-types.md)|<xref:System.UInt32?displayProperty=nameWithType>|
|[`nint`](nint-nuint.md)|<xref:System.IntPtr?displayProperty=nameWithType>|
|[`nuint`](nint-nuint.md)|<xref:System.UIntPtr?displayProperty=nameWithType>|
|[`long`](integral-numeric-types.md)|<xref:System.Int64?displayProperty=nameWithType>|
|[`ulong`](integral-numeric-types.md)|<xref:System.UInt64?displayProperty=nameWithType>|
|[`short`](integral-numeric-types.md)|<xref:System.Int16?displayProperty=nameWithType>|
|[`ushort`](integral-numeric-types.md)|<xref:System.UInt16?displayProperty=nameWithType>|

다음 표에서는 C# 기본 제공 [참조](../keywords/reference-types.md) 형식을 나열합니다.

|C# 형식 키워드|.NET 형식|
|--------------|-------------------------|
|[`object`](reference-types.md#the-object-type)|<xref:System.Object?displayProperty=nameWithType>|
|[`string`](reference-types.md#the-string-type)|<xref:System.String?displayProperty=nameWithType>|
|[`dynamic`](reference-types.md#the-dynamic-type)|<xref:System.Object?displayProperty=nameWithType>|

이전 표에서 왼쪽 열의 각 C# 형식 키워드는 해당하는 .NET 형식의 별칭입니다([nint 및 nuint](nint-nuint.md) 제외). 서로 교환하여 사용할 수 있습니다. 예를 들어 다음 선언은 동일한 형식의 변수를 선언합니다.

```csharp
int a = 123;
System.Int32 b = 123;
```

첫 번째 표의 마지막 두 행에 있는 `nint` 및 `nuint` 형식은 기본 크기 정수입니다. 이들은 지정된 .NET 형식에 의해 내부적으로 표시되지만, 각 경우에 키워드와 .NET 형식을 서로 바꿔 사용할 수 없습니다. 컴파일러는 `nint` 및 `nuint`에 대한 작업 및 변환을 포인터 형식 `System.IntPtr` 및 `System.UIntPtr`에 대해 제공하지 않는 정수 형식으로 제공합니다. 자세한 내용은 [`nint` 및 `nuint`형식](nint-nuint.md)을 참조하세요.

[`void`](void.md) 키워드는 형식이 없음을 나타냅니다. 이 키워드는 값을 반환하지 않는 메서드의 반환 형식으로 사용합니다.

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 형식의 기본값](default-values.md)
