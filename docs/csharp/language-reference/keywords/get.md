---
description: get - C# 참조
title: get - C# 참조
ms.date: 03/10/2017
f1_keywords:
- get_CSharpKeyword
- get
helpviewer_keywords:
- get keyword [C#]
ms.assetid: a52de048-fbe0-41b0-82ec-8e4ac04d3a71
ms.openlocfilehash: 7e13dc3ed6577717c64b4e36000a9e090f7b4751
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89139738"
---
# <a name="get-c-reference"></a><span data-ttu-id="55cf1-103">get(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="55cf1-103">get (C# Reference)</span></span>

<span data-ttu-id="55cf1-104">`get` 키워드는 속성 값 또는 인덱서 요소를 반환하는 속성 또는 인덱서의 *accessor* 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="55cf1-104">The `get` keyword defines an *accessor* method in a property or indexer that returns the property value or the indexer element.</span></span> <span data-ttu-id="55cf1-105">자세한 내용은 [속성](../../programming-guide/classes-and-structs/properties.md), [자동으로 구현된 속성](../../programming-guide/classes-and-structs/auto-implemented-properties.md) 및 [인덱서](../../programming-guide/indexers/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="55cf1-105">For more information, see [Properties](../../programming-guide/classes-and-structs/properties.md), [Auto-Implemented Properties](../../programming-guide/classes-and-structs/auto-implemented-properties.md) and [Indexers](../../programming-guide/indexers/index.md).</span></span>  
  
<span data-ttu-id="55cf1-106">다음 예제에서는 `Seconds`라는 속성의 `get` 및 `set` 접근자를 둘 다 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="55cf1-106">The following example defines both a `get` and a `set` accessor for a property named `Seconds`.</span></span> <span data-ttu-id="55cf1-107">`_seconds`라는 private 필드를 사용하여 속성 값을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="55cf1-107">It uses a private field named `_seconds` to back the property value.</span></span>  

 [!code-csharp[get#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  
  
<span data-ttu-id="55cf1-108">대체로 `get` 접근자는 앞의 예제와 마찬가지로 값을 반환하는 단일 문으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="55cf1-108">Often, the `get` accessor consists of a single statement that returns a value, as it did in the previous example.</span></span> <span data-ttu-id="55cf1-109">C# 7.0부터 `get` 접근자를 식 본문 멤버로 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55cf1-109">Starting with C# 7.0, you can implement the `get` accessor as an expression-bodied member.</span></span> <span data-ttu-id="55cf1-110">다음 예제에서는 `get` 및 `set` 접근자 둘 다를 식 본문 멤버로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="55cf1-110">The following example implements both the `get` and the `set` accessor as expression-bodied members.</span></span>

 [!code-csharp[get#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]

<span data-ttu-id="55cf1-111">속성의 `get` 및 `set` 접근자가 private 지원 필드의 값 설정 또는 검색 이외의 다른 작업을 수행하지 않는 간단한 사례의 경우 자동 구현 속성에 대한 C# 컴파일러의 지원을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55cf1-111">For simple cases in which a property's `get` and `set` accessors perform no other operation than setting or retrieving a value in a private backing field, you can take advantage of the C# compiler's support for auto-implemented properties.</span></span> <span data-ttu-id="55cf1-112">다음 예제에서는 `Hours`를 자동 구현 속성으로 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="55cf1-112">The following example implements `Hours` as an auto-implemented property.</span></span>
  
 [!code-csharp[get#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
  
## <a name="c-language-specification"></a><span data-ttu-id="55cf1-113">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="55cf1-113">C# Language Specification</span></span>

 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="55cf1-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="55cf1-114">See also</span></span>

- [<span data-ttu-id="55cf1-115">C# 참조</span><span class="sxs-lookup"><span data-stu-id="55cf1-115">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="55cf1-116">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="55cf1-116">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="55cf1-117">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="55cf1-117">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="55cf1-118">속성</span><span class="sxs-lookup"><span data-stu-id="55cf1-118">Properties</span></span>](../../programming-guide/classes-and-structs/properties.md)
