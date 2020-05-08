---
title: 클라우드 네이티브 통신 패턴
description: 클라우드 네이티브 응용 프로그램의 주요 서비스 통신 문제에 대 한 자세한 정보
author: robvet
ms.date: 08/31/2019
ms.openlocfilehash: b3edc0817fb76ad99a1344b17d600eb747187f86
ms.sourcegitcommit: 957c49696eaf048c284ef8f9f8ffeb562357ad95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2020
ms.locfileid: "82895625"
---
# <a name="cloud-native-communication-patterns"></a><span data-ttu-id="e0c5e-103">클라우드 네이티브 통신 패턴</span><span class="sxs-lookup"><span data-stu-id="e0c5e-103">Cloud-native communication patterns</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="e0c5e-104">클라우드 네이티브 시스템을 구성 하는 경우 통신은 디자인을 결정 하는 것이 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-104">When constructing a cloud-native system, communication becomes a significant design decision.</span></span> <span data-ttu-id="e0c5e-105">프런트 엔드 클라이언트 응용 프로그램은 백 엔드 마이크로 서비스와 어떻게 통신 하나요?</span><span class="sxs-lookup"><span data-stu-id="e0c5e-105">How does a front-end client application communicate with a back-end microservice?</span></span> <span data-ttu-id="e0c5e-106">백 엔드 마이크로 서비스는 어떻게 서로 통신 하나요?</span><span class="sxs-lookup"><span data-stu-id="e0c5e-106">How do back-end microservices communicate with each other?</span></span> <span data-ttu-id="e0c5e-107">클라우드 네이티브 응용 프로그램에서 통신을 구현할 때 고려할 원리, 패턴 및 모범 사례는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="e0c5e-107">What are the principles, patterns, and best practices to consider when implementing communication in cloud-native applications?</span></span>

## <a name="communication-considerations"></a><span data-ttu-id="e0c5e-108">통신 고려 사항</span><span class="sxs-lookup"><span data-stu-id="e0c5e-108">Communication considerations</span></span>

<span data-ttu-id="e0c5e-109">모놀리식 응용 프로그램에서 통신은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-109">In a monolithic application, communication is straightforward.</span></span> <span data-ttu-id="e0c5e-110">코드 모듈은 서버에서 동일한 실행 공간 (프로세스)으로 함께 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-110">The code modules execute together in the same executable space (process) on a server.</span></span> <span data-ttu-id="e0c5e-111">이 접근 방식은 모든 항목을 공유 메모리에서 함께 실행 하는 경우 성능상의 이점을 누릴 수 있지만 유지 관리, 진화 및 확장 하기 어려운 코드를 긴밀 하 게 결합 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-111">This approach can have performance advantages as everything runs together in shared memory, but results in tightly coupled code that becomes difficult to maintain, evolve, and scale.</span></span>

<span data-ttu-id="e0c5e-112">클라우드 네이티브 시스템은 수많은 작고 독립적인 마이크로 서비스를 사용 하 여 마이크로 서비스 기반 아키텍처를 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-112">Cloud-native systems implement a microservice-based architecture with many small, independent microservices.</span></span> <span data-ttu-id="e0c5e-113">각 마이크로 서비스는 별도의 프로세스로 실행 되며 일반적으로 *클러스터*에 배포 되는 컨테이너 내에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-113">Each microservice executes in a separate process and typically runs inside a container that is deployed to a *cluster*.</span></span>

<span data-ttu-id="e0c5e-114">클러스터는 가상 머신 풀을 함께 그룹화 하 여 항상 사용 가능한 환경을 형성 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-114">A cluster groups a pool of virtual machines together to form a highly available environment.</span></span> <span data-ttu-id="e0c5e-115">컨테이너 화 된 마이크로 서비스 배포 및 관리를 담당 하는 오케스트레이션 도구로 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-115">They're managed with an orchestration tool, which is responsible for deploying and managing the containerized microservices.</span></span> <span data-ttu-id="e0c5e-116">그림 4-1에는 완전히 관리 되는 [Azure Kubernetes Services](https://docs.microsoft.com/azure/aks/intro-kubernetes)를 사용 하 여 azure 클라우드에 배포 된 [Kubernetes](https://kubernetes.io) 클러스터가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-116">Figure 4-1 shows a [Kubernetes](https://kubernetes.io) cluster deployed into the Azure cloud with the fully managed [Azure Kubernetes Services](https://docs.microsoft.com/azure/aks/intro-kubernetes).</span></span>

![Azure의 Kubernetes 클러스터](./media/kubernetes-cluster-in-azure.png)

<span data-ttu-id="e0c5e-118">**그림 4-1**.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-118">**Figure 4-1**.</span></span> <span data-ttu-id="e0c5e-119">Azure의 Kubernetes 클러스터</span><span class="sxs-lookup"><span data-stu-id="e0c5e-119">A Kubernetes cluster in Azure</span></span>

<span data-ttu-id="e0c5e-120">클러스터 전체에서 마이크로 서비스는 Api 및 메시징 기술을 통해 서로 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-120">Across the cluster, microservices communicate with each other through APIs and messaging technologies.</span></span>

<span data-ttu-id="e0c5e-121">다양 한 이점을 제공 하는 반면 마이크로 서비스는 식사를 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-121">While they provide many benefits, microservices are no free lunch.</span></span> <span data-ttu-id="e0c5e-122">이제 구성 요소 간의 로컬 in-process 메서드 호출이 네트워크 호출로 바뀝니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-122">Local in-process method calls between components are now replaced with network calls.</span></span> <span data-ttu-id="e0c5e-123">각 마이크로 서비스는 네트워크 프로토콜을 통해 통신 해야 하므로 시스템에 복잡성이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-123">Each microservice must communicate over a network protocol, which adds complexity to your system:</span></span>

- <span data-ttu-id="e0c5e-124">네트워크 정체, 대기 시간 및 일시적인 오류는 일정 한 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-124">Network congestion, latency, and transient faults are a constant concern.</span></span>

- <span data-ttu-id="e0c5e-125">복원 력 (즉, 실패 한 요청 재시도)은 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-125">Resiliency (that is, retrying failed requests) is essential.</span></span>

- <span data-ttu-id="e0c5e-126">일관 된 상태를 유지 하려면 일부 호출이로 [idempotent](https://www.restapitutorial.com/lessons/idempotency.html) 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-126">Some calls must be [idempotent](https://www.restapitutorial.com/lessons/idempotency.html) as to keep consistent state.</span></span>

- <span data-ttu-id="e0c5e-127">각 마이크로 서비스는 호출을 인증 하 고 권한을 부여 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-127">Each microservice must authenticate and authorize calls.</span></span>

- <span data-ttu-id="e0c5e-128">각 메시지는 serialize 되 고 deserialize 되어야 하며,이는 비용이 많이 들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-128">Each message must be serialized and then deserialized - which can be expensive.</span></span>

- <span data-ttu-id="e0c5e-129">메시지 암호화/해독은 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-129">Message encryption/decryption becomes important.</span></span>

<span data-ttu-id="e0c5e-130">Microsoft에서 무료로 제공 되는 [.Net 마이크로 서비스: 컨테이너 화 된 .Net 응용 프로그램에 대 한 아키텍처](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)는 마이크로 서비스 응용 프로그램에 대 한 통신 패턴의 심층 적용을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-130">The book [.NET Microservices: Architecture for Containerized .NET Applications](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook), available for free from Microsoft, provides an in-depth coverage of communication patterns for microservice applications.</span></span> <span data-ttu-id="e0c5e-131">이 장에서는 Azure 클라우드에서 제공 되는 구현 옵션과 함께 이러한 패턴에 대 한 개략적인 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-131">In this chapter, we provide a high-level overview of these patterns along with implementation options available in the Azure cloud.</span></span>

<span data-ttu-id="e0c5e-132">이 장에서는 먼저 프런트 엔드 응용 프로그램과 백 엔드 마이크로 서비스 간의 통신을 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-132">In this chapter, we'll first address communication between front-end applications and back-end microservices.</span></span> <span data-ttu-id="e0c5e-133">그런 다음 백 엔드 마이크로 서비스가 서로 통신 하는 것을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-133">We'll then look at back-end microservices communicate with each other.</span></span> <span data-ttu-id="e0c5e-134">Up 및 gRPC 통신 기술을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-134">We'll explore the up and gRPC communication technology.</span></span> <span data-ttu-id="e0c5e-135">마지막으로, 서비스 메시 기술을 사용 하 여 새로운 혁신적인 통신 패턴을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-135">Finally, we'll look new innovative communication patterns using service mesh technology.</span></span> <span data-ttu-id="e0c5e-136">또한 Azure 클라우드에서 클라우드 네이티브 통신을 지원 하기 위해 다양 한 종류의 *지원 서비스* 를 제공 하는 방법도 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e0c5e-136">We'll also see how the Azure cloud provides different kinds of *backing services* to support cloud-native communication.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="e0c5e-137">[이전](other-deployment-options.md)
>[다음](front-end-communication.md)</span><span class="sxs-lookup"><span data-stu-id="e0c5e-137">[Previous](other-deployment-options.md)
[Next](front-end-communication.md)</span></span>
