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
# <a name="jsonserializerdeserialize-requires-single-character-string"></a><span data-ttu-id="d8b27-103">JsonSerializer.Deserialize에는 단일 문자열이 필요함</span><span class="sxs-lookup"><span data-stu-id="d8b27-103">JsonSerializer.Deserialize requires single-character string</span></span>

<span data-ttu-id="d8b27-104">형식 매개 변수가 <xref:System.Char>인 경우 deserialization에 성공하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>의 문자열 인수에 단일 문자가 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-104">When the type parameter is <xref:System.Char>, the string argument to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> must contain a single character for deserialization to succeed.</span></span>

## <a name="change-description"></a><span data-ttu-id="d8b27-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="d8b27-105">Change description</span></span>

<span data-ttu-id="d8b27-106">이전 .NET 버전에서 형식 매개 변수가 <xref:System.Char>인 경우 <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>에 다중 문자열을 전달하면 deserialization은 성공하지만 첫 번째 문자만 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-106">In previous .NET versions, if you pass a multi-character string to <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> and the type parameter is <xref:System.Char>, the deserialization succeeds and only the first character is deserialized.</span></span>

<span data-ttu-id="d8b27-107">.NET 5.0 이상에서 형식 매개 변수가 <xref:System.Char>인 경우 단일 문자열 이외의 값을 전달하면 <xref:System.Text.Json.JsonException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-107">In .NET 5.0 and later, when the type parameter is <xref:System.Char>, passing anything other than a single-character string causes a <xref:System.Text.Json.JsonException> to be thrown.</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first character 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one character.
JsonSerializer.Deserialize<char>("\"abc\"");

// Correct usage.
JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a><span data-ttu-id="d8b27-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="d8b27-108">Version introduced</span></span>

<span data-ttu-id="d8b27-109">5.0</span><span class="sxs-lookup"><span data-stu-id="d8b27-109">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="d8b27-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="d8b27-110">Reason for change</span></span>

<span data-ttu-id="d8b27-111"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>는 단일 JSON 값을 나타내는 텍스트를 제네릭 형식 매개 변수에 지정된 형식의 인스턴스로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-111"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> parses text that represents a single JSON value into an instance of the type specified by the generic type parameter.</span></span> <span data-ttu-id="d8b27-112">제공한 페이로드가 지정된 제네릭 형식 매개 변수에 유효한 경우에만 구문 분석이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-112">Parsing should only succeed when the provided payload is valid for the specified generic type parameter.</span></span> <span data-ttu-id="d8b27-113"><xref:System.Char> 값 형식에 유효한 페이로드는 단일 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-113">For a <xref:System.Char> value type, a valid payload is a single character string.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="d8b27-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="d8b27-114">Recommended action</span></span>

<span data-ttu-id="d8b27-115"><xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>을 사용하여 문자열을 <xref:System.Char> 형식으로 구문 분석하는 경우 문자열이 단일 문자로 구성되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d8b27-115">When parsing a string into a <xref:System.Char> type using <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType>, make sure the string consists of a single character.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="d8b27-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d8b27-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%60%601(System.String,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Deserialize``1(System.String,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
