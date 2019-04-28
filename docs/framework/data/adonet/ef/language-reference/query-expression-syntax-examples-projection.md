---
title: '쿼리 식 구문 예제: 프로젝션'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 079926c5-e6b5-4fb9-b4cf-9c63886dd626
ms.openlocfilehash: 9c10c334ae2a10df1f75384ce042781b6f1bd43a
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61614416"
---
# <a name="query-expression-syntax-examples-projection"></a><span data-ttu-id="cb3bd-102">쿼리 식 구문 예제: 프로젝션</span><span class="sxs-lookup"><span data-stu-id="cb3bd-102">Query Expression Syntax Examples: Projection</span></span>
<span data-ttu-id="cb3bd-103">이 항목의 예제에 사용 하는 방법을 보여 줍니다는 `Select` 메서드 및 `From … From …` 쿼리 키워드는 [AdventureWorks Sales 모델](https://archive.codeplex.com/?p=msftdbprodsamples) 쿼리 식 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3bd-103">The examples in this topic demonstrate how to use the `Select` method and the `From … From …` keywords to query the [AdventureWorks Sales Model](https://archive.codeplex.com/?p=msftdbprodsamples) using query expression syntax.</span></span> <span data-ttu-id="cb3bd-104">`From … From …`은 `SelectMany` 메서드에 해당하는 쿼리 기반 키워드입니다.</span><span class="sxs-lookup"><span data-stu-id="cb3bd-104">`From … From …` is the query based equivalent of the `SelectMany` method.</span></span> <span data-ttu-id="cb3bd-105">이 예제에서 사용하는 AdventureWorks Sales 모델에서는 AdventureWorks 샘플 데이터베이스의 Contact, Address, Product, SalesOrderHeader 및 SalesOrderDetail 테이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3bd-105">The AdventureWorks Sales model used in these examples is built from the Contact, Address, Product, SalesOrderHeader, and SalesOrderDetail tables in the AdventureWorks sample database.</span></span>  
  
 <span data-ttu-id="cb3bd-106">이 항목의 예제에서는 다음을 사용 `using` / `Imports` 문:</span><span class="sxs-lookup"><span data-stu-id="cb3bd-106">The examples in this topic use the following `using`/`Imports` statements:</span></span>  
  
 [!code-csharp[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#importsusing)]
 [!code-vb[DP L2E Examples#ImportsUsing](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#importsusing)]  
  
## <a name="select"></a><span data-ttu-id="cb3bd-107">선택</span><span class="sxs-lookup"><span data-stu-id="cb3bd-107">Select</span></span>  
  
### <a name="example"></a><span data-ttu-id="cb3bd-108">예제</span><span class="sxs-lookup"><span data-stu-id="cb3bd-108">Example</span></span>  
 <span data-ttu-id="cb3bd-109">다음 예제에서는 <xref:System.Linq.Enumerable.Select%2A> 메서드를 사용하여 `Product` 테이블의 모든 행을 반환하고 제품 이름을 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3bd-109">The following example uses the <xref:System.Linq.Enumerable.Select%2A> method to return all the rows from the `Product` table and display the product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple1)]
 [!code-vb[DP L2E Examples#SelectSimple1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple1)]  
  
### <a name="example"></a><span data-ttu-id="cb3bd-110">예제</span><span class="sxs-lookup"><span data-stu-id="cb3bd-110">Example</span></span>  
 <span data-ttu-id="cb3bd-111">다음 예제에서는 <xref:System.Linq.Enumerable.Select%2A>를 사용하여 제품 이름만으로 구성된 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3bd-111">The following example uses <xref:System.Linq.Enumerable.Select%2A> to return a sequence of only product names.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectsimple2)]
 [!code-vb[DP L2E Examples#SelectSimple2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectsimple2)]  
  
### <a name="example"></a><span data-ttu-id="cb3bd-112">예제</span><span class="sxs-lookup"><span data-stu-id="cb3bd-112">Example</span></span>  
 <span data-ttu-id="cb3bd-113">다음 예제에서는 <xref:System.Linq.Queryable.Select%2A> 메서드를 사용하여 `Product.Name` 및 `Product.ProductID` 속성을 익명 형식 시퀀스로 프로젝션합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3bd-113">The following example uses the <xref:System.Linq.Queryable.Select%2A> method to project the `Product.Name` and `Product.ProductID` properties into a sequence of anonymous types.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectanonymoustypes)]
 [!code-vb[DP L2E Examples#SelectAnonymousTypes](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectanonymoustypes)]  
  
## <a name="from--from--selectmany"></a><span data-ttu-id="cb3bd-114">보낸 사람...</span><span class="sxs-lookup"><span data-stu-id="cb3bd-114">From …</span></span> <span data-ttu-id="cb3bd-115">보낸 사람...</span><span class="sxs-lookup"><span data-stu-id="cb3bd-115">From …</span></span> <span data-ttu-id="cb3bd-116">(SelectMany)</span><span class="sxs-lookup"><span data-stu-id="cb3bd-116">(SelectMany)</span></span>  
  
### <a name="example"></a><span data-ttu-id="cb3bd-117">예제</span><span class="sxs-lookup"><span data-stu-id="cb3bd-117">Example</span></span>  
 <span data-ttu-id="cb3bd-118">다음 예제에서는 `From … From …`(<xref:System.Linq.Enumerable.SelectMany%2A> 메서드와 같음)을 사용하여 `TotalDue`가 500.00보다 작은 모든 주문을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3bd-118">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where `TotalDue` is less than 500.00.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom)]  
  
### <a name="example"></a><span data-ttu-id="cb3bd-119">예제</span><span class="sxs-lookup"><span data-stu-id="cb3bd-119">Example</span></span>  
 <span data-ttu-id="cb3bd-120">다음 예제에서는 `From … From …`(<xref:System.Linq.Enumerable.SelectMany%2A> 메서드와 같음)을 사용하여 2002년 10월 1일 이후에 작성된 모든 주문을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3bd-120">The following example uses `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order was made on October 1, 2002 or later.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanycompoundfrom2)]
 [!code-vb[DP L2E Examples#SelectManyCompoundFrom2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanycompoundfrom2)]  
  
### <a name="example"></a><span data-ttu-id="cb3bd-121">예제</span><span class="sxs-lookup"><span data-stu-id="cb3bd-121">Example</span></span>  
 <span data-ttu-id="cb3bd-122">다음 예제에서는 `From … From …`(<xref:System.Linq.Enumerable.SelectMany%2A> 메서드와 같음)을 사용하여 주문 합계가 10000.00보다 큰 모든 주문을 선택하고 `From` 할당을 사용하여 합계가 두 번 요청되지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="cb3bd-122">The following example uses a `From … From …` (the equivalent of the <xref:System.Linq.Enumerable.SelectMany%2A> method) to select all orders where the order total is greater than 10000.00 and uses `From` assignment to avoid requesting the total twice.</span></span>  
  
 [!code-csharp[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DP L2E Examples/CS/Program.cs#selectmanyfromassignment)]
 [!code-vb[DP L2E Examples#SelectManyFromAssignment](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DP L2E Examples/VB/Module1.vb#selectmanyfromassignment)]  
  
## <a name="see-also"></a><span data-ttu-id="cb3bd-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="cb3bd-123">See also</span></span>

- [<span data-ttu-id="cb3bd-124">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="cb3bd-124">Queries in LINQ to Entities</span></span>](../../../../../../docs/framework/data/adonet/ef/language-reference/queries-in-linq-to-entities.md)
