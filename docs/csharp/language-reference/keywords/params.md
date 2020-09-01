---
description: 매개 변수 배열의 params 키워드 - C# 참조
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
ms.openlocfilehash: a2726c725508cd297001aaabddeff414704d1115
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134473"
---
# <a name="params-c-reference"></a><span data-ttu-id="98397-103">params(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="98397-103">params (C# Reference)</span></span>

<span data-ttu-id="98397-104">`params` 키워드를 사용하면 가변 개수의 인수를 사용하는 [메서드 매개 변수](method-parameters.md)를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98397-104">By using the `params` keyword, you can specify a [method parameter](method-parameters.md) that takes a variable number of arguments.</span></span> <span data-ttu-id="98397-105">매개 변수 배열은 1차원 배열이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98397-105">The parameter type must be a single-dimensional array.</span></span>

<span data-ttu-id="98397-106">메서드 선언에서 `params` 키워드 뒤에는 추가 매개 변수가 허용되지 않으며, `params` 키워드 하나만 메서드 선언에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98397-106">No additional parameters are permitted after the `params` keyword in a method declaration, and only one `params` keyword is permitted in a method declaration.</span></span>

<span data-ttu-id="98397-107">`params` 매개 변수의 선언된 형식이 1차원 배열이 아닌 경우 컴파일러 오류 [CS0225](../../misc/cs0225.md)가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="98397-107">If the declared type of the `params` parameter is not a single-dimensional array, compiler error [CS0225](../../misc/cs0225.md) occurs.</span></span>

<span data-ttu-id="98397-108">`params` 매개 변수를 사용하여 메서드를 호출하면 다음을 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98397-108">When you call a method with a `params` parameter, you can pass in:</span></span>

- <span data-ttu-id="98397-109">배열 요소 형식의 쉼표로 구분된 인수 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="98397-109">A comma-separated list of arguments of the type of the array elements.</span></span>
- <span data-ttu-id="98397-110">지정된 형식의 인수 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="98397-110">An array of arguments of the specified type.</span></span>
- <span data-ttu-id="98397-111">인수가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="98397-111">No arguments.</span></span> <span data-ttu-id="98397-112">인수를 보내지 않는 경우 `params` 목록의 길이는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="98397-112">If you send no arguments, the length of the `params` list is zero.</span></span>

## <a name="example"></a><span data-ttu-id="98397-113">예제</span><span class="sxs-lookup"><span data-stu-id="98397-113">Example</span></span>

<span data-ttu-id="98397-114">다음 예제에서는 `params` 매개 변수에 인수를 보낼 수 있는 다양한 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="98397-114">The following example demonstrates various ways in which arguments can be sent to a `params` parameter.</span></span>

[!code-csharp[csrefKeywordsMethodParams#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsMethodParams/CS/csrefKeywordsMethodParams.cs#5)]

## <a name="c-language-specification"></a><span data-ttu-id="98397-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="98397-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="98397-116">참조</span><span class="sxs-lookup"><span data-stu-id="98397-116">See also</span></span>

- [<span data-ttu-id="98397-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="98397-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="98397-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="98397-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="98397-119">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="98397-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="98397-120">메서드 매개 변수</span><span class="sxs-lookup"><span data-stu-id="98397-120">Method Parameters</span></span>](method-parameters.md)
