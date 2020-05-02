---
title: 매개 변수 배열의 params 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- params_CSharpKeyword
- params
helpviewer_keywords:
- parameters [C#], params
- params keyword [C#]
- parameter array
ms.assetid: 1690815e-b52b-4967-8380-5780aff08012
ms.openlocfilehash: 77d7fd19ff57f80f401191027e2fae95026e1966
ms.sourcegitcommit: 465547886a1224a5435c3ac349c805e39ce77706
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2020
ms.locfileid: "81738839"
---
# <a name="params-c-reference"></a><span data-ttu-id="39181-102">params(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="39181-102">params (C# Reference)</span></span>

<span data-ttu-id="39181-103">`params` 키워드를 사용하면 가변 개수의 인수를 사용하는 [메서드 매개 변수](method-parameters.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39181-103">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="39181-104">매개 변수 배열은 1차원 배열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="39181-104">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="39181-105">메서드 선언에서 `params` 키워드 뒤에는 추가 매개 변수가 허용되지 않으며, `params` 키워드 하나만 메서드 선언에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39181-105">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="39181-106">`params` 매개 변수의 선언된 형식이 1차원 배열이 아닌 경우 컴파일러 오류 [CS0225](../../misc/cs0225.md)가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="39181-106">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="39181-107">`params` 매개 변수를 사용하여 메서드를 호출하면 다음을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="39181-107">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="39181-108">배열 요소 형식의 쉼표로 구분된 인수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="39181-108">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="39181-109">지정된 형식의 인수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="39181-109">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="39181-110">인수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="39181-110">No arguments.</span></span> <span data-ttu-id="39181-111">인수를 보내지 않는 경우 `params` 목록의 길이는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="39181-111">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="39181-112">예제</span><span class="sxs-lookup"><span data-stu-id="39181-112">Example</span></span>

<span data-ttu-id="39181-113">다음 예제에서는 `params` 매개 변수에 인수를 보낼 수 있는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="39181-113">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="39181-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="39181-114">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="39181-115">참조</span><span class="sxs-lookup"><span data-stu-id="39181-115">See also</span></span>

- [<span data-ttu-id="39181-116">C# 참조</span><span class="sxs-lookup"><span data-stu-id="39181-116">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="39181-117">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="39181-117">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="39181-118">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="39181-118">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="39181-119">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="39181-119">Method Parameters</span></span>](method-parameters.md)
