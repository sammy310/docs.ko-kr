---
title: Dispose 메서드 구현
description: 이 문서에서는 .NET에서 코드에 사용되는 비관리형 리소스를 해제하는 Dispose 메서드를 구현하는 방법을 알아봅니다.
ms.date: 05/27/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- Dispose method
- garbage collection, Dispose method
ms.assetid: eb4e1af0-3b48-4fbc-ad4e-fc2f64138bf9
ms.openlocfilehash: c8b4b9a79577776bc049ef77e222d63374178708
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2020
ms.locfileid: "84447175"
---
# <a name="implement-a-dispose-method"></a>Dispose 메서드 구현

<xref:System.IDisposable.Dispose%2A> 메서드 구현은 주로 코드에서 사용하는 관리되지 않는 리소스를 해제하는 데 사용됩니다. <xref:System.IDisposable> 구현인 인스턴스 멤버를 사용하는 경우에는 <xref:System.IDisposable.Dispose%2A> 호출을 계단식 배열하는 것이 일반적입니다. <xref:System.IDisposable.Dispose%2A> 구현에는 이전에 수행한 작업을 실행 취소하는 것과 같은 추가적인 이유가 있습니다. 예를 들어 할당된 메모리를 해제하고, 추가된 컬렉션에서 항목을 제거하고, 획득한 잠금의 해제 신호를 보내는 등의 작업이 있습니다.

[.NET 가비지 수집기](index.md)는 관리되지 않는 메모리를 할당하거나 해제하지 않습니다. Dispose 패턴이라고도 하는 개체 삭제 패턴에서는 개체의 수명에 순서를 적용합니다. Dispose 패턴은 <xref:System.IDisposable> 인터페이스를 구현하는 개체에 사용되며, 파일 및 파이프 핸들, 레지스트리 핸들, 대기 핸들 또는 관리되지 않는 메모리 블록에 대한 포인터와 상호 작용하는 경우 일반적으로 사용됩니다. 이는 가비지 수집기가 관리되지 않는 개체를 회수할 수 없기 때문입니다.

리소스가 항상 적절하게 정리되게 하려면 <xref:System.IDisposable.Dispose%2A> 메서드가 멱등원(idempotent)이어야 합니다(예외를 throw하지 않고 여러 번 호출할 수 있음). 또한 <xref:System.IDisposable.Dispose%2A>의 후속 호출은 아무 작업도 수행하지 않아야 합니다.

<xref:System.GC.KeepAlive%2A?displayProperty=nameWithType> 메서드에 대해 제공된 코드 예에서는 개체 또는 개체의 멤버에 대한 관리되지 않는 참조가 여전히 사용 중인 동안 가비지 수집으로 인해 종료자가 실행되게 할 수 있는 방법을 보여 줍니다. <xref:System.GC.KeepAlive%2A?displayProperty=nameWithType>를 활용하여 현재 루틴의 시작부터 이 메서드가 호출되는 시점까지 개체를 가비지 수집에 부적절하도록 만드는 것이 좋을 수도 있습니다.

## <a name="safe-handles"></a>SafeHandle

개체 종료자에 대한 코드를 작성하는 작업은 올바르게 수행되지 않을 경우 문제를 일으킬 수 있는 복잡한 작업입니다. 따라서 종료자를 구현하는 대신 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType> 개체를 생성하는 것이 좋습니다.

<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>은 관리되지 않는 리소스를 식별하는 <xref:System.IntPtr?displayProperty=nameWithType>을 래핑하는 관리되는 추상 형식입니다. Windows에서는 핸들을 식별하며, Unix에서는 파일 설명자를 식별합니다. 이 리소스는 `SafeHandle`이 삭제되거나 `SafeHandle`에 대한 모든 참조가 삭제되고 `SafeHandle` 인스턴스가 종료될 때 한 번만 해제되도록 하는 데 필요한 모든 논리를 제공합니다.

<xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>은 추상 기본 클래스입니다. 파생 클래스는 다양한 종류의 핸들에 대해 특정 인스턴스를 제공합니다. 이러한 파생 클래스는 잘못된 것으로 간주되는 <xref:System.IntPtr?displayProperty=nameWithType> 값과 실제로 핸들을 해제하는 방법의 유효성을 검사합니다. 예를 들어 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>은 `SafeHandle`에서 파생되어 열려 있는 파일 핸들/설명자를 식별하는 `IntPtrs`을 래핑하고 <xref:System.Runtime.InteropServices.SafeHandle.ReleaseHandle?displayProperty=nameWithType> 메서드를 재정의하여 닫습니다(Unix의 `close` 함수 또는 Windows의 `CloseHandle` 함수를 통해). 관리되지 않는 리소스를 만드는 대부분의 .NET 라이브러리 API는 원시 포인터를 다시 전달하는 대신 `SafeHandle`에서 이를 래핑하고 필요에 따라 해당 `SafeHandle`을 사용자에게 반환합니다. 관리되지 않는 구성 요소와 상호 작용하고 관리되지 않는 리소스에 대한 `IntPtr`을 가져오는 경우 고유한 `SafeHandle` 형식을 만들어 래핑할 수 있습니다. 따라서 비 `SafeHandle` 형식이 종료자를 구현해야 하는 경우는 거의 없습니다. 대부분의 삭제 가능한 패턴 구현에서는 다른 관리되는 리소스(이 중 일부는 `SafeHandle`이 될 수 있음)를 래핑하는 것으로 끝납니다.

<xref:Microsoft.Win32.SafeHandles> 네임스페이스에서 다음과 같은 파생된 클래스가 SafeHandle을 제공합니다.

- 파일, 메모리 매핑된 파일 및 파이프에 대한 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle>, <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedFileHandle> 및 <xref:Microsoft.Win32.SafeHandles.SafePipeHandle> 클래스
- 메모리 뷰에 대한 <xref:Microsoft.Win32.SafeHandles.SafeMemoryMappedViewHandle> 클래스
- 암호화 구문에 대한 <xref:Microsoft.Win32.SafeHandles.SafeNCryptKeyHandle>, <xref:Microsoft.Win32.SafeHandles.SafeNCryptProviderHandle> 및 <xref:Microsoft.Win32.SafeHandles.SafeNCryptSecretHandle> 클래스
- 레지스트리 키에 대한 <xref:Microsoft.Win32.SafeHandles.SafeRegistryHandle> 클래스
- 대기 핸들에 대한 <xref:Microsoft.Win32.SafeHandles.SafeWaitHandle> 클래스

## <a name="dispose-and-disposebool"></a>Dispose() 및 Dispose(bool)

<xref:System.IDisposable> 인터페이스에서는 매개 변수가 없는 단일 메서드인 <xref:System.IDisposable.Dispose%2A>를 구현해야 합니다. 또한 모든 봉인되지 않은 클래스에는 추가 `Dispose(bool)` 오버로드 메서드가 구현되어야 합니다.

- 매개 변수가 없는 `public` 비가상(Visual Basic의 경우 `NonInheritable`) <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 구현

- 서명이 다음과 같은 `protected virtual`(Visual Basic의 경우 `Overridable`) `Dispose` 메서드

  [!code-csharp[Conceptual.Disposable#8](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#8)]
  [!code-vb[Conceptual.Disposable#8](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#8)]

  > [!IMPORTANT]
  > `disposing` 매개 변수가 종료자에서 호출되는 경우 `false`이고 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType> 메서드에서 호출되는 경우 `true`여야 합니다. 즉, 결정적으로 호출되는 경우에는 `true`이고, 비결정적으로 호출되는 경우에는 `false`입니다.

### <a name="the-dispose-method"></a>Dispose() 메서드

`public`, 비가상(Visual Basic의 경우 `NonInheritable`), 매개 변수 없는 `Dispose` 메서드는 형식의 소비자에 의해 호출되므로, 관리되지 않는 리소스를 해제하고, 일반 정리를 수행하고, 종료자(있는 경우)를 실행할 필요가 없음을 나타내기 위한 것입니다. 관리되는 개체와 관련된 실제 메모리를 해제하는 것은 항상 [가비지 수집기](index.md)의 영역입니다. 이로 인해 다음과 같은 표준 구현이 수행됩니다.

[!code-csharp[Conceptual.Disposable#7](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/dispose1.cs#7)]
[!code-vb[Conceptual.Disposable#7](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/dispose1.vb#7)]

`Dispose` 메서드가 모든 개체를 정리하므로, 가비지 수집기가 더 이상 개체의 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 재정의를 호출할 필요가 없습니다. 따라서 <xref:System.GC.SuppressFinalize%2A> 메서드를 호출하면 가비지 수집기가 종료자를 실행하지 않도록 방지됩니다. 형식에 종료자가 없는 경우 <xref:System.GC.SuppressFinalize%2A?displayProperty=nameWithType>에 대한 호출이 영향을 미치지 않습니다. 실제 정리는 `Dispose(bool)` 메서드 오버로드에 의해 수행됩니다.

### <a name="the-disposebool-method-overload"></a>Dispose(bool) 메서드 오버로드

오버로드에서 `disposing` 매개 변수는 메서드 호출이 <xref:System.IDisposable.Dispose%2A> 메서드(값이 `true`)에서 수행되는지 또는 종료자(값이 `false`)에서 수행되는지를 나타내는 <xref:System.Boolean>입니다.

메서드 본문은 다음과 같은 두 가지 코드 블록으로 구성됩니다.

- 관리되지 않는 리소스를 해제하는 블록. 이 블록은 `disposing` 매개 변수의 값에 관계없이 실행됩니다.
- 관리되는 리소스를 해제하는 조건부 블록. 이 블록은 `disposing` 값이 `true`인 경우 실행됩니다. 해제되는 관리되는 리소스는 다음과 같습니다.

  - **<xref:System.IDisposable>을 구현하는 관리되는 개체.** 조건부 블록을 사용하여 <xref:System.IDisposable.Dispose%2A> 구현(cascade dispose)을 호출할 수 있습니다. 관리되지 않는 리소스를 래핑하기 위해 <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>의 파생 클래스를 사용한 경우 여기에서 <xref:System.Runtime.InteropServices.SafeHandle.Dispose?displayProperty=nameWithType> 구현을 호출해야 합니다.

  - **많은 메모리를 사용하거나 부족한 리소스를 사용하는 관리되는 개체.** 관리되는 큰 개체 참조를 `null`에 할당하여 더 연결할 수 없는 상태로 만듭니다. 이렇게 하면 비결정적으로 회수된 경우보다 빠르게 해제됩니다.

메서드 호출이 종료자에서 수행된 경우 관리되지 않는 리소스를 해제하는 코드만 실행되어야 합니다. 구현자는 false 경로가 회수되었을 수 있는 관리되는 개체와 상호 작용하지 않도록 해야 합니다. 이는 종료하는 동안 가비지 수집기가 관리되는 개체를 제거하는 순서가 비결정적이기 때문에 중요합니다.

## <a name="cascade-dispose-calls"></a>Cascade dispose 호출

클래스가 필드 또는 속성을 소유하고 해당 형식이 <xref:System.IDisposable>을 구현하는 경우 포함하는 클래스 자체도 <xref:System.IDisposable>을 구현해야 합니다. <xref:System.IDisposable> 구현을 인스턴스화하고 인스턴스 멤버로 저장하는 클래스도 정리를 담당합니다. 이는 참조되는 삭제 가능한 형식에 <xref:System.IDisposable.Dispose%2A> 메서드를 통해 결정적으로 정리를 수행할 수 있는 기회를 제공하기 위한 것입니다. 이 예제에서 클래스는 `sealed`입니다(Visual Basic의 경우 `NotInheritable`).

[!code-csharp[Conceptual.Disposable#1](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/disposable1.cs#1)]
[!code-vb[Conceptual.Disposable#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/disposable1.vb#1)]

## <a name="implement-the-dispose-pattern"></a>Dispose 패턴 구현

모든 봉인되지 않은 클래스 또는 `NotInheritable`으로 수정되지 않는 Visual Basic 클래스는 상속될 수 있기 때문에 잠재적 기본 클래스로 간주해야 합니다. 잠재적 기본 클래스에 대한 삭제 패턴을 구현하는 경우 다음을 제공해야 합니다.

- <xref:System.IDisposable.Dispose%2A> 메서드를 호출하는 `Dispose(bool)` 구현
- 실제 정리를 수행하는 `Dispose(bool)` 메서드
- 관리되지 않는 리소스를 래핑하는 <xref:System.Runtime.InteropServices.SafeHandle>에서 파생된 클래스(권장) 또는 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 메서드 재정의 <xref:System.Runtime.InteropServices.SafeHandle> 클래스는 종료자를 제공하므로 직접 작성할 필요가 없습니다.

> [!IMPORTANT]
> 기본 클래스는 관리되는 개체만 참조할 수 있으며 Dispose 패턴을 구현할 수 있습니다. 이러한 경우 종료자는 필요하지 않습니다. 종료자는 관리되지 않는 리소스를 직접 참조하는 경우에만 필요합니다.

SafeHandle을 사용하는 기본 클래스에 대한 삭제 패턴을 구현하는 일반적인 패턴은 다음과 같습니다.

[!code-csharp[System.IDisposable#3](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base1.cs#3)]
[!code-vb[System.IDisposable#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base1.vb#3)]

> [!NOTE]
> 이전 예제에서는 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 사용하여 패턴을 보여 줍니다. <xref:System.Runtime.InteropServices.SafeHandle>에서 파생된 개체를 대신 사용할 수 있습니다. 예제에서는 해당 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 제대로 인스턴스화하지 않습니다.

<xref:System.Object.Finalize%2A?displayProperty=nameWithType>를 재정의하는 기본 클래스에 대한 삭제 패턴을 구현하는 일반적인 패턴은 다음과 같습니다.

[!code-csharp[System.IDisposable#5](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/base2.cs#5)]
[!code-vb[System.IDisposable#5](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/base2.vb#5)]

> [!TIP]
> C#에서는 <xref:System.Object.Finalize%2A?displayProperty=nameWithType>를 재정의하여 [종료자](../../csharp/programming-guide/classes-and-structs/destructors.md)를 만듭니다. Visual Basic에서는 `Protected Overrides Sub Finalize()`를 사용하여 이 작업을 수행합니다.

## <a name="implement-the-dispose-pattern-for-a-derived-class"></a>파생 클래스에 대한 Dispose 패턴 구현

<xref:System.IDisposable>의 기본 클래스 구현은 파생된 클래스에 의해 상속되므로 <xref:System.IDisposable> 인터페이스를 구현하는 클래스에서 파생된 클래스가 <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>을 구현하지 않아야 합니다. 대신, 파생 클래스를 정리하려면 다음을 제공합니다.

- 기본 클래스 메서드를 재정의하고 파생 클래스의 실제 정리를 수행하는 `protected override void Dispose(bool)` 메서드. 또한 이 메서드는 기본 클래스의 `base.Dispose(bool)`(Visual Basic의 경우 `MyBase.Dispose(bool)`) 메서드를 호출하며 인수에 대해 삭제 중 상태를 전달합니다.
- 관리되지 않는 리소스를 래핑하는 <xref:System.Runtime.InteropServices.SafeHandle>에서 파생된 클래스(권장) 또는 <xref:System.Object.Finalize%2A?displayProperty=nameWithType> 메서드 재정의 <xref:System.Runtime.InteropServices.SafeHandle> 클래스는 사용자가 코딩할 필요가 없는 종료자를 제공합니다. 종료자를 제공하는 경우 `disposing` 인수가 `false`인 `Dispose(bool)` 오버로드를 호출해야 합니다.

SafeHandle을 사용하는 파생된 클래스에 대한 삭제 패턴을 구현하는 일반적인 패턴은 다음과 같습니다.

[!code-csharp[System.IDisposable#4](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived1.cs#4)]
[!code-vb[System.IDisposable#4](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived1.vb#4)]

> [!NOTE]
> 이전 예제에서는 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 사용하여 패턴을 보여 줍니다. <xref:System.Runtime.InteropServices.SafeHandle>에서 파생된 개체를 대신 사용할 수 있습니다. 예제에서는 해당 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 제대로 인스턴스화하지 않습니다.

<xref:System.Object.Finalize%2A?displayProperty=nameWithType>를 재정의하는 파생된 클래스에 대한 삭제 패턴을 구현하는 일반적인 패턴은 다음과 같습니다.

[!code-csharp[System.IDisposable#6](../../../samples/snippets/csharp/VS_Snippets_CLR_System/system.idisposable/cs/derived2.cs#6)]
[!code-vb[System.IDisposable#6](../../../samples/snippets/visualbasic/VS_Snippets_CLR_System/system.idisposable/vb/derived2.vb#6)]

## <a name="implement-the-dispose-pattern-with-safe-handles"></a>SafeHandle을 사용하여 Dispose 패턴 구현

다음 예제는 SafeHandle을 사용하여 관리되지 않는 리소스를 캡슐화하는 기본 클래스에 대한 삭제 패턴인 `DisposableStreamResource`를 보여 줍니다. 이는 `DisposableStreamResource`을 사용하여 열려 있는 파일을 나타내는 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 래핑하는 <xref:System.IO.Stream> 클래스를 정의합니다. 또한 이 클래스에는 파일 스트림에서 총 바이트 수를 반환하는 단일 속성인 `Size`도 포함됩니다.

[!code-csharp[Conceptual.Disposable#9](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/base1.cs#9)]
[!code-vb[Conceptual.Disposable#9](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/base1.vb#9)]

## <a name="implement-the-dispose-pattern-for-a-derived-class-with-safe-handles"></a>SafeHandle을 사용하여 파생 클래스에 대한 Dispose 패턴 구현

다음 예제는 이전 예제에 제공된 `DisposableStreamResource2` 클래스에서 상속되는 파생된 클래스에 대한 삭제 패턴인 `DisposableStreamResource`를 보여 줍니다. 클래스에서 추가 메서드인 `WriteFileInfo`를 추가하고 <xref:Microsoft.Win32.SafeHandles.SafeFileHandle> 개체를 사용하여 쓰기 가능 파일의 핸들을 래핑합니다.

[!code-csharp[Conceptual.Disposable#10](../../../samples/snippets/csharp/VS_Snippets_CLR/conceptual.disposable/cs/derived1.cs#10)]
[!code-vb[Conceptual.Disposable#10](../../../samples/snippets/visualbasic/VS_Snippets_CLR/conceptual.disposable/vb/derived1.vb#10)]

## <a name="see-also"></a>참조

- <xref:System.GC.SuppressFinalize%2A>
- <xref:System.IDisposable>
- <xref:System.IDisposable.Dispose%2A?displayProperty=nameWithType>
- <xref:Microsoft.Win32.SafeHandles>
- <xref:System.Runtime.InteropServices.SafeHandle?displayProperty=nameWithType>
- <xref:System.Object.Finalize%2A?displayProperty=nameWithType>
- [클래스 및 구조체 정의 및 사용(C++/CLI)](/cpp/dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli)
