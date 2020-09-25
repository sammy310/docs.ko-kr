---
title: 고가용성 및 재해 복구에 대한 SqlClient 지원
description: AlwaysOn 가용성 그룹를 사용 하 여 SQL Server의 고가용성, 재해 복구에 대 한 SqlClient 응용 프로그램 지원에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 61e0b396-09d7-4e13-9711-7dcbcbd103a0
ms.openlocfilehash: 7693210b7d9387e9b58fcc95febd3df0c70b4743
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203438"
---
# <a name="sqlclient-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="06e7b-103">고가용성 및 재해 복구에 대한 SqlClient 지원</span><span class="sxs-lookup"><span data-stu-id="06e7b-103">SqlClient Support for High Availability, Disaster Recovery</span></span>

<span data-ttu-id="06e7b-104">이 항목에서는 고가용성, 재해 복구에 대 한 SqlClient 지원 (.NET Framework 4.5에 추가 됨)에 대해 설명 합니다 (AlwaysOn 가용성 그룹.</span><span class="sxs-lookup"><span data-stu-id="06e7b-104">This topic discusses SqlClient support (added in .NET Framework 4.5) for high-availability, disaster recovery -- AlwaysOn Availability Groups.</span></span>  <span data-ttu-id="06e7b-105">SQL Server 2012에는 AlwaysOn 가용성 그룹 기능이 추가되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-105">AlwaysOn Availability Groups feature was added to SQL Server 2012.</span></span> <span data-ttu-id="06e7b-106">AlwaysOn 가용성 그룹에 대한 자세한 내용은 SQL Server 온라인 설명서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06e7b-106">For more information about AlwaysOn Availability Groups, see SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="06e7b-107">이제 연결 속성에 고가용성 재해 복구 AG(가용성 그룹)의 가용성 그룹 수신기 또는 SQL Server 2012 장애 조치(Failover) 클러스터 인스턴스를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-107">You can now specify the availability group listener of a (high-availability, disaster-recovery) availability group (AG) or SQL Server 2012 Failover Cluster Instance in the connection property.</span></span> <span data-ttu-id="06e7b-108">SqlClient 애플리케이션이 장애 조치되는 AlwaysOn 데이터베이스에 연결되는 경우 장애 조치 후 작업을 계속하기 위해 원래 연결이 끊어지고 애플리케이션은 새 연결을 열어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-108">If a SqlClient application is connected to an AlwaysOn database that fails over, the original connection is broken and the application must open a new connection to continue work after the failover.</span></span>  
  
 <span data-ttu-id="06e7b-109">가용성 그룹 수신기 또는 SQL Server 2012 장애 조치 클러스터 인스턴스에 연결하지 않는 경우와 여러 IP 주소가 하나의 호스트 이름에 연결되어 있는 경우에는 SqlClient가 DNS 항목과 연결된 모든 IP 주소를 순차적으로 반복합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-109">If you are not connecting to an availability group listener or SQL Server 2012 Failover Cluster Instance, and if multiple IP addresses are associated with a hostname, SqlClient will iterate sequentially through all IP addresses associated with DNS entry.</span></span> <span data-ttu-id="06e7b-110">DNS 서버가 반환한 첫 번째 IP 주소가 NIC(네트워크 인터페이스 카드)에 바인딩되지 않은 경우 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-110">This can be time consuming if the first IP address returned by DNS server is not bound to any network interface card (NIC).</span></span> <span data-ttu-id="06e7b-111">가용성 그룹 수신기 또는 SQL Server 2012 장애 조치 클러스터 인스턴스에 연결할 때 SqlClient는 모든 IP 주소에 병렬로 연결하려고 시도하며 연결에 성공할 경우 드라이버는 보류 중인 연결 시도를 모두 취소합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-111">When connecting to an availability group listener or SQL Server 2012 Failover Cluster Instance, SqlClient attempts to establish connections to all IP addresses in parallel and if a connection attempt succeeds, the driver will discard any pending connection attempts.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="06e7b-112">연결 제한 시간을 늘리고 연결 재시도 논리를 구현하면 애플리케이션이 가용성 그룹에 연결될 가능성이 증가합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-112">Increasing connection timeout and implementing connection retry logic will increase the probability that an application will connect to an availability group.</span></span> <span data-ttu-id="06e7b-113">또한 장애 조치(failover)로 인해 연결이 실패할 수 있으므로 실패한 연결을 다시 연결할 때까지 다시 시도하는 연결 재시도 논리를 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-113">Also, because a connection can fail because of a failover, you should implement connection retry logic, retrying a failed connection until it reconnects.</span></span>  
  
 <span data-ttu-id="06e7b-114">.NET Framework 4.5의 SqlClient에 다음 연결 속성이 추가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-114">The following connection properties were added to SqlClient in .NET Framework 4.5:</span></span>  
  
- `ApplicationIntent`  
  
- `MultiSubnetFailover`  
  
 <span data-ttu-id="06e7b-115">다음과 같은 방법으로 프로그래밍 방식으로 이러한 연결 문자열 키워드를 수정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-115">You can programmatically modify these connection string keywords with:</span></span>  
  
1. <xref:System.Data.SqlClient.SqlConnectionStringBuilder.ApplicationIntent%2A>  
  
2. <xref:System.Data.SqlClient.SqlConnectionStringBuilder.MultiSubnetFailover%2A>  

> [!NOTE]
> <span data-ttu-id="06e7b-116">`MultiSubnetFailover` `true` .NET Framework 4.6.1 이상 버전에서는로 설정 하지 않아도 됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-116">Setting `MultiSubnetFailover` to `true` isn't required with .NET Framework 4.6.1 or later versions.</span></span>
  
## <a name="connecting-with-multisubnetfailover"></a><span data-ttu-id="06e7b-117">MultiSubnetFailover로 연결</span><span class="sxs-lookup"><span data-stu-id="06e7b-117">Connecting With MultiSubnetFailover</span></span>  

 <span data-ttu-id="06e7b-118">SQL Server 2012 가용성 그룹 수신기 또는 SQL Server 2012 장애 조치(Failover) 클러스터 인스턴스에 연결할 때는 항상 `MultiSubnetFailover=True`를 지정하십시오.</span><span class="sxs-lookup"><span data-stu-id="06e7b-118">Always specify `MultiSubnetFailover=True` when connecting to a SQL Server 2012 availability group listener or SQL Server 2012 Failover Cluster Instance.</span></span> <span data-ttu-id="06e7b-119">`MultiSubnetFailover`를 사용하면 SQL Server 2012에서 모든 가용성 그룹 및 장애 조치(Failover) 클러스터 인스턴스에 대한 장애 조치(Failover)를 빠르게 수행하고 단일 및 다중 서브넷 AlwaysOn 토폴로지에 대한 장애 조치(Failover) 시간을 크게 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-119">`MultiSubnetFailover` enables faster failover for all Availability Groups and or Failover Cluster Instance in SQL Server 2012 and will significantly reduce failover time for single and multi-subnet AlwaysOn topologies.</span></span> <span data-ttu-id="06e7b-120">다중 서브넷 장애 조치(Failover) 중에는 클라이언트가 연결을 병렬로 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-120">During a multi-subnet failover, the client will attempt connections in parallel.</span></span> <span data-ttu-id="06e7b-121">서브넷 장애 조치(Failover) 중에는 TCP 연결을 적극적으로 재시도합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-121">During a subnet failover, will aggressively retry the TCP connection.</span></span>  
  
 <span data-ttu-id="06e7b-122">`MultiSubnetFailover` 연결 속성은 애플리케이션이 가용성 그룹 또는 SQL Server 2012 장애 조치 클러스터 인스턴스에 배포되고 SqlClient가 모든 IP 주소에 연결하려고 시도하여 주 SQL Server 인스턴스에서 데이터베이스에 연결하려고 시도할 것임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-122">The `MultiSubnetFailover` connection property indicates that the application is being deployed in an availability group or SQL Server 2012 Failover Cluster Instance and that SqlClient will try to connect to the database on the primary SQL Server instance by trying to connect to all the IP addresses.</span></span> <span data-ttu-id="06e7b-123">연결에 대해 `MultiSubnetFailover=True`가 지정되면 클라이언트는 운영 체제의 기본 TCP 재전송 간격보다 빠르게 TCP 연결을 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-123">When `MultiSubnetFailover=True` is specified for a connection, the client retries TCP connection attempts faster than the operating system’s default TCP retransmit intervals.</span></span> <span data-ttu-id="06e7b-124">이렇게 하면 AlwaysOn 가용성 그룹 또는 AlwaysOn 장애 조치(Failover) 클러스터 인스턴스의 장애 조치(Failover) 후 더 빠르게 다시 연결할 수 있습니다. 이 설정은 단일/다중 서브넷 가용성 그룹 및 장애 조치(Failover) 클러스터 인스턴스에 모두 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-124">This enables faster reconnection after failover of either an AlwaysOn Availability Group or an AlwaysOn Failover Cluster Instance, and is applicable to both single- and multi-subnet Availability Groups and Failover Cluster Instances.</span></span>  
  
 <span data-ttu-id="06e7b-125">SqlClient의 연결 문자열 키워드에 대한 자세한 내용은 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06e7b-125">For more information about connection string keywords in SqlClient, see <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A>.</span></span>  
  
 <span data-ttu-id="06e7b-126">가용성 그룹 수신기 또는 SQL Server 2012 장애 조치 클러스터 인스턴스 이외의 대상에 연결할 때 `MultiSubnetFailover=True`를 지정하면 성능이 저하될 수 있으므로 이는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-126">Specifying `MultiSubnetFailover=True` when connecting to something other than a availability group listener or SQL Server 2012 Failover Cluster Instance may result in a negative performance impact, and is not supported.</span></span>  
  
 <span data-ttu-id="06e7b-127">다음 지침에 따라 가용성 그룹의 서버 또는 SQL Server 2012 장애조치 클러스터 인스턴스로 연결하세요.</span><span class="sxs-lookup"><span data-stu-id="06e7b-127">Use the following guidelines to connect to a server in an availability group or SQL Server 2012 Failover Cluster Instance:</span></span>  
  
- <span data-ttu-id="06e7b-128">단일 또는 다중 서브넷에 연결할 때 `MultiSubnetFailover` 연결 속성을 사용하십시오. 그러면 두 경우 모두 성능이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-128">Use the `MultiSubnetFailover` connection property when connecting to a single subnet or multi-subnet; it will improve performance for both.</span></span>  
  
- <span data-ttu-id="06e7b-129">가용성 그룹에 연결하려면 가용성 그룹에 대한 가용성 그룹 수신기를 연결 문자열의 서버로 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-129">To connect to an availability group, specify the availability group listener of the availability group as the server in your connection string.</span></span>  
  
- <span data-ttu-id="06e7b-130">IP 주소가 64개 이상으로 구성된 SQL Server 인스턴스에 연결하면 연결 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-130">Connecting to a SQL Server instance configured with more than 64 IP addresses will cause a connection failure.</span></span>  
  
- <span data-ttu-id="06e7b-131">`MultiSubnetFailover` 연결 속성을 사용하는 애플리케이션 동작은 SQL Server 인증, Kerberos 인증, Windows 인증 등의 인증 유형에 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-131">Behavior of an application that uses the `MultiSubnetFailover` connection property is not affected based on the type of authentication: SQL Server Authentication, Kerberos Authentication, or Windows Authentication.</span></span>  
  
- <span data-ttu-id="06e7b-132">장애 조치 시간을 수용하도록 `Connect Timeout` 값을 늘리고 애플리케이션 연결 재시도 횟수를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-132">Increase the value of `Connect Timeout` to accommodate for failover time and reduce application connection retry attempts.</span></span>  
  
- <span data-ttu-id="06e7b-133">분산된 트랜잭션은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-133">Distributed transactions are not supported.</span></span>  
  
 <span data-ttu-id="06e7b-134">읽기 전용 라우팅이 적용되지 않으면 다음과 같은 경우 보조 복제본 위치에 대한 연결이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-134">If read-only routing is not in effect, connecting to a secondary replica location will fail in the following situations:</span></span>  
  
1. <span data-ttu-id="06e7b-135">보조 복제본 위치가 연결을 허용하도록 구성되어 있지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="06e7b-135">If the secondary replica location is not configured to accept connections.</span></span>  
  
2. <span data-ttu-id="06e7b-136">애플리케이션에서 `ApplicationIntent=ReadWrite`(아래 설명 참조)를 사용하고 보조 복제본 위치가 읽기 전용 액세스용으로 구성되어 있는 경우</span><span class="sxs-lookup"><span data-stu-id="06e7b-136">If an application uses `ApplicationIntent=ReadWrite` (discussed below) and the secondary replica location is configured for read-only access.</span></span>  
  
 <span data-ttu-id="06e7b-137"><xref:System.Data.SqlClient.SqlDependency>는 읽기 전용 보조 복제본에서 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-137"><xref:System.Data.SqlClient.SqlDependency> is not supported on read-only secondary replicas.</span></span>  
  
 <span data-ttu-id="06e7b-138">주 복제본이 읽기 전용 작업을 거부하도록 구성되어 있고 연결 문자열에 `ApplicationIntent=ReadOnly`가 포함되어 있으면 연결이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-138">A connection will fail if a primary replica is configured to reject read-only workloads and the connection string contains `ApplicationIntent=ReadOnly`.</span></span>  
  
## <a name="upgrading-to-use-multi-subnet-clusters-from-database-mirroring"></a><span data-ttu-id="06e7b-139">데이터베이스 미러링에서 다중 서브넷 클러스터를 사용하도록 업그레이드</span><span class="sxs-lookup"><span data-stu-id="06e7b-139">Upgrading to Use Multi-Subnet Clusters from Database Mirroring</span></span>  

 <span data-ttu-id="06e7b-140">연결 문자열에 `MultiSubnetFailover` 및 `Failover Partner` 연결 키워드가 있거나 `MultiSubnetFailover=True`와 TCP가 아닌 프로토콜이 사용되면 연결 오류(<xref:System.ArgumentException>)가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-140">A connection error (<xref:System.ArgumentException>) will occur if the `MultiSubnetFailover` and `Failover Partner` connection keywords are present in the connection string, or if `MultiSubnetFailover=True` and a protocol other than TCP is used.</span></span> <span data-ttu-id="06e7b-141">`MultiSubnetFailover`가 사용되고 SQL Server에서 데이터베이스 미러링 쌍의 일부임을 나타내는 장애 조치(Failover) 파트너 응답을 반환하는 경우에도 오류(<xref:System.Data.SqlClient.SqlException>)가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-141">An error (<xref:System.Data.SqlClient.SqlException>) will also occur if `MultiSubnetFailover` is used and the SQL Server returns a failover partner response indicating it is part of a database mirroring pair.</span></span>  
  
 <span data-ttu-id="06e7b-142">현재 데이터베이스 미러링을 사용 중인 SqlClient 애플리케이션을 다중 서브넷 시나리오로 업그레이드할 경우에는 `Failover Partner` 연결 속성을 제거하고 이를 `MultiSubnetFailover`로 설정된 `True`로 바꾸고, 연결 문자열에서 서버 이름을 가용성 그룹 수신기로 바꿔야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-142">If you upgrade a SqlClient application that currently uses database mirroring to a multi-subnet scenario, you should remove the `Failover Partner` connection property and replace it with `MultiSubnetFailover` set to `True` and replace the server name in the connection string with an availability group listener.</span></span> <span data-ttu-id="06e7b-143">연결 문자열에 `Failover Partner` 및 `MultiSubnetFailover=True`가 사용될 경우 드라이버에서 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-143">If a connection string uses `Failover Partner` and `MultiSubnetFailover=True`, the driver will generate an error.</span></span> <span data-ttu-id="06e7b-144">하지만 연결 문자열에 `Failover Partner` 및 `MultiSubnetFailover=False`(또는 `ApplicationIntent=ReadWrite`)가 사용될 경우 애플리케이션에 데이터베이스 미러링이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-144">However, if a connection string uses `Failover Partner` and `MultiSubnetFailover=False` (or `ApplicationIntent=ReadWrite`), the application will use database mirroring.</span></span>  
  
 <span data-ttu-id="06e7b-145">AG의 기본 데이터베이스에서 데이터베이스 미러링이 사용되고 가용성 그룹 수신기 대신 주 데이터베이스에 연결하는 연결 문자열에 `MultiSubnetFailover=True`가 사용된 경우 드라이버에서 오류를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-145">The driver will return an error if database mirroring is used on the primary database in the AG, and if `MultiSubnetFailover=True` is used in the connection string that connects to a primary database instead of to an availability group listener.</span></span>  
  
## <a name="specifying-application-intent"></a><span data-ttu-id="06e7b-146">애플리케이션 의도 지정</span><span class="sxs-lookup"><span data-stu-id="06e7b-146">Specifying Application Intent</span></span>  

 <span data-ttu-id="06e7b-147">`ApplicationIntent=ReadOnly`인 경우 클라이언트는 AlwaysOn이 설정된 데이터베이스에 연결할 때 읽기 작업을 요청합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-147">When `ApplicationIntent=ReadOnly`, the client requests a read workload when connecting to an AlwaysOn enabled database.</span></span> <span data-ttu-id="06e7b-148">서버는 연결 시 그리고 USE 데이터베이스 문 중에 AlwaysOn이 설정된 데이터베이스에 한하여 의도를 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-148">The server will enforce the intent at connection time and during a USE database statement but only to an Always On enabled database.</span></span>  
  
 <span data-ttu-id="06e7b-149">`ApplicationIntent` 키워드는 레거시 읽기 전용 데이터베이스에 적용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-149">The `ApplicationIntent` keyword does not work with legacy, read-only databases.</span></span>  
  
 <span data-ttu-id="06e7b-150">데이터베이스는 대상 AlwaysOn 데이터베이스에 대한 읽기 작업을 허용하거나 허용하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-150">A database can allow or disallow read workloads on the targeted AlwaysOn database.</span></span> <span data-ttu-id="06e7b-151">(이 설정은 `PRIMARY_ROLE` 및 `SECONDARY_ROLE`Transact-SQL 문의 `ALLOW_CONNECTIONS` 절로 수행됩니다.)</span><span class="sxs-lookup"><span data-stu-id="06e7b-151">(This is done with the `ALLOW_CONNECTIONS` clause of the `PRIMARY_ROLE` and `SECONDARY_ROLE`Transact-SQL statements.)</span></span>  
  
 <span data-ttu-id="06e7b-152">`ApplicationIntent` 키워드는 읽기 전용 라우팅을 설정하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-152">The `ApplicationIntent` keyword is used to enable read-only routing.</span></span>  
  
## <a name="read-only-routing"></a><span data-ttu-id="06e7b-153">읽기 전용 라우팅</span><span class="sxs-lookup"><span data-stu-id="06e7b-153">Read-Only Routing</span></span>  

 <span data-ttu-id="06e7b-154">읽기 전용 라우팅은 데이터베이스의 읽기 전용 복사본의 가용성을 유지할 수 있는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-154">Read-only routing is a feature that can ensure the availability of a read only replica of a database.</span></span> <span data-ttu-id="06e7b-155">읽기 전용 라우팅을 활성화하려면:</span><span class="sxs-lookup"><span data-stu-id="06e7b-155">To enable read-only routing:</span></span>  
  
1. <span data-ttu-id="06e7b-156">AlwaysOn 가용성 그룹의 가용성 그룹 수신기에 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-156">You must connect to an Always On Availability Group availability group listener.</span></span>  
  
2. <span data-ttu-id="06e7b-157">`ApplicationIntent` 연결 문자열 키워드를 `ReadOnly`로 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-157">The `ApplicationIntent` connection string keyword must be set to `ReadOnly`.</span></span>  
  
3. <span data-ttu-id="06e7b-158">읽기 전용 라우팅을 설정하려면 데이터베이스 관리자가 가용성 그룹을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-158">The Availability Group must be configured by the database administrator to enable read-only routing.</span></span>  
  
 <span data-ttu-id="06e7b-159">읽기 전용 라우팅을 사용하는 여러 연결 중 일부가 동일한 읽기 전용 복사본에 연결되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-159">It is possible that multiple connections using read-only routing will not all connect to the same read-only replica.</span></span> <span data-ttu-id="06e7b-160">데이터베이스 동기화를 변경하거나 서버 라우팅 구성을 변경하면 클라이언트를 다른 읽기 전용 복사본에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-160">Changes in database synchronization or changes in the server's routing configuration can result in client connections to different read-only replicas.</span></span> <span data-ttu-id="06e7b-161">모든 읽기 전용 요청을 동일한 읽기 전용 복제본에 연결하려면 가용성 그룹 수신기를 `Data Source` 연결 문자열 키워드에 전달하지 마십시오.</span><span class="sxs-lookup"><span data-stu-id="06e7b-161">To ensure that all read-only requests connect to the same read-only replica, do not pass an availability group listener to the `Data Source` connection string keyword.</span></span> <span data-ttu-id="06e7b-162">대신, 읽기 전용 인스턴스의 이름을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-162">Instead, specify the name of the read-only instance.</span></span>  
  
 <span data-ttu-id="06e7b-163">읽기 전용 라우팅은 먼저 주 데이터베이스에 연결한 후 사용 가능한 최선의 읽기 가능한 보조 데이터베이스를 검색하기 때문에 주 데이터베이스에 연결할 때보다 시간이 더 많이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-163">Read-only routing may take longer than connecting to the primary because read only routing first connects to the primary and then looks for the best available readable secondary.</span></span> <span data-ttu-id="06e7b-164">따라서 로그인 제한 시간을 늘려야 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e7b-164">Because of this, you should increase your login timeout.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e7b-165">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06e7b-165">See also</span></span>

- [<span data-ttu-id="06e7b-166">SQL Server 기능 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="06e7b-166">SQL Server Features and ADO.NET</span></span>](sql-server-features-and-adonet.md)
- [<span data-ttu-id="06e7b-167">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="06e7b-167">ADO.NET Overview</span></span>](../ado-net-overview.md)
