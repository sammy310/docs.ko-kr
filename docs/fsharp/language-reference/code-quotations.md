---
title: 코드 인용
description: '프로그래밍 방식으로 F # 코드 식을 생성 하 고 사용할 수 있도록 하는 언어 기능인 F # 코드 인용에 대해 알아봅니다.'
ms.date: 08/13/2020
ms.openlocfilehash: 070e127397a5da7d70281d08ef7cafdb9b4f4fe5
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88558337"
---
# <a name="code-quotations"></a><span data-ttu-id="81ade-103">코드 인용</span><span class="sxs-lookup"><span data-stu-id="81ade-103">Code quotations</span></span>

<span data-ttu-id="81ade-104">이 문서에서는 F # 코드 식을 프로그래밍 방식으로 생성 하 고 사용할 수 있도록 하는 언어 기능인 *코드 인용*을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-104">This article describes *code quotations*, a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="81ade-105">이 기능을 사용 하면 F # 코드를 나타내는 추상 구문 트리를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-105">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="81ade-106">그런 다음 응용 프로그램의 필요에 따라 추상 구문 트리를 트래버스 하 고 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-106">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="81ade-107">예를 들어, 트리를 사용 하 여 F # 코드를 생성 하거나 다른 언어로 코드를 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-107">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>

## <a name="quoted-expressions"></a><span data-ttu-id="81ade-108">따옴표 붙은 식</span><span class="sxs-lookup"><span data-stu-id="81ade-108">Quoted Expressions</span></span>

<span data-ttu-id="81ade-109">*따옴표 붙은 식은* 프로그램의 일부로 컴파일되지 않고 f # 식을 나타내는 개체로 컴파일되는 방식으로 구분 되는 코드의 f # 식입니다 (예:</span><span class="sxs-lookup"><span data-stu-id="81ade-109">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="81ade-110">다음 두 가지 방법 중 하나를 사용 하 여 따옴표 붙은 식을 표시할 수 있습니다. 형식 정보를 사용 하거나 형식 정보를 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-110">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="81ade-111">형식 정보를 포함 하려는 경우 기호를 사용 하 여 `<@` `@>` 따옴표 붙은 식을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-111">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="81ade-112">형식 정보가 필요 하지 않은 경우에는 기호와를 사용 `<@@` `@@>` 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-112">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="81ade-113">다음 코드는 형식화 된 및 형식화 되지 않은 따옴표를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-113">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="81ade-114">형식 정보를 포함 하지 않는 경우에는 긴 식 트리를 더 빠르게 트래버스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-114">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="81ade-115">형식화 된 기호로 묶은 식의 결과 형식은입니다 `Expr<'T>` . 여기서 형식 매개 변수는 F # 컴파일러의 형식 유추 알고리즘에 의해 결정 된 식의 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-115">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="81ade-116">형식 정보 없이 코드 따옴표를 사용 하는 경우 따옴표 붙은 식의 형식은 제네릭이 아닌 형식 [Expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html)입니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-116">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span></span> <span data-ttu-id="81ade-117">형식화 된 클래스에 대해 [Raw](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) 속성을 호출 `Expr` 하 여 형식화 되지 않은 개체를 가져올 수 있습니다 `Expr` .</span><span class="sxs-lookup"><span data-stu-id="81ade-117">You can call the [Raw](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr-1.html#Raw) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="81ade-118">`Expr`따옴표로 묶인 식을 사용 하지 않고도 클래스에서 프로그래밍 방식으로 F # 식 개체를 생성할 수 있도록 하는 다양 한 정적 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-118">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="81ade-119">코드 인용에는 전체 식이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-119">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="81ade-120">예를 들어 바인딩의 경우 바인딩 `let` 이름 및 바인딩을 사용 하는 추가 식의 정의가 모두 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-120">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="81ade-121">자세한 구문에서 키워드 뒤에 오는 식입니다 `in` .</span><span class="sxs-lookup"><span data-stu-id="81ade-121">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="81ade-122">모듈의 최상위 수준에서이는 모듈의 다음 식일 뿐 아니라 따옴표 안에 명시적으로 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-122">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="81ade-123">따라서 다음 식은 유효 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-123">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="81ade-124">그러나 다음 식은 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-124">But the following expressions are valid.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="81ade-125">F # 따옴표를 계산 하려면 [f # 따옴표 계산기](https://github.com/fsprojects/FSharp.Quotations.Evaluator)를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-125">To evaluate F# quotations, you must use the [F# Quotation Evaluator](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span></span> <span data-ttu-id="81ade-126">F # 식 개체를 평가 하 고 실행 하는 기능을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-126">It provides support for evaluating and executing F# expression objects.</span></span>

## <a name="expr-type"></a><span data-ttu-id="81ade-127">Expr 형식</span><span class="sxs-lookup"><span data-stu-id="81ade-127">Expr Type</span></span>

<span data-ttu-id="81ade-128">형식의 인스턴스는 `Expr` F # 식을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-128">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="81ade-129">제네릭 및 제네릭이 아닌 `Expr` 형식은 모두 F # 라이브러리 설명서에 설명 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-129">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="81ade-130">자세한 내용은 [Fsharp.core 네임 스페이스](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) 및 [인용구 클래스](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81ade-130">For more information, see [FSharp.Quotations Namespace](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations.html) and [Quotations.Expr Class](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-fsharpexpr.html).</span></span>

## <a name="splicing-operators"></a><span data-ttu-id="81ade-131">스플라이스 연산자</span><span class="sxs-lookup"><span data-stu-id="81ade-131">Splicing Operators</span></span>

<span data-ttu-id="81ade-132">스플라이스를 사용 하면 프로그래밍 방식으로 또는 다른 코드 인용에서 만든 식과 리터럴 코드 따옴표를 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-132">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="81ade-133">`%`및 `%%` 연산자를 사용 하 여 코드 인용에 F # 식 개체를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-133">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="81ade-134">연산자를 사용 하 여 형식화 `%` 된 식 개체를 형식화 된 따옴표로 삽입 합니다. 연산자를 사용 하 여 형식화 되지 `%%` 않은 식 개체를 형식화 되지 않은 따옴표로 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-134">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="81ade-135">두 연산자는 단항 전위 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-135">Both operators are unary prefix operators.</span></span> <span data-ttu-id="81ade-136">따라서 `expr` 가 형식의 형식화 되지 않은 식인 경우에는 `Expr` 다음 코드를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-136">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="81ade-137">`expr`가 형식의 형식화 된 인용 인 경우 `Expr<int>` 다음 코드는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-137">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="81ade-138">예제</span><span class="sxs-lookup"><span data-stu-id="81ade-138">Example</span></span>

### <a name="description"></a><span data-ttu-id="81ade-139">Description</span><span class="sxs-lookup"><span data-stu-id="81ade-139">Description</span></span>

<span data-ttu-id="81ade-140">다음 예제에서는 코드 인용을 사용 하 여 F # 코드를 식 개체에 배치한 다음 식을 나타내는 F # 코드를 인쇄 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-140">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="81ade-141">`println` `print` F # 식 개체 (형식 `Expr` )를 친숙 한 형식으로 표시 하는 재귀 함수를 포함 하는 함수가 정의 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-141">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="81ade-142">[Fsharp.core](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) 및 [fsharp.core](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) 모듈에는 식 개체를 분석 하는 데 사용할 수 있는 여러 가지 활성 패턴이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-142">There are several active patterns in the [FSharp.Quotations.Patterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-patternsmodule.html) and [FSharp.Quotations.DerivedPatterns](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="81ade-143">이 예제에는 F # 식에 나타날 수 있는 모든 패턴이 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-143">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="81ade-144">인식할 수 없는 모든 패턴은 와일드 카드 패턴 ()에 대 한 일치를 트리거하고 `_` 메서드를 사용 하 여 렌더링 됩니다 .이 메서드를 사용 하면 해당 `ToString` `Expr` 형식에서 일치 식에 추가할 활성 패턴을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-144">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>

### <a name="code"></a><span data-ttu-id="81ade-145">코드</span><span class="sxs-lookup"><span data-stu-id="81ade-145">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a><span data-ttu-id="81ade-146">출력</span><span class="sxs-lookup"><span data-stu-id="81ade-146">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="81ade-147">예제</span><span class="sxs-lookup"><span data-stu-id="81ade-147">Example</span></span>

### <a name="description"></a><span data-ttu-id="81ade-148">Description</span><span class="sxs-lookup"><span data-stu-id="81ade-148">Description</span></span>

<span data-ttu-id="81ade-149">[Exprshape.rebuildshapecombination 모듈](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) 의 세 가지 활성 패턴을 사용 하 여 활성 패턴이 적을수록 식 트리를 트래버스할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-149">You can also use the three active patterns in the [ExprShape module](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="81ade-150">이러한 활성 패턴은 트리를 트래버스 하려고 하지만 대부분의 노드에 모든 정보가 필요 하지 않은 경우에 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-150">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="81ade-151">이러한 패턴을 사용 하는 경우 모든 F # 식은 `ShapeVar` 식이 변수인 경우, 식이 `ShapeLambda` 람다 식인 경우 또는 `ShapeCombination` 식이 다른 것 인 경우에는 다음 세 가지 패턴 중 하 나와 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-151">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="81ade-152">이전 코드 예제와 같이 활성 패턴을 사용 하 여 식 트리를 트래버스하는 경우에는 더 많은 패턴을 사용 하 여 가능한 모든 F # 식 형식을 처리 해야 하며 코드는 더 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-152">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="81ade-153">자세한 내용은 [exprshape.rebuildshapecombination. ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20))을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="81ade-153">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-exprshapemodule.html#(%20|ShapeVar|ShapeLambda|ShapeCombination|%20)).</span></span>

<span data-ttu-id="81ade-154">다음 코드 예제는 보다 복잡 한 순회를 위한 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-154">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="81ade-155">이 코드에서는 함수 호출를 포함 하는 식에 대해 식 트리가 생성 됩니다 `add` .</span><span class="sxs-lookup"><span data-stu-id="81ade-155">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="81ade-156">[SpecificCall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) 활성 패턴은 식 트리에서에 대 한 호출을 검색 하는 데 사용 됩니다 `add` .</span><span class="sxs-lookup"><span data-stu-id="81ade-156">The [SpecificCall](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-quotations-derivedpatternsmodule.html#(%20|SpecificCall|_|%20)) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="81ade-157">이 활성 패턴은 호출의 인수를 값에 할당 합니다 `exprList` .</span><span class="sxs-lookup"><span data-stu-id="81ade-157">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="81ade-158">이 경우에는 두 개만 있으므로이를 끌어올 수 있으며 함수는 인수에서 재귀적으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-158">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="81ade-159">결과는 `mul` splice 연산자 ()를 사용 하 여에 대 한 호출을 나타내는 코드 따옴표로 삽입 됩니다 `%%` .</span><span class="sxs-lookup"><span data-stu-id="81ade-159">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="81ade-160">`println`이전 예제의 함수는 결과를 표시 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="81ade-160">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="81ade-161">다른 활성 패턴 분기의 코드는 동일한 식 트리를 다시 생성 하므로 결과 식의 변경 내용만에서로 변경 됩니다 `add` `mul` .</span><span class="sxs-lookup"><span data-stu-id="81ade-161">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>

### <a name="code"></a><span data-ttu-id="81ade-162">코드</span><span class="sxs-lookup"><span data-stu-id="81ade-162">Code</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a><span data-ttu-id="81ade-163">출력</span><span class="sxs-lookup"><span data-stu-id="81ade-163">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="81ade-164">참고 항목</span><span class="sxs-lookup"><span data-stu-id="81ade-164">See also</span></span>

- [<span data-ttu-id="81ade-165">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="81ade-165">F# Language Reference</span></span>](index.md)
