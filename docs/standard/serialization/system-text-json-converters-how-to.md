---
title: JSON serialization용 사용자 지정 변환기를 작성하는 방법 - .NET
description: System.Text.Json 네임스페이스에 제공된 JSON 직렬화 클래스의 사용자 지정 변환기를 만드는 방법을 알아봅니다.
ms.date: 12/09/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
- converters
ms.openlocfilehash: 33334ccd8bad4ac5a9f5dccde79ff3ae09ca8f89
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008866"
---
# <a name="how-to-write-custom-converters-for-json-serialization-marshalling-in-net"></a>.NET에서 JSON serialization(마샬링)용 사용자 지정 변환기를 작성하는 방법

이 문서에서는 <xref:System.Text.Json> 네임스페이스에 제공된 JSON serialization 클래스에 대한 사용자 지정 변환기를 만드는 방법을 보여 줍니다. `System.Text.Json`에 대한 소개는 [.NET에서 JSON을 직렬화 및 역직렬화하는 방법](system-text-json-how-to.md)을 참조하세요.

*변환기* 는 개체 또는 값을 JSON으로 변환하는 클래스입니다. `System.Text.Json` 네임스페이스에는 JavaScript 기본 형식에 매핑되는 기본 형식 대부분에 대한 기본 제공 변환기가 있습니다. 다음과 같은 용도로 사용자 지정 변환기를 작성할 수 있습니다.

* 기본 제공 변환기의 기본 동작을 재정의합니다. 예를 들어 `DateTime` 값을 mm/dd/yyyy 형식으로 표시하도록 할 수 있습니다. 기본적으로 RFC 3339 프로필을 포함하여 ISO 8601-1:2019가 지원됩니다. 자세한 내용은 [System.Text.Json의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)을 참조하세요.
* 사용자 지정 값 형식을 지원합니다. 예를 들어 `PhoneNumber` 구조체입니다.

현재 릴리스에 포함되지 않은 기능을 사용하여 `System.Text.Json`를 사용자 지정하거나 확장하는 사용자 지정 변환기를 작성할 수도 있습니다. 이 문서의 뒷부분에서 다음과 같은 시나리오에 대해 설명합니다.

::: zone pivot="dotnet-5-0"

* [유추된 형식을 개체 속성으로 역직렬화](#deserialize-inferred-types-to-object-properties)
* [다형 deserialization 지원](#support-polymorphic-deserialization)
* [Stack\<T>에 대한 왕복 지원](#support-round-trip-for-stackt)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [유추된 형식을 개체 속성으로 역직렬화](#deserialize-inferred-types-to-object-properties)
* [문자열이 아닌 키를 사용하는 사전 지원](#support-dictionary-with-non-string-key)
* [다형 deserialization 지원](#support-polymorphic-deserialization)
* [Stack\<T>에 대한 왕복 지원](#support-round-trip-for-stackt)
::: zone-end

사용자 지정 변환기에 대해 작성하는 코드에서는 새 <xref:System.Text.Json.JsonSerializerOptions> 인스턴스를 사용하는 경우 성능 저하에 대해 알고 있어야 합니다. 자세한 내용은 [JsonSerializerOptions 인스턴스 다시 사용](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances)을 참조하세요.

## <a name="custom-converter-patterns"></a>사용자 지정 변환기 패턴

사용자 지정 변환기를 만드는 데는 기본 패턴과 팩터리 패턴의 두 가지 패턴이 있습니다. 팩터리 패턴은 `Enum` 형식 또는 개방형 제네릭을 처리하는 변환기를 위한 것입니다. 기본 패턴은 제네릭이 아닌 형식과 폐쇄형 제네릭 형식을 위한 것입니다.  예를 들어 다음 형식의 변환기에는 팩터리 패턴이 필요합니다.

* <xref:System.Collections.Generic.Dictionary%602>
* <xref:System.Enum>
* <xref:System.Collections.Generic.List%601>

기본 패턴으로 처리할 수 있는 형식의 몇 가지 예는 다음과 같습니다.

* `Dictionary<int, string>`
* `WeekdaysEnum`
* `List<DateTimeOffset>`
* <xref:System.DateTime>
* <xref:System.Int32>

기본 패턴은 한 형식을 처리할 수 있는 클래스를 만듭니다. 팩터리 패턴은 런타임에 특정 형식이 필요한지 여부를 결정하는 클래스를 만들고 적절한 변환기를 동적으로 만듭니다.

## <a name="sample-basic-converter"></a>샘플 기본 변환기

다음 샘플은 기존 데이터 형식에 대한 기본 serialization을 재정의하는 변환기입니다. 변환기는 `DateTimeOffset` 속성에 mm/dd/yyyy 형식을 사용합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DateTimeOffsetConverter.cs":::

## <a name="sample-factory-pattern-converter"></a>샘플 팩터리 패턴 변환기

다음 코드에서는 `Dictionary<Enum,TValue>`와 함께 작동하는 사용자 지정 변환기를 보여 줍니다. 첫 번째 제네릭 형식 매개 변수가 `Enum`이고 두 번째는 개방형이기 때문에 이 코드는 팩터리 패턴을 따릅니다. `CanConvert` 메서드는 두 개의 제네릭 매개 변수(이 중 첫 번째는 `Enum` 형식)가 있는 `Dictionary`에 대해서만 `true`를 반환합니다. 내부 변환기는 런타임에 `TValue`에 제공되는 형식을 처리하기 위해 기존 변환기를 가져옵니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

위의 코드는 이 문서의 뒷부분에 나오는 [문자열이 아닌 키를 사용하는 사전 지원](#support-dictionary-with-non-string-key)에서 보여 주는 것과 동일합니다.

## <a name="steps-to-follow-the-basic-pattern"></a>기본 패턴을 따르기 위한 단계

다음 단계에서는 기본 패턴을 따라 변환기를 만드는 방법을 설명합니다.

* <xref:System.Text.Json.Serialization.JsonConverter%601>에서 파생되는 클래스를 만듭니다. 여기서 `T`는 직렬화 및 역직렬화할 형식입니다.
* 들어오는 JSON을 역직렬화하고 `T` 형식으로 변환하도록 `Read` 메서드를 재정의합니다. 메서드에 전달된 <xref:System.Text.Json.Utf8JsonReader>를 사용하여 JSON을 읽습니다.
* 들어오는 `T` 형식의 개체를 직렬화하도록 `Write` 메서드를 재정의합니다. 메서드에 전달된 <xref:System.Text.Json.Utf8JsonWriter>를 사용하여 JSON을 작성합니다.
* 필요한 경우에만 `CanConvert` 메서드를 재정의합니다. 기본 구현은 변환할 형식이 `T` 형식일 때 `true`를 반환합니다. 따라서 `T` 형식만 지원하는 변환기는 이 메서드를 재정의할 필요가 없습니다. 이 메서드를 재정의해야 하는 변환기의 예제는 이 문서의 뒷부분에 나오는 [다형 deserialization](#support-polymorphic-deserialization) 섹션을 참조하세요.

사용자 지정 변환기 작성을 위한 참조 구현으로 [기본 제공 변환기 소스 코드](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/)를 참조할 수 있습니다.

## <a name="steps-to-follow-the-factory-pattern"></a>팩터리 패턴을 따르기 위한 단계

다음 단계에서는 팩터리 패턴을 따라 변환기를 만드는 방법을 설명합니다.

* <xref:System.Text.Json.Serialization.JsonConverterFactory>에서 파생되는 클래스를 만듭니다.
* 변환할 형식이 변환기에서 처리할 수 있는 형식인 경우 true를 반환하도록 `CanConvert` 메서드를 재정의합니다. 예를 들어 `List<T>`에 대한 변환기인 경우 `List<int>`, `List<string>` 및 `List<DateTime>`만 처리할 수 있습니다.
* 런타임에 제공되는 변환할 형식을 처리할 변환기 클래스 인스턴스를 반환하도록 `CreateConverter` 메서드를 재정의합니다.
* `CreateConverter` 메서드가 인스턴스화하는 변환기 클래스를 만듭니다.

개체와 문자열 간에 변환하는 코드가 모든 형식에 대해 동일하지 않기 때문에 개방형 제네릭에는 팩터리 패턴이 필요합니다. 개방형 제네릭 형식(예: `List<T>`)에 대한 변환기는 백그라운드에서 폐쇄형 제네릭 형식(예: `List<DateTime>`)에 대한 변환기를 만들어야 합니다. 변환기가 처리할 수 있는 각 폐쇄형 제네릭 형식을 처리하기 위해 코드를 작성해야 합니다.

`Enum` 형식은 개방형 제네릭 형식과 유사합니다. `Enum`에 대한 변환기는 내부적으로 특정 `Enum`(예: `WeekdaysEnum`)에 대한 변환기를 만들어야 합니다.

## <a name="error-handling"></a>오류 처리

직렬 변환기는 <xref:System.Text.Json.JsonException> 및 <xref:System.NotSupportedException> 예외 형식을 특별히 처리합니다.

### <a name="jsonexception"></a>JsonException

메시지 없이 `JsonException`을 throw하는 경우 직렬 변환기는 JSON에서 오류를 발생시킨 부분의 경로를 포함하는 메시지를 만듭니다. 예를 들어 `throw new JsonException()` 문은 다음 예제와 같은 오류 메시지를 생성합니다.

```output
Unhandled exception. System.Text.Json.JsonException:
The JSON value could not be converted to System.Object.
Path: $.Date | LineNumber: 1 | BytePositionInLine: 37.
```

메시지를 제공하는 경우(예: `throw new JsonException("Error occurred")`) 직렬 변환기는 <xref:System.Text.Json.JsonException.Path>, <xref:System.Text.Json.JsonException.LineNumber>, 및 <xref:System.Text.Json.JsonException.BytePositionInLine> 속성을 계속 설정합니다.

### <a name="notsupportedexception"></a>NotSupportedException

`NotSupportedException`을 throw하는 경우 메시지에 항상 경로 정보를 받습니다. 메시지를 제공하는 경우 경로 정보가 추가됩니다. 예를 들어 `throw new NotSupportedException("Error occurred.")` 문은 다음 예제와 같은 오류 메시지를 생성합니다.

```output
Error occurred. The unsupported member type is located on type
'System.Collections.Generic.Dictionary`2[Samples.SummaryWords,System.Int32]'.
Path: $.TemperatureRanges | LineNumber: 4 | BytePositionInLine: 24
```

### <a name="when-to-throw-which-exception-type"></a>예외 형식을 throw하는 경우

JSON 페이로드에 역직렬화되는 형식에 유효하지 않은 토큰이 포함된 경우 `JsonException`을 throw합니다.

특정 형식을 허용하지 않으려면 `NotSupportedException`을 throw합니다. 이 예외는 직렬 변환기가 지원되지 않는 형식에 대해 자동으로 throw하는 예외입니다. 예를 들어 `System.Type`은 보안상의 이유로 지원되지 않으므로, 역직렬화하려고 하면 `NotSupportedException`이 발생합니다.

필요에 따라 다른 예외를 throw할 수 있지만, JSON 경로 정보는 자동으로 포함되지 않습니다.

## <a name="register-a-custom-converter"></a>사용자 지정 변환기 등록

`Serialize` 및 `Deserialize` 메서드가 사용할 수 있도록 사용자 지정 변환기를 *등록* 합니다. 다음 방법 중 하나를 선택합니다.

* <xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> 컬렉션에 변환기 클래스의 인스턴스를 추가합니다.
* [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) 특성을 사용자 지정 변환기가 필요한 속성에 적용합니다.
* [[JsonConverter]](xref:System.Text.Json.Serialization.JsonConverterAttribute) 특성을 사용자 지정 값 형식을 나타내는 클래스 또는 구조체에 적용합니다.

## <a name="registration-sample---converters-collection"></a>등록 샘플 - 변환기 컬렉션

다음은 <xref:System.ComponentModel.DateTimeOffsetConverter>를 <xref:System.DateTimeOffset> 형식의 속성에 대한 기본값으로 지정하는 예제입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Serialize":::

다음 형식의 인스턴스를 직렬화한다고 가정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

다음은 사용자 지정 변환기가 사용되었음을 보여 주는 JSON 출력의 예입니다.

```json
{
  "Date": "08/01/2019",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

다음 코드에서는 사용자 지정 `DateTimeOffset` 변환기를 사용하여 역직렬화하기 위해 동일한 방법을 사용합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithConvertersCollection.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-property"></a>등록 샘플 - 속성에 적용되는 [JsonConverter]

다음 코드에서는 `Date` 속성에 대한 사용자 지정 변환기를 선택합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithConverterAttribute":::

`WeatherForecastWithConverterAttribute`를 직렬화하는 코드는 `JsonSerializeOptions.Converters`를 사용할 필요가 없습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Serialize":::

역직렬화하는 코드도 `Converters`를 사용할 필요가 없습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RegisterConverterWithAttributeOnProperty.cs" id="Deserialize":::

## <a name="registration-sample---jsonconverter-on-a-type"></a>등록 샘플 - 형식에 적용되는 [JsonConverter]

다음은 구조체를 만들고 `[JsonConverter]` 특성을 적용하는 코드입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Temperature.cs":::

앞의 구조체에 대한 사용자 지정 변환기는 다음과 같습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/TemperatureConverter.cs":::

구조체의 `[JsonConvert]` 특성은 사용자 지정 변환기를 `Temperature` 형식의 속성에 대한 기본값으로 등록합니다. 이 변환기는 다음 형식의 `TemperatureCelsius` 속성을 직렬화 또는 역직렬화할 때 자동으로 사용됩니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithTemperatureStruct":::

## <a name="converter-registration-precedence"></a>변환기 등록 우선 순위

serialization 또는 deserialization 동안 각 JSON 요소에 대해 가장 높은 우선 순위에서 가장 낮은 순서로 변환기가 선택됩니다.

* 속성에 적용된 `[JsonConverter]`.
* `Converters` 컬렉션에 추가된 변환기.
* 사용자 지정 값 형식 또는 POCO에 적용된 `[JsonConverter]`.

`Converters` 컬렉션에 특정 형식에 대한 여러 사용자 지정 변환기가 등록된 경우 `CanConvert`에 true를 반환하는 첫 번째 변환기가 사용됩니다.

기본 제공 변환기는 해당하는 사용자 지정 변환기가 등록되지 않은 경우에만 선택됩니다.

## <a name="converter-samples-for-common-scenarios"></a>일반 시나리오용 변환기 샘플

다음 섹션에서는 기본 제공 기능이 처리하지 않는 몇 가지 일반적인 시나리오를 해결하는 변환기 샘플을 제공합니다.

::: zone pivot="dotnet-5-0"

* [유추된 형식을 개체 속성으로 역직렬화](#deserialize-inferred-types-to-object-properties)
* [다형 deserialization 지원](#support-polymorphic-deserialization)
* [Stack\<T>에 대한 왕복 지원](#support-round-trip-for-stackt)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [유추된 형식을 개체 속성으로 역직렬화](#deserialize-inferred-types-to-object-properties)
* [문자열이 아닌 키를 사용하는 사전 지원](#support-dictionary-with-non-string-key)
* [다형 deserialization 지원](#support-polymorphic-deserialization)
* [Stack\<T>에 대한 왕복 지원](#support-round-trip-for-stackt)
::: zone-end

### <a name="deserialize-inferred-types-to-object-properties"></a>유추된 형식을 개체 속성으로 역직렬화

`object` 형식의 속성으로 역직렬화할 때 `JsonElement` 개체가 만들어집니다. 그 이유는 역직렬 변환기가 만들 CLR 형식을 알지 못하고 추측하려고 하지 않기 때문입니다. 예를 들어 JSON 속성에 "true"가 있는 경우 역직렬 변환기는 값이 `Boolean`임을 유추하지 않으며 요소에 "01/01/2019"가 있는 경우 역직렬 변환기가 `DateTime`를 유추하지 않습니다.

형식 유추는 정확하지 않을 수 있습니다. 역직렬 변환기가 소수점이 없는 JSON 번호를 `long`으로 구문 분석하는 경우 값이 원래 `ulong` 또는 `BigInteger`로 직렬화되었다면 범위를 벗어남 문제가 발생할 수 있습니다. 소수점이 있는 숫자를 `double`로 구문 분석하면 해당 숫자가 원래 `decimal`로 직렬화된 경우에는 전체 자릿수가 손실될 수 있습니다.

형식 유추가 필요한 시나리오의 경우 다음 코드는 `object` 속성에 대한 사용자 지정 변환기를 보여 줍니다. 이 코드는 다음과 같이 변환합니다.

* `true` 및 `false`를 `Boolean`으로
* 소수점이 없는 숫자를 `long`으로
* 소수점이 있는 숫자를 `double`로
* 날짜를 `DateTime`으로
* 문자열을 `string`으로
* 그 밖의 모든 항목으로 `JsonElement`로

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ObjectToInferredTypesConverter.cs":::

다음 코드는 변환기를 등록합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeInferredTypesToObject.cs" id="Register":::

다음은 `object` 속성을 사용하는 예제 형식입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithObjectProperties":::

다음의 역직렬화 JSON 예제에는 `DateTime`, `long` 및 `string`으로 역직렬화될 값이 포함되어 있습니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

사용자 지정 변환기가 없으면 deserialization은 각 속성에 `JsonElement`를 배치합니다.

`System.Text.Json.Serialization` 네임스페이스의 [unit tests 폴더](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)에는 `object` 속성에 대한 deserialization을 처리하는 사용자 지정 변환기의 더 많은 예제가 있습니다.

::: zone pivot="dotnet-core-3-1"

### <a name="support-dictionary-with-non-string-key"></a>문자열이 아닌 키를 사용하는 사전 지원

사전 컬렉션에 대한 기본 제공 지원은 `Dictionary<string, TValue>`입니다. 즉, 키가 문자열이어야 합니다. 정수 또는 다른 형식을 키로 사용하는 사전을 지원하려면 사용자 지정 변환기가 필요합니다.

다음 코드에서는 `Dictionary<Enum,TValue>`와 함께 작동하는 사용자 지정 변환기를 보여 줍니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DictionaryTKeyEnumTValueConverter.cs":::

다음 코드는 변환기를 등록합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripDictionaryTkeyEnumTValue.cs" id="Register":::

이 변환기는 다음 `Enum`을 사용하는 다음 클래스의 `TemperatureRanges` 속성을 직렬화 및 역직렬화할 수 있습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnumDictionary":::

Serialization의 JSON 출력은 다음 예제와 같습니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "Cold": 20,
    "Hot": 40
  }
}
```

`System.Text.Json.Serialization` 네임스페이스의 [unit tests 폴더](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)에는 비 문자열 키 사전을 처리하는 사용자 지정 변환기의 더 많은 예제가 있습니다.
::: zone-end

### <a name="support-polymorphic-deserialization"></a>다형 deserialization 지원

기본 제공 기능을 통해 제한적으로 [다형 serialization](system-text-json-polymorphism.md)을 제공할 수 있지만 deserialization은 전혀 지원되지 않습니다. deserialization을 수행하려면 사용자 지정 변환기가 필요합니다.

예를 들어 `Employee` 및 `Customer` 파생 클래스를 사용하는 `Person` 추상 기본 클래스가 있다고 가정합니다. 다형성 deserialization은 디자인 타임에 `Person`을 deserialization 대상으로 지정할 수 있고 런타임에 JSON의 `Customer` 및 `Employee` 개체가 올바르게 역직렬화됨을 의미합니다. deserialization 동안 JSON에서 필요한 형식을 식별하는 단서를 찾아야 합니다. 사용 가능한 단서의 종류는 각 시나리오마다 다릅니다. 예를 들어 판별자 속성을 사용할 수 있거나 특정 속성이 존재하는지 여부에 의존해야 할 수도 있습니다. 현재 릴리스의 `System.Text.Json`에서는 다형 deserialization 시나리오를 처리하는 방법을 지정하는 특성을 제공하지 않으므로 사용자 지정 변환기가 필요합니다.

다음 코드에서는 기본 클래스, 두 개의 파생 클래스 및 해당 클래스에 대한 사용자 지정 변환기를 보여 줍니다. 이 변환기는 판별자 속성을 사용하여 다형 deserialization을 수행합니다. 형식 판별자는 클래스 정의에 없지만 serialization 동안 만들어지고 deserialization 동안 읽힙니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Person.cs" id="Person":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/PersonConverterWithTypeDiscriminator.cs":::

다음 코드는 변환기를 등록합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPolymorphic.cs" id="Register":::

변환기는 동일한 직렬화 변환기를 사용하여 만든 JSON을 역직렬화할 수 있습니다. 예를 들면 다음과 같습니다.

```json
[
  {
    "TypeDiscriminator": 1,
    "CreditLimit": 10000,
    "Name": "John"
  },
  {
    "TypeDiscriminator": 2,
    "OfficeNumber": "555-1234",
    "Name": "Nancy"
  }
]
```

이전 예제의 변환기 코드는 각 속성을 수동으로 읽고 씁니다. 대신 `Deserialize` 또는 `Serialize`를 호출하여 일부 작업을 수행할 수 있습니다. 예제는 [이 StackOverflow 게시물](https://stackoverflow.com/a/59744873/12509023)을 참조하세요.

### <a name="support-round-trip-for-stackt"></a>Stack\<T>에 대한 왕복 지원

JSON 문자열을 <xref:System.Collections.Generic.Stack%601> 개체로 역직렬화한 다음 해당 개체를 직렬화하는 경우 스택의 내용이 역순으로 표시됩니다. 이 동작은 다음 형식 및 인터페이스, 그리고 이러한 형식에서 파생되는 사용자 정의 형식에 적용됩니다.

* <xref:System.Collections.Stack>
* <xref:System.Collections.Generic.Stack%601>
* <xref:System.Collections.Concurrent.ConcurrentStack%601>
* <xref:System.Collections.Immutable.ImmutableStack%601>
* <xref:System.Collections.Immutable.IImmutableStack%601>

스택에서 원래 순서를 유지하는 serialization 및 deserialization을 지원하려면 사용자 지정 변환기가 필요합니다.

다음 코드는 `Stack<T>` 개체에 대한 라운드트립을 가능하게 하는 사용자 지정 변환기를 보여 줍니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonConverterFactoryForStackOfT.cs":::

다음 코드는 변환기를 등록합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripStackOfT.cs" id="Register":::

## <a name="handle-null-values"></a>Null 값 처리

기본적으로 직렬 변환기는 null 값을 다음과 같이 처리합니다.

* 참조 형식 및 <xref:System.Nullable%601> 형식:

  * 직렬화 시 사용자 지정 변환기에 `null`을 전달하지 않습니다.
  * 역직렬화 시 사용자 지정 변환기에 `JsonTokenType.Null`을 전달하지 않습니다.
  * 역직렬화 시 `null` 인스턴스를 반환합니다.
  * 직렬화 시 기록기로 직접 `null`을 씁니다.

* null을 허용하지 않는 값 형식:

  * 역직렬화 시 사용자 지정 변환기에 `JsonTokenType.Null`을 전달합니다. (사용자 지정 변환기를 사용할 수 없는 경우 형식의 내부 변환기에서 `JsonException` 예외가 throw됩니다.)

이 null 처리 동작은 주로 변환기에 대한 추가 호출을 건너뛰어 성능을 최적화하기 위한 것입니다. 또한 nullable 형식의 변환기가 모든 `Read` 및 `Write` 메서드 재정의가 시작될 때 강제로 `null`을 확인하지 않도록 합니다.

::: zone pivot="dotnet-5-0"
사용자 지정 변환기가 참조 또는 값 형식의 `null`을 처리할 수 있게 하려면 다음 예제와 같이 `true`를 반환하도록 <xref:System.Text.Json.Serialization.JsonConverter%601.HandleNull%2A?displayProperty=nameWithType>을 재정의하세요.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CustomConverterHandleNull.cs" highlight="19":::
::: zone-end

## <a name="other-custom-converter-samples"></a>기타 사용자 지정 변환기 샘플

[Newtonsoft.Json에서 System.Text.Json로 마이그레이션](system-text-json-migrate-from-newtonsoft-how-to.md) 문서에는 사용자 지정 변환기의 추가 샘플이 포함되어 있습니다.

`System.Text.Json.Serialization` 소스 코드의 [unit tests 폴더](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/)에는 다음과 같은 다른 사용자 지정 변환기 샘플이 포함되어 있습니다.

* [역직렬화할 때 null을 0으로 변환하는 Int32 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.NullValueType.cs)
* [역직렬화할 때 문자열 및 숫자 값을 모두 허용하는 Int32 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Int32.cs)
* [Enum 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Enum.cs)
* 외부 데이터를 허용하는 [List\<T> 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.List.cs)
* [쉼표로 구분된 숫자 목록과 함께 작동하는 Long[] 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/tests/Serialization/CustomConverterTests.Array.cs)

기존 기본 제공 변환기의 동작을 수정하는 변환기를 만들어야 하는 경우 [기존 변환기의 소스 코드](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)를 가져와 사용자 지정을 위한 시작 지점으로 사용할 수 있습니다.

## <a name="additional-resources"></a>추가 자료

* [기본 제공 변환기 소스 코드](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters)
* [System.Text.Json 개요](system-text-json-overview.md)
* [JSON 직렬화 및 역직렬화 방법](system-text-json-how-to.md)
* [JsonSerializerOptions 인스턴스 인스턴스화](system-text-json-configure-options.md)
* [대/소문자를 구분하지 않는 일치를 사용하도록 설정](system-text-json-character-casing.md)
* [속성 이름 및 값 사용자 지정](system-text-json-customize-properties.md)
* [속성 무시](system-text-json-ignore-properties.md)
* [잘못된 JSON 허용](system-text-json-invalid-json.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [참조 유지](system-text-json-preserve-references.md)
* [변경할 수 없는 형식 및 public이 아닌 접근자](system-text-json-immutability.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [Newtonsoft.Json에서 System.Text.Json으로 마이그레이션](system-text-json-migrate-from-newtonsoft-how-to.md)
* [문자 인코딩 사용자 지정](system-text-json-character-encoding.md)
* [사용자 지정 직렬 변환기 및 역직렬 변환기 작성](write-custom-serializer-deserializer.md)
* [DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
* [System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)
