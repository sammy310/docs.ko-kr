---
title: 마이크로 서비스 아키텍처
description: 컨테이너화된 .NET 애플리케이션용 .NET 마이크로 서비스 아키텍처 | 마이크로 서비스 아키텍처의 30.000 피트 보기.
ms.date: 09/20/2018
ms.openlocfilehash: d1c58d218be9e5f8c0ae8ae732f9bdd06674a2c2
ms.sourcegitcommit: 8a0fe8a2227af612f8b8941bdb8b19d6268748e7
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/03/2019
ms.locfileid: "71834393"
---
# <a name="microservices-architecture"></a><span data-ttu-id="c95f6-103">마이크로 서비스 아키텍처</span><span class="sxs-lookup"><span data-stu-id="c95f6-103">Microservices architecture</span></span>

<span data-ttu-id="c95f6-104">이름에서 알 수 있듯이 마이크로 서비스 아키텍처는 작은 서비스의 집합인 서버 애플리케이션을 빌드하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-104">As the name implies, a microservices architecture is an approach to building a server application as a set of small services.</span></span> <span data-ttu-id="c95f6-105">즉, 이 방식이 프런트 엔드에도 사용되고 있지만 마이크로 서비스 아키텍처는 주로 백 엔드를 지향합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-105">That means a microservices architecture is mainly oriented to the back-end, although the approach is also being used for the front end.</span></span> <span data-ttu-id="c95f6-106">각 서비스는 자체 프로세스에서 실행되며 HTTP/HTTPS, WebSockets 또는 [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol)와 같은 프로토콜을 사용하여 다른 프로세스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-106">Each service runs in its own process and communicates with other processes using protocols such as HTTP/HTTPS, WebSockets, or [AMQP](https://en.wikipedia.org/wiki/Advanced_Message_Queuing_Protocol).</span></span> <span data-ttu-id="c95f6-107">각 마이크로 서비스는 특정 컨텍스트 경계 내에서 특정 엔드투엔드 도메인이나 비즈니스 기능을 구현하고 자율적으로 개발되고 독립적으로 배포될 수 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-107">Each microservice implements a specific end-to-end domain or business capability within a certain context boundary, and each must be developed autonomously and be deployable independently.</span></span> <span data-ttu-id="c95f6-108">마지막으로 각 마이크로 서비스는 관련 도메인 데이터 모델과 도메인 논리(주권 및 분산 데이터 관리)를 소유해야 하며 다양한 데이터 스토리지 기술(SQL, NoSQL) 및 프로그래밍 언어를 기반으로 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-108">Finally, each microservice should own its related domain data model and domain logic (sovereignty and decentralized data management) and could be based on different data storage technologies (SQL, NoSQL) and different programming languages.</span></span>

<span data-ttu-id="c95f6-109">마이크로 서비스의 크기는 얼마여야 하나요?</span><span class="sxs-lookup"><span data-stu-id="c95f6-109">What size should a microservice be?</span></span> <span data-ttu-id="c95f6-110">마이크로 서비스를 개발하는 경우 크기는 중요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-110">When developing a microservice, size shouldn't be the important point.</span></span> <span data-ttu-id="c95f6-111">대신 중요한 점은 각 서비스에 대해 개발, 배포 및 크기 조정의 자율성을 갖도록 느슨하게 결합된 서비스를 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-111">Instead, the important point should be to create loosely coupled services so you have autonomy of development, deployment, and scale, for each service.</span></span> <span data-ttu-id="c95f6-112">물론 마이크로 서비스를 식별하고 디자인하는 경우 다른 마이크로 서비스에서 과도한 직접 종속성이 없다면 가능한 작게 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-112">Of course, when identifying and designing microservices, you should try to make them as small as possible as long as you don't have too many direct dependencies with other microservices.</span></span> <span data-ttu-id="c95f6-113">마이크로 서비스의 크기보다 중요한 점은 내부 응집력 및 다른 서비스로부터의 독립성입니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-113">More important than the size of the microservice is the internal cohesion it must have and its independence from other services.</span></span>

<span data-ttu-id="c95f6-114">마이크로 서비스 아키텍처를 사용하는 이유는 무엇인가요?</span><span class="sxs-lookup"><span data-stu-id="c95f6-114">Why a microservices architecture?</span></span> <span data-ttu-id="c95f6-115">즉, 장기 유연성을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-115">In short, it provides long-term agility.</span></span> <span data-ttu-id="c95f6-116">마이크로 서비스를 사용하면 세부적이고 자율적인 수명 주기를 포함하는 많은 독립적으로 배포 가능한 서비스에 기반한 애플리케이션을 만들 수 있도록 하여 복잡한 대규모의 확장성이 뛰어난 시스템에서 유지 관리 기능을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-116">Microservices enable better maintainability in complex, large, and highly-scalable systems by letting you create applications based on many independently deployable services that each have granular and autonomous lifecycles.</span></span>

<span data-ttu-id="c95f6-117">추가 이점으로 마이크로 서비스를 독립적으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-117">As an additional benefit, microservices can scale out independently.</span></span> <span data-ttu-id="c95f6-118">단위로 확장해야 하는 단일 모놀리식 애플리케이션 대신 특정 마이크로 서비스를 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-118">Instead of having a single monolithic application that you must scale out as a unit, you can instead scale out specific microservices.</span></span> <span data-ttu-id="c95f6-119">이런 방식으로 확장해야 하는 애플리케이션의 다른 영역을 확장하지 않고 추가 처리 기능이 필요한 기능 영역 또는 요청을 지원하는 네트워크 대역폭을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-119">That way, you can scale just the functional area that needs more processing power or network bandwidth to support demand, rather than scaling out other areas of the application that don't need to be scaled.</span></span> <span data-ttu-id="c95f6-120">즉, 하드웨어를 적게 사용하기 때문에 비용이 절감됩니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-120">That means cost savings because you need less hardware.</span></span>

![두 배포 방법 간의 차이점을 보여 주는 다이어그램입니다.](./media/microservices-architecture/monolith-deployment-vs-microservice-approach.png)

<span data-ttu-id="c95f6-122">**그림 4-6**</span><span class="sxs-lookup"><span data-stu-id="c95f6-122">**Figure 4-6**.</span></span> <span data-ttu-id="c95f6-123">모놀리식 배포 대 마이크로 서비스 접근 방식</span><span class="sxs-lookup"><span data-stu-id="c95f6-123">Monolithic deployment versus the microservices approach</span></span>

<span data-ttu-id="c95f6-124">그림 4-6에 나와 있는 것처럼 일반적인 모놀리식 접근 방식에서는 여러 서버/VM에서 전체 앱을 복제하여 애플리케이션을 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-124">As Figure 4-6 shows, in the traditional monolithic approach, the application scales by cloning the whole app in several servers/VM.</span></span> <span data-ttu-id="c95f6-125">마이크로 서비스 방식에서는 기능이 더 작은 서비스로 분리되므로 각 서비스를 독립적으로 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-125">In the microservices approach, functionality is segregated in smaller services, so each service can scale independently.</span></span> <span data-ttu-id="c95f6-126">마이크로 서비스 접근 방식을 사용하면 복잡한 대규모의 확장형 애플리케이션의 특정한 일부 영역을 변경할 수 있기 때문에 각 마이크로 서비스를 신속하게 변경하고 반복할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-126">The microservices approach allows agile changes and rapid iteration of each microservice, because you can change specific, small areas of complex, large, and scalable applications.</span></span>

<span data-ttu-id="c95f6-127">세분화된 마이크로 서비스 기반 애플리케이션을 구축하는 작업은 연속 통합 및 지속적인 업데이트 사례를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-127">Architecting fine-grained microservices-based applications enables continuous integration and continuous delivery practices.</span></span> <span data-ttu-id="c95f6-128">또한 애플리케이션이 새 기능을 사용하도록 가속화합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-128">It also accelerates delivery of new functions into the application.</span></span> <span data-ttu-id="c95f6-129">애플리케이션의 세분화된 컴퍼지션을 사용하면 격리된 마이크로 서비스를 실행하고 테스트하며, 해당 서비스 간에 지우기 계약을 유지하면서 자율적으로 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-129">Fine-grained composition of applications also allows you to run and test microservices in isolation, and to evolve them autonomously while maintaining clear contracts between them.</span></span> <span data-ttu-id="c95f6-130">인터페이스 또는 계약을 변경하지 않으면 다른 마이크로 서비스를 중단하지 않고 마이크로 서비스의 내부 구현을 변경하거나 새 기능을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-130">As long as you don't change the interfaces or contracts, you can change the internal implementation of any microservice or add new functionality without breaking other microservices.</span></span>

<span data-ttu-id="c95f6-131">마이크로 서비스 기반 시스템을 사용하여 프로덕션에 성공할 수 있는 중요한 측면은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-131">The following are important aspects to enable success in going into production with a microservices-based system:</span></span>

- <span data-ttu-id="c95f6-132">서비스와 인프라의 모니터링 및 상태 검사</span><span class="sxs-lookup"><span data-stu-id="c95f6-132">Monitoring and health checks of the services and infrastructure.</span></span>

- <span data-ttu-id="c95f6-133">서비스에 대한 확장성 있는 인프라(즉, 클라우드 및 오케스트레이터)</span><span class="sxs-lookup"><span data-stu-id="c95f6-133">Scalable infrastructure for the services (that is, cloud and orchestrators).</span></span>

- <span data-ttu-id="c95f6-134">여러 수준의 보안 설계 및 구현: 인증, 권한 부여, 암호 관리, 보안 통신 등</span><span class="sxs-lookup"><span data-stu-id="c95f6-134">Security design and implementation at multiple levels: authentication, authorization, secrets management, secure communication, etc.</span></span>

- <span data-ttu-id="c95f6-135">일반적으로 다양한 마이크로 서비스에 중점을 두고 다양한 팀과 함께 신속한 애플리케이션 배달</span><span class="sxs-lookup"><span data-stu-id="c95f6-135">Rapid application delivery, usually with different teams focusing on different microservices.</span></span>

- <span data-ttu-id="c95f6-136">DevOps 및 CI/CD 사례 및 인프라</span><span class="sxs-lookup"><span data-stu-id="c95f6-136">DevOps and CI/CD practices and infrastructure.</span></span>

<span data-ttu-id="c95f6-137">이 중에서 처음 3개만을 이 가이드에서 다루거나 소개합니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-137">Of these, only the first three are covered or introduced in this guide.</span></span> <span data-ttu-id="c95f6-138">애플리케이션 수명 주기와 관련된 마지막 두 가지는 추가 [Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기](https://aka.ms/dockerlifecycleebook) eBook에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="c95f6-138">The last two points, which are related to application lifecycle, are covered in the additional [Containerized Docker Application Lifecycle with Microsoft Platform and Tools](https://aka.ms/dockerlifecycleebook) e-book.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="c95f6-139">추가 자료</span><span class="sxs-lookup"><span data-stu-id="c95f6-139">Additional resources</span></span>

- <span data-ttu-id="c95f6-140">**Mark Russinovich 마이크로 서비스: 클라우드 기반의 애플리케이션 혁명** </span><span class="sxs-lookup"><span data-stu-id="c95f6-140">**Mark Russinovich. Microservices: An application revolution powered by the cloud** </span></span>\
  <https://azure.microsoft.com/blog/microservices-an-application-revolution-powered-by-the-cloud/>

- <span data-ttu-id="c95f6-141">**Martin Fowler. 마이크로 서비스** </span><span class="sxs-lookup"><span data-stu-id="c95f6-141">**Martin Fowler. Microservices** </span></span>\
  <https://www.martinfowler.com/articles/microservices.html>

- <span data-ttu-id="c95f6-142">**Martin Fowler. 마이크로 서비스 필수 구성 요소** </span><span class="sxs-lookup"><span data-stu-id="c95f6-142">**Martin Fowler. Microservice Prerequisites** </span></span>\
  <https://martinfowler.com/bliki/MicroservicePrerequisites.html>

- <span data-ttu-id="c95f6-143">**Jimmy Nilsson. 청크 클라우드 컴퓨팅** </span><span class="sxs-lookup"><span data-stu-id="c95f6-143">**Jimmy Nilsson. Chunk Cloud Computing** </span></span>\
  <https://www.infoq.com/articles/CCC-Jimmy-Nilsson>

- <span data-ttu-id="c95f6-144">**Cesar de la Torre. Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 애플리케이션 수명 주기**(다운로드 가능한 eBook)</span><span class="sxs-lookup"><span data-stu-id="c95f6-144">**Cesar de la Torre. Containerized Docker Application Lifecycle with Microsoft Platform and Tools** (downloadable e-book) </span></span>\
  <https://aka.ms/dockerlifecycleebook>

>[!div class="step-by-step"]
><span data-ttu-id="c95f6-145">[이전](service-oriented-architecture.md)
>[다음](data-sovereignty-per-microservice.md)</span><span class="sxs-lookup"><span data-stu-id="c95f6-145">[Previous](service-oriented-architecture.md)
[Next](data-sovereignty-per-microservice.md)</span></span>
