---
description: unchecked 키워드 - C# 참조
title: unchecked 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- unchecked_CSharpKeyword
- unchecked
helpviewer_keywords:
- unchecked keyword [C#]
ms.assetid: 0c021f7c-923f-4b3d-a58f-55336f5ac27e
ms.openlocfilehash: bb66639e3657b247b9ebcad1594daf1f57a5c76b
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89141987"
---
# <a name="unchecked-c-reference"></a><span data-ttu-id="69a92-103">unchecked(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="69a92-103">unchecked (C# Reference)</span></span>

<span data-ttu-id="69a92-104">`unchecked` 키워드는 정수 형식 산술 연산 및 변환에 대한 오버플로 검사를 비활성화하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a92-104">The `unchecked` keyword is used to suppress overflow-checking for integral-type arithmetic operations and conversions.</span></span>

<span data-ttu-id="69a92-105">unchecked 컨텍스트에서 식이 대상 형식의 범위를 벗어난 값을 생성하는 경우 오버플로에 플래그가 지정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69a92-105">In an unchecked context, if an expression produces a value that is outside the range of the destination type, the overflow is not flagged.</span></span> <span data-ttu-id="69a92-106">예를 들어 다음 예제의 계산은 `unchecked` 블록 또는 식에서 수행되므로 결과가 정수에 비해 너무 크다는 사실이 무시되며 `int1`에 -2,147,483,639 값이 할당됩니다.</span><span class="sxs-lookup"><span data-stu-id="69a92-106">For example, because the calculation in the following example is performed in an `unchecked` block or expression, the fact that the result is too large for an integer is ignored, and `int1` is assigned the value -2,147,483,639.</span></span>

[!code-csharp[csrefKeywordsChecked#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#5)]

<span data-ttu-id="69a92-107">`unchecked` 환경을 제거하면 컴파일 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="69a92-107">If the `unchecked` environment is removed, a compilation error occurs.</span></span> <span data-ttu-id="69a92-108">식의 모든 항이 상수이기 때문에 컴파일 시간에 오버플로가 검색될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a92-108">The overflow can be detected at compile time because all the terms of the expression are constants.</span></span>

<span data-ttu-id="69a92-109">상수가 아닌 항을 포함하는 식은 컴파일 시간 및 런타임에 기본적으로 확인되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="69a92-109">Expressions that contain non-constant terms are unchecked by default at compile time and run time.</span></span> <span data-ttu-id="69a92-110">checked 환경을 사용하도록 설정하는 방법에 대한 자세한 내용은 [checked](checked.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69a92-110">See [checked](checked.md) for information about enabling a checked environment.</span></span>

<span data-ttu-id="69a92-111">오버플로를 확인하는 데 시간이 걸리기 때문에 오버플로 위험이 없는 상황에서는 unchecked 코드를 사용하여 성능을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="69a92-111">Because checking for overflow takes time, the use of unchecked code in situations where there is no danger of overflow might improve performance.</span></span> <span data-ttu-id="69a92-112">그러나 오버플로가 발생할 가능성이 있는 경우 checked 환경을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="69a92-112">However, if overflow is a possibility, a checked environment should be used.</span></span>

## <a name="example"></a><span data-ttu-id="69a92-113">예제</span><span class="sxs-lookup"><span data-stu-id="69a92-113">Example</span></span>

<span data-ttu-id="69a92-114">이 샘플에서는 `unchecked` 키워드를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="69a92-114">This sample shows how to use the `unchecked` keyword.</span></span>

[!code-csharp[csrefKeywordsChecked#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsChecked/CS/csrefKeywordsChecked.cs#2)]

## <a name="c-language-specification"></a><span data-ttu-id="69a92-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="69a92-115">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="69a92-116">참조</span><span class="sxs-lookup"><span data-stu-id="69a92-116">See also</span></span>

- [<span data-ttu-id="69a92-117">C# 참조</span><span class="sxs-lookup"><span data-stu-id="69a92-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="69a92-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="69a92-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="69a92-119">C# 키워드</span><span class="sxs-lookup"><span data-stu-id="69a92-119">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="69a92-120">Checked 및 Unchecked</span><span class="sxs-lookup"><span data-stu-id="69a92-120">Checked and Unchecked</span></span>](checked-and-unchecked.md)
- [<span data-ttu-id="69a92-121">checked</span><span class="sxs-lookup"><span data-stu-id="69a92-121">checked</span></span>](checked.md)
