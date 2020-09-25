---
title: SQL Server에서 데이터베이스 미러링
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 89befaff-bb46-4290-8382-e67cdb0e3de9
ms.openlocfilehash: 7e2c1c8ea1cbc1bb22452b9ef9d1f250c96118ea
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91173538"
---
# <a name="database-mirroring-in-sql-server"></a><span data-ttu-id="954ed-102">SQL Server에서 데이터베이스 미러링</span><span class="sxs-lookup"><span data-stu-id="954ed-102">Database Mirroring in SQL Server</span></span>

<span data-ttu-id="954ed-103">SQL Server의 데이터베이스 미러링을 사용하면 대기 서버에서 SQL Server 데이터베이스의 복사본, 즉 미러를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-103">Database mirroring in SQL Server allows you to keep a copy, or mirror, of a SQL Server database on a standby server.</span></span> <span data-ttu-id="954ed-104">미러링을 사용하면 별도의 데이터 복사본 두 개가 항상 존재하여 높은 가용성과 완전한 데이터 중복성을 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-104">Mirroring ensures that two separate copies of the data exist at all times, providing high availability and complete data redundancy.</span></span> <span data-ttu-id="954ed-105">.NET Data Provider for SQL Server에서는 데이터베이스 미러링을 암시적으로 지원하므로 SQL Server 데이터베이스에 대해 미러링이 구성되고 나면 개발자가 별도의 동작을 수행하거나 코드를 작성할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-105">The .NET Data Provider for SQL Server provides implicit support for database mirroring, so that the developer does not need to take any action or write any code once it has been configured for a SQL Server database.</span></span> <span data-ttu-id="954ed-106">또한 <xref:System.Data.SqlClient.SqlConnection> 개체는 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>에서의 장애 조치(failover) 파트너 서버 이름 제공을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-106">In addition, the <xref:System.Data.SqlClient.SqlConnection> object supports an explicit connection mode that allows supplying the name of a failover partner server in the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="954ed-107">미러링용으로 구성된 데이터베이스를 대상으로 하는 <xref:System.Data.SqlClient.SqlConnection> 개체에 대하여 다음과 같은 간단한 이벤트 시퀀스가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-107">The following simplified sequence of events occurs for a <xref:System.Data.SqlClient.SqlConnection> object that targets a database configured for mirroring:</span></span>  
  
1. <span data-ttu-id="954ed-108">클라이언트 애플리케이션이 주 데이터베이스에 성공적으로 연결되고 서버에서 파트너 서버의 이름을 다시 보냅니다(클라이언트에 캐시됨).</span><span class="sxs-lookup"><span data-stu-id="954ed-108">The client application successfully connects to the principal database, and the server sends back the name of the partner server, which is then cached on the client.</span></span>  
  
2. <span data-ttu-id="954ed-109">주 데이터베이스가 포함된 서버가 실패하거나 연결이 중단되면 연결 및 트랜잭션 상태가 손실됩니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-109">If the server containing the principal database fails or connectivity is interrupted, connection and transaction state is lost.</span></span> <span data-ttu-id="954ed-110">클라이언트 애플리케이션은 주 데이터베이스에 대한 연결을 다시 설정하려고 시도하고 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-110">The client application attempts to re-establish a connection to the principal database and fails.</span></span>  
  
3. <span data-ttu-id="954ed-111">그런 다음 클라이언트 애플리케이션은 파트너 서버에서 미러 데이터베이스에 대한 연결을 투명하게 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-111">The client application then transparently attempts to establish a connection to the mirror database on the partner server.</span></span> <span data-ttu-id="954ed-112">성공하면 연결이 미러 데이터베이스로 리디렉션되고, 그러면 새로운 주 데이터베이스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-112">If it succeeds, the connection is redirected to the mirror database, which then becomes the new principal database.</span></span>  
  
## <a name="specifying-the-failover-partner-in-the-connection-string"></a><span data-ttu-id="954ed-113">연결 문자열에 장애 조치 파트너 지정</span><span class="sxs-lookup"><span data-stu-id="954ed-113">Specifying the Failover Partner in the Connection String</span></span>  

 <span data-ttu-id="954ed-114">연결 문자열에 장애 조치(failover) 파트너 서버 이름을 제공하는 경우에는 클라이언트 애플리케이션이 처음 연결될 때 주 데이터베이스를 사용할 수 없다면 클라이언트는 장애 조치(failover) 파트너와의 연결을 투명하게 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-114">If you supply the name of a failover partner server in the connection string, the client will transparently attempt a connection with the failover partner if the principal database is unavailable when the client application first connects.</span></span>  
  
```csharp
";Failover Partner=PartnerServerName"  
```  
  
 <span data-ttu-id="954ed-115">장애 조치(failover) 파트너 서버의 이름을 생략하고 클라이언트 애플리케이션이 처음 연결될 때 주 데이터베이스를 사용할 수 없다면 <xref:System.Data.SqlClient.SqlException>이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-115">If you omit the name of the failover partner server and the principal database is unavailable when the client application first connects then a <xref:System.Data.SqlClient.SqlException> is raised.</span></span>  
  
 <span data-ttu-id="954ed-116"><xref:System.Data.SqlClient.SqlConnection>이 성공적으로 열리면 서버에서 장애 조치(failover) 파트너의 이름이 반환되어 연결 문자열에 제공된 모든 값을 대체합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-116">When a <xref:System.Data.SqlClient.SqlConnection> is successfully opened, the failover partner name is returned by the server and supersedes any values supplied in the connection string.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="954ed-117">데이터베이스 미러링 시나리오의 경우 연결 문자열에 초기 카탈로그 또는 데이터베이스 이름을 명시적으로 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-117">You must explicitly specify the initial catalog or database name in the connection string for database mirroring scenarios.</span></span> <span data-ttu-id="954ed-118">클라이언트에서 명시적으로 지정된 초기 카탈로그 또는 데이터베이스가 없는 연결에 대한 장애 조치 정보를 받으면 장애 조치 정보가 캐시되지 않고 주 서버가 실패해도 애플리케이션에서 장애 조치를 시도하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-118">If the client receives failover information on a connection that doesn't have an explicitly specified initial catalog or database, the failover information is not cached and the application does not attempt to fail over if the principal server fails.</span></span> <span data-ttu-id="954ed-119">연결 문자열에 장애 조치(failover) 파트너에 대한 값은 있지만 초기 카탈로그 또는 데이터베이스에 대한 값이 없는 경우에는 `InvalidArgumentException`이 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-119">If a connection string has a value for the failover partner, but no value for the initial catalog or database, an `InvalidArgumentException` is raised.</span></span>  
  
## <a name="retrieving-the-current-server-name"></a><span data-ttu-id="954ed-120">현재 서버 이름 검색</span><span class="sxs-lookup"><span data-stu-id="954ed-120">Retrieving the Current Server Name</span></span>  

 <span data-ttu-id="954ed-121">장애 조치(failover) 시 <xref:System.Data.SqlClient.SqlConnection> 개체의 <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> 속성을 사용하여 현재 연결이 실제로 연결된 서버의 이름을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-121">In the event of a failover, you can retrieve the name of the server to which the current connection is actually connected by using the <xref:System.Data.SqlClient.SqlConnection.DataSource%2A> property of a <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="954ed-122">다음 코드 조각은 연결 변수가 열린 <xref:System.Data.SqlClient.SqlConnection>을 참조한다고 가정하여 활성 서버의 이름을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-122">The following code fragment retrieves the name of the active server, assuming that the connection variable references an open <xref:System.Data.SqlClient.SqlConnection>.</span></span>  
  
 <span data-ttu-id="954ed-123">장애 조치 이벤트가 발생하고 연결이 미러 서버로 전환되면 **DataSource** 속성이 업데이트되며 미러 이름을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-123">When a failover event occurs and the connection is switched to the mirror server, the **DataSource** property is updated to reflect the mirror name.</span></span>  
  
```vb  
Dim activeServer As String = connection.DataSource  
```  
  
```csharp  
string activeServer = connection.DataSource;  
```  
  
## <a name="sqlclient-mirroring-behavior"></a><span data-ttu-id="954ed-124">SqlClient 미러링 동작</span><span class="sxs-lookup"><span data-stu-id="954ed-124">SqlClient Mirroring Behavior</span></span>  

 <span data-ttu-id="954ed-125">클라이언트는 항상 현재 주 서버에 연결을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-125">The client always tries to connect to the current principal server.</span></span> <span data-ttu-id="954ed-126">실패하면 장애 조치(failover) 파트너로 연결을 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-126">If it fails, it tries the failover partner.</span></span> <span data-ttu-id="954ed-127">미러 데이터베이스가 파트너 서버의 주 역할로 이미 전환된 경우에는 연결이 성공하고 새로운 주-미러 매핑이 클라이언트로 전송되며 호출 <xref:System.AppDomain>의 수명 동안 캐시됩니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-127">If the mirror database has already been switched to the principal role on the partner server, the connection succeeds and the new principal-mirror mapping is sent to the client and cached for the lifetime of the calling <xref:System.AppDomain>.</span></span> <span data-ttu-id="954ed-128">이 매핑은 영구 스토리지에 저장되지 않으므로 다른 **AppDomain** 또는 프로세스의 후속 연결에는 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-128">It is not stored in persistent storage and is not available for subsequent connections in a different **AppDomain** or process.</span></span> <span data-ttu-id="954ed-129">그러나 동일한 **AppDomain** 내에서의 후속 연결에는 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-129">However, it is available for subsequent connections within the same **AppDomain**.</span></span> <span data-ttu-id="954ed-130">같거나 다른 컴퓨터에서 실행되는 다른 **AppDomain** 또는 프로세스에는 항상 연결 풀이 있으며 이러한 연결은 다시 설정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-130">Note that another **AppDomain** or process running on the same or a different computer always has its pool of connections, and those connections are not reset.</span></span> <span data-ttu-id="954ed-131">이 경우 주 데이터베이스가 다운되면 각 프로세스 또는 **AppDomain**이 실패하고 나서 풀이 자동으로 지워집니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-131">In that case, if the primary database goes down, each process or **AppDomain** fails once, and the pool is automatically cleared.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="954ed-132">서버에서의 미러링 지원은 데이터베이스별로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-132">Mirroring support on the server is configured on a per-database basis.</span></span> <span data-ttu-id="954ed-133">다중 파트 이름을 사용하거나 현재 데이터베이스를 변경하는 방식으로 주/미러 집합에 포함되지 않은 다른 데이터베이스에 대해 데이터 조작 작업이 실행되는 경우, 이러한 다른 데이터베이스에 대한 변경 내용은 실패 시 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-133">If data manipulation operations are executed against other databases not included in the principal/mirror set, either by using multipart names or by changing the current database, the changes to these other databases do not propagate in the event of failure.</span></span> <span data-ttu-id="954ed-134">미러되지 않은 데이터베이스에서 데이터가 수정되는 경우에는 오류가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-134">No error is generated when data is modified in a database that is not mirrored.</span></span> <span data-ttu-id="954ed-135">개발자는 이러한 작업이 미칠 수 있는 영향을 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-135">The developer must evaluate the possible impact of such operations.</span></span>  
  
## <a name="database-mirroring-resources"></a><span data-ttu-id="954ed-136">데이터베이스 미러링 리소스</span><span class="sxs-lookup"><span data-stu-id="954ed-136">Database Mirroring Resources</span></span>  

 <span data-ttu-id="954ed-137">미러링 구성, 배포 및 관리에 대한 개념 설명서 및 정보를 보려면 SQL Server 설명서에서 다음 리소스를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="954ed-137">For conceptual documentation and information on configuring, deploying and administering mirroring, see the following resources in SQL Server documentation.</span></span>  
  
|<span data-ttu-id="954ed-138">리소스</span><span class="sxs-lookup"><span data-stu-id="954ed-138">Resource</span></span>|<span data-ttu-id="954ed-139">설명</span><span class="sxs-lookup"><span data-stu-id="954ed-139">Description</span></span>|  
|--------------|-----------------|  
|[<span data-ttu-id="954ed-140">데이터베이스 미러링</span><span class="sxs-lookup"><span data-stu-id="954ed-140">Database Mirroring</span></span>](/sql/database-engine/database-mirroring/database-mirroring-sql-server)|<span data-ttu-id="954ed-141">SQL Server에서 미러링을 설정 및 구성하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="954ed-141">Describes how to set up and configure mirroring in SQL Server.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="954ed-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="954ed-142">See also</span></span>

- [<span data-ttu-id="954ed-143">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="954ed-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
