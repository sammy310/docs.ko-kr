---
title: C# 7.0의 새로운 기능 - C# 가이드
description: C# 언어 버전 7.0의 새로운 기능을 살펴봅니다.
ms.date: 10/02/2020
ms.assetid: fd41596d-d0c2-4816-b94d-c4d00a5d0243
ms.openlocfilehash: 897729022e45e96d0f54057ef4dad1a4fc0d6799
ms.sourcegitcommit: 0bb8074d524e0dcf165430b744bb143461f17026
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2021
ms.locfileid: "103480855"
---
# <a name="whats-new-in-c-70-through-c-73"></a><span data-ttu-id="fde57-103">C# 7.0~C# 7.3의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="fde57-103">What's new in C# 7.0 through C# 7.3</span></span>

<span data-ttu-id="fde57-104">C# 7.0~C# 7.3에서는 C#을 사용한 개발 환경에 다양한 기능과 증분 개선 사항을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-104">C# 7.0 through C# 7.3 brought a number of features and incremental improvements to your development experience with C#.</span></span> <span data-ttu-id="fde57-105">이 문서에서는 새로운 언어 기능과 컴파일러 옵션에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-105">This article provides an overview of the new language features and compiler options.</span></span> <span data-ttu-id="fde57-106">.NET Framework 기반 애플리케이션에 대해 지원되는 최신 버전인 C# 7.3의 동작을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-106">The descriptions describe the behavior for C# 7.3, which is the most recent version supported for .NET Framework-based applications.</span></span>

<span data-ttu-id="fde57-107">C# 7.1에 추가된 [언어 버전 선택](../language-reference/configure-language-version.md) 구성 요소를 사용하면 프로젝트 파일에서 컴파일러 언어 버전을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-107">The [language version selection](../language-reference/configure-language-version.md) configuration element was added with C# 7.1, which enables you to specify the compiler language version in your project file.</span></span>

<span data-ttu-id="fde57-108">C# 7.0~7.3에서는 C# 언어에 다음 기능과 테마를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-108">C# 7.0-7.3 adds these features and themes to the C# language:</span></span>

- [<span data-ttu-id="fde57-109">튜플 및 무시 항목</span><span class="sxs-lookup"><span data-stu-id="fde57-109">Tuples and discards</span></span>](#tuples-and-discards)
  - <span data-ttu-id="fde57-110">여러 public 필드가 포함된 간단한 명명되지 않은 형식을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-110">You can create lightweight, unnamed types that contain multiple public fields.</span></span> <span data-ttu-id="fde57-111">컴파일러 및 IDE 도구는 이러한 형식의 의미 체계를 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-111">Compilers and IDE tools understand the semantics of these types.</span></span>
  - <span data-ttu-id="fde57-112">삭제는 할당된 값에 신경 쓰지 않을 때 할당에서 사용되는 임시 쓰기 전용 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-112">Discards are temporary, write-only variables used in assignments when you don't care about the value assigned.</span></span> <span data-ttu-id="fde57-113">매개 변수는 `out` 매개 변수를 사용하여 메서드를 호출할 때뿐만 아니라 튜플 및 사용자 정의 형식을 분해할 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-113">They're most useful when deconstructing tuples and user-defined types, as well as when calling methods with `out` parameters.</span></span>
- [<span data-ttu-id="fde57-114">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="fde57-114">Pattern Matching</span></span>](#pattern-matching)
  - <span data-ttu-id="fde57-115">임의 형식 및 해당 형식의 멤버 값에 따라 분기 논리를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-115">You can create branching logic based on arbitrary types and values of the members of those types.</span></span>
- [<span data-ttu-id="fde57-116">`async` `Main` 메서드</span><span class="sxs-lookup"><span data-stu-id="fde57-116">`async` `Main` method</span></span>](#async-main)
  - <span data-ttu-id="fde57-117">애플리케이션에 대한 진입점은 `async` 한정자를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-117">The entry point for an application can have the `async` modifier.</span></span>
- [<span data-ttu-id="fde57-118">로컬 함수</span><span class="sxs-lookup"><span data-stu-id="fde57-118">Local Functions</span></span>](#local-functions)
  - <span data-ttu-id="fde57-119">함수를 다른 함수 내부에 중첩하여 범위와 표시 여부를 제한할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-119">You can nest functions inside other functions to limit their scope and visibility.</span></span>
- [<span data-ttu-id="fde57-120">추가 식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="fde57-120">More expression-bodied members</span></span>](#more-expression-bodied-members)
  - <span data-ttu-id="fde57-121">식을 사용하여 작성할 수 있는 멤버 목록이 증가했습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-121">The list of members that can be authored using expressions has grown.</span></span>
- [<span data-ttu-id="fde57-122">`throw` 식</span><span class="sxs-lookup"><span data-stu-id="fde57-122">`throw` Expressions</span></span>](#throw-expressions)
  - <span data-ttu-id="fde57-123">`throw` 문이었기 때문에 이전에 허용되지 않은 코드 구문에서 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-123">You can throw exceptions in code constructs that previously weren't allowed because `throw` was a statement.</span></span>
- [<span data-ttu-id="fde57-124">`default` 리터럴 식</span><span class="sxs-lookup"><span data-stu-id="fde57-124">`default` literal expressions</span></span>](#default-literal-expressions)
  - <span data-ttu-id="fde57-125">대상 형식을 유추할 수 있는 경우 기본 값 식에서 기본 리터럴 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-125">You can use default literal expressions in default value expressions when the target type can be inferred.</span></span>
- [<span data-ttu-id="fde57-126">숫자 리터럴 구문 개선 사항</span><span class="sxs-lookup"><span data-stu-id="fde57-126">Numeric literal syntax improvements</span></span>](#numeric-literal-syntax-improvements)
  - <span data-ttu-id="fde57-127">새로운 토큰으로 숫자 상수의 가독성이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-127">New tokens improve readability for numeric constants.</span></span>
- [<span data-ttu-id="fde57-128">`out` 변수</span><span class="sxs-lookup"><span data-stu-id="fde57-128">`out` variables</span></span>](#out-variables)
  - <span data-ttu-id="fde57-129">`out` 값을 사용되는 메서드에 대한 인수로 인라인으로 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-129">You can declare `out` values inline as arguments to the method where they're used.</span></span>
- [<span data-ttu-id="fde57-130">뒤에 오지 않는 명명된 인수</span><span class="sxs-lookup"><span data-stu-id="fde57-130">Non-trailing named arguments</span></span>](#non-trailing-named-arguments)
  - <span data-ttu-id="fde57-131">명명된 인수 뒤에는 위치 인수가 올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-131">Named arguments can be followed by positional arguments.</span></span>
- [<span data-ttu-id="fde57-132">`private protected` 액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="fde57-132">`private protected` access modifier</span></span>](#private-protected-access-modifier)
  - <span data-ttu-id="fde57-133">`private protected` 액세스 한정자는 동일한 어셈블리의 파생된 클래스에 대해 액세스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-133">The `private protected` access modifier enables access for derived classes in the same assembly.</span></span>
- [<span data-ttu-id="fde57-134">향상된 오버로드 확인</span><span class="sxs-lookup"><span data-stu-id="fde57-134">Improved overload resolution</span></span>](#improved-overload-candidates)
  - <span data-ttu-id="fde57-135">오버로드 확인 모호성을 해결하는 새로운 규칙</span><span class="sxs-lookup"><span data-stu-id="fde57-135">New rules to resolve overload resolution ambiguity.</span></span>
- [<span data-ttu-id="fde57-136">안전하고 효율적인 코드를 작성하는 방법</span><span class="sxs-lookup"><span data-stu-id="fde57-136">Techniques for writing safe efficient code</span></span>](#enabling-more-efficient-safe-code)
  - <span data-ttu-id="fde57-137">참조 의미 체계를 사용하는 값 유형으로 작동할 수 있는 구문 개선의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-137">A combination of syntax improvements that enable working with value types using reference semantics.</span></span>

<span data-ttu-id="fde57-138">마지막으로, 컴파일러에는 다음과 같은 새 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-138">Finally, the compiler has new options:</span></span>

- <span data-ttu-id="fde57-139">`-refout` 및 `-refonly` - [참조 어셈블리 생성](#reference-assembly-generation)을 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-139">`-refout` and `-refonly` that control [reference assembly generation](#reference-assembly-generation).</span></span>
- <span data-ttu-id="fde57-140">`-publicsign` - OSS(오픈 소스 소프트웨어) 시그니처를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-140">`-publicsign` to enable Open Source Software (OSS) signing of assemblies.</span></span>
- <span data-ttu-id="fde57-141">`-pathmap` - 소스 디렉터리에 대한 매핑을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-141">`-pathmap` to provide a mapping for source directories.</span></span>

<span data-ttu-id="fde57-142">이 문서의 나머지 부분에서는 해당 기능에 대한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-142">The remainder of this article provides an overview of each feature.</span></span> <span data-ttu-id="fde57-143">각 기능의 논리적 근거와 구문을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-143">For each feature, you'll learn the reasoning behind it and the syntax.</span></span> <span data-ttu-id="fde57-144">`dotnet try` 글로벌 도구를 사용하여 환경에서 다음과 같은 기능을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-144">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="fde57-145">[dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) 글로벌 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-145">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="fde57-146">[dotnet/try-samples](https://github.com/dotnet/try-samples) 리포지토리를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-146">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="fde57-147">현재 디렉터리를 *try-samples* 리포지토리의 *csharp7* 하위 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-147">Set the current directory to the *csharp7* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="fde57-148">`dotnet try`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-148">Run `dotnet try`.</span></span>

## <a name="tuples-and-discards"></a><span data-ttu-id="fde57-149">튜플 및 무시 항목</span><span class="sxs-lookup"><span data-stu-id="fde57-149">Tuples and discards</span></span>

<span data-ttu-id="fde57-150">C#에서는 디자인 의도를 설명하는 데 사용되는 클래스 및 구조체에 대한 다양한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-150">C# provides a rich syntax for classes and structs that is used to explain your design intent.</span></span> <span data-ttu-id="fde57-151">하지만 다양한 구문에는 이점이 거의 없는데 추가 작업이 필요한 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-151">But sometimes that rich syntax requires extra work with minimal benefit.</span></span> <span data-ttu-id="fde57-152">일반적으로 두 개 이상의 데이터 요소가 포함된 간단한 구조체가 필요한 메서드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-152">You may often write methods that need a simple structure containing more than one data element.</span></span> <span data-ttu-id="fde57-153">이러한 시나리오를 지원하기 위해 *튜플* 이 C#에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-153">To support these scenarios *tuples* were added to C#.</span></span> <span data-ttu-id="fde57-154">튜플은 데이터 멤버를 나타내는 여러 필드가 포함된 간단한 데이터 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-154">Tuples are lightweight data structures that contain multiple fields to represent the data members.</span></span> <span data-ttu-id="fde57-155">필드의 유효성이 검사되지 않고 고유한 메서드를 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-155">The fields aren't validated, and you can't define your own methods.</span></span> <span data-ttu-id="fde57-156">C# 튜플 형식은 `==` 및 `!=`를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-156">C# tuple types support `==` and `!=`.</span></span> <span data-ttu-id="fde57-157">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="fde57-157">For more information.</span></span>

> [!NOTE]
> <span data-ttu-id="fde57-158">튜플은 C# 7.0 이전부터 사용할 수 있었지만 비효율적이었고 언어 지원이 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-158">Tuples were available before C# 7.0, but they were inefficient and had no language support.</span></span> <span data-ttu-id="fde57-159">즉, 튜플 요소는 `Item1`, `Item2` 등으로만 참조될 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-159">This meant that tuple elements could only be referenced as `Item1`, `Item2` and so on.</span></span> <span data-ttu-id="fde57-160">C# 7.0은 새롭고 보다 효율적인 튜플 유형을 사용하여 튜플의 필드에 대해 의미론적 이름을 사용할 수 있는 튜플에 대한 언어 지원을 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-160">C# 7.0 introduces language support for tuples, which enables semantic names for the fields of a tuple using new, more efficient tuple types.</span></span>

<span data-ttu-id="fde57-161">각 멤버에 값을 할당하고 필요에 따라 튜플의 각 멤버에 의미 체계 이름을 입력하여 튜플을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-161">You can create a tuple by assigning a value to each member, and optionally providing semantic names to each of the members of the tuple:</span></span>

[!code-csharp[NamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#NamedTuple "Named tuple")]

<span data-ttu-id="fde57-162">`namedLetters` 튜플에는 `Alpha` 및 `Beta`라는 필드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-162">The `namedLetters` tuple contains fields referred to as `Alpha` and `Beta`.</span></span> <span data-ttu-id="fde57-163">이러한 이름은 컴파일 시간에만 존재하며 런타임 시 리플렉션을 통해 튜플을 검사하는 경우 보존되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-163">Those names exist only at compile time and aren't preserved, for example when inspecting the tuple using reflection at run time.</span></span>

<span data-ttu-id="fde57-164">튜플 할당에서 할당의 오른쪽에 필드의 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-164">In a tuple assignment, you can also specify the names of the fields on the right-hand side of the assignment:</span></span>

[!code-csharp[ImplicitNamedTuple](~/samples/snippets/csharp/new-in-7/program.cs#ImplicitNamedTuple "Implicitly named tuple")]

<span data-ttu-id="fde57-165">메서드에서 반환된 튜플의 멤버를 패키지 해제하려는 경우가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-165">There may be times when you want to unpackage the members of a tuple that were returned from a method.</span></span>  <span data-ttu-id="fde57-166">이 작업을 수행하려면 튜플에서 각 값에 대한 개별 변수를 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-166">You can do that by declaring separate variables for each of the values in the tuple.</span></span> <span data-ttu-id="fde57-167">이 패키지 해제 작업을 튜플 *분해* 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-167">This unpackaging is called *deconstructing* the tuple:</span></span>

[!code-csharp[CallingWithDeconstructor](~/samples/snippets/csharp/new-in-7/program.cs#CallingWithDeconstructor "Deconstructing a tuple")]

<span data-ttu-id="fde57-168">.NET에 있는 형식에 대한 비슷한 분해를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-168">You can also provide a similar deconstruction for any type in .NET.</span></span> <span data-ttu-id="fde57-169">`Deconstruct` 메서드를 클래스의 멤버로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-169">You write a `Deconstruct` method as a member of the class.</span></span> <span data-ttu-id="fde57-170">해당 `Deconstruct` 메서드는 추출하려는 각 속성에 대한 `out` 인수 집합을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-170">That `Deconstruct` method provides a set of `out` arguments for each of the properties you want to extract.</span></span> <span data-ttu-id="fde57-171">`X` 및 `Y` 좌표를 추출하는 분해자 메서드를 제공하는 이 `Point` 클래스를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-171">Consider this `Point` class that provides a deconstructor method that extracts the `X` and `Y` coordinates:</span></span>

[!code-csharp[PointWithDeconstruction](~/samples/snippets/csharp/new-in-7/point.cs#PointWithDeconstruction "Point with deconstruction method")]

<span data-ttu-id="fde57-172">튜플에 `Point`을 할당하여 개별 필드를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-172">You can extract the individual fields by assigning a `Point` to a tuple:</span></span>

[!code-csharp[DeconstructPoint](~/samples/snippets/csharp/new-in-7/program.cs#DeconstructPoint "Deconstruct a point")]

<span data-ttu-id="fde57-173">여러 번 튜플을 초기화할 때 할당의 오른쪽에 사용되는 변수는 튜플 요소에 대해 원하는 이름과 동일합니다. 튜플 요소의 이름은 튜플을 초기화하는 데 사용된 변수를 통해 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-173">Many times when you initialize a tuple, the variables used for the right side of the assignment are the same as the names you'd like for the tuple elements: The names of tuple elements can be inferred from the variables used to initialize the tuple:</span></span>

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

<span data-ttu-id="fde57-174">[튜플 형식](../language-reference/builtin-types/value-tuples.md) 문서에서 해당 기능을 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-174">You can learn more about this feature in the [Tuple types](../language-reference/builtin-types/value-tuples.md) article.</span></span>

<span data-ttu-id="fde57-175">종종 튜플을 분해하거나 `out` 매개 변수로 메서드를 호출할 때 값을 신경 쓰지 않고 사용하지 않을 변수를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-175">Often when deconstructing a tuple or calling a method with `out` parameters, you're forced to define a variable whose value you don't care about and don't intend to use.</span></span> <span data-ttu-id="fde57-176">C#은 *버림* 에 대한 지원을 추가하여 이 시나리오를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-176">C# adds support for *discards* to handle this scenario.</span></span> <span data-ttu-id="fde57-177">무시는 이름이 `_`(밑줄 문자)인 쓰기 전용 변수입니다. 단일 변수에 버리려는 모든 값을 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-177">A discard is a write-only variable whose name is `_` (the underscore character); you can assign all of the values that you intend to discard to the single variable.</span></span> <span data-ttu-id="fde57-178">버림은 할당 문과 별도로 분리되는 할당되지 않은 변수와 같습니다. 코드에서 버림을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-178">A discard is like an unassigned variable; apart from the assignment statement, the discard can't be used in code.</span></span>

<span data-ttu-id="fde57-179">다음 시나리오에서는 버림이 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-179">Discards are supported in the following scenarios:</span></span>

- <span data-ttu-id="fde57-180">튜플이나 사용자 정의 형식을 분해할 때.</span><span class="sxs-lookup"><span data-stu-id="fde57-180">When deconstructing tuples or user-defined types.</span></span>
- <span data-ttu-id="fde57-181">[out](../language-reference/keywords/out-parameter-modifier.md) 매개 변수로 메서드를 호출할 때.</span><span class="sxs-lookup"><span data-stu-id="fde57-181">When calling methods with [out](../language-reference/keywords/out-parameter-modifier.md) parameters.</span></span>
- <span data-ttu-id="fde57-182">[is](../language-reference/keywords/is.md) 및 [switch](../language-reference/keywords/switch.md) 문을 사용한 패턴 일치 작업에서.</span><span class="sxs-lookup"><span data-stu-id="fde57-182">In a pattern matching operation with the [is](../language-reference/keywords/is.md) and [switch](../language-reference/keywords/switch.md) statements.</span></span>
- <span data-ttu-id="fde57-183">할당 값을 버림으로 명시적으로 지정할 때 독립 실행형 식별자인 경우.</span><span class="sxs-lookup"><span data-stu-id="fde57-183">As a standalone identifier when you want to explicitly identify the value of an assignment as a discard.</span></span>

<span data-ttu-id="fde57-184">다음 예제에서는 서로 다른 2년간의 도시 데이터가 포함된 6 튜플을 반환하는 `QueryCityDataForYears` 메서드를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-184">The following example defines a `QueryCityDataForYears` method that returns a 6-tuple that contains data for a city for two different years.</span></span> <span data-ttu-id="fde57-185">예제의 메서드 호출은 메서드에 의해 반환된 두 개의 채우기 값에만 관련되어 있으므로 튜플을 해체할 때 튜플의 나머지 값을 버림으로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-185">The method call in the example is concerned only with the two population values returned by the method and so treats the remaining values in the tuple as discards when it deconstructs the tuple.</span></span>

[!code-csharp[Tuple-discard](~/samples/snippets/csharp/programming-guide/deconstructing-tuples/discard-tuple1.cs)]

<span data-ttu-id="fde57-186">자세한 내용은 [버림](../discards.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-186">For more information, see [Discards](../discards.md).</span></span>

## <a name="pattern-matching"></a><span data-ttu-id="fde57-187">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="fde57-187">Pattern matching</span></span>

<span data-ttu-id="fde57-188">‘패턴 일치’는 코드에서 제어 흐름을 표현하는 새로운 방법을 제공하는 기능 세트입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-188">*Pattern matching* is a set of features that enable new ways to express control flow in your code.</span></span> <span data-ttu-id="fde57-189">형식, 값 또는 속성 값에 대해 변수를 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-189">You can test variables for their type, values or the values of their properties.</span></span> <span data-ttu-id="fde57-190">해당 기술은 좀 더 읽기 쉬운 코드 흐름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-190">These techniques create more readable code flow.</span></span>

<span data-ttu-id="fde57-191">패턴 일치는 `is` 식과 `switch` 식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-191">Pattern matching supports `is` expressions and `switch` expressions.</span></span> <span data-ttu-id="fde57-192">각 식을 통해 개체 및 관련 속성을 검사하여 해당 개체가 검색된 패턴을 충족하는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-192">Each enables inspecting an object and its properties to determine if that object satisfies the sought pattern.</span></span> <span data-ttu-id="fde57-193">`when` 키워드를 사용하여 패턴에 대한 추가 규칙을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-193">You use the `when` keyword to specify additional rules to the pattern.</span></span>

<span data-ttu-id="fde57-194">`is` 패턴 식은 친숙한 [`is` 연산자](../language-reference/keywords/is.md#pattern-matching-with-is)를 확장하여 해당 형식에 대한 개체를 쿼리하고 하나의 명령에서 결과를 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-194">The `is` pattern expression extends the familiar [`is` operator](../language-reference/keywords/is.md#pattern-matching-with-is) to query an object about its type and assign the result in one instruction.</span></span> <span data-ttu-id="fde57-195">다음 코드는 변수가 `int`인지 검사하고, 그럴 경우 현재 합계에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-195">The following code checks if a variable is an `int`, and if so, adds it to the current sum:</span></span>

```csharp
if (input is int count)
    sum += count;
```

<span data-ttu-id="fde57-196">앞서 간단한 예제에서는 `is` 식의 개선 사항을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-196">The preceding small example demonstrates the enhancements to the `is` expression.</span></span> <span data-ttu-id="fde57-197">참조 형식뿐만 아니라 값 형식에 대해 테스트할 수 있고, 올바른 형식의 새로운 변수에 성공적인 결과를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-197">You can test against value types as well as reference types, and you can assign the successful result to a new variable of the correct type.</span></span>

<span data-ttu-id="fde57-198">switch 일치 식에는 이미 C# 언어의 일부인 `switch` 문에 기반을 둔 친숙한 구문이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-198">The switch match expression has a familiar syntax, based on the `switch` statement already part of the C# language.</span></span> <span data-ttu-id="fde57-199">업데이트된 switch 문에는 몇 가지 새로운 구문이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-199">The updated switch statement has several new constructs:</span></span>

- <span data-ttu-id="fde57-200">`switch` 식의 관리 형식은 더 이상 정수 형식, `Enum` 형식, `string` 또는 해당 형식 중 하나에 해당하는 nullable 형식으로 제한되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-200">The governing type of a `switch` expression is no longer restricted to integral types, `Enum` types, `string`, or a nullable type corresponding to one of those types.</span></span> <span data-ttu-id="fde57-201">모든 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-201">Any type may be used.</span></span>
- <span data-ttu-id="fde57-202">각 `case` 레이블에서 `switch` 식 형식을 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-202">You can test the type of the `switch` expression in each `case` label.</span></span> <span data-ttu-id="fde57-203">`is` 식과 마찬가지로 해당 형식에 새 변수를 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-203">As with the `is` expression, you may assign a new variable to that type.</span></span>
- <span data-ttu-id="fde57-204">`when` 절을 해당 변수의 추가 테스트 조건에 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-204">You may add a `when` clause to further test conditions on that variable.</span></span>
- <span data-ttu-id="fde57-205">이제 `case` 레이블의 순서가 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-205">The order of `case` labels is now important.</span></span> <span data-ttu-id="fde57-206">일치하는 첫 번째 분기가 실행됩니다. 다른 분기는 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-206">The first branch to match is executed; others are skipped.</span></span>

<span data-ttu-id="fde57-207">다음 코드에서는 이 새로운 기능을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-207">The following code demonstrates these new features:</span></span>

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

- <span data-ttu-id="fde57-208">`case 0:`은 친숙한 상수 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-208">`case 0:` is the familiar constant pattern.</span></span>
- <span data-ttu-id="fde57-209">`case IEnumerable<int> childSequence:`는 형식 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-209">`case IEnumerable<int> childSequence:` is a type pattern.</span></span>
- <span data-ttu-id="fde57-210">`case int n when n > 0:`은 추가 `when` 조건을 포함한 형식 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-210">`case int n when n > 0:` is a type pattern with an additional `when` condition.</span></span>
- <span data-ttu-id="fde57-211">`case null:`은 null 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-211">`case null:` is the null pattern.</span></span>
- <span data-ttu-id="fde57-212">`default:`는 친숙한 기본 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-212">`default:` is the familiar default case.</span></span>

<span data-ttu-id="fde57-213">C# 7.1부터 `is` 및 `switch` 형식 패턴의 패턴 식에는 제네릭 형식 매개 변수의 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-213">Beginning with C# 7.1, the pattern expression for `is` and the `switch` type pattern may have the type of a generic type parameter.</span></span> <span data-ttu-id="fde57-214">이 방법은 `struct` 또는 `class` 형식 중 하나일 수 있는 형식을 확인하고 boxing을 방지하려는 경우에 가장 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-214">This can be most useful when checking types that may be either `struct` or `class` types, and you want to avoid boxing.</span></span>

<span data-ttu-id="fde57-215">[C#의 패턴 일치](../pattern-matching.md)에서 패턴 일치에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-215">You can learn more about pattern matching in [Pattern Matching in C#](../pattern-matching.md).</span></span>

## <a name="async-main"></a><span data-ttu-id="fde57-216">비동기 기본</span><span class="sxs-lookup"><span data-stu-id="fde57-216">Async main</span></span>

<span data-ttu-id="fde57-217">*비동기 기본* 메서드를 통해 `Main` 메서드에서 `await`를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-217">An *async main* method enables you to use `await` in your `Main` method.</span></span> <span data-ttu-id="fde57-218">이전에 다음을 작성해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-218">Previously you would need to write:</span></span>

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

<span data-ttu-id="fde57-219">이제 다음을 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-219">You can now write:</span></span>

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

<span data-ttu-id="fde57-220">프로그램이 종료 코드를 반환하지 않는 경우 <xref:System.Threading.Tasks.Task>를 반환하는 `Main` 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-220">If your program doesn't return an exit code, you can declare a `Main` method that returns a <xref:System.Threading.Tasks.Task>:</span></span>

```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

<span data-ttu-id="fde57-221">프로그래밍 가이드의 [비동기 기본](../programming-guide/main-and-command-args/index.md) 문서에서 세부 정보에 대해 자세히 읽어볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-221">You can read more about the details in the [async main](../programming-guide/main-and-command-args/index.md) article in the programming guide.</span></span>

## <a name="local-functions"></a><span data-ttu-id="fde57-222">로컬 함수</span><span class="sxs-lookup"><span data-stu-id="fde57-222">Local functions</span></span>

<span data-ttu-id="fde57-223">클래스에 대한 대부분의 디자인에는 한 위치에서만 호출되는 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-223">Many designs for classes include methods that are called from only one location.</span></span> <span data-ttu-id="fde57-224">이러한 추가 private 메서드는 각 메서드를 작고 집중되게 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-224">These additional private methods keep each method small and focused.</span></span> <span data-ttu-id="fde57-225">*로컬 함수* 를 사용하면 다른 메서드의 컨텍스트 내부에서 메서드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-225">*Local functions* enable you to declare methods inside the context of another method.</span></span> <span data-ttu-id="fde57-226">로컬 함수를 통해 클래스 readers는 로컬 메서드가 선언된 컨텍스트에서만 호출된다는 것을 더 쉽게 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-226">Local functions make it easier for readers of the class to see that the local method is only called from the context in which it is declared.</span></span>

<span data-ttu-id="fde57-227">로컬 함수는 일반적으로 공용 반복기 메서드 및 공용 비동기 메서드에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-227">There are two common use cases for local functions: public iterator methods and public async methods.</span></span> <span data-ttu-id="fde57-228">두 메서드 형식 모두 프로그래머가 예상한 것보다 늦게 오류를 보고하는 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-228">Both types of methods generate code that reports errors later than programmers might expect.</span></span> <span data-ttu-id="fde57-229">반복기 메서드에서 모든 예외는 반환된 시퀀스를 열거하는 코드를 호출할 경우에만 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-229">In iterator methods, any exceptions are observed only when calling code that enumerates the returned sequence.</span></span> <span data-ttu-id="fde57-230">비동기 메서드에서 모든 예외는 반환된 `Task`가 대기 상태일 경우에만 관찰됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-230">In async methods, any exceptions are only observed when the returned `Task` is awaited.</span></span> <span data-ttu-id="fde57-231">다음 예제에서는 로컬 함수를 사용하여 반복기 구현으로부터 매개 변수 유효성 검사를 분리하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-231">The following example demonstrates separating parameter validation from the iterator implementation using a local function:</span></span>

[!code-csharp[22_IteratorMethodLocal](~/samples/snippets/csharp/new-in-7/Iterator.cs#IteratorMethodLocal "Iterator method with local function")]

<span data-ttu-id="fde57-232">`async` 메서드에서 같은 방법을 사용하면 인수 유효성 검사에서 발생하는 예외가 비동기 작업이 시작되기 전에 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-232">The same technique can be employed with `async` methods to ensure that exceptions arising from argument validation are thrown before the asynchronous work begins:</span></span>

[!code-csharp[TaskExample](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#TaskExample "Task returning method with local function")]

<span data-ttu-id="fde57-233">이제 다음 구문이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-233">This syntax is now supported:</span></span>

```csharp
[field: SomeThingAboutFieldAttribute]
public int SomeProperty { get; set; }
```

<span data-ttu-id="fde57-234">`SomeThingAboutFieldAttribute` 특성은 `SomeProperty`에 대한 컴파일러 생성 지원 필드에 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-234">The attribute `SomeThingAboutFieldAttribute` is applied to the compiler generated backing field for `SomeProperty`.</span></span> <span data-ttu-id="fde57-235">자세한 내용은 C# 프로그래밍 가이드의 [특성](../programming-guide/concepts/attributes/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-235">For more information, see [attributes](../programming-guide/concepts/attributes/index.md) in the C# programming guide.</span></span>

> [!NOTE]
> <span data-ttu-id="fde57-236">로컬 함수가 지원하는 일부 디자인은 *람다 식* 을 사용하여 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-236">Some of the designs that are supported by local functions can also be accomplished using *lambda expressions*.</span></span> <span data-ttu-id="fde57-237">자세한 내용은 [로컬 함수와 람다 식 비교](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-237">For more information, see [Local functions vs. lambda expressions](../programming-guide/classes-and-structs/local-functions.md#local-functions-vs-lambda-expressions).</span></span>

## <a name="more-expression-bodied-members"></a><span data-ttu-id="fde57-238">추가 식 본문 멤버</span><span class="sxs-lookup"><span data-stu-id="fde57-238">More expression-bodied members</span></span>

<span data-ttu-id="fde57-239">C# 6에서는 멤버 함수의 식 본문 멤버 및 읽기 전용 속성을 추가했습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-239">C# 6 introduced expression-bodied members for member functions and read-only properties.</span></span> <span data-ttu-id="fde57-240">C# 7.0에서는 식으로 구현될 수 있는 허용 멤버를 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-240">C# 7.0 expands the allowed members that can be implemented as expressions.</span></span> <span data-ttu-id="fde57-241">C# 7.0에서는 *속성* 및 *인덱서* 에 대한 *생성자*, *종료자* 및 `get`/`set` 접근자를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-241">In C# 7.0, you can implement *constructors*, *finalizers*, and `get` and `set` accessors on *properties* and *indexers*.</span></span> <span data-ttu-id="fde57-242">다음 코드는 각각에 대한 예제를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-242">The following code shows examples of each:</span></span>

[!code-csharp[ExpressionBodiedMembers](~/samples/snippets/csharp/new-in-7/expressionmembers.cs#ExpressionBodiedEverything "new expression-bodied members")]

> [!NOTE]
> <span data-ttu-id="fde57-243">이 예제에는 종료자가 필요하지 않지만 구문을 보여 주기 위해 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-243">This example does not need a finalizer, but it is shown to demonstrate the syntax.</span></span> <span data-ttu-id="fde57-244">관리되지 않는 리소스를 릴리스해야 하는 경우가 아니면 클래스에서 종료자를 구현하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-244">You should not implement a finalizer in your class unless it is necessary to  release unmanaged resources.</span></span> <span data-ttu-id="fde57-245">관리되지 않는 리소스를 직접 관리하지 않고 <xref:System.Runtime.InteropServices.SafeHandle> 클래스를 사용하는 것도 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-245">You should also consider using the <xref:System.Runtime.InteropServices.SafeHandle> class instead of managing unmanaged resources directly.</span></span>

<span data-ttu-id="fde57-246">식 본문 멤버의 새 위치는 C# 언어의 중요한 마일스톤을 나타냅니다. 이러한 기능은 오픈 소스 [Roslyn](https://github.com/dotnet/Roslyn) 프로젝트에서 작업하는 커뮤니티 멤버에 의해 구현되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-246">These new locations for expression-bodied members represent an important milestone for the C# language: These features were implemented by community members working on the open-source [Roslyn](https://github.com/dotnet/Roslyn) project.</span></span>

<span data-ttu-id="fde57-247">메서드를 식 본문 멤버로 변경하는 것은 [이진 호환 가능 변경](version-update-considerations.md#binary-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-247">Changing a method to an expression bodied member is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>

## <a name="throw-expressions"></a><span data-ttu-id="fde57-248">Throw 식</span><span class="sxs-lookup"><span data-stu-id="fde57-248">Throw expressions</span></span>

<span data-ttu-id="fde57-249">C#에서 `throw`는 항상 문이었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-249">In C#, `throw` has always been a statement.</span></span> <span data-ttu-id="fde57-250">`throw`는 식이 아닌 명령문이므로 이 명령문을 사용할 수 없는 C# 구문이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-250">Because `throw` is a statement, not an expression, there were C# constructs where you couldn't use it.</span></span> <span data-ttu-id="fde57-251">이러한 구문에는 조건식, null 병합 식 및 몇몇 람다 식이 포함되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-251">These included conditional expressions, null coalescing expressions, and some lambda expressions.</span></span> <span data-ttu-id="fde57-252">식 본문 멤버가 추가됨에 따라 `throw` 식이 유용할 수 있는 추가 위치도 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-252">The addition of expression-bodied members adds more locations where `throw` expressions would be useful.</span></span> <span data-ttu-id="fde57-253">이러한 구문을 작성할 수 있도록 C# 7.0에서는 [*throw 식*](../language-reference/keywords/throw.md#the-throw-expression)을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-253">So that you can write any of these constructs, C# 7.0 introduces [*throw expressions*](../language-reference/keywords/throw.md#the-throw-expression).</span></span>

<span data-ttu-id="fde57-254">이렇게 추가하면 자세한 식 기반 코드를 쉽게 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-254">This addition makes it easier to write more expression-based code.</span></span> <span data-ttu-id="fde57-255">오류 검사를 위해 명령문을 추가할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-255">You don't need additional statements for error checking.</span></span>

## <a name="default-literal-expressions"></a><span data-ttu-id="fde57-256">기본 리터럴 식</span><span class="sxs-lookup"><span data-stu-id="fde57-256">Default literal expressions</span></span>

<span data-ttu-id="fde57-257">기본 리터럴 식은 기본값 식에 대한 향상된 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-257">Default literal expressions are an enhancement to default value expressions.</span></span> <span data-ttu-id="fde57-258">이러한 식은 변수를 기본 값으로 초기화합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-258">These expressions initialize a variable to the default value.</span></span> <span data-ttu-id="fde57-259">여기서 이전에 다음을 작성했습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-259">Where you previously would write:</span></span>

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

<span data-ttu-id="fde57-260">이제 초기화의 오른쪽에서 형식을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-260">You can now omit the type on the right-hand side of the initialization:</span></span>

```csharp
Func<string, bool> whereClause = default;
```

<span data-ttu-id="fde57-261">자세한 내용은 [기본 연산자](../language-reference/operators/default.md) 문서의 [기본 리터럴](../language-reference/operators/default.md#default-literal) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-261">For more information, see the [default literal](../language-reference/operators/default.md#default-literal) section of the [default operator](../language-reference/operators/default.md) article.</span></span>

## <a name="numeric-literal-syntax-improvements"></a><span data-ttu-id="fde57-262">숫자 리터럴 구문 개선 사항</span><span class="sxs-lookup"><span data-stu-id="fde57-262">Numeric literal syntax improvements</span></span>

<span data-ttu-id="fde57-263">숫자 상수를 잘못 읽으면 코드를 처음 읽을 때 이해하기가 더 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-263">Misreading numeric constants can make it harder to understand code when reading it for the first time.</span></span> <span data-ttu-id="fde57-264">비트 마스크 또는 다른 기호 값은 잘못 이해하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-264">Bit masks or other symbolic values are prone to misunderstanding.</span></span> <span data-ttu-id="fde57-265">C# 7.0에는 의도한 용도에 맞게 가장 읽기 쉬운 방식으로 숫자를 작성할 수 있는 *이진 리터럴* 및 *숫자 구분 기호* 라는 두 가지 새로운 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-265">C# 7.0 includes two new features to write numbers in the most readable fashion for the intended use: *binary literals*, and *digit separators*.</span></span>

<span data-ttu-id="fde57-266">비트 마스크를 만들 때 또는 숫자의 이진 표현이 가장 읽기 쉬운 코드를 만들 때마다 해당 숫자를 이진으로 작성하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-266">For those times when you're creating bit masks, or whenever a binary representation of a number makes the most readable code, write that number in binary:</span></span>

[!code-csharp[ThousandSeparators](~/samples/snippets/csharp/new-in-7/Program.cs#ThousandSeparators "Thousands separators")]

<span data-ttu-id="fde57-267">상수의 시작 부분에 있는 `0b`는 숫자가 이진 숫자로 작성되었음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-267">The `0b` at the beginning of the constant indicates that the number is written as a binary number.</span></span> <span data-ttu-id="fde57-268">이진 숫자는 길어질 수 있으므로, 이전 예제의 이진 상수와 같이 `_`을 숫자 구분 기호로 추가하면 일반적으로 비트 패턴을 더 쉽게 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-268">Binary numbers can get long, so it's often easier to see the bit patterns by introducing the `_` as a digit separator, as shown in the binary constant in the preceding example.</span></span> <span data-ttu-id="fde57-269">숫자 구분 기호는 상수 내의 어디에나 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-269">The digit separator can appear anywhere in the constant.</span></span> <span data-ttu-id="fde57-270">10진수 숫자의 경우 숫자 구분 기호를 천 단위 구분 기호로 사용하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-270">For base 10 numbers, it is common to use it as a thousands separator.</span></span> <span data-ttu-id="fde57-271">16진수 및 이진 숫자 리터럴은 `_`로 시작할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-271">Hex and binary numeric literals may begin with an `_`:</span></span>

[!code-csharp[LargeIntegers](~/samples/snippets/csharp/new-in-7/Program.cs#LargeIntegers "Large integer")]

<span data-ttu-id="fde57-272">숫자 구분 기호는 `decimal`, `float` 및 `double` 형식에서도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-272">The digit separator can be used with `decimal`, `float`, and `double` types as well:</span></span>

[!code-csharp[OtherConstants](~/samples/snippets/csharp/new-in-7/Program.cs#OtherConstants "non-integral constants")]

<span data-ttu-id="fde57-273">함께 사용하면 숫자 상수를 훨씬 더 읽기 쉽게 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-273">Taken together, you can declare numeric constants with much more readability.</span></span>

## <a name="out-variables"></a><span data-ttu-id="fde57-274">`out` 변수</span><span class="sxs-lookup"><span data-stu-id="fde57-274">`out` variables</span></span>

<span data-ttu-id="fde57-275">`out` 매개 변수를 지원하는 기존 구문이 C# 7에서 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-275">The existing syntax that supports `out` parameters has been improved in C# 7.</span></span> <span data-ttu-id="fde57-276">이제 개별 선언 문을 작성하는 대신 메서드 호출의 인수 목록에서 `out` 변수를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-276">You can now declare `out` variables in the argument list of a method call, rather than writing a separate declaration statement:</span></span>

[!code-csharp[OutVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVariableDeclarations "Out variable declarations")]

<span data-ttu-id="fde57-277">이전 예제와 같이 `out` 변수의 형식을 명확하게 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-277">You may want to specify the type of the `out` variable for clarity, as shown in the preceding example.</span></span> <span data-ttu-id="fde57-278">그러나 이 언어는 암시적 형식 지역 변수를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-278">However, the language does support using an implicitly typed local variable:</span></span>

[!code-csharp[OutVarVariableDeclarations](~/samples/snippets/csharp/new-in-7/program.cs#OutVarVariableDeclarations "Implicitly typed Out variable")]

- <span data-ttu-id="fde57-279">코드를 읽기가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-279">The code is easier to read.</span></span>
  - <span data-ttu-id="fde57-280">out 변수는 앞의 코드 줄이 아니라 변수를 사용하는 곳에서 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-280">You declare the out variable where you use it, not on a preceding line of code.</span></span>
- <span data-ttu-id="fde57-281">초기 값을 할당할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-281">No need to assign an initial value.</span></span>
  - <span data-ttu-id="fde57-282">메서드 호출에서 사용되는 위치에 `out` 변수를 선언하여 변수가 할당되기 전에 실수로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-282">By declaring the `out` variable where it's used in a method call, you can't accidentally use it before it is assigned.</span></span>

<span data-ttu-id="fde57-283">`out` 변수 선언이 허용하기 위해 C# 7.0에 추가된 구문은 필드 이니셜라이저, 속성 이니셜라이저, 생성자 이니셜라이저 및 쿼리 절을 포함하도록 확장되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-283">The syntax added in C# 7.0 to allow `out` variable declarations has been extended to include field initializers, property initializers, constructor initializers, and query clauses.</span></span> <span data-ttu-id="fde57-284">이를 통해 다음 예제와 같은 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-284">It enables code such as the following example:</span></span>

```csharp
public class B
{
   public B(int i, out int j)
   {
      j = i;
   }
}

public class D : B
{
   public D(int i) : base(i, out var j)
   {
      Console.WriteLine($"The value of 'j' is {j}");
   }
}
```

## <a name="non-trailing-named-arguments"></a><span data-ttu-id="fde57-285">뒤에 오지 않는 명명된 인수</span><span class="sxs-lookup"><span data-stu-id="fde57-285">Non-trailing named arguments</span></span>

<span data-ttu-id="fde57-286">명명된 인수가 올바른 위치에 있을 때 메서드 호출은 이제 위치 인수보다 앞에 있는 명명된 인수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-286">Method calls may now use named arguments that precede positional arguments when those named arguments are in the correct positions.</span></span> <span data-ttu-id="fde57-287">자세한 내용은 [명명된 인수 및 선택적 인수](../programming-guide/classes-and-structs/named-and-optional-arguments.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-287">For more information, see [Named and optional arguments](../programming-guide/classes-and-structs/named-and-optional-arguments.md).</span></span>

## <a name="private-protected-access-modifier"></a><span data-ttu-id="fde57-288">*private protected* 액세스 한정자</span><span class="sxs-lookup"><span data-stu-id="fde57-288">*private protected* access modifier</span></span>

<span data-ttu-id="fde57-289">새로운 복합 액세스 한정자인 `private protected`는 동일한 어셈블리에 선언된 클래스 또는 파생 클래스를 포함하여 멤버에 액세스할 수 있음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-289">A new compound access modifier: `private protected` indicates that a member may be accessed by containing class or derived classes that are declared in the same assembly.</span></span> <span data-ttu-id="fde57-290">`protected internal`은 동일한 어셈블리에 있는 파생 클래스나 클래스에 의한 액세스를 허용하지만 `private protected`는 동일한 어셈블리에서 선언된 파생 유형에 대한 액세스를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-290">While `protected internal` allows access by derived classes or classes that are in the same assembly, `private protected` limits access to derived types declared in the same assembly.</span></span>

<span data-ttu-id="fde57-291">자세한 내용은 언어 참조에서 [액세스 한정자](../language-reference/keywords/access-modifiers.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-291">For more information, see [access modifiers](../language-reference/keywords/access-modifiers.md) in the language reference.</span></span>

## <a name="improved-overload-candidates"></a><span data-ttu-id="fde57-292">향상된 오버로드 후보</span><span class="sxs-lookup"><span data-stu-id="fde57-292">Improved overload candidates</span></span>

<span data-ttu-id="fde57-293">모든 릴리스에서 오버로드 해결 규칙은 모호한 메서드 호출에 “분명한” 선택이 있는 상황을 해결하도록 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-293">In every release, the overload resolution rules get updated to address situations where ambiguous method invocations have an "obvious" choice.</span></span> <span data-ttu-id="fde57-294">이 릴리스는 컴파일러가 분명한 선택 항목을 선택하도록 도와주는 세 가지 새로운 규칙을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-294">This release adds three new rules to help the compiler pick the obvious choice:</span></span>

1. <span data-ttu-id="fde57-295">메서드 그룹에 인스턴스와 정적 멤버가 둘 다 포함되어 있으면 인스턴스 수신기 또는 컨텍스트 없이 호출되는 경우 컴파일러는 인스턴스 멤버를 버립니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-295">When a method group contains both instance and static members, the compiler discards the instance members if the method was invoked without an instance receiver or context.</span></span> <span data-ttu-id="fde57-296">메서드가 인스턴스 수신기를 통해 호출된 경우 컴파일러는 정적 멤버를 버립니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-296">The compiler discards the static members if the method was invoked with an instance receiver.</span></span> <span data-ttu-id="fde57-297">수신기가 없는 경우 컴파일러는 정적 컨텍스트에 정적 멤버만 포함하고, 이외의 경우에는 정적 및 인스턴스 멤버를 둘 다 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-297">When there is no receiver, the compiler includes only static members in a static context, otherwise both static and instance members.</span></span> <span data-ttu-id="fde57-298">수신기가 모호하게 인스턴스 또는 형식인 경우에는 컴파일러가 둘 다 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-298">When the receiver is ambiguously an instance or type, the compiler includes both.</span></span> <span data-ttu-id="fde57-299">암시적 `this` 인스턴스 수신기를 사용할 수 없는 정적 컨텍스트에는 정적 멤버와 같이 `this`가 정의되지 않은 멤버의 본문과 필드 이니셜라이저 및 생성자 이니셜라이저와 같이 `this`를 사용할 수 없는 위치가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-299">A static context, where an implicit `this` instance receiver cannot be used, includes the body of members where no `this` is defined, such as static members, as well as places where `this` cannot be used, such as field initializers and constructor-initializers.</span></span>
1. <span data-ttu-id="fde57-300">형식 인수가 해당 제약 조건을 충족하지 않는 제네릭 메서드가 메서드 그룹에 포함된 경우 이러한 멤버는 후보 집합에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-300">When a method group contains some generic methods whose type arguments do not satisfy their constraints, these members are removed from the candidate set.</span></span>
1. <span data-ttu-id="fde57-301">메서드 그룹 변환의 경우 반환 형식이 대리자의 반환 형식과 일치하지 않는 후보 메서드가 집합에서 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-301">For a method group conversion, candidate methods whose return type doesn't match up with the delegate's return type are removed from the set.</span></span>

<span data-ttu-id="fde57-302">어떤 메서드가 더 나은지 알고 있으면 모호한 메서드 오버로드에 대한 컴파일러 오류가 감소하므로 이 변경을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-302">You'll only notice this change because you'll find fewer compiler errors for ambiguous method overloads when you are sure which method is better.</span></span>

## <a name="enabling-more-efficient-safe-code"></a><span data-ttu-id="fde57-303">좀 더 효율적인 안전한 코드 사용</span><span class="sxs-lookup"><span data-stu-id="fde57-303">Enabling more efficient safe code</span></span>

<span data-ttu-id="fde57-304">안전하게 실행할 C# 코드 및 안전하지 않은 코드를 작성할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-304">You should be able to write C# code safely that performs as well as unsafe code.</span></span> <span data-ttu-id="fde57-305">안전한 코드를 사용하면 버퍼 오버런, 이상 포인터 및 기타 메모리 액세스 오류와 같은 오류 클래스를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-305">Safe code avoids classes of errors, such as buffer overruns, stray pointers, and other memory access errors.</span></span> <span data-ttu-id="fde57-306">이러한 새 기능은 확인 가능한 안전한 코드의 기능을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-306">These new features expand the capabilities of verifiable safe code.</span></span> <span data-ttu-id="fde57-307">안전한 구문을 사용하여 더 많은 코드를 작성하도록 노력하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-307">Strive to write more of your code using safe constructs.</span></span> <span data-ttu-id="fde57-308">이러한 기능을 사용하면 이 작업이 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-308">These features make that easier.</span></span>

<span data-ttu-id="fde57-309">다음 새로운 기능은 안전한 코드에 대해 향상된 성능의 테마를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-309">The following new features support the theme of better performance for safe code:</span></span>

- <span data-ttu-id="fde57-310">고정하지 않고 고정 필드에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-310">You can access fixed fields without pinning.</span></span>
- <span data-ttu-id="fde57-311">`ref` 지역 변수를 다시 할당할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-311">You can reassign `ref` local variables.</span></span>
- <span data-ttu-id="fde57-312">`stackalloc` 배열에서 이니셜라이저를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-312">You can use initializers on `stackalloc` arrays.</span></span>
- <span data-ttu-id="fde57-313">패턴을 지원하는 모든 형식과 함께 `fixed` 문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-313">You can use `fixed` statements with any type that supports a pattern.</span></span>
- <span data-ttu-id="fde57-314">추가적인 제네릭 제약 조건을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-314">You can use additional generic constraints.</span></span>
- <span data-ttu-id="fde57-315">매개 변수의 `in` 한정자는 인수가 참조에 의해 전달되지만 호출된 메서드에 의해 수정되지 않도록 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-315">The `in` modifier on parameters, to specify that an argument is passed by reference but not modified by the called method.</span></span> <span data-ttu-id="fde57-316">`in` 한정자를 인수에 추가하는 것은 [소스 호환 가능 변경](version-update-considerations.md#source-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-316">Adding the `in` modifier to an argument is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span>
- <span data-ttu-id="fde57-317">메서드의 `ref readonly` 한정자는 메서드가 참조별 값을 반환하지만 해당 개체에 대한 쓰기를 허용하지 않음을 나타내기 위해 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-317">The `ref readonly` modifier on method returns, to indicate that a method returns its value by reference but doesn't allow writes to that object.</span></span> <span data-ttu-id="fde57-318">반환이 값에 할당되는 경우 `ref readonly` 한정자를 추가하는 것은 [소스 호환 가능 변경](version-update-considerations.md#source-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-318">Adding the `ref readonly` modifier is a [source compatible change](version-update-considerations.md#source-compatible-changes), if the return is assigned to a value.</span></span> <span data-ttu-id="fde57-319">기존 `ref` 반환 문에 `readonly` 한정자를 추가하는 것은 [호환되지 않는 변경](version-update-considerations.md#incompatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-319">Adding the `readonly` modifier to an existing `ref` return statement is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="fde57-320">호출자가 `readonly` 한정자를 포함하도록 `ref` 지역 변수의 선언을 업데이트하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-320">It requires callers to update the declaration of `ref` local variables to include the `readonly` modifier.</span></span>
- <span data-ttu-id="fde57-321">`readonly struct` 선언은 구조체가 변경 가능하지 않으며 `in` 매개 변수로서 멤버 메서드로 전달되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-321">The `readonly struct` declaration, to indicate that a struct is immutable and should be passed as an `in` parameter to its member methods.</span></span> <span data-ttu-id="fde57-322">기존 구조체 선언에 `readonly` 한정자를 추가하는 것은 [이진 호환 가능 변경](version-update-considerations.md#binary-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-322">Adding the `readonly` modifier to an existing struct declaration is a [binary compatible change](version-update-considerations.md#binary-compatible-changes).</span></span>
- <span data-ttu-id="fde57-323">`ref struct` 선언은 구조체 유형이 관리되는 메모리에 직접 액세스하고 항상 스택에 할당되어야 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-323">The `ref struct` declaration, to indicate that a struct type accesses managed memory directly and must always be stack allocated.</span></span> <span data-ttu-id="fde57-324">기존 `struct` 선언에 `ref` 한정자를 추가하는 것은 [호환되지 않는 변경](version-update-considerations.md#incompatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-324">Adding the `ref` modifier to an existing `struct` declaration is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="fde57-325">`ref struct`는 클래스의 멤버가 되거나 힙에 할당될 수 있는 다른 위치에서 사용될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-325">A `ref struct` cannot be a member of a class or used in other locations where it may be allocated on the heap.</span></span>

<span data-ttu-id="fde57-326">[안전하고 효율적인 코드 작성](../write-safe-efficient-code.md)에서 모든 변경 내용을 자세히 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-326">You can read more about all these changes in [Write safe efficient code](../write-safe-efficient-code.md).</span></span>

### <a name="ref-locals-and-returns"></a><span data-ttu-id="fde57-327">Ref local 및 return</span><span class="sxs-lookup"><span data-stu-id="fde57-327">Ref locals and returns</span></span>

<span data-ttu-id="fde57-328">이 기능을 통해 다른 곳에 정의된 변수에 대한 참조를 사용 및 반환하는 알고리즘이 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-328">This feature enables algorithms that use and return references to variables defined elsewhere.</span></span> <span data-ttu-id="fde57-329">한 가지 예는 큰 매트릭스를 사용하고 특정 특징을 가진 하나의 위치를 찾는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-329">One example is working with large matrices, and finding a single location with certain characteristics.</span></span> <span data-ttu-id="fde57-330">다음 메서드는 **참조** 를 행렬의 해당 스토리지에 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-330">The following method returns a **reference** to that storage in the matrix:</span></span>

[!code-csharp[FindReturningRef](~/samples/snippets/csharp/new-in-7/MatrixSearch.cs#FindReturningRef "Find returning by reference")]

<span data-ttu-id="fde57-331">다음 코드에서처럼 반환 값을 `ref`로 선언하고 행렬에서 해당 값을 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-331">You can declare the return value as a `ref` and modify that value in the matrix, as shown in the following code:</span></span>

[!code-csharp[AssignRefReturn](~/samples/snippets/csharp/new-in-7/Program.cs#AssignRefReturn "Assign ref return")]

<span data-ttu-id="fde57-332">C# 언어에는 `ref` 로컬 및 반환을 잘못 사용하지 않도록 방지하는 몇 가지 규칙이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-332">The C# language has several rules that protect you from misusing the `ref` locals and returns:</span></span>

- <span data-ttu-id="fde57-333">`ref` 키워드를 메서드 서명 및 메서드의 모든 `return` 문에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-333">You must add the `ref` keyword to the method signature and to all `return` statements in a method.</span></span>
  - <span data-ttu-id="fde57-334">그러면 메서드가 메서드 전체에서 참조별로 반환되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-334">That makes it clear the method returns by reference throughout the method.</span></span>
- <span data-ttu-id="fde57-335">`ref return`은 값 변수 또는 `ref` 변수에 할당될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-335">A `ref return` may be assigned to a value variable, or a `ref` variable.</span></span>
  - <span data-ttu-id="fde57-336">호출자는 반환 값을 복사할지 여부를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-336">The caller controls whether the return value is copied or not.</span></span> <span data-ttu-id="fde57-337">반환 값을 할당할 때 `ref` 한정자를 생략하면 호출자가 스토리지에 대한 참조가 아닌 값의 복사본을 요청한다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-337">Omitting the `ref` modifier when assigning the return value indicates that the caller wants a copy of the value, not a reference to the storage.</span></span>
- <span data-ttu-id="fde57-338">표준 메서드 반환 값을 `ref` 로컬 변수에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-338">You can't assign a standard method return value to a `ref` local variable.</span></span>
  - <span data-ttu-id="fde57-339">이로 인해 `ref int i = sequence.Count();` 같은 문이 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-339">That disallows statements like `ref int i = sequence.Count();`</span></span>
- <span data-ttu-id="fde57-340">메서드 실행보다 길게 수명이 연장되지 않는 변수에 `ref`를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-340">You can't return a `ref` to a variable whose lifetime doesn't extend beyond the execution of the method.</span></span>
  - <span data-ttu-id="fde57-341">즉, 로컬 변수 또는 비슷한 범위의 변수에 참조를 반환할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-341">That means you can't return a reference to a local variable or a variable with a similar scope.</span></span>
- <span data-ttu-id="fde57-342">`ref` local 및 return은 비동기 메서드와 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-342">`ref` locals and returns can't be used with async methods.</span></span>
  - <span data-ttu-id="fde57-343">컴파일러는 비동기 메서드가 반환될 때 참조된 변수가 최종 값으로 설정되었는지 여부를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-343">The compiler can't know if the referenced variable has been set to its final value when the async method returns.</span></span>

<span data-ttu-id="fde57-344">ref local 및 ref return을 추가하면 값을 복사하거나 역참조 작업을 여러 번 수행하는 경우를 방지하여 더 효율적인 알고리즘이 가능해집니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-344">The addition of ref locals and ref returns enables algorithms that are more efficient by avoiding copying values, or performing dereferencing operations multiple times.</span></span>

<span data-ttu-id="fde57-345">`ref`를 반환 값에 추가하는 것은 [소스 호환 가능 변경](version-update-considerations.md#source-compatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-345">Adding `ref` to the return value is a [source compatible change](version-update-considerations.md#source-compatible-changes).</span></span> <span data-ttu-id="fde57-346">기존 코드는 컴파일되지만, 참조 반환 값은 할당 시 복사됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-346">Existing code compiles, but the ref return value is copied when assigned.</span></span> <span data-ttu-id="fde57-347">호출자는 반환 값 스토리지를 `ref` 지역 변수로 업데이트하여 반환을 참조로 저장해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-347">Callers must update the storage for the return value to a `ref` local variable to store the return as a reference.</span></span>

<span data-ttu-id="fde57-348">이제 `ref` 지역 변수를 다시 할당하여 초기화된 후 다른 인스턴스를 참조할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-348">Now, `ref` locals may be reassigned to refer to different instances after being initialized.</span></span> <span data-ttu-id="fde57-349">이제 다음 코드가 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-349">The following code now compiles:</span></span>

```csharp
ref VeryLargeStruct refLocal = ref veryLargeStruct; // initialization
refLocal = ref anotherVeryLargeStruct; // reassigned, refLocal refers to different storage.
```

<span data-ttu-id="fde57-350">자세한 내용은 [`ref` 반환 및 `ref` 지역](../programming-guide/classes-and-structs/ref-returns.md)에 대한 아티클 및 [`foreach`](../language-reference/keywords/foreach-in.md)에 대한 아티클을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-350">For more information, see the article on [`ref` returns and `ref` locals](../programming-guide/classes-and-structs/ref-returns.md), and the article on [`foreach`](../language-reference/keywords/foreach-in.md).</span></span>

<span data-ttu-id="fde57-351">자세한 내용은 [ref 키워드](../language-reference/keywords/ref.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-351">For more information, see the [ref keyword](../language-reference/keywords/ref.md) article.</span></span>

### <a name="conditional-ref-expressions"></a><span data-ttu-id="fde57-352">조건부 `ref` 식</span><span class="sxs-lookup"><span data-stu-id="fde57-352">Conditional `ref` expressions</span></span>

<span data-ttu-id="fde57-353">마지막으로, 조건식은 값 결과 대신 참조 결과를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-353">Finally, the conditional expression may produce a ref result instead of a value result.</span></span> <span data-ttu-id="fde57-354">예를 들어 다음을 작성하여 두 배열 중 하나의 첫 번째 요소에 대한 참조를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-354">For example, you would write the following to retrieve a reference to the first element in one of two arrays:</span></span>

```csharp
ref var r = ref (arr != null ? ref arr[0] : ref otherArr[0]);
```

<span data-ttu-id="fde57-355">`r` 변수는 `arr` 또는 `otherArr`의 첫 번째 값에 대한 참조입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-355">The variable `r` is a reference to the first value in either `arr` or `otherArr`.</span></span>

<span data-ttu-id="fde57-356">자세한 내용은 언어 참조에서 [조건부 연산자(?:)](../language-reference/operators/conditional-operator.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-356">For more information, see [conditional operator (?:)](../language-reference/operators/conditional-operator.md) in the language reference.</span></span>

### <a name="in-parameter-modifier"></a><span data-ttu-id="fde57-357">`in` 매개 변수 한정자</span><span class="sxs-lookup"><span data-stu-id="fde57-357">`in` parameter modifier</span></span>

<span data-ttu-id="fde57-358">`in` 키워드는 기존 ref 및 out 키워드를 보완하여 참조로 인수를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-358">The `in` keyword complements the existing ref and out keywords to pass arguments by reference.</span></span> <span data-ttu-id="fde57-359">`in` 키워드는 인수를 참조로 전달하도록 지정하지만 호출된 메서드는 값을 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-359">The `in` keyword specifies passing the argument by reference, but the called method doesn't modify the value.</span></span>

<span data-ttu-id="fde57-360">다음 코드와 같이 값 또는 읽기 전용 참조로 전달되는 오버로드를 선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-360">You may declare overloads that pass by value or by readonly reference, as shown in the following code:</span></span>

```csharp
static void M(S arg);
static void M(in S arg);
```

<span data-ttu-id="fde57-361">값으로 전달(이전 예제의 첫 번째 경우) 오버로드가 읽기 전용 참조로 전달 버전보다 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-361">The by value (first in the preceding example) overload is better than the by readonly reference version.</span></span> <span data-ttu-id="fde57-362">읽기 전용 참조 인수를 사용하여 버전을 호출하려면 메서드를 호출할 때 `in` 한정자를 포함해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-362">To call the version with the readonly reference argument, you must include the `in` modifier when calling the method.</span></span>

<span data-ttu-id="fde57-363">자세한 내용은 [`in` 매개 변수 한정자](../language-reference/keywords/in-parameter-modifier.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-363">For more information, see the article on the [`in` parameter modifier](../language-reference/keywords/in-parameter-modifier.md).</span></span>

### <a name="more-types-support-the-fixed-statement"></a><span data-ttu-id="fde57-364">더 많은 형식이 `fixed` 문을 지원함</span><span class="sxs-lookup"><span data-stu-id="fde57-364">More types support the `fixed` statement</span></span>

<span data-ttu-id="fde57-365">`fixed` 문은 제한된 형식 집합을 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-365">The `fixed` statement supported a limited set of types.</span></span> <span data-ttu-id="fde57-366">C# 7.3부터 `ref T` 또는 `ref readonly T`를 반환하는 `GetPinnableReference()` 메서드를 포함하는 모든 형식이 `fixed`일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-366">Starting with C# 7.3, any type that contains a `GetPinnableReference()` method that returns a `ref T` or `ref readonly T` may be `fixed`.</span></span> <span data-ttu-id="fde57-367">이 기능을 추가하면 `fixed`를 <xref:System.Span%601?displayProperty=nameWithType> 및 관련 형식과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-367">Adding this feature means that `fixed` can be used with <xref:System.Span%601?displayProperty=nameWithType> and related types.</span></span>

<span data-ttu-id="fde57-368">자세한 내용은 언어 참조에서 [`fixed` 문](../language-reference/keywords/fixed-statement.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-368">For more information, see the [`fixed` statement](../language-reference/keywords/fixed-statement.md) article in the language reference.</span></span>

### <a name="indexing-fixed-fields-does-not-require-pinning"></a><span data-ttu-id="fde57-369">`fixed` 필드 인덱싱에 고정이 필요하지 않음</span><span class="sxs-lookup"><span data-stu-id="fde57-369">Indexing `fixed` fields does not require pinning</span></span>

<span data-ttu-id="fde57-370">다음 구조체를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-370">Consider this struct:</span></span>

```csharp
unsafe struct S
{
    public fixed int myFixedField[10];
}
```

<span data-ttu-id="fde57-371">이전 버전의 C#에서는 `myFixedField`의 일부인 정수 중 하나에 액세스하려면 변수를 고정해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-371">In earlier versions of C#, you needed to pin a variable to access one of the integers that are part of `myFixedField`.</span></span> <span data-ttu-id="fde57-372">이제 다음 코드는 별도의 `fixed` 문 안에 `p` 변수를 고정하지 않고 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-372">Now, the following code compiles without pinning the variable `p` inside a separate `fixed` statement:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        int p = s.myFixedField[5];
    }
}
```

<span data-ttu-id="fde57-373">`p` 변수는 `myFixedField`의 한 요소에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-373">The variable `p` accesses one element in `myFixedField`.</span></span> <span data-ttu-id="fde57-374">별도의 `int*` 변수를 선언할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-374">You don't need to declare a separate `int*` variable.</span></span> <span data-ttu-id="fde57-375">`unsafe` 컨텍스트는 여전히 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-375">You still need an `unsafe` context.</span></span> <span data-ttu-id="fde57-376">이전 버전의 C#에서는 두 번째 고정된 포인터를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-376">In earlier versions of C#, you need to declare a second fixed pointer:</span></span>

```csharp
class C
{
    static S s = new S();

    unsafe public void M()
    {
        fixed (int* ptr = s.myFixedField)
        {
            int p = ptr[5];
        }
    }
}
```

<span data-ttu-id="fde57-377">자세한 내용은 [`fixed` 문](../language-reference/keywords/fixed-statement.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-377">For more information, see the article on the [`fixed` statement](../language-reference/keywords/fixed-statement.md).</span></span>

### <a name="stackalloc-arrays-support-initializers"></a><span data-ttu-id="fde57-378">`stackalloc` 배열이 이니셜라이저를 지원함</span><span class="sxs-lookup"><span data-stu-id="fde57-378">`stackalloc` arrays support initializers</span></span>

<span data-ttu-id="fde57-379">초기화할 때 배열의 요소 값을 지정할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-379">You've been able to specify the values for elements in an array when you initialize it:</span></span>

```csharp
var arr = new int[3] {1, 2, 3};
var arr2 = new int[] {1, 2, 3};
```

<span data-ttu-id="fde57-380">이제 `stackalloc`로 선언된 배열에 동일한 구문을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-380">Now, that same syntax can be applied to arrays that are declared with `stackalloc`:</span></span>

```csharp
int* pArr = stackalloc int[3] {1, 2, 3};
int* pArr2 = stackalloc int[] {1, 2, 3};
Span<int> arr = stackalloc [] {1, 2, 3};
```

<span data-ttu-id="fde57-381">자세한 내용은 [`stackalloc` 연산자](../language-reference/operators/stackalloc.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-381">For more information, see the [`stackalloc` operator](../language-reference/operators/stackalloc.md) article.</span></span>

### <a name="enhanced-generic-constraints"></a><span data-ttu-id="fde57-382">향상된 제네릭 제약 조건</span><span class="sxs-lookup"><span data-stu-id="fde57-382">Enhanced generic constraints</span></span>

<span data-ttu-id="fde57-383">이제 형식 매개 변수에 대한 기본 클래스 제약 조건으로 <xref:System.Enum?displayProperty=nameWithType> 또는 <xref:System.Delegate?displayProperty=nameWithType> 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-383">You can now specify the type <xref:System.Enum?displayProperty=nameWithType> or <xref:System.Delegate?displayProperty=nameWithType> as base class constraints for a type parameter.</span></span>

<span data-ttu-id="fde57-384">또한 새 `unmanaged` 제약 조건을 사용하여 형식 매개 변수가 nullable이 아닌 [비관리형 형식](../language-reference/builtin-types/unmanaged-types.md)이 되도록 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-384">You can also use the new `unmanaged` constraint, to specify that a type parameter must be a non-nullable [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span>

<span data-ttu-id="fde57-385">자세한 내용은 [`where` 제네릭 제약 조건](../language-reference/keywords/where-generic-type-constraint.md) 및 [형식 매개 변수 제약 조건](../programming-guide/generics/constraints-on-type-parameters.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-385">For more information, see the articles on [`where` generic constraints](../language-reference/keywords/where-generic-type-constraint.md) and [constraints on type parameters](../programming-guide/generics/constraints-on-type-parameters.md).</span></span>

<span data-ttu-id="fde57-386">기존 형식에 이러한 제약 조건을 추가하는 것은 [호환되지 않는 변경](version-update-considerations.md#incompatible-changes)입니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-386">Adding these constraints to existing types is an [incompatible change](version-update-considerations.md#incompatible-changes).</span></span> <span data-ttu-id="fde57-387">폐쇄형 제네릭 형식은 더 이상 이러한 새 제약 조건을 충족할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-387">Closed generic types may no longer meet these new constraints.</span></span>

### <a name="generalized-async-return-types"></a><span data-ttu-id="fde57-388">일반화된 비동기 반환 형식</span><span class="sxs-lookup"><span data-stu-id="fde57-388">Generalized async return types</span></span>

<span data-ttu-id="fde57-389">비동기 메서드에서 `Task` 개체를 반환하면 특정 경로에 성능 병목 현상이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-389">Returning a `Task` object from async methods can introduce performance bottlenecks in certain paths.</span></span> <span data-ttu-id="fde57-390">`Task`는 참조 형식이므로 이를 사용하는 것은 개체 할당을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-390">`Task` is a reference type, so using it means allocating an object.</span></span> <span data-ttu-id="fde57-391">`async` 한정자로 선언된 메서드가 캐시된 결과를 반환하거나 동기적으로 완료된 경우 코드의 성능이 중요한 섹션에서 추가 할당에 상당한 시간이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-391">In cases where a method declared with the `async` modifier returns a cached result, or completes synchronously, the extra allocations can become a significant time cost in performance critical sections of code.</span></span> <span data-ttu-id="fde57-392">연속 루프에서 이러한 할당이 발생하면 부담이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-392">It can become costly if those allocations occur in tight loops.</span></span>

<span data-ttu-id="fde57-393">새로운 언어 기능을 통해 비동기 메서드 반환 형식이 `Task`, `Task<T>` 및 `void`에 제한되지 않게 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-393">The new language feature means that async method return types aren't limited to `Task`, `Task<T>`, and `void`.</span></span> <span data-ttu-id="fde57-394">반환된 형식은 비동기 패턴을 충족해야 합니다. 즉, `GetAwaiter` 메서드에 액세스할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-394">The returned type must still satisfy the async pattern, meaning a `GetAwaiter` method must be accessible.</span></span> <span data-ttu-id="fde57-395">한 가지 구체적인 예로 이 새로운 언어 기능을 사용할 수 있도록 `ValueTask` 형식이 .NET에 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-395">As one concrete example, the `ValueTask` type has been added to .NET to make use of this new language feature:</span></span>

[!code-csharp[UsingValueTask](~/samples/snippets/csharp/new-in-7/AsyncWork.cs#UsingValueTask "Using ValueTask")]

> [!NOTE]
> <span data-ttu-id="fde57-396"><xref:System.Threading.Tasks.ValueTask%601> 형식을 사용하려면 NuGet 패키지 [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/)를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-396">You need to add the NuGet package [`System.Threading.Tasks.Extensions`](https://www.nuget.org/packages/System.Threading.Tasks.Extensions/) > in order to use the <xref:System.Threading.Tasks.ValueTask%601> type.</span></span>

<span data-ttu-id="fde57-397">이 개선 사항은 라이브러리 작성자가 성능이 중요한 코드에서 `Task`를 할당하지 않도록 방지하는 데 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-397">This enhancement is most useful for library authors to avoid allocating a `Task` in performance critical code.</span></span>

## <a name="new-compiler-options"></a><span data-ttu-id="fde57-398">새로운 컴파일러 옵션</span><span class="sxs-lookup"><span data-stu-id="fde57-398">New compiler options</span></span>

<span data-ttu-id="fde57-399">새로운 컴파일러 옵션은 C# 프로그램에 대한 새로운 빌드 및 DevOps 시나리오를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-399">New compiler options support new build and DevOps scenarios for C# programs.</span></span>

### <a name="reference-assembly-generation"></a><span data-ttu-id="fde57-400">참조 어셈블리 생성</span><span class="sxs-lookup"><span data-stu-id="fde57-400">Reference assembly generation</span></span>

<span data-ttu-id="fde57-401">*참조 전용 어셈블리* 를 생성하는 두 가지 새로운 컴파일러 옵션인 [**ProduceReferenceAssembly**](../language-reference/compiler-options/output.md#producereferenceassembly) 및 [**ProduceOnlyReferenceAssembly**](../language-reference/compiler-options/code-generation.md#produceonlyreferenceassembly)가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-401">There are two new compiler options that generate *reference-only assemblies*: [**ProduceReferenceAssembly**](../language-reference/compiler-options/output.md#producereferenceassembly) and [**ProduceOnlyReferenceAssembly**](../language-reference/compiler-options/code-generation.md#produceonlyreferenceassembly).</span></span>
<span data-ttu-id="fde57-402">연결된 문서에서는 이러한 옵션과 참조 어셈블리를 보다 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-402">The linked articles explain these options and reference assemblies in more detail.</span></span>

### <a name="public-or-open-source-signing"></a><span data-ttu-id="fde57-403">공개 또는 오픈 소스 서명</span><span class="sxs-lookup"><span data-stu-id="fde57-403">Public or Open Source signing</span></span>

<span data-ttu-id="fde57-404">**PublicSign** 컴파일러 옵션은 공개 키를 사용하여 어셈블리에 서명하도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-404">The **PublicSign** compiler option instructs the compiler to sign the assembly using a public key.</span></span> <span data-ttu-id="fde57-405">어셈블리는 서명됨으로 표시되지만 시그니처는 공개 키에서 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-405">The assembly is marked as signed, but the signature is taken from the public key.</span></span> <span data-ttu-id="fde57-406">이 옵션을 사용하면 공개 키를 사용하여 오픈 소스 프로젝트에서 서명된 어셈블리를 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-406">This option enables you to build signed assemblies from open-source projects using a public key.</span></span>

<span data-ttu-id="fde57-407">자세한 내용은 [**PublicSign** 컴파일러 옵션](../language-reference/compiler-options/security.md#publicsign) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-407">For more information, see the [**PublicSign** compiler option](../language-reference/compiler-options/security.md#publicsign) article.</span></span>

### <a name="pathmap"></a><span data-ttu-id="fde57-408">pathmap</span><span class="sxs-lookup"><span data-stu-id="fde57-408">pathmap</span></span>

<span data-ttu-id="fde57-409">**PathMap** 컴파일러 옵션은 빌드 환경의 소스 경로를 매핑된 소스 경로로 바꾸도록 컴파일러에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-409">The **PathMap** compiler option instructs the compiler to replace source paths from the build environment with mapped source paths.</span></span> <span data-ttu-id="fde57-410">**PathMap** 옵션은 컴파일러가 PDB 파일 또는 <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>에 대해 작성한 소스 경로를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="fde57-410">The **PathMap** option controls the source path written by the compiler to PDB files or for the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute>.</span></span>

<span data-ttu-id="fde57-411">자세한 내용은 [**PathMap** 컴파일러 옵션](../language-reference/compiler-options/advanced.md#pathmap) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fde57-411">For more information, see the [**PathMap** compiler option](../language-reference/compiler-options/advanced.md#pathmap) article.</span></span>
