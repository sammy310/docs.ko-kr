---
title: C# 8.0의 새로운 기능 - C# 가이드
description: C# 8.0의 새로운 기능을 살펴봅니다.
ms.date: 04/07/2020
ms.openlocfilehash: 27c2d7e2d6f0e665e7abe4fdcfb94c140224cc89
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895429"
---
# <a name="whats-new-in-c-80"></a><span data-ttu-id="b4e23-103">C# 8.0의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="b4e23-103">What's new in C# 8.0</span></span>

<span data-ttu-id="b4e23-104">C#8.0은 다음 기능 및 향상된 기능을 C# 언어에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-104">C# 8.0 adds the following features and enhancements to the C# language:</span></span>

- [<span data-ttu-id="b4e23-105">읽기 전용 멤버</span><span class="sxs-lookup"><span data-stu-id="b4e23-105">Readonly members</span></span>](#readonly-members)
- [<span data-ttu-id="b4e23-106">기본 인터페이스 메서드</span><span class="sxs-lookup"><span data-stu-id="b4e23-106">Default interface methods</span></span>](#default-interface-methods)
- <span data-ttu-id="b4e23-107">[패턴 일치 개선 사항](#more-patterns-in-more-places):</span><span class="sxs-lookup"><span data-stu-id="b4e23-107">[Pattern matching enhancements](#more-patterns-in-more-places):</span></span>
  - [<span data-ttu-id="b4e23-108">Switch 식</span><span class="sxs-lookup"><span data-stu-id="b4e23-108">Switch expressions</span></span>](#switch-expressions)
  - [<span data-ttu-id="b4e23-109">속성 패턴</span><span class="sxs-lookup"><span data-stu-id="b4e23-109">Property patterns</span></span>](#property-patterns)
  - [<span data-ttu-id="b4e23-110">튜플 패턴</span><span class="sxs-lookup"><span data-stu-id="b4e23-110">Tuple patterns</span></span>](#tuple-patterns)
  - [<span data-ttu-id="b4e23-111">위치 패턴</span><span class="sxs-lookup"><span data-stu-id="b4e23-111">Positional patterns</span></span>](#positional-patterns)
- [<span data-ttu-id="b4e23-112">using 선언</span><span class="sxs-lookup"><span data-stu-id="b4e23-112">Using declarations</span></span>](#using-declarations)
- [<span data-ttu-id="b4e23-113">정적 로컬 함수</span><span class="sxs-lookup"><span data-stu-id="b4e23-113">Static local functions</span></span>](#static-local-functions)
- [<span data-ttu-id="b4e23-114">삭제 가능한 ref struct</span><span class="sxs-lookup"><span data-stu-id="b4e23-114">Disposable ref structs</span></span>](#disposable-ref-structs)
- [<span data-ttu-id="b4e23-115">nullable 참조 형식</span><span class="sxs-lookup"><span data-stu-id="b4e23-115">Nullable reference types</span></span>](#nullable-reference-types)
- [<span data-ttu-id="b4e23-116">비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="b4e23-116">Asynchronous streams</span></span>](#asynchronous-streams)
- [<span data-ttu-id="b4e23-117">비동기 삭제 가능</span><span class="sxs-lookup"><span data-stu-id="b4e23-117">Asynchronous disposable</span></span>](#asynchronous-disposable)
- [<span data-ttu-id="b4e23-118">인덱스 및 범위</span><span class="sxs-lookup"><span data-stu-id="b4e23-118">Indices and ranges</span></span>](#indices-and-ranges)
- [<span data-ttu-id="b4e23-119">null 병합 할당</span><span class="sxs-lookup"><span data-stu-id="b4e23-119">Null-coalescing assignment</span></span>](#null-coalescing-assignment)
- [<span data-ttu-id="b4e23-120">관리되지 않는 생성 형식</span><span class="sxs-lookup"><span data-stu-id="b4e23-120">Unmanaged constructed types</span></span>](#unmanaged-constructed-types)
- [<span data-ttu-id="b4e23-121">중첩 식의 stackalloc</span><span class="sxs-lookup"><span data-stu-id="b4e23-121">Stackalloc in nested expressions</span></span>](#stackalloc-in-nested-expressions)
- [<span data-ttu-id="b4e23-122">보간된 약어 문자열의 향상된 기능</span><span class="sxs-lookup"><span data-stu-id="b4e23-122">Enhancement of interpolated verbatim strings</span></span>](#enhancement-of-interpolated-verbatim-strings)

<span data-ttu-id="b4e23-123">C#8.0은 **.NET Core 3.x** 및 **.NET Standard 2.1**에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-123">C# 8.0 is supported on **.NET Core 3.x** and **.NET Standard 2.1**.</span></span> <span data-ttu-id="b4e23-124">자세한 내용은 [C# 언어 버전 관리](../language-reference/configure-language-version.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-124">For more information, see [C# language versioning](../language-reference/configure-language-version.md).</span></span>

<span data-ttu-id="b4e23-125">이 문서의 나머지 부분에서는 이러한 기능에 대해 간략하게 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-125">The remainder of this article briefly describes these features.</span></span> <span data-ttu-id="b4e23-126">심화 문서가 공개되면 해당 자습서에 대한 링크 및 개요가 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-126">Where in-depth articles are available, links to those tutorials and overviews are provided.</span></span> <span data-ttu-id="b4e23-127">`dotnet try` 글로벌 도구를 사용하여 환경에서 다음과 같은 기능을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-127">You can explore these features in your environment using the `dotnet try` global tool:</span></span>

1. <span data-ttu-id="b4e23-128">[dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) 글로벌 도구를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-128">Install the [dotnet-try](https://github.com/dotnet/try/blob/master/README.md#setup) global tool.</span></span>
1. <span data-ttu-id="b4e23-129">[dotnet/try-samples](https://github.com/dotnet/try-samples) 리포지토리를 복제합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-129">Clone the [dotnet/try-samples](https://github.com/dotnet/try-samples) repository.</span></span>
1. <span data-ttu-id="b4e23-130">현재 디렉터리를 *try-samples* 리포지토리의 *csharp8* 하위 디렉터리로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-130">Set the current directory to the *csharp8* subdirectory for the *try-samples* repository.</span></span>
1. <span data-ttu-id="b4e23-131">`dotnet try`를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-131">Run `dotnet try`.</span></span>

## <a name="readonly-members"></a><span data-ttu-id="b4e23-132">읽기 전용 멤버</span><span class="sxs-lookup"><span data-stu-id="b4e23-132">Readonly members</span></span>

<span data-ttu-id="b4e23-133">구조체의 멤버에 `readonly` 한정자를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-133">You can apply the `readonly` modifier to members of a struct.</span></span> <span data-ttu-id="b4e23-134">이 한정자는 멤버가 상태를 수정하지 않음을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-134">It indicates that the member doesn't modify state.</span></span> <span data-ttu-id="b4e23-135">이것이 `readonly` 한정자를 `struct` 선언에 적용하는 것보다 더 세부적입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-135">It's more granular than applying the `readonly` modifier to a `struct` declaration.</span></span>  <span data-ttu-id="b4e23-136">다음과 같이 변경 가능한 구조체를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-136">Consider the following mutable struct:</span></span>

```csharp
public struct Point
{
    public double X { get; set; }
    public double Y { get; set; }
    public double Distance => Math.Sqrt(X * X + Y * Y);

    public override string ToString() =>
        $"({X}, {Y}) is {Distance} from the origin";
}
```

<span data-ttu-id="b4e23-137">대부분의 구조체와 마찬가지로 `ToString()` 메서드는 상태를 수정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-137">Like most structs, the `ToString()` method doesn't modify state.</span></span> <span data-ttu-id="b4e23-138">`readonly` 한정자를 `ToString()`의 선언에 추가하여 다음을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-138">You could indicate that by adding the `readonly` modifier to the declaration of `ToString()`:</span></span>

```csharp
public readonly override string ToString() =>
    $"({X}, {Y}) is {Distance} from the origin";
```

<span data-ttu-id="b4e23-139">`ToString`은 `readonly`로 표시되지 않은 `Distance` 속성에 액세스하므로 위와 같이 변경할 경우 컴파일러 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-139">The preceding change generates a compiler warning, because `ToString` accesses the `Distance` property, which isn't marked `readonly`:</span></span>

```console
warning CS8656: Call to non-readonly member 'Point.Distance.get' from a 'readonly' member results in an implicit copy of 'this'
```

<span data-ttu-id="b4e23-140">컴파일러는 방어 복사본을 만들 필요가 있을 때 사용자에게 경고합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-140">The compiler warns you when it needs to create a defensive copy.</span></span>  <span data-ttu-id="b4e23-141">`Distance` 속성은 상태를 변경하지 않으므로 `readonly` 한정자를 선언에 추가하여 이 경고를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-141">The `Distance` property doesn't change state, so you can fix this warning by adding the `readonly` modifier to the declaration:</span></span>

```csharp
public readonly double Distance => Math.Sqrt(X * X + Y * Y);
```

<span data-ttu-id="b4e23-142">읽기 전용 속성에는 `readonly` 한정자가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-142">Notice that the `readonly` modifier is necessary on a read-only property.</span></span> <span data-ttu-id="b4e23-143">컴파일러는 `get` 접근자가 상태를 수정하지 않는다고 가정하지 않습니다. 명시적으로 `readonly`를 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-143">The compiler doesn't assume `get` accessors don't modify state; you must declare `readonly` explicitly.</span></span> <span data-ttu-id="b4e23-144">단, 자동 구현 속성은 예외입니다. 컴파일러에서 모든 자동 구현 getter를 `readonly`로 처리하므로 예제의 `X` 및 `Y` 속성에는 `readonly` 한정자를 추가할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-144">Auto-implemented properties are an exception; the compiler will treat all auto-implemented getters as `readonly`, so here there's no need to add the `readonly` modifier to the `X` and `Y` properties.</span></span>

<span data-ttu-id="b4e23-145">컴파일러는 `readonly` 멤버가 상태를 수정하지 않는다는 규칙을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-145">The compiler does enforce the rule that `readonly` members don't modify state.</span></span> <span data-ttu-id="b4e23-146">`readonly` 한정자를 제거하지 않을 경우 다음 메서드는 컴파일되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-146">The following method won't compile unless you remove the `readonly` modifier:</span></span>

```csharp
public readonly void Translate(int xOffset, int yOffset)
{
    X += xOffset;
    Y += yOffset;
}
```

<span data-ttu-id="b4e23-147">이 기능을 사용하여 디자인 의도를 지정할 수 있으므로 컴파일러는 이를 적용하고 디자인 의도에 따라 최적화를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-147">This feature lets you specify your design intent so the compiler can enforce it, and make optimizations based on that intent.</span></span>

<span data-ttu-id="b4e23-148">자세한 내용은 [구조체 형식](../language-reference/builtin-types/struct.md) 문서의 [`readonly` 인스턴스 멤버](../language-reference/builtin-types/struct.md#readonly-instance-members) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-148">For more information, see the [`readonly` instance members](../language-reference/builtin-types/struct.md#readonly-instance-members) section of the [Structure types](../language-reference/builtin-types/struct.md) article.</span></span>

## <a name="default-interface-methods"></a><span data-ttu-id="b4e23-149">기본 인터페이스 메서드</span><span class="sxs-lookup"><span data-stu-id="b4e23-149">Default interface methods</span></span>

<span data-ttu-id="b4e23-150">이제 인터페이스에 멤버를 추가하고 해당 멤버에 대 한 구현을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-150">You can now add members to interfaces and provide an implementation for those members.</span></span> <span data-ttu-id="b4e23-151">이 언어 기능을 사용하여 API 작성자는 소스 또는 이진과 해당 인터페이스의 기존 구현과의 호환성에 영향을 미치지 않고 후속 버전에서 인터페이스에 메서드를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-151">This language feature enables API authors to add methods to an interface in later versions without breaking source or binary compatibility with existing implementations of that interface.</span></span> <span data-ttu-id="b4e23-152">기존 구현은 기본 구현을 *상속*합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-152">Existing implementations *inherit* the default implementation.</span></span> <span data-ttu-id="b4e23-153">또한 이 기능을 사용하여 C#은 유사한 기능을 지원하는 Android 또는 Swift를 대상으로 하는 API와 상호 운용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-153">This feature also enables C# to interoperate with APIs that target Android or Swift, which support similar features.</span></span> <span data-ttu-id="b4e23-154">또한 기본 인터페이스 메서드는 “특성” 언어 기능과 유사한 시나리오를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-154">Default interface methods also enable scenarios similar to a "traits" language feature.</span></span>

<span data-ttu-id="b4e23-155">기본 인터페이스 메서드는 많은 시나리오와 언어 요소에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-155">Default interface methods affect many scenarios and language elements.</span></span> <span data-ttu-id="b4e23-156">첫 번째 자습서에서는 [기본 구현으로 인터페이스 업데이트](../tutorials/default-interface-methods-versions.md)에 대해 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-156">Our first tutorial covers [updating an interface with default implementations](../tutorials/default-interface-methods-versions.md).</span></span> <span data-ttu-id="b4e23-157">다른 자습서 및 참조 업데이트는 일반 릴리스 시점에 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-157">Other tutorials and reference updates are coming in time for general release.</span></span>

## <a name="more-patterns-in-more-places"></a><span data-ttu-id="b4e23-158">더 많은 곳에서 더 많은 패턴 사용</span><span class="sxs-lookup"><span data-stu-id="b4e23-158">More patterns in more places</span></span>

<span data-ttu-id="b4e23-159">**패턴 일치**는 관련이 있으나 유형이 다른 데이터에서 셰이프 종속 기능을 사용할 수 있도록 지원하는 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-159">**Pattern matching** gives tools to provide shape-dependent functionality across related but different kinds of data.</span></span> <span data-ttu-id="b4e23-160">C# 7.0부터 [`is`](../language-reference/keywords/is.md) 식과 [`switch`](../language-reference/keywords/switch.md) 문을 사용하는 형식 패턴 및 상수 패턴을 위한 구문이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-160">C# 7.0 introduced syntax for type patterns and constant patterns by using the [`is`](../language-reference/keywords/is.md) expression and the [`switch`](../language-reference/keywords/switch.md) statement.</span></span> <span data-ttu-id="b4e23-161">이 기능은 데이터와 기능을 각각 별도로 구분하는 프로그래밍 패러다임을 지원하기 위한 조심스러운 첫 번째 단계입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-161">These features represented the first tentative steps toward supporting programming paradigms where data and functionality live apart.</span></span> <span data-ttu-id="b4e23-162">업계에서 마이크로 서비스와 기타 클라우드 기반 아키텍처를 도입하는 사례가 늘어남에 따라 다른 언어 도구에 대한 요구가 높아졌습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-162">As the industry moves toward more microservices and other cloud-based architectures, other language tools are needed.</span></span>

<span data-ttu-id="b4e23-163">C# 8.0은 코드의 더 많은 곳에서 더 많은 패턴 식을 사용할 수 있도록 이 용어를 확대합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-163">C# 8.0 expands this vocabulary so you can use more pattern expressions in more places in your code.</span></span> <span data-ttu-id="b4e23-164">데이터와 기능을 각각 별도로 구분하는 경우 이러한 기능을 고려해 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-164">Consider these features when your data and functionality are separate.</span></span> <span data-ttu-id="b4e23-165">알고리즘이 개체의 런타임 형식이 아닌 다른 요소에 종속되는 경우 패턴 일치를 고려해 보시기 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-165">Consider pattern matching when your algorithms depend on a fact other than the runtime type of an object.</span></span> <span data-ttu-id="b4e23-166">이러한 기법은 디자인을 표현할 추가적인 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-166">These techniques provide another way to express designs.</span></span>

<span data-ttu-id="b4e23-167">C# 8.0에는 더 많은 곳에서 패턴을 사용할 수 있도록 지원하는 기능에 더해 **재귀 패턴**도 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-167">In addition to new patterns in new places, C# 8.0 adds **recursive patterns**.</span></span> <span data-ttu-id="b4e23-168">패턴 식의 결과는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-168">The result of any pattern expression is an expression.</span></span> <span data-ttu-id="b4e23-169">재귀 패턴은 다른 패턴 식의 출력에 적용된 패턴 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-169">A recursive pattern is simply a pattern expression applied to the output of another pattern expression.</span></span>

### <a name="switch-expressions"></a><span data-ttu-id="b4e23-170">Switch 식</span><span class="sxs-lookup"><span data-stu-id="b4e23-170">Switch expressions</span></span>

<span data-ttu-id="b4e23-171">[`switch`](../language-reference/keywords/switch.md) 문의 결과 각각의 `case` 블록에서 값이 생성되는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-171">Often, a [`switch`](../language-reference/keywords/switch.md) statement produces a value in each of its `case` blocks.</span></span> <span data-ttu-id="b4e23-172">**Switch 식**을 사용하면 더욱더 간결한 식 구문을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-172">**Switch expressions** enable you to use more concise expression syntax.</span></span> <span data-ttu-id="b4e23-173">`case` 및 `break` 키워드를 반복적으로 사용하고 중괄호를 적용해야 하는 경우가 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-173">There are fewer repetitive `case` and `break` keywords, and fewer curly braces.</span></span>  <span data-ttu-id="b4e23-174">다음과 같이 무지개의 색을 나열하는 enum 예를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-174">As an example, consider the following enum that lists the colors of the rainbow:</span></span>

```csharp
public enum Rainbow
{
    Red,
    Orange,
    Yellow,
    Green,
    Blue,
    Indigo,
    Violet
}
```

<span data-ttu-id="b4e23-175">애플리케이션이 `R`, `G` 및 `B` 구성 요소에서 생성된 `RGBColor` 형식을 정의한 경우 switch 식을 포함하는 다음 메서드를 사용하여 `Rainbow` 값을 RGB 값으로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-175">If your application defined an `RGBColor` type that is constructed from the `R`, `G` and `B` components, you could convert a `Rainbow` value to its RGB values using the following method containing a switch expression:</span></span>

```csharp
public static RGBColor FromRainbow(Rainbow colorBand) =>
    colorBand switch
    {
        Rainbow.Red    => new RGBColor(0xFF, 0x00, 0x00),
        Rainbow.Orange => new RGBColor(0xFF, 0x7F, 0x00),
        Rainbow.Yellow => new RGBColor(0xFF, 0xFF, 0x00),
        Rainbow.Green  => new RGBColor(0x00, 0xFF, 0x00),
        Rainbow.Blue   => new RGBColor(0x00, 0x00, 0xFF),
        Rainbow.Indigo => new RGBColor(0x4B, 0x00, 0x82),
        Rainbow.Violet => new RGBColor(0x94, 0x00, 0xD3),
        _              => throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand)),
    };
```

<span data-ttu-id="b4e23-176">여기에서 몇 가지 구문 개선 사항을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-176">There are several syntax improvements here:</span></span>

- <span data-ttu-id="b4e23-177">변수가 `switch` 키워드 앞에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-177">The variable comes before the `switch` keyword.</span></span> <span data-ttu-id="b4e23-178">이처럼 순서가 변경된 결과 switch 식과 switch 문을 눈으로 구분하기가 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-178">The different order makes it visually easy to distinguish the switch expression from the switch statement.</span></span>
- <span data-ttu-id="b4e23-179">`case` 및 `:` 요소가 `=>`으로 대체되어</span><span class="sxs-lookup"><span data-stu-id="b4e23-179">The `case` and `:` elements are replaced with `=>`.</span></span> <span data-ttu-id="b4e23-180">간결성과 직관성이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-180">It's more concise and intuitive.</span></span>
- <span data-ttu-id="b4e23-181">`default` 케이스가 `_` 무시 항목으로 대체되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-181">The `default` case is replaced with a `_` discard.</span></span>
- <span data-ttu-id="b4e23-182">본문이 문이 아닌 식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-182">The bodies are expressions, not statements.</span></span>

<span data-ttu-id="b4e23-183">기존의 `switch` 문을 사용하는 동일한 코드와 비교해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-183">Contrast that with the equivalent code using the classic `switch` statement:</span></span>

```csharp
public static RGBColor FromRainbowClassic(Rainbow colorBand)
{
    switch (colorBand)
    {
        case Rainbow.Red:
            return new RGBColor(0xFF, 0x00, 0x00);
        case Rainbow.Orange:
            return new RGBColor(0xFF, 0x7F, 0x00);
        case Rainbow.Yellow:
            return new RGBColor(0xFF, 0xFF, 0x00);
        case Rainbow.Green:
            return new RGBColor(0x00, 0xFF, 0x00);
        case Rainbow.Blue:
            return new RGBColor(0x00, 0x00, 0xFF);
        case Rainbow.Indigo:
            return new RGBColor(0x4B, 0x00, 0x82);
        case Rainbow.Violet:
            return new RGBColor(0x94, 0x00, 0xD3);
        default:
            throw new ArgumentException(message: "invalid enum value", paramName: nameof(colorBand));
    };
}
```

### <a name="property-patterns"></a><span data-ttu-id="b4e23-184">속성 패턴</span><span class="sxs-lookup"><span data-stu-id="b4e23-184">Property patterns</span></span>

<span data-ttu-id="b4e23-185">**속성 패턴**을 사용하면 검사 대상 개체의 속성을 일치시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-185">The **property pattern** enables you to match on properties of the object examined.</span></span> <span data-ttu-id="b4e23-186">구매자의 주소를 기준으로 판매세를 계산하는 전자상거래 사이트를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-186">Consider an eCommerce site that must compute sales tax based on the buyer's address.</span></span> <span data-ttu-id="b4e23-187">판매세 계산은 `Address` 클래스의 주요 임무가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-187">That computation isn't a core responsibility of an `Address` class.</span></span> <span data-ttu-id="b4e23-188">판매세는 시간이 흐름에 따라 주소 형식이 변경되는 빈도보다 자주 변경될 가능성이 큽니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-188">It will change over time, likely more often than address format changes.</span></span> <span data-ttu-id="b4e23-189">판매세의 금액은 주소의 `State` 속성에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-189">The amount of sales tax depends on the `State` property of the address.</span></span> <span data-ttu-id="b4e23-190">다음 메서드는 속성 패턴을 사용하여 주소 및 가격으로부터 판매세를 컴퓨팅합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-190">The following method uses the property pattern to compute the sales tax from the address and the price:</span></span>

```csharp
public static decimal ComputeSalesTax(Address location, decimal salePrice) =>
    location switch
    {
        { State: "WA" } => salePrice * 0.06M,
        { State: "MN" } => salePrice * 0.075M,
        { State: "MI" } => salePrice * 0.05M,
        // other cases removed for brevity...
        _ => 0M
    };
```

<span data-ttu-id="b4e23-191">패턴 일치는 이 알고리즘을 표현하기 위한 더 간결한 구문을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-191">Pattern matching creates a concise syntax for expressing this algorithm.</span></span>

### <a name="tuple-patterns"></a><span data-ttu-id="b4e23-192">튜플 패턴</span><span class="sxs-lookup"><span data-stu-id="b4e23-192">Tuple patterns</span></span>

<span data-ttu-id="b4e23-193">일부 알고리즘은 여러 입력을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-193">Some algorithms depend on multiple inputs.</span></span> <span data-ttu-id="b4e23-194">**튜플 패턴**을 사용하면 [튜플](../tuples.md)로 표현되는 여러 값에 따라 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-194">**Tuple patterns** allow you to switch based on multiple values expressed as a [tuple](../tuples.md).</span></span>  <span data-ttu-id="b4e23-195">다음 코드는 게임 ‘가위, 바위, 보’에 대한 전환 식을 보여 줍니다. </span><span class="sxs-lookup"><span data-stu-id="b4e23-195">The following code shows a switch expression for the game *rock, paper, scissors*:</span></span>

```csharp
public static string RockPaperScissors(string first, string second)
    => (first, second) switch
    {
        ("rock", "paper") => "rock is covered by paper. Paper wins.",
        ("rock", "scissors") => "rock breaks scissors. Rock wins.",
        ("paper", "rock") => "paper covers rock. Paper wins.",
        ("paper", "scissors") => "paper is cut by scissors. Scissors wins.",
        ("scissors", "rock") => "scissors is broken by rock. Rock wins.",
        ("scissors", "paper") => "scissors cuts paper. Scissors wins.",
        (_, _) => "tie"
    };
```

<span data-ttu-id="b4e23-196">메시지는 승자를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-196">The messages indicate the winner.</span></span> <span data-ttu-id="b4e23-197">버리기 사례는 동률의 세 가지 조합 또는 기타 텍스트 입력을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-197">The discard case represents the three combinations for ties, or other text inputs.</span></span>

### <a name="positional-patterns"></a><span data-ttu-id="b4e23-198">위치 패턴</span><span class="sxs-lookup"><span data-stu-id="b4e23-198">Positional patterns</span></span>

<span data-ttu-id="b4e23-199">일부 형식에는 해당 속성을 불연속 변수로 분해하는 `Deconstruct` 메서드가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-199">Some types include a `Deconstruct` method that deconstructs its properties into discrete variables.</span></span> <span data-ttu-id="b4e23-200">`Deconstruct` 메서드에 액세스할 수 있는 경우 **위치 패턴**을 사용하여 개체의 속성을 검사하고 패턴에 해당 속성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-200">When a `Deconstruct` method is accessible, you can use **positional patterns** to inspect properties of the object and use those properties for a pattern.</span></span>  <span data-ttu-id="b4e23-201">`X` 및 `Y`의 불연속 변수를 만들려면 `Deconstruct` 메서드를 포함하는 다음 `Point` 클래스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-201">Consider the following `Point` class that includes a `Deconstruct` method to create discrete variables for `X` and `Y`:</span></span>

```csharp
public class Point
{
    public int X { get; }
    public int Y { get; }

    public Point(int x, int y) => (X, Y) = (x, y);

    public void Deconstruct(out int x, out int y) =>
        (x, y) = (X, Y);
}
```

<span data-ttu-id="b4e23-202">또한 사분면의 다양한 위치를 나타내는 다음 열거형을 고려하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-202">Additionally, consider the following enum that represents various positions of a quadrant:</span></span>

```csharp
public enum Quadrant
{
    Unknown,
    Origin,
    One,
    Two,
    Three,
    Four,
    OnBorder
}
```

<span data-ttu-id="b4e23-203">다음 메서드는 **위치 패턴**을 사용하여 `x`와 `y`의 값을 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-203">The following method uses the **positional pattern** to extract the values of `x` and `y`.</span></span> <span data-ttu-id="b4e23-204">그런 다음, `when` 절을 사용하여 점의 `Quadrant`를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-204">Then, it uses a `when` clause to determine the `Quadrant` of the point:</span></span>

```csharp
static Quadrant GetQuadrant(Point point) => point switch
{
    (0, 0) => Quadrant.Origin,
    var (x, y) when x > 0 && y > 0 => Quadrant.One,
    var (x, y) when x < 0 && y > 0 => Quadrant.Two,
    var (x, y) when x < 0 && y < 0 => Quadrant.Three,
    var (x, y) when x > 0 && y < 0 => Quadrant.Four,
    var (_, _) => Quadrant.OnBorder,
    _ => Quadrant.Unknown
};
```

<span data-ttu-id="b4e23-205">이전 switch의 버리기 패턴은 `x` 또는 `y` 중 하나만 0인 경우에 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-205">The discard pattern in the preceding switch matches when either `x` or `y` is 0, but not both.</span></span> <span data-ttu-id="b4e23-206">expression 식은 항상 값을 생성하거나 예외를 throw해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-206">A switch expression must either produce a value or throw an exception.</span></span> <span data-ttu-id="b4e23-207">일치하는 케이스가 없으면 switch 식이 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-207">If none of the cases match, the switch expression throws an exception.</span></span> <span data-ttu-id="b4e23-208">switch 식이 가능한 모든 케이스를 포함하지 않으면 컴파일러에서 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-208">The compiler generates a warning for you if you don't cover all possible cases in your switch expression.</span></span>

<span data-ttu-id="b4e23-209">이 [패턴 일치에 대한 고급 자습서](../tutorials/pattern-matching.md)에서 패턴 일치 기법을 탐색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-209">You can explore pattern matching techniques in this [advanced tutorial on pattern matching](../tutorials/pattern-matching.md).</span></span>

## <a name="using-declarations"></a><span data-ttu-id="b4e23-210">Using 선언</span><span class="sxs-lookup"><span data-stu-id="b4e23-210">Using declarations</span></span>

<span data-ttu-id="b4e23-211">**using 선언**은 `using` 키워드 뒤에 오는 변수 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-211">A **using declaration** is a variable declaration preceded by the `using` keyword.</span></span> <span data-ttu-id="b4e23-212">using 선언은 선언되는 변수를 바깥쪽 범위의 끝에서 삭제하라고 컴파일러에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-212">It tells the compiler that the variable being declared should be disposed at the end of the enclosing scope.</span></span> <span data-ttu-id="b4e23-213">텍스트 파일을 쓰는 다음 코드를 예로 들어 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-213">For example, consider the following code that writes a text file:</span></span>

```csharp
static int WriteLinesToFile(IEnumerable<string> lines)
{
    using var file = new System.IO.StreamWriter("WriteLines2.txt");
    // Notice how we declare skippedLines after the using statement.
    int skippedLines = 0;
    foreach (string line in lines)
    {
        if (!line.Contains("Second"))
        {
            file.WriteLine(line);
        }
        else
        {
            skippedLines++;
        }
    }
    // Notice how skippedLines is in scope here.
    return skippedLines;
    // file is disposed here
}
```

<span data-ttu-id="b4e23-214">위 예에서 메서드의 닫는 중괄호에 도달하면 파일이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-214">In the preceding example, the file is disposed when the closing brace for the method is reached.</span></span> <span data-ttu-id="b4e23-215">이 지점이 바로 `file`이 선언된 범위의 끝입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-215">That's the end of the scope in which `file` is declared.</span></span> <span data-ttu-id="b4e23-216">위 코드는 기존의 [using 문](../language-reference/keywords/using-statement.md) 문을 사용하는 다음 코드와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-216">The preceding code is equivalent to the following code that uses the classic [using statement](../language-reference/keywords/using-statement.md):</span></span>

```csharp
static int WriteLinesToFile(IEnumerable<string> lines)
{
    // We must declare the variable outside of the using block
    // so that it is in scope to be returned.
    int skippedLines = 0;
    using (var file = new System.IO.StreamWriter("WriteLines2.txt"))
    {
        foreach (string line in lines)
        {
            if (!line.Contains("Second"))
            {
                file.WriteLine(line);
            }
            else
            {
                skippedLines++;
            }
        }
    } // file is disposed here
    return skippedLines;
}
```

<span data-ttu-id="b4e23-217">위 예에서 `using` 문의 닫는 중괄호에 도달하면 파일이 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-217">In the preceding example, the file is disposed when the closing brace associated with the `using` statement is reached.</span></span>

<span data-ttu-id="b4e23-218">두 경우 모두 컴파일러가 `Dispose()`를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-218">In both cases, the compiler generates the call to `Dispose()`.</span></span> <span data-ttu-id="b4e23-219">`using` 문의 식을 삭제할 수 없는 경우 컴파일러에서 오류를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-219">The compiler generates an error if the expression in the `using` statement isn't disposable.</span></span>

## <a name="static-local-functions"></a><span data-ttu-id="b4e23-220">정적 로컬 함수</span><span class="sxs-lookup"><span data-stu-id="b4e23-220">Static local functions</span></span>

<span data-ttu-id="b4e23-221">이제 로컬 함수가 바깥쪽 범위의 변수를 참조하는 경우가 없도록 로컬 함수에 `static` 한정자를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-221">You can now add the `static` modifier to local functions to ensure that local function doesn't capture (reference) any variables from the enclosing scope.</span></span> <span data-ttu-id="b4e23-222">이렇게 하면 `CS8421` "정적 로컬 함수는 \<variable>에 대한 참조를 포함할 수 없습니다."를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-222">Doing so generates `CS8421`, "A static local function can't contain a reference to \<variable>."</span></span>

<span data-ttu-id="b4e23-223">다음과 같은 코드를 생각해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-223">Consider the following code.</span></span> <span data-ttu-id="b4e23-224">여기서 로컬 함수 `LocalFunction`은 바깥쪽 범위(메서드 `M`)에서 선언된 변수 `y`에 액세스합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-224">The local function `LocalFunction` accesses the variable `y`, declared in the enclosing scope (the method `M`).</span></span> <span data-ttu-id="b4e23-225">따라서 `LocalFunction`을 `static` 한정자와 함께 선언할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-225">Therefore, `LocalFunction` can't be declared with the `static` modifier:</span></span>

```csharp
int M()
{
    int y;
    LocalFunction();
    return y;

    void LocalFunction() => y = 0;
}
```

<span data-ttu-id="b4e23-226">다음 코드에는 정적 로컬 함수가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-226">The following code contains a static local function.</span></span> <span data-ttu-id="b4e23-227">여기서 로컬 함수는 바깥쪽 범위의 변수에 액세스하지 않으므로 정적이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-227">It can be static because it doesn't access any variables in the enclosing scope:</span></span>

```csharp
int M()
{
    int y = 5;
    int x = 7;
    return Add(x, y);

    static int Add(int left, int right) => left + right;
}
```

## <a name="disposable-ref-structs"></a><span data-ttu-id="b4e23-228">삭제 가능한 ref struct</span><span class="sxs-lookup"><span data-stu-id="b4e23-228">Disposable ref structs</span></span>

<span data-ttu-id="b4e23-229">`ref` 한정자를 사용하여 선언된 `struct`는 인터페이스를 구현할 수 없으므로 <xref:System.IDisposable>을 구현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-229">A `struct` declared with the `ref` modifier may not implement any interfaces and so can't implement <xref:System.IDisposable>.</span></span> <span data-ttu-id="b4e23-230">따라서 `ref struct`가 삭제 가능해지려면 액세스 가능한 `void Dispose()` 메서드를 가져야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-230">Therefore, to enable a `ref struct` to be disposed, it must have an accessible `void Dispose()` method.</span></span> <span data-ttu-id="b4e23-231">이 기능은 `readonly ref struct` 선언에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-231">This feature also applies to `readonly ref struct` declarations.</span></span>

## <a name="nullable-reference-types"></a><span data-ttu-id="b4e23-232">nullable 참조 형식</span><span class="sxs-lookup"><span data-stu-id="b4e23-232">Nullable reference types</span></span>

<span data-ttu-id="b4e23-233">nullable 주석 컨텍스트에서 참조 형식의 변수는 모두 **nullable이 아닌 참조 형식**으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-233">Inside a nullable annotation context, any variable of a reference type is considered to be a **nonnullable reference type**.</span></span> <span data-ttu-id="b4e23-234">변수가 null이 될 수 있음을 나타내려면 형식 이름 뒤에 `?`를 추가하여 해당 변수를 **nullable 참조 형식**으로 선언해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-234">If you want to indicate that a variable may be null, you must append the type name with the `?` to declare the variable as a **nullable reference type**.</span></span>

<span data-ttu-id="b4e23-235">nullable이 아닌 참조 형식의 경우, 로컬 변수가 선언될 때 null이 아닌 값으로 초기화되도록 컴파일러가 흐름 분석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-235">For nonnullable reference types, the compiler uses flow analysis to ensure that local variables are initialized to a non-null value when declared.</span></span> <span data-ttu-id="b4e23-236">필드는 생성 시점에 초기화되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-236">Fields must be initialized during construction.</span></span> <span data-ttu-id="b4e23-237">사용 가능한 생성자 호출이나 이니셜라이저를 통해 변수가 설정되지 않으면 컴파일러에서 경고를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-237">The compiler generates a warning if the variable isn't set by a call to any of the available constructors or by an initializer.</span></span> <span data-ttu-id="b4e23-238">또한, nullable이 아닌 참조 형식은 null이 될 수 있는 값에 할당할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-238">Furthermore, nonnullable reference types can't be assigned a value that could be null.</span></span>

<span data-ttu-id="b4e23-239">nullable 참조 형식은 할당되지 않았는지 또는 null로 초기화되었는지 검사되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-239">Nullable reference types aren't checked to ensure they aren't assigned or initialized to null.</span></span> <span data-ttu-id="b4e23-240">단, nullable 참조 형식의 변수가 액세스되거나 nullable이 아닌 참조 형식에 할당되기 전에 null에 대해 검사되도록 컴파일러가 흐름 분석을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-240">However, the compiler uses flow analysis to ensure that any variable of a nullable reference type is checked against null before it's accessed or assigned to a nonnullable reference type.</span></span>

<span data-ttu-id="b4e23-241">[nullable 참조 형식](../nullable-references.md) 개요에서 이 기능에 대해 자세히 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-241">You can learn more about the feature in the overview of [nullable reference types](../nullable-references.md).</span></span> <span data-ttu-id="b4e23-242">[nullable 참조 형식 자습서](../tutorials/nullable-reference-types.md)를 활용하여 새 애플리케이션에서 직접 사용해 보세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-242">Try it yourself in a new application in this [nullable reference types tutorial](../tutorials/nullable-reference-types.md).</span></span> <span data-ttu-id="b4e23-243">[자습서: nullable 참조 형식이 있는 기존 코드 마이그레이션에서는](../tutorials/upgrade-to-nullable-references.md) nullable 참조 형식을 사용할 수 있도록 기존 코드베이스를 마이그레이션하는 방법을 알아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-243">Learn about the steps to migrate an existing codebase to make use of nullable reference types in the [migrating an application to use nullable reference types tutorial](../tutorials/upgrade-to-nullable-references.md).</span></span>

## <a name="asynchronous-streams"></a><span data-ttu-id="b4e23-244">비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="b4e23-244">Asynchronous streams</span></span>

<span data-ttu-id="b4e23-245">C# 8.0부터 스트림을 비동기식으로 만들고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-245">Starting with C# 8.0, you can create and consume streams asynchronously.</span></span> <span data-ttu-id="b4e23-246">비동기 스트림을 반환하는 메서드는 다음과 같은 세 가지 속성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-246">A method that returns an asynchronous stream has three properties:</span></span>

1. <span data-ttu-id="b4e23-247">`async` 한정자를 사용하여 선언되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-247">It's declared with the `async` modifier.</span></span>
1. <span data-ttu-id="b4e23-248"><xref:System.Collections.Generic.IAsyncEnumerable%601>를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-248">It returns an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span>
1. <span data-ttu-id="b4e23-249">비동기 스트림의 연속적인 요소를 반환하기 위해 메서드가 `yield return` 문을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-249">The method contains `yield return` statements to return successive elements in the asynchronous stream.</span></span>

<span data-ttu-id="b4e23-250">비동기 스트림을 사용하려면 스트림의 요소를 열거할 때 `foreach` 키워드 앞에 `await` 키워드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-250">Consuming an asynchronous stream requires you to add the `await` keyword before the `foreach` keyword when you enumerate the elements of the stream.</span></span> <span data-ttu-id="b4e23-251">`await` 키워드를 추가하려면 비동기 스트림을 열거하는 메서드가 `async` 한정자와 함께 선언되어야 하며, 이 메서드가 `async` 메서드를 허용하는 형식을 반환해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-251">Adding the `await` keyword requires the method that enumerates the asynchronous stream to be declared with the `async` modifier and to return a type allowed for an `async` method.</span></span> <span data-ttu-id="b4e23-252">일반적으로 이는 <xref:System.Threading.Tasks.Task> 또는 <xref:System.Threading.Tasks.Task%601> 형식을 반환해야 함을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-252">Typically that means returning a <xref:System.Threading.Tasks.Task> or <xref:System.Threading.Tasks.Task%601>.</span></span> <span data-ttu-id="b4e23-253"><xref:System.Threading.Tasks.ValueTask> 또는 <xref:System.Threading.Tasks.ValueTask%601> 형식도 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-253">It can also be a <xref:System.Threading.Tasks.ValueTask> or <xref:System.Threading.Tasks.ValueTask%601>.</span></span> <span data-ttu-id="b4e23-254">메서드는 비동기 스트림을 사용할 수도 있고 생성할 수 있습니다. 비동기 스트림을 생성한다는 것은 메서드가 <xref:System.Collections.Generic.IAsyncEnumerable%601>를 반환한다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-254">A method can both consume and produce an asynchronous stream, which means it would return an <xref:System.Collections.Generic.IAsyncEnumerable%601>.</span></span> <span data-ttu-id="b4e23-255">다음 코드는 0에서 19까지의 시퀀스를 생성합니다. 숫자가 생성되는 각 시점 사이에는 100ms의 대기 시간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-255">The following code generates a sequence from 0 to 19, waiting 100 ms between generating each number:</span></span>

```csharp
public static async System.Collections.Generic.IAsyncEnumerable<int> GenerateSequence()
{
    for (int i = 0; i < 20; i++)
    {
        await Task.Delay(100);
        yield return i;
    }
}
```

<span data-ttu-id="b4e23-256">`await foreach` 문을 사용하여 시퀀스를 열거합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-256">You would enumerate the sequence using the `await foreach` statement:</span></span>

```csharp
await foreach (var number in GenerateSequence())
{
    Console.WriteLine(number);
}
```

<span data-ttu-id="b4e23-257">[비동기 스트림 생성 및 사용](../tutorials/generate-consume-asynchronous-stream.md) 자습서에서 직접 비동기 스트림을 사용해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-257">You can try asynchronous streams yourself in our tutorial on [creating and consuming async streams](../tutorials/generate-consume-asynchronous-stream.md).</span></span> <span data-ttu-id="b4e23-258">기본적으로 스트림 요소는 캡처된 컨텍스트에서 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-258">By default, stream elements are processed in the captured context.</span></span> <span data-ttu-id="b4e23-259">컨텍스트 캡처를 사용하지 않도록 설정하려면 <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> 확장 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-259">If you want to disable capturing of the context, use the <xref:System.Threading.Tasks.TaskAsyncEnumerableExtensions.ConfigureAwait%2A?displayProperty=nameWithType> extension method.</span></span> <span data-ttu-id="b4e23-260">동기화 컨텍스트 및 현재 컨텍스트 캡처에 대한 자세한 내용은 [작업 기반 비동기 패턴 사용](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md)에 대한 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-260">For more information about synchronization contexts and capturing the current context, see the article on [consuming the Task-based asynchronous pattern](../../standard/asynchronous-programming-patterns/consuming-the-task-based-asynchronous-pattern.md).</span></span>

## <a name="asynchronous-disposable"></a><span data-ttu-id="b4e23-261">비동기 삭제 가능</span><span class="sxs-lookup"><span data-stu-id="b4e23-261">Asynchronous disposable</span></span>

<span data-ttu-id="b4e23-262">C# 8.0부터 언어는 <xref:System.IAsyncDisposable?displayProperty=nameWithType> 인터페이스를 구현하는 비동기 삭제 가능 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-262">Starting with C# 8.0, the language supports asynchronous disposable types that implement the <xref:System.IAsyncDisposable?displayProperty=nameWithType> interface.</span></span> <span data-ttu-id="b4e23-263">`using` 식의 피연산자는 <xref:System.IDisposable> 또는 <xref:System.IAsyncDisposable>을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-263">The operand of a `using` expression can implement either <xref:System.IDisposable> or <xref:System.IAsyncDisposable>.</span></span> <span data-ttu-id="b4e23-264">`IAsyncDisposable`의 경우 컴파일러는 <xref:System.IAsyncDisposable.DisposeAsync%2A?displayProperty=nameWithType>에서 반환된 <xref:System.Threading.Tasks.Task>를 `await`하는 코드를 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-264">In the case of `IAsyncDisposable`, the compiler generates code to `await` the <xref:System.Threading.Tasks.Task> returned from <xref:System.IAsyncDisposable.DisposeAsync%2A?displayProperty=nameWithType>.</span></span> <span data-ttu-id="b4e23-265">자세한 내용은 [`using` 문](../language-reference/keywords/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-265">For more information, see the [`using` statement](../language-reference/keywords/using-statement.md).</span></span>

## <a name="indices-and-ranges"></a><span data-ttu-id="b4e23-266">인덱스 및 범위</span><span class="sxs-lookup"><span data-stu-id="b4e23-266">Indices and ranges</span></span>

<span data-ttu-id="b4e23-267">인덱스와 범위는 시퀀스에서 단일 요소 또는 범위에 액세스하기 위한 간결한 구문을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-267">Indices and ranges provide a succinct syntax for accessing single elements or ranges in a sequence.</span></span>

<span data-ttu-id="b4e23-268">이 언어 지원은 다음과 같은 두 가지 새 형식 및 두 가지 새 연산자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-268">This language support relies on two new types, and two new operators:</span></span>

- <span data-ttu-id="b4e23-269"><xref:System.Index?displayProperty=nameWithType>는 인덱스를 시퀀스로 표현합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-269"><xref:System.Index?displayProperty=nameWithType> represents an index into a sequence.</span></span>
- <span data-ttu-id="b4e23-270">인덱스가 시퀀스의 끝을 기준으로 하도록 지정하는 끝부터 인덱스 연산자 `^`입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-270">The index from end operator `^`, which specifies that an index is relative to the end of the sequence.</span></span>
- <span data-ttu-id="b4e23-271"><xref:System.Range?displayProperty=nameWithType>는 시퀀스의 하위 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-271"><xref:System.Range?displayProperty=nameWithType> represents a sub range of a sequence.</span></span>
- <span data-ttu-id="b4e23-272">범위의 시작과 끝을 피연산자로 지정하는 범위 연산자 `..`입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-272">The range operator `..`, which specifies the start and end of a range as its operands.</span></span>

<span data-ttu-id="b4e23-273">인덱스에 대한 규칙을 사용하여 시작하겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-273">Let's start with the rules for indexes.</span></span> <span data-ttu-id="b4e23-274">`sequence`배열을 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-274">Consider an array `sequence`.</span></span> <span data-ttu-id="b4e23-275">`0` 인덱스는 `sequence[0]`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-275">The `0` index is the same as `sequence[0]`.</span></span> <span data-ttu-id="b4e23-276">`^0` 인덱스는 `sequence[sequence.Length]`와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-276">The `^0` index is the same as `sequence[sequence.Length]`.</span></span> <span data-ttu-id="b4e23-277">`sequence[^0]`은 `sequence[sequence.Length]`처럼 예외를 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-277">Note that `sequence[^0]` does throw an exception, just as `sequence[sequence.Length]` does.</span></span> <span data-ttu-id="b4e23-278">`n`이 어떤 숫자이든, 인덱스 `^n`은 `sequence.Length - n`과 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-278">For any number `n`, the index `^n` is the same as `sequence.Length - n`.</span></span>

<span data-ttu-id="b4e23-279">한 범위는 어떤 범위의 *시작* 및 *끝*을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-279">A range specifies the *start* and *end* of a range.</span></span> <span data-ttu-id="b4e23-280">범위의 시작은 포함되지만, 범위의 끝은 포함되지 않으므로, *시작*은 범위에 포함되고 *끝*은 범위에 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-280">The start of the range is inclusive, but the end of the range is exclusive, meaning the *start* is included in the range but the *end* isn't included in the range.</span></span> <span data-ttu-id="b4e23-281">`[0..sequence.Length]`가 전체 범위를 나타내는 것처럼 `[0..^0]` 범위는 전체 범위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-281">The range `[0..^0]` represents the entire range, just as `[0..sequence.Length]` represents the entire range.</span></span>

<span data-ttu-id="b4e23-282">몇 가지 예를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-282">Let's look at a few examples.</span></span> <span data-ttu-id="b4e23-283">다음과 같은 배열이 있습니다. 앞에서부터의 인덱스와 뒤에서부터의 인덱스가 주석으로 처리되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-283">Consider the following array, annotated with its index from the start and from the end:</span></span>

```csharp
var words = new string[]
{
                // index from start    index from end
    "The",      // 0                   ^9
    "quick",    // 1                   ^8
    "brown",    // 2                   ^7
    "fox",      // 3                   ^6
    "jumped",   // 4                   ^5
    "over",     // 5                   ^4
    "the",      // 6                   ^3
    "lazy",     // 7                   ^2
    "dog"       // 8                   ^1
};              // 9 (or words.Length) ^0
```

<span data-ttu-id="b4e23-284">다음과 같이 `^1` 인덱스를 사용하여 마지막 단어를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-284">You can retrieve the last word with the `^1` index:</span></span>

```csharp
Console.WriteLine($"The last word is {words[^1]}");
// writes "dog"
```

<span data-ttu-id="b4e23-285">다음 코드는 “quick”, “brown”, “fox”라는 단어를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-285">The following code creates a subrange with the words "quick", "brown", and "fox".</span></span> <span data-ttu-id="b4e23-286">이 하위 범위에는 `words[1]`부터 `words[3]`까지 포함되며,</span><span class="sxs-lookup"><span data-stu-id="b4e23-286">It includes `words[1]` through `words[3]`.</span></span> <span data-ttu-id="b4e23-287">`words[4]` 요소가 범위에 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-287">The element `words[4]` isn't in the range.</span></span>

```csharp
var quickBrownFox = words[1..4];
```

<span data-ttu-id="b4e23-288">다음 코드는 “lazy”와 “dog”를 포함하는 하위 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-288">The following code creates a subrange with "lazy" and "dog".</span></span> <span data-ttu-id="b4e23-289">이 하위 범위에는 `words[^2]`과 `words[^1]`이 포함되며.</span><span class="sxs-lookup"><span data-stu-id="b4e23-289">It includes `words[^2]` and `words[^1]`.</span></span> <span data-ttu-id="b4e23-290">끝 인덱스 `words[^0]`은 포함되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-290">The end index `words[^0]` isn't included:</span></span>

```csharp
var lazyDog = words[^2..^0];
```

<span data-ttu-id="b4e23-291">다음 예제는 시작만, 끝만, 그리고 시작과 끝이 모두 열린 범위를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-291">The following examples create ranges that are open ended for the start, end, or both:</span></span>

```csharp
var allWords = words[..]; // contains "The" through "dog".
var firstPhrase = words[..4]; // contains "The" through "fox"
var lastPhrase = words[6..]; // contains "the", "lazy" and "dog"
```

<span data-ttu-id="b4e23-292">범위를 변수로 선언할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-292">You can also declare ranges as variables:</span></span>

```csharp
Range phrase = 1..4;
```

<span data-ttu-id="b4e23-293">이렇게 변수로 선언된 범위는 `[` 문자와 `]` 문자 사이에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-293">The range can then be used inside the `[` and `]` characters:</span></span>

```csharp
var text = words[phrase];
```

<span data-ttu-id="b4e23-294">배열만 인덱스와 범위를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-294">Not only arrays support indices and ranges.</span></span> <span data-ttu-id="b4e23-295">[문자열](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601> 또는 <xref:System.ReadOnlySpan%601>에서 인덱스 및 범위를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-295">You can also use indices and ranges with [string](../language-reference/builtin-types/reference-types.md#the-string-type), <xref:System.Span%601>, or <xref:System.ReadOnlySpan%601>.</span></span> <span data-ttu-id="b4e23-296">자세한 내용은 [인덱스 및 범위에 대한 형식 지원](../tutorials/ranges-indexes.md#type-support-for-indices-and-ranges)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-296">For more information, see [Type support for indices and ranges](../tutorials/ranges-indexes.md#type-support-for-indices-and-ranges).</span></span>

<span data-ttu-id="b4e23-297">인덱스와 범위에 대한 자세한 내용은 [인덱스 및 범위](../tutorials/ranges-indexes.md)에 대한 자습서에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-297">You can explore more about indices and ranges in the tutorial on [indices and ranges](../tutorials/ranges-indexes.md).</span></span>

## <a name="null-coalescing-assignment"></a><span data-ttu-id="b4e23-298">null 병합 할당</span><span class="sxs-lookup"><span data-stu-id="b4e23-298">Null-coalescing assignment</span></span>

<span data-ttu-id="b4e23-299">C# 8.0에서 null 병합 할당 연산자 `??=`가 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-299">C# 8.0 introduces the null-coalescing assignment operator `??=`.</span></span> <span data-ttu-id="b4e23-300">`??=` 연산자를 사용하여 왼쪽 피연산자가 `null`로 계산되는 경우에만 오른쪽 피연산자의 값을 왼쪽 피연산자에 대입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-300">You can use the `??=` operator to assign the value of its right-hand operand to its left-hand operand only if the left-hand operand evaluates to `null`.</span></span>

```csharp
List<int> numbers = null;
int? i = null;

numbers ??= new List<int>();
numbers.Add(i ??= 17);
numbers.Add(i ??= 20);

Console.WriteLine(string.Join(" ", numbers));  // output: 17 17
Console.WriteLine(i);  // output: 17
```

<span data-ttu-id="b4e23-301">자세한 내용은 [?? 및 ??= 연산자](../language-reference/operators/null-coalescing-operator.md) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-301">For more information, see the [?? and ??= operators](../language-reference/operators/null-coalescing-operator.md) article.</span></span>

## <a name="unmanaged-constructed-types"></a><span data-ttu-id="b4e23-302">관리되지 않는 생성 형식</span><span class="sxs-lookup"><span data-stu-id="b4e23-302">Unmanaged constructed types</span></span>

<span data-ttu-id="b4e23-303">C# 7.3 및 이전 버전에서 생성 형식(하나 이상의 형식 인수를 포함하는 형식)은 [관리되지 않는 형식](../language-reference/builtin-types/unmanaged-types.md)일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-303">In C# 7.3 and earlier, a constructed type (a type that includes at least one type argument) can't be an [unmanaged type](../language-reference/builtin-types/unmanaged-types.md).</span></span> <span data-ttu-id="b4e23-304">C# 8.0부터는 관리되지 않는 형식의 필드만 포함된 경우 생성된 값 형식이 관리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-304">Starting with C# 8.0, a constructed value type is unmanaged if it contains fields of unmanaged types only.</span></span>

<span data-ttu-id="b4e23-305">예를 들어 다음과 같은 제네릭 `Coords<T>` 형식의 정의를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-305">For example, given the following definition of the generic `Coords<T>` type:</span></span>

```csharp
public struct Coords<T>
{
    public T X;
    public T Y;
}
```

<span data-ttu-id="b4e23-306">`Coords<int>` 형식은 C# 8.0 이상에서 관리되지 않는 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-306">the `Coords<int>` type is an unmanaged type in C# 8.0 and later.</span></span> <span data-ttu-id="b4e23-307">관리되지 않는 형식과 마찬가지로 이 형식의 변수에 대한 포인터를 만들거나 이 형식의 인스턴스에 대해 [스택에서 메모리 블록을 할당](../language-reference/operators/stackalloc.md)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-307">Like for any unmanaged type, you can create a pointer to a variable of this type or [allocate a block of memory on the stack](../language-reference/operators/stackalloc.md) for instances of this type:</span></span>

```csharp
Span<Coords<int>> coordinates = stackalloc[]
{
    new Coords<int> { X = 0, Y = 0 },
    new Coords<int> { X = 0, Y = 3 },
    new Coords<int> { X = 4, Y = 0 }
};
```

<span data-ttu-id="b4e23-308">자세한 내용은 [관리되지 않는 형식](../language-reference/builtin-types/unmanaged-types.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4e23-308">For more information, see [Unmanaged types](../language-reference/builtin-types/unmanaged-types.md).</span></span>

## <a name="stackalloc-in-nested-expressions"></a><span data-ttu-id="b4e23-309">중첩 식의 stackalloc</span><span class="sxs-lookup"><span data-stu-id="b4e23-309">Stackalloc in nested expressions</span></span>

<span data-ttu-id="b4e23-310">C# 8.0부터 [stackalloc](../language-reference/operators/stackalloc.md) 식의 결과가 <xref:System.Span%601?displayProperty=nameWithType> 또는 <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> 형식이면 다른 식에서 `stackalloc` 식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-310">Starting with C# 8.0, if the result of a [stackalloc](../language-reference/operators/stackalloc.md) expression is of the <xref:System.Span%601?displayProperty=nameWithType> or <xref:System.ReadOnlySpan%601?displayProperty=nameWithType> type, you can use the `stackalloc` expression in other expressions:</span></span>

```csharp
Span<int> numbers = stackalloc[] { 1, 2, 3, 4, 5, 6 };
var ind = numbers.IndexOfAny(stackalloc[] { 2, 4, 6, 8 });
Console.WriteLine(ind);  // output: 1
```

## <a name="enhancement-of-interpolated-verbatim-strings"></a><span data-ttu-id="b4e23-311">보간된 약어 문자열의 향상된 기능</span><span class="sxs-lookup"><span data-stu-id="b4e23-311">Enhancement of interpolated verbatim strings</span></span>

<span data-ttu-id="b4e23-312">[보간된](../language-reference/tokens/interpolated.md) 약어 문자열에서 `$` 및 `@` 토큰은 순서에 관계없이 사용할 수 있습니다. `$@"..."` 및 `@$"..."` 모두 유효한 보간된 약어 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-312">Order of the `$` and `@` tokens in [interpolated](../language-reference/tokens/interpolated.md) verbatim strings can be any: both `$@"..."` and `@$"..."` are valid interpolated verbatim strings.</span></span> <span data-ttu-id="b4e23-313">이전 C# 버전에서는 `$` 토큰이 `@` 토큰 앞에 나타나야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e23-313">In earlier C# versions, the `$` token must appear before the `@` token.</span></span>
