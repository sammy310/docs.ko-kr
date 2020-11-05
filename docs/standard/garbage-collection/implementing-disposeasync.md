---
title: DisposeAsync 메서드 구현
description: DisposeAsync 및 DisposeAsyncCore 메서드를 구현하여 비동기 리소스 정리를 수행하는 방법을 알아봅니다.
author: IEvangelist
ms.author: dapine
ms.date: 10/26/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 5aa82c507c22a4795f39267ac8f435599fb9cd92
ms.sourcegitcommit: 279fb6e8d515df51676528a7424a1df2f0917116
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2020
ms.locfileid: "92687721"
---
# <a name="implement-a-disposeasync-method"></a>DisposeAsync 메서드 구현

<xref:System.IAsyncDisposable?displayProperty=nameWithType> 인터페이스는 C# 8.0의 일부로 도입되었습니다. <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 메서드는 [Dispose 메서드를 구현](implementing-dispose.md)할 때와 마찬가지로 리소스 정리를 수행하는 경우에 구현합니다. 그러나 중요한 차이점 하나는 이 구현에서는 비동기 정리 작업이 가능하다는 것입니다. <xref:System.IAsyncDisposable.DisposeAsync>는 비동기 삭제 작업을 나타내는 <xref:System.Threading.Tasks.ValueTask>를 반환합니다.

일반적으로 <xref:System.IAsyncDisposable> 인터페이스를 구현할 때 해당 클래스에서는 <xref:System.IDisposable> 인터페이스도 구현합니다. <xref:System.IAsyncDisposable> 인터페이스의 좋은 구현 패턴은 동기 삭제나 비동기 삭제용으로 준비하는 것입니다. Dispose 패턴을 구현하기 위한 모든 지침은 비동기 구현에도 적용됩니다. 이 문서에서는 [Dispose 메서드를 구현](implementing-dispose.md)하는 방법을 이미 잘 알고 있다고 가정합니다.

## <a name="disposeasync-and-disposeasynccore"></a>DisposeAsync() 및 DisposeAsyncCore()

<xref:System.IAsyncDisposable> 인터페이스는 매개 변수가 없는 단일 메서드 <xref:System.IAsyncDisposable.DisposeAsync>를 선언합니다. 봉인되지 않은 클래스에는 마찬가지로 <xref:System.Threading.Tasks.ValueTask>를 반환하는 추가 `DisposeAsyncCore()` 메서드가 있어야 합니다.

- 매개 변수가 없는 `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 구현
- 시그니처가 다음과 같은 `protected virtual ValueTask DisposeAsyncCore()` 메서드

  ```csharp
  protected virtual ValueTask DisposeAsyncCore()
  {
  }
  ```

### <a name="the-disposeasync-method"></a>DisposeAsync() 메서드

`public` 매개 변수가 없는 `DisposeAsync()` 메서드는 `await using` 문에서 암시적으로 호출되며 관리되지 않는 리소스를 해제하고, 일반 정리를 수행하고, 종료자(있는 경우)를 실행할 필요가 없음을 나타내기 위한 것입니다. 관리형 개체와 관련된 메모리를 해제하는 것은 항상 [가비지 수집기](index.md)의 영역입니다. 이로 인해 다음과 같은 표준 구현이 수행됩니다.

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
> 삭제 패턴과 비교해 비동기 삭제 패턴의 한 가지 주된 차이점은 `Dispose(bool)` 오버로드 메서드에 대한 <xref:System.IAsyncDisposable.DisposeAsync>의 호출에서 인수로 `false`가 지정된다는 것입니다. 그러나 <xref:System.IDisposable.Dispose?displayProperty=nameWithType> 메서드를 구현할 때는 대신 `true`가 전달됩니다. 이렇게 하면 동기 삭제 패턴과 기능적 동등성을 보장하고, 또한 종료자 코드 경로가 계속 호출되도록 할 수 있습니다. 즉, `DisposeAsyncCore()` 메서드에서 관리형 리소스를 비동기적으로 삭제하므로 동기적으로도 삭제할 필요가 없습니다. 따라서 `Dispose(true)` 대신 `Dispose(false)`를 호출합니다.

### <a name="the-disposeasynccore-method"></a>DisposeAsyncCore() 메서드

`DisposeAsyncCore()` 메서드는 관리되는 리소스의 비동기 정리를 수행하거나 `DisposeAsync()`에 대한 계단식 호출에 사용됩니다. 서브클래스가 <xref:System.IAsyncDisposable> 구현인 기본 클래스를 상속하는 경우 일반적인 비동기 정리 작업을 캡슐화합니다. `DisposeAsyncCore()` 메서드는 `virtual`이므로 파생 클래스에서 재정의에 추가 정리를 정의할 수 있습니다.

> [!TIP]
> <xref:System.IAsyncDisposable> 구현이 `sealed`인 경우에는 `DisposeAsyncCore()` 메서드가 필요하지 않으며 <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 메서드에서 직접 비동기 정리를 수행할 수 있습니다.

## <a name="implement-the-async-dispose-pattern"></a>비동기 삭제 패턴 구현

모든 봉인되지 않은 클래스는 상속될 수 있기 때문에 잠재적 기본 클래스로 간주해야 합니다. 잠재적 기본 클래스에 대한 비동기 삭제 패턴을 구현하는 경우 `protected virtual ValueTask DisposeAsyncCore()` 메서드를 제공해야 합니다. 다음은 <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>를 사용하는 비동기 삭제 패턴의 구현 예제입니다.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

앞의 예제에서는 <xref:System.Text.Json.Utf8JsonWriter>를 사용합니다. `System.Text.Json`에 대한 자세한 내용은 [Newtonsoft.Json에서 System.Text.Json으로 마이그레이션하는 방법](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md)을 참조하세요.

## <a name="implement-both-dispose-and-async-dispose-patterns"></a>삭제 패턴과 비동기 삭제 패턴 둘 다 구현

특히 클래스 범위에 이러한 구현의 인스턴스가 포함된 경우 <xref:System.IDisposable> 인터페이스와 <xref:System.IAsyncDisposable> 인터페이스를 둘 다 구현해야 할 수도 있습니다. 이렇게 하면 정리 호출을 적절히 계단식 배열할 수 있습니다. 다음은 두 인터페이스를 모두 구현하는 예제 클래스이며 정리에 대한 적절한 지침을 보여 줍니다.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/dispose-and-disposeasync.cs":::

<xref:System.IDisposable.Dispose?displayProperty=nameWithType> 구현과 <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 구현은 둘 다 간단한 상용구 코드입니다.

`Dispose(bool)` 오버로드 메서드에서 <xref:System.IDisposable> 인스턴스는 `null`이 아닌 경우 조건적으로 삭제됩니다. <xref:System.IAsyncDisposable> 인스턴스는 <xref:System.IDisposable>로 캐스팅되며 `null`이 아닌 경우 삭제됩니다. 그런 다음, 두 인스턴스가 모두 `null`에 할당됩니다.

`DisposeAsyncCore()` 메서드를 사용하여 동일한 논리 접근 방식을 따릅니다. <xref:System.IAsyncDisposable> 인스턴스가 `null`이 아닌 경우에는 `DisposeAsync().ConfigureAwait(false)` 호출이 대기됩니다. <xref:System.IDisposable> 인스턴스가 <xref:System.IAsyncDisposable>의 구현이기도 한 경우에도 비동기적으로 삭제됩니다. 그런 다음, 두 인스턴스가 모두 `null`에 할당됩니다.

## <a name="using-async-disposable"></a>비동기 삭제 가능 사용

<xref:System.IAsyncDisposable> 인터페이스를 구현하는 개체를 제대로 사용하려면 [await](../../csharp/language-reference/operators/await.md) 및 [using](../../csharp/language-reference/keywords/using-statement.md) 키워드를 함께 사용합니다. `ExampleAsyncDisposable` 클래스를 인스턴스화한 후에 `await using` 문에 래핑하는 다음 예제를 살펴보세요.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/proper-await-using.cs":::

> [!IMPORTANT]
> <xref:System.IAsyncDisposable> 인터페이스의 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)> 확장 메서드를 사용하면 작업 연속이 원래 컨텍스트 또는 스케줄러에서 마샬링되는 방법을 구성할 수 있습니다. `ConfigureAwait`에 대한 자세한 내용은 [ConfigureAwait FAQ](https://devblogs.microsoft.com/dotnet/configureawait-faq/)를 참조하세요.

`ConfigureAwait`를 사용하지 않아도 되는 상황에서는 `await using` 문을 다음과 같이 간소화할 수 있습니다.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-non-configureawait.cs":::

또한 [using 선언](../../csharp/whats-new/csharp-8.md#using-declarations)의 암시적 범위를 사용하도록 작성할 수 있습니다.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/await-using-declaration.cs":::

## <a name="stacked-usings"></a>스택형 using

<xref:System.IAsyncDisposable>을 구현하는 여러 개체를 만들고 사용하는 상황에서는 <xref:System.Threading.Tasks.ValueTask.ConfigureAwait%2A>를 사용하여 `await using` 문을 스택하면 잘못된 조건에서 <xref:System.IAsyncDisposable.DisposeAsync> 호출을 방지할 수 있습니다. <xref:System.IAsyncDisposable.DisposeAsync>가 항상 호출되게 하려면 스택을 방지해야 합니다. 다음 세 가지 코드 예제는 대신 사용할 수 있는 패턴을 보여 줍니다.

### <a name="acceptable-pattern-one"></a>허용 가능한 패턴 1

:::code language="csharp" id="one" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

앞의 예제에서 각 비동기 정리 작업은 `await using` 블록에서 명시적으로 범위가 지정됩니다. 외부 범위는 `objOne`이 `objTwo`를 둘러싸는 중괄호를 설정하는 방법으로 정의되므로 `objTwo`가 먼저 삭제된 후 `objOne`이 삭제됩니다. `IAsyncDisposable` 인스턴스는 둘 다 <xref:System.IAsyncDisposable.DisposeAsync> 메서드를 대기시키므로 비동기 정리 작업을 수행합니다. 호출은 스택되지 않고 중첩됩니다.

### <a name="acceptable-pattern-two"></a>허용 가능한 패턴 2

:::code language="csharp" id="two" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

앞의 예제에서 각 비동기 정리 작업은 `await using` 블록에서 명시적으로 범위가 지정됩니다. 각 블록의 끝에서 해당 `IAsyncDisposable` 인스턴스는 <xref:System.IAsyncDisposable.DisposeAsync> 메서드를 대기시키므로 비동기 정리 작업을 수행합니다. 호출은 스택되지 않고 순차적입니다. 이 시나리오에서는 `objOne`이 먼저 삭제된 후 `objTwo`가 삭제됩니다.

### <a name="acceptable-pattern-three"></a>허용 가능한 패턴 3

:::code language="csharp" id="three" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

앞의 예제에서 각 비동기 정리 작업은 포함하는 메서드 본문에서 암시적으로 범위가 지정됩니다. 바깥쪽 블록의 끝에서 `IAsyncDisposable` 인스턴스는 비동기 정리 작업을 수행합니다. 이는 선언된 순서의 역순으로 실행됩니다. 즉, `objOne` 전에 `objTwo`가 삭제됩니다.

### <a name="unacceptable-pattern"></a>허용되지 않는 패턴

`AnotherAsyncDisposable` 생성자에서 예외가 throw되면 `objOne`이 제대로 삭제되지 않습니다.

:::code language="csharp" id="dontdothis" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

> [!TIP]
> 예기치 않은 동작이 발생할 수 있으므로 이 패턴을 사용하지 마세요.

## <a name="see-also"></a>참조

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
