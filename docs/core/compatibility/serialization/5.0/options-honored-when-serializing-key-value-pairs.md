---
title: '호환성이 손상되는 변경: PropertyNamingPolicy, PropertyNameCaseInsensitive 및 Encoder 옵션이 키-값 쌍에 적용됨'
description: 키-값 쌍 인스턴스의 Key 및 Value 속성 이름을 직렬화하고 역직렬화할 때 PropertyNamingPolicy, PropertyNameCaseInsensitive 및 Encoder 옵션이 적용되는 .NET 5.0의 호환성이 손상되는 변경에 대해 알아봅니다.
ms.date: 10/18/2020
ms.openlocfilehash: 5d75cb7feea32cc4b942e5261c5b609e00a5082c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95759942"
---
# <a name="propertynamingpolicy-propertynamecaseinsensitive-and-encoder-options-are-honored-when-serializing-and-deserializing-key-value-pairs"></a><span data-ttu-id="ffcbc-103">PropertyNamingPolicy, PropertyNameCaseInsensitive 및 Encoder 옵션은 키-값 쌍을 직렬화 및 역직렬화할 때 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-103">PropertyNamingPolicy, PropertyNameCaseInsensitive, and Encoder options are honored when serializing and deserializing key-value pairs</span></span>

<span data-ttu-id="ffcbc-104"><xref:System.Text.Json.JsonSerializer>는 이제 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스의 <xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 속성 이름을 직렬화할 때 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 및 <xref:System.Text.Json.JsonSerializerOptions.Encoder> 옵션을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-104"><xref:System.Text.Json.JsonSerializer> now honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options when serializing the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names of a <xref:System.Collections.Generic.KeyValuePair%602> instance.</span></span> <span data-ttu-id="ffcbc-105">또한 <xref:System.Text.Json.JsonSerializer>는 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스를 역직렬화할 때 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 및 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> 옵션을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-105">Additionally, <xref:System.Text.Json.JsonSerializer> honors the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options when deserializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span>

## <a name="change-description"></a><span data-ttu-id="ffcbc-106">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="ffcbc-106">Change description</span></span>

### <a name="serialization"></a><span data-ttu-id="ffcbc-107">Serialization</span><span class="sxs-lookup"><span data-stu-id="ffcbc-107">Serialization</span></span>

<span data-ttu-id="ffcbc-108">.NET Core 3.x 버전 및 [System.Text.Json NuGet 패키지](https://www.nuget.org/packages/System.Text.Json)의 4.6.0-4.7.2 버전에서는 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 및 <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> 옵션에 관계없이 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스의 속성은 항상 "Key" 및 "Value"로 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-108">In .NET Core 3.x versions and in the 4.6.0-4.7.2 versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), the properties of <xref:System.Collections.Generic.KeyValuePair%602> instances are always serialized as "Key" and "Value" exactly, regardless of any <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> and <xref:System.Text.Json.JsonSerializerOptions.Encoder?displayProperty=nameWithType> options.</span></span> <span data-ttu-id="ffcbc-109">다음 코드 예제는 지정된 특성 이름 지정 정책이 지시하더라도 직렬화 후에는 <xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 특성이 어떻게 카멜식 대/소문자를 구분하지 *않는지* 를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-109">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are *not* camel-cased after serialization, even though the specified property-naming policy dictates so.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// Expected: {"key":1,"value":1}
// Actual: {"Key":1,"Value":1}
```

<span data-ttu-id="ffcbc-110">.NET 5.0부터 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스를 직렬화할 때 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 및 <xref:System.Text.Json.JsonSerializerOptions.Encoder> 옵션이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-110">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are honored when serializing <xref:System.Collections.Generic.KeyValuePair%602> instances.</span></span> <span data-ttu-id="ffcbc-111">다음 코드 예제는 지정된 특성 이름 지정 정책에 따라 직렬화 후 <xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 특성이 어떻게 카멜식 대/소문자를 구분하는지 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-111">The following code example shows how the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> properties are camel-cased after serialization, in accordance with the specified property-naming policy.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
KeyValuePair<int, int> kvp = KeyValuePair.Create(1, 1);
Console.WriteLine(JsonSerializer.Serialize(kvp, options));
// {"key":1,"value":1}
```

### <a name="deserialization"></a><span data-ttu-id="ffcbc-112">Deserialization</span><span class="sxs-lookup"><span data-stu-id="ffcbc-112">Deserialization</span></span>

<span data-ttu-id="ffcbc-113">.NET Core 3.x 버전과 [System.Text.Json NuGet 패키지](https://www.nuget.org/packages/System.Text.Json)의 4.7.x 버전에서는, 예를 들어 대문자로 시작하지 않고 JSON 속성 이름이 정확하게 `Key` 및 `Value`가 아닌 경우 <xref:System.Text.Json.JsonException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-113">In .NET Core 3.x versions and in the 4.7.x versions of the [System.Text.Json NuGet package](https://www.nuget.org/packages/System.Text.Json), a <xref:System.Text.Json.JsonException> is thrown when the JSON property names are not precisely `Key` and `Value`, for example, if they don't start with an uppercase letter.</span></span> <span data-ttu-id="ffcbc-114">지정된 자산 이름 지정 정책이 명시적으로 허용하더라도 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-114">The exception is thrown even if a specified property-naming policy expressly permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";
// Throws JsonException.
JsonSerializer.Deserialize<KeyValuePair<int, int>>(json, options);
```

<span data-ttu-id="ffcbc-115">.NET 5.0부터 <xref:System.Text.Json.JsonSerializer>를 사용하여 역직렬화할 때 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 및 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> 옵션이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-115">Starting in .NET 5.0, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> and <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> options are honored when deserializing using <xref:System.Text.Json.JsonSerializer>.</span></span> <span data-ttu-id="ffcbc-116">예를 들어, 다음 코드 조각은 지정된 속성 이름 지정 정책에서 허용하기 때문에 소문자의 <xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 속성 이름을 성공적으로 역직렬화하는 것을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-116">For example, the following code snippet shows successful deserialization of lowercased <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names because the specified property-naming policy permits it.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""key"":1,""value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

<span data-ttu-id="ffcbc-117">이전 버전으로 직렬화된 페이로드를 수용하기 위해 역직렬화할 때 일치하도록 "Key" 및 "Value"는 특수 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-117">To accommodate payloads that were serialized with previous versions, "Key" and "Value" are special-cased to match when deserializing.</span></span> <span data-ttu-id="ffcbc-118"><xref:System.Collections.Generic.KeyValuePair%602.Key> 및 <xref:System.Collections.Generic.KeyValuePair%602.Value> 속성 이름이 다음 코드 예제의 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> 옵션에 따라 카멜식 대/소문자를 구분하지 않더라도 성공적으로 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-118">Even though the <xref:System.Collections.Generic.KeyValuePair%602.Key> and <xref:System.Collections.Generic.KeyValuePair%602.Value> property names aren't camel-cased according to the in <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> option in the following code example, they deserialize successfully.</span></span>

```csharp
var options = new JsonSerializerOptions { PropertyNamingPolicy = JsonNamingPolicy.CamelCase };
string json = @"{""Key"":1,""Value"":1}";

KeyValuePair<int, int> kvp = JsonSerializer.Deserialize<KeyValuePair<int, int>>(json);
Console.WriteLine(kvp.Key); // 1
Console.WriteLine(kvp.Value); // 1
```

## <a name="version-introduced"></a><span data-ttu-id="ffcbc-119">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="ffcbc-119">Version introduced</span></span>

<span data-ttu-id="ffcbc-120">5.0</span><span class="sxs-lookup"><span data-stu-id="ffcbc-120">5.0</span></span>

## <a name="reason-for-change"></a><span data-ttu-id="ffcbc-121">변경 이유</span><span class="sxs-lookup"><span data-stu-id="ffcbc-121">Reason for change</span></span>

<span data-ttu-id="ffcbc-122">상당한 고객 피드백에서 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy>를 적용해야 한다고 나타났습니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-122">Substantial customer feedback indicated that the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy> should be honored.</span></span> <span data-ttu-id="ffcbc-123">완전성을 위해 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> 및 <xref:System.Text.Json.JsonSerializerOptions.Encoder> 옵션도 적용되므로 <xref:System.Collections.Generic.KeyValuePair%602> 인스턴스는 다른 POCO(Plain Old CLR Object)와 동일하게 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-123">For completeness, the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive> and <xref:System.Text.Json.JsonSerializerOptions.Encoder> options are also honored, so that <xref:System.Collections.Generic.KeyValuePair%602> instances are treated the same as any other plain old CLR object (POCO).</span></span>

## <a name="recommended-action"></a><span data-ttu-id="ffcbc-124">권장 조치</span><span class="sxs-lookup"><span data-stu-id="ffcbc-124">Recommended action</span></span>

<span data-ttu-id="ffcbc-125">이 변경 내용이 방해가 되는 경우 원하는 의미 체계를 구현하는 [사용자 지정 변환기](../../../../standard/serialization/system-text-json-converters-how-to.md)를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ffcbc-125">If this change is disruptive to you, you can use a [custom converter](../../../../standard/serialization/system-text-json-converters-how-to.md) that implements the desired semantics.</span></span>

## <a name="affected-apis"></a><span data-ttu-id="ffcbc-126">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="ffcbc-126">Affected APIs</span></span>

- <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.SerializeAsync%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=fullName>
- <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A?displayProperty=fullName>

<!--

### Affected APIs

- `Overload:System.Text.Json.JsonSerializer.Serialize`
- `Overload:System.Text.Json.JsonSerializer.SerializeAsync`
- `Overload:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes`
- `Overload:System.Text.Json.JsonSerializer.Deserialize`
- `Overload:System.Text.Json.JsonSerializer.DeserializeAsync`

### Category

Serialization

-->
