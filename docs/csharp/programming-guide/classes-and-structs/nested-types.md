---
title: 중첩 형식 - C# 프로그래밍 가이드
description: 클래스, 구조체 또는 인터페이스 내에서 정의된 형식을 C#에서 중첩 형식이라고 합니다.
ms.date: 02/08/2020
helpviewer_keywords:
- nested types [C#]
ms.assetid: f2e1b315-e3d1-48ce-977f-7bae0960ba99
ms.openlocfilehash: 0741ae88103b16ce34fd5a38b789beaf428e734a
ms.sourcegitcommit: 0014aa4d5cb2da56a70e03fc68f663d64df5247a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/09/2020
ms.locfileid: "96918582"
---
# <a name="nested-types-c-programming-guide"></a>중첩 형식(C# 프로그래밍 가이드)

[클래스](../../language-reference/keywords/class.md), [구조체](../../language-reference/builtin-types/struct.md), [대리자](../../language-reference/builtin-types/reference-types.md#the-delegate-type) 또는 [인터페이스](../../language-reference/keywords/interface.md) 내에서 정의된 형식을 중첩 형식이라고 합니다. 예

[!code-csharp[DeclareNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedClass)]

외부 형식이 클래스, 인터페이스 또는 구조체 중 무엇인지에 관계없이, 중첩 형식은 기본적으로 [private](../../language-reference/keywords/private.md)으로 설정됩니다. 즉, 포함하는 형식에서만 액세스할 수 있습니다. 앞의 예제에서 `Nested` 클래스는 외부 형식에서 액세스할 수 없습니다.

다음과 같이 [액세스 한정자](../../language-reference/keywords/access-modifiers.md)를 지정하여 중첩 형식의 접근성을 정의할 수도 있습니다.

- **클래스** 의 중첩 형식은 [public](../../language-reference/keywords/public.md), [protected](../../language-reference/keywords/protected.md), [internal](../../language-reference/keywords/internal.md), [protected internal](../../language-reference/keywords/protected-internal.md), [private](../../language-reference/keywords/private.md) 또는 [private protected](../../language-reference/keywords/private-protected.md)일 수 있습니다.

   그러나 [sealed 클래스](../../language-reference/keywords/sealed.md) 내에서 `protected`, `protected internal` 또는 `private protected` 중첩 클래스를 정의하면 컴파일러 경고 [CS0628](../../misc/cs0628.md), “sealed 클래스에 새 protected 멤버가 선언되었습니다.”가 생성됩니다.
  
- **구조체** 의 중첩 형식은 [public](../../language-reference/keywords/public.md), [internal](../../language-reference/keywords/internal.md) 또는 [private](../../language-reference/keywords/private.md)일 수 있습니다.

다음 예제에서는 `Nested` 클래스를 public으로 설정합니다.

[!code-csharp[PublicNestedClass](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#PublicNestedClass)]

중첩 형식(내부 형식)은 이 형식을 포함하고 있는 형식(외부 형식)에 액세스할 수 있습니다. 포함하는 형식에 액세스하려면 중첩 형식의 생성자에 인수로 전달합니다. 예를 들어:

[!code-csharp[DeclareNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#DeclareNestedInstance)]

중첩 형식은 이 형식을 포함하는 형식에 액세스할 수 있는 모든 멤버에 액세스할 수 있습니다. 또한 상속 및 보호된 멤버를 포함하여 외부 형식의 개인 및 보호된 멤버에 액세스할 수 있습니다.

위 선언에서 `Nested` 클래스의 전체 이름은 `Container.Nested`입니다. 이 이름은 다음과 같이 중첩된 클래스의 새 인스턴스를 만드는 데 사용됩니다.

[!code-csharp[UseNestedInstance](~/samples/snippets/csharp/objectoriented/nestedtypes.cs#UseNestedInstance)]

## <a name="see-also"></a>참고 항목

- [C# 프로그래밍 가이드](../index.md)
- [클래스 및 구조체](./index.md)
- [액세스 한정자](./access-modifiers.md)
- [생성자](./constructors.md)
