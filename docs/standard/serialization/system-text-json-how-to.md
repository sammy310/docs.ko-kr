---
title: -.Net을 사용 하 여 C# JSON을 serialize 및 deserialize 하는 방법
author: tdykstra
ms.author: tdykstra
ms.date: 09/16/2019
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: f0245feb710f33d5fcea2a7125b8753ba6064018
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73740438"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="0bc01-102">.NET에서 JSON을 serialize 및 deserialize 하는 방법</span><span class="sxs-lookup"><span data-stu-id="0bc01-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0bc01-103">JSON serialization 설명서는 생성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="0bc01-104">이 문서에서는 모든 시나리오를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="0bc01-105">자세한 내용은 GitHub의 dotnet/corefx 리포지토리, 특히 [json 기능-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc)에서 발생 하는 system.servicemodel [문제](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) 를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="0bc01-106">이 문서에서는 <xref:System.Text.Json> 네임 스페이스를 사용 하 여 JavaScript Object Notation (JSON)로 serialize 및 deserialize 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="0bc01-107">지침 및 샘플 코드는 [ASP.NET Core](/aspnet/core/)와 같은 프레임 워크가 아닌 라이브러리를 직접 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="0bc01-108">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="0bc01-108">Namespaces</span></span>

<span data-ttu-id="0bc01-109"><xref:System.Text.Json> 네임 스페이스에는 모든 진입점과 기본 형식이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="0bc01-110"><xref:System.Text.Json.Serialization> 네임 스페이스에는 serialization 및 deserialization과 관련 된 고급 시나리오 및 사용자 지정을 위한 특성 및 Api가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="0bc01-111">이 문서에 표시 된 코드 예제에는 다음 네임 스페이스 중 하나 또는 둘 다에 대 한 `using` 지시문이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-111">The code examples shown in this article require `using` directives for one or both of these namespaces:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="0bc01-112"><xref:System.Runtime.Serialization> 네임 스페이스의 특성은 현재 `System.Text.Json`에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="0bc01-113">JSON에 .NET 개체를 작성 하는 방법 (직렬화)</span><span class="sxs-lookup"><span data-stu-id="0bc01-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="0bc01-114">JSON을 문자열 또는 파일에 쓰려면 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-114">To write JSON to a string or to a file, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="0bc01-115">다음 예제에서는 JSON을 문자열로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-115">The following example creates JSON as a string:</span></span>

```csharp
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="0bc01-116">다음 예제에서는 동기 코드를 사용 하 여 JSON 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-116">The following example uses synchronous code to create a JSON file:</span></span>

```csharp
File.WriteAllText(outputFileName, JsonSerializer.Serialize(weatherForecast));
```

<span data-ttu-id="0bc01-117">다음 예제에서는 비동기 코드를 사용 하 여 JSON 파일을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-117">The following example uses asynchronous code to create a JSON file:</span></span>

```csharp
using (FileStream fs = File.Create(outputFileName))
{
    await JsonSerializer.SerializeAsync(fs, weatherForecast);
}
```

<span data-ttu-id="0bc01-118">앞의 예제에서는 serialize 되는 형식에 대 한 형식 유추를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-118">The preceding examples use type inference for the type being serialized.</span></span> <span data-ttu-id="0bc01-119">`Serialize()` 오버 로드는 제네릭 형식 매개 변수를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-119">An overload of `Serialize()` takes a generic type parameter:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

### <a name="serialization-example"></a><span data-ttu-id="0bc01-120">Serialization 예제</span><span class="sxs-lookup"><span data-stu-id="0bc01-120">Serialization example</span></span>

<span data-ttu-id="0bc01-121">컬렉션 및 중첩 클래스를 포함 하는 예제 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-121">Here's an example type that contains collections and nested classes:</span></span>

```csharp
public class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public IList<DateTimeOffset> DatesAvailable { get; set;}
    public Dictionary<string, HighLowTemperatures> TemperatureRanges { get; set; }
    public string [] SummaryWords { get; set; }
}

public class HighLowTemperatures
{
    public Temperature High { get; set; }
    public Temperature Low { get; set; }
}

public class Temperature
{
    public int DegreesCelsius { get; set; }
}
```

<span data-ttu-id="0bc01-122">이전 형식의 인스턴스를 serialize 하는 JSON 출력은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-122">The JSON output from serializing an instance of the preceding type looks like the following example.</span></span> <span data-ttu-id="0bc01-123">JSON 출력은 기본적으로 축소 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-123">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="0bc01-124">다음 예제에서는 동일한 JSON (공백 및 들여쓰기를 사용 하 여 잘 인쇄 됨)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-124">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "DatesAvailable": [
    "2019-08-01T00:00:00-07:00",
    "2019-08-02T00:00:00-07:00"
  ],
  "TemperatureRanges": {
    "Cold": {
      "High": {
        "DegreesCelsius": 20
      },
      "Low": {
        "DegreesCelsius": -10
      }
    },
    "Hot": {
      "High": {
        "DegreesCelsius": 60
      },
      "Low": {
        "DegreesCelsius": 20
      }
    }
  },
  "SummaryWords": [
    "Cool",
    "Windy",
    "Humid"
  ]
}
```

### <a name="serialize-to-utf-8"></a><span data-ttu-id="0bc01-125">U t f-8로 직렬화</span><span class="sxs-lookup"><span data-stu-id="0bc01-125">Serialize to UTF-8</span></span>

<span data-ttu-id="0bc01-126">U t f-8로 serialize 하려면 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-126">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] jsonUtf8Bytes = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="0bc01-127"><xref:System.Text.Json.Utf8JsonWriter>를 사용 하는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버 로드도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-127">A <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is also available.</span></span>

<span data-ttu-id="0bc01-128">U t f-8로 serialize 하는 것은 문자열 기반 메서드를 사용 하는 것 보다 약 5-10% 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-128">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="0bc01-129">차이점은 바이트 (u t f-8)를 문자열 (UTF-16)로 변환할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-129">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="0bc01-130">Serialization 동작</span><span class="sxs-lookup"><span data-stu-id="0bc01-130">Serialization behavior</span></span>

* <span data-ttu-id="0bc01-131">기본적으로 모든 public 속성이 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-131">By default, all public properties are serialized.</span></span> <span data-ttu-id="0bc01-132">[제외할 속성을 지정할](#exclude-properties-from-serialization)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-132">You can [specify properties to exclude](#exclude-properties-from-serialization).</span></span>
* <span data-ttu-id="0bc01-133">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) 는 ascii가 아닌 문자, ascii 범위 내의 HTML 구분 문자 및 [JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프 되어야 하는 문자를 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-133">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="0bc01-134">기본적으로 JSON은 축소 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-134">By default, JSON is minified.</span></span> <span data-ttu-id="0bc01-135">[JSON을 잘 인쇄할](#serialize-to-formatted-json)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-135">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="0bc01-136">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-136">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="0bc01-137">[JSON 이름 대/소문자를 사용자 지정할](#customize-json-names-and-values)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-137">You can [customize JSON name casing](#customize-json-names-and-values).</span></span>
* <span data-ttu-id="0bc01-138">순환 참조가 감지 되 고 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-138">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="0bc01-139">자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [순환 참조에 대 한 문제](https://github.com/dotnet/corefx/issues/38579) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bc01-139">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="0bc01-140">현재는 필드가 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-140">Currently, fields are excluded.</span></span>

<span data-ttu-id="0bc01-141">지원 되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-141">Supported types include:</span></span>

* <span data-ttu-id="0bc01-142">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-142">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="0bc01-143">사용자 정의 [일반 이전 CLR 개체 (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="0bc01-143">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="0bc01-144">1 차원 및 가변 배열 (`ArrayName[][]`)</span><span class="sxs-lookup"><span data-stu-id="0bc01-144">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="0bc01-145">`TValue` `object`, `JsonElement`또는 POCO 인 `Dictionary<string,TValue>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-145">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="0bc01-146">다음 네임 스페이스의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-146">Collections from the following namespaces.</span></span> <span data-ttu-id="0bc01-147">자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [컬렉션 지원에 대 한 문제](https://github.com/dotnet/corefx/issues/36643) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bc01-147">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

<span data-ttu-id="0bc01-148">추가 형식을 처리 하거나 기본 변환기에서 지원 하지 않는 기능을 제공 하는 [사용자 지정 변환기를 구현할](system-text-json-converters-how-to.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-148">You can [implement custom converters](system-text-json-converters-how-to.md) to handle additional types or provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="0bc01-149">JSON을 .NET 개체로 읽는 방법 (deserialize)</span><span class="sxs-lookup"><span data-stu-id="0bc01-149">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="0bc01-150">문자열이 나 파일에서 deserialize 하려면 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-150">To deserialize from a string or a file, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="0bc01-151">다음 예제에서는 문자열에서 JSON을 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-151">The following example reads JSON from a string:</span></span>

```csharp
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="0bc01-152">동기 코드를 사용 하 여 파일에서 deserialize 하려면 다음 예제와 같이 파일을 문자열로 읽습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-152">To deserialize from a file by using synchronous code, read the file into a string, as shown in the following example:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);
weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(jsonString);
```

<span data-ttu-id="0bc01-153">비동기 코드를 사용 하 여 파일에서 deserialize 하려면 <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-153">To deserialize from a file by using asynchronous code, call the <xref:System.Text.Json.JsonSerializer.DeserializeAsync%2A> method:</span></span>

```csharp
using (FileStream fs = File.OpenRead(inputFileName))
{
    weatherForecast = await JsonSerializer.DeserializeAsync<WeatherForecast>(fs);
}
```

<span data-ttu-id="0bc01-154">예제 형식 및 해당 JSON은 [Serialization 예제](#serialization-example) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bc01-154">For an example type and corresponding JSON, see the [Serialization example](#serialization-example) section.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="0bc01-155">U t f-8에서 Deserialize</span><span class="sxs-lookup"><span data-stu-id="0bc01-155">Deserialize from UTF-8</span></span>

<span data-ttu-id="0bc01-156">U t f-8에서 deserialize 하려면 다음 예제와 같이 `Utf8JsonReader` 또는 `ReadOnlySpan<byte>`를 사용 하는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 오버 로드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-156">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples.</span></span> <span data-ttu-id="0bc01-157">이 예에서는 JSON이 jsonUtf8Bytes 이라는 바이트 배열에 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-157">The examples assume the JSON is in a byte array named jsonUtf8Bytes.</span></span>

```csharp
var readOnlySpan = new ReadOnlySpan<byte>(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
var utf8Reader = new Utf8JsonReader(jsonUtf8Bytes);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="0bc01-158">Deserialization 동작</span><span class="sxs-lookup"><span data-stu-id="0bc01-158">Deserialization behavior</span></span>

* <span data-ttu-id="0bc01-159">기본적으로 속성 이름 일치는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-159">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="0bc01-160">[대/소문자](#case-insensitive-property-matching)를 구분 하지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-160">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="0bc01-161">JSON에 읽기 전용 속성에 대 한 값이 포함 된 경우에는이 값이 무시 되 고 예외가 throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-161">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="0bc01-162">매개 변수가 없는 생성자가 없는 참조 형식으로의 Deserialization은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-162">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="0bc01-163">변경할 수 없는 개체 또는 읽기 전용 속성에 대 한 Deserialization은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-163">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="0bc01-164">자세한 내용은 github의 dotnet/corefx 리포지토리에서 [변경 불가능 한 개체 지원](https://github.com/dotnet/corefx/issues/38569) 및 [읽기 전용 속성 지원 문제](https://github.com/dotnet/corefx/issues/38163) 에 대 한 github 문제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bc01-164">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="0bc01-165">기본적으로 열거형은 숫자로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-165">By default, enums are supported as numbers.</span></span> <span data-ttu-id="0bc01-166">[열거형 이름을 문자열로 serialize](#enums-as-strings)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-166">You can [serialize enum names as strings](#enums-as-strings).</span></span>
* <span data-ttu-id="0bc01-167">필드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-167">Fields aren't supported.</span></span>
* <span data-ttu-id="0bc01-168">기본적으로 JSON의 주석이 나 후행 쉼표는 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-168">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="0bc01-169">[주석과 후행 쉼표를 허용할](#allow-comments-and-trailing-commas)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-169">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas).</span></span>
* <span data-ttu-id="0bc01-170">[기본 최대 깊이](xref:System.Text.Json.JsonReaderOptions.MaxDepth) 는 64입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-170">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

<span data-ttu-id="0bc01-171">기본 변환기에서 지원 하지 않는 기능을 제공 하기 위해 [사용자 지정 변환기를 구현할](system-text-json-converters-how-to.md) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-171">You can [implement custom converters](system-text-json-converters-how-to.md) to provide functionality that isn't supported by the built-in converters.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="0bc01-172">형식이 지정 된 JSON으로 직렬화</span><span class="sxs-lookup"><span data-stu-id="0bc01-172">Serialize to formatted JSON</span></span>

<span data-ttu-id="0bc01-173">JSON 출력을 잘 인쇄 하려면 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>를 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-173">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0bc01-174">다음은 serialize 되 고 잘 인쇄 되는 JSON 출력의 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-174">Here's an example type to be serialized and pretty-printed JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

## <a name="customize-json-names-and-values"></a><span data-ttu-id="0bc01-175">JSON 이름 및 값 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0bc01-175">Customize JSON names and values</span></span>

<span data-ttu-id="0bc01-176">기본적으로 속성 이름 및 사전 키는 대/소문자를 포함 하 여 JSON 출력에서 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-176">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="0bc01-177">열거형 값은 숫자로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-177">Enum values are represented as numbers.</span></span> <span data-ttu-id="0bc01-178">이 섹션에서는 다음을 수행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-178">This section explains how to:</span></span>

* <span data-ttu-id="0bc01-179">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0bc01-179">Customize individual property names</span></span>
* <span data-ttu-id="0bc01-180">모든 속성 이름을 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="0bc01-180">Convert all property names to camel case</span></span>
* <span data-ttu-id="0bc01-181">사용자 지정 속성 명명 정책 구현</span><span class="sxs-lookup"><span data-stu-id="0bc01-181">Implement a custom property naming policy</span></span>
* <span data-ttu-id="0bc01-182">사전 키를 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="0bc01-182">Convert dictionary keys to camel case</span></span>
* <span data-ttu-id="0bc01-183">문자열 및 카멜식 대/소문자로 열거형 변환</span><span class="sxs-lookup"><span data-stu-id="0bc01-183">Convert enums to strings and camel case</span></span> 

<span data-ttu-id="0bc01-184">JSON 속성 이름 및 값을 특수 하 게 처리 해야 하는 다른 시나리오의 경우 [사용자 지정 변환기를 구현할](system-text-json-converters-how-to.md)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-184">For other scenarios that require special handling of JSON property names and values, you can [implement custom converters](system-text-json-converters-how-to.md).</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="0bc01-185">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0bc01-185">Customize individual property names</span></span>

<span data-ttu-id="0bc01-186">개별 속성의 이름을 설정 하려면 [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-186">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="0bc01-187">직렬화 및 결과 JSON의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-187">Here's an example type to serialize and resulting JSON:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="0bc01-188">이 특성에 의해 설정 된 속성 이름:</span><span class="sxs-lookup"><span data-stu-id="0bc01-188">The property name set by this attribute:</span></span>

* <span data-ttu-id="0bc01-189">Serialization 및 deserialization을 위해 양방향으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-189">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="0bc01-190">속성 명명 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-190">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="0bc01-191">모든 JSON 속성 이름에 카멜식 대/소문자 사용</span><span class="sxs-lookup"><span data-stu-id="0bc01-191">Use camel case for all JSON property names</span></span>

<span data-ttu-id="0bc01-192">모든 JSON 속성 이름에 카멜식 대/소문자를 사용 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>를 `JsonNamingPolicy.CamelCase`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-192">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0bc01-193">직렬화 및 JSON 출력에 대 한 예제 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-193">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureCelsius { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureCelsius": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="0bc01-194">카멜식 대/소문자 속성 명명 정책:</span><span class="sxs-lookup"><span data-stu-id="0bc01-194">The camel case property naming policy:</span></span>

* <span data-ttu-id="0bc01-195">Serialization 및 deserialization에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-195">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="0bc01-196">`[JsonPropertyName]` 특성에 의해 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-196">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="0bc01-197">이 때문에이 예제에서 JSON 속성 이름 `Wind`는 카멜식 대/소문자가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-197">This is why the JSON property name `Wind` in the example is not camel case.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="0bc01-198">사용자 지정 JSON 속성 명명 정책 사용</span><span class="sxs-lookup"><span data-stu-id="0bc01-198">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="0bc01-199">사용자 지정 JSON 속성 명명 정책을 사용 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonNamingPolicy>에서 파생 되는 클래스를 만들고 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-199">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="0bc01-200">그런 다음 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 속성을 명명 정책 클래스의 인스턴스로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-200">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0bc01-201">직렬화 및 JSON 출력에 대 한 예제 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-201">Here's an example class to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonPropertyName("Wind")]
    public int WindSpeed { get; set; }
}
```

```json
{
  "DATE": "2019-08-01T00:00:00-07:00",
  "TEMPERATUREC": 25,
  "SUMMARY": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="0bc01-202">JSON 속성 명명 정책:</span><span class="sxs-lookup"><span data-stu-id="0bc01-202">The JSON property naming policy:</span></span>

* <span data-ttu-id="0bc01-203">Serialization 및 deserialization에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-203">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="0bc01-204">`[JsonPropertyName]` 특성에 의해 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-204">Is overridden by `[JsonPropertyName]` attributes.</span></span> <span data-ttu-id="0bc01-205">이 때문에이 예제의 JSON 속성 이름 `Wind` 대문자는 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-205">This is why the JSON property name `Wind` in the example is not upper case.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="0bc01-206">카멜식 대/소문자 사전 키</span><span class="sxs-lookup"><span data-stu-id="0bc01-206">Camel case dictionary keys</span></span>

<span data-ttu-id="0bc01-207">Serialize 할 개체의 속성이 `Dictionary<string,TValue>`형식이 면 `string` 키를 카멜식 대/소문자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-207">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="0bc01-208">이렇게 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy>를 `JsonNamingPolicy.CamelCase`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-208">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0bc01-209">키-값 쌍 `"HotMinTemp", 40` `"ColdMinTemp", 20` 키-값 쌍이 있는 `TemperatureRanges` 라는 사전이 포함 된 개체를 serialize 하면 다음 예제와 같이 JSON 출력이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-209">Serializing an object with a dictionary named `TemperatureRanges` that has key-value pairs `"ColdMinTemp", 20` and `"HotMinTemp", 40` would result in JSON output like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "coldMinTemp": 20,
    "hotMinTemp": 40
  }
}
```

<span data-ttu-id="0bc01-210">사전 키에 대 한 카멜식 대/소문자 명명 정책은 serialization에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-210">The camel case naming policy for dictionary keys applies to serialization only.</span></span> <span data-ttu-id="0bc01-211">사전을 deserialize 하면 `DictionaryKeyPolicy`에 대 한 `JsonNamingPolicy.CamelCase` 지정 하더라도 키가 JSON 파일과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-211">If you deserialize a dictionary, the keys will match the JSON file even if you specify `JsonNamingPolicy.CamelCase` for the `DictionaryKeyPolicy`.</span></span>

### <a name="enums-as-strings"></a><span data-ttu-id="0bc01-212">문자열로 된 열거형</span><span class="sxs-lookup"><span data-stu-id="0bc01-212">Enums as strings</span></span>

<span data-ttu-id="0bc01-213">기본적으로 열거형은 숫자로 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-213">By default, enums are serialized as numbers.</span></span> <span data-ttu-id="0bc01-214">열거형 이름을 문자열로 serialize 하려면 <xref:System.Text.Json.Serialization.JsonStringEnumConverter>을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-214">To serialize enum names as strings, use the <xref:System.Text.Json.Serialization.JsonStringEnumConverter>.</span></span>

<span data-ttu-id="0bc01-215">예를 들어, 열거형을 포함 하는 다음 클래스를 serialize 해야 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-215">For example, suppose you need to serialize the following class that has an enum:</span></span>

```csharp
class WeatherForecastWithEnum
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public Summary Summary { get; set; }
}

public enum Summary
{
    Cold, Cool, Warm, Hot
}
```

<span data-ttu-id="0bc01-216">요약이 `Hot`되는 경우 기본적으로 직렬화 된 JSON에는 숫자 값 3이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-216">If the Summary is `Hot`, by default the serialized JSON has the numeric value 3:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": 3
}
```

<span data-ttu-id="0bc01-217">다음 샘플 코드에서는 열거형 이름을 대신 직렬화 하 고이를 카멜식 대/소문자로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-217">The following sample code serializes the enum names instead, and converts them to camel case:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
jsonWithEnumsAsStrings = JsonSerializer.Serialize(weatherForecastWithEnum, options);
```

<span data-ttu-id="0bc01-218">결과 JSON은 다음 예제와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-218">The resulting JSON looks like the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "hot"
}
```

<span data-ttu-id="0bc01-219">다음 예제에 표시 된 것과 같이 문자열로 열거형에 대 한 지원도 deserialization에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-219">The support for enums as strings applies to deserialization also, as shown in the following example:</span></span>

```csharp
options = new JsonSerializerOptions();
options.Converters.Add(new JsonStringEnumConverter(JsonNamingPolicy.CamelCase));
weatherForecastWithEnum = JsonSerializer.Deserialize<WeatherForecastWithEnum>(jsonWithEnumsAsStrings, options);
```

## <a name="exclude-properties-from-serialization"></a><span data-ttu-id="0bc01-220">Serialization에서 속성 제외</span><span class="sxs-lookup"><span data-stu-id="0bc01-220">Exclude properties from serialization</span></span>

<span data-ttu-id="0bc01-221">기본적으로 모든 public 속성이 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-221">By default, all public properties are serialized.</span></span> <span data-ttu-id="0bc01-222">JSON 출력에 표시 하지 않으려는 경우 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-222">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="0bc01-223">이 섹션에서는 다음을 제외 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-223">This section explains how to exclude:</span></span>

* <span data-ttu-id="0bc01-224">개별 속성</span><span class="sxs-lookup"><span data-stu-id="0bc01-224">Individual properties</span></span>
* <span data-ttu-id="0bc01-225">모든 읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="0bc01-225">All read-only properties</span></span>
* <span data-ttu-id="0bc01-226">모든 null 값 속성</span><span class="sxs-lookup"><span data-stu-id="0bc01-226">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="0bc01-227">개별 속성 제외</span><span class="sxs-lookup"><span data-stu-id="0bc01-227">Exclude individual properties</span></span>

<span data-ttu-id="0bc01-228">개별 속성을 무시 하려면 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-228">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="0bc01-229">다음은 serialize 및 JSON 출력에 대 한 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-229">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonIgnore]
    public int WindSpeed { get; set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="0bc01-230">모든 읽기 전용 속성을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-230">Exclude all read-only properties</span></span>

<span data-ttu-id="0bc01-231">공용 setter가 아닌 공용 getter가 포함 된 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-231">A property is read-only if it contains a public getter but not a public setter.</span></span> <span data-ttu-id="0bc01-232">모든 읽기 전용 속성을 제외 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>를 `true`으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-232">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0bc01-233">다음은 serialize 및 JSON 출력에 대 한 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-233">Here's an example type to serialize and JSON output:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    public int WindSpeed { get; private set; }
}
```

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
}
```

<span data-ttu-id="0bc01-234">이 옵션은 serialization에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-234">This option applies only to serialization.</span></span> <span data-ttu-id="0bc01-235">Deserialization을 수행 하는 동안 읽기 전용 속성은 기본적으로 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-235">During deserialization, read-only properties are ignored by default.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="0bc01-236">모든 null 값 속성 제외</span><span class="sxs-lookup"><span data-stu-id="0bc01-236">Exclude all null value properties</span></span>

<span data-ttu-id="0bc01-237">모든 null 값 속성을 제외 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-237">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0bc01-238">직렬화 및 JSON 출력에 대 한 예제 개체는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-238">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="0bc01-239">속성</span><span class="sxs-lookup"><span data-stu-id="0bc01-239">Property</span></span> |<span data-ttu-id="0bc01-240">값</span><span class="sxs-lookup"><span data-stu-id="0bc01-240">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="0bc01-241">날짜</span><span class="sxs-lookup"><span data-stu-id="0bc01-241">Date</span></span>    | <span data-ttu-id="0bc01-242">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="0bc01-242">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="0bc01-243">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="0bc01-243">TemperatureC</span></span>| <span data-ttu-id="0bc01-244">25</span><span class="sxs-lookup"><span data-stu-id="0bc01-244">25</span></span> |
| <span data-ttu-id="0bc01-245">요약</span><span class="sxs-lookup"><span data-stu-id="0bc01-245">Summary</span></span>| <span data-ttu-id="0bc01-246">null</span><span class="sxs-lookup"><span data-stu-id="0bc01-246">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="0bc01-247">이 설정은 serialization 및 deserialization에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-247">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="0bc01-248">Deserialization에 미치는 영향에 대 한 자세한 내용은 [deserialize 할 때 Null 무시](#ignore-null-when-deserializing)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bc01-248">For information about its effect on deserialization, see [Ignore null when deserializing](#ignore-null-when-deserializing).</span></span>

## <a name="customize-character-encoding"></a><span data-ttu-id="0bc01-249">문자 인코딩 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="0bc01-249">Customize character encoding</span></span>

<span data-ttu-id="0bc01-250">기본적으로 serializer는 ASCII가 아닌 문자를 모두 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-250">By default, the serializer escapes all non-ASCII characters.</span></span>  <span data-ttu-id="0bc01-251">즉, `xxxxx`가 문자의 유니코드 코드 인 `\uxxxx`로 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-251">That is, it replaces them with `\uxxxx` where `xxxxx` is the Unicode code of the character.</span></span>  <span data-ttu-id="0bc01-252">예를 들어 `Summary` 속성이 키릴 자모 жарко로 설정 된 경우이 예제와 같이 `WeatherForecast` 개체가 serialize 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-252">For example, if the `Summary` property is set to Cyrillic жарко, the `WeatherForecast` object is serialized as shown in this example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "\u0436\u0430\u0440\u043A\u043E"
}
```

### <a name="serialize-language-character-sets"></a><span data-ttu-id="0bc01-253">언어 문자 집합 Serialize</span><span class="sxs-lookup"><span data-stu-id="0bc01-253">Serialize language character sets</span></span>

<span data-ttu-id="0bc01-254">하나 이상의 언어의 문자 집합을 serialize 하려면 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>의 인스턴스를 만들 때 [유니코드 범위](xref:System.Text.Unicode.UnicodeRanges) 를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-254">To serialize the character set(s) of one or more languages, specify [Unicode range(s)](xref:System.Text.Unicode.UnicodeRanges) when creating an instance of <xref:System.Text.Encodings.Web.JavaScriptEncoder?displayProperty=fullName>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(UnicodeRanges.Cyrillic, UnicodeRanges.GreekExtended)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0bc01-255">이 코드는 키릴 자모와 그리스어 문자를 직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-255">This code serializes Cyrillic and Greek characters.</span></span> <span data-ttu-id="0bc01-256">다음 예제에서는 키릴 자모 문자를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-256">Cyrillic characters are shown in the following example:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жарко",
}
```

<span data-ttu-id="0bc01-257">모든 언어를 지정 하려면 <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-257">To specify all languages, use <xref:System.Text.Unicode.UnicodeRanges.All?displayProperty=nameWithType>.</span></span>

### <a name="serialize-specific-characters"></a><span data-ttu-id="0bc01-258">특정 문자 Serialize</span><span class="sxs-lookup"><span data-stu-id="0bc01-258">Serialize specific characters</span></span>

<span data-ttu-id="0bc01-259">대안은 이스케이프 되지 않고에서 허용 하려는 개별 문자를 지정 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-259">An alternative is to specify individual characters that you want to allow through without being escaped.</span></span> <span data-ttu-id="0bc01-260">다음 예제에서는 жарко의 처음 두 자만 직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-260">The following example serializes only the first two characters of жарко:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
using System.Text.Unicode;
```

```csharp
var encoderSettings = new TextEncoderSettings();
encoderSettings.AllowCharacters('\u0436', '\u0430');
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.Create(encoderSettings)
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="0bc01-261">앞의 코드에서 생성 된 JSON의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-261">Here's an example of JSON produced by the preceding code:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "жа\u0440\u043A\u043E"
}
```

### <a name="serialize-all-characters"></a><span data-ttu-id="0bc01-262">모든 문자를 직렬화 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-262">Serialize all characters</span></span>

<span data-ttu-id="0bc01-263">이스케이프를 최소화 하기 위해 다음 예제와 같이 <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-263">To minimize escaping you can use <xref:System.Text.Encodings.Web.JavaScriptEncoder.UnsafeRelaxedJsonEscaping?displayProperty=nameWithType>, as shown in the following example:</span></span>

```csharp
using System.Text.Encodings.Web;
using System.Text.Json;
```

```csharp
options = new JsonSerializerOptions
{
    Encoder = JavaScriptEncoder.UnsafeRelaxedJsonEscaping
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

> [!CAUTION]
> <span data-ttu-id="0bc01-264">기본 인코더와 달리 `UnsafeRelaxedJsonEscaping` 인코더는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-264">Unlike the default encoder, the `UnsafeRelaxedJsonEscaping` encoder:</span></span>
>
> * <span data-ttu-id="0bc01-265">는 `<`, `>`, `&`및 `'`과 같은 HTML 구분 문자를 이스케이프 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-265">Doesn't escape HTML-sensitive characters such as `<`, `>`, `&`, and `'`.</span></span>
> * <span data-ttu-id="0bc01-266">는 클라이언트와 서버에서 *문자 집합*에 동의 하지 않을 수 있는 것과 같은 XSS 또는 정보 공개 공격에 대해 심층 방어를 추가로 보호 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-266">Doesn't offer any additional defense-in-depth protections against XSS or information disclosure attacks, such as those which might result from the client and server disagreeing on the *charset*.</span></span>
> * <span data-ttu-id="0bc01-267">는 문자가 이스케이프 되지 않은에서 전달 될 수 있는 기본 인코더 보다 더 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-267">Is more permissive than the default encoder on which characters are allowed to pass through unescaped.</span></span>
>
> <span data-ttu-id="0bc01-268">클라이언트에서 결과 페이로드를 u t f-8로 인코딩된 JSON으로 해석 하는 것으로 알려진 경우에만 안전 하지 않은 인코더를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-268">Use the unsafe encoder only when it's known that the client will be interpreting the resulting payload as UTF-8 encoded JSON.</span></span> <span data-ttu-id="0bc01-269">예를 들어 서버에서 응답 헤더 `Content-Type: application/json; charset=utf-8`보내는 경우이를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-269">For example, you can use it if the server is sending the response header `Content-Type: application/json; charset=utf-8`.</span></span> <span data-ttu-id="0bc01-270">원시 `UnsafeRelaxedJsonEscaping` 출력을 HTML 페이지나 `<script>` 요소로 내보낼 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-270">Never allow the raw `UnsafeRelaxedJsonEscaping` output to be emitted into an HTML page or a `<script>` element.</span></span>

## <a name="serialize-properties-of-derived-classes"></a><span data-ttu-id="0bc01-271">파생 클래스의 속성 직렬화</span><span class="sxs-lookup"><span data-stu-id="0bc01-271">Serialize properties of derived classes</span></span>

<span data-ttu-id="0bc01-272">컴파일 시간에 serialize 할 형식을 지정 하는 경우 다형성 serialization이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-272">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="0bc01-273">예를 들어 `WeatherForecast` 클래스와 파생 클래스 `WeatherForecastWithWind`있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-273">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
class WeatherForecastWithWind : WeatherForecast
{
    public int WindSpeed { get; set; }
}
```

<span data-ttu-id="0bc01-274">컴파일 시간에 `Serialize` 메서드의 형식 인수를 `WeatherForecast`한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-274">And suppose the type argument of the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="0bc01-275">이 시나리오에서는 `weatherForecast` 개체가 실제로 `WeatherForecastWithWind` 개체인 경우에도 `WindSpeed` 속성이 serialize 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-275">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="0bc01-276">기본 클래스 속성만 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-276">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="0bc01-277">이 동작은 파생 된 런타임 생성 형식에서 실수로 데이터가 노출 되는 것을 방지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-277">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="0bc01-278">파생 형식의 속성을 serialize 하려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-278">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="0bc01-279">런타임에 형식을 지정할 수 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A> 오버 로드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-279">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="0bc01-280">`object`로 serialize 될 개체를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-280">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="0bc01-281">위의 예제 시나리오에서 두 가지 방법으로 인해 `WindSpeed` 속성이 JSON 출력에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-281">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

<span data-ttu-id="0bc01-282">다형 deserialization에 대 한 자세한 내용은 [다형성 Deserialization 지원](system-text-json-converters-how-to.md#support-polymorphic-deserialization)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bc01-282">For information about polymorphic deserialization, see [Support polymorphic deserialization](system-text-json-converters-how-to.md#support-polymorphic-deserialization).</span></span>

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="0bc01-283">주석과 후행 쉼표 허용</span><span class="sxs-lookup"><span data-stu-id="0bc01-283">Allow comments and trailing commas</span></span>

<span data-ttu-id="0bc01-284">기본적으로 주석 및 후행 쉼표는 JSON에서 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-284">By default, comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="0bc01-285">JSON에서 주석을 허용 하려면 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 속성을 `JsonCommentHandling.Skip`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-285">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="0bc01-286">그리고 후행 쉼표를 허용 하려면 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-286">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="0bc01-287">다음 예제에서는 두 가지를 모두 허용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-287">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="0bc01-288">다음은 주석과 후행 쉼표를 사용 하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-288">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="0bc01-289">대/소문자를 구분 하지 않는 속성 일치</span><span class="sxs-lookup"><span data-stu-id="0bc01-289">Case-insensitive property matching</span></span>

<span data-ttu-id="0bc01-290">기본적으로 deserialization은 JSON과 대상 개체 속성 간에 일치 하는 대/소문자를 구분 하는 속성 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-290">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="0bc01-291">이 동작을 변경 하려면 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> `true`으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-291">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="0bc01-292">카멜식 대/소문자 속성 이름을 사용 하는 JSON 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-292">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="0bc01-293">파스칼식 대/소문자 속성 이름을 포함 하는 다음 형식으로 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-293">It can be deserialized into the following type that has Pascal case property names.</span></span>

```json
{
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
}
```

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="0bc01-294">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="0bc01-294">Handle overflow JSON</span></span>

<span data-ttu-id="0bc01-295">Deserialize 하는 동안 대상 형식의 속성으로 표시 되지 않는 데이터를 JSON에 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-295">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="0bc01-296">예를 들어 대상 형식이 다음과 같다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-296">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="0bc01-297">Deserialize 할 JSON은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-297">And the JSON to be deserialized is this:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
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

<span data-ttu-id="0bc01-298">표시 된 형식에 표시 된 JSON을 deserialize 하는 경우 `DatesAvailable` 및 `SummaryWords` 속성은 이동 하지 않으며 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-298">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="0bc01-299">이러한 속성과 같은 추가 데이터를 캡처하려면 `Dictionary<string,object>` 또는 `Dictionary<string,JsonElement>`형식의 속성에 [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) 특성을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-299">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
    [JsonExtensionData]
    public Dictionary<string, object> ExtensionData { get; set; }
}
```

<span data-ttu-id="0bc01-300">앞에서 설명한 JSON을이 샘플 형식으로 deserialize 하는 경우 추가 데이터는 `ExtensionData` 속성의 키-값 쌍이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-300">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="0bc01-301">속성</span><span class="sxs-lookup"><span data-stu-id="0bc01-301">Property</span></span> |<span data-ttu-id="0bc01-302">값</span><span class="sxs-lookup"><span data-stu-id="0bc01-302">Value</span></span>  |<span data-ttu-id="0bc01-303">노트</span><span class="sxs-lookup"><span data-stu-id="0bc01-303">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="0bc01-304">날짜</span><span class="sxs-lookup"><span data-stu-id="0bc01-304">Date</span></span>    | <span data-ttu-id="0bc01-305">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="0bc01-305">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="0bc01-306">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="0bc01-306">TemperatureC</span></span>| <span data-ttu-id="0bc01-307">0</span><span class="sxs-lookup"><span data-stu-id="0bc01-307">0</span></span> | <span data-ttu-id="0bc01-308">대/소문자를 구분 하는 불일치 (JSON의`temperatureC`) 이므로 속성은 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-308">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="0bc01-309">요약</span><span class="sxs-lookup"><span data-stu-id="0bc01-309">Summary</span></span> | <span data-ttu-id="0bc01-310">핫스폿을</span><span class="sxs-lookup"><span data-stu-id="0bc01-310">Hot</span></span> ||
| <span data-ttu-id="0bc01-311">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="0bc01-311">ExtensionData</span></span> | <span data-ttu-id="0bc01-312">temperatureC: 25</span><span class="sxs-lookup"><span data-stu-id="0bc01-312">temperatureC: 25</span></span> |<span data-ttu-id="0bc01-313">Case가 일치 하지 않기 때문에이 JSON 속성은 추가 이며 사전에서 키-값 쌍이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-313">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="0bc01-314">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="0bc01-314">DatesAvailable:</span></span><br>  <span data-ttu-id="0bc01-315">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="0bc01-315">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="0bc01-316">오전 8/2/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="0bc01-316">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="0bc01-317">JSON의 추가 속성은 키-값 쌍이 되며 배열은 값 개체로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-317">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="0bc01-318">요약 단어:</span><span class="sxs-lookup"><span data-stu-id="0bc01-318">SummaryWords:</span></span><br><span data-ttu-id="0bc01-319">표</span><span class="sxs-lookup"><span data-stu-id="0bc01-319">Cool</span></span><br><span data-ttu-id="0bc01-320">바람</span><span class="sxs-lookup"><span data-stu-id="0bc01-320">Windy</span></span><br><span data-ttu-id="0bc01-321">Humid</span><span class="sxs-lookup"><span data-stu-id="0bc01-321">Humid</span></span> |<span data-ttu-id="0bc01-322">JSON의 추가 속성은 키-값 쌍이 되며 배열은 값 개체로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-322">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="0bc01-323">대상 개체가 serialize 되 면 확장 데이터 키 값 쌍은 수신 JSON에 있는 것 처럼 JSON 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-323">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 0,
  "Summary": "Hot",
  "temperatureC": 25,
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

<span data-ttu-id="0bc01-324">`ExtensionData` 속성 이름이 JSON에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-324">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="0bc01-325">이 동작을 통해 JSON은 deserialize 되지 않는 추가 데이터를 잃지 않고도 라운드트립을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-325">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="ignore-null-when-deserializing"></a><span data-ttu-id="0bc01-326">Deserialize 할 때 null 무시</span><span class="sxs-lookup"><span data-stu-id="0bc01-326">Ignore null when deserializing</span></span>

<span data-ttu-id="0bc01-327">기본적으로 JSON의 속성이 null 이면 대상 개체의 해당 속성이 null로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-327">By default, if a property in JSON is null, the corresponding property in the target object is set to null.</span></span> <span data-ttu-id="0bc01-328">일부 시나리오에서는 대상 속성에 기본값이 있을 수 있으며 null 값이 기본값을 재정의 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-328">In some scenarios, the target property might have a default value, and you don't want a null value to override the default.</span></span>

<span data-ttu-id="0bc01-329">예를 들어 다음 코드는 대상 개체를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-329">For example, suppose the following code represents your target object:</span></span>

```csharp
class WeatherForecastWithDefault
{
    public WeatherForecastWithDefault()
    {
        Summary = "No summary";
    }
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="0bc01-330">다음 JSON을 deserialize 한다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-330">And suppose the following JSON is deserialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": null,
}
```

<span data-ttu-id="0bc01-331">Deserialization 후 `WeatherForecastWithDefault` 개체의 `Summary` 속성은 null입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-331">After deserialization, the `Summary` property of the `WeatherForecastWithDefault` object is null.</span></span>

<span data-ttu-id="0bc01-332">이 동작을 변경 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType>를 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-332">To change this behavior, set <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
weatherForecast = JsonSerializer.Deserialize<WeatherForecastWithDefault>(json, options);
```

<span data-ttu-id="0bc01-333">이 옵션을 사용 하는 경우 `WeatherForecastWithDefault` 개체의 `Summary` 속성이 deserialization 후의 기본값 "요약 없음"입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-333">With this option, the `Summary` property of the `WeatherForecastWithDefault` object is the default value "No summary" after deserialization.</span></span>

<span data-ttu-id="0bc01-334">JSON의 Null 값은 유효한 경우에만 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-334">Null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="0bc01-335">Null을 허용 하지 않는 값 형식에 대 한 Null 값은 예외를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-335">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="0bc01-336">자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [nullable이 아닌 값 형식에 대 한 문제](https://github.com/dotnet/corefx/issues/40922) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0bc01-336">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="utf8jsonreader-utf8jsonwriter-and-jsondocument"></a><span data-ttu-id="0bc01-337">Utf8JsonReader, Utf8JsonWriter 및 JsonDocument</span><span class="sxs-lookup"><span data-stu-id="0bc01-337">Utf8JsonReader, Utf8JsonWriter, and JsonDocument</span></span>

<span data-ttu-id="0bc01-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>는 `ReadOnlySpan<byte>`에서 읽어온 UTF-8 인코드된 JSON 텍스트를 위한 고성능, 저할당, 전달 전용 판독기입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-338"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="0bc01-339">`Utf8JsonReader`는 사용자 지정 파서 및 deserializers를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-339">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="0bc01-340"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonReader`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-340">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="0bc01-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>는 `String`, `Int32`및 `DateTime`같은 일반적인 .NET 유형에 서 UTF-8 인코딩 JSON 텍스트를 작성 하는 고성능 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-341"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="0bc01-342">기록기는 사용자 지정 serializer를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-342">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="0bc01-343"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonWriter`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-343">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="0bc01-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName>는 `Utf8JsonReader`를 사용 하 여 읽기 전용 문서 개체 모델 (DOM)를 빌드하는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-344"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="0bc01-345">DOM은 JSON 페이로드의 데이터에 대 한 임의 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-345">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="0bc01-346">페이로드를 구성 하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-346">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="0bc01-347">`JsonElement`는 Api와 함께 배열 및 개체 열거자를 제공 하 여 JSON 텍스트를 일반적인 .NET 형식으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-347">The `JsonElement` provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="0bc01-348">`JsonDocument` <xref:System.Text.Json.JsonDocument.RootElement> 속성을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-348">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="0bc01-349">다음 섹션에서는 JSON을 읽고 쓰기 위해 이러한 도구를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-349">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="0bc01-350">JsonDocument를 사용 하 여 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="0bc01-350">Use JsonDocument for access to data</span></span>

<span data-ttu-id="0bc01-351">다음 예제에서는 <xref:System.Text.Json.JsonDocument> 클래스를 사용 하 여 데이터에 대 한 임의 액세스를 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-351">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data:</span></span>

```csharp
double sum = 0;
int count = 0;

using (JsonDocument document = JsonDocument.Parse(jsonString))
{
    JsonElement root = document.RootElement;
    JsonElement studentsElement = root.GetProperty("Students");
    foreach (JsonElement student in studentsElement.EnumerateArray())
    {
        if (student.TryGetProperty("Grade", out JsonElement gradeElement))
        {
            sum += gradeElement.GetDouble();
        }
        else
        {
            sum += 70;
        }
        count++;
    }
}

double average = sum / count;
Console.WriteLine($"Average grade: {average}");
```

<span data-ttu-id="0bc01-352">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="0bc01-352">The preceding code:</span></span>

* <span data-ttu-id="0bc01-353">JSON을 분석 하는 것이 `jsonString`라는 문자열에 있다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-353">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="0bc01-354">`Grade` 속성이 있는 `Students` 배열의 개체에 대 한 평균 등급을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-354">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span> 
* <span data-ttu-id="0bc01-355">등급이 없는 학생의 기본 등급 (70)을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-355">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="0bc01-356">각 반복으로 `count` 변수를 증가 시켜 학생 수를 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-356">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="0bc01-357">대신 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-357">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>:</span></span>

  ```csharp
  count = studentsElement.GetArrayLength();
  ```

<span data-ttu-id="0bc01-358">이 코드에서 처리 하는 JSON의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-358">Here's an example of the JSON that this code processes:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher's Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="0bc01-359">JsonDocument를 사용 하 여 JSON 쓰기</span><span class="sxs-lookup"><span data-stu-id="0bc01-359">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="0bc01-360">다음 예제에서는 <xref:System.Text.Json.JsonDocument>에서 JSON을 작성 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-360">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

```csharp
string jsonString = File.ReadAllText(inputFileName);

var writerOptions = new JsonWriterOptions { Indented = true };
var documentOptions = new JsonDocumentOptions { CommentHandling = JsonCommentHandling.Skip };

using (FileStream fs = File.Create(outputFileName))
using (var writer = new Utf8JsonWriter(fs, options: writerOptions))
using (JsonDocument document = JsonDocument.Parse(jsonString, documentOptions))
{
    JsonElement root = document.RootElement;

    if (root.ValueKind == JsonValueKind.Object)
    {
        writer.WriteStartObject();
    }
    else
    {
        return;
    }

    foreach (JsonProperty property in root.EnumerateObject())
    {
        property.WriteTo(writer);
    }

    writer.WriteEndObject();

    writer.Flush();
}
```

<span data-ttu-id="0bc01-361">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="0bc01-361">The preceding code:</span></span>

* <span data-ttu-id="0bc01-362">JSON 파일을 읽고, `JsonDocument`에 데이터를 로드 하 고, 서식 있는 (예쁜 인쇄) JSON을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-362">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="0bc01-363"><xref:System.Text.Json.JsonDocumentOptions>를 사용 하 여 입력 JSON의 주석이 허용 되지만 무시 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-363">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="0bc01-364">완료 되 면 작성기에서 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-364">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="0bc01-365">또는 삭제 될 때 작성자가 autoflush 수 있도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-365">An alternative is to let the writer autoflush when it's disposed.</span></span> 

<span data-ttu-id="0bc01-366">예제 코드에서 처리할 JSON 입력의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-366">Here's an example of JSON input to be processed by the example code:</span></span>

```json
{"Class Name": "Science","Teacher's Name": "Jane","Semester": "2019-01-01","Students": [{"Name": "John","Grade": 94.3},{"Name": "James","Grade": 81.0},{"Name": "Julia","Grade": 91.9},{"Name": "Jessica","Grade": 72.4},{"Name": "Johnathan"}],"Final": true}
```

<span data-ttu-id="0bc01-367">결과는 다음과 같이 잘 인쇄 된 JSON 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-367">The result is the following pretty-printed JSON output:</span></span>

```json
{
  "Class Name": "Science",
  "Teacher\u0027s Name": "Jane",
  "Semester": "2019-01-01",
  "Students": [
    {
      "Name": "John",
      "Grade": 94.3
    },
    {
      "Name": "James",
      "Grade": 81.0
    },
    {
      "Name": "Julia",
      "Grade": 91.9
    },
    {
      "Name": "Jessica",
      "Grade": 72.4
    },
    {
      "Name": "Johnathan"
    }
  ],
  "Final": true
}
```

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="0bc01-368">Utf8JsonWriter 사용</span><span class="sxs-lookup"><span data-stu-id="0bc01-368">Use Utf8JsonWriter</span></span>

<span data-ttu-id="0bc01-369">다음 예제에서는 <xref:System.Text.Json.Utf8JsonWriter> 클래스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-369">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

```csharp
var options = new JsonWriterOptions
{
    Indented = true
};

using (var stream = new MemoryStream())
{
    using (var writer = new Utf8JsonWriter(stream, options))
    {
        writer.WriteStartObject();
        writer.WriteString("date", DateTimeOffset.UtcNow);
        writer.WriteNumber("temp", 42);
        writer.WriteEndObject();
    }

    string json = Encoding.UTF8.GetString(stream.ToArray());
    Console.WriteLine(json);
}
```

## <a name="use-utf8jsonreader"></a><span data-ttu-id="0bc01-370">Utf8JsonReader 사용</span><span class="sxs-lookup"><span data-stu-id="0bc01-370">Use Utf8JsonReader</span></span>

<span data-ttu-id="0bc01-371">다음 예제에서는 <xref:System.Text.Json.Utf8JsonReader> 클래스를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-371">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

```csharp
var options = new JsonReaderOptions
{
    AllowTrailingCommas = true,
    CommentHandling = JsonCommentHandling.Skip
};
Utf8JsonReader reader = new Utf8JsonReader(jsonUtf8, options);

while (reader.Read())
{
    Console.Write(reader.TokenType);

    switch (reader.TokenType)
    {
        case JsonTokenType.PropertyName:
        case JsonTokenType.String:
            {
                string text = reader.GetString();
                Console.Write(" ");
                Console.Write(text);
                break;
            }

        case JsonTokenType.Number:
            {
                int value = reader.GetInt32();
                Console.Write(" ");
                Console.Write(value);
                break;
            }

            // Other token types elided for brevity
    }

    Console.WriteLine();
}
```

<span data-ttu-id="0bc01-372">위의 코드는 `jsonUtf8` 변수가 u t f-8로 인코딩된 유효한 JSON을 포함 하는 바이트 배열 이라고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-372">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="0bc01-373">Utf8JsonReader를 사용 하 여 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="0bc01-373">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="0bc01-374">다음 예제에서는 파일을 동기적으로 읽고 값을 검색 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-374">The following example shows how to read a file synchronously and search for a value:</span></span>

```csharp
class Program
{
    private static readonly byte[] s_nameUtf8 = Encoding.UTF8.GetBytes("name");
    private static readonly byte[] s_universityUtf8 = Encoding.UTF8.GetBytes("University");

    private static void ReaderFromFileSync(string fileName)
    {
         string jsonString = File.ReadAllText(fileName);
         ReadOnlySpan<byte> jsonReadOnlySpan = Encoding.UTF8.GetBytes(jsonString);

        int count = 0;
        int total = 0;

        var json = new Utf8JsonReader(jsonReadOnlySpan, isFinalBlock: true, state: default);

        while (json.Read())
        {
            JsonTokenType tokenType = json.TokenType;

            switch (tokenType)
            {
                case JsonTokenType.StartObject:
                    total++;
                    break;
                case JsonTokenType.PropertyName:
                    if (json.ValueSpan.SequenceEqual(s_nameUtf8))
                    {
                        bool result = json.Read();

                        Debug.Assert(result);  // Assume valid JSON
                        Debug.Assert(json.TokenType == JsonTokenType.String);   // Assume known, valid JSON schema

                        if (json.ValueSpan.EndsWith(s_universityUtf8))
                        {
                            count++;
                        }
                    }
                    break;
            }
        }
        Console.WriteLine($"{count} out of {total} have names that end with 'University'");
    }
}
```

<span data-ttu-id="0bc01-375">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="0bc01-375">The preceding code:</span></span>

* <span data-ttu-id="0bc01-376">는 파일이 u t f-16으로 인코딩되고 u t f-8로 코드 변환 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-376">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="0bc01-377">U t f-8로 인코딩된 파일은 다음 코드를 사용 하 여 `ReadOnlySpan<byte>`직접 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-377">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName); 
  ```

* <span data-ttu-id="0bc01-378">JSON에 개체 배열이 포함 되어 있다고 가정 하 고 각 개체에 문자열 형식의 "name" 속성이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-378">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="0bc01-379">"대학"으로 끝나는 개체 및 `name` 속성 값을 계산 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-379">Counts objects and `name` property values that end with "University".</span></span>

<span data-ttu-id="0bc01-380">위의 코드에서 읽을 수 있는 JSON 샘플은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-380">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="0bc01-381">결과 요약 메시지는 "2-4 중에서 이름이 ' 대학 '로 끝나는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-381">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

```json
[
  {
    "web_pages": [ "https://contoso.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contoso.edu" ],
    "name": "Contoso Community College"
  },
  {
    "web_pages": [ "http://fabrikam.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikam.edu" ],
    "name": "Fabrikam Community College"
  },
  {
    "web_pages": [ "http://www.contosouniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "contosouniversity.edu" ],
    "name": "Contoso University"
  },
  {
    "web_pages": [ "http://www.fabrikamuniversity.edu/" ],
    "alpha_two_code": "US",
    "state-province": null,
    "country": "United States",
    "domains": [ "fabrikamuniversity.edu" ],
    "name": "Fabrikam University"
  }
]
```

## <a name="additional-resources"></a><span data-ttu-id="0bc01-382">추가 자료</span><span class="sxs-lookup"><span data-stu-id="0bc01-382">Additional resources</span></span>

* [<span data-ttu-id="0bc01-383">System.object 개요</span><span class="sxs-lookup"><span data-stu-id="0bc01-383">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="0bc01-384">System.object API 참조</span><span class="sxs-lookup"><span data-stu-id="0bc01-384">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="0bc01-385">System.object의 사용자 지정 변환기를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="0bc01-385">Write custom converters for System.Text.Json</span></span>](system-text-json-converters-how-to.md)
* [<span data-ttu-id="0bc01-386">System.object의 DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="0bc01-386">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
