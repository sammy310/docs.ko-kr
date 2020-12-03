---
title: '호환성이 손상되는 변경: Deserialize에 단일 문자열이 필요함'
description: JsonSerializer.Deserialize에 단일 문자열이 필요한 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 10/18/2020
ms.openlocfilehash: 780f2928d776ecb6db9a7fc05a720e889eb363e7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759971"
---
# <a name="jsonserializerdeserialize-requires-single-character-string"></a>JsonSerializer.Deserialize에는 단일 문자열이 필요함

형식 매개 변수가 <xref:System.Char>인 경우 deserialization에 성공하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>의 문자열 인수에 단일 문자가 포함되어야 합니다.

## <a name="change-description"></a>변경 내용 설명

이전 .NET 버전에서 형식 매개 변수가 <xref:System.Char>인 경우 <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>에 다중 문자열을 전달하면 deserialization은 성공하지만 첫 번째 문자만 역직렬화됩니다.

.NET 5.0 이상에서 형식 매개 변수가 <xref:System.Char>인 경우 단일 문자열 이외의 값을 전달하면 <xref:System.Text.Json.JsonException>이 throw됩니다.

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a>도입된 버전

5.0

## <a name="reason-for-change"></a>변경 이유

<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>는 단일 JSON 값을 나타내는 텍스트를 제네릭 형식 매개 변수에 지정된 형식의 인스턴스로 구문 분석합니다. 제공한 페이로드가 지정된 제네릭 형식 매개 변수에 유효한 경우에만 구문 분석이 성공합니다. <xref:System.Char> 값 형식에 유효한 페이로드는 단일 문자열입니다.

## <a name="recommended-action"></a>권장 조치

<xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>을 사용하여 문자열을 <xref:System.Char> 형식으로 구문 분석하는 경우 문자열이 단일 문자로 구성되어 있는지 확인합니다.

## <a name="affected-apis"></a>영향을 받는 API

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
