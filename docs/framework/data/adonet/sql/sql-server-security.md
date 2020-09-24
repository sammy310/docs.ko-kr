---
title: SQL Server 보안
ms.date: 03/30/2017
ms.assetid: 9053724d-a1fb-4f0f-b9dc-7f6dd893e8ff
ms.openlocfilehash: 5db14e681b5a9445c034be60993661a61a038e08
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177308"
---
# <a name="sql-server-security"></a><span data-ttu-id="055c7-102">SQL Server 보안</span><span class="sxs-lookup"><span data-stu-id="055c7-102">SQL Server Security</span></span>

<span data-ttu-id="055c7-103">SQL Server에는 보안 데이터베이스 애플리케이션을 만들 수 있도록 지원하는 많은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-103">SQL Server has many features that support creating secure database applications.</span></span>  
  
 <span data-ttu-id="055c7-104">데이터 절도나 손상같이 일반적으로 발생하는 보안 문제는 사용 중인 SQL Server 버전에 관계없이 항상 고려해야 할 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-104">Common security considerations, such as data theft or vandalism, apply regardless of the version of SQL Server you are using.</span></span> <span data-ttu-id="055c7-105">데이터 무결성도 보안 문제로 간주해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-105">Data integrity should also be considered as a security issue.</span></span> <span data-ttu-id="055c7-106">데이터가 보호되지 않는 경우 임시 데이터 조작이 허용되고 잘못된 값을 사용하여 데이터가 실수로 또는 악의적으로 수정되거나 완전히 삭제되면 데이터가 가치가 없게 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-106">If data is not protected, it is possible that it could become worthless if ad hoc data manipulation is permitted and the data is inadvertently or maliciously modified with incorrect values or deleted entirely.</span></span> <span data-ttu-id="055c7-107">또한 기밀 정보의 올바른 저장과 같이 반드시 준수해야 하는 법적 요구 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-107">In addition, there are often legal requirements that must be adhered to, such as the correct storage of confidential information.</span></span> <span data-ttu-id="055c7-108">일부 개인 정보 저장은 특정 관할지에 적용되는 법에 따라 전적으로 규정됩니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-108">Storing some kinds of personal data is proscribed entirely, depending on the laws that apply in a particular jurisdiction.</span></span>  
  
 <span data-ttu-id="055c7-109">Windows가 버전마다 다른 것처럼 SQL Server도 버전마다 보안 기능이 다르며 최신 버전이 이전 버전보다 향상된 보안 기능을 가지고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-109">Each version of SQL Server has different security features, as does each version of Windows, with later versions having enhanced functionality over earlier ones.</span></span> <span data-ttu-id="055c7-110">보안 기능만으로는 안전한 데이터베이스 애플리케이션을 보장할 수 없다는 것을 이해하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-110">It is important to understand that security features alone cannot guarantee a secure database application.</span></span> <span data-ttu-id="055c7-111">각 데이터베이스 애플리케이션은 요구 사항, 실행 환경, 배포 모델, 물리적 위치 및 사용자 집단에서 고유합니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-111">Each database application is unique in its requirements, execution environment, deployment model, physical location, and user population.</span></span> <span data-ttu-id="055c7-112">범위가 로컬인 일부 애플리케이션의 경우 최소한의 보안만 필요한 반면 다른 로컬 애플리케이션이나 인터넷을 통해 배포된 애플리케이션은 엄격한 보안 조치와 지속적인 모니터링 및 평가가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-112">Some applications that are local in scope may need only minimal security whereas other local applications or applications deployed over the Internet may require stringent security measures and ongoing monitoring and evaluation.</span></span>  
  
 <span data-ttu-id="055c7-113">SQL Server 데이터베이스 애플리케이션의 보안 요구 사항은 디자인 타임부터 고려해야 하며 뒤늦게 생각해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-113">The security requirements of a SQL Server database application should be considered at design time, not as an afterthought.</span></span> <span data-ttu-id="055c7-114">개발 주기 초기에 위협을 평가하면 취약성이 발견될 때마다 잠재적 피해를 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-114">Evaluating threats early in the development cycle gives you the opportunity to mitigate potential damage wherever a vulnerability is detected.</span></span>  
  
 <span data-ttu-id="055c7-115">애플리케이션의 초기 디자인이 건전하더라도 시스템이 발전함에 따라 새로운 위협이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-115">Even if the initial design of an application is sound, new threats may emerge as the system evolves.</span></span> <span data-ttu-id="055c7-116">데이터베이스에 대해 여러 방어선을 만들어 보안 위반으로 인한 피해를 최소화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-116">By creating multiple lines of defense around your database, you can minimize the damage inflicted by a security breach.</span></span> <span data-ttu-id="055c7-117">첫 번째 방어선은 절대적으로 필요한 권한 이상의 권한을 부여하지 않고 공격 노출 영역을 줄이는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-117">Your first line of defense is to reduce the attack surface area by never to granting more permissions than are absolutely necessary.</span></span>  
  
 <span data-ttu-id="055c7-118">이 단원의 항목에서는 개발자와 관련이 있는 SQL Server의 보안 기능에 대해 간략히 설명하며, 이러한 항목에 대해 자세히 다루고 있는 SQL Server 온라인 설명서와 기타 리소스의 관련 항목으로 연결되는 링크를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-118">The topics in this section briefly describe the security features in SQL Server that are relevant for developers, with links to relevant topics in SQL Server Books Online and other resources that provide more detailed coverage.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="055c7-119">섹션 내용</span><span class="sxs-lookup"><span data-stu-id="055c7-119">In This Section</span></span>  

 [<span data-ttu-id="055c7-120">SQL Server 보안 개요</span><span class="sxs-lookup"><span data-stu-id="055c7-120">Overview of SQL Server Security</span></span>](overview-of-sql-server-security.md)  
 <span data-ttu-id="055c7-121">SQL Server의 아키텍처와 보안 기능에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-121">Describes the architecture and security features of SQL Server.</span></span>  
  
 [<span data-ttu-id="055c7-122">SQL Server의 애플리케이션 보안 시나리오</span><span class="sxs-lookup"><span data-stu-id="055c7-122">Application Security Scenarios in SQL Server</span></span>](application-security-scenarios-in-sql-server.md)  
 <span data-ttu-id="055c7-123">ADO.NET 및 SQL Server 애플리케이션에 대한 다양한 애플리케이션 보안 시나리오를 설명하는 항목을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-123">Contains topics discussing various application security scenarios for ADO.NET and SQL Server applications.</span></span>  
  
 [<span data-ttu-id="055c7-124">SQL Server Express 보안</span><span class="sxs-lookup"><span data-stu-id="055c7-124">SQL Server Express Security</span></span>](sql-server-express-security.md)  
 <span data-ttu-id="055c7-125">SQL Server Express의 보안 고려 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-125">Describes security considerations for SQL Server Express.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="055c7-126">관련 섹션</span><span class="sxs-lookup"><span data-stu-id="055c7-126">Related Sections</span></span>  

[<span data-ttu-id="055c7-127">SQL Server 데이터베이스 엔진 및 Azure SQL Database 보안 센터</span><span class="sxs-lookup"><span data-stu-id="055c7-127">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](/sql/relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database)  
<span data-ttu-id="055c7-128">SQL Server 및 Azure SQL Database의 보안 고려 사항에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-128">Describes security considerations for SQL Server and Azure SQL Database.</span></span>

[<span data-ttu-id="055c7-129">SQL Server 설치에 대한 보안 고려 사항</span><span class="sxs-lookup"><span data-stu-id="055c7-129">Security Considerations for a SQL Server Installation</span></span>](/sql/sql-server/install/security-considerations-for-a-sql-server-installation)  
<span data-ttu-id="055c7-130">SQL Server를 설치하기 전에 고려해야 하는 보안 문제에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="055c7-130">Describes security concerns to consider before installing SQL Server.</span></span>

## <a name="see-also"></a><span data-ttu-id="055c7-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="055c7-131">See also</span></span>

- [<span data-ttu-id="055c7-132">ADO.NET 애플리케이션 보안</span><span class="sxs-lookup"><span data-stu-id="055c7-132">Securing ADO.NET Applications</span></span>](../securing-ado-net-applications.md)
- [<span data-ttu-id="055c7-133">SQL Server 및 ADO.NET</span><span class="sxs-lookup"><span data-stu-id="055c7-133">SQL Server and ADO.NET</span></span>](index.md)
