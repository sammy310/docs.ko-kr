---
title: F# 코드 서식 지정 지침
description: F# 코드 서식 지정에 대한 지침을 알아봅니다.
ms.date: 11/04/2019
ms.openlocfilehash: b8be70dd29a04e71614308164e541b99a1724305
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81739561"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="072dd-103">F# 코드 서식 지정 지침</span><span class="sxs-lookup"><span data-stu-id="072dd-103">F# code formatting guidelines</span></span>

<span data-ttu-id="072dd-104">이 문서에서는 F# 코드가 다음과 같은지 코드를 포맷하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="072dd-105">더 읽기 쉬운</span><span class="sxs-lookup"><span data-stu-id="072dd-105">More legible</span></span>
* <span data-ttu-id="072dd-106">Visual Studio 및 기타 편집기에서 도구를 포맷하여 적용하는 규칙에 따라</span><span class="sxs-lookup"><span data-stu-id="072dd-106">In accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="072dd-107">온라인의 다른 코드와 유사</span><span class="sxs-lookup"><span data-stu-id="072dd-107">Similar to other code online</span></span>

<span data-ttu-id="072dd-108">이 지침은 [안둥 판에](https://github.com/dungpa)의해 F # 서식 규칙에 대한 [포괄적 인 가이드를 기반으로합니다.](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md)</span><span class="sxs-lookup"><span data-stu-id="072dd-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="072dd-109">들여쓰기에 대한 일반 규칙</span><span class="sxs-lookup"><span data-stu-id="072dd-109">General rules for indentation</span></span>

<span data-ttu-id="072dd-110">F#은 기본적으로 상당한 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-110">F# uses significant white space by default.</span></span> <span data-ttu-id="072dd-111">다음 지침은 이로 인해 부과될 수 있는 몇 가지 문제를 저글링하는 방법에 대한 지침을 제공하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="072dd-112">공백 사용</span><span class="sxs-lookup"><span data-stu-id="072dd-112">Using spaces</span></span>

<span data-ttu-id="072dd-113">들여쓰기가 필요한 경우 탭이 아닌 공백을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="072dd-114">하나 이상의 공간이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-114">At least one space is required.</span></span> <span data-ttu-id="072dd-115">조직에서 는 코딩 표준을 만들어 들여쓰기에 사용할 공백 수를 지정할 수 있습니다. 들여쓰기가 발생하는 각 수준에서 2, 3 또는 4개의 들여쓰기 공백이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three, or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="072dd-116">**들여쓰기당 4개의 공백을 권장합니다.**</span><span class="sxs-lookup"><span data-stu-id="072dd-116">**We recommend four spaces per indentation.**</span></span>

<span data-ttu-id="072dd-117">즉, 프로그램의 들여 쓰기는 주관적인 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="072dd-118">변형은 괜찮지만 따라야 할 첫 번째 규칙은 *들여쓰기의 일관성입니다.*</span><span class="sxs-lookup"><span data-stu-id="072dd-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="072dd-119">일반적으로 허용되는 들여쓰기 스타일을 선택하고 코드베이스 전체에서 체계적으로 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="072dd-120">공백 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-120">Formatting white space</span></span>

<span data-ttu-id="072dd-121">F#은 공백에 민감합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-121">F# is white space sensitive.</span></span> <span data-ttu-id="072dd-122">공백의 대부분의 의미 체계는 적절한 들여쓰기로 덮여 있지만 고려해야 할 몇 가지 다른 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="072dd-123">산술 식에서 연산자 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="072dd-124">항상 이진 산술 식 주위에 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="072dd-125">Unary `-` 연산자는 항상 부정하는 값 다음에 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-125">Unary `-` operators should always be immediately followed by the value they are negating:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="072dd-126">`-` 연산자 후에 공백 문자를 추가하면 다른 사람에게 혼동을 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="072dd-127">요약하자면, 항상 다음을 하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="072dd-128">공백으로 이진 연산자 서라운드</span><span class="sxs-lookup"><span data-stu-id="072dd-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="072dd-129">어설프게 연산자 후 후행 공백이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="072dd-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="072dd-130">이진 산술 연산자 지침은 특히 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="072dd-131">이진 `-` 연산자 를 둘러싸지 못하면 특정 서식 선택 과 결합하면 이연산자로 해석될 수 `-`있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="072dd-132">공백으로 사용자 지정 연산자 정의 둘러싸기</span><span class="sxs-lookup"><span data-stu-id="072dd-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="072dd-133">항상 공백을 사용하여 연산자 정의를 둘러싸는다.</span><span class="sxs-lookup"><span data-stu-id="072dd-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="072dd-134">시작되고 `*` 두 개 이상의 문자가 있는 사용자 지정 연산자의 경우 컴파일러 모호성을 피하기 위해 정의의 시작 부분에 공백을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="072dd-135">따라서 모든 연산자의 정의를 단일 공백 문자로 둘러싸는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="072dd-136">공백이 있는 서라운드 기능 매개변수 화살표</span><span class="sxs-lookup"><span data-stu-id="072dd-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="072dd-137">함수의 서명을 정의할 때 기호 주위에 `->` 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="072dd-138">공백이 있는 서라운드 함수 인수</span><span class="sxs-lookup"><span data-stu-id="072dd-138">Surround function arguments with white space</span></span>

<span data-ttu-id="072dd-139">함수를 정의할 때 각 인수 주위에 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a><span data-ttu-id="072dd-140">긴 멤버 정의를 위해 새 줄에 매개변수 배치</span><span class="sxs-lookup"><span data-stu-id="072dd-140">Place parameters on a new line for long member definitions</span></span>

<span data-ttu-id="072dd-141">멤버 정의가 매우 긴 경우 새 줄에 매개 변수를 배치하고 하나의 범위를 들여쓰기합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-141">If you have a very long member definition, place the parameters on new lines and indent them one scope.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(
        aVeryLongType: AVeryLongTypeThatYouNeedToUse
        aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
        aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="072dd-142">생성자에도 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-142">This also applies to constructors:</span></span>

```fsharp
type C(
    aVeryLongType: AVeryLongTypeThatYouNeedToUse
    aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse
    aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

### <a name="type-annotations"></a><span data-ttu-id="072dd-143">형식 주석</span><span class="sxs-lookup"><span data-stu-id="072dd-143">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="072dd-144">오른쪽 패드 함수 인수 형식 주석</span><span class="sxs-lookup"><span data-stu-id="072dd-144">Right-pad function argument type annotations</span></span>

<span data-ttu-id="072dd-145">형식 주석으로 인수를 정의할 때 기호 다음 `:` 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-145">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="072dd-146">공백이 있는 서라운드 리턴 유형 주석</span><span class="sxs-lookup"><span data-stu-id="072dd-146">Surround return type annotations with white space</span></span>

<span data-ttu-id="072dd-147">let-bound 함수 또는 값 형식 어노션(함수의 경우 반환 형식)에서 기호 `:` 앞뒤의 공백을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-147">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="072dd-148">빈 줄 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-148">Formatting blank lines</span></span>

* <span data-ttu-id="072dd-149">최상위 함수와 클래스 정의를 두 개의 빈 줄로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-149">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="072dd-150">클래스 내의 메서드 정의는 한 줄로 구분됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-150">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="072dd-151">추가 빈 줄을 (아껴서) 관련 함수 그룹을 분리하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-151">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="072dd-152">빈 줄은 관련 한 줄(예: 더미 구현 집합)간에 생략될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-152">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="072dd-153">함수의 빈 줄을 아껴서 사용하여 논리 섹션을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-153">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="072dd-154">주석 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-154">Formatting comments</span></span>

<span data-ttu-id="072dd-155">일반적으로 ML 스타일 블록 주석보다 여러 개의 이중 슬래시 주석을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-155">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="072dd-156">인라인 주석은 첫 번째 문자를 대문자로 대문자로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-156">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="072dd-157">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="072dd-157">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="072dd-158">클래스 바인딩, 식 바인딩 및 패턴 바인딩된 값 및 함수에 camelCase 사용</span><span class="sxs-lookup"><span data-stu-id="072dd-158">Use camelCase for class-bound, expression-bound, and pattern-bound values and functions</span></span>

<span data-ttu-id="072dd-159">로컬 변수로 바인딩된 모든 이름또는 패턴 일치 및 함수 정의에 대해 camelCase를 사용하는 것이 일반적이고 허용되는 F# 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-159">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="072dd-160">클래스의 로컬 바인딩된 함수도 camelCase를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-160">Locally bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="072dd-161">모듈 바인딩 된 공용 기능에 대 한 낙 타 케이스를 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="072dd-161">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="072dd-162">모듈 바인딩 된 함수가 공용 API의 일부인 경우 camelCase를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-162">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="072dd-163">내부 및 개인 모듈 바인딩 값 및 함수에 camelCase 사용</span><span class="sxs-lookup"><span data-stu-id="072dd-163">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="072dd-164">다음을 포함하여 개인 모듈 바인딩 값에 camelCase를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-164">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="072dd-165">스크립트의 임시 함수</span><span class="sxs-lookup"><span data-stu-id="072dd-165">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="072dd-166">모듈 또는 형식의 내부 구현을 구성하는 값</span><span class="sxs-lookup"><span data-stu-id="072dd-166">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="072dd-167">매개 변수에 낙타 케이스 사용</span><span class="sxs-lookup"><span data-stu-id="072dd-167">Use camelCase for parameters</span></span>

<span data-ttu-id="072dd-168">모든 매개 변수는 .NET 명명 규칙에 따라 camelCase를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-168">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="072dd-169">모듈에 파스칼 케이스 사용</span><span class="sxs-lookup"><span data-stu-id="072dd-169">Use PascalCase for modules</span></span>

<span data-ttu-id="072dd-170">모든 모듈(최상위, 내부, 개인, 중첩)은 PascalCase를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-170">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="072dd-171">형식 선언, 멤버 및 레이블에 PascalCase 사용</span><span class="sxs-lookup"><span data-stu-id="072dd-171">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="072dd-172">클래스, 인터페이스, 구조체, 열거형, 대리자, 레코드 및 구별된 공용 구조체는 모두 PascalCase를 사용하여 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-172">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="072dd-173">레코드 및 차별된 공용 구조체에 대한 형식 및 레이블 내의 멤버도 PascalCase를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-173">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

```fsharp
type IMyInterface =
    abstract Something: int

type MyClass() =
    member this.MyMethod(x, y) = x + y

type MyRecord = { IntVal: int; StringVal: string }

type SchoolPerson =
    | Professor
    | Student
    | Advisor
    | Administrator
```

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="072dd-174">.NET에 내재된 구문에 파스칼 케이스 사용</span><span class="sxs-lookup"><span data-stu-id="072dd-174">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="072dd-175">네임스페이스, 예외, 이벤트 및`.dll` 프로젝트/이름도 PascalCase를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-175">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="072dd-176">이렇게 하면 다른 .NET 언어의 소비가 소비자에게 더 자연스럽게 느껴질 뿐만 아니라 발생할 가능성이 있는 .NET 명명 규칙과도 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-176">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="072dd-177">이름에 밑줄 을 피하기</span><span class="sxs-lookup"><span data-stu-id="072dd-177">Avoid underscores in names</span></span>

<span data-ttu-id="072dd-178">역사적으로 일부 F# 라이브러리는 이름에 밑줄을 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-178">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="072dd-179">그러나 .NET 명명 규칙과 충돌하기 때문에 더 이상 널리 받아들여지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-179">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="072dd-180">즉, 일부 F# 프로그래머는 역사적 이유로 부분적으로 강조를 사용하며 관용과 존중이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-180">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="072dd-181">그러나 스타일은 종종 그것을 사용할지 여부에 대한 선택의 여지가 다른 사람에 의해 싫어한다는 것을 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="072dd-181">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="072dd-182">한 가지 예외로는 밑줄이 일반적인 네이티브 구성 요소와의 상호 운용이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-182">One exception includes interoperating with native components, where underscores are common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="072dd-183">표준 F# 연산자 사용</span><span class="sxs-lookup"><span data-stu-id="072dd-183">Use standard F# operators</span></span>

<span data-ttu-id="072dd-184">다음 연산자는 F# 표준 라이브러리에 정의되어 있으며 등가물을 정의하는 대신 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-184">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="072dd-185">이러한 연산자는 코드를 더 읽기 쉽고 숙어적으로 만드는 경향이 있으므로 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-185">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="072dd-186">OCaml 또는 기타 함수형 프로그래밍 언어를 사용한 개발자는 다른 숙어에 익숙할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-186">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="072dd-187">다음 목록에는 권장F# 연산자가 요약됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-187">The following list summarizes the recommended F# operators.</span></span>

```fsharp
x |> f // Forward pipeline
f >> g // Forward composition
x |> ignore // Discard away a value
x + y // Overloaded addition (including string concatenation)
x - y // Overloaded subtraction
x * y // Overloaded multiplication
x / y // Overloaded division
x % y // Overloaded modulus
x && y // Lazy/short-cut "and"
x || y // Lazy/short-cut "or"
x <<< y // Bitwise left shift
x >>> y // Bitwise right shift
x ||| y // Bitwise or, also for working with “flags” enumeration
x &&& y // Bitwise and, also for working with “flags” enumeration
x ^^^ y // Bitwise xor, also for working with “flags” enumeration
```

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="072dd-188">제네릭 ()`Foo<T>`접두사 구문 ()`T Foo`</span><span class="sxs-lookup"><span data-stu-id="072dd-188">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="072dd-189">F#은 제네릭 형식(예: `int list`)의 이름 지정후부 ML 스타일과 접두사 .NET `list<int>`스타일(예: )을 모두 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-189">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="072dd-190">다음 다섯 가지 특정 유형을 제외하고 .NET 스타일을 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-190">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="072dd-191">F# 목록의 경우 접두사 `int list` 양식을 `list<int>`사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="072dd-191">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="072dd-192">F# 옵션의 경우 다음 값 `int option` 서식 양식을 사용하십시오. `option<int>`</span><span class="sxs-lookup"><span data-stu-id="072dd-192">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="072dd-193">F# 값 옵션의 경우 다음 `int voption` 값 `voption<int>`양식을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="072dd-193">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="072dd-194">F# 배열의 경우 또는 `int[]` `int array` `array<int>`또는 구문 이름을 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="072dd-194">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="072dd-195">참조 셀의 `int ref` 경우 `ref<int>` 또는 `Ref<int>`을 대신 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="072dd-195">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="072dd-196">다른 모든 형식의 경우 접두사 양식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-196">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="072dd-197">tuples 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-197">Formatting tuples</span></span>

<span data-ttu-id="072dd-198">튜플 인스턴스화는 괄호로 만들어야 하며 그 안에 있는 구분 쉼표 뒤에는 단일 공간(예: `(1, 2)`. `(x, y, z)`</span><span class="sxs-lookup"><span data-stu-id="072dd-198">A tuple instantiation should be parenthesized, and the delimiting commas within it should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="072dd-199">일반적으로 tuples의 패턴 일치에서 괄호를 생략하는 것이 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-199">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="072dd-200">또한 튜플이 함수의 반환 값인 경우 괄호를 생략하는 것이 일반적으로 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-200">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="072dd-201">요약하면 괄호 모양의 튜플 인스턴스화를 선호하지만 패턴 일치 또는 반환 값에 튜플을 사용하는 경우 괄호를 피하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-201">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="072dd-202">구별된 공용 구조체 선언 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-202">Formatting discriminated union declarations</span></span>

<span data-ttu-id="072dd-203">네 `|` 개의 공백에 의한 형식 정의의 들여쓰기:</span><span class="sxs-lookup"><span data-stu-id="072dd-203">Indent `|` in type definition by four spaces:</span></span>

```fsharp
// OK
type Volume =
    | Liter of float
    | FluidOunce of float
    | ImperialPint of float

// Not OK
type Volume =
| Liter of float
| USPint of float
| ImperialPint of float
```

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="072dd-204">구별된 공용 구조체 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-204">Formatting discriminated unions</span></span>

<span data-ttu-id="072dd-205">여러 줄로 분할되는 인스턴스화된 구별된 공용 구조체는 포함된 데이터를 들여쓰기와 함께 새 범위를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-205">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="072dd-206">닫는 괄호는 새 줄에 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-206">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="072dd-207">레코드 선언 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-207">Formatting record declarations</span></span>

<span data-ttu-id="072dd-208">형식 `{` 정의를 네 개의 공백으로 들여쓰기하고 동일한 줄에서 필드 목록을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-208">Indent `{` in type definition by four spaces and start the field list on the same line:</span></span>

```fsharp
// OK
type PostalAddress =
    { Address: string
      City: string
      Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Not OK
type PostalAddress =
  { Address: string
    City: string
    Zip: string }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

// Unusual in F#
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
```

<span data-ttu-id="072dd-209">레코드에서 인터페이스 구현 또는 멤버를 선언하는 경우 새 줄에 여는 토큰과 닫는 토큰을 새 줄에 배치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-209">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    }
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="072dd-210">레코드 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-210">Formatting records</span></span>

<span data-ttu-id="072dd-211">짧은 레코드는 한 줄로 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-211">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="072dd-212">더 긴 레코드는 레이블에 새 줄을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-212">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="072dd-213">다음 경우 열기 토큰을 새 줄에 배치하고 한 범위 위에 탭된 내용과 새 줄의 닫는 토큰을 배치하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-213">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="072dd-214">들여쓰기 범위가 다른 코드에서 레코드 이동</span><span class="sxs-lookup"><span data-stu-id="072dd-214">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="072dd-215">함수에 파이핑</span><span class="sxs-lookup"><span data-stu-id="072dd-215">Piping them into a function</span></span>

```fsharp
let rainbow =
    {
        Boss1 = "Jeffrey"
        Boss2 = "Jeffrey"
        Boss3 = "Jeffrey"
        Boss4 = "Jeffrey"
        Boss5 = "Jeffrey"
        Boss6 = "Jeffrey"
        Boss7 = "Jeffrey"
        Boss8 = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"]
    }

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface

let foo a =
    a
    |> Option.map (fun x ->
        {
            MyField = x
        })
```

<span data-ttu-id="072dd-216">목록 및 배열 요소에도 동일한 규칙이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-216">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="072dd-217">복사 및 업데이트 레코드 식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-217">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="072dd-218">복사 및 업데이트 레코드 표현식은 여전히 레코드이므로 유사한 지침이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-218">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="072dd-219">짧은 표현식은 한 줄에 맞을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-219">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="072dd-220">더 긴 표현식은 새 줄을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-220">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="072dd-221">또한 레코드 지침과 마찬가지로 중괄호에 대해 별도의 줄을 전용으로 지정하고 식을 사용하여 오른쪽에 하나의 범위를 들여쓰기할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-221">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="072dd-222">괄호 없이 선택적 값으로 값을 래핑하는 것과 같은 특수한 경우에는 한 줄에 중괄호를 유지해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-222">In some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

```fsharp
type S = { F1: int; F2: string }
type State = { F:  S option }

let state = { F = Some { F1 = 1; F2 = "Hello" } }
let newState =
    {
        state with
            F = Some {
                    F1 = 0
                    F2 = ""
                }
    }
```

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="072dd-223">목록 및 배열 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-223">Formatting lists and arrays</span></span>

<span data-ttu-id="072dd-224">연산자 주위에 `::` 공백을 쓰기`::` `x :: l` (infix 연산자이므로 공백으로 둘러싸여 있음).</span><span class="sxs-lookup"><span data-stu-id="072dd-224">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="072dd-225">단일 줄에 선언된 목록 및 배열은 오프닝 대괄호 뒤와 닫는 대괄호 앞에 공백이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-225">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="072dd-226">항상 두 개의 서로 다른 중괄호와 같은 연산자 사이에 적어도 하나의 공간을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-226">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="072dd-227">예를 들어 `[` a와 `{`a 사이에 공백을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-227">For example, leave a space between a `[` and a `{`.</span></span>

```fsharp
// OK
[ { IngredientName = "Green beans"; Quantity = 250 }
  { IngredientName = "Pine nuts"; Quantity = 250 }
  { IngredientName = "Feta cheese"; Quantity = 250 }
  { IngredientName = "Olive oil"; Quantity = 10 }
  { IngredientName = "Lemon"; Quantity = 1 } ]

// Not OK
[{ IngredientName = "Green beans"; Quantity = 250 }
 { IngredientName = "Pine nuts"; Quantity = 250 }
 { IngredientName = "Feta cheese"; Quantity = 250 }
 { IngredientName = "Olive oil"; Quantity = 10 }
 { IngredientName = "Lemon"; Quantity = 1 }]
```

<span data-ttu-id="072dd-228">튜플의 목록 또는 배열에 대해동일한 지침이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-228">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="072dd-229">여러 줄로 분할된 목록 및 배열은 레코드와 마찬가지로 다음과 같은 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-229">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

```fsharp
let pascalsTriangle =
    [|
        [| 1 |]
        [| 1; 1 |]
        [| 1; 2; 1 |]
        [| 1; 3; 3; 1 |]
        [| 1; 4; 6; 4; 1 |]
        [| 1; 5; 10; 10; 5; 1 |]
        [| 1; 6; 15; 20; 15; 6; 1 |]
        [| 1; 7; 21; 35; 35; 21; 7; 1 |]
        [| 1; 8; 28; 56; 70; 56; 28; 8; 1 |]
    |]
```

<span data-ttu-id="072dd-230">그리고 레코드와 마찬가지로 자체 줄에서 개폐 대괄호를 선언하면 코드를 이동하고 함수로 파이프를 쉽게 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-230">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="072dd-231">프로그래밍 방식으로 배열 및 목록을 생성할 `->` `do ... yield` 때 값이 항상 생성되는 경우보다 선호합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-231">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x*x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x*x ]
```

<span data-ttu-id="072dd-232">이전 버전의 F# 언어는 `yield` 데이터를 조건부로 생성할 수 있거나 평가할 연속식이 있을 수 있는 상황에서 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-232">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="072dd-233">이전 F# `yield` 언어 버전으로 컴파일해야 하지 않는 한 이러한 키워드를 생략하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-233">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

```fsharp
// Preferred
let daysOfWeek includeWeekend =
    [
        "Monday"
        "Tuesday"
        "Wednesday"
        "Thursday"
        "Friday"
        if includeWeekend then
            "Saturday"
            "Sunday"
    ]

// Not preferred
let daysOfWeek' includeWeekend =
    [
        yield "Monday"
        yield "Tuesday"
        yield "Wednesday"
        yield "Thursday"
        yield "Friday"
        if includeWeekend then
            yield "Saturday"
            yield "Sunday"
    ]
```

<span data-ttu-id="072dd-234">경우에 따라 `do...yield` 가독성에 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-234">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="072dd-235">이러한 경우는 주관적이지만 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-235">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="072dd-236">if 표현식서식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-236">Formatting if expressions</span></span>

<span data-ttu-id="072dd-237">조건부 들여쓰기는 이를 구성하는 식의 크기에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-237">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="072dd-238">과 `cond` `e1` `e2` 짧은 경우 한 줄에 쓰기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-238">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="072dd-239">의 `cond`경우 `e1` `e2` 중 하나이거나 더 길지만 다중 줄이 아닌 경우:</span><span class="sxs-lookup"><span data-stu-id="072dd-239">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="072dd-240">식 중 어느 것이 다중 줄인 경우:</span><span class="sxs-lookup"><span data-stu-id="072dd-240">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="072dd-241">다음과 같은 범위에서 `else` 들여쓰기되는 여러 조건부 `elif` `if`</span><span class="sxs-lookup"><span data-stu-id="072dd-241">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="072dd-242">패턴 일치 구문</span><span class="sxs-lookup"><span data-stu-id="072dd-242">Pattern matching constructs</span></span>

<span data-ttu-id="072dd-243">들여쓰기 `|` 없이 일치의 각 절에 대해 a를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-243">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="072dd-244">식이 짧은 경우 각 하위 표현식도 간단한 경우 한 줄을 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-244">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

```fsharp
// OK
match l with
| { him = x; her = "Posh" } :: tail -> x
| _ :: tail -> findDavid tail
| [] -> failwith "Couldn't find David"

// Not OK
match l with
    | { him = x; her = "Posh" } :: tail -> x
    | _ :: tail -> findDavid tail
    | [] -> failwith "Couldn't find David"
```

<span data-ttu-id="072dd-245">패턴 일치 화살표의 오른쪽에 있는 식이 너무 큰 경우 다음 줄로 이동하여 `match` / `|`에서 한 단계 들여쓰기합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-245">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="072dd-246">에서 시작하는 `function`익명 함수의 패턴 일치는 일반적으로 너무 멀리 들여쓰기해서는 안됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-246">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="072dd-247">예를 들어 다음과 같이 한 범위를 들여쓰기하는 것은 괜찮습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-247">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="072dd-248">`let` 키워드를 사용하더라도 `let rec` `let` `function` 을 시작한 후 4개의 공백을 들여쓰기하거나 정의한 함수에서 패턴 일치를 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-248">Pattern matching in functions defined by `let` or `let rec` should be indented four spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="072dd-249">화살표를 정렬하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-249">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="072dd-250">시도 서식 지정/식 사용</span><span class="sxs-lookup"><span data-stu-id="072dd-250">Formatting try/with expressions</span></span>

<span data-ttu-id="072dd-251">예외 형식의 패턴 일치는 `with`와 동일한 수준에서 들여쓰기되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-251">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

```fsharp
try
    if System.DateTime.Now.Second % 3 = 0 then
        raise (new System.Exception())
    else
        raise (new System.ApplicationException())
with
| :? System.ApplicationException ->
    printfn "A second that was not a multiple of 3"
| _ ->
    printfn "A second that was a multiple of 3"
```

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="072dd-252">함수 매개 변수 응용 프로그램 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-252">Formatting function parameter application</span></span>

<span data-ttu-id="072dd-253">일반적으로 대부분의 함수 매개 변수 응용 프로그램은 동일한 줄에서 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-253">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="072dd-254">새 줄의 함수에 매개 변수를 적용하려면 매개 변수를 하나의 범위로 들여쓰기합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-254">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

```fsharp
// OK
sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
sprintf
     "\t%s - %i\n\r"
     x.IngredientName x.Quantity

// OK
let printVolumes x =
    printf "Volume in liters = %f, in us pints = %f, in imperial = %f"
        (convertVolumeToLiter x)
        (convertVolumeUSPint x)
        (convertVolumeImperialPint x)
```

<span data-ttu-id="072dd-255">람다 식에 함수 인수와 동일한 지침이 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-255">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="072dd-256">람다 식의 본문에 한 범위에 의해 들여쓰기된 다른 줄을 가질 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="072dd-256">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

```fsharp
let printListWithOffset a list1 =
    List.iter
        (fun elem -> printfn "%d" (a + elem))
        list1

// OK if lambda body is long enough
let printListWithOffset a list1 =
    List.iter
        (fun elem ->
            printfn "%d" (a + elem))
        list1
```

<span data-ttu-id="072dd-257">그러나 lambda 식의 본문이 두 줄 이상인 경우 함수에 단일 인수로 적용된 다중 줄 구문이 아니라 별도의 함수로 팩터링하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-257">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="072dd-258">infix 연산자 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-258">Formatting infix operators</span></span>

<span data-ttu-id="072dd-259">연산자는 공백으로 구분합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-259">Separate operators by spaces.</span></span> <span data-ttu-id="072dd-260">이 규칙에 대한 명백한 `!` 예외는 연산자입니다. `.`</span><span class="sxs-lookup"><span data-stu-id="072dd-260">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="072dd-261">Infix 표현식은 동일한 열에서 라인업해도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-261">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="072dd-262">파이프라인 연산자 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-262">Formatting pipeline operators</span></span>

<span data-ttu-id="072dd-263">파이프라인 `|>` 연산자는 작동식 아래에 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-263">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

```fsharp
// Preferred approach
let methods2 =
    System.AppDomain.CurrentDomain.GetAssemblies()
    |> List.ofArray
    |> List.map (fun assm -> assm.GetTypes())
    |> Array.concat
    |> List.ofArray
    |> List.map (fun t -> t.GetMethods())
    |> Array.concat

// Not OK
let methods2 = System.AppDomain.CurrentDomain.GetAssemblies()
            |> List.ofArray
            |> List.map (fun assm -> assm.GetTypes())
            |> Array.concat
            |> List.ofArray
            |> List.map (fun t -> t.GetMethods())
            |> Array.concat
```

### <a name="formatting-modules"></a><span data-ttu-id="072dd-264">모듈 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-264">Formatting modules</span></span>

<span data-ttu-id="072dd-265">로컬 모듈의 코드는 모듈을 기준으로 들여쓰기되어야 하지만 최상위 모듈의 코드는 들여쓰기해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-265">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="072dd-266">네임스페이스 요소는 들여쓰기할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-266">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a*a + b*b

module A2 =
    let function2 a b = a*a - b*b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="072dd-267">개체 표현식 및 인터페이스 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-267">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="072dd-268">개체 표현식과 인터페이스는 네 개의 공백 `member` 후에 들여쓰기되는 것과 동일한 방식으로 정렬되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-268">Object expressions and interfaces should be aligned in the same way with `member` being indented after four spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="072dd-269">식의 공백 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-269">Formatting white space in expressions</span></span>

<span data-ttu-id="072dd-270">F# 식에서 불필요한 공백을 피하십시오.</span><span class="sxs-lookup"><span data-stu-id="072dd-270">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="072dd-271">명명된 인수에는 `=`다음을 둘러싼 공간도 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-271">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="072dd-272">특성 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-272">Formatting attributes</span></span>

<span data-ttu-id="072dd-273">[특성은](../language-reference/attributes.md) 구문 위에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-273">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

```fsharp
[<SomeAttribute>]
type MyClass() = ...

[<RequireQualifiedAccess>]
module M =
    let f x = x

[<Struct>]
type MyRecord =
    { Label1: int
      Label2: string }
```

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="072dd-274">매개 변수에 특성 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-274">Formatting attributes on parameters</span></span>

<span data-ttu-id="072dd-275">특성은 매개 변수에 배치될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-275">Attributes can also be places on parameters.</span></span> <span data-ttu-id="072dd-276">이 경우 매개 변수와 같은 줄에 이름을 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-276">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="072dd-277">여러 특성 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-277">Formatting multiple attributes</span></span>

<span data-ttu-id="072dd-278">매개 변수가 아닌 구문에 여러 특성이 적용되면 줄당 하나의 특성이 있도록 배치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-278">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="072dd-279">매개 변수에 적용할 때 동일한 줄에 있어야 하며 `;` 구분 기호로 구분되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-279">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="072dd-280">리터럴 서식 지정</span><span class="sxs-lookup"><span data-stu-id="072dd-280">Formatting literals</span></span>

<span data-ttu-id="072dd-281">특성을 `Literal` 사용하는 [F# 리터럴은](../language-reference/literals.md) 특성을 자체 줄에 배치하고 PascalCase 이름을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="072dd-281">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="072dd-282">값과 동일한 줄에 특성을 배치하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="072dd-282">Avoid placing the attribute on the same line as the value.</span></span>
