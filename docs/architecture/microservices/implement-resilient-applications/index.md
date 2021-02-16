---
title: 복원력 있는 애플리케이션 구현
description: 마이크로 서비스 아키텍처의 핵심 개념인 복원력에 대해 알아봅니다. 일시적 오류가 발생하면 해당 오류를 적절하게 처리하는 방법을 알아야 합니다.
ms.date: 01/30/2020
ms.openlocfilehash: 3ed4474eaa1225e80f05db86965e4ba53b5d2301
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100429327"
---
# <a name="implement-resilient-applications"></a><span data-ttu-id="2b81f-104">복원력 있는 애플리케이션 구현</span><span class="sxs-lookup"><span data-stu-id="2b81f-104">Implement resilient applications</span></span>

<span data-ttu-id="2b81f-105">*마이크로 서비스와 클라우드 기반 애플리케이션에서는 결국 발생하게 되는 부분 오류를 수용해야 합니다. 부분 오류에 탄력적으로 대처할 수 있도록 애플리케이션을 디자인해야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="2b81f-105">*Your microservice and cloud-based applications must embrace the partial failures that will certainly occur eventually. You must design your application to be resilient to those partial failures.*</span></span>

<span data-ttu-id="2b81f-106">복원력은 오류를 복구하고 계속 작업을 진행하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-106">Resiliency is the ability to recover from failures and continue to function.</span></span> <span data-ttu-id="2b81f-107">이는 오류를 방지하는 기능이 아닌 오류가 발생할 수 있다는 사실을 받아들이고 가동 중지 시간 또는 데이터 손실을 방지할 수 있도록 해당 오류에 응답하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-107">It isn't about avoiding failures but accepting the fact that failures will happen and responding to them in a way that avoids downtime or data loss.</span></span> <span data-ttu-id="2b81f-108">복원력의 목표는 오류 발생 후 애플리케이션을 완전히 작동 중인 상태로 되돌리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-108">The goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="2b81f-109">마이크로 서비스 기반 애플리케이션을 디자인하고 배포하기는 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-109">It's challenging enough to design and deploy a microservices-based application.</span></span> <span data-ttu-id="2b81f-110">그러나 일부 오류가 명확히 발생하는 환경에서 애플리케이션을 계속 실행하는 작업도 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-110">But you also need to keep your application running in an environment where some sort of failure is certain.</span></span> <span data-ttu-id="2b81f-111">따라서 애플리케이션에 복원력이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-111">Therefore, your application should be resilient.</span></span> <span data-ttu-id="2b81f-112">응용 프로그램은 클라우드에서의 네트워크 중단 또는 노드 또는 VM 충돌과 같은 부분 오류에 대처할 수 있도록 디자인되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-112">It should be designed to cope with partial failures, like network outages or nodes or VMs crashing in the cloud.</span></span> <span data-ttu-id="2b81f-113">클러스터 내에서 다른 노드로 이동한 마이크로 서비스(컨테이너)도 애플리케이션에서 일시적 단기 오류를 유발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-113">Even microservices (containers) being moved to a different node within a cluster can cause intermittent short failures within the application.</span></span>

<span data-ttu-id="2b81f-114">애플리케이션의 여러 개별 구성 요소도 상태 모니터링 기능과 통합해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-114">The many individual components of your application should also incorporate health monitoring features.</span></span> <span data-ttu-id="2b81f-115">이 장의 지침을 따라 가동 중지 시간 또는 복잡한 클라우드 기반 배포의 일반적인 문제가 발생하는 환경에서도 원활하게 작동하는 애플리케이션을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-115">By following the guidelines in this chapter, you can create an application that can work smoothly in spite of transient downtime or the normal hiccups that occur in complex and cloud-based deployments.</span></span>

>[!IMPORTANT]
> <span data-ttu-id="2b81f-116">eShopOnContainer는 릴리스 3.0.0까지 [Polly 라이브러리](https://thepollyproject.azurewebsites.net/)를 사용하여 [형식화된 클라이언트](./use-httpclientfactory-to-implement-resilient-http-requests.md)로 복원력을 구현해 왔습니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-116">eShopOnContainer had been using the [Polly library](https://thepollyproject.azurewebsites.net/) to implement resiliency using [Typed Clients](./use-httpclientfactory-to-implement-resilient-http-requests.md) up until the release 3.0.0.</span></span>
>
> <span data-ttu-id="2b81f-117">릴리스 3.0.0부터는 Kubernetes 클러스터 내에서 투명하고 구성 가능한 방식으로 재시도를 처리하기 때문에 코드에서 문제를 처리할 필요가 없는 [Linkerd 메시](https://linkerd.io/)를 사용하여 HTTP 호출 복원력이 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-117">Starting with release 3.0.0, the HTTP calls resiliency is implemented using a [Linkerd mesh](https://linkerd.io/), that handles retries in a transparent and configurable fashion, within a Kubernetes cluster, without having to handle those concerns in the code.</span></span>
>
> <span data-ttu-id="2b81f-118">Polly 라이브러리는 특히 서비스를 시작하는 동안 데이터베이스 연결에 복원력을 더하는 데 여전히 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-118">The Polly library is still used to add resilience to database connections, specially while starting up the services.</span></span>

>[!WARNING]
> <span data-ttu-id="2b81f-119">이 섹션의 모든 코드 샘플은 Linkerd를 사용하기 전에 유효했으며 현재 실제 코드를 반영하도록 업데이트되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-119">All code samples in this section were valid before using Linkerd and are not updated to reflect the current actual code.</span></span> <span data-ttu-id="2b81f-120">따라서 이 섹션의 맥락에서만 의미가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2b81f-120">So they make sense in the context of this section.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="2b81f-121">[이전](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
>[다음](handle-partial-failure.md)</span><span class="sxs-lookup"><span data-stu-id="2b81f-121">[Previous](../microservice-ddd-cqrs-patterns/microservice-application-layer-implementation-web-api.md)
[Next](handle-partial-failure.md)</span></span>
