---
title: 서비스 메시 통신 인프라
description: 서비스 메시 기술이 클라우드 네이티브 마이크로 서비스 통신을 간소화하는 방법에 대해 알아봅니다.
author: robvet
ms.date: 03/03/2020
ms.openlocfilehash: 8bb57e990dbf1baf8c246fe4aacfbb2904a251e6
ms.sourcegitcommit: f87ad41b8e62622da126aa928f7640108c4eff98
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "80805758"
---
# <a name="service-mesh-communication-infrastructure"></a><span data-ttu-id="ed83e-103">서비스 메시 통신 인프라</span><span class="sxs-lookup"><span data-stu-id="ed83e-103">Service Mesh communication infrastructure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="ed83e-104">이 장에서는 마이크로 서비스 통신의 과제를 탐구했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-104">Throughout this chapter, we've explored the challenges of microservice communication.</span></span> <span data-ttu-id="ed83e-105">개발 팀은 백 엔드 서비스가 서로 통신하는 방식에 민감해야 한다고 말했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-105">We said that development teams need to be sensitive to how back-end services communicate with each other.</span></span> <span data-ttu-id="ed83e-106">이상적으로는 서비스 간 통신이 적을수록 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-106">Ideally, the less inter-service communication, the better.</span></span> <span data-ttu-id="ed83e-107">그러나 백 엔드 서비스가 작업을 완료하기 위해 서로 의존하는 경우가 많기 때문에 항상 피할 수 있는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-107">However, avoidance isn't always possible as back-end services often rely on one another to complete operations.</span></span>

<span data-ttu-id="ed83e-108">동기 HTTP 통신 및 비동기 메시징을 구현하기 위한 다양한 방법을 살펴봤습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-108">We explored different approaches for implementing synchronous HTTP communication and asynchronous messaging.</span></span> <span data-ttu-id="ed83e-109">각 경우에 개발자는 통신 코드를 구현해야 하는 부담을 안고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-109">In each of the cases, the developer is burdened with implementing communication code.</span></span> <span data-ttu-id="ed83e-110">통신 코드는 복잡하고 시간이 많이 많이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-110">Communication code is complex and time intensive.</span></span> <span data-ttu-id="ed83e-111">잘못된 결정은 심각한 성능 문제를 초래할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-111">Incorrect decisions can lead to significant performance issues.</span></span>

<span data-ttu-id="ed83e-112">마이크로 서비스 통신에 대한 보다 현대적인 접근 방식은 서비스 *메시라는*새롭고 빠르게 진화하는 기술을 중심으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-112">A more modern approach to microservice communication centers around a new and rapidly evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="ed83e-113">[서비스 메시는](https://www.nginx.com/blog/what-is-a-service-mesh/) 서비스 간 통신, 복원력 및 많은 교차 절단 문제를 처리하는 기능이 내장된 구성 가능한 인프라 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-113">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service-to-service communication, resiliency, and many cross-cutting concerns.</span></span> <span data-ttu-id="ed83e-114">이러한 우려에 대한 책임은 마이크로 서비스에서 서비스 메시 계층으로 이동합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-114">It moves the responsibility for these concerns out of the microservices and into service mesh layer.</span></span> <span data-ttu-id="ed83e-115">통신은 마이크로 서비스에서 멀리 추상화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-115">Communication is abstracted away from your microservices.</span></span>

<span data-ttu-id="ed83e-116">서비스 메시의 핵심 구성 요소는 프록시입니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-116">A key component of a service mesh is a proxy.</span></span> <span data-ttu-id="ed83e-117">클라우드 네이티브 응용 프로그램에서 프록시 인스턴스는 일반적으로 각 마이크로 서비스와 공존합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-117">In a cloud-native application, an instance of a proxy is typically colocated with each microservice.</span></span> <span data-ttu-id="ed83e-118">두 프로세스는 별도의 프로세스에서 실행되는 동안 밀접하게 연결되어 동일한 수명 주기를 공유합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-118">While they execute in separate processes, the two are closely linked and share the same lifecycle.</span></span> <span data-ttu-id="ed83e-119">사이드카 [패턴이라고](https://docs.microsoft.com/azure/architecture/patterns/sidecar)하는 이 패턴은 도 4-24에 도시되어 있다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-119">This pattern, known as the [Sidecar pattern](https://docs.microsoft.com/azure/architecture/patterns/sidecar), and is shown in Figure 4-24.</span></span>

![사이드 카가 있는 서비스 메쉬](./media/service-mesh-with-side-car.png)

<span data-ttu-id="ed83e-121">**그림 4-24**</span><span class="sxs-lookup"><span data-stu-id="ed83e-121">**Figure 4-24**.</span></span> <span data-ttu-id="ed83e-122">사이드 카가 있는 서비스 메쉬</span><span class="sxs-lookup"><span data-stu-id="ed83e-122">Service mesh with a side car</span></span>

<span data-ttu-id="ed83e-123">이전 그림에서는 각 마이크로 서비스와 함께 실행되는 프록시에 의해 메시지가 가로채는 방법을 참고합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-123">Note in the previous figure how messages are intercepted by a proxy that runs alongside each microservice.</span></span> <span data-ttu-id="ed83e-124">각 프록시는 마이크로 서비스와 관련된 트래픽 규칙으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-124">Each proxy can be configured with traffic rules specific to the microservice.</span></span> <span data-ttu-id="ed83e-125">메시지를 이해하고 서비스 및 외부 세계로 메시지를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-125">It understands messages and can route them across your services and the outside world.</span></span>

<span data-ttu-id="ed83e-126">서비스 간 통신 관리와 함께 서비스 메시는 서비스 검색 및 부하 분산을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-126">Along with managing service-to-service communication, the Service Mesh provides support for service discovery and load balancing.</span></span>

<span data-ttu-id="ed83e-127">일단 구성되면 서비스 메시는 매우 기능적입니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-127">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="ed83e-128">메시는 서비스 검색 끝점에서 해당 인스턴스 풀을 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-128">The mesh retrieves a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="ed83e-129">결과의 대기 시간 및 응답 유형을 기록하는 특정 서비스 인스턴스에 요청을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-129">It sends a request to a specific service instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="ed83e-130">최근 요청에 대한 관찰된 대기 시간을 포함하여 여러 요인에 따라 빠른 응답을 반환할 가능성이 가장 높은 인스턴스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-130">It chooses the instance most likely to return a fast response based on different factors, including the observed latency for recent requests.</span></span>

<span data-ttu-id="ed83e-131">서비스 메시는 응용 프로그램 수준에서 트래픽, 통신 및 네트워킹 문제를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-131">A service mesh manages traffic, communication, and networking concerns at the application level.</span></span> <span data-ttu-id="ed83e-132">메시지와 요청을 이해합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-132">It understands messages and requests.</span></span> <span data-ttu-id="ed83e-133">서비스 메시는 일반적으로 컨테이너 오케스트레이터와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-133">A service mesh typically integrates with a container orchestrator.</span></span> <span data-ttu-id="ed83e-134">Kubernetes는 서비스 메시를 추가할 수 있는 확장 가능한 아키텍처를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-134">Kubernetes supports an extensible architecture in which a service mesh can be added.</span></span>

<span data-ttu-id="ed83e-135">6장에서는 아키텍처 및 사용 가능한 오픈 소스 구현에 대한 토론을 포함하여 서비스 메시 기술에 대해 자세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-135">In chapter 6, we deep-dive into Service Mesh technologies including a discussion on its architecture and available open-source implementations.</span></span>

## <a name="summary"></a><span data-ttu-id="ed83e-136">요약</span><span class="sxs-lookup"><span data-stu-id="ed83e-136">Summary</span></span>

<span data-ttu-id="ed83e-137">이 장에서는 클라우드 네이티브 통신 패턴에 대해 설명했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-137">In this chapter, we discussed cloud-native communication patterns.</span></span> <span data-ttu-id="ed83e-138">프론트 엔드 클라이언트가 백 엔드 마이크로 서비스와 통신하는 방법을 검토하는 것으로 시작했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-138">We started by examining how front-end clients communicate with back-end microservices.</span></span> <span data-ttu-id="ed83e-139">그 과정에서 API 게이트웨이 플랫폼과 실시간 통신에 대해 이야기했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-139">Along the way, we talked about API Gateway platforms and real-time communication.</span></span> <span data-ttu-id="ed83e-140">그런 다음 마이크로 서비스가 다른 백 엔드 서비스와 통신하는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-140">We then looked at how microservices communicate with other back-end services.</span></span> <span data-ttu-id="ed83e-141">서비스 간에 동기 HTTP 통신과 비동기 메시징을 모두 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-141">We looked at both synchronous HTTP communication and asynchronous messaging across services.</span></span> <span data-ttu-id="ed83e-142">우리는 클라우드 네이티브 세계에서 곧 출시될 기술인 gRPC를 다루었습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-142">We covered gRPC, an upcoming technology in the cloud-native world.</span></span> <span data-ttu-id="ed83e-143">마지막으로 마이크로 서비스 통신을 간소화할 수 있는 서비스 메시라는 새롭고 빠르게 진화하는 기술을 도입했습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-143">Finally, we introduced a new and rapidly evolving technology entitled Service Mesh that can streamline microservice communication.</span></span>

<span data-ttu-id="ed83e-144">특히 클라우드 네이티브 시스템에서 통신을 구현하는 데 도움이 되는 관리되는 Azure 서비스에 중점을 두는 데 중점을 두어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-144">Special emphasis was on managed Azure services that can help implement communication in cloud-native systems:</span></span>

- [<span data-ttu-id="ed83e-145">Azure 응용 프로그램 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="ed83e-145">Azure Application Gateway</span></span>](https://docs.microsoft.com/azure/application-gateway/overview)
- [<span data-ttu-id="ed83e-146">Azure API Management</span><span class="sxs-lookup"><span data-stu-id="ed83e-146">Azure API Management</span></span>](https://azure.microsoft.com/services/api-management/)
- [<span data-ttu-id="ed83e-147">Azure SignalR Service</span><span class="sxs-lookup"><span data-stu-id="ed83e-147">Azure SignalR Service</span></span>](https://azure.microsoft.com/services/signalr-service/)
- [<span data-ttu-id="ed83e-148">Azure Storage 큐</span><span class="sxs-lookup"><span data-stu-id="ed83e-148">Azure Storage Queues</span></span>](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [<span data-ttu-id="ed83e-149">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="ed83e-149">Azure Service Bus</span></span>](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [<span data-ttu-id="ed83e-150">Azure Event Grid</span><span class="sxs-lookup"><span data-stu-id="ed83e-150">Azure Event Grid</span></span>](https://docs.microsoft.com/azure/event-grid/overview)
- [<span data-ttu-id="ed83e-151">Azure 이벤트 허브</span><span class="sxs-lookup"><span data-stu-id="ed83e-151">Azure Event Hub</span></span>](https://azure.microsoft.com/services/event-hubs/)

<span data-ttu-id="ed83e-152">다음으로 클라우드 네이티브 시스템의 분산 데이터로 이동하고 이점과 과제를 해결합니다.</span><span class="sxs-lookup"><span data-stu-id="ed83e-152">We next move to distributed data in cloud-native systems and the benefits and challenges that it presents.</span></span>

### <a name="references"></a><span data-ttu-id="ed83e-153">참조</span><span class="sxs-lookup"><span data-stu-id="ed83e-153">References</span></span>

- [<span data-ttu-id="ed83e-154">.NET 마이크로 서비스: 컨테이너화된 .NET 응용 프로그램을 위한 아키텍처</span><span class="sxs-lookup"><span data-stu-id="ed83e-154">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [<span data-ttu-id="ed83e-155">마이크로 서비스를 위한 서비스 간 통신 설계</span><span class="sxs-lookup"><span data-stu-id="ed83e-155">Designing Interservice Communication for Microservices</span></span>](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [<span data-ttu-id="ed83e-156">Azure SignalR 서비스, 실시간 기능을 추가 하기 위해 완전 관리 되는 서비스</span><span class="sxs-lookup"><span data-stu-id="ed83e-156">Azure SignalR Service, a fully managed service to add real-time functionality</span></span>](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [<span data-ttu-id="ed83e-157">Azure API 게이트웨이 도입 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="ed83e-157">Azure API Gateway Ingress Controller</span></span>](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [<span data-ttu-id="ed83e-158">Azure Kubernetes 서비스(AKS)의 침투 정보</span><span class="sxs-lookup"><span data-stu-id="ed83e-158">About Ingress in Azure Kubernetes Service (AKS)</span></span>](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [<span data-ttu-id="ed83e-159">gRPC 문서</span><span class="sxs-lookup"><span data-stu-id="ed83e-159">gRPC Documentation</span></span>](https://grpc.io/docs/guides/)

- [<span data-ttu-id="ed83e-160">WCF 개발자를 위한 gRPC</span><span class="sxs-lookup"><span data-stu-id="ed83e-160">gRPC for WCF Developers</span></span>](https://docs.microsoft.com/dotnet/architecture/grpc-for-wcf-developers/)

- [<span data-ttu-id="ed83e-161">GRPC 서비스와 HTTP API 비교</span><span class="sxs-lookup"><span data-stu-id="ed83e-161">Comparing gRPC Services with HTTP APIs</span></span>](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

- [<span data-ttu-id="ed83e-162">.NET 비디오로 gRPC 서비스 구축</span><span class="sxs-lookup"><span data-stu-id="ed83e-162">Building gRPC Services with .NET video</span></span>](https://channel9.msdn.com/Shows/The-Cloud-Native-Show/Building-Microservices-with-gRPC-and-NET)

>[!div class="step-by-step"]
><span data-ttu-id="ed83e-163">[이전](grpc.md)
>[다음](database-per-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="ed83e-163">[Previous](grpc.md)
[Next](database-per-microservice.md)</span></span>
