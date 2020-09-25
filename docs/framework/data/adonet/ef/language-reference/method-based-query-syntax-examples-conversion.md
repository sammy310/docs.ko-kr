---
title: '메서드 기반 쿼리 구문 예제: 변환'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 19f66872-d5ab-49f8-969f-e53f9632a13d
ms.openlocfilehash: e2b5ae3b7c7733216f18914c497d080fe8d71a8e
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91192089"
---
# <a name="method-based-query-syntax-examples-conversion"></a><span data-ttu-id="33d99-102">메서드 기반 쿼리 구문 예제: 변환</span><span class="sxs-lookup"><span data-stu-id="33d99-102">Method-Based Query Syntax Examples: Conversion</span></span>

<span data-ttu-id="33d99-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.ToArray%2A> <xref:System.Linq.Enumerable.ToDictionary%2A> <xref:System.Linq.Enumerable.ToList%2A> 메서드 기반 쿼리 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하기 위해, 및 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="33d99-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.ToArray%2A>, <xref:System.Linq.Enumerable.ToDictionary%2A> and <xref:System.Linq.Enumerable.ToList%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="33d99-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="33d99-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="33d99-105">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="33d99-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="toarray"></a><span data-ttu-id="33d99-106">ToArray</span><span class="sxs-lookup"><span data-stu-id="33d99-106">ToArray</span></span>  
  
### <a name="example"></a><span data-ttu-id="33d99-107">예제</span><span class="sxs-lookup"><span data-stu-id="33d99-107">Example</span></span>  

 <span data-ttu-id="33d99-108">다음 예제에서는 <xref:System.Linq.Enumerable.ToArray%2A> 메서드로 시퀀스를 즉시 계산하여 배열에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="33d99-108">The following example uses the <xref:System.Linq.Enumerable.ToArray%2A> method to immediately evaluate a sequence into an array.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToArray](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#toarray)]
 [!code-vb[DP L2E Examples#ToArray](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#toarray)]  
  
## <a name="todictionary"></a><span data-ttu-id="33d99-109">ToDictionary</span><span class="sxs-lookup"><span data-stu-id="33d99-109">ToDictionary</span></span>  
  
### <a name="example"></a><span data-ttu-id="33d99-110">예제</span><span class="sxs-lookup"><span data-stu-id="33d99-110">Example</span></span>  

 <span data-ttu-id="33d99-111">다음 예제에서는 <xref:System.Linq.Enumerable.ToDictionary%2A> 메서드로 시퀀스 및 관련 키 식을 즉시 계산하여 사전에 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="33d99-111">The following example uses the <xref:System.Linq.Enumerable.ToDictionary%2A> method to immediately evaluate a sequence and a related key expression into a dictionary.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#todictionary)]
 [!code-vb[DP L2E Examples#ToDictionary](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#todictionary)]  
  
## <a name="tolist"></a><span data-ttu-id="33d99-112">ToList</span><span class="sxs-lookup"><span data-stu-id="33d99-112">ToList</span></span>  
  
### <a name="example"></a><span data-ttu-id="33d99-113">예제</span><span class="sxs-lookup"><span data-stu-id="33d99-113">Example</span></span>  

 <span data-ttu-id="33d99-114">다음 예제에서는 <xref:System.Linq.Enumerable.ToList%2A> 메서드로 시퀀스를 즉시 계산하여 <xref:System.Collections.Generic.List%601>에 넣습니다. 여기서 `T`는 <xref:System.Data.DataRow> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="33d99-114">The following example uses the <xref:System.Linq.Enumerable.ToList%2A> method to immediately evaluate a sequence into a <xref:System.Collections.Generic.List%601>, where `T` is of type <xref:System.Data.DataRow>.</span></span>  
  
 [!code-csharp[DP L2E Examples#ToList](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#tolist)]
 [!code-vb[DP L2E Examples#ToList](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#tolist)]  
  
## <a name="see-also"></a><span data-ttu-id="33d99-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="33d99-115">See also</span></span>

- [<span data-ttu-id="33d99-116">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="33d99-116">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
