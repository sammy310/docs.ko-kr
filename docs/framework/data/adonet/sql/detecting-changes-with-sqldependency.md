---
title: SqlDependency로 변경 내용 감지
description: SqlDependency 개체를 SqlCommand와 연결 하 여 쿼리 결과가 ADO.NET에서 원래 검색 된 결과와 다를 때를 검색 합니다.
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: e6a58316-f005-4477-92e1-45cc2eb8c5b4
ms.openlocfilehash: b196d42477e1778c45df64b1390502645fdd649d
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84286470"
---
# <a name="detecting-changes-with-sqldependency"></a><span data-ttu-id="25d64-103">SqlDependency로 변경 내용 감지</span><span class="sxs-lookup"><span data-stu-id="25d64-103">Detecting Changes with SqlDependency</span></span>

<span data-ttu-id="25d64-104">쿼리 결과가 원래 검색된 결과와 다를 때를 감지하기 위해 <xref:System.Data.SqlClient.SqlDependency> 개체를 <xref:System.Data.SqlClient.SqlCommand>에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-104">A <xref:System.Data.SqlClient.SqlDependency> object can be associated with a <xref:System.Data.SqlClient.SqlCommand> in order to detect when query results differ from those originally retrieved.</span></span> <span data-ttu-id="25d64-105">연결된 명령의 결과가 변경될 때 발생하는 `OnChange` 이벤트에 대리자를 할당할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-105">You can also assign a delegate to the `OnChange` event, which will fire when the results change for an associated command.</span></span> <span data-ttu-id="25d64-106">명령을 실행하기 전에 <xref:System.Data.SqlClient.SqlDependency>를 명령과 연결해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-106">You must associate the <xref:System.Data.SqlClient.SqlDependency> with the command before you execute the command.</span></span> <span data-ttu-id="25d64-107"><xref:System.Data.SqlClient.SqlDependency>의 `HasChanges` 속성을 사용하여 데이터를 처음 검색한 이후 쿼리 결과가 변경되었는지 여부를 확인할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-107">The `HasChanges` property of the <xref:System.Data.SqlClient.SqlDependency> can also be used to determine if the query results have changed since the data was first retrieved.</span></span>

## <a name="security-considerations"></a><span data-ttu-id="25d64-108">보안 고려사항</span><span class="sxs-lookup"><span data-stu-id="25d64-108">Security Considerations</span></span>

<span data-ttu-id="25d64-109">종속성 인프라는 지정된 명령에 대한 기본 데이터가 변경되었다는 알림을 받기 위해 <xref:System.Data.SqlClient.SqlDependency.Start%2A>가 호출될 때 열리는 <xref:System.Data.SqlClient.SqlConnection>에 의존합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-109">The dependency infrastructure relies on a <xref:System.Data.SqlClient.SqlConnection> that is opened when <xref:System.Data.SqlClient.SqlDependency.Start%2A> is called in order to receive notifications that the underlying data has changed for a given command.</span></span> <span data-ttu-id="25d64-110">클라이언트에서 `SqlDependency.Start`에 대한 호출을 시작하는 기능은 <xref:System.Data.SqlClient.SqlClientPermission> 및 코드 액세스 보안 특성을 사용하여 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-110">The ability for a client to initiate the call to `SqlDependency.Start` is controlled through the use of <xref:System.Data.SqlClient.SqlClientPermission> and code access security attributes.</span></span> <span data-ttu-id="25d64-111">자세한 내용은 [쿼리 알림 사용](enabling-query-notifications.md) 및 [코드 액세스 보안 및 ADO.NET](../code-access-security.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="25d64-111">For more information, see [Enabling Query Notifications](enabling-query-notifications.md) and [Code Access Security and ADO.NET](../code-access-security.md).</span></span>

### <a name="example"></a><span data-ttu-id="25d64-112">예제</span><span class="sxs-lookup"><span data-stu-id="25d64-112">Example</span></span>

<span data-ttu-id="25d64-113">다음 단계에서는 종속성을 선언하고, 명령을 실행하고, 결과 집합이 변경될 때 알림을 받는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-113">The following steps illustrate how to declare a dependency, execute a command, and receive a notification when the result set changes:</span></span>

1. <span data-ttu-id="25d64-114">서버에 대한 `SqlDependency` 연결을 개시합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-114">Initiate a `SqlDependency` connection to the server.</span></span>

2. <span data-ttu-id="25d64-115"><xref:System.Data.SqlClient.SqlConnection> 및 <xref:System.Data.SqlClient.SqlCommand> 개체를 만들어 서버에 연결하고 Transact-SQL 문을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-115">Create <xref:System.Data.SqlClient.SqlConnection> and <xref:System.Data.SqlClient.SqlCommand> objects to connect to the server and define a Transact-SQL statement.</span></span>

3. <span data-ttu-id="25d64-116">새 `SqlDependency` 개체를 만들거나 기존 개체를 사용하여 `SqlCommand` 개체에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-116">Create a new `SqlDependency` object, or use an existing one, and bind it to the `SqlCommand` object.</span></span> <span data-ttu-id="25d64-117">내부적으로 이는 <xref:System.Data.Sql.SqlNotificationRequest> 개체를 만들고 필요에 따라 명령 개체에 바인딩합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-117">Internally, this creates a <xref:System.Data.Sql.SqlNotificationRequest> object and binds it to the command object as needed.</span></span> <span data-ttu-id="25d64-118">이 알림 요청에는 이 `SqlDependency` 개체를 고유하게 식별하는 내부 식별자가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-118">This notification request contains an internal identifier that uniquely identifies this `SqlDependency` object.</span></span> <span data-ttu-id="25d64-119">또한 아직 활성 상태가 아닌 경우 클라이언트 수신기를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-119">It also starts the client listener if it is not already active.</span></span>

4. <span data-ttu-id="25d64-120">`SqlDependency` 개체의 `OnChange` 이벤트에 이벤트 처리기를 구독합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-120">Subscribe an event handler to the `OnChange` event of the `SqlDependency` object.</span></span>

5. <span data-ttu-id="25d64-121">`SqlCommand` 개체의 `Execute` 메서드 중 하나를 사용하여 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-121">Execute the command using any of the `Execute` methods of the `SqlCommand` object.</span></span> <span data-ttu-id="25d64-122">명령이 알림 개체에 바인딩되기 때문에 서버에서는 알림을 생성해야 하는 것으로 인식하며 큐 정보는 종속성 큐를 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-122">Because the command is bound to the notification object, the server recognizes that it must generate a notification, and the queue information will point to the dependencies queue.</span></span>

6. <span data-ttu-id="25d64-123">서버에 대한 `SqlDependency` 연결을 중단합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-123">Stop the `SqlDependency` connection to the server.</span></span>

<span data-ttu-id="25d64-124">이후에 사용자가 기본 데이터를 변경하는 경우 Microsoft SQL Server는 이러한 변경 내용에 대해 보류 중 알림이 있음을 감지하고, `SqlDependency.Start`를 호출하여 생성된 기본 `SqlConnection`을 통해 처리되어 클라이언트로 전달되는 알림을 게시합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-124">If any user subsequently changes the underlying data, Microsoft SQL Server detects that there is a notification pending for such a change, and posts a notification that is processed and forwarded to the client through the underlying `SqlConnection` that was created by calling `SqlDependency.Start`.</span></span> <span data-ttu-id="25d64-125">클라이언트 수신기는 무효화 메시지를 수신합니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-125">The client listener receives the invalidation message.</span></span> <span data-ttu-id="25d64-126">그런 다음 클라이언트 수신기는 연결된 `SqlDependency` 개체를 찾고 `OnChange` 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-126">The client listener then locates the associated `SqlDependency` object and fires the `OnChange` event.</span></span>

<span data-ttu-id="25d64-127">다음 코드 조각에서는 애플리케이션 예제를 만드는 데 사용할 디자인 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="25d64-127">The following code fragment shows the design pattern you would use to create a sample application.</span></span>

```vb
Sub Initialization()
    ' Create a dependency connection.
    SqlDependency.Start(connectionString, queueName)
End Sub

Sub SomeMethod()
    ' Assume connection is an open SqlConnection.
    ' Create a new SqlCommand object.
    Using command As New SqlCommand( _
      "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers", _
      connection)

        ' Create a dependency and associate it with the SqlCommand.
        Dim dependency As New SqlDependency(command)
        ' Maintain the refernce in a class member.
        ' Subscribe to the SqlDependency event.
        AddHandler dependency.OnChange, AddressOf OnDependencyChange

        ' Execute the command.
        Using reader = command.ExecuteReader()
            ' Process the DataReader.
        End Using
    End Using
End Sub

' Handler method
Sub OnDependencyChange(ByVal sender As Object, _
    ByVal e As SqlNotificationEventArgs)
    ' Handle the event (for example, invalidate this cache entry).
End Sub

Sub Termination()
    ' Release the dependency
    SqlDependency.Stop(connectionString, queueName)
End Sub
```

```csharp
void Initialization()
{
    // Create a dependency connection.
    SqlDependency.Start(connectionString, queueName);
}

void SomeMethod()
{
    // Assume connection is an open SqlConnection.

    // Create a new SqlCommand object.
    using (SqlCommand command=new SqlCommand(
        "SELECT ShipperID, CompanyName, Phone FROM dbo.Shippers",
        connection))
    {

        // Create a dependency and associate it with the SqlCommand.
        SqlDependency dependency=new SqlDependency(command);
        // Maintain the reference in a class member.

        // Subscribe to the SqlDependency event.
        dependency.OnChange+=new
           OnChangeEventHandler(OnDependencyChange);

        // Execute the command.
        using (SqlDataReader reader = command.ExecuteReader())
        {
            // Process the DataReader.
        }
    }
}

// Handler method
void OnDependencyChange(object sender,
   SqlNotificationEventArgs e )
{
  // Handle the event (for example, invalidate this cache entry).
}

void Termination()
{
    // Release the dependency.
    SqlDependency.Stop(connectionString, queueName);
}
```

## <a name="see-also"></a><span data-ttu-id="25d64-128">참고 항목</span><span class="sxs-lookup"><span data-stu-id="25d64-128">See also</span></span>

- [<span data-ttu-id="25d64-129">SQL Server에서 쿼리 알림</span><span class="sxs-lookup"><span data-stu-id="25d64-129">Query Notifications in SQL Server</span></span>](query-notifications-in-sql-server.md)
- [<span data-ttu-id="25d64-130">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="25d64-130">ADO.NET Overview</span></span>](../ado-net-overview.md)
