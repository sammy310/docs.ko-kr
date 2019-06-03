---
title: break 문 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- break
- break_CSharpKeyword
helpviewer_keywords:
- break keyword [C#]
ms.assetid: be2571ed-efb0-4965-b122-81e5b09db0b9
ms.openlocfilehash: 15b193d9f294c01826b6b60587678ad76248e976
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66422067"
---
# <a name="break-c-reference"></a><span data-ttu-id="e29b3-102">break(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="e29b3-102">break (C# Reference)</span></span>

<span data-ttu-id="e29b3-103">`break` 문은 배치된 지점에서 가장 가까운 바깥쪽 루프 또는 [switch](../../../csharp/language-reference/keywords/switch.md) 문을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b3-103">The `break` statement terminates the closest enclosing loop or [switch](../../../csharp/language-reference/keywords/switch.md) statement in which it appears.</span></span> <span data-ttu-id="e29b3-104">제어는 종료된 문 뒤의 문으로 전달됩니다(있는 경우).</span><span class="sxs-lookup"><span data-stu-id="e29b3-104">Control is passed to the statement that follows the terminated statement, if any.</span></span>

## <a name="example"></a><span data-ttu-id="e29b3-105">예제</span><span class="sxs-lookup"><span data-stu-id="e29b3-105">Example</span></span>

<span data-ttu-id="e29b3-106">이 예제의 조건문에는 1부터 100까지 개수를 계산하는 카운터가 포함되지만 `break` 문은 4회 계산 후에 루프를 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="e29b3-106">In this example, the conditional statement contains a counter that is supposed to count from 1 to 100; however, the `break` statement terminates the loop after 4 counts.</span></span>

[!code-csharp[csrefKeywordsJump#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#1)]

## <a name="example"></a><span data-ttu-id="e29b3-107">예제</span><span class="sxs-lookup"><span data-stu-id="e29b3-107">Example</span></span>

<span data-ttu-id="e29b3-108">이 예제에서 `break` 문은 내부 중첩 루프를 중단하고 제어를 외부 루프에 반환하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="e29b3-108">In this example, the `break` statement is used to break out of an inner nested loop, and return control to the outer loop.</span></span>

[!code-csharp[csrefKeywordsJump#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#7)]

## <a name="example"></a><span data-ttu-id="e29b3-109">예제</span><span class="sxs-lookup"><span data-stu-id="e29b3-109">Example</span></span>

<span data-ttu-id="e29b3-110">이 예제에서는 [switch](../../../csharp/language-reference/keywords/switch.md) 문에서 `break`의 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e29b3-110">This example demonstrates the use of `break` in a [switch](../../../csharp/language-reference/keywords/switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#2)]

<span data-ttu-id="e29b3-111">`4`를 입력하면 다음과 같이 출력됩니다.</span><span class="sxs-lookup"><span data-stu-id="e29b3-111">If you entered `4`, the output would be:</span></span>

```console
Enter your selection (1, 2, or 3): 4
Sorry, invalid selection.
```

## <a name="c-language-specification"></a><span data-ttu-id="e29b3-112">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="e29b3-112">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="e29b3-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e29b3-113">See also</span></span>

- [<span data-ttu-id="e29b3-114">C# 참조</span><span class="sxs-lookup"><span data-stu-id="e29b3-114">C# Reference</span></span>](../../../csharp/language-reference/index.md)
- [<span data-ttu-id="e29b3-115">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="e29b3-115">C# Programming Guide</span></span>](../../../csharp/programming-guide/index.md)
- [<span data-ttu-id="e29b3-116">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="e29b3-116">C# Keywords</span></span>](../../../csharp/language-reference/keywords/index.md)
- [<span data-ttu-id="e29b3-117">switch</span><span class="sxs-lookup"><span data-stu-id="e29b3-117">switch</span></span>](../../../csharp/language-reference/keywords/switch.md)
