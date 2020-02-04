---
title: 애플리케이션 보안
ms.date: 03/30/2017
ms.assetid: 005a1d43-6ee5-471e-ad98-1d30a44d49d5
ms.openlocfilehash: c1bdf4329665e4d29a47c26fb7dba8eb41c1cc3a
ms.sourcegitcommit: 19014f9c081ca2ff19652ca12503828db8239d48
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/04/2020
ms.locfileid: "76980030"
---
# <a name="securing-adonet-applications"></a><span data-ttu-id="97ad6-102">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="97ad6-102">Securing ADO.NET Applications</span></span>
<span data-ttu-id="97ad6-103">보안 ADO.NET 애플리케이션을 작성하려면 사용자 입력의 유효성을 확인하지 않는 것과 같은 일반적인 코딩 문제를 피하는 것 외에도 여러 부분을 고려해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-103">Writing a secure ADO.NET application involves more than avoiding common coding pitfalls such as not validating user input.</span></span> <span data-ttu-id="97ad6-104">데이터에 액세스하는 애플리케이션에는 공격자가 중요한 데이터를 검색, 조작 또는 제거하는 데 악용할 수 있는 여러 잠재적인 오류 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-104">An application that accesses data has many potential points of failure that an attacker can exploit to retrieve, manipulate, or destroy sensitive data.</span></span> <span data-ttu-id="97ad6-105">따라서 애플리케이션 디자인 단계의 위협 모델링 과정에서부터 최종 배포와 진행 중인 유지 관리에 이르기까지 보안의 모든 측면을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-105">It is therefore important to understand all aspects of security, from the process of threat modeling during the design phase of your application, to its eventual deployment and ongoing maintenance.</span></span>  
  
 <span data-ttu-id="97ad6-106">.NET Framework에서는 데이터베이스 애플리케이션을 보호하고 관리할 수 있는 여러 유용한 클래스, 서비스 및 도구를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-106">The .NET Framework provides many useful classes, services, and tools for securing and administering database applications.</span></span> <span data-ttu-id="97ad6-107">CLR(공용 언어 런타임)은 관리 코드의 권한을 더 제한하는 CAS(코드 액세스 보안)를 사용하여 실행될 코드에 형식 안전 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-107">The common language runtime (CLR) provides a type-safe environment for code to run in, with code access security (CAS) to restrict further the permissions of managed code.</span></span> <span data-ttu-id="97ad6-108">다음 보안 데이터 액세스 코딩 연습에서는 잠재적인 공격자에 의해 발생할 수 있는 손상을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-108">Following secure data access coding practices limits the damage that can be inflicted by a potential attacker.</span></span>  
  
 <span data-ttu-id="97ad6-109">보안 코드를 작성하면 데이터베이스와 같은 관리되지 않는 리소스 작업을 할 때 자초한 보안 허점을 막지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-109">Writing secure code does not guard against self-inflicted security holes when working with unmanaged resources such as databases.</span></span> <span data-ttu-id="97ad6-110">SQL Server와 같은 대부분의 서버 데이터베이스는 제대로 구현되는 경우 보안을 강화하는 자체 보안 시스템을 가집니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-110">Most server databases, such as SQL Server, have their own security systems, which enhance security when implemented correctly.</span></span> <span data-ttu-id="97ad6-111">그러나 제대로 구성되지 않은 경우 강력한 보안 시스템으로 구성된 데이터 소스라 할지라도 공격에 취약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-111">However, even a data source with a robust security system can be victimized in an attack if it is not configured appropriately.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="97ad6-112">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="97ad6-112">In This Section</span></span>  
 [<span data-ttu-id="97ad6-113">보안 개요</span><span class="sxs-lookup"><span data-stu-id="97ad6-113">Security Overview</span></span>](security-overview.md)  
 <span data-ttu-id="97ad6-114">보안 ADO.NET 애플리케이션 디자인에 대한 권장 사항을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-114">Provides recommendations for designing secure ADO.NET applications.</span></span>  
  
 [<span data-ttu-id="97ad6-115">보안 데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="97ad6-115">Secure Data Access</span></span>](secure-data-access.md)  
 <span data-ttu-id="97ad6-116">안전한 데이터 소스의 데이터로 작업하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-116">Describes how to work with data from a secured data source.</span></span>  
  
 [<span data-ttu-id="97ad6-117">안전한 클라이언트 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="97ad6-117">Secure Client Applications</span></span>](secure-client-applications.md)  
 <span data-ttu-id="97ad6-118">클라이언트 애플리케이션 보안을 위한 고려 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-118">Describes security considerations for client applications.</span></span>  
  
 [<span data-ttu-id="97ad6-119">코드 액세스 보안 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97ad6-119">Code Access Security and ADO.NET</span></span>](code-access-security.md)  
 <span data-ttu-id="97ad6-120">CAS를 사용하여 ADO.NET 코드를 보호하는 방법 및</span><span class="sxs-lookup"><span data-stu-id="97ad6-120">Describes how CAS can help protect ADO.NET code.</span></span> <span data-ttu-id="97ad6-121">부분 신뢰를 사용하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-121">Also discusses how to work with partial trust.</span></span>  
  
 [<span data-ttu-id="97ad6-122">개인 정보 및 데이터 보안</span><span class="sxs-lookup"><span data-stu-id="97ad6-122">Privacy and Data Security</span></span>](privacy-and-data-security.md)  
 <span data-ttu-id="97ad6-123">ADO.NET 애플리케이션의 암호화 옵션에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-123">Describes encryption options for ADO.NET applications.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="97ad6-124">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="97ad6-124">Related Sections</span></span>  
 [<span data-ttu-id="97ad6-125">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="97ad6-125">SQL Server Security</span></span>](./sql/sql-server-security.md)  
 <span data-ttu-id="97ad6-126">개발자 관점에서 SQL Server 보안 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-126">Describes SQL Server security features from a developer's perspective.</span></span>  
  
 [<span data-ttu-id="97ad6-127">보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="97ad6-127">Security Considerations</span></span>](./ef/security-considerations.md)  
 <span data-ttu-id="97ad6-128">Entity Framework 애플리케이션의 보안에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-128">Describes security for Entity Framework applications.</span></span>  
  
 [<span data-ttu-id="97ad6-129">Security</span><span class="sxs-lookup"><span data-stu-id="97ad6-129">Security</span></span>](../../../standard/security/index.md)  
 <span data-ttu-id="97ad6-130">.NET에서 보안의 여러 가지 측면에 대해 설명하는 항목의 링크가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-130">Contains links to topics describing all aspects of security in .NET.</span></span>  
  
 <span data-ttu-id="97ad6-131">[보안 도구](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="97ad6-131">[Security Tools](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2008/7w3fd0wb(v=vs.90))</span></span>  
 <span data-ttu-id="97ad6-132">보안 정책을 보호하고 관리하는 .NET Framework 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-132">.NET Framework tools for securing and administering security policy.</span></span>  
  
 <span data-ttu-id="97ad6-133">[보안 애플리케이션을 만들기 위한 리소스](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="97ad6-133">[Resources for Creating Secure Applications](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/ms165101(v=vs.100))</span></span>  
 <span data-ttu-id="97ad6-134">보안 애플리케이션 만들기에 대한 항목의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-134">Provides links to topics for creating secure applications.</span></span>  
  
 [<span data-ttu-id="97ad6-135">보안 관련 참조 목록</span><span class="sxs-lookup"><span data-stu-id="97ad6-135">Security Bibliography</span></span>](/visualstudio/ide/securing-applications)  
 <span data-ttu-id="97ad6-136">온라인 및 인쇄 작업에서 사용 가능한 외부 리소스의 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="97ad6-136">Provides links to external resources available online and in print.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="97ad6-137">참조</span><span class="sxs-lookup"><span data-stu-id="97ad6-137">See also</span></span>

- [<span data-ttu-id="97ad6-138">ADO.NET</span><span class="sxs-lookup"><span data-stu-id="97ad6-138">ADO.NET</span></span>](index.md)
- [<span data-ttu-id="97ad6-139">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="97ad6-139">ADO.NET Overview</span></span>](ado-net-overview.md)
