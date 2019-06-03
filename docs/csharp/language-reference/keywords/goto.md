---
title: goto 문 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- goto_CSharpKeyword
- goto
helpviewer_keywords:
- goto keyword [C#]
ms.assetid: 2c03c9c1-8119-44ef-b740-fb3d287a42fe
ms.openlocfilehash: 675893f02a0022b403d2afc018d24d6f826b8f75
ms.sourcegitcommit: 10986410e59ff29f2ec55c6759bde3eb4d1a00cb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/31/2019
ms.locfileid: "66421810"
---
# <a name="goto-c-reference"></a><span data-ttu-id="f1d94-102">goto(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="f1d94-102">goto (C# Reference)</span></span>

<span data-ttu-id="f1d94-103">`goto` 문은 레이블 지정된 문으로 직접 프로그램 컨트롤을 전송합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d94-103">The `goto` statement transfers the program control directly to a labeled statement.</span></span>

<span data-ttu-id="f1d94-104">`goto`는 일반적으로 `switch` 문에서 switch-case 레이블 또는 기본 레이블로 컨트롤을 전송하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f1d94-104">A common use of `goto` is to transfer control to a specific switch-case label or the default label in a `switch` statement.</span></span>

<span data-ttu-id="f1d94-105">`goto` 문은 많이 중첩된 루프를 회피하는 데도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f1d94-105">The `goto` statement is also useful to get out of deeply nested loops.</span></span>

## <a name="example"></a><span data-ttu-id="f1d94-106">예제</span><span class="sxs-lookup"><span data-stu-id="f1d94-106">Example</span></span>

<span data-ttu-id="f1d94-107">다음 예제에서는 [switch](switch.md) 문에서 `goto`의 사용 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1d94-107">The following example demonstrates using `goto` in a [switch](switch.md) statement.</span></span>

[!code-csharp[csrefKeywordsJump#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#4)]

## <a name="example"></a><span data-ttu-id="f1d94-108">예제</span><span class="sxs-lookup"><span data-stu-id="f1d94-108">Example</span></span>

<span data-ttu-id="f1d94-109">다음 예제에서는 `goto`를 사용하여 중첩된 루프에서 벗어나는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f1d94-109">The following example demonstrates using `goto` to break out from nested loops.</span></span>

[!code-csharp[csrefKeywordsJump#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="f1d94-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="f1d94-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="f1d94-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f1d94-111">See also</span></span>

- [<span data-ttu-id="f1d94-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="f1d94-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="f1d94-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f1d94-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="f1d94-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="f1d94-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="f1d94-115">goto 문(C++)</span><span class="sxs-lookup"><span data-stu-id="f1d94-115">goto Statement (C++)</span></span>](/cpp/cpp/goto-statement-cpp)
