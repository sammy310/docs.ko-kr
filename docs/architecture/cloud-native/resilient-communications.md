---
title: 복원력 있는 통신
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 복원 력 있는 통신
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 33e4c03c1f3d8c01f72c588326fbb0bdfa512cdd
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613748"
---
# <a name="resilient-communications"></a><span data-ttu-id="aa081-103">복원 력 있는 통신</span><span class="sxs-lookup"><span data-stu-id="aa081-103">Resilient communications</span></span>

<span data-ttu-id="aa081-104">이 책 전체에서 마이크로 서비스 기반 아키텍처 접근 방식을 받아들이고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-104">Throughout this book, we've embraced a microservice-based architectural approach.</span></span> <span data-ttu-id="aa081-105">이러한 아키텍처는 중요 한 이점을 제공 하지만 많은 문제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-105">While such an architecture provides important benefits, it presents many challenges:</span></span>

- <span data-ttu-id="aa081-106">*Out-of-process 네트워크 통신.*</span><span class="sxs-lookup"><span data-stu-id="aa081-106">*Out-of-process network communication.*</span></span> <span data-ttu-id="aa081-107">각 마이크로 서비스는 네트워크 정체, 대기 시간 및 일시적인 오류를 소개 하는 네트워크 프로토콜을 통해 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-107">Each microservice communicates over a network protocol that introduces network congestion, latency, and transient faults.</span></span>

- <span data-ttu-id="aa081-108">*서비스 검색.*</span><span class="sxs-lookup"><span data-stu-id="aa081-108">*Service discovery.*</span></span> <span data-ttu-id="aa081-109">자체 IP 주소 및 포트가 있는 컴퓨터 클러스터에서 실행 될 때 마이크로 서비스에서 서로를 검색 하 고 통신 하는 방법</span><span class="sxs-lookup"><span data-stu-id="aa081-109">How do microservices discover and communicate with each other when running across a cluster of machines with their own IP addresses and ports?</span></span>

- <span data-ttu-id="aa081-110">*복구.*</span><span class="sxs-lookup"><span data-stu-id="aa081-110">*Resiliency.*</span></span> <span data-ttu-id="aa081-111">단기 오류를 관리 하 고 시스템을 안정적으로 유지 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="aa081-111">How do you manage short-lived failures and keep the system stable?</span></span>

- <span data-ttu-id="aa081-112">*부하 분산.*</span><span class="sxs-lookup"><span data-stu-id="aa081-112">*Load balancing.*</span></span> <span data-ttu-id="aa081-113">인바운드 트래픽은 마이크로 서비스의 여러 인스턴스에 걸쳐 어떻게 분산 되나요?</span><span class="sxs-lookup"><span data-stu-id="aa081-113">How does inbound traffic get distributed across multiple instances of a microservice?</span></span>

- <span data-ttu-id="aa081-114">*보안.*</span><span class="sxs-lookup"><span data-stu-id="aa081-114">*Security.*</span></span> <span data-ttu-id="aa081-115">전송 수준 암호화 및 인증서 관리와 같은 보안 문제는 어떻게 적용 되나요?</span><span class="sxs-lookup"><span data-stu-id="aa081-115">How are security concerns such as transport-level encryption and certificate management enforced?</span></span>

- <span data-ttu-id="aa081-116">*분산 모니터링.*</span><span class="sxs-lookup"><span data-stu-id="aa081-116">*Distributed Monitoring.*</span></span> <span data-ttu-id="aa081-117">-여러 사용 마이크로 서비스에서 단일 요청에 대 한 추적 및 모니터링의 상관 관계를 어떻게 파악 하 고 캡처해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="aa081-117">- How do you correlate and capture traceability and monitoring for a single request across multiple consuming microservices?</span></span>

<span data-ttu-id="aa081-118">다양 한 라이브러리 및 프레임 워크를 사용 하 여 이러한 문제를 해결할 수 있지만 구현에는 비용이 많이 들고 복잡 하며 시간이 많이 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-118">You can address these concerns with different libraries and frameworks, but the implementation can be expensive, complex, and time-consuming.</span></span> <span data-ttu-id="aa081-119">비즈니스 논리에 결합 된 인프라 문제도 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-119">You also end up with infrastructure concerns coupled to business logic.</span></span>

## <a name="service-mesh"></a><span data-ttu-id="aa081-120">서비스 메시</span><span class="sxs-lookup"><span data-stu-id="aa081-120">Service mesh</span></span>

<span data-ttu-id="aa081-121">더 나은 방법은 *서비스 메시*의 진화 하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-121">A better approach is an evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="aa081-122">[서비스 메시](https://www.nginx.com/blog/what-is-a-service-mesh/) 는 서비스 통신 및 위에서 언급 한 기타 과제를 처리 하는 기본 제공 기능이 포함 된 구성 가능한 인프라 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-122">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service communication and the other challenges mentioned above.</span></span> <span data-ttu-id="aa081-123">이러한 문제를 서비스 프록시로 이동 하 여 이러한 문제를 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-123">It decouples these concerns by moving them into a service proxy.</span></span> <span data-ttu-id="aa081-124">프록시는 비즈니스 코드에서 격리를 제공 하기 위해 별도의 프로세스 ( [사이드카](https://docs.microsoft.com/azure/architecture/patterns/sidecar)라고 함)에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-124">The proxy is deployed into a separate process (called a [sidecar](https://docs.microsoft.com/azure/architecture/patterns/sidecar)) to provide isolation from business code.</span></span> <span data-ttu-id="aa081-125">그러나 사이드카는 서비스에 연결 되며,이를 사용 하 여 생성 되 고 수명 주기를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-125">However, the sidecar is linked to the service - it's created with it and shares its lifecycle.</span></span> <span data-ttu-id="aa081-126">그림 6-7에서는이 시나리오를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-126">Figure 6-7 shows this scenario.</span></span>

![측 자동차를 사용 하는 서비스 메시](./media/service-mesh-with-side-car.png)

<span data-ttu-id="aa081-128">**그림 6-7**</span><span class="sxs-lookup"><span data-stu-id="aa081-128">**Figure 6-7**.</span></span> <span data-ttu-id="aa081-129">측 자동차를 사용 하는 서비스 메시</span><span class="sxs-lookup"><span data-stu-id="aa081-129">Service mesh with a side car</span></span>

<span data-ttu-id="aa081-130">위의 그림에서 프록시는 마이크로 서비스와 클러스터 간의 통신을 차단 하 고 관리 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-130">In the previous figure, note how the proxy intercepts and manages communication among the microservices and the cluster.</span></span>

<span data-ttu-id="aa081-131">서비스 메시는 논리적으로 서로 다른 두 구성 요소인 [데이터 평면과](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) [컨트롤 평면](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc)으로 분할 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-131">A service mesh is logically split into two disparate components: A [data plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc) and [control plane](https://blog.envoyproxy.io/service-mesh-data-plane-vs-control-plane-2774e720f7fc).</span></span> <span data-ttu-id="aa081-132">그림 6-8에서는 이러한 구성 요소와 해당 책임을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-132">Figure 6-8 shows these components and their responsibilities.</span></span>

![서비스 메시 컨트롤 및 데이터 평면](./media/istio-control-and-data-plane.png)

<span data-ttu-id="aa081-134">**그림 6-8.**</span><span class="sxs-lookup"><span data-stu-id="aa081-134">**Figure 6-8.**</span></span> <span data-ttu-id="aa081-135">서비스 메시 컨트롤 및 데이터 평면</span><span class="sxs-lookup"><span data-stu-id="aa081-135">Service mesh control and data plane</span></span>

<span data-ttu-id="aa081-136">구성 된 후에는 서비스 메쉬가 매우 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-136">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="aa081-137">서비스 검색 끝점에서 인스턴스의 해당 풀을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-137">It can retrieve a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="aa081-138">그런 다음 메시는 특정 인스턴스에 요청을 보내 결과의 대기 시간 및 응답 유형을 기록할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-138">The mesh can then send a request to a specific instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="aa081-139">메시는 최근 요청에 대 한 관찰 된 대기 시간을 비롯 하 여 많은 요소를 기준으로 빠른 응답을 반환할 가능성이 가장 높은 인스턴스를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-139">A mesh can choose the instance most likely to return a fast response based on many factors, including its observed latency for recent requests.</span></span>

<span data-ttu-id="aa081-140">인스턴스가 응답 하지 않거나 실패 하면 메시는 다른 인스턴스에서 요청을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-140">If an instance is unresponsive or fails, the mesh will retry the request on another instance.</span></span> <span data-ttu-id="aa081-141">오류가 반환 되 면 메시는 로드 균형 조정 풀에서 인스턴스를 제거 하 고 치료 된 후에 다시 말하지만 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-141">If it returns errors, a mesh will evict the instance from the load-balancing pool and restate it after it heals.</span></span> <span data-ttu-id="aa081-142">요청 시간이 초과 되 면 메시에 실패할 수 있습니다. 그런 다음 요청을 다시 시도 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-142">If a request times out, a mesh can fail and then retry the request.</span></span> <span data-ttu-id="aa081-143">메시는 메트릭 및 분산 추적을 캡처하여 중앙 메트릭 시스템으로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-143">A mesh captures and emits metrics and distributed tracing to a centralized metrics system.</span></span>

## <a name="istio-and-envoy"></a><span data-ttu-id="aa081-144">Istio 및 엔보이</span><span class="sxs-lookup"><span data-stu-id="aa081-144">Istio and Envoy</span></span>

<span data-ttu-id="aa081-145">몇 가지 서비스 메시 옵션이 현재 존재 하지만이 문서를 작성할 당시에는 [Istio](https://istio.io/docs/concepts/what-is-istio/) 가 가장 인기 있는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-145">While a few service mesh options currently exist, [Istio](https://istio.io/docs/concepts/what-is-istio/) is the most popular at the time of this writing.</span></span> <span data-ttu-id="aa081-146">Istio는 IBM, Google 및 Lyft의 공동 공동입니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-146">Istio is a joint venture from IBM, Google, and Lyft.</span></span> <span data-ttu-id="aa081-147">새 배포 응용 프로그램 또는 기존 응용 프로그램에 통합 될 수 있는 오픈 소스 제품입니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-147">It's an open-source offering that can be integrated into a new or existing distributed application.</span></span> <span data-ttu-id="aa081-148">이 기술은 마이크로 서비스를 보호, 연결 및 모니터링 하기 위한 일관 되 고 완전 한 솔루션을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-148">The technology provides a consistent and complete solution to secure, connect, and monitor microservices.</span></span> <span data-ttu-id="aa081-149">해당 기능에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-149">Its features include:</span></span>

- <span data-ttu-id="aa081-150">강력한 id 기반 인증 및 권한 부여를 사용 하 여 클러스터에서 서비스 간 통신을 보호 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-150">Secure service-to-service communication in a cluster with strong identity-based authentication and authorization.</span></span>
- <span data-ttu-id="aa081-151">HTTP, [Grpc](https://grpc.io/), WEBSOCKET 및 TCP 트래픽에 대 한 자동 부하 분산.</span><span class="sxs-lookup"><span data-stu-id="aa081-151">Automatic load balancing for HTTP, [gRPC](https://grpc.io/), WebSocket, and TCP traffic.</span></span>
- <span data-ttu-id="aa081-152">풍부한 라우팅 규칙, 다시 시도, 장애 조치 (failover) 및 오류 주입을 통해 트래픽 동작을 세부적으로 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-152">Fine-grained control of traffic behavior with rich routing rules, retries, failovers, and fault injection.</span></span>
- <span data-ttu-id="aa081-153">액세스 제어, 요율 제한 및 할당량을 지 원하는 플러그형 정책 계층 및 구성 API</span><span class="sxs-lookup"><span data-stu-id="aa081-153">A pluggable policy layer and configuration API supporting access controls, rate limits, and quotas.</span></span>
- <span data-ttu-id="aa081-154">클러스터 수신 및 송신을 포함 하 여 클러스터 내의 모든 트래픽에 대 한 자동 메트릭, 로그 및 추적</span><span class="sxs-lookup"><span data-stu-id="aa081-154">Automatic metrics, logs, and traces for all traffic within a cluster, including cluster ingress and egress.</span></span>

<span data-ttu-id="aa081-155">Istio 구현에 대 한 주요 구성 요소는 [엔보이 프록시](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)를 담당 하는 프록시 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-155">A key component for an Istio implementation is a proxy service entitled the [Envoy proxy](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy).</span></span> <span data-ttu-id="aa081-156">각 서비스와 함께 실행 되며 다음과 같은 기능에 대 한 플랫폼 독립적인 토대를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-156">It runs alongside each service and provides a platform-agnostic foundation for the following features:</span></span>

- <span data-ttu-id="aa081-157">동적 서비스 검색.</span><span class="sxs-lookup"><span data-stu-id="aa081-157">Dynamic service discovery.</span></span>
- <span data-ttu-id="aa081-158">부하 분산 -</span><span class="sxs-lookup"><span data-stu-id="aa081-158">Load balancing.</span></span>
- <span data-ttu-id="aa081-159">TLS 종료.</span><span class="sxs-lookup"><span data-stu-id="aa081-159">TLS termination.</span></span>
- <span data-ttu-id="aa081-160">HTTP 및 gRPC 프록시.</span><span class="sxs-lookup"><span data-stu-id="aa081-160">HTTP and gRPC proxies.</span></span>
- <span data-ttu-id="aa081-161">회로 차단기 복원 력.</span><span class="sxs-lookup"><span data-stu-id="aa081-161">Circuit breaker resiliency.</span></span>
- <span data-ttu-id="aa081-162">상태 검사.</span><span class="sxs-lookup"><span data-stu-id="aa081-162">Health checks.</span></span>
- <span data-ttu-id="aa081-163">[카나리아](https://martinfowler.com/bliki/CanaryRelease.html) 배포를 사용 하 여 업데이트를 롤링 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-163">Rolling updates with [canary](https://martinfowler.com/bliki/CanaryRelease.html) deployments.</span></span>

<span data-ttu-id="aa081-164">앞에서 설명한 것 처럼 엔보이는 클러스터의 각 마이크로 서비스에 대 한 사이드카으로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-164">As previously discussed, Envoy is deployed as a sidecar to each microservice in the cluster.</span></span>

## <a name="integration-with-azure-kubernetes-services"></a><span data-ttu-id="aa081-165">Azure Kubernetes Services와의 통합</span><span class="sxs-lookup"><span data-stu-id="aa081-165">Integration with Azure Kubernetes Services</span></span>

<span data-ttu-id="aa081-166">Azure cloud는 Istio를 수용 하 고 Azure Kubernetes 서비스 내에서이를 직접 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-166">The Azure cloud embraces Istio and provides direct support for it within Azure Kubernetes Services.</span></span> <span data-ttu-id="aa081-167">다음 링크를 통해 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa081-167">The following links can help you get started:</span></span>

- [<span data-ttu-id="aa081-168">AKS에 Istio 설치</span><span class="sxs-lookup"><span data-stu-id="aa081-168">Installing Istio in AKS</span></span>](https://docs.microsoft.com/azure/aks/istio-install)
- [<span data-ttu-id="aa081-169">AKS 및 Istio 사용</span><span class="sxs-lookup"><span data-stu-id="aa081-169">Using AKS and Istio</span></span>](https://docs.microsoft.com/azure/aks/istio-scenario-routing)

### <a name="references"></a><span data-ttu-id="aa081-170">참조</span><span class="sxs-lookup"><span data-stu-id="aa081-170">References</span></span>

- [<span data-ttu-id="aa081-171">Polly</span><span class="sxs-lookup"><span data-stu-id="aa081-171">Polly</span></span>](http://www.thepollyproject.org/)

- [<span data-ttu-id="aa081-172">다시 시도 패턴</span><span class="sxs-lookup"><span data-stu-id="aa081-172">Retry pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/retry)

- [<span data-ttu-id="aa081-173">회로 차단기 패턴</span><span class="sxs-lookup"><span data-stu-id="aa081-173">Circuit Breaker pattern</span></span>](https://docs.microsoft.com/azure/architecture/patterns/circuit-breaker)

- [<span data-ttu-id="aa081-174">Azure의 복원 력</span><span class="sxs-lookup"><span data-stu-id="aa081-174">Resilience in Azure whitepaper</span></span>](https://azure.microsoft.com/mediahandler/files/resourcefiles/resilience-in-azure-whitepaper/Resilience%20in%20Azure.pdf)

- [<span data-ttu-id="aa081-175">네트워크 대기 시간</span><span class="sxs-lookup"><span data-stu-id="aa081-175">network latency</span></span>](https://www.techopedia.com/definition/8553/network-latency)

- [<span data-ttu-id="aa081-176">중복</span><span class="sxs-lookup"><span data-stu-id="aa081-176">Redundancy</span></span>](https://docs.microsoft.com/azure/architecture/guide/design-principles/redundancy)

- [<span data-ttu-id="aa081-177">지역에서 복제</span><span class="sxs-lookup"><span data-stu-id="aa081-177">geo-replication</span></span>](https://docs.microsoft.com/azure/sql-database/sql-database-active-geo-replication)

- [<span data-ttu-id="aa081-178">Azure Traffic Manager</span><span class="sxs-lookup"><span data-stu-id="aa081-178">Azure Traffic Manager</span></span>](https://docs.microsoft.com/azure/traffic-manager/traffic-manager-overview)

- [<span data-ttu-id="aa081-179">자동 크기 조정 지침</span><span class="sxs-lookup"><span data-stu-id="aa081-179">Autoscaling guidance</span></span>](https://docs.microsoft.com/azure/architecture/best-practices/auto-scaling)

- [<span data-ttu-id="aa081-180">Istio</span><span class="sxs-lookup"><span data-stu-id="aa081-180">Istio</span></span>](https://istio.io/docs/concepts/what-is-istio/)

- [<span data-ttu-id="aa081-181">엔보이 프록시</span><span class="sxs-lookup"><span data-stu-id="aa081-181">Envoy proxy</span></span>](https://www.envoyproxy.io/docs/envoy/latest/intro/what_is_envoy)

>[!div class="step-by-step"]
><span data-ttu-id="aa081-182">[이전](infrastructure-resiliency-azure.md)
>[다음](monitoring-health.md)</span><span class="sxs-lookup"><span data-stu-id="aa081-182">[Previous](infrastructure-resiliency-azure.md)
[Next](monitoring-health.md)</span></span>
