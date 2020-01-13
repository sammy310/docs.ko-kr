---
title: return 문 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: 116bad7a1f9f61311d287c575b52547d63c9e1c0
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713133"
---
# <a name="return-c-reference"></a><span data-ttu-id="ba5ad-102">return(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ba5ad-102">return (C# Reference)</span></span>

<span data-ttu-id="ba5ad-103">`return` 문은 해당 문이 나타나는 메서드의 실행을 종료하고 제어를 호출 메서드로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="ba5ad-104">선택적 값을 반환할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-104">It can also return an optional value.</span></span> <span data-ttu-id="ba5ad-105">메서드가 `void` 형식인 경우 `return` 문을 생략할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="ba5ad-106">return 문이 `try` 블록 안에 있으면 `finally` 블록(있는 경우)은 제어가 호출 메서드로 반환되기 전에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="ba5ad-107">예제</span><span class="sxs-lookup"><span data-stu-id="ba5ad-107">Example</span></span>

 <span data-ttu-id="ba5ad-108">다음 예제에서 `CalculateArea()` 메서드는 `area` 로컬 변수를 `double` 값으로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="ba5ad-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="ba5ad-109">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ba5ad-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ba5ad-110">참조</span><span class="sxs-lookup"><span data-stu-id="ba5ad-110">See also</span></span>

- [<span data-ttu-id="ba5ad-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="ba5ad-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ba5ad-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ba5ad-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ba5ad-113">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="ba5ad-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ba5ad-114">return 문</span><span class="sxs-lookup"><span data-stu-id="ba5ad-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
