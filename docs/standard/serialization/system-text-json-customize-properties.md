---
title: System.Text.Json으로 속성 이름 및 값을 사용자 지정하는 방법
description: .NET에서 System.Text.Json을 사용하여 직렬화할 때 속성 이름 및 값을 사용자 지정하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: c754d41071e886bc1efcc3a30e249bf9e554ab5b
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599592"
---
# <a name="how-to-customize-property-names-and-values-with-no-locsystemtextjson"></a>System.Text.Json으로 속성 이름 및 값을 사용자 지정하는 방법

기본적으로 대/소문자를 비롯한 속성 이름 및 사전 키는 JSON 출력에서 변경되지 않습니다. 열거형 값은 숫자로 표시됩니다. 이 문서에서는 다음을 수행하는 방법을 알아봅니다.

> [!NOTE]
> [웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)은 카멜식 대/소문자입니다.

* [개별 속성 이름 사용자 지정](#customize-individual-property-names)
* [모든 속성 이름을 카멜식 대/소문자로 변환](#use-camel-case-for-all-json-property-names)
* [사용자 지정 속성 명명 정책 구현](#use-a-custom-json-property-naming-policy)
* [사전 키를 카멜식 대/소문자로 변환](#camel-case-dictionary-keys)
* [열거형을 문자열 및 카멜식 대/소문자로 변환](#enums-as-strings)

JSON 속성 이름 및 값을 특수하게 처리해야 하는 다른 시나리오의 경우 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)하면 됩니다.

## <a name="customize-individual-property-names"></a>개별 속성 이름 사용자 지정

개별 속성 이름을 설정하려면 [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) 특성을 사용합니다.

다음은 직렬화 형식과 그 결과 JSON의 예입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

이 특성을 통해 설정된 속성 이름은 다음과 같은 특징이 있습니다.

* 직렬화 및 역직렬화 양방향으로 적용됩니다.
* 속성 명명 정책보다 우선합니다.

## <a name="use-camel-case-for-all-json-property-names"></a>모든 JSON 속성 이름에 카멜식 대/소문자 사용

모든 JSON 속성 이름에 카멜식 대/소문자를 사용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>을 `JsonNamingPolicy.CamelCase`로 설정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs" id="Serialize":::

다음은 직렬화 클래스 및 JSON 출력의 예입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

카멜식 대/소문자 속성 명명 정책은 다음과 같습니다.

* 직렬화 및 역직렬화에 적용됩니다.
* `[JsonPropertyName]` 특성에 의해 재정의됩니다. 이러한 이유로 이 예제의 JSON 속성 이름 `Wind`는 카멜식 대/소문자가 아닙니다.

## <a name="use-a-custom-json-property-naming-policy"></a>사용자 지정 JSON 속성 명명 정책 사용

사용자 지정 JSON 속성 명명 정책을 사용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonNamingPolicy>에서 파생되는 클래스를 만들고 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 메서드를 재정의합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs":::

그리고 다음과 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 속성을 명명 정책 클래스의 인스턴스로 설정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs" id="Serialize":::

다음은 직렬화 클래스 및 JSON 출력의 예입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPropertyNameAttribute":::

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

JSON 속성 명명 정책은 다음과 같습니다.

* 직렬화 및 역직렬화에 적용됩니다.
* `[JsonPropertyName]` 특성에 의해 재정의됩니다. 이러한 이유로 이 예제의 JSON 속성 이름 `Wind`는 대문자가 아닙니다.

## <a name="camel-case-dictionary-keys"></a>카멜식 대/소문자 사전 키

직렬화할 개체의 속성이 `Dictionary<string,TValue>` 형식이면 `string` 키를 카멜식 대/소문자로 변환할 수 있습니다. 이렇게 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy>를 `JsonNamingPolicy.CamelCase`로 설정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs" id="Serialize":::

키-값 쌍 `"ColdMinTemp", 20` 및 `"HotMinTemp", 40`가 있는 `TemperatureRanges`라는 사전이 포함된 개체를 직렬화하면 다음 예제와 같은 JSON 출력이 생성됩니다.

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

사전 키에 대한 카멜식 대/소문자 명명 정책은 직렬화에만 적용됩니다. 사전을 역직렬화하면 `DictionaryKeyPolicy`에 대 한 `JsonNamingPolicy.CamelCase`를 지정하더라도 키가 JSON 파일과 일치합니다.

## <a name="enums-as-strings"></a>문자열인 열거형

기본적으로 열거형은 숫자로 직렬화됩니다. 열거형 이름을 문자열로 직렬화하려면 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>를 사용합니다.

예를 들어 열거형을 포함하는 다음 클래스를 직렬화해야 한다고 가정해 봅시다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithEnum":::

Summary가 `Hot`이면 기본적으로 직렬화된 JSON은 다음과 같이 숫자 값 3을 갖습니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

다음 샘플 코드는 숫자 값 대신 열거형 이름을 직렬화하고, 이름을 카멜식 대/소문자로 변환합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Serialize":::

그 결과로 얻는 JSON은 다음 예제와 유사합니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

다음 예제와 같이 열거형 문자열 이름도 역직렬화할 수 있습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs" id="Deserialize":::

## <a name="see-also"></a>참고 항목

* [System.Text.Json 개요](system-text-json-overview.md)
* [JsonSerializerOptions 인스턴스화](system-text-json-configure-options.md)
* [대/소문자를 구분하지 않는 일치를 사용하도록 설정](system-text-json-character-casing.md)
* [속성 무시](system-text-json-ignore-properties.md)
* [잘못된 JSON 허용](system-text-json-invalid-json.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [순환 참조 보존](system-text-json-preserve-references.md)
* [변경할 수 없는 형식 및 public이 아닌 접근자](system-text-json-immutability.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
