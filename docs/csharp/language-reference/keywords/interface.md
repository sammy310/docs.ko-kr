---
title: interface - C# 참조
ms.date: 01/17/2020
f1_keywords:
- interface_CSharpKeyword
helpviewer_keywords:
- interface keyword [C#]
ms.assetid: 7da38e81-4f99-4bc5-b07d-c986b687eeba
ms.openlocfilehash: 473f5f8e226f0a144746ac943afcffdccd4777c7
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77625854"
---
# <a name="no-loc-textinterface-c-reference"></a>:::no-loc text="interface":::(C# 참조)

인터페이스는 계약을 정의합니다. 해당 계약을 구현 하는 [`class`](class.md) 또는 [`struct`](../builtin-types/struct.md)는 인터페이스에 정의된 구성원의 구현을 제공해야 합니다. C# 8.0부터 인터페이스는 구성원에 대한 기본 구현을 정의할 수 있습니다. 공통적인 기능에 대해 단일 구현을 제공하기 위해 [`static`](static.md) 구성원을 정의할 수도 있습니다.

다음 예제에서 `ImplementationClass` 클래스는 매개 변수가 없고 `void`를 반환하는 `SampleMethod`라는 메서드를 구현해야 합니다.

자세한 내용과 예제는 [인터페이스](../../programming-guide/interfaces/index.md)를 참조하세요.

## <a name="example"></a>예제

[!code-csharp[csrefKeywordsTypes#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#14)]

인터페이스는 네임스페이스 또는 클래스의 구성원일 수 있습니다. 인터페이스 선언에는 다음 구성원의 선언(구현이 없는 서명)을 포함할 수 있습니다.

- [메서드](../../programming-guide/classes-and-structs/methods.md)
- [속성](../../programming-guide/classes-and-structs/using-properties.md)
- [인덱서](../../programming-guide/indexers/using-indexers.md)
- [이벤트](event.md)

이러한 앞의 구성원 선언에는 일반적으로 본문이 포함되지 않습니다. C# 8.0부터는 인터페이스 구성원이 본문을 선언할 수 있습니다. 이를 *기본 구현*이라고 합니다. 본문이 있는 구성원은 인터페이스가 재정의 구현을 제공하지 않는 클래스 및 구조체에 대해 "기본" 구현을 제공하도록 허용할 수 있습니다. 또한 C# 8.0부터 인터페이스에는 다음이 포함될 수 있습니다.

- [상수](const.md)
- [연산자](../operators/operator-overloading.md)
- [정적 생성자](../../programming-guide/classes-and-structs/constructors.md#static-constructors).
- [중첩 형식](../../programming-guide/classes-and-structs/nested-types.md)
- [정적 필드, 메서드, 속성, 인덱서 및 이벤트](static.md)
- 명시적 인터페이스 구현 구문을 사용한 구성원 선언
- 명시적 액세스 한정자(기본 액세스는 [`public`](access-modifiers.md))

인터페이스에는 인스턴스 상태를 포함할 수 없습니다. 이제 정적 필드가 허용되지만 인터페이스에서는 인스턴스 필드가 허용되지 않습니다. [인스턴스 자동 속성](../../programming-guide/classes-and-structs/auto-implemented-properties.md)은 숨겨진 필드를 암시적으로 선언하므로 인터페이스에서 지원되지 않습니다. 이 규칙은 속성 선언에 미묘한 영향을 미칩니다. 인터페이스 선언에서 다음 코드는 `class` 또는 `struct`에서와 같이 자동으로 구현된 속성을 선언하지 않습니다. 대신, 기본 구현은 없지만 인터페이스를 구현하는 형식에서 구현되어야 하는 속성을 선언합니다.

```csharp
public interface INamed
{
  public string Name {get; set;}
}
```

인터페이스는 하나 이상의 기본 인터페이스에서 상속할 수 있습니다. 인터페이스가 기본 인터페이스에 구현된 [메서드를 재정의](override.md)하는 경우 [명시적 인터페이스 구현](../../programming-guide/interfaces/explicit-interface-implementation.md) 구문을 사용해야 합니다.

기본 형식 목록에 기본 클래스 및 인터페이스가 포함된 경우 기본 클래스가 목록의 첫 번째 항목이어야 합니다.

인터페이스를 구현하는 클래스는 해당 인터페이스의 멤버를 명시적으로 구현할 수 있습니다. 명시적으로 구현된 멤버는 클래스 인스턴스를 통해 액세스할 수 없고 인터페이스 인스턴스를 통해서만 액세스할 수 있습니다. 또한 기본 인터페이스 구성원은 인터페이스의 인스턴스를 통해서만 액세스할 수 있습니다.

명시적 인터페이스 구현에 대한 자세한 내용은 [명시적 인터페이스 구현](../../programming-guide/interfaces/explicit-interface-implementation.md)을 참조하세요.

## <a name="example"></a>예제

다음 예제에서는 인터페이스의 구현 방법을 보여 줍니다. 이 예제에서 인터페이스에는 속성 선언이 포함되어 있고, 클래스에는 구현이 포함되어 있습니다. `IPoint`를 구현하는 클래스의 모든 인스턴스에는 정수 속성 `x` 및 `y`가 있습니다.

[!code-csharp[csrefKeywordsTypes#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#15)]

## <a name="c-language-specification"></a>C# 언어 사양

자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [인터페이스](~/_csharplang/spec/interfaces.md) 섹션 및 [기본 인터페이스 구성원 - C# 8.0](~/_csharplang/proposals/csharp-8.0/default-interface-methods.md)의 기능 사양을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [참조 형식](reference-types.md)
- [인터페이스](../../programming-guide/interfaces/index.md)
- [속성 사용](../../programming-guide/classes-and-structs/using-properties.md)
- [인덱서 사용](../../programming-guide/indexers/using-indexers.md)
- [인터페이스](../../programming-guide/interfaces/index.md)
