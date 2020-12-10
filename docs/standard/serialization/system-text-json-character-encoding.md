---
title: System.Text.Json을 사용하여 문자 인코딩을 사용자 지정하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 문자 인코딩을 사용자 지정하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: f6a50a3ca2a5e871294cf7c056cbf197a61cd668
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439863"
---
# <a name="how-to-customize-character-encoding-with-no-locsystemtextjson"></a>System.Text.Json을 사용하여 문자 인코딩을 사용자 지정하는 방법

기본적으로 직렬 변환기는 ASCII가 아닌 문자를 모두 이스케이프합니다. 즉, ASCII가 아닌 문자를 `\uxxxx`로 바꾸며, 여기서 `xxxx`는 문자의 유니코드 코드입니다. 예를 들어 다음 JSON의 `Summary` 속성이 키릴 자모 `жарко`로 설정된 경우 다음 예제와 같이 `WeatherForecast` 개체가 직렬화됩니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

## <a name="serialize-language-character-sets"></a>언어 문자 세트 직렬화

하나 이상의 언어 문자 세트를 이스케이프하지 않고 직렬화하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> 인스턴스를 만들 때 [유니코드 범위](xref:System.Text.Unicode.UnicodeRanges)를 지정합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="LanguageSets":::

이 코드는 키릴 자모 또는 그리스어 문자를 이스케이프하지 않습니다. `Summary` 속성이 키릴 자모 `жарко`로 설정된 경우 다음 예제와 같이 `WeatherForecast` 개체가 직렬화됩니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

모든 언어 세트를 이스케이프하지 않고 직렬화하려면 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>을 사용합니다.

## <a name="serialize-specific-characters"></a>특정 문자 직렬화

이스케이프하지 않고 허용하려는 개별 문자를 지정하는 방법도 있습니다. 다음 예제는 `жарко`의 처음 두 문자만 직렬화합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="SelectedCharacters":::

다음은 이전 코드에서 생성된 JSON 예제입니다.

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

## <a name="serialize-all-characters"></a>모든 문자 직렬화

이스케이프를 최소화하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>을 사용합니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="Usings":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs" id="UnsafeRelaxed":::

> [!CAUTION]
> 기본 인코더와 비교할 때, `UnsafeRelaxedJsonEscaping` 인코더는 문자를 이스케이프하지 않은 상태로 통과할 수 있도록 허용하는 기준이 더 관대합니다.
>
> * `<`, `>`, `&` 및 `'`처럼 HTML 구분 문자를 이스케이프하지 않습니다.
> * *문자 세트* 에 대한 클라이언트와 서버의 내용이 서로 다를 때 발생할 수 있는 XSS 또는 정보 노출 공격에 대한 심층 방어를 추가로 제공하지 않습니다.
>
> 클라이언트가 결과 페이로드를 UTF-8로 인코딩된 JSON으로 해석한다는 사실을 알고 있는 경우에만 안전하지 않은 인코더를 사용해야 합니다. 예를 들어 서버에서 응답 헤더 `Content-Type: application/json; charset=utf-8`을 보내는 경우에 사용할 수 있습니다. 원시 `UnsafeRelaxedJsonEscaping` 출력을 HTML 페이지나 `<script>` 요소로 내보내도록 허용하면 절대 안 됩니다.

## <a name="see-also"></a>참고 항목

* [System.Text.Json 개요](system-text-json-overview.md)
* [사용자 지정 직렬 변환기 및 역직렬 변환기를 작성하는 방법](write-custom-serializer-deserializer.md)
* [JSON 직렬화용 사용자 지정 변환기를 작성하는 방법](system-text-json-converters-how-to.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
