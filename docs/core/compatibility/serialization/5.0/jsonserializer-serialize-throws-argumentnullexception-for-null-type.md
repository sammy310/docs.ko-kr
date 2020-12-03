---
title: '호환성이 손상되는 변경: 형식 매개 변수가 null인 경우 Serialize에서 예외를 throw함'
description: 형식 매개 변수가 있는 JsonSerialize serialization 메서드가 해당 매개 변수에 대해 null이 전달될 때마다 예외를 throw하는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 10/18/2020
ms.openlocfilehash: af2885394418072ad7efec5855490b5b80152fe6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759947"
---
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a>형식 매개 변수가 null인 경우 JsonSerializer.Serialize에서 ArgumentNullException을 throw함

<xref:System.Type> 형식의 매개 변수가 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType> 및 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 오버로드는 해당 매개 변수에 대해 `null`이 전달될 때마다 <xref:System.ArgumentNullException>을 throw합니다.

## <a name="change-description"></a>변경 내용 설명

.NET Core 3.1에서 <xref:System.Type> 매개 변수가 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> 오버로드는 `Type inputType` 매개 변수에 대해 `null`이 전달될 때 <xref:System.ArgumentNullException>을 throw하지만 `Object value` 매개 변수도 `null`인 경우에는 예외를 throw하지 않습니다. .NET 5.0부터 해당 메서드는 <xref:System.Type> 매개 변수에 대해 `null`이 전달될 때 ‘항상’ <xref:System.ArgumentNullException>을 throw합니다.

.NET Core 3.1의 동작:

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

.NET 5.0 이상의 동작:

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="reason-for-change"></a>변경 이유

`Type inputType` 매개 변수에 대해 `null`을 전달할 수 없으며 항상 <xref:System.ArgumentNullException>이 throw되어야 합니다.

## <a name="recommended-action"></a>권장 조치

해당 메서드의 `Type inputType` 매개 변수에 대해 `null`을 전달하지 않습니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
