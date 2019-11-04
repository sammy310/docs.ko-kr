---
title: 정적으로 확인된 형식 매개 변수
description: F# 정적으로 확인 된 형식 매개 변수를 사용 하는 방법에 대해 설명 합니다 .이 매개 변수는 컴파일 시간에 런타임에 대신 실제 형식으로 바뀝니다.
ms.date: 05/16/2016
ms.openlocfilehash: 017c18dd3caaa484ddc653557573f548e3224ca0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73425007"
---
# <a name="statically-resolved-type-parameters"></a><span data-ttu-id="ade92-103">정적으로 확인된 형식 매개 변수</span><span class="sxs-lookup"><span data-stu-id="ade92-103">Statically Resolved Type Parameters</span></span>

<span data-ttu-id="ade92-104">*정적으로 확인 된 형식 매개 변수* 는 컴파일 타임에 런타임에 대신 실제 형식으로 대체 되는 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-104">A *statically resolved type parameter* is a type parameter that is replaced with an actual type at compile time instead of at run time.</span></span> <span data-ttu-id="ade92-105">앞에 캐럿 (^) 기호가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-105">They are preceded by a caret (^) symbol.</span></span>

## <a name="syntax"></a><span data-ttu-id="ade92-106">구문</span><span class="sxs-lookup"><span data-stu-id="ade92-106">Syntax</span></span>

```fsharp
ˆtype-parameter
```

## <a name="remarks"></a><span data-ttu-id="ade92-107">주의</span><span class="sxs-lookup"><span data-stu-id="ade92-107">Remarks</span></span>

<span data-ttu-id="ade92-108">F# 언어에는 두 가지 종류의 형식 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-108">In the F# language, there are two distinct kinds of type parameters.</span></span> <span data-ttu-id="ade92-109">첫 번째 종류는 표준 제네릭 형식 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-109">The first kind is the standard generic type parameter.</span></span> <span data-ttu-id="ade92-110">`'T` 및 `'U`와 같이 아포스트로피 (')로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-110">These are indicated by an apostrophe ('), as in `'T` and `'U`.</span></span> <span data-ttu-id="ade92-111">다른 .NET Framework 언어의 제네릭 형식 매개 변수와 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-111">They are equivalent to generic type parameters in other .NET Framework languages.</span></span> <span data-ttu-id="ade92-112">다른 종류는 정적으로 확인 되 고 `^T` 및 `^U`와 같이 캐럿 기호로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-112">The other kind is statically resolved and is indicated by a caret symbol, as in `^T` and `^U`.</span></span>

<span data-ttu-id="ade92-113">정적으로 확인 된 형식 매개 변수는 멤버 제약 조건과 함께 사용 됩니다 .이 제약 조건은 형식 인수를 사용 하기 위해 특정 멤버를 포함 해야 하도록 지정할 수 있는 제약 조건입니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-113">Statically resolved type parameters are primarily useful in conjunction with member constraints, which are constraints that allow you to specify that a type argument must have a particular member or members in order to be used.</span></span> <span data-ttu-id="ade92-114">일반 제네릭 형식 매개 변수를 사용 하 여 이러한 종류의 제약 조건을 만들 수 있는 방법은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-114">There is no way to create this kind of constraint by using a regular generic type parameter.</span></span>

<span data-ttu-id="ade92-115">다음 표에서는 두 종류의 형식 매개 변수 간의 유사점과 차이점을 요약 하 여 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-115">The following table summarizes the similarities and differences between the two kinds of type parameters.</span></span>

|<span data-ttu-id="ade92-116">기능</span><span class="sxs-lookup"><span data-stu-id="ade92-116">Feature</span></span>|<span data-ttu-id="ade92-117">제네릭</span><span class="sxs-lookup"><span data-stu-id="ade92-117">Generic</span></span>|<span data-ttu-id="ade92-118">정적으로 해결 됨</span><span class="sxs-lookup"><span data-stu-id="ade92-118">Statically resolved</span></span>|
|-------|-------|-------------------|
|<span data-ttu-id="ade92-119">구문</span><span class="sxs-lookup"><span data-stu-id="ade92-119">Syntax</span></span>|<span data-ttu-id="ade92-120">`'T`, `'U`</span><span class="sxs-lookup"><span data-stu-id="ade92-120">`'T`, `'U`</span></span>|<span data-ttu-id="ade92-121">`^T`, `^U`</span><span class="sxs-lookup"><span data-stu-id="ade92-121">`^T`, `^U`</span></span>|
|<span data-ttu-id="ade92-122">해결 시간</span><span class="sxs-lookup"><span data-stu-id="ade92-122">Resolution time</span></span>|<span data-ttu-id="ade92-123">실행 시간</span><span class="sxs-lookup"><span data-stu-id="ade92-123">Run time</span></span>|<span data-ttu-id="ade92-124">컴파일 시간</span><span class="sxs-lookup"><span data-stu-id="ade92-124">Compile time</span></span>|
|<span data-ttu-id="ade92-125">멤버 제약 조건</span><span class="sxs-lookup"><span data-stu-id="ade92-125">Member constraints</span></span>|<span data-ttu-id="ade92-126">멤버 제약 조건과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-126">Cannot be used with member constraints.</span></span>|<span data-ttu-id="ade92-127">멤버 제약 조건과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-127">Can be used with member constraints.</span></span>|
|<span data-ttu-id="ade92-128">코드 생성</span><span class="sxs-lookup"><span data-stu-id="ade92-128">Code generation</span></span>|<span data-ttu-id="ade92-129">표준 제네릭 형식 매개 변수가 있는 형식 (또는 메서드)으로 인해 단일 제네릭 형식 또는 메서드가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-129">A type (or method) with standard generic type parameters results in the generation of a single generic type or method.</span></span>|<span data-ttu-id="ade92-130">필요한 각 형식에 대해 하나씩, 형식 및 메서드의 여러 인스턴스화가 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-130">Multiple instantiations of types and methods are generated, one for each type that is needed.</span></span>|
|<span data-ttu-id="ade92-131">형식과 함께 사용</span><span class="sxs-lookup"><span data-stu-id="ade92-131">Use with types</span></span>|<span data-ttu-id="ade92-132">형식에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-132">Can be used on types.</span></span>|<span data-ttu-id="ade92-133">는 형식에 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-133">Cannot be used on types.</span></span>|
|<span data-ttu-id="ade92-134">인라인 함수와 함께 사용</span><span class="sxs-lookup"><span data-stu-id="ade92-134">Use with inline functions</span></span>|<span data-ttu-id="ade92-135">아니요.</span><span class="sxs-lookup"><span data-stu-id="ade92-135">No.</span></span> <span data-ttu-id="ade92-136">인라인 함수는 표준 제네릭 형식 매개 변수를 사용 하 여 매개 변수화 할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-136">An inline function cannot be parameterized with a standard generic type parameter.</span></span>|<span data-ttu-id="ade92-137">예.</span><span class="sxs-lookup"><span data-stu-id="ade92-137">Yes.</span></span> <span data-ttu-id="ade92-138">인라인이 아닌 함수 또는 메서드에서는 정적으로 확인 된 형식 매개 변수를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-138">Statically resolved type parameters cannot be used on functions or methods that are not inline.</span></span>|

<span data-ttu-id="ade92-139">많은 F# 핵심 라이브러리 함수, 특히 연산자는 정적으로 형식 매개 변수를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-139">Many F# core library functions, especially operators, have statically resolved type parameters.</span></span> <span data-ttu-id="ade92-140">이러한 함수 및 연산자는 인라인으로 되어 숫자 계산을 위한 효율적인 코드 생성을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-140">These functions and operators are inline, and result in efficient code generation for numeric computations.</span></span>

<span data-ttu-id="ade92-141">연산자를 사용 하거나 정적으로 확인 된 형식 매개 변수를 사용 하는 다른 함수를 사용 하는 인라인 메서드 및 함수는 정적으로 확인 된 형식 매개 변수를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-141">Inline methods and functions that use operators, or use other functions that have statically resolved type parameters, can also use statically resolved type parameters themselves.</span></span> <span data-ttu-id="ade92-142">대개 형식 유추는 정적으로 확인 된 형식 매개 변수를 갖도록 이러한 인라인 함수를 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-142">Often, type inference infers such inline functions to have statically resolved type parameters.</span></span> <span data-ttu-id="ade92-143">다음 예제에서는 정적으로 확인 된 형식 매개 변수를 갖도록 유추 되는 연산자 정의를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-143">The following example illustrates an operator definition that is inferred to have a statically resolved type parameter.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-3/snippet401.fs)]

<span data-ttu-id="ade92-144">`(+@)`의 확인 된 형식은 `(+)`와 `(*)`를 모두 사용 하는 것을 기반으로 하며, 두 경우 모두 형식 유추를 통해 정적으로 확인 된 형식 매개 변수에 대 한 멤버 제약 조건을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-144">The resolved type of `(+@)` is based on the use of both `(+)` and `(*)`, both of which cause type inference to infer member constraints on the statically resolved type parameters.</span></span> <span data-ttu-id="ade92-145">F# 인터프리터와 같이 확인 된 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-145">The resolved type, as shown in the F# interpreter, is as follows.</span></span>

```fsharp
^a -> ^c -> ^d
when (^a or ^b) : (static member ( + ) : ^a * ^b -> ^d) and
(^a or ^c) : (static member ( * ) : ^a * ^c -> ^b)
```

<span data-ttu-id="ade92-146">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-146">The output is as follows.</span></span>

```console
2
1.500000
```

<span data-ttu-id="ade92-147">4\.1부터 F# 정적으로 확인 된 형식 매개 변수 시그니처에서 구체적 형식 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-147">Starting with F# 4.1, you can also specify concrete type names in statically resolved type parameter signatures.</span></span>  <span data-ttu-id="ade92-148">이전 버전의 언어에서 형식 이름은 실제로 컴파일러에서 유추 될 수 있지만 실제로 시그니처에는 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-148">In previous versions of the language, the type name could actually be inferred by the compiler, but could not actually be specified in the signature.</span></span>  <span data-ttu-id="ade92-149">4\.1의 F# 경우 정적으로 확인 된 형식 매개 변수 시그니처에서 구체적 형식 이름을 지정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-149">As of F# 4.1, you may also specify concrete type names in statically resolved type parameter signatures.</span></span> <span data-ttu-id="ade92-150">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="ade92-150">Here's an example:</span></span>

```fsharp
let inline konst x _ = x

type CFunctor() =
    static member inline fmap (f: ^a -> ^b, a: ^a list) = List.map f a
    static member inline fmap (f: ^a -> ^b, a: ^a option) =
        match a with
        | None -> None
        | Some x -> Some (f x)

    // default implementation of replace
    static member inline replace< ^a, ^b, ^c, ^d, ^e when ^a :> CFunctor and (^a or ^d): (static member fmap: (^b -> ^c) * ^d -> ^e) > (a, f) =
        ((^a or ^d) : (static member fmap : (^b -> ^c) * ^d -> ^e) (konst a, f))

    // call overridden replace if present
    static member inline replace< ^a, ^b, ^c when ^b: (static member replace: ^a * ^b -> ^c)>(a: ^a, f: ^b) =
        (^b : (static member replace: ^a * ^b -> ^c) (a, f))

let inline replace_instance< ^a, ^b, ^c, ^d when (^a or ^c): (static member replace: ^b * ^c -> ^d)> (a: ^b, f: ^c) =
        ((^a or ^c): (static member replace: ^b * ^c -> ^d) (a, f))

// Note the concrete type 'CFunctor' specified in the signature
let inline replace (a: ^a) (f: ^b): ^a0 when (CFunctor or  ^b): (static member replace: ^a *  ^b ->  ^a0) =
    replace_instance<CFunctor, _, _, _> (a, f)
```

## <a name="see-also"></a><span data-ttu-id="ade92-151">참조</span><span class="sxs-lookup"><span data-stu-id="ade92-151">See also</span></span>

- [<span data-ttu-id="ade92-152">제네릭</span><span class="sxs-lookup"><span data-stu-id="ade92-152">Generics</span></span>](index.md)
- [<span data-ttu-id="ade92-153">형식 유추</span><span class="sxs-lookup"><span data-stu-id="ade92-153">Type Inference</span></span>](../type-inference.md)
- [<span data-ttu-id="ade92-154">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="ade92-154">Automatic Generalization</span></span>](automatic-generalization.md)
- [<span data-ttu-id="ade92-155">제약 조건</span><span class="sxs-lookup"><span data-stu-id="ade92-155">Constraints</span></span>](constraints.md)
- [<span data-ttu-id="ade92-156">인라인 함수</span><span class="sxs-lookup"><span data-stu-id="ade92-156">Inline Functions</span></span>](../functions/inline-functions.md)
