---
ms.openlocfilehash: 5b49dcae45e44bfd9ec3e150ad25c3f21d62c18e
ms.sourcegitcommit: b59237ca4ec763969a0dd775a3f8f39f8c59fe24
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2020
ms.locfileid: "91955341"
---
### <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="14dd4-101">형식 매개 변수가 null인 경우 JsonSerializer.Serialize에서 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="14dd4-101">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="14dd4-102"><xref:System.Type> 매개 변수가 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 오버로드는 <xref:System.Type> 매개 변수에 대해 `null`이 전달될 때마다 이제 <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd4-102"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter now throw an <xref:System.ArgumentNullException> whenever `null` is passed for the <xref:System.Type> parameter.</span></span>

#### <a name="change-description"></a><span data-ttu-id="14dd4-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="14dd4-103">Change description</span></span>

<span data-ttu-id="14dd4-104">.NET Core 3.1에서 <xref:System.Type> 매개 변수가 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> 오버로드는 `Type inputType` 매개 변수에 대해 `null`이 전달될 때 <xref:System.ArgumentNullException>을 throw하지만 `Object value` 매개 변수도 `null`인 경우에는 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14dd4-104">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="14dd4-105">.NET 5.0부터 해당 메서드는 <xref:System.Type> 매개 변수에 대해 `null`이 전달될 때 ‘항상’ <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd4-105">Starting in .NET 5.0, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="14dd4-106">.NET Core 3.1의 동작:</span><span class="sxs-lookup"><span data-stu-id="14dd4-106">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="14dd4-107">.NET 5.0 이상의 동작:</span><span class="sxs-lookup"><span data-stu-id="14dd4-107">Behavior in .NET 5.0 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

#### <a name="version-introduced"></a><span data-ttu-id="14dd4-108">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="14dd4-108">Version introduced</span></span>

<span data-ttu-id="14dd4-109">5.0</span><span class="sxs-lookup"><span data-stu-id="14dd4-109">5.0</span></span>

#### <a name="reason-for-change"></a><span data-ttu-id="14dd4-110">변경 이유</span><span class="sxs-lookup"><span data-stu-id="14dd4-110">Reason for change</span></span>

<span data-ttu-id="14dd4-111">`Type inputType` 매개 변수에 대해 `null`을 전달할 수 없으며 항상 <xref:System.ArgumentNullException>이 throw되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="14dd4-111">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="14dd4-112">권장 조치</span><span class="sxs-lookup"><span data-stu-id="14dd4-112">Recommended action</span></span>

<span data-ttu-id="14dd4-113">해당 메서드의 `Type inputType` 매개 변수에 대해 `null`을 전달하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="14dd4-113">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

#### <a name="category"></a><span data-ttu-id="14dd4-114">범주</span><span class="sxs-lookup"><span data-stu-id="14dd4-114">Category</span></span>

<span data-ttu-id="14dd4-115">Serialization</span><span class="sxs-lookup"><span data-stu-id="14dd4-115">Serialization</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="14dd4-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="14dd4-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

#### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

-->
