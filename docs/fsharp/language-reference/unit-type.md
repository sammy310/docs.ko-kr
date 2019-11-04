---
title: 단위 형식
description: 값이 필요 F# 하거나 원하는 값이 없는 경우 언어 구문에 값이 필요한 위치를 저장 하는 데 ' unit ' 형식이 자주 사용 되는 방법을 알아봅니다.
ms.date: 05/16/2016
ms.openlocfilehash: a5960fb05af50486a78345d10a5ad913e65729e3
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73424027"
---
# <a name="unit-type"></a><span data-ttu-id="5fae1-103">단위 형식</span><span class="sxs-lookup"><span data-stu-id="5fae1-103">Unit Type</span></span>

<span data-ttu-id="5fae1-104">`unit` 형식은 특정 값이 없음을 나타내는 형식입니다. `unit` 형식에는 다른 값이 없거나 필요한 경우 자리 표시자 역할을 하는 단일 값만 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="5fae1-105">구문</span><span class="sxs-lookup"><span data-stu-id="5fae1-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="5fae1-106">주의</span><span class="sxs-lookup"><span data-stu-id="5fae1-106">Remarks</span></span>

<span data-ttu-id="5fae1-107">모든 F# 식은 값으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="5fae1-108">관심이 있는 값을 생성 하지 않는 식의 경우 `unit` 형식의 값이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="5fae1-109">`unit` 형식은 C# 및 C++와 같은 언어의 `void` 형식과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="5fae1-110">`unit` 형식에는 단일 값이 있으며이 값은 토큰 `()`표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="5fae1-111">`unit` 형식의 값은 언어 구문에 값이 필요한 F# 위치를 포함 하는 프로그래밍에 자주 사용 되며, 값이 필요 하지 않거나 원하는 경우에는 값이 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="5fae1-112">예는 `printf` 함수의 반환 값일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="5fae1-113">함수에서 `printf` 작업의 중요 한 작업이 발생 하기 때문에 함수는 실제 값을 반환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="5fae1-114">따라서 반환 값은 `unit`형식입니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="5fae1-115">일부 구문에는 `unit` 값이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="5fae1-116">예를 들어 모듈의 최상위 수준에 있는 `do` 바인딩 또는 코드는 `unit` 값으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="5fae1-117">다음 예제와 같이 모듈의 최상위 수준에 있는 `do` 바인딩 또는 코드에서 사용 되지 않은 `unit` 값 이외의 결과가 생성 되는 경우 컴파일러는 경고를 보고 합니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="5fae1-118">이 경고는 함수형 프로그래밍의 특징입니다. 다른 .NET 프로그래밍 언어에는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="5fae1-119">함수에서 의도 하지 않은 결과가 발생 하지 않는 순수한 함수형 프로그램에서 최종 반환 값은 함수 호출의 유일한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="5fae1-120">따라서 결과가 무시 되는 경우 프로그래밍 오류가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="5fae1-121">는 F# 순수 함수형 프로그래밍 언어가 아니지만 가능 하면 항상 함수형 프로그래밍 스타일을 따르는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="5fae1-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="5fae1-122">참조</span><span class="sxs-lookup"><span data-stu-id="5fae1-122">See also</span></span>

- [<span data-ttu-id="5fae1-123">형식을</span><span class="sxs-lookup"><span data-stu-id="5fae1-123">Primitive</span></span>](basic-types.md)
- [<span data-ttu-id="5fae1-124">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="5fae1-124">F# Language Reference</span></span>](index.md)
