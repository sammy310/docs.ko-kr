---
description: '자세히 알아보기: SqlNotificationRequest를 사용 하 여 SqlCommand 실행'
title: SqlNotificationRequest를 사용하여 SqlCommand 실행
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1776f48f-9bea-41f6-83a4-c990c7a2c991
ms.openlocfilehash: d3e82022794aa67d4bd20223cac852097f2be9dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767052"
---
# <a name="sqlcommand-execution-with-a-sqlnotificationrequest"></a><span data-ttu-id="126bb-103">SqlNotificationRequest를 사용하여 SqlCommand 실행</span><span class="sxs-lookup"><span data-stu-id="126bb-103">SqlCommand Execution with a SqlNotificationRequest</span></span>

<span data-ttu-id="126bb-104">서버에서 데이터를 가져온 후 데이터가 변경될 때 알림을 생성하도록 <xref:System.Data.SqlClient.SqlCommand>를 구성할 수 있으며 쿼리가 다시 실행되면 결과 집합이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-104">A <xref:System.Data.SqlClient.SqlCommand> can be configured to generate a notification when data changes after it has been fetched from the server and the result set would be different if the query were executed again.</span></span> <span data-ttu-id="126bb-105">이 기능은 서버에서 사용자 지정 알림 큐를 사용하려는 시나리오 또는 라이브 개체를 유지하지 않으려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-105">This is useful for scenarios where you want to use custom notification queues on the server or when you do not want to maintain live objects.</span></span>

## <a name="creating-the-notification-request"></a><span data-ttu-id="126bb-106">Notification 요청 만들기</span><span class="sxs-lookup"><span data-stu-id="126bb-106">Creating the Notification Request</span></span>

<span data-ttu-id="126bb-107"><xref:System.Data.Sql.SqlNotificationRequest> 개체를 사용하여 `SqlCommand` 개체에 바인딩하고 알림 요청을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-107">You can use a <xref:System.Data.Sql.SqlNotificationRequest> object to create the notification request by binding it to a `SqlCommand` object.</span></span> <span data-ttu-id="126bb-108">요청이 만들어지면 `SqlNotificationRequest` 개체가 더 이상 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-108">Once the request is created, you no longer need the `SqlNotificationRequest` object.</span></span> <span data-ttu-id="126bb-109">모든 알림에 대해 큐를 쿼리하고 적절하게 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-109">You can query the queue for any notifications and respond appropriately.</span></span> <span data-ttu-id="126bb-110">애플리케이션이 종료된 후 다시 시작되는 경우에도 알림이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-110">Notifications can occur even if the application is shut down and subsequently restarted.</span></span>

<span data-ttu-id="126bb-111">연결된 알림에 대한 명령이 실행될 때 원래 결과 집합에 대한 변경 사항이 있으면 알림 요청에 구성되어 있는 SQL Server 큐로 메시지를 보내는 작업이 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-111">When the command with the associated notification is executed, any changes to the original result set trigger sending a message to the SQL Server queue that was configured in the notification request.</span></span>

<span data-ttu-id="126bb-112">SQL Server 큐를 폴링하고 메시지를 해석하는 방법은 애플리케이션에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-112">How you poll the SQL Server queue and interpret the message is specific to your application.</span></span> <span data-ttu-id="126bb-113">애플리케이션에서는 큐를 폴링하고 메시지의 내용에 따라 반응하는 작업을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-113">The application is responsible for polling the queue and reacting based on the contents of the message.</span></span>

> [!NOTE]
> <span data-ttu-id="126bb-114"><xref:System.Data.SqlClient.SqlDependency>에서 SQL Server 알림 요청을 사용하는 경우 기본 서비스 이름을 사용하는 대신 고유한 큐 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-114">When using SQL Server notification requests with <xref:System.Data.SqlClient.SqlDependency>, create your own queue name instead of using the default service name.</span></span>

<span data-ttu-id="126bb-115"><xref:System.Data.Sql.SqlNotificationRequest>에 대한 새로운 클라이언트 측 보안 요소는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-115">There are no new client-side security elements for <xref:System.Data.Sql.SqlNotificationRequest>.</span></span> <span data-ttu-id="126bb-116">이는 주로 서버 기능이며 서버는 사용자가 알림을 요청하는 데 필요한 특수 권한을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-116">This is primarily a server feature, and the server has created special privileges that users must have to request a notification.</span></span>

### <a name="example"></a><span data-ttu-id="126bb-117">예제</span><span class="sxs-lookup"><span data-stu-id="126bb-117">Example</span></span>

<span data-ttu-id="126bb-118">다음 코드 조각에서는 <xref:System.Data.Sql.SqlNotificationRequest>를 만들고 <xref:System.Data.SqlClient.SqlCommand>에 연결하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="126bb-118">The following code fragment demonstrates how to create a <xref:System.Data.Sql.SqlNotificationRequest> and associate it with a <xref:System.Data.SqlClient.SqlCommand>.</span></span>

```vb
' Assume connection is an open SqlConnection.
' Create a new SqlCommand object.
Dim command As New SqlCommand( _
  "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection)

' Create a SqlNotificationRequest object.
Dim notifcationRequest As New SqlNotificationRequest()
notificationRequest.id = "NotificationID"
notificationRequest.Service = "mySSBQueue"

' Associate the notification request with the command.
command.Notification = notificationRequest
' Execute the command.
command.ExecuteReader()
' Process the DataReader.
' You can use Transact-SQL syntax to periodically poll the
' SQL Server queue to see if you have a new message.
```

```csharp
// Assume connection is an open SqlConnection.
// Create a new SqlCommand object.
SqlCommand command=new SqlCommand(
 "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", connection);

// Create a SqlNotificationRequest object.
SqlNotificationRequest notificationRequest=new SqlNotificationRequest();
notificationRequest.id="NotificationID";
notificationRequest.Service="mySSBQueue";

// Associate the notification request with the command.
command.Notification=notificationRequest;
// Execute the command.
command.ExecuteReader();
// Process the DataReader.
// You can use Transact-SQL syntax to periodically poll the
// SQL Server queue to see if you have a new message.
```

## <a name="see-also"></a><span data-ttu-id="126bb-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="126bb-119">See also</span></span>

- [<span data-ttu-id="126bb-120">SQL Server의 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="126bb-120">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="126bb-121">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="126bb-121">ADO.NET Overview</span></span>](../ado-net-overview.md)
