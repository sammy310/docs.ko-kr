---
title: '메서드 기반 쿼리 구문 예제: 분할'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b7b64874-c3c8-4bdb-862c-89a168d07827
ms.openlocfilehash: 659c05f261b854b1f2bb9bc3bce7c2889650571f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91191894"
---
# <a name="method-based-query-syntax-examples-partitioning"></a><span data-ttu-id="e032c-102">메서드 기반 쿼리 구문 예제: 분할</span><span class="sxs-lookup"><span data-stu-id="e032c-102">Method-Based Query Syntax Examples: Partitioning</span></span>

<span data-ttu-id="e032c-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> <xref:System.Linq.Enumerable.Take%2A> 쿼리 식 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하기 위해, 및 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e032c-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Skip%2A>, and <xref:System.Linq.Enumerable.Take%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using query expression syntax.</span></span> <span data-ttu-id="e032c-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e032c-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="e032c-105">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="e032c-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="skip"></a><span data-ttu-id="e032c-106">건너뛰기</span><span class="sxs-lookup"><span data-stu-id="e032c-106">Skip</span></span>  
  
### <a name="example"></a><span data-ttu-id="e032c-107">예제</span><span class="sxs-lookup"><span data-stu-id="e032c-107">Example</span></span>  

 <span data-ttu-id="e032c-108">다음 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 메서드를 사용하여 Contact 테이블에서 맨 위쪽에 있는 5개를 제외한 나머지 연락처 정보를 모두 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e032c-108">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first five contacts of the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipsimple)]
 [!code-vb[DP L2E Examples#SkipSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipsimple)]  
  
### <a name="example"></a><span data-ttu-id="e032c-109">예제</span><span class="sxs-lookup"><span data-stu-id="e032c-109">Example</span></span>  

 <span data-ttu-id="e032c-110">다음 예제에서는 <xref:System.Linq.Enumerable.Skip%2A> 메서드를 사용하여 Seattle에 있는 처음 2개의 주소를 제외한 모든 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e032c-110">The following example uses the <xref:System.Linq.Enumerable.Skip%2A> method to get all but the first two addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#SkipNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#skipnested)]
 [!code-vb[DP L2E Examples#SkipNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#skipnested)]  
  
## <a name="take"></a><span data-ttu-id="e032c-111">Take</span><span class="sxs-lookup"><span data-stu-id="e032c-111">Take</span></span>  
  
### <a name="example"></a><span data-ttu-id="e032c-112">예제</span><span class="sxs-lookup"><span data-stu-id="e032c-112">Example</span></span>  

 <span data-ttu-id="e032c-113">다음 예제에서는 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 Contact 테이블에서 맨 위쪽에 있는 5개의 연락처 정보를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e032c-113">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get only the first five contacts from the Contact table.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takesimple)]
 [!code-vb[DP L2E Examples#TakeSimple](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takesimple)]  
  
### <a name="example"></a><span data-ttu-id="e032c-114">예제</span><span class="sxs-lookup"><span data-stu-id="e032c-114">Example</span></span>  

 <span data-ttu-id="e032c-115">다음 예제에서는 <xref:System.Linq.Enumerable.Take%2A> 메서드를 사용하여 Seattle에 있는 처음 3개의 주소를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e032c-115">The following example uses the <xref:System.Linq.Enumerable.Take%2A> method to get the first three addresses in Seattle.</span></span>  
  
 [!code-csharp[DP L2E Examples#TakeNested](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#takenested)]
 [!code-vb[DP L2E Examples#TakeNested](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#takenested)]  
  
## <a name="see-also"></a><span data-ttu-id="e032c-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e032c-116">See also</span></span>

- [<span data-ttu-id="e032c-117">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="e032c-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
