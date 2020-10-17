---
ms.openlocfilehash: 5b49dcae45e44bfd9ec3e150ad25c3f21d62c18e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955341"
---
### <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a>형식 매개 변수가 null인 경우 JsonSerializer.Serialize에서 ArgumentNullException을 throw함

<xref:System.Type> 매개 변수가 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 오버로드는 <xref:System.Type> 매개 변수에 대해 `null`이 전달될 때마다 이제 <xref:System.ArgumentNullException>을 throw합니다.

#### <a name="change-description"></a>변경 내용 설명

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

#### <a name="version-introduced"></a>도입된 버전

5.0

#### <a name="reason-for-change"></a>변경 이유

`Type inputType` 매개 변수에 대해 `null`을 전달할 수 없으며 항상 <xref:System.ArgumentNullException>이 throw되어야 합니다.

#### <a name="recommended-action"></a>권장 조치

해당 메서드의 `Type inputType` 매개 변수에 대해 `null`을 전달하지 않습니다.

#### <a name="category"></a>범주

Serialization

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

-->
