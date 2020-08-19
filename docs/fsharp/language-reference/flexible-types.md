---
title: 유연한 형식
description: '매개 변수, 변수 또는 값에 지정 된 형식과 호환 되는 형식이 있음을 나타내는 F # 유연한 형식 주석을 사용 하는 방법에 대해 알아봅니다.'
ms.date: 08/15/2020
ms.openlocfilehash: 44241ad082cd7f3de9e0cc6a48b8a8946e7b33d3
ms.sourcegitcommit: 8bfeb5930ca48b2ee6053f16082dcaf24d46d221
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/18/2020
ms.locfileid: "88557752"
---
# <a name="flexible-types"></a><span data-ttu-id="6cf5c-103">유연한 형식</span><span class="sxs-lookup"><span data-stu-id="6cf5c-103">Flexible Types</span></span>

<span data-ttu-id="6cf5c-104">*유연한 형식 주석은* 매개 변수, 변수 또는 값에 지정 된 형식과 호환 되는 형식이 있음을 나타냅니다 .이 경우 호환성은 클래스 또는 인터페이스의 개체 지향 계층 구조에 있는 위치에 따라 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-104">A *flexible type annotation* indicates that a parameter, variable, or value has a type that is compatible with a specified type, where compatibility is determined by position in an object-oriented hierarchy of classes or interfaces.</span></span> <span data-ttu-id="6cf5c-105">유연한 형식은 형식 계층 구조에서 더 높은 형식으로의 자동 변환이 발생 하지 않는 경우 특히 유용 하지만, 계층 구조 또는 인터페이스를 구현 하는 모든 형식에 대해 기능을 사용할 수 있도록 하려는 경우에도 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-105">Flexible types are useful specifically when the automatic conversion to types higher in the type hierarchy does not occur but you still want to enable your functionality to work with any type in the hierarchy or any type that implements an interface.</span></span>

## <a name="syntax"></a><span data-ttu-id="6cf5c-106">구문</span><span class="sxs-lookup"><span data-stu-id="6cf5c-106">Syntax</span></span>

```fsharp
#type
```

## <a name="remarks"></a><span data-ttu-id="6cf5c-107">설명</span><span class="sxs-lookup"><span data-stu-id="6cf5c-107">Remarks</span></span>

<span data-ttu-id="6cf5c-108">이전 구문에서 *형식은* 기본 형식 또는 인터페이스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-108">In the previous syntax, *type* represents a base type or an interface.</span></span>

<span data-ttu-id="6cf5c-109">유연한 형식은 기본 또는 인터페이스 형식과 호환 되는 형식으로 허용 되는 형식을 제한 하는 제약 조건이 있는 제네릭 형식과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-109">A flexible type is equivalent to a generic type that has a constraint that limits the allowed types to types that are compatible with the base or interface type.</span></span> <span data-ttu-id="6cf5c-110">즉, 다음 두 줄의 코드는 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-110">That is, the following two lines of code are equivalent.</span></span>

```fsharp
#SomeType

'T when 'T :> SomeType
```

<span data-ttu-id="6cf5c-111">유연한 형식은 여러 유형의 상황에서 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-111">Flexible types are useful in several types of situations.</span></span> <span data-ttu-id="6cf5c-112">예를 들어 고차 함수 (함수를 인수로 사용 하는 함수)가 있는 경우 함수에서 유연한 형식을 반환 하는 것이 유용한 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-112">For example, when you have a higher order function (a function that takes a function as an argument), it is often useful to have the function return a flexible type.</span></span> <span data-ttu-id="6cf5c-113">다음 예제에서의 시퀀스 인수를 사용 하는 유연한 형식을 사용 하면 `iterate2` 고차 함수에서 시퀀스, 배열, 목록 및 기타 열거 가능한 형식을 생성 하는 함수를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-113">In the following example, the use of a flexible type with a sequence argument in `iterate2` enables the higher order function to work with functions that generate sequences, arrays, lists, and any other enumerable type.</span></span>

<span data-ttu-id="6cf5c-114">다음 두 함수 중 하나는 시퀀스를 반환 하는 함수 중 하나는 유연한 형식을 반환 하는 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-114">Consider the following two functions, one of which returns a sequence, the other of which returns a flexible type.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4101.fs)]

<span data-ttu-id="6cf5c-115">또 다른 예로, [Seq. concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#concat) library 함수를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-115">As another example, consider the [Seq.concat](https://fsharp.github.io/fsharp-core-docs/reference/fsharp-collections-seqmodule.html#concat) library function:</span></span>

```fsharp
val concat: sequences:seq<#seq<'T>> -> seq<'T>
```

<span data-ttu-id="6cf5c-116">다음의 열거 가능한 시퀀스를이 함수에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-116">You can pass any of the following enumerable sequences to this function:</span></span>

- <span data-ttu-id="6cf5c-117">목록 목록</span><span class="sxs-lookup"><span data-stu-id="6cf5c-117">A list of lists</span></span>
- <span data-ttu-id="6cf5c-118">배열 목록</span><span class="sxs-lookup"><span data-stu-id="6cf5c-118">A list of arrays</span></span>
- <span data-ttu-id="6cf5c-119">목록 배열</span><span class="sxs-lookup"><span data-stu-id="6cf5c-119">An array of lists</span></span>
- <span data-ttu-id="6cf5c-120">시퀀스의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-120">An array of sequences</span></span>
- <span data-ttu-id="6cf5c-121">열거 가능한 시퀀스의 다른 조합</span><span class="sxs-lookup"><span data-stu-id="6cf5c-121">Any other combination of enumerable sequences</span></span>

<span data-ttu-id="6cf5c-122">다음 코드에서는를 사용 하 여 `Seq.concat` 유연한 형식으로 지원할 수 있는 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-122">The following code uses `Seq.concat` to demonstrate the scenarios that you can support by using flexible types.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet4102.fs)]

<span data-ttu-id="6cf5c-123">출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-123">The output is as follows.</span></span>

```console
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
seq [1; 2; 3; 4; ...]
```

<span data-ttu-id="6cf5c-124">다른 개체 지향 언어와 마찬가지로 F #의 경우 인터페이스를 구현 하는 파생 형식 또는 형식이 자동으로 기본 형식 또는 인터페이스 형식으로 변환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-124">In F#, as in other object-oriented languages, there are contexts in which derived types or types that implement interfaces are automatically converted to a base type or interface type.</span></span> <span data-ttu-id="6cf5c-125">이러한 자동 변환은 직접 인수에서 발생 하지만 형식이 하위 위치에 있거나 함수 형식의 반환 형식 또는 형식 인수로 같은 보다 복잡 한 형식의 일부로 포함 된 경우에는 발생 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-125">These automatic conversions occur in direct arguments, but not when the type is in a subordinate position, as part of a more complex type such as a return type of a function type, or as a type argument.</span></span> <span data-ttu-id="6cf5c-126">따라서 유연한 형식 표기법은 적용 하는 형식이 보다 복잡 한 형식의 일부일 때 주로 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cf5c-126">Thus, the flexible type notation is primarily useful when the type you are applying it to is part of a more complex type.</span></span>

## <a name="see-also"></a><span data-ttu-id="6cf5c-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6cf5c-127">See also</span></span>

- [<span data-ttu-id="6cf5c-128">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="6cf5c-128">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="6cf5c-129">제네릭</span><span class="sxs-lookup"><span data-stu-id="6cf5c-129">Generics</span></span>](./generics/index.md)
