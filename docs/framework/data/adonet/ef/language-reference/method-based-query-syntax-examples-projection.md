---
title: '메서드 기반 쿼리 구문 예제: 프로젝션'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 505491fa-5920-43ce-8a96-c25389e125d8
ms.openlocfilehash: 32db3d0f85e525ad1850df59f0abe66bf82b137b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91175787"
---
# <a name="method-based-query-syntax-examples-projection"></a><span data-ttu-id="159b6-102">메서드 기반 쿼리 구문 예제: 프로젝션</span><span class="sxs-lookup"><span data-stu-id="159b6-102">Method-Based Query Syntax Examples: Projection</span></span>

<span data-ttu-id="159b6-103">이 항목의 예제에서는 <xref:System.Linq.Enumerable.Select%2A> <xref:System.Linq.Enumerable.SelectMany%2A> 메서드 기반 쿼리 구문을 사용 하 여 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) 을 쿼리 하기 위해 및 메서드를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="159b6-103">The examples in this topic demonstrate how to use the <xref:System.Linq.Enumerable.Select%2A> and <xref:System.Linq.Enumerable.SelectMany%2A> methods to query the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks) using method-based query syntax.</span></span> <span data-ttu-id="159b6-104">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="159b6-104">The AdventureWorks Sales Model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="159b6-105">이 항목의 예제에서는 다음 문을 사용 합니다 `using` / `Imports` .</span><span class="sxs-lookup"><span data-stu-id="159b6-105">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="159b6-106">선택</span><span class="sxs-lookup"><span data-stu-id="159b6-106">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="159b6-107">예제</span><span class="sxs-lookup"><span data-stu-id="159b6-107">Example</span></span>  

 <span data-ttu-id="159b6-108">다음 예제에서는 <xref:System.Linq.Queryable.Select%2A> 메서드를 사용하여 `Product.Name` 및 `Product.ProductID` 속성을 익명 형식 시퀀스로 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="159b6-108">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes_mq)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes_mq)]  
  
### <a name="example"></a><span data-ttu-id="159b6-109">예제</span><span class="sxs-lookup"><span data-stu-id="159b6-109">Example</span></span>  

 <span data-ttu-id="159b6-110">다음 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 메서드를 사용하여 제품 이름만으로 구성된 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="159b6-110">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2_mq)]
 [!code-vb[DP L2E Examples#SelectSimple2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2_mq)]  
  
## <a name="selectmany"></a><span data-ttu-id="159b6-111">SelectMany</span><span class="sxs-lookup"><span data-stu-id="159b6-111">SelectMany</span></span>  
  
### <a name="example"></a><span data-ttu-id="159b6-112">예제</span><span class="sxs-lookup"><span data-stu-id="159b6-112">Example</span></span>  

 <span data-ttu-id="159b6-113">다음 예제에서는 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드를 사용하여 `TotalDue`가 500.00보다 작은 모든 주문을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="159b6-113">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom_mq)]  
  
### <a name="example"></a><span data-ttu-id="159b6-114">예제</span><span class="sxs-lookup"><span data-stu-id="159b6-114">Example</span></span>  

 <span data-ttu-id="159b6-115">다음 예제에서는 <xref:System.Linq.Enumerable.SelectMany%2A> 메서드를 사용하여 2002년 10월 1일 이후에 작성된 모든 주문을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="159b6-115">The following example uses the <xref:System.Linq.Enumerable.SelectMany%2A> method to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2_mq)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2_MQ](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2_mq)]  
  
## <a name="see-also"></a><span data-ttu-id="159b6-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="159b6-116">See also</span></span>

- [<span data-ttu-id="159b6-117">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="159b6-117">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
