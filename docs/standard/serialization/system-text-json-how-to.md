---
title: C#을 사용하여 JSON을 직렬화 및 역직렬화하는 방법 - .NET
description: System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 알아봅니다. 샘플 코드가 포함되어 있습니다.
ms.date: 11/30/2020
ms.custom: contperfq2
no-loc:
- System.Text.Json
- Newtonsoft.Json
zone_pivot_groups: dotnet-version
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: 9ea9e2fef5ef66f2a5ff816168abfbd7b2e75276
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96437680"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="404b3-104">.NET에서 JSON을 직렬화 및 역직렬화(마샬링 및 역 마샬링)하는 방법</span><span class="sxs-lookup"><span data-stu-id="404b3-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="404b3-105">이 문서에서는 <xref:System.Text.Json?displayProperty=fullName> 네임스페이스를 사용하여 JSON(JavaScript Object Notation)으로 직렬화와 JSON으로부터 역직렬화하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="404b3-106">`Newtonsoft.Json`에서 기존 코드를 이식하는 경우 [`System.Text.Json`으로 마이그레이션 방법](system-text-json-migrate-from-newtonsoft-how-to.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="404b3-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="404b3-107">지침 및 샘플 코드에서는 [ASP.NET Core](/aspnet/core/) 같은 프레임워크를 통하지 않고 직접 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="404b3-108">대부분의 직렬화 샘플 코드는 JSON을 "보기 좋게 출력"하도록(사람이 읽기 쉽도록 들여쓰기 및 공백 사용) <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="404b3-109">프로덕션에 사용하는 경우에는 일반적으로 이 설정의 기본값인 `false`를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="404b3-110">코드 예제에서는 다음 클래스와 그 변형을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-110">The code examples refer to the following class and variants of it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a><span data-ttu-id="404b3-111">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="404b3-111">Namespaces</span></span>

<span data-ttu-id="404b3-112"><xref:System.Text.Json> 네임스페이스에는 모든 진입점과 기본 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="404b3-113"><xref:System.Text.Json.Serialization> 네임스페이스에는 직렬화 및 역직렬화와 관련된 고급 시나리오 및 사용자 지정을 위한 특성과 API가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="404b3-114">이 문서의 코드 예제에서는 두 네임스페이스 중 하나 또는 둘 다에 `using` 지시문이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> <span data-ttu-id="404b3-115"><xref:System.Runtime.Serialization> 네임스페이스의 특성은 `System.Text.Json`에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-as-json-serialize"></a><span data-ttu-id="404b3-116">.NET 개체를 JSON으로 쓰는 방법(직렬화)</span><span class="sxs-lookup"><span data-stu-id="404b3-116">How to write .NET objects as JSON (serialize)</span></span>

<span data-ttu-id="404b3-117">문자열 또는 파일에 JSON을 쓰려면 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="404b3-118">다음은 JSON 파일을 문자열로 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-118">The following example creates JSON as a string:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

<span data-ttu-id="404b3-119">다음은 동기 코드를 사용하여 JSON 파일을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-119">The following example uses synchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

<span data-ttu-id="404b3-120">다음은 비동기 코드를 사용하여 JSON 파일을 만드는 예지입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-120">The following example uses asynchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

<span data-ttu-id="404b3-121">앞의 예제에서는 직렬화되는 형식에 형식 유추를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="404b3-122">`Serialize()`의 오버로드는 제네릭 형식 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a><span data-ttu-id="404b3-123">직렬화 예제</span><span class="sxs-lookup"><span data-stu-id="404b3-123">Serialization example</span></span>

<span data-ttu-id="404b3-124">다음은 수집 유형 속성과 사용자 정의 형식을 포함하는 예제 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> <span data-ttu-id="404b3-125">"POCO"는 [Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_old_CLR_object)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="404b3-126">POCO는 예를 들어 상속 또는 속성을 통해 프레임워크별 형식에 의존하지 않는 .NET 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="404b3-127">다음은 이전 형식의 인스턴스를 직렬화하는 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="404b3-128">JSON 출력은 기본적으로 축소됩니다(공백, 들여쓰기, 줄 바꿈 문자가 제거됨).</span><span class="sxs-lookup"><span data-stu-id="404b3-128">The JSON output is minified (whitespace, indentation, and new-line characters are removed) by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="404b3-129">다음 예제에서는 동일한 JSON 형식을 보여주지만 다음과 같은 형식이 지정됩니다(공백 및 들여쓰기를 사용하여 보기 좋게 인쇄됨).</span><span class="sxs-lookup"><span data-stu-id="404b3-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

## <a name="serialize-to-utf-8"></a><span data-ttu-id="404b3-130">UTF-8로 직렬화</span><span class="sxs-lookup"><span data-stu-id="404b3-130">Serialize to UTF-8</span></span>

<span data-ttu-id="404b3-131">UTF-8로 직렬화하려면 다음과 같이 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-131">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

<span data-ttu-id="404b3-132"><xref:System.Text.Json.Utf8JsonWriter>를 사용하는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버로드도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-132">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="404b3-133">UTF-8로 직렬화하면 문자열 기반 메서드를 사용할 때보다 약 5-10% 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="404b3-134">속도에서 차이가 나는 이유는 바이트(UTF-8)를 문자열(UTF-16)로 변환할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="404b3-135">Serialization 동작</span><span class="sxs-lookup"><span data-stu-id="404b3-135">Serialization behavior</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="404b3-136">기본적으로 모든 public 속성은 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="404b3-137">[무시할 속성을 지정](system-text-json-ignore-properties.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-137">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="404b3-138">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)는 ASCII가 아닌 문자, ASCII 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프되어야 하는 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="404b3-139">기본적으로 JSON은 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-139">By default, JSON is minified.</span></span> <span data-ttu-id="404b3-140">[JSON을 보기 좋게 출력](#serialize-to-formatted-json)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="404b3-141">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="404b3-142">[JSON 이름 대/소문자를 사용자 지정](system-text-json-customize-properties.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-142">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="404b3-143">기본적으로 순환 참조가 검색되고 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="404b3-144">[참조를 보존하고 순환 참조를 처리](system-text-json-preserve-references.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-144">You can [preserve references and handle circular references](system-text-json-preserve-references.md).</span></span>
* <span data-ttu-id="404b3-145">기본적으로 [필드](../../csharp/programming-guide/classes-and-structs/fields.md)는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="404b3-146">[필드를 포함](#include-fields)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="404b3-147">ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-147">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="404b3-148">자세한 내용은 [JsonSerializerOptions 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="404b3-148">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="404b3-149">기본적으로 모든 public 속성은 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="404b3-150">[무시할 속성을 지정](system-text-json-ignore-properties.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-150">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="404b3-151">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)는 ASCII가 아닌 문자, ASCII 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프되어야 하는 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="404b3-152">기본적으로 JSON은 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-152">By default, JSON is minified.</span></span> <span data-ttu-id="404b3-153">[JSON을 보기 좋게 출력](#serialize-to-formatted-json)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="404b3-154">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="404b3-155">[JSON 이름 대/소문자를 사용자 지정](system-text-json-customize-properties.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-155">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="404b3-156">순환 참조가 감지되고 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="404b3-157">[필드](../../csharp/programming-guide/classes-and-structs/fields.md)는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="404b3-158">지원되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="404b3-159">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="404b3-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="404b3-160">사용자 정의 [POCO(Plain Old CLR Object)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="404b3-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="404b3-161">1차원 및 가변 배열(`T[][]`)</span><span class="sxs-lookup"><span data-stu-id="404b3-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="404b3-162">다음 네임스페이스의 컬렉션 및 사전.</span><span class="sxs-lookup"><span data-stu-id="404b3-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="404b3-163">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="404b3-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="404b3-164">사용자 정의 [POCO(Plain Old CLR Object)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="404b3-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="404b3-165">1차원 및 가변 배열(`ArrayName[][]`)</span><span class="sxs-lookup"><span data-stu-id="404b3-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="404b3-166">`Dictionary<string,TValue>`. 여기서 `TValue`는 `object`, `JsonElement` 또는 POCO입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="404b3-167">다음 네임스페이스의 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="404b3-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="404b3-168">추가 형식을 처리하거나 기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-as-net-objects-deserialize"></a><span data-ttu-id="404b3-169">JSON을 .NET 개체로 읽는 방법(역직렬화)</span><span class="sxs-lookup"><span data-stu-id="404b3-169">How to read JSON as .NET objects (deserialize)</span></span>

<span data-ttu-id="404b3-170">문자열 또는 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-170">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="404b3-171">다음 예제에서는 문자열에서 JSON을 읽고, 앞에서 [직렬화 예제](#serialization-example)에서 설명한 `WeatherForecastWithPOCOs` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

<span data-ttu-id="404b3-172">동기 코드를 사용하여 파일에서 역직렬화하려면 다음 예제와 같이 파일을 문자열로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

<span data-ttu-id="404b3-173">비동기 코드를 사용하여 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-173">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a><span data-ttu-id="404b3-174">UTF-8에서 역직렬화</span><span class="sxs-lookup"><span data-stu-id="404b3-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="404b3-175">UTF-8에서 역직렬화하려면 다음 예제와 같이 `ReadOnlySpan<byte>` 또는 `Utf8JsonReader`을 사용하는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-175">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `ReadOnlySpan<byte>` or a `Utf8JsonReader`, as shown in the following examples.</span></span> <span data-ttu-id="404b3-176">이 예제에서는 JSON이 jsonUtf8Bytes라는 바이트 배열에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a><span data-ttu-id="404b3-177">역직렬화 동작</span><span class="sxs-lookup"><span data-stu-id="404b3-177">Deserialization behavior</span></span>

<span data-ttu-id="404b3-178">JSON을 역직렬화할 때 다음 동작이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="404b3-179">속성 이름 일치 시에 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="404b3-180">[대/소문자를 구분 하지 않도록 지정](system-text-json-character-casing.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-180">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span>
* <span data-ttu-id="404b3-181">JSON에 읽기 전용 속성의 값이 포함되어 있으면 해당 값이 무시되고 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="404b3-182">public이 아닌 생성자는 직렬 변환기에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="404b3-183">변경 불가능한 개체 또는 읽기 전용 속성으로의 역직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="404b3-184">[변경 불가능한 형식 및 레코드](system-text-json-immutability.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="404b3-184">See [Immutable types and Records](system-text-json-immutability.md).</span></span>
* <span data-ttu-id="404b3-185">기본적으로 열거형은 숫자로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="404b3-186">[열거형 이름을 문자열로 직렬화](system-text-json-customize-properties.md#enums-as-strings)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-186">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="404b3-187">기본적으로 필드는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-187">By default, fields are ignored.</span></span> <span data-ttu-id="404b3-188">[필드를 포함](#include-fields)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="404b3-189">기본적으로 JSON의 주석이나 후행 쉼표는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="404b3-190">[주석과 후행 쉼표를 허용](system-text-json-invalid-json.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-190">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="404b3-191">[기본 최댓값](xref:System.Text.Json.JsonReaderOptions.MaxDepth)은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-191">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="404b3-192">ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-192">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="404b3-193">자세한 내용은 [JsonSerializerOptions 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="404b3-193">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="404b3-194">속성 이름 일치 시에 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="404b3-195">[대/소문자를 구분 하지 않도록 지정](system-text-json-character-casing.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-195">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span> <span data-ttu-id="404b3-196">ASP.NET Core 앱은[대/소문자 구분 사용 안 함을 기본값으로 지정](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-196">ASP.NET Core apps [specify case-insensitivity by default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="404b3-197">JSON에 읽기 전용 속성의 값이 포함되어 있으면 해당 값이 무시되고 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="404b3-198">public, internal 또는 private일 수 있는 매개 변수가 없는 생성자가 역직렬화에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="404b3-199">변경할 수 없는 개체 또는 읽기 전용 속성으로의 역직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="404b3-200">기본적으로 열거형은 숫자로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="404b3-201">[열거형 이름을 문자열로 직렬화](system-text-json-customize-properties.md#enums-as-strings)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-201">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="404b3-202">필드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-202">Fields aren't supported.</span></span>
* <span data-ttu-id="404b3-203">기본적으로 JSON의 주석이나 후행 쉼표는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="404b3-204">[주석과 후행 쉼표를 허용](system-text-json-invalid-json.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-204">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="404b3-205">[기본 최댓값](xref:System.Text.Json.JsonReaderOptions.MaxDepth)은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-205">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="404b3-206">ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-206">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="404b3-207">자세한 내용은 [JsonSerializerOptions 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="404b3-207">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="404b3-208">기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="404b3-209">형식이 지정된 JSON으로 직렬화</span><span class="sxs-lookup"><span data-stu-id="404b3-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="404b3-210">JSON 출력을 보기 좋게 출력하려면 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-210">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

<span data-ttu-id="404b3-211">다음 형식은 직렬화하여 보기 좋게 출력할 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="include-fields"></a><span data-ttu-id="404b3-212">필드 포함</span><span class="sxs-lookup"><span data-stu-id="404b3-212">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="404b3-213">다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> 전역 설정 또는 [JsonInclude](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 특성을 사용하여 직렬화 또는 역직렬화할 때의 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-213">Use the <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

<span data-ttu-id="404b3-214">읽기 전용 필드를 무시하려면 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 전역 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-214">To ignore read-only fields, use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="404b3-215">.NET Core 3.1의 System.Text.Json에서는 필드가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-215">Fields are not supported in System.Text.Json in .NET Core 3.1.</span></span> <span data-ttu-id="404b3-216">[사용자 지정 변환기](system-text-json-converters-how-to.md)는 이 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-216">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="404b3-217">HttpClient 및 Httpclient 확장 메서드</span><span class="sxs-lookup"><span data-stu-id="404b3-217">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="404b3-218">네트워크에서 JSON 페이로드를 직렬화 및 역직렬화하는 작업은 일반적인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-218">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="404b3-219">[HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) 및 [Httpclient](xref:System.Net.Http.Json.HttpContentJsonExtensions) 확장 메서드를 사용하면 코드 한 줄로 이러한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-219">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="404b3-220">이러한 확장 메서드는 [JsonSerializerOptions의 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-220">These extension methods use [web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="404b3-221">다음 예제는 <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> 및 <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-221">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

<span data-ttu-id="404b3-222">[HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions)에는 System.Text.Json의 확장 메서드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-222">There are also extension methods for System.Text.Json on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="404b3-223">`HttpClient` 및 `HttpContent`의 확장 메서드는 .NET Core 3.1의 System.Text.Json에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="404b3-223">Extension methods on `HttpClient` and `HttpContent` are not available in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="404b3-224">참고 항목</span><span class="sxs-lookup"><span data-stu-id="404b3-224">See also</span></span>

* [<span data-ttu-id="404b3-225">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="404b3-225">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="404b3-226">사용자 지정 변환기를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="404b3-226">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="404b3-227">Newtonsoft.Json에서 마이그레이션하는 방법</span><span class="sxs-lookup"><span data-stu-id="404b3-227">How to migrate from Newtonsoft.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="404b3-228">System.Text.Json의 DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="404b3-228">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="404b3-229">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="404b3-229">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
