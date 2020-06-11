---
title: C# foreach 문
ms.date: 06/03/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: 1645a246c9feee2a92c0d4e4bbeda47f0afde7d9
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84401890"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="07ada-102">foreach, in(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="07ada-102">foreach, in (C# reference)</span></span>

<span data-ttu-id="07ada-103">`foreach` 문은 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스를 구현하는 형식의 인스턴스에 있는 각 요소에 대해 문 또는 문 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-103">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="07ada-104">`foreach` 문은 해당 형식으로 제한되지 않으며 다음 조건을 충족하는 모든 형식의 인스턴스에 적용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-104">The `foreach` statement isn't limited to those types and can be applied to an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="07ada-105">반환 형식이 클래스, 구조체 또는 인터페이스 유형인 public 매개 변수가 없는 `GetEnumerator` 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-105">has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type,</span></span>
- <span data-ttu-id="07ada-106">`GetEnumerator` 메서드의 반환 형식이 public `Current` 속성과 반환 형식이 <xref:System.Boolean>인 public 매개 변수가 없는 `MoveNext` 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-106">the return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="07ada-107">대부분의 사용에서 `foreach`는 각 요소가 `T`형식인 `IEnumerable<T>` 식을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-107">In most uses, `foreach` iterates an `IEnumerable<T>` expression where each element is of type `T`.</span></span> <span data-ttu-id="07ada-108">그러나 요소는 `Current` 속성의 형식이 암시적 또는 명시적으로 변환된 모든 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-108">However, the elements may be any type that has an implicit or explicit conversion from the type of the `Current` property.</span></span> <span data-ttu-id="07ada-109">`Current` 속성이 `SomeType`을 반환하는 경우 요소의 형식은 다음과 같을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-109">If the `Current` property returns `SomeType`, the type of the elements may be:</span></span>

- <span data-ttu-id="07ada-110">`SomeType`의 임의 기본 클래스</span><span class="sxs-lookup"><span data-stu-id="07ada-110">Any of the base classes of `SomeType`.</span></span>
- <span data-ttu-id="07ada-111">`SomeType`에서 구현하는 임의 인터페이스</span><span class="sxs-lookup"><span data-stu-id="07ada-111">Any of the interfaces implemented by `SomeType`.</span></span>

<span data-ttu-id="07ada-112">또한 `SomeType`이 `class` 또는 `interface`이고 `sealed`가 아닌 경우 요소의 형식에는 다음이 포함될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-112">Furthermore, if `SomeType` is a `class` or an `interface` and not `sealed`, the type of elements may include:</span></span>

- <span data-ttu-id="07ada-113">`SomeType`에서 파생된 임의 형식</span><span class="sxs-lookup"><span data-stu-id="07ada-113">Any type derived from `SomeType`.</span></span>
- <span data-ttu-id="07ada-114">임의 인터페이스.</span><span class="sxs-lookup"><span data-stu-id="07ada-114">Any arbitrary interface.</span></span> <span data-ttu-id="07ada-115">`SomeType`에서 파생되거나 이 형식을 구현하는 클래스에서 모든 인터페이스가 구현될 수 있기 때문에 모든 인터페이스가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-115">Any interface is allowed because any interface may be implemented by a class derived from or implementing `SomeType`.</span></span>

<span data-ttu-id="07ada-116">이전 규칙과 일치하는 임의 형식을 사용하여 반복 변수를 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-116">You may declare the iteration variable using any type that matches the preceding rules.</span></span> <span data-ttu-id="07ada-117">`SomeType`에서 반복 변수의 형식으로 변환하는 데 명시적인 캐스트가 필요한 경우에는 변환이 실패하면 해당 작업에서 <xref:System.InvalidCastException>을 throw할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-117">If the conversion from `SomeType` to the type of the iteration variable requires an explicit cast, that operation may throw an <xref:System.InvalidCastException> when the conversion fails.</span></span>

<span data-ttu-id="07ada-118">C# 7.3부터는 열거자의 `Current` 속성이 [참조 반환 값](ref.md#reference-return-values)(`ref T` 여기서 `T`는 컬렉션 요소의 형식임)을 반환하는 경우 `ref` 또는 `ref readonly` 한정자를 사용하여 반복 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-118">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of the collection element), you can declare the iteration variable with the `ref` or `ref readonly` modifier.</span></span>

<span data-ttu-id="07ada-119">C# 8.0부터 컬렉션 형식이 <xref:System.Collections.Generic.IAsyncEnumerable%601> 인터페이스를 구현할 때 `foreach` 문에 `await` 연산자가 적용될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-119">Beginning with C# 8.0, the `await` operator may be applied to the `foreach` statement when the collection type implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="07ada-120">루프의 각 반복은 다음 요소가 비동기적으로 검색되는 동안 일시 중단될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-120">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="07ada-121">기본적으로 스트림 요소는 캡처된 컨텍스트에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-121">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="07ada-122">컨텍스트 캡처를 사용하지 않도록 설정하려면 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 확장 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-122">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="07ada-123">동기화 컨텍스트 및 현재 컨텍스트 캡처에 대한 자세한 내용은 [작업 기반 비동기 패턴 사용](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07ada-123">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

<span data-ttu-id="07ada-124">`foreach` 문 블록 내 원하는 지점에서 [break](break.md) 문을 사용하여 루프를 중단하거나 [continue](continue.md) 문을 사용하여 루프의 다음 반복을 한 단계 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-124">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="07ada-125">[goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 `foreach` 루프를 종료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-125">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="07ada-126">`foreach` 문이 `null`에 적용되면 <xref:System.NullReferenceException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-126">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="07ada-127">`foreach` 문의 소스 컬렉션이 비어 있으면 `foreach` 루프의 본문이 실행되지 않고 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-127">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="examples"></a><span data-ttu-id="07ada-128">예</span><span class="sxs-lookup"><span data-stu-id="07ada-128">Examples</span></span>

[!INCLUDE[interactive-note](~/includes/csharp-interactive-note.md)]

<span data-ttu-id="07ada-129">다음 예제는 <xref:System.Collections.Generic.IEnumerable%601> 인터페이스를 구현하는 <xref:System.Collections.Generic.List%601> 형식의 인스턴스와 함께 `foreach` 문의 사용법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-129">The following example shows usage of the `foreach` statement with an instance of the <xref:System.Collections.Generic.List%601> type that implements the <xref:System.Collections.Generic.IEnumerable%601> interface:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="07ada-130">다음 예제에서는 인터페이스를 구현하지 않는 <xref:System.Span%601?displayProperty=nameWithType> 형식의 인스턴스와 함께 `foreach` 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-130">The next example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="07ada-131">다음 예제에서는 `ref` 반복 변수를 사용하여 stackalloc 배열의 각 항목 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-131">The following example uses a `ref` iteration variable to set the value of each item in a stackalloc array.</span></span> <span data-ttu-id="07ada-132">`ref readonly` 버전은 컬렉션을 반복하여 모든 값을 인쇄합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-132">The `ref readonly` version iterates the collection to print all the values.</span></span> <span data-ttu-id="07ada-133">`readonly` 선언은 암시적 로컬 변수 선언을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-133">The `readonly` declaration uses an implicit local variable declaration.</span></span> <span data-ttu-id="07ada-134">명시적으로 변수 선언을 입력하므로 `ref` 또는 `ref readonly`에서 암시적 변수 선언을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-134">Implicit variable declarations can be used with either `ref` or `ref readonly` declarations, as can explicitly typed variable declarations.</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="07ada-135">다음 예에서는 `await foreach`를 사용하여 각 요소를 비동기적으로 생성하는 컬렉션을 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="07ada-135">The following example uses `await foreach` to iterate a collection that generates each element asynchronously:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach"  :::

## <a name="c-language-specification"></a><span data-ttu-id="07ada-136">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="07ada-136">C# language specification</span></span>

<span data-ttu-id="07ada-137">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [foreach 문](~/_csharplang/spec/statements.md#the-foreach-statement) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="07ada-137">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="07ada-138">참조</span><span class="sxs-lookup"><span data-stu-id="07ada-138">See also</span></span>

- [<span data-ttu-id="07ada-139">C# 참조</span><span class="sxs-lookup"><span data-stu-id="07ada-139">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="07ada-140">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="07ada-140">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="07ada-141">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="07ada-141">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="07ada-142">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="07ada-142">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="07ada-143">for 문</span><span class="sxs-lookup"><span data-stu-id="07ada-143">for statement</span></span>](for.md)
