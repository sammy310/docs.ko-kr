---
title: '메서드 기반 쿼리 구문 예제: ELEMENT 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 96d393a34af69935e75582ef1954ddd661a355f0
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192050"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="8daf3-102">메서드 기반 쿼리 구문 예제: ELEMENT 연산자</span><span class="sxs-lookup"><span data-stu-id="8daf3-102">Method-Based Query Syntax Examples: Element Operators</span></span>

<span data-ttu-id="8daf3-103">이 항목의 예제에서는 메서드를 사용 하 여 <xref:System.Linq.Enumerable.First%2A> 메서드 기반 쿼리 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8daf3-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="8daf3-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="8daf3-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="8daf3-105">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="8daf3-105">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="8daf3-106">첫째</span><span class="sxs-lookup"><span data-stu-id="8daf3-106">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="8daf3-107">예제</span><span class="sxs-lookup"><span data-stu-id="8daf3-107">Example</span></span>  

 <span data-ttu-id="8daf3-108">다음 예제에서는 메서드를 사용 하 여 <xref:System.Linq.Enumerable.First%2A> ' caroline '로 시작 하는 첫 번째 전자 메일 주소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8daf3-108">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="8daf3-109">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8daf3-109">See also</span></span>

- [<span data-ttu-id="8daf3-110">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="8daf3-110">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
