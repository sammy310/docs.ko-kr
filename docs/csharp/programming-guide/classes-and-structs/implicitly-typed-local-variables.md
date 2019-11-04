---
title: 암시적 형식 지역 변수 - C# 프로그래밍 가이드
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- implicitly-typed local variables [C#]
- var [C#]
ms.assetid: b9218fb2-ef5d-4814-8a8e-2bc29b0bbc9b
ms.openlocfilehash: 7010c38797ab64e5106c96c06cd814c143ca9c24
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73419382"
---
# <a name="implicitly-typed-local-variables-c-programming-guide"></a><span data-ttu-id="718bf-102">암시적 형식 지역 변수(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="718bf-102">Implicitly typed local variables (C# Programming Guide)</span></span>

<span data-ttu-id="718bf-103">명시적 형식을 제공하지 않고 지역 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-103">Local variables can be declared without giving an explicit type.</span></span> <span data-ttu-id="718bf-104">`var` 키워드는 초기화 문의 오른쪽에 있는 식에서 변수의 형식을 유추하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-104">The `var` keyword instructs the compiler to infer the type of the variable from the expression on the right side of the initialization statement.</span></span> <span data-ttu-id="718bf-105">유추된 형식은 기본 제공 형식, 무명 형식, 사용자 정의 형식 또는 .NET Framework 클래스 라이브러리에 정의된 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-105">The inferred type may be a built-in type, an anonymous type, a user-defined type, or a type defined in the .NET Framework class library.</span></span> <span data-ttu-id="718bf-106">`var`을 사용하여 배열을 초기화하는 방법에 대한 자세한 내용은 [암시적으로 형식화된 배열](../arrays/implicitly-typed-arrays.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="718bf-106">For more information about how to initialize arrays with `var`, see [Implicitly Typed Arrays](../arrays/implicitly-typed-arrays.md).</span></span>

<span data-ttu-id="718bf-107">다음 예제에서는 `var`을 사용하여 지역 변수를 선언하는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-107">The following examples show various ways in which local variables can be declared with `var`:</span></span>

[!code-csharp[csProgGuideLINQ#43](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#43)]

<span data-ttu-id="718bf-108">`var` 키워드는 "variant"를 의미하지 않고 변수가 느슨하게 형식화되었거나 런타임에 바인딩되었음을 나타내지도 않습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-108">It is important to understand that the `var` keyword does not mean "variant" and does not indicate that the variable is loosely typed, or late-bound.</span></span> <span data-ttu-id="718bf-109">단지 컴파일러가 가장 적절한 형식을 결정하고 할당함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-109">It just means that the compiler determines and assigns the most appropriate type.</span></span>

<span data-ttu-id="718bf-110">`var` 키워드는 다음과 같은 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-110">The `var` keyword may be used in the following contexts:</span></span>

- <span data-ttu-id="718bf-111">앞의 예제와 같이 지역 변수(메서드 범위에서 선언된 변수)에 대해 사용</span><span class="sxs-lookup"><span data-stu-id="718bf-111">On local variables (variables declared at method scope) as shown in the previous example.</span></span>

- <span data-ttu-id="718bf-112">[for](../../language-reference/keywords/for.md) 초기화 문에서 사용</span><span class="sxs-lookup"><span data-stu-id="718bf-112">In a [for](../../language-reference/keywords/for.md) initialization statement.</span></span>

    ```csharp
    for(var x = 1; x < 10; x++)
    ```

- <span data-ttu-id="718bf-113">[foreach](../../language-reference/keywords/foreach-in.md) 초기화 문에서 사용</span><span class="sxs-lookup"><span data-stu-id="718bf-113">In a [foreach](../../language-reference/keywords/foreach-in.md) initialization statement.</span></span>

    ```csharp
    foreach(var item in list){...}
    ```

- <span data-ttu-id="718bf-114">[using](../../language-reference/keywords/using-statement.md) 문에서 사용</span><span class="sxs-lookup"><span data-stu-id="718bf-114">In a [using](../../language-reference/keywords/using-statement.md) statement.</span></span>

    ```csharp
    using (var file = new StreamReader("C:\\myfile.txt")) {...}
    ```

<span data-ttu-id="718bf-115">자세한 내용은 [방법: 쿼리 식에서 암시적 형식 지역 변수 및 배열 사용](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="718bf-115">For more information, see [How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md).</span></span>

## <a name="var-and-anonymous-types"></a><span data-ttu-id="718bf-116">var 및 무명 형식</span><span class="sxs-lookup"><span data-stu-id="718bf-116">var and anonymous types</span></span>

<span data-ttu-id="718bf-117">대부분의 경우 `var` 사용은 선택 사항이며 단지 편리한 구문을 위해 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-117">In many cases the use of `var` is optional and is just a syntactic convenience.</span></span> <span data-ttu-id="718bf-118">그러나 변수가 무명 형식을 사용하여 초기화된 경우 나중에 개체의 속성에 액세스해야 하면 변수를 `var`로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-118">However, when a variable is initialized with an anonymous type you must declare the variable as `var` if you need to access the properties of the object at a later point.</span></span> <span data-ttu-id="718bf-119">이것이 [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] 쿼리 식의 일반적인 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-119">This is a common scenario in [!INCLUDE[vbteclinq](~/includes/vbteclinq-md.md)] query expressions.</span></span> <span data-ttu-id="718bf-120">자세한 내용은 [무명 형식](anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="718bf-120">For more information, see [Anonymous Types](anonymous-types.md).</span></span>

<span data-ttu-id="718bf-121">소스 코드의 관점에서 무명 형식에는 이름이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-121">From the perspective of your source code, an anonymous type has no name.</span></span> <span data-ttu-id="718bf-122">따라서 쿼리 변수가 `var`로 초기화된 경우 반환된 개체 시퀀스의 속성에 액세스하는 유일한 방법은 `var`을 `foreach` 문의 반복 변수 형식으로 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-122">Therefore, if a query variable has been initialized with `var`, then the only way to access the properties in the returned sequence of objects is to use `var` as the type of the iteration variable in the `foreach` statement.</span></span>

[!code-csharp[csProgGuideLINQ#44](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideLINQ/CS/csRef30LangFeatures_2.cs#44)]

## <a name="remarks"></a><span data-ttu-id="718bf-123">설명</span><span class="sxs-lookup"><span data-stu-id="718bf-123">Remarks</span></span>

<span data-ttu-id="718bf-124">암시적 형식 변수 선언에는 다음과 같은 제한 사항이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-124">The following restrictions apply to implicitly-typed variable declarations:</span></span>

- <span data-ttu-id="718bf-125">지역 변수가 동일한 문에서 선언 및 초기화된 경우에만 `var`을 사용할 수 있습니다. 변수를 null이나 메서드 그룹 또는 익명 함수로 초기화할 수는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-125">`var` can only be used when a local variable is declared and initialized in the same statement; the variable cannot be initialized to null, or to a method group or an anonymous function.</span></span>

- <span data-ttu-id="718bf-126">클래스 범위의 필드에는 `var`을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-126">`var` cannot be used on fields at class scope.</span></span>

- <span data-ttu-id="718bf-127">`var`을 사용하여 선언된 변수는 초기화 식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-127">Variables declared by using `var` cannot be used in the initialization expression.</span></span> <span data-ttu-id="718bf-128">즉, `: int i = (i = 20);` 식은 유효하지만 `var i = (i = 20);` 식은 컴파일 시간 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-128">In other words, this expression is legal`: int i = (i = 20);` but this expression produces a compile-time error: `var i = (i = 20);`</span></span>

- <span data-ttu-id="718bf-129">동일한 문에서 여러 개의 암시적 형식 변수를 초기화할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-129">Multiple implicitly-typed variables cannot be initialized in the same statement.</span></span>

- <span data-ttu-id="718bf-130">`var`라는 형식이 범위 내에 있으면 `var` 키워드가 해당 형식 이름으로 확인되고 암시적 형식 지역 변수 선언의 일부로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-130">If a type named `var` is in scope, then the `var` keyword will resolve to that type name and will not be treated as part of an implicitly typed local variable declaration.</span></span>

<span data-ttu-id="718bf-131">`var` 키워드를 사용한 암시적 형식화는 로컬 메서드 범위의 변수에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-131">Implicit typing with the `var` keyword can only be applied to variables at local method scope.</span></span> <span data-ttu-id="718bf-132">C# 컴파일러가 코드를 처리하면서 논리적 패러독스를 만나게 되므로 암시적 형식 지정은 클래스 필드에 사용할 수 없습니다. 컴파일러는 필드 형식을 알아야 하나 할당 식을 분석할 때까지 형식을 결정할 수 없고 형식을 모르면 식을 평가할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-132">Implicit typing is not available for class fields as the C# compiler would encounter a logical paradox as it processed the code: the compiler needs to know the type of the field, but it cannot determine the type until the assignment expression is analyzed, and the expression cannot be evaluated without knowing the type.</span></span> <span data-ttu-id="718bf-133">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="718bf-133">Consider the following code:</span></span>

```csharp
private var bookTitles;
```

<span data-ttu-id="718bf-134">`bookTitles`는 `var` 형식의 클래스 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-134">`bookTitles` is a class field given the type `var`.</span></span> <span data-ttu-id="718bf-135">이 필드는 평가할 식이 없으므로 어떤 형식의 `bookTitles`가 될지 컴파일러가 추론하는 것이 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-135">As the field has no expression to evaluate, it is impossible for the compiler to infer what type `bookTitles` is supposed to be.</span></span> <span data-ttu-id="718bf-136">또한 필드에 식을 추가(로컬 변수에서처럼)하는 것으로는 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-136">In addition, adding an expression to the field (like you would for a local variable) is also insufficient:</span></span>

```csharp
private var bookTitles = new List<string>();
```

<span data-ttu-id="718bf-137">컴파일러에서 코드 컴파일 중 필드를 만나면 연결된 식을 처리하기 전에 각 필드의 형식을 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-137">When the compiler encounters fields during code compilation, it records each field's type before processing any expressions associated with it.</span></span> <span data-ttu-id="718bf-138">컴파일러가 `bookTitles` 구문 분석을 시도하는 동일한 패러독스를 만나면 필드 형식을 알아야 하지만 컴파일러는 일반적으로 식을 분석하여 `var` 형식을 판단합니다. 이는 앞의 형식을 알지 못하면 불가능합니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-138">The compiler encounters the same paradox trying to parse `bookTitles`: it needs to know the type of the field, but the compiler would normally determine `var`'s type by analyzing the expression, which isn't possible without knowing the type beforehand.</span></span>

<span data-ttu-id="718bf-139">`var`은 생성된 쿼리 변수 형식을 정확하게 확인하기 어려운 쿼리 식에서도 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-139">You may find that `var` can also be useful with query expressions in which the exact constructed type of the query variable is difficult to determine.</span></span> <span data-ttu-id="718bf-140">그룹화 및 정렬 작업에서 이러한 경우가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-140">This can occur with grouping and ordering operations.</span></span>

<span data-ttu-id="718bf-141">또한 `var` 키워드는 변수의 특정 형식이 키보드에서 입력하기 번거롭거나, 명확하거나, 코드의 가독성에 도움이 되지 않는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-141">The `var` keyword can also be useful when the specific type of the variable is tedious to type on the keyboard, or is obvious, or does not add to the readability of the code.</span></span> <span data-ttu-id="718bf-142">이런 방식으로 `var`이 유용한 한 가지 예로 그룹 작업에 사용되는 경우 등의 중첩된 제네릭 형식이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-142">One example where `var` is helpful in this manner is with nested generic types such as those used with group operations.</span></span> <span data-ttu-id="718bf-143">다음 쿼리에서 쿼리 변수의 형식은 `IEnumerable<IGrouping<string, Student>>`입니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-143">In the following query, the type of the query variable is `IEnumerable<IGrouping<string, Student>>`.</span></span> <span data-ttu-id="718bf-144">사용자나 코드를 유지 관리해야 하는 다른 사용자가 이 점을 이해하기만 하면 편리하고 간단하도록 암시적 형식을 사용하는 데 문제가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-144">As long as you and others who must maintain your code understand this, there is no problem with using implicit typing for convenience and brevity.</span></span>

[!code-csharp[cscsrefQueryKeywords#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/CsCsrefQueryKeywords/CS/Group.cs#13)]

<span data-ttu-id="718bf-145">그러나 `var`을 사용하면 최소한 다른 개발자가 코드를 이해하기 더 어려워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-145">However, the use of `var` does have at least the potential to make your code more difficult to understand for other developers.</span></span> <span data-ttu-id="718bf-146">이런 이유로, C# 문서에서는 일반적으로 필요한 경우에만 `var`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="718bf-146">For that reason, the C# documentation generally uses `var` only when it is required.</span></span>

## <a name="see-also"></a><span data-ttu-id="718bf-147">참고 항목</span><span class="sxs-lookup"><span data-stu-id="718bf-147">See also</span></span>

- [<span data-ttu-id="718bf-148">C# 참조</span><span class="sxs-lookup"><span data-stu-id="718bf-148">C# Reference</span></span>](../../language-reference/index.md)
- [<span data-ttu-id="718bf-149">암시적으로 형식화된 배열</span><span class="sxs-lookup"><span data-stu-id="718bf-149">Implicitly Typed Arrays</span></span>](../arrays/implicitly-typed-arrays.md)
- [<span data-ttu-id="718bf-150">방법: 쿼리 식에서 암시적 형식 지역 변수 및 배열 사용</span><span class="sxs-lookup"><span data-stu-id="718bf-150">How to: Use Implicitly Typed Local Variables and Arrays in a Query Expression</span></span>](how-to-use-implicitly-typed-local-variables-and-arrays-in-a-query-expression.md)
- [<span data-ttu-id="718bf-151">익명 형식</span><span class="sxs-lookup"><span data-stu-id="718bf-151">Anonymous Types</span></span>](anonymous-types.md)
- [<span data-ttu-id="718bf-152">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="718bf-152">Object and Collection Initializers</span></span>](object-and-collection-initializers.md)
- [<span data-ttu-id="718bf-153">var</span><span class="sxs-lookup"><span data-stu-id="718bf-153">var</span></span>](../../language-reference/keywords/var.md)
- [<span data-ttu-id="718bf-154">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="718bf-154">LINQ in C#</span></span>](../../linq/index.md)
- [<span data-ttu-id="718bf-155">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="718bf-155">LINQ (Language-Integrated Query)</span></span>](../../linq/index.md)
- [<span data-ttu-id="718bf-156">for</span><span class="sxs-lookup"><span data-stu-id="718bf-156">for</span></span>](../../language-reference/keywords/for.md)
- [<span data-ttu-id="718bf-157">foreach, in</span><span class="sxs-lookup"><span data-stu-id="718bf-157">foreach, in</span></span>](../../language-reference/keywords/foreach-in.md)
- [<span data-ttu-id="718bf-158">using 문</span><span class="sxs-lookup"><span data-stu-id="718bf-158">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
