---
title: 연결 풀링
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: 4cba53993489f51ed39ac52bff4fa252beb9aafd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180455"
---
# <a name="connection-pooling"></a><span data-ttu-id="c76c8-102">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="c76c8-102">Connection Pooling</span></span>
<span data-ttu-id="c76c8-103">데이터 소스에 연결하는 작업은 시간이 많이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c76c8-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="c76c8-104">ADO.NET 연결을 여는 비용을 최소화 하려면 이라는 최적화 기법을 사용 *연결 풀링을*를 반복적으로 열고 닫는 연결의 비용을 최소화 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="c76c8-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="c76c8-105">연결 풀링은 .NET Framework 데이터 공급자마다 각각 다른 방식으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="c76c8-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c76c8-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="c76c8-106">In This Section</span></span>  
 [<span data-ttu-id="c76c8-107">SQL Server 연결 풀링(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="c76c8-107">SQL Server Connection Pooling (ADO.NET)</span></span>](../../../../docs/framework/data/adonet/sql-server-connection-pooling.md)  
 <span data-ttu-id="c76c8-108">연결 풀링에 대해 간략하게 설명 하 고 SQL Server에서 연결 풀링이 작동 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c76c8-108">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="c76c8-109">OLE DB, ODBC 및 Oracle 연결 풀링</span><span class="sxs-lookup"><span data-stu-id="c76c8-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](../../../../docs/framework/data/adonet/ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="c76c8-110">.NET Framework Data Provider for OLE DB, .NET Framework Data Provider for ODBC 및 .NET Framework Data Provider for Oracle의 연결 풀링에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c76c8-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c76c8-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="c76c8-111">See also</span></span>

- [<span data-ttu-id="c76c8-112">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="c76c8-112">Retrieving and Modifying Data in ADO.NET</span></span>](../../../../docs/framework/data/adonet/retrieving-and-modifying-data.md)
- [<span data-ttu-id="c76c8-113">ADO.NET 관리되는 공급자 및 데이터 집합 개발자 센터</span><span class="sxs-lookup"><span data-stu-id="c76c8-113">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
