---
title: 연결 풀링
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: c431011cf57fd9ef79c2f0a099ab1080116c571f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70786718"
---
# <a name="connection-pooling"></a><span data-ttu-id="a6a0e-102">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="a6a0e-102">Connection Pooling</span></span>
<span data-ttu-id="a6a0e-103">데이터 소스에 연결하는 작업은 시간이 많이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6a0e-103">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="a6a0e-104">연결을 여는 비용을 최소화 하기 위해 ADO.NET에서는 연결 *풀링*이라는 최적화 기법을 사용 하 여 연결을 반복적으로 열고 닫는 데 드는 비용을 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a0e-104">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="a6a0e-105">연결 풀링은 .NET Framework 데이터 공급자마다 각각 다른 방식으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6a0e-105">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="a6a0e-106">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="a6a0e-106">In This Section</span></span>  
 [<span data-ttu-id="a6a0e-107">SQL Server 연결 풀링(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="a6a0e-107">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="a6a0e-108">연결 풀링의 개요를 제공 하 고 SQL Server 연결 풀링이 작동 하는 방식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a0e-108">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="a6a0e-109">OLE DB, ODBC 및 Oracle 연결 풀링</span><span class="sxs-lookup"><span data-stu-id="a6a0e-109">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="a6a0e-110">.NET Framework Data Provider for OLE DB, .NET Framework Data Provider for ODBC 및 .NET Framework Data Provider for Oracle의 연결 풀링에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a6a0e-110">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a6a0e-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="a6a0e-111">See also</span></span>

- [<span data-ttu-id="a6a0e-112">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="a6a0e-112">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="a6a0e-113">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="a6a0e-113">ADO.NET Overview</span></span>](ado-net-overview.md)
