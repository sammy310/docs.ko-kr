---
title: 컨테이너 및 오케스트레이터 활용
description: Azure에서 Docker 컨테이너 및 Kubernetes Orchestrator 활용
ms.date: 06/30/2019
ms.openlocfilehash: 7b136ed2760ea471f42ff82d20298ff8714c6dee
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841764"
---
# <a name="leveraging-containers-and-orchestrators"></a><span data-ttu-id="b41ab-103">컨테이너 및 오케스트레이터 활용</span><span class="sxs-lookup"><span data-stu-id="b41ab-103">Leveraging containers and orchestrators</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="b41ab-104">컨테이너 및 orchestrator는 모놀리식 배포 방법에 일반적으로 발생 하는 문제를 해결 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-104">Containers and orchestrators are designed to solve problems common to monolithic deployment approaches.</span></span>

## <a name="challenges-with-monolithic-deployments"></a><span data-ttu-id="b41ab-105">모놀리식 배포 문제</span><span class="sxs-lookup"><span data-stu-id="b41ab-105">Challenges with monolithic deployments</span></span>

<span data-ttu-id="b41ab-106">일반적으로 대부분의 응용 프로그램은 단일 단위로 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-106">Traditionally, most applications have been deployed as a single unit.</span></span> <span data-ttu-id="b41ab-107">이러한 응용 프로그램을 monolith 라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-107">Such applications are referred to as a monolith.</span></span> <span data-ttu-id="b41ab-108">그림 3-1에 표시 된 것 처럼 여러 모듈 또는 어셈블리로 구성 된 경우에도 응용 프로그램을 단일 단위로 배포 하는 일반적인 방법은 모놀리식 architecture 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-108">This general approach of deploying applications as single units even if they're composed of multiple modules or assemblies is known as monolithic architecture, as shown in Figure 3-1.</span></span>

![모놀리식 아키텍처.](./media/monolithic-architecture.png)

<span data-ttu-id="b41ab-110">**그림 3-1**.</span><span class="sxs-lookup"><span data-stu-id="b41ab-110">**Figure 3-1**.</span></span> <span data-ttu-id="b41ab-111">모놀리식 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="b41ab-111">Monolithic architecture.</span></span>

<span data-ttu-id="b41ab-112">모놀리식 아키텍처는 간단 하지만 다음과 같은 다양 한 문제를 겪고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-112">Although they have the benefit of simplicity, monolithic architectures face a number of challenges:</span></span>

### <a name="deployments"></a><span data-ttu-id="b41ab-113">배포</span><span class="sxs-lookup"><span data-stu-id="b41ab-113">Deployments</span></span>

<span data-ttu-id="b41ab-114">모놀리식 응용 프로그램에 배포 하는 경우 일반적으로 하나의 작은 모듈만 교체 하더라도 전체 응용 프로그램을 다시 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-114">Deploying to monolithic applications typically requires restarting the entire application, even if only one small module is being replaced.</span></span> <span data-ttu-id="b41ab-115">응용 프로그램을 호스팅하는 컴퓨터의 수에 따라 배포 중에 가동 중지 시간이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-115">Depending on the number of machines hosting the application, this can result in downtime during deployments.</span></span>

### <a name="hosting"></a><span data-ttu-id="b41ab-116">호스팅</span><span class="sxs-lookup"><span data-stu-id="b41ab-116">Hosting</span></span>

<span data-ttu-id="b41ab-117">모놀리식 응용 프로그램은 단일 컴퓨터 인스턴스에서 완전히 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-117">Monolithic applications are hosted entirely on a single machine instance.</span></span> <span data-ttu-id="b41ab-118">이렇게 하려면 분산 응용 프로그램의 모든 모듈에 필요한 것 보다 높은 기능을 필요로 하는 하드웨어가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-118">This may require higher-capability hardware than any module in a distributed application would need.</span></span> <span data-ttu-id="b41ab-119">또한 앱의 어느 부분도 병목 상태가 되 면 전체 응용 프로그램을 확장 하기 위해 추가 컴퓨터 노드에 배포 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-119">Also, if any part of the app becomes a bottleneck, the entire application must be deployed to additional machine nodes in order to scale out.</span></span>

### <a name="environment"></a><span data-ttu-id="b41ab-120">환경</span><span class="sxs-lookup"><span data-stu-id="b41ab-120">Environment</span></span>

<span data-ttu-id="b41ab-121">모놀리식 응용 프로그램은 일반적으로 기존 호스팅 환경 (운영 체제, 설치 된 프레임 워크 등)에 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-121">Monolithic applications are typically deployed into an existing hosting environment (operating system, installed frameworks, etc.).</span></span> <span data-ttu-id="b41ab-122">이 환경은 응용 프로그램을 개발 하거나 테스트 한 환경과 일치 하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-122">This environment may not match the environment in which the application was developed or tested.</span></span> <span data-ttu-id="b41ab-123">응용 프로그램 환경의 불일치는 모놀리식 배포에 대 한 문제의 일반적인 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-123">Inconsistencies in the application's environment are a common source of problems for monolithic deployments.</span></span>

### <a name="coupling"></a><span data-ttu-id="b41ab-124">커플링</span><span class="sxs-lookup"><span data-stu-id="b41ab-124">Coupling</span></span>

<span data-ttu-id="b41ab-125">모놀리식 응용 프로그램은 응용 프로그램의 서로 다른 부분과 응용 프로그램 및 해당 환경 간에 상당한 결합을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-125">Monolithic applications are likely to have a great deal of coupling between different parts of the application, and between the application and its environment.</span></span> <span data-ttu-id="b41ab-126">이를 통해 다른 구현에서 확장성 또는 교환을 향상 시키기 위해 특정 서비스나 문제를 나중에 파악 하기 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-126">This can make it difficult to factor out a particular service or concern later, in order to increase its scalability or swap in an alternative implementation.</span></span> <span data-ttu-id="b41ab-127">이러한 결합으로 인해 시스템 변경에 대 한 잠재적 영향이 크게 증가 하 여 대규모 응용 프로그램에서 광범위 하 게 테스트 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-127">This coupling also leads to much larger potential impacts for changes to the system, requiring extensive testing in larger applications.</span></span>

### <a name="technology-choice"></a><span data-ttu-id="b41ab-128">기술 선택</span><span class="sxs-lookup"><span data-stu-id="b41ab-128">Technology choice</span></span>

<span data-ttu-id="b41ab-129">모놀리식 응용 프로그램은 하나의 단위로 빌드되고 배포 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-129">Monolithic applications are built and deployed as a unit.</span></span> <span data-ttu-id="b41ab-130">이를 통해 간단 하 고 일관성을 제공 하지만 혁신의 장벽 일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-130">This offers simplicity and uniformity but can be a barrier to innovation.</span></span> <span data-ttu-id="b41ab-131">시스템의 새 기능이 나 모듈이 보다 최신 플랫폼 또는 프레임 워크에 더 적합할 수 있지만 일관성을 위해 응용 프로그램의 현재 접근 방법 및 개발 및 배포의 용이성을 사용 하 여 빌드될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-131">Although a new feature or module in the system might be better-suited to a more modern platform or framework, it's likely to be built using the application's current approach for the sake of consistency as well as ease of development and deployment.</span></span>

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a><span data-ttu-id="b41ab-132">컨테이너와 orchestrator의 이점은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b41ab-132">What are the benefits of containers and orchestrators?</span></span>

<span data-ttu-id="b41ab-133">Docker는 가장 인기 있는 컨테이너 관리 및 이미징 플랫폼으로, Linux 및 Windows에서 컨테이너를 신속 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-133">Docker is the most popular container management and imaging platform and allows you to quickly work with containers on Linux and Windows.</span></span> <span data-ttu-id="b41ab-134">컨테이너는 모든 시스템에서 동일한 방식으로 실행 되는 별도의 재현 가능한 응용 프로그램 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-134">Containers provide separate but reproducible application environments that run the same way on any system.</span></span> <span data-ttu-id="b41ab-135">이렇게 하면 클라우드 네이티브 응용 프로그램에서 응용 프로그램 및 앱 구성 요소를 개발 하 고 호스팅하는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-135">This makes them perfect for developing and hosting applications and app components in cloud-native applications.</span></span> <span data-ttu-id="b41ab-136">컨테이너는 서로 격리 되므로 충돌을 유발 하는 종속성 없이 동일한 호스트 하드웨어의 두 컨테이너는 서로 다른 버전의 소프트웨어와 운영 체제도 설치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-136">Containers are isolated from one another, so two containers on the same host hardware can have different versions of software and even operating system installed, without the dependencies causing conflicts.</span></span>

<span data-ttu-id="b41ab-137">그리고 컨테이너는 소스 제어에 체크 인할 수 있는 간단한 파일에 의해 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-137">What’s more, containers are defined by simple files that can be checked into source control.</span></span> <span data-ttu-id="b41ab-138">업데이트를 적용 하거나 추가 서비스를 설치 하기 위해 수동 작업을 수행 해야 하는 가상 컴퓨터를 비롯 하 여 전체 서버와 달리 컨테이너 인프라를 사용 하면 버전을 쉽게 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-138">Unlike full servers, even virtual machines, which frequently require manual work to apply updates or install additional services, container infrastructure can easily be version-controlled.</span></span> <span data-ttu-id="b41ab-139">따라서 컨테이너에서 실행 되도록 빌드된 앱은 자동화 된 도구를 사용 하 여 빌드 파이프라인의 일부로 개발, 테스트 및 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-139">Thus, apps built to run in containers can be developed, tested, and deployed using automated tools as part of a build pipeline.</span></span>

<span data-ttu-id="b41ab-140">컨테이너는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-140">Containers are immutable.</span></span> <span data-ttu-id="b41ab-141">컨테이너의 정의가 있으면 해당 컨테이너를 다시 만들 수 있으며 동일한 방식으로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-141">Once you have the definition of a container, you can recreate that container and it will run exactly the same way.</span></span> <span data-ttu-id="b41ab-142">이 불변성은 구성 요소 기반 디자인에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-142">This immutability lends itself to component-based design.</span></span> <span data-ttu-id="b41ab-143">응용 프로그램의 일부는 자주 변경 되지 않는 부분을 자주 변경 하는 경우에만 전체 앱을 다시 배포 하는 이유는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b41ab-143">If some parts of an application don’t change as often as others, why redeploy the entire app when you can just deploy the parts that change most frequently?</span></span> <span data-ttu-id="b41ab-144">앱의 다양 한 기능 및 교차를 분리 하는 작업은 별도의 단위로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-144">Different features and cross-cutting concerns of an app can be broken up into separate units.</span></span> <span data-ttu-id="b41ab-145">그림 3-2에서는 특정 기능이 나 기능을 위임 하 여 모놀리식 앱이 컨테이너 및 마이크로 서비스를 활용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-145">Figure 3-2 shows how a monolithic app can take advantage of containers and microservices by delegating certain features or functionality.</span></span> <span data-ttu-id="b41ab-146">앱 자체의 나머지 기능도 컨테이너 화 된 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-146">The remaining functionality in the app itself has also been containerized.</span></span>

<span data-ttu-id="b41ab-147">모놀리식 앱을 분리 하 여 백 엔드에서 마이크로 서비스를 사용할 ![. **그림 3-2**을](./media/breaking-up-monolith-with-backend-microservices.png)
합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-147">![Breaking up a monolithic app to use microservices in the back end.](./media/breaking-up-monolith-with-backend-microservices.png)
**Figure 3-2**.</span></span> <span data-ttu-id="b41ab-148">백 엔드에서 마이크로 서비스를 사용 하도록 모놀리식 앱을 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-148">Breaking up a monolithic app to use microservices in the back end.</span></span>

<span data-ttu-id="b41ab-149">별도 컨테이너를 사용 하 여 빌드된 클라우드 네이티브 앱은 필요한 만큼 응용 프로그램을 배포 하는 기능을 활용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-149">Cloud-native apps built using separate containers benefit from the ability to deploy as much or as little of an application as needed.</span></span> <span data-ttu-id="b41ab-150">각 서비스에 해당 하는 리소스가 있는 노드에서 개별 서비스를 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-150">Individual services can be hosted on nodes with resources appropriate to each service.</span></span> <span data-ttu-id="b41ab-151">각 서비스를 실행 하는 환경은 변경할 수 없으며, 개발, 테스트 및 프로덕션 간에 공유할 수 있으며, 쉽게 버전을 관리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-151">The environment each service runs in is immutable, can be shared between dev, test, and production, and can easily be versioned.</span></span> <span data-ttu-id="b41ab-152">응용 프로그램의 서로 다른 영역 간 결합은 서비스 간 호출 또는 메시지로 명시적으로 발생 하며,이는 monolith 내에서 컴파일 타임 종속성이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-152">Coupling between different areas of the application occurs explicitly as calls or messages between services, not compile-time dependencies within the monolith.</span></span> <span data-ttu-id="b41ab-153">그리고 전체 앱의 지정 된 부분은 나머지 앱을 변경할 필요 없이 해당 기능이 나 기능에 가장 적합 한 기술을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-153">And any given part of the overall app can choose the technology that makes the most sense for that feature or capability without requiring changes to the rest of the app.</span></span>

## <a name="what-are-the-scaling-benefits"></a><span data-ttu-id="b41ab-154">크기 조정 혜택은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b41ab-154">What are the scaling benefits?</span></span>

<span data-ttu-id="b41ab-155">컨테이너를 기반으로 하는 서비스는 Kubernetes 같은 오케스트레이션 도구에서 제공 하는 크기 조정 혜택을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-155">Services built on containers can leverage scaling benefits provided by orchestration tools like Kubernetes.</span></span> <span data-ttu-id="b41ab-156">기본적으로 컨테이너는 자신에 대 한 정보를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-156">By design containers only know about themselves.</span></span> <span data-ttu-id="b41ab-157">함께 작업 해야 하는 여러 컨테이너를 시작 하는 경우에는 더 높은 수준으로 구성 하는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-157">Once you start to have multiple containers that need to work together, it can be worthwhile to organize them at a higher level.</span></span> <span data-ttu-id="b41ab-158">많은 수의 컨테이너와 네트워크 구성과 같은 공유 종속성을 구성 하는 것은 오케스트레이션 도구가 날짜를 절약 하는 데 제공 되는 위치입니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-158">Organizing large numbers of containers and their shared dependencies, such as network configuration, is where orchestration tools come in to save the day!</span></span> <span data-ttu-id="b41ab-159">Kubernetes는 컨테이너 화 된 응용 프로그램의 배포, 크기 조정 및 관리를 자동화 하도록 설계 된 컨테이너 오케스트레이션 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-159">Kubernetes is a container orchestration platform designed to automate deployment, scaling, and management of containerized applications.</span></span> <span data-ttu-id="b41ab-160">컨테이너 그룹의 위에 추상화 계층을 만들고이를 *pod*로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-160">It creates an abstraction layer on top of groups of containers and organizes them into *pods*.</span></span> <span data-ttu-id="b41ab-161">Pod는 *노드라고*하는 작업자 컴퓨터에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-161">Pods run on worker machines referred to as *nodes*.</span></span> <span data-ttu-id="b41ab-162">전체적으로 구성 된 그룹을 *클러스터*라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-162">The whole organized group is referred to as a *cluster*.</span></span> <span data-ttu-id="b41ab-163">그림 3-3에서는 Kubernetes 클러스터의 여러 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-163">Figure 3-3 shows the different components of a Kubernetes cluster.</span></span>

<span data-ttu-id="b41ab-164">Kubernetes 클러스터 구성 요소를 ![합니다. **그림 3-3**을](./media/kubernetes-cluster-components.png)
합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-164">![Kubernetes cluster components.](./media/kubernetes-cluster-components.png)
**Figure 3-3**.</span></span> <span data-ttu-id="b41ab-165">Kubernetes 클러스터 구성 요소</span><span class="sxs-lookup"><span data-stu-id="b41ab-165">Kubernetes cluster components.</span></span>

<span data-ttu-id="b41ab-166">Kubernetes에는 수요에 맞게 클러스터 크기를 조정 하는 기능이 기본적으로 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-166">Kubernetes has built-in support for scaling clusters to meet demand.</span></span> <span data-ttu-id="b41ab-167">컨테이너 화 된 마이크로 서비스와 결합 되어 클라우드 네이티브 응용 프로그램에 필요한 경우 추가 리소스를 사용 하 여 수요 급증에 신속 하 고 효율적으로 대응할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-167">Combined with containerized micro-services, this provides cloud-native applications with the ability to quickly and efficiently respond to spikes in demand with additional resources when and where they're needed.</span></span>

### <a name="declarative-versus-imperative"></a><span data-ttu-id="b41ab-168">선언적 및 명령적</span><span class="sxs-lookup"><span data-stu-id="b41ab-168">Declarative versus imperative</span></span>

<span data-ttu-id="b41ab-169">Kubernetes는 선언적 및 명령적 개체 구성을 모두 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-169">Kubernetes supports both declarative and imperative object configuration.</span></span> <span data-ttu-id="b41ab-170">명령적 방식에는 각 단계를 수행할 작업을 Kubernetes 알려주는 다양 한 명령이 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-170">The imperative approach involves running various commands that tell Kubernetes what to do each step of the way.</span></span> <span data-ttu-id="b41ab-171">이 이미지를 *실행* 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-171">*Run* this image.</span></span> <span data-ttu-id="b41ab-172">이 pod를 *삭제* 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-172">*Delete* this pod.</span></span> <span data-ttu-id="b41ab-173">이 포트를 *노출* 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-173">*Expose* this port.</span></span> <span data-ttu-id="b41ab-174">선언적 방법을 사용 하는 경우 *수행할* 작업 대신 *원하는* 작업을 설명 하는 구성 파일을 사용 하 고 Kubernetes 원하는 최종 상태를 얻기 위해 수행할 작업을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-174">With the declarative approach, you use a configuration file that describes *what you want* instead of *what to do* and Kubernetes figures out what to do to achieve the desired end state.</span></span> <span data-ttu-id="b41ab-175">명령적 명령을 사용 하 여 클러스터를 이미 구성한 경우 `kubectl get svc SERVICENAME -o yaml > service.yaml`를 사용 하 여 선언적 매니페스트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-175">If you've already configured your cluster using imperative commands, you can export a declarative manifest by using `kubectl get svc SERVICENAME -o yaml > service.yaml`.</span></span> <span data-ttu-id="b41ab-176">이렇게 하면 다음과 같은 매니페스트 파일이 생성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-176">This will produce a manifest file like this one:</span></span>

```yaml
apiVersion: v1
kind: Service
metadata:
  creationTimestamp: "2019-09-13T13:58:47Z"
  labels:
    component: apiserver
    provider: kubernetes
  name: kubernetes
  namespace: default
  resourceVersion: "153"
  selfLink: /api/v1/namespaces/default/services/kubernetes
  uid: 9b1fac62-d62e-11e9-8968-00155d38010d
spec:
  clusterIP: 10.96.0.1
  ports:
  - name: https
    port: 443
    protocol: TCP
    targetPort: 6443
  sessionAffinity: None
  type: ClusterIP
status:
  loadBalancer: {}
```

<span data-ttu-id="b41ab-177">선언적 구성을 사용 하는 경우 구성 파일이 있는 폴더에 대 한 `kubectl diff -f FOLDERNAME`를 사용 하 여 커밋하기 전에 적용 되는 변경 내용을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-177">When using declarative configuration, you can preview the changes that will be made before committing them by using `kubectl diff -f FOLDERNAME` against the folder where your configuration files are located.</span></span> <span data-ttu-id="b41ab-178">변경 내용을 적용 하려면 `kubectl apply -f FOLDERNAME`를 실행 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-178">Once you're sure you want to apply the changes, run `kubectl apply -f FOLDERNAME`.</span></span> <span data-ttu-id="b41ab-179">폴더 계층 구조를 재귀적으로 처리 하 `-R`를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-179">Add `-R` to recursively process a folder hierarchy.</span></span>

<span data-ttu-id="b41ab-180">서비스 외에도 *배포*와 같은 다른 Kubernetes 기능에 대해 선언적 구성을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-180">In addition to services, you can use declarative configuration for other Kubernetes features, such as *deployments*.</span></span> <span data-ttu-id="b41ab-181">선언적 배포는 배포 컨트롤러에서 클러스터 리소스를 업데이트 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-181">Declarative deployments are used by deployment controllers to update cluster resources.</span></span> <span data-ttu-id="b41ab-182">배포는 새 변경 내용을 롤아웃 하거나, 추가 로드를 지원 하도록 확장 하거나, 이전 수정 버전으로 롤백하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-182">Deployments are used to roll out new changes, scale up to support more load, or roll back to a previous revision.</span></span> <span data-ttu-id="b41ab-183">클러스터가 불안정 한 경우 선언적 배포는 클러스터를 자동으로 원하는 상태로 전환 하는 메커니즘을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-183">If a cluster is unstable, declarative deployments provide a mechanism for automatically bringing the cluster back to a desired state.</span></span>

<span data-ttu-id="b41ab-184">선언적 구성을 사용 하면 응용 프로그램 코드와 함께 체크 인하고 버전을 지정할 수 있는 코드로 인프라를 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-184">Using declarative configuration allows infrastructure to be represented as code that can be checked in and versioned alongside the application code.</span></span> <span data-ttu-id="b41ab-185">이를 통해 소스 제어 변경에 연결 된 빌드 및 배포 파이프라인을 사용 하 여 향상 된 변경 제어 및 연속 배포에 대 한 지원이 향상 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-185">This provides improved change control and better support for continuous deployment using a build and deploy pipeline tied to source control changes.</span></span>

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a><span data-ttu-id="b41ab-186">컨테이너 및 orchestrator에 적합 한 시나리오는 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="b41ab-186">What scenarios are ideal for containers and orchestrators?</span></span>

<span data-ttu-id="b41ab-187">다음 시나리오는 컨테이너 및 orchestrator를 사용 하는 데 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-187">The following scenarios are ideal for using containers and orchestrators.</span></span>

### <a name="applications-requiring-high-uptime-and-scalability"></a><span data-ttu-id="b41ab-188">높은 작동 시간 및 확장성을 필요로 하는 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b41ab-188">Applications requiring high uptime and scalability</span></span>

<span data-ttu-id="b41ab-189">가동 시간 및 확장성 요구 사항이 높은 개별 응용 프로그램은 마이크로 서비스, 컨테이너 및 orchestrator를 사용 하는 클라우드 기본 아키텍처에 적합 한 후보입니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-189">Individual applications that have high uptime and scalability requirements are ideal candidates for cloud-native architectures using microservices, containers, and orchestrators.</span></span> <span data-ttu-id="b41ab-190">이러한 응용 프로그램은 버전이 지정 된 환경을 사용 하 여 컨테이너에서 개발할 수 있으며, 프로덕션으로 이동 하기 전에 광범위 하 게 테스트할 수 있으며 가동 중지 시간이 0 인 프로덕션에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-190">These applications can be developed in containers using versioned environments, can be extensively tested before going to production, and can be deployed to production with zero downtime.</span></span> <span data-ttu-id="b41ab-191">Kubernetes 클러스터를 사용 하면 이러한 앱이 주문형으로 확장 되 고 노드 오류에서 자동으로 복구 될 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-191">The use of Kubernetes clusters ensures such apps can also scale on demand and recover automatically from node failures.</span></span>

### <a name="large-numbers-of-applications"></a><span data-ttu-id="b41ab-192">많은 수의 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="b41ab-192">Large numbers of applications</span></span>

<span data-ttu-id="b41ab-193">이후에 배포 하 고 많은 수의 응용 프로그램을 유지 관리 해야 하는 조직은 컨테이너 및 orchestrator의 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-193">Organizations that deploy and must subsequently maintain large numbers of applications benefit from containers and orchestrators.</span></span> <span data-ttu-id="b41ab-194">컨테이너 화 된 환경 및 Kubernetes 클러스터를 설정 하는 앞의 노력은 고정 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-194">The up front effort of setting up containerized environments and Kubernetes clusters is primarily a fixed cost.</span></span> <span data-ttu-id="b41ab-195">개별 응용 프로그램을 배포, 유지 관리 및 업데이트 하면 유지 관리 해야 하는 응용 프로그램의 수에 따라 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-195">Deploying, maintaining, and updating individual applications has a cost that varies with the number of applications that must be maintained.</span></span> <span data-ttu-id="b41ab-196">매우 적은 수의 응용 프로그램을 사용 하면 사용자 지정 응용 프로그램을 수동으로 유지 관리 하는 복잡성이 컨테이너 및 orchestrator를 사용 하 여 솔루션을 구현 하는 비용을 초과할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-196">Beyond a certain fairly small number of applications, the complexity of maintaining custom applications manually exceeds the cost of implementing a solution using containers and orchestrators.</span></span>

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a><span data-ttu-id="b41ab-197">컨테이너와 orchestrator를 사용 하지 않는 경우는 언제 인가요?</span><span class="sxs-lookup"><span data-stu-id="b41ab-197">When should you avoid using containers and orchestrators?</span></span>

<span data-ttu-id="b41ab-198">12 단계 앱 원칙에 따라 응용 프로그램을 빌드할 수 없는 경우 또는 컨테이너와 orchestrator을 방지 하는 것이 더 좋을 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-198">If you're unwilling or unable to build your application following Twelve-Factor App principles, you'll probably be better off avoiding containers and orchestrators.</span></span> <span data-ttu-id="b41ab-199">이러한 경우 VM 기반 호스팅 플랫폼과 함께 이동 하는 것이 가장 좋을 수 있습니다. 또는 특정 기능을 별도의 컨테이너 또는 서버를 사용 하지 않는 함수로 회전할 수 있는 하이브리드 시스템이 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-199">In these cases, it may be best to move forward with a VM-based hosting platform, or possibly some hybrid system in which you can spin off certain pieces of functionality into separate containers or even serverless functions.</span></span>

## <a name="development-resources"></a><span data-ttu-id="b41ab-200">개발 리소스</span><span class="sxs-lookup"><span data-stu-id="b41ab-200">Development resources</span></span>

<span data-ttu-id="b41ab-201">이 섹션에서는 다음 응용 프로그램에 컨테이너 및 orchestrator 사용을 시작 하는 데 도움이 될 수 있는 간단한 개발 리소스 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-201">This section shows a short list of development resources that may help you get started using containers and orchestrators for your next application.</span></span> <span data-ttu-id="b41ab-202">클라우드 네이티브 마이크로 서비스 아키텍처 앱을 설계 하는 방법에 대 한 지침은이 설명서의 [.Net 마이크로 서비스: 컨테이너 화 된 .Net 응용 프로그램용 아키텍처](https://aka.ms/microservicesebook)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b41ab-202">If you're looking for guidance on how to design your cloud-native microservices architecture app, read this book's companion, [.NET Microservices: Architecture for Containerized .NET Applications](https://aka.ms/microservicesebook).</span></span>

### <a name="local-kubernetes-development"></a><span data-ttu-id="b41ab-203">로컬 Kubernetes 개발</span><span class="sxs-lookup"><span data-stu-id="b41ab-203">Local Kubernetes Development</span></span>

<span data-ttu-id="b41ab-204">Kubernetes 배포는 프로덕션 환경에서 뛰어난 가치를 제공 하지만 로컬에서 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-204">Kubernetes deployments provide great value in production environments, but you can also run them locally.</span></span> <span data-ttu-id="b41ab-205">개별 앱 또는 마이크로 서비스에서 독립적으로 작업 하는 데는 많은 시간이 걸릴 수 있지만 프로덕션 환경에 배포할 때 실행 되는 것 처럼 전체 시스템을 로컬로 실행할 수 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-205">Although much of the time it's good to be able to work on individual apps or microservices independently, sometimes it's good to be able to run the whole system locally just as it will run when deployed to production.</span></span> <span data-ttu-id="b41ab-206">이를 위해 여러 가지 방법을 사용할 수 있으며,이 중 두 가지는 Minikube 및 Docker Desktop입니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-206">There are several ways to achieve this, two of which are Minikube and Docker Desktop.</span></span> <span data-ttu-id="b41ab-207">또한 Visual Studio는 Docker 개발용 도구를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-207">Visual Studio also provides tooling for Docker development.</span></span>

### <a name="minikube"></a><span data-ttu-id="b41ab-208">Minikube</span><span class="sxs-lookup"><span data-stu-id="b41ab-208">Minikube</span></span>

<span data-ttu-id="b41ab-209">Minikube 란?</span><span class="sxs-lookup"><span data-stu-id="b41ab-209">What is Minikube?</span></span> <span data-ttu-id="b41ab-210">Minikube 프로젝트에서는 "Minikube가 macOS, Linux 및 Windows에서 로컬 Kubernetes 클러스터를 구현 합니다." 라고 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-210">The Minikube project says "Minikube implements a local Kubernetes cluster on macOS, Linux, and Windows."</span></span> <span data-ttu-id="b41ab-211">주요 목표는 "로컬 Kubernetes 응용 프로그램 개발에 가장 적합 한 도구 이며이에 적합 한 모든 Kubernetes 기능을 지 원하는 것입니다."</span><span class="sxs-lookup"><span data-stu-id="b41ab-211">Its primary goals are "to be the best tool for local Kubernetes application development and to support all Kubernetes features that fit."</span></span> <span data-ttu-id="b41ab-212">Minikube 설치는 Docker와는 별개 이지만 Minikube는 Docker 데스크톱과 지원 되는 것과 다른 하이퍼바이저를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-212">Installing Minikube is separate from Docker, but Minikube supports different hypervisors than Docker Desktop supports.</span></span> <span data-ttu-id="b41ab-213">Minikube에서 현재 지원 되는 Kubernetes 기능은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-213">The following Kubernetes features are currently supported by Minikube:</span></span>

- <span data-ttu-id="b41ab-214">DNS</span><span class="sxs-lookup"><span data-stu-id="b41ab-214">DNS</span></span>
- <span data-ttu-id="b41ab-215">NodePorts</span><span class="sxs-lookup"><span data-stu-id="b41ab-215">NodePorts</span></span>
- <span data-ttu-id="b41ab-216">ConfigMaps 및 비밀</span><span class="sxs-lookup"><span data-stu-id="b41ab-216">ConfigMaps and secrets</span></span>
- <span data-ttu-id="b41ab-217">대시보드</span><span class="sxs-lookup"><span data-stu-id="b41ab-217">Dashboards</span></span>
- <span data-ttu-id="b41ab-218">컨테이너 런타임: Docker, rkt, CRI 및 containerd</span><span class="sxs-lookup"><span data-stu-id="b41ab-218">Container runtimes: Docker, rkt, CRI-O, and containerd</span></span>
- <span data-ttu-id="b41ab-219">CNI (컨테이너 네트워크 인터페이스)를 사용 하도록 설정</span><span class="sxs-lookup"><span data-stu-id="b41ab-219">Enabling Container Network Interface (CNI)</span></span>
- <span data-ttu-id="b41ab-220">수신</span><span class="sxs-lookup"><span data-stu-id="b41ab-220">Ingress</span></span>

<span data-ttu-id="b41ab-221">Minikube를 설치한 후 이미지를 다운로드 하 고 로컬 Kubernetes 클러스터를 시작 하는 `minikube start` 명령을 실행 하 여 신속 하 게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-221">After installing Minikube, you can quickly start using it by running the `minikube start` command, which downloads an image and start the local Kubernetes cluster.</span></span> <span data-ttu-id="b41ab-222">클러스터가 시작 되 면 표준 Kubernetes `kubectl` 명령을 사용 하 여 상호 작용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-222">Once the cluster is started, you interact with it using the standard Kubernetes `kubectl` commands.</span></span>

### <a name="docker-desktop"></a><span data-ttu-id="b41ab-223">Docker 데스크톱</span><span class="sxs-lookup"><span data-stu-id="b41ab-223">Docker Desktop</span></span>

<span data-ttu-id="b41ab-224">Windows의 Docker Desktop에서 직접 Kubernetes 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-224">You can also work with Kubernetes directly from Docker Desktop on Windows.</span></span> <span data-ttu-id="b41ab-225">이 옵션은 Windows 컨테이너를 사용 하는 경우에만 사용할 수 있으며 비 Windows 컨테이너에도 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-225">This is your only option if you're using Windows Containers, and is a great choice for non-Windows containers as well.</span></span> <span data-ttu-id="b41ab-226">표준 Docker 데스크톱 구성 앱은 Docker 데스크톱에서 실행 되는 Kubernetes를 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-226">The standard Docker Desktop configuration app is used to configure Kubernetes running from Docker Desktop.</span></span>

![Docker Desktop에서 Kubernetes 구성](./media/docker-desktop-kubernetes.png)

<span data-ttu-id="b41ab-228">**그림 3-4**.</span><span class="sxs-lookup"><span data-stu-id="b41ab-228">**Figure 3-4**.</span></span> <span data-ttu-id="b41ab-229">Docker Desktop에서 Kubernetes를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-229">Configuring Kubernetes in Docker Desktop.</span></span>

<span data-ttu-id="b41ab-230">Docker Desktop은 이미 컨테이너 화 된 apps를 로컬로 구성 하 고 실행 하기 위한 가장 인기 있는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-230">Docker Desktop is already the most popular tool for configuring and running containerized apps locally.</span></span> <span data-ttu-id="b41ab-231">Docker Desktop을 사용 하는 경우 프로덕션 환경에 배포할 정확한 Docker 컨테이너 이미지 집합에 대해 로컬로 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-231">When you work with Docker Desktop, you can develop locally against the exact same set of Docker container images that you'll deploy to production.</span></span> <span data-ttu-id="b41ab-232">Docker Desktop은 컨테이너 화 된 apps를 로컬로 빌드, 테스트 및 제공 하도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-232">Docker Desktop is designed to "build, test, and ship" containerized apps locally.</span></span> <span data-ttu-id="b41ab-233">이미지가 Azure Container Registry 또는 Docker Hub와 같은 이미지 레지스트리로 배송 된 후 AKS (Azure Kubernetes Service)와 같은 서비스는 프로덕션에서 응용 프로그램을 관리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-233">Once the images have been shipped to an image registry like Azure Container Registry or Docker Hub, then services like Azure Kubernetes Service (AKS) manage the application in production.</span></span>

### <a name="visual-studio-docker-tooling"></a><span data-ttu-id="b41ab-234">Visual Studio Docker 도구</span><span class="sxs-lookup"><span data-stu-id="b41ab-234">Visual Studio Docker Tooling</span></span>

<span data-ttu-id="b41ab-235">Visual Studio는 웹 응용 프로그램에 대 한 Docker 개발을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-235">Visual Studio supports Docker development for web applications.</span></span> <span data-ttu-id="b41ab-236">새 ASP.NET Core 응용 프로그램을 만드는 경우 그림 3-5에 표시 된 것 처럼 프로젝트 만들기 프로세스의 일부로 Docker 지원을 사용 하 여이 응용 프로그램을 구성 하는 옵션이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-236">When you create a new ASP.NET Core application, you're given the option to configure it with Docker support as part of the project creation process, as shown in Figure 3-5.</span></span>

![Visual Studio에서 Docker 지원 사용](./media/visual-studio-enable-docker-support.png)

<span data-ttu-id="b41ab-238">**그림 3-5**.</span><span class="sxs-lookup"><span data-stu-id="b41ab-238">**Figure 3-5**.</span></span> <span data-ttu-id="b41ab-239">Visual Studio에서 Docker 지원 사용</span><span class="sxs-lookup"><span data-stu-id="b41ab-239">Visual Studio Enable Docker Support</span></span>

<span data-ttu-id="b41ab-240">이 옵션을 선택 하면 프로젝트는 Docker 컨테이너에서 앱을 빌드하고 호스트 하는 데 사용할 수 있는 루트에 `Dockerfile`를 사용 하 여 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-240">When this option is selected, the project is created with a `Dockerfile` in its root, which can be used to build and host the app in a Docker container.</span></span> <span data-ttu-id="b41ab-241">예제 Dockerfile은 그림 3-6에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-241">An example Dockerfile is shown in Figure 3-6.</span></span>

```docker
FROM mcr.microsoft.com/dotnet/core/aspnet:3.0-stretch-slim AS base
WORKDIR /app
EXPOSE 80
EXPOSE 443

FROM mcr.microsoft.com/dotnet/core/sdk:3.0-stretch AS build
WORKDIR /src
COPY ["WebApplication3/WebApplication3.csproj", "WebApplication3/"]
RUN dotnet restore "WebApplication3/WebApplication3.csproj"
COPY . .
WORKDIR "/src/WebApplication3"
RUN dotnet build "WebApplication3.csproj" -c Release -o /app

FROM build AS publish
RUN dotnet publish "WebApplication3.csproj" -c Release -o /app

FROM base AS final
WORKDIR /app
COPY --from=publish /app .
ENTRYPOINT ["dotnet", "WebApplication3.dll"]
```

<span data-ttu-id="b41ab-242">**그림 3-6**.</span><span class="sxs-lookup"><span data-stu-id="b41ab-242">**Figure 3-6**.</span></span> <span data-ttu-id="b41ab-243">Visual Studio에서 Dockerfile을 생성 했습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-243">Visual Studio generated Dockerfile</span></span>

<span data-ttu-id="b41ab-244">앱이 실행 되는 기본 동작은 Docker도 사용 하도록 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-244">The default behavior when the app runs is configured to use Docker as well.</span></span> <span data-ttu-id="b41ab-245">그림 3-7에서는 Docker 지원을 추가 하 여 만든 새 ASP.NET Core 프로젝트에서 사용할 수 있는 다양 한 실행 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-245">Figure 3-7 shows the different run options available from a new ASP.NET Core project created with Docker support added.</span></span>

![Visual Studio Docker 실행 옵션](./media/visual-studio-docker-run-options.png)

<span data-ttu-id="b41ab-247">**그림 3-7**.</span><span class="sxs-lookup"><span data-stu-id="b41ab-247">**Figure 3-7**.</span></span> <span data-ttu-id="b41ab-248">Visual Studio Docker 실행 옵션</span><span class="sxs-lookup"><span data-stu-id="b41ab-248">Visual Studio Docker Run Options</span></span>

<span data-ttu-id="b41ab-249">로컬 개발 외에도 [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) 는 여러 개발자가 Azure 내에서 고유한 Kubernetes 구성으로 작업할 수 있는 편리한 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-249">In addition to local development, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) provides a convenient way for multiple developers to work with their own Kubernetes configurations within Azure.</span></span> <span data-ttu-id="b41ab-250">그림 3-7에서 볼 수 있듯이, Azure Dev Spaces에서 응용 프로그램을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-250">As you can see in Figure 3-7, you can also run the application in Azure Dev Spaces.</span></span>

<span data-ttu-id="b41ab-251">ASP.NET Core 응용 프로그램을 만들 때 Docker 지원을 추가 하지 않으면 나중에 언제 든 지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-251">If you don't add Docker support to your ASP.NET Core application when you create it, you can always add it later.</span></span> <span data-ttu-id="b41ab-252">그림 3-8에 표시 된 것 처럼 Visual Studio 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **추가** > **Docker 지원**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-252">From the Visual Studio Solution Explorer, right click on the project and select **Add** > **Docker Support**, as shown in Figure 3-8.</span></span>

![Visual Studio Docker 지원 추가](./media/visual-studio-add-docker-support.png)

<span data-ttu-id="b41ab-254">**그림 3-8**.</span><span class="sxs-lookup"><span data-stu-id="b41ab-254">**Figure 3-8**.</span></span> <span data-ttu-id="b41ab-255">Visual Studio Docker 지원 추가</span><span class="sxs-lookup"><span data-stu-id="b41ab-255">Visual Studio Add Docker Support</span></span>

<span data-ttu-id="b41ab-256">Docker 지원 외에도 그림 3-8에 표시 된 컨테이너 오케스트레이션 지원을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-256">In addition to Docker support, you can also add Container Orchestration Support, also shown in Figure 3-8.</span></span> <span data-ttu-id="b41ab-257">기본적으로 orchestrator는 Kubernetes 및 투구를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-257">By default, the orchestrator uses Kubernetes and Helm.</span></span> <span data-ttu-id="b41ab-258">Orchestrator를 선택 하면 `azds.yaml` 파일이 프로젝트 루트에 추가 되 고 Kubernetes에 응용 프로그램을 구성 하 고 배포 하는 데 사용 되는 투구 차트가 포함 된 `charts` 폴더가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-258">Once you've chosen the orchestrator, a `azds.yaml` file is added to the project root and a `charts` folder is added containing the Helm charts used to configure and deploy the application to Kubernetes.</span></span> <span data-ttu-id="b41ab-259">그림 3-9에서는 새 프로젝트의 결과 파일을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b41ab-259">Figure 3-9 shows the resulting files in a new project.</span></span>

![Visual Studio Orchestrator 지원 추가](./media/visual-studio-add-orchestrator-support.png)

<span data-ttu-id="b41ab-261">**그림 3-9**.</span><span class="sxs-lookup"><span data-stu-id="b41ab-261">**Figure 3-9**.</span></span> <span data-ttu-id="b41ab-262">Visual Studio Orchestrator 지원 추가</span><span class="sxs-lookup"><span data-stu-id="b41ab-262">Visual Studio Add Orchestrator Support</span></span>

## <a name="references"></a><span data-ttu-id="b41ab-263">참조</span><span class="sxs-lookup"><span data-stu-id="b41ab-263">References</span></span>

- [<span data-ttu-id="b41ab-264">Kubernetes 란?</span><span class="sxs-lookup"><span data-stu-id="b41ab-264">What is Kubernetes?</span></span>](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [<span data-ttu-id="b41ab-265">Minikube를 사용 하 여 Kubernetes 설치</span><span class="sxs-lookup"><span data-stu-id="b41ab-265">Installing Kubernetes with Minikube</span></span>](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [<span data-ttu-id="b41ab-266">MiniKube vs Docker Desktop</span><span class="sxs-lookup"><span data-stu-id="b41ab-266">MiniKube vs Docker Desktop</span></span>](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [<span data-ttu-id="b41ab-267">Docker용 Visual Studio Tools</span><span class="sxs-lookup"><span data-stu-id="b41ab-267">Visual Studio Tools for Docker</span></span>](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
><span data-ttu-id="b41ab-268">[이전](scale-applications.md)
>[다음](leverage-serverless-functions.md)</span><span class="sxs-lookup"><span data-stu-id="b41ab-268">[Previous](scale-applications.md)
[Next](leverage-serverless-functions.md)</span></span>
