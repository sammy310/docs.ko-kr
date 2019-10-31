---
title: 기존 .NET 앱을 Azure IaaS로 리프트 앤 시프트 (클라우드 인프라 준비)
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존 .NET 응용 프로그램을 현대화.
ms.date: 04/28/2018
ms.openlocfilehash: c7638a034dbb27baea1b097bdb66175bfb5a71f2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73089632"
---
# <a name="lift-and-shift-existing-net-apps-to-azure-iaas-cloud-infrastructure-ready"></a><span data-ttu-id="2138e-103">기존 .NET 앱을 Azure IaaS로 리프트 앤 시프트 (클라우드 인프라 준비)</span><span class="sxs-lookup"><span data-stu-id="2138e-103">Lift and shift existing .NET apps to Azure IaaS (Cloud Infrastructure-Ready)</span></span>

> <span data-ttu-id="2138e-104">비전: 온-프레미스 투자와 하드웨어 및 네트워킹 유지 관리의 총 비용을 줄이기 위해 첫 번째 단계로 클라우드의 기존 응용 프로그램을 rehost.</span><span class="sxs-lookup"><span data-stu-id="2138e-104">Vision: As a first step, to reduce your on-premises investment and total cost of hardware and networking maintenance, simply rehost your existing applications in the cloud.</span></span>

<span data-ttu-id="2138e-105">기존 응용 프로그램을 Azure IaaS (infrastructure as a service) 플랫폼으로 마이그레이션하 *는 방법* 에 앞서 Azure에서 iaas로 직접 마이그레이션해야 하 *는 이유를* 분석 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-105">Before getting into *how* to migrate your existing applications to the Azure infrastructure as a service (IaaS) platform, it's important to analyze the reasons *why* you'd want to migrate directly to IaaS in Azure.</span></span> <span data-ttu-id="2138e-106">이 현대화 완성도 수준에서 시나리오는 기본적으로 현재 온-프레미스 인프라를 계속 사용 하는 대신 클라우드에서 Vm 사용을 시작 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-106">The scenario at this modernization maturity level essentially is to start using VMs in the cloud, instead of continuing to use your current, on-premises infrastructure.</span></span>

<span data-ttu-id="2138e-107">분석할 또 다른 점은 Azure에서 고급 관리 서비스를 추가 하는 대신 순수 IaaS 클라우드로 *마이그레이션하는 것입니다.*</span><span class="sxs-lookup"><span data-stu-id="2138e-107">Another point to analyze is *why* you might want to migrate to pure IaaS cloud instead of just adding more advanced managed services in Azure.</span></span> <span data-ttu-id="2138e-108">첫 번째 장소에서 IaaS를 필요로 하는 사례를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-108">Determine what cases might require IaaS in the first place.</span></span>

<span data-ttu-id="2138e-109">그림 2-1은 현대화 완성도 수준에서 클라우드 인프라 준비 응용 프로그램을 배치 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-109">Figure 2-1 positions Cloud Infrastructure-Ready applications in the modernization maturity levels:</span></span>

![클라우드 인프라 준비 응용 프로그램 위치 지정](./media/image2-1.png)

<span data-ttu-id="2138e-111">**그림 2-1.**</span><span class="sxs-lookup"><span data-stu-id="2138e-111">**Figure 2-1.**</span></span> <span data-ttu-id="2138e-112">클라우드 인프라 준비 응용 프로그램 위치 지정</span><span class="sxs-lookup"><span data-stu-id="2138e-112">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="why-migrate-existing-net-web-applications-to-azure-iaas"></a><span data-ttu-id="2138e-113">기존 .NET 웹 응용 프로그램을 Azure IaaS로 마이그레이션하는 이유</span><span class="sxs-lookup"><span data-stu-id="2138e-113">Why migrate existing .NET web applications to Azure IaaS</span></span>

<span data-ttu-id="2138e-114">초기 IaaS 수준 에서도 클라우드로 마이그레이션하는 주된 이유는 비용 절감을 구현 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-114">The main reason to migrate to the cloud, even at an initial IaaS level, is to achieve cost reductions.</span></span> <span data-ttu-id="2138e-115">조직에서는 관리 인프라 서비스를 추가로 사용 하 여 하드웨어 유지 관리, 서버 또는 VM 프로 비전 및 배포 및 인프라 관리에 대 한 투자를 낮출 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-115">By using more managed infrastructure services, your organization can lower its investment in hardware maintenance, server or VM provisioning and deployment, and infrastructure management.</span></span>

<span data-ttu-id="2138e-116">앱을 클라우드로 이동 하기로 결정 한 후에는 PaaS와 같은 고급 옵션 대신 IaaS를 선택할 수 있는 주된 이유가 IaaS 환경이 더 친숙 하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-116">After you make the decision to move your apps to the cloud, the main reason why you might choose IaaS instead of more advanced options like PaaS is simply that the IaaS environment will be more familiar.</span></span> <span data-ttu-id="2138e-117">현재 온-프레미스 환경과 유사한 환경으로 전환 하면 더 낮은 학습 곡선이 제공 되므로 클라우드로 가장 빨리 경로를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-117">Moving to an environment that's similar to your current, on-premises environment offers a lower learning curve, which makes it the quickest path to the cloud.</span></span>

<span data-ttu-id="2138e-118">그러나 클라우드에서 가장 빠른 경로를 사용할 경우 응용 프로그램이 클라우드에서 실행 되는 것이 가장 많은 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-118">However, taking the quickest path to the cloud doesn't mean that you will gain the most benefit from having your applications running in the cloud.</span></span> <span data-ttu-id="2138e-119">모든 조직은 이미 도입 된 클라우드 최적화 및 클라우드 기본 완성도 수준을 기반으로 하는 클라우드 마이그레이션에서 가장 중요 한 이점을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-119">Any organization will gain the most significant benefits from a cloud migration at the already introduced Cloud-Optimized and Cloud-Native maturity levels.</span></span>

<span data-ttu-id="2138e-120">또한 응용 프로그램이 이미 클라우드에서 실행 중일 때 IaaS 에서도 응용 프로그램을 현대화 하 고 다시 설계 하기가 더 쉬워졌습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-120">It also has become evident that applications are easier to modernize and rearchitect in the future when they are already running in the cloud, even on IaaS.</span></span> <span data-ttu-id="2138e-121">응용 프로그램 데이터 마이그레이션은 이미 수행 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-121">Application data migration has already been achieved.</span></span> <span data-ttu-id="2138e-122">또한 조직에서는 클라우드에서 작업 하는 데 필요한 기술을 획득 하 고 "클라우드 문화권"에서 작동 하도록 전환 했습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-122">Also, your organization will have gained skills required for working in the cloud and made the shift to operating in a "cloud culture."</span></span>

## <a name="when-to-migrate-to-iaas-instead-of-to-paas"></a><span data-ttu-id="2138e-123">PaaS가 아닌 IaaS로 마이그레이션하는 경우</span><span class="sxs-lookup"><span data-stu-id="2138e-123">When to migrate to IaaS instead of to PaaS</span></span>

<span data-ttu-id="2138e-124">다음 섹션에서는 주로 PaaS 플랫폼과 서비스를 기반으로 하는 클라우드 최적화 응용 프로그램에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-124">The next sections discuss Cloud-Optimized applications that are mostly based on PaaS platforms and services.</span></span> <span data-ttu-id="2138e-125">이러한 앱을 통해 클라우드로 마이그레이션하는 것이 가장 많은 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-125">These apps give you the most benefits from migrating to the cloud.</span></span>

<span data-ttu-id="2138e-126">단순히 기존 응용 프로그램을 클라우드로 이동 하려는 경우에는 Azure App Service에서 실행 하기 위해 크게 수정 하지 않아도 되는 기존 응용 프로그램을 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-126">If your goal is simply to move existing applications to the cloud, first, identify existing applications that would not require substantial modification to run in Azure App Service.</span></span> <span data-ttu-id="2138e-127">이러한 앱은 클라우드 최적화를 위한 첫 번째 후보가 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-127">These apps should be the first candidates for Cloud-Optimized.</span></span>

<span data-ttu-id="2138e-128">그런 다음 여전히 Windows 컨테이너 및 PaaS로 이동할 수 없는 앱 (App Service 예: Azure Kubernetes Service와 같은 orchestrator 또는)에 대해 이러한 앱을 단순 일반 Vm (IaaS)으로 마이그레이션합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-128">Then, for the apps that still cannot move to Windows Containers and PaaS such as App Service or orchestrators like Azure Kubernetes Service, migrate those to simple plain VMs (IaaS).</span></span>

<span data-ttu-id="2138e-129">그러나 Vm을 올바르게 구성, 보호 및 유지 관리 하려면 Azure에서 PaaS 서비스를 사용 하는 것과 비교 하 여 훨씬 더 많은 시간과 IT 전문 지식이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-129">But, keep in mind that correctly configuring, securing, and maintaining VMs requires much more time and IT expertise compared to using PaaS services in Azure.</span></span> <span data-ttu-id="2138e-130">Azure Virtual Machines를 고려 하는 경우 VM 환경을 패치, 업데이트 및 관리 하는 데 필요한 지속적인 유지 관리 노력을 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-130">If you are considering Azure Virtual Machines, make sure that you take into account the ongoing maintenance effort required to patch, update, and manage your VM environment.</span></span> <span data-ttu-id="2138e-131">Azure Virtual Machines는 IaaS입니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-131">Azure Virtual Machines is IaaS.</span></span>

## <a name="use-azure-migrate-to-analyze-and-migrate-your-existing-applications-to-azure"></a><span data-ttu-id="2138e-132">Azure Migrate를 사용 하 여 기존 응용 프로그램을 분석 하 고 Azure로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2138e-132">Use Azure Migrate to analyze and migrate your existing applications to Azure</span></span>

<span data-ttu-id="2138e-133">클라우드로 마이그레이션하는 것은 어려울 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-133">Migrating to the cloud doesn't have to be difficult.</span></span> <span data-ttu-id="2138e-134">그러나 많은 조직에서 시작 하 여 환경에 대 한 심층 가시성을 얻고 응용 프로그램, 워크 로드 및 데이터를 긴밀 하 게 상호 종속 시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-134">But many organizations struggle to get started - to get deep visibility into the environment and the tight interdependencies between applications, workloads, and data.</span></span> <span data-ttu-id="2138e-135">이러한 표시가 없으면 경로를 앞으로 계획 하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-135">Without that visibility, it can be difficult to plan the path forward.</span></span> <span data-ttu-id="2138e-136">성공적인 마이그레이션에 필요한 사항에 대 한 자세한 정보를 제외 하 고 조직 내에서 올바른 대화를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-136">Without detailed information on what's required for a successful migration, you can't have the right conversations within your organization.</span></span> <span data-ttu-id="2138e-137">잠재적 비용 혜택에 대 한 충분 한 사항이 나 워크 로드를 리프트 앤 시프트 할 수 있는지 또는 워크 로드를 성공적으로 마이그레이션하는 데 상당한 재작업이 필요한 지를 알 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-137">You don't know enough about the potential cost benefits, or whether workloads could just lift-and-shift or would require significant rework to migrate successfully.</span></span> <span data-ttu-id="2138e-138">수많은 조직 주저 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-138">No wonder many organizations hesitate.</span></span>

<span data-ttu-id="2138e-139">[Azure Migrate](https://aka.ms/azuremigrate) 는 Azure로 마이그레이션하는 데 도움이 되는 지침, 통찰력 및 메커니즘을 제공 하는 새로운 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-139">[Azure Migrate](https://aka.ms/azuremigrate) is a new service that provides the guidance, insights, and mechanisms needed to assist you in migrating to Azure.</span></span> <span data-ttu-id="2138e-140">Azure Migrate 제공:</span><span class="sxs-lookup"><span data-stu-id="2138e-140">Azure Migrate provides:</span></span>

- <span data-ttu-id="2138e-141">온-프레미스 가상 머신에 대 한 검색 및 평가</span><span class="sxs-lookup"><span data-stu-id="2138e-141">Discovery and assessment for on-premises virtual machines</span></span>

- <span data-ttu-id="2138e-142">다중 계층 응용 프로그램의 신뢰도 높은 검색을 위한 기본 제공 종속성 매핑</span><span class="sxs-lookup"><span data-stu-id="2138e-142">Inbuilt dependency mapping for high-confidence discovery of multi-tier applications</span></span>

- <span data-ttu-id="2138e-143">Azure virtual machines에 대 한 인텔리전트 올바른 크기 조정</span><span class="sxs-lookup"><span data-stu-id="2138e-143">Intelligent right sizing to Azure virtual machines</span></span>

- <span data-ttu-id="2138e-144">잠재적 문제를 수정 위한 지침과 함께 호환성 보고</span><span class="sxs-lookup"><span data-stu-id="2138e-144">Compatibility reporting with guidelines for remediating potential issues</span></span>

- <span data-ttu-id="2138e-145">데이터베이스 검색 및 마이그레이션을 위해 Azure Database Management Service와 통합</span><span class="sxs-lookup"><span data-stu-id="2138e-145">Integration with Azure Database Management Service for database discovery and migration</span></span>

<span data-ttu-id="2138e-146">Azure Migrate를 통해 비즈니스에 미치는 영향을 최소화 하면서 워크 로드를 마이그레이션할 수 있으며 Azure에서 예상 대로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-146">Azure Migrate gives you confidence that your workloads can migrate with minimal impact to the business and run as expected in Azure.</span></span> <span data-ttu-id="2138e-147">적절 한 도구와 지침을 사용 하면 중요 한 성능 및 안정성 요구를 충족 하는 동시에 투자 수익률을 최대한 달성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-147">With the right tools and guidance, you can achieve maximum return on investment while assuring that critical performance and reliability needs are met.</span></span>

<span data-ttu-id="2138e-148">그림 2-2은 Azure Migrate에서 수행 하는 모든 서버 및 응용 프로그램 연결에 대 한 기본 제공 종속성 매핑을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-148">Figure 2-2 shows you the built-in dependency mapping for all server and application connections performed by Azure Migrate.</span></span>

![클라우드 인프라 준비 응용 프로그램 위치 지정](./media/image2-2.png)

<span data-ttu-id="2138e-150">**그림 2-2.**</span><span class="sxs-lookup"><span data-stu-id="2138e-150">**Figure 2-2.**</span></span> <span data-ttu-id="2138e-151">클라우드 인프라 준비 응용 프로그램 위치 지정</span><span class="sxs-lookup"><span data-stu-id="2138e-151">Positioning Cloud Infrastructure-Ready applications</span></span>

## <a name="use-azure-site-recovery-to-migrate-your-existing-vms-to-azure-vms"></a><span data-ttu-id="2138e-152">Azure Site Recovery를 사용 하 여 기존 Vm을 Azure Vm으로 마이그레이션</span><span class="sxs-lookup"><span data-stu-id="2138e-152">Use Azure Site Recovery to migrate your existing VMs to Azure VMs</span></span>

<span data-ttu-id="2138e-153">종단 간 [Azure Migrate](https://aka.ms/azuremigrate)의 일부로 [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) 는 Azure의 vm으로 웹 앱을 쉽게 마이그레이션하는 데 사용할 수 있는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-153">As part of the end-to-end [Azure Migrate](https://aka.ms/azuremigrate), [Azure Site Recovery](https://docs.microsoft.com/azure/site-recovery/site-recovery-overview) is a tool that you can use to easily migrate your web apps to VMs in Azure.</span></span> <span data-ttu-id="2138e-154">Site Recovery를 사용 하 여 온-프레미스 Vm 및 물리적 서버를 Azure에 복제 하거나 보조 온-프레미스 위치에 복제할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-154">You can use Site Recovery to replicate on-premises VMs and physical servers to Azure, or to replicate them to a secondary on-premises location.</span></span> <span data-ttu-id="2138e-155">지원 되는 Azure VM, 온-프레미스 *Hyper-v* VM, *VMware* Vm 또는 Windows 또는 Linux 물리적 서버에서 실행 되는 워크 로드를 복제할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-155">You can even replicate a workload that's running on a supported Azure VM, on an on-premises *Hyper-V* VM, on a *VMware* VM, or on a Windows or Linux physical server.</span></span> <span data-ttu-id="2138e-156">Azure로 복제 하면 보조 데이터 센터를 유지 관리 하는 비용과 복잡성이 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-156">Replication to Azure eliminates the cost and complexity of maintaining a secondary datacenter.</span></span>

<span data-ttu-id="2138e-157">Site Recovery은 부분적으로 온-프레미스이 고 일부는 Azure에 있는 하이브리드 환경에 대해서도 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-157">Site Recovery is also made specifically for hybrid environments that are partly on-premises and partly on Azure.</span></span> <span data-ttu-id="2138e-158">Site Recovery를 사용 하면 Vm 및 온-프레미스 물리적 서버에서 실행 되는 앱을 사이트 작동이 중단 된 상태로 유지 하 여 비즈니스 연속성을 보장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-158">Site Recovery helps ensure business continuity by keeping your apps that are running on VMs and on-premises physical servers available if a site goes down.</span></span> <span data-ttu-id="2138e-159">Vm 및 물리적 서버에서 실행 되는 워크 로드를 복제 하 여 기본 사이트를 사용할 수 없는 경우 보조 위치에서 계속 사용할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-159">It replicates workloads that are running on VMs and physical servers so that they remain available in a secondary location if the primary site isn't available.</span></span> <span data-ttu-id="2138e-160">작업을 다시 실행 하는 경우 기본 사이트로 작업을 복구 합니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-160">It recovers workloads to the primary site when it's up and running again.</span></span>

<span data-ttu-id="2138e-161">그림 2-3에서는 Azure Site Recovery를 사용 하 여 여러 VM 마이그레이션을 실행 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2138e-161">Figure 2-3 shows the execution of multiple VM migrations by using Azure Site Recovery.</span></span>

![클라우드 인프라 준비 응용 프로그램 위치 지정](./media/image2-3.png)

<span data-ttu-id="2138e-163">**그림 2-3.**</span><span class="sxs-lookup"><span data-stu-id="2138e-163">**Figure 2-3.**</span></span> <span data-ttu-id="2138e-164">클라우드 인프라 준비 응용 프로그램 위치 지정</span><span class="sxs-lookup"><span data-stu-id="2138e-164">Positioning Cloud Infrastructure-Ready applications</span></span>

### <a name="additional-resources"></a><span data-ttu-id="2138e-165">추가 자료</span><span class="sxs-lookup"><span data-stu-id="2138e-165">Additional resources</span></span>

- <span data-ttu-id="2138e-166">**Azure Migrate 데이터 시트**</span><span class="sxs-lookup"><span data-stu-id="2138e-166">**Azure Migrate Datasheet**</span></span>

    <https://aka.ms/azuremigration\_datasheet>

- <span data-ttu-id="2138e-167">**Azure Migrate**</span><span class="sxs-lookup"><span data-stu-id="2138e-167">**Azure Migrate**</span></span>

    <https://aka.ms/azuremigrate>

- <span data-ttu-id="2138e-168">**Azure 마이그레이션 센터**</span><span class="sxs-lookup"><span data-stu-id="2138e-168">**Azure migration center**</span></span>

    <https://azure.microsoft.com/migration/>

- <span data-ttu-id="2138e-169">**Site Recovery를 사용 하 여 Azure로 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="2138e-169">**Migrate to Azure with Site Recovery**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-to-azure>

- <span data-ttu-id="2138e-170">**Azure Site Recovery 서비스 개요**</span><span class="sxs-lookup"><span data-stu-id="2138e-170">**Azure Site Recovery service overview**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-overview>

- <span data-ttu-id="2138e-171">**AWS의 Vm을 Azure Vm으로 마이그레이션**</span><span class="sxs-lookup"><span data-stu-id="2138e-171">**Migrating VMs in AWS to Azure VMs**</span></span>

    <https://docs.microsoft.com/azure/site-recovery/site-recovery-migrate-aws-to-azure>

>[!div class="step-by-step"]
><span data-ttu-id="2138e-172">[이전](index.md)
>[다음](migrate-your-relational-databases-to-azure.md)</span><span class="sxs-lookup"><span data-stu-id="2138e-172">[Previous](index.md)
[Next](migrate-your-relational-databases-to-azure.md)</span></span> <!-- Next Chapter -->
