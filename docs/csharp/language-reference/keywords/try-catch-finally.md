---
title: try-catch-finally - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- catch-finally_CSharpKeyword
- catch-finally
helpviewer_keywords:
- finally blocks [C#]
- try-catch statement [C#]
ms.assetid: a1b443b0-ff7a-43ab-b835-0cc9bfbd15ca
ms.openlocfilehash: 66f24994c7fcd2037887507bae65f590e4f90019
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65633873"
---
# <a name="try-catch-finally-c-reference"></a><span data-ttu-id="ce5e9-102">try-catch-finally(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="ce5e9-102">try-catch-finally (C# Reference)</span></span>

<span data-ttu-id="ce5e9-103">`catch` 및 `finally`를 함께 사용하는 일반적인 경우는 `try` 블록에서 리소스를 얻어 사용하고, `catch` 블록에서 예외 상황을 처리하고, `finally` 블록에서 리소스를 해제하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ce5e9-103">A common usage of `catch` and `finally` together is to obtain and use resources in a `try` block, deal with exceptional circumstances in a `catch` block, and release the resources in the `finally` block.</span></span>

 <span data-ttu-id="ce5e9-104">예외를 다시 throw하는 방법에 대한 자세한 내용과 예제는 [try-catch](try-catch.md) 및 [예외 throw](../../../standard/exceptions/index.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce5e9-104">For more information and examples on re-throwing exceptions, see [try-catch](try-catch.md) and [Throwing Exceptions](../../../standard/exceptions/index.md).</span></span> <span data-ttu-id="ce5e9-105">`finally` 블록에 대한 자세한 내용은 [try-finally](try-finally.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ce5e9-105">For more information about the `finally` block, see [try-finally](try-finally.md).</span></span>

## <a name="example"></a><span data-ttu-id="ce5e9-106">예제</span><span class="sxs-lookup"><span data-stu-id="ce5e9-106">Example</span></span>

[!code-csharp[csrefKeywordsExceptions#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsExceptions/CS/csrefKeywordsExceptions.cs#1)]  

## <a name="c-language-specification"></a><span data-ttu-id="ce5e9-107">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="ce5e9-107">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="ce5e9-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ce5e9-108">See also</span></span>

- [<span data-ttu-id="ce5e9-109">C# 참조</span><span class="sxs-lookup"><span data-stu-id="ce5e9-109">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="ce5e9-110">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="ce5e9-110">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="ce5e9-111">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="ce5e9-111">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="ce5e9-112">try, throw 및 catch 문(C++)</span><span class="sxs-lookup"><span data-stu-id="ce5e9-112">try, throw, and catch Statements (C++)</span></span>](/cpp/cpp/try-throw-and-catch-statements-cpp)
- [<span data-ttu-id="ce5e9-113">예외 처리 문</span><span class="sxs-lookup"><span data-stu-id="ce5e9-113">Exception Handling Statements</span></span>](exception-handling-statements.md)
- [<span data-ttu-id="ce5e9-114">throw</span><span class="sxs-lookup"><span data-stu-id="ce5e9-114">throw</span></span>](throw.md)
- [<span data-ttu-id="ce5e9-115">방법: 명시적으로 예외 Throw</span><span class="sxs-lookup"><span data-stu-id="ce5e9-115">How to: Explicitly Throw Exceptions</span></span>](../../../standard/exceptions/how-to-explicitly-throw-exceptions.md)
- [<span data-ttu-id="ce5e9-116">using 문</span><span class="sxs-lookup"><span data-stu-id="ce5e9-116">using Statement</span></span>](using-statement.md)
