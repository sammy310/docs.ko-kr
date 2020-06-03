---
title: System.Buffers - .NET
ms.date: 12/05/2019
ms.technology: dotnet-standard
helpviewer_keywords:
- buffers [.NET]
- I/O [.NET], buffers
author: rick-anderson
ms.author: riande
ms.openlocfilehash: d113def0182dc6a5bcea6c18b2d0e4b475946e31
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739617"
---
# <a name="work-with-buffers-in-net"></a>.NET에서 버퍼 작업

이 문서에서는 여러 버퍼에서 실행되는 데이터를 읽는 데 도움이 되는 형식을 개략적으로 설명합니다. 이러한 형식은 주로 <xref:System.IO.Pipelines.PipeReader> 개체를 지원하는 데 사용됩니다.

## <a name="ibufferwritert"></a>IBufferWriter\<T\>

<xref:System.Buffers.IBufferWriter%601?displayProperty=fullName>는 비동기 버퍼링 쓰기에 대한 계약입니다. 최저 수준에서 인터페이스는,

- 기본적이며 사용하기 어렵지 않습니다.
- <xref:System.Memory%601> 또는 <xref:System.Span%601>에 대한 액세스를 허용합니다. `Memory<T>` 또는 `Span<T>`에 쓸 수 있으며 작성된 `T` 항목의 수를 확인할 수 있습니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet)]

위의 메서드는,

- `GetSpan(5)`을 사용하여 `IBufferWriter<byte>`에서 최소 5바이트의 버퍼를 요청합니다.
- 반환된 `Span<byte>`에 ASCII 문자열 "Hello"를 위한 바이트를 씁니다.
- <xref:System.Buffers.IBufferWriter%601>를 호출하여 버퍼에 쓴 바이트 수를 표시합니다.

이 쓰기 메서드는 `IBufferWriter<T>`에서 제공하는 `Memory<T>`/`Span<T>` 버퍼를 사용합니다. 또는 <xref:System.Buffers.BuffersExtensions.Write%2A> 확장 메서드를 사용하여 기존 버퍼를 `IBufferWriter<T>`에 복사할 수 있습니다. `Write`가 필요에 따라 `GetSpan`/`Advance`를 호출하는 작업을 수행하므로 쓰기 후 `Advance`를 호출할 필요가 없습니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet2)]

<xref:System.Buffers.ArrayBufferWriter%601>는 백업 저장소가 단일 연속 배열인 `IBufferWriter<T>`의 구현입니다.

### <a name="ibufferwriter-common-problems"></a>IBufferWriter의 일반적인 문제

- `GetSpan` 및 `GetMemory`는 적어도 요청된 양의 메모리를 포함하는 버퍼를 반환합니다. 정확한 버퍼 크기를 가정하지 마세요.
- 연속 호출이 동일한 버퍼 또는 동일한 크기의 버퍼를 반환한다는 보장은 없습니다.
- 추가 데이터를 계속 작성하려면 `Advance`를 호출한 후 새 버퍼를 요청해야 합니다. `Advance`를 호출한 후에는 이전에 가져온 버퍼를 쓸 수 없습니다.

## <a name="readonlysequencet"></a>ReadOnlySequence\<T\>

![파이프에서 읽기 전용 메모리의 시퀀스 위치 이하의 메모리를 표시하는 ReadOnlySequence입니다.](media/buffers/ro-sequence.png)

<xref:System.Buffers.ReadOnlySequence%601>은 `T`의 연속 또는 불연속 시퀀스를 나타낼 수 있는 구조체입니다. 다음에서 생성할 수 있습니다.

1. `T[]`
1. `ReadOnlyMemory<T>`
1. 연결된 목록 노드 <xref:System.Buffers.ReadOnlySequenceSegment%601>과 인덱스의 쌍으로, 시퀀스의 시작 및 끝 위치를 나타냅니다.

세 번째 표현은 `ReadOnlySequence<T>`의 다양한 작업에 대한 성능에 영향을 미치므로 가장 흥미로운 부분입니다.

|표현|연산|복잡성|
---|---|---|
|`T[]`/`ReadOnlyMemory<T>`|`Length`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`GetPosition(long)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(int, int)`|`O(1)`|
|`T[]`/`ReadOnlyMemory<T>`|`Slice(SequencePostion,  SequencePostion)`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`Length`|`O(1)`|
|`ReadOnlySequenceSegment<T>`|`GetPosition(long)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(int, int)`|`O(number of segments)`|
|`ReadOnlySequenceSegment<T>`|`Slice(SequencePostion, SequencePostion)`|`O(1)`|

이 혼합된 표현으로 인해 `ReadOnlySequence<T>`는 인덱스를 정수가 아닌 `SequencePosition`으로 노출합니다. `SequencePosition`:

- 이 메서드가 시작된 `ReadOnlySequence<T>`에 대한 인덱스를 나타내는 불투명 값입니다.
- 정수와 개체 두 부분으로 구성됩니다. 이들 두 값이 표현하는 내용은 `ReadOnlySequence<T>` 구현에 연결됩니다.

### <a name="access-data"></a>데이터 액세스

`ReadOnlySequence<T>`는 데이터를 `ReadOnlyMemory<T>`의 열거 가능 항목으로 노출합니다. 각 세그먼트를 열거하는 작업은 기본 foreach를 사용하여 수행할 수 있습니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet3)]

위의 메서드는 각 세그먼트에서 특정 바이트를 검색합니다. 각 세그먼트의 `SequencePosition`을 추적해야 하는 경우 <xref:System.Buffers.ReadOnlySequence%601.TryGet%2A?displayProperty=nameWithType>가 더 적합합니다. 다음 샘플에서는 정수 대신 `SequencePosition`을 반환하도록 위의 코드를 변경합니다. `SequencePosition`을 반환하면 호출자가 특정 인덱스에서 데이터를 가져오기 위해 두 번째 검색이 방지되는 이점을 얻을 수 있습니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet4)]

`SequencePosition`와 `TryGet`의 조합은 열거자처럼 동작합니다. 위치 필드는 각 반복이 시작될 때 `ReadOnlySequence<T>` 내에서 각 세그먼트의 시작으로 수정됩니다.

위의 메서드는 `ReadOnlySequence<T>`에 대한 확장 메서드로 존재합니다. <xref:System.Buffers.BuffersExtensions.PositionOf%2A>는 위의 코드를 간소화하는 데 사용할 수 있습니다.

```csharp
SequencePosition? FindIndexOf(in ReadOnlySequence<byte> buffer, byte data) => buffer.PositionOf(data);
```

#### <a name="process-a-readonlysequencet"></a>ReadOnlySequence\<T\> 처리

데이터가 시퀀스 내의 여러 세그먼트로 분할될 수 있으므로 `ReadOnlySequence<T>` 처리는 어려울 수 있습니다. 최상의 성능을 위해 코드를 다음 두 개의 경로로 분할합니다.

- 단일 세그먼트 케이스를 처리하는 빠른 경로.
- 여러 세그먼트로 분할된 데이터를 처리하는 느린 경로.

다중 분할된 시퀀스에서 데이터를 처리하는 데 사용할 수 있는 몇 가지 방법이 있습니다.

- [`SequenceReader<T>`](#sequencereadert)를 사용합니다.
- 구문 분석된 세그먼트 내에서 `SequencePosition` 및 인덱스를 추적하여 데이터를 세그먼트 단위로 구문 분석합니다. 이렇게 하면 불필요한 할당을 피할 수 있지만 특히 버퍼가 작은 경우에는 비효율적입니다.
- `ReadOnlySequence<T>`를 연속된 배열에 복사하고 단일 버퍼처럼 처리합니다.
  - `ReadOnlySequence<T>` 크기가 작으면 [stackalloc](../../csharp/language-reference/operators/stackalloc.md) 연산자를 사용하여 스택 할당 버퍼에 데이터를 복사하는 것이 합리적입니다.
  - <xref:System.Buffers.ArrayPool%601.Shared%2A?displayProperty=nameWithType>를 사용하여 `ReadOnlySequence<T>`를 풀링된 배열에 복사합니다.
  - [`ReadOnlySequence<T>.ToArray()`](xref:System.Buffers.BuffersExtensions.ToArray%2A)를 사용합니다. 이는 힙에서 새 `T[]`를 할당하므로 실행 부하 과다 경로에는 권장되지 않습니다.

다음 예제에서는 `ReadOnlySequence<byte>`를 처리하는 몇 가지 일반적인 사례를 보여 줍니다.

##### <a name="process-binary-data"></a>이진 데이터 처리

다음 예제에서는 `ReadOnlySequence<byte>`의 시작 부분에서 4바이트 Big Endian 정수 길이를 구문 분석합니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet5)]

[!INCLUDE [localized code comments](../../../includes/code-comments-loc.md)]

##### <a name="process-text-data"></a>텍스트 데이터 처리

다음 예제가 하는 일:

- `ReadOnlySequence<byte>`에서 첫 번째 줄 바꿈(`\r\n`)을 찾아 out 'line' 매개 변수를 통해 반환합니다.
- 입력 버퍼에서 `\r\n`을 제외하고 해당 줄을 자릅니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet6)]

##### <a name="empty-segments"></a>빈 세그먼트

`ReadOnlySequence<T>` 안에 빈 세그먼트를 저장하는 것은 유효합니다. 세그먼트를 명시적으로 열거하는 동안 빈 세그먼트가 발생할 수 있습니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet7)]

위의 코드는 빈 세그먼트를 사용하여 `ReadOnlySequence<byte>`를 만들고 이러한 빈 세그먼트가 다양한 API에 미치는 영향을 보여 줍니다.

- `SequencePosition`이 빈 세그먼트를 가리키는 `ReadOnlySequence<T>.Slice`는 해당 세그먼트를 유지합니다.
- 정수가 포함된 `ReadOnlySequence<T>.Slice`는 빈 세그먼트를 건너뜁니다.
- `ReadOnlySequence<T>`를 열거하면 빈 세그먼트가 열거됩니다.

### <a name="potential-problems-with-readonlysequencet-and-sequenceposition"></a>ReadOnlySequence\<T> 및 SequencePosition의 잠재적 문제점

`ReadOnlySequence<T>`/`SequencePosition`을 처리할 때 일반 `ReadOnlySpan<T>`/`ReadOnlyMemory<T>`/`T[]`/`int`에 비해 비정상적인 결과가 몇 가지 있습니다.

- `SequencePosition`은 절대 위치가 아니라 특정 `ReadOnlySequence<T>`의 위치 표식입니다. 특정 `ReadOnlySequence<T>`를 기준으로 하기 때문에 이 메서드가 시작된 `ReadOnlySequence<T>`의 외부에서 사용하는 경우 의미가 없습니다.
- `ReadOnlySequence<T>` 없이는 `SequencePosition`에서 산술 연산을 수행할 수 없습니다. 즉 `position++`와 같은 기본 작업을 실행하면 `ReadOnlySequence<T>.GetPosition(position, 1)`이 작성됩니다.
- `GetPosition(long)`은 음수 인덱스를 지원하지 **않습니다**. 즉, 모든 세그먼트를 탐색하지 않고 두 번째에서 마지막까지 문자를 가져올 수 없습니다.
- 두 개의 `SequencePosition`를 비교할 수 없어 다음 작업을 수행하기 어렵습니다.
  - 한 위치가 다른 위치보다 크거나 작은 경우를 확인합니다.
  - 몇 가지 구문 분석 알고리즘을 작성합니다.
- `ReadOnlySequence<T>`는 개체 참조보다 크고, 가능하면 [in](../../csharp/language-reference/keywords/in-parameter-modifier.md) 또는 [ref](../../csharp/language-reference/keywords/ref.md)에 의해 전달되어야 합니다. `in` 또는 `ref`를 통해 `ReadOnlySequence<T>`를 전달하면 [구조체](../../csharp/language-reference/builtin-types/struct.md) 복사본이 줄어듭니다.
- 빈 세그먼트:
  - `ReadOnlySequence<T>` 내에서 유효합니다.
  - `ReadOnlySequence<T>.TryGet` 메서드를 사용하여 반복할 때 표시될 수 있습니다.
  - `ReadOnlySequence<T>.Slice()` 메서드와 `SequencePosition` 개체를 사용하여 시퀀스를조각화할 수 있습니다.

## <a name="sequencereadert"></a>SequenceReader\<T\>

<xref:System.Buffers.SequenceReader%601>:

- `ReadOnlySequence<T>` 처리를 간소화하기 위해 .NET Core 3.0에 도입된 새로운 형식입니다.
- 단일 세그먼트 `ReadOnlySequence<T>`와 다중 세그먼트 `ReadOnlySequence<T>` 간의 차이를 통합합니다.
- 세그먼트 간에 분할될 수 있거나 분할될 수 없는 이진 및 텍스트 데이터(`byte` 및 `char`)를 읽기 위한 도우미를 제공합니다.

이진 데이터와 구분된 데이터를 모두 처리하는 기본 제공 메서드가 있습니다. 다음 섹션에서는 이러한 메서드가 `SequenceReader<T>`에서 어떻게 나타나는지 보여 줍니다.

### <a name="access-data"></a>데이터 액세스

`SequenceReader<T>`에는 `ReadOnlySequence<T>` 내에서 직접 데이터를 열거하는 메서드가 있습니다. 다음 코드는 `ReadOnlySequence<byte>`를 한 번에 `byte` 처리하는 예제입니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet8)]

`CurrentSpan`는 현재 세그먼트의 `Span`을 노출합니다. 이는 메서드에서 수동으로 수행된 것과 비슷합니다.

### <a name="use-position"></a>위치 사용

다음 코드는 `SequenceReader<T>`를 사용한 `FindIndexOf` 구현 예제입니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet9)]

### <a name="process-binary-data"></a>이진 데이터 처리

다음 예제에서는 `ReadOnlySequence<byte>`의 시작 부분에서 4바이트 Big Endian 정수 길이를 구문 분석합니다.

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet11)]

### <a name="process-text-data"></a>텍스트 데이터 처리

[!code-csharp[](~/samples/snippets/csharp/buffers/MyClass.cs?name=snippet10)]

### <a name="sequencereadert-common-problems"></a>SequenceReader\<T\>의 일반적인 문제

- `SequenceReader<T>`는 변경 가능한 구조체이므로 항상 [reference](../../csharp/language-reference/keywords/ref.md)로 전달되어야 합니다.
- `SequenceReader<T>`는 [ref struct](../../csharp/language-reference/builtin-types/struct.md#ref-struct)이므로 동기 메서드에만 사용할 수 있고 필드에 저장할 수 없습니다. 자세한 내용은 [안전하고 효율적인 C# 코드 작성](../../csharp/write-safe-efficient-code.md)을 참조하세요.
- `SequenceReader<T>`는 정방향 전용 판독기로 사용하도록 최적화되어 있습니다. `Rewind`는 다른 `Read`, `Peek`및 `IsNext` API를 활용하여 해결할 수 없는 작은 백업에 사용됩니다.
