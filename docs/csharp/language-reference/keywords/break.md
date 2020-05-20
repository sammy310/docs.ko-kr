---
title: break 문 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: ef276fd9e8da0ea25695c5afdf06a300bbd2a123
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713759"
---
# <a name="break-c-reference"></a><span data-ttu-id="2c24d-102">break(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="2c24d-102">break (C# Reference)</span></span>

<span data-ttu-id="2c24d-103">`break` 문은 배치된 지점에서 가장 가까운 바깥쪽 루프 또는 [switch](./switch.md) 문을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2c24d-103">The `break` statement terminates the closest enclosing loop or [switch](./switch.md) statement in which it appears.</span></span> <span data-ttu-id="2c24d-104">제어는 종료된 문 뒤의 문으로 전달됩니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="2c24d-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="2c24d-105">예제</span><span class="sxs-lookup"><span data-stu-id="2c24d-105">Example</span></span>

<span data-ttu-id="2c24d-106">이 예제의 조건문에는 1부터 100까지 개수를 계산하는 카운터가 포함되지만 `break` 문은 4회 계산 후에 루프를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="2c24d-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="2c24d-107">예제</span><span class="sxs-lookup"><span data-stu-id="2c24d-107">Example</span></span>

<span data-ttu-id="2c24d-108">이 예제에서는 [switch](./switch.md) 문에서 `break`의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2c24d-108">This example demonstrates the use of `break` in a [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="2c24d-109">`4`를 입력하면 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c24d-109">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="example"></a><span data-ttu-id="2c24d-110">예제</span><span class="sxs-lookup"><span data-stu-id="2c24d-110">Example</span></span>

<span data-ttu-id="2c24d-111">이 예제에서 `break` 문은 내부 중첩 루프를 중단하고 제어를 외부 루프에 반환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c24d-111">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span> <span data-ttu-id="2c24d-112">컨트롤은 중첩된 루프에서 _오직_ 반환된 한 레벨 업입니다.</span><span class="sxs-lookup"><span data-stu-id="2c24d-112">Control is _only_ returned one level up in the nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="2c24d-113">예제</span><span class="sxs-lookup"><span data-stu-id="2c24d-113">Example</span></span>

<span data-ttu-id="2c24d-114">이 예제에서 `break` 문은 루프의 각 반복 중에 현재 분기를 중단하는 데만 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c24d-114">In this example, the `break` statement is only used to break out of the current branch during each iteration of the loop.</span></span> <span data-ttu-id="2c24d-115">루프 자체는 중첩된 [switch](./switch.md) 문에 속하는 `break`의 인스턴스에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c24d-115">The loop itself is unaffected by the instances of `break` that belong to the nested [switch](./switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#8)]

## <a name="c-language-specification"></a><span data-ttu-id="2c24d-116">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="2c24d-116">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="2c24d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c24d-117">See also</span></span>

- [<span data-ttu-id="2c24d-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="2c24d-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="2c24d-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="2c24d-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="2c24d-120">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="2c24d-120">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="2c24d-121">switch</span><span class="sxs-lookup"><span data-stu-id="2c24d-121">switch</span></span>](./switch.md)
