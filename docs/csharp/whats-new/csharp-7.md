---
title: C# 7.0의 새로운 기능 - C# 가이드
description: C# 언어 버전 7.0의 새로운 기능을 살펴봅니다.
ms.date: 02/20/2019
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: a6ac5c00ceb2ce8e5e56e2a86a8cde937d5108e2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77448636"
---
# <a name="whats-new-in-c-70"></a><span data-ttu-id="cfc1b-103">C# 7.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="cfc1b-103">What's new in C# 7.0</span></span>

<span data-ttu-id="cfc1b-104">C# 7.0에서는 C# 언어에 많은 새로운 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-104">C# 7.0 adds a number of new features to the C# language:</span></span>

- [<span data-ttu-id="cfc1b-105">`out` 변수</span><span class="sxs-lookup"><span data-stu-id="cfc1b-105">`out` variables</span></span>](#out-variables)
  - <span data-ttu-id="cfc1b-106">`out` 값을 사용되는 메서드에 대한 인수로 인라인으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-106">You can declare `out` values inline as arguments to the method where they're used.</span></span>
- [<span data-ttu-id="cfc1b-107">튜플</span><span class="sxs-lookup"><span data-stu-id="cfc1b-107">Tuples</span></span>](#tuples)
  - <span data-ttu-id="cfc1b-108">여러 public 필드가 포함된 간단한 명명되지 않은 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-108">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="cfc1b-109">컴파일러 및 IDE 도구는 이러한 형식의 의미 체계를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-109">Compilers and IDE tools understand the semantics of these types.</span></span>
- [<span data-ttu-id="cfc1b-110">삭제</span><span class="sxs-lookup"><span data-stu-id="cfc1b-110">Discards</span></span>](#discards)
  - <span data-ttu-id="cfc1b-111">삭제는 할당된 값에 신경 쓰지 않을 때 할당에서 사용되는 임시 쓰기 전용 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-111">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="cfc1b-112">매개 변수는 `out` 매개 변수를 사용하여 메서드를 호출할 때뿐만 아니라 튜플 및 사용자 정의 형식을 분해할 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-112">They're most useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
- [<span data-ttu-id="cfc1b-113">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="cfc1b-113">Pattern Matching</span></span>](#pattern-matching)
  - <span data-ttu-id="cfc1b-114">임의 형식 및 해당 형식의 멤버 값에 따라 분기 논리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-114">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
- [<span data-ttu-id="cfc1b-115">`ref` local 및 return</span><span class="sxs-lookup"><span data-stu-id="cfc1b-115">`ref` locals and returns</span></span>](#ref-locals-and-returns)
  - <span data-ttu-id="cfc1b-116">메서드 지역 변수와 반환 값은 다른 스토리지에 대한 참조일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-116">Method local variables and return values can be references to other storage.</span></span>
- [<span data-ttu-id="cfc1b-117">로컬 함수</span><span class="sxs-lookup"><span data-stu-id="cfc1b-117">Local Functions</span></span>](#local-functions)
  - <span data-ttu-id="cfc1b-118">함수를 다른 함수 내부에 중첩하여 범위와 표시 여부를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-118">You can nest functions inside other functions to limit their scope and visibility.</span></span>
- [<span data-ttu-id="cfc1b-119">추가 식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="cfc1b-119">More expression-bodied members</span></span>](#more-expression-bodied-members)
  - <span data-ttu-id="cfc1b-120">식을 사용하여 작성할 수 있는 멤버 목록이 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-120">The list of members that can be authored using expressions has grown.</span></span>
- [<span data-ttu-id="cfc1b-121">`throw` 식</span><span class="sxs-lookup"><span data-stu-id="cfc1b-121">`throw` Expressions</span></span>](#throw-expressions)
  - <span data-ttu-id="cfc1b-122">`throw` 문이었기 때문에 이전에 허용되지 않은 코드 구문에서 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-122">You can throw exceptions in code constructs that previously weren't allowed because `throw` was a statement.</span></span>
- [<span data-ttu-id="cfc1b-123">일반화된 비동기 반환 형식</span><span class="sxs-lookup"><span data-stu-id="cfc1b-123">Generalized async return types</span></span>](#generalized-async-return-types)
  - <span data-ttu-id="cfc1b-124">`async` 한정자를 사용하여 선언된 메서드는 `Task` 및 `Task<T>` 외에 다른 형식을 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-124">Methods declared with the `async` modifier can return other types in addition to `Task` and `Task<T>`.</span></span>
- [<span data-ttu-id="cfc1b-125">숫자 리터럴 구문 개선 사항</span><span class="sxs-lookup"><span data-stu-id="cfc1b-125">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
  - <span data-ttu-id="cfc1b-126">새로운 토큰으로 숫자 상수의 가독성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-126">New tokens improve readability for numeric constants.</span></span>

<span data-ttu-id="cfc1b-127">이 문서의 나머지 부분에서는 해당 기능에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-127">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="cfc1b-128">각 기능의 배경과 원리를 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-128">For each feature, you'll learn the reasoning behind it.</span></span> <span data-ttu-id="cfc1b-129">구문을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-129">You'll learn the syntax.</span></span> <span data-ttu-id="cfc1b-130">`dotnet try` 글로벌 도구를 사용하여 환경에서 다음과 같은 기능을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-130">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="cfc1b-131">[dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) 글로벌 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-131">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="cfc1b-132">[dotnet/try-samples](https://github.com/dotnet/try-samples) 리포지토리를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-132">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="cfc1b-133">현재 디렉터리를 *try-samples* 리포지토리의 *csharp7* 하위 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-133">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="cfc1b-134">`dotnet try`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-134">Run `dotnet try`.</span></span>

## <a name="out-variables"></a><span data-ttu-id="cfc1b-135">`out` 변수</span><span class="sxs-lookup"><span data-stu-id="cfc1b-135">`out` variables</span></span>

<span data-ttu-id="cfc1b-136">`out` 매개 변수를 지원하는 기존 구문이 이 버전에서 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-136">The existing syntax that supports `out` parameters has been improved in this version.</span></span> <span data-ttu-id="cfc1b-137">이제 개별 선언 문을 작성하는 대신 메서드 호출의 인수 목록에서 `out` 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-137">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="cfc1b-138">위에 나와 있는 대로 쉽게 구별할 수 있도록 `out` 변수의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-138">You may want to specify the type of the `out` variable for clarity, as shown above.</span></span> <span data-ttu-id="cfc1b-139">그러나 이 언어는 암시적 형식 지역 변수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-139">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- <span data-ttu-id="cfc1b-140">코드를 읽기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-140">The code is easier to read.</span></span>
  - <span data-ttu-id="cfc1b-141">위의 다른 줄이 아니라 사용하는 위치에서 out 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-141">You declare the out variable where you use it, not on another line above.</span></span>
- <span data-ttu-id="cfc1b-142">초기 값을 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-142">No need to assign an initial value.</span></span>
  - <span data-ttu-id="cfc1b-143">메서드 호출에서 사용되는 위치에 `out` 변수를 선언하여 변수가 할당되기 전에 실수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-143">By declaring the `out` variable where it's used in a method call, you can't accidentally use it before it is assigned.</span></span>

## <a name="tuples"></a><span data-ttu-id="cfc1b-144">튜플</span><span class="sxs-lookup"><span data-stu-id="cfc1b-144">Tuples</span></span>

<span data-ttu-id="cfc1b-145">C#에서는 디자인 의도를 설명하는 데 사용되는 클래스 및 구조체에 대한 다양한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-145">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="cfc1b-146">하지만 다양한 구문에는 이점이 거의 없는데 추가 작업이 필요한 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-146">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="cfc1b-147">일반적으로 두 개 이상의 데이터 요소가 포함된 간단한 구조체가 필요한 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-147">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="cfc1b-148">이러한 시나리오를 지원하기 위해 *튜플*이 C#에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-148">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="cfc1b-149">튜플은 데이터 멤버를 나타내는 여러 필드가 포함된 간단한 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-149">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span>
<span data-ttu-id="cfc1b-150">필드는 유효성이 검사되지 않고 자체 메서드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-150">The fields aren't validated, and you can't define your own methods</span></span>

> [!NOTE]
> <span data-ttu-id="cfc1b-151">튜플은 C# 7.0 이전부터 사용할 수 있었지만 비효율적이었고 언어 지원이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-151">Tuples were available before C# 7.0, but they were inefficient and had no language support.</span></span>
> <span data-ttu-id="cfc1b-152">즉, 튜플 요소는 `Item1`, `Item2` 등으로만 참조될 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-152">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="cfc1b-153">C# 7.0은 새롭고 보다 효율적인 튜플 유형을 사용하여 튜플의 필드에 대해 의미론적 이름을 사용할 수 있는 튜플에 대한 언어 지원을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-153">C# 7.0 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="cfc1b-154">각 멤버에 값을 할당하고 필요에 따라 튜플의 각 멤버에 의미 체계 이름을 입력하여 튜플을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-154">You can create a tuple by assigning a value to each member, and optionally providing semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

<span data-ttu-id="cfc1b-155">`namedLetters` 튜플에는 `Alpha` 및 `Beta`라는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-155">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="cfc1b-156">이러한 이름은 컴파일 시간에만 존재하며 런타임 시 리플렉션을 통해 튜플을 검사하는 경우 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-156">Those names exist only at compile time and aren't preserved, for example when inspecting the tuple using reflection at runtime.</span></span>

<span data-ttu-id="cfc1b-157">튜플 할당에서 할당의 오른쪽에 필드의 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-157">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="cfc1b-158">메서드에서 반환된 튜플의 멤버를 패키지 해제하려는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-158">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="cfc1b-159">이 작업을 수행하려면 튜플에서 각 값에 대한 개별 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-159">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="cfc1b-160">이 패키지 해제 작업을 튜플 *분해*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-160">This unpackaging is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

<span data-ttu-id="cfc1b-161">.NET에 있는 형식에 대한 비슷한 분해를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-161">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="cfc1b-162">`Deconstruct` 메서드를 클래스의 멤버로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-162">You write a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="cfc1b-163">해당 `Deconstruct` 메서드는 추출하려는 각 속성에 대한 `out` 인수 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-163">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="cfc1b-164">`X` 및 `Y` 좌표를 추출하는 분해자 메서드를 제공하는 이 `Point` 클래스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-164">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

<span data-ttu-id="cfc1b-165">튜플에 `Point`을 할당하여 개별 필드를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-165">You can extract the individual fields by assigning a `Point` to a tuple:</span></span>

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="cfc1b-166">[튜플 문서](../tuples.md)에서 튜플에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-166">You can learn more in depth about tuples in the [tuples article](../tuples.md).</span></span>

## <a name="discards"></a><span data-ttu-id="cfc1b-167">버림</span><span class="sxs-lookup"><span data-stu-id="cfc1b-167">Discards</span></span>

<span data-ttu-id="cfc1b-168">종종 튜플을 분해하거나 `out` 매개 변수로 메서드를 호출할 때 값을 신경 쓰지 않고 사용하지 않을 변수를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-168">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="cfc1b-169">C#은 *버림*에 대한 지원을 추가하여 이 시나리오를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-169">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="cfc1b-170">무시는 이름이 `_`(밑줄 문자)인 쓰기 전용 변수입니다. 단일 변수에 버리려는 모든 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-170">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="cfc1b-171">버림은 할당 문과 별도로 분리되는 할당되지 않은 변수와 같습니다. 코드에서 버림을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-171">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="cfc1b-172">다음 시나리오에서는 버림이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-172">Discards are supported in the following scenarios:</span></span>

- <span data-ttu-id="cfc1b-173">튜플이나 사용자 정의 형식을 분해할 때.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-173">When deconstructing tuples or user-defined types.</span></span>
- <span data-ttu-id="cfc1b-174">[out](../language-reference/keywords/out-parameter-modifier.md) 매개 변수로 메서드를 호출할 때.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-174">When calling methods with [out](../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>
- <span data-ttu-id="cfc1b-175">[is](../language-reference/keywords/is.md) 및 [switch](../language-reference/keywords/switch.md) 문을 사용한 패턴 일치 작업에서.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-175">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>
- <span data-ttu-id="cfc1b-176">할당 값을 버림으로 명시적으로 지정할 때 독립 실행형 식별자인 경우.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-176">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="cfc1b-177">다음 예제에서는 서로 다른 2년간의 도시 데이터가 포함된 6 튜플을 반환하는 `QueryCityDataForYears` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-177">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains data for a city for two different years.</span></span> <span data-ttu-id="cfc1b-178">예제의 메서드 호출은 메서드에 의해 반환된 두 개의 채우기 값에만 관련되어 있으므로 튜플을 해체할 때 튜플의 나머지 값을 버림으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-178">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="cfc1b-179">자세한 내용은 [버림](../discards.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-179">For more information, see [Discards](../discards.md).</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="cfc1b-180">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="cfc1b-180">Pattern matching</span></span>

<span data-ttu-id="cfc1b-181">*패턴 일치*는 개체 형식이 아닌 속성에 대한 메서드 디스패치를 구현할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-181">*Pattern matching* is a feature that allows you to implement method dispatch on properties other than the type of an object.</span></span> <span data-ttu-id="cfc1b-182">개체 형식에 따른 메서드 디스패치에 이미 익숙할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-182">You're probably already familiar with method dispatch based on the type of an object.</span></span> <span data-ttu-id="cfc1b-183">개체 기반 프로그래밍에서 가상 및 재정의 메서드는 개체 형식에 따라 메서드 디스패치를 구현하기 위해 언어 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-183">In object-oriented programming, virtual and override methods provide language syntax to implement method dispatching based on an object's type.</span></span> <span data-ttu-id="cfc1b-184">기본 및 파생 클래스는 서로 다른 구현을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-184">Base and Derived classes provide different implementations.</span></span>
<span data-ttu-id="cfc1b-185">패턴 일치 식은 이 개념을 확장하므로 상속 계층 구조를 통해 관련되지 않은 형식 및 데이터 요소에서 비슷한 디스패치 패턴을 쉽게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-185">Pattern matching expressions extend this concept so that you can easily implement similar dispatch patterns for types and data elements that aren't related through an inheritance hierarchy.</span></span>

<span data-ttu-id="cfc1b-186">패턴 일치는 `is` 식과 `switch` 식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-186">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="cfc1b-187">각 식을 통해 개체 및 관련 속성을 검사하여 해당 개체가 검색된 패턴을 충족하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-187">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="cfc1b-188">`when` 키워드를 사용하여 패턴에 대한 추가 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-188">You use the `when` keyword to specify additional rules to the pattern.</span></span>

<span data-ttu-id="cfc1b-189">`is` 패턴 식은 친숙한 [`is` 연산자](../language-reference/keywords/is.md#pattern-matching-with-is)를 확장하여 해당 형식에 대한 개체를 쿼리하고 하나의 명령에서 결과를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-189">The `is` pattern expression extends the familiar [`is` operator](../language-reference/keywords/is.md#pattern-matching-with-is) to query an object about its type and assign the result in one instruction.</span></span> <span data-ttu-id="cfc1b-190">다음 코드는 변수가 `int`인지 검사하고, 그럴 경우 현재 합계에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-190">The following code checks if a variable is an `int`, and if so, adds it to the current sum:</span></span>

```csharp
if (input is int count)
    sum += count;
```

<span data-ttu-id="cfc1b-191">앞서 간단한 예제에서는 `is` 식의 개선 사항을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-191">The preceding small example demonstrates the enhancements to the `is` expression.</span></span> <span data-ttu-id="cfc1b-192">참조 형식뿐만 아니라 값 형식에 대해 테스트할 수 있고, 올바른 형식의 새로운 변수에 성공적인 결과를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-192">You can test against value types as well as reference types, and you can assign the successful result to a new variable of the correct type.</span></span>

<span data-ttu-id="cfc1b-193">switch 일치 식에는 이미 C# 언어의 일부인 `switch` 문에 기반을 둔 친숙한 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-193">The switch match expression has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="cfc1b-194">업데이트된 switch 문에는 몇 가지 새로운 구문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-194">The updated switch statement has several new constructs:</span></span>

- <span data-ttu-id="cfc1b-195">`switch` 식의 관리 형식은 더 이상 정수 형식, `Enum` 형식, `string` 또는 해당 형식 중 하나에 해당하는 nullable 형식으로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-195">The governing type of a `switch` expression is no longer restricted to integral types, `Enum` types, `string`, or a nullable type corresponding to one of those types.</span></span> <span data-ttu-id="cfc1b-196">모든 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-196">Any type may be used.</span></span>
- <span data-ttu-id="cfc1b-197">각 `case` 레이블에서 `switch` 식 형식을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-197">You can test the type of the `switch` expression in each `case` label.</span></span> <span data-ttu-id="cfc1b-198">`is` 식과 마찬가지로 해당 형식에 새 변수를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-198">As with the `is` expression, you may assign a new variable to that type.</span></span>
- <span data-ttu-id="cfc1b-199">`when` 절을 해당 변수의 추가 테스트 조건에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-199">You may add a `when` clause to further test conditions on that variable.</span></span>
- <span data-ttu-id="cfc1b-200">이제 `case` 레이블의 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-200">The order of `case` labels is now important.</span></span> <span data-ttu-id="cfc1b-201">일치하는 첫 번째 분기가 실행됩니다. 다른 분기는 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-201">The first branch to match is executed; others are skipped.</span></span>

<span data-ttu-id="cfc1b-202">다음 코드에서는 이 새로운 기능을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-202">The following code demonstrates these new features:</span></span>

```csharp
public static int SumPositiveNumbers(IEnumerable<object> sequence)
{
    int sum = 0;
    foreach (var i in sequence)
    {
        switch (i)
        {
            case 0:
                break;
            case IEnumerable<int> childSequence:
            {
                foreach(var item in childSequence)
                    sum += (item > 0) ? item : 0;
                break;
            }
            case int n when n > 0:
                sum += n;
                break;
            case null:
                throw new NullReferenceException("Null found in sequence");
            default:
                throw new InvalidOperationException("Unrecognized type");
        }
    }
    return sum;
}
```

- <span data-ttu-id="cfc1b-203">`case 0:`은 친숙한 상수 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-203">`case 0:` is the familiar constant pattern.</span></span>
- <span data-ttu-id="cfc1b-204">`case IEnumerable<int> childSequence:`는 형식 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-204">`case IEnumerable<int> childSequence:` is a type pattern.</span></span>
- <span data-ttu-id="cfc1b-205">`case int n when n > 0:`은 추가 `when` 조건을 포함한 형식 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-205">`case int n when n > 0:` is a type pattern with an additional `when` condition.</span></span>
- <span data-ttu-id="cfc1b-206">`case null:`은 null 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-206">`case null:` is the null pattern.</span></span>
- <span data-ttu-id="cfc1b-207">`default:`는 친숙한 기본 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-207">`default:` is the familiar default case.</span></span>

<span data-ttu-id="cfc1b-208">[C#의 패턴 일치](../pattern-matching.md)에서 패턴 일치에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-208">You can learn more about pattern matching in [Pattern Matching in C#](../pattern-matching.md).</span></span>

## <a name="ref-locals-and-returns"></a><span data-ttu-id="cfc1b-209">Ref local 및 return</span><span class="sxs-lookup"><span data-stu-id="cfc1b-209">Ref locals and returns</span></span>

<span data-ttu-id="cfc1b-210">이 기능을 통해 다른 곳에 정의된 변수에 대한 참조를 사용 및 반환하는 알고리즘이 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-210">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="cfc1b-211">한 가지 예는 큰 매트릭스를 사용하고 특정 특징을 가진 하나의 위치를 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-211">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="cfc1b-212">다음 메서드는 **참조**를 행렬의 해당 스토리지에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-212">The following method returns a **reference** to that storage in the matrix:</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="cfc1b-213">다음 코드에서처럼 반환 값을 `ref`로 선언하고 행렬에서 해당 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-213">You can declare the return value as a `ref` and modify that value in the matrix, as shown in the following code:</span></span>

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

<span data-ttu-id="cfc1b-214">C# 언어에는 `ref` 로컬 및 반환을 잘못 사용하지 않도록 방지하는 몇 가지 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-214">The C# language has several rules that protect you from misusing the `ref` locals and returns:</span></span>

- <span data-ttu-id="cfc1b-215">`ref` 키워드를 메서드 서명 및 메서드의 모든 `return` 문에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-215">You must add the `ref` keyword to the method signature and to all `return` statements in a method.</span></span>
  - <span data-ttu-id="cfc1b-216">그러면 메서드가 메서드 전체에서 참조별로 반환되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-216">That makes it clear the method returns by reference throughout the method.</span></span>
- <span data-ttu-id="cfc1b-217">`ref return`은 값 변수 또는 `ref` 변수에 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-217">A `ref return` may be assigned to a value variable, or a `ref` variable.</span></span>
  - <span data-ttu-id="cfc1b-218">호출자는 반환 값을 복사할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-218">The caller controls whether the return value is copied or not.</span></span> <span data-ttu-id="cfc1b-219">반환 값을 할당할 때 `ref` 한정자를 생략하면 호출자가 스토리지에 대한 참조가 아닌 값의 복사본을 요청한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-219">Omitting the `ref` modifier when assigning the return value indicates that the caller wants a copy of the value, not a reference to the storage.</span></span>
- <span data-ttu-id="cfc1b-220">표준 메서드 반환 값을 `ref` 로컬 변수에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-220">You can't assign a standard method return value to a `ref` local variable.</span></span>
  - <span data-ttu-id="cfc1b-221">이로 인해 `ref int i = sequence.Count();` 같은 문이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-221">That disallows statements like `ref int i = sequence.Count();`</span></span>
- <span data-ttu-id="cfc1b-222">메서드 실행보다 길게 수명이 연장되지 않는 변수에 `ref`를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-222">You can't return a `ref` to a variable whose lifetime doesn't extend beyond the execution of the method.</span></span>
  - <span data-ttu-id="cfc1b-223">즉, 로컬 변수 또는 비슷한 범위의 변수에 참조를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-223">That means you can't return a reference to a local variable or a variable with a similar scope.</span></span>
- <span data-ttu-id="cfc1b-224">`ref` local 및 return은 비동기 메서드와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-224">`ref` locals and returns can't be used with async methods.</span></span>
  - <span data-ttu-id="cfc1b-225">컴파일러는 비동기 메서드가 반환될 때 참조된 변수가 최종 값으로 설정되었는지 여부를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-225">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="cfc1b-226">ref local 및 ref return을 추가하면 값을 복사하거나 역참조 작업을 여러 번 수행하는 경우를 방지하여 더 효율적인 알고리즘이 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-226">The addition of ref locals and ref returns enables algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span>

<span data-ttu-id="cfc1b-227">`ref`를 반환 값에 추가하는 것은 [소스 호환 가능 변경](version-update-considerations.md#source-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-227">Adding `ref` to the return value is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span> <span data-ttu-id="cfc1b-228">기존 코드는 컴파일되지만, 참조 반환 값은 할당 시 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-228">Existing code compiles, but the ref return value is copied when assigned.</span></span> <span data-ttu-id="cfc1b-229">호출자는 반환 값 스토리지를 `ref` 지역 변수로 업데이트하여 반환을 참조로 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-229">Callers must update the storage for the return value to a `ref` local variable to store the return as a reference.</span></span>

<span data-ttu-id="cfc1b-230">자세한 내용은 [ref 키워드](../language-reference/keywords/ref.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-230">For more information, see the [ref keyword](../language-reference/keywords/ref.md) article.</span></span>

## <a name="local-functions"></a><span data-ttu-id="cfc1b-231">로컬 함수</span><span class="sxs-lookup"><span data-stu-id="cfc1b-231">Local functions</span></span>

<span data-ttu-id="cfc1b-232">클래스에 대한 대부분의 디자인에는 한 위치에서만 호출되는 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-232">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="cfc1b-233">이러한 추가 private 메서드는 각 메서드를 작고 집중되게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-233">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="cfc1b-234">*로컬 함수*를 사용하면 다른 메서드의 컨텍스트 내부에서 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-234">*Local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="cfc1b-235">로컬 함수를 통해 클래스 readers는 로컬 메서드가 선언된 컨텍스트에서만 호출된다는 것을 더 쉽게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-235">Local functions make it easier for readers of the class to see that the local method is only called from the context in which it is declared.</span></span>

<span data-ttu-id="cfc1b-236">로컬 함수는 일반적으로 공용 반복기 메서드 및 공용 비동기 메서드에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-236">There are two common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="cfc1b-237">두 메서드 형식 모두 프로그래머가 예상한 것보다 늦게 오류를 보고하는 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-237">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="cfc1b-238">반복기 메서드에서 모든 예외는 반환된 시퀀스를 열거하는 코드를 호출할 경우에만 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-238">In iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="cfc1b-239">비동기 메서드에서 모든 예외는 반환된 `Task`가 대기 상태일 경우에만 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-239">In async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span> <span data-ttu-id="cfc1b-240">다음 예제에서는 로컬 함수를 사용하여 반복기 구현으로부터 매개 변수 유효성 검사를 분리하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-240">The following example demonstrates separating parameter validation from the iterator implementation using a local function:</span></span>

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="cfc1b-241">`async` 메서드에서 같은 방법을 사용하면 인수 유효성 검사에서 발생하는 예외가 비동기 작업이 시작되기 전에 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-241">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

> [!NOTE]
> <span data-ttu-id="cfc1b-242">로컬 함수가 지원하는 일부 디자인은 *람다 식*을 사용하여 완료할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-242">Some of the designs that are supported by local functions could also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="cfc1b-243">자세한 내용은 [로컬 함수와 람다 식 비교](../local-functions-vs-lambdas.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-243">For more information, see [Local functions vs. lambda expressions](../local-functions-vs-lambdas.md).</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="cfc1b-244">추가 식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="cfc1b-244">More expression-bodied members</span></span>

<span data-ttu-id="cfc1b-245">C# 6에서는 멤버 함수의 [식 본문 멤버](csharp-6.md#expression-bodied-function-members) 및 읽기 전용 속성을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-245">C# 6 introduced [expression-bodied members](csharp-6.md#expression-bodied-function-members) for member functions, and read-only properties.</span></span> <span data-ttu-id="cfc1b-246">C# 7.0에서는 식으로 구현될 수 있는 허용 멤버를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-246">C# 7.0 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="cfc1b-247">C# 7.0에서는 *속성* 및 *인덱서*에 대한 *생성자*, *종료자* 및 `get`/`set` 접근자를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-247">In C# 7.0, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="cfc1b-248">다음 코드는 각각에 대한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-248">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="cfc1b-249">이 예제에는 종료자가 필요하지 않지만 구문을 보여 주기 위해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-249">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="cfc1b-250">관리되지 않는 리소스를 릴리스해야 하는 경우가 아니면 클래스에서 종료자를 구현하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-250">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="cfc1b-251">관리되지 않는 리소스를 직접 관리하지 않고 <xref:System.Runtime.InteropServices.SafeHandle> 클래스를 사용하는 것도 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-251">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="cfc1b-252">식 본문 멤버의 새 위치는 C# 언어의 중요한 마일스톤을 나타냅니다. 이러한 기능은 오픈 소스 [Roslyn](https://github.com/dotnet/Roslyn) 프로젝트에서 작업하는 커뮤니티 멤버에 의해 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-252">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

<span data-ttu-id="cfc1b-253">메서드를 식 본문 멤버로 변경하는 것은 [이진 호환 가능 변경](version-update-considerations.md#binary-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-253">Changing a method to an expression bodied member is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="cfc1b-254">Throw 식</span><span class="sxs-lookup"><span data-stu-id="cfc1b-254">Throw expressions</span></span>

<span data-ttu-id="cfc1b-255">C#에서 `throw`는 항상 문이었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-255">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="cfc1b-256">`throw`는 식이 아닌 명령문이므로 이 명령문을 사용할 수 없는 C# 구문이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-256">Because `throw` is a statement, not an expression, there were C# constructs where you couldn't use it.</span></span> <span data-ttu-id="cfc1b-257">이러한 구문에는 조건식, null 병합 식 및 몇몇 람다 식이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-257">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="cfc1b-258">식 본문 멤버가 추가됨에 따라 `throw` 식이 유용할 수 있는 추가 위치도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-258">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="cfc1b-259">이러한 구문을 작성할 수 있도록 C# 7.0에서는 [*throw 식*](../language-reference/keywords/throw.md#the-throw-expression)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-259">So that you can write any of these constructs, C# 7.0 introduces [*throw expressions*](../language-reference/keywords/throw.md#the-throw-expression).</span></span>

<span data-ttu-id="cfc1b-260">이렇게 추가하면 자세한 식 기반 코드를 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-260">This addition makes it easier to write more expression-based code.</span></span> <span data-ttu-id="cfc1b-261">오류 검사를 위해 명령문을 추가할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-261">You don't need additional statements for error checking.</span></span>

## <a name="generalized-async-return-types"></a><span data-ttu-id="cfc1b-262">일반화된 비동기 반환 형식</span><span class="sxs-lookup"><span data-stu-id="cfc1b-262">Generalized async return types</span></span>

<span data-ttu-id="cfc1b-263">비동기 메서드에서 `Task` 개체를 반환하면 특정 경로에 성능 병목 현상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-263">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="cfc1b-264">`Task`는 참조 형식이므로 이를 사용하는 것은 개체 할당을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-264">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="cfc1b-265">`async` 한정자로 선언된 메서드가 캐시된 결과를 반환하거나 동기적으로 완료된 경우 코드의 성능이 중요한 섹션에서 추가 할당에 상당한 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-265">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="cfc1b-266">연속 루프에서 이러한 할당이 발생하면 부담이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-266">It can become costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="cfc1b-267">새로운 언어 기능을 통해 비동기 메서드 반환 형식이 `Task`, `Task<T>` 및 `void`에 제한되지 않게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-267">The new language feature means that async method return types aren't limited to `Task`, `Task<T>`, and `void`.</span></span> <span data-ttu-id="cfc1b-268">반환된 형식은 비동기 패턴을 충족해야 합니다. 즉, `GetAwaiter` 메서드에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-268">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="cfc1b-269">한 가지 구체적인 예로 이 새로운 언어 기능을 사용할 수 있도록 `ValueTask` 형식이 .NET에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-269">As one concrete example, the `ValueTask` type has been added to .NET to make use of this new language feature:</span></span>

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="cfc1b-270"><xref:System.Threading.Tasks.ValueTask%601> 형식을 사용하려면 NuGet 패키지 [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/)를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-270">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="cfc1b-271">이 개선 사항은 라이브러리 작성자가 성능이 중요한 코드에서 `Task`를 할당하지 않도록 방지하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-271">This enhancement is most useful for library authors to avoid allocating a `Task` in performance critical code.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="cfc1b-272">숫자 리터럴 구문 개선 사항</span><span class="sxs-lookup"><span data-stu-id="cfc1b-272">Numeric literal syntax improvements</span></span>

<span data-ttu-id="cfc1b-273">숫자 상수를 잘못 읽으면 코드를 처음 읽을 때 이해하기가 더 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-273">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="cfc1b-274">비트 마스크 또는 다른 기호 값은 잘못 이해하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-274">Bit masks or other symbolic values are prone to misunderstanding.</span></span> <span data-ttu-id="cfc1b-275">C# 7.0에는 의도한 용도에 맞게 가장 읽기 쉬운 방식으로 숫자를 작성할 수 있는 *이진 리터럴* 및 *숫자 구분 기호*라는 두 가지 새로운 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-275">C# 7.0 includes two new features to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="cfc1b-276">비트 마스크를 만들 때 또는 숫자의 이진 표현이 가장 읽기 쉬운 코드를 만들 때마다 해당 숫자를 이진으로 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-276">For those times when you're creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

<span data-ttu-id="cfc1b-277">상수의 시작 부분에 있는 `0b`는 숫자가 이진 숫자로 작성되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-277">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span> <span data-ttu-id="cfc1b-278">이진 숫자는 길어질 수 있으므로 위의 이진 상수에 표시된 대로 `_`을 숫자 구분 기호로 추가하면 비트 패턴을 더 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-278">Binary numbers can get long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator, as shown above in the binary constant.</span></span> <span data-ttu-id="cfc1b-279">숫자 구분 기호는 상수 내의 어디에나 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-279">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="cfc1b-280">기본 10개 숫자의 경우 일반적으로 숫자 구분 기호가 천 단위 구분 기호로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-280">For base 10 numbers, it is common to use it as a thousands separator:</span></span>

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

<span data-ttu-id="cfc1b-281">숫자 구분 기호는 `decimal`, `float` 및 `double` 형식에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-281">The digit separator can be used with `decimal`, `float`, and `double` types as well:</span></span>

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

<span data-ttu-id="cfc1b-282">함께 사용하면 숫자 상수를 훨씬 더 읽기 쉽게 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cfc1b-282">Taken together, you can declare numeric constants with much more readability.</span></span>
