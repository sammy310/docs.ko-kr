---
title: System.Text.Json을 사용하여 사용자 지정 직렬 변환기 및 역직렬 변환기를 작성하는 방법
description: System.Text.Json 네임스페이스를 사용하여 JSON용 사용자 지정 직렬 변환기 및 역직렬 변환기를 작성하는 방법을 알아봅니다.
ms.date: 11/30/2020
no-loc:
- System.Text.Json
- Newtonsoft.Json
helpviewer_keywords:
- JSON serialization
- serializing objects
- serialization
- objects, serializing
ms.openlocfilehash: a01d3c8dd18c114ea1c3aabc402bc841a6025ffe
ms.sourcegitcommit: 721c3e4bdbb1ea0bb420818ec944c538fe5c513a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/01/2020
ms.locfileid: "96439860"
---
# <a name="how-to-write-custom-serializers-and-deserializers-with-no-locsystemtextjson"></a><span data-ttu-id="ac935-103">System.Text.Json을 사용하여 사용자 지정 직렬 변환기 및 역직렬 변환기를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="ac935-103">How to write custom serializers and deserializers with System.Text.Json</span></span>

<span data-ttu-id="ac935-104"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName>은 `ReadOnlySpan<byte>` 또는 `ReadOnlySequence<byte>`에서 읽어온 UTF-8 인코딩 JSON 텍스트를 위한 고성능, 저할당, 전달 전용 판독기입니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-104"><xref:System.Text.Json.Utf8JsonReader?displayProperty=fullName> is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>` or `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="ac935-105">`Utf8JsonReader`는 사용자 지정 구문 분석기 및 역직렬 변환기를 빌드하는 데 활용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-105">The `Utf8JsonReader` is a low-level type that can be used to build custom parsers and deserializers.</span></span> <span data-ttu-id="ac935-106"><xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonReader`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-106">The <xref:System.Text.Json.JsonSerializer.Deserialize%2A?displayProperty=nameWithType> method uses `Utf8JsonReader` under the covers.</span></span>

<span data-ttu-id="ac935-107"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName>은 `String`, `Int32` 및 `DateTime`과 같은 일반적인 .NET 형식에서 UTF-8 인코딩 JSON 텍스트를 쓸 수 있는 고성능 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-107"><xref:System.Text.Json.Utf8JsonWriter?displayProperty=fullName> is a high-performance way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="ac935-108">writer는 사용자 지정 직렬 변환기를 빌드하는 데 사용할 수 있는 하위 수준 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-108">The writer is a low-level type that can be used to build custom serializers.</span></span> <span data-ttu-id="ac935-109"><xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> 메서드는 내부적으로 `Utf8JsonWriter`를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-109">The <xref:System.Text.Json.JsonSerializer.Serialize%2A?displayProperty=nameWithType> method uses `Utf8JsonWriter` under the covers.</span></span>

<span data-ttu-id="ac935-110"><xref:System.Text.Json.JsonDocument?displayProperty=fullName>은 `Utf8JsonReader`를 사용하여 읽기 전용 DOM(문서 개체 모델)을 빌드하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-110"><xref:System.Text.Json.JsonDocument?displayProperty=fullName> provides the ability to build a read-only Document Object Model (DOM) by using `Utf8JsonReader`.</span></span> <span data-ttu-id="ac935-111">DOM은 JSON 페이로드의 데이터에 대한 임의 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-111">The DOM provides random access to data in a JSON payload.</span></span> <span data-ttu-id="ac935-112">페이로드를 구성하는 JSON 요소는 <xref:System.Text.Json.JsonElement> 형식을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-112">The JSON elements that compose the payload can be accessed via the <xref:System.Text.Json.JsonElement> type.</span></span> <span data-ttu-id="ac935-113">`JsonElement` 형식은 JSON 텍스트를 일반적인 .NET 형식으로 변환하는 API와 함께 배열 및 개체 열거자를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-113">The `JsonElement` type provides array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="ac935-114">`JsonDocument`는 <xref:System.Text.Json.JsonDocument.RootElement> 속성을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-114">`JsonDocument` exposes a <xref:System.Text.Json.JsonDocument.RootElement> property.</span></span>

<span data-ttu-id="ac935-115">다음 섹션에서는 이러한 도구를 사용하여 JSON을 읽고 쓰는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-115">The following sections show how to use these tools for reading and writing JSON.</span></span>

## <a name="use-jsondocument-for-access-to-data"></a><span data-ttu-id="ac935-116">JsonDocument를 사용하여 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="ac935-116">Use JsonDocument for access to data</span></span>

<span data-ttu-id="ac935-117">다음 예제에서는 <xref:System.Text.Json.JsonDocument> 클래스를 사용하여 JSON 문자열의 데이터에 임의로 액세스하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-117">The following example shows how to use the <xref:System.Text.Json.JsonDocument> class for random access to data in a JSON string:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades1":::

<span data-ttu-id="ac935-118">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="ac935-118">The preceding code:</span></span>

* <span data-ttu-id="ac935-119">분석할 JSON은 `jsonString`이라는 문자열에 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-119">Assumes the JSON to analyze is in a string named `jsonString`.</span></span>
* <span data-ttu-id="ac935-120">`Grade` 속성이 있는 `Students` 배열의 개체에 대한 평균 등급을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-120">Calculates an average grade for objects in a `Students` array that have a `Grade` property.</span></span>
* <span data-ttu-id="ac935-121">등급이 없는 학생에게 기본 등급 70을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-121">Assigns a default grade of 70 for students who don't have a grade.</span></span>
* <span data-ttu-id="ac935-122">반복마다 `count` 변수를 늘려서 학생 수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-122">Counts students by incrementing a `count` variable with each iteration.</span></span> <span data-ttu-id="ac935-123">다음 예제처럼 <xref:System.Text.Json.JsonElement.GetArrayLength%2A>를 호출하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-123">An alternative is to call <xref:System.Text.Json.JsonElement.GetArrayLength%2A>, as shown in the following example:</span></span>

  :::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentDataAccess.cs" id="AverageGrades2":::

<span data-ttu-id="ac935-124">다음은 이 코드가 처리하는 JSON 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-124">Here's an example of the JSON that this code processes:</span></span>

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-jsondocument-to-write-json"></a><span data-ttu-id="ac935-125">JsonDocument를 사용하여 JSON 쓰기</span><span class="sxs-lookup"><span data-stu-id="ac935-125">Use JsonDocument to write JSON</span></span>

<span data-ttu-id="ac935-126">다음 예제에서는 <xref:System.Text.Json.JsonDocument>에서 JSON을 쓰는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-126">The following example shows how to write JSON from a <xref:System.Text.Json.JsonDocument>:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/JsonDocumentWriteJson.cs" id="Serialize":::

<span data-ttu-id="ac935-127">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="ac935-127">The preceding code:</span></span>

* <span data-ttu-id="ac935-128">JSON 파일을 읽고, `JsonDocument`에 데이터를 로드하고, 서식 있는(보기 좋게 출력된) JSON을 파일에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-128">Reads a JSON file, loads the data into a `JsonDocument`, and writes formatted (pretty-printed) JSON to a file.</span></span>
* <span data-ttu-id="ac935-129"><xref:System.Text.Json.JsonDocumentOptions>를 사용하여 입력 JSON의 주석을 허용하지만 무시하도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-129">Uses <xref:System.Text.Json.JsonDocumentOptions> to specify that comments in the input JSON are allowed but ignored.</span></span>
* <span data-ttu-id="ac935-130">완료되면 writer에서 <xref:System.Text.Json.Utf8JsonWriter.Flush%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-130">When finished, calls <xref:System.Text.Json.Utf8JsonWriter.Flush%2A> on the writer.</span></span> <span data-ttu-id="ac935-131">삭제될 때 writer가 자동으로 플러시하도록 설정하는 방법도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-131">An alternative is to let the writer auto-flush when it's disposed.</span></span>

<span data-ttu-id="ac935-132">다음은 예제 코드에서 처리할 JSON 입력의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-132">Here's an example of JSON input to be processed by the example code:</span></span>

:::code language="json" source="snippets/system-text-json-how-to/csharp/Grades.json":::

<span data-ttu-id="ac935-133">결과는 다음과 같이 보기 좋게 출력된 JSON 출력입니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-133">The result is the following pretty-printed JSON output:</span></span>

:::code language="json" source="snippets/system-text-json-how-to/csharp/GradesPrettyPrint.json":::

## <a name="use-utf8jsonwriter"></a><span data-ttu-id="ac935-134">Utf8JsonWriter 사용</span><span class="sxs-lookup"><span data-stu-id="ac935-134">Use Utf8JsonWriter</span></span>

<span data-ttu-id="ac935-135">다음 예제에서는 <xref:System.Text.Json.Utf8JsonWriter> 클래스 사용 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-135">The following example shows how to use the <xref:System.Text.Json.Utf8JsonWriter> class:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8WriterToStream.cs" id="Serialize":::

## <a name="use-utf8jsonreader"></a><span data-ttu-id="ac935-136">Utf8JsonReader 사용</span><span class="sxs-lookup"><span data-stu-id="ac935-136">Use Utf8JsonReader</span></span>

<span data-ttu-id="ac935-137">다음 예제에서는 <xref:System.Text.Json.Utf8JsonReader> 클래스 사용 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-137">The following example shows how to use the <xref:System.Text.Json.Utf8JsonReader> class:</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromBytes.cs" id="Deserialize":::

<span data-ttu-id="ac935-138">위의 코드는 `jsonUtf8` 변수가 UTF-8로 인코딩된 유효한 JSON을 포함하는 바이트 배열이라고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-138">The preceding code assumes that the `jsonUtf8` variable is a byte array that contains valid JSON, encoded as UTF-8.</span></span>

### <a name="filter-data-using-utf8jsonreader"></a><span data-ttu-id="ac935-139">Utf8JsonReader를 사용하여 데이터 필터링</span><span class="sxs-lookup"><span data-stu-id="ac935-139">Filter data using Utf8JsonReader</span></span>

<span data-ttu-id="ac935-140">다음 예제는 파일을 동기적으로 읽고 값을 검색하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-140">The following example shows how to synchronously read a file, and search for a value.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderFromFile.cs":::

<span data-ttu-id="ac935-141">이 예제의 비동기 버전은 [.NET 샘플 JSON 프로젝트](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ac935-141">For an asynchronous version of this example, see [.NET samples JSON project](https://github.com/dotnet/samples/blob/18e31a5f1abd4f347bf96bfdc3e40e2cfb36e319/core/json/Program.cs).</span></span>

<span data-ttu-id="ac935-142">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="ac935-142">The preceding code:</span></span>

* <span data-ttu-id="ac935-143">JSON에 개체 배열이 포함되고 각 개체에 문자열 형식의 "name" 속성이 포함될 수 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-143">Assumes the JSON contains an array of objects and each object may contain a "name" property of type string.</span></span>
* <span data-ttu-id="ac935-144">"대학교"로 끝나는 개체 및 "이름" 속성 값의 개수를 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-144">Counts objects and "name" property values that end with "University".</span></span>
* <span data-ttu-id="ac935-145">파일이 UTF-16으로 인코딩되고 UTF-8로 코드 변환된다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-145">Assumes the file is encoded as UTF-16 and transcodes it into UTF-8.</span></span> <span data-ttu-id="ac935-146">UTF-8로 인코딩된 파일은 다음 코드를 사용하여 `ReadOnlySpan<byte>`로 직접 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-146">A file encoded as UTF-8 can be read directly into a `ReadOnlySpan<byte>`, by using the following code:</span></span>

  ```csharp
  ReadOnlySpan<byte> jsonReadOnlySpan = File.ReadAllBytes(fileName);
  ```

  <span data-ttu-id="ac935-147">파일에 UTF-8 BOM(바이트 순서 표시)이 포함된 경우 제거한 후 바이트를 `Utf8JsonReader`에 전달해야 합니다. 판독기에는 텍스트가 필요하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-147">If the file contains a UTF-8 byte order mark (BOM), remove it before passing the bytes to the `Utf8JsonReader`, since the reader expects text.</span></span> <span data-ttu-id="ac935-148">그렇지 않으면 BOM은 잘못된 JSON으로 간주되고, 판독기에서 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-148">Otherwise, the BOM is considered invalid JSON, and the reader throws an exception.</span></span>

<span data-ttu-id="ac935-149">다음은 위의 코드에서 읽을 수 있는 JSON 샘플입니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-149">Here's a JSON sample that the preceding code can read.</span></span> <span data-ttu-id="ac935-150">다음과 같이 "4개 이름 중 2개가 '대학교'로 끝나는 이름"이라는 결과 요약 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-150">The resulting summary message is "2 out of 4 have names that end with 'University'":</span></span>

:::code language="json" source="snippets/system-text-json-how-to/csharp/Universities.json":::

### <a name="read-from-a-stream-using-utf8jsonreader"></a><span data-ttu-id="ac935-151">Utf8JsonReader를 사용하여 스트림에서 읽기</span><span class="sxs-lookup"><span data-stu-id="ac935-151">Read from a stream using Utf8JsonReader</span></span>

<span data-ttu-id="ac935-152">큰 파일(예: 기가바이트 이상 크기)을 읽을 때 전체 파일을 한 번에 메모리에 로드하지 않아도 되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-152">When reading a large file (a gigabyte or more in size, for example), you might want to avoid having to load the entire file into memory at once.</span></span> <span data-ttu-id="ac935-153">이 시나리오에서는 <xref:System.IO.FileStream>을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-153">For this scenario, you can use a <xref:System.IO.FileStream>.</span></span>

<span data-ttu-id="ac935-154">`Utf8JsonReader`를 사용하여 스트림에서 읽는 경우 다음 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-154">When using the `Utf8JsonReader` to read from a stream, the following rules apply:</span></span>

* <span data-ttu-id="ac935-155">부분 JSON 페이로드를 포함하는 버퍼는 판독기가 진행할 수 있도록 최소한 그 안에 있는 가장 큰 JSON 토큰만큼 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-155">The buffer containing the partial JSON payload must be at least as large as the largest JSON token within it so that the reader can make forward progress.</span></span>
* <span data-ttu-id="ac935-156">버퍼는 최소한 JSON 내에서 가장 큰 공백 시퀀스만큼 커야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-156">The buffer must be at least as large as the largest sequence of white space within the JSON.</span></span>
* <span data-ttu-id="ac935-157">판독기는 JSON 페이로드의 다음 <xref:System.Text.Json.Utf8JsonReader.TokenType%2A>을 완전히 읽을 때까지는 읽은 데이터를 추적하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-157">The reader doesn't keep track of the data it has read until it completely reads the next <xref:System.Text.Json.Utf8JsonReader.TokenType%2A> in the JSON payload.</span></span> <span data-ttu-id="ac935-158">따라서 버퍼에 바이트가 남아 있으면 판독기에 다시 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-158">So when there are bytes left over in the buffer, you have to pass them to the reader again.</span></span> <span data-ttu-id="ac935-159"><xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A>를 사용하여 남은 바이트 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-159">You can use <xref:System.Text.Json.Utf8JsonReader.BytesConsumed%2A> to determine how many bytes are left over.</span></span>

<span data-ttu-id="ac935-160">다음 코드에서는 스트림에서 읽는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-160">The following code illustrates how to read from a stream.</span></span> <span data-ttu-id="ac935-161">이 예제에서는 <xref:System.IO.MemoryStream>을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-161">The example shows a <xref:System.IO.MemoryStream>.</span></span> <span data-ttu-id="ac935-162">`FileStream`이 시작 시 UTF-8 BOM을 포함하는 경우를 제외하고는 <xref:System.IO.FileStream>에서 비슷한 코드가 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-162">Similar code will work with a <xref:System.IO.FileStream>, except when the `FileStream` contains a UTF-8 BOM at the start.</span></span> <span data-ttu-id="ac935-163">이 경우 남은 바이트를 `Utf8JsonReader`에 전달하기 전에 버퍼에서 3바이트를 제거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-163">In that case, you need to strip those three bytes from the buffer before passing the remaining bytes to the `Utf8JsonReader`.</span></span> <span data-ttu-id="ac935-164">그렇지 않으면 BOM이 JSON의 유효한 부분으로 간주되지 않으므로 판독기가 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-164">Otherwise the reader would throw an exception, since the BOM is not considered a valid part of the JSON.</span></span>

<span data-ttu-id="ac935-165">이 샘플 코드는 4KB 버퍼로 시작하며 크기가 작아 전체 JSON 토큰을 수용할 수 없을 때마다 버퍼 크기를 두 배로 늘립니다. 이는 판독기가 JSON 페이로드에 대한 작업을 진행하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-165">The sample code starts with a 4KB buffer and doubles the buffer size each time it finds that the size is not large enough to fit a complete JSON token, which is required for the reader to make forward progress on the JSON payload.</span></span> <span data-ttu-id="ac935-166">이 코드 조각에 제공된 JSON 샘플은 10바이트와 같이 매우 작은 초기 버퍼 크기를 설정하는 경우에만 버퍼 크기 증가를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-166">The JSON sample provided in the snippet triggers a buffer size increase only if you set a very small initial buffer size, for example, 10 bytes.</span></span> <span data-ttu-id="ac935-167">초기 버퍼 크기를 10으로 설정하는 경우 `Console.WriteLine` 문은 버퍼 크기 증가의 원인과 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-167">If you set the initial buffer size to 10, the `Console.WriteLine` statements illustrate the cause and effect of buffer size increases.</span></span> <span data-ttu-id="ac935-168">4KB 초기 버퍼 크기에서 전체 샘플 JSON은 각 `Console.WriteLine`마다 표시되며 버퍼 크기를 늘릴 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-168">At the 4KB initial buffer size, the entire sample JSON is shown by each `Console.WriteLine`, and the buffer size never has to be increased.</span></span>

:::code language="csharp" source="snippets/system-text-json-how-to/csharp/Utf8ReaderPartialRead.cs":::

<span data-ttu-id="ac935-169">앞의 예제에서는 버퍼 크기를 늘릴 수 있는 크기 제한을 설정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-169">The preceding example sets no limit to how large the buffer can grow.</span></span> <span data-ttu-id="ac935-170">토큰 크기가 너무 클 경우 코드는 <xref:System.OutOfMemoryException> 예외와 함께 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-170">If the token size is too large, the code could fail with an <xref:System.OutOfMemoryException> exception.</span></span> <span data-ttu-id="ac935-171">이 문제는 JSON이 크기가 약 1GB 이상인 토큰을 포함하는 경우 발생할 수 있습니다. 1GB 크기가 두 배가 되면 `int32` 버퍼에 비해 너무 커지기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="ac935-171">This can happen if the JSON contains a token that is around 1 GB or more in size, because doubling the 1 GB size results in a size that is too large to fit into an `int32` buffer.</span></span>

## <a name="see-also"></a><span data-ttu-id="ac935-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ac935-172">See also</span></span>

* [<span data-ttu-id="ac935-173">System.Text.Json 개요</span><span class="sxs-lookup"><span data-stu-id="ac935-173">System.Text.Json overview</span></span>](system-text-json-overview.md)
* [<span data-ttu-id="ac935-174">문자 인코딩을 사용자 지정하는 방법</span><span class="sxs-lookup"><span data-stu-id="ac935-174">How to customize character encoding</span></span>](system-text-json-character-encoding.md)
* [<span data-ttu-id="ac935-175">JSON 직렬화용 사용자 지정 변환기를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="ac935-175">How to write custom converters for JSON serialization</span></span>](system-text-json-converters-how-to.md)
* <span data-ttu-id="ac935-176">[System.Text.Json API 참조](xref:System.Text.Json)</span><span class="sxs-lookup"><span data-stu-id="ac935-176">[System.Text.Json API reference](xref:System.Text.Json)</span></span>
