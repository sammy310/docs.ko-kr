---
title: 데이터 원본에 연결
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: b9e69b029ad37c583e51c219f87ff9d7d8e7315c
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91203776"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="c81d9-102">데이터 원본에 연결(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="c81d9-102">Connecting to a Data Source in ADO.NET</span></span>

<span data-ttu-id="c81d9-103">ADO.NET에서는 연결 문자열에 필요한 인증 정보를 제공 하 여 **연결** 개체를 사용 하 여 특정 데이터 원본에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81d9-103">In ADO.NET, you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="c81d9-104">사용 하는 **연결** 개체는 데이터 원본 유형에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="c81d9-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="c81d9-105">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbConnection> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbConnection> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlConnection> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcConnection> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleConnection> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c81d9-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c81d9-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c81d9-106">In This Section</span></span>  

 <span data-ttu-id="c81d9-107">[연결 설정](establishing-the-connection.md)</span><span class="sxs-lookup"><span data-stu-id="c81d9-107">[Establishing the Connection](establishing-the-connection.md)</span></span>\
 <span data-ttu-id="c81d9-108">**Connection** 개체를 사용 하 여 데이터 원본에 대 한 연결을 설정 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81d9-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 <span data-ttu-id="c81d9-109">[연결 이벤트](connection-events.md)</span><span class="sxs-lookup"><span data-stu-id="c81d9-109">[Connection Events](connection-events.md)</span></span>\
 <span data-ttu-id="c81d9-110">**InfoMessage** 이벤트를 사용 하 여 데이터 소스에서 정보 메시지를 검색 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c81d9-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c81d9-111">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c81d9-111">See also</span></span>

- [<span data-ttu-id="c81d9-112">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="c81d9-112">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="c81d9-113">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="c81d9-113">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="c81d9-114">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="c81d9-114">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="c81d9-115">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="c81d9-115">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="c81d9-116">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="c81d9-116">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="c81d9-117">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="c81d9-117">ADO.NET Overview</span></span>](ado-net-overview.md)
