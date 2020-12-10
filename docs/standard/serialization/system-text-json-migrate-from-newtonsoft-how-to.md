---
title: Newtonsoft.Json에서 System.Text.Json으로 마이그레이션 - .NET
description: Newtonsoft.Json에서 System.Text.Json으로 마이그레이션하는 방법을 알아봅니다. 샘플 코드가 포함되어 있습니다.
author: tdykstra
ms.author: tdykstra
no-loc:
- System.Text.Json
- Newtonsoft.Json
ms.date: 11/30/2020
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: bc256c5129cd4a7306e632685474b159a43ce76c
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96438058"
---
# <a name="how-to-migrate-from-no-locnewtonsoftjson-to-no-locsystemtextjson"></a>Newtonsoft.Json에서 System.Text.Json로 마이그레이션하는 방법

이 문서에서는 [Newtonsoft.Json](https://www.newtonsoft.com/json)에서 <xref:System.Text.Json>로 마이그레이션하는 방법을 보여줍니다.

`System.Text.Json` 네임스페이스는 JSON(JavaScript Object Notation)에서 직렬화 및 역직렬화하는 기능을 제공합니다. `System.Text.Json` 라이브러리는 [.NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1) 이상 버전의 런타임에 포함되어 있습니다. 다른 대상 프레임워크의 경우 [System.Text.Json](https://www.nuget.org/packages/System.Text.Json) NuGet 패키지를 설치합니다. 패키지는 다음을 지원합니다.

* .NET Standard 2.0 이상 버전
* .NET Framework 4.7.2 이상 버전
* .NET Core 2.0, 2.1, 2.2

`System.Text.Json`은 성능, 보안 및 표준 규정 준수에 중점을 둡니다. 기본 동작에서 몇 가지 큰 차이가 있으며 `Newtonsoft.Json`과의 기능 패리티를 목표로 하지 않습니다. 일부 시나리오에서는 `System.Text.Json`에 기본 기능이 없지만, 권장 해결 방법이 있습니다. 그 외의 시나리오에서는 해결 방법이 실용적이지 않습니다. 애플리케이션에서 사용하는 기능이 없는 경우 [이슈를 제출](https://github.com/dotnet/runtime/issues/new)하여 해당 시나리오에 대한 지원을 추가할 수 있는지 알아보세요.

이 문서의 대부분은 <xref:System.Text.Json.JsonSerializer> API 사용 방법에 대한 내용이지만, <xref:System.Text.Json.JsonDocument>(DOM(문서 개체 모델)을 나타냄), <xref:System.Text.Json.Utf8JsonReader> 및 <xref:System.Text.Json.Utf8JsonWriter> 형식을 사용하는 방법에 대한 지침도 포함되어 있습니다.

## <a name="table-of-differences-between-no-locnewtonsoftjson-and-no-locsystemtextjson"></a>Newtonsoft.Json와 System.Text.Json 간의 차이점 표

다음 표에는 `Newtonsoft.Json` 기능과 그에 상응하는 `System.Text.Json` 기능이 나열되어 있습니다. 상응하는 기능은 다음 범주로 분류됩니다.

* 기본 제공 기능에서 지원됩니다. `System.Text.Json`에서 유사한 동작을 가져오려면 특성 또는 글로벌 옵션을 사용해야 할 수도 있습니다.
* 지원되지 않으며, 해결이 가능합니다. 해결 방법은 [사용자 지정 변환기](system-text-json-converters-how-to.md)이며, 사용자 지정 변환기는 `Newtonsoft.Json` 기능과의 완전한 패리티를 제공하지 않을 수 있습니다. 그 중 일부는 샘플 코드가 예제로 제공됩니다. 이러한 `Newtonsoft.Json` 기능을 사용하는 경우 마이그레이션을 수행하려면 .NET 개체 모델 또는 기타 코드 변경 내용을 수정해야 합니다.
* 지원되지 않으며, 해결 방법이 실용적이지 않거나 가능하지 않습니다. 이러한 `Newtonsoft.Json` 기능을 사용하는 경우 중요한 변경 없이는 마이그레이션을 수행할 수 없습니다.

::: zone pivot="dotnet-5-0"
| Newtonsoft.Json 기능                               | System.Text.Json 해당 항목 |
|-------------------------------------------------------|-----------------------------|
| 기본적으로 대/소문자를 구분하지 않는 역직렬화           | ✔️ [PropertyNameCaseInsensitive 글로벌 설정](#case-insensitive-deserialization) |
| 카멜식 대/소문자 속성 이름                             | ✔️ [PropertyNamingPolicy 글로벌 설정](system-text-json-customize-properties.md#use-camel-case-for-all-json-property-names) |
| 최소 문자 이스케이프                            | ✔️ [엄격한 문자 이스케이프, 구성 가능](#minimal-character-escaping) |
| `NullValueHandling.Ignore` 글로벌 설정             | ✔️ [DefaultIgnoreCondition 전역 옵션](system-text-json-ignore-properties.md#ignore-all-null-value-properties) |[조건부로 속성 무시](#conditionally-ignore-a-property)
| 주석 허용                                        | ✔️ [ReadCommentHandling 글로벌 설정](#comments) |
| 후행 쉼표 허용                                 | ✔️ [AllowTrailingCommas 글로벌 설정](#trailing-commas) |
| 사용자 지정 변환기 등록                         | ✔️ [우선 순위가 다름](#converter-registration-precedence) |
| 기본적으로 최대 깊이 없음                           | ✔️ [기본 최대 깊이는 64, 구성 가능](#maximum-depth) |
| `PreserveReferencesHandling` 글로벌 설정           | ✔️ [ReferenceHandling 전역 설정](#preserve-object-references-and-handle-loops) |
| 따옴표 안의 숫자를 직렬화하거나 역직렬화            | ✔️ [NumberHandling 전역 설정, [JsonNumberHandling] 특성](#allow-or-write-numbers-in-quotes) |
| 변경할 수 없는 클래스 및 구조체로 역직렬화          | ✔️ [JsonConstructor, C# 9 레코드](#deserialize-to-immutable-classes-and-structs) |
| 필드에 대한 지원                                    | ✔️ [IncludeFields 전역 설정, [JsonInclude] 특성](#public-and-non-public-fields) |
| `DefaultValueHandling` 글로벌 설정                 | ✔️ [DefaultIgnoreCondition 전역 설정](#conditionally-ignore-a-property) |
| `[JsonProperty]`에서의 `NullValueHandling` 설정       | ✔️ [JsonIgnore 특성](#conditionally-ignore-a-property)  |
| `[JsonProperty]`에서의 `DefaultValueHandling` 설정    | ✔️ [JsonIgnore 특성](#conditionally-ignore-a-property)  |
| 문자열이 아닌 키로 `Dictionary` 역직렬화          | ✔️ [지원됨](#dictionary-with-non-string-key) |
| public이 아닌 속성 setter 및 getter 지원   | ✔️ [JsonInclude 특성](#non-public-property-setters-and-getters) |
| `[JsonConstructor]` 특성                         | ✔️ [JsonConstructor 특성](#specify-constructor-to-use-when-deserializing) |
| 광범위한 형식 지원                    | ⚠️ [일부 형식은 사용자 지정 변환기 필요](#types-without-built-in-support) |
| 다형 직렬화                             | ⚠️ [지원되지 않음, 해결 가능, 샘플](#polymorphic-serialization) |
| 다형 역직렬화                           | ⚠️ [지원되지 않음, 해결 가능, 샘플](#polymorphic-deserialization) |
| 유추 형식을 `object` 속성으로 역직렬화      | ⚠️ [지원되지 않음, 해결 가능, 샘플](#deserialization-of-object-properties) |
| JSON `null` 리터럴을 null을 허용하지 않는 값 형식으로 역직렬화 | ⚠️ [지원되지 않음, 해결 가능, 샘플](#deserialize-null-to-non-nullable-type) |
| `[JsonProperty]` 특성에 대한 `Required` 설정        | ⚠️ [지원되지 않음, 해결 가능, 샘플](#required-properties) |
| 속성을 무시하는 `DefaultContractResolver`       | ⚠️ [지원되지 않음, 해결 가능, 샘플](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`, `DateFormatString` 설정   | ⚠️ [지원되지 않음, 해결 가능, 샘플](#specify-date-format) |
| 콜백                                             | ⚠️ [지원되지 않음, 해결 가능, 샘플](#callbacks) |
| `JsonConvert.PopulateObject` 메서드                   | ⚠️ [지원되지 않음, 해결 가능](#populate-existing-objects) |
| `ObjectCreationHandling` 글로벌 설정               | ⚠️ [지원되지 않음, 해결 가능](#reuse-rather-than-replace-properties) |
| setter 없이 컬렉션에 추가                    | ⚠️ [지원되지 않음, 해결 가능](#add-to-collections-without-setters) |
| `ReferenceLoopHandling` 글로벌 설정                | ❌ [지원되지 않음](#preserve-object-references-and-handle-loops) |
| `System.Runtime.Serialization` 특성 지원 | ❌ [지원되지 않음](#systemruntimeserialization-attributes) |
| `MissingMemberHandling` 글로벌 설정                | ❌ [지원되지 않음](#missingmemberhandling) |
| 따옴표 없는 속성 이름 허용                   | ❌ [지원되지 않음](#json-strings-property-names-and-string-values) |
| 문자열 값 주변에 작은따옴표 허용              | ❌ [지원되지 않음](#json-strings-property-names-and-string-values) |
| 문자열 속성에 문자열이 아닌 JSON 값 허용    | ❌ [지원되지 않음](#non-string-values-for-string-properties) |
::: zone-end

::: zone pivot="dotnet-core-3-1"
| Newtonsoft.Json 기능                               | System.Text.Json 해당 항목 |
|-------------------------------------------------------|-----------------------------|
| 기본적으로 대/소문자를 구분하지 않는 역직렬화           | ✔️ [PropertyNameCaseInsensitive 글로벌 설정](#case-insensitive-deserialization) |
| 카멜식 대/소문자 속성 이름                             | ✔️ [PropertyNamingPolicy 글로벌 설정](system-text-json-customize-properties.md#use-camel-case-for-all-json-property-names) |
| 최소 문자 이스케이프                            | ✔️ [엄격한 문자 이스케이프, 구성 가능](#minimal-character-escaping) |
| `NullValueHandling.Ignore` 글로벌 설정             | ✔️ [IgnoreNullValues 글로벌 옵션](system-text-json-ignore-properties.md#ignore-all-null-value-properties) |
| 주석 허용                                        | ✔️ [ReadCommentHandling 글로벌 설정](#comments) |
| 후행 쉼표 허용                                 | ✔️ [AllowTrailingCommas 글로벌 설정](#trailing-commas) |
| 사용자 지정 변환기 등록                         | ✔️ [우선 순위가 다름](#converter-registration-precedence) |
| 기본적으로 최대 깊이 없음                           | ✔️ [기본 최대 깊이는 64, 구성 가능](#maximum-depth) |
| 광범위한 형식 지원                    | ⚠️ [일부 형식은 사용자 지정 변환기 필요](#types-without-built-in-support) |
| 문자열을 숫자로 역직렬화                        | ⚠️ [지원되지 않음, 해결 가능, 샘플](#allow-or-write-numbers-in-quotes) |
| 문자열이 아닌 키로 `Dictionary` 역직렬화          | ⚠️ [지원되지 않음, 해결 가능, 샘플](#dictionary-with-non-string-key) |
| 다형 직렬화                             | ⚠️ [지원되지 않음, 해결 가능, 샘플](#polymorphic-serialization) |
| 다형 역직렬화                           | ⚠️ [지원되지 않음, 해결 가능, 샘플](#polymorphic-deserialization) |
| 유추 형식을 `object` 속성으로 역직렬화      | ⚠️ [지원되지 않음, 해결 가능, 샘플](#deserialization-of-object-properties) |
| JSON `null` 리터럴을 null을 허용하지 않는 값 형식으로 역직렬화 | ⚠️ [지원되지 않음, 해결 가능, 샘플](#deserialize-null-to-non-nullable-type) |
| 변경할 수 없는 클래스 및 구조체로 역직렬화          | ⚠️ [지원되지 않음, 해결 가능, 샘플](#deserialize-to-immutable-classes-and-structs) |
| `[JsonConstructor]` 특성                         | ⚠️ [지원되지 않음, 해결 가능, 샘플](#specify-constructor-to-use-when-deserializing) |
| `[JsonProperty]` 특성에 대한 `Required` 설정        | ⚠️ [지원되지 않음, 해결 가능, 샘플](#required-properties) |
| `[JsonProperty]` 특성에 대한 `NullValueHandling` 설정 | ⚠️ [지원되지 않음, 해결 가능, 샘플](#conditionally-ignore-a-property)  |
| `[JsonProperty]` 특성에 대한 `DefaultValueHandling` 설정 | ⚠️ [지원되지 않음, 해결 가능, 샘플](#conditionally-ignore-a-property)  |
| `DefaultValueHandling` 글로벌 설정                 | ⚠️ [지원되지 않음, 해결 가능, 샘플](#conditionally-ignore-a-property) |
| 속성을 무시하는 `DefaultContractResolver`       | ⚠️ [지원되지 않음, 해결 가능, 샘플](#conditionally-ignore-a-property) |
| `DateTimeZoneHandling`, `DateFormatString` 설정   | ⚠️ [지원되지 않음, 해결 가능, 샘플](#specify-date-format) |
| 콜백                                             | ⚠️ [지원되지 않음, 해결 가능, 샘플](#callbacks) |
| public 및 비-public 필드 지원              | ⚠️ [지원되지 않음, 해결 가능](#public-and-non-public-fields) |
| public이 아닌 속성 setter 및 getter 지원   | ⚠️ [지원되지 않음, 해결 가능](#non-public-property-setters-and-getters) |
| `JsonConvert.PopulateObject` 메서드                   | ⚠️ [지원되지 않음, 해결 가능](#populate-existing-objects) |
| `ObjectCreationHandling` 글로벌 설정               | ⚠️ [지원되지 않음, 해결 가능](#reuse-rather-than-replace-properties) |
| setter 없이 컬렉션에 추가                    | ⚠️ [지원되지 않음, 해결 가능](#add-to-collections-without-setters) |
| `PreserveReferencesHandling` 글로벌 설정           | ❌ [지원되지 않음](#preserve-object-references-and-handle-loops) |
| `ReferenceLoopHandling` 글로벌 설정                | ❌ [지원되지 않음](#preserve-object-references-and-handle-loops) |
| `System.Runtime.Serialization` 특성 지원 | ❌ [지원되지 않음](#systemruntimeserialization-attributes) |
| `MissingMemberHandling` 글로벌 설정                | ❌ [지원되지 않음](#missingmemberhandling) |
| 따옴표 없는 속성 이름 허용                   | ❌ [지원되지 않음](#json-strings-property-names-and-string-values) |
| 문자열 값 주변에 작은따옴표 허용              | ❌ [지원되지 않음](#json-strings-property-names-and-string-values) |
| 문자열 속성에 문자열이 아닌 JSON 값 허용    | ❌ [지원되지 않음](#non-string-values-for-string-properties) |
::: zone-end

이 목록은 `Newtonsoft.Json` 기능의 전체 목록이 아닙니다. 이 목록에는 [GitHub 이슈](https://github.com/dotnet/runtime/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) 또는 [StackOverflow](https://stackoverflow.com/questions/tagged/system.text.json) 게시물에 요청된 여러 시나리오가 포함되어 있습니다. 여기에 나열된 시나리오 중에서 현재 샘플 코드가 없는 시나리오에 대한 해결 방법을 구현하셨으며 그 방법을 공유하려는 분들은 이 페이지 하단의 **피드백** 섹션에서 **이 페이지** 를 선택하세요. 그러면 이 설명서의 GitHub 리포지토리에 이슈가 작성되고 이 페이지의 **피드백** 섹션에도 이슈가 나열됩니다.

## <a name="differences-in-default-jsonserializer-behavior-compared-to-no-locnewtonsoftjson"></a>기본 JsonSerializer와 Newtonsoft.Json의 동작 차이

<xref:System.Text.Json>은 기본적으로 엄격하며, 호출자를 대신하여 추측하거나 해석하는 것을 금지하고 결정적 동작을 강조합니다. 이 라이브러리는 성능과 보안을 위해 의도적으로 이렇게 설계되었습니다. `Newtonsoft.Json`은 기본적으로 유연합니다. 이러한 기본적인 디자인의 차이로 인해 기본 동작에서 다음과 같은 여러 가지 차이가 있습니다.

### <a name="case-insensitive-deserialization"></a>대/소문자를 구분하지 않는 역직렬화

역직렬화를 수행하는 동안 `Newtonsoft.Json`은 기본적으로 대/소문자를 구분하지 않는 속성 이름을 매칭합니다. <xref:System.Text.Json>은 기본적으로 대/소문자를 구분하며, 이 방법은 매칭을 정확히 수행하기 때문에 보다 나은 성능을 제공합니다. 대/소문자를 구분하지 않는 매칭 방법에 대한 자세한 내용은 [대/소문자를 구분하지 않는 속성 매칭](system-text-json-character-casing.md)을 참조하세요.

ASP.NET Core를 사용하여 간접적으로 `System.Text.Json`을 사용하는 경우 `Newtonsoft.Json`과 같은 동작을 얻기 위해 아무것도 할 필요가 없습니다. ASP.NET Core는 `System.Text.Json`을 사용할 때 [카멜식 대/소문자 구분 속성 이름](system-text-json-customize-properties.md#use-camel-case-for-all-json-property-names) 및 대/소문자를 구분하지 않는 매칭에 대한 설정을 지정합니다.

::: zone pivot="dotnet-5-0"
ASP.NET Core에서는 기본적으로 [따옴표 붙은 숫자](#allow-or-write-numbers-in-quotes)의 역직렬화도 가능합니다.
::: zone-end

### <a name="minimal-character-escaping"></a>최소 문자 이스케이프

직렬화할 때 `Newtonsoft.Json`은 문자를 이스케이프하지 않고 허용하는 것에 대해 비교적 관대합니다. 즉, 문자를 `\uxxxx`로 바꾸지 않으며, 여기서 `xxxx`는 문자의 코드 포인트입니다. 문자를 이스케이프할 때는 문자 앞에 `\`를 내보냅니다. 예를 들어 `"`는 `\"`가 됩니다. <xref:System.Text.Json>은 XSS(교차 사이트 스크립팅) 또는 정보 공개 공격에 대한 심층 방어를 제공하기 위해 기본적으로 더 많은 문자를 이스케이프하며, 그러기 위해 6문자 시퀀스를 사용합니다. `System.Text.Json`은 기본적으로 ASCII가 아닌 모든 문자를 이스케이프하므로, `Newtonsoft.Json`에서 `StringEscapeHandling.EscapeNonAscii`를 사용 중이라면 아무것도 할 필요가 없습니다. 또한 `System.Text.Json`은 기본적으로 HTML 구분 문자를 이스케이프합니다. 기본 `System.Text.Json` 동작을 재정의하는 방법에 대한 자세한 내용은 [문자 인코딩 사용자 지정](system-text-json-character-encoding.md)을 참조하세요.

### <a name="comments"></a>주석

역직렬화할 때 `Newtonsoft.Json`은 기본적으로 JSON의 주석을 무시합니다. [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에 주석이 포함되지 않기 때문에 <xref:System.Text.Json>은 기본적으로 주석에 대해 예외를 throw합니다. 주석을 허용하는 방법에 대한 자세한 내용은 [주석과 후행 쉼표 허용](system-text-json-invalid-json.md)을 참조하세요.

### <a name="trailing-commas"></a>후행 쉼표

역직렬화할 때 `Newtonsoft.Json`은 기본적으로 후행 쉼표를 무시합니다. 또한 여러 개의 후행 쉼표를 무시합니다(예: `[{"Color":"Red"},{"Color":"Green"},,]`). [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 후행 쉼표를 허용하지 않기 때문에 <xref:System.Text.Json>은 기본적으로 후행 쉼표에 대해 예외를 throw합니다. `System.Text.Json`에서 후행 쉼표를 허용하게 만드는 방법은 [주석과 후행 쉼표 허용](system-text-json-invalid-json.md)을 참조하세요. 후행 쉼표를 여러 개 허용하는 방법은 없습니다.

### <a name="converter-registration-precedence"></a>변환기 등록 우선 순위

사용자 지정 변환기에 대한 `Newtonsoft.Json` 등록 우선 순위는 다음과 같습니다.

* 속성의 특성
* 형식의 특성
* [변환기](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_Converters.htm) 컬렉션

이 순서는 형식 수준에서 특성을 적용하여 등록된 변환기가 `Converters` 컬렉션의 사용자 지정 변환기를 재정의한다는 뜻입니다. 두 등록 모두 속성 수준에서 특성에 의해 재정의됩니다.

사용자 지정 변환기에 대한 <xref:System.Text.Json> 등록 우선 순위는 다음과 같이 다릅니다.

* 속성의 특성
* <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션
* 형식의 특성

여기서 `Converters` 컬렉션의 사용자 지정 변환기가 형식 수준에서 특성을 재정의한다는 차이가 있습니다. 이 우선 순위 순서의 숨은 의도는 런타임 변경이 디자인 타임 선택 항목을 재정의하도록 하는 것입니다. 우선 순위를 변경할 수 있는 방법은 없습니다.

사용자 지정 변환기 등록에 대한 자세한 내용은 [사용자 지정 변환기 등록](system-text-json-converters-how-to.md#register-a-custom-converter)을 참조하세요.

### <a name="maximum-depth"></a>최대 깊이

`Newtonsoft.Json`은 기본적으로 최대 깊이 제한이 없습니다. <xref:System.Text.Json>의 경우 기본 제한은 64이며, <xref:System.Text.Json.JsonSerializerOptions.MaxDepth?displayProperty=nameWithType>을 설정하여 구성할 수 있습니다.

ASP.NET Core를 사용하여 간접적으로 `System.Text.Json`를 사용하는 경우 기본 최대 깊이 제한은 32입니다. 기본값은 모델 바인딩과 동일하며 [JsonOptions 클래스](https://github.com/dotnet/aspnetcore/blob/1f56888ea03f6a113587a6c4ac4d8b2ded326ffa/src/Mvc/Mvc.Core/src/JsonOptions.cs#L17-L20)에 설정됩니다.

### <a name="json-strings-property-names-and-string-values"></a>JSON 문자열(속성 이름 및 문자열 값)

역직렬화할 때 `Newtonsoft.Json`은 큰따옴표/작은따옴표로 묶은 속성 이름 또는 따옴표 없는 속성 이름을 허용합니다. 큰따옴표 또는 작은따옴표로 묶은 문자열 값을 허용합니다. 예를 들어 `Newtonsoft.Json`은 다음 JSON을 허용합니다.

```json
{
  "name1": "value",
  'name2': "value",
  name3: 'value'
}
```

`System.Text.Json`은 큰따옴표로 묶은 속성 이름과 문자열 값만 허용합니다. [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 이 형식을 요구하며 유일하게 유효한 JSON으로 간주되는 형식이기 때문입니다.

작은따옴표로 묶은 값은 다음 메시지와 함께 [JsonException](xref:System.Text.Json.JsonException)을 반환합니다.

```output
''' is an invalid start of a value.
```

### <a name="non-string-values-for-string-properties"></a>문자열 속성에 문자열이 아닌 값 허용

`Newtonsoft.Json`은 형식 문자열의 속성으로 역직렬화할 때 숫자 또는 리터럴 `true` 및 `false`처럼 문자열이 아닌 값을 허용합니다. 아래는 `Newtonsoft.Json`이 성공적으로 다음 클래스로 역직렬화하는 JSON 예제입니다.

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

`System.Text.Json`은 문자열이 아닌 값을 문자열 속성으로 역직렬화하지 않습니다. 문자열 필드에 대해 문자열이 아닌 값을 받으면 다음 메시지와 함께 [JsonException](xref:System.Text.Json.JsonException)이 반환됩니다.

```output
The JSON value could not be converted to System.String.
```

## <a name="scenarios-using-jsonserializer"></a>JsonSerializer를 사용하는 시나리오

다음 시나리오는 기본 제공 기능에서 지원되지 않지만 해결이 가능합니다. 해결 방법은 [사용자 지정 변환기](system-text-json-converters-how-to.md)이며, 사용자 지정 변환기는 `Newtonsoft.Json` 기능과의 완전한 패리티를 제공하지 않을 수 있습니다. 그 중 일부는 샘플 코드가 예제로 제공됩니다. 이러한 `Newtonsoft.Json` 기능을 사용하는 경우 마이그레이션을 수행하려면 .NET 개체 모델 또는 기타 코드 변경 내용을 수정해야 합니다.

다음 몇몇 시나리오는 해결 방법이 실용적이지 않거나 가능하지 않습니다. 이러한 `Newtonsoft.Json` 기능을 사용하는 경우 중요한 변경 없이는 마이그레이션을 수행할 수 없습니다.

### <a name="allow-or-write-numbers-in-quotes"></a>따옴표 안에 숫자를 허용하거나 씁니다.

::: zone pivot="dotnet-5-0"
`Newtonsoft.Json`은 JSON 문자열로 표시되는(따옴표로 묶은) 숫자를 직렬화 또는 역직렬화할 수 있습니다. 예를 들어 `{"DegreesCelsius":23}` 대신 `{"DegreesCelsius":"23"}`을 허용할 수 있습니다. <xref:System.Text.Json>에서 이 동작을 사용하도록 설정하려면 <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType>을 <xref:System.Text.Json.Serialization.JsonNumberHandling.WriteAsString> 또는 <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>으로 설정하거나 [JsonNumberHandling](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) 특성을 사용합니다.

ASP.NET Core를 사용하여 간접적으로 `System.Text.Json`을 사용하는 경우 `Newtonsoft.Json`과 같은 동작을 얻기 위해 아무것도 할 필요가 없습니다. ASP.NET Core는 `System.Text.Json`을 사용할 때 [웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 지정하고, 웹 기본값은 따옴표 붙은 숫자를 허용합니다.

자세한 내용은 [따옴표 안의 숫자 허용 또는 쓰기](system-text-json-invalid-json.md)를 참조하세요.
::: zone-end

::: zone pivot="dotnet-core-3-1"
`Newtonsoft.Json`은 JSON 문자열로 표시되는(따옴표로 묶은) 숫자를 직렬화 또는 역직렬화할 수 있습니다. 예를 들어 `{"DegreesCelsius":23}` 대신 `{"DegreesCelsius":"23"}`을 허용할 수 있습니다. .NET Core 3.1의 <xref:System.Text.Json>에서 해당 동작을 사용하도록 설정하려면 다음 예제와 같이 사용자 지정 변환기를 구현합니다. 이 변환기는 다음과 같이 `long`으로 정의된 속성을 처리합니다.

* 속성을 JSON 문자열로 직렬화합니다.
* 역직렬화할 때 JSON 숫자 및 따옴표 안의 숫자를 허용합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/LongToStringConverter.cs":::

개별 `long` 속성에 대한 [특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.
::: zone-end

### <a name="specify-constructor-to-use-when-deserializing"></a>역직렬화할 때 사용할 생성자 지정

`Newtonsoft.Json` `[JsonConstructor]` 특성을 사용하면 POCO로 역직렬화할 때 호출할 생성자를 지정할 수 있습니다.

::: zone pivot="dotnet-5-0"
`System.Text.Json`에는 [JsonConstructor](xref:System.Text.Json.Serialization.JsonConstructorAttribute) 특성도 있습니다. 자세한 내용은 [변경 불가능한 형식 및 레코드](system-text-json-immutability.md)를 참조하세요.
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1에서 <xref:System.Text.Json>은 매개 변수 없는 생성자만 지원합니다. 사용자 지정 변환기에서 필요한 생성자를 호출하여 문제를 해결할 수 있습니다. 예제는 [변경할 수 없는 클래스 및 구조체로 역직렬화](#deserialize-to-immutable-classes-and-structs)를 참조하세요.
::: zone-end

### <a name="conditionally-ignore-a-property"></a>조건부로 속성 무시

`Newtonsoft.Json`은 직렬화 또는 역직렬화에서 속성을 조건부로 무시하는 여러 가지 방법이 있습니다.

* `DefaultContractResolver`를 사용하면 임의의 조건에 따라 포함하거나 무시할 속성을 선택할 수 있습니다.
* `JsonSerializerSettings`의 `NullValueHandling` 및 `DefaultValueHandling` 설정을 사용하면 모든 Null 값 또는 기본값 속성을 무시하도록 지정할 수 있습니다.
* `[JsonProperty]` 특성의 `NullValueHandling` 및 `DefaultValueHandling` 설정을 사용하면 Null 또는 기본값으로 설정된 경우에 무시할 개별 속성을 지정할 수 있습니다.

::: zone pivot="dotnet-5-0"

<xref:System.Text.Json>은 직렬화하는 동안 다음과 같은 방법으로 속성이나 필드를 무시할 수 있습니다.

* 속성의 [[JsonIgnore]](system-text-json-ignore-properties.md#ignore-individual-properties) 특성은 직렬화하는 동안 JSON에서 속성을 생략하게 합니다.
* [IgnoreReadOnlyProperties](system-text-json-ignore-properties.md#ignore-all-read-only-properties) 전역 옵션을 사용하면 모든 읽기 전용 속성을 무시할 수 있습니다.
* [필드를 포함](system-text-json-how-to.md#include-fields)하는 경우 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 전역 옵션을 통해 모든 읽기 전용 필드를 무시할 수 있습니다.
* `DefaultIgnoreCondition` 전역 옵션을 사용하면 [기본값이 있는 모든 값 형식 속성을 무시](system-text-json-ignore-properties.md#ignore-all-default-value-properties)하거나 [null 값이 있는 모든 참조 형식 속성을 무시](system-text-json-ignore-properties.md#ignore-all-null-value-properties)할 수 있습니다.

::: zone-end

::: zone pivot="dotnet-core-3-1"

.NET Core 3.1에서 <xref:System.Text.Json>은 직렬화하는 동안 다음과 같은 방법으로 속성을 무시할 수 있습니다.

* 속성의 [[JsonIgnore]](system-text-json-ignore-properties.md#ignore-individual-properties) 특성은 직렬화하는 동안 JSON에서 속성을 생략하게 합니다.
* [IgnoreNullValues](system-text-json-ignore-properties.md#ignore-all-null-value-properties) 전역 옵션을 사용하면 모든 Null 값 속성을 무시할 수 있습니다.
* [IgnoreReadOnlyProperties](system-text-json-ignore-properties.md#ignore-all-read-only-properties) 전역 옵션을 사용하면 모든 읽기 전용 속성을 무시할 수 있습니다.
::: zone-end

이러한 옵션은 다음 기능이 **없습니다**.

::: zone pivot="dotnet-5-0"

* 런타임에 평가되는 임의의 조건을 기준으로 선택한 속성을 무시합니다.

::: zone-end

::: zone pivot="dotnet-core-3-1"

* 형식의 기본값이 있는 모든 속성을 무시합니다.
* 형식의 기본값이 있는 속성 중 선택한 일부를 무시합니다.
* 선택한 속성의 값이 Null이면 해당 속성을 무시합니다.
* 런타임에 평가되는 임의의 조건을 기준으로 선택한 속성을 무시합니다.

::: zone-end

이 기능을 사용하려면 사용자 지정 변환기를 작성하면 됩니다. 다음은 이 방법을 보여주는 샘플 POCO 및 사용자 지정 변환기입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecastRuntimeIgnoreConverter.cs":::

`Summary` 속성의 값이 Null, 빈 문자열 또는 "N/A"이면 이 변환기는 직렬화에서 이 속성을 생략합니다.

[클래스에 대한 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-type)하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.

이 방법은 다음과 같은 경우에 추가 논리가 필요합니다.

* POCO에 복합 속성이 포함됩니다.
* `[JsonIgnore]`, 옵션(예: 사용자 지정 인코더) 같은 특성을 처리해야 합니다.

### <a name="public-and-non-public-fields"></a>public 및 비-public 필드

`Newtonsoft.Json`은 속성뿐 아니라 필드까지 직렬화 및 역직렬화할 수 있습니다.

::: zone pivot="dotnet-5-0"
<xref:System.Text.Json>에서 <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> 전역 설정 또는 [JsonInclude](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 특성을 사용하여 직렬화 또는 역직렬화할 때 public 필드를 포함합니다. 예제는 [필드 포함](system-text-json-how-to.md#include-fields)을 참조하세요.
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1에서 <xref:System.Text.Json>은 public 속성에서만 작동합니다. 사용자 지정 변환기는 이 기능을 제공할 수 있습니다.
::: zone-end

### <a name="preserve-object-references-and-handle-loops"></a>개체 참조 유지 및 루프 처리

기본적으로 `Newtonsoft.Json`은 값으로 직렬화합니다. 예를 들어 개체에 두 개의 속성이 있고 두 속성은 동일한 `Person` 개체에 대한 참조를 포함하는 경우 해당 `Person` 개체의 속성 값이 JSON에서 중복됩니다.

`Newtonsoft.Json`에는 참조로 직렬화할 수 있는 `JsonSerializerSettings`에 대한 `PreserveReferencesHandling` 설정이 있습니다.

* 첫 번째 `Person` 개체에 대해 만든 JSON에 식별자 메타데이터가 추가됩니다.
* 두 번째 `Person` 개체에 대해 만든 JSON에는 속성 값 대신 해당 식별자에 대한 참조가 포함됩니다.

`Newtonsoft.Json`에는 예외를 throw하는 대신 순환 참조를 무시할 수 있는 `ReferenceLoopHandling` 설정도 있습니다.

::: zone pivot="dotnet-5-0"
<xref:System.Text.Json>에서 참조를 보존하고 순환 참조를 처리하려면 <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A?displayProperty=nameWithType>을 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>로 설정합니다. `ReferenceHandler.Preserve` 설정은 `Newtonsoft.Json`의 `PreserveReferencesHandling` = `PreserveReferencesHandling.All`과 동일합니다.

Newtonsoft.Json [ReferenceResolver](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializer_ReferenceResolver.htm)와 마찬가지로 <xref:System.Text.Json.Serialization.ReferenceResolver?displayProperty=fullName> 클래스는 직렬화 및 역직렬화 시 참조를 보존하는 동작을 정의합니다. 파생 클래스를 만들어 사용자 지정 동작을 지정합니다. 예제는 [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs)를 참조하세요.

일부 관련 `Newtonsoft.Json` 기능은 지원되지 않습니다.

* [JsonPropertyAttribute.IsReference](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonPropertyAttribute_IsReference.htm)
* [JsonPropertyAttribute.ReferenceLoopHandling](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonPropertyAttribute_ReferenceLoopHandling.htm)
* [JsonSerializerSettings.ReferenceLoopHandling](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonSerializerSettings_ReferenceLoopHandling.htm)

자세한 내용은 [참조 보존 및 순환 참조 처리](system-text-json-preserve-references.md)를 참조하세요.
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1의 <xref:System.Text.Json>은 값을 사용하는 직렬화만 지원하며 순환 참조에 대한 예외를 throw합니다.
::: zone-end

### <a name="dictionary-with-non-string-key"></a>키가 문자열이 아닌 사전

::: zone pivot="dotnet-5-0"
`Newtonsoft.Json` 및 `System.Text.Json`은 모두 `Dictionary<TKey, TValue>` 형식의 컬렉션을 지원합니다.
::: zone-end

::: zone pivot="dotnet-core-3-1"
`Newtonsoft.Json`은 `Dictionary<TKey, TValue>` 형식의 컬렉션을 지원합니다. .NET Core 3.1에서 <xref:System.Text.Json>의 사전 컬렉션에 대한 기본 지원은 `Dictionary<string, TValue>`로 제한됩니다. 즉, 키는 문자열이어야 합니다.

.NET Core 3.1에서 정수 또는 다른 형식의 키를 사용하는 사전을 지원하려면 [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md#support-dictionary-with-non-string-key)의 예제와 같은 변환기를 만듭니다.
::: zone-end

### <a name="types-without-built-in-support"></a>기본적으로 지원되지 않는 형식

<xref:System.Text.Json>은 기본적으로 다음 형식을 지원하지 않습니다.

* <xref:System.Data.DataTable> 및 관련 형식
* [구분된 공용 구조체](../../fsharp/language-reference/discriminated-unions.md), [레코드 형식](../../fsharp/language-reference/records.md), [익명 레코드 형식](../../fsharp/language-reference/anonymous-records.md) 등의 F# 형식
* <xref:System.Dynamic.ExpandoObject>
* <xref:System.TimeZoneInfo>
* <xref:System.Numerics.BigInteger>
* <xref:System.TimeSpan>
* <xref:System.DBNull>
* <xref:System.Type>
* <xref:System.ValueTuple> 및 관련 제네릭 형식

기본적으로 지원되지 않는 형식에 대한 사용자 지정 변환기를 구현할 수 있습니다.

### <a name="polymorphic-serialization"></a>다형 직렬화

`Newtonsoft.Json`은 다형 직렬화를 자동으로 수행합니다. <xref:System.Text.Json>의 제한 다형 직렬화 기능에 대한 자세한 내용은 [파생 클래스의 속성 직렬화](system-text-json-polymorphism.md)를 참조하세요.

해당 문서에 설명된 해결 방법은 `object` 형식으로 파생 클래스를 포함할 수 있는 속성을 정의하는 방법입니다. 이 방법을 사용할 수 없는 경우 다른 옵션은 [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md#support-polymorphic-deserialization)의 예제와 같이 전체 상속 형식 계층 구조에 대한 `Write` 메서드를 사용하여 변환기를 만드는 것입니다.

### <a name="polymorphic-deserialization"></a>다형 역직렬화

`Newtonsoft.Json`에는 직렬화하는 동안 JSON에 형식 이름 메타데이터를 추가하는 `TypeNameHandling` 설정이 있습니다. 이 설정은 역직렬화하는 동안 메타데이터를 사용하여 다형 역직렬화를 수행합니다. <xref:System.Text.Json>은 제한된 범위의 [다형 직렬화](system-text-json-polymorphism.md)를 수행할 수 있지만 다형 역직렬화는 수행할 수 없습니다.

다형 역직렬화를 지원하려면 [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md#support-polymorphic-deserialization)의 예제와 같은 변환기를 만듭니다.

### <a name="deserialization-of-object-properties"></a>개체 속성 역직렬화

`Newtonsoft.Json`은 <xref:System.Object>로 역직렬화할 때 다음을 수행합니다.

* JSON 페이로드의 기본 값 형식(`null` 제외)을 유추하고 저장된 `string`, `long`, `double`, `boolean` 또는 `DateTime`을 boxed 개체로 반환합니다. *기본 값* 은 JSON 숫자, 문자열, `true`, `false`, `null` 등의 단일 JSON 값입니다.
* JSON 페이로드의 복합 값에 대한 `JObject` 또는 `JArray`를 반환합니다. *복합 값* 은 중괄호(`{}`) 안에 있는 JSON 키-값 쌍 컬렉션 또는 대괄호(`[]`) 안에 있는 값 목록입니다. 중괄호 또는 대괄호 안에 있는 속성과 값이 추가 속성 또는 값을 가질 수 있습니다.
* 페이로드에 `null` JSON 리터럴이 있으면 null 참조를 반환합니다.

<xref:System.Text.Json>은 <xref:System.Object>로 역직렬화할 때마다 기본 값과 복합 값 모두에 대한 boxed `JsonElement`를 저장하며, 다음은 그 예입니다.

* `object` 속성
* `object` 사전 값
* `object` 배열 값
* 루트 `object`

그러나 페이로드에 `null` JSON 리터럴이 있으면 `System.Text.Json`은 `null`을 `Newtonsoft.Json`과 같은 방법으로 처리하고 null 참조를 반환합니다.

`object` 속성에 대한 형식 유추를 구현하려면 [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md#deserialize-inferred-types-to-object-properties)의 예제와 같은 변환기를 만듭니다.

### <a name="deserialize-null-to-non-nullable-type"></a>null을 허용하지 않는 형식으로 Null 역직렬화

`Newtonsoft.Json`은 는 다음과 같은 시나리오에서 예외를 throw하지 않습니다.

* `NullValueHandling`이 `Ignore`로 설정된 경우
* 역직렬화를 수행하는 동안 JSON은 null을 허용하지 않는 값 형식에 대해 Null 값을 포함합니다.

동일한 시나리오에서 <xref:System.Text.Json>은 예외를 throw합니다. (`System.Text.Json`에서 해당하는 null 처리 설정은 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> = `true`입니다.)

대상 형식을 소유하고 있는 경우 가장 좋은 해결 방법은 문제가 되는 속성을 null 허용으로 만드는 것입니다(예를 들어 `int`를 `int?`로 변경).

또 다른 해결 방법은 `DateTimeOffset` 형식의 Null 값을 처리하는 다음 예제처럼 형식에 대한 변환기를 만드는 것입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DateTimeOffsetNullHandlingConverter.cs":::

[속성에 대한 특성을 사용](system-text-json-converters-how-to.md#registration-sample---jsonconverter-on-a-property)하거나 <xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.

**참고:** 위의 변환기는 기본값을 지정하는 POCO를 `Newtonsoft.Json`이 처리하는 방법과는 **다르게 Null 값을 처리** 합니다. 예를 들어 다음 코드가 대상 개체를 보여준다고 가정하겠습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithDefault":::

그리고 앞의 변환기를 사용하여 다음 JSON을 역직렬화한다고 가정합니다.

```json
{
  "Date": null,
  "TemperatureCelsius": 25,
  "Summary": null
}
```

역직렬화 후 `Date` 속성에 1/1/0001(`default(DateTimeOffset)`)이 있습니다. 즉, 생성자에서 설정한 값이 덮어쓰기 되었습니다. POCO 및 JSON이 동일할 때 `Newtonsoft.Json` 역직렬화 시 `Date` 속성에 1/1/2001이 남습니다.

### <a name="deserialize-to-immutable-classes-and-structs"></a>변경할 수 없는 클래스 및 구조체로 역직렬화

`Newtonsoft.Json`은 매개 변수가 있는 생성자를 사용할 수 있기 때문에 변경 불가능한 클래스 및 구조체로 역직렬화할 수 있습니다.

::: zone pivot="dotnet-5-0"
<xref:System.Text.Json>에서 [JsonConstructor](xref:System.Text.Json.Serialization.JsonConstructorAttribute) 특성을 사용하여 매개 변수가 있는 생성자의 사용을 지정합니다. C# 9의 레코드도 변경할 수 없으며, 역직렬화 대상으로 지원됩니다. 자세한 내용은 [변경 불가능한 형식 및 레코드](system-text-json-immutability.md)를 참조하세요.
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1에서 <xref:System.Text.Json>은 매개 변수 없는 public 생성자만 지원합니다. 사용자 지정 변환기에서 매개 변수가 있는 생성자를 호출하여 문제를 해결할 수 있습니다.

다음은 여러 생성자 매개 변수가 있는 변경할 수 없는 구조체입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ImmutablePoint.cs" id="ImmutablePoint":::

다음은 이 구조체를 직렬화 및 역직렬화하는 변환기입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ImmutablePointConverter.cs":::

<xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.

개방형 제네릭 속성을 처리하는 비슷한 변환기의 예제는 [키-값 쌍에 사용되는 기본 제공 변환기](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/src/System/Text/Json/Serialization/Converters/JsonValueConverterKeyValuePair.cs)를 참조하세요.
::: zone-end

### <a name="required-properties"></a>필수 속성

`Newtonsoft.Json`에서 `[JsonProperty]` 특성에 대한 `Required`를 설정하여 속성을 필수로 지정합니다. 필수로 지정된 속성에 대해 JSON에서 값을 받지 못하면 `Newtonsoft.Json`이 예외를 throw합니다.

대상 형식의 속성 중 하나에 대한 값을 받지 못해도 <xref:System.Text.Json>은 예외를 throw하지 않습니다. 예를 들어 `WeatherForecast` 클래스가 있는 경우 다음과 같습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

다음 JSON은 오류 없이 역직렬화됩니다.

```json
{
    "TemperatureCelsius": 25,
    "Summary": "Hot"
}
```

JSON에 `Date` 속성이 없으면 역직렬화가 실패하도록 구성하려면 사용자 지정 변환기를 구현합니다. 다음 샘플 변환기 코드는 역직렬화 완료 후 `Date` 속성이 설정되지 않으면 예외를 throw합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverter.cs":::

<xref:System.Text.Json.JsonSerializerOptions.Converters?displayProperty=nameWithType> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.

변환기를 재귀적으로 호출하는 이 패턴을 사용하려면 특성이 아닌 <xref:System.Text.Json.JsonSerializerOptions>를 사용하여 변환기를 등록해야 합니다. 특성을 사용하여 변환기를 등록하는 경우 사용자 지정 변환기가 재귀적으로 자신을 호출합니다. 그 결과 스택 오버플로 예외로 이어지는 무한 루프가 발생합니다.

옵션 개체를 사용하여 변환기를 등록하는 경우 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 또는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A>를 재귀적으로 호출할 때 옵션 개체를 전달하지 않음으로써 무한 루프 발생을 방지합니다. options 개체는 <xref:System.Text.Json.JsonSerializerOptions.Converters%2A> 컬렉션을 포함하고 있습니다. 이 개체를 `Serialize` 또는 `Deserialize`에 전달하면 사용자 지정 변환기가 자신을 호출하여 스택 오버플로 예외로 이어지는 무한 루프가 발생합니다. 기본 옵션이 실현 불가능한 경우 필요한 설정을 사용하여 새로운 옵션 인스턴스를 만듭니다. 이 방법은 각각의 새 인스턴스가 독립적으로 캐시하므로 속도가 느립니다.

변환할 클래스에서 `JsonConverterAttribute` 등록을 사용할 수 있는 대체 패턴이 있습니다. 이 방식으로 변환기 코드는 변환할 클래스에서 파생된 클래스에 대해 `Serialize` 또는 `Deserialize`를 호출합니다. 파생 클래스에는 `JsonConverterAttribute`가 적용되지 않습니다. 이 대체 패턴의 다음 예제에서:

* `WeatherForecastWithRequiredPropertyConverterAttribute`는 역직렬화할 클래스이며 `JsonConverterAttribute`가 적용됩니다.
* `WeatherForecastWithoutRequiredPropertyConverterAttribute`는 변환기 특성이 없는 파생 클래스입니다.
* 변환기의 코드는 `WeatherForecastWithoutRequiredPropertyConverterAttribute`에서 `Serialize` 및 `Deserialize`를 호출하여 무한 루프를 방지합니다. 추가 개체 인스턴스화 및 속성 값 복사로 인해 직렬화에 대한 이 방식에 성능 비용이 발생합니다.

`WeatherForecast*` 형식은 다음과 같습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithReqPptyConverterAttr":::

변환기는 다음과 같습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecastRequiredPropertyConverterForAttributeRegistration.cs":::

특성(예: [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 또는 다른 옵션(예: 사용자 지정 인코더))을 처리해야 하는 경우에는 필수 속성 변환기에 추가 논리가 필요합니다. 또한 예제 코드는 생성자에서 기본값이 설정된 속성을 처리하지 않습니다. 이 방법은 다음과 같은 시나리오를 구분하지 않습니다.

* JSON에서 속성이 누락되었습니다.
* null을 허용하지 않는 형식의 속성은 JSON에 있지만, 값은 형식에 대한 기본값입니다(`int`는 0).
* null 허용 값 형식의 속성이 JSON에 있지만, 값은 Null입니다.

### <a name="specify-date-format"></a>날짜 형식 지정

`Newtonsoft.Json`은 `DateTime` 및 `DateTimeOffset` 형식의 속성 직렬화 및 역직렬화 방식을 여러 가지 방법으로 제어할 수 있습니다.

* `DateTimeZoneHandling` 설정을 사용하여 모든 `DateTime` 값을 UTC 날짜로 직렬화할 수 있습니다.
* `DateFormatString` 설정 및 `DateTime` 변환기를 사용하여 날짜 문자열의 형식을 사용자 지정할 수 있습니다.

<xref:System.Text.Json>에서 기본적으로 지원되는 유일한 형식은 널리 사용되고 모호하지 않고 라운드트립을 정확하게 수행하는 ISO 8601-1:2019입니다. 다른 형식을 사용하려면 사용자 지정 변환기를 만듭니다. 자세한 내용은 [System.Text.Json의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)을 참조하세요.

### <a name="callbacks"></a>콜백

`Newtonsoft.Json`은 다음과 같이 직렬화 또는 역직렬화 프로세스의 여러 지점에서 사용자 지정 코드를 실행할 수 있습니다.

* OnDeserializing(개체 역직렬화를 시작할 때)
* OnDeserialized(개체 역직렬화가 완료될 때)
* OnSerializing(개체 직렬화를 시작할 때)
* OnSerialized(개체 직렬화가 완료될 때)

<xref:System.Text.Json>에서는 사용자 지정 변환기를 작성하여 콜백을 시뮬레이션할 수 있습니다. 다음 예제에서는 POCO용 사용자 지정 변환기를 보여줍니다. 이 변환기에는 `Newtonsoft.Json` 콜백에 해당하는 각 지점에 메시지를 표시하는 코드가 포함되어 있습니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecastCallbacksConverter.cs":::

<xref:System.Text.Json.JsonSerializerOptions.Converters> 컬렉션에 [변환기를 추가](system-text-json-converters-how-to.md#registration-sample---converters-collection)하여 이 사용자 지정 변환기를 등록합니다.

이전 샘플을 따르는 사용자 지정 변환기를 사용하는 경우:

* `OnDeserializing` 코드는 새 POCO 인스턴스에 액세스할 수 없습니다. 역직렬화를 시작할 때 새 POCO 인스턴스를 조작하려면 이 코드를 POCO 생성자에 배치하세요.
* 옵션 개체에 변환기를 등록하고 `Serialize` 또는 `Deserialize`를 재귀적으로 호출할 때 옵션 개체를 전달하지 않음으로써 무한 루프 발생을 방지합니다.

`Serialize` 또는 `Deserialize`를 재귀적으로 호출하는 사용자 지정 변환기에 대한 자세한 내용은 이 문서의 앞부분에 나오는 [필수 속성](#required-properties) 섹션을 참조하세요.

### <a name="non-public-property-setters-and-getters"></a>public이 아닌 속성 setter 및 getter

`Newtonsoft.Json`은 `JsonProperty` 특성을 통해 private/internal 속성 setter 및 getter를 사용할 수 있습니다.

::: zone pivot="dotnet-5-0"
<xref:System.Text.Json>은 [JsonInclude](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 특성을 통해 private 및 internal 속성 setter 및 getter를 지원합니다. 샘플 코드는 [public이 아닌 속성 접근자](system-text-json-immutability.md)를 참조하세요.
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1에서 <xref:System.Text.Json>은 public setter만 지원합니다. 사용자 지정 변환기는 이 기능을 제공할 수 있습니다.
::: zone-end

### <a name="populate-existing-objects"></a>기존 개체 채우기

`Newtonsoft.Json`의 `JsonConvert.PopulateObject` 메서드는 새 인스턴스를 만드는 대신 JSON 문서를 클래스의 기존 인스턴스로 역직렬화합니다. <xref:System.Text.Json>은 항상 매개 변수 없는 기본 public 생성자를 사용하여 대상 형식의 새 인스턴스를 만듭니다. 사용자 지정 변환기는 기존 인스턴스로 역직렬화할 수 있습니다.

### <a name="reuse-rather-than-replace-properties"></a>속성을 바꾸지 않고 재사용

`Newtonsoft.Json` `ObjectCreationHandling` 설정을 사용하면 역직렬화 중에 속성의 개체를 바꾸지 않고 재사용하도록 지정할 수 있습니다. <xref:System.Text.Json>은 항상 속성의 개체를 바꿉니다.  사용자 지정 변환기는 이 기능을 제공할 수 있습니다.

### <a name="add-to-collections-without-setters"></a>setter 없이 컬렉션에 추가

역직렬화를 수행하는 동안 `Newtonsoft.Json`은 속성에 setter가 없는 경우에도 개체를 컬렉션에 추가합니다. <xref:System.Text.Json>은 setter가 없는 속성을 무시합니다. 사용자 지정 변환기는 이 기능을 제공할 수 있습니다.

### <a name="systemruntimeserialization-attributes"></a>System.Runtime.Serialization 특성

<xref:System.Text.Json>은 `DataMemberAttribute` 및 `IgnoreDataMemberAttribute`와 같은 `System.Runtime.Serialization` 네임스페이스의 특성을 지원하지 않습니다.

### <a name="octal-numbers"></a>8진수

`Newtonsoft.Json`은 선행 0이 있는 숫자를 8진수로 처리합니다. [RFC 8259](https://tools.ietf.org/html/rfc8259) 사양에서 선행 0을 허용하지 않으므로 <xref:System.Text.Json>은 선행 0을 허용하지 않습니다.

### <a name="missingmemberhandling"></a>MissingMemberHandling

JSON이 대상 형식에 없는 속성을 포함하는 경우 역직렬화 중에 예외를 throw하도록 `Newtonsoft.Json`을 구성할 수 있습니다. <xref:System.Text.Json>은 [[JsonExtensionData] 특성](system-text-json-handle-overflow.md)를 사용하는 경우를 제외하고 JSON의 추가 속성을 무시합니다. 누락된 멤버 기능에 대한 해결 방법은 없습니다.

### <a name="tracewriter"></a>TraceWriter

`Newtonsoft.Json`은 직렬화 또는 역직렬화에서 생성된 로그를 살펴보는 `TraceWriter`를 사용하여 디버그할 수 있습니다. <xref:System.Text.Json>은 로깅을 수행하지 않습니다.

## <a name="jsondocument-and-jsonelement-compared-to-jtoken-like-jobject-jarray"></a>JsonDocument 및 JsonElement과 JToken(예: JObject, JArray)의 비교

<xref:System.Text.Json.JsonDocument?displayProperty=fullName>은 기존 JSON 페이로드의 **읽기 전용** DOM(문서 개체 모델)을 구문 분석하고 빌드하는 기능을 제공합니다. DOM은 JSON 페이로드의 데이터에 대한 임의 액세스를 제공합니다. 페이로드를 구성하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다. `JsonElement` 형식은 JSON 텍스트를 일반적인 .NET 형식으로 변환하는 API를 제공합니다. `JsonDocument`는 <xref:System.Text.Json.JsonDocument.RootElement> 속성을 노출합니다.

### <a name="jsondocument-is-idisposable"></a>JsonDocument는 IDisposable

`JsonDocument`는 데이터의 메모리 내 보기를 풀링된 버퍼에 빌드합니다. 따라서 `Newtonsoft.Json`의 `JObject` 또는 `JArray`와 달리, `JsonDocument` 형식은 `IDisposable`을 구현하며 using 블록 내에서 사용해야 합니다.

수명 소유권 및 폐기 책임을 호출자에 양도하려는 경우에만 API에서 `JsonDocument`를 반환하세요. 대부분의 시나리오에서는 이렇게 할 필요가 없습니다. 호출자가 전체 JSON 문서를 사용해야 하는 경우 <xref:System.Text.Json.JsonElement>인 <xref:System.Text.Json.JsonDocument.RootElement%2A>의 <xref:System.Text.Json.JsonElement.Clone%2A>을 반환하세요. 호출자가 JSON 문서 내의 특정 요소를 사용해야 하는 경우 해당 <xref:System.Text.Json.JsonElement>의 <xref:System.Text.Json.JsonElement.Clone%2A>을 반환하세요. `Clone`을 만들지 않고 `RootElement` 또는 하위 요소를 직접 반환하면 해당 소유권을 가진 `JsonDocument`가 폐기된 후에 반환되는 `JsonElement`에 호출자가 액세스할 수 없습니다.

다음은 `Clone`을 만들어야 하는 예제입니다.

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

위의 코드에는 `fileName` 속성을 포함하는 `JsonElement`가 필요합니다. 위의 코드는 JSON 파일을 열고 `JsonDocument`를 만듭니다. 이 메서드는 호출자가 전체 문서를 사용하려 한다고 가정하고 `RootElement`의 `Clone`을 반환합니다.

`JsonElement`를 수신하고 하위 요소를 반환하는 경우에는 하위 요소의 `Clone`을 반환할 필요가 없습니다. 호출자는 전달된 `JsonElement`가 속한 `JsonDocument`를 활성 상태로 유지해야 합니다. 예를 들어:

```csharp
public JsonElement ReturnFileName(JsonElement source)
{
   return source.GetProperty("fileName");
}
```

### <a name="jsondocument-is-read-only"></a>JsonDocument는 읽기 전용

<xref:System.Text.Json> DOM은 JSON 요소를 추가, 제거 또는 수정할 수 없습니다. 이렇게 설계한 이유는 성능을 향상하고 일반 JSON 페이로드 크기를 구문 분석할 때 할당을 줄이는(즉, 1MB 미만) 것입니다. 현재 시나리오에서 수정 가능한 DOM을 사용하는 경우 다음 해결 방법 중 하나를 사용할 수 있습니다.

* `JsonDocument`를 처음부터 새로 빌드하려면(즉, `Parse` 메서드에 기존 JSON 페이로드를 전달하지 않고) `Utf8JsonWriter`를 사용하여 JSON 텍스트를 작성하고 해당 출력을 구문 분석하여 새 `JsonDocument`를 만듭니다.
* 기존 `JsonDocument`를 수정하려면 이를 사용하여 JSON 텍스트를 작성하고, 작성하는 동안 필요한 대로 변경하고, 해당 출력을 구문 분석하여 새 `JsonDocument`를 만듭니다.
* `Newtonsoft.Json`의 `JObject.Merge` 또는 `JContainer.Merge` API에 해당하는 기존 JSON 문서를 병합하려면 [이 GitHub 이슈](https://github.com/dotnet/corefx/issues/42466#issuecomment-570475853)를 참조하세요.

### <a name="jsonelement-is-a-union-struct"></a>JsonElement는 공용 구조체

`JsonDocument`는 `RootElement`를 JSON 요소를 포함하는 공용 구조체 형식인 <xref:System.Text.Json.JsonElement> 형식의 속성으로 노출합니다. `Newtonsoft.Json`은 `JObject`, `JArray`, `JToken` 등의 전용 계층형 형식을 사용합니다. `JsonElement`는 검색하고 열거할 수 있으며, `JsonElement`를 사용하여 JSON 요소를 .NET 형식으로 구체화할 수 있습니다.

### <a name="how-to-search-a-jsondocument-and-jsonelement-for-sub-elements"></a>하위 요소의 JsonDocument 및 JsonElement를 검색하는 방법

`Newtonsoft.Json`에서 `JObject` 또는 `JArray`를 사용하여 JSON 토큰을 검색하면 일부 사전을 조회하기 때문에 비교적 속도가 빠릅니다. 그에 비해, `JsonElement`에서 검색하려면 속성을 순차적으로 검색해야 하므로 상대적으로 느립니다(예: `TryGetProperty`를 사용하는 경우). <xref:System.Text.Json>은 조회 시간이 아닌 초기 구문 분석 시간을 최소화하도록 설계되었습니다. 따라서 `JsonDocument` 개체를 검색할 때 성능을 최적화하려면 다음 방법을 사용하세요.

* 자체적으로 인덱싱 또는 루프를 수행하지 말고 기본 제공 열거자(<xref:System.Text.Json.JsonElement.EnumerateArray%2A> 및 <xref:System.Text.Json.JsonElement.EnumerateObject%2A>)를 사용합니다.
* `RootElement`를 사용하여 전체 `JsonDocument`의 모든 속성을 순차적으로 검색하지 마세요. 그 대신, 알려진 JSON 데이터 구조체를 기반으로 중첩된 JSON 개체를 검색합니다. 예를 들어 `Student` 개체에서 `Grade` 속성을 찾고 있는 경우 모든 `JsonElement` 개체를 검색하여 `Grade` 속성을 찾지 말고, `Student` 개체를 반복하여 각 개체의 `Grade` 값을 가져옵니다. 모든 개체를 검색하면 동일한 데이터에 대해 불필요한 전달 과정이 발생합니다.

코드 예제는 [JsonDocument를 사용하여 데이터 액세스](write-custom-serializer-deserializer.md#use-jsondocument-for-access-to-data)를 참조하세요.

## <a name="utf8jsonreader-compared-to-jsontextreader"></a>Utf8JsonReader과 JsonTextReader 비교

<xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>은 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) 또는 [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601)에서 읽어온 UTF-8 인코딩 JSON 텍스트를 위한 고성능, 저할당, 전달 전용 판독기입니다. `Utf8JsonReader`는 사용자 지정 구문 분석기 및 역직렬 변환기를 빌드하는 데 활용할 수 있는 하위 수준 형식입니다.

다음 섹션에서는 `Utf8JsonReader`를 사용할 때 권장하는 프로그래밍 패턴에 대해 설명합니다.

### <a name="utf8jsonreader-is-a-ref-struct"></a>Utf8JsonReader는 ref struct

`Utf8JsonReader` 형식은 *ref struct* 이므로 [특정 제한](../../csharp/language-reference/builtin-types/struct.md#ref-struct)이 있습니다. 예를 들어 ref struct가 아닌 클래스 또는 구조체에 필드로 저장할 수 없습니다. 고성능을 얻으려면 출력 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601)를 캐시해야 하는데 그 자체가 ref struct이므로 이 형식은 `ref struct`여야 합니다. 또한 이 형식은 상태를 유지하기 때문에 변경 가능합니다. 따라서 값이 아닌 **ref로 전달** 해야 합니다. 값으로 전달하면 구조체 복사본이 생성되고 상태 변경 내용이 호출자에게 표시되지 않습니다. `Newtonsoft.Json` `JsonTextReader`는 클래스이므로 `Newtonsoft.Json`과는 다릅니다. ref struct 사용 방법에 대한 자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../csharp/write-safe-efficient-code.md)을 참조하세요.

### <a name="read-utf-8-text"></a>UTF-8 텍스트 읽기

`Utf8JsonReader`를 사용할 때 가능한 최상의 성능을 얻으려면 UTF-16 문자열이 아닌 UTF-8 텍스트로 이미 인코딩된 JSON 페이로드를 읽으세요. 코드 예제는 [Utf8JsonReader를 사용하여 데이터 필터링](write-custom-serializer-deserializer.md#filter-data-using-utf8jsonreader)을 참조하세요.

### <a name="read-with-a-stream-or-pipereader"></a>Stream 또는 PipeReader를 사용하여 읽기

`Utf8JsonReader`는 UTF-8로 인코딩된 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601) 또는 [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601)에서 읽기(<xref:System.IO.Pipelines.PipeReader>에서 읽은 결과)를 지원합니다.

동기 읽기의 경우 스트림의 끝에서 바이트 배열까지 JSON 페이로드를 읽은 후 판독기에 전달할 수 있습니다. 문자열(UTF-16으로 인코딩되는)에서 읽으려면 <xref:System.Text.Encoding.UTF8>.<xref:System.Text.Encoding.GetBytes%2A>를 호출하여 먼저 문자열을 UTF-8로 인코딩된 바이트 배열로 변환합니다. 그런 다음, `Utf8JsonReader`에 전달합니다.

`Utf8JsonReader`는 입력을 JSON 텍스트로 간주하므로 UTF-8 BOM(바이트 순서 표시)은 잘못된 JSON으로 간주됩니다. 호출자는 데이터를 판독기에 전달하기 전에 필터링해야 합니다.

코드 예제는 [Utf8JsonReader 사용](write-custom-serializer-deserializer.md#use-utf8jsonreader)을 참조하세요.

### <a name="read-with-multi-segment-readonlysequence"></a>다중 세그먼트 ReadOnlySequence를 사용하여 읽기

JSON 입력이 [ReadOnlySpan\<byte>](xref:System.ReadOnlySpan%601)이면 읽기 루프를 진행할 때 판독기의 `ValueSpan` 속성에서 각 JSON 요소에 액세스할 수 있습니다. 그러나 입력이 [ReadOnlySequence\<byte>](xref:System.Buffers.ReadOnlySequence%601)(<xref:System.IO.Pipelines.PipeReader>에서 읽은 결과)인 경우에는 일부 JSON 요소가 `ReadOnlySequence<byte>` 개체의 여러 세그먼트에 걸쳐 있을 수 있습니다. 이러한 요소는 연속 메모리 블록의 <xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>에서 액세스할 수 없습니다. 그 대신, 다중 세그먼트 `ReadOnlySequence<byte>`가 입력으로 사용될 때마다 판독기에서 <xref:System.Text.Json.Utf8JsonReader.HasValueSequence%2A> 속성을 폴링하여 현재 JSON 요소에 액세스하는 방법을 확인하세요. 다음은 권장 패턴입니다.

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

### <a name="use-valuetextequals-for-property-name-lookups"></a>속성 이름 조회에 ValueTextEquals 사용

<xref:System.Text.Json.Utf8JsonReader.ValueSpan%2A>을 사용하여 바이트 단위 비교를 수행하려면 속성 이름 조회를 위한 <xref:System.MemoryExtensions.SequenceEqual%2A>을 호출하지 마세요. 그 대신 JSON에서 이스케이프된 모든 문자를 이스케이프 해제하는 <xref:System.Text.Json.Utf8JsonReader.ValueTextEquals%2A>를 호출하세요. 다음은 "name"이라는 속성을 검색하는 방법을 보여주는 예제입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs" id="DefineUtf8Var":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/ValueTextEqualsExample.cs" id="UseUtf8Var" highlight="9":::

### <a name="read-null-values-into-nullable-value-types"></a>Null 값을 null 허용 값 형식으로 읽기

`Newtonsoft.Json`은 자동으로 `bool?`를 반환하여 `Null` `TokenType`을 처리하는 `ReadAsBoolean`처럼 <xref:System.Nullable%601>을 반환하는 API를 제공합니다. 기본 제공 `System.Text.Json` API는 null을 허용하지 않는 값 형식만 반환합니다. 예를 들어 <xref:System.Text.Json.Utf8JsonReader.GetBoolean%2A?displayProperty=nameWithType>은 `bool`을 반환합니다. JSON에서 `Null`을 발견하면 예외를 throw합니다. 다음 예제에서는 Null을 처리하는 두 가지 방법을 보여줍니다. 하나는 null 허용 값 형식을 반환하는 방법이고, 다른 하나는 기본값을 반환하는 방법입니다.

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

특정 대상 프레임워크에 `Newtonsoft.Json`을 계속 사용해야 하는 경우 다중 대상을 지정하여 두 가지를 구현할 수 있습니다. 그러나 이 방법은 간단하지 않으며 `#ifdefs` 및 원본 복제가 필요합니다. 최대한 많은 코드를 공유하는 한 가지 방법은 `Utf8JsonReader` 및 `Newtonsoft.Json` `JsonTextReader` 주위에 `ref struct` 래퍼를 만드는 것입니다. 이 래퍼는 동작의 차이를 격리하면서 공개 노출 영역을 통합합니다. 이렇게 하면 새 형식을 참조로 전달하는 것과 함께 변경 내용을 주로 형식 생성으로 격리할 수 있습니다. 다음은 [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 라이브러리가 따르는 패턴입니다.

* [UnifiedJsonReader.JsonTextReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.JsonTextReader.cs)
* [UnifiedJsonReader.Utf8JsonReader.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonReader.Utf8JsonReader.cs)

## <a name="utf8jsonwriter-compared-to-jsontextwriter"></a>Utf8JsonWriter와 JsonTextWriter 비교

<xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>은 `String`, `Int32` 및 `DateTime`과 같은 일반적인 .NET 형식에서 UTF-8 인코딩 JSON 텍스트를 쓸 수 있는 고성능 방법을 제공합니다. writer는 사용자 지정 직렬 변환기를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.

다음 섹션에서는 `Utf8JsonWriter`를 사용할 때 권장하는 프로그래밍 패턴에 대해 설명합니다.

### <a name="write-with-utf-8-text"></a>UTF-8 텍스트를 사용하여 쓰기

`Utf8JsonWriter`를 사용할 때 가능한 최상의 성능을 얻으려면 UTF-16 문자열이 아닌 UTF-8 텍스트로 이미 인코드된 JSON 페이로드를 쓰세요. UTF-16 문자열 리터럴을 사용하는 대신 <xref:System.Text.Json.JsonEncodedText>를 사용하여 알려진 문자열 속성 이름 및 값을 정적으로 캐시 및 미리 인코딩하여 작성기에 전달하세요. 이 방법이 UTF-8 바이트 배열을 캐시하여 사용하는 것보다 빠릅니다.

이 방법은 사용자 지정 이스케이프를 수행해야 하는 경우에도 통합니다. `System.Text.Json`은 문자열을 작성하는 동안 이스케이프를 해제할 수 없습니다. 그러나 사용자 지정 <xref:System.Text.Encodings.Web.JavaScriptEncoder>를 작성기에 옵션으로 전달하거나, 자체 `JavascriptEncoder`를 사용하여 이스케이프를 수행하는 고유한 `JsonEncodedText`를 만든 후 문자열 대신 `JsonEncodedText`를 작성할 수 있습니다. 자세한 내용은 [문자 인코딩 사용자 지정](system-text-json-character-encoding.md)을 참조하세요.

### <a name="write-raw-values"></a>원시 값 작성

`Newtonsoft.Json` `WriteRawValue` 메서드는 값이 필요한 원시 JSON을 작성합니다. <xref:System.Text.Json>에는 직접적으로 대응하는 기능이 없지만, 다음과 같은 해결 방법을 통해 유효한 JSON만 작성되도록 할 수 있습니다.

```csharp
using JsonDocument doc = JsonDocument.Parse(string);
doc.WriteTo(writer);
```

### <a name="customize-character-escaping"></a>문자 이스케이프 사용자 지정

`JsonTextWriter`의 [StringEscapeHandling](https://www.newtonsoft.com/json/help/html/T_Newtonsoft_Json_StringEscapeHandling.htm) 설정은 모든 비 ASCII 문자 **또는** HTML 문자를 이스케이프하는 옵션을 제공합니다. 기본적으로 `Utf8JsonWriter`는 모든 비 ASCII 문자 **및** HTML 문자를 이스케이프합니다. 이러한 이스케이프는 심층 방어 보안을 위해 수행됩니다. 다른 이스케이프 정책을 지정하려면 <xref:System.Text.Encodings.Web.JavaScriptEncoder>를 만들고 <xref:System.Text.Json.JsonWriterOptions.Encoder?displayProperty=nameWithType>을 설정하세요. 자세한 내용은 [문자 인코딩 사용자 지정](system-text-json-character-encoding.md)을 참조하세요.

### <a name="customize-json-format"></a>JSON 형식 사용자 지정

`JsonTextWriter`에는 다음과 같은 설정이 있으며, `Utf8JsonWriter`에는 해당 기능이 없습니다.

* [Indentation](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_Indentation.htm) - 들여쓸 문자 수를 지정합니다. `Utf8JsonWriter`는 항상 2자 들여쓰기를 수행합니다.
* [IndentChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_IndentChar.htm) - 들여쓰기에 사용할 문자를 지정합니다.  `Utf8JsonWriter`는 항상 공백을 사용합니다.
* [QuoteChar](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteChar.htm) - 문자열 값을 묶는 데 사용할 문자를 지정합니다.  `Utf8JsonWriter`는 항상 큰따옴표를 사용합니다.
* [QuoteName](https://www.newtonsoft.com/json/help/html/P_Newtonsoft_Json_JsonTextWriter_QuoteName.htm) - 속성 이름을 따옴표로 묶을지 여부를 지정합니다.  `Utf8JsonWriter`는 항상 속성 이름을 따옴표로 묶습니다.

이러한 방법으로 `Utf8JsonWriter`에서 생성된 JSON을 사용자 지정할 수 있는 해결 방법은 없습니다.

### <a name="write-null-values"></a>null 값 쓰기

`Utf8JsonWriter`를 사용하여 null 값을 쓰려면 다음을 호출합니다.

* <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A> - Null을 사용하는 키-값 쌍을 값으로 씁니다.
* <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue%2A> - Null을 JSON 배열의 요소로 씁니다.

문자열 속성의 경우 문자열이 Null이면 <xref:System.Text.Json.Utf8JsonWriter.WriteString%2A> 및 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>는 `WriteNull` 및 `WriteNullValue`와 동일합니다.

### <a name="write-timespan-uri-or-char-values"></a>Timespan, Uri 또는 char 값 쓰기

`JsonTextWriter`는 [TimeSpan](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_18.htm), [Uri](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_22.htm) 및 [char](https://www.newtonsoft.com/json/help/html/M_Newtonsoft_Json_JsonTextWriter_WriteValue_3.htm) 값에 대한 `WriteValue` 메서드를 제공합니다. `Utf8JsonWriter`에는 이에 해당하는 메서드가 없습니다. 그 대신 이러한 값을 문자열로 포맷하고(예를 들어 `ToString()`을 호출) <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue%2A>를 호출할 수 있습니다.

### <a name="multi-targeting"></a>멀티 타기팅

특정 대상 프레임워크에 `Newtonsoft.Json`을 계속 사용해야 하는 경우 다중 대상을 지정하여 두 가지를 구현할 수 있습니다. 그러나 이 방법은 간단하지 않으며 `#ifdefs` 및 원본 복제가 필요합니다. 최대한 많은 코드를 공유하는 한 가지 방법은 `Utf8JsonWriter` 및 `Newtonsoft` `JsonTextWriter` 주위에 래퍼를 만드는 것입니다. 이 래퍼는 동작의 차이를 격리하면서 공개 노출 영역을 통합합니다. 이를 통해 변경 내용을 주로 형식 생성으로 격리할 수 있습니다. [Microsoft.Extensions.DependencyModel](https://www.nuget.org/packages/Microsoft.Extensions.DependencyModel/3.1.0/) 라이브러리는 다음 패턴을 따릅니다.

* [UnifiedJsonWriter.JsonTextWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.JsonTextWriter.cs)
* [UnifiedJsonWriter.Utf8JsonWriter.cs](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/installer/managed/Microsoft.Extensions.DependencyModel/UnifiedJsonWriter.Utf8JsonWriter.cs)

## <a name="additional-resources"></a>추가 자료

<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)[Restore this when the roadmap is updated.]-->
* [System.Text.Json 개요](system-text-json-overview.md)
* [System.Text.Json 사용 방법](system-text-json-how-to.md)
* [사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md)
* [System.Text.Json의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
* [System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)
