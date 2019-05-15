---
title: 단위 형식
description: 에 대해 알아봅니다 하는 방법을 F# 'unit' 유형은 자리를 값이 필요한 언어 구문을 사용 하 여 필요한 되었거나 필요한 값이 없는 경우에 자주 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: d515e19489bfa7de6f17194fd74176cfa0bcd7c9
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65645129"
---
# <a name="unit-type"></a><span data-ttu-id="559a1-103">단위 형식</span><span class="sxs-lookup"><span data-stu-id="559a1-103">Unit Type</span></span>

<span data-ttu-id="559a1-104">합니다 `unit` 의 특정 값이 없음을 나타내는 형식인 형식은 `unit` 형식은 다른 값이 없으므로 있거나 필요한 경우 자리 표시자로 역할을 하는 단일 값만 합니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-104">The `unit` type is a type that indicates the absence of a specific value; the `unit` type has only a single value, which acts as a placeholder when no other value exists or is needed.</span></span>

## <a name="syntax"></a><span data-ttu-id="559a1-105">구문</span><span class="sxs-lookup"><span data-stu-id="559a1-105">Syntax</span></span>

```fsharp
// The value of the unit type.
()
```

## <a name="remarks"></a><span data-ttu-id="559a1-106">설명</span><span class="sxs-lookup"><span data-stu-id="559a1-106">Remarks</span></span>

<span data-ttu-id="559a1-107">모든 F# 식은 값으로 계산 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-107">Every F# expression must evaluate to a value.</span></span> <span data-ttu-id="559a1-108">형식의 값을 원하는 값을 생성 하지 않습니다 하는 식에 대 한 `unit` 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-108">For expressions that do not generate a value that is of interest, the value of type `unit` is used.</span></span> <span data-ttu-id="559a1-109">`unit` 형식와 유사 합니다 `void` 와 같은 언어에서 입력 C# 및 C++.</span><span class="sxs-lookup"><span data-stu-id="559a1-109">The `unit` type resembles the `void` type in languages such as C# and C++.</span></span>

<span data-ttu-id="559a1-110">합니다 `unit` 형식은 단일 값 및 해당 값은 토큰에 나타난 `()`합니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-110">The `unit` type has a single value, and that value is indicated by the token `()`.</span></span>

<span data-ttu-id="559a1-111">값을 `unit` 형식에 주로 사용 됩니다 F# 하지만 값은 필요한 또는 원하는 언어 구문을 사용 하 여 값이 필요한 경우 위치를 저장 하는 프로그래밍 합니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-111">The value of the `unit` type is often used in F# programming to hold the place where a value is required by the language syntax, but when no value is needed or desired.</span></span> <span data-ttu-id="559a1-112">반환 값을 예로 들 수 있습니다는 `printf` 함수입니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-112">An example might be the return value of a `printf` function.</span></span> <span data-ttu-id="559a1-113">있으므로의 중요 한 작업을 `printf` 작업 함수에서 발생이 함수는 실제 값을 반환할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-113">Because the important actions of the `printf` operation occur in the function, the function does not have to return an actual value.</span></span> <span data-ttu-id="559a1-114">형식의 반환 값은 따라서 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-114">Therefore, the return value is of type `unit`.</span></span>

<span data-ttu-id="559a1-115">일부 구문은 예상을 `unit` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-115">Some constructs expect a `unit` value.</span></span> <span data-ttu-id="559a1-116">예를 들어, 한 `do` 바인딩 또는 코드 모듈의 최상위 수준에서 평가 되어야 하는 `unit` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-116">For example, a `do` binding or any code at the top level of a module is expected to evaluate to a `unit` value.</span></span> <span data-ttu-id="559a1-117">컴파일러 경고를 보고 경우는 `do` 바인딩 또는 코드 모듈의 최상위 수준에서 결과 이외의 `unit` 다음 예와에서 같이 사용 되지 않는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-117">The compiler reports a warning when a `do` binding or code at the top level of a module produces a result other than the `unit` value that is not used, as shown in the following example.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-1/snippet901.fs)]

<span data-ttu-id="559a1-118">이 경고는 함수형 프로그래밍;의 특징 다른.NET 프로그래밍 언어에에서는 표시 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-118">This warning is a characteristic of functional programming; it does not appear in other .NET programming languages.</span></span> <span data-ttu-id="559a1-119">함수 없는 부작용을 순수 함수형 프로그램에서 최종 반환 값은 함수 호출의 유일한 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-119">In a purely functional program, in which functions do not have any side effects, the final return value is the only result of a function call.</span></span> <span data-ttu-id="559a1-120">따라서 결과 무시 하는 경우 가능한 프로그래밍 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-120">Therefore, when the result is ignored, it is a possible programming error.</span></span> <span data-ttu-id="559a1-121">하지만 F# 순수 하 게 제대로 작동 하지 않는 프로그래밍 언어, 것이 좋습니다 가능한 함수형 프로그래밍 스타일을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="559a1-121">Although F# is not a purely functional programming language, it is a good practice to follow functional programming style whenever possible.</span></span>

## <a name="see-also"></a><span data-ttu-id="559a1-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="559a1-122">See also</span></span>

- [<span data-ttu-id="559a1-123">기본</span><span class="sxs-lookup"><span data-stu-id="559a1-123">Primitive</span></span>](primitive-types.md)
- [<span data-ttu-id="559a1-124">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="559a1-124">F# Language Reference</span></span>](index.md)
