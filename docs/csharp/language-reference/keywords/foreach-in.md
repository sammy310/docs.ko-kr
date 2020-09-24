---
description: foreach, in(C# 참조)
title: C# foreach 문
ms.date: 09/18/2020
f1_keywords:
- foreach
- foreach_CSharpKeyword
helpviewer_keywords:
- foreach keyword [C#]
- foreach statement [C#]
- in keyword [C#]
ms.assetid: 5a9c5ddc-5fd3-457a-9bb6-9abffcd874ec
ms.openlocfilehash: ea8a6f86595348a32b707caf9782f84147fefc87
ms.sourcegitcommit: 43ed174f085840ca18a791dc89fe833174da766d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/21/2020
ms.locfileid: "90828892"
---
# <a name="foreach-in-c-reference"></a><span data-ttu-id="a10c0-103">foreach, in(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="a10c0-103">foreach, in (C# reference)</span></span>

<span data-ttu-id="a10c0-104">`foreach` 문은 다음 예제와 같이 <xref:System.Collections.IEnumerable?displayProperty=nameWithType> 또는 <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> 인터페이스를 구현하는 형식의 인스턴스에 있는 각 요소에 대해 문 또는 문 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-104">The `foreach` statement executes a statement or a block of statements for each element in an instance of the type that implements the <xref:System.Collections.IEnumerable?displayProperty=nameWithType> or <xref:System.Collections.Generic.IEnumerable%601?displayProperty=nameWithType> interface, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="1" interactive="try-dotnet-method" :::

<span data-ttu-id="a10c0-105">`foreach` 문은 이러한 형식으로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-105">The `foreach` statement isn't limited to those types.</span></span> <span data-ttu-id="a10c0-106">다음 조건을 충족하는 모든 형식의 인스턴스와 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-106">You can use it with an instance of any type that satisfies the following conditions:</span></span>

- <span data-ttu-id="a10c0-107">형식에는 반환 형식이 클래스, 구조체 또는 인터페이스 유형인 public 매개 변수가 없는 `GetEnumerator` 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-107">A type has the public parameterless `GetEnumerator` method whose return type is either class, struct, or interface type.</span></span> <span data-ttu-id="a10c0-108">C# 9.0부터는 `GetEnumerator` 메서드가 형식의 [확장 메서드](../../programming-guide/classes-and-structs/extension-methods.md)일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-108">Beginning with C# 9.0, the `GetEnumerator` method can be a type's [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>
- <span data-ttu-id="a10c0-109">`GetEnumerator` 메서드의 반환 형식이 public `Current` 속성과 반환 형식이 <xref:System.Boolean>인 public 매개 변수가 없는 `MoveNext` 메서드를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-109">The return type of the `GetEnumerator` method has the public `Current` property and the public parameterless `MoveNext` method whose return type is <xref:System.Boolean>.</span></span>

<span data-ttu-id="a10c0-110">다음 예제에서는 인터페이스를 구현하지 않는 <xref:System.Span%601?displayProperty=nameWithType> 형식의 인스턴스와 함께 `foreach` 문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-110">The following example uses the `foreach` statement with an instance of the <xref:System.Span%601?displayProperty=nameWithType> type, which doesn't implement any interfaces:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="2" :::

<span data-ttu-id="a10c0-111">C# 7.3부터는 열거자의 `Current` 속성이 [참조 반환 값](ref.md#reference-return-values)(`ref T` 여기서 `T`는 컬렉션 요소의 형식임)을 반환하는 경우 다음 예제와 같이 `ref` 또는 `ref readonly` 한정자를 사용하여 반복 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-111">Beginning with C# 7.3, if the enumerator's `Current` property returns a [reference return value](ref.md#reference-return-values) (`ref T` where `T` is the type of a collection element), you can declare an iteration variable with the `ref` or `ref readonly` modifier, as the following example shows:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="RefSpan" :::

<span data-ttu-id="a10c0-112">C# 8.0부터는 `await foreach` 문을 사용하여 비동기 데이터 스트림 즉, <xref:System.Collections.Generic.IAsyncEnumerable%601> 인터페이스를 구현하는 컬렉션 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-112">Beginning with C# 8.0, you can use the `await foreach` statement to consume an asynchronous stream of data, that is, the collection type that implements the <xref:System.Collections.Generic.IAsyncEnumerable%601> interface.</span></span> <span data-ttu-id="a10c0-113">루프의 각 반복은 다음 요소가 비동기적으로 검색되는 동안 일시 중단될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-113">Each iteration of the loop may be suspended while the next element is retrieved asynchronously.</span></span> <span data-ttu-id="a10c0-114">다음 예제에서는 `await foreach` 문을 사용하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-114">The following example shows how to use the `await foreach` statement:</span></span>

:::code language="csharp" source="snippets/IterationKeywordsExamples.cs" id="AwaitForeach" :::

<span data-ttu-id="a10c0-115">기본적으로 스트림 요소는 캡처된 컨텍스트에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-115">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="a10c0-116">컨텍스트 캡처를 사용하지 않도록 설정하려면 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 확장 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-116">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="a10c0-117">동기화 컨텍스트 및 현재 컨텍스트 캡처에 대한 자세한 내용은 [작업 기반 비동기 패턴 사용](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a10c0-117">For more information about synchronization contexts and capturing the current context, see [Consuming the Task-based asynchronous pattern](../../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span> <span data-ttu-id="a10c0-118">비동기 스트림에 대한 자세한 내용은 [C# 8.0의 새로운 기능](../../whats-new/csharp-8.md) 문서의 [비동기 스트림](../../whats-new/csharp-8.md#asynchronous-streams) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a10c0-118">For more information about asynchronous streams, see the [Asynchronous streams](../../whats-new/csharp-8.md#asynchronous-streams) section of the [What's new in C# 8.0](../../whats-new/csharp-8.md) article.</span></span>

<span data-ttu-id="a10c0-119">`foreach` 문 블록 내 원하는 지점에서 [break](break.md) 문을 사용하여 루프를 중단하거나 [continue](continue.md) 문을 사용하여 루프의 다음 반복을 한 단계 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-119">At any point within the `foreach` statement block, you can break out of the loop by using the [break](break.md) statement, or step to the next iteration in the loop by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="a10c0-120">[goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 `foreach` 루프를 종료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-120">You can also exit a `foreach` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

<span data-ttu-id="a10c0-121">`foreach` 문이 `null`에 적용되면 <xref:System.NullReferenceException>이 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-121">If the `foreach` statement is applied to `null`, a <xref:System.NullReferenceException> is thrown.</span></span> <span data-ttu-id="a10c0-122">`foreach` 문의 소스 컬렉션이 비어 있으면 `foreach` 루프의 본문이 실행되지 않고 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-122">If the source collection of the `foreach` statement is empty, the body of the `foreach` loop isn't executed and skipped.</span></span>

## <a name="type-of-an-iteration-variable"></a><span data-ttu-id="a10c0-123">반복 변수의 형식</span><span class="sxs-lookup"><span data-stu-id="a10c0-123">Type of an iteration variable</span></span>

<span data-ttu-id="a10c0-124">다음 코드와 같이 `var` 키워드를 사용하여 컴파일러가 `foreach` 문에서 반복 변수의 형식을 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-124">You can use the `var` keyword to let the compiler infer the type of an iteration variable in the `foreach` statement, as the following code shows:</span></span>

```csharp
foreach (var item in collection) { }
```

<span data-ttu-id="a10c0-125">다음 코드와 같이 반복 변수의 형식을 명시적으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-125">You can also explicitly specify the type of an iteration variable, as the following code shows:</span></span>

```csharp
IEnumerable<T> collection = new T[5];
foreach (V item in collection) { }
```

<span data-ttu-id="a10c0-126">위의 양식에서 컬렉션 요소의 `T` 형식은 암시적 또는 명시적으로 반복 변수의 `V` 형식으로 변환할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-126">In the preceding form, type `T` of a collection element must be implicitly or explicitly convertible to type `V` of an iteration variable.</span></span> <span data-ttu-id="a10c0-127">`T`에서 `V`로의 명시적 변환이 런타임에 실패하는 경우 `foreach` 문은 <xref:System.InvalidCastException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-127">If an explicit conversion from `T` to `V` fails at run time, the `foreach` statement throws an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="a10c0-128">예를 들어 `T`가 봉인되지 않은 클래스 형식인 경우 `V`는 `T`가 구현하지 않는 형식을 포함하여 모든 인터페이스 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-128">For example, if `T` is a non-sealed class type, `V` can be any interface type, even the one that `T` doesn't implement.</span></span> <span data-ttu-id="a10c0-129">런타임에 컬렉션 요소의 형식은 `T`에서 파생되어 실제로 `V`를 구현하는 형식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-129">At run time, the type of a collection element may be the one that derives from `T` and actually implements `V`.</span></span> <span data-ttu-id="a10c0-130">그렇지 않은 경우에는 <xref:System.InvalidCastException>을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="a10c0-130">If that's not the case, an <xref:System.InvalidCastException> is thrown.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a10c0-131">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="a10c0-131">C# language specification</span></span>

<span data-ttu-id="a10c0-132">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [foreach 문](~/_csharplang/spec/statements.md#the-foreach-statement) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a10c0-132">For more information, see [The foreach statement](~/_csharplang/spec/statements.md#the-foreach-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="a10c0-133">C# 8.0 이상에 추가된 기능에 대한 자세한 내용은 다음 기능 제안 노트를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a10c0-133">For more information about features added in C# 8.0 and later, see the following feature proposal notes:</span></span>

- [<span data-ttu-id="a10c0-134">비동기 스트림(C# 8.0)</span><span class="sxs-lookup"><span data-stu-id="a10c0-134">Async streams (C# 8.0)</span></span>](~/_csharplang/proposals/csharp-8.0/async-streams.md)
- [<span data-ttu-id="a10c0-135">`foreach` 루프에 대한 확장 `GetEnumerator` 지원(C# 9.0)</span><span class="sxs-lookup"><span data-stu-id="a10c0-135">Extension `GetEnumerator` support for `foreach` loops (C# 9.0)</span></span>](~/_csharplang/proposals/csharp-9.0/extension-getenumerator.md)

## <a name="see-also"></a><span data-ttu-id="a10c0-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a10c0-136">See also</span></span>

- [<span data-ttu-id="a10c0-137">C# 참조</span><span class="sxs-lookup"><span data-stu-id="a10c0-137">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a10c0-138">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="a10c0-138">C# keywords</span></span>](index.md)
- [<span data-ttu-id="a10c0-139">배열에 foreach 사용</span><span class="sxs-lookup"><span data-stu-id="a10c0-139">Using foreach with arrays</span></span>](../../programming-guide/arrays/using-foreach-with-arrays.md)
- [<span data-ttu-id="a10c0-140">for 문</span><span class="sxs-lookup"><span data-stu-id="a10c0-140">for statement</span></span>](for.md)
