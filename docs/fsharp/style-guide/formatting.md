---
title: F#코드 서식 지정 지침
description: 서식 지정에 대 한 지침을 알아보려면 F# 코드입니다.
ms.date: 02/08/2019
ms.openlocfilehash: 259d4bb2147d1fc8bc5d35d7ff2e3c34ec2185d0
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61902592"
---
# <a name="f-code-formatting-guidelines"></a><span data-ttu-id="2f957-103">F#코드 서식 지정 지침</span><span class="sxs-lookup"><span data-stu-id="2f957-103">F# code formatting guidelines</span></span>

<span data-ttu-id="2f957-104">이 문서에서는 프로그램 코드의 서식을 지정 하는 방법에 대 한 지침을 제공 하 여 F# 코드는:</span><span class="sxs-lookup"><span data-stu-id="2f957-104">This article offers guidelines for how to format your code so that your F# code is:</span></span>

* <span data-ttu-id="2f957-105">일반적으로 보다 쉽게 읽을 것으로 간주</span><span class="sxs-lookup"><span data-stu-id="2f957-105">Generally viewed as more legible</span></span>
* <span data-ttu-id="2f957-106">Visual Studio의 도구 및 다른 편집기를 지정 하 여 적용 되는 규칙에 따라는</span><span class="sxs-lookup"><span data-stu-id="2f957-106">Is in accordance with conventions applied by formatting tools in Visual Studio and other editors</span></span>
* <span data-ttu-id="2f957-107">다른 온라인으로 코드와 유사</span><span class="sxs-lookup"><span data-stu-id="2f957-107">Similar to other code online</span></span>

<span data-ttu-id="2f957-108">다음이 지침에 기반한 [에 대 한 포괄적인 지침 F# 서식 지정 규칙](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) 하 여 [Anh 똥 Phan](https://github.com/dungpa)합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-108">These guidelines are based on [A comprehensive guide to F# Formatting Conventions](https://github.com/dungpa/fantomas/blob/master/docs/FormattingConventions.md) by [Anh-Dung Phan](https://github.com/dungpa).</span></span>

## <a name="general-rules-for-indentation"></a><span data-ttu-id="2f957-109">들여쓰기에 대 한 일반 규칙</span><span class="sxs-lookup"><span data-stu-id="2f957-109">General rules for indentation</span></span>

<span data-ttu-id="2f957-110">F#기본적으로 유효 공백 문자를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-110">F# uses significant white space by default.</span></span> <span data-ttu-id="2f957-111">다음 지침을 적용할 수이 하는 몇 가지 과제를 다루어야 하는 방법에 대 한 지침을 제공 하려는.</span><span class="sxs-lookup"><span data-stu-id="2f957-111">The following guidelines are intended to provide guidance as to how to juggle some challenges this can impose.</span></span>

### <a name="using-spaces"></a><span data-ttu-id="2f957-112">공간 사용</span><span class="sxs-lookup"><span data-stu-id="2f957-112">Using spaces</span></span>

<span data-ttu-id="2f957-113">들여쓰기가 필요한 경우 공백, 탭 하지 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-113">When indentation is required, you must use spaces, not tabs.</span></span> <span data-ttu-id="2f957-114">하나 이상의 공간이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-114">At least one space is required.</span></span> <span data-ttu-id="2f957-115">조직에 들여쓰기;에 사용할 공백 수를 지정 하는 코딩 표준을 만들 수 있습니다. 2, 3 또는 4 개의 공백 들여쓰기 발생 하는 각 수준에서 들여쓰기 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-115">Your organization can create coding standards to specify the number of spaces to use for indentation; two, three or four spaces of indentation at each level where indentation occurs is typical.</span></span>

<span data-ttu-id="2f957-116">**들여쓰기 당 4 개의 공백을 사용 하는 것이 좋습니다.**</span><span class="sxs-lookup"><span data-stu-id="2f957-116">**We recommend 4 spaces per indentation.**</span></span>

<span data-ttu-id="2f957-117">즉, 프로그램의 들여쓰기는 주관적입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-117">That said, indentation of programs is a subjective matter.</span></span> <span data-ttu-id="2f957-118">변형 좋은지 이지만 첫 번째 규칙을 따라야 *들여쓰기 일관성*합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-118">Variations are OK, but the first rule you should follow is *consistency of indentation*.</span></span> <span data-ttu-id="2f957-119">들여쓰기의 일반적으로 허용 되는 스타일을 선택 하 고 코드 베이스 전체에서 체계적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-119">Choose a generally accepted style of indentation and use it systematically throughout your codebase.</span></span>

## <a name="formatting-white-space"></a><span data-ttu-id="2f957-120">공백 문자 서식 지정</span><span class="sxs-lookup"><span data-stu-id="2f957-120">Formatting white space</span></span>

<span data-ttu-id="2f957-121">F#공백 문자는 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-121">F# is white space sensitive.</span></span> <span data-ttu-id="2f957-122">공백에서 대부분의 의미 체계를 적절 한 들여쓰기 하 여 처리 되지만 몇 가지 다른 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-122">Although most semantics from white space are covered by proper indentation, there are some other things to consider.</span></span>

### <a name="formatting-operators-in-arithmetic-expressions"></a><span data-ttu-id="2f957-123">산술 식의 연산자를 서식 지정</span><span class="sxs-lookup"><span data-stu-id="2f957-123">Formatting operators in arithmetic expressions</span></span>

<span data-ttu-id="2f957-124">항상 이진 산술 연산자 주위의 공백을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-124">Always use white space around binary arithmetic expressions:</span></span>

```fsharp
let subtractThenAdd x = x - 1 + 3
```

<span data-ttu-id="2f957-125">단항 `-` 연산자에는 부정 되는 값을 가져야 합니다. 다음에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-125">Unary `-` operators should always have the value they are negating immediately follow:</span></span>

```fsharp
// OK
let negate x = -x

// Bad
let negateBad x = - x
```

<span data-ttu-id="2f957-126">다음 공백 문자를 추가 합니다 `-` 연산자 다른 혼란이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-126">Adding a white-space character after the `-` operator can lead to confusion for others.</span></span>

<span data-ttu-id="2f957-127">이 요약 하자면, 항상 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-127">In summary, it's important to always:</span></span>

* <span data-ttu-id="2f957-128">공백 문자를 사용 하 여 서라운드 이항 연산자</span><span class="sxs-lookup"><span data-stu-id="2f957-128">Surround binary operators with white space</span></span>
* <span data-ttu-id="2f957-129">단항 연산자 뒤에 후행 공백이 절대로</span><span class="sxs-lookup"><span data-stu-id="2f957-129">Never have trailing white space after a unary operator</span></span>

<span data-ttu-id="2f957-130">이진 산술 연산자 지침 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-130">The binary arithmetic operator guideline is especially important.</span></span> <span data-ttu-id="2f957-131">이진 파일을 묶을 실패 `-` 연산자를 특정 형식 지정 옵션을 함께 사용 하면 단항으로 해석 될 수 있습니다 `-`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-131">Failing to surround a binary `-` operator, when combined with certain formatting choices, could lead to interpreting it as a unary `-`.</span></span>

### <a name="surround-a-custom-operator-definition-with-white-space"></a><span data-ttu-id="2f957-132">주위에 공백 문자를 사용 하 여 사용자 지정 연산자 정의</span><span class="sxs-lookup"><span data-stu-id="2f957-132">Surround a custom operator definition with white space</span></span>

<span data-ttu-id="2f957-133">항상 사용 하 여 공백 묶을 연산자 정의:</span><span class="sxs-lookup"><span data-stu-id="2f957-133">Always use white space to surround an operator definition:</span></span>

```fsharp
// OK
let ( !> ) x f = f x

// Bad
let (!>) x f = f x
```

<span data-ttu-id="2f957-134">로 시작 하는 모든 사용자 지정 연산자에 대 한 `*` 있는 둘 이상의 문자를 컴파일러 모호성을 피하기 위해 정의의 시작 부분에 공백을 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-134">For any custom operator that starts with `*` and that has more than one character, you need to add a white space to the beginning of the definition to avoid a compiler ambiguity.</span></span> <span data-ttu-id="2f957-135">이 인해 단일 공백 문자를 사용 하 여 모든 연산자의 정의 단순히 입력 해야 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-135">Because of this, we recommend that you simply surround the definitions of all operators with a single white-space character.</span></span>

### <a name="surround-function-parameter-arrows-with-white-space"></a><span data-ttu-id="2f957-136">주위에 공백 문자를 사용 하 여 함수 매개 변수 화살표</span><span class="sxs-lookup"><span data-stu-id="2f957-136">Surround function parameter arrows with white space</span></span>

<span data-ttu-id="2f957-137">함수의 시그니처를 정의할 때는 주위의 공백을 사용 하 여는 `->` 기호:</span><span class="sxs-lookup"><span data-stu-id="2f957-137">When defining the signature of a function, use white space around the `->` symbol:</span></span>

```fsharp
// OK
type MyFun = int -> int -> string

// Bad
type MyFunBad = int->int->string
```

## <a name="formatting-blank-lines"></a><span data-ttu-id="2f957-138">빈 줄을 서식 지정</span><span class="sxs-lookup"><span data-stu-id="2f957-138">Formatting blank lines</span></span>

* <span data-ttu-id="2f957-139">별도 최상위 함수 및 클래스 정의 두 개의 빈 줄을 사용 하 여 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-139">Separate top-level function and class definitions with two blank lines.</span></span>
* <span data-ttu-id="2f957-140">클래스 내의 메서드 정의 비어 있는 단일 선으로 구분 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-140">Method definitions inside a class are separated by a single blank line.</span></span>
* <span data-ttu-id="2f957-141">빈 줄을 별도의 관련 된 기능 그룹 (제한적) 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-141">Extra blank lines may be used (sparingly) to separate groups of related functions.</span></span> <span data-ttu-id="2f957-142">다양 한 관련된 one-liner (예를 들어, 구현 집합을 더미) 사이의 빈 줄을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-142">Blank lines may be omitted between a bunch of related one-liners (for example, a set of dummy implementations).</span></span>
* <span data-ttu-id="2f957-143">논리적 섹션을 나타내기 위해 함수에서 빈 줄을 제한적으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-143">Use blank lines in functions, sparingly, to indicate logical sections.</span></span>

## <a name="formatting-comments"></a><span data-ttu-id="2f957-144">주석 형식</span><span class="sxs-lookup"><span data-stu-id="2f957-144">Formatting comments</span></span>

<span data-ttu-id="2f957-145">일반적으로 기계 학습 스타일 블록 주석 통해 여러 이중 슬래시 주석을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-145">Generally prefer multiple double-slash comments over ML-style block comments.</span></span>

```fsharp
// Prefer this style of comments when you want
// to express written ideas on multiple lines.

(*
    ML-style comments are fine, but not a .NET-ism.
    They are useful when needing to modify multi-line comments, though.
*)
```

<span data-ttu-id="2f957-146">인라인 주석을 첫 번째 글자를 대문자로 표시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-146">Inline comments should capitalize the first letter.</span></span>

```fsharp
let f x = x + 1 // Increment by one.
```

## <a name="naming-conventions"></a><span data-ttu-id="2f957-147">명명 규칙</span><span class="sxs-lookup"><span data-stu-id="2f957-147">Naming conventions</span></span>

### <a name="use-camelcase-for-class-bound-expression-bound-and-pattern-bound-values-and-functions"></a><span data-ttu-id="2f957-148">CamelCase를 사용 하 여 클래스 바인딩, 바인딩 식 및 패턴 바인딩된 값 및 함수에 대 한</span><span class="sxs-lookup"><span data-stu-id="2f957-148">Use camelCase for class-bound, expression-bound and pattern-bound values and functions</span></span>

<span data-ttu-id="2f957-149">일반적이 고 허용 F# 모든 이름은 지역 변수 또는 패턴 일치에 바인딩되고 정의 함수에 대 한 camelCase를 사용 하는 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-149">It is common and accepted F# style to use camelCase for all names bound as local variables or in pattern matches and function definitions.</span></span>

```fsharp
// OK
let addIAndJ i j = i + j

// Bad
let addIAndJ I J = I+J

// Bad
let AddIAndJ i j = i + j
```

<span data-ttu-id="2f957-150">클래스에 바인딩된 로컬로 함수도 camelCase를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-150">Locally-bound functions in classes should also use camelCase.</span></span>

```fsharp
type MyClass() =

    let doSomething () =

    let firstResult = ...

    let secondResult = ...

    member x.Result = doSomething()
```

### <a name="use-camelcase-for-module-bound-public-functions"></a><span data-ttu-id="2f957-151">CamelCase를 사용 하 여 모듈 바인딩된 공용 함수에 대 한</span><span class="sxs-lookup"><span data-stu-id="2f957-151">Use camelCase for module-bound public functions</span></span>

<span data-ttu-id="2f957-152">모듈 바인딩된 함수는 공용 API의 일부 이면 camelCase 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-152">When a module-bound function is part of a public API, it should use camelCase:</span></span>

```fsharp
module MyAPI =
    let publicFunctionOne param1 param2 param2 = ...

    let publicFunctionTwo param1 param2 param3 = ...
```

### <a name="use-camelcase-for-internal-and-private-module-bound-values-and-functions"></a><span data-ttu-id="2f957-153">CamelCase를 사용 하 여 내부 및 개인 모듈 바인딩된 값 및 함수에 대 한</span><span class="sxs-lookup"><span data-stu-id="2f957-153">Use camelCase for internal and private module-bound values and functions</span></span>

<span data-ttu-id="2f957-154">다음을 포함 하 여 개인 모듈 바인딩된 값에 대 한 camelCase를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-154">Use camelCase for private module-bound values, including the following:</span></span>

* <span data-ttu-id="2f957-155">스크립트의 임시 함수</span><span class="sxs-lookup"><span data-stu-id="2f957-155">Ad hoc functions in scripts</span></span>

* <span data-ttu-id="2f957-156">값 형식 또는 모듈의 내부 구현을 구성</span><span class="sxs-lookup"><span data-stu-id="2f957-156">Values making up the internal implementation of a module or type</span></span>

```fsharp
let emailMyBossTheLatestResults =
    ...
```

### <a name="use-camelcase-for-parameters"></a><span data-ttu-id="2f957-157">CamelCase를 사용 하 여 매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f957-157">Use camelCase for parameters</span></span>

<span data-ttu-id="2f957-158">모든 매개 변수는.NET 명명 규칙에 따라 camelCase를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-158">All parameters should use camelCase in accordance with .NET naming conventions.</span></span>

```fsharp
module MyModule =
    let myFunction paramOne paramTwo = ...

type MyClass() =
    member this.MyMethod(paramOne, paramTwo) = ...
```

### <a name="use-pascalcase-for-modules"></a><span data-ttu-id="2f957-159">PascalCase를 사용 하 여 모듈에 대 한</span><span class="sxs-lookup"><span data-stu-id="2f957-159">Use PascalCase for modules</span></span>

<span data-ttu-id="2f957-160">모든 모듈 (예: 최상위, 내부, 개인, 중첩 된) PascalCase를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-160">All modules (top-level, internal, private, nested) should use PascalCase.</span></span>

```fsharp
module MyTopLevelModule

module Helpers =
    module private SuperHelpers =
        ...

    ...
```

### <a name="use-pascalcase-for-type-declarations-members-and-labels"></a><span data-ttu-id="2f957-161">형식 선언, 멤버 및 레이블을 사용 하 여 PascalCase</span><span class="sxs-lookup"><span data-stu-id="2f957-161">Use PascalCase for type declarations, members, and labels</span></span>

<span data-ttu-id="2f957-162">클래스, 인터페이스, 구조체, 열거형, 대리자, 레코드 및 구분 된 공용 구조체 모든 PascalCase로 명명 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-162">Classes, interfaces, structs, enumerations, delegates, records, and discriminated unions should all be named with PascalCase.</span></span> <span data-ttu-id="2f957-163">형식 및 레코드 및 구분 된 공용 구조체에 대 한 레이블 내에서 멤버 PascalCase 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-163">Members within types and labels for records and discriminated unions should also use PascalCase.</span></span>

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

### <a name="use-pascalcase-for-constructs-intrinsic-to-net"></a><span data-ttu-id="2f957-164">PascalCase를 사용 하 여.NET으로 내장 되는 구문에 대 한</span><span class="sxs-lookup"><span data-stu-id="2f957-164">Use PascalCase for constructs intrinsic to .NET</span></span>

<span data-ttu-id="2f957-165">네임 스페이스, 예외, 이벤트 및 프로젝트 /`.dll` 이름을 PascalCase에도 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-165">Namespaces, exceptions, events, and project/`.dll` names should also use PascalCase.</span></span> <span data-ttu-id="2f957-166">뿐만 아니라 소비자에 게 자연스럽 게 느낄 다른.NET 언어에서 소비 되셨나요, 그리고 발생할 가능성이 있는.NET 명명 규칙에 부합 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-166">Not only does this make consumption from other .NET languages feel more natural to consumers, it's also consistent with .NET naming conventions that you are likely to encounter.</span></span>

### <a name="avoid-underscores-in-names"></a><span data-ttu-id="2f957-167">이름에 밑줄을 방지 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-167">Avoid underscores in names</span></span>

<span data-ttu-id="2f957-168">지금까지 일부 F# 라이브러리 이름에 밑줄을 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-168">Historically, some F# libraries have used underscores in names.</span></span> <span data-ttu-id="2f957-169">그러나이 더 이상 광범위 하 게 수락 되 면.NET 명명 규칙을 사용 하 여 충돌 하기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-169">However, this is no longer widely accepted, partly because it clashes with .NET naming conventions.</span></span> <span data-ttu-id="2f957-170">즉, 일부 F# 프로그래머 밑줄 많이, 부분적으로 기록 상의 용도로 및 사용 허용 오차 존경 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-170">That said, some F# programmers use underscores heavily, partly for historical reasons, and tolerance and respect is important.</span></span> <span data-ttu-id="2f957-171">그러나 사용할 것인지 선택할 수 있는 다른 사용자가 스타일은 종종 싫는 주의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-171">However, be aware that the style is often disliked by others who have a choice about whether to use it.</span></span>

<span data-ttu-id="2f957-172">밑줄을 매우 자주 네이티브 구성 요소와의 상호 운용 하는 몇 가지 예외 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-172">Some exceptions includes interoperating with native components, where underscores are very common.</span></span>

### <a name="use-standard-f-operators"></a><span data-ttu-id="2f957-173">사용 하 여 표준 F# 연산자</span><span class="sxs-lookup"><span data-stu-id="2f957-173">Use standard F# operators</span></span>

<span data-ttu-id="2f957-174">에 정의 된 다음 연산자는 F# 표준 라이브러리 항목을 정의 하는 대신 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-174">The following operators are defined in the F# standard library and should be used instead of defining equivalents.</span></span> <span data-ttu-id="2f957-175">더 읽기 쉽고 자연 스러운 코드를 확인 하는 경향이 있습니다 이러한 연산자를 사용 하 여 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-175">Using these operators is recommended as it tends to make code more readable and idiomatic.</span></span> <span data-ttu-id="2f957-176">OCaml 또는 다른 함수형 프로그래밍 언어에서 배경의 개발자가 익숙한 다른 관용구를 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-176">Developers with a background in OCaml or other functional programming language may be accustomed to different idioms.</span></span> <span data-ttu-id="2f957-177">다음 목록은 요약 권장 되는 F# 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-177">The following list summarizes the recommended F# operators.</span></span>

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

### <a name="use-prefix-syntax-for-generics-foot-in-preference-to-postfix-syntax-t-foo"></a><span data-ttu-id="2f957-178">제네릭에 대 한 접두사 구문을 사용 하 여 (`Foo<T>`) 후 위 구문 보다 우선적으로 (`T Foo`)</span><span class="sxs-lookup"><span data-stu-id="2f957-178">Use prefix syntax for generics (`Foo<T>`) in preference to postfix syntax (`T Foo`)</span></span>

<span data-ttu-id="2f957-179">F#제네릭 형식 명명 모두는 후 위 ML 스타일 상속 (예를 들어 `int list`) 접두사.NET 스타일 뿐만 아니라 (예를 들어 `list<int>`).</span><span class="sxs-lookup"><span data-stu-id="2f957-179">F# inherits both the postfix ML style of naming generic types (for example, `int list`) as well as the prefix .NET style (for example, `list<int>`).</span></span> <span data-ttu-id="2f957-180">네 개의 특정 형식 제외 하 고.NET 스타일을 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-180">Prefer the .NET style, except for four specific types:</span></span>

1. <span data-ttu-id="2f957-181">에 대 한 F# 목록, 후 위 형식 사용: `int list` 대신 `list<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-181">For F# Lists, use the postfix form: `int list` rather than `list<int>`.</span></span>
2. <span data-ttu-id="2f957-182">에 대 한 F# 옵션을 사용 후 위 형식: `int option` 대신 `option<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-182">For F# Options, use the postfix form: `int option` rather than `option<int>`.</span></span>
3. <span data-ttu-id="2f957-183">에 대 한 F# 배열 구문 이름을 사용 하 여 `int[]` 대신 `int array` 하거나 `array<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-183">For F# arrays, use the syntactic name `int[]` rather than `int array` or `array<int>`.</span></span>
4. <span data-ttu-id="2f957-184">참조 셀에 대 한 사용 `int ref` 대신 `ref<int>` 또는 `Ref<int>`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-184">For Reference Cells, use `int ref` rather than `ref<int>` or `Ref<int>`.</span></span>

<span data-ttu-id="2f957-185">다른 모든 형식에 대 한 접두사 형식을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-185">For all other types, use the prefix form.</span></span>

## <a name="formatting-tuples"></a><span data-ttu-id="2f957-186">튜플 형식</span><span class="sxs-lookup"><span data-stu-id="2f957-186">Formatting tuples</span></span>

<span data-ttu-id="2f957-187">튜플 인스턴스화를 괄호로 묶고 고 내의 구분 쉼표 뒤에 야 공백, 예: `(1, 2)`, `(x, y, z)`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-187">A tuple instantiation should be parenthesized, and the delimiting commas within should be followed by a single space, for example: `(1, 2)`, `(x, y, z)`.</span></span>

<span data-ttu-id="2f957-188">튜플 패턴 일치에서 괄호를 생략 하려면 일반적으로 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-188">It is commonly accepted to omit parentheses in pattern matching of tuples:</span></span>

```fsharp
let (x, y) = z // Destructuring
let x, y = z // OK

// OK
match x, y with
| 1, _ -> 0
| x, 1 -> 0
| x, y -> 1
```

<span data-ttu-id="2f957-189">튜플 함수 반환 값인 경우 괄호를 생략 하려면 일반적으로 허용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-189">It is also commonly accepted to omit parentheses if the tuple is the return value of a function:</span></span>

```fsharp
// OK
let update model msg =
    match msg with
    | 1 -> model + 1, []
    | _ -> model, [ msg ]
```

<span data-ttu-id="2f957-190">요약 하자면, 괄호로 묶인 튜플 인스턴스화를 선호 하지만 패턴 일치 또는 반환 값에 대 한 튜플을 사용 하는 경우 괄호를 방지 하려면 세밀 하 게 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-190">In summary, prefer parenthesized tuple instantiations, but when using tuples for pattern matching or a return value, it is considered fine to avoid parentheses.</span></span>

## <a name="formatting-discriminated-union-declarations"></a><span data-ttu-id="2f957-191">구별 된 공용 구조체 선언 서식 지정</span><span class="sxs-lookup"><span data-stu-id="2f957-191">Formatting discriminated union declarations</span></span>

<span data-ttu-id="2f957-192">들여쓰기 `|` 4 개의 공백 사용 하 여 형식 정의에서:</span><span class="sxs-lookup"><span data-stu-id="2f957-192">Indent `|` in type definition by 4 spaces:</span></span>

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

## <a name="formatting-discriminated-unions"></a><span data-ttu-id="2f957-193">구별 된 공용 구조체 형식</span><span class="sxs-lookup"><span data-stu-id="2f957-193">Formatting discriminated unions</span></span>

<span data-ttu-id="2f957-194">여러 줄에 분할 된 인스턴스화된 구별 된 공용 구조체 들여쓰기를 사용 하 여 새 범위를 포함 된 데이터를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-194">Instantiated Discriminated Unions that split across multiple lines should give contained data a new scope with indentation:</span></span>

```fsharp
let tree1 =
    BinaryNode
        (BinaryNode(BinaryValue 1, BinaryValue 2),
         BinaryNode(BinaryValue 3, BinaryValue 4))
```

<span data-ttu-id="2f957-195">닫는 괄호를 새 줄 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-195">The closing parenthesis can also be on a new line:</span></span>

```fsharp
let tree1 =
    BinaryNode(
        BinaryNode(BinaryValue 1, BinaryValue 2),
        BinaryNode(BinaryValue 3, BinaryValue 4)
    )
```

## <a name="formatting-record-declarations"></a><span data-ttu-id="2f957-196">서식 레코드 선언</span><span class="sxs-lookup"><span data-stu-id="2f957-196">Formatting record declarations</span></span>

<span data-ttu-id="2f957-197">들여쓰기 `{` 형식에서 4로 정의 공백 및 필드 목록 같은 줄에서 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-197">Indent `{` in type definition by 4 spaces and start the field list on the same line:</span></span>

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

<span data-ttu-id="2f957-198">열기 토큰을 새 줄의 닫는 토큰을 새 줄에 배치 하는 것은 레코드에서 인터페이스 구현 또는 멤버를 선언 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-198">Placing the opening token on a new line and the closing token on a new line is preferable if you are declaring interface implementations or members on the record:</span></span>

```fsharp
// Declaring additional members on PostalAddress
type PostalAddress =
    {
        Address: string
        City: string
        Zip: string
    } with
    member x.ZipAndCity = sprintf "%s %s" x.Zip x.City

type MyRecord =
    {
        SomeField: int
    }
    interface IMyInterface
```

## <a name="formatting-records"></a><span data-ttu-id="2f957-199">레코드 형식</span><span class="sxs-lookup"><span data-stu-id="2f957-199">Formatting records</span></span>

<span data-ttu-id="2f957-200">짧은 레코드는 한 줄에 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-200">Short records can be written in one line:</span></span>

```fsharp
let point = { X = 1.0; Y = 0.0 }
```

<span data-ttu-id="2f957-201">오래 된 레코드는 레이블에 대 한 새 줄을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-201">Records that are longer should use new lines for labels:</span></span>

```fsharp
let rainbow =
    { Boss = "Jeffrey"
      Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="2f957-202">배치를 여는 새 줄에 토큰 콘텐츠 탭 하나를 통해 범위 및 새 줄에 닫는 토큰이 있다면 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-202">Placing the opening token on a new line, the contents tabbed over one scope, and the closing token on a new line is preferable if you are:</span></span>

* <span data-ttu-id="2f957-203">다양 한 들여쓰기 범위를 사용 하 여 코드 내에서 레코드를 이동</span><span class="sxs-lookup"><span data-stu-id="2f957-203">Moving records around in code with different indentation scopes</span></span>
* <span data-ttu-id="2f957-204">함수에 파이프 하</span><span class="sxs-lookup"><span data-stu-id="2f957-204">Piping them into a function</span></span>

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

<span data-ttu-id="2f957-205">목록 및 배열 요소에 대 한 동일한 규칙이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-205">The same rules apply for list and array elements.</span></span>

## <a name="formatting-copy-and-update-record-expressions"></a><span data-ttu-id="2f957-206">형식 지정 식 복사 및 업데이트 레코드</span><span class="sxs-lookup"><span data-stu-id="2f957-206">Formatting copy-and-update record expressions</span></span>

<span data-ttu-id="2f957-207">복사 및 업데이트 레코드 식이 a 레코드 여전히 유사한 지침이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-207">A copy-and-update record expression is still a record, so similar guidelines apply.</span></span>

<span data-ttu-id="2f957-208">간단한 식 한 줄에 넣을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-208">Short expressions can fit on one line:</span></span>

```fsharp
let point2 = { point with X = 1; Y = 2 }
```

<span data-ttu-id="2f957-209">긴 식 새 줄을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-209">Longer expressions should use new lines:</span></span>

```fsharp
let rainbow2 =
    { rainbow with
        Boss = "Jeffrey"
        Lackeys = ["Zippy"; "George"; "Bungle"] }
```

<span data-ttu-id="2f957-210">및로 레코드 지침을 사용 하 여 하려는 중괄호에 대 한 별도 줄을 염두에 두고 있고 하나의 범위에서 식 사용 하 여 오른쪽 들여쓰기입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-210">And as with the record guidance, you may want to dedicate separate lines for the braces and indent one scope to the right with the expression.</span></span> <span data-ttu-id="2f957-211">괄호가 없을 경우 선택적으로 값을 래핑 같은 특별 한 경우도 있습니다 할 경우 한 줄에 중괄호를 유지 하는 참고:</span><span class="sxs-lookup"><span data-stu-id="2f957-211">Note that in some special cases, such as wrapping a value with an optional without parentheses, you may need to keep a brace on one line:</span></span>

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

## <a name="formatting-lists-and-arrays"></a><span data-ttu-id="2f957-212">서식 지정 목록 및 배열</span><span class="sxs-lookup"><span data-stu-id="2f957-212">Formatting lists and arrays</span></span>

<span data-ttu-id="2f957-213">작성할 `x :: l` 주위에 공백을 사용 하 여 합니다 `::` 연산자 (`::` 는 공백으로 둘러싸인 따라서 중 위 연산자,)입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-213">Write `x :: l` with spaces around the `::` operator (`::` is an infix operator, hence surrounded by spaces).</span></span>

<span data-ttu-id="2f957-214">목록과 배열 선언 줄에 여는 괄호 뒤와 닫는 괄호 앞에 공백이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-214">List and arrays declared on a single line should have a space after the opening bracket and before the closing bracket:</span></span>

```fsharp
let xs = [ 1; 2; 3 ]
let ys = [| 1; 2; 3; |]
```

<span data-ttu-id="2f957-215">항상 두 명의 고유 중괄호 같은 연산자 사이 하나 이상의 공백을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-215">Always use at least one space between two distinct brace-like operators.</span></span> <span data-ttu-id="2f957-216">예를 들어 사이 공백을 둡니다를 `[` 및 `{`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-216">For example, leave a space between a `[` and a `{`.</span></span>

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

<span data-ttu-id="2f957-217">목록 또는 튜플의 배열에 대 한 동일한 지침이 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-217">The same guideline applies for lists or arrays of tuples.</span></span>

<span data-ttu-id="2f957-218">목록 및 여러 줄 분할 되는 배열 레코드와 마찬가지로 비슷한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-218">Lists and arrays that split across multiple lines follow a similar rule as records do:</span></span>

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

<span data-ttu-id="2f957-219">와 레코드와 마찬가지로 자체 줄에 여는 태그와 닫는 괄호를 선언 보다 쉽게 이동 코딩 및 함수에 파이핑 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-219">And as with records, declaring the opening and closing brackets on their own line will make moving code around and piping into functions easier.</span></span>

## <a name="formatting-if-expressions"></a><span data-ttu-id="2f957-220">경우에 형식 지정 식</span><span class="sxs-lookup"><span data-stu-id="2f957-220">Formatting if expressions</span></span>

<span data-ttu-id="2f957-221">조건문의 들여쓰기 구성 하는 식의 크기에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-221">Indentation of conditionals depends on the sizes of the expressions that make them up.</span></span> <span data-ttu-id="2f957-222">하는 경우 `cond`, `e1` 및 `e2` 짧은, 한 줄에 작성 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-222">If `cond`, `e1` and `e2` are short, simply write them on one line:</span></span>

```fsharp
if cond then e1 else e2
```

<span data-ttu-id="2f957-223">경우 `cond`, `e1` 또는 `e2` 더 있지만 여러 줄 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-223">If either `cond`, `e1` or `e2` are longer, but not multi-line:</span></span>

```fsharp
if cond
then e1
else e2
```

<span data-ttu-id="2f957-224">식이 있는 경우 여러 줄:</span><span class="sxs-lookup"><span data-stu-id="2f957-224">If any of the expressions are multi-line:</span></span>

```fsharp
if cond then
    e1
else
    e2
```

<span data-ttu-id="2f957-225">사용 하 여 여러 가지 조건을 `elif` 하 고 `else` 와 동일한 범위에서 들여쓰기가 적용 되는 `if`:</span><span class="sxs-lookup"><span data-stu-id="2f957-225">Multiple conditionals with `elif` and `else` are indented at the same scope as the `if`:</span></span>

```fsharp
if cond1 then e1
elif cond2 then e2
elif cond3 then e3
else e4
```

### <a name="pattern-matching-constructs"></a><span data-ttu-id="2f957-226">패턴 일치 하는 구문</span><span class="sxs-lookup"><span data-stu-id="2f957-226">Pattern matching constructs</span></span>

<span data-ttu-id="2f957-227">사용 된 `|` 없습니다 들여쓰기를 사용 하 여 일치 하는 각 절에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-227">Use a `|` for each clause of a match with no indentation.</span></span> <span data-ttu-id="2f957-228">식 짧은 경우 각 하위 식에 간단한 이기도 한 경우는 단일 선을 사용을 고려할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-228">If the expression is short, you can consider using a single line if each subexpression is also simple.</span></span>

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

<span data-ttu-id="2f957-229">패턴 일치 화살표 오른쪽의 식이 너무 큰 경우 들여쓰기 한 단계에서 다음 줄으로 이동 합니다 `match` / `|`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-229">If the expression on the right of the pattern matching arrow is too large, move it to the following line, indented one step from the `match`/`|`.</span></span>

```fsharp
match lam with
| Var v -> 1
| Abs(x, body) ->
    1 + sizeLambda body
| App(lam1, lam2) ->
    sizeLambda lam1 + sizeLambda lam2

```

<span data-ttu-id="2f957-230">패턴 일치 익명 함수에 의해 시작 `function`을 해야 일반적으로 들여쓰지 멀리 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-230">Pattern matching of anonymous functions, starting by `function`, should generally not indent too far.</span></span> <span data-ttu-id="2f957-231">예를 들어, 한 범위를 다음과 같이 들여쓰기 괜찮습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-231">For example, indenting one scope as follows is fine:</span></span>

```fsharp
lambdaList
|> List.map (function
    | Abs(x, body) -> 1 + sizeLambda 0 body
    | App(lam1, lam2) -> sizeLambda (sizeLambda 0 lam1) lam2
    | Var v -> 1)
```

<span data-ttu-id="2f957-232">패턴에서 정의 된 함수에서 일치 `let` 또는 `let rec` 시작 후 들여쓰기 4 공간을 사용 해야 `let`경우에 `function` 키워드가 사용:</span><span class="sxs-lookup"><span data-stu-id="2f957-232">Pattern matching in functions defined by `let` or `let rec` should be indented 4 spaces after starting of `let`, even if `function` keyword is used:</span></span>

```fsharp
let rec sizeLambda acc = function
    | Abs(x, body) -> sizeLambda (succ acc) body
    | App(lam1, lam2) -> sizeLambda (sizeLambda acc lam1) lam2
    | Var v -> succ acc
```

<span data-ttu-id="2f957-233">화살표를 정렬 하는 것은 좋지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-233">We do not recommend aligning arrows.</span></span>

## <a name="formatting-trywith-expressions"></a><span data-ttu-id="2f957-234">서식 지정 시도 / 식을 사용 하 여</span><span class="sxs-lookup"><span data-stu-id="2f957-234">Formatting try/with expressions</span></span>

<span data-ttu-id="2f957-235">예외 형식에 패턴 일치와 같은 수준에서 써야 `with`합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-235">Pattern matching on the exception type should be indented at the same level as `with`.</span></span>

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

## <a name="formatting-function-parameter-application"></a><span data-ttu-id="2f957-236">서식 지정 함수에 대 한 매개 변수 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="2f957-236">Formatting function parameter application</span></span>

<span data-ttu-id="2f957-237">일반적으로 대부분의 함수 매개 변수 응용 프로그램 같은 줄에서 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-237">In general, most function parameter application is done on the same line.</span></span>

<span data-ttu-id="2f957-238">새 줄에 함수에 매개 변수를 적용 하려는 경우 하나의 범위로 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-238">If you wish to apply parameters to a function on a new line, indent them by one scope.</span></span>

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

<span data-ttu-id="2f957-239">동일한 지침이 함수 인수로 람다 식에 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-239">The same guidelines apply for lambda expressions as function arguments.</span></span> <span data-ttu-id="2f957-240">범위를 하나 만큼 들여씁니다 본문 람다 식의 본문에서 다른 줄에 넣을 수 있는 경우</span><span class="sxs-lookup"><span data-stu-id="2f957-240">If the body of a lambda expression, the body can have another line, indented by one scope</span></span>

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

<span data-ttu-id="2f957-241">그러나 둘 이상의 줄 람다 식의 본문을 사용 하는 경우 별도 함수에 팩터링 하는 것이 좋습니다 보다 단일 인수로 함수에 적용 하는 여러 줄 구문입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-241">However, if the body of a lambda expression is more than one line, consider factoring it out into a separate function rather than have a multi-line construct applied as a single argument to a function.</span></span>

### <a name="formatting-infix-operators"></a><span data-ttu-id="2f957-242">서식 지정 중 위 연산자</span><span class="sxs-lookup"><span data-stu-id="2f957-242">Formatting infix operators</span></span>

<span data-ttu-id="2f957-243">공백 사용 하 여 별도 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-243">Separate operators by spaces.</span></span> <span data-ttu-id="2f957-244">이 규칙에 확실 한 예외는 `!` 고 `.` 연산자.</span><span class="sxs-lookup"><span data-stu-id="2f957-244">Obvious exceptions to this rule are the `!` and `.` operators.</span></span>

<span data-ttu-id="2f957-245">중 위 식은 다음과 같습니다. 확인에 동일한 열 목록</span><span class="sxs-lookup"><span data-stu-id="2f957-245">Infix expressions are OK to lineup on same column:</span></span>

```fsharp
acc +
(sprintf "\t%s - %i\n\r"
     x.IngredientName x.Quantity)

let function1 arg1 arg2 arg3 arg4 =
    arg1 + arg2 +
    arg3 + arg4
```

### <a name="formatting-pipeline-operators"></a><span data-ttu-id="2f957-246">파이프라인 연산자를 서식 지정</span><span class="sxs-lookup"><span data-stu-id="2f957-246">Formatting pipeline operators</span></span>

<span data-ttu-id="2f957-247">파이프라인 `|>` 연산자에서 작동 하는 식 아래에 있는 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-247">Pipeline `|>` operators should go underneath the expressions they operate on.</span></span>

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

### <a name="formatting-modules"></a><span data-ttu-id="2f957-248">모듈을 서식 지정</span><span class="sxs-lookup"><span data-stu-id="2f957-248">Formatting modules</span></span>

<span data-ttu-id="2f957-249">로컬 모듈의 코드 모듈을 기준으로 써야 하지만 최상위 모듈에는 코드를 들여쓰지 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-249">Code in a local module must be indented relative to the module, but code in a top-level module should not be indented.</span></span> <span data-ttu-id="2f957-250">Namespace 요소 들여쓰기 될 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-250">Namespace elements do not have to be indented.</span></span>

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

### <a name="formatting-object-expressions-and-interfaces"></a><span data-ttu-id="2f957-251">서식 개체 식 및 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f957-251">Formatting object expressions and interfaces</span></span>

<span data-ttu-id="2f957-252">개체 식 및 인터페이스는 동일한 방식으로 정렬 해야 합니다 `member` 4 개의 공백을 후 들여쓰기 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-252">Object expressions and interfaces should be aligned in the same way with `member` being indented after 4 spaces.</span></span>

```fsharp
let comparer =
    { new IComparer<string> with
          member x.Compare(s1, s2) =
              let rev (s: String) =
                  new String (Array.rev (s.ToCharArray()))
              let reversed = rev s1
              reversed.CompareTo (rev s2) }
```

### <a name="formatting-white-space-in-expressions"></a><span data-ttu-id="2f957-253">식에서 공백 서식 지정</span><span class="sxs-lookup"><span data-stu-id="2f957-253">Formatting white space in expressions</span></span>

<span data-ttu-id="2f957-254">불필요 한 공백을 사용 하지 않습니다 F# 식입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-254">Avoid extraneous white space in F# expressions.</span></span>

```fsharp
// OK
spam (ham.[1])

// Not OK
spam ( ham.[ 1 ] )
```

<span data-ttu-id="2f957-255">명명 된 인수도 없어야 공간 관련 된 `=`:</span><span class="sxs-lookup"><span data-stu-id="2f957-255">Named arguments should also not have space surrounding the `=`:</span></span>

```fsharp
// OK
let makeStreamReader x = new System.IO.StreamReader(path=x)

// Not OK
let makeStreamReader x = new System.IO.StreamReader(path = x)
```

## <a name="formatting-attributes"></a><span data-ttu-id="2f957-256">서식 지정 특성</span><span class="sxs-lookup"><span data-stu-id="2f957-256">Formatting attributes</span></span>

<span data-ttu-id="2f957-257">[특성](../language-reference/attributes.md) 구문 위에 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-257">[Attributes](../language-reference/attributes.md) are placed above a construct:</span></span>

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

### <a name="formatting-attributes-on-parameters"></a><span data-ttu-id="2f957-258">매개 변수에 대 한 서식 특성</span><span class="sxs-lookup"><span data-stu-id="2f957-258">Formatting attributes on parameters</span></span>

<span data-ttu-id="2f957-259">특성의 매개 변수 위치 일 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-259">Attributes can also be places on parameters.</span></span> <span data-ttu-id="2f957-260">이 경우 이름을 매개 변수로 전과 동일한 줄에 다음 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-260">In this case, place then on the same line as the parameter and before the name:</span></span>

```fsharp
// Defines a class that takes an optional value as input defaulting to false.
type C() =
    member __.M([<Optional; DefaultParameterValue(false)>] doSomething: bool)
```

### <a name="formatting-multiple-attributes"></a><span data-ttu-id="2f957-261">여러 특성을 서식 지정</span><span class="sxs-lookup"><span data-stu-id="2f957-261">Formatting multiple attributes</span></span>

<span data-ttu-id="2f957-262">여러 특성 매개 변수 없는 구문에 적용 되 면 배치 되어야 줄당 하나의 특성이 되도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-262">When multiple attributes are applied to a construct that is not a parameter, they should be placed such that there is one attribute per line:</span></span>

```fsharp
[<Struct>]
[<IsByRefLike>]
type MyRecord =
    { Label1: int
      Label2: string }
```

<span data-ttu-id="2f957-263">매개 변수를 적용 하면 동일한 줄에 있어야 하며 구분을 `;` 구분 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-263">When applied to a parameter, they must be on the same line and separated by a `;` separator.</span></span>

## <a name="formatting-literals"></a><span data-ttu-id="2f957-264">형식 지정 리터럴</span><span class="sxs-lookup"><span data-stu-id="2f957-264">Formatting literals</span></span>

<span data-ttu-id="2f957-265">[F#리터럴](../language-reference/literals.md) 를 사용 하는 `Literal` 특성에서 특성 자체 줄에 배치 하 고 camelCase 명명을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f957-265">[F# literals](../language-reference/literals.md) using the `Literal` attribute should place the attribute on its own line and use camelCase naming:</span></span>

```fsharp
[<Literal>]
let path = __SOURCE_DIRECTORY__ + "/" + __SOURCE_FILE__

[<Literal>]
let myUrl = "www.mywebsitethatiamworkingwith.com"
```

<span data-ttu-id="2f957-266">특성 값으로 동일한 줄에 배치 하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="2f957-266">Avoid placing the attribute on the same line as the value.</span></span>
