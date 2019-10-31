---
title: 관계형 데이터베이스를 azure로 마이그레이션
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존 .NET 응용 프로그램 현대화 | 관계형 데이터베이스를 azure로 마이그레이션
ms.date: 04/28/2018
ms.openlocfilehash: efd1548c3f74fc27450f4949d71a1c4d61907ba5
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73093622"
---
# <a name="migrate-your-relational-databases-to-azure"></a><span data-ttu-id="0228a-103">관계형 데이터베이스를 azure로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0228a-103">Migrate your relational databases to azure</span></span>

<span data-ttu-id="0228a-104">비전: Azure는 가장 포괄적인 데이터베이스 마이그레이션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-104">Vision: Azure offers the most comprehensive database migration.</span></span>

<span data-ttu-id="0228a-105">Azure에서 데이터베이스 서버를 IaaS Vm으로 직접 마이그레이션하거나 (순수한 리프트 앤 시프트), 추가 혜택을 위해 Azure SQL Database로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-105">In Azure, you can migrate your database servers directly to IaaS VMs (pure lift and shift), or you can migrate to Azure SQL Database, for additional benefits.</span></span> <span data-ttu-id="0228a-106">Azure SQL Database는 관리 되는 인스턴스와 전체 DBaaS (Database as a service) 옵션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-106">Azure SQL Database offers managed instance and full database-as-a-service (DBaaS) options.</span></span> <span data-ttu-id="0228a-107">그림 3-1에서는 Azure에서 사용할 수 있는 여러 관계형 데이터베이스 마이그레이션 경로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-107">Figure 3-1 shows the multiple relational database migration paths available in Azure.</span></span>

![Azure의 데이터베이스 마이그레이션 경로](./media/image3-1.png)

<span data-ttu-id="0228a-109">**그림 3-1.**</span><span class="sxs-lookup"><span data-stu-id="0228a-109">**Figure 3-1.**</span></span> <span data-ttu-id="0228a-110">Azure의 데이터베이스 마이그레이션 경로</span><span class="sxs-lookup"><span data-stu-id="0228a-110">Database migration paths in Azure</span></span>

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a><span data-ttu-id="0228a-111">Azure SQL Database Managed Instance로 마이그레이션해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="0228a-111">When to migrate to Azure SQL Database Managed Instance</span></span>

<span data-ttu-id="0228a-112">대부분의 경우 Azure SQL Database Managed Instance는 데이터를 Azure로 마이그레이션할 때 고려해 야 하는 가장 좋은 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-112">In most cases, Azure SQL Database Managed Instance will be your best option to consider when you migrate your data to Azure.</span></span> <span data-ttu-id="0228a-113">SQL Server 데이터베이스를 마이그레이션하는 경우 응용 프로그램을 다시 설계 하거나 데이터 또는 데이터 액세스 코드를 변경 하지 않아도 되도록 100%의 보장을 요구 하는 경우 Azure SQL Database의 Managed Instance 기능을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-113">If you are migrating SQL Server databases and need nearly 100% assurance that you won't need to rearchitect your application or make changes to your data or data access code, choose the Managed Instance feature of Azure SQL Database.</span></span>

<span data-ttu-id="0228a-114">Azure SQL Database Managed Instance 인스턴스 수준 기능 SQL Server에 대 한 추가 요구 사항이 있거나 표준 Azure SQL Database (단일 데이터베이스 모델)에서 제공 되는 기능 이외에 격리 요구 사항이 있는 경우에 가장 적합 한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-114">Azure SQL Database Managed Instance is the best option if you have additional requirements for SQL Server instance-level functionality, or isolation requirements beyond the features provided in a standard Azure SQL Database (single database model).</span></span> <span data-ttu-id="0228a-115">마지막으로 가장 많은 PaaS를 선택 하지만 기존 SQL server와 동일한 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-115">This last one is the most PaaS-oriented choice, but it doesn't offer the same features as that of a traditional SQL server.</span></span> <span data-ttu-id="0228a-116">마이그레이션은 마찰 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-116">Migration might surface frictions.</span></span>

<span data-ttu-id="0228a-117">예를 들어 인스턴스 수준 SQL Server 기능에 대 한 심층적인 투자를 수행한 조직은 SQL Managed Instance로 마이그레이션하는 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-117">For example, an organization that has made deep investments in instance-level SQL Server capabilities would benefit from migrating to SQL Managed Instance.</span></span> <span data-ttu-id="0228a-118">인스턴스 수준 SQL Server 기능의 예로는 SQL CLR (공용 언어 런타임) 통합, SQL Server 에이전트, 데이터베이스 간 쿼리 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-118">Examples of instance-level SQL Server capabilities include SQL common language runtime (CLR) integration, SQL Server Agent, and cross-database querying.</span></span> <span data-ttu-id="0228a-119">표준 Azure SQL Database (단일 데이터베이스 모델)에서는 이러한 기능에 대 한 지원을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-119">Support for these features is not available in standard Azure SQL Database (a single-database model).</span></span>

<span data-ttu-id="0228a-120">강력 하 게 규제 된 업계에서 작동 하 고 보안을 위해 격리를 유지 해야 하는 조직에서는 SQL Managed Instance 모델을 선택 하는 것이 유용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-120">An organization that operates in a highly regulated industry, and which needs to maintain isolation for security purposes, also might benefit from choosing the SQL Managed Instance model.</span></span>

<span data-ttu-id="0228a-121">Azure SQL Database의 Managed Instance에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-121">Managed Instance in Azure SQL Database has the following characteristics:</span></span>

- <span data-ttu-id="0228a-122">Azure Virtual Network를 통한 보안 격리</span><span class="sxs-lookup"><span data-stu-id="0228a-122">Security isolation through Azure Virtual Network</span></span>

- <span data-ttu-id="0228a-123">응용 프로그램 화면 호환성, 다음 기능 사용:</span><span class="sxs-lookup"><span data-stu-id="0228a-123">Application surface compatibility, with these features:</span></span>

  - <span data-ttu-id="0228a-124">SQL Server 에이전트 및 SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="0228a-124">SQL Server Agent and SQL Server Profiler</span></span>

  - <span data-ttu-id="0228a-125">데이터베이스 간 참조 및 쿼리, SQL CLR, 복제, CDC (변경 데이터 캡처) 및 Service Broker</span><span class="sxs-lookup"><span data-stu-id="0228a-125">Cross-database references and queries, SQL CLR, replication, change data capture (CDC), and Service Broker</span></span>

- <span data-ttu-id="0228a-126">최대 35 TB의 데이터베이스 크기</span><span class="sxs-lookup"><span data-stu-id="0228a-126">Database sizes up to 35 TB</span></span>

- <span data-ttu-id="0228a-127">다음 기능이 포함 된 최소 가동 중지 시간 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0228a-127">Minimum-downtime migration, with these features:</span></span>

  - <span data-ttu-id="0228a-128">Azure Database Migration Service</span><span class="sxs-lookup"><span data-stu-id="0228a-128">Azure Database Migration Service</span></span>

  - <span data-ttu-id="0228a-129">네이티브 백업 및 복원 및 로그 전달</span><span class="sxs-lookup"><span data-stu-id="0228a-129">Native backup and restore, and log shipping</span></span>

<span data-ttu-id="0228a-130">이러한 기능을 사용 하 여 기존 응용 프로그램 데이터베이스를 Azure SQL Database로 마이그레이션하면 Managed Instance 모델에서 PaaS의 SQL Server에 대 한 거의 100%의 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-130">With these capabilities, when you migrate existing application databases to Azure SQL Database, the Managed Instance model offers nearly 100% of the benefits of PaaS for SQL Server.</span></span> <span data-ttu-id="0228a-131">Managed Instance는 응용 프로그램 디자인을 변경 하지 않고 인스턴스 수준 기능을 계속 사용 하는 SQL Server 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-131">Managed Instance is a SQL Server environment where you continue using instance-level capabilities without changing your application design.</span></span>

<span data-ttu-id="0228a-132">Managed Instance은 현재 SQL Server를 사용 하 고 있으며 클라우드의 네트워크 보안이 유연 해야 하는 엔터프라이즈에 가장 적합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-132">Managed Instance is probably the best fit for enterprises that currently are using SQL Server, and which require flexibility in their network security in the cloud.</span></span> <span data-ttu-id="0228a-133">SQL 데이터베이스용 개인 가상 네트워크를 보유 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-133">It's like having a private virtual network for your SQL databases.</span></span>

## <a name="when-to-migrate-to-azure-sql-database"></a><span data-ttu-id="0228a-134">Azure SQL Database로 마이그레이션해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="0228a-134">When to migrate to Azure SQL Database</span></span>

<span data-ttu-id="0228a-135">앞서 언급 했 듯이, 표준 Azure SQL Database는 완전히 관리 되는 관계형 DBaaS입니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-135">As mentioned, the standard Azure SQL Database is a fully managed, relational DBaaS.</span></span> <span data-ttu-id="0228a-136">SQL Database는 현재 전 세계 38 데이터 센터에서 수백만 개의 프로덕션 데이터베이스를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-136">SQL Database currently manages millions of production databases, across 38 datacenters, around the world.</span></span> <span data-ttu-id="0228a-137">간단한 트랜잭션 데이터 관리부터 광범위 한 응용 프로그램 및 워크 로드를 지원 하 여 글로벌 규모로 고급 데이터를 처리 해야 하는 가장 중요 한 데이터를 많이 사용 하는 중요 업무용 응용 프로그램을 구동 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-137">It supports a broad range of applications and workloads, from managing straightforward transactional data, to driving the most data-intensive, mission-critical applications that require advanced data processing at a global scale.</span></span>

<span data-ttu-id="0228a-138">전체 PaaS 기능, 더 나은 가격 책정 및 궁극적으로 저렴 한 비용으로 인해 기본, 표준 SQL 데이터베이스를 사용 하는 응용 프로그램을 사용 하 고 추가 인스턴스 기능을 사용 하지 않는 경우 "기본적으로" 선택 사항으로 표준 Azure SQL Database 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-138">Because of its full PaaS features, better pricing-and ultimately lower cost-you should move to the standard Azure SQL Database as your "by-default choice" if you have an application that uses basic, standard SQL databases, and no additional instance features.</span></span> <span data-ttu-id="0228a-139">SQL CLR 통합, SQL Server 에이전트 및 데이터베이스 간 쿼리와 같은 SQL Server 기능은 표준 Azure SQL Database에서 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-139">SQL Server features like SQL CLR integration, SQL Server Agent, and cross-database querying are not supported in the standard Azure SQL Database.</span></span> <span data-ttu-id="0228a-140">이러한 기능은 Azure SQL Database Managed Instance 모델 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-140">Those features are available only in the Azure SQL Database Managed Instance model.</span></span>

<span data-ttu-id="0228a-141">Azure SQL Database는 앱 개발자 용으로 빌드된 유일한 인텔리전트 클라우드 데이터베이스 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-141">Azure SQL Database is the only intelligent cloud database service that's built for app developers.</span></span> <span data-ttu-id="0228a-142">또한 테 넌 트 앱을 효율적으로 제공 하는 데 도움이 되도록 가동 중지 시간 없이 즉시 확장 되는 유일한 클라우드 데이터베이스 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-142">It's also the only cloud database service that scales on-the-fly, without downtime, to help you efficiently deliver multitenant apps.</span></span> <span data-ttu-id="0228a-143">궁극적으로 Azure SQL Database은 혁신 하는 데 더 많은 시간을 두고 출시 시간을 단축 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-143">Ultimately, Azure SQL Database leaves you more time to innovate, and it accelerates your time to market.</span></span> <span data-ttu-id="0228a-144">원하는 언어와 플랫폼을 사용 하 여 안전한 앱을 빌드하고 SQL database에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-144">You can build secure apps and connect to your SQL database by using the languages and platforms that you prefer.</span></span>

<span data-ttu-id="0228a-145">Azure SQL Database는 다음과 같은 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-145">Azure SQL Database offers the following benefits:</span></span>

- <span data-ttu-id="0228a-146">앱을 학습 하 고 적응 하는 기본 제공 인텔리전스 (기계 학습)</span><span class="sxs-lookup"><span data-stu-id="0228a-146">Built-in intelligence (machine learning) that learns and adapts to your app</span></span>

- <span data-ttu-id="0228a-147">주문형 데이터베이스 프로 비전</span><span class="sxs-lookup"><span data-stu-id="0228a-147">On-demand database provisioning</span></span>

- <span data-ttu-id="0228a-148">모든 워크 로드에 대 한 제품의 범위</span><span class="sxs-lookup"><span data-stu-id="0228a-148">A range of offers, for all workloads</span></span>

- <span data-ttu-id="0228a-149">99.99% 가용성 SLA, 영 유지 관리</span><span class="sxs-lookup"><span data-stu-id="0228a-149">99.99% availability SLA, zero maintenance</span></span>

- <span data-ttu-id="0228a-150">데이터 보호를 위한 지역에서 복제 및 복원 서비스</span><span class="sxs-lookup"><span data-stu-id="0228a-150">Geo-replication and restore services for data protection</span></span>

- <span data-ttu-id="0228a-151">Azure SQL Database 지정 시간 복원 기능</span><span class="sxs-lookup"><span data-stu-id="0228a-151">Azure SQL Database Point in Time Restore feature</span></span>

- <span data-ttu-id="0228a-152">하이브리드 및 마이그레이션을 포함 하 여 SQL Server 2016과의 호환성</span><span class="sxs-lookup"><span data-stu-id="0228a-152">Compatibility with SQL Server 2016, including hybrid and migration</span></span>

<span data-ttu-id="0228a-153">표준 Azure SQL Database Azure SQL Database Managed Instance 보다 PaaS에 가깝습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-153">The standard Azure SQL Database is closer to PaaS than Azure SQL Database Managed Instance.</span></span> <span data-ttu-id="0228a-154">관리 되는 클라우드에서 더 많은 이점을 얻을 수 있으므로 표준 Azure SQL Database를 사용 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-154">Prefer the standard Azure SQL Database because you'll get more benefits from a managed cloud.</span></span> <span data-ttu-id="0228a-155">그러나 Azure SQL Database는 일반 및 온-프레미스 SQL Server 인스턴스와 몇 가지 주요 차이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-155">However, Azure SQL Database has some key differences from regular and on-premises SQL Server instances.</span></span> <span data-ttu-id="0228a-156">기존 응용 프로그램의 데이터베이스 요구 사항 및 엔터프라이즈 요구 사항 및 정책에 따라 클라우드로의 마이그레이션을 계획할 때 가장 적합 한 선택이 아닐 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-156">Depending on your existing application's database requirements, and your enterprise requirements and policies, it might not be the best choice when you are planning your migration to the cloud.</span></span>

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a><span data-ttu-id="0228a-157">원본 RDBMS를 VM (IaaS)으로 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="0228a-157">When to move your original RDBMS to a VM (IaaS)</span></span>

<span data-ttu-id="0228a-158">마이그레이션 옵션 중 하나는 Oracle, IBM DB2, MySQL, PostgreSQL 또는 SQL Server를 포함 하 여 원래 RDBMS (관계형 데이터베이스 관리 시스템)를 Azure VM에서 실행 되는 유사한 서버로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-158">One of your migration options is to move your original relational database management system (RDBMS), including Oracle, IBM DB2, MySQL, PostgreSQL, or SQL Server, to a similar server that's running on an Azure VM.</span></span> <span data-ttu-id="0228a-159">변경을 최소화 하거나 전혀 변경 하지 않고 클라우드로 가장 빠르게 마이그레이션해야 하는 기존 응용 프로그램이 있는 경우 클라우드의 IaaS로 직접 마이그레이션하는 것은 공평 한 옵션 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-159">If you have existing applications that require the fastest migration to the cloud with minimal changes, or no changes at all, a direct migration to IaaS in the cloud might be a fair option.</span></span> <span data-ttu-id="0228a-160">모든 클라우드의 이점을 활용 하는 가장 좋은 방법이 아닐 수 있지만 가장 빠른 초기 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-160">It might not be the best way to take advantage of all the cloud's benefits, but it's probably the fastest initial path.</span></span>

<span data-ttu-id="0228a-161">현재 Microsoft Azure는 IaaS Vm으로 배포 된 [데이터베이스 서버](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) 를 최대 331 개까지 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-161">Currently, Microsoft Azure supports up to [331 different database servers](https://azuremarketplace.microsoft.com/marketplace/apps/category/databases?page=1&subcategories=databases-all) deployed as IaaS VMs.</span></span> <span data-ttu-id="0228a-162">여기에는 SQL Server, Oracle, MySQL, PostgreSQL 및 IBM DB2와 같은 널리 사용 되는 RDBMS와 MongoDB, Cassandra, DataStax, Cloudera Iadb 및와 같은 기타 여러 NoSQL 데이터베이스가 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-162">These include popular RDBMS like SQL Server, Oracle, MySQL, PostgreSQL, and IBM DB2, and many other NoSQL databases like MongoDB, Cassandra, DataStax, MariaDB, and Cloudera.</span></span>

> [!NOTE]
> <span data-ttu-id="0228a-163">RDBMS를 Azure VM으로 이동 하는 것이 IaaS 이기 때문에 데이터를 클라우드로 마이그레이션하는 가장 빠른 방법일 수 있지만,이 방법은 IT 팀 (데이터베이스 관리자 및 IT 전문가)에 상당한 투자가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-163">Although moving your RDBMS to an Azure VM might be the fastest way to migrate your data to the cloud (because it is IaaS), this approach requires a significant investment in your IT teams (database administrators and IT pros).</span></span> <span data-ttu-id="0228a-164">엔터프라이즈 팀은 고가용성, 재해 복구 및 SQL Server에 대 한 패치를 설정 하 고 관리할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-164">Enterprise teams need to be able to set up and manage high availability, disaster recovery, and patching for SQL Server.</span></span> <span data-ttu-id="0228a-165">이 컨텍스트에는 모든 관리 권한이 있는 사용자 지정 된 환경도 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-165">This context also needs a customized environment, with full administrative rights.</span></span>

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a><span data-ttu-id="0228a-166">VM (IaaS)으로 SQL Server로 마이그레이션해야 하는 경우</span><span class="sxs-lookup"><span data-stu-id="0228a-166">When to migrate to SQL Server as a VM (IaaS)</span></span>

<span data-ttu-id="0228a-167">일반 VM으로 SQL Server로 마이그레이션해야 하는 경우도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-167">There might be a few cases where you still need to migrate to SQL Server as a regular VM.</span></span> <span data-ttu-id="0228a-168">SQL Server Reporting Services를 사용 해야 하는 경우를 예로 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-168">An example scenario is if you need to use SQL Server Reporting Services.</span></span> <span data-ttu-id="0228a-169">그러나 대부분의 경우에는 온-프레미스 SQL server에서 마이그레이션하는 데 필요한 모든 항목을 제공할 수 있으므로 SQL Server VM로의 마이그레이션은 마지막으로 시도 하는 것이 Azure SQL Database Managed Instance.</span><span class="sxs-lookup"><span data-stu-id="0228a-169">In most cases, though, Azure SQL Database Managed Instance can provide everything you need to migrate from on-premises SQL servers, so migration to a SQL Server VM should be your last resort to try.</span></span>

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a><span data-ttu-id="0228a-170">Azure Database Migration Service를 사용 하 여 관계형 데이터베이스를 Azure로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="0228a-170">Use Azure Database Migration Service to migrate your relational databases to Azure</span></span>

<span data-ttu-id="0228a-171">Azure Database Migration Service를 사용 하 여 Azure VM에서 대상 데이터베이스가 Azure SQL Database, Azure SQL Database Managed Instance 또는 SQL Server 되는지 여부와 상관 없이 SQL Server, Oracle, MySQL 등의 관계형 데이터베이스를 Azure로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-171">You can use Azure Database Migration Service to migrate relational databases like SQL Server, Oracle, and MySQL to Azure, whether your target database is Azure SQL Database, Azure SQL Database Managed Instance, or SQL Server on an Azure VM.</span></span>

<span data-ttu-id="0228a-172">자동 워크플로는 평가 보고 기능을 통해 데이터베이스를 마이그레이션하기 전에 수행 해야 하는 변경 사항을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-172">The automated workflow, with assessment reporting, guides you through the changes you need to make before you migrate the database.</span></span> <span data-ttu-id="0228a-173">준비가 되 면 서비스는 원본 데이터베이스를 Azure로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-173">When you are ready, the service migrates the source database to Azure.</span></span>

<span data-ttu-id="0228a-174">원래 RDBMS를 변경할 때마다 다시 테스트 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-174">Whenever you change an original RDBMS, you might need to retest.</span></span> <span data-ttu-id="0228a-175">테스트 결과에 따라 응용 프로그램에서 SQL 문장이 나 ORM (개체-관계형 매핑) 코드를 변경 해야 할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-175">You also might need to change the SQL sentences or Object-Relational Mapping (ORM) code in your application, depending on testing results.</span></span>

<span data-ttu-id="0228a-176">다른 데이터베이스 (예: IBM DB2)가 있고 리프트 앤 시프트 방식을 선택 하는 경우 더 복잡 한 데이터 마이그레이션을 수행 하려는 경우가 아니면 이러한 데이터베이스를 Azure에서 IaaS Vm으로 계속 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-176">If you have any other database (for example, IBM DB2) and you opt for a lift and shift approach, you might want to continue using those databases as IaaS VMs in Azure, unless you are willing to perform a more complex data migration.</span></span> <span data-ttu-id="0228a-177">더 복잡 한 데이터 마이그레이션은 새 스키마와 다른 프로그래밍 라이브러리를 사용 하 여 다른 데이터베이스 형식으로 마이그레이션할 수 있기 때문에 추가 작업이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="0228a-177">A more complex data migration will require additional effort because you'd be migrating to a different database type with new schema and different programming libraries.</span></span>

<span data-ttu-id="0228a-178">Azure Database Migration Service를 사용 하 여 데이터베이스를 마이그레이션하는 방법에 대 한 자세한 내용은 Azure SQL Database Managed Instance 및 Azure Database Migration Service를 사용 하 여 [클라우드로 빠르게 가져오기](https://channel9.msdn.com/Events/Build/2017/P4008)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0228a-178">To learn how to migrate databases by using Azure Database Migration Service, see [Get to the cloud faster with Azure SQL Database Managed Instance and Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="0228a-179">추가 자료</span><span class="sxs-lookup"><span data-stu-id="0228a-179">Additional resources</span></span>

- <span data-ttu-id="0228a-180">**클라우드 SQL Server 옵션 선택: Azure SQL Database (PaaS) 또는 Azure VM에서 SQL Server (IaaS)**</span><span class="sxs-lookup"><span data-stu-id="0228a-180">**Choose a cloud SQL Server option: Azure SQL Database (PaaS) or SQL Server on Azure VM (IaaS)**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- <span data-ttu-id="0228a-181">**Azure SQL DB Managed Instance 및 Database Migration Service를 사용 하 여 클라우드로 더 빠르게 시작**</span><span class="sxs-lookup"><span data-stu-id="0228a-181">**Get to the cloud faster with Azure SQL DB Managed Instance and Database Migration Service**</span></span>

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- <span data-ttu-id="0228a-182">**클라우드에서 SQL Database로 SQL Server 데이터베이스 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="0228a-182">**SQL Server database migration to SQL Database in the cloud**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- <span data-ttu-id="0228a-183">**Azure SQL Database**</span><span class="sxs-lookup"><span data-stu-id="0228a-183">**Azure SQL Database**</span></span>

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- <span data-ttu-id="0228a-184">**가상 컴퓨터의 SQL Server**</span><span class="sxs-lookup"><span data-stu-id="0228a-184">**SQL Server on virtual machines**</span></span>

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> <span data-ttu-id="0228a-185">[이전](lift-and-shift-existing-apps-azure-iaas.md)
> [다음](modernize-existing-apps-to-cloud-optimized/index.md)</span><span class="sxs-lookup"><span data-stu-id="0228a-185">[Previous](lift-and-shift-existing-apps-azure-iaas.md)
[Next](modernize-existing-apps-to-cloud-optimized/index.md)</span></span> <!-- Next Chapter -->
