---
description: '자세한 정보: 방법: 데이터베이스 함수 호출'
title: '방법: 데이터베이스 함수 호출'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 79038efa-15bf-464a-83e2-35fe145252ce
ms.openlocfilehash: d5c5854d375546d1604b6e27e6f757f1e126f9b4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724520"
---
# <a name="how-to-call-database-functions"></a><span data-ttu-id="eae81-103">방법: 데이터베이스 함수 호출</span><span class="sxs-lookup"><span data-stu-id="eae81-103">How to: Call Database Functions</span></span>

<span data-ttu-id="eae81-104"><xref:System.Data.Objects.SqlClient.SqlFunctions> 클래스에는 LINQ to Entities 쿼리에 사용할 SQL Server 함수를 노출하는 메서드가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-104">The <xref:System.Data.Objects.SqlClient.SqlFunctions> class contains methods that expose SQL Server functions to use in LINQ to Entities queries.</span></span> <span data-ttu-id="eae81-105">LINQ to Entities 쿼리에서 <xref:System.Data.Objects.SqlClient.SqlFunctions> 메서드를 사용할 때 해당되는 데이터베이스 함수가 데이터베이스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-105">When you use <xref:System.Data.Objects.SqlClient.SqlFunctions> methods in LINQ to Entities queries, the corresponding database functions are executed in the database.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eae81-106">값 집합에 대한 계산을 수행하고 집계 데이터베이스 함수라고도 하는 단일 값을 반환하는 데이터베이스 함수를 직접 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-106">Database functions that perform a calculation on a set of values and return a single value (also known as aggregate database functions) can be directly invoked.</span></span> <span data-ttu-id="eae81-107">기타 정식 함수는 LINQ to Entities 쿼리의 일부로만 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-107">Other canonical functions can only be called as part of a LINQ to Entities query.</span></span> <span data-ttu-id="eae81-108">집계 함수를 직접 호출하려면 <xref:System.Data.Objects.ObjectQuery%601>를 함수로 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-108">To call an aggregate function directly, you must pass an <xref:System.Data.Objects.ObjectQuery%601> to the function.</span></span> <span data-ttu-id="eae81-109">자세한 내용은 아래 두 번째 예제를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="eae81-109">For more information, see the second example below.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="eae81-110"><xref:System.Data.Objects.SqlClient.SqlFunctions> 클래스의 메서드는 SQL Server 함수와 관련되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-110">The methods in the <xref:System.Data.Objects.SqlClient.SqlFunctions> class are specific to SQL Server functions.</span></span> <span data-ttu-id="eae81-111">데이터베이스 함수를 노출하는 유사한 클래스가 다른 공급자를 통해 제공될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-111">Similar classes that expose database functions may be available through other providers.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eae81-112">예제</span><span class="sxs-lookup"><span data-stu-id="eae81-112">Example</span></span>  

 <span data-ttu-id="eae81-113">다음 예에서는 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-113">The following example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="eae81-114">이 예제에서는 <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> 메서드를 사용하여 성이 "Si"로 시작하는 모든 담당자를 반환하는 LINQ to Entities 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-114">The example executes a LINQ to Entities query that uses the <xref:System.Data.Objects.SqlClient.SqlFunctions.CharIndex%2A> method to return all contacts whose last name starts with "Si":</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#3)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#3)]  
  
## <a name="example"></a><span data-ttu-id="eae81-115">예제</span><span class="sxs-lookup"><span data-stu-id="eae81-115">Example</span></span>  

 <span data-ttu-id="eae81-116">다음 예에서는 [AdventureWorks Sales 모델](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks)을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-116">The following example uses the [AdventureWorks Sales Model](https://github.com/Microsoft/sql-server-samples/releases/tag/adventureworks).</span></span> <span data-ttu-id="eae81-117">이 예제에서는 집계 <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> 메서드를 직접 호출합니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-117">The example calls the aggregate <xref:System.Data.Objects.SqlClient.SqlFunctions.ChecksumAggregate%2A> method directly.</span></span> <span data-ttu-id="eae81-118"><xref:System.Data.Objects.ObjectQuery%601>는 LINQ to Entities 쿼리에 포함되지 않고 호출되도록 지정하는 함수로 전달됩니다.</span><span class="sxs-lookup"><span data-stu-id="eae81-118">Note that an <xref:System.Data.Objects.ObjectQuery%601> is passed to the function, which allows it to be called without being part of a LINQ to Entities query.</span></span>  
  
 [!code-csharp[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/dp l2e canonicalandstorefunctions/cs/program.cs#4)]
 [!code-vb[DP L2E CanonicalAndStoreFunctions#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/dp l2e canonicalandstorefunctions/vb/module1.vb#4)]  
  
## <a name="see-also"></a><span data-ttu-id="eae81-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="eae81-119">See also</span></span>

- [<span data-ttu-id="eae81-120">LINQ to Entities 쿼리에서 함수 호출</span><span class="sxs-lookup"><span data-stu-id="eae81-120">Calling Functions in LINQ to Entities Queries</span></span>](calling-functions-in-linq-to-entities-queries.md)
- [<span data-ttu-id="eae81-121">LINQ to Entities에서 쿼리</span><span class="sxs-lookup"><span data-stu-id="eae81-121">Queries in LINQ to Entities</span></span>](queries-in-linq-to-entities.md)
