---
title: 매개 변수 및 인수
description: 에 대해 알아봅니다 F# 매개 변수를 정의 하 고 함수, 메서드 및 속성에 인수를 전달 하기 위한 언어 지원 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: b68b3fdd14a66a7312efa5adb709adaeceaae282
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352285"
---
# <a name="parameters-and-arguments"></a><span data-ttu-id="d4d3d-103">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="d4d3d-103">Parameters and Arguments</span></span>

<span data-ttu-id="d4d3d-104">이 항목에는 매개 변수를 정의 하 고 함수, 메서드 및 속성에 인수 전달에 대 한 언어 지원을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-104">This topic describes language support for defining parameters and passing arguments to functions, methods, and properties.</span></span> <span data-ttu-id="d4d3d-105">참조로 전달 하는 방법 및 정의 하는 가변 개수의 인수를 사용할 수 있는 메서드를 사용 하는 방법에 대 한 정보를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-105">It includes information about how to pass by reference, and how to define and use methods that can take a variable number of arguments.</span></span>

## <a name="parameters-and-arguments"></a><span data-ttu-id="d4d3d-106">매개 변수 및 인수</span><span class="sxs-lookup"><span data-stu-id="d4d3d-106">Parameters and Arguments</span></span>

<span data-ttu-id="d4d3d-107">용어 *매개 변수* 제공 해야 하는 값의 이름을 설명 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-107">The term *parameter* is used to describe the names for values that are expected to be supplied.</span></span> <span data-ttu-id="d4d3d-108">용어 *인수* 각 매개 변수에 대해 제공 된 값에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-108">The term *argument* is used for the values provided for each parameter.</span></span>

<span data-ttu-id="d4d3d-109">튜플 또는 변환된 형식 또는 둘의 조합에서 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-109">Parameters can be specified in tuple or curried form, or in some combination of the two.</span></span> <span data-ttu-id="d4d3d-110">명시적 매개 변수 이름을 사용 하 여 인수를 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-110">You can pass arguments by using an explicit parameter name.</span></span> <span data-ttu-id="d4d3d-111">메서드의 매개 변수 선택적으로 지정 하 고 기본 값이 지정 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-111">Parameters of methods can be specified as optional and given a default value.</span></span>

## <a name="parameter-patterns"></a><span data-ttu-id="d4d3d-112">매개 변수 패턴</span><span class="sxs-lookup"><span data-stu-id="d4d3d-112">Parameter Patterns</span></span>

<span data-ttu-id="d4d3d-113">함수 및 메서드를 제공 하는 매개 변수는 일반적으로 공백으로 구분 하는 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-113">Parameters supplied to functions and methods are, in general, patterns separated by spaces.</span></span> <span data-ttu-id="d4d3d-114">이 원칙적으로 된 패턴에 설명 된 것을 의미 [일치 식](match-expressions.md) 함수 또는 멤버에 대 한 매개 변수 목록에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-114">This means that, in principle, any of the patterns described in [Match Expressions](match-expressions.md) can be used in a parameter list for a function or member.</span></span>

<span data-ttu-id="d4d3d-115">메서드는 일반적으로 인수 전달 튜플 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-115">Methods usually use the tuple form of passing arguments.</span></span> <span data-ttu-id="d4d3d-116">튜플 형식 인수가.NET 메서드에 전달 되는 방법은 일치 하기 때문에 다른.NET 언어의 관점에서 명확 하 게 결과 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-116">This achieves a clearer result from the perspective of other .NET languages because the tuple form matches the way arguments are passed in .NET methods.</span></span>

<span data-ttu-id="d4d3d-117">커리 된 양식을 사용 하 여 만든 함수를 사용 하 여 사용할 가장 자주 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-117">The curried form is most often used with functions created by using `let` bindings.</span></span>

<span data-ttu-id="d4d3d-118">다음 의사 코드 예제에서는 튜플 및 커리 된 인수를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-118">The following pseudocode shows examples of tuple and curried arguments.</span></span>

```fsharp
// Tuple form.
member this.SomeMethod(param1, param2) = ...
// Curried form.
let function1 param1 param2 = ...
```

<span data-ttu-id="d4d3d-119">일부 인수 튜플을에 있으며 일부 경우 결합 된 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-119">Combined forms are possible when some arguments are in tuples and some are not.</span></span>

```fsharp
let function2 param1 (param2a, param2b) param3 = ...
```

<span data-ttu-id="d4d3d-120">매개 변수 목록의 다른 패턴도 사용할 수 있지만 매개 변수 패턴을 모든 사용 가능한 입력에 일치 하지 않는 경우 있을 불완전 한 일치 하는 런타임 시.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-120">Other patterns can also be used in parameter lists, but if the parameter pattern does not match all possible inputs, there might be an incomplete match at run time.</span></span> <span data-ttu-id="d4d3d-121">예외 `MatchFailureException` 인수의 값 매개 변수 목록에 지정 된 패턴과 일치 하지 않는 경우 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-121">The exception `MatchFailureException` is generated when the value of an argument does not match the patterns specified in the parameter list.</span></span> <span data-ttu-id="d4d3d-122">불완전 한 일치 항목에 대 한 매개 변수 패턴을 사용 하면 컴파일러가 경고 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-122">The compiler issues a warning when a parameter pattern allows for incomplete matches.</span></span> <span data-ttu-id="d4d3d-123">다른 패턴은 하나 이상의 매개 변수 목록에 대 한 일반적으로 유용 하 고 와일드 카드 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-123">At least one other pattern is commonly useful for parameter lists, and that is the wildcard pattern.</span></span> <span data-ttu-id="d4d3d-124">제공 되는 인수를 무시 하려는 경우 매개 변수 목록에서 와일드 카드 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-124">You use the wildcard pattern in a parameter list when you simply want to ignore any arguments that are supplied.</span></span> <span data-ttu-id="d4d3d-125">다음 코드는 인수 목록에서 와일드 카드 패턴의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-125">The following code illustrates the use of the wildcard pattern in an argument list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3801.fs)]

<span data-ttu-id="d4d3d-126">와일드 카드 패턴은 일반적으로 다음 코드와 같이 문자열 배열로 제공 되는 명령줄 인수에 관심이 없는 경우 전달 된 인수를 수행 해야 할 때 유용 하 고, 프로그램의 주 진입점 같이 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-126">The wildcard pattern can be useful whenever you do not need the arguments passed in, such as in the main entry point to a program, when you are not interested in the command-line arguments that are normally supplied as a string array, as in the following code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3802.fs)]

<span data-ttu-id="d4d3d-127">인수에 자주 사용 되는 다른 패턴은 `as` 구별 된 공용 구조체 및 활성 패턴을 사용 하 여 연결 된 식별자 패턴과 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-127">Other patterns that are sometimes used in arguments are the `as` pattern, and identifier patterns associated with discriminated unions and active patterns.</span></span> <span data-ttu-id="d4d3d-128">다음과 같이 단일 사례 구별 된 공용 구조체 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-128">You can use the single-case discriminated union pattern as follows.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3803.fs)]

<span data-ttu-id="d4d3d-129">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-129">The output is as follows.</span></span>

```
Data begins at 0 and ends at 4 in string Et tu, Brute?
Et tu
```

<span data-ttu-id="d4d3d-130">원하는 형식으로 다음 예제와 같이 인수가 변환 하는 경우에 활성 패턴 예를 들어, 매개 변수로 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-130">Active patterns can be useful as parameters, for example, when transforming an argument into a desired format, as in the following example:</span></span>

```fsharp
type Point = { x : float; y : float }

let (| Polar |) { x = x; y = y} =
    ( sqrt (x*x + y*y), System.Math.Atan (y/ x) )

let radius (Polar(r, _)) = r
let angle (Polar(_, theta)) = theta
```

<span data-ttu-id="d4d3d-131">사용할 수는 `as` 코드의 다음 줄에 표시 된 대로 로컬 값으로 일치 하는 값을 저장 하는 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-131">You can use the `as` pattern to store a matched value as a local value, as is shown in the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3805.fs)]

<span data-ttu-id="d4d3d-132">가끔씩 사용 되는 또 다른 패턴에 마지막 인수는 함수 본문으로 제공 하 여 명명 되지 않은 상태로 유지 하는 함수를 즉시 암시적 인수에 패턴 일치를 수행 하는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-132">Another pattern that is used occasionally is a function that leaves the last argument unnamed by providing, as the body of the function, a lambda expression that immediately performs a pattern match on the implicit argument.</span></span> <span data-ttu-id="d4d3d-133">이러한 예로 다음 코드 줄.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-133">An example of this is the following line of code.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3804.fs)]

<span data-ttu-id="d4d3d-134">이 코드는 제네릭 목록을 반환 하는 함수를 정의 `true` 목록이 비어 있으면 및 `false` 그렇지 않은 경우.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-134">This code defines a function that takes a generic list and returns `true` if the list is empty, and `false` otherwise.</span></span> <span data-ttu-id="d4d3d-135">이러한 기술의 사용 가능 코드를 읽기가 어려울 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-135">The use of such techniques can make code more difficult to read.</span></span>

<span data-ttu-id="d4d3d-136">경우에 따라 불완전 한 일치 항목을 포함 하는 패턴은 유용, 예를 들어 프로그램에서 목록 있는 세 개의 요소를 알고 있는 경우 사용할 수 있습니다 다음과 같은 패턴을 매개 변수 목록.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-136">Occasionally, patterns that involve incomplete matches are useful, for example, if you know that the lists in your program have only three elements, you might use a pattern like the following in a parameter list.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3806.fs)]

<span data-ttu-id="d4d3d-137">불완전 한 일치 하는 패턴도 사용 빠른 프로토타입 및 기타 임시 사용 하 여 가장 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-137">The use of patterns that have incomplete matches is best reserved for quick prototyping and other temporary uses.</span></span> <span data-ttu-id="d4d3d-138">컴파일러에서 이러한 코드에 대 한 경고가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-138">The compiler will issue a warning for such code.</span></span> <span data-ttu-id="d4d3d-139">이러한 패턴은 가능한 모든 입력의 일반적인 사례를 다룰 수는 없습니다 및 Api 구성 요소에 대해 적합 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-139">Such patterns cannot cover the general case of all possible inputs and therefore are not suitable for component APIs.</span></span>

## <a name="named-arguments"></a><span data-ttu-id="d4d3d-140">명명된 인수</span><span class="sxs-lookup"><span data-stu-id="d4d3d-140">Named Arguments</span></span>

<span data-ttu-id="d4d3d-141">메서드에 대 한 인수는 쉼표로 구분 된 인수 목록에서 위치에 따라 지정할 수 있습니다 또는 전달할 수는 메서드를 명시적으로 뒤에 등호와 값을 전달 해야 하는 이름을 제공 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-141">Arguments for methods can be specified by position in a comma-separated argument list, or they can be passed to a method explicitly by providing the name, followed by an equal sign and the value to be passed in.</span></span> <span data-ttu-id="d4d3d-142">이름을 제공 하 여 지정 하는 경우에 선언에 사용 되는 다른 순서로 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-142">If specified by providing the name, they can appear in a different order from that used in the declaration.</span></span>

<span data-ttu-id="d4d3d-143">명명 된 인수 가능 코드 가독성 및 보다 융통성 있는 특정 형식의 메서드 매개 변수의 순서를 바꾸는 등의 API 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-143">Named arguments can make code more readable and more adaptable to certain types of changes in the API, such as a reordering of method parameters.</span></span>

<span data-ttu-id="d4d3d-144">명명 된 인수를 사용할 수 방법에 대해서만 아니라 `let`-바인딩된 함수, 함수 값 또는 람다 식입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-144">Named arguments are allowed only for methods, not for `let`-bound functions, function values, or lambda expressions.</span></span>

<span data-ttu-id="d4d3d-145">다음 코드 예제에서는 명명 된 인수의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-145">The following code example demonstrates the use of named arguments.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3807.fs)]

<span data-ttu-id="d4d3d-146">클래스 생성자 호출에서 명명 된 인수는 유사한 구문을 사용 하 여 클래스의 속성 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-146">In a call to a class constructor, you can set the values of properties of the class by using a syntax similar to that of named arguments.</span></span> <span data-ttu-id="d4d3d-147">다음 예제에서는이 구문을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-147">The following example shows this syntax.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet3506.fs)]

<span data-ttu-id="d4d3d-148">자세한 내용은 [생성자 (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05)합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-148">For more information, see [Constructors (F#)](https://msdn.microsoft.com/library/2cd0ed07-d214-4125-8317-4f288af99f05).</span></span>

## <a name="optional-parameters"></a><span data-ttu-id="d4d3d-149">선택적 매개 변수</span><span class="sxs-lookup"><span data-stu-id="d4d3d-149">Optional Parameters</span></span>

<span data-ttu-id="d4d3d-150">매개 변수 이름 앞에 물음표를 사용 하 여 메서드에 대 한 선택적 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-150">You can specify an optional parameter for a method by using a question mark in front of the parameter name.</span></span> <span data-ttu-id="d4d3d-151">선택적 매개 변수로 해석 됩니다는 F# 를 사용 하 여 옵션 형식 쿼리는 정상적인 방법으로 쿼리할 수 있도록 형식 옵션을 `match` 식을 `Some` 및 `None`.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-151">Optional parameters are interpreted as the F# option type, so you can query them in the regular way that option types are queried, by using a `match` expression with `Some` and `None`.</span></span> <span data-ttu-id="d4d3d-152">선택적 매개 변수를 사용 하 여 만든 함수에 없는 멤버에 대해서만 허용 됩니다 `let` 바인딩.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-152">Optional parameters are permitted only on members, not on functions created by using `let` bindings.</span></span>

<span data-ttu-id="d4d3d-153">값을 전달할 수 기존 선택적 메서드에 매개 변수 이름으로 같은 `?arg=None` 나 `?arg=Some(3)` 또는 `?arg=arg`합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-153">You can pass existing optional values to method by parameter name, such as `?arg=None` or `?arg=Some(3)` or `?arg=arg`.</span></span> <span data-ttu-id="d4d3d-154">이 기능은 다른 메서드에 선택적 인수를 전달 하는 메서드를 작성 하는 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-154">This can be useful when building a method that passes optional arguments to another method.</span></span>

<span data-ttu-id="d4d3d-155">함수를 사용할 수도 있습니다 `defaultArg`, 선택적 인수의 기본값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-155">You can also use a function `defaultArg`, which sets a default value of an optional argument.</span></span> <span data-ttu-id="d4d3d-156">`defaultArg` 함수는 첫 번째 인수는 선택적 매개 변수와 두 번째 기본 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-156">The `defaultArg` function takes the optional parameter as the first argument and the default value as the second.</span></span>

<span data-ttu-id="d4d3d-157">다음 예에서는 선택적 매개 변수의 사용을 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-157">The following example illustrates the use of optional parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3808.fs)]

<span data-ttu-id="d4d3d-158">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-158">The output is as follows.</span></span>

```
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
Baud Rate: 300 Duplex: Half Parity: true
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 9600 Duplex: Full Parity: false
Baud Rate: 4800 Duplex: Half Parity: false
```

<span data-ttu-id="d4d3d-159">위해 C# 및 Visual Basic interop 특성을 사용할 수 있습니다 `[<Optional; DefaultParameterValue<(...)>]` 에서 F#호출자는 선택 사항으로 인수로 표시 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-159">For the purposes of C# and Visual Basic interop you can use the attributes `[<Optional; DefaultParameterValue<(...)>]` in F#, so that callers will see an argument as optional.</span></span> <span data-ttu-id="d4d3d-160">이 해당 인수에 선택적으로 정의 하는 C# 에서처럼 `MyMethod(int i = 3)`합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-160">This is equivalent to defining the argument as optional in C# as in `MyMethod(int i = 3)`.</span></span>

```fsharp
open System
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue("Hello world")>] message) =
        printfn "%s" message
```

<span data-ttu-id="d4d3d-161">또한 기본 매개 변수 값으로 새 개체를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-161">You can also specify a new object as a default parameter value.</span></span> <span data-ttu-id="d4d3d-162">예를 들어 합니다 `Foo` 멤버는 선택적인 있을 수 있습니다 `CancellationToken` 대신 입력으로:</span><span class="sxs-lookup"><span data-stu-id="d4d3d-162">For example, the `Foo` member could have an optional `CancellationToken` as input instead:</span></span>

```fsharp
open System.Threading
open System.Runtime.InteropServices
type C =
    static member Foo([<Optional; DefaultParameterValue(CancellationToken())>] ct: CancellationToken) =
        printfn "%A" ct
```

<span data-ttu-id="d4d3d-163">인수로 지정 된 값 `DefaultParameterValue` 매개 변수의 형식과 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-163">The value given as argument to `DefaultParameterValue` must match the type of the parameter.</span></span> <span data-ttu-id="d4d3d-164">예를 들어, 다음은 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-164">For example, the following is not allowed:</span></span>

```fsharp
type C =
    static member Wrong([<Optional; DefaultParameterValue("string")>] i:int) = ()
```

<span data-ttu-id="d4d3d-165">이 경우 컴파일러는 경고를 생성 하 고 두 특성 모두 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-165">In this case, the compiler generates a warning and will ignore both attributes altogether.</span></span> <span data-ttu-id="d4d3d-166">기본값이 `null` 형식 주석이 지정 해야 경우 컴파일러에서 유추 잘못 된 형식, 즉 `[<Optional; DefaultParameterValue(null:obj)>] o:obj`합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-166">Note that the default value `null` needs to be type-annotated, as otherwise the compiler infers the wrong type, i.e. `[<Optional; DefaultParameterValue(null:obj)>] o:obj`.</span></span>

## <a name="passing-by-reference"></a><span data-ttu-id="d4d3d-167">참조로 전달</span><span class="sxs-lookup"><span data-stu-id="d4d3d-167">Passing by Reference</span></span>

<span data-ttu-id="d4d3d-168">전달는 F# 참조로 값이 포함 됩니다 [byref](byrefs.md), 관리 되는 포인터 형식은입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-168">Passing an F# value by reference involves [byrefs](byrefs.md), which are managed pointer types.</span></span> <span data-ttu-id="d4d3d-169">다음과 같이 형식을 사용 하는 지침:</span><span class="sxs-lookup"><span data-stu-id="d4d3d-169">Guidance for which type to use is as follows:</span></span>

* <span data-ttu-id="d4d3d-170">사용 하 여 `inref<'T>` 포인터를 읽을 수만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-170">Use `inref<'T>` if you only need to read the pointer.</span></span>
* <span data-ttu-id="d4d3d-171">사용 하 여 `outref<'T>` 포인터에 대 한 작성 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-171">Use `outref<'T>` if you only need to write to the pointer.</span></span>
* <span data-ttu-id="d4d3d-172">사용 하 여 `byref<'T>` 에서 읽기 및 포인터에 대 한 쓰기 해야 할 경우.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-172">Use `byref<'T>` if you need to both read from and write to the pointer.</span></span>

```fsharp
let example1 (x: inref<int>) = printfn "It's %d" x

let example2 (x: outref<int>) = x <- x + 1

let example3 (x: byref<int>) =
    printfn "It'd %d" x
    x <- x + 1

// No need to make it mutable, since it's read-only
let x = 1
example1 &x

// Needs to be mutable, since we write to it
let mutable y = 2
example2 &y
example3 &y // Now 'y' is 3
```

<span data-ttu-id="d4d3d-173">매개 변수가 포인터가 고 값은 변경할 수 있으므로 모든 값을 변경 하는 함수의 실행 한 후 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-173">Because the parameter is a pointer and the value is mutable, any changes to the value are retained after the execution of the function.</span></span>

<span data-ttu-id="d4d3d-174">튜플을 반환 값으로 하 여 저장 `out` .NET 라이브러리 메서드의 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-174">You can use a tuple as a return value to store any `out` parameters in .NET library methods.</span></span> <span data-ttu-id="d4d3d-175">처리할 수 있습니다 합니다 `out` 매개 변수는 `byref` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-175">Alternatively, you can treat the `out` parameter as a `byref` parameter.</span></span> <span data-ttu-id="d4d3d-176">다음 코드 예제에서는 두 가지 방법을 모두 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-176">The following code example illustrates both ways.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-1/snippet3810.fs)]

## <a name="parameter-arrays"></a><span data-ttu-id="d4d3d-177">매개 변수 배열</span><span class="sxs-lookup"><span data-stu-id="d4d3d-177">Parameter Arrays</span></span>

<span data-ttu-id="d4d3d-178">임의 개수의 유형이 다른 형식의 매개 변수를 사용 하는 함수를 정의 해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-178">Occasionally it is necessary to define a function that takes an arbitrary number of parameters of heterogeneous type.</span></span> <span data-ttu-id="d4d3d-179">사용할 수 있는 모든 형식에 대 한 계정에 가능한 모든 오버 로드 된 메서드를 만드는 유용 하지 것입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-179">It would not be practical to create all the possible overloaded methods to account for all the types that could be used.</span></span> <span data-ttu-id="d4d3d-180">매개 변수 배열 기능을 통해 이러한 메서드에 대 한 지원을 제공 하는.NET 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-180">The .NET implementations provide support for such methods through the parameter array feature.</span></span> <span data-ttu-id="d4d3d-181">임의 개수의 매개 변수를 사용 하 여 해당 시그니처에서 매개 변수 배열을 사용 하는 메서드를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-181">A method that takes a parameter array in its signature can be provided with an arbitrary number of parameters.</span></span> <span data-ttu-id="d4d3d-182">매개 변수 배열에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-182">The parameters are put into an array.</span></span> <span data-ttu-id="d4d3d-183">함수에 전달 될 수 있는 매개 변수 유형이 결정 하는 배열 요소의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-183">The type of the array elements determines the parameter types that can be passed to the function.</span></span> <span data-ttu-id="d4d3d-184">매개 변수 배열을 정의 하는 경우 `System.Object` 요소 형식으로 클라이언트 코드 수 전달한 모든 형식의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-184">If you define the parameter array with `System.Object` as the element type, then client code can pass values of any type.</span></span>

<span data-ttu-id="d4d3d-185">F#을 매개 변수 배열 메서드에서만에서 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-185">In F#, parameter arrays can only be defined in methods.</span></span> <span data-ttu-id="d4d3d-186">독립 실행형 함수 또는 모듈에 정의 된 함수에서 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-186">They cannot be used in standalone functions or functions that are defined in modules.</span></span>

<span data-ttu-id="d4d3d-187">매개 변수 배열을 사용 하 여 정의한는 `ParamArray` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-187">You define a parameter array by using the `ParamArray` attribute.</span></span> <span data-ttu-id="d4d3d-188">`ParamArray` 특성은 마지막 매개 변수에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-188">The `ParamArray` attribute can only be applied to the last parameter.</span></span>

<span data-ttu-id="d4d3d-189">다음 코드에서 형식 정의와 매개 변수 배열을 사용 하는.NET 메서드를 호출 하는 방법을 보여 줍니다 F# 매개 변수 배열을 사용 하는 메서드가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-189">The following code illustrates both calling a .NET method that takes a parameter array and the definition of a type in F# that has a method that takes a parameter array.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/parameters-and-arguments-2/snippet3811.fs)]

<span data-ttu-id="d4d3d-190">프로젝트를 실행 하는 경우 이전 코드의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d3d-190">When run in a project, the output of the previous code is as follows:</span></span>

```console
a 1 10 Hello world 1 True
"a"
1
10.0
"Hello world"
1u
true
```

## <a name="see-also"></a><span data-ttu-id="d4d3d-191">참고자료</span><span class="sxs-lookup"><span data-stu-id="d4d3d-191">See also</span></span>

- [<span data-ttu-id="d4d3d-192">멤버</span><span class="sxs-lookup"><span data-stu-id="d4d3d-192">Members</span></span>](members/index.md)
