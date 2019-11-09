---
title: Azure Kubernetes Service의 모니터링
description: Azure Kubernetes Service의 모니터링
ms.date: 09/23/2019
ms.openlocfilehash: 71192601eac2169db188b25da3dc91b71b860903
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "73841128"
---
# <a name="monitoring-in-azure-kubernetes-services"></a><span data-ttu-id="55810-103">Azure Kubernetes Service의 모니터링</span><span class="sxs-lookup"><span data-stu-id="55810-103">Monitoring in Azure Kubernetes Services</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="55810-104">Kubernetes의 기본 제공 로깅은 기본 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="55810-104">The built-in logging in Kubernetes is primitive.</span></span> <span data-ttu-id="55810-105">그러나 로그를 Kubernetes 하 고 적절 하 게 분석할 수 있는 위치에 저장할 수 있는 몇 가지 유용한 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55810-105">However, there are some great options for getting the logs out of Kubernetes and into a place where they can be properly analyzed.</span></span> <span data-ttu-id="55810-106">AKS 클러스터를 모니터링 해야 하는 경우 Kubernetes에 대 한 탄력적 스택 구성은 훌륭한 솔루션입니다.</span><span class="sxs-lookup"><span data-stu-id="55810-106">If you need to monitor your AKS clusters, configuring Elastic Stack for Kubernetes is a great solution.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="55810-107">탄력적 스택</span><span class="sxs-lookup"><span data-stu-id="55810-107">Elastic Stack</span></span>

<span data-ttu-id="55810-108">탄력적 스택은 Kubernetes 클러스터에서 정보를 수집 하는 강력한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="55810-108">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="55810-109">Kubernetes는 Elasticsearch 끝점에 로그를 보내는 작업을 지원 하며, [대부분](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)의 경우 그림 7-5에 표시 된 것 처럼 환경 변수를 설정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55810-109">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="55810-110">**그림 7-5** -Kubernetes에 대 한 구성 변수</span><span class="sxs-lookup"><span data-stu-id="55810-110">**Figure 7-5** - Configuration variables for Kubernetes</span></span>

<span data-ttu-id="55810-111">그러면 클러스터에 Elasticsearch가 설치 되 고 모든 클러스터 로그를 대상으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55810-111">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="55810-112">Kubernetes의 수집 로그에 대 한 쿼리 결과를 보여 주는 Kibana 대시보드의 예](./media/kibana-dashboard.png)
**그림 7-6**을 ![합니다.</span><span class="sxs-lookup"><span data-stu-id="55810-112">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="55810-113">Kubernetes의 수집 로그에 대 한 쿼리 결과를 보여 주는 Kibana 대시보드의 예</span><span class="sxs-lookup"><span data-stu-id="55810-113">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="azure-container-monitoring"></a><span data-ttu-id="55810-114">Azure 컨테이너 모니터링</span><span class="sxs-lookup"><span data-stu-id="55810-114">Azure Container Monitoring</span></span>

<span data-ttu-id="55810-115">Azure 컨테이너 모니터링은 Kubernetes 뿐만 아니라 DC/OS, Docker Swarm 및 Red Hat OpenShift와 같은 다른 오케스트레이션 엔진에서 로그를 사용 하도록 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="55810-115">Azure Container Monitoring supports consuming logs from not just Kubernetes but also from other orchestration engines such as DC/OS, Docker Swarm, and Red Hat OpenShift.</span></span>

<span data-ttu-id="55810-116">다양 한 컨테이너의 로그를 사용 하 ![](./media/containers-diagram.png)
**그림 7-7**.</span><span class="sxs-lookup"><span data-stu-id="55810-116">![Consuming logs from various containers](./media/containers-diagram.png)
**Figure 7-7**.</span></span>  <span data-ttu-id="55810-117">다양 한 컨테이너의 로그 사용</span><span class="sxs-lookup"><span data-stu-id="55810-117">Consuming logs from various containers</span></span>

<span data-ttu-id="55810-118">로그 및 메트릭 정보는 클러스터에서 실행 되는 컨테이너 뿐만 아니라 클러스터 호스트 자체 에서도 수집 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55810-118">Log and metric information is gathered not just from the containers running in the cluster but also from the cluster hosts themselves.</span></span> <span data-ttu-id="55810-119">두 로그 정보의 상관 관계를 설정 하 여 오류를 보다 쉽게 추적할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55810-119">It allows correlating log information from the two making it much easier to track down an error.</span></span>

<span data-ttu-id="55810-120">로그 수집기 설치는 [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) 및 [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) 클러스터에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="55810-120">Installing the log collectors differs on [Windows](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-windows-agent-for-kubernetes) and [Linux](https://docs.microsoft.com/azure/azure-monitor/insights/containers#configure-a-log-analytics-linux-agent-for-kubernetes) clusters.</span></span> <span data-ttu-id="55810-121">그러나 두 경우 모두 로그 수집은 Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/)로 구현 됩니다. 즉, 로그 수집기는 각 노드에서 컨테이너로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55810-121">But in both cases the log collection is implemented as a Kubernetes [DaemonSet](https://kubernetes.io/docs/concepts/workloads/controllers/daemonset/), meaning that the log collector is run as a container on each of the nodes.</span></span>

<span data-ttu-id="55810-122">Orchestrator 또는 운영 체제에서 Azure Monitor 디먼을 실행 하는 것과 관계 없이 로그 정보는 사용자가 익숙한 동일한 Azure Monitor 도구에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55810-122">No matter which orchestrator or operating system is running the Azure Monitor daemon, the log information is forwarded to the same Azure Monitor tools with which users are familiar.</span></span> <span data-ttu-id="55810-123">이를 통해 하이브리드 Kubernetes/Azure Functions 환경과 같은 여러 로그 원본을 혼합 하는 환경에서 병렬 환경이 보장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="55810-123">This ensures a parallel experience in environments that mix different log sources such as a hybrid Kubernetes/Azure Functions environment.</span></span>

<span data-ttu-id="55810-124">실행 중인 많은 컨테이너의 로깅 및 메트릭 정보를 보여 주는 샘플 대시보드를 ![합니다. **그림 7-8**을](./media/containers-dashboard.png)
합니다.</span><span class="sxs-lookup"><span data-stu-id="55810-124">![A sample dashboard showing logging and metric information from a number of running containers.](./media/containers-dashboard.png)
**Figure 7-8**.</span></span> <span data-ttu-id="55810-125">실행 중인 많은 컨테이너의 로깅 및 메트릭 정보를 보여 주는 샘플 대시보드</span><span class="sxs-lookup"><span data-stu-id="55810-125">A sample dashboard showing logging and metric information from a number of running containers.</span></span>

## <a name="logfinalize"></a><span data-ttu-id="55810-126">.Log. Finalize ()</span><span class="sxs-lookup"><span data-stu-id="55810-126">Log.Finalize()</span></span>

<span data-ttu-id="55810-127">로깅은 가장 간과 되는 응용 프로그램을 대규모로 배포 하는 가장 중요 한 부분 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="55810-127">Logging is one of the most overlooked and yet most important parts of deploying any application at scale.</span></span> <span data-ttu-id="55810-128">응용 프로그램의 크기와 복잡성이 증가 함에 따라 응용 프로그램을 디버깅 하는 데 어려움이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="55810-128">As the size and complexity of applications increase, then so does the difficulty of debugging them.</span></span> <span data-ttu-id="55810-129">최고 품질의 로그를 사용 가능 하 게 설정 하면 디버깅이 훨씬 간편해 지 며 "거의 불가능 하지 않음" 영역에서 "편리한 환경"으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="55810-129">Having top quality logs available makes debugging much easier and moves it from the realm of "nearly impossible" to "a pleasant experience".</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="55810-130">[이전](logging-with-elastic-stack.md)
>[다음](azure-monitor.md)</span><span class="sxs-lookup"><span data-stu-id="55810-130">[Previous](logging-with-elastic-stack.md)
[Next](azure-monitor.md)</span></span>
