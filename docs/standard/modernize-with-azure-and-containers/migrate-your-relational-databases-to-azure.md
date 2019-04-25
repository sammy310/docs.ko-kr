---
title: 관계형 데이터베이스를 azure로 마이그레이션
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 관계형 데이터베이스를 azure로 마이그레이션
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 04/28/2018
ms.openlocfilehash: 600c47b6b0ccaf704c8e7b638c759e990acaaacf
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61812785"
---
# <a name="migrate-your-relational-databases-to-azure"></a><span data-ttu-id="a5f54-103">관계형 데이터베이스를 azure로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="a5f54-103">Migrate your relational databases to azure</span></span>

<span data-ttu-id="a5f54-104">Vision: Azure는 가장 포괄적인 데이터베이스 마이그레이션은 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-104">Vision: Azure offers the most comprehensive database migration.</span></span>

<span data-ttu-id="a5f54-105">Azure에서 IaaS VM(순수한 리프트 앤 시프트)에 직접 데이터베이스 서버를 마이그레이션하거나, 추가적인 이득을 얻기 위해 Azure SQL Database로 마이그레이션할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-105">In Azure, you can migrate your database servers directly to IaaS VMs (pure lift and shift), or you can migrate to Azure SQL Database, for additional benefits.</span></span> <span data-ttu-id="a5f54-106">Azure SQL Database에서는 관리되는 인스턴스와 서비스 형태의 전체 데이터베이스(DBaaS) 옵션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-106">Azure SQL Database offers managed instance and full database-as-a-service (DBaaS) options.</span></span> <span data-ttu-id="a5f54-107">그림 3-1에서는 Azure에서 사용할 수 있는 다양한 관계형 데이터베이스 마이그레이션 경로를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-107">Figure 3-1 shows the multiple relational database migration paths available in Azure.</span></span>

![Azure에서 데이터베이스 마이그레이션 경로](./media/image3-1.png)

> <span data-ttu-id="a5f54-109">**그림 3-1.**</span><span class="sxs-lookup"><span data-stu-id="a5f54-109">**Figure 3-1.**</span></span> <span data-ttu-id="a5f54-110">Azure에서 데이터베이스 마이그레이션 경로</span><span class="sxs-lookup"><span data-stu-id="a5f54-110">Database migration paths in Azure</span></span>

## <a name="when-to-migrate-to-azure-sql-database-managed-instance"></a><span data-ttu-id="a5f54-111">Azure SQL Database Managed Instance로 마이그레이션할 시기</span><span class="sxs-lookup"><span data-stu-id="a5f54-111">When to migrate to Azure SQL Database Managed Instance</span></span>

<span data-ttu-id="a5f54-112">대부분의 경우, Azure SQL Database Managed Instance에 Azure에 데이터를 마이그레이션할 때 고려할 최선의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-112">In most cases, Azure SQL Database Managed Instance will be your best option to consider when you migrate your data to Azure.</span></span> <span data-ttu-id="a5f54-113">SQL Server 데이터베이스를 마이그레이션하는 거의 하지 않아도 응용 프로그램을 재설계 하거나 데이터 또는 데이터 액세스 코드를 변경 하는 100% 보증 해야 하는 경우 Azure SQL Database의 관리 되는 인스턴스 기능을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-113">If you are migrating SQL Server databases and need nearly 100% assurance that you won't need to rearchitect your application or make changes to your data or data access code, choose the Managed Instance feature of Azure SQL Database.</span></span>

<span data-ttu-id="a5f54-114">Azure SQL Database 관리 되는 인스턴스는 SQL Server 인스턴스 수준 기능에 대 한 추가 요구 사항 또는 표준 Azure SQL Database (단일 데이터베이스 모델)에서 제공 하는 기능 이상의 격리 요구 사항이 있는 경우 최상의 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-114">Azure SQL Database Managed Instance is the best option if you have additional requirements for SQL Server instance-level functionality, or isolation requirements beyond the features provided in a standard Azure SQL Database (single database model).</span></span> <span data-ttu-id="a5f54-115">마지막은 가장 PaaS 지향 선택 되었지만 기존 SQL server와 동일한 기능을 제공 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-115">This last one is the most PaaS-oriented choice, but it doesn't offer the same features as that of a traditional SQL server.</span></span> <span data-ttu-id="a5f54-116">마이그레이션 마찰을 표시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-116">Migration might surface frictions.</span></span>

<span data-ttu-id="a5f54-117">예를 들어, SQL Server 기능 인스턴스 수준에서에서 심층 투자에 조직에서 SQL Managed Instance로 마이그레이션 도움이 되는 경우</span><span class="sxs-lookup"><span data-stu-id="a5f54-117">For example, an organization that has made deep investments in instance-level SQL Server capabilities would benefit from migrating to SQL Managed Instance.</span></span> <span data-ttu-id="a5f54-118">인스턴스 수준 SQL Server 기능의 예제는 SQL 공용 언어 런타임 (CLR) 통합, SQL Server 에이전트 및 데이터베이스 간 쿼리 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-118">Examples of instance-level SQL Server capabilities include SQL common language runtime (CLR) integration, SQL Server Agent, and cross-database querying.</span></span> <span data-ttu-id="a5f54-119">이러한 기능에 대 한 지원이 표준 Azure SQL Database (단일 데이터베이스 모델)에서 사용할 수 없는 경우</span><span class="sxs-lookup"><span data-stu-id="a5f54-119">Support for these features is not available in standard Azure SQL Database (a single-database model).</span></span>

<span data-ttu-id="a5f54-120">매우 규제 산업에서 작동 하는 및 보안을 위해 격리를 유지 해야 하는 조직을에서 이점을 얻을 수 SQL Managed Instance 모델을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-120">An organization that operates in a highly regulated industry, and which needs to maintain isolation for security purposes, also might benefit from choosing the SQL Managed Instance model.</span></span>

<span data-ttu-id="a5f54-121">Azure SQL Database에서 관리 되는 인스턴스에는 다음과 같은 특징이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-121">Managed Instance in Azure SQL Database has the following characteristics:</span></span>

- <span data-ttu-id="a5f54-122">Azure Virtual Network를 통해 보안 격리</span><span class="sxs-lookup"><span data-stu-id="a5f54-122">Security isolation through Azure Virtual Network</span></span>

- <span data-ttu-id="a5f54-123">응용 프로그램 노출 호환성, 이러한 기능을 사용 하 여:</span><span class="sxs-lookup"><span data-stu-id="a5f54-123">Application surface compatibility, with these features:</span></span>

  - <span data-ttu-id="a5f54-124">SQL Server 에이전트 및 SQL Server Profiler</span><span class="sxs-lookup"><span data-stu-id="a5f54-124">SQL Server Agent and SQL Server Profiler</span></span>

  - <span data-ttu-id="a5f54-125">데이터베이스 간 참조 및 쿼리를 SQL CLR, 복제, 변경 데이터 캡처 (CDC) 및 Service Broker</span><span class="sxs-lookup"><span data-stu-id="a5f54-125">Cross-database references and queries, SQL CLR, replication, change data capture (CDC), and Service Broker</span></span>

- <span data-ttu-id="a5f54-126">데이터베이스 크기 최대 35TB</span><span class="sxs-lookup"><span data-stu-id="a5f54-126">Database sizes up to 35 TB</span></span>

- <span data-ttu-id="a5f54-127">이러한 기능을 사용 하 여 최소 가동 중지 시간 마이그레이션:</span><span class="sxs-lookup"><span data-stu-id="a5f54-127">Minimum-downtime migration, with these features:</span></span>

  - <span data-ttu-id="a5f54-128">Azure Database Migration Service</span><span class="sxs-lookup"><span data-stu-id="a5f54-128">Azure Database Migration Service</span></span>

  - <span data-ttu-id="a5f54-129">기본 백업 및 복원, 로그 전달</span><span class="sxs-lookup"><span data-stu-id="a5f54-129">Native backup and restore, and log shipping</span></span>

<span data-ttu-id="a5f54-130">이러한 기능을 사용 하 여 Azure SQL Database에 기존 응용 프로그램 데이터베이스를 마이그레이션하는 경우 관리 되는 인스턴스 모델 제공 PaaS의 이점 중 거의 100% SQL Server에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-130">With these capabilities, when you migrate existing application databases to Azure SQL Database, the Managed Instance model offers nearly 100% of the benefits of PaaS for SQL Server.</span></span> <span data-ttu-id="a5f54-131">관리 되는 인스턴스는 인스턴스 수준 기능을 사용 하 여 응용 프로그램 디자인을 변경 하지 않고 계속 하면 SQL Server 환경입니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-131">Managed Instance is a SQL Server environment where you continue using instance-level capabilities without changing your application design.</span></span>

<span data-ttu-id="a5f54-132">관리 되는 인스턴스는 현재 SQL Server를 사용 중인 및 클라우드에서 네트워크 보안에 유연성이 필요한는 기업에 가장 적합 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-132">Managed Instance is probably the best fit for enterprises that currently are using SQL Server, and which require flexibility in their network security in the cloud.</span></span> <span data-ttu-id="a5f54-133">SQL database에 대 한 개인 가상 네트워크를 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-133">It's like having a private virtual network for your SQL databases.</span></span>

## <a name="when-to-migrate-to-azure-sql-database"></a><span data-ttu-id="a5f54-134">Azure SQL Database로 마이그레이션할 시기</span><span class="sxs-lookup"><span data-stu-id="a5f54-134">When to migrate to Azure SQL Database</span></span>

<span data-ttu-id="a5f54-135">언급 했 듯이 표준 Azure SQL Database는 완전히 관리 되는 관계형 DBaaS 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-135">As mentioned, the standard Azure SQL Database is a fully managed, relational DBaaS.</span></span> <span data-ttu-id="a5f54-136">SQL Database는 현재 전 세계 38 데이터 센터에서 수백만 개의 프로덕션 데이터베이스를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-136">SQL Database currently manages millions of production databases, across 38 datacenters, around the world.</span></span> <span data-ttu-id="a5f54-137">광범위 한 응용 프로그램 및 글로벌 규모로 고급 데이터 처리를 필요로 하는 데이터를 가장 많이 사용 하는 중요 업무용 응용 프로그램을 이끌어내기 위해 간단한 트랜잭션 데이터 관리에서 워크 로드를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-137">It supports a broad range of applications and workloads, from managing straightforward transactional data, to driving the most data-intensive, mission-critical applications that require advanced data processing at a global scale.</span></span>

<span data-ttu-id="a5f54-138">해당 전체 PaaS 기능으로 인해 보다 나은 가격-궁극적으로 비용을 절감 하 고-있다면 응용 프로그램을 사용 하 여 기본, 표준 SQL database 인스턴스 추가 기능이 없습니다 "기본적으로 선택한"으로 표준 Azure SQL Database로 이동 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-138">Because of its full PaaS features, better pricing-and ultimately lower cost-you should move to the standard Azure SQL Database as your "by-default choice" if you have an application that uses basic, standard SQL databases, and no additional instance features.</span></span> <span data-ttu-id="a5f54-139">표준 Azure SQL Database에서 SQL CLR 통합, SQL Server 에이전트 및 데이터베이스 간 쿼리와 같은 SQL Server 기능을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-139">SQL Server features like SQL CLR integration, SQL Server Agent, and cross-database querying are not supported in the standard Azure SQL Database.</span></span> <span data-ttu-id="a5f54-140">이러한 기능은 Azure SQL Database Managed Instance 모델 에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-140">Those features are available only in the Azure SQL Database Managed Instance model.</span></span>

<span data-ttu-id="a5f54-141">Azure SQL Database는 앱 개발자를 위한 기본 제공 되는 지능형 클라우드 데이터베이스 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-141">Azure SQL Database is the only intelligent cloud database service that's built for app developers.</span></span> <span data-ttu-id="a5f54-142">즉석에서 다중 테 넌 트 앱을 효율적으로 제공 하는 데 가동 중지 시간 없이 크기가 조정 되는 유일한 클라우드 데이터베이스 서비스 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-142">It's also the only cloud database service that scales on-the-fly, without downtime, to help you efficiently deliver multitenant apps.</span></span> <span data-ttu-id="a5f54-143">궁극적으로 Azure SQL Database를 혁신 하는 데 더 오래 유지 및 출시 시간 가속화 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-143">Ultimately, Azure SQL Database leaves you more time to innovate, and it accelerates your time to market.</span></span> <span data-ttu-id="a5f54-144">보안 앱을 빌드하고 원하는 플랫폼과 언어를 사용 하 여 SQL database에 연결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-144">You can build secure apps and connect to your SQL database by using the languages and platforms that you prefer.</span></span>

<span data-ttu-id="a5f54-145">Azure SQL Database는 다음과 같은 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-145">Azure SQL Database offers the following benefits:</span></span>

- <span data-ttu-id="a5f54-146">학습 및 적응 응용 프로그램에 기본 제공 인텔리전스 (기계 학습)</span><span class="sxs-lookup"><span data-stu-id="a5f54-146">Built-in intelligence (machine learning) that learns and adapts to your app</span></span>

- <span data-ttu-id="a5f54-147">요청 시 데이터베이스 프로 비전</span><span class="sxs-lookup"><span data-stu-id="a5f54-147">On-demand database provisioning</span></span>

- <span data-ttu-id="a5f54-148">모든 워크 로드에 대 한 제품의 범위</span><span class="sxs-lookup"><span data-stu-id="a5f54-148">A range of offers, for all workloads</span></span>

- <span data-ttu-id="a5f54-149">99.99% 가용성 SLA, 0 개 유지 관리</span><span class="sxs-lookup"><span data-stu-id="a5f54-149">99.99% availability SLA, zero maintenance</span></span>

- <span data-ttu-id="a5f54-150">데이터 보호에 대 한 지역에서 복제 및 복원 서비스</span><span class="sxs-lookup"><span data-stu-id="a5f54-150">Geo-replication and restore services for data protection</span></span>

- <span data-ttu-id="a5f54-151">Azure SQL Database 지정 시간 복원 기능</span><span class="sxs-lookup"><span data-stu-id="a5f54-151">Azure SQL Database Point in Time Restore feature</span></span>

- <span data-ttu-id="a5f54-152">SQL Server 2016에서는 하이브리드 및 마이그레이션을 비롯 한 호환성</span><span class="sxs-lookup"><span data-stu-id="a5f54-152">Compatibility with SQL Server 2016, including hybrid and migration</span></span>

<span data-ttu-id="a5f54-153">표준 Azure SQL Database 보다 더 가까운 PaaS로 Azure SQL Database Managed Instance.</span><span class="sxs-lookup"><span data-stu-id="a5f54-153">The standard Azure SQL Database is closer to PaaS than Azure SQL Database Managed Instance.</span></span> <span data-ttu-id="a5f54-154">관리 되는 클라우드에서 많은 혜택을 얻게 되므로 표준 Azure SQL Database를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-154">Prefer the standard Azure SQL Database because you'll get more benefits from a managed cloud.</span></span> <span data-ttu-id="a5f54-155">그러나 Azure SQL Database 일반에서 몇 가지 주요 차이점이 있으며 온-프레미스 SQL Server 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="a5f54-155">However, Azure SQL Database has some key differences from regular and on-premises SQL Server instances.</span></span> <span data-ttu-id="a5f54-156">기존 응용 프로그램의 데이터베이스 요구 사항 및 enterprise 요구 사항 및 정책에 따라 아닐 최상의 클라우드로 마이그레이션을 계획할 때.</span><span class="sxs-lookup"><span data-stu-id="a5f54-156">Depending on your existing application's database requirements, and your enterprise requirements and policies, it might not be the best choice when you are planning your migration to the cloud.</span></span>

## <a name="when-to-move-your-original-rdbms-to-a-vm-iaas"></a><span data-ttu-id="a5f54-157">원래 RDBMS에 VM (IaaS)으로 이동 하는 경우</span><span class="sxs-lookup"><span data-stu-id="a5f54-157">When to move your original RDBMS to a VM (IaaS)</span></span>

<span data-ttu-id="a5f54-158">마이그레이션 옵션 중 하나에 원래 관계형 데이터베이스 관리 시스템 (RDBMS), Oracle, IBM DB2, MySQL, PostgreSQL 또는 SQL Server를 포함 하 여 Azure VM에서 실행 되는 유사한 서버로 이동 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-158">One of your migration options is to move your original relational database management system (RDBMS), including Oracle, IBM DB2, MySQL, PostgreSQL, or SQL Server, to a similar server that's running on an Azure VM.</span></span> <span data-ttu-id="a5f54-159">최소한의 변경 내용 또는 변경 없이 클라우드에서 가장 빠른 마이그레이션에 필요한 기존 응용 프로그램에 있는 경우 IaaS 클라우드에서로 직접 마이그레이션하는 공정 옵션을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-159">If you have existing applications that require the fastest migration to the cloud with minimal changes, or no changes at all, a direct migration to IaaS in the cloud might be a fair option.</span></span> <span data-ttu-id="a5f54-160">가장 좋은 방법은 클라우드의 모든 이점을 활용 되지 않을 수 있습니다 하지만 가장 빠른 초기 경로 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-160">It might not be the best way to take advantage of all the cloud's benefits, but it's probably the fastest initial path.</span></span>

<span data-ttu-id="a5f54-161">현재까지 Microsoft Azure 지원 [331 다른 데이터베이스 서버](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) IaaS Vm으로 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-161">Currently, Microsoft Azure supports up to [331 different database servers](https://azuremarketplace.microsoft.com/en-us/marketplace/apps/category/databases?page=1&subcategories=databases-all) deployed as IaaS VMs.</span></span> <span data-ttu-id="a5f54-162">여기에 SQL Server, Oracle, MySQL, PostgreSQL 및 IBM DB2와 같은 인기 있는 RDBMS MongoDB, Cassandra, DataStax, MariaDB, 및 Cloudera와 같은 다른 많은 NoSQL 데이터베이스 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-162">These include popular RDBMS like SQL Server, Oracle, MySQL, PostgreSQL, and IBM DB2, and many other NoSQL databases like MongoDB, Cassandra, DataStax, MariaDB, and Cloudera.</span></span>

> [!NOTE]
> <span data-ttu-id="a5f54-163">이동 되지만 Azure VM에 사용자 RDBMS (이기 때문에 IaaS) 데이터를 클라우드로 마이그레이션에 대 한 가장 빠른 방법은 있을 수 있으며,이 방법을 사용 하려면 (데이터베이스 관리자와 IT 전문가) IT 팀에 많은 투자를 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-163">Although moving your RDBMS to an Azure VM might be the fastest way to migrate your data to the cloud (because it is IaaS), this approach requires a significant investment in your IT teams (database administrators and IT pros).</span></span> <span data-ttu-id="a5f54-164">엔터프라이즈 팀 설정 하 고 고가용성, 재해 복구 및 SQL Server에 대 한 패치를 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-164">Enterprise teams need to be able to set up and manage high availability, disaster recovery, and patching for SQL Server.</span></span> <span data-ttu-id="a5f54-165">이 컨텍스트는 또한 모든 관리 권한이 있는 사용자 지정된 된 환경이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-165">This context also needs a customized environment, with full administrative rights.</span></span>

## <a name="when-to-migrate-to-sql-server-as-a-vm-iaas"></a><span data-ttu-id="a5f54-166">VM (IaaS)으로 SQL Server로 마이그레이션할 시기</span><span class="sxs-lookup"><span data-stu-id="a5f54-166">When to migrate to SQL Server as a VM (IaaS)</span></span>

<span data-ttu-id="a5f54-167">몇 가지 계속 해야 하는 경우 일반 VM과 SQL Server로 마이그레이션에 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-167">There might be a few cases where you still need to migrate to SQL Server as a regular VM.</span></span> <span data-ttu-id="a5f54-168">예제 시나리오는 SQL Server Reporting Services를 사용 해야 하는 경우.</span><span class="sxs-lookup"><span data-stu-id="a5f54-168">An example scenario is if you need to use SQL Server Reporting Services.</span></span> <span data-ttu-id="a5f54-169">대부분의 경우에서 하지만 Azure SQL Database Managed Instance 제공할 수 있도록 SQL Server VM에 대 한 마이그레이션 시도 하 여 마지막 수단으로 사용 해야 합니다. 온-프레미스 SQL server에서 마이그레이션하는 데 필요한 모든 것.</span><span class="sxs-lookup"><span data-stu-id="a5f54-169">In most cases, though, Azure SQL Database Managed Instance can provide everything you need to migrate from on-premises SQL servers, so migration to a SQL Server VM should be your last resort to try.</span></span>

## <a name="use-azure-database-migration-service-to-migrate-your-relational-databases-to-azure"></a><span data-ttu-id="a5f54-170">Azure Database Migration Service를 사용 하 여 Azure에 관계형 데이터베이스를 마이그레이션하려면</span><span class="sxs-lookup"><span data-stu-id="a5f54-170">Use Azure Database Migration Service to migrate your relational databases to Azure</span></span> 

<span data-ttu-id="a5f54-171">Azure SQL Database, Azure SQL Database 관리 되는 인스턴스 또는 Azure VM에서 SQL Server 대상 데이터베이스 인지를 Azure로 SQL Server, Oracle 및 MySQL 등의 관계형 데이터베이스를 마이그레이션하려면 Azure Database Migration Service를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-171">You can use Azure Database Migration Service to migrate relational databases like SQL Server, Oracle, and MySQL to Azure, whether your target database is Azure SQL Database, Azure SQL Database Managed Instance, or SQL Server on an Azure VM.</span></span>

<span data-ttu-id="a5f54-172">평가 보고를 사용 하면 자동화 된 워크플로 데이터베이스를 마이그레이션할 수 있도록 원하는 변경 작업을 안내 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-172">The automated workflow, with assessment reporting, guides you through the changes you need to make before you migrate the database.</span></span> <span data-ttu-id="a5f54-173">준비가 될 때 서비스에서 Azure로 원본 데이터베이스를 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-173">When you are ready, the service migrates the source database to Azure.</span></span>

<span data-ttu-id="a5f54-174">원래 RDBMS를 변경할 때마다 다시 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-174">Whenever you change an original RDBMS, you might need to retest.</span></span> <span data-ttu-id="a5f54-175">SQL 문장이 나 테스트 결과 따라 응용 프로그램에서 개체-관계형 매핑 (ORM) 코드를 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-175">You also might need to change the SQL sentences or Object-Relational Mapping (ORM) code in your application, depending on testing results.</span></span>

<span data-ttu-id="a5f54-176">다른 데이터베이스 (예를 들어, IBM DB2) 있고 리프트 앤 시프트 방식을 선택할 경우 하려는 해당 데이터베이스를 사용 하 여 Azure에서 IaaS Vm으로 계속 더 복잡 한 데이터 마이그레이션을 수행 하려면 원치 않는 경우.</span><span class="sxs-lookup"><span data-stu-id="a5f54-176">If you have any other database (for example, IBM DB2) and you opt for a lift and shift approach, you might want to continue using those databases as IaaS VMs in Azure, unless you are willing to perform a more complex data migration.</span></span> <span data-ttu-id="a5f54-177">새 스키마 및 다른 프로그래밍 라이브러리를 사용 하 여 다른 데이터베이스 형식으로 마이그레이션하는 경우 때문에 더 복잡 한 데이터 마이그레이션을 노력을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-177">A more complex data migration will require additional effort because you'd be migrating to a different database type with new schema and different programming libraries.</span></span>

<span data-ttu-id="a5f54-178">Azure Database Migration Service를 사용 하 여 데이터베이스를 마이그레이션하는 방법에 알아보려면 참조 [Azure SQL Database 관리 되는 인스턴스 및 Azure Database Migration Service를 사용 하 여 더 빠르게 클라우드에](https://channel9.msdn.com/Events/Build/2017/P4008)합니다.</span><span class="sxs-lookup"><span data-stu-id="a5f54-178">To learn how to migrate databases by using Azure Database Migration Service, see [Get to the cloud faster with Azure SQL Database Managed Instance and Azure Database Migration Service](https://channel9.msdn.com/Events/Build/2017/P4008).</span></span>

## <a name="additional-resources"></a><span data-ttu-id="a5f54-179">추가 자료</span><span class="sxs-lookup"><span data-stu-id="a5f54-179">Additional resources</span></span>

- <span data-ttu-id="a5f54-180">**클라우드 SQL Server 옵션 선택: Azure SQL Database (PaaS) 또는 Azure VM (IaaS)에서 SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a5f54-180">**Choose a cloud SQL Server option: Azure SQL Database (PaaS) or SQL Server on Azure VM (IaaS)**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas>

- <span data-ttu-id="a5f54-181">**Azure SQL DB 관리 되는 인스턴스 및 Database Migration Service를 사용 하 여 더 빠르게 클라우드로 가져오기**</span><span class="sxs-lookup"><span data-stu-id="a5f54-181">**Get to the cloud faster with Azure SQL DB Managed Instance and Database Migration Service**</span></span>

    <https://channel9.msdn.com/Events/Build/2017/P4008>

- <span data-ttu-id="a5f54-182">**클라우드에서 SQL Database로 SQL Server 데이터베이스 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="a5f54-182">**SQL Server database migration to SQL Database in the cloud**</span></span>

    <https://docs.microsoft.com/azure/sql-database/sql-database-cloud-migrate>

- <span data-ttu-id="a5f54-183">**Azure SQL Database**</span><span class="sxs-lookup"><span data-stu-id="a5f54-183">**Azure SQL Database**</span></span>

    <https://azure.microsoft.com/services/sql-database/?v=16.50>

- <span data-ttu-id="a5f54-184">**Virtual machines의 SQL Server**</span><span class="sxs-lookup"><span data-stu-id="a5f54-184">**SQL Server on virtual machines**</span></span>

    <https://azure.microsoft.com/services/virtual-machines/sql-server/>

> [!div class="step-by-step"]
> <span data-ttu-id="a5f54-185">[이전](lift-and-shift-existing-apps-azure-iaas.md)
> [다음](modernize-existing-apps-to-cloud-optimized/index.md)</span><span class="sxs-lookup"><span data-stu-id="a5f54-185">[Previous](lift-and-shift-existing-apps-azure-iaas.md)
[Next](modernize-existing-apps-to-cloud-optimized/index.md)</span></span>
