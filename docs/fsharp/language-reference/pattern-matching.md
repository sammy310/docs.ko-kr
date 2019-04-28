---
title: 패턴 일치
description: 패턴을 사용 하는 방법을 알아봅니다 F# 논리 구조를 사용 하 여 데이터를 비교 하려면 데이터를 구성 부분으로 분해 하거나 데이터에서 정보를 추출 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: bb6b41f6d15612e4a65abd4a3d5d7291d84a8f3c
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61795462"
---
# <a name="pattern-matching"></a><span data-ttu-id="db877-103">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="db877-103">Pattern Matching</span></span>

<span data-ttu-id="db877-104">패턴은 입력된 데이터를 변환 하는 것에 대 한 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="db877-105">전체에서 사용 되는 F# 논리적 구조체 또는 구조체를 사용 하 여 데이터를 비교 하는 언어 구성 요소에 데이터를 분해 또는 다양 한 방법으로 데이터에서 정보를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="db877-106">설명</span><span class="sxs-lookup"><span data-stu-id="db877-106">Remarks</span></span>

<span data-ttu-id="db877-107">패턴은 같은 여러 가지 언어 구문에 사용 되는 `match` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="db877-108">함수에 대 한 인수를 처리 하는 경우 사용할 `let` 바인딩, 람다 식에 연결 된 예외 처리기는 `try...with` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="db877-109">자세한 내용은 [일치 식](match-expressions.md)를 [let 바인딩](functions/let-bindings.md), [람다 식: 합니다 `fun` 키워드](functions/lambda-expressions-the-fun-keyword.md), 및 [예외: 합니다 `try...with` 식](exception-handling/the-try-with-expression.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="db877-110">예를 들어를 `match` 식을 *패턴* 파이프 기호 뒤에 오는 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="db877-111">각 패턴은 어떤 방식으로든에서 입력을 변환 하기 위한 규칙에 따라 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="db877-112">에 `match` 식에서는 각 패턴은 입력된 데이터의 패턴을 사용 하 여 호환 되는지 확인 하려면 다시 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="db877-113">일치 하는 항목이 있으면 결과 식에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="db877-114">일치 하는 항목이 없는 경우 다음 번 패턴 규칙 테스트 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="db877-115">선택적 요소인 when *조건을* 부분에 설명 되어 [일치 식](match-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="db877-116">지원 되는 패턴은 다음 표에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="db877-117">런타임 시 각 테이블에 나열 된 순서로 다음 패턴에 대 한 입력을 테스트 및 패턴은 재귀적으로 적용된에서 처음부터 마지막 코드에 왼쪽에서 오른쪽 패턴에 대해 각 줄에 나타나는 대로 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="db877-118">이름</span><span class="sxs-lookup"><span data-stu-id="db877-118">Name</span></span>|<span data-ttu-id="db877-119">설명</span><span class="sxs-lookup"><span data-stu-id="db877-119">Description</span></span>|<span data-ttu-id="db877-120">예제</span><span class="sxs-lookup"><span data-stu-id="db877-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="db877-121">상수 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-121">Constant pattern</span></span>|<span data-ttu-id="db877-122">모든 숫자, 문자 또는 문자열 리터럴, 열거형 상수, 또는 정의 된 리터럴 식별자</span><span class="sxs-lookup"><span data-stu-id="db877-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="db877-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="db877-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="db877-124">식별자 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-124">Identifier pattern</span></span>|<span data-ttu-id="db877-125">구별된 된 공용 구조체, 예외 레이블 또는 활성 패턴 case의 case 값</span><span class="sxs-lookup"><span data-stu-id="db877-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="db877-126">변수 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-126">Variable pattern</span></span>|<span data-ttu-id="db877-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="db877-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="db877-128">`as` 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-128">`as` pattern</span></span>|<span data-ttu-id="db877-129">*패턴* 으로 *식별자*</span><span class="sxs-lookup"><span data-stu-id="db877-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="db877-130">또는 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-130">OR pattern</span></span>|<span data-ttu-id="db877-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="db877-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="db877-132">및 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-132">AND pattern</span></span>|<span data-ttu-id="db877-133">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="db877-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="db877-134">Cons 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-134">Cons pattern</span></span>|<span data-ttu-id="db877-135">*identifier* :: *list-identifier*</span><span class="sxs-lookup"><span data-stu-id="db877-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="db877-136">목록 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-136">List pattern</span></span>|<span data-ttu-id="db877-137">[ *pattern_1*; ... ; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="db877-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="db877-138">배열 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-138">Array pattern</span></span>|<span data-ttu-id="db877-139">[&#124; *pattern_1*;...; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="db877-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="db877-140">범위 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-140">Parenthesized pattern</span></span>|<span data-ttu-id="db877-141">( *pattern* )</span><span class="sxs-lookup"><span data-stu-id="db877-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="db877-142">튜플 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-142">Tuple pattern</span></span>|<span data-ttu-id="db877-143">( *pattern_1*, ... , *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="db877-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="db877-144">레코드 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-144">Record pattern</span></span>|<span data-ttu-id="db877-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="db877-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="db877-146">와일드 카드 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-146">Wildcard pattern</span></span>|<span data-ttu-id="db877-147">_</span><span class="sxs-lookup"><span data-stu-id="db877-147">_</span></span>|`_`|
|<span data-ttu-id="db877-148">형식 주석이 함께 포함 된 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-148">Pattern together with type annotation</span></span>|<span data-ttu-id="db877-149">*패턴* : *형식*</span><span class="sxs-lookup"><span data-stu-id="db877-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="db877-150">형식 테스트 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-150">Type test pattern</span></span>|<span data-ttu-id="db877-151">:?</span><span class="sxs-lookup"><span data-stu-id="db877-151">:?</span></span> <span data-ttu-id="db877-152">*형식* [로 *식별자* ]</span><span class="sxs-lookup"><span data-stu-id="db877-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="db877-153">Null 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-153">Null pattern</span></span>|<span data-ttu-id="db877-154">null</span><span class="sxs-lookup"><span data-stu-id="db877-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="db877-155">상수 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-155">Constant Patterns</span></span>

<span data-ttu-id="db877-156">상수 패턴은 숫자, 문자 및 문자열 리터럴, 열거형 상수 (열거형 형식의 이름 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="db877-157">`match` 상수 패턴만 있는 식을 다른 언어의 case 문과 비교해 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="db877-158">입력은 리터럴 값과 비교 하 고 값이 같으면 패턴이 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="db877-159">리터럴의 형식을 입력의 형식과 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="db877-160">다음 예에서는 리터럴 패턴의 사용을 보여 줍니다 및 변수 패턴과 OR 패턴도 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="db877-161">리터럴 패턴의 또 다른 예로 열거형 상수에 기반을 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="db877-162">열거형 상수를 사용 하는 경우에 열거형 형식 이름을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="db877-163">식별자 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-163">Identifier Patterns</span></span>

<span data-ttu-id="db877-164">패턴이 유효한 식별자를 형성 하는 문자 문자열인 경우 식별자의 형식 패턴 일치 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="db877-165">식별자는 단일 문자 보다 긴를 대문자로 시작 하는 경우 컴파일러는 식별자 패턴과 일치 여부를 확인 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="db877-166">이 패턴의 식별자는 리터럴 특성는 구별 된 공용 구조체 케이스, 예외 식별자 또는 활성 패턴 케이스로 표시 된 값을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="db877-167">일치 하는 식별자가 없는 경우 검색이 실패 하 고 패턴 규칙 인 변수 패턴을 입력으로 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="db877-168">구별 된 공용 구조체 패턴 간단한 명명 된 case 또는 수는 값 또는 여러 값이 포함 된 튜플을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="db877-169">값의 경우 값에 대 한 식별자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="db877-170">튜플의 경우 튜플 패턴에는 튜플의 각 요소에 대 한 식별자 또는 하나에 대 한 필드 이름 포함 하는 식별자를 제공 해야 합니다 또는 이상의 명명 된 공용 구조체 필드입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="db877-171">예제를 보려면이 섹션의 코드 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db877-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="db877-172">합니다 `option` 이라는 두 케이스가 있는 구별된 된 공용 구조체 유형이 `Some` 고 `None`합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="db877-173">한 가지 경우 (`Some`)에 값은 있지만 다른 (`None`) 명명 된 사례 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="db877-174">따라서 `Some` 연관 된 값에 대 한 변수를 보유 해야 합니다 `Some` 있지만 `None` 자체적으로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="db877-175">다음 코드에서 변수 `var1` 일치를 통해 얻은 값이 지정 되는 `Some` 사례입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="db877-176">다음 예제에서는 `PersonName` 구별 된 공용 구조체에 문자열 및 문자 이름의 수 있는 형식을 나타내는 노드가 혼합 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="db877-177">구별 된 공용 구조체의 경우가 `FirstOnly`, `LastOnly`, 및 `FirstLast`합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="db877-178">명명 된 필드가 있는 구별 된 공용 구조체, 등호 (=) 사용 하 여 명명된 된 필드의 값을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="db877-179">예를 들어, 다음과 같은 선언 사용 하 여 구별된 된 공용 구조체를 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="db877-180">패턴 일치 식에서 명명된 된 필드를 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="db877-181">명명된 된 필드의 사용은 선택 사항 이므로 이전 예제에서는 둘 다 `Circle(r)` 고 `Circle(radius = r)` 효과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="db877-182">세미콜론 (;)를 사용 하 여 여러 필드를 지정 하는 경우를 구분 기호로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="db877-183">활성 패턴을 사용 하 여 더 복잡 한 사용자 지정 패턴 일치를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="db877-184">활성 패턴에 대 한 자세한 내용은 참조 하세요. [활성 패턴](active-patterns.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="db877-185">식별자가 예외가 있는 경우는 예외 처리기의 컨텍스트에서 일치 하는 패턴에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="db877-186">예외 처리의 패턴 일치에 대 한 자세한 내용은 참조 하세요. [예외: 합니다 `try...with` 식](exception-handling/the-try-with-expression.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="db877-187">변수 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-187">Variable Patterns</span></span>

<span data-ttu-id="db877-188">변수 패턴은 오른쪽의 실행 식에 사용할 수 있는 되는 변수 이름에 일치 하는 값을 할당 합니다 `->` 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="db877-189">변수 패턴 만으로도 모든 입력을 일치 하지만 변수 패턴 튜플과 배열 변수를 분해할 수 같은 더 복잡 한 구조체를 사용 하므로 다른 패턴 내에 나타나는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="db877-190">다음 예제에서는 튜플 패턴 내에서 변수 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db877-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="db877-191">as 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-191">as Pattern</span></span>

<span data-ttu-id="db877-192">합니다 `as` 패턴은 있는 패턴을 `as` 절이 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="db877-193">`as` 절의 실행 식에 사용할 수 있는 이름에 일치 하는 값을 바인딩하는 `match` 식 또는 경우에이 패턴은 사용 하는 위치를 `let` 바인딩, 로컬 범위에 대 한 바인딩으로 이름이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="db877-194">다음 예제에서는 `as` 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="db877-195">또는 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-195">OR Pattern</span></span>

<span data-ttu-id="db877-196">OR 패턴에는 입력된 데이터에는 여러 패턴에 일치 시킬 수 있고 결과적으로 동일한 코드를 실행 하려는 경우 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="db877-197">OR 패턴의 양쪽 모두의 형식이 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="db877-198">다음 예제에서는 OR 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db877-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="db877-199">및 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-199">AND Pattern</span></span>

<span data-ttu-id="db877-200">AND 패턴 입력이 두 가지 패턴 일치는 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="db877-201">AND 패턴의 양쪽 모두의 형식이 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="db877-202">다음과 같습니다 `detectZeroTuple` 에서처럼 합니다 [튜플 패턴](https://msdn.microsoft.com/library/#tuple) 섹션의 뒷부분에 나오는이 항목에서는 있지만 여기에는 둘 다 `var1` 및 `var2` AND 패턴을 사용 하 여 가져온 값으로.</span><span class="sxs-lookup"><span data-stu-id="db877-202">The following example is like `detectZeroTuple` shown in the [Tuple Pattern](https://msdn.microsoft.com/library/#tuple) section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="db877-203">Cons 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-203">Cons Pattern</span></span>

<span data-ttu-id="db877-204">Cons 패턴의 첫 번째 요소로 분해 하는 합니다 *헤드*, 및 나머지 요소를 포함 하는 목록을 합니다 *비상*.</span><span class="sxs-lookup"><span data-stu-id="db877-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="db877-205">목록 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-205">List Pattern</span></span>

<span data-ttu-id="db877-206">목록 패턴 목록을 요소의 수를 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="db877-207">목록 패턴 자체에 특정 수의 요소를 이루어진 목록만 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="db877-208">배열 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-208">Array Pattern</span></span>

<span data-ttu-id="db877-209">배열 패턴은 목록 패턴과 비슷하며 및 특정 길이의 배열을 분해를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="db877-210">범위 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-210">Parenthesized Pattern</span></span>

<span data-ttu-id="db877-211">패턴을 원하는 대로 결합할 주위의 괄호를 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="db877-212">다음 예제에서는 괄호는 여 AND 패턴과 cons 패턴 사이의 결합 관계를 제어 하려면 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="db877-213">튜플 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-213">Tuple Pattern</span></span>

<span data-ttu-id="db877-214">튜플 패턴은 튜플 형식의 입력을 일치 및 패턴 일치는 튜플의 각 위치에 대 한 변수를 사용 하 여 해당 구성 요소로 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="db877-215">다음 예제에서는 튜플 패턴을 보여 줍니다 및 리터럴 패턴, 변수 패턴 및 와일드 카드 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="db877-216">레코드 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-216">Record Pattern</span></span>

<span data-ttu-id="db877-217">레코드 패턴은 필드의 값을 추출 하는 레코드를 분해 하기 위해 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="db877-218">패턴을 레코드의 모든 필드를 참조할 필요가 없습니다. 생략된 한 필드는 방금 일치에 참여 하지 않습니다 하 고 추출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="db877-219">와일드 카드 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-219">Wildcard Pattern</span></span>

<span data-ttu-id="db877-220">와일드 카드 패턴은 밑줄 표현 (`_`) 문자 및 입력 변수에 할당 대신 삭제 되는 점을 제외 하 고, 변수 패턴과 마찬가지로 모든 입력을 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="db877-221">와일드 카드 패턴은 대개 다른 패턴 내 자리 표시자로 오른쪽의 식에 필요 하지 않은 값을 `->` 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="db877-222">와일드 카드 패턴 일치 하지 않는 입력을 일치 하도록 패턴 목록의 끝에도 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="db877-223">이 항목의 많은 코드 예제에서 와일드 카드 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db877-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="db877-224">앞의 코드에 대 한 예를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="db877-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="db877-225">형식 주석이 함께 포함 하는 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="db877-226">패턴 형식 주석을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-226">Patterns can have type annotations.</span></span> <span data-ttu-id="db877-227">이러한 다른 형식 주석과 마찬가지로 동작 및 다른 형식 주석과 마찬가지로 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="db877-228">패턴에서 형식 주석을 주위의 괄호 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="db877-229">다음 코드 형식 주석이 있는 패턴을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="db877-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="db877-230">형식 테스트 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-230">Type Test Pattern</span></span>

<span data-ttu-id="db877-231">형식 테스트 패턴 일치 형식에 대해 입력이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="db877-232">입력 형식이 일치 하는 (또는 파생된 형식의) 패턴을 일치 하는 지정 된 형식 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="db877-233">다음 예제에서는 형식 테스트 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="db877-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

## <a name="null-pattern"></a><span data-ttu-id="db877-234">Null 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-234">Null Pattern</span></span>

<span data-ttu-id="db877-235">Null 패턴은 null 값을 허용 하는 형식을 사용 하 여 작업할 때 나타날 수 있는 null 값을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-235">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="db877-236">Null 패턴은.NET Framework 코드와 상호 작용할 때 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="db877-236">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="db877-237">예를 들어,.NET API의 반환 값에 대 한 입력 수를 `match` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="db877-237">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="db877-238">반환 값이 null 인지 그리고 반환된 된 값의 기타 특성에 따라 프로그램 흐름을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-238">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="db877-239">Null 패턴은 전파 프로그램의 나머지 부분에서 null 값을 방지 하기 위해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="db877-239">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="db877-240">다음 예제에서는 null 패턴과 변수 패턴을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="db877-240">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="db877-241">참고자료</span><span class="sxs-lookup"><span data-stu-id="db877-241">See also</span></span>

- [<span data-ttu-id="db877-242">일치 식</span><span class="sxs-lookup"><span data-stu-id="db877-242">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="db877-243">활성 패턴</span><span class="sxs-lookup"><span data-stu-id="db877-243">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="db877-244">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="db877-244">F# Language Reference</span></span>](index.md)