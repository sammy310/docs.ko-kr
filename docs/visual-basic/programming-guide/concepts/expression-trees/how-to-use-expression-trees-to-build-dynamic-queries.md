---
title: 런타임 상태를 기준으로 쿼리 (Visual Basic)
description: LINQ 메서드 호출 또는 이러한 메서드에 전달 된 식 트리를 변경 하 여 코드에서 런타임 상태에 따라 동적으로 쿼리 하는 데 사용할 수 있는 다양 한 기술에 대해 설명 합니다.
ms.date: 02/14/2021
ms.assetid: 16278787-7532-4b65-98b2-7a412406c4ee
ms.openlocfilehash: c9f57950b2c26c0cca798ab632da90bf9f6c519a
ms.sourcegitcommit: f0fc5db7bcbf212e46933e9cf2d555bb82666141
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/17/2021
ms.locfileid: "100584841"
---
# <a name="querying-based-on-runtime-state-visual-basic"></a><span data-ttu-id="a61c0-103">런타임 상태를 기준으로 쿼리 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a61c0-103">Querying based on runtime state (Visual Basic)</span></span>

<span data-ttu-id="a61c0-104"><xref:System.Linq.IQueryable>데이터 원본에 대해 또는 [IQueryable (Of T)](<xref:System.Linq.IQueryable%601>) 을 정의 하는 코드를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-104">Consider code that defines an <xref:System.Linq.IQueryable> or an [IQueryable(Of T)](<xref:System.Linq.IQueryable%601>) against a data source:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Initialize":::

<span data-ttu-id="a61c0-105">이 코드를 실행할 때마다 동일한 정확한 쿼리가 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-105">Every time you run this code, the same exact query will be executed.</span></span> <span data-ttu-id="a61c0-106">이는 런타임에 조건에 따라 코드에서 다른 쿼리를 실행 하려는 경우에는 자주 유용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-106">This is frequently not very useful, as you may want your code to execute different queries depending on conditions at runtime.</span></span> <span data-ttu-id="a61c0-107">이 문서에서는 런타임 상태에 따라 다른 쿼리를 실행 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-107">This article describes how you can execute a different query based on runtime state.</span></span>

## <a name="iqueryable--iqueryableof-t-and-expression-trees"></a><span data-ttu-id="a61c0-108">IQueryable/IQueryable (Of T) 및 식 트리</span><span class="sxs-lookup"><span data-stu-id="a61c0-108">IQueryable / IQueryable(Of T) and expression trees</span></span>

<span data-ttu-id="a61c0-109">기본적으로에는 <xref:System.Linq.IQueryable> 다음과 같은 두 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-109">Fundamentally, an <xref:System.Linq.IQueryable> has two components:</span></span>

* <span data-ttu-id="a61c0-110"><xref:System.Linq.IQueryable.Expression>&mdash;식 트리 형식의 현재 쿼리 구성 요소에 대 한 언어 및 datasource를 구분 하지 않는 표현입니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-110"><xref:System.Linq.IQueryable.Expression>&mdash;a language- and datasource-agnostic representation of the current query's components, in the form of an expression tree.</span></span>
* <span data-ttu-id="a61c0-111"><xref:System.Linq.IQueryable.Provider>&mdash;현재 쿼리를 값 또는 값 집합으로 구체화 하는 방법을 알고 있는 LINQ 공급자의 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-111"><xref:System.Linq.IQueryable.Provider>&mdash;an instance of a LINQ provider, which knows how to materialize the current query into a value or set of values.</span></span>

<span data-ttu-id="a61c0-112">동적 쿼리 컨텍스트에서 공급자는 일반적으로 동일 하 게 유지 됩니다. 쿼리의 식 트리가 쿼리와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-112">In the context of dynamic querying, the provider will usually remain the same; the expression tree of the query will differ from query to query.</span></span>

<span data-ttu-id="a61c0-113">식 트리는 변경할 수 없습니다. 다른 식 트리가 필요 &mdash; 하므로 다른 쿼리를 수행 하려면 &mdash; 기존 식 트리를 새로운 식 트리로 변환 해야 <xref:System.Linq.IQueryable> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-113">Expression trees are immutable; if you want a different expression tree&mdash;and thus a different query&mdash;you'll need to translate the existing expression tree to a new one, and thus to a new <xref:System.Linq.IQueryable>.</span></span>

<span data-ttu-id="a61c0-114">다음 섹션에서는 런타임 상태에 대 한 응답으로 다르게 쿼리 하는 특정 기술에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-114">The following sections describe specific techniques for querying differently in response to runtime state:</span></span>

- <span data-ttu-id="a61c0-115">식 트리 내에서 런타임 상태를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-115">Use runtime state from within the expression tree</span></span>
- <span data-ttu-id="a61c0-116">추가 LINQ 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="a61c0-116">Call additional LINQ methods</span></span>
- <span data-ttu-id="a61c0-117">LINQ 메서드에 전달 된 식 트리를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-117">Vary the expression tree passed into the LINQ methods</span></span>
- <span data-ttu-id="a61c0-118">에서 팩터리 메서드를 사용 하 여 [식 (TDelegate의)](xref:System.Linq.Expressions.Expression%601) 식 트리를 생성 합니다. <xref:System.Linq.Expressions.Expression></span><span class="sxs-lookup"><span data-stu-id="a61c0-118">Construct an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601) expression tree using the factory methods at <xref:System.Linq.Expressions.Expression></span></span>
- <span data-ttu-id="a61c0-119">의 식 트리에 메서드 호출 노드를 추가 합니다. <xref:System.Linq.IQueryable></span><span class="sxs-lookup"><span data-stu-id="a61c0-119">Add method call nodes to an <xref:System.Linq.IQueryable>'s expression tree</span></span>
- <span data-ttu-id="a61c0-120">문자열 생성 및 [동적 LINQ 라이브러리](https://dynamic-linq.net/) 사용</span><span class="sxs-lookup"><span data-stu-id="a61c0-120">Construct strings, and use the [Dynamic LINQ library](https://dynamic-linq.net/)</span></span>

## <a name="use-runtime-state-from-within-the-expression-tree"></a><span data-ttu-id="a61c0-121">식 트리 내에서 런타임 상태를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-121">Use runtime state from within the expression tree</span></span>

<span data-ttu-id="a61c0-122">LINQ 공급자가 지 원하는 것으로 가정 하 여 동적으로 쿼리 하는 가장 간단한 방법은 다음 코드 예제와 같이 닫혀 있는 변수를 통해 쿼리에서 직접 런타임 상태를 참조 하는 것입니다 `length` .</span><span class="sxs-lookup"><span data-stu-id="a61c0-122">Assuming the LINQ provider supports it, the simplest way to query dynamically is to reference the runtime state directly in the query via a closed-over variable, such as `length` in the following code example:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Runtime_state_from_within_expression_tree":::

<span data-ttu-id="a61c0-123">내부 식 트리 &mdash; 이므로 쿼리가 &mdash; 수정 되지 않았습니다 .의 값이 변경 되었기 때문에 쿼리는 다른 값만 반환 합니다 `length` .</span><span class="sxs-lookup"><span data-stu-id="a61c0-123">The internal expression tree&mdash;and thus the query&mdash;haven't been modified; the query returns different values only because the value of `length` has been changed.</span></span>

## <a name="call-additional-linq-methods"></a><span data-ttu-id="a61c0-124">추가 LINQ 메서드 호출</span><span class="sxs-lookup"><span data-stu-id="a61c0-124">Call additional LINQ methods</span></span>

<span data-ttu-id="a61c0-125">일반적으로에서 [기본 제공 되는 LINQ 메서드](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) 는 <xref:System.Linq.Queryable> 다음 두 단계를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-125">Generally, the [built-in LINQ methods](https://github.com/dotnet/runtime/blob/master/src/libraries/System.Linq.Queryable/src/System/Linq/Queryable.cs) at <xref:System.Linq.Queryable> perform two steps:</span></span>

* <span data-ttu-id="a61c0-126">메서드 호출을 나타내는에서 현재 식 트리를 래핑합니다 <xref:System.Linq.Expressions.MethodCallExpression> .</span><span class="sxs-lookup"><span data-stu-id="a61c0-126">Wrap the current expression tree in a <xref:System.Linq.Expressions.MethodCallExpression> representing the method call.</span></span>
* <span data-ttu-id="a61c0-127">래핑된 식 트리를 공급자에 게 다시 전달 하 여 공급자의 메서드를 통해 값을 반환 <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> 하거나, 메서드를 통해 번역 된 쿼리 개체를 반환 <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-127">Pass the wrapped expression tree back to the provider, either to return a value via the provider's <xref:System.Linq.IQueryProvider.Execute%2A?displayProperty=nameWithType> method; or to return a translated query object via the <xref:System.Linq.IQueryProvider.CreateQuery%2A?displayProperty=nameWithType> method.</span></span>

<span data-ttu-id="a61c0-128">원래 쿼리를 [IQueryable (Of T)](xref:System.Linq.IQueryable%601)반환 메서드의 결과로 바꿔서 새 쿼리를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-128">You can replace the original query with the result of an [IQueryable(Of T)](xref:System.Linq.IQueryable%601)-returning method, to get a new query.</span></span> <span data-ttu-id="a61c0-129">다음 예제와 같이 런타임 상태를 기준으로이 작업을 조건부로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-129">You can do this conditionally based on runtime state, as in the following example:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Added_method_calls":::

## <a name="vary-the-expression-tree-passed-into-the-linq-methods"></a><span data-ttu-id="a61c0-130">LINQ 메서드에 전달 된 식 트리를 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-130">Vary the expression tree passed into the LINQ methods</span></span>

<span data-ttu-id="a61c0-131">런타임 상태에 따라 다양 한 식을 LINQ 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-131">You can pass in different expressions to the LINQ methods, depending on runtime state:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Varying_expressions":::

<span data-ttu-id="a61c0-132">[LinqKit](http://www.albahari.com/nutshell/linqkit.aspx)의 [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx)와 같은 타사 라이브러리를 사용 하 여 다양 한 하위 식을 작성 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-132">You might also want to compose the various sub-expressions using a third-party library such as [LinqKit](http://www.albahari.com/nutshell/linqkit.aspx)'s [PredicateBuilder](http://www.albahari.com/nutshell/predicatebuilder.aspx):</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compose_expression":::

## <a name="construct-expression-trees-and-queries-using-factory-methods"></a><span data-ttu-id="a61c0-133">팩터리 메서드를 사용 하 여 식 트리 및 쿼리 생성</span><span class="sxs-lookup"><span data-stu-id="a61c0-133">Construct expression trees and queries using factory methods</span></span>

<span data-ttu-id="a61c0-134">이 시점까지 모든 예제에서 컴파일 시간에 요소 형식을 알 수 &mdash; `String` &mdash; 있으므로 쿼리 형식이 알려졌습니다 &mdash; `IQueryable(Of String)` .</span><span class="sxs-lookup"><span data-stu-id="a61c0-134">In all the examples up to this point, we've known the element type at compile time&mdash;`String`&mdash;and thus the type of the query&mdash;`IQueryable(Of String)`.</span></span> <span data-ttu-id="a61c0-135">요소 형식의 쿼리에 구성 요소를 추가 하거나 요소 형식에 따라 다른 구성 요소를 추가 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-135">You may need to add components to a query of any element type, or to add different components depending on the element type.</span></span> <span data-ttu-id="a61c0-136">에서 팩터리 메서드를 사용 하 여 식 트리를 처음부터 만들 수 <xref:System.Linq.Expressions.Expression?displayProperty=fullName> 있으므로 런타임에 식을 특정 요소 형식으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-136">You can create expression trees from the ground up, using the factory methods at <xref:System.Linq.Expressions.Expression?displayProperty=fullName>, and thus tailor the expression at runtime to a specific element type.</span></span>

### <a name="constructing-an-expressionof-tdelegate"></a><span data-ttu-id="a61c0-137">식 생성 [(TDelegate의 경우)](xref:System.Linq.Expressions.Expression%601)</span><span class="sxs-lookup"><span data-stu-id="a61c0-137">Constructing an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601)</span></span>

<span data-ttu-id="a61c0-138">LINQ 메서드 중 하나에 전달할 식을 생성할 때는 실제로 [식](xref:System.Linq.Expressions.Expression%601)의 인스턴스를 구성 하는 `TDelegate` 것입니다. 여기서는 `Func(Of String, Boolean)` , `Action` 또는 사용자 지정 대리자 형식과 같은 대리자 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-138">When you construct an expression to pass into one of the LINQ methods, you're actually constructing an instance of [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601), where `TDelegate` is some delegate type such as `Func(Of String, Boolean)`, `Action`, or a custom delegate type.</span></span>

<span data-ttu-id="a61c0-139">[식 (TDelegate))](xref:System.Linq.Expressions.Expression%601) 는 <xref:System.Linq.Expressions.LambdaExpression> 다음과 같은 전체 람다 식을 나타내는에서 상속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-139">[Expression(Of TDelegate))](xref:System.Linq.Expressions.Expression%601) inherits from <xref:System.Linq.Expressions.LambdaExpression>, which represents a complete lambda expression like the following:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Compiler_generated":::

<span data-ttu-id="a61c0-140">에는 <xref:System.Linq.Expressions.LambdaExpression> 다음 두 가지 구성 요소가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-140">A <xref:System.Linq.Expressions.LambdaExpression> has two components:</span></span>

* <span data-ttu-id="a61c0-141">&mdash; `(x As String)` &mdash; 속성이 나타내는 매개 변수 목록 <xref:System.Linq.Expressions.LambdaExpression.Parameters></span><span class="sxs-lookup"><span data-stu-id="a61c0-141">a parameter list&mdash;`(x As String)`&mdash;represented by the <xref:System.Linq.Expressions.LambdaExpression.Parameters> property</span></span>
* <span data-ttu-id="a61c0-142">&mdash; `x.StartsWith("a")` &mdash; 속성이 나타내는 본문 <xref:System.Linq.Expressions.LambdaExpression.Body> 입니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-142">a body&mdash;`x.StartsWith("a")`&mdash;represented by the <xref:System.Linq.Expressions.LambdaExpression.Body> property.</span></span>

<span data-ttu-id="a61c0-143">[식 (TDelegate의 경우)](xref:System.Linq.Expressions.Expression%601) 을 생성 하는 기본 단계는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-143">The basic steps in constructing an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601) are as follows:</span></span>

* <span data-ttu-id="a61c0-144"><xref:System.Linq.Expressions.ParameterExpression>팩터리 메서드를 사용 하 여 람다 식에서 각 매개 변수 (있는 경우)에 대 한 개체를 정의 <xref:System.Linq.Expressions.Expression.Parameter%2A> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-144">Define <xref:System.Linq.Expressions.ParameterExpression> objects for each of the parameters (if any) in the lambda expression, using the <xref:System.Linq.Expressions.Expression.Parameter%2A> factory method.</span></span>

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_parameter":::

* <span data-ttu-id="a61c0-145">사용자가 <xref:System.Linq.Expressions.LambdaExpression> 정의한 및의 팩터리 메서드를 사용 하 여의 본문을 생성 <xref:System.Linq.Expressions.ParameterExpression> <xref:System.Linq.Expressions.Expression> 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-145">Construct the body of your <xref:System.Linq.Expressions.LambdaExpression>, using the <xref:System.Linq.Expressions.ParameterExpression>(s) you've defined, and the factory methods at <xref:System.Linq.Expressions.Expression>.</span></span> <span data-ttu-id="a61c0-146">예를 들어를 나타내는 식은 `x.StartsWith("a")` 다음과 같이 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-146">For instance, an expression representing `x.StartsWith("a")` could be constructed like this:</span></span>

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_body":::

* <span data-ttu-id="a61c0-147">적절 한 팩터리 메서드 오버 로드를 사용 하 여 매개 변수 및 본문을 컴파일 시간 형식화 [식 (TDelegate)](xref:System.Linq.Expressions.Expression%601)로 래핑합니다 <xref:System.Linq.Expressions.Expression.Lambda%2A> .</span><span class="sxs-lookup"><span data-stu-id="a61c0-147">Wrap the parameters and body in a compile-time-typed [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601), using the appropriate <xref:System.Linq.Expressions.Expression.Lambda%2A> factory method overload:</span></span>

    :::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_method_lambda":::

<span data-ttu-id="a61c0-148">다음 섹션에서는 LINQ 메서드에 전달할 [식 (TDelegate)](xref:System.Linq.Expressions.Expression%601) 을 생성 하 고 팩터리 메서드를 사용 하 여이 작업을 수행 하는 방법의 전체 예제를 제공 하는 시나리오에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-148">The following sections describe a scenario in which you might want to construct an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601) to pass into a LINQ method, and provide a complete example of how to do so using the factory methods.</span></span>

### <a name="scenario"></a><span data-ttu-id="a61c0-149">시나리오</span><span class="sxs-lookup"><span data-stu-id="a61c0-149">Scenario</span></span>

<span data-ttu-id="a61c0-150">여러 엔터티 형식이 있다고 가정해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-150">Let's say you have multiple entity types:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Entities.vb":::

<span data-ttu-id="a61c0-151">이러한 엔터티 형식에 대해 필드 중 하나에 지정 된 텍스트가 있는 엔터티만 필터링 하 고 반환 하려고 합니다 `string` .</span><span class="sxs-lookup"><span data-stu-id="a61c0-151">For any of these entity types, you want to filter and return only those entities that have a given text inside one of their `string` fields.</span></span> <span data-ttu-id="a61c0-152">의 경우 `Person` 및 속성을 검색 합니다 `FirstName` `LastName` .</span><span class="sxs-lookup"><span data-stu-id="a61c0-152">For `Person`, you'd want to search the `FirstName` and `LastName` properties:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="PersonsQry":::

<span data-ttu-id="a61c0-153">하지만의 경우 속성만 `Car` 검색 하려고 합니다 `Model` .</span><span class="sxs-lookup"><span data-stu-id="a61c0-153">but for `Car`, you'd want to search only the `Model` property:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="CarsQry":::

<span data-ttu-id="a61c0-154">에 대해 하나의 사용자 지정 함수를 작성 하 고에 대해 다른 사용자 지정 함수를 작성할 수 있지만 `IQueryable(Of Person)` `IQueryable(Of Car)` , 다음 함수는 특정 요소 형식에 관계 없이 기존 쿼리에이 필터링을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-154">While you could write one custom function for `IQueryable(Of Person)` and another for `IQueryable(Of Car)`, the following function adds this filtering to any existing query, irrespective of the specific element type.</span></span>

### <a name="example"></a><span data-ttu-id="a61c0-155">예제</span><span class="sxs-lookup"><span data-stu-id="a61c0-155">Example</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate":::

<span data-ttu-id="a61c0-156">함수는 `TextFilter` 뿐 아니라 [IQueryable (Of T)](xref:System.Linq.IQueryable%601) 를 사용 하 고 반환 하기 때문에 <xref:System.Linq.IQueryable> 텍스트 필터 뒤에 컴파일 시간 형식화 된 쿼리 요소를 더 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-156">Because the `TextFilter` function takes and returns an [IQueryable(Of T)](xref:System.Linq.IQueryable%601) (and not just an <xref:System.Linq.IQueryable>), you can add further compile-time-typed query elements after the text filter.</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_expression_of_tdelegate_usage":::

## <a name="add-method-call-nodes-to-the-xrefsystemlinqiqueryables-expression-tree"></a><span data-ttu-id="a61c0-157">식 트리에 메서드 호출 노드를 추가 합니다. <xref:System.Linq.IQueryable></span><span class="sxs-lookup"><span data-stu-id="a61c0-157">Add method call nodes to the <xref:System.Linq.IQueryable>'s expression tree</span></span>

<span data-ttu-id="a61c0-158"><xref:System.Linq.IQueryable> [IQueryable (of T)](xref:System.Linq.IQueryable%601)이 아닌가 있는 경우 제네릭 LINQ 메서드를 직접 호출할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-158">If you have an <xref:System.Linq.IQueryable> instead of an [IQueryable(Of T)](xref:System.Linq.IQueryable%601), you can't directly call the generic LINQ methods.</span></span> <span data-ttu-id="a61c0-159">한 가지 대안은 위와 같이 내부 식 트리를 작성 하 고 리플렉션을 사용 하 여 식 트리를 전달 하는 동안 적절 한 LINQ 메서드를 호출 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-159">One alternative is to build the inner expression tree as above, and use reflection to invoke the appropriate LINQ method while passing in the expression tree.</span></span>

<span data-ttu-id="a61c0-160">LINQ 메서드 호출을 나타내는에 전체 트리를 래핑하여 LINQ 메서드의 기능을 복제할 수도 있습니다 <xref:System.Linq.Expressions.MethodCallExpression> .</span><span class="sxs-lookup"><span data-stu-id="a61c0-160">You could also duplicate the LINQ method's functionality, by wrapping the entire tree in a <xref:System.Linq.Expressions.MethodCallExpression> which represents a call to the LINQ method:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Factory_methods_lambdaexpression":::

<span data-ttu-id="a61c0-161">이 경우 컴파일 시간 `T` 제네릭 자리 표시 자가 없으므로 <xref:System.Linq.Expressions.Expression.Lambda%2A> 컴파일 시간 형식 정보를 요구 하지 않는 오버 로드를 사용 하 고 <xref:System.Linq.Expressions.LambdaExpression> [식 (tdelegate의 경우)](xref:System.Linq.Expressions.Expression%601)대신을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-161">Note that in this case you don't have a compile-time `T` generic placeholder, so you'll use the <xref:System.Linq.Expressions.Expression.Lambda%2A> overload which doesn't require compile-time type information, and which produces a <xref:System.Linq.Expressions.LambdaExpression> instead of an an [Expression(Of TDelegate)](xref:System.Linq.Expressions.Expression%601).</span></span>

## <a name="the-dynamic-linq-library"></a><span data-ttu-id="a61c0-162">동적 LINQ 라이브러리</span><span class="sxs-lookup"><span data-stu-id="a61c0-162">The Dynamic LINQ library</span></span>

<span data-ttu-id="a61c0-163">팩터리 메서드를 사용 하 여 식 트리를 생성 하는 것은 비교적 복잡 합니다. 문자열을 작성 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-163">Constructing expression trees using factory methods is relatively complex; it is easier to compose strings.</span></span> <span data-ttu-id="a61c0-164">[동적 linq 라이브러리](https://dynamic-linq.net/) 는의 표준 LINQ 메서드에 해당 하는의 확장 메서드 집합을 노출 하 <xref:System.Linq.IQueryable> <xref:System.Linq.Queryable> 고, 식 트리 대신 [특수 구문](https://dynamic-linq.net/expression-language) 에서 문자열을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-164">The [Dynamic LINQ library](https://dynamic-linq.net/) exposes a set of extension methods on <xref:System.Linq.IQueryable> corresponding to the standard LINQ methods at <xref:System.Linq.Queryable>, and which accept strings in a [special syntax](https://dynamic-linq.net/expression-language) instead of expression trees.</span></span> <span data-ttu-id="a61c0-165">라이브러리는 문자열에서 적절 한 식 트리를 생성 하 고 번역 된 결과를 반환할 수 있습니다 <xref:System.Linq.IQueryable> .</span><span class="sxs-lookup"><span data-stu-id="a61c0-165">The library generates the appropriate expression tree from the string, and can return the resultant translated <xref:System.Linq.IQueryable>.</span></span>

<span data-ttu-id="a61c0-166">예를 들어 앞의 예제 (식 트리 생성 포함)를 다음과 같이 다시 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a61c0-166">For instance, the previous example (including the expression tree construction) could be rewritten as follows:</span></span>

:::code language="vb" source="../../../../../samples/snippets/visualbasic/programming-guide/dynamic-linq-expression-trees/Program.vb" id="Dynamic_linq":::

## <a name="see-also"></a><span data-ttu-id="a61c0-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a61c0-167">See also</span></span>

- [<span data-ttu-id="a61c0-168">식 트리(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a61c0-168">Expression Trees (Visual Basic)</span></span>](index.md)
- [<span data-ttu-id="a61c0-169">방법: 식 트리 실행(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="a61c0-169">How to: Execute Expression Trees (Visual Basic)</span></span>](how-to-execute-expression-trees.md)
