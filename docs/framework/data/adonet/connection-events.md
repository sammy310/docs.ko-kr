---
description: '자세한 정보: 연결 이벤트'
title: 연결 이벤트
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 5a29de74-acfc-4134-8616-829dd7ce0710
ms.openlocfilehash: fcf131e41ce90db11e84fd241744e348f4ca739e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663809"
---
# <a name="connection-events"></a><span data-ttu-id="2cd69-103">연결 이벤트</span><span class="sxs-lookup"><span data-stu-id="2cd69-103">Connection Events</span></span>

<span data-ttu-id="2cd69-104">모든 .NET Framework 데이터 공급자에는 데이터 원본에서 정보 메시지를 검색 하거나 **연결** 상태가 변경 되었는지 여부를 확인 하는 데 사용할 수 있는 두 개의 이벤트가 포함 된 **연결** 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-104">All of the .NET Framework data providers have **Connection** objects with two events that you can use to retrieve informational messages from a data source or to determine if the state of a **Connection** has changed.</span></span> <span data-ttu-id="2cd69-105">다음 표는 **Connection** 개체의 이벤트를 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-105">The following table describes the events of the **Connection** object.</span></span>  
  
|<span data-ttu-id="2cd69-106">이벤트</span><span class="sxs-lookup"><span data-stu-id="2cd69-106">Event</span></span>|<span data-ttu-id="2cd69-107">Description</span><span class="sxs-lookup"><span data-stu-id="2cd69-107">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="2cd69-108">**InfoMessage**</span><span class="sxs-lookup"><span data-stu-id="2cd69-108">**InfoMessage**</span></span>|<span data-ttu-id="2cd69-109">정보 메시지가 데이터 소스에서 반환될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-109">Occurs when an informational message is returned from a data source.</span></span> <span data-ttu-id="2cd69-110">정보 메시지는 예외가 throw되지 않는 데이터 소스의 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-110">Informational messages are messages from a data source that do not result in an exception being thrown.</span></span>|  
|<span data-ttu-id="2cd69-111">**StateChange**</span><span class="sxs-lookup"><span data-stu-id="2cd69-111">**StateChange**</span></span>|<span data-ttu-id="2cd69-112">**연결** 상태가 변경되면 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-112">Occurs when the state of the **Connection** changes.</span></span>|  
  
## <a name="working-with-the-infomessage-event"></a><span data-ttu-id="2cd69-113">InfoMessage 이벤트 사용</span><span class="sxs-lookup"><span data-stu-id="2cd69-113">Working with the InfoMessage Event</span></span>  

 <span data-ttu-id="2cd69-114"><xref:System.Data.SqlClient.SqlConnection.InfoMessage> 개체의 <xref:System.Data.SqlClient.SqlConnection> 이벤트를 사용하여 SQL Server 데이터 소스에서 경고 및 정보 메시지를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-114">You can retrieve warnings and informational messages from a SQL Server data source using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="2cd69-115">데이터 소스에서 반환된 오류의 심각도 수준이 11~16에 해당하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-115">Errors returned from the data source with a severity level of 11 through 16 cause an exception to be thrown.</span></span> <span data-ttu-id="2cd69-116">그러나 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 사용하여 오류와 무관한 데이터 소스의 메시지를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-116">However, the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event can be used to obtain messages from the data source that are not associated with an error.</span></span> <span data-ttu-id="2cd69-117">Microsoft SQL Server의 경우 심각도 수준 10 이하의 모든 오류는 정보 메시지로 간주되고 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 사용하여 캡처될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-117">In the case of Microsoft SQL Server, any error with a severity of 10 or less is considered to be an informational message, and can be captured by using the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span> <span data-ttu-id="2cd69-118">자세한 내용은 [데이터베이스 엔진 오류 심각도](/sql/relational-databases/errors-events/database-engine-error-severities) 문서를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2cd69-118">For more information, see the [Database Engine Error Severities](/sql/relational-databases/errors-events/database-engine-error-severities) article.</span></span>
  
 <span data-ttu-id="2cd69-119"><xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트는 **오류** 속성에 데이터 원본의 메시지 모음을 포함하는 <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> 개체를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-119">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event receives an <xref:System.Data.SqlClient.SqlInfoMessageEventArgs> object containing, in its **Errors** property, a collection of the messages from the data source.</span></span> <span data-ttu-id="2cd69-120">이 컬렉션의 **오류** 개체에서 오류 번호와 메시지 텍스트 및 오류 소스를 쿼리 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-120">You can query the **Error** objects in this collection for the error number and message text, as well as the source of the error.</span></span> <span data-ttu-id="2cd69-121">.NET Framework Data Provider for SQL Server는 메시지가 발생한 데이터베이스, 저장 프로시저 및 줄 번호에 대한 자세한 내용도 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-121">The .NET Framework Data Provider for SQL Server also includes detail about the database, stored procedure, and line number that the message came from.</span></span>  
  
### <a name="example"></a><span data-ttu-id="2cd69-122">예제</span><span class="sxs-lookup"><span data-stu-id="2cd69-122">Example</span></span>  

 <span data-ttu-id="2cd69-123">다음 코드 예제에서는 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트에 대한 이벤트 처리기를 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-123">The following code example shows how to add an event handler for the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
```vb  
' Assumes that connection represents a SqlConnection object.  
  AddHandler connection.InfoMessage, _  
    New SqlInfoMessageEventHandler(AddressOf OnInfoMessage)  
  
Private Shared Sub OnInfoMessage(sender As Object, _  
  args As SqlInfoMessageEventArgs)  
  Dim err As SqlError  
  For Each err In args.Errors  
    Console.WriteLine("The {0} has received a severity {1}, _  
       state {2} error number {3}\n" & _  
      "on line {4} of procedure {5} on server {6}:\n{7}", _  
      err.Source, err.Class, err.State, err.Number, err.LineNumber, _  
    err.Procedure, err.Server, err.Message)  
  Next  
End Sub  
```  
  
```csharp  
// Assumes that connection represents a SqlConnection object.  
  connection.InfoMessage +=
    new SqlInfoMessageEventHandler(OnInfoMessage);  
  
protected static void OnInfoMessage(  
  object sender, SqlInfoMessageEventArgs args)  
{  
  foreach (SqlError err in args.Errors)  
  {  
    Console.WriteLine(  
  "The {0} has received a severity {1}, state {2} error number {3}\n" +  
  "on line {4} of procedure {5} on server {6}:\n{7}",  
   err.Source, err.Class, err.State, err.Number, err.LineNumber,
   err.Procedure, err.Server, err.Message);  
  }  
}  
```  
  
## <a name="handling-errors-as-infomessages"></a><span data-ttu-id="2cd69-124">오류를 InfoMessages로 처리</span><span class="sxs-lookup"><span data-stu-id="2cd69-124">Handling Errors as InfoMessages</span></span>  

 <span data-ttu-id="2cd69-125"><xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트는 일반적으로 서버에서 전송되는 정보 및 경고 메시지에 대해서만 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-125">The <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event will normally fire only for informational and warning messages that are sent from the server.</span></span> <span data-ttu-id="2cd69-126">그러나 실제 오류가 발생하면 서버 작업을 시작한 **ExecuteNonQuery** 또는 **ExecuteReader** 메서드의 실행이 중지되고 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-126">However, when an actual error occurs, the execution of the **ExecuteNonQuery** or **ExecuteReader** method that initiated the server operation is halted and an exception is thrown.</span></span>  
  
 <span data-ttu-id="2cd69-127">서버에서 발생한 오류와는 상관없이 명령에서 나머지 문을 계속 처리하려면 <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A>의 <xref:System.Data.SqlClient.SqlConnection> 속성을 `true`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-127">If you want to continue processing the rest of the statements in a command regardless of any errors produced by the server, set the <xref:System.Data.SqlClient.SqlConnection.FireInfoMessageEventOnUserErrors%2A> property of the <xref:System.Data.SqlClient.SqlConnection> to `true`.</span></span> <span data-ttu-id="2cd69-128">이렇게 하면 연결에서 예외를 throw하고 처리를 중단하는 대신 오류에 대해 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트를 발생시킵니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-128">Doing this causes the connection to fire the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event for errors instead of throwing an exception and interrupting processing.</span></span> <span data-ttu-id="2cd69-129">그러면 클라이언트 애플리케이션에서 이 이벤트를 처리하고 오류 조건에 응답할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-129">The client application can then handle this event and respond to error conditions.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2cd69-130">심각도 수준이 17 이상인 오류는 서버에서 명령 처리를 중지하도록 하며 예외로 처리되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-130">An error with a severity level of 17 or above that causes the server to stop processing the command must be handled as an exception.</span></span> <span data-ttu-id="2cd69-131">이 경우 오류가 <xref:System.Data.SqlClient.SqlConnection.InfoMessage> 이벤트에서 처리되는 방법과 상관없이 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-131">In this case, an exception is thrown regardless of how the error is handled in the <xref:System.Data.SqlClient.SqlConnection.InfoMessage> event.</span></span>  
  
## <a name="working-with-the-statechange-event"></a><span data-ttu-id="2cd69-132">StateChange 이벤트 사용</span><span class="sxs-lookup"><span data-stu-id="2cd69-132">Working with the StateChange Event</span></span>  

 <span data-ttu-id="2cd69-133">**StateChange** 이벤트는 **연결** 상태가 변경될 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-133">The **StateChange** event occurs when the state of a **Connection** changes.</span></span> <span data-ttu-id="2cd69-134">**StateChange** 이벤트는 **OriginalState** 및 **CurrentState** 속성을 사용하여 **연결** 의 상태 변경을 확인할 수 있는 <xref:System.Data.StateChangeEventArgs>를 받습니다. .</span><span class="sxs-lookup"><span data-stu-id="2cd69-134">The **StateChange** event receives <xref:System.Data.StateChangeEventArgs> that enable you to determine the change in state of the **Connection** by using the **OriginalState** and **CurrentState** properties.</span></span> <span data-ttu-id="2cd69-135">**OriginalState** 속성은 변경되기 전의 **연결** 상태를 나타내는 <xref:System.Data.ConnectionState> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-135">The **OriginalState** property is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** before it changed.</span></span> <span data-ttu-id="2cd69-136">**CurrentState** 는 **연결** 이 변경된 후의 상태를 나타내는 <xref:System.Data.ConnectionState> 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-136">**CurrentState** is a <xref:System.Data.ConnectionState> enumeration that indicates the state of the **Connection** after it changed.</span></span>  
  
 <span data-ttu-id="2cd69-137">다음 코드 예제는 **StateChange** 이벤트를 사용하여 **연결** 상태가 변경될 때 콘솔에 메시지를 씁니다.</span><span class="sxs-lookup"><span data-stu-id="2cd69-137">The following code example uses the **StateChange** event to write a message to the console when the state of the **Connection** changes.</span></span>  
  
```vb  
' Assumes connection represents a SqlConnection object.  
  AddHandler connection.StateChange, _  
    New StateChangeEventHandler(AddressOf OnStateChange)  
  
Protected Shared Sub OnStateChange( _  
  sender As Object, args As StateChangeEventArgs)  
  
  Console.WriteLine( _  
  "The current Connection state has changed from {0} to {1}.", _  
  args.OriginalState, args.CurrentState)  
End Sub  
```  
  
```csharp  
// Assumes connection represents a SqlConnection object.  
  connection.StateChange  += new StateChangeEventHandler(OnStateChange);  
  
protected static void OnStateChange(object sender,
  StateChangeEventArgs args)  
{  
  Console.WriteLine(  
    "The current Connection state has changed from {0} to {1}.",  
      args.OriginalState, args.CurrentState);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="2cd69-138">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2cd69-138">See also</span></span>

- [<span data-ttu-id="2cd69-139">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="2cd69-139">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="2cd69-140">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="2cd69-140">ADO.NET Overview</span></span>](ado-net-overview.md)
