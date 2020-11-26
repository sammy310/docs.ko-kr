---
title: System.Buffers - .NET
ms.date: 12/05/2019
helpviewer_keywords:
- buffers [.NET]
- I/O [.NET], buffers
author: rick-anderson
ms.author: riande
ms.openlocfilehash: afcd6976e6220349fbec370c47b11596a35a81a2
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/18/2020
ms.locfileid: "94823526"
---
# <a name="work-with-buffers-in-net"></a><span data-ttu-id="6eac5-102">.NET에서 버퍼 작업</span><span class="sxs-lookup"><span data-stu-id="6eac5-102">Work with Buffers in .NET</span></span>

<span data-ttu-id="6eac5-103">이 문서에서는 여러 버퍼에서 실행되는 데이터를 읽는 데 도움이 되는 형식을 개략적으로 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-103">This article provides an overview of types that help read data that runs across multiple buffers.</span></span> <span data-ttu-id="6eac5-104">이러한 형식은 주로 <xref:System.IO.Pipelines.PipeReader> 개체를 지원하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-104">They're primarily used to support <xref:System.IO.Pipelines.PipeReader> objects.</span></span>

## <a name="ibufferwritert"></a><span data-ttu-id="6eac5-105">IBufferWriter\<T\></span><span class="sxs-lookup"><span data-stu-id="6eac5-105">IBufferWriter\<T\></span></span>

<span data-ttu-id="6eac5-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName>는 비동기 버퍼링 쓰기에 대한 계약입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-106"><xref:System.Buffers.IBufferWriter%601?displayProperty=fullName> is a contract for synchronous buffered writing.</span></span> <span data-ttu-id="6eac5-107">최저 수준에서 인터페이스는,</span><span class="sxs-lookup"><span data-stu-id="6eac5-107">At the lowest level, the interface:</span></span>

- <span data-ttu-id="6eac5-108">기본적이며 사용하기 어렵지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-108">Is basic and not difficult to use.</span></span>
- <span data-ttu-id="6eac5-109"><xref:System.Memory%601> 또는 <xref:System.Span%601>에 대한 액세스를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-109">Allows access to a <xref:System.Memory%601> or <xref:System.Span%601>.</span></span> <span data-ttu-id="6eac5-110">`Memory<T>` 또는 `Span<T>`에 쓸 수 있으며 작성된 `T` 항목의 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-110">The `Memory<T>` or `Span<T>` can be written to and you can determine how many `T` items were written.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

<span data-ttu-id="6eac5-111">위의 메서드는,</span><span class="sxs-lookup"><span data-stu-id="6eac5-111">The preceding method:</span></span>

- <span data-ttu-id="6eac5-112">`GetSpan(5)`을 사용하여 `IBufferWriter<byte>`에서 최소 5바이트의 버퍼를 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-112">Requests a buffer of at least 5 bytes from the `IBufferWriter<byte>` using `GetSpan(5)`.</span></span>
- <span data-ttu-id="6eac5-113">반환된 `Span<byte>`에 ASCII 문자열 "Hello"를 위한 바이트를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-113">Writes bytes for the ASCII string "Hello" to the returned `Span<byte>`.</span></span>
- <span data-ttu-id="6eac5-114"><xref:System.Buffers.IBufferWriter%601>를 호출하여 버퍼에 쓴 바이트 수를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-114">Calls  <xref:System.Buffers.IBufferWriter%601> to indicate how many bytes were written to the buffer.</span></span>

<span data-ttu-id="6eac5-115">이 쓰기 메서드는 `IBufferWriter<T>`에서 제공하는 `Memory<T>`/`Span<T>` 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-115">This method of writing uses the `Memory<T>`/`Span<T>` buffer provided by the `IBufferWriter<T>`.</span></span> <span data-ttu-id="6eac5-116">또는 <xref:System.Buffers.BuffersExtensions.Write%2A> 확장 메서드를 사용하여 기존 버퍼를 `IBufferWriter<T>`에 복사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-116">Alternatively, the <xref:System.Buffers.BuffersExtensions.Write%2A> extension method can be used to copy an existing buffer to the `IBufferWriter<T>`.</span></span> <span data-ttu-id="6eac5-117">`Write`가 필요에 따라 `GetSpan`/`Advance`를 호출하는 작업을 수행하므로 쓰기 후 `Advance`를 호출할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-117">`Write` does the work of calling `GetSpan`/`Advance` as appropriate, so there's no need to call `Advance` after writing:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<span data-ttu-id="6eac5-118"><xref:System.Buffers.ArrayBufferWriter%601>는 백업 저장소가 단일 연속 배열인 `IBufferWriter<T>`의 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-118"><xref:System.Buffers.ArrayBufferWriter%601> is an implementation of `IBufferWriter<T>` whose backing store is a single contiguous array.</span></span>

### <a name="ibufferwriter-common-problems"></a><span data-ttu-id="6eac5-119">IBufferWriter의 일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="6eac5-119">IBufferWriter common problems</span></span>

- <span data-ttu-id="6eac5-120">`GetSpan` 및 `GetMemory`는 적어도 요청된 양의 메모리를 포함하는 버퍼를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-120">`GetSpan` and `GetMemory` return a buffer with at least the requested amount of memory.</span></span> <span data-ttu-id="6eac5-121">정확한 버퍼 크기를 가정하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="6eac5-121">Don't assume exact buffer sizes.</span></span>
- <span data-ttu-id="6eac5-122">연속 호출이 동일한 버퍼 또는 동일한 크기의 버퍼를 반환한다는 보장은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-122">There's no guarantee that successive calls will return the same buffer or the same-sized buffer.</span></span>
- <span data-ttu-id="6eac5-123">추가 데이터를 계속 작성하려면 `Advance`를 호출한 후 새 버퍼를 요청해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-123">A new buffer must be requested after calling `Advance` to continue writing more data.</span></span> <span data-ttu-id="6eac5-124">`Advance`를 호출한 후에는 이전에 가져온 버퍼를 쓸 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-124">A previously acquired buffer cannot be written to after `Advance` has been called.</span></span>

## <a name="readonlysequencet"></a><span data-ttu-id="6eac5-125">ReadOnlySequence\<T\></span><span class="sxs-lookup"><span data-stu-id="6eac5-125">ReadOnlySequence\<T\></span></span>

![파이프에서 읽기 전용 메모리의 시퀀스 위치 이하의 메모리를 표시하는 ReadOnlySequence입니다.](media/buffers/ro-sequence.png)

<span data-ttu-id="6eac5-127"><xref:System.Buffers.ReadOnlySequence%601>은 `T`의 연속 또는 불연속 시퀀스를 나타낼 수 있는 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-127"><xref:System.Buffers.ReadOnlySequence%601> is a struct that can represent a contiguous or noncontiguous sequence of `T`.</span></span> <span data-ttu-id="6eac5-128">다음에서 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-128">It can be constructed from:</span></span>

1. <span data-ttu-id="6eac5-129">`T[]`</span><span class="sxs-lookup"><span data-stu-id="6eac5-129">A `T[]`</span></span>
1. <span data-ttu-id="6eac5-130">`ReadOnlyMemory<T>`</span><span class="sxs-lookup"><span data-stu-id="6eac5-130">A `ReadOnlyMemory<T>`</span></span>
1. <span data-ttu-id="6eac5-131">연결된 목록 노드 <xref:System.Buffers.ReadOnlySequenceSegment%601>과 인덱스의 쌍으로, 시퀀스의 시작 및 끝 위치를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-131">A pair of linked list node <xref:System.Buffers.ReadOnlySequenceSegment%601> and index to represent the start and end position of the sequence.</span></span>

<span data-ttu-id="6eac5-132">세 번째 표현은 `ReadOnlySequence<T>`의 다양한 작업에 대한 성능에 영향을 미치므로 가장 흥미로운 부분입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-132">The third representation is the most interesting one as it has performance implications on various operations on the `ReadOnlySequence<T>`:</span></span>

|<span data-ttu-id="6eac5-133">표현</span><span class="sxs-lookup"><span data-stu-id="6eac5-133">Representation</span></span>|<span data-ttu-id="6eac5-134">연산</span><span class="sxs-lookup"><span data-stu-id="6eac5-134">Operation</span></span>|<span data-ttu-id="6eac5-135">복잡성</span><span class="sxs-lookup"><span data-stu-id="6eac5-135">Complexity</span></span>|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

<span data-ttu-id="6eac5-136">이 혼합된 표현으로 인해 `ReadOnlySequence<T>`는 인덱스를 정수가 아닌 `SequencePosition`으로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-136">Because of this mixed representation, the `ReadOnlySequence<T>` exposes indexes as `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="6eac5-137">`SequencePosition`:</span><span class="sxs-lookup"><span data-stu-id="6eac5-137">A `SequencePosition`:</span></span>

- <span data-ttu-id="6eac5-138">이 메서드가 시작된 `ReadOnlySequence<T>`에 대한 인덱스를 나타내는 불투명 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-138">Is an opaque value that represents an index into the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="6eac5-139">정수와 개체 두 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-139">Consists of two parts, an integer and an object.</span></span> <span data-ttu-id="6eac5-140">이들 두 값이 표현하는 내용은 `ReadOnlySequence<T>` 구현에 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-140">What these two values represent are tied to the implementation of `ReadOnlySequence<T>`.</span></span>

### <a name="access-data"></a><span data-ttu-id="6eac5-141">데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="6eac5-141">Access data</span></span>

<span data-ttu-id="6eac5-142">`ReadOnlySequence<T>`는 데이터를 `ReadOnlyMemory<T>`의 열거 가능 항목으로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-142">The `ReadOnlySequence<T>` exposes data as an enumerable of `ReadOnlyMemory<T>`.</span></span> <span data-ttu-id="6eac5-143">각 세그먼트를 열거하는 작업은 기본 foreach를 사용하여 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-143">Enumerating each of the segments can be done using a basic foreach:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

<span data-ttu-id="6eac5-144">위의 메서드는 각 세그먼트에서 특정 바이트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-144">The preceding method searches each segment for a specific byte.</span></span> <span data-ttu-id="6eac5-145">각 세그먼트의 `SequencePosition`을 추적해야 하는 경우 <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType>가 더 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-145">If you need to keep track of each segment's `SequencePosition`, <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType> is more appropriate.</span></span> <span data-ttu-id="6eac5-146">다음 샘플에서는 정수 대신 `SequencePosition`을 반환하도록 위의 코드를 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-146">The next sample changes the preceding code to return a `SequencePosition` instead of an integer.</span></span> <span data-ttu-id="6eac5-147">`SequencePosition`을 반환하면 호출자가 특정 인덱스에서 데이터를 가져오기 위해 두 번째 검색이 방지되는 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-147">Returning a `SequencePosition` has the benefit of allowing the caller to avoid a second scan to get the data at a specific index.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

<span data-ttu-id="6eac5-148">`SequencePosition`와 `TryGet`의 조합은 열거자처럼 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-148">The combination of `SequencePosition` and `TryGet` acts like an enumerator.</span></span> <span data-ttu-id="6eac5-149">위치 필드는 각 반복이 시작될 때 `ReadOnlySequence<T>` 내에서 각 세그먼트의 시작으로 수정됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-149">The position field is modified at the start of each iteration to be start of each segment within the `ReadOnlySequence<T>`.</span></span>

<span data-ttu-id="6eac5-150">위의 메서드는 `ReadOnlySequence<T>`에 대한 확장 메서드로 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-150">The preceding method exists as an extension method on `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="6eac5-151"><xref:System.Buffers.BuffersExtensions.PositionOf%2A>는 위의 코드를 간소화하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-151"><xref:System.Buffers.BuffersExtensions.PositionOf%2A> can be used to simplify the preceding code:</span></span>

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a><span data-ttu-id="6eac5-152">ReadOnlySequence\<T\> 처리</span><span class="sxs-lookup"><span data-stu-id="6eac5-152">Process a ReadOnlySequence\<T\></span></span>

<span data-ttu-id="6eac5-153">데이터가 시퀀스 내의 여러 세그먼트로 분할될 수 있으므로 `ReadOnlySequence<T>` 처리는 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-153">Processing a `ReadOnlySequence<T>` can be challenging since data may be split across multiple segments within the sequence.</span></span> <span data-ttu-id="6eac5-154">최상의 성능을 위해 코드를 다음 두 개의 경로로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-154">For the best performance, split code into two paths:</span></span>

- <span data-ttu-id="6eac5-155">단일 세그먼트 케이스를 처리하는 빠른 경로.</span><span class="sxs-lookup"><span data-stu-id="6eac5-155">A fast path that deals with the single segment case.</span></span>
- <span data-ttu-id="6eac5-156">여러 세그먼트로 분할된 데이터를 처리하는 느린 경로.</span><span class="sxs-lookup"><span data-stu-id="6eac5-156">A slow path that deals with the data split across segments.</span></span>

<span data-ttu-id="6eac5-157">다중 분할된 시퀀스에서 데이터를 처리하는 데 사용할 수 있는 몇 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-157">There are a few approaches that can be used to process data in multi-segmented sequences:</span></span>

- <span data-ttu-id="6eac5-158">[`SequenceReader<T>`](#sequencereadert)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-158">Use the [`SequenceReader<T>`](#sequencereadert).</span></span>
- <span data-ttu-id="6eac5-159">구문 분석된 세그먼트 내에서 `SequencePosition` 및 인덱스를 추적하여 데이터를 세그먼트 단위로 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-159">Parse data segment by segment, keeping track of the `SequencePosition` and index within the segment parsed.</span></span> <span data-ttu-id="6eac5-160">이렇게 하면 불필요한 할당을 피할 수 있지만 특히 버퍼가 작은 경우에는 비효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-160">This avoids unnecessary allocations but may be inefficient, especially for small buffers.</span></span>
- <span data-ttu-id="6eac5-161">`ReadOnlySequence<T>`를 연속된 배열에 복사하고 단일 버퍼처럼 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-161">Copy the `ReadOnlySequence<T>` to a contiguous array and treat it like a single buffer:</span></span>
  - <span data-ttu-id="6eac5-162">`ReadOnlySequence<T>` 크기가 작으면 [stackalloc](../../csharp/language-reference/operators/stackalloc.md) 연산자를 사용하여 스택 할당 버퍼에 데이터를 복사하는 것이 합리적입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-162">If the size of the `ReadOnlySequence<T>` is small, it may be reasonable to copy the data into a stack-allocated buffer using the [stackalloc](../../csharp/language-reference/operators/stackalloc.md) operator.</span></span>
  - <span data-ttu-id="6eac5-163"><xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>를 사용하여 `ReadOnlySequence<T>`를 풀링된 배열에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-163">Copy the `ReadOnlySequence<T>` into a pooled array using <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>.</span></span>
  - <span data-ttu-id="6eac5-164">[`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-164">Use [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A).</span></span> <span data-ttu-id="6eac5-165">이는 힙에서 새 `T[]`를 할당하므로 실행 부하 과다 경로에는 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-165">This isn't recommended in hot paths as it allocates a new `T[]` on the heap.</span></span>

<span data-ttu-id="6eac5-166">다음 예제에서는 `ReadOnlySequence<byte>`를 처리하는 몇 가지 일반적인 사례를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-166">The following examples demonstrate some common cases for processing `ReadOnlySequence<byte>`:</span></span>

##### <a name="process-binary-data"></a><span data-ttu-id="6eac5-167">이진 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="6eac5-167">Process binary data</span></span>

<span data-ttu-id="6eac5-168">다음 예제에서는 `ReadOnlySequence<byte>`의 시작 부분에서 4바이트 Big Endian 정수 길이를 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-168">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a><span data-ttu-id="6eac5-169">텍스트 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="6eac5-169">Process text data</span></span>

<span data-ttu-id="6eac5-170">다음 예제가 하는 일:</span><span class="sxs-lookup"><span data-stu-id="6eac5-170">The following example:</span></span>

- <span data-ttu-id="6eac5-171">`ReadOnlySequence<byte>`에서 첫 번째 줄 바꿈(`\r\n`)을 찾아 out 'line' 매개 변수를 통해 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-171">Finds the first newline (`\r\n`) in the `ReadOnlySequence<byte>` and returns it via the out 'line' parameter.</span></span>
- <span data-ttu-id="6eac5-172">입력 버퍼에서 `\r\n`을 제외하고 해당 줄을 자릅니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-172">Trims that line, excluding the `\r\n` from the input buffer.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a><span data-ttu-id="6eac5-173">빈 세그먼트</span><span class="sxs-lookup"><span data-stu-id="6eac5-173">Empty segments</span></span>

<span data-ttu-id="6eac5-174">`ReadOnlySequence<T>` 안에 빈 세그먼트를 저장하는 것은 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-174">It's valid to store empty segments inside of a `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="6eac5-175">세그먼트를 명시적으로 열거하는 동안 빈 세그먼트가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-175">Empty segments may occur while enumerating segments explicitly:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

<span data-ttu-id="6eac5-176">위의 코드는 빈 세그먼트를 사용하여 `ReadOnlySequence<byte>`를 만들고 이러한 빈 세그먼트가 다양한 API에 미치는 영향을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-176">The preceding code creates a `ReadOnlySequence<byte>` with empty segments and shows how those empty segments affect the various APIs:</span></span>

- <span data-ttu-id="6eac5-177">`SequencePosition`이 빈 세그먼트를 가리키는 `ReadOnlySequence<T>.Slice`는 해당 세그먼트를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-177">`ReadOnlySequence<T>.Slice` with a `SequencePosition` pointing to an empty segment preserves that segment.</span></span>
- <span data-ttu-id="6eac5-178">정수가 포함된 `ReadOnlySequence<T>.Slice`는 빈 세그먼트를 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-178">`ReadOnlySequence<T>.Slice` with an int skips over the empty segments.</span></span>
- <span data-ttu-id="6eac5-179">`ReadOnlySequence<T>`를 열거하면 빈 세그먼트가 열거됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-179">Enumerating the `ReadOnlySequence<T>` enumerates the empty segments.</span></span>

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a><span data-ttu-id="6eac5-180">ReadOnlySequence\<T> 및 SequencePosition의 잠재적 문제</span><span class="sxs-lookup"><span data-stu-id="6eac5-180">Potential problems with ReadOnlySequence\<T> and SequencePosition</span></span>

<span data-ttu-id="6eac5-181">`ReadOnlySequence<T>`/`SequencePosition`을 처리할 때 일반 `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int`에 비해 비정상적인 결과가 몇 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-181">There are several unusual outcomes when dealing with a `ReadOnlySequence<T>`/`SequencePosition` vs. a normal `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int`:</span></span>

- <span data-ttu-id="6eac5-182">`SequencePosition`은 절대 위치가 아니라 특정 `ReadOnlySequence<T>`의 위치 표식입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-182">`SequencePosition` is a position marker for a specific `ReadOnlySequence<T>`, not an absolute position.</span></span> <span data-ttu-id="6eac5-183">특정 `ReadOnlySequence<T>`를 기준으로 하기 때문에 이 메서드가 시작된 `ReadOnlySequence<T>`의 외부에서 사용하는 경우 의미가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-183">Because it's relative to a specific `ReadOnlySequence<T>`, it doesn't have meaning if used outside of the `ReadOnlySequence<T>` where it originated.</span></span>
- <span data-ttu-id="6eac5-184">`ReadOnlySequence<T>` 없이는 `SequencePosition`에서 산술 연산을 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-184">Arithmetic can't be performed on `SequencePosition` without the `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="6eac5-185">즉 `position++`와 같은 기본 작업을 실행하면 `ReadOnlySequence<T>.GetPosition(position, 1)`이 작성됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-185">That means doing basic things like `position++` is written `ReadOnlySequence<T>.GetPosition(position, 1)`.</span></span>
- <span data-ttu-id="6eac5-186">`GetPosition(long)`은 음수 인덱스를 지원하지 **않습니다**.</span><span class="sxs-lookup"><span data-stu-id="6eac5-186">`GetPosition(long)` does **not** support negative indexes.</span></span> <span data-ttu-id="6eac5-187">즉, 모든 세그먼트를 탐색하지 않고 두 번째에서 마지막까지 문자를 가져올 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-187">That means it's impossible to get the second to last character without walking all segments.</span></span>
- <span data-ttu-id="6eac5-188">두 개의 `SequencePosition`를 비교할 수 없어 다음 작업을 수행하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-188">Two `SequencePosition` can't be compared, making it difficult to:</span></span>
  - <span data-ttu-id="6eac5-189">한 위치가 다른 위치보다 크거나 작은 경우를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-189">Know if one position is greater than or less than another position.</span></span>
  - <span data-ttu-id="6eac5-190">몇 가지 구문 분석 알고리즘을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-190">Write some parsing algorithms.</span></span>
- <span data-ttu-id="6eac5-191">`ReadOnlySequence<T>`는 개체 참조보다 크고, 가능하면 [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) 또는 [ref](../../csharp/language-reference/keywords/ref.md)에 의해 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-191">`ReadOnlySequence<T>` is bigger than an object reference and should be passed by [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) or [ref](../../csharp/language-reference/keywords/ref.md) where possible.</span></span> <span data-ttu-id="6eac5-192">`in` 또는 `ref`를 통해 `ReadOnlySequence<T>`를 전달하면 [구조체](../../csharp/language-reference/builtin-types/struct.md) 복사본이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-192">Passing `ReadOnlySequence<T>` by `in` or `ref` reduces copies of the [struct](../../csharp/language-reference/builtin-types/struct.md).</span></span>
- <span data-ttu-id="6eac5-193">빈 세그먼트:</span><span class="sxs-lookup"><span data-stu-id="6eac5-193">Empty segments:</span></span>
  - <span data-ttu-id="6eac5-194">`ReadOnlySequence<T>` 내에서 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-194">Are valid within a `ReadOnlySequence<T>`.</span></span>
  - <span data-ttu-id="6eac5-195">`ReadOnlySequence<T>.TryGet` 메서드를 사용하여 반복할 때 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-195">Can appear when iterating using the `ReadOnlySequence<T>.TryGet` method.</span></span>
  - <span data-ttu-id="6eac5-196">`ReadOnlySequence<T>.Slice()` 메서드와 `SequencePosition` 개체를 사용하여 시퀀스를조각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-196">Can appear slicing the sequence using the `ReadOnlySequence<T>.Slice()` method with `SequencePosition` objects.</span></span>

## <a name="sequencereadert"></a><span data-ttu-id="6eac5-197">SequenceReader\<T\></span><span class="sxs-lookup"><span data-stu-id="6eac5-197">SequenceReader\<T\></span></span>

<span data-ttu-id="6eac5-198"><xref:System.Buffers.SequenceReader%601>:</span><span class="sxs-lookup"><span data-stu-id="6eac5-198"><xref:System.Buffers.SequenceReader%601>:</span></span>

- <span data-ttu-id="6eac5-199">`ReadOnlySequence<T>` 처리를 간소화하기 위해 .NET Core 3.0에 도입된 새로운 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-199">Is a new type that was introduced in .NET Core 3.0 to simplify the processing of a `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="6eac5-200">단일 세그먼트 `ReadOnlySequence<T>`와 다중 세그먼트 `ReadOnlySequence<T>` 간의 차이를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-200">Unifies the differences between a single segment `ReadOnlySequence<T>` and multi-segment `ReadOnlySequence<T>`.</span></span>
- <span data-ttu-id="6eac5-201">세그먼트 간에 분할될 수 있거나 분할될 수 없는 이진 및 텍스트 데이터(`byte` 및 `char`)를 읽기 위한 도우미를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-201">Provides helpers for reading binary and text data (`byte` and `char`) that may or may not be split across segments.</span></span>

<span data-ttu-id="6eac5-202">이진 데이터와 구분된 데이터를 모두 처리하는 기본 제공 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-202">There are built-in methods for dealing with processing both binary and delimited data.</span></span> <span data-ttu-id="6eac5-203">다음 섹션에서는 이러한 메서드가 `SequenceReader<T>`에서 어떻게 나타나는지 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-203">The following section demonstrates what those same methods look like with the `SequenceReader<T>`:</span></span>

### <a name="access-data"></a><span data-ttu-id="6eac5-204">데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="6eac5-204">Access data</span></span>

<span data-ttu-id="6eac5-205">`SequenceReader<T>`에는 `ReadOnlySequence<T>` 내에서 직접 데이터를 열거하는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-205">`SequenceReader<T>` has methods for enumerating data inside of the `ReadOnlySequence<T>` directly.</span></span> <span data-ttu-id="6eac5-206">다음 코드는 `ReadOnlySequence<byte>`를 한 번에 `byte` 처리하는 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-206">The following code is an example of processing a `ReadOnlySequence<byte>` a `byte` at a time:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

<span data-ttu-id="6eac5-207">`CurrentSpan`는 현재 세그먼트의 `Span`을 노출합니다. 이는 메서드에서 수동으로 수행된 것과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-207">The `CurrentSpan` exposes the current segment's `Span`, which is similar to what was done in the method manually.</span></span>

### <a name="use-position"></a><span data-ttu-id="6eac5-208">위치 사용</span><span class="sxs-lookup"><span data-stu-id="6eac5-208">Use position</span></span>

<span data-ttu-id="6eac5-209">다음 코드는 `SequenceReader<T>`를 사용한 `FindIndexOf` 구현 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-209">The following code is an example implementation of `FindIndexOf` using the `SequenceReader<T>`:</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a><span data-ttu-id="6eac5-210">이진 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="6eac5-210">Process binary data</span></span>

<span data-ttu-id="6eac5-211">다음 예제에서는 `ReadOnlySequence<byte>`의 시작 부분에서 4바이트 Big Endian 정수 길이를 구문 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-211">The following example parses a 4-byte big-endian integer length from the start of the `ReadOnlySequence<byte>`.</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a><span data-ttu-id="6eac5-212">텍스트 데이터 처리</span><span class="sxs-lookup"><span data-stu-id="6eac5-212">Process text data</span></span>

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a><span data-ttu-id="6eac5-213">SequenceReader\<T\>의 일반적인 문제</span><span class="sxs-lookup"><span data-stu-id="6eac5-213">SequenceReader\<T\> common problems</span></span>

- <span data-ttu-id="6eac5-214">`SequenceReader<T>`는 변경 가능한 구조체이므로 항상 [reference](../../csharp/language-reference/keywords/ref.md)로 전달되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-214">Because `SequenceReader<T>` is a mutable struct, it should always be passed by [reference](../../csharp/language-reference/keywords/ref.md).</span></span>
- <span data-ttu-id="6eac5-215">`SequenceReader<T>`는 [ref struct](../../csharp/language-reference/builtin-types/struct.md#ref-struct)이므로 동기 메서드에만 사용할 수 있고 필드에 저장할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-215">`SequenceReader<T>` is a [ref struct](../../csharp/language-reference/builtin-types/struct.md#ref-struct) so it can only be used in synchronous methods and can't be stored in fields.</span></span> <span data-ttu-id="6eac5-216">자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../csharp/write-safe-efficient-code.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6eac5-216">For more information, see [Write safe and efficient C# code](../../csharp/write-safe-efficient-code.md).</span></span>
- <span data-ttu-id="6eac5-217">`SequenceReader<T>`는 정방향 전용 판독기로 사용하도록 최적화되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-217">`SequenceReader<T>` is optimized for use as a forward-only reader.</span></span> <span data-ttu-id="6eac5-218">`Rewind`는 다른 `Read`, `Peek`및 `IsNext` API를 활용하여 해결할 수 없는 작은 백업에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6eac5-218">`Rewind` is intended for small backups that can't be addressed utilizing other `Read`, `Peek`, and `IsNext` APIs.</span></span>
