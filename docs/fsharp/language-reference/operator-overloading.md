---
title: 연산자 오버로드
description: 클래스 또는 레코드 형식과의 F#전역 수준에서 산술 연산자를 오버 로드 하는 방법에 대해 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: d902a06193481ed87131b3336cd8a2ff54b811b4
ms.sourcegitcommit: 56f1d1203d0075a461a10a301459d3aa452f4f47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2019
ms.locfileid: "71216839"
---
# <a name="operator-overloading"></a><span data-ttu-id="de8c8-103">연산자 오버로드</span><span class="sxs-lookup"><span data-stu-id="de8c8-103">Operator Overloading</span></span>

<span data-ttu-id="de8c8-104">이 항목에서는 클래스 또는 레코드 형식과 전역 수준에서 산술 연산자를 오버 로드 하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-104">This topic describes how to overload arithmetic operators in a class or record type, and at the global level.</span></span>

## <a name="syntax"></a><span data-ttu-id="de8c8-105">구문</span><span class="sxs-lookup"><span data-stu-id="de8c8-105">Syntax</span></span>

```fsharp
// Overloading an operator as a class or record member.
static member (operator-symbols) (parameter-list) =
    method-body
// Overloading an operator at the global level
let [inline] (operator-symbols) parameter-list = function-body
```

## <a name="remarks"></a><span data-ttu-id="de8c8-106">설명</span><span class="sxs-lookup"><span data-stu-id="de8c8-106">Remarks</span></span>

<span data-ttu-id="de8c8-107">위의 구문에서 *연산자-기호* 는 `+` `-` `*` `/`,,,, 등중하나입니다.`=`</span><span class="sxs-lookup"><span data-stu-id="de8c8-107">In the previous syntax, the *operator-symbol* is one of `+`, `-`, `*`, `/`, `=`, and so on.</span></span> <span data-ttu-id="de8c8-108">*매개 변수 목록* 은 해당 연산자에 대 한 일반적인 구문에서 피연산자를 표시 하는 순서 대로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-108">The *parameter-list* specifies the operands in the order they appear in the usual syntax for that operator.</span></span> <span data-ttu-id="de8c8-109">*메서드 본문* 은 결과 값을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-109">The *method-body* constructs the resulting value.</span></span>

<span data-ttu-id="de8c8-110">연산자의 연산자 오버 로드는 정적 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-110">Operator overloads for operators must be static.</span></span> <span data-ttu-id="de8c8-111">`+` `~`및 와`-`같은 단항 연산자에 대 한 연산자 오버 로드는 다음과 같이 연산자가 이항 연산자가 아니라 단항 연산자 임을 나타내기 위해 *연산자-기호* 에 물결표 ()를 사용 해야 합니다. 선언한.</span><span class="sxs-lookup"><span data-stu-id="de8c8-111">Operator overloads for unary operators, such as `+` and `-`, must use a tilde (`~`) in the *operator-symbol* to indicate that the operator is a unary operator and not a binary operator, as shown in the following declaration.</span></span>

```fsharp
static member (~-) (v : Vector)
```

<span data-ttu-id="de8c8-112">다음 코드에서는 연산자가 두 개뿐인 벡터 클래스를 보여 줍니다. 그 중 하나는 단항 빼기 연산자이고 다른 하나는 스칼라 값을 곱하기 위한 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-112">The following code illustrates a vector class that has just two operators, one for unary minus and one for multiplication by a scalar.</span></span> <span data-ttu-id="de8c8-113">이 예제에서는 벡터와 스칼라가 표시 되는 순서에 관계 없이 연산자가 작동 해야 하므로 스칼라 곱셈에 대 한 두 개의 오버 로드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-113">In the example, two overloads for scalar multiplication are needed because the operator must work regardless of the order in which the vector and scalar appear.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4001.fs)]

## <a name="creating-new-operators"></a><span data-ttu-id="de8c8-114">새 운영자 만들기</span><span class="sxs-lookup"><span data-stu-id="de8c8-114">Creating New Operators</span></span>

<span data-ttu-id="de8c8-115">모든 표준 연산자를 오버 로드할 수 있지만 특정 문자의 시퀀스에서 새 연산자를 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-115">You can overload all the standard operators, but you can also create new operators out of sequences of certain characters.</span></span> <span data-ttu-id="de8c8-116">허용 되는 연산자 `!`문자 `%`는 `&`, `*` `+` ,`-`,, ,,`.`,,,,,입니다. `/` `<` `=` `>` `?`,,, 및`~`가 있습니다. `@` `^` `|`</span><span class="sxs-lookup"><span data-stu-id="de8c8-116">Allowed operator characters are `!`, `%`, `&`, `*`, `+`, `-`, `.`, `/`, `<`, `=`, `>`, `?`, `@`, `^`, `|`, and `~`.</span></span> <span data-ttu-id="de8c8-117">문자 `~` 는 연산자 단항을 만드는 특별 한 의미를 가지 며 연산자 문자 시퀀스의 일부가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-117">The `~` character has the special meaning of making an operator unary, and is not part of the operator character sequence.</span></span> <span data-ttu-id="de8c8-118">모든 연산자를 단항로 설정할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-118">Not all operators can be made unary.</span></span>

<span data-ttu-id="de8c8-119">사용 하는 정확한 문자 시퀀스에 따라 연산자는 특정 우선 순위와 결합성을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-119">Depending on the exact character sequence you use, your operator will have a certain precedence and associativity.</span></span> <span data-ttu-id="de8c8-120">결합성은 왼쪽에서 오른쪽 또는 오른쪽에서 왼쪽으로 지정할 수 있으며, 동일한 수준의 우선 순위의 연산자가 괄호 없이 순서 대로 나타날 때마다 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-120">Associativity can be either left to right or right to left and is used whenever operators of the same level of precedence appear in sequence without parentheses.</span></span>

<span data-ttu-id="de8c8-121">연산자 문자 `.` 는 우선 순위에 영향을 주지 않으므로 예를 들어 일반 곱하기와 우선 순위와 결합성이 같은 고유한 곱셈 버전을 정의 하려는 경우와 같은연산자를만들수있습니다 `.*`.</span><span class="sxs-lookup"><span data-stu-id="de8c8-121">The operator character `.` does not affect precedence, so that, for example, if you want to define your own version of multiplication that has the same precedence and associativity as ordinary multiplication, you could create operators such as `.*`.</span></span>

<span data-ttu-id="de8c8-122">연산자 `?` 와 `?<-` 만 시작할`?`수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-122">Only the operators `?` and `?<-` may start with `?`.</span></span>

<span data-ttu-id="de8c8-123">에서 F# 모든 연산자의 우선 순위를 보여 주는 테이블은 [기호 및 연산자 참조](./symbol-and-operator-reference/index.md)에서 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-123">A table that shows the precedence of all operators in F# can be found in [Symbol and Operator Reference](./symbol-and-operator-reference/index.md).</span></span>

## <a name="overloaded-operator-names"></a><span data-ttu-id="de8c8-124">오버 로드 된 연산자 이름</span><span class="sxs-lookup"><span data-stu-id="de8c8-124">Overloaded Operator Names</span></span>

<span data-ttu-id="de8c8-125">F# 컴파일러가 연산자 식을 컴파일하는 경우 해당 연산자에 대해 컴파일러에서 생성 된 이름이 있는 메서드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-125">When the F# compiler compiles an operator expression, it generates a method that has a compiler-generated name for that operator.</span></span> <span data-ttu-id="de8c8-126">메서드의 MSIL (Microsoft 중간 언어)에 표시 되는 이름이 며 리플렉션 및 IntelliSense 에서도이 이름이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-126">This is the name that appears in the Microsoft intermediate language (MSIL) for the method, and also in reflection and IntelliSense.</span></span> <span data-ttu-id="de8c8-127">일반적으로는 이러한 이름을 코드에서 F# 사용할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-127">You do not normally need to use these names in F# code.</span></span>

<span data-ttu-id="de8c8-128">다음 표에서는 표준 연산자와 해당 하는 생성 된 이름을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-128">The following table shows the standard operators and their corresponding generated names.</span></span>

|<span data-ttu-id="de8c8-129">연산자</span><span class="sxs-lookup"><span data-stu-id="de8c8-129">Operator</span></span>|<span data-ttu-id="de8c8-130">생성 된 이름</span><span class="sxs-lookup"><span data-stu-id="de8c8-130">Generated name</span></span>|
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

<span data-ttu-id="de8c8-131">여기에 나열 되지 않은 연산자 문자의 다른 조합은 연산자로 사용할 수 있으며 다음 표의 개별 문자에 대 한 이름을 연결 하 여 구성 된 이름을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-131">Other combinations of operator characters that are not listed here can be used as operators and have names that are made up by concatenating names for the individual characters from the following table.</span></span> <span data-ttu-id="de8c8-132">예: +!</span><span class="sxs-lookup"><span data-stu-id="de8c8-132">For example, +!</span></span> <span data-ttu-id="de8c8-133">가 `op_PlusBang`됩니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-133">becomes `op_PlusBang`.</span></span>

|<span data-ttu-id="de8c8-134">연산자 문자</span><span class="sxs-lookup"><span data-stu-id="de8c8-134">Operator character</span></span>|<span data-ttu-id="de8c8-135">name</span><span class="sxs-lookup"><span data-stu-id="de8c8-135">Name</span></span>|
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

## <a name="prefix-and-infix-operators"></a><span data-ttu-id="de8c8-136">전위 및 중 위 연산자</span><span class="sxs-lookup"><span data-stu-id="de8c8-136">Prefix and Infix Operators</span></span>

<span data-ttu-id="de8c8-137">*전위* 연산자는 함수와 매우 유사 하 게 피연산자 또는 피연산자 앞에 배치 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-137">*Prefix* operators are expected to be placed in front of an operand or operands, much like a function.</span></span> <span data-ttu-id="de8c8-138">중 *위* 연산자는 두 피연산자 사이에 배치 될 것으로 예상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-138">*Infix* operators are expected to be placed between the two operands.</span></span>

<span data-ttu-id="de8c8-139">특정 연산자만 전위 연산자로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-139">Only certain operators can be used as prefix operators.</span></span> <span data-ttu-id="de8c8-140">일부 연산자는 항상 전위 연산자이 고, 다른 연산자는 중 위 또는 접두사가 될 수 있으며 나머지 연산자는 항상 중 위 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-140">Some operators are always prefix operators, others can be infix or prefix, and the rest are always infix operators.</span></span> <span data-ttu-id="de8c8-141">`!`를 제외한 `!=`로 시작하는 연산자와 `~` 연산자 또는 `~` 연산자의 반복적인 시퀀스는 항상 전위 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-141">Operators that begin with `!`, except `!=`, and the operator `~`, or repeated sequences of`~`, are always prefix operators.</span></span> <span data-ttu-id="de8c8-142">`+`연산자 ,`&`,, ,,`%`, 및`%%` 는 전위 연산자 또는 중 위 연산자 일 수 있습니다. `-.` `-` `+.` `&&`</span><span class="sxs-lookup"><span data-stu-id="de8c8-142">The operators `+`, `-`, `+.`, `-.`, `&`, `&&`, `%`, and `%%` can be prefix operators or infix operators.</span></span> <span data-ttu-id="de8c8-143">접두사 연산자가 정의 될 때 접두사 연산자의 시작 부분에를 `~` 추가 하 여 이러한 연산자의 전위 버전을 중 위 버전과 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-143">You distinguish the prefix version of these operators from the infix version by adding a `~` at the beginning of a prefix operator when it is defined.</span></span> <span data-ttu-id="de8c8-144">연산자 `~` 를 사용 하는 경우 (정의 된 경우에만)는 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-144">The `~` is not used when you use the operator, only when it is defined.</span></span>

## <a name="example"></a><span data-ttu-id="de8c8-145">예제</span><span class="sxs-lookup"><span data-stu-id="de8c8-145">Example</span></span>

<span data-ttu-id="de8c8-146">다음 코드에서는 연산자 오버 로드를 사용 하 여 분수 형식을 구현 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-146">The following code illustrates the use of operator overloading to implement a fraction type.</span></span> <span data-ttu-id="de8c8-147">분수는 분자와 분모로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-147">A fraction is represented by a numerator and a denominator.</span></span> <span data-ttu-id="de8c8-148">함수 `hcf` 는 분수를 줄이는 데 사용 되는 가장 높은 공통 요소를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-148">The function `hcf` is used to determine the highest common factor, which is used to reduce fractions.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4002.fs)]

<span data-ttu-id="de8c8-149">**출력:**</span><span class="sxs-lookup"><span data-stu-id="de8c8-149">**Output:**</span></span>

```console
3/4 + 1/2 = 5/4
3/4 - 1/2 = 1/4
3/4 * 1/2 = 3/8
3/4 / 1/2 = 3/2
3/4 + 1 = 7/4
```

## <a name="operators-at-the-global-level"></a><span data-ttu-id="de8c8-150">전역 수준의 연산자</span><span class="sxs-lookup"><span data-stu-id="de8c8-150">Operators at the Global Level</span></span>

<span data-ttu-id="de8c8-151">전역 수준에서 연산자를 정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-151">You can also define operators at the global level.</span></span> <span data-ttu-id="de8c8-152">다음 코드에서는 연산자 `+?`를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-152">The following code defines an operator `+?`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4003.fs)]

<span data-ttu-id="de8c8-153">위의 코드 `12`의 출력은입니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-153">The output of the above code is `12`.</span></span>

<span data-ttu-id="de8c8-154">새로 정의 된 연산자에 대 한 F# 범위 지정 규칙이 기본 제공 연산자 보다 우선적으로 적용 되기 때문에 이러한 방식으로 정규 산술 연산자를 다시 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-154">You can redefine the regular arithmetic operators in this manner because the scoping rules for F# dictate that newly defined operators take precedence over the built-in operators.</span></span>

<span data-ttu-id="de8c8-155">키워드 `inline` 는 일반적으로 호출 코드에 가장 잘 통합 된 작은 함수인 전역 연산자와 함께 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-155">The keyword `inline` is often used with global operators, which are often small functions that are best integrated into the calling code.</span></span> <span data-ttu-id="de8c8-156">또한 연산자 함수를 인라인으로 만들면 정적으로 확인 된 형식 매개 변수와 함께 작동 하 여 정적으로 확인 된 제네릭 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de8c8-156">Making operator functions inline also enables them to work with statically resolved type parameters to produce statically resolved generic code.</span></span> <span data-ttu-id="de8c8-157">자세한 내용은 [인라인 함수](./functions/inline-functions.md) 및 [정적으로 확인 된 형식 매개 변수](./generics/statically-resolved-type-parameters.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="de8c8-157">For more information, see [Inline Functions](./functions/inline-functions.md) and [Statically Resolved Type Parameters](./generics/statically-resolved-type-parameters.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="de8c8-158">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de8c8-158">See also</span></span>

- [<span data-ttu-id="de8c8-159">멤버</span><span class="sxs-lookup"><span data-stu-id="de8c8-159">Members</span></span>](./members/index.md)
