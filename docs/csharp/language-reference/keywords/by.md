---
description: by 상황별 키워드 - C# 참조
title: by 상황별 키워드 - C# 참조
ms.date: 07/20/2015
f1_keywords:
- by
- by_CSharpKeyword
helpviewer_keywords:
- by keyword [C#]
ms.assetid: efe6f0e3-be40-4df2-a144-c7db968ae052
ms.openlocfilehash: 2bc62f6f7f9e8a6d434ea254d5b04e563c41bc26
ms.sourcegitcommit: d579fb5e4b46745fd0f1f8874c94c6469ce58604
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/30/2020
ms.locfileid: "89134694"
---
# <a name="by-c-reference"></a><span data-ttu-id="0669e-103">by(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="0669e-103">by (C# Reference)</span></span>

<span data-ttu-id="0669e-104">`by` 상황별 키워드는 쿼리 식의 `group` 절에서 사용되어 반환된 항목의 그룹화 방법을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0669e-104">The `by` contextual keyword is used in the `group` clause in a query expression to specify how the returned items should be grouped.</span></span> <span data-ttu-id="0669e-105">자세한 내용은 [group 절](./group-clause.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0669e-105">For more information, see [group clause](./group-clause.md).</span></span>

## <a name="example"></a><span data-ttu-id="0669e-106">예제</span><span class="sxs-lookup"><span data-stu-id="0669e-106">Example</span></span>

<span data-ttu-id="0669e-107">다음 예제에서는 `group` 절에 `by` 상황별 키워드를 사용하여 각 학생의 성에서 첫 번째 문자에 따라 학생들을 그룹화하도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0669e-107">The following example shows the use of the `by` contextual keyword in a `group` clause to specify that the students should be grouped according to the first letter of the last name of each student.</span></span>

[!code-csharp[csrefKeywordsContextual#10](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#10)]

## <a name="see-also"></a><span data-ttu-id="0669e-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0669e-108">See also</span></span>

- [<span data-ttu-id="0669e-109">C#의 LINQ</span><span class="sxs-lookup"><span data-stu-id="0669e-109">LINQ in C#</span></span>](../../linq/index.md)
