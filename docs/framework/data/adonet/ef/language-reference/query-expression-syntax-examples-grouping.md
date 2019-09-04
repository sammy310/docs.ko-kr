---
title: '쿼리 식 구문 예제: 그룹화'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2d83d7c0-b3be-4c92-a630-25cd1285de31
ms.openlocfilehash: bbb41918e4d3637ff1e04275ad6151510dfa036b
ms.sourcegitcommit: 4e2d355baba82814fa53efd6b8bbb45bfe054d11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/04/2019
ms.locfileid: "70249502"
---
# <a name="query-expression-syntax-examples-grouping"></a><span data-ttu-id="11e7f-102">쿼리 식 구문 예제: 그룹화</span><span class="sxs-lookup"><span data-stu-id="11e7f-102">Query Expression Syntax Examples: Grouping</span></span>
<span data-ttu-id="11e7f-103">이 항목의 예제에서는 쿼리 식 구문을 사용 하 `GroupBy` 여 [AdventureWorks Sales 모델](https://archive.codeplex.com/?p=msftdbprodsamples) 을 쿼리 하는 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="11e7f-103">The examples in this topic demonstrate how to use the `GroupBy` method to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="11e7f-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="11e7f-104">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="11e7f-105">이 항목의 예제에서는 다음 `using` / `Imports` 문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="11e7f-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="example"></a><span data-ttu-id="11e7f-106">예제</span><span class="sxs-lookup"><span data-stu-id="11e7f-106">Example</span></span>  
 <span data-ttu-id="11e7f-107">다음 예제에서는 우편 번호로 그룹화된 `Address` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="11e7f-107">The following example returns `Address` objects grouped by postal code.</span></span> <span data-ttu-id="11e7f-108">결과는 익명 형식으로 프로젝션됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e7f-108">The results are projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple3)]
 [!code-vb[DP L2E Examples#GroupBySimple3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple3)]  
  
## <a name="example"></a><span data-ttu-id="11e7f-109">예제</span><span class="sxs-lookup"><span data-stu-id="11e7f-109">Example</span></span>  
 <span data-ttu-id="11e7f-110">다음 예제에서는 연락처 성의 첫 번째 문자로 그룹화된 `Contact` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="11e7f-110">The following example returns `Contact` objects grouped by the first letter of the contact's last name.</span></span> <span data-ttu-id="11e7f-111">또한 결과는 성의 첫 번째 문자로 정렬되며 익명 형식으로 프로젝션됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e7f-111">The results are also sorted by the first letter of last name and projected into an anonymous type.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbysimple2)]
 [!code-vb[DP L2E Examples#GroupBySimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbysimple2)]  
  
## <a name="example"></a><span data-ttu-id="11e7f-112">예제</span><span class="sxs-lookup"><span data-stu-id="11e7f-112">Example</span></span>  
 <span data-ttu-id="11e7f-113">다음 예제에서는 고객 ID별로 그룹화된 `SalesOrderHeader` 개체를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="11e7f-113">The following example returns `SalesOrderHeader` objects grouped by customer ID.</span></span> <span data-ttu-id="11e7f-114">또한 고객별 판매 수량도 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="11e7f-114">The number of sales for each customer is also returned.</span></span>  
  
 [!code-csharp[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#groupbycount)]
 [!code-vb[DP L2E Examples#GroupByCount](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#groupbycount)]  
  
## <a name="see-also"></a><span data-ttu-id="11e7f-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="11e7f-115">See also</span></span>

- [<span data-ttu-id="11e7f-116">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="11e7f-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
