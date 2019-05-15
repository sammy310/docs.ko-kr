---
title: 모니터링 및 원격 분석을 사용하여 앱을 최신화
description: Azure 클라우드와 Windows 컨테이너를 사용하여 기존 .NET 응용 프로그램 최신화 | 모니터링 및 원격 분석을 사용하여 앱을 최신화
ms.date: 04/30/2018
ms.openlocfilehash: 94196365e6ed93839b28ed3b375e75a9119ae12d
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65643685"
---
# <a name="modernize-your-apps-with-monitoring-and-telemetry"></a><span data-ttu-id="44e87-103">모니터링 및 원격 분석을 사용하여 앱을 최신화</span><span class="sxs-lookup"><span data-stu-id="44e87-103">Modernize your apps with monitoring and telemetry</span></span>

<span data-ttu-id="44e87-104">프로덕션 환경에서 응용 프로그램을 실행하는 경우 응용 프로그램 성능에 대한 통찰력이 중요합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-104">When you run an application in production, it's critical that you have insights about how your application is performing.</span></span> <span data-ttu-id="44e87-105">높은 수준으로 실행되고 있읍니까?</span><span class="sxs-lookup"><span data-stu-id="44e87-105">Is it performing at a high level?</span></span> <span data-ttu-id="44e87-106">사용자에게 오류를 발생시키거나 아니면 안정적이고 신뢰할 수 있는 응용 프로그램입니까?</span><span class="sxs-lookup"><span data-stu-id="44e87-106">Are users getting errors, or is the application stable and reliable?</span></span> <span data-ttu-id="44e87-107">다양한 성능 모니터링과 강력한 알림, 대시보드가 있어야 응용 프로그램이 사용할 수 있고 기대한 대로 실행되는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-107">You need rich performance monitoring, powerful alerting, and dashboards to help ensure that your application is available and performing as expected.</span></span> <span data-ttu-id="44e87-108">또한 문제가 있다면 신속하게 확인하여 얼마나 많은 고객이 영향을 받는지 확인하고, 문제를 찾아서 해결하기 위해 근본 원인을 분석하는 작업을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-108">You also need to be able to see quickly if there's a problem, determine how many customers are affected, and perform a root-cause analysis to find and fix the issue.</span></span>

## <a name="monitor-your-application-with-application-insights"></a><span data-ttu-id="44e87-109">Application Insights를 사용 하 여 응용 프로그램 모니터링</span><span class="sxs-lookup"><span data-stu-id="44e87-109">Monitor your application with Application Insights</span></span>

<span data-ttu-id="44e87-110">Application Insights는 여러 플랫폼에서 작업 하는 웹 개발자를 위한 확장 가능한 응용 프로그램 성능 관리 (APM) 서비스.</span><span class="sxs-lookup"><span data-stu-id="44e87-110">Application Insights is an extensible Application Performance Management (APM) service for web developers who work on multiple platforms.</span></span> <span data-ttu-id="44e87-111">라이브 웹 응용 프로그램을 모니터링 하는 데 사용할.</span><span class="sxs-lookup"><span data-stu-id="44e87-111">Use it to monitor your live web application.</span></span> <span data-ttu-id="44e87-112">Application Insights는 성능 이상을 자동으로 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-112">Application Insights automatically detects performance anomalies.</span></span> <span data-ttu-id="44e87-113">문제 진단을 도와주 고 실제로 할 앱을 사용 하 여 이해를 돕는 강력한 분석 도구를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-113">It includes powerful analytics tools to help you diagnose issues, and to help you understand what users actually do with your app.</span></span> <span data-ttu-id="44e87-114">Application Insights는 성능 및 유용성을 지속적으로 향상 시킬 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-114">Application Insights is designed to help you continuously improve performance and usability.</span></span> <span data-ttu-id="44e87-115">다양 한.NET, Node.js 및 J2EE, 여부를 포함 하는 플랫폼에서 앱에 대 한 작동 호스팅된 온-프레미스 또는 클라우드에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-115">It works for apps on a wide variety of platforms, including .NET, Node.js, and J2EE, whether hosted on-premises or in the cloud.</span></span> <span data-ttu-id="44e87-116">Application Insights는 DevOps 프로세스를 통합 하 고 다양 한 개발 도구에 대 한 연결 지점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-116">Application Insights integrates with your DevOps processes, and has connection points to a variety of development tools.</span></span>

<span data-ttu-id="44e87-117">그림 4-10 Application Insights에서 응용 프로그램을 모니터링 하는 방법 및 이러한 insights 대시보드에 처럼 하는 방법의 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-117">Figure 4-10 shows an example of how Application Insights monitors your application and how it surfaces those insights to a dashboard.</span></span>

![Application Insights 모니터링 대시보드](./media/image10.png)

> <span data-ttu-id="44e87-119">**그림 4-10 합니다.**</span><span class="sxs-lookup"><span data-stu-id="44e87-119">**Figure 4-10.**</span></span> <span data-ttu-id="44e87-120">Application Insights 모니터링 대시보드</span><span class="sxs-lookup"><span data-stu-id="44e87-120">Application Insights monitoring dashboard</span></span>

## <a name="monitor-your-docker-infrastructure-with-log-analytics-and-its-container-monitoring-solution"></a><span data-ttu-id="44e87-121">Log Analytics와 해당 컨테이너 모니터링 솔루션을 사용 하 여 Docker 인프라 모니터링</span><span class="sxs-lookup"><span data-stu-id="44e87-121">Monitor your Docker infrastructure with Log Analytics and its Container Monitoring solution</span></span>

<span data-ttu-id="44e87-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) 의 일부인 합니다 [Microsoft Azure 모니터링 솔루션 전체](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-122">[Azure Log Analytics](https://docs.microsoft.com/azure/log-analytics/log-analytics-overview) is part of the [Microsoft Azure overall monitoring solution](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview).</span></span> <span data-ttu-id="44e87-123">이기도 서비스 [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview)합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-123">It's also a service in [Operations Management Suite (OMS)](https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview).</span></span> <span data-ttu-id="44e87-124">Log Analytics 모니터링 하는 클라우드 및 온-프레미스 환경 (온-프레미스에 대 한 OMS) 가용성과 성능을 유지 하기 위해.</span><span class="sxs-lookup"><span data-stu-id="44e87-124">Log Analytics monitors cloud and on-premises environments (OMS for on-premises) to help maintain availability and performance.</span></span> <span data-ttu-id="44e87-125">여러 원본에서 분석 기능을 제공 하려면 다른 모니터링 도구에서 한 클라우드 및 온-프레미스 환경의 리소스로 생성 된 데이터를 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-125">It collects data generated by resources in your cloud and on-premises environments and from other monitoring tools to provide analysis across multiple sources.</span></span>

<span data-ttu-id="44e87-126">Azure 인프라 로그와 관련 하 여 Log Analytics는 Azure 서비스로 서 수집 하 여 다른 Azure 서비스의 로그 및 메트릭 데이터 (통해 [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure Vm, Docker 컨테이너 및 온-프레미스 또는 기타 클라우드 인프라입니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-126">In relation to Azure infrastructure logs, Log Analytics, as an Azure service, ingests log and metric data from other Azure services (via [Azure Monitor](https://docs.microsoft.com/azure/monitoring-and-diagnostics/monitoring-overview-azure-monitor)), Azure VMs, Docker containers, and on-premises or other cloud infrastructures.</span></span> <span data-ttu-id="44e87-127">Log Analytics는 유연한 로그 검색 및이 데이터를 기반으로 아웃은 분석을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-127">Log Analytics offers flexible log search and out-of-the box analytics on top of this data.</span></span> <span data-ttu-id="44e87-128">지정 된 조건에 따라 원본에서 데이터를 분석 하 여, 모든 로그에서 복잡 한 쿼리를 사용 하면을 사전에 경고할 수 다양 한 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-128">It provides rich tools that you can use to analyze data across sources, it allows complex queries across all logs, and it can proactively alert based on specified conditions.</span></span> <span data-ttu-id="44e87-129">쿼리 및 시각화할 수 있는 중앙 Log Analytics 리포지토리에서 사용자 지정 데이터도 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-129">You can even collect custom data in the central Log Analytics repository, where you can query and visualize it.</span></span> <span data-ttu-id="44e87-130">Log Analytics 기본 제공 솔루션 보안에 즉시 통찰력을 활용 하 고 인프라의 기능 또한 취할 수입니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-130">You also can take advantage of the Log Analytics built-in solutions to immediately gain insights into the security and functionality of your infrastructure.</span></span>

<span data-ttu-id="44e87-131">OMS 포털 또는 모든 브라우저에서 실행 하는 Azure portal을 통해 Log Analytics에 액세스할 수 있으며 구성 설정에 대 한 액세스를 사용 하 여 및 여러 도구 제공을 분석 하 고 수집 된 데이터를 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-131">You can access Log Analytics through the OMS portal or the Azure portal, which run in any browser, and provide you with access to configuration settings and multiple tools to analyze and act on collected data.</span></span>

<span data-ttu-id="44e87-132">합니다 [컨테이너 모니터링 솔루션](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) 사용 하면 Log Analytics에에서 보고 하 고이 단일 위치에서 Docker 및 Windows 컨테이너 호스트를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-132">The [Container Monitoring solution](https://docs.microsoft.com/azure/log-analytics/log-analytics-containers) in Log Analytics helps you view and manage your Docker and Windows Container hosts in a single location.</span></span> <span data-ttu-id="44e87-133">솔루션은를 실행 하는 및 실행 중인 컨테이너는 컨테이너 이미지를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-133">The solution shows which containers are running, what container image they're running, and where containers are running.</span></span> <span data-ttu-id="44e87-134">컨테이너를 사용 하 여 사용 중인 명령을 포함 하 여 자세한 감사 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-134">You can view detailed audit information, including commands that are being used with containers.</span></span> <span data-ttu-id="44e87-135">원격 Docker 또는 Windows 호스트를 확인 하지 않고도 중앙 집중식된 로그를 검색 하 여 컨테이너를 해결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-135">You also can troubleshoot containers by viewing and searching centralized logs, without needing to remotely view Docker or Windows hosts.</span></span> <span data-ttu-id="44e87-136">컨테이너 호스트에서 성가 시 고 소비 과도 한 리소스 수를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-136">You can find containers that might be noisy and consuming excess resources on a host.</span></span> <span data-ttu-id="44e87-137">또한 중앙화 된 CPU, 메모리, 저장소 및 네트워크 사용량 및 컨테이너에 대 한 성능 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-137">Additionally, you can view centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span> <span data-ttu-id="44e87-138">Windows를 실행 하는 컴퓨터에 중앙 집중화를 Windows Server에서 로그를 비교 합니다. Hyper-v 및 Docker 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-138">On computers running Windows, you can centralize and compare logs from Windows Server, Hyper-V, and Docker containers.</span></span> <span data-ttu-id="44e87-139">솔루션에서는 다음과 같은 컨테이너 오 케 스트레이 터를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-139">The solution supports the following container orchestrators:</span></span>

- <span data-ttu-id="44e87-140">Docker Swarm</span><span class="sxs-lookup"><span data-stu-id="44e87-140">Docker Swarm</span></span>

- <span data-ttu-id="44e87-141">DC/OS</span><span class="sxs-lookup"><span data-stu-id="44e87-141">DC/OS</span></span>

- <span data-ttu-id="44e87-142">Kubernetes</span><span class="sxs-lookup"><span data-stu-id="44e87-142">Kubernetes</span></span>

- <span data-ttu-id="44e87-143">Service Fabric</span><span class="sxs-lookup"><span data-stu-id="44e87-143">Service Fabric</span></span>

- <span data-ttu-id="44e87-144">Red Hat OpenShift</span><span class="sxs-lookup"><span data-stu-id="44e87-144">Red Hat OpenShift</span></span>

<span data-ttu-id="44e87-145">그림 4-11 다양 한 컨테이너 호스트와 에이전트와 OMS 간의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-145">Figure 4-11 shows the relationships between various container hosts and agents and OMS.</span></span>

![Log Analytics 컨테이너 모니터링 솔루션](./media/image11.png)

> <span data-ttu-id="44e87-147">**그림 4-11 합니다.**</span><span class="sxs-lookup"><span data-stu-id="44e87-147">**Figure 4-11.**</span></span> <span data-ttu-id="44e87-148">Log Analytics 컨테이너 모니터링 솔루션</span><span class="sxs-lookup"><span data-stu-id="44e87-148">Log Analytics Container Monitoring solution</span></span>

<span data-ttu-id="44e87-149">Log Analytics 컨테이너 모니터링 솔루션을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-149">You can use the Log Analytics Container Monitoring solution to:</span></span>

- <span data-ttu-id="44e87-150">단일 위치에서 모든 컨테이너 호스트에 대 한 정보를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44e87-150">See information about all container hosts in a single location.</span></span>

- <span data-ttu-id="44e87-151">알고 있는 컨테이너를 실행 하는 어떤 이미지를 실행 및 실행 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-151">Know which containers are running, what image they're running, and where they're running.</span></span>

- <span data-ttu-id="44e87-152">컨테이너에 대 한 작업에 대 한 감사 내역을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="44e87-152">See an audit trail for actions on containers.</span></span>

- <span data-ttu-id="44e87-153">Docker 호스트에 원격 로그인이 없는 중앙 집중식된 로그를 검색 하 여이 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-153">Troubleshoot by viewing and searching centralized logs without remote login to the Docker hosts.</span></span>

- <span data-ttu-id="44e87-154">"시끄러운 이웃" 수 있으며 과도 한 리소스를 호스트에서 사용 하는 컨테이너를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-154">Find containers that might be "noisy neighbors," and be consuming excess resources on a host.</span></span>

- <span data-ttu-id="44e87-155">중앙화 된 CPU, 메모리, 저장소 및 네트워크 사용량 및 컨테이너에 대 한 성능 정보를 봅니다.</span><span class="sxs-lookup"><span data-stu-id="44e87-155">View centralized CPU, memory, storage, and network usage, and performance information, for containers.</span></span>

### <a name="additional-resources"></a><span data-ttu-id="44e87-156">추가 자료</span><span class="sxs-lookup"><span data-stu-id="44e87-156">Additional resources</span></span>

- <span data-ttu-id="44e87-157">**Microsoft Azure의 모니터링 개요**</span><span class="sxs-lookup"><span data-stu-id="44e87-157">**Overview of monitoring in Microsoft Azure**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="44e87-158">**Application Insights란?**</span><span class="sxs-lookup"><span data-stu-id="44e87-158">**What is Application Insights?**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/app/app-insights-overview>

- <span data-ttu-id="44e87-159">**Log Analytics 란?**</span><span class="sxs-lookup"><span data-stu-id="44e87-159">**What is Log Analytics?**</span></span>

<https://docs.microsoft.com/azure/log-analytics/log-analytics-overview>

- <span data-ttu-id="44e87-160">**Azure Monitor의 컨테이너 모니터링 솔루션**</span><span class="sxs-lookup"><span data-stu-id="44e87-160">**Container Monitoring solution in Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/insights/containers>

- <span data-ttu-id="44e87-161">**Azure Monitor 개요**</span><span class="sxs-lookup"><span data-stu-id="44e87-161">**Overview of Azure Monitor**</span></span>

<https://docs.microsoft.com/azure/azure-monitor/overview>

- <span data-ttu-id="44e87-162">**Operations Management Suite (OMS) 란?**</span><span class="sxs-lookup"><span data-stu-id="44e87-162">**What is Operations Management Suite (OMS)?**</span></span>

<https://docs.microsoft.com/azure/operations-management-suite/operations-management-suite-overview>

- <span data-ttu-id="44e87-163">**OMS 사용 하 여 Service Fabric에서 Windows Server 컨테이너 모니터링**</span><span class="sxs-lookup"><span data-stu-id="44e87-163">**Monitoring Windows Server containers in Service Fabric with OMS**</span></span>

<https://docs.microsoft.com/azure/service-fabric/service-fabric-diagnostics-containers-windowsserver>

>[!div class="step-by-step"]
><span data-ttu-id="44e87-164">[이전](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
>[다음](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span><span class="sxs-lookup"><span data-stu-id="44e87-164">[Previous](build-resilient-services-ready-for-the-cloud-embrace-transient-failures-in-the-cloud.md)
[Next](modernize-your-apps-lifecycle-with-ci-cd-pipelines-and-devops-tools-in-the-cloud.md)</span></span>
