---
title: 하이브리드 클라우드로 마이그레이션 시나리오
description: Azure 클라우드 및 Windows 컨테이너를 사용 하 여 기존 .NET 응용 프로그램 현대화 | 하이브리드 클라우드 시나리오로 마이그레이션
ms.date: 04/30/2018
ms.openlocfilehash: 4348a9b538042fee7ebd9c08f480491f17425937
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394541"
---
# <a name="migrate-to-hybrid-cloud-scenarios"></a><span data-ttu-id="1609e-103">하이브리드 클라우드로 마이그레이션 시나리오</span><span class="sxs-lookup"><span data-stu-id="1609e-103">Migrate to hybrid cloud scenarios</span></span>

<span data-ttu-id="1609e-104">일부 조직 및 기업은 규정 또는 자체 정책으로 인해 일부 응용 프로그램을 Microsoft Azure 또는 다른 공용 클라우드와 같은 공용 클라우드로 마이그레이션할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-104">Some organizations and enterprises can't migrate some of their applications to public clouds like Microsoft Azure or any other public cloud due to regulations or their own policies.</span></span> <span data-ttu-id="1609e-105">그러나 조직에서 일부 응용 프로그램을 공용 클라우드 및 다른 응용 프로그램에 온-프레미스에 배치 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-105">However, it's likely that any organization might benefit from having some of their applications in the public cloud and other applications on-premises.</span></span> <span data-ttu-id="1609e-106">그러나 혼합 환경에서는 공용 클라우드와 온-프레미스 환경에 사용 되는 다양 한 플랫폼 및 기술로 인해 환경에서 과도 한 복잡성이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-106">But a mixed environment can lead to excessive complexity in environments due to different platforms and technologies used in public clouds versus on-premises environments.</span></span>

<span data-ttu-id="1609e-107">Microsoft는 Azure 하이브리드 클라우드에서 일관성을 유지 하면서 기존 자산을 온-프레미스 및 공용 클라우드에서 최적화할 수 있는 최상의 하이브리드 클라우드 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-107">Microsoft provides the best hybrid cloud solution, one in which you can optimize your existing assets on-premises and in the public cloud, while you ensure consistency in an Azure hybrid cloud.</span></span> <span data-ttu-id="1609e-108">기존 기술을 최대화 하 고 클라우드 또는 온-프레미스에서 실행할 수 있는 앱을 빌드하는 데 Azure Stack (온-프레미스) 및 Azure (공용 클라우드)를 사용 하 여 유연 하 고 통합 된 접근 방식을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-108">You can maximize existing skills, and get a flexible, unified approach to building apps that can run in the cloud or on-premises, thanks to Azure Stack (on-premises) and Azure (public cloud).</span></span>

<span data-ttu-id="1609e-109">보안과 관련 하 여 하이브리드 클라우드를 통해 관리 및 보안을 중앙 집중화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-109">When it comes to security, you can centralize management and security across your hybrid cloud.</span></span> <span data-ttu-id="1609e-110">온-프레미스 및 클라우드 앱에 대 한 Single Sign-On 제공 하 여 데이터 센터에서 클라우드로 모든 자산에 대 한 제어를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-110">You can get control over all assets, from your datacenter to the cloud, by providing single sign-on to on-premises and cloud apps.</span></span> <span data-ttu-id="1609e-111">하이브리드 클라우드로 Active Directory를 확장 하 고 id 관리를 사용 하 여이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-111">You accomplish this by extending Active Directory to a hybrid cloud, and by using identity management.</span></span>

<span data-ttu-id="1609e-112">마지막으로, 데이터를 원활 하 게 배포 및 분석 하 고, 클라우드 및 온-프레미스 자산에 대해 동일한 쿼리 언어를 사용 하 고, Azure에서 분석 및 심층 학습을 적용 하 여 원본에 관계 없이 데이터를 보강 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-112">Finally, you can distribute and analyze data seamlessly, use the same query languages for cloud and on-premises assets, and apply analytics and deep learning in Azure to enrich your data, regardless of its source.</span></span>

## <a name="azure-stack"></a><span data-ttu-id="1609e-113">Azure Stack</span><span class="sxs-lookup"><span data-stu-id="1609e-113">Azure Stack</span></span>

<span data-ttu-id="1609e-114">Azure Stack는 조직의 데이터 센터에서 Azure 서비스를 제공할 수 있도록 하는 하이브리드 클라우드 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-114">Azure Stack is a hybrid cloud platform that lets you deliver Azure services from your organization's datacenter.</span></span> <span data-ttu-id="1609e-115">Azure Stack는 edge 및 연결 되지 않은 환경과 같은 주요 시나리오에서 최신 응용 프로그램에 대 한 새로운 옵션을 지원 하거나 특정 보안 및 규정 준수 요구 사항을 충족 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-115">Azure Stack is designed to support new options for your modern applications in key scenarios, like edge and unconnected environments, or meeting specific security and compliance requirements.</span></span>

<span data-ttu-id="1609e-116">그림 4-13은 Microsoft에서 제공 하는 진정한 하이브리드 클라우드 플랫폼에 대 한 개요를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-116">Figure 4-13 shows an overview of the true hybrid cloud platform that Microsoft offers.</span></span>

![Azure Stack 및 Azure를 사용 하는 Microsoft 하이브리드 클라우드 플랫폼의 다이어그램입니다.](./media/migrate-to-hybrid-cloud-scenarios/microsoft-hybrid-cloud-platform.png)

<span data-ttu-id="1609e-118">**그림 4-13.**</span><span class="sxs-lookup"><span data-stu-id="1609e-118">**Figure 4-13.**</span></span> <span data-ttu-id="1609e-119">Azure Stack 및 Azure를 사용 하는 Microsoft 하이브리드 클라우드 플랫폼</span><span class="sxs-lookup"><span data-stu-id="1609e-119">Microsoft hybrid cloud platform with Azure Stack and Azure</span></span>

<span data-ttu-id="1609e-120">Azure Stack는 요구 사항을 충족 하기 위해 두 가지 배포 옵션으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-120">Azure Stack is offered in two deployment options, to meet your needs:</span></span>

- <span data-ttu-id="1609e-121">Azure Stack 통합 시스템</span><span class="sxs-lookup"><span data-stu-id="1609e-121">Azure Stack integrated systems</span></span>

- <span data-ttu-id="1609e-122">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="1609e-122">Azure Stack Development Kit</span></span>

### <a name="azure-stack-integrated-systems"></a><span data-ttu-id="1609e-123">Azure Stack 통합 시스템</span><span class="sxs-lookup"><span data-stu-id="1609e-123">Azure Stack integrated systems</span></span>

<span data-ttu-id="1609e-124">Azure Stack 통합 시스템은 Microsoft 및 하드웨어 파트너의 파트너 관계를 통해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-124">Azure Stack integrated systems are offered through a partnership of Microsoft and hardware partners.</span></span> <span data-ttu-id="1609e-125">파트너 관계는 관리의 단순성에 맞춰 조정 되는 클라우드 지향 혁신을 제공 하는 솔루션을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-125">The partnership creates a solution that offers cloud-paced innovation that is balanced with simplicity in management.</span></span> <span data-ttu-id="1609e-126">Azure Stack는 하드웨어 및 소프트웨어의 통합 시스템으로 제공 되므로 클라우드의 혁신을 채택 하면서도 유연 하 고 유연 하 게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-126">Because Azure Stack is offered as an integrated system of hardware and software, you get the right amount of flexibility and control, while still adopting innovation from the cloud.</span></span> <span data-ttu-id="1609e-127">Azure Stack 통합 시스템의 크기는 4 개에서 12 개 사이의 노드 이며 하드웨어 파트너와 Microsoft에서 공동으로 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-127">Azure Stack integrated systems range in size from 4 to 12 nodes, and are jointly supported by the hardware partner and Microsoft.</span></span> <span data-ttu-id="1609e-128">Azure Stack 통합 시스템을 사용 하 여 프로덕션 워크 로드에 대 한 새 시나리오를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-128">Use Azure Stack integrated systems to implement new scenarios for your production workloads.</span></span>

### <a name="azure-stack-development-kit"></a><span data-ttu-id="1609e-129">Azure Stack Development Kit</span><span class="sxs-lookup"><span data-stu-id="1609e-129">Azure Stack Development Kit</span></span>

<span data-ttu-id="1609e-130">Microsoft Azure Stack Development Kit는 Azure Stack을 평가 하 고 학습 하는 데 사용할 수 있는 Azure Stack의 단일 노드 배포입니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-130">Microsoft Azure Stack Development Kit is a single-node deployment of Azure Stack, which you can use to evaluate and learn about Azure Stack.</span></span> <span data-ttu-id="1609e-131">Azure와 일치 하는 Api 및 도구를 사용 하 여 개발할 수 있는 개발자 환경으로 Azure Stack Development Kit를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-131">You can also use Azure Stack Development Kit as a developer environment, where you can develop using APIs and tooling that are consistent with Azure.</span></span> <span data-ttu-id="1609e-132">Azure Stack Development Kit은 프로덕션 환경으로 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1609e-132">Azure Stack Development Kit is not intended to be used as a production environment.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1609e-133">추가 자료</span><span class="sxs-lookup"><span data-stu-id="1609e-133">Additional resources</span></span>

- <span data-ttu-id="1609e-134">**Azure 하이브리드 클라우드**</span><span class="sxs-lookup"><span data-stu-id="1609e-134">**Azure hybrid cloud**</span></span>

    <https://azure.microsoft.com/overview/hybrid-cloud/>

- <span data-ttu-id="1609e-135">**Azure Stack**</span><span class="sxs-lookup"><span data-stu-id="1609e-135">**Azure Stack**</span></span>

    <https://azure.microsoft.com/overview/azure-stack/>

- <span data-ttu-id="1609e-136">**Windows 컨테이너에 대 한 Active Directory 서비스 계정**</span><span class="sxs-lookup"><span data-stu-id="1609e-136">**Active Directory Service Accounts for Windows Containers**</span></span>

    <https://docs.microsoft.com/virtualization/windowscontainers/manage-containers/manage-serviceaccounts>

- <span data-ttu-id="1609e-137">**Active Directory 지원으로 컨테이너 만들기**</span><span class="sxs-lookup"><span data-stu-id="1609e-137">**Create a container with Active Directory support**</span></span>

    <https://blogs.msdn.microsoft.com/containerstuff/2017/01/30/create-a-container-with-active-directory-support/>

- <span data-ttu-id="1609e-138">**Azure 하이브리드 혜택 라이선스**</span><span class="sxs-lookup"><span data-stu-id="1609e-138">**Azure Hybrid Benefit licensing**</span></span>

    <https://azure.microsoft.com/pricing/hybrid-benefit/>

>[!div class="step-by-step"]
><span data-ttu-id="1609e-139">[이전](life-cycle-ci-cd-pipelines-devops-tools.md)
>[다음](../walkthroughs-technical-get-started-overview.md)</span><span class="sxs-lookup"><span data-stu-id="1609e-139">[Previous](life-cycle-ci-cd-pipelines-devops-tools.md)
[Next](../walkthroughs-technical-get-started-overview.md)</span></span>
