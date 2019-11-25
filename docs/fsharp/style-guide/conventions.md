---
title: F# 코딩 규칙
description: 코드를 작성할 F# 때 일반적인 지침과 관용구에 대해 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: 60eff6392d71caa54eeb438f2f6ba9db910f1bc1
ms.sourcegitcommit: f348c84443380a1959294cdf12babcb804cfa987
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/12/2019
ms.locfileid: "73978221"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="b6e2a-103">F# 코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="b6e2a-103">F# coding conventions</span></span>

<span data-ttu-id="b6e2a-104">다음 규칙은 많은 F# 코드 베이스를 사용 하 여 작업 하는 환경에서 공식화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="b6e2a-105">[좋은 F# 코드의 5 가지 원칙은](index.md#five-principles-of-good-f-code) 각 권장 사항의 기초가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="b6e2a-106">이러한 요소는 [ F# 구성 요소 디자인 지침](component-design-guidelines.md)과 관련이 있지만 라이브러리와 같은 구성 F# 요소 뿐 아니라 모든 코드에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="b6e2a-107">코드 구성</span><span class="sxs-lookup"><span data-stu-id="b6e2a-107">Organizing code</span></span>

<span data-ttu-id="b6e2a-108">F#는 코드를 구성 하는 두 가지 기본 방법인 모듈 및 네임 스페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="b6e2a-109">이와 유사 하지만 다음과 같은 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="b6e2a-110">네임 스페이스는 .NET 네임 스페이스로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="b6e2a-111">모듈은 정적 클래스로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="b6e2a-112">네임 스페이스는 항상 최상위 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-112">Namespaces are always top level.</span></span> <span data-ttu-id="b6e2a-113">모듈은 최상위 수준 이며 다른 모듈 내에 중첩 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="b6e2a-114">네임 스페이스는 여러 파일에 걸쳐 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="b6e2a-115">모듈은 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-115">Modules cannot.</span></span>
* <span data-ttu-id="b6e2a-116">모듈은 `[<RequireQualifiedAccess>]` 및 `[<AutoOpen>]`으로 데코레이팅 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="b6e2a-117">다음 지침은이를 사용 하 여 코드를 구성 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="b6e2a-118">최상위 수준에서 네임 스페이스 선호</span><span class="sxs-lookup"><span data-stu-id="b6e2a-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="b6e2a-119">공개적으로 사용할 수 있는 코드의 경우 네임 스페이스는 최상위 수준의 모듈에 우선적으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="b6e2a-120">.NET 네임 스페이스로 컴파일되기 때문에 문제가 없는에서 C# 사용 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="b6e2a-121">에서 F#유일 하 게 호출 하는 경우에만 최상위 모듈을 사용할 수 있습니다. C# 그러나 소비자의 경우에는`MyCode`모듈을 사용 하 여`MyClass`를 한정 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="b6e2a-122">신중 하 게 적용 `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="b6e2a-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="b6e2a-123">`[<AutoOpen>]` 구문은 호출자가 사용할 수 있는 항목의 범위를 pollute 수 있으며, 무언가가 제공 되는 위치에 대 한 답은 "매직"입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="b6e2a-124">일반적으로 좋은 방법은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-124">This is generally not a good thing.</span></span> <span data-ttu-id="b6e2a-125">이 규칙에 대 한 예외는 F# 핵심 라이브러리 자체 이지만이 사실은 약간의 논쟁 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="b6e2a-126">그러나 공용 api와 별도로 구성 하려는 공용 API에 대 한 도우미 기능이 있는 경우 편리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="b6e2a-127">이렇게 하면 호출할 때마다 도우미를 완전히 정규화 하지 않고도 함수의 공용 API에서 구현 세부 정보를 완전히 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="b6e2a-128">또한 네임 스페이스 수준에서 확장 메서드와 식 작성기를 표시 하는 것은 `[<AutoOpen>]`로 깔끔하게 표현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="b6e2a-129">이름이 충돌 하거나 가독성에 도움이 될 때마다 `[<RequireQualifiedAccess>]`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="b6e2a-130">모듈에 `[<RequireQualifiedAccess>]` 특성을 추가 하면 모듈이 열리지 않을 수 있으며 모듈의 요소에 대 한 참조에 명시적으로 정규화 된 액세스가 필요 함을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="b6e2a-131">예를 들어 `Microsoft.FSharp.Collections.List` 모듈에는이 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="b6e2a-132">이는 모듈의 함수 및 값에 다른 모듈의 이름과 충돌할 가능성이 있는 이름이 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="b6e2a-133">정규화 된 액세스를 요구 하면 라이브러리의 장기 유지 관리 및 진화 크게 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="b6e2a-134">`open` 문 정렬 토폴로지 방식으로</span><span class="sxs-lookup"><span data-stu-id="b6e2a-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="b6e2a-135">에서 F#선언 순서는 `open`문을 포함 하 여 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="b6e2a-136">이는와 C#는 달리`using`및`using static`의 효과는 파일에서 해당 문의 순서와는 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="b6e2a-137">에서 F#범위로 열린 요소는 이미 존재 하는 다른 요소를 숨길 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="b6e2a-138">즉, `open` 문을 다시 정렬 하 여 코드의 의미를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="b6e2a-139">따라서 사전순으로와 같은 모든 `open` 문을 임의로 정렬 하는 것은 일반적으로 권장 되지 않습니다. 목록 다른 동작을 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="b6e2a-140">대신 [토폴로지 방식으로](https://en.wikipedia.org/wiki/Topological_sorting)를 정렬 하는 것이 좋습니다. 즉, 시스템 _계층이_ 정의 된 순서에 따라 `open` 문을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="b6e2a-141">다른 토폴로지 계층 내에서 영숫자 정렬을 수행 하는 것도 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="b6e2a-142">예를 들어 F# 컴파일러 서비스 공용 API 파일에 대 한 토폴로지 정렬은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="b6e2a-143">줄 바꿈으로 인해 토폴로지 계층이 분리 되며, 각 계층은 나중에 사전순으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="b6e2a-144">이렇게 하면 값을 실수로 숨기는 대신 코드가 완전히 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="b6e2a-145">파생 작업이 있는 값을 포함 하는 클래스 사용</span><span class="sxs-lookup"><span data-stu-id="b6e2a-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="b6e2a-146">값을 초기화 하는 경우에는 데이터베이스 또는 다른 원격 리소스에 대 한 컨텍스트 인스턴스화와 같은 부작용이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="b6e2a-147">모듈에서 이러한 항목을 초기화 하 고 이후 함수에서 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="b6e2a-148">이는 다음과 같은 몇 가지 이유로 인해 종종 잘못 된 개념입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="b6e2a-149">먼저 `dep1` 및 `dep2`를 사용 하 여 응용 프로그램 구성이 코드 베이스에 푸시됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="b6e2a-150">이는 더 큰 코드 베이스에서 유지 관리 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="b6e2a-151">두 번째로, 구성 요소가 여러 스레드를 사용 하는 경우 정적으로 초기화 된 데이터에는 스레드로부터 안전 하지 않은 값을 포함 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="b6e2a-152">`dep3`에서이를 명확 하 게 위반 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="b6e2a-153">마지막으로, 모듈 초기화는 전체 컴파일 단위에 대 한 정적 생성자로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="b6e2a-154">해당 모듈의 let 바인딩 값 초기화에 오류가 발생 하는 경우 응용 프로그램의 전체 수명 동안 캐시 된 `TypeInitializationException`으로 매니페스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="b6e2a-155">이는 진단 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="b6e2a-156">일반적으로 원인을 확인할 수 있는 내부 예외가 있지만, 그렇지 않은 경우 근본 원인을 알려 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="b6e2a-157">대신 간단한 클래스를 사용 하 여 종속성을 유지 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member _.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member _.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="b6e2a-158">이렇게 하면 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-158">This enables the following:</span></span>

1. <span data-ttu-id="b6e2a-159">API 자체 외부에서 모든 종속 상태를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="b6e2a-160">이제 API 외부에서 구성을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="b6e2a-161">종속 값을 초기화 하는 동안 발생 하는 오류는 `TypeInitializationException`로 매니페스트가 될 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="b6e2a-162">이제 API를 더 쉽게 테스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="b6e2a-163">오류 관리</span><span class="sxs-lookup"><span data-stu-id="b6e2a-163">Error management</span></span>

<span data-ttu-id="b6e2a-164">대량 시스템에서 오류를 관리 하는 것은 복잡 하 고 미묘한 시스템을 내결함성이 있는지 확인 하는 실버 글머리 기호가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="b6e2a-165">다음 지침에서는이 까다로운 공간을 탐색 하는 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="b6e2a-166">도메인의 내장 형식에서 오류 사례 및 잘못 된 상태를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="b6e2a-167">[구별 된 공용 구조체](../language-reference/discriminated-unions.md)를 F# 사용 하면 형식 시스템에서 잘못 된 프로그램 상태를 나타내는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="b6e2a-168">예를 들어 다음과 같은 가치를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="b6e2a-169">이 경우 은행 계좌에서 입출금 계좌 money가 실패할 수 있는 알려진 세 가지 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="b6e2a-170">각 오류 사례는 형식으로 표시 되므로 프로그램 전체에서 안전 하 게 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="b6e2a-171">일반적으로 도메인에서 어떤 작업을 **수행할 수 있는지에 대** 한 다양 한 방법을 모델링할 수 있는 경우 오류 처리 코드는 일반 프로그램 흐름 외에도 처리 해야 하는 것으로 처리 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="b6e2a-172">단순히 일반적인 프로그램 흐름의 일부 이며 **예외적인**것으로 간주 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="b6e2a-173">이에는 다음과 같은 두 가지 주요 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="b6e2a-174">시간이 지남에 따라 도메인을 변경 하면 더 쉽게 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="b6e2a-175">오류 사례는 단위 테스트를 용이 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="b6e2a-176">형식을 사용 하 여 오류를 나타낼 수 없는 경우 예외를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="b6e2a-177">모든 오류가 문제 도메인에 표시 되는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="b6e2a-178">이러한 종류의 *오류는 본질적* 으로 예외 이므로에서 F#예외를 발생 시키고 catch 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="b6e2a-179">먼저 [예외 디자인 지침](../../standard/design-guidelines/exceptions.md)을 읽는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="b6e2a-180">이러한 항목은에 F#도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-180">These are also applicable to F#.</span></span>

<span data-ttu-id="b6e2a-181">예외를 발생 시키기 위해 F# 에서 사용할 수 있는 기본 구문은 다음과 같은 기본 설정 순서로 고려 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="b6e2a-182">기능</span><span class="sxs-lookup"><span data-stu-id="b6e2a-182">Function</span></span> | <span data-ttu-id="b6e2a-183">구문</span><span class="sxs-lookup"><span data-stu-id="b6e2a-183">Syntax</span></span> | <span data-ttu-id="b6e2a-184">용도</span><span class="sxs-lookup"><span data-stu-id="b6e2a-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="b6e2a-185">지정 된 인수 이름을 사용 하 여 `System.ArgumentNullException`을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="b6e2a-186">지정 된 인수 이름 및 메시지를 사용 하 여 `System.ArgumentException`을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="b6e2a-187">지정 된 메시지를 사용 하 여 `System.InvalidOperationException`을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="b6e2a-188">예외를 throw 하는 일반적인 용도의 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="b6e2a-189">지정 된 메시지를 사용 하 여 `System.Exception`을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="b6e2a-190">형식 문자열과 해당 입력에 의해 결정 되는 메시지를 사용 하 여 `System.Exception`을 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="b6e2a-191">`nullArg`, `invalidArg` 및 `invalidOp`를 사용 하 여 해당 하는 경우 `ArgumentNullException`, `ArgumentException` 및 `InvalidOperationException`을 throw 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="b6e2a-192">`failwith` 및 `failwithf` 함수는 특정 예외가 아닌 기본 `Exception` 형식을 발생 시키기 때문에 일반적으로 피해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="b6e2a-193">[예외 디자인 지침](../../standard/design-guidelines/exceptions.md)에 따라 가능 하면 더 구체적인 예외를 발생 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="b6e2a-194">예외 처리 구문 사용</span><span class="sxs-lookup"><span data-stu-id="b6e2a-194">Using exception-handling syntax</span></span>

<span data-ttu-id="b6e2a-195">F#에서는`try...with`구문을 통해 예외 패턴을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="b6e2a-196">패턴 일치를 사용 하 여 예외 발생 시 수행할 기능을 조정 하는 것은 코드를 깨끗 하 게 유지 하려는 경우 다소 복잡할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="b6e2a-197">이를 처리 하는 방법 중 하나는 오류 사례를 제외 하 고 예외 자체를 사용 하 여 기능을 그룹화 하는 수단으로 [활성 패턴](../language-reference/active-patterns.md) 을 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="b6e2a-198">예를 들어, 예외를 throw 하는 경우 예외 메타 데이터에 중요 한 정보를 포함 하는 API를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="b6e2a-199">활성 패턴 내에서 캡처된 예외의 본문에 유용한 값을 래핑 해제 하 고이 값을 반환 하면 몇 가지 상황에서 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="b6e2a-200">Monadic 오류 처리를 사용 하 여 예외 바꾸기</span><span class="sxs-lookup"><span data-stu-id="b6e2a-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="b6e2a-201">예외는 함수형 프로그래밍에서 약간의 금기시 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="b6e2a-202">실제로 예외는 순도를 위반 하므로 매우 작동 하지 않는 것을 고려 하는 것이 안전 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="b6e2a-203">그러나이 경우 코드를 실행 해야 하는 현실을 무시 하 고 런타임 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="b6e2a-204">일반적으로 불쾌 예상치를 최소화 하기 위해 대부분의 항목이 순수 또는 합계는 아닌 것으로 가정 하 여 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="b6e2a-205">.NET 런타임 및 언어 간 에코 시스템의 관련성 및 적합성과 관련 하 여 다음과 같은 핵심 장점/측면을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="b6e2a-206">여기에는 문제를 디버깅할 때 매우 유용한 자세한 진단 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="b6e2a-207">런타임 및 기타 .NET 언어에서 잘 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="b6e2a-208">이를 통해 의미 체계의 일부 하위 집합을 임시 기반으로 구현 하 여 예외를 *방지* 하는 코드와 비교할 때 중요 한 상용구를 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="b6e2a-209">이 세 번째 지점은 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-209">This third point is critical.</span></span> <span data-ttu-id="b6e2a-210">복잡 한 복잡 한 작업의 경우 예외를 사용 하지 못하면 다음과 같은 구조를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="b6e2a-211">"Stringly 형식" 오류에 대 한 패턴 일치와 같은 손상 된 코드를 쉽게 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="b6e2a-212">또한 "더 좋은" 형식을 반환 하는 "simple" 함수를 원하는 경우 예외를 무시 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="b6e2a-213">불행 하 게도 파일 시스템에서 발생할 수 있는 많은 작업을 기반으로 많은 예외를 throw 할 수 있으며 `tryReadAllText`,이 코드는 실제로 사용자 환경에서 발생할 수 있는 문제에 대 한 정보를 모두 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="b6e2a-214">이 코드를 결과 형식으로 바꾸면 "stringly" 오류 메시지 구문 분석으로 돌아갑니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="b6e2a-215">예외 개체 자체를 `Error` 생성자에 배치 하면 함수 대신 호출 사이트에서 예외 형식을 올바르게 처리 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="b6e2a-216">이렇게 하면 확인 된 예외가 생성 되며이는 API의 호출자로 처리 하지 어렵습니다 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="b6e2a-217">위의 예제에 대 한 좋은 대안은 *특정* 예외를 catch 하 고 해당 예외의 컨텍스트에서 의미 있는 값을 반환 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="b6e2a-218">`tryReadAllText` 함수를 다음과 같이 수정 하는 경우 `None`는 보다 의미 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="b6e2a-219">이 함수는 모두 catch로 작동 하는 대신, 파일을 찾을 수 없는 경우를 적절 하 게 처리 하 고 해당 의미를 반환에 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="b6e2a-220">이 반환 값은 컨텍스트 정보를 삭제 하거나 호출자가 코드의 해당 지점에서 관련이 없을 수 있는 사례를 처리 하도록 강제 하는 동시에 해당 오류 사례에 매핑될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="b6e2a-221">`Result<'Success, 'Error>`와 같은 형식은 중첩 되지 않은 기본 작업에 적합 하며 F# , 선택적 형식은 어떤 항목이 *어떤 항목* 을 반환 하거나 *아무 것도*반환 하지 않는 경우를 나타내는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="b6e2a-222">그러나 예외를 대체 하지는 않지만 예외를 대체 하려는 시도에서 사용 하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="b6e2a-223">대신, 예외 및 오류 관리 정책의 특정 측면을 대상 방식으로 처리 하기 위해 신중 하 게 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="b6e2a-224">부분 응용 프로그램 및 지점 없는 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b6e2a-224">Partial application and point-free programming</span></span>

<span data-ttu-id="b6e2a-225">F#에서는 부분 응용 프로그램을 지원 하므로 특정 시점 스타일로 프로그래밍 하는 다양 한 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="b6e2a-226">이는 모듈 내에서 코드를 다시 사용 하거나 항목을 구현 하는 데 도움이 될 수 있지만 일반적으로 공개적으로 노출 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="b6e2a-227">일반적으로 지점 없는 프로그래밍은 그 자체로는 적합 하지 않으며 스타일에 사용 되지 않은 사용자에 게 상당한 인식 장벽을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="b6e2a-228">공용 Api에서 부분 응용 프로그램 및 currying 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="b6e2a-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="b6e2a-229">거의 예외를 제외 하 고 공용 Api에서 부분 응용 프로그램을 사용 하는 것은 소비자에 게 혼란 스 러 울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="b6e2a-230">일반적으로 코드의 F# `let`바인딩된 값은 **함수 값**이 아닌 **값**입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="b6e2a-231">값과 함수 값을 함께 사용 하면 특히 함수를 작성 하는 `>>`와 같은 연산자와 함께 사용 하는 경우 exchange에서 적은 수의 코드 줄을 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="b6e2a-232">지점 없는 프로그래밍에 대 한 도구 의미 고려</span><span class="sxs-lookup"><span data-stu-id="b6e2a-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="b6e2a-233">커리 함수는 인수에 레이블을 나타내지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="b6e2a-234">이는 도구에 영향을 미칩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-234">This has tooling implications.</span></span> <span data-ttu-id="b6e2a-235">다음 두 가지 함수를 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="b6e2a-236">둘 다 유효한 함수 이지만 `funcWithApplication`은 커리 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="b6e2a-237">편집기에서 해당 유형을 가리키면 다음과 같이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="b6e2a-238">호출 사이트에서 Visual Studio와 같은 도구 설명에서는 `string` 및 `int` 입력 형식이 실제로 나타내는 것과 같은 의미 있는 정보를 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="b6e2a-239">공개적으로 사용할 수 있는 `funcWithApplication`와 같은 지점 없는 코드가 발생 하는 경우 도구에서 인수에 대해 의미 있는 이름을 선택할 수 있도록 전체 η 확장을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="b6e2a-240">또한 디버깅 지점-무료 코드는 불가능 한 경우 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="b6e2a-241">디버깅 도구는 이름에 바인딩된 값 (예: `let` 바인딩)을 사용 하므로 중간 값을 실행을 통해 중간 값을 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="b6e2a-242">코드에 검사할 값이 없는 경우에는 디버그할 항목이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="b6e2a-243">나중에 디버깅 도구는 이전에 실행 된 경로를 기반으로 이러한 값을 합성 하기 위해 발전 했을 수 있지만 *잠재적* 디버깅 기능에 대 한 사용자의 수를 추가 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="b6e2a-244">부분 응용 프로그램을 내부 상용구를 줄이기 위한 기술로 고려</span><span class="sxs-lookup"><span data-stu-id="b6e2a-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="b6e2a-245">이전 지점과는 달리 부분 응용 프로그램은 응용 프로그램 내에서 상용구를 줄이는 데 사용할 수 있는 훌륭한 도구 또는 API의 심층적 내부 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="b6e2a-246">이러한 Api는 자주 사용 하는 것이 어려운 Api의 구현을 단위 테스트 하는 데 유용 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="b6e2a-247">예를 들어 다음 코드는 이러한 프레임 워크에 대 한 외부 종속성을 사용 하지 않고 관련 맞춤식 API를 배워야 하는 대부분의 모의 프레임 워크에서 제공 하는 작업을 수행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="b6e2a-248">예를 들어 다음 솔루션 토폴로지를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="b6e2a-249">`ImplementationLogic.fsproj` 다음과 같은 코드를 노출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member _.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="b6e2a-250">`ImplementationLogic.Tests.fsproj`의 단위 테스트 `Transactions.doTransaction`은 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fsproj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="b6e2a-251">모의 컨텍스트 개체를 사용 하 여 `doTransaction`을 부분적으로 적용 하면 매번 모의 컨텍스트를 생성할 필요 없이 모든 단위 테스트에서 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

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

<span data-ttu-id="b6e2a-252">이 기법은 전체 코드 베이스에 전체적으로 적용 되는 것은 아니지만, 복잡 한 내부 및 이러한 내부 단위 테스트를 위해 상용구를 줄이는 것이 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="b6e2a-253">액세스 제어</span><span class="sxs-lookup"><span data-stu-id="b6e2a-253">Access control</span></span>

<span data-ttu-id="b6e2a-254">F#에는 .NET 런타임에서 사용할 수 있는 것으로 상속 되는 [Access control](../language-reference/access-control.md)에 대 한 여러 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="b6e2a-255">이러한 형식은 형식에만 사용할 수 있으며 함수에도 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="b6e2a-256">공개적으로 사용할 수 있어야 할 때까지`public` 되지 않는 형식 및 멤버를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="b6e2a-257">이를 통해 소비자가 두 가지를 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="b6e2a-258">모든 도우미 기능 `private`유지 하기 위해 노력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="b6e2a-259">도우미 함수의 전용 모듈에 `[<AutoOpen>]`를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="b6e2a-260">형식 유추 및 제네릭</span><span class="sxs-lookup"><span data-stu-id="b6e2a-260">Type inference and generics</span></span>

<span data-ttu-id="b6e2a-261">형식 유추를 통해 여러 상용구를 입력 하는 것을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="b6e2a-262">F# 컴파일러의 자동 일반화를 통해 사용자의 추가 노력 없이 보다 일반적인 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="b6e2a-263">그러나 이러한 기능은 보편적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="b6e2a-264">공용 Api에서 명시적 형식의 인수 이름을 지정 하 고이에 대 한 형식 유추를 사용 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="b6e2a-265">그 이유는 컴파일러가 아니라 API의 모양을 **제어 하는 것입니다.**</span><span class="sxs-lookup"><span data-stu-id="b6e2a-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="b6e2a-266">컴파일러는 형식을 유추 하는 데 적절 한 작업을 수행할 수 있지만, 사용 하는 내부에 변경 된 형식이 있는 경우 API의 모양을 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="b6e2a-267">이는 원하는 대로 지정할 수 있지만 다운스트림 소비자가 처리 해야 하는 API 변경이 거의 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="b6e2a-268">대신 공용 API의 셰이프를 명시적으로 제어 하는 경우 이러한 주요 변경 사항을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="b6e2a-269">DDD 용어로는이를 손상 방지 계층으로 간주할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="b6e2a-270">제네릭 인수에 의미 있는 이름을 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="b6e2a-271">특정 도메인에 한정 되지 않는 진정한 제네릭 코드를 작성 하지 않는 한 의미 있는 이름을 사용 하면 다른 프로그래머가 작업 중인 도메인을 이해 하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="b6e2a-272">예를 들어 문서 데이터베이스와 상호 작용 하는 컨텍스트에서 `'Document` 라는 형식 매개 변수를 사용 하면 작업 중인 함수 또는 멤버가 일반 문서 형식을 허용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="b6e2a-273">제네릭 형식 매개 변수의 이름을 지정 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="b6e2a-274">이것은 .NET에서 작업을 수행 하는 일반적인 방법 이므로 snake_case 또는 camelCase이 아닌 다른 사용자를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="b6e2a-275">마지막으로, 자동 일반화는 항상 또는 규모가 많은 코드 베이스를 처음 접하는 F# 사용자에 게는 유용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="b6e2a-276">일반적으로 사용 되는 구성 요소를 사용 하는 경우 인지 오버 헤드가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="b6e2a-277">또한 자동으로 일반화 된 함수를 다른 입력 형식으로 사용 하지 않는 경우 (예를 들어 사용 하려는 경우에만) 해당 시점에서 제네릭이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="b6e2a-278">작성 하는 코드의 경우에는 항상 제네릭을 활용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="b6e2a-279">성능</span><span class="sxs-lookup"><span data-stu-id="b6e2a-279">Performance</span></span>

<span data-ttu-id="b6e2a-280">F#기본적으로 값은 변경할 수 없습니다 .이를 통해 특정 버그 클래스 (특히 동시성 및 병렬 처리와 관련 된 클래스)를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="b6e2a-281">그러나 특정 한 경우에는 실행 시간이 나 메모리 할당의 최적 또는 적절 한 효율성을 얻기 위해 상태의 내부 변형을 사용 하 여 작업 범위를 가장 잘 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="b6e2a-282">이는`mutable`키워드를 사용 하 여 옵트인 F# 할 때 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="b6e2a-283">그러나의 F# `mutable` 사용 하는 것은 함수 순도와는 다를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="b6e2a-284">이는 순도에서 [참조 투명도](https://en.wikipedia.org/wiki/Referential_transparency)로 기대치를 조정 하는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="b6e2a-285">참조 투명도-비 순도-함수를 작성할 F# 때의 끝 목표입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="b6e2a-286">이렇게 하면 성능에 중요 한 코드를 위해 변형 기반 구현에 대해 함수형 인터페이스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="b6e2a-287">변경할 수 없는 인터페이스에서 변경 가능한 코드 줄 바꿈</span><span class="sxs-lookup"><span data-stu-id="b6e2a-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="b6e2a-288">참조 투명성을 목표로 하는 경우 성능에 중요 한 함수의 변경 가능한 underbelly을 노출 하지 않는 코드를 작성 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="b6e2a-289">예를 들어 다음 코드는 F# 핵심 라이브러리에서 `Array.contains` 함수를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="b6e2a-290">이 함수를 여러 번 호출 하면 기본 배열이 변경 되지 않으며,이 함수를 사용 하 여 변경 가능한 상태를 유지 관리 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="b6e2a-291">거의 모든 코드 줄에서 변형을 사용 하는 경우에도 투명 하 게 엔터티와.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="b6e2a-292">변경 가능한 데이터를 클래스에 캡슐화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="b6e2a-293">이전 예제에서는 단일 함수를 사용 하 여 변경 가능한 데이터를 사용 하는 작업을 캡슐화 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="b6e2a-294">이는 더 복잡 한 데이터 집합에는 항상 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="b6e2a-295">다음 함수 집합을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-295">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="b6e2a-296">이 코드는 성능이 우수 하지만 호출자가 유지 관리 해야 하는 변형 기반 데이터 구조를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="b6e2a-297">변경할 수 있는 기본 멤버가 없는 클래스 내부에이를 래핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

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

<span data-ttu-id="b6e2a-298">`Closure1Table`는 기본 변형 기반 데이터 구조를 캡슐화 하 여 호출자가 내부 데이터 구조를 유지 하지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="b6e2a-299">클래스는 세부 정보를 호출자에 게 노출 하지 않고 변형 기반 데이터 및 루틴을 캡슐화 하는 강력한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="b6e2a-300">셀을 참조 하는 `let mutable` 선호</span><span class="sxs-lookup"><span data-stu-id="b6e2a-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="b6e2a-301">참조 셀은 값 자체가 아닌 값에 대 한 참조를 표시 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="b6e2a-302">성능이 중요 한 코드에는 사용 될 수 있지만 일반적으로 권장 되지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="b6e2a-303">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="b6e2a-304">이제 참조 셀을 사용 하 여 기본 데이터를 역참조 하 고 다시 참조 해야 하는 모든 후속 코드를 "pollutes" 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="b6e2a-305">대신 `let mutable`을 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="b6e2a-306">람다 식의 중간에 있는 단일 변형 지점 외에도 `acc`에 해당 하는 다른 모든 코드는 일반적인 `let`바인딩된 변경 불가능 값의 사용량과 다른 방식으로이 작업을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="b6e2a-307">이렇게 하면 시간이 지남에 따라 더 쉽게 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="b6e2a-308">개체 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="b6e2a-308">Object programming</span></span>

<span data-ttu-id="b6e2a-309">F#개체 및 개체 지향 (OO) 개념을 완벽 하 게 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="b6e2a-310">대부분의 OO 개념은 강력 하 고 유용 하지만 모두 사용 하기에 적합 한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="b6e2a-311">다음 목록에서는 상위 수준에서의 OO 기능 범주에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="b6e2a-312">**다음과 같은 다양 한 상황에서 이러한 기능을 사용 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="b6e2a-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="b6e2a-313">점 표기법 (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="b6e2a-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="b6e2a-314">인스턴스 멤버</span><span class="sxs-lookup"><span data-stu-id="b6e2a-314">Instance members</span></span>
* <span data-ttu-id="b6e2a-315">암시적 생성자</span><span class="sxs-lookup"><span data-stu-id="b6e2a-315">Implicit constructors</span></span>
* <span data-ttu-id="b6e2a-316">정적 멤버</span><span class="sxs-lookup"><span data-stu-id="b6e2a-316">Static members</span></span>
* <span data-ttu-id="b6e2a-317">인덱서 표기법 (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="b6e2a-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="b6e2a-318">명명 된 인수 및 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="b6e2a-318">Named and Optional arguments</span></span>
* <span data-ttu-id="b6e2a-319">인터페이스 및 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="b6e2a-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="b6e2a-320">**이러한 기능에 대해 먼저 도달 하지 말고 문제를 해결 하는 데 편리한 경우에는 신중 하 게 적용 해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6e2a-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="b6e2a-321">메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="b6e2a-321">Method overloading</span></span>
* <span data-ttu-id="b6e2a-322">캡슐화 된 변경 가능한 데이터</span><span class="sxs-lookup"><span data-stu-id="b6e2a-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="b6e2a-323">형식에 대 한 연산자</span><span class="sxs-lookup"><span data-stu-id="b6e2a-323">Operators on types</span></span>
* <span data-ttu-id="b6e2a-324">자동 속성</span><span class="sxs-lookup"><span data-stu-id="b6e2a-324">Auto properties</span></span>
* <span data-ttu-id="b6e2a-325">`IDisposable` 및 `IEnumerable` 구현</span><span class="sxs-lookup"><span data-stu-id="b6e2a-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="b6e2a-326">형식 확장</span><span class="sxs-lookup"><span data-stu-id="b6e2a-326">Type extensions</span></span>
* <span data-ttu-id="b6e2a-327">이벤트</span><span class="sxs-lookup"><span data-stu-id="b6e2a-327">Events</span></span>
* <span data-ttu-id="b6e2a-328">Structs</span><span class="sxs-lookup"><span data-stu-id="b6e2a-328">Structs</span></span>
* <span data-ttu-id="b6e2a-329">대리자</span><span class="sxs-lookup"><span data-stu-id="b6e2a-329">Delegates</span></span>
* <span data-ttu-id="b6e2a-330">열거형</span><span class="sxs-lookup"><span data-stu-id="b6e2a-330">Enums</span></span>

<span data-ttu-id="b6e2a-331">**일반적으로 이러한 기능을 사용 해야 하는 경우를 방지 합니다.**</span><span class="sxs-lookup"><span data-stu-id="b6e2a-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="b6e2a-332">상속 기반 형식 계층 구조 및 구현 상속</span><span class="sxs-lookup"><span data-stu-id="b6e2a-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="b6e2a-333">Null 및 `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="b6e2a-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="b6e2a-334">상속 보다 컴퍼지션 선호</span><span class="sxs-lookup"><span data-stu-id="b6e2a-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="b6e2a-335">[상속을 통한 컴퍼지션](https://en.wikipedia.org/wiki/Composition_over_inheritance) 은 좋은 F# 코드가 준수 하는 긴 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="b6e2a-336">기본 원칙은 기본 클래스를 노출 하지 않고 해당 기본 클래스에서 호출자가 강제로 상속 하 여 기능을 가져와야 한다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="b6e2a-337">클래스가 필요 하지 않은 경우 개체 식을 사용 하 여 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="b6e2a-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="b6e2a-338">[개체 식을](../language-reference/object-expressions.md) 사용 하면 인터페이스를 즉석에서 구현 하 고 구현 된 인터페이스를 클래스 내부에서 수행할 필요 없이 값에 바인딩할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="b6e2a-339">특히 인터페이스를 구현 하기만 하면 전체 _클래스가 필요 하지_ 않은 경우 편리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="b6e2a-340">예를 들어,에 대 한 `open` 문이 없는 기호를 추가한 경우 코드 수정 [작업을 제공 하기 위해](http://ionide.io/) 다음 코드를 사용할 때 코드를 수정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="b6e2a-341">Visual Studio Code API와 상호 작용할 때 클래스가 필요 하지 않기 때문에 개체 식이이에 적합 한 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="b6e2a-342">또한 테스트 루틴이 포함 된 인터페이스를 임시 방식으로 스텁 하려는 경우 단위 테스트에도 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="consider-type-abbreviations-to-shorten-signatures"></a><span data-ttu-id="b6e2a-343">서명을 줄이려면 형식 약어를 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-343">Consider Type Abbreviations to shorten signatures</span></span>

<span data-ttu-id="b6e2a-344">[형식 약어](../language-reference/type-abbreviations.md) 는 함수 시그니처 또는 보다 복잡 한 형식과 같은 다른 형식에 레이블을 할당 하는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="b6e2a-345">예를 들어 다음 별칭은 심층 학습 라이브러리인 [CNTK](https://docs.microsoft.com/cognitive-toolkit/)를 사용 하 여 계산을 정의 하는 데 필요한 항목에 레이블을 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://docs.microsoft.com/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="b6e2a-346">`Computation` 이름은 별칭을 추가할 시그니처와 일치 하는 함수를 나타내는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="b6e2a-347">이와 같은 형식 약어를 사용 하면 편리 하며 더 간결한 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="b6e2a-348">도메인을 나타내기 위해 형식 약어를 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="b6e2a-349">형식 약어는 함수 시그니처에 이름을 제공 하는 데 편리 하지만 다른 형식을 abbreviating 때 혼동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="b6e2a-350">다음 약어를 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="b6e2a-351">이는 여러 가지 방법으로 혼동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="b6e2a-352">`BufferSize`는 추상이 아닙니다. 단지 정수에 대 한 다른 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="b6e2a-353">`BufferSize` 공용 API에 노출 되는 경우 `int`만을 의미 하는 것으로 쉽게 잘못 해석 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="b6e2a-354">일반적으로 도메인 형식은 여러 특성을 가지 며 `int`와 같은 기본 형식이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="b6e2a-355">이 약어는 이러한 가정을 위반 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="b6e2a-356">`BufferSize` (고 대/소문자)의 대/소문자 구분은이 형식에 더 많은 데이터가 포함 되어 있음을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="b6e2a-357">이 별칭은 함수에 명명 된 인수를 제공 하는 것과 비교 하 여 향상 된 명확성을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="b6e2a-358">약어는 컴파일된 IL에서 매니페스트 되지 않습니다. 단지 정수 이며이 별칭은 컴파일 타임 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) = ...
```

<span data-ttu-id="b6e2a-359">요약 하자면, 형식 약어의 단점은 abbreviating 된 형식에 대 한 추상화가 **아니라** 는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="b6e2a-360">앞의 예제에서 `BufferSize`는 추가 데이터를 포함 하지 않는 커버 아래에 있는 `int` 뿐만 아니라 이미 있는 `int` 외에도 유형 시스템의 이점도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>

<span data-ttu-id="b6e2a-361">형식 약어를 사용 하 여 도메인을 나타내는 다른 방법은 단일 대/소문자 구분 공용 구조체를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-361">An alternative approach to using type abbreviations to represent a domain is to use single-case discriminated unions.</span></span> <span data-ttu-id="b6e2a-362">이전 샘플은 다음과 같이 모델링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-362">The previous sample can be modeled as follows:</span></span>

```fsharp
type BufferSize = BufferSize of int
```

<span data-ttu-id="b6e2a-363">`BufferSize`와 해당 내부 값을 기준으로 작동 하는 코드를 작성 하는 경우 임의의 정수를 전달 하는 대신 하나를 생성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-363">If you write code that operates in terms of `BufferSize` and its underlying value, you need to construct one rather than pass in any arbitrary integer:</span></span>

```fsharp
module Networking =
    ...
    let send data (BufferSize size) =
    ...
```

<span data-ttu-id="b6e2a-364">이렇게 하면 호출자가 함수를 호출 하기 전에 값을 래핑하는 `BufferSize` 형식을 생성 해야 하기 때문에 임의의 정수를 `send` 함수에 잘못 전달할 가능성이 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="b6e2a-364">This reduces the likelihood of mistakenly passing an arbitrary integer into the `send` function, because the caller must construct a `BufferSize` type to wrap a value before calling the function.</span></span>
