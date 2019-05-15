---
title: let 바인딩
description: 사용 하는 방법을 알아봅니다는 F# 'let' 바인딩 값 또는 함수를 사용 하 여 식별자를 연결 하는 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: ac33ee761cd4881f3d82d6680a07f62a1d7e77e5
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641878"
---
# <a name="let-bindings"></a><span data-ttu-id="f801d-103">let 바인딩</span><span class="sxs-lookup"><span data-stu-id="f801d-103">let Bindings</span></span>

<span data-ttu-id="f801d-104">A *바인딩* 식별자 값 또는 함수를 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-104">A *binding* associates an identifier with a value or function.</span></span> <span data-ttu-id="f801d-105">사용할는 `let` 값 또는 함수에 이름을 바인딩할 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-105">You use the `let` keyword to bind a name to a value or function.</span></span>

## <a name="syntax"></a><span data-ttu-id="f801d-106">구문</span><span class="sxs-lookup"><span data-stu-id="f801d-106">Syntax</span></span>

```fsharp
// Binding a value:
let identifier-or-pattern [: type] =expressionbody-expression
// Binding a function value:
let identifier parameter-list [: return-type ] =expressionbody-expression
```

## <a name="remarks"></a><span data-ttu-id="f801d-107">설명</span><span class="sxs-lookup"><span data-stu-id="f801d-107">Remarks</span></span>

<span data-ttu-id="f801d-108">`let` 키워드 또는 이름 하나 이상에 대 한 함수 값을 정의 하는 바인딩 식에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-108">The `let` keyword is used in binding expressions to define values or function values for one or more names.</span></span> <span data-ttu-id="f801d-109">가장 간단한 형태의 `let` 식에 이름을 바인딩하는 간단한 값을 다음과 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-109">The simplest form of the `let` expression binds a name to a simple value, as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1101.fs)]

<span data-ttu-id="f801d-110">새 줄을 사용 하 여 식의 식별자를 구분 하는 경우 다음 코드와 같이 식의 각 줄을 들여쓰기 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-110">If you separate the expression from the identifier by using a new line, you must indent each line of the expression, as in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1102.fs)]

<span data-ttu-id="f801d-111">단순한 이름 대신 이름을 포함 하는 패턴을 지정할 수 있습니다, 예를 들어, 튜플, 다음 코드와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-111">Instead of just a name, a pattern that contains names can be specified, for example, a tuple, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1103.fs)]

<span data-ttu-id="f801d-112">합니다 *식 본문* 이름이 사용 되는 식입니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-112">The *body-expression* is the expression in which the names are used.</span></span> <span data-ttu-id="f801d-113">본문 식에서 첫 번째 문자를 사용 하 여 정확 하 게 구성 줄 들여쓰기 자체 줄에 표시 된 `let` 키워드:</span><span class="sxs-lookup"><span data-stu-id="f801d-113">The body expression appears on its own line, indented to line up exactly with the first character in the `let` keyword:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1104.fs)]

<span data-ttu-id="f801d-114">`let` 바인딩 수 수준에 나타날 모듈, 클래스 형식 정의에서 나 로컬 범위에서 함수 정의와 같이 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-114">A `let` binding can appear at the module level, in the definition of a class type, or in local scopes, such as in a function definition.</span></span> <span data-ttu-id="f801d-115">`let` 최상위 수준 모듈 또는 클래스 형식에 바인딩 본문 식을에 필요 하지는 않지만 다른 범위 수준에서 본문 식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-115">A `let` binding at the top level in a module or in a class type does not need to have a body expression, but at other scope levels, the body expression is required.</span></span> <span data-ttu-id="f801d-116">바인딩된 이름을 정의 하면서 전 시점에는 없는 지점 이후에 사용할 수는 `let` 다음 코드 에서처럼 바인딩 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-116">The bound names are usable after the point of definition, but not at any point before the `let` binding appears, as is illustrated in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1105.fs)]

## <a name="function-bindings"></a><span data-ttu-id="f801d-117">함수 바인딩</span><span class="sxs-lookup"><span data-stu-id="f801d-117">Function Bindings</span></span>

<span data-ttu-id="f801d-118">다음 코드와 같이 함수 이름 및 매개 변수를 함수 바인딩을 포함 한다는 함수 바인딩 값 바인딩에 대 한 규칙을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-118">Function bindings follow the rules for value bindings, except that function bindings include the function name and the parameters, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1106.fs)]

<span data-ttu-id="f801d-119">일반적으로 매개 변수는 튜플 패턴 같은 패턴.</span><span class="sxs-lookup"><span data-stu-id="f801d-119">In general, parameters are patterns, such as a tuple pattern:</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1107.fs)]

<span data-ttu-id="f801d-120">`let` 바인딩 식 마지막 식의 값을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-120">A `let` binding expression evaluates to the value of the last expression.</span></span> <span data-ttu-id="f801d-121">다음 코드 예제에서는 값에 따라서 `result` 에서 계산 됩니다 `100 * function3 (1, 2)`를 반환 하는 `300`합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-121">Therefore, in the following code example, the value of `result` is computed from `100 * function3 (1, 2)`, which evaluates to `300`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1109.fs)]

<span data-ttu-id="f801d-122">자세한 내용은 [함수](index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f801d-122">For more information, see [Functions](index.md).</span></span>

## <a name="type-annotations"></a><span data-ttu-id="f801d-123">형식 주석</span><span class="sxs-lookup"><span data-stu-id="f801d-123">Type Annotations</span></span>

<span data-ttu-id="f801d-124">괄호 안에 포함 된 모든 형식 이름 뒤에 오는 콜론 (:)를 포함 하 여 형식 매개 변수를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-124">You can specify types for parameters by including a colon (:) followed by a type name, all enclosed in parentheses.</span></span> <span data-ttu-id="f801d-125">또한 마지막 매개 변수 뒤에 콜론과 형식을 추가 하 여 반환 값의 형식을 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-125">You can also specify the type of the return value by appending the colon and type after the last parameter.</span></span> <span data-ttu-id="f801d-126">전체 형식 주석은 `function1`, 매개 변수 형식으로 정수를 사용 하 여은 다음과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-126">The full type annotations for `function1`, with integers as the parameter types, would be as follows.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1108.fs)]

<span data-ttu-id="f801d-127">명시적 형식 매개 변수가 없는 경우 함수 매개 변수의 형식을 확인할 형식을 유추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-127">When there are no explicit type parameters, type inference is used to determine the types of parameters of functions.</span></span> <span data-ttu-id="f801d-128">제네릭으로 매개 변수의 형식을 자동으로 일반화 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-128">This can include automatically generalizing the type of a parameter to be generic.</span></span>

<span data-ttu-id="f801d-129">자세한 내용은 [자동 일반화](../generics/automatic-generalization.md) 하 고 [Typeinference](../type-inference.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-129">For more information, see [Automatic Generalization](../generics/automatic-generalization.md) and [Type Inference](../type-inference.md).</span></span>

## <a name="let-bindings-in-classes"></a><span data-ttu-id="f801d-130">클래스의 let 바인딩</span><span class="sxs-lookup"><span data-stu-id="f801d-130">let Bindings in Classes</span></span>

<span data-ttu-id="f801d-131">`let` 바인딩 구조체 또는 레코드 종류는 있지만 클래스 형식에 나타날 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-131">A `let` binding can appear in a class type but not in a structure or record type.</span></span> <span data-ttu-id="f801d-132">클래스 형식에 바인딩 let을 사용 하려면 클래스에 기본 생성자가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-132">To use a let binding in a class type, the class must have a primary constructor.</span></span> <span data-ttu-id="f801d-133">생성자 매개 변수는 클래스 정의의 형식 이름 뒤에 나타나야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-133">Constructor parameters must appear after the type name in the class definition.</span></span> <span data-ttu-id="f801d-134">A `let` 전용 필드 및 해당 클래스 형식 및 함께 멤버 클래스 형식에 대 한 바인딩 정의 `do` 형식에서 바인딩 유형에 대 한 기본 생성자의 코드를 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-134">A `let` binding in a class type defines private fields and members for that class type and, together with `do` bindings in the type, forms the code for the primary constructor for the type.</span></span> <span data-ttu-id="f801d-135">다음 코드 예제에서는 클래스를 보여 줍니다 `MyClass` 전용 필드를 사용 하 여 `field1` 고 `field2`입니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-135">The following code examples show a class `MyClass` with private fields `field1` and `field2`.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1110.fs)]

<span data-ttu-id="f801d-136">범위 `field1` 고 `field2` 선언 된 형식으로 제한 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-136">The scopes of `field1` and `field2` are limited to the type in which they are declared.</span></span> <span data-ttu-id="f801d-137">자세한 내용은 참조 하세요. [ `let` 클래스에서 바인딩을](../members/let-bindings-in-classes.md) 하 고 [클래스](../classes.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-137">For more information, see [`let` Bindings in Classes](../members/let-bindings-in-classes.md) and [Classes](../classes.md).</span></span>

## <a name="type-parameters-in-let-bindings"></a><span data-ttu-id="f801d-138">형식 매개 변수에 let 바인딩</span><span class="sxs-lookup"><span data-stu-id="f801d-138">Type Parameters in let Bindings</span></span>

<span data-ttu-id="f801d-139">`let` 계산 식 또는 형식의 모듈 수준에서 바인딩 명시적 형식 매개 변수를 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-139">A `let` binding at the module level, in a type, or in a computation expression can have explicit type parameters.</span></span> <span data-ttu-id="f801d-140">Let 식에서 함수 정의 내에서 같은 바인딩을 형식 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-140">A let binding in an expression, such as within a function definition, cannot have type parameters.</span></span> <span data-ttu-id="f801d-141">자세한 내용은 [제네릭](../generics/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f801d-141">For more information, see [Generics](../generics/index.md).</span></span>

## <a name="attributes-on-let-bindings"></a><span data-ttu-id="f801d-142">특성의 let 바인딩</span><span class="sxs-lookup"><span data-stu-id="f801d-142">Attributes on let Bindings</span></span>

<span data-ttu-id="f801d-143">특성은 최상위에 적용할 수 있습니다 `let` 모듈에서는 다음 코드 에서처럼 바인딩.</span><span class="sxs-lookup"><span data-stu-id="f801d-143">Attributes can be applied to top-level `let` bindings in a module, as shown in the following code.</span></span>

[!code-fsharp[Main](../../../../samples/snippets/fsharp/lang-ref-1/snippet1111.fs)]

## <a name="scope-and-accessibility-of-let-bindings"></a><span data-ttu-id="f801d-144">범위 및 액세스 가능성의 Let 바인딩</span><span class="sxs-lookup"><span data-stu-id="f801d-144">Scope and Accessibility of Let Bindings</span></span>

<span data-ttu-id="f801d-145">Let 바인딩을 사용 하 여 선언 된 엔터티의 범위를 포함 하는 부분으로 제한 됩니다 바인딩은 표시 되 면 (예: 함수, 모듈, 파일 또는 클래스)의 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-145">The scope of an entity declared with a let binding is limited to the portion of the containing scope (such as a function, module, file or class) after the binding appears.</span></span> <span data-ttu-id="f801d-146">따라서 해당 한다고 할 수 있습니다 let 바인딩 범위로 이름을 새로 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-146">Therefore, it can be said that a let binding introduces a name into a scope.</span></span> <span data-ttu-id="f801d-147">모듈의 let 바인딩 값 또는 함수는 모듈의 클라이언트에서 액세스할 수 한 모듈은 모듈의 공용 함수로 컴파일된 모듈의 let 바인딩 때문에 액세스할 수 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-147">In a module, a let-bound value or function is accessible to clients of a module as long as the module is accessible, since the let bindings in a module are compiled into public functions of the module.</span></span> <span data-ttu-id="f801d-148">반면, 클래스의 let 바인딩에 private 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-148">By contrast, let bindings in a class are private to the class.</span></span>

<span data-ttu-id="f801d-149">일반적으로 모듈의 함수에에서는 클라이언트 코드에서 사용 하는 경우 모듈의 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-149">Normally, functions in modules must be qualified by the name of the module when used by client code.</span></span> <span data-ttu-id="f801d-150">예를 들어 모듈 `Module1` 함수가 `function1`, 사용자 지정 `Module1.function1` 함수를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-150">For example, if a module `Module1` has a function `function1`, users would specify `Module1.function1` to refer to the function.</span></span>

<span data-ttu-id="f801d-151">사용자가 모듈의 모듈 이름으로 한정 되지 않고 해당 모듈 내 함수 사용 하기 위해 사용할 수 있도록 내보내기 선언은 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-151">Users of a module may use an import declaration to make the functions within that module available for use without being qualified by the module name.</span></span> <span data-ttu-id="f801d-152">위에서 언급 한 예에서 사용자 모듈의 열 수 있습니다이 경우 모듈 가져오기 선언 열기를 사용 하 여 `Module1` 이후에 참조 및 `function1` 직접.</span><span class="sxs-lookup"><span data-stu-id="f801d-152">In the example just mentioned, users of the module can in that case open the module by using the import declaration open `Module1` and thereafter refer to `function1` directly.</span></span>

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

<span data-ttu-id="f801d-153">일부 모듈 특성이 [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), 즉, 노출 되는 함수는 모듈의 이름으로 한정 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-153">Some modules have the attribute [RequireQualifiedAccess](https://msdn.microsoft.com/library/8b9b6ade-0471-4413-ac5d-638cd0de5f15), which means that the functions that they expose must be qualified with the name of the module.</span></span> <span data-ttu-id="f801d-154">예를 들어는 F# 특성이이 목록 모듈입니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-154">For example, the F# List module has this attribute.</span></span>

<span data-ttu-id="f801d-155">모듈 및 액세스 제어에 대 한 자세한 내용은 참조 하세요. [모듈](../modules.md) 하 고 [Access Control](../access-control.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f801d-155">For more information on modules and access control, see [Modules](../modules.md) and [Access Control](../access-control.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f801d-156">참고자료</span><span class="sxs-lookup"><span data-stu-id="f801d-156">See also</span></span>

- [<span data-ttu-id="f801d-157">함수</span><span class="sxs-lookup"><span data-stu-id="f801d-157">Functions</span></span>](index.md)
- [<span data-ttu-id="f801d-158">클래스의 `let` 바인딩</span><span class="sxs-lookup"><span data-stu-id="f801d-158">`let` Bindings in Classes</span></span>](../members/let-bindings-in-classes.md)
