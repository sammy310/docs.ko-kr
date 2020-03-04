---
title: 명시적 인터페이스 구현 - C# 프로그래밍 가이드
ms.date: 01/24/2020
helpviewer_keywords:
- explicit interfaces [C#]
- interfaces [C#], explicit
ms.assetid: 181c901f-0d4c-4f29-97fc-895079617bf2
ms.openlocfilehash: c6f1f849e0d4e831802b4c9b8b4bc3887363a34c
ms.sourcegitcommit: 44a7cd8687f227fc6db3211ccf4783dc20235e51
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/26/2020
ms.locfileid: "77628152"
---
# <a name="explicit-interface-implementation-c-programming-guide"></a>명시적 인터페이스 구현(C# 프로그래밍 가이드)

[클래스](../../language-reference/keywords/class.md)가 시그니처가 동일한 멤버를 포함하는 두 인터페이스를 구현하는 경우, 해당 멤버를 클래스에 구현하면 양쪽 인터페이스 모두가 해당 멤버를 구현에 사용합니다. 다음 예제에서 `Paint`에 대한 모든 호출은 같은 메서드를 호출합니다. 이 첫 번째 샘플에서는 다음 형식을 정의합니다.

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefineTypes)]

다음 샘플에서는 다음 메서드를 호출합니다.

[!code-csharp[DefineSimpleTypes](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallMethods)]

두 인터페이스 멤버가 동일한 기능을 수행하지 않을 경우, 인터페이스 둘 중 하나 또는 둘 다 잘못 구현될 수 있습니다. 인터페이스를 통해서만 호출되고 해당 인터페이스에만 관련되는 클래스 멤버를 만드는 방식으로 인터페이스 멤버를 명시적으로 구현할 수 있습니다. 인터페이스 이름과 마침표를 사용하여 클래스 멤버의 이름을 지정하면 됩니다. 예를 들어:

[!code-csharp[DefineExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#ExplicitImplementation)]

클래스 멤버 `IControl.Paint`는 `IControl` 인터페이스를 통해서만 사용할 수 있고 `ISurface.Paint`는 `ISurface`를 통해서만 사용할 수 있습니다. 두 메서드 구현은 서로 별개이며 어느 쪽도 클래스에서 직접 사용할 수 없습니다. 예를 들어:

[!code-csharp[CallExplicitImplementation](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallExplicitImplementation)]

명시적 구현은 두 인터페이스가 속성이나 메서드와 같이 동일한 이름을 가진 서로 다른 멤버를 선언하는 사례를 해결하는 데도 사용됩니다. 두 인터페이스를 모두 구현하려면 클래스는 `P` 속성이나 `P` 메서드 중 하나 또는 둘 다에 대해 명시적 구현을 사용하여 컴파일러 오류를 방지해야 합니다. 예를 들어:

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#NameCollision)]

클래스가 인터페이스로부터 메서드 구현을 상속하는 경우, 해당 메서드는 인터페이스 형식의 참조를 통해서만 액세스할 수 있습니다. 상속된 멤버는 public 인터페이스의 일부로 표시되지 않습니다. 다음 샘플은 인터페이스에 메서드에 대한 기본 구현을 정의합니다.

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#DefaultImplementation)]

다음 샘플은 기본 구현을 호출합니다.

[!code-csharp[NameCollisions](~/samples/snippets/csharp/interfaces/ExplicitImplementation.cs#CallDefaultImplementation)]

`IControl` 인터페이스를 구현하는 모든 클래스는 기본 `Paint` 메서드를 public 메서드로 또는 명시적 인터페이스 구현으로 재정의할 수 있습니다.

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [클래스 및 구조체](../classes-and-structs/index.md)
- [인터페이스](./index.md)
- [상속](../classes-and-structs/inheritance.md)
