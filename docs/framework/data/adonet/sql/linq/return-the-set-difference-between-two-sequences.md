---
description: '자세한 정보: 두 시퀀스 간의 차집합 반환'
title: 두 시퀀스 간의 차집합 반환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 62efb546-c898-408f-af21-36e7c6fed217
ms.openlocfilehash: 6836195ac4e1ee678fd3e8089e7c341f7dd247e8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662986"
---
# <a name="return-the-set-difference-between-two-sequences"></a><span data-ttu-id="63fb0-103">두 시퀀스 간의 차집합 반환</span><span class="sxs-lookup"><span data-stu-id="63fb0-103">Return the Set Difference Between Two Sequences</span></span>

<span data-ttu-id="63fb0-104"><xref:System.Linq.Queryable.Except%2A> 연산자를 사용하여 두 시퀀스 간의 차집합을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="63fb0-104">Use the <xref:System.Linq.Queryable.Except%2A> operator to return the set difference between two sequences.</span></span>  
  
## <a name="example"></a><span data-ttu-id="63fb0-105">예제</span><span class="sxs-lookup"><span data-stu-id="63fb0-105">Example</span></span>  

 <span data-ttu-id="63fb0-106">이 예에서는 <xref:System.Linq.Queryable.Except%2A> 를 사용 하 여 살고 있지만 살고 있는 모든 국가/지역의 시퀀스를 반환 `Customers` `Employees` 합니다.</span><span class="sxs-lookup"><span data-stu-id="63fb0-106">This example uses <xref:System.Linq.Queryable.Except%2A> to return a sequence of all countries/regions in which `Customers` live but in which no `Employees` live.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#41](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#41)]
 [!code-vb[DLinqQueryExamples#41](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#41)]  
  
 <span data-ttu-id="63fb0-107">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]에서 <xref:System.Linq.Queryable.Except%2A> 작업은 집합에 대해서만 적절하게 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63fb0-107">In [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], the <xref:System.Linq.Queryable.Except%2A> operation is well defined only on sets.</span></span> <span data-ttu-id="63fb0-108">다중 집합에 대한 의미 체계는 정의되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63fb0-108">The semantics for multisets is undefined.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="63fb0-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="63fb0-109">See also</span></span>

- [<span data-ttu-id="63fb0-110">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="63fb0-110">Query Examples</span></span>](query-examples.md)
- [<span data-ttu-id="63fb0-111">표준 쿼리 연산자 변환</span><span class="sxs-lookup"><span data-stu-id="63fb0-111">Standard Query Operator Translation</span></span>](standard-query-operator-translation.md)
