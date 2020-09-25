---
title: '메서드 기반 쿼리 구문 예제: 그룹화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: cb23c25c-1075-4cc3-a8ff-4db72e536c0d
ms.openlocfilehash: 2d84e755217878bfa248add37a752224a20d3f84
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191985"
---
# <a name="method-based-query-syntax-examples-grouping"></a><span data-ttu-id="cf498-102">메서드 기반 쿼리 구문 예제: 그룹화</span><span class="sxs-lookup"><span data-stu-id="cf498-102">Method-Based Query Syntax Examples: Grouping</span></span>

<span data-ttu-id="cf498-103">이 항목의 예제에서는 메서드를 사용 하 여 `GroupBy` 메서드 기반 쿼리 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cf498-103">The examples in this topic show you how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="cf498-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cf498-104">The AdventureWorks Sales Model that is used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="cf498-105">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="cf498-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="cf498-106">예제</span><span class="sxs-lookup"><span data-stu-id="cf498-106">Example</span></span>  

 <span data-ttu-id="cf498-107">다음 예제에서는 `GroupBy` 메서드를 사용하여 우편 번호별로 그룹화된 `Address` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cf498-107">The following example uses the `GroupBy` method to return `Address` objects that are grouped by postal code.</span></span> <span data-ttu-id="cf498-108">결과는 익명 형식으로 프로젝션됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf498-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple3_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3_mq)]  
  
## <a name="example"></a><span data-ttu-id="cf498-109">예제</span><span class="sxs-lookup"><span data-stu-id="cf498-109">Example</span></span>  

 <span data-ttu-id="cf498-110">다음 예제에서는 `GroupBy` 메서드를 사용하여 연락처 성의 첫 번째 문자로 그룹화된 `Contact` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cf498-110">The following example uses the `GroupBy` method to return `Contact` objects that are grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="cf498-111">또한 결과는 성의 첫 번째 문자별로 정렬되며 익명 형식으로 프로젝션됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf498-111">The results are also sorted by the first letter of the last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2_mq)]
 [!code-vb[DP L2E Examples#GroupBySimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2_mq)]  
  
## <a name="example"></a><span data-ttu-id="cf498-112">예제</span><span class="sxs-lookup"><span data-stu-id="cf498-112">Example</span></span>  

 <span data-ttu-id="cf498-113">다음 예제에서는 `GroupBy` 메서드를 사용하여 고객 ID별로 그룹화된 `SalesOrderHeader` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cf498-113">The following example uses the `GroupBy` method to return `SalesOrderHeader` objects that are grouped by customer ID.</span></span> <span data-ttu-id="cf498-114">또한 고객별 판매 수량도 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="cf498-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount_mq)]
 [!code-vb[DP L2E Examples#GroupByCount_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="cf498-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cf498-115">See also</span></span>

- [<span data-ttu-id="cf498-116">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="cf498-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
