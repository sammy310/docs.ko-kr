---
title: DisposeAsync 메서드 구현
description: ''
author: IEvangelist
ms.author: dapine
ms.date: 06/02/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
helpviewer_keywords:
- DisposeAsync method
- garbage collection, DisposeAsync method
ms.openlocfilehash: 91ace1932e8bb751e8e1d85e00b3e239a01aa9ea
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309822"
---
# <a name="implement-a-disposeasync-method"></a>DisposeAsync 메서드 구현

<xref:System.IAsyncDisposable?displayProperty=nameWithType> 인터페이스는 C# 8.0의 일부로 도입되었습니다. <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 메서드는 [Dispose 메서드를 구현](implementing-dispose.md)할 때와 마찬가지로 리소스 정리를 수행하는 경우에 구현합니다. 그러나 중요한 차이점 하나는 이 구현에서는 비동기 정리 작업이 가능하다는 것입니다. <xref:System.IAsyncDisposable.DisposeAsync>는 비동기 삭제 작업을 나타내는 <xref:System.Threading.Tasks.ValueTask>를 반환합니다.

일반적으로 <xref:System.IAsyncDisposable> 인터페이스를 구현할 때 클래스에서는 <xref:System.IDisposable> 인터페이스도 구현합니다. <xref:System.IAsyncDisposable> 인터페이스의 좋은 구현 패턴은 동기 삭제나 비동기 삭제용으로 준비하는 것입니다. 삭제 패턴을 구현하기 위한 모든 지침은 비동기 구현에 적용됩니다. 이 문서에서는 [Dispose 메서드를 구현](implementing-dispose.md)하는 방법을 이미 잘 알고 있다고 가정합니다.

## <a name="disposeasync-and-disposeasynccore"></a>DisposeAsync() 및 DisposeAsyncCore()

<xref:System.IAsyncDisposable> 인터페이스는 매개 변수가 없는 단일 메서드 <xref:System.IAsyncDisposable.DisposeAsync>를 선언합니다. 봉인되지 않은 클래스에는 마찬가지로 <xref:System.Threading.Tasks.ValueTask>를 반환하는 추가 `DisposeAsyncCore()` 메서드가 있어야 합니다.

- 매개 변수가 없는 `public` <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType> 구현
- 시그니처가 다음과 같은 `protected virtual ValueTask DisposeAsyncCore()` 메서드

```csharp
protected virtual ValueTask DisposeAsyncCore()
{
}
```

`DisposeAsyncCore()` 메서드는 `virtual`이므로 파생 클래스에서 재정의에 추가 정리를 정의할 수 있습니다.

### <a name="the-disposeasync-method"></a>DisposeAsync() 메서드

`public` 매개 변수 없는 `DisposeAsync()` 메서드는 `await using` 문에서 암시적으로 호출되며 비관리형 리소스를 해제하고, 일반 정리를 수행하고, 종료자(있는 경우)를 실행할 필요가 없음을 나타내기 위한 것입니다. 관리형 개체와 관련된 메모리를 해제하는 것은 항상 [가비지 수집기](index.md)의 영역입니다. 이로 인해 다음과 같은 표준 구현이 수행됩니다.

```csharp
public async ValueTask DisposeAsync()
{
    // Perform async cleanup.
    await DisposeAsyncCore();

    // Dispose of managed resources.
    Dispose(false);
    // Suppress finalization.
    GC.SuppressFinalize(this);
}
```

> [!NOTE]
> 삭제 패턴과 비교해 비동기 삭제 패턴의 한 가지 주된 차이점은 `Dispose(bool)` 오버로드 메서드에 대한 <xref:System.IAsyncDisposable.DisposeAsync>의 호출에서 인수로 `false`가 지정된다는 것입니다. 그러나 <xref:System.IDisposable.Dispose?displayProperty=nameWithType> 메서드를 구현할 때는 대신 `true`가 전달됩니다. 이렇게 하면 동기 삭제 패턴과 기능적 동등성을 보장하고, 또한 종료자 코드 경로가 계속 호출되도록 할 수 있습니다. 즉, `DisposeAsyncCore()` 메서드에서 관리형 리소스를 비동기적으로 삭제하므로 동기적으로도 삭제할 필요가 없습니다. 따라서 `Dispose(true)` 대신 `Dispose(false)`를 호출합니다.

## <a name="implement-the-async-dispose-pattern"></a>비동기 삭제 패턴 구현

모든 봉인되지 않은 클래스는 상속될 수 있기 때문에 잠재적 기본 클래스로 간주해야 합니다. 잠재적 기본 클래스에 대한 비동기 삭제 패턴을 구현하는 경우 `protected virtual ValueTask DisposeAsyncCore()` 메서드를 제공해야 합니다. 다음은 <xref:System.Text.Json.Utf8JsonWriter?displayProperty=nameWithType>를 사용하는 비동기 삭제 패턴의 구현 예제입니다.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/disposeasync.cs":::

앞의 예제에서는 <xref:System.Text.Json.Utf8JsonWriter>를 사용합니다. `System.Text.Json`에 대한 자세한 내용은 [Newtonsoft.Json에서 System.Text.Json으로 마이그레이션하는 방법](../serialization/system-text-json-migrate-from-newtonsoft-how-to.md)을 참조하세요.

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

<xref:System.IAsyncDisposable>을 구현하는 여러 개체를 만들고 사용하는 상황에서는 잘못된 조건에서 `using` 문을 스택하면 <xref:System.IAsyncDisposable.DisposeAsync> 호출을 방지할 수 있습니다. 잠재적 문제를 방지하기 위해 스택하는 대신 다음 예제 패턴을 따라야 합니다.

:::code language="csharp" source="../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.asyncdisposable/stacked-await-usings.cs":::

## <a name="see-also"></a>참조

- <xref:System.IAsyncDisposable>
- <xref:System.IAsyncDisposable.DisposeAsync?displayProperty=nameWithType>
- <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait(System.IAsyncDisposable,System.Boolean)>
