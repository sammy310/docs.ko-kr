---
description: '자세한 정보: 쿼리 식 구문 예제: Element 연산자'
title: '쿼리 식 구문 예제: 요소 연산자'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 32268fe2-de18-4065-8060-f250def83837
ms.openlocfilehash: 0dc6d49959abba712cef572eaa549138af646bd5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99696245"
---
# <a name="query-expression-syntax-examples-element-operators"></a><span data-ttu-id="9feaf-103">쿼리 식 구문 예제: 요소 연산자</span><span class="sxs-lookup"><span data-stu-id="9feaf-103">Query Expression Syntax Examples: Element Operators</span></span>

<span data-ttu-id="9feaf-104">이 항목의 예제에서는 <xref:System.Linq.Enumerable.First%2A> 쿼리 식 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하는 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="9feaf-104">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.First%2A> method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using the query expression syntax.</span></span> <span data-ttu-id="9feaf-105">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9feaf-105">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="9feaf-106">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="9feaf-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="first"></a><span data-ttu-id="9feaf-107">첫째</span><span class="sxs-lookup"><span data-stu-id="9feaf-107">First</span></span>  
  
### <a name="example"></a><span data-ttu-id="9feaf-108">예제</span><span class="sxs-lookup"><span data-stu-id="9feaf-108">Example</span></span>  

 <span data-ttu-id="9feaf-109">다음 예제에서는 <xref:System.Linq.Enumerable.First%2A> 메서드를 사용하여 이름이 "Brooke"인 첫 번째 연락처를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="9feaf-109">The following example uses the <xref:System.Linq.Enumerable.First%2A> method to return the first contact whose first name is "Brooke".</span></span>  
  
 [!code-csharp[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#firstsimple)]
 [!code-vb[DP L2E Examples#FirstSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#firstsimple)]  
  
## <a name="see-also"></a><span data-ttu-id="9feaf-110">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9feaf-110">See also</span></span>

- [<span data-ttu-id="9feaf-111">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="9feaf-111">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
