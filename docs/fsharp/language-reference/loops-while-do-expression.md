---
title: '루프: while...do 식'
description: 잠시 시간을 확인 하세요. do 식은 지정 된 테스트 조건이 true 인 동안 반복 실행 (반복)을 수행 하는 데 사용 됩니다.
ms.date: 05/16/2016
ms.openlocfilehash: f05bdd9f8f4b9446d59f68e1231fb75e18e9b526
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68630758"
---
# <a name="loops-whiledo-expression"></a><span data-ttu-id="2b138-103">루프: while...do 식</span><span class="sxs-lookup"><span data-stu-id="2b138-103">Loops: while...do Expression</span></span>

<span data-ttu-id="2b138-104">`while...do` 식은 지정 된 테스트 조건이 true 인 동안 반복 실행 (반복)을 수행 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b138-104">The `while...do` expression is used to perform iterative execution (looping) while a specified test condition is true.</span></span>

## <a name="syntax"></a><span data-ttu-id="2b138-105">구문</span><span class="sxs-lookup"><span data-stu-id="2b138-105">Syntax</span></span>

```fsharp
while test-expression do
    body-expression
```

## <a name="remarks"></a><span data-ttu-id="2b138-106">설명</span><span class="sxs-lookup"><span data-stu-id="2b138-106">Remarks</span></span>

<span data-ttu-id="2b138-107">*테스트 식이* 계산 됩니다. 이면 본문 식이 실행 되 고 테스트 식이 다시 계산 됩니다. `true`</span><span class="sxs-lookup"><span data-stu-id="2b138-107">The *test-expression* is evaluated; if it is `true`, the *body-expression* is executed and the test expression is evaluated again.</span></span> <span data-ttu-id="2b138-108">*본문 식* 에는 형식이 `unit`있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b138-108">The *body-expression* must have type `unit`.</span></span> <span data-ttu-id="2b138-109">테스트 식이 이면 반복이 `false`종료 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b138-109">If the test expression is `false`, the iteration ends.</span></span>

<span data-ttu-id="2b138-110">다음 예에서는 `while...do` 식을 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2b138-110">The following example illustrates the use of the `while...do` expression.</span></span>

[!code-fsharp[Main](~/samples/snippets/fsharp/lang-ref-2/snippet5301.fs)]

<span data-ttu-id="2b138-111">이전 코드의 출력은 1에서 20 사이의 난수 스트림으로, 마지막 값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="2b138-111">The output of the previous code is a stream of random numbers between 1 and 20, the last of which is 10.</span></span>

```
13 19 8 18 16 2 10
Found a 10!
```

> [!NOTE]
> <span data-ttu-id="2b138-112">시퀀스 식과 `while...do` 기타 계산 식에를 사용할 수 있습니다 .이 경우 사용자 지정 된 버전 `while...do` 의 식이 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b138-112">You can use `while...do` in sequence expressions and other computation expressions, in which case a customized version of the `while...do` expression is used.</span></span> <span data-ttu-id="2b138-113">자세한 내용은 [시퀀스](sequences.md), [비동기 워크플로](asynchronous-workflows.md)및 [계산 식](computation-expressions.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2b138-113">For more information, see [Sequences](sequences.md), [Asynchronous Workflows](asynchronous-workflows.md), and [Computation Expressions](computation-expressions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="2b138-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2b138-114">See also</span></span>

- [<span data-ttu-id="2b138-115">F# 언어 참조</span><span class="sxs-lookup"><span data-stu-id="2b138-115">F# Language Reference</span></span>](index.md)
- [<span data-ttu-id="2b138-116">하며 `for...in`식</span><span class="sxs-lookup"><span data-stu-id="2b138-116">Loops: `for...in` Expression</span></span>](loops-for-in-expression.md)
- [<span data-ttu-id="2b138-117">하며 `for...to`식</span><span class="sxs-lookup"><span data-stu-id="2b138-117">Loops: `for...to` Expression</span></span>](loops-for-to-expression.md)
