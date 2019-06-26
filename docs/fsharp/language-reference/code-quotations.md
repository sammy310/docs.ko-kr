---
title: 코드 인용
description: 에 대해 알아봅니다 F# 코드 인용을 생성 하 여 작업할 수 있는 언어 기능 F# 식에 프로그래밍 방식으로 코드입니다.
ms.date: 05/16/2016
ms.openlocfilehash: 30fd5b575fa59d78c3e70c1a94cd921a6a655ace
ms.sourcegitcommit: bab17fd81bab7886449217356084bf4881d6e7c8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2019
ms.locfileid: "67402124"
---
# <a name="code-quotations"></a><span data-ttu-id="6916e-103">코드 인용</span><span class="sxs-lookup"><span data-stu-id="6916e-103">Code Quotations</span></span>

> [!NOTE]
> <span data-ttu-id="6916e-104">API 참조 링크를 통해 MSDN으로 이동됩니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-104">The API reference link will take you to MSDN.</span></span>  <span data-ttu-id="6916e-105">docs.microsoft.com API 참조가 완전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-105">The docs.microsoft.com API reference is not complete.</span></span>

<span data-ttu-id="6916e-106">이 항목에 설명 합니다 *코드 인용*를 생성 하 여 작업할 수 있도록 언어 기능을 F# 식을 프로그래밍 방식으로 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-106">This topic describes *code quotations*, a language feature that enables you to generate and work with F# code expressions programmatically.</span></span> <span data-ttu-id="6916e-107">이 기능은 사용 하는 추상 구문 트리를 생성할 수 있습니다. F# 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-107">This feature lets you generate an abstract syntax tree that represents F# code.</span></span> <span data-ttu-id="6916e-108">추상 구문 트리 트래버스 고 응용 프로그램의 필요에 따라 처리 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-108">The abstract syntax tree can then be traversed and processed according to the needs of your application.</span></span> <span data-ttu-id="6916e-109">예를 들어, 생성 하는 트리를 사용할 수 있습니다 F# 코드 또는 다른 언어로 코드를 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-109">For example, you can use the tree to generate F# code or generate code in some other language.</span></span>

## <a name="quoted-expressions"></a><span data-ttu-id="6916e-110">따옴표 붙은 식</span><span class="sxs-lookup"><span data-stu-id="6916e-110">Quoted Expressions</span></span>

<span data-ttu-id="6916e-111">*인용 된 식* 됩니다는 F# 프로그램의 일부로 컴파일되지 않은 방식으로 구분 된 하지만 대신 나타내는 개체로 컴파일된 코드에서 식은 F# 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-111">A *quoted expression* is an F# expression in your code that is delimited in such a way that it is not compiled as part of your program, but instead is compiled into an object that represents an F# expression.</span></span> <span data-ttu-id="6916e-112">따옴표 붙은 식에서 두 가지 방법 중 하나를 표시할 수 있습니다: 형식 정보를 사용 하 여 만들거나 형식 정보가 없는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-112">You can mark a quoted expression in one of two ways: either with type information or without type information.</span></span> <span data-ttu-id="6916e-113">기호를 사용 하는 형식 정보를 포함 하려는 경우 `<@` 및 `@>` 인용된 식을 구분 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-113">If you want to include type information, you use the symbols `<@` and `@>` to delimit the quoted expression.</span></span> <span data-ttu-id="6916e-114">기호를 사용 하는 형식 정보를 필요 하지 않은 경우 `<@@` 고 `@@>`입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-114">If you do not need type information, you use the symbols `<@@` and `@@>`.</span></span> <span data-ttu-id="6916e-115">다음 코드는 형식화 및 형식화 되지 않은 따옴표를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-115">The following code shows typed and untyped quotations.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet501.fs)]

<span data-ttu-id="6916e-116">큰 식 트리를 트래버스하 빠릅니다 형식 정보가 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-116">Traversing a large expression tree is faster if you do not include type information.</span></span> <span data-ttu-id="6916e-117">형식화 된 기호를 사용 하 여 따옴표 붙은 식의 결과 형식은 `Expr<'T>`, 형식 매개 변수를 기준으로 식의 형식에는 F# 컴파일러의 형식 유추 알고리즘입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-117">The resulting type of an expression quoted with the typed symbols is `Expr<'T>`, where the type parameter has the type of the expression as determined by the F# compiler's type inference algorithm.</span></span> <span data-ttu-id="6916e-118">따옴표 붙은 식의 형식이 제네릭이 아닌 형식의 형식 정보 없이 코드 인용을 사용 하면 [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65)합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-118">When you use code quotations without type information, the type of the quoted expression is the non-generic type [Expr](https://msdn.microsoft.com/library/ed6a2caf-69d4-45c2-ab97-e9b3be9bce65).</span></span> <span data-ttu-id="6916e-119">호출할 수 있습니다 합니다 [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) 형식화 된 속성 `Expr` 클래스는 형식화 되지 않은 가져오려고 `Expr` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-119">You can call the [Raw](https://msdn.microsoft.com/library/47fb94f1-e77f-4c68-aabc-2b0ba40d59c2) property on the typed `Expr` class to obtain the untyped `Expr` object.</span></span>

<span data-ttu-id="6916e-120">다양 한 정적 메서드를 생성할 수 있도록 F# 식에 프로그래밍 방식으로 개체를 `Expr` 클래스를 사용 하지 않고 따옴표 붙은 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-120">There are a variety of static methods that allow you to generate F# expression objects programmatically in the `Expr` class without using quoted expressions.</span></span>

<span data-ttu-id="6916e-121">참고 코드 인용에는 전체 식이 포함 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-121">Note that a code quotation must include a complete expression.</span></span> <span data-ttu-id="6916e-122">에 대 한는 `let` 바인딩, 예를 들어 해야 바인딩된 이름 및 바인딩을 사용 하는 추가 식을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-122">For a `let` binding, for example, you need both the definition of the bound name and an additional expression that uses the binding.</span></span> <span data-ttu-id="6916e-123">자세한 구문에서이 뒤에 오는 식의 `in` 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-123">In verbose syntax, this is an expression that follows the `in` keyword.</span></span> <span data-ttu-id="6916e-124">모듈의 최상위 수준에서 모듈에서 다음 식은 바로 이것이 이지만 인용에 명시적으로 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-124">At the top-level in a module, this is just the next expression in the module, but in a quotation, it is explicitly required.</span></span>

<span data-ttu-id="6916e-125">따라서 다음 식은 올바르지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-125">Therefore, the following expression is not valid.</span></span>

```fsharp
// Not valid:
// <@ let f x = x + 1 @>
```

<span data-ttu-id="6916e-126">하지만 다음 식은 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-126">But the following expressions are valid.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet502.fs)]

<span data-ttu-id="6916e-127">평가 F# 를 사용 해야 합니다를 묶어 합니다 [ F# 인용 계산기](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span><span class="sxs-lookup"><span data-stu-id="6916e-127">To evaluate F# quotations, you must use the [F# Quotation Evaluator](https://github.com/fsprojects/FSharp.Quotations.Evaluator).</span></span> <span data-ttu-id="6916e-128">평가 및 실행에 대 한 지원을 제공 F# 식 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-128">It provides support for evaluating and executing F# expression objects.</span></span>

## <a name="expr-type"></a><span data-ttu-id="6916e-129">Expr 형식</span><span class="sxs-lookup"><span data-stu-id="6916e-129">Expr Type</span></span>

<span data-ttu-id="6916e-130">인스턴스를 `Expr` 나타내는 입력는 F# 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-130">An instance of the `Expr` type represents an F# expression.</span></span> <span data-ttu-id="6916e-131">제네릭 및 제네릭이 아닌 `Expr` 형식에 설명 된는 F# 라이브러리 설명서를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-131">Both the generic and the non-generic `Expr` types are documented in the F# library documentation.</span></span> <span data-ttu-id="6916e-132">자세한 내용은 [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) 하 고 [Quotations.Expr 클래스](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-132">For more information, see [Microsoft.FSharp.Quotations Namespace](https://msdn.microsoft.com/visualfsharpdocs/conceptual/microsoft.fsharp.quotations-namespace-%5bfsharp%5d) and [Quotations.Expr Class](https://msdn.microsoft.com/visualfsharpdocs/conceptual/quotations.expr-class-%5bfsharp%5d).</span></span>

## <a name="splicing-operators"></a><span data-ttu-id="6916e-133">결합 연산자</span><span class="sxs-lookup"><span data-stu-id="6916e-133">Splicing Operators</span></span>

<span data-ttu-id="6916e-134">스플라이스를 사용 하면 프로그래밍 방식으로 또는 다른 코드 인용에 만든 식 사용 하 여 리터럴 코드 인용을 결합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-134">Splicing enables you to combine literal code quotations with expressions that you have created programmatically or from another code quotation.</span></span> <span data-ttu-id="6916e-135">`%` 하 고 `%%` 연산자를 사용 하면 추가할 수는 F# 코드 인용에 식 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-135">The `%` and `%%` operators enable you to add an F# expression object into a code quotation.</span></span> <span data-ttu-id="6916e-136">사용할 합니다 `%` 형식의 식 개체를 형식화 된 따옴표로 삽입 연산자를 사용 하 여는 `%%` 는 형식화 되지 않은 따옴표에 형식화 되지 않은 식 개체를 삽입 하는 연산자.</span><span class="sxs-lookup"><span data-stu-id="6916e-136">You use the `%` operator to insert a typed expression object into a typed quotation; you use the `%%` operator to insert an untyped expression object into an untyped quotation.</span></span> <span data-ttu-id="6916e-137">두 연산자는 단항 전위 연산자입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-137">Both operators are unary prefix operators.</span></span> <span data-ttu-id="6916e-138">따라서 경우 `expr` 형식의 형식화 되지 않은 식 `Expr`, 다음 코드는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-138">Thus if `expr` is an untyped expression of type `Expr`, the following code is valid.</span></span>

```fsharp
<@@ 1 + %%expr @@>
```

<span data-ttu-id="6916e-139">경우에 `expr` 형식의 형식화 된 견적 `Expr<int>`, 다음 코드는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-139">And if `expr` is a typed quotation of type `Expr<int>`, the following code is valid.</span></span>

```fsharp
<@ 1 + %expr @>
```

## <a name="example"></a><span data-ttu-id="6916e-140">예제</span><span class="sxs-lookup"><span data-stu-id="6916e-140">Example</span></span>

### <a name="description"></a><span data-ttu-id="6916e-141">설명</span><span class="sxs-lookup"><span data-stu-id="6916e-141">Description</span></span>

<span data-ttu-id="6916e-142">다음 예제에서는 적용할 코드 인용의 사용을 보여 줍니다. F# 코드를 expression 개체를 한 다음 인쇄를 F# expression을 나타내는 코드입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-142">The following example illustrates the use of code quotations to put F# code into an expression object and then print the F# code that represents the expression.</span></span> <span data-ttu-id="6916e-143">함수 `println` 정의 된 재귀 함수를 포함 하는 `print` 표시 하는 F# expression 개체 (형식의 `Expr`) 친숙 한 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-143">A function `println` is defined that contains a recursive function `print` that displays an F# expression object (of type `Expr`) in a friendly format.</span></span> <span data-ttu-id="6916e-144">여러 활성 패턴은는 [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) 하 고 [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) 식 개체를 분석 하는 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-144">There are several active patterns in the [Microsoft.FSharp.Quotations.Patterns](https://msdn.microsoft.com/library/093944a9-c752-403a-8983-5fcd5dbf92a4) and [Microsoft.FSharp.Quotations.DerivedPatterns](https://msdn.microsoft.com/library/d2434a6e-ae7b-4f3d-b567-c162938bc9cd) modules that can be used to analyze expression objects.</span></span> <span data-ttu-id="6916e-145">이 예제에 표시 될 수 있는 모든 패턴을 다루지 않습니다는 F# 식입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-145">This example does not include all the possible patterns that might appear in an F# expression.</span></span> <span data-ttu-id="6916e-146">패턴 와일드 카드 패턴 일치를 트리거 인식 되지 않은 (`_`) 하 고 사용 하 여 렌더링 되는 `ToString` 메서드는에 `Expr` 입력을 일치 식에 추가할 활성 패턴을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-146">Any unrecognized pattern triggers a match to the wildcard pattern (`_`) and is rendered by using the `ToString` method, which, on the `Expr` type, lets you know the active pattern to add to your match expression.</span></span>

### <a name="code"></a><span data-ttu-id="6916e-147">코드</span><span class="sxs-lookup"><span data-stu-id="6916e-147">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet601.fs)]

### <a name="output"></a><span data-ttu-id="6916e-148">출력</span><span class="sxs-lookup"><span data-stu-id="6916e-148">Output</span></span>

```fsharp
fun (x:System.Int32) -> x + 1
a + 1
let f = fun (x:System.Int32) -> x + 10 in f 10
```

## <a name="example"></a><span data-ttu-id="6916e-149">예제</span><span class="sxs-lookup"><span data-stu-id="6916e-149">Example</span></span>

### <a name="description"></a><span data-ttu-id="6916e-150">설명</span><span class="sxs-lookup"><span data-stu-id="6916e-150">Description</span></span>

<span data-ttu-id="6916e-151">세 가지 활성 패턴을 사용할 수도 있습니다는 [ExprShape 모듈](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) 적은 활성 패턴을 사용 하 여 식 트리.</span><span class="sxs-lookup"><span data-stu-id="6916e-151">You can also use the three active patterns in the [ExprShape module](https://msdn.microsoft.com/library/7685150e-2432-4d39-9338-57292eff18de) to traverse expression trees with fewer active patterns.</span></span> <span data-ttu-id="6916e-152">이러한 활성 패턴 트리 트래버스 하려고 하지만 노드의 대부분에서 모든 정보를 수행 해야 하는 경우 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-152">These active patterns can be useful when you want to traverse a tree but you do not need all the information in most of the nodes.</span></span> <span data-ttu-id="6916e-153">사용 하는 경우 이러한 패턴을 모든 F# 식의 다음 세 가지 패턴 중 하 나와 일치: `ShapeVar` 식이 변수에 `ShapeLambda` 식이 람다 식 또는 `ShapeCombination` 식이 다른 경우.</span><span class="sxs-lookup"><span data-stu-id="6916e-153">When you use these patterns, any F# expression matches one of the following three patterns: `ShapeVar` if the expression is a variable, `ShapeLambda` if the expression is a lambda expression, or `ShapeCombination` if the expression is anything else.</span></span> <span data-ttu-id="6916e-154">더 많은 패턴을 사용 하 여 모든 가능한 처리 해야 하는 이전 코드 예제와 같이 활성 패턴을 사용 하 여 식 트리를 이동 하는 경우 F# 식 형식 및 코드는 더 복잡 한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-154">If you traverse an expression tree by using the active patterns as in the previous code example, you have to use many more patterns to handle all possible F# expression types, and your code will be more complex.</span></span> <span data-ttu-id="6916e-155">자세한 내용은 [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination 활성 패턴](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d)합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-155">For more information, see [ExprShape.ShapeVar&#124;ShapeLambda&#124;ShapeCombination Active Pattern](https://msdn.microsoft.com/visualfsharpdocs/conceptual/exprshape.shapevarhshapelambdahshapecombination-active-pattern-%5bfsharp%5d).</span></span>

<span data-ttu-id="6916e-156">다음 코드 예제에서는 보다 복잡 한 순회에 대 한 기준으로 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-156">The following code example can be used as a basis for more complex traversals.</span></span> <span data-ttu-id="6916e-157">이 코드에서는 함수 호출을 포함 하는 식에 대 한 식 트리로 만들어집니다 `add`합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-157">In this code, an expression tree is created for an expression that involves a function call, `add`.</span></span> <span data-ttu-id="6916e-158">합니다 [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) 활성 패턴에 대 한 호출과 검색 하는 `add` 식 트리에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-158">The [SpecificCall](https://msdn.microsoft.com/library/05a77b21-20fe-4b9a-8e07-aa999538198d) active pattern is used to detect any call to `add` in the expression tree.</span></span> <span data-ttu-id="6916e-159">이 활성 패턴에 대 한 호출의 인수를 할당 합니다 `exprList` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-159">This active pattern assigns the arguments of the call to the `exprList` value.</span></span> <span data-ttu-id="6916e-160">이 경우 두 가지 유형만 있습니다를 끌어내기이 고 함수는 인수에 재귀적으로 호출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-160">In this case, there are only two, so these are pulled out and the function is called recursively on the arguments.</span></span> <span data-ttu-id="6916e-161">결과에 대 한 호출을 나타내는 코드 인용에 삽입 됩니다 `mul` 결합 연산자를 사용 하 여 (`%%`).</span><span class="sxs-lookup"><span data-stu-id="6916e-161">The results are inserted into a code quotation that represents a call to `mul` by using the splice operator (`%%`).</span></span> <span data-ttu-id="6916e-162">`println` 이전 예제의 함수 결과 표시 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-162">The `println` function from the previous example is used to display the results.</span></span>

<span data-ttu-id="6916e-163">다른 활성 패턴 분기의 코드에 동일한 식 트리를 결과 식에서 유일한 변경 내용은 변경 이므로 다시 생성 `add` 에 `mul`입니다.</span><span class="sxs-lookup"><span data-stu-id="6916e-163">The code in the other active pattern branches just regenerates the same expression tree, so the only change in the resulting expression is the change from `add` to `mul`.</span></span>

### <a name="code"></a><span data-ttu-id="6916e-164">코드</span><span class="sxs-lookup"><span data-stu-id="6916e-164">Code</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet701.fs)]

### <a name="output"></a><span data-ttu-id="6916e-165">출력</span><span class="sxs-lookup"><span data-stu-id="6916e-165">Output</span></span>

```fsharp
1 + Module1.add(2,Module1.add(3,4))
1 + Module1.mul(2,Module1.mul(3,4))
```

## <a name="see-also"></a><span data-ttu-id="6916e-166">참고자료</span><span class="sxs-lookup"><span data-stu-id="6916e-166">See also</span></span>

- [<span data-ttu-id="6916e-167">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="6916e-167">F# Language Reference</span></span>](index.md)
