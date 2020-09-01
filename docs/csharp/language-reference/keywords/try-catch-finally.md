---
description: try-catch-finally - C# 참조
title: try-catch-finally - C# 참조
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 6e85330e12c53e0728ef671530709748090ebe02
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89142013"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="61703-103">try-catch-finally(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="61703-103">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="61703-104">`catch` 및 `finally`를 함께 사용하는 일반적인 경우는 `try` 블록에서 리소스를 얻어 사용하고, `catch` 블록에서 예외 상황을 처리하고, `finally` 블록에서 리소스를 해제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="61703-104">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="61703-105">예외를 다시 throw하는 방법에 대한 자세한 내용과 예제는 [try-catch](try-catch.md) 및 [예외 throw](../../../standard/exceptions/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61703-105">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="61703-106">`finally` 블록에 대한 자세한 내용은 [try-finally](try-finally.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61703-106">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="61703-107">예제</span><span class="sxs-lookup"><span data-stu-id="61703-107">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="61703-108">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="61703-108">C# language specification</span></span>

<span data-ttu-id="61703-109">자세한 내용은 [C# 언어 사양](~/_csharplang/spec/introduction.md)의 [try 문](~/_csharplang/spec/statements.md#the-try-statement) 섹션을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="61703-109">For more information, see [The try statement](~/_csharplang/spec/statements.md#the-try-statement) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="61703-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="61703-110">See also</span></span>

- [<span data-ttu-id="61703-111">C# 참조</span><span class="sxs-lookup"><span data-stu-id="61703-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="61703-112">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="61703-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="61703-113">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="61703-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="61703-114">try, throw 및 catch 문(C++)</span><span class="sxs-lookup"><span data-stu-id="61703-114">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="61703-115">throw</span><span class="sxs-lookup"><span data-stu-id="61703-115">throw</span></span>](throw.md)
- [<span data-ttu-id="61703-116">방법: 명시적으로 예외 Throw</span><span class="sxs-lookup"><span data-stu-id="61703-116">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="61703-117">using 문</span><span class="sxs-lookup"><span data-stu-id="61703-117">using Statement</span></span>](using-statement.md)
