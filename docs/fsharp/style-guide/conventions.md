---
title: F#코딩 규칙
description: 작성 하는 경우 일반 지침 및 코드에 알아봅니다 F# 코드입니다.
ms.date: 05/14/2018
ms.openlocfilehash: 1ef016184180eb8d233295e8985903e07693ad26
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59186747"
---
# <a name="f-coding-conventions"></a><span data-ttu-id="2aea1-103">F#코딩 규칙</span><span class="sxs-lookup"><span data-stu-id="2aea1-103">F# coding conventions</span></span>

<span data-ttu-id="2aea1-104">다음 규칙에 작업 환경에서 공식화 됩니다 F# 코드 베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-104">The following conventions are formulated from experience working with large F# codebases.</span></span> <span data-ttu-id="2aea1-105">합니다 [good의 다섯 가지 원칙 F# 코드](index.md#five-principles-of-good-f-code) 각 권장 사항의 기반이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-105">The [Five principles of good F# code](index.md#five-principles-of-good-f-code) are the foundation of each recommendation.</span></span> <span data-ttu-id="2aea1-106">관련이 합니다 [ F# 구성 요소 디자인 지침](component-design-guidelines.md), 이지만에 적용할 수 있습니다 F# 코드 라이브러리와 같은 뿐 아니라 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-106">They are related to the [F# component design guidelines](component-design-guidelines.md), but are applicable for any F# code, not just components such as libraries.</span></span>

## <a name="organizing-code"></a><span data-ttu-id="2aea1-107">코드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-107">Organizing code</span></span>

<span data-ttu-id="2aea1-108">F#코드를 구성 하는 두 가지 기능: 모듈 및 네임 스페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-108">F# features two primary ways to organize code: modules and namespaces.</span></span> <span data-ttu-id="2aea1-109">이러한 유사 하지만 다음과 같은 차이가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-109">These are similar, but do have the following differences:</span></span>

* <span data-ttu-id="2aea1-110">네임 스페이스는.NET 네임 스페이스도 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-110">Namespaces are compiled as .NET namespaces.</span></span> <span data-ttu-id="2aea1-111">모듈은 정적 클래스로 컴파일됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-111">Modules are compiled as static classes.</span></span>
* <span data-ttu-id="2aea1-112">네임 스페이스는 항상 최상위 수준입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-112">Namespaces are always top level.</span></span> <span data-ttu-id="2aea1-113">최상위 및 다른 모듈 내에 중첩 모듈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-113">Modules can be top-level and nested within other modules.</span></span>
* <span data-ttu-id="2aea1-114">네임 스페이스는 여러 파일을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-114">Namespaces can span multiple files.</span></span> <span data-ttu-id="2aea1-115">모듈 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-115">Modules cannot.</span></span>
* <span data-ttu-id="2aea1-116">모듈을 데코 레이트 할 수 있습니다 `[<RequireQualifiedAccess>]` 고 `[<AutoOpen>]`입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-116">Modules can be decorated with `[<RequireQualifiedAccess>]` and `[<AutoOpen>]`.</span></span>

<span data-ttu-id="2aea1-117">다음 지침은 세미콜론을 사용 하 여 코드를 구성 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-117">The following guidelines will help you use these to organize your code.</span></span>

### <a name="prefer-namespaces-at-the-top-level"></a><span data-ttu-id="2aea1-118">최상위 수준에서 네임 스페이스를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-118">Prefer namespaces at the top level</span></span>

<span data-ttu-id="2aea1-119">공개적으로 사용할 수 있는 모든 코드에 대 한 네임 스페이스는 최상위 모듈에 기본 설정.</span><span class="sxs-lookup"><span data-stu-id="2aea1-119">For any publicly consumable code, namespaces are preferential to modules at the top level.</span></span> <span data-ttu-id="2aea1-120">.NET 네임 스페이스를 컴파일되지 때문에 문제 없이 C#에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-120">Because they are compiled as .NET namespaces, they are consumable from C# with no issue.</span></span>

```fsharp
// Good!
namespace MyCode

type MyClass() =
    ...
```

<span data-ttu-id="2aea1-121">최상위 모듈을 사용 하 여 다른 에서만 호출 될 때 나타날 수 없습니다 F#, 하지만 C# 소비자를 한정할 필요에서 달라진 것을 호출자에 게 수 `MyClass` 사용 하 여는 `MyCode` 모듈.</span><span class="sxs-lookup"><span data-stu-id="2aea1-121">Using a top-level module may not appear different when called only from F#, but for C# consumers, callers may be surprised by having to qualify `MyClass` with the `MyCode` module.</span></span>

```fsharp
// Bad!
module MyCode

type MyClass() =
    ...
```

### <a name="carefully-apply-autoopen"></a><span data-ttu-id="2aea1-122">신중 하 게 적용 `[<AutoOpen>]`</span><span class="sxs-lookup"><span data-stu-id="2aea1-122">Carefully apply `[<AutoOpen>]`</span></span>

<span data-ttu-id="2aea1-123">`[<AutoOpen>]` 구문을 호출자에 게 사용할 수 있는 항목의 범위를 손상 시 키 지 수 및 항목에서 원본 위치에 대 한 답은 "매직"입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-123">The `[<AutoOpen>]` construct can pollute the scope of what is available to callers, and the answer to where something comes from is "magic".</span></span> <span data-ttu-id="2aea1-124">이 일반적으로 유용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-124">This is generally not a good thing.</span></span> <span data-ttu-id="2aea1-125">이 규칙의 예외는 F# (하지만 이것이 약간 논쟁의 여지가) 자체 핵심 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-125">An exception to this rule is the F# Core Library itself (though this fact is also a bit controversial).</span></span>

<span data-ttu-id="2aea1-126">그러나 것 편의 위해 해당 공용 API에서 개별적으로 구성 하려는 공용 API에 대 한 도우미 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-126">However, it is a convenience if you have helper functionality for a public API that you wish to organize separately from that public API.</span></span>

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

<span data-ttu-id="2aea1-127">이렇게 하면 완벽 하 게 호출 될 때마다 도우미를 한정할 필요 없이 공용 API 함수에서 명확 하 게 별도 구현 세부 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-127">This lets you cleanly separate implementation details from the public API of a function without having to fully qualify a helper each time you call it.</span></span>

<span data-ttu-id="2aea1-128">또한 확장 메서드 및 식 작성기는 네임 스페이스 수준에서 노출 깔끔하게으로 표현할 수 `[<AutoOpen>]`입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-128">Additionally, exposing extension methods and expression builders at the namespace level can be neatly expressed with `[<AutoOpen>]`.</span></span>

### <a name="use-requirequalifiedaccess-whenever-names-could-conflict-or-you-feel-it-helps-with-readability"></a><span data-ttu-id="2aea1-129">사용 하 여 `[<RequireQualifiedAccess>]` 이름이 충돌할 수 있습니다 또는 수 있다고 생각 가독성을 높이 데 도움이 될 때마다</span><span class="sxs-lookup"><span data-stu-id="2aea1-129">Use `[<RequireQualifiedAccess>]` whenever names could conflict or you feel it helps with readability</span></span>

<span data-ttu-id="2aea1-130">추가 된 `[<RequireQualifiedAccess>]` 모듈을 열 수 있습니다 하 액세스를 정규화 하는 모듈의 요소에 대 한 참조가 필요 명시적 특성을 모듈을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-130">Adding the `[<RequireQualifiedAccess>]` attribute to a module indicates that the module may not be opened and that references to the elements of the module require explicit qualified access.</span></span> <span data-ttu-id="2aea1-131">예를 들어를 `Microsoft.FSharp.Collections.List` 모듈에이 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-131">For example, the `Microsoft.FSharp.Collections.List` module has this attribute.</span></span>

<span data-ttu-id="2aea1-132">이 함수 및 모듈의 값 이름이 다른 모듈에서 이름이 충돌할 가능성이 있는 경우에 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-132">This is useful when functions and values in the module have names that are likely to conflict with names in other modules.</span></span> <span data-ttu-id="2aea1-133">정규화 된 액세스가 필요한 장기적 유지 관리성 및 라이브러리의 진화를 크게 증가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-133">Requiring qualified access can greatly increase the long-term maintainability and evolvability of a library.</span></span>

```fsharp
[<RequireQualifiedAccess>]
module StringTokenization =
    let parse s = ...

...

let s = getAString()
let parsed = StringTokenization.parse s // Must qualify to use 'parse'
```

### <a name="sort-open-statements-topologically"></a><span data-ttu-id="2aea1-134">정렬 `open` 문을 표면</span><span class="sxs-lookup"><span data-stu-id="2aea1-134">Sort `open` statements topologically</span></span>

<span data-ttu-id="2aea1-135">F#를 선언 측면을 비롯 한 순서 `open` 문입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-135">In F#, the order of declarations matters, including with `open` statements.</span></span> <span data-ttu-id="2aea1-136">이 C#과 달리 여기서 미치는 `using` 및 `using static` 파일에서 이러한 문은 순서와 무관 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-136">This is unlike C#, where the effect of `using` and `using static` is independent of the ordering of those statements in a file.</span></span>

<span data-ttu-id="2aea1-137">F#를 범위로 열 요소는 이미 다른 섀도잉할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-137">In F#, elements opened into a scope can shadow others already present.</span></span> <span data-ttu-id="2aea1-138">즉, 해당 재정렬 `open` 문을 코드의 의미를 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-138">This means that reordering `open` statements could alter the meaning of code.</span></span> <span data-ttu-id="2aea1-139">결과적으로 모든 정렬 임의의 `open` 문 (예를 들어, 사전순으로) 일반적으로 권장 되지 않습니다 내용을 볼 수 있는 다른 동작을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-139">As a result, any arbitrary sorting of all `open` statements (for example, alphanumerically) is generally not recommended, lest you generate different behavior that you might expect.</span></span>

<span data-ttu-id="2aea1-140">대신 좋습니다 정렬 하기 [표면](https://en.wikipedia.org/wiki/Topological_sorting); 순서 즉, 프로그램 `open` 문은 나타나는 순서 대로 _계층_ 정의 된 시스템의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-140">Instead, we recommend that you sort them [topologically](https://en.wikipedia.org/wiki/Topological_sorting); that is, order your `open` statements in the order in which _layers_ of your system are defined.</span></span> <span data-ttu-id="2aea1-141">다양 한 토폴로지 계층 정렬 영숫자 수행도 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-141">Doing alphanumeric sorting within different topological layers may also be considered.</span></span>

<span data-ttu-id="2aea1-142">예를 들어 다음은 정렬에 대 한 토폴로지는 F# 컴파일러 서비스 공개 API 파일:</span><span class="sxs-lookup"><span data-stu-id="2aea1-142">As an example, here is the topological sorting for the F# compiler service public API file:</span></span>

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

<span data-ttu-id="2aea1-143">줄 바꿈을 나중에 사전순으로 정렬 하 고 각 계층을 사용 하 여 토폴로지 계층을 구분 하는 참고 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-143">Note that a line break separates topological layers, with each layer being sorted alphanumerically afterwards.</span></span> <span data-ttu-id="2aea1-144">이 값을 실수로 섀도잉 없이 코드를 완전히 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-144">This cleanly organizes code without accidentally shadowing values.</span></span>

## <a name="use-classes-to-contain-values-that-have-side-effects"></a><span data-ttu-id="2aea1-145">의도 하지 않은 값을 포함 하도록 클래스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-145">Use classes to contain values that have side effects</span></span>

<span data-ttu-id="2aea1-146">경우가 많은 경우 값을 초기화 있습니다 데이터베이스나 다른 원격 리소스에 대 한 컨텍스트를 인스턴스화하고 같은 부작용이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-146">There are many times when initializing a value can have side effects, such as instantiating a context to a database or other remote resource.</span></span> <span data-ttu-id="2aea1-147">모듈에서 이러한 작업을 초기화 하 고 후속 함수에서 사용 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-147">It is tempting to initialize such things in a module and use it in subsequent functions:</span></span>

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

<span data-ttu-id="2aea1-148">이 자주 좋은 몇 가지 이유로:</span><span class="sxs-lookup"><span data-stu-id="2aea1-148">This is frequently a bad idea for a few reasons:</span></span>

<span data-ttu-id="2aea1-149">응용 프로그램 구성을 사용 하 여 코드 베이스에 푸시됩니다. 먼저 `dep1` 고 `dep2`입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-149">First, application configuration is pushed into the codebase with `dep1` and `dep2`.</span></span> <span data-ttu-id="2aea1-150">이 더 큰 코드 베이스에서 유지 관리 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-150">This is difficult to maintain in larger codebases.</span></span>

<span data-ttu-id="2aea1-151">두 번째, 정적으로 초기화 된 데이터는 구성 요소 자체 여러 스레드에서 사용 하는 경우 스레드로부터 안전 하지 않은 값을 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-151">Second, statically initialized data should not include values that are not thread safe if your component will itself use multiple threads.</span></span> <span data-ttu-id="2aea1-152">이 명확 하 게에 위반 `dep3`합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-152">This is clearly violated by `dep3`.</span></span>

<span data-ttu-id="2aea1-153">마지막으로 모듈을 초기화 전체 컴파일 단위에 대 한 정적 생성자로 컴파일합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-153">Finally, module initialization compiles into a static constructor for the entire compilation unit.</span></span> <span data-ttu-id="2aea1-154">으로 매니페스트는 모듈의 let 바인딩 값 초기화에서 오류가 발생할 경우를 `TypeInitializationException` 는 다음 응용 프로그램의 전체 수명 동안 캐시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-154">If any error occurs in let-bound value initialization in that module, it manifests as a `TypeInitializationException` that is then cached for the entire lifetime of the application.</span></span> <span data-ttu-id="2aea1-155">이 진단이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-155">This can be difficult to diagnose.</span></span> <span data-ttu-id="2aea1-156">일반적으로 내부 예외에 대 한 이유를 시작할 수 있습니다 하지만 없는 경우 다음이 근본 원인을 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-156">There is usually an inner exception that you can attempt to reason about, but if there is not, then there is no telling what the root cause is.</span></span>

<span data-ttu-id="2aea1-157">대신,만 사용 하 여 간단한 클래스 종속성을 갖는.</span><span class="sxs-lookup"><span data-stu-id="2aea1-157">Instead, just use a simple class to hold dependencies:</span></span>

```fsharp
type MyParametricApi(dep1, dep2, dep3) =
    member __.Function1 arg1 = doStuffWith dep1 dep2 dep3 arg1
    member __.Function2 arg2 = doStuffWith dep1 dep2 dep3 arg2
```

<span data-ttu-id="2aea1-158">이 후 다음이 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-158">This enables the following:</span></span>

1. <span data-ttu-id="2aea1-159">API 자체 외부 종속 된 모든 상태를 푸시합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-159">Pushing any dependent state outside of the API itself.</span></span>
2. <span data-ttu-id="2aea1-160">구성은 API를 외부에서 지금 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-160">Configuration can now be done outside of the API.</span></span>
3. <span data-ttu-id="2aea1-161">종속 값에 대 한 초기화 오류도 나타날 가능성이 없는 `TypeInitializationException`입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-161">Errors in initialization for dependent values are not likely to manifest as a `TypeInitializationException`.</span></span>
4. <span data-ttu-id="2aea1-162">API를 쉽게 테스트 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-162">The API is now easier to test.</span></span>

## <a name="error-management"></a><span data-ttu-id="2aea1-163">오류 관리</span><span class="sxs-lookup"><span data-stu-id="2aea1-163">Error management</span></span>

<span data-ttu-id="2aea1-164">대규모 시스템의 오류 관리는 복잡 하 고 미묘한 노력, 되며 없습니다 silver 시스템 보장 글머리 기호는 내결함성 및 잘 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-164">Error management in large systems is a complex and nuanced endeavor, and there are no silver bullets in ensuring your systems are fault-tolerant and behave well.</span></span> <span data-ttu-id="2aea1-165">다음 지침은 이동이 어렵게 공간에 대 한 지침을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-165">The following guidelines should offer guidance in navigating this difficult space.</span></span>

### <a name="represent-error-cases-and-illegal-state-in-types-intrinsic-to-your-domain"></a><span data-ttu-id="2aea1-166">오류 사례 및 도메인에 기본 형식에 잘못 된 상태를 나타내는</span><span class="sxs-lookup"><span data-stu-id="2aea1-166">Represent error cases and illegal state in types intrinsic to your domain</span></span>

<span data-ttu-id="2aea1-167">사용 하 여 [구별 된 공용 구조체](../language-reference/discriminated-unions.md), F# 형식 시스템에 결함이 있는 프로그램 상태를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-167">With [Discriminated Unions](../language-reference/discriminated-unions.md), F# gives you the ability to represent faulty program state in your type system.</span></span> <span data-ttu-id="2aea1-168">예를 들어:</span><span class="sxs-lookup"><span data-stu-id="2aea1-168">For example:</span></span>

```fsharp
type MoneyWithdrawalResult =
    | Success of amount:decimal
    | InsufficientFunds of balance:decimal
    | CardExpired of DateTime
    | UndisclosedFailure
```

<span data-ttu-id="2aea1-169">이 경우 세 가지 알려진 money 은행 계좌에서 출금 실패할 수 있는 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-169">In this case, there are three known ways that withdrawing money from a bank account can fail.</span></span> <span data-ttu-id="2aea1-170">각 오류 사례 형식으로 표현 되 고 있으므로 처리할 수 있습니다 사용 하 여 안전 하 게 프로그램 전체에서.</span><span class="sxs-lookup"><span data-stu-id="2aea1-170">Each error case is represented in the type, and can thus be dealt with safely throughout the program.</span></span>

```fsharp
let handleWithdrawal amount =
    let w = withdrawMoney amount
    match w with
    | Success am -> printfn "Successfully withdrew %f" am
    | InsufficientFunds balance -> printfn "Failed: balance is %f" balance
    | CardExpired expiredDate -> printfn "Failed: card expired on %O" expiredDate
    | UndisclosedFailure -> printfn "Failed: unknown"
```

<span data-ttu-id="2aea1-171">일반적으로 다양 한 방법을 모델링할 수 없습니다. 했을 수 없습니다 **실패** 도메인에서 다음 오류 처리 코드는 더 이상 처리 일반 프로그램 흐름 외에도 처리 해야 하는 것으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-171">In general, if you can model the different ways that something can **fail** in your domain, then error handling code is no longer treated as something you must deal with in addition to regular program flow.</span></span> <span data-ttu-id="2aea1-172">단순히 일반 프로그램 흐름의 일부 이며 간주 되지 않습니다 **예외적인**합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-172">It is simply a part of normal program flow, and not considered **exceptional**.</span></span> <span data-ttu-id="2aea1-173">이 두 가지 주요 이점을 가지 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-173">There are two primary benefits to this:</span></span>

1. <span data-ttu-id="2aea1-174">시간이 지남에 따라 변경 되는 도메인을 유지 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-174">It is easier to maintain as your domain changes over time.</span></span>
2. <span data-ttu-id="2aea1-175">오류 사례는 단위 테스트 하기 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-175">Error cases are easier to unit test.</span></span>

### <a name="use-exceptions-when-errors-cannot-be-represented-with-types"></a><span data-ttu-id="2aea1-176">오류 형식으로 표현할 수 없는 경우 예외를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-176">Use exceptions when errors cannot be represented with types</span></span>

<span data-ttu-id="2aea1-177">문제 도메인의 모든 오류를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-177">Not all errors can be represented in a problem domain.</span></span> <span data-ttu-id="2aea1-178">이러한 종류의 오류를 *예외적인* 본질적으로 따라서 시키고 예외를 catch 하는 기능 F#합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-178">These kinds of faults are *exceptional* in nature, hence the ability to raise and catch exceptions in F#.</span></span>

<span data-ttu-id="2aea1-179">첫째, 것이 좋습니다 읽어 합니다 [예외 디자인 지침](../../standard/design-guidelines/exceptions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-179">First, it is recommended that you read the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md).</span></span> <span data-ttu-id="2aea1-180">이러한 경우에 적용할 F#입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-180">These are also applicable to F#.</span></span>

<span data-ttu-id="2aea1-181">기본 구문에서 사용할 수 있는 F# 다음 우선 순위에서 예외를 발생 시키기 위해 고려해 야에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-181">The main constructs available in F# for the purposes of raising exceptions should be considered in the following order of preference:</span></span>

| <span data-ttu-id="2aea1-182">함수</span><span class="sxs-lookup"><span data-stu-id="2aea1-182">Function</span></span> | <span data-ttu-id="2aea1-183">구문</span><span class="sxs-lookup"><span data-stu-id="2aea1-183">Syntax</span></span> | <span data-ttu-id="2aea1-184">용도</span><span class="sxs-lookup"><span data-stu-id="2aea1-184">Purpose</span></span> |
|----------|--------|---------|
| `nullArg` | `nullArg "argumentName"` | <span data-ttu-id="2aea1-185">발생 한 `System.ArgumentNullException` 지정한 인수 이름을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-185">Raises a `System.ArgumentNullException` with the specified argument name.</span></span> |
| `invalidArg` | `invalidArg "argumentName" "message"` | <span data-ttu-id="2aea1-186">발생 한 `System.ArgumentException` 지정 된 인수 이름과 메시지를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-186">Raises a `System.ArgumentException` with a specified argument name and message.</span></span> |
| `invalidOp` | `invalidOp "message"` | <span data-ttu-id="2aea1-187">발생 한 `System.InvalidOperationException` 지정된 된 메시지를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-187">Raises a `System.InvalidOperationException` with the specified message.</span></span> |
|`raise`| `raise (ExceptionType("message"))` | <span data-ttu-id="2aea1-188">예외를 throw 하는 것에 대 한 일반 용도의 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-188">General-purpose mechanism for throwing exceptions.</span></span> |
| `failwith` | `failwith "message"` | <span data-ttu-id="2aea1-189">발생 한 `System.Exception` 지정된 된 메시지를 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-189">Raises a `System.Exception` with the specified message.</span></span> |
| `failwithf` | `failwithf "format string" argForFormatString` | <span data-ttu-id="2aea1-190">발생을 `System.Exception` 서식 문자열 및 해당 입력에 따른 메시지와 함께 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-190">Raises a `System.Exception` with a message determined by the format string and its inputs.</span></span> |

<span data-ttu-id="2aea1-191">사용 하 여 `nullArg`, `invalidArg` 하 고 `invalidOp` throw 하는 메커니즘으로 `ArgumentNullException`를 `ArgumentException` 및 `InvalidOperationException` 적절 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-191">Use `nullArg`, `invalidArg` and `invalidOp` as the mechanism to throw `ArgumentNullException`, `ArgumentException` and `InvalidOperationException` when appropriate.</span></span>

<span data-ttu-id="2aea1-192">합니다 `failwith` 및 `failwithf` 함수 기본 발생 하므로 피해 야 일반적으로 `Exception` 특정 예외가 아닌를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-192">The `failwith` and `failwithf` functions should generally be avoided because they raise the base `Exception` type, not a specific exception.</span></span> <span data-ttu-id="2aea1-193">기준으로 합니다 [예외 디자인 지침](../../standard/design-guidelines/exceptions.md), 가능한 경우 보다 구체적인 예외를 발생 시키려면 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-193">As per the [Exception Design Guidelines](../../standard/design-guidelines/exceptions.md), you want to raise more specific exceptions when you can.</span></span>

### <a name="using-exception-handling-syntax"></a><span data-ttu-id="2aea1-194">예외 처리 구문을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="2aea1-194">Using exception-handling syntax</span></span>

<span data-ttu-id="2aea1-195">F#통해 예외 패턴을 지원 합니다 `try...with` 구문:</span><span class="sxs-lookup"><span data-stu-id="2aea1-195">F# supports exception patterns via the `try...with` syntax:</span></span>

```fsharp
try
    tryGetFileContents()
with
| :? System.IO.FileNotFoundException as e -> // Do something with it here
| :? System.Security.SecurityException as e -> // Do something with it here
```

<span data-ttu-id="2aea1-196">패턴 일치와 함께 예외가 발생 하는 경우 수행 하는 기능을 조정 하는 정리 코드를 유지 하려는 경우에 약간 까다로울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-196">Reconciling functionality to perform in the face of an exception with pattern matching can be a bit tricky if you wish to keep the code clean.</span></span> <span data-ttu-id="2aea1-197">이 처리 하기 위해 이러한 방법 중 하나를 사용 하는 것 [활성 패턴](../language-reference/active-patterns.md) 자체 예외를 사용 하 여 오류 사례를 둘러싼 그룹 기능을 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-197">One such way to handle this is to use [active patterns](../language-reference/active-patterns.md) as a means to group functionality surrounding an error case with an exception itself.</span></span> <span data-ttu-id="2aea1-198">예를 들어, 예외를 throw 할 때 예외 메타 데이터에서 중요 한 정보를 포함 하는 API 사용 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-198">For example, you may be consuming an API that, when it throws an exception, encloses valuable information in the exception metadata.</span></span> <span data-ttu-id="2aea1-199">활성 패턴 내에서 캡처된 예외의 본문에 유용한 값을 래핑 해제 및 반환 값 일부 상황에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-199">Unwrapping a useful value in the body of the captured exception inside the Active Pattern and returning that value can be helpful in some situations.</span></span>

### <a name="do-not-use-monadic-error-handling-to-replace-exceptions"></a><span data-ttu-id="2aea1-200">Monadic 오류 예외를 바꾸려면 처리를 사용 하지 마세요</span><span class="sxs-lookup"><span data-stu-id="2aea1-200">Do not use monadic error handling to replace exceptions</span></span>

<span data-ttu-id="2aea1-201">예외는 함수형 프로그래밍에서 다소 taboo로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-201">Exceptions are seen as somewhat taboo in functional programming.</span></span> <span data-ttu-id="2aea1-202">실제로 예외 not 상당히 기능으로 간주 해도 이므로 무결성을 위반 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-202">Indeed, exceptions violate purity, so it's safe to consider them not-quite functional.</span></span> <span data-ttu-id="2aea1-203">그러나이 코드 실행 해야 합니다는 위치 및 해당 런타임 오류가 발생할 수 있습니다 실제로 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-203">However, this ignores the reality of where code must run, and that runtime errors can occur.</span></span> <span data-ttu-id="2aea1-204">일반적으로 대부분의 항목이 순수 아니고 총 반갑지 않은 놀라움을 최소화 하기 위해 가정 하에서 코드를 작성 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-204">In general, write code on the assumption that most things are neither pure nor total, to minimize unpleasant surprises.</span></span>

<span data-ttu-id="2aea1-205">것이 핵심 장점/의 다음 측면을 예외는 관련성 및 전체.NET 런타임 및 언어 간 에코 시스템의 적합성에 대해 고려해 야 할 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-205">It is important to consider the following core strengths/aspects of Exceptions with respect to their relevance and appropriateness in the .NET runtime and cross-language ecosystem as a whole:</span></span>

1. <span data-ttu-id="2aea1-206">문제를 디버깅 하는 경우 매우 유용 하는 자세한 진단 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-206">They contain detailed diagnostic information, which is very helpful when debugging an issue.</span></span>
2. <span data-ttu-id="2aea1-207">런타임 및 기타.NET 언어에서 잘 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-207">They are well-understood by the runtime and other .NET languages.</span></span>
3. <span data-ttu-id="2aea1-208">해당 방법에서 사용 되는 코드를 비교할 때 중요 한 상용구 줄일 수 있습니다 *방지* 임시 단위로 해당 의미 체계의 일부 하위 집합을 구현 하 여 예외입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-208">They can reduce significant boilerplate when compared with code that goes out of its way to *avoid* exceptions by implementing some subset of their semantics on an ad-hoc basis.</span></span>

<span data-ttu-id="2aea1-209">이 세 번째 점이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-209">This third point is critical.</span></span> <span data-ttu-id="2aea1-210">복잡 한 작업의 중요 한 경우 예외를 사용 하지 않고이 같은 구조를 사용 하 여 처리에서 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-210">For nontrivial complex operations, failing to use exceptions can result in dealing with structures like this:</span></span>

```fsharp
Result<Result<MyType, string>, string list>
```

<span data-ttu-id="2aea1-211">"형식의 stringly" 오류에 패턴 일치와 같은 취약 한 코드를 쉽게 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-211">Which can easily lead to fragile code like pattern matching on "stringly-typed" errors:</span></span>

```fsharp
let result = doStuff()
match result with
| Ok r -> ...
| Error e ->
    if e.Contains "Error string 1" then ...
    elif e.Contains "Error string 2" then ...
    else ... // Who knows?
```

<span data-ttu-id="2aea1-212">또한 "멋진" 형식을 반환 하는 "단순" 함수에 대 한 원하는 모든 예외를 무시 하 고 싶을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-212">Additionally, it can be tempting to swallow any exception in the desire for a "simple" function that returns a "nicer" type:</span></span>

```fsharp
// This is bad!
let tryReadAllText (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with _ -> None
```

<span data-ttu-id="2aea1-213">아쉽게도 `tryReadAllText` 무수 한 파일 시스템에서 발생할 수 있는 작업을 기반으로 하는 다양 한 예외를 throw 할 수 있습니다 및이 코드를 지금 삭제 수 실제로 수 무엇이 환경의 대 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-213">Unfortunately, `tryReadAllText` can throw numerous exceptions based on the myriad of things that can happen on a file system, and this code discards away any information about what might actually be going wrong in your environment.</span></span> <span data-ttu-id="2aea1-214">결과 형식을 사용 하 여이 코드를 대체 하는 경우 작성할 때는 메시지 구문 분석 오류 "형식의 stringly" 돌아가기:</span><span class="sxs-lookup"><span data-stu-id="2aea1-214">If you replace this code with a result type, then you're back to "stringly-typed" error message parsing:</span></span>

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

<span data-ttu-id="2aea1-215">예외 개체 자체를 배치 하 고에 `Error` 아닌 함수 호출 사이트에서 예외 형식으로 제대로 처리 하는 생성자만 강제 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-215">And placing the exception object itself in the `Error` constructor just forces you to properly deal with the exception type at the call site rather than in the function.</span></span> <span data-ttu-id="2aea1-216">이렇게 효율적으로 악명이 높습니다 재미 API의 호출자가 처리 되지 않는 확인된 예외를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-216">Doing this effectively creates checked exceptions, which are notoriously unfun to deal with as a caller of an API.</span></span>

<span data-ttu-id="2aea1-217">위의 예제에 대 한 좋은 대안은 catch 하는 것 *특정* 예외 및 해당 예외의 컨텍스트에서 의미 있는 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-217">A good alternative to the above examples is to catch *specific* exceptions and return a meaningful value in the context of that exception.</span></span> <span data-ttu-id="2aea1-218">수정 하는 경우는 `tryReadAllText` 함수를 다음과 같이 `None` 자세한 의미가:</span><span class="sxs-lookup"><span data-stu-id="2aea1-218">If you modify the `tryReadAllText` function as follows, `None` has more meaning:</span></span>

```fsharp
let tryReadAllTextIfPresent (path : string) =
    try System.IO.File.ReadAllText path |> Some
    with :? FileNotFoundException -> None
```

<span data-ttu-id="2aea1-219">범용으로 작동 하는 대신이 함수는 이제 제대로 처리 경우 파일을 찾을 수 없습니다 하 고 반환 하는 의미를 할당 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-219">Instead of functioning as a catch-all, this function will now properly handle the case when a file was not found and assign that meaning to a return.</span></span> <span data-ttu-id="2aea1-220">반환 값이 모든 컨텍스트 정보를 삭제 하거나 호출자가 코드의 해당 지점에서 적절 하지 않을 경우를 처리 하도록 강제 하지 하는 동안 해당 오류 사례를 매핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-220">This return value can map to that error case, while not discarding any contextual information or forcing callers to deal with a case that may not be relevant at that point in the code.</span></span>

<span data-ttu-id="2aea1-221">와 같은 형식 `Result<'Success, 'Error>` 적합 한 기본 작업에 대 한 중첩 되지 않습니다 여기서 및 F# 선택적 형식은 완벽 한 반환 없습니다 것을 나타내는 경우에 대 한 *무언가* 또는 *아무것도*.</span><span class="sxs-lookup"><span data-stu-id="2aea1-221">Types such as `Result<'Success, 'Error>` are appropriate for basic operations where they aren't nested, and F# optional types are perfect for representing when something could either return *something* or *nothing*.</span></span> <span data-ttu-id="2aea1-222">예외에 대 한 대체 하지는 하지만 하며 해서는 안 시도할 때에서 예외를 교체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-222">They are not a replacement for exceptions, though, and should not be used in an attempt to replace exceptions.</span></span> <span data-ttu-id="2aea1-223">대신 이러한 해야 신중 하 게 요소에 적용할 수 주소 특정 예외 및 오류 관리 정책의 대상으로 지정 된 방식에서입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-223">Rather, they should be applied judiciously to address specific aspects of exception and error management policy in targeted ways.</span></span>

## <a name="partial-application-and-point-free-programming"></a><span data-ttu-id="2aea1-224">부분 응용 프로그램 및 지점 무료 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2aea1-224">Partial application and point-free programming</span></span>

<span data-ttu-id="2aea1-225">F#지점 무료 스타일에서 부분 응용 프로그램 및 따라서 다양 한 프로그램을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-225">F# supports partial application, and thus, various ways to program in a point-free style.</span></span> <span data-ttu-id="2aea1-226">이 모듈 또는 항목의 구현 내에서 코드 재사용에 대 한 도움이 될 수 있지만 이것은 일반적으로 공개적으로 노출 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-226">This can be beneficial for code reuse within a module or the implementation of something, but it is generally not something to expose publicly.</span></span> <span data-ttu-id="2aea1-227">일반적으로 지점 무료 프로그래밍에 자체의 전문화 아니며 스타일을 사용 하지는 사람들에 게 중요 한 cognitive barrier를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-227">In general, point-free programming is not a virtue in and of itself, and can add a significant cognitive barrier for people who are not immersed in the style.</span></span>

### <a name="do-not-use-partial-application-and-currying-in-public-apis"></a><span data-ttu-id="2aea1-228">부분 응용 프로그램 및 공용 api에서 (currying) 사용 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="2aea1-228">Do not use partial application and currying in public APIs</span></span>

<span data-ttu-id="2aea1-229">거의 예외를 제외 하 고, 공용 Api에서 부분 응용 프로그램의 사용 소비자에 대 한 혼동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-229">With little exception, the use of partial application in public APIs can be confusing for consumers.</span></span> <span data-ttu-id="2aea1-230">일반적으로 `let`-값에 바인딩된 F# 코드 **값**아니라 **함수 값**.</span><span class="sxs-lookup"><span data-stu-id="2aea1-230">Usually, `let`-bound values in F# code are **values**, not **function values**.</span></span> <span data-ttu-id="2aea1-231">와 같은 연산자를 사용 하 여 결합 하는 경우에 특히 소수의 cognitive 오버 헤드를 줄이려면 상당한 대가로 코드 줄을 저장 하는 중 발생할 수 있습니다 함수 값과 함께 혼합 `>>` 함수를 작성 하 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-231">Mixing together values and function values can result in saving a small number of lines of code in exchange for quite a bit of cognitive overhead, especially if combined with operators such as `>>` to compose functions.</span></span>

### <a name="consider-the-tooling-implications-for-point-free-programming"></a><span data-ttu-id="2aea1-232">지점 무료 프로그래밍 도구 결과 고려해 야</span><span class="sxs-lookup"><span data-stu-id="2aea1-232">Consider the tooling implications for point-free programming</span></span>

<span data-ttu-id="2aea1-233">커리 된 함수는 해당 인수 레이블이 지정 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-233">Curried functions do not label their arguments.</span></span> <span data-ttu-id="2aea1-234">이 의미를 도구에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-234">This has tooling implications.</span></span> <span data-ttu-id="2aea1-235">다음 두 가지 함수를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-235">Consider the following two functions:</span></span>

```fsharp
let func name age =
    printfn "My name is %s and I am %d years old!" name age

let funcWithApplication =
    printfn "My name is %s and I am %d years old!"
```

<span data-ttu-id="2aea1-236">둘 다 유효 함수 있지만 `funcWithApplication` 커리 된 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-236">Both are valid functions, but `funcWithApplication` is a curried function.</span></span> <span data-ttu-id="2aea1-237">편집기에서 해당 형식의 마우스로 가리키면이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-237">When you hover over their types in an editor, you see this:</span></span>

```fsharp
val func : name:string -> age:int -> unit

val funcWithApplication : (string -> int -> unit)
```

<span data-ttu-id="2aea1-238">호출 사이트에서 Visual Studio와 같은 도구에서 도구 설명을 제공 되지 것입니다 어떤 의미 있는 정보를 `string` 고 `int` 입력된 형식은 실제로 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-238">At the call site, tooltips in tooling such as Visual Studio will not give you meaningful information as to what the `string` and `int` input types actually represent.</span></span>

<span data-ttu-id="2aea1-239">다음과 같은 코드 포인트 무료 발생 하는 경우 `funcWithApplication` 는 공개적으로 사용할 수 있는 것이 좋습니다 도구 수에 의미 있는 이름을 인수에 대 한 작업을 전체 η 확장을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-239">If you encounter point-free code like `funcWithApplication` that is publicly consumable, it is recommended to do a full η-expansion so that tooling can pick up on meaningful names for arguments.</span></span>

<span data-ttu-id="2aea1-240">또한 지점 해제 코드를 디버깅 어려울 수 있습니다, 거의 불가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-240">Furthermore, debugging point-free code can be challenging, if not impossible.</span></span> <span data-ttu-id="2aea1-241">이름에 바인딩된 값에 의존 하는 디버깅 도구 (예를 들어 `let` 바인딩) 실행 중간 중간 값을 검사할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-241">Debugging tools rely on values bound to names (for example, `let` bindings) so that you can inspect intermediate values midway through execution.</span></span> <span data-ttu-id="2aea1-242">코드를 검사할 값이 없는 있는 경우 디버그 것이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-242">When your code has no values to inspect, there is nothing to debug.</span></span> <span data-ttu-id="2aea1-243">나중에 디버깅 도구 이전에 실행된 경로에 따라 이러한 값을 만드는 진화 할 수 있지만 사용자 선택에서 다변화 하는 좋은 방법이 아닙니다 *잠재적인* 기능을 디버그 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-243">In the future, debugging tools may evolve to synthesize these values based on previously executed paths, but it's not a good idea to hedge your bets on *potential* debugging functionality.</span></span>

### <a name="consider-partial-application-as-a-technique-to-reduce-internal-boilerplate"></a><span data-ttu-id="2aea1-244">내부 상용구를 줄이기 위해 기술로 서 부분 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2aea1-244">Consider partial application as a technique to reduce internal boilerplate</span></span>

<span data-ttu-id="2aea1-245">앞서 달리 부분 응용 프로그램은 응용 프로그램 또는 API의 심층적인 내부 내부 상용구를 줄이기 위한 훌륭한 도구.</span><span class="sxs-lookup"><span data-stu-id="2aea1-245">In contrast to the previous point, partial application is a wonderful tool for reducing boilerplate inside of an application or the deeper internals of an API.</span></span> <span data-ttu-id="2aea1-246">단위 테스트 상용구 경우가 얼마나 많은 노력을 처리 하는 더 복잡 한 Api 구현 하는 데 도움이 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-246">It can be helpful for unit testing the implementation of more complicated APIs, where boilerplate is often a pain to deal with.</span></span> <span data-ttu-id="2aea1-247">예를 들어, 수행 하는 방법은 다음 코드와 어떤 가장 모의 프레임 워크를 제공 하면 이러한 프레임 워크 외부 종속성을 수행 하지 않고 API를 맞춤식 관련 배울 필요 하며</span><span class="sxs-lookup"><span data-stu-id="2aea1-247">For example, the following code shows how you can accomplish what most mocking frameworks give you without taking an external dependency on such a framework and having to learn a related bespoke API.</span></span>

<span data-ttu-id="2aea1-248">예를 들어, 다음 솔루션 토폴로지를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-248">For example, consider the following solution topography:</span></span>

```
MySolution.sln
|_/ImplementationLogic.fsproj
|_/ImplementationLogic.Tests.fsproj
|_/API.fsproj
```

<span data-ttu-id="2aea1-249">`ImplementationLogic.fsproj` 와 같은 코드를 노출 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-249">`ImplementationLogic.fsproj` might expose code such as:</span></span>

```fsharp
module Transactions =
    let doTransaction txnContext txnType balance =
        ...

type Transactor(ctx, currentBalance) =
    member __.ExecuteTransaction(txnType) =
        Transactions.doTransaction ctx txtType currentBalance
        ...
```

<span data-ttu-id="2aea1-250">단위 테스트 `Transactions.doTransaction` 에서 `ImplementationLogic.Tests.fspoj` 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-250">Unit testing `Transactions.doTransaction` in `ImplementationLogic.Tests.fspoj` is easy:</span></span>

```fsharp
namespace TransactionsTestingUtil

open Transactions

module TransactionsTestable =
    let getTestableTransactionRoutine mockContext = Transactions.doTransaction mockContext
```

<span data-ttu-id="2aea1-251">부분적으로 적용 `doTransaction` 모의 컨텍스트를 사용 하 여 개체 때마다 모의 컨텍스트를 생성 하지 않고도 단위 테스트의 모든 함수를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-251">Partially applying `doTransaction` with a mocking context object lets you call the function in all of your unit tests without needing to construct a mocked context each time:</span></span>

```fsharp
namespace TransactionTests

open Xunit
open TransactionTypes
open TransactionsTestingUtil
open TransactionsTestingUtil.TransactionsTestable

let testableContext =
    { new ITransactionContext with
        member __.TheFirstMember() = ...
        member __.TheSecondMember() = ... }

let transactionRoutine = getTestableTransactionRoutine testableContext

[<Fact>]
let ``Test withdrawal transaction with 0.0 for balance``() =
    let expected = ...
    let actual = transactionRoutine TransactionType.Withdraw 0.0
    Assert.Equal(expected, actual)
```

<span data-ttu-id="2aea1-252">전체 코드 베이스에이 기술을 보편적으로 적용 되지 해야 하지만 복잡 한 내부 및 단위 테스트 해당 내부 요소에 대 한 상용구를 줄이기 위해 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-252">This technique should not be universally applied to your entire codebase, but it is a good way to reduce boilerplate for complicated internals and unit testing those internals.</span></span>

## <a name="access-control"></a><span data-ttu-id="2aea1-253">액세스 제어</span><span class="sxs-lookup"><span data-stu-id="2aea1-253">Access control</span></span>

<span data-ttu-id="2aea1-254">F#에 대 한 여러 옵션이 [액세스 제어](../language-reference/access-control.md).NET 런타임에서 사용할 수 있는 항목에서 상속 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-254">F# has multiple options for [Access control](../language-reference/access-control.md), inherited from what is available in the .NET runtime.</span></span> <span data-ttu-id="2aea1-255">이러한 형식에 대 한 바로 사용할 수 없는 경우-도 사용할 수 있습니다 이러한 함수에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-255">These are not just usable for types - you can use them for functions, too.</span></span>

* <span data-ttu-id="2aea1-256">비-선호`public` 형식 및 공개적으로 사용할 수 있도록 하는 데 필요할 때까지 멤버입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-256">Prefer non-`public` types and members until you need them to be publicly consumable.</span></span> <span data-ttu-id="2aea1-257">또한 어떤 소비자 결합을 되도록 최소화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-257">This also minimizes what consumers couple to.</span></span>
* <span data-ttu-id="2aea1-258">모든 도우미 기능을 유지 하도록 `private`합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-258">Strive to keep all helper functionality `private`.</span></span>
* <span data-ttu-id="2aea1-259">사용을 고려 `[<AutoOpen>]` 도우미 함수의 다양 한 경우 개인 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-259">Consider the use of `[<AutoOpen>]` on a private module of helper functions if they become numerous.</span></span>

## <a name="type-inference-and-generics"></a><span data-ttu-id="2aea1-260">형식 유추 및 제네릭</span><span class="sxs-lookup"><span data-stu-id="2aea1-260">Type inference and generics</span></span>

<span data-ttu-id="2aea1-261">형식 유추 상용구 많은 입력에서 절약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-261">Type inference can save you from typing a lot of boilerplate.</span></span> <span data-ttu-id="2aea1-262">및 자동 일반화에는 F# 컴파일러는 하면 사용자의 추가 작업 없이 거의 보다 일반적인 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-262">And automatic generalization in the F# compiler can help you write more generic code with almost no extra effort on your part.</span></span> <span data-ttu-id="2aea1-263">그러나 이러한 기능은 일반적으로 좋은 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-263">However, these features are not universally good.</span></span>

* <span data-ttu-id="2aea1-264">공용 Api의 명시적 형식 인수 이름 레이블을 지정 하는 것이 좋습니다. 및이 대 한 형식 유추에 의존 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2aea1-264">Consider labeling argument names with explicit types in public APIs and do not rely on type inference for this.</span></span>

    <span data-ttu-id="2aea1-265">이유 **있습니다** 컴파일러가 아닌 API의 모양 제어에서 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-265">The reason for this is that **you** should be in control of the shape of your API, not the compiler.</span></span> <span data-ttu-id="2aea1-266">컴파일러를 형식 유추에서 세밀 하 게 작업을 수행할 수 이지만 의존 하는 내부 형식을 변경한 경우 변경 내용을 API의 모양을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-266">Although the compiler can do a fine job at inferring types for you, it is possible to have the shape of your API change if the internals it relies on have changed types.</span></span> <span data-ttu-id="2aea1-267">원하는 항목을이 수 있지만 다운스트림 소비자가 처리 하는 주요 API 변경 내용을 거의 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-267">This may be what you want, but it will almost certainly result in a breaking API change that downstream consumers will then have to deal with.</span></span> <span data-ttu-id="2aea1-268">대신 공용 API의 모양의 명시적으로 제어 하는 경우 이러한 주요 변경 내용을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-268">Instead, if you explicitly control the shape of your public API, then you can control these breaking changes.</span></span> <span data-ttu-id="2aea1-269">DDD 용어에서이 수 생각할 수 손상 방지 레이어를 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-269">In DDD terms, this can be thought of as an Anti-corruption layer.</span></span>

* <span data-ttu-id="2aea1-270">제네릭 인수에 의미 있는 이름을 제공 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-270">Consider giving a meaningful name to your generic arguments.</span></span>

    <span data-ttu-id="2aea1-271">특정 도메인에 한정 되지 않은 제네릭 실제로 코드를 작성 하는 경우가 아니면에 의미 있는 이름을 하는 도메인을 이해 하는 프로그래머에 게 다른 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-271">Unless you are writing truly generic code that is not specific to a particular domain, a meaningful name can help other programmers understanding the domain they're working in.</span></span> <span data-ttu-id="2aea1-272">예를 들어, 형식 매개 변수 라는 `'Document` 문서와 상호 작용의 컨텍스트에서 데이터베이스 더 명확 하 게 제네릭 문서 형식을 함수 또는 멤버를 사용 하 여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-272">For example, a type parameter named `'Document` in the context of interacting with a document database makes it clearer that generic document types can be accepted by the function or member you are working with.</span></span>

* <span data-ttu-id="2aea1-273">PascalCase 사용 하 여 제네릭 형식 매개 변수를 명명 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-273">Consider naming generic type parameters with PascalCase.</span></span>

    <span data-ttu-id="2aea1-274">이것이 하므로 camelCase 또는 snake_case를 사용 하는 대신 PascalCase를 사용 하는 것이 좋습니다..NET 작업을 수행 하는 일반적인 방법은입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-274">This is the general way to do things in .NET, so it's recommended that you use PascalCase rather than snake_case or camelCase.</span></span>

<span data-ttu-id="2aea1-275">마지막으로, 자동 일반화 되지 항상 처음 사용 하는 사람들에 게 유용 하 게 F# 또는 큰 코드 베이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-275">Finally, automatic generalization is not always a boon for people who are new to F# or a large codebase.</span></span> <span data-ttu-id="2aea1-276">일반적인 구성 요소를 사용 하 여 cognitive 오버 헤드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-276">There is cognitive overhead in using components that are generic.</span></span> <span data-ttu-id="2aea1-277">또한 자동으로 다른 입력 형식 (let 마찬가지로 사용 되어야 하는 경우에), 일반화 된 함수를 사용 되지 않습니다 경우는 해당 시점에 제네릭에 실제 이점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-277">Furthermore, if automatically generalized functions are not used with different input types (let alone if they are intended to be used as such), then there is no real benefit to them being generic at that point in time.</span></span> <span data-ttu-id="2aea1-278">항상 코드를 작성 하는 제네릭에서 실제로 이익을 경우 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-278">Always consider if the code you are writing will actually benefit from being generic.</span></span>

## <a name="performance"></a><span data-ttu-id="2aea1-279">성능</span><span class="sxs-lookup"><span data-stu-id="2aea1-279">Performance</span></span>

<span data-ttu-id="2aea1-280">F#값은 특정 부류의 버그 (특히 해당 관련 된 동시성 및 병렬 처리 수준)를 방지할 수 있습니다는 기본적으로 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-280">F# values are immutable by default, which allows you to avoid certain classes of bugs (especially those involving concurrency and parallelism).</span></span> <span data-ttu-id="2aea1-281">그러나 경우에 따라 실행 시간 또는 메모리 할당의 최적의 (또는 합당 한도) 효율성을 달성 하기 위해 작업의 범위를 가장 잘 구현 될 수 있습니다 상태의 전체 변형을 사용 하 여.</span><span class="sxs-lookup"><span data-stu-id="2aea1-281">However, in certain cases, in order to achieve optimal (or even reasonable) efficiency of execution time or memory allocations, a span of work may best be implemented by using in-place mutation of state.</span></span> <span data-ttu-id="2aea1-282">이것이 가능한 것으로 옵트인 별로 F# 와 `mutable` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-282">This is possible in an opt-in basis with F# with the `mutable` keyword.</span></span>

<span data-ttu-id="2aea1-283">그러나 이용 `mutable` 에서 F# 기능 순도 잘 어울리지 생각 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-283">However, use of `mutable` in F# may feel at odds with functional purity.</span></span> <span data-ttu-id="2aea1-284">해도 괜찮은 사용자 기대 수준에는 순수성 조정 하는 경우 이것이 [참조 투명성](https://en.wikipedia.org/wiki/Referential_transparency)합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-284">This is fine, if you adjust expectations from purity to [referential transparency](https://en.wikipedia.org/wiki/Referential_transparency).</span></span> <span data-ttu-id="2aea1-285">참조 투명성-순도-작성 하는 경우 최종 목표는 F# 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-285">Referential transparency - not purity - is the end goal when writing F# functions.</span></span> <span data-ttu-id="2aea1-286">이 옵션을 사용 하면 성능이 중요 한 코드는 변이 기반 구현을 통해 기능 인터페이스를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-286">This allows you to write a functional interface over a mutation-based implementation for performance critical code.</span></span>

### <a name="wrap-mutable-code-in-immutable-interfaces"></a><span data-ttu-id="2aea1-287">변경할 수 없는 인터페이스에서 변경할 수 있는 코드를 줄 바꿈</span><span class="sxs-lookup"><span data-stu-id="2aea1-287">Wrap mutable code in immutable interfaces</span></span>

<span data-ttu-id="2aea1-288">이 목표로 참조 투명성을 사용 하 여 성능이 중요 한 함수를 변경할 수 있는 언더 벨 리를 노출 하지 않는 코드를 쓸 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-288">With referential transparency as a goal, it is critical to write code that does not expose the mutable underbelly of performance-critical functions.</span></span> <span data-ttu-id="2aea1-289">예를 들어, 다음 코드 구현 된 `Array.contains` 함수는 F# 핵심 라이브러리:</span><span class="sxs-lookup"><span data-stu-id="2aea1-289">For example, the following code implements the `Array.contains` function in the F# core library:</span></span>

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

<span data-ttu-id="2aea1-290">이 함수를 여러 번 호출 기본 배열에는 변경 되지 않습니다 요구 하지도 않습니다 사용에서 변경할 수 있는 상태를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-290">Calling this function multiple times does not change the underlying array, nor does it require you to maintain any mutable state in consuming it.</span></span> <span data-ttu-id="2aea1-291">그는 코드의 거의 모든 줄 변형을 사용 하는 경우에 것 참조가 투명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-291">It is referentially transparent, even though almost every line of code within it uses mutation.</span></span>

### <a name="consider-encapsulating-mutable-data-in-classes"></a><span data-ttu-id="2aea1-292">클래스에서 변경할 수 있는 데이터를 캡슐화 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-292">Consider encapsulating mutable data in classes</span></span>

<span data-ttu-id="2aea1-293">변경할 수 있는 데이터를 사용 하 여 작업을 캡슐화 하는 단일 함수를 사용 하는 앞의 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-293">The previous example used a single function to encapsulate operations using mutable data.</span></span> <span data-ttu-id="2aea1-294">이 부족 항상 더 복잡 한 데이터 집합에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-294">This is not always sufficient for more complex sets of data.</span></span> <span data-ttu-id="2aea1-295">다음 함수 집합을 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-295">Consider the following sets of functions:</span></span>

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

<span data-ttu-id="2aea1-296">이 코드가 성능이 있지만 호출자가 유지 관리 하는 것에 대 한 책임이 있으며 기반 데이터 구조를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-296">This code is performant, but it exposes the mutation-based data structure that callers are responsible for maintaining.</span></span> <span data-ttu-id="2aea1-297">이 변경할 수 있는 기본 멤버 없이 클래스 내부 래핑할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-297">This can be wrapped inside of a class with no underlying members that can change:</span></span>

```fsharp
open System.Collections.Generic

/// The results of computing the LALR(1) closure of an LR(0) kernel
type Closure1Table() =
    let t = Dictionary<Item0, HashSet<TerminalIndex>>()

    member __.Add(key, value) =
        if not (t.ContainsKey(key)) then
            t.Add(key, value)
        else
            t.[key] <- value

    member __.Count = t.Count

    member __.Contains(key, value) =
        match t.TryGetValue(key) with
        | (true, v) -> v.Equals(value)
        | (false, _) -> false
```

<span data-ttu-id="2aea1-298">`Closure1Table` 호출자가 기본 데이터 구조를 유지 하도록 강제 적용 하지 않는 것으로 기본 변이 기반 데이터 구조를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-298">`Closure1Table` encapsulates the underlying mutation-based data structure, thereby not forcing callers to maintain the underlying data structure.</span></span> <span data-ttu-id="2aea1-299">클래스는 데이터와 루틴 호출자에 게 세부 정보를 노출 하지 않고 변이 기반을 캡슐화 하는 강력한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-299">Classes are a powerful way to encapsulate data and routines that are mutation-based without exposing the details to callers.</span></span>

### <a name="prefer-let-mutable-to-reference-cells"></a><span data-ttu-id="2aea1-300">원하는 `let mutable` 참조 셀</span><span class="sxs-lookup"><span data-stu-id="2aea1-300">Prefer `let mutable` to reference cells</span></span>

<span data-ttu-id="2aea1-301">참조 셀은 자체 값이 아닌 값에 대 한 참조를 나타내는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-301">Reference cells are a way to represent the reference to a value rather than the value itself.</span></span> <span data-ttu-id="2aea1-302">성능이 중요 한 코드를 사용할 수 있습니다, 있지만 이러한 일반적으로 권장 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-302">Although they can be used for performance-critical code, they are generally not recommended.</span></span> <span data-ttu-id="2aea1-303">다음 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2aea1-303">Consider the following example:</span></span>

```fsharp
let kernels =
    let acc = ref Set.empty

    processWorkList startKernels (fun kernel ->
        if not ((!acc).Contains(kernel)) then
            acc := (!acc).Add(kernel)
        ...)

    !acc |> Seq.toList
```

<span data-ttu-id="2aea1-304">참조 셀을 이제 사용 "오염" 역참조를 다시 참조 하려면 기본 데이터를 갖는 모든 후속 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-304">The use of a reference cell now "pollutes" all subsequent code with having to dereference and re-reference the underlying data.</span></span> <span data-ttu-id="2aea1-305">대신 `let mutable`:</span><span class="sxs-lookup"><span data-stu-id="2aea1-305">Instead, consider `let mutable`:</span></span>

```fsharp
let kernels =
    let mutable acc = Set.empty

    processWorkList startKernels (fun kernel ->
        if not (acc.Contains(kernel)) then
            acc <- acc.Add(kernel)
        ...)

    acc |> Seq.toList
```

<span data-ttu-id="2aea1-306">람다 식 중간 변경의 단일 지점 외에도 다른 모든 코드는 터치 `acc` 는 더 일반적인 사용에 다른 방식으로 수행할 수 `let`-바인딩된 변경할 수 없는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-306">Aside from the single point of mutation in the middle of the lambda expression, all other code that touches `acc` can do so in a manner that is no different to the usage of a normal `let`-bound immutable value.</span></span> <span data-ttu-id="2aea1-307">이 쉽게 시간이 지남에 따라 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-307">This will make it easier to change over time.</span></span>

## <a name="object-programming"></a><span data-ttu-id="2aea1-308">개체 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="2aea1-308">Object programming</span></span>

<span data-ttu-id="2aea1-309">F#개체 및 개체 지향 (개체 지향) 개념에 대 한 전체 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-309">F# has full support for objects and object-oriented (OO) concepts.</span></span> <span data-ttu-id="2aea1-310">여러 개체 지향 개념 강력 하 고 유용 하지만, 그 중 일부는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-310">Although many OO concepts are powerful and useful, not all of them are ideal to use.</span></span> <span data-ttu-id="2aea1-311">다음 목록에서는 높은 수준에서 개체 지향 기능 범주에 대 한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-311">The following lists offer guidance on categories of OO features at a high level.</span></span>

<span data-ttu-id="2aea1-312">**대부분의 경우에서 이러한 기능을 사용 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="2aea1-312">**Consider using these features in many situations:**</span></span>

* <span data-ttu-id="2aea1-313">점 표기법 (`x.Length`)</span><span class="sxs-lookup"><span data-stu-id="2aea1-313">Dot notation (`x.Length`)</span></span>
* <span data-ttu-id="2aea1-314">인스턴스 멤버</span><span class="sxs-lookup"><span data-stu-id="2aea1-314">Instance members</span></span>
* <span data-ttu-id="2aea1-315">암시적 생성자</span><span class="sxs-lookup"><span data-stu-id="2aea1-315">Implicit constructors</span></span>
* <span data-ttu-id="2aea1-316">정적 멤버</span><span class="sxs-lookup"><span data-stu-id="2aea1-316">Static members</span></span>
* <span data-ttu-id="2aea1-317">인덱서 표기법 (`arr.[x]`)</span><span class="sxs-lookup"><span data-stu-id="2aea1-317">Indexer notation (`arr.[x]`)</span></span>
* <span data-ttu-id="2aea1-318">명명 된 인수와 선택적 인수</span><span class="sxs-lookup"><span data-stu-id="2aea1-318">Named and Optional arguments</span></span>
* <span data-ttu-id="2aea1-319">인터페이스 및 인터페이스 구현</span><span class="sxs-lookup"><span data-stu-id="2aea1-319">Interfaces and interface implementations</span></span>

<span data-ttu-id="2aea1-320">**먼저 이러한 기능에 대 한 도달 하지 않으므로 없지만 편리 하 게 문제를 해결 하는 경우에 적용할 신중 하 게 수행 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2aea1-320">**Don't reach for these features first, but do judiciously apply them when they are convenient to solve a problem:**</span></span>

* <span data-ttu-id="2aea1-321">메서드 오버로드</span><span class="sxs-lookup"><span data-stu-id="2aea1-321">Method overloading</span></span>
* <span data-ttu-id="2aea1-322">변경할 수 있는 데이터를 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-322">Encapsulated mutable data</span></span>
* <span data-ttu-id="2aea1-323">형식에 연산자</span><span class="sxs-lookup"><span data-stu-id="2aea1-323">Operators on types</span></span>
* <span data-ttu-id="2aea1-324">자동 속성</span><span class="sxs-lookup"><span data-stu-id="2aea1-324">Auto properties</span></span>
* <span data-ttu-id="2aea1-325">구현 `IDisposable` 및 `IEnumerable`</span><span class="sxs-lookup"><span data-stu-id="2aea1-325">Implementing `IDisposable` and `IEnumerable`</span></span>
* <span data-ttu-id="2aea1-326">형식 확장명</span><span class="sxs-lookup"><span data-stu-id="2aea1-326">Type extensions</span></span>
* <span data-ttu-id="2aea1-327">이벤트</span><span class="sxs-lookup"><span data-stu-id="2aea1-327">Events</span></span>
* <span data-ttu-id="2aea1-328">구조체</span><span class="sxs-lookup"><span data-stu-id="2aea1-328">Structs</span></span>
* <span data-ttu-id="2aea1-329">대리자</span><span class="sxs-lookup"><span data-stu-id="2aea1-329">Delegates</span></span>
* <span data-ttu-id="2aea1-330">열거형</span><span class="sxs-lookup"><span data-stu-id="2aea1-330">Enums</span></span>

<span data-ttu-id="2aea1-331">**일반적으로 사용 하지 않는 한 이러한 기능을 방지 합니다.**</span><span class="sxs-lookup"><span data-stu-id="2aea1-331">**Generally avoid these features unless you must use them:**</span></span>

* <span data-ttu-id="2aea1-332">형식 상속 기반 계층 구조 및 상속 구현</span><span class="sxs-lookup"><span data-stu-id="2aea1-332">Inheritance-based type hierarchies and implementation inheritance</span></span>
* <span data-ttu-id="2aea1-333">Null 및 `Unchecked.defaultof<_>`</span><span class="sxs-lookup"><span data-stu-id="2aea1-333">Nulls and `Unchecked.defaultof<_>`</span></span>

### <a name="prefer-composition-over-inheritance"></a><span data-ttu-id="2aea1-334">상속을 사용 하 여 컴퍼지션 선호합니다</span><span class="sxs-lookup"><span data-stu-id="2aea1-334">Prefer composition over inheritance</span></span>

<span data-ttu-id="2aea1-335">[상속을 통해 컴포지션](https://en.wikipedia.org/wiki/Composition_over_inheritance) 장기 관용구는 양호 F# 코드 준수 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-335">[Composition over inheritance](https://en.wikipedia.org/wiki/Composition_over_inheritance) is a long-standing idiom that good F# code can adhere to.</span></span> <span data-ttu-id="2aea1-336">기본 원칙 해야 하지 기본 클래스를 노출 하는 호출자 기능을 활용 하려면 해당 기본 클래스에서 상속 하도록 강제 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-336">The fundamental principle is that you should not expose a base class and force callers to inherit from that base class to get functionality.</span></span>

### <a name="use-object-expressions-to-implement-interfaces-if-you-dont-need-a-class"></a><span data-ttu-id="2aea1-337">개체 식을 사용 하 여 클래스 필요가 없는 경우 인터페이스를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-337">Use object expressions to implement interfaces if you don't need a class</span></span>

<span data-ttu-id="2aea1-338">[개체 식](../language-reference/object-expressions.md) 클래스 내부 작업을 수행 하지 않고도 값으로 구현된 된 인터페이스를 바인딩 즉석에서 인터페이스를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-338">[Object Expressions](../language-reference/object-expressions.md) allow you to implement interfaces on the fly, binding the implemented interface to a value without needing to do so inside of a class.</span></span> <span data-ttu-id="2aea1-339">이 편리 하 고 경우에 특히 있습니다 _만_ 전체 클래스에 대 한 필요가 없습니다 인터페이스를 구현 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-339">This is convenient, especially if you _only_ need to implement the interface and have no need for a full class.</span></span>

<span data-ttu-id="2aea1-340">예를 들어, 다음은 코드에서 실행 되는 [Ionide](http://ionide.io/) 가지고 있지 않은 기호를 추가한 경우 코드 수정 작업을 제공 하는 `open` 문을:</span><span class="sxs-lookup"><span data-stu-id="2aea1-340">For example, here is the code that is run in [Ionide](http://ionide.io/) to provide a code fix action if you've added a symbol that you don't have an `open` statement for:</span></span>

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

<span data-ttu-id="2aea1-341">에 있기 때문에 클래스 하지 않아도 Visual Studio Code API와 상호 작용할 때 개체 식이란이 이상적인 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-341">Because there is no need for a class when interacting with the Visual Studio Code API, Object Expressions are an ideal tool for this.</span></span> <span data-ttu-id="2aea1-342">단위 테스트, 임시 방식으로 테스트 루틴을 사용 하 여 인터페이스를 없애는 하려고 할 때 유용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-342">They are also valuable for unit testing, when you want to stub out an interface with test routines in an ad hoc manner.</span></span>

## <a name="type-abbreviations"></a><span data-ttu-id="2aea1-343">형식 약어</span><span class="sxs-lookup"><span data-stu-id="2aea1-343">Type Abbreviations</span></span>

<span data-ttu-id="2aea1-344">[형식 약어](../language-reference/type-abbreviations.md) 은 함수 서명 등 보다 복잡 한 형식을 다른 형식에 레이블을 지정 하는 편리한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-344">[Type Abbreviations](../language-reference/type-abbreviations.md) are a convenient way to assign a label to another type, such as a function signature or a more complex type.</span></span> <span data-ttu-id="2aea1-345">다음 별칭 레이블을 사용 하 여 계산을 정의 하는 데 필요한 항목을 할당 하는 예를 들어 [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), 심층 학습 라이브러리:</span><span class="sxs-lookup"><span data-stu-id="2aea1-345">For example, the following alias assigns a label to what's needed to define a computation with [CNTK](https://www.microsoft.com/en-us/cognitive-toolkit/), a deep learning library:</span></span>

```fsharp
open CNTK

// DeviceDescriptor, Variable, and Function all come from CNTK
type Computation = DeviceDescriptor -> Variable -> Function
```

<span data-ttu-id="2aea1-346">`Computation` 이름은 편리 하 게 시그니처와 일치 하는 것이 별칭을 지정 하는 모든 함수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-346">The `Computation` name is a convenient way to denote any function that matches the signature it is aliasing.</span></span> <span data-ttu-id="2aea1-347">다음과 같은 형식 약어를 사용 하 여 편리 하 고 더 간결한 코드 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-347">Using Type Abbreviations like this is convenient and allows for more succinct code.</span></span>

### <a name="avoid-using-type-abbreviations-to-represent-your-domain"></a><span data-ttu-id="2aea1-348">도메인을 나타내는 형식 약어를 사용 하지 마십시오</span><span class="sxs-lookup"><span data-stu-id="2aea1-348">Avoid using Type Abbreviations to represent your domain</span></span>

<span data-ttu-id="2aea1-349">형식 약어 함수 서명에 이름을 지정 하는 것에 대 한 편리 하기는 하지만 이러한 혼동 될 수 있습니다 다른 형식 이니셜 하는 경우입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-349">Although Type Abbreviations are convenient for giving a name to function signatures, they can be confusing when abbreviating other types.</span></span> <span data-ttu-id="2aea1-350">이 약어를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-350">Consider this abbreviation:</span></span>

```fsharp
// Does not actually abstract integers.
type BufferSize = int
```

<span data-ttu-id="2aea1-351">이 여러 가지 방법으로 혼동 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-351">This can be confusing in multiple ways:</span></span>

* <span data-ttu-id="2aea1-352">`BufferSize` 추상화; 아닙니다. 정수에 대 한 다른 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-352">`BufferSize` is not an abstraction; it is just another name for an integer.</span></span>
* <span data-ttu-id="2aea1-353">하는 경우 `BufferSize` 노출 된 공용 API에서이 쉽게 잘못 해석 될 수 이상의 의미 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-353">If `BufferSize` is exposed in a public API, it can easily be misinterpreted to mean more than just `int`.</span></span> <span data-ttu-id="2aea1-354">일반적으로 도메인에 여러 특성이 형식과 같은 기본 형식이 아닌 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-354">Generally, domain types have multiple attributes to them and are not primitive types like `int`.</span></span> <span data-ttu-id="2aea1-355">이 약어 위반 가정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-355">This abbreviation violates that assumption.</span></span>
* <span data-ttu-id="2aea1-356">대/소문자 `BufferSize` (PascalCase)는이 이와 같은 더 많은 데이터를 보유 하는 것을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-356">The casing of `BufferSize` (PascalCase) implies that this type holds more data.</span></span>
* <span data-ttu-id="2aea1-357">이 별칭 함수에 명명 된 인수를 제공에 비해 향상 된 명확성을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-357">This alias does not offer increased clarity compared with providing a named argument to a function.</span></span>
* <span data-ttu-id="2aea1-358">약어 컴파일된 IL; 영향은 없습니다. 마찬가지로 정수 이므로이 별칭은 컴파일 타임 구문.</span><span class="sxs-lookup"><span data-stu-id="2aea1-358">The abbreviation will not manifest in compiled IL; it is just an integer and this alias is a compile-time construct.</span></span>

```fsharp
module Networking =
    ...
    let send data (bufferSize: int) =
        ...
```

<span data-ttu-id="2aea1-359">요약 하자면, 형식 약어를 사용 하 여 문제는 이들이 **되지** 이니셜는 이러한 형식을 통해 추상화 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-359">In summary, the pitfall with Type Abbreviations is that they are **not** abstractions over the types they are abbreviating.</span></span> <span data-ttu-id="2aea1-360">이전 예에서 `BufferSize` 것을 `int` 없는 추가 데이터 나 내용 외에도 형식 시스템에서 모든 혜택을 사용 하 여 내부적으로 `int` 이미 합니다.</span><span class="sxs-lookup"><span data-stu-id="2aea1-360">In the previous example, `BufferSize` is just an `int` under the covers, with no additional data, nor any benefits from the type system besides what `int` already has.</span></span>
