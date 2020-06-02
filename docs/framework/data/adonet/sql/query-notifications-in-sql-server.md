---
title: SQL Server에서 쿼리 알림
description: 예를 들어 응용 프로그램 표시를 새로 고치는 SQL Server 데이터베이스에서 데이터가 변경 된 경우 쿼리 알림을 사용 하 여 응용 프로그램에 알리는 방법에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 0f0ba1a1-3180-4af8-87f7-c795dc8f8f55
ms.openlocfilehash: 1351c83b6cc5837115321d53e8779c0f364c3099
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286225"
---
# <a name="query-notifications-in-sql-server"></a><span data-ttu-id="685d5-103">SQL Server에서 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="685d5-103">Query Notifications in SQL Server</span></span>
<span data-ttu-id="685d5-104">Service Broker 인프라를 기반으로 구축된 쿼리 알림을 통해 애플리케이션은 데이터 변경 시 알림을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-104">Built upon the Service Broker infrastructure, query notifications allow applications to be notified when data has changed.</span></span> <span data-ttu-id="685d5-105">이 기능은 데이터베이스의 정보 캐시를 제공하며 원본 데이터 변경 시 알림을 받아야 하는 애플리케이션(예: 웹 애플리케이션)에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-105">This feature is particularly useful for applications that provide a cache of information from a database, such as a Web application, and need to be notified when the source data is changed.</span></span>  
  
 <span data-ttu-id="685d5-106">ADO.NET를 사용하여 쿼리 알림을 구현하는 방법에는 세 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-106">There are three ways you can implement query notifications using ADO.NET:</span></span>  
  
1. <span data-ttu-id="685d5-107">하위 수준 구현은 서버 쪽 기능을 노출하는 `SqlNotificationRequest` 클래스에서 제공합니다. 이를 통해 알림 요청을 사용하여 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-107">The low-level implementation is provided by the `SqlNotificationRequest` class that exposes server-side functionality, enabling you to execute a command with a notification request.</span></span>  
  
2. <span data-ttu-id="685d5-108">상위 수준 구현은 원본 애플리케이션과 SQL Server 간의 알림 기능에 대한 상위 수준 추상화를 제공하는 클래스인 `SqlDependency` 클래스에서 제공합니다. 이를 통해 종속성을 사용하여 서버의 변경 내용을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-108">The high-level implementation is provided by the `SqlDependency` class, which is a class that provides a high-level abstraction of notification functionality between the source application and SQL Server, enabling you to use a dependency to detect changes in the server.</span></span> <span data-ttu-id="685d5-109">이는 일반적으로 관리 클라이언트 애플리케이션에서 .NET Framework Data Provider for SQL Server를 사용하여 SQL Server 알림 기능을 가장 간단하고 효과적으로 활용하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-109">In most cases, this is the simplest and most effective way to leverage SQL Server notifications capability by managed client applications using the .NET Framework Data Provider for SQL Server.</span></span>  
  
3. <span data-ttu-id="685d5-110">또한 ASP.NET 2.0 이상을 사용하여 작성된 웹 애플리케이션에서는 `SqlCacheDependency` 도우미 클래스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-110">In addition, Web applications built using ASP.NET 2.0 or later can use the `SqlCacheDependency` helper classes.</span></span>  
  
 <span data-ttu-id="685d5-111">쿼리 알림은 기본 데이터의 변경 내용에 대한 응답으로 표시 또는 캐시를 새로 고쳐야 하는 애플리케이션에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-111">Query notifications are used for applications that need to refresh displays or caches in response to changes in underlying data.</span></span> <span data-ttu-id="685d5-112">.NET Framework 애플리케이션에서 Microsoft SQL Server를 사용하여 SQL Server에 명령을 보낼 수 있을 뿐 아니라 동일한 명령을 실행했을 때 처음 검색한 것과 다른 결과 집합이 나오면 알림을 생성하도록 요청할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-112">Microsoft SQL Server allows .NET Framework applications to send a command to SQL Server and request notification if executing the same command would produce result sets different from those initially retrieved.</span></span> <span data-ttu-id="685d5-113">서버에서 생성된 알림은 나중에 처리하기 위해 큐를 통해 전송됩니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-113">Notifications generated at the server are sent through queues to be processed later.</span></span>  
  
 <span data-ttu-id="685d5-114">SELECT 및 EXECUTE 문에 대한 알림을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-114">You can set up notifications for SELECT and EXECUTE statements.</span></span> <span data-ttu-id="685d5-115">EXECUTE 문을 사용하는 경우 SQL Server는 EXECUTE 문 자체가 아니라 실행된 명령에 대한 알림을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-115">When using an EXECUTE statement, SQL Server registers a notification for the command executed rather than the EXECUTE statement itself.</span></span> <span data-ttu-id="685d5-116">명령은 SELECT 문의 요구 사항과 제한 사항을 따라야 합니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-116">The command must meet the requirements and limitations for a SELECT statement.</span></span> <span data-ttu-id="685d5-117">알림을 등록하는 명령에 하나 이상의 문이 포함된 경우 데이터베이스 엔진은 일괄 처리에 있는 각 문에 대한 알림을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-117">When a command that registers a notification contains more than one statement, the Database Engine creates a notification for each statement in the batch.</span></span>  
  
 <span data-ttu-id="685d5-118">을 개발 하는 애플리케이션 데이터가 변경 되 면 신뢰할 수 있는 하위 보조 알림이 필요한 경우 섹션을 검토 **효율적인 쿼리 알림 전략을 계획** 고 **쿼리에 대 한 대안 알림을** 에 [알림에 대 한 계획](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) 문서.</span><span class="sxs-lookup"><span data-stu-id="685d5-118">If you are developing an application where you need reliable sub-second notifications when data changes, review the sections **Planning an Efficient Query Notifications Strategy** and **Alternatives to Query Notifications** in the [Planning for Notifications](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms187528(v=sql.105)) article.</span></span> <span data-ttu-id="685d5-119">쿼리 알림 및 SQL Server Service Broker에 대 한 자세한 내용은 SQL Server 설명서의 다음 문서에 대 한 링크를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="685d5-119">For more information about Query Notifications and SQL Server Service Broker, see the following links to articles in the SQL Server documentation.</span></span>  
  
 <span data-ttu-id="685d5-120">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="685d5-120">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="685d5-121">[쿼리 알림 사용](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="685d5-121">[Using Query Notifications](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms175110(v=sql.105))</span></span>  
  
- <span data-ttu-id="685d5-122">[알림에 대한 쿼리 만들기](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="685d5-122">[Creating a Query for Notification](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="685d5-123">[개발(Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="685d5-123">[Development (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522889(v=sql.105))</span></span>  
  
- <span data-ttu-id="685d5-124">[Service Broker 개발자 정보 센터](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="685d5-124">[Service Broker Developer InfoCenter](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="685d5-125">[개발자 가이드(Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="685d5-125">[Developer's Guide (Service Broker)](https://docs.microsoft.com/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="685d5-126">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="685d5-126">In This Section</span></span>  
 [<span data-ttu-id="685d5-127">쿼리 알림 사용</span><span class="sxs-lookup"><span data-stu-id="685d5-127">Enabling Query Notifications</span></span>](enabling-query-notifications.md)  
 <span data-ttu-id="685d5-128">쿼리 알림을 설정하고 사용하기 위한 요구 사항을 포함하여 쿼리 알림을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-128">Discusses how to use query notifications, including the requirements for enabling and using them.</span></span>  
  
 [<span data-ttu-id="685d5-129">ASP.NET 애플리케이션에서 SqlDependency</span><span class="sxs-lookup"><span data-stu-id="685d5-129">SqlDependency in an ASP.NET Application</span></span>](sqldependency-in-an-aspnet-app.md)  
 <span data-ttu-id="685d5-130">ASP.NET 애플리케이션에서 쿼리 알림을 사용하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-130">Demonstrates how to use query notifications from an ASP.NET application.</span></span>  
  
 [<span data-ttu-id="685d5-131">SqlDependency로 변경 내용 감지</span><span class="sxs-lookup"><span data-stu-id="685d5-131">Detecting Changes with SqlDependency</span></span>](detecting-changes-with-sqldependency.md)  
 <span data-ttu-id="685d5-132">쿼리 결과가 원래 수신된 결과와 다를 때를 감지하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-132">Demonstrates how to detect when query results will be different from those originally received.</span></span>  
  
 [<span data-ttu-id="685d5-133">SqlNotificationRequest를 사용하여 SqlCommand 실행</span><span class="sxs-lookup"><span data-stu-id="685d5-133">SqlCommand Execution with a SqlNotificationRequest</span></span>](sqlcommand-execution-with-a-sqlnotificationrequest.md)  
 <span data-ttu-id="685d5-134">쿼리 알림과 함께 작동하도록 <xref:System.Data.SqlClient.SqlCommand> 개체를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-134">Demonstrates configuring a <xref:System.Data.SqlClient.SqlCommand> object to work with a query notification.</span></span>  
  
## <a name="reference"></a><span data-ttu-id="685d5-135">참조</span><span class="sxs-lookup"><span data-stu-id="685d5-135">Reference</span></span>  
 <xref:System.Data.Sql.SqlNotificationRequest>  
 <span data-ttu-id="685d5-136"><xref:System.Data.Sql.SqlNotificationRequest> 클래스와 모든 해당 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-136">Describes the <xref:System.Data.Sql.SqlNotificationRequest> class and all of its members.</span></span>  
  
 <xref:System.Data.SqlClient.SqlDependency>  
 <span data-ttu-id="685d5-137"><xref:System.Data.SqlClient.SqlDependency> 클래스와 모든 해당 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-137">Describes the <xref:System.Data.SqlClient.SqlDependency> class and all of its members.</span></span>  
  
 <xref:System.Web.Caching.SqlCacheDependency>  
 <span data-ttu-id="685d5-138"><xref:System.Web.Caching.SqlCacheDependency> 클래스와 모든 해당 멤버에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="685d5-138">Describes the <xref:System.Web.Caching.SqlCacheDependency> class and all of its members.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="685d5-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="685d5-139">See also</span></span>

- [<span data-ttu-id="685d5-140">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="685d5-140">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="685d5-141">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="685d5-141">ADO.NET Overview</span></span>](../ado-net-overview.md)
