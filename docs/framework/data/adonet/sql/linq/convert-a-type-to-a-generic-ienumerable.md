---
description: '자세히 알아보기: 형식을 제네릭 IEnumerable로 변환'
title: 제네릭 IEnumerable로 형식 변환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: 9be9022bce84808e18514937116ea962065dc1a8
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712521"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="47e53-103">제네릭 IEnumerable로 형식 변환</span><span class="sxs-lookup"><span data-stu-id="47e53-103">Convert a Type to a Generic IEnumerable</span></span>

<span data-ttu-id="47e53-104"><xref:System.Linq.Enumerable.AsEnumerable%2A>을 사용하여 제네릭 `IEnumerable`로 형식화된 인수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="47e53-104">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47e53-105">예제</span><span class="sxs-lookup"><span data-stu-id="47e53-105">Example</span></span>  

 <span data-ttu-id="47e53-106">이 예제에서는 기본 제네릭 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 사용하여 `Query`에서 쿼리를 SQL로 변환하여 해당 쿼리를 서버에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47e53-106">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="47e53-107">그러나 `where` 절에서는 SQL로 변환할 수 없는 사용자 정의 클라이언트측 메서드(`isValidProduct`)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="47e53-107">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="47e53-108">이 솔루션에서는 <xref:System.Collections.Generic.IEnumerable%601>의 클라이언트측 제네릭 `where` 구현을 지정하여 제네릭 <xref:System.Linq.IQueryable%601>을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="47e53-108">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="47e53-109">이 작업은 <xref:System.Linq.Enumerable.AsEnumerable%2A> 연산자를 호출하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="47e53-109">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="47e53-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47e53-110">See also</span></span>

- [<span data-ttu-id="47e53-111">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="47e53-111">Query Examples</span></span>](query-examples.md)
