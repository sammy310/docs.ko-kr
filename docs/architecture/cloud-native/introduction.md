---
title: 클라우드 네이티브 애플리케이션 소개
description: 클라우드 네이티브 컴퓨팅에 대해 알아보기
author: robvet
ms.date: 08/26/2019
ms.openlocfilehash: c9ffd34ec3deb04abddbbf85a9e5a6ed2b57c8f9
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989053"
---
# <a name="introduction-to-cloud-native-applications"></a><span data-ttu-id="a6f85-103">클라우드 네이티브 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="a6f85-103">Introduction to cloud-native applications</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="a6f85-104">또 다른 날, 사무실에서 "다음 큰 일"을 위해 일하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-104">Another day, at the office, working on "the next big thing."</span></span>

<span data-ttu-id="a6f85-105">휴대폰이 울립니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-105">Your cellphone rings.</span></span> <span data-ttu-id="a6f85-106">그것은 당신의 친절한 모집입니다 - 새로운 직업에 대해 하루에 두 번 당신을 호출 하는 사람.</span><span class="sxs-lookup"><span data-stu-id="a6f85-106">It's your friendly recruiter - the one who calls you twice a day about new jobs.</span></span>

<span data-ttu-id="a6f85-107">그러나 이번에는 스타트업, 자본 및 많은 자금 조달이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-107">But this time it's different: Start-up, equity, and plenty of funding.</span></span>

<span data-ttu-id="a6f85-108">클라우드와 최첨단 기술에 대한 언급은 당신을 엣지로 밀어넣습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-108">The mention of the cloud and cutting-edge technology pushes you over the edge.</span></span>

<span data-ttu-id="a6f85-109">몇 주 를 빨리 감기 당신은 지금 주요 전자 상거래 응용 프로그램을 설계 하는 디자인 세션에서 새로운 직원.</span><span class="sxs-lookup"><span data-stu-id="a6f85-109">Fast forward a few weeks and you're now a new employee in a design session architecting a major eCommerce application.</span></span> <span data-ttu-id="a6f85-110">다른 주요 전자 상거래 사이트를 완료할 예정입니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-110">You're going to complete with other leading eCommerce sites.</span></span>

<span data-ttu-id="a6f85-111">어떻게 구축 하시겠습니까?</span><span class="sxs-lookup"><span data-stu-id="a6f85-111">How will you build it?</span></span>

<span data-ttu-id="a6f85-112">지난 15년간의 지침을 따르면 그림 1.1에 표시된 시스템을 빌드할 가능성이 큽입니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-112">If you follow the guidance from past 15 years, you'll most likely build the system shown in Figure 1.1.</span></span>

![전통적인 모놀리식 디자인](./media/monolithic-design.png)

<span data-ttu-id="a6f85-114">**그림 1-1 .**</span><span class="sxs-lookup"><span data-stu-id="a6f85-114">**Figure 1-1**.</span></span> <span data-ttu-id="a6f85-115">전통적인 모놀리식 디자인</span><span class="sxs-lookup"><span data-stu-id="a6f85-115">Traditional monolithic design</span></span>

<span data-ttu-id="a6f85-116">모든 도메인 논리를 포함하는 대규모 코어 응용 프로그램을 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-116">You construct a large core application containing all of your domain logic.</span></span> <span data-ttu-id="a6f85-117">여기에는 ID, 카탈로그, 주문 등과 같은 모듈이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-117">It includes modules such as Identity, Catalog, Ordering, and more.</span></span> <span data-ttu-id="a6f85-118">핵심 앱은 큰 관계형 데이터베이스와 통신합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-118">The core app communicates with a large relational database.</span></span> <span data-ttu-id="a6f85-119">코어는 HTML 인터페이스를 통해 기능을 노출합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-119">The core exposes functionality via an HTML interface.</span></span>

<span data-ttu-id="a6f85-120">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="a6f85-120">Congratulations!</span></span>  <span data-ttu-id="a6f85-121">방금 모놀리식 응용 프로그램을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-121">You just created a monolithic application.</span></span>

<span data-ttu-id="a6f85-122">모든 것이 나쁘지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-122">Not all is bad.</span></span> <span data-ttu-id="a6f85-123">모놀리스는 몇 가지 뚜렷한 이점을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-123">Monoliths offer some distinct advantages.</span></span> <span data-ttu-id="a6f85-124">예를 들어, 그들은 간단합니다 ...</span><span class="sxs-lookup"><span data-stu-id="a6f85-124">For example, they're straightforward to...</span></span>

- <span data-ttu-id="a6f85-125">build</span><span class="sxs-lookup"><span data-stu-id="a6f85-125">build</span></span>
- <span data-ttu-id="a6f85-126">test</span><span class="sxs-lookup"><span data-stu-id="a6f85-126">test</span></span>
- <span data-ttu-id="a6f85-127">배포</span><span class="sxs-lookup"><span data-stu-id="a6f85-127">deploy</span></span>
- <span data-ttu-id="a6f85-128">문제 해결</span><span class="sxs-lookup"><span data-stu-id="a6f85-128">troubleshoot</span></span>
- <span data-ttu-id="a6f85-129">소수 자릿수</span><span class="sxs-lookup"><span data-stu-id="a6f85-129">scale</span></span>

<span data-ttu-id="a6f85-130">오늘날 존재하는 많은 성공적인 앱이 모놀리스로 만들어졌습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-130">Many successful apps that exist today were created as monoliths.</span></span> <span data-ttu-id="a6f85-131">이 앱은 인기를 얻었으며 반복 후 계속 진화하여 점점 더 많은 기능을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-131">The app is a hit and continues to evolve, iteration after iteration, adding more and more functionality.</span></span>

<span data-ttu-id="a6f85-132">그러나 어느 시점에서, 당신은 불편을 느끼기 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-132">At some point, however, you begin to feel uncomfortable.</span></span> <span data-ttu-id="a6f85-133">당신은 자신이 응용 프로그램의 제어를 잃고 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-133">You find yourself losing control of the application.</span></span> <span data-ttu-id="a6f85-134">시간이 지남에 따라, 느낌은 더 강렬해지고 당신은 결국 **공포 주기로**알려진 상태로 들어갑니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-134">As time goes on, the feeling becomes more intense and you eventually enter a state known as the **Fear Cycle**.</span></span>

- <span data-ttu-id="a6f85-135">응용 프로그램은 하나의 사람이 그것을 이해하지 너무 압도적으로 복잡해지고있다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-135">The app has become so overwhelmingly complicated that no single person understands it.</span></span>
- <span data-ttu-id="a6f85-136">변경이 두려워 - 각 변경은 의도하지 않고 비용이 많이 드는 부작용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-136">You fear making changes - each change has unintended and costly side effects.</span></span>
- <span data-ttu-id="a6f85-137">새로운 기능/수정 프로그램은 구현하기가 까다롭고 시간이 많이 걸리며 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-137">New features/fixes become tricky, time-consuming, and expensive to implement.</span></span>
- <span data-ttu-id="a6f85-138">각 릴리스는 전체 응용 프로그램의 전체 배포가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-138">Each release as small as it may be requires a full deployment of the entire application.</span></span>
- <span data-ttu-id="a6f85-139">하나의 불안정한 구성 요소는 전체 시스템을 충돌시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-139">One unstable component can crash the entire system.</span></span>
- <span data-ttu-id="a6f85-140">새로운 기술과 프레임워크는 선택 사항이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-140">New technologies and frameworks aren't an option.</span></span>
- <span data-ttu-id="a6f85-141">민첩한 전달 방법을 구현하기는 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-141">It's difficult to implement agile delivery methodologies.</span></span>
- <span data-ttu-id="a6f85-142">코드 베이스가 "특별한 경우"로 악화됨에 따라 아키텍처 침식이 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-142">Architectural erosion sets in as the code base deteriorates with never-ending "special cases."</span></span>
- <span data-ttu-id="a6f85-143">컨설턴트는 다시 작성하라고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-143">The consultants tell you to rewrite it.</span></span>

<span data-ttu-id="a6f85-144">많은 조직에서 시스템 구축에 클라우드 네이티브 접근 방식을 채택하여 모놀리식 공포 주기를 해결했습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-144">Many organizations have addressed the monolithic fear cycle by adopting a cloud-native approach to building systems.</span></span> <span data-ttu-id="a6f85-145">그림 1-2는 클라우드 네이티브 기술과 사례를 적용하여 구축된 동일한 시스템을 보여 주었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-145">Figure 1-2 shows the same system built applying cloud-native techniques and practices.</span></span>

![클라우드 네이티브 디자인](./media/cloud-native-design.png)

<span data-ttu-id="a6f85-147">**그림 1-2 .**</span><span class="sxs-lookup"><span data-stu-id="a6f85-147">**Figure 1-2**.</span></span> <span data-ttu-id="a6f85-148">클라우드 네이티브 디자인</span><span class="sxs-lookup"><span data-stu-id="a6f85-148">Cloud-native design</span></span>

<span data-ttu-id="a6f85-149">응용 프로그램이 작은 격리된 마이크로 서비스 집합에서 분해되는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-149">Note how the application is decomposed across a set of small isolated microservices.</span></span> <span data-ttu-id="a6f85-150">각 서비스는 자체 포함되며 자체 코드, 데이터 및 종속성을 캡슐화합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-150">Each service is self-contained and encapsulates its own code, data, and dependencies.</span></span> <span data-ttu-id="a6f85-151">각 하나는 소프트웨어 컨테이너에 배포되고 컨테이너 오케스트레이터에 의해 관리됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-151">Each is deployed in a software container and managed by a container orchestrator.</span></span> <span data-ttu-id="a6f85-152">큰 관계형 데이터베이스 대신 각 서비스는 데이터 저장소를 소유하며, 그 유형은 데이터 요구 사항에 따라 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-152">Instead of a large relational database, each service owns it own datastore, the type of which vary based upon the data needs.</span></span> <span data-ttu-id="a6f85-153">일부 서비스는 관계형 데이터베이스에 종속되지만 다른 서비스는 NoSQL 데이터베이스에 종속됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-153">Note how some services depend on a relational database, but other on NoSQL databases.</span></span> <span data-ttu-id="a6f85-154">한 서비스는 해당 상태를 분산 캐시에 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-154">One service stores its state in a distributed cache.</span></span> <span data-ttu-id="a6f85-155">트래픽을 핵심 백 엔드 서비스로 라우팅하고 많은 교차 절단 문제를 적용하는 API Gateway 서비스를 통해 모든 트래픽이 어떻게 라우팅되는지 에 유의하십시오.</span><span class="sxs-lookup"><span data-stu-id="a6f85-155">Note how all traffic routes through an API Gateway service that is responsible for routing traffic to the core back-end services  and enforcing many cross-cutting concerns.</span></span> <span data-ttu-id="a6f85-156">가장 중요한 것은 응용 프로그램이 최신 클라우드 플랫폼에서 발견되는 확장성 및 복원력 기능을 최대한 활용합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-156">Most importantly, the application takes full advantage of the scalability and resiliency features found in modern cloud platforms.</span></span>

### <a name="cloud-native-computing"></a><span data-ttu-id="a6f85-157">클라우드 네이티브 컴퓨팅</span><span class="sxs-lookup"><span data-stu-id="a6f85-157">Cloud-native computing</span></span>

<span data-ttu-id="a6f85-158">흠... 방금 "클라우드 네이티브"라는 용어를*사용했습니다.*</span><span class="sxs-lookup"><span data-stu-id="a6f85-158">Hmm... We just used the term, "*Cloud Native*."</span></span> <span data-ttu-id="a6f85-159">처음에는 "그게 정확히 무슨 뜻인가요?" 하고 생각했을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-159">You first thought might be, "What exactly does that mean?"</span></span> <span data-ttu-id="a6f85-160">소프트웨어 공급업체가 더 많은 물건을 시장에 출시하는 또 다른 업계의 유행어가 죠?"</span><span class="sxs-lookup"><span data-stu-id="a6f85-160">Another industry buzzword concocted by software vendors to market more stuff?"</span></span>

<span data-ttu-id="a6f85-161">다행히도 그것은 훨씬 다르며이 책이 당신을 설득하는 데 도움이되기를 바랍니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-161">Fortunately it's far different and hopefully this book will help convince you.</span></span>

<span data-ttu-id="a6f85-162">짧은 시간 내에 클라우드 네이티브는 소프트웨어 업계의 주도적인 트렌드가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-162">Within a short time, cloud native has become a driving trend in the software industry.</span></span> <span data-ttu-id="a6f85-163">현대의 소프트웨어 개발 관행, 기술 및 클라우드 인프라를 최대한 활용하는 대규모의 복잡한 시스템을 구축하는 방법에 대해 생각하는 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-163">It's a new way to think about building large, complex systems, an approach that takes full advantage of modern software development practices, technologies, and cloud infrastructure.</span></span> <span data-ttu-id="a6f85-164">이 접근 방식은 시스템을 설계, 구현, 배포 및 운영하는 방식을 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-164">The approach changes the way you design, implement, deploy, and operationalize systems.</span></span>

<span data-ttu-id="a6f85-165">우리 산업을 이끄는 지속적인 과대 광고와는 달리 클라우드 네이티브는 *"for-real"입니다.*</span><span class="sxs-lookup"><span data-stu-id="a6f85-165">Unlike the continuous hype that drives our industry, cloud native is "*for-real*".</span></span> <span data-ttu-id="a6f85-166">300개 이상의 대기업컨소시엄인 클라우드 네이티브 컴퓨팅 재단(CNCF)을 통해 기술 및 클라우드 스택 전반에 걸쳐 클라우드 네이티브 컴퓨팅을 유비쿼터스로 만들 수 있습니다. [Cloud Native Computing Foundation](https://www.cncf.io/)</span><span class="sxs-lookup"><span data-stu-id="a6f85-166">Consider the [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), a consortium of over 300 major corporations with a charter to make cloud-native computing ubiquitous across technology and cloud stacks.</span></span> <span data-ttu-id="a6f85-167">가장 영향력 있는 오픈 소스 그룹 중 하나인 이 그룹은 GitHub에서 가장 빠르게 성장하는 오픈 소스 프로젝트를 많이 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-167">As one of the most influential open-source groups, it hosts many of the fastest-growing open source-projects in GitHub.</span></span> <span data-ttu-id="a6f85-168">여기에는 [Kubernetes,](https://kubernetes.io/) [프로메테우스,](https://prometheus.io/) [헬름,](https://helm.sh/) [특사](https://www.envoyproxy.io/)및 [gRPC와](https://grpc.io/)같은 프로젝트가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-168">They include projects such as [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Envoy](https://www.envoyproxy.io/), and [gRPC](https://grpc.io/).</span></span>

<span data-ttu-id="a6f85-169">CNCF는 오픈 소스 및 벤더 중립성의 생태계를 육성합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-169">The CNCF fosters an ecosystem of open-source and vendor-neutrality.</span></span> <span data-ttu-id="a6f85-170">이러한 원칙에 따라 기술에 구애받지 않는 클라우드 네이티브 원칙, 패턴 및 모범 사례를 제시합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-170">Following that lead, we present cloud-native principles, patterns, and best practices that are technology agnostic.</span></span> <span data-ttu-id="a6f85-171">동시에 클라우드 네이티브 시스템을 구축하기 위해 Microsoft Azure 클라우드에서 사용할 수 있는 서비스와 인프라에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-171">At the same time, we discuss the services and infrastructure available in the Microsoft Azure cloud for constructing cloud-native systems.</span></span>

<span data-ttu-id="a6f85-172">그렇다면 클라우드 네이티브란 정확히 무엇일까요?</span><span class="sxs-lookup"><span data-stu-id="a6f85-172">So, what exactly is Cloud Native?</span></span> <span data-ttu-id="a6f85-173">앉아서 휴식을 취하고이 새로운 세계를 탐험할 수 있도록 도와드리겠습니다.</span><span class="sxs-lookup"><span data-stu-id="a6f85-173">Sit back, relax, and let us help you explore this new world.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="a6f85-174">[이전](index.md)
>[다음](definition.md)</span><span class="sxs-lookup"><span data-stu-id="a6f85-174">[Previous](index.md)
[Next](definition.md)</span></span>
