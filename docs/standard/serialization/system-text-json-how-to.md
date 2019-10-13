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
ms.openlocfilehash: 22c2fd5fc5eaf7a5dc9b71a7335b0b844fa92b51
ms.sourcegitcommit: 9c3a4f2d3babca8919a1e490a159c1500ba7a844
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/12/2019
ms.locfileid: "72291612"
---
# <a name="how-to-serialize-and-deserialize-json-in-net"></a><span data-ttu-id="87427-102">.NET에서 JSON을 serialize 및 deserialize 하는 방법</span><span class="sxs-lookup"><span data-stu-id="87427-102">How to serialize and deserialize JSON in .NET</span></span>

> [!IMPORTANT]
> <span data-ttu-id="87427-103">JSON serialization 설명서는 생성 중입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-103">The JSON serialization documentation is under construction.</span></span> <span data-ttu-id="87427-104">이 문서에서는 모든 시나리오를 다루지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-104">This article doesn't cover all scenarios.</span></span> <span data-ttu-id="87427-105">자세한 내용은 GitHub의 dotnet/corefx 리포지토리, 특히 [json 기능-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc)에서 발생 하는 system.servicemodel [문제](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) 를 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-105">For more information, examine [System.Text.Json issues](https://github.com/dotnet/corefx/issues?q=is%3Aopen+is%3Aissue+label%3Aarea-System.Text.Json) in the dotnet/corefx repository on GitHub, especially those labeled [json-functionality-doc](https://github.com/dotnet/corefx/labels/json-functionality-doc).</span></span>

<span data-ttu-id="87427-106">이 문서에서는 <xref:System.Text.Json> 네임 스페이스를 사용 하 여 JSON (JavaScript Object Notation)으로 serialize 및 deserialize 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87427-106">This article shows how to use the <xref:System.Text.Json> namespace to serialize and deserialize to and from JavaScript Object Notation (JSON).</span></span> <span data-ttu-id="87427-107">지침 및 샘플 코드는 [ASP.NET Core](/aspnet/core/)와 같은 프레임 워크가 아닌 라이브러리를 직접 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-107">The directions and sample code use the library directly, not through a framework such as [ASP.NET Core](/aspnet/core/).</span></span>

## <a name="namespaces"></a><span data-ttu-id="87427-108">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="87427-108">Namespaces</span></span>

<span data-ttu-id="87427-109">@No__t-0 네임 스페이스는 모든 진입점과 기본 유형을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-109">The <xref:System.Text.Json> namespace contains all the entry points and the main types.</span></span> <span data-ttu-id="87427-110">@No__t-0 네임 스페이스에는 serialization 및 deserialization과 관련 된 고급 시나리오 및 사용자 지정을 위한 특성 및 Api가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-110">The <xref:System.Text.Json.Serialization> namespace contains attributes and APIs for advanced scenarios and customization specific to serialization and deserialization.</span></span> <span data-ttu-id="87427-111">따라서이 문서에 표시 된 코드 예제에는 다음 `using` 지시문 중 하나 또는 둘 다가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-111">Therefore, the code examples shown in this article require one or both of the following `using` directives:</span></span>

```csharp
using System.Text.Json;
using System.Text.Json.Serialization;
```

<span data-ttu-id="87427-112">@No__t-0 네임 스페이스의 특성은 현재 `System.Text.Json`에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-112">Attributes from the <xref:System.Runtime.Serialization> namespace aren't currently supported in `System.Text.Json`.</span></span>

## <a name="how-to-write-net-objects-to-json-serialize"></a><span data-ttu-id="87427-113">JSON에 .NET 개체를 작성 하는 방법 (직렬화)</span><span class="sxs-lookup"><span data-stu-id="87427-113">How to write .NET objects to JSON (serialize)</span></span>

<span data-ttu-id="87427-114">JSON을 문자열에 쓰려면 <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-114">To write JSON to a string, call the <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="87427-115">다음 예제에서는 제네릭 형식 매개 변수를 포함 하는 오버 로드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-115">The following example uses an overload with a generic type parameter:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="87427-116">제네릭 형식 매개 변수를 생략 하 고 제네릭 형식 유추를 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-116">You can omit the generic type parameter and use generic type inference instead:</span></span>

```csharp
WeatherForecast weatherForecast;
//...
string json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="87427-117">다음은 컬렉션 및 중첩 클래스를 포함 하는 serialize 되는 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-117">Here's an example type to be serialized, which contains collections and nested classes:</span></span>

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

<span data-ttu-id="87427-118">JSON 출력은 기본적으로 축소 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-118">The JSON output is minified by default:</span></span> 

```json
{"Date":"2019-08-01T00:00:00-07:00","TemperatureC":25,"Summary":"Hot","DatesAvailable":["2019-08-01T00:00:00-07:00","2019-08-02T00:00:00-07:00"],"TemperatureRanges":{"Cold":{"High":{"DegreesCelsius":20},"Low":{"DegreesCelsius":-10}},"Hot":{"High":{"DegreesCelsius":60},"Low":{"DegreesCelsius":20}}},"SummaryWords":["Cool","Windy","Humid"]}
```

<span data-ttu-id="87427-119">다음 예제에서는 동일한 JSON (공백 및 들여쓰기를 사용 하 여 잘 인쇄 됨)을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87427-119">The following example shows the same JSON, formatted (that is, pretty-printed with whitespace and indentation):</span></span>

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

<span data-ttu-id="87427-120">@No__t-0의 오버 로드를 사용 하면 <xref:System.IO.Stream>로 serialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-120">Overloads of <xref:System.Text.Json.JsonSerializer.Serialize%2A> let you serialize to a <xref:System.IO.Stream>.</span></span> <span data-ttu-id="87427-121">비동기 버전의 `Stream` 오버 로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-121">Async versions of the `Stream` overloads are available.</span></span>

### <a name="serialize-to-utf-8"></a><span data-ttu-id="87427-122">U t f-8로 직렬화</span><span class="sxs-lookup"><span data-stu-id="87427-122">Serialize to UTF-8</span></span>

<span data-ttu-id="87427-123">U t f-8로 serialize 하려면 <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-123">To serialize to UTF-8, call the <xref:System.Text.Json.JsonSerializer.SerializeToUtf8Bytes%2A?displayProperty=nameWithType> method:</span></span>

```csharp
byte[] utf8Json = JsonSerializer.SerializeToUtf8Bytes<WeatherForecast>(weatherForecast);
```

<span data-ttu-id="87427-124">또는 <xref:System.Text.Json.Utf8JsonWriter>을 사용 하는 @no__t 0 오버 로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-124">As an alternative, a <xref:System.Text.Json.JsonSerializer.Serialize%2A> overload that takes a <xref:System.Text.Json.Utf8JsonWriter> is available.</span></span>

<span data-ttu-id="87427-125">U t f-8로 serialize 하는 것은 문자열 기반 메서드를 사용 하는 것 보다 약 5-10% 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="87427-125">Serializing to UTF-8 is about 5-10% faster than using the string-based methods.</span></span> <span data-ttu-id="87427-126">차이점은 바이트 (u t f-8)를 문자열 (UTF-16)로 변환할 필요가 없기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-126">The difference is because the bytes (as UTF-8) don't need to be converted to strings (UTF-16).</span></span>

## <a name="serialization-behavior"></a><span data-ttu-id="87427-127">Serialization 동작</span><span class="sxs-lookup"><span data-stu-id="87427-127">Serialization behavior</span></span>

* <span data-ttu-id="87427-128">기본적으로 모든 public 속성이 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-128">By default, all public properties are serialized.</span></span> <span data-ttu-id="87427-129">[제외할 속성을 지정할](#exclude-properties)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-129">You can [specify properties to exclude](#exclude-properties).</span></span>
* <span data-ttu-id="87427-130">[기본 인코더](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) 는 ascii가 아닌 문자, ascii 범위 내의 HTML 구분 문자 및 [JSON 사양](https://tools.ietf.org/html/rfc8259#section-7)에 따라 이스케이프 되어야 하는 문자를 이스케이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-130">The [default encoder](xref:System.Text.Encodings.Web.JavaScriptEncoder.Default) escapes non-ASCII characters, HTML-sensitive characters within the ASCII-range, and characters that must be escaped according to [the JSON spec](https://tools.ietf.org/html/rfc8259#section-7).</span></span>
* <span data-ttu-id="87427-131">기본적으로 JSON은 축소 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-131">By default, JSON is minified.</span></span> <span data-ttu-id="87427-132">[JSON을 잘 인쇄할](#serialize-to-formatted-json)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-132">You can [pretty-print the JSON](#serialize-to-formatted-json).</span></span>
* <span data-ttu-id="87427-133">기본적으로 JSON 이름의 대/소문자는 .NET 이름과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-133">By default, casing of JSON names matches the .NET names.</span></span> <span data-ttu-id="87427-134">[JSON 이름 대/소문자를 사용자 지정할](#customize-json-names)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-134">You can [customize JSON name casing](#customize-json-names).</span></span>
* <span data-ttu-id="87427-135">순환 참조가 감지 되 고 예외가 throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-135">Circular references are detected and exceptions thrown.</span></span> <span data-ttu-id="87427-136">자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [순환 참조에 대 한 문제](https://github.com/dotnet/corefx/issues/38579) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87427-136">For more information, see the [issue on circular references](https://github.com/dotnet/corefx/issues/38579) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="87427-137">현재는 필드가 제외 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-137">Currently, fields are excluded.</span></span>

<span data-ttu-id="87427-138">지원 되는 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-138">Supported types include:</span></span>

* <span data-ttu-id="87427-139">숫자 형식, 문자열, 부울 등 JavaScript 기본 형식에 매핑되는 .NET 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-139">.NET primitives that map to JavaScript primitives, such as numeric types, strings, and Boolean.</span></span>
* <span data-ttu-id="87427-140">사용자 정의 [일반 이전 CLR 개체 (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span><span class="sxs-lookup"><span data-stu-id="87427-140">User-defined [Plain Old CLR Objects (POCOs)](https://stackoverflow.com/questions/250001/poco-definition).</span></span>
* <span data-ttu-id="87427-141">1 차원 및 가변 배열 (`ArrayName[][]`)</span><span class="sxs-lookup"><span data-stu-id="87427-141">One-dimensional and jagged arrays (`ArrayName[][]`).</span></span>
* <span data-ttu-id="87427-142">`TValue` @no__t `object`, `JsonElement` 또는 POCO입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-142">`Dictionary<string,TValue>` where `TValue` is `object`, `JsonElement`, or a POCO.</span></span>
* <span data-ttu-id="87427-143">다음 네임 스페이스의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-143">Collections from the following namespaces.</span></span> <span data-ttu-id="87427-144">자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [컬렉션 지원에 대 한 문제](https://github.com/dotnet/corefx/issues/36643) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87427-144">For more information, see the [issue on collection support](https://github.com/dotnet/corefx/issues/36643) in the dotnet/corefx repository on GitHub.</span></span>
  * <xref:System.Collections>
  * <xref:System.Collections.Generic>
  * <xref:System.Collections.Immutable>

## <a name="how-to-read-json-into-net-objects-deserialize"></a><span data-ttu-id="87427-145">JSON을 .NET 개체로 읽는 방법 (deserialize)</span><span class="sxs-lookup"><span data-stu-id="87427-145">How to read JSON into .NET objects (deserialize)</span></span>

<span data-ttu-id="87427-146">문자열에서 deserialize 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-146">To deserialize from a string, call the <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method, as shown in the following example:</span></span>

```csharp
string json = ... ;

var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json);
```

<span data-ttu-id="87427-147">예제는 [직렬화](#how-to-write-net-objects-to-json-serialize) 섹션을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87427-147">For an example, see the [serialize](#how-to-write-net-objects-to-json-serialize) section.</span></span> <span data-ttu-id="87427-148">JSON 및 .NET 개체는 동일 하지만 방향이 반대입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-148">The JSON and .NET object are the same, but the direction is reversed.</span></span>

<span data-ttu-id="87427-149">@No__t-0의 오버 로드를 사용 하면 `Stream`에서 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-149">Overloads of <xref:System.Text.Json.JsonSerializer.Deserialize*> let you deserialize from a `Stream`.</span></span>  <span data-ttu-id="87427-150">비동기 버전의 `Stream` 오버 로드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-150">Async versions of the `Stream` overloads are available.</span></span>

### <a name="deserialize-from-utf-8"></a><span data-ttu-id="87427-151">U t f-8에서 Deserialize</span><span class="sxs-lookup"><span data-stu-id="87427-151">Deserialize from UTF-8</span></span>

<span data-ttu-id="87427-152">U t f-8에서 deserialize 하려면 다음 예제와 같이 `Utf8JsonReader` 또는 `ReadOnlySpan<byte>`를 사용 하는 <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 오버 로드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-152">To deserialize from UTF-8, call a <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> overload that takes a `Utf8JsonReader` or a `ReadOnlySpan<byte>`, as shown in the following examples:</span></span>

```csharp
byte[] utf8Json;
//...
var readOnlySpan = new ReadOnlySpan<byte>(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(readOnlySpan);
```

```csharp
byte[] utf8Json;
//...
var utf8Reader = new Utf8JsonReader(utf8Json);
weatherForecast = JsonSerializer.Deserialize<WeatherForecastMin>(ref utf8Reader);
```

## <a name="deserialization-behavior"></a><span data-ttu-id="87427-153">Deserialization 동작</span><span class="sxs-lookup"><span data-stu-id="87427-153">Deserialization behavior</span></span>

* <span data-ttu-id="87427-154">기본적으로 속성 이름 일치는 대/소문자를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-154">By default, property name matching is case-sensitive.</span></span> <span data-ttu-id="87427-155">[대/소문자](#case-insensitive-property-matching)를 구분 하지 않도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-155">You can [specify case-insensitivity](#case-insensitive-property-matching).</span></span>
* <span data-ttu-id="87427-156">JSON에 읽기 전용 속성에 대 한 값이 포함 된 경우에는이 값이 무시 되 고 예외가 throw 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-156">If the JSON contains a value for a read-only property, the value is ignored and no exception is thrown.</span></span>
* <span data-ttu-id="87427-157">매개 변수가 없는 생성자가 없는 참조 형식으로의 Deserialization은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-157">Deserialization to reference types without a parameterless constructor isn't supported.</span></span>
* <span data-ttu-id="87427-158">변경할 수 없는 개체 또는 읽기 전용 속성에 대 한 Deserialization은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-158">Deserialization to immutable objects or read-only properties isn't supported.</span></span> <span data-ttu-id="87427-159">자세한 내용은 github의 dotnet/corefx 리포지토리에서 [변경 불가능 한 개체 지원](https://github.com/dotnet/corefx/issues/38569) 및 [읽기 전용 속성 지원 문제](https://github.com/dotnet/corefx/issues/38163) 에 대 한 github 문제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87427-159">For more information, see the GitHub [issue on immutable object support](https://github.com/dotnet/corefx/issues/38569) and the [issue on read-only property support](https://github.com/dotnet/corefx/issues/38163) in the dotnet/corefx repository on GitHub.</span></span>
* <span data-ttu-id="87427-160">기본적으로 열거형은 숫자로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-160">By default, enums are supported as numbers.</span></span>
* <span data-ttu-id="87427-161">필드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-161">Fields aren't supported.</span></span>
* <span data-ttu-id="87427-162">기본적으로 JSON의 주석이 나 후행 쉼표는 예외를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-162">By default, comments or trailing commas in the JSON throw exceptions.</span></span> <span data-ttu-id="87427-163">필요한 경우 [주석과 후행 쉼표를 허용할](#allow-comments-and-trailing-commas) 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-163">You can [allow comments and trailing commas](#allow-comments-and-trailing-commas) if needed.</span></span>
* <span data-ttu-id="87427-164">[기본 최대 깊이](xref:System.Text.Json.JsonReaderOptions.MaxDepth) 는 64입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-164">The [default maximum depth](xref:System.Text.Json.JsonReaderOptions.MaxDepth) is 64.</span></span>

## <a name="serialize-to-formatted-json"></a><span data-ttu-id="87427-165">형식이 지정 된 JSON으로 직렬화</span><span class="sxs-lookup"><span data-stu-id="87427-165">Serialize to formatted JSON</span></span>

<span data-ttu-id="87427-166">JSON 출력을 잘 인쇄 하려면 <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType>을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-166">To pretty-print the JSON output, set <xref:System.Text.Json.JsonSerializerOptions.WriteIndented?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    WriteIndented = true,
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="87427-167">직렬화 및 JSON 출력의 예제 유형은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-167">Here's an example type to be serialized and JSON output:</span></span>

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

## <a name="allow-comments-and-trailing-commas"></a><span data-ttu-id="87427-168">주석과 후행 쉼표 허용</span><span class="sxs-lookup"><span data-stu-id="87427-168">Allow comments and trailing commas</span></span>

<span data-ttu-id="87427-169">JSON에서는 기본적으로 주석과 후행 쉼표를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-169">By default comments and trailing commas are not allowed in JSON.</span></span> <span data-ttu-id="87427-170">JSON에서 주석을 허용 하려면 <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> 속성을 `JsonCommentHandling.Skip`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-170">To allow comments in the JSON, set the <xref:System.Text.Json.JsonSerializerOptions.ReadCommentHandling?displayProperty=nameWithType> property to `JsonCommentHandling.Skip`.</span></span> <span data-ttu-id="87427-171">후행 쉼표를 허용 하려면 <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-171">And to allow trailing commas, set the <xref:System.Text.Json.JsonSerializerOptions.AllowTrailingCommas?displayProperty=nameWithType> property to `true`.</span></span> <span data-ttu-id="87427-172">다음 예제에서는 두 가지를 모두 허용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87427-172">The following example shows how to allow both:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    ReadCommentHandling = JsonCommentHandling.Skip,
    AllowTrailingCommas = true
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(json, options);
```

<span data-ttu-id="87427-173">다음은 주석과 후행 쉼표를 사용 하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-173">Here's example JSON with comments and a trailing comma:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25, // Fahrenheit 77
  "Summary": "Hot", /* Zharko */
}
```

## <a name="customize-json-names"></a><span data-ttu-id="87427-174">JSON 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="87427-174">Customize JSON names</span></span>

<span data-ttu-id="87427-175">기본적으로 속성 이름 및 사전 키는 대/소문자를 포함 하 여 JSON 출력에서 변경 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-175">By default, property names and dictionary keys are unchanged in the JSON output, including case.</span></span> <span data-ttu-id="87427-176">이 섹션에서는 다음을 수행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-176">This section explains how to:</span></span>

* <span data-ttu-id="87427-177">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="87427-177">Customize individual property names</span></span>
* <span data-ttu-id="87427-178">모든 속성 이름을 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="87427-178">Convert all property names to camel case</span></span>
* <span data-ttu-id="87427-179">사용자 지정 속성 명명 정책 구현</span><span class="sxs-lookup"><span data-stu-id="87427-179">Implement a custom property naming policy</span></span>
* <span data-ttu-id="87427-180">사전 키를 카멜식 대/소문자로 변환</span><span class="sxs-lookup"><span data-stu-id="87427-180">Convert dictionary keys to camel case</span></span>

<span data-ttu-id="87427-181">현재는 열거형을 카멜식 대/소문자로 자동 변환 하는 기능이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-181">Currently, there's no support for automatically converting enums to camel case.</span></span> <span data-ttu-id="87427-182">자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [카멜식 대/소문자 지원 열거 문제](https://github.com/dotnet/corefx/issues/37725) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87427-182">For more information, see the [issue on enum camel case support](https://github.com/dotnet/corefx/issues/37725) in the dotnet/corefx repository on GitHub.</span></span>

### <a name="customize-individual-property-names"></a><span data-ttu-id="87427-183">개별 속성 이름 사용자 지정</span><span class="sxs-lookup"><span data-stu-id="87427-183">Customize individual property names</span></span>

<span data-ttu-id="87427-184">개별 속성의 이름을 설정 하려면 [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-184">To set the name of individual properties, use the [[JsonPropertyName]](xref:System.Text.Json.Serialization.JsonPropertyNameAttribute) attribute.</span></span>

<span data-ttu-id="87427-185">직렬화 및 결과 JSON의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-185">Here's an example type to serialize and resulting JSON:</span></span>

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

<span data-ttu-id="87427-186">이 특성에 의해 설정 된 속성 이름:</span><span class="sxs-lookup"><span data-stu-id="87427-186">The property name set by this attribute:</span></span>

* <span data-ttu-id="87427-187">Serialization 및 deserialization을 위해 양방향으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-187">Applies in both directions, for serialization and deserialization.</span></span>
* <span data-ttu-id="87427-188">속성 명명 정책 보다 우선 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-188">Takes precedence over property naming policies.</span></span>

### <a name="use-camel-case-for-all-json-property-names"></a><span data-ttu-id="87427-189">모든 JSON 속성 이름에 카멜식 대/소문자 사용</span><span class="sxs-lookup"><span data-stu-id="87427-189">Use camel case for all JSON property names</span></span>

<span data-ttu-id="87427-190">모든 JSON 속성 이름에 카멜식 대/소문자를 사용 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType>을 `JsonNamingPolicy.CamelCase`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-190">To use camel case for all JSON property names, set <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="87427-191">직렬화 및 JSON 출력에 대 한 예제 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-191">Here's an example class to serialize and JSON output:</span></span>

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
  "date": "2019-08-01T00:00:00-07:00",
  "temperatureC": 25,
  "summary": "Hot",
  "Wind": 35
}
```

<span data-ttu-id="87427-192">카멜식 대/소문자 속성 명명 정책:</span><span class="sxs-lookup"><span data-stu-id="87427-192">The camel case property naming policy:</span></span>

* <span data-ttu-id="87427-193">Serialization 및 deserialization에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-193">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="87427-194">@No__t-0 특성에 의해 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-194">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="use-a-custom-json-property-naming-policy"></a><span data-ttu-id="87427-195">사용자 지정 JSON 속성 명명 정책 사용</span><span class="sxs-lookup"><span data-stu-id="87427-195">Use a custom JSON property naming policy</span></span>

<span data-ttu-id="87427-196">사용자 지정 JSON 속성 명명 정책을 사용 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonNamingPolicy>에서 파생 되는 클래스를 만들고 <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> 메서드를 재정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-196">To use a custom JSON property naming policy, create a class that derives from <xref:System.Text.Json.JsonNamingPolicy> and override the <xref:System.Text.Json.JsonNamingPolicy.ConvertName%2A> method, as shown in the following example:</span></span>

```csharp
class UpperCaseNamingPolicy : JsonNamingPolicy
{
    public override string ConvertName(string name)
    {
        return name.ToUpper();
    }
}
```

<span data-ttu-id="87427-197">그런 다음 <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> 속성을 명명 정책 클래스의 인스턴스로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-197">Then set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNamingPolicy?displayProperty=nameWithType> property to an instance of your naming policy class:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNamingPolicy = new UpperCaseNamingPolicy()
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="87427-198">직렬화 및 JSON 출력에 대 한 예제 클래스는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-198">Here's an example class to serialize and JSON output:</span></span>

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

<span data-ttu-id="87427-199">JSON 속성 명명 정책:</span><span class="sxs-lookup"><span data-stu-id="87427-199">The JSON property naming policy:</span></span>

* <span data-ttu-id="87427-200">Serialization 및 deserialization에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-200">Applies to serialization and deserialization.</span></span>
* <span data-ttu-id="87427-201">@No__t-0 특성에 의해 재정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-201">Is overridden by `[JsonPropertyName]` attributes.</span></span>

### <a name="camel-case-dictionary-keys"></a><span data-ttu-id="87427-202">카멜식 대/소문자 사전 키</span><span class="sxs-lookup"><span data-stu-id="87427-202">Camel case dictionary keys</span></span>

<span data-ttu-id="87427-203">Serialize 할 개체의 속성 형식이 `Dictionary<string,TValue>` 인 경우 `string` 키를 카멜식 대/소문자로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-203">If a property of an object to be serialized is of type `Dictionary<string,TValue>`, the `string` keys can be converted to camel case.</span></span> <span data-ttu-id="87427-204">이렇게 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy>을 `JsonNamingPolicy.CamelCase`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-204">To do that, set <xref:System.Text.Json.JsonSerializerOptions.DictionaryKeyPolicy> to `JsonNamingPolicy.CamelCase`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    DictionaryKeyPolicy = JsonNamingPolicy.CamelCase
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="87427-205">직렬화 및 JSON 출력에 대 한 예제 개체는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-205">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="87427-206">속성</span><span class="sxs-lookup"><span data-stu-id="87427-206">Property</span></span> |<span data-ttu-id="87427-207">값</span><span class="sxs-lookup"><span data-stu-id="87427-207">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="87427-208">Date</span><span class="sxs-lookup"><span data-stu-id="87427-208">Date</span></span>    | <span data-ttu-id="87427-209">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="87427-209">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="87427-210">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="87427-210">TemperatureC</span></span>| <span data-ttu-id="87427-211">25</span><span class="sxs-lookup"><span data-stu-id="87427-211">25</span></span> |
| <span data-ttu-id="87427-212">요약</span><span class="sxs-lookup"><span data-stu-id="87427-212">Summary</span></span>| <span data-ttu-id="87427-213">핫스폿을</span><span class="sxs-lookup"><span data-stu-id="87427-213">Hot</span></span>|
| <span data-ttu-id="87427-214">TemperatureRanges</span><span class="sxs-lookup"><span data-stu-id="87427-214">TemperatureRanges</span></span> | <span data-ttu-id="87427-215">콜드, 20</span><span class="sxs-lookup"><span data-stu-id="87427-215">Cold, 20</span></span><br><span data-ttu-id="87427-216">핫, 40</span><span class="sxs-lookup"><span data-stu-id="87427-216">Hot, 40</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "TemperatureRanges": {
    "cold": 20,
    "hot": 40
  }
}
```

<span data-ttu-id="87427-217">카멜식 대/소문자 명명 정책은 serialization에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-217">The camel case naming policy applies to serialization only.</span></span>

## <a name="exclude-properties"></a><span data-ttu-id="87427-218">제외 속성</span><span class="sxs-lookup"><span data-stu-id="87427-218">Exclude properties</span></span>

<span data-ttu-id="87427-219">기본적으로 모든 public 속성이 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-219">By default, all public properties are serialized.</span></span> <span data-ttu-id="87427-220">JSON 출력에 표시 하지 않으려는 경우 몇 가지 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-220">If you don't want some of them to appear in the JSON output, you have several options.</span></span> <span data-ttu-id="87427-221">이 섹션에서는 다음을 제외 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-221">This section explains how to exclude:</span></span>

* <span data-ttu-id="87427-222">개별 속성</span><span class="sxs-lookup"><span data-stu-id="87427-222">Individual properties</span></span>
* <span data-ttu-id="87427-223">모든 읽기 전용 속성</span><span class="sxs-lookup"><span data-stu-id="87427-223">All read-only properties</span></span>
* <span data-ttu-id="87427-224">모든 null 값 속성</span><span class="sxs-lookup"><span data-stu-id="87427-224">All null-value properties</span></span> 

### <a name="exclude-individual-properties"></a><span data-ttu-id="87427-225">개별 속성 제외</span><span class="sxs-lookup"><span data-stu-id="87427-225">Exclude individual properties</span></span>

<span data-ttu-id="87427-226">개별 속성을 무시 하려면 [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) 특성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-226">To ignore individual properties, use the [[JsonIgnore]](xref:System.Text.Json.Serialization.JsonIgnoreAttribute) attribute.</span></span>

<span data-ttu-id="87427-227">다음은 serialize 및 JSON 출력에 대 한 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-227">Here's an example type to serialize and JSON output:</span></span>

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

### <a name="exclude-all-read-only-properties"></a><span data-ttu-id="87427-228">모든 읽기 전용 속성을 제외 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-228">Exclude all read-only properties</span></span>

<span data-ttu-id="87427-229">모든 읽기 전용 속성을 제외 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType>을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-229">To exclude all read-only properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreReadOnlyProperties?displayProperty=nameWithType> to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreReadOnlyProperties = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="87427-230">다음은 serialize 및 JSON 출력에 대 한 예제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-230">Here's an example type to serialize and JSON output:</span></span>

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

<span data-ttu-id="87427-231">이 옵션은 serialization에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-231">This option applies only to serialization.</span></span> <span data-ttu-id="87427-232">Deserialization을 수행 하는 동안 읽기 전용 속성은 기본적으로 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-232">During deserialization, read-only properties are ignored by default.</span></span> <span data-ttu-id="87427-233">공용 setter가 아닌 공용 getter가 포함 된 속성은 읽기 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="87427-233">A property is read-only if it contains a public getter but not a public setter.</span></span>

### <a name="exclude-all-null-value-properties"></a><span data-ttu-id="87427-234">모든 null 값 속성 제외</span><span class="sxs-lookup"><span data-stu-id="87427-234">Exclude all null value properties</span></span>

<span data-ttu-id="87427-235">모든 null 값 속성을 제외 하려면 다음 예제와 같이 <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> 속성을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-235">To exclude all null value properties, set the <xref:System.Text.Json.JsonSerializerOptions.IgnoreNullValues> property to `true`, as shown in the following example:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    IgnoreNullValues = true
};
json = JsonSerializer.Serialize(weatherForecast, options);
```

<span data-ttu-id="87427-236">직렬화 및 JSON 출력에 대 한 예제 개체는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-236">Here's an example object to serialize and JSON output:</span></span>

|<span data-ttu-id="87427-237">속성</span><span class="sxs-lookup"><span data-stu-id="87427-237">Property</span></span> |<span data-ttu-id="87427-238">값</span><span class="sxs-lookup"><span data-stu-id="87427-238">Value</span></span>  |
|---------|---------|
| <span data-ttu-id="87427-239">Date</span><span class="sxs-lookup"><span data-stu-id="87427-239">Date</span></span>    | <span data-ttu-id="87427-240">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="87427-240">8/1/2019 12:00:00 AM -07:00</span></span>|
| <span data-ttu-id="87427-241">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="87427-241">TemperatureC</span></span>| <span data-ttu-id="87427-242">25</span><span class="sxs-lookup"><span data-stu-id="87427-242">25</span></span> |
| <span data-ttu-id="87427-243">요약</span><span class="sxs-lookup"><span data-stu-id="87427-243">Summary</span></span>| <span data-ttu-id="87427-244">null</span><span class="sxs-lookup"><span data-stu-id="87427-244">null</span></span>|

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25
}
```

<span data-ttu-id="87427-245">이 설정은 serialization 및 deserialization에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-245">This setting applies to serialization and deserialization.</span></span> <span data-ttu-id="87427-246">Deserialization을 수행 하는 동안 JSON의 null 값은 유효한 경우에만 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-246">During deserialization, null values in the JSON are ignored only if they are valid.</span></span> <span data-ttu-id="87427-247">Null을 허용 하지 않는 값 형식에 대 한 Null 값은 예외를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="87427-247">Null values for non-nullable value types cause exceptions.</span></span> <span data-ttu-id="87427-248">자세한 내용은 GitHub의 dotnet/corefx 리포지토리에서 [nullable이 아닌 값 형식에 대 한 문제](https://github.com/dotnet/corefx/issues/40922) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="87427-248">For more information, see the [issue on non-nullable value types](https://github.com/dotnet/corefx/issues/40922) in the dotnet/corefx repository on GitHub.</span></span>

## <a name="case-insensitive-property-matching"></a><span data-ttu-id="87427-249">대/소문자를 구분 하지 않는 속성 일치</span><span class="sxs-lookup"><span data-stu-id="87427-249">Case-insensitive property matching</span></span>

<span data-ttu-id="87427-250">기본적으로 deserialization은 JSON과 대상 개체 속성 간에 일치 하는 대/소문자를 구분 하는 속성 이름을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-250">By default, deserialization looks for case-sensitive property name matches between JSON and the target object properties.</span></span> <span data-ttu-id="87427-251">이 동작을 변경 하려면 <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType>을 `true`로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-251">To change that behavior, set the <xref:System.Text.Json.JsonSerializerOptions.PropertyNameCaseInsensitive?displayProperty=nameWithType> to `true`:</span></span>

```csharp
var options = new JsonSerializerOptions
{
    PropertyNameCaseInsensitive = true,
};
var weatherForecast = JsonSerializer.Deserialize<WeatherForecast>(weatherForecast, options);
```

<span data-ttu-id="87427-252">카멜식 대/소문자 속성 이름을 사용 하는 JSON 예제는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-252">Here's example JSON with camel case property names.</span></span> <span data-ttu-id="87427-253">파스칼식 대/소문자 속성 이름을 포함 하는 다음 형식으로 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-253">It can be deserialized into the following type that has Pascal case property names.</span></span>

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

## <a name="include-properties-of-derived-classes"></a><span data-ttu-id="87427-254">파생 클래스의 속성 포함</span><span class="sxs-lookup"><span data-stu-id="87427-254">Include properties of derived classes</span></span>

<span data-ttu-id="87427-255">컴파일 시간에 serialize 할 형식을 지정 하는 경우 다형성 serialization이 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-255">Polymorphic serialization isn't supported when you specify at compile time the type to be serialized.</span></span> <span data-ttu-id="87427-256">예를 들어 `WeatherForecast` 클래스와 파생 클래스 `WeatherForecastWithWind` 인 경우를 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-256">For example, suppose you have a `WeatherForecast` class and a derived class `WeatherForecastWithWind`:</span></span>

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

<span data-ttu-id="87427-257">컴파일 시간에 `Serialize` 메서드를 통해 전달 되거나 유추 된 형식이 `WeatherForecast` 인 경우</span><span class="sxs-lookup"><span data-stu-id="87427-257">And suppose the type passed to, or inferred by, the `Serialize` method at compile time is `WeatherForecast`:</span></span>

```csharp
string json = JsonSerializer.Serialize<WeatherForecast>(weatherForecast);
```

```csharp
WeatherForecast weatherForecast;
//...
json = JsonSerializer.Serialize(weatherForecast);
```

<span data-ttu-id="87427-258">이 시나리오에서는 `weatherForecast` 개체가 실제로 `WeatherForecastWithWind` 개체인 경우에도 `WindSpeed` 속성이 serialize 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-258">In this scenario, the `WindSpeed` property is not serialized even if the `weatherForecast` object is actually a `WeatherForecastWithWind` object.</span></span> <span data-ttu-id="87427-259">기본 클래스 속성만 직렬화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-259">Only the base class properties are serialized:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot"
}
```

<span data-ttu-id="87427-260">이 동작은 파생 된 런타임 생성 형식에서 실수로 데이터가 노출 되는 것을 방지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-260">This behavior is intended to help prevent accidental exposure of data in a derived runtime-created type.</span></span>

<span data-ttu-id="87427-261">파생 형식의 속성을 serialize 하려면 다음 방법 중 하나를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-261">To serialize the properties of the derived type, use one of the following approaches:</span></span>

* <span data-ttu-id="87427-262">런타임에 형식을 지정할 수 있는 <xref:System.Text.Json.JsonSerializer.Serialize%2A>의 오버 로드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-262">Call an overload of <xref:System.Text.Json.JsonSerializer.Serialize%2A> that lets you specify the type at runtime:</span></span>

  ```csharp
  json = JsonSerializer.Serialize(weatherForecast, weatherForecast.GetType());
  ```

* <span data-ttu-id="87427-263">@No__t-0으로 serialize 될 개체를 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-263">Declare the object to be serialized as `object`.</span></span>

  ```csharp
  json = JsonSerializer.Serialize<object>(weatherForecast);
  ```

<span data-ttu-id="87427-264">위의 예제 시나리오에서 두 가지 방법 모두 `WindSpeed` 속성이 JSON 출력에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-264">In the preceding example scenario, both approaches cause the `WindSpeed` property to be included in the JSON output:</span></span>

```json
{
  "Date": "2019-08-01T00:00:00-07:00",
  "TemperatureC": 25,
  "Summary": "Hot",
  "WindSpeed": 35
}
```

## <a name="handle-overflow-json"></a><span data-ttu-id="87427-265">오버플로 JSON 처리</span><span class="sxs-lookup"><span data-stu-id="87427-265">Handle overflow JSON</span></span>

<span data-ttu-id="87427-266">Deserialize 하는 동안 대상 형식의 속성으로 표시 되지 않는 데이터를 JSON에 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-266">While deserializing, you might receive data in the JSON that is not represented by properties of the target type.</span></span> <span data-ttu-id="87427-267">예를 들어 대상 형식이 다음과 같다고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-267">For example, suppose your target type is this:</span></span>

```csharp
class WeatherForecast
{
    public DateTimeOffset Date { get; set; }
    public int TemperatureC { get; set; }
    public string Summary { get; set; }
}
```

<span data-ttu-id="87427-268">Deserialize 할 JSON은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-268">And the JSON to be deserialized is this:</span></span>

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

<span data-ttu-id="87427-269">표시 된 형식에 표시 된 JSON을 deserialize 하는 경우 `DatesAvailable` 및 `SummaryWords` 속성은 이동 하지 않으며 손실 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-269">If you deserialize the JSON shown into the type shown, the `DatesAvailable` and `SummaryWords` properties have nowhere to go and are lost.</span></span> <span data-ttu-id="87427-270">이러한 속성과 같은 추가 데이터를 캡처하려면 [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) 특성을 `Dictionary<string,object>` 또는 `Dictionary<string,JsonElement>` 형식의 속성에 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-270">To capture extra data such as these properties, apply the [JsonExtensionData](xref:System.Text.Json.Serialization.JsonExtensionDataAttribute) attribute to a property of type `Dictionary<string,object>` or `Dictionary<string,JsonElement>`:</span></span>

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

<span data-ttu-id="87427-271">앞에서 설명한 JSON을이 샘플 형식으로 deserialize 하는 경우 추가 데이터는 `ExtensionData` 속성의 키-값 쌍이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-271">When you deserialize the JSON shown earlier into this sample type, the extra data becomes key-value pairs of the `ExtensionData` property:</span></span>

|<span data-ttu-id="87427-272">속성</span><span class="sxs-lookup"><span data-stu-id="87427-272">Property</span></span> |<span data-ttu-id="87427-273">값</span><span class="sxs-lookup"><span data-stu-id="87427-273">Value</span></span>  |<span data-ttu-id="87427-274">참고</span><span class="sxs-lookup"><span data-stu-id="87427-274">Notes</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="87427-275">Date</span><span class="sxs-lookup"><span data-stu-id="87427-275">Date</span></span>    | <span data-ttu-id="87427-276">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="87427-276">8/1/2019 12:00:00 AM -07:00</span></span>||
| <span data-ttu-id="87427-277">TemperatureC</span><span class="sxs-lookup"><span data-stu-id="87427-277">TemperatureC</span></span>| <span data-ttu-id="87427-278">0</span><span class="sxs-lookup"><span data-stu-id="87427-278">0</span></span> | <span data-ttu-id="87427-279">대/소문자를 구분 하는 불일치 (JSON의 `temperatureC`). 따라서 속성은 설정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-279">Case-sensitive mismatch (`temperatureC` in the JSON), so the property isn't set.</span></span> |
| <span data-ttu-id="87427-280">요약</span><span class="sxs-lookup"><span data-stu-id="87427-280">Summary</span></span> | <span data-ttu-id="87427-281">핫스폿을</span><span class="sxs-lookup"><span data-stu-id="87427-281">Hot</span></span> ||
| <span data-ttu-id="87427-282">ExtensionData</span><span class="sxs-lookup"><span data-stu-id="87427-282">ExtensionData</span></span> | <span data-ttu-id="87427-283">temperatureC: 25</span><span class="sxs-lookup"><span data-stu-id="87427-283">temperatureC: 25</span></span> |<span data-ttu-id="87427-284">Case가 일치 하지 않기 때문에이 JSON 속성은 추가 이며 사전에서 키-값 쌍이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-284">Since the case didn't match, this JSON property is an extra and becomes a key-value pair in the dictionary.</span></span>|
|| <span data-ttu-id="87427-285">DatesAvailable:</span><span class="sxs-lookup"><span data-stu-id="87427-285">DatesAvailable:</span></span><br>  <span data-ttu-id="87427-286">오전 8/1/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="87427-286">8/1/2019 12:00:00 AM -07:00</span></span><br><span data-ttu-id="87427-287">오전 8/2/2019 12:00:00-07:00</span><span class="sxs-lookup"><span data-stu-id="87427-287">8/2/2019 12:00:00 AM -07:00</span></span> |<span data-ttu-id="87427-288">JSON의 추가 속성은 키-값 쌍이 되며 배열은 값 개체로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-288">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|
| |<span data-ttu-id="87427-289">요약 단어:</span><span class="sxs-lookup"><span data-stu-id="87427-289">SummaryWords:</span></span><br><span data-ttu-id="87427-290">표</span><span class="sxs-lookup"><span data-stu-id="87427-290">Cool</span></span><br><span data-ttu-id="87427-291">바람</span><span class="sxs-lookup"><span data-stu-id="87427-291">Windy</span></span><br><span data-ttu-id="87427-292">Humid</span><span class="sxs-lookup"><span data-stu-id="87427-292">Humid</span></span> |<span data-ttu-id="87427-293">JSON의 추가 속성은 키-값 쌍이 되며 배열은 값 개체로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-293">Extra property from the JSON becomes a key-value pair, with an array as the value object.</span></span>|

<span data-ttu-id="87427-294">대상 개체가 serialize 되 면 확장 데이터 키 값 쌍은 수신 JSON에 있는 것 처럼 JSON 속성이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87427-294">When the target object is serialized, the extension data key value pairs become JSON properties just as they were in the incoming JSON:</span></span>

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

<span data-ttu-id="87427-295">@No__t-0 속성 이름은 JSON에 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-295">Notice that the `ExtensionData` property name doesn't appear in the JSON.</span></span> <span data-ttu-id="87427-296">이 동작을 통해 JSON은 deserialize 되지 않는 추가 데이터를 잃지 않고도 라운드트립을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87427-296">This behavior lets the JSON make a round trip without losing any extra data that otherwise wouldn't be deserialized.</span></span>

## <a name="use-utf8jsonwriter-directly"></a><span data-ttu-id="87427-297">Utf8JsonWriter 직접 사용</span><span class="sxs-lookup"><span data-stu-id="87427-297">Use Utf8JsonWriter directly</span></span>

<span data-ttu-id="87427-298">다음 예제에서는 <xref:System.Text.Json.Utf8JsonWriter> 클래스를 직접 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87427-298">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class directly.</span></span>

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

## <a name="use-utf8jsonreader-directly"></a><span data-ttu-id="87427-299">Utf8JsonReader 직접 사용</span><span class="sxs-lookup"><span data-stu-id="87427-299">Use Utf8JsonReader directly</span></span>

<span data-ttu-id="87427-300">다음 예제에서는 <xref:System.Text.Json.Utf8JsonReader> 클래스를 직접 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="87427-300">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class directly.</span></span> <span data-ttu-id="87427-301">이 코드에서는 `jsonUtf8` 변수가 u t f-8로 인코딩된 유효한 JSON을 포함 하는 바이트 배열 이라고 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="87427-301">The code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

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

## <a name="additional-resources"></a><span data-ttu-id="87427-302">추가 자료</span><span class="sxs-lookup"><span data-stu-id="87427-302">Additional resources</span></span>

* [<span data-ttu-id="87427-303">System.object 개요</span><span class="sxs-lookup"><span data-stu-id="87427-303">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="87427-304">System.object API 참조</span><span class="sxs-lookup"><span data-stu-id="87427-304">System.Text.Json API reference</span></span>](xref:System.Text.Json)
* [<span data-ttu-id="87427-305">System.object의 DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="87427-305">DateTime and DateTimeOffset support in System.Text.Json</span></span>](../datetime/system-text-json-support.md)
