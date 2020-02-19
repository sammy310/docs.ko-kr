---
title: SQL Server에서 쿼리 알림
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 11d9a1a800bea4224853a57b128ca89c9f2cf781
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452372"
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="15118-102">SQL Server에서 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="15118-102">Query Notifications in SQL Server</span></span>
<span data-ttu-id="15118-103">Service Broker 인프라를 기반으로 구축된 쿼리 알림을 통해 애플리케이션은 데이터 변경 시 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15118-103">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="15118-104">이 기능은 데이터베이스의 정보 캐시를 제공하며 원본 데이터 변경 시 알림을 받아야 하는 애플리케이션(예: 웹 애플리케이션)에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-104">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="15118-105">ADO.NET을 사용하여 쿼리 알림을 구현하는 방법은 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15118-105">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1. <span data-ttu-id="15118-106">하위 수준 구현은 서버측 기능을 노출하여 알림 요청으로 명령을 실행할 수 있도록 하는 `SqlNotificationRequest` 클래스에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-106">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2. <span data-ttu-id="15118-107">상위 수준 구현은 원본 애플리케이션과 SQL Server 간에 알림 기능의 상위 수준 추상화를 제공하여 종속성을 통해 서버의 변경 내용을 감지할 수 있게 해주는 `SqlDependency` 클래스에서 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-107">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="15118-108">이는 일반적으로 관리 클라이언트 애플리케이션에서 .NET Framework Data Provider for SQL Server를 사용하여 SQL Server 알림 기능을 가장 간단하고 효과적으로 활용하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="15118-108">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3. <span data-ttu-id="15118-109">또한 ASP.NET 2.0 이상을 사용하여 작성된 웹 애플리케이션에서는 `SqlCacheDependency` 도우미 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15118-109">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="15118-110">쿼리 알림은 원본으로 사용하는 데이터의 변경에 대한 응답으로 표시나 캐시를 새로 고쳐야 하는 애플리케이션에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-110">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="15118-111">.NET Framework 애플리케이션에서 Microsoft SQL Server를 사용하여 SQL Server에 명령을 보낼 수 있을 뿐 아니라 동일한 명령을 실행했을 때 처음 검색한 것과 다른 결과 집합이 나오면 알림을 생성하도록 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15118-111">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="15118-112">서버에서 생성된 알림은 나중에 처리하기 위해 큐를 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="15118-112">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="15118-113">SELECT 및 EXECUTE 문에 대해 알림을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="15118-113">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="15118-114">EXECUTE 문을 사용할 경우 SQL Server에서는 EXECUTE 문 자체가 아니라 실행되는 명령에 대해 알림을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-114">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="15118-115">명령은 SELECT 문의 요구 사항과 제한 사항을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-115">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="15118-116">알림을 등록하는 명령에 하나 이상의 문이 포함된 경우 데이터베이스 엔진은 일괄 처리에 있는 각 문에 대한 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="15118-116">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="15118-117">을 개발 하는 애플리케이션 데이터가 변경 되 면 신뢰할 수 있는 하위 보조 알림이 필요한 경우 섹션을 검토 **효율적인 쿼리 알림 전략을 계획** 고 **쿼리에 대 한 대안 알림을** 에 [알림에 대 한 계획](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) 문서.</span><span class="sxs-lookup"><span data-stu-id="15118-117">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) article.</span></span> <span data-ttu-id="15118-118">쿼리 알림 및 SQL Server Service Broker에 대 한 자세한 내용은 SQL Server 설명서의 다음 문서에 대 한 링크를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="15118-118">For more information about Query Notifications and SQL Server Service Broker, see the following links to articles in the SQL Server documentation.</span></span>  
  
 <span data-ttu-id="15118-119">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="15118-119">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="15118-120">[쿼리 알림 사용](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="15118-120">[Using Query Notifications](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span></span>  
  
- <span data-ttu-id="15118-121">[알림에 대한 쿼리 만들기](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="15118-121">[Creating a Query for Notification](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="15118-122">[개발(Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="15118-122">[Development (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span></span>  
  
- <span data-ttu-id="15118-123">[Service Broker 개발자 정보 센터](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="15118-123">[Service Broker Developer InfoCenter](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="15118-124">[개발자 가이드(Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="15118-124">[Developer's Guide (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="15118-125">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="15118-125">In This Section</span></span>  
 [<span data-ttu-id="15118-126">쿼리 알림 사용</span><span class="sxs-lookup"><span data-stu-id="15118-126">Enabling Query Notifications</span></span>](enabling-query-notifications.md)  
 <span data-ttu-id="15118-127">쿼리 알림 활성화 및 사용에 필요한 요구 사항 등 쿼리 알림 사용 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-127">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="15118-128">ASP.NET 애플리케이션의 SqlDependency</span><span class="sxs-lookup"><span data-stu-id="15118-128">SqlDependency in an ASP.NET Application</span></span>](sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="15118-129">ASP.NET 애플리케이션에서 쿼리 알림을 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-129">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="15118-130">SqlDependency로 변경 내용 감지</span><span class="sxs-lookup"><span data-stu-id="15118-130">Detecting Changes with SqlDependency</span></span>](detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="15118-131">쿼리 결과가 원래 수신된 결과와 다를 때 감지하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-131">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="15118-132">SqlNotificationRequest를 사용하여 SqlCommand 실행</span><span class="sxs-lookup"><span data-stu-id="15118-132">SqlCommand Execution with a SqlNotificationRequest</span></span>](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="15118-133">쿼리 알림을 사용하기 위해 <xref:System.Data.SqlClient.SqlCommand> 개체를 구성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-133">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="15118-134">참조</span><span class="sxs-lookup"><span data-stu-id="15118-134">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="15118-135"><xref:System.Data.Sql.SqlNotificationRequest> 클래스와 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-135">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="15118-136"><xref:System.Data.SqlClient.SqlDependency> 클래스와 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-136">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="15118-137"><xref:System.Web.Caching.SqlCacheDependency> 클래스와 해당 멤버 전체에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="15118-137">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15118-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15118-138">See also</span></span>

- [<span data-ttu-id="15118-139">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="15118-139">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="15118-140">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="15118-140">ADO.NET Overview</span></span>](../ado-net-overview.md)
