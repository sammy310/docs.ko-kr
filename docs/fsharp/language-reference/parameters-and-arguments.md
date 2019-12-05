---
title: 매개 변수 및 인수
description: 매개 변수 F# 를 정의 하 고 함수, 메서드 및 속성에 인수를 전달 하는 언어 지원에 대해 알아봅니다.
ms.date: 12/04/2019
ms.openlocfilehash: b234ef939128e7cf09d35f9580d4d5010d7dc639
ms.sourcegitcommit: a4f9b754059f0210e29ae0578363a27b9ba84b64
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/05/2019
ms.locfileid: "74837131"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="1f91c-103">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="1f91c-103">Parameters and Arguments</span></span>

<span data-ttu-id="1f91c-104">이 항목에서는 매개 변수를 정의 하 고 함수, 메서드 및 속성에 인수를 전달 하는 언어 지원에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="1f91c-105">여기에는 참조로 전달 하는 방법 및 다양 한 수의 인수를 사용할 수 있는 메서드를 정의 하 고 사용 하는 방법에 대 한 정보가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="1f91c-106">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="1f91c-106">Parameters and Arguments</span></span>

<span data-ttu-id="1f91c-107">Term *매개 변수* 는 제공 될 것으로 예상 되는 값의 이름을 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="1f91c-108">Term *인수* 는 각 매개 변수에 제공 된 값에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="1f91c-109">매개 변수는 튜플 또는 커리 된 형식으로 지정 하거나 둘 중 일부를 조합 하 여 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="1f91c-110">명시적 매개 변수 이름을 사용 하 여 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="1f91c-111">메서드의 매개 변수는 선택적으로 지정할 수 있으며 기본값을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="1f91c-112">매개 변수 패턴</span><span class="sxs-lookup"><span data-stu-id="1f91c-112">Parameter Patterns</span></span>

<span data-ttu-id="1f91c-113">함수 및 메서드에 제공 되는 매개 변수는 일반적으로 공백으로 구분 되는 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="1f91c-114">즉, 원칙적으로 [일치 식](match-expressions.md) 에 설명 된 모든 패턴을 함수 또는 멤버에 대 한 매개 변수 목록에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="1f91c-115">메서드는 일반적으로 인수를 전달 하는 튜플 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="1f91c-116">이는 튜플 형식이 .NET 메서드에 인수가 전달 되는 방식과 일치 하므로 다른 .NET 언어의 관점에서 보다 명확한 결과를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="1f91c-117">커리 된 형식은 `let` 바인딩을 사용 하 여 만든 함수와 가장 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="1f91c-118">다음 의사 코드에서는 튜플 및 커리 된 인수의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="1f91c-119">일부 인수는 튜플에 있고 일부는 그렇지 않은 경우 결합 된 폼을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="1f91c-120">다른 패턴은 매개 변수 목록에서 사용할 수도 있지만 매개 변수 패턴이 가능한 모든 입력과 일치 하지 않는 경우 런타임에 불완전 하 게 일치 하는 항목이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="1f91c-121">예외 `MatchFailureException`는 인수 값이 매개 변수 목록에 지정 된 패턴과 일치 하지 않는 경우에 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="1f91c-122">컴파일러는 매개 변수 패턴에서 불완전 한 일치 항목을 허용할 때 경고를 발생 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="1f91c-123">하나 이상의 다른 패턴은 일반적으로 매개 변수 목록에 유용 하며 와일드 카드 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="1f91c-124">제공 된 인수를 무시 하려는 경우에는 매개 변수 목록에서 와일드 카드 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="1f91c-125">다음 코드에서는 인수 목록에서 와일드 카드 패턴을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="1f91c-126">와일드 카드 패턴은 다음 코드와 같이 일반적으로 문자열 배열로 제공 되는 명령줄 인수에 관심이 없는 경우에 전달 된 인수가 필요 하지 않을 때마다 유용할 수 있습니다 (예: 프로그램에 대 한 기본 진입점).</span><span class="sxs-lookup"><span data-stu-id="1f91c-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="1f91c-127">인수에 사용 되는 다른 패턴은 `as` 패턴 및 구분 된 공용 구조체와 활성 패턴과 관련 된 식별자 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="1f91c-128">다음과 같이 단일 대/소문자 구분 된 공용 구조체 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="1f91c-129">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-129">The output is as follows.</span></span>

```console
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="1f91c-130">활성 패턴은 예를 들어 다음 예제와 같이 인수를 원하는 형식으로 변환 하는 경우 매개 변수로 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="1f91c-131">다음 코드 줄에 표시 된 것 처럼 `as` 패턴을 사용 하 여 일치 하는 값을 로컬 값으로 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="1f91c-132">때때로 사용 되는 다른 패턴은 함수의 본문으로 암시적 인수에서 패턴 일치를 즉시 수행 하는 람다 식을 제공 하 여 명명 되지 않은 마지막 인수를 유지 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="1f91c-133">이에 대 한 예제는 다음 코드 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="1f91c-134">이 코드는 제네릭 목록을 사용 하는 함수를 정의 하 고 목록이 비어 있는 경우 `true`을 반환 하 고, 그렇지 않으면 `false` 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="1f91c-135">이러한 기술을 사용 하면 코드를 읽기가 더 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="1f91c-136">때로는 불완전 한 일치 항목을 포함 하는 패턴이 유용 합니다. 예를 들어 프로그램의 목록에 요소가 세 개만 있는 경우에는 매개 변수 목록에서 다음과 같은 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="1f91c-137">불완전 한 일치 항목이 있는 패턴의 사용은 빠른 프로토타입 및 기타 임시 용도로 사용 하기에 가장 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="1f91c-138">컴파일러는 이러한 코드에 대 한 경고를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="1f91c-139">이러한 패턴은 가능한 모든 입력의 일반적인 경우를 포함할 수 없으므로 구성 요소 Api에 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="1f91c-140">명명된 인수</span><span class="sxs-lookup"><span data-stu-id="1f91c-140">Named Arguments</span></span>

<span data-ttu-id="1f91c-141">메서드에 대 한 인수는 쉼표로 구분 된 인수 목록에서 위치로 지정 하거나, 이름, 앞에 등호 및 전달 될 값을 제공 하 여 명시적으로 메서드에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="1f91c-142">이름을 제공 하 여 지정 하는 경우 선언에 사용 된 것과 다른 순서로 표시 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="1f91c-143">명명 된 인수를 사용 하면 메서드 매개 변수를 다시 정렬 하는 등 API의 특정 변경 내용에 대 한 코드를 더 읽기 쉽고 더 쉽게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="1f91c-144">명명 된 인수는 `let`바인딩된 함수, 함수 값 또는 람다 식이 아닌 메서드에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="1f91c-145">다음 코드 예제에서는 명명 된 인수를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="1f91c-146">클래스 생성자에 대 한 호출에서 명명 된 인수의 구문과 유사한 구문을 사용 하 여 클래스의 속성 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="1f91c-147">다음 예제에서는이 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="1f91c-148">자세한 내용은 [생성자 (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1f91c-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="1f91c-149">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f91c-149">Optional Parameters</span></span>

<span data-ttu-id="1f91c-150">매개 변수 이름 앞에 물음표를 사용 하 여 메서드에 대 한 선택적 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="1f91c-151">선택적 매개 변수는 F# 옵션 유형으로 해석 되므로 `Some` 및 `None`에 `match` 식을 사용 하 여 옵션 유형을 쿼리 하는 일반적인 방법으로 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="1f91c-152">선택적 매개 변수는 `let` 바인딩을 사용 하 여 만든 함수가 아닌 멤버에만 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="1f91c-153">`?arg=None` 또는 `?arg=Some(3)` 또는 `?arg=arg`와 같은 매개 변수 이름을 통해 메서드에 기존 선택적 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="1f91c-154">이는 다른 메서드에 선택적 인수를 전달 하는 메서드를 작성할 때 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="1f91c-155">선택적 인수의 기본값을 설정 하는 함수 `defaultArg`사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="1f91c-156">`defaultArg` 함수는 선택적 매개 변수를 첫 번째 인수로 사용 하 고 기본값을 두 번째 인수로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="1f91c-157">다음 예에서는 선택적 매개 변수를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="1f91c-158">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-158">The output is as follows.</span></span>

```console
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="1f91c-159">C# 및 Visual Basic interop를 위해에서 F#`[<Optional; DefaultParameterValue<(...)>]` 특성을 사용할 수 있으므로 호출자가 인수를 선택적으로 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="1f91c-160">이는 `MyMethod(int i = 3)`에서 C# 와 같이 인수를 선택적으로 정의 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="1f91c-161">새 개체를 기본 매개 변수 값으로 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="1f91c-162">예를 들어 `Foo` 멤버는 대신 선택적인 `CancellationToken`를 입력할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-162">For example, the `Foo` member could have an optional `CancellationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="1f91c-163">`DefaultParameterValue` 인수로 지정 된 값은 매개 변수의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="1f91c-164">예를 들어 다음은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="1f91c-165">이 경우 컴파일러는 경고를 생성 하 고 두 특성을 모두 무시 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="1f91c-166">컴파일러가 잘못 된 형식 (예: `[<Optional; DefaultParameterValue(null:obj)>] o:obj`를 유추 하는 것 처럼 `null` 기본값은 형식으로 주석을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="1f91c-167">참조로 전달</span><span class="sxs-lookup"><span data-stu-id="1f91c-167">Passing by Reference</span></span>

<span data-ttu-id="1f91c-168">참조로 F# 값을 전달 하는 데는 관리 되는 포인터 형식인 [byref 배열과 같은](byrefs.md)이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="1f91c-169">사용할 형식에 대 한 지침은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-169">Guidance for which type to use is as follows:</span></span>

- <span data-ttu-id="1f91c-170">포인터를 읽기만 하면 `inref<'T>`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
- <span data-ttu-id="1f91c-171">포인터에만 써야 하는 경우 `outref<'T>`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
- <span data-ttu-id="1f91c-172">포인터에 대 한 읽기 및 쓰기를 모두 수행 해야 하는 경우 `byref<'T>`를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

let test () =
    // No need to make it mutable, since it's read-only
    let x = 1
    example1 &x

    // Needs to be mutable, since we write to it
    let mutable y = 2
    example2 &y
    example3 &y // Now 'y' is 3
```

<span data-ttu-id="1f91c-173">매개 변수는 포인터이 고 값은 변경할 수 있으므로 값에 대 한 모든 변경 내용은 함수를 실행 한 후에도 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="1f91c-174">튜플을 반환 값으로 사용 하 여 .NET 라이브러리 메서드에서 `out` 매개 변수를 저장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="1f91c-175">또는 `out` 매개 변수를 `byref` 매개 변수로 취급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="1f91c-176">다음 코드 예제에서는 두 가지 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="1f91c-177">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="1f91c-177">Parameter Arrays</span></span>

<span data-ttu-id="1f91c-178">경우에 따라 형식이 다른 형식의 매개 변수를 임의로 사용 하는 함수를 정의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="1f91c-179">사용 가능한 모든 형식을 고려 하는 오버 로드 된 모든 메서드를 만드는 것은 실용적이 지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="1f91c-180">.NET 구현은 매개 변수 배열 기능을 통해 이러한 메서드에 대 한 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="1f91c-181">시그니처에 매개 변수 배열을 사용 하는 메서드는 임의의 수의 매개 변수를 사용 하 여 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="1f91c-182">매개 변수는 배열에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-182">The parameters are put into an array.</span></span> <span data-ttu-id="1f91c-183">배열 요소의 형식은 함수에 전달 될 수 있는 매개 변수 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="1f91c-184">`System.Object`를 요소 형식으로 사용 하 여 매개 변수 배열을 정의 하는 경우 클라이언트 코드는 모든 형식의 값을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="1f91c-185">에서 F#매개 변수 배열은 메서드에만 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="1f91c-186">모듈에 정의 된 독립 실행형 함수 또는 함수에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="1f91c-187">`ParamArray` 특성을 사용 하 여 매개 변수 배열을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="1f91c-188">`ParamArray` 특성은 마지막 매개 변수에만 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="1f91c-189">다음 코드에서는 매개 변수 배열을 사용 하는 .NET 메서드를 호출 하는 방법과에서 F# 매개 변수 배열을 사용 하는 메서드가 있는 형식의 정의를 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="1f91c-190">프로젝트에서 실행 하는 경우 이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1f91c-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="1f91c-191">참조</span><span class="sxs-lookup"><span data-stu-id="1f91c-191">See also</span></span>

- [<span data-ttu-id="1f91c-192">멤버</span><span class="sxs-lookup"><span data-stu-id="1f91c-192">Members</span></span>](./members/index.md)
