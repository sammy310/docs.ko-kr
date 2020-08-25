---
title: 패턴 일치
description: 'F #에서 패턴을 사용 하 여 데이터를 논리적 구조와 비교 하거나 데이터를 구성 부분으로 분해 하거나 데이터에서 정보를 추출 하는 방법을 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 6d284b941824bc15a8e872a4e28e22c0e159191d
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88811511"
---
# <a name="pattern-matching"></a><span data-ttu-id="1ed3e-103">패턴 일치</span><span class="sxs-lookup"><span data-stu-id="1ed3e-103">Pattern Matching</span></span>

<span data-ttu-id="1ed3e-104">패턴은 입력 데이터를 변환 하는 규칙입니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-104">Patterns are rules for transforming input data.</span></span> <span data-ttu-id="1ed3e-105">이러한 데이터는 F # 언어 전체에서 데이터를 논리적 구조 또는 구조와 비교 하거나, 데이터를 구성 부분으로 분해 하거나, 다양 한 방법으로 데이터에서 정보를 추출 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-105">They are used throughout the F# language to compare data with a logical structure or structures, decompose data into constituent parts, or extract information from data in various ways.</span></span>

## <a name="remarks"></a><span data-ttu-id="1ed3e-106">설명</span><span class="sxs-lookup"><span data-stu-id="1ed3e-106">Remarks</span></span>

<span data-ttu-id="1ed3e-107">패턴은 식과 같은 다양 한 언어 구문에서 사용 됩니다 `match` .</span><span class="sxs-lookup"><span data-stu-id="1ed3e-107">Patterns are used in many language constructs, such as the `match` expression.</span></span> <span data-ttu-id="1ed3e-108">이러한 함수는 `let` 바인딩, 람다 식 및 식과 연결 된 예외 처리기의 함수에 대 한 인수를 처리할 때 사용 됩니다 `try...with` .</span><span class="sxs-lookup"><span data-stu-id="1ed3e-108">They are used when you are processing arguments for functions in `let` bindings, lambda expressions, and in the exception handlers associated with the `try...with` expression.</span></span> <span data-ttu-id="1ed3e-109">자세한 내용은 [일치 식](match-expressions.md), [let 바인딩](./functions/let-bindings.md), [람다 식: `fun` 키워드](./functions/lambda-expressions-the-fun-keyword.md)및 [예외: `try...with` 식](./exception-handling/the-try-with-expression.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-109">For more information, see [Match Expressions](match-expressions.md), [let Bindings](./functions/let-bindings.md), [Lambda Expressions: The `fun` Keyword](./functions/lambda-expressions-the-fun-keyword.md), and [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

<span data-ttu-id="1ed3e-110">예를 들어 식에서 `match` *패턴* 은 파이프 기호 뒤에 오는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-110">For example, in the `match` expression, the *pattern* is what follows the pipe symbol.</span></span>

```fsharp
match expression with
| pattern [ when condition ] -> result-expression
...
```

<span data-ttu-id="1ed3e-111">각 패턴은 특정 방식으로 입력을 변환 하는 규칙 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-111">Each pattern acts as a rule for transforming input in some way.</span></span> <span data-ttu-id="1ed3e-112">식에서 `match` 각 패턴을 검사 하 여 입력 데이터가 패턴과 호환 되는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-112">In the `match` expression, each pattern is examined in turn to see if the input data is compatible with the pattern.</span></span> <span data-ttu-id="1ed3e-113">일치 하는 항목이 있으면 결과 식이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-113">If a match is found, the result expression is executed.</span></span> <span data-ttu-id="1ed3e-114">일치 항목을 찾을 수 없는 경우 다음 패턴 규칙을 테스트 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-114">If a match is not found, the next pattern rule is tested.</span></span> <span data-ttu-id="1ed3e-115">선택적 when *조건* 부분은 [일치 식](match-expressions.md)에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-115">The optional when *condition* part is explained in [Match Expressions](match-expressions.md).</span></span>

<span data-ttu-id="1ed3e-116">다음 표에서는 지원 되는 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-116">Supported patterns are shown in the following table.</span></span> <span data-ttu-id="1ed3e-117">런타임에 입력은 테이블에 나열 된 순서 대로 다음 각 패턴에 대해 테스트 되 고 패턴은 코드에 표시 되는 첫 번째부터 마지막으로, 각 줄의 패턴에 대해 왼쪽에서 오른쪽으로 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-117">At run time, the input is tested against each of the following patterns in the order listed in the table, and patterns are applied recursively, from first to last as they appear in your code, and from left to right for the patterns on each line.</span></span>

|<span data-ttu-id="1ed3e-118">Name</span><span class="sxs-lookup"><span data-stu-id="1ed3e-118">Name</span></span>|<span data-ttu-id="1ed3e-119">Description</span><span class="sxs-lookup"><span data-stu-id="1ed3e-119">Description</span></span>|<span data-ttu-id="1ed3e-120">예제</span><span class="sxs-lookup"><span data-stu-id="1ed3e-120">Example</span></span>|
|----|-----------|-------|
|<span data-ttu-id="1ed3e-121">상수 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-121">Constant pattern</span></span>|<span data-ttu-id="1ed3e-122">모든 숫자, 문자 또는 문자열 리터럴, 열거형 상수 또는 정의 된 리터럴 식별자</span><span class="sxs-lookup"><span data-stu-id="1ed3e-122">Any numeric, character, or string literal, an enumeration constant, or a defined literal identifier</span></span>|<span data-ttu-id="1ed3e-123">`1.0`, `"test"`, `30`, `Color.Red`</span><span class="sxs-lookup"><span data-stu-id="1ed3e-123">`1.0`, `"test"`, `30`, `Color.Red`</span></span>|
|<span data-ttu-id="1ed3e-124">식별자 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-124">Identifier pattern</span></span>|<span data-ttu-id="1ed3e-125">구분 된 공용 구조체, 예외 레이블 또는 활성 패턴 사례의 case 값</span><span class="sxs-lookup"><span data-stu-id="1ed3e-125">A case value of a discriminated union, an exception label, or an active pattern case</span></span>|`Some(x)`<br /><br />`Failure(msg)`|
|<span data-ttu-id="1ed3e-126">변수 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-126">Variable pattern</span></span>|<span data-ttu-id="1ed3e-127">*identifier*</span><span class="sxs-lookup"><span data-stu-id="1ed3e-127">*identifier*</span></span>|`a`|
|<span data-ttu-id="1ed3e-128">`as` 되풀이</span><span class="sxs-lookup"><span data-stu-id="1ed3e-128">`as` pattern</span></span>|<span data-ttu-id="1ed3e-129">*식별자* 로 서의 *패턴*</span><span class="sxs-lookup"><span data-stu-id="1ed3e-129">*pattern* as *identifier*</span></span>|`(a, b) as tuple1`|
|<span data-ttu-id="1ed3e-130">OR 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-130">OR pattern</span></span>|<span data-ttu-id="1ed3e-131">*pattern1* &#124; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="1ed3e-131">*pattern1* &#124; *pattern2*</span></span>|<code>([h] &#124; [h; _])</code>|
|<span data-ttu-id="1ed3e-132">및 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-132">AND pattern</span></span>|<span data-ttu-id="1ed3e-133">*pattern1* &amp; *pattern2*</span><span class="sxs-lookup"><span data-stu-id="1ed3e-133">*pattern1* &amp; *pattern2*</span></span>|`(a, b) & (_, "test")`|
|<span data-ttu-id="1ed3e-134">단점 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-134">Cons pattern</span></span>|<span data-ttu-id="1ed3e-135">*identifier* :: *list 식별자*</span><span class="sxs-lookup"><span data-stu-id="1ed3e-135">*identifier* :: *list-identifier*</span></span>|`h :: t`|
|<span data-ttu-id="1ed3e-136">목록 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-136">List pattern</span></span>|<span data-ttu-id="1ed3e-137">[ *pattern_1*; ...; *pattern_n* ]</span><span class="sxs-lookup"><span data-stu-id="1ed3e-137">[ *pattern_1*; ... ; *pattern_n* ]</span></span>|`[ a; b; c ]`|
|<span data-ttu-id="1ed3e-138">배열 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-138">Array pattern</span></span>|<span data-ttu-id="1ed3e-139">[&#124; *pattern_1*; ...; *pattern_n* &#124;]</span><span class="sxs-lookup"><span data-stu-id="1ed3e-139">[&#124; *pattern_1*; ..; *pattern_n* &#124;]</span></span>|<code>[&#124; a; b; c &#124;]</code>|
|<span data-ttu-id="1ed3e-140">괄호로 묶인 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-140">Parenthesized pattern</span></span>|<span data-ttu-id="1ed3e-141">( *패턴* )</span><span class="sxs-lookup"><span data-stu-id="1ed3e-141">( *pattern* )</span></span>|`( a )`|
|<span data-ttu-id="1ed3e-142">튜플 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-142">Tuple pattern</span></span>|<span data-ttu-id="1ed3e-143">( *pattern_1*, ..., *pattern_n* )</span><span class="sxs-lookup"><span data-stu-id="1ed3e-143">( *pattern_1*, ... , *pattern_n* )</span></span>|`( a, b )`|
|<span data-ttu-id="1ed3e-144">레코드 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-144">Record pattern</span></span>|<span data-ttu-id="1ed3e-145">{ *identifier1*  =  *pattern_1*; ... ; *identifier_n*  =  *pattern_n* }</span><span class="sxs-lookup"><span data-stu-id="1ed3e-145">{ *identifier1* = *pattern_1*; ... ; *identifier_n* = *pattern_n* }</span></span>|`{ Name = name; }`|
|<span data-ttu-id="1ed3e-146">와일드 카드 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-146">Wildcard pattern</span></span>|<span data-ttu-id="1ed3e-147">_</span><span class="sxs-lookup"><span data-stu-id="1ed3e-147">_</span></span>|`_`|
|<span data-ttu-id="1ed3e-148">형식 주석과 함께 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-148">Pattern together with type annotation</span></span>|<span data-ttu-id="1ed3e-149">*패턴* : *형식*</span><span class="sxs-lookup"><span data-stu-id="1ed3e-149">*pattern* : *type*</span></span>|`a : int`|
|<span data-ttu-id="1ed3e-150">형식 테스트 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-150">Type test pattern</span></span>|<span data-ttu-id="1ed3e-151">:?</span><span class="sxs-lookup"><span data-stu-id="1ed3e-151">:?</span></span> <span data-ttu-id="1ed3e-152">*유형* [as *식별자* ]</span><span class="sxs-lookup"><span data-stu-id="1ed3e-152">*type* [ as *identifier* ]</span></span>|`:? System.DateTime as dt`|
|<span data-ttu-id="1ed3e-153">Null 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-153">Null pattern</span></span>|<span data-ttu-id="1ed3e-154">null</span><span class="sxs-lookup"><span data-stu-id="1ed3e-154">null</span></span>|`null`|

## <a name="constant-patterns"></a><span data-ttu-id="1ed3e-155">상수 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-155">Constant Patterns</span></span>

<span data-ttu-id="1ed3e-156">상수 패턴은 숫자, 문자 및 문자열 리터럴, 열거형 상수 (열거형 형식 이름 포함)입니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-156">Constant patterns are numeric, character, and string literals, enumeration constants (with the enumeration type name included).</span></span> <span data-ttu-id="1ed3e-157">`match`상수 패턴만 있는 식은 다른 언어의 case 문과 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-157">A `match` expression that has only constant patterns can be compared to a case statement in other languages.</span></span> <span data-ttu-id="1ed3e-158">입력을 리터럴 값과 비교 하 고 값이 같으면 패턴이 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-158">The input is compared with the literal value and the pattern matches if the values are equal.</span></span> <span data-ttu-id="1ed3e-159">리터럴의 형식은 입력의 형식과 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-159">The type of the literal must be compatible with the type of the input.</span></span>

<span data-ttu-id="1ed3e-160">다음 예제에서는 리터럴 패턴을 사용 하는 방법을 보여 줍니다. 또한 변수 패턴과 또는 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-160">The following example demonstrates the use of literal patterns, and also uses a variable pattern and an OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4801.fs)]

<span data-ttu-id="1ed3e-161">리터럴 패턴의 또 다른 예로는 열거 상수를 기반으로 하는 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-161">Another example of a literal pattern is a pattern based on enumeration constants.</span></span> <span data-ttu-id="1ed3e-162">열거형 상수를 사용 하는 경우 열거형 형식 이름을 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-162">You must specify the enumeration type name when you use enumeration constants.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4802.fs)]

## <a name="identifier-patterns"></a><span data-ttu-id="1ed3e-163">식별자 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-163">Identifier Patterns</span></span>

<span data-ttu-id="1ed3e-164">패턴이 유효한 식별자를 구성 하는 문자열인 경우 식별자의 형식에 따라 패턴이 일치 하는 방법이 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-164">If the pattern is a string of characters that forms a valid identifier, the form of the identifier determines how the pattern is matched.</span></span> <span data-ttu-id="1ed3e-165">식별자가 단일 문자 보다 길고 대문자로 시작 하는 경우 컴파일러는 식별자 패턴에 대해 일치를 수행 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-165">If the identifier is longer than a single character and starts with an uppercase character, the compiler tries to make a match to the identifier pattern.</span></span> <span data-ttu-id="1ed3e-166">이 패턴의 식별자는 리터럴 특성, 구분 된 공용 구조체 케이스, 예외 식별자 또는 활성 패턴 사례로 표시 된 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-166">The identifier for this pattern could be a value marked with the Literal attribute, a discriminated union case, an exception identifier, or an active pattern case.</span></span> <span data-ttu-id="1ed3e-167">일치 하는 식별자를 찾을 수 없으면 일치가 실패 하 고 다음 패턴 규칙 인 변수 패턴은 입력과 비교 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-167">If no matching identifier is found, the match fails and the next pattern rule, the variable pattern, is compared to the input.</span></span>

<span data-ttu-id="1ed3e-168">구분 된 공용 구조체 패턴은 단순한 명명 된 사례 이거나 값 또는 여러 값이 포함 된 튜플을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-168">Discriminated union patterns can be simple named cases or they can have a value, or a tuple containing multiple values.</span></span> <span data-ttu-id="1ed3e-169">값이 있는 경우 값에 대 한 식별자를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-169">If there is a value, you must specify an identifier for the value.</span></span> <span data-ttu-id="1ed3e-170">튜플의 경우 하나 이상의 명명 된 공용 구조체 필드에 대 한 필드 이름이 포함 된 식별자 나 튜플의 각 요소에 대 한 식별자를 사용 하 여 튜플 패턴을 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-170">In the case of a tuple, you must supply a tuple pattern with an identifier for each element of the tuple or an identifier with a field name for one or more named union fields.</span></span> <span data-ttu-id="1ed3e-171">예제는이 섹션의 코드 예제를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-171">See the code examples in this section for examples.</span></span>

<span data-ttu-id="1ed3e-172">`option`형식은 및의 두 가지 경우를 포함 하는 구별 된 공용 구조체입니다 `Some` `None` .</span><span class="sxs-lookup"><span data-stu-id="1ed3e-172">The `option` type is a discriminated union that has two cases, `Some` and `None`.</span></span> <span data-ttu-id="1ed3e-173">한 case ( `Some` )에는 값이 있지만 다른 하나는 `None` 명명 된 case입니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-173">One case (`Some`) has a value, but the other (`None`) is just a named case.</span></span> <span data-ttu-id="1ed3e-174">따라서는 `Some` 사례와 연결 된 값에 대 한 변수를 포함 해야 `Some` 하지만 `None` 자체로 표시 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-174">Therefore, `Some` needs to have a variable for the value associated with the `Some` case, but `None` must appear by itself.</span></span> <span data-ttu-id="1ed3e-175">다음 코드에서 변수에는 `var1` case와 일치 하 여 얻은 값이 제공 됩니다 `Some` .</span><span class="sxs-lookup"><span data-stu-id="1ed3e-175">In the following code, the variable `var1` is given the value that is obtained by matching to the `Some` case.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4803.fs)]

<span data-ttu-id="1ed3e-176">다음 예제에서 `PersonName` 구별 된 공용 구조체에는 가능한 형식의 이름을 나타내는 문자열과 문자의 혼합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-176">In the following example, the `PersonName` discriminated union contains a mixture of strings and characters that represent possible forms of names.</span></span> <span data-ttu-id="1ed3e-177">구분 된 공용 구조체의 사례는 `FirstOnly` , `LastOnly` 및 `FirstLast` 입니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-177">The cases of the discriminated union are `FirstOnly`, `LastOnly`, and `FirstLast`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4804.fs)]

<span data-ttu-id="1ed3e-178">명명 된 필드가 있는 구별 된 공용 구조체의 경우에는 등호 (=)를 사용 하 여 명명 된 필드의 값을 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-178">For discriminated unions that have named fields, you use the equals sign (=) to extract the value of a named field.</span></span> <span data-ttu-id="1ed3e-179">예를 들어 다음과 같은 선언으로 구분 된 공용 구조체를 생각해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-179">For example, consider a discriminated union with a declaration like the following.</span></span>

```fsharp
type Shape =
    | Rectangle of height : float * width : float
    | Circle of radius : float
```

<span data-ttu-id="1ed3e-180">패턴 일치 식에서 다음과 같이 명명 된 필드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-180">You can use the named fields in a pattern matching expression as follows.</span></span>

```fsharp
let matchShape shape =
    match shape with
    | Rectangle(height = h) -> printfn "Rectangle with length %f" h
    | Circle(r) -> printfn "Circle with radius %f" r
```

<span data-ttu-id="1ed3e-181">명명 된 필드의 사용은 선택 사항 이므로 앞의 예제에서 및는 모두 `Circle(r)` `Circle(radius = r)` 동일한 효과를 가집니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-181">The use of the named field is optional, so in the previous example, both `Circle(r)` and `Circle(radius = r)` have the same effect.</span></span>

<span data-ttu-id="1ed3e-182">여러 필드를 지정 하는 경우 세미콜론 (;)을 사용 합니다. 구분 기호로.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-182">When you specify multiple fields, use the semicolon (;) as a separator.</span></span>

```fsharp
match shape with
| Rectangle(height = h; width = w) -> printfn "Rectangle with height %f and width %f" h w
| _ -> ()
```

<span data-ttu-id="1ed3e-183">활성 패턴을 사용 하면 보다 복잡 한 사용자 지정 패턴 일치를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-183">Active patterns enable you to define more complex custom pattern matching.</span></span> <span data-ttu-id="1ed3e-184">활성 패턴에 대 한 자세한 내용은 [활성 패턴](active-patterns.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-184">For more information about active patterns, see [Active Patterns](active-patterns.md).</span></span>

<span data-ttu-id="1ed3e-185">식별자가 예외인 경우 예외 처리기의 컨텍스트에서 패턴 일치에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-185">The case in which the identifier is an exception is used in pattern matching in the context of exception handlers.</span></span> <span data-ttu-id="1ed3e-186">예외 처리의 패턴 일치에 대 한 자세한 내용은 [예외: `try...with` 식](./exception-handling/the-try-with-expression.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-186">For information about pattern matching in exception handling, see [Exceptions: The `try...with` Expression](./exception-handling/the-try-with-expression.md).</span></span>

## <a name="variable-patterns"></a><span data-ttu-id="1ed3e-187">변수 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-187">Variable Patterns</span></span>

<span data-ttu-id="1ed3e-188">변수 패턴은 변수 이름에 일치 하는 값을 할당 합니다. 그런 다음 기호 오른쪽의 실행 식에 사용할 수 있습니다 `->` .</span><span class="sxs-lookup"><span data-stu-id="1ed3e-188">The variable pattern assigns the value being matched to a variable name, which is then available for use in the execution expression to the right of the `->` symbol.</span></span> <span data-ttu-id="1ed3e-189">변수 패턴 단독은 모든 입력과 일치 하지만 변수 패턴은 종종 다른 패턴 내에 표시 되므로 튜플 및 배열과 같은 보다 복잡 한 구조를 변수로 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-189">A variable pattern alone matches any input, but variable patterns often appear within other patterns, therefore enabling more complex structures such as tuples and arrays to be decomposed into variables.</span></span>

<span data-ttu-id="1ed3e-190">다음 예제에서는 튜플 패턴 내의 변수 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-190">The following example demonstrates a variable pattern within a tuple pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4805.fs)]

## <a name="as-pattern"></a><span data-ttu-id="1ed3e-191">as 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-191">as Pattern</span></span>

<span data-ttu-id="1ed3e-192">`as`패턴은 절이 추가 된 패턴입니다 `as` .</span><span class="sxs-lookup"><span data-stu-id="1ed3e-192">The `as` pattern is a pattern that has an `as` clause appended to it.</span></span> <span data-ttu-id="1ed3e-193">절은 일치 하는 `as` 값을 식의 실행 식에 사용할 수 있는 이름에 바인딩합니다 `match` . 또는이 패턴을 바인딩에서 사용 하는 경우에는 `let` 이름이 로컬 범위에 바인딩으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-193">The `as` clause binds the matched value to a name that can be used in the execution expression of a `match` expression, or, in the case where this pattern is used in a `let` binding, the name is added as a binding to the local scope.</span></span>

<span data-ttu-id="1ed3e-194">다음 예제에서는 패턴을 사용 합니다 `as` .</span><span class="sxs-lookup"><span data-stu-id="1ed3e-194">The following example uses an `as` pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4806.fs)]

## <a name="or-pattern"></a><span data-ttu-id="1ed3e-195">OR 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-195">OR Pattern</span></span>

<span data-ttu-id="1ed3e-196">또는 패턴은 입력 데이터가 여러 패턴을 일치 시킬 수 있는 경우와 같은 코드를 결과로 실행 하려고 할 때 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-196">The OR pattern is used when input data can match multiple patterns, and you want to execute the same code as a result.</span></span> <span data-ttu-id="1ed3e-197">또는 패턴 양쪽의 형식이 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-197">The types of both sides of the OR pattern must be compatible.</span></span>

<span data-ttu-id="1ed3e-198">다음 예제에서는 또는 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-198">The following example demonstrates the OR pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4807.fs)]

## <a name="and-pattern"></a><span data-ttu-id="1ed3e-199">및 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-199">AND Pattern</span></span>

<span data-ttu-id="1ed3e-200">및 패턴에서는 입력이 두 패턴에 일치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-200">The AND pattern requires that the input match two patterns.</span></span> <span data-ttu-id="1ed3e-201">및 패턴의 양쪽 모두 형식이 호환 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-201">The types of both sides of the AND pattern must be compatible.</span></span>

<span data-ttu-id="1ed3e-202">다음 예제는 `detectZeroTuple` 이 항목의 뒷부분에 나오는 튜플 패턴 단원에 나와 있는 것과 유사 하지만 및 `var1` 패턴을 사용 하 여 및 모두 `var2` 값으로 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-202">The following example is like `detectZeroTuple` shown in the Tuple Pattern section later in this topic, but here both `var1` and `var2` are obtained as values by using the AND pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4808.fs)]

## <a name="cons-pattern"></a><span data-ttu-id="1ed3e-203">단점 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-203">Cons Pattern</span></span>

<span data-ttu-id="1ed3e-204">단점 패턴은 목록을 첫 번째 요소, *헤드*및 나머지 요소 ( *tail*)가 포함 된 목록으로 분해 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-204">The cons pattern is used to decompose a list into the first element, the *head*, and a list that contains the remaining elements, the *tail*.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4809.fs)]

## <a name="list-pattern"></a><span data-ttu-id="1ed3e-205">목록 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-205">List Pattern</span></span>

<span data-ttu-id="1ed3e-206">목록 패턴을 사용 하면 목록을 여러 요소로 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-206">The list pattern enables lists to be decomposed into a number of elements.</span></span> <span data-ttu-id="1ed3e-207">목록 패턴 자체는 특정 수의 요소 목록만 일치 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-207">The list pattern itself can match only lists of a specific number of elements.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4810.fs)]

## <a name="array-pattern"></a><span data-ttu-id="1ed3e-208">배열 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-208">Array Pattern</span></span>

<span data-ttu-id="1ed3e-209">배열 패턴은 목록 패턴과 비슷하며 특정 길이의 배열을 분해 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-209">The array pattern resembles the list pattern and can be used to decompose arrays of a specific length.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4811.fs)]

## <a name="parenthesized-pattern"></a><span data-ttu-id="1ed3e-210">괄호로 묶인 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-210">Parenthesized Pattern</span></span>

<span data-ttu-id="1ed3e-211">괄호는 원하는 결합성을 얻기 위해 패턴을 기준으로 그룹화 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-211">Parentheses can be grouped around patterns to achieve the desired associativity.</span></span> <span data-ttu-id="1ed3e-212">다음 예제에서는 괄호를 사용 하 여 및 패턴과 단점 패턴 간의 연관성을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-212">In the following example, parentheses are used to control associativity between an AND pattern and a cons pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4812.fs)]

## <a name="tuple-pattern"></a><span data-ttu-id="1ed3e-213">튜플 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-213">Tuple Pattern</span></span>

<span data-ttu-id="1ed3e-214">튜플 패턴은 튜플 형식의 입력과 일치 하며 튜플의 각 위치에 대해 패턴 일치 변수를 사용 하 여 튜플을 구성 요소로 분해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-214">The tuple pattern matches input in tuple form and enables the tuple to be decomposed into its constituent elements by using pattern matching variables for each position in the tuple.</span></span>

<span data-ttu-id="1ed3e-215">다음 예제에서는 튜플 패턴을 보여 주고 리터럴 패턴, 변수 패턴 및 와일드 카드 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-215">The following example demonstrates the tuple pattern and also uses literal patterns, variable patterns, and the wildcard pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4813.fs)]

## <a name="record-pattern"></a><span data-ttu-id="1ed3e-216">레코드 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-216">Record Pattern</span></span>

<span data-ttu-id="1ed3e-217">레코드 패턴은 레코드를 분해 하 여 필드 값을 추출 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-217">The record pattern is used to decompose records to extract the values of fields.</span></span> <span data-ttu-id="1ed3e-218">패턴은 레코드의 모든 필드를 참조할 필요가 없습니다. 생략 된 필드는 일치에 참여 하지 않으며 추출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-218">The pattern does not have to reference all fields of the record; any omitted fields just do not participate in matching and are not extracted.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4814.fs)]

## <a name="wildcard-pattern"></a><span data-ttu-id="1ed3e-219">와일드 카드 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-219">Wildcard Pattern</span></span>

<span data-ttu-id="1ed3e-220">와일드 카드 패턴은 밑줄 ( `_` ) 문자로 표시 되 고 변수 패턴과 마찬가지로 입력을 일치 시킵니다. 단, 입력은 변수에 할당 되는 것이 아니라 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-220">The wildcard pattern is represented by the underscore (`_`) character and matches any input, just like the variable pattern, except that the input is discarded instead of assigned to a variable.</span></span> <span data-ttu-id="1ed3e-221">와일드 카드 패턴은 기호 오른쪽의 식에 필요 하지 않은 값에 대 한 자리 표시자로 다른 패턴 내에서 자주 사용 됩니다 `->` .</span><span class="sxs-lookup"><span data-stu-id="1ed3e-221">The wildcard pattern is often used within other patterns as a placeholder for values that are not needed in the expression to the right of the `->` symbol.</span></span> <span data-ttu-id="1ed3e-222">또한 와일드 카드 패턴은 일치 하지 않는 입력을 일치 시키기 위해 패턴 목록의 끝에 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-222">The wildcard pattern is also frequently used at the end of a list of patterns to match any unmatched input.</span></span> <span data-ttu-id="1ed3e-223">와일드 카드 패턴은이 항목의 여러 코드 예제에서 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-223">The wildcard pattern is demonstrated in many code examples in this topic.</span></span> <span data-ttu-id="1ed3e-224">한 가지 예는 위의 코드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-224">See the preceding code for one example.</span></span>

## <a name="patterns-that-have-type-annotations"></a><span data-ttu-id="1ed3e-225">형식 주석이 있는 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-225">Patterns That Have Type Annotations</span></span>

<span data-ttu-id="1ed3e-226">패턴에 형식 주석을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-226">Patterns can have type annotations.</span></span> <span data-ttu-id="1ed3e-227">다른 형식 주석과 같은 다른 형식 주석과 가이드 유추와 같은 방식으로 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-227">These behave like other type annotations and guide inference like other type annotations.</span></span> <span data-ttu-id="1ed3e-228">패턴의 형식 주석 앞뒤에는 괄호가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-228">Parentheses are required around type annotations in patterns.</span></span> <span data-ttu-id="1ed3e-229">다음 코드에서는 형식 주석이 있는 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-229">The following code shows a pattern that has a type annotation.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4815.fs)]

## <a name="type-test-pattern"></a><span data-ttu-id="1ed3e-230">형식 테스트 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-230">Type Test Pattern</span></span>

<span data-ttu-id="1ed3e-231">형식 테스트 패턴은 입력을 형식에 대해 일치 시키는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-231">The type test pattern is used to match the input against a type.</span></span> <span data-ttu-id="1ed3e-232">입력 형식이 패턴에 지정 된 형식 (또는 파생 형식)과 일치 하면 일치가 성공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-232">If the input type is a match to (or a derived type of) the type specified in the pattern, the match succeeds.</span></span>

<span data-ttu-id="1ed3e-233">다음 예제에서는 형식 테스트 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-233">The following example demonstrates the type test pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4816.fs)]

<span data-ttu-id="1ed3e-234">식별자가 특정 파생 형식 인지만 확인 하는 경우 `as identifier` 다음 예제와 같이 패턴의 일부가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-234">If you're only checking if an identifier is of a particular derived type, you don't need the `as identifier` part of the pattern, as shown in the following example:</span></span>

```fsharp
type A() = class end
type B() = inherit A()
type C() = inherit A()

let m (a: A) =
    match a with
    | :? B -> printfn "It's a B"
    | :? C -> printfn "It's a C"
    | _ -> ()
```

## <a name="null-pattern"></a><span data-ttu-id="1ed3e-235">Null 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-235">Null Pattern</span></span>

<span data-ttu-id="1ed3e-236">Null 패턴은 null 값을 허용 하는 형식으로 작업할 때 나타날 수 있는 null 값과 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-236">The null pattern matches the null value that can appear when you are working with types that allow a null value.</span></span> <span data-ttu-id="1ed3e-237">Null 패턴은 .NET Framework 코드와 상호 작용할 때 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-237">Null patterns are frequently used when interoperating with .NET Framework code.</span></span> <span data-ttu-id="1ed3e-238">예를 들어 .NET API의 반환 값은 식에 대 한 입력이 될 수 있습니다 `match` .</span><span class="sxs-lookup"><span data-stu-id="1ed3e-238">For example, the return value of a .NET API might be the input to a `match` expression.</span></span> <span data-ttu-id="1ed3e-239">반환 값이 null 인지 여부 및 반환 된 값의 다른 특성에 따라 프로그램 흐름을 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-239">You can control program flow based on whether the return value is null, and also on other characteristics of the returned value.</span></span> <span data-ttu-id="1ed3e-240">Null 패턴을 사용 하 여 null 값이 프로그램의 나머지 부분에 전파 되지 않도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-240">You can use the null pattern to prevent null values from propagating to the rest of your program.</span></span>

<span data-ttu-id="1ed3e-241">다음 예에서는 null 패턴과 변수 패턴을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1ed3e-241">The following example uses the null pattern and the variable pattern.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4817.fs)]

## <a name="see-also"></a><span data-ttu-id="1ed3e-242">추가 정보</span><span class="sxs-lookup"><span data-stu-id="1ed3e-242">See also</span></span>

- [<span data-ttu-id="1ed3e-243">일치 식</span><span class="sxs-lookup"><span data-stu-id="1ed3e-243">Match Expressions</span></span>](match-expressions.md)
- [<span data-ttu-id="1ed3e-244">활성 패턴</span><span class="sxs-lookup"><span data-stu-id="1ed3e-244">Active Patterns</span></span>](active-patterns.md)
- [<span data-ttu-id="1ed3e-245">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="1ed3e-245">F# Language Reference</span></span>](index.md)
