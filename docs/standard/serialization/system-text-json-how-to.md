---
title: C#을 사용하여 JSON을 직렬화 및 역직렬화하는 방법 - .NET
description: System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 알아봅니다. 샘플 코드가 포함되어 있습니다.
ms.date: 11/05/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: aba45a99562b67df17e1ff33ecc3c8bbad63ec30
ms.sourcegitcommit: 30a686fd4377fe6472aa04e215c0de711bc1c322
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/10/2020
ms.locfileid: "94440818"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="8d0cb-104">.NET에서 JSON을 직렬화 및 역직렬화(마샬링 및 역 마샬링)하는 방법</span><span class="sxs-lookup"><span data-stu-id="8d0cb-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="8d0cb-105">이 문서에서는 <xref:System.Text.Json?displayProperty=fullName> 네임스페이스를 사용하여 JSON(JavaScript Object Notation)으로 직렬화와 JSON으로부터 역직렬화하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="8d0cb-106">`Newtonsoft.Json`에서 기존 코드를 이식하는 경우 [`System.Text.Json`으로 마이그레이션 방법](system-text-json-migrate-from-newtonsoft-how-to.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="8d0cb-107">지침 및 샘플 코드에서는 [ASP.NET Core](/aspnet/core/) 같은 프레임워크를 통하지 않고 직접 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="8d0cb-108">대부분의 직렬화 샘플 코드는 JSON을 "보기 좋게 출력"하도록(사람이 읽기 쉽도록 들여쓰기 및 공백 사용) <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="8d0cb-109">프로덕션에 사용하는 경우에는 일반적으로 이 설정의 기본값인 `false`를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="8d0cb-110">코드 예제에서는 다음 클래스와 그 변형을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-110">The code examples refer to the following class and variants of it:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="namespaces"></a><span data-ttu-id="8d0cb-111">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="8d0cb-111">Namespaces</span></span>

<span data-ttu-id="8d0cb-112"><xref:System.Text.Json> 네임스페이스에는 모든 진입점과 기본 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="8d0cb-113"><xref:System.Text.Json.Serialization> 네임스페이스에는 직렬화 및 역직렬화와 관련된 고급 시나리오 및 사용자 지정을 위한 특성과 API가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="8d0cb-114">이 문서의 코드 예제에서는 두 네임스페이스 중 하나 또는 둘 다에 `using` 지시문이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="8d0cb-115"><xref:System.Runtime.Serialization> 네임스페이스의 특성은 `System.Text.Json`에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="8d0cb-116">JSON에 .NET 개체를 쓰는 방법(직렬화)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-116">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="8d0cb-117">문자열 또는 파일에 JSON을 쓰려면 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="8d0cb-118">다음은 JSON 파일을 문자열로 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-118">The following example creates JSON as a string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-119">다음은 동기 코드를 사용하여 JSON 파일을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-119">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-120">다음은 비동기 코드를 사용하여 JSON 파일을 만드는 예지입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-120">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-121">앞의 예제에서는 직렬화되는 형식에 형식 유추를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="8d0cb-122">`Serialize()`의 오버로드는 제네릭 형식 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="8d0cb-123">직렬화 예제</span><span class="sxs-lookup"><span data-stu-id="8d0cb-123">Serialization example</span></span>

<span data-ttu-id="8d0cb-124">다음은 수집 유형 속성과 사용자 정의 형식을 포함하는 예제 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

> [!TIP]
> <span data-ttu-id="8d0cb-125">"POCO"는 [Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_old_CLR_object)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="8d0cb-126">POCO는 예를 들어 상속 또는 속성을 통해 프레임워크별 형식에 의존하지 않는 .NET 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="8d0cb-127">다음은 이전 형식의 인스턴스를 직렬화하는 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="8d0cb-128">JSON 출력은 기본적으로 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-128">The JSON output is minified by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="8d0cb-129">다음 예제에서는 동일한 JSON 형식을 보여주지만 다음과 같은 형식이 지정됩니다(공백 및 들여쓰기를 사용하여 보기 좋게 인쇄됨).</span><span class="sxs-lookup"><span data-stu-id="8d0cb-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="8d0cb-130">UTF-8로 직렬화</span><span class="sxs-lookup"><span data-stu-id="8d0cb-130">Serialize to UTF-8</span></span>

<span data-ttu-id="8d0cb-131">UTF-8로 직렬화하려면 다음과 같이 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-131">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-132"><xref:System.Text.Json.Utf8JsonWriter>를 사용하는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버로드도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-132">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="8d0cb-133">UTF-8로 직렬화하면 문자열 기반 메서드를 사용할 때보다 약 5-10% 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="8d0cb-134">속도에서 차이가 나는 이유는 바이트(UTF-8)를 문자열(UTF-16)로 변환할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="8d0cb-135">Serialization 동작</span><span class="sxs-lookup"><span data-stu-id="8d0cb-135">Serialization behavior</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="8d0cb-136">기본적으로 모든 public 속성은 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="8d0cb-137">[무시할 속성을 지정](#ignore-properties)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-137">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="8d0cb-138">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)는 ASCII가 아닌 문자, ASCII 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프되어야 하는 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="8d0cb-139">기본적으로 JSON은 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-139">By default, JSON is minified.</span></span> <span data-ttu-id="8d0cb-140">[JSON을 보기 좋게 출력](#serialize-to-formatted-json)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="8d0cb-141">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="8d0cb-142">[JSON 이름 대/소문자를 사용자 지정](#customize-json-names-and-values)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-142">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="8d0cb-143">기본적으로 순환 참조가 검색되고 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="8d0cb-144">[참조를 보존하고 순환 참조를 처리](#preserve-references-and-handle-circular-references)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-144">You can [preserve references and handle circular references](#preserve-references-and-handle-circular-references).</span></span>
* <span data-ttu-id="8d0cb-145">기본적으로 [필드](../../csharp/programming-guide/classes-and-structs/fields.md)는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="8d0cb-146">[필드를 포함](#include-fields)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="8d0cb-147">ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-147">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="8d0cb-148">자세한 내용은 [JsonSerializerOptions 웹 기본값](#web-defaults-for-jsonserializeroptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-148">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="8d0cb-149">기본적으로 모든 public 속성은 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="8d0cb-150">[무시할 속성을 지정](#ignore-properties)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-150">You can [specify properties to ignore](#ignore-properties).</span></span>
* <span data-ttu-id="8d0cb-151">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)는 ASCII가 아닌 문자, ASCII 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프되어야 하는 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="8d0cb-152">기본적으로 JSON은 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-152">By default, JSON is minified.</span></span> <span data-ttu-id="8d0cb-153">[JSON을 보기 좋게 출력](#serialize-to-formatted-json)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="8d0cb-154">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="8d0cb-155">[JSON 이름 대/소문자를 사용자 지정](#customize-json-names-and-values)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-155">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="8d0cb-156">순환 참조가 감지되고 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="8d0cb-157">[필드](../../csharp/programming-guide/classes-and-structs/fields.md)는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="8d0cb-158">지원되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="8d0cb-159">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="8d0cb-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="8d0cb-160">사용자 정의 [POCO(Plain Old CLR Object)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="8d0cb-161">1차원 및 가변 배열(`T[][]`)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="8d0cb-162">다음 네임스페이스의 컬렉션 및 사전.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="8d0cb-163">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="8d0cb-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="8d0cb-164">사용자 정의 [POCO(Plain Old CLR Object)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="8d0cb-165">1차원 및 가변 배열(`ArrayName[][]`)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="8d0cb-166">`Dictionary<string,TValue>`. 여기서 `TValue`는 `object`, `JsonElement` 또는 POCO입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="8d0cb-167">다음 네임스페이스의 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="8d0cb-168">추가 형식을 처리하거나 기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="8d0cb-169">JSON을 .NET 개체로 읽는 방법(역직렬화)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-169">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="8d0cb-170">문자열 또는 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-170">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="8d0cb-171">다음 예제에서는 문자열에서 JSON을 읽고, 앞에서 [직렬화 예제](#serialization-example)에서 설명한 `WeatherForecastWithPOCOs` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="8d0cb-172">동기 코드를 사용하여 파일에서 역직렬화하려면 다음 예제와 같이 파일을 문자열로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="8d0cb-173">비동기 코드를 사용하여 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-173">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="8d0cb-174">UTF-8에서 역직렬화</span><span class="sxs-lookup"><span data-stu-id="8d0cb-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="8d0cb-175">UTF-8에서 역직렬화하려면 다음 예제와 같이 `Utf8JsonReader` 또는 `ReadOnlySpan<byte>`을 사용하는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-175">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="8d0cb-176">이 예제에서는 JSON이 jsonUtf8Bytes라는 바이트 배열에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="8d0cb-177">역직렬화 동작</span><span class="sxs-lookup"><span data-stu-id="8d0cb-177">Deserialization behavior</span></span>

<span data-ttu-id="8d0cb-178">JSON을 역직렬화할 때 다음 동작이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="8d0cb-179">속성 이름 일치 시에 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="8d0cb-180">[대/소문자를 구분 하지 않도록 지정](#case-insensitive-property-matching)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-180">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="8d0cb-181">JSON에 읽기 전용 속성의 값이 포함되어 있으면 해당 값이 무시되고 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="8d0cb-182">public이 아닌 생성자는 직렬 변환기에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="8d0cb-183">변경 불가능한 개체 또는 읽기 전용 속성으로의 역직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="8d0cb-184">[변경 불가능한 형식 및 레코드](#immutable-types-and-records)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-184">See [Immutable types and Records](#immutable-types-and-records).</span></span>
* <span data-ttu-id="8d0cb-185">기본적으로 열거형은 숫자로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="8d0cb-186">[열거형 이름을 문자열로 직렬화](#enums-as-strings)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-186">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="8d0cb-187">기본적으로 필드는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-187">By default, fields are ignored.</span></span> <span data-ttu-id="8d0cb-188">[필드를 포함](#include-fields)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="8d0cb-189">기본적으로 JSON의 주석이나 후행 쉼표는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="8d0cb-190">[주석과 후행 쉼표를 허용](#allow-comments-and-trailing-commas)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-190">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="8d0cb-191">[기본 최댓값](xref:System.Text.Json.JsonReaderOptions.MaxDepth)은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-191">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="8d0cb-192">ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-192">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="8d0cb-193">자세한 내용은 [JsonSerializerOptions 웹 기본값](#web-defaults-for-jsonserializeroptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-193">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="8d0cb-194">속성 이름 일치 시에 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="8d0cb-195">[대/소문자를 구분 하지 않도록 지정](#case-insensitive-property-matching)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-195">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span> <span data-ttu-id="8d0cb-196">ASP.NET Core 앱은[대/소문자 구분 사용 안 함을 기본값으로 지정](#web-defaults-for-jsonserializeroptions)합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-196">ASP.NET Core apps [specify case-insensitivity by default](#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="8d0cb-197">JSON에 읽기 전용 속성의 값이 포함되어 있으면 해당 값이 무시되고 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="8d0cb-198">public, internal 또는 private일 수 있는 매개 변수가 없는 생성자가 역직렬화에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="8d0cb-199">변경할 수 없는 개체 또는 읽기 전용 속성으로의 역직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="8d0cb-200">기본적으로 열거형은 숫자로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="8d0cb-201">[열거형 이름을 문자열로 직렬화](#enums-as-strings)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-201">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="8d0cb-202">필드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-202">Fields aren't supported.</span></span>
* <span data-ttu-id="8d0cb-203">기본적으로 JSON의 주석이나 후행 쉼표는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="8d0cb-204">[주석과 후행 쉼표를 허용](#allow-comments-and-trailing-commas)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-204">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="8d0cb-205">[기본 최댓값](xref:System.Text.Json.JsonReaderOptions.MaxDepth)은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-205">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="8d0cb-206">ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-206">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="8d0cb-207">자세한 내용은 [JsonSerializerOptions 웹 기본값](#web-defaults-for-jsonserializeroptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-207">For more information, see [Web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="8d0cb-208">기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="8d0cb-209">형식이 지정된 JSON으로 직렬화</span><span class="sxs-lookup"><span data-stu-id="8d0cb-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="8d0cb-210">JSON 출력을 보기 좋게 출력하려면 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-210">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="8d0cb-211">다음 형식은 직렬화하여 보기 좋게 출력할 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a><span data-ttu-id="8d0cb-212">필드 포함</span><span class="sxs-lookup"><span data-stu-id="8d0cb-212">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="8d0cb-213">다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> 전역 설정 또는 [JsonInclude](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 특성을 사용하여 직렬화 또는 역직렬화할 때의 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-213">Use the <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="15,17,19,31":::

<span data-ttu-id="8d0cb-214">읽기 전용 필드를 무시하려면 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 전역 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-214">To ignore read-only fields, use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-215">.NET Core 3.1의 System.Text.Json에서는 필드가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-215">Fields are not supported in System.Text.Json in .NET Core 3.1.</span></span> <span data-ttu-id="8d0cb-216">[사용자 지정 변환기](system-text-json-converters-how-to.md)는 이 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-216">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="customize-json-names-and-values"></a><span data-ttu-id="8d0cb-217">JSON 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8d0cb-217">Customize JSON names and values</span></span>

<span data-ttu-id="8d0cb-218">기본적으로 대/소문자를 비롯한 속성 이름 및 사전 키는 JSON 출력에서 변경되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-218">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="8d0cb-219">열거형 값은 숫자로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-219">Enum values are represented as numbers.</span></span> <span data-ttu-id="8d0cb-220">이 섹션에서는 다음을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-220">This section explains how to:</span></span>

* [<span data-ttu-id="8d0cb-221">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8d0cb-221">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="8d0cb-222">모든 속성 이름을 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="8d0cb-222">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="8d0cb-223">사용자 지정 속성 명명 정책 구현</span><span class="sxs-lookup"><span data-stu-id="8d0cb-223">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="8d0cb-224">사전 키를 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="8d0cb-224">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="8d0cb-225">열거형을 문자열 및 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="8d0cb-225">Convert enums to strings and camel case</span></span>](#enums-as-strings)

<span data-ttu-id="8d0cb-226">JSON 속성 이름 및 값을 특수하게 처리해야 하는 다른 시나리오의 경우 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-226">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="8d0cb-227">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8d0cb-227">Customize individual property names</span></span>

<span data-ttu-id="8d0cb-228">개별 속성 이름을 설정하려면 [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-228">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="8d0cb-229">다음은 직렬화 형식과 그 결과 JSON의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-229">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8d0cb-230">이 특성을 통해 설정된 속성 이름은 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-230">The property name set by this attribute:</span></span>

* <span data-ttu-id="8d0cb-231">직렬화 및 역직렬화 양방향으로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-231">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="8d0cb-232">속성 명명 정책보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-232">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="8d0cb-233">모든 JSON 속성 이름에 카멜식 대/소문자 사용</span><span class="sxs-lookup"><span data-stu-id="8d0cb-233">Use camel case for all JSON property names</span></span>

<span data-ttu-id="8d0cb-234">모든 JSON 속성 이름에 카멜식 대/소문자를 사용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>을 `JsonNamingPolicy.CamelCase`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-234">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="8d0cb-235">다음은 직렬화 클래스 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-235">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8d0cb-236">카멜식 대/소문자 속성 명명 정책은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-236">The camel case property naming policy:</span></span>

* <span data-ttu-id="8d0cb-237">직렬화 및 역직렬화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-237">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8d0cb-238">`[JsonPropertyName]` 특성에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-238">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="8d0cb-239">이러한 이유로 이 예제의 JSON 속성 이름 `Wind`는 카멜식 대/소문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-239">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="8d0cb-240">사용자 지정 JSON 속성 명명 정책 사용</span><span class="sxs-lookup"><span data-stu-id="8d0cb-240">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="8d0cb-241">사용자 지정 JSON 속성 명명 정책을 사용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonNamingPolicy>에서 파생되는 클래스를 만들고 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-241">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="8d0cb-242">그리고 다음과 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 속성을 명명 정책 클래스의 인스턴스로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-242">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-243">다음은 직렬화 클래스 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-243">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="8d0cb-244">JSON 속성 명명 정책은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-244">The JSON property naming policy:</span></span>

* <span data-ttu-id="8d0cb-245">직렬화 및 역직렬화에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-245">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="8d0cb-246">`[JsonPropertyName]` 특성에 의해 재정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-246">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="8d0cb-247">이러한 이유로 이 예제의 JSON 속성 이름 `Wind`는 대문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-247">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="8d0cb-248">카멜식 대/소문자 사전 키</span><span class="sxs-lookup"><span data-stu-id="8d0cb-248">Camel case dictionary keys</span></span>

<span data-ttu-id="8d0cb-249">직렬화할 개체의 속성이 `Dictionary<string,TValue>` 형식이면 `string` 키를 카멜식 대/소문자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-249">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="8d0cb-250">이렇게 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy>를 `JsonNamingPolicy.CamelCase`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-250">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-251">키-값 쌍 `"ColdMinTemp", 20` 및 `"HotMinTemp", 40`가 있는 `TemperatureRanges`라는 사전이 포함된 개체를 직렬화하면 다음 예제와 같은 JSON 출력이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-251">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="8d0cb-252">사전 키에 대한 카멜식 대/소문자 명명 정책은 직렬화에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-252">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="8d0cb-253">사전을 역직렬화하면 `DictionaryKeyPolicy`에 대 한 `JsonNamingPolicy.CamelCase`를 지정하더라도 키가 JSON 파일과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-253">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="8d0cb-254">문자열인 열거형</span><span class="sxs-lookup"><span data-stu-id="8d0cb-254">Enums as strings</span></span>

<span data-ttu-id="8d0cb-255">기본적으로 열거형은 숫자로 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-255">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="8d0cb-256">열거형 이름을 문자열로 직렬화하려면 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-256">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="8d0cb-257">예를 들어 열거형을 포함하는 다음 클래스를 직렬화해야 한다고 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-257">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="8d0cb-258">Summary가 `Hot`이면 기본적으로 직렬화된 JSON은 다음과 같이 숫자 값 3을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-258">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="8d0cb-259">다음 샘플 코드는 숫자 값 대신 열거형 이름을 직렬화하고, 이름을 카멜식 대/소문자로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-259">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-260">그 결과로 얻는 JSON은 다음 예제와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-260">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="8d0cb-261">다음 예제와 같이 열거형 문자열 이름도 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-261">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="ignore-properties"></a><span data-ttu-id="8d0cb-262">속성 무시</span><span class="sxs-lookup"><span data-stu-id="8d0cb-262">Ignore properties</span></span>

<span data-ttu-id="8d0cb-263">기본적으로 모든 public 속성은 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-263">By default, all public properties are serialized.</span></span> <span data-ttu-id="8d0cb-264">그 중 일부 속성을 JSON 출력에 표시하지 않으려는 경우에 사용할 수 있는 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-264">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="8d0cb-265">이 섹션에서는 다음을 무시하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-265">This section explains how to ignore:</span></span>

::: zone pivot="dotnet-5-0"

* [<span data-ttu-id="8d0cb-266">개별 속성</span><span class="sxs-lookup"><span data-stu-id="8d0cb-266">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="8d0cb-267">모든 읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="8d0cb-267">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="8d0cb-268">모든 Null 값 속성</span><span class="sxs-lookup"><span data-stu-id="8d0cb-268">All null-value properties</span></span>](#ignore-all-null-value-properties)
* [<span data-ttu-id="8d0cb-269">모든 기본값 속성</span><span class="sxs-lookup"><span data-stu-id="8d0cb-269">All default-value properties</span></span>](#ignore-all-default-value-properties)
::: zone-end

::: zone pivot="dotnet-core-3-1"

* [<span data-ttu-id="8d0cb-270">개별 속성</span><span class="sxs-lookup"><span data-stu-id="8d0cb-270">Individual properties</span></span>](#ignore-individual-properties)
* [<span data-ttu-id="8d0cb-271">모든 읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="8d0cb-271">All read-only properties</span></span>](#ignore-all-read-only-properties)
* [<span data-ttu-id="8d0cb-272">모든 Null 값 속성</span><span class="sxs-lookup"><span data-stu-id="8d0cb-272">All null-value properties</span></span>](#ignore-all-null-value-properties)
::: zone-end

### <a name="ignore-individual-properties"></a><span data-ttu-id="8d0cb-273">개별 속성 무시</span><span class="sxs-lookup"><span data-stu-id="8d0cb-273">Ignore individual properties</span></span>

<span data-ttu-id="8d0cb-274">개별 속성을 무시하려면 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-274">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="8d0cb-275">다음은 직렬화 형식 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-275">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

::: zone pivot="dotnet-5-0"
<span data-ttu-id="8d0cb-276">[JsonIgnore](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성의 `Condition` 속성을 설정하여 조건부 제외를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-276">You can specify conditional exclusion by setting the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property.</span></span> <span data-ttu-id="8d0cb-277"><xref:System.Text.Json.Serialization.JsonIgnoreCondition> 열거형은 다음 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-277">The <xref:System.Text.Json.Serialization.JsonIgnoreCondition> enum provides the following options:</span></span>

* <span data-ttu-id="8d0cb-278">`Always` - 속성이 항상 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-278">`Always` - The property is always ignored.</span></span> <span data-ttu-id="8d0cb-279">`Condition`을 지정하지 않으면 이 옵션으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-279">If no `Condition` is specified, this option is assumed.</span></span>
* <span data-ttu-id="8d0cb-280">`Never` - `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties` 및 `IgnoreReadOnlyFields` 전역 설정에 관계 없이 속성은 항상 직렬화 및 역직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-280">`Never` - The property is always serialized and deserialized, regardless of the `DefaultIgnoreCondition`, `IgnoreReadOnlyProperties`, and `IgnoreReadOnlyFields` global settings.</span></span>
* <span data-ttu-id="8d0cb-281">`WhenWritingDefault` - 속성이 참조 형식 `null` 또는 값 형식 `default`인 경우 직렬화 시 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-281">`WhenWritingDefault` - The property is ignored on serialization if it's a reference type `null` or a value type `default`.</span></span>
* <span data-ttu-id="8d0cb-282">`WhenWritingNull` - 속성이 참조 형식 `null`인 경우 직렬화 시 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-282">`WhenWritingNull` - The property is ignored on serialization if it's a reference type `null`.</span></span>

<span data-ttu-id="8d0cb-283">다음 예는 [JsonIgnore](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성의 `Condition` 속성을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-283">The following example illustrates use of the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute's `Condition` property:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/JsonIgnoreAttributeExample.cs" highlight="10,13,16":::
::: zone-end

### <a name="ignore-all-read-only-properties"></a><span data-ttu-id="8d0cb-284">모든 읽기 전용 속성 무시</span><span class="sxs-lookup"><span data-stu-id="8d0cb-284">Ignore all read-only properties</span></span>

<span data-ttu-id="8d0cb-285">public setter가 아닌 public getter를 포함하는 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-285">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="8d0cb-286">직렬화할 때 모든 읽기 전용 속성을 무시하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-286">To ignore all read-only properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-287">다음은 직렬화 형식 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-287">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="8d0cb-288">이 옵션은 직렬화에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-288">This option applies only to serialization.</span></span> <span data-ttu-id="8d0cb-289">역직렬화를 수행할 때 읽기 전용 속성은 기본적으로 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-289">During deserialization, read-only properties are ignored by default.</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="8d0cb-290">이 옵션은 속성에만 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-290">This option applies only to properties.</span></span> <span data-ttu-id="8d0cb-291">[필드를 직렬화](#include-fields)할 때 읽기 전용 필드를 무시하려면 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 전역 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-291">To ignore read-only fields when [serializing fields](#include-fields), use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

### <a name="ignore-all-null-value-properties"></a><span data-ttu-id="8d0cb-292">모든 Null 값 속성 무시</span><span class="sxs-lookup"><span data-stu-id="8d0cb-292">Ignore all null-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="8d0cb-293">모든 Null 값 속성을 무시하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> 속성을 <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-293">To ignore all null-value properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingNull>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreNullOnSerialize.cs" highlight="28":::

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-294">직렬화할 때 모든 Null 값 속성을 무시하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-294">To ignore all null-value properties when serializing, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-295">다음은 직렬화 개체 및 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-295">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="8d0cb-296">속성</span><span class="sxs-lookup"><span data-stu-id="8d0cb-296">Property</span></span> |<span data-ttu-id="8d0cb-297">값</span><span class="sxs-lookup"><span data-stu-id="8d0cb-297">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="8d0cb-298">날짜</span><span class="sxs-lookup"><span data-stu-id="8d0cb-298">Date</span></span>    | <span data-ttu-id="8d0cb-299">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="8d0cb-299">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="8d0cb-300">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="8d0cb-300">TemperatureCelsius</span></span>| <span data-ttu-id="8d0cb-301">25</span><span class="sxs-lookup"><span data-stu-id="8d0cb-301">25</span></span> |
| <span data-ttu-id="8d0cb-302">요약</span><span class="sxs-lookup"><span data-stu-id="8d0cb-302">Summary</span></span>| <span data-ttu-id="8d0cb-303">null</span><span class="sxs-lookup"><span data-stu-id="8d0cb-303">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

::: zone-end

### <a name="ignore-all-default-value-properties"></a><span data-ttu-id="8d0cb-304">모든 기본값 속성 무시</span><span class="sxs-lookup"><span data-stu-id="8d0cb-304">Ignore all default-value properties</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="8d0cb-305">값 형식 속성에서 기본값의 직렬화를 방지하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> 속성을 <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-305">To prevent serialization of default values in value type properties, set the <xref:System.Text.Json.JsonSerializerOptions.DefaultIgnoreCondition> property to <xref:System.Text.Json.Serialization.JsonIgnoreCondition.WhenWritingDefault>, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/IgnoreValueDefaultOnSerialize.cs" highlight="28":::
::: zone-end

<span data-ttu-id="8d0cb-306">`WhenWritingDefault` 설정은 null 값 참조 형식 속성의 직렬화도 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-306">The `WhenWritingDefault` setting also prevents serialization of null-value reference type properties.</span></span>

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-307">.NET Core 3.1에서 System.Text.Json의 값 형식 기본값으로 속성의 직렬화를 방지하는 기본 제공 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-307">There is no built-in way to prevent serialization of properties with value type defaults in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="customize-character-encoding"></a><span data-ttu-id="8d0cb-308">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="8d0cb-308">Customize character encoding</span></span>

<span data-ttu-id="8d0cb-309">기본적으로 직렬 변환기는 ASCII가 아닌 문자를 모두 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-309">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="8d0cb-310">즉, ASCII가 아닌 문자를 `\uxxxx`로 바꾸며, 여기서 `xxxx`는 문자의 유니코드 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-310">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="8d0cb-311">예를 들어 `Summary` 속성이 키릴 자모로 설정된 경우 다음 예제와 같이 `WeatherForecast` 개체가 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-311">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="8d0cb-312">언어 문자 세트 직렬화</span><span class="sxs-lookup"><span data-stu-id="8d0cb-312">Serialize language character sets</span></span>

<span data-ttu-id="8d0cb-313">하나 이상의 언어 문자 세트를 이스케이프하지 않고 직렬화하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName> 인스턴스를 만들 때 [유니코드 범위](xref:System.Text.Unicode.UnicodeRanges)를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-313">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="8d0cb-314">이 코드는 키릴 자모 또는 그리스어 문자를 이스케이프하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-314">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="8d0cb-315">`Summary` 속성이 키릴 자모로 설정된 경우 `WeatherForecast` 개체는 다음 예제와 같이 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-315">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="8d0cb-316">모든 언어 세트를 이스케이프하지 않고 직렬화하려면 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-316">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="8d0cb-317">특정 문자 직렬화</span><span class="sxs-lookup"><span data-stu-id="8d0cb-317">Serialize specific characters</span></span>

<span data-ttu-id="8d0cb-318">이스케이프하지 않고 허용하려는 개별 문자를 지정하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-318">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="8d0cb-319">다음 예제에서는 키릴 자모의 처음 두 문자만 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-319">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="8d0cb-320">다음은 이전 코드에서 생성된 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-320">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="8d0cb-321">모든 문자 직렬화</span><span class="sxs-lookup"><span data-stu-id="8d0cb-321">Serialize all characters</span></span>

<span data-ttu-id="8d0cb-322">이스케이프를 최소화하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-322">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="8d0cb-323">기본 인코더와 비교할 때, `UnsafeRelaxedJsonEscaping` 인코더는 문자를 이스케이프하지 않은 상태로 통과할 수 있도록 허용하는 기준이 더 관대합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-323">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="8d0cb-324">`<`, `>`, `&` 및 `'`처럼 HTML 구분 문자를 이스케이프하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-324">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="8d0cb-325">*문자 세트* 에 대한 클라이언트와 서버의 내용이 서로 다를 때 발생할 수 있는 XSS 또는 정보 노출 공격에 대한 심층 방어를 추가로 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-325">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="8d0cb-326">클라이언트가 결과 페이로드를 UTF-8로 인코딩된 JSON으로 해석한다는 사실을 알고 있는 경우에만 안전하지 않은 인코더를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-326">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="8d0cb-327">예를 들어 서버에서 응답 헤더 `Content-Type: application/json; charset=utf-8`을 보내는 경우에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-327">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="8d0cb-328">원시 `UnsafeRelaxedJsonEscaping` 출력을 HTML 페이지나 `<script>` 요소로 내보내도록 허용하면 절대 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-328">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="8d0cb-329">파생 클래스의 속성 직렬화</span><span class="sxs-lookup"><span data-stu-id="8d0cb-329">Serialize properties of derived classes</span></span>

<span data-ttu-id="8d0cb-330">다형 형식 계층 구조의 직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-330">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="8d0cb-331">예를 들어 속성이 인터페이스 또는 추상 클래스로 정의된 경우에는 런타임 형식에 추가 속성이 있더라도 인터페이스 또는 추상 클래스에 정의된 속성만 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-331">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="8d0cb-332">이 동작의 예외는 이 섹션에 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-332">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="8d0cb-333">예를 들어 `WeatherForecast` 클래스와 `WeatherForecastDerived` 파생 클래스가 있다고 가정해 봅시다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-333">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="8d0cb-334">그리고 컴파일 시간에 `Serialize` 메서드의 형식 인수가 `WeatherForecast`라고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-334">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="8d0cb-335">이 시나리오에서는 `weatherForecast` 개체가 실제로 `WeatherForecastDerived` 개체인 경우에도 `WindSpeed` 속성이 직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-335">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="8d0cb-336">기본 클래스 속성만 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-336">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="8d0cb-337">이 동작의 목적은 파생된 런타임 생성 형식에서 실수로 데이터가 노출되는 것을 방지하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-337">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="8d0cb-338">이전 예제의 파생 형식 속성을 직렬화하려면 다음 방법 중 하나를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-338">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="8d0cb-339">런타임에 형식을 지정할 수 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-339">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at run time:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="8d0cb-340">`object`로 직렬화할 개체를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-340">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="8d0cb-341">위의 예제 시나리오에서 두 방법 모두 다음과 같이 `WindSpeed` 속성이 JSON 출력에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-341">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="8d0cb-342">이러한 접근 방식은 루트 개체의 속성이 아니라 직렬화할 루트 개체에 대해서만 다형 직렬화를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-342">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span>

<span data-ttu-id="8d0cb-343">`object` 형식으로 정의하면 하위 수준 개체에 대한 다형 직렬화를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-343">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="8d0cb-344">예를 들어 `WeatherForecast` 클래스에 `WeatherForecast` 또는 `object` 형식으로 정의할 수 있는 `PreviousForecast`라는 속성이 있다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-344">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="8d0cb-345">이 `PreviousForecast` 속성은 다음과 같이 `WeatherForecastDerived` 인스턴스를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-345">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="8d0cb-346">`WeatherForecastWithPrevious` 직렬화의 JSON 출력에는 `WindSpeed`가 포함되지 **않습니다**.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-346">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="8d0cb-347">`WeatherForecastWithPreviousAsObject` 직렬화의 JSON 출력에는 `WindSpeed`가 포함 **됩니다**.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-347">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="8d0cb-348">루트 개체가 파생 형식이 아닐 수도 있으므로 `WeatherForecastWithPreviousAsObject`를 직렬화하기 위해 `Serialize<object>` 또는 `GetType`을 반드시 호출해야 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-348">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="8d0cb-349">예를 들어 다음 코드 예제는 `Serialize<object>` 또는 `GetType`을 호출하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-349">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="8d0cb-350">이전 코드는 다음과 같이 `WeatherForecastWithPreviousAsObject`를 올바르게 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-350">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="8d0cb-351">속성을 `object`로 정의하는 동일한 방법이 인터페이스에서도 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-351">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="8d0cb-352">다음과 같은 인터페이스 및 구현이 있고, 구현 인스턴스가 포함된 속성을 사용하여 클래스를 직렬화하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-352">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/IForecast.cs)]

<span data-ttu-id="8d0cb-353">`Forecasts`의 인스턴스를 직렬화할 경우 `Tuesday`가 `object`로 정의되어 있으므로 `Tuesday`만 `WindSpeed` 속성을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-353">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="8d0cb-354">다음 예제에서는 이전 코드의 결과로 생성되는 JSON을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-354">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="8d0cb-355">다형 **serialization** 및 **deserialization** 에 대한 자세한 내용은 [Newtonsoft.Json에서 System.Text.Json로 마이그레이션하는 방법](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-355">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="8d0cb-356">주석과 후행 쉼표 허용</span><span class="sxs-lookup"><span data-stu-id="8d0cb-356">Allow comments and trailing commas</span></span>

<span data-ttu-id="8d0cb-357">기본적으로 주석과 후행 쉼표는 JSON에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-357">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="8d0cb-358">JSON에서 주석을 허용하려면 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 속성을 `JsonCommentHandling.Skip`으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-358">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="8d0cb-359">그리고 후행 쉼표를 허용하려면 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-359">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="8d0cb-360">다음 예제에서는 주석과 후행 쉼표를 허용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-360">The following example shows how to allow both:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="8d0cb-361">다음은 주석과 후행 쉼표를 사용하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-361">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="8d0cb-362">대/소문자를 구분하지 않는 속성 매칭</span><span class="sxs-lookup"><span data-stu-id="8d0cb-362">Case-insensitive property matching</span></span>

<span data-ttu-id="8d0cb-363">기본적으로 역직렬화는 JSON과 대상 개체 속성 간에 일치하는 대/소문자 구분 속성 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-363">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="8d0cb-364">이 동작을 변경하려면 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-364">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="8d0cb-365">다음은 카멜식 대/소문자 속성 이름을 사용하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-365">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="8d0cb-366">파스칼식 대/소문자 속성 이름을 사용하는 다음 형식으로 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-366">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="8d0cb-367">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="8d0cb-367">Handle overflow JSON</span></span>

<span data-ttu-id="8d0cb-368">역직렬화할 때 대상 형식의 속성으로 표시되지 않는 데이터를 JSON에서 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-368">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="8d0cb-369">예를 들어 대상 형식이 다음과 같다고 가정하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-369">For example, suppose your target type is this:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="8d0cb-370">그리고 역직렬화할 JSON은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-370">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="8d0cb-371">표시된 JSON을 표시된 형식으로 역직렬화하면 `DatesAvailable` 및 `SummaryWords` 속성은 이동할 곳이 없으므로 없어집니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-371">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="8d0cb-372">이러한 속성과 같은 추가 데이터를 캡처하려면 다음과 같이 [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) 특성을 `Dictionary<string,object>` 또는 `Dictionary<string,JsonElement>` 형식의 속성에 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-372">To capture extra data such as these properties, apply the [[JsonExtensionData]](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="8d0cb-373">앞에서 보여드린 JSON을 이 샘플 형식으로 역직렬화하면 추가 데이터는 다음과 같이 `ExtensionData` 속성의 키-값 쌍이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-373">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="8d0cb-374">속성</span><span class="sxs-lookup"><span data-stu-id="8d0cb-374">Property</span></span> |<span data-ttu-id="8d0cb-375">값</span><span class="sxs-lookup"><span data-stu-id="8d0cb-375">Value</span></span>  |<span data-ttu-id="8d0cb-376">참고</span><span class="sxs-lookup"><span data-stu-id="8d0cb-376">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="8d0cb-377">날짜</span><span class="sxs-lookup"><span data-stu-id="8d0cb-377">Date</span></span>    | <span data-ttu-id="8d0cb-378">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="8d0cb-378">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="8d0cb-379">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="8d0cb-379">TemperatureCelsius</span></span>| <span data-ttu-id="8d0cb-380">0</span><span class="sxs-lookup"><span data-stu-id="8d0cb-380">0</span></span> | <span data-ttu-id="8d0cb-381">대/소문자를 구분하는 불일치(JSON의 `temperatureCelsius`). 따라서 속성이 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-381">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="8d0cb-382">요약</span><span class="sxs-lookup"><span data-stu-id="8d0cb-382">Summary</span></span> | <span data-ttu-id="8d0cb-383">핫</span><span class="sxs-lookup"><span data-stu-id="8d0cb-383">Hot</span></span> ||
| <span data-ttu-id="8d0cb-384">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="8d0cb-384">ExtensionData</span></span> | <span data-ttu-id="8d0cb-385">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="8d0cb-385">temperatureCelsius: 25</span></span> |<span data-ttu-id="8d0cb-386">대/소문자가 일치하지 않으므로 이 JSON 속성은 추가 속성이며 사전에서 키-값 쌍이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-386">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="8d0cb-387">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="8d0cb-387">DatesAvailable:</span></span><br>  <span data-ttu-id="8d0cb-388">8/1/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="8d0cb-388">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="8d0cb-389">8/2/2019 12:00:00 AM -07:00</span><span class="sxs-lookup"><span data-stu-id="8d0cb-389">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="8d0cb-390">JSON의 추가 속성은 키-값 쌍이 되고, 배열은 값 개체로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-390">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="8d0cb-391">SummaryWords:</span><span class="sxs-lookup"><span data-stu-id="8d0cb-391">SummaryWords:</span></span><br><span data-ttu-id="8d0cb-392">표</span><span class="sxs-lookup"><span data-stu-id="8d0cb-392">Cool</span></span><br><span data-ttu-id="8d0cb-393">Windy</span><span class="sxs-lookup"><span data-stu-id="8d0cb-393">Windy</span></span><br><span data-ttu-id="8d0cb-394">Humid</span><span class="sxs-lookup"><span data-stu-id="8d0cb-394">Humid</span></span> |<span data-ttu-id="8d0cb-395">JSON의 추가 속성은 키-값 쌍이 되고, 배열은 값 개체로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-395">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="8d0cb-396">대상 개체가 직렬화되면 확장 데이터 키 값 쌍은 마치 수신 JSON에 있는 것처럼 JSON 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-396">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="8d0cb-397">`ExtensionData` 속성 이름은 JSON에 표시되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-397">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="8d0cb-398">이 동작을 통해 JSON은 추가 데이터를 잃지 않고도 라운드트립을 수행할 수 있으며, 이 동작이 없으면 추가 데이터가 역직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-398">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="preserve-references-and-handle-circular-references"></a><span data-ttu-id="8d0cb-399">참조를 보존하고 순환 참조를 처리</span><span class="sxs-lookup"><span data-stu-id="8d0cb-399">Preserve references and handle circular references</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="8d0cb-400">참조를 보존하고 순환 참조를 처리하려면 <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A>를 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-400">To preserve references and handle circular references, set <xref:System.Text.Json.JsonSerializerOptions.ReferenceHandler%2A> to <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A>.</span></span> <span data-ttu-id="8d0cb-401">이렇게 설정하면 다음과 같은 동작이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-401">This setting causes the following behavior:</span></span>

* <span data-ttu-id="8d0cb-402">직렬화 시:</span><span class="sxs-lookup"><span data-stu-id="8d0cb-402">On serialize:</span></span>

  <span data-ttu-id="8d0cb-403">복합 형식을 쓸 때 직렬 변환기는 메타데이터 속성(`$id`, `$values`, `$ref`)도 씁니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-403">When writing complex types, the serializer also writes metadata properties (`$id`, `$values`, and `$ref`).</span></span>

* <span data-ttu-id="8d0cb-404">역직렬화 시:</span><span class="sxs-lookup"><span data-stu-id="8d0cb-404">On deserialize:</span></span>

  <span data-ttu-id="8d0cb-405">메타데이터가 필요하며(필수는 아님), 역직렬 변환기는 이해를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-405">Metadata is expected (although not mandatory), and the deserializer tries to understand it.</span></span>

<span data-ttu-id="8d0cb-406">다음 코드는 `Preserve` 설정을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-406">The following code illustrates use of the `Preserve` setting.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/PreserveReferences.cs" highlight="34":::

<span data-ttu-id="8d0cb-407">이 기능은 값 형식 또는 변경 불가능한 형식을 유지하는 데 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-407">This feature can't be used to preserve value types or immutable types.</span></span> <span data-ttu-id="8d0cb-408">역직렬화 시 변경 불가능한 형식의 인스턴스는 전체 페이로드를 읽은 후에 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-408">On deserialization, the instance of an immutable type is created after the entire payload is read.</span></span> <span data-ttu-id="8d0cb-409">따라서 JSON 페이로드 내에 해당 참조가 표시되는 경우 동일한 인스턴스를 역직렬화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-409">So it would be impossible to deserialize the same instance if a reference to it appears within the JSON payload.</span></span>

<span data-ttu-id="8d0cb-410">값 형식, 변경 불가능한 형식, 배열의 경우 참조 메타데이터가 직렬화되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-410">For value types, immutable types, and arrays, no reference metadata is serialized.</span></span> <span data-ttu-id="8d0cb-411">역직렬화 시 `$ref` 또는 `$id`가 발견되면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-411">On deserialization, an exception is thrown if `$ref` or `$id` is found.</span></span> <span data-ttu-id="8d0cb-412">하지만 Newtonsoft.Json을 사용하여 직렬화된 페이로드를 역직렬화할 수 있도록 값 형식은 `$id`(및 컬렉션의 경우에는 `$values`)를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-412">However, value types ignore `$id` (and `$values` in the case of collections) to make it possible to deserialize payloads that were serialized by using Newtonsoft.Json.</span></span>  <span data-ttu-id="8d0cb-413">Newtonsoft.Json은 이러한 형식의 메타데이터를 직렬화합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-413">Newtonsoft.Json does serialize metadata for such types.</span></span>

<span data-ttu-id="8d0cb-414">개체가 같은지 확인하기 위해 System.Text.Json은 두 개체 인스턴스를 비교할 때 값 같음(<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType>) 대신 참조 같음(<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>)을 사용하는 <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-414">To determine if objects are equal, System.Text.Json uses <xref:System.Collections.Generic.ReferenceEqualityComparer.Instance%2A?displayProperty=nameWithType>, which uses reference equality (<xref:System.Object.ReferenceEquals(System.Object,System.Object)?displayProperty=nameWithType>) instead of value equality (<xref:System.Object.Equals(System.Object)?displayProperty=nameWithType> when comparing two object instances.</span></span>

<span data-ttu-id="8d0cb-415">참조가 직렬화 및 역직렬화되는 방법에 대한 자세한 내용은 <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-415">For more information about how references are serialized and deserialized, see <xref:System.Text.Json.Serialization.ReferenceHandler.Preserve%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="8d0cb-416"><xref:System.Text.Json.Serialization.ReferenceResolver> 클래스는 직렬화 및 역직렬화 시 참조를 보존하는 동작을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-416">The <xref:System.Text.Json.Serialization.ReferenceResolver> class defines the behavior of preserving references on serialization and deserialization.</span></span> <span data-ttu-id="8d0cb-417">파생 클래스를 만들어 사용자 지정 동작을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-417">Create a derived class to specify custom behavior.</span></span> <span data-ttu-id="8d0cb-418">예제는 [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-418">For an example, see [GuidReferenceResolver](https://github.com/dotnet/docs/blob/9d5e88edbd7f12be463775ffebbf07ac8415fe18/docs/standard/serialization/snippets/system-text-json-how-to-5-0/csharp/GuidReferenceResolverExample.cs).</span></span>

::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-419">.NET Core 3.1의 System.Text.Json은 값을 사용하는 직렬화만 지원하며 순환 참조에 대한 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-419">System.Text.Json in .NET Core 3.1 only supports serialization by value and throws an exception for circular references.</span></span>
::: zone-end

## <a name="allow-or-write-numbers-in-quotes"></a><span data-ttu-id="8d0cb-420">따옴표 안에 숫자를 허용하거나 씁니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-420">Allow or write numbers in quotes</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="8d0cb-421">일부 직렬 변환기는 숫자를 JSON 문자열로 인코딩합니다(따옴표로 묶음).</span><span class="sxs-lookup"><span data-stu-id="8d0cb-421">Some serializers encode numbers as JSON strings (surrounded by quotes).</span></span> <span data-ttu-id="8d0cb-422">예를 들어 `{"DegreesCelsius":23}` 대신 `{"DegreesCelsius":"23"}`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-422">For example: `{"DegreesCelsius":"23"}` instead of `{"DegreesCelsius":23}`.</span></span> <span data-ttu-id="8d0cb-423">전체 입력 개체 그래프에서 따옴표 안의 숫자를 직렬화하거나 따옴표 안의 숫자를 허용하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType>을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-423">To serialize numbers in quotes or accept numbers in quotes across the entire input object graph, set <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A?displayProperty=nameWithType> as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/QuotedNumbers.cs" highlight="27-28":::

<span data-ttu-id="8d0cb-424">ASP.NET Core를 통해 간접적으로 System.Text.Json을 사용하는 경우 ASP.NET Core가 [웹 기본 옵션](xref:System.Text.Json.JsonSerializerDefaults.Web)을 지정하기 때문에 역직렬화할 때 따옴표 붙은 숫자가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-424">When you use System.Text.Json indirectly through ASP.NET Core, quoted numbers are allowed when deserializing because ASP.NET Core specifies [web default options](xref:System.Text.Json.JsonSerializerDefaults.Web).</span></span>

<span data-ttu-id="8d0cb-425">특정 속성, 필드 또는 형식에 따옴표 붙은 숫자를 허용하거나 쓰려면 [JsonNumberHandling](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-425">To allow or write quoted numbers for specific properties, fields, or types, use the [[JsonNumberHandling]](xref:System.Text.Json.Serialization.JsonNumberHandlingAttribute) attribute.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-426">.NET Core 3.1에서 System.Text.Json은 따옴표로 묶은 숫자의 직렬화 또는 역직렬화를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-426">System.Text.Json in .NET Core 3.1 doesn't support serializing or deserializing numbers surrounded by quotation marks.</span></span> <span data-ttu-id="8d0cb-427">자세한 내용은 [따옴표 안의 숫자 허용 또는 쓰기](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-427">For more information, see [Allow or write numbers in quotes](system-text-json-migrate-from-newtonsoft-how-to.md#allow-or-write-numbers-in-quotes).</span></span>
::: zone-end

## <a name="immutable-types-and-records"></a><span data-ttu-id="8d0cb-428">변경 불가능한 형식 및 레코드</span><span class="sxs-lookup"><span data-stu-id="8d0cb-428">Immutable types and Records</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="8d0cb-429">System.Text.Json은 매개 변수가 있는 생성자를 사용할 수 있습니다. 이 생성자를 사용하면 변경 불가능한 클래스 또는 구조체를 역직렬화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-429">System.Text.Json can use a parameterized constructor, which makes it possible to deserialize an immutable class or struct.</span></span> <span data-ttu-id="8d0cb-430">클래스의 경우 유일한 생성자가 매개 변수가 있는 생성자이면 해당 생성자가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-430">For a class, if the only constructor is a parameterized one, that constructor will be used.</span></span> <span data-ttu-id="8d0cb-431">구조체 또는 여러 생성자가 포함된 클래스의 경우 [JsonConstructor](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) 특성을 적용하여 사용할 생성자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-431">For a struct, or a class with multiple constructors, specify the one to use by applying the [[JsonConstructor]](xref:System.Text.Json.Serialization.JsonConstructorAttribute.%23ctor%2A) attribute.</span></span> <span data-ttu-id="8d0cb-432">특성을 사용하지 않는 경우 매개 변수가 없는 public 생성자가 있으면 항상 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-432">When the attribute is not used, a public parameterless constructor is always used if present.</span></span> <span data-ttu-id="8d0cb-433">특성은 public 생성자에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-433">The attribute can only be used with public constructors.</span></span> <span data-ttu-id="8d0cb-434">다음 예제는 `[JsonConstructor]` 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-434">The following example uses the `[JsonConstructor]` attribute:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/ImmutableTypes.cs" highlight="13":::

<span data-ttu-id="8d0cb-435">다음 예제와 같이 C# 9의 레코드도 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-435">Records in C# 9 are also supported, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Records.cs":::

<span data-ttu-id="8d0cb-436">모든 속성 setter가 public이 아니기 때문에 변경 불가능한 형식의 경우 [public이 아닌 속성 접근자](#non-public-property-accessors)에 대한 다음 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-436">For types that are immutable because all their property setters are non-public, see the following section about [non-public property accessors](#non-public-property-accessors).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-437">`JsonConstructorAttribute` 및 C# 9 레코드 지원은 .Net Core 3.1에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-437">`JsonConstructorAttribute` and C# 9 Record support aren't available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="non-public-property-accessors"></a><span data-ttu-id="8d0cb-438">public이 아닌 속성 접근자</span><span class="sxs-lookup"><span data-stu-id="8d0cb-438">Non-public property accessors</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="8d0cb-439">public이 아닌 속성 접근자를 사용하도록 설정하려면 다음 예제와 같이 [JsonInclude](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 특성을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-439">To enable use of a non-public property accessor, use the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/NonPublicAccessors.cs" highlight="12,15":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-440">public이 아닌 속성 접근자는 .NET Core 3.1에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-440">Non-public property accessors are not supported in .NET Core 3.1.</span></span> <span data-ttu-id="8d0cb-441">자세한 내용은 [Newtonsoft.Json에서 마이그레이션 문서](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-441">For more information, see [the Migrate from Newtonsoft.Json article](system-text-json-migrate-from-newtonsoft-how-to.md#non-public-property-setters-and-getters).</span></span>
::: zone-end

## <a name="copy-jsonserializeroptions"></a><span data-ttu-id="8d0cb-442">JsonSerializerOptions 복사</span><span class="sxs-lookup"><span data-stu-id="8d0cb-442">Copy JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="8d0cb-443">다음 예제와 같이 기존 인스턴스와 동일한 옵션으로 새 인스턴스를 만들 수 있는 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions))이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-443">There is a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerOptions)) that lets you create a new instance with the same options as an existing instance, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/CopyOptions.cs" highlight="29":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-444">기존 인스턴스를 사용하는 `JsonSerializerOptions` 생성자는 .NET Core 3.1에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-444">A `JsonSerializerOptions` constructor that takes an existing instance is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="web-defaults-for-jsonserializeroptions"></a><span data-ttu-id="8d0cb-445">JsonSerializerOptions의 웹 기본값</span><span class="sxs-lookup"><span data-stu-id="8d0cb-445">Web defaults for JsonSerializerOptions</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="8d0cb-446">서로 다른 웹앱 기본값을 갖는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-446">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>
* <xref:System.Text.Json.JsonSerializerOptions.NumberHandling%2A> = <xref:System.Text.Json.Serialization.JsonNumberHandling.AllowReadingFromString>

<span data-ttu-id="8d0cb-447">다음 예제와 같이 ASP.NET Core가 웹앱에 사용하는 기본 옵션으로 새 인스턴스를 만들 수 있는 [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true)이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-447">There's a [JsonSerializerOptions constructor](xref:System.Text.Json.JsonSerializerOptions.%23ctor(System.Text.Json.JsonSerializerDefaults)?view=net-5.0&preserve-view=true) that lets you create a new instance with the default options that ASP.NET Core uses for web apps, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/OptionsDefaults.cs" highlight="24":::
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-448">서로 다른 웹앱 기본값을 갖는 옵션은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-448">Here are the options that have different defaults for web apps:</span></span>

* <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive%2A> = `true`
* <xref:System.Text.Json.JsonNamingPolicy> = <xref:System.Text.Json.JsonNamingPolicy.CamelCase>

<span data-ttu-id="8d0cb-449">기본값 집합을 지정하는 `JsonSerializerOptions` 생성자는 .NET Core 3.1에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-449">A `JsonSerializerOptions` constructor that specifies a set of defaults is not available in .NET Core 3.1.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="8d0cb-450">HttpClient 및 Httpclient 확장 메서드</span><span class="sxs-lookup"><span data-stu-id="8d0cb-450">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="8d0cb-451">네트워크에서 JSON 페이로드를 직렬화 및 역직렬화하는 작업은 일반적인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-451">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="8d0cb-452">[HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) 및 [Httpclient](xref:System.Net.Http.Json.HttpContentJsonExtensions) 확장 메서드를 사용하면 코드 한 줄로 이러한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-452">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="8d0cb-453">이러한 확장 메서드는 [JsonSerializerOptions의 웹 기본값](#web-defaults-for-jsonserializeroptions)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-453">These extension methods use [web defaults for JsonSerializerOptions](#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="8d0cb-454">다음 예제는 <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> 및 <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-454">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="23,30":::

<span data-ttu-id="8d0cb-455">[HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions)에는 System.Text.Json의 확장 메서드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-455">There are also extension methods for System.Text.Json on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="8d0cb-456">`HttpClient` 및 `HttpContent`의 확장 메서드는 .NET Core 3.1의 System.Text.Json에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-456">Extension methods on `HttpClient` and `HttpContent` are not available in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="8d0cb-457">Utf8JsonReader, Utf8JsonWriter 및 JsonDocument</span><span class="sxs-lookup"><span data-stu-id="8d0cb-457">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="8d0cb-458"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>은 `ReadOnlySpan<byte>` 또는 `ReadOnlySequence<byte>`에서 읽어온 UTF-8 인코딩 JSON 텍스트를 위한 고성능, 저할당, 전달 전용 판독기입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-458"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="8d0cb-459">`Utf8JsonReader`는 사용자 지정 구문 분석기 및 역직렬 변환기를 빌드하는 데 활용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-459">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="8d0cb-460"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonReader`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-460">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="8d0cb-461"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>은 `String`, `Int32` 및 `DateTime`과 같은 일반적인 .NET 형식에서 UTF-8 인코딩 JSON 텍스트를 쓸 수 있는 고성능 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-461"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="8d0cb-462">writer는 사용자 지정 직렬 변환기를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-462">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="8d0cb-463"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonWriter`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-463">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="8d0cb-464"><xref:System.Text.Json.JsonDocument?displayProperty=fullName>은 `Utf8JsonReader`를 사용하여 읽기 전용 DOM(문서 개체 모델)을 빌드하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-464"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="8d0cb-465">DOM은 JSON 페이로드의 데이터에 대한 임의 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-465">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="8d0cb-466">페이로드를 구성하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-466">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="8d0cb-467">`JsonElement` 형식은 JSON 텍스트를 일반적인 .NET 형식으로 변환하는 API와 함께 배열 및 개체 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-467">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="8d0cb-468">`JsonDocument`는 <xref:System.Text.Json.JsonDocument.RootElement> 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-468">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="8d0cb-469">다음 섹션에서는 이러한 도구를 사용하여 JSON을 읽고 쓰는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-469">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="8d0cb-470">JsonDocument를 사용하여 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="8d0cb-470">Use JsonDocument for access to data</span></span>

<span data-ttu-id="8d0cb-471">다음 예제에서는 <xref:System.Text.Json.JsonDocument> 클래스를 사용하여 JSON 문자열의 데이터에 임의로 액세스하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-471">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="8d0cb-472">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="8d0cb-472">The preceding code:</span></span>

* <span data-ttu-id="8d0cb-473">분석할 JSON은 `jsonString`이라는 문자열에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-473">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="8d0cb-474">`Grade` 속성이 있는 `Students` 배열의 개체에 대한 평균 등급을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-474">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="8d0cb-475">등급이 없는 학생에게 기본 등급 70을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-475">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="8d0cb-476">반복마다 `count` 변수를 늘려서 학생 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-476">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="8d0cb-477">다음 예제처럼 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>를 호출하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-477">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="8d0cb-478">다음은 이 코드가 처리하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-478">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="8d0cb-479">JsonDocument를 사용하여 JSON 쓰기</span><span class="sxs-lookup"><span data-stu-id="8d0cb-479">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="8d0cb-480">다음 예제에서는 <xref:System.Text.Json.JsonDocument>에서 JSON을 쓰는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-480">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="8d0cb-481">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="8d0cb-481">The preceding code:</span></span>

* <span data-ttu-id="8d0cb-482">JSON 파일을 읽고, `JsonDocument`에 데이터를 로드하고, 서식 있는(보기 좋게 출력된) JSON을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-482">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="8d0cb-483"><xref:System.Text.Json.JsonDocumentOptions>를 사용하여 입력 JSON의 주석을 허용하지만 무시하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-483">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="8d0cb-484">완료되면 writer에서 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-484">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="8d0cb-485">삭제될 때 writer가 자동으로 플러시하도록 설정하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-485">An alternative is to let the writer autoflush when it's disposed.</span></span>

<span data-ttu-id="8d0cb-486">다음은 예제 코드에서 처리할 JSON 입력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-486">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Grades.json)]

<span data-ttu-id="8d0cb-487">결과는 다음과 같이 보기 좋게 출력된 JSON 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-487">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="8d0cb-488">Utf8JsonWriter 사용</span><span class="sxs-lookup"><span data-stu-id="8d0cb-488">Use Utf8JsonWriter</span></span>

<span data-ttu-id="8d0cb-489">다음 예제에서는 <xref:System.Text.Json.Utf8JsonWriter> 클래스 사용 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-489">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="8d0cb-490">Utf8JsonReader 사용</span><span class="sxs-lookup"><span data-stu-id="8d0cb-490">Use Utf8JsonReader</span></span>

<span data-ttu-id="8d0cb-491">다음 예제에서는 <xref:System.Text.Json.Utf8JsonReader> 클래스 사용 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-491">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="8d0cb-492">위의 코드는 `jsonUtf8` 변수가 UTF-8로 인코딩된 유효한 JSON을 포함하는 바이트 배열이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-492">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="8d0cb-493">Utf8JsonReader를 사용하여 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="8d0cb-493">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="8d0cb-494">다음 예제에서는 파일을 동기적으로 읽고 값을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-494">The following example shows how to read a file synchronously and search for a value.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="8d0cb-495">[이 예제의 비동기 버전](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs)을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-495">(An [async version of this example](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs) is available.)</span></span>

<span data-ttu-id="8d0cb-496">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="8d0cb-496">The preceding code:</span></span>

* <span data-ttu-id="8d0cb-497">JSON에 개체 배열이 포함되고 각 개체에 문자열 형식의 "name" 속성이 포함될 수 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-497">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="8d0cb-498">"대학교"로 끝나는 개체 및 "이름" 속성 값의 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-498">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="8d0cb-499">파일이 UTF-16으로 인코딩되고 UTF-8로 코드 변환된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-499">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="8d0cb-500">UTF-8로 인코딩된 파일은 다음 코드를 사용하여 `ReadOnlySpan<byte>`로 직접 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-500">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="8d0cb-501">파일에 UTF-8 BOM(바이트 순서 표시)이 포함된 경우 제거한 후 바이트를 `Utf8JsonReader`에 전달해야 합니다. 판독기에는 텍스트가 필요하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-501">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="8d0cb-502">그렇지 않으면 BOM은 잘못된 JSON으로 간주되고, 판독기에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-502">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="8d0cb-503">다음은 위의 코드에서 읽을 수 있는 JSON 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-503">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="8d0cb-504">다음과 같이 "4개 이름 중 2개가 '대학교'로 끝나는 이름"이라는 결과 요약 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-504">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](snippets/system-text-json-how-to/csharp/Universities.json)]

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="8d0cb-505">Utf8JsonReader를 사용하여 스트림에서 읽기</span><span class="sxs-lookup"><span data-stu-id="8d0cb-505">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="8d0cb-506">큰 파일(예: 기가바이트 이상 크기)을 읽을 때 전체 파일을 한 번에 메모리에 로드하지 않아도 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-506">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="8d0cb-507">이 시나리오에서는 <xref:System.IO.FileStream>을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-507">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="8d0cb-508">`Utf8JsonReader`를 사용하여 스트림에서 읽는 경우 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-508">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="8d0cb-509">부분 JSON 페이로드를 포함하는 버퍼는 판독기가 진행할 수 있도록 최소한 그 안에 있는 가장 큰 JSON 토큰만큼 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-509">The buffer containing the partial JSON payload must be at least as large as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="8d0cb-510">버퍼는 최소한 JSON 내에서 가장 큰 공백 시퀀스만큼 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-510">The buffer must be at least as large as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="8d0cb-511">판독기는 JSON 페이로드의 다음 <xref:System.Text.Json.Utf8JsonReader.TokenType%2A>을 완전히 읽을 때까지는 읽은 데이터를 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-511">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="8d0cb-512">따라서 버퍼에 바이트가 남아 있으면 판독기에 다시 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-512">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="8d0cb-513"><xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A>를 사용하여 남은 바이트 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-513">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="8d0cb-514">다음 코드에서는 스트림에서 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-514">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="8d0cb-515">이 예제에서는 <xref:System.IO.MemoryStream>을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-515">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="8d0cb-516">`FileStream`이 시작 시 UTF-8 BOM을 포함하는 경우를 제외하고는 <xref:System.IO.FileStream>에서 비슷한 코드가 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-516">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="8d0cb-517">이 경우 남은 바이트를 `Utf8JsonReader`에 전달하기 전에 버퍼에서 3바이트를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-517">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="8d0cb-518">그렇지 않으면 BOM이 JSON의 유효한 부분으로 간주되지 않으므로 판독기가 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-518">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="8d0cb-519">이 샘플 코드는 4KB 버퍼로 시작하며 크기가 작아 전체 JSON 토큰을 수용할 수 없을 때마다 버퍼 크기를 두 배로 늘립니다. 이는 판독기가 JSON 페이로드에 대한 작업을 진행하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-519">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not large enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="8d0cb-520">이 코드 조각에 제공된 JSON 샘플은 10바이트와 같이 매우 작은 초기 버퍼 크기를 설정하는 경우에만 버퍼 크기 증가를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-520">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="8d0cb-521">초기 버퍼 크기를 10으로 설정하는 경우 `Console.WriteLine` 문은 버퍼 크기 증가의 원인과 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-521">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="8d0cb-522">4KB 초기 버퍼 크기에서 전체 샘플 JSON은 각 `Console.WriteLine`마다 표시되며 버퍼 크기를 늘릴 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-522">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

[!code-csharp[](snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs)]

<span data-ttu-id="8d0cb-523">앞의 예제에서는 버퍼 크기를 늘릴 수 있는 크기 제한을 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-523">The preceding example sets no limit to how large the buffer can grow.</span></span> <span data-ttu-id="8d0cb-524">토큰 크기가 너무 클 경우 코드는 <xref:System.OutOfMemoryException> 예외와 함께 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-524">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="8d0cb-525">이 문제는 JSON이 크기가 약 1GB 이상인 토큰을 포함하는 경우 발생할 수 있습니다. 1GB 크기가 두 배가 되면 `int32` 버퍼에 비해 너무 커지기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="8d0cb-525">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="8d0cb-526">추가 자료</span><span class="sxs-lookup"><span data-stu-id="8d0cb-526">Additional resources</span></span>

* [<span data-ttu-id="8d0cb-527">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="8d0cb-527">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="8d0cb-528">사용자 지정 변환기를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="8d0cb-528">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="8d0cb-529">Newtonsoft.Json에서 마이그레이션하는 방법</span><span class="sxs-lookup"><span data-stu-id="8d0cb-529">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="8d0cb-530">System.Text.Json의 DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="8d0cb-530">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="8d0cb-531">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="8d0cb-531">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
