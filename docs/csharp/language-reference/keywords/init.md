---
description: init 키워드 - C# 참조
title: init 키워드 - C# 참조
ms.date: 03/03/2021
f1_keywords:
- init
- init_CSharpKeyword
helpviewer_keywords:
- init keyword [C#]
ms.openlocfilehash: 2271b5332c8bfd3223d0c034a44eca4e2ca0ca54
ms.sourcegitcommit: e3cf8227573e13b8e1f4e3dc007404881cdafe47
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/11/2021
ms.locfileid: "103190438"
---
# <a name="init-c-reference"></a>init(C# 참조)

C# 9 이상에서 키워드는 `init` 속성 또는 인덱서에 *접근자* 메서드를 정의합니다. init 전용 setter는 개체 생성 중에만 속성 또는 인덱서 요소에 값을 할당합니다. 자세한 내용 및 예제는 [속성](../../programming-guide/classes-and-structs/properties.md), [자동 구현 속성](../../programming-guide/classes-and-structs/auto-implemented-properties.md) 및 [인덱서](../../programming-guide/indexers/index.md)를 참조하세요.

다음 예제에서는 `Seconds`라는 속성의 `get` 및 `init` 접근자를 모두 정의합니다. `_seconds`라는 private 필드를 사용하여 속성 값을 지원합니다.

[!code-csharp[init#1](snippets/InitExample1.cs)]

대체로 `init` 접근자는 앞의 예제와 마찬가지로 값을 할당하는 단일 명령문으로 구성됩니다. `init` 접근자를 식 본문 멤버로 구현할 수 있습니다. 다음 예제에서는 `get` 및 `init` 접근자 둘 다를 식 본문 멤버로 구현합니다.

[!code-csharp[init#3](snippets/InitExample3.cs)]
  
속성의 `get` 및 `init` 접근자가 private 지원 필드의 값 설정 또는 검색 이외의 다른 작업을 수행하지 않는 간단한 사례의 경우 자동 구현 속성에 대한 C# 컴파일러의 지원을 활용할 수 있습니다. 다음 예제에서는 `Hours`를 자동 구현 속성으로 구현합니다.

[!code-csharp[init#2](snippets/InitExample2.cs)]
  
## <a name="c-language-specification"></a>C# 언어 사양

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>참조

- [C# 참조](../index.md)
- [C# 프로그래밍 가이드](../../programming-guide/index.md)
- [C# 키워드](index.md)
- [속성](../../programming-guide/classes-and-structs/properties.md)
