---
title: SQL Server 공용 언어 런타임 통합
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 12ae15d72644e314aa694f8d169bc8f45fa284a2
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77452346"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="d4ae8-102">SQL Server 공용 언어 런타임 통합</span><span class="sxs-lookup"><span data-stu-id="d4ae8-102">SQL Server Common Language Runtime Integration</span></span>
<span data-ttu-id="d4ae8-103">SQL Server 2005에는 .NET Framework for Microsoft Windows의 CLR(공용 언어 런타임) 구성 요소가 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-103">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="d4ae8-104">따라서 Microsoft Visual Basic .NET 및 Microsoft Visual C#을 비롯하여 모든 .NET Framework 언어를 사용하여 저장 프로시저, 트리거, 사용자 정의 형식, 사용자 정의 함수, 사용자 정의 집계 및 스트리밍 테이블 반환 함수를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-104">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="d4ae8-105"><xref:Microsoft.SqlServer.Server> 네임스페이스에는 관리 코드에서 Microsoft SQL Server 환경과 상호 작용할 수 있도록 하는 새로운 API(응용 프로그래밍 인터페이스) 집합이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-105">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="d4ae8-106">이 단원에서는 SQL Server CLR(공용 언어 런타임) 통합 및 ADO.NET에 대한 SQL Server in-process 고유의 확장과 관련된 기능 및 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-106">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="d4ae8-107">이 단원은 SQL Server CLR 통합으로 프로그래밍을 시작하는 데 필요한 정보만 제공하며 모든 정보를 포괄적으로 다루지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-107">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="d4ae8-108">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-108">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="d4ae8-109">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="d4ae8-109">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="d4ae8-110">CLR(공용 언어 런타임) 통합 프로그래밍 개요</span><span class="sxs-lookup"><span data-stu-id="d4ae8-110">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a><span data-ttu-id="d4ae8-111">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="d4ae8-111">In This Section</span></span>  
 [<span data-ttu-id="d4ae8-112">SQL Server CLR 통합 소개</span><span class="sxs-lookup"><span data-stu-id="d4ae8-112">Introduction to SQL Server CLR Integration</span></span>](introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="d4ae8-113">SQL Server CLR 통합에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-113">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="d4ae8-114">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-114">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="d4ae8-115">CLR 사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="d4ae8-115">CLR User-Defined Functions</span></span>](clr-user-defined-functions.md)  
 <span data-ttu-id="d4ae8-116">테이블 반환 함수, 스칼라 함수, 사용자 정의 집계 함수 등 여러 가지 종류의 CLR 함수를 구현하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-116">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="d4ae8-117">CLR 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="d4ae8-117">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
 <span data-ttu-id="d4ae8-118">CLR 사용자 정의 형식을 구현하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-118">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="d4ae8-119">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-119">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="d4ae8-120">CLR 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="d4ae8-120">CLR Stored Procedures</span></span>](clr-stored-procedures.md)  
 <span data-ttu-id="d4ae8-121">CLR 저장 프로시저를 구현하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-121">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="d4ae8-122">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-122">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="d4ae8-123">CLR 트리거</span><span class="sxs-lookup"><span data-stu-id="d4ae8-123">CLR Triggers</span></span>](clr-triggers.md)  
 <span data-ttu-id="d4ae8-124">CLR 트리거를 구현하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-124">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="d4ae8-125">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-125">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="d4ae8-126">컨텍스트 연결</span><span class="sxs-lookup"><span data-stu-id="d4ae8-126">The Context Connection</span></span>](the-context-connection.md)  
 <span data-ttu-id="d4ae8-127">컨텍스트 연결에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-127">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="d4ae8-128">ADO.NET의 SQL Server In-Process별 동작</span><span class="sxs-lookup"><span data-stu-id="d4ae8-128">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="d4ae8-129">ADO.NET에 대한 SQL Server in-process 고유의 확장명 및 컨텍스트 연결에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-129">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="d4ae8-130">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4ae8-130">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d4ae8-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4ae8-131">See also</span></span>

- [<span data-ttu-id="d4ae8-132">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="d4ae8-132">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="d4ae8-133">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="d4ae8-133">ADO.NET Overview</span></span>](../ado-net-overview.md)
