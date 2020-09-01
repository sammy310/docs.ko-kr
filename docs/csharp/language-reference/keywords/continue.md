---
description: continue 문 - C# 참조
title: continue 문 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 76578b0ad7e2b969609fbf50df1f9ab7de6e5097
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89128441"
---
# <a name="continue-c-reference"></a><span data-ttu-id="220a4-103">continue(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="220a4-103">continue (C# Reference)</span></span>

<span data-ttu-id="220a4-104">`continue` 문은 자신이 나타나는 바깥쪽 [while](./while.md), [do](./do.md), [for](./for.md) 또는 [foreach](./foreach-in.md) 문의 다음 반복으로 제어를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="220a4-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="220a4-105">예제</span><span class="sxs-lookup"><span data-stu-id="220a4-105">Example</span></span>

<span data-ttu-id="220a4-106">이 예제에서 카운터는 1에서 10까지 계산하도록 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="220a4-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="220a4-107">`continue` 문을 `(i < 9)` 식과 함께 사용하면 `continue`와 `for` 본문의 끝 사이에 있는 문을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="220a4-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="220a4-108">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="220a4-108">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="220a4-109">참조</span><span class="sxs-lookup"><span data-stu-id="220a4-109">See also</span></span>

- [<span data-ttu-id="220a4-110">C# 참조</span><span class="sxs-lookup"><span data-stu-id="220a4-110">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="220a4-111">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="220a4-111">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="220a4-112">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="220a4-112">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="220a4-113">break 문</span><span class="sxs-lookup"><span data-stu-id="220a4-113">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
