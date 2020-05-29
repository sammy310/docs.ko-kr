---
title: ''
description: 이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다. 샘플 코드가 포함되어 있습니다.
ms.date: ''
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords: []
ms.openlocfilehash: f1a5da448b08f9b4f1cf3fa6cba67fb376b00a6f
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/20/2020
ms.locfileid: "83702230"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="b8ce6-103">.NET에서 JSON을 직렬화 및 역직렬화(마샬링 및 역 마샬링)하는 방법</span><span class="sxs-lookup"><span data-stu-id="b8ce6-103">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="b8ce6-104">이 문서에서는 <xref:System.Text.Json> 네임스페이스를 사용하여 JSON(JavaScript Object Notation)으로/에서 직렬화 및 역직렬화하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-104">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="b8ce6-105">`Newtonsoft.Json`에서 기존 코드를 이식하는 경우 [`System.Text.Json`으로 마이그레이션 방법](system-text-json-migrate-from-newtonsoft-how-to.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-105">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="b8ce6-106">지침 및 샘플 코드에서는 [ASP.NET Core](/aspnet/core/) 같은 프레임워크를 통하지 않고 직접 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-106">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="b8ce6-107">대부분의 직렬화 샘플 코드는 JSON을 "보기 좋게 출력"하도록(사람이 읽기 쉽도록 들여쓰기 및 공백 사용) <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-107">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="b8ce6-108">프로덕션에 사용하는 경우에는 일반적으로 이 설정의 기본값인 `false`를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-108">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="b8ce6-109">코드 예제에서는 다음 클래스와 그 변형을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-109">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="b8ce6-110">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="b8ce6-110">Namespaces</span></span>

<span data-ttu-id="b8ce6-111"><xref:System.Text.Json> 네임스페이스에는 모든 진입점과 기본 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-111">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="b8ce6-112"><xref:System.Text.Json.Serialization> 네임스페이스에는 직렬화 및 역직렬화와 관련된 고급 시나리오 및 사용자 지정을 위한 특성과 API가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-112">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="b8ce6-113">이 문서의 코드 예제에서는 두 네임스페이스 중 하나 또는 둘 다에 `using` 지시문이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-113">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="b8ce6-114"><xref:System.Runtime.Serialization> 네임스페이스의 특성은 현재 `System.Text.Json`에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-114">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="b8ce6-115">JSON에 .NET 개체를 쓰는 방법(직렬화)</span><span class="sxs-lookup"><span data-stu-id="b8ce6-115">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="b8ce6-116">문자열 또는 파일에 JSON을 쓰려면 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-116">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="b8ce6-117">다음은 JSON 파일을 문자열로 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-117">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-118">다음은 동기 코드를 사용하여 JSON 파일을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-118">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-119">다음은 비동기 코드를 사용하여 JSON 파일을 만드는 예지입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-119">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-120">앞의 예제에서는 직렬화되는 형식에 형식 유추를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-120">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="b8ce6-121">`Serialize()`의 오버로드는 제네릭 형식 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-121">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="b8ce6-122">직렬화 예제</span><span class="sxs-lookup"><span data-stu-id="b8ce6-122">Serialization example</span></span>

<span data-ttu-id="b8ce6-123">다음은 컬렉션 및 중첩 클래스를 포함하는 클래스 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-123">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="b8ce6-124">다음은 이전 형식의 인스턴스를 직렬화하는 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-124">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="b8ce6-125">JSON 출력은 기본적으로 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-125">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="b8ce6-126">다음 예제에서는 동일한 JSON 형식(공백 및 들여쓰기를 사용하여 보기 좋게 인쇄됨)을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-126">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": 20,
      "Low": -10
    },
    "Hot": {
      "High": 60,
      "Low": 20
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="b8ce6-127">UTF-8로 직렬화</span><span class="sxs-lookup"><span data-stu-id="b8ce6-127">Serialize to UTF-8</span></span>

<span data-ttu-id="b8ce6-128">UTF-8로 직렬화하려면 다음과 같이 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-128">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-129"><xref:System.Text.Json.Utf8JsonWriter>를 사용하는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버로드도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-129">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="b8ce6-130">UTF-8로 직렬화하면 문자열 기반 메서드를 사용할 때보다 약 5-10% 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-130">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="b8ce6-131">속도에서 차이가 나는 이유는 바이트(UTF-8)를 문자열(UTF-16)로 변환할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-131">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="b8ce6-132">Serialization 동작</span><span class="sxs-lookup"><span data-stu-id="b8ce6-132">Serialization behavior</span></span>

* <span data-ttu-id="b8ce6-133">기본적으로 모든 public 속성은 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-133">By default, all public properties are serialized.</span></span> <span data-ttu-id="b8ce6-134">[제외할 속성을 지정](#exclude-properties-from-serialization)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-134">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="b8ce6-135">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)는 ASCII가 아닌 문자, ASCII 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프되어야 하는 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-135">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="b8ce6-136">기본적으로 JSON은 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-136">By default, JSON is minified.</span></span> <span data-ttu-id="b8ce6-137">[JSON을 보기 좋게 출력](#serialize-to-formatted-json)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-137">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="b8ce6-138">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-138">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="b8ce6-139">[JSON 이름 대/소문자를 사용자 지정](#customize-json-names-and-values)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-139">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="b8ce6-140">순환 참조가 감지되고 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-140">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="b8ce6-141">현재는 필드가 제외됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-141">Currently, fields are excluded.</span></span>

<span data-ttu-id="b8ce6-142">지원되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-142">Supported types include:</span></span>

* <span data-ttu-id="b8ce6-143">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="b8ce6-143">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="b8ce6-144">사용자 정의 [POCO(Plain Old CLR Object)](https://stackoverflow.com/questions/250001/poco-definition)</span><span class="sxs-lookup"><span data-stu-id="b8ce6-144">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="b8ce6-145">1차원 및 가변 배열(`ArrayName[][]`)</span><span class="sxs-lookup"><span data-stu-id="b8ce6-145">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="b8ce6-146">`Dictionary<string,TValue>`. 여기서 `TValue`는 `object`, `JsonElement` 또는 POCO입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-146">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="b8ce6-147">다음 네임스페이스의 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-147">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="b8ce6-148">추가 형식을 처리하거나 기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="b8ce6-149">JSON을 .NET 개체로 읽는 방법(역직렬화)</span><span class="sxs-lookup"><span data-stu-id="b8ce6-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="b8ce6-150">문자열 또는 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="b8ce6-151">다음 예제에서는 문자열에서 JSON을 읽고, 앞에서 [직렬화 예제](#serialization-example)에서 설명한 `WeatherForecast` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-151">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="b8ce6-152">동기 코드를 사용하여 파일에서 역직렬화하려면 다음 예제와 같이 파일을 문자열로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="b8ce6-153">비동기 코드를 사용하여 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="b8ce6-154">UTF-8에서 역직렬화</span><span class="sxs-lookup"><span data-stu-id="b8ce6-154">Deserialize from UTF-8</span></span>

<span data-ttu-id="b8ce6-155">UTF-8에서 역직렬화하려면 다음 예제와 같이 `Utf8JsonReader` 또는 `ReadOnlySpan<byte>`을 사용하는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-155">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="b8ce6-156">이 예제에서는 JSON이 jsonUtf8Bytes라는 바이트 배열에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-156">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="b8ce6-157">역직렬화 동작</span><span class="sxs-lookup"><span data-stu-id="b8ce6-157">Deserialization behavior</span></span>

* <span data-ttu-id="b8ce6-158">속성 이름 일치 시에 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-158">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="b8ce6-159">[대/소문자를 구분 하지 않도록 지정](#case-insensitive-property-matching)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-159">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="b8ce6-160">JSON에 읽기 전용 속성의 값이 포함되어 있으면 해당 값이 무시되고 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-160">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="b8ce6-161">매개 변수 없는 생성자가 없는 참조 형식으로의 역직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-161">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="b8ce6-162">변경할 수 없는 개체 또는 읽기 전용 속성으로의 역직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-162">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="b8ce6-163">기본적으로 열거형은 숫자로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-163">By default, enums are supported as numbers.</span></span> <span data-ttu-id="b8ce6-164">[열거형 이름을 문자열로 직렬화](#enums-as-strings)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-164">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="b8ce6-165">필드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-165">Fields aren't supported.</span></span>
* <span data-ttu-id="b8ce6-166">기본적으로 JSON의 주석이나 후행 쉼표는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-166">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="b8ce6-167">[주석과 후행 쉼표를 허용](#allow-comments-and-trailing-commas)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-167">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="b8ce6-168">[기본 최댓값](xref:System.Text.Json.JsonReaderOptions.MaxDepth)은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-168">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="b8ce6-169">기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-169">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="b8ce6-170">형식이 지정된 JSON으로 직렬화</span><span class="sxs-lookup"><span data-stu-id="b8ce6-170">Serialize to formatted JSON</span></span>

<span data-ttu-id="b8ce6-171">JSON 출력을 보기 좋게 출력하려면 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-171">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="b8ce6-172">다음 형식은 직렬화하여 보기 좋게 출력할 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-172">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="b8ce6-173">JSON 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b8ce6-173">Customize JSON names and values</span></span>

<span data-ttu-id="b8ce6-174">기본적으로 대/소문자를 비롯한 속성 이름 및 사전 키는 JSON 출력에서 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-174">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="b8ce6-175">열거형 값은 숫자로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-175">Enum values are represented as numbers.</span></span> <span data-ttu-id="b8ce6-176">이 섹션에서는 다음을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-176">This section explains how to:</span></span>

* [<span data-ttu-id="b8ce6-177">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b8ce6-177">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="b8ce6-178">모든 속성 이름을 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="b8ce6-178">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="b8ce6-179">사용자 지정 속성 명명 정책 구현</span><span class="sxs-lookup"><span data-stu-id="b8ce6-179">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="b8ce6-180">사전 키를 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="b8ce6-180">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="b8ce6-181">열거형을 문자열 및 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="b8ce6-181">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="b8ce6-182">JSON 속성 이름 및 값을 특수하게 처리해야 하는 다른 시나리오의 경우 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-182">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="b8ce6-183">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b8ce6-183">Customize individual property names</span></span>

<span data-ttu-id="b8ce6-184">개별 속성 이름을 설정하려면 [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="b8ce6-185">다음은 직렬화 형식과 그 결과 JSON의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-185">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="b8ce6-186">이 특성을 통해 설정된 속성 이름은 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="b8ce6-187">직렬화 및 역직렬화 양방향으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="b8ce6-188">속성 명명 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="b8ce6-189">모든 JSON 속성 이름에 카멜식 대/소문자 사용</span><span class="sxs-lookup"><span data-stu-id="b8ce6-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="b8ce6-190">모든 JSON 속성 이름에 카멜식 대/소문자를 사용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>을 `JsonNamingPolicy.CamelCase`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="b8ce6-191">다음은 직렬화 클래스 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-191">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="b8ce6-192">카멜식 대/소문자 속성 명명 정책은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="b8ce6-193">직렬화 및 역직렬화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="b8ce6-194">`[JsonPropertyName]` 특성에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-194">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="b8ce6-195">이러한 이유로 이 예제의 JSON 속성 이름 `Wind`는 카멜식 대/소문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-195">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="b8ce6-196">사용자 지정 JSON 속성 명명 정책 사용</span><span class="sxs-lookup"><span data-stu-id="b8ce6-196">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="b8ce6-197">사용자 지정 JSON 속성 명명 정책을 사용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonNamingPolicy>에서 파생되는 클래스를 만들고 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-197">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="b8ce6-198">그리고 다음과 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 속성을 명명 정책 클래스의 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-198">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-199">다음은 직렬화 클래스 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-199">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="b8ce6-200">JSON 속성 명명 정책은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-200">The JSON property naming policy:</span></span>

* <span data-ttu-id="b8ce6-201">직렬화 및 역직렬화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-201">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="b8ce6-202">`[JsonPropertyName]` 특성에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-202">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="b8ce6-203">이러한 이유로 이 예제의 JSON 속성 이름 `Wind`는 대문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-203">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="b8ce6-204">카멜식 대/소문자 사전 키</span><span class="sxs-lookup"><span data-stu-id="b8ce6-204">Camel case dictionary keys</span></span>

<span data-ttu-id="b8ce6-205">직렬화할 개체의 속성이 `Dictionary<string,TValue>` 형식이면 `string` 키를 카멜식 대/소문자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-205">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="b8ce6-206">이렇게 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy>를 `JsonNamingPolicy.CamelCase`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-206">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-207">키-값 쌍 `"ColdMinTemp", 20` 및 `"HotMinTemp", 40`가 있는 `TemperatureRanges`라는 사전이 포함된 개체를 직렬화하면 다음 예제와 같은 JSON 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-207">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="b8ce6-208">사전 키에 대한 카멜식 대/소문자 명명 정책은 직렬화에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-208">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="b8ce6-209">사전을 역직렬화하면 `DictionaryKeyPolicy`에 대 한 `JsonNamingPolicy.CamelCase`를 지정하더라도 키가 JSON 파일과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-209">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="b8ce6-210">문자열인 열거형</span><span class="sxs-lookup"><span data-stu-id="b8ce6-210">Enums as strings</span></span>

<span data-ttu-id="b8ce6-211">기본적으로 열거형은 숫자로 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-211">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="b8ce6-212">열거형 이름을 문자열로 직렬화하려면 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-212">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="b8ce6-213">예를 들어 열거형을 포함하는 다음 클래스를 직렬화해야 한다고 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-213">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="b8ce6-214">Summary가 `Hot`이면 기본적으로 직렬화된 JSON은 다음과 같이 숫자 값 3을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-214">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="b8ce6-215">다음 샘플 코드는 숫자 값 대신 열거형 이름을 직렬화하고, 이름을 카멜식 대/소문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-215">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-216">그 결과로 얻는 JSON은 다음 예제와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-216">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="b8ce6-217">다음 예제와 같이 열거형 문자열 이름도 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-217">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="b8ce6-218">직렬화에서 속성 제외</span><span class="sxs-lookup"><span data-stu-id="b8ce6-218">Exclude properties from serialization</span></span>

<span data-ttu-id="b8ce6-219">기본적으로 모든 public 속성은 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="b8ce6-220">그 중 일부 속성을 JSON 출력에 표시하지 않으려는 경우에 사용할 수 있는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="b8ce6-221">이 섹션에서는 다음 속성을 제외하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-221">This section explains how to exclude:</span></span>

* [<span data-ttu-id="b8ce6-222">개별 속성</span><span class="sxs-lookup"><span data-stu-id="b8ce6-222">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="b8ce6-223">모든 읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="b8ce6-223">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="b8ce6-224">모든 Null 값 속성</span><span class="sxs-lookup"><span data-stu-id="b8ce6-224">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="b8ce6-225">개별 속성 제외</span><span class="sxs-lookup"><span data-stu-id="b8ce6-225">Exclude individual properties</span></span>

<span data-ttu-id="b8ce6-226">개별 속성을 무시하려면 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="b8ce6-227">다음은 직렬화 형식 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-227">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="b8ce6-228">모든 읽기 전용 속성 제외</span><span class="sxs-lookup"><span data-stu-id="b8ce6-228">Exclude all read-only properties</span></span>

<span data-ttu-id="b8ce6-229">public setter가 아닌 public getter를 포함하는 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-229">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="b8ce6-230">모든 읽기 전용 속성을 제외하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-230">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-231">다음은 직렬화 형식 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-231">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="b8ce6-232">이 옵션은 직렬화에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-232">This option applies only to serialization.</span></span> <span data-ttu-id="b8ce6-233">역직렬화를 수행할 때 읽기 전용 속성은 기본적으로 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-233">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="b8ce6-234">모든 Null 값 속성 제외</span><span class="sxs-lookup"><span data-stu-id="b8ce6-234">Exclude all null value properties</span></span>

<span data-ttu-id="b8ce6-235">모든 Null 값 속성을 제외하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-236">다음은 직렬화 개체 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="b8ce6-237">속성</span><span class="sxs-lookup"><span data-stu-id="b8ce6-237">Property</span></span> |<span data-ttu-id="b8ce6-238">값</span><span class="sxs-lookup"><span data-stu-id="b8ce6-238">Value</span></span>  |
|---
<span data-ttu-id="b8ce6-239">title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-239">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-240">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-240">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-241">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-241">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-242">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-242">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-243">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-243">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b8ce6-244">title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-244">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-245">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-245">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-246">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-246">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-247">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-247">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-248">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-248">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b8ce6-249">-----|--- title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-249">-----|--- title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-250">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-250">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-251">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-251">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-252">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-252">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-253">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-253">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b8ce6-254">title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-254">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-255">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-255">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-256">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-256">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-257">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-257">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-258">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-258">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b8ce6-259">-----| | Date    | 8/1/2019 12:00:00 AM -07:00| | TemperatureCelsius| 25 | | Summary| null|</span><span class="sxs-lookup"><span data-stu-id="b8ce6-259">-----| | Date    | 8/1/2019 12:00:00 AM -07:00| | TemperatureCelsius| 25 | | Summary| null|</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="b8ce6-260">이 설정은 직렬화 및 역직렬화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-260">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="b8ce6-261">역직렬화에 미치는 영향에 대한 자세한 내용은 [역직렬화할 때 Null 무시](#ignore-null-when-deserializing)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-261">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="b8ce6-262">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="b8ce6-262">Customize character encoding</span></span>

<span data-ttu-id="b8ce6-263">기본적으로 직렬 변환기는 ASCII가 아닌 문자를 모두 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-263">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="b8ce6-264">즉, ASCII가 아닌 문자를 `\uxxxx`로 바꾸며, 여기서 `xxxx`는 문자의 유니코드 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-264">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="b8ce6-265">예를 들어 `Summary` 속성이 키릴 자모로 설정된 경우 다음 예제와 같이 `WeatherForecast` 개체가 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-265">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="b8ce6-266">언어 문자 세트 직렬화</span><span class="sxs-lookup"><span data-stu-id="b8ce6-266">Serialize language character sets</span></span>

<span data-ttu-id="b8ce6-267">하나 이상의 언어 문자 세트를 이스케이프하지 않고 직렬화하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> 인스턴스를 만들 때 [유니코드 범위](xref:System.Text.Unicode.UnicodeRanges)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-267">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="b8ce6-268">이 코드는 키릴 자모 또는 그리스어 문자를 이스케이프하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-268">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="b8ce6-269">`Summary` 속성이 키릴 자모로 설정된 경우 `WeatherForecast` 개체는 다음 예제와 같이 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-269">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="b8ce6-270">모든 언어 세트를 이스케이프하지 않고 직렬화하려면 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-270">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="b8ce6-271">특정 문자 직렬화</span><span class="sxs-lookup"><span data-stu-id="b8ce6-271">Serialize specific characters</span></span>

<span data-ttu-id="b8ce6-272">이스케이프하지 않고 허용하려는 개별 문자를 지정하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-272">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="b8ce6-273">다음 예제에서는 키릴 자모의 처음 두 문자만 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-273">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="b8ce6-274">다음은 이전 코드에서 생성된 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-274">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="b8ce6-275">모든 문자 직렬화</span><span class="sxs-lookup"><span data-stu-id="b8ce6-275">Serialize all characters</span></span>

<span data-ttu-id="b8ce6-276">이스케이프를 최소화하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-276">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="b8ce6-277">기본 인코더와 비교할 때, `UnsafeRelaxedJsonEscaping` 인코더는 문자를 이스케이프하지 않은 상태로 통과할 수 있도록 허용하는 기준이 더 관대합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-277">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="b8ce6-278">`<`, `>`, `&` 및 `'`처럼 HTML 구분 문자를 이스케이프하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-278">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="b8ce6-279">*문자 세트*에 대한 클라이언트와 서버의 내용이 서로 다를 때 발생할 수 있는 XSS 또는 정보 노출 공격에 대한 심층 방어를 추가로 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-279">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="b8ce6-280">클라이언트가 결과 페이로드를 UTF-8로 인코딩된 JSON으로 해석한다는 사실을 알고 있는 경우에만 안전하지 않은 인코더를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-280">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="b8ce6-281">예를 들어 서버에서 응답 헤더 `Content-Type: application/json; charset=utf-8`을 보내는 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-281">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="b8ce6-282">원시 `UnsafeRelaxedJsonEscaping` 출력을 HTML 페이지나 `<script>` 요소로 내보내도록 허용하면 절대 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-282">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="b8ce6-283">파생 클래스의 속성 직렬화</span><span class="sxs-lookup"><span data-stu-id="b8ce6-283">Serialize properties of derived classes</span></span>

<span data-ttu-id="b8ce6-284">다형 형식 계층 구조의 직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-284">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="b8ce6-285">예를 들어 속성이 인터페이스 또는 추상 클래스로 정의된 경우에는 런타임 형식에 추가 속성이 있더라도 인터페이스 또는 추상 클래스에 정의된 속성만 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-285">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="b8ce6-286">이 동작의 예외는 이 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-286">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="b8ce6-287">예를 들어 `WeatherForecast` 클래스와 `WeatherForecastDerived` 파생 클래스가 있다고 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-287">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="b8ce6-288">그리고 컴파일 시간에 `Serialize` 메서드의 형식 인수가 `WeatherForecast`라고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-288">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="b8ce6-289">이 시나리오에서는 `weatherForecast` 개체가 실제로 `WeatherForecastDerived` 개체인 경우에도 `WindSpeed` 속성이 직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-289">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="b8ce6-290">기본 클래스 속성만 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-290">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="b8ce6-291">이 동작의 목적은 파생된 런타임 생성 형식에서 실수로 데이터가 노출되는 것을 방지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-291">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="b8ce6-292">이전 예제의 파생 형식 속성을 직렬화하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-292">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="b8ce6-293">런타임에 형식을 지정할 수 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-293">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="b8ce6-294">`object`로 직렬화할 개체를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-294">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="b8ce6-295">위의 예제 시나리오에서 두 방법 모두 다음과 같이 `WindSpeed` 속성이 JSON 출력에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-295">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="b8ce6-296">이러한 접근 방식은 루트 개체의 속성이 아니라 직렬화할 루트 개체에 대해서만 다형 직렬화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-296">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="b8ce6-297">`object` 형식으로 정의하면 하위 수준 개체에 대한 다형 직렬화를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-297">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="b8ce6-298">예를 들어 `WeatherForecast` 클래스에 `WeatherForecast` 또는 `object` 형식으로 정의할 수 있는 `PreviousForecast`라는 속성이 있다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-298">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="b8ce6-299">이 `PreviousForecast` 속성은 다음과 같이 `WeatherForecastDerived` 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-299">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="b8ce6-300">`WeatherForecastWithPrevious` 직렬화의 JSON 출력에는 `WindSpeed`가 포함되지 **않습니다**.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-300">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="b8ce6-301">`WeatherForecastWithPreviousAsObject` 직렬화의 JSON 출력에는 `WindSpeed`가 포함**됩니다**.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-301">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="b8ce6-302">루트 개체가 파생 형식이 아닐 수도 있으므로 `WeatherForecastWithPreviousAsObject`를 직렬화하기 위해 `Serialize<object>` 또는 `GetType`을 반드시 호출해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-302">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="b8ce6-303">예를 들어 다음 코드 예제는 `Serialize<object>` 또는 `GetType`을 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-303">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="b8ce6-304">이전 코드는 다음과 같이 `WeatherForecastWithPreviousAsObject`를 올바르게 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-304">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "PreviousForecast": {
    "WindSpeed": 35,
    "Date": "2019-08-01T00:00:00-07:00",
    "TemperatureCelsius": 25,
    "Summary": "Hot"
  }
}
```

<span data-ttu-id="b8ce6-305">속성을 `object`로 정의하는 동일한 방법이 인터페이스에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-305">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="b8ce6-306">다음과 같은 인터페이스 및 구현이 있고, 구현 인스턴스가 포함된 속성을 사용하여 클래스를 직렬화하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-306">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="b8ce6-307">`Forecasts`의 인스턴스를 직렬화할 경우 `Tuesday`가 `object`로 정의되어 있으므로 `Tuesday`만 `WindSpeed` 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-307">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="b8ce6-308">다음 예제에서는 이전 코드의 결과로 생성되는 JSON을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-308">The following example shows the JSON that results from the preceding code:</span></span>

```json
{
  "Monday": {
    "Date": "2020-01-06T00:00:00-08:00",
    "TemperatureCelsius": 10,
    "Summary": "Cool"
  },
  "Tuesday": {
    "Date": "2020-01-07T00:00:00-08:00",
    "TemperatureCelsius": 11,
    "Summary": "Rainy",
    "WindSpeed": 10
  }
}
```

<span data-ttu-id="b8ce6-309">다형 **serialization** 및 **deserialization**에 대한 자세한 내용은 [Newtonsoft.Json에서 System.Text.Json로 마이그레이션하는 방법](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-309">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="b8ce6-310">주석과 후행 쉼표 허용</span><span class="sxs-lookup"><span data-stu-id="b8ce6-310">Allow comments and trailing commas</span></span>

<span data-ttu-id="b8ce6-311">기본적으로 주석과 후행 쉼표는 JSON에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-311">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="b8ce6-312">JSON에서 주석을 허용하려면 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 속성을 `JsonCommentHandling.Skip`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-312">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="b8ce6-313">그리고 후행 쉼표를 허용하려면 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-313">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="b8ce6-314">다음 예제에서는 주석과 후행 쉼표를 허용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-314">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="b8ce6-315">다음은 주석과 후행 쉼표를 사용하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-315">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="b8ce6-316">대/소문자를 구분하지 않는 속성 매칭</span><span class="sxs-lookup"><span data-stu-id="b8ce6-316">Case-insensitive property matching</span></span>

<span data-ttu-id="b8ce6-317">기본적으로 역직렬화는 JSON과 대상 개체 속성 간에 일치하는 대/소문자 구분 속성 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-317">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="b8ce6-318">이 동작을 변경하려면 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-318">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="b8ce6-319">다음은 카멜식 대/소문자 속성 이름을 사용하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-319">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="b8ce6-320">파스칼식 대/소문자 속성 이름을 사용하는 다음 형식으로 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-320">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="b8ce6-321">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="b8ce6-321">Handle overflow JSON</span></span>

<span data-ttu-id="b8ce6-322">역직렬화할 때 대상 형식의 속성으로 표시되지 않는 데이터를 JSON에서 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-322">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="b8ce6-323">예를 들어 대상 형식이 다음과 같다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-323">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="b8ce6-324">그리고 역직렬화할 JSON은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-324">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="b8ce6-325">표시된 JSON을 표시된 형식으로 역직렬화하면 `DatesAvailable` 및 `SummaryWords` 속성은 이동할 곳이 없으므로 없어집니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-325">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="b8ce6-326">이러한 속성과 같은 추가 데이터를 캡처하려면 다음과 같이 [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) 특성을 `Dictionary<string,object>` 또는 `Dictionary<string,JsonElement>` 형식의 속성에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-326">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="b8ce6-327">앞에서 보여드린 JSON을 이 샘플 형식으로 역직렬화하면 추가 데이터는 다음과 같이 `ExtensionData` 속성의 키-값 쌍이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-327">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="b8ce6-328">속성</span><span class="sxs-lookup"><span data-stu-id="b8ce6-328">Property</span></span> |<span data-ttu-id="b8ce6-329">값</span><span class="sxs-lookup"><span data-stu-id="b8ce6-329">Value</span></span>  |<span data-ttu-id="b8ce6-330">참고</span><span class="sxs-lookup"><span data-stu-id="b8ce6-330">Notes</span></span>  |
|---
<span data-ttu-id="b8ce6-331">title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-331">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-332">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-332">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-333">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-333">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-334">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-334">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-335">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-335">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b8ce6-336">title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-336">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-337">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-337">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-338">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-338">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-339">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-339">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-340">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-340">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b8ce6-341">-----|--- title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-341">-----|--- title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-342">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-342">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-343">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-343">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-344">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-344">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-345">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-345">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b8ce6-346">title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-346">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-347">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-347">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-348">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-348">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-349">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-349">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-350">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-350">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b8ce6-351">-----|--- title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-351">-----|--- title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-352">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-352">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-353">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-353">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-354">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-354">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-355">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-355">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

-
<span data-ttu-id="b8ce6-356">title: description: '이 문서에서는 System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-356">title: description: 'This article shows you how to use the System.Text.Json namespace to serialize to and deserialize from JSON in .NET.</span></span> <span data-ttu-id="b8ce6-357">샘플 코드가 포함되어 있습니다.'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-357">It includes sample code.'</span></span>
<span data-ttu-id="b8ce6-358">ms.date: no-loc:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-358">ms.date: no-loc:</span></span>
- <span data-ttu-id="b8ce6-359">'System.Text.Json'</span><span class="sxs-lookup"><span data-stu-id="b8ce6-359">'System.Text.Json'</span></span>
- <span data-ttu-id="b8ce6-360">'Newtonsoft.Json' helpviewer_keywords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-360">'Newtonsoft.Json' helpviewer_keywords:</span></span>
- 
- 
- 
- 

<span data-ttu-id="b8ce6-361">-----| | Date    | 8/1/2019 12:00:00 AM -07:00|| | TemperatureCelsius| 0 | 대/소문자를 구분하는 불일치(JSON의 `temperatureCelsius`), 따라서 속성은 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-361">-----| | Date    | 8/1/2019 12:00:00 AM -07:00|| | TemperatureCelsius| 0 | Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> <span data-ttu-id="b8ce6-362">| | Summary | Hot || | ExtensionData | temperatureCelsius: 25 |대/소문자가 일치하지 않으므로 이 JSON 속성은 추가 속성이며 사전에서 키-값 쌍이 됩니다.| || DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-362">| | Summary | Hot || | ExtensionData | temperatureCelsius: 25 |Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.| || DatesAvailable:</span></span><br>  <span data-ttu-id="b8ce6-363">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="b8ce6-363">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="b8ce6-364">8/2/2019 12:00:00 AM -07:00 |JSON의 추가 속성은 키-값 쌍이 되고, 배열은 값 개체로 사용됩니다.| | |SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="b8ce6-364">8/2/2019 12:00:00 AM -07:00 |Extra property from the JSON becomes a key-value pair, with an array as the value object.| | |SummaryWords:</span></span><br><span data-ttu-id="b8ce6-365">표</span><span class="sxs-lookup"><span data-stu-id="b8ce6-365">Cool</span></span><br><span data-ttu-id="b8ce6-366">Windy</span><span class="sxs-lookup"><span data-stu-id="b8ce6-366">Windy</span></span><br><span data-ttu-id="b8ce6-367">Humid |JSON의 추가 속성은 키-값 쌍이 되고, 배열은 값 개체로 사용됩니다.|</span><span class="sxs-lookup"><span data-stu-id="b8ce6-367">Humid |Extra property from the JSON becomes a key-value pair, with an array as the value object.|</span></span>

<span data-ttu-id="b8ce6-368">대상 개체가 직렬화되면 확장 데이터 키 값 쌍은 마치 수신 JSON에 있는 것처럼 JSON 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-368">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 0,
  "Summary": "Hot",
  "temperatureCelsius": 25,
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

<span data-ttu-id="b8ce6-369">`ExtensionData` 속성 이름은 JSON에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-369">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="b8ce6-370">이 동작을 통해 JSON은 추가 데이터를 잃지 않고도 라운드트립을 수행할 수 있으며, 이 동작이 없으면 추가 데이터가 역직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-370">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="b8ce6-371">역직렬화할 때 Null 무시</span><span class="sxs-lookup"><span data-stu-id="b8ce6-371">Ignore null when deserializing</span></span>

<span data-ttu-id="b8ce6-372">기본적으로 JSON의 속성이 Null이면 대상 개체의 해당 속성은 Null로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-372">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="b8ce6-373">대상 속성에 기본값이 사용되며 기본값이 Null 값으로 재정의되지 않기를 원하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-373">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="b8ce6-374">예를 들어 다음 코드가 대상 개체를 보여준다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-374">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="b8ce6-375">그리고 다음 JSON이 역직렬화된다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-375">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="b8ce6-376">역직렬화 후 `WeatherForecastWithDefault` 개체의 `Summary` 속성은 Null입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-376">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="b8ce6-377">이 동작을 변경하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-377">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="b8ce6-378">이 옵션을 사용하면 역직렬화 후 `WeatherForecastWithDefault` 개체의 `Summary` 속성은 기본값인 "No summary"입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-378">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="b8ce6-379">JSON의 Null 값은 유효한 경우에만 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-379">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="b8ce6-380">null을 허용하지 않는 값 형식에 Null 값을 사용하면 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-380">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="b8ce6-381">Utf8JsonReader, Utf8JsonWriter 및 JsonDocument</span><span class="sxs-lookup"><span data-stu-id="b8ce6-381">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="b8ce6-382"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>은 `ReadOnlySpan<byte>` 또는 `ReadOnlySequence<byte>`에서 읽어온 UTF-8 인코딩 JSON 텍스트를 위한 고성능, 저할당, 전달 전용 판독기입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-382"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="b8ce6-383">`Utf8JsonReader`는 사용자 지정 구문 분석기 및 역직렬 변환기를 빌드하는 데 활용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-383">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="b8ce6-384"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonReader`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-384">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="b8ce6-385"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>은 `String`, `Int32` 및 `DateTime`과 같은 일반적인 .NET 형식에서 UTF-8 인코딩 JSON 텍스트를 쓸 수 있는 고성능 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-385"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="b8ce6-386">writer는 사용자 지정 직렬 변환기를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-386">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="b8ce6-387"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonWriter`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-387">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="b8ce6-388"><xref:System.Text.Json.JsonDocument?displayProperty=fullName>은 `Utf8JsonReader`를 사용하여 읽기 전용 DOM(문서 개체 모델)을 빌드하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-388"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="b8ce6-389">DOM은 JSON 페이로드의 데이터에 대한 임의 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-389">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="b8ce6-390">페이로드를 구성하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-390">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="b8ce6-391">`JsonElement` 형식은 JSON 텍스트를 일반적인 .NET 형식으로 변환하는 API와 함께 배열 및 개체 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-391">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="b8ce6-392">`JsonDocument`는 <xref:System.Text.Json.JsonDocument.RootElement> 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-392">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="b8ce6-393">다음 섹션에서는 이러한 도구를 사용하여 JSON을 읽고 쓰는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-393">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="b8ce6-394">JsonDocument를 사용하여 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="b8ce6-394">Use JsonDocument for access to data</span></span>

<span data-ttu-id="b8ce6-395">다음 예제에서는 <xref:System.Text.Json.JsonDocument> 클래스를 사용하여 JSON 문자열의 데이터에 임의로 액세스하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-395">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="b8ce6-396">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="b8ce6-396">The preceding code:</span></span>

* <span data-ttu-id="b8ce6-397">분석할 JSON은 `jsonString`이라는 문자열에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-397">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="b8ce6-398">`Grade` 속성이 있는 `Students` 배열의 개체에 대한 평균 등급을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-398">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="b8ce6-399">등급이 없는 학생에게 기본 등급 70을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-399">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="b8ce6-400">반복마다 `count` 변수를 늘려서 학생 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-400">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="b8ce6-401">다음 예제처럼 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>를 호출하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-401">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="b8ce6-402">다음은 이 코드가 처리하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-402">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="b8ce6-403">JsonDocument를 사용하여 JSON 쓰기</span><span class="sxs-lookup"><span data-stu-id="b8ce6-403">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="b8ce6-404">다음 예제에서는 <xref:System.Text.Json.JsonDocument>에서 JSON을 쓰는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-404">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="b8ce6-405">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="b8ce6-405">The preceding code:</span></span>

* <span data-ttu-id="b8ce6-406">JSON 파일을 읽고, `JsonDocument`에 데이터를 로드하고, 서식 있는(보기 좋게 출력된) JSON을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-406">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="b8ce6-407"><xref:System.Text.Json.JsonDocumentOptions>를 사용하여 입력 JSON의 주석을 허용하지만 무시하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-407">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="b8ce6-408">완료되면 writer에서 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-408">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="b8ce6-409">삭제될 때 writer가 자동으로 플러시하도록 설정하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-409">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="b8ce6-410">다음은 예제 코드에서 처리할 JSON 입력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-410">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="b8ce6-411">결과는 다음과 같이 보기 좋게 출력된 JSON 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-411">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="b8ce6-412">Utf8JsonWriter 사용</span><span class="sxs-lookup"><span data-stu-id="b8ce6-412">Use Utf8JsonWriter</span></span>

<span data-ttu-id="b8ce6-413">다음 예제에서는 <xref:System.Text.Json.Utf8JsonWriter> 클래스 사용 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-413">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="b8ce6-414">Utf8JsonReader 사용</span><span class="sxs-lookup"><span data-stu-id="b8ce6-414">Use Utf8JsonReader</span></span>

<span data-ttu-id="b8ce6-415">다음 예제에서는 <xref:System.Text.Json.Utf8JsonReader> 클래스 사용 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-415">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="b8ce6-416">위의 코드는 `jsonUtf8` 변수가 UTF-8로 인코딩된 유효한 JSON을 포함하는 바이트 배열이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-416">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="b8ce6-417">Utf8JsonReader를 사용하여 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="b8ce6-417">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="b8ce6-418">다음 예제에서는 파일을 동기적으로 읽고 값을 검색하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-418">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="b8ce6-419">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="b8ce6-419">The preceding code:</span></span>

* <span data-ttu-id="b8ce6-420">JSON에 개체 배열이 포함되고 각 개체에 문자열 형식의 "name" 속성이 포함될 수 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-420">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="b8ce6-421">"대학교"로 끝나는 개체 및 "이름" 속성 값의 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-421">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="b8ce6-422">파일이 UTF-16으로 인코딩되고 UTF-8로 코드 변환된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-422">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="b8ce6-423">UTF-8로 인코딩된 파일은 다음 코드를 사용하여 `ReadOnlySpan<byte>`로 직접 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-423">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="b8ce6-424">파일에 UTF-8 BOM(바이트 순서 표시)이 포함된 경우 제거한 후 바이트를 `Utf8JsonReader`에 전달해야 합니다. 판독기에는 텍스트가 필요하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-424">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="b8ce6-425">그렇지 않으면 BOM은 잘못된 JSON으로 간주되고, 판독기에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-425">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="b8ce6-426">다음은 위의 코드에서 읽을 수 있는 JSON 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-426">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="b8ce6-427">다음과 같이 "4개 이름 중 2개가 '대학교'로 끝나는 이름"이라는 결과 요약 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-427">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="b8ce6-428">Utf8JsonReader를 사용하여 스트림에서 읽기</span><span class="sxs-lookup"><span data-stu-id="b8ce6-428">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="b8ce6-429">큰 파일(예: 기가바이트 이상 크기)을 읽을 때 전체 파일을 한 번에 메모리에 로드하지 않아도 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-429">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="b8ce6-430">이 시나리오에서는 <xref:System.IO.FileStream>을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-430">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="b8ce6-431">`Utf8JsonReader`를 사용하여 스트림에서 읽는 경우 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-431">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="b8ce6-432">부분 JSON 페이로드를 포함하는 버퍼는 판독기가 진행할 수 있도록 최소한 그 안에 있는 가장 큰 JSON 토큰만큼 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-432">The buffer containing the partial JSON payload must be at least as big as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="b8ce6-433">버퍼는 최소한 JSON 내에서 가장 큰 공백 시퀀스만큼 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-433">The buffer must be at least as big as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="b8ce6-434">판독기는 JSON 페이로드의 다음 <xref:System.Text.Json.Utf8JsonReader.TokenType%2A>을 완전히 읽을 때까지는 읽은 데이터를 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-434">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="b8ce6-435">따라서 버퍼에 바이트가 남아 있으면 판독기에 다시 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-435">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="b8ce6-436"><xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A>를 사용하여 남은 바이트 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-436">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="b8ce6-437">다음 코드에서는 스트림에서 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-437">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="b8ce6-438">이 예제에서는 <xref:System.IO.MemoryStream>을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-438">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="b8ce6-439">`FileStream`이 시작 시 UTF-8 BOM을 포함하는 경우를 제외하고는 <xref:System.IO.FileStream>에서 비슷한 코드가 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-439">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="b8ce6-440">이 경우 남은 바이트를 `Utf8JsonReader`에 전달하기 전에 버퍼에서 3바이트를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-440">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="b8ce6-441">그렇지 않으면 BOM이 JSON의 유효한 부분으로 간주되지 않으므로 판독기가 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-441">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="b8ce6-442">이 샘플 코드는 4KB 버퍼로 시작하여 크기가 부족하여 전체 JSON 토큰을 수용할 수 없을 때마다 버퍼 크기를 두 배로 늘립니다. 이는 판독기가 JSON 페이로드에 대한 작업을 진행하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-442">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not big enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="b8ce6-443">이 코드 조각에 제공된 JSON 샘플은 10바이트와 같이 매우 작은 초기 버퍼 크기를 설정하는 경우에만 버퍼 크기 증가를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-443">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="b8ce6-444">초기 버퍼 크기를 10으로 설정하는 경우 `Console.WriteLine` 문은 버퍼 크기 증가의 원인과 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-444">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="b8ce6-445">4KB 초기 버퍼 크기에서 전체 샘플 JSON은 각 `Console.WriteLine`마다 표시되며 버퍼 크기를 늘릴 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-445">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="b8ce6-446">앞의 예제에서는 버퍼 크기를 늘릴 수 있는 크기 제한을 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-446">The preceding example sets no limit to how big the buffer can grow.</span></span> <span data-ttu-id="b8ce6-447">토큰 크기가 너무 클 경우 코드는 <xref:System.OutOfMemoryException> 예외와 함께 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-447">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="b8ce6-448">이 문제는 JSON이 크기가 약 1GB 이상인 토큰을 포함하는 경우 발생할 수 있습니다. 1GB 크기가 두 배가 되면 `int32` 버퍼에 비해 너무 커지기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="b8ce6-448">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="b8ce6-449">추가 자료</span><span class="sxs-lookup"><span data-stu-id="b8ce6-449">Additional resources</span></span>

* <span data-ttu-id="b8ce6-450">[System.Text.Json 개요](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="b8ce6-450">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* [<span data-ttu-id="b8ce6-451">사용자 지정 변환기를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="b8ce6-451">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="b8ce6-452">[Newtonsoft.Json에서 마이그레이션하는 방법](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="b8ce6-452">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="b8ce6-453">[System.Text.Json의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="b8ce6-453">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="b8ce6-454">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="b8ce6-454">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
