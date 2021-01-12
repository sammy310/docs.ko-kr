---
title: '호환성이 손상되는 변경: Char 역직렬화에 단일 문자열이 필요함'
description: Char 대상으로 역직렬화할 때 System.Text.Json에서 JSON에 단일 문자 문자열이 필요한 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 12/15/2020
ms.openlocfilehash: 39a2d25b00bf8855cfbf46a4d78b8545052703e5
ms.sourcegitcommit: 635a0ff775d2447a81ef7233a599b8f88b162e5d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/17/2020
ms.locfileid: "97633873"
---
# <a name="systemtextjson-requires-single-char-string-to-deserialize-a-char"></a><span data-ttu-id="528a9-103">Char를 역직렬화하기 위해 System.Text.Json에 단일 문자 문자열 필요</span><span class="sxs-lookup"><span data-stu-id="528a9-103">System.Text.Json requires single-char string to deserialize a char</span></span>

<span data-ttu-id="528a9-104"><xref:System.Text.Json>을 사용하여 <xref:System.Char>를 역직렬화하려면 JSON 문자열에 단일 문자가 포함되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="528a9-104">To successfully deserialize a <xref:System.Char> using <xref:System.Text.Json>, the JSON string must contain a single character.</span></span>

## <a name="change-description"></a><span data-ttu-id="528a9-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="528a9-105">Change description</span></span>

<span data-ttu-id="528a9-106">이전 .NET 버전에서는 JSON의 다중 `char` 문자열이 `char` 속성 또는 필드로 역직렬화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="528a9-106">In previous .NET versions, a multi-`char` string in the JSON is successfully deserialized to a `char` property or field.</span></span> <span data-ttu-id="528a9-107">다음 예제와 같이 문자열의 첫 번째 `char`만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="528a9-107">Only the first `char` of the string is used, as in the following example:</span></span>

```csharp
// .NET Core 3.0 and 3.1: Returns the first char 'a'.
// .NET 5.0 and later: Throws JsonException because payload has more than one char.
char deserializedChar = JsonSerializer.Deserialize<char>("\"abc\"");
```

<span data-ttu-id="528a9-108">.NET 5.0 이상에서는 역직렬화 대상이 `char`인 경우 단일 `char` 문자열 이외의 모든 항목은 <xref:System.Text.Json.JsonException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="528a9-108">In .NET 5.0 and later, anything other than a single-`char` string causes a <xref:System.Text.Json.JsonException> to be thrown when the deserialization target is a `char`.</span></span> <span data-ttu-id="528a9-109">다음 예제 문자열은 모든 .NET 버전에서 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="528a9-109">The following example string is successfully deserialized in all .NET versions:</span></span>

```csharp
// Correct usage.
char deserializedChar = JsonSerializer.Deserialize<char>("\"a\"");
```

## <a name="version-introduced"></a><span data-ttu-id="528a9-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="528a9-110">Version introduced</span></span>

<span data-ttu-id="528a9-111">5.0</span><span class="sxs-lookup"><span data-stu-id="528a9-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="528a9-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="528a9-112">Reason for change</span></span>

<span data-ttu-id="528a9-113">역직렬화의 구문 분석은 제공된 페이로드가 대상 유형에 유효한 경우에만 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="528a9-113">Parsing for deserialization should only succeed when the provided payload is valid for the target type.</span></span> <span data-ttu-id="528a9-114">`char` 형식의 경우 유효한 페이로드는 단일 `char` 문자열뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="528a9-114">For a `char` type, the only valid payload is a single-`char` string.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="528a9-115">권장 조치</span><span class="sxs-lookup"><span data-stu-id="528a9-115">Recommended action</span></span>

<span data-ttu-id="528a9-116">JSON을 `char` 대상으로 역직렬화할 때 문자열이 단일 `char`으로 구성되어 있는지 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="528a9-116">When you deserialize JSON into a `char` target, make sure the string consists of a single `char`.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="528a9-117">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="528a9-117">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Deserialize`

### Category

Serialization

-->
