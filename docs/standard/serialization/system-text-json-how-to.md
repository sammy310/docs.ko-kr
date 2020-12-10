---
title: C#을 사용하여 JSON을 직렬화 및 역직렬화하는 방법 - .NET
description: System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 알아봅니다. 샘플 코드가 포함되어 있습니다.
ms.date: 11/30/2020
ms.custom: contperfq2
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 9ea9e2fef5ef66f2a5ff816168abfbd7b2e75276
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437680"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a>.NET에서 JSON을 직렬화 및 역직렬화(마샬링 및 역 마샬링)하는 방법

이 문서에서는 <xref:System.Text.Json?displayProperty=fullName> 네임스페이스를 사용하여 JSON(JavaScript Object Notation)으로 직렬화와 JSON으로부터 역직렬화하는 방법을 보여줍니다. `Newtonsoft.Json`에서 기존 코드를 이식하는 경우 [`System.Text.Json`으로 마이그레이션 방법](system-text-json-migrate-from-newtonsoft-how-to.md)을 참조하세요.

지침 및 샘플 코드에서는 [ASP.NET Core](/aspnet/core/) 같은 프레임워크를 통하지 않고 직접 라이브러리를 사용합니다.

대부분의 직렬화 샘플 코드는 JSON을 "보기 좋게 출력"하도록(사람이 읽기 쉽도록 들여쓰기 및 공백 사용) <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다. 프로덕션에 사용하는 경우에는 일반적으로 이 설정의 기본값인 `false`를 적용합니다.

코드 예제에서는 다음 클래스와 그 변형을 참조합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a>네임스페이스

<xref:System.Text.Json> 네임스페이스에는 모든 진입점과 기본 형식이 포함되어 있습니다. <xref:System.Text.Json.Serialization> 네임스페이스에는 직렬화 및 역직렬화와 관련된 고급 시나리오 및 사용자 지정을 위한 특성과 API가 포함되어 있습니다. 이 문서의 코드 예제에서는 두 네임스페이스 중 하나 또는 둘 다에 `using` 지시문이 필요합니다.

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> <xref:System.Runtime.Serialization> 네임스페이스의 특성은 `System.Text.Json`에서 지원되지 않습니다.

## <a name="how-to-write-net-objects-as-json-serialize"></a>.NET 개체를 JSON으로 쓰는 방법(직렬화)

문자열 또는 파일에 JSON을 쓰려면 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.

다음은 JSON 파일을 문자열로 만드는 예제입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

다음은 동기 코드를 사용하여 JSON 파일을 만드는 예제입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

다음은 비동기 코드를 사용하여 JSON 파일을 만드는 예지입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

앞의 예제에서는 직렬화되는 형식에 형식 유추를 사용합니다. `Serialize()`의 오버로드는 제네릭 형식 매개 변수를 사용합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a>직렬화 예제

다음은 수집 유형 속성과 사용자 정의 형식을 포함하는 예제 클래스입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> "POCO"는 [Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_old_CLR_object)를 나타냅니다. POCO는 예를 들어 상속 또는 속성을 통해 프레임워크별 형식에 의존하지 않는 .NET 형식입니다.

다음은 이전 형식의 인스턴스를 직렬화하는 JSON 출력의 예입니다. JSON 출력은 기본적으로 축소됩니다(공백, 들여쓰기, 줄 바꿈 문자가 제거됨).

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

다음 예제에서는 동일한 JSON 형식을 보여주지만 다음과 같은 형식이 지정됩니다(공백 및 들여쓰기를 사용하여 보기 좋게 인쇄됨).

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

## <a name="serialize-to-utf-8"></a>UTF-8로 직렬화

UTF-8로 직렬화하려면 다음과 같이 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 메서드를 호출합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

<xref:System.Text.Json.Utf8JsonWriter>를 사용하는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버로드도 사용할 수 있습니다.

UTF-8로 직렬화하면 문자열 기반 메서드를 사용할 때보다 약 5-10% 더 빠릅니다. 속도에서 차이가 나는 이유는 바이트(UTF-8)를 문자열(UTF-16)로 변환할 필요가 없기 때문입니다.

## <a name="serialization-behavior"></a>Serialization 동작

::: zone pivot="dotnet-5-0"

* 기본적으로 모든 public 속성은 직렬화됩니다. [무시할 속성을 지정](system-text-json-ignore-properties.md)할 수 있습니다.
* [기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)는 ASCII가 아닌 문자, ASCII 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프되어야 하는 문자를 이스케이프합니다.
* 기본적으로 JSON은 축소됩니다. [JSON을 보기 좋게 출력](#serialize-to-formatted-json)할 수 있습니다.
* 기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치합니다. [JSON 이름 대/소문자를 사용자 지정](system-text-json-customize-properties.md)할 수 있습니다.
* 기본적으로 순환 참조가 검색되고 예외가 throw됩니다. [참조를 보존하고 순환 참조를 처리](system-text-json-preserve-references.md)할 수 있습니다.
* 기본적으로 [필드](../../csharp/programming-guide/classes-and-structs/fields.md)는 무시됩니다. [필드를 포함](#include-fields)할 수 있습니다.

ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다. 자세한 내용은 [JsonSerializerOptions 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 참조하세요.
::: zone-end

::: zone pivot="dotnet-core-3-1"

* 기본적으로 모든 public 속성은 직렬화됩니다. [무시할 속성을 지정](system-text-json-ignore-properties.md)할 수 있습니다.
* [기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)는 ASCII가 아닌 문자, ASCII 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프되어야 하는 문자를 이스케이프합니다.
* 기본적으로 JSON은 축소됩니다. [JSON을 보기 좋게 출력](#serialize-to-formatted-json)할 수 있습니다.
* 기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치합니다. [JSON 이름 대/소문자를 사용자 지정](system-text-json-customize-properties.md)할 수 있습니다.
* 순환 참조가 감지되고 예외가 throw됩니다.
* [필드](../../csharp/programming-guide/classes-and-structs/fields.md)는 무시됩니다.
::: zone-end

지원되는 형식은 다음과 같습니다.
::: zone pivot="dotnet-5-0"

* 숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식
* 사용자 정의 [POCO(Plain Old CLR Object)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)
* 1차원 및 가변 배열(`T[][]`)
* 다음 네임스페이스의 컬렉션 및 사전.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* 숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식
* 사용자 정의 [POCO(Plain Old CLR Object)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)
* 1차원 및 가변 배열(`ArrayName[][]`)
* `Dictionary<string,TValue>`. 여기서 `TValue`는 `object`, `JsonElement` 또는 POCO입니다.
* 다음 네임스페이스의 컬렉션.
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

추가 형식을 처리하거나 기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.

## <a name="how-to-read-json-as-net-objects-deserialize"></a>JSON을 .NET 개체로 읽는 방법(역직렬화)

문자열 또는 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.

다음 예제에서는 문자열에서 JSON을 읽고, 앞에서 [직렬화 예제](#serialization-example)에서 설명한 `WeatherForecastWithPOCOs` 클래스의 인스턴스를 만듭니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

동기 코드를 사용하여 파일에서 역직렬화하려면 다음 예제와 같이 파일을 문자열로 읽습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

비동기 코드를 사용하여 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 메서드를 호출합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a>UTF-8에서 역직렬화

UTF-8에서 역직렬화하려면 다음 예제와 같이 `ReadOnlySpan<byte>` 또는 `Utf8JsonReader`을 사용하는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 오버로드를 호출합니다. 이 예제에서는 JSON이 jsonUtf8Bytes라는 바이트 배열에 있다고 가정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a>역직렬화 동작

JSON을 역직렬화할 때 다음 동작이 적용됩니다.

::: zone pivot="dotnet-5-0"

* 속성 이름 일치 시에 대/소문자를 구분합니다. [대/소문자를 구분 하지 않도록 지정](system-text-json-character-casing.md)할 수 있습니다.
* JSON에 읽기 전용 속성의 값이 포함되어 있으면 해당 값이 무시되고 예외가 throw되지 않습니다.
* public이 아닌 생성자는 직렬 변환기에서 무시됩니다.
* 변경 불가능한 개체 또는 읽기 전용 속성으로의 역직렬화는 지원되지 않습니다. [변경 불가능한 형식 및 레코드](system-text-json-immutability.md)를 참조하세요.
* 기본적으로 열거형은 숫자로 지원됩니다. [열거형 이름을 문자열로 직렬화](system-text-json-customize-properties.md#enums-as-strings)할 수 있습니다.
* 기본적으로 필드는 무시됩니다. [필드를 포함](#include-fields)할 수 있습니다.
* 기본적으로 JSON의 주석이나 후행 쉼표는 예외를 throw합니다. [주석과 후행 쉼표를 허용](system-text-json-invalid-json.md)할 수 있습니다.
* [기본 최댓값](xref:System.Text.Json.JsonReaderOptions.MaxDepth)은 64입니다.

ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다. 자세한 내용은 [JsonSerializerOptions 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 참조하세요.
::: zone-end

::: zone pivot="dotnet-core-3-1"

* 속성 이름 일치 시에 대/소문자를 구분합니다. [대/소문자를 구분 하지 않도록 지정](system-text-json-character-casing.md)할 수 있습니다. ASP.NET Core 앱은[대/소문자 구분 사용 안 함을 기본값으로 지정](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)합니다.
* JSON에 읽기 전용 속성의 값이 포함되어 있으면 해당 값이 무시되고 예외가 throw되지 않습니다.
* public, internal 또는 private일 수 있는 매개 변수가 없는 생성자가 역직렬화에 사용됩니다.
* 변경할 수 없는 개체 또는 읽기 전용 속성으로의 역직렬화는 지원되지 않습니다.
* 기본적으로 열거형은 숫자로 지원됩니다. [열거형 이름을 문자열로 직렬화](system-text-json-customize-properties.md#enums-as-strings)할 수 있습니다.
* 필드는 지원되지 않습니다.
* 기본적으로 JSON의 주석이나 후행 쉼표는 예외를 throw합니다. [주석과 후행 쉼표를 허용](system-text-json-invalid-json.md)할 수 있습니다.
* [기본 최댓값](xref:System.Text.Json.JsonReaderOptions.MaxDepth)은 64입니다.

ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다. 자세한 내용은 [JsonSerializerOptions 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 참조하세요.
::: zone-end

기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.

## <a name="serialize-to-formatted-json"></a>형식이 지정된 JSON으로 직렬화

JSON 출력을 보기 좋게 출력하려면 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

다음 형식은 직렬화하여 보기 좋게 출력할 JSON 출력의 예입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a>필드 포함

::: zone pivot="dotnet-5-0"
다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> 전역 설정 또는 [JsonInclude](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 특성을 사용하여 직렬화 또는 역직렬화할 때의 필드를 포함합니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

읽기 전용 필드를 무시하려면 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 전역 설정을 사용합니다.
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1의 System.Text.Json에서는 필드가 지원되지 않습니다. [사용자 지정 변환기](system-text-json-converters-how-to.md)는 이 기능을 제공할 수 있습니다.
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a>HttpClient 및 Httpclient 확장 메서드

::: zone pivot="dotnet-5-0"

네트워크에서 JSON 페이로드를 직렬화 및 역직렬화하는 작업은 일반적인 작업입니다. [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) 및 [Httpclient](xref:System.Net.Http.Json.HttpContentJsonExtensions) 확장 메서드를 사용하면 코드 한 줄로 이러한 작업을 수행할 수 있습니다. 이러한 확장 메서드는 [JsonSerializerOptions의 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 사용합니다.

다음 예제는 <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> 및 <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>의 사용 방법을 보여 줍니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

[HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions)에는 System.Text.Json의 확장 메서드도 있습니다.
::: zone-end

::: zone pivot="dotnet-core-3-1"
`HttpClient` 및 `HttpContent`의 확장 메서드는 .NET Core 3.1의 System.Text.Json에서 사용할 수 없습니다.
::: zone-end

## <a name="see-also"></a>참고 항목

* [System.Text.Json 개요](system-text-json-overview.md)
* [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md)
* [Newtonsoft.Json에서 마이그레이션하는 방법](system-text-json-migrate-from-newtonsoft-how-to.md)
* [System.Text.Json의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
