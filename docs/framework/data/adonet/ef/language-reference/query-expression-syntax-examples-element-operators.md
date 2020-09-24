---
title: '쿼리 식 구문 예제: 요소 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 8cd550120e949f247a17ca6c7dafca06607a4e7e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91152990"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="7583b-102">쿼리 식 구문 예제: 요소 연산자</span><span class="sxs-lookup"><span data-stu-id="7583b-102">Query Expression Syntax Examples: Element Operators</span></span>

<span data-ttu-id="7583b-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.First%2A> 쿼리 식 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하는 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7583b-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using the query expression syntax.</span></span> <span data-ttu-id="7583b-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7583b-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="7583b-105">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="7583b-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="7583b-106">첫째</span><span class="sxs-lookup"><span data-stu-id="7583b-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="7583b-107">예제</span><span class="sxs-lookup"><span data-stu-id="7583b-107">Example</span></span>  

 <span data-ttu-id="7583b-108">다음 예제에서는 <xref:System.Linq.Enumerable.First%2A> 메서드를 사용하여 이름이 "Brooke"인 첫 번째 연락처를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="7583b-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="7583b-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7583b-109">See also</span></span>

- [<span data-ttu-id="7583b-110">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="7583b-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
