---
title: '루프: for...to 식'
description: F# 자세한 내용은 다음을 참조 하세요. to expression은 루프 변수의 값 범위에 대해 루프를 반복 하는 데 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: 882b6e48dd09efcb57f7ef2f419e68a6c43393a5
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "74283910"
---
# <a name="loops-forto-expression"></a><span data-ttu-id="ed6c8-103">루프: for...to 식</span><span class="sxs-lookup"><span data-stu-id="ed6c8-103">Loops: for...to Expression</span></span>

<span data-ttu-id="ed6c8-104">`for...to` 식은 루프 변수의 값 범위에 대해 루프에서 반복 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c8-104">The `for...to` expression is used to iterate in a loop over a range of values of a loop variable.</span></span>

## <a name="syntax"></a><span data-ttu-id="ed6c8-105">구문</span><span class="sxs-lookup"><span data-stu-id="ed6c8-105">Syntax</span></span>

```fsharp
for identifier = start [ to | downto ] finish do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="ed6c8-106">설명</span><span class="sxs-lookup"><span data-stu-id="ed6c8-106">Remarks</span></span>

<span data-ttu-id="ed6c8-107">식별자의 형식은 *start* 및 *finish* 식의 형식에서 유추 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c8-107">The type of the identifier is inferred from the type of the *start* and *finish* expressions.</span></span> <span data-ttu-id="ed6c8-108">이러한 식의 형식은 32 비트 정수 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c8-108">Types for these expressions must be 32-bit integers.</span></span>

<span data-ttu-id="ed6c8-109">기술적으로는 `for...to` 식이 명령형 프로그래밍 언어의 일반적인 문과 비슷합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c8-109">Although technically an expression, `for...to` is more like a traditional statement in an imperative programming language.</span></span> <span data-ttu-id="ed6c8-110">*본문 식* 의 반환 형식은 `unit`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c8-110">The return type for the *body-expression* must be `unit`.</span></span> <span data-ttu-id="ed6c8-111">다음 예에서는 `for...to` 식의 다양 한 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c8-111">The following examples show various uses of the `for...to` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5101.fs)]

<span data-ttu-id="ed6c8-112">위 코드는 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed6c8-112">The output of the previous code is as follows.</span></span>

```console
1 2 3 4 5 6 7 8 9 10
10 9 8 7 6 5 4 3 2 1
2 3 4 5 6 7 8 9 10 11 12 13 14 15 16 17 18
```

## <a name="see-also"></a><span data-ttu-id="ed6c8-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ed6c8-113">See also</span></span>

- [<span data-ttu-id="ed6c8-114">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="ed6c8-114">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="ed6c8-115">루프: `for...in` 식</span><span class="sxs-lookup"><span data-stu-id="ed6c8-115">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="ed6c8-116">루프: `while...do` 식</span><span class="sxs-lookup"><span data-stu-id="ed6c8-116">Loops: `while...do` Expression</span></span>](loops-while-do-expression.md)
