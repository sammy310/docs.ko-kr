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
# <a name="init-c-reference"></a><span data-ttu-id="dff19-103">init(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="dff19-103">init (C# Reference)</span></span>

<span data-ttu-id="dff19-104">C# 9 이상에서 키워드는 `init` 속성 또는 인덱서에 *접근자* 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dff19-104">In C# 9 and later, the `init` keyword defines an *accessor* method in a property or indexer.</span></span> <span data-ttu-id="dff19-105">init 전용 setter는 개체 생성 중에만 속성 또는 인덱서 요소에 값을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="dff19-105">An init-only setter assigns a value to the property or the indexer element only during object construction.</span></span> <span data-ttu-id="dff19-106">자세한 내용 및 예제는 [속성](../../programming-guide/classes-and-structs/properties.md), [자동 구현 속성](../../programming-guide/classes-and-structs/auto-implemented-properties.md) 및 [인덱서](../../programming-guide/indexers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dff19-106">For more information and examples, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md), and [Indexers](../../programming-guide/indexers/index.md).</span></span>

<span data-ttu-id="dff19-107">다음 예제에서는 `Seconds`라는 속성의 `get` 및 `init` 접근자를 모두 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="dff19-107">The following example defines both a `get` and an `init` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="dff19-108">`_seconds`라는 private 필드를 사용하여 속성 값을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="dff19-108">It uses a private field named `_seconds` to back the property value.</span></span>

[!code-csharp[init#1](snippets/InitExample1.cs)]

<span data-ttu-id="dff19-109">대체로 `init` 접근자는 앞의 예제와 마찬가지로 값을 할당하는 단일 명령문으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="dff19-109">Often, the `init` accessor consists of a single statement that assigns a value, as it did in the previous example.</span></span> <span data-ttu-id="dff19-110">`init` 접근자를 식 본문 멤버로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dff19-110">You can implement the `init` accessor as an expression-bodied member.</span></span> <span data-ttu-id="dff19-111">다음 예제에서는 `get` 및 `init` 접근자 둘 다를 식 본문 멤버로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dff19-111">The following example implements both the `get` and the `init` accessors as expression-bodied members.</span></span>

[!code-csharp[init#3](snippets/InitExample3.cs)]
  
<span data-ttu-id="dff19-112">속성의 `get` 및 `init` 접근자가 private 지원 필드의 값 설정 또는 검색 이외의 다른 작업을 수행하지 않는 간단한 사례의 경우 자동 구현 속성에 대한 C# 컴파일러의 지원을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dff19-112">For simple cases in which a property's `get` and `init` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="dff19-113">다음 예제에서는 `Hours`를 자동 구현 속성으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="dff19-113">The following example implements `Hours` as an auto-implemented property.</span></span>

[!code-csharp[init#2](snippets/InitExample2.cs)]
  
## <a name="c-language-specification"></a><span data-ttu-id="dff19-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="dff19-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="dff19-115">참조</span><span class="sxs-lookup"><span data-stu-id="dff19-115">See also</span></span>

- [<span data-ttu-id="dff19-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="dff19-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="dff19-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="dff19-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="dff19-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="dff19-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="dff19-119">속성</span><span class="sxs-lookup"><span data-stu-id="dff19-119">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
