---
description: '자세히 알아보기: ADO.NET에서 데이터 원본에 연결'
title: 데이터 원본에 연결
deescription: Learn about Connection objects, used to connect to data sources in ADO.NET. The Connection object you choose depends on the type of data source.
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: 0bf66b9dc609a704cf89380e2376f50197e047a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99663887"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="83645-103">데이터 원본에 연결(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="83645-103">Connecting to a Data Source in ADO.NET</span></span>

<span data-ttu-id="83645-104">ADO.NET에서는 연결 문자열에 필요한 인증 정보를 제공 하 여 **연결** 개체를 사용 하 여 특정 데이터 원본에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="83645-104">In ADO.NET, you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="83645-105">사용하는 **Connection** 개체는 데이터 원본의 형식에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="83645-105">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="83645-106">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbConnection> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbConnection> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlConnection> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcConnection> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleConnection> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="83645-106">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="83645-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="83645-107">In This Section</span></span>  

 <span data-ttu-id="83645-108">[연결 설정](establishing-the-connection.md)</span><span class="sxs-lookup"><span data-stu-id="83645-108">[Establishing the Connection](establishing-the-connection.md)</span></span>\
 <span data-ttu-id="83645-109">**Connection** 개체를 사용하여 데이터 원본에 대한 연결을 설정하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83645-109">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 <span data-ttu-id="83645-110">[연결 이벤트](connection-events.md)</span><span class="sxs-lookup"><span data-stu-id="83645-110">[Connection Events](connection-events.md)</span></span>\
 <span data-ttu-id="83645-111">**InfoMessage** 이벤트를 사용하여 데이터 원본에서 정보 메시지를 검색하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="83645-111">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83645-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="83645-112">See also</span></span>

- [<span data-ttu-id="83645-113">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="83645-113">Connection Strings</span></span>](connection-strings.md)
- [<span data-ttu-id="83645-114">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="83645-114">Connection Pooling</span></span>](connection-pooling.md)
- [<span data-ttu-id="83645-115">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="83645-115">Commands and Parameters</span></span>](commands-and-parameters.md)
- [<span data-ttu-id="83645-116">DataAdapters 및 DataReaders</span><span class="sxs-lookup"><span data-stu-id="83645-116">DataAdapters and DataReaders</span></span>](dataadapters-and-datareaders.md)
- [<span data-ttu-id="83645-117">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="83645-117">Transactions and Concurrency</span></span>](transactions-and-concurrency.md)
- [<span data-ttu-id="83645-118">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="83645-118">ADO.NET Overview</span></span>](ado-net-overview.md)
