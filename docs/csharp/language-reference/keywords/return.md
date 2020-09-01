---
description: return 문 - C# 참조
title: return 문 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 486db846304c0972942ff58f3d5b276083681abe
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89137005"
---
# <a name="return-c-reference"></a><span data-ttu-id="8b630-103">return(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="8b630-103">return (C# Reference)</span></span>

<span data-ttu-id="8b630-104">`return` 문은 해당 문이 나타나는 메서드의 실행을 종료하고 제어를 호출 메서드로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8b630-104">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="8b630-105">선택적 값을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b630-105">It can also return an optional value.</span></span> <span data-ttu-id="8b630-106">메서드가 `void` 형식인 경우 `return` 문을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b630-106">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="8b630-107">return 문이 `try` 블록 안에 있으면 `finally` 블록(있는 경우)은 제어가 호출 메서드로 반환되기 전에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="8b630-107">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="8b630-108">예제</span><span class="sxs-lookup"><span data-stu-id="8b630-108">Example</span></span>

 <span data-ttu-id="8b630-109">다음 예제에서 `CalculateArea()` 메서드는 `area` 로컬 변수를 `double` 값으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="8b630-109">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="8b630-110">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="8b630-110">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="8b630-111">참조</span><span class="sxs-lookup"><span data-stu-id="8b630-111">See also</span></span>

- [<span data-ttu-id="8b630-112">C# 참조</span><span class="sxs-lookup"><span data-stu-id="8b630-112">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="8b630-113">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="8b630-113">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="8b630-114">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="8b630-114">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="8b630-115">return 문</span><span class="sxs-lookup"><span data-stu-id="8b630-115">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
