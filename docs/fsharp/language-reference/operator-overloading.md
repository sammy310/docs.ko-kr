---
title: 연산자 오버로드
description: 전역 수준에서 클래스 또는 레코드 형식에 산술 연산자를 오버 로드 하는 방법을 알아봅니다 F#입니다.
ms.date: 05/16/2016
ms.openlocfilehash: c4b52b02522b750aa55ca6cf4097295e35ab1739
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61666250"
---
# <a name="operator-overloading"></a><span data-ttu-id="35ba5-103">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="35ba5-103">Operator Overloading</span></span>

<span data-ttu-id="35ba5-104">이 항목에는 전역 수준에서 클래스 또는 레코드 형식에 산술 연산자를 오버 로드 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>

## <a name="syntax"></a><span data-ttu-id="35ba5-105">구문</span><span class="sxs-lookup"><span data-stu-id="35ba5-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="35ba5-106">설명</span><span class="sxs-lookup"><span data-stu-id="35ba5-106">Remarks</span></span>

<span data-ttu-id="35ba5-107">위 구문에는 *연산자 기호* 중 하나인 `+`, `-`, `*`, `/`, `=`등.</span><span class="sxs-lookup"><span data-stu-id="35ba5-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="35ba5-108">합니다 *매개 변수 목록을* 연산자에 대 한 일반적인 구문에 나타나는 순서로 피연산자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="35ba5-109">합니다 *메서드 본문* 결과 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="35ba5-110">연산자에 대 한 연산자 오버 로드는 정적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="35ba5-111">같은 단항 연산자의 연산자 오버 로드 `+` 및 `-`, 물결표를 사용 해야 합니다 (`~`)에 *연산자 기호* 에서처럼 연산자는 단항 연산자, 이항 연산자가 아니라,을 나타내기 위해 합니다 다음 선언입니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="35ba5-112">다음 코드에서는 연산자가 두 개뿐인 벡터 클래스를 보여 줍니다. 그 중 하나는 단항 빼기 연산자이고 다른 하나는 스칼라 값을 곱하기 위한 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="35ba5-113">예제에서는 두 개의 오버 로드가 스칼라 곱하기 연산자 벡터와 스칼라 나타나는 순서에 관계 없이 작동 해야 하기 때문에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="35ba5-114">새 운영자 만들기</span><span class="sxs-lookup"><span data-stu-id="35ba5-114">Creating New Operators</span></span>

<span data-ttu-id="35ba5-115">모든 표준 연산자를 오버 로드할 수 있지만 새 연산자 특정 문자의 시퀀스를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="35ba5-116">연산자 문자는 허용 `!`, `%`, `&`, `*`, `+`를 `-`, `.`를 `/`, `<`를 `=`, `>`, `?`, `@`, `^`합니다 `|`, 및 `~`합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="35ba5-117">`~` 문자는 연산자 단항 만드는 특별 한 의미가 및 연산자 문자 시퀀스의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="35ba5-118">일부 연산자는 단항을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="35ba5-119">사용할 정확한 문자 시퀀스에 따라 특정 우선 순위 및 결합성에 연산자 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="35ba5-120">결합성 왼쪽 또는 오른쪽에서 왼쪽으로 하거나 유지할 수 있습니다 하 고의 우선 순위가 동일한 연산자에 괄호가 없는 순서로 표시 될 때마다 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="35ba5-121">연산자 문자 `.` 예를 들어, 동일한 우선 순위 및 결합성 일반 곱으로 포함 하는 곱하기의 고유한 버전을 정의 하려는 경우 등의연산자만들수있도록우선순위,영향을주지않습니다`.*`.</span><span class="sxs-lookup"><span data-stu-id="35ba5-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="35ba5-122">연산자만 `?` 하 고 `?<-` 로 시작할 수 `?`입니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="35ba5-123">모든 연산자의 우선 순위를 보여 주는 테이블이 F# 에서 찾을 수 있습니다 [기호 및 연산자 참조](symbol-and-operator-reference/index.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](symbol-and-operator-reference/index.md).</span></span>

## <a name="overloaded-operator-names"></a><span data-ttu-id="35ba5-124">오버 로드 된 연산자 이름</span><span class="sxs-lookup"><span data-stu-id="35ba5-124">Overloaded Operator Names</span></span>

<span data-ttu-id="35ba5-125">경우는 F# 컴파일러 컴파일합니다 연산자 식 연산자에 대 한 컴파일러에서 생성 된 이름을 가진 메서드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="35ba5-126">이 MSIL (Microsoft intermediate language) 방법의 경우에 리플렉션 및 IntelliSense에 표시 되는 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="35ba5-127">일반적으로에서 이러한 이름을 사용할 필요가 없습니다 F# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="35ba5-128">다음 표에서 표준 연산자를 보여 줍니다. 하 고 해당 이름을 생성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-128">The following table shows the standard operators and their corresponding generated names.</span></span>

|<span data-ttu-id="35ba5-129">연산자</span><span class="sxs-lookup"><span data-stu-id="35ba5-129">Operator</span></span>|<span data-ttu-id="35ba5-130">생성 된 이름</span><span class="sxs-lookup"><span data-stu-id="35ba5-130">Generated name</span></span>|
|--------|--------------|
|`[]`|`op_Nil`|
|`::`|`op_Cons`|
|`+`|`op_Addition`|
|`-`|`op_Subtraction`|
|`*`|`op_Multiply`|
|`/`|`op_Division`|
|`@`|`op_Append`|
|`^`|`op_Concatenate`|
|`%`|`op_Modulus`|
|`&&&`|`op_BitwiseAnd`|
|<code>&#124;&#124;&#124;</code>|`op_BitwiseOr`|
|`^^^`|`op_ExclusiveOr`|
|`<<<`|`op_LeftShift`|
|`~~~`|`op_LogicalNot`|
|`>>>`|`op_RightShift`|
|`~+`|`op_UnaryPlus`|
|`~-`|`op_UnaryNegation`|
|`=`|`op_Equality`|
|`<=`|`op_LessThanOrEqual`|
|`>=`|`op_GreaterThanOrEqual`|
|`<`|`op_LessThan`|
|`>`|`op_GreaterThan`|
|`?`|`op_Dynamic`|
|`?<-`|`op_DynamicAssignment`|
|<code>&#124;></code>|`op_PipeRight`|
|<code><&#124;</code>|`op_PipeLeft`|
|`!`|`op_Dereference`|
|`>>`|`op_ComposeRight`|
|`<<`|`op_ComposeLeft`|
|`<@ @>`|`op_Quotation`|
|`<@@ @@>`|`op_QuotationUntyped`|
|`+=`|`op_AdditionAssignment`|
|`-=`|`op_SubtractionAssignment`|
|`*=`|`op_MultiplyAssignment`|
|`/=`|`op_DivisionAssignment`|
|`..`|`op_Range`|
|`.. ..`|`op_RangeStep`|

<span data-ttu-id="35ba5-131">여기에 나열 되지 않는 연산자의 다른 조합을 연산자로 사용할 수 있고 다음 테이블에서 개별 문자에 대 한 이름을 연결 하 여 구성 된 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="35ba5-132">예를 들어, +!</span><span class="sxs-lookup"><span data-stu-id="35ba5-132">For example, +!</span></span> <span data-ttu-id="35ba5-133">가 `op_PlusBang`합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-133">becomes `op_PlusBang`.</span></span>

|<span data-ttu-id="35ba5-134">연산자 문자</span><span class="sxs-lookup"><span data-stu-id="35ba5-134">Operator character</span></span>|<span data-ttu-id="35ba5-135">이름</span><span class="sxs-lookup"><span data-stu-id="35ba5-135">Name</span></span>|
|------------------|----|
|`>`|`Greater`|
|`<`|`Less`|
|`+`|`Plus`|
|`-`|`Minus`|
|`*`|`Multiply`|
|`/`|`Divide`|
|`=`|`Equals`|
|`~`|`Twiddle`|
|`%`|`Percent`|
|`.`|`Dot`|
|`&`|`Amp`|
|<code>&#124;</code>|`Bar`|
|`@`|`At`|
|`^`|`Hat`|
|`!`|`Bang`|
|`?`|`Qmark`|
|`(`|`LParen`|
|`,`|`Comma`|
|`)`|`RParen`|
|`[`|`LBrack`|
|`]`|`RBrack`|

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="35ba5-136">접두사 및 중 위 연산자</span><span class="sxs-lookup"><span data-stu-id="35ba5-136">Prefix and Infix Operators</span></span>

<span data-ttu-id="35ba5-137">*접두사* 연산자는 하나 이상의 피연산자는 함수와 비슷하게 앞에 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="35ba5-138">*위* 연산자는 두 피연산자 사이 배치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="35ba5-139">전위 연산자와 특정 연산자만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="35ba5-140">일부 연산자는 항상 전위 연산자, 중 위 또는 접두사 수 다른 및 나머지 연산자는 언제나 중 위</span><span class="sxs-lookup"><span data-stu-id="35ba5-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="35ba5-141">`!`를 제외한 `!=`로 시작하는 연산자와 `~` 연산자 또는 `~` 연산자의 반복적인 시퀀스는 항상 전위 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="35ba5-142">연산자 `+`, `-`, `+.`, `-.`를 `&`를 `&&`를 `%`, 및 `%%` 전위 연산자 또는 연산자 중 위 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="35ba5-143">추가 하 여 이러한 연산자의 전위 버전 중 위에서와 구분을 `~` 전위 연산자 정의 될 때 시작 부분에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="35ba5-144">`~` 정의 될 때에 연산자를 사용 하는 경우 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="35ba5-145">예제</span><span class="sxs-lookup"><span data-stu-id="35ba5-145">Example</span></span>

<span data-ttu-id="35ba5-146">다음 코드는 분수 형식을 구현 하는 오버 로드 된 연산자의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="35ba5-147">분수는 분자와 분모 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="35ba5-148">함수 `hcf` 분수를 줄이기 위해 사용 되는 가장 큰 공통 인수를 확인 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="35ba5-149">**출력:**</span><span class="sxs-lookup"><span data-stu-id="35ba5-149">**Output:**</span></span>

```
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="35ba5-150">전역 수준에서 연산자</span><span class="sxs-lookup"><span data-stu-id="35ba5-150">Operators at the Global Level</span></span>

<span data-ttu-id="35ba5-151">또한 전역 수준에서 연산자를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-151">You can also define operators at the global level.</span></span> <span data-ttu-id="35ba5-152">다음 코드는 운영자 정의 `+?`합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="35ba5-153">위 코드의 출력은 `12`합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="35ba5-154">규칙에 대 한 범위 지정 하기 때문에이 방식으로 일반 산술 연산자를 재정의할 수 있습니다 F# 는 새로 정의 된 연산자 보다 우선 기본 제공 연산자를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="35ba5-155">키워드 `inline` 호출 코드에 가장 잘 통합 되는 작은 함수는 전역 연산자를 사용 하 여 자주 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="35ba5-156">또한 making 연산자 함수 인라인을 사용 하면 제네릭 정적으로 확인 된 코드를 생성 하기 위해 정적으로 확인 된 형식 매개 변수를 사용 하 여 작업할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="35ba5-157">자세한 내용은 [인라인 함수](functions/inline-functions.md) 하 고 [정적으로 확인 한 형식 매개](generics/statically-resolved-type-parameters.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="35ba5-157">For more information, see [Inline Functions](functions/inline-functions.md) and [Statically Resolved Type Parameters](generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="35ba5-158">참고자료</span><span class="sxs-lookup"><span data-stu-id="35ba5-158">See also</span></span>

- [<span data-ttu-id="35ba5-159">멤버</span><span class="sxs-lookup"><span data-stu-id="35ba5-159">Members</span></span>](members/index.md)