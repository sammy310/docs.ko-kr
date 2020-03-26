---
title: 에서 마이그레이션 Newtonsoft.Json System.Text.Json - .NET
author: tdykstra
ms.author: tdykstra
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: 01/10/2020
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 957bafcdf69d5792702962db6598458a0c8ec974
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291578"
---
# <a name="how-to-migrate-from-newtonsoftjson-to-systemtextjson"></a>Newtonsoft.json에서 System.Text.Json으로 마이그레이션하는 방법

이 문서에서는 [Newtonsoft.Json에서](https://www.newtonsoft.com/json) 로 <xref:System.Text.Json>마이그레이션하는 방법을 보여 주며.

네임스페이스는 `System.Text.Json` 자바스크립트 개체 표기법(JSON)에서 직렬화및 직렬화하는 기능을 제공합니다. `System.Text.Json` 라이브러리는 [.NET Core 3.0](https://aka.ms/netcore3download) 공유 프레임워크에 포함됩니다. 다른 대상 프레임워크의 경우 [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet 패키지를 설치합니다. 이 패키지는 다음을 지원합니다.

* .NET 표준 2.0 이상 버전
* .NET 프레임워크 4.7.2 이상 버전
* .NET 코어 2.0, 2.1 및 2.2

`System.Text.Json`주로 성능, 보안 및 표준 준수에 중점을 둡니다. 기본 동작에 몇 가지 주요 차이점이 `Newtonsoft.Json`있으며. 일부 `System.Text.Json` 시나리오에서는 기본 제공 기능이 없지만 권장되는 해결 방법이 있습니다. 다른 시나리오에서는 해결 방법을 사용할 수 없습니다. 응용 프로그램이 누락된 기능에 의존하는 경우 시나리오를 지원할 수 있는지 확인하기 위해 [문제를 제기하는](https://github.com/dotnet/runtime/issues/new) 것이 좋습니다.

<!-- For information about which features might be added in future releases, see the [Roadmap](https://github.com/dotnet/runtime/tree/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md). [Restore this when the roadmap is updated.]-->

이 문서의 <xref:System.Text.Json.JsonSerializer> 대부분은 API를 사용하는 방법에 관한 것이지만(문서 개체 <xref:System.Text.Json.JsonDocument> 모델 또는 DOM을 나타내는) <xref:System.Text.Json.Utf8JsonReader>및 <xref:System.Text.Json.Utf8JsonWriter> 형식을 사용하는 방법에 대한 지침도 포함되어 있습니다.

## <a name="table-of-differences-between-newtonsoftjson-and-systemtextjson"></a>뉴턴소프트.Json과 시스템 간의 차이점 표.Text.Json

다음 표에는 `Newtonsoft.Json` 기능 `System.Text.Json` 및 등가물 등이 나열되어 있습니다. 등가물은 다음 범주에 속합니다.

* 내장 기능에서 지원됩니다. 유사한 동작을 `System.Text.Json` 가져오는 경우 특성 또는 전역 옵션을 사용해야 할 수 있습니다.
* 지원되지 않는 해결 방법은 가능합니다. 해결 방법을 사용하면 기능과 `Newtonsoft.Json` 완전한 패리티를 제공하지 못할 수 있는 사용자 지정 [변환기입니다.](system-text-json-converters-how-to.md) 이들 중 일부에 대 한 샘플 코드는 예제로 제공 됩니다. 이러한 `Newtonsoft.Json` 기능을 사용할 경우 .NET 개체 모델 또는 기타 코드 변경 사항을 수정해야 합니다.
* 지원되지 않는 해결 방법은 실용적이지 않거나 불가능합니다. 이러한 `Newtonsoft.Json` 기능을 사용하면 크게 변경하지 않으면 마이그레이션이 불가능합니다.

| 뉴턴소프트.Json 기능                               | 시스템.텍스트.Json 등가물 |
|-------------------------------------------------------|-----------------------------|
| 대/소문자 구분 되지 않습니다 기본적으로 역직렬화           | ✔️ [속성이름지정지 전역 설정](#case-insensitive-deserialization) |
| 낙타 대/소문자 속성 이름                             | ✔️ [속성 명명정책 전역 설정](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) |
| 최소한의 문자 이스케이프                            | ✔️ [엄격한 문자 이스케이프, 구성 가능](#minimal-character-escaping) |
| `NullValueHandling.Ignore`전역 설정             | [✔️ 무시NullValues 전역 옵션](system-text-json-how-to.md#exclude-all-null-value-properties) |
| 댓글 허용                                        | ✔️ [읽기댓글처리 전역 설정](#comments) |
| 후행 쉼표 허용                                 | [✔️ 허용트레일링콤마스 글로벌 설정](#trailing-commas) |
| 사용자 지정 변환기 등록                         | ✔️ [우선 순위는 다릅니다.](#converter-registration-precedence) |
| 기본적으로 최대 깊이 없음                           | ✔️ [기본 최대 깊이 64, 구성 가능](#maximum-depth) |
| 광범위한 유형 지원                    | ⚠️[일부 유형에는 사용자 지정 변환기가 필요합니다.](#types-without-built-in-support) |
| 문자열을 숫자로 직렬화                        | ⚠️[지원되지 않음, 해결 방법, 샘플](#quoted-numbers) |
| 비문자열 `Dictionary` 키로 직렬화          | ⚠️[지원되지 않음, 해결 방법, 샘플](#dictionary-with-non-string-key) |
| 다형성 직렬화                             | ⚠️[지원되지 않음, 해결 방법, 샘플](#polymorphic-serialization) |
| 다형성 직렬화                           | ⚠️[지원되지 않음, 해결 방법, 샘플](#polymorphic-deserialization) |
| 추론된 형식을 속성에 `object` 역직렬화      | ⚠️[지원되지 않음, 해결 방법, 샘플](#deserialization-of-object-properties) |
| JSON `null` 리터럴을 null able 값 형식으로 역직렬화 | ⚠️[지원되지 않음, 해결 방법, 샘플](#deserialize-null-to-non-nullable-type) |
| 변경할 수 없는 클래스 및 구조체로 직렬화          | ⚠️[지원되지 않음, 해결 방법, 샘플](#deserialize-to-immutable-classes-and-structs) |
| `[JsonConstructor]` 특성                         | ⚠️[지원되지 않음, 해결 방법, 샘플](#specify-constructor-to-use) |
| `Required`속성 `[JsonProperty]` 에 설정        | ⚠️[지원되지 않음, 해결 방법, 샘플](#required-properties) |
| `NullValueHandling`속성 `[JsonProperty]` 에 설정 | ⚠️[지원되지 않음, 해결 방법, 샘플](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`속성 `[JsonProperty]` 에 설정 | ⚠️[지원되지 않음, 해결 방법, 샘플](#conditionally-ignore-a-property)  |
| `DefaultValueHandling`전역 설정                 | ⚠️[지원되지 않음, 해결 방법, 샘플](#conditionally-ignore-a-property) |
| `DefaultContractResolver`속성을 제외하려면       | ⚠️[지원되지 않음, 해결 방법, 샘플](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`, `DateFormatString` 설정   | ⚠️[지원되지 않음, 해결 방법, 샘플](#specify-date-format) |
| 콜백                                             | ⚠️[지원되지 않음, 해결 방법, 샘플](#callbacks) |
| 공공 및 비공개 분야 지원              | ⚠️[지원되지 않음, 해결 해결](#public-and-non-public-fields) |
| 내부 및 사유 재산 세터 및 게터 지원 | ⚠️[지원되지 않음, 해결 해결](#internal-and-private-property-setters-and-getters) |
| `JsonConvert.PopulateObject` 메서드                   | ⚠️[지원되지 않음, 해결 해결](#populate-existing-objects) |
| `ObjectCreationHandling`전역 설정               | ⚠️[지원되지 않음, 해결 해결](#reuse-rather-than-replace-properties) |
| 세터 없이 컬렉션에 추가                    | ⚠️[지원되지 않음, 해결 해결](#add-to-collections-without-setters) |
| `PreserveReferencesHandling`전역 설정           | ❌[지원되지 않음](#preserve-object-references-and-handle-loops) |
| `ReferenceLoopHandling`전역 설정                | ❌[지원되지 않음](#preserve-object-references-and-handle-loops) |
| 특성 `System.Runtime.Serialization` 지원 | ❌[지원되지 않음](#systemruntimeserialization-attributes) |
| `MissingMemberHandling`전역 설정                | ❌[지원되지 않음](#missingmemberhandling) |
| 따옴표 없이 속성 이름 허용                   | ❌[지원되지 않음](#json-strings-property-names-and-string-values) |
| 문자열 값 주위에 단일 따옴표 허용              | ❌[지원되지 않음](#json-strings-property-names-and-string-values) |
| 문자열 속성에 대해 비문자열 JSON 값 허용    | ❌[지원되지 않음](#non-string-values-for-string-properties) |

이 기능은 전체 `Newtonsoft.Json` 기능 목록이 아닙니다. 목록에는 [GitHub 문제](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) 또는 [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) 게시물에서 요청된 많은 시나리오가 포함됩니다. 현재 샘플 코드가 없는 시나리오 중 하나에 대한 해결 방법을 구현하고 솔루션을 공유하려면 이 페이지의 [피드백 섹션에서](/dotnet/standard/serialization/system-text-json-migrate-from-newtonsoft-how-to#feedback) **이 페이지를** 선택합니다. 그러면 GitHub 문제가 생성되고 이 페이지 하단에 나열됩니다.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-newtonsoftjson"></a>뉴턴소프트.Json에 비해 기본 Json Serializer 동작의 차이

<xref:System.Text.Json>은 기본적으로 엄격하며 호출자 대신 추측이나 해석을 방지하여 결정적인 동작을 강조합니다. 라이브러리는 성능과 보안을 위해 이러한 방식으로 의도적으로 설계되었습니다. `Newtonsoft.Json`기본적으로 유연합니다. 이러한 기본적인 디자인 차이는 기본 동작의 다음과 같은 특정 차이점 뒤에 있습니다.

### <a name="case-insensitive-deserialization"></a>대/소문자 구분 역직렬화

역직렬화 `Newtonsoft.Json` 하는 동안 대/소문자를 구분 하지 않는 속성 이름은 기본적으로 일치 합니다. 기본값은 <xref:System.Text.Json> 대/소문자를 구분하는 것으로, 정확한 일치를 수행하기 때문에 더 나은 성능을 제공합니다. 대/소문자를 구분하지 않는 일치를 수행하는 방법에 대한 자세한 내용은 [대/소문자를 구분하지 않는 속성 일치를](system-text-json-how-to.md#case-insensitive-property-matching)참조하십시오.

ASP.NET Core를 `System.Text.Json` 사용하여 간접적으로 사용하는 `Newtonsoft.Json`경우. ASP.NET Core는 [camel-caseing 속성 이름과](system-text-json-how-to.md#use-camel-case-for-all-json-property-names) 대/소문자를 구분하지 않는 `System.Text.Json`일치에 대한 설정을 지정합니다.

### <a name="minimal-character-escaping"></a>최소한의 문자 이스케이프

직렬화 `Newtonsoft.Json` 하는 동안, 그들을 탈출 하지 않고 통해 문자를 시키는 것에 대 한 상대적으로 허용. 즉, 문자의 코드 포인트가 `\uxxxx` `xxxx` 있는 곳으로 대체하지 는 않습니다. 이스케이프를 수행하는 경우 문자 앞에 를 `\` 내보내서(예: `"` `\"`됨)을 방출합니다. <xref:System.Text.Json>XSS(교차 사이트 스크립팅) 또는 정보 공개 공격에 대한 심층 방어를 제공하기 위해 기본적으로 더 많은 문자를 이스케이프하고 6자 시퀀스를 사용하여 이를 수행합니다. `System.Text.Json`기본적으로 ASCII가 아닌 모든 문자를 이스케이프하므로 에서 사용하는 `StringEscapeHandling.EscapeNonAscii` 경우 아무 것도 `Newtonsoft.Json`수행할 필요가 없습니다. `System.Text.Json`또한 기본적으로 HTML에 민감한 문자를 이스케이프합니다. 기본 `System.Text.Json` 동작을 재정의하는 방법에 대한 자세한 내용은 [문자 인코딩 사용자 지정을](system-text-json-how-to.md#customize-character-encoding)참조하십시오.

### <a name="comments"></a>주석

직렬화 하는 `Newtonsoft.Json` 동안 JSON에서 주석을 기본적으로 무시 합니다. <xref:System.Text.Json> [기본값은 RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에 주석이 포함되어 있지 않으므로 주석에 대한 예외를 throw하는 것입니다. 주석을 허용하는 방법에 대한 자세한 내용은 [댓글 허용 및 후행 쉼표](system-text-json-how-to.md#allow-comments-and-trailing-commas)를 참조하십시오.

### <a name="trailing-commas"></a>후행 쉼표

역직렬화 `Newtonsoft.Json` 하는 동안 기본적으로 후행 쉼표를 무시 합니다. 또한 여러 후행 쉼표(예: `[{"Color":"Red"},{"Color":"Green"},,]`)를 무시합니다. <xref:System.Text.Json> [기본값은 RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 허용하지 않기 때문에 후행 쉼표에 대한 예외를 throw하는 것입니다. 수락하는 방법에 대한 자세한 내용은 [주석 허용 및 후행 쉼표](system-text-json-how-to.md#allow-comments-and-trailing-commas)를 참조하십시오. `System.Text.Json` 여러 후행 쉼표를 허용하는 방법은 없습니다.

### <a name="converter-registration-precedence"></a>변환기 등록 우선 순위

사용자 `Newtonsoft.Json` 지정 변환기의 등록 우선 순위는 다음과 같습니다.

* 속성에 대한 속성
* 형식에 대한 특성
* [변환기](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) 컬렉션

이 순서는 형식 수준에서 특성을 `Converters` 적용하여 등록된 변환기에서 컬렉션의 사용자 지정 변환기를 재정의한다는 것을 의미합니다. 이 두 등록은 속성 수준에서 특성에 의해 재정의됩니다.

사용자 <xref:System.Text.Json> 지정 변환기에 대한 등록 우선 순위는 다릅니다.

* 속성에 대한 속성
* <xref:System.Text.Json.JsonSerializerOptions.Converters>컬렉션
* 형식에 대한 특성

여기서 차이점은 `Converters` 컬렉션의 사용자 지정 변환기가 형식 수준에서 특성을 재정의한다는 것입니다. 이 우선 순위 의 뒤에 의도는 런타임 변경을 디자인-시간 선택 재정의하는 것입니다. 우선 순위를 변경할 수 있는 방법은 없습니다.

사용자 지정 변환기 등록에 대한 자세한 내용은 [사용자 지정 변환기 등록을](system-text-json-converters-how-to.md#register-a-custom-converter)참조하십시오.

### <a name="maximum-depth"></a>최대 깊이

`Newtonsoft.Json`기본적으로 최대 깊이 제한이 없습니다. 기본 <xref:System.Text.Json> 제한은 64이며 설정하여 <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>구성할 수 있습니다.

### <a name="json-strings-property-names-and-string-values"></a>JSON 문자열(속성 이름 및 문자열 값)

직렬화 하는 `Newtonsoft.Json` 동안 큰따옴표, 따옴표 또는 따옴표 없이 둘러싸인 속성 이름을 허용 합니다. 큰따옴따옴표 또는 따옴표로 둘러싸인 문자열 값을 허용합니다. 예를 들어 `Newtonsoft.Json` 다음 JSON을 수락합니다.

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json`해당 형식은 [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에 의해 필요하고 유효한 JSON으로 간주되는 유일한 형식이기 때문에 속성 이름과 문자열 값만 double 값으로 허용합니다.

단일 따옴표로 둘러싸인 값은 [JsonException과](xref:System.Text.Json.JsonException) 다음 메시지가 표시됩니다.

```
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>문자열 속성에 대한 비문자열 값

`Newtonsoft.Json`형식 문자열의 속성에 대한 serialization에 대해 `true` 숫자 `false`또는 리터럴 및 및 의 경우 비문자열 값을 허용합니다. 다음은 다음 클래스로 성공적으로 `Newtonsoft.Json` 직렬화하는 JSON의 예입니다.

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

`System.Text.Json`문자열이 아닌 값을 문자열 속성으로 디serialize하지 않습니다. 문자열 필드에 대해 수신된 비문자열 값은 [JsonException을](xref:System.Text.Json.JsonException) 다음과 같은 메시지와 함께 생성합니다.

```
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer-that-require-workarounds"></a>해결 방법을 필요로 하는 Json Serializer를 사용하는 시나리오

다음 시나리오는 기본 제공 기능에서 지원되지 않지만 해결 방법을 해결할 수 있습니다. 해결 방법을 사용하면 기능과 `Newtonsoft.Json` 완전한 패리티를 제공하지 못할 수 있는 사용자 지정 [변환기입니다.](system-text-json-converters-how-to.md) 이들 중 일부에 대 한 샘플 코드는 예제로 제공 됩니다. 이러한 `Newtonsoft.Json` 기능을 사용할 경우 .NET 개체 모델 또는 기타 코드 변경 사항을 수정해야 합니다.

### <a name="types-without-built-in-support"></a>기본 제공 지원이 없는 유형

<xref:System.Text.Json>다음 형식에 대 한 기본 제공 지원을 제공 하지 않습니다.

* <xref:System.Data.DataTable>및 관련 유형
* F# 형식(예: [구별된 공용 구조체,](../../fsharp/language-reference/discriminated-unions.md) [레코드 형식](../../fsharp/language-reference/records.md)및 [익명 레코드 유형)](../../fsharp/language-reference/anonymous-records.md)
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple>및 관련 제네릭 형식

기본 제공 지원이 없는 형식에 대해 사용자 지정 변환기를 구현할 수 있습니다.

### <a name="quoted-numbers"></a>인용된 숫자

`Newtonsoft.Json`JSON 문자열로 표시되는 숫자를 직렬화하거나 역직렬화할 수 있습니다(따옴표로 둘러싸인). 예를 `{"DegreesCelsius":"23"}` `{"DegreesCelsius":23}`들어, 다음을 대신 받아들일 수 있습니다. 에서 <xref:System.Text.Json>해당 동작을 활성화하려면 다음 예제와 같은 사용자 지정 변환기를 구현합니다. 변환기는 다음과 같이 `long`정의된 속성을 처리합니다.

* JSON 문자열로 직렬화합니다.
* 직렬화하는 동안 따옴표 내에서 JSON 번호와 숫자를 허용합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/LongToStringConverter.cs)]

개별 `long` 속성에 [특성을 사용하거나](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가하여](system-text-json-converters-how-to.md#registration-sample---converters-collection) 이 사용자 지정 변환기를 등록합니다.

### <a name="dictionary-with-non-string-key"></a>문자열이 아닌 키가 있는 사전

`Newtonsoft.Json`형식의 `Dictionary<TKey, TValue>`컬렉션을 지원합니다. 에서 사전 컬렉션에 대한 기본 <xref:System.Text.Json> 제공 `Dictionary<string, TValue>`지원은 로 제한됩니다. 즉, 키는 문자열이어야 합니다.

정수 또는 다른 형식을 키로 사용하여 사전을 지원하려면 [사용자 지정 변환기를 작성하는 방법의](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key)예제와 같은 변환기를 만듭니다.

### <a name="polymorphic-serialization"></a>다형성 직렬화

`Newtonsoft.Json`다형성 직렬화를 자동으로 수행합니다. 의 <xref:System.Text.Json>제한된 다형성 직렬화 기능에 대한 자세한 내용은 [파생 클래스의 Serialize 속성을](system-text-json-how-to.md#serialize-properties-of-derived-classes)참조하십시오.

설명된 해결 방법은 파생 클래스를 형식으로 `object`포함할 수 있는 속성을 정의하는 것입니다. 이것이 불가능한 경우 다른 옵션은 사용자 지정 변환기를 `Write` 작성하는 방법의 예제와 같은 전체 상속 형식 계층 구조에 대한 메서드를 사용하여 변환기를 만드는 [것입니다.](system-text-json-converters-how-to.md#support-polymorphic-deserialization)

### <a name="polymorphic-deserialization"></a>다형성 직렬화

`Newtonsoft.Json`을 `TypeNameHandling` 사용 하 고 일련화 하는 동안 JSON에 형식 이름 메타 데이터를 추가 하는 설정이 있습니다. 다형성 역직렬화를 수행 하도록 직렬화 하는 동안 메타 데이터를 사용 합니다. <xref:System.Text.Json>다형성 [직렬화의](system-text-json-how-to.md#serialize-properties-of-derived-classes) 제한된 범위를 수행할 수 있지만 다형성 역직렬화는 수행할 수 없습니다.

다형성 역직렬화를 지원하려면 사용자 지정 변환기를 작성하는 방법의 예제와 같은 [변환기를](system-text-json-converters-how-to.md#support-polymorphic-deserialization)만듭니다.

### <a name="deserialization-of-object-properties"></a>개체 속성의 역직렬화

을 `Newtonsoft.Json` 로 직렬화하면 <xref:System.Object>다음과 같은

* JSON `null`페이로드(제외)에서 기본 값의 유형을 유추하고 `string`저장된 , `long`또는 `double` `boolean`boxed `DateTime` 개체로 반환합니다. *기본 값은* JSON 번호, 문자열, `true`및 `false` `null`및 는 단일 JSON 값입니다.
* JSON `JObject` `JArray` 페이로드의 복잡한 값에 대해 또는 반환합니다. *복잡한 값은* 중괄호()`{}`내의 JSON 키-값 쌍의 컬렉션 또는`[]`괄호()의 값 목록입니다. 중괄호 또는 괄호 내의 속성 및 값에는 추가 속성 또는 값이 있을 수 있습니다.
* 페이로드에 JSON 리터럴이 `null` 있는 경우 null 참조를 반환합니다.

<xref:System.Text.Json>`JsonElement` 예를 들어 <xref:System.Object>.

* `object` 속성입니다.
* 사전 `object` 값입니다.
* `object` 배열 값입니다.
* 루트 `object`.

그러나 `System.Text.Json` `null` 페이로드에 JSON 리터럴이 있는 경우 null 참조를 동일하게 `Newtonsoft.Json` 처리하고 null 참조를 `null` 반환합니다.

속성에 대한 형식 `object` 추론을 구현하려면 사용자 지정 변환기를 작성하는 방법의 예제와 같은 [변환기를](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties)만듭니다.

### <a name="deserialize-null-to-non-nullable-type"></a>null을 null이 아닌 형식으로 디serialize

`Newtonsoft.Json`다음 시나리오에서는 예외를 throw하지 않습니다.

* `NullValueHandling`로 설정됩니다. `Ignore`
* 역직렬화 하는 동안 JSON null 값 형식에 대 한 null 값을 포함 합니다.

동일한 시나리오에서 <xref:System.Text.Json> 예외를 throw합니다. (해당 널 처리 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>설정은 .)

대상 형식을 소유하고 있는 경우 가장 좋은 해결 방법은 문제의 속성을 null(예: 변경)으로 `int` 만드는 것입니다. `int?`

또 다른 해결 방법은 형식에 대 한 null 값을 처리 하는 다음 `DateTimeOffset` 예제와 같이 형식에 대 한 변환기를 만드는 것입니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DateTimeOffsetNullHandlingConverter.cs)]

[속성에 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property) 하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection) 하 여이 사용자 지정 변환기를 등록 합니다.

**참고:** 앞의 변환기는 **기본값을 지정하는** POCO와 다르게 `Newtonsoft.Json` null 값을 처리합니다. 예를 들어 다음 코드가 대상 개체를 나타낸다고 가정합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

다음 JSON이 선행 변환기를 사용하여 역직렬화된다고 가정합니다.

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

역직렬화 후 `Date` 속성에는 1/1/0001 ()`default(DateTimeOffset)`즉 생성자에서 설정된 값이 덮어씁됩니다. 동일한 POCO와 JSON을 `Newtonsoft.Json` 감안할 때, 직렬화는 2001년 1월 1일 숙소에 남게 `Date` 됩니다.

### <a name="deserialize-to-immutable-classes-and-structs"></a>변경할 수 없는 클래스 및 구조체로 직렬화

`Newtonsoft.Json`매개 변수가 있는 생성자(생성자)를 사용할 수 있으므로 변경할 수 없는 클래스와 구조체로 직렬화할 수 있습니다. <xref:System.Text.Json>는 공용 매개 변수 없는 생성자만 지원합니다. 해결 방법으로 사용자 지정 변환기에서 매개 변수가 있는 생성자(생성자)를 호출할 수 있습니다.

다음은 여러 생성자 매개 변수가 있는 변경할 수 없는 구조체입니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePoint.cs#ImmutablePoint)]

그리고 이 구조체를 직렬화하고 직렬화하는 변환기는 다음과 같습니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ImmutablePointConverter.cs)]

컬렉션에 [변환기를 추가하여](system-text-json-converters-how-to.md#registration-sample---converters-collection) 이 사용자 <xref:System.Text.Json.JsonSerializerOptions.Converters> 지정 변환기를 등록합니다.

열려 있는 제네릭 속성을 처리하는 유사한 변환기의 예는 [키-값 쌍에 대한 기본 제공 변환기를](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs)참조하십시오.

### <a name="specify-constructor-to-use"></a>사용할 생성자 지정

이 `Newtonsoft.Json` `[JsonConstructor]` 특성을 사용하면 POCO에 역직렬화할 때 호출할 생성자를 지정할 수 있습니다. <xref:System.Text.Json>매개 변수 없는 생성자만 지원합니다. 해결 방법으로 사용자 지정 변환기에서 필요한 생성자 중 어떤 생성기를 호출할 수 있습니다. [불변클래스 및 구조체에 대한 Serialize의 예제를](#deserialize-to-immutable-classes-and-structs)참조하십시오.

### <a name="required-properties"></a>필수 속성

에서 `Newtonsoft.Json`속성에 설정 `Required` 하여 속성이 필요 `[JsonProperty]` 하 게 지정 합니다. `Newtonsoft.Json`필요에 따라 표시된 속성에 대해 JSON에서 값을 받지 않으면 예외를 throw합니다.

<xref:System.Text.Json>대상 형식의 속성 중 하나에 대해 값이 수신되지 않으면 예외를 throw하지 않습니다. 예를 들어 클래스가 `WeatherForecast` 있는 경우:

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

다음 JSON은 오류 없이 역직렬화됩니다.

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

JSON에 속성이 없는 `Date` 경우 역직렬화가 실패하도록 하려면 사용자 지정 변환기를 구현합니다. 다음 샘플 변환기 코드는 역직화가 완료된 후 속성이 `Date` 설정되지 않은 경우 예외를 throw합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRequiredPropertyConverter.cs)]

[POCO 클래스의 특성을 사용하거나](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가하여](system-text-json-converters-how-to.md#registration-sample---converters-collection) 이 사용자 지정 변환기를 등록합니다.

이 패턴을 따르는 경우 재귀 호출 또는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> <xref:System.Text.Json.JsonSerializer.Deserialize%2A>을 호출할 때 옵션 개체를 전달하지 마십시오. 옵션 개체에는 <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> 컬렉션이 포함되어 있습니다. 사용자 지정 변환기 `Serialize` `Deserialize`호출을 또는 에 전달하는 경우 스택 오버플로 예외를 초래하는 무한 루프를 만듭니다. 기본 옵션이 불가능한 경우 필요한 설정을 사용하여 옵션의 새 인스턴스를 만듭니다. 이 방법은 각 새 인스턴스가 독립적으로 캐시되므로 속도가 느려집니다.

위의 변환기 코드는 간단한 예입니다. 특성(예: [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 또는 다른 옵션(예: 사용자 지정 인코더)을 처리해야 하는 경우 추가 논리가 필요합니다. 또한 예제 코드는 생성자에서 기본값이 설정된 속성을 처리하지 않습니다. 이 방법은 다음 시나리오를 구분하지 않습니다.

* JSON에서 속성이 없습니다.
* Null이 아닌 형식에 대한 속성은 JSON에 있지만 값은 `int`에 대해 0과 같은 형식의 기본값입니다.
* nullable 값 형식에 대 한 속성JSON에 있지만 값은 null입니다.

### <a name="conditionally-ignore-a-property"></a>조건부 로 속성 무시

`Newtonsoft.Json`직렬화 또는 직렬화에 대한 속성을 조건부로 무시하는 방법에는 여러 가지가 있습니다.

* `DefaultContractResolver`을 사용하면 임의의 기준에 따라 포함하거나 제외할 속성을 선택할 수 있습니다.
* `NullValueHandling` 및 `DefaultValueHandling` 설정에서 `JsonSerializerSettings` 모든 null-값 또는 기본값 속성을 무시 하도록 지정합니다.
* `NullValueHandling` 속성의 `DefaultValueHandling` `[JsonProperty]` 및 설정을 사용하면 null 또는 기본값으로 설정할 때 무시해야 하는 개별 속성을 지정할 수 있습니다.

<xref:System.Text.Json>직렬화하는 동안 속성을 생략하는 다음 방법을 제공합니다.

* 속성의 [[JsonIgnore]](system-text-json-how-to.md#exclude-individual-properties) 특성으로 인해 직렬화 하는 동안 JSON에서 속성을 생략 합니다.
* [IgnoreNullValues](system-text-json-how-to.md#exclude-all-null-value-properties) 전역 옵션을 사용하면 모든 null 값 속성을 제외할 수 있습니다.
* [IgnoreReadOnlyProperties](system-text-json-how-to.md#exclude-all-read-only-properties) 전역 옵션을 사용하면 모든 읽기 전용 속성을 제외할 수 있습니다.

이러한 옵션을 사용하면 다음을 수행할 수 **없습니다.**

* 형식의 기본값이 있는 모든 속성을 무시합니다.
* 형식의 기본값이 있는 선택한 속성을 무시합니다.
* 값이 null인 경우 선택한 속성을 무시합니다.
* 런타임에 평가된 임의의 기준에 따라 선택한 속성을 무시합니다.

이 기능에 대해 사용자 지정 변환기를 작성할 수 있습니다. 다음은 이 방법을 보여 주는 샘플 POCO 및 사용자 지정 변환기입니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastRuntimeIgnoreConverter.cs)]

변환기는 해당 `Summary` 값이 null, 빈 문자열 또는 "N/A"인 경우 직렬화에서 속성을 생략합니다.

[클래스에 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) 하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection) 하 여이 사용자 지정 변환기를 등록 합니다.

이 접근 방식에는 다음과 같은 경우 추가 논리가 필요합니다.

* POCO에는 복잡한 속성이 포함됩니다.
* 사용자 지정 인코더와 `[JsonIgnore]` 같은 옵션 과 같은 특성을 처리해야 합니다.

### <a name="specify-date-format"></a>날짜 형식 지정

`Newtonsoft.Json`여러 가지 방법으로 형식 `DateTime` 및 `DateTimeOffset` 형식의 속성이 직렬화되고 역직렬화되는 방법을 제어할 수 있습니다.

* 이 `DateTimeZoneHandling` 설정을 사용하여 모든 `DateTime` 값을 UTC 날짜로 직렬화할 수 있습니다.
* `DateFormatString` 설정 및 `DateTime` 변환기를 사용하여 날짜 문자열의 형식을 사용자 지정할 수 있습니다.

에서, <xref:System.Text.Json>내장 된 지원이있는 유일한 형식은 ISO 8601-1 : 2019 널리 채택되고 모호하지 않으며 정확하게 왕복합니다. 다른 형식을 사용하려면 사용자 지정 변환기를 만듭니다. 자세한 내용은 [System.Text.Json 에서 DateTime 및 DateTimeOffset 지원을](../datetime/system-text-json-support.md)참조하십시오.

### <a name="callbacks"></a>콜백

`Newtonsoft.Json`직렬화 또는 직렬화 프로세스의 여러 지점에서 사용자 지정 코드를 실행할 수 있습니다.

* 온디직부시즈(개체 역직렬화를 시작할 때)
* 온디직렬화(개체 역직렬화가 완료된 경우)
* 온 직렬화(개체 직렬화를 시작할 때)
* 온직렬화(개체 직렬화 완료 시)

에서 <xref:System.Text.Json>사용자 지정 변환기를 작성하여 콜백을 시뮬레이션할 수 있습니다. 다음 예제에서는 POCO에 대 한 사용자 지정 변환기를 보여 주다. 변환기는 `Newtonsoft.Json` 콜백에 해당하는 각 지점에서 메시지를 표시하는 코드를 포함합니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecastCallbacksConverter.cs)]

[클래스에 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type) 하거나 <xref:[!OP.NO-LOC(System.Text.Json)].JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection) 하 여이 사용자 지정 변환기를 등록 합니다.

위의 샘플 다음에 오는 사용자 지정 변환기를 사용하는 경우:

* 코드는 `OnDeserializing` 새 POCO 인스턴스에 액세스할 수 없습니다. 직렬화의 시작 시 새 POCO 인스턴스를 조작하려면 해당 코드를 POCO 생성자에 넣습니다.
* 재귀 호출 또는 `Serialize` `Deserialize`에서 를 호출할 때 옵션 개체를 전달하지 마십시오. 옵션 개체에는 `Converters` 컬렉션이 포함되어 있습니다. `Serialize` 또는 `Deserialize`에 전달하는 경우 변환기가 사용되어 스택 오버플로 예외가 발생하는 무한 루프가 생성됩니다.

### <a name="public-and-non-public-fields"></a>공공 및 비공개 필드

`Newtonsoft.Json`속성뿐만 아니라 필드를 직렬화하고 역직해제할 수 있습니다. <xref:System.Text.Json>공용 속성에서만 작동합니다. 사용자 지정 변환기는 이 기능을 제공할 수 있습니다.

### <a name="internal-and-private-property-setters-and-getters"></a>내부 및 개인 재산 세터 및 게터

`Newtonsoft.Json``JsonProperty` 속성을 통해 개인 및 내부 속성 세터 및 게터를 사용할 수 있습니다. <xref:System.Text.Json>공용 세터만 지원합니다. 사용자 지정 변환기는 이 기능을 제공할 수 있습니다.

### <a name="populate-existing-objects"></a>기존 개체 채우기

메서드는 `JsonConvert.PopulateObject` `Newtonsoft.Json` JSON 문서를 새 인스턴스를 만드는 대신 클래스의 기존 인스턴스로 직렬화합니다. <xref:System.Text.Json>항상 기본 public 매개 변수 없는 생성자 사용 하 여 대상 형식의 새 인스턴스를 만듭니다. 사용자 지정 변환기는 기존 인스턴스로 역직렬화할 수 있습니다.

### <a name="reuse-rather-than-replace-properties"></a>속성을 바꾸기 대신 재사용

이 `Newtonsoft.Json` `ObjectCreationHandling` 설정을 사용하면 역직렬화 중에 대체하지 않고 속성의 개체를 다시 사용할 수 있도록 지정할 수 있습니다. <xref:System.Text.Json>항상 속성의 개체를 바꿉습니다.  사용자 지정 변환기는 이 기능을 제공할 수 있습니다.

### <a name="add-to-collections-without-setters"></a>세터 없이 컬렉션에 추가

역직렬화 `Newtonsoft.Json` 하는 동안 속성에 setter가 없는 경우에 컬렉션에 개체를 추가 합니다. <xref:System.Text.Json>은 setter가 없는 속성을 무시합니다. 사용자 지정 변환기는 이 기능을 제공할 수 있습니다.

## <a name="scenarios-that-jsonserializer-currently-doesnt-support"></a>Json Serializer가 현재 지원하지 않는 시나리오

다음 시나리오의 경우 해결 방법을 사용할 수 없거나 불가능합니다. 이러한 `Newtonsoft.Json` 기능을 사용하면 크게 변경하지 않으면 마이그레이션이 불가능합니다.

### <a name="preserve-object-references-and-handle-loops"></a>개체 참조 및 핸들 루프 보존

기본적으로 값별로 `Newtonsoft.Json` 직렬화됩니다. 예를 들어 개체에 동일한 `Person` 개체에 대한 참조가 포함된 두 개의 `Person` 속성이 포함된 경우 해당 개체의 속성 값이 JSON에서 중복됩니다.

`Newtonsoft.Json`참조로 `PreserveReferencesHandling` 직렬화할 수 `JsonSerializerSettings` 있는 설정이 있습니다.

* 식별자 메타데이터가 첫 번째 `Person` 개체에 대해 생성된 JSON에 추가됩니다.
* 두 번째 `Person` 개체에 대해 만들어진 JSON에는 속성 값 대신 해당 식별자에 대한 참조가 포함됩니다.

`Newtonsoft.Json`또한 예외를 throw하는 대신 순환 참조를 `ReferenceLoopHandling` 무시할 수 있는 설정도 있습니다.

<xref:System.Text.Json>값별로 직렬화를 지원하고 순환 참조에 대한 예외를 throw합니다.

### <a name="systemruntimeserialization-attributes"></a>시스템.런타임.직렬화 특성

<xref:System.Text.Json>와 같은 네임스페이스의 `System.Runtime.Serialization` 특성은 지원하지 않습니다. `IgnoreDataMemberAttribute` `DataMemberAttribute`

### <a name="octal-numbers"></a>옥탈 번호

`Newtonsoft.Json`숫자를 선행 0으로 팔각형 숫자로 처리합니다. <xref:System.Text.Json>[RFC 8259](https://tools.ietf.org/html/rfc8259) 사양은 이를 허용하지 않으므로 선행 영점 허용이 없습니다.

### <a name="missingmemberhandling"></a>누락된 회원 취급

`Newtonsoft.Json`JSON대상 유형에 누락된 속성을 포함하는 경우 역직렬화 중에 예외를 throw하도록 구성할 수 있습니다. <xref:System.Text.Json>[[JsonExtensionData] 특성을](system-text-json-how-to.md#handle-overflow-json)사용하는 경우를 제외하고 JSON에서 추가 속성을 무시합니다. 누락된 멤버 기능에 대한 해결 방법이 없습니다.

### <a name="tracewriter"></a>트레이스라이터

`Newtonsoft.Json`을 사용하여 `TraceWriter` 직렬화 또는 역직렬화로 생성된 로그를 볼 수 있습니다. <xref:System.Text.Json>로깅을 수행하지 않습니다.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument 및 JsonElementJToken에 비해 (예 : JObject, JArray)

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>은 기존 JSON 페이로드에서 **읽기 전용** 문서 개체 모델(DOM)을 구문 분석하고 빌드하는 기능을 제공합니다. DOM은 JSON 페이로드의 데이터에 대한 임의 액세스를 제공합니다. 페이로드를 구성하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다. 이 `JsonElement` 형식은 JSON 텍스트를 일반적인 .NET 유형으로 변환하는 API를 제공합니다. `JsonDocument`속성을 노출합니다. <xref:System.Text.Json.JsonDocument.RootElement>

### <a name="jsondocument-is-idisposable"></a>JsonDocument는 I일회용입니다.

`JsonDocument`는 풀링된 버퍼에 데이터의 메모리 내 보기를 빌드합니다. 따라서 `JObject` 형식은 `JArray` `Newtonsoft.Json` `JsonDocument` 사용 블록 내에서 `IDisposable` 사용되어야 합니다.

평생 소유권을 이전하고 호출자에게 책임을 폐기하려는 경우에만 API에서 a를 `JsonDocument` 반환합니다. 대부분의 시나리오에서는 필요하지 않습니다. 호출자는 전체 JSON 문서로 작업해야 하는 <xref:System.Text.Json.JsonElement.Clone%2A> 경우 <xref:System.Text.Json.JsonDocument.RootElement%2A>을 <xref:System.Text.Json.JsonElement>반환합니다. 호출자는 JSON 문서 내의 특정 요소로 작업해야 <xref:System.Text.Json.JsonElement.Clone%2A> 하는 <xref:System.Text.Json.JsonElement>경우 을 반환합니다. 을 `RootElement` 만들지 `Clone`않고 또는 하위 요소를 직접 반환하는 경우 호출자는 `JsonElement` `JsonDocument` 해당 요소가 삭제된 후 반환된 정보에 액세스할 수 없습니다.

다음은 다음을 수행해야 하는 예제입니다. `Clone`

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

앞의 코드는 속성을 `JsonElement` 포함하는 `fileName` a를 기대합니다. JSON 파일을 열고 `JsonDocument`을 만듭니다. 메서드는 호출자는 전체 문서로 작업하려고 한다고 가정하므로 `Clone` 을 `RootElement`반환합니다.

하위 요소를 `JsonElement` 받고 하위 요소를 반환하는 경우 하위 요소 중 `Clone` a를 반환할 필요가 없습니다. 호출자는 전달된 사람이 `JsonDocument` `JsonElement` 속한 것을 계속 유지할 책임이 있습니다. 예를 들어:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument는 읽기 전용입니다.

DOM은 <xref:System.Text.Json> JSON 요소를 추가, 제거 또는 수정할 수 없습니다. 이러한 방식으로 성능과 일반적인 JSON 페이로드 크기(즉, < 1MB)를 구문 분석하기 위한 할당을 줄이도록 설계되었습니다. 시나리오에서 현재 수정 가능한 DOM을 사용하는 경우 다음 해결 방법 중 하나가 가능할 수 있습니다.

* 처음부터 `JsonDocument` 빌드하려면(즉, 기존 JSON 페이로드를 `Parse` 메서드에 전달하지 않고) JSON 텍스트를 `Utf8JsonWriter` 사용하여 출력을 구문 분석하여 `JsonDocument`새 .
* 기존 `JsonDocument`을 수정하려면 JSON 텍스트를 작성하고, 작성하는 동안 변경하고, 출력을 구문 분석하여 `JsonDocument`새 .
* 기존 JSON 문서를 병합하려면 `JObject.Merge` 또는 `JContainer.Merge` `Newtonsoft.Json`API와 동일하므로 [이 GitHub 문제를](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853)참조하십시오.

### <a name="jsonelement-is-a-union-struct"></a>JsonElement는 공용 구조체입니다.

`JsonDocument`는 `RootElement` JSON 요소를 포괄하는 공용 구조체 형식인 형식의 <xref:System.Text.Json.JsonElement>속성으로 노출합니다. `Newtonsoft.Json`는 " `JObject``JArray` `JToken`및 등과 같은 전용 계층 적 형식을 사용합니다. `JsonElement`검색하고 열거할 수 있으며 JSON 요소를 `JsonElement` .NET 유형으로 구체화하는 데 사용할 수 있습니다.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>하위 요소에 대한 JsonDocument 및 JsonElement를 검색하는 방법

일부 사전에서 조회하기 `JObject` 때문에 `JArray` `Newtonsoft.Json` JSON 토큰을 사용하거나 검색하는 것이 상대적으로 빠르다. 비교하여, 에 `JsonElement` 검색 속성의 순차적 인 검색이 필요하므로 상대적으로 `TryGetProperty`느립니다 (예를 들어 사용하는 경우). <xref:System.Text.Json>는 조회 시간이 아닌 초기 구문 분석 시간을 최소화하도록 설계되었습니다. 따라서 `JsonDocument` 개체를 검색할 때 성능을 최적화하려면 다음 방법을 사용합니다.

* 고유한 인덱싱 또는 루프를<xref:System.Text.Json.JsonElement.EnumerateArray%2A> <xref:System.Text.Json.JsonElement.EnumerateObject%2A>수행하는 대신 기본 제공 열거형(및) 을 사용합니다.
* 을 사용하여 `RootElement`모든 속성을 통해 `JsonDocument` 전체에서 순차적 검색을 수행하지 마십시오. 대신 JSON 데이터의 알려진 구조를 기반으로 중첩된 JSON 개체를 검색합니다. `Grade` 예를 들어 개체에서 `Student` 속성을 찾는 경우 `Student` `Grade` `JsonElement` `Grade` 속성을 찾는 모든 개체를 검색하는 대신 개체를 반복하고 각 개체에 대한 값을 가져옵니다. 후자를 수행하면 동일한 데이터를 통해 불필요한 전달이 발생합니다.

코드 예제에서는 [JsonDocument 를 사용하여 데이터에 액세스할 수 있습니다.](system-text-json-how-to.md#use-jsondocument-for-access-to-data)

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>JsonText리더와 비교한 Utf8Json리더

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>는 UTF-8 인코딩 된 JSON 텍스트에 대한 고성능, 낮은 할당, 정방향 전용 판독기, [ReadOnlySpan\<바이트>](xref:System.ReadOnlySpan%601) 또는 [\<ReadOnlySequence 바이트>](xref:System.Buffers.ReadOnlySequence%601)읽습니다. 는 `Utf8JsonReader` 사용자 지정 구문 분석기 및 역직렬화기를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.

다음 섹션에서는 을 사용하는 `Utf8JsonReader`데 권장되는 프로그래밍 패턴을 설명합니다.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader는 심판 구조체입니다.

형식은 `Utf8JsonReader` 참조 *구조체이므로*특정 제한 [사항이 있습니다.](../../csharp/language-reference/keywords/ref.md#ref-struct-types) 예를 들어 ref 구조체 이외의 클래스 또는 구조체에 필드로 저장할 수 없습니다. 높은 성능을 얻으려면 이 형식은 `ref struct` [readOnlySpan\<바이트>](xref:System.ReadOnlySpan%601)입력을 캐시해야 하므로 이 유형이 어야 합니다. 또한 이 형식은 상태를 유지하므로 변경할 수 있습니다. 따라서 **값보다는 참조로 전달합니다.** 값으로 전달하면 구조복사본이 생성되고 상태 변경 내용이 호출자에게 표시되지 않습니다. 이는 클래스이기 `Newtonsoft.Json` 때문에 `Newtonsoft.Json` `JsonTextReader` 다릅니다. 참조 구조체를 사용하는 방법에 대한 자세한 내용은 [안전하고 효율적인 C# 코드 작성을](../../csharp/write-safe-efficient-code.md)참조하십시오.

### <a name="read-utf-8-text"></a>UTF-8 텍스트 읽기

`Utf8JsonReader`을 사용하는 동안 최상의 성능을 얻으려면 UTF-16 문자열이 아닌 UTF-8 텍스트로 이미 인코딩된 JSON 페이로드를 읽어보십시오. 코드 예제는 [Utf8JsonReader를 사용하여 데이터 필터를](system-text-json-how-to.md#filter-data-using-utf8jsonreader)참조하십시오.

### <a name="read-with-a-stream-or-pipereader"></a>스트림 또는 파이프리더로 읽기

이 `Utf8JsonReader` 지원은 UTF-8 인코딩된 [ReadOnlySpan\<바이트>](xref:System.ReadOnlySpan%601) 또는 [\<ReadOnlySequence 바이트>](xref:System.Buffers.ReadOnlySequence%601) 읽기(에서 읽은 결과)에서 읽기를 <xref:System.IO.Pipelines.PipeReader>지원합니다.

동기 읽기의 경우 스트림이 끝날 때까지 JSON 페이로드를 바이트 배열로 읽고 판독기로 전달할 수 있습니다. 문자열(UTF-16으로 인코딩됨)에서 읽으시면 <xref:System.Text.Encoding.UTF8>을 참조하십시오.<xref:System.Text.Encoding.GetBytes%2A> 을 사용하여 문자열을 UTF-8 인코딩된 바이트 배열로 트랜스코딩합니다. 그런 다음 `Utf8JsonReader`에 전달합니다.

입력을 `Utf8JsonReader` JSON 텍스트로 간주하므로 UTF-8 바이트 순서 표시(BOM)는 잘못된 JSON으로 간주됩니다. 호출자는 데이터를 판독기에 전달하기 전에 필터링해야 합니다.

코드 예제의 경우 [Utf8JsonReader 사용을](system-text-json-how-to.md#use-utf8jsonreader)참조하십시오.

### <a name="read-with-multi-segment-readonlysequence"></a>다중 세그먼트 ReadOnly시퀀스를 사용하여 읽기

JSON 입력이 [ReadOnlySpan\<바이트>](xref:System.ReadOnlySpan%601)경우 읽기 루프를 `ValueSpan` 통과할 때 각 JSON 요소는 판독기의 속성에서 액세스할 수 있습니다. 그러나 입력이 [ReadOnlySequence\<바이트](xref:System.Buffers.ReadOnlySequence%601)>(a에서 <xref:System.IO.Pipelines.PipeReader>읽은 결과)인 경우 일부 JSON 요소는 `ReadOnlySequence<byte>` 개체의 여러 세그먼트를 가로질러 갈 수 있습니다. 이러한 요소는 연속 메모리 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> 블록에서 액세스할 수 없습니다. 대신 다중 세그먼트를 `ReadOnlySequence<byte>` 입력으로 사용할 때마다 <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> 판독기에서 속성을 폴링하여 현재 JSON 요소에 액세스하는 방법을 알아내도록 합니다. 권장되는 패턴은 다음과 같습니다.

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

### <a name="use-valuetextequals-for-property-name-lookups"></a>속성 이름 조회에 값텍스트같음 사용

속성 이름 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A> 조회를 호출하여 <xref:System.MemoryExtensions.SequenceEqual%2A> 바이트별 비교를 수행하는 데 사용하지 마십시오. 대신 <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A> 호출, 때문에 그 메서드는 JSON에서 이스케이프 되는 모든 문자를 이스케이프 해제 합니다. 다음은 "name"이라는 이름의 속성을 검색하는 방법을 보여 주는 예제입니다.

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetDefineUtf8Var)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/ValueTextEqualsExample.cs?name=SnippetUseUtf8Var&highlight=11)]

### <a name="read-null-values-into-nullable-value-types"></a>null 값을 null 값 유형으로 읽습니다.

`Newtonsoft.Json`을 <xref:System.Nullable%601>반환하여 `Null` `TokenType` `bool?`을 처리하는 `ReadAsBoolean`API를 제공합니다. 기본 제공 `System.Text.Json` API는 null이 아닌 값 형식만 반환합니다. 예를 들어 <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType> 을 `bool`반환합니다. JSON에서 발견하면 `Null` 예외를 throw합니다. 다음 예제에서는 null을 처리하는 두 가지 방법을 보여 주며, 하나는 nullable 값 형식을 반환하고 다른 방법은 기본값을 반환합니다.

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

특정 대상 프레임워크에 `Newtonsoft.Json` 계속 사용해야 하는 경우 다중 대상을 지정하고 두 가지 구현을 가질 수 있습니다. 그러나 이것은 사소한 것이 아니며 일부 `#ifdefs` 및 소스 중복이 필요합니다. 가능한 한 많은 코드를 공유하는 한 가지 `ref struct` 방법은 `Utf8JsonReader` 주위에 `Newtonsoft.Json` `JsonTextReader`래퍼를 만들고 . 이 래퍼는 행동 차이를 격리하면서 공용 표면적을 통합합니다. 이렇게 하면 변경 내용을 주로 형식의 구성에 격리하고 새 형식을 참조로 전달할 수 있습니다. 다음은 [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 라이브러리가 따르는 패턴입니다.

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>JsonText 라이터에 비해 Utf8Json작가

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>는 다음과 같은 `String`일반적인 .NET 형식에서 UTF-8 인코딩 된 JSON 텍스트를 작성하는 고성능 `Int32`방법입니다. `DateTime` 기록기는 사용자 지정 serializer를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.

다음 섹션에서는 을 사용하는 `Utf8JsonWriter`데 권장되는 프로그래밍 패턴을 설명합니다.

### <a name="write-with-utf-8-text"></a>UTF-8 텍스트로 쓰기

`Utf8JsonWriter`을 사용하는 동안 최상의 성능을 얻으려면 UTF-16 문자열이 아닌 UTF-8 텍스트로 이미 인코딩된 JSON 페이로드를 작성합니다. UTF-16 문자열 리터럴을 사용하는 대신 알려진 문자열 속성 이름과 값을 고정값으로 캐시하고 미리 인코딩하고 작성기에 전달하는 데 사용합니다. <xref:System.Text.Json.JsonEncodedText> 이는 UTF-8 바이트 배열을 캐싱하고 사용하는 것보다 빠릅니다.

이 방법은 사용자 지정 이스케이프를 수행해야 하는 경우에도 작동합니다. `System.Text.Json`문자열을 작성하는 동안 이스케이프를 사용하지 않도록 설정하지 않습니다. 그러나 사용자 고유의 사용자 <xref:System.Text.Encodings.Web.JavaScriptEncoder> 지정을 작성기에 옵션으로 전달하거나 `JsonEncodedText` 이스케이프를 수행하는 데 사용하는 `JavascriptEncoder` 사용자 `JsonEncodedText` 고유의 사용자 지정을 만든 다음 문자열 대신 을 작성할 수 있습니다. 자세한 내용은 [문자 인코딩 사용자 지정을](system-text-json-how-to.md#customize-character-encoding)참조하십시오.

### <a name="write-raw-values"></a>원시 값 쓰기

메서드는 `Newtonsoft.Json` `WriteRawValue` 값이 예상되는 원시 JSON을 씁니다. <xref:System.Text.Json>직접적인 등가물은 없지만 유효한 JSON만 작성되도록 하는 해결 방법은 다음과 같습니다.

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>캐릭터 이스케이프 사용자 지정

[StringEscape처리](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) 설정은 `JsonTextWriter` ASCII가 아닌 모든 문자 **또는** HTML 문자를 이스케이프할 수 있는 옵션을 제공합니다. 기본적으로 ASCII가 아닌 모든 `Utf8JsonWriter` **문자와** HTML 문자를 이스케이프합니다. 이 이스케이프는 심층적인 보안상의 이유로 수행됩니다. 다른 이스케이프 정책을 지정하려면 <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>를 만들고 설정합니다. <xref:System.Text.Encodings.Web.JavaScriptEncoder> 자세한 내용은 [문자 인코딩 사용자 지정을](system-text-json-how-to.md#customize-character-encoding)참조하십시오.

### <a name="customize-json-format"></a>JSON 형식 사용자 지정

`JsonTextWriter`다음과 같은 설정이 `Utf8JsonWriter` 포함되어 있습니다.

* [들여쓰기](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - 들여쓰기할 문자 수를 지정합니다. `Utf8JsonWriter`항상 2자 들여쓰기를 수행합니다.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - 들여쓰기에 사용할 문자를 지정합니다.  `Utf8JsonWriter`항상 공백을 사용합니다.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - 문자열 값을 둘러싸는 데 사용할 문자를 지정합니다.  `Utf8JsonWriter`항상 큰따옴표를 사용합니다.
* [QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - 따옴표로 속성 이름을 둘러싸는지 여부를 지정합니다.  `Utf8JsonWriter`항상 따옴표로 그들을 둘러싸고.

이러한 방법으로 생성된 JSON을 사용자 지정할 수 `Utf8JsonWriter` 있는 해결 방법은 없습니다.

### <a name="write-null-values"></a>null 값 쓰기

을 사용하여 `Utf8JsonWriter`null 값을 작성하려면 다음을 호출합니다.

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A>을 사용하여 null을 값으로 사용하여 키-값 쌍을 작성합니다.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A>을 사용하여 null을 JSON 배열의 요소로 작성합니다.

string 속성의 경우 문자열이 <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> null이고 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A> 와 `WriteNull` 동일합니다. `WriteNullValue`

### <a name="write-timespan-uri-or-char-values"></a>쓰기 시간 범위, Uri 또는 문자 값

`JsonTextWriter`는 `WriteValue` [TimeSpan,](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm) [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm)및 [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) 값에 대한 메서드를 제공합니다. `Utf8JsonWriter`동등한 메서드가 없습니다. 대신 이러한 값을 문자열(예: `ToString()`호출)으로 서식을 지정하고 을 호출합니다. <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>

### <a name="multi-targeting"></a>멀티 타기팅

특정 대상 프레임워크에 `Newtonsoft.Json` 계속 사용해야 하는 경우 다중 대상을 지정하고 두 가지 구현을 가질 수 있습니다. 그러나 이것은 사소한 것이 아니며 일부 `#ifdefs` 및 소스 중복이 필요합니다. 가능한 한 많은 코드를 공유하는 한 가지 방법은 `Utf8JsonWriter` 주위에 `Newtonsoft` `JsonTextWriter`래퍼를 만들고 . 이 래퍼는 행동 차이를 격리하면서 공용 표면적을 통합합니다. 이렇게 하면 주로 형식의 구성에 변경 내용을 격리할 수 있습니다. [Microsoft.Extensions.종속성 모델](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 라이브러리는 다음과 같습니다.

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>추가 리소스

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [System.Text.Json개요](system-text-json-overview.md)
* [사용 방법System.Text.Json](system-text-json-how-to.md)
* [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md)
* [날짜 시간 및 날짜 시간 오프셋 지원에서System.Text.Json](../datetime/system-text-json-support.md)
* [System.Text.JsonAPI 참조](xref:System.Text.Json)
* [System.Text.Json. 직렬화 API 참조](xref:System.Text.Json.Serialization)
