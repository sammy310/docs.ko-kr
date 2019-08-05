---
title: global 상황별 키워드 - C# 참조
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- global
- global_CSharpKeyword
helpviewer_keywords:
- global keyword [C#]
ms.assetid: 8932c16a-6959-42c2-86e7-2c4221ab788b
ms.openlocfilehash: 9a8c7b5134cc29668aae53e8a3f86ddae4c8263a
ms.sourcegitcommit: f20dd18dbcf2275513281f5d9ad7ece6a62644b4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/30/2019
ms.locfileid: "68627689"
---
# <a name="global-c-reference"></a><span data-ttu-id="533e7-102">global(C# 참조)</span><span class="sxs-lookup"><span data-stu-id="533e7-102">global (C# Reference)</span></span>

<span data-ttu-id="533e7-103">`global` 상황별 키워드가 [:: 연산자](../operators/namespace-alias-qualifier.md) 앞에 배치되는 경우, 이 키워드는 전역 네임스페이스를 가리킵니다. 이는 모든 C# 프로그램의 기본 네임스페이스이며 다른 경우에는 명명되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="533e7-103">The `global` contextual keyword, when it comes before the [:: operator](../operators/namespace-alias-qualifier.md), refers to the global namespace, which is the default namespace for any C# program and is otherwise unnamed.</span></span> <span data-ttu-id="533e7-104">자세한 내용은 [방법: 전역 네임스페이스 별칭 사용](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="533e7-104">For more information, see [How to: Use the Global Namespace Alias](../../programming-guide/namespaces/how-to-use-the-global-namespace-alias.md).</span></span>

## <a name="example"></a><span data-ttu-id="533e7-105">예</span><span class="sxs-lookup"><span data-stu-id="533e7-105">Example</span></span>

<span data-ttu-id="533e7-106">다음 예제에서는 `global` 상황별 키워드를 사용하여 `TestApp` 클래스가 전역 네임스페이스에 정의되도록 지정하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="533e7-106">The following example shows how to use the `global` contextual keyword to specify that the class `TestApp` is defined in the global namespace:</span></span>

[!code-csharp[csrefKeywordsContextual#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsContextual/CS/csrefKeywordsContextual.cs#13)]

## <a name="see-also"></a><span data-ttu-id="533e7-107">참고 항목</span><span class="sxs-lookup"><span data-stu-id="533e7-107">See also</span></span>

- [<span data-ttu-id="533e7-108">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="533e7-108">Namespaces</span></span>](../../programming-guide/namespaces/index.md)
