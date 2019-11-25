---
title: 모니터링 및 원격 분석을 사용하여 앱 현대화
description: Azure Cloud 및 Windows 컨테이너를 사용하여 기존 .NET 애플리케이션 현대화 | 모니터링 및 원격 분석을 사용하여 앱 현대화
ms.date: 04/30/2018
ms.openlocfilehash: 3d629e89a73c870d4b6396c6b1d0ecbe95b79ead
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/08/2019
ms.locfileid: "72393847"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="4be12-103">모니터링 및 원격 분석을 사용하여 앱 현대화</span><span class="sxs-lookup"><span data-stu-id="4be12-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="4be12-104">프로덕션 환경에서 애플리케이션을 실행하는 경우 애플리케이션 작동 방식에 대한 정보를 파악하는 것이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="4be12-105">애플리케이션이 상위 수준에서 실행되나요?</span><span class="sxs-lookup"><span data-stu-id="4be12-105">Is it performing at a high level?</span></span> <span data-ttu-id="4be12-106">애플리케이션이 안정적이고 신뢰할 수 있나요, 아니면 사용자에게 오류가 발생하나요?</span><span class="sxs-lookup"><span data-stu-id="4be12-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="4be12-107">애플리케이션을 사용할 수 있고 예상대로 작동하는지 확인하는 데 도움이 되는 다양한 성능 모니터링, 강력한 경고 및 대시보드가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="4be12-108">또한 문제가 있는지 신속하게 확인하고, 얼마나 많은 고객이 영향을 받는지 확인하고, 근본 원인 분석을 수행하여 문제를 찾고 해결할 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="4be12-109">Application Insights를 사용하여 애플리케이션 모니터링</span><span class="sxs-lookup"><span data-stu-id="4be12-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="4be12-110">Application Insights는 여러 플랫폼에서 작업하는 웹 개발자를 위한 확장 가능한 APM(애플리케이션 성능 관리) 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="4be12-111">이를 사용하여 라이브 웹 애플리케이션을 모니터링합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="4be12-112">Application Insights는 자동으로 성능 이상을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="4be12-113">문제를 진단하고 사용자들이 앱을 사용하여 실제로 수행할 작업을 이해할 수 있도록 돕는 강력한 분석 도구를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="4be12-114">Application Insights는 성능 및 유용성을 지속적으로 향상시킬 수 있도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="4be12-115">온-프레미스 또는 클라우드에서 호스팅되는지 여부에 관계없이 .NET, Node.js 및 J2EE를 포함하여 다양한 플랫폼의 응용 프로그램에서 작동합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="4be12-116">Application Insights는 DevOps 프로세스와 통합되며, 다양한 개발 도구와의 연결 지점을 갖고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="4be12-117">그림 4-10에서는 Application Insights가 애플리케이션을 모니터링하는 방법과 해당 인사이트를 대시보드에 표시하는 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights 모니터링 대시보드의 스크린샷](./media/modernize-your-apps-with-monitoring-and-telemetry/application-insights-monitoring-dashboard.png)

<span data-ttu-id="4be12-119">**그림 4-10.**</span><span class="sxs-lookup"><span data-stu-id="4be12-119">**Figure 4-10.**</span></span> <span data-ttu-id="4be12-120">Application Insights 모니터링 대시보드</span><span class="sxs-lookup"><span data-stu-id="4be12-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="4be12-121">Log Analytics 및 해당 컨테이너 모니터링 솔루션을 사용하여 Docker 인프라 모니터링</span><span class="sxs-lookup"><span data-stu-id="4be12-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="4be12-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview)는 [Microsoft Azure 전체 모니터링 솔루션](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="4be12-123">또한 [OMS(Operations Management Suite)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)의 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="4be12-124">Log Analytics는 클라우드 및 온-프레미스 환경(온-프레미스용 OMS)을 모니터링하여 가용성과 성능을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="4be12-125">이 서비스는 클라우드 및 온-프레미스 환경에서 리소스에 의해 생성되고 여러 원본에 대한 분석을 제공하는 다른 모니터링 도구에서 생성된 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="4be12-126">Azure 인프라 로그와 관련하여, Log Analytics는 Azure 서비스로서 다른 Azure 서비스([Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)를 통해), Azure VM, Docker 컨테이너 및 온-프레미스 또는 기타 클라우드 인프라에서 로그 및 메트릭 데이터를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="4be12-127">Log Analytics는 이 데이터를 기반으로 하는 유연한 로그 검색과 기본 분석을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="4be12-128">소스에서 데이터를 분석하는 데 사용할 수 있는 다양한 도구를 제공하고, 모든 로그에서 복잡한 쿼리를 허용하며, 지정된 조건을 기반으로 사전에 경고할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="4be12-129">중앙 Log Analytics 리포지토리에서 사용자 지정 데이터를 수집하여 쿼리하고 시각화할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="4be12-130">또한 Log Analytics의 기본 제공 솔루션을 활용하여 인프라의 보안 및 기능을 즉시 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="4be12-131">수집된 데이터를 분석 및 조작하기 위해 모든 브라우저에서 실행되고 구성 설정 및 여러 도구에 대한 액세스를 제공하는 OMS 포털 또는 Azure Portal을 통해 Log Analytics에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="4be12-132">Log Analytics의 [컨테이너 모니터링 솔루션](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers)을 사용하여 단일 위치에서 Docker 및 Windows 컨테이너 호스트를 보고 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="4be12-133">솔루션은 어떤 컨테이너가 실행 중인지, 실행 중인 컨테이너 이미지 및 컨테이너가 실행 중인 위치를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="4be12-134">컨테이너에 사용되는 명령을 포함하여 자세한 감사 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="4be12-135">또한 중앙화된 로그를 보고 검색하면 원격으로 Docker 또는 Windows 호스트를 보지 않고도 컨테이너의 문제를 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="4be12-136">호스트에서 방해가 되고 과도한 리소스를 사용하는 컨테이너를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="4be12-137">또한 컨테이너에 대해 중앙화된 CPU 메모리, 스토리지, 네트워크 사용 및 성능 정보를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="4be12-138">Windows를 실행하는 컴퓨터에서 Windows Server, Hyper-V, Docker 컨테이너에서 로그를 중앙 집중화 및 비교할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="4be12-139">솔루션은 다음과 같은 컨테이너 오케스트레이터를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="4be12-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="4be12-140">Docker Swarm</span></span>

- <span data-ttu-id="4be12-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="4be12-141">DC/OS</span></span>

- <span data-ttu-id="4be12-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="4be12-142">Kubernetes</span></span>

- <span data-ttu-id="4be12-143">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="4be12-143">Red Hat OpenShift</span></span>

<span data-ttu-id="4be12-144">그림 4-11에서는 다양한 컨테이너 호스트와 에이전트 및 OMS 간의 관계를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-144">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Log Analytics 컨테이너 모니터링 솔루션의 스크린샷](./media/modernize-your-apps-with-monitoring-and-telemetry/log-analytics-container-monitoring-solution.png)

<span data-ttu-id="4be12-146">**그림 4-11.**</span><span class="sxs-lookup"><span data-stu-id="4be12-146">**Figure 4-11.**</span></span> <span data-ttu-id="4be12-147">Log Analytics 컨테이너 모니터링 솔루션</span><span class="sxs-lookup"><span data-stu-id="4be12-147">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="4be12-148">Log Analytics 컨테이너 모니터링 솔루션을 다음과 같이 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4be12-148">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="4be12-149">단일 위치의 모든 컨테이너 호스트에 대한 정보를 확인</span><span class="sxs-lookup"><span data-stu-id="4be12-149">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="4be12-150">실행 중인 컨테이너, 실행 중인 이미지 및 실행 중인 위치를 확인</span><span class="sxs-lookup"><span data-stu-id="4be12-150">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="4be12-151">컨테이너에 대한 작업 감사 내역을 확인</span><span class="sxs-lookup"><span data-stu-id="4be12-151">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="4be12-152">Docker 호스트에 원격 로그인하지 않고 중앙 집중식 로그를 보고 검색하여 문제 해결</span><span class="sxs-lookup"><span data-stu-id="4be12-152">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="4be12-153">호스트에서 “방해가 되고” 과도한 리소스를 소모하는 컨테이너를 검색</span><span class="sxs-lookup"><span data-stu-id="4be12-153">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="4be12-154">컨테이너에 대한 CPU 메모리, 저장소, 네트워크 사용 및 성능 정보를 중앙 집중식으로 확인</span><span class="sxs-lookup"><span data-stu-id="4be12-154">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="4be12-155">추가 자료</span><span class="sxs-lookup"><span data-stu-id="4be12-155">Additional resources</span></span>

- <span data-ttu-id="4be12-156">**Microsoft Azure 모니터링 개요**</span><span class="sxs-lookup"><span data-stu-id="4be12-156">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="4be12-157">**Application Insights란?**</span><span class="sxs-lookup"><span data-stu-id="4be12-157">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="4be12-158">**Log Analytics란?**</span><span class="sxs-lookup"><span data-stu-id="4be12-158">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="4be12-159">**Azure Monitor의 컨테이너 모니터링 솔루션**</span><span class="sxs-lookup"><span data-stu-id="4be12-159">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="4be12-160">**Azure Monitor 개요**</span><span class="sxs-lookup"><span data-stu-id="4be12-160">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="4be12-161">**OMS(Operations Management Suite)란?**</span><span class="sxs-lookup"><span data-stu-id="4be12-161">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

>[!div class="step-by-step"]
><span data-ttu-id="4be12-162">[이전](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[다음](life-cycle-ci-cd-pipelines-devops-tools.md)</span><span class="sxs-lookup"><span data-stu-id="4be12-162">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](life-cycle-ci-cd-pipelines-devops-tools.md)</span></span>
