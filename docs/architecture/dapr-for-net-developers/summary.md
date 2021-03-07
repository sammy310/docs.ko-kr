---
title: 요약 및 진행 방향
description: 핵심 핵심 결론을 요약 하 고 앞으로 이동 하는 방법을 살펴봅니다.
ms.date: 02/04/2021
author: robvet
ms.openlocfilehash: c15104f861dd6cfb999d3f67f19b988d1a8ffb03
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401831"
---
# <a name="summary-and-the-road-ahead"></a><span data-ttu-id="e065b-103">요약 및 진행 방향</span><span class="sxs-lookup"><span data-stu-id="e065b-103">Summary and the road ahead</span></span>

<span data-ttu-id="e065b-104">Microsoft는이에 대 한 microsoft의 고객을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-104">We're at the end of our Dapr flight.</span></span> <span data-ttu-id="e065b-105">[2 장](dapr-at-20000-feet.md) 에서 2만 피트로의 제트 비행기 비행은 최종 접근 방식으로 진행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-105">The jet plane flying at 20,000 feet from [chapter 2](dapr-at-20000-feet.md) is on final approach and about to land.</span></span>

<span data-ttu-id="e065b-106">비행기가 게이트에서 택시 면이 가이드의 몇 가지 중요 한 결론을 검토해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-106">As the plane taxis to the gate, let's take a minute to review some important conclusions from this guide:</span></span>

- <span data-ttu-id="e065b-107">D **4** -d 4는 분산 응용 프로그램을 빌드하는 방법을 간소화 하는 *배포 응용 프로그램 런타임* 입니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-107">**Dapr** - Dapr is a *Distributed Application Runtime* that streamlines how you build distributed applications.</span></span> <span data-ttu-id="e065b-108">구성 요소 및 플러그형 구성 요소의 아키텍처를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-108">It exposes an architecture of building blocks and pluggable components.</span></span> <span data-ttu-id="e065b-109">6apr는 응용 프로그램을 Eapr 런타임에 존재 하는 인프라 기능에 바인딩하는 **동적 붙이기를** 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-109">Dapr provides a **dynamic glue** that binds your application with infrastructure capabilities that exist in the Dapr runtime.</span></span> <span data-ttu-id="e065b-110">인프라를 구축 하는 대신 사용자와 팀이 비즈니스 기능을 고객에 게 제공 하는 데 주력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-110">Instead of building infrastructure plumbing, you and your team focus on delivering business features to customers.</span></span>

- <span data-ttu-id="e065b-111">**오픈 소스 및 플랫폼 간** -기본 EAPR API는 HTTP 또는 grpc를 지 원하는 *모든 플랫폼* 에서 사용 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-111">**Open source and cross-platform** - The native Dapr API can be consumed by *any platform* that supports HTTP or gRPC.</span></span> <span data-ttu-id="e065b-112">또한 d 4는 인기 있는 개발 플랫폼용 언어 관련 Sdk를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-112">Dapr also provides language-specific SDKs for popular development platforms.</span></span> <span data-ttu-id="e065b-113">Eapr v 1.0은 Go, Python, .NET, Java, PHP 및 JavaScript를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-113">Dapr v1.0 supports Go, Python, .NET, Java, PHP, and JavaScript.</span></span>

- <span data-ttu-id="e065b-114">**빌딩 블록** -4 월 빌딩 블록은 배포 응용 프로그램 기능을 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-114">**Building blocks** - Dapr building blocks encapsulate distributed application functionality.</span></span> <span data-ttu-id="e065b-115">이 문서를 작성할 당시에는 그림 11-1에 표시 된 7 개의 빌딩 블록을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-115">At the time of this writing, Dapr supports the seven building blocks shown in figure 11-1.</span></span>

![4apr 빌딩 블록](./media/dapr-at-20000-feet/building-blocks.png)

<span data-ttu-id="e065b-117">**그림 11-1**.</span><span class="sxs-lookup"><span data-stu-id="e065b-117">**Figure 11-1**.</span></span> <span data-ttu-id="e065b-118">4apr 빌딩 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-118">Dapr building blocks.</span></span>

- <span data-ttu-id="e065b-119">**구성 요소** -4apr 구성 요소는 각 6apr 빌딩 블록 기능에 대 한 구체적인 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-119">**Components** - Dapr components provide the concrete implementation for each Dapr building block capability.</span></span> <span data-ttu-id="e065b-120">개발자가 응용 프로그램 코드를 변경 하지 않고 구성 요소 구현을 교환할 수 있도록 하는 공용 인터페이스를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-120">They expose a common interface that enables developers to swap out component implementations without changing application code.</span></span> <span data-ttu-id="e065b-121">그림 11-2에서는 구성 요소, 구성 요소 및 서비스 간의 관계를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-121">Figure 11-2 shows the relationship among components, building blocks, and your service.</span></span>

![4apr 빌딩 블록 통합](./media/dapr-at-20000-feet/building-blocks-integration.png)

<span data-ttu-id="e065b-123">**그림 11-2**.</span><span class="sxs-lookup"><span data-stu-id="e065b-123">**Figure 11-2**.</span></span> <span data-ttu-id="e065b-124">4apr 빌딩 블록 통합.</span><span class="sxs-lookup"><span data-stu-id="e065b-124">Dapr building block integration.</span></span>

- <span data-ttu-id="e065b-125">**사이드카** -사이드카 아키텍처의 응용 프로그램과 함께 별도의 컨테이너 프로세스로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-125">**Sidecars** - Dapr runs alongside your application in a sidecar architecture, either as a separate process of a container.</span></span> <span data-ttu-id="e065b-126">응용 프로그램은 HTTP 및 gRPC를 통해 Eapr Api와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-126">Your application communicates with the Dapr APIs over HTTP and gRPC.</span></span> <span data-ttu-id="e065b-127">사이드카는 서비스에 포함 되지 않고 연결 된 격리 및 캡슐화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-127">Sidecars provide isolation and encapsulation as they aren't part of the service, but connected to it.</span></span> <span data-ttu-id="e065b-128">그림 11-3은 사이드카 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-128">Figure 11-3 shows a sidecar architecture.</span></span>

![사이드카 아키텍처](./media/dapr-at-20000-feet/sidecar-generic.png)

<span data-ttu-id="e065b-130">**그림 11-3**.</span><span class="sxs-lookup"><span data-stu-id="e065b-130">**Figure 11-3**.</span></span> <span data-ttu-id="e065b-131">사이드카 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="e065b-131">Sidecar architecture.</span></span>

- <span data-ttu-id="e065b-132">**호스팅 환경** 6apr는 플랫폼 간 지원을 제공 하며 여러 환경에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-132">**Hosting environments** Dapr has cross-platform support and can run in multiple environments.</span></span> <span data-ttu-id="e065b-133">이 문서를 작성할 당시에는 자체 호스트 된 로컬 모드와 Kubernetes 환경을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-133">At the time of this writing, the environments include a local self-hosted mode and Kubernetes.</span></span>

- <span data-ttu-id="e065b-134">**eShopOnDapr** -이 책에는 [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr)이라는 참조 응용 프로그램이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-134">**eShopOnDapr** - This book includes an accompanying reference application entitled [eShopOnDapr](https://github.com/dotnet-architecture/eShopOnDapr).</span></span> <span data-ttu-id="e065b-135">참조 응용 프로그램은 인기 있는 전자 상거래 응용 프로그램 도메인을 사용 하 여 각 구성 요소를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-135">Using a popular e-commerce application domain, the reference application demonstrates the usage of each building block.</span></span> <span data-ttu-id="e065b-136">몇 년 전에 릴리스되는 널리 사용 되는 [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers)의 진화입니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-136">It's an evolution of the widely popular [eShopOnContainers](https://github.com/dotnet-architecture/eShopOnContainers), released several years ago.</span></span>

## <a name="the-road-ahead"></a><span data-ttu-id="e065b-137">앞으로 이동</span><span class="sxs-lookup"><span data-stu-id="e065b-137">The road ahead</span></span>

<span data-ttu-id="e065b-138">향후에는 배포 응용 프로그램 개발에 매우 큰 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-138">Looking forward, Dapr has the potential to have a profound impact on distributed application development.</span></span> <span data-ttu-id="e065b-139">Eapr 팀과 오픈 소스 기여자에서 무엇을 받을 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="e065b-139">What can you expect from the Dapr team and its open-source contributors?</span></span>

<span data-ttu-id="e065b-140">작성 당시에는 다음과 같은 추가 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-140">At the time of writing, the list of proposed enhancements for Dapr include:</span></span>

- <span data-ttu-id="e065b-141">기존 구성 요소에 대 한 향상 된 기능:</span><span class="sxs-lookup"><span data-stu-id="e065b-141">Feature enhancements to existing building blocks:</span></span>
  - <span data-ttu-id="e065b-142">상태 관리의 쿼리 기능을 사용 하 여 여러 값을 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-142">Query capabilities in state management enabling you to retrieve multiple values.</span></span>
  - <span data-ttu-id="e065b-143">Pub/sub에서 필터링 항목을 사용 하 여 콘텐츠를 기준으로 항목을 필터링 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-143">Topic filtering in pub/sub enabling you to filter topics based on their content.</span></span>
  - <span data-ttu-id="e065b-144">관찰성의 응용 프로그램 추적 API는 특정 라이브러리에 바인딩하지 않고도 응용 프로그램에서 직접 추적 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-144">An application tracing API in observability that provides tracing in the application directly without having to bind to specific libraries.</span></span>
  - <span data-ttu-id="e065b-145">행위자 프로그래밍 모델에 이벤트 구동 기능을 제공 하는 행위자에 대 한 바인딩 및 pub/sub 지원.</span><span class="sxs-lookup"><span data-stu-id="e065b-145">Binding and pub/sub support for actors providing event driven capabilities to the actor programming model.</span></span> <span data-ttu-id="e065b-146">바인딩된 구성 요소는 이벤트 및 메시지를 트리거하고 행위자의 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-146">Bound components will trigger events and messages invoke methods in the actor.</span></span>

- <span data-ttu-id="e065b-147">새 구성 요소:</span><span class="sxs-lookup"><span data-stu-id="e065b-147">New building blocks:</span></span>
  - <span data-ttu-id="e065b-148">구성 데이터를 읽고 쓰기 위한 구성 API 빌딩 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-148">Configuration API building block for reading and writing configuration data.</span></span> <span data-ttu-id="e065b-149">이 블록은 Azure Configuration Manager 또는 GCP 구성 관리를 포함 하는 공급자에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-149">The block will bind to providers that include Azure Configuration Manager or GCP Configuration Management.</span></span>
  - <span data-ttu-id="e065b-150">0에서 시작 하는 Http 크기 자동 크기 조정.</span><span class="sxs-lookup"><span data-stu-id="e065b-150">Http scale-to-zero autoscale.</span></span>
  - <span data-ttu-id="e065b-151">단일 인스턴스 및 잠금 의미 체계 기능을 제공 하는 리더 선거 빌딩 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-151">Leader election building block to provide singleton instances and locking semantic capabilities.</span></span>
  - <span data-ttu-id="e065b-152">서비스 호출에 대 한 투명 프록시 구성 요소를 사용 하 여 네트워크 수준에서 Url 또는 DNS 주소를 기반으로 메시지를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-152">Transparent proxying building block for service invocation, enabling you to route messages based on URLs or DNS addresses at the network level.</span></span>
  - <span data-ttu-id="e065b-153">복원 력 빌딩 블록 (회로 차단기, 대량 헤드 & 시간 제한).</span><span class="sxs-lookup"><span data-stu-id="e065b-153">Resiliency building block (circuit breakers, bulkheads & timeouts).</span></span>

- <span data-ttu-id="e065b-154">프레임 워크 및 클라우드 기본 기술과 통합.</span><span class="sxs-lookup"><span data-stu-id="e065b-154">Integration with frameworks and cloud native technologies.</span></span> <span data-ttu-id="e065b-155">일부 사례:</span><span class="sxs-lookup"><span data-stu-id="e065b-155">Some examples include:</span></span>
  - <span data-ttu-id="e065b-156">Django</span><span class="sxs-lookup"><span data-stu-id="e065b-156">Django</span></span>
  - <span data-ttu-id="e065b-157">Nodejs</span><span class="sxs-lookup"><span data-stu-id="e065b-157">Nodejs</span></span>
  - <span data-ttu-id="e065b-158">고속</span><span class="sxs-lookup"><span data-stu-id="e065b-158">Express</span></span>
  - <span data-ttu-id="e065b-159">Kyma</span><span class="sxs-lookup"><span data-stu-id="e065b-159">Kyma</span></span>
  - <span data-ttu-id="e065b-160">미드웨이</span><span class="sxs-lookup"><span data-stu-id="e065b-160">Midway</span></span>

- <span data-ttu-id="e065b-161">새 언어 Sdk:</span><span class="sxs-lookup"><span data-stu-id="e065b-161">New language SDKs:</span></span>
  - <span data-ttu-id="e065b-162">JavaScript</span><span class="sxs-lookup"><span data-stu-id="e065b-162">JavaScript</span></span>
  - <span data-ttu-id="e065b-163">RUST</span><span class="sxs-lookup"><span data-stu-id="e065b-163">RUST</span></span>
  - <span data-ttu-id="e065b-164">C++</span><span class="sxs-lookup"><span data-stu-id="e065b-164">C++</span></span>

- <span data-ttu-id="e065b-165">새 호스팅 플랫폼:</span><span class="sxs-lookup"><span data-stu-id="e065b-165">New hosting platforms:</span></span>
  - <span data-ttu-id="e065b-166">VM</span><span class="sxs-lookup"><span data-stu-id="e065b-166">VMs</span></span>
  - <span data-ttu-id="e065b-167">Azure IoT Edge</span><span class="sxs-lookup"><span data-stu-id="e065b-167">Azure IoT Edge</span></span>
  - <span data-ttu-id="e065b-168">Azure Stack Edge</span><span class="sxs-lookup"><span data-stu-id="e065b-168">Azure Stack Edge</span></span>
  - <span data-ttu-id="e065b-169">Azure Service Fabric</span><span class="sxs-lookup"><span data-stu-id="e065b-169">Azure Service Fabric</span></span>

- <span data-ttu-id="e065b-170">개발자 및 운영자 생산성 도구:</span><span class="sxs-lookup"><span data-stu-id="e065b-170">Developer and operator productivity tooling:</span></span>
  - <span data-ttu-id="e065b-171">VS Code 확장입니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-171">VS Code extension.</span></span>
  - <span data-ttu-id="e065b-172">DevOps 파이프라인 개발을 위한 로컬 디버깅을 위한 원격 개발 컨테이너</span><span class="sxs-lookup"><span data-stu-id="e065b-172">Remote Dev Containers for local debugging a DevOps pipeline development.</span></span>
  - <span data-ttu-id="e065b-173">Eapr 응용 프로그램 관리의 운영 문제를 심층적으로 파악할 수 있게 해 주는 4 차 운영 대시보드 향상 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-173">Dapr operational dashboard enhancements that will provide deeper visibility into the operational concerns of managing Dapr applications.</span></span>

<span data-ttu-id="e065b-174">D 4 월 버전 1.0은 개발자에 게 배포 응용 프로그램을 빌드하기 위한 훌륭한 도구 상자를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-174">Dapr version 1.0 provides developers with a compelling toolbox for building distributed applications.</span></span> <span data-ttu-id="e065b-175">제안 된 향상 된 기능 목록에서 볼 수 있듯이, 많은 새로운 기능을 사용 하 여 Capr가 활성 개발 중입니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-175">As the proposed enhancement list shows, Dapr is under active development with many new capabilities to come.</span></span> <span data-ttu-id="e065b-176">이후 업데이트를 위해 [eapr 사이트](https://dapr.io/) 및 [eapr 알림 블로그](https://cloudblogs.microsoft.com/opensource/2019/10/16/announcing-dapr-open-source-project-build-microservice-applications/) 를 계속 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e065b-176">Stay tuned to the [Dapr site](https://dapr.io/) and [Dapr announcement blog](https://cloudblogs.microsoft.com/opensource/2019/10/16/announcing-dapr-open-source-project-build-microservice-applications/) for future updates.</span></span>

>[!div class="step-by-step"]
>[<span data-ttu-id="e065b-177">이전</span><span class="sxs-lookup"><span data-stu-id="e065b-177">Previous</span></span>](secrets.md)
