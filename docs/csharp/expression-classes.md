---
title: 식 트리를 지원하는 프레임워크 형식
description: 식 트리를 지원하는 프레임워크 형식, 식 트리 만들기, 식 트리 API 작업을 위한 기술에 대해 알아봅니다.
ms.date: 06/20/2016
ms.technology: csharp-advanced-concepts
ms.assetid: e9c85021-0d36-48af-91b7-aaaa66f22654
ms.openlocfilehash: 8483c46dde3ea97138e55ab84a5924a3d2578730
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79146088"
---
# <a name="framework-types-supporting-expression-trees"></a><span data-ttu-id="fb66e-103">식 트리를 지원하는 프레임워크 형식</span><span class="sxs-lookup"><span data-stu-id="fb66e-103">Framework Types Supporting Expression Trees</span></span>

[<span data-ttu-id="fb66e-104">이전 -- 식 트리 설명</span><span class="sxs-lookup"><span data-stu-id="fb66e-104">Previous -- Expression Trees Explained</span></span>](expression-trees-explained.md)

<span data-ttu-id="fb66e-105">.NET Core 프레임워크에는 식 트리에서 작동하는 클래스 목록이 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-105">There is a large list of classes in the .NET Core framework that work with Expression Trees.</span></span>
<span data-ttu-id="fb66e-106">전체 목록은 <xref:System.Linq.Expressions>에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-106">You can see the full list at <xref:System.Linq.Expressions>.</span></span>
<span data-ttu-id="fb66e-107">전체 목록을 실행하는 대신 프레임워크 클래스가 어떻게 디자인되었는지 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-107">Rather than run through the full list, let's understand how the framework classes have been designed.</span></span>

<span data-ttu-id="fb66e-108">언어 디자인에서 식이란 값을 계산하고 반환하는 코드의 본문입니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-108">In language design, an expression is a body of code that evaluates and returns a value.</span></span> <span data-ttu-id="fb66e-109">식은 매우 간단할 수 있습니다. 상수 식 `1`은 상수 값 1을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-109">Expressions may be very simple: the constant expression `1` returns the constant value of 1.</span></span> <span data-ttu-id="fb66e-110">식은 더 복잡할 수도 있습니다. `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` 식은 2차 방정식의 근을 반환합니다(방정식에 솔루션이 있는 경우).</span><span class="sxs-lookup"><span data-stu-id="fb66e-110">They may be more complicated: The expression `(-B + Math.Sqrt(B*B - 4 * A * C)) / (2 * A)` returns one root for a quadratic equation (in the case where the equation has a solution).</span></span>  

## <a name="it-all-starts-with-systemlinqexpression"></a><span data-ttu-id="fb66e-111">모두 System.Linq.Expression으로 시작</span><span class="sxs-lookup"><span data-stu-id="fb66e-111">It all starts with System.Linq.Expression</span></span>

<span data-ttu-id="fb66e-112">식 트리 사용의 복잡성 중 하나는 많은 종류의 식이 프로그램의 여러 위치에서 유효하다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-112">One of the complexities of working with expression trees is that many different kinds of expressions are valid in many places in programs.</span></span> <span data-ttu-id="fb66e-113">대입 식을 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="fb66e-113">Consider an assignment expression.</span></span> <span data-ttu-id="fb66e-114">대입 식의 오른쪽은 상수 값, 변수, 메서드 호출 식 등이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-114">The right hand side of an assignment could be a constant value, a variable, a method call expression, or others.</span></span> <span data-ttu-id="fb66e-115">해당 언어 유연성은 식 트리를 트래버스할 때 트리 노드의 모든 위치에서 여러 가지 다른 식 형식이 표시될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-115">That language flexibility means that you may encounter many different expression types anywhere in the nodes of a tree when you traverse an expression tree.</span></span> <span data-ttu-id="fb66e-116">따라서 기본 식 형식으로 작업하는 것이 가장 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-116">Therefore, when you can work with the base expression type, that's the simplest way to work.</span></span> <span data-ttu-id="fb66e-117">그러나 더 많은 것을 알아야 하는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-117">However, sometimes you need to know more.</span></span>
<span data-ttu-id="fb66e-118">기본 식 클래스에는 `NodeType` 속성이 이러한 용도로 포함되어 있으며,</span><span class="sxs-lookup"><span data-stu-id="fb66e-118">The base Expression class contains a `NodeType` property for this purpose.</span></span>
<span data-ttu-id="fb66e-119">가능한 식 형식의 열거형인 `ExpressionType`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-119">It returns an `ExpressionType` which is an enumeration of possible expression types.</span></span>
<span data-ttu-id="fb66e-120">노드의 형식을 알고 있다면 해당 형식으로 캐스트할 수 있으며 식 노드의 형식을 알고 있으면 특정 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-120">Once you know the type of the node, you can cast it to that type, and perform specific actions knowing the type of the expression node.</span></span> <span data-ttu-id="fb66e-121">특정 노드 유형을 검색한 다음 이러한 식의 특정 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-121">You can search for certain node types, and then work with the specific properties of that kind of expression.</span></span>

<span data-ttu-id="fb66e-122">예를 들어 다음 코드는 변수 액세스 식에서 변수의 이름을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-122">For example, this code will print the name of a variable for a variable access expression.</span></span> <span data-ttu-id="fb66e-123">노드 유형을 확인하고 변수 액세스 식에 캐스트한 다음 특정 식 형식의 속성을 확인하는 방법을 따랐습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-123">I've followed the practice of checking the node type, then casting to a variable access expression and then checking the properties of the specific expression type:</span></span>

```csharp
Expression<Func<int, int>> addFive = (num) => num + 5;

if (addFive.NodeType == ExpressionType.Lambda)
{
    var lambdaExp = (LambdaExpression)addFive;

    var parameter = lambdaExp.Parameters.First();

    Console.WriteLine(parameter.Name);
    Console.WriteLine(parameter.Type);
}
```

## <a name="creating-expression-trees"></a><span data-ttu-id="fb66e-124">식 트리 만들기</span><span class="sxs-lookup"><span data-stu-id="fb66e-124">Creating Expression Trees</span></span>

<span data-ttu-id="fb66e-125">`System.Linq.Expression` 클래스에는 식을 만드는 많은 정적 메서드도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-125">The `System.Linq.Expression` class also contains many static methods to create expressions.</span></span> <span data-ttu-id="fb66e-126">이러한 메서드는 자식에 대해 제공된 인수를 사용하여 식 노드를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-126">These methods create an expression node using the arguments supplied for its children.</span></span> <span data-ttu-id="fb66e-127">이러한 방식으로 리프 노드에서 위로 식을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-127">In this way, you build an expression up from its leaf nodes.</span></span> <span data-ttu-id="fb66e-128">예를 들어 다음 코드는 더하기 식을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-128">For example, this code builds an Add expression:</span></span>

```csharp
// Addition is an add expression for "1 + 2"
var one = Expression.Constant(1, typeof(int));
var two = Expression.Constant(2, typeof(int));
var addition = Expression.Add(one, two);
```

<span data-ttu-id="fb66e-129">이 간단한 예제를 통해 식 트리를 만들고 사용하는 데 많은 형식이 관련됨을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-129">You can see from this simple example that many types are involved in creating and working with expression trees.</span></span> <span data-ttu-id="fb66e-130">이러한 복잡성은 C# 언어에서 제공하는 풍부한 어휘의 기능을 제공하는 데 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-130">That complexity is necessary to provide the capabilities of the rich vocabulary provided by the C# language.</span></span>

## <a name="navigating-the-apis"></a><span data-ttu-id="fb66e-131">API 탐색</span><span class="sxs-lookup"><span data-stu-id="fb66e-131">Navigating the APIs</span></span>
<span data-ttu-id="fb66e-132">C# 언어의 거의 모든 구문 요소에 매핑되는 식 노드 유형이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-132">There are Expression node types that map to almost all of the syntax elements of the C# language.</span></span> <span data-ttu-id="fb66e-133">각 형식에는 해당 언어 요소 형식에 대한 특정 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-133">Each type has specific methods for that type of language element.</span></span> <span data-ttu-id="fb66e-134">한 번에 기억해야 할 사항이 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-134">It's a lot to keep in your head at one time.</span></span> <span data-ttu-id="fb66e-135">다음은 모든 사항을 기억하는 대신 식 트리로 작업할 때 사용할 수 있는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-135">Rather than try to memorize everything, here are the techniques I use to work with Expression trees:</span></span>

1. <span data-ttu-id="fb66e-136">`ExpressionType` 열거형의 멤버를 확인하여 검색할 수 있는 노드를 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-136">Look at the members of the `ExpressionType` enum to determine possible nodes you should be examining.</span></span> <span data-ttu-id="fb66e-137">실제로 식 트리를 트래버스하고 이해하려는 경우에 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-137">This really helps when you want to traverse and understand an expression tree.</span></span>
2. <span data-ttu-id="fb66e-138">`Expression` 클래스의 정적 멤버를 확인하여 식을 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-138">Look at the static members of the `Expression` class to build an expression.</span></span> <span data-ttu-id="fb66e-139">이러한 메서드는 자식 노드 집합에서 모든 식 형식을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-139">Those methods can build any expression type from a set of its child nodes.</span></span>
3. <span data-ttu-id="fb66e-140">`ExpressionVisitor` 클래스를 확인하여 수정된 식 트리를 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-140">Look at the `ExpressionVisitor` class to build a modified expression tree.</span></span>

<span data-ttu-id="fb66e-141">세 영역을 각각 확인하면 더 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-141">You'll find more as you look at each of those three areas.</span></span> <span data-ttu-id="fb66e-142">이러한 세 단계 중 한 단계로 시작하면 반드시 필요한 항목을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fb66e-142">Invariably, you will find what you need when you start with one of those three steps.</span></span>

 [<span data-ttu-id="fb66e-143">다음 -- 식 트리 실행</span><span class="sxs-lookup"><span data-stu-id="fb66e-143">Next -- Executing Expression Trees</span></span>](expression-trees-execution.md)
