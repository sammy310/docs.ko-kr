---
description: var - C# 참조
title: var - C# 참조
ms.date: 10/02/2020
f1_keywords:
- var
- var_CSharpKeyword
helpviewer_keywords:
- var keyword [C#]
ms.assetid: 0777850a-2691-4e3e-927f-0c850f5efe15
ms.openlocfilehash: d04bea9bcf5be726d3e81a1a53abed31f59330a0
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2020
ms.locfileid: "91608714"
---
# <a name="var-c-reference"></a><span data-ttu-id="f2b67-103">var (C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f2b67-103">var (C# reference)</span></span>

<span data-ttu-id="f2b67-104">C# 3부터 메서드 범위에서 선언된 변수에 암시적 “형식” `var`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-104">Beginning with C# 3, variables that are declared at method scope can have an implicit "type" `var`.</span></span> <span data-ttu-id="f2b67-105">암시적 형식 지역 변수는 형식을 직접 선언한 것처럼 강력한 형식이지만 컴파일러가 형식을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-105">An implicitly typed local variable is strongly typed just as if you had declared the type yourself, but the compiler determines the type.</span></span> <span data-ttu-id="f2b67-106">`i`의 다음 두 선언은 기능이 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-106">The following two declarations of `i` are functionally equivalent:</span></span>

```csharp
var i = 10; // Implicitly typed.
int i = 10; // Explicitly typed.
```

> [!IMPORTANT]
> <span data-ttu-id="f2b67-107">[null 허용 참조 형식](../builtin-types/nullable-reference-types.md)을 사용하도록 설정하고 `var`를 사용하면 식 형식이 null 허용이 아니더라도 항상 null 허용 참조 형식을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-107">When `var` is used with [nullable reference types](../builtin-types/nullable-reference-types.md) enabled, it always implies a nullable reference type even if the expression type isn't nullable.</span></span>

<span data-ttu-id="f2b67-108">`var` 키워드는 일반적으로 생성자 호출 식과 함께 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-108">A common use of the `var` keyword is with constructor invocation expressions.</span></span> <span data-ttu-id="f2b67-109">`var`를 사용하면 다음 예제와 같이 변수 선언 및 개체 인스턴스화에서 형식 이름을 반복하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-109">The use of `var` allows you to not repeat a type name in a variable declaration and object instantiation, as the following example shows:</span></span>

```csharp
var xs = new List<int>();
```

<span data-ttu-id="f2b67-110">C# 9.0부터 대상으로 형식화된 [`new` 식](../operators/new-operator.md)을 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-110">Beginning with C# 9.0, you can use a target-typed [`new` expression](../operators/new-operator.md) as an alternative:</span></span>

```csharp
List<int> xs = new();
List<int>? ys = new();
```

## <a name="example"></a><span data-ttu-id="f2b67-111">예제</span><span class="sxs-lookup"><span data-stu-id="f2b67-111">Example</span></span>

<span data-ttu-id="f2b67-112">다음 예제에서는 두 가지 쿼리 식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-112">The following example shows two query expressions.</span></span> <span data-ttu-id="f2b67-113">첫 번째 식에서는 `var`을 사용할 수 있지만, 쿼리 결과의 형식을 `IEnumerable<string>`으로 명시적으로 정의할 수 있기 때문에 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-113">In the first expression, the use of `var` is permitted but is not required, because the type of the query result can be stated explicitly as an `IEnumerable<string>`.</span></span> <span data-ttu-id="f2b67-114">그러나 두 번째 식에서 `var`은 결과가 익명 형식의 컬렉션이 되도록 허용하고 해당 형식의 이름은 컴파일러 자체에만 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-114">However, in the second expression, `var` allows the result to be a collection of anonymous types, and the name of that type is not accessible except to the compiler itself.</span></span> <span data-ttu-id="f2b67-115">`var`을 사용하면 결과에 대한 새 클래스를 만들 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-115">Use of `var` eliminates the requirement to create a new class for the result.</span></span> <span data-ttu-id="f2b67-116">예제 #2에서는 `foreach` 반복 변수 `item`도 암시적 형식이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2b67-116">Note that in Example #2, the `foreach` iteration variable `item` must also be implicitly typed.</span></span>

[!code-csharp[csrefKeywordsTypes#18](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsTypes/CS/keywordsTypes.cs#18)]

## <a name="see-also"></a><span data-ttu-id="f2b67-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f2b67-117">See also</span></span>

- [<span data-ttu-id="f2b67-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f2b67-118">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f2b67-119">암시적 형식 지역 변수</span><span class="sxs-lookup"><span data-stu-id="f2b67-119">Implicitly typed local variables</span></span>](../../programming-guide/classes-and-structs/implicitly-typed-local-variables.md)
- [<span data-ttu-id="f2b67-120">LINQ 쿼리 작업의 형식 관계</span><span class="sxs-lookup"><span data-stu-id="f2b67-120">Type relationships in LINQ query operations</span></span>](../../programming-guide/concepts/linq/type-relationships-in-linq-query-operations.md)
