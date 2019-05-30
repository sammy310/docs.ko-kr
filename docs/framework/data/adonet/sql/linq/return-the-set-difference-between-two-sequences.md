---
title: 두 시퀀스 간의 차집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 5bb7d797ad2adc4374f7a10c11d66be69feeb7a1
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/30/2019
ms.locfileid: "66380043"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="248a0-102">두 시퀀스 간의 차집합 반환</span><span class="sxs-lookup"><span data-stu-id="248a0-102">Return the Set Difference Between Two Sequences</span></span>
<span data-ttu-id="248a0-103"><xref:System.Linq.Queryable.Except%2A> 연산자를 사용하여 두 시퀀스 간의 차집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="248a0-103">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="248a0-104">예제</span><span class="sxs-lookup"><span data-stu-id="248a0-104">Example</span></span>  
 <span data-ttu-id="248a0-105">이 예제에서는 <xref:System.Linq.Queryable.Except%2A> 는 모든 국가/지역의 시퀀스를 반환 하도록 `Customers` 살지 않는 `Employees` live.</span><span class="sxs-lookup"><span data-stu-id="248a0-105">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="248a0-106">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Linq.Queryable.Except%2A> 작업은 집합에 대해서만 적절하게 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="248a0-106">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="248a0-107">다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="248a0-107">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="248a0-108">참고자료</span><span class="sxs-lookup"><span data-stu-id="248a0-108">See also</span></span>

- [<span data-ttu-id="248a0-109">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="248a0-109">Query Examples</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/query-examples.md)
- [<span data-ttu-id="248a0-110">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="248a0-110">Standard Query Operator Translation</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/standard-query-operator-translation.md)
