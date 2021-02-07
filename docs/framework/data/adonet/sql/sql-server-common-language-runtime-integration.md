---
description: SQL Server 공용 언어 런타임 통합에 대해 자세히 알아보세요.
title: SQL Server 공용 언어 런타임 통합
ms.date: 03/30/2017
ms.assetid: c7a324c4-160d-44c2-b593-641af06eca61
ms.openlocfilehash: 096bba0d183526ec8e5d272c5ea6a77ad0778e5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99767403"
---
# <a name="sql-server-common-language-runtime-integration"></a><span data-ttu-id="062e1-103">SQL Server 공용 언어 런타임 통합</span><span class="sxs-lookup"><span data-stu-id="062e1-103">SQL Server Common Language Runtime Integration</span></span>

<span data-ttu-id="062e1-104">SQL Server 2005에는 .NET Framework for Microsoft Windows의 CLR(공용 언어 런타임) 구성 요소가 통합되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-104">SQL Server 2005 introduced the integration of the common language runtime (CLR) component of the .NET Framework for Microsoft Windows.</span></span> <span data-ttu-id="062e1-105">따라서 Microsoft Visual Basic .NET 및 Microsoft Visual C#을 비롯하여 모든 .NET Framework 언어를 사용하여 저장 프로시저, 트리거, 사용자 정의 형식, 사용자 정의 함수, 사용자 정의 집계 및 스트리밍 테이블 반환 함수를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-105">This means that you can write stored procedures, triggers, user-defined types, user-defined functions, user-defined aggregates, and streaming table-valued functions, using any .NET Framework language, including Microsoft Visual Basic .NET and Microsoft Visual C#.</span></span> <span data-ttu-id="062e1-106"><xref:Microsoft.SqlServer.Server> 네임스페이스에는 관리 코드에서 Microsoft SQL Server 환경과 상호 작용할 수 있도록 하는 새로운 API(응용 프로그래밍 인터페이스) 집합이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-106">The <xref:Microsoft.SqlServer.Server> namespace contains a set of new application programming interfaces (APIs) so that managed code can interact with the Microsoft SQL Server environment.</span></span>  
  
 <span data-ttu-id="062e1-107">이 단원에서는 SQL Server CLR(공용 언어 런타임) 통합 및 ADO.NET에 대한 SQL Server in-process 고유의 확장과 관련된 기능 및 동작에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-107">This section describes features and behaviors that are specific to SQL Server common language runtime (CLR) integration and the SQL Server in-process specific extensions to ADO.NET.</span></span>  
  
 <span data-ttu-id="062e1-108">이 단원은 SQL Server CLR 통합으로 프로그래밍을 시작하는 데 필요한 정보만 제공하며 모든 정보를 포괄적으로 다루지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-108">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="062e1-109">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="062e1-109">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="062e1-110">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="062e1-110">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="062e1-111">CLR(공용 언어 런타임) 통합 프로그래밍 개요</span><span class="sxs-lookup"><span data-stu-id="062e1-111">Common Language Runtime (CLR) Integration Programming Concepts</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-clr-integration-programming-concepts)  
  
## <a name="in-this-section"></a><span data-ttu-id="062e1-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="062e1-112">In This Section</span></span>  

 [<span data-ttu-id="062e1-113">SQL Server CLR 통합 소개</span><span class="sxs-lookup"><span data-stu-id="062e1-113">Introduction to SQL Server CLR Integration</span></span>](introduction-to-sql-server-clr-integration.md)  
 <span data-ttu-id="062e1-114">SQL Server CLR 통합에 대해 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-114">Provides an introduction to SQL Server CLR integration.</span></span> <span data-ttu-id="062e1-115">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-115">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="062e1-116">CLR 사용자 정의 함수</span><span class="sxs-lookup"><span data-stu-id="062e1-116">CLR User-Defined Functions</span></span>](clr-user-defined-functions.md)  
 <span data-ttu-id="062e1-117">테이블 반환 함수, 스칼라 함수, 사용자 정의 집계 함수 등 여러 가지 종류의 CLR 함수를 구현하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-117">Describes how to implement and use the various types of CLR functions: table-valued, scalar, and user-defined aggregate functions.</span></span>  
  
 [<span data-ttu-id="062e1-118">CLR 사용자 정의 형식</span><span class="sxs-lookup"><span data-stu-id="062e1-118">CLR User-Defined Types</span></span>](clr-user-defined-types.md)  
 <span data-ttu-id="062e1-119">CLR 사용자 정의 형식을 구현하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-119">Describes how to implement and use CLR user-defined types.</span></span> <span data-ttu-id="062e1-120">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-120">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="062e1-121">CLR 저장 프로시저</span><span class="sxs-lookup"><span data-stu-id="062e1-121">CLR Stored Procedures</span></span>](clr-stored-procedures.md)  
 <span data-ttu-id="062e1-122">CLR 저장 프로시저를 구현하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-122">Describes how to implement and use CLR stored procedures.</span></span> <span data-ttu-id="062e1-123">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-123">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="062e1-124">CLR 트리거</span><span class="sxs-lookup"><span data-stu-id="062e1-124">CLR Triggers</span></span>](clr-triggers.md)  
 <span data-ttu-id="062e1-125">CLR 트리거를 구현하고 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-125">Describes how to implement and use CLR triggers.</span></span> <span data-ttu-id="062e1-126">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-126">Provides links to additional topics.</span></span>  
  
 [<span data-ttu-id="062e1-127">컨텍스트 연결</span><span class="sxs-lookup"><span data-stu-id="062e1-127">The Context Connection</span></span>](the-context-connection.md)  
 <span data-ttu-id="062e1-128">컨텍스트 연결에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-128">Describes the context connection.</span></span>  
  
 [<span data-ttu-id="062e1-129">ADO.NET의 SQL Server In-Process별 동작</span><span class="sxs-lookup"><span data-stu-id="062e1-129">SQL Server In-Process-Specific Behavior of ADO.NET</span></span>](sql-server-in-process-specific-behavior-of-adonet.md)  
 <span data-ttu-id="062e1-130">ADO.NET에 대한 SQL Server in-process 고유의 확장명 및 컨텍스트 연결에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-130">Describes the SQL Server in-process specific extensions to ADO.NET, and the context connection.</span></span> <span data-ttu-id="062e1-131">또한 추가 항목에 대한 링크도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="062e1-131">Provides links to additional topics.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062e1-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="062e1-132">See also</span></span>

- [<span data-ttu-id="062e1-133">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="062e1-133">SQL Server and ADO.NET</span></span>](index.md)
- [<span data-ttu-id="062e1-134">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="062e1-134">ADO.NET Overview</span></span>](../ado-net-overview.md)
