---
title: 전 세계는 20,000 피트로
description: 분산 응용 프로그램의 이점과 문제는 모놀리식 및 SOA 접근 방식을 살펴보세요.
author: robvet
ms.date: 02/07/2021
ms.openlocfilehash: b857355880c3942526d751312d98f2b822704759
ms.sourcegitcommit: 42d436ebc2a7ee02fc1848c7742bc7d80e13fc2f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2021
ms.locfileid: "102401832"
---
# <a name="the-world-is-distributed"></a><span data-ttu-id="c0847-103">전 세계는 20,000 피트로</span><span class="sxs-lookup"><span data-stu-id="c0847-103">The world is distributed</span></span>

<span data-ttu-id="c0847-104">' 쿨 어린이 '에 게 문의 하세요. *최신, 분산 시스템은 모놀리식 앱이* 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-104">Just ask any 'cool kid': *Modern, distributed systems are in, and monolithic apps are out!*</span></span>

<span data-ttu-id="c0847-105">그러나 단순히 "쿨 어린이"가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-105">But, it's not just "cool kids."</span></span> <span data-ttu-id="c0847-106">프로그레시브 IT 리더, 회사 설계자 및 astute 개발자는 최신 배포 응용 프로그램을 탐색 하 고 평가할 때 이와 동일한 생각을 에코 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-106">Progressive IT Leaders, corporate architects, and astute developers are echoing these same thoughts as they explore and evaluate modern distributed applications.</span></span> <span data-ttu-id="c0847-107">대부분은에서 구매 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-107">Many have bought in.</span></span> <span data-ttu-id="c0847-108">이러한 응용 프로그램은 배포 된 마이크로 서비스 응용 프로그램의 원칙, 패턴 및 방법에 따라 기존 엔터프라이즈 응용 프로그램을 새로 설계 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-108">They're designing new and replatforming existing enterprise applications following the principles, patterns, and practices of distributed microservice applications.</span></span>

<span data-ttu-id="c0847-109">그러나이 진화를 통해 많은 질문이 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-109">But, this evolution raises many questions...</span></span>

- <span data-ttu-id="c0847-110">배포 응용 프로그램은 정확히 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c0847-110">What exactly is a distributed application?</span></span>
- <span data-ttu-id="c0847-111">인기를 얻는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c0847-111">Why are they gaining popularity?</span></span>
- <span data-ttu-id="c0847-112">비용은 얼마 인가요?</span><span class="sxs-lookup"><span data-stu-id="c0847-112">What are the costs?</span></span>
- <span data-ttu-id="c0847-113">그리고 중요 한 점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c0847-113">And, importantly, what are the tradeoffs?</span></span>

<span data-ttu-id="c0847-114">시작 하려면 이전 15 년을 되감거나 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-114">To start, let's rewind and look at the past 15 years.</span></span> <span data-ttu-id="c0847-115">이 기간 동안에는 일반적으로 응용 프로그램을 단일 모놀리식 단위로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-115">During this period, we typically constructed applications as a single, monolithic unit.</span></span> <span data-ttu-id="c0847-116">그림 1-1은 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-116">Figure 1-1 shows the architecture.</span></span>

![모놀리식 아키텍처.](./media/the-world-is-distributed/monolithic-design.png)

<span data-ttu-id="c0847-118">**그림 1-1**.</span><span class="sxs-lookup"><span data-stu-id="c0847-118">**Figure 1-1**.</span></span> <span data-ttu-id="c0847-119">모놀리식 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="c0847-119">Monolithic architecture.</span></span>

<span data-ttu-id="c0847-120">주문, Id 및 마케팅을 위한 모듈이 단일 서버 프로세스에서 실행 되는 방식을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-120">Note how the modules for Ordering, Identity, and Marketing execute in a single-server process.</span></span> <span data-ttu-id="c0847-121">응용 프로그램 데이터는 공유 데이터베이스에 저장 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-121">Application data is stored in a shared database.</span></span> <span data-ttu-id="c0847-122">비즈니스 기능은 HTML 및 RESTful 인터페이스를 통해 노출 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-122">Business functionality is exposed via HTML and RESTful interfaces.</span></span>

<span data-ttu-id="c0847-123">여러 가지 방법으로 모놀리식 apps는 `straightforward` 입니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-123">In many ways, monolithic apps are `straightforward`.</span></span> <span data-ttu-id="c0847-124">다음과 같이 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-124">They're straightforward to:</span></span>

- <span data-ttu-id="c0847-125">빌드</span><span class="sxs-lookup"><span data-stu-id="c0847-125">Build</span></span>
- <span data-ttu-id="c0847-126">테스트</span><span class="sxs-lookup"><span data-stu-id="c0847-126">Test</span></span>
- <span data-ttu-id="c0847-127">배포</span><span class="sxs-lookup"><span data-stu-id="c0847-127">Deploy</span></span>
- <span data-ttu-id="c0847-128">문제 해결</span><span class="sxs-lookup"><span data-stu-id="c0847-128">Troubleshoot</span></span>
- <span data-ttu-id="c0847-129">수직 확장 (수직 확장)</span><span class="sxs-lookup"><span data-stu-id="c0847-129">Scale vertically (scale up)</span></span>

<span data-ttu-id="c0847-130">그러나 모놀리식 아키텍처는 상당한 문제를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-130">However, monolithic architectures can present significant challenges.</span></span>

<span data-ttu-id="c0847-131">시간이 지남에 따라 제어를 잃지 않는 지점에 도달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-131">Over time, you may reach a point where you begin to lose control...</span></span>

- <span data-ttu-id="c0847-132">단일 사람이 이해 하지 못하는 경우 모놀리식가 대다수 복잡해 집니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-132">The monolith has become so overwhelmingly complicated that no single person understands it.</span></span>
- <span data-ttu-id="c0847-133">의도 하지 않으며 비용이 많이 드는 부작용이 발생 하기 때문에 변경 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-133">You fear making changes as each brings unintended and costly side effects.</span></span>
- <span data-ttu-id="c0847-134">새로운 기능/픽스는 시간이 많이 걸리고 구현 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-134">New features/fixes become time-consuming and expensive to implement.</span></span>
- <span data-ttu-id="c0847-135">변경 내용이 가장 적은 경우에도 전체 응용 프로그램을 전체적으로 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-135">Even the smallest change requires full deployment of the entire application - expensive and risky.</span></span>
- <span data-ttu-id="c0847-136">불안정 한 구성 요소 하나는 전체 시스템의 작동이 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-136">One unstable component can crash the entire system.</span></span>
- <span data-ttu-id="c0847-137">새 기술 및 프레임 워크를 추가 하는 것은 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-137">Adding new technologies and frameworks aren't an option.</span></span>
- <span data-ttu-id="c0847-138">Agile 배달 방법론을 구현 하는 것은 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-138">Implementing agile delivery methodologies are difficult.</span></span>
- <span data-ttu-id="c0847-139">아키텍처 erosion은의를 코드 베이스 deteriorates로 설정 합니다. "특별 한 사례"는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-139">Architectural erosion sets in as the code base deteriorates with never-ending "special cases."</span></span>
- <span data-ttu-id="c0847-140">궁극적으로 컨설턴트가 제공 되며 다시 작성 하는 것을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-140">Eventually the consultants come in and tell you to rewrite it.</span></span>

<span data-ttu-id="c0847-141">이 조건을 전문가 호출 `the Fear Cycle` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-141">IT practitioners call this condition `the Fear Cycle`.</span></span> <span data-ttu-id="c0847-142">모든 기간 동안 기술 비즈니스에 경험이 있다면이를 경험 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-142">If you've been in the technology business for any length of time, good chance you've experienced it.</span></span> <span data-ttu-id="c0847-143">IT 예산에 신속한 확보가 되 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-143">It's stressful and exhausts your IT budget.</span></span> <span data-ttu-id="c0847-144">새롭고 혁신적인 솔루션을 구축 하는 대신 대부분의 예산이 레거시 앱을 유지 관리 하는 데 소요 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-144">Instead of building new and innovative solutions, most of your budget is spent maintaining legacy apps.</span></span>

<span data-ttu-id="c0847-145">비즈니스에는 걱정 하지 않아도 `speed and agility` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-145">Instead of fear, businesses require `speed and agility`.</span></span> <span data-ttu-id="c0847-146">이는 시장 조건에 신속 하 게 대응할 수 있는 아키텍처 스타일을 검색 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-146">They seek an architectural style with which they can rapidly respond to market conditions.</span></span> <span data-ttu-id="c0847-147">라이브 응용 프로그램의 작은 영역을 즉시 업데이트 하 고 개별적으로 확장 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-147">They need to instantaneously update and individually scale small areas of a live application.</span></span>

<span data-ttu-id="c0847-148">빠른 속도와 민첩성은 [서비스 지향 아키텍처](https://en.wikipedia.org/wiki/Service-oriented_architecture)또는의 형태로 제공 `SOA` 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-148">An early attempt to gain speed and agility came in the form of [Service Oriented Architecture](https://en.wikipedia.org/wiki/Service-oriented_architecture), or `SOA`.</span></span> <span data-ttu-id="c0847-149">이 모델에서 서비스 소비자 및 서비스 공급자는 협력 라고도 [Service Bus](https://en.wikipedia.org/wiki/Enterprise_service_bus)하는 미들웨어 메시징 구성 요소를 통해 또는 라고도 `ESB` 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-149">In this model, service consumers and service providers collaborated via middleware messaging components, often referred to as an [Enterprise Service Bus](https://en.wikipedia.org/wiki/Enterprise_service_bus), or `ESB`.</span></span> <span data-ttu-id="c0847-150">그림 1-2은 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-150">Figure 1-2 shows the architecture.</span></span>

![SOA.](./media/the-world-is-distributed/soa-basic.png)

<span data-ttu-id="c0847-152">**그림 1-2**.</span><span class="sxs-lookup"><span data-stu-id="c0847-152">**Figure 1-2**.</span></span> <span data-ttu-id="c0847-153">SOA 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="c0847-153">SOA architecture.</span></span>

<span data-ttu-id="c0847-154">SOA를 사용 하는 경우 ESB에 중앙 집중화 된 서비스 공급자가 등록 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-154">With SOA, centralized service providers registered with the ESB.</span></span> <span data-ttu-id="c0847-155">비즈니스 논리는 공급자와 소비자를 통합 하기 위해 ESB에 기본 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-155">Business logic would be built into the ESB to integrate providers and consumers.</span></span> <span data-ttu-id="c0847-156">그러면 서비스 소비자가 ESB를 사용 하 여 이러한 공급자를 찾고 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-156">Service consumers could then find and communicate with these providers using the ESB.</span></span>

<span data-ttu-id="c0847-157">SOA를 사용 하는 경우에도이 접근 방식을 구현 하는 것이 복잡 해지고 병목 현상이 발생 하기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-157">Despite the promises of SOA, implementing this approach often increased complexity and introduced bottlenecks.</span></span> <span data-ttu-id="c0847-158">유지 관리 비용은 ESB 미들웨어 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-158">Maintenance costs became high and ESB middleware expensive.</span></span> <span data-ttu-id="c0847-159">경향이 서비스는 커집니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-159">Services tended to be large.</span></span> <span data-ttu-id="c0847-160">일반적으로 공유 되는 종속성 및 데이터 저장소입니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-160">They often shared dependencies and data storage.</span></span> <span data-ttu-id="c0847-161">결과적으로,이는 종종 변경에 대 한 저항력이 있는 중앙 집중식 서비스와 함께 ' distributed 모놀리식 ' 구조를 생성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-161">In the end, SOAs often resulted in a 'distributed monolithic' structure with centralized services that were resistant to change.</span></span>

<span data-ttu-id="c0847-162">오늘날 대부분의 조직은 시스템을 구축 하는 분산 마이크로 서비스 아키텍처 방식을 채택 하 여 속도와 민첩성을 실현 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-162">Nowadays, many organizations have realized speed and agility by adopting a distributed microservice architectural approach to building systems.</span></span> <span data-ttu-id="c0847-163">그림 1-3에서는 분산 된 기법 및 방법을 사용 하 여 구축 된 동일한 시스템을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-163">Figure 1-3 shows the same system built using distributed techniques and practices.</span></span>

![분산 아키텍처.](./media/the-world-is-distributed/distributed-design.png)

<span data-ttu-id="c0847-165">**그림 1-3**.</span><span class="sxs-lookup"><span data-stu-id="c0847-165">**Figure 1-3**.</span></span> <span data-ttu-id="c0847-166">분산 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="c0847-166">Distributed architecture.</span></span>

<span data-ttu-id="c0847-167">분산 서비스 집합에서 동일한 응용 프로그램을 분해 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-167">Note how the same application is decomposed across a set of distributed services.</span></span> <span data-ttu-id="c0847-168">각는 자체 포함 되며 자체 코드, 데이터 및 종속성을 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-168">Each is self-contained and encapsulates its own code, data, and dependencies.</span></span> <span data-ttu-id="c0847-169">각는 소프트웨어 컨테이너에 배포 되 고 컨테이너 orchestrator에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-169">Each is deployed in a software container and managed by a container orchestrator.</span></span> <span data-ttu-id="c0847-170">각 서비스는 여러 서비스에서 공유 하는 단일 데이터베이스 대신 개인 데이터베이스를 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-170">Instead of a single database shared by multiple services, each service owns a private database.</span></span> <span data-ttu-id="c0847-171">다른 서비스는이 데이터베이스에 직접 액세스할 수 없으며, 서비스를 소유 하는 서비스의 공용 API를 통해 노출 된 데이터만 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-171">Other services can't access this database directly and can only get to data that is exposed through the public API of the service that owns it.</span></span> <span data-ttu-id="c0847-172">일부 서비스에는 완전 한 관계형 데이터베이스가 필요 하 고 다른 서비스는 NoSQL 데이터 저장소가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-172">Note how some services require a full relational database, but others, a NoSQL datastore.</span></span> <span data-ttu-id="c0847-173">바구니 서비스는 분산 키/값 캐시에 상태를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-173">The basket service stores its state in a distributed key/value cache.</span></span> <span data-ttu-id="c0847-174">인바운드 트래픽이 API 게이트웨이 서비스를 통해 라우팅되는 방법에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0847-174">Note how inbound traffic routes through an API Gateway service.</span></span> <span data-ttu-id="c0847-175">서비스에 대 한 호출을 전달 하 고 크로스 절삭 문제를 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-175">It's responsible for directing calls to  services and enforcing cross-cutting concerns.</span></span> <span data-ttu-id="c0847-176">가장 중요 한 점은 응용 프로그램은 최신 클라우드 플랫폼에서 제공 하는 확장성, 가용성 및 복원 력 기능을 완전히 활용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-176">Most importantly, the application takes full advantage of the scalability, availability, and resiliency features found in modern cloud platforms.</span></span>

<span data-ttu-id="c0847-177">그러나 분산 서비스는 민첩성과 속도를 제공할 수 있지만 다른 과제를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-177">But, while distributed services can provide agility and speed, they present a different set of challenges.</span></span> <span data-ttu-id="c0847-178">다음 사항을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="c0847-178">Consider the following...</span></span>

- <span data-ttu-id="c0847-179">분산 서비스에서 서로를 검색 하 고 동기적으로 통신 하는 방법</span><span class="sxs-lookup"><span data-stu-id="c0847-179">How can distributed services discover each other and communicate synchronously?</span></span>
- <span data-ttu-id="c0847-180">비동기 메시징을 구현 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="c0847-180">How can they implement asynchronous messaging?</span></span>
- <span data-ttu-id="c0847-181">트랜잭션 간에 컨텍스트 정보를 유지 관리 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="c0847-181">How can they maintain contextual information across a transaction?</span></span>
- <span data-ttu-id="c0847-182">오류에 대 한 복원 력을 어떻게 만들 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="c0847-182">How can they become resilient to failure?</span></span>
- <span data-ttu-id="c0847-183">변동 수요를 충족 하기 위해 확장할 수 있는 방법은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="c0847-183">How can they scale to meet fluctuating demand?</span></span>
- <span data-ttu-id="c0847-184">모니터링 및 관찰 되는 방법</span><span class="sxs-lookup"><span data-stu-id="c0847-184">How are they monitored and observed?</span></span>

<span data-ttu-id="c0847-185">이러한 각 문제에 대해 여러 제품을 사용할 수 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-185">For each of these challenges, multiple products are often available.</span></span> <span data-ttu-id="c0847-186">그러나 응용 프로그램을 제품 차이로 보호 하 고 코드를 유지 관리 가능 하 고 이식 가능한 상태로 유지 하는 것은 쉽지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-186">But, shielding your application from product differences and keeping code maintainable and portable become a challenge.</span></span>

<span data-ttu-id="c0847-187">이 책에서는 4Apr를 소개 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-187">This book introduces Dapr.</span></span> <span data-ttu-id="c0847-188">6apr는 배포 응용 프로그램 런타임입니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-188">Dapr is a distributed application runtime.</span></span> <span data-ttu-id="c0847-189">분산 응용 프로그램과 함께 제공 되는 다양 한 문제를 직접 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-189">It directly addresses many of the challenges found that come along with distributed applications.</span></span> <span data-ttu-id="c0847-190">앞서 살펴본 것 처럼, 배포 응용 프로그램 개발에는 매우 큰 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-190">Looking ahead, Dapr has the potential to have a profound impact on distributed application development.</span></span>

## <a name="summary"></a><span data-ttu-id="c0847-191">요약</span><span class="sxs-lookup"><span data-stu-id="c0847-191">Summary</span></span>

<span data-ttu-id="c0847-192">이 장에서는 분산 응용 프로그램을 채택 하는 방법을 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-192">In this chapter, we discussed the adoption of distributed applications.</span></span> <span data-ttu-id="c0847-193">Microsoft는 분산 서비스와 모놀리식 시스템 접근 방식을 대조 합니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-193">We contrasted a monolithic system approach with that of distributed services.</span></span> <span data-ttu-id="c0847-194">분산 된 접근 방식을 고려할 때 많은 일반적인 문제를 지적 했습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-194">We pointed out many of the common challenges when considering a distributed approach.</span></span>

<span data-ttu-id="c0847-195">이제는 새로운 세계의 새로운 세계를 소개 하 고 안심 하 고 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c0847-195">Now, sit back, relax, and let us introduce you the new world of Dapr.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c0847-196">[이전](foreword.md)
>[다음](dapr-at-20000-feet.md)</span><span class="sxs-lookup"><span data-stu-id="c0847-196">[Previous](foreword.md)
[Next](dapr-at-20000-feet.md)</span></span>
