---
title: Memory<T> 및 Span<T> 사용 지침
description: 이 문서에서는 파이프라인에서 사용할 수 있는 .NET Core의 구조적 데이터 버퍼인 Memory<T> 및 Span<T>에 대해 설명합니다.
ms.date: 10/01/2018
helpviewer_keywords:
- Memory&lt;T&gt; and Span&lt;T&gt; best practices
- using Memory&lt;T&gt; and Span&lt;T&gt;
ms.openlocfilehash: d9a50fa18e027b6df7415438e1a5584003f7a094
ms.sourcegitcommit: 358a28048f36a8dca39a9fe6e6ac1f1913acadd5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/23/2020
ms.locfileid: "85245598"
---
# <a name="memoryt-and-spant-usage-guidelines"></a><span data-ttu-id="7f46b-103">Memory\<T> 및 Span\<T> 사용 지침</span><span class="sxs-lookup"><span data-stu-id="7f46b-103">Memory\<T> and Span\<T> usage guidelines</span></span>

<span data-ttu-id="7f46b-104">.NET Core에는 메모리의 인접한 임의 영역을 나타내는 여러 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-104">.NET Core includes a number of types that represent an arbitrary contiguous region of memory.</span></span> <span data-ttu-id="7f46b-105">.NET Core 2.0에서는 관리형 또는 비관리형 메모리로 지원할 수 있는 경량 메모리 버퍼인 <xref:System.Span%601> 및 <xref:System.ReadOnlySpan%601>이 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-105">.NET Core 2.0 introduced <xref:System.Span%601> and <xref:System.ReadOnlySpan%601>, which are lightweight memory buffers that can be backed by managed or unmanaged memory.</span></span> <span data-ttu-id="7f46b-106">이러한 형식은 스택에만 저장될 수 있기 때문에 비동기 메서드 호출을 포함한 여러 시나리오에 적합하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-106">Because these types can only be stored on the stack, they are unsuitable for a number of scenarios, including asynchronous method calls.</span></span> <span data-ttu-id="7f46b-107">.NET Core 2.1에서는 <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601> 및 <xref:System.Buffers.MemoryPool%601>을 포함한 여러 형식이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-107">.NET Core 2.1 adds a number of additional types, including <xref:System.Memory%601>, <xref:System.ReadOnlyMemory%601>, <xref:System.Buffers.IMemoryOwner%601>, and <xref:System.Buffers.MemoryPool%601>.</span></span> <span data-ttu-id="7f46b-108"><xref:System.Span%601>과 마찬가지로, <xref:System.Memory%601> 및 관련 형식은 관리형 및 비관리형 메모리 둘 다로 지원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-108">Like <xref:System.Span%601>, <xref:System.Memory%601> and its related types can be backed by both managed and unmanaged memory.</span></span> <span data-ttu-id="7f46b-109"><xref:System.Span%601>과 달리, <xref:System.Memory%601>는 관리형 힙에 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-109">Unlike <xref:System.Span%601>, <xref:System.Memory%601> can be stored on the managed heap.</span></span>

<span data-ttu-id="7f46b-110"><xref:System.Span%601> 및 <xref:System.Memory%601>는 둘 다 파이프라인에 사용할 수 있는 구조적 데이터의 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-110">Both <xref:System.Span%601> and <xref:System.Memory%601> are buffers of structured data that can be used in pipelines.</span></span> <span data-ttu-id="7f46b-111">즉, 일부 또는 모든 데이터가 파이프라인의 구성 요소에 효율적으로 전달될 수 있도록 설계되었으며, 해당 구성 요소는 데이터를 처리하고 선택적으로 버퍼를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-111">That is, they are designed so that some or all of the data can be efficiently passed to components in the pipeline, which can process them and optionally modify the buffer.</span></span> <span data-ttu-id="7f46b-112"><xref:System.Memory%601> 및 관련 형식은 여러 구성 요소나 여러 스레드에서 액세스할 수 있으므로 개발자가 몇 가지 표준 사용법 지침에 따라 강력한 코드를 생성하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-112">Because <xref:System.Memory%601> and its related types can be accessed by multiple components or by multiple threads, it's important that developers follow some standard usage guidelines to produce robust code.</span></span>

## <a name="owners-consumers-and-lifetime-management"></a><span data-ttu-id="7f46b-113">소유자, 소비자 및 수명 관리</span><span class="sxs-lookup"><span data-stu-id="7f46b-113">Owners, consumers, and lifetime management</span></span>

<span data-ttu-id="7f46b-114">API 간에 버퍼를 전달할 수 있으며, 때때로 여러 스레드에서 버퍼에 액세스할 수 있으므로 수명 관리를 고려하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-114">Since buffers can be passed around between APIs, and since buffers can sometimes be accessed from multiple threads, it's important to consider lifetime management.</span></span> <span data-ttu-id="7f46b-115">다음 세 가지 핵심 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-115">There are three core concepts:</span></span>

- <span data-ttu-id="7f46b-116">**소유권**.</span><span class="sxs-lookup"><span data-stu-id="7f46b-116">**Ownership**.</span></span> <span data-ttu-id="7f46b-117">버퍼 인스턴스의 소유자는 더 이상 사용하지 않는 버퍼 삭제를 포함하여 수명 관리를 책임집니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-117">The owner of a buffer instance is responsible for lifetime management, including destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="7f46b-118">모든 버퍼에 단일 소유자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-118">All buffers have a single owner.</span></span> <span data-ttu-id="7f46b-119">일반적으로 소유자는 버퍼를 만들었거나 팩터리에서 버퍼를 수신한 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-119">Generally the owner is the component that created the buffer or that received the buffer from a factory.</span></span> <span data-ttu-id="7f46b-120">소유권을 양도할 수도 있습니다. **Component-A**가 버퍼 제어를 **Component-B**에 양도할 수 있으며, 이 시점부터 **Component-A**는 더 이상 버퍼를 사용할 수 없고 **Component-B**가 더 이상 사용하지 않는 버퍼 삭제를 책임집니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-120">Ownership can also be transferred; **Component-A** can relinquish control of the buffer to **Component-B**, at which point **Component-A** may no longer use the buffer, and **Component-B** becomes responsible for destroying the buffer when it's no longer in use.</span></span>

- <span data-ttu-id="7f46b-121">**소비**.</span><span class="sxs-lookup"><span data-stu-id="7f46b-121">**Consumption**.</span></span> <span data-ttu-id="7f46b-122">버퍼 인스턴스의 소비자는 버퍼 인스턴스를 읽고 써서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-122">The consumer of a buffer instance is allowed to use the buffer instance by reading from it and possibly writing to it.</span></span> <span data-ttu-id="7f46b-123">외부 동기화 메커니즘을 제공하지 않으면 버퍼는 한 번에 하나의 소비자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-123">Buffers can have one consumer at a time unless some external synchronization mechanism is provided.</span></span> <span data-ttu-id="7f46b-124">버퍼의 활성 소비자는 버퍼의 소유자가 아니어도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-124">The active consumer of a buffer isn't necessarily the buffer's owner.</span></span>

- <span data-ttu-id="7f46b-125">**임대 시간**.</span><span class="sxs-lookup"><span data-stu-id="7f46b-125">**Lease**.</span></span> <span data-ttu-id="7f46b-126">임대 시간은 특정 구성 요소가 버퍼의 소비자가 될 수 있는 기간입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-126">The lease is the length of time that a particular component is allowed to be the consumer of the buffer.</span></span>

<span data-ttu-id="7f46b-127">다음 의사 코드 예제에서는 이러한 세 가지 개념을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-127">The following pseudo-code example illustrates these three concepts.</span></span> <span data-ttu-id="7f46b-128"><xref:System.Char> 형식의 <xref:System.Memory%601> 버퍼를 인스턴스화하는 `Main` 메서드를 포함하고, `WriteInt32ToBuffer` 메서드를 호출하여 정수의 문자열 표현을 버퍼에 쓴 다음, `DisplayBufferToConsole` 메서드를 호출하여 버퍼의 값을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-128">It includes a `Main` method that instantiates a <xref:System.Memory%601> buffer of type <xref:System.Char>, calls the `WriteInt32ToBuffer` method to write the string representation of an integer to the buffer, and then calls the `DisplayBufferToConsole` method to display the value of the buffer.</span></span>

```csharp
using System;

class Program
{
    // Write 'value' as a human-readable string to the output buffer.
    void WriteInt32ToBuffer(int value, Buffer buffer);

    // Display the contents of the buffer to the console.
    void DisplayBufferToConsole(Buffer buffer);

    // Application code
    static void Main()
    {
        var buffer = CreateBuffer();
        try
        {
            int value = Int32.Parse(Console.ReadLine());
            WriteInt32ToBuffer(value, buffer);
            DisplayBufferToConsole(buffer);
        }
        finally
        {
            buffer.Destroy();
        }
    }
}
```

<span data-ttu-id="7f46b-129">`Main` 메서드가 버퍼(이 경우 <xref:System.Span%601> 인스턴스)를 만들기 때문에 해당 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-129">The `Main` method creates the buffer (in this case an <xref:System.Span%601> instance) and so is its owner.</span></span> <span data-ttu-id="7f46b-130">따라서 `Main`이 더 이상 사용하지 않는 버퍼 삭제를 책임집니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-130">Therefore, `Main` is responsible for destroying the buffer when it's no longer in use.</span></span> <span data-ttu-id="7f46b-131">이 메서드는 버퍼의 <xref:System.Span%601.Clear?displayProperty=nameWithType> 메서드를 호출하여 삭제 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-131">It does this by calling the buffer's <xref:System.Span%601.Clear?displayProperty=nameWithType> method.</span></span> <span data-ttu-id="7f46b-132">여기서는 <xref:System.Span%601.Clear> 메서드가 실제로 메모리를 지웁니다. <xref:System.Span%601> 구조체에는 실제로 버퍼를 삭제하는 메서드가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-132">(The <xref:System.Span%601.Clear> method here actually clears the buffer's memory; the <xref:System.Span%601> structure doesn't actually have a method that destroys the buffer.)</span></span>

<span data-ttu-id="7f46b-133">버퍼에는 두 개의 소비자 `WriteInt32ToBuffer` 및 `DisplayBufferToConsole`이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-133">The buffer has two consumers, `WriteInt32ToBuffer` and `DisplayBufferToConsole`.</span></span> <span data-ttu-id="7f46b-134">한 번에 하나의 소비자만 있고(`WriteInt32ToBuffer`, `DisplayBufferToConsole` 순), 두 소비자 모두 버퍼를 소유하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-134">There is only one consumer at a time (first `WriteInt32ToBuffer`, then `DisplayBufferToConsole`), and neither of the consumers owns the buffer.</span></span> <span data-ttu-id="7f46b-135">또한 이 컨텍스트의 “소비자”는 버퍼의 읽기 전용 보기를 암시하지 않습니다. 버퍼의 읽기/쓰기 보기가 제공되면 `WriteInt32ToBuffer`와 같이 소비자가 버퍼 내용을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-135">Note also that "consumer" in this context doesn't imply a read-only view of the buffer; consumers can modify the buffer's contents, as `WriteInt32ToBuffer` does, if given a read/write view of the buffer.</span></span>

<span data-ttu-id="7f46b-136">`WriteInt32ToBuffer` 메서드는 메서드 호출 시작과 메서드가 반환되는 시간 사이에 버퍼를 임대합니다(사용할 수 있음).</span><span class="sxs-lookup"><span data-stu-id="7f46b-136">The `WriteInt32ToBuffer` method has a lease on (can consume) the buffer between the start of the method call and the time the method returns.</span></span> <span data-ttu-id="7f46b-137">마찬가지로, `DisplayBufferToConsole`은 버퍼가 실행되는 동안 버퍼를 임대하고, 메서드가 해제되면 임대가 해제됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-137">Similarly, `DisplayBufferToConsole` has a lease on the buffer while it's executing, and the lease is released when the method unwinds.</span></span> <span data-ttu-id="7f46b-138">임대 관리에 대한 API는 없습니다. “임대”는 개념적 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-138">(There is no API for lease management; a "lease" is a conceptual matter.)</span></span>

## <a name="memoryt-and-the-ownerconsumer-model"></a><span data-ttu-id="7f46b-139">Memory\<T> 및 소유자/소비자 모델</span><span class="sxs-lookup"><span data-stu-id="7f46b-139">Memory\<T> and the owner/consumer model</span></span>

<span data-ttu-id="7f46b-140">[소유자, 소비자 및 수명 관리](#owners-consumers-and-lifetime-management) 섹션에 설명된 대로, 버퍼에는 항상 하나의 소유자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-140">As the [Owners, consumers, and lifetime management](#owners-consumers-and-lifetime-management) section notes, a buffer always has an owner.</span></span> <span data-ttu-id="7f46b-141">.NET Core는 다음 두 가지 소유권 모델을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-141">.NET Core supports two ownership models:</span></span>

- <span data-ttu-id="7f46b-142">단일 소유권을 지원하는 모델.</span><span class="sxs-lookup"><span data-stu-id="7f46b-142">A model that supports single ownership.</span></span> <span data-ttu-id="7f46b-143">전체 수명 동안 버퍼에 단일 소유자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-143">A buffer has a single owner for its entire lifetime.</span></span>

- <span data-ttu-id="7f46b-144">소유권 이전을 지원하는 모델.</span><span class="sxs-lookup"><span data-stu-id="7f46b-144">A model that supports ownership transfer.</span></span> <span data-ttu-id="7f46b-145">버퍼의 소유권을 원래 소유자(생성자)에서 다른 구성 요소로 양도할 수 있으며, 그 후에는 해당 구성 요소가 버퍼의 수명 관리를 책임집니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-145">Ownership of a buffer can be transferred from its original owner (its creator) to another component, which then becomes responsible for the buffer's lifetime management.</span></span> <span data-ttu-id="7f46b-146">이 소유자는 다시 소유권을 다른 구성 요소에 이전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-146">That owner can in turn transfer ownership to another component, and so on.</span></span>

<span data-ttu-id="7f46b-147"><xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> 인터페이스를 사용하여 버퍼의 소유권을 명시적으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-147">You use the <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType> interface to explicitly manage the ownership of a buffer.</span></span> <span data-ttu-id="7f46b-148"><xref:System.Buffers.IMemoryOwner%601>는 두 소유권 모델을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-148"><xref:System.Buffers.IMemoryOwner%601> supports both ownership models.</span></span> <span data-ttu-id="7f46b-149"><xref:System.Buffers.IMemoryOwner%601> 참조가 있는 구성 요소가 버퍼를 소유합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-149">The component that has an <xref:System.Buffers.IMemoryOwner%601> reference owns the buffer.</span></span> <span data-ttu-id="7f46b-150">다음 예제에서는 <xref:System.Buffers.IMemoryOwner%601?> 인스턴스를 사용하여 <xref:System.Memory%601> 버퍼의 소유권을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-150">The following example uses an <xref:System.Buffers.IMemoryOwner%601?> instance to reflect the ownership of a <xref:System.Memory%601> buffer.</span></span>

[!code-csharp[ownership](~/samples/snippets/standard/buffers/memory-t/owner/owner.cs)]

<span data-ttu-id="7f46b-151">[`using`](../../csharp/language-reference/keywords/using-statement.md)을 사용하여 이 예제를 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-151">We can also write this example with the [`using`](../../csharp/language-reference/keywords/using-statement.md):</span></span>

[!code-csharp[ownership-using](~/samples/snippets/standard/buffers/memory-t/owner-using/owner-using.cs)]

<span data-ttu-id="7f46b-152">이 코드에서는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-152">In this code:</span></span>

- <span data-ttu-id="7f46b-153">`Main` 메서드에 <xref:System.Buffers.IMemoryOwner%601> 인스턴스에 대한 참조가 있으므로 `Main` 메서드가 버퍼의 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-153">The `Main` method holds the reference to the <xref:System.Buffers.IMemoryOwner%601> instance, so the `Main` method is the owner of the buffer.</span></span>

- <span data-ttu-id="7f46b-154">`WriteInt32ToBuffer` 및 `DisplayBufferToConsole` 메서드는 공용 API로 <xref:System.Memory%601>를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-154">The `WriteInt32ToBuffer` and `DisplayBufferToConsole` methods accept <xref:System.Memory%601> as a public API.</span></span> <span data-ttu-id="7f46b-155">따라서 버퍼의 소비자가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-155">Therefore, they are consumers of the buffer.</span></span> <span data-ttu-id="7f46b-156">또한 한 번에 하나씩 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-156">And they only consume it one at a time.</span></span>

<span data-ttu-id="7f46b-157">`WriteInt32ToBuffer` 메서드는 버퍼에 값을 쓰기 위한 것이지만 `DisplayBufferToConsole` 메서드는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-157">Although the `WriteInt32ToBuffer` method is intended to write a value to the buffer, the `DisplayBufferToConsole` method isn't.</span></span> <span data-ttu-id="7f46b-158">이를 반영하기 위해 <xref:System.ReadOnlyMemory%601> 형식의 인수를 허용했을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-158">To reflect this, it could have accepted an argument of type <xref:System.ReadOnlyMemory%601>.</span></span> <span data-ttu-id="7f46b-159"><xref:System.ReadOnlyMemory%601>에 대한 자세한 내용은 [Rule #2: 버퍼가 읽기 전용이어야 하는 경우 ReadOnlySpan\<T> 또는 ReadOnlyMemory\<T> 사용](#rule-2)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f46b-159">For more information on <xref:System.ReadOnlyMemory%601>, see [Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only](#rule-2).</span></span>

### <a name="ownerless-memoryt-instances"></a><span data-ttu-id="7f46b-160">"소유자가 없는" Memory\<T> 인스턴스</span><span class="sxs-lookup"><span data-stu-id="7f46b-160">"Ownerless" Memory\<T> instances</span></span>

<span data-ttu-id="7f46b-161"><xref:System.Buffers.IMemoryOwner%601>를 사용하지 않고 <xref:System.Memory%601> 인스턴스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-161">You can create a <xref:System.Memory%601> instance without using <xref:System.Buffers.IMemoryOwner%601>.</span></span> <span data-ttu-id="7f46b-162">이 경우 버퍼의 소유권은 명시적이 아니라 암시적이며 단일 소유자 모델만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-162">In this case, ownership of the buffer is implicit rather than explicit, and only the single-owner model is supported.</span></span> <span data-ttu-id="7f46b-163">이렇게 하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-163">You can do this by:</span></span>

- <span data-ttu-id="7f46b-164">다음 예제와 같이 `T[]`를 전달하여 <xref:System.Memory%601> 생성자 중 하나를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-164">Calling one of the  <xref:System.Memory%601> constructors directly, passing in a `T[]`, as the following example does.</span></span>

- <span data-ttu-id="7f46b-165">[String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) 확장 메서드를 호출하여 `ReadOnlyMemory<char>` 인스턴스를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-165">Calling the [String.AsMemory](xref:System.MemoryExtensions.AsMemory(System.String)) extension method to produce a `ReadOnlyMemory<char>` instance.</span></span>

[!code-csharp[ownerless-memory](~/samples/snippets/standard/buffers/memory-t/ownerless/ownerless.cs)]

<span data-ttu-id="7f46b-166">처음에 <xref:System.Memory%601> 인스턴스를 만드는 메서드가 버퍼의 암시적 소유자입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-166">The method that initially creates the <xref:System.Memory%601> instance is the implicit owner of the buffer.</span></span> <span data-ttu-id="7f46b-167">이전을 지원하는 <xref:System.Buffers.IMemoryOwner%601> 인스턴스가 없으므로 소유권을 다른 구성 요소에 이전할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-167">Ownership cannot be transferred to any other component because there is no <xref:System.Buffers.IMemoryOwner%601> instance to facilitate the transfer.</span></span> <span data-ttu-id="7f46b-168">또는 런타임의 가비지 수집기가 버퍼를 소유하고, 모든 메서드는 버퍼를 사용하기만 한다고 가정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-168">(As an alternative, you can also imagine that the runtime's garbage collector owns the buffer, and all methods just consume the buffer.)</span></span>

## <a name="usage-guidelines"></a><span data-ttu-id="7f46b-169">사용 지침</span><span class="sxs-lookup"><span data-stu-id="7f46b-169">Usage guidelines</span></span>

<span data-ttu-id="7f46b-170">메모리 블록은 소유되지만 여러 구성 요소에 전달되고, 이 중에서 일부가 특정 메모리 블록에서 동시에 작업할 수 있기 때문에 <xref:System.Memory%601> 및 <xref:System.Span%601> 사용 방법에 대한 지침을 설정하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-170">Because a memory block is owned but is intended to be passed to multiple components, some of which may operate upon a particular memory block simultaneously, it is important to establish guidelines for using both <xref:System.Memory%601> and <xref:System.Span%601>.</span></span>  <span data-ttu-id="7f46b-171">지침이 필요한 이유는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-171">Guidelines are necessary because:</span></span>

- <span data-ttu-id="7f46b-172">소유자가 해제한 후에도 구성 요소가 메모리 블록에 대한 참조를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-172">It is possible for a component to retain a reference to a memory block after its owner has released it.</span></span>

- <span data-ttu-id="7f46b-173">다른 구성 요소가 작업 중인 버퍼에 대해 구성 요소가 동시에 작업하여 버퍼의 데이터가 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-173">It is possible for a component to operate on a buffer at the same time that another component is operating on it, in the process corrupting the data in the buffer.</span></span>

- <span data-ttu-id="7f46b-174"><xref:System.Span%601>의 스택 할당 특성은 성능을 최적화하고 <xref:System.Span%601>을 메모리 블록에서 작업하는 기본 형식으로 설정하는 반면, <xref:System.Span%601>에 몇 가지 주요 제한 사항이 적용되게도 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-174">While the stack-allocated nature of <xref:System.Span%601> optimizes performance and makes <xref:System.Span%601> the preferred type for operating on a memory block, it also subjects <xref:System.Span%601> to some major restrictions.</span></span> <span data-ttu-id="7f46b-175"><xref:System.Span%601>을 사용해야 하는 경우와 <xref:System.Memory%601>를 사용해야 하는 경우를 아는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-175">It is important to know when to use a <xref:System.Span%601> and when to use <xref:System.Memory%601>.</span></span>

<span data-ttu-id="7f46b-176">다음은 <xref:System.Memory%601> 및 관련 형식을 성공적으로 사용하기 위한 권장 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-176">The following are our recommendations for successfully using <xref:System.Memory%601> and its related types.</span></span> <span data-ttu-id="7f46b-177"><xref:System.Memory%601> 및 <xref:System.Span%601>에 적용되는 지침은 명시적으로 달리 언급되지 않는 한 <xref:System.ReadOnlyMemory%601> 및 <xref:System.ReadOnlySpan%601>에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-177">Guidance that applies to <xref:System.Memory%601> and <xref:System.Span%601> also applies to <xref:System.ReadOnlyMemory%601> and <xref:System.ReadOnlySpan%601> unless we explicitly note otherwise.</span></span>

<span data-ttu-id="7f46b-178">**규칙 #1: 동기 API의 경우 가능하면 Memory\<T> 대신 Span\<T>를 매개 변수로 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f46b-178">**Rule #1: For a synchronous API, use Span\<T> instead of Memory\<T> as a parameter if possible.**</span></span>

<span data-ttu-id="7f46b-179"><xref:System.Span%601>은 <xref:System.Memory%601>보다 유연하며 더 광범위한 인접한 메모리 버퍼를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-179"><xref:System.Span%601> is more versatile than <xref:System.Memory%601> and can represent a wider variety of contiguous memory buffers.</span></span> <span data-ttu-id="7f46b-180">또한 <xref:System.Span%601>은 <xref:System.Memory%601>보다 나은 성능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-180"><xref:System.Span%601> also offers better performance than <xref:System.Memory%601>.</span></span> <span data-ttu-id="7f46b-181">마지막으로 <xref:System.Memory%601.Span?displayProperty=nameWithType> 속성을 사용하여 <xref:System.Memory%601> 인스턴스를 <xref:System.Span%601>으로 변환할 수 있습니다. 단, Span\<T>-Memory\<T> 변환은 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-181">Finally, you can use the <xref:System.Memory%601.Span?displayProperty=nameWithType> property to convert a <xref:System.Memory%601> instance to a <xref:System.Span%601>, although Span\<T>-to-Memory\<T> conversion isn't possible.</span></span> <span data-ttu-id="7f46b-182">따라서 호출자에게 <xref:System.Memory%601> 인스턴스가 있는 경우 <xref:System.Span%601> 매개 변수를 사용하여 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-182">So if your callers happen to have a <xref:System.Memory%601> instance, they'll be able to call your methods with <xref:System.Span%601> parameters anyway.</span></span>

<span data-ttu-id="7f46b-183"><xref:System.Memory%601> 형식 대신 <xref:System.Span%601> 형식의 매개 변수를 사용하면 올바른 소비 메서드 구현을 작성하는 데에도 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-183">Using a parameter of type <xref:System.Span%601> instead of type <xref:System.Memory%601> also helps you write a correct consuming method implementation.</span></span> <span data-ttu-id="7f46b-184">메서드의 임대 기간을 지나서 버퍼에 액세스를 시도하지 않는지 확인하기 위해 자동으로 컴파일 시간 검사가 수행됩니다(뒷부분에서 자세히 설명).</span><span class="sxs-lookup"><span data-stu-id="7f46b-184">You'll automatically get compile-time checks to ensure that you're not attempting to access the buffer beyond your method's lease (more on this later).</span></span>

<span data-ttu-id="7f46b-185">때로는 완전히 동기인 경우에도 <xref:System.Span%601> 매개 변수 대신 <xref:System.Memory%601> 매개 변수를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-185">Sometimes, you'll have to use a <xref:System.Memory%601> parameter instead of a <xref:System.Span%601> parameter, even if you're fully synchronous.</span></span> <span data-ttu-id="7f46b-186">사용하는 API가 <xref:System.Memory%601> 인수만 허용하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-186">Perhaps an API that you depend accepts only <xref:System.Memory%601> arguments.</span></span> <span data-ttu-id="7f46b-187">이 동작은 정상적이지만, <xref:System.Memory%601>를 동기적으로 사용하는 경우 관련된 절충에 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-187">This is fine, but be aware of the tradeoffs involved when using <xref:System.Memory%601> synchronously.</span></span>

<a name="rule-2"></a>

<span data-ttu-id="7f46b-188">**규칙 #2: 버퍼가 읽기 전용이어야 하는 경우 ReadOnlySpan\<T> 또는 ReadOnlyMemory\<T> 사용**을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f46b-188">**Rule #2: Use ReadOnlySpan\<T> or ReadOnlyMemory\<T> if the buffer should be read-only.**</span></span>

<span data-ttu-id="7f46b-189">앞의 예제에서 `DisplayBufferToConsole` 메서드는 버퍼에서 읽기만 하고 버퍼 내용을 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-189">In the earlier examples, the `DisplayBufferToConsole` method only reads from the buffer; it doesn't modify the contents of the buffer.</span></span> <span data-ttu-id="7f46b-190">메서드 시그니처를 다음으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-190">The method signature should be changed to the following.</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlyMemory<char> buffer);
```

<span data-ttu-id="7f46b-191">실제로 이 규칙과 규칙 #1을 결합하면 더 나은 결과를 얻을 수 있으며, 다음과 같이 메서드 시그니처를 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-191">In fact, if we combine this rule and Rule #1, we can do even better and rewrite the method signature as follows:</span></span>

```csharp
void DisplayBufferToConsole(ReadOnlySpan<char> buffer);
```

<span data-ttu-id="7f46b-192">이제 `DisplayBufferToConsole` 메서드는 `T[]`, [stackalloc](../../csharp/language-reference/operators/stackalloc.md)로 할당된 스토리지 등 거의 모든 버퍼 형식에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-192">The `DisplayBufferToConsole` method now works with virtually every buffer type imaginable: `T[]`, storage allocated with [stackalloc](../../csharp/language-reference/operators/stackalloc.md), and so on.</span></span> <span data-ttu-id="7f46b-193">이 메서드에 <xref:System.String>을 직접 전달할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-193">You can even pass a <xref:System.String> directly into it!</span></span>

<span data-ttu-id="7f46b-194">**규칙 #3: 메서드가 Memory\<T>를 사용하고 `void`를 반환하는 경우 메서드가 반환된 후에는 Memory\<T> 인스턴스를 사용하면 안 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7f46b-194">**Rule #3: If your method accepts Memory\<T> and returns `void`, you must not use the Memory\<T> instance after your method returns.**</span></span>

<span data-ttu-id="7f46b-195">이 내용은 앞에서 언급한 “임대 기간” 개념과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-195">This relates to the "lease" concept mentioned earlier.</span></span> <span data-ttu-id="7f46b-196"><xref:System.Memory%601> 인스턴스에 대한 void 반환 메서드의 임대 기간은 메서드가 시작될 때 시작되고 메서드가 종료될 때 종료됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-196">A void-returning method's lease on the <xref:System.Memory%601> instance begins when the method is entered, and it ends when the method exits.</span></span> <span data-ttu-id="7f46b-197">콘솔의 입력에 따라 루프에서 `Log`를 호출하는 다음 예제를 고려해 보세요.</span><span class="sxs-lookup"><span data-stu-id="7f46b-197">Consider the following example, which calls `Log` in a loop based on input from the console.</span></span>

[!code-csharp[void-returning](~/samples/snippets/standard/buffers/memory-t/void-returning/void-returning.cs#1)]

<span data-ttu-id="7f46b-198">`Log`가 완전히 동기 메서드인 경우에는 메모리 인스턴스의 활성 소비자가 항상 하나뿐이므로 이 코드가 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-198">If `Log` is a fully synchronous method, this code will behave as expected because there is only one active consumer of the memory instance at any given time.</span></span>
<span data-ttu-id="7f46b-199">그러나 `Log`에 이 구현이 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-199">But imagine instead that `Log` has this implementation.</span></span>

```csharp
// !!! INCORRECT IMPLEMENTATION !!!
static void Log(ReadOnlyMemory<char> message)
{
    // Run in background so that we don't block the main thread while performing IO.
    Task.Run(() =>
    {
        StreamWriter sw = File.AppendText(@".\input-numbers.dat");
        sw.WriteLine(message);
    });
}
```

<span data-ttu-id="7f46b-200">이 구현에서 `Log`는 원래 메서드가 반환된 후에도 백그라운드에서 <xref:System.Memory%601> 인스턴스를 계속 사용하려고 시도하기 때문에 해당 임대 기간을 위반합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-200">In this implementation, `Log` violates its lease because it still attempts to use the <xref:System.Memory%601> instance in the background after the original method has returned.</span></span> <span data-ttu-id="7f46b-201">`Log`가 읽는 동안 `Main` 메서드가 버퍼를 변경할 수 있으며, 이로 인해 데이터가 손상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-201">The `Main` method could mutate the buffer while `Log` attempts to read from it, which could result in data corruption.</span></span>

<span data-ttu-id="7f46b-202">이 문제를 해결하는 몇 가지 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-202">There are several ways to resolve this:</span></span>

- <span data-ttu-id="7f46b-203">다음과 같은 `Log` 메서드 구현처럼, `Log` 메서드가 `void` 대신 <xref:System.Threading.Tasks.Task>를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-203">The `Log` method can return a <xref:System.Threading.Tasks.Task> instead of `void`, as the following implementation of the `Log` method does.</span></span>

   [!code-csharp[task-returning](~/samples/snippets/standard/buffers/memory-t/task-returning2/task-returning2.cs#1)]

- <span data-ttu-id="7f46b-204">다음과 같이 `Log`를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-204">`Log` can instead be implemented as follows:</span></span>

   [!code-csharp[defensive-copy](~/samples/snippets/standard/buffers/memory-t/task-returning/task-returning.cs#1)]

<span data-ttu-id="7f46b-205">**규칙 #4: 메서드가 Memory\<T>를 사용하고 Task를 반환하는 경우, Task가 터미널 상태로 전환된 후에는 Memory\<T> 인스턴스를 사용하면 안 됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7f46b-205">**Rule #4: If your method accepts a Memory\<T> and returns a Task, you must not use the Memory\<T> instance after the Task transitions to a terminal state.**</span></span>

<span data-ttu-id="7f46b-206">이 규칙은 단순히 규칙 #3의 비동기 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-206">This is just the async variant of Rule #3.</span></span> <span data-ttu-id="7f46b-207">이 규칙을 준수하기 위해 이전 예제의 `Log` 메서드를 다음과 같이 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-207">The `Log` method from the earlier example can be written as follows to comply with this rule:</span></span>

[!code-csharp[task-returning-async](~/samples/snippets/standard/buffers/memory-t/void-returning-async/void-returning-async.cs#1)]

<span data-ttu-id="7f46b-208">여기서 “터미널 상태”는 Task가 완료됨, 오류 또는 취소됨 상태로 전환됨을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-208">Here, "terminal state" means that the task transitions to a completed, faulted, or canceled state.</span></span> <span data-ttu-id="7f46b-209">즉, “터미널 상태”는 “await에서 throw하거나 실행을 계속하게 하는 모든 것”을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-209">In other words, "terminal state" means "anything that would cause await to throw or to continue execution."</span></span>

<span data-ttu-id="7f46b-210">이 지침은 <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601> 또는 유사한 형식을 반환하는 메서드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-210">This guidance applies to methods that return <xref:System.Threading.Tasks.Task>, <xref:System.Threading.Tasks.Task%601>, <xref:System.Threading.Tasks.ValueTask%601>, or any similar type.</span></span>

<span data-ttu-id="7f46b-211">**규칙 #5: 생성자가 Memory\<T>를 매개 변수로 사용하는 경우 생성된 개체의 인스턴스 메서드가 Memory\<T> 인스턴스의 소비자로 간주됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7f46b-211">**Rule #5: If your constructor accepts Memory\<T> as a parameter, instance methods on the constructed object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="7f46b-212">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f46b-212">Consider the following example:</span></span>

```csharp
class OddValueExtractor
{
    public OddValueExtractor(ReadOnlyMemory<int> input);
    public bool TryReadNextOddValue(out int value);
}

void PrintAllOddValues(ReadOnlyMemory<int> input)
{
    var extractor = new OddValueExtractor(input);
    while (extractor.TryReadNextOddValue(out int value))
    {
      Console.WriteLine(value);
    }
}
```

<span data-ttu-id="7f46b-213">여기서 `OddValueExtractor` 생성자는 `ReadOnlyMemory<int>`를 생성자 매개 변수로 사용하므로 생성자 자체는 `ReadOnlyMemory<int>` 인스턴스의 소비자이며, 반환된 값의 모든 인스턴스 메서드도 원래 `ReadOnlyMemory<int>` 인스턴스의 소비자입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-213">Here, the `OddValueExtractor` constructor accepts a `ReadOnlyMemory<int>` as a constructor parameter, so the constructor itself is a consumer of the `ReadOnlyMemory<int>` instance, and all instance methods on the returned value are also consumers of the original `ReadOnlyMemory<int>` instance.</span></span> <span data-ttu-id="7f46b-214">즉, 인스턴스가 `TryReadNextOddValue` 메서드에 직접 전달되지 않더라도 `TryReadNextOddValue`가 `ReadOnlyMemory<int>` 인스턴스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-214">This means that `TryReadNextOddValue` consumes the `ReadOnlyMemory<int>` instance, even though the instance isn't passed directly to the `TryReadNextOddValue` method.</span></span>

<span data-ttu-id="7f46b-215">**규칙 #6: 설정 가능한 Memory\<T> 형식의 속성(또는 동등한 인스턴스 메서드)이 형식에 있는 경우 해당 개체의 인스턴스 메서드는 Memory\<T> 인스턴스의 소비자로 간주됩니다.**</span><span class="sxs-lookup"><span data-stu-id="7f46b-215">**Rule #6: If you have a settable Memory\<T>-typed property (or an equivalent instance method) on your type, instance methods on that object are assumed to be consumers of the Memory\<T> instance.**</span></span>

<span data-ttu-id="7f46b-216">이 규칙은 단순히 규칙 #5의 변형입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-216">This is really just a variant of Rule #5.</span></span> <span data-ttu-id="7f46b-217">이 규칙이 필요한 이유는 속성 setter 또는 이와 동등한 메서드가 해당 입력을 캡처하고 유지한다고 가정되므로 동일한 개체의 인스턴스 메서드가 캡처된 상태를 활용할 수 있기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-217">This rule exists because property setters or equivalent methods are assumed to capture and persist their inputs, so instance methods on the same object may utilize the captured state.</span></span>

<span data-ttu-id="7f46b-218">다음 예제는 이 규칙을 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-218">The following example triggers this rule:</span></span>

```csharp
class Person
{
    // Settable property.
    public Memory<char> FirstName { get; set; }

    // alternatively, equivalent "setter" method
    public SetFirstName(Memory<char> value);

    // alternatively, a public settable field
    public Memory<char> FirstName;
}
```

<span data-ttu-id="7f46b-219">**규칙 #7: IMemoryOwner\<T> 참조가 있는 경우 일정 시점에서 삭제하거나 해당 소유권을 이전해야 합니다(둘 다는 아님).**</span><span class="sxs-lookup"><span data-stu-id="7f46b-219">**Rule #7: If you have an IMemoryOwner\<T> reference, you must at some point dispose of it or transfer its ownership (but not both).**</span></span>

<span data-ttu-id="7f46b-220">관리형 또는 비관리형 메모리에서 <xref:System.Memory%601> 인스턴스를 지원할 수 있으므로 <xref:System.Memory%601> 인스턴스에서 수행된 작업이 완료되면 소유자가 <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-220">Since a <xref:System.Memory%601> instance may be backed by either managed or unmanaged memory, the owner must call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> when work performed on the <xref:System.Memory%601> instance is complete.</span></span> <span data-ttu-id="7f46b-221">또는 소유자가 <xref:System.Buffers.IMemoryOwner%601> 인스턴스의 소유권을 다른 구성 요소에 이전할 수 있습니다. 이 시점에서 획득하는 구성 요소는 적절한 시점에 <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>을 호출할 책임이 있습니다(뒷부분에서 자세히 설명).</span><span class="sxs-lookup"><span data-stu-id="7f46b-221">Alternatively, the owner may transfer ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component, at which point the acquiring component becomes responsible for calling <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType> at the appropriate time (more on this later).</span></span>

<span data-ttu-id="7f46b-222"><xref:System.Buffers.MemoryPool%601.Dispose%2A> 메서드를 호출하지 않으면 비관리형 메모리 누수 또는 기타 성능 저하가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-222">Failure to call the <xref:System.Buffers.MemoryPool%601.Dispose%2A> method may lead to unmanaged memory leaks or other performance degradation.</span></span>

<span data-ttu-id="7f46b-223">이 규칙은 <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType> 등의 팩터리 메서드를 호출하는 코드에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-223">This rule also applies to code that calls factory methods like <xref:System.Buffers.MemoryPool%601.Rent%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="7f46b-224">호출자는 반환된 <xref:System.Buffers.IMemoryOwner%601>의 소유자가 되며, 인스턴스가 완료되면 삭제할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-224">The caller becomes the owner of the returned <xref:System.Buffers.IMemoryOwner%601> and is responsible for disposing of the instance when finished.</span></span>

<span data-ttu-id="7f46b-225">**규칙 #8: API 노출 영역에 IMemoryOwner\<T> 매개 변수가 있는 경우 해당 인스턴스의 소유권을 허용하는 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="7f46b-225">**Rule #8: If you have an IMemoryOwner\<T> parameter in your API surface, you are accepting ownership of that instance.**</span></span>

<span data-ttu-id="7f46b-226">이 형식의 인스턴스를 허용하면 해당 구성 요소가 이 인스턴스를 소유하려고 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-226">Accepting an instance of this type signals that your component intends to take ownership of this instance.</span></span> <span data-ttu-id="7f46b-227">해당 구성 요소가 규칙 #7에 따라 적절하게 삭제할 책임이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-227">Your component becomes responsible for proper disposal according to Rule #7.</span></span>

<span data-ttu-id="7f46b-228"><xref:System.Buffers.IMemoryOwner%601> 인스턴스의 소유권을 다른 구성 요소에 이전하는 구성 요소는 메서드 호출이 완료된 후 해당 인스턴스를 더 이상 사용하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-228">Any component that transfers ownership of the <xref:System.Buffers.IMemoryOwner%601> instance to a different component should no longer use that instance after the method call completes.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7f46b-229">생성자가 <xref:System.Buffers.IMemoryOwner%601>를 매개 변수로 사용하는 경우 해당 형식이 <xref:System.IDisposable>을 구현해야 하며, <xref:System.IDisposable.Dispose%2A> 메서드가 <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>을 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-229">If your constructor accepts <xref:System.Buffers.IMemoryOwner%601> as a parameter, its type should implement <xref:System.IDisposable>, and your <xref:System.IDisposable.Dispose%2A> method should call <xref:System.Buffers.MemoryPool%601.Dispose%2A?displayProperty=nameWithType>.</span></span>

<span data-ttu-id="7f46b-230">**규칙 #9: 동기 P/Invoke 메서드를 래핑하는 경우 API가 Span\<T>를 매개 변수로 사용해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f46b-230">**Rule #9: If you're wrapping a synchronous p/invoke method, your API should accept Span\<T> as a parameter.**</span></span>

<span data-ttu-id="7f46b-231">규칙 #1에 따라 <xref:System.Span%601>은 일반적으로 동기 API에 사용할 올바른 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-231">According to Rule #1, <xref:System.Span%601> is generally the correct type to use for synchronous APIs.</span></span> <span data-ttu-id="7f46b-232">다음 예제와 같이 [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) 키워드를 통해 <xref:System.Span%601> 인스턴스를 고정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-232">You can pin <xref:System.Span%601> instances via the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword, as in the following example.</span></span>

```csharp
using System.Runtime.InteropServices;

[DllImport(...)]
private static extern unsafe int ExportedMethod(byte* pbData, int cbData);

public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        int retVal = ExportedMethod(pbData, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="7f46b-233">앞의 예제에서, 입력 범위가 비어 있는 경우 `pbData`는 Null일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-233">In the previous example, `pbData` can be null if, for example, the input span is empty.</span></span> <span data-ttu-id="7f46b-234">내보낸 메서드에서 `pbData`가 Null이 아니어야 하는 경우 `cbData`가 0이더라도 메서드를 다음과 같이 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-234">If the exported method absolutely requires that `pbData` be non-null, even if `cbData` is 0, the method can be implemented as follows:</span></span>

```csharp
public unsafe int ManagedWrapper(Span<byte> data)
{
    fixed (byte* pbData = &MemoryMarshal.GetReference(data))
    {
        byte dummy = 0;
        int retVal = ExportedMethod((pbData != null) ? pbData : &dummy, data.Length);

        /* error checking retVal goes here */

        return retVal;
    }
}
```

<span data-ttu-id="7f46b-235">**규칙 #10: 비동기 P/Invoke 메서드를 래핑하는 경우 API가 Memory\<T>를 매개 변수로 사용해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7f46b-235">**Rule #10: If you're wrapping an asynchronous p/invoke method, your API should accept Memory\<T> as a parameter.**</span></span>

<span data-ttu-id="7f46b-236">비동기 작업에서는 [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) 키워드를 사용할 수 없으므로 인스턴스가 나타내는 인접한 메모리 종류와 관계없이 <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> 메서드를 사용하여 <xref:System.Memory%601> 인스턴스를 고정합니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-236">Since you cannot use the [`fixed`](../../csharp/language-reference/keywords/fixed-statement.md) keyword across asynchronous operations, you use the <xref:System.Memory%601.Pin%2A?displayProperty=nameWithType> method to pin <xref:System.Memory%601> instances, regardless of the kind of contiguous memory the instance represents.</span></span> <span data-ttu-id="7f46b-237">다음 예제에서는 이 API를 사용하여 비동기 P/Invoke 호출을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7f46b-237">The following example shows how to use this API to perform an asynchronous p/invoke call.</span></span>

```csharp
using System.Runtime.InteropServices;

[UnmanagedFunctionPointer(...)]
private delegate void OnCompletedCallback(IntPtr state, int result);

[DllImport(...)]
private static extern unsafe int ExportedAsyncMethod(byte* pbData, int cbData, IntPtr pState, IntPtr lpfnOnCompletedCallback);

private static readonly IntPtr _callbackPtr = GetCompletionCallbackPointer();

public unsafe Task<int> ManagedWrapperAsync(Memory<byte> data)
{
    // setup
    var tcs = new TaskCompletionSource<int>();
    var state = new MyCompletedCallbackState
    {
        Tcs = tcs
    };
    var pState = (IntPtr)GCHandle.Alloc(state);

    var memoryHandle = data.Pin();
    state.MemoryHandle = memoryHandle;

    // make the call
    int result;
    try
    {
        result = ExportedAsyncMethod((byte*)memoryHandle.Pointer, data.Length, pState, _callbackPtr);
    }
    catch
    {
        ((GCHandle)pState).Free(); // cleanup since callback won't be invoked
        memoryHandle.Dispose();
        throw;
    }

    if (result != PENDING)
    {
        // Operation completed synchronously; invoke callback manually
        // for result processing and cleanup.
        MyCompletedCallbackImplementation(pState, result);
    }

    return tcs.Task;
}

private static void MyCompletedCallbackImplementation(IntPtr state, int result)
{
    GCHandle handle = (GCHandle)state;
    var actualState = (MyCompletedCallbackState)(handle.Target);
    handle.Free();
    actualState.MemoryHandle.Dispose();

    /* error checking result goes here */

    if (error)
    {
        actualState.Tcs.SetException(...);
    }
    else
    {
        actualState.Tcs.SetResult(result);
    }
}

private static IntPtr GetCompletionCallbackPointer()
{
    OnCompletedCallback callback = MyCompletedCallbackImplementation;
    GCHandle.Alloc(callback); // keep alive for lifetime of application
    return Marshal.GetFunctionPointerForDelegate(callback);
}

private class MyCompletedCallbackState
{
    public TaskCompletionSource<int> Tcs;
    public MemoryHandle MemoryHandle;
}
```

## <a name="see-also"></a><span data-ttu-id="7f46b-238">참조</span><span class="sxs-lookup"><span data-stu-id="7f46b-238">See also</span></span>

- <xref:System.Memory%601?displayProperty=nameWithType>
- <xref:System.Buffers.IMemoryOwner%601?displayProperty=nameWithType>
- <xref:System.Span%601?displayProperty=nameWithType>
