---
title: SQL Server CLR 통합 소개
description: SQL Server와의 CLR 통합은 관리 코드에서 저장 프로시저, 트리거, 사용자 정의 함수, 사용자 정의 형식 및 사용자 정의 집계를 지원 합니다.
ms.date: 03/30/2017
ms.assetid: 551d2290-ed80-49be-b377-44b32444da1c
ms.openlocfilehash: 969afd7dea4aadf88bbb69cbe85d9cd84b233e4f
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91194559"
---
# <a name="introduction-to-sql-server-clr-integration"></a><span data-ttu-id="98d41-103">SQL Server CLR 통합 소개</span><span class="sxs-lookup"><span data-stu-id="98d41-103">Introduction to SQL Server CLR Integration</span></span>

<span data-ttu-id="98d41-104">CLR(공용 언어 런타임)은 Microsoft .NET Framework의 핵심으로, 모든 .NET Framework 코드의 실행 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-104">The common language runtime (CLR) is the heart of the Microsoft .NET Framework and provides the execution environment for all .NET Framework code.</span></span> <span data-ttu-id="98d41-105">CLR 내에서 실행되는 코드를 관리 코드라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-105">Code that runs within the CLR is referred to as managed code.</span></span> <span data-ttu-id="98d41-106">CLR은 JIT(Just-In-Time) 컴파일, 메모리 할당 및 관리, 형식 안전성 적용, 예외 처리, 스레드 관리, 보안을 비롯하여 프로그램 실행에 필요한 다양한 기능과 서비스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-106">The CLR provides various functions and services required for program execution, including just-in-time (JIT) compilation, allocating and managing memory, enforcing type safety, exception handling, thread management, and security.</span></span>  
  
 <span data-ttu-id="98d41-107">Microsoft SQL Server에 호스팅된 CLR(CLR 통합이라고 함)을 사용하면 관리 코드로 저장 프로시저, 트리거, 사용자 정의 함수, 사용자 정의 형식 및 사용자 정의 집계를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-107">With the CLR hosted in Microsoft SQL Server (called CLR integration), you can author stored procedures, triggers, user-defined functions, user-defined types, and user-defined aggregates in managed code.</span></span> <span data-ttu-id="98d41-108">관리 코드는 실행 전에 네이티브 코드로 컴파일되므로 일부 시나리오에서 성능이 훨씬 향상될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-108">Because managed code compiles to native code prior to execution, you can achieve significant performance increases in some scenarios.</span></span>  
  
 <span data-ttu-id="98d41-109">관리 코드에서는 CAS(코드 액세스 보안), 코드 링크 및 애플리케이션 도메인을 사용하여 어셈블리에서 특정 작업을 수행하지 못하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-109">Managed code uses Code Access Security (CAS), code links, and application domains to prevent assemblies from performing certain operations.</span></span> <span data-ttu-id="98d41-110">SQL Server에서는 CAS를 사용하여 관리 코드의 보안을 손쉽게 유지하고 운영 체제나 데이터베이스 서버의 성능이 떨어지지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-110">SQL Server uses CAS to help secure the managed code and prevent compromise of the operating system or database server.</span></span>  
  
 <span data-ttu-id="98d41-111">이 단원은 SQL Server CLR 통합으로 프로그래밍을 시작하는 데 필요한 정보만 제공하며 모든 정보를 포괄적으로 다루지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-111">This section is meant to provide only enough information to get started programming with SQL Server CLR integration, and is not meant to be comprehensive.</span></span> <span data-ttu-id="98d41-112">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98d41-112">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="98d41-113">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="98d41-113">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="98d41-114">CLR(공용 언어 런타임) 통합 개요</span><span class="sxs-lookup"><span data-stu-id="98d41-114">Common Language Runtime (CLR) Integration Overview</span></span>](/sql/relational-databases/clr-integration/common-language-runtime-integration-overview)  
  
## <a name="enabling-clr-integration"></a><span data-ttu-id="98d41-115">CLR 통합 사용</span><span class="sxs-lookup"><span data-stu-id="98d41-115">Enabling CLR Integration</span></span>  

 <span data-ttu-id="98d41-116">Microsoft SQL Server에서 CLR(공용 언어 런타임) 통합 기능은 기본적으로 사용하지 않도록 설정되어 있으며 CLR 통합을 사용하여 구현되는 개체를 사용하려면 이를 활성화해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-116">The common language runtime (CLR) integration feature is off by default in Microsoft SQL Server, and must be enabled in order to use objects that are implemented using CLR integration.</span></span> <span data-ttu-id="98d41-117">Transact-SQL을 사용하여 CLR 통합을 활성화하려면 다음과 같이 `clr enabled` 저장 프로시저의 `sp_configure` 옵션을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-117">To enable CLR integration using Transact-SQL, use the `clr enabled` option of the `sp_configure` stored procedure as shown:</span></span>  
  
```sql  
sp_configure 'clr enabled', 1  
GO  
RECONFIGURE  
GO  
```  
  
 <span data-ttu-id="98d41-118">`clr enabled` 옵션을 0으로 설정하면 CLR 통합이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-118">You can disable CLR integration by setting the `clr enabled` option to 0.</span></span> <span data-ttu-id="98d41-119">CLR 통합을 비활성화하면 SQL Server에서는 모든 CLR 루틴의 실행을 중지하고 모든 애플리케이션 도메인을 언로드합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-119">When you disable CLR integration, SQL Server stops executing all CLR routines and unloads all application domains.</span></span>  
  
 <span data-ttu-id="98d41-120">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98d41-120">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="98d41-121">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="98d41-121">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="98d41-122">CLR 통합 사용</span><span class="sxs-lookup"><span data-stu-id="98d41-122">Enabling CLR Integration</span></span>](/sql/relational-databases/clr-integration/clr-integration-enabling)  
  
## <a name="deploying-a-clr-assembly"></a><span data-ttu-id="98d41-123">CLR 어셈블리 배포</span><span class="sxs-lookup"><span data-stu-id="98d41-123">Deploying a CLR Assembly</span></span>  

 <span data-ttu-id="98d41-124">테스트 서버에서 CLR 메서드를 테스트하고 확인하고 나면 개발 스크립트를 사용하여 프로덕션 서버에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-124">Once the CLR methods have been tested and verified on the test server, they can be distributed to production servers using a deployment script.</span></span> <span data-ttu-id="98d41-125">배포 스크립트는 수동으로 생성하거나 SQL Server Management Studio를 사용하여 생성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-125">The deployment script can be generated manually, or by using SQL Server Management Studio.</span></span> <span data-ttu-id="98d41-126">자세한 내용은 사용 중인 SQL Server 버전에 대 한 SQL Server 설명서의 버전을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="98d41-126">For more detailed information, see the version of SQL Server documentation for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="98d41-127">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="98d41-127">**SQL Server documentation**</span></span>  
  
1. [<span data-ttu-id="98d41-128">CLR 데이터베이스 개체 배포</span><span class="sxs-lookup"><span data-stu-id="98d41-128">Deploying CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/deploying-clr-database-objects)  
  
## <a name="clr-integration-security"></a><span data-ttu-id="98d41-129">CLR 통합 보안</span><span class="sxs-lookup"><span data-stu-id="98d41-129">CLR Integration Security</span></span>  

 <span data-ttu-id="98d41-130">Microsoft .NET Framework CLR(공용 언어 런타임)과 통합된 Microsoft SQL Server 보안 모델은 SQL Server 내에서 실행되는 다양한 유형의 CLR 및 비 CLR 개체 간에 액세스를 관리 및 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-130">The security model of the Microsoft SQL Server integration with the Microsoft .NET Framework common language runtime (CLR) manages and secures access between different types of CLR and non-CLR objects running within SQL Server.</span></span> <span data-ttu-id="98d41-131">이러한 개체는 서버에서 실행되는 Transact-SQL 문이나 다른 CLR 개체에서 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-131">These objects may be called by a Transact-SQL statement or another CLR object running in the server.</span></span>  
  
 <span data-ttu-id="98d41-132">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98d41-132">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="98d41-133">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="98d41-133">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="98d41-134">CLR 통합 보안</span><span class="sxs-lookup"><span data-stu-id="98d41-134">CLR Integration Security</span></span>](/sql/relational-databases/clr-integration/security/clr-integration-security)  
  
## <a name="debugging-a-clr-assembly"></a><span data-ttu-id="98d41-135">CLR 어셈블리 디버깅</span><span class="sxs-lookup"><span data-stu-id="98d41-135">Debugging a CLR Assembly</span></span>  

 <span data-ttu-id="98d41-136">Microsoft SQL Server는 데이터베이스에서의 Transact-SQL 및 CLR(공용 언어 런타임) 개체 디버깅을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-136">Microsoft SQL Server provides support for debugging Transact-SQL and common language runtime (CLR) objects in the database.</span></span> <span data-ttu-id="98d41-137">디버깅은 여러 언어에서 수행되므로 사용자는 Transact-SQL에서 CLR 개체로 또는 CLR 개체에서 Transact-SQL로 매끄럽게 단계를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98d41-137">Debugging works across languages: users can step seamlessly into CLR objects from Transact-SQL, and vice versa.</span></span>  
  
 <span data-ttu-id="98d41-138">자세한 내용을 보려면 현재 사용하고 있는 SQL Server 버전에 해당하는 SQL Server 온라인 설명서 버전을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="98d41-138">For more detailed information, see the version of SQL Server Books Online for the version of SQL Server you are using.</span></span>  
  
 <span data-ttu-id="98d41-139">**SQL Server 설명서**</span><span class="sxs-lookup"><span data-stu-id="98d41-139">**SQL Server documentation**</span></span>  
  
- [<span data-ttu-id="98d41-140">CLR 데이터베이스 개체 디버깅</span><span class="sxs-lookup"><span data-stu-id="98d41-140">Debugging CLR Database Objects</span></span>](/sql/relational-databases/clr-integration/debugging-clr-database-objects)  
  
## <a name="see-also"></a><span data-ttu-id="98d41-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="98d41-141">See also</span></span>

- [<span data-ttu-id="98d41-142">코드 액세스 보안 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="98d41-142">Code Access Security and ADO.NET</span></span>](../code-access-security.md)
- [<span data-ttu-id="98d41-143">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="98d41-143">ADO.NET Overview</span></span>](../ado-net-overview.md)
