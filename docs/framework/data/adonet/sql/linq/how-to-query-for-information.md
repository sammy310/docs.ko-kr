---
title: '방법: 정보 쿼리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: ed32bbe7d27357cbed7d77dd235b698a65c0e29e
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70793541"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="6c296-102">방법: 정보 쿼리</span><span class="sxs-lookup"><span data-stu-id="6c296-102">How to: Query for Information</span></span>
<span data-ttu-id="6c296-103">[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]의 쿼리는 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]의 쿼리와 동일한 구문을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6c296-103">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)].</span></span> <span data-ttu-id="6c296-104">유일한 차이점은 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 쿼리에서 참조 된 개체가 데이터베이스의 요소에 매핑되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6c296-104">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="6c296-105">자세한 내용은 [LINQ 쿼리 소개(C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c296-105">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="6c296-106">에서는 작성한 쿼리를 해당 SQL 쿼리로 변환하고 SQL Server에 전달하여 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6c296-106">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="6c296-107">[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 쿼리의 일부 기능을 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 애플리케이션에서 사용할 때 특히 주의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6c296-107">Some features of [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="6c296-108">자세한 내용은 [쿼리 개념](query-concepts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6c296-108">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="6c296-109">예제</span><span class="sxs-lookup"><span data-stu-id="6c296-109">Example</span></span>  
 <span data-ttu-id="6c296-110">다음 쿼리에서는 London의 고객 목록을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="6c296-110">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="6c296-111">이 예제에서 `Customers`는 Northwind 샘플 데이터베이스의 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="6c296-111">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="6c296-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="6c296-112">See also</span></span>

- [<span data-ttu-id="6c296-113">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="6c296-113">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="6c296-114">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="6c296-114">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="6c296-115">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="6c296-115">Querying the Database</span></span>](querying-the-database.md)
