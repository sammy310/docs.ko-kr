---
title: 아키텍처 접근 방식-서버 리스 앱
description: N 계층 아키텍처에서 서버를 사용 하지 않는 방식으로 클라우드 기반 엔터프라이즈 응용 프로그램을 빌드하는 아키텍처를 소개 합니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: 74de96bef48f16ced4adf82855a740aa0afcdf1d
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72522903"
---
# <a name="architecture-approaches"></a><span data-ttu-id="cd786-103">아키텍처 접근 방식</span><span class="sxs-lookup"><span data-stu-id="cd786-103">Architecture approaches</span></span>

<span data-ttu-id="cd786-104">엔터프라이즈 앱을 설계 하는 기존 방법을 이해 하면 서버를 사용 하지 않는 역할을 명확 하 게 파악할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="cd786-105">수십 년 동안 소프트웨어를 개발 하는 여러 가지 방법과 패턴이 있으며 모두 사용자의 장단점을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="cd786-106">대부분의 경우 최종 솔루션은 단일 방법에 대 한 결정을 포함 하지 않을 수 있지만 여러 접근 방식을 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="cd786-107">마이그레이션 시나리오에는 하이브리드 방식을 통해 한 아키텍처 방법에서 다른 아키텍처 방법으로 이동 하는 경우가 종종 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="cd786-108">이 장에서는 엔터프라이즈 응용 프로그램에 대 한 논리적 및 물리적 아키텍처 패턴에 대 한 개요를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="cd786-109">아키텍처 패턴</span><span class="sxs-lookup"><span data-stu-id="cd786-109">Architecture patterns</span></span>

<span data-ttu-id="cd786-110">최신 비즈니스 응용 프로그램은 다양 한 아키텍처 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="cd786-111">이 섹션은 일반적인 패턴의 설문 조사를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="cd786-112">여기에 나열 된 패턴은 모든 모범 사례는 아니지만 다양 한 접근 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="cd786-113">자세한 내용은 [Azure 응용 프로그램 아키텍처 가이드](https://docs.microsoft.com/azure/architecture/guide/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="cd786-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="cd786-114">거</span><span class="sxs-lookup"><span data-stu-id="cd786-114">Monoliths</span></span>

<span data-ttu-id="cd786-115">많은 비즈니스 응용 프로그램은 모놀리식 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="cd786-116">레거시 응용 프로그램은 종종 거로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="cd786-117">모놀리식 패턴에서 모든 응용 프로그램 문제는 단일 배포에 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="cd786-118">사용자 인터페이스에서 데이터베이스 호출에 이르기까지 모든 항목은 동일한 코드 베이스에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![Monolith 아키텍처](./media/monolith-architecture.png)

<span data-ttu-id="cd786-120">모놀리식 접근 방식에는 몇 가지 장점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="cd786-121">대개 단일 코드 베이스를 끌어와 작업을 시작 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="cd786-122">램프 시간이 단축 될 수 있으며 테스트 환경을 만드는 것은 새 복사본을 제공 하는 것 만큼 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="cd786-123">모놀리식는 여러 구성 요소와 응용 프로그램을 포함 하도록 설계 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="cd786-124">아쉽게도 모놀리식 패턴은 규모에 맞게 세분화 되는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="cd786-125">모놀리식 방식의 주요 단점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-125">Major disadvantages of the monolith approach include:</span></span>

- <span data-ttu-id="cd786-126">동일한 코드 베이스에서 병렬로 작업 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-126">Difficult to work in parallel in the same code base.</span></span>
- <span data-ttu-id="cd786-127">사소한 변경 내용에 관계 없이 전체 응용 프로그램의 새 버전을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
- <span data-ttu-id="cd786-128">리팩터링은 전체 응용 프로그램에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-128">Refactoring potentially impacts the entire application.</span></span>
- <span data-ttu-id="cd786-129">종종 규모를 조정 하는 유일한 해결책은 리소스를 많이 사용 하는 리소스를 많이 사용 하는 여러 복사본을 만드는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
- <span data-ttu-id="cd786-130">시스템이 확장 되거나 다른 시스템을 확보 하면 통합이 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
- <span data-ttu-id="cd786-131">전체 monolith를 구성 해야 하기 때문에 테스트 하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
- <span data-ttu-id="cd786-132">코드를 다시 사용 하는 것은 어려운 일 이며 다른 앱은 자신의 코드 복사본을 포함 하는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="cd786-133">많은 기업은 모놀리식 응용 프로그램을 마이그레이션하고 동시에 더 사용 가능한 패턴으로 리팩터링 하는 기회를 클라우드로 살펴보세요.</span><span class="sxs-lookup"><span data-stu-id="cd786-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="cd786-134">개별 응용 프로그램 및 구성 요소를 분리 하 여 개별적으로 유지 관리, 배포 및 확장할 수 있도록 하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="cd786-135">N 계층 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="cd786-135">N-Layer applications</span></span>

<span data-ttu-id="cd786-136">N 계층 응용 프로그램은 응용 프로그램 논리를 특정 계층으로 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="cd786-137">가장 일반적인 계층은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-137">The most common layers include:</span></span>

- <span data-ttu-id="cd786-138">사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="cd786-138">User interface</span></span>
- <span data-ttu-id="cd786-139">비즈니스 논리</span><span class="sxs-lookup"><span data-stu-id="cd786-139">Business logic</span></span>
- <span data-ttu-id="cd786-140">데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="cd786-140">Data access</span></span>

<span data-ttu-id="cd786-141">다른 레이어에는 미들웨어, 일괄 처리 및 API가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="cd786-142">계층은 논리적 이므로 주의 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="cd786-143">격리 된 상태에서 개발 되기는 하지만 모두 동일한 대상 플랫폼에 배포 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N 계층 아키텍처](./media/n-layer-architecture.png)

<span data-ttu-id="cd786-145">N 계층 접근 방법에는 다음과 같은 몇 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-145">There are several advantages to the N-Layer approach, including:</span></span>

- <span data-ttu-id="cd786-146">리팩터링이 계층으로 격리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-146">Refactoring is isolated to a layer.</span></span>
- <span data-ttu-id="cd786-147">팀에서 개별 계층을 독립적으로 빌드, 테스트, 배포 및 유지 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
- <span data-ttu-id="cd786-148">계층은 스왑할 수 있습니다. 예를 들어 데이터 계층은 UI 계층을 변경할 필요 없이 여러 데이터베이스에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="cd786-149">서버 리스 서버를 사용 하 여 하나 이상의 계층을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="cd786-150">마이크로 서비스</span><span class="sxs-lookup"><span data-stu-id="cd786-150">Microservices</span></span>

<span data-ttu-id="cd786-151">**[마이크로 서비스](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** 아키텍처에는 다음을 포함 하는 일반적인 특성이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

- <span data-ttu-id="cd786-152">응용 프로그램은 여러 개의 작은 서비스로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-152">Applications are composed of several small services.</span></span>
- <span data-ttu-id="cd786-153">각 서비스는 자체 프로세스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-153">Each service runs in its own process.</span></span>
- <span data-ttu-id="cd786-154">서비스는 비즈니스 도메인에 맞춰 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-154">Services are aligned around business domains.</span></span>
- <span data-ttu-id="cd786-155">서비스는 일반적으로 HTTP를 전송으로 사용 하는 경량 Api를 통해 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
- <span data-ttu-id="cd786-156">서비스는 독립적으로 배포 및 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-156">Services can be deployed and upgraded independently.</span></span>
- <span data-ttu-id="cd786-157">서비스는 단일 데이터 저장소에 종속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-157">Services aren't dependent on a single data store.</span></span>
- <span data-ttu-id="cd786-158">시스템은 오류를 염두에 두고 설계 되었으며, 특정 서비스가 실패 해도 앱이 계속 실행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="cd786-159">마이크로 서비스는 다른 아키텍처 방법과 함께 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="cd786-160">예를 들어 N 계층 아키텍처는 중간 계층에 마이크로 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="cd786-161">IIS 호스트의 가상 디렉터리에서 컨테이너에 이르는 다양 한 방식으로 마이크로 서비스를 구현할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="cd786-162">마이크로 서비스의 특징은 서버 리스 구현에 특히 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![마이크로 서비스 아키텍처](./media/microservices-architecture.png)

<span data-ttu-id="cd786-164">마이크로 서비스 아키텍처의 장점에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-164">The pros of microservices architectures include:</span></span>

- <span data-ttu-id="cd786-165">리팩터링은 단일 서비스로 격리 되는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-165">Refactoring is often isolated to a single service.</span></span>
- <span data-ttu-id="cd786-166">서비스는 서로 독립적으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-166">Services can be upgraded independently of each other.</span></span>
- <span data-ttu-id="cd786-167">복원 력과 탄력성은 개별 서비스의 요구 사항에 맞게 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
- <span data-ttu-id="cd786-168">개발은 서로 다른 팀 및 플랫폼에서 병렬로 수행 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-168">Development can happen in parallel across disparate teams and platforms.</span></span>
- <span data-ttu-id="cd786-169">격리 된 서비스에 대 한 포괄적인 테스트를 작성 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="cd786-170">마이크로 서비스에는 다음을 포함 하 여 고유한 과제가 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-170">Microservices come with their own challenges, including:</span></span>

- <span data-ttu-id="cd786-171">사용 가능한 서비스 및 해당 서비스를 호출 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-171">Determining what services are available and how to call them.</span></span>
- <span data-ttu-id="cd786-172">서비스의 수명 주기 관리</span><span class="sxs-lookup"><span data-stu-id="cd786-172">Managing the lifecycle of services.</span></span>
- <span data-ttu-id="cd786-173">서비스를 전체 응용 프로그램에 맞추는 방법 이해</span><span class="sxs-lookup"><span data-stu-id="cd786-173">Understanding how services fit together in the overall application.</span></span>
- <span data-ttu-id="cd786-174">서로 다른 서비스에서 수행 된 호출의 전체 시스템 테스트</span><span class="sxs-lookup"><span data-stu-id="cd786-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="cd786-175">궁극적으로 이러한 모든 문제를 해결 하는 솔루션은 나중에 설명 하는 서버를 사용 하지 않는의 이점을 활용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="cd786-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="cd786-176">[이전](index.md)
>[다음](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="cd786-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
