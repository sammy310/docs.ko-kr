---
title: let 바인딩
description: "식별자와 값 또는 함수를 연결 하는 F # ' let ' 바인딩을 사용 하는 방법을 알아봅니다."
ms.date: 05/16/2016
ms.openlocfilehash: 6f2396f480c5e6c631d0022f4732419ee5b07db6
ms.sourcegitcommit: 9c45035b781caebc63ec8ecf912dc83fb6723b1f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/25/2020
ms.locfileid: "88812226"
---
# <a name="let-bindings"></a><span data-ttu-id="dbabe-103">let 바인딩</span><span class="sxs-lookup"><span data-stu-id="dbabe-103">let Bindings</span></span>

<span data-ttu-id="dbabe-104">*바인딩은* 식별자를 값 또는 함수와 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="dbabe-105">키워드를 사용 하 여 `let` 값 또는 함수에 이름을 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="dbabe-106">구문</span><span class="sxs-lookup"><span data-stu-id="dbabe-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="dbabe-107">설명</span><span class="sxs-lookup"><span data-stu-id="dbabe-107">Remarks</span></span>

<span data-ttu-id="dbabe-108">`let`키워드는 하나 이상의 이름에 대 한 값 또는 함수 값을 정의 하는 바인딩 식에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="dbabe-109">가장 간단한 형태의 `let` 식은 다음과 같이 이름을 단순 값에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="dbabe-110">새 줄을 사용 하 여 식별자에서 식을 구분 하는 경우 다음 코드와 같이 식의 각 줄을 들여씁니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="dbabe-111">이름 대신 이름을 포함 하는 패턴 (예: 다음 코드와 같이 튜플)을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="dbabe-112">*본문 식은* 이름이 사용 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="dbabe-113">Body 식이 해당 줄에 표시 되 고 키워드의 첫 번째 문자를 사용 하 여 정확히 줄 위로 들여쓰기 됩니다 `let` .</span><span class="sxs-lookup"><span data-stu-id="dbabe-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="dbabe-114">`let`바인딩은 모듈 수준, 클래스 형식 정의 또는 함수 정의에서와 같은 로컬 범위에서 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="dbabe-115">`let`모듈의 최상위 수준 또는 클래스 형식에서 바인딩에는 본문 식이 필요 하지 않지만 다른 범위 수준에는 body 식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="dbabe-116">다음 코드에 나와 있는 것 처럼 바인딩 이름은 정의 지점 후에 사용할 수 있지만 바인딩이 나타나기 전의 시점에는 사용할 수 없습니다 `let` .</span><span class="sxs-lookup"><span data-stu-id="dbabe-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="dbabe-117">함수 바인딩</span><span class="sxs-lookup"><span data-stu-id="dbabe-117">Function Bindings</span></span>

<span data-ttu-id="dbabe-118">함수 바인딩은 함수 이름 및 매개 변수를 포함 하는 것을 제외 하 고 다음 코드에 표시 된 것과 같이 값 바인딩에 대 한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="dbabe-119">일반적으로 매개 변수는 튜플 패턴과 같은 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="dbabe-120">`let`바인딩 식은 마지막 식의 값으로 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="dbabe-121">따라서 다음 코드 예제에서의 값은 `result` 로 계산 되는에서 계산 됩니다 `100 * function3 (1, 2)` `300` .</span><span class="sxs-lookup"><span data-stu-id="dbabe-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="dbabe-122">자세한 내용은 [함수](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbabe-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="dbabe-123">형식 주석</span><span class="sxs-lookup"><span data-stu-id="dbabe-123">Type Annotations</span></span>

<span data-ttu-id="dbabe-124">콜론 (:)을 포함 하 여 매개 변수의 형식을 지정할 수 있습니다. 다음에 형식 이름이 오고 모두 괄호로 묶여 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="dbabe-125">마지막 매개 변수 뒤에 콜론과 형식을 추가 하 여 반환 값의 형식을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="dbabe-126">`function1`정수를 매개 변수 형식으로 사용 하는에 대 한 전체 형식 주석은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="dbabe-127">명시적 형식 매개 변수가 없는 경우 형식 유추를 사용 하 여 함수 매개 변수의 형식을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="dbabe-128">여기에는 매개 변수의 형식을 제네릭으로 자동으로 일반화 하는 작업이 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="dbabe-129">자세한 내용은 [자동 일반화](../generics/automatic-generalization.md) 및 [형식 유추](../type-inference.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbabe-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="dbabe-130">클래스의 let 바인딩</span><span class="sxs-lookup"><span data-stu-id="dbabe-130">let Bindings in Classes</span></span>

<span data-ttu-id="dbabe-131">`let`바인딩은 클래스 형식에 표시 될 수 있지만 구조체 또는 레코드 형식에는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="dbabe-132">클래스 형식에 let 바인딩을 사용 하려면 클래스에 기본 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="dbabe-133">생성자 매개 변수는 클래스 정의의 형식 이름 뒤에 나와야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="dbabe-134">`let`클래스 형식의 바인딩은 해당 클래스 형식에 대 한 전용 필드 및 멤버를 정의 하 고, `do` 형식의 바인딩과 함께 형식의 기본 생성자에 대 한 코드를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="dbabe-135">다음 코드 예제에서는 `MyClass` 전용 필드와를 사용 하는 클래스를 보여 줍니다 `field1` `field2` .</span><span class="sxs-lookup"><span data-stu-id="dbabe-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="dbabe-136">및의 범위 `field1` 는 `field2` 선언 된 형식으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="dbabe-137">자세한 내용은 클래스 및 클래스 [ `let` 의 바인딩](../members/let-bindings-in-classes.md) 을 참조 [Classes](../classes.md)하세요.</span><span class="sxs-lookup"><span data-stu-id="dbabe-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="dbabe-138">Let 바인딩의 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="dbabe-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="dbabe-139">`let`모듈 수준, 형식 또는 계산 식의 바인딩은 명시적 형식 매개 변수를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="dbabe-140">함수 정의 내에서와 같이 식의 let 바인딩에는 형식 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="dbabe-141">자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dbabe-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="dbabe-142">Let 바인딩의 특성</span><span class="sxs-lookup"><span data-stu-id="dbabe-142">Attributes on let Bindings</span></span>

<span data-ttu-id="dbabe-143">다음 코드와 같이 모듈의 최상위 바인딩에 특성을 적용할 수 있습니다 `let` .</span><span class="sxs-lookup"><span data-stu-id="dbabe-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="dbabe-144">Let 바인딩의 범위 및 접근성</span><span class="sxs-lookup"><span data-stu-id="dbabe-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="dbabe-145">Let 바인딩을 사용 하 여 선언 된 엔터티의 범위는 바인딩이 표시 된 후 포함 하는 범위 (예: 함수, 모듈, 파일 또는 클래스)의 일부분으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="dbabe-146">따라서 let 바인딩에서 범위에 이름을 제공 하는 것으로 간주 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="dbabe-147">모듈의 let 바인딩 값 또는 함수는 모듈의 public 함수로 컴파일되기 때문에 모듈의 클라이언트가 액세스할 수 있는 한 모듈의 클라이언트에서 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="dbabe-148">이와 대조적으로 클래스의 let 바인딩은 클래스 전용입니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="dbabe-149">일반적으로 모듈의 함수는 클라이언트 코드에서 사용 될 때 모듈의 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="dbabe-150">예를 들어 모듈에 함수가 있는 경우 `Module1` `function1` 사용자는 `Module1.function1` 함수를 참조 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="dbabe-151">모듈의 사용자는 가져오기 선언을 사용 하 여 모듈 이름으로 한정 되지 않고 해당 모듈 내의 함수를 사용할 수 있도록 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="dbabe-152">위에서 언급 한 예제에서 모듈의 사용자는이 경우에는 가져오기 선언을 사용 하 여 모듈을 열고 `Module1` , 그 이후에는를 `function1` 직접 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

```fsharp
module Module1 =
    let function1 x = x + 1.0

module Module2 =
    let function2 x =
        Module1.function1 x

open Module1

let function3 x =
    function1 x
```

<span data-ttu-id="dbabe-153">일부 모듈에는 [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html)특성이 있습니다. 즉, 표시 되는 함수는 모듈 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-153">Some modules have the attribute [RequireQualifiedAccess](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-core-requirequalifiedaccessattribute.html), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="dbabe-154">예를 들어 F # 목록 모듈에는이 특성이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="dbabe-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="dbabe-155">모듈 및 access control에 대 한 자세한 내용은 [모듈](../modules.md) 및 [Access Control](../access-control.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="dbabe-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="dbabe-156">참조</span><span class="sxs-lookup"><span data-stu-id="dbabe-156">See also</span></span>

- [<span data-ttu-id="dbabe-157">함수</span><span class="sxs-lookup"><span data-stu-id="dbabe-157">Functions</span></span>](index.md)
- [<span data-ttu-id="dbabe-158">`let` 클래스의 바인딩</span><span class="sxs-lookup"><span data-stu-id="dbabe-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
