---
title: 모니터링 및 원격 분석을 사용하여 앱을 최신화
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 모니터링 및 원격 분석을 사용하여 앱을 최신화
ms.date: 04/30/2018
ms.openlocfilehash: cdd7738606b086e980c4a50348166a7e23e15fa5
ms.sourcegitcommit: 628e8147ca10187488e6407dab4c4e6ebe0cac47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/15/2019
ms.locfileid: "72318485"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="6cab9-103">모니터링 및 원격 분석을 사용하여 앱을 최신화</span><span class="sxs-lookup"><span data-stu-id="6cab9-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="6cab9-104">프로덕션 환경에서 응용 프로그램을 실행하는 경우 응용 프로그램 성능에 대한 통찰력이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="6cab9-105">높은 수준으로 실행되고 있읍니까?</span><span class="sxs-lookup"><span data-stu-id="6cab9-105">Is it performing at a high level?</span></span> <span data-ttu-id="6cab9-106">사용자에게 오류를 발생시키거나 아니면 안정적이고 신뢰할 수 있는 응용 프로그램입니까?</span><span class="sxs-lookup"><span data-stu-id="6cab9-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="6cab9-107">다양한 성능 모니터링과 강력한 알림, 대시보드가 있어야 응용 프로그램이 사용할 수 있고 기대한 대로 실행되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="6cab9-108">또한 문제가 있다면 신속하게 확인하여 얼마나 많은 고객이 영향을 받는지 확인하고, 문제를 찾아서 해결하기 위해 근본 원인을 분석하는 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="6cab9-109">Application Insights를 사용 하 여 응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="6cab9-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="6cab9-110">Application Insights는 여러 플랫폼에서 작업 하는 웹 개발자를 위한 확장 가능한 APM (응용 프로그램 성능 관리) 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="6cab9-111">라이브 웹 응용 프로그램을 모니터링 하는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="6cab9-112">Application Insights에서 성능 변칙을 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="6cab9-113">여기에는 문제를 진단 하 고 사용자가 앱에서 실제로 수행 하는 작업을 이해 하는 데 도움이 되는 강력한 분석 도구가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="6cab9-114">Application Insights은 지속적으로 성능과 유용성을 향상 시킬 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="6cab9-115">이는 온-프레미스 또는 클라우드에서 호스트 되는지에 관계 없이 .NET, node.js 및 J2EE를 비롯 한 다양 한 플랫폼에서 앱에 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="6cab9-116">Application Insights는 DevOps 프로세스와 통합 되며 다양 한 개발 도구에 대 한 연결 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="6cab9-117">그림 4-10에서는 응용 프로그램을 Application Insights 모니터링 하는 방법 및 해당 정보를 대시보드에 표시 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights 모니터링 대시보드의 스크린샷](./media/modernize-your-apps-with-monitoring-and-telemetry/application-insights-monitoring-dashboard.png)

<span data-ttu-id="6cab9-119">**그림 4-10.**</span><span class="sxs-lookup"><span data-stu-id="6cab9-119">**Figure 4-10.**</span></span> <span data-ttu-id="6cab9-120">Application Insights 모니터링 대시보드</span><span class="sxs-lookup"><span data-stu-id="6cab9-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="6cab9-121">Log Analytics 및 해당 컨테이너 모니터링 솔루션을 사용 하 여 Docker 인프라 모니터링</span><span class="sxs-lookup"><span data-stu-id="6cab9-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="6cab9-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) 는 [Microsoft Azure 전체 모니터링 솔루션](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="6cab9-123">[OMS (Operations Management Suite)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)의 서비스 이기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="6cab9-124">Log Analytics는 클라우드 및 온-프레미스 환경 (온-프레미스 용 OMS)을 모니터링 하 여 가용성과 성능을 유지 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="6cab9-125">클라우드 및 온-프레미스 환경에서 리소스에 의해 생성 된 데이터를 수집 하 고 다른 모니터링 도구를 통해 여러 원본에 걸쳐 분석을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="6cab9-126">Azure 인프라 로그와 관련 하 여 Azure 서비스로 Log Analytics, 다른 Azure 서비스 ( [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)를 통해), azure Vm, Docker 컨테이너, 온-프레미스 또는 기타 클라우드 인프라에서 로그 및 메트릭 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="6cab9-127">Log Analytics은이 데이터를 기반으로 하는 유연한 로그 검색 및 기본 제공 분석을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="6cab9-128">이 도구는 다양 한 원본에서 데이터를 분석 하는 데 사용할 수 있는 다양 한 도구를 제공 하며, 모든 로그에서 복잡 한 쿼리를 허용 하 고 지정 된 조건에 따라 사전에 경고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="6cab9-129">중앙 Log Analytics 리포지토리에서 사용자 지정 데이터를 수집 하 여 쿼리하고 시각화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="6cab9-130">또한 Log Analytics 기본 제공 솔루션을 활용 하 여 인프라의 보안 및 기능에 대 한 정보를 즉시 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="6cab9-131">모든 브라우저에서 실행 되는 OMS 포털 또는 Azure Portal를 통해 Log Analytics에 액세스할 수 있으며, 수집 된 데이터를 분석 하 고 작업 하는 구성 설정 및 여러 도구에 대 한 액세스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="6cab9-132">Log Analytics의 [컨테이너 모니터링 솔루션](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) 을 사용 하 여 단일 위치에서 Docker 및 Windows 컨테이너 호스트를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="6cab9-133">이 솔루션은 실행 중인 컨테이너, 실행 중인 컨테이너 이미지 및 컨테이너가 실행 되는 위치를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="6cab9-134">컨테이너에 사용 되는 명령을 포함 하 여 자세한 감사 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="6cab9-135">Docker 또는 Windows 호스트를 원격으로 볼 필요 없이 중앙 집중식 로그를 보고 검색 하 여 컨테이너 문제를 해결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="6cab9-136">잡음이 있을 수 있으며 호스트에서 초과 리소스를 소비 하는 컨테이너를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="6cab9-137">또한 컨테이너에 대해 중앙 집중식 CPU, 메모리, 저장소, 네트워크 사용량 및 성능 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="6cab9-138">Windows를 실행 하는 컴퓨터에서 Windows Server, Hyper-v 및 Docker 컨테이너의 로그를 중앙 집중화 하 고 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="6cab9-139">이 솔루션은 다음 컨테이너 orchestrator 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="6cab9-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="6cab9-140">Docker Swarm</span></span>

- <span data-ttu-id="6cab9-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="6cab9-141">DC/OS</span></span>

- <span data-ttu-id="6cab9-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="6cab9-142">Kubernetes</span></span>

- <span data-ttu-id="6cab9-143">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="6cab9-143">Red Hat OpenShift</span></span>

<span data-ttu-id="6cab9-144">그림 4-11은 다양 한 컨테이너 호스트와 에이전트 및 OMS 간의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-144">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Log Analytics 컨테이너 모니터링 솔루션의 스크린샷](./media/modernize-your-apps-with-monitoring-and-telemetry/log-analytics-container-monitoring-solution.png)

<span data-ttu-id="6cab9-146">**그림 4-11.**</span><span class="sxs-lookup"><span data-stu-id="6cab9-146">**Figure 4-11.**</span></span> <span data-ttu-id="6cab9-147">Log Analytics 컨테이너 모니터링 솔루션</span><span class="sxs-lookup"><span data-stu-id="6cab9-147">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="6cab9-148">Log Analytics 컨테이너 모니터링 솔루션을 사용 하 여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-148">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="6cab9-149">단일 위치의 모든 컨테이너 호스트에 대 한 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6cab9-149">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="6cab9-150">실행 중인 컨테이너, 실행 중인 이미지 및 실행 중인 위치를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-150">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="6cab9-151">컨테이너에 대 한 작업에 대 한 감사 내역을 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="6cab9-151">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="6cab9-152">Docker 호스트에 대 한 원격 로그인 없이 중앙 집중식 로그를 보고 검색 하 여 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-152">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="6cab9-153">"잡음이 있는 환경"이 될 수 있는 컨테이너를 찾고 호스트에서 리소스를 과도 하 게 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-153">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="6cab9-154">컨테이너에 대 한 중앙 집중식 CPU, 메모리, 저장소, 네트워크 사용량 및 성능 정보를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6cab9-154">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="6cab9-155">추가 자료</span><span class="sxs-lookup"><span data-stu-id="6cab9-155">Additional resources</span></span>

- <span data-ttu-id="6cab9-156">**Microsoft Azure의 모니터링 개요**</span><span class="sxs-lookup"><span data-stu-id="6cab9-156">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="6cab9-157">**Application Insights란?**</span><span class="sxs-lookup"><span data-stu-id="6cab9-157">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="6cab9-158">**Log Analytics 이란?**</span><span class="sxs-lookup"><span data-stu-id="6cab9-158">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="6cab9-159">**Azure Monitor의 컨테이너 모니터링 솔루션**</span><span class="sxs-lookup"><span data-stu-id="6cab9-159">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="6cab9-160">**Azure Monitor 개요**</span><span class="sxs-lookup"><span data-stu-id="6cab9-160">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="6cab9-161">**OMS (Operations Management Suite) 란?**</span><span class="sxs-lookup"><span data-stu-id="6cab9-161">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
><span data-ttu-id="6cab9-162">[이전](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[다음](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="6cab9-162">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>
