---
title: '루프: while...do 식'
description: 참조 하는 방법을... 하는 동안 수행 식은 지정된 된 테스트 조건이 참인 동안 반복 실행 (루프)를 수행 하는데 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: 5823ace27348ff4d4397a726bf2254f8fa0ee09b
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641826"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="bb04a-103">루프: while...do 식</span><span class="sxs-lookup"><span data-stu-id="bb04a-103">Loops: while...do Expression</span></span>

<span data-ttu-id="bb04a-104">`while...do` 식은 지정된 된 테스트 조건이 참인 동안 반복 실행 (루프)를 수행 하는데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb04a-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb04a-105">구문</span><span class="sxs-lookup"><span data-stu-id="bb04a-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="bb04a-106">설명</span><span class="sxs-lookup"><span data-stu-id="bb04a-106">Remarks</span></span>

<span data-ttu-id="bb04a-107">*테스트 식* 를 평가 합니다;이 경우 `true`, *식 본문* 실행 테스트 식을 다시 계산 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb04a-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="bb04a-108">합니다 *식 본문* 형식이 있어야 `unit`합니다.</span><span class="sxs-lookup"><span data-stu-id="bb04a-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="bb04a-109">테스트 식이 `false`, 반복 종료 합니다.</span><span class="sxs-lookup"><span data-stu-id="bb04a-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="bb04a-110">다음 예제를 사용 하 여 `while...do` 식입니다.</span><span class="sxs-lookup"><span data-stu-id="bb04a-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](../../../samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="bb04a-111">이전 코드의 출력은 1에서 20 사이의 난수는 마지막은 10 스트림입니다.</span><span class="sxs-lookup"><span data-stu-id="bb04a-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="bb04a-112">사용할 수 있습니다 `while...do` 시퀀스 식 및 기타 계산 식, 사용자 지정된 버전의 경우는 `while...do` 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bb04a-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="bb04a-113">자세한 내용은 [시퀀스](sequences.md)를 [비동기 워크플로](asynchronous-workflows.md), 및 [계산 식](computation-expressions.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bb04a-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="bb04a-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="bb04a-114">See also</span></span>

- [<span data-ttu-id="bb04a-115">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="bb04a-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="bb04a-116">루프: `for...in` Expression</span><span class="sxs-lookup"><span data-stu-id="bb04a-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="bb04a-117">루프: `for...to` Expression</span><span class="sxs-lookup"><span data-stu-id="bb04a-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
