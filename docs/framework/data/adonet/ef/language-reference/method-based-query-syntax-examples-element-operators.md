---
description: '자세한 정보: Method-Based 쿼리 구문 예제: Element 연산자'
title: '메서드 기반 쿼리 구문 예제: ELEMENT 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 8438b995-bd07-4223-b22d-13adadef33fb
ms.openlocfilehash: 8a83602c4d374ae02b4f39ee75821718f8b53f3e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673585"
---
# <a name="method-based-query-syntax-examples-element-operators"></a><span data-ttu-id="eabfe-103">메서드 기반 쿼리 구문 예제: ELEMENT 연산자</span><span class="sxs-lookup"><span data-stu-id="eabfe-103">Method-Based Query Syntax Examples: Element Operators</span></span>

<span data-ttu-id="eabfe-104">이 항목의 예제에서는 메서드를 사용 하 여 <xref:System.Linq.Enumerable.First%2A> 메서드 기반 쿼리 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="eabfe-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="eabfe-105">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="eabfe-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="eabfe-106">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="eabfe-106">The example in this topic uses the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="eabfe-107">첫째</span><span class="sxs-lookup"><span data-stu-id="eabfe-107">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="eabfe-108">예제</span><span class="sxs-lookup"><span data-stu-id="eabfe-108">Example</span></span>  

 <span data-ttu-id="eabfe-109">다음 예제에서는 메서드를 사용 하 여 <xref:System.Linq.Enumerable.First%2A> ' caroline '로 시작 하는 첫 번째 전자 메일 주소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="eabfe-109">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to find the first email address that starts with 'caroline'.</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstcondition_mq)]
 [!code-vb[DP L2E Examples#FirstCondition_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstcondition_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="eabfe-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eabfe-110">See also</span></span>

- [<span data-ttu-id="eabfe-111">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="eabfe-111">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
