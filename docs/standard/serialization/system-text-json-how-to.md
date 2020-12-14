---
title: C#을 사용하여 JSON을 직렬화 및 역직렬화하는 방법 - .NET
description: System.Text.Json 네임스페이스를 사용하여 .NET에서 JSON으로 직렬화 및 역직렬화하는 방법을 알아봅니다. 샘플 코드가 포함되어 있습니다.
ms.date: 12/02/2020
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
ms.openlocfilehash: 1ea4ff71b9e21bd7c5b12598581b33e1e96ebb19
ms.sourcegitcommit: 81f1bba2c97a67b5ca76bcc57b37333ffca60c7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2020
ms.locfileid: "97008840"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="1d1a9-104">.NET에서 JSON을 직렬화 및 역직렬화(마샬링 및 역 마샬링)하는 방법</span><span class="sxs-lookup"><span data-stu-id="1d1a9-104">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="1d1a9-105">이 문서에서는 <xref:System.Text.Json?displayProperty=fullName> 네임스페이스를 사용하여 JSON(JavaScript Object Notation)으로 직렬화와 JSON으로부터 역직렬화하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-105">This article shows how to use the <xref:System.Text.Json?displayProperty=fullName> namespace to serialize to and deserialize from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="1d1a9-106">`Newtonsoft.Json`에서 기존 코드를 이식하는 경우 [`System.Text.Json`으로 마이그레이션 방법](system-text-json-migrate-from-newtonsoft-how-to.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-106">If you're porting existing code from `Newtonsoft.Json`, see [How to migrate to `System.Text.Json`](system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

<span data-ttu-id="1d1a9-107">지침 및 샘플 코드에서는 [ASP.NET Core](/aspnet/core/) 같은 프레임워크를 통하지 않고 직접 라이브러리를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="1d1a9-108">대부분의 직렬화 샘플 코드는 JSON을 "보기 좋게 출력"하도록(사람이 읽기 쉽도록 들여쓰기 및 공백 사용) <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-108">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="1d1a9-109">프로덕션에 사용하는 경우에는 일반적으로 이 설정의 기본값인 `false`를 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-109">For production use, you would typically accept the default value of `false` for this setting.</span></span>

<span data-ttu-id="1d1a9-110">코드 예제에서는 다음 클래스와 그 변형을 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-110">The code examples refer to the following class and variants of it:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

## <a name="namespaces"></a><span data-ttu-id="1d1a9-111">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="1d1a9-111">Namespaces</span></span>

<span data-ttu-id="1d1a9-112"><xref:System.Text.Json> 네임스페이스에는 모든 진입점과 기본 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-112">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="1d1a9-113"><xref:System.Text.Json.Serialization> 네임스페이스에는 직렬화 및 역직렬화와 관련된 고급 시나리오 및 사용자 지정을 위한 특성과 API가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-113">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="1d1a9-114">이 문서의 코드 예제에서는 두 네임스페이스 중 하나 또는 둘 다에 `using` 지시문이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-114">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

> [!IMPORTANT]
> <span data-ttu-id="1d1a9-115"><xref:System.Runtime.Serialization> 네임스페이스의 특성은 `System.Text.Json`에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-115">Attributes from the <xref:System.Runtime.Serialization> namespace aren't supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-as-json-serialize"></a><span data-ttu-id="1d1a9-116">.NET 개체를 JSON으로 쓰는 방법(직렬화)</span><span class="sxs-lookup"><span data-stu-id="1d1a9-116">How to write .NET objects as JSON (serialize)</span></span>

<span data-ttu-id="1d1a9-117">문자열 또는 파일에 JSON을 쓰려면 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-117">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1d1a9-118">다음은 JSON 파일을 문자열로 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-118">The following example creates JSON as a string:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Serialize":::

<span data-ttu-id="1d1a9-119">다음은 동기 코드를 사용하여 JSON 파일을 만드는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-119">The following example uses synchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Serialize":::

<span data-ttu-id="1d1a9-120">다음은 비동기 코드를 사용하여 JSON 파일을 만드는 예지입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-120">The following example uses asynchronous code to create a JSON file:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Serialize":::

<span data-ttu-id="1d1a9-121">앞의 예제에서는 직렬화되는 형식에 형식 유추를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-121">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="1d1a9-122">`Serialize()`의 오버로드는 제네릭 형식 매개 변수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-122">An overload of `Serialize()` takes a generic type parameter:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializeWithGenericParameter":::

### <a name="serialization-example"></a><span data-ttu-id="1d1a9-123">직렬화 예제</span><span class="sxs-lookup"><span data-stu-id="1d1a9-123">Serialization example</span></span>

<span data-ttu-id="1d1a9-124">다음은 수집 유형 속성과 사용자 정의 형식을 포함하는 예제 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-124">Here's an example class that contains collection-type properties and a user-defined type:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WFWithPOCOs":::

> [!TIP]
> <span data-ttu-id="1d1a9-125">"POCO"는 [Plain Old CLR Object](https://en.wikipedia.org/wiki/Plain_old_CLR_object)를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-125">"POCO" stands for [plain old CLR object](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span> <span data-ttu-id="1d1a9-126">POCO는 예를 들어 상속 또는 속성을 통해 프레임워크별 형식에 의존하지 않는 .NET 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-126">A POCO is a .NET type that doesn't depend on any framework-specific types, for example, through inheritance or attributes.</span></span>

<span data-ttu-id="1d1a9-127">다음은 이전 형식의 인스턴스를 직렬화하는 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-127">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="1d1a9-128">JSON 출력은 기본적으로 축소됩니다(공백, 들여쓰기, 줄 바꿈 문자가 제거됨).</span><span class="sxs-lookup"><span data-stu-id="1d1a9-128">The JSON output is minified (whitespace, indentation, and new-line characters are removed) by default:</span></span>

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="1d1a9-129">다음 예제에서는 동일한 JSON 형식을 보여주지만 다음과 같은 형식이 지정됩니다(공백 및 들여쓰기를 사용하여 보기 좋게 인쇄됨).</span><span class="sxs-lookup"><span data-stu-id="1d1a9-129">The following example shows the same JSON, but formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

## <a name="serialize-to-utf-8"></a><span data-ttu-id="1d1a9-130">UTF-8로 직렬화</span><span class="sxs-lookup"><span data-stu-id="1d1a9-130">Serialize to UTF-8</span></span>

<span data-ttu-id="1d1a9-131">UTF-8로 직렬화하려면 다음과 같이 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-131">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Serialize":::

<span data-ttu-id="1d1a9-132"><xref:System.Text.Json.Utf8JsonWriter>를 사용하는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버로드도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-132">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="1d1a9-133">UTF-8로 직렬화하면 문자열 기반 메서드를 사용할 때보다 약 5-10% 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-133">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="1d1a9-134">속도에서 차이가 나는 이유는 바이트(UTF-8)를 문자열(UTF-16)로 변환할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-134">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="1d1a9-135">Serialization 동작</span><span class="sxs-lookup"><span data-stu-id="1d1a9-135">Serialization behavior</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="1d1a9-136">기본적으로 모든 public 속성은 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-136">By default, all public properties are serialized.</span></span> <span data-ttu-id="1d1a9-137">[무시할 속성을 지정](system-text-json-ignore-properties.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-137">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="1d1a9-138">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)는 ASCII가 아닌 문자, ASCII 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프되어야 하는 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-138">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="1d1a9-139">기본적으로 JSON은 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-139">By default, JSON is minified.</span></span> <span data-ttu-id="1d1a9-140">[JSON을 보기 좋게 출력](#serialize-to-formatted-json)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-140">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="1d1a9-141">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-141">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="1d1a9-142">[JSON 이름 대/소문자를 사용자 지정](system-text-json-customize-properties.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-142">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="1d1a9-143">기본적으로 순환 참조가 검색되고 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-143">By default, circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="1d1a9-144">[참조를 보존하고 순환 참조를 처리](system-text-json-preserve-references.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-144">You can [preserve references and handle circular references](system-text-json-preserve-references.md).</span></span>
* <span data-ttu-id="1d1a9-145">기본적으로 [필드](../../csharp/programming-guide/classes-and-structs/fields.md)는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-145">By default, [fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span> <span data-ttu-id="1d1a9-146">[필드를 포함](#include-fields)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-146">You can [include fields](#include-fields).</span></span>

<span data-ttu-id="1d1a9-147">ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-147">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="1d1a9-148">자세한 내용은 [JsonSerializerOptions 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-148">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="1d1a9-149">기본적으로 모든 public 속성은 직렬화됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-149">By default, all public properties are serialized.</span></span> <span data-ttu-id="1d1a9-150">[무시할 속성을 지정](system-text-json-ignore-properties.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-150">You can [specify properties to ignore](system-text-json-ignore-properties.md).</span></span>
* <span data-ttu-id="1d1a9-151">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default)는 ASCII가 아닌 문자, ASCII 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프되어야 하는 문자를 이스케이프합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-151">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="1d1a9-152">기본적으로 JSON은 축소됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-152">By default, JSON is minified.</span></span> <span data-ttu-id="1d1a9-153">[JSON을 보기 좋게 출력](#serialize-to-formatted-json)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-153">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="1d1a9-154">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-154">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="1d1a9-155">[JSON 이름 대/소문자를 사용자 지정](system-text-json-customize-properties.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-155">You can [customize JSON name casing](system-text-json-customize-properties.md).</span></span>
* <span data-ttu-id="1d1a9-156">순환 참조가 감지되고 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-156">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="1d1a9-157">[필드](../../csharp/programming-guide/classes-and-structs/fields.md)는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-157">[Fields](../../csharp/programming-guide/classes-and-structs/fields.md) are ignored.</span></span>
::: zone-end

<span data-ttu-id="1d1a9-158">지원되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-158">Supported types include:</span></span>
::: zone pivot="dotnet-5-0"

* <span data-ttu-id="1d1a9-159">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="1d1a9-159">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="1d1a9-160">사용자 정의 [POCO(Plain Old CLR Object)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="1d1a9-160">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="1d1a9-161">1차원 및 가변 배열(`T[][]`)</span><span class="sxs-lookup"><span data-stu-id="1d1a9-161">One-dimensional and jagged arrays (`T[][]`).</span></span>
* <span data-ttu-id="1d1a9-162">다음 네임스페이스의 컬렉션 및 사전.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-162">Collections and dictionaries from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="1d1a9-163">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식</span><span class="sxs-lookup"><span data-stu-id="1d1a9-163">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="1d1a9-164">사용자 정의 [POCO(Plain Old CLR Object)](https://en.wikipedia.org/wiki/Plain_old_CLR_object)</span><span class="sxs-lookup"><span data-stu-id="1d1a9-164">User-defined [plain old CLR objects (POCOs)](https://en.wikipedia.org/wiki/Plain_old_CLR_object).</span></span>
* <span data-ttu-id="1d1a9-165">1차원 및 가변 배열(`ArrayName[][]`)</span><span class="sxs-lookup"><span data-stu-id="1d1a9-165">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="1d1a9-166">`Dictionary<string,TValue>`. 여기서 `TValue`는 `object`, `JsonElement` 또는 POCO입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-166">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="1d1a9-167">다음 네임스페이스의 컬렉션.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-167">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>
  * <xref:System.Collections.Concurrent>
  * <xref:System.Collections.Specialized>
  * <xref:System.Collections.ObjectModel>
::: zone-end

<span data-ttu-id="1d1a9-168">추가 형식을 처리하거나 기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-168">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-as-net-objects-deserialize"></a><span data-ttu-id="1d1a9-169">JSON을 .NET 개체로 읽는 방법(역직렬화)</span><span class="sxs-lookup"><span data-stu-id="1d1a9-169">How to read JSON as .NET objects (deserialize)</span></span>

<span data-ttu-id="1d1a9-170">문자열 또는 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-170">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="1d1a9-171">다음 예제에서는 문자열에서 JSON을 읽고, 앞에서 [직렬화 예제](#serialization-example)에서 설명한 `WeatherForecastWithPOCOs` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-171">The following example reads JSON from a string and creates an instance of the `WeatherForecastWithPOCOs` class shown earlier for the [serialization example](#serialization-example):</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="Deserialize":::

<span data-ttu-id="1d1a9-172">동기 코드를 사용하여 파일에서 역직렬화하려면 다음 예제와 같이 파일을 문자열로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-172">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFile.cs" id="Deserialize":::

<span data-ttu-id="1d1a9-173">비동기 코드를 사용하여 파일에서 역직렬화하려면 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-173">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToFileAsync.cs" id="Deserialize":::

## <a name="deserialize-from-utf-8"></a><span data-ttu-id="1d1a9-174">UTF-8에서 역직렬화</span><span class="sxs-lookup"><span data-stu-id="1d1a9-174">Deserialize from UTF-8</span></span>

<span data-ttu-id="1d1a9-175">UTF-8에서 역직렬화하려면 다음 예제와 같이 `ReadOnlySpan<byte>` 또는 `Utf8JsonReader`을 사용하는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 오버로드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-175">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `ReadOnlySpan<byte>` or a `Utf8JsonReader`, as shown in the following examples.</span></span> <span data-ttu-id="1d1a9-176">이 예제에서는 JSON이 jsonUtf8Bytes라는 바이트 배열에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-176">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize1":::

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToUtf8.cs" id="Deserialize2":::

## <a name="deserialization-behavior"></a><span data-ttu-id="1d1a9-177">역직렬화 동작</span><span class="sxs-lookup"><span data-stu-id="1d1a9-177">Deserialization behavior</span></span>

<span data-ttu-id="1d1a9-178">JSON을 역직렬화할 때 다음 동작이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-178">The following behaviors apply when deserializing JSON:</span></span>

::: zone pivot="dotnet-5-0"

* <span data-ttu-id="1d1a9-179">속성 이름 일치 시에 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-179">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="1d1a9-180">[대/소문자를 구분 하지 않도록 지정](system-text-json-character-casing.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-180">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span>
* <span data-ttu-id="1d1a9-181">JSON에 읽기 전용 속성의 값이 포함되어 있으면 해당 값이 무시되고 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-181">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="1d1a9-182">public이 아닌 생성자는 직렬 변환기에서 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-182">Non-public constructors are ignored by the serializer.</span></span>
* <span data-ttu-id="1d1a9-183">변경 불가능한 개체 또는 읽기 전용 속성으로의 역직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-183">Deserialization to immutable objects or read-only properties is supported.</span></span> <span data-ttu-id="1d1a9-184">[변경 불가능한 형식 및 레코드](system-text-json-immutability.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-184">See [Immutable types and Records](system-text-json-immutability.md).</span></span>
* <span data-ttu-id="1d1a9-185">기본적으로 열거형은 숫자로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-185">By default, enums are supported as numbers.</span></span> <span data-ttu-id="1d1a9-186">[열거형 이름을 문자열로 직렬화](system-text-json-customize-properties.md#enums-as-strings)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-186">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="1d1a9-187">기본적으로 필드는 무시됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-187">By default, fields are ignored.</span></span> <span data-ttu-id="1d1a9-188">[필드를 포함](#include-fields)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-188">You can [include fields](#include-fields).</span></span>
* <span data-ttu-id="1d1a9-189">기본적으로 JSON의 주석이나 후행 쉼표는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-189">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="1d1a9-190">[주석과 후행 쉼표를 허용](system-text-json-invalid-json.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-190">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="1d1a9-191">[기본 최댓값](xref:System.Text.Json.JsonReaderOptions.MaxDepth)은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-191">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="1d1a9-192">ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-192">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="1d1a9-193">자세한 내용은 [JsonSerializerOptions 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-193">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"

* <span data-ttu-id="1d1a9-194">속성 이름 일치 시에 대/소문자를 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-194">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="1d1a9-195">[대/소문자를 구분 하지 않도록 지정](system-text-json-character-casing.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-195">You can [specify case-insensitivity](system-text-json-character-casing.md).</span></span> <span data-ttu-id="1d1a9-196">ASP.NET Core 앱은[대/소문자 구분 사용 안 함을 기본값으로 지정](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-196">ASP.NET Core apps [specify case-insensitivity by default](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
* <span data-ttu-id="1d1a9-197">JSON에 읽기 전용 속성의 값이 포함되어 있으면 해당 값이 무시되고 예외가 throw되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-197">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="1d1a9-198">public, internal 또는 private일 수 있는 매개 변수가 없는 생성자가 역직렬화에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-198">A parameterless constructor, which can be public, internal, or private, is used for deserialization.</span></span>
* <span data-ttu-id="1d1a9-199">변경할 수 없는 개체 또는 읽기 전용 속성으로의 역직렬화는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-199">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="1d1a9-200">기본적으로 열거형은 숫자로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-200">By default, enums are supported as numbers.</span></span> <span data-ttu-id="1d1a9-201">[열거형 이름을 문자열로 직렬화](system-text-json-customize-properties.md#enums-as-strings)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-201">You can [serialize enum names as strings](system-text-json-customize-properties.md#enums-as-strings).</span></span>
* <span data-ttu-id="1d1a9-202">필드는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-202">Fields aren't supported.</span></span>
* <span data-ttu-id="1d1a9-203">기본적으로 JSON의 주석이나 후행 쉼표는 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-203">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="1d1a9-204">[주석과 후행 쉼표를 허용](system-text-json-invalid-json.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-204">You can [allow comments and trailing commas](system-text-json-invalid-json.md).</span></span>
* <span data-ttu-id="1d1a9-205">[기본 최댓값](xref:System.Text.Json.JsonReaderOptions.MaxDepth)은 64입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-205">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="1d1a9-206">ASP.NET Core 앱에서 System.Text.Json을 간접적으로 사용하는 경우 몇 가지 기본 동작이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-206">When you use System.Text.Json indirectly in an ASP.NET Core app, some default behaviors are different.</span></span> <span data-ttu-id="1d1a9-207">자세한 내용은 [JsonSerializerOptions 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-207">For more information, see [Web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>
::: zone-end

<span data-ttu-id="1d1a9-208">기본 변환기에서 지원하지 않는 기능을 제공하는 [사용자 지정 변환기를 구현](system-text-json-converters-how-to.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-208">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="1d1a9-209">형식이 지정된 JSON으로 직렬화</span><span class="sxs-lookup"><span data-stu-id="1d1a9-209">Serialize to formatted JSON</span></span>

<span data-ttu-id="1d1a9-210">JSON 출력을 보기 좋게 출력하려면 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-210">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/RoundtripToString.cs" id="SerializePrettyPrint":::

<span data-ttu-id="1d1a9-211">다음 형식은 직렬화하여 보기 좋게 출력할 JSON 출력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-211">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/WeatherForecast.cs" id="WF":::

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="1d1a9-212">동일한 옵션으로 `JsonSerializerOptions`를 반복적으로 사용하는 경우 사용할 때마다 새 `JsonSerializerOptions` 인스턴스를 만들지 마세요.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-212">If you use `JsonSerializerOptions` repeatedly with the same options, don't create a new `JsonSerializerOptions` instance each time you use it.</span></span> <span data-ttu-id="1d1a9-213">모든 호출에 대해 동일한 인스턴스를 다시 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-213">Reuse the same instance for every call.</span></span> <span data-ttu-id="1d1a9-214">자세한 내용은 [JsonSerializerOptions 인스턴스 다시 사용](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-214">For more information, see [Reuse JsonSerializerOptions instances](system-text-json-configure-options.md#reuse-jsonserializeroptions-instances).</span></span>

## <a name="include-fields"></a><span data-ttu-id="1d1a9-215">필드 포함</span><span class="sxs-lookup"><span data-stu-id="1d1a9-215">Include fields</span></span>

::: zone pivot="dotnet-5-0"
<span data-ttu-id="1d1a9-216">다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> 전역 설정 또는 [JsonInclude](xref:System.Text.Json.Serialization.JsonIncludeAttribute) 특성을 사용하여 직렬화 또는 역직렬화할 때의 필드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-216">Use the <xref:System.Text.Json.JsonSerializerOptions.IncludeFields?displayProperty=nameWithType> global setting or the [[JsonInclude]](xref:System.Text.Json.Serialization.JsonIncludeAttribute) attribute to include fields when serializing or deserializing, as shown in the following example:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/Fields.cs" highlight="16,18,20,32-35":::

<span data-ttu-id="1d1a9-217">읽기 전용 필드를 무시하려면 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> 전역 설정을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-217">To ignore read-only fields, use the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyFields%2A?displayProperty=nameWithType> global setting.</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1d1a9-218">.NET Core 3.1의 System.Text.Json에서는 필드가 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-218">Fields are not supported in System.Text.Json in .NET Core 3.1.</span></span> <span data-ttu-id="1d1a9-219">[사용자 지정 변환기](system-text-json-converters-how-to.md)는 이 기능을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-219">[Custom converters](system-text-json-converters-how-to.md) can provide this functionality.</span></span>
::: zone-end

## <a name="httpclient-and-httpcontent-extension-methods"></a><span data-ttu-id="1d1a9-220">HttpClient 및 Httpclient 확장 메서드</span><span class="sxs-lookup"><span data-stu-id="1d1a9-220">HttpClient and HttpContent extension methods</span></span>

::: zone pivot="dotnet-5-0"

<span data-ttu-id="1d1a9-221">네트워크에서 JSON 페이로드를 직렬화 및 역직렬화하는 작업은 일반적인 작업입니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-221">Serializing and deserializing JSON payloads from the network are common operations.</span></span> <span data-ttu-id="1d1a9-222">[HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) 및 [Httpclient](xref:System.Net.Http.Json.HttpContentJsonExtensions) 확장 메서드를 사용하면 코드 한 줄로 이러한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-222">Extension methods on [HttpClient](xref:System.Net.Http.Json.HttpClientJsonExtensions) and [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions) let you do these operations in a single line of code.</span></span> <span data-ttu-id="1d1a9-223">이러한 확장 메서드는 [JsonSerializerOptions의 웹 기본값](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-223">These extension methods use [web defaults for JsonSerializerOptions](system-text-json-configure-options.md#web-defaults-for-jsonserializeroptions).</span></span>

<span data-ttu-id="1d1a9-224">다음 예제는 <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> 및 <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-224">The following example illustrates use of <xref:System.Net.Http.Json.HttpClientJsonExtensions.GetFromJsonAsync%2A?displayProperty=nameWithType> and <xref:System.Net.Http.Json.HttpClientJsonExtensions.PostAsJsonAsync%2A?displayProperty=nameWithType>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to-5-0/csharp/HttpClientExtensionMethods.cs" highlight="26,33":::

<span data-ttu-id="1d1a9-225">[HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions)에는 System.Text.Json의 확장 메서드도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-225">There are also extension methods for System.Text.Json on [HttpContent](xref:System.Net.Http.Json.HttpContentJsonExtensions).</span></span>
::: zone-end

::: zone pivot="dotnet-core-3-1"
<span data-ttu-id="1d1a9-226">`HttpClient` 및 `HttpContent`의 확장 메서드는 .NET Core 3.1의 System.Text.Json에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1d1a9-226">Extension methods on `HttpClient` and `HttpContent` are not available in System.Text.Json in .NET Core 3.1.</span></span>
::: zone-end

## <a name="see-also"></a><span data-ttu-id="1d1a9-227">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1d1a9-227">See also</span></span>

* [<span data-ttu-id="1d1a9-228">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="1d1a9-228">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="1d1a9-229">JsonSerializerOptions 인스턴스 인스턴스화</span><span class="sxs-lookup"><span data-stu-id="1d1a9-229">Instantiate JsonSerializerOptions instances</span></span>](system-text-json-configure-options.md)
* [<span data-ttu-id="1d1a9-230">대/소문자를 구분하지 않는 일치를 사용하도록 설정</span><span class="sxs-lookup"><span data-stu-id="1d1a9-230">Enable case-insensitive matching</span></span>](system-text-json-character-casing.md)
* [<span data-ttu-id="1d1a9-231">속성 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1d1a9-231">Customize property names and values</span></span>](system-text-json-customize-properties.md)
* [<span data-ttu-id="1d1a9-232">속성 무시</span><span class="sxs-lookup"><span data-stu-id="1d1a9-232">Ignore properties</span></span>](system-text-json-ignore-properties.md)
* [<span data-ttu-id="1d1a9-233">잘못된 JSON 허용</span><span class="sxs-lookup"><span data-stu-id="1d1a9-233">Allow invalid JSON</span></span>](system-text-json-invalid-json.md)
* [<span data-ttu-id="1d1a9-234">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="1d1a9-234">Handle overflow JSON</span></span>](system-text-json-handle-overflow.md)
* [<span data-ttu-id="1d1a9-235">참조 유지</span><span class="sxs-lookup"><span data-stu-id="1d1a9-235">Preserve references</span></span>](system-text-json-preserve-references.md)
* [<span data-ttu-id="1d1a9-236">변경할 수 없는 형식 및 public이 아닌 접근자</span><span class="sxs-lookup"><span data-stu-id="1d1a9-236">Immutable types and non-public accessors</span></span>](system-text-json-immutability.md)
* [<span data-ttu-id="1d1a9-237">다형 직렬화</span><span class="sxs-lookup"><span data-stu-id="1d1a9-237">Polymorphic serialization</span></span>](system-text-json-polymorphism.md)
* [<span data-ttu-id="1d1a9-238">Newtonsoft.Json에서 System.Text.Json으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="1d1a9-238">Migrate from Newtonsoft.Json to System.Text.Json</span></span>](system-text-json-migrate-from-newtonsoft-how-to.md)
* [<span data-ttu-id="1d1a9-239">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="1d1a9-239">Customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="1d1a9-240">사용자 지정 직렬 변환기 및 역직렬 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="1d1a9-240">Write custom serializers and deserializers</span></span>](write-custom-serializer-deserializer.md)
* [<span data-ttu-id="1d1a9-241">JSON serialization용 사용자 지정 변환기 작성</span><span class="sxs-lookup"><span data-stu-id="1d1a9-241">Write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="1d1a9-242">DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="1d1a9-242">DateTime and DateTimeOffset support</span></span>](../datetime/system-text-json-support.md)
* <span data-ttu-id="1d1a9-243">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="1d1a9-243">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
* <span data-ttu-id="1d1a9-244">[System.Text.Json.Serialization API 참조](xref:System.Text.Json.Serialization)</span><span class="sxs-lookup"><span data-stu-id="1d1a9-244">[System.Text.Json.Serialization API reference](xref:System.Text.Json.Serialization)</span></span>
