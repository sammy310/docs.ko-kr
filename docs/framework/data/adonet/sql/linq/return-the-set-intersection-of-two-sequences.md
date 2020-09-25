---
title: 두 시퀀스의 교집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: d09c344e-3548-4944-a3ed-051880e3f5b8
ms.openlocfilehash: 421ec544345e41f910bf80c855a3a6b4de1c46a6
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91200227"
---
# <a name="return-the-set-intersection-of-two-sequences"></a><span data-ttu-id="4cfb0-102">두 시퀀스의 교집합 반환</span><span class="sxs-lookup"><span data-stu-id="4cfb0-102">Return the Set Intersection of Two Sequences</span></span>

<span data-ttu-id="4cfb0-103"><xref:System.Linq.Queryable.Intersect%2A> 연산자를 사용하여 두 시퀀스의 교집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-103">Use the <xref:System.Linq.Queryable.Intersect%2A> operator to return the set intersection of two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4cfb0-104">예제</span><span class="sxs-lookup"><span data-stu-id="4cfb0-104">Example</span></span>  

 <span data-ttu-id="4cfb0-105">이 예에서는 <xref:System.Linq.Queryable.Intersect%2A> 를 사용 하 여와 라이브 모두에 있는 모든 국가/지역의 시퀀스를 반환 합니다 `Customers` `Employees` .</span><span class="sxs-lookup"><span data-stu-id="4cfb0-105">This example uses <xref:System.Linq.Queryable.Intersect%2A> to return a sequence of all countries/regions in which both `Customers` and `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#42](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#42)]
 [!code-vb[DLinqQueryExamples#42](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#42)]  
  
 <span data-ttu-id="4cfb0-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Linq.Queryable.Intersect%2A> 작업은 집합에 대해서만 적절하게 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Intersect%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="4cfb0-107">다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4cfb0-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4cfb0-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4cfb0-108">See also</span></span>

- [<span data-ttu-id="4cfb0-109">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="4cfb0-109">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="4cfb0-110">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="4cfb0-110">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
