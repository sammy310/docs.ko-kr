---
title: by 상황별 키워드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: 9f888f170f749eb5aac5cd39cd7c733920581542
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73422880"
---
# <a name="by-c-reference"></a><span data-ttu-id="31094-102">by(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="31094-102">by (C# Reference)</span></span>

<span data-ttu-id="31094-103">`by` 상황별 키워드는 쿼리 식의 `group` 절에서 사용되어 반환된 항목의 그룹화 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="31094-103">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="31094-104">자세한 내용은 [group 절](./group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="31094-104">For more information, see [group clause](./group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="31094-105">예</span><span class="sxs-lookup"><span data-stu-id="31094-105">Example</span></span>

<span data-ttu-id="31094-106">다음 예제에서는 `group` 절에 `by` 상황별 키워드를 사용하여 각 학생의 성에서 첫 번째 문자에 따라 학생들을 그룹화하도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="31094-106">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="31094-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="31094-107">See also</span></span>

- [<span data-ttu-id="31094-108">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="31094-108">LINQ in C#</span></span>](../../linq/index.md)
