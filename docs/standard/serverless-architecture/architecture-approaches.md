---
title: 서버 리스 앱 아키텍처 접근 방식
description: 서버 리스 N 계층 아키텍처에서 클라우드 기반 엔터프라이즈 응용 프로그램을 빌드하기 위한 아키텍처 소개에 가깝습니다.
author: JEREMYLIKNESS
ms.author: jeliknes
ms.date: 06/26/2018
ms.openlocfilehash: ee529abd1f6955d4f542464dd9a2380dd663571f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65638833"
---
# <a name="architecture-approaches"></a><span data-ttu-id="fc0b8-103">아키텍처 접근 방식</span><span class="sxs-lookup"><span data-stu-id="fc0b8-103">Architecture approaches</span></span>

<span data-ttu-id="fc0b8-104">역할을 서버 리스 분명히 엔터프라이즈 앱을 설계 하는 기존 방법 이해.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-104">Understanding existing approaches to architecting enterprise apps helps clarify the role played by serverless.</span></span> <span data-ttu-id="fc0b8-105">접근 방식 및 소프트웨어 개발의 수십 년 동안 발전 하는 패턴을 많이 있고 모든 고유한 장점과 단점입니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-105">There are many approaches and patterns that evolved over decades of software development, and all have their own pros and cons.</span></span> <span data-ttu-id="fc0b8-106">대부분의 경우 ultimate 솔루션 단일 방식을 결정 하는 것을 포함 하지 않을 수 있습니다 하지만 여러 가지 방법으로 통합 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-106">In many cases, the ultimate solution may not involve deciding on a single approach but may integrate several approaches.</span></span> <span data-ttu-id="fc0b8-107">마이그레이션 시나리오는 경우가 많습니다 하이브리드 접근 방식을 통해 다른 하나의 아키텍처 접근 방식에서 전환 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-107">Migration scenarios often involve shifting from one architecture approach to another through a hybrid approach.</span></span>

<span data-ttu-id="fc0b8-108">이 장에서 엔터프라이즈 응용 프로그램에 대 한 논리적 및 물리적 아키텍처 패턴을 모두의 개요를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-108">This chapter provides an overview of both logical and physical architecture patterns for enterprise applications.</span></span>

## <a name="architecture-patterns"></a><span data-ttu-id="fc0b8-109">아키텍처 패턴</span><span class="sxs-lookup"><span data-stu-id="fc0b8-109">Architecture patterns</span></span>

<span data-ttu-id="fc0b8-110">최신 비즈니스 응용 프로그램을 다양 한 아키텍처 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-110">Modern business applications follow a variety of architecture patterns.</span></span> <span data-ttu-id="fc0b8-111">이 섹션에서는 일반적인 패턴의 설문 조사를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-111">This section represents a survey of common patterns.</span></span> <span data-ttu-id="fc0b8-112">여기에 나열 된 패턴 반드시 모든 모범 사례를 아니지만 여러 가지 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-112">The patterns listed here aren't necessarily all best practices, but illustrate different approaches.</span></span>

<span data-ttu-id="fc0b8-113">자세한 내용은 [Azure 응용 프로그램 아키텍처 가이드](https://docs.microsoft.com/azure/architecture/guide/)합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-113">For more information, see [Azure application architecture guide](https://docs.microsoft.com/azure/architecture/guide/).</span></span>

## <a name="monoliths"></a><span data-ttu-id="fc0b8-114">모놀리식</span><span class="sxs-lookup"><span data-stu-id="fc0b8-114">Monoliths</span></span>

<span data-ttu-id="fc0b8-115">많은 비즈니스 응용 프로그램이 모놀리식 패턴을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-115">Many business applications follow a monolith pattern.</span></span> <span data-ttu-id="fc0b8-116">레거시 응용 프로그램은 종종 모놀리식으로 구현 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-116">Legacy applications are often implemented as monoliths.</span></span> <span data-ttu-id="fc0b8-117">모놀리식 패턴에서 모든 응용 프로그램 문제는 단일 배포에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-117">In the monolith pattern, all application concerns are contained in a single deployment.</span></span> <span data-ttu-id="fc0b8-118">데이터베이스를 호출 하는 사용자 인터페이스에서 모두 동일한 코드 베이스에 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-118">Everything from user interface to database calls is included in the same codebase.</span></span>

![모놀리식 아키텍처](./media/monolith-architecture.png)

<span data-ttu-id="fc0b8-120">모놀리식 방식의 장점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-120">There are several advantages to the monolith approach.</span></span> <span data-ttu-id="fc0b8-121">종종 단일 코드 베이스를 풀다운합니다 작업을 시작 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-121">It's often easy to pull down a single code base and start working.</span></span> <span data-ttu-id="fc0b8-122">시간이 더 작을 수도 있습니다 및 테스트 환경을 만드는 간단 하 게 새 복사본을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-122">Ramp up time may be less, and creating test environments is as simple as providing a new copy.</span></span> <span data-ttu-id="fc0b8-123">모놀리식 여러 구성 요소 및 응용 프로그램을 포함 하도록 디자인 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-123">The monolith may be designed to include multiple components and applications.</span></span>

<span data-ttu-id="fc0b8-124">아쉽게도 모놀리식 패턴 대규모로 세분화는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-124">Unfortunately, the monolith pattern tends to break down at scale.</span></span> <span data-ttu-id="fc0b8-125">모놀리식 방식의 주요 단점은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-125">Major disadvantages of the monolith approach include:</span></span>

* <span data-ttu-id="fc0b8-126">동일한 코드 베이스에서 병렬로 작업 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-126">Difficult to work in parallel in the same code base.</span></span>
* <span data-ttu-id="fc0b8-127">변경 되 면 얼마나 간단한 지에 관계 없이 전체 응용 프로그램의 새 버전을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-127">Any change, no matter how trivial, requires deploying a new version of the entire application.</span></span>
* <span data-ttu-id="fc0b8-128">리팩터링 잠재적으로 전체 응용 프로그램에 영향을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-128">Refactoring potentially impacts the entire application.</span></span>
* <span data-ttu-id="fc0b8-129">크기를 조정 하는 유일한 방법은 여러 만들려는 경우가 모놀리식 복사본 리소스를 많이 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-129">Often the only solution to scale is to create multiple, resource-intensive copies of the monolith.</span></span>
* <span data-ttu-id="fc0b8-130">시스템을 확장 하거나 다른 시스템을 획득 하면 통합 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-130">As systems expand or other systems are acquired, integration can be difficult.</span></span>
* <span data-ttu-id="fc0b8-131">전체 모놀리식 구성 하기 위해 테스트 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-131">It may be difficult to test due to the need to configure the entire monolith.</span></span>
* <span data-ttu-id="fc0b8-132">코드 재사용 하기는 쉽지 않으며 종종 다른 앱 종료 코드의 자체 복사본을 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-132">Code reuse is challenging and often other apps end up having their own copies of code.</span></span>

<span data-ttu-id="fc0b8-133">많은 기업 클라우드 모놀리식 응용 프로그램 마이그레이션 및 동시에 더 많은 사용 가능한 패턴을 리팩터링할 수 있는 기회로 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-133">Many businesses look to the cloud as an opportunity to migrate monolith applications and at the same time refactor them to more usable patterns.</span></span> <span data-ttu-id="fc0b8-134">것이 일반적 유지 관리, 배포 및 개별적으로 확장할 수 있도록 개별 응용 프로그램 및 구성 요소를 알아낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-134">It's common to break out the individual applications and components to allow them to be maintained, deployed, and scaled separately.</span></span>

## <a name="n-layer-applications"></a><span data-ttu-id="fc0b8-135">N 계층 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="fc0b8-135">N-Layer applications</span></span>

<span data-ttu-id="fc0b8-136">특정 계층으로 응용 프로그램 논리를 파티션 하는 N 계층 응용 프로그램입니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-136">N-layer application partition application logic into specific layers.</span></span> <span data-ttu-id="fc0b8-137">가장 일반적인 계층은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-137">The most common layers include:</span></span>

* <span data-ttu-id="fc0b8-138">사용자 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fc0b8-138">User interface</span></span>
* <span data-ttu-id="fc0b8-139">비즈니스 논리</span><span class="sxs-lookup"><span data-stu-id="fc0b8-139">Business logic</span></span>
* <span data-ttu-id="fc0b8-140">데이터 액세스</span><span class="sxs-lookup"><span data-stu-id="fc0b8-140">Data access</span></span>

<span data-ttu-id="fc0b8-141">미들웨어, 일괄 처리 및 API 레이어가 포함 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-141">Other layers may include middleware, batch processing, and API.</span></span> <span data-ttu-id="fc0b8-142">계층은 논리적 두는 것이 반드시 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-142">It's important to note the layers are logical.</span></span> <span data-ttu-id="fc0b8-143">격리에서 개발 하는, 있지만 이러한 모든를 배포할 수 있습니다 동일한 대상 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-143">Although they're developed in isolation, they may all be deployed to the same target platform.</span></span>

![N 계층 아키텍처](./media/n-layer-architecture.png)

<span data-ttu-id="fc0b8-145">여러 가지 이점이 있습니다 N 계층 접근 방식을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-145">There are several advantages to the N-Layer approach, including:</span></span>

* <span data-ttu-id="fc0b8-146">리팩터링 계층으로 격리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-146">Refactoring is isolated to a layer.</span></span>
* <span data-ttu-id="fc0b8-147">팀 수 독립적으로 빌드, 테스트, 배포 및 별도 계층 유지 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-147">Teams can independently build, test, deploy, and maintain separate layers.</span></span>
* <span data-ttu-id="fc0b8-148">레이어를 스왑할 수, 데이터 계층은 UI 계층을 변경 하지 않고도 여러 데이터베이스에 액세스할 수 있습니다 예를 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-148">Layers can be swapped out, for example the data layer may access multiple databases without requiring changes to the UI layer.</span></span>

<span data-ttu-id="fc0b8-149">하나 이상의 레이어를 구현 하려면 서버를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-149">Serverless may be used to implement one or more layers.</span></span>

## <a name="microservices"></a><span data-ttu-id="fc0b8-150">마이크로 서비스</span><span class="sxs-lookup"><span data-stu-id="fc0b8-150">Microservices</span></span>

<span data-ttu-id="fc0b8-151">**[마이크로 서비스](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)**  아키텍처를 포함 하는 공통 특성을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-151">**[Microservices](https://docs.microsoft.com/azure/architecture/guide/architecture-styles/microservices)** architectures contain common characteristics that include:</span></span>

* <span data-ttu-id="fc0b8-152">응용 프로그램은 여러 소규모 서비스로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-152">Applications are composed of several small services.</span></span>
* <span data-ttu-id="fc0b8-153">각 서비스가 자체 프로세스에서 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-153">Each service runs in its own process.</span></span>
* <span data-ttu-id="fc0b8-154">서비스는 비즈니스 도메인 관련 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-154">Services are aligned around business domains.</span></span>
* <span data-ttu-id="fc0b8-155">서비스는 일반적으로 전송으로 HTTP를 사용 하는 간단한 Api를 통해 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-155">Services communicate over lightweight APIs, typically using HTTP as the transport.</span></span>
* <span data-ttu-id="fc0b8-156">서비스를 배포 하 고 독립적으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-156">Services can be deployed and upgraded independently.</span></span>
* <span data-ttu-id="fc0b8-157">서비스는 단일 데이터 저장소에 종속 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-157">Services aren't dependent on a single data store.</span></span>
* <span data-ttu-id="fc0b8-158">따라서에서 오류는 시스템은 설계 되었습니다 및 특정 서비스가 실패 하는 경우에 앱을 계속 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-158">The system is designed with failure in mind, and the app may still run even when certain services fail.</span></span>

<span data-ttu-id="fc0b8-159">마이크로 서비스는 다른 아키텍처 접근 방식에 배타적일 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-159">Microservices don't have to be mutually exclusive to other architecture approaches.</span></span> <span data-ttu-id="fc0b8-160">예를 들어, 중간 계층에 대 한 N 계층 아키텍처는 마이크로 서비스를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-160">For example, an N-Tier architecture may use microservices for the middle tier.</span></span> <span data-ttu-id="fc0b8-161">다양 한 방법으로 IIS 컨테이너 호스트에 가상 디렉터리에서에서 마이크로 서비스를 구현 하는 것도 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-161">It's also possible to implement microservices in a variety of ways, from virtual directories on IIS hosts to containers.</span></span> <span data-ttu-id="fc0b8-162">마이크로 서비스의 특징 있도록 서버 리스 구현에 특히 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-162">The characteristics of microservices make them especially ideal for serverless implementations.</span></span>

![마이크로 서비스 아키텍처](./media/microservices-architecture.png)

<span data-ttu-id="fc0b8-164">마이크로 서비스 아키텍처의 장점에는 다음이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-164">The pros of microservices architectures include:</span></span>

* <span data-ttu-id="fc0b8-165">리팩터링 하는 단일 서비스 격리 된 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-165">Refactoring is often isolated to a single service.</span></span>
* <span data-ttu-id="fc0b8-166">서비스는 서로 독립적으로 업그레이드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-166">Services can be upgraded independently of each other.</span></span>
* <span data-ttu-id="fc0b8-167">복원 력 및 탄력성을 개별 서비스의 요구를 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-167">Resiliency and elasticity can be tuned to the demands of individual services.</span></span>
* <span data-ttu-id="fc0b8-168">개발 플랫폼과 서로 다른 팀에서 동시에 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-168">Development can happen in parallel across disparate teams and platforms.</span></span>
* <span data-ttu-id="fc0b8-169">격리 된 서비스에 대 한 포괄적인 테스트를 작성 하는 것이 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-169">It's easier to write comprehensive tests for isolated services.</span></span>

<span data-ttu-id="fc0b8-170">마이크로 서비스 포함 하 여 고유한 과제를 수반 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-170">Microservices come with their own challenges, including:</span></span>

* <span data-ttu-id="fc0b8-171">어떤 서비스가 가능한 지 및 호출 하는 방법을 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-171">Determining what services are available and how to call them.</span></span>
* <span data-ttu-id="fc0b8-172">서비스의 수명 주기를 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-172">Managing the lifecycle of services.</span></span>
* <span data-ttu-id="fc0b8-173">서비스 함께 전체 응용 프로그램에 맞추는 방법을 이해 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-173">Understanding how services fit together in the overall application.</span></span>
* <span data-ttu-id="fc0b8-174">전체 시스템 테스트의 서로 다른 서비스에서 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-174">Full system testing of calls made across disparate services.</span></span>

<span data-ttu-id="fc0b8-175">궁극적으로 모든 나중에 설명 하는 서버 리스의 이점 이용을 포함 하 여 이러한 문제를 해결 하는 솔루션을 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc0b8-175">Ultimately there are solutions to address all of these challenges, including tapping into the benefits of serverless that are discussed later.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fc0b8-176">[이전](index.md)
>[다음](architecture-deployment-approaches.md)</span><span class="sxs-lookup"><span data-stu-id="fc0b8-176">[Previous](index.md)
[Next](architecture-deployment-approaches.md)</span></span>
