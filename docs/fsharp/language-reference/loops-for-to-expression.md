---
title: '루프: for...to 식'
description: F# 자세한 내용은 다음을 참조 하세요. to expression은 루프 변수의 값 범위에 대해 루프를 반복 하는 데 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: 910c04aa4ea6b2c637dcad147347c1c317b5e0c0
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68626618"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="f2c55-103">루프: for...to 식</span><span class="sxs-lookup"><span data-stu-id="f2c55-103">Loops: for...to Expression</span></span>

<span data-ttu-id="f2c55-104">루프 변수의 값 범위에 대해 루프를 반복 하는 데 식이사용됩니다.`for...to`</span><span class="sxs-lookup"><span data-stu-id="f2c55-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="f2c55-105">구문</span><span class="sxs-lookup"><span data-stu-id="f2c55-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="f2c55-106">설명</span><span class="sxs-lookup"><span data-stu-id="f2c55-106">Remarks</span></span>

<span data-ttu-id="f2c55-107">식별자의 형식은 *start* 및 *finish* 식의 형식에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2c55-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="f2c55-108">이러한 식의 형식은 32 비트 정수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c55-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="f2c55-109">기술적으로 `for...to` 는 식이 명령형 프로그래밍 언어의 일반적인 문과 유사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c55-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="f2c55-110">*본문 식* 의 반환 형식은 여야 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="f2c55-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="f2c55-111">다음 예에서는 다양 한 `for...to` 식 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f2c55-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="f2c55-112">위 코드는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="f2c55-112">The output of the previous code is as follows.</span></span>

```
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="f2c55-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="f2c55-113">See also</span></span>

- [<span data-ttu-id="f2c55-114">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="f2c55-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="f2c55-115">하며 `for...in`식</span><span class="sxs-lookup"><span data-stu-id="f2c55-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="f2c55-116">하며 `while...do`식</span><span class="sxs-lookup"><span data-stu-id="f2c55-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
