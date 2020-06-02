---
title: 연결 풀링
description: ADO.NET에서 데이터 원본에 대 한 연결을 여는 데 드는 비용을 최소화 하기 위해 사용 하는 최적화 방법인 연결 풀링을 알아봅니다.
ms.date: 03/30/2017
ms.assetid: 955c057f-aea8-4ba8-aa6d-e3dfa18ba8d5
ms.openlocfilehash: b8f89dfda7edbde14dbb5945f10f2284ac43c3d8
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84287092"
---
# <a name="connection-pooling"></a><span data-ttu-id="726cb-103">연결 풀링</span><span class="sxs-lookup"><span data-stu-id="726cb-103">Connection Pooling</span></span>
<span data-ttu-id="726cb-104">데이터 소스에 연결하는 작업은 시간이 많이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="726cb-104">Connecting to a data source can be time consuming.</span></span> <span data-ttu-id="726cb-105">연결을 여는 비용을 최소화 하기 위해 ADO.NET에서는 연결 *풀링*이라는 최적화 기법을 사용 하 여 연결을 반복적으로 열고 닫는 데 드는 비용을 최소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="726cb-105">To minimize the cost of opening connections, ADO.NET uses an optimization technique called *connection pooling*, which minimizes the cost of repeatedly opening and closing connections.</span></span> <span data-ttu-id="726cb-106">연결 풀링은 .NET Framework 데이터 공급자마다 각각 다른 방식으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="726cb-106">Connection pooling is handled differently for the .NET Framework data providers.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="726cb-107">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="726cb-107">In This Section</span></span>  
 [<span data-ttu-id="726cb-108">SQL Server 연결 풀링(ADO.NET)</span><span class="sxs-lookup"><span data-stu-id="726cb-108">SQL Server Connection Pooling (ADO.NET)</span></span>](sql-server-connection-pooling.md)  
 <span data-ttu-id="726cb-109">연결 풀링의 개요를 제공 하 고 SQL Server 연결 풀링이 작동 하는 방식을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="726cb-109">Provides an overview of connection pooling and describes how connection pooling works in SQL Server.</span></span>  
  
 [<span data-ttu-id="726cb-110">OLE DB, ODBC 및 Oracle 연결 풀링</span><span class="sxs-lookup"><span data-stu-id="726cb-110">OLE DB, ODBC, and Oracle Connection Pooling</span></span>](ole-db-odbc-and-oracle-connection-pooling.md)  
 <span data-ttu-id="726cb-111">.NET Framework Data Provider for OLE DB, .NET Framework Data Provider for ODBC 및 .NET Framework Data Provider for Oracle의 연결 풀링에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="726cb-111">Describes connection pooling for the .NET Framework Data Provider for OLE DB, the .NET Framework Data Provider for ODBC, and the .NET Framework Data Provider for Oracle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="726cb-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="726cb-112">See also</span></span>

- [<span data-ttu-id="726cb-113">ADO.NET에서 데이터 검색 및 수정</span><span class="sxs-lookup"><span data-stu-id="726cb-113">Retrieving and Modifying Data in ADO.NET</span></span>](retrieving-and-modifying-data.md)
- [<span data-ttu-id="726cb-114">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="726cb-114">ADO.NET Overview</span></span>](ado-net-overview.md)
