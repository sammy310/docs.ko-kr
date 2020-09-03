---
title: DisposeAsync 메서드 구현
description: DisposeAsync 및 DisposeAsyncCore 메서드를 구현하여 비동기 리소스 정리를 수행하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 08/25/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 268cea7584040ad92e2da75e5e03112480cda93c
ms.sourcegitcommit: 2560a355c76b0a04cba0d34da870df9ad94ceca3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/28/2020
ms.locfileid: "89053180"
---
# <a name="implement-a-disposeasync-method"></a><span data-ttu-id="84817-103">DisposeAsync 메서드 구현</span><span class="sxs-lookup"><span data-stu-id="84817-103">Implement a DisposeAsync method</span></span>

<span data-ttu-id="84817-104"><xref:System.IAsyncDisposable?displayProperty=nameWithType> 인터페이스는 C# 8.0의 일부로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="84817-104">The <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface was introduced as part of C# 8.0.</span></span> <span data-ttu-id="84817-105"><xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 메서드는 [Dispose 메서드를 구현](implementing-dispose.md)할 때와 마찬가지로 리소스 정리를 수행하는 경우에 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-105">You implement the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method when you need to perform resource cleanup, just as you would when [implementing a Dispose method](implementing-dispose.md).</span></span> <span data-ttu-id="84817-106">그러나 중요한 차이점 하나는 이 구현에서는 비동기 정리 작업이 가능하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84817-106">One of the key differences however, is that this implementation allows for asynchronous cleanup operations.</span></span> <span data-ttu-id="84817-107"><xref:System.IAsyncDisposable.DisposeAsync>는 비동기 삭제 작업을 나타내는 <xref:System.Threading.Tasks.ValueTask>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-107">The <xref:System.IAsyncDisposable.DisposeAsync> returns a <xref:System.Threading.Tasks.ValueTask> that represents the asynchronous dispose operation.</span></span>

<span data-ttu-id="84817-108">일반적으로 <xref:System.IAsyncDisposable> 인터페이스를 구현할 때 해당 클래스에서는 <xref:System.IDisposable> 인터페이스도 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-108">It is typical when implementing the <xref:System.IAsyncDisposable> interface that classes will also implement the <xref:System.IDisposable> interface.</span></span> <span data-ttu-id="84817-109"><xref:System.IAsyncDisposable> 인터페이스의 좋은 구현 패턴은 동기 삭제나 비동기 삭제용으로 준비하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84817-109">A good implementation pattern of the <xref:System.IAsyncDisposable> interface is to be prepared for either synchronous, or asynchronous dispose.</span></span> <span data-ttu-id="84817-110">Dispose 패턴을 구현하기 위한 모든 지침은 비동기 구현에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84817-110">All of the guidance for implementing the dispose pattern also applies to the asynchronous implementation.</span></span> <span data-ttu-id="84817-111">이 문서에서는 [Dispose 메서드를 구현](implementing-dispose.md)하는 방법을 이미 잘 알고 있다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-111">This article assumes that you're already familiar with how to [implement a Dispose method](implementing-dispose.md).</span></span>

## <a name="disposeasync-and-disposeasynccore"></a><span data-ttu-id="84817-112">DisposeAsync() 및 DisposeAsyncCore()</span><span class="sxs-lookup"><span data-stu-id="84817-112">DisposeAsync() and DisposeAsyncCore()</span></span>

<span data-ttu-id="84817-113"><xref:System.IAsyncDisposable> 인터페이스는 매개 변수가 없는 단일 메서드 <xref:System.IAsyncDisposable.DisposeAsync>를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-113">The <xref:System.IAsyncDisposable> interface declares a single parameterless method, <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="84817-114">봉인되지 않은 클래스에는 마찬가지로 <xref:System.Threading.Tasks.ValueTask>를 반환하는 추가 `DisposeAsyncCore()` 메서드가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-114">Any non-sealed class should have an additional `DisposeAsyncCore()` method that also returns a <xref:System.Threading.Tasks.ValueTask>.</span></span>

- <span data-ttu-id="84817-115">매개 변수가 없는 `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 구현</span><span class="sxs-lookup"><span data-stu-id="84817-115">A `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> implementation that has no parameters.</span></span>
- <span data-ttu-id="84817-116">시그니처가 다음과 같은 `protected virtual ValueTask DisposeAsyncCore()` 메서드</span><span class="sxs-lookup"><span data-stu-id="84817-116">A `protected virtual ValueTask DisposeAsyncCore()` method whose signature is:</span></span>

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a><span data-ttu-id="84817-117">DisposeAsync() 메서드</span><span class="sxs-lookup"><span data-stu-id="84817-117">The DisposeAsync() method</span></span>

<span data-ttu-id="84817-118">`public` 매개 변수가 없는 `DisposeAsync()` 메서드는 `await using` 문에서 암시적으로 호출되며 관리되지 않는 리소스를 해제하고, 일반 정리를 수행하고, 종료자(있는 경우)를 실행할 필요가 없음을 나타내기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84817-118">The `public` parameterless `DisposeAsync()` method is called implicitly in an `await using` statement, and its purpose is to free unmanaged resources, perform general cleanup, and to indicate that the finalizer, if one is present, need not run.</span></span> <span data-ttu-id="84817-119">관리형 개체와 관련된 메모리를 해제하는 것은 항상 [가비지 수집기](index.md)의 영역입니다.</span><span class="sxs-lookup"><span data-stu-id="84817-119">Freeing the memory associated with a managed object is always the domain of the [garbage collector](index.md).</span></span> <span data-ttu-id="84817-120">이로 인해 다음과 같은 표준 구현이 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="84817-120">Because of this, it has a standard implementation:</span></span>

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
> <span data-ttu-id="84817-121">삭제 패턴과 비교해 비동기 삭제 패턴의 한 가지 주된 차이점은 `Dispose(bool)` 오버로드 메서드에 대한 <xref:System.IAsyncDisposable.DisposeAsync>의 호출에서 인수로 `false`가 지정된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="84817-121">One primary difference in the async dispose pattern compared to the dispose pattern, is that the call from <xref:System.IAsyncDisposable.DisposeAsync> to the `Dispose(bool)` overload method is given `false` as an argument.</span></span> <span data-ttu-id="84817-122">그러나 <xref:System.IDisposable.Dispose?displayProperty=nameWithType> 메서드를 구현할 때는 대신 `true`가 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="84817-122">When implementing the <xref:System.IDisposable.Dispose?displayProperty=nameWithType> method, however; `true` is passed instead.</span></span> <span data-ttu-id="84817-123">이렇게 하면 동기 삭제 패턴과 기능적 동등성을 보장하고, 또한 종료자 코드 경로가 계속 호출되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84817-123">This helps ensure functional equivalence with the synchronous dispose pattern, and further ensures that finalizer code paths still get invoked.</span></span> <span data-ttu-id="84817-124">즉, `DisposeAsyncCore()` 메서드에서 관리형 리소스를 비동기적으로 삭제하므로 동기적으로도 삭제할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="84817-124">In other words, the `DisposeAsyncCore()` method will dispose of managed resources asynchronously, so you don't want to dispose of them synchronously as well.</span></span> <span data-ttu-id="84817-125">따라서 `Dispose(true)` 대신 `Dispose(false)`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-125">Therefore, call `Dispose(false)` instead of `Dispose(true)`.</span></span>

### <a name="the-disposeasynccore-method"></a><span data-ttu-id="84817-126">DisposeAsyncCore() 메서드</span><span class="sxs-lookup"><span data-stu-id="84817-126">The DisposeAsyncCore() method</span></span>

<span data-ttu-id="84817-127">`DisposeAsyncCore()` 메서드는 관리되는 리소스의 비동기 정리를 수행하거나 `DisposeAsync()`에 대한 계단식 호출에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="84817-127">The `DisposeAsyncCore()` method is intended to perform the asynchronous cleanup of managed resources or for cascading calls to `DisposeAsync()`.</span></span> <span data-ttu-id="84817-128">서브클래스가 <xref:System.IAsyncDisposable> 구현인 기본 클래스를 상속하는 경우 일반적인 비동기 정리 작업을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-128">It encapsulates the common asynchronous cleanup operations when a subclass inherits a base class that is an implementation of <xref:System.IAsyncDisposable>.</span></span> <span data-ttu-id="84817-129">`DisposeAsyncCore()` 메서드는 `virtual`이므로 파생 클래스에서 재정의에 추가 정리를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84817-129">The `DisposeAsyncCore()` method is `virtual` so that derived classes can define additional cleanup in their overrides.</span></span>

> [!TIP]
> <span data-ttu-id="84817-130"><xref:System.IAsyncDisposable> 구현이 `sealed`인 경우에는 `DisposeAsyncCore()` 메서드가 필요하지 않으며 <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 메서드에서 직접 비동기 정리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84817-130">If an implementation of <xref:System.IAsyncDisposable> is `sealed`, the `DisposeAsyncCore()` method is not needed, and the asynchronous cleanup can be performed directly in the <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> method.</span></span>

## <a name="implement-the-async-dispose-pattern"></a><span data-ttu-id="84817-131">비동기 삭제 패턴 구현</span><span class="sxs-lookup"><span data-stu-id="84817-131">Implement the async dispose pattern</span></span>

<span data-ttu-id="84817-132">모든 봉인되지 않은 클래스는 상속될 수 있기 때문에 잠재적 기본 클래스로 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-132">All non-sealed classes should be considered a potential base class, because they could be inherited.</span></span> <span data-ttu-id="84817-133">잠재적 기본 클래스에 대한 비동기 삭제 패턴을 구현하는 경우 `protected virtual ValueTask DisposeAsyncCore()` 메서드를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-133">If you implement the async dispose pattern for any potential base class, you must provide the `protected virtual ValueTask DisposeAsyncCore()` method.</span></span> <span data-ttu-id="84817-134">다음은 <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>를 사용하는 비동기 삭제 패턴의 구현 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="84817-134">Here is an example implementation of the async dispose pattern that uses a <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

<span data-ttu-id="84817-135">앞의 예제에서는 <xref:System.Text.Json.Utf8JsonWriter>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-135">The preceding example uses the <xref:System.Text.Json.Utf8JsonWriter>.</span></span> <span data-ttu-id="84817-136">`System.Text.Json`에 대한 자세한 내용은 [Newtonsoft.Json에서 System.Text.Json으로 마이그레이션하는 방법](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84817-136">For more information about `System.Text.Json`, see [How to migrate from Newtonsoft.Json to System.Text.Json](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md).</span></span>

## <a name="using-async-disposable"></a><span data-ttu-id="84817-137">비동기 삭제 가능 사용</span><span class="sxs-lookup"><span data-stu-id="84817-137">Using async disposable</span></span>

<span data-ttu-id="84817-138"><xref:System.IAsyncDisposable> 인터페이스를 구현하는 개체를 제대로 사용하려면 [await](../../csharp/language-reference/operators/await.md) 및 [using](../../csharp/language-reference/keywords/using-statement.md) 키워드를 함께 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-138">To properly consume an object that implements the <xref:System.IAsyncDisposable> interface, you use the [await](../../csharp/language-reference/operators/await.md), and [using](../../csharp/language-reference/keywords/using-statement.md) keywords together.</span></span> <span data-ttu-id="84817-139">`ExampleAsyncDisposable` 클래스를 인스턴스화한 후에 `await using` 문에 래핑하는 다음 예제를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="84817-139">Consider the following example, where the `ExampleAsyncDisposable` class is instantiated and then wrapped in an `await using` statement.</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <span data-ttu-id="84817-140"><xref:System.IAsyncDisposable> 인터페이스의 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> 확장 메서드를 사용하면 작업 연속이 원래 컨텍스트 또는 스케줄러에서 마샬링되는 방법을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84817-140">Use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> extension method of the <xref:System.IAsyncDisposable> interface to configure how the continuation of the task is marshalled on its original context or scheduler.</span></span> <span data-ttu-id="84817-141">`ConfigureAwait`에 대한 자세한 내용은 [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="84817-141">For more information on `ConfigureAwait`, see [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/).</span></span>

<span data-ttu-id="84817-142">`ConfigureAwait`를 사용하지 않아도 되는 상황에서는 `await using` 문을 다음과 같이 간소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84817-142">For situations where the usage of `ConfigureAwait` is not needed, the `await using` statement could be simplified as follows:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

<span data-ttu-id="84817-143">또한 [using 선언](../../csharp/whats-new/csharp-8.md#using-declarations)의 암시적 범위를 사용하도록 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84817-143">Furthermore, it could be written to use the implicit scoping of a [using declaration](../../csharp/whats-new/csharp-8.md#using-declarations).</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a><span data-ttu-id="84817-144">스택형 using</span><span class="sxs-lookup"><span data-stu-id="84817-144">Stacked usings</span></span>

<span data-ttu-id="84817-145"><xref:System.IAsyncDisposable>을 구현하는 여러 개체를 만들고 사용하는 상황에서는 잘못된 조건에서 `using` 문을 스택하면 <xref:System.IAsyncDisposable.DisposeAsync> 호출을 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="84817-145">In situations where you create and use multiple objects that implement <xref:System.IAsyncDisposable>, it's possible that stacking `using` statements in errant conditions could prevent calls to <xref:System.IAsyncDisposable.DisposeAsync>.</span></span> <span data-ttu-id="84817-146">잠재적 문제를 방지하기 위해 스택하는 대신 다음 예제 패턴을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="84817-146">In order to help prevent potential concern, you should avoid stacking, and instead follow this example pattern:</span></span>

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a><span data-ttu-id="84817-147">참조</span><span class="sxs-lookup"><span data-stu-id="84817-147">See also</span></span>

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
