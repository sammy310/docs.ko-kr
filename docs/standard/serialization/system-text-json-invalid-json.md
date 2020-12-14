---
title: System.Text.Json을 사용하여 일부 잘못된 종류의 JSON을 허용하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 주석, 후행 쉼표, 따옴표 붙은 숫자를 허용하는 방법을 알아봅니다.
ms.date: 12/03/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2559b081010fb0a2fa208b121cb095efdeb8da2e
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97009811"
---
# <a name="how-to-allow-some-kinds-of-invalid-json-with-no-locsystemtextjson"></a>System.Text.Json을 사용하여 일부 잘못된 종류의 JSON을 허용하는 방법

이 문서에서는 JSON에서 주석, 후행 쉼표, 따옴표 붙은 숫자를 허용하는 방법과 숫자를 문자열로 쓰는 방법을 알아봅니다.

## <a name="allow-comments-and-trailing-commas"></a>주석과 후행 쉼표 허용

기본적으로 주석과 후행 쉼표는 JSON에서 허용되지 않습니다. JSON에서 주석을 허용하려면 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 속성을 `JsonCommentHandling.Skip`으로 설정합니다.
그리고 후행 쉼표를 허용하려면 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 속성을 `true`로 설정합니다. 다음 예제에서는 주석과 후행 쉼표를 허용하는 방법을 보여줍니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs" id="Deserialize":::

다음은 주석과 후행 쉼표를 사용하는 JSON 예제입니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
  // Comments on
  /* separate lines */
}
```

## <a name="allow-or-write-numbers-in-quotes"></a>따옴표 안에 숫자를 허용하거나 씁니다.

::: zone pivot="dotnet-5-0"

일부 직렬 변환기는 숫자를 JSON 문자열로 인코딩합니다(따옴표로 묶음).

예:

```json
{
    "DegreesCelsius": "23"
}
```

다음 식을 사용하는 대신

```json
{
    "DegreesCelsius": 23
}
```

전체 입력 개체 그래프에서 따옴표 안의 숫자를 직렬화하거나 따옴표 안의 숫자를 허용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType>을 설정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-29":::

ASP.NET Core를 통해 간접적으로 `System.Text.Json`을 사용하는 경우 ASP.NET Core가 [웹 기본 옵션](xref:System.Text.Json.JsonSerializerDefaults.Web)을 지정하기 때문에 역직렬화할 때 따옴표 붙은 숫자가 허용됩니다.

특정 속성, 필드 또는 형식에 따옴표 붙은 숫자를 허용하거나 쓰려면 [JsonNumberHandling](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) 특성을 사용합니다.
::: zone-end

::: zone pivot="dotnet-core-3-1"
.NET Core 3.1에서 `System.Text.Json`은 따옴표로 묶은 숫자의 직렬화 또는 역직렬화를 지원하지 않습니다. 자세한 내용은 [따옴표 안의 숫자 허용 또는 쓰기](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes)를 참조하세요.
::: zone-end

## <a name="see-also"></a>참고 항목

* [System.Text.Json 개요](system-text-json-overview.md)
* [JSON 직렬화 및 역직렬화 방법](system-text-json-how-to.md)
* [JsonSerializerOptions 인스턴스 인스턴스화](system-text-json-configure-options.md)
* [대/소문자를 구분하지 않는 일치를 사용하도록 설정](system-text-json-character-casing.md)
* [속성 이름 및 값 사용자 지정](system-text-json-customize-properties.md)
* [속성 무시](system-text-json-ignore-properties.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [참조 유지](system-text-json-preserve-references.md)
* [변경할 수 없는 형식 및 public이 아닌 접근자](system-text-json-immutability.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [Newtonsoft.Json에서 System.Text.Json으로 마이그레이션](system-text-json-migrate-from-newtonsoft-how-to.md)
* [문자 인코딩 사용자 지정](system-text-json-character-encoding.md)
* [사용자 지정 직렬 변환기 및 역직렬 변환기 작성](write-custom-serializer-deserializer.md)
* [JSON serialization용 사용자 지정 변환기 작성](system-text-json-converters-how-to.md)
* [DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
* [System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)
