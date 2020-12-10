---
title: System.Text.Json으로 대/소문자를 구분하지 않는 이름 일치를 사용하는 방법
description: .NET에서 JSON으로 직렬화하고 JSON에서 역직렬화할 때 대/소문자를 구분하지 않는 속성 이름 일치를 사용하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 2d663ac8c1c15d61959a62c40d9a3b0993484032
ms.sourcegitcommit: 9d525bb8109216ca1dc9e39c149d4902f4b43da5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "96599078"
---
# <a name="how-to-enable-case-insensitive-property-name-matching-with-no-locsystemtextjson"></a>System.Text.Json으로 대/소문자를 구분하지 않는 이름 일치를 사용하는 방법

이 문서에서는 `System.Text.Json` 네임스페이스로 대/소문자를 구분하지 않는 속성 이름 일치를 사용하는 방법을 알아봅니다.

## <a name="case-insensitive-property-matching"></a>대/소문자를 구분하지 않는 속성 매칭

기본적으로 역직렬화는 JSON과 대상 개체 속성 간에 일치하는 대/소문자 구분 속성 이름을 찾습니다. 이 동작을 변경하려면 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType>을 `true`로 설정합니다.

> [!NOTE]
> [웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)은 대/소문자 구분 안 함입니다.

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs" id="Deserialize":::

다음은 카멜식 대/소문자 속성 이름을 사용하는 JSON 예제입니다. 파스칼식 대/소문자 속성 이름을 사용하는 다음 형식으로 역직렬화할 수 있습니다.

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="see-also"></a>참고 항목

* [System.Text.Json 개요](system-text-json-overview.md)
* [JsonSerializerOptions 인스턴스화](system-text-json-configure-options.md)
* [속성 이름 및 값 사용자 지정](system-text-json-customize-properties.md)
* [속성 무시](system-text-json-ignore-properties.md)
* [잘못된 JSON 허용](system-text-json-invalid-json.md)
* [오버플로 JSON 처리](system-text-json-handle-overflow.md)
* [순환 참조 보존](system-text-json-preserve-references.md)
* [변경할 수 없는 형식 및 public이 아닌 접근자](system-text-json-immutability.md)
* [다형 직렬화](system-text-json-polymorphism.md)
* [System.Text.Json API 참조](xref:System.Text.Json)
