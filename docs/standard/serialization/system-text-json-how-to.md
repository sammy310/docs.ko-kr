---
title: -.Net을 사용 하 여 C# JSON을 serialize 및 deserialize 하는 방법
ms.date: 01/10/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: fdca8d957bb2453e90652af1dfe5ef99b33b1b2c
ms.sourcegitcommit: 5d769956a04b6d68484dd717077fabc191c21da5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/17/2020
ms.locfileid: "76163204"
---
# <a name="how-to-serialize-and-deserialize-marshal-and-unmarshal-json-in-net"></a><span data-ttu-id="cf71a-102">.NET에서 JSON을 serialize 및 deserialize (marshal 및 트랜잭션의 역마샬링 위해) 하는 방법</span><span class="sxs-lookup"><span data-stu-id="cf71a-102">How to serialize and deserialize (marshal and unmarshal) JSON in .NET</span></span>

<span data-ttu-id="cf71a-103">이 문서에서는 <xref:System.Text.Json> 네임 스페이스를 사용 하 여 JavaScript Object Notation (JSON)로 serialize 및 deserialize 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-103">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span>

<span data-ttu-id="cf71a-104">지침 및 샘플 코드는 [ASP.NET Core](/aspnet/core/)와 같은 프레임 워크가 아닌 라이브러리를 직접 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-104">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

<span data-ttu-id="cf71a-105">대부분의 serialization 샘플 코드는 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>를 `true` 하 여 JSON (사람이 가독성을 위해 들여쓰기 및 공백 포함)을 "잘 인쇄" 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-105">Most of the serialization sample code sets <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true` to "pretty-print" the JSON (with indentation and whitespace for human readability).</span></span> <span data-ttu-id="cf71a-106">프로덕션 사용을 위해 일반적으로이 설정에 `false`의 기본값을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-106">For production use, you would typically accept the default value of `false` for this setting.</span></span>

## <a name="namespaces"></a><span data-ttu-id="cf71a-107">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="cf71a-107">Namespaces</span></span>

<span data-ttu-id="cf71a-108"><xref:System.Text.Json> 네임 스페이스에는 모든 진입점과 기본 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-108">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="cf71a-109"><xref:System.Text.Json.Serialization> 네임 스페이스에는 serialization 및 deserialization과 관련 된 고급 시나리오 및 사용자 지정을 위한 특성 및 Api가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-109">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="cf71a-110">이 문서에 표시 된 코드 예제에는 다음 네임 스페이스 중 하나 또는 둘 다에 대 한 `using` 지시문이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-110">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="cf71a-111"><xref:System.Runtime.Serialization> 네임 스페이스의 특성은 현재 `System.Text.Json`에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-111">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="cf71a-112">JSON에 .NET 개체를 작성 하는 방법 (직렬화)</span><span class="sxs-lookup"><span data-stu-id="cf71a-112">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="cf71a-113">JSON을 문자열 또는 파일에 쓰려면 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-113">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="cf71a-114">다음 예제에서는 JSON을 문자열로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-114">The following example creates JSON as a string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-115">다음 예제에서는 동기 코드를 사용 하 여 JSON 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-115">The following example uses synchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-116">다음 예제에서는 비동기 코드를 사용 하 여 JSON 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-116">The following example uses asynchronous code to create a JSON file:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-117">앞의 예제에서는 serialize 되는 형식에 대 한 형식 유추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-117">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="cf71a-118">`Serialize()` 오버 로드는 제네릭 형식 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-118">An overload of `Serialize()` takes a generic type parameter:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializeWithGenericParameter)]

### <a name="serialization-example"></a><span data-ttu-id="cf71a-119">Serialization 예제</span><span class="sxs-lookup"><span data-stu-id="cf71a-119">Serialization example</span></span>

<span data-ttu-id="cf71a-120">컬렉션 및 중첩 된 클래스를 포함 하는 클래스의 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-120">Here's an example class that contains collections and a nested class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPOCOs)]

<span data-ttu-id="cf71a-121">이전 형식의 인스턴스를 serialize 하는 JSON 출력은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-121">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="cf71a-122">JSON 출력은 기본적으로 축소 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-122">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureCelsius":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":20,"Low":-10},"Hot":{"High":60,"Low":20}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="cf71a-123">다음 예제에서는 동일한 JSON (공백 및 들여쓰기를 사용 하 여 잘 인쇄 됨)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-123">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

### <a name="serialize-to-utf-8"></a><span data-ttu-id="cf71a-124">U t f-8로 직렬화</span><span class="sxs-lookup"><span data-stu-id="cf71a-124">Serialize to UTF-8</span></span>

<span data-ttu-id="cf71a-125">U t f-8로 serialize 하려면 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-125">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-126"><xref:System.Text.Json.Utf8JsonWriter>를 사용 하는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버 로드도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-126">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="cf71a-127">U t f-8로 serialize 하는 것은 문자열 기반 메서드를 사용 하는 것 보다 약 5-10% 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-127">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="cf71a-128">차이점은 바이트 (u t f-8)를 문자열 (UTF-16)로 변환할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-128">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="cf71a-129">Serialization 동작</span><span class="sxs-lookup"><span data-stu-id="cf71a-129">Serialization behavior</span></span>

* <span data-ttu-id="cf71a-130">기본적으로 모든 public 속성이 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-130">By default, all public properties are serialized.</span></span> <span data-ttu-id="cf71a-131">[제외할 속성을 지정할](#exclude-properties-from-serialization)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-131">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="cf71a-132">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) 는 ascii가 아닌 문자, ascii 범위 내의 HTML 구분 문자 및 [RFC 8259 JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프 되어야 하는 문자를 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-132">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the RFC 8259 JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="cf71a-133">기본적으로 JSON은 축소 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-133">By default, JSON is minified.</span></span> <span data-ttu-id="cf71a-134">[JSON을 잘 인쇄할](#serialize-to-formatted-json)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-134">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="cf71a-135">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-135">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="cf71a-136">[JSON 이름 대/소문자를 사용자 지정할](#customize-json-names-and-values)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-136">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="cf71a-137">순환 참조가 감지 되 고 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-137">Circular references are detected and exceptions thrown.</span></span>
* <span data-ttu-id="cf71a-138">현재는 필드가 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-138">Currently, fields are excluded.</span></span>

<span data-ttu-id="cf71a-139">지원 되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-139">Supported types include:</span></span>

* <span data-ttu-id="cf71a-140">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-140">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="cf71a-141">사용자 정의 [일반 이전 CLR 개체 (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="cf71a-141">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="cf71a-142">1 차원 및 가변 배열 (`ArrayName[][]`)</span><span class="sxs-lookup"><span data-stu-id="cf71a-142">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="cf71a-143">`TValue` `object`, `JsonElement`또는 POCO 인 `Dictionary<string,TValue>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-143">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="cf71a-144">다음 네임 스페이스의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-144">Collections from the following namespaces.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="cf71a-145">추가 형식을 처리 하거나 기본 변환기에서 지원 하지 않는 기능을 제공 하는 [사용자 지정 변환기를 구현할](system-text-json-converters-how-to.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-145">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="cf71a-146">JSON을 .NET 개체로 읽는 방법 (deserialize)</span><span class="sxs-lookup"><span data-stu-id="cf71a-146">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="cf71a-147">문자열이 나 파일에서 deserialize 하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-147">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="cf71a-148">다음 예제에서는 문자열에서 JSON을 읽고 [serialization 예제](#serialization-example)에 대해 앞에서 설명한 `WeatherForecast` 클래스의 인스턴스를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-148">The following example reads JSON from a string and creates an instance of the `WeatherForecast` class shown earlier for the [serialization example](#serialization-example):</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetDeserialize)]

<span data-ttu-id="cf71a-149">동기 코드를 사용 하 여 파일에서 deserialize 하려면 다음 예제와 같이 파일을 문자열로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-149">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFile.cs?name=SnippetDeserialize)]

<span data-ttu-id="cf71a-150">비동기 코드를 사용 하 여 파일에서 deserialize 하려면 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-150">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToFileAsync.cs?name=SnippetDeserialize)]

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="cf71a-151">U t f-8에서 Deserialize</span><span class="sxs-lookup"><span data-stu-id="cf71a-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="cf71a-152">U t f-8에서 deserialize 하려면 다음 예제와 같이 `Utf8JsonReader` 또는 `ReadOnlySpan<byte>`를 사용 하는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 오버 로드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="cf71a-153">이 예에서는 JSON이 jsonUtf8Bytes 이라는 바이트 배열에 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-153">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize1)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToUtf8.cs?name=SnippetDeserialize2)]

## <a name="deserialization-behavior"></a><span data-ttu-id="cf71a-154">Deserialization 동작</span><span class="sxs-lookup"><span data-stu-id="cf71a-154">Deserialization behavior</span></span>

* <span data-ttu-id="cf71a-155">기본적으로 속성 이름 일치는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-155">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="cf71a-156">[대/소문자](#case-insensitive-property-matching)를 구분 하지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-156">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="cf71a-157">JSON에 읽기 전용 속성에 대 한 값이 포함 된 경우에는이 값이 무시 되 고 예외가 throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-157">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="cf71a-158">매개 변수가 없는 생성자가 없는 참조 형식으로의 Deserialization은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-158">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="cf71a-159">변경할 수 없는 개체 또는 읽기 전용 속성에 대 한 Deserialization은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-159">Deserialization to immutable objects or read-only properties isn't supported.</span></span>
* <span data-ttu-id="cf71a-160">기본적으로 열거형은 숫자로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-160">By default, enums are supported as numbers.</span></span> <span data-ttu-id="cf71a-161">[열거형 이름을 문자열로 serialize](#enums-as-strings)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-161">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="cf71a-162">필드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-162">Fields aren't supported.</span></span>
* <span data-ttu-id="cf71a-163">기본적으로 JSON의 주석이 나 후행 쉼표는 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-163">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="cf71a-164">[주석과 후행 쉼표를 허용할](#allow-comments-and-trailing-commas)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-164">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="cf71a-165">[기본 최대 깊이](xref:System.Text.Json.JsonReaderOptions.MaxDepth) 는 64입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-165">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="cf71a-166">기본 변환기에서 지원 하지 않는 기능을 제공 하기 위해 [사용자 지정 변환기를 구현할](system-text-json-converters-how-to.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-166">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="cf71a-167">형식이 지정 된 JSON으로 직렬화</span><span class="sxs-lookup"><span data-stu-id="cf71a-167">Serialize to formatted JSON</span></span>

<span data-ttu-id="cf71a-168">JSON 출력을 잘 인쇄 하려면 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>를 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-168">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripToString.cs?name=SnippetSerializePrettyPrint)]

<span data-ttu-id="cf71a-169">다음은 serialize 되 고 잘 인쇄 되는 JSON 출력의 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-169">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="cf71a-170">JSON 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="cf71a-170">Customize JSON names and values</span></span>

<span data-ttu-id="cf71a-171">기본적으로 속성 이름 및 사전 키는 대/소문자를 포함 하 여 JSON 출력에서 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-171">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="cf71a-172">열거형 값은 숫자로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-172">Enum values are represented as numbers.</span></span> <span data-ttu-id="cf71a-173">이 섹션에서는 다음을 수행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-173">This section explains how to:</span></span>

* [<span data-ttu-id="cf71a-174">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="cf71a-174">Customize individual property names</span></span>](#customize-individual-property-names)
* [<span data-ttu-id="cf71a-175">모든 속성 이름을 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="cf71a-175">Convert all property names to camel case</span></span>](#use-camel-case-for-all-json-property-names)
* [<span data-ttu-id="cf71a-176">사용자 지정 속성 명명 정책 구현</span><span class="sxs-lookup"><span data-stu-id="cf71a-176">Implement a custom property naming policy</span></span>](#use-a-custom-json-property-naming-policy)
* [<span data-ttu-id="cf71a-177">사전 키를 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="cf71a-177">Convert dictionary keys to camel case</span></span>](#camel-case-dictionary-keys)
* [<span data-ttu-id="cf71a-178">문자열 및 카멜식 대/소문자로 열거형 변환</span><span class="sxs-lookup"><span data-stu-id="cf71a-178">Convert enums to strings and camel case</span></span>](#enums-as-strings) 

<span data-ttu-id="cf71a-179">JSON 속성 이름 및 값을 특수 하 게 처리 해야 하는 다른 시나리오의 경우 [사용자 지정 변환기를 구현할](system-text-json-converters-how-to.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-179">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="cf71a-180">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="cf71a-180">Customize individual property names</span></span>

<span data-ttu-id="cf71a-181">개별 속성의 이름을 설정 하려면 [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-181">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="cf71a-182">직렬화 및 결과 JSON의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-182">Here's an example type to serialize and resulting JSON:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="cf71a-183">이 특성에 의해 설정 된 속성 이름:</span><span class="sxs-lookup"><span data-stu-id="cf71a-183">The property name set by this attribute:</span></span>

* <span data-ttu-id="cf71a-184">Serialization 및 deserialization을 위해 양방향으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-184">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="cf71a-185">속성 명명 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-185">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="cf71a-186">모든 JSON 속성 이름에 카멜식 대/소문자 사용</span><span class="sxs-lookup"><span data-stu-id="cf71a-186">Use camel case for all JSON property names</span></span>

<span data-ttu-id="cf71a-187">모든 JSON 속성 이름에 카멜식 대/소문자를 사용 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>를 `JsonNamingPolicy.CamelCase`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-187">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundTripCamelCasePropertyNames.cs?name=Serialize)]

<span data-ttu-id="cf71a-188">직렬화 및 JSON 출력에 대 한 예제 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-188">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="cf71a-189">카멜식 대/소문자 속성 명명 정책:</span><span class="sxs-lookup"><span data-stu-id="cf71a-189">The camel case property naming policy:</span></span>

* <span data-ttu-id="cf71a-190">Serialization 및 deserialization에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-190">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="cf71a-191">`[JsonPropertyName]` 특성에 의해 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-191">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="cf71a-192">이 때문에이 예제에서 JSON 속성 이름 `Wind`는 카멜식 대/소문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-192">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="cf71a-193">사용자 지정 JSON 속성 명명 정책 사용</span><span class="sxs-lookup"><span data-stu-id="cf71a-193">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="cf71a-194">사용자 지정 JSON 속성 명명 정책을 사용 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonNamingPolicy>에서 파생 되는 클래스를 만들고 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-194">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/UpperCaseNamingPolicy.cs)]

<span data-ttu-id="cf71a-195">그런 다음 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 속성을 명명 정책 클래스의 인스턴스로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-195">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripPropertyNamingPolicy.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-196">직렬화 및 JSON 출력에 대 한 예제 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-196">Here's an example class to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPropertyNameAttribute)]

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATURECELSIUS": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="cf71a-197">JSON 속성 명명 정책:</span><span class="sxs-lookup"><span data-stu-id="cf71a-197">The JSON property naming policy:</span></span>

* <span data-ttu-id="cf71a-198">Serialization 및 deserialization에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-198">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="cf71a-199">`[JsonPropertyName]` 특성에 의해 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-199">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="cf71a-200">이 때문에이 예제의 JSON 속성 이름 `Wind` 대문자는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-200">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="cf71a-201">카멜식 대/소문자 사전 키</span><span class="sxs-lookup"><span data-stu-id="cf71a-201">Camel case dictionary keys</span></span>

<span data-ttu-id="cf71a-202">Serialize 할 개체의 속성이 `Dictionary<string,TValue>`형식이 면 `string` 키를 카멜식 대/소문자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-202">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="cf71a-203">이렇게 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy>를 `JsonNamingPolicy.CamelCase`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-203">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCamelCaseDictionaryKeys.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-204">키-값 쌍 `"HotMinTemp", 40` `"ColdMinTemp", 20` 키-값 쌍이 있는 `TemperatureRanges` 라는 사전이 포함 된 개체를 serialize 하면 다음 예제와 같이 JSON 출력이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-204">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

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

<span data-ttu-id="cf71a-205">사전 키에 대 한 카멜식 대/소문자 명명 정책은 serialization에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-205">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="cf71a-206">사전을 deserialize 하면 `DictionaryKeyPolicy`에 대 한 `JsonNamingPolicy.CamelCase` 지정 하더라도 키가 JSON 파일과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-206">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="cf71a-207">문자열로 된 열거형</span><span class="sxs-lookup"><span data-stu-id="cf71a-207">Enums as strings</span></span>

<span data-ttu-id="cf71a-208">기본적으로 열거형은 숫자로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-208">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="cf71a-209">열거형 이름을 문자열로 serialize 하려면 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-209">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="cf71a-210">예를 들어, 열거형을 포함 하는 다음 클래스를 serialize 해야 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-210">For example, suppose you need to serialize the following class that has an enum:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithEnum)]

<span data-ttu-id="cf71a-211">요약이 `Hot`되는 경우 기본적으로 직렬화 된 JSON에는 숫자 값 3이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-211">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": 3
}
```

<span data-ttu-id="cf71a-212">다음 샘플 코드는 숫자 값 대신 열거형 이름을 직렬화 하 고 이름을 카멜식 case로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-212">The following sample code serializes the enum names instead of the numeric values, and converts the names to camel case:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-213">결과 JSON은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-213">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="cf71a-214">다음 예제와 같이 열거형 문자열 이름도 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-214">Enum string names can be deserialized as well, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/RoundtripEnumAsString.cs?name=SnippetDeserialize)]

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="cf71a-215">Serialization에서 속성 제외</span><span class="sxs-lookup"><span data-stu-id="cf71a-215">Exclude properties from serialization</span></span>

<span data-ttu-id="cf71a-216">기본적으로 모든 public 속성이 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-216">By default, all public properties are serialized.</span></span> <span data-ttu-id="cf71a-217">JSON 출력에 표시 하지 않으려는 경우 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-217">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="cf71a-218">이 섹션에서는 다음을 제외 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-218">This section explains how to exclude:</span></span>

* [<span data-ttu-id="cf71a-219">개별 속성</span><span class="sxs-lookup"><span data-stu-id="cf71a-219">Individual properties</span></span>](#exclude-individual-properties)
* [<span data-ttu-id="cf71a-220">모든 읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="cf71a-220">All read-only properties</span></span>](#exclude-all-read-only-properties)
* [<span data-ttu-id="cf71a-221">모든 null 값 속성</span><span class="sxs-lookup"><span data-stu-id="cf71a-221">All null-value properties</span></span>](#exclude-all-null-value-properties)

### <a name="exclude-individual-properties"></a><span data-ttu-id="cf71a-222">개별 속성 제외</span><span class="sxs-lookup"><span data-stu-id="cf71a-222">Exclude individual properties</span></span>

<span data-ttu-id="cf71a-223">개별 속성을 무시 하려면 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-223">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="cf71a-224">다음은 serialize 및 JSON 출력에 대 한 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-224">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithIgnoreAttribute)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="cf71a-225">모든 읽기 전용 속성을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-225">Exclude all read-only properties</span></span>

<span data-ttu-id="cf71a-226">공용 setter가 아닌 공용 getter가 포함 된 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-226">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="cf71a-227">모든 읽기 전용 속성을 제외 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>를 `true`으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-227">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeReadOnlyProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-228">다음은 serialize 및 JSON 출력에 대 한 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-228">Here's an example type to serialize and JSON output:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithROProperty)]

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="cf71a-229">이 옵션은 serialization에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-229">This option applies only to serialization.</span></span> <span data-ttu-id="cf71a-230">Deserialization을 수행 하는 동안 읽기 전용 속성은 기본적으로 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-230">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="cf71a-231">모든 null 값 속성 제외</span><span class="sxs-lookup"><span data-stu-id="cf71a-231">Exclude all null value properties</span></span>

<span data-ttu-id="cf71a-232">모든 null 값 속성을 제외 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-232">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeExcludeNullValueProperties.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-233">직렬화 및 JSON 출력에 대 한 예제 개체는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-233">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="cf71a-234">속성</span><span class="sxs-lookup"><span data-stu-id="cf71a-234">Property</span></span> |<span data-ttu-id="cf71a-235">값</span><span class="sxs-lookup"><span data-stu-id="cf71a-235">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="cf71a-236">날짜</span><span class="sxs-lookup"><span data-stu-id="cf71a-236">Date</span></span>    | <span data-ttu-id="cf71a-237">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="cf71a-237">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="cf71a-238">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="cf71a-238">TemperatureCelsius</span></span>| <span data-ttu-id="cf71a-239">25</span><span class="sxs-lookup"><span data-stu-id="cf71a-239">25</span></span> |
| <span data-ttu-id="cf71a-240">요약</span><span class="sxs-lookup"><span data-stu-id="cf71a-240">Summary</span></span>| <span data-ttu-id="cf71a-241">null</span><span class="sxs-lookup"><span data-stu-id="cf71a-241">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25
}
```

<span data-ttu-id="cf71a-242">이 설정은 serialization 및 deserialization에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-242">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="cf71a-243">Deserialization에 미치는 영향에 대 한 자세한 내용은 [deserialize 할 때 Null 무시](#ignore-null-when-deserializing)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf71a-243">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="cf71a-244">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="cf71a-244">Customize character encoding</span></span>

<span data-ttu-id="cf71a-245">기본적으로 serializer는 ASCII가 아닌 문자를 모두 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-245">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="cf71a-246">즉, `xxxx`가 문자의 유니코드 코드 인 `\uxxxx`로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-246">That is, it replaces them with `\uxxxx` where `xxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="cf71a-247">예를 들어 `Summary` 속성이 키릴 자모 жарко로 설정 된 경우이 예제와 같이 `WeatherForecast` 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-247">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="cf71a-248">언어 문자 집합 Serialize</span><span class="sxs-lookup"><span data-stu-id="cf71a-248">Serialize language character sets</span></span>

<span data-ttu-id="cf71a-249">이스케이프 하지 않고 하나 이상의 언어의 문자 집합을 serialize 하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>의 인스턴스를 만들 때 [유니코드 범위](xref:System.Text.Unicode.UnicodeRanges) 를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-249">To serialize the character set(s) of one or more languages without escaping, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetLanguageSets)]

<span data-ttu-id="cf71a-250">이 코드는 키릴 자모 또는 그리스어 문자를 이스케이프 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-250">This code doesn't escape Cyrillic or Greek characters.</span></span> <span data-ttu-id="cf71a-251">`Summary` 속성이 키릴 자모 жарко로 설정 된 경우 `WeatherForecast` 개체는 다음 예제와 같이 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-251">If the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жарко"
}
```

<span data-ttu-id="cf71a-252">이스케이프 하지 않고 모든 언어 집합을 serialize 하려면 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-252">To serialize all language sets without escaping, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="cf71a-253">특정 문자 Serialize</span><span class="sxs-lookup"><span data-stu-id="cf71a-253">Serialize specific characters</span></span>

<span data-ttu-id="cf71a-254">대안은 이스케이프 되지 않고에서 허용 하려는 개별 문자를 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-254">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="cf71a-255">다음 예제에서는 жарко의 처음 두 자만 직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-255">The following example serializes only the first two characters of жарко:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetSelectedCharacters)]

<span data-ttu-id="cf71a-256">앞의 코드에서 생성 된 JSON의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-256">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="cf71a-257">모든 문자를 직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-257">Serialize all characters</span></span>

<span data-ttu-id="cf71a-258">이스케이프를 최소화 하기 위해 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-258">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUsings)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializeCustomEncoding.cs?name=SnippetUnsafeRelaxed)]

> [!CAUTION]
> <span data-ttu-id="cf71a-259">기본 인코더와 비교할 때 `UnsafeRelaxedJsonEscaping` 인코더는 문자를 이스케이프 되지 않은 통과할 수 있도록 허용 하는 것 보다 더 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-259">Compared to the default encoder, the `UnsafeRelaxedJsonEscaping` encoder is more permissive about allowing characters to pass through unescaped:</span></span>
>
> * <span data-ttu-id="cf71a-260">`<`, `>`, `&`및 `'`과 같은 HTML 구분 문자를 이스케이프 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-260">It doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="cf71a-261">클라이언트와 서버에서 *문자 집합*에 동의 하지 않을 수 있는 것과 같은 XSS 또는 정보 공개 공격에 대해 심층 방어를 추가로 보호 하는 기능은 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-261">It doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
>
> <span data-ttu-id="cf71a-262">클라이언트에서 결과 페이로드를 u t f-8로 인코딩된 JSON으로 해석 하는 것으로 알려진 경우에만 안전 하지 않은 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-262">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="cf71a-263">예를 들어 서버에서 응답 헤더 `Content-Type: application/json; charset=utf-8`보내는 경우이를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-263">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="cf71a-264">원시 `UnsafeRelaxedJsonEscaping` 출력을 HTML 페이지나 `<script>` 요소로 내보낼 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-264">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="cf71a-265">파생 클래스의 속성 직렬화</span><span class="sxs-lookup"><span data-stu-id="cf71a-265">Serialize properties of derived classes</span></span>

<span data-ttu-id="cf71a-266">다형 형식 계층의 Serialization은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-266">Serialization of a polymorphic type hierarchy is not supported.</span></span> <span data-ttu-id="cf71a-267">예를 들어 속성이 인터페이스나 추상 클래스로 정의 된 경우에는 런타임 형식에 추가 속성이 있더라도 인터페이스 또는 추상 클래스에 정의 된 속성만 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-267">For example, if a property is defined as an interface or an abstract class, only the properties defined on the interface or abstract class are serialized, even if the runtime type has additional properties.</span></span> <span data-ttu-id="cf71a-268">이 동작에 대 한 예외는이 섹션에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-268">The exceptions to this behavior are explained in this section.</span></span>

<span data-ttu-id="cf71a-269">예를 들어 `WeatherForecast` 클래스와 파생 클래스 `WeatherForecastDerived`있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-269">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastDerived`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFDerived)]

<span data-ttu-id="cf71a-270">컴파일 시간에 `Serialize` 메서드의 형식 인수를 `WeatherForecast`한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-270">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeDefault)]

<span data-ttu-id="cf71a-271">이 시나리오에서는 `weatherForecast` 개체가 실제로 `WeatherForecastDerived` 개체인 경우에도 `WindSpeed` 속성이 serialize 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-271">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastDerived` object.</span></span> <span data-ttu-id="cf71a-272">기본 클래스 속성만 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-272">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="cf71a-273">이 동작은 파생 된 런타임 생성 형식에서 실수로 데이터가 노출 되는 것을 방지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-273">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="cf71a-274">이전 예제에서 파생 형식의 속성을 serialize 하려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-274">To serialize the properties of the derived type in the preceding example, use one of the following approaches:</span></span>

* <span data-ttu-id="cf71a-275">런타임에 형식을 지정할 수 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버 로드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-275">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeGetType)]

* <span data-ttu-id="cf71a-276">`object`로 serialize 될 개체를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-276">Declare the object to be serialized as `object`.</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeObject)]

<span data-ttu-id="cf71a-277">위의 예제 시나리오에서 두 가지 방법으로 인해 `WindSpeed` 속성이 JSON 출력에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-277">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "WindSpeed": 35,
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": "Hot"
}
```

> [!IMPORTANT]
> <span data-ttu-id="cf71a-278">이러한 접근 방식은 루트 개체의 속성이 아니라 serialize 될 루트 개체에 대해서만 다형성 serialization을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-278">These approaches provide polymorphic serialization only for the root object to be serialized, not for properties of that root object.</span></span> 

<span data-ttu-id="cf71a-279">`object`형식으로 정의 하는 경우 하위 수준 개체에 대해 다형성 serialization을 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-279">You can get polymorphic serialization for lower-level objects if you define them as type `object`.</span></span> <span data-ttu-id="cf71a-280">예를 들어 `WeatherForecast` 클래스에 `WeatherForecast` 또는 `object`형식으로 정의할 수 있는 `PreviousForecast` 라는 속성이 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-280">For example, suppose your `WeatherForecast` class has a property named `PreviousForecast` that can be defined as type `WeatherForecast` or `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPrevious)]

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithPreviousAsObject)]

<span data-ttu-id="cf71a-281">`PreviousForecast` 속성이 `WeatherForecastDerived`의 인스턴스를 포함 하는 경우:</span><span class="sxs-lookup"><span data-stu-id="cf71a-281">If the `PreviousForecast` property contains an instance of `WeatherForecastDerived`:</span></span>

* <span data-ttu-id="cf71a-282">`WeatherForecastWithPrevious` 직렬화의 JSON 출력에는 `WindSpeed`**포함 되지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="cf71a-282">The JSON output from serializing `WeatherForecastWithPrevious` **doesn't include** `WindSpeed`.</span></span>
* <span data-ttu-id="cf71a-283">`WeatherForecastWithPreviousAsObject` serialize의 JSON 출력에 `WindSpeed`**포함 됩니다** .</span><span class="sxs-lookup"><span data-stu-id="cf71a-283">The JSON output from serializing `WeatherForecastWithPreviousAsObject` **includes** `WindSpeed`.</span></span>

<span data-ttu-id="cf71a-284">`WeatherForecastWithPreviousAsObject`serialize 하기 위해 루트 개체가 파생 형식일 수 있는 것이 아니기 때문에 `Serialize<object>` 또는 `GetType`를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-284">To serialize `WeatherForecastWithPreviousAsObject`, it isn't necessary to call `Serialize<object>` or `GetType` because the root object isn't the one that may be of a derived type.</span></span> <span data-ttu-id="cf71a-285">다음 코드 예제에서는 `Serialize<object>` 또는 `GetType`를 호출 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-285">The following code example doesn't call `Serialize<object>` or `GetType`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeSecondLevel)]

<span data-ttu-id="cf71a-286">위의 코드는 `WeatherForecastWithPreviousAsObject`를 올바르게 serialize 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-286">The preceding code correctly serializes `WeatherForecastWithPreviousAsObject`:</span></span>

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

<span data-ttu-id="cf71a-287">`object`로 속성을 정의 하는 것과 동일한 방법이 인터페이스와 함께 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-287">The same approach of defining properties as `object` works with interfaces.</span></span> <span data-ttu-id="cf71a-288">다음 인터페이스 및 구현이 있고 구현 인스턴스가 포함 된 속성을 사용 하 여 클래스를 serialize 하려는 경우를 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-288">Suppose you have the following interface and implementation, and you want to serialize a class with properties that contain implementation instances:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/IForecast.cs)]

<span data-ttu-id="cf71a-289">`Forecasts`의 인스턴스를 serialize 하는 경우 `Tuesday`가 `object`로 정의 되어 있으므로 `Tuesday`만 `WindSpeed` 속성을 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-289">When you serialize an instance of `Forecasts`, only `Tuesday` shows the `WindSpeed` property, because `Tuesday` is defined as `object`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/SerializePolymorphic.cs?name=SnippetSerializeInterface)]

<span data-ttu-id="cf71a-290">다음 예제에서는 앞의 코드에서 생성 되는 JSON을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-290">The following example shows the JSON that results from the preceding code:</span></span>

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

<span data-ttu-id="cf71a-291">다형 **직렬화**에 대 한 자세한 내용과 **deserialization**에 대 한 자세한 내용은 [Newtonsoft.Json에서 System.Text.Json로 마이그레이션하는 방법 ](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cf71a-291">For more information about polymorphic **serialization**, and for information about **deserialization**, see [How to migrate from Newtonsoft.Json to System.Text.Json](system-text-json-migrate-from-newtonsoft-how-to.md#polymorphic-serialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="cf71a-292">주석과 후행 쉼표 허용</span><span class="sxs-lookup"><span data-stu-id="cf71a-292">Allow comments and trailing commas</span></span>

<span data-ttu-id="cf71a-293">기본적으로 주석 및 후행 쉼표는 JSON에서 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-293">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="cf71a-294">JSON에서 주석을 허용 하려면 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 속성을 `JsonCommentHandling.Skip`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-294">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span>
<span data-ttu-id="cf71a-295">그리고 후행 쉼표를 허용 하려면 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-295">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="cf71a-296">다음 예제에서는 두 가지를 모두 허용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-296">The following example shows how to allow both:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCommasComments.cs?name=SnippetDeserialize)]

<span data-ttu-id="cf71a-297">다음은 주석과 후행 쉼표를 사용 하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-297">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="cf71a-298">대/소문자를 구분 하지 않는 속성 일치</span><span class="sxs-lookup"><span data-stu-id="cf71a-298">Case-insensitive property matching</span></span>

<span data-ttu-id="cf71a-299">기본적으로 deserialization은 JSON과 대상 개체 속성 간에 일치 하는 대/소문자를 구분 하는 속성 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-299">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="cf71a-300">이 동작을 변경 하려면 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType>를 `true`으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-300">To change that behavior, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeCaseInsensitive.cs?name=SnippetDeserialize)]

<span data-ttu-id="cf71a-301">카멜식 대/소문자 속성 이름을 사용 하는 JSON 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-301">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="cf71a-302">파스칼식 대/소문자 속성 이름을 포함 하는 다음 형식으로 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-302">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
}
```

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

## <a name="handle-overflow-json"></a><span data-ttu-id="cf71a-303">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="cf71a-303">Handle overflow JSON</span></span>

<span data-ttu-id="cf71a-304">Deserialize 하는 동안 대상 형식의 속성으로 표시 되지 않는 데이터를 JSON에 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-304">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="cf71a-305">예를 들어 대상 형식이 다음과 같다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-305">For example, suppose your target type is this:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWF)]

<span data-ttu-id="cf71a-306">Deserialize 할 JSON은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-306">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="cf71a-307">표시 된 형식에 표시 된 JSON을 deserialize 하는 경우 `DatesAvailable` 및 `SummaryWords` 속성은 이동 하지 않으며 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-307">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="cf71a-308">이러한 속성과 같은 추가 데이터를 캡처하려면 `Dictionary<string,object>` 또는 `Dictionary<string,JsonElement>`형식의 속성에 [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) 특성을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-308">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithExtensionData)]

<span data-ttu-id="cf71a-309">앞에서 설명한 JSON을이 샘플 형식으로 deserialize 하는 경우 추가 데이터는 `ExtensionData` 속성의 키-값 쌍이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-309">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="cf71a-310">속성</span><span class="sxs-lookup"><span data-stu-id="cf71a-310">Property</span></span> |<span data-ttu-id="cf71a-311">값</span><span class="sxs-lookup"><span data-stu-id="cf71a-311">Value</span></span>  |<span data-ttu-id="cf71a-312">참고</span><span class="sxs-lookup"><span data-stu-id="cf71a-312">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="cf71a-313">날짜</span><span class="sxs-lookup"><span data-stu-id="cf71a-313">Date</span></span>    | <span data-ttu-id="cf71a-314">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="cf71a-314">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="cf71a-315">TemperatureCelsius</span><span class="sxs-lookup"><span data-stu-id="cf71a-315">TemperatureCelsius</span></span>| <span data-ttu-id="cf71a-316">0</span><span class="sxs-lookup"><span data-stu-id="cf71a-316">0</span></span> | <span data-ttu-id="cf71a-317">대/소문자를 구분 하는 불일치 (JSON의`temperatureCelsius`) 이므로 속성은 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-317">Case-sensitive mismatch (`temperatureCelsius` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="cf71a-318">요약</span><span class="sxs-lookup"><span data-stu-id="cf71a-318">Summary</span></span> | <span data-ttu-id="cf71a-319">높음</span><span class="sxs-lookup"><span data-stu-id="cf71a-319">Hot</span></span> ||
| <span data-ttu-id="cf71a-320">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="cf71a-320">ExtensionData</span></span> | <span data-ttu-id="cf71a-321">temperatureCelsius: 25</span><span class="sxs-lookup"><span data-stu-id="cf71a-321">temperatureCelsius: 25</span></span> |<span data-ttu-id="cf71a-322">Case가 일치 하지 않기 때문에이 JSON 속성은 추가 이며 사전에서 키-값 쌍이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-322">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="cf71a-323">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="cf71a-323">DatesAvailable:</span></span><br>  <span data-ttu-id="cf71a-324">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="cf71a-324">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="cf71a-325">오전 8/2/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="cf71a-325">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="cf71a-326">JSON의 추가 속성은 키-값 쌍이 되며 배열은 값 개체로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-326">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="cf71a-327">요약 단어:</span><span class="sxs-lookup"><span data-stu-id="cf71a-327">SummaryWords:</span></span><br><span data-ttu-id="cf71a-328">표</span><span class="sxs-lookup"><span data-stu-id="cf71a-328">Cool</span></span><br><span data-ttu-id="cf71a-329">바람</span><span class="sxs-lookup"><span data-stu-id="cf71a-329">Windy</span></span><br><span data-ttu-id="cf71a-330">Humid</span><span class="sxs-lookup"><span data-stu-id="cf71a-330">Humid</span></span> |<span data-ttu-id="cf71a-331">JSON의 추가 속성은 키-값 쌍이 되며 배열은 값 개체로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-331">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="cf71a-332">대상 개체가 serialize 되 면 확장 데이터 키 값 쌍은 수신 JSON에 있는 것 처럼 JSON 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-332">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="cf71a-333">`ExtensionData` 속성 이름이 JSON에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-333">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="cf71a-334">이 동작을 통해 JSON은 deserialize 되지 않는 추가 데이터를 잃지 않고도 라운드트립을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-334">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="cf71a-335">Deserialize 할 때 null 무시</span><span class="sxs-lookup"><span data-stu-id="cf71a-335">Ignore null when deserializing</span></span>

<span data-ttu-id="cf71a-336">기본적으로 JSON의 속성이 null 이면 대상 개체의 해당 속성이 null로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-336">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="cf71a-337">일부 시나리오에서는 대상 속성에 기본값이 있을 수 있으며 null 값이 기본값을 재정의 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-337">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="cf71a-338">예를 들어 다음 코드는 대상 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-338">For example, suppose the following code represents your target object:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/WeatherForecast.cs?name=SnippetWFWithDefault)]

<span data-ttu-id="cf71a-339">다음 JSON을 deserialize 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-339">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureCelsius": 25,
  "Summary": null
}
```

<span data-ttu-id="cf71a-340">Deserialization 후 `WeatherForecastWithDefault` 개체의 `Summary` 속성은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-340">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="cf71a-341">이 동작을 변경 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>를 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-341">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/DeserializeIgnoreNull.cs?name=SnippetDeserialize)]

<span data-ttu-id="cf71a-342">이 옵션을 사용 하는 경우 `WeatherForecastWithDefault` 개체의 `Summary` 속성이 deserialization 후의 기본값 "요약 없음"입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-342">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="cf71a-343">JSON의 Null 값은 유효한 경우에만 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-343">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="cf71a-344">Null을 허용 하지 않는 값 형식에 대 한 Null 값은 예외를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-344">Null values for non-nullable value types cause exceptions.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="cf71a-345">Utf8JsonReader, Utf8JsonWriter 및 JsonDocument</span><span class="sxs-lookup"><span data-stu-id="cf71a-345">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="cf71a-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>는 u t f-8로 인코딩된 JSON 텍스트에 대 한 고성능, 낮은 할당, 전방 전용 판독기 이며 `ReadOnlySpan<byte>` 또는 `ReadOnlySequence<byte>`에서 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-346"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="cf71a-347">`Utf8JsonReader`는 사용자 지정 파서 및 deserializers를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-347">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="cf71a-348"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonReader`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-348">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="cf71a-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>는 `String`, `Int32`및 `DateTime`같은 일반적인 .NET 유형에 서 UTF-8 인코딩 JSON 텍스트를 작성 하는 고성능 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-349"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="cf71a-350">기록기는 사용자 지정 serializer를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-350">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="cf71a-351"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonWriter`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-351">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="cf71a-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName>는 `Utf8JsonReader`를 사용 하 여 읽기 전용 문서 개체 모델 (DOM)를 빌드하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-352"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="cf71a-353">DOM은 JSON 페이로드의 데이터에 대 한 임의 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-353">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="cf71a-354">페이로드를 구성 하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-354">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="cf71a-355">`JsonElement` 형식은 JSON 텍스트를 일반적인 .NET 형식으로 변환 하는 Api와 함께 배열 및 개체 열거자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-355">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="cf71a-356">`JsonDocument` <xref:System.Text.Json.JsonDocument.RootElement> 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-356">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="cf71a-357">다음 섹션에서는 JSON을 읽고 쓰기 위해 이러한 도구를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-357">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="cf71a-358">JsonDocument를 사용 하 여 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="cf71a-358">Use JsonDocument for access to data</span></span>

<span data-ttu-id="cf71a-359">다음 예제에서는 JSON 문자열에 있는 데이터에 대 한 임의 액세스를 위해 <xref:System.Text.Json.JsonDocument> 클래스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-359">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades1)]

<span data-ttu-id="cf71a-360">위의 코드:</span><span class="sxs-lookup"><span data-stu-id="cf71a-360">The preceding code:</span></span>

* <span data-ttu-id="cf71a-361">JSON을 분석 하는 것이 `jsonString`라는 문자열에 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-361">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="cf71a-362">`Grade` 속성이 있는 `Students` 배열의 개체에 대 한 평균 등급을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-362">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="cf71a-363">등급이 없는 학생의 기본 등급 (70)을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-363">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="cf71a-364">각 반복으로 `count` 변수를 증가 시켜 학생 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-364">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="cf71a-365">다른 방법은 다음 예제와 같이 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>를 호출 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-365">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  [!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentDataAccess.cs?name=SnippetAverageGrades2)]

<span data-ttu-id="cf71a-366">이 코드에서 처리 하는 JSON의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-366">Here's an example of the JSON that this code processes:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="cf71a-367">JsonDocument를 사용 하 여 JSON 쓰기</span><span class="sxs-lookup"><span data-stu-id="cf71a-367">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="cf71a-368">다음 예제에서는 <xref:System.Text.Json.JsonDocument>에서 JSON을 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-368">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/JsonDocumentWriteJson.cs?name=SnippetSerialize)]

<span data-ttu-id="cf71a-369">위의 코드:</span><span class="sxs-lookup"><span data-stu-id="cf71a-369">The preceding code:</span></span>

* <span data-ttu-id="cf71a-370">JSON 파일을 읽고, `JsonDocument`에 데이터를 로드 하 고, 서식 있는 (예쁜 인쇄) JSON을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-370">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="cf71a-371"><xref:System.Text.Json.JsonDocumentOptions>를 사용 하 여 입력 JSON의 주석이 허용 되지만 무시 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-371">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="cf71a-372">완료 되 면 작성기에서 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-372">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="cf71a-373">또는 삭제 될 때 작성자가 autoflush 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-373">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="cf71a-374">예제 코드에서 처리할 JSON 입력의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-374">Here's an example of JSON input to be processed by the example code:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Grades.json)]

<span data-ttu-id="cf71a-375">결과는 다음과 같이 잘 인쇄 된 JSON 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-375">The result is the following pretty-printed JSON output:</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/GradesPrettyPrint.json)]

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="cf71a-376">Utf8JsonWriter 사용</span><span class="sxs-lookup"><span data-stu-id="cf71a-376">Use Utf8JsonWriter</span></span>

<span data-ttu-id="cf71a-377">다음 예제에서는 <xref:System.Text.Json.Utf8JsonWriter> 클래스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-377">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8WriterToStream.cs?name=SnippetSerialize)]

## <a name="use-utf8jsonreader"></a><span data-ttu-id="cf71a-378">Utf8JsonReader 사용</span><span class="sxs-lookup"><span data-stu-id="cf71a-378">Use Utf8JsonReader</span></span>

<span data-ttu-id="cf71a-379">다음 예제에서는 <xref:System.Text.Json.Utf8JsonReader> 클래스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-379">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromBytes.cs?name=SnippetDeserialize)]

<span data-ttu-id="cf71a-380">위의 코드는 `jsonUtf8` 변수가 u t f-8로 인코딩된 유효한 JSON을 포함 하는 바이트 배열 이라고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-380">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="cf71a-381">Utf8JsonReader를 사용 하 여 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="cf71a-381">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="cf71a-382">다음 예제에서는 파일을 동기적으로 읽고 값을 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-382">The following example shows how to read a file synchronously and search for a value:</span></span>

[!code-csharp[](~/samples/snippets/core/system-text-json/csharp/Utf8ReaderFromFile.cs)]

<span data-ttu-id="cf71a-383">위의 코드:</span><span class="sxs-lookup"><span data-stu-id="cf71a-383">The preceding code:</span></span>

* <span data-ttu-id="cf71a-384">JSON에 개체 배열이 포함 되어 있다고 가정 하 고 각 개체에 문자열 형식의 "name" 속성이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-384">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="cf71a-385">"대학"으로 끝나는 개체 및 "이름" 속성 값의 개수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-385">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="cf71a-386">는 파일이 u t f-16으로 인코딩되고 u t f-8로 코드 변환 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-386">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="cf71a-387">U t f-8로 인코딩된 파일은 다음 코드를 사용 하 여 `ReadOnlySpan<byte>`직접 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-387">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

  <span data-ttu-id="cf71a-388">파일에 UTF-8 바이트 순서 표시 (BOM)가 포함 된 경우 판독기가 텍스트를 예상 하므로 `Utf8JsonReader`바이트를 전달 하기 전에이를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-388">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="cf71a-389">그렇지 않으면 BOM은 잘못 된 JSON으로 간주 되며 판독기는 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-389">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="cf71a-390">위의 코드에서 읽을 수 있는 JSON 샘플은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-390">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="cf71a-391">결과 요약 메시지는 "2-4 중에서 이름이 ' 대학 '로 끝나는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cf71a-391">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

[!code-json[](~/samples/snippets/core/system-text-json/csharp/Universities.json)]

## <a name="additional-resources"></a><span data-ttu-id="cf71a-392">추가 자료</span><span class="sxs-lookup"><span data-stu-id="cf71a-392">Additional resources</span></span>

* <span data-ttu-id="cf71a-393">[System.Text.Json 개요](system-text-json-overview.md)</span><span class="sxs-lookup"><span data-stu-id="cf71a-393">[System.Text.Json overview](system-text-json-overview.md)</span></span>
* [<span data-ttu-id="cf71a-394">사용자 지정 변환기를 작성 하는 방법</span><span class="sxs-lookup"><span data-stu-id="cf71a-394">How to write custom converters</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="cf71a-395">[Newtonsoft.Json에서 마이그레이션하는 방법](system-text-json-migrate-from-newtonsoft-how-to.md)</span><span class="sxs-lookup"><span data-stu-id="cf71a-395">[How to migrate from Newtonsoft.Json](system-text-json-migrate-from-newtonsoft-how-to.md)</span></span>
* <span data-ttu-id="cf71a-396">[System.Text.Json의 DateTime 및 DateTimeOffset 지원](../datetime/system-text-json-support.md)</span><span class="sxs-lookup"><span data-stu-id="cf71a-396">[DateTime and DateTimeOffset support in System.Text.Json](../datetime/system-text-json-support.md)</span></span>
* <span data-ttu-id="cf71a-397">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="cf71a-397">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
<!-- * [System.Text.Json roadmap](https://github.com/dotnet/runtime/blob/81bf79fd9aa75305e55abe2f7e9ef3f60624a3a1/src/libraries/System.Text.Json/roadmap/README.md)-->
