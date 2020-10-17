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
ms.openlocfilehash: 6c70934c3b861e1a1433e5c0b95bb32e9d717c53
ms.sourcegitcommit: eb7e87496f42361b1da98562dd75b516c9d58bbc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/09/2020
ms.locfileid: "91877654"
---
# <a name="continue-c-reference"></a><span data-ttu-id="02c86-103">continue(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="02c86-103">continue (C# Reference)</span></span>

<span data-ttu-id="02c86-104">`continue` 문은 자신이 나타나는 바깥쪽 [while](./while.md), [do](./do.md), [for](./for.md) 또는 [foreach](./foreach-in.md) 문의 다음 반복으로 제어를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="02c86-104">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="02c86-105">예제</span><span class="sxs-lookup"><span data-stu-id="02c86-105">Example</span></span>

<span data-ttu-id="02c86-106">이 예제에서 카운터는 1에서 10까지 계산하도록 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="02c86-106">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="02c86-107">`continue` 문을 `(i < 9)` 식과 함께 사용하면 `i`가 9보다 작은 반복에서 `continue`와 `for` 본문 끝 사이에 있는 문을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="02c86-107">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped in the iterations where `i` is less than 9.</span></span> <span data-ttu-id="02c86-108">`for` 루프의 마지막 두 반복(i == 9 및 i == 10)에서는 `continue` 문이 실행되지 않고 `i` 값이 콘솔에 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="02c86-108">In the last two iterations of the `for` loop (where i == 9 and i == 10), the `continue` statement is not executed and the value of `i` is printed to the console.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="02c86-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="02c86-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="02c86-110">참조</span><span class="sxs-lookup"><span data-stu-id="02c86-110">See also</span></span>

- [<span data-ttu-id="02c86-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="02c86-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="02c86-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="02c86-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="02c86-113">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="02c86-113">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="02c86-114">break 문</span><span class="sxs-lookup"><span data-stu-id="02c86-114">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
