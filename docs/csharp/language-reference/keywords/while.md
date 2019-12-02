---
title: while - C# 참조
ms.custom: seodec18
ms.date: 05/28/2018
f1_keywords:
- while_CSharpKeyword
- while
helpviewer_keywords:
- while keyword [C#]
ms.assetid: 72a0765c-6852-4aca-b327-4a11cb7f5c59
ms.openlocfilehash: fad0ceae9cf1080e7f4b553e0808fd531fd28c57
ms.sourcegitcommit: 93762e1a0dae1b5f64d82eebb7b705a6d566d839
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/27/2019
ms.locfileid: "74552388"
---
# <a name="while-c-reference"></a><span data-ttu-id="1c457-102">while(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="1c457-102">while (C# Reference)</span></span>

<span data-ttu-id="1c457-103">`while` 문은 지정된 부울 식이 `true`로 계산되는 동안 문 또는 문 블록을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-103">The `while` statement executes a statement or a block of statements while a specified Boolean expression evaluates to `true`.</span></span> <span data-ttu-id="1c457-104">이 식은 각 루프를 실행하기 전에 평가되기 때문에 `while` 루프는 0번 이상 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-104">Because that expression is evaluated before each execution of the loop, a `while` loop executes zero or more times.</span></span> <span data-ttu-id="1c457-105">이는 한 번 이상 실행되는 [do](do.md) 루프와 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-105">This differs from the [do](do.md) loop, which executes one or more times.</span></span>

<span data-ttu-id="1c457-106">`while` 문 블록 내의 어느 지점에서나 [break](break.md) 문을 사용하여 루프를 중단할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-106">At any point within the `while` statement block, you can break out of the loop by using the [break](break.md) statement.</span></span>

<span data-ttu-id="1c457-107">[continue](continue.md) 문을 사용하여 `while` 식의 계산을 직접 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-107">You can step directly to the evaluation of the `while` expression by using the [continue](continue.md) statement.</span></span> <span data-ttu-id="1c457-108">식이 `true`로 계산될 경우 루프의 첫 번째 문에서 계속 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-108">If the expression evaluates to `true`, execution continues at the first statement in the loop.</span></span> <span data-ttu-id="1c457-109">그렇지 않으면 실행은 루프 뒤에 나오는 첫 번째 문에서 계속됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-109">Otherwise, execution continues at the first statement after the loop.</span></span>

<span data-ttu-id="1c457-110">[goto](goto.md), [return](return.md) 또는 [throw](throw.md) 문으로 `while` 루프를 종료할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-110">You also can exit a `while` loop by the [goto](goto.md), [return](return.md), or [throw](throw.md) statements.</span></span>

## <a name="example"></a><span data-ttu-id="1c457-111">예</span><span class="sxs-lookup"><span data-stu-id="1c457-111">Example</span></span>

<span data-ttu-id="1c457-112">다음 예제에서는 `while` 문의 사용법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-112">The following example shows the usage of the `while` statement.</span></span> <span data-ttu-id="1c457-113">**Run**을 선택하여 예제 코드를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-113">Select **Run** to run the example code.</span></span> <span data-ttu-id="1c457-114">그런 다음, 코드를 수정하고 다시 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1c457-114">After that you can modify the code and run it again.</span></span>

[!code-csharp-interactive[while loop example](~/samples/snippets/csharp/keywords/IterationKeywordsExamples.cs#3)]

## <a name="c-language-specification"></a><span data-ttu-id="1c457-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="1c457-115">C# language specification</span></span>

<span data-ttu-id="1c457-116">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [while 문](~/_csharplang/spec/statements.md#the-while-statement) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c457-116">For more information, see [The while statement](~/_csharplang/spec/statements.md#the-while-statement) section of the [C# language specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span>

## <a name="see-also"></a><span data-ttu-id="1c457-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c457-117">See also</span></span>

- [<span data-ttu-id="1c457-118">C# 참조</span><span class="sxs-lookup"><span data-stu-id="1c457-118">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="1c457-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="1c457-119">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="1c457-120">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="1c457-120">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="1c457-121">do 문</span><span class="sxs-lookup"><span data-stu-id="1c457-121">do statement</span></span>](do.md)
