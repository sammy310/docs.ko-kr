---
title: 메서드에서 쿼리 반환
description: 쿼리를 반환하는 방법.
ms.date: 11/30/2016
ms.assetid: db220f79-c35b-41f2-886c-cd068672d42d
ms.openlocfilehash: 646e771d637aa242231e3fe216d4a856bb156649
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203334"
---
# <a name="how-to-return-a-query-from-a-method-c-programming-guide"></a><span data-ttu-id="bda2f-103">메서드에서 쿼리를 반환하는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="bda2f-103">How to return a query from a method (C# Programming Guide)</span></span>

<span data-ttu-id="bda2f-104">이 예제는 메서드에서 반환 값 및 `out` 매개 변수로서 쿼리를 반환하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bda2f-104">This example shows how to return a query from a method as the return value and as an `out` parameter.</span></span>  
  
 <span data-ttu-id="bda2f-105">쿼리 개체는 구성 가능하므로 메서드에서 쿼리를 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda2f-105">Query objects are composable, meaning that you can return a query from a method.</span></span> <span data-ttu-id="bda2f-106">쿼리를 나타내는 개체는 결과 컬렉션을 저장하지 않고, 대신 필요할 때 결과를 생성하는 단계를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2f-106">Objects that represent queries do not store the resulting collection, but rather the steps to produce the results when needed.</span></span> <span data-ttu-id="bda2f-107">메서드에서 쿼리 개체를 반환하는 경우 메서드를 추가로 작성하거나 수정할 수 있다는 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bda2f-107">The advantage of returning query objects from methods is that they can be further composed or modified.</span></span> <span data-ttu-id="bda2f-108">따라서 쿼리를 반환하는 메서드의 반환 값 또는 `out` 매개 변수도 해당 형식을 가지고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2f-108">Therefore any return value or `out` parameter of a method that returns a query must also have that type.</span></span> <span data-ttu-id="bda2f-109">메서드가 쿼리를 구체적인 <xref:System.Collections.Generic.List%601> 또는 <xref:System.Array> 형식으로 구체화하는 경우 쿼리 자체가 아니라 쿼리 결과를 반환하는 것으로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda2f-109">If a method materializes a query into a concrete <xref:System.Collections.Generic.List%601> or <xref:System.Array> type, it is considered to be returning the query results instead of the query itself.</span></span> <span data-ttu-id="bda2f-110">메서드에서 반환되는 쿼리 변수는 여전히 구성 또는 수정 가능합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2f-110">A query variable that is returned from a method can still be composed or modified.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bda2f-111">예제</span><span class="sxs-lookup"><span data-stu-id="bda2f-111">Example</span></span>  

 <span data-ttu-id="bda2f-112">다음 예제에서 첫 번째 메서드는 쿼리를 반환 값으로 반환하고 두 번째 메서드는 쿼리를 `out` 매개 변수로 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="bda2f-112">In the following example, the first method returns a query as a return value, and the second method returns a query as an `out` parameter.</span></span> <span data-ttu-id="bda2f-113">두 경우 모두 쿼리 결과가 아니라 쿼리가 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="bda2f-113">Note that in both cases it is a query that is  returned, not query results.</span></span>  
  
 [!code-csharp[csProgGuideLINQ#80](~/samples/snippets/csharp/concepts/linq/how-to-return-a-query-from-a-method_1.cs)]  

## <a name="see-also"></a><span data-ttu-id="bda2f-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bda2f-114">See also</span></span>

- [<span data-ttu-id="bda2f-115">LINQ(Language-Integrated Query)</span><span class="sxs-lookup"><span data-stu-id="bda2f-115">Language Integrated Query (LINQ)</span></span>](index.md)
