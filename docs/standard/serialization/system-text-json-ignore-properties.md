---
title: System.Text.Json을 사용하여 속성을 무시하는 방법
description: .NET에서 System.Text.Json을 사용하여 직렬화할 때 속성을 무시하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: ed7ef8509d6660bbbbaf194a87aa9d4815143507
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439823"
---
# <a name="how-to-ignore-properties-with-no-locsystemtextjson"></a>System.Text.Json을 사용하여 속성을 무시하는 방법

C# 개체를 JavaScript Object Notation(JSON)으로 직렬화하면 기본적으로 모든 public 속성이 직렬화됩니다. 그중 일부 속성을 결과 JSON에 표시하지 않으려는 경우 사용할 수 있는 몇 가지 옵션이 있습니다. 이 문서에서는 다양한 조건을 기준으로 속성을 무시하는 방법을 알아봅니다.

::: zone pivot="dotnet-5-0"

* [개별 속성](#ignore-individual-properties)
* [모든 읽기 전용 속성](#ignore-all-read-only-properties)
* [모든 Null 값 속성](#ignore-all-null-value-properties)
* [모든 기본값 속성](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [개별 속성](#ignore-individual-properties)
* [모든 읽기 전용 속성](#ignore-all-read-only-properties)
* [모든 Null 값 속성](#ignore-all-null-value-properties)
::: zone-end

## <a name="ignore-individual-properties"></a>개별 속성 무시

개별 속성을 무시하려면 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성을 사용합니다.

다음은 직렬화 형식 및 JSON 출력의 예입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithIgnoreAttribute":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
[JsonIgnore](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성의 `Condition` 속성을 설정하여 조건부 제외를 지정할 수 있습니다. <xref:System.Text.Json.Serialization.JsonIgnoreCondition> 열거형은 다음 옵션을 제공합니다.

* `Always` - 속성이 항상 무시됩니다. `Condition`을 지정하지 않으면 이 옵션으로 간주됩니다.
* `Never` - `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` 및 `IgnoreReadOnlyFields` 전역 설정에 관계 없이 속성은 항상 직렬화 및 역직렬화됩니다.
* `WhenWritingDefault` - 속성이 참조 형식 `null`, null 허용 값 형식 `null` 또는 값 형식 `default`인 경우 직렬화 시 무시됩니다.
* `WhenWritingNull` - 속성이 참조 형식 `null` 또는 null 허용 값 형식 `null`인 경우 직렬화 시 무시됩니다.

다음 예는 [JsonIgnore](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성의 `Condition` 속성을 사용하는 방법을 보여 줍니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

## <a name="ignore-all-read-only-properties"></a>모든 읽기 전용 속성 무시

public setter가 아닌 public getter를 포함하는 속성은 읽기 전용입니다. 직렬화할 때 모든 읽기 전용 속성을 무시하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>을 `true`로 설정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs" id="Serialize":::

다음은 직렬화 형식 및 JSON 출력의 예입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithROProperty":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

이 옵션은 직렬화에만 적용됩니다. 역직렬화를 수행할 때 읽기 전용 속성은 기본적으로 무시됩니다.

::: zone pivot="dotnet-5-0"
이 옵션은 속성에만 적용됩니다. [필드를 직렬화](system-text-json-how-to.md#include-fields)할 때 읽기 전용 필드를 무시하려면 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 전역 설정을 사용합니다.
::: zone-end

## <a name="ignore-all-null-value-properties"></a>모든 Null 값 속성 무시

::: zone pivot="dotnet-5-0"
모든 Null 값 속성을 무시하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> 속성을 <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>로 설정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
직렬화할 때 모든 Null 값 속성을 무시하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 속성을 `true`로 설정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs" id="Serialize":::

다음은 직렬화 개체 및 JSON 출력의 예입니다.

| 속성             | 값                         |
|----------------------|-------------------------------|
| `Date`               | `8/1/2019 12:00:00 AM -07:00` |
| `TemperatureCelsius` | `25`                          |
| `Summary`            | `null`                        |

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

## <a name="ignore-all-default-value-properties"></a>모든 기본값 속성 무시

::: zone pivot="dotnet-5-0"
값 형식 속성에서 기본값의 직렬화를 방지하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> 속성을 <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>로 설정 합니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault> 설정은 null 값 참조 형식 및 null 허용 값 형식 속성의 직렬화도 방지합니다.

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1에서 `System.Text.Json`의 값 형식 기본값으로 속성의 직렬화를 방지하는 기본 제공 방법은 없습니다.
::: zone-end

## <a name="see-also"></a>참고 항목

* [System.Text.Json 개요](system-text-json-overview.md)
* [JsonSerializerOptions 인스턴스화](system-text-json-configure-options.md)
* [대/소문자를 구분하지 않는 일치를 사용하도록 설정](system-text-json-character-casing.md)
* [속성 이름 및 값 사용자 지정](system-text-json-customize-properties.md)
* [잘못된 JSON 허용](system-text-json-invalid-json.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [순환 참조 보존](system-text-json-preserve-references.md)
* [변경할 수 없는 형식 및 public이 아닌 접근자](system-text-json-immutability.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
