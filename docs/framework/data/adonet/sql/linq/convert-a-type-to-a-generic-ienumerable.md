---
title: 제네릭 IEnumerable로 형식 변환
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 64774fb5-7447-4296-ad3b-8a94346f99a1
ms.openlocfilehash: c2d34ae708f79d9f920679b3714a100fe8943c38
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91164417"
---
# <a name="convert-a-type-to-a-generic-ienumerable"></a><span data-ttu-id="fdf44-102">제네릭 IEnumerable로 형식 변환</span><span class="sxs-lookup"><span data-stu-id="fdf44-102">Convert a Type to a Generic IEnumerable</span></span>

<span data-ttu-id="fdf44-103"><xref:System.Linq.Enumerable.AsEnumerable%2A>을 사용하여 제네릭 `IEnumerable`로 형식화된 인수를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf44-103">Use <xref:System.Linq.Enumerable.AsEnumerable%2A> to return the argument typed as a generic `IEnumerable`.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fdf44-104">예제</span><span class="sxs-lookup"><span data-stu-id="fdf44-104">Example</span></span>  

 <span data-ttu-id="fdf44-105">이 예제에서는 기본 제네릭 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]를 사용하여 `Query`에서 쿼리를 SQL로 변환하여 해당 쿼리를 서버에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf44-105">In this example, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (using the default generic `Query`) would try to convert the query to SQL and execute it on the server.</span></span> <span data-ttu-id="fdf44-106">그러나 `where` 절에서는 SQL로 변환할 수 없는 사용자 정의 클라이언트측 메서드(`isValidProduct`)를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf44-106">But the `where` clause references a user-defined client-side method (`isValidProduct`), which cannot be converted to SQL.</span></span>  
  
 <span data-ttu-id="fdf44-107">이 솔루션에서는 <xref:System.Collections.Generic.IEnumerable%601>의 클라이언트측 제네릭 `where` 구현을 지정하여 제네릭 <xref:System.Linq.IQueryable%601>을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf44-107">The solution is to specify the client-side generic <xref:System.Collections.Generic.IEnumerable%601> implementation of `where` to replace the generic <xref:System.Linq.IQueryable%601>.</span></span> <span data-ttu-id="fdf44-108">이 작업은 <xref:System.Linq.Enumerable.AsEnumerable%2A> 연산자를 호출하여 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="fdf44-108">You do this by invoking the <xref:System.Linq.Enumerable.AsEnumerable%2A> operator.</span></span>  
  
 [!code-csharp[DLinqQueryExamples#46](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQueryExamples/cs/Program.cs#46)]
 [!code-vb[DLinqQueryExamples#46](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQueryExamples/vb/Module1.vb#46)]  
  
## <a name="see-also"></a><span data-ttu-id="fdf44-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fdf44-109">See also</span></span>

- [<span data-ttu-id="fdf44-110">쿼리 예제</span><span class="sxs-lookup"><span data-stu-id="fdf44-110">Query Examples</span></span>](query-examples.md)
