---
title: '호환성이 손상되는 변경: 형식 매개 변수가 null인 경우 Serialize에서 예외를 throw함'
description: 형식 매개 변수가 있는 JsonSerialize serialization 메서드가 해당 매개 변수에 대해 Null이 전달될 때마다 예외를 throw하는 .NET 5의 호환성이 손상되는 변경에 관해 알아봅니다.
ms.date: 10/18/2020
ms.openlocfilehash: 81b3b754c11599eea435c750f1386fcaa2f0b54d
ms.sourcegitcommit: 9c589b25b005b9a7f87327646020eb85c3b6306f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "102256298"
---
# <a name="jsonserializerserialize-throws-argumentnullexception-when-type-parameter-is-null"></a><span data-ttu-id="89c7f-103">형식 매개 변수가 null인 경우 JsonSerializer.Serialize에서 ArgumentNullException을 throw함</span><span class="sxs-lookup"><span data-stu-id="89c7f-103">JsonSerializer.Serialize throws ArgumentNullException when type parameter is null</span></span>

<span data-ttu-id="89c7f-104"><xref:System.Type> 형식의 매개 변수가 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType> 및 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 오버로드는 해당 매개 변수에 대해 `null`이 전달될 때마다 <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="89c7f-104"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> overloads that have a parameter of type <xref:System.Type> now throw an <xref:System.ArgumentNullException> whenever `null` is passed for that parameter.</span></span>

## <a name="change-description"></a><span data-ttu-id="89c7f-105">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="89c7f-105">Change description</span></span>

<span data-ttu-id="89c7f-106">.NET Core 3.1에서 <xref:System.Type> 매개 변수가 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> 오버로드는 `Type inputType` 매개 변수에 대해 `null`이 전달될 때 <xref:System.ArgumentNullException>을 throw하지만 `Object value` 매개 변수도 `null`인 경우에는 예외를 throw하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89c7f-106">In .NET Core 3.1, the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType>, <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=nameWithType>, and <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=nameWithType> overloads that have a <xref:System.Type> parameter throw an <xref:System.ArgumentNullException> when `null` is passed for the `Type inputType` parameter, but not if the `Object value` parameter is also `null`.</span></span> <span data-ttu-id="89c7f-107">.NET 5부터 해당 메서드는 <xref:System.Type> 매개 변수에 대해 `null`이 전달될 때 ‘항상’ <xref:System.ArgumentNullException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="89c7f-107">Starting in .NET 5, these methods *always* throw an <xref:System.ArgumentNullException> when `null` is passed for the <xref:System.Type> parameter.</span></span>

<span data-ttu-id="89c7f-108">.NET Core 3.1의 동작:</span><span class="sxs-lookup"><span data-stu-id="89c7f-108">Behavior in .NET Core 3.1:</span></span>

```csharp
// Returns a string with value "null".
JsonSerializer.Serialize(null, null);

// Returns a byte array with value "null".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

<span data-ttu-id="89c7f-109">.NET 5 이상의 동작:</span><span class="sxs-lookup"><span data-stu-id="89c7f-109">Behavior in .NET 5 and later:</span></span>

```csharp
// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.Serialize(null, null);

// Throws ArgumentNullException: "Value cannot be null. (Parameter 'inputType')".
JsonSerializer.SerializeToUtf8Bytes(null, null);
```

## <a name="version-introduced"></a><span data-ttu-id="89c7f-110">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="89c7f-110">Version introduced</span></span>

<span data-ttu-id="89c7f-111">5.0</span><span class="sxs-lookup"><span data-stu-id="89c7f-111">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="89c7f-112">변경 이유</span><span class="sxs-lookup"><span data-stu-id="89c7f-112">Reason for change</span></span>

<span data-ttu-id="89c7f-113">`Type inputType` 매개 변수에 대해 `null`을 전달할 수 없으며 항상 <xref:System.ArgumentNullException>이 throw되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89c7f-113">Passing in `null` for the `Type inputType` parameter is unacceptable and should always throw an <xref:System.ArgumentNullException>.</span></span>

## <a name="recommended-action"></a><span data-ttu-id="89c7f-114">권장 조치</span><span class="sxs-lookup"><span data-stu-id="89c7f-114">Recommended action</span></span>

<span data-ttu-id="89c7f-115">해당 메서드의 `Type inputType` 매개 변수에 대해 `null`을 전달하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89c7f-115">Make sure that you are not passing `null` for the `Type inputType` parameter of these methods.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="89c7f-116">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="89c7f-116">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)?displayProperty=fullName>

<!--

### Affected APIs

- `M:System.Text.Json.JsonSerializer.Serialize(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.Serialize(System.Text.Json.Utf8JsonWriter,System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`
- `M:System.Text.Json.JsonSerializer.SerializeAsync(System.IO.Stream,System.Object,System.Type,System.Text.Json.JsonSerializerOptions,System.Threading.CancellationToken)`
- `M:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes(System.Object,System.Type,System.Text.Json.JsonSerializerOptions)`

### Category

Serialization

-->
