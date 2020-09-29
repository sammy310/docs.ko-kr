---
title: 아키텍처 접근 방식 - 서버리스 앱
description: N 계층 아키텍처에서 서버리스까지 클라우드 기반 엔터프라이즈 애플리케이션을 빌드하는 아키텍처를 소개합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 0ab84d1f3425c1fda787756b73fd8315fe6d4231
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91171977"
---
# <a name="architecture-approaches"></a><span data-ttu-id="465c4-103">아키텍처 접근 방식</span><span class="sxs-lookup"><span data-stu-id="465c4-103">Architecture approaches</span></span>

<span data-ttu-id="465c4-104">엔터프라이즈 앱 설계에 대한 기존 접근 방식을 이해하면 서버리스의 역할을 명확하게 파악하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="465c4-105">수십 년 동안 소프트웨어 개발과 관련하여 다양한 접근 방식 및 패턴이 진화해 왔으며 각각 장단점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="465c4-106">대부분 경우 최종 솔루션에 단일 접근 방식이 아니라 여러 접근 방식이 통합될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="465c4-107">마이그레이션 시나리오에서는 하이브리드 방식을 통해 한 아키텍처 접근 방식에서 다른 아키텍처 접근 방식으로 전환하는 경우가 자주 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="465c4-108">이 장에서는 엔터프라이즈 애플리케이션에 대한 논리적 및 물리적 아키텍처 패턴의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="465c4-109">아키텍처 패턴</span><span class="sxs-lookup"><span data-stu-id="465c4-109">Architecture patterns</span></span>

<span data-ttu-id="465c4-110">최신 비즈니스 애플리케이션은 다양한 아키텍처 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="465c4-111">이 섹션에서는 일반적인 패턴을 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="465c4-112">여기에 나열된 패턴이 모든 모범 사례를 망라한 것은 아니지만 다양한 접근 방식을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="465c4-113">자세한 내용은 [Azure 애플리케이션 아키텍처 가이드](/azure/architecture/guide/)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="465c4-113">For more information, see [Azure application architecture guide](/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="465c4-114">모놀리식</span><span class="sxs-lookup"><span data-stu-id="465c4-114">Monoliths</span></span>

<span data-ttu-id="465c4-115">많은 비즈니스 애플리케이션은 모놀리식 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="465c4-116">레거시 애플리케이션은 종종 모놀리식으로 구현됩니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="465c4-117">모놀리식 패턴에서는 모든 애플리케이션 관심 사항이 단일 배포에 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="465c4-118">사용자 인터페이스에서 데이터베이스 호출에 이르기까지 모든 항목이 동일한 코드 베이스에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![모놀리식 아키텍처](./media/monolith-architecture.png)

<span data-ttu-id="465c4-120">모놀리식 접근 방식에는 몇 가지 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="465c4-121">대개 단일 코드 베이스를 끌어와 작업을 시작하는 것이 간편합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="465c4-122">램프 작동 시간이 단축될 수 있으며 테스트 환경을 만드는 것은 새 복사본을 제공하는 것처럼 간단합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="465c4-123">모놀리식은 여러 구성 요소와 애플리케이션을 포함하도록 디자인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="465c4-124">아쉽게도 모놀리식 패턴은 확장 시 세분화되는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="465c4-125">모놀리식 접근 방식의 주요 단점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="465c4-126">동일한 코드 베이스에서 병렬로 작업하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="465c4-127">아무리 사소한 변경이라도 전체 애플리케이션의 새 버전을 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="465c4-128">리팩터링이 전체 애플리케이션에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="465c4-129">종종 규모를 조정하는 유일한 솔루션이 모놀리식의 복사본을 여러 개 만드는 것인데, 이는 리소스를 많이 사용하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="465c4-130">시스템이 확장되거나 다른 시스템을 획득하면 통합이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="465c4-131">전체 모놀리식을 구성해야 하기 때문에 테스트가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="465c4-132">코드 재사용은 어려운 문제이며 다른 앱이 각각 코드 복사본을 갖게 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="465c4-133">많은 기업이 모놀리식 애플리케이션을 마이그레이션하는 동시에 사용성이 향상된 패턴으로 리팩터링하는 기회로 클라우드를 고려합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="465c4-134">개별적으로 유지 관리, 배포 및 확장할 수 있도록 개별 애플리케이션 및 구성 요소를 분리하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="465c4-135">N 계층 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="465c4-135">N-Layer applications</span></span>

<span data-ttu-id="465c4-136">N 계층 애플리케이션은 애플리케이션 논리를 특정 레이어로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="465c4-137">가장 일반적인 레이어는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-137">The most common layers include:</span></span>

- <span data-ttu-id="465c4-138">사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="465c4-138">User interface</span></span>
- <span data-ttu-id="465c4-139">비즈니스 논리</span><span class="sxs-lookup"><span data-stu-id="465c4-139">Business logic</span></span>
- <span data-ttu-id="465c4-140">데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="465c4-140">Data access</span></span>

<span data-ttu-id="465c4-141">다른 레이어에는 미들웨어, 일괄 처리 및 API가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="465c4-142">레이어가 논리적이라는 점을 유의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="465c4-143">격리된 상태에서 개발되기는 하지만 모두 동일한 대상 플랫폼에 배포될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N 계층 아키텍처](./media/n-layer-architecture.png)

<span data-ttu-id="465c4-145">N 계층 접근 방식에는 다음과 같은 몇 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="465c4-146">리팩터링이 레이어로 격리됩니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="465c4-147">팀에서 개별 레이어를 독립적으로 빌드, 테스트, 배포 및 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="465c4-148">레이어를 스왑할 수 있습니다. 예를 들어 데이터 레이어는 UI 레이어를 변경할 필요 없이 여러 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="465c4-149">서버리스를 사용하여 하나 이상의 레이어를 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="465c4-150">마이크로 서비스</span><span class="sxs-lookup"><span data-stu-id="465c4-150">Microservices</span></span>

<span data-ttu-id="465c4-151">**[마이크로 서비스](/azure/architecture/guide/architecture-styles/microservices)** 아키텍처에는 다음과 같은 공통 특성이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-151">**[Microservices](/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="465c4-152">애플리케이션이 여러 개의 소규모 서비스로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="465c4-153">각 서비스는 자체 프로세스에서 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="465c4-154">서비스는 비즈니스 도메인을 중심으로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="465c4-155">서비스는 일반적으로 HTTP 전송을 사용하는 경량 API를 통해 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="465c4-156">서비스는 독립적으로 배포 및 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="465c4-157">서비스는 단일 데이터 저장소에 종속되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="465c4-158">시스템은 실패를 염두에 두고 디자인되며, 특정 서비스가 실패해도 앱이 계속 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="465c4-159">마이크로 서비스는 다른 아키텍처 접근 방식과 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="465c4-160">예를 들어 N 계층 아키텍처는 중간 계층에 마이크로 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="465c4-161">IIS 호스트의 가상 디렉터리에서 컨테이너에 이르는 다양한 방식으로 마이크로 서비스를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="465c4-162">마이크로 서비스의 특징은 서버리스 구현에 특히 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![마이크로 서비스 아키텍처](./media/microservices-architecture.png)

<span data-ttu-id="465c4-164">마이크로 서비스 아키텍처의 장점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="465c4-165">리팩터링은 단일 서비스로 격리되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="465c4-166">서비스는 서로 독립적으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="465c4-167">복원력 및 탄력성은 개별 서비스의 요구 사항에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="465c4-168">개발은 여러 팀 및 플랫폼에서 병렬로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="465c4-169">격리된 서비스에 대한 포괄적 테스트를 작성하기 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="465c4-170">마이크로 서비스에는 다음과 같은 고유한 문제가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="465c4-171">사용 가능한 서비스 및 해당 서비스를 호출하는 방법 결정</span><span class="sxs-lookup"><span data-stu-id="465c4-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="465c4-172">서비스 수명 주기 관리</span><span class="sxs-lookup"><span data-stu-id="465c4-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="465c4-173">서비스가 전체 애플리케이션와 연동하는 방식 이해</span><span class="sxs-lookup"><span data-stu-id="465c4-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="465c4-174">개별 서비스 호출에 대한 전체 시스템 테스트</span><span class="sxs-lookup"><span data-stu-id="465c4-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="465c4-175">궁극적으로 나중에 설명할 서버리스의 이점을 활용하는 것을 포함하여 이러한 모든 문제를 해결하는 방법이 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="465c4-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="465c4-176">[이전](index.md)
>[다음](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="465c4-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
