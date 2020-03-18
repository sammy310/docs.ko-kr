---
title: 액세스 한정자 - C# 프로그래밍 가이드
ms.date: 03/08/2020
helpviewer_keywords:
- C# Language, access modifiers
- access modifiers [C#], about
ms.assetid: 6e81ee82-224f-4a12-9baf-a0dca2656c5b
ms.openlocfilehash: 749d53344a2518966cfa5d937069ba73dfd6be8f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77628230"
---
# <a name="access-modifiers-c-programming-guide"></a>액세스 한정자(C# 프로그래밍 가이드)

모든 형식과 형식 멤버에는 액세스 수준이 있습니다. 액세스 수준은 사용 중인 어셈블리나 다른 어셈블리에서 형식 또는 형식 멤버를 사용할 수 있는지 여부를 제어합니다. 다음 액세스 한정자를 사용하여 형식 또는 멤버를 선언할 때 해당 항목의 액세스 수준을 지정할 수 있습니다.

- [public](../../language-reference/keywords/public.md): 동일한 어셈블리의 다른 코드나 해당 어셈블리를 참조하는 다른 어셈블리의 코드에서 형식이나 멤버에 액세스할 수 있습니다.
- [private](../../language-reference/keywords/private.md): 같은 `class` 또는 `struct`의 코드에서만 형식 또는 멤버에 액세스할 수 있습니다.
- [protected](../../language-reference/keywords/protected.md): 같은 `class` 또는 해당 `class`에서 파생된 `class`의 코드에서만 형식 또는 멤버에 액세스할 수 있습니다.
- [internal](../../language-reference/keywords/internal.md): 동일한 어셈블리의 코드에서는 형식이나 멤버에 액세스할 수 있지만 다른 어셈블리의 코드에서는 액세스할 수 없습니다.
- [protected internal](../../language-reference/keywords/protected-internal.md): 형식 또는 멤버가 선언된 어셈블리의 모든 코드에서 또는 다른 어셈블리의 파생 `class` 내에서 형식 또는 멤버에 액세스할 수 있습니다.
- [private protected](../../language-reference/keywords/private-protected.md): 형식 또는 멤버가 선언된 어셈블리, 같은 `class`나 해당 `class`에서 파생된 형식의 코드에서만 형식 또는 멤버에 액세스할 수 있습니다.

다음 예제에서는 형식 및 멤버에 대해 액세스 한정자를 지정하는 방법을 보여 줍니다.

[!code-csharp[PublicAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#PublicAccess)]

모든 액세스 한정자를 모든 컨텍스트에서 모든 형식 또는 멤버에서 사용할 수 있는 것은 아닙니다. 형식 멤버의 액세스 수준이 해당 형식 멤버를 포함하는 형식의 액세스 수준으로 제한되는 경우도 있습니다.

## <a name="class-and-struct-accessibility"></a>클래스 및 구조체 액세스 수준  

네임스페이스 내에서 직접 선언된(즉, 다른 클래스 또는 구조체 내에 중첩되지 않은) 클래스와 구조체는 `public`과 `internal` 중 하나일 수 있습니다. 액세스 한정자가 지정되지 않은 경우 기본값은 `Internal`입니다.  

구조체 멤버(중첩 클래스 및 구조체 포함)는 `public`, `internal` 또는 `private`으로 선언할 수 있습니다. 클래스 멤버(중첩 클래스 포함)는 `public`, `protected internal`, `protected`, `internal`, `private protected` 또는 `private`으로 선언할 수 있습니다. 클래스 멤버와 구조체 멤버(중첩 클래스 및 구조체 포함)의 액세스 수준은 기본적으로 `private`입니다. private 중첩 형식은 해당 형식을 포함하는 형식 외부에서 액세스할 수 없습니다.

파생 클래스는 기본 형식보다 높은 액세스 수준을 가질 수 없습니다. internal 클래스 `A`에서 파생된 public 클래스 `B`를 선언할 수 없습니다. 이것이 허용된다면 파생 클래스에서 `A`의 모든 `protected` 또는 `internal` 멤버에 액세스할 수 있게 되므로 결과적으로 `A`가 public이 되는 것과 같아집니다.

다른 특정 어셈블리에서 internal 형식에 액세스할 수 있도록 하려면 `InternalsVisibleToAttribute`를 시용하면 됩니다. 자세한 내용은 [Friend 어셈블리](../../../standard/assembly/friend.md)를 참조하세요.

## <a name="class-and-struct-member-accessibility"></a>클래스 및 구조체 멤버 액세스 수준  

중첩 클래스 및 구조체를 포함한 클래스 멤버는 6가지 액세스 형식으로 선언될 수 있습니다. 구조체는 상속을 지원하지 않으므로 구조체 멤버는 `protected`, `protected internal` 또는 `private protected`로 선언할 수 없습니다.

일반적으로 멤버의 액세스 수준은 해당 멤버를 포함하는 형식의 액세스 수준보다 크지 않습니다. 그러나 멤버가 인터페이스 메서드를 구현하거나 public 기본 클래스에 정의된 가상 메서드를 재정의하는 경우에는 어셈블리 외부에서 internal 클래스의 `public` 멤버에 액세스할 수 있습니다.

멤버의 필드, 속성 또는 이벤트 형식은 멤버 자체의 액세스 수준 이상을 가져야 합니다. 마찬가지로, 메서드, 인덱서 또는 대리자의 반환 형식과 매개 변수 형식은 멤버 자체의 액세스 수준 이상을 가져야 합니다. 예를 들어 `C`도 `public`이 아닌 이상 클래스 `C`를 반환하는 `public` 메서드 `M`이 있을 수 없습니다. 마찬가지로, `A`가 `private`으로 선언되었다면 `A` 형식의 `protected` 속성이 있을 수 없습니다.

사용자 정의 연산자는 항상 `public` 및 `static`으로 선언해야 합니다. 자세한 내용은 [연산자 오버로드](../../language-reference/operators/operator-overloading.md)를 참조하세요.

종료자에는 접근성 한정자를 사용할 수 없습니다.

`class` 또는 `struct` 멤버의 액세스 수준을 설정하려면 다음 예제와 같이 멤버 선언에 해당 키워드를 추가하세요.

[!code-csharp[MethodAccess](~/samples/snippets/csharp/objectoriented/accessmodifiers.cs#MethodAccess)]

## <a name="other-types"></a>기타 형식

네임스페이스 내에서 직접 선언된 인터페이스는 `public` 또는 `internal`일 수 있고, 클래스 및 구조체와 마찬가지로 인터페이스도 기본적으로 `internal` 액세스로 설정됩니다. 인터페이스는 다른 형식이 클래스나 구조체에 액세스하는 데 사용되므로 인터페이스 멤버는 기본적으로 `public`입니다. 인터페이스 멤버 선언은 모든 액세스 한정자를 포함할 수 있습니다. 이는 정적 메서드가 모든 클래스 구현자에 필요한 공통된 구현을 제공하도록 할 때 가장 유용합니다.

열거형 멤버는 항상 `public`이고 어떤 액세스 한정자도 적용할 수 없습니다.

대리자는 클래스 및 구조체처럼 동작합니다. 기본적으로 대리자는 네임스페이스 내에서 직접 선언된 경우 `internal` 액세스를 갖고 중첩된 경우 `private` 액세스를 갖습니다.

## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  

## <a name="see-also"></a>참조

- [C# 프로그래밍 가이드](../index.md)
- [클래스 및 구조체](./index.md)
- [인터페이스](../interfaces/index.md)
- [private](../../language-reference/keywords/private.md)
- [public](../../language-reference/keywords/public.md)
- [internal](../../language-reference/keywords/internal.md)
- [protected](../../language-reference/keywords/protected.md)
- [protected internal](../../language-reference/keywords/protected-internal.md)
- [private protected](../../language-reference/keywords/private-protected.md)
- [class](../../language-reference/keywords/class.md)
- [struct](../../language-reference/builtin-types/struct.md)
- [interface](../../language-reference/keywords/interface.md)
