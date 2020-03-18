---
title: continue 문 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- continue_CSharpKeyword
- continue
helpviewer_keywords:
- continue keyword [C#]
ms.assetid: 8a5ac96f-f98a-4519-b32d-345847ed7be0
ms.openlocfilehash: 83b43b31eacf0ed835ee3d7a919538eb9f1dd1e8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "75713668"
---
# <a name="continue-c-reference"></a><span data-ttu-id="645b6-102">continue(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="645b6-102">continue (C# Reference)</span></span>

<span data-ttu-id="645b6-103">`continue` 문은 자신이 나타나는 바깥쪽 [while](./while.md), [do](./do.md), [for](./for.md) 또는 [foreach](./foreach-in.md) 문의 다음 반복으로 제어를 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="645b6-103">The `continue` statement passes control to the next iteration of the enclosing [while](./while.md), [do](./do.md), [for](./for.md), or [foreach](./foreach-in.md) statement in which it appears.</span></span>

## <a name="example"></a><span data-ttu-id="645b6-104">예제</span><span class="sxs-lookup"><span data-stu-id="645b6-104">Example</span></span>

<span data-ttu-id="645b6-105">이 예제에서 카운터는 1에서 10까지 계산하도록 초기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="645b6-105">In this example, a counter is initialized to count from 1 to 10.</span></span> <span data-ttu-id="645b6-106">`continue` 문을 `(i < 9)` 식과 함께 사용하면 `continue`와 `for` 본문의 끝 사이에 있는 문을 건너뜁니다.</span><span class="sxs-lookup"><span data-stu-id="645b6-106">By using the `continue` statement in conjunction with the expression `(i < 9)`, the statements between `continue` and the end of the `for` body are skipped.</span></span>

[!code-csharp[csrefKeywordsJump#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="645b6-107">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="645b6-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="645b6-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="645b6-108">See also</span></span>

- [<span data-ttu-id="645b6-109">C# 참조</span><span class="sxs-lookup"><span data-stu-id="645b6-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="645b6-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="645b6-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="645b6-111">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="645b6-111">C# Keywords</span></span>](./index.md)
- [<span data-ttu-id="645b6-112">break 문</span><span class="sxs-lookup"><span data-stu-id="645b6-112">break Statement</span></span>](/cpp/cpp/break-statement-cpp)
