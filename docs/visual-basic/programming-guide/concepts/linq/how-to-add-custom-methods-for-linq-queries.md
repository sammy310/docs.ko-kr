---
description: '자세한 정보: 방법: LINQ 쿼리에 대 한 사용자 지정 메서드 추가 (Visual Basic)'
title: '방법: LINQ 쿼리용 사용자 지정 메서드 추가'
ms.date: 08/28/2020
ms.assetid: 099b2e2a-83cd-45c6-aa4d-01b398b5faaf
ms.openlocfilehash: 62acf22a8be9986388233ee34121a97d65a87f43
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100424530"
---
# <a name="how-to-add-custom-methods-for-linq-queries-visual-basic"></a><span data-ttu-id="ff237-103">방법: LINQ 쿼리에 대 한 사용자 지정 메서드 추가 (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ff237-103">How to: Add custom methods for LINQ queries (Visual Basic)</span></span>

<span data-ttu-id="ff237-104"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 확장 메서드를 추가하여 LINQ 쿼리에 사용하는 메서드 세트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-104">You extend the set of methods that you use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="ff237-105">예를 들어 표준 평균 또는 최대 작업 외에 사용자 지정 집계 메서드를 만들어 값 시퀀스에서 단일 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-105">For example, in addition to the standard average or maximum operations, you create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="ff237-106">값 시퀀스에 대한 특정 데이터 변환 또는 사용자 지정 필터로 작동하고 새 시퀀스를 반환하는 메서드도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-106">You also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="ff237-107">이러한 메서드의 예로는 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Reverse%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-107">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="ff237-108"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 확장하면 사용자 지정 메서드를 열거 가능한 컬렉션에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-108">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="ff237-109">자세한 내용은 [확장 메서드](../../language-features/procedures/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ff237-109">For more information, see [Extension Methods](../../language-features/procedures/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="ff237-110">집계 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="ff237-110">Adding an aggregate method</span></span>

<span data-ttu-id="ff237-111">집계 메서드는 값 집합에서 하나의 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-111">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="ff237-112">LINQ는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Max%2A>를 포함하여 여러 집계 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-112">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="ff237-113"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 확장 메서드를 추가하여 고유한 집계 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-113">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="ff237-114">다음 코드 예제에서는 `double` 형식의 숫자 시퀀스에 대한 중앙값을 계산하는 `Median`이라는 확장 메서드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-114">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

:::code language="vb" source="./snippets/LinqExtension.vb" :::

<span data-ttu-id="ff237-115"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 다른 집계 메서드를 호출하는 것과 같은 방식으로 열거 가능한 컬렉션에 대해 이 확장 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-115">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

> [!NOTE]
> <span data-ttu-id="ff237-116">Visual Basic 또는 절에 대해 메서드 호출 또는 표준 쿼리 구문을 사용할 수 있습니다 `Aggregate` `Group By` .</span><span class="sxs-lookup"><span data-stu-id="ff237-116">In Visual Basic, you can either use a method call or standard query syntax for the `Aggregate` or `Group By` clause.</span></span> <span data-ttu-id="ff237-117">자세한 내용은 [Aggregate 절](../../../language-reference/queries/aggregate-clause.md) 및 [Group By 절](../../../language-reference/queries/group-by-clause.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ff237-117">For more information, see [Aggregate Clause](../../../language-reference/queries/aggregate-clause.md) and [Group By Clause](../../../language-reference/queries/group-by-clause.md).</span></span>

<span data-ttu-id="ff237-118">다음 코드 예제에서는 `double` 형식의 배열에 대해 `Median` 메서드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-118">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

:::code language="vb" source="./snippets/Program.vb" ID="MedianUsage":::

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="ff237-119">집계 메서드를 오버 로드 하 여 다양 한 형식 허용</span><span class="sxs-lookup"><span data-stu-id="ff237-119">Overloading an aggregate method to accept various types</span></span>

<span data-ttu-id="ff237-120">다양한 형식의 시퀀스를 허용하도록 집계 메서드를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-120">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="ff237-121">표준 접근법은 각 형식에 대한 오버로드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-121">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="ff237-122">또 다른 접근법은 제네릭 형식을 사용하고 대리자를 통해 이를 특정 형식으로 변환할 오버로드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-122">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="ff237-123">두 가지 접근법을 결합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-123">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="ff237-124">각 형식에 대한 오버로드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ff237-124">To create an overload for each type</span></span>

<span data-ttu-id="ff237-125">지원하려는 각 형식에 대한 특정 오버로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-125">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="ff237-126">다음 코드 예제에서는 `integer` 형식에 대한 `Median` 메서드의 오버로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-126">The following code example shows an overload of the `Median` method for the `integer` type.</span></span>

:::code language="vb" source="./snippets/OtherExtensions.vb" ID="IntOverload":::

<span data-ttu-id="ff237-127">이제 다음 코드와 같이 `integer` 및 `double` 형식에 대한 `Median` 오버로드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-127">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

:::code language="vb" source="./snippets/Program.vb" ID="OverloadUsage":::

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="ff237-128">제네릭 오버로드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="ff237-128">To create a generic overload</span></span>

<span data-ttu-id="ff237-129">제네릭 개체의 시퀀스를 허용하는 오버로드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-129">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="ff237-130">이 오버로드는 대리자를 매개 변수로 사용하여 제네릭 형식의 개체 시퀀스를 특정 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-130">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="ff237-131">다음 코드에서는 <xref:System.Func%602> 대리자를 매개 변수로 사용하는 `Median` 메서드의 오버로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-131">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="ff237-132">이 대리자는 제네릭 형식의 개체를 사용 `T` 하 여 형식의 개체를 반환 `double` 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-132">This delegate takes an object of generic type `T` and returns an object of type `double`.</span></span>

:::code language="vb" source="./snippets/OtherExtensions.vb" ID="GenericOverload":::

<span data-ttu-id="ff237-133">이제 임의 형식의 개체 시퀀스에 대해 `Median` 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-133">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="ff237-134">형식에 자체 메서드 오버로드가 없으면 대리자 매개 변수를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-134">If the type does not have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="ff237-135">Visual Basic에서 람다 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-135">In Visual Basic, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="ff237-136">또한 `Aggregate` 메서드 호출 대신 또는 절을 사용 하는 경우 `Group By` 이 절 범위에 있는 값 또는 식을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-136">Also, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="ff237-137">다음 예제 코드에서는 정수 배열 및 문자열 배열에 대해 `Median` 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-137">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="ff237-138">문자열의 경우 배열에서 문자열 길이의 중앙값이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-138">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="ff237-139">예제에서는 각 경우에 <xref:System.Func%602> 대리자 매개 변수를 `Median` 메서드에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-139">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

:::code language="vb" source="./snippets/Program.vb" ID="GenericUsage":::

## <a name="adding-a-method-that-returns-a-collection"></a><span data-ttu-id="ff237-140">컬렉션을 반환 하는 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="ff237-140">Adding a method that returns a collection</span></span>

<span data-ttu-id="ff237-141">값 시퀀스를 반환하는 사용자 지정 쿼리 메서드를 사용하여 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-141">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="ff237-142">이 경우 메서드는 <xref:System.Collections.Generic.IEnumerable%601> 형식의 컬렉션을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-142">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="ff237-143">이러한 메서드는 필터 또는 데이터 변환을 값 시퀀스에 적용하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-143">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="ff237-144">다음 예제에서는 모든 기타 요소를 첫 번째 인수부터 반환하는 `AlternateElements` 확장 메서드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-144">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

:::code language="vb" source="./snippets/OtherExtensions.vb" ID="SequenceElement":::

<span data-ttu-id="ff237-145">다음 코드와 같이 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 다른 메서드를 호출할 때와 같은 방법으로 열거 가능한 모든 컬렉션에 대해 이 확장 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ff237-145">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

:::code language="vb" source="./snippets/Program.vb" ID="SequenceUsage":::

## <a name="see-also"></a><span data-ttu-id="ff237-146">참조</span><span class="sxs-lookup"><span data-stu-id="ff237-146">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="ff237-147">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="ff237-147">Extension Methods</span></span>](../../language-features/procedures/extension-methods.md)
