---
title: 컨테이너화된 애플리케이션 서비스 모니터링
description: 컨테이너 아키텍처 모니터링의 주요 특징을 알아봅니다.
ms.date: 02/15/2019
ms.openlocfilehash: e14553d510751d8a75020a1b6beb9fd7bc29596e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "68673460"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="7477a-103">컨테이너화된 애플리케이션 서비스 모니터링</span><span class="sxs-lookup"><span data-stu-id="7477a-103">Monitor containerized application services</span></span>

<span data-ttu-id="7477a-104">여러 컨테이너와 마이크로서비스로 분할된 애플리케이션은 전체 애플리케이션의 동작을 모니터링하고 분석할 수 있는 방법이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="7477a-105">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="7477a-105">Azure Monitor</span></span>

<span data-ttu-id="7477a-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/)는 라이브 애플리케이션을 모니터링하는 확장 가능한 분석 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="7477a-107">이 서비스를 사용하면 성능 이슈를 감지하고 진단하여 사용자가 실제로 앱에서 무엇을 하는지 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="7477a-108">이 서비스는 개발자가 서비스 또는 애플리케이션의 성능과 사용 편의성을 지속적으로 개선할 수 있도록 도와줄 의도로 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="7477a-109">Azure Monitor는 .NET, Java, Node.js, 온-프레미스 또는 클라우드에 호스트되는 다른 여러 플랫폼을 비롯한 다양한 플랫폼에서 웹/서비스 및 독립 실행형 앱과 함께 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="7477a-110">추가 자료</span><span class="sxs-lookup"><span data-stu-id="7477a-110">Additional resources</span></span>

- <span data-ttu-id="7477a-111">**Azure Monitor 개요** </span><span class="sxs-lookup"><span data-stu-id="7477a-111">**Overview of Azure Monitor** </span></span>\
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="7477a-112">**Application Insights란?**</span><span class="sxs-lookup"><span data-stu-id="7477a-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="7477a-113">**Azure Monitor 메트릭이란?**</span><span class="sxs-lookup"><span data-stu-id="7477a-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="7477a-114">**Azure Monitor의 컨테이너 모니터링 솔루션** </span><span class="sxs-lookup"><span data-stu-id="7477a-114">**Container Monitoring solution in Azure Monitor** </span></span>\
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="7477a-115">서비스 보안 및 백업</span><span class="sxs-lookup"><span data-stu-id="7477a-115">Security and backup services</span></span>

<span data-ttu-id="7477a-116">애플리케이션 및 인프라가 비즈니스 요구 사항을 지원하도록 최상의 상태를 유지하려면 여러 가지 지원 업무를 처리해야 하며, 마이크로서비스 영역에서는 상황이 점점 복잡해지고 있습니다. 따라서 조치를 취해야 할 때 상위 수준 보기와 세부 정보 보기를 모두 사용할 수 있는 방법이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="7477a-117">Azure 도구는 클라우드 리소스와 온-프레미스 리소스의 네 가지 중요한 측면을 관리하고 살펴볼 수 있는 통합 보기를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="7477a-118">**보안**.</span><span class="sxs-lookup"><span data-stu-id="7477a-118">**Security**.</span></span> <span data-ttu-id="7477a-119">[Azure Security Center](https://azure.microsoft.com/services/security-center/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="7477a-120">가상 머신, 앱 및 워크로드의 보안을 완벽하게 살펴보고 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="7477a-121">보안 정책 관리를 중앙 집중화하고 기존 프로세스 및 도구를 통합합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="7477a-122">고급 분석을 사용하여 실제 위협을 감지합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="7477a-123">**백업**.</span><span class="sxs-lookup"><span data-stu-id="7477a-123">**Backup**.</span></span> <span data-ttu-id="7477a-124">[Azure Backup](https://azure.microsoft.com/services/backup/)을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="7477a-125">많은 비용이 발생하는 업무 중단을 방지하고, 규정 준수 목표를 충족하고, 랜섬웨어 및 사람의 오류로부터 데이터를 보호합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="7477a-126">전송 및 저장 시 백업 데이터의 암호화를 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="7477a-127">다단계 인증을 기반으로 액세스 권한을 부여하여 단 사용을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="7477a-128">**온-프레미스 리소스**.</span><span class="sxs-lookup"><span data-stu-id="7477a-128">**On-premises resources**.</span></span> <span data-ttu-id="7477a-129">[진정으로 일관적인 하이브리드 클라우드](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/)를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7477a-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="7477a-130">[이전](manage-production-docker-environments.md)
>[다음](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="7477a-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
