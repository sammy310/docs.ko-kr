---
title: LINQ를 지원하는 C# 기능
ms.date: 07/20/2015
helpviewer_keywords:
- LINQ [C#], features supporting LINQ
ms.assetid: 524b0078-ebfd-45a7-b390-f2ceb9d84797
ms.openlocfilehash: 9fc8adaa49d02f8b69c2db6e94a28b9fab36b3b0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75635797"
---
# <a name="c-features-that-support-linq"></a><span data-ttu-id="67ae3-102">LINQ를 지원하는 C# 기능</span><span class="sxs-lookup"><span data-stu-id="67ae3-102">C# Features That Support LINQ</span></span>

<span data-ttu-id="67ae3-103">다음 섹션에서는 C# 3.0에 도입된 새로운 언어 구문을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-103">The following section introduces new language constructs introduced in C# 3.0.</span></span> <span data-ttu-id="67ae3-104">이러한 새 기능은 모두 LINQ 쿼리에서 어느 정도 사용되지만 LINQ로 제한되지 않고 유용한 모든 컨텍스트에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-104">Although these new features are all used to a degree with LINQ queries, they are not limited to LINQ and can be used in any context where you find them useful.</span></span>

## <a name="query-expressions"></a><span data-ttu-id="67ae3-105">쿼리 식</span><span class="sxs-lookup"><span data-stu-id="67ae3-105">Query Expressions</span></span>

<span data-ttu-id="67ae3-106">쿼리 식은 SQL이나 XQuery와 유사한 선언적 구문을 사용하여 IEnumerable 컬렉션을 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-106">Query expressions use a declarative syntax similar to SQL or XQuery to query over IEnumerable collections.</span></span> <span data-ttu-id="67ae3-107">컴파일 시간에 쿼리 구문은 LINQ 공급자의 표준 쿼리 연산자 확장 메서드 구현에 대한 메서드 호출로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-107">At compile time query syntax is converted to method calls to a LINQ provider's implementation of the standard query operator extension methods.</span></span> <span data-ttu-id="67ae3-108">애플리케이션은 `using` 지시문으로 적절한 네임스페이스를 지정하여 범위 내에 있는 표준 쿼리 연산자를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-108">Applications control the standard query operators that are in scope by specifying the appropriate namespace with a `using` directive.</span></span> <span data-ttu-id="67ae3-109">다음 쿼리 식은 문자열의 배열을 사용하고 문자열의 첫 번째 문자에 따라 그룹화하며 그룹의 순서를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-109">The following query expression takes an array of strings, groups them according to the first character in the string, and orders the groups.</span></span>

```csharp
var query = from str in stringArray
            group str by str[0] into stringGroup
            orderby stringGroup.Key
            select stringGroup;
```

<span data-ttu-id="67ae3-110">자세한 내용은 [LINQ 쿼리 식](../../../linq/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ae3-110">For more information, see [LINQ Query Expressions](../../../linq/index.md).</span></span>

## <a name="implicitly-typed-variables-var"></a><span data-ttu-id="67ae3-111">암시적으로 형식화된 변수(var)</span><span class="sxs-lookup"><span data-stu-id="67ae3-111">Implicitly Typed Variables (var)</span></span>

<span data-ttu-id="67ae3-112">변수를 선언하고 초기화할 때 명시적으로 형식을 지정하는 대신 다음과 같이 [var](../../../language-reference/keywords/var.md) 한정자를 사용하여 형식을 유추하고 할당하도록 컴파일러에 지시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-112">Instead of explicitly specifying a type when you declare and initialize a variable, you can use the [var](../../../language-reference/keywords/var.md) modifier to instruct the compiler to infer and assign the type, as shown here:</span></span>

```csharp
var number = 5;
var name = "Virginia";
var query = from str in stringArray
            where str[0] == 'm'
            select str;
```

<span data-ttu-id="67ae3-113">`var`로 선언된 변수는 형식을 명시적으로 지정한 변수만큼 강력한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-113">Variables declared as `var` are just as strongly-typed as variables whose type you specify explicitly.</span></span> <span data-ttu-id="67ae3-114">`var`을 사용하면 무명 형식을 만들 수 있지만 지역 변수에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-114">The use of `var` makes it possible to create anonymous types, but it can be used only for local variables.</span></span> <span data-ttu-id="67ae3-115">배열은 암시적 형식 지정을 사용하여 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-115">Arrays can also be declared with implicit typing.</span></span>

<span data-ttu-id="67ae3-116">자세한 내용은 [암시적으로 형식화된 지역 변수](../../classes-and-structs/implicitly-typed-local-variables.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ae3-116">For more information, see [Implicitly Typed Local Variables](../../classes-and-structs/implicitly-typed-local-variables.md).</span></span>

## <a name="object-and-collection-initializers"></a><span data-ttu-id="67ae3-117">개체 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="67ae3-117">Object and Collection Initializers</span></span>

<span data-ttu-id="67ae3-118">개체 및 컬렉션 이니셜라이저를 사용하면 개체에 대한 생성자를 명시적으로 호출하지 않고 개체를 초기화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-118">Object and collection initializers make it possible to initialize objects without explicitly calling a constructor for the object.</span></span> <span data-ttu-id="67ae3-119">일반적으로 이니셜라이저는 소스 데이터를 새 데이터 형식으로 프로젝션할 때 쿼리 식에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-119">Initializers are typically used in query expressions when they project the source data into a new data type.</span></span> <span data-ttu-id="67ae3-120">public `Name` 및 `Phone` 속성이 있는 `Customer`라는 클래스를 가정할 경우 다음 코드에서처럼 개체 이니셜라이저를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-120">Assuming a class named `Customer` with public `Name` and `Phone` properties, the object initializer can be used as in the following code:</span></span>

```csharp
var cust = new Customer { Name = "Mike", Phone = "555-1212" };
```

<span data-ttu-id="67ae3-121">계속해서 `Customer` 클래스를 사용하여 `IncomingOrders`라는 데이터 소스가 있다고 가정하고 큰 `OrderSize`가 있는 각 주문의 경우 해당 주문을 기반으로 새 `Customer`를 만들려고 한다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-121">Continuing with our `Customer` class, assume that there is a data source called `IncomingOrders`, and that for each order with a large `OrderSize`, we would like to create a new `Customer` based off of that order.</span></span> <span data-ttu-id="67ae3-122">LINQ 쿼리는 이 데이터 소스에서 실행하고 개체 초기화를 사용하여 컬렉션을 채울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-122">A LINQ query can be executed on this data source and use object initialization to fill a collection:</span></span>

```csharp
var newLargeOrderCustomers = from o in IncomingOrders
                            where o.OrderSize > 5
                            select new Customer { Name = o.Name, Phone = o.Phone };
```

<span data-ttu-id="67ae3-123">데이터 소스에는 `Customer` 클래스보다 더 많은 속성(예: `OrderSize`)이 있을 수 있지만, 개체 초기화를 사용하면 쿼리에서 반환된 데이터가 원하는 데이터 형식으로 모델링되므로 클래스와 관련된 데이터를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-123">The data source may have more properties lying under the hood than the `Customer` class such as `OrderSize`, but with object initialization, the data returned from the query is molded into the desired data type; we choose the data that is relevant to our class.</span></span> <span data-ttu-id="67ae3-124">따라서 이제 `IEnumerable`이 원하는 새 `Customer`로 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-124">As a result, we now have an `IEnumerable` filled with the new `Customer`s we wanted.</span></span> <span data-ttu-id="67ae3-125">위의 내용은 LINQ 메서드 구문으로 작성할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-125">The above can also be written in LINQ's method syntax:</span></span>

```csharp
var newLargeOrderCustomers = IncomingOrders.Where(x => x.OrderSize > 5).Select(y => new Customer { Name = y.Name, Phone = y.Phone });
```

<span data-ttu-id="67ae3-126">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67ae3-126">For more information, see:</span></span>

- [<span data-ttu-id="67ae3-127">개체 이니셜라이저 및 컬렉션 이니셜라이저</span><span class="sxs-lookup"><span data-stu-id="67ae3-127">Object and Collection Initializers</span></span>](../../classes-and-structs/object-and-collection-initializers.md)

- [<span data-ttu-id="67ae3-128">표준 쿼리 연산자의 쿼리 식 구문</span><span class="sxs-lookup"><span data-stu-id="67ae3-128">Query Expression Syntax for Standard Query Operators</span></span>](./query-expression-syntax-for-standard-query-operators.md)

## <a name="anonymous-types"></a><span data-ttu-id="67ae3-129">익명 형식</span><span class="sxs-lookup"><span data-stu-id="67ae3-129">Anonymous Types</span></span>

<span data-ttu-id="67ae3-130">무명 형식은 컴파일러에서 생성되며 형식 이름은 컴파일러에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-130">An anonymous type is constructed by the compiler and the type name is only available to the compiler.</span></span> <span data-ttu-id="67ae3-131">무명 형식은 별도의 명명된 형식을 정의하지 않고 쿼리 결과에서 일시적으로 속성 집합을 그룹화하는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-131">Anonymous types provide a convenient way to group a set of properties temporarily in a query result without having to define a separate named type.</span></span> <span data-ttu-id="67ae3-132">무명 형식은 다음과 같이 새로운 식과 개체 이니셜라이저를 사용하여 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-132">Anonymous types are initialized with a new expression and an object initializer, as shown here:</span></span>

```csharp
select new {name = cust.Name, phone = cust.Phone};
```

<span data-ttu-id="67ae3-133">자세한 내용은 [무명 형식](../../classes-and-structs/anonymous-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ae3-133">For more information, see [Anonymous Types](../../classes-and-structs/anonymous-types.md).</span></span>

## <a name="extension-methods"></a><span data-ttu-id="67ae3-134">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="67ae3-134">Extension Methods</span></span>

<span data-ttu-id="67ae3-135">확장 메서드는 형식과 연결하여 형식에 대한 인스턴스 메서드인 것처럼 호출할 수 있는 정적 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-135">An extension method is a static method that can be associated with a type, so that it can be called as if it were an instance method on the type.</span></span> <span data-ttu-id="67ae3-136">이 기능을 사용하면 실제로 수정하지 않고도 기존 형식에 새 메서드를 "추가"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-136">This feature enables you to, in effect, "add" new methods to existing types without actually modifying them.</span></span> <span data-ttu-id="67ae3-137">표준 쿼리 연산자는 <xref:System.Collections.Generic.IEnumerable%601>을 구현하는 모든 형식에 대해 LINQ 쿼리 기능을 제공하는 확장 메서드 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-137">The standard query operators are a set of extension methods that provide LINQ query functionality for any type that implements <xref:System.Collections.Generic.IEnumerable%601>.</span></span>

<span data-ttu-id="67ae3-138">자세한 내용은 [확장 메서드](../../classes-and-structs/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67ae3-138">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="lambda-expressions"></a><span data-ttu-id="67ae3-139">람다 식</span><span class="sxs-lookup"><span data-stu-id="67ae3-139">Lambda Expressions</span></span>

<span data-ttu-id="67ae3-140">람다 식은 => 연산자를 사용하여 함수 본문에서 입력 매개 변수를 구분하는 인라인 함수이며 컴파일 시간에 대리자나 식 트리로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-140">A lambda expression is an inline function that uses the => operator to separate input parameters from the function body and can be converted at compile time to a delegate or an expression tree.</span></span> <span data-ttu-id="67ae3-141">LINQ 프로그래밍에서는 표준 쿼리 연산자에 대한 메서드를 직접 호출할 때 람다 식이 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="67ae3-141">In LINQ programming, you will encounter lambda expressions when you make direct method calls to the standard query operators.</span></span>

<span data-ttu-id="67ae3-142">자세한 내용은 다음을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="67ae3-142">For more information, see:</span></span>

- [<span data-ttu-id="67ae3-143">익명 함수</span><span class="sxs-lookup"><span data-stu-id="67ae3-143">Anonymous Functions</span></span>](../../statements-expressions-operators/anonymous-functions.md)

- [<span data-ttu-id="67ae3-144">람다 식</span><span class="sxs-lookup"><span data-stu-id="67ae3-144">Lambda Expressions</span></span>](../../statements-expressions-operators/lambda-expressions.md)

- [<span data-ttu-id="67ae3-145">식 트리(C#)</span><span class="sxs-lookup"><span data-stu-id="67ae3-145">Expression Trees (C#)</span></span>](../expression-trees/index.md)

## <a name="see-also"></a><span data-ttu-id="67ae3-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="67ae3-146">See also</span></span>

- [<span data-ttu-id="67ae3-147">LINQ(Language-Integrated Query)(C#)</span><span class="sxs-lookup"><span data-stu-id="67ae3-147">Language-Integrated Query (LINQ) (C#)</span></span>](./index.md)
