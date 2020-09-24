---
title: DisposeAsync 메서드 구현
description: DisposeAsync 및 DisposeAsyncCore 메서드를 구현하여 비동기 리소스 정리를 수행하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 09/16/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 6ddfd860571d883e20fdb18985fe2bc2d9477dec
ms.sourcegitcommit: fe8877e564deb68d77fa4b79f55584ac8d7e8997
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/17/2020
ms.locfileid: "90720285"
---
# <a name="implement-a-disposeasync-method"></a><span data-ttu-id="3de4a-103">DisposeAsync 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="3de4a-103">Implement a DisposeAsync method</span></span>

<span data-ttu-id="3de4a-104"><xref:System.IAsyncDisposable?displayProperty=nameWithType> 인터페이스는 C# 8.0의 일부로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-104">The <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface was introduced as part of C# 8.0.</span></span> <span data-ttu-id="3de4a-105"><xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 메서드는 [Dispose 메서드를 구현](implementing-dispose.md)할 때와 마찬가지로 리소스 정리를 수행하는 경우에 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-105">You implement the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method when you need to perform resource cleanup, just as you would when [implementing a Dispose method](implementing-dispose.md).</span></span> <span data-ttu-id="3de4a-106">그러나 중요한 차이점 하나는 이 구현에서는 비동기 정리 작업이 가능하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-106">One of the key differences however, is that this implementation allows for asynchronous cleanup operations.</span></span> <span data-ttu-id="3de4a-107"><xref:System.IAsyncDisposable.DisposeAsync>는 비동기 삭제 작업을 나타내는 <xref:System.Threading.Tasks.ValueTask>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-107">The <xref:System.IAsyncDisposable.DisposeAsync> returns a <xref:System.Threading.Tasks.ValueTask> that represents the asynchronous dispose operation.</span></span>

<span data-ttu-id="3de4a-108">일반적으로 <xref:System.IAsyncDisposable> 인터페이스를 구현할 때 해당 클래스에서는 <xref:System.IDisposable> 인터페이스도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-108">It is typical when implementing the <xref:System.IAsyncDisposable> interface that classes will also implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="3de4a-109"><xref:System.IAsyncDisposable> 인터페이스의 좋은 구현 패턴은 동기 삭제나 비동기 삭제용으로 준비하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-109">A good implementation pattern of the <xref:System.IAsyncDisposable> interface is to be prepared for either synchronous or asynchronous dispose.</span></span> <span data-ttu-id="3de4a-110">Dispose 패턴을 구현하기 위한 모든 지침은 비동기 구현에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-110">All of the guidance for implementing the dispose pattern also applies to the asynchronous implementation.</span></span> <span data-ttu-id="3de4a-111">이 문서에서는 [Dispose 메서드를 구현](implementing-dispose.md)하는 방법을 이미 잘 알고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-111">This article assumes that you're already familiar with how to [implement a Dispose method](implementing-dispose.md).</span></span>

## <a name="disposeasync-and-disposeasynccore"></a><span data-ttu-id="3de4a-112">DisposeAsync() 및 DisposeAsyncCore()</span><span class="sxs-lookup"><span data-stu-id="3de4a-112">DisposeAsync() and DisposeAsyncCore()</span></span>

<span data-ttu-id="3de4a-113"><xref:System.IAsyncDisposable> 인터페이스는 매개 변수가 없는 단일 메서드 <xref:System.IAsyncDisposable.DisposeAsync>를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-113">The <xref:System.IAsyncDisposable> interface declares a single parameterless method, <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="3de4a-114">봉인되지 않은 클래스에는 마찬가지로 <xref:System.Threading.Tasks.ValueTask>를 반환하는 추가 `DisposeAsyncCore()` 메서드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-114">Any non-sealed class should have an additional `DisposeAsyncCore()` method that also returns a <xref:System.Threading.Tasks.ValueTask>.</span></span>

- <span data-ttu-id="3de4a-115">매개 변수가 없는 `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 구현</span><span class="sxs-lookup"><span data-stu-id="3de4a-115">A `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementation that has no parameters.</span></span>
- <span data-ttu-id="3de4a-116">시그니처가 다음과 같은 `protected virtual ValueTask DisposeAsyncCore()` 메서드</span><span class="sxs-lookup"><span data-stu-id="3de4a-116">A `protected virtual ValueTask DisposeAsyncCore()` method whose signature is:</span></span>

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a><span data-ttu-id="3de4a-117">DisposeAsync() 메서드</span><span class="sxs-lookup"><span data-stu-id="3de4a-117">The DisposeAsync() method</span></span>

<span data-ttu-id="3de4a-118">`public` 매개 변수가 없는 `DisposeAsync()` 메서드는 `await using` 문에서 암시적으로 호출되며 관리되지 않는 리소스를 해제하고, 일반 정리를 수행하고, 종료자(있는 경우)를 실행할 필요가 없음을 나타내기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-118">The `public` parameterless `DisposeAsync()` method is called implicitly in an `await using` statement, and its purpose is to free unmanaged resources, perform general cleanup, and to indicate that the finalizer, if one is present, need not run.</span></span> <span data-ttu-id="3de4a-119">관리형 개체와 관련된 메모리를 해제하는 것은 항상 [가비지 수집기](index.md)의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-119">Freeing the memory associated with a managed object is always the domain of the [garbage collector](index.md).</span></span> <span data-ttu-id="3de4a-120">이로 인해 다음과 같은 표준 구현이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-120">Because of this, it has a standard implementation:</span></span>

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of unmanaged resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> <span data-ttu-id="3de4a-121">삭제 패턴과 비교해 비동기 삭제 패턴의 한 가지 주된 차이점은 `Dispose(bool)` 오버로드 메서드에 대한 <xref:System.IAsyncDisposable.DisposeAsync>의 호출에서 인수로 `false`가 지정된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-121">One primary difference in the async dispose pattern compared to the dispose pattern, is that the call from <xref:System.IAsyncDisposable.DisposeAsync> to the `Dispose(bool)` overload method is given `false` as an argument.</span></span> <span data-ttu-id="3de4a-122">그러나 <xref:System.IDisposable.Dispose?displayProperty=nameWithType> 메서드를 구현할 때는 대신 `true`가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-122">When implementing the <xref:System.IDisposable.Dispose?displayProperty=nameWithType> method, however, `true` is passed instead.</span></span> <span data-ttu-id="3de4a-123">이렇게 하면 동기 삭제 패턴과 기능적 동등성을 보장하고, 또한 종료자 코드 경로가 계속 호출되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-123">This helps ensure functional equivalence with the synchronous dispose pattern, and further ensures that finalizer code paths still get invoked.</span></span> <span data-ttu-id="3de4a-124">즉, `DisposeAsyncCore()` 메서드에서 관리형 리소스를 비동기적으로 삭제하므로 동기적으로도 삭제할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-124">In other words, the `DisposeAsyncCore()` method will dispose of managed resources asynchronously, so you don't want to dispose of them synchronously as well.</span></span> <span data-ttu-id="3de4a-125">따라서 `Dispose(true)` 대신 `Dispose(false)`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-125">Therefore, call `Dispose(false)` instead of `Dispose(true)`.</span></span>

### <a name="the-disposeasynccore-method"></a><span data-ttu-id="3de4a-126">DisposeAsyncCore() 메서드</span><span class="sxs-lookup"><span data-stu-id="3de4a-126">The DisposeAsyncCore() method</span></span>

<span data-ttu-id="3de4a-127">`DisposeAsyncCore()` 메서드는 관리되는 리소스의 비동기 정리를 수행하거나 `DisposeAsync()`에 대한 계단식 호출에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-127">The `DisposeAsyncCore()` method is intended to perform the asynchronous cleanup of managed resources or for cascading calls to `DisposeAsync()`.</span></span> <span data-ttu-id="3de4a-128">서브클래스가 <xref:System.IAsyncDisposable> 구현인 기본 클래스를 상속하는 경우 일반적인 비동기 정리 작업을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-128">It encapsulates the common asynchronous cleanup operations when a subclass inherits a base class that is an implementation of <xref:System.IAsyncDisposable>.</span></span> <span data-ttu-id="3de4a-129">`DisposeAsyncCore()` 메서드는 `virtual`이므로 파생 클래스에서 재정의에 추가 정리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-129">The `DisposeAsyncCore()` method is `virtual` so that derived classes can define additional cleanup in their overrides.</span></span>

> [!TIP]
> <span data-ttu-id="3de4a-130"><xref:System.IAsyncDisposable> 구현이 `sealed`인 경우에는 `DisposeAsyncCore()` 메서드가 필요하지 않으며 <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 메서드에서 직접 비동기 정리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-130">If an implementation of <xref:System.IAsyncDisposable> is `sealed`, the `DisposeAsyncCore()` method is not needed, and the asynchronous cleanup can be performed directly in the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method.</span></span>

## <a name="implement-the-async-dispose-pattern"></a><span data-ttu-id="3de4a-131">비동기 삭제 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="3de4a-131">Implement the async dispose pattern</span></span>

<span data-ttu-id="3de4a-132">모든 봉인되지 않은 클래스는 상속될 수 있기 때문에 잠재적 기본 클래스로 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-132">All non-sealed classes should be considered a potential base class, because they could be inherited.</span></span> <span data-ttu-id="3de4a-133">잠재적 기본 클래스에 대한 비동기 삭제 패턴을 구현하는 경우 `protected virtual ValueTask DisposeAsyncCore()` 메서드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-133">If you implement the async dispose pattern for any potential base class, you must provide the `protected virtual ValueTask DisposeAsyncCore()` method.</span></span> <span data-ttu-id="3de4a-134">다음은 <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>를 사용하는 비동기 삭제 패턴의 구현 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-134">Here is an example implementation of the async dispose pattern that uses a <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

<span data-ttu-id="3de4a-135">앞의 예제에서는 <xref:System.Text.Json.Utf8JsonWriter>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-135">The preceding example uses the <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="3de4a-136">`System.Text.Json`에 대한 자세한 내용은 [Newtonsoft.Json에서 System.Text.Json으로 마이그레이션하는 방법](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3de4a-136">For more information about `System.Text.Json`, see [How to migrate from Newtonsoft.Json to System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

## <a name="implement-both-dispose-and-async-dispose-patterns"></a><span data-ttu-id="3de4a-137">삭제 패턴과 비동기 삭제 패턴 둘 다 구현</span><span class="sxs-lookup"><span data-stu-id="3de4a-137">Implement both dispose and async dispose patterns</span></span>

<span data-ttu-id="3de4a-138">특히 클래스 범위에 이러한 구현의 인스턴스가 포함된 경우 <xref:System.IDisposable> 인터페이스와 <xref:System.IAsyncDisposable> 인터페이스를 둘 다 구현해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-138">You may need to implement both the <xref:System.IDisposable> and <xref:System.IAsyncDisposable> interfaces, especially when your class scope contains instances of these implementations.</span></span> <span data-ttu-id="3de4a-139">이렇게 하면 정리 호출을 적절히 계단식 배열할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-139">Doing so ensures that you can properly cascade clean up calls.</span></span> <span data-ttu-id="3de4a-140">다음은 두 인터페이스를 모두 구현하는 예제 클래스이며 정리에 대한 적절한 지침을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-140">Here is an example class that implements both interfaces and demonstrates the proper guidance for cleanup.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/dispose-and-disposeasync.cs":::

<span data-ttu-id="3de4a-141"><xref:System.IDisposable.Dispose?displayProperty=nameWithType> 구현과 <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 구현은 둘 다 간단한 상용구 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-141">The <xref:System.IDisposable.Dispose?displayProperty=nameWithType> and <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementations are both simple boilerplate code.</span></span>

<span data-ttu-id="3de4a-142">`Dispose(bool)` 오버로드 메서드에서 <xref:System.IDisposable> 인스턴스는 `null`이 아닌 경우 조건적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-142">In the `Dispose(bool)` overload method, the <xref:System.IDisposable> instance is conditionally disposed of if it is not `null`.</span></span> <span data-ttu-id="3de4a-143"><xref:System.IAsyncDisposable> 인스턴스는 <xref:System.IDisposable>로 캐스팅되며 `null`이 아닌 경우 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-143">The <xref:System.IAsyncDisposable> instance is cast as <xref:System.IDisposable>, and if it is also not `null`, it is disposed of as well.</span></span> <span data-ttu-id="3de4a-144">그런 다음, 두 인스턴스가 모두 `null`에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-144">Both instances are then assigned to `null`.</span></span>

<span data-ttu-id="3de4a-145">`DisposeAsyncCore()` 메서드를 사용하여 동일한 논리 접근 방식을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-145">With the `DisposeAsyncCore()` method, the same logical approach is followed.</span></span> <span data-ttu-id="3de4a-146"><xref:System.IAsyncDisposable> 인스턴스가 `null`이 아닌 경우에는 `DisposeAsync().ConfigureAwait(false)` 호출이 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-146">If the <xref:System.IAsyncDisposable> instance is not `null`, its call to `DisposeAsync().ConfigureAwait(false)` is awaited.</span></span> <span data-ttu-id="3de4a-147"><xref:System.IDisposable> 인스턴스가 <xref:System.IAsyncDisposable>의 구현이기도 한 경우에도 비동기적으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-147">If the <xref:System.IDisposable> instance is also an implementation of <xref:System.IAsyncDisposable>, it's also disposed of asynchronously.</span></span> <span data-ttu-id="3de4a-148">그런 다음, 두 인스턴스가 모두 `null`에 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-148">Both instances are then assigned to `null`.</span></span>

## <a name="using-async-disposable"></a><span data-ttu-id="3de4a-149">비동기 삭제 가능 사용</span><span class="sxs-lookup"><span data-stu-id="3de4a-149">Using async disposable</span></span>

<span data-ttu-id="3de4a-150"><xref:System.IAsyncDisposable> 인터페이스를 구현하는 개체를 제대로 사용하려면 [await](../../csharp/language-reference/operators/await.md) 및 [using](../../csharp/language-reference/keywords/using-statement.md) 키워드를 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-150">To properly consume an object that implements the <xref:System.IAsyncDisposable> interface, you use the [await](../../csharp/language-reference/operators/await.md) and [using](../../csharp/language-reference/keywords/using-statement.md) keywords together.</span></span> <span data-ttu-id="3de4a-151">`ExampleAsyncDisposable` 클래스를 인스턴스화한 후에 `await using` 문에 래핑하는 다음 예제를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="3de4a-151">Consider the following example, where the `ExampleAsyncDisposable` class is instantiated and then wrapped in an `await using` statement.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <span data-ttu-id="3de4a-152"><xref:System.IAsyncDisposable> 인터페이스의 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> 확장 메서드를 사용하면 작업 연속이 원래 컨텍스트 또는 스케줄러에서 마샬링되는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-152">Use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> extension method of the <xref:System.IAsyncDisposable> interface to configure how the continuation of the task is marshalled on its original context or scheduler.</span></span> <span data-ttu-id="3de4a-153">`ConfigureAwait`에 대한 자세한 내용은 [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3de4a-153">For more information on `ConfigureAwait`, see [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span></span>

<span data-ttu-id="3de4a-154">`ConfigureAwait`를 사용하지 않아도 되는 상황에서는 `await using` 문을 다음과 같이 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-154">For situations where the usage of `ConfigureAwait` is not needed, the `await using` statement could be simplified as follows:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

<span data-ttu-id="3de4a-155">또한 [using 선언](../../csharp/whats-new/csharp-8.md#using-declarations)의 암시적 범위를 사용하도록 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-155">Furthermore, it could be written to use the implicit scoping of a [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a><span data-ttu-id="3de4a-156">스택형 using</span><span class="sxs-lookup"><span data-stu-id="3de4a-156">Stacked usings</span></span>

<span data-ttu-id="3de4a-157"><xref:System.IAsyncDisposable>을 구현하는 여러 개체를 만들고 사용하는 상황에서는 잘못된 조건에서 `using` 문을 스택하면 <xref:System.IAsyncDisposable.DisposeAsync> 호출을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-157">In situations where you create and use multiple objects that implement <xref:System.IAsyncDisposable>, it's possible that stacking `using` statements in errant conditions could prevent calls to <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="3de4a-158">잠재적 문제를 방지하기 위해 스택하는 대신 다음 예제 패턴을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3de4a-158">In order to help prevent potential concern, you should avoid stacking, and instead follow this example pattern:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a><span data-ttu-id="3de4a-159">참조</span><span class="sxs-lookup"><span data-stu-id="3de4a-159">See also</span></span>

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
