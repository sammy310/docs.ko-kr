---
title: 형식 유추
description: 설명 하는 방법을 F# 컴파일러가 값, 변수, 매개 변수 및 반환 값의 형식을 유추 합니다.
ms.date: 05/16/2016
ms.openlocfilehash: ab1a4aa8df4312287df749d5d6d0ea2858091152
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641673"
---
# <a name="type-inference"></a><span data-ttu-id="69e96-103">형식 유추</span><span class="sxs-lookup"><span data-stu-id="69e96-103">Type Inference</span></span>

<span data-ttu-id="69e96-104">이 항목에 설명 하는 방법을 F# 컴파일러가 값, 변수, 매개 변수 및 반환 값의 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-104">This topic describes how the F# compiler infers the types of values, variables, parameters and return values.</span></span>

## <a name="type-inference-in-general"></a><span data-ttu-id="69e96-105">형식 유추를 일반 사항</span><span class="sxs-lookup"><span data-stu-id="69e96-105">Type Inference in General</span></span>

<span data-ttu-id="69e96-106">형식 유추는 유형을 지정할 필요가 없습니다 F# 컴파일러 형식을 최종적으로 추론할 수 없습니다. 제외 하 고 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-106">The idea of type inference is that you do not have to specify the types of F# constructs except when the compiler cannot conclusively deduce the type.</span></span> <span data-ttu-id="69e96-107">명시적 형식 정보를 생략 하면 의미 하는 F# 은 동적으로 형식화 된 언어 또는 값을 F# 는 약하게 형식화 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-107">Omitting explicit type information does not mean that F# is a dynamically typed language or that values in F# are weakly typed.</span></span> <span data-ttu-id="69e96-108">F#정적 형식의 언어 컴파일러를 컴파일하는 동안 각 구문에 대 한 정확한 형식을 추론 하는 경우</span><span class="sxs-lookup"><span data-stu-id="69e96-108">F# is a statically typed language, which means that the compiler deduces an exact type for each construct during compilation.</span></span> <span data-ttu-id="69e96-109">각 구문의 형식을 추론 하도록 컴파일러에 대 한 충분 한 정보가 없는 경우 코드 어딘가에 명시적 형식 주석을 추가 하 여 일반적으로 추가 형식 정보를 제공 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-109">If there is not enough information for the compiler to deduce the types of each construct, you must supply additional type information, typically by adding explicit type annotations somewhere in the code.</span></span>

## <a name="inference-of-parameter-and-return-types"></a><span data-ttu-id="69e96-110">매개 변수 및 반환 형식 유추</span><span class="sxs-lookup"><span data-stu-id="69e96-110">Inference of Parameter and Return Types</span></span>

<span data-ttu-id="69e96-111">매개 변수 목록, 각 매개 변수의 형식을 지정할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-111">In a parameter list, you do not have to specify the type of each parameter.</span></span> <span data-ttu-id="69e96-112">및 아직 F# 정적 형식의 언어 이며 따라서 모든 값과 식 형식이 한정 된 컴파일 타임에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-112">And yet, F# is a statically typed language, and therefore every value and expression has a definite type at compile time.</span></span> <span data-ttu-id="69e96-113">컴파일러는 명시적으로 지정 하지 않는 해당 형식에 대 한 컨텍스트를 기반으로 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-113">For those types that you do not specify explicitly, the compiler infers the type based on the context.</span></span> <span data-ttu-id="69e96-114">형식에 별도로 지정 하지 않은 경우에 제네릭으로 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-114">If the type is not otherwise specified, it is inferred to be generic.</span></span> <span data-ttu-id="69e96-115">코드에서는 값을 일관 되지 않게 하는 경우 이러한 방식으로 단일 이상 인지 유추 컴파일러 오류를 보고, 값의 모든 사용을 충족 하는 형식.</span><span class="sxs-lookup"><span data-stu-id="69e96-115">If the code uses a value inconsistently, in such a way that there is no single inferred type that satisfies all the uses of a value, the compiler reports an error.</span></span>

<span data-ttu-id="69e96-116">함수의 반환 형식은 함수에 있는 마지막 식의 형식에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-116">The return type of a function is determined by the type of the last expression in the function.</span></span>

<span data-ttu-id="69e96-117">예를 들어, 다음 코드에서는 형식 매개 변수에서에서 `a` 및 `b` 반환 형식 모두로 유추 하 고 `int` 때문에 리터럴 `100` 형식의 `int`합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-117">For example, in the following code, the parameter types `a` and `b` and the return type are all inferred to be `int` because the literal `100` is of type `int`.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet301.fs)]

<span data-ttu-id="69e96-118">리터럴은 변경 하 여 형식 유추를 조작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-118">You can influence type inference by changing the literals.</span></span> <span data-ttu-id="69e96-119">경우는 `100` 는 `uint32` 접미사를 추가 하 여 `u`, 유형을 `a`, `b`, 반환 값으로 유추 되 고 `uint32`입니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-119">If you make the `100` a `uint32` by appending the suffix `u`, the types of `a`, `b`, and the return value are inferred to be `uint32`.</span></span>

<span data-ttu-id="69e96-120">영향을 줄 수도 수, 함수 및 메서드를 특정 형식에만 사용 하는 같은 형식에 대 한 제한이 의미 하는 기타 항목을 사용 하 여 형식을 유추 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-120">You can also influence type inference by using other constructs that imply restrictions on the type, such as functions and methods that work with only a particular type.</span></span>

<span data-ttu-id="69e96-121">또한 적용할 수 있습니다 명시적 형식 주석을 함수 또는 메서드 매개 변수 또는 식에서 변수는 다음 예와에서 같이.</span><span class="sxs-lookup"><span data-stu-id="69e96-121">Also, you can apply explicit type annotations to function or method parameters or to variables in expressions, as shown in the following examples.</span></span> <span data-ttu-id="69e96-122">오류가 발생 하면 다른 제약 조건 간에 충돌이 발생 하면 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-122">Errors result if conflicts occur between different constraints.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet302.fs)]

<span data-ttu-id="69e96-123">형식 주석이 매개 변수를 모두 제공 하 여 함수의 반환 값을 명시적으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-123">You can also explicitly specify the return value of a function by providing a type annotation after all the parameters.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet303.fs)]

<span data-ttu-id="69e96-124">일반적인 사례는 형식 주석을 유용 매개 변수의 경우 매개 변수는 개체 형식 및 멤버를 사용 하려는 경우</span><span class="sxs-lookup"><span data-stu-id="69e96-124">A common case where a type annotation is useful on a parameter is when the parameter is an object type and you want to use a member.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet304.fs)]

## <a name="automatic-generalization"></a><span data-ttu-id="69e96-125">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="69e96-125">Automatic Generalization</span></span>

<span data-ttu-id="69e96-126">함수 코드 매개 변수의 형식에 종속 된 경우 컴파일러는 매개 변수를 제네릭를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-126">If the function code is not dependent on the type of a parameter, the compiler considers the parameter to be generic.</span></span> <span data-ttu-id="69e96-127">이 이라고 *자동 일반화*, 복잡성을 늘리지 않고 일반 코드를 작성 하는 데 강력한 aid 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-127">This is called *automatic generalization*, and it can be a powerful aid to writing generic code without increasing complexity.</span></span>

<span data-ttu-id="69e96-128">예를 들어, 다음 함수는 튜플로 모든 형식의 두 매개 변수를 결합합니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-128">For example, the following function combines two parameters of any type into a tuple.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-3/snippet305.fs)]

<span data-ttu-id="69e96-129">형식 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-129">The type is inferred to be</span></span>

```fsharp
'a -> 'b -> 'a * 'b
```

## <a name="additional-information"></a><span data-ttu-id="69e96-130">추가 정보</span><span class="sxs-lookup"><span data-stu-id="69e96-130">Additional Information</span></span>

<span data-ttu-id="69e96-131">형식 유추에서 자세히 설명 되어는 F# 언어 사양입니다.</span><span class="sxs-lookup"><span data-stu-id="69e96-131">Type inference is described in more detail in the F# Language Specification.</span></span>

## <a name="see-also"></a><span data-ttu-id="69e96-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="69e96-132">See also</span></span>

- [<span data-ttu-id="69e96-133">자동 일반화</span><span class="sxs-lookup"><span data-stu-id="69e96-133">Automatic Generalization</span></span>](generics/automatic-generalization.md)
