---
title: 서비스 메시 통신 인프라
description: Service 메시 기술이 클라우드 네이티브 마이크로 서비스 통신을 간소화 하는 방법에 대해 알아봅니다.
author: robvet
ms.date: 09/10/2019
ms.openlocfilehash: a9192bf9f5827d05b2453c796c72e11782f9f911
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/22/2019
ms.locfileid: "73841284"
---
# <a name="service-mesh-communication-infrastructure"></a><span data-ttu-id="4a0fb-103">서비스 메시 통신 인프라</span><span class="sxs-lookup"><span data-stu-id="4a0fb-103">Service Mesh communication infrastructure</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="4a0fb-104">이 장에서는 마이크로 서비스 통신의 과제를 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-104">Throughout this chapter, we've explored the challenges of microservice communication.</span></span> <span data-ttu-id="4a0fb-105">개발 팀이 백 엔드 서비스와 통신 하는 방법에 대 한 중요 한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-105">We said that development teams need to be sensitive to how back-end services communicate with each other.</span></span> <span data-ttu-id="4a0fb-106">이상적으로 서비스 간 통신은 더 효율적입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-106">Ideally, the less inter-service communication, the better.</span></span> <span data-ttu-id="4a0fb-107">그러나 백 엔드 서비스에서 작업을 완료 하기 위해 서로 의존 하는 경우가 종종 있기 때문에 방지는 항상 가능 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-107">However, avoidance isn't always possible as back-end services often rely on one another to complete operations.</span></span>

<span data-ttu-id="4a0fb-108">동기 HTTP 통신과 비동기 메시징 구현에 대 한 여러 가지 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-108">We explored different approaches for implementing synchronous HTTP communication and asynchronous messaging.</span></span> <span data-ttu-id="4a0fb-109">각 사례에서 개발자는 통신 코드 구현에 부담이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-109">In each of the cases, the developer is burdened with implementing communication code.</span></span> <span data-ttu-id="4a0fb-110">통신 코드는 복잡 하 고 시간이 많이 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-110">Communication code is complex and time intensive.</span></span> <span data-ttu-id="4a0fb-111">잘못 된 결정은 심각한 성능 문제를 일으킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-111">Incorrect decisions can lead to significant performance issues.</span></span>

<span data-ttu-id="4a0fb-112">새롭고 신속 하 게 진화 하는 기술 *서비스 메시*를 중심으로 하는 마이크로 서비스 communication의 최신 접근 방식입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-112">A more modern approach to microservice communication centers around a new and rapidly evolving technology entitled *Service Mesh*.</span></span> <span data-ttu-id="4a0fb-113">서비스 [메시](https://www.nginx.com/blog/what-is-a-service-mesh/) 는 서비스 간 통신, 복원 력 및 많은 크로스 절삭 문제를 처리 하는 기본 제공 기능이 포함 된 구성 가능한 인프라 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-113">A [service mesh](https://www.nginx.com/blog/what-is-a-service-mesh/) is a configurable infrastructure layer with built-in capabilities to handle service-to-service communication, resiliency, and many cross-cutting concerns.</span></span> <span data-ttu-id="4a0fb-114">이러한 문제에 대 한 책임을 마이크로 서비스 및 서비스 메시 계층으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-114">It moves the responsibility for these concerns out of the microservices and into service mesh layer.</span></span> <span data-ttu-id="4a0fb-115">통신은 마이크로 서비스에서 벗어나 추상화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-115">Communication is abstracted away from your microservices.</span></span>

<span data-ttu-id="4a0fb-116">서비스 메시의 주요 구성 요소는 프록시입니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-116">A key component of a service mesh is a proxy.</span></span> <span data-ttu-id="4a0fb-117">클라우드 네이티브 응용 프로그램에서 프록시 인스턴스는 일반적으로 각 마이크로 서비스와 공동 배치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-117">In a cloud-native application, an instance of a proxy is typically colocated with each microservice.</span></span> <span data-ttu-id="4a0fb-118">별도의 프로세스에서 실행 되는 동안 둘은 밀접 하 게 연결 되 고 동일한 수명 주기를 공유 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-118">While they execute in separate processes, the two are closely linked and share the same lifecycle.</span></span> <span data-ttu-id="4a0fb-119">[사이드카 패턴](https://docs.microsoft.com/azure/architecture/patterns/sidecar)이라고 하는이 패턴은 그림 4-23에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-119">This pattern, known as the [Sidecar pattern](https://docs.microsoft.com/azure/architecture/patterns/sidecar), and is shown in Figure 4-23.</span></span>

![측 자동차를 사용 하는 서비스 메시](./media/service-mesh-with-side-car.png)

<span data-ttu-id="4a0fb-121">**그림 4-23**</span><span class="sxs-lookup"><span data-stu-id="4a0fb-121">**Figure 4-23**.</span></span> <span data-ttu-id="4a0fb-122">측 자동차를 사용 하는 서비스 메시</span><span class="sxs-lookup"><span data-stu-id="4a0fb-122">Service mesh with a side car</span></span>

<span data-ttu-id="4a0fb-123">위의 그림에서는 각 마이크로 서비스 함께 실행 되는 프록시가 메시지를 가로채는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-123">Note in the previous figure how messages are intercepted by a proxy that runs alongside each microservice.</span></span> <span data-ttu-id="4a0fb-124">각 프록시는 마이크로 서비스 관련 된 트래픽 규칙을 사용 하 여 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-124">Each proxy can be configured with traffic rules specific to the microservice.</span></span> <span data-ttu-id="4a0fb-125">메시지를 이해 하 고 서비스와 외부 세계에서 메시지를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-125">It understands messages and can route them across your services and the outside world.</span></span>

<span data-ttu-id="4a0fb-126">서비스 및 서비스 간 통신 관리와 함께 서비스 메시는 서비스 검색 및 부하 분산을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-126">Along with managing service-to-service communication, the Service Mesh provides support for service discovery and load balancing.</span></span>

<span data-ttu-id="4a0fb-127">구성 된 후에는 서비스 메쉬가 매우 작동 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-127">Once configured, a service mesh is highly functional.</span></span> <span data-ttu-id="4a0fb-128">메시는 서비스 검색 끝점에서 해당 인스턴스의 풀을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-128">The mesh retrieves a corresponding pool of instances from a service discovery endpoint.</span></span> <span data-ttu-id="4a0fb-129">특정 서비스 인스턴스로 요청을 보내고 결과의 대기 시간 및 응답 유형을 기록 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-129">It sends a request to a specific service instance, recording the latency and response type of the result.</span></span> <span data-ttu-id="4a0fb-130">최근 요청에 대해 관찰 된 대기 시간을 비롯 하 여 다양 한 요인을 기반으로 빠른 응답을 반환할 가능성이 가장 높은 인스턴스를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-130">It chooses the instance most likely to return a fast response based on different factors, including the observed latency for recent requests.</span></span>

<span data-ttu-id="4a0fb-131">서비스 메시는 응용 프로그램 수준에서 트래픽, 통신 및 네트워킹 문제를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-131">A service mesh manages traffic, communication, and networking concerns at the application level.</span></span> <span data-ttu-id="4a0fb-132">메시지와 요청을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-132">It understands messages and requests.</span></span> <span data-ttu-id="4a0fb-133">일반적으로 서비스 메시는 컨테이너 orchestrator와 통합 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-133">A service mesh typically integrates with a container orchestrator.</span></span> <span data-ttu-id="4a0fb-134">Kubernetes는 서비스 메시를 추가할 수 있는 확장 가능한 아키텍처를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-134">Kubernetes supports an extensible architecture in which a service mesh can be added.</span></span>

<span data-ttu-id="4a0fb-135">6 장에서는 아키텍처와 사용 가능한 오픈 소스 구현에 대 한 논의를 포함 하 여 서비스 메시 기술에 대해 자세히 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-135">In chapter 6, we deep-dive into Service Mesh technologies including a discussion on its architecture and available open-source implementations.</span></span>

## <a name="summary"></a><span data-ttu-id="4a0fb-136">요약</span><span class="sxs-lookup"><span data-stu-id="4a0fb-136">Summary</span></span>

<span data-ttu-id="4a0fb-137">이 장에서는 클라우드 기본 통신 패턴에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-137">In this chapter, we discussed cloud-native communication patterns.</span></span> <span data-ttu-id="4a0fb-138">프런트 엔드 클라이언트가 백 엔드 마이크로 서비스와 통신 하는 방식을 검토 하 여 시작 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-138">We started by examining how front-end clients communicate with back-end microservices.</span></span> <span data-ttu-id="4a0fb-139">이 과정을 통해 API Gateway 플랫폼과 실시간 통신에 대해 알아보았습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-139">Along the way, we talked about API Gateway platforms and real-time communication.</span></span> <span data-ttu-id="4a0fb-140">그런 다음 마이크로 서비스가 다른 백 엔드 서비스와 통신 하는 방법을 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-140">We then looked at how microservices communicate with other back-end services.</span></span> <span data-ttu-id="4a0fb-141">서비스 간 동기 HTTP 통신과 비동기 메시징을 모두 살펴보았습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-141">We looked at both synchronous HTTP communication and asynchronous messaging across services.</span></span> <span data-ttu-id="4a0fb-142">클라우드 기본 세계에서 예정 된 기술인 gRPC를 다루었습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-142">We covered gRPC, an upcoming technology in the cloud-native world.</span></span> <span data-ttu-id="4a0fb-143">마지막으로 마이크로 서비스 통신을 간소화할 수 있는 새롭고 신속 하 게 진화 하는 기술 서비스 메시를 도입 했습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-143">Finally, we introduced a new and rapidly evolving technology entitled Service Mesh that can streamline microservice communication.</span></span>

<span data-ttu-id="4a0fb-144">클라우드 네이티브 시스템에서 통신을 구현 하는 데 도움이 되는 관리 되는 Azure 서비스에 대 한 특별 한 강조는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-144">Special emphasis was on managed Azure services that can help implement communication in cloud-native systems:</span></span>

- [<span data-ttu-id="4a0fb-145">Azure 애플리케이션 게이트웨이</span><span class="sxs-lookup"><span data-stu-id="4a0fb-145">Azure Application Gateway</span></span>](https://docs.microsoft.com/azure/application-gateway/overview)
- [<span data-ttu-id="4a0fb-146">Azure API Management</span><span class="sxs-lookup"><span data-stu-id="4a0fb-146">Azure API Management</span></span>](https://azure.microsoft.com/services/api-management/)
- [<span data-ttu-id="4a0fb-147">Azure SignalR Service</span><span class="sxs-lookup"><span data-stu-id="4a0fb-147">Azure SignalR Service</span></span>](https://azure.microsoft.com/services/signalr-service/)
- [<span data-ttu-id="4a0fb-148">Azure Storage 큐</span><span class="sxs-lookup"><span data-stu-id="4a0fb-148">Azure Storage Queues</span></span>](https://docs.microsoft.com/azure/storage/queues/storage-queues-introduction)
- [<span data-ttu-id="4a0fb-149">Azure Service Bus</span><span class="sxs-lookup"><span data-stu-id="4a0fb-149">Azure Service Bus</span></span>](https://docs.microsoft.com/azure/service-bus-messaging/service-bus-messaging-overview)
- [<span data-ttu-id="4a0fb-150">Azure Event Grid</span><span class="sxs-lookup"><span data-stu-id="4a0fb-150">Azure Event Grid</span></span>](https://docs.microsoft.com/azure/event-grid/overview)
- [<span data-ttu-id="4a0fb-151">Azure 이벤트 허브</span><span class="sxs-lookup"><span data-stu-id="4a0fb-151">Azure Event Hub</span></span>](https://azure.microsoft.com/services/event-hubs/)

<span data-ttu-id="4a0fb-152">이제 클라우드 네이티브 시스템에서 분산 된 데이터로 이동 하 고 그에 따른 이점과 과제가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a0fb-152">We next move to distributed data in cloud-native systems and the benefits and challenges that it presents.</span></span>

### <a name="references"></a><span data-ttu-id="4a0fb-153">참조 항목</span><span class="sxs-lookup"><span data-stu-id="4a0fb-153">References</span></span>

- [<span data-ttu-id="4a0fb-154">.NET 마이크로 서비스: 컨테이너 화 된 .NET 응용 프로그램에 대 한 아키텍처</span><span class="sxs-lookup"><span data-stu-id="4a0fb-154">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)

- [<span data-ttu-id="4a0fb-155">마이크로 서비스에 대 한 서비스 간 통신 디자인</span><span class="sxs-lookup"><span data-stu-id="4a0fb-155">Designing Interservice Communication for Microservices</span></span>](https://docs.microsoft.com/azure/architecture/microservices/design/interservice-communication)

- [<span data-ttu-id="4a0fb-156">실시간 기능을 추가 하는 완전히 관리 되는 서비스인 Azure SignalR Service</span><span class="sxs-lookup"><span data-stu-id="4a0fb-156">Azure SignalR Service, a fully managed service to add real-time functionality</span></span>](https://azure.microsoft.com/blog/azure-signalr-service-a-fully-managed-service-to-add-real-time-functionality/)

- [<span data-ttu-id="4a0fb-157">Azure API 게이트웨이 수신 컨트롤러</span><span class="sxs-lookup"><span data-stu-id="4a0fb-157">Azure API Gateway Ingress Controller</span></span>](https://azure.github.io/application-gateway-kubernetes-ingress/)

- [<span data-ttu-id="4a0fb-158">AKS (Azure Kubernetes Service)의 수신 정보</span><span class="sxs-lookup"><span data-stu-id="4a0fb-158">About Ingress in Azure Kubernetes Service (AKS)</span></span>](https://vincentlauzon.com/2018/10/10/about-ingress-in-azure-kubernetes-service-aks/)

- [<span data-ttu-id="4a0fb-159">실용적인 gRPC</span><span class="sxs-lookup"><span data-stu-id="4a0fb-159">Practical gRPC</span></span>](https://www.worldcat.org/title/practical-grpc/oclc/1042342319)

- [<span data-ttu-id="4a0fb-160">gRPC 설명서</span><span class="sxs-lookup"><span data-stu-id="4a0fb-160">gRPC Documentation</span></span>](https://grpc.io/docs/guides/)

- <span data-ttu-id="4a0fb-161">[WCF 개발자를 위한 grpc](https://bing.com) [Mark의 grpc 서적]</span><span class="sxs-lookup"><span data-stu-id="4a0fb-161">[gRPC for WCF Developers](https://bing.com) [Mark's gRPC book]</span></span>

- [<span data-ttu-id="4a0fb-162">GRPC 서비스와 HTTP Api 비교</span><span class="sxs-lookup"><span data-stu-id="4a0fb-162">Comparing gRPC Services with HTTP APIs</span></span>](https://docs.microsoft.com/aspnet/core/grpc/comparison?view=aspnetcore-3.0)

>[!div class="step-by-step"]
><span data-ttu-id="4a0fb-163">[이전](rest-grpc.md)
>[다음](distributed-data.md)</span><span class="sxs-lookup"><span data-stu-id="4a0fb-163">[Previous](rest-grpc.md)
[Next](distributed-data.md)</span></span>
