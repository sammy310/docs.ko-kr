---
description: '자세히 알아보기: 방법: 정보 쿼리'
title: '방법: 정보 쿼리'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e538d288-2070-40ca-9da6-4fbc68cd6ad0
ms.openlocfilehash: 41774834fe919b28d71691203941cb8e0a8a0397
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802023"
---
# <a name="how-to-query-for-information"></a><span data-ttu-id="3d675-103">방법: 정보 쿼리</span><span class="sxs-lookup"><span data-stu-id="3d675-103">How to: Query for Information</span></span>

<span data-ttu-id="3d675-104">의 쿼리 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 는 LINQ의 쿼리와 동일한 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3d675-104">Queries in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] use the same syntax as queries in LINQ.</span></span> <span data-ttu-id="3d675-105">유일한 차이점은 쿼리에서 참조 된 개체가 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 데이터베이스의 요소에 매핑되는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3d675-105">The only difference is that the objects referenced in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] queries are mapped to elements in a database.</span></span> <span data-ttu-id="3d675-106">자세한 내용은 [LINQ 쿼리 소개(C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="3d675-106">For more information, see [Introduction to LINQ Queries (C#)](../../../../../csharp/programming-guide/concepts/linq/introduction-to-linq-queries.md).</span></span>  
  
 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]<span data-ttu-id="3d675-107">에서는 작성한 쿼리를 해당 SQL 쿼리로 변환하고 SQL Server에 전달하여 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3d675-107">translates the queries you write into equivalent SQL queries and sends them to the server for processing.</span></span>  
  
 <span data-ttu-id="3d675-108">LINQ 쿼리의 일부 기능은 응용 프로그램에서 특별 한 주의가 필요할 수 있습니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="3d675-108">Some features of LINQ queries might need special attention in [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] applications.</span></span> <span data-ttu-id="3d675-109">자세한 내용은 [쿼리 개념](query-concepts.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3d675-109">For more information, see [Query Concepts](query-concepts.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="3d675-110">예제</span><span class="sxs-lookup"><span data-stu-id="3d675-110">Example</span></span>  

 <span data-ttu-id="3d675-111">다음 쿼리에서는 London의 고객 목록을 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="3d675-111">The following query asks for a list of customers from London.</span></span> <span data-ttu-id="3d675-112">이 예제에서 `Customers`는 Northwind 샘플 데이터베이스의 테이블입니다.</span><span class="sxs-lookup"><span data-stu-id="3d675-112">In this example, `Customers` is a table in the Northwind sample database.</span></span>  
  
 [!code-csharp[DLinqQuerying#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqQuerying/cs/Program.cs#1)]
 [!code-vb[DLinqQuerying#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqQuerying/vb/Module1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3d675-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="3d675-113">See also</span></span>

- [<span data-ttu-id="3d675-114">개체 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="3d675-114">Creating the Object Model</span></span>](creating-the-object-model.md)
- [<span data-ttu-id="3d675-115">샘플 데이터베이스 다운로드</span><span class="sxs-lookup"><span data-stu-id="3d675-115">Downloading Sample Databases</span></span>](downloading-sample-databases.md)
- [<span data-ttu-id="3d675-116">데이터베이스 쿼리</span><span class="sxs-lookup"><span data-stu-id="3d675-116">Querying the Database</span></span>](querying-the-database.md)
