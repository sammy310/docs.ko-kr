---
title: F# 코딩 규칙
description: F# 코드를 작성할 때 일반적인 지침과 숙어를 배웁니다.
ms.date: 01/15/2020
ms.openlocfilehash: 7266211e501bdb52564220781e2347d1aceaf296
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401150"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="67bf0-103">F# 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="67bf0-103">F# coding conventions</span></span>

<span data-ttu-id="67bf0-104">다음 규칙은 대규모 F# 코드베이스를 사용하면 서두르는 경험에서 공식화됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="67bf0-105">[좋은 F # 코드의 다섯 가지 원칙은](index.md#five-principles-of-good-f-code) 각 권장 사항의 기초입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="67bf0-106">F# 구성 [요소 디자인 지침과](component-design-guidelines.md)관련이 있지만 라이브러리와 같은 구성 요소뿐만 아니라 모든 F# 코드에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="67bf0-107">코드 구성</span><span class="sxs-lookup"><span data-stu-id="67bf0-107">Organizing code</span></span>

<span data-ttu-id="67bf0-108">F#에는 모듈과 네임스페이스라는 두 가지 기본 코드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="67bf0-109">이들은 비슷하지만 다음과 같은 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="67bf0-110">네임스페이스는 .NET 네임스페이스로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="67bf0-111">모듈은 정적 클래스로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="67bf0-112">네임스페이스는 항상 최상위 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-112">Namespaces are always top level.</span></span> <span data-ttu-id="67bf0-113">모듈은 최상위 수준이며 다른 모듈 내에 중첩될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="67bf0-114">네임스페이스는 여러 파일에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="67bf0-115">모듈은 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-115">Modules cannot.</span></span>
* <span data-ttu-id="67bf0-116">모듈을 장식할 `[<RequireQualifiedAccess>]` 수 `[<AutoOpen>]`있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="67bf0-117">다음 지침은 코드를 구성하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="67bf0-118">최상위 수준에서 네임스페이스 선호</span><span class="sxs-lookup"><span data-stu-id="67bf0-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="67bf0-119">공개적으로 소모품 코드의 경우 네임스페이스는 최상위 수준의 모듈보다 우선합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="67bf0-120">.NET 네임스페이스로 컴파일되므로 문제 없이 C#에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="67bf0-121">최상위 모듈을 사용하면 F#에서만 호출할 때 다르게 나타나지 않을 수 있지만 C# 소비자의 `MyClass` 경우 `MyCode` 호출자는 모듈을 사용할 수 있어야 하므로 놀랄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="67bf0-122">신중하게 적용`[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="67bf0-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="67bf0-123">구문은 `[<AutoOpen>]` 발신자가 사용할 수 있는 범위의 범위를 오염시킬 수 있으며, 무언가의 유래에 대한 대답은 "마법"입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="67bf0-124">이것은 좋은 일이 아니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-124">This is not a good thing.</span></span> <span data-ttu-id="67bf0-125">이 규칙의 예외는 F# 코어 라이브러리 자체입니다(이 사실은 약간 논란의 여지가 있음).</span><span class="sxs-lookup"><span data-stu-id="67bf0-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="67bf0-126">그러나 공용 API와 별도로 구성하려는 공용 API에 대한 도우미 기능이 있는 경우 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

```fsharp
module MyAPI =
    [<AutoOpen>]
    module private Helpers =
        let helper1 x y z =
            ...

    let myFunction1 x =
        let y = ...
        let z = ...

        helper1 x y z
```

<span data-ttu-id="67bf0-127">이렇게 하면 호출할 때마다 도우미를 완전히 한정할 필요 없이 함수의 공용 API에서 구현 세부 정보를 완전히 분리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="67bf0-128">또한 네임스페이스 수준에서 확장 메서드 및 식 빌더를 노출하면 을 로 `[<AutoOpen>]`깔끔하게 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="67bf0-129">이름이 `[<RequireQualifiedAccess>]` 충돌하거나 가독성에 도움이 된다고 느낄 때마다 사용</span><span class="sxs-lookup"><span data-stu-id="67bf0-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="67bf0-130">모듈에 `[<RequireQualifiedAccess>]` 특성을 추가하면 모듈이 열리지 않을 수 있으며 모듈의 요소에 대한 참조에는 명시적 권한 있는 액세스가 필요하다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="67bf0-131">예를 들어 `Microsoft.FSharp.Collections.List` 모듈에 이 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="67bf0-132">이 기능은 모듈의 함수와 값에 다른 모듈의 이름과 충돌할 가능성이 있는 이름이 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="67bf0-133">자격을 갖춘 액세스가 필요하면 라이브러리의 장기적인 유지 관리 및 사용 가능성을 크게 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="67bf0-134">정렬 `open` 문 토폴로지</span><span class="sxs-lookup"><span data-stu-id="67bf0-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="67bf0-135">F#에서 선언순서는 `open` 문을 포함하여 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="67bf0-136">이는 파일에서 해당 명령문의 `using` 순서와 는 별개의 효과가 있는 `using static` C#과는 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="67bf0-137">F#에서 범위로 열린 요소는 이미 존재하는 다른 요소를 숨가일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="67bf0-138">즉, 명령문을 `open` 다시 정렬하면 코드의 의미가 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="67bf0-139">따라서 예상할 수 있는 다른 `open` 동작을 생성하지 않도록 모든 명령문(예: 범수치)을 임의로 정렬하는 것은 권장되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="67bf0-140">대신 [위상적으로](https://en.wikipedia.org/wiki/Topological_sorting)정렬하는 것이 좋습니다. 즉, 시스템의 `open` _계층이_ 정의된 순서대로 명령문을 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="67bf0-141">상이한 토폴로지 레이어 내에서 상숫자 정렬을 수행하는 것도 고려될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="67bf0-142">예를 들어 F# 컴파일러 서비스 공용 API 파일에 대한 토폴로지 정렬은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

```fsharp
namespace Microsoft.FSharp.Compiler.SourceCodeServices

open System
open System.Collections.Generic
open System.Collections.Concurrent
open System.Diagnostics
open System.IO
open System.Reflection
open System.Text

open Microsoft.FSharp.Compiler
open Microsoft.FSharp.Compiler.AbstractIL
open Microsoft.FSharp.Compiler.AbstractIL.Diagnostics
open Microsoft.FSharp.Compiler.AbstractIL.IL
open Microsoft.FSharp.Compiler.AbstractIL.ILBinaryReader
open Microsoft.FSharp.Compiler.AbstractIL.Internal
open Microsoft.FSharp.Compiler.AbstractIL.Internal.Library

open Microsoft.FSharp.Compiler.AccessibilityLogic
open Microsoft.FSharp.Compiler.Ast
open Microsoft.FSharp.Compiler.CompileOps
open Microsoft.FSharp.Compiler.CompileOptions
open Microsoft.FSharp.Compiler.Driver
open Microsoft.FSharp.Compiler.ErrorLogger
open Microsoft.FSharp.Compiler.Infos
open Microsoft.FSharp.Compiler.InfoReader
open Microsoft.FSharp.Compiler.Lexhelp
open Microsoft.FSharp.Compiler.Layout
open Microsoft.FSharp.Compiler.Lib
open Microsoft.FSharp.Compiler.NameResolution
open Microsoft.FSharp.Compiler.PrettyNaming
open Microsoft.FSharp.Compiler.Parser
open Microsoft.FSharp.Compiler.Range
open Microsoft.FSharp.Compiler.Tast
open Microsoft.FSharp.Compiler.Tastops
open Microsoft.FSharp.Compiler.TcGlobals
open Microsoft.FSharp.Compiler.TypeChecker
open Microsoft.FSharp.Compiler.SourceCodeServices.SymbolHelpers

open Internal.Utilities
open Internal.Utilities.Collections
```

<span data-ttu-id="67bf0-143">선 바선은 위상레이어를 구분하며, 각 레이어는 나중에 상숫자로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="67bf0-144">이렇게 하면 실수로 값을 섀도핑하지 않고 코드를 깔끔하게 정리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="67bf0-145">클래스를 사용하여 부작용이 있는 값을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="67bf0-146">값을 초기화하는 경우 데이터베이스 또는 기타 원격 리소스에 컨텍스트를 인스턴스화하는 등의 부작용이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="67bf0-147">모듈에서 이러한 것들을 초기화하고 후속 함수에서 사용하는 것이 유혹합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

```fsharp
// This is bad!
module MyApi =
    let dep1 = File.ReadAllText "/Users/{your name}/connectionstring.txt"
    let dep2 = Environment.GetEnvironmentVariable "DEP_2"

    let private r = Random()
    let dep3() = r.Next() // Problematic if multiple threads use this

    let function1 arg = doStuffWith dep1 dep2 dep3 arg
    let function2 arg = doSutffWith dep1 dep2 dep3 arg
```

<span data-ttu-id="67bf0-148">이것은 종종 몇 가지 이유로 나쁜 생각:</span><span class="sxs-lookup"><span data-stu-id="67bf0-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="67bf0-149">첫째, 응용 프로그램 구성을 `dep1` 와 `dep2`함께 코드베이스에 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="67bf0-150">이 문제는 더 큰 코드베이스에서 유지 관리하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="67bf0-151">둘째, 정적 초기화 된 데이터는 구성 요소 자체가 여러 스레드를 사용하는 경우 스레드가 안전하지 않은 값을 포함해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="67bf0-152">이것은 분명히 에 `dep3`의해 위반됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="67bf0-153">마지막으로 모듈 초기화는 전체 컴파일 단위에 대한 정적 생성자로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="67bf0-154">해당 모듈의 let-bound 값 초기화에서 오류가 발생하면 응용 `TypeInitializationException` 프로그램의 전체 수명 동안 캐시되는 것으로 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="67bf0-155">이것은 진단하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="67bf0-156">일반적으로 추론을 시도할 수 있는 내부 예외가 있지만 그렇지 않은 경우 근본 원인을 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="67bf0-157">대신 간단한 클래스를 사용하여 종속성을 유지하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="67bf0-158">이렇게 하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-158">This enables the following:</span></span>

1. <span data-ttu-id="67bf0-159">API 자체 외부에서 종속 상태를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="67bf0-160">이제 API 외부에서 구성을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="67bf0-161">종속 값에 대한 초기화 오류는 `TypeInitializationException`로 나타나지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="67bf0-162">이제 API를 더 쉽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="67bf0-163">오류 관리</span><span class="sxs-lookup"><span data-stu-id="67bf0-163">Error management</span></span>

<span data-ttu-id="67bf0-164">대형 시스템의 오류 관리는 복잡하고 미묘한 노력이며 시스템이 내결함성이 있고 잘 행동하도록 보장하는 실버 글머리 기호가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="67bf0-165">다음 지침은 이 어려운 공간을 탐색하는 데 지침을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="67bf0-166">도메인에 고유한 형식의 오류 사례 및 잘못된 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="67bf0-167">[구별된 공용 구조체를](../language-reference/discriminated-unions.md)사용하면 F#을 사용하여 형식 시스템에서 잘못된 프로그램 상태를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="67bf0-168">다음은 그 예입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="67bf0-169">이 경우 은행 계좌에서 돈을 인출하는 데 실패할 수 있는 세 가지 알려진 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="67bf0-170">각 오류 사례는 형식에 표시되므로 프로그램 전체에서 안전하게 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="67bf0-171">일반적으로 도메인에서 **오류가 발생할** 수 있는 다양한 방법을 모델링할 수 있는 경우 오류 처리 코드는 더 이상 일반 프로그램 흐름 외에도 처리해야 하는 것으로 처리되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="67bf0-172">그것은 단순히 정상적인 프로그램 흐름의 일부이며, **뛰어난**간주되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="67bf0-173">이두 가지 주요 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="67bf0-174">시간이 지남에 따라 도메인이 변경됨에 따라 유지 관리가 더 쉬워집니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="67bf0-175">오류 케이스는 단위 테스트가 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="67bf0-176">오류를 형식으로 나타낼 수 없는 경우 예외 사용</span><span class="sxs-lookup"><span data-stu-id="67bf0-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="67bf0-177">문제 도메인에 모든 오류를 나타낼 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="67bf0-178">이러한 종류의 오류는 본질적으로 *예외적이므로* F #에서 예외를 발생시키고 catch할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="67bf0-179">먼저 [예외 디자인 지침을](../../standard/design-guidelines/exceptions.md)읽는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="67bf0-180">F#에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-180">These are also applicable to F#.</span></span>

<span data-ttu-id="67bf0-181">예외를 발생시키기 위해 F#에서 사용할 수 있는 기본 구문은 다음과 같은 기본 설정 순서로 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="67bf0-182">함수</span><span class="sxs-lookup"><span data-stu-id="67bf0-182">Function</span></span> | <span data-ttu-id="67bf0-183">구문</span><span class="sxs-lookup"><span data-stu-id="67bf0-183">Syntax</span></span> | <span data-ttu-id="67bf0-184">목적</span><span class="sxs-lookup"><span data-stu-id="67bf0-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="67bf0-185">지정된 `System.ArgumentNullException` 인수 이름으로 a를 발생시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="67bf0-186">지정된 `System.ArgumentException` 인수 이름과 메시지를 가진 a를 발생시다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="67bf0-187">지정된 `System.InvalidOperationException` 메시지와 함께 를 발생 시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="67bf0-188">예외를 throw하기 위한 범용 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="67bf0-189">지정된 `System.Exception` 메시지와 함께 를 발생 시면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="67bf0-190">형식 `System.Exception` 문자열 및 해당 입력에 의해 결정된 메시지와 함께 a를 발생시다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="67bf0-191">을 `nullArg` `invalidArg` 던지고 `invalidOp` 적절한 `ArgumentNullException` `ArgumentException` `InvalidOperationException` 경우 메커니즘으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="67bf0-192">및 함수는 일반적으로 특정 예외가 아니라 `Exception` 기본 형식을 발생하므로 피해야 합니다. `failwithf` `failwith`</span><span class="sxs-lookup"><span data-stu-id="67bf0-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="67bf0-193">[예외 디자인 지침에](../../standard/design-guidelines/exceptions.md)따라 가능한 경우 보다 구체적인 예외를 발생시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="67bf0-194">예외 처리 구문 사용</span><span class="sxs-lookup"><span data-stu-id="67bf0-194">Using exception-handling syntax</span></span>

<span data-ttu-id="67bf0-195">F#은 `try...with` 구문을 통해 예외 패턴을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="67bf0-196">패턴을 일치시키는 예외상황에서 수행할 기능을 조정하는 것은 코드를 깨끗하게 유지하려는 경우 다소 까다로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="67bf0-197">이를 처리하는 한 가지 방법은 활성 [패턴을](../language-reference/active-patterns.md) 예외 자체로 오류 사례와 함께 둘러싼 기능을 그룹화하는 수단으로 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="67bf0-198">예를 들어 예외를 throw할 때 예외 메타데이터에 중요한 정보를 둘러싸는 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="67bf0-199">활성 패턴 내에서 캡처된 예외본문에 유용한 값을 래핑 해제하고 해당 값을 반환하는 것은 경우에 따라 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="67bf0-200">예외를 대체하기 위해 모나드 오류 처리를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="67bf0-201">예외는 함수형 프로그래밍에서 다소 금기사항으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="67bf0-202">실제로 예외는 순도를 위반하므로 기능적이지 않다고 간주하는 것이 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="67bf0-203">그러나 코드가 실행되어야 하는 위치와 런타임 오류가 발생할 수 있는 현실을 무시합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="67bf0-204">일반적으로 대부분의 것이 순수하거나 총체적이지 않은다는 가정하에 코드를 작성하여 불쾌한 놀라움을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="67bf0-205">.NET 런타임 및 크로스언어 생태계전체에서의 관련성 및 적합성과 관련하여 예외의 다음과 같은 핵심 강점/측면을 고려하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="67bf0-206">여기에는 자세한 진단 정보가 포함되어 있어 문제를 디버깅할 때 매우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="67bf0-207">런타임 및 기타 .NET 언어에서 잘 이해됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="67bf0-208">임시로 의미 체계의 일부 하위 집합을 구현하여 예외를 *피하기* 위해 방해가 되는 코드와 비교할 때 중요한 상용구를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="67bf0-209">이 세 번째 지점은 매우 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-209">This third point is critical.</span></span> <span data-ttu-id="67bf0-210">사소한 복잡한 작업의 경우 예외를 사용하지 않으면 다음과 같은 구조를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="67bf0-211">"문자열 형식"오류에 패턴 일치와 같은 깨지기 쉬운 코드로 쉽게 이어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="67bf0-212">또한 "더 좋은" 형식을 반환 하는 "간단한" 함수에 대 한 욕망에서 예외를 삼 키는 유혹 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="67bf0-213">안타깝게도 `tryReadAllText` 파일 시스템에서 발생할 수 있는 수많은 예외를 기반으로 수많은 예외를 throw할 수 있으며, 이 코드는 사용자 환경에서 실제로 잘못될 수 있는 것에 대한 정보를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="67bf0-214">이 코드를 결과 유형으로 바꾸면 "문자열 형식" 오류 메시지 구문 분석으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Ok
    with e -> Error e.Message

let r = tryReadAllText "path-to-file"
match r with
| Ok text -> ...
| Error e ->
    if e.Contains "uh oh, here we go again..." then ...
    else ...
```

<span data-ttu-id="67bf0-215">또한 예외 개체 자체를 `Error` 생성자에 배치하면 함수가 아닌 호출 사이트에서 예외 형식을 올바르게 처리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="67bf0-216">이렇게 하면 API 호출자로 처리하는 것이 재미없는 것으로 악명 높은 검사된 예외가 효과적으로 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="67bf0-217">위의 예제에 대한 좋은 대안은 *특정* 예외를 catch하고 해당 예외의 컨텍스트에서 의미 있는 값을 반환하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="67bf0-218">다음과 같이 `tryReadAllText` 함수를 수정하면 더 많은 의미가 `None` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="67bf0-219">이제 이 함수는 포괄 함수로 작동하는 대신 파일이 발견되지 않은 경우 케이스를 제대로 처리하고 해당 의미를 반환에 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="67bf0-220">이 반환 값은 컨텍스트 정보를 삭제하거나 호출자가 코드의 해당 지점에서 관련이 없을 수 있는 경우를 처리하도록 강요하지 는 않지만 해당 오류 사례에 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="67bf0-221">중첩되지 `Result<'Success, 'Error>` 않은 기본 작업에 적합한 유형과 같은 형식과 F# 선택적 형식은 무언가 또는 *아무것도* *반환할* 수 있는 시기를 나타내는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="67bf0-222">그러나 예외를 대체하는 것은 아니며 예외를 대체하기 위해 사용해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="67bf0-223">대신 예외 및 오류 관리 정책의 특정 측면을 대상으로 처리하기 위해 신중하게 적용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="67bf0-224">부분 응용 프로그램 및 포인트 없는 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="67bf0-224">Partial application and point-free programming</span></span>

<span data-ttu-id="67bf0-225">F#은 부분 응용 프로그램을 지원하므로 포인트 프리 스타일로 프로그래밍하는 다양한 방법을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="67bf0-226">이는 모듈 내에서 코드를 다시 사용하거나 무언가를 구현하는 데 도움이 될 수 있지만 공개적으로 노출하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-226">This can be beneficial for code reuse within a module or the implementation of something, but it is not something to expose publicly.</span></span> <span data-ttu-id="67bf0-227">일반적으로 포인트 프리 프로그래밍은 그 자체로 미덕이 아니며 스타일에 몰두하지 않는 사람들에게 중요한 인지 장벽을 추가 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="67bf0-228">공용 API에서 부분 응용 프로그램 및 카레를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="67bf0-229">거의 예외가 없는 경우 공용 API에서 부분 응용 프로그램을 사용하는 것은 소비자에게 혼동을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="67bf0-230">일반적으로 `let`F# 코드의 -bound 값은 **함수 값이**아닌 **값입니다.**</span><span class="sxs-lookup"><span data-stu-id="67bf0-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="67bf0-231">값과 함수 값을 함께 혼합하면 특히 함수를 구성하는 것과 같은 `>>` 연산자와 결합된 경우 인지 오버헤드가 상당히 적은 코드 줄을 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="67bf0-232">포인트 프리 프로그래밍의 툴링 의미 고려</span><span class="sxs-lookup"><span data-stu-id="67bf0-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="67bf0-233">커리 함수는 인수에 레이블을 지정하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="67bf0-234">이것은 툴링 에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-234">This has tooling implications.</span></span> <span data-ttu-id="67bf0-235">다음 두 가지 기능을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="67bf0-236">둘 다 유효한 함수이지만 `funcWithApplication` 커리 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="67bf0-237">편집기에서 해당 형식 위로 마우스를 가져가면 다음과 같은 이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="67bf0-238">호출 사이트에서 Visual `string` Studio와 같은 도구 설명은 입력 유형이 `int` 실제로 무엇을 나타내는지에 대한 의미 있는 정보를 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="67bf0-239">공개적으로 사용할 수 있는 `funcWithApplication` 점 없는 코드가 발생하는 경우 도구링이 인수에 대한 의미 있는 이름을 선택할 수 있도록 전체 θ-expansion를 수행하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="67bf0-240">또한 포인트 없는 코드를 디버깅하는 것은 불가능하지는 않더라도 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="67bf0-241">디버깅 도구는 이름에 바인딩된 값(예: `let` 바인딩)에 의존하므로 실행 중간에 중간 값을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="67bf0-242">코드에 검사할 값이 없는 경우 디버깅할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="67bf0-243">나중에 디버깅 도구는 이전에 실행된 경로를 기반으로 이러한 값을 합성하기 위해 진화할 수 있지만 *잠재적인* 디버깅 기능에 대한 베팅을 헤지하는 것은 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="67bf0-244">내부 상용구를 줄이는 기술로 부분 적용을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="67bf0-245">이전 지점과 달리 부분 응용 프로그램은 응용 프로그램 내부 또는 API의 내부를 더 깊게 줄이는 훌륭한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="67bf0-246">상용구가 종종 다루기 힘든 더 복잡한 API의 구현을 단위 테스트하는 데 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="67bf0-247">예를 들어 다음 코드에서는 이러한 프레임워크에 대한 외부 종속성을 취하고 관련 맞춤형 API를 학습하지 않고도 대부분의 모의 프레임워크가 제공하는 작업을 수행하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="67bf0-248">예를 들어 다음 솔루션 지형을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="67bf0-249">`ImplementationLogic.fsproj`다음과 같은 코드가 노출될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="67bf0-250">단위 `Transactions.doTransaction` `ImplementationLogic.Tests.fsproj` 테스트는 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="67bf0-251">모의 컨텍스트 `doTransaction` 개체를 부분적으로 적용하면 매번 조롱된 컨텍스트를 생성할 필요 없이 모든 단위 테스트에서 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member _.TheFirstMember() = ...
        member _.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="67bf0-252">이 기술은 전체 코드베이스에 보편적으로 적용되어서는 안 되지만 복잡한 내부 및 단위 테스트에 대한 상용구를 줄이는 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="67bf0-253">Access Control</span><span class="sxs-lookup"><span data-stu-id="67bf0-253">Access control</span></span>

<span data-ttu-id="67bf0-254">F#에는 .NET 런타임에서 사용할 수 있는 [액세스 제어에](../language-reference/access-control.md)대한 여러 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="67bf0-255">형식에만 사용할 수 있는 것이 아니라 함수에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="67bf0-256">비유형`public` 및 멤버를 공개적으로 사용할 수 있어야 할 때까지 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="67bf0-257">또한 소비자가 커플하는 것을 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="67bf0-258">모든 도우미 기능을 `private`유지 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="67bf0-259">도우미 함수가 `[<AutoOpen>]` 많을 경우 개인 도우미 함수 모듈에서 사용하는 것을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="67bf0-260">형식 추론 및 제네릭</span><span class="sxs-lookup"><span data-stu-id="67bf0-260">Type inference and generics</span></span>

<span data-ttu-id="67bf0-261">형식 추론은 상용구를 많이 입력하는 것을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="67bf0-262">또한 F# 컴파일러의 자동 일반화를 사용하면 추가 노력 없이 더 많은 제네릭 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="67bf0-263">그러나 이러한 기능은 보편적으로 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="67bf0-264">공용 API에서 명시적 형식을 사용하여 인수 이름에 레이블을 지정하는 것이 고려되며 이에 대한 형식 추론에 의존하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="67bf0-265">그 이유는 **컴파일러가** 아니라 API의 모양을 제어해야 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="67bf0-266">컴파일러는 형식을 유추할 때 훌륭한 작업을 수행할 수 있지만 형식에 의존하는 내부 가 변경된 경우 API 의 모양이 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="67bf0-267">이것은 당신이 원하는 것 일 수 있지만, 그것은 거의 확실히 다운 스트림 소비자가 처리해야 할 것입니다 깨는 API 변경을 초래할 것이다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="67bf0-268">대신 공용 API의 모양을 명시적으로 제어하는 경우 이러한 주요 변경 내용을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="67bf0-269">DDD 용어로, 이것은 부패 방지 계층으로 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="67bf0-270">일반 인수에 의미 있는 이름을 지정하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="67bf0-271">특정 도메인에 국한되지 않는 진정한 일반 코드를 작성하지 않는 한 의미 있는 이름은 다른 프로그래머가 작업 중인 도메인을 이해하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="67bf0-272">예를 들어 문서 데이터베이스와 상호 작용하는 컨텍스트에서 명명된 `'Document` 형식 매개 변수를 사용하면 작업 중인 함수 나 멤버에서 일반 문서 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="67bf0-273">PascalCase를 사용 하 여 일반 형식 매개 변수의 이름을 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="67bf0-274">이것은 .NET에서 작업을 수행하는 일반적인 방법이므로 snake_case 나 camelCase보다는 파스칼 케이스를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="67bf0-275">마지막으로 자동 일반화가 F# 또는 대규모 코드베이스를 새로 접하는 사람들에게 항상 도움이 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="67bf0-276">일반적인 구성 요소를 사용 하 여 인지 오버 헤드가 있다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="67bf0-277">또한 자동으로 일반화된 함수가 다른 입력 형식과 함께 사용되지 않는 경우(이와 같이 사용하려는 경우는 물론) 해당 시점에서 일반 함수가 되는 것은 실질적인 이점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="67bf0-278">작성하는 코드가 실제로 제네릭이 되는 것이 도움이 될지 항상 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="67bf0-279">성능</span><span class="sxs-lookup"><span data-stu-id="67bf0-279">Performance</span></span>

### <a name="prefer-structs-for-small-data-types"></a><span data-ttu-id="67bf0-280">작은 데이터 유형에 대한 구조체 선호</span><span class="sxs-lookup"><span data-stu-id="67bf0-280">Prefer structs for small data types</span></span>

<span data-ttu-id="67bf0-281">구조체(값 유형라고도 함)를 사용하면 일반적으로 개체 할당을 피하기 때문에 일부 코드의 성능이 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-281">Using structs (also called Value Types) can often result in higher performance for some code because it typically avoids allocating objects.</span></span> <span data-ttu-id="67bf0-282">그러나 구조체가 항상 "더 빠르게" 단추는 아닙니다: 구조체의 데이터 크기가 16바이트를 초과하는 경우 데이터를 복사하면 참조 형식을 사용하는 것보다 CPU 시간이 더 많이 소요될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-282">However, structs are not always a "go faster" button: if the size of the data in a struct exceeds 16 bytes, copying the data can often result in more CPU time spend than using a reference type.</span></span>

<span data-ttu-id="67bf0-283">구조체를 사용해야 하는지 확인하려면 다음 조건을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-283">To determine if you should use a struct, consider the following conditions:</span></span>

- <span data-ttu-id="67bf0-284">데이터 크기가 16바이트 이하인 경우.</span><span class="sxs-lookup"><span data-stu-id="67bf0-284">If the size of your data is 16 bytes or smaller.</span></span>
- <span data-ttu-id="67bf0-285">이러한 데이터 형식 중 상당수가 실행 중인 프로그램의 메모리에 상주할 가능성이 있는 경우</span><span class="sxs-lookup"><span data-stu-id="67bf0-285">If you're likely to have many of these data types resident in memory in a running program.</span></span>

<span data-ttu-id="67bf0-286">첫 번째 조건이 적용되는 경우 일반적으로 구조체를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-286">If the first condition applies, you should generally use a struct.</span></span> <span data-ttu-id="67bf0-287">둘 다 적용 하는 경우 거의 항상 구조체를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-287">If both apply, you should almost always use a struct.</span></span> <span data-ttu-id="67bf0-288">이전 조건이 적용되는 경우도 있지만 구조체를 사용하는 것이 참조 형식을 사용하는 것보다 더 좋거나 나쁘지는 않지만 드물다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-288">There may be some cases where the previous conditions apply, but using a struct is no better or worse than using a reference type, but they are likely to be rare.</span></span> <span data-ttu-id="67bf0-289">하지만 이런 식으로 변경할 때는 항상 측정하는 것이 중요하며 가정이나 직관에 따라 작동하지 않는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-289">It's important to always measure when making changes like this, though, and not operate on assumption or intuition.</span></span>

#### <a name="prefer-struct-tuples-when-grouping-small-value-types"></a><span data-ttu-id="67bf0-290">작은 값 형식을 그룹화할 때 구조체 투플 선호</span><span class="sxs-lookup"><span data-stu-id="67bf0-290">Prefer struct tuples when grouping small value types</span></span>

<span data-ttu-id="67bf0-291">다음 두 가지 기능을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-291">Consider the following two functions:</span></span>

```fsharp
let rec runWithTuple t offset times =
    let offsetValues x y z offset =
        (x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let (x, y, z) = t
        let r = offsetValues x y z offset
        runWithTuple r offset (times - 1)

let rec runWithStructTuple t offset times =
    let offsetValues x y z offset =
        struct(x + offset, y + offset, z + offset)

    if times <= 0 then
        t
    else
        let struct(x, y, z) = t
        let r = offsetValues x y z offset
        runWithStructTuple r offset (times - 1)
```

<span data-ttu-id="67bf0-292">[BenchmarkDotNet과](https://benchmarkdotnet.org/)같은 통계 벤치마킹 도구를 사용하여 이러한 함수를 벤치마킹하면 구조형 투플을 사용하는 `runWithStructTuple` 함수가 40% 더 빠르게 실행되고 메모리가 할당되지 않는다는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-292">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that the `runWithStructTuple` function that uses struct tuples runs 40% faster and allocates no memory.</span></span>

<span data-ttu-id="67bf0-293">그러나 이러한 결과가 항상 사용자 고유의 코드에서 발생하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-293">However, these results won't always be the case in your own code.</span></span> <span data-ttu-id="67bf0-294">함수를 "를 `inline`으로 표시하는 경우 참조 튜플을 사용하는 코드는 몇 가지 추가 최적화를 얻을 수 있거나 할당할 코드가 단순히 최적화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-294">If you mark a function as `inline`, code that uses reference tuples may get some additional optimizations, or code that would allocate could simply be optimized away.</span></span> <span data-ttu-id="67bf0-295">성능에 관한 때마다 항상 결과를 측정해야 하며 가정이나 직관에 따라 작동하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-295">You should always measure results whenever performance is concerned, and never operate based on assumption or intuition.</span></span>

#### <a name="prefer-struct-records-when-the-data-type-is-small"></a><span data-ttu-id="67bf0-296">데이터 형식이 작은 경우 구조체 레코드 선호</span><span class="sxs-lookup"><span data-stu-id="67bf0-296">Prefer struct records when the data type is small</span></span>

<span data-ttu-id="67bf0-297">앞에서 설명한 엄지 손가락 규칙에는 [F# 레코드 형식도](../language-reference/records.md)있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-297">The rule of thumb described earlier also holds for [F# record types](../language-reference/records.md).</span></span> <span data-ttu-id="67bf0-298">이를 처리하는 다음 데이터 형식 및 함수를 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-298">Consider the following data types and functions that process them:</span></span>

```fsharp
type Point = { X: float; Y: float; Z: float }

[<Struct>]
type SPoint = { X: float; Y: float; Z: float }

let rec processPoint (p: Point) offset times =
    let inline offsetValues (p: Point) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processPoint r offset (times - 1)

let rec processStructPoint (p: SPoint) offset times =
    let inline offsetValues (p: SPoint) offset =
        { p with X = p.X + offset; Y = p.Y + offset; Z = p.Z + offset }

    if times <= 0 then
        p
    else
        let r = offsetValues p offset
        processStructPoint r offset (times - 1)
```

<span data-ttu-id="67bf0-299">이는 이전 튜플 코드와 유사하지만 이번에는 예제에서 레코드와 인라인된 내부 함수를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-299">This is similar to the previous tuple code, but this time the example uses records and an inlined inner function.</span></span>

<span data-ttu-id="67bf0-300">[BenchmarkDotNet과](https://benchmarkdotnet.org/)같은 통계 벤치마킹 도구를 사용하여 이러한 함수를 `processStructPoint` 벤치마킹하면 거의 60 % 더 빨리 실행되고 관리되는 힙에 아무 것도 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-300">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `processStructPoint` runs nearly 60% faster and allocates nothing on the managed heap.</span></span>

#### <a name="prefer-struct-discriminated-unions-when-the-data-type-is-small"></a><span data-ttu-id="67bf0-301">데이터 형식이 작은 경우 구조체 구분 공용 구조체 선호</span><span class="sxs-lookup"><span data-stu-id="67bf0-301">Prefer struct discriminated unions when the data type is small</span></span>

<span data-ttu-id="67bf0-302">구조체 투플 및 레코드가 있는 성능에 대한 이전 관찰은 [F# 차별 된 공용 구조체에](../language-reference/discriminated-unions.md)대해서도 보유하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-302">The previous observations about performance with struct tuples and records also holds for [F# Discriminated Unions](../language-reference/discriminated-unions.md).</span></span> <span data-ttu-id="67bf0-303">다음 코드를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="67bf0-303">Consider the following code:</span></span>

```fsharp
    type Name = Name of string

    [<Struct>]
    type SName = SName of string

    let reverseName (Name s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> Name

    let structReverseName (SName s) =
        s.ToCharArray()
        |> Array.rev
        |> string
        |> SName
```

<span data-ttu-id="67bf0-304">도메인 모델링을 위해 이와 같은 단일 사례 구별 공용 구조체를 정의하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-304">It's common to define single-case Discriminated Unions like this for domain modeling.</span></span> <span data-ttu-id="67bf0-305">[BenchmarkDotNet과](https://benchmarkdotnet.org/)같은 통계 벤치마킹 도구를 사용하여 이러한 함수를 `structReverseName` 벤치마킹하면 작은 `reverseName` 문자열보다 약 25 % 더 빨리 실행되는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-305">When you benchmark these functions with a statistical benchmarking tool like [BenchmarkDotNet](https://benchmarkdotnet.org/), you'll find that `structReverseName` runs about 25% faster than `reverseName` for small strings.</span></span> <span data-ttu-id="67bf0-306">큰 문자열의 경우 둘 다 거의 동일하게 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-306">For large strings, both perform about the same.</span></span> <span data-ttu-id="67bf0-307">따라서 이 경우 항상 구조체를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-307">So, in this case, it's always preferable to use a struct.</span></span> <span data-ttu-id="67bf0-308">앞서 언급했듯이, 항상 가정이나 직관에 따라 측정하고 작동하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-308">As previously mentioned, always measure and do not operate on assumptions or intuition.</span></span>

<span data-ttu-id="67bf0-309">이전 예제에서는 구조체 구별 된 공용 구조체가 더 나은 성능을 보여 주었지만 도메인을 모델링 할 때 더 큰 구별 공용 구조체가 있는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-309">Although the previous example showed that a struct Discriminated Union yielded better performance, it is common to have larger Discriminated Unions when modeling a domain.</span></span> <span data-ttu-id="67bf0-310">더 많은 복사가 포함될 수 있기 때문에 이와 같은 더 큰 데이터 형식은 작업에 따라 구조체인 경우 잘 수행되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-310">Larger data types like that may not perform as well if they are structs depending on the operations on them, since more copying could be involved.</span></span>

### <a name="functional-programming-and-mutation"></a><span data-ttu-id="67bf0-311">함수형 프로그래밍 및 돌연변이</span><span class="sxs-lookup"><span data-stu-id="67bf0-311">Functional programming and mutation</span></span>

<span data-ttu-id="67bf0-312">F# 값은 기본적으로 변경할 수 없으며 특정 클래스의 버그(특히 동시성 및 병렬 처리와 관련된 버그)를 방지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-312">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="67bf0-313">그러나 경우에 따라 실행 시간 또는 메모리 할당의 최적(또는 합리적인) 효율성을 달성하기 위해 작업 범위가 상태 내 돌연변이를 사용하여 구현되는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-313">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="67bf0-314">이는 키워드와 함께 F#을 사용하면 옵트인할 수 `mutable` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-314">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="67bf0-315">F `mutable` #에서의 사용은 기능적 순도와 확률을 느낄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-315">Use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="67bf0-316">이것은 이해할 수 있지만, 모든 곳에서 기능적 순도는 성능 목표와 상충될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-316">This is understandable, but functional purity everywhere can be at odds with performance goals.</span></span> <span data-ttu-id="67bf0-317">타협은 호출자가 함수를 호출 할 때 발생하는 일에 대해 걱정할 필요가 있도록 돌연변이를 캡슐화하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-317">A compromise is to encapsulate mutation such that callers need not care about what happens when they call a function.</span></span> <span data-ttu-id="67bf0-318">이를 통해 성능에 중요한 코드에 대한 돌연변이 기반 구현을 통해 기능 인터페이스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-318">This allows you to write a functional interface over a mutation-based implementation for performance-critical code.</span></span>

#### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="67bf0-319">변경할 수 없는 인터페이스에서 변경 가능한 코드 래핑</span><span class="sxs-lookup"><span data-stu-id="67bf0-319">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="67bf0-320">참조 투명성을 목표로 하는 경우 성능에 중요한 함수의 가변적 하복부를 노출하지 않는 코드를 작성하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-320">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="67bf0-321">예를 들어 다음 코드는 `Array.contains` F# 코어 라이브러리에서 함수를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-321">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

```fsharp
[<CompiledName("Contains")>]
let inline contains value (array:'T[]) =
    checkNonNull "array" array
    let mutable state = false
    let mutable i = 0
    while not state && i < array.Length do
        state <- value = array.[i]
        i <- i + 1
    state
```

<span data-ttu-id="67bf0-322">이 함수를 여러 번 호출해도 기본 배열이 변경되지 않으며 사용할 때 변경 가능한 상태를 유지할 필요도 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-322">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="67bf0-323">내부의 거의 모든 코드 줄이 돌연변이를 사용하더라도 참조적으로 투명합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-323">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

#### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="67bf0-324">클래스에서 가변 데이터 캡슐화 고려</span><span class="sxs-lookup"><span data-stu-id="67bf0-324">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="67bf0-325">이전 예제는 단일 함수를 사용하여 가변 가능한 데이터를 사용하여 작업을 캡슐화했습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-325">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="67bf0-326">이 경우 보다 복잡한 데이터 집합에 항상 충분하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-326">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="67bf0-327">다음 함수 집합을 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-327">Consider the following sets of functions:</span></span>

```fsharp
open System.Collections.Generic

let addToClosureTable (key, value) (t: Dictionary<_,_>) =
    if not (t.ContainsKey(key)) then
        t.Add(key, value)
    else
        t.[key] <- value

let closureTableCount (t: Dictionary<_,_>) = t.Count

let closureTableContains (key, value) (t: Dictionary<_, HashSet<_>>) =
    match t.TryGetValue(key) with
    | (true, v) -> v.Equals(value)
    | (false, _) -> false
```

<span data-ttu-id="67bf0-328">이 코드는 수행되지만 호출자가 유지 관리하는 돌연변이 기반 데이터 구조를 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-328">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="67bf0-329">변경할 수 있는 기본 멤버가 없는 클래스 내부에 래핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-329">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member _.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member _.Count = t.Count

    member _.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="67bf0-330">`Closure1Table`기본 돌연변이 기반 데이터 구조를 캡슐화하므로 호출자가 기본 데이터 구조를 유지 관리하도록 강요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-330">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="67bf0-331">클래스는 호출자에게 세부 정보를 노출하지 않고 돌연변이 기반의 데이터와 루틴을 캡슐화하는 강력한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-331">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

#### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="67bf0-332">셀 `let mutable` 참조 선호</span><span class="sxs-lookup"><span data-stu-id="67bf0-332">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="67bf0-333">참조 셀은 값 자체가 아닌 값에 대한 참조를 나타내는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-333">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="67bf0-334">성능이 중요한 코드에 사용할 수는 있지만 권장되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-334">Although they can be used for performance-critical code, they are not recommended.</span></span> <span data-ttu-id="67bf0-335">다음과 같은 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="67bf0-335">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="67bf0-336">참조 셀의 사용은 이제 기본 데이터를 디레참조하고 다시 참조해야하는 모든 후속 코드를 "오염"합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-336">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="67bf0-337">대신 다음을 고려하십시오. `let mutable`</span><span class="sxs-lookup"><span data-stu-id="67bf0-337">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="67bf0-338">lambda 식 중간에 있는 단일 돌연변이 점을 제외하고, 접촉하는 `acc` 다른 모든 코드는 정상 `let`-바인딩된 불변값의 사용과 다르지 않은 방식으로 그렇게 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-338">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="67bf0-339">이렇게 하면 시간이 지남에 따라 쉽게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-339">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="67bf0-340">개체 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="67bf0-340">Object programming</span></span>

<span data-ttu-id="67bf0-341">F#은 개체 및 객체 지향(OO) 개념을 완전히 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-341">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="67bf0-342">많은 OO 개념이 강력하고 유용하지만 모든 개념이 사용하기에 이상적인 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-342">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="67bf0-343">다음 목록은 상위 수준에서 OO 기능 범주에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-343">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="67bf0-344">**여러 상황에서 이러한 기능을 사용하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="67bf0-344">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="67bf0-345">도트 표기`x.Length`()</span><span class="sxs-lookup"><span data-stu-id="67bf0-345">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="67bf0-346">인스턴스 멤버</span><span class="sxs-lookup"><span data-stu-id="67bf0-346">Instance members</span></span>
* <span data-ttu-id="67bf0-347">암시적 생성자</span><span class="sxs-lookup"><span data-stu-id="67bf0-347">Implicit constructors</span></span>
* <span data-ttu-id="67bf0-348">정적 멤버</span><span class="sxs-lookup"><span data-stu-id="67bf0-348">Static members</span></span>
* <span data-ttu-id="67bf0-349">인덱서 표기 ()`arr.[x]`</span><span class="sxs-lookup"><span data-stu-id="67bf0-349">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="67bf0-350">명명된 인수 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="67bf0-350">Named and Optional arguments</span></span>
* <span data-ttu-id="67bf0-351">인터페이스 및 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="67bf0-351">Interfaces and interface implementations</span></span>

<span data-ttu-id="67bf0-352">**먼저 이러한 기능에 도달하지 말고 문제를 해결하는 데 편리할 때 신중하게 적용하십시오.**</span><span class="sxs-lookup"><span data-stu-id="67bf0-352">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="67bf0-353">메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="67bf0-353">Method overloading</span></span>
* <span data-ttu-id="67bf0-354">캡슐화된 변경 가능 데이터</span><span class="sxs-lookup"><span data-stu-id="67bf0-354">Encapsulated mutable data</span></span>
* <span data-ttu-id="67bf0-355">형식의 연산자</span><span class="sxs-lookup"><span data-stu-id="67bf0-355">Operators on types</span></span>
* <span data-ttu-id="67bf0-356">자동 속성</span><span class="sxs-lookup"><span data-stu-id="67bf0-356">Auto properties</span></span>
* <span data-ttu-id="67bf0-357">구현 `IDisposable` 및`IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="67bf0-357">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="67bf0-358">형식 확장</span><span class="sxs-lookup"><span data-stu-id="67bf0-358">Type extensions</span></span>
* <span data-ttu-id="67bf0-359">이벤트</span><span class="sxs-lookup"><span data-stu-id="67bf0-359">Events</span></span>
* <span data-ttu-id="67bf0-360">구조체</span><span class="sxs-lookup"><span data-stu-id="67bf0-360">Structs</span></span>
* <span data-ttu-id="67bf0-361">대리자</span><span class="sxs-lookup"><span data-stu-id="67bf0-361">Delegates</span></span>
* <span data-ttu-id="67bf0-362">열거형</span><span class="sxs-lookup"><span data-stu-id="67bf0-362">Enums</span></span>

<span data-ttu-id="67bf0-363">**일반적으로 이러한 기능을 사용해야 하는 경우가 아니면 이러한 기능을 사용하지 마십시오.**</span><span class="sxs-lookup"><span data-stu-id="67bf0-363">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="67bf0-364">상속 기반 유형 계층 구조 및 구현 상속</span><span class="sxs-lookup"><span data-stu-id="67bf0-364">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="67bf0-365">널 및`Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="67bf0-365">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="67bf0-366">상속보다 컴포지션 선호</span><span class="sxs-lookup"><span data-stu-id="67bf0-366">Prefer composition over inheritance</span></span>

<span data-ttu-id="67bf0-367">[상속에 대한 컴포지션은](https://en.wikipedia.org/wiki/Composition_over_inheritance) 좋은 F# 코드가 준수할 수 있는 오랜 관용구입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-367">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="67bf0-368">기본 원칙은 기본 클래스를 노출하지 말고 호출자에게 해당 기본 클래스에서 상속하여 기능을 얻도록 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-368">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="67bf0-369">클래스가 필요하지 않은 경우 개체 식을 사용하여 인터페이스를 구현합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-369">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="67bf0-370">[개체 표현식을](../language-reference/object-expressions.md) 사용하면 즉시 인터페이스를 구현할 수 있으므로 클래스 내에서 인터페이스를 사용할 필요 없이 구현된 인터페이스를 값으로 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-370">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="67bf0-371">특히 _인터페이스만_ 구현해야 하고 전체 클래스가 필요하지 않은 경우에 편리합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-371">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="67bf0-372">예를 들어, `open` 다음에 대한 문이 없는 기호를 추가한 경우 [Ionide에서](http://ionide.io/) 실행되는 코드는 코드 수정 작업을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-372">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

```fsharp
    let private createProvider () =
        { new CodeActionProvider with
            member this.provideCodeActions(doc, range, context, ct) =
                let diagnostics = context.diagnostics
                let diagnostic = diagnostics |> Seq.tryFind (fun d -> d.message.Contains "Unused open statement")
                let res =
                    match diagnostic with
                    | None -> [||]
                    | Some d ->
                        let line = doc.lineAt d.range.start.line
                        let cmd = createEmpty<Command>
                        cmd.title <- "Remove unused open"
                        cmd.command <- "fsharp.unusedOpenFix"
                        cmd.arguments <- Some ([| doc |> unbox; line.range |> unbox; |] |> ResizeArray)
                        [|cmd |]
                res
                |> ResizeArray
                |> U2.Case1
        }
```

<span data-ttu-id="67bf0-373">Visual Studio 코드 API와 상호 작용할 때 클래스가 필요하지 않으므로 개체 표현식은 이에 대한 이상적인 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-373">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="67bf0-374">또한 임시 방식으로 테스트 루틴이 있는 인터페이스를 스텁하려는 경우 단위 테스트에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-374">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="67bf0-375">서명을 줄이려면 약어 를 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-375">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="67bf0-376">[유형 약어는](../language-reference/type-abbreviations.md) 함수 시그니처 또는 보다 복잡한 형식과 같은 다른 형식에 레이블을 할당하는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-376">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="67bf0-377">예를 들어 다음 별칭은 딥 러닝 라이브러리인 [CNTK를](https://docs.microsoft.com/cognitive-toolkit/)사용하여 계산을 정의하는 데 필요한 레이블을 할당합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-377">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="67bf0-378">이름은 `Computation` 별칭인 서명과 일치하는 함수를 나타내는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-378">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="67bf0-379">이와 같은 유형 약어를 사용하면 편리하고 간결한 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-379">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="67bf0-380">도메인을 나타내는 유형 약어를 사용하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-380">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="67bf0-381">유형 약어는 함수 시그니처에 이름을 지정하는 데 편리하지만 다른 형식을 축약할 때 혼동을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-381">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="67bf0-382">이 약어를 고려하십시오.</span><span class="sxs-lookup"><span data-stu-id="67bf0-382">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="67bf0-383">이는 여러 가지 방법으로 혼동될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-383">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="67bf0-384">`BufferSize`추상화가 아닙니다. 정수의 또 다른 이름일 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-384">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="67bf0-385">공용 `BufferSize` API에 노출되면 단순한 `int`의미 이상으로 쉽게 잘못 해석될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-385">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="67bf0-386">일반적으로 도메인 유형에는 여러 특성이 있으며 와 같은 `int`기본 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-386">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="67bf0-387">이 약어는 이러한 가정을 위반합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-387">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="67bf0-388">(PascalCase)의 `BufferSize` 대/소문자는 이 형식에 더 많은 데이터가 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-388">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="67bf0-389">이 별칭은 함수에 명명된 인수를 제공하는 것과 비교하여 선명도를 높이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-389">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="67bf0-390">약어는 컴파일된 IL에서 나타나지 않습니다. 정수일 뿐이며 이 별칭은 컴파일 타임 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-390">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="67bf0-391">요약하면 유형 약어의 함정은 축약하는 형식에 대한 추상화가 **아니라는** 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-391">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="67bf0-392">이전 예제에서는 `BufferSize` 추가 데이터가 `int` 없으며 `int` 이미 있는 것 외에 형식 시스템의 이점도 없는 표지 아래에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-392">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="67bf0-393">도메인을 나타내는 형식 약어를 사용하는 다른 방법은 단일 대/소문자 구분 공용 구조체를 사용하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-393">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="67bf0-394">이전 샘플은 다음과 같이 모델링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-394">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="67bf0-395">기본 값과 측면에서 작동하는 코드를 `BufferSize` 작성하는 경우 임의의 정수에서 전달하는 대신 하나를 생성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-395">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="67bf0-396">이렇게 하면 호출자는 함수를 호출하기 전에 `send` 값을 래핑하는 `BufferSize` 형식을 생성해야 하기 때문에 임의의 정수를 함수에 실수로 전달할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="67bf0-396">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
