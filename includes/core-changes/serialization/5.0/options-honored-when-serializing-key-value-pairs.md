---
ms.openlocfilehash: 07980cf94d5de0173808da2ce44adb409fdd5419
ms.sourcegitcommit: 39b1d5f2978be15409c189a66ab30781d9082cd8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/14/2020
ms.locfileid: "92050473"
---
### <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a>PropertyNamingPolicy, PropertyNameCaseInsensitive 및 Encoder 옵션은 키-값 쌍을 직렬화 및 역직렬화할 때 적용됩니다.

<xref:System.Text.Json.JsonSerializer>는 이제 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스의 <xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 속성 이름을 직렬화할 때 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 및 <xref:System.Text.Json.JsonSerializerOptions.Encoder> 옵션을 적용합니다. 또한 <xref:System.Text.Json.JsonSerializer>는 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스를 역직렬화할 때 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 및 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> 옵션을 적용합니다.

#### <a name="change-description"></a>변경 내용 설명

##### <a name="serialization"></a>Serialization

.NET Core 3.x 버전 및 [System.Text.Json NuGet 패키지](https://www.nuget.org/packages/System.Text.Json)의 4.6.0-4.7.2 버전에서는 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 및 <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> 옵션에 관계없이 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스의 속성은 항상 "Key" 및 "Value"로 직렬화됩니다. 다음 코드 예제는 지정된 특성 이름 지정 정책이 지시하더라도 직렬화 후에는 <xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 특성이 어떻게 카멜식 대/소문자를 구분하지 *않는지*를 보여줍니다.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

.NET 5.0부터 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스를 직렬화할 때 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 및 <xref:System.Text.Json.JsonSerializerOptions.Encoder> 옵션이 적용됩니다. 다음 코드 예제는 지정된 특성 이름 지정 정책에 따라 직렬화 후 <xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 특성이 어떻게 카멜식 대/소문자를 구분하는지 보여줍니다.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

##### <a name="deserialization"></a>Deserialization

.NET Core 3.x 버전과 [System.Text.Json NuGet 패키지](https://www.nuget.org/packages/System.Text.Json)의 4.7.x 버전에서는, 예를 들어 대문자로 시작하지 않고 JSON 속성 이름이 정확하게 `Key` 및 `Value`가 아닌 경우 <xref:System.Text.Json.JsonException>이 throw됩니다. 지정된 자산 이름 지정 정책이 명시적으로 허용하더라도 예외가 throw됩니다.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

.NET 5.0부터 <xref:System.Text.Json.JsonSerializer>를 사용하여 역직렬화할 때 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 및 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> 옵션이 적용됩니다. 예를 들어, 다음 코드 조각은 지정된 속성 이름 지정 정책에서 허용하기 때문에 소문자의 <xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 속성 이름을 성공적으로 역직렬화하는 것을 보여줍니다.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

이전 버전으로 직렬화된 페이로드를 수용하기 위해 역직렬화할 때 일치하도록 "Key" 및 "Value"는 특수 대/소문자를 구분합니다. <xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 속성 이름이 다음 코드 예제의 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 옵션에 따라 카멜식 대/소문자를 구분하지 않더라도 성공적으로 역직렬화됩니다.

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

#### <a name="version-introduced"></a>도입된 버전

5.0

#### <a name="reason-for-change"></a>변경 이유

상당한 고객 피드백에서 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy>를 적용해야 한다고 나타났습니다. 완전성을 위해 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> 및 <xref:System.Text.Json.JsonSerializerOptions.Encoder> 옵션도 적용되므로 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스는 다른 POCO(Plain Old CLR Object)와 동일하게 처리됩니다.

#### <a name="recommended-action"></a>권장 조치

이 변경 내용이 방해가 되는 경우 원하는 의미 체계를 구현하는 [사용자 지정 변환기](../../../../docs/standard/serialization/system-text-json-converters-how-to.md)를 사용할 수 있습니다.

#### <a name="category"></a>범주

Serialization

#### <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

#### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Serialize`
- `Overload:System.Text.Json.JsonSerializer.SerializeAsync`
- `Overload:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes`
- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

-->
