---
title: SQL Server 보안 개요
description: 알려진 위협 요소를 파악 하 고 향후 위협을 예상 하기 위해 SQL Server 보안 아키텍처에 대해 알아봅니다.
ms.date: 03/30/2017
ms.assetid: ae66dd75-5c16-4cc0-9e12-774dd26d3fb9
ms.openlocfilehash: ba396774e760a550246d0f0507984d3f7212204b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91172660"
---
# <a name="overview-of-sql-server-security"></a><span data-ttu-id="6464f-103">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="6464f-103">Overview of SQL Server Security</span></span>

<span data-ttu-id="6464f-104">보안 위협에 대처하는 가장 좋은 방법은 여러 보안 계층으로 구성된 심층적인 방어 전략을 구현하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-104">A defense-in-depth strategy, with overlapping layers of security, is the best way to counter security threats.</span></span> <span data-ttu-id="6464f-105">SQL Server는 데이터베이스 관리자와 개발자가 안전한 데이터베이스 애플리케이션과 위협 대처 방안을 만들 수 있도록 디자인된 보안 아키텍처를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-105">SQL Server provides a security architecture that is designed to allow database administrators and developers to create secure database applications and counter threats.</span></span> <span data-ttu-id="6464f-106">SQL Server의 각 버전은 새로운 기능이 추가되어 이전 버전의 SQL Server에 비해 향상되었지만</span><span class="sxs-lookup"><span data-stu-id="6464f-106">Each version of SQL Server has improved on previous versions of SQL Server with the introduction of new features and functionality.</span></span> <span data-ttu-id="6464f-107">사용자 환경에 맞게 직접 보안을 구성하고 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-107">However, security does not ship in the box.</span></span> <span data-ttu-id="6464f-108">보안 요구 사항은 애플리케이션마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-108">Each application is unique in its security requirements.</span></span> <span data-ttu-id="6464f-109">따라서 개발자는 알려진 위협에 대응하는 데 가장 적합한 기능의 조합이 무엇인지 파악하고 향후 발생할 수 있는 위협에 대비할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-109">Developers need to understand which combination of features and functionality are most appropriate to counter known threats, and to anticipate threats that may arise in the future.</span></span>  
  
 <span data-ttu-id="6464f-110">SQL Server 인스턴스에는 서버를 비롯한 여러 엔터티의 계층 구조적 컬렉션이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-110">A SQL Server instance contains a hierarchical collection of entities, starting with the server.</span></span> <span data-ttu-id="6464f-111">각 서버에는 여러 개의 데이터베이스가 있고, 각 데이터베이스에는 보안 개체의 컬렉션이 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-111">Each server contains multiple databases, and each database contains a collection of securable objects.</span></span> <span data-ttu-id="6464f-112">SQL Server 모든 보안 개체에는 SQL Server에 대 한 액세스 권한을 부여 받은 개인, 그룹 또는 프로세스의 *보안 주체*에 게 부여할 수 있는 연결 된 *사용 권한이* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-112">Every SQL Server securable has associated *permissions* that can be granted to a *principal*, which is an individual, group or process granted access to SQL Server.</span></span> <span data-ttu-id="6464f-113">SQL Server 보안 프레임 워크는 *인증* 및 *권한 부여*를 통해 보안 개체에 대 한 액세스를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-113">The SQL Server security framework manages access to securable entities through *authentication* and *authorization*.</span></span>  
  
- <span data-ttu-id="6464f-114">인증은 보안 주체가 서버에서 확인하는 자격 증명을 제출하여 액세스를 요청함으로써 SQL Server에 로그온하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-114">Authentication is the process of logging on to SQL Server by which a principal requests access by submitting credentials that the server evaluates.</span></span> <span data-ttu-id="6464f-115">인증을 통해 사용자 또는 프로세스의 ID가 인증됩니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-115">Authentication establishes the identity of the user or process being authenticated.</span></span>  
  
- <span data-ttu-id="6464f-116">권한 부여는 보안 주체가 액세스할 수 있는 보호 가능한 리소스와, 해당 리소스에 대해 허용되는 작업을 결정하는 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-116">Authorization is the process of determining which securable resources a principal can access, and which operations are allowed for those resources.</span></span>  
  
 <span data-ttu-id="6464f-117">이 단원의 항목에서는 SQL Server 보안 기본 사항에 대해 설명하며 보다 자세한 설명을 볼 수 있는 SQL Server 온라인 설명서의 해당 항목에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-117">The topics in this section cover SQL Server security fundamentals, providing links to the complete documentation in the relevant version of SQL Server Books Online.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="6464f-118">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="6464f-118">In This Section</span></span>  

 [<span data-ttu-id="6464f-119">SQL Server에서 인증</span><span class="sxs-lookup"><span data-stu-id="6464f-119">Authentication in SQL Server</span></span>](authentication-in-sql-server.md)  
 <span data-ttu-id="6464f-120">SQL Server의 로그인 및 인증에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-120">Describes logins and authentication in SQL Server and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="6464f-121">SQL Server의 서버 및 데이터베이스 역할</span><span class="sxs-lookup"><span data-stu-id="6464f-121">Server and Database Roles in SQL Server</span></span>](server-and-database-roles-in-sql-server.md)  
 <span data-ttu-id="6464f-122">고정 서버 역할과 데이터베이스 역할, 사용자 지정 데이터베이스 역할 및 기본 제공 계정에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-122">Describes fixed server and database roles, custom database roles, and built-in accounts and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="6464f-123">SQL Server에서 소유권 및 사용자와 스키마 분리</span><span class="sxs-lookup"><span data-stu-id="6464f-123">Ownership and User-Schema Separation in SQL Server</span></span>](ownership-and-user-schema-separation-in-sql-server.md)  
 <span data-ttu-id="6464f-124">개체 소유권과 사용자 스키마 분리에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-124">Describes object ownership and  user-schema separation and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="6464f-125">SQL Server에서 권한 부여 및 권한</span><span class="sxs-lookup"><span data-stu-id="6464f-125">Authorization and Permissions in SQL Server</span></span>](authorization-and-permissions-in-sql-server.md)  
 <span data-ttu-id="6464f-126">최소 권한 원칙을 사용하여 권한을 부여하는 방법에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-126">Describes granting permissions using the principle of least privilege and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="6464f-127">SQL Server에서 데이터 암호화</span><span class="sxs-lookup"><span data-stu-id="6464f-127">Data Encryption in SQL Server</span></span>](data-encryption-in-sql-server.md)  
 <span data-ttu-id="6464f-128">SQL Server의 데이터 암호화 옵션에 대해 설명하고 추가 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-128">Describes data encryption options in SQL Server and provides links to additional resources.</span></span>  
  
 [<span data-ttu-id="6464f-129">SQL Server의 CLR 통합 보안</span><span class="sxs-lookup"><span data-stu-id="6464f-129">CLR Integration Security in SQL Server</span></span>](clr-integration-security-in-sql-server.md)  
 <span data-ttu-id="6464f-130">CLR 통합 보안 리소스에 대한 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="6464f-130">Provides links to CLR integration security resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6464f-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6464f-131">See also</span></span>

- [<span data-ttu-id="6464f-132">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="6464f-132">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="6464f-133">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="6464f-133">SQL Server Security</span></span>](sql-server-security.md)
- [<span data-ttu-id="6464f-134">SQL Server의 애플리케이션 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="6464f-134">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)
- [<span data-ttu-id="6464f-135">ADO.NET 개요</span><span class="sxs-lookup"><span data-stu-id="6464f-135">ADO.NET Overview</span></span>](../ado-net-overview.md)
