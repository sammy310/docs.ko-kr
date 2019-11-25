---
title: -.Net을 사용 하 여 C# JSON을 serialize 및 deserialize 하는 방법
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 3d3dc0011562e25854938aff857f2832a5978b49
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283338"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a>.NET에서 JSON을 serialize 및 deserialize 하는 방법

이 문서에서는 <xref:System.Text.Json> 네임 스페이스를 사용 하 여 JavaScript Object Notation (JSON)로 serialize 및 deserialize 하는 방법을 보여 줍니다.

지침 및 샘플 코드는 [ASP.NET Core](/aspnet/core/)와 같은 프레임 워크가 아닌 라이브러리를 직접 사용 합니다.

대부분의 serialization 샘플 코드는 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>를 `true` 하 여 JSON (사람이 가독성을 위해 들여쓰기 및 공백 포함)을 "잘 인쇄" 하도록 설정 합니다. 프로덕션 사용을 위해 일반적으로이 설정에 `false`의 기본값을 적용 합니다.

## <a name="namespaces"></a>네임스페이스

<xref:System.Text.Json> 네임 스페이스에는 모든 진입점과 기본 형식이 포함 되어 있습니다. <xref:System.Text.Json.Serialization> 네임 스페이스에는 serialization 및 deserialization과 관련 된 고급 시나리오 및 사용자 지정을 위한 특성 및 Api가 포함 되어 있습니다. 이 문서에 표시 된 코드 예제에는 다음 네임 스페이스 중 하나 또는 둘 다에 대 한 `using` 지시문이 필요 합니다.

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<xref:System.Runtime.Serialization> 네임 스페이스의 특성은 현재 `System.Text.Json`에서 지원 되지 않습니다.

## <a name="how-to-write-net-objects-to-json-serialize"></a>JSON에 .NET 개체를 작성 하는 방법 (직렬화)

JSON을 문자열 또는 파일에 쓰려면 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드를 호출 합니다.

다음 예제에서는 JSON을 문자열로 만듭니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

다음 예제에서는 동기 코드를 사용 하 여 JSON 파일을 만듭니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

다음 예제에서는 비동기 코드를 사용 하 여 JSON 파일을 만듭니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

앞의 예제에서는 serialize 되는 형식에 대 한 형식 유추를 사용 합니다. `Serialize()` 오버 로드는 제네릭 형식 매개 변수를 사용 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a>Serialization 예제

컬렉션 및 중첩 된 클래스를 포함 하는 클래스의 예제는 다음과 같습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

이전 형식의 인스턴스를 serialize 하는 JSON 출력은 다음 예제와 같습니다. JSON 출력은 기본적으로 축소 되어 있습니다. 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

다음 예제에서는 동일한 JSON (공백 및 들여쓰기를 사용 하 여 잘 인쇄 됨)을 보여 줍니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a>U t f-8로 직렬화

U t f-8로 serialize 하려면 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 메서드를 호출 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<xref:System.Text.Json.Utf8JsonWriter>를 사용 하는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버 로드도 사용할 수 있습니다.

U t f-8로 serialize 하는 것은 문자열 기반 메서드를 사용 하는 것 보다 약 5-10% 더 빠릅니다. 차이점은 바이트 (u t f-8)를 문자열 (UTF-16)로 변환할 필요가 없기 때문입니다.

## <a name="serialization-behavior"></a>Serialization 동작

* 기본적으로 모든 public 속성이 직렬화 됩니다. [제외할 속성을 지정할](#exclude-properties-from-serialization)수 있습니다.
* [기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) 는 ascii가 아닌 문자, ascii 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프 되어야 하는 문자를 이스케이프 합니다.
* 기본적으로 JSON은 축소 되어 있습니다. [JSON을 잘 인쇄할](#serialize-to-formatted-json)수 있습니다.
* 기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치 합니다. [JSON 이름 대/소문자를 사용자 지정할](#customize-json-names-and-values)수 있습니다.
* 순환 참조가 감지 되 고 예외가 throw 됩니다. 자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [순환 참조에 대 한 문제 38579](https://github.com/dotnet/corefx/issues/38579) 을 참조 하세요.
* 현재는 필드가 제외 됩니다.

지원 되는 형식은 다음과 같습니다.

* 숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식입니다.
* 사용자 정의 [일반 이전 CLR 개체 (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).
* 1 차원 및 가변 배열 (`ArrayName[][]`)
* `TValue` `object`, `JsonElement`또는 POCO 인 `Dictionary<string,TValue>` 합니다.
* 다음 네임 스페이스의 컬렉션입니다. 자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [컬렉션 지원에 대 한 문제](https://github.com/dotnet/corefx/issues/36643) 를 참조 하세요.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

추가 형식을 처리 하거나 기본 변환기에서 지원 하지 않는 기능을 제공 하는 [사용자 지정 변환기를 구현할](system-text-json-converters-how-to.md) 수 있습니다.

## <a name="how-to-read-json-into-net-objects-deserialize"></a>JSON을 .NET 개체로 읽는 방법 (deserialize)

문자열이 나 파일에서 deserialize 하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 호출 합니다.

다음 예제에서는 문자열에서 JSON을 읽고 [serialization 예제](#serialization-example)에 대해 앞에서 설명한 `WeatherForecast` 클래스의 인스턴스를 만듭니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

동기 코드를 사용 하 여 파일에서 deserialize 하려면 다음 예제와 같이 파일을 문자열로 읽습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

비동기 코드를 사용 하 여 파일에서 deserialize 하려면 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 메서드를 호출 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a>U t f-8에서 Deserialize

U t f-8에서 deserialize 하려면 다음 예제와 같이 `Utf8JsonReader` 또는 `ReadOnlySpan<byte>`를 사용 하는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 오버 로드를 호출 합니다. 이 예에서는 JSON이 jsonUtf8Bytes 이라는 바이트 배열에 있다고 가정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a>Deserialization 동작

* 기본적으로 속성 이름 일치는 대/소문자를 구분 합니다. [대/소문자](#case-insensitive-property-matching)를 구분 하지 않도록 지정할 수 있습니다.
* JSON에 읽기 전용 속성에 대 한 값이 포함 된 경우에는이 값이 무시 되 고 예외가 throw 되지 않습니다.
* 매개 변수가 없는 생성자가 없는 참조 형식으로의 Deserialization은 지원 되지 않습니다.
* 변경할 수 없는 개체 또는 읽기 전용 속성에 대 한 Deserialization은 지원 되지 않습니다. 자세한 내용은 github의 dotnet/corefx 리포지토리에서 [읽기 전용 속성 지원](https://github.com/dotnet/corefx/issues/38163) 에 대 한 [변경 불가능 개체 지원](https://github.com/dotnet/corefx/issues/38569) 및 문제 38163의 github 문제 38569을 참조 하세요.
* 기본적으로 열거형은 숫자로 지원 됩니다. [열거형 이름을 문자열로 serialize](#enums-as-strings)할 수 있습니다.
* 필드는 지원 되지 않습니다.
* 기본적으로 JSON의 주석이 나 후행 쉼표는 예외를 throw 합니다. [주석과 후행 쉼표를 허용할](#allow-comments-and-trailing-commas)수 있습니다.
* [기본 최대 깊이](xref:System.Text.Json.JsonReaderOptions.MaxDepth) 는 64입니다.

기본 변환기에서 지원 하지 않는 기능을 제공 하기 위해 [사용자 지정 변환기를 구현할](system-text-json-converters-how-to.md) 수 있습니다.

## <a name="serialize-to-formatted-json"></a>형식이 지정 된 JSON으로 직렬화

JSON 출력을 잘 인쇄 하려면 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>를 `true`로 설정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

다음은 serialize 되 고 잘 인쇄 되는 JSON 출력의 예제 형식입니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a>JSON 이름 및 값 사용자 지정

기본적으로 속성 이름 및 사전 키는 대/소문자를 포함 하 여 JSON 출력에서 변경 되지 않습니다. 열거형 값은 숫자로 표시 됩니다. 이 섹션에서는 다음을 수행 하는 방법을 설명 합니다.

* [개별 속성 이름 사용자 지정](#customize-individual-property-names)
* [모든 속성 이름을 카멜식 대/소문자로 변환](#use-camel-case-for-all-json-property-names)
* [사용자 지정 속성 명명 정책 구현](#use-a-custom-json-property-naming-policy)
* [사전 키를 카멜식 대/소문자로 변환](#camel-case-dictionary-keys)
* [문자열 및 카멜식 대/소문자로 열거형 변환](#enums-as-strings) 

JSON 속성 이름 및 값을 특수 하 게 처리 해야 하는 다른 시나리오의 경우 [사용자 지정 변환기를 구현할](system-text-json-converters-how-to.md)수 있습니다.

### <a name="customize-individual-property-names"></a>개별 속성 이름 사용자 지정

개별 속성의 이름을 설정 하려면 [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) 특성을 사용 합니다.

직렬화 및 결과 JSON의 예는 다음과 같습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

이 특성에 의해 설정 된 속성 이름:

* Serialization 및 deserialization을 위해 양방향으로 적용 됩니다.
* 속성 명명 정책 보다 우선 합니다.

### <a name="use-camel-case-for-all-json-property-names"></a>모든 JSON 속성 이름에 카멜식 대/소문자 사용

모든 JSON 속성 이름에 카멜식 대/소문자를 사용 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>를 `JsonNamingPolicy.CamelCase`로 설정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

직렬화 및 JSON 출력에 대 한 예제 클래스는 다음과 같습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

카멜식 대/소문자 속성 명명 정책:

* Serialization 및 deserialization에 적용 됩니다.
* `[JsonPropertyName]` 특성에 의해 재정의 됩니다. 이 때문에이 예제에서 JSON 속성 이름 `Wind`는 카멜식 대/소문자가 아닙니다.

### <a name="use-a-custom-json-property-naming-policy"></a>사용자 지정 JSON 속성 명명 정책 사용

사용자 지정 JSON 속성 명명 정책을 사용 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonNamingPolicy>에서 파생 되는 클래스를 만들고 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 메서드를 재정의 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

그런 다음 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 속성을 명명 정책 클래스의 인스턴스로 설정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

직렬화 및 JSON 출력에 대 한 예제 클래스는 다음과 같습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

JSON 속성 명명 정책:

* Serialization 및 deserialization에 적용 됩니다.
* `[JsonPropertyName]` 특성에 의해 재정의 됩니다. 이 때문에이 예제의 JSON 속성 이름 `Wind` 대문자는 아닙니다.

### <a name="camel-case-dictionary-keys"></a>카멜식 대/소문자 사전 키

Serialize 할 개체의 속성이 `Dictionary<string,TValue>`형식이 면 `string` 키를 카멜식 대/소문자로 변환할 수 있습니다. 이렇게 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy>를 `JsonNamingPolicy.CamelCase`로 설정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

키-값 쌍 `"HotMinTemp", 40` `"ColdMinTemp", 20` 키-값 쌍이 있는 `TemperatureRanges` 라는 사전이 포함 된 개체를 serialize 하면 다음 예제와 같이 JSON 출력이 생성 됩니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

사전 키에 대 한 카멜식 대/소문자 명명 정책은 serialization에만 적용 됩니다. 사전을 deserialize 하면 `DictionaryKeyPolicy`에 대 한 `JsonNamingPolicy.CamelCase` 지정 하더라도 키가 JSON 파일과 일치 합니다.

### <a name="enums-as-strings"></a>문자열로 된 열거형

기본적으로 열거형은 숫자로 serialize 됩니다. 열거형 이름을 문자열로 serialize 하려면 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>을 사용 합니다.

예를 들어, 열거형을 포함 하는 다음 클래스를 serialize 해야 한다고 가정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

요약이 `Hot`되는 경우 기본적으로 직렬화 된 JSON에는 숫자 값 3이 있습니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

다음 샘플 코드는 숫자 값 대신 열거형 이름을 직렬화 하 고 이름을 카멜식 case로 변환 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

결과 JSON은 다음 예제와 같습니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

다음 예제와 같이 열거형 문자열 이름도 deserialize 할 수 있습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a>Serialization에서 속성 제외

기본적으로 모든 public 속성이 직렬화 됩니다. JSON 출력에 표시 하지 않으려는 경우 몇 가지 옵션이 있습니다. 이 섹션에서는 다음을 제외 하는 방법을 설명 합니다.

* [개별 속성](#exclude-individual-properties)
* [모든 읽기 전용 속성](#exclude-all-read-only-properties)
* [모든 null 값 속성](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a>개별 속성 제외

개별 속성을 무시 하려면 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성을 사용 합니다.

다음은 serialize 및 JSON 출력에 대 한 예제 형식입니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a>모든 읽기 전용 속성을 제외 합니다.

공용 setter가 아닌 공용 getter가 포함 된 속성은 읽기 전용입니다. 모든 읽기 전용 속성을 제외 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>를 `true`으로 설정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

다음은 serialize 및 JSON 출력에 대 한 예제 형식입니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

이 옵션은 serialization에만 적용 됩니다. Deserialization을 수행 하는 동안 읽기 전용 속성은 기본적으로 무시 됩니다.

### <a name="exclude-all-null-value-properties"></a>모든 null 값 속성 제외

모든 null 값 속성을 제외 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 속성을 `true`로 설정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

직렬화 및 JSON 출력에 대 한 예제 개체는 다음과 같습니다.

|속성 |값  |
|---------|---------|
| 날짜    | 오전 8/1/2019 12:00:00-07:00|
| TemperatureCelsius| 25 |
| 요약| null|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

이 설정은 serialization 및 deserialization에 적용 됩니다. Deserialization에 미치는 영향에 대 한 자세한 내용은 [deserialize 할 때 Null 무시](#ignore-null-when-deserializing)를 참조 하세요.

## <a name="customize-character-encoding"></a>문자 인코딩 사용자 지정

기본적으로 serializer는 ASCII가 아닌 문자를 모두 이스케이프 합니다.  즉, `xxxx`가 문자의 유니코드 코드 인 `\uxxxx`로 대체 합니다.  예를 들어 `Summary` 속성이 키릴 자모 жарко로 설정 된 경우이 예제와 같이 `WeatherForecast` 개체가 serialize 됩니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a>언어 문자 집합 Serialize

이스케이프 하지 않고 하나 이상의 언어의 문자 집합을 serialize 하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>의 인스턴스를 만들 때 [유니코드 범위](xref:System.Text.Unicode.UnicodeRanges) 를 지정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

이 코드는 키릴 자모 또는 그리스어 문자를 이스케이프 하지 않습니다. `Summary` 속성이 키릴 자모 жарко로 설정 된 경우 `WeatherForecast` 개체는 다음 예제와 같이 serialize 됩니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

이스케이프 하지 않고 모든 언어 집합을 serialize 하려면 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>을 사용 합니다.

### <a name="serialize-specific-characters"></a>특정 문자 Serialize

대안은 이스케이프 되지 않고에서 허용 하려는 개별 문자를 지정 하는 것입니다. 다음 예제에서는 жарко의 처음 두 자만 직렬화 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

앞의 코드에서 생성 된 JSON의 예는 다음과 같습니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a>모든 문자를 직렬화 합니다.

이스케이프를 최소화 하기 위해 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>를 사용할 수 있습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> 기본 인코더와 비교할 때 `UnsafeRelaxedJsonEscaping` 인코더는 문자를 이스케이프 되지 않은 통과할 수 있도록 허용 하는 것 보다 더 허용 됩니다.
>
> * `<`, `>`, `&`및 `'`과 같은 HTML 구분 문자를 이스케이프 하지 않습니다.
> * 클라이언트와 서버에서 *문자 집합*에 동의 하지 않을 수 있는 것과 같은 XSS 또는 정보 공개 공격에 대해 심층 방어를 추가로 보호 하는 기능은 제공 하지 않습니다.
>
> 클라이언트에서 결과 페이로드를 u t f-8로 인코딩된 JSON으로 해석 하는 것으로 알려진 경우에만 안전 하지 않은 인코더를 사용 합니다. 예를 들어 서버에서 응답 헤더 `Content-Type: application/json; charset=utf-8`보내는 경우이를 사용할 수 있습니다. 원시 `UnsafeRelaxedJsonEscaping` 출력을 HTML 페이지나 `<script>` 요소로 내보낼 수는 없습니다.

## <a name="serialize-properties-of-derived-classes"></a>파생 클래스의 속성 직렬화

컴파일 시간에 serialize 할 형식을 지정 하는 경우 다형성 serialization이 지원 되지 않습니다. 예를 들어 `WeatherForecast` 클래스와 파생 클래스 `WeatherForecastWithWind`있다고 가정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

컴파일 시간에 `Serialize` 메서드의 형식 인수를 `WeatherForecast`한다고 가정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

이 시나리오에서는 `weatherForecast` 개체가 실제로 `WeatherForecastWithWind` 개체인 경우에도 `WindSpeed` 속성이 serialize 되지 않습니다. 기본 클래스 속성만 직렬화 됩니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

이 동작은 파생 된 런타임 생성 형식에서 실수로 데이터가 노출 되는 것을 방지 하는 데 사용 됩니다.

파생 형식의 속성을 serialize 하려면 다음 방법 중 하나를 사용 합니다.

* 런타임에 형식을 지정할 수 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버 로드를 호출 합니다.

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* `object`로 serialize 될 개체를 선언 합니다.

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

위의 예제 시나리오에서 두 가지 방법으로 인해 `WindSpeed` 속성이 JSON 출력에 포함 됩니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

다형 deserialization에 대 한 자세한 내용은 [다형성 Deserialization 지원](system-text-json-converters-how-to.md#support-polymorphic-deserialization)을 참조 하세요.

## <a name="allow-comments-and-trailing-commas"></a>주석과 후행 쉼표 허용

기본적으로 주석 및 후행 쉼표는 JSON에서 허용 되지 않습니다. JSON에서 주석을 허용 하려면 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 속성을 `JsonCommentHandling.Skip`로 설정 합니다.
그리고 후행 쉼표를 허용 하려면 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 속성을 `true`로 설정 합니다. 다음 예제에서는 두 가지를 모두 허용 하는 방법을 보여 줍니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

다음은 주석과 후행 쉼표를 사용 하는 JSON 예제입니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a>대/소문자를 구분 하지 않는 속성 일치

기본적으로 deserialization은 JSON과 대상 개체 속성 간에 일치 하는 대/소문자를 구분 하는 속성 이름을 찾습니다. 이 동작을 변경 하려면 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType>를 `true`으로 설정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

카멜식 대/소문자 속성 이름을 사용 하는 JSON 예제는 다음과 같습니다. 파스칼식 대/소문자 속성 이름을 포함 하는 다음 형식으로 deserialize 할 수 있습니다.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a>오버플로 JSON 처리

Deserialize 하는 동안 대상 형식의 속성으로 표시 되지 않는 데이터를 JSON에 받을 수 있습니다. 예를 들어 대상 형식이 다음과 같다고 가정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

Deserialize 할 JSON은 다음과 같습니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

표시 된 형식에 표시 된 JSON을 deserialize 하는 경우 `DatesAvailable` 및 `SummaryWords` 속성은 이동 하지 않으며 손실 됩니다. 이러한 속성과 같은 추가 데이터를 캡처하려면 `Dictionary<string,object>` 또는 `Dictionary<string,JsonElement>`형식의 속성에 [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) 특성을 적용 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

앞에서 설명한 JSON을이 샘플 형식으로 deserialize 하는 경우 추가 데이터는 `ExtensionData` 속성의 키-값 쌍이 됩니다.

|속성 |값  |메모  |
|---------|---------|---------|
| 날짜    | 오전 8/1/2019 12:00:00-07:00||
| TemperatureCelsius| 0 | 대/소문자를 구분 하는 불일치 (JSON의`temperatureCelsius`) 이므로 속성은 설정 되지 않습니다. |
| 요약 | 핫스폿을 ||
| ExtensionData | temperatureCelsius: 25 |Case가 일치 하지 않기 때문에이 JSON 속성은 추가 이며 사전에서 키-값 쌍이 됩니다.|
|| DatesAvailable:<br>  오전 8/1/2019 12:00:00-07:00<br>오전 8/2/2019 12:00:00-07:00 |JSON의 추가 속성은 키-값 쌍이 되며 배열은 값 개체로 사용 됩니다.|
| |요약 단어:<br>표<br>바람<br>Humid |JSON의 추가 속성은 키-값 쌍이 되며 배열은 값 개체로 사용 됩니다.|

대상 개체가 serialize 되 면 확장 데이터 키 값 쌍은 수신 JSON에 있는 것 처럼 JSON 속성이 됩니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

`ExtensionData` 속성 이름이 JSON에 표시 되지 않습니다. 이 동작을 통해 JSON은 deserialize 되지 않는 추가 데이터를 잃지 않고도 라운드트립을 수행할 수 있습니다.

## <a name="ignore-null-when-deserializing"></a>Deserialize 할 때 null 무시

기본적으로 JSON의 속성이 null 이면 대상 개체의 해당 속성이 null로 설정 됩니다. 일부 시나리오에서는 대상 속성에 기본값이 있을 수 있으며 null 값이 기본값을 재정의 하지 않도록 합니다.

예를 들어 다음 코드는 대상 개체를 나타냅니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

다음 JSON을 deserialize 한다고 가정 합니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Deserialization 후 `WeatherForecastWithDefault` 개체의 `Summary` 속성은 null입니다.

이 동작을 변경 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>를 `true`로 설정 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

이 옵션을 사용 하는 경우 `WeatherForecastWithDefault` 개체의 `Summary` 속성이 deserialization 후의 기본값 "요약 없음"입니다.

JSON의 Null 값은 유효한 경우에만 무시 됩니다. Null을 허용 하지 않는 값 형식에 대 한 Null 값은 예외를 발생 시킵니다. 자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [nullable이 아닌 값 형식에 대 한 문제 40922](https://github.com/dotnet/corefx/issues/40922) 을 참조 하세요.

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a>Utf8JsonReader, Utf8JsonWriter 및 JsonDocument

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>는 `ReadOnlySpan<byte>`에서 읽어온 UTF-8 인코드된 JSON 텍스트를 위한 고성능, 저할당, 전달 전용 판독기입니다. `Utf8JsonReader`는 사용자 지정 파서 및 deserializers를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다. <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonReader`를 사용 합니다.

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>는 `String`, `Int32`및 `DateTime`같은 일반적인 .NET 유형에 서 UTF-8 인코딩 JSON 텍스트를 작성 하는 고성능 방법입니다. 기록기는 사용자 지정 serializer를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다. <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonWriter`를 사용 합니다.

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>는 `Utf8JsonReader`를 사용 하 여 읽기 전용 문서 개체 모델 (DOM)를 빌드하는 기능을 제공 합니다. DOM은 JSON 페이로드의 데이터에 대 한 임의 액세스를 제공 합니다. 페이로드를 구성 하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다. `JsonElement` 형식은 JSON 텍스트를 일반적인 .NET 형식으로 변환 하는 Api와 함께 배열 및 개체 열거자를 제공 합니다. `JsonDocument` <xref:System.Text.Json.JsonDocument.RootElement> 속성을 노출 합니다.

다음 섹션에서는 JSON을 읽고 쓰기 위해 이러한 도구를 사용 하는 방법을 보여 줍니다.

## <a name="use-jsondocument-for-access-to-data"></a>JsonDocument를 사용 하 여 데이터 액세스

다음 예제에서는 JSON 문자열에 있는 데이터에 대 한 임의 액세스를 위해 <xref:System.Text.Json.JsonDocument> 클래스를 사용 하는 방법을 보여 줍니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

위의 코드는:

* JSON을 분석 하는 것이 `jsonString`라는 문자열에 있다고 가정 합니다.
* `Grade` 속성이 있는 `Students` 배열의 개체에 대 한 평균 등급을 계산 합니다. 
* 등급이 없는 학생의 기본 등급 (70)을 할당 합니다.
* 각 반복으로 `count` 변수를 증가 시켜 학생 수를 계산 합니다. 다른 방법은 다음 예제와 같이 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>를 호출 하는 것입니다.

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

이 코드에서 처리 하는 JSON의 예는 다음과 같습니다.

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a>JsonDocument를 사용 하 여 JSON 쓰기

다음 예제에서는 <xref:System.Text.Json.JsonDocument>에서 JSON을 작성 하는 방법을 보여 줍니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

위의 코드는:

* JSON 파일을 읽고, `JsonDocument`에 데이터를 로드 하 고, 서식 있는 (예쁜 인쇄) JSON을 파일에 씁니다.
* <xref:System.Text.Json.JsonDocumentOptions>를 사용 하 여 입력 JSON의 주석이 허용 되지만 무시 되도록 지정 합니다.
* 완료 되 면 작성기에서 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>를 호출 합니다. 또는 삭제 될 때 작성자가 autoflush 수 있도록 하는 것이 좋습니다. 

예제 코드에서 처리할 JSON 입력의 예는 다음과 같습니다.

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

결과는 다음과 같이 잘 인쇄 된 JSON 출력입니다.

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a>Utf8JsonWriter 사용

다음 예제에서는 <xref:System.Text.Json.Utf8JsonWriter> 클래스를 사용 하는 방법을 보여 줍니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a>Utf8JsonReader 사용

다음 예제에서는 <xref:System.Text.Json.Utf8JsonReader> 클래스를 사용 하는 방법을 보여 줍니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

위의 코드는 `jsonUtf8` 변수가 u t f-8로 인코딩된 유효한 JSON을 포함 하는 바이트 배열 이라고 가정 합니다.

### <a name="filter-data-using-utf8jsonreader"></a>Utf8JsonReader를 사용 하 여 데이터 필터링

다음 예제에서는 파일을 동기적으로 읽고 값을 검색 하는 방법을 보여 줍니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

위의 코드는:

* 는 파일이 u t f-16으로 인코딩되고 u t f-8로 코드 변환 가정 합니다. U t f-8로 인코딩된 파일은 다음 코드를 사용 하 여 `ReadOnlySpan<byte>`직접 읽을 수 있습니다.

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* JSON에 개체 배열이 포함 되어 있다고 가정 하 고 각 개체에 문자열 형식의 "name" 속성이 포함 될 수 있습니다.
* "대학"으로 끝나는 개체 및 `name` 속성 값을 계산 합니다.

위의 코드에서 읽을 수 있는 JSON 샘플은 다음과 같습니다. 결과 요약 메시지는 "2-4 중에서 이름이 ' 대학 '로 끝나는 이름입니다.

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a>추가 자료

* [System.object 개요](system-text-json-overview.md)
* [System.object API 참조](xref:System.Text.Json)
* [System.object의 사용자 지정 변환기를 작성 합니다.](system-text-json-converters-how-to.md)
* [System.object의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)
* [Json-기능-doc로 레이블이 지정 된 dotnet/corefx 리포지토리의 GitHub 문제](https://github.com/dotnet/corefx/labels/json-functionality-doc) 
