---
description: ADO.NET 및 LINQ to SQL에 대해 자세히 알아보세요.
title: ADO.NET 및 LINQ to SQL
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 49ac6da0-f2e1-46fa-963e-1b6dcb63fef7
ms.openlocfilehash: 1f3f4a50c13af857ecd9f3195c7f431dd46ed3ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99712963"
---
# <a name="adonet-and-linq-to-sql"></a><span data-ttu-id="6061d-103">ADO.NET 및 LINQ to SQL</span><span class="sxs-lookup"><span data-stu-id="6061d-103">ADO.NET and LINQ to SQL</span></span>

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="6061d-104">는 ADO.NET 기술 제품군의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-104">is part of the ADO.NET family of technologies.</span></span> <span data-ttu-id="6061d-105">ADO.NET 공급자 모델에서 제공 하는 서비스를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-105">It is based on services provided by the ADO.NET provider model.</span></span> <span data-ttu-id="6061d-106">따라서 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 기존 ADO.NET 응용 프로그램과 코드를 혼합 하 고 현재 ADO.NET 솔루션을로 마이그레이션할 수 있습니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6061d-106">You can therefore mix [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] code with existing ADO.NET applications and migrate current ADO.NET solutions to [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)].</span></span> <span data-ttu-id="6061d-107">다음 그림에서는 이 관계를 간략하게 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-107">The following illustration provides a high-level view of the relationship.</span></span>  
  
 <span data-ttu-id="6061d-108">![LINQ to SQL 및 ADO.NET](./media/dlinq-3.png "DLinq_3")</span><span class="sxs-lookup"><span data-stu-id="6061d-108">![LINQ to SQL and ADO.NET](./media/dlinq-3.png "DLinq_3")</span></span>  
  
## <a name="connections"></a><span data-ttu-id="6061d-109">Connections</span><span class="sxs-lookup"><span data-stu-id="6061d-109">Connections</span></span>  

 <span data-ttu-id="6061d-110">를 만들 때 기존 ADO.NET 연결을 제공할 수 있습니다 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext> .</span><span class="sxs-lookup"><span data-stu-id="6061d-110">You can supply an existing ADO.NET connection when you create a [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <xref:System.Data.Linq.DataContext>.</span></span> <span data-ttu-id="6061d-111">쿼리를 포함한 <xref:System.Data.Linq.DataContext>에 대한 모든 작업은 제공된 이 연결을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-111">All operations against the <xref:System.Data.Linq.DataContext> (including queries) use this provided connection.</span></span> <span data-ttu-id="6061d-112">연결이 이미 열려 있는 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 사용자의 작업이 끝났을 때 연결을 그대로 둡니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-112">If the connection is already open, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] leaves it as is when you are finished with it.</span></span>  
  
 [!code-csharp[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCommunicatingWithDatabase/cs/Program.cs#4)]
 [!code-vb[DLinqCommunicatingWithDatabase#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCommunicatingWithDatabase/vb/Module1.vb#4)]  
  
 <span data-ttu-id="6061d-113">다음 코드와 같이 <xref:System.Data.Linq.DataContext.Connection%2A> 속성을 사용하여 항상 연결에 액세스하고 연결을 닫을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-113">You can always access the connection and close it yourself by using the <xref:System.Data.Linq.DataContext.Connection%2A> property, as in the following code:</span></span>  
  
 [!code-csharp[DLinqAdoNet#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#1)]
 [!code-vb[DLinqAdoNet#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#1)]  
  
## <a name="transactions"></a><span data-ttu-id="6061d-114">트랜잭션</span><span class="sxs-lookup"><span data-stu-id="6061d-114">Transactions</span></span>  

 <span data-ttu-id="6061d-115">애플리케이션에서 이미 고유한 데이터베이스 트랜잭션을 시작했으며 <xref:System.Data.Linq.DataContext>를 관련시키려는 경우 해당 트랜잭션을 <xref:System.Data.Linq.DataContext>에 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-115">You can supply your <xref:System.Data.Linq.DataContext> with your own database transaction when your application has already initiated the transaction and you want your <xref:System.Data.Linq.DataContext> to be involved.</span></span>  
  
 <span data-ttu-id="6061d-116">.NET Framework를 사용 하 여 트랜잭션을 수행 하는 기본 방법은 개체를 사용 하는 것입니다 <xref:System.Transactions.TransactionScope> .</span><span class="sxs-lookup"><span data-stu-id="6061d-116">The preferred method of doing transactions with the .NET Framework is to use the <xref:System.Transactions.TransactionScope> object.</span></span> <span data-ttu-id="6061d-117">이 방법을 사용하면 데이터베이스 및 다른 메모리 상주 리소스 관리자 사이에서 작동하는 분산 트랜잭션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-117">By using this approach, you can make distributed transactions that work across databases and other memory-resident resource managers.</span></span> <span data-ttu-id="6061d-118">트랜잭션 범위는 시작하는 데 리소스가 거의 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-118">Transaction scopes require few resources to start.</span></span> <span data-ttu-id="6061d-119">트랜잭션 범위는 해당 범위 내에 여러 연결이 있는 경우에만 분산 트랜잭션으로 승격됩니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-119">They promote themselves to distributed transactions only when there are multiple connections within the scope of the transaction.</span></span>  
  
 [!code-csharp[DLinqAdoNet#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#2)]
 [!code-vb[DLinqAdoNet#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#2)]  
  
 <span data-ttu-id="6061d-120">이 방법을 모든 데이터베이스에 사용할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-120">You cannot use this approach for all databases.</span></span> <span data-ttu-id="6061d-121">예를 들어 SQL Server 2000 서버에 대해 작동 하는 경우 SqlClient 연결은 시스템 트랜잭션을 승격할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-121">For example, the SqlClient connection cannot promote system transactions when it works against a SQL Server 2000 server.</span></span> <span data-ttu-id="6061d-122">대신에 사용 중인 트랜잭션 범위가 있을 때마다 완전한 분산 트랜잭션에 자동으로 참여합니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-122">Instead, it automatically enlists to a full, distributed transaction whenever it sees a transaction scope being used.</span></span>  
  
## <a name="direct-sql-commands"></a><span data-ttu-id="6061d-123">SQL 명령 직접 실행</span><span class="sxs-lookup"><span data-stu-id="6061d-123">Direct SQL Commands</span></span>  

 <span data-ttu-id="6061d-124"><xref:System.Data.Linq.DataContext>를 사용하여 변경 내용을 쿼리하거나 전송하는 기능으로는 원하는 특수한 작업을 수행할 수 없는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-124">At times you can encounter situations where the ability of the <xref:System.Data.Linq.DataContext> to query or submit changes is insufficient for the specialized task you want to perform.</span></span> <span data-ttu-id="6061d-125">이러한 상황에서는 <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> 메서드를 사용하여 SQL 명령을 데이터베이스에 대해 실행하고 쿼리 결과를 개체로 변환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-125">In these circumstances you can use the <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method to issue SQL commands to the database and convert the query results to objects.</span></span>  
  
 <span data-ttu-id="6061d-126">예를 들어 `Customer` 클래스의 데이터가 두 개의 테이블(customer1 및 customer2)에 퍼져 있다고 가정해 봅니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-126">For example, assume that the data for the `Customer` class is spread over two tables (customer1 and customer2).</span></span> <span data-ttu-id="6061d-127">다음 쿼리는 `Customer` 개체의 시퀀스를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-127">The following query returns a sequence of `Customer` objects:</span></span>  
  
 [!code-csharp[DLinqAdoNet#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#3)]
 [!code-vb[DLinqAdoNet#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#3)]  
  
 <span data-ttu-id="6061d-128">표 형식 결과의 열 이름이 엔터티 클래스의 열 속성과 일치할 경우 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]은 모든 SQL 쿼리에서 개체를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-128">As long as the column names in the tabular results match column properties of your entity class, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] creates your objects out of any SQL query.</span></span>  
  
### <a name="parameters"></a><span data-ttu-id="6061d-129">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6061d-129">Parameters</span></span>  

 <span data-ttu-id="6061d-130"><xref:System.Data.Linq.DataContext.ExecuteQuery%2A> 메서드에서는 매개 변수가 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-130">The <xref:System.Data.Linq.DataContext.ExecuteQuery%2A> method accepts parameters.</span></span> <span data-ttu-id="6061d-131">다음 코드는 매개 변수화된 쿼리를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-131">The following code executes a parameterized query:</span></span>  
  
 [!code-csharp[DlinqAdoNet#4](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqAdoNet/cs/Program.cs#4)]
 [!code-vb[DlinqAdoNet#4](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqAdoNet/vb/Module1.vb#4)]  
  
> [!NOTE]
> <span data-ttu-id="6061d-132">매개 변수는 `Console.WriteLine()` 및 `String.Format()`에서 사용되는 동일한 중괄호 표기법을 사용하여 쿼리 텍스트에서 표현됩니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-132">Parameters are expressed in the query text by using the same curly notation used by `Console.WriteLine()` and `String.Format()`.</span></span> <span data-ttu-id="6061d-133">`String.Format()`은 제공된 쿼리 문자열을 가지며 중괄호로 묶인 매개 변수를 `@p0`, `@p1` …, `@p(n)` 등과 같은 생성된 매개 변수 이름으로 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="6061d-133">`String.Format()` takes the query string you provide and substitutes the curly-braced parameters with generated parameter names such as `@p0`, `@p1` …, `@p(n)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6061d-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6061d-134">See also</span></span>

- [<span data-ttu-id="6061d-135">배경 정보</span><span class="sxs-lookup"><span data-stu-id="6061d-135">Background Information</span></span>](background-information.md)
- [<span data-ttu-id="6061d-136">방법: ADO.NET 명령 및 DataContext 간의 연결 다시 사용</span><span class="sxs-lookup"><span data-stu-id="6061d-136">How to: Reuse a Connection Between an ADO.NET Command and a DataContext</span></span>](how-to-reuse-a-connection-between-an-ado-net-command-and-a-datacontext.md)
