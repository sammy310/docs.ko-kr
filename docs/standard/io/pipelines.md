---
title: I/O 파이프라인 - .NET
description: .NET에서 I/O 파이프라인을 효율적으로 사용하고 코드에서 문제를 방지하는 방법에 대해 알아봅니다.
ms.date: 08/27/2020
helpviewer_keywords:
- Pipelines
- Pipelines I/O
- I/O [.NET], Pipelines
author: rick-anderson
ms.author: riande
ms.openlocfilehash: 508ae0e2b854f81ee639a63063a8f6d73ae84863
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94830638"
---
# <a name="systemiopipelines-in-net"></a><span data-ttu-id="41705-103">.NET의 System.IO.Pipelines</span><span class="sxs-lookup"><span data-stu-id="41705-103">System.IO.Pipelines in .NET</span></span>

<span data-ttu-id="41705-104"><xref:System.IO.Pipelines>는 .NET에서 고성능 I/O를 더 쉽게 수행할 수 있도록 설계된 새 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-104"><xref:System.IO.Pipelines> is a new library that is designed to make it easier to do high-performance I/O in .NET.</span></span> <span data-ttu-id="41705-105">.NET Standard를 대상으로 하며 모든 .NET 구현에서 작동하는 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-105">It's a library targeting .NET Standard that works on all .NET implementations.</span></span>

<a name="solve"></a>

## <a name="what-problem-does-systemiopipelines-solve"></a><span data-ttu-id="41705-106">System.IO.Pipelines이 해결하는 문제</span><span class="sxs-lookup"><span data-stu-id="41705-106">What problem does System.IO.Pipelines solve</span></span>

<!-- corner case doesn't MT (machine translate)   -->
<span data-ttu-id="41705-107">스트리밍 데이터를 구문 분석하는 앱은 특수하고 비정상적인 코드 흐름이 많은 상용구 코드로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-107">Apps that parse streaming data are composed of boilerplate code having many specialized and unusual code flows.</span></span> <span data-ttu-id="41705-108">상용구와 특수 사례 코드는 복잡하고 유지관리가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-108">The boilerplate and special case code is complex and difficult to maintain.</span></span>

<span data-ttu-id="41705-109">`System.IO.Pipelines`는 다음을 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-109">`System.IO.Pipelines` was architected to:</span></span>

* <span data-ttu-id="41705-110">고성능 스트리밍 데이터 구문 분석 수행</span><span class="sxs-lookup"><span data-stu-id="41705-110">Have high performance parsing streaming data.</span></span>
* <span data-ttu-id="41705-111">코드 복잡성 감소</span><span class="sxs-lookup"><span data-stu-id="41705-111">Reduce code complexity.</span></span>

<span data-ttu-id="41705-112">다음 코드는 클라이언트에서 줄로 구분된 메시지를 수신하는 TCP 서버(`'\n'`으로 구분됨)에서 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-112">The following code is typical for a TCP server that receives line-delimited messages (delimited by `'\n'`) from a client:</span></span>

```csharp
async Task ProcessLinesAsync(NetworkStream stream)
{
    var buffer = new byte[1024];
    await stream.ReadAsync(buffer, 0, buffer.Length);

    // Process a single line from the buffer
    ProcessLine(buffer);
}
```

<span data-ttu-id="41705-113">위의 코드에는 몇 가지 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-113">The preceding code has several problems:</span></span>

* <span data-ttu-id="41705-114">`ReadAsync`에 대한 단일 호출에서 전체 메시지(줄의 끝)를 수신하지 못할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-114">The entire message (end of line) might not be received in a single call to `ReadAsync`.</span></span>
* <span data-ttu-id="41705-115">`stream.ReadAsync`의 결과를 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-115">It's ignoring the result of `stream.ReadAsync`.</span></span> <span data-ttu-id="41705-116">`stream.ReadAsync`가 읽은 데이터의 양을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-116">`stream.ReadAsync` returns how much data was read.</span></span>
* <span data-ttu-id="41705-117">단일 `ReadAsync` 호출에서 여러 줄을 읽는 경우를 처리하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-117">It doesn't handle the case where multiple lines are read in a single `ReadAsync` call.</span></span>
* <span data-ttu-id="41705-118">각 읽기에 `byte` 배열을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-118">It allocates a `byte` array with each read.</span></span>

<span data-ttu-id="41705-119">위의 문제를 해결하려면 다음과 같이 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-119">To fix the preceding problems, the following changes are required:</span></span>

* <span data-ttu-id="41705-120">새 줄을 찾을 때까지 들어오는 데이터를 버퍼링합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-120">Buffer the incoming data until a new line is found.</span></span>
* <span data-ttu-id="41705-121">버퍼에 반환된 모든 줄을 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-121">Parse all the lines returned in the buffer.</span></span>
* <span data-ttu-id="41705-122">줄이 1KB(1024바이트)보다 클 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-122">It's possible that the line is bigger than 1 KB (1024 bytes).</span></span> <span data-ttu-id="41705-123">버퍼 내부의 전체 줄을 맞추려면 구분 기호를 찾을 때까지 코드에서 입력 버퍼의 크기를 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-123">The code needs to resize the input buffer until the delimiter is found in order to fit the complete line inside the buffer.</span></span>

  * <span data-ttu-id="41705-124">버퍼 크기를 조정하는 경우 입력에 더 긴 줄이 표시되면 더 많은 버퍼 복사본이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-124">If the buffer is resized, more buffer copies are made as longer lines appear in the input.</span></span>
  * <span data-ttu-id="41705-125">불필요한 공간을 줄이려면 줄 읽기에 사용되는 버퍼를 압축합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-125">To reduce wasted space, compact the buffer used for reading lines.</span></span>

* <span data-ttu-id="41705-126">메모리를 반복해서 할당하지 않도록 버퍼 풀링을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-126">Consider using buffer pooling to avoid allocating memory repeatedly.</span></span>
* <span data-ttu-id="41705-127">다음 코드는 이러한 문제 중 일부를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-127">The following code addresses some of these problems:</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ProcessLinesAsync.cs" id="snippet":::

<span data-ttu-id="41705-128">이전 코드는 복잡하며, 식별된 모든 문제를 해결하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-128">The previous code is complex and doesn't address all the problems identified.</span></span> <span data-ttu-id="41705-129">고성능 네트워킹은 일반적으로 성능을 최대화하는 매우 복잡한 코드를 작성하는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-129">High-performance networking usually means writing very complex code to maximize performance.</span></span> <span data-ttu-id="41705-130">`System.IO.Pipelines`는 이러한 종류의 코드 작성을 더 쉽게 만들기 위해 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-130">`System.IO.Pipelines` was designed to make writing this type of code easier.</span></span>

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

## <a name="pipe"></a><span data-ttu-id="41705-131">파이프</span><span class="sxs-lookup"><span data-stu-id="41705-131">Pipe</span></span>

<span data-ttu-id="41705-132"><xref:System.IO.Pipelines.Pipe> 클래스를 사용하여 `PipeWriter/PipeReader` 쌍을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-132">The <xref:System.IO.Pipelines.Pipe> class can be used to create a `PipeWriter/PipeReader` pair.</span></span> <span data-ttu-id="41705-133">`PipeWriter`에 작성된 모든 데이터는 `PipeReader`에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-133">All data written into the `PipeWriter` is available in the `PipeReader`:</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet2":::

<a name="pbu"></a>

### <a name="pipe-basic-usage"></a><span data-ttu-id="41705-134">파이프 기본 사용 방법</span><span class="sxs-lookup"><span data-stu-id="41705-134">Pipe basic usage</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Pipe.cs" id="snippet":::

<span data-ttu-id="41705-135">두 가지 루프가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-135">There are two loops:</span></span>

* <span data-ttu-id="41705-136">`FillPipeAsync`는 `Socket`에서 읽고 `PipeWriter`에 씁니다.</span><span class="sxs-lookup"><span data-stu-id="41705-136">`FillPipeAsync` reads from the `Socket` and writes to the `PipeWriter`.</span></span>
* <span data-ttu-id="41705-137">`ReadPipeAsync`는 `PipeReader`에서 읽고 들어오는 줄을 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-137">`ReadPipeAsync` reads from the `PipeReader` and parses incoming lines.</span></span>

<span data-ttu-id="41705-138">할당된 명시적 버퍼가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-138">There are no explicit buffers allocated.</span></span> <span data-ttu-id="41705-139">모든 버퍼 관리는 `PipeReader` 및 `PipeWriter` 구현에 위임됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-139">All buffer management is delegated to the `PipeReader` and `PipeWriter` implementations.</span></span> <span data-ttu-id="41705-140">버퍼 관리를 위임하면 더 쉽게 코드 사용을 비즈니스 논리에만 집중할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-140">Delegating buffer management makes it easier for consuming code to focus solely on the business logic.</span></span>

<span data-ttu-id="41705-141">첫 번째 루프에서 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-141">In the first loop:</span></span>

* <span data-ttu-id="41705-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType>는 기본 작성기에서 메모리를 가져오기 위해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-142"><xref:System.IO.Pipelines.PipeWriter.GetMemory(System.Int32)?displayProperty=nameWithType> is called to get memory from the underlying writer.</span></span>
* <span data-ttu-id="41705-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType>는 버퍼에 기록된 데이터의 양을 `PipeWriter`에 알리기 위해 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-143"><xref:System.IO.Pipelines.PipeWriter.Advance(System.Int32)?displayProperty=nameWithType> is called to tell the `PipeWriter` how much data was written to the buffer.</span></span>
* <span data-ttu-id="41705-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>는 `PipeReader`에서 데이터를 사용할 수 있도록 호출됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-144"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType> is called to make the data available to the `PipeReader`.</span></span>

<span data-ttu-id="41705-145">두 번째 루프에서 `PipeReader`는 `PipeWriter`로 작성된 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-145">In the second loop, the `PipeReader` consumes the buffers written by `PipeWriter`.</span></span> <span data-ttu-id="41705-146">버퍼는 소켓에서 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="41705-146">The buffers come from the socket.</span></span> <span data-ttu-id="41705-147">`PipeReader.ReadAsync`에 대한 호출:</span><span class="sxs-lookup"><span data-stu-id="41705-147">The call to `PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="41705-148">두 가지 중요 한 정보를 포함하는 <xref:System.IO.Pipelines.ReadResult>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-148">Returns a <xref:System.IO.Pipelines.ReadResult> that contains two important pieces of information:</span></span>

  * <span data-ttu-id="41705-149">`ReadOnlySequence<byte>` 형식으로 읽은 데이터입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-149">The data that was read in the form of `ReadOnlySequence<byte>`.</span></span>
  * <span data-ttu-id="41705-150">EOF(데이터의 끝)에 도달했는지 여부를 나타내는 부울 `IsCompleted`입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-150">A boolean `IsCompleted` that indicates if the end of data (EOF) has been reached.</span></span>

<span data-ttu-id="41705-151">EOL(줄의 끝) 구분 기호를 찾은 후 줄을 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-151">After finding the end of line (EOL) delimiter and parsing the line:</span></span>

* <span data-ttu-id="41705-152">논리는 버퍼를 처리하여 이미 처리된 작업을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="41705-152">The logic processes the buffer to skip what's already processed.</span></span>
* <span data-ttu-id="41705-153">`PipeReader.AdvanceTo`를 호출하여 사용되고 검사된 데이터의 양을 `PipeReader`에 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="41705-153">`PipeReader.AdvanceTo` is called to tell the `PipeReader` how much data has been consumed and examined.</span></span>

<span data-ttu-id="41705-154">판독기 및 작성기 루프는 `Complete`를 호출하여 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-154">The reader and writer loops end by calling `Complete`.</span></span> <span data-ttu-id="41705-155">`Complete`는 기본 파이프가 할당된 메모리를 해제하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-155">`Complete` lets the underlying Pipe release the memory it allocated.</span></span>

### <a name="backpressure-and-flow-control"></a><span data-ttu-id="41705-156">역 압력 및 흐름 제어</span><span class="sxs-lookup"><span data-stu-id="41705-156">Backpressure and flow control</span></span>

<span data-ttu-id="41705-157">다음과 같이 읽기와 구문 분석이 함께 작동하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-157">Ideally, reading and parsing work together:</span></span>

* <span data-ttu-id="41705-158">쓰기 스레드는 네트워크의 데이터를 사용하며 이를 버퍼에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-158">The writing thread consumes data from the network and puts it in buffers.</span></span>
* <span data-ttu-id="41705-159">구문 분석 스레드는 적절한 데이터 구조를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-159">The parsing thread is responsible for constructing the appropriate data structures.</span></span>

<span data-ttu-id="41705-160">일반적으로 다음과 같은 이유로 인해 구문 분석에는 네트워크에서 데이터 블록을 복사하는 것보다 시간이 더 걸립니다.</span><span class="sxs-lookup"><span data-stu-id="41705-160">Typically, parsing takes more time than just copying blocks of data from the network:</span></span>

* <span data-ttu-id="41705-161">읽기 스레드가 구문 분석 스레드 앞에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-161">The reading thread gets ahead of the parsing thread.</span></span>
* <span data-ttu-id="41705-162">읽기 스레드의 속도가 느려야 하거나 구문 분석 스레드에 대한 데이터를 저장하기 위해 더 많은 메모리를 할당해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-162">The reading thread has to either slow down or allocate more memory to store the data for the parsing thread.</span></span>

<span data-ttu-id="41705-163">성능을 최적화하기 위해 잦은 일시 중지와 더 많은 메모리 할당 사이에서 균형을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-163">For optimal performance, there's a balance between frequent pauses and allocating more memory.</span></span>

<span data-ttu-id="41705-164">위의 문제를 해결하기 위해 `Pipe`에는 데이터 흐름을 제어하는 두 가지 설정이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-164">To solve the preceding problem, the `Pipe` has two settings to control the flow of data:</span></span>

* <span data-ttu-id="41705-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> 일시 중지를 호출하기 전에 버퍼링되어야 하는 데이터의 양을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-165"><xref:System.IO.Pipelines.PipeOptions.PauseWriterThreshold>: Determines how much data should be buffered before calls to <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> pause.</span></span>
* <span data-ttu-id="41705-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: `PipeWriter.FlushAsync` 호출을 다시 시작하기 전에 판독기가 관찰해야 하는 데이터의 양을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-166"><xref:System.IO.Pipelines.PipeOptions.ResumeWriterThreshold>: Determines how much data the reader has to observe before calls to `PipeWriter.FlushAsync` resume.</span></span>

![ResumeWriterThreshold 및PauseWriterThreshold의 다이어그램](media/pipelines/resume-pause.png)

<span data-ttu-id="41705-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="41705-168"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="41705-169">`Pipe`의 데이터 크기가 `PauseWriterThreshold`를 넘으면 불완전한 `ValueTask<FlushResult>`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-169">Returns an incomplete `ValueTask<FlushResult>` when the amount of data in the `Pipe` crosses `PauseWriterThreshold`.</span></span>
* <span data-ttu-id="41705-170">`ResumeWriterThreshold`보다 작으면 `ValueTask<FlushResult>`가 완료됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-170">Completes `ValueTask<FlushResult>` when it becomes lower than `ResumeWriterThreshold`.</span></span>

<span data-ttu-id="41705-171">하나의 값이 사용될 경우 발생할 수 있는 빠른 순환을 방지하기 위해 두 값이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-171">Two values are used to prevent rapid cycling, which can occur if one value is used.</span></span>

### <a name="examples"></a><span data-ttu-id="41705-172">예</span><span class="sxs-lookup"><span data-stu-id="41705-172">Examples</span></span>

```csharp
// The Pipe will start returning incomplete tasks from FlushAsync until
// the reader examines at least 5 bytes.
var options = new PipeOptions(pauseWriterThreshold: 10, resumeWriterThreshold: 5);
var pipe = new Pipe(options);
```

### <a name="pipescheduler"></a><span data-ttu-id="41705-173">PipeScheduler</span><span class="sxs-lookup"><span data-stu-id="41705-173">PipeScheduler</span></span>

<span data-ttu-id="41705-174">일반적으로 `async` 및 `await`를 사용하는 경우 비동기 코드는 <xref:System.Threading.Tasks.TaskScheduler> 또는 현재 <xref:System.Threading.SynchronizationContext>에서 다시 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-174">Typically when using `async` and `await`, asynchronous code resumes on either on a <xref:System.Threading.Tasks.TaskScheduler> or on the current <xref:System.Threading.SynchronizationContext>.</span></span>

<span data-ttu-id="41705-175">I/O를 수행하는 경우 I/O가 수행되는 위치를 세부적으로 제어하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-175">When doing I/O, it's important to have fine-grained control over where the I/O is performed.</span></span> <span data-ttu-id="41705-176">이 컨트롤을 사용하면 CPU 캐시를 효과적으로 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-176">This control allows taking advantage of CPU caches effectively.</span></span> <span data-ttu-id="41705-177">효율적인 캐싱은 웹 서버와 같은 고성능 앱에 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-177">Efficient caching is critical for high-performance apps like web servers.</span></span> <span data-ttu-id="41705-178"><xref:System.IO.Pipelines.PipeScheduler>는 비동기 콜백이 실행되는 위치에 대한 제어를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-178"><xref:System.IO.Pipelines.PipeScheduler> provides control over where asynchronous callbacks run.</span></span> <span data-ttu-id="41705-179">기본적으로 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-179">By default:</span></span>

* <span data-ttu-id="41705-180">현재 <xref:System.Threading.SynchronizationContext>가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-180">The current <xref:System.Threading.SynchronizationContext> is used.</span></span>
* <span data-ttu-id="41705-181">`SynchronizationContext`가 없으면 스레드 풀을 사용하여 콜백을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-181">If there's no `SynchronizationContext`, it uses the thread pool to run callbacks.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/Program.cs" id="snippet":::

<span data-ttu-id="41705-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool)은 스레드 풀에 대한 콜백을 큐에 대기시키는 <xref:System.IO.Pipelines.PipeScheduler> 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-182">[PipeScheduler.ThreadPool](xref:System.IO.Pipelines.PipeScheduler.ThreadPool) is the <xref:System.IO.Pipelines.PipeScheduler> implementation that queues callbacks to the thread pool.</span></span> <span data-ttu-id="41705-183">`PipeScheduler.ThreadPool`은 기본값이며 일반적으로 최상의 선택입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-183">`PipeScheduler.ThreadPool` is the default and generally the best choice.</span></span> <span data-ttu-id="41705-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline)은 교착 상태와 같은 의도하지 않은 결과를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-184">[PipeScheduler.Inline](xref:System.IO.Pipelines.PipeScheduler.Inline) can cause unintended consequences such as deadlocks.</span></span>

### <a name="pipe-reset"></a><span data-ttu-id="41705-185">파이프 다시 설정</span><span class="sxs-lookup"><span data-stu-id="41705-185">Pipe reset</span></span>

<span data-ttu-id="41705-186">`Pipe` 개체를 다시 사용하는 것이 효율적인 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-186">It's frequently efficient to reuse the `Pipe` object.</span></span> <span data-ttu-id="41705-187">파이프를 다시 설정하려면 `PipeReader`와 `PipeWriter`가 모두 완료될 때 <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A>을 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-187">To reset the pipe, call <xref:System.IO.Pipelines.PipeReader> <xref:System.IO.Pipelines.Pipe.Reset%2A> when both the `PipeReader` and `PipeWriter` are complete.</span></span>

## <a name="pipereader"></a><span data-ttu-id="41705-188">PipeReader</span><span class="sxs-lookup"><span data-stu-id="41705-188">PipeReader</span></span>

<span data-ttu-id="41705-189"><xref:System.IO.Pipelines.PipeReader>는 호출자를 대신하여 메모리를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-189"><xref:System.IO.Pipelines.PipeReader> manages memory on the caller's behalf.</span></span> <span data-ttu-id="41705-190">**항상**<xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>를 호출한 후 <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-190">**Always** call <xref:System.IO.Pipelines.PipeReader.AdvanceTo%2A?displayProperty=nameWithType> after calling <xref:System.IO.Pipelines.PipeReader.ReadAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="41705-191">이를 통해 `PipeReader`는 호출자가 메모리를 작업을 완료하는 시기를 알 수 있어서 메모리를 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-191">This lets the `PipeReader` know when the caller is done with the memory so that it can be tracked.</span></span> <span data-ttu-id="41705-192">`PipeReader.ReadAsync`에서 반환된 `ReadOnlySequence<byte>`는 `PipeReader.AdvanceTo`를 호출할 때까지만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-192">The `ReadOnlySequence<byte>` returned from `PipeReader.ReadAsync` is only valid until the call the `PipeReader.AdvanceTo`.</span></span> <span data-ttu-id="41705-193">`PipeReader.AdvanceTo`를 호출한 후에는 `ReadOnlySequence<byte>`를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-193">It's illegal to use `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo`.</span></span>

<span data-ttu-id="41705-194">`PipeReader.AdvanceTo`는 두 개의 <xref:System.SequencePosition> 인수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-194">`PipeReader.AdvanceTo` takes two <xref:System.SequencePosition> arguments:</span></span>

* <span data-ttu-id="41705-195">첫 번째 인수는 사용된 메모리의 양을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-195">The first argument determines how much memory was consumed.</span></span>
* <span data-ttu-id="41705-196">두 번째 인수는 관찰된 버퍼의 양을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-196">The second argument determines how much of the buffer was observed.</span></span>

<span data-ttu-id="41705-197">데이터를 사용됨으로 표시하면 파이프가 메모리를 기본 버퍼 풀로 반환할 수 있다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-197">Marking data as consumed means that the pipe can return the memory to the underlying buffer pool.</span></span> <span data-ttu-id="41705-198">데이터를 관찰됨으로 표시하면 `PipeReader.ReadAsync`에 대한 다음 호출의 수행 내용을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-198">Marking data as observed controls what the next call to `PipeReader.ReadAsync` does.</span></span> <span data-ttu-id="41705-199">모든 항목을 관찰됨으로 표시하면 파이프에 더 많은 데이터를 쓸 때까지 `PipeReader.ReadAsync`에 대한 다음 호출이 반환되지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-199">Marking everything as observed means that the next call to `PipeReader.ReadAsync` won't return until there's more data written to the pipe.</span></span> <span data-ttu-id="41705-200">다른 모든 값을 사용하면 `PipeReader.ReadAsync`에 대한 다음 호출이 관찰된 데이터 ‘및’ 관찰되지 않은 데이터로 즉시 반환되지만 이미 사용된 데이터는 반환되지 않습니다. </span><span class="sxs-lookup"><span data-stu-id="41705-200">Any other value will make the next call to `PipeReader.ReadAsync` return immediately with the observed *and* unobserved data, but not data that has already been consumed.</span></span>

### <a name="read-streaming-data-scenarios"></a><span data-ttu-id="41705-201">스트리밍 데이터 읽기 시나리오</span><span class="sxs-lookup"><span data-stu-id="41705-201">Read streaming data scenarios</span></span>

<span data-ttu-id="41705-202">스트리밍 데이터를 읽으려고 할 때 나타나는 몇 가지 일반적인 패턴은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-202">There are a couple of typical patterns that emerge when trying to read streaming data:</span></span>

* <span data-ttu-id="41705-203">데이터 스트림이 지정된 경우 단일 메시지를 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-203">Given a stream of data, parse a single message.</span></span>
* <span data-ttu-id="41705-204">데이터 스트림이 지정된 경우 사용 가능한 모든 메시지를 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-204">Given a stream of data, parse all available messages.</span></span>

<span data-ttu-id="41705-205">다음 예에서는 `ReadOnlySequence<byte>`의 메시지를 구문 분석하는 데 `TryParseMessage` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-205">The following examples use the `TryParseMessage` method for parsing messages from a `ReadOnlySequence<byte>`.</span></span> <span data-ttu-id="41705-206">`TryParseMessage`는 단일 메시지를 구문 분석하고 입력 버퍼를 업데이트하여 버퍼에서 구문 분석된 메시지를 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="41705-206">`TryParseMessage` parses a single message and update the input buffer to trim the parsed message from the buffer.</span></span> <span data-ttu-id="41705-207">`TryParseMessage`는 .NET의 일부가 아니므로 다음 섹션에서 사용되는 사용자 작성 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-207">`TryParseMessage` is not part of .NET, it's a user written method used in the following sections.</span></span>

```csharp
bool TryParseMessage(ref ReadOnlySequence<byte> buffer, out Message message);
```

### <a name="read-a-single-message"></a><span data-ttu-id="41705-208">단일 메시지 읽기</span><span class="sxs-lookup"><span data-stu-id="41705-208">Read a single message</span></span>

<span data-ttu-id="41705-209">다음 코드는 `PipeReader`에서 단일 메시지를 읽고 호출자에게 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-209">The following code reads a single message from a `PipeReader` and returns it to the caller.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/ReadSingleMsg.cs" id="snippet":::

<span data-ttu-id="41705-210">위의 코드는</span><span class="sxs-lookup"><span data-stu-id="41705-210">The preceding code:</span></span>

* <span data-ttu-id="41705-211">단일 메시지를 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-211">Parses a single message.</span></span>
* <span data-ttu-id="41705-212">사용된 `SequencePosition`을 업데이트하고 `SequencePosition`을 검사하여 잘린 입력 버퍼의 시작을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="41705-212">Updates the consumed `SequencePosition` and examined `SequencePosition` to point to the start of the trimmed input buffer.</span></span>

<span data-ttu-id="41705-213">`TryParseMessage`는 입력 버퍼에서 구문 분석된 메시지를 제거하므로 두 개의 `SequencePosition` 인수가 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-213">The two `SequencePosition` arguments are updated because `TryParseMessage` removes the parsed message from the input buffer.</span></span> <span data-ttu-id="41705-214">일반적으로 버퍼에서 단일 메시지를 구문 분석할 때 검사된 위치는 다음 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-214">Generally, when parsing a single message from the buffer, the examined position should be one of the following:</span></span>

* <span data-ttu-id="41705-215">메시지 끝</span><span class="sxs-lookup"><span data-stu-id="41705-215">The end of the message.</span></span>
* <span data-ttu-id="41705-216">메시지를 찾을 수 없는 경우 받은 버퍼의 끝</span><span class="sxs-lookup"><span data-stu-id="41705-216">The end of the received buffer if no message was found.</span></span>

<span data-ttu-id="41705-217">단일 메시지 사례에서 오류가 발생할 가능성이 가장 높습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-217">The single message case has the most potential for errors.</span></span> <span data-ttu-id="41705-218">*검사됨* 으로 잘못된 값을 전달하면 메모리 부족 예외 또는 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-218">Passing the wrong values to *examined* can result in an out of memory exception or an infinite loop.</span></span> <span data-ttu-id="41705-219">자세한 내용은 이 문서의 [PipeReader의 일반적인 문제](#gotchas) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="41705-219">For more information, see the [PipeReader common problems](#gotchas) section in this article.</span></span>

### <a name="reading-multiple-messages"></a><span data-ttu-id="41705-220">여러 메시지 읽기</span><span class="sxs-lookup"><span data-stu-id="41705-220">Reading multiple messages</span></span>

<span data-ttu-id="41705-221">다음 코드는 `PipeReader`에서 모든 메시지를 읽고 각각에 대해 `ProcessMessageAsync`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-221">The following code reads all messages from a `PipeReader` and calls `ProcessMessageAsync` on each.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection1.cs" id="snippet":::

### <a name="cancellation"></a><span data-ttu-id="41705-222">취소</span><span class="sxs-lookup"><span data-stu-id="41705-222">Cancellation</span></span>

<span data-ttu-id="41705-223">`PipeReader.ReadAsync`:</span><span class="sxs-lookup"><span data-stu-id="41705-223">`PipeReader.ReadAsync`:</span></span>

* <span data-ttu-id="41705-224"><xref:System.Threading.CancellationToken> 전달을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-224">Supports passing a <xref:System.Threading.CancellationToken>.</span></span>
* <span data-ttu-id="41705-225">읽기 보류 중에 `CancellationToken`이 취소되는 경우 <xref:System.OperationCanceledException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-225">Throws an <xref:System.OperationCanceledException> if the `CancellationToken` is canceled while there's a read pending.</span></span>
* <span data-ttu-id="41705-226"><xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>을 통해 현재 읽기 작업을 취소하는 방법을 지원하여 예외 증가를 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-226">Supports a way to cancel the current read operation via <xref:System.IO.Pipelines.PipeReader.CancelPendingRead%2A?displayProperty=nameWithType>, which avoids raising an exception.</span></span> <span data-ttu-id="41705-227">`PipeReader.CancelPendingRead`를 호출하면 `PipeReader.ReadAsync`에 대한 현재 또는 다음 호출이 `IsCanceled`가 `true`로 설정된 <xref:System.IO.Pipelines.ReadResult>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-227">Calling `PipeReader.CancelPendingRead` causes the current or next call to `PipeReader.ReadAsync` to return a <xref:System.IO.Pipelines.ReadResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="41705-228">이는 기존 읽기 루프를 비파괴적이고 예외 없는 방식으로 중지하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-228">This can be useful for halting the existing read loop in a non-destructive and non-exceptional way.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyConnection.cs" id="snippet":::

<a name="gotchas"></a>

### <a name="pipereader-common-problems"></a><span data-ttu-id="41705-229">PipeReader의 일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="41705-229">PipeReader common problems</span></span>

* <span data-ttu-id="41705-230">`consumed` 또는 `examined`에 잘못된 값을 전달하면 이미 읽은 데이터를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-230">Passing the wrong values to `consumed` or `examined` may result in reading already read data.</span></span>
* <span data-ttu-id="41705-231">`buffer.End`를 검사됨으로 전달하면 다음과 같은 결과를 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-231">Passing `buffer.End` as examined may result in:</span></span>

  * <span data-ttu-id="41705-232">중단된 데이터</span><span class="sxs-lookup"><span data-stu-id="41705-232">Stalled data</span></span>
  * <span data-ttu-id="41705-233">데이터가 사용되지 않는 경우 OOM(메모리 부족) 예외 발생</span><span class="sxs-lookup"><span data-stu-id="41705-233">Possibly an eventual Out of Memory (OOM) exception if data isn't consumed.</span></span> <span data-ttu-id="41705-234">(예: 버퍼에서 한 번에 하나의 메시지를 처리하는 경우 `PipeReader.AdvanceTo(position, buffer.End)`)</span><span class="sxs-lookup"><span data-stu-id="41705-234">For example, `PipeReader.AdvanceTo(position, buffer.End)` when processing a single message at a time from the buffer.</span></span>

* <span data-ttu-id="41705-235">`consumed` 또는 `examined`에 잘못된 값을 전달하면 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-235">Passing the wrong values to `consumed` or `examined` may result in an infinite loop.</span></span> <span data-ttu-id="41705-236">예를 들어 `PipeReader.AdvanceTo(buffer.Start)`는 `buffer.Start`이 변경되지 않은 경우 `PipeReader.ReadAsync`에 대한 다음 호출이 새 데이터가 도착하기 전에 즉시 반환되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-236">For example, `PipeReader.AdvanceTo(buffer.Start)` if `buffer.Start` hasn't changed will cause the next call to `PipeReader.ReadAsync` to return immediately before new data arrives.</span></span>
* <span data-ttu-id="41705-237">`consumed` 또는 `examined`에 잘못된 값을 전달하면 무한 버퍼링(최종 OOM)이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-237">Passing the wrong values to `consumed` or `examined` may result in infinite buffering (eventual OOM).</span></span>
* <span data-ttu-id="41705-238">`PipeReader.AdvanceTo`를 호출한 후 `ReadOnlySequence<byte>`를 사용하면 메모리가 손상될 수 있습니다(사용 가능해진 이후 사용).</span><span class="sxs-lookup"><span data-stu-id="41705-238">Using the `ReadOnlySequence<byte>` after calling `PipeReader.AdvanceTo` may result in memory corruption (use after free).</span></span>
* <span data-ttu-id="41705-239">`PipeReader.Complete/CompleteAsync`를 호출하지 못하면 메모리 누수가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-239">Failing to call `PipeReader.Complete/CompleteAsync` may result in a memory leak.</span></span>
* <span data-ttu-id="41705-240">버퍼를 처리하기 전에 <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType>를 확인하고 읽기 논리를 종료하면 데이터 손실이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-240">Checking <xref:System.IO.Pipelines.ReadResult.IsCompleted?displayProperty=nameWithType> and exiting the reading logic before processing the buffer results in data loss.</span></span> <span data-ttu-id="41705-241">루프 종료 조건은 `ReadResult.Buffer.IsEmpty` 및 `ReadResult.IsCompleted`를 기반으로 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-241">The loop exit condition should be based on `ReadResult.Buffer.IsEmpty` and `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="41705-242">이렇게 하면 무한 루프가 잘못 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-242">Doing this incorrectly could result in an infinite loop.</span></span>

#### <a name="problematic-code"></a><span data-ttu-id="41705-243">문제 코드</span><span class="sxs-lookup"><span data-stu-id="41705-243">Problematic code</span></span>

<span data-ttu-id="41705-244">❌ **데이터 손실**</span><span class="sxs-lookup"><span data-stu-id="41705-244">❌ **Data loss**</span></span>

<span data-ttu-id="41705-245">`IsCompleted`가 `true`로 설정된 경우 `ReadResult`는 최종 데이터 세그먼트를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-245">The `ReadResult` can return the final segment of data when `IsCompleted` is set to `true`.</span></span> <span data-ttu-id="41705-246">읽기 루프를 종료하기 전에 해당 데이터를 읽지 않으면 데이터가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-246">Not reading that data before exiting the read loop will result in data loss.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="41705-247">❌ **무한 루프**</span><span class="sxs-lookup"><span data-stu-id="41705-247">❌ **Infinite loop**</span></span>

<span data-ttu-id="41705-248">`Result.IsCompleted`가 `true`이지만 버퍼에 완전한 메시지가 없는 경우 다음 논리로 인해 무한 루프가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-248">The following logic may result in an infinite loop if the `Result.IsCompleted` is `true` but there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet2":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="41705-249">동일한 문제가 있는 또 다른 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-249">Here's another piece of code with the same problem.</span></span> <span data-ttu-id="41705-250">`ReadResult.IsCompleted`를 확인하기 전에 비어 있지 않은 버퍼를 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-250">It's checking for a non-empty buffer before checking `ReadResult.IsCompleted`.</span></span> <span data-ttu-id="41705-251">`else if`이기 때문에 버퍼에 완전한 메시지가 없는 경우 무한 반복됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-251">Because it's in an `else if`, it will loop forever if there's never a complete message in the buffer.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet3":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="41705-252">❌ **예기치 않은 중단**</span><span class="sxs-lookup"><span data-stu-id="41705-252">❌ **Unexpected Hang**</span></span>

<span data-ttu-id="41705-253">`examined` 위치에서 `buffer.End`를 사용하여 `PipeReader.AdvanceTo`를 무조건 호출하면 단일 메시지를 구문 분석할 때 작동이 중지될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-253">Unconditionally calling `PipeReader.AdvanceTo` with `buffer.End` in the `examined` position may result in hangs when parsing a single message.</span></span> <span data-ttu-id="41705-254">`PipeReader.AdvanceTo`에 대한 다음 호출은 다음까지 반환되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-254">The next call to `PipeReader.AdvanceTo` won't return until:</span></span>

* <span data-ttu-id="41705-255">파이프에 기록된 데이터가 더 있음</span><span class="sxs-lookup"><span data-stu-id="41705-255">There's more data written to the pipe.</span></span>
* <span data-ttu-id="41705-256">새 데이터는 이전에 검사되지 않았음</span><span class="sxs-lookup"><span data-stu-id="41705-256">And the new data wasn't previously examined.</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet4":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="41705-257">❌ **OOM(메모리 부족)**</span><span class="sxs-lookup"><span data-stu-id="41705-257">❌ **Out of Memory (OOM)**</span></span>

<span data-ttu-id="41705-258">다음 조건에서 다음 코드는 <xref:System.OutOfMemoryException>이 발생할 때까지 버퍼링을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-258">With the following conditions, the following code keeps buffering until an <xref:System.OutOfMemoryException> occurs:</span></span>

* <span data-ttu-id="41705-259">최대 메시지 크기가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-259">There's no maximum message size.</span></span>
* <span data-ttu-id="41705-260">`PipeReader`에서 반환된 데이터는 완전한 메시지를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-260">The data returned from the `PipeReader` doesn't make a complete message.</span></span> <span data-ttu-id="41705-261">예를 들어, 다른 쪽에서 매우 용량이 큰 메시지(예: 4GB 메시지)를 작성하기 때문에 완전한 메시지를 생성하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-261">For example, it doesn't make a complete message because the other side is writing a large message (For example, a 4-GB message).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet5":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

<span data-ttu-id="41705-262">❌ **메모리 손상**</span><span class="sxs-lookup"><span data-stu-id="41705-262">❌ **Memory Corruption**</span></span>

<span data-ttu-id="41705-263">버퍼를 읽는 도우미를 작성하는 경우 `Advance`를 호출하기 전에 반환된 모든 페이로드를 복사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-263">When writing helpers that read the buffer, any returned payload should be copied before calling `Advance`.</span></span> <span data-ttu-id="41705-264">다음 예제에서는 `Pipe`가 버렸고 다음 작업(읽기/쓰기)에 다시 사용할 수도 있는 메모리를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-264">The following example will return memory that the `Pipe` has discarded and may reuse it for the next operation (read/write).</span></span>

[!INCLUDE [pipelines-do-not-use-1](../../../includes/pipelines-do-not-use-1.md)]

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippetMessage":::

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/DoNotUse.cs" id="snippet6":::

[!INCLUDE [pipelines-do-not-use-2](../../../includes/pipelines-do-not-use-2.md)]

## <a name="pipewriter"></a><span data-ttu-id="41705-265">PipeWriter</span><span class="sxs-lookup"><span data-stu-id="41705-265">PipeWriter</span></span>

<span data-ttu-id="41705-266"><xref:System.IO.Pipelines.PipeWriter>는 호출자를 대신해 쓰기 위한 버퍼를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-266">The <xref:System.IO.Pipelines.PipeWriter> manages buffers for writing on the caller's behalf.</span></span> <span data-ttu-id="41705-267">`PipeWriter`는 [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601)를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-267">`PipeWriter` implements [`IBufferWriter<byte>`](xref:System.Buffers.IBufferWriter%601).</span></span> <span data-ttu-id="41705-268">`IBufferWriter<byte>`는 추가 버퍼 복사본 없이 쓰기를 수행하기 위해 버퍼에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-268">`IBufferWriter<byte>` makes it possible to get access to buffers to perform writes without additional buffer copies.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet":::

<span data-ttu-id="41705-269">이전 코드는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-269">The previous code:</span></span>

* <span data-ttu-id="41705-270"><xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>을 사용하여 `PipeWriter`에서 최소 5바이트의 버퍼를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-270">Requests a buffer of at least 5 bytes from the `PipeWriter` using <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>.</span></span>
* <span data-ttu-id="41705-271">반환된 `Memory<byte>`에 ASCII 문자열 `"Hello"`를 위한 바이트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="41705-271">Writes bytes for the ASCII string `"Hello"` to the returned `Memory<byte>`.</span></span>
* <span data-ttu-id="41705-272"><xref:System.IO.Pipelines.PipeWriter.Advance%2A>를 호출하여 버퍼에 쓴 바이트 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-272">Calls <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to indicate how many bytes were written to the buffer.</span></span>
* <span data-ttu-id="41705-273">기본 디바이스로 바이트를 전송하는 `PipeWriter`를 플러시합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-273">Flushes the `PipeWriter`, which sends the bytes to the underlying device.</span></span>

<span data-ttu-id="41705-274">이전 작성 메서드에서는 `PipeWriter`에서 제공하는 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-274">The previous method of writing uses the buffers provided by the `PipeWriter`.</span></span> <span data-ttu-id="41705-275">또는, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span><span class="sxs-lookup"><span data-stu-id="41705-275">Alternatively, <xref:System.IO.Pipelines.PipeWriter.WriteAsync%2A?displayProperty=nameWithType>:</span></span>

* <span data-ttu-id="41705-276">기존 버퍼를 `PipeWriter`에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-276">Copies the existing buffer to the `PipeWriter`.</span></span>
* <span data-ttu-id="41705-277">`GetSpan`, `Advance`를 적절하게 호출하고 <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-277">Calls `GetSpan`, `Advance` as appropriate and calls <xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>.</span></span>

:::code language="csharp" source="~/samples/snippets/csharp/pipelines/MyPipeWriter.cs" id="snippet2":::

### <a name="cancellation"></a><span data-ttu-id="41705-278">취소</span><span class="sxs-lookup"><span data-stu-id="41705-278">Cancellation</span></span>

<span data-ttu-id="41705-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A>에서는 <xref:System.Threading.CancellationToken> 전달을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-279"><xref:System.IO.Pipelines.PipeWriter.FlushAsync%2A> supports passing a <xref:System.Threading.CancellationToken>.</span></span> <span data-ttu-id="41705-280">`CancellationToken`을 전달하면 플러시가 보류 중인 동안 토큰이 취소되는 경우 `OperationCanceledException`을 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-280">Passing a `CancellationToken` results in an `OperationCanceledException` if the token is canceled while there's a flush pending.</span></span> <span data-ttu-id="41705-281">`PipeWriter.FlushAsync`는 예외를 발생시키지 않고 <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType>을 통해 현재 플러시 작업을 취소하는 메서드를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-281">`PipeWriter.FlushAsync` supports a way to cancel the current flush operation via <xref:System.IO.Pipelines.PipeWriter.CancelPendingFlush%2A?displayProperty=nameWithType> without raising an exception.</span></span> <span data-ttu-id="41705-282">`PipeWriter.CancelPendingFlush`를 호출하면 `PipeWriter.FlushAsync` 또는 `PipeWriter.WriteAsync`에 대한 현재 또는 다음 호출이 `IsCanceled`가 `true`로 설정된 <xref:System.IO.Pipelines.FlushResult>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-282">Calling `PipeWriter.CancelPendingFlush` causes the current or next call to `PipeWriter.FlushAsync` or `PipeWriter.WriteAsync` to return a <xref:System.IO.Pipelines.FlushResult> with `IsCanceled` set to `true`.</span></span> <span data-ttu-id="41705-283">이는 생성 플러시를 비파괴적이고 예외 없는 방식으로 중지하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-283">This can be useful for halting the yielding flush in a non-destructive and non-exceptional way.</span></span>

<a name="pwcp"></a>

### <a name="pipewriter-common-problems"></a><span data-ttu-id="41705-284">PipeWriter의 일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="41705-284">PipeWriter common problems</span></span>

* <span data-ttu-id="41705-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> 및 <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A>는 적어도 요청된 양의 메모리를 포함하는 버퍼를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-285"><xref:System.IO.Pipelines.PipeWriter.GetSpan%2A> and <xref:System.IO.Pipelines.PipeWriter.GetMemory%2A> return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="41705-286">정확한 버퍼 크기를 가정하지 **마세요**.</span><span class="sxs-lookup"><span data-stu-id="41705-286">**Don't** assume exact buffer sizes.</span></span>
* <span data-ttu-id="41705-287">연속 호출이 동일한 버퍼 또는 동일한 크기의 버퍼를 반환한다는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-287">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
* <span data-ttu-id="41705-288">추가 데이터를 계속 작성하려면 <xref:System.IO.Pipelines.PipeWriter.Advance%2A>를 호출한 후 새 버퍼를 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-288">A new buffer must be requested after calling <xref:System.IO.Pipelines.PipeWriter.Advance%2A> to continue writing more data.</span></span> <span data-ttu-id="41705-289">이전에 획득한 버퍼에 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-289">The previously acquired buffer can't be written to.</span></span>
* <span data-ttu-id="41705-290">`GetMemory` 또는 `GetSpan`을 호출하면 `FlushAsync`에 대한 불완전한 호출이 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-290">Calling `GetMemory` or `GetSpan` while there's an incomplete call to `FlushAsync` isn't safe.</span></span>
* <span data-ttu-id="41705-291">플러시된 데이터가 없는 상태에서 `Complete` 또는 `CompleteAsync`를 호출하면 메모리가 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-291">Calling `Complete` or `CompleteAsync` while there's unflushed data can result in memory corruption.</span></span>

## <a name="iduplexpipe"></a><span data-ttu-id="41705-292">IDuplexPipe</span><span class="sxs-lookup"><span data-stu-id="41705-292">IDuplexPipe</span></span>

<span data-ttu-id="41705-293"><xref:System.IO.Pipelines.IDuplexPipe>는 읽기와 쓰기를 모두 지원하는 형식에 대한 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-293">The <xref:System.IO.Pipelines.IDuplexPipe> is a contract for types that support both reading and writing.</span></span> <span data-ttu-id="41705-294">예를 들어 네트워크 연결은 `IDuplexPipe`로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-294">For example, a network connection would be represented by an `IDuplexPipe`.</span></span>

 <span data-ttu-id="41705-295">`PipeReader` 및 `PipeWriter`를 포함하는 `Pipe`와 달리 `IDuplexPipe`는 전이중 연결의 단일 측면을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="41705-295">Unlike `Pipe`, which contains a `PipeReader` and a `PipeWriter`, `IDuplexPipe` represents a single side of a full duplex connection.</span></span> <span data-ttu-id="41705-296">이는 `PipeWriter`로 쓴 내용이 `PipeReader`에서 읽히지 않는다는 의미입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-296">That means what is written to the `PipeWriter` will not be read from the `PipeReader`.</span></span>

## <a name="streams"></a><span data-ttu-id="41705-297">스트림</span><span class="sxs-lookup"><span data-stu-id="41705-297">Streams</span></span>

<span data-ttu-id="41705-298">스트림 데이터를 읽거나 쓸 때는 일반적으로 역직렬 변환기를 사용하여 데이터를 읽고 직렬 변환기를 사용하여 데이터를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="41705-298">When reading or writing stream data, you typically read data using a de-serializer and write data using a serializer.</span></span> <span data-ttu-id="41705-299">대부분의 읽기 및 쓰기 스트림 API에는 `Stream` 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-299">Most of these read and write stream APIs have a `Stream` parameter.</span></span> <span data-ttu-id="41705-300">기존 API와 더욱 쉽게 통합할 수 있도록 `PipeReader` 및 `PipeWriter`는 <xref:System.IO.Pipelines.PipeReader.AsStream%2A> 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-300">To make it easier to integrate with these existing APIs, `PipeReader` and `PipeWriter` expose an <xref:System.IO.Pipelines.PipeReader.AsStream%2A> method.</span></span> <span data-ttu-id="41705-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A>은 `PipeReader` 또는 `PipeWriter` 주위에 `Stream` 구현을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-301"><xref:System.IO.Pipelines.PipeWriter.AsStream%2A> returns a `Stream` implementation around the `PipeReader` or `PipeWriter`.</span></span>

### <a name="stream-example"></a><span data-ttu-id="41705-302">스트림 예제</span><span class="sxs-lookup"><span data-stu-id="41705-302">Stream example</span></span>

<span data-ttu-id="41705-303"><xref:System.IO.Stream> 개체와 선택적으로 해당하는 생성 옵션이 제공된 경우 정적 `Create` 메서드를 사용하여 `PipeReader` 및 `PipeWriter` 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-303">`PipeReader` and `PipeWriter` instances can be created using the static `Create` methods given a <xref:System.IO.Stream> object and optional corresponding creation options.</span></span>

<span data-ttu-id="41705-304"><xref:System.IO.Pipelines.StreamPipeReaderOptions>를 사용하면 다음 매개 변수로 `PipeReader` 인스턴스 생성을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-304">The <xref:System.IO.Pipelines.StreamPipeReaderOptions> allow for control over the creation of the `PipeReader` instance with the following parameters:</span></span>

- <span data-ttu-id="41705-305"><xref:System.IO.Pipelines.StreamPipeReaderOptions.BufferSize?displayProperty=nameWithType>은 풀에서 메모리를 대여할 때 사용되는 최소 버퍼 크기(바이트)이며, 기본값은 `4096`입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-305"><xref:System.IO.Pipelines.StreamPipeReaderOptions.BufferSize?displayProperty=nameWithType> is the minimum buffer size in bytes used when renting memory from the pool, and defaults to `4096`.</span></span>
- <span data-ttu-id="41705-306"><xref:System.IO.Pipelines.StreamPipeReaderOptions.LeaveOpen?displayProperty=nameWithType> 플래그는 `PipeReader`가 완료된 후 기본 스트림을 열어 둘지 여부를 결정하며, 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-306"><xref:System.IO.Pipelines.StreamPipeReaderOptions.LeaveOpen?displayProperty=nameWithType> flag determines whether or not the underlying stream is left open after the `PipeReader` completes, and defaults to `false`.</span></span>
- <span data-ttu-id="41705-307"><xref:System.IO.Pipelines.StreamPipeReaderOptions.MinimumReadSize?displayProperty=nameWithType>은 새 버퍼가 할당되기 전에 버퍼에 남은 바이트의 임계값을 나타내며, 기본값은 `1024`입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-307"><xref:System.IO.Pipelines.StreamPipeReaderOptions.MinimumReadSize?displayProperty=nameWithType> represents the threshold of remaining bytes in the buffer before a new buffer is allocated, and defaults to `1024`.</span></span>
- <span data-ttu-id="41705-308"><xref:System.IO.Pipelines.StreamPipeReaderOptions.Pool?displayProperty=nameWithType>은 메모리를 할당할 때 사용되는 `MemoryPool<byte>`이며, 기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-308"><xref:System.IO.Pipelines.StreamPipeReaderOptions.Pool?displayProperty=nameWithType> is the `MemoryPool<byte>` used when allocating memory, and defaults to `null`.</span></span>

<span data-ttu-id="41705-309"><xref:System.IO.Pipelines.StreamPipeWriterOptions>를 사용하면 다음 매개 변수로 `PipeWriter` 인스턴스 생성을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="41705-309">The <xref:System.IO.Pipelines.StreamPipeWriterOptions> allow for control over the creation of the `PipeWriter` instance with the following parameters:</span></span>

- <span data-ttu-id="41705-310"><xref:System.IO.Pipelines.StreamPipeWriterOptions.LeaveOpen?displayProperty=nameWithType> 플래그는 `PipeWriter`가 완료된 후 기본 스트림을 열어 둘지 여부를 결정하며, 기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-310"><xref:System.IO.Pipelines.StreamPipeWriterOptions.LeaveOpen?displayProperty=nameWithType> flag determines whether or not the underlying stream is left open after the `PipeWriter` completes, and defaults to `false`.</span></span>
- <span data-ttu-id="41705-311"><xref:System.IO.Pipelines.StreamPipeWriterOptions.MinimumBufferSize?displayProperty=nameWithType>은 <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool>에서 메모리를 대여할 때 사용할 최소 버퍼 크기를 나타내며, 기본값은 `4096`입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-311"><xref:System.IO.Pipelines.StreamPipeWriterOptions.MinimumBufferSize?displayProperty=nameWithType> represents the minimum buffer size to use when renting memory from the <xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool>, and defaults to `4096`.</span></span>
- <span data-ttu-id="41705-312"><xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool?displayProperty=nameWithType>은 메모리를 할당할 때 사용되는 `MemoryPool<byte>`이며, 기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="41705-312"><xref:System.IO.Pipelines.StreamPipeWriterOptions.Pool?displayProperty=nameWithType> is the `MemoryPool<byte>` used when allocating memory, and defaults to `null`.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41705-313">`Create` 메서드를 사용하여 `PipeReader` 및 `PipeWriter` 인스턴스를 만드는 경우 `Stream` 개체 수명을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-313">When creating `PipeReader` and `PipeWriter` instances using the `Create` methods, you need to consider the `Stream` object lifetime.</span></span> <span data-ttu-id="41705-314">판독기 또는 기록기 작업이 완료된 후 스트림에 액세스해야 하는 경우 생성 옵션의 `LeaveOpen` 플래그를 `true`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-314">If you need access to the stream after the reader or writer is done with it, you'll need to set the `LeaveOpen` flag to `true` on the creation options.</span></span> <span data-ttu-id="41705-315">그러지 않으면 스트림이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="41705-315">Otherwise, the stream will be closed.</span></span>

<span data-ttu-id="41705-316">다음 코드는 스트림에서 `Create` 메서드를 사용하여 `PipeReader` 및 `PipeWriter` 인스턴스를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="41705-316">The following code demonstrates the creation of `PipeReader` and `PipeWriter` instances using the `Create` methods from a stream.</span></span>

:::code language="csharp" source="snippets/pipelines/Program.cs":::

<span data-ttu-id="41705-317">애플리케이션이 <xref:System.IO.StreamReader>를 사용하여 *lorem-ipsum.txt* 파일을 스트림으로 읽어옵니다.</span><span class="sxs-lookup"><span data-stu-id="41705-317">The application uses a <xref:System.IO.StreamReader> to read the *lorem-ipsum.txt* file as a stream.</span></span> <span data-ttu-id="41705-318"><xref:System.IO.FileStream>이 `PipeReader` 개체를 인스턴스화하는 <xref:System.IO.Pipelines.PipeReader.Create%2A?displayProperty=nameWithType>에 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="41705-318">The <xref:System.IO.FileStream> is passed to <xref:System.IO.Pipelines.PipeReader.Create%2A?displayProperty=nameWithType>, which instantiates a `PipeReader` object.</span></span> <span data-ttu-id="41705-319">그런 다음, 콘솔 애플리케이션이 <xref:System.Console.OpenStandardOutput?displayProperty=nameWithType>을 사용하여 표준 출력 스트림을 <xref:System.IO.Pipelines.PipeWriter.Create%2A?displayProperty=nameWithType>에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-319">The console application then passes its standard output stream to <xref:System.IO.Pipelines.PipeWriter.Create%2A?displayProperty=nameWithType> using <xref:System.Console.OpenStandardOutput?displayProperty=nameWithType>.</span></span> <span data-ttu-id="41705-320">이 예제에서는 [취소](#cancellation)를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="41705-320">The example supports [cancellation](#cancellation).</span></span>
