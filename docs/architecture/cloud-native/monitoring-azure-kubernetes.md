---
title: Azure Kubernetes Service의 모니터링
description: Azure Kubernetes Service의 모니터링
ms.date: 02/05/2020
ms.openlocfilehash: 5c46b9e8599f70d430ad26cf1364343454d30a16
ms.sourcegitcommit: 700ea803fb06c5ce98de017c7f76463ba33ff4a9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2020
ms.locfileid: "77450065"
---
# <a name="monitoring-in-azure-kubernetes-services"></a><span data-ttu-id="46a95-103">Azure Kubernetes Service의 모니터링</span><span class="sxs-lookup"><span data-stu-id="46a95-103">Monitoring in Azure Kubernetes Services</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="46a95-104">Kubernetes의 기본 제공 로깅은 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-104">The built-in logging in Kubernetes is primitive.</span></span> <span data-ttu-id="46a95-105">그러나 로그를 Kubernetes 하 고 적절 하 게 분석할 수 있는 위치에 저장할 수 있는 몇 가지 유용한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-105">However, there are some great options for getting the logs out of Kubernetes and into a place where they can be properly analyzed.</span></span> <span data-ttu-id="46a95-106">AKS 클러스터를 모니터링 해야 하는 경우 Kubernetes에 대 한 탄력적 스택 구성은 훌륭한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-106">If you need to monitor your AKS clusters, configuring Elastic Stack for Kubernetes is a great solution.</span></span>

## <a name="azure-monitor-for-containers"></a><span data-ttu-id="46a95-107">컨테이너용 Azure Monitor</span><span class="sxs-lookup"><span data-stu-id="46a95-107">Azure Monitor for Containers</span></span>

<span data-ttu-id="46a95-108">[컨테이너에 대 한 Azure Monitor는](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview) 뿐만 아니라 DC/OS, Docker Swarm 및 Red Hat openshift와 같은 다른 오케스트레이션 엔진에서 뿐만 아니라 Kubernetes의 로그 사용을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-108">[Azure Monitor for Containers](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-overview) supports consuming logs from not just Kubernetes but also from other orchestration engines such as DC/OS, Docker Swarm, and Red Hat OpenShift.</span></span>

<span data-ttu-id="46a95-109">다양 한 컨테이너의 로그를 사용 하 ![](./media/containers-diagram.png)
**그림 7-10**.</span><span class="sxs-lookup"><span data-stu-id="46a95-109">![Consuming logs from various containers](./media/containers-diagram.png)
**Figure 7-10**.</span></span> <span data-ttu-id="46a95-110">다양 한 컨테이너의 로그 사용</span><span class="sxs-lookup"><span data-stu-id="46a95-110">Consuming logs from various containers</span></span>

<span data-ttu-id="46a95-111">[프로메테우스](https://prometheus.io/) 는 인기 있는 오픈 소스 메트릭 모니터링 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-111">[Prometheus](https://prometheus.io/) is a popular open source metric monitoring solution.</span></span> <span data-ttu-id="46a95-112">클라우드 기본 계산 파운데이션의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-112">It is part of the Cloud Native Compute Foundation.</span></span> <span data-ttu-id="46a95-113">일반적으로, 프로메테우스를 사용 하려면 고유한 저장소로 프로메테우스 서버를 관리 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-113">Typically, using Prometheus requires managing a Prometheus server with its own store.</span></span> <span data-ttu-id="46a95-114">그러나 [컨테이너에 대 한 Azure Monitor는 프로메테우스 메트릭 끝점과의 직접 통합을 제공](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-prometheus-integration)하므로 별도의 서버가 필요 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-114">However, [Azure Monitor for Containers provides direct integration with Prometheus metrics endpoints](https://docs.microsoft.com/azure/azure-monitor/insights/container-insights-prometheus-integration), so a separate server is not required.</span></span>

<span data-ttu-id="46a95-115">로그 및 메트릭 정보는 클러스터에서 실행 되는 컨테이너 뿐만 아니라 클러스터 호스트 자체 에서도 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-115">Log and metric information is gathered not just from the containers running in the cluster but also from the cluster hosts themselves.</span></span> <span data-ttu-id="46a95-116">두 로그 정보의 상관 관계를 설정 하 여 오류를 보다 쉽게 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-116">It allows correlating log information from the two making it much easier to track down an error.</span></span>

<span data-ttu-id="46a95-117">로그 수집기 설치는 [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) 및 [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) 클러스터에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-117">Installing the log collectors differs on [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) and [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) clusters.</span></span> <span data-ttu-id="46a95-118">그러나 두 경우 모두 로그 수집은 Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)로 구현 됩니다. 즉, 로그 수집기는 각 노드에서 컨테이너로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-118">But in both cases the log collection is implemented as a Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), meaning that the log collector is run as a container on each of the nodes.</span></span>

<span data-ttu-id="46a95-119">Orchestrator 또는 운영 체제에서 Azure Monitor 디먼을 실행 하는 것과 관계 없이 로그 정보는 사용자가 익숙한 동일한 Azure Monitor 도구에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-119">No matter which orchestrator or operating system is running the Azure Monitor daemon, the log information is forwarded to the same Azure Monitor tools with which users are familiar.</span></span> <span data-ttu-id="46a95-120">이를 통해 하이브리드 Kubernetes/Azure Functions 환경과 같은 여러 로그 원본을 혼합 하는 환경에서 병렬 환경이 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-120">This ensures a parallel experience in environments that mix different log sources such as a hybrid Kubernetes/Azure Functions environment.</span></span>

<span data-ttu-id="46a95-121">실행 중인 많은 컨테이너의 로깅 및 메트릭 정보를 보여 주는 샘플 대시보드를 ![합니다. **그림 7-11**을](./media/containers-dashboard.png)
합니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-121">![A sample dashboard showing logging and metric information from a number of running containers.](./media/containers-dashboard.png)
**Figure 7-11**.</span></span> <span data-ttu-id="46a95-122">실행 중인 많은 컨테이너의 로깅 및 메트릭 정보를 보여 주는 샘플 대시보드</span><span class="sxs-lookup"><span data-stu-id="46a95-122">A sample dashboard showing logging and metric information from a number of running containers.</span></span>

## <a name="logfinalize"></a><span data-ttu-id="46a95-123">.Log. Finalize ()</span><span class="sxs-lookup"><span data-stu-id="46a95-123">Log.Finalize()</span></span>

<span data-ttu-id="46a95-124">로깅은 가장 간과 되는 응용 프로그램을 대규모로 배포 하는 가장 중요 한 부분 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-124">Logging is one of the most overlooked and yet most important parts of deploying any application at scale.</span></span> <span data-ttu-id="46a95-125">응용 프로그램의 크기와 복잡성이 증가 함에 따라 응용 프로그램을 디버깅 하는 데 어려움이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-125">As the size and complexity of applications increase, then so does the difficulty of debugging them.</span></span> <span data-ttu-id="46a95-126">최고 품질의 로그를 사용 가능 하 게 설정 하면 디버깅이 훨씬 간편해 지 며 "거의 불가능 하지 않음" 영역에서 "편리한 환경"으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="46a95-126">Having top quality logs available makes debugging much easier and moves it from the realm of "nearly impossible" to "a pleasant experience".</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="46a95-127">[이전](logging-with-elastic-stack.md)
>[다음](azure-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="46a95-127">[Previous](logging-with-elastic-stack.md)
[Next](azure-monitor.md)</span></span>
