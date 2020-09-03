---
title: LINQ 쿼리용 사용자 지정 메서드를 추가하는 방법(C#)
description: C#에서 IEnumerable<T> 인터페이스에 확장 메서드를 추가하여 LINQ 쿼리의 구문을 확장하는 방법을 알아봅니다.
ms.date: 08/26/2020
ms.assetid: 1a500f60-2e10-49fb-8b2a-d8d08e4817cb
ms.openlocfilehash: 768882fce40a2fc6e018f24c8928341e7c65bc4b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89122428"
---
# <a name="how-to-add-custom-methods-for-linq-queries-c"></a><span data-ttu-id="7ff51-103">LINQ 쿼리용 사용자 지정 메서드를 추가하는 방법(C#)</span><span class="sxs-lookup"><span data-stu-id="7ff51-103">How to add custom methods for LINQ queries (C#)</span></span>

<span data-ttu-id="7ff51-104"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 확장 메서드를 추가하여 LINQ 쿼리에 사용하는 메서드 세트를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-104">You extend the set of methods that you use for LINQ queries by adding extension methods to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span> <span data-ttu-id="7ff51-105">예를 들어 표준 평균 또는 최대 작업 외에 사용자 지정 집계 메서드를 만들어 값 시퀀스에서 단일 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-105">For example, in addition to the standard average or maximum operations, you create a custom aggregate method to compute a single value from a sequence of values.</span></span> <span data-ttu-id="7ff51-106">값 시퀀스에 대한 특정 데이터 변환 또는 사용자 지정 필터로 작동하고 새 시퀀스를 반환하는 메서드도 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-106">You also create a method that works as a custom filter or a specific data transform for a sequence of values and returns a new sequence.</span></span> <span data-ttu-id="7ff51-107">이러한 메서드의 예로는 <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A> 및 <xref:System.Linq.Enumerable.Reverse%2A>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-107">Examples of such methods are <xref:System.Linq.Enumerable.Distinct%2A>, <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Reverse%2A>.</span></span>

<span data-ttu-id="7ff51-108"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 확장하면 사용자 지정 메서드를 열거 가능한 컬렉션에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-108">When you extend the <xref:System.Collections.Generic.IEnumerable%601> interface, you can apply your custom methods to any enumerable collection.</span></span> <span data-ttu-id="7ff51-109">자세한 내용은 [확장 메서드](../../classes-and-structs/extension-methods.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ff51-109">For more information, see [Extension Methods](../../classes-and-structs/extension-methods.md).</span></span>

## <a name="adding-an-aggregate-method"></a><span data-ttu-id="7ff51-110">집계 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="7ff51-110">Adding an aggregate method</span></span>

<span data-ttu-id="7ff51-111">집계 메서드는 값 집합에서 하나의 값을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-111">An aggregate method computes a single value from a set of values.</span></span> <span data-ttu-id="7ff51-112">LINQ는 <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A> 및 <xref:System.Linq.Enumerable.Max%2A>를 포함하여 여러 집계 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-112">LINQ provides several aggregate methods, including <xref:System.Linq.Enumerable.Average%2A>, <xref:System.Linq.Enumerable.Min%2A>, and <xref:System.Linq.Enumerable.Max%2A>.</span></span> <span data-ttu-id="7ff51-113"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에 확장 메서드를 추가하여 고유한 집계 메서드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-113">You can create your own aggregate method by adding an extension method to the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="7ff51-114">다음 코드 예제에서는 `double` 형식의 숫자 시퀀스에 대한 중앙값을 계산하는 `Median`이라는 확장 메서드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-114">The following code example shows how to create an extension method called `Median` to compute a median for a sequence of numbers of type `double`.</span></span>

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="LinqExtensionClass":::

<span data-ttu-id="7ff51-115"><xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 다른 집계 메서드를 호출하는 것과 같은 방식으로 열거 가능한 컬렉션에 대해 이 확장 메서드를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-115">You call this extension method for any enumerable collection in the same way you call other aggregate methods from the <xref:System.Collections.Generic.IEnumerable%601> interface.</span></span>

<span data-ttu-id="7ff51-116">다음 코드 예제에서는 `double` 형식의 배열에 대해 `Median` 메서드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-116">The following code example shows how to use the `Median` method for an array of type `double`.</span></span>

:::code language="csharp" source="./snippets/Program.cs" ID="MedianUsage":::

### <a name="overloading-an-aggregate-method-to-accept-various-types"></a><span data-ttu-id="7ff51-117">다양한 형식을 허용하도록 집계 메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="7ff51-117">Overloading an Aggregate Method to Accept Various Types</span></span>

<span data-ttu-id="7ff51-118">다양한 형식의 시퀀스를 허용하도록 집계 메서드를 오버로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-118">You can overload your aggregate method so that it accepts sequences of various types.</span></span> <span data-ttu-id="7ff51-119">표준 접근법은 각 형식에 대한 오버로드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-119">The standard approach is to create an overload for each type.</span></span> <span data-ttu-id="7ff51-120">또 다른 접근법은 제네릭 형식을 사용하고 대리자를 통해 이를 특정 형식으로 변환할 오버로드를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-120">Another approach is to create an overload that will take a generic type and convert it to a specific type by using a delegate.</span></span> <span data-ttu-id="7ff51-121">두 가지 접근법을 결합할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-121">You can also combine both approaches.</span></span>

#### <a name="to-create-an-overload-for-each-type"></a><span data-ttu-id="7ff51-122">각 형식에 대한 오버로드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7ff51-122">To create an overload for each type</span></span>

<span data-ttu-id="7ff51-123">지원하려는 각 형식에 대한 특정 오버로드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-123">You can create a specific overload for each type that you want to support.</span></span> <span data-ttu-id="7ff51-124">다음 코드 예제에서는 `int` 형식에 대한 `Median` 메서드의 오버로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-124">The following code example shows an overload of the `Median` method for the `int` type.</span></span>

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="IntOverload":::

<span data-ttu-id="7ff51-125">이제 다음 코드와 같이 `integer` 및 `double` 형식에 대한 `Median` 오버로드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-125">You can now call the `Median` overloads for both `integer` and `double` types, as shown in the following code:</span></span>

:::code language="csharp" source="./snippets/Program.cs" ID="OverloadUsage":::

#### <a name="to-create-a-generic-overload"></a><span data-ttu-id="7ff51-126">제네릭 오버로드를 만들려면</span><span class="sxs-lookup"><span data-stu-id="7ff51-126">To create a generic overload</span></span>

<span data-ttu-id="7ff51-127">제네릭 개체의 시퀀스를 허용하는 오버로드를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-127">You can also create an overload that accepts a sequence of generic objects.</span></span> <span data-ttu-id="7ff51-128">이 오버로드는 대리자를 매개 변수로 사용하여 제네릭 형식의 개체 시퀀스를 특정 형식으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-128">This overload takes a delegate as a parameter and uses it to convert a sequence of objects of a generic type to a specific type.</span></span>

<span data-ttu-id="7ff51-129">다음 코드에서는 <xref:System.Func%602> 대리자를 매개 변수로 사용하는 `Median` 메서드의 오버로드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-129">The following code shows an overload of the `Median` method that takes the <xref:System.Func%602> delegate as a parameter.</span></span> <span data-ttu-id="7ff51-130">이 대리자는 제네릭 형식 T의 개체를 사용하고 `double` 형식의 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-130">This delegate takes an object of generic type T and returns an object of type `double`.</span></span>

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="GenericOverload":::

<span data-ttu-id="7ff51-131">이제 임의 형식의 개체 시퀀스에 대해 `Median` 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-131">You can now call the `Median` method for a sequence of objects of any type.</span></span> <span data-ttu-id="7ff51-132">형식에 자체 메서드 오버로드가 없으면 대리자 매개 변수를 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-132">If the type doesn't have its own method overload, you have to pass a delegate parameter.</span></span> <span data-ttu-id="7ff51-133">C#에서는 이 목적으로 람다 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-133">In C#, you can use a lambda expression for this purpose.</span></span> <span data-ttu-id="7ff51-134">또한 Visual Basic에서만, 메서드 호출 대신 `Aggregate` 또는 `Group By` 절을 사용할 경우 범위 내에 있는 값 또는 식을 이 절에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-134">Also, in Visual Basic only, if you use the `Aggregate` or `Group By` clause instead of the method call, you can pass any value or expression that is in the scope this clause.</span></span>

<span data-ttu-id="7ff51-135">다음 예제 코드에서는 정수 배열 및 문자열 배열에 대해 `Median` 메서드를 호출하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-135">The following example code shows how to call the `Median` method for an array of integers and an array of strings.</span></span> <span data-ttu-id="7ff51-136">문자열의 경우 배열에서 문자열 길이의 중앙값이 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-136">For strings, the median for the lengths of strings in the array is calculated.</span></span> <span data-ttu-id="7ff51-137">예제에서는 각 경우에 <xref:System.Func%602> 대리자 매개 변수를 `Median` 메서드에 전달하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-137">The example shows how to pass the <xref:System.Func%602> delegate parameter to the `Median` method for each case.</span></span>

:::code language="csharp" source="./snippets/Program.cs" ID="GenericUsage":::

## <a name="adding-a-method-that-returns-a-sequence"></a><span data-ttu-id="7ff51-138">시퀀스를 반환하는 메서드 추가</span><span class="sxs-lookup"><span data-stu-id="7ff51-138">Adding a method that returns a sequence</span></span>

<span data-ttu-id="7ff51-139">값 시퀀스를 반환하는 사용자 지정 쿼리 메서드를 사용하여 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-139">You can extend the <xref:System.Collections.Generic.IEnumerable%601> interface with a custom query method that returns a sequence of values.</span></span> <span data-ttu-id="7ff51-140">이 경우 메서드는 <xref:System.Collections.Generic.IEnumerable%601> 형식의 컬렉션을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-140">In this case, the method must return a collection of type <xref:System.Collections.Generic.IEnumerable%601>.</span></span> <span data-ttu-id="7ff51-141">이러한 메서드는 필터 또는 데이터 변환을 값 시퀀스에 적용하는 데 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-141">Such methods can be used to apply filters or data transforms to a sequence of values.</span></span>

<span data-ttu-id="7ff51-142">다음 예제에서는 모든 기타 요소를 첫 번째 인수부터 반환하는 `AlternateElements` 확장 메서드를 만드는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-142">The following example shows how to create an extension method named `AlternateElements` that returns every other element in a collection, starting from the first element.</span></span>

:::code language="csharp" source="./snippets/LinqExtensions.cs" ID="SequenceElement":::

<span data-ttu-id="7ff51-143">다음 코드와 같이 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스에서 다른 메서드를 호출할 때와 같은 방법으로 열거 가능한 모든 컬렉션에 대해 이 확장 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ff51-143">You can call this extension method for any enumerable collection just as you would call other methods from the <xref:System.Collections.Generic.IEnumerable%601> interface, as shown in the following code:</span></span>

:::code language="csharp" source="./snippets/Program.cs" ID="SequenceUsage":::

## <a name="see-also"></a><span data-ttu-id="7ff51-144">참조</span><span class="sxs-lookup"><span data-stu-id="7ff51-144">See also</span></span>

- <xref:System.Collections.Generic.IEnumerable%601>
- [<span data-ttu-id="7ff51-145">확장명 메서드</span><span class="sxs-lookup"><span data-stu-id="7ff51-145">Extension Methods</span></span>](../../classes-and-structs/extension-methods.md)
