---
title: 쿼리 알림 사용
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: a5333e19-8e55-4aa9-82dc-ca8745e516ed
ms.openlocfilehash: 4e9b3a2e1f176a9d01e983bc469cc4032fa5d730
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91156175"
---
# <a name="enabling-query-notifications"></a><span data-ttu-id="87048-102">쿼리 알림 사용</span><span class="sxs-lookup"><span data-stu-id="87048-102">Enabling Query Notifications</span></span>

<span data-ttu-id="87048-103">쿼리 알림을 사용하는 애플리케이션에는 일반적인 요구 사항 집합이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87048-103">Applications that consume query notifications have a common set of requirements.</span></span> <span data-ttu-id="87048-104">SQL 쿼리 알림을 지원하도록 데이터 소스를 올바르게 구성해야 하며, 사용자는 올바른 클라이언트측 및 서버측 권한을 가지고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-104">Your data source must be correctly configured to support SQL query notifications, and the user must have the correct client-side and server-side permissions.</span></span>  
  
 <span data-ttu-id="87048-105">쿼리 알림을 사용하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-105">To use query notifications you must:</span></span>  
  
- <span data-ttu-id="87048-106">데이터베이스에 대해 쿼리 알림을 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-106">Enable query notifications for your database.</span></span>  
  
- <span data-ttu-id="87048-107">데이터베이스에 연결하는 데 사용되는 사용자 ID가 필요한 권한을 갖는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-107">Ensure that the user ID used to connect to the database has the necessary permissions.</span></span>  
  
- <span data-ttu-id="87048-108"><xref:System.Data.SqlClient.SqlCommand> 개체를 사용하여 <xref:System.Data.SqlClient.SqlDependency> 또는 <xref:System.Data.Sql.SqlNotificationRequest> 같은 관련된 알림 개체로 올바른 SELECT 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-108">Use a <xref:System.Data.SqlClient.SqlCommand> object to execute a valid SELECT statement with an associated notification object—either <xref:System.Data.SqlClient.SqlDependency> or <xref:System.Data.Sql.SqlNotificationRequest>.</span></span>  
  
- <span data-ttu-id="87048-109">모니터링되는 데이터가 변경될 경우 알림을 처리하는 코드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-109">Provide code to process the notification if the data being monitored changes.</span></span>  
  
## <a name="query-notifications-requirements"></a><span data-ttu-id="87048-110">쿼리 알림 요구 사항</span><span class="sxs-lookup"><span data-stu-id="87048-110">Query Notifications Requirements</span></span>  

 <span data-ttu-id="87048-111">쿼리 알림은 특정 요구 사항 목록을 충족하는 SELECT 문에 대해서만 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="87048-111">Query notifications are supported only for SELECT statements that meet a list of specific requirements.</span></span> <span data-ttu-id="87048-112">다음 표에서는 SQL Server 온라인 설명서의 Service Broker 및 쿼리 알림 설명서에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-112">The following table provides links to the Service Broker and Query Notifications documentation in SQL Server Books Online.</span></span>  
  
 <span data-ttu-id="87048-113">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="87048-113">**SQL Server documentation**</span></span>  
  
- <span data-ttu-id="87048-114">[알림에 대한 쿼리 만들기](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87048-114">[Creating a Query for Notification](/previous-versions/sql/sql-server-2008-r2/ms181122(v=sql.105))</span></span>  
  
- <span data-ttu-id="87048-115">[Service Broker에 대한 보안 고려 사항](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="87048-115">[Security Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166059(v=sql.90))</span></span>  
  
- <span data-ttu-id="87048-116">[보안 및 보호(Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87048-116">[Security and Protection (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522911(v=sql.105))</span></span>  
  
- <span data-ttu-id="87048-117">[Notifications Services에 대한 보안 고려 사항](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="87048-117">[Security Considerations for Notifications Services](/previous-versions/sql/sql-server-2005/ms172604(v=sql.90))</span></span>  
  
- <span data-ttu-id="87048-118">[쿼리 알림 사용 권한](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87048-118">[Query Notification Permissions](/previous-versions/sql/sql-server-2008-r2/ms188311(v=sql.105))</span></span>  
  
- <span data-ttu-id="87048-119">[Service Broker에 대한 국가별 고려 사항](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span><span class="sxs-lookup"><span data-stu-id="87048-119">[International Considerations for Service Broker](/previous-versions/sql/sql-server-2005/ms166028(v=sql.90))</span></span>  
  
- <span data-ttu-id="87048-120">[솔루션 디자인 고려 사항(Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87048-120">[Solution Design Considerations (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522899(v=sql.105))</span></span>  
  
- <span data-ttu-id="87048-121">[Service Broker 개발자 정보 센터](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87048-121">[Service Broker Developer InfoCenter](/previous-versions/sql/sql-server-2008-r2/ms166100(v=sql.105))</span></span>  
  
- <span data-ttu-id="87048-122">[개발자 가이드(Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span><span class="sxs-lookup"><span data-stu-id="87048-122">[Developer's Guide (Service Broker)](/previous-versions/sql/sql-server-2008-r2/bb522908(v=sql.105))</span></span>  
  
## <a name="enabling-query-notifications-to-run-sample-code"></a><span data-ttu-id="87048-123">쿼리 알림 활성화 샘플 코드</span><span class="sxs-lookup"><span data-stu-id="87048-123">Enabling Query Notifications to Run Sample Code</span></span>  

 <span data-ttu-id="87048-124">SQL Server Management Studio를 사용하여 **AdventureWorks** 데이터베이스에 대해 Service Broker를 활성화하려면 다음 Transact-SQL 문을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-124">To enable Service Broker on the **AdventureWorks** database by using SQL Server Management Studio, execute the following Transact-SQL statement:</span></span>  
  
 `ALTER DATABASE AdventureWorks SET ENABLE_BROKER;`  
  
 <span data-ttu-id="87048-125">쿼리 알림 샘플이 올바르게 실행되려면 데이터베이스 서버에서 다음 Transact-SQL 문을 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-125">For the query notification samples to run correctly, the following Transact-SQL statements must be executed on the database server.</span></span>  
  
```sql
CREATE QUEUE ContactChangeMessages;  
  
CREATE SERVICE ContactChangeNotifications  
  ON QUEUE ContactChangeMessages  
([http://schemas.microsoft.com/SQL/Notifications/PostQueryNotification]);  
```  
  
## <a name="query-notifications-permissions"></a><span data-ttu-id="87048-126">쿼리 알림 권한</span><span class="sxs-lookup"><span data-stu-id="87048-126">Query Notifications Permissions</span></span>  

 <span data-ttu-id="87048-127">알림을 요청하는 명령을 실행하는 사용자에게는 서버에 대한 SUBSCRIBE QUERY NOTIFICATIONS 데이터베이스 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-127">Users who execute commands requesting notification must have SUBSCRIBE QUERY NOTIFICATIONS database permission on the server.</span></span>  
  
 <span data-ttu-id="87048-128">부분 신뢰 상황에서 실행되는 클라이언트 쪽 코드에는 <xref:System.Data.SqlClient.SqlClientPermission>이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-128">Client-side code that runs in a partial trust situation requires the <xref:System.Data.SqlClient.SqlClientPermission>.</span></span>  
  
 <span data-ttu-id="87048-129">다음 코드는 <xref:System.Data.SqlClient.SqlClientPermission> 개체를 만들고 <xref:System.Security.Permissions.PermissionState>를 <xref:System.Security.Permissions.PermissionState.Unrestricted>로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-129">The following code creates a <xref:System.Data.SqlClient.SqlClientPermission> object, setting the <xref:System.Security.Permissions.PermissionState> to <xref:System.Security.Permissions.PermissionState.Unrestricted>.</span></span> <span data-ttu-id="87048-130">호출 스택의 모든 상위 호출자에게 권한이 부여되지 않은 경우 <xref:System.Security.CodeAccessPermission.Demand%2A>는 런타임에 <xref:System.Security.SecurityException>을 강제 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-130">The <xref:System.Security.CodeAccessPermission.Demand%2A> will force a <xref:System.Security.SecurityException> at run time if all callers higher in the call stack have not been granted the permission.</span></span>  
  
 [!code-csharp[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/CS/source.cs#1)]
 [!code-vb[DataWorks SqlNotification.Perms#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks SqlNotification.Perms/VB/source.vb#1)]  
  
## <a name="choosing-a-notification-object"></a><span data-ttu-id="87048-131">알림 개체 선택</span><span class="sxs-lookup"><span data-stu-id="87048-131">Choosing a Notification Object</span></span>  

 <span data-ttu-id="87048-132">쿼리 알림 API에서는 알림을 처리하기 위한 두 개의 개체인 <xref:System.Data.SqlClient.SqlDependency> 및 <xref:System.Data.Sql.SqlNotificationRequest>입니다.</span><span class="sxs-lookup"><span data-stu-id="87048-132">The query notifications API provides two objects to process notifications: <xref:System.Data.SqlClient.SqlDependency> and <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="87048-133">일반적으로 대부분의 비 ASP.NET 애플리케이션에서는 <xref:System.Data.SqlClient.SqlDependency> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-133">In general, most non-ASP.NET applications should use the <xref:System.Data.SqlClient.SqlDependency> object.</span></span> <span data-ttu-id="87048-134">ASP.NET 애플리케이션에서는 상위 수준의 <xref:System.Web.Caching.SqlCacheDependency>를 사용하여 <xref:System.Data.SqlClient.SqlDependency>를 래핑하고 알림 및 캐시 개체를 관리하기 위한 프레임워크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-134">ASP.NET applications should use the higher-level <xref:System.Web.Caching.SqlCacheDependency>, which wraps <xref:System.Data.SqlClient.SqlDependency> and provides a framework for administering the notification and cache objects.</span></span>  
  
### <a name="using-sqldependency"></a><span data-ttu-id="87048-135">SqlDependency 사용</span><span class="sxs-lookup"><span data-stu-id="87048-135">Using SqlDependency</span></span>  

 <span data-ttu-id="87048-136"><xref:System.Data.SqlClient.SqlDependency>를 사용하려면 사용 중인 SQL Server 데이터베이스에 대해 Service Broker를 활성화해야 하며 사용자는 알림을 수신할 수 있는 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-136">To use <xref:System.Data.SqlClient.SqlDependency>, Service Broker must be enabled for the SQL Server database being used, and users must have permissions to receive notifications.</span></span> <span data-ttu-id="87048-137">알림 큐와 같은 Service Broker 개체는 미리 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="87048-137">Service Broker objects, such as the notification queue, are predefined.</span></span>  
  
 <span data-ttu-id="87048-138">또한 <xref:System.Data.SqlClient.SqlDependency>는 작업자 스레드를 자동으로 실행하여 큐에 게시될 때 알림을 처리합니다. 또한 Service Broker 메시지를 구문 분석하여 정보를 이벤트 인수 데이터로 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-138">In addition, <xref:System.Data.SqlClient.SqlDependency> automatically launches a worker thread to process notifications as they are posted to the queue; it also parses the Service Broker message, exposing the information as event argument data.</span></span> <span data-ttu-id="87048-139"><xref:System.Data.SqlClient.SqlDependency>는 데이터베이스에 대한 종속성을 설정하기 위해 `Start` 메서드를 호출하여 초기화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-139"><xref:System.Data.SqlClient.SqlDependency> must be initialized by calling the `Start` method to establish a dependency to the database.</span></span> <span data-ttu-id="87048-140">이 메서드는 필요한 각 데이터베이스 연결에 대해 애플리케이션을 초기화할 때 한 번만 호출해야 하는 정적 메서드입니다.</span><span class="sxs-lookup"><span data-stu-id="87048-140">This is a static method that needs to be called only once during application initialization for each database connection required.</span></span> <span data-ttu-id="87048-141">만들어진 각 종속성 연결에 대해 애플리케이션이 종료될 때 `Stop` 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-141">The `Stop` method should be called at application termination for each dependency connection that was made.</span></span>  
  
### <a name="using-sqlnotificationrequest"></a><span data-ttu-id="87048-142">SqlNotificationRequest 사용</span><span class="sxs-lookup"><span data-stu-id="87048-142">Using SqlNotificationRequest</span></span>  

 <span data-ttu-id="87048-143">반면, <xref:System.Data.Sql.SqlNotificationRequest>에서는 전체 수신 인프라를 직접 구현해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-143">In contrast, <xref:System.Data.Sql.SqlNotificationRequest> requires you to implement the entire listening infrastructure yourself.</span></span> <span data-ttu-id="87048-144">또한 큐, 서비스, 큐에서 지원하는 메시지 유형과 같은 모든 지원 Service Broker 개체를 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-144">In addition, all the supporting Service Broker objects such as the queue, service, and message types supported by the queue must be defined.</span></span> <span data-ttu-id="87048-145">이 수동 접근 방식은 애플리케이션에 특별한 알림 메시지나 알림 동작이 필요하거나 애플리케이션이 대규모 Service Broker 애플리케이션의 일부인 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="87048-145">This manual approach is useful if your application requires special notification messages or notification behaviors, or if your application is part of a larger Service Broker application.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87048-146">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87048-146">See also</span></span>

- [<span data-ttu-id="87048-147">SQL Server의 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="87048-147">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="87048-148">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="87048-148">ADO.NET Overview</span></span>](../ado-net-overview.md)
