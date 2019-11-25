---
title: System.Text.Json의 DateTime 및 DateTimeOffset 지원
description: DateTime 및 DateTimeOffset 형식이 System.object 라이브러리에서 지원 되는 방법에 대 한 개요입니다.
ms.technology: dotnet-standard
author: layomia
ms.author: laakinri
ms.date: 07/22/2019
helpviewer_keywords:
- JSON, Serializer, Utf8
- JSON DateTime, JSON DateTimeOffset
- DateTime, DateTimeOffset
- JsonSerializer, Utf8JsonReader, Utf8JsonWriter, JsonElement, JsonDocument
- JSON Serializer, JSON Reader, JSON Writer
- Converter, JSON Converter, DateTime Converter
- ISO, ISO 8601, ISO 8601-1:2019
ms.openlocfilehash: 04e0e3c613b194ac85241d50d3bc5fd5dc0b6e54
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73977332"
---
# <a name="datetime-and-datetimeoffset-support-in-systemtextjson"></a><span data-ttu-id="89736-103">System.Text.Json의 DateTime 및 DateTimeOffset 지원</span><span class="sxs-lookup"><span data-stu-id="89736-103">DateTime and DateTimeOffset support in System.Text.Json</span></span>

<span data-ttu-id="89736-104">System.string 라이브러리는 ISO 8601:-2019 확장 프로필에 따라 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값을 구문 분석 하 고 씁니다.</span><span class="sxs-lookup"><span data-stu-id="89736-104">The System.Text.Json library parses and writes <xref:System.DateTime> and <xref:System.DateTimeOffset> values according to the ISO 8601:-2019 extended profile.</span></span>
<span data-ttu-id="89736-105">[변환기](xref:System.Text.Json.Serialization.JsonConverter%601) 는 <xref:System.Text.Json.JsonSerializer>serialize 및 deserialize에 대 한 사용자 지정 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-105">[Converters](xref:System.Text.Json.Serialization.JsonConverter%601) provide custom support for serializing and deserializing with <xref:System.Text.Json.JsonSerializer>.</span></span>
<span data-ttu-id="89736-106"><xref:System.Text.Json.Utf8JsonReader> 및 <xref:System.Text.Json.Utf8JsonWriter>를 사용 하는 경우에도 사용자 지정 지원을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-106">Custom support can also be implemented when using <xref:System.Text.Json.Utf8JsonReader> and <xref:System.Text.Json.Utf8JsonWriter>.</span></span>

## <a name="support-for-the-iso-8601-12019-format"></a><span data-ttu-id="89736-107">ISO 8601-1:2019 형식에 대 한 지원</span><span class="sxs-lookup"><span data-stu-id="89736-107">Support for the ISO 8601-1:2019 format</span></span>

<span data-ttu-id="89736-108"><xref:System.Text.Json.JsonSerializer>, <xref:System.Text.Json.Utf8JsonReader>, <xref:System.Text.Json.Utf8JsonWriter>및 <xref:System.Text.Json.JsonElement> 형식은 ISO 8601-1:2019 형식의 확장 된 프로필에 따라 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 텍스트 표현을 구문 분석 하 고 작성 합니다. 예: 2019-07-26T16:59:57-05:00.</span><span class="sxs-lookup"><span data-stu-id="89736-108">The <xref:System.Text.Json.JsonSerializer>, <xref:System.Text.Json.Utf8JsonReader>, <xref:System.Text.Json.Utf8JsonWriter>, and <xref:System.Text.Json.JsonElement> types parse and write <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations according to the extended profile of the ISO 8601-1:2019 format; for example, 2019-07-26T16:59:57-05:00.</span></span>

<span data-ttu-id="89736-109"><xref:System.Text.Json.JsonSerializer>를 사용 하 여 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 데이터를 직렬화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-109"><xref:System.DateTime> and <xref:System.DateTimeOffset> data can be serialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-serializing-with-jsonserializer](~/samples/snippets/standard/datetime/json/csharp/serializing-with-jsonserializer/Program.cs)]

<span data-ttu-id="89736-110">또한 <xref:System.Text.Json.JsonSerializer>를 사용 하 여 deserialize 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-110">They can also be deserialized with <xref:System.Text.Json.JsonSerializer>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-valid](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-valid/Program.cs)]

<span data-ttu-id="89736-111">기본 옵션을 사용 하 여 입력 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 텍스트 표현은 확장 된 ISO 8601-1:2019 프로필을 준수 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-111">With default options, input <xref:System.DateTime> and <xref:System.DateTimeOffset> text representations must conform to the extended ISO 8601-1:2019 profile.</span></span>
<span data-ttu-id="89736-112">프로필에 맞지 않는 표시를 deserialize 하려고 하면 <xref:System.Text.Json.JsonSerializer>에서 <xref:System.Text.Json.JsonException>를 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-112">Attempting to deserialize representations that don't conform to the profile will cause <xref:System.Text.Json.JsonSerializer> to throw a <xref:System.Text.Json.JsonException>:</span></span>

[!code-csharp[example-deserializing-with-jsonserializer-error](~/samples/snippets/standard/datetime/json/csharp/deserializing-with-jsonserializer-error/Program.cs)]

<span data-ttu-id="89736-113"><xref:System.Text.Json.JsonDocument>는 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 표현을 포함 하 여 JSON 페이로드의 내용에 대 한 구조적 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-113">The <xref:System.Text.Json.JsonDocument> provides structured access to the contents of a JSON payload, including <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span> <span data-ttu-id="89736-114">아래 예제에서는 온도 수집이 지정 된 경우 월요일의 평균 온도를 계산할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89736-114">The example below shows how, when given a collection of temperatures, the average temperature on Mondays can be calculated:</span></span>

[!code-csharp[example-computing-with-jsondocument-valid](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-valid/Program.cs)]

<span data-ttu-id="89736-115">호환 되지 않는 <xref:System.DateTime> 표현의 페이로드가 지정 된 경우 평균 온도를 계산 하려고 하면 <xref:System.Text.Json.JsonDocument>에서 <xref:System.FormatException>을 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-115">Attempting to compute the average temperature given a payload with non-compliant <xref:System.DateTime> representations will cause <xref:System.Text.Json.JsonDocument> to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-computing-with-jsondocument-error](~/samples/snippets/standard/datetime/json/csharp/computing-with-jsondocument-error/Program.cs)]

<span data-ttu-id="89736-116">낮은 수준 <xref:System.Text.Json.Utf8JsonWriter> <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 데이터를 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-116">The lower level <xref:System.Text.Json.Utf8JsonWriter> writes <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/writing-with-utf8jsonwriter/Program.cs)]

<span data-ttu-id="89736-117"><xref:System.Text.Json.Utf8JsonReader> <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 데이터를 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-117"><xref:System.Text.Json.Utf8JsonReader> parses <xref:System.DateTime> and <xref:System.DateTimeOffset> data:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-valid](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-valid/Program.cs)]

<span data-ttu-id="89736-118"><xref:System.Text.Json.Utf8JsonReader>를 사용 하 여 비호환 형식을 읽으려고 하면 <xref:System.FormatException>throw 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-118">Attempting to read non-compliant formats with <xref:System.Text.Json.Utf8JsonReader> will cause it to throw a <xref:System.FormatException>:</span></span>

[!code-csharp[example-reading-with-utf8jsonreader-error](~/samples/snippets/standard/datetime/json/csharp/reading-with-utf8jsonreader-error/Program.cs)]

## <a name="custom-support-for-xrefsystemdatetime-and-xrefsystemdatetimeoffset"></a><span data-ttu-id="89736-119"><xref:System.DateTime> 및 <xref:System.DateTimeOffset>에 대 한 사용자 지정 지원</span><span class="sxs-lookup"><span data-stu-id="89736-119">Custom support for <xref:System.DateTime> and <xref:System.DateTimeOffset></span></span>

### <a name="when-using-xrefsystemtextjsonjsonserializer"></a><span data-ttu-id="89736-120"><xref:System.Text.Json.JsonSerializer> 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="89736-120">When using <xref:System.Text.Json.JsonSerializer></span></span>

<span data-ttu-id="89736-121">Serializer에서 사용자 지정 구문 분석 또는 서식 지정을 수행 하려는 경우 [사용자 지정 변환기](xref:System.Text.Json.Serialization.JsonConverter%601)를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-121">If you want the serializer to perform custom parsing or formatting, you can implement [custom converters](xref:System.Text.Json.Serialization.JsonConverter%601).</span></span>
<span data-ttu-id="89736-122">다음은 몇 가지 예입니다.</span><span class="sxs-lookup"><span data-stu-id="89736-122">Here are a few examples:</span></span>

#### <a name="using-datetimeoffsetparse-and-datetimeoffsettostring"></a><span data-ttu-id="89736-123">`DateTime(Offset).Parse` 및 `DateTime(Offset).ToString` 사용</span><span class="sxs-lookup"><span data-stu-id="89736-123">Using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`</span></span>

<span data-ttu-id="89736-124">입력 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 텍스트 표현의 형식을 확인할 수 없는 경우 변환기 읽기 논리에서 `DateTime(Offset).Parse` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-124">If you can't determine the formats of your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations, you can use the `DateTime(Offset).Parse` method in your converter read logic.</span></span> <span data-ttu-id="89736-125">이렇게 하면를 사용할 수 있습니다. 확장 된 ISO 8601-1:2019 프로필을 준수 하지 않는 iso 8601 문자열과 iso 8601 형식을 비롯 하 여 다양 한 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 텍스트 형식 구문 분석에 대 한 광범위 한 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-125">This allows you to use .NET's extensive support for parsing various <xref:System.DateTime> and <xref:System.DateTimeOffset> text formats, including non-ISO 8601 strings and ISO 8601 formats that don't conform to the extended ISO 8601-1:2019 profile.</span></span> <span data-ttu-id="89736-126">이 방법은 serializer의 기본 구현을 사용 하는 것 보다 성능이 훨씬 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-126">This approach is significantly less performant than using the serializer's native implementation.</span></span>

<span data-ttu-id="89736-127">Serialize를 위해 변환기 쓰기 논리에 `DateTime(Offset).ToString` 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-127">For serializing, you can use the `DateTime(Offset).ToString` method in your converter write logic.</span></span> <span data-ttu-id="89736-128">이를 통해 [표준 날짜 및 시간 형식](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)및 [사용자 지정 날짜 및 시간 형식을](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings)사용 하 여 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 값을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-128">This allows you to write <xref:System.DateTime> and <xref:System.DateTimeOffset> values using any of the [standard date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), and the [custom date and time formats](https://docs.microsoft.com/dotnet/standard/base-types/custom-date-and-time-format-strings).</span></span>
<span data-ttu-id="89736-129">이는 serializer의 기본 구현을 사용 하는 것 보다 성능이 훨씬 낮습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-129">This is also significantly less performant than using the serializer's native implementation.</span></span>

[!code-csharp[example-showing-datetime-parse](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example1/Program.cs)]

> [!NOTE]
> <span data-ttu-id="89736-130"><xref:System.Text.Json.Serialization.JsonConverter%601>를 구현할 때 `T` <xref:System.DateTime>되는 경우 `typeToConvert` 매개 변수는 항상 `typeof(DateTime)`됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-130">When implementing <xref:System.Text.Json.Serialization.JsonConverter%601>, and `T` is <xref:System.DateTime>, the `typeToConvert` parameter will always be `typeof(DateTime)`.</span></span>
<span data-ttu-id="89736-131">매개 변수는 다형성 사례를 처리 하는 데 유용 하며 제네릭을 사용 하 여 성능에 `typeof(T)`를 가져올 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-131">The parameter is useful for handling polymorphic cases and when using generics to get `typeof(T)` in a performant way.</span></span>

#### <a name="using-xrefsystembufferstextutf8parser-and-xrefsystembufferstextutf8formatter"></a><span data-ttu-id="89736-132"><xref:System.Buffers.Text.Utf8Parser> 및 <xref:System.Buffers.Text.Utf8Formatter> 사용</span><span class="sxs-lookup"><span data-stu-id="89736-132">Using <xref:System.Buffers.Text.Utf8Parser> and <xref:System.Buffers.Text.Utf8Formatter></span></span>

<span data-ttu-id="89736-133">입력 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 텍스트 표현이 "R", "l", "O" 또는 "G" [표준 날짜 및 시간 형식 문자열](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings)중 하나를 준수 하거나 이러한 형식 중 하나에 따라 쓰려면 변환기 논리에서 빠른 utf-8 기반 구문 분석 및 형식 지정 메서드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-133">You can use fast UTF-8-based parsing and formatting methods in your converter logic if your input <xref:System.DateTime> or <xref:System.DateTimeOffset> text representations are compliant with one of the "R", "l", "O", or "G" [standard date and time format strings](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings), or you want to write according to one of these formats.</span></span> <span data-ttu-id="89736-134">`DateTime(Offset).Parse` 및 `DateTime(Offset).ToString`를 사용 하는 것 보다 훨씬 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="89736-134">This is much faster than using `DateTime(Offset).Parse` and `DateTime(Offset).ToString`.</span></span>

<span data-ttu-id="89736-135">이 예제에서는 ["R" 표준 형식](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier)에 따라 <xref:System.DateTime> 값을 serialize 및 deserialize 하는 사용자 지정 변환기를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89736-135">This example shows a custom converter that serializes and deserializes <xref:System.DateTime> values according to [the "R" standard format](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-rfc1123-r-r-format-specifier):</span></span>

[!code-csharp[example-showing-utf8-parser-and-formatter](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example2/Program.cs)]

> [!NOTE]
> <span data-ttu-id="89736-136">"R" 표준 형식은 항상 29 자 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="89736-136">The "R" standard format will always be 29 characters long.</span></span>

#### <a name="using-datetimeoffsetparse-as-a-fallback-to-the-serializers-native-parsing"></a><span data-ttu-id="89736-137">`DateTime(Offset).Parse`을 serializer의 네이티브 구문 분석에 대 한 대체 (fallback)로 사용</span><span class="sxs-lookup"><span data-stu-id="89736-137">Using `DateTime(Offset).Parse` as a fallback to the serializer's native parsing</span></span>

<span data-ttu-id="89736-138">일반적으로 입력 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 데이터가 확장 된 ISO 8601-1:2019 프로필을 따르도록 하려는 경우 serializer의 네이티브 구문 분석 논리를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-138">If you generally expect your input <xref:System.DateTime> or <xref:System.DateTimeOffset> data to conform to the extended ISO 8601-1:2019 profile, you can use the serializer's native parsing logic.</span></span> <span data-ttu-id="89736-139">경우에만 대체 메커니즘을 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-139">You can also implement a fallback mechanism just in case.</span></span>
<span data-ttu-id="89736-140">이 예에서는 <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>를 사용 하 여 <xref:System.DateTime> 텍스트 표현의 구문 분석에 실패 한 후 변환기에서 <xref:System.DateTime.Parse(System.String)>를 사용 하 여 데이터를 성공적으로 구문 분석 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89736-140">This example shows that, after failing to parse a <xref:System.DateTime> text representation using <xref:System.Text.Json.Utf8JsonReader.TryGetDateTime(System.DateTime@)>, the converter successfully parses the data using <xref:System.DateTime.Parse(System.String)>.</span></span>

[!code-csharp[example-showing-datetime-parse-as-fallback](~/samples/snippets/standard/datetime/json/csharp/datetime-converter-examples/example3/Program.cs)]

### <a name="when-writing-with-xrefsystemtextjsonutf8jsonwriter"></a><span data-ttu-id="89736-141"><xref:System.Text.Json.Utf8JsonWriter>를 사용 하 여 작성 하는 경우</span><span class="sxs-lookup"><span data-stu-id="89736-141">When writing with <xref:System.Text.Json.Utf8JsonWriter></span></span>

<span data-ttu-id="89736-142"><xref:System.Text.Json.Utf8JsonWriter>를 사용 하 여 사용자 지정 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 텍스트 표현을 작성 하려는 경우 사용자 지정 표현의 서식을 <xref:System.String>, `ReadOnlySpan<Byte>`, `ReadOnlySpan<Char>`또는 <xref:System.Text.Json.JsonEncodedText>로 지정한 다음 해당 [Utf8JsonWriter](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestringvalue?view=netcore-3.0) 또는 [Utf8JsonWriter](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestring?view=netcore-3.0) 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-142">If you want to write a custom <xref:System.DateTime> or <xref:System.DateTimeOffset> text representation with <xref:System.Text.Json.Utf8JsonWriter>, you can format your custom representation to a <xref:System.String>, `ReadOnlySpan<Byte>`, `ReadOnlySpan<Char>`, or <xref:System.Text.Json.JsonEncodedText>, then pass it to the corresponding [Utf8JsonWriter.WriteStringValue](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestringvalue?view=netcore-3.0) or [Utf8JsonWriter.WriteString](https://docs.microsoft.com/dotnet/api/system.text.json.utf8jsonwriter.writestring?view=netcore-3.0) method.</span></span>

<span data-ttu-id="89736-143">다음 예제에서는 <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>를 사용 하 여 사용자 지정 <xref:System.DateTime> 형식을 만든 다음 <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)> 메서드로 작성할 수 있는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89736-143">The following example shows how a custom <xref:System.DateTime> format can be created with <xref:System.DateTime.ToString(System.String,System.IFormatProvider)>, then written with the <xref:System.Text.Json.Utf8JsonWriter.WriteStringValue(System.String)> method:</span></span>

[!code-csharp[example-custom-writing-with-utf8jsonwriter](~/samples/snippets/standard/datetime/json/csharp/custom-writing-with-utf8jsonwriter/Program.cs)]

### <a name="when-reading-with-xrefsystemtextjsonutf8jsonreader"></a><span data-ttu-id="89736-144"><xref:System.Text.Json.Utf8JsonReader>를 사용 하 여 읽는 경우</span><span class="sxs-lookup"><span data-stu-id="89736-144">When reading with <xref:System.Text.Json.Utf8JsonReader></span></span>

<span data-ttu-id="89736-145"><xref:System.Text.Json.Utf8JsonReader>를 사용 하 여 사용자 지정 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset> 텍스트 표현을 읽으려면 <xref:System.Text.Json.Utf8JsonReader.GetString>를 사용 하 여 현재 JSON 토큰의 값을 <xref:System.String>로 가져온 다음 사용자 지정 논리를 사용 하 여 값을 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-145">If you want to read a custom <xref:System.DateTime> or <xref:System.DateTimeOffset> text representation with <xref:System.Text.Json.Utf8JsonReader>, you can get the value of the current JSON token as a <xref:System.String> using <xref:System.Text.Json.Utf8JsonReader.GetString>, then parse the value using custom logic.</span></span>

<span data-ttu-id="89736-146">다음 예에서는 <xref:System.Text.Json.Utf8JsonReader.GetString>를 사용 하 여 사용자 지정 <xref:System.DateTimeOffset> 텍스트 표현을 검색 한 다음 <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>를 사용 하 여 구문 분석 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="89736-146">The following example shows how a custom <xref:System.DateTimeOffset> text representation can be retrieved using <xref:System.Text.Json.Utf8JsonReader.GetString>, then parsed using <xref:System.DateTimeOffset.ParseExact(System.String,System.String,System.IFormatProvider)>:</span></span>

[!code-csharp[example-custom-reading-with-utf8jsonreader](~/samples/snippets/standard/datetime/json/csharp/custom-reading-with-utf8jsonreader/Program.cs)]

## <a name="the-extended-iso-8601-12019-profile-in-systemtextjson"></a><span data-ttu-id="89736-147">System.object의 확장 된 ISO 8601-1:2019 프로필</span><span class="sxs-lookup"><span data-stu-id="89736-147">The extended ISO 8601-1:2019 profile in System.Text.Json</span></span>

### <a name="date-and-time-components"></a><span data-ttu-id="89736-148">날짜 및 시간 구성 요소</span><span class="sxs-lookup"><span data-stu-id="89736-148">Date and time components</span></span>

<span data-ttu-id="89736-149"><xref:System.Text.Json>에 구현 된 확장 ISO 8601-1:2019 프로필은 날짜 및 시간 표현에 대해 다음과 같은 구성 요소를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-149">The extended ISO 8601-1:2019 profile implemented in <xref:System.Text.Json> defines the following components for date and time representations.</span></span> <span data-ttu-id="89736-150">이러한 구성 요소는 <xref:System.DateTime> 및 <xref:System.DateTimeOffset> 표현을 구문 분석 하 고 서식을 지정할 때 지원 되는 다양 한 세분성 수준을 정의 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-150">These components are used to define various levels of granularity supported when parsing and formatting <xref:System.DateTime> and <xref:System.DateTimeOffset> representations.</span></span>

| <span data-ttu-id="89736-151">구성 요소</span><span class="sxs-lookup"><span data-stu-id="89736-151">Component</span></span>       | <span data-ttu-id="89736-152">서식</span><span class="sxs-lookup"><span data-stu-id="89736-152">Format</span></span>                      | <span data-ttu-id="89736-153">설명</span><span class="sxs-lookup"><span data-stu-id="89736-153">Description</span></span>                                                                     |
|-----------------|-----------------------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="89736-154">Year</span><span class="sxs-lookup"><span data-stu-id="89736-154">Year</span></span>            | <span data-ttu-id="89736-155">"yyyy"</span><span class="sxs-lookup"><span data-stu-id="89736-155">"yyyy"</span></span>                      | <span data-ttu-id="89736-156">0001-9999</span><span class="sxs-lookup"><span data-stu-id="89736-156">0001-9999</span></span>                                                                       |
| <span data-ttu-id="89736-157">월</span><span class="sxs-lookup"><span data-stu-id="89736-157">Month</span></span>           | <span data-ttu-id="89736-158">"MM"</span><span class="sxs-lookup"><span data-stu-id="89736-158">"MM"</span></span>                        | <span data-ttu-id="89736-159">01-12</span><span class="sxs-lookup"><span data-stu-id="89736-159">01-12</span></span>                                                                           |
| <span data-ttu-id="89736-160">Day</span><span class="sxs-lookup"><span data-stu-id="89736-160">Day</span></span>             | <span data-ttu-id="89736-161">"dd"</span><span class="sxs-lookup"><span data-stu-id="89736-161">"dd"</span></span>                        | <span data-ttu-id="89736-162">월/연도를 기준으로 하는 01-28, 01-29, 01-30, 01-31</span><span class="sxs-lookup"><span data-stu-id="89736-162">01-28, 01-29, 01-30, 01-31 based on month/year</span></span>                                  |
| <span data-ttu-id="89736-163">Hour</span><span class="sxs-lookup"><span data-stu-id="89736-163">Hour</span></span>            | <span data-ttu-id="89736-164">"HH"</span><span class="sxs-lookup"><span data-stu-id="89736-164">"HH"</span></span>                        | <span data-ttu-id="89736-165">00-23</span><span class="sxs-lookup"><span data-stu-id="89736-165">00-23</span></span>                                                                           |
| <span data-ttu-id="89736-166">Minute</span><span class="sxs-lookup"><span data-stu-id="89736-166">Minute</span></span>          | <span data-ttu-id="89736-167">"mm"</span><span class="sxs-lookup"><span data-stu-id="89736-167">"mm"</span></span>                        | <span data-ttu-id="89736-168">00-59</span><span class="sxs-lookup"><span data-stu-id="89736-168">00-59</span></span>                                                                           |
| <span data-ttu-id="89736-169">Second</span><span class="sxs-lookup"><span data-stu-id="89736-169">Second</span></span>          | <span data-ttu-id="89736-170">"ss"</span><span class="sxs-lookup"><span data-stu-id="89736-170">"ss"</span></span>                        | <span data-ttu-id="89736-171">00-59</span><span class="sxs-lookup"><span data-stu-id="89736-171">00-59</span></span>                                                                           |
| <span data-ttu-id="89736-172">초 분수</span><span class="sxs-lookup"><span data-stu-id="89736-172">Second fraction</span></span> | <span data-ttu-id="89736-173">"FFFFFFF"</span><span class="sxs-lookup"><span data-stu-id="89736-173">"FFFFFFF"</span></span>                   | <span data-ttu-id="89736-174">최소 1 자리 숫자, 최대 16 자리</span><span class="sxs-lookup"><span data-stu-id="89736-174">Minimum of one digit, maximum of 16 digits</span></span>                                      |
| <span data-ttu-id="89736-175">시간 오프셋</span><span class="sxs-lookup"><span data-stu-id="89736-175">Time offset</span></span>     | <span data-ttu-id="89736-176">"K"</span><span class="sxs-lookup"><span data-stu-id="89736-176">"K"</span></span>                         | <span data-ttu-id="89736-177">"Z" 또는 "(' + '/'-') HH ': ' mm"</span><span class="sxs-lookup"><span data-stu-id="89736-177">Either "Z" or "('+'/'-')HH':'mm"</span></span>                                                |
| <span data-ttu-id="89736-178">부분 시간</span><span class="sxs-lookup"><span data-stu-id="89736-178">Partial time</span></span>    | <span data-ttu-id="89736-179">"HH ': ' mm ': ' ss [FFFFFFF]"</span><span class="sxs-lookup"><span data-stu-id="89736-179">"HH':'mm':'ss[FFFFFFF]"</span></span>     | <span data-ttu-id="89736-180">UTC 오프셋 정보가 없는 시간</span><span class="sxs-lookup"><span data-stu-id="89736-180">Time without UTC offset information</span></span>                                             |
| <span data-ttu-id="89736-181">전체 날짜</span><span class="sxs-lookup"><span data-stu-id="89736-181">Full date</span></span>       | <span data-ttu-id="89736-182">"yyyy'-'mm'-'dd't'hh-'MM'-'dd"</span><span class="sxs-lookup"><span data-stu-id="89736-182">"yyyy'-'MM'-'dd"</span></span>            | <span data-ttu-id="89736-183">달력 날짜</span><span class="sxs-lookup"><span data-stu-id="89736-183">Calendar date</span></span>                                                                   |
| <span data-ttu-id="89736-184">전체 시간</span><span class="sxs-lookup"><span data-stu-id="89736-184">Full time</span></span>       | <span data-ttu-id="89736-185">"' Partial time'K"</span><span class="sxs-lookup"><span data-stu-id="89736-185">"'Partial time'K"</span></span>           | <span data-ttu-id="89736-186">현지 시간과 UTC 사이의 시간 오프셋을 사용한 하루 또는 현지 시간 (UTC)</span><span class="sxs-lookup"><span data-stu-id="89736-186">UTC of day or Local time of day with the time offset between local time and UTC</span></span> |
| <span data-ttu-id="89736-187">날짜 시간</span><span class="sxs-lookup"><span data-stu-id="89736-187">Date time</span></span>       | <span data-ttu-id="89736-188">"' 전체 날짜 ' ' ' ' 전체 시간 '"</span><span class="sxs-lookup"><span data-stu-id="89736-188">"'Full date''T''Full time'"</span></span> | <span data-ttu-id="89736-189">달력 날짜 및 시간 (예: 2019-07-26T16:59:57-05:00)</span><span class="sxs-lookup"><span data-stu-id="89736-189">Calendar date and time of day, e.g. 2019-07-26T16:59:57-05:00</span></span>                   |

### <a name="support-for-parsing"></a><span data-ttu-id="89736-190">구문 분석 지원</span><span class="sxs-lookup"><span data-stu-id="89736-190">Support for parsing</span></span>

<span data-ttu-id="89736-191">구문 분석에 대해 정의 되는 세분성 수준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-191">The following levels of granularity are defined for parsing:</span></span>

1. <span data-ttu-id="89736-192">' 전체 날짜 '</span><span class="sxs-lookup"><span data-stu-id="89736-192">'Full date'</span></span>
    1. <span data-ttu-id="89736-193">"yyyy'-'mm'-'dd't'hh-'MM'-'dd"</span><span class="sxs-lookup"><span data-stu-id="89736-193">"yyyy'-'MM'-'dd"</span></span>

2. <span data-ttu-id="89736-194">"' 전체 날짜 ' ' ' ' ' 시간 ' ': ' ' Minute '"</span><span class="sxs-lookup"><span data-stu-id="89736-194">"'Full date''T''Hour'':''Minute'"</span></span>
    1. <span data-ttu-id="89736-195">"yyyy'-'mm'-'dd't'hh-'MM'-' m ': ' MM '</span><span class="sxs-lookup"><span data-stu-id="89736-195">"yyyy'-'MM'-'dd'T'HH':'mm"</span></span>

3. <span data-ttu-id="89736-196">"' 전체 날짜 ' ' ' ' ' 부분 시간 '"</span><span class="sxs-lookup"><span data-stu-id="89736-196">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="89736-197">"yyyy'-'mm'-'dd't'hh-'MM'-% Ddu: ' MM ': ' ss ' ([정렬 가능한 (" s ") 서식 지정자](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span><span class="sxs-lookup"><span data-stu-id="89736-197">"yyyy'-'MM'-'dd'T'HH':'mm':'ss" ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>
    2. <span data-ttu-id="89736-198">"yyyy'-'mm'-'dd't'hh-'MM'-% n이 (가): ' MM ': ' ss '. ' FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="89736-198">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

4. <span data-ttu-id="89736-199">"' 전체 날짜 ' ' ' ' 시간 시간 ' ': ' ' Minute ' ' 시간 오프셋 '"</span><span class="sxs-lookup"><span data-stu-id="89736-199">"'Full date''T''Time hour'':''Minute''Time offset'"</span></span>
    1. <span data-ttu-id="89736-200">"yyyy'-'mm'-'dd't'hh-'MM'-% n n e t ': ' mmZ '</span><span class="sxs-lookup"><span data-stu-id="89736-200">"yyyy'-'MM'-'dd'T'HH':'mmZ"</span></span>
    2. <span data-ttu-id="89736-201">"yyyy'-'mm'-'dd't'hh-'MM'-% Ddn ': ' mm (' + '/'-') HH ': ' mm"</span><span class="sxs-lookup"><span data-stu-id="89736-201">"yyyy'-'MM'-'dd'T'HH':'mm('+'/'-')HH':'mm"</span></span>

5. <span data-ttu-id="89736-202">' 날짜 시간 '</span><span class="sxs-lookup"><span data-stu-id="89736-202">'Date time'</span></span>
    1. <span data-ttu-id="89736-203">"yyyy'-'mm'-'dd't'hh-'MM'-% n이 (가): ' MM ': ' ssZ '</span><span class="sxs-lookup"><span data-stu-id="89736-203">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>
    2. <span data-ttu-id="89736-204">"yyyy'-'mm'-'dd't'hh-'MM'-% n이 (가): ' MM ': ' ss '. ' FFFFFFFZ "</span><span class="sxs-lookup"><span data-stu-id="89736-204">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>
    3. <span data-ttu-id="89736-205">"yyyy'-'mm'-'dd't'hh-'MM'-% n n e t ': ' mm ': ' ss (' + '/'-') HH ': ' mm '</span><span class="sxs-lookup"><span data-stu-id="89736-205">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>
    4. <span data-ttu-id="89736-206">"yyyy'-'mm'-'dd't'hh-'MM'-% n이 (가): ' MM ': ' ss '. ' FFFFFFF (' + '/'-') HH ': ' mm '</span><span class="sxs-lookup"><span data-stu-id="89736-206">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

<span data-ttu-id="89736-207">초에 소수 자릿수가 있으면 숫자가 하나 이상 있어야 합니다. `2019-07-26T00:00:00.` 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-207">If there are decimal fractions for seconds, there must be at least one digit; `2019-07-26T00:00:00.` is not allowed.</span></span>
<span data-ttu-id="89736-208">최대 16 개의 소수 자릿수가 허용 되지만 처음 7 개만 구문 분석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-208">While up to 16 fractional digits are allowed, only the first seven are parsed.</span></span> <span data-ttu-id="89736-209">그 외의 모든 항목은 0으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-209">Anything beyond that is considered a zero.</span></span>
<span data-ttu-id="89736-210">예를 들어 `2019-07-26T00:00:00.1234567890` `2019-07-26T00:00:00.1234567`되는 것 처럼 구문 분석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-210">For example, `2019-07-26T00:00:00.1234567890` will be parsed as if it is `2019-07-26T00:00:00.1234567`.</span></span>
<span data-ttu-id="89736-211">이는이 해상도로 제한 되는 <xref:System.DateTime> 구현과의 호환성을 유지 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="89736-211">This is to stay compatible with the <xref:System.DateTime> implementation, which is limited to this resolution.</span></span>

<span data-ttu-id="89736-212">윤 초는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-212">Leap seconds are not supported.</span></span>

### <a name="support-for-formatting"></a><span data-ttu-id="89736-213">서식 지정 지원</span><span class="sxs-lookup"><span data-stu-id="89736-213">Support for formatting</span></span>

<span data-ttu-id="89736-214">서식 지정에 대해 정의 된 세분성 수준은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="89736-214">The following levels of granularity are defined for formatting:</span></span>

1. <span data-ttu-id="89736-215">"' 전체 날짜 ' ' ' ' ' 부분 시간 '"</span><span class="sxs-lookup"><span data-stu-id="89736-215">"'Full date''T''Partial time'"</span></span>
    1. <span data-ttu-id="89736-216">"yyyy'-'mm'-'dd't'hh-'MM'-% Ddu: ' MM ': ' ss ' ([정렬 가능한 (" s ") 서식 지정자](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span><span class="sxs-lookup"><span data-stu-id="89736-216">"yyyy'-'MM'-'dd'T'HH':'mm':'ss"  ([The Sortable ("s") Format Specifier](https://docs.microsoft.com/dotnet/standard/base-types/standard-date-and-time-format-strings#the-sortable-s-format-specifier))</span></span>

        <span data-ttu-id="89736-217">오프셋 정보 없이 소수 자릿수 초 없이 <xref:System.DateTime>의 형식을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-217">Used to format a <xref:System.DateTime> without fractional seconds and without offset information.</span></span>

    2. <span data-ttu-id="89736-218">"yyyy'-'mm'-'dd't'hh-'MM'-% n이 (가): ' MM ': ' ss '. ' FFFFFFF</span><span class="sxs-lookup"><span data-stu-id="89736-218">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF"</span></span>

        <span data-ttu-id="89736-219">오프셋 정보 없이 소수 자릿수 초를 사용 하 여 <xref:System.DateTime>의 형식을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-219">Used to format a <xref:System.DateTime> with fractional seconds but without offset information.</span></span>

2. <span data-ttu-id="89736-220">' 날짜 시간 '</span><span class="sxs-lookup"><span data-stu-id="89736-220">'Date time'</span></span>
    1. <span data-ttu-id="89736-221">"yyyy'-'mm'-'dd't'hh-'MM'-% n이 (가): ' MM ': ' ssZ '</span><span class="sxs-lookup"><span data-stu-id="89736-221">"yyyy'-'MM'-'dd'T'HH':'mm':'ssZ"</span></span>

        <span data-ttu-id="89736-222">소수 자릿수 초를 제외 하 고 UTC 오프셋을 사용 하 여 <xref:System.DateTime>의 형식을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-222">Used to format a <xref:System.DateTime> without fractional seconds but with a UTC offset.</span></span>

    2. <span data-ttu-id="89736-223">"yyyy'-'mm'-'dd't'hh-'MM'-% n이 (가): ' MM ': ' ss '. ' FFFFFFFZ "</span><span class="sxs-lookup"><span data-stu-id="89736-223">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFFZ"</span></span>

        <span data-ttu-id="89736-224">소수 자릿수 초 및 UTC 오프셋을 사용 하 여 <xref:System.DateTime>의 형식을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-224">Used to format a <xref:System.DateTime> with fractional seconds and with a UTC offset.</span></span>

    3. <span data-ttu-id="89736-225">"yyyy'-'mm'-'dd't'hh-'MM'-% n n e t ': ' mm ': ' ss (' + '/'-') HH ': ' mm '</span><span class="sxs-lookup"><span data-stu-id="89736-225">"yyyy'-'MM'-'dd'T'HH':'mm':'ss('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="89736-226">소수 자릿수 초를 제외 하 고 로컬 오프셋을 사용 하 여 <xref:System.DateTime> 또는 <xref:System.DateTimeOffset>의 형식을 지정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-226">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> without fractional seconds but with a local offset.</span></span>

    4. <span data-ttu-id="89736-227">"yyyy'-'mm'-'dd't'hh-'MM'-% n이 (가): ' MM ': ' ss '. ' FFFFFFF (' + '/'-') HH ': ' mm '</span><span class="sxs-lookup"><span data-stu-id="89736-227">"yyyy'-'MM'-'dd'T'HH':'mm':'ss'.'FFFFFFF('+'/'-')HH':'mm"</span></span>

        <span data-ttu-id="89736-228"><xref:System.DateTime> 또는 <xref:System.DateTimeOffset>의 형식을 지정 하는 데 사용 됩니다. 소수 자릿수 초 및 현지 오프셋을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="89736-228">Used to format a <xref:System.DateTime> or <xref:System.DateTimeOffset> with fractional seconds and with a local offset.</span></span>

<span data-ttu-id="89736-229">있는 경우 최대 7 개의 소수 자릿수가 기록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-229">If present, a maximum of 7 fractional digits are written.</span></span> <span data-ttu-id="89736-230">이는이 해상도로 제한 되는 <xref:System.DateTime> 구현에 맞게 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="89736-230">This aligns with the <xref:System.DateTime> implementation, which is limited to this resolution.</span></span>
