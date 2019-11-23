---
title: 탄력적 스택으로 로깅
description: 탄력적 스택, Logstash 태 시 및 Kibana를 사용 하 여 로깅
ms.date: 09/23/2019
ms.openlocfilehash: 989834925bc08541bf484e1a4567a56ac324872f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841740"
---
# <a name="logging-with-elastic-stack"></a><span data-ttu-id="b0926-103">탄력적 스택으로 로깅</span><span class="sxs-lookup"><span data-stu-id="b0926-103">Logging with Elastic Stack</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b0926-104">다양 한 중앙 집중식 로깅 도구를 사용할 수 있으며, 무료 오픈 소스 도구에서 비용이 많이 드는 옵션에 이르기까지 다양 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-104">There are many good centralized logging tools and they vary in cost from being free, open-source tools, to more expensive options.</span></span> <span data-ttu-id="b0926-105">대부분의 경우 무료 도구는 유료 제품 보다 우수 하거나 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-105">In many cases, the free tools are as good as or better than the paid offerings.</span></span> <span data-ttu-id="b0926-106">이러한 도구 중 하나는 탄력적 검색, Logstash 및 Kibana의 세 가지 오픈 소스 구성 요소를 조합한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-106">One such tool is a combination of three open-source components: Elastic search, Logstash, and Kibana.</span></span>
<span data-ttu-id="b0926-107">이러한 도구를 집합적으로 탄력적 스택 또는 ELK 스택 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-107">Collectively these tools are known as the Elastic Stack or ELK stack.</span></span>

## <a name="what-are-the-advantages-of-elastic-stack"></a><span data-ttu-id="b0926-108">탄력적 스택의 장점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b0926-108">What are the advantages of Elastic Stack?</span></span>

<span data-ttu-id="b0926-109">탄력적 스택은 경제적인 확장 가능 하 고 안전한 방식으로 중앙 집중식 로깅을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-109">Elastic Stack provides centralized logging in a low-cost, scalable, cloud-friendly manner.</span></span> <span data-ttu-id="b0926-110">사용자 인터페이스를 사용 하면 데이터 분석을 간소화 하므로 clunky 인터페이스를 사용 하는 대신 데이터에서 사항은 정보를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-110">Its user interface streamlines data analysis so you can spend your time gleaning insights from your data instead of fighting with a clunky interface.</span></span> <span data-ttu-id="b0926-111">분산 응용 프로그램이 더 많은 종류의 서비스에 걸쳐 있는 경우에는 다양 한 입력을 지원 하므로 로그 및 메트릭 데이터를 시스템에 계속 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-111">It supports a wide variety of inputs so as your distributed application spans more and different kinds of services, you can expect to continue to be able to feed log and metric data into the system.</span></span> <span data-ttu-id="b0926-112">또한 탄력적 스택은 많은 데이터 집합에 대해서도 빠른 검색을 지원 하므로, 규모가 많은 응용 프로그램 에서도 자세한 데이터를 기록 하 고 성능에 대 한 가시성을 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-112">The Elastic Stack also supports fast searches even across large data sets, making it possible even for large applications to log detailed data and still be able to have visibility into it in a performant fashion.</span></span>

## <a name="logstash"></a><span data-ttu-id="b0926-113">Logstash</span><span class="sxs-lookup"><span data-stu-id="b0926-113">Logstash</span></span>

<span data-ttu-id="b0926-114">첫 번째 구성 요소는 [Logstash 태](https://www.elastic.co/products/logstash)입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-114">The first component is [Logstash](https://www.elastic.co/products/logstash).</span></span> <span data-ttu-id="b0926-115">이 도구는 다양 한 원본에서 로그 정보를 수집 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-115">This tool is used to gather log information from a large variety of different sources.</span></span> <span data-ttu-id="b0926-116">예를 들어 Logstash 태는 디스크에서 로그를 읽고 [Serilog](https://serilog.net/)같은 로깅 라이브러리에서 메시지를 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-116">For instance, Logstash can read logs from disk and also receive messages from logging libraries like [Serilog](https://serilog.net/).</span></span> <span data-ttu-id="b0926-117">Logstash 태 시 로그에서 몇 가지 기본 필터링 및 확장을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-117">Logstash can do some basic filtering and expansion on the logs as they arrive.</span></span> <span data-ttu-id="b0926-118">예를 들어 로그에 IP 주소가 포함 되어 있는 경우, Logstash 태 시 지리적 조회를 수행 하 고 해당 메시지에 대 한 국가 또는 시/도를 가져오도록 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-118">For instance, if your logs contain IP addresses then Logstash may be configured to do a geographical lookup and obtain a country or even city of origin for that message.</span></span>

<span data-ttu-id="b0926-119">Serilog는 매개 변수가 있는 로깅을 허용 하는 .NET 언어의 로깅 라이브러리입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-119">Serilog is a logging library for .NET languages, which allows for parameterized logging.</span></span> <span data-ttu-id="b0926-120">필드를 포함 하는 텍스트 로그 메시지를 생성 하는 대신 매개 변수는 별도로 유지 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-120">Instead of generating a textual log message that embeds fields, parameters are kept separate.</span></span> <span data-ttu-id="b0926-121">이를 통해 보다 지능적인 필터링 및 검색을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-121">This allows for more intelligent filtering and searching.</span></span> <span data-ttu-id="b0926-122">Logstash 태 시 쓰기에 대 한 샘플 Serilog 구성은 그림 7-2에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-122">A sample Serilog configuration for writing to Logstash appears in Figure 7-2.</span></span>

```csharp
var log = new LoggerConfiguration()
         .WriteTo.Http("http://localhost:8080")
         .CreateLogger();
```

<span data-ttu-id="b0926-123">**그림 7-2** HTTP를 통한 logstash 태에 직접 로그 정보를 쓰기 위한 Serilog config</span><span class="sxs-lookup"><span data-stu-id="b0926-123">**Figure 7-2** Serilog config for writing log information directly to logstash over HTTP</span></span>

<span data-ttu-id="b0926-124">Logstash 태는 그림 7-3에 표시 된 것과 같은 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-124">Logstash would use a configuration like the one shown in Figure 7-3.</span></span>

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

<span data-ttu-id="b0926-125">**그림 7-3** -Serilog에서 로그를 사용 하기 위한 logstash 태 시 구성</span><span class="sxs-lookup"><span data-stu-id="b0926-125">**Figure 7-3** - A Logstash configuration for consuming logs from Serilog</span></span>

<span data-ttu-id="b0926-126">광범위 한 로그 조작이 필요 하지 않은 시나리오의 경우 [에는 보다](https://www.elastic.co/products/beats)큰 것으로 알려진 logstash 태의 대안이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-126">For scenarios where extensive log manipulation isn't needed there's an alternative to Logstash known as [Beats](https://www.elastic.co/products/beats).</span></span> <span data-ttu-id="b0926-127">비트는 로그에서 네트워크 데이터 및 작동 시간 정보에 이르는 다양 한 데이터를 수집할 수 있는 도구 제품군입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-127">Beats is a family of tools that can gather a wide variety of data from logs to network data and uptime information.</span></span> <span data-ttu-id="b0926-128">많은 응용 프로그램은 Logstash 태 시와 비트를 모두 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-128">Many applications will use both Logstash and Beats.</span></span>

<span data-ttu-id="b0926-129">Logstash 태에서 로그를 수집한 후에는 해당 로그를 저장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-129">Once the logs have been gathered by Logstash, it needs somewhere to put them.</span></span> <span data-ttu-id="b0926-130">Logstash 태은 다양 한 출력을 지원 하지만, 더 흥미로운 방법 중 하나는 탄력적 검색입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-130">While Logstash supports many different outputs, one of the more exciting ones is Elastic search.</span></span>

## <a name="elastic-search"></a><span data-ttu-id="b0926-131">탄력적 검색</span><span class="sxs-lookup"><span data-stu-id="b0926-131">Elastic search</span></span>

<span data-ttu-id="b0926-132">탄력적 검색은 도착 하면 로그를 인덱싱할 수 있는 강력한 검색 엔진입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-132">Elastic search is a powerful search engine that can index logs as they arrive.</span></span> <span data-ttu-id="b0926-133">로그에 대 한 쿼리를 신속 하 게 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-133">It makes running queries against the logs quick.</span></span> <span data-ttu-id="b0926-134">탄력적 검색은 대량의 로그를 처리할 수 있으며 극단적인 경우 많은 노드에서 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-134">Elastic search can handle huge quantities of logs and, in extreme cases, can be scaled out across many nodes.</span></span>

<span data-ttu-id="b0926-135">매개 변수를 포함 하기 위해 또는 Logstash 태 시 처리를 통해 분할 된 매개 변수를 포함 하도록 만들어진 로그 메시지는 Elasticsearch에서이 정보를 유지 하기 때문에 직접 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-135">Log messages that have been crafted to contain parameters or that have had parameters split from them through Logstash processing, can be queried directly as Elasticsearch preserves this information.</span></span>

<span data-ttu-id="b0926-136">`jill@example.com`에서 방문한 상위 10 개 페이지를 검색 하는 쿼리는 그림 7-4에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-136">A query that searches for the top 10 pages visited by `jill@example.com`, appears in Figure 7-4.</span></span>

```
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

<span data-ttu-id="b0926-137">**그림 7-4** -사용자가 방문 하는 상위 10 개 페이지를 찾기 위한 Elasticsearch 쿼리</span><span class="sxs-lookup"><span data-stu-id="b0926-137">**Figure 7-4** - An Elasticsearch query for finding top 10 pages visited by a user</span></span>

## <a name="visualizing-information-with-kibana-web-dashboards"></a><span data-ttu-id="b0926-138">Kibana 웹 대시보드를 사용 하 여 정보 시각화</span><span class="sxs-lookup"><span data-stu-id="b0926-138">Visualizing information with Kibana web dashboards</span></span>

<span data-ttu-id="b0926-139">스택의 최종 구성 요소는 Kibana입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-139">The final component of the stack is Kibana.</span></span> <span data-ttu-id="b0926-140">이 도구는 웹 대시보드에 대화형 시각화를 제공 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-140">This tool is used to provide interactive visualizations in a web dashboard.</span></span> <span data-ttu-id="b0926-141">대시보드는 비기술적 사용자가 아니더라도 제작 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-141">Dashboards may be crafted even by users who are non-technical.</span></span> <span data-ttu-id="b0926-142">Elasticsearch 인덱스에 상주 하는 대부분의 데이터는 Kibana 대시보드에 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-142">Most data that is resident in the Elasticsearch index, can be included in the Kibana dashboards.</span></span> <span data-ttu-id="b0926-143">개별 사용자는 다른 대시보드를 사용할 수 있으며, Kibana 사용자 특정 대시보드를 허용 하 여이 사용자 지정을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-143">Individual users may have different dashboard desires and Kibana enables this customization through allowing user-specific dashboards.</span></span>

## <a name="installing-elastic-stack-on-azure"></a><span data-ttu-id="b0926-144">Azure에서 탄력적 스택 설치</span><span class="sxs-lookup"><span data-stu-id="b0926-144">Installing Elastic Stack on Azure</span></span>

<span data-ttu-id="b0926-145">탄력적 스택은 다양 한 방법으로 Azure에 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-145">The Elastic stack can be installed on Azure in a number of ways.</span></span> <span data-ttu-id="b0926-146">항상으로 [가상 컴퓨터를 프로 비전 하 고 탄력적 스택을 직접 설치할](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-146">As always, it's possible to [provision virtual machines and install Elastic Stack on them directly](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch).</span></span> <span data-ttu-id="b0926-147">이 옵션은 가장 높은 수준의 사용자 지정 가능성를 제공 하므로 숙련 된 사용자가 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-147">This option is preferred by some experienced users as it offers the highest degree of customizability.</span></span> <span data-ttu-id="b0926-148">인프라를 서비스로 배포 하는 경우에는 해당 경로를 사용 하 여 컴퓨터를 보호 하 고 패치를 최신 상태로 유지 하는 등의 서비스와 관련 된 모든 작업의 소유권을 유지 하는 데 중요 한 관리 오버 헤드가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-148">Deploying on infrastructure as a service introduces significant management overhead forcing those who take that path to take ownership of all the tasks associated with infrastructure as a service such as securing the machines and keeping up-to-date with patches.</span></span>

<span data-ttu-id="b0926-149">오버 헤드가 감소 하는 옵션은 탄력적 스택이 이미 구성 된 많은 Docker 컨테이너 중 하나를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-149">An option with less overhead is to make use of one of the many Docker containers on which the Elastic Stack has already been configured.</span></span> <span data-ttu-id="b0926-150">이러한 컨테이너는 기존 Kubernetes 클러스터로 끌어와 응용 프로그램 코드와 함께 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-150">These containers can be dropped into an existing Kubernetes cluster and run alongside application code.</span></span> <span data-ttu-id="b0926-151">[Sebp/elk](https://elk-docker.readthedocs.io/) 컨테이너는 잘 문서화 되 고 테스트 된 탄력적 스택 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-151">The [sebp/elk](https://elk-docker.readthedocs.io/) container is a well-documented and tested Elastic Stack container.</span></span>

<span data-ttu-id="b0926-152">또 다른 옵션은 [최근에 발표 한 ELK as a service 제품](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/)입니다.</span><span class="sxs-lookup"><span data-stu-id="b0926-152">Another option is a [recently announced ELK-as-a-service offering](https://devops.com/logz-io-unveils-azure-open-source-elk-monitoring-solution/).</span></span>

## <a name="references"></a><span data-ttu-id="b0926-153">참조</span><span class="sxs-lookup"><span data-stu-id="b0926-153">References</span></span>

- [<span data-ttu-id="b0926-154">Azure에 탄력적 스택 설치</span><span class="sxs-lookup"><span data-stu-id="b0926-154">Install Elastic Stack on Azure</span></span>](https://docs.microsoft.com/azure/virtual-machines/linux/tutorial-elasticsearch)

>[!div class="step-by-step"]
><span data-ttu-id="b0926-155">[이전](observability-patterns.md)
>[다음](monitoring-azure-kubernetes.md)</span><span class="sxs-lookup"><span data-stu-id="b0926-155">[Previous](observability-patterns.md)
[Next](monitoring-azure-kubernetes.md)</span></span>
