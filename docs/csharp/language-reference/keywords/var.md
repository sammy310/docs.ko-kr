---
description: var - C# 참조
title: var - C# 참조
ms.date: 07/20/2015
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: 303a880a54a79e50515060e0ea28e8d021fa1b76
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141714"
---
# <a name="var-c-reference"></a><span data-ttu-id="cc42a-103">var(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="cc42a-103">var (C# Reference)</span></span>

<span data-ttu-id="cc42a-104">Visual C# 3.0부터 메서드 범위에서 선언된 변수에 암시적 "형식" `var`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc42a-104">Beginning in Visual C# 3.0, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="cc42a-105">암시적 형식 지역 변수는 형식을 직접 선언한 것처럼 강력한 형식이지만 컴파일러가 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="cc42a-105">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="cc42a-106">`i`의 다음 두 선언은 기능이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="cc42a-106">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

<span data-ttu-id="cc42a-107">자세한 내용은 [암시적 형식 지역 변수](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) 및 [LINQ 쿼리 작업의 형식 관계](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc42a-107">For more information, see [Implicitly Typed Local Variables](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md) and [Type Relationships in LINQ Query Operations](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cc42a-108">nullable 참조 형식을 사용하도록 설정하고 `var`을 사용하면 식 형식이 nullable이 아니더라도 항상 nullable 참조 형식을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="cc42a-108">When `var` is used with nullable reference types enabled, it always implies a nullable reference type even if the expression type isn't nullable.</span></span>

## <a name="example"></a><span data-ttu-id="cc42a-109">예제</span><span class="sxs-lookup"><span data-stu-id="cc42a-109">Example</span></span>

<span data-ttu-id="cc42a-110">다음 예제에서는 두 가지 쿼리 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cc42a-110">The following example shows two query expressions.</span></span> <span data-ttu-id="cc42a-111">첫 번째 식에서는 `var`을 사용할 수 있지만, 쿼리 결과의 형식을 `IEnumerable<string>`으로 명시적으로 정의할 수 있기 때문에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cc42a-111">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="cc42a-112">그러나 두 번째 식에서 `var`은 결과가 익명 형식의 컬렉션이 되도록 허용하고 해당 형식의 이름은 컴파일러 자체에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cc42a-112">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="cc42a-113">`var`을 사용하면 결과에 대한 새 클래스를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cc42a-113">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="cc42a-114">예제 #2에서는 `foreach` 반복 변수 `item`도 암시적 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc42a-114">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="cc42a-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cc42a-115">See also</span></span>

- [<span data-ttu-id="cc42a-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="cc42a-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="cc42a-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="cc42a-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="cc42a-118">암시적 형식 지역 변수</span><span class="sxs-lookup"><span data-stu-id="cc42a-118">Implicitly Typed Local Variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
