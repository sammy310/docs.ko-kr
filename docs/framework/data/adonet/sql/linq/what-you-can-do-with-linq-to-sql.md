---
description: '자세히 알아보기: LINQ to SQL에서 수행할 수 있는 작업'
title: LINQ to SQL을- 사용하여 할 수 있는 작업
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 061d98b2-baa7-4336-8ad2-c14de8134d91
ms.openlocfilehash: adf1d8dfab69db27d15634a12dbdfbfa287dbb4c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99791753"
---
# <a name="what-you-can-do-with-linq-to-sql"></a><span data-ttu-id="4195b-103">LINQ to SQL을- 사용하여 할 수 있는 작업</span><span class="sxs-lookup"><span data-stu-id="4195b-103">What You Can Do With LINQ to SQL</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4195b-104">에서는 SQL 개발자가 필요로 하는 모든 주요 기능을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-104">supports all the key capabilities you would expect as a SQL developer.</span></span> <span data-ttu-id="4195b-105">정보를 쿼리하고 테이블에 정보를 삽입, 업데이트 및 삭제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-105">You can query for information, and insert, update, and delete information from tables.</span></span>  
  
## <a name="selecting"></a><span data-ttu-id="4195b-106">선택</span><span class="sxs-lookup"><span data-stu-id="4195b-106">Selecting</span></span>  

 <span data-ttu-id="4195b-107">사용자 고유의 프로그래밍 언어로 LINQ 쿼리를 작성 한 다음 해당 쿼리를 실행 하 여 결과를 검색 하기만 하면 (*프로젝션*)를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-107">Selecting (*projection*) is achieved by just writing a LINQ query in your own programming language, and then executing that query to retrieve the results.</span></span> <span data-ttu-id="4195b-108">필요한 모든 작업은[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 를 통해 사용자에게 익숙한 필수 SQL 작업으로 변환됩니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-108">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] itself translates all the necessary operations into the necessary SQL operations that you are familiar with.</span></span> <span data-ttu-id="4195b-109">자세한 내용은 [LINQ to SQL](index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4195b-109">For more information, see [LINQ to SQL](index.md).</span></span>  
  
 <span data-ttu-id="4195b-110">다음 예제에서는 London의 고객사 이름이 검색되어 콘솔 창에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-110">In the following example, the company names of customers from London are retrieved and displayed in the console window.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#1)]
 [!code-vb[DLinqGettingStarted#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#1)]  
  
## <a name="inserting"></a><span data-ttu-id="4195b-111">삽입</span><span class="sxs-lookup"><span data-stu-id="4195b-111">Inserting</span></span>  

 <span data-ttu-id="4195b-112">SQL `Insert`를 실행하려면 개체를 사용자가 만든 개체 모델에 추가하고 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 에서 <xref:System.Data.Linq.DataContext>를 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-112">To execute a SQL `Insert`, just add objects to the object model you have created, and call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext>.</span></span>  
  
 <span data-ttu-id="4195b-113">다음 예제에서는 `Customers` 을 사용하여 새 고객 및 새 고객에 대한 정보가 <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>테이블에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-113">In the following example, a new customer and information about the customer is added to the `Customers` table by using <xref:System.Data.Linq.Table%601.InsertOnSubmit%2A>.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#2)]
 [!code-vb[DLinqGettingStarted#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#2)]  
  
## <a name="updating"></a><span data-ttu-id="4195b-114">업데이트</span><span class="sxs-lookup"><span data-stu-id="4195b-114">Updating</span></span>  

 <span data-ttu-id="4195b-115">데이터베이스 항목을 `Update` 하려면 먼저 해당 항목을 검색하고 이를 개체 모델에서 직접 편집합니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-115">To `Update` a database entry, first retrieve the item and edit it directly in the object model.</span></span> <span data-ttu-id="4195b-116">개체를 수정한 후 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 에서 <xref:System.Data.Linq.DataContext> 를 호출하여 데이터베이스를 업데이트합니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-116">After you have modified the object, call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to update the database.</span></span>  
  
 <span data-ttu-id="4195b-117">다음 예제에서는 London의 모든 고객들이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-117">In the following example, all customers who are from London are retrieved.</span></span> <span data-ttu-id="4195b-118">그런 다음 도시 이름이 "London"에서 "London - Metro"로 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-118">Then the name of the city is changed from "London" to "London - Metro".</span></span> <span data-ttu-id="4195b-119">마지막으로 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 가 호출되어 변경 내용을 데이터베이스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-119">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to send the changes to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#3)]
 [!code-vb[DLinqGettingStarted#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#3)]  
  
## <a name="deleting"></a><span data-ttu-id="4195b-120">삭제 중</span><span class="sxs-lookup"><span data-stu-id="4195b-120">Deleting</span></span>  

 <span data-ttu-id="4195b-121">항목을 `Delete` 하려면 항목이 속해 있는 컬렉션에서 항목을 제거한 다음 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 에서 <xref:System.Data.Linq.DataContext> 를 호출하여 변경 내용을 커밋합니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-121">To `Delete` an item, remove the item from the collection to which it belongs, and then call <xref:System.Data.Linq.DataContext.SubmitChanges%2A> on the <xref:System.Data.Linq.DataContext> to commit the change.</span></span>  
  
> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="4195b-122">에서는 하위 삭제 작업을 인식하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-122">does not recognize cascade-delete operations.</span></span> <span data-ttu-id="4195b-123">제약 조건이 있는 테이블의 행을 삭제 하려면 [방법: 데이터베이스에서 행 삭제](how-to-delete-rows-from-the-database.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4195b-123">If you want to delete a row in a table that has constraints against it, see [How to: Delete Rows From the Database](how-to-delete-rows-from-the-database.md).</span></span>  
  
 <span data-ttu-id="4195b-124">다음 예제에서는 `CustomerID` 가 `98128` 인 고객이 데이터베이스에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-124">In the following example, the customer who has `CustomerID` of `98128` is retrieved from the database.</span></span> <span data-ttu-id="4195b-125">그런 다음 고객 열이 검색되었는지 확인한 후 <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> 이 호출되어 컬렉션에서 개체가 제거됩니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-125">Then, after confirming that the customer row was retrieved, <xref:System.Data.Linq.Table%601.DeleteOnSubmit%2A> is called to remove that object from the collection.</span></span> <span data-ttu-id="4195b-126">마지막으로 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 가 호출되어 삭제 내용을 데이터베이스로 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="4195b-126">Finally, <xref:System.Data.Linq.DataContext.SubmitChanges%2A> is called to forward the deletion to the database.</span></span>  
  
 [!code-csharp[DLinqGettingStarted#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqGettingStarted/cs/Program.cs#4)]
 [!code-vb[DLinqGettingStarted#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqGettingStarted/vb/Module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="4195b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4195b-127">See also</span></span>

- [<span data-ttu-id="4195b-128">프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="4195b-128">Programming Guide</span></span>](programming-guide.md)
- [<span data-ttu-id="4195b-129">LINQ to SQL 개체 모델</span><span class="sxs-lookup"><span data-stu-id="4195b-129">The LINQ to SQL Object Model</span></span>](the-linq-to-sql-object-model.md)
- [<span data-ttu-id="4195b-130">시작</span><span class="sxs-lookup"><span data-stu-id="4195b-130">Getting Started</span></span>](getting-started.md)
