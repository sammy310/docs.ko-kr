---
title: 하이브리드 클라우드로 마이그레이션 시나리오
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 하이브리드 클라우드 시나리오로 마이그레이션
ms.date: 04/30/2018
ms.openlocfilehash: dcbb799a45609f8bb811866c4041951abf1fda8b
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937369"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="002c4-103">하이브리드 클라우드로 마이그레이션 시나리오</span><span class="sxs-lookup"><span data-stu-id="002c4-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="002c4-104">일부 조직 및 기업은 규정 또는 자체 정책으로 인해 일부 애플리케이션을 Microsoft Azure와 같은 공용 클라우드로 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="002c4-105">그러나 모든 조직은 일부 애플리케이션을 공용 클라우드에 배치하고 다른 애플리케이션을 온-프레미스에 배치하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="002c4-106">다만 혼합 환경에서는 공용 클라우드와 온-프레미스 환경에 사용되는 다양한 플랫폼 및 기술로 인해 환경에서 과도한 복잡성이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="002c4-107">Microsoft는 Azure 하이브리드 클라우드에서 일관성을 유지하면서 기존 자산을 온-프레미스 및 공용 클라우드에서 최적화할 수 있는 최상의 하이브리드 클라우드 솔루션을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="002c4-108">Azure Stack(온-프레미스) 및 Azure(공용 클라우드) 덕분에 기존 역량을 극대화하고 클라우드 또는 온-프레미스에서 실행할 수 있는 앱을 빌드하는 유연하고 통합된 접근 방식을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="002c4-109">보안과 관련하여 하이브리드 클라우드를 통해 관리 및 보안을 중앙 집중화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="002c4-110">온-프레미스 및 클라우드 앱에 대한 Single Sign-On을 제공하여 데이터 센터에서 클라우드까지 모든 자산에 대한 제어를 확보할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="002c4-111">이는 Active Directory를 하이브리드 클라우드로 확장하고 ID 관리를 사용하여 달성합니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="002c4-112">마지막으로, 데이터를 원활하게 배포 및 분석하고, 클라우드 및 온-프레미스 자산에 대해 동일한 쿼리 언어를 사용하고, Azure에서 분석 및 딥 러닝을 적용하여 원본에 관계없이 데이터를 보강할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="002c4-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="002c4-113">Azure Stack</span></span>

<span data-ttu-id="002c4-114">Azure Stack은 조직의 데이터 센터에서 Azure 서비스를 제공할 수 있게 해주는 하이브리드 클라우드 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="002c4-115">Azure Stack은 에지 및 연결되지 않은 환경과 같은 주요 시나리오에서 최신 애플리케이션에 대한 새로운 옵션을 지원하거나 특정 보안 및 규정 준수 요구 사항을 충족하도록 디자인되었습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="002c4-116">그림 4-13에서는 Microsoft가 제공하는 진정한 하이브리드 클라우드 플랫폼에 대한 개요를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Azure Stack과 Azure를 사용하는 Microsoft 하이브리드 클라우드 플랫폼의 다이어그램](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="002c4-118">**그림 4-13.**</span><span class="sxs-lookup"><span data-stu-id="002c4-118">**Figure 4-13.**</span></span> <span data-ttu-id="002c4-119">Azure Stack 및 Azure를 사용하는 Microsoft 하이브리드 클라우드 플랫폼</span><span class="sxs-lookup"><span data-stu-id="002c4-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="002c4-120">Azure Stack은 사용자 요구 사항을 충족하기 위해 두 가지 배포 옵션으로 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="002c4-121">Azure Stack 통합 시스템</span><span class="sxs-lookup"><span data-stu-id="002c4-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="002c4-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="002c4-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="002c4-123">Azure Stack 통합 시스템</span><span class="sxs-lookup"><span data-stu-id="002c4-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="002c4-124">Azure Stack 통합 시스템은 Microsoft와 하드웨어 파트너 간 파트너 관계를 통해 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="002c4-125">이 파트너 관계는 관리 단순성과 균형을 이루는 클라우드 지향 혁신을 제공하는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="002c4-126">Azure Stack은 하드웨어와 소프트웨어의 통합 시스템으로 제공되므로 클라우드의 혁신을 채택하면서도 필요한 만큼의 제어 기능을 유연하게 이용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="002c4-127">Azure Stack 통합 시스템은 4~12개 노드를 포함하며 하드웨어 파트너와 Microsoft를 통해 공동으로 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="002c4-128">프로덕션 워크로드용으로 새로운 시나리오를 구현하려면 Azure Stack 통합 시스템을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="002c4-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="002c4-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="002c4-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="002c4-130">Microsoft Azure Stack Development Kit는 Azure Stack을 평가하고 학습하는 데 사용할 수 있는 Azure Stack의 단일 노드 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="002c4-131">Azure Stack Development Kit를 개발자 환경으로 활용해 Azure와 동일한 API와 도구를 사용하여 개발 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="002c4-132">Azure Stack Development Kit는 프로덕션 환경으로 사용하기 위한 도구가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="002c4-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="002c4-133">추가 자료</span><span class="sxs-lookup"><span data-stu-id="002c4-133">Additional resources</span></span>

- <span data-ttu-id="002c4-134">**Azure 하이브리드 클라우드**</span><span class="sxs-lookup"><span data-stu-id="002c4-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="002c4-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="002c4-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="002c4-136">**Windows 컨테이너용 Active Directory 서비스 계정**</span><span class="sxs-lookup"><span data-stu-id="002c4-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="002c4-137">**Active Directory 지원으로 컨테이너 만들기**</span><span class="sxs-lookup"><span data-stu-id="002c4-137">**Create a container with Active Directory support**</span></span>

    <https://docs.microsoft.com/archive/blogs/containerstuff/create-a-container-with-active-directory-support>

- <span data-ttu-id="002c4-138">**Azure 하이브리드 혜택 라이선스**</span><span class="sxs-lookup"><span data-stu-id="002c4-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="002c4-139">[이전](life-cycle-ci-cd-pipelines-devops-tools.md)
>[다음](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="002c4-139">[Previous](life-cycle-ci-cd-pipelines-devops-tools.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
