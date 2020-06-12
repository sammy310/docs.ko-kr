---
title: Azure로 SQL Server 데이터베이스 마이그레이션
description: 온-프레미스 SQL Server에서 Azure로 SQL Server 데이터베이스를 마이그레이션하는 방법에 대해 알아보세요.
ms.topic: how-to
ms.date: 05/27/2020
ms.openlocfilehash: ed5d6ef9395dca14d8e0ecba82d3fc18cb3d629a
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2020
ms.locfileid: "84241450"
---
# <a name="migrate-a-sql-server-database-to-azure"></a><span data-ttu-id="499a1-103">Azure로 SQL Server 데이터베이스 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="499a1-103">Migrate a SQL Server database to Azure</span></span>

<span data-ttu-id="499a1-104">이 문서에서는 SQL Server 데이터베이스를 Azure로 마이그레이션하기 위한 두 가지 옵션의 간략한 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-104">This article provides a brief outline of two options for migrating a SQL Server database to Azure.</span></span> <span data-ttu-id="499a1-105">Azure에는 프로덕션 SQL Server 데이터베이스의 마이그레이션을 위한 세 가지 기본 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-105">Azure has three primary options for migrating a production SQL Server database.</span></span> <span data-ttu-id="499a1-106">이 문서에서는 다음 두 가지 옵션을 중점적으로 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-106">This article focuses on the following two options:</span></span>

1. <span data-ttu-id="499a1-107">[Azure VM의 SQL Server](https://docs.microsoft.com/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-iaas-overview): Azure에서 실행되는 Windows Virtual Machine에 설치되고 호스팅되는 SQL Server 인스턴스로, IaaS(서비스 제공 인프라)라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-107">[SQL Server on Azure VMs](https://docs.microsoft.com/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-iaas-overview): A SQL Server instance installed and hosted on a Windows Virtual Machine running in Azure, also known as Infrastructure as a Service (IaaS).</span></span>
2. <span data-ttu-id="499a1-108">[Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview): 완전히 관리되는 SQL 데이터베이스 Azure 서비스로, PaaS(Platform as a Service)라고도 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-108">[Azure SQL Database](https://docs.microsoft.com/azure/sql-database/sql-database-technical-overview): A fully managed SQL database Azure service, also known as Platform as a Service (PaaS).</span></span>

<span data-ttu-id="499a1-109">두 가지 모두 장단점이 있으며 마이그레이션하기 전에 평가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-109">Both come with pros and cons that you will need to evaluate before migrating.</span></span> <span data-ttu-id="499a1-110">세 번째 옵션은 [Azure SQL Database 관리되는 인스턴스](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance)입니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-110">The third option is [Azure SQL Database managed instances](https://docs.microsoft.com/azure/sql-database/sql-database-managed-instance).</span></span>

## <a name="get-started"></a><span data-ttu-id="499a1-111">시작</span><span class="sxs-lookup"><span data-stu-id="499a1-111">Get started</span></span>

<span data-ttu-id="499a1-112">다음 마이그레이션 가이드는 사용하는 서비스에 따라 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-112">The following migration guides will be useful, depending on which service you use:</span></span>

* [<span data-ttu-id="499a1-113">Azure VM에서 SQL Server로 SQL Server 데이터베이스 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="499a1-113">Migrate a SQL Server database to SQL Server in an Azure VM</span></span>](https://docs.microsoft.com/azure/virtual-machines/windows/sql/virtual-machines-windows-migrate-sql)
* [<span data-ttu-id="499a1-114">SQL Server 데이터베이스를 Azure SQL Database로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="499a1-114">Migrate your SQL Server database to Azure SQL Database</span></span>](https://docs.microsoft.com/azure/sql-database/sql-database-migrate-your-sql-server-database)

<span data-ttu-id="499a1-115">또한 개념 콘텐츠에 대한 다음 링크는 VM을 더 잘 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-115">Additionally, the following links to conceptual content will help you understand VMs better:</span></span>

* [<span data-ttu-id="499a1-116">Azure Virtual Machines의 SQL Server에 대한 고가용성 및 재해 복구</span><span class="sxs-lookup"><span data-stu-id="499a1-116">High availability and disaster recovery for SQL Server in Azure Virtual Machines</span></span>](https://docs.microsoft.com/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-high-availability-dr)
* [<span data-ttu-id="499a1-117">Azure Virtual Machines의 SQL Server에 대한 성능 모범 사례</span><span class="sxs-lookup"><span data-stu-id="499a1-117">Performance best practices for SQL Server in Azure Virtual Machines</span></span>](https://docs.microsoft.com/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-performance)
* [<span data-ttu-id="499a1-118">Azure Virtual Machines의 SQL Server에 대한 애플리케이션 패턴 및 개발 전략</span><span class="sxs-lookup"><span data-stu-id="499a1-118">Application Patterns and Development Strategies for SQL Server in Azure Virtual Machines</span></span>](https://docs.microsoft.com/azure/virtual-machines/windows/sql/virtual-machines-windows-sql-server-app-patterns-dev-strategies)

<span data-ttu-id="499a1-119">다음 링크는 Azure SQL Database를 더 잘 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-119">And the following links will help you understand Azure SQL Database better:</span></span>

* [<span data-ttu-id="499a1-120">Azure SQL Database 서버 및 데이터베이스 만들기 및 관리</span><span class="sxs-lookup"><span data-stu-id="499a1-120">Create and manage Azure SQL Database servers and databases</span></span>](https://docs.microsoft.com/azure/sql-database/sql-database-servers-databases)
* [<span data-ttu-id="499a1-121">DTU(데이터베이스 트랜잭션 단위) 및 eDTU(탄력적 데이터베이스 트랜잭션 단위)</span><span class="sxs-lookup"><span data-stu-id="499a1-121">Database Transaction Units (DTUs) and elastic Database Transaction Units (eDTUs)</span></span>](https://docs.microsoft.com/azure/sql-database/sql-database-what-is-a-dtu)
* [<span data-ttu-id="499a1-122">Azure SQL Database 리소스 제한</span><span class="sxs-lookup"><span data-stu-id="499a1-122">Azure SQL Database resource limits</span></span>](https://docs.microsoft.com/azure/sql-database/sql-database-resource-limits)

## <a name="choosing-iaas-or-paas"></a><span data-ttu-id="499a1-123">IaaS 또는 PaaS 선택</span><span class="sxs-lookup"><span data-stu-id="499a1-123">Choosing IaaS or PaaS</span></span>

<span data-ttu-id="499a1-124">데이터베이스를 마이그레이션할 위치를 평가할 때 IaaS 또는 PaaS 중 더 적절한 기능을 결정합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-124">When evaluating where to migrate your database, determine if IaaS or PaaS is more appropriate for you.</span></span>

<span data-ttu-id="499a1-125">**다음과 같은 경우 Azure VM에서 SQL Server를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="499a1-125">**Choose SQL Server in Azure VMs if:**</span></span>

* <span data-ttu-id="499a1-126">최소한의 변경만으로 데이터베이스 및 애플리케이션을 "리프트 앤 시프트"할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-126">You are looking to "lift and shift" your database and applications with minimal to no changes.</span></span>
* <span data-ttu-id="499a1-127">데이터베이스 서버와 이 서버가 실행되는 VM을 완전히 제어하려 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-127">You prefer having full control over your database server and the VM it runs on.</span></span>
* <span data-ttu-id="499a1-128">사용하려는 SQL Server 및 Windows Server 라이선스가 이미 있습니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-128">You already have SQL Server and Windows Server licenses that you intend to use.</span></span>

<span data-ttu-id="499a1-129">**다음과 같은 경우 Azure SQL Database를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="499a1-129">**Choose Azure SQL Database if:**</span></span>

* <span data-ttu-id="499a1-130">Azure에서 애플리케이션을 현대화하고 다른 PaaS 서비스를 사용하기 위해 마이그레이션하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-130">You are looking to modernize your applications and are migrating to use other PaaS services in Azure.</span></span>
* <span data-ttu-id="499a1-131">데이터베이스 서버와 이 서버가 실행되는 VM을 관리하지 않으려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-131">You do not wish to manage your database server and the VM it runs on.</span></span>
* <span data-ttu-id="499a1-132">SQL Server 또는 Windows Server 라이선스에 권한이 없거나 만료된 라이선스를 허용하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-132">You do not have SQL Server or Windows Server licenses, or you intend to let licenses you have expire.</span></span>

<span data-ttu-id="499a1-133">다음 표에서는 일련의 시나리오를 기반으로 각 서비스 간의 차이점을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-133">The following table describes differences between each service based on a set of scenarios.</span></span>

| <span data-ttu-id="499a1-134">시나리오</span><span class="sxs-lookup"><span data-stu-id="499a1-134">Scenario</span></span> | <span data-ttu-id="499a1-135">Azure VM의 SQL Server</span><span class="sxs-lookup"><span data-stu-id="499a1-135">SQL Server in Azure VMs</span></span> | <span data-ttu-id="499a1-136">Azure SQL Database</span><span class="sxs-lookup"><span data-stu-id="499a1-136">Azure SQL Database</span></span> |
|----------|-------------------------|--------------------|
| <span data-ttu-id="499a1-137">마이그레이션</span><span class="sxs-lookup"><span data-stu-id="499a1-137">Migration</span></span> | <span data-ttu-id="499a1-138">데이터베이스를 최소한으로 변경해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-138">Requires minimal changes to your database.</span></span> | <span data-ttu-id="499a1-139">[Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595)에 의해 결정된 대로 Azure SQL에서 사용할 수 없는 기능을 사용하거나 로컬로 설치된 실행 파일처럼 다른 종속성이 있는 경우 데이터베이스를 변경해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-139">May require changes to your database if you use features unavailable in Azure SQL, as determined by the [Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595), or if you have other dependencies such as locally installed executables.</span></span>|
| <span data-ttu-id="499a1-140">가용성, 복구 및 업그레이드 관리</span><span class="sxs-lookup"><span data-stu-id="499a1-140">Managing availability, recovery, and upgrades</span></span> | <span data-ttu-id="499a1-141">가용성 및 복구는 수동으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-141">Availability and recovery are configured manually.</span></span> <span data-ttu-id="499a1-142">업그레이드는 [VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade)를 사용하여 자동화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-142">Upgrades can be automated with [VM Scale Sets](https://docs.microsoft.com/azure/virtual-machine-scale-sets/virtual-machine-scale-sets-automatic-upgrade).</span></span> | <span data-ttu-id="499a1-143">자동으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-143">Automatically managed for you.</span></span> |
| <span data-ttu-id="499a1-144">기본 OS 구성</span><span class="sxs-lookup"><span data-stu-id="499a1-144">Underlying OS configuration</span></span> | <span data-ttu-id="499a1-145">수동 구성.</span><span class="sxs-lookup"><span data-stu-id="499a1-145">Manual configuration.</span></span> | <span data-ttu-id="499a1-146">자동으로 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-146">Automatically managed for you.</span></span> |
| <span data-ttu-id="499a1-147">데이터베이스 크기 관리</span><span class="sxs-lookup"><span data-stu-id="499a1-147">Managing database size</span></span> | <span data-ttu-id="499a1-148">SQL Server 인스턴스당 최대 256TB의 스토리지 용량을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-148">Supports up to 256 TB of storage per SQL Server instance.</span></span> | <span data-ttu-id="499a1-149">수평 분할 전까지 8TB의 스토리지 용량을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-149">Supports 8 TB of storage before needing a horizontal partition.</span></span> |
| <span data-ttu-id="499a1-150">비용 관리</span><span class="sxs-lookup"><span data-stu-id="499a1-150">Managing costs</span></span> | <span data-ttu-id="499a1-151">SQL Server 라이선스 비용, Windows Server 라이선스 비용 및 VM 비용(코어, RAM 및 스토리지 기준)을 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-151">You must manage SQL Server license costs, Windows Server license costs, and VM costs (based on cores, RAM, and storage).</span></span> | <span data-ttu-id="499a1-152">서비스 비용을 관리해야 합니다(탄력적인 풀을 사용하는 경우 [eDTU 또는 DTU](https://docs.microsoft.com/azure/sql-database/sql-database-what-is-a-dtu), 스토리지 및 데이터베이스 수 기준).</span><span class="sxs-lookup"><span data-stu-id="499a1-152">You must manage service costs (based on [eDTUs or DTUs](https://docs.microsoft.com/azure/sql-database/sql-database-what-is-a-dtu), storage, and number of databases if using an elastic pool).</span></span> <span data-ttu-id="499a1-153">SLA의 비용도 관리해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-153">You must also manage the cost of any SLA.</span></span> |

<span data-ttu-id="499a1-154">둘 간의 차이점을 자세히 알아보려면 [Choose the right deployment option in Azure SQL](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas)(Azure SQL에서 적합한 배포 옵션 선택)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="499a1-154">To learn more about the differences between the two, see [Choose the right deployment option in Azure SQL](https://docs.microsoft.com/azure/sql-database/sql-database-paas-vs-sql-server-iaas).</span></span>

## <a name="faq"></a><span data-ttu-id="499a1-155">FAQ</span><span class="sxs-lookup"><span data-stu-id="499a1-155">FAQ</span></span>

* <span data-ttu-id="499a1-156">**Azure VM 또는 Azure SQL Database에서 SQL Server와 함께 SQL Server Management Studio 및 SQL Server Reporting Services(SSRS)와 같은 도구를 계속 사용할 수 있나요?**</span><span class="sxs-lookup"><span data-stu-id="499a1-156">**Can I still use tools such as SQL Server Management Studio and SQL Server Reporting Services (SSRS) with SQL Server in Azure VMs or Azure SQL Database?**</span></span>

    <span data-ttu-id="499a1-157">예.</span><span class="sxs-lookup"><span data-stu-id="499a1-157">Yes.</span></span> <span data-ttu-id="499a1-158">모든 Microsoft SQL 도구는 두 서비스 모두에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-158">All Microsoft SQL tooling works with both services.</span></span> <span data-ttu-id="499a1-159">SSRS는 Azure SQL Database의 일부가 아니기 때문에 Azure VM에서 실행한 다음, 데이터베이스 인스턴스를 가리키도록 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-159">SSRS is not part of Azure SQL Database, though, and it's recommended that you run it in an Azure VM and then point it to your database instance.</span></span>

* <span data-ttu-id="499a1-160">**PaaS로 전환하고 싶지만 데이터베이스가 호환될지 확실하지 않습니다. 유용한 도구가 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="499a1-160">**I want to go PaaS but I'm not sure if my database is compatible. Are there tools to help?**</span></span>

    <span data-ttu-id="499a1-161">예.</span><span class="sxs-lookup"><span data-stu-id="499a1-161">Yes.</span></span> <span data-ttu-id="499a1-162">[Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595)는 Azure SQL Database로 마이그레이션 시 사용되는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-162">The [Data Migration Assistant](https://www.microsoft.com/download/details.aspx?id=53595) is a tool that is used as a part of migrating to Azure SQL Database.</span></span> <span data-ttu-id="499a1-163">[Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/)는 IaaS 또는 PaaS에 사용할 수 있는 미리 보기 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-163">The [Azure Database Migration Service](https://azure.microsoft.com/campaigns/database-migration/) is a preview service that you can use for either IaaS or PaaS.</span></span>

* <span data-ttu-id="499a1-164">**비용을 추정할 수 있습니까?**</span><span class="sxs-lookup"><span data-stu-id="499a1-164">**Can I estimate costs?**</span></span>

    <span data-ttu-id="499a1-165">예.</span><span class="sxs-lookup"><span data-stu-id="499a1-165">Yes.</span></span> <span data-ttu-id="499a1-166">[Azure Pricing Calculator](https://azure.microsoft.com/pricing/calculator/)는 VM 및 데이터베이스 서비스를 포함한 모든 Azure 서비스 비용을 계산하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="499a1-166">The [Azure Pricing Calculator](https://azure.microsoft.com/pricing/calculator/) can be used for estimating costs for all Azure services, including VMs and database services.</span></span>

## <a name="next-steps"></a><span data-ttu-id="499a1-167">다음 단계</span><span class="sxs-lookup"><span data-stu-id="499a1-167">Next steps</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="499a1-168">올바른 Azure 호스팅 옵션 선택</span><span class="sxs-lookup"><span data-stu-id="499a1-168">Choose the right Azure hosting option</span></span>](choose.md)
