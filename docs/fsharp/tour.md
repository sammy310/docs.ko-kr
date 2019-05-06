---
title: F# 둘러보기
description: 이 자습서에서는 예제 코드를 사용하여 F# 프로그래밍 언어의 주요 기능을 살펴봅니다.
ms.date: 11/06/2018
ms.openlocfilehash: 4b3ec7fd2c42712440ea7d7045c560ab20390b45
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61901732"
---
# <a name="tour-of-f"></a><span data-ttu-id="071f3-103">F\# 둘러보기</span><span class="sxs-lookup"><span data-stu-id="071f3-103">Tour of F\#</span></span>

<span data-ttu-id="071f3-104">F#에 대해 자세히 이해하려면 F# 코드를 읽고 작성하는 방법이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-104">The best way to learn about F# is to read and write F# code.</span></span> <span data-ttu-id="071f3-105">이 문서에서는 F# 언어의 주요 기능 중 일부를 둘러보고 컴퓨터에서 실행할 수 있는 코드 조각을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-105">This article will act as a tour through some of the key features of the F# language and give you some code snippets that you can execute on your machine.</span></span> <span data-ttu-id="071f3-106">개발 환경 설정에 대한 자세한 내용은 [시작하기](tutorials/getting-started/index.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="071f3-106">To learn about setting up a development environment, check out [Getting Started](tutorials/getting-started/index.md).</span></span>

<span data-ttu-id="071f3-107">F#에 함수(function)와 유형(type)이라는 두 가지 기본 개념이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-107">There are two primary concepts in F#: functions and types.</span></span>  <span data-ttu-id="071f3-108">둘러보기에서는 이 두 가지 개념에 해당하는 언어의 기능을 강조합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-108">This tour will emphasize features of the language which fall into these two concepts.</span></span>

## <a name="executing-the-code-online"></a><span data-ttu-id="071f3-109">온라인에서 코드 실행</span><span class="sxs-lookup"><span data-stu-id="071f3-109">Executing the code online</span></span>

<span data-ttu-id="071f3-110">F#이 컴퓨터에 설치되지 않았다면 [Fable REPL](https://fable.io/repl/)을 사용하여 온라인의 모든 샘플을 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-110">If you don't have F# installed on your machine, you can execute all of the samples online with the [Fable REPL](https://fable.io/repl/).</span></span> <span data-ttu-id="071f3-111">Fable은 F#과 유사하며 브라우저에서 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-111">Fable is a dialect of F# that executes directly in your browser.</span></span> <span data-ttu-id="071f3-112">REPL에서 다음에 나오는 예제를 보기 위해서는 Fable REPL의 왼쪽 메뉴 바에서 **Samples > Learn > Tour of F#** 를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="071f3-112">To view the samples that follow in the REPL, check out **Samples > Learn > Tour of F#** in the left-hand menu bar of the Fable REPL.</span></span>

## <a name="functions-and-modules"></a><span data-ttu-id="071f3-113">함수와 모듈</span><span class="sxs-lookup"><span data-stu-id="071f3-113">Functions and Modules</span></span>

<span data-ttu-id="071f3-114">F# 프로그램의 가장 기본적인 부분은 ***모듈***로 구성된 ***함수***입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-114">The most fundamental pieces of any F# program are ***functions*** organized into ***modules***.</span></span>  <span data-ttu-id="071f3-115">[함수](language-reference/functions/index.md)는 입력에 대한 작업으로 출력을 생성하고, F#에서 작업을 그룹화하는 기본 방식인 [모듈](language-reference/modules.md)로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-115">[Functions](language-reference/functions/index.md) perform work on inputs to produce outputs, and they are organized under [Modules](language-reference/modules.md), which are the primary way you group things in F#.</span></span>  <span data-ttu-id="071f3-116">[`let` 바인딩](language-reference/functions/let-bindings.md)을 사용하여 정의하며, 함수 이름을 지정하고 해당 인수를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-116">They are defined using the [`let` binding](language-reference/functions/let-bindings.md), which give the function a name and define its arguments.</span></span>

[!code-fsharp[BasicFunctions](../../samples/snippets/fsharp/tour.fs#L101-L133)]

<span data-ttu-id="071f3-117">`let` 바인딩 이름으로 유사한 다른 언어에서 변수에 값을 바인딩하는 방법을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-117">`let` bindings are also how you bind a value to a name, similar to a variable in other languages.</span></span>  <span data-ttu-id="071f3-118">`let` 바인딩은 ***변경할 수 없는*** 기본적으로 값 또는 함수 이름에 바인딩된 후 변경할 수 없습니다 즉 원위치 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-118">`let` bindings are ***immutable*** by default, which means that once a value or function is bound to a name, it cannot be changed in-place.</span></span>  <span data-ttu-id="071f3-119">이 변수는 다른 언어로 대조적 ***변경할 수 있는***, 즉 해당 값에서에서 변경할 수 있습니다 언제 든 지 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-119">This is in contrast to variables in other languages, which are ***mutable***, meaning their values can be changed at any point in time.</span></span>  <span data-ttu-id="071f3-120">변경할 수 있는 바인딩을 필요로 하는 경우 사용할 수 있습니다 `let mutable ...` 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-120">If you require a mutable binding, you can use `let mutable ...` syntax.</span></span>

[!code-fsharp[Immutability](../../samples/snippets/fsharp/tour.fs#L75-L94)]

## <a name="numbers-booleans-and-strings"></a><span data-ttu-id="071f3-121">숫자, 부울 및 문자열</span><span class="sxs-lookup"><span data-stu-id="071f3-121">Numbers, Booleans, and Strings</span></span>

<span data-ttu-id="071f3-122">.NET 언어로, F# 지원 동일한 기본 [기본 형식](language-reference/primitive-types.md) .NET에 존재 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-122">As a .NET language, F# supports the same underlying [primitive types](language-reference/primitive-types.md) that exist in .NET.</span></span>

<span data-ttu-id="071f3-123">다양 한 숫자 형식은 F#의 표현 됩니다 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-123">Here is how various numeric types are represented in F#:</span></span>

[!code-fsharp[Numbers](../../samples/snippets/fsharp/tour.fs#L49-L68)]

<span data-ttu-id="071f3-124">부울 값 이며 다음과 같은 기본 조건부 논리를 수행 합니다. 여기서:</span><span class="sxs-lookup"><span data-stu-id="071f3-124">Here's what Boolean values and performing basic conditional logic looks like:</span></span>

[!code-fsharp[Bools](../../samples/snippets/fsharp/tour.fs#L142-L152)]

<span data-ttu-id="071f3-125">어떤 basic 다음과 같습니다 [문자열](language-reference/strings.md) 조작 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-125">And here's what basic [string](language-reference/strings.md) manipulation looks like:</span></span>

[!code-fsharp[Strings](../../samples/snippets/fsharp/tour.fs#L158-L180)]

## <a name="tuples"></a><span data-ttu-id="071f3-126">튜플</span><span class="sxs-lookup"><span data-stu-id="071f3-126">Tuples</span></span>

<span data-ttu-id="071f3-127">[튜플](language-reference/tuples.md) F#에서는 큰 문제가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-127">[Tuples](language-reference/tuples.md) are a big deal in F#.</span></span>  <span data-ttu-id="071f3-128">이들은 자체 값으로 취급 될 수 있는 명명 되지 않은 않았지만 순서가 지정 된 값의 그룹입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-128">They are a grouping of unnamed, but ordered values, that can be treated as values themselves.</span></span>  <span data-ttu-id="071f3-129">다른 값에서 집계 된 값으로 생각 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-129">Think of them as values which are aggregated from other values.</span></span>  <span data-ttu-id="071f3-130">편리 하 게 함수에서 여러 값을 반환 하거나 임시 편의 대 한 값 그룹화와 같은 다양 한 용도로 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-130">They have many uses, such as conveniently returning multiple values from a function, or grouping values for some ad-hoc convenience.</span></span>

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L186-L203)]

<span data-ttu-id="071f3-131">F# 4.1을 기준으로 만들 수도 있습니다 `struct` 튜플.</span><span class="sxs-lookup"><span data-stu-id="071f3-131">As of F# 4.1, you can also create `struct` tuples.</span></span>  <span data-ttu-id="071f3-132">이러한도 완벽 하 게 상호 작용도 C# 7/Visual Basic 15 튜플 `struct` 튜플.</span><span class="sxs-lookup"><span data-stu-id="071f3-132">These also interoperate fully with C#7/Visual Basic 15 tuples, which are also `struct` tuples:</span></span>

[!code-fsharp[Tuples](../../samples/snippets/fsharp/tour.fs#L205-L218)]

<span data-ttu-id="071f3-133">반드시 `struct` 튜플은 값 형식, 튜플 참조를 암시적으로 변환할 수 없으므로 또는 그 반대의 경우도 마찬가지입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-133">It's important to note that because `struct` tuples are value types, they cannot be implicitly converted to reference tuples, or vice versa.</span></span>  <span data-ttu-id="071f3-134">참조 및 구조체 튜플 간에 명시적으로 변환 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-134">You must explicitly convert between a reference and struct tuple.</span></span>

## <a name="pipelines-and-composition"></a><span data-ttu-id="071f3-135">파이프라인 및 컴퍼지션</span><span class="sxs-lookup"><span data-stu-id="071f3-135">Pipelines and Composition</span></span>

<span data-ttu-id="071f3-136">와 같은 연산자를 파이프할 `|>` F#의 데이터를 처리 하는 경우 널리 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-136">Pipe operators such as `|>` are used extensively when processing data in F#.</span></span> <span data-ttu-id="071f3-137">이러한 연산자는 "파이프라인" 함수의 유연한 방식으로 설정할 수 있도록 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-137">These operators are functions that allow you to establish "pipelines" of functions in a flexible manner.</span></span> <span data-ttu-id="071f3-138">다음 예제에서는 간단한 기능 파이프라인 빌드를 이러한 연산자를 활용할 수는 어떻게 과정을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-138">The following example walks through how you can take advantage of these operators to build a simple functional pipeline:</span></span>

[!code-fsharp[Pipelines](../../samples/snippets/fsharp/tour.fs#L227-L282)]

<span data-ttu-id="071f3-139">앞의 예제 수 목록 처리 함수를 첫 번째 클래스 함수를 포함 하 여 F#의 많은 기능을 사용 하 고 [부분 응용 프로그램](language-reference/functions/index.md#partial-application-of-arguments)합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-139">The previous sample made use of many features of F#, including list processing functions, first-class functions, and [partial application](language-reference/functions/index.md#partial-application-of-arguments).</span></span> <span data-ttu-id="071f3-140">각 이러한 개념에 대 한 심층적 이해가, 다소 고급 될 수 있지만 명확 해야 하는 방법을 쉽게 파이프라인을 빌드할 때 데이터를 처리 하는 데 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-140">Although a deep understanding of each of those concepts can become somewhat advanced, it should be clear how easily functions can be used to process data when building pipelines.</span></span>

## <a name="lists-arrays-and-sequences"></a><span data-ttu-id="071f3-141">목록, 배열 및 시퀀스</span><span class="sxs-lookup"><span data-stu-id="071f3-141">Lists, Arrays, and Sequences</span></span>

<span data-ttu-id="071f3-142">목록, 배열 및 시퀀스는 F# 핵심 라이브러리의 세 가지 기본 컬렉션 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-142">Lists, Arrays, and Sequences are three primary collection types in the F# core library.</span></span>

<span data-ttu-id="071f3-143">[나열](language-reference/lists.md) 은 정렬 된, 변경할 수 없는 컬렉션 같은 형식의 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-143">[Lists](language-reference/lists.md) are ordered, immutable collections of elements of the same type.</span></span>  <span data-ttu-id="071f3-144">즉, 많은 경우 열거형 하지만 임의 액세스 및 연결에 대 한 잘못 된 선택에 대 한 의미는 단일 연결 목록의 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-144">They are singly-linked lists, which means they are meant for enumeration, but a poor choice for random access and concatenation if they're large.</span></span>  <span data-ttu-id="071f3-145">일반적으로 사용 하지 않는 단일 연결 목록을 나타내는 목록 다른 인기 있는 언어로 나열 달리이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-145">This in contrast to Lists in other popular languages, which typically do not use a singly-linked list to represent Lists.</span></span>

[!code-fsharp[Lists](../../samples/snippets/fsharp/tour.fs#L309-L359)]

<span data-ttu-id="071f3-146">[배열](language-reference/arrays.md) 은 고정 크기 *변경할 수 있는* 형식이 같은 요소의 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-146">[Arrays](language-reference/arrays.md) are fixed-size, *mutable* collections of elements of the same type.</span></span>  <span data-ttu-id="071f3-147">요소의 빠른 임의 액세스를 지원 하며 F# 목록에서는 방금 연속 된 메모리 블록을 이기 때문에 보다 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-147">They support fast random access of elements, and are faster than F# lists because they are just contiguous blocks of memory.</span></span>

[!code-fsharp[Arrays](../../samples/snippets/fsharp/tour.fs#L368-L407)]

<span data-ttu-id="071f3-148">[시퀀스](language-reference/sequences.md) 동일한 형식의 모든 요소를 논리적으로 연속 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-148">[Sequences](language-reference/sequences.md) are a logical series of elements, all of the same type.</span></span>  <span data-ttu-id="071f3-149">이들은 목록과 배열 되는 모든 논리적 일련의 요소에 "보기"의 수는 보다 일반적인 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-149">These are a more general type than Lists and Arrays, capable of being your "view" into any logical series of elements.</span></span>  <span data-ttu-id="071f3-150">또한 될까요 될 수 있으므로 ***지연***, 즉, 요소는 필요할 때에 계산할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-150">They also stand out because they can be ***lazy***, which means that elements can be computed only when they are needed.</span></span>

[!code-fsharp[Sequences](../../samples/snippets/fsharp/tour.fs#L418-L452)]

## <a name="recursive-functions"></a><span data-ttu-id="071f3-151">재귀 함수</span><span class="sxs-lookup"><span data-stu-id="071f3-151">Recursive Functions</span></span>

<span data-ttu-id="071f3-152">컬렉션 또는 요소의 시퀀스로 처리는 사용 하 여 일반적으로 수행 됩니다 [재귀](language-reference/functions/index.md#recursive-functions) F#에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-152">Processing collections or sequences of elements is typically done with [recursion](language-reference/functions/index.md#recursive-functions) in F#.</span></span>  <span data-ttu-id="071f3-153">F#에 루프 및 명령형 프로그래밍에 대 한 지원으로 재귀는 정확성을 보장 하기 위해 더 쉽기 때문에 기본 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-153">Although F# has support for loops and imperative programming, recursion is preferred because it is easier to guarantee correctness.</span></span>

> [!NOTE]
> <span data-ttu-id="071f3-154">다음 예제에서는 패턴 일치를 통해 사용 된 `match` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-154">The following example makes use of the pattern matching via the `match` expression.</span></span>  <span data-ttu-id="071f3-155">이 문서의 뒷부분에서이 기본 구문을 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-155">This fundamental construct is covered later in this article.</span></span>

[!code-fsharp[RecursiveFunctions](../../samples/snippets/fsharp/tour.fs#L461-L500)]

<span data-ttu-id="071f3-156">F# 또한가 마무리 호출 최적화에 대 한 전체 지원 있습니다 빠른 루프 구문으로는 재귀 호출을 최적화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-156">F# also has full support for Tail Call Optimization, which is a way to optimize recursive calls so that they are just as fast as a loop construct.</span></span>

## <a name="record-and-discriminated-union-types"></a><span data-ttu-id="071f3-157">레코드와 구별 된 공용 구조체 형식</span><span class="sxs-lookup"><span data-stu-id="071f3-157">Record and Discriminated Union Types</span></span>

<span data-ttu-id="071f3-158">레코드 및 공용 구조체 형식을 F# 코드에 사용 되는 두 가지 기본 데이터 형식이 되며 일반적으로 가장 좋은 방법은 F# 프로그램에서 데이터를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-158">Record and Union types are two fundamental data types used in F# code, and are generally the best way to represent data in an F# program.</span></span>  <span data-ttu-id="071f3-159">이렇게 하면 해당 클래스와 유사 다른 언어로, 주요 차이점 중 하나 이지만 구조적 같음 의미 체계를가지고 있다고 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-159">Although this makes them similar to classes in other languages, one of their primary differences is that they have structural equality semantics.</span></span>  <span data-ttu-id="071f3-160">즉, "고유 하 게" 비교할 수는 같음 간단-다른 같으면 하나 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-160">This means that they are "natively" comparable and equality is straightforward - just check if one is equal to the other.</span></span>

<span data-ttu-id="071f3-161">[레코드](language-reference/records.md) 선택적 멤버 (예: 메서드)를 사용 하 여 명명 된 값의 집계 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-161">[Records](language-reference/records.md) are an aggregate of named values, with optional members (such as methods).</span></span>  <span data-ttu-id="071f3-162">C# 또는 Java에 익숙한 경우 다음이 있어야 Poco 또는 Pojo-비슷한 의례 줄이고 구조적 일치성이 포함 된 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-162">If you're familiar with C# or Java, then these should feel similar to POCOs or POJOs - just with structural equality and less ceremony.</span></span>

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L507-L559)]

<span data-ttu-id="071f3-163">F# 4.1을 기준으로 나타낼 수도 있습니다 레코드는 `struct`s입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-163">As of F# 4.1, you can also represent Records as `struct`s.</span></span>  <span data-ttu-id="071f3-164">사용 하 여 `[<Struct>]` 특성:</span><span class="sxs-lookup"><span data-stu-id="071f3-164">This is done with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Records](../../samples/snippets/fsharp/tour.fs#L561-L568)]

<span data-ttu-id="071f3-165">[구별 된 공용 구조체 (DUs)](language-reference/discriminated-unions.md) 명명 된 폼의 경우 숫자가 될 수 있는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-165">[Discriminated Unions (DUs)](language-reference/discriminated-unions.md) are values which could be a number of named forms or cases.</span></span>  <span data-ttu-id="071f3-166">데이터 형식에 저장 된 여러 고유 값 중 하나일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-166">Data stored in the type can be one of several distinct values.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L575-L631)]

<span data-ttu-id="071f3-167">DUs로 이용할 수 있습니다 *단일 사례 구별 된 공용 구조체*기본 형식을 통해 모델링 되는 도메인과 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-167">You can also use DUs as *Single-Case Discriminated Unions*, to help with domain modeling over primitive types.</span></span>  <span data-ttu-id="071f3-168">종종, 문자열 및 다른 기본 형식과 무언가 나타내는 데 사용 됩니다 하 고 특정 의미를 지정 하므로 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-168">Often times, strings and other primitive types are used to represent something, and are thus given a particular meaning.</span></span>  <span data-ttu-id="071f3-169">그러나 기본 데이터 표현의 실수로 잘못 된 값을 할당할 때 발생할 수 있습니다!</span><span class="sxs-lookup"><span data-stu-id="071f3-169">However, using only the primitive representation of the data can result in mistakenly assigning an incorrect value!</span></span>  <span data-ttu-id="071f3-170">각 유형의 단일 사례 공용 구조체의 고유 정보를 나타내는이 시나리오의 정확성을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-170">Representing each type of information as a distinct single-case union can enforce correctness in this scenario.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L633-L654)]

<span data-ttu-id="071f3-171">에 단일 사례 구별 된 공용 구조체, 기본 값을 가져오려면 위의 샘플에서 보여 주는 것 처럼 명시적으로 unwrap 해야 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-171">As the above sample demonstrates, to get the underlying value in a single-case Discriminated Union, you must explicitly unwrap it.</span></span>

<span data-ttu-id="071f3-172">또한 DUs 기능도 재귀 정의 트리 및 본질적으로 재귀적 데이터를 쉽게 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-172">Additionally, DUs also support recursive definitions, allowing you to easily represent trees and inherently recursive data.</span></span>  <span data-ttu-id="071f3-173">예를 들어 다음과 같습니다 사용 하 여 이진 검색 트리를 표시 하는 방법 `exists` 및 `insert` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-173">For example, here's how you can represent a Binary Search Tree with `exists` and `insert` functions.</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L656-L683)]

<span data-ttu-id="071f3-174">DUs 데이터 형식에서 트리의 재귀 구조를 나타낼 수 있으므로이 재귀 구조에서 작동 간단 하 고 정확성을 보장 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-174">Because DUs allow you to represent the recursive structure of the tree in the data type, operating on this recursive structure is straightforward and guarantees correctness.</span></span>  <span data-ttu-id="071f3-175">또한 아래와 같이 패턴 일치에 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-175">It is also supported in pattern matching, as shown below.</span></span>

<span data-ttu-id="071f3-176">또한 DUs로 나타낼 수 있습니다 `struct`와 s는 `[<Struct>]` 특성:</span><span class="sxs-lookup"><span data-stu-id="071f3-176">Additionally, you can represent DUs as `struct`s with the `[<Struct>]` attribute:</span></span>

[!code-fsharp[Unions](../../samples/snippets/fsharp/tour.fs#L685-L696)]

<span data-ttu-id="071f3-177">그러나 두 가지 주요 작업을 수행할 때는 염두에:</span><span class="sxs-lookup"><span data-stu-id="071f3-177">However, there are two key things to keep in mind when doing so:</span></span>

1. <span data-ttu-id="071f3-178">DU 구조체를 재귀적으로 정의 일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-178">A struct DU cannot be recursively-defined.</span></span>
2. <span data-ttu-id="071f3-179">DU 구조체에는 각 해당 사례에 대 한 고유한 이름을 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-179">A struct DU must have unique names for each of its cases.</span></span>

<span data-ttu-id="071f3-180">위의 따르지 컴파일 오류가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-180">Failure to follow the above will result in a compilation error.</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="071f3-181">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="071f3-181">Pattern Matching</span></span>

<span data-ttu-id="071f3-182">[일치 패턴](language-reference/pattern-matching.md) 기능은 F# 언어는 F# 형식에서 작동 하는 것에 대 한 정확성을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-182">[Pattern Matching](language-reference/pattern-matching.md) is the F# language feature which enables correctness for operating on F# types.</span></span>  <span data-ttu-id="071f3-183">위의 샘플에서 이와 매우 많은 `match x with ...` 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-183">In the above samples, you probably noticed quite a bit of `match x with ...` syntax.</span></span>  <span data-ttu-id="071f3-184">이 구조를 사용 하면 컴파일러에 일치 하는 철저 한 패턴을 통해 데이터 형식을 사용 하는 경우 모든 가능한 사례에 대 한 계정 수를 적용할 데이터 형식의 "모양"를 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-184">This construct allows the compiler, which can understand the "shape" of data types, to force you to account for all possible cases when using a data type through what is known as Exhaustive Pattern Matching.</span></span>  <span data-ttu-id="071f3-185">올바른지, 매우 강력한 이며 컴파일 시간에 런타임 문제가 일반적으로 될 항목이 "리프트"를 영리 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-185">This is incredibly powerful for correctness, and can be cleverly used to "lift" what would normally be a runtime concern into compile-time.</span></span>

[!code-fsharp[PatternMatching](../../samples/snippets/fsharp/tour.fs#L705-L742)]

<span data-ttu-id="071f3-186">사용 하는 것을 알았을 것은 `_` 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-186">Something you may have noticed is the use of the `_` pattern.</span></span>  <span data-ttu-id="071f3-187">이 [와일드 카드 패턴](language-reference/pattern-matching.md#wildcard-pattern), "신경을 어떤 대상을" 설명할 방법이 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-187">This is known as the [Wildcard Pattern](language-reference/pattern-matching.md#wildcard-pattern), which is a way of saying "I don't care what something is".</span></span>  <span data-ttu-id="071f3-188">실수로 철저 한 패턴 일치를 무시 하 고 더 이상 사용 하 여 주의 하지 않으면 컴파일 타임 사항이에서 이점을 얻을 수 편리 하기는 하지만 `_`합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-188">Although convenient, you can accidentally bypass Exhaustive Pattern Matching and no longer benefit from compile-time enforcements if you aren't careful in using `_`.</span></span>  <span data-ttu-id="071f3-189">분해 된 형식의 특정 부분에 신경 때 가장 적합 하면 패턴 일치 식의에서 의미 있는 모든 사례는 열거 된 경우 일치 또는 마지막 절을 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-189">It is best used when you don't care about certain pieces of a decomposed type when pattern matching, or the final clause when you have enumerated all meaningful cases in a pattern matching expression.</span></span>

<span data-ttu-id="071f3-190">[활성 패턴](language-reference/active-patterns.md) 패턴 일치를 사용 하는 다른 강력한 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-190">[Active Patterns](language-reference/active-patterns.md) are another powerful construct to use with pattern matching.</span></span>  <span data-ttu-id="071f3-191">그러면 패턴 일치 호출 사이트에서 분해 하는 사용자 지정 양식, 입력된 데이터를 분할할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-191">They allow you to partition input data into custom forms, decomposing them at the pattern match call site.</span></span>  <span data-ttu-id="071f3-192">또한 매개 변수화 할 수, 있으므로 다음 파티션 함수로 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-192">They can also be parameterized, thus allowing to define the partition as a function.</span></span>  <span data-ttu-id="071f3-193">활성 패턴을 지원 하기 위해 이전 예제를 확장 합니다. 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-193">Expanding the previous example to support Active Patterns looks something like this:</span></span>

[!code-fsharp[ActivePatterns](../../samples/snippets/fsharp/tour.fs#L764-L786)]

## <a name="optional-types"></a><span data-ttu-id="071f3-194">선택적 형식</span><span class="sxs-lookup"><span data-stu-id="071f3-194">Optional Types</span></span>

<span data-ttu-id="071f3-195">구별 된 공용 구조체 유형의 특수 경우는 옵션 종류를 F# 핵심 라이브러리의 일부는 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-195">One special case of Discriminated Union types is the Option Type, which is so useful that it's a part of the F# core library.</span></span>

<span data-ttu-id="071f3-196">[옵션 형식](language-reference/options.md) 는 두 가지 경우 중 하나를 나타내는 형식: 값 또는 전혀 아무 작업도 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-196">[The Option Type](language-reference/options.md) is a type which represents one of two cases: a value, or nothing at all.</span></span>  <span data-ttu-id="071f3-197">값 수 또는 특정 작업으로 나타나지 않을 수 있는 모든 시나리오에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-197">It is used in any scenario where a value may or may not result from a particular operation.</span></span>  <span data-ttu-id="071f3-198">이 강제로 수행 런타임 별로 중요 하지 않고 컴파일 시간 문제가 있으므로 두 경우에 대 한 계정 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-198">This then forces you to account for both cases, making it a compile-time concern rather than a runtime concern.</span></span>  <span data-ttu-id="071f3-199">Api에서 자주 사용 되 이러한 위치 `null` 에 대해 걱정할 필요가 없도록 아무것도 대신 나타내는 데 사용 됩니다 `NullReferenceException` 대부분에서입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-199">These are often used in APIs where `null` is used to represent "nothing" instead, thus eliminating the need to worry about `NullReferenceException` in many circumstances.</span></span>

[!code-fsharp[Options](../../samples/snippets/fsharp/tour.fs#L789-L814)]

## <a name="units-of-measure"></a><span data-ttu-id="071f3-200">측정 단위</span><span class="sxs-lookup"><span data-stu-id="071f3-200">Units of Measure</span></span>

<span data-ttu-id="071f3-201">F#의 형식 시스템의 고유한 특징 중 하나는 측정 단위를 통해 숫자 리터럴에 대 한 컨텍스트를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-201">One unique feature of F#'s type system is the ability to provide context for numeric literals through Units of Measure.</span></span>

<span data-ttu-id="071f3-202">[측정 단위](language-reference/units-of-measure.md) 미터로 등의 단위를 숫자 형식에 연결할 수 있도록 및 있는 함수에서 작업을 수행 숫자 리터럴 대신 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-202">[Units of Measure](language-reference/units-of-measure.md) allow you to associate a numeric type to a unit, such as Meters, and have functions perform work on units rather than numeric literals.</span></span>  <span data-ttu-id="071f3-203">그러면 컴파일러가 특정 컨텍스트에서 의미가에 전달 된 숫자 리터럴 형식에 해당 종류의 작업을 사용 하 여 연결 된 런타임 오류를 없앰으로써 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-203">This enables the compiler to verify that the types of numeric literals passed in make sense under a certain context, thus eliminating runtime errors associated with that kind of work.</span></span>

[!code-fsharp[UnitsOfMeasure](../../samples/snippets/fsharp/tour.fs#L817-L842)]

<span data-ttu-id="071f3-204">F# 핵심 라이브러리는 많은 SI 단위 유형 및 변환 단위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-204">The F# Core library defines many SI unit types and unit conversions.</span></span>  <span data-ttu-id="071f3-205">자세한 내용은 체크 아웃 합니다 [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-205">To learn more, check out the [Microsoft.FSharp.Data.UnitSystems.SI Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.data.unitsystems.si-namespace-%5bfsharp%5d).</span></span>

## <a name="classes-and-interfaces"></a><span data-ttu-id="071f3-206">클래스 및 인터페이스</span><span class="sxs-lookup"><span data-stu-id="071f3-206">Classes and Interfaces</span></span>

<span data-ttu-id="071f3-207">F#에.NET 클래스에 대 한 전체 지원을 [인터페이스](language-reference/interfaces.md), [추상 클래스](language-reference/abstract-classes.md)합니다 [상속](language-reference/inheritance.md)등.</span><span class="sxs-lookup"><span data-stu-id="071f3-207">F# also has full support for .NET classes, [Interfaces](language-reference/interfaces.md), [Abstract Classes](language-reference/abstract-classes.md), [Inheritance](language-reference/inheritance.md), and so on.</span></span>

<span data-ttu-id="071f3-208">[클래스](language-reference/classes.md) .NET 개체를 나타내는 형식인 속성, 메서드 및 이벤트를 사용할 수 있는 해당 [멤버](language-reference/members/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-208">[Classes](language-reference/classes.md) are types that represent .NET objects, which can have properties, methods, and events as its [Members](language-reference/members/index.md).</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L845-L880)]

<span data-ttu-id="071f3-209">제네릭 클래스 정의 매우 간단 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-209">Defining generic classes is also very straightforward.</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L883-L908)]

<span data-ttu-id="071f3-210">인터페이스를 구현 하려면 사용할 수 있습니다 `interface ... with` 구문 요소나 [개체 식](language-reference/object-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-210">To implement an Interface, you can use either `interface ... with` syntax or an [Object Expression](language-reference/object-expressions.md).</span></span>

[!code-fsharp[Classes](../../samples/snippets/fsharp/tour.fs#L911-L934)]

## <a name="which-types-to-use"></a><span data-ttu-id="071f3-211">사용 형식</span><span class="sxs-lookup"><span data-stu-id="071f3-211">Which Types to Use</span></span>

<span data-ttu-id="071f3-212">중요 한 질문에 잠재 고객 클래스, 레코드, 구분 된 공용 구조체 및 튜플의 존재 여부: 사용 해야 하는?</span><span class="sxs-lookup"><span data-stu-id="071f3-212">The presence of Classes, Records, Discriminated Unions, and Tuples leads to an important question: which should you use?</span></span>  <span data-ttu-id="071f3-213">요소와 마찬가지로 대부분의 상황에서에서 답변 상황에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-213">Like most everything in life, the answer depends on your circumstances.</span></span>

<span data-ttu-id="071f3-214">튜플 함수에서 여러 값을 반환 하 고 임시 집계 값을 사용 하 여 자체 값으로 탁월 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-214">Tuples are great for returning multiple values from a function, and using an ad-hoc aggregate of values as a value itself.</span></span>

<span data-ttu-id="071f3-215">레코드는 "의 다음 단계인" 튜플, 레이블 및 선택적 멤버에 대 한 지원 이라는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-215">Records are a "step up" from Tuples, having named labels and support for optional members.</span></span>  <span data-ttu-id="071f3-216">이러한 옵션은 데이터 전송 중에 프로그램을 통해 격식이 표현을 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-216">They are great for a low-ceremony representation of data in-transit through your program.</span></span>  <span data-ttu-id="071f3-217">구조적 같음에 있기 때문에 비교를 사용 하 여 쉽게 사용할 수는 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-217">Because they have structural equality, they are easy to use with comparison.</span></span>

<span data-ttu-id="071f3-218">구별 된 공용 구조체는 여러 가지 이지만 핵심 혜택에 대 한 모든 가능한 "모양" 데이터를 가질 수 있는 계정에 패턴 일치와 함께에서 사용 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-218">Discriminated Unions have many uses, but the core benefit is to be able to utilize them in conjunction with Pattern Matching to account for all possible "shapes" that a data can have.</span></span>  

<span data-ttu-id="071f3-219">클래스는 상당히 많은 정보를 나타내는 한도 기능에 해당 정보를 연결 해야 하는 등의 이유로 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-219">Classes are great for a huge number of reasons, such as when you need to represent information and also tie that information to functionality.</span></span>  <span data-ttu-id="071f3-220">일반적으로 일부 데이터를 개념적으로 관련이 있는 기능이 클래스 및 개체 지향 프로그래밍의 원리를 사용 하 여 경우에 큰 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-220">As a rule of thumb, when you have functionality which is conceptually tied to some data, using Classes and the principles of Object-Oriented Programming is a big benefit.</span></span>  <span data-ttu-id="071f3-221">클래스는 또한 기본 데이터 형식을 C# 및 Visual Basic의 경우와 상호 작용할 때 거의 모든 항목에 대 한 클래스를 사용 하는 이러한 언어입니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-221">Classes are also the preferred data type when interoperating with C# and Visual Basic, as these languages use classes for nearly everything.</span></span>

## <a name="next-steps"></a><span data-ttu-id="071f3-222">다음 단계</span><span class="sxs-lookup"><span data-stu-id="071f3-222">Next Steps</span></span>

<span data-ttu-id="071f3-223">지금까지 살펴본 언어의 주요 기능 중 일부는 이제 첫 번째 F# 프로그램 작성을 준비 해야 합니다!</span><span class="sxs-lookup"><span data-stu-id="071f3-223">Now that you've seen some of the primary features of the language, you should be ready to write your first F# programs!</span></span>  <span data-ttu-id="071f3-224">체크 아웃 [Getting Started](tutorials/getting-started/index.md) 에 개발 환경을 설정 하 여 일부 코드를 작성 하는 방법을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-224">Check out [Getting Started](tutorials/getting-started/index.md) to learn how to set up your development environment and write some code.</span></span>

<span data-ttu-id="071f3-225">자세히 학습을 위한 다음 단계를 원하는 수 있지만 것이 좋습니다 [에 함수형 프로그래밍 소개 F# ](introduction-to-functional-programming/index.md) 핵심 함수형 프로그래밍 개념에 익숙하지 가져오려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-225">The next steps for learning more can be whatever you like, but we recommend [Introduction to Functional Programming in F#](introduction-to-functional-programming/index.md) to get comfortable with core Functional Programming concepts.</span></span>  <span data-ttu-id="071f3-226">이러한 강력한 프로그램 F# 빌드에 필수적인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="071f3-226">These will be essential in building robust programs in F#.</span></span>

<span data-ttu-id="071f3-227">또한 체크 아웃 합니다 [F# 언어 참조](language-reference/index.md) F#에서 광범위 한 개념적 콘텐츠를 보려면.</span><span class="sxs-lookup"><span data-stu-id="071f3-227">Also, check out the [F# Language Reference](language-reference/index.md) to see a comprehensive collection of conceptual content on F#.</span></span>
