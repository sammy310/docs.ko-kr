---
title: 런타임 상태에 따라 쿼리(C#)
description: LINQ 메서드 호출 또는 해당 메서드에 전달된 식 트리를 다양화하여 코드에서 런타임 상태에 따라 동적으로 쿼리하는 데 사용할 수 있는 다양한 기술을 설명합니다.
ms.date: 02/11/2021
ms.assetid: 52cd44dd-a3ec-441e-b93a-4eca388119c7
ms.openlocfilehash: 0dcf1696ca323ac4823c80c7993fef7873fd8ed5
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433785"
---
# <a name="querying-based-on-runtime-state-c"></a><span data-ttu-id="ebcda-103">런타임 상태에 따라 쿼리(C#)</span><span class="sxs-lookup"><span data-stu-id="ebcda-103">Querying based on runtime state (C#)</span></span>

<span data-ttu-id="ebcda-104">데이터 소스에 대해 <xref:System.Linq.IQueryable> 또는 [IQueryable\<T>](<xref:System.Linq.IQueryable%601>)을 정의하는 코드를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-104">Consider code that defines an <xref:System.Linq.IQueryable> or an [IQueryable\<T>](<xref:System.Linq.IQueryable%601>) against a data source:</span></span>

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Initialize":::

<span data-ttu-id="ebcda-105">해당 코드를 실행할 때마다 똑같은 쿼리가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-105">Every time you run this code, the same exact query will be executed.</span></span> <span data-ttu-id="ebcda-106">코드에서 런타임에 조건에 따라 다른 쿼리를 실행하려고 할 수 있으므로 이 방식은 그다지 유용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-106">This is frequently not very useful, as you may want your code to execute different queries depending on conditions at runtime.</span></span> <span data-ttu-id="ebcda-107">이 문서에서는 런타임 상태에 따라 다른 쿼리를 실행하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-107">This article describes how you can execute a different query based on runtime state.</span></span>

## <a name="iqueryable--iqueryablet-and-expression-trees"></a><span data-ttu-id="ebcda-108">IQueryable/IQueryable\<T> 및 식 트리</span><span class="sxs-lookup"><span data-stu-id="ebcda-108">IQueryable / IQueryable\<T> and expression trees</span></span>

<span data-ttu-id="ebcda-109">기본적으로 <xref:System.Linq.IQueryable>에는 다음 두 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-109">Fundamentally, an <xref:System.Linq.IQueryable> has two components:</span></span>

* <span data-ttu-id="ebcda-110"><xref:System.Linq.IQueryable.Expression> &mdash; 식 트리 형식으로 현재 쿼리 구성 요소의 언어 및 데이터 소스 중립적 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-110"><xref:System.Linq.IQueryable.Expression>&mdash;a language- and datasource-agnostic representation of the current query's components, in the form of an expression tree.</span></span>
* <span data-ttu-id="ebcda-111"><xref:System.Linq.IQueryable.Provider> &mdash; 현재 쿼리를 값 또는 값 세트로 구체화하는 방법을 인식하는 LINQ 공급자의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-111"><xref:System.Linq.IQueryable.Provider>&mdash;an instance of a LINQ provider, which knows how to materialize the current query into a value or set of values.</span></span>

<span data-ttu-id="ebcda-112">동적 쿼리 컨텍스트에서 공급자는 일반적으로 동일하게 유지됩니다. 쿼리의 식 트리는 쿼리별로 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-112">In the context of dynamic querying, the provider will usually remain the same; the expression tree of the query will differ from query to query.</span></span>

<span data-ttu-id="ebcda-113">식 트리는 변경할 수 없습니다. 다른 식 트리 &mdash;및 이에 따라 다른 쿼리&mdash;가 필요한 경우에는 기존 식 트리를 새 식 트리로 변환하고 이에 따라 새 <xref:System.Linq.IQueryable>로 변환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-113">Expression trees are immutable; if you want a different expression tree&mdash;and thus a different query&mdash;you'll need to translate the existing expression tree to a new one, and thus to a new <xref:System.Linq.IQueryable>.</span></span>

<span data-ttu-id="ebcda-114">다음 섹션에서는 런타임 상태에 대한 응답으로 다르게 쿼리하는 특정 기술을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-114">The following sections describe specific techniques for querying differently in response to runtime state:</span></span>

- <span data-ttu-id="ebcda-115">식 트리 내에서 런타임 상태 사용</span><span class="sxs-lookup"><span data-stu-id="ebcda-115">Use runtime state from within the expression tree</span></span>
- <span data-ttu-id="ebcda-116">추가 LINQ 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="ebcda-116">Call additional LINQ methods</span></span>
- <span data-ttu-id="ebcda-117">LINQ 메서드에 전달된 식 트리 다양화</span><span class="sxs-lookup"><span data-stu-id="ebcda-117">Vary the expression tree passed into the LINQ methods</span></span>
- <span data-ttu-id="ebcda-118"><xref:System.Linq.Expressions.Expression>에서 팩터리 메서드를 사용하여 [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) 식 트리 생성</span><span class="sxs-lookup"><span data-stu-id="ebcda-118">Construct an [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) expression tree using the factory methods at <xref:System.Linq.Expressions.Expression></span></span>
- <span data-ttu-id="ebcda-119"><xref:System.Linq.IQueryable>의 식 트리에 메서드 호출 노드 추가</span><span class="sxs-lookup"><span data-stu-id="ebcda-119">Adding method call nodes to an <xref:System.Linq.IQueryable>'s expression tree</span></span>
- <span data-ttu-id="ebcda-120">문자열을 생성하고 [동적 LINQ 라이브러리](https://dynamic-linq.net/) 사용</span><span class="sxs-lookup"><span data-stu-id="ebcda-120">Construct strings, and use the [Dynamic LINQ library](https://dynamic-linq.net/)</span></span>

## <a name="use-runtime-state-from-within-the-expression-tree"></a><span data-ttu-id="ebcda-121">식 트리 내에서 런타임 상태 사용</span><span class="sxs-lookup"><span data-stu-id="ebcda-121">Use runtime state from within the expression tree</span></span>

<span data-ttu-id="ebcda-122">LINQ 공급자가 지원하는 경우 동적으로 쿼리하는 가장 간단한 방법은 다음 코드 예제의 `length` 같이 둘러싸인 변수를 통해 쿼리에서 직접 런타임 상태를 참조하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-122">Assuming the LINQ provider supports it, the simplest way to query dynamically is to reference the runtime state directly in the query via a closed-over variable, such as `length` in the following code example:</span></span>

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Runtime_state_from_within_expression_tree":::

<span data-ttu-id="ebcda-123">내부 식 트리(및 이에 따라 쿼리)는 수정되지 않았습니다. `length` 값이 변경되었기 때문에 쿼리는 다른 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-123">The internal expression tree&mdash;and thus the query&mdash;haven't been modified; the query returns different values only because the value of `length` has been changed.</span></span>

## <a name="call-additional-linq-methods"></a><span data-ttu-id="ebcda-124">추가 LINQ 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="ebcda-124">Call additional LINQ methods</span></span>

<span data-ttu-id="ebcda-125">일반적으로 <xref:System.Linq.Queryable>의 [기본 제공 LINQ 메서드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs)는 다음 두 단계를 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-125">Generally, the [built-in LINQ methods](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) at <xref:System.Linq.Queryable> perform two steps:</span></span>

* <span data-ttu-id="ebcda-126">메서드 호출을 나타내는 <xref:System.Linq.Expressions.MethodCallExpression>으로 현재 식 트리를 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-126">Wrap the current expression tree in a <xref:System.Linq.Expressions.MethodCallExpression> representing the method call.</span></span>
* <span data-ttu-id="ebcda-127">래핑된 식 트리를 공급자에게 다시 전달하여 공급자의 <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> 메서드를 통해 값을 반환하거나 <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType> 메서드를 통해 변환된 쿼리 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-127">Pass the wrapped expression tree back to the provider, either to return a value via the provider's <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> method; or to return a translated query object via the <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="ebcda-128">원래 쿼리를 [IQueryable\<T>](xref:System.Linq.IQueryable%601) 반환 메서드의 결과로 바꿔서 새 쿼리를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-128">You can replace the original query with the result of an [IQueryable\<T>](xref:System.Linq.IQueryable%601)-returning method, to get a new query.</span></span> <span data-ttu-id="ebcda-129">다음 예제와 같이 런타임 상태에 따라 해당 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-129">You can do this based on runtime state, as in the following example:</span></span>

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Added_method_calls":::

## <a name="vary-the-expression-tree-passed-into-the-linq-methods"></a><span data-ttu-id="ebcda-130">LINQ 메서드에 전달된 식 트리 다양화</span><span class="sxs-lookup"><span data-stu-id="ebcda-130">Vary the expression tree passed into the LINQ methods</span></span>

<span data-ttu-id="ebcda-131">런타임 상태에 따라 다양한 식을 LINQ 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-131">You can pass in different expressions to the LINQ methods, depending on runtime state:</span></span>

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Varying_expressions":::

<span data-ttu-id="ebcda-132">[LinqKit](http://www.albahari.com/nutshell/linqkit.aspx)의 [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx)와 같은 타사 라이브러리를 사용하여 다양한 하위 식을 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-132">You might also want to compose the various sub-expressions using a third-party library such as [LinqKit](http://www.albahari.com/nutshell/linqkit.aspx)'s [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx):</span></span>

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Compose_expressions":::

## <a name="construct-expression-trees-and-queries-using-factory-methods"></a><span data-ttu-id="ebcda-133">팩터리 메서드를 사용하여 식 트리 및 쿼리 생성</span><span class="sxs-lookup"><span data-stu-id="ebcda-133">Construct expression trees and queries using factory methods</span></span>

<span data-ttu-id="ebcda-134">지금까지 모든 예제에서 컴파일 시간의 요소 형식 `string` 및 이에 따른 쿼리 형식 `IQueryable<string>`을 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-134">In all the examples up to this point, we've known the element type at compile time&mdash;`string`&mdash;and thus the type of the query&mdash;`IQueryable<string>`.</span></span> <span data-ttu-id="ebcda-135">요소 형식의 쿼리에 구성 요소를 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-135">You may need to add components to a query of any element type.</span></span> <span data-ttu-id="ebcda-136">요소 형식에 따라 다른 구성 요소를 추가해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-136">You may need to add different components, depending on the element type.</span></span> <span data-ttu-id="ebcda-137"><xref:System.Linq.Expressions.Expression?displayProperty=fullName>에서 팩터리 메서드를 사용하여 처음부터 식 트리를 만들 수 있으므로 특정 요소 형식에 맞게 식을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-137">You can create expression trees from the ground up, using the factory methods at <xref:System.Linq.Expressions.Expression?displayProperty=fullName>, and thus tailor the expression to a specific element type.</span></span>

### <a name="constructing-an-expressiontdelegate"></a><span data-ttu-id="ebcda-138">[Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) 생성</span><span class="sxs-lookup"><span data-stu-id="ebcda-138">Constructing an [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601)</span></span>

<span data-ttu-id="ebcda-139">LINQ 메서드 중 하나에 전달할 식을 생성하는 경우 실제로는 [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601)의 인스턴스를 생성하는 것입니다. 여기서 `TDelegate`는 `Func<string, bool>`, `Action` 또는 사용자 지정 대리자 형식과 같은 대리자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-139">When you construct an expression to pass into one of the LINQ methods, you're actually constructing an instance of [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601), where `TDelegate` is some delegate type such as `Func<string, bool>`, `Action`, or a custom delegate type.</span></span>

<span data-ttu-id="ebcda-140">[Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601)는 다음과 같은 전체 람다 식을 나타내는 <xref:System.Linq.Expressions.LambdaExpression>에서 상속됩니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-140">[Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) inherits from <xref:System.Linq.Expressions.LambdaExpression>, which represents a complete lambda expression like the following:</span></span>

```csharp
Expression<Func<string, bool>> expr = x => x.StartsWith("a");
```

<span data-ttu-id="ebcda-141"><xref:System.Linq.Expressions.LambdaExpression>에는 다음 두 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-141">A <xref:System.Linq.Expressions.LambdaExpression> has two components:</span></span>

* <span data-ttu-id="ebcda-142"><xref:System.Linq.Expressions.LambdaExpression.Parameters> 속성으로 표시되는 매개 변수 목록 `(string x)`</span><span class="sxs-lookup"><span data-stu-id="ebcda-142">a parameter list&mdash;`(string x)`&mdash;represented by the <xref:System.Linq.Expressions.LambdaExpression.Parameters> property</span></span>
* <span data-ttu-id="ebcda-143"><xref:System.Linq.Expressions.LambdaExpression.Body> 속성으로 표시되는 본문 `x.StartsWith("a")`</span><span class="sxs-lookup"><span data-stu-id="ebcda-143">a body&mdash;`x.StartsWith("a")`&mdash;represented by the <xref:System.Linq.Expressions.LambdaExpression.Body> property.</span></span>

<span data-ttu-id="ebcda-144">[Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601)를 생성하는 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-144">The basic steps in constructing an [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) are as follows:</span></span>

* <span data-ttu-id="ebcda-145"><xref:System.Linq.Expressions.Expression.Parameter%2A> 팩터리 메서드를 사용하여 람다 식에서 각 매개 변수(있는 경우)에 대해 <xref:System.Linq.Expressions.ParameterExpression> 개체를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-145">Define <xref:System.Linq.Expressions.ParameterExpression> objects for each of the parameters (if any) in the lambda expression, using the <xref:System.Linq.Expressions.Expression.Parameter%2A> factory method.</span></span>

    ```csharp
    ParameterExpression x = Parameter(typeof(string), "x");
    ```

* <span data-ttu-id="ebcda-146">정의한 <xref:System.Linq.Expressions.ParameterExpression>을 사용하여 <xref:System.Linq.Expressions.LambdaExpression> 본문을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-146">Construct the body of your <xref:System.Linq.Expressions.LambdaExpression>, using the <xref:System.Linq.Expressions.ParameterExpression> you've defined.</span></span> <span data-ttu-id="ebcda-147">예를 들어 `x.StartsWith("a")`를 나타내는 식은 다음과 같이 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-147">For instance, an expression representing `x.StartsWith("a")` could be constructed like this:</span></span>

    ```csharp
    Expression body = Call(
        x,
        typeof(string).GetMethod("StartsWith", new [] {typeof(string)}),
        Constant("a")
    );
    ```

* <span data-ttu-id="ebcda-148">적절한 <xref:System.Linq.Expressions.Expression.Lambda%2A> 팩터리 메서드 오버로드를 사용하여 컴파일 시간 형식의 [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601)로 매개 변수와 본문을 래핑합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-148">Wrap the parameters and body in a compile-time-typed [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601), using the appropriate <xref:System.Linq.Expressions.Expression.Lambda%2A> factory method overload:</span></span>

    ```csharp
    Expression<Func<string, bool>> expr = Lambda<Func<string, bool>>(body, prm);
    ```

<span data-ttu-id="ebcda-149">다음 섹션에서는 LINQ 메서드에 전달할 [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601)를 생성하려고 하는 시나리오를 설명하고 팩터리 메서드를 사용하여 해당 작업을 수행하는 방법의 전체 예제를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-149">The following sections describe a scenario in which you might want to construct an [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) to pass into a LINQ method, and provide a complete example of how to do so using the factory methods.</span></span>

### <a name="scenario"></a><span data-ttu-id="ebcda-150">시나리오</span><span class="sxs-lookup"><span data-stu-id="ebcda-150">Scenario</span></span>

<span data-ttu-id="ebcda-151">여러 엔터티 형식이 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-151">Let's say you have multiple entity types:</span></span>

```csharp
record Person(string LastName, string FirstName, DateTime DateOfBirth);
record Car(string Model, int Year);
```

<span data-ttu-id="ebcda-152">해당 엔터티 형식에 대해 해당 `string` 필드 중 하나에 지정된 텍스트가 포함된 엔터티만 필터링하고 반환하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-152">For any of these entity types, you want to filter and return only those entities that have a given text inside one of their `string` fields.</span></span> <span data-ttu-id="ebcda-153">`Person`의 경우 `FirstName` 및 `LastName` 속성을 검색하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-153">For `Person`, you'd want to search the `FirstName` and `LastName` properties:</span></span>

```csharp
string term = /* ... */;
var personsQry = new List<Person>()
    .AsQueryable()
    .Where(x => x.FirstName.Contains(term) || x.LastName.Contains(term));
```

<span data-ttu-id="ebcda-154">그러나 `Car`의 경우 `Model` 속성만 검색하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-154">but for `Car`, you'd want to search only the `Model` property:</span></span>

```csharp
string term = /* ... */;
var carsQry = new List<Car>()
    .AsQueryable()
    .Where(x => x.Model.Contains(term));
```

<span data-ttu-id="ebcda-155">`IQueryable<Person>` 및 `IQueryable<Car>`에 대해 하나씩 사용자 지정 함수를 작성할 수 있지만, 다음 함수는 특정 요소 형식과 관계없이 이 필터링을 기존 쿼리에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-155">While you could write one custom function for `IQueryable<Person>` and another for `IQueryable<Car>`, the following function adds this filtering to any existing query, irrespective of the specific element type.</span></span>

### <a name="example"></a><span data-ttu-id="ebcda-156">예제</span><span class="sxs-lookup"><span data-stu-id="ebcda-156">Example</span></span>

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Factory_methods_expression_of_tdelegate":::

<span data-ttu-id="ebcda-157">`TextFilter` 함수는 <xref:System.Linq.IQueryable>만이 아니라 [IQueryable\<T>](xref:System.Linq.IQueryable%601)를 사용하고 반환하기 때문에 텍스트 필터 뒤에 컴파일 시간 형식의 쿼리 요소를 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-157">Because the `TextFilter` function takes and returns an [IQueryable\<T>](xref:System.Linq.IQueryable%601) (and not just an <xref:System.Linq.IQueryable>), you can add further compile-time-typed query elements after the text filter.</span></span>

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Factory_methods_expression_of_tdelegate_usage":::

## <a name="adding-method-call-nodes-to-the-xrefsystemlinqiqueryables-expression-tree"></a><span data-ttu-id="ebcda-158"><xref:System.Linq.IQueryable>의 식 트리에 메서드 호출 노드 추가</span><span class="sxs-lookup"><span data-stu-id="ebcda-158">Adding method call nodes to the <xref:System.Linq.IQueryable>'s expression tree</span></span>

<span data-ttu-id="ebcda-159">[IQueryable\<T>](xref:System.Linq.IQueryable%601) 대신 <xref:System.Linq.IQueryable>이 있는 경우 제네릭 LINQ 메서드를 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-159">If you have an <xref:System.Linq.IQueryable> instead of an [IQueryable\<T>](xref:System.Linq.IQueryable%601), you can't directly call the generic LINQ methods.</span></span> <span data-ttu-id="ebcda-160">한 가지 대안은 위와 같이 내부 식 트리를 빌드하고 리플렉션을 사용하여 식 트리를 전달하는 동안 적절한 LINQ 메서드를 호출하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-160">One alternative is to build the inner expression tree as above, and use reflection to invoke the appropriate LINQ method while passing in the expression tree.</span></span>

<span data-ttu-id="ebcda-161">LINQ 메서드 호출을 나타내는 <xref:System.Linq.Expressions.MethodCallExpression>으로 전체 트리를 래핑하여 LINQ 메서드의 기능을 복제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-161">You could also duplicate the LINQ method's functionality, by wrapping the entire tree in a <xref:System.Linq.Expressions.MethodCallExpression> which represents a call to the LINQ method:</span></span>

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Factory_methods_lambdaexpression":::

<span data-ttu-id="ebcda-162">이 경우 컴파일 시간 `T` 제네릭 자리 표시자가 없으므로 컴파일 시간 형식 정보가 필요하지 않고 [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601) 대신 <xref:System.Linq.Expressions.LambdaExpression>을 생성하는 <xref:System.Linq.Expressions.Expression.Lambda%2A> 오버로드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-162">Note that in this case you don't have a compile-time `T` generic placeholder, so you'll use the <xref:System.Linq.Expressions.Expression.Lambda%2A> overload which doesn't require compile-time type information, and which produces a <xref:System.Linq.Expressions.LambdaExpression> instead of an an [Expression\<TDelegate>](xref:System.Linq.Expressions.Expression%601).</span></span>

## <a name="the-dynamic-linq-library"></a><span data-ttu-id="ebcda-163">동적 LINQ 라이브러리</span><span class="sxs-lookup"><span data-stu-id="ebcda-163">The Dynamic LINQ library</span></span>

<span data-ttu-id="ebcda-164">팩터리 메서드를 사용하여 식 트리를 생성하는 작업은 비교적 복잡하며, 문자열을 작성하는 작업이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-164">Constructing expression trees using factory methods is relatively complex; it is easier to compose strings.</span></span> <span data-ttu-id="ebcda-165">[동적 LINQ 라이브러리](https://dynamic-linq.net/)는 <xref:System.Linq.Queryable>에서 표준 LINQ 메서드에 해당하며 식 트리 대신 [특수 구문](https://dynamic-linq.net/expression-language)에서 문자열을 허용하는 <xref:System.Linq.IQueryable>에 확장 메서드 세트를 공개합니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-165">The [Dynamic LINQ library](https://dynamic-linq.net/) exposes a set of extension methods on <xref:System.Linq.IQueryable> corresponding to the standard LINQ methods at <xref:System.Linq.Queryable>, and which accept strings in a [special syntax](https://dynamic-linq.net/expression-language) instead of expression trees.</span></span> <span data-ttu-id="ebcda-166">라이브러리는 문자열에서 적절한 식 트리를 생성하며 결과로 변환된 <xref:System.Linq.IQueryable>을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-166">The library generates the appropriate expression tree from the string, and can return the resultant translated <xref:System.Linq.IQueryable>.</span></span>

<span data-ttu-id="ebcda-167">예를 들어 이전 예제를 다음과 같이 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ebcda-167">For instance, the previous example could be rewritten as follows:</span></span>

:::code language="csharp" source="../../../../../samples/snippets/csharp/programming-guide/dynamic-linq-expression-trees/Program.cs" id="Dynamic_linq":::

## <a name="see-also"></a><span data-ttu-id="ebcda-168">참조</span><span class="sxs-lookup"><span data-stu-id="ebcda-168">See also</span></span>

- [<span data-ttu-id="ebcda-169">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="ebcda-169">Expression Trees (C#)</span></span>](./index.md)
- [<span data-ttu-id="ebcda-170">식 트리 실행 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="ebcda-170">How to execute expression trees (C#)</span></span>](./how-to-execute-expression-trees.md)
- [<span data-ttu-id="ebcda-171">런타임에 동적으로 조건자 필터 지정</span><span class="sxs-lookup"><span data-stu-id="ebcda-171">Dynamically specify predicate filters at runtime</span></span>](../../../linq/dynamically-specify-predicate-filters-at-runtime.md)
