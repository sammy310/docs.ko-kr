---
ms.openlocfilehash: c9547cdc2f127cf13a3610118a26736930fcd8bd
ms.sourcegitcommit: 348bb052d5cef109a61a3d5253faa5d7167d55ac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2020
ms.locfileid: "82021641"
---
### <a name="change-in-semantics-of-stringnull-in-utf8jsonwriter"></a><span data-ttu-id="85865-101">Utf8JsonWriter에서 `(string)null` 의미 체계 변경</span><span class="sxs-lookup"><span data-stu-id="85865-101">Change in semantics of `(string)null` in Utf8JsonWriter</span></span>

<span data-ttu-id="85865-102">.NET Core 3.0 미리 보기 7에서 null 문자열은 <xref:System.Text.Json.Utf8JsonWriter>에서 빈 문자열로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="85865-102">In .NET Core 3.0 Preview 7, the null string is treated as the empty string in <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="85865-103">.NET Core 3.0 미리 보기 8부터 null 문자열은 속성 이름으로 사용될 때 예외를 throw하고 값으로 사용될 때 JSON null 토큰을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="85865-103">Starting with .NET Core 3.0 Preview 8, the null string throws an exception when used as a property name, and it emits the JSON null token when used as a value.</span></span>

#### <a name="change-description"></a><span data-ttu-id="85865-104">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="85865-104">Change description</span></span>

<span data-ttu-id="85865-105">.Net Core 3.0 미리 보기 7에서는 `null` 문자열이 속성 이름을 쓸 때와 값을 쓸 때 모두 `""`로 처리되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85865-105">In .NET Core 3.0 Preview 7, the `null` string was treated as `""` both when writing property names and when writing values.</span></span>  

<span data-ttu-id="85865-106">.Net Core 3.0 미리 보기 8부터 `null` 속성 이름은 `ArgumentNullException`을 throw하고 `null` 값이 <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> 또는 <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>에 대한 호출로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="85865-106">Starting with .NET Core 3.0 Preview 8, a `null` property name throws an `ArgumentNullException`, and a `null` value is treated as a call to <xref:System.Text.Json.Utf8JsonWriter.WriteNull%2A?displayProperty=nameWithType> or <xref:System.Text.Json.Utf8JsonWriter.WriteNullValue?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="85865-107">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="85865-107">Consider the following code:</span></span>

```csharp
string propertyName1 = null;
string propertyValue1 = null;
string propertyName2 = "prop2";
string propertyValue2 = null;
string simpleValue1 = null;

using (Utf8JsonWriter writer = new Utf8JsonWriter(stream))
{
    writer.WriteStartArray();

    writer.WriteStartObject();
    writer.WriteString(propertyName1, propertyValue1);
    writer.WriteString(propertyName2, propertyValue2);
    writer.WriteEndObject();

    writer.WriteStringValue(simpleValue1);

    writer.WriteEndArray();
}
```

<span data-ttu-id="85865-108">.NET Core 3.0 미리 보기 7에서 실행하는 경우 작성기는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="85865-108">If run with .NET Core 3.0 Preview 7, the writer produces the following output:</span></span>

```js
[{"":"","prop2":""},""]
```

<span data-ttu-id="85865-109">.Net Core 3.0 미리 보기 8부터 `writer.WriteString(propertyName1, propertyValue1)`을 호출하면 <xref:System.ArgumentNullException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="85865-109">Starting with .NET Core 3.0 Preview 8, the call to `writer.WriteString(propertyName1, propertyValue1)` throws an <xref:System.ArgumentNullException>.</span></span>  <span data-ttu-id="85865-110">`propertyName1 = null`을 `propertyName1 = string.Empty`로 바꾸면 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="85865-110">If `propertyName1 = null` is replaced with `propertyName1 = string.Empty`, the output would now be:</span></span>

```js
[{"":null,"prop2":null},null]
```

<span data-ttu-id="85865-111">이 변경은 `null` 값에 대한 호출자의 기대에 더 부합하도록 실시된 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85865-111">This change was made to better align with caller expectations for `null` values.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="85865-112">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="85865-112">Version introduced</span></span>

<span data-ttu-id="85865-113">3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="85865-113">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="85865-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="85865-114">Recommended action</span></span>

<span data-ttu-id="85865-115"><xref:System.Text.Json.Utf8JsonWriter> 클래스를 사용하여 속성 이름 및 값을 쓸 때</span><span class="sxs-lookup"><span data-stu-id="85865-115">When writing property names and values with the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

- <span data-ttu-id="85865-116">비 `null` 문자열이 속성 이름으로 사용되는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85865-116">Ensure non-`null` strings are used as property names.</span></span>

- <span data-ttu-id="85865-117">이전 동작이 필요한 경우 null 병합 호출(예: `writer.WriteString(propertyName1 ?? "", propertyValue1)`)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="85865-117">If the previous behavior is desired, use a null coalescing invocation; for example, `writer.WriteString(propertyName1 ?? "", propertyValue1)`.</span></span>

- <span data-ttu-id="85865-118">`null` 문자열 값에 `null` 리터럴을 쓰는 것이 바람직하지 않은 경우 null 결합 호출(예: `writer.WriteString(propertyName2, propertyValue2 ?? "")`)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="85865-118">If writing a `null` literal for a `null` string value is not desirable, use a null coalescing invocation; for example, `writer.WriteString(propertyName2, propertyValue2 ?? "")`.</span></span>

#### <a name="category"></a><span data-ttu-id="85865-119">범주</span><span class="sxs-lookup"><span data-stu-id="85865-119">Category</span></span>

<span data-ttu-id="85865-120">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="85865-120">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="85865-121">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="85865-121">Affected APIs</span></span>

- <xref:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Byte%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan%7BSystem.Char%7D)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)?displayProperty=nameWithType>
- <xref:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Text.Json.Utf8JsonWriter.WriteBase64String(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteBoolean(System.String,System.Boolean)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNull(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Int64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt32)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.UInt64)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Single)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Double)`
- `M:System.Text.Json.Utf8JsonWriter.WriteNumber(System.String,System.Decimal)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartArray(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStartObject(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Byte})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.ReadOnlySpan{System.Char})`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Text.Json.JsonEncodedText)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTime)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.DateTimeOffset)`
- `M:System.Text.Json.Utf8JsonWriter.WriteString(System.String,System.Guid)`
- `M:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)`
- `M:System.Text.Json.Utf8JsonWriter.WritePropertyName(System.String)`

-->
