---
title: Newtonsoft.json에서 System.object로 마이그레이션-.NET
author: tdykstra
ms.author: tdykstra
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 01f94bcfce97da8c71b1b709baa34c2b7509a5e5
ms.sourcegitcommit: ed3f926b6cdd372037bbcc214dc8f08a70366390
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/16/2020
ms.locfileid: "76116694"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>Newtonsoft.json에서 System.object로 마이그레이션하는 방법

이 문서에서는 [newtonsoft.json](https://www.newtonsoft.com/json) 에서 <xref:System.Text.Json>로 마이그레이션하는 방법을 보여 줍니다.

 `System.Text.Json`는 주로 성능, 보안 및 표준 준수에 중점을 둘 것입니다. 기본 동작에는 몇 가지 주요 차이점이 있으며 `Newtonsoft.Json`기능 패리티를 목표로 하지 않습니다. 일부 시나리오에서는 `System.Text.Json`에 기본 제공 기능이 없지만 권장 해결 방법이 있습니다. 다른 시나리오의 경우 해결 방법은 실용적이 지 않습니다. 응용 프로그램이 누락 된 기능에 종속 된 경우 시나리오에 대 한 지원을 추가할 수 있는지 확인 하는 [문제](https://github.com/dotnet/runtime/issues/new) 를 확인 하는 것이 좋습니다.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

이 문서의 대부분은 <xref:System.Text.Json.JsonSerializer> API를 사용 하는 방법에 대 한 것 이지만 <xref:System.Text.Json.JsonDocument> (문서 개체 모델 또는 DOM을 나타냄), <xref:System.Text.Json.Utf8JsonReader>및 <xref:System.Text.Json.Utf8JsonWriter> 유형을 사용 하는 방법에 대 한 지침도 포함 되어 있습니다. 문서는 다음과 같은 순서로 섹션으로 구성 됩니다.

* [Newtonsoft.json에 비해 **기본** JsonSerializer 동작의 차이점](#differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson)
* [해결 방법이 필요한 JsonSerializer를 사용 하는 시나리오](#scenarios-using-jsonserializer-that-require-workarounds)
* [JsonSerializer 현재 지원 하지 않는 시나리오](#scenarios-that-jsonserializer-currently-doesnt-support)
* [JToken과 같은 JsonDocument 및 JsonElement (예: Jtoken, Jtoken)](#jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray)
* [Utf8JsonReader와 JsonTextReader 비교](#utf8jsonreader-compared-to-jsontextreader)
* [Utf8JsonWriter와 JsonTextWriter 비교](#utf8jsonwriter-compared-to-jsontextwriter)

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>Newtonsoft.json에 비해 기본 JsonSerializer 동작의 차이점

<xref:System.Text.Json>은 기본적으로 엄격 하며, 호출자를 대신 하 여 추측 또는 해석을 방지 하 여 결정적 동작을 강조 합니다. 라이브러리는 이러한 방식으로 성능 및 보안을 위해 의도적으로 설계 되었습니다. `Newtonsoft.Json`은 기본적으로 유연 합니다. 이러한 기본적인 디자인의 차이점은 기본 동작의 다음과 같은 몇 가지 중요 한 차이점입니다.

### <a name="case-insensitive-deserialization"></a>대/소문자를 구분 하지 않는 deserialization 

Deserialization을 수행 하는 동안 `Newtonsoft.Json`는 기본적으로 대/소문자를 구분 하지 않는 속성 이름을 비교 합니다. <xref:System.Text.Json> 기본값은 대/소문자를 구분 하며,이는 정확히 일치 하는 항목을 수행 하기 때문에 더 나은 성능을 제공 합니다. 대/소문자를 구분 하지 않는 일치를 수행 하는 방법은 대/소문자를 구분 하지 않는 [속성 일치](system-text-json-how-to.md#case-insensitive-property-matching)를 참조 하세요.

ASP.NET Core를 사용 하 여 간접적으로 `System.Text.Json`를 사용 하는 경우 `Newtonsoft.Json`와 같은 동작을 수행 하기 위해 아무것도 수행할 필요가 없습니다. ASP.NET Core는 [카멜식 대/소문자 속성 이름](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) 및 대/소문자를 구분 하지 않는 일치를 `System.Text.Json`사용 하는 경우 해당 설정을 지정 합니다.

### <a name="comments"></a>설명

Deserialization을 수행 하는 동안 `Newtonsoft.Json`는 기본적으로 JSON의 주석을 무시 합니다. <xref:System.Text.Json> 기본값은 [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에 포함 되지 않기 때문에 주석에 대 한 예외를 throw 하는 것입니다. 주석을 허용 하는 방법에 대 한 자세한 내용은 [주석 및 후행 쉼표 허용](system-text-json-how-to.md#allow-comments-and-trailing-commas)을 참조 하세요.

### <a name="trailing-commas"></a>후행 쉼표

Deserialization을 수행 하는 동안 `Newtonsoft.Json`는 기본적으로 후행 쉼표를 무시 합니다. 또한 여러 개의 후행 쉼표를 무시 합니다 (예: `[{"Color":"Red"},{"Color":"Green"},,]`). <xref:System.Text.Json> 기본값은 [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 허용 하지 않으므로 후행 쉼표에 대 한 예외를 throw 하는 것입니다. `System.Text.Json` 허용 하는 방법에 대 한 자세한 내용은 [주석 및 후행 쉼표 허용](system-text-json-how-to.md#allow-comments-and-trailing-commas)을 참조 하세요. 후행 쉼표를 여러 개 허용 하는 방법은 없습니다.

### <a name="json-strings-property-names-and-string-values"></a>JSON 문자열 (속성 이름 및 문자열 값)

Deserialization을 수행 하는 동안 `Newtonsoft.Json` 큰따옴표, 작은따옴표 또는 따옴표 없이 속성 이름을 허용 합니다. 큰따옴표 또는 작은따옴표로 묶은 문자열 값을 허용 합니다. 예를 들어 `Newtonsoft.Json`는 다음 JSON을 허용 합니다.

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json`는 [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 필요 하며 유효한 JSON으로 간주 되는 유일한 형식 이므로 속성 이름과 문자열 값을 큰따옴표로만 허용 합니다.

작은따옴표로 묶인 값을 사용 하면 다음과 같은 메시지와 함께 [JsonException](xref:System.Text.Json.JsonException) 이 발생 합니다.

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>문자열 속성에 대 한 문자열이 아닌 값

문자열 형식의 속성에 대 한 deserialization을 위해 숫자, 리터럴 `true` 및 `false`와 같은 문자열이 아닌 값을 `Newtonsoft.Json` 허용 합니다. 다음 클래스를 성공적으로 deserialize `Newtonsoft.Json` JSON의 예는 다음과 같습니다.

```json
{
  "String1": 1,
  "String2": true,
  "String3": false
}
```

```csharp
public class ExampleClass
{
    public string String1 { get; set; }
    public string String2 { get; set; }
    public string String3 { get; set; }
}
```

`System.Text.Json`은 문자열이 아닌 값을 문자열 속성으로 deserialize 하지 않습니다. 문자열 필드에 대해 문자열이 아닌 값을 받으면 다음과 같은 메시지와 함께 [JsonException](xref:System.Text.Json.JsonException) 이 발생 합니다.

```
The JSON value could not be converted to System.String.
```

### <a name="converter-registration-precedence"></a>변환기 등록 우선 순위

사용자 지정 변환기에 대 한 `Newtonsoft.Json` 등록 우선 순위는 다음과 같습니다.

* 속성의 특성
* 형식의 특성
* [변환기](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) 컬렉션

이 순서는 `Converters` 컬렉션의 사용자 지정 변환기가 형식 수준에서 특성을 적용 하 여 등록 된 변환기에 의해 재정의 됨을 의미 합니다. 이러한 등록은 모두 속성 수준에서 특성에 의해 재정의 됩니다.

사용자 지정 변환기에 대 한 <xref:System.Text.Json> 등록 우선 순위는 다릅니다.

* 속성의 특성
* <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션
* 형식의 특성

여기서 차이점은 `Converters` 컬렉션의 사용자 지정 변환기가 형식 수준에서 특성을 재정의 한다는 것입니다. 이 우선 순위를 설정 하는 것은 런타임 변경 시 디자인 타임 선택 항목을 재정의 하는 것입니다. 우선 순위를 변경할 수 있는 방법은 없습니다.

사용자 지정 변환기 등록에 대 한 자세한 내용은 [사용자 지정 변환기 등록](system-text-json-converters-how-to.md#register-a-custom-converter)을 참조 하세요.

### <a name="character-escaping"></a>문자 이스케이프

Serialization 중에는 문자를 이스케이프 하지 않고 문자를 허용 하는 것에 대 한 `Newtonsoft.Json` 비교적 허용 됩니다. 즉, `xxxx` 문자 코드 포인트 인 `\uxxxx`로 대체 하지 않습니다. 이를 이스케이프 처리 하는 경우에는 문자 앞에 `\`을 내보내면 됩니다. 예를 들어 `"` `\"`됩니다. <xref:System.Text.Json>은 기본적으로 더 많은 문자를 이스케이프 하 여 XSS (교차 사이트 스크립팅) 또는 정보 공개 공격에 대해 심층 방어 보호를 제공 하며,이를 위해 6 문자 시퀀스를 사용 합니다. `System.Text.Json`은 기본적으로 ASCII가 아닌 모든 문자를 이스케이프 하므로 `Newtonsoft.Json`에서 `StringEscapeHandling.EscapeNonAscii`를 사용 하는 경우에는 아무것도 수행할 필요가 없습니다. 또한 `System.Text.Json`는 기본적으로 HTML 구분 문자를 이스케이프 합니다. 기본 `System.Text.Json` 동작을 재정의 하는 방법에 대 한 자세한 내용은 [문자 인코딩 사용자 지정](system-text-json-how-to.md#customize-character-encoding)을 참조 하세요.

### <a name="deserialization-of-object-properties"></a>개체 속성 Deserialization

`Newtonsoft.Json`에서 POCOs의 속성 또는 `Dictionary<string, object>`형식의 사전에 `object` 속성을 deserialize 합니다.

* JSON 페이로드의 기본 값 형식 (`null`제외)을 유추 하 고 저장 된 `string`, `long`, `double`, `boolean`또는 `DateTime`를 boxed 개체로 반환 합니다. *기본 값* 은 json number, string, `true`, `false`, `null`등의 단일 json 값입니다.
* JSON 페이로드의 복합 값에 대 한 `JObject` 또는 `JArray`을 반환 합니다. *복합 값* 은 중괄호 (`{}`) 내에 있는 JSON 키-값 쌍의 컬렉션 이거나 대괄호 안에 있는 값 목록 (`[]`)입니다. 중괄호 또는 대괄호 안의 속성 및 값에는 추가 속성이 나 값이 있을 수 있습니다.
* 페이로드에 `null` JSON 리터럴이 있는 경우 null 참조를 반환 합니다.

<xref:System.Text.Json>은 `System.Object` 속성 또는 사전 값 내에서 기본 값과 복합 값 모두에 대해 boxed `JsonElement`를 저장 합니다. 그러나 `Newtonsoft.Json`와 동일 하 게 `null`를 처리 하 고 페이로드에 `null` JSON 리터럴이 있는 경우 null 참조를 반환 합니다.

`object` 속성에 대 한 형식 유추를 구현 하려면 [사용자 지정 변환기를 작성 하는 방법](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties)의 예제와 같은 변환기를 만듭니다.

### <a name="maximum-depth"></a>최대 깊이

`Newtonsoft.Json`은 기본적으로 최대 깊이 제한이 없습니다. <xref:System.Text.Json>의 경우 기본 제한은 64이 고 <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>을 설정 하 여 구성할 수 있습니다.

### <a name="omit-null-value-properties"></a>Null 값 속성 생략

`Newtonsoft.Json`에는 null 값 속성이 serialization에서 제외 되도록 하는 전역 설정이 있습니다. [Nullvaluehandling. 무시](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_NullValueHandling.htm)합니다. <xref:System.Text.Json>의 해당 옵션은 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues%2A>입니다.

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>해결 방법이 필요한 JsonSerializer를 사용 하는 시나리오

다음 시나리오는 기본 제공 기능에서 지원 되지 않지만 문제 해결을 위해 샘플 코드가 제공 됩니다. 대부분의 해결 방법은 [사용자 지정 변환기](system-text-json-converters-how-to.md)를 구현 해야 합니다.

### <a name="specify-date-format"></a>날짜 형식 지정

`Newtonsoft.Json` `DateTime` 및 `DateTimeOffset` 형식의 속성을 serialize 및 deserialize 하는 방법을 제어 하는 여러 가지 방법을 제공 합니다.

* `DateTimeZoneHandling` 설정을 사용 하 여 모든 `DateTime` 값을 UTC 날짜로 serialize 할 수 있습니다.
* `DateFormatString` 설정 및 `DateTime` 변환기를 사용 하 여 날짜 문자열의 형식을 사용자 지정할 수 있습니다.

<xref:System.Text.Json>기본적으로 지원 되는 유일한 형식은 ISO 8601-1:2019입니다 .이는 널리 사용 되 고 명확 하 게 도입 되었으며 라운드트립을 정확 하 게 수행 하기 때문입니다. 다른 형식을 사용 하려면 사용자 지정 변환기를 만듭니다. 자세한 내용은 [system.object의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)을 참조 하세요.

### <a name="quoted-numbers"></a>따옴표 붙은 숫자

JSON 문자열로 표시 되는 숫자를 직렬화 하거나 deserialize 할 수 `Newtonsoft.Json` (따옴표로 묶인). 예를 들어, `{"DegreesCelsius":23}`대신 `{"DegreesCelsius":"23"}`를 수락할 수 있습니다. <xref:System.Text.Json>에서 해당 동작을 사용 하도록 설정 하려면 다음 예제와 같이 사용자 지정 변환기를 구현 합니다. 변환기는 `long`으로 정의 된 속성을 처리 합니다.

* JSON 문자열로 serialize 합니다. 
* Deserialize 하는 동안 따옴표 안의 JSON 숫자 및 숫자를 허용 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

개별 `long` 속성에서 [특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) 하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection) 하 여이 사용자 지정 변환기를 등록 합니다.

### <a name="dictionary-with-non-string-key"></a>문자열이 아닌 키를 포함 하는 사전

`Newtonsoft.Json`는 `Dictionary<TKey, TValue>`형식의 컬렉션을 지원 합니다. <xref:System.Text.Json>의 사전 컬렉션에 대 한 기본 제공 지원은 `Dictionary<string, TValue>`으로 제한 됩니다. 즉, 키는 문자열 이어야 합니다.

정수 또는 다른 형식을 키로 사용 하 여 사전을 지원 하려면 [사용자 지정 변환기를 작성 하는 방법](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key)의 예제와 같은 변환기를 만듭니다.

### <a name="polymorphic-serialization"></a>다형 serialization

`Newtonsoft.Json`는 다형성 serialization을 자동으로 수행 합니다. <xref:System.Text.Json>의 제한 된 다형성 serialization 기능에 대 한 자세한 내용은 [파생 클래스의 속성 직렬화](system-text-json-how-to.md#serialize-properties-of-derived-classes)를 참조 하세요.

`object`형식으로 파생 클래스를 포함할 수 있는 속성을 정의 하는 방법을 설명 합니다. 이렇게 할 수 없는 경우 [사용자 지정 변환기를 작성 하는 방법](system-text-json-converters-how-to.md#support-polymorphic-deserialization)의 예제와 같이 전체 상속 형식 계층 구조에 대 한 `Write` 메서드를 사용 하 여 변환기를 만드는 것이 또 다른 옵션입니다.

### <a name="polymorphic-deserialization"></a>다형 deserialization

`Newtonsoft.Json`에는 직렬화 하는 동안 JSON에 형식 이름 메타 데이터를 추가 하는 `TypeNameHandling` 설정이 있습니다. Deserialize 하는 동안 메타 데이터를 사용 하 여 다형 deserialization을 수행 합니다. <xref:System.Text.Json>는 다형성 [serialization](system-text-json-how-to.md#serialize-properties-of-derived-classes) 의 제한 된 범위를 수행할 수 있지만 다형성 deserialization은 수행할 수 없습니다.

다형 deserialization을 지원 하려면 [사용자 지정 변환기를 작성 하는 방법](system-text-json-converters-how-to.md#support-polymorphic-deserialization)의 예제와 같은 변환기를 만듭니다.

### <a name="required-properties"></a>필수 속성

Deserialization을 수행 하는 동안 대상 형식의 속성 중 하나에 대해 JSON에서 값을 받지 못한 경우에는 <xref:System.Text.Json> 예외를 throw 하지 않습니다. 예를 들어 `WeatherForecast` 클래스가 있는 경우 다음을 수행 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

다음 JSON은 오류 없이 deserialize 됩니다.

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

JSON에 `Date` 속성이 없는 경우 deserialization이 실패 하도록 하려면 사용자 지정 변환기를 구현 합니다. 다음 샘플 변환기 코드는 deserialization이 완료 된 후 `Date` 속성이 설정 되지 않은 경우 예외를 throw 합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

[POCO 클래스에서 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) 하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection) 하 여이 사용자 지정 변환기를 등록 합니다.

이 패턴을 따르는 경우 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 또는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A>를 재귀적으로 호출 하는 경우 options 개체를 전달 하지 마세요. Options 개체는 <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> 컬렉션을 포함 합니다. `Serialize` 또는 `Deserialize`에 전달 하는 경우 사용자 지정 변환기가 자신을 호출 하 여 스택 오버플로 예외가 발생 하는 무한 루프를 만듭니다. 기본 옵션이 적절 하지 않은 경우 필요한 설정을 사용 하 여 옵션의 새 인스턴스를 만듭니다. 이 접근 방식은 각 새 인스턴스를 독립적으로 캐시 하므로 속도가 느립니다.

앞의 변환기 코드는 단순화 된 예제입니다. 특성 (예: [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) ) 또는 다른 옵션 (예: 사용자 지정 인코더)을 처리 해야 하는 경우에는 추가 논리가 필요 합니다. 또한 예제 코드는 생성자에서 기본값이 설정 된 속성을 처리 하지 않습니다. 이 방법은 다음과 같은 시나리오를 구분 하지 않습니다.

* JSON에서 속성이 누락 되었습니다.
* Nullable이 아닌 형식에 대 한 속성은 JSON에 있지만 값은 `int`의 경우 0과 같이 형식에 대 한 기본값입니다.
* Nullable 형식의 속성은 JSON에 있지만 값은 null입니다.

### <a name="deserialize-null-to-non-nullable-type"></a>Null을 허용 하지 않는 형식으로 Deserialize 합니다. 

다음 시나리오에서는 `Newtonsoft.Json` 예외를 throw 하지 않습니다.

* `NullValueHandling` `Ignore`로 설정 됩니다.
* Deserialization을 수행 하는 동안 JSON은 null을 허용 하지 않는 형식에 대해 null 값을 포함 합니다.

동일한 시나리오에서 <xref:System.Text.Json>는 예외를 throw 합니다. 해당 하는 null 처리 설정은 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>입니다.

대상 유형을 소유 하는 경우 가장 좋은 해결 방법은 해당 속성을 nullable nullable로 설정 하는 것입니다 (예: `int` `int?`로 변경).

또 다른 해결 방법은 `DateTimeOffset` 형식에 대해 null 값을 처리 하는 다음 예제와 같이 형식에 대 한 변환기를 만드는 것입니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

[속성의 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) 하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection) 하 여이 사용자 지정 변환기를 등록 합니다.

**참고:** 위의 변환기는 기본값을 지정 하는 POCOs에 대해 `Newtonsoft.Json`는 것과는 **다른 방식으로 null 값을 처리** 합니다. 예를 들어 다음 코드는 대상 개체를 나타냅니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

그리고 앞의 변환기를 사용 하 여 다음 JSON을 deserialize 한다고 가정 합니다.

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

Deserialization 후 `Date` 속성에 1/1/0001 (`default(DateTimeOffset)`)가 있습니다. 즉, 생성자에 설정 된 값을 덮어씁니다. 동일한 POCO 및 JSON을 지정 하는 경우 `Newtonsoft.Json` deserialization은 `Date` 속성에 1/1/2001을 남겨 둡니다.

### <a name="deserialize-to-immutable-classes-and-structs"></a>변경할 수 없는 클래스 및 구조체로 Deserialize

매개 변수가 있는 생성자를 사용할 수 있기 때문에 변경 불가능 한 클래스 및 구조체로 deserialize 할 수 `Newtonsoft.Json`. <xref:System.Text.Json>은 매개 변수가 없는 public 생성자만 지원 합니다. 이 문제를 해결 하기 위해 사용자 지정 변환기에서 매개 변수가 있는 생성자를 호출할 수 있습니다.

여러 생성자 매개 변수를 사용 하는 변경할 수 없는 구조체는 다음과 같습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

이 구조체를 serialize 하 고 deserialize 하는 변환기는 다음과 같습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

<xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 변환기를 [추가](system-text-json-converters-how-to.md#registration-sample---converters-collection) 하 여이 사용자 지정 변환기를 등록 합니다.

개방형 제네릭 속성을 처리 하는 비슷한 변환기의 예제는 [키-값 쌍에 대 한 기본 제공 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs)를 참조 하세요.

### <a name="specify-constructor-to-use"></a>사용할 생성자를 지정 합니다.

`Newtonsoft.Json` `[JsonConstructor]` 특성을 사용 하면 POCO로 deserialize 할 때 호출할 생성자를 지정할 수 있습니다. <xref:System.Text.Json>는 매개 변수가 없는 생성자만 지원 합니다. 이 문제를 해결 하려면 사용자 지정 변환기에서 필요한 생성자를 호출할 수 있습니다. [변경할 수 없는 클래스 및 구조체로 Deserialize 하](#deserialize-to-immutable-classes-and-structs)는 예제를 참조 하세요.

### <a name="conditionally-ignore-a-property"></a>조건부로 속성 무시

`Newtonsoft.Json`는 serialization 또는 deserialization에서 속성을 조건부로 무시 하는 여러 가지 방법이 있습니다.

* `DefaultContractResolver`를 사용 하 여 임의 조건에 따라 포함 하거나 제외할 속성을 선택할 수 있습니다. 
* `JsonSerializerSettings`의 `NullValueHandling` 및 `DefaultValueHandling` 설정을 사용 하 여 모든 null 값 또는 기본 값 속성을 무시 하도록 지정할 수 있습니다.
* `[JsonProperty]` 특성의 `NullValueHandling` 및 `DefaultValueHandling` 설정을 사용 하면 null 또는 기본값으로 설정 된 경우 무시 해야 하는 개별 속성을 지정할 수 있습니다.

<xref:System.Text.Json>는 serialize 하는 동안 속성을 생략 하는 다음과 같은 방법을 제공 합니다.

* 속성의 [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) 특성을 지정 하면 serialization 중에 JSON에서 속성이 생략 됩니다.
* [Ignorenullvalues](system-text-json-how-to.md#exclude-all-null-value-properties) 전역 옵션을 사용 하면 모든 null 값 속성을 제외할 수 있습니다.
* [Ignorreadonly 속성](system-text-json-how-to.md#exclude-all-read-only-properties) 전역 옵션을 사용 하면 모든 읽기 전용 속성을 제외할 수 있습니다.

이러한 옵션을 사용할 수 **없습니다** .

* 형식에 대 한 기본값이 있는 모든 속성을 무시 합니다.
* 형식에 대 한 기본값이 있는 선택한 속성을 무시 합니다.
* 해당 값이 null 인 경우 선택한 속성을 무시 합니다.
* 런타임에 평가 되는 임의의 조건에 따라 선택한 속성을 무시 합니다. 

이 기능을 위해 사용자 지정 변환기를 작성할 수 있습니다. 다음은이 접근 방식을 보여 주는 샘플 POCO 및 사용자 지정 변환기입니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

변환기를 설정 하면 해당 값이 null, 빈 문자열 또는 "N/A" 인 경우 serialization에서 `Summary` 속성이 생략 됩니다. 

[클래스에서 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) 하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection) 하 여이 사용자 지정 변환기를 등록 합니다.

이 방법에는 다음과 같은 경우 추가 논리가 필요 합니다.

* POCO에는 복잡 한 속성이 포함 되어 있습니다.
* `[JsonIgnore]` 또는 사용자 지정 인코더와 같은 옵션과 같은 특성을 처리 해야 합니다.

### <a name="callbacks"></a>콜백

`Newtonsoft.Json`를 사용 하면 serialization 또는 deserialization 프로세스의 여러 지점에서 사용자 지정 코드를 실행할 수 있습니다.

* OnDeserializing (개체 deserialize를 시작할 때)
* OnDeserialized 됨 (개체 deserialize 완료 시)
* OnSerializing (개체 직렬화를 시작할 때)
* OnSerialized 됨 (개체 직렬화를 완료 한 경우)

<xref:System.Text.Json>에서 사용자 지정 변환기를 작성 하 여 콜백을 시뮬레이션할 수 있습니다. 다음 예제에서는 POCO의 사용자 지정 변환기를 보여 줍니다. 변환기에는 `Newtonsoft.Json` 콜백에 해당 하는 각 지점에서 메시지를 표시 하는 코드가 포함 되어 있습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

[클래스에서 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) 하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection) 하 여이 사용자 지정 변환기를 등록 합니다.

이전 샘플을 따르는 사용자 지정 변환기를 사용 하는 경우:

* `OnDeserializing` 코드는 새 POCO 인스턴스에 액세스할 수 없습니다. Deserialization을 시작할 때 새 POCO 인스턴스를 조작 하려면 POCO 생성자에 해당 코드를 저장 합니다.
* `Serialize` 또는 `Deserialize`를 재귀적으로 호출 하는 경우 options 개체를 전달 하지 마세요. Options 개체는 `Converters` 컬렉션을 포함 합니다. `Serialize` 또는 `Deserialize`에 전달 하는 경우 변환기가 사용 되어 스택 오버플로 예외가 발생 하는 무한 루프를 만듭니다.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>JsonSerializer 현재 지원 하지 않는 시나리오

해결 방법은 다음과 같은 시나리오에서 가능 하지만 일부는 구현 하기가 비교적 어렵습니다. 이 문서에서는 이러한 시나리오에 대 한 해결 방법에 대 한 코드 샘플을 제공 하지 않습니다.

`System.Text.Json`에 해당 하는 항목이 없는 `Newtonsoft.Json` 기능에 대 한 완전 한 목록은 아닙니다. 이 목록에는 [GitHub 문제](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) 또는 [stackoverflow](https://stackoverflow.com/questions/tagged/system.text.json) 게시물에서 요청 된 많은 시나리오가 포함 되어 있습니다.

이러한 시나리오 중 하나에 대 한 해결 방법을 구현 하 고 코드를 공유할 수 있는 경우 페이지 맨 아래에 있는 "**이 페이지**" 단추를 선택 합니다. 그러면 GitHub 문제를 만들어 페이지 아래쪽에 나열 된 문제에 추가 합니다.

### <a name="types-without-built-in-support"></a>기본 제공 지원이 없는 형식

<xref:System.Text.Json>는 다음 형식에 대 한 기본 제공 지원을 제공 하지 않습니다.

* <xref:System.Data.DataTable> 및 관련 형식
* F#[구분 된 공용 구조체](../../fsharp/language-reference/discriminated-unions.md), [레코드 형식](../../fsharp/language-reference/records.md)및 [익명 레코드 형식과](../../fsharp/language-reference/anonymous-records.md)같은 형식입니다.
* <xref:System.Collections.Specialized> 네임 스페이스의 컬렉션 형식
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple> 및 연결 된 제네릭 형식

기본 제공 지원이 없는 형식에 대해 사용자 지정 변환기를 구현할 수 있습니다.

### <a name="public-and-non-public-fields"></a>Public 및 public이 아닌 필드

`Newtonsoft.Json` 필드 및 속성을 serialize 및 deserialize 할 수 있습니다. <xref:System.Text.Json>는 공용 속성 에서만 작동 합니다. 사용자 지정 변환기는이 기능을 제공할 수 있습니다.

### <a name="internal-and-private-property-setters-and-getters"></a>내부 및 개인 속성 setter 및 getter

`Newtonsoft.Json`는 `JsonProperty` 특성을 통해 전용 및 내부 속성 setter 및 getter를 사용할 수 있습니다. <xref:System.Text.Json>는 공용 setter만 지원 합니다. 사용자 지정 변환기는이 기능을 제공할 수 있습니다.

### <a name="preserve-object-references-and-handle-loops"></a>개체 참조 유지 및 루프 처리

기본적으로 `Newtonsoft.Json`는 값으로 직렬화 됩니다. 예를 들어 개체가 동일한 `Person` 개체에 대 한 참조를 포함 하는 두 개의 속성을 포함 하는 경우 해당 `Person` 개체의 속성 값이 JSON에서 중복 됩니다.

`Newtonsoft.Json`에는 참조로 serialize 할 수 있는 `JsonSerializerSettings` `PreserveReferencesHandling` 설정이 있습니다.

* 첫 번째 `Person` 개체에 대해 만든 JSON에 식별자 메타 데이터가 추가 됩니다.
* 두 번째 `Person` 개체에 대해 만든 JSON에는 속성 값 대신 해당 식별자에 대 한 참조가 포함 됩니다.

또한 `Newtonsoft.Json`에는 예외를 throw 하는 대신 순환 참조를 무시할 수 있는 `ReferenceLoopHandling` 설정이 있습니다.

<xref:System.Text.Json>는 값으로 직렬화만 지원 하 고 순환 참조에 대해 예외를 throw 합니다.

### <a name="systemruntimeserialization-attributes"></a>System.object. 직렬화 특성

<xref:System.Text.Json>은 `DataMemberAttribute` 및 `IgnoreDataMemberAttribute`과 같은 `System.Runtime.Serialization` 네임 스페이스의 특성을 지원 하지 않습니다.

### <a name="octal-numbers"></a>8 진수

`Newtonsoft.Json`는 앞에 오는 0을 8 진수로 처리 합니다. <xref:System.Text.Json> [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 허용 하지 않으므로 선행 0을 허용 하지 않습니다.

### <a name="populate-existing-objects"></a>기존 개체 채우기

`Newtonsoft.Json`의 `JsonConvert.PopulateObject` 메서드는 새 인스턴스를 만드는 대신 JSON 문서를 클래스의 기존 인스턴스로 deserialize 합니다. <xref:System.Text.Json>는 항상 기본 public 매개 변수가 없는 생성자를 사용 하 여 대상 형식의 새 인스턴스를 만듭니다. 사용자 지정 변환기는 기존 인스턴스로 deserialize 할 수 있습니다.

### <a name="reuse-rather-than-replace-properties"></a>속성 바꾸기 대신 다시 사용

`Newtonsoft.Json` `ObjectCreationHandling` 설정을 사용 하면 deserialization 중에 속성의 개체를 대체 하는 대신 다시 사용 하도록 지정할 수 있습니다. <xref:System.Text.Json>는 항상 속성에서 개체를 바꿉니다.  사용자 지정 변환기는이 기능을 제공할 수 있습니다.

### <a name="add-to-collections-without-setters"></a>Setter를 사용 하지 않고 컬렉션에 추가

Deserialization을 수행 하는 동안 속성에 setter가 없는 경우에도 `Newtonsoft.Json` 개체를 컬렉션에 추가 합니다. <xref:System.Text.Json>는 setter가 없는 속성을 무시 합니다. 사용자 지정 변환기는이 기능을 제공할 수 있습니다.

### <a name="missingmemberhandling"></a>MissingMemberHandling

JSON에 대상 형식에 없는 속성이 포함 된 경우 deserialization 하는 동안 예외를 throw 하도록 `Newtonsoft.Json`를 구성할 수 있습니다. <xref:System.Text.Json>는 [[JsonExtensionData] 특성](system-text-json-how-to.md#handle-overflow-json)을 사용 하는 경우를 제외 하 고 JSON의 추가 속성을 무시 합니다. 누락 된 멤버 기능에 대 한 해결 방법은 없습니다.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json`를 사용 하면 `TraceWriter`를 사용 하 여 serialization 또는 deserialization에 의해 생성 된 로그를 볼 수 있습니다. <xref:System.Text.Json>는 로깅을 수행 하지 않습니다.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JToken과 같은 JsonDocument 및 JsonElement (예: Jtoken, Jtoken)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>는 기존 JSON 페이로드에서 **읽기** 전용 문서 개체 모델 (DOM)를 구문 분석 하 고 작성 하는 기능을 제공 합니다. DOM은 JSON 페이로드의 데이터에 대 한 임의 액세스를 제공 합니다. 페이로드를 구성 하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다. `JsonElement` 형식은 JSON 텍스트를 일반적인 .NET 형식으로 변환 하는 Api를 제공 합니다. `JsonDocument` <xref:System.Text.Json.JsonDocument.RootElement> 속성을 노출 합니다.

### <a name="jsondocument-is-idisposable"></a>JsonDocument는 IDisposable입니다.

`JsonDocument`는 풀링된 버퍼에 데이터의 메모리 내 뷰를 빌드합니다. 따라서 `Newtonsoft.Json`에서 `JObject` 또는 `JArray`와 달리 `JsonDocument` 형식은 `IDisposable`를 구현 하며 using 블록 내에서 사용 해야 합니다. 

수명 소유권을 양도 하 고 호출자에 게 책임을 삭제 하려는 경우에만 API에서 `JsonDocument`을 반환 합니다. 대부분의 시나리오에서는 필요 하지 않습니다. 호출자가 전체 JSON 문서를 사용 해야 하는 경우 <xref:System.Text.Json.JsonElement><xref:System.Text.Json.JsonDocument.RootElement%2A><xref:System.Text.Json.JsonElement.Clone%2A> 반환 합니다. 호출자가 JSON 문서 내의 특정 요소를 사용 해야 하는 경우 해당 <xref:System.Text.Json.JsonElement>의 <xref:System.Text.Json.JsonElement.Clone%2A> 반환 합니다. `Clone`하지 않고 `RootElement` 또는 하위 요소를 직접 반환 하는 경우 호출자는이를 소유 하는 `JsonDocument` 삭제 된 후 반환 된 `JsonElement`에 액세스할 수 없습니다.

`Clone`해야 하는 예는 다음과 같습니다.

```csharp
public JsonElement LookAndLoad(JsonElement source)
{
    string json = File.ReadAllText(source.GetProperty("fileName").GetString());
   
    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        return doc.RootElement.Clone();
    }
}
```

위의 코드에는 `fileName` 속성을 포함 하는 `JsonElement` 필요 합니다. JSON 파일을 열고 `JsonDocument`를 만듭니다. 메서드는 호출자가 전체 문서를 사용 하 고 있는 것으로 가정 하 여 `RootElement``Clone` 반환 합니다. 

`JsonElement` 받고 하위 요소를 반환 하는 경우 하위 요소의 `Clone`를 반환할 필요가 없습니다. 호출자는 전달 된 `JsonElement`이 속한 `JsonDocument`의 활성 상태를 유지 해야 합니다. 예를 들면 다음과 같습니다.:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument는 읽기 전용입니다.

<xref:System.Text.Json> DOM은 JSON 요소를 추가, 제거 또는 수정할 수 없습니다. 이러한 방식으로 성능을 향상 하 고 일반적인 JSON 페이로드 크기를 구문 분석 하기 위한 할당 (< 1mb)을 줄일 수 있습니다. 현재 시나리오에서 수정 가능한 DOM을 사용 하는 경우 다음 해결 방법 중 하나를 사용할 수 있습니다.

* `JsonDocument`를 처음부터 새로 작성 하려면 (즉, `Parse` 메서드에 기존 JSON 페이로드를 전달 하지 않고), `Utf8JsonWriter`를 사용 하 여 JSON 텍스트를 작성 하 고이의 출력을 구문 분석 하 여 새 `JsonDocument`를 만듭니다.
* 기존 `JsonDocument`을 수정 하려면이를 사용 하 여 JSON 텍스트를 작성 하 고, 작성 하는 동안 변경 하 고, 새 `JsonDocument`을 만들 때의 출력을 구문 분석 합니다.
* `Newtonsoft.Json`에서 `JObject.Merge` 또는 `JContainer.Merge` Api에 해당 하는 기존 JSON 문서를 병합 하려면 [이 GitHub 문제](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853)를 참조 하세요.

### <a name="jsonelement-is-a-union-struct"></a>JsonElement는 union 구조체입니다.

`JsonDocument`은 모든 JSON 요소를 포함 하는 공용 구조체 형식인 <xref:System.Text.Json.JsonElement>형식의 속성으로 `RootElement`를 노출 합니다. `Newtonsoft.Json` `JObject`,`JArray`, `JToken`등의 전용 계층적 유형을 사용 합니다. `JsonElement`는 검색 및 열거할 수 있는 기능으로, `JsonElement`를 사용 하 여 JSON 요소를 .NET 형식으로 구체화할 수 있습니다.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>하위 요소에 대해 JsonDocument 및 JsonElement를 검색 하는 방법

`JObject` 또는 `Newtonsoft.Json` `JArray`를 사용 하 여 JSON 토큰을 검색 하는 것은 일부 사전에서 조회 되기 때문에 비교적 빠릅니다. 비교 하 여 `JsonElement` 검색은 속성을 순차적으로 검색 해야 하므로 상대적으로 느립니다 (예: `TryGetProperty`를 사용 하는 경우). <xref:System.Text.Json>은 조회 시간이 아니라 초기 구문 분석 시간을 최소화 하도록 설계 되었습니다. 따라서 `JsonDocument` 개체를 검색할 때 성능을 최적화 하려면 다음 방법을 사용 합니다.

* 사용자 고유의 인덱싱 또는 루프를 수행 하는 대신 기본 제공 열거자 (<xref:System.Text.Json.JsonElement.EnumerateArray%2A> 및 <xref:System.Text.Json.JsonElement.EnumerateObject%2A>)를 사용 합니다.
* `RootElement`를 사용 하 여 모든 속성을 통해 전체 `JsonDocument`에서 순차적 검색을 수행 하지 않습니다. 대신, 알려진 JSON 데이터 구조를 기반으로 중첩 된 JSON 개체를 검색 합니다. 예를 들어 `Student` 개체에서 `Grade` 속성을 찾고 있는 경우 `JsonElement` 속성을 검색 하는 모든 `Grade` 개체를 검색 하는 대신 `Student` 개체를 반복 하 고 각 개체에 대 한 `Grade` 값을 가져옵니다. 후자를 수행 하면 동일한 데이터에 대해 불필요 한 패스가 발생 합니다.

코드 예제는 [데이터 액세스에 JsonDocument 사용](system-text-json-how-to.md#use-jsondocument-for-access-to-data)을 참조 하세요.

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader와 JsonTextReader 비교

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>는 u t f-8로 인코딩된 JSON 텍스트에 대 한 고성능, 낮은 할당, 전방 전용 판독기로, [ReadOnlySpan\<바이트 >](xref:System.ReadOnlySpan%601) 또는 [ReadOnlySequence\<바이트 >](xref:System.Buffers.ReadOnlySequence%601)에서 읽습니다. `Utf8JsonReader`는 사용자 지정 파서 및 deserializers를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.

다음 섹션에서는 `Utf8JsonReader`사용을 위한 권장 프로그래밍 패턴에 대해 설명 합니다.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader는 ref 구조체입니다.

`Utf8JsonReader` 형식은 *ref 구조체*이므로 [특정 제한 사항이](../../csharp/language-reference/keywords/ref.md#ref-struct-types)있습니다. 예를 들어 ref 구조체가 아닌 클래스 또는 구조체에 필드로 저장할 수 없습니다. 고성능을 얻기 위해이 형식은 입력 [ReadOnlySpan\<바이트 >](xref:System.ReadOnlySpan%601)를 캐시 해야 하므로 해당 형식이 ref 구조체 이기 때문에 `ref struct` 이어야 합니다. 또한이 형식은 상태를 유지 하기 때문에 변경 가능 합니다. 따라서 값 **이 아닌 ref로 전달** 합니다. 값으로 전달 하면 구조체 복사본이 생성 되 고 상태 변경 내용이 호출자에 게 표시 되지 않습니다. `Newtonsoft.Json` `JsonTextReader`은 클래스 이므로 `Newtonsoft.Json`와 다릅니다. Ref 구조체를 사용 하는 방법에 대 한 자세한 내용은 [안전 하 고 C# 효율적인 코드 작성](../../csharp/write-safe-efficient-code.md)을 참조 하세요.

### <a name="read-utf-8-text"></a>UTF-8 텍스트 읽기

`Utf8JsonReader`사용 하는 동안 최상의 성능을 얻으려면 UTF-16 문자열이 아닌 u t f-8 텍스트로 이미 인코드된 JSON 페이로드를 읽어 보십시오. 코드 예제를 보려면 Utf8JsonReader를 [사용 하 여 데이터 필터링](system-text-json-how-to.md#filter-data-using-utf8jsonreader)을 참조 하세요.

### <a name="read-with-a-stream-or-pipereader"></a>Stream 또는 PipeReader를 사용 하 여 읽기

`Utf8JsonReader`는 u t f-8로 인코딩된 [ReadOnlySpan\<byte >](xref:System.ReadOnlySpan%601) 또는 [ReadOnlySequence\<바이트 >](xref:System.Buffers.ReadOnlySequence%601) (<xref:System.IO.Pipelines.PipeReader>에서 읽은 결과)에서 읽기를 지원 합니다.

동기 읽기의 경우 스트림의 끝에서 바이트 배열로 JSON 페이로드를 읽은 후 판독기에 전달할 수 있습니다. U t f-16으로 인코딩된 문자열에서 읽으려면 <xref:System.Text.Encoding.UTF8>를 호출 합니다.<xref:System.Text.Encoding.GetBytes%2A> 먼저 문자열을 u t f-8로 인코딩된 바이트 배열로 변환 합니다. 그런 다음 `Utf8JsonReader`에 전달 합니다. 

`Utf8JsonReader`는 입력을 JSON 텍스트로 간주 하므로 UTF-8 BOM (바이트 순서 표시)은 잘못 된 JSON으로 간주 됩니다. 호출자는 데이터를 판독기에 전달 하기 전에 필터링 해야 합니다.

코드 예제는 [Utf8JsonReader 사용](system-text-json-how-to.md#use-utf8jsonreader)을 참조 하세요.

### <a name="read-with-multi-segment-readonlysequence"></a>다중 세그먼트 ReadOnlySequence를 사용 하 여 읽기

JSON 입력이 [ReadOnlySpan\<바이트 >](xref:System.ReadOnlySpan%601)경우 읽기 루프를 진행할 때 판독기의 `ValueSpan` 속성에서 각 json 요소에 액세스할 수 있습니다. 그러나 입력이 [ReadOnlySequence\<바이트 >](xref:System.Buffers.ReadOnlySequence%601) (<xref:System.IO.Pipelines.PipeReader>에서 읽은 결과) 인 경우 일부 JSON 요소는 `ReadOnlySequence<byte>` 개체의 여러 세그먼트를 걸쳐 있을 수 있습니다. 이러한 요소는 연속 메모리 블록의 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>에서 액세스할 수 없습니다. 대신 다중 `ReadOnlySequence<byte>` 세그먼트가 입력으로 사용 될 때마다 판독기에서 <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> 속성을 폴링하여 현재 JSON 요소에 액세스 하는 방법을 확인 합니다. 권장 패턴은 다음과 같습니다.

```csharp
while (reader.Read())
{
    switch (reader.TokenType)
    {
        // ...
        ReadOnlySpan<byte> jsonElement = reader.HasValueSequence ?
            reader.ValueSequence.ToArray() :
            reader.ValueSpan;
        // ...
    }
}
```

### <a name="use-valuetextequals-for-property-name-lookups"></a>속성 이름 조회에 대 한 사용

속성 이름 조회를 위해 <xref:System.MemoryExtensions.SequenceEqual%2A>를 호출 하 여 바이트 단위 비교를 수행 하려면 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>를 사용 하지 마세요. 해당 메서드가 JSON에서 이스케이프 된 모든 문자를 unescapes 하므로 대신 <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>를 호출 합니다. "Name" 이라는 속성을 검색 하는 방법을 보여 주는 예제는 다음과 같습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>Null 값을 nullable 값 형식으로 읽습니다.

`Newtonsoft.Json`는 `TokenType`를 반환 하 여 `Null` `bool?`를 처리 하는 `ReadAsBoolean`와 같은 <xref:System.Nullable%601>를 반환 하는 Api를 제공 합니다. 기본 제공 `System.Text.Json` Api는 null을 허용 하지 않는 값 형식만 반환 합니다. 예를 들어 <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType>은 `bool`을 반환 합니다. JSON에서 `Null` 발견 되 면 예외를 throw 합니다. 다음 예제에서는 null을 처리 하는 두 가지 방법, 즉 nullable 값 형식을 반환 하 고 기본값을 반환 하 여 null을 처리 하는 방법을 보여 줍니다.

```csharp
public bool? ReadAsNullableBoolean()
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return null;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

```csharp
public bool ReadAsBoolean(bool defaultValue)
{
    _reader.Read();
    if (_reader.TokenType == JsonTokenType.Null)
    {
        return defaultValue;
    }
    if (_reader.TokenType != JsonTokenType.True && _reader.TokenType != JsonTokenType.False)
    {
        throw new JsonException();
    }
    return _reader.GetBoolean();
}
```

### <a name="multi-targeting"></a>멀티 타기팅

특정 대상 프레임 워크에 대 한 `Newtonsoft.Json`를 계속 사용 해야 하는 경우 다중 대상을 지정할 수 있으며 두 가지 구현을 구현할 수 있습니다. 그러나이 방법은 간단 하지 않으며 일부 `#ifdefs` 및 원본 복제가 필요 합니다. 가능한 한 많은 코드를 공유 하는 한 가지 방법은 `Utf8JsonReader` 및 `Newtonsoft.Json` `JsonTextReader`주위에 `ref struct` 래퍼를 만드는 것입니다. 이 래퍼는 동작 차이를 격리 하면서 공개 노출 영역을 통합 합니다. 이렇게 하면 새 형식을 참조로 전달 하는 것과 함께 주로 형식 생성에 대 한 변경 내용을 격리할 수 있습니다. [DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 라이브러리가 따르는 패턴은 다음과 같습니다.

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter와 JsonTextWriter 비교

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>는 `String`, `Int32`및 `DateTime`같은 일반적인 .NET 유형에 서 UTF-8 인코딩 JSON 텍스트를 작성 하는 고성능 방법입니다. 기록기는 사용자 지정 serializer를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.

다음 섹션에서는 `Utf8JsonWriter`사용을 위한 권장 프로그래밍 패턴에 대해 설명 합니다.

### <a name="write-with-utf-8-text"></a>UTF-8 텍스트를 사용 하 여 쓰기

`Utf8JsonWriter`사용 하는 동안 최상의 성능을 얻으려면 UTF-16 문자열이 아닌 u t f-8 텍스트로 이미 인코드된 JSON 페이로드를 작성 합니다. <xref:System.Text.Json.JsonEncodedText>를 사용 하 여 알려진 문자열 속성 이름 및 값을 캐시 하 고 정적으로 미리 인코딩하고 UTF-16 문자열 리터럴을 사용 하는 대신 작성기에 전달 합니다. 이는 u t f-8 바이트 배열을 캐시 하 고 사용 하는 것 보다 빠릅니다.

이 방법은 사용자 지정 이스케이프를 수행 해야 하는 경우에도 작동 합니다. `System.Text.Json` 문자열을 작성 하는 동안 이스케이프를 사용 하지 않도록 설정할 수 없습니다. 그러나 사용자 지정 <xref:System.Text.Encodings.Web.JavaScriptEncoder>를 작성기에 옵션으로 전달 하거나 `JavascriptEncoder`를 사용 하 여 이스케이프를 수행 하는 고유한 `JsonEncodedText` 만든 다음 문자열 대신 `JsonEncodedText`를 작성할 수 있습니다. 자세한 내용은 [문자 인코딩 사용자 지정](system-text-json-how-to.md#customize-character-encoding)을 참조 하세요.

### <a name="write-raw-values"></a>원시 값 쓰기

`Newtonsoft.Json` `WriteRawValue` 메서드는 값이 필요한 원시 JSON을 작성 합니다. <xref:System.Text.Json>에는 직접적인 대응 기능이 없지만, 올바른 JSON만 작성 되도록 하는 해결 방법은 다음과 같습니다.

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>문자 이스케이프 사용자 지정

`JsonTextWriter` [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) 설정은 ASCII가 아닌 문자 **또는** HTML 문자를 모두 이스케이프 하는 옵션을 제공 합니다. 기본적으로 `Utf8JsonWriter`는 ASCII가 아닌 문자 **및** HTML 문자를 모두 이스케이프 합니다. 이러한 이스케이프는 심층 방어 보안을 위해 수행 됩니다. 다른 이스케이프 정책을 지정 하려면 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 만들고 <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>를 설정 합니다. 자세한 내용은 [문자 인코딩 사용자 지정](system-text-json-how-to.md#customize-character-encoding)을 참조 하세요.

### <a name="customize-json-format"></a>JSON 형식 사용자 지정

`JsonTextWriter`에는 다음과 같은 설정이 포함 됩니다. `Utf8JsonWriter`에는 해당 항목이 없습니다.

* [들여쓰기](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) -들여쓸 문자 수를 지정 합니다. `Utf8JsonWriter` 항상 2 자 들여쓰기를 수행 합니다.
* [Indentchar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) -들여쓰기에 사용할 문자를 지정 합니다.  `Utf8JsonWriter`은 항상 공백을 사용 합니다.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) -문자열 값을 묶는 데 사용할 문자를 지정 합니다.  `Utf8JsonWriter` 항상 큰따옴표를 사용 합니다.
* [QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) -속성 이름을 따옴표로 묶을 지 여부를 지정 합니다.  `Utf8JsonWriter` 항상 따옴표로 묶습니다.

이러한 방법으로 `Utf8JsonWriter`에서 생성 된 JSON을 사용자 지정할 수 있는 해결 방법은 없습니다.

### <a name="write-null-values"></a>Null 값 쓰기

`Utf8JsonWriter`를 사용 하 여 null 값을 쓰려면를 호출 합니다.

* 값으로 null을 사용 하 여 키-값 쌍을 쓰려면 <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> 합니다.
* null을 JSON 배열의 요소로 쓰려면 <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> 합니다.

문자열 속성의 경우 문자열이 null 이면 <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> 및 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>은 `WriteNull` 및 `WriteNullValue`와 동일 합니다.

### <a name="write-timespan-uri-or-char-values"></a>Timespan, Uri 또는 char 값 쓰기

`JsonTextWriter`는 [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)및 [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) 값에 대 한 `WriteValue` 메서드를 제공 합니다. `Utf8JsonWriter`에는 동일한 메서드가 없습니다. 대신 `ToString()`를 호출 하 여 이러한 값을 문자열로 포맷 하 고 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>를 호출 합니다.

### <a name="multi-targeting"></a>멀티 타기팅

특정 대상 프레임 워크에 대 한 `Newtonsoft.Json`를 계속 사용 해야 하는 경우 다중 대상을 지정할 수 있으며 두 가지 구현을 구현할 수 있습니다. 그러나이 방법은 간단 하지 않으며 일부 `#ifdefs` 및 원본 복제가 필요 합니다. 가능한 한 많은 코드를 공유 하는 한 가지 방법은 `Utf8JsonWriter`와 `Newtonsoft` `JsonTextWriter`에 대 한 래퍼를 만드는 것입니다. 이 래퍼는 동작 차이를 격리 하면서 공개 노출 영역을 통합 합니다. 이를 통해 주로 형식 생성에 대 한 변경 내용을 격리할 수 있습니다. [DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 라이브러리는 다음과 같습니다.

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>추가 자료

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [System.object 개요](system-text-json-overview.md)
* [System.object를 사용 하는 방법](system-text-json-how-to.md)
* [사용자 지정 변환기를 작성 하는 방법](system-text-json-converters-how-to.md)
* [System.object의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)
* [System.object API 참조](xref:System.Text.Json)
* [System.string API 참조](xref:System.Text.Json.Serialization)
