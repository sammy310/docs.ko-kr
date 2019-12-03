---
title: 서비스 메시-WCF 개발자를 위한 gRPC
description: 서비스 메시를 사용 하 여 Kubernetes 클러스터의 gRPC 서비스에 대 한 요청을 라우팅하고 분산 합니다.
ms.date: 09/02/2019
ms.openlocfilehash: cc4855b1ed27e29076e4f13f5c5d3dffa63a6554
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74711272"
---
# <a name="service-meshes"></a><span data-ttu-id="4baf7-103">서비스 메시</span><span class="sxs-lookup"><span data-stu-id="4baf7-103">Service meshes</span></span>

<span data-ttu-id="4baf7-104">서비스 메시는 네트워크 내에서 라우팅 서비스 요청을 제어 하는 인프라 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-104">A service mesh is an infrastructure component that takes control of routing service requests within a network.</span></span> <span data-ttu-id="4baf7-105">서비스 메시는 다음과 같은 Kubernetes 클러스터 내에서 모든 종류의 네트워크 수준 문제를 처리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-105">Service meshes can handle all kinds of network-level concerns within a Kubernetes cluster, including:</span></span>

- <span data-ttu-id="4baf7-106">서비스 검색</span><span class="sxs-lookup"><span data-stu-id="4baf7-106">Service discovery</span></span>
- <span data-ttu-id="4baf7-107">부하 분산</span><span class="sxs-lookup"><span data-stu-id="4baf7-107">Load balancing</span></span>
- <span data-ttu-id="4baf7-108">내결함성</span><span class="sxs-lookup"><span data-stu-id="4baf7-108">Fault tolerance</span></span>
- <span data-ttu-id="4baf7-109">암호화</span><span class="sxs-lookup"><span data-stu-id="4baf7-109">Encryption</span></span>
- <span data-ttu-id="4baf7-110">모니터링</span><span class="sxs-lookup"><span data-stu-id="4baf7-110">Monitoring</span></span>

<span data-ttu-id="4baf7-111">Kubernetes service 메시는 메시에 포함 된 각 pod에 *사이드카 proxy*라는 추가 컨테이너를 추가 하 여 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-111">Kubernetes service meshes work by adding an extra container, called a *sidecar proxy*, to each pod included in the mesh.</span></span> <span data-ttu-id="4baf7-112">프록시는 모든 인바운드 및 아웃 바운드 네트워크 요청을 처리 하 여 네트워크 문제를 구성 하 고 관리 하는 작업은 응용 프로그램 컨테이너와 별도로 유지 하 고 대부분의 경우 응용 프로그램 코드를 변경 하지 않고도 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-112">The proxy takes over handling all inbound and outbound network requests, allowing configuration and management of networking matters to be kept separate from the application containers and, in many cases, without requiring any changes to the application code.</span></span>

<span data-ttu-id="4baf7-113">[이전 챕터의 예제](kubernetes.md#test-the-application)를 사용 합니다. 여기서 웹 응용 프로그램의 grpc 요청은 모두 grpc 서비스의 단일 인스턴스로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-113">Take the [previous chapter's example](kubernetes.md#test-the-application), where the gRPC requests from the web application were all routed to a single instance of the gRPC service.</span></span> <span data-ttu-id="4baf7-114">이는 서비스의 호스트 이름이 IP 주소로 확인 되 고 해당 IP 주소가 `HttpClientHandler` 인스턴스의 수명 동안 캐시 되기 때문에 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-114">This happens because the service's hostname is resolved to an IP address, and that IP address is cached for the lifetime of the `HttpClientHandler` instance.</span></span> <span data-ttu-id="4baf7-115">DNS 조회를 수동으로 처리 하거나 여러 클라이언트를 만들어이 문제를 해결할 수 있지만 비즈니스 또는 고객 가치를 추가 하지 않으면 응용 프로그램 코드가 상당히 복잡 해질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-115">It might be possible to work around this by handling DNS lookups manually or creating multiple clients, but this would complicate the application code considerably without adding any business or customer value.</span></span>

<span data-ttu-id="4baf7-116">서비스 메시를 사용 하 여 응용 프로그램 컨테이너의 요청은 사이드카 프록시로 전송 되며이를 통해 다른 서비스의 모든 인스턴스에 지능적으로 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-116">Using a service mesh, the requests from the application container are sent to the sidecar proxy, which can distribute them intelligently across all instances of the other service.</span></span> <span data-ttu-id="4baf7-117">메시도 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-117">The mesh can also:</span></span>

- <span data-ttu-id="4baf7-118">서비스의 개별 인스턴스 오류에 대해 원활 하 게 대응 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-118">Respond seamlessly to failures of individual instances of a service.</span></span>
- <span data-ttu-id="4baf7-119">실패 한 호출 또는 시간 제한에 대 한 재시도 의미 체계를 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-119">Handle retry semantics for failed calls or timeouts</span></span>
- <span data-ttu-id="4baf7-120">클라이언트 응용 프로그램에 반환 하지 않고 실패 한 요청을 대체 인스턴스로 경로를 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-120">Reroute failed requests to an alternate instance without returning to the client application at all.</span></span>

<span data-ttu-id="4baf7-121">다음 스크린샷은 응용 프로그램 코드를 변경 하거나 사용 중인 Docker 이미지를 변경 하지 않고 Linkerd 서비스 메시로 실행 되는 StockWeb 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-121">The following screenshot shows the StockWeb application running with the Linkerd service mesh, with no changes to the application code, or even the Docker image being used.</span></span> <span data-ttu-id="4baf7-122">필요한 유일한 변경 내용은 `stockdata` 및 `stockweb` 서비스에 대 한 YAML 파일의 배포에 대 한 주석을 추가 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-122">The only change required was the addition of an annotation to the Deployment in the YAML files for the `stockdata` and `stockweb` services.</span></span>

![서비스 메시를 사용 하는 StockWeb](media/service-mesh/stockweb-servicemesh-screenshot.png)

<span data-ttu-id="4baf7-124">응용 프로그램 코드의 단일 `HttpClient` 인스턴스에서 발생 하더라도 StockWeb 응용 프로그램의 요청이 StockData 서비스의 두 복제본으로 라우트 되었음을 서버 열에서 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-124">You can see from the Server column that the requests from the StockWeb application have been routed to both replicas of the StockData service, despite originating from a single `HttpClient` instance in the application code.</span></span> <span data-ttu-id="4baf7-125">실제로 코드를 검토 하는 경우 StockData 서비스에 대 한 모든 100 요청이 동일한 `HttpClient` 인스턴스를 사용 하 여 동시에 실행 되는 것을 확인할 수 있습니다. 그러나 서비스 메시에서는 이러한 요청이 분산 되지만 많은 서비스 인스턴스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-125">In fact, if you review the code, you'll see that all 100 requests to the StockData service are made simultaneously using the same `HttpClient` instance, yet with the service mesh, those requests will be balanced across however many service instances are available.</span></span>

<span data-ttu-id="4baf7-126">서비스 메시는 클러스터 내의 트래픽에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-126">Service meshes only apply to traffic within a cluster.</span></span> <span data-ttu-id="4baf7-127">외부 클라이언트의 경우 [다음 챕터 부하 분산을](load-balancing.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4baf7-127">For external clients, see [the next chapter, Load Balancing](load-balancing.md).</span></span>

## <a name="service-mesh-options"></a><span data-ttu-id="4baf7-128">서비스 메시 옵션</span><span class="sxs-lookup"><span data-stu-id="4baf7-128">Service mesh options</span></span>

<span data-ttu-id="4baf7-129">현재 Kubernetes: Istio, Linkerd 및 Consul Connect와 함께 사용할 수 있는 세 가지 범용 서비스 메시 구현이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-129">There are three general-purpose service mesh implementations currently available for use with Kubernetes: Istio, Linkerd, and Consul Connect.</span></span> <span data-ttu-id="4baf7-130">세 가지 모두 요청 라우팅/프록시, 트래픽 암호화, 복원 력, 호스트 간 인증 및 트래픽 제어를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-130">All three provide request routing/proxying, traffic encryption, resilience, host-to-host authentication, and traffic control.</span></span>

<span data-ttu-id="4baf7-131">서비스 메시를 선택 하는 것은 여러 요소에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-131">Choosing a service mesh depends multiple factors:</span></span>

- <span data-ttu-id="4baf7-132">비용, 규정 준수, 유료 지원 계획 등의 조직의 특정 요구 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-132">The organization's specific requirements around costs, compliance, paid support plans, and so on.</span></span>
- <span data-ttu-id="4baf7-133">클러스터의 특성, 크기, 배포 된 서비스 수 및 클러스터 네트워크 내의 트래픽 양에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-133">The nature of the cluster, its size, the number of services deployed, and the volume of traffic within the cluster network.</span></span>
- <span data-ttu-id="4baf7-134">메시를 쉽게 배포 및 관리 하 고 서비스에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-134">Ease of deploying and managing the mesh and using it with services.</span></span>

<span data-ttu-id="4baf7-135">각 서비스 메시에 대 한 자세한 내용은 해당 웹 사이트에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-135">More information on each service mesh is available from their respective websites.</span></span>

- [<span data-ttu-id="4baf7-136">**Istio** -istio.io</span><span class="sxs-lookup"><span data-stu-id="4baf7-136">**Istio** - istio.io</span></span>](https://istio.io)
- [<span data-ttu-id="4baf7-137">**Linkerd** -linkerd.io</span><span class="sxs-lookup"><span data-stu-id="4baf7-137">**Linkerd** - linkerd.io</span></span>](https://linkerd.io)
- [<span data-ttu-id="4baf7-138">**Consul** -consul.io/mesh.html</span><span class="sxs-lookup"><span data-stu-id="4baf7-138">**Consul** - consul.io/mesh.html</span></span>](https://consul.io/mesh.html)

## <a name="example-add-linkerd-to-a-deployment"></a><span data-ttu-id="4baf7-139">예: Linkerd를 배포에 추가</span><span class="sxs-lookup"><span data-stu-id="4baf7-139">Example: add Linkerd to a deployment</span></span>

<span data-ttu-id="4baf7-140">이 예제에서는 [이전 섹션](kubernetes.md)의 *StockKube* 응용 프로그램과 함께 linkerd 서비스 메시를 사용 하는 방법에 대해 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-140">In this example, you'll learn how to use the Linkerd service mesh with the *StockKube* application from [the previous section](kubernetes.md).</span></span>
<span data-ttu-id="4baf7-141">이 예제를 따르려면 [Linkerd CLI를 설치](https://linkerd.io/2/getting-started/#step-1-install-the-cli)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-141">To follow this example, you'll need to [install the Linkerd CLI](https://linkerd.io/2/getting-started/#step-1-install-the-cli).</span></span> <span data-ttu-id="4baf7-142">Windows 이진 파일은 GitHub 릴리스 섹션에서 다운로드할 수 있습니다. edge 릴리스 중 하나가 아니라 **안정적인** 최신 릴리스를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-142">Windows binaries can be downloaded from the GitHub releases section; make sure to use the most recent **stable** release and not one of the edge releases.</span></span>

<span data-ttu-id="4baf7-143">Linkerd CLI가 설치 된 상태에서 [Linkerd 웹 사이트의*시작* 지침]을 따라 Kubernetes 클러스터에 linkerd 구성 요소를 설치 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-143">With the Linkerd CLI installed, follow the [*Getting Started* instructions on the Linkerd web site] to install the Linkerd components on your Kubernetes cluster.</span></span> <span data-ttu-id="4baf7-144">지침은 로컬 Kubernetes 인스턴스에서 몇 분 정도 소요 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-144">The instructions are straight-forward and installation should only take a couple of minutes on a local Kubernetes instance.</span></span>

### <a name="add-linkerd-to-kubernetes-deployments"></a><span data-ttu-id="4baf7-145">Kubernetes 배포에 Linkerd 추가</span><span class="sxs-lookup"><span data-stu-id="4baf7-145">Add Linkerd to Kubernetes deployments</span></span>

<span data-ttu-id="4baf7-146">Linkerd CLI는 Kubernetes 파일에 필요한 섹션과 속성을 추가 하는 `inject` 명령을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-146">The Linkerd CLI provides an `inject` command to add the necessary sections and properties to Kubernetes files.</span></span> <span data-ttu-id="4baf7-147">명령을 실행 하 고 새 파일에 출력을 쓸 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-147">You can run the command and write the output to a new file.</span></span>

```console
linkerd inject stockdata.yml > stockdata-with-mesh.yml
linkerd inject stockweb.yml > stockweb-with-mesh.yml
```

<span data-ttu-id="4baf7-148">새 파일을 검사 하 여 변경한 내용을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-148">You can inspect the new files to see what changes have been made.</span></span> <span data-ttu-id="4baf7-149">배포 개체의 경우 Linkerd가 생성 될 때 Pod에 사이드카 proxy 컨테이너를 삽입 하도록 메타 데이터 주석이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-149">For Deployment objects, a metadata annotation is added to tell Linkerd to inject a sidecar proxy container into the Pod when it's created.</span></span>

<span data-ttu-id="4baf7-150">`linkerd inject` 명령의 출력을 직접 `kubectl`로 파이프 하는 것도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-150">It's also possible to pipe the output of the `linkerd inject` command to `kubectl` directly.</span></span> <span data-ttu-id="4baf7-151">다음 명령은 PowerShell 또는 모든 Linux 셸에서 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-151">The following commands will work in PowerShell or any Linux shell.</span></span>

```console
linkerd inject stockdata.yml | kubectl apply -f -
linkerd inject stockweb.yml | kubectl apply -f -
```

### <a name="inspect-services-in-the-linkerd-dashboard"></a><span data-ttu-id="4baf7-152">Linkerd 대시보드의 서비스 검사</span><span class="sxs-lookup"><span data-stu-id="4baf7-152">Inspect services in the Linkerd dashboard</span></span>

<span data-ttu-id="4baf7-153">`linkerd` CLI를 사용 하 여 Linkerd 대시보드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-153">Launch the Linkerd dashboard using the `linkerd` CLI.</span></span>

```console
linkerd dashboard
```

<span data-ttu-id="4baf7-154">대시보드는 메시에 연결 된 모든 서비스에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4baf7-154">The dashboard provides detailed information about all services that are connected to the mesh.</span></span>

![StockKube 응용 프로그램을 보여 주는 linkerd 대시보드](media/service-mesh/linkerd-screenshot.png)

<span data-ttu-id="4baf7-156">다음 예제와 같이 StockData gRPC 서비스의 복제본 수를 늘리고 브라우저에서 StockWeb 페이지를 새로 고치면 서버 열에 Id가 혼합 되어 있어 사용 가능한 모든 인스턴스에서 요청이 처리 되 고 있음을 알 수 있습니다. .</span><span class="sxs-lookup"><span data-stu-id="4baf7-156">If you increase the number of replicas of the StockData gRPC service as shown in the following example, and refresh the StockWeb page in the browser, you should see a mix of IDs in the Server column, indicating that requests are being served by all the available instances.</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: stockdata
  namespace: stocks
spec:
  selector:
    matchLabels:
      run: stockdata
  replicas: 2 # Increase the target number of instances
  template:
    metadata:
      annotations:
        linkerd.io/inject: enabled
      creationTimestamp: null
      labels:
        run: stockdata
    spec:
      containers:
      - name: stockdata
        image: stockdata:1.0.0
        imagePullPolicy: Never
        resources:
          limits:
            cpu: 100m
            memory: 100Mi
        ports:
        - containerPort: 80
```

>[!div class="step-by-step"]
><span data-ttu-id="4baf7-157">[이전](kubernetes.md)
>[다음](load-balancing.md)</span><span class="sxs-lookup"><span data-stu-id="4baf7-157">[Previous](kubernetes.md)
[Next](load-balancing.md)</span></span>
