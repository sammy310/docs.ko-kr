---
title: 컨테이너화된 애플리케이션 서비스 모니터링
description: 모니터링 컨테이너 아키텍처의 몇 가지 주요 측면에 알아봅니다.
ms.date: 02/15/2019
ms.openlocfilehash: e14553d510751d8a75020a1b6beb9fd7bc29596e
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65641210"
---
# <a name="monitor-containerized-application-services"></a><span data-ttu-id="1df13-103">컨테이너화된 애플리케이션 서비스 모니터링</span><span class="sxs-lookup"><span data-stu-id="1df13-103">Monitor containerized application services</span></span>

<span data-ttu-id="1df13-104">이 응용 프로그램 컨테이너 및 마이크로 서비스를 여러 분할을 모니터링 하 고 전체 응용 프로그램의 동작을 분석 하는 방법이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-104">It's critical for applications split into multiple containers and microservices to have a way to monitor and analyze the behavior of the whole application.</span></span>

## <a name="azure-monitor"></a><span data-ttu-id="1df13-105">Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="1df13-105">Azure Monitor</span></span>

<span data-ttu-id="1df13-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) 라이브 응용 프로그램을 모니터링 하는 확장 가능한 분석 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-106">[Azure Monitor](https://azure.microsoft.com/services/monitor/) is an extensible analytics service that monitors your live application.</span></span> <span data-ttu-id="1df13-107">성능 문제 감지 및 진단 하는 데 실제로 할 앱을 사용 하 여 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-107">It helps you to detect and diagnose performance issues and to understand what users actually do with your app.</span></span> <span data-ttu-id="1df13-108">지속적으로 성능을 향상 시킬 수 있도록 의도 및 서비스 또는 응용 프로그램의 사용 편의성을 사용 하 여 개발자를 위해 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-108">It's designed for developers, with the intent of helping you to continuously improve the performance and usability of your services or applications.</span></span> <span data-ttu-id="1df13-109">Azure Monitor는 다양 한 클라우드 또는.NET, Java, Node.js 및 기타 여러 플랫폼, 호스팅된 온-프레미스와 같은 플랫폼에서 앱을 웹/서비스와 독립 실행형을 사용 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-109">Azure Monitor works with both web/services and standalone apps on a wide variety of platforms like .NET, Java, Node.js and many other platforms, hosted on-premises or in the cloud.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="1df13-110">추가 자료</span><span class="sxs-lookup"><span data-stu-id="1df13-110">Additional resources</span></span>

- <span data-ttu-id="1df13-111">**Azure Monitor 개요** \\</span><span class="sxs-lookup"><span data-stu-id="1df13-111">**Overview of Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="1df13-112">**Application Insights란?**</span><span class="sxs-lookup"><span data-stu-id="1df13-112">**What is Application Insights?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="1df13-113">**Azure Monitor 메트릭 이란?**</span><span class="sxs-lookup"><span data-stu-id="1df13-113">**What is Azure Monitor Metrics?**</span></span> \
  <https://docs.microsoft.com/azure/azure-monitor/platform/data-platform-metrics>

- <span data-ttu-id="1df13-114">**Azure Monitor의 컨테이너 모니터링 솔루션** \\</span><span class="sxs-lookup"><span data-stu-id="1df13-114">**Container Monitoring solution in Azure Monitor** \\</span></span>
  <https://docs.microsoft.com/azure/azure-monitor/insights/containers>

## <a name="security-and-backup-services"></a><span data-ttu-id="1df13-115">보안 및 백업 서비스</span><span class="sxs-lookup"><span data-stu-id="1df13-115">Security and backup services</span></span>

<span data-ttu-id="1df13-116">많은 응용 프로그램 및 인프라는 비즈니스 요구를 지 원하는 최상의 조건에서 확인을 처리 해야 하는 세부 정보를 사용 하 여 여러 지원 작업 되며 상황이 더 복잡해 집니다 마이크로 서비스 영역에서는 해야 하는 방법 상위 수준 및 세부 보기를 될 하 여 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-116">There are many support chores with lots of details that you have to handle to ensure your applications and infrastructure are in top notch condition to support business needs, and the situation becomes more complicated in the microservices realm, so you need a way to have both high-level and detailed views when you need to take action.</span></span>

<span data-ttu-id="1df13-117">Azure를 통해 클라우드 및 온-프레미스 리소스의 네 가지 중요 한 측면의 통합된 보기를 제공 하는 도구에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-117">Azure has the tools to manage and provide a unified view of four critical aspects of both your cloud and on-premises resources:</span></span>

- <span data-ttu-id="1df13-118">**보안**합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-118">**Security**.</span></span> <span data-ttu-id="1df13-119">사용 하 여 [Azure Security Center](https://azure.microsoft.com/services/security-center/)합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-119">With [Azure Security Center](https://azure.microsoft.com/services/security-center/).</span></span>
  - <span data-ttu-id="1df13-120">완전 한 가시성과 제어권을 통해 virtual machines, 앱 및 워크 로드의 보안을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-120">Get full visibility and control over the security of your virtual machines, apps, and workloads.</span></span>
  - <span data-ttu-id="1df13-121">보안 정책의 관리를 중앙 집중화 하 고 기존 프로세스 및 도구를 통합 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-121">Centralize the management of your security policies and integrate existing processes and tools.</span></span>
  - <span data-ttu-id="1df13-122">고급 분석을 사용 하 여 실제 위협을 감지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-122">Detect real threats with advanced analytics.</span></span>

- <span data-ttu-id="1df13-123">**백업**합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-123">**Backup**.</span></span> <span data-ttu-id="1df13-124">사용 하 여 [Azure Backup](https://azure.microsoft.com/services/backup/)합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-124">With [Azure Backup](https://azure.microsoft.com/services/backup/).</span></span>
  - <span data-ttu-id="1df13-125">비용이 많이 드는 업무 중단을 방지 하 고 규정 준수 목표를 충족 랜 섬 웨어 및 사람의 오류 로부터 데이터를 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-125">Avoid costly business disruptions, meet compliance goals, and protect your data against ransomware and human errors.</span></span>
  - <span data-ttu-id="1df13-126">전송 중 및 미사용 시 암호화 된 백업 데이터를 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-126">Keep your backup data encrypted in transit and at rest.</span></span>
  - <span data-ttu-id="1df13-127">무단된 사용을 방지 하기 위해 다단계 인증을 기반으로 하는 액세스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-127">Ensure access based on multifactor authentication to prevent unauthorized use.</span></span>

- <span data-ttu-id="1df13-128">**온-프레미스 리소스**합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-128">**On-premises resources**.</span></span> <span data-ttu-id="1df13-129">사용 하 여 [일관 된 하이브리드 클라우드](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/)합니다.</span><span class="sxs-lookup"><span data-stu-id="1df13-129">With [a truly consistent hybrid cloud](https://azure.microsoft.com/resources/truly-consistent-hybrid-cloud-with-microsoft-azure/).</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="1df13-130">[이전](manage-production-docker-environments.md)
>[다음](../key-takeaways/index.md)</span><span class="sxs-lookup"><span data-stu-id="1df13-130">[Previous](manage-production-docker-environments.md)
[Next](../key-takeaways/index.md)</span></span>
