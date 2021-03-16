---
title: '호환성이 손상되는 변경: Char 역직렬화에 단일 문자열이 필요함'
description: Char 대상으로 역직렬화할 때 System.Text.Json에서 JSON에 단일 문자 문자열이 필요한 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 12/15/2020
ms.openlocfilehash: e901f8ee7e7521af948a3bcde5cf969640436f7f
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256337"
---
# <a name="systemtextjson-requires-single-char-string-to-deserialize-a-char"></a>Char를 역직렬화하기 위해 System.Text.Json에 단일 문자 문자열 필요

<xref:System.Text.Json>을 사용하여 <xref:System.Char>를 역직렬화하려면 JSON 문자열에 단일 문자가 포함되어 있어야 합니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서는 JSON의 다중 `char` 문자열이 `char` 속성 또는 필드로 역직렬화되었습니다. 다음 예제와 같이 문자열의 첫 번째 `char`만 사용됩니다.

```csharp
// .NET Core 3.0 and 3.1: Returns the first char 'a'.
// .NET 5 and later: Throws JsonException because payload has more than one char.
char deserializedChar = JsonSerializer.Deserialize<char>("\"abc\"");
```

.NET 5 이상에서는 deserialization 대상이 `char`인 경우 단일 `char` 문자열 이외의 모든 항목은 <xref:System.Text.Json.JsonException>을 throw합니다. 다음 예제 문자열은 모든 .NET 버전에서 역직렬화됩니다.

```csharp
// Correct usage.
char deserializedChar = JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="reason-for-change"></a>변경 이유

역직렬화의 구문 분석은 제공된 페이로드가 대상 유형에 유효한 경우에만 성공합니다. `char` 형식의 경우 유효한 페이로드는 단일 `char` 문자열뿐입니다.

## <a name="recommended-action"></a>권장 조치

JSON을 `char` 대상으로 역직렬화할 때 문자열이 단일 `char`으로 구성되어 있는지 확인하세요.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`

### Category

Serialization

-->
