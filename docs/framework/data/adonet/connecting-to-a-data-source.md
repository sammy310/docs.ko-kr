---
title: 데이터 원본에 연결(ADO.NET)
ms.date: 03/30/2017
ms.assetid: 9abc3f92-1be3-4e1a-b360-762dc689650e
ms.openlocfilehash: c04624be758e4bc7c8b1981ad6a9dc44430d62b5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59083714"
---
# <a name="connecting-to-a-data-source-in-adonet"></a><span data-ttu-id="940cc-102">데이터 원본에 연결(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="940cc-102">Connecting to a Data Source in ADO.NET</span></span>
<span data-ttu-id="940cc-103">ADO.NET 사용 하 여는 **연결** 개체에 연결 문자열에 필요한 인증 정보를 제공 하 여 특정 데이터 원본에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="940cc-103">In ADO.NET you use a **Connection** object to connect to a specific data source by supplying necessary authentication information in a connection string.</span></span> <span data-ttu-id="940cc-104">합니다 **연결** 개체를 사용 하면 데이터 원본의 유형에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="940cc-104">The **Connection** object you use depends on the type of data source.</span></span>  
  
 <span data-ttu-id="940cc-105">.NET Framework에 포함된 각 .NET Framework 데이터 공급자에는 <xref:System.Data.Common.DbConnection> 개체가 있습니다. .NET Framework Data Provider for OLE DB에는 <xref:System.Data.OleDb.OleDbConnection> 개체가 있고 .NET Framework Data Provider for SQL Server에는 <xref:System.Data.SqlClient.SqlConnection> 개체가 있으며 .NET Framework Data Provider for ODBC에는 <xref:System.Data.Odbc.OdbcConnection> 개체가 있고 .NET Framework Data Provider for Oracle에는 <xref:System.Data.OracleClient.OracleConnection> 개체가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="940cc-105">Each .NET Framework data provider included with the .NET Framework has a <xref:System.Data.Common.DbConnection> object: the .NET Framework Data Provider for OLE DB includes an <xref:System.Data.OleDb.OleDbConnection> object, the .NET Framework Data Provider for SQL Server includes a <xref:System.Data.SqlClient.SqlConnection> object, the .NET Framework Data Provider for ODBC includes an <xref:System.Data.Odbc.OdbcConnection> object, and the .NET Framework Data Provider for Oracle includes an <xref:System.Data.OracleClient.OracleConnection> object.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="940cc-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="940cc-106">In This Section</span></span>  
 [<span data-ttu-id="940cc-107">연결 설정</span><span class="sxs-lookup"><span data-stu-id="940cc-107">Establishing the Connection</span></span>](../../../../docs/framework/data/adonet/establishing-the-connection.md)  
 <span data-ttu-id="940cc-108">사용 하는 방법에 설명 합니다는 **연결** 개체 데이터 원본에 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="940cc-108">Describes how to use a **Connection** object to establish a connection to a data source.</span></span>  
  
 [<span data-ttu-id="940cc-109">연결 이벤트</span><span class="sxs-lookup"><span data-stu-id="940cc-109">Connection Events</span></span>](../../../../docs/framework/data/adonet/connection-events.md)  
 <span data-ttu-id="940cc-110">사용 하는 방법에 설명 합니다는 **InfoMessage** 이벤트 데이터 원본에서 정보 메시지를 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="940cc-110">Describes how to use an **InfoMessage** event to retrieve informational messages from a data source.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="940cc-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="940cc-111">See also</span></span>

- [<span data-ttu-id="940cc-112">연결 문자열</span><span class="sxs-lookup"><span data-stu-id="940cc-112">Connection Strings</span></span>](../../../../docs/framework/data/adonet/connection-strings.md)
- [<span data-ttu-id="940cc-113">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="940cc-113">Connection Pooling</span></span>](../../../../docs/framework/data/adonet/connection-pooling.md)
- [<span data-ttu-id="940cc-114">명령 및 매개 변수</span><span class="sxs-lookup"><span data-stu-id="940cc-114">Commands and Parameters</span></span>](../../../../docs/framework/data/adonet/commands-and-parameters.md)
- [<span data-ttu-id="940cc-115">DataAdapter 및 DataReader</span><span class="sxs-lookup"><span data-stu-id="940cc-115">DataAdapters and DataReaders</span></span>](../../../../docs/framework/data/adonet/dataadapters-and-datareaders.md)
- [<span data-ttu-id="940cc-116">트랜잭션 및 동시성</span><span class="sxs-lookup"><span data-stu-id="940cc-116">Transactions and Concurrency</span></span>](../../../../docs/framework/data/adonet/transactions-and-concurrency.md)
- [<span data-ttu-id="940cc-117">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="940cc-117">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
