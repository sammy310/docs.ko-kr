---
title: F# 코드 서식 지정 지침
description: 'F # 코드의 서식을 지정 하기 위한 지침을 알아봅니다.'
ms.date: 11/04/2019
ms.openlocfilehash: a65600a6c685929aef8582e49caded6340fb09e2
ms.sourcegitcommit: 0fa2b7b658bf137e813a7f4d09589d64c148ebf5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/14/2020
ms.locfileid: "86309705"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="fd3e9-103">F# 코드 서식 지정 지침</span><span class="sxs-lookup"><span data-stu-id="fd3e9-103">F# code formatting guidelines</span></span>

<span data-ttu-id="fd3e9-104">이 문서에서는 F # 코드가 다음과 같이 되도록 코드의 형식을 지정 하는 방법에 대 한 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="fd3e9-105">보다 읽기 쉬운</span><span class="sxs-lookup"><span data-stu-id="fd3e9-105">More legible</span></span>
* <span data-ttu-id="fd3e9-106">Visual Studio 및 기타 편집기의 서식 도구에서 적용 하는 규칙에 따라</span><span class="sxs-lookup"><span data-stu-id="fd3e9-106">In accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="fd3e9-107">온라인에서 다른 코드와 유사</span><span class="sxs-lookup"><span data-stu-id="fd3e9-107">Similar to other code online</span></span>

<span data-ttu-id="fd3e9-108">이러한 지침은 [Anh-Ahn-dung Phan](https://github.com/dungpa)에서 [F # 형식 지정 규칙에 대 한 포괄적인 가이드](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) 를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="fd3e9-109">들여쓰기에 대 한 일반 규칙</span><span class="sxs-lookup"><span data-stu-id="fd3e9-109">General rules for indentation</span></span>

<span data-ttu-id="fd3e9-110">F #은 기본적으로 유효 공백을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-110">F# uses significant white space by default.</span></span> <span data-ttu-id="fd3e9-111">다음 지침은이에서 적용할 수 있는 몇 가지 문제를 따를 하는 방법에 대 한 지침을 제공 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="fd3e9-112">공백 사용</span><span class="sxs-lookup"><span data-stu-id="fd3e9-112">Using spaces</span></span>

<span data-ttu-id="fd3e9-113">들여쓰기가 필요한 경우 탭이 아닌 공백을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="fd3e9-114">공간이 하나 이상 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-114">At least one space is required.</span></span> <span data-ttu-id="fd3e9-115">조직에서 들여쓰기에 사용할 공백 수를 지정 하는 코딩 표준을 만들 수 있습니다. 들여쓰기가 발생 하는 각 수준에서 두 개, 세 개 또는 네 개의 들여쓰기 공간이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three, or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="fd3e9-116">**들여쓰기 당 4 개의 공백을 권장 합니다.**</span><span class="sxs-lookup"><span data-stu-id="fd3e9-116">**We recommend four spaces per indentation.**</span></span>

<span data-ttu-id="fd3e9-117">즉, 프로그램의 들여쓰기는 주관적인 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="fd3e9-118">변형이 양호 하지만 따라야 하는 첫 번째 규칙은 *들여쓰기의 일관성*입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="fd3e9-119">일반적으로 허용 되는 들여쓰기 스타일을 선택 하 고 코드 베이스 전체에서 체계적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="fd3e9-120">공백 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-120">Formatting white space</span></span>

<span data-ttu-id="fd3e9-121">F #은 공백으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-121">F# is white space sensitive.</span></span> <span data-ttu-id="fd3e9-122">공백에서 대부분의 의미 체계는 적절 한 들여쓰기가 적용 되지만 몇 가지 사항을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="fd3e9-123">산술 식의 형식 지정 연산자</span><span class="sxs-lookup"><span data-stu-id="fd3e9-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="fd3e9-124">항상 이진 산술 식 주위의 공백을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="fd3e9-125">단항 `-` 연산자는 부정 하는 값이 항상 뒤에와 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-125">Unary `-` operators should always be immediately followed by the value they are negating:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="fd3e9-126">연산자 뒤에 공백 문자를 추가 `-` 하면 다른 사람이 혼동을 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="fd3e9-127">요약 하자면, 항상 다음을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="fd3e9-128">공백을 사용 하 여 이항 연산자를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="fd3e9-129">단항 연산자 뒤에 후행 공백이 없어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="fd3e9-130">이항 산술 연산자 지침은 특히 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="fd3e9-131">`-`특정 형식 선택 항목과 함께 사용할 경우 이항 연산자를 감쌀 수 없으면 단항로 해석 될 수 있습니다 `-` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="fd3e9-132">공백을 사용 하 여 사용자 지정 연산자 정의 감싸기</span><span class="sxs-lookup"><span data-stu-id="fd3e9-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="fd3e9-133">항상 공백을 사용 하 여 연산자 정의를 둘러쌉니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="fd3e9-134">로 시작 하 고 둘 이상의 문자를 포함 하는 사용자 지정 연산자의 경우 `*` 컴파일러 모호성을 방지 하기 위해 정의의 시작 부분에 공백을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="fd3e9-135">따라서 모든 연산자의 정의를 단일 공백 문자로 묶는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="fd3e9-136">공백을 사용 하 여 함수 매개 변수 화살표 감싸기</span><span class="sxs-lookup"><span data-stu-id="fd3e9-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="fd3e9-137">함수의 시그니처를 정의 하는 경우 기호 주위의 공백을 사용 합니다 `->` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

### <a name="surround-function-arguments-with-white-space"></a><span data-ttu-id="fd3e9-138">공백을 사용 하 여 함수 인수를 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-138">Surround function arguments with white space</span></span>

<span data-ttu-id="fd3e9-139">함수를 정의 하는 경우 각 인수 주위에 공백을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-139">When defining a function, use white space around each argument.</span></span>

```fsharp
// OK
let myFun (a: decimal) b c = a + b + c

// Bad
let myFunBad (a:decimal)(b)c = a + b + c
```

### <a name="place-parameters-on-a-new-line-for-long-member-definitions"></a><span data-ttu-id="fd3e9-140">Long 멤버 정의에 대해 새 줄에 매개 변수를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-140">Place parameters on a new line for long member definitions</span></span>

<span data-ttu-id="fd3e9-141">멤버 정의가 매우 긴 경우 새 줄에 매개 변수를 추가 하 고 다음 매개 변수의 들여쓰기 수준에 맞게 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-141">If you have a very long member definition, place the parameters on new lines and indent them to match the indentation level of the subsequent parameter.</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
        // ... the body of the method follows
```

<span data-ttu-id="fd3e9-142">이는 생성자에도 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-142">This also applies to constructors:</span></span>

```fsharp
type C(aVeryLongType: AVeryLongTypeThatYouNeedToUse,
       aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse,
       aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse) =
    // ... the body of the class follows
```

<span data-ttu-id="fd3e9-143">명시적 반환 형식 주석이 있는 경우 또는의 끝 `)` `=` 또는 새 줄에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-143">If there is an explicit return type annotation, it can either be at the end of the `)` and before the `=`, or on a new line.</span></span> <span data-ttu-id="fd3e9-144">반환 형식에 긴 이름이 있는 경우 후자의 경우에는 다음을 수행 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-144">If the return type also has a long name, the latter might be preferable:</span></span>

```fsharp
type C() =
    member _.LongMethodWithLotsOfParameters(aVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aSecondVeryLongType: AVeryLongTypeThatYouNeedToUse,
                                            aThirdVeryLongType: AVeryLongTypeThatYouNeedToUse)
                                            : AVeryLongReturnType =
        // ... the body of the method follows
```

### <a name="type-annotations"></a><span data-ttu-id="fd3e9-145">형식 주석</span><span class="sxs-lookup"><span data-stu-id="fd3e9-145">Type annotations</span></span>

#### <a name="right-pad-function-argument-type-annotations"></a><span data-ttu-id="fd3e9-146">오른쪽 패드 함수 인수 형식 주석</span><span class="sxs-lookup"><span data-stu-id="fd3e9-146">Right-pad function argument type annotations</span></span>

<span data-ttu-id="fd3e9-147">형식 주석을 사용 하 여 인수를 정의 하는 경우 기호 뒤에 공백을 사용 합니다 `:` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-147">When defining arguments with type annotations, use white space after the `:` symbol:</span></span>

```fsharp
// OK
let complexFunction (a: int) (b: int) c = a + b + c

// Bad
let complexFunctionBad (a :int) (b :int) (c:int) = a + b + c
```

#### <a name="surround-return-type-annotations-with-white-space"></a><span data-ttu-id="fd3e9-148">공백을 사용 하 여 반환 형식 주석 감싸기</span><span class="sxs-lookup"><span data-stu-id="fd3e9-148">Surround return type annotations with white space</span></span>

<span data-ttu-id="fd3e9-149">Let 바인딩 함수 또는 값 형식 주석 (함수의 경우 반환 형식)에서 기호 앞뒤에 공백을 사용 합니다 `:` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-149">In a let-bound function or value type annotation (return type in the case of a function), use white space before and after the `:` symbol:</span></span>

```fsharp
// OK
let expensiveToCompute : int = 0 // Type annotation for let-bound value
let myFun (a: decimal) b c : decimal = a + b + c // Type annotation for the return type of a function
// Bad
let expensiveToComputeBad1:int = 1
let expensiveToComputeBad2 :int = 2
let myFunBad (a: decimal) b c:decimal = a + b + c
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="fd3e9-150">빈 줄 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-150">Formatting blank lines</span></span>

* <span data-ttu-id="fd3e9-151">두 개의 빈 줄로 최상위 함수와 클래스 정의를 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-151">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="fd3e9-152">클래스 내의 메서드 정의는 한 개의 빈 줄로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-152">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="fd3e9-153">별도의 빈 줄을 사용 하 여 관련 함수 그룹을 구분할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-153">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="fd3e9-154">관련 된 한 줄 (예: 더미 구현 집합) 간에 빈 줄이 생략 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-154">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="fd3e9-155">함수에서 빈 줄을 사용 하 여 논리적 섹션을 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-155">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="fd3e9-156">주석 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-156">Formatting comments</span></span>

<span data-ttu-id="fd3e9-157">일반적으로 ML 스타일 블록 주석에 대해 여러 개의 이중 슬래시 주석을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-157">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="fd3e9-158">인라인 주석은 첫 문자를 대문자로 표기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-158">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="fd3e9-159">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="fd3e9-159">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="fd3e9-160">클래스 바인딩, 식 바인딩 및 패턴 바인딩된 값과 함수에 camelCase 사용</span><span class="sxs-lookup"><span data-stu-id="fd3e9-160">Use camelCase for class-bound, expression-bound, and pattern-bound values and functions</span></span>

<span data-ttu-id="fd3e9-161">지역 변수 또는 패턴 일치 및 함수 정의로 바인딩된 모든 이름에 camelCase를 사용 하는 것은 일반적이 고 허용 되는 F # 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-161">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="fd3e9-162">클래스의 로컬 바인딩 함수는 camelCase도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-162">Locally bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="fd3e9-163">모듈 바인딩 public 함수에 camelCase 사용</span><span class="sxs-lookup"><span data-stu-id="fd3e9-163">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="fd3e9-164">모듈 바인딩 함수는 공용 API의 일부인 경우 camelCase를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-164">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="fd3e9-165">내부 및 전용 모듈 바인딩된 값 및 함수에 대해 camelCase 사용</span><span class="sxs-lookup"><span data-stu-id="fd3e9-165">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="fd3e9-166">다음을 포함 하 여 전용 모듈 바인딩 값에 camelCase를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-166">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="fd3e9-167">스크립트의 임시 함수</span><span class="sxs-lookup"><span data-stu-id="fd3e9-167">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="fd3e9-168">모듈 또는 형식의 내부 구현을 구성 하는 값</span><span class="sxs-lookup"><span data-stu-id="fd3e9-168">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="fd3e9-169">매개 변수에 camelCase 사용</span><span class="sxs-lookup"><span data-stu-id="fd3e9-169">Use camelCase for parameters</span></span>

<span data-ttu-id="fd3e9-170">모든 매개 변수는 .NET 명명 규칙에 따라 camelCase을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-170">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="fd3e9-171">모듈에 대 한 고 Calcase 사용</span><span class="sxs-lookup"><span data-stu-id="fd3e9-171">Use PascalCase for modules</span></span>

<span data-ttu-id="fd3e9-172">모든 모듈 (최상위, 내부, 전용, 중첩)은가는 대/소문자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-172">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="fd3e9-173">형식 선언, 멤버 및 레이블에 대 한 대/소문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-173">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="fd3e9-174">클래스, 인터페이스, 구조체, 열거형, 대리자, 레코드 및 구분 된 공용 구조체는 모두 라는 이름으로 지정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-174">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="fd3e9-175">레코드 및 구분 된 공용 구조체에 대 한 형식 및 레이블 내의 멤버는 같은 경우에도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-175">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="fd3e9-176">.NET에 내장 되어 있는 구문에 대 한 대/소문자를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-176">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="fd3e9-177">네임 스페이스, 예외, 이벤트 및 프로젝트/ `.dll` 이름에는 대/소문자를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-177">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="fd3e9-178">다른 .NET 언어를 사용 하 여 소비자에 게 더 자연스럽 게 사용할 수 있을 뿐만 아니라 발생할 수 있는 .NET 명명 규칙도 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-178">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="fd3e9-179">이름에 밑줄을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-179">Avoid underscores in names</span></span>

<span data-ttu-id="fd3e9-180">지금까지 일부 F # 라이브러리는 이름에 밑줄을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-180">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="fd3e9-181">그러나 .NET 명명 규칙과 충돌 하기 때문에이는 더 이상 광범위 하 게 허용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-181">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="fd3e9-182">즉, 일부 F # 프로그래머는 자주 사용 되는 밑줄을 사용 하 고, 일부는 기록 하기 위해 부분적으로 사용 되며, 허용 오차 및 존중은 중요 합니다</span><span class="sxs-lookup"><span data-stu-id="fd3e9-182">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="fd3e9-183">그러나 스타일을 사용할지 여부를 선택 하는 다른 사용자가 스타일을 선호 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-183">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="fd3e9-184">한 가지 예외는 기본 구성 요소와의 상호 운용을 포함 하며, 여기서 밑줄은 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-184">One exception includes interoperating with native components, where underscores are common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="fd3e9-185">표준 F # 연산자 사용</span><span class="sxs-lookup"><span data-stu-id="fd3e9-185">Use standard F# operators</span></span>

<span data-ttu-id="fd3e9-186">다음 연산자는 F # 표준 라이브러리에서 정의 되며, 해당 연산자를 정의 하는 대신 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-186">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="fd3e9-187">이러한 연산자를 사용 하는 것은 코드를 더 읽기 쉽고 자연 스러운 하는 경향이 있기 때문에 권장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-187">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="fd3e9-188">OCaml 또는 기타 함수형 프로그래밍 언어의 배경이 있는 개발자는 다른 관용구에 익숙할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-188">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="fd3e9-189">다음 목록에서는 권장 되는 F # 연산자를 요약 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-189">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="fd3e9-190">`Foo<T>`후 위 구문 ()에 대 한 기본 설정에서 제네릭 ()에 전위 구문을 사용 합니다. `T Foo`</span><span class="sxs-lookup"><span data-stu-id="fd3e9-190">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="fd3e9-191">F #은 이름 지정 제네릭 형식의 후 위 ML 스타일 (예: `int list` ) 및 접두사 .net 스타일 (예:)을 모두 상속 합니다 `list<int>` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-191">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="fd3e9-192">다음 5 가지 특정 형식을 제외 하 고 .NET 스타일을 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-192">Prefer the .NET style, except for five specific types:</span></span>

1. <span data-ttu-id="fd3e9-193">F # 목록의 경우 대신 후 위 형태를 사용 `int list` `list<int>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-193">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="fd3e9-194">F # 옵션의 경우 대신 후 위 형태를 사용 `int option` `option<int>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-194">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="fd3e9-195">F # 값 옵션의 경우 대신 후 위 형태를 사용 `int voption` `voption<int>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-195">For F# Value Options, use the postfix form: `int voption` rather than `voption<int>`.</span></span>
4. <span data-ttu-id="fd3e9-196">F # 배열의 경우 또는 대신 구문 이름을 사용 합니다 `int[]` `int array` `array<int>` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-196">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
5. <span data-ttu-id="fd3e9-197">참조 셀의 경우 또는 대신을 사용 `int ref` `ref<int>` `Ref<int>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-197">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="fd3e9-198">다른 모든 형식의 경우 접두사 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-198">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="fd3e9-199">튜플 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-199">Formatting tuples</span></span>

<span data-ttu-id="fd3e9-200">튜플 인스턴스화는 괄호로 묶어야 하며 그 안에 있는 구분 쉼표 뒤에는 단일 공백이와 야 합니다 (예:) `(1, 2)` `(x, y, z)` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-200">A tuple instantiation should be parenthesized, and the delimiting commas within it should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="fd3e9-201">일반적으로 튜플의 패턴 일치에서 괄호를 생략 하는 것이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-201">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="fd3e9-202">튜플이 함수의 반환 값인 경우에도 일반적으로 괄호를 생략 하는 것이 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-202">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="fd3e9-203">요약 하자면 괄호로 묶은 튜플 인스턴스화를 선호 하지만 패턴 일치 또는 반환 값에 튜플을 사용 하는 경우 괄호를 사용 하지 않는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-203">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="fd3e9-204">구별 된 공용 구조체 선언 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-204">Formatting discriminated union declarations</span></span>

<span data-ttu-id="fd3e9-205">`|`형식 정의에서 네 개의 공백으로 들여쓰기:</span><span class="sxs-lookup"><span data-stu-id="fd3e9-205">Indent `|` in type definition by four spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="fd3e9-206">구별 된 공용 구조체 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-206">Formatting discriminated unions</span></span>

<span data-ttu-id="fd3e9-207">여러 줄로 분할 된, 인스턴스화된 구별 된 공용 구조체는 포함 된 데이터에 들여쓰기를 사용 하 여 새 범위를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-207">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="fd3e9-208">또한 닫는 괄호는 새 줄에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-208">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="fd3e9-209">레코드 선언 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-209">Formatting record declarations</span></span>

<span data-ttu-id="fd3e9-210">`{`형식 정의에서 네 개의 공백으로 들여쓰기 하 고 같은 줄에서 필드 목록을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-210">Indent `{` in type definition by four spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="fd3e9-211">레코드에서 인터페이스 구현이 나 멤버를 선언 하는 경우에는 여는 토큰을 새 줄에 배치 하 고 닫는 토큰을 새 줄에 배치 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-211">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

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

## <a name="formatting-records"></a><span data-ttu-id="fd3e9-212">레코드 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-212">Formatting records</span></span>

<span data-ttu-id="fd3e9-213">짧은 레코드는 한 줄로 작성 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-213">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="fd3e9-214">더 긴 레코드는 레이블에 새 줄을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-214">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="fd3e9-215">여는 토큰을 새 줄에 배치 하 고, 콘텐츠를 한 범위 위로 탭 하 고, 다음을 수행 하는 경우 새 줄에 닫는 토큰을 추가 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-215">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="fd3e9-216">다른 들여쓰기 범위를 사용 하 여 코드에서 레코드 이동</span><span class="sxs-lookup"><span data-stu-id="fd3e9-216">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="fd3e9-217">함수에 파이핑</span><span class="sxs-lookup"><span data-stu-id="fd3e9-217">Piping them into a function</span></span>

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

<span data-ttu-id="fd3e9-218">목록 및 배열 요소에도 동일한 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-218">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="fd3e9-219">복사 및 업데이트 레코드 식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-219">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="fd3e9-220">복사 및 업데이트 레코드 식은 여전히 레코드 이므로 비슷한 지침이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-220">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="fd3e9-221">짧은 식은 한 줄에 맞출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-221">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="fd3e9-222">더 긴 식은 새 줄을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-222">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = [ "Zippy"; "George"; "Bungle" ] }
```

<span data-ttu-id="fd3e9-223">레코드 지침과 마찬가지로 중괄호에 대 한 별도의 줄을 사용 하 고 식을 사용 하 여 하나의 범위를 오른쪽으로 들여쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-223">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="fd3e9-224">괄호 없이 선택적으로 값을 래핑하는 것과 같은 일부 특수 한 경우에는 중괄호를 한 줄에 유지 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-224">In some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

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

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="fd3e9-225">목록 및 배열 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-225">Formatting lists and arrays</span></span>

<span data-ttu-id="fd3e9-226">`x :: l`연산자 주위에 공백을 사용 하 여 씁니다 `::` `::` .는 중 위 연산자 이므로 공백으로 둘러싸여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-226">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="fd3e9-227">한 줄에 선언 된 목록 및 배열에는 여는 대괄호 뒤와 닫는 대괄호 앞에 공백을 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-227">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="fd3e9-228">두 개의 서로 다른 중괄호와 비슷한 연산자 사이에는 항상 하나 이상의 공백을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-228">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="fd3e9-229">예를 들어와 사이에 공백을 둡니다 `[` `{` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-229">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="fd3e9-230">튜플 목록 또는 배열에도 동일한 지침이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-230">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="fd3e9-231">여러 줄에 걸쳐 분할 된 목록 및 배열은 레코드와 비슷한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-231">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="fd3e9-232">레코드와 마찬가지로, 여는 대괄호와 닫는 대괄호를 자체 줄에 선언 하면 코드를 더 쉽게 이동 하 고 파이프로 파이프 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-232">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

<span data-ttu-id="fd3e9-233">프로그래밍 방식으로 배열과 목록을 생성 하는 `->` 경우 `do ... yield` 값이 항상 생성 되는 경우를 대신 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-233">When generating arrays and lists programmatically, prefer `->` over `do ... yield` when a value is always generated:</span></span>

```fsharp
// Preferred
let squares = [ for x in 1..10 -> x * x ]

// Not preferred
let squares' = [ for x in 1..10 do yield x * x ]
```

<span data-ttu-id="fd3e9-234">이전 버전의 F # 언어는 `yield` 데이터가 조건부로 생성 될 수 있는 경우를 지정 해야 하며, 그렇지 않은 경우에는 계산 될 연속 식이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-234">Older versions of the F# language required specifying `yield` in situations where data may be generated conditionally, or there may be consecutive expressions to be evaluated.</span></span> <span data-ttu-id="fd3e9-235">`yield`이전 F # 언어 버전으로 컴파일하지 않아야 하는 경우를 제외 하 고 이러한 키워드를 생략 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-235">Prefer omitting these `yield` keywords unless you must compile with an older F# language version:</span></span>

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

<span data-ttu-id="fd3e9-236">경우에 따라에서 `do...yield` 가독성을 향상 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-236">In some cases, `do...yield` may aid in readability.</span></span> <span data-ttu-id="fd3e9-237">이러한 경우에는 주관적인을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-237">These cases, though subjective, should be taken into consideration.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="fd3e9-238">If 식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-238">Formatting if expressions</span></span>

<span data-ttu-id="fd3e9-239">조건 들여쓰기는 구성 하는 식의 크기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-239">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="fd3e9-240">`cond` `e1` 및 `e2` 가 짧으면 한 줄에 작성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-240">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="fd3e9-241">또는 중 `cond` 하나 `e1` 이상이 `e2` 긴 하지만 여러 줄이 아닌 경우:</span><span class="sxs-lookup"><span data-stu-id="fd3e9-241">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="fd3e9-242">식이 여러 줄 인 경우:</span><span class="sxs-lookup"><span data-stu-id="fd3e9-242">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="fd3e9-243">및를 사용 하는 여러 `elif` `else` 조건이와 동일한 범위에서 들여쓰기 됩니다 `if` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-243">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="fd3e9-244">패턴 일치 구문</span><span class="sxs-lookup"><span data-stu-id="fd3e9-244">Pattern matching constructs</span></span>

<span data-ttu-id="fd3e9-245">`|`들여쓰기가 없는 일치 항목의 for each 절을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-245">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="fd3e9-246">식이 짧으면 각 하위 식이 simple 인 경우 한 줄을 사용 하는 것을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-246">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="fd3e9-247">패턴 일치 화살표 오른쪽의 식이 너무 크면 다음 줄로 이동 하 여에서 한 단계를 들여씁니다 `match` / `|` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-247">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="fd3e9-248">에서 시작 하는 익명 함수의 패턴 일치는 `function` 일반적으로 너무 멀리 들여쓰기 되지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-248">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="fd3e9-249">예를 들어 다음과 같이 한 범위를 들여쓰는 것은 괜찮습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-249">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="fd3e9-250">키워드를 사용 하는 경우에도 또는에서 정의한 함수의 패턴 일치는 `let` `let rec` 를 시작한 후 4 개의 공백으로 들여쓰기 되어야 합니다 `let` `function` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-250">Pattern matching in functions defined by `let` or `let rec` should be indented four spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="fd3e9-251">화살표를 정렬 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-251">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="fd3e9-252">Try/with 식 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-252">Formatting try/with expressions</span></span>

<span data-ttu-id="fd3e9-253">예외 형식에 대 한 패턴 일치는와 동일한 수준으로 들여쓰기 되어야 합니다 `with` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-253">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="fd3e9-254">형식 지정 함수 매개 변수 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="fd3e9-254">Formatting function parameter application</span></span>

<span data-ttu-id="fd3e9-255">일반적으로 대부분의 함수 매개 변수 응용 프로그램은 같은 줄에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-255">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="fd3e9-256">새 줄에 함수에 대 한 매개 변수를 적용 하려는 경우 한 범위 만큼 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-256">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="fd3e9-257">람다 식에 대 한 동일한 지침이 함수 인수로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-257">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="fd3e9-258">람다 식의 본문 인 경우 본문은 한 범위로 들여쓰기 된 다른 줄을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-258">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="fd3e9-259">그러나 람다 식의 본문이 두 줄 이상인 경우에는 함수에 단일 인수로 적용 되는 여러 줄 구문을 포함 하지 않고 별도의 함수로 팩터링 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-259">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="fd3e9-260">중 위 연산자 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-260">Formatting infix operators</span></span>

<span data-ttu-id="fd3e9-261">연산자를 공백으로 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-261">Separate operators by spaces.</span></span> <span data-ttu-id="fd3e9-262">이 규칙에 대 한 명백한 예외는 `!` 및 `.` 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-262">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="fd3e9-263">중 위 식은 동일한 열의 목록에 대해 확인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-263">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="fd3e9-264">파이프라인 연산자 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-264">Formatting pipeline operators</span></span>

<span data-ttu-id="fd3e9-265">파이프라인 `|>` 연산자는 작동 하는 식 아래로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-265">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="fd3e9-266">서식 모듈</span><span class="sxs-lookup"><span data-stu-id="fd3e9-266">Formatting modules</span></span>

<span data-ttu-id="fd3e9-267">로컬 모듈의 코드는 모듈을 기준으로 들여쓰기 되어야 하지만 최상위 모듈의 코드는 들여쓰지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-267">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="fd3e9-268">네임 스페이스 요소를 들여쓸 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-268">Namespace elements do not have to be indented.</span></span>

```fsharp
// A is a top-level module.
module A

let function1 a b = a - b * b
```

```fsharp
// A1 and A2 are local modules.
module A1 =
    let function1 a b = a * a + b * b

module A2 =
    let function2 a b = a * a - b * b
```

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="fd3e9-269">개체 식 및 인터페이스 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-269">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="fd3e9-270">개체 식과 인터페이스는 `member` 네 개의 공간 이후에 들여쓰는 것과 같은 방식으로 정렬 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-270">Object expressions and interfaces should be aligned in the same way with `member` being indented after four spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="fd3e9-271">식의 공백 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-271">Formatting white space in expressions</span></span>

<span data-ttu-id="fd3e9-272">F # 식에 불필요 한 공백을 사용 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-272">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="fd3e9-273">명명 된 인수에는를 둘러싼 공간이 없어야 합니다 `=` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-273">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="fd3e9-274">서식 특성</span><span class="sxs-lookup"><span data-stu-id="fd3e9-274">Formatting attributes</span></span>

<span data-ttu-id="fd3e9-275">[특성](../language-reference/attributes.md) 은 구문 위에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-275">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="fd3e9-276">매개 변수의 특성 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-276">Formatting attributes on parameters</span></span>

<span data-ttu-id="fd3e9-277">특성은 매개 변수에도 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-277">Attributes can also be placed on parameters.</span></span> <span data-ttu-id="fd3e9-278">이 경우 매개 변수와 같은 줄에, 이름 앞에를 놓습니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-278">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member _.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="fd3e9-279">여러 특성 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-279">Formatting multiple attributes</span></span>

<span data-ttu-id="fd3e9-280">매개 변수가 아닌 구문에 여러 특성을 적용 하는 경우에는 줄 마다 하나의 특성이 있도록 배치 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-280">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="fd3e9-281">매개 변수에 적용 되는 경우 동일한 줄에 있고 구분 기호로 구분 되어야 합니다 `;` .</span><span class="sxs-lookup"><span data-stu-id="fd3e9-281">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="fd3e9-282">리터럴 서식 지정</span><span class="sxs-lookup"><span data-stu-id="fd3e9-282">Formatting literals</span></span>

<span data-ttu-id="fd3e9-283">특성을 사용 하는 [F # 리터럴은](../language-reference/literals.md) 해당 `Literal` 줄에 특성을 추가 하 고, 다음을 사용 하 여 대/소문자 이름을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-283">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use PascalCase naming:</span></span>

```fsharp
[<Literal>]
let Path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let MyUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="fd3e9-284">특성을 값과 같은 줄에 배치 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="fd3e9-284">Avoid placing the attribute on the same line as the value.</span></span>
