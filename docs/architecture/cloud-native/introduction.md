---
title: 클라우드 네이티브 애플리케이션 소개
description: 클라우드 기본 컴퓨팅에 대해 알아보기
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: 6ec02a1388d6e0f26cdaa1f728f23a22ba52d735
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613943"
---
# <a name="introduction-to-cloud-native-applications"></a><span data-ttu-id="f939e-103">클라우드 네이티브 애플리케이션 소개</span><span class="sxs-lookup"><span data-stu-id="f939e-103">Introduction to cloud-native applications</span></span>

<span data-ttu-id="f939e-104">다른 날에는 "다음으로 큰 문제"에 대해 작업 하 고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-104">Another day, at the office, working on "the next big thing."</span></span>

<span data-ttu-id="f939e-105">휴대폰 링입니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-105">Your cellphone rings.</span></span> <span data-ttu-id="f939e-106">새 작업에 대해 하루에 두 번 호출 하는 채용 담당자입니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-106">It's your friendly recruiter - the one who calls you twice a day about new jobs.</span></span>

<span data-ttu-id="f939e-107">그러나 이번에는 시작, 자본 및 많은 자금 등이 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-107">But this time it's different: Start-up, equity, and plenty of funding.</span></span>

<span data-ttu-id="f939e-108">클라우드 및 최첨단 기술을 언급 하면에 지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-108">The mention of the cloud and cutting-edge technology pushes you over the edge.</span></span>

<span data-ttu-id="f939e-109">몇 주 후에는 이제 디자인 세션에서 주요 전자 상거래 응용 프로그램을 설계 하는 새 직원이 될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-109">Fast forward a few weeks and you're now a new employee in a design session architecting a major eCommerce application.</span></span> <span data-ttu-id="f939e-110">선행 전자 상거래 사이트와 경쟁할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-110">You're going to compete with the leading eCommerce sites.</span></span>

<span data-ttu-id="f939e-111">빌드하는 방법</span><span class="sxs-lookup"><span data-stu-id="f939e-111">How will you build it?</span></span>

<span data-ttu-id="f939e-112">지난 15 년 동안의 지침을 따르는 경우 그림 1.1에 표시 된 시스템을 빌드할 가능성이 가장 높습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-112">If you follow the guidance from past 15 years, you'll most likely build the system shown in Figure 1.1.</span></span>

![기존 모놀리식 디자인](./media/monolithic-design.png)

<span data-ttu-id="f939e-114">**그림 1-1**.</span><span class="sxs-lookup"><span data-stu-id="f939e-114">**Figure 1-1**.</span></span> <span data-ttu-id="f939e-115">기존 모놀리식 디자인</span><span class="sxs-lookup"><span data-stu-id="f939e-115">Traditional monolithic design</span></span>

<span data-ttu-id="f939e-116">모든 도메인 논리를 포함 하는 매우 중요 한 응용 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-116">You construct a large core application containing all of your domain logic.</span></span> <span data-ttu-id="f939e-117">여기에는 Id, 카탈로그, 순서 지정 등의 모듈이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-117">It includes modules such as Identity, Catalog, Ordering, and more.</span></span> <span data-ttu-id="f939e-118">핵심 앱은 많은 관계형 데이터베이스와 통신 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-118">The core app communicates with a large relational database.</span></span> <span data-ttu-id="f939e-119">핵심은 HTML 인터페이스를 통해 기능을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-119">The core exposes functionality via an HTML interface.</span></span>

<span data-ttu-id="f939e-120">축하합니다!</span><span class="sxs-lookup"><span data-stu-id="f939e-120">Congratulations!</span></span>  <span data-ttu-id="f939e-121">방금 모놀리식 응용 프로그램을 만들었습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-121">You just created a monolithic application.</span></span>

<span data-ttu-id="f939e-122">모두 잘못 된 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-122">Not all is bad.</span></span> <span data-ttu-id="f939e-123">거은 몇 가지 이점을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-123">Monoliths offer some distinct advantages.</span></span> <span data-ttu-id="f939e-124">예를 들어, 다음은 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-124">For example, they're straightforward to...</span></span>

- <span data-ttu-id="f939e-125">build</span><span class="sxs-lookup"><span data-stu-id="f939e-125">build</span></span>
- <span data-ttu-id="f939e-126">test</span><span class="sxs-lookup"><span data-stu-id="f939e-126">test</span></span>
- <span data-ttu-id="f939e-127">배포</span><span class="sxs-lookup"><span data-stu-id="f939e-127">deploy</span></span>
- <span data-ttu-id="f939e-128">문제점</span><span class="sxs-lookup"><span data-stu-id="f939e-128">troubleshoot</span></span>
- <span data-ttu-id="f939e-129">소수 자릿수</span><span class="sxs-lookup"><span data-stu-id="f939e-129">scale</span></span>

<span data-ttu-id="f939e-130">오늘 존재 하는 많은 성공한 앱이 거로 생성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-130">Many successful apps that exist today were created as monoliths.</span></span> <span data-ttu-id="f939e-131">앱이 적중 되며 계속 해 서 진화 하 고 반복 후 반복 해 서 더 많은 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-131">The app is a hit and continues to evolve, iteration after iteration, adding more and more functionality.</span></span>

<span data-ttu-id="f939e-132">그러나 어느 시점에서 불편을 느낄 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-132">At some point, however, you begin to feel uncomfortable.</span></span> <span data-ttu-id="f939e-133">응용 프로그램에 대 한 제어 권한을 잃게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-133">You find yourself losing control of the application.</span></span> <span data-ttu-id="f939e-134">시간이 지남에 따라 느낌이 점점 더 유용 하 게 표시 되 고 궁극적으로 라는 상태를 입력 합니다 `Fear Cycle` .</span><span class="sxs-lookup"><span data-stu-id="f939e-134">As time goes on, the feeling becomes more intense and you eventually enter a state known as the `Fear Cycle`.</span></span>

- <span data-ttu-id="f939e-135">응용 프로그램은 한 사람이 이해 하지 대다수 복잡해 집니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-135">The app has become so overwhelmingly complicated that no single person understands it.</span></span>
- <span data-ttu-id="f939e-136">변경 해야 하는 경우-각 변경에 의도 하지 않으며 비용이 많이 드는 부작용이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-136">You fear making changes - each change has unintended and costly side effects.</span></span>
- <span data-ttu-id="f939e-137">새로운 기능/픽스는 복잡 하 고 시간이 많이 걸리고 구현 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-137">New features/fixes become tricky, time-consuming, and expensive to implement.</span></span>
- <span data-ttu-id="f939e-138">각 릴리스는 가능 하면 작고 전체 응용 프로그램을 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-138">Each release as small as possible and requires a full deployment of the entire application.</span></span>
- <span data-ttu-id="f939e-139">불안정 한 구성 요소 하나는 전체 시스템의 작동이 중단 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-139">One unstable component can crash the entire system.</span></span>
- <span data-ttu-id="f939e-140">새 기술 및 프레임 워크는 옵션이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-140">New technologies and frameworks aren't an option.</span></span>
- <span data-ttu-id="f939e-141">Agile 배달 방법론은 구현 하기 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-141">It's difficult to implement agile delivery methodologies.</span></span>
- <span data-ttu-id="f939e-142">아키텍처 erosion은의를 코드 베이스 deteriorates로 설정 합니다. "특별 한 사례"는 그렇지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-142">Architectural erosion sets in as the code base deteriorates with never-ending "special cases."</span></span>
- <span data-ttu-id="f939e-143">컨설턴트는 다시 작성 하는 것을 알려줍니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-143">The consultants tell you to rewrite it.</span></span>

<span data-ttu-id="f939e-144">대부분의 조직에서는 시스템을 구축 하는 클라우드 기본 방법을 채택 하 여 모놀리식 우려 주기를 해결 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-144">Many organizations have addressed the monolithic fear cycle by adopting a cloud-native approach to building systems.</span></span> <span data-ttu-id="f939e-145">그림 1-2은 클라우드 기본 기술 및 사례를 적용 하는 동일한 시스템을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-145">Figure 1-2 shows the same system built applying cloud-native techniques and practices.</span></span>

![클라우드 네이티브 디자인](./media/cloud-native-design.png)

<span data-ttu-id="f939e-147">**그림 1-2**.</span><span class="sxs-lookup"><span data-stu-id="f939e-147">**Figure 1-2**.</span></span> <span data-ttu-id="f939e-148">클라우드 네이티브 디자인</span><span class="sxs-lookup"><span data-stu-id="f939e-148">Cloud-native design</span></span>

<span data-ttu-id="f939e-149">응용 프로그램을 여러 개의 격리 된 소규모 마이크로 서비스 집합으로 분해 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-149">Note how the application is decomposed across a set of small isolated microservices.</span></span> <span data-ttu-id="f939e-150">각 서비스는 자체 포함 되며 자체 코드, 데이터 및 종속성을 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-150">Each service is self-contained and encapsulates its own code, data, and dependencies.</span></span> <span data-ttu-id="f939e-151">각는 소프트웨어 컨테이너에 배포 되 고 컨테이너 orchestrator에서 관리 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-151">Each is deployed in a software container and managed by a container orchestrator.</span></span> <span data-ttu-id="f939e-152">각 서비스는 대량 관계형 데이터베이스 대신 데이터 요구 사항에 따라 다양 한 데이터 저장소를 소유 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-152">Instead of a large relational database, each service owns it own datastore, the type of which vary based upon the data needs.</span></span> <span data-ttu-id="f939e-153">일부 서비스가 관계형 데이터베이스에 종속 되는 방법에 대해 설명 하 고 NoSQL 데이터베이스에서 다른 서비스를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-153">Note how some services depend on a relational database, but other on NoSQL databases.</span></span> <span data-ttu-id="f939e-154">한 서비스는 분산 캐시에 상태를 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-154">One service stores its state in a distributed cache.</span></span> <span data-ttu-id="f939e-155">모든 트래픽이 코어 백 엔드 서비스에 대 한 트래픽을 전달 하 고 많은 크로스 절삭 문제를 적용 하는 API 게이트웨이 서비스를 통해 라우팅하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-155">Note how all traffic routes through an API Gateway service that is responsible for directing traffic to the core back-end services and enforcing many cross-cutting concerns.</span></span> <span data-ttu-id="f939e-156">가장 중요 한 점은 응용 프로그램은 최신 클라우드 플랫폼에서 제공 하는 확장성, 가용성 및 복원 력 기능을 완전히 활용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-156">Most importantly, the application takes full advantage of the scalability, availability, and resiliency features found in modern cloud platforms.</span></span>

### <a name="cloud-native-computing"></a><span data-ttu-id="f939e-157">클라우드 네이티브 컴퓨팅</span><span class="sxs-lookup"><span data-stu-id="f939e-157">Cloud-native computing</span></span>

<span data-ttu-id="f939e-158">흠 ... _Cloud Native_라는 용어를 사용 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-158">Hmm... We just used the term, _Cloud Native_.</span></span> <span data-ttu-id="f939e-159">처음에는 "무엇을 의미 하나요?" 라고 생각할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-159">Your first thought might be, "What exactly does that mean?"</span></span> <span data-ttu-id="f939e-160">소프트웨어 공급 업체의 다른 업계 throw concocted</span><span class="sxs-lookup"><span data-stu-id="f939e-160">Another industry buzzword concocted by software vendors to market more stuff?"</span></span>

<span data-ttu-id="f939e-161">다행히이 책은 매우 다르며,이 책은 사용자의 권유를 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-161">Fortunately it's far different and hopefully this book will help convince you.</span></span>

<span data-ttu-id="f939e-162">짧은 시간 내에 클라우드 기본은 소프트웨어 업계에서 주행 추세를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-162">Within a short time, cloud native has become a driving trend in the software industry.</span></span> <span data-ttu-id="f939e-163">최신 소프트웨어 개발 사례, 기술 및 클라우드 인프라를 최대한 활용 하는 방법인 크고 복잡 한 시스템을 구축 하는 것에 대해 생각 하는 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-163">It's a new way to think about building large, complex systems, an approach that takes full advantage of modern software development practices, technologies, and cloud infrastructure.</span></span> <span data-ttu-id="f939e-164">이 방법은 시스템을 디자인, 구현, 배포 및 운영 하는 방식을 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-164">The approach changes the way you design, implement, deploy, and operationalize systems.</span></span>

<span data-ttu-id="f939e-165">업계를 구동 하는 지속적인 믿으세요와 달리 클라우드 네이티브는 _-real_입니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-165">Unlike the continuous hype that drives our industry, cloud native is _for-real_.</span></span> <span data-ttu-id="f939e-166">300이 넘는 주요 회사의 컨소시엄 인 cncf ( [Cloud Native 컴퓨팅 Foundation](https://www.cncf.io/) )를 사용 하 여 기술 및 클라우드 스택에서 클라우드 기본 컴퓨팅을 수행할 수 있도록 하는 기본 사항입니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-166">Consider the [Cloud Native Computing Foundation](https://www.cncf.io/) (CNCF), a consortium of over 300 major corporations with a charter to make cloud-native computing ubiquitous across technology and cloud stacks.</span></span> <span data-ttu-id="f939e-167">가장 영향력 있는 오픈 소스 그룹 중 하나인 GitHub에서 가장 빠르게 성장 하는 오픈 소스 프로젝트를 많이 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-167">As one of the most influential open-source groups, it hosts many of the fastest-growing open source-projects in GitHub.</span></span> <span data-ttu-id="f939e-168">[Kubernetes](https://kubernetes.io/), [프로메테우스](https://prometheus.io/), [투구](https://helm.sh/), [엔보이](https://www.envoyproxy.io/)및 [grpc](https://grpc.io/)와 같은 프로젝트를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-168">They include projects such as [Kubernetes](https://kubernetes.io/), [Prometheus](https://prometheus.io/), [Helm](https://helm.sh/), [Envoy](https://www.envoyproxy.io/), and [gRPC](https://grpc.io/).</span></span>

<span data-ttu-id="f939e-169">CNCF 발전시키는 오픈 소스 및 공급 업체 중립성의 에코 시스템을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-169">The CNCF fosters an ecosystem of open-source and vendor-neutrality.</span></span> <span data-ttu-id="f939e-170">그 후에이 책에서는 기술에 독립적인 클라우드 기본 원칙, 패턴 및 모범 사례를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-170">Following that lead, this book presents cloud-native principles, patterns, and best practices that are technology agnostic.</span></span> <span data-ttu-id="f939e-171">동시에 클라우드 네이티브 시스템을 구성 하기 위해 Microsoft Azure 클라우드에서 제공 되는 서비스 및 인프라에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f939e-171">At the same time, we discuss the services and infrastructure available in the Microsoft Azure cloud for constructing cloud-native systems.</span></span>

<span data-ttu-id="f939e-172">그렇다면 정확히 클라우드 기본 이란 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="f939e-172">So, what exactly is Cloud Native?</span></span> <span data-ttu-id="f939e-173">이 새로운 세계를 탐색 하는 데 도움을 주세요.</span><span class="sxs-lookup"><span data-stu-id="f939e-173">Sit back, relax, and let us help you explore this new world.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="f939e-174">[이전](index.md)
>[다음](definition.md)</span><span class="sxs-lookup"><span data-stu-id="f939e-174">[Previous](index.md)
[Next](definition.md)</span></span>
