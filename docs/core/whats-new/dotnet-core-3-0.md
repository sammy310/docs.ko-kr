---
title: .NET Core 3.0의 새로운 기능
description: .NET Core 3.0에 있는 새로운 기능에 대해 알아봅니다.
dev_langs:
- csharp
- vb
author: thraka
ms.author: adegeo
ms.date: 12/31/2018
ms.openlocfilehash: 086be4649f4e7e27ff98df6f26d08856683865c8
ms.sourcegitcommit: 438919211260bb415fc8f96ca3eabc33cf2d681d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2019
ms.locfileid: "59611785"
---
# <a name="whats-new-in-net-core-30-preview-2"></a><span data-ttu-id="efb5a-103">.NET Core 3.0(Preview 2)의 새로운 기능</span><span class="sxs-lookup"><span data-stu-id="efb5a-103">What's new in .NET Core 3.0 (Preview 2)</span></span>

<span data-ttu-id="efb5a-104">이 문서에서는 .NET Core 3.0(Preview 2)의 새로운 기능을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-104">This article describes what is new in .NET Core 3.0 (preview 2).</span></span> <span data-ttu-id="efb5a-105">가장 중요한 개선 사항 중 하나는 Windows 데스크톱 애플리케이션에 대한 지원(Windows만 해당)입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-105">One of the biggest enhancements is support for Windows desktop applications (Windows only).</span></span> <span data-ttu-id="efb5a-106">Windows 데스크톱이라는 .NET Core 3.0 SDK 구성 요소를 활용하여 Windows Forms 및 WPF(Windows Presentation Foundation) 애플리케이션을 포팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-106">By utilizing a .NET Core 3.0 SDK component called Windows Desktop, you can port your Windows Forms and Windows Presentation Foundation (WPF) applications.</span></span> <span data-ttu-id="efb5a-107">분명히 말하지만, Windows 데스크톱 구성 요소는 Windows에서만 지원되고 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-107">To be clear, the Windows Desktop component is only supported and included on Windows.</span></span> <span data-ttu-id="efb5a-108">자세한 내용은 아래의 [Windows 데스크톱](#windows-desktop) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-108">For more information, see the section [Windows desktop](#windows-desktop) below.</span></span>

<span data-ttu-id="efb5a-109">.NET Core 3.0에서는 C# 8.0에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-109">.NET Core 3.0 adds support for C# 8.0.</span></span>

<span data-ttu-id="efb5a-110">Windows, Mac 및 Linux에서 지금 바로 [.NET Core 3.0 Preview 2를 다운로드하여 시작](https://aka.ms/netcore3download)하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-110">[Download and get started with .NET Core 3.0 Preview 2](https://aka.ms/netcore3download) right now on Windows, Mac and Linux.</span></span> <span data-ttu-id="efb5a-111">릴리스에 대한 전체 세부 정보는 [.NET Core 3.0 Preview 2 릴리스 정보](https://aka.ms/netcore3releasenotes)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-111">You can see complete details of the release in the [.NET Core 3.0 Preview 2 release notes](https://aka.ms/netcore3releasenotes).</span></span>

<span data-ttu-id="efb5a-112">각 버전에서 릴리스된 내용에 대한 자세한 내용은 다음 공지 사항을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-112">For more information about what was released with each version, see the following announcements:</span></span>

- [<span data-ttu-id="efb5a-113">.NET Core 3.0 Preview 1 공지 사항</span><span class="sxs-lookup"><span data-stu-id="efb5a-113">.NET Core 3.0 Preview 1 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-1-and-open-sourcing-windows-desktop-frameworks/)
- [<span data-ttu-id="efb5a-114">.NET Core 3.0 Preview 2 공지 사항</span><span class="sxs-lookup"><span data-stu-id="efb5a-114">.NET Core 3.0 Preview 2 announcement</span></span>](https://devblogs.microsoft.com/dotnet/announcing-net-core-3-preview-2/)

## <a name="c-8"></a><span data-ttu-id="efb5a-115">C# 8</span><span class="sxs-lookup"><span data-stu-id="efb5a-115">C# 8</span></span>

<span data-ttu-id="efb5a-116">.NET Core 3.0은 C# 8을 지원하고 .NET Core 3.0 Preview 2에서는 다음과 같은 새로운 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-116">.NET Core 3.0 supports C# 8, and as of .NET Core 3.0 Preview 2, supports these new features.</span></span> <span data-ttu-id="efb5a-117">C# 8.0 기능에 대한 자세한 내용은 다음 블로그 게시물을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-117">For more information about C# 8.0 features, see the following blog posts:</span></span>

- <span data-ttu-id="efb5a-118">[Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/)(C# 8.0으로 더 많은 패턴 작업 수행)</span><span class="sxs-lookup"><span data-stu-id="efb5a-118">[Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/)</span></span>
- <span data-ttu-id="efb5a-119">[Take C# 8.0 for a spin](https://devblogs.microsoft.com/dotnet/take-c-8-0-for-a-spin/)(C# 8.0으로 작업 시도)</span><span class="sxs-lookup"><span data-stu-id="efb5a-119">[Take C# 8.0 for a spin](https://devblogs.microsoft.com/dotnet/take-c-8-0-for-a-spin/)</span></span>
- <span data-ttu-id="efb5a-120">[Building C# 8.0](https://devblogs.microsoft.com/dotnet/building-c-8-0/)(C# 8.0 빌드)</span><span class="sxs-lookup"><span data-stu-id="efb5a-120">[Building C# 8.0](https://devblogs.microsoft.com/dotnet/building-c-8-0/)</span></span>

### <a name="ranges-and-indices"></a><span data-ttu-id="efb5a-121">범위 및 인덱스</span><span class="sxs-lookup"><span data-stu-id="efb5a-121">Ranges and indices</span></span>

<span data-ttu-id="efb5a-122">새 `Index` 형식을 인덱싱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-122">The new `Index` type can be used for indexing.</span></span> <span data-ttu-id="efb5a-123">시작부터 계산되는 `int`의 인덱스를 만들거나, 접두사 `^` 연산자(C#)를 사용하여 끝부터 계산되는 인덱스를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-123">You can create one from an `int` that counts from the beginning, or with a prefix `^` operator (C#) that counts from the end:</span></span>

```csharp
Index i1 = 3;  // number 3 from beginning
Index i2 = ^4; // number 4 from end
int[] a = { 0, 1, 2, 3, 4, 5, 6, 7, 8, 9 };
Console.WriteLine($"{a[i1]}, {a[i2]}"); // "3, 6"
```

<span data-ttu-id="efb5a-124">시작 인덱스와 끝 인덱스의 두 `Index` 값으로 구성되고 `x..y` 범위 식(C#)으로 작성할 수 있는 `Range` 유형도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-124">There is also a `Range` type, which consists of two `Index` values, one for the start and one for the end, and can be written with a `x..y` range expression (C#).</span></span> <span data-ttu-id="efb5a-125">조각을 생성하기 위해 `Range`를 사용하여 인덱싱할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-125">You can then index with a `Range` in order to produce a slice:</span></span>

```csharp
var slice = a[i1..i2]; // { 3, 4, 5 }
```

### <a name="async-streams"></a><span data-ttu-id="efb5a-126">비동기 스트림</span><span class="sxs-lookup"><span data-stu-id="efb5a-126">Async streams</span></span>

<span data-ttu-id="efb5a-127">`IAsyncEnumerable<T>` 형식은 `IEnumerable<T>`의 새로운 비동기 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-127">The `IAsyncEnumerable<T>` type is a new asynchronous version of `IEnumerable<T>`.</span></span> <span data-ttu-id="efb5a-128">이 언어를 사용하면 `IAsyncEnumerable<T>`을 통해 `await foreach`를 수행하여 요소를 사용하고 `yield return`을 사용하여 요소를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-128">The language lets you `await foreach` over `IAsyncEnumerable<T>` to consume their elements, and use `yield return` to them to produce elements.</span></span>

<span data-ttu-id="efb5a-129">다음 예제에서는 비동기 스트림의 생성 및 사용을 둘 다 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-129">The following example demonstrates both production and consumption of async streams.</span></span> <span data-ttu-id="efb5a-130">`foreach` 문은 비동기이며, `yield return`을 사용하여 호출자에 대한 비동기 스트림을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-130">The `foreach` statement is async and itself uses `yield return` to produce an async stream for callers.</span></span> <span data-ttu-id="efb5a-131">이 패턴(`yield return` 사용)은 비동기 스트림 생성을 위한 권장 모델입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-131">This pattern (using `yield return`) is the recommended model for producing async streams.</span></span>

```csharp
async IAsyncEnumerable<int> GetBigResultsAsync()
{
    await foreach (var result in GetResultsAsync())
    {
        if (result > 20) yield return result;
    }
}
```

<span data-ttu-id="efb5a-132">`await foreach`를 수행할 수 있을 뿐 아니라, 비동기 반복기(예: `await` 및 `yield`가 둘 다 가능한 `IAsyncEnumerable/IAsyncEnumerator`를 반환하는 반복기)를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-132">In addition to being able to `await foreach`, you can also create async iterators, for example, an iterator that returns an `IAsyncEnumerable/IAsyncEnumerator` that you can both `await` and `yield` in.</span></span> <span data-ttu-id="efb5a-133">삭제해야 하는 개체의 경우 `Stream` 및 `Timer`와 같은 다양한 BCL 유형이 구현하는 `IAsyncDisposable`을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-133">For objects that need to be disposed, you can use `IAsyncDisposable`, which various BCL types implement, such as `Stream` and `Timer`.</span></span>

> [!NOTE]
> <span data-ttu-id="efb5a-134">Visual Studio 2019 또는 [Visual Studio Code의 C# 확장](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5)의 최신 미리 보기를 사용하여 개발하려는 경우, 비동기식 스트림을 사용하려면 .NET Core 3.0 미리 보기 2가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-134">You need .NET Core 3.0 Preview 2 to use async streams if you want to develop with either Visual Studio 2019 or the latest preview of the [C# extension for Visual Studio Code](https://github.com/OmniSharp/omnisharp-vscode/releases/tag/v1.18.0-beta5).</span></span> <span data-ttu-id="efb5a-135">명령줄에서 .NET Core 3.0 Preview 2를 사용하는 경우에는, 모든 것이 예상대로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-135">If you are using .NET Core 3.0 Preview 2 at the command line, then everything will work as expected.</span></span>

### <a name="using-declarations"></a><span data-ttu-id="efb5a-136">Using 선언</span><span class="sxs-lookup"><span data-stu-id="efb5a-136">Using Declarations</span></span>

<span data-ttu-id="efb5a-137">*using* 선언은 개체가 제대로 처리되도록 하는 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-137">*Using declarations* are a new way to ensure your object is properly disposed.</span></span> <span data-ttu-id="efb5a-138">*using*을 선언하면 개체가 범위 내에 있는 동안 개체가 활성 상태로 유지됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-138">A *using declaration* keeps the object alive while it is still in scope.</span></span> <span data-ttu-id="efb5a-139">개체가 범위를 벗어나면 자동으로 삭제됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-139">Once the object becomes out of scope, it is automatically disposed.</span></span> <span data-ttu-id="efb5a-140">이렇게 하면 중첩된 *using* 문이 줄어들고 코드가 보다 명확해집니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-140">This will reduce nested *using statements* and make your code cleaner.</span></span>

```csharp
static void Main(string[] args)
{
    using var options = Parse(args);
    if (options["verbose"]) { WriteLine("Logging..."); }

} // options disposed here
```

### <a name="switch-expressions"></a><span data-ttu-id="efb5a-141">Switch 식</span><span class="sxs-lookup"><span data-stu-id="efb5a-141">Switch Expressions</span></span>

<span data-ttu-id="efb5a-142">*switch* 식은 *switch* 문을 수행하는 명확한 방법이지만 식이기 때문에 값이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-142">*Switch expressions* are a cleaner way of doing a *switch statement* but, since it's an expression, returns a value.</span></span> <span data-ttu-id="efb5a-143">*switch* 식은 패턴 매칭과 완전히 통합되어 있으며, 무시 패턴(`_`)을 사용하여 `default` 값을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-143">*Switch expressions* are also fully integrated with pattern matching, and use the discard pattern, `_`, to represent the `default` value.</span></span>

<span data-ttu-id="efb5a-144">*switch* 식에 대한 구문은 다음 예제에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-144">You can see the syntax for *switch expressions* in the following example:</span></span>

```csharp
static string Display(object o) => o switch
{
    Point { X: 0, Y: 0 }         => "origin",
    Point { X: var x, Y: var y } => $"({x}, {y})",
    _                            => "unknown"
};
```

<span data-ttu-id="efb5a-145">이 예제에는 두 가지 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-145">There are two patterns at play in this example.</span></span> <span data-ttu-id="efb5a-146">`o`은(는) 먼저 `Point` 형식 패턴과 매칭한 다음, {중괄호} 내부의 속성 패턴과 매칭합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-146">`o` first matches with the `Point` *type pattern* and then with the *property pattern* inside the *{curly braces}*.</span></span> <span data-ttu-id="efb5a-147">`_`은 *switch* 문에 대한 `default`와 동일한 `discard pattern`을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-147">The `_` describes the `discard pattern`, which is the same as `default` for *switch statements*.</span></span>

<span data-ttu-id="efb5a-148">패턴을 사용하면 테스트를 구현하는 프로시저 코드 대신 의도를 캡처하는 선언적 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-148">Patterns enable you to write declarative code that captures your intent instead of procedural code that implements tests for it.</span></span> <span data-ttu-id="efb5a-149">지루한 프로시저 코드를 구현할 책임이 컴파일러에 있고, 항상 제대로 수행하도록 보장됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-149">The compiler becomes responsible for implementing that boring procedural code and is guaranteed to always do it correctly.</span></span>

<span data-ttu-id="efb5a-150">*switch* 문이 *switch* 식보다 더 나은 선택이 되는 경우가 있고, 패턴이 두 구문 스타일 모두에 사용되는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-150">There will still be cases where *switch statements* will be a better choice than *switch expressions* and patterns can be used with both syntax styles.</span></span>

<span data-ttu-id="efb5a-151">자세한 내용은 [Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/)(C# 8.0으로 더 많은 패턴 작업 수행)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-151">For more information, see [Do more with patterns in C# 8.0](https://devblogs.microsoft.com/dotnet/do-more-with-patterns-in-c-8-0/).</span></span>

## <a name="ieee-floating-point-improvements"></a><span data-ttu-id="efb5a-152">IEEE 부동 소수점 개선 사항</span><span class="sxs-lookup"><span data-stu-id="efb5a-152">IEEE Floating-point improvements</span></span>

<span data-ttu-id="efb5a-153">부동 소수점 API는 [IEEE 754-2008 개정판](https://en.wikipedia.org/wiki/IEEE_754-2008_revision)을 준수하도록 업데이트되고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-153">Floating point APIs are in the process of being updated to comply with [IEEE 754-2008 revision](https://en.wikipedia.org/wiki/IEEE_754-2008_revision).</span></span> <span data-ttu-id="efb5a-154">이러한 변경의 목표는 "필요한" 모든 작업을 노출하고 이 작업이 IEEE 사양을 준수하는지 확인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-154">The goal of these changes is to expose all "required" operations and ensure that they are behaviorally compliant with the IEEE spec.</span></span>

<span data-ttu-id="efb5a-155">구문 분석 및 서식 지정 개선 사항:</span><span class="sxs-lookup"><span data-stu-id="efb5a-155">Parsing and formatting fixes:</span></span>

* <span data-ttu-id="efb5a-156">모든 길이의 입력을 올바르게 구문 분석하고 반올림합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-156">Correctly parse and round inputs of any length.</span></span>
* <span data-ttu-id="efb5a-157">음수 0을 올바르게 구문 분석하고 형식을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-157">Correctly parse and format negative zero.</span></span>
* <span data-ttu-id="efb5a-158">대/소문자를 구분하지 않는 검사를 수행하여 Infinity와 NaN을 올바르게 구문 분석하고, 적용 가능한 경우 선행 `+` 옵션을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-158">Correctly parse Infinity and NaN by performing a case-insensitive check and allowing an optional preceding `+` where applicable.</span></span>

<span data-ttu-id="efb5a-159">새로운 Math API에 포함된 사항:</span><span class="sxs-lookup"><span data-stu-id="efb5a-159">New Math APIs have:</span></span>

* `BitIncrement/BitDecrement`\
<span data-ttu-id="efb5a-160">`nextUp` 및 `nextDown` IEEE 연산에 해당합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-160">Corresponds to the `nextUp` and `nextDown` IEEE operations.</span></span> <span data-ttu-id="efb5a-161">입력보다 크거나 작은 값을 각각 비교하는 최소 부동 소수점 숫자를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-161">They return the smallest floating-point number that compares greater or lesser than the input (respectively).</span></span> <span data-ttu-id="efb5a-162">예를 들어 `Math.BitIncrement(0.0)`는 `double.Epsilon`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-162">For example, `Math.BitIncrement(0.0)` would return `double.Epsilon`.</span></span>

* `MaxMagnitude/MinMagnitude`\
<span data-ttu-id="efb5a-163">`maxNumMag` 및 `minNumMag` IEEE 연산에 해당하며 두 입력의 규모 중 더 크거나 작은 값을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-163">Corresponds to the `maxNumMag` and `minNumMag` IEEE operations, they return the value that is greater or lesser in magnitude of the two inputs (respectively).</span></span> <span data-ttu-id="efb5a-164">예를 들어 `Math.MaxMagnitude(2.0, -3.0)`는 `-3.0`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-164">For example, `Math.MaxMagnitude(2.0, -3.0)` would return `-3.0`.</span></span>

* `ILogB`\
<span data-ttu-id="efb5a-165">`logB` IEEE 연산에 해당하며 정수값을 반환하고, 입력 매개 변수의 정수 기분-2 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-165">Corresponds to the `logB` IEEE operation which returns an integral value, it returns the integral base-2 log of the input parameter.</span></span> <span data-ttu-id="efb5a-166">`floor(log2(x))`와 사실상 동일하지만 반올림 오류를 최소화하면서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-166">This is effectively the same as `floor(log2(x))`, but done with minimal rounding error.</span></span>

* `ScaleB`\
<span data-ttu-id="efb5a-167">정수 값을 취하는 `scaleB` IEEE 연산에 해당하며 사실상 `x * pow(2, n)`을 반환하지만 반올림 오류를 최소화하면서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-167">Corresponds to the `scaleB` IEEE operation which takes an integral value, it returns effectively `x * pow(2, n)`, but is done with minimal rounding error.</span></span>

* `Log2`\
<span data-ttu-id="efb5a-168">`log2` IEEE 연산에 해당하며, 기본-2 로그를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-168">Corresponds to the `log2` IEEE operation, it returns the base-2 logarithm.</span></span> <span data-ttu-id="efb5a-169">반올림 오류를 최소화합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-169">It minimizes rounding error.</span></span>

* `FusedMultiplyAdd`\
<span data-ttu-id="efb5a-170">`fma` IEEE 연산에 해당하며, 단일 곱셈 누산기(fused multiply add) 계산을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-170">Corresponds to the `fma` IEEE operation, it performs a fused multiply add.</span></span> <span data-ttu-id="efb5a-171">다시 말해, `(x * y) + z`를 단일 연산으로 수행하기 때문에 반올림 오류가 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-171">That is, it does `(x * y) + z` as a single operation, there-by minimizing the rounding error.</span></span> <span data-ttu-id="efb5a-172">예를 들어 `FusedMultiplyAdd(1e308, 2.0, -1e308)`는 `1e308`을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-172">An example would be `FusedMultiplyAdd(1e308, 2.0, -1e308)` which returns `1e308`.</span></span> <span data-ttu-id="efb5a-173">일반 `(1e308 * 2.0) - 1e308`은 `double.PositiveInfinity`를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-173">The regular `(1e308 * 2.0) - 1e308` returns `double.PositiveInfinity`.</span></span>

* `CopySign`\
<span data-ttu-id="efb5a-174">`copySign` IEEE 연산에 해당하며, `x`의 값을 반환하지만 `y`의 부호를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-174">Corresponds to the `copySign` IEEE operation, it returns the value of `x`, but with the sign of `y`.</span></span>

## <a name="net-platform-dependent-intrinsics"></a><span data-ttu-id="efb5a-175">.NET 플랫폼 종속 내장 함수</span><span class="sxs-lookup"><span data-stu-id="efb5a-175">.NET Platform Dependent Intrinsics</span></span>

<span data-ttu-id="efb5a-176">**SIMD** 또는 **비트 조작 명령어** 세트와 같은 특정 perf-oriented CPU 명령어에 대한 액세스를 허용하는 API가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-176">APIs have been added that allow access to certain perf-oriented CPU instructions, such as the **SIMD** or **Bit Manipulation instruction** sets.</span></span> <span data-ttu-id="efb5a-177">이러한 명령어를 사용하면 특정 시나리오(효율적인 데이터 병렬 처리)에서 성능을 크게 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-177">These instructions can help achieve big performance improvements in certain scenarios, such as processing data efficiently in parallel.</span></span> <span data-ttu-id="efb5a-178">.NET 라이브러리는 프로그램에서 사용할 API를 노출하는 것 외에도 이러한 명령어를 사용하여 성능을 향상시키기 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-178">In addition to exposing the APIs for your programs to use, the .NET libraries have begun using these instructions to improve performance.</span></span>

<span data-ttu-id="efb5a-179">다음 CoreCLR PR은 구현 또는 사용을 통해 몇 가지 내장 함수를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-179">The following CoreCLR PRs demonstrate a few of the intrinsics, either via implementation or use:</span></span>

* <span data-ttu-id="efb5a-180">[Implement simple SSE2 hardware intrinsics](https://github.com/dotnet/coreclr/pull/15585)(간단한 SSE2 하드웨어 내장 함수 구현)</span><span class="sxs-lookup"><span data-stu-id="efb5a-180">[Implement simple SSE2 hardware intrinsics](https://github.com/dotnet/coreclr/pull/15585)</span></span>
* <span data-ttu-id="efb5a-181">[Implement the SSE hardware intrinsics](https://github.com/dotnet/coreclr/pull/15538)(SSE 하드웨어 내장 함수 구현)</span><span class="sxs-lookup"><span data-stu-id="efb5a-181">[Implement the SSE hardware intrinsics](https://github.com/dotnet/coreclr/pull/15538)</span></span>
* <span data-ttu-id="efb5a-182">[Arm64 Base HW Intrinsics](https://github.com/dotnet/coreclr/pull/16822)(Arm64 Base HW 내장 함수)</span><span class="sxs-lookup"><span data-stu-id="efb5a-182">[Arm64 Base HW Intrinsics](https://github.com/dotnet/coreclr/pull/16822)</span></span>
* <span data-ttu-id="efb5a-183">[Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}](https://github.com/dotnet/coreclr/pull/21073)(Locate{First|Last}Found{Byte|Char}에 TZCNT 및 LZCNT 사용)</span><span class="sxs-lookup"><span data-stu-id="efb5a-183">[Use TZCNT and LZCNT for Locate{First|Last}Found{Byte|Char}](https://github.com/dotnet/coreclr/pull/21073)</span></span>

<span data-ttu-id="efb5a-184">자세한 내용은 [.NET 플랫폼 종속 내장 함수](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md)를 참조하세요. 여기에는 하드웨어 인프라를 정의하고, Microsoft, 칩 공급 업체나 기타 회사 또는 개인이 .NET 코드에 노출되어야 하는 하드웨어/칩 API를 정의할 수 있는 방법이 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-184">For more information, see [.NET Platform Dependent Intrinsics](https://github.com/dotnet/designs/blob/master/accepted/platform-intrinsics.md), which defines an approach for defining this hardware infrastructure, allowing Microsoft, chip vendors, or any other company or individual to define hardware/chip APIs that should be exposed to .NET code.</span></span>

## <a name="default-executables"></a><span data-ttu-id="efb5a-185">기본 실행 파일</span><span class="sxs-lookup"><span data-stu-id="efb5a-185">Default executables</span></span>

<span data-ttu-id="efb5a-186">이제 .NET Core에서 기본적으로 [프레임워크 종속 실행 파일](../deploying/index.md#framework-dependent-executables-fde)을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-186">.NET Core will now build [framework-dependent executables](../deploying/index.md#framework-dependent-executables-fde) by default.</span></span> <span data-ttu-id="efb5a-187">이는 전역으로 설치된 .NET Core 버전을 사용하는 애플리케이션을 위한 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-187">This is new for applications that use a globally installed version of .NET Core.</span></span> <span data-ttu-id="efb5a-188">지금까지는 [자체 포함 배포](../deploying/index.md#self-contained-deployments-scd)만 실행 파일을 생성했습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-188">Until now, only [self-contained deployments](../deploying/index.md#self-contained-deployments-scd) would produce an executable.</span></span>

<span data-ttu-id="efb5a-189">사용 중인 SDK의 환경 및 플랫폼과 일치하는 경우 `dotnet build` 또는 `dotnet publish` 중에 실행 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-189">During `dotnet build` or `dotnet publish`, an executable is created provided that matches the environment and platform of the SDK you are using.</span></span> <span data-ttu-id="efb5a-190">다른 네이티브 실행 파일과 마찬가지로 이러한 실행 파일에서도 다음과 같은 동일한 기능을 예상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-190">You can expect the same things with these executables as you would other native executables, such as:</span></span>

* <span data-ttu-id="efb5a-191">실행 파일을 두 번 클릭할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-191">You can double-click on the executable.</span></span>
* <span data-ttu-id="efb5a-192">Windows의 `myapp.exe`, Linux 및 macOS의 `./myapp`과 같은 애플리케이션을 명령 프롬프트에서 직접 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-192">You can launch the application from a command prompt directly, such as `myapp.exe` on Windows, and `./myapp` on Linux and macOS.</span></span>

## <a name="build-copies-dependencies"></a><span data-ttu-id="efb5a-193">빌드 복사본 종속성</span><span class="sxs-lookup"><span data-stu-id="efb5a-193">Build copies dependencies</span></span>

<span data-ttu-id="efb5a-194">이제 `dotnet build`가 애플리케이션에 대한 NuGet 종속성을 NuGet 캐시에서 빌드 출력 폴더로 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-194">`dotnet build` now copies NuGet dependencies for your application from the NuGet cache to the build output folder.</span></span> <span data-ttu-id="efb5a-195">이전에는 종속성이 `dotnet publish` 중에만 복사되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-195">Previously, dependencies were only copied as part of `dotnet publish`.</span></span>

<span data-ttu-id="efb5a-196">연결, Razor 페이지 게시 등 여전히 게시해야 하는 일부 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-196">There are some operations, like linking and razor page publishing that will still require publishing.</span></span>

## <a name="local-dotnet-tools"></a><span data-ttu-id="efb5a-197">로컬 dotnet 도구</span><span class="sxs-lookup"><span data-stu-id="efb5a-197">Local dotnet tools</span></span>

> [!WARNING]
> <span data-ttu-id="efb5a-198">.NET Core Local Tools가 .NET Core 3.0 Preview 1과 .NET Core 3.0 Preview 2 사이에 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-198">There was a change in .NET Core Local Tools between .NET Core 3.0 Preview 1 and .NET Core 3.0 Preview 2.</span></span>  <span data-ttu-id="efb5a-199">`dotnet tool restore` 또는 `dotnet tool install`와 같은 명령을 실행하여 Preview 1의 로컬 도구를 사용한 적이 있으면, 로컬 도구 캐시 폴더를 삭제해야 Preview 2에서 로컬 도구가 제대로 작동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-199">If you tried out local tools in Preview 1 by running a command like `dotnet tool restore` or `dotnet tool install`, you need to delete your local tools cache folder before local tools will work correctly in Preview 2.</span></span> <span data-ttu-id="efb5a-200">이 폴더의 위치는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-200">This folder is located at:</span></span>
>
> <span data-ttu-id="efb5a-201">mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="efb5a-201">On mac, Linux: `rm -r $HOME/.dotnet/toolResolverCache`</span></span>
>
> <span data-ttu-id="efb5a-202">Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span><span class="sxs-lookup"><span data-stu-id="efb5a-202">On Windows: `rmdir /s %USERPROFILE%\.dotnet\toolResolverCache`</span></span>
>
> <span data-ttu-id="efb5a-203">이 폴더를 삭제하지 않으면 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-203">If you do not delete this folder, you will receive an error.</span></span>

<span data-ttu-id="efb5a-204">.NET Core 2.1은 전역 도구를 지원한 한편, .NET Core 3.0은 이제 로컬 도구를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-204">While .NET Core 2.1 supported global tools, .NET Core 3.0 now has local tools.</span></span> <span data-ttu-id="efb5a-205">로컬 도구는 전역 도구와 유사하지만 디스크의 특정 위치와 연결됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-205">Local tools are similar to global tools but are associated with a particular location on disk.</span></span> <span data-ttu-id="efb5a-206">이를 통해 프로젝트별 및 리포지토리별 도구를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-206">This enables per-project and per-repository tooling.</span></span> <span data-ttu-id="efb5a-207">로컬로 설치된 도구는 전역으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-207">Any tool installed locally isn't available globally.</span></span> <span data-ttu-id="efb5a-208">도구는 NuGet 패키지로 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-208">Tools are distributed as NuGet packages.</span></span>

<span data-ttu-id="efb5a-209">로컬 도구는 현재 디렉터리에 있는 매니페스트 파일 이름 `dotnet-tools.json`을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-209">Local tools rely on a manifest file name `dotnet-tools.json` in your current directory.</span></span> <span data-ttu-id="efb5a-210">이 매니페스트 파일은 해당 폴더 및 그 아래에서 사용할 수 있는 도구를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-210">This manifest file defines the tools to be available at that folder and below.</span></span> <span data-ttu-id="efb5a-211">리포지토리 루트에 이 매니페스트 파일을 만들면 코드를 복제하는 누구든지 성공적인 코드 작업에 필요한 도구를 복원하고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-211">By creating this manifest file at the root of your repository, you ensure anyone cloning your code can restore and use the tools that are needed to successfully work with your code.</span></span>

<span data-ttu-id="efb5a-212">`dotnet-tools.json` 매니페스트 파일을 만들려면, 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-212">To create a `dotnet-tools.json` manifest file, use:</span></span>

```console
dotnet new tool-manifest
```

<span data-ttu-id="efb5a-213">다음을 사용하여 로컬 매니페스트에 새 도구를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-213">Add a new tool to the local manifest with:</span></span>

```console
dotnet tool install <packageId>
```

<span data-ttu-id="efb5a-214">다음을 사용하여 로컬 매니페스트의 도구를 나열할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-214">You can also list the tools in the local manifest with:</span></span>

```console
dotnet tool list
```

<span data-ttu-id="efb5a-215">어떤 도구가 전역적으로 설치되어 있는지 보려면 다음을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-215">To see what tools are installed globally, use:</span></span>

```console
dotnet tool list -g
```

<span data-ttu-id="efb5a-216">로컬 도구 매니페스트 파일을 사용할 수 있지만 매니페스트에 정의된 도구가 설치되어 있지 않으면 다음 명령을 사용하여 해당 도구를 자동으로 다운로드하고 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-216">When the local tools manifest file is available, but the tools defined in the manifest have not been installed, use the following command to automatically download and install those tools:</span></span>

```console
dotnet tool restore
```

<span data-ttu-id="efb5a-217">다음 명령을 사용하여 로컬 도구를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-217">Run a local tool with the following command:</span></span>

```console
dotnet tool run <tool-command-name>
```

<span data-ttu-id="efb5a-218">로컬 도구가 실행되면 dotnet은 현재 디렉터리 구조 위로 매니페스트를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-218">When a local tool is run, dotnet searches for a manifest up the current directory structure.</span></span> <span data-ttu-id="efb5a-219">도구 매니페스트 파일이 있으면 해당 파일에서 요청된 도구를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-219">When a tool manifest file is found, it is searched for the requested tool.</span></span> <span data-ttu-id="efb5a-220">도구가 매니페스트에서 발견되었지만 캐시에 없는 경우 사용자에게 오류가 표시되고 `dotnet tool restore`를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-220">If the tool is found in the manifest, but not the cache, the user receives an error and needs to run `dotnet tool restore`.</span></span>

<span data-ttu-id="efb5a-221">로컬 도구 매니페스트 파일에서 도구를 제거하려면 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-221">To remove a tool from the local tool manifest file, run the following command:</span></span>

```console
dotnet tool uninstall <packageId>
```

<span data-ttu-id="efb5a-222">도구 매니페스트 파일은 리포지토리 작업에 필요한 버전 업데이트 등을 위한 수동 편집을 허용하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-222">The tool manifest file is designed to allow hand editing – which you might do to update the required version for working with the repository.</span></span> <span data-ttu-id="efb5a-223">예제 `dotnet-tools.json` 파일은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-223">Here is an example `dotnet-tools.json` file:</span></span>

```json
{
  "version": 1,
  "isRoot": true,
  "tools": {
    "dotnetsay": {
      "version": "2.1.4",
      "commands": [
        "dotnetsay"
      ]
    },
    "t-rex": {
      "version": "1.0.103",
      "commands": [
        "t-rex"
      ]
    }
  }
}
```

<span data-ttu-id="efb5a-224">전역 도구와 로컬 도구 둘 다, 호환되는 버전의 런타임이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-224">For both global and local tools, a compatible version of the runtime is required.</span></span> <span data-ttu-id="efb5a-225">현재 NuGet.org의 많은 도구는 .NET Core 런타임 2.1을 대상으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-225">Many tools currently on NuGet.org target .NET Core Runtime 2.1.</span></span> <span data-ttu-id="efb5a-226">이러한 도구를 전역 또는 로컬로 설치하려면 여전히 [NET Core 2.1 런타임](https://dotnet.microsoft.com/download/dotnet-core/2.1)을 설치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-226">To install those globally or locally, you would still need to install the [NET Core 2.1 Runtime](https://dotnet.microsoft.com/download/dotnet-core/2.1).</span></span>

## <a name="windows-desktop"></a><span data-ttu-id="efb5a-227">Windows 바탕 화면</span><span class="sxs-lookup"><span data-stu-id="efb5a-227">Windows desktop</span></span>

<span data-ttu-id="efb5a-228">.NET Core 3.0 Preview 1부터 WPF 및 Windows Forms를 사용하여 Windows 데스크톱 애플리케이션을 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-228">Starting with .NET Core 3.0 Preview 1, you can build Windows desktop applications using WPF and Windows Forms.</span></span> <span data-ttu-id="efb5a-229">이러한 프레임워크는 [XAML 아일랜드](/windows/uwp/xaml-platform/xaml-host-controls)를 통해 Windows UI XAML 라이브러리(WinUI)의 최신 컨트롤 및 Fluent 스타일을 사용하는 것도 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-229">These frameworks also support using modern controls and Fluent styling from the Windows UI XAML Library (WinUI) via [XAML islands](/windows/uwp/xaml-platform/xaml-host-controls).</span></span>

<span data-ttu-id="efb5a-230">Windows 데스크톱 구성 요소는 Windows .NET Core 3.0 SDK의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-230">The Windows Desktop component is part of the Windows .NET Core 3.0 SDK.</span></span>

<span data-ttu-id="efb5a-231">다음 `dotnet` 명령을 사용하여 새 WPF 또는 Windows Forms 앱을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-231">You can create a new WPF or Windows Forms app with the following `dotnet` commands:</span></span>

```console
dotnet new wpf
dotnet new winforms
```

<span data-ttu-id="efb5a-232">Visual Studio 2019에는 .NET Core 3.0 Windows Forms 및 WPF용 **새 프로젝트** 템플릿이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-232">Visual Studio 2019 adds **New Project** templates for .NET Core 3.0 Windows Forms and WPF.</span></span> <span data-ttu-id="efb5a-233">디자이너는 아직 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-233">Designers are still not yet supported.</span></span> <span data-ttu-id="efb5a-234">Visual Studio 2019에서 이러한 프로젝트를 열고 시작하고 디버그할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-234">And you can open, launch, and debug these projects in Visual Studio 2019.</span></span>

<span data-ttu-id="efb5a-235">Visual Studio 2017 15.9에서는 [.NET Core 미리 보기를 활성화](https://devblogs.microsoft.com/dotnet/net-core-tooling-update-for-visual-studio-2017-version-15-9/)하는 기능이 추가되었지만 해당 기능을 켜야 하며, 이 시나리오는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-235">Visual Studio 2017 15.9 adds the ability to [enable .NET Core previews](https://devblogs.microsoft.com/dotnet/net-core-tooling-update-for-visual-studio-2017-version-15-9/), but you need to turn that feature on, and it's not a supported scenario.</span></span>

<span data-ttu-id="efb5a-236">새 프로젝트는 몇 가지 내용만 추가되고, 기존 .NET Core 프로젝트와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-236">The new projects are the same as existing .NET Core projects, with a couple additions.</span></span> <span data-ttu-id="efb5a-237">기본 .NET Core 콘솔 프로젝트와 기본 Windows Forms 및 WPF 프로젝트의 비교는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-237">Here is the comparison of the basic .NET Core console project and a basic Windows Forms and WPF project.</span></span>

<span data-ttu-id="efb5a-238">.NET Core 콘솔 프로젝트에서 프로젝트는 `Microsoft.NET.Sdk` SDK를 사용하고 `netcoreapp3.0` 대상 프레임워크를 통해 .NET Core 3.0에 대한 종속성을 선언합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-238">In a .NET Core console project, the project uses the `Microsoft.NET.Sdk` SDK and declares a dependency on .NET Core 3.0 via the `netcoreapp3.0` target framework.</span></span> <span data-ttu-id="efb5a-239">Windows 데스크톱 앱을 만들려면 `Microsoft.NET.Sdk.WindowsDesktop` SDK를 사용하고, 사용할 UI 프레임워크를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-239">To create a Windows Desktop app, use the `Microsoft.NET.Sdk.WindowsDesktop` SDK and choose which UI framework to use:</span></span>

```diff
-<Project Sdk="Microsoft.NET.Sdk">
+<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
+   <UseWPF>true</UseWPF>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="efb5a-240">WPF가 아닌 Windows Forms를 선택하려면 `UseWPF` 대신 `UseWindowsForms`를 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-240">To choose Windows Forms over WPF, set `UseWindowsForms` instead of `UseWPF`:</span></span>

```diff
<Project Sdk="Microsoft.NET.Sdk.WindowsDesktop">
  <PropertyGroup>
    <OutputType>Exe</OutputType>
    <TargetFramework>netcoreapp3.0</TargetFramework>
-   <UseWPF>true</UseWPF>
+   <UseWindowsForms>true</UseWindowsForms>
  </PropertyGroup>
</Project>
```

<span data-ttu-id="efb5a-241">앱이 두 프레임워크를 모두 사용하는 경우(예: Windows Forms 대화 상자에서 WPF 컨트롤을 호스트하는 경우) `UseWPF` 및 `UseWindowsForms`를 둘 다 `true`로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-241">Both `UseWPF` and `UseWindowsForms` can be set to `true` if the app uses both frameworks, for example when a Windows Forms dialog is hosting a WPF control.</span></span>

<span data-ttu-id="efb5a-242">[dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) 및 [dotnet/core](https://github.com/dotnet/core/issues) 리포지토리에서 피드백을 공유하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-242">Please share your feedback on the [dotnet/winforms](https://github.com/dotnet/winforms/issues),  [dotnet/wpf](https://github.com/dotnet/wpf/issues) and [dotnet/core](https://github.com/dotnet/core/issues) repos.</span></span>

## <a name="msix-deployment-for-windows-desktop"></a><span data-ttu-id="efb5a-243">Windows 데스크톱용 MSIX 배포</span><span class="sxs-lookup"><span data-stu-id="efb5a-243">MSIX Deployment for Windows Desktop</span></span>

<span data-ttu-id="efb5a-244">[MSIX](https://docs.microsoft.com/windows/msix/)는 새로운 Windows 앱 패키지 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-244">[MSIX](https://docs.microsoft.com/windows/msix/) is a new Windows app package format.</span></span> <span data-ttu-id="efb5a-245">Windows 10에 .NET Core 3.0 데스크톱 애플리케이션을 배포하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-245">It can be used to deploy .NET Core 3.0 desktop applications to Windows 10.</span></span>

<span data-ttu-id="efb5a-246">Visual Studio 2019에 제공되는 [Windows 애플리케이션 패키징 프로젝트](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net)를 사용하면 [자체 포함](../deploying/index.md#self-contained-deployments-scd) .NET Core 애플리케이션을 사용하여 MSIX 패키지를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-246">The [Windows Application Packaging Project](https://docs.microsoft.com/windows/uwp/porting/desktop-to-uwp-packaging-dot-net), available in Visual Studio 2019, allows you to create MSIX packages with [self-contained](../deploying/index.md#self-contained-deployments-scd) .NET Core applications.</span></span>

> [!NOTE]
> <span data-ttu-id="efb5a-247">NET Core 프로젝트 파일은 `<RuntimeIdentifiers>` 속성에 지원되는 런타임을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-247">The .NET Core project file must specify the supported runtimes in the `<RuntimeIdentifiers>` property:</span></span>
>
> ```xml
> <RuntimeIdentifiers>win-x86;win-x64</RuntimeIdentifiers>
> ```

## <a name="fast-built-in-json-support"></a><span data-ttu-id="efb5a-248">빠른 기본 제공 JSON 지원</span><span class="sxs-lookup"><span data-stu-id="efb5a-248">Fast built-in JSON support</span></span>

<span data-ttu-id="efb5a-249">.NET 에코시스템은 [**Json.NET**](https://www.newtonsoft.com/json) 및 여전히 유용한 기타 인기 있는 JSON 라이브러리를 사용해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-249">The .NET ecosystem has relied on [**Json.NET**](https://www.newtonsoft.com/json) and other popular JSON libraries, which continue to be good choices.</span></span> <span data-ttu-id="efb5a-250">**Json.NET**은 내부적으로 UTF-16인 .NET 문자열을 기본 데이터 형식으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-250">**Json.NET** uses .NET strings as its base datatype, which are UTF-16 under the hood.</span></span>

<span data-ttu-id="efb5a-251">새로 기본 제공되는 JSON 지원은 성능이 높고, 할당이 낮으며 `Span<byte>`를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-251">The new built-in JSON support is high-performance, low allocation, and based on `Span<byte>`.</span></span> <span data-ttu-id="efb5a-252">.NET Core 3.0 `System.Text.Json` 네임스페이스에 세 가지 주요 JSON 관련 형식이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-252">Three new main JSON-related types have been added to .NET Core 3.0 the `System.Text.Json` namespace.</span></span>

### <a name="utf8jsonreader"></a><span data-ttu-id="efb5a-253">Utf8JsonReader</span><span class="sxs-lookup"><span data-stu-id="efb5a-253">Utf8JsonReader</span></span>

<span data-ttu-id="efb5a-254">`System.Text.Json.Utf8JsonReader`는 `ReadOnlySpan<byte>`에서 읽어온 UTF-8 인코드된 JSON 텍스트를 위한 고성능, 저할당, 전달 전용 판독기입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-254">`System.Text.Json.Utf8JsonReader` is a high-performance, low allocation, forward-only reader for UTF-8 encoded JSON text, read from a `ReadOnlySpan<byte>`.</span></span> <span data-ttu-id="efb5a-255">`Utf8JsonReader`는 사용자 지정 구문 분석기 및 역직렬 변환기를 빌드하는 데 활용할 수 있는 하위 수준의 기초 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-255">The `Utf8JsonReader` is a foundational, low-level type, that can be leveraged to build custom parsers and deserializers.</span></span> <span data-ttu-id="efb5a-256">새 `Utf8JsonReader`를 사용하여 JSON 페이로드를 읽을 경우 **Json.NET**의 판독기를 사용하는 것에 비해 2배 더 빠릅니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-256">Reading through a JSON payload using the new `Utf8JsonReader` is 2x faster than using the reader from **Json.NET**.</span></span> <span data-ttu-id="efb5a-257">JSON 토큰을 (UTF-16) 문자열로 실현해야 할 때까지 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-257">It does not allocate until you need to actualize JSON tokens as (UTF-16) strings.</span></span>

<span data-ttu-id="efb5a-258">이 새로운 API에는 다음 구성 요소가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-258">This new API will include the following components:</span></span>

* <span data-ttu-id="efb5a-259">미리 보기 1: JSON 판독기(순차적 액세스)</span><span class="sxs-lookup"><span data-stu-id="efb5a-259">In Preview 1: JSON reader (sequential access)</span></span>
* <span data-ttu-id="efb5a-260">향후 제공 예정: JSON 기록기, DOM(임의 액세스), poco 직렬 변환기, poco 역직렬 변환기</span><span class="sxs-lookup"><span data-stu-id="efb5a-260">Coming next: JSON writer, DOM (random access), poco serializer, poco deserializer</span></span>

<span data-ttu-id="efb5a-261">시작점으로 사용할 수 있는 `Utf8JsonReader`의 기본 판독기 루프는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-261">Here is the basic reader loop for the `Utf8JsonReader` that can be used as a starting point:</span></span>

```csharp
using System.Text.Json;

public static void Utf8JsonReaderLoop(ReadOnlySpan<byte> dataUtf8)
{
    var json = new Utf8JsonReader(dataUtf8, isFinalBlock: true, state: default);

    while (json.Read())
    {
        JsonTokenType tokenType = json.TokenType;
        ReadOnlySpan<byte> valueSpan = json.ValueSpan;
        switch (tokenType)
        {
            case JsonTokenType.StartObject:
            case JsonTokenType.EndObject:
                break;
            case JsonTokenType.StartArray:
            case JsonTokenType.EndArray:
                break;
            case JsonTokenType.PropertyName:
                break;
            case JsonTokenType.String:
                string valueString = json.GetStringValue();
                break;
            case JsonTokenType.Number:
                if (!json.TryGetInt32Value(out int valueInteger))
                {
                    throw new FormatException();
                }
                break;
            case JsonTokenType.True:
            case JsonTokenType.False:
                bool valueBool = json.GetBooleanValue();
                break;
            case JsonTokenType.Null:
                break;
            default:
                throw new ArgumentException();
        }
    }

    dataUtf8 = dataUtf8.Slice((int)json.BytesConsumed);
    JsonReaderState state = json.CurrentState;
}
```

### <a name="utf8jsonwriter"></a><span data-ttu-id="efb5a-262">Utf8JsonWriter</span><span class="sxs-lookup"><span data-stu-id="efb5a-262">Utf8JsonWriter</span></span>

<span data-ttu-id="efb5a-263">`System.Text.Json.Utf8JsonWriter`는 `String`, `Int32` 및 `DateTime`과 같은 일반적인 .NET 형식에서 UTF-8 인코딩 JSON 텍스트를 쓰는 캐시를 사용하지 않고 앞으로만 이동 가능한 고성능의 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-263">`System.Text.Json.Utf8JsonWriter` provides a high-performance, non-cached, forward-only way to write UTF-8 encoded JSON text from common .NET types like `String`, `Int32`, and `DateTime`.</span></span> <span data-ttu-id="efb5a-264">reader와 마찬가지로 writer는 사용자 지정 serializer를 빌드하는 데 활용될 수 있는 기초적인 하위 수준 유형입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-264">Like the reader, the writer is a foundational, low-level type, that can be leveraged to build custom serializers.</span></span> <span data-ttu-id="efb5a-265">새로운 `Utf8JsonWriter`를 사용하여 JSON 페이로드를 작성하면 **Json.NET**의 writer를 사용하는 것보다 30-80% 빠르며 할당하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-265">Writing a JSON payload using the new `Utf8JsonWriter` is 30-80% faster than using the writer from **Json.NET** and does not allocate.</span></span>

<span data-ttu-id="efb5a-266">다음은 시작점으로 사용할 수 있는 `Utf8JsonWriter`의 샘플 사용법입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-266">Here is a sample usage of the `Utf8JsonWriter` that can be used as a starting point:</span></span>

```csharp
static int WriteJson(IBufferWriter<byte> output, long[] extraData)
{
    var json = new Utf8JsonWriter(output, state: default);

    json.WriteStartObject();

    json.WriteNumber("age", 15, escape: false);
    json.WriteString("date", DateTime.Now);
    json.WriteString("first", "John");
    json.WriteString("last", "Smith");

    json.WriteStartArray("phoneNumbers", escape: false);
    json.WriteStringValue("425-000-1212", escape: false);
    json.WriteStringValue("425-000-1213");
    json.WriteEndArray();

    json.WriteStartObject("address");
    json.WriteString("street", "1 Microsoft Way");
    json.WriteString("city", "Redmond");
    json.WriteNumber("zip", 98052);
    json.WriteEndObject();

    json.WriteStartArray("ExtraArray");
    for (var i = 0; i < extraData.Length; i++)
    {
        json.WriteNumberValue(extraData[i]);
    }
    json.WriteEndArray();

    json.WriteEndObject();

    json.Flush(isFinalBlock: true);

    return (int)json.BytesWritten;
}
```

<span data-ttu-id="efb5a-267">`Utf8JsonWriter`는 JSON 데이터를 동기식으로 작성하는 출력 위치로 `IBufferWriter<byte>`를 수락하고, 호출자는 구체적인 구현을 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-267">The `Utf8JsonWriter` accepts `IBufferWriter<byte>` as the output location to synchronously write the json data into, and you as the caller need to provide a concrete implementation.</span></span> <span data-ttu-id="efb5a-268">플랫폼에 이 인터페이스의 구현이 현재 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-268">The platform does not currently include an implementation of this interface.</span></span> <span data-ttu-id="efb5a-269">`IBufferWriter<byte>`에 대한 예를 보려면 <https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35>를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-269">For an example of `IBufferWriter<byte>`, see <https://gist.github.com/ahsonkhan/c76a1cc4dc7107537c3fdc0079a68b35>.</span></span>

### <a name="jsondocument"></a><span data-ttu-id="efb5a-270">JsonDocument</span><span class="sxs-lookup"><span data-stu-id="efb5a-270">JsonDocument</span></span>

<span data-ttu-id="efb5a-271">`System.Text.Json.JsonDocument`는 `Utf8JsonReader`를 기반으로 빌드됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-271">`System.Text.Json.JsonDocument` is built on top of the `Utf8JsonReader`.</span></span> <span data-ttu-id="efb5a-272">`JsonDocument`는 JSON 데이터를 구문 분석하고 임의 액세스 및 열거를 지원하기 위해 쿼리할 수 있는 읽기 전용 DOM(문서 개체 모델)을 작성하는 기능을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-272">The `JsonDocument` provides the ability to parse JSON data and build a read-only Document Object Model (DOM) that can be queried to support random access and enumeration.</span></span> <span data-ttu-id="efb5a-273">데이터를 구성하는 JSON 요소는 `JsonDocument`에 의해 `RootElement`라는 속성으로 노출되는 `JsonElement` 형식을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-273">The JSON elements that compose the data can be accessed via the `JsonElement` type which is exposed by the `JsonDocument` as a property called `RootElement`.</span></span> <span data-ttu-id="efb5a-274">`JsonElement`는 JSON 텍스트를 일반적인 .NET 형식으로 변환하는 API와 함께 개체 열거자와 JSON 배열을 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-274">The `JsonElement` contains the JSON array and object enumerators along with APIs to convert JSON text to common .NET types.</span></span> <span data-ttu-id="efb5a-275">`JsonDocument`를 사용하여 일반적인 JSON 페이로드를 구분 분석하고 모든 멤버에 액세스하면 **Json.NET**보다 2-3배 빠르고, 합리적인 크기(예 : 1MB 미만)의 데이터가 거의 할당되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-275">Parsing a typical JSON payload and accessing all its members using the `JsonDocument` is 2-3x faster than **Json.NET** with very little allocations for data that is reasonably sized (i.e. < 1 MB).</span></span>

<span data-ttu-id="efb5a-276">다음은 시작점으로 사용할 수 있는 `JsonDocument` 및 `JsonElement`의 샘플 사용법입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-276">Here is a sample usage of the `JsonDocument` and `JsonElement` that can be used as a starting point:</span></span>

```csharp
static double ParseJson()
{
    const string json = " [ { \"name\": \"John\" }, [ \"425-000-1212\", 15 ], { \"grades\": [ 90, 80, 100, 75 ] } ]";

    double average = -1;

    using (JsonDocument doc = JsonDocument.Parse(json))
    {
        JsonElement root = doc.RootElement;
        JsonElement info = root[1];

        string phoneNumber = info[0].GetString();
        int age = info[1].GetInt32();

        JsonElement grades = root[2].GetProperty("grades");

        double sum = 0;
        foreach (JsonElement grade in grades.EnumerateArray())
        {
            sum += grade.GetInt32();
        }

        int numberOfCourses = grades.GetArrayLength();
        average = sum / numberOfCourses;
    }

    return average;
}
```

## <a name="assembly-unloadability"></a><span data-ttu-id="efb5a-277">어셈블리 언로드 기능(unloadability)</span><span class="sxs-lookup"><span data-stu-id="efb5a-277">Assembly Unloadability</span></span>

<span data-ttu-id="efb5a-278">어셈블리 언로드 기능(unloadability)은 `AssemblyLoadContext`의 새로운 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-278">Assembly unloadability is a new capability of `AssemblyLoadContext`.</span></span> <span data-ttu-id="efb5a-279">이 새로운 기능은 API 측면에서 보면 대부분 투명하며 몇 가지 새로운 API만으로 노출됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-279">This new feature is largely transparent from an API perspective, exposed with just a few new APIs.</span></span> <span data-ttu-id="efb5a-280">이 기능을 사용하면 인스턴스화된 유형, 정적 필드 및 어셈블리 자체에 대한 모든 메모리를 해제하여 로더 컨텍스트를 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-280">It enables a loader context to be unloaded, releasing all memory for instantiated types, static fields and for the assembly itself.</span></span> <span data-ttu-id="efb5a-281">애플리케이션은 이 메커니즘을 통해 메모리 누수가 발생하지 않고 영구적으로 어셈블리를 로드 및 언로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-281">An application should be able to load and unload assemblies via this mechanism forever without experiencing a memory leak.</span></span>

<span data-ttu-id="efb5a-282">이 기능은 다음과 유사한 시나리오에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-282">This new capability can be used for scenarios similar to:</span></span>

* <span data-ttu-id="efb5a-283">동적 플러그인 로드 및 언로드가 필요한 플러그인 시나리오.</span><span class="sxs-lookup"><span data-stu-id="efb5a-283">Plugin scenarios where dynamic plugin loading and unloading is required.</span></span>
* <span data-ttu-id="efb5a-284">동적인 코드 컴파일, 실행 및 플러시.</span><span class="sxs-lookup"><span data-stu-id="efb5a-284">Dynamically compiling, running and then flushing code.</span></span> <span data-ttu-id="efb5a-285">웹 사이트, 스크립팅 엔진 등에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-285">Useful for web sites, scripting engines, etc.</span></span>
* <span data-ttu-id="efb5a-286">많은 경우 [MetadataLoadContext](#type-metadataloadcontext)(Preview 1에 릴리스됨)를 선택하는 것이 더 유용하더라도 내성을 위해 어셈블리를(예: ReflectionOnlyLoad) 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-286">Loading assemblies for introspection (like ReflectionOnlyLoad), although [MetadataLoadContext](#type-metadataloadcontext) (released in Preview 1) will be a better choice in many cases.</span></span>

<span data-ttu-id="efb5a-287">자세한 내용은 [언로드 기능(unloadability) 사용](https://github.com/dotnet/coreclr/pull/22221)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-287">For more information, see the [Using Unloadability](https://github.com/dotnet/coreclr/pull/22221) document.</span></span>

<span data-ttu-id="efb5a-288">어셈블리를 언로드하려면 로더 컨텍스트 외부의 관리형 개체에 대한 모든 참조를 이해하고 관리해야 하는 상당한 주의가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-288">Assembly unloading requires significant care to ensure that all references to managed objects from outside a loader context are understood and managed.</span></span> <span data-ttu-id="efb5a-289">로더 컨텍스트가 언로드되도록 요청되면, 외부 참조가 참조되지 않아야 하기 때문에 로더 컨텍스트가 자체로만 일관성을 유지해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-289">When the loader context is requested to be unloaded, any outside references need to have been unreferenced so that the loader context is self-consistent only to itself.</span></span>

<span data-ttu-id="efb5a-290">어셈블리 언로드 기능(unloadability)은 AppDomains(Application Domains)에 의해 .NET Framework에 제공되며 .NET Core에서는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-290">Assembly unloadability was provided in the .NET Framework by Application Domains (AppDomains), which are not supported with .NET Core.</span></span> <span data-ttu-id="efb5a-291">AppDomains에는 새로운 모델에 비해 장점과 한계가 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-291">AppDomains had both benefits and limitations compared to this new model.</span></span> <span data-ttu-id="efb5a-292">이 새로운 로더 모델은 AppDomains에 비해 더 유연하고 성능이 높다고 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-292">Consider this new loader model to be more flexible and higher performant when compared to AppDomains.</span></span>

## <a name="windows-native-interop"></a><span data-ttu-id="efb5a-293">Windows 네이티브 Interop</span><span class="sxs-lookup"><span data-stu-id="efb5a-293">Windows Native Interop</span></span>

<span data-ttu-id="efb5a-294">Windows는 플랫 C API, COM 및 WinRT의 형태로 다양한 네이티브 API를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-294">Windows offers a rich native API, in the form of flat C APIs, COM, and WinRT.</span></span> <span data-ttu-id="efb5a-295">.NET Core 1.0부터는 **P/Invoke**가 지원되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-295">Since .NET Core 1.0, **P/Invoke** has been supported.</span></span> <span data-ttu-id="efb5a-296">이제 .NET Core 3.0에 **CoCreate COM API** 및 **Activate WinRT API** 기능에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-296">Now with .NET Core 3.0, support for the ability to **CoCreate COM APIs** and **Activate WinRT APIs** has been added.</span></span>

<span data-ttu-id="efb5a-297">[Excel 데모 소스 코드](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo)를 통해 COM 사용 사례를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-297">You can see an example of using COM with the [Excel Demo source code](https://github.com/dotnet/samples/tree/master/core/extensions/ExcelDemo).</span></span>

## <a name="type-sequencereader"></a><span data-ttu-id="efb5a-298">유형: SequenceReader</span><span class="sxs-lookup"><span data-stu-id="efb5a-298">Type: SequenceReader</span></span>

<span data-ttu-id="efb5a-299">.NET Core 3.0에서는 `ReadOnlySequence<T>`용 판독기로 사용할 수 있는 `System.Buffers.SequenceReader`가 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-299">In .NET Core 3.0, `System.Buffers.SequenceReader` has been added which can be used as a reader for `ReadOnlySequence<T>`.</span></span> <span data-ttu-id="efb5a-300">이를 통해 여러 지원 버퍼에 걸쳐 있을 수 있는 `System.IO.Pipelines` 데이터의 고성능, 저할당 구문 분석이 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-300">This allows easy, high performance, low allocation parsing of `System.IO.Pipelines` data that can cross multiple backing buffers.</span></span>

<span data-ttu-id="efb5a-301">다음 예제에서는 입력 `Sequence`를 유효한 `CR/LF` 구분 줄로 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-301">The following example breaks an input `Sequence` into valid `CR/LF` delimited lines:</span></span>

```csharp
private static ReadOnlySpan<byte> CRLF => new byte[] { (byte)'\r', (byte)'\n' };

public static void ReadLines(ReadOnlySequence<byte> sequence)
{
    SequenceReader<byte> reader = new SequenceReader<byte>(sequence);

    while (!reader.End)
    {
        if (!reader.TryReadToAny(out ReadOnlySpan<byte> line, CRLF, advancePastDelimiter:false))
        {
            // Couldn't find another delimiter
            // ...
        }

        if (!reader.IsNext(CRLF, advancePast: true))
        {
            // Not a good CR/LF pair
            // ...
        }

        // line is valid, process
        ProcessLine(line);
    }
}
```

## <a name="type-metadataloadcontext"></a><span data-ttu-id="efb5a-302">유형: MetadataLoadContext</span><span class="sxs-lookup"><span data-stu-id="efb5a-302">Type: MetadataLoadContext</span></span>

<span data-ttu-id="efb5a-303">호출자의 애플리케이션 도메인에 영향을 주지 않고 어셈블리 메타데이터를 읽을 수 있도록 하는 `MetadataLoadContext` 형식이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-303">The `MetadataLoadContext` type has been added that enables reading assembly metadata without affecting the caller’s application domain.</span></span> <span data-ttu-id="efb5a-304">현재 런타임 환경과 다른 아키텍처 및 플랫폼용으로 빌드된 어셈블리를 포함하여, 어셈블리는 데이터로 읽힙니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-304">Assemblies are read as data, including assemblies built for different architectures and platforms than the current runtime environment.</span></span> <span data-ttu-id="efb5a-305">`MetadataLoadContext`는 .NET Framework에서만 사용할 수 있는 <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>와 겹칩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-305">`MetadataLoadContext` overlaps with the <xref:System.Reflection.Assembly.ReflectionOnlyLoad*>, which is only available in the .NET Framework.</span></span>

<span data-ttu-id="efb5a-306">`MetdataLoadContext`는 [System.Reflection.MetadataLoadContext 패키지](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext)에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-306">`MetdataLoadContext` is available in the [System.Reflection.MetadataLoadContext package](https://www.nuget.org/packages/System.Reflection.MetadataLoadContext).</span></span> <span data-ttu-id="efb5a-307">.NET Standard 2.0 패키지입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-307">It is a .NET Standard 2.0 package.</span></span>

<span data-ttu-id="efb5a-308">`MetadataLoadContext`는 <xref:System.Runtime.Loader.AssemblyLoadContext> 형식과 마찬가지로 API를 노출하지만 해당 형식을 기반으로 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-308">The `MetadataLoadContext` exposes APIs similar to the <xref:System.Runtime.Loader.AssemblyLoadContext> type, but is not based on that type.</span></span> <span data-ttu-id="efb5a-309"><xref:System.Runtime.Loader.AssemblyLoadContext>와 마찬가지로, `MetadataLoadContext`를 사용하면 격리된 어셈블리 로드 Universe 내에서 어셈블리를 로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-309">Much like <xref:System.Runtime.Loader.AssemblyLoadContext>, the `MetadataLoadContext` enables loading assemblies within an isolated assembly loading universe.</span></span> <span data-ttu-id="efb5a-310">`MetdataLoadContext` API는 <xref:System.Reflection.Assembly> 개체를 반환하여 익숙한 리플렉션 API를 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-310">`MetdataLoadContext` APIs return <xref:System.Reflection.Assembly> objects, enabling the use of familiar reflection APIs.</span></span> <span data-ttu-id="efb5a-311">[MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127) 등의 실행 지향 API는 허용되지 않으며 InvalidOperationException을 throw합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-311">Execution-oriented APIs, such as [MethodBase.Invoke](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/src/System/Reflection/TypeLoading/Methods/RoMethod.cs#L127), are not allowed and will throw InvalidOperationException.</span></span>

<span data-ttu-id="efb5a-312">다음 샘플은 지정된 인터페이스를 구현하는 어셈블리에서 구체적인 형식을 찾는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-312">The following sample demonstrates how to find concrete types in an assembly that implements a given interface:</span></span>

```csharp
var paths = new string[] {@"C:\myapp\mscorlib.dll", @"C:\myapp\myapp.dll"};
var resolver = new PathAssemblyResolver(paths);
using (var lc = new MetadataLoadContext(resolver))
{
    Assembly a = lc.LoadFromAssemblyName("myapp");
    Type myInterface = a.GetType("MyApp.IPluginInterface");
    foreach (Type t in a.GetTypes())
    {
        if (t.IsClass && myInterface.IsAssignableFrom(t))
            Console.WriteLine($"Class {t.FullName} implements IPluginInterface");
    }
}
```

<span data-ttu-id="efb5a-313">`MetadataLoadContext`에 대한 시나리오에는 어셈블리 세트를 데이터로 검사하고, 검사가 수행된 후 모든 파일 잠금 및 메모리가 해제되어야 하는 디자인 타임 기능, 빌드 타임 도구 및 런타임 강화 기능이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-313">Scenarios for `MetadataLoadContext` include design-time features, build-time tooling, and runtime light-up features that need to inspect a set of assemblies as data and have all file locks and memory freed after inspection is performed.</span></span>

<span data-ttu-id="efb5a-314">`MetadataLoadContext`에는 생성자에게 전달되는 확인자 클래스가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-314">The `MetadataLoadContext` has a resolver class passed to its constructor.</span></span> <span data-ttu-id="efb5a-315">확인자의 작업은 `AssemblyName`이 제공될 경우 `Assembly`를 로드하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-315">The resolver's job is to load an `Assembly` given its `AssemblyName`.</span></span> <span data-ttu-id="efb5a-316">확인자 클래스는 추상 `MetadataAssemblyResolver` 클래스에서 파생됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-316">The resolver class derives from the abstract `MetadataAssemblyResolver` class.</span></span> <span data-ttu-id="efb5a-317">경로 기반 시나리오에 대한 확인자 구현은 `PathAssemblyResolver`를 사용하여 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-317">An implementation of the resolver for path-based scenarios is provided with `PathAssemblyResolver`.</span></span>

<span data-ttu-id="efb5a-318">[MetadataLoadContext 테스트](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests)는 많은 사용 사례를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-318">The [MetadataLoadContext tests](https://github.com/dotnet/corefx/tree/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests) demonstrate many use cases.</span></span> <span data-ttu-id="efb5a-319">[어셈블리 테스트](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs)에서 시작하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-319">The [Assembly tests](https://github.com/dotnet/corefx/blob/master/src/System.Reflection.MetadataLoadContext/tests/src/Tests/Assembly/AssemblyTests.cs) are a good place to start.</span></span>

## <a name="tls-13--openssl-111-on-linux"></a><span data-ttu-id="efb5a-320">Linux의 TLS 1.3 및 OpenSSL 1.1.1</span><span class="sxs-lookup"><span data-stu-id="efb5a-320">TLS 1.3 & OpenSSL 1.1.1 on Linux</span></span>

<span data-ttu-id="efb5a-321">이제 .NET Core는 지정된 환경에서 사용 가능한 경우 [OpenSSL 1.1.1의 TLS 1.3 지원](https://www.openssl.org/blog/blog/2018/09/11/release111/)을 이용합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-321">.NET Core will now take advantage of [TLS 1.3 support in OpenSSL 1.1.1](https://www.openssl.org/blog/blog/2018/09/11/release111/), when it is available in a given environment.</span></span> <span data-ttu-id="efb5a-322">[OpenSSL 팀](https://www.openssl.org/blog/blog/2018/09/11/release111/)을 기준으로, TLS 1.3의 여러 가지 혜택이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-322">There are multiple benefits of TLS 1.3, per the [OpenSSL team](https://www.openssl.org/blog/blog/2018/09/11/release111/):</span></span>

* <span data-ttu-id="efb5a-323">클라이언트와 서버 간에 필요한 왕복 횟수가 감소하여 연결 시간이 향상되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-323">Improved connection times due to a reduction in the number of round trips required between the client and server.</span></span>

* <span data-ttu-id="efb5a-324">사용되지 않는 다양한 비보안 암호화 알고리즘이 제거되고 연결 핸드셰이크가 더 많이 암호화되어 보안이 개선되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-324">Improved security due to the removal of various obsolete and insecure cryptographic algorithms and encryption of more of the connection handshake.</span></span>

<span data-ttu-id="efb5a-325">.NET Core 3.0 Preview 1은 **OpenSSL 1.1.1**, **OpenSSL 1.1.0** 또는 **OpenSSL 1.0.2**(Linux 시스템에서 발견된 가장 적합한 버전)를 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-325">.NET Core 3.0 Preview 1 is capable of utilizing **OpenSSL 1.1.1**, **OpenSSL 1.1.0**, or **OpenSSL 1.0.2** (whatever the best version found is, on a Linux system).</span></span>  <span data-ttu-id="efb5a-326">**OpenSSL 1.1.1**이 사용 가능한 경우 SslStream 및 HttpClient 형식은 클라이언트와 서버가 둘 다 **TLS 1.3**을 지원할 경우 `SslProtocols.None`(시스템 기본 프로토콜)을 사용할 때 **TLS 1.3**을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-326">When **OpenSSL 1.1.1** is available the SslStream and HttpClient types will use **TLS 1.3** when using `SslProtocols.None` (system default protocols), assuming both the client and server support **TLS 1.3**.</span></span>

<span data-ttu-id="efb5a-327">다음 샘플은 <https://www.cloudflare.com>에 연결하는 Ubuntu 18.10의 .NET Core 3.0 Preview 1을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-327">The following sample demonstrates .NET Core 3.0 Preview 1 on Ubuntu 18.10 connecting to <https://www.cloudflare.com>:</span></span>

```csharp
using System;
using System.Net.Security;
using System.Net.Sockets;
using System.Threading.Tasks;

namespace tlstest
{
    class Program
    {
        static async Task Main()
        {
            using (TcpClient tcpClient = new TcpClient())
            {
                string targetHost = "www.cloudflare.com";

                await tcpClient.ConnectAsync(targetHost, 443);

                using (SslStream sslStream = new SslStream(tcpClient.GetStream()))
                {
                    await sslStream.AuthenticateAsClientAsync(targetHost);
                    await Console.Out.WriteLineAsync($"Connected to {targetHost} with {sslStream.SslProtocol}");
                }
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/tlstest$ dotnet run
Connected to www.cloudflare.com with Tls13
user@comp-ubuntu1810:~/tlstest$ openssl version
OpenSSL 1.1.1  11 Sep 2018
```

>[!IMPORTANT]
><span data-ttu-id="efb5a-328">Windows 및 macOS에서는 아직 **TLS 1.3**을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-328">Windows and macOS do not yet support **TLS 1.3**.</span></span> <span data-ttu-id="efb5a-329">지원이 제공되면 .NET Core 3.0은 이러한 운영 체제에서 **TLS 1.3**을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-329">.NET Core 3.0 will support **TLS 1.3** on these operating systems when support becomes available.</span></span>

## <a name="cryptography"></a><span data-ttu-id="efb5a-330">암호화</span><span class="sxs-lookup"><span data-stu-id="efb5a-330">Cryptography</span></span>

<span data-ttu-id="efb5a-331">`System.Security.Cryptography.AesGcm` 및 `System.Security.Cryptography.AesCcm`을 통해 구현된 **AES-GCM** 및 **AES-CCM** 암호에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-331">Support has been added for **AES-GCM** and **AES-CCM** ciphers, implemented via `System.Security.Cryptography.AesGcm` and `System.Security.Cryptography.AesCcm`.</span></span> <span data-ttu-id="efb5a-332">이러한 알고리즘은 [AEAD(연결 데이터를 사용한 인증된 암호화) 알고리즘](https://en.wikipedia.org/wiki/Authenticated_encryption)이자, .NET Core에 추가된 최초의 AE(인증된 암호화) 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-332">These algorithms are both [Authenticated Encryption with Association Data (AEAD) algorithms](https://en.wikipedia.org/wiki/Authenticated_encryption), and the first Authenticated Encryption (AE) algorithms added to .NET Core.</span></span>

<span data-ttu-id="efb5a-333">다음 코드는 **AesGcm** 암호를 사용하여 임의 데이터를 암호화하고 암호를 해독하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-333">The following code demonstrates using **AesGcm** cipher to encrypt and decrypt random data.</span></span>

<span data-ttu-id="efb5a-334">**AesCcm**에 대한 코드는 거의 동일하게 표시됩니다(클래스 변수 이름만 다름)</span><span class="sxs-lookup"><span data-stu-id="efb5a-334">The code for **AesCcm** would look almost identical (only the class variable names would be different).</span></span>

```csharp
// key should be: pre-known, derived, or transported via another channel, such as RSA encryption
byte[] key = new byte[16];
RandomNumberGenerator.Fill(key);

byte[] nonce = new byte[12];
RandomNumberGenerator.Fill(nonce);

// normally this would be your data
byte[] dataToEncrypt = new byte[1234];
byte[] associatedData = new byte[333];
RandomNumberGenerator.Fill(dataToEncrypt);
RandomNumberGenerator.Fill(associatedData);

// these will be filled during the encryption
byte[] tag = new byte[16];
byte[] ciphertext = new byte[dataToEncrypt.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Encrypt(nonce, dataToEncrypt, ciphertext, tag, associatedData);
}

// tag, nonce, ciphertext, associatedData should be sent to the other part

byte[] decryptedData = new byte[ciphertext.Length];

using (AesGcm aesGcm = new AesGcm(key))
{
    aesGcm.Decrypt(nonce, ciphertext, tag, decryptedData, associatedData);
}

// do something with the data
// this should always print that data is the same
Console.WriteLine($"AES-GCM: Decrypted data is{(dataToEncrypt.SequenceEqual(decryptedData) ? "the same as" : "different than")} original data.");
```

## <a name="cryptographic-key-importexport"></a><span data-ttu-id="efb5a-335">암호화 키 가져오기/내보내기</span><span class="sxs-lookup"><span data-stu-id="efb5a-335">Cryptographic Key Import/Export</span></span>

<span data-ttu-id="efb5a-336">.NET Core 3.0 Preview 1은 X.509 인증서를 사용하지 않고도 표준 형식에서 비대칭 공개 키와 개인 키를 가져오고 내보낼 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-336">.NET Core 3.0 Preview 1 supports the import and export of asymmetric public and private keys from standard formats, without needing to use an X.509 certificate.</span></span>

<span data-ttu-id="efb5a-337">모든 키 유형(RSA, DSA, ECDsa, ECDiffieHellman)은 공개 키에 대한 **X.509 SubjectPublicKeyInfo** 형식과 개인 키에 대한 **PKCS#8 PrivateKeyInfo** 및 **PKCS#8 EncryptedPrivateKeyInfo** 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-337">All key types (RSA, DSA, ECDsa, ECDiffieHellman) support the **X.509 SubjectPublicKeyInfo** format for public keys, and the **PKCS#8 PrivateKeyInfo** and **PKCS#8 EncryptedPrivateKeyInfo** formats for private keys.</span></span> <span data-ttu-id="efb5a-338">RSA는 **PKCS#1 RSAPublicKey** 및 **PKCS#1 RSAPrivateKey**를 추가로 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-338">RSA additionally supports **PKCS#1 RSAPublicKey** and **PKCS#1 RSAPrivateKey**.</span></span> <span data-ttu-id="efb5a-339">내보내기 메서드는 모두 DER로 인코드된 이진 데이터를 생성하고, 가져오기 메서드도 동일한 동작을 예상합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-339">The export methods all produce DER-encoded binary data, and the import methods expect the same.</span></span> <span data-ttu-id="efb5a-340">키가 텍스트에 편리한 PEM 형식으로 저장된 경우 호출자는 가져오기 메서드를 호출하기 전에 콘텐츠를 base64로 디코드해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-340">If a key is stored in the text-friendly PEM format, the caller will need to base64-decode the content before calling an import method.</span></span>

```csharp
using System;
using System.IO;
using System.Security.Cryptography;

namespace rsakeyprint
{
    class Program
    {
        static void Main(string[] args)
        {
            using (RSA rsa = RSA.Create())
            {
                byte[] keyBytes = File.ReadAllBytes(args[0]);
                rsa.ImportRSAPrivateKey(keyBytes, out int bytesRead);

                Console.WriteLine($"Read {bytesRead} bytes, {keyBytes.Length-bytesRead} extra byte(s) in file.");
                RSAParameters rsaParameters = rsa.ExportParameters(true);
                Console.WriteLine(BitConverter.ToString(rsaParameters.D));
            }
        }
    }
}
```

```console
user@comp-ubuntu1810:~/rsakeyprint$ echo Making a small key to save on screen space.
Making a small key to save on screen space.
user@comp-ubuntu1810:~/rsakeyprint$ openssl genrsa 768 | openssl rsa -outform der -out rsa.key
Generating RSA private key, 768 bit long modulus (2 primes)
..+++++++
........+++++++
e is 65537 (0x010001)
writing RSA key
user@comp-ubuntu1810:~/rsakeyprint$ dotnet run rsa.key
Read 461 bytes, 0 extra byte(s) in file.
0F-D0-82-34-F8-13-38-4A-7F-C7-52-4A-F6-93-F8-FB-6D-98-7A-6A-04-3B-BC-35-8C-7D-AC-A5-A3-6E-AD-C1-66-30-81-2C-2A-DE-DA-60-03-6A-2C-D9-76-15-7F-61-97-57-
79-E1-6E-45-62-C3-83-04-97-CB-32-EF-C5-17-5F-99-60-92-AE-B6-34-6F-30-06-03-AC-BF-15-24-43-84-EB-83-60-EF-4D-3B-BD-D9-5D-56-26-F0-51-CE-F1
user@comp-ubuntu1810:~/rsakeyprint$ openssl rsa -in rsa.key -inform der -text -noout | grep -A7 private
privateExponent:
    0f:d0:82:34:f8:13:38:4a:7f:c7:52:4a:f6:93:f8:
    fb:6d:98:7a:6a:04:3b:bc:35:8c:7d:ac:a5:a3:6e:
    ad:c1:66:30:81:2c:2a:de:da:60:03:6a:2c:d9:76:
    15:7f:61:97:57:79:e1:6e:45:62:c3:83:04:97:cb:
    32:ef:c5:17:5f:99:60:92:ae:b6:34:6f:30:06:03:
    ac:bf:15:24:43:84:eb:83:60:ef:4d:3b:bd:d9:5d:
    56:26:f0:51:ce:f1
```

<span data-ttu-id="efb5a-341">PKCS#8 파일은 `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` 클래스를 통해 검사할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-341">PKCS#8 files can be inspected with the `System.Security.Cryptography.Pkcs.Pkcs8PrivateKeyInfo` class.</span></span>

<span data-ttu-id="efb5a-342">PFX/PKCS#12 파일은 각각 `System.Security.Cryptography.Pkcs.Pkcs12Info` 및 `System.Security.Cryptography.Pkcs.Pkcs12Builder`를 통해 검사하고 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-342">PFX/PKCS#12 files can be inspected and manipulated with `System.Security.Cryptography.Pkcs.Pkcs12Info` and `System.Security.Cryptography.Pkcs.Pkcs12Builder`, respectively.</span></span>

## <a name="serialport-for-linux"></a><span data-ttu-id="efb5a-343">Linux용 SerialPort</span><span class="sxs-lookup"><span data-stu-id="efb5a-343">SerialPort for Linux</span></span>

<span data-ttu-id="efb5a-344">.NET Core 3.0은 이제 Linux에서 <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType>을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-344">.NET Core 3.0 now supports <xref:System.IO.Ports.SerialPort?displayProperty=nameWithType> on Linux.</span></span>

<span data-ttu-id="efb5a-345">이전에는 .NET Core가 Windows에서만 `SerialPort` 형식 사용을 지원했습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-345">Previously, .NET Core only supported using the `SerialPort` type on Windows.</span></span>

## <a name="more-bcl-improvements"></a><span data-ttu-id="efb5a-346">더 많은 BCL 개선 사항</span><span class="sxs-lookup"><span data-stu-id="efb5a-346">More BCL Improvements</span></span>

<span data-ttu-id="efb5a-347">.NET Core 2.1에서 도입된 `Span<T>`, `Memory<T>` 및 관련 형식이 .NET Core 3.0에서 최적화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-347">The `Span<T>`, `Memory<T>`, and related types that were introduced in .NET Core 2.1, have been optimized in .NET Core 3.0.</span></span> <span data-ttu-id="efb5a-348">이제 범위 구성, 조각화, 구문 분석, 서식 지정과 같은 일반적인 작업의 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-348">Common operations such as span construction, slicing, parsing, and formatting now perform better.</span></span>

<span data-ttu-id="efb5a-349">또한 `String` 등의 형식이 내부적으로 개선되어, `Dictionary<TKey, TValue>` 및 기타 컬렉션에서 키로 사용할 때 보다 효율적으로 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-349">Additionally, types like `String` have seen under-the-cover improvements to make them more efficient when used as keys with `Dictionary<TKey, TValue>` and other collections.</span></span> <span data-ttu-id="efb5a-350">코드 변경 없이도 이러한 개선 사항을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-350">No code changes are required to benefit from these improvements.</span></span>

<span data-ttu-id="efb5a-351">또한 다음 개선 사항이 .NET Core 3 Preview 1에서 새로 도입되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-351">The following improvements are also new in .NET Core 3 Preview 1:</span></span>

* <span data-ttu-id="efb5a-352">HttpClient에 기본 제공되는 Brotli 지원</span><span class="sxs-lookup"><span data-stu-id="efb5a-352">Brotli support built in to HttpClient</span></span>
* <span data-ttu-id="efb5a-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span><span class="sxs-lookup"><span data-stu-id="efb5a-353">ThreadPool.UnsafeQueueWorkItem(IThreadPoolWorkItem)</span></span>
* <span data-ttu-id="efb5a-354">Unsafe.Unbox</span><span class="sxs-lookup"><span data-stu-id="efb5a-354">Unsafe.Unbox</span></span>
* <span data-ttu-id="efb5a-355">CancellationToken.Unregister</span><span class="sxs-lookup"><span data-stu-id="efb5a-355">CancellationToken.Unregister</span></span>
* <span data-ttu-id="efb5a-356">복합 산술 연산자</span><span class="sxs-lookup"><span data-stu-id="efb5a-356">Complex arithmetic operators</span></span>
* <span data-ttu-id="efb5a-357">TCP 연결 유지용 소켓 API</span><span class="sxs-lookup"><span data-stu-id="efb5a-357">Socket APIs for TCP keep alive</span></span>
* <span data-ttu-id="efb5a-358">StringBuilder.GetChunks</span><span class="sxs-lookup"><span data-stu-id="efb5a-358">StringBuilder.GetChunks</span></span>
* <span data-ttu-id="efb5a-359">IPEndPoint 구문 분석</span><span class="sxs-lookup"><span data-stu-id="efb5a-359">IPEndPoint parsing</span></span>
* <span data-ttu-id="efb5a-360">RandomNumberGenerator.GetInt32</span><span class="sxs-lookup"><span data-stu-id="efb5a-360">RandomNumberGenerator.GetInt32</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="efb5a-361">계층화된 컴파일</span><span class="sxs-lookup"><span data-stu-id="efb5a-361">Tiered compilation</span></span>

<span data-ttu-id="efb5a-362">[계층화된 컴파일](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/)은 .NET Core 3.0에서 기본적으로 켜져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-362">[Tiered compilation](https://devblogs.microsoft.com/dotnet/tiered-compilation-preview-in-net-core-2-1/) is on by default with .NET Core 3.0.</span></span> <span data-ttu-id="efb5a-363">런타임 시 JIT(Just-In-Time) 컴파일러를 보다 유연하게 사용해서 시작 시 성능과 처리량 극대화를 위한 성능을 둘 다 개선할 수 있도록 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-363">It is a feature that enables the runtime to more adaptively use the Just-In-Time (JIT) compiler to get better performance, both at startup and to maximize throughput.</span></span>

<span data-ttu-id="efb5a-364">이 기능은 [.NET Core 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/)에서 옵트인 기능으로 추가되었으며, [.NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/)에서 기본적으로 사용할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-364">This feature was added as an opt-in feature in [.NET Core 2.1](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-1/) and then was enabled by default in [.NET Core 2.2 Preview 2](https://devblogs.microsoft.com/dotnet/announcing-net-core-2-2-preview-2/).</span></span> <span data-ttu-id="efb5a-365">이후에 .NET Core 2.2 릴리스에서 다시 옵트인으로 되돌려졌습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-365">Subsequently, it has been reverted back to opt in with the .NET Core 2.2 release.</span></span>

## <a name="arm64-linux-support"></a><span data-ttu-id="efb5a-366">ARM64 Linux 지원</span><span class="sxs-lookup"><span data-stu-id="efb5a-366">ARM64 Linux support</span></span>

<span data-ttu-id="efb5a-367">Linux용 ARM64에 대한 지원이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-367">Support has been added for ARM64 for Linux.</span></span> <span data-ttu-id="efb5a-368">ARM64는 현재 IoT 시나리오에서 주로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-368">The primary use case for ARM64 is currently with IoT scenarios.</span></span>

<span data-ttu-id="efb5a-369">Alpine, Debian 및 Ubuntu [Docker 이미지를 ARM64용 .NET Core에 사용할 수 있습니다](https://hub.docker.com/r/microsoft/dotnet/).</span><span class="sxs-lookup"><span data-stu-id="efb5a-369">Alpine, Debian and Ubuntu [Docker images are available for .NET Core for ARM64](https://hub.docker.com/r/microsoft/dotnet/).</span></span>

<span data-ttu-id="efb5a-370">자세한 내용은 [.NET Core ARM64 상태](https://github.com/dotnet/announcements/issues/82)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-370">Please check [.NET Core ARM64 Status](https://github.com/dotnet/announcements/issues/82) for more information.</span></span>

>[!NOTE]
> <span data-ttu-id="efb5a-371">**ARM64** Windows 지원은 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-371">**ARM64** Windows support isn't yet available.</span></span>

## <a name="install-net-core-30-previews-on-linux-with-snap"></a><span data-ttu-id="efb5a-372">Snap으로 Linux에 .NET Core 3.0 미리 보기 설치</span><span class="sxs-lookup"><span data-stu-id="efb5a-372">Install .NET Core 3.0 Previews on Linux with Snap</span></span>

<span data-ttu-id="efb5a-373">Snap은 [Snap을 지원하는 Linux 배포판](https://docs.snapcraft.io/installing-snapd/6735)에서 .NET Core 미리 보기를 설치하고 사용해 보기 좋은 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-373">Snap is the preferred way to install and try .NET Core previews on [Linux distributions that support Snap](https://docs.snapcraft.io/installing-snapd/6735).</span></span>

<span data-ttu-id="efb5a-374">시스템에서 Snap을 구성한 후, 다음 명령을 실행하여 [.NET Core SDK 3.0 미리 보기 SDK](https://snapcraft.io/dotnet-sdk)를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-374">After configuring Snap on your system, run the following command to install the [.NET Core SDK 3.0 Preview SDK](https://snapcraft.io/dotnet-sdk).</span></span>

```console
sudo snap install dotnet-sdk --beta --classic
```

<span data-ttu-id="efb5a-375">Snap 패키지를 사용하여 .NET Core를 설치하면 기본 .NET Core 명령이 `dotnet`이 아니라 `dotnet-sdk.dotnet`입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-375">When .NET Core in installed using the Snap package, the default .NET Core command is `dotnet-sdk.dotnet`, as opposed to just `dotnet`.</span></span> <span data-ttu-id="efb5a-376">네임스페이스 지정 명령의 이점은 전역적으로 설치된 .NET Core 버전이 있을 경우 충돌하지 않는다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-376">The benefit of the namespaced command is that it will not conflict with a globally installed .NET Core version you may have.</span></span> <span data-ttu-id="efb5a-377">이 명령은 다음을 사용하여 `dotnet`에 별칭으로 사용될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-377">This command can be aliased to `dotnet` with:</span></span>

```console
sudo snap alias dotnet-sdk.dotnet dotnet
```

<span data-ttu-id="efb5a-378">일부 배포판은 SSL 인증서에 액세스하려면 추가 단계가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-378">Some distros require an additional step to enable access to the SSL certificate.</span></span> <span data-ttu-id="efb5a-379">자세한 내용은 [Linux 설정](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="efb5a-379">See our [Linux Setup](https://github.com/dotnet/core/blob/master/Documentation/linux-setup.md) for details.</span></span>

## <a name="gpio-support-for-raspberry-pi"></a><span data-ttu-id="efb5a-380">Raspberry Pi에 대한 GPIO 지원</span><span class="sxs-lookup"><span data-stu-id="efb5a-380">GPIO Support for Raspberry Pi</span></span>

<span data-ttu-id="efb5a-381">GPIO 프로그래밍에 사용할 수 있는 두 개의 새 패키지가 NuGet에 릴리스되었습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-381">Two new packages have been released to NuGet that you can use for GPIO programming.</span></span>

* [<span data-ttu-id="efb5a-382">System.Device.Gpio</span><span class="sxs-lookup"><span data-stu-id="efb5a-382">System.Device.Gpio</span></span>](https://www.nuget.org/packages/System.Device.Gpio/0.1.0-prerelease.19078.2)
* [<span data-ttu-id="efb5a-383">Iot.Device.Bindings</span><span class="sxs-lookup"><span data-stu-id="efb5a-383">Iot.Device.Bindings</span></span>](https://www.nuget.org/packages/Iot.Device.Bindings/0.1.0-prerelease.19078.2)

<span data-ttu-id="efb5a-384">GPIO 패키지에는 GPIO, SPI, I2C 및 PWM 디바이스용 API가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-384">The GPIO Packages includes APIs for GPIO, SPI, I2C and PWM devices.</span></span> <span data-ttu-id="efb5a-385">IoT 바인딩 패키지에는 다양한 칩과 센서에 대한 [디바이스 바인딩](https://github.com/dotnet/iot/blob/master/src/devices/README.md)이 포함되며 [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices)에서 동일한 것을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-385">The IoT bindings package includes [device bindings](https://github.com/dotnet/iot/blob/master/src/devices/README.md) for various chips and sensors, the same ones available at [dotnet/iot - src/devices](https://github.com/dotnet/iot/tree/master/src/devices).</span></span>

<span data-ttu-id="efb5a-386">.NET Core 3.0 Preview 1의 일부로 발표된 업데이트된 직렬 포트 API는 이 패키지의 일부는 아니지만 .NET Core 플랫폼의 일부로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-386">The updated serial port APIs that were announced as part of .NET Core 3.0 Preview 1 are not part of these packages but are available as part of the .NET Core platform.</span></span>

## <a name="platform-support"></a><span data-ttu-id="efb5a-387">플랫폼 지원</span><span class="sxs-lookup"><span data-stu-id="efb5a-387">Platform Support</span></span>

<span data-ttu-id="efb5a-388">.NET Core 3은 다음 운영 체제에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-388">.NET Core 3 will be supported on the following operating systems:</span></span>

* <span data-ttu-id="efb5a-389">Windows 클라이언트: 7, 8.1, 10(1607+)</span><span class="sxs-lookup"><span data-stu-id="efb5a-389">Windows Client: 7, 8.1, 10 (1607+)</span></span>
* <span data-ttu-id="efb5a-390">Windows Server 2012 R2 SP1+</span><span class="sxs-lookup"><span data-stu-id="efb5a-390">Windows Server: 2012 R2 SP1+</span></span>
* <span data-ttu-id="efb5a-391">macOS: 10.12+</span><span class="sxs-lookup"><span data-stu-id="efb5a-391">macOS: 10.12+</span></span>
* <span data-ttu-id="efb5a-392">RHEL: 6+</span><span class="sxs-lookup"><span data-stu-id="efb5a-392">RHEL: 6+</span></span>
* <span data-ttu-id="efb5a-393">Fedora: 26+</span><span class="sxs-lookup"><span data-stu-id="efb5a-393">Fedora: 26+</span></span>
* <span data-ttu-id="efb5a-394">Ubuntu: 16.04+</span><span class="sxs-lookup"><span data-stu-id="efb5a-394">Ubuntu: 16.04+</span></span>
* <span data-ttu-id="efb5a-395">Debian: 9+</span><span class="sxs-lookup"><span data-stu-id="efb5a-395">Debian: 9+</span></span>
* <span data-ttu-id="efb5a-396">SLES: 12+</span><span class="sxs-lookup"><span data-stu-id="efb5a-396">SLES: 12+</span></span>
* <span data-ttu-id="efb5a-397">openSUSE: 42.3+</span><span class="sxs-lookup"><span data-stu-id="efb5a-397">openSUSE: 42.3+</span></span>
* <span data-ttu-id="efb5a-398">Alpine: 3.8+</span><span class="sxs-lookup"><span data-stu-id="efb5a-398">Alpine: 3.8+</span></span>

<span data-ttu-id="efb5a-399">칩이 지원되는 운영 체제:</span><span class="sxs-lookup"><span data-stu-id="efb5a-399">Chip support follows:</span></span>

* <span data-ttu-id="efb5a-400">Windows, macOS 및 Linux의 x64</span><span class="sxs-lookup"><span data-stu-id="efb5a-400">x64 on Windows, macOS, and Linux</span></span>
* <span data-ttu-id="efb5a-401">Windows의 x86</span><span class="sxs-lookup"><span data-stu-id="efb5a-401">x86 on Windows</span></span>
* <span data-ttu-id="efb5a-402">Windows 및 Linux의 ARM32</span><span class="sxs-lookup"><span data-stu-id="efb5a-402">ARM32 on Windows and Linux</span></span>
* <span data-ttu-id="efb5a-403">Linux의 ARM64</span><span class="sxs-lookup"><span data-stu-id="efb5a-403">ARM64 on Linux</span></span>

<span data-ttu-id="efb5a-404">Linux의 경우 ARM32는 Debian 9 이상 및 Ubuntu 16.04 이상에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-404">For Linux, ARM32 is supported on Debian 9+ and Ubuntu 16.04+.</span></span> <span data-ttu-id="efb5a-405">ARM64의 경우, Alpine 3.8이 추가된 ARM32와 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-405">For ARM64, it is the same as ARM32 with the addition of Alpine 3.8.</span></span> <span data-ttu-id="efb5a-406">이것은 X64에 지원되는 것과 동일한 버전의 배포판입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-406">These are the same versions of those distros as is supported for X64.</span></span>

<span data-ttu-id="efb5a-407">.NET Core 3.0의 Docker 이미지는 [Docker 허브의 microsoft/dotnet](https://hub.docker.com/r/microsoft/dotnet/)에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-407">Docker images for .NET Core 3.0 are available at [microsoft/dotnet on Docker Hub](https://hub.docker.com/r/microsoft/dotnet/).</span></span> <span data-ttu-id="efb5a-408">Microsoft는 현재 [MCR(Microsoft 컨테이너 레지스트리)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/)을 채택하고 있으며 최종 .NET Core 3.0 이미지는 MCR에만 게시될 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="efb5a-408">Microsoft is currently in the process of adopting [Microsoft Container Registry (MCR)](https://cloudblogs.microsoft.com/opensource/2019/01/17/improved-discovery-experience-microsoft-containers-docker-hub/) and it is expected that the final .NET Core 3.0 images will only be published to MCR.</span></span>
