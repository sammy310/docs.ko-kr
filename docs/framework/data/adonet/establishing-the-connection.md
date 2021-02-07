---
description: '자세한 정보: 연결 설정'
title: 연결 설정
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 3af512f3-87d9-4005-9e2f-abb1060ff43f
ms.openlocfilehash: e7f8c837476a678f003eb0477934bb8bd08fd896
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99724338"
---
# <a name="establishing-the-connection"></a><span data-ttu-id="ca107-103">연결 설정</span><span class="sxs-lookup"><span data-stu-id="ca107-103">Establishing the Connection</span></span>

<span data-ttu-id="ca107-104">Microsoft SQL Server에 연결하려면 .NET Framework Data Provider for SQL Server의 <xref:System.Data.SqlClient.SqlConnection> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-104">To connect to Microsoft SQL Server, use the <xref:System.Data.SqlClient.SqlConnection> object of the .NET Framework Data Provider for SQL Server.</span></span> <span data-ttu-id="ca107-105">OLE DB 데이터 소스에 연결하려면 .NET Framework Data Provider for OLE DB의 <xref:System.Data.OleDb.OleDbConnection> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-105">To connect to an OLE DB data source, use the <xref:System.Data.OleDb.OleDbConnection> object of the .NET Framework Data Provider for OLE DB.</span></span> <span data-ttu-id="ca107-106">ODBC 데이터 소스에 연결하려면 .NET Framework Data Provider for ODBC의 <xref:System.Data.Odbc.OdbcConnection> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-106">To connect to an ODBC data source, use the <xref:System.Data.Odbc.OdbcConnection> object of the .NET Framework Data Provider for ODBC.</span></span> <span data-ttu-id="ca107-107">Oracle 데이터 소스에 연결하려면 .NET Framework Data Provider for Oracle의 <xref:System.Data.OracleClient.OracleConnection> 개체를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-107">To connect to an Oracle data source, use the <xref:System.Data.OracleClient.OracleConnection> object of the .NET Framework Data Provider for Oracle.</span></span> <span data-ttu-id="ca107-108">연결 문자열을 안전하게 저장하고 검색하려면 [연결 정보 보호](protecting-connection-information.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-108">For securely storing and retrieving connection strings, see [Protecting Connection Information](protecting-connection-information.md).</span></span>  
  
## <a name="closing-connections"></a><span data-ttu-id="ca107-109">연결 닫기</span><span class="sxs-lookup"><span data-stu-id="ca107-109">Closing Connections</span></span>  

 <span data-ttu-id="ca107-110">사용이 끝나면 해당 연결이 풀로 반환되도록 닫아 두는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-110">We recommend that you always close the connection when you are finished using it, so that the connection can be returned to the pool.</span></span> <span data-ttu-id="ca107-111">Visual Basic 또는 C#의 `Using` 블록은 처리되지 않은 예외가 발생하더라도 코드에 블록이 있으면 연결을 자동으로 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-111">The `Using` block in Visual Basic or C# automatically disposes of the connection when the code exits the block, even in the case of an unhandled exception.</span></span> <span data-ttu-id="ca107-112">자세한 내용은 [using 문](../../../csharp/language-reference/keywords/using-statement.md) 및 [Using 문](../../../visual-basic/language-reference/statements/using-statement.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-112">See [using Statement](../../../csharp/language-reference/keywords/using-statement.md) and [Using Statement](../../../visual-basic/language-reference/statements/using-statement.md) for more information.</span></span>  
  
 <span data-ttu-id="ca107-113">사용 중인 공급자에 대해 연결 개체의 `Close` 또는 `Dispose` 메서드를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-113">You can also use the `Close` or `Dispose` methods of the connection object for the provider that you are using.</span></span> <span data-ttu-id="ca107-114">명시적으로 닫히지 않은 연결은 풀에 추가되거나 반환되지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-114">Connections that are not explicitly closed might not be added or returned to the pool.</span></span> <span data-ttu-id="ca107-115">예를 들어, 범위를 벗어났지만 명시적으로 닫히지 않은 연결은 최대 풀 크기에 도달했으며 여전히 유효한 경우에만 연결 풀로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-115">For example, a connection that has gone out of scope but that has not been explicitly closed will only be returned to the connection pool if the maximum pool size has been reached and the connection is still valid.</span></span> <span data-ttu-id="ca107-116">자세한 내용은 [OLE DB, ODBC 및 Oracle 연결 풀링](ole-db-odbc-and-oracle-connection-pooling.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-116">For more information, see [OLE DB, ODBC, and Oracle Connection Pooling](ole-db-odbc-and-oracle-connection-pooling.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca107-117">클래스의 `Finalize` 메소드에 있는 **Connection**, **DataReader** 또는 기타 관리 개체에서 `Close` 또는 `Dispose`를 호출하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-117">Do not call `Close` or `Dispose` on a **Connection**, a **DataReader**, or any other managed object in the `Finalize` method of your class.</span></span> <span data-ttu-id="ca107-118">종료자에서는 클래스에 직접 속한 관리되지 않는 리소스만 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-118">In a finalizer, only release unmanaged resources that your class owns directly.</span></span> <span data-ttu-id="ca107-119">클래스에 관리되지 않는 리소스가 없는 경우 클래스 정의에 `Finalize` 메서드를 포함하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-119">If your class does not own any unmanaged resources, do not include a `Finalize` method in your class definition.</span></span> <span data-ttu-id="ca107-120">자세한 내용은 [가비지 수집](../../../standard/garbage-collection/index.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-120">For more information, see [Garbage Collection](../../../standard/garbage-collection/index.md).</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca107-121">연결이 연결 풀에서 반환될 경우에는 실제로 해제된 것이 아니므로 연결이 연결 풀에서 반입되거나 연결 풀로 반환되는 경우 서버에서 로그인 및 로그아웃 이벤트가 발생하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-121">Login and logout events will not be raised on the server when a connection is fetched from or returned to the connection pool, because the connection is not actually closed when it is returned to the connection pool.</span></span> <span data-ttu-id="ca107-122">자세한 내용은 [SQL Server 연결 풀링(ADO.NET)](sql-server-connection-pooling.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-122">For more information, see [SQL Server Connection Pooling (ADO.NET)](sql-server-connection-pooling.md).</span></span>  
  
## <a name="connecting-to-sql-server"></a><span data-ttu-id="ca107-123">SQL Server에 연결</span><span class="sxs-lookup"><span data-stu-id="ca107-123">Connecting to SQL Server</span></span>  

 <span data-ttu-id="ca107-124">.NET Framework Data Provider for SQL Server에서는 OLE DB(ADO) 연결 문자열 형식과 유사한 연결 문자열 형식을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-124">The .NET Framework Data Provider for SQL Server supports a connection string format that is similar to the OLE DB (ADO) connection string format.</span></span> <span data-ttu-id="ca107-125">유효한 문자열 형식 이름 및 값은 <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> 개체의 <xref:System.Data.SqlClient.SqlConnection> 속성을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-125">For valid string format names and values, see the <xref:System.Data.SqlClient.SqlConnection.ConnectionString%2A> property of the <xref:System.Data.SqlClient.SqlConnection> object.</span></span> <span data-ttu-id="ca107-126"><xref:System.Data.SqlClient.SqlConnectionStringBuilder> 클래스를 사용하여 런타임에 구문상 유효한 연결 문자열을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-126">You can also use the <xref:System.Data.SqlClient.SqlConnectionStringBuilder> class to create syntactically valid connection strings at run time.</span></span> <span data-ttu-id="ca107-127">자세한 내용은 [연결 문자열 작성기](connection-string-builders.md)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-127">For more information, see [Connection String Builders](connection-string-builders.md).</span></span>  
  
 <span data-ttu-id="ca107-128">다음 코드 예제에서는 SQL Server 데이터베이스에 대해 연결을 만들어 여는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-128">The following code example demonstrates how to create and open a connection to a SQL Server database.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New SqlConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (SqlConnection connection = new SqlConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
### <a name="integrated-security-and-aspnet"></a><span data-ttu-id="ca107-129">통합 보안 및 ASP.NET</span><span class="sxs-lookup"><span data-stu-id="ca107-129">Integrated Security and ASP.NET</span></span>  

 <span data-ttu-id="ca107-130">트러스트된 연결이라고도 하는 SQL Server 통합 보안은 연결 문자열에 사용자 ID와 암호를 노출하지 않아 안전하게 SQL Server에 연결할 수 있으므로 연결 인증에 권장되는 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-130">SQL Server integrated security (also known as trusted connections) helps to provide protection when connecting to SQL Server as it does not expose a user ID and password in the connection string and is the recommended method for authenticating a connection.</span></span> <span data-ttu-id="ca107-131">통합 보안에서는 실행 중인 프로세스의 현재 보안 ID, 즉 토큰을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-131">Integrated security uses the current security identity, or token, of the executing process.</span></span> <span data-ttu-id="ca107-132">데스크톱 애플리케이션의 경우에는 일반적으로 현재 로그온한 사용자의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-132">For desktop applications, this is typically the identity of the currently logged-on user.</span></span>  
  
 <span data-ttu-id="ca107-133">ASP.NET 애플리케이션의 보안 ID는 여러 가지 서로 다른 옵션 중 하나로 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-133">The security identity for ASP.NET applications can be set to one of several different options.</span></span> <span data-ttu-id="ca107-134">ASP.NET 애플리케이션에서 SQL Server에 연결할 때 사용하는 보안 ID에 대한 자세한 내용은 [ASP.NET 가장](/previous-versions/aspnet/xh507fc5(v=vs.100)), [ASP.NET 인증](/previous-versions/aspnet/eeyk640h(v=vs.100)) 및 [방법: Windows 통합 보안을 사용하여 SQL Server에 액세스](/previous-versions/aspnet/bsz5788z(v=vs.100))를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-134">To better understand the security identity that an ASP.NET application uses when connecting to SQL Server, see [ASP.NET Impersonation](/previous-versions/aspnet/xh507fc5(v=vs.100)), [ASP.NET Authentication](/previous-versions/aspnet/eeyk640h(v=vs.100)), and [How to: Access SQL Server Using Windows Integrated Security](/previous-versions/aspnet/bsz5788z(v=vs.100)).</span></span>  
  
## <a name="connecting-to-an-ole-db-data-source"></a><span data-ttu-id="ca107-135">OLE DB 데이터 소스 연결</span><span class="sxs-lookup"><span data-stu-id="ca107-135">Connecting to an OLE DB Data Source</span></span>  

 <span data-ttu-id="ca107-136">OLE DB에 대 한 .NET Framework Data Provider는 **OleDbConnection** 개체를 사용 하 여 OLE DB를 사용 하 여 노출 된 데이터 원본에 대 한 연결을 제공 합니다 (예를 들어 OLE DB에 대 한 SQL Server 공급자).</span><span class="sxs-lookup"><span data-stu-id="ca107-136">The .NET Framework Data Provider for OLE DB provides connectivity to data sources exposed using OLE DB (through SQLOLEDB, the OLE DB Provider for SQL Server), using the **OleDbConnection** object.</span></span>  
  
 <span data-ttu-id="ca107-137">.NET Framework Data Provider for OLE DB의 경우 연결 문자열 형식은 ADO에서 사용되는 연결 문자열 형식과 동일하지만, 다음과 같은 예외가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-137">For the .NET Framework Data Provider for OLE DB, the connection string format is identical to the connection string format used in ADO, with the following exceptions:</span></span>  
  
- <span data-ttu-id="ca107-138">**공급자** 키워드가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-138">The **Provider** keyword is required.</span></span>  
  
- <span data-ttu-id="ca107-139">**URL**, **원격 공급자** 및 **원격 서버** 키워드는 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-139">The **URL**, **Remote Provider**, and **Remote Server** keywords are not supported.</span></span>  
  
 <span data-ttu-id="ca107-140">OLE DB 연결 문자열에 대한 자세한 내용은 <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> 항목을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca107-140">For more information about OLE DB connection strings, see the <xref:System.Data.OleDb.OleDbConnection.ConnectionString%2A> topic.</span></span> <span data-ttu-id="ca107-141"><xref:System.Data.OleDb.OleDbConnectionStringBuilder>를 사용하여 런타임에 연결 문자열을 만들 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-141">You can also use the <xref:System.Data.OleDb.OleDbConnectionStringBuilder> to create connection strings at run time.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="ca107-142">**OleDbConnection** 개체는 OLE DB 공급자와 관련 된 동적 속성을 설정 하거나 검색 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-142">The **OleDbConnection** object does not support setting or retrieving dynamic properties specific to an OLE DB provider.</span></span> <span data-ttu-id="ca107-143">OLE DB 공급자의 연결 문자열에 전달 될 수 있는 속성만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-143">Only properties that can be passed in the connection string for the OLE DB provider are supported.</span></span>  
  
 <span data-ttu-id="ca107-144">다음 코드 예제에서는 OLE DB 데이터 소스에 대해 연결을 만들어 여는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-144">The following code example demonstrates how to create and open a connection to an OLE DB data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OleDbConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OleDbConnection connection =
  new OleDbConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="do-not-use-universal-data-link-files"></a><span data-ttu-id="ca107-145">유니버설 데이터 링크 파일 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="ca107-145">Do Not Use Universal Data Link Files</span></span>  

 <span data-ttu-id="ca107-146">UDL (Universal Data Link) 파일에 **OleDbConnection** 에 대 한 연결 정보를 제공할 수 있습니다. 그러나 이렇게 하지 않는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-146">It is possible to supply connection information for an **OleDbConnection** in a Universal Data Link (UDL) file; however you should avoid doing so.</span></span> <span data-ttu-id="ca107-147">UDL 파일은 암호화되지 않으므로 연결 문자열 정보를 일반 텍스트로 노출시킵니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-147">UDL files are not encrypted, and expose connection string information in clear text.</span></span> <span data-ttu-id="ca107-148">UDL 파일은 애플리케이션에 대해 외부 파일 기반 리소스이므로 .NET Framework를 사용하여 보호할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-148">Because a UDL file is an external file-based resource to your application, it cannot be secured using the .NET Framework.</span></span>  
  
## <a name="connecting-to-an-odbc-data-source"></a><span data-ttu-id="ca107-149">ODBC 데이터 소스 연결</span><span class="sxs-lookup"><span data-stu-id="ca107-149">Connecting to an ODBC Data Source</span></span>  

 <span data-ttu-id="ca107-150">ODBC에 대 한 .NET Framework Data Provider는 **odbcconnection.connectionstring** 개체를 사용 하 여 odbc를 통해 노출 된 데이터 원본에 대 한 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-150">The .NET Framework Data Provider for ODBC provides connectivity to data sources exposed using ODBC using the **OdbcConnection** object.</span></span>  
  
 <span data-ttu-id="ca107-151">.NET Framework Data Provider for ODBC의 경우 연결 문자열 형식은 ODBC 연결 문자열 형식에 최대한 일치하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-151">For the .NET Framework Data Provider for ODBC, the connection string format is designed to match the ODBC connection string format as closely as possible.</span></span> <span data-ttu-id="ca107-152">또한 ODBC DSN(데이터 소스 이름)을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-152">You may also supply an ODBC data source name (DSN).</span></span> <span data-ttu-id="ca107-153">**Odbcconnection.connectionstring** 에 대 한 자세한 내용은를 참조 하십시오 <xref:System.Data.Odbc.OdbcConnection> .</span><span class="sxs-lookup"><span data-stu-id="ca107-153">For more detail on the **OdbcConnection** , see the <xref:System.Data.Odbc.OdbcConnection>.</span></span>  
  
 <span data-ttu-id="ca107-154">다음 코드 예제에서는 ODBC 데이터 소스에 대해 연결을 만들어 여는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-154">The following code example demonstrates how to create and open a connection to an ODBC data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OdbcConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OdbcConnection connection =
  new OdbcConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
```  
  
## <a name="connecting-to-an-oracle-data-source"></a><span data-ttu-id="ca107-155">Oracle 데이터 소스 연결</span><span class="sxs-lookup"><span data-stu-id="ca107-155">Connecting to an Oracle Data Source</span></span>  

 <span data-ttu-id="ca107-156">Oracle의 .NET Framework Data Provider는 **OracleConnection** 개체를 사용 하 여 oracle 데이터 원본에 대 한 연결을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-156">The .NET Framework Data Provider for Oracle provides connectivity to Oracle data sources using the **OracleConnection** object.</span></span>  
  
 <span data-ttu-id="ca107-157">.NET Framework Data Provider for Oracle의 경우 연결 문자열 형식은 MSDAORA(OLE DB Provider for Oracle) 연결 문자열 형식에 최대한 일치하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-157">For the .NET Framework Data Provider for Oracle, the connection string format is designed to match the OLE DB Provider for Oracle (MSDAORA) connection string format as closely as possible.</span></span> <span data-ttu-id="ca107-158">**OracleConnection** 에 대 한 자세한 내용은를 참조 하십시오 <xref:System.Data.OracleClient.OracleConnection> .</span><span class="sxs-lookup"><span data-stu-id="ca107-158">For more detail on the **OracleConnection**, see the <xref:System.Data.OracleClient.OracleConnection>.</span></span>  
  
 <span data-ttu-id="ca107-159">다음 코드 예제에서는 Oracle 데이터 소스에 대해 연결을 만들어 여는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="ca107-159">The following code example demonstrates how to create and open a connection to an Oracle data source.</span></span>  
  
```vb  
' Assumes connectionString is a valid connection string.  
Using connection As New OracleConnection(connectionString)  
    connection.Open()  
    ' Do work here.  
End Using  
```  
  
```csharp  
// Assumes connectionString is a valid connection string.  
using (OracleConnection connection =
  new OracleConnection(connectionString))  
{  
    connection.Open();  
    // Do work here.  
}  
OracleConnection nwindConn = new OracleConnection("Data Source=MyOracleServer;Integrated Security=yes;");  
nwindConn.Open();  
```  
  
## <a name="see-also"></a><span data-ttu-id="ca107-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca107-160">See also</span></span>

- [<span data-ttu-id="ca107-161">데이터 소스에 연결</span><span class="sxs-lookup"><span data-stu-id="ca107-161">Connecting to a Data Source</span></span>](connecting-to-a-data-source.md)
- [<span data-ttu-id="ca107-162">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="ca107-162">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="ca107-163">OLE DB, ODBC 및 Oracle 연결 풀링</span><span class="sxs-lookup"><span data-stu-id="ca107-163">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)
- [<span data-ttu-id="ca107-164">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="ca107-164">ADO.NET Overview</span></span>](ado-net-overview.md)
