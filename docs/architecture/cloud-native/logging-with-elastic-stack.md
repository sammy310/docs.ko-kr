---
title: 탄력적 스택으로 로깅
description: 탄력적 스택, Logstash 태 시 및 Kibana를 사용 하 여 로깅
ms.date: 05/13/2020
ms.openlocfilehash: 3f10b0d06c87b7bed6d3e302742b1dc52e2c9d3b
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91155343"
---
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="3c15d-103">탄력적 스택으로 로깅</span><span class="sxs-lookup"><span data-stu-id="3c15d-103">Logging with Elastic Stack</span></span>

<span data-ttu-id="3c15d-104">다양 한 중앙 집중식 로깅 도구를 사용할 수 있으며, 무료 오픈 소스 도구에서 비용이 많이 드는 옵션에 이르기까지 다양 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="3c15d-105">대부분의 경우 무료 도구는 유료 제품 보다 우수 하거나 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="3c15d-106">이러한 도구 중 하나는 탄력적 검색, Logstash 및 Kibana의 세 가지 오픈 소스 구성 요소를 조합한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span>

<span data-ttu-id="3c15d-107">이러한 도구를 집합적으로 탄력적 스택 또는 ELK 스택 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="elastic-stack"></a><span data-ttu-id="3c15d-108">탄력적 스택</span><span class="sxs-lookup"><span data-stu-id="3c15d-108">Elastic Stack</span></span>

<span data-ttu-id="3c15d-109">탄력적 스택은 Kubernetes 클러스터에서 정보를 수집 하는 강력한 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-109">The Elastic Stack is a powerful option for gathering information from a Kubernetes cluster.</span></span> <span data-ttu-id="3c15d-110">Kubernetes는 Elasticsearch 끝점에 로그를 보내는 작업을 지원 하며, [대부분](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/)의 경우 그림 7-5에 표시 된 것 처럼 환경 변수를 설정 하기만 하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-110">Kubernetes supports sending logs to an Elasticsearch endpoint, and for the [most part](https://kubernetes.io/docs/tasks/debug-application-cluster/logging-elasticsearch-kibana/), all you need to get started is to set the environment variables as shown in Figure 7-5:</span></span>

```kubernetes
KUBE_LOGGING_DESTINATION=elasticsearch
KUBE_ENABLE_NODE_LOGGING=true
```

<span data-ttu-id="3c15d-111">**그림 7-5**.</span><span class="sxs-lookup"><span data-stu-id="3c15d-111">**Figure 7-5**.</span></span> <span data-ttu-id="3c15d-112">Kubernetes에 대 한 구성 변수</span><span class="sxs-lookup"><span data-stu-id="3c15d-112">Configuration variables for Kubernetes</span></span>

<span data-ttu-id="3c15d-113">그러면 클러스터에 Elasticsearch가 설치 되 고 모든 클러스터 로그를 대상으로 전송 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-113">This will install Elasticsearch on the cluster and target sending all the cluster logs to it.</span></span>

<span data-ttu-id="3c15d-114">![Kubernetes 그림 7-6의 수집 로그에 대 한 쿼리 결과를 보여 주는 Kibana 대시보드의 예 ](./media/kibana-dashboard.png)
 **Figure 7-6**입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-114">![An example of a Kibana dashboard showing the results of a query against logs ingested from Kubernetes](./media/kibana-dashboard.png)
**Figure 7-6**.</span></span> <span data-ttu-id="3c15d-115">Kubernetes의 수집 로그에 대 한 쿼리 결과를 보여 주는 Kibana 대시보드의 예</span><span class="sxs-lookup"><span data-stu-id="3c15d-115">An example of a Kibana dashboard showing the results of a query against logs that are ingested from Kubernetes</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="3c15d-116">탄력적 스택의 장점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="3c15d-116">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="3c15d-117">탄력적 스택은 경제적인 확장 가능 하 고 안전한 방식으로 중앙 집중식 로깅을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-117">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="3c15d-118">사용자 인터페이스를 사용 하면 데이터 분석을 간소화 하므로 clunky 인터페이스를 사용 하는 대신 데이터에서 사항은 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-118">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="3c15d-119">분산 응용 프로그램이 더 많은 종류의 서비스에 걸쳐 있는 경우에는 다양 한 입력을 지원 하므로 로그 및 메트릭 데이터를 시스템에 계속 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-119">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="3c15d-120">또한 탄력적 스택은 많은 데이터 집합에 대해서도 빠른 검색을 지원 하므로, 규모가 많은 응용 프로그램 에서도 자세한 데이터를 기록 하 고 성능에 대 한 가시성을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-120">The Elastic Stack also supports fast searches even across large data sets, making it possible even for large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="3c15d-121">Logstash</span><span class="sxs-lookup"><span data-stu-id="3c15d-121">Logstash</span></span>

<span data-ttu-id="3c15d-122">첫 번째 구성 요소는 [Logstash 태](https://www.elastic.co/products/logstash)입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-122">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="3c15d-123">이 도구는 다양 한 원본에서 로그 정보를 수집 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-123">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="3c15d-124">예를 들어 Logstash 태는 디스크에서 로그를 읽고 [Serilog](https://serilog.net/)같은 로깅 라이브러리에서 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-124">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="3c15d-125">Logstash 태 시 로그에서 몇 가지 기본 필터링 및 확장을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-125">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="3c15d-126">예를 들어 로그에 IP 주소가 포함 되어 있는 경우, Logstash 태 시 지리적 조회를 수행 하 고 해당 메시지에 대 한 국가 또는 시/도를 가져오도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-126">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span>

<span data-ttu-id="3c15d-127">Serilog는 매개 변수가 있는 로깅을 허용 하는 .NET 언어의 로깅 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-127">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="3c15d-128">필드를 포함 하는 텍스트 로그 메시지를 생성 하는 대신 매개 변수는 별도로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-128">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="3c15d-129">이를 통해 보다 지능적인 필터링 및 검색을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-129">This allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="3c15d-130">Logstash 태 시 쓰기에 대 한 샘플 Serilog 구성은 그림 7-7에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-130">A sample Serilog configuration for writing to Logstash appears in Figure 7-7.</span></span>

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="3c15d-131">**그림 7-7**.</span><span class="sxs-lookup"><span data-stu-id="3c15d-131">**Figure 7-7**.</span></span> <span data-ttu-id="3c15d-132">HTTP를 통한 logstash 태에 직접 로그 정보를 쓰기 위한 Serilog config</span><span class="sxs-lookup"><span data-stu-id="3c15d-132">Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="3c15d-133">Logstash 태는 그림 7-8에 표시 된 것과 같은 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-133">Logstash would use a configuration like the one shown in Figure 7-8.</span></span>

```
input {
    http {
        #default host 0.0.0.0:8080
        codec => json
    }
}

output {
    elasticsearch {
        hosts => "elasticsearch:9200"
        index=>"sales-%{+xxxx.ww}"
    }
}
```

<span data-ttu-id="3c15d-134">**그림 7-8**.</span><span class="sxs-lookup"><span data-stu-id="3c15d-134">**Figure 7-8**.</span></span> <span data-ttu-id="3c15d-135">Serilog에서 로그를 사용 하기 위한 Logstash 태 시 구성</span><span class="sxs-lookup"><span data-stu-id="3c15d-135">A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="3c15d-136">광범위 한 로그 조작이 필요 하지 않은 시나리오의 경우 [에는 보다](https://www.elastic.co/products/beats)큰 것으로 알려진 logstash 태의 대안이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-136">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="3c15d-137">비트는 로그에서 네트워크 데이터 및 작동 시간 정보에 이르는 다양 한 데이터를 수집할 수 있는 도구 제품군입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-137">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="3c15d-138">많은 응용 프로그램은 Logstash 태 시와 비트를 모두 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-138">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="3c15d-139">Logstash 태에서 로그를 수집한 후에는 해당 로그를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-139">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="3c15d-140">Logstash 태은 다양 한 출력을 지원 하지만, 더 흥미로운 방법 중 하나는 탄력적 검색입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-140">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="3c15d-141">탄력적 검색</span><span class="sxs-lookup"><span data-stu-id="3c15d-141">Elastic search</span></span>

<span data-ttu-id="3c15d-142">탄력적 검색은 도착 하면 로그를 인덱싱할 수 있는 강력한 검색 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-142">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="3c15d-143">로그에 대 한 쿼리를 신속 하 게 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-143">It makes running queries against the logs quick.</span></span> <span data-ttu-id="3c15d-144">탄력적 검색은 대량의 로그를 처리할 수 있으며 극단적인 경우 많은 노드에서 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-144">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span>

<span data-ttu-id="3c15d-145">매개 변수를 포함 하기 위해 또는 Logstash 태 시 처리를 통해 분할 된 매개 변수를 포함 하도록 만들어진 로그 메시지는 Elasticsearch에서이 정보를 유지 하기 때문에 직접 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-145">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="3c15d-146">에서 방문한 상위 10 페이지를 검색 하는 쿼리는 `jill@example.com` 그림 7-9에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-146">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-9.</span></span>

```json
"query": {
    "match": {
      "user": "jill@example.com"
    }
  },
  "aggregations": {
    "top_10_pages": {
      "terms": {
        "field": "page",
        "size": 10
      }
    }
  }
```

<span data-ttu-id="3c15d-147">**그림 7-9**.</span><span class="sxs-lookup"><span data-stu-id="3c15d-147">**Figure 7-9**.</span></span> <span data-ttu-id="3c15d-148">사용자가 방문 하는 상위 10 개 페이지를 찾기 위한 Elasticsearch 쿼리</span><span class="sxs-lookup"><span data-stu-id="3c15d-148">An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="3c15d-149">Kibana 웹 대시보드를 사용 하 여 정보 시각화</span><span class="sxs-lookup"><span data-stu-id="3c15d-149">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="3c15d-150">스택의 최종 구성 요소는 Kibana입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-150">The final component of the stack is Kibana.</span></span> <span data-ttu-id="3c15d-151">이 도구는 웹 대시보드에 대화형 시각화를 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-151">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="3c15d-152">대시보드는 비기술적 사용자가 아니더라도 제작 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-152">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="3c15d-153">Elasticsearch 인덱스에 상주 하는 대부분의 데이터는 Kibana 대시보드에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-153">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="3c15d-154">개별 사용자는 다른 대시보드를 사용할 수 있으며, Kibana 사용자 특정 대시보드를 허용 하 여이 사용자 지정을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-154">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span>

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="3c15d-155">Azure에서 탄력적 스택 설치</span><span class="sxs-lookup"><span data-stu-id="3c15d-155">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="3c15d-156">탄력적 스택은 다양 한 방법으로 Azure에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-156">The Elastic stack can be installed on Azure in a number of ways.</span></span> <span data-ttu-id="3c15d-157">항상으로 [가상 컴퓨터를 프로 비전 하 고 탄력적 스택을 직접 설치할](/azure/virtual-machines/linux/tutorial-elasticsearch)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-157">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="3c15d-158">이 옵션은 가장 높은 수준의 사용자 지정 가능성를 제공 하므로 숙련 된 사용자가 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-158">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="3c15d-159">인프라를 서비스로 배포 하는 경우에는 해당 경로를 사용 하 여 컴퓨터를 보호 하 고 패치를 최신 상태로 유지 하는 등의 서비스와 관련 된 모든 작업의 소유권을 유지 하는 데 중요 한 관리 오버 헤드가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-159">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span>

<span data-ttu-id="3c15d-160">오버 헤드가 감소 하는 옵션은 탄력적 스택이 이미 구성 된 많은 Docker 컨테이너 중 하나를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-160">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="3c15d-161">이러한 컨테이너는 기존 Kubernetes 클러스터로 끌어와 응용 프로그램 코드와 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-161">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="3c15d-162">[Sebp/elk](https://elk-docker.readthedocs.io/) 컨테이너는 잘 문서화 되 고 테스트 된 탄력적 스택 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-162">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="3c15d-163">또 다른 옵션은 [최근에 발표 한 ELK as a service 제품](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/)입니다.</span><span class="sxs-lookup"><span data-stu-id="3c15d-163">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="3c15d-164">참조</span><span class="sxs-lookup"><span data-stu-id="3c15d-164">References</span></span>

- [<span data-ttu-id="3c15d-165">Azure에 탄력적 스택 설치</span><span class="sxs-lookup"><span data-stu-id="3c15d-165">Install Elastic Stack on Azure</span></span>](/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="3c15d-166">[이전](observability-patterns.md)
>[다음](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="3c15d-166">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>
