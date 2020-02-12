---
title: F# 둘러보기
description: 이 자습서에서는 예제 코드를 사용하여 F# 프로그래밍 언어의 주요 기능을 살펴봅니다.
ms.date: 02/09/2020
ms.openlocfilehash: ac2eef40e2dbc494e41a9760f0a70edb0f7ce399
ms.sourcegitcommit: 011314e0c8eb4cf4a11d92078f58176c8c3efd2d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/11/2020
ms.locfileid: "77124574"
---
# <a name="tour-of-f"></a><span data-ttu-id="f30ba-103">F\# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="f30ba-103">Tour of F\#</span></span>

<span data-ttu-id="f30ba-104">F#에 대해 자세히 이해하려면 F# 코드를 읽고 작성하는 방법이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-104">The best way to learn about F# is to read and write F# code.</span></span> <span data-ttu-id="f30ba-105">이 문서에서는 F# 언어의 주요 기능 중 일부를 둘러보고 컴퓨터에서 실행할 수 있는 코드 조각을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-105">This article will act as a tour through some of the key features of the F# language and give you some code snippets that you can execute on your machine.</span></span> <span data-ttu-id="f30ba-106">개발 환경을 설정 하는 방법에 대 한 자세한 내용은 [시작](get-started/index.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="f30ba-106">To learn about setting up a development environment, check out [Getting Started](get-started/index.md).</span></span>

<span data-ttu-id="f30ba-107">F#에 함수(function)와 유형(type)이라는 두 가지 기본 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-107">There are two primary concepts in F#: functions and types.</span></span>  <span data-ttu-id="f30ba-108">둘러보기에서는 이 두 가지 개념에 해당하는 언어의 기능을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-108">This tour will emphasize features of the language which fall into these two concepts.</span></span>

## <a name="executing-the-code-online"></a><span data-ttu-id="f30ba-109">온라인에서 코드 실행</span><span class="sxs-lookup"><span data-stu-id="f30ba-109">Executing the code online</span></span>

<span data-ttu-id="f30ba-110">컴퓨터에가 설치 F# 되어 있지 않은 경우에는 [Weasembmba를 사용해 보세요 F# ](https://tryfsharp.fsbolero.io/).</span><span class="sxs-lookup"><span data-stu-id="f30ba-110">If you don't have F# installed on your machine, you can execute all of the samples in your browser with [Try F# on WebAssembly](https://tryfsharp.fsbolero.io/).</span></span> <span data-ttu-id="f30ba-111">Fable은 F#과 유사하며 브라우저에서 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-111">Fable is a dialect of F# that executes directly in your browser.</span></span> <span data-ttu-id="f30ba-112">Repl에서 팔 로우 하는 예제를 보려면 fable repl의 왼쪽 메뉴 모음에서 **샘플 F# >** 확인 하 여 > 둘러보기를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-112">To view the samples that follow in the REPL, check out **Samples > Learn > Tour of F#** in the left-hand menu bar of the Fable REPL.</span></span>

## <a name="functions-and-modules"></a><span data-ttu-id="f30ba-113">함수와 모듈</span><span class="sxs-lookup"><span data-stu-id="f30ba-113">Functions and Modules</span></span>

<span data-ttu-id="f30ba-114">F# 프로그램의 가장 기본적인 부분은 ***모듈로***구성 된 ***함수*** 입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-114">The most fundamental pieces of any F# program are ***functions*** organized into ***modules***.</span></span>  <span data-ttu-id="f30ba-115">[함수](./language-reference/functions/index.md) 는 입력에 대 한 작업을 수행 하 여 출력을 생성 [Modules](./language-reference/modules.md)하며, 이러한 함수는 항목을 그룹화 하는 기본 F#방법인 모듈 아래에 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-115">[Functions](./language-reference/functions/index.md) perform work on inputs to produce outputs, and they are organized under [Modules](./language-reference/modules.md), which are the primary way you group things in F#.</span></span>  <span data-ttu-id="f30ba-116">이는 함수에 이름을 지정 하 고 인수를 정의 하는 [`let` 바인딩을](./language-reference/functions/let-bindings.md)사용 하 여 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-116">They are defined using the [`let` binding](./language-reference/functions/let-bindings.md), which give the function a name and define its arguments.</span></span>

[!code-fsharp[BasicFunctions](~/samples/snippets/fsharp/tour.fs#L101-L133)]

<span data-ttu-id="f30ba-117">`let` 바인딩은 다른 언어의 변수와 유사 하 게 값을 이름에 바인딩하는 방법 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-117">`let` bindings are also how you bind a value to a name, similar to a variable in other languages.</span></span>  <span data-ttu-id="f30ba-118">`let` 바인딩은 기본적으로 ***변경할*** 수 없습니다. 즉, 값 이나 함수를 이름에 바인딩한 후에는 내부에서 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-118">`let` bindings are ***immutable*** by default, which means that once a value or function is bound to a name, it cannot be changed in-place.</span></span>  <span data-ttu-id="f30ba-119">이는 ***변경할***수 있는 다른 언어의 변수와 대조적입니다. 즉, 특정 시점에 해당 값을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-119">This is in contrast to variables in other languages, which are ***mutable***, meaning their values can be changed at any point in time.</span></span>  <span data-ttu-id="f30ba-120">변경할 수 있는 바인딩이 필요한 경우 `let mutable ...` 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-120">If you require a mutable binding, you can use `let mutable ...` syntax.</span></span>

[!code-fsharp[Immutability](~/samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a><span data-ttu-id="f30ba-121">숫자, 부울 및 문자열</span><span class="sxs-lookup"><span data-stu-id="f30ba-121">Numbers, Booleans, and Strings</span></span>

<span data-ttu-id="f30ba-122">.NET 언어는 .NET에 F# 존재 하는 동일한 기본 [기본 형식을](language-reference/basic-types.md) 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-122">As a .NET language, F# supports the same underlying [primitive types](language-reference/basic-types.md) that exist in .NET.</span></span>

<span data-ttu-id="f30ba-123">다양 한 숫자 형식은 F#의 표현 됩니다 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-123">Here is how various numeric types are represented in F#:</span></span>

[!code-fsharp[Numbers](~/samples/snippets/fsharp/tour.fs#L49-L68)]

<span data-ttu-id="f30ba-124">부울 값과 기본 조건부 논리를 수행 하는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-124">Here's what Boolean values and performing basic conditional logic looks like:</span></span>

[!code-fsharp[Bools](~/samples/snippets/fsharp/tour.fs#L142-L152)]

<span data-ttu-id="f30ba-125">그리고 다음과 같은 기본적인 [문자열](./language-reference/strings.md) 조작이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-125">And here's what basic [string](./language-reference/strings.md) manipulation looks like:</span></span>

[!code-fsharp[Strings](~/samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a><span data-ttu-id="f30ba-126">튜플</span><span class="sxs-lookup"><span data-stu-id="f30ba-126">Tuples</span></span>

<span data-ttu-id="f30ba-127">[튜플은](./language-reference/tuples.md) 큰 거래 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-127">[Tuples](./language-reference/tuples.md) are a big deal in F#.</span></span>  <span data-ttu-id="f30ba-128">값 자체로 처리 될 수 있는 명명 되지 않았지만 순서가 지정 된 값의 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-128">They are a grouping of unnamed, but ordered values, that can be treated as values themselves.</span></span>  <span data-ttu-id="f30ba-129">이러한 값을 다른 값에서 집계 된 값으로 간주 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-129">Think of them as values which are aggregated from other values.</span></span>  <span data-ttu-id="f30ba-130">함수에서 여러 값을 편리 하 게 반환 하거나 일부 임시 편의를 위해 값을 그룹화 하는 등의 여러 가지 용도로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-130">They have many uses, such as conveniently returning multiple values from a function, or grouping values for some ad-hoc convenience.</span></span>

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L186-L203)]

<span data-ttu-id="f30ba-131">`struct` 튜플을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-131">You can also create `struct` tuples.</span></span>  <span data-ttu-id="f30ba-132">또한 튜플도 `struct` c # 7/Visual Basic 15 튜플로 완전히 상호 운용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-132">These also interoperate fully with C#7/Visual Basic 15 tuples, which are also `struct` tuples:</span></span>

[!code-fsharp[Tuples](~/samples/snippets/fsharp/tour.fs#L205-L218)]

<span data-ttu-id="f30ba-133">`struct` 튜플은 값 형식 이므로 참조 튜플로 암시적으로 변환 될 수 없으며, 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-133">It's important to note that because `struct` tuples are value types, they cannot be implicitly converted to reference tuples, or vice versa.</span></span>  <span data-ttu-id="f30ba-134">참조와 구조체 튜플 사이에서 명시적으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-134">You must explicitly convert between a reference and struct tuple.</span></span>

## <a name="pipelines-and-composition"></a><span data-ttu-id="f30ba-135">파이프라인 및 컴퍼지션</span><span class="sxs-lookup"><span data-stu-id="f30ba-135">Pipelines and Composition</span></span>

<span data-ttu-id="f30ba-136">`|>`와 같은 파이프 연산자는에서 F#데이터를 처리할 때 광범위 하 게 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-136">Pipe operators such as `|>` are used extensively when processing data in F#.</span></span> <span data-ttu-id="f30ba-137">이러한 연산자는 함수에 대 한 "파이프라인"을 유연 하 게 설정할 수 있도록 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-137">These operators are functions that allow you to establish "pipelines" of functions in a flexible manner.</span></span> <span data-ttu-id="f30ba-138">다음 예제에서는 이러한 연산자를 활용 하 여 간단한 함수 파이프라인을 만드는 방법을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-138">The following example walks through how you can take advantage of these operators to build a simple functional pipeline:</span></span>

[!code-fsharp[Pipelines](~/samples/snippets/fsharp/tour.fs#L227-L282)]

<span data-ttu-id="f30ba-139">위의 샘플에서는 목록 처리 함수, 첫 번째 F#클래스 함수 및 [부분 응용 프로그램](./language-reference/functions/index.md#partial-application-of-arguments)을 포함 하 여의 여러 기능을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-139">The previous sample made use of many features of F#, including list processing functions, first-class functions, and [partial application](./language-reference/functions/index.md#partial-application-of-arguments).</span></span> <span data-ttu-id="f30ba-140">이러한 각 개념에 대 한 심층적인 이해는 다소 고급이 될 수 있지만 파이프라인을 빌드할 때 쉽게 함수를 사용 하 여 데이터를 처리할 수 있는지 명확 하 게 이해 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-140">Although a deep understanding of each of those concepts can become somewhat advanced, it should be clear how easily functions can be used to process data when building pipelines.</span></span>

## <a name="lists-arrays-and-sequences"></a><span data-ttu-id="f30ba-141">목록, 배열 및 시퀀스</span><span class="sxs-lookup"><span data-stu-id="f30ba-141">Lists, Arrays, and Sequences</span></span>

<span data-ttu-id="f30ba-142">목록, 배열 및 시퀀스는 F# 핵심 라이브러리의 세 가지 기본 컬렉션 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-142">Lists, Arrays, and Sequences are three primary collection types in the F# core library.</span></span>

<span data-ttu-id="f30ba-143">[목록은](./language-reference/lists.md) 동일한 형식의 요소에 대 한 순서가 지정 되지 않은 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-143">[Lists](./language-reference/lists.md) are ordered, immutable collections of elements of the same type.</span></span>  <span data-ttu-id="f30ba-144">이러한 목록은 단일 항목 연결 목록입니다. 즉, 열거형을 위한 것 이며, 크기가 클 경우 임의 액세스 및 연결에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-144">They are singly-linked lists, which means they are meant for enumeration, but a poor choice for random access and concatenation if they're large.</span></span>  <span data-ttu-id="f30ba-145">이는 일반적으로 단일 연결 목록을 사용 하 여 목록을 표시 하지 않는 다른 인기 언어의 목록과 대조 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-145">This in contrast to Lists in other popular languages, which typically do not use a singly-linked list to represent Lists.</span></span>

[!code-fsharp[Lists](~/samples/snippets/fsharp/tour.fs#L309-L359)]

<span data-ttu-id="f30ba-146">[배열은](./language-reference/arrays.md) 동일한 형식의 요소에 대 한 고정 크기의 *변경* 가능한 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-146">[Arrays](./language-reference/arrays.md) are fixed-size, *mutable* collections of elements of the same type.</span></span>  <span data-ttu-id="f30ba-147">요소의 빠른 임의 액세스를 지원 하며 F# 목록에서는 방금 연속 된 메모리 블록을 이기 때문에 보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-147">They support fast random access of elements, and are faster than F# lists because they are just contiguous blocks of memory.</span></span>

[!code-fsharp[Arrays](~/samples/snippets/fsharp/tour.fs#L368-L407)]

<span data-ttu-id="f30ba-148">[시퀀스](./language-reference/sequences.md) 는 요소의 논리적 계열로, 모두 동일한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-148">[Sequences](./language-reference/sequences.md) are a logical series of elements, all of the same type.</span></span>  <span data-ttu-id="f30ba-149">이러한 형식은 목록 및 배열 보다 일반적인 형식으로, 논리적 요소 시리즈에 대 한 "뷰"가 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-149">These are a more general type than Lists and Arrays, capable of being your "view" into any logical series of elements.</span></span>  <span data-ttu-id="f30ba-150">***지연***될 수도 있기 때문에이는 가능 합니다. 즉, 필요할 때만 요소를 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-150">They also stand out because they can be ***lazy***, which means that elements can be computed only when they are needed.</span></span>

[!code-fsharp[Sequences](~/samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a><span data-ttu-id="f30ba-151">재귀 함수</span><span class="sxs-lookup"><span data-stu-id="f30ba-151">Recursive Functions</span></span>

<span data-ttu-id="f30ba-152">컬렉션 또는 요소의 시퀀스를 처리 하는 작업은 [recursion](./language-reference/functions/index.md#recursive-functions) 일반적으로 F#에서 재귀를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-152">Processing collections or sequences of elements is typically done with [recursion](./language-reference/functions/index.md#recursive-functions) in F#.</span></span>  <span data-ttu-id="f30ba-153">F#에 루프 및 명령형 프로그래밍에 대 한 지원으로 재귀는 정확성을 보장 하기 위해 더 쉽기 때문에 기본 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-153">Although F# has support for loops and imperative programming, recursion is preferred because it is easier to guarantee correctness.</span></span>

> [!NOTE]
> <span data-ttu-id="f30ba-154">다음 예제에서는 `match` 식을 통해 패턴 일치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-154">The following example makes use of the pattern matching via the `match` expression.</span></span>  <span data-ttu-id="f30ba-155">이 기본 구문은이 문서의 뒷부분에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-155">This fundamental construct is covered later in this article.</span></span>

[!code-fsharp[RecursiveFunctions](~/samples/snippets/fsharp/tour.fs#L461-L500)]

<span data-ttu-id="f30ba-156">F# 또한가 마무리 호출 최적화에 대 한 전체 지원 있습니다 빠른 루프 구문으로는 재귀 호출을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-156">F# also has full support for Tail Call Optimization, which is a way to optimize recursive calls so that they are just as fast as a loop construct.</span></span>

## <a name="record-and-discriminated-union-types"></a><span data-ttu-id="f30ba-157">레코드 및 구분 된 공용 구조체 형식</span><span class="sxs-lookup"><span data-stu-id="f30ba-157">Record and Discriminated Union Types</span></span>

<span data-ttu-id="f30ba-158">레코드 및 공용 구조체 형식을 F# 코드에 사용 되는 두 가지 기본 데이터 형식이 되며 일반적으로 가장 좋은 방법은 F# 프로그램에서 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-158">Record and Union types are two fundamental data types used in F# code, and are generally the best way to represent data in an F# program.</span></span>  <span data-ttu-id="f30ba-159">이렇게 하면 다른 언어의 클래스와 유사 하지만, 기본적인 차이점 중 하나는 구조적 같음 의미 체계가 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-159">Although this makes them similar to classes in other languages, one of their primary differences is that they have structural equality semantics.</span></span>  <span data-ttu-id="f30ba-160">즉, 이러한 값은 "기본적으로" 비교 가능 하며 같음은 매우 간단 합니다. 즉, 다른 것과 동일한 지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-160">This means that they are "natively" comparable and equality is straightforward - just check if one is equal to the other.</span></span>

<span data-ttu-id="f30ba-161">[레코드](./language-reference/records.md) 는 선택적 멤버 (예: 메서드)가 있는 명명 된 값의 집계입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-161">[Records](./language-reference/records.md) are an aggregate of named values, with optional members (such as methods).</span></span>  <span data-ttu-id="f30ba-162">C# 또는 Java에 대해 잘 알고 있는 경우에는 구조적 같음 및 less 공식 절차을 사용 하는 pocos 또는 POJOs와 유사 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-162">If you're familiar with C# or Java, then these should feel similar to POCOs or POJOs - just with structural equality and less ceremony.</span></span>

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L507-L559)]

<span data-ttu-id="f30ba-163">레코드를 구조체로 나타낼 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-163">You can also represent Records as structs.</span></span> <span data-ttu-id="f30ba-164">`[<Struct>]` 특성을 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-164">This is done with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Records](~/samples/snippets/fsharp/tour.fs#L561-L568)]

<span data-ttu-id="f30ba-165">[구분 된 공용 구조체 (du)](./language-reference/discriminated-unions.md) 는 명명 된 형식이 나 사례의 수 일 수 있는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-165">[Discriminated Unions (DUs)](./language-reference/discriminated-unions.md) are values which could be a number of named forms or cases.</span></span>  <span data-ttu-id="f30ba-166">형식에 저장 된 데이터는 여러 개의 고유 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-166">Data stored in the type can be one of several distinct values.</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L575-L631)]

<span data-ttu-id="f30ba-167">Du를 *단일 대/소문자 구분 된 공용 구조체*로 사용 하 여 기본 형식에 대 한 도메인 모델링에 도움이 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-167">You can also use DUs as *Single-Case Discriminated Unions*, to help with domain modeling over primitive types.</span></span>  <span data-ttu-id="f30ba-168">자주, 문자열 및 기타 기본 형식을 사용 하 여 무언가를 표시 하면 특정 의미가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-168">Often times, strings and other primitive types are used to represent something, and are thus given a particular meaning.</span></span>  <span data-ttu-id="f30ba-169">그러나 데이터의 기본 표시만 사용 하면 잘못 된 값이 잘못 할당 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-169">However, using only the primitive representation of the data can result in mistakenly assigning an incorrect value!</span></span>  <span data-ttu-id="f30ba-170">각 유형의 정보를 별개의 단일 사례 공용 구조체로 표현 하면이 시나리오에서 정확성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-170">Representing each type of information as a distinct single-case union can enforce correctness in this scenario.</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L633-L654)]

<span data-ttu-id="f30ba-171">위의 샘플에서 보여 주는 것 처럼, 단일 대/소문자 구분 된 공용 구조체에서 내부 값을 가져오려면 명시적으로 래핑 해제 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-171">As the above sample demonstrates, to get the underlying value in a single-case Discriminated Union, you must explicitly unwrap it.</span></span>

<span data-ttu-id="f30ba-172">또한 Du는 재귀 정의를 지원 하 여 트리 및 본질적으로 재귀적 데이터를 쉽게 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-172">Additionally, DUs also support recursive definitions, allowing you to easily represent trees and inherently recursive data.</span></span>  <span data-ttu-id="f30ba-173">예를 들어 `exists` 및 `insert` 함수를 사용 하 여 이진 검색 트리를 나타낼 수 있는 방법은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-173">For example, here's how you can represent a Binary Search Tree with `exists` and `insert` functions.</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L656-L683)]

<span data-ttu-id="f30ba-174">Du를 사용 하면 데이터 형식에서 트리의 재귀 구조를 나타낼 수 있으므로이 재귀적 구조에서 작업 하는 것은 간단 하며 정확성을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-174">Because DUs allow you to represent the recursive structure of the tree in the data type, operating on this recursive structure is straightforward and guarantees correctness.</span></span>  <span data-ttu-id="f30ba-175">또한 아래와 같이 패턴 일치에서 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-175">It is also supported in pattern matching, as shown below.</span></span>

<span data-ttu-id="f30ba-176">또한 `[<Struct>]` 특성을 사용 하 여 Du을 `struct`s로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-176">Additionally, you can represent DUs as `struct`s with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Unions](~/samples/snippets/fsharp/tour.fs#L685-L696)]

<span data-ttu-id="f30ba-177">그러나이 작업을 수행할 때는 다음 두 가지 주요 사항을 염두에 두어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-177">However, there are two key things to keep in mind when doing so:</span></span>

1. <span data-ttu-id="f30ba-178">구조체 DU는 재귀적으로 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-178">A struct DU cannot be recursively-defined.</span></span>
2. <span data-ttu-id="f30ba-179">구조체 DU는 각 사례에 대해 고유한 이름을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-179">A struct DU must have unique names for each of its cases.</span></span>

<span data-ttu-id="f30ba-180">위의 작업을 수행 하는 데 실패 하면 컴파일 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-180">Failure to follow the above will result in a compilation error.</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="f30ba-181">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="f30ba-181">Pattern Matching</span></span>

<span data-ttu-id="f30ba-182">[패턴 일치](./language-reference/pattern-matching.md) 는 형식 F# 에 F# 대 한 작업을 정확 하 게 수행할 수 있도록 하는 언어 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-182">[Pattern Matching](./language-reference/pattern-matching.md) is the F# language feature which enables correctness for operating on F# types.</span></span>  <span data-ttu-id="f30ba-183">위의 샘플에서 상당히 많은 `match x with ...` 구문을 알게 되었을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-183">In the above samples, you probably noticed quite a bit of `match x with ...` syntax.</span></span>  <span data-ttu-id="f30ba-184">이 구문을 사용 하면 컴파일러가 데이터 형식의 "셰이프"를 이해할 수 있으므로 전체 패턴 일치를 통해 데이터 형식을 사용 하는 경우 가능한 모든 사례를 설명할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-184">This construct allows the compiler, which can understand the "shape" of data types, to force you to account for all possible cases when using a data type through what is known as Exhaustive Pattern Matching.</span></span>  <span data-ttu-id="f30ba-185">이는 정확성을 위해 매우 강력 하며, 일반적으로 컴파일 시간에 대 한 런타임 문제를 "리프트" 하는 데 사용 되는 영리 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-185">This is incredibly powerful for correctness, and can be cleverly used to "lift" what would normally be a runtime concern into compile-time.</span></span>

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L705-L742)]

<span data-ttu-id="f30ba-186">`_` 패턴을 사용 하는 것이 무엇 인지 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-186">Something you may have noticed is the use of the `_` pattern.</span></span>  <span data-ttu-id="f30ba-187">이를 [와일드 카드 패턴](./language-reference/pattern-matching.md#wildcard-pattern)이라고 하며,이 패턴은 "무엇이 무엇 인지 걱정할 필요가 없습니다." 라는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-187">This is known as the [Wildcard Pattern](./language-reference/pattern-matching.md#wildcard-pattern), which is a way of saying "I don't care what something is".</span></span>  <span data-ttu-id="f30ba-188">매우 편리 하지만 `_`를 사용 하는 데 익숙하지 않은 경우에는 실수로 완전 한 패턴 일치를 무시 하 고 컴파일 시간 사항을 더 이상 혜택을 받지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-188">Although convenient, you can accidentally bypass Exhaustive Pattern Matching and no longer benefit from compile-time enforcements if you aren't careful in using `_`.</span></span>  <span data-ttu-id="f30ba-189">패턴 일치의 경우 분해 된 형식의 특정 부분을 고려 하지 않거나 패턴 일치 식에 모든 의미 있는 사례를 열거 한 경우에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-189">It is best used when you don't care about certain pieces of a decomposed type when pattern matching, or the final clause when you have enumerated all meaningful cases in a pattern matching expression.</span></span>

<span data-ttu-id="f30ba-190">다음 예제에서는 구문 분석 작업이 실패 하는 경우 `_` 사례가 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-190">In the following example, the `_` case is used when a parse operation fails.</span></span>

[!code-fsharp[PatternMatching](~/samples/snippets/fsharp/tour.fs#L744-L762)]

<span data-ttu-id="f30ba-191">[활성 패턴](./language-reference/active-patterns.md) 은 패턴 일치에 사용할 수 있는 또 다른 강력한 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-191">[Active Patterns](./language-reference/active-patterns.md) are another powerful construct to use with pattern matching.</span></span>  <span data-ttu-id="f30ba-192">입력 데이터를 사용자 지정 형식으로 분할 하 여 패턴 일치 호출 사이트에서 분해 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-192">They allow you to partition input data into custom forms, decomposing them at the pattern match call site.</span></span>  <span data-ttu-id="f30ba-193">매개 변수화 될 수도 있으므로 파티션을 함수로 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-193">They can also be parameterized, thus allowing to define the partition as a function.</span></span>  <span data-ttu-id="f30ba-194">활성 패턴을 지원 하기 위해 이전 예제를 확장 하는 것은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-194">Expanding the previous example to support Active Patterns looks something like this:</span></span>

[!code-fsharp[ActivePatterns](~/samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a><span data-ttu-id="f30ba-195">선택적 형식</span><span class="sxs-lookup"><span data-stu-id="f30ba-195">Optional Types</span></span>

<span data-ttu-id="f30ba-196">구별 된 공용 구조체 유형의 특수 경우는 옵션 종류를 F# 핵심 라이브러리의 일부는 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-196">One special case of Discriminated Union types is the Option Type, which is so useful that it's a part of the F# core library.</span></span>

<span data-ttu-id="f30ba-197">[옵션 형식은](./language-reference/options.md) 두 가지 사례 (값 또는 nothing) 중 하나를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-197">[The Option Type](./language-reference/options.md) is a type which represents one of two cases: a value, or nothing at all.</span></span>  <span data-ttu-id="f30ba-198">특정 작업에서 값이 생성 될 수도 있고 그렇지 않을 수도 있는 모든 시나리오에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-198">It is used in any scenario where a value may or may not result from a particular operation.</span></span>  <span data-ttu-id="f30ba-199">이렇게 하면 두 경우 모두를 고려 하 여 런타임 문제 보다는 컴파일 시간을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-199">This then forces you to account for both cases, making it a compile-time concern rather than a runtime concern.</span></span>  <span data-ttu-id="f30ba-200">이러한 기능은 종종 "nothing"을 나타내는 데 사용 되는 `null` Api에서 사용 되므로 많은 상황에서 `NullReferenceException`에 대해 걱정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-200">These are often used in APIs where `null` is used to represent "nothing" instead, thus eliminating the need to worry about `NullReferenceException` in many circumstances.</span></span>

[!code-fsharp[Options](~/samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a><span data-ttu-id="f30ba-201">측정 단위</span><span class="sxs-lookup"><span data-stu-id="f30ba-201">Units of Measure</span></span>

<span data-ttu-id="f30ba-202">F#의 형식 시스템의 고유한 특징 중 하나는 측정 단위를 통해 숫자 리터럴에 대 한 컨텍스트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-202">One unique feature of F#'s type system is the ability to provide context for numeric literals through Units of Measure.</span></span>

<span data-ttu-id="f30ba-203">[측정 단위](./language-reference/units-of-measure.md) 를 사용 하 여 숫자 형식을 미터와 같은 단위에 연결 하 고 함수에서 숫자 리터럴이 아닌 단위에 대 한 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-203">[Units of Measure](./language-reference/units-of-measure.md) allow you to associate a numeric type to a unit, such as Meters, and have functions perform work on units rather than numeric literals.</span></span>  <span data-ttu-id="f30ba-204">이를 통해 컴파일러는 특정 컨텍스트에서 전달 된 숫자 리터럴의 형식이 적합 한지 확인할 수 있습니다. 따라서 해당 종류의 작업과 관련 된 런타임 오류가 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-204">This enables the compiler to verify that the types of numeric literals passed in make sense under a certain context, thus eliminating runtime errors associated with that kind of work.</span></span>

[!code-fsharp[UnitsOfMeasure](~/samples/snippets/fsharp/tour.fs#L817-L842)]

<span data-ttu-id="f30ba-205">F# 핵심 라이브러리는 많은 SI 단위 유형 및 변환 단위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-205">The F# Core library defines many SI unit types and unit conversions.</span></span>  <span data-ttu-id="f30ba-206">자세히 알아보려면 [Microsoft.FSharp.Data.UnitSystems.SI 네임 스페이스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="f30ba-206">To learn more, check out the [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).</span></span>

## <a name="classes-and-interfaces"></a><span data-ttu-id="f30ba-207">클래스 및 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f30ba-207">Classes and Interfaces</span></span>

<span data-ttu-id="f30ba-208">F#또한에는 .NET 클래스, [인터페이스](./language-reference/interfaces.md), [추상 클래스](./language-reference/abstract-classes.md), [상속](./language-reference/inheritance.md)등에 대 한 모든 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-208">F# also has full support for .NET classes, [Interfaces](./language-reference/interfaces.md), [Abstract Classes](./language-reference/abstract-classes.md), [Inheritance](./language-reference/inheritance.md), and so on.</span></span>

<span data-ttu-id="f30ba-209">[클래스](./language-reference/classes.md) 는 속성, 메서드 및 이벤트를 [멤버로](./language-reference/members/index.md)가질 수 있는 .net 개체를 나타내는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-209">[Classes](./language-reference/classes.md) are types that represent .NET objects, which can have properties, methods, and events as its [Members](./language-reference/members/index.md).</span></span>

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L845-L880)]

<span data-ttu-id="f30ba-210">제네릭 클래스를 정의 하는 것도 매우 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-210">Defining generic classes is also very straightforward.</span></span>

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L883-L908)]

<span data-ttu-id="f30ba-211">인터페이스를 구현 하려면 `interface ... with` 구문 또는 [개체 식을](./language-reference/object-expressions.md)사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-211">To implement an Interface, you can use either `interface ... with` syntax or an [Object Expression](./language-reference/object-expressions.md).</span></span>

[!code-fsharp[Classes](~/samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a><span data-ttu-id="f30ba-212">사용할 형식</span><span class="sxs-lookup"><span data-stu-id="f30ba-212">Which Types to Use</span></span>

<span data-ttu-id="f30ba-213">클래스, 레코드, 구분 된 공용 구조체 및 튜플이 있으면 다음과 같은 중요 한 질문을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-213">The presence of Classes, Records, Discriminated Unions, and Tuples leads to an important question: which should you use?</span></span>  <span data-ttu-id="f30ba-214">대부분의 경우와 마찬가지로 대답은 사용자의 상황에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-214">Like most everything in life, the answer depends on your circumstances.</span></span>

<span data-ttu-id="f30ba-215">튜플은 함수에서 여러 값을 반환 하 고 값의 임시 집계를 값 자체로 사용 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-215">Tuples are great for returning multiple values from a function, and using an ad-hoc aggregate of values as a value itself.</span></span>

<span data-ttu-id="f30ba-216">레코드는 튜플의 "프로시저 단위" 이며 명명 된 레이블과 선택적 멤버에 대 한 지원이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-216">Records are a "step up" from Tuples, having named labels and support for optional members.</span></span>  <span data-ttu-id="f30ba-217">프로그램을 통해 전송 중인 데이터를 낮은 공식 절차 표현 하는 데 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-217">They are great for a low-ceremony representation of data in-transit through your program.</span></span>  <span data-ttu-id="f30ba-218">구조는 구조가 일치 하므로 비교와 함께 사용 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-218">Because they have structural equality, they are easy to use with comparison.</span></span>

<span data-ttu-id="f30ba-219">구별 된 공용 구조체는 많은 용도로 사용 되지만 핵심 혜택은 데이터에 포함 될 수 있는 모든 가능한 "셰이프"를 고려 하는 패턴 일치와 함께 사용할 수 있다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-219">Discriminated Unions have many uses, but the core benefit is to be able to utilize them in conjunction with Pattern Matching to account for all possible "shapes" that a data can have.</span></span>  

<span data-ttu-id="f30ba-220">클래스는 정보를 표시 하 고 해당 정보를 기능에 연결 해야 하는 경우와 같이 다양 한 이유로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-220">Classes are great for a huge number of reasons, such as when you need to represent information and also tie that information to functionality.</span></span>  <span data-ttu-id="f30ba-221">일반적으로 일부 데이터에 연결 된 기능을 사용 하는 경우 클래스 및 개체 지향 프로그래밍의 원리를 사용 하는 것이 큰 장점입니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-221">As a rule of thumb, when you have functionality which is conceptually tied to some data, using Classes and the principles of Object-Oriented Programming is a big benefit.</span></span>  <span data-ttu-id="f30ba-222">이러한 언어는 거의 모든 항목에 대해 클래스를 C# 사용 하므로 클래스는 및 Visual Basic 상호 운용할 때 기본 데이터 형식 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-222">Classes are also the preferred data type when interoperating with C# and Visual Basic, as these languages use classes for nearly everything.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f30ba-223">다음 단계</span><span class="sxs-lookup"><span data-stu-id="f30ba-223">Next Steps</span></span>

<span data-ttu-id="f30ba-224">지금까지 살펴본 언어의 주요 기능 중 일부는 이제 첫 번째 F# 프로그램 작성을 준비 해야 합니다!</span><span class="sxs-lookup"><span data-stu-id="f30ba-224">Now that you've seen some of the primary features of the language, you should be ready to write your first F# programs!</span></span>  <span data-ttu-id="f30ba-225">[시작](get-started/index.md) 을 확인 하 여 개발 환경을 설정 하 고 일부 코드를 작성 하는 방법을 알아보세요.</span><span class="sxs-lookup"><span data-stu-id="f30ba-225">Check out [Getting Started](get-started/index.md) to learn how to set up your development environment and write some code.</span></span>

<span data-ttu-id="f30ba-226">자세한 정보를 얻기 위한 다음 단계는 원하는 대로 지정할 수 있지만 핵심 함수형 프로그래밍 개념에 익숙해지면 [의 F# 함수형 프로그래밍에 대해 소개](./introduction-to-functional-programming/index.md) 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-226">The next steps for learning more can be whatever you like, but we recommend [Introduction to Functional Programming in F#](./introduction-to-functional-programming/index.md) to get comfortable with core Functional Programming concepts.</span></span>  <span data-ttu-id="f30ba-227">이러한 강력한 프로그램 F# 빌드에 필수적인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f30ba-227">These will be essential in building robust programs in F#.</span></span>

<span data-ttu-id="f30ba-228">또한 [ F# 언어 참조](./language-reference/index.md) 를 확인 하 여에 대 F#한 포괄적인 개념 콘텐츠 컬렉션을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="f30ba-228">Also, check out the [F# Language Reference](./language-reference/index.md) to see a comprehensive collection of conceptual content on F#.</span></span>
