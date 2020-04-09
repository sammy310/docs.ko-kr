---
title: 컨테이너 및 오케스트레이터 활용
description: Azure에서 Docker 컨테이너 및 Kubernetes 오케스트레이터 활용
ms.date: 06/30/2019
ms.openlocfilehash: 44b2fff8c9c88717d83e41a421b9817e2cc68135
ms.sourcegitcommit: e3cbf26d67f7e9286c7108a2752804050762d02d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/09/2020
ms.locfileid: "80989040"
---
# <a name="leveraging-containers-and-orchestrators"></a><span data-ttu-id="bc34f-103">컨테이너 및 오케스트레이터 활용</span><span class="sxs-lookup"><span data-stu-id="bc34f-103">Leveraging containers and orchestrators</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="bc34f-104">컨테이너 및 오케스트레이터는 모놀리식 배포 방식에 공통적인 문제를 해결하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-104">Containers and orchestrators are designed to solve problems common to monolithic deployment approaches.</span></span>

## <a name="challenges-with-monolithic-deployments"></a><span data-ttu-id="bc34f-105">모놀리식 배포의 과제</span><span class="sxs-lookup"><span data-stu-id="bc34f-105">Challenges with monolithic deployments</span></span>

<span data-ttu-id="bc34f-106">일반적으로 대부분의 응용 프로그램은 단일 단위로 배포되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-106">Traditionally, most applications have been deployed as a single unit.</span></span> <span data-ttu-id="bc34f-107">이러한 응용 프로그램을 모놀리스라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-107">Such applications are referred to as a monolith.</span></span> <span data-ttu-id="bc34f-108">그림 3-1과 같이 여러 모듈이나 어셈블리로 구성된 경우에도 응용 프로그램을 단일 단위로 배포하는 일반적인 방법을 모놀리식 아키텍처라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-108">This general approach of deploying applications as single units even if they're composed of multiple modules or assemblies is known as monolithic architecture, as shown in Figure 3-1.</span></span>

![모놀리식 아키텍처입니다.](./media/monolithic-architecture.png)

<span data-ttu-id="bc34f-110">**그림 3-1**.</span><span class="sxs-lookup"><span data-stu-id="bc34f-110">**Figure 3-1**.</span></span> <span data-ttu-id="bc34f-111">모놀리식 아키텍처입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-111">Monolithic architecture.</span></span>

<span data-ttu-id="bc34f-112">단순함의 이점이 있지만 모놀리식 아키텍처는 다음과 같은 여러 가지 과제에 직면해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-112">Although they have the benefit of simplicity, monolithic architectures face a number of challenges:</span></span>

### <a name="deployments"></a><span data-ttu-id="bc34f-113">배포</span><span class="sxs-lookup"><span data-stu-id="bc34f-113">Deployments</span></span>

<span data-ttu-id="bc34f-114">모놀리식 응용 프로그램에 배포하려면 일반적으로 하나의 작은 모듈만 교체되더라도 전체 응용 프로그램을 다시 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-114">Deploying to monolithic applications typically requires restarting the entire application, even if only one small module is being replaced.</span></span> <span data-ttu-id="bc34f-115">응용 프로그램을 호스팅하는 컴퓨터 수에 따라 배포 중에 가동 중지 시간이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-115">Depending on the number of machines hosting the application, this can result in downtime during deployments.</span></span>

### <a name="hosting"></a><span data-ttu-id="bc34f-116">Hosting</span><span class="sxs-lookup"><span data-stu-id="bc34f-116">Hosting</span></span>

<span data-ttu-id="bc34f-117">모놀리식 응용 프로그램은 전적으로 단일 컴퓨터 인스턴스에서 호스팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-117">Monolithic applications are hosted entirely on a single machine instance.</span></span> <span data-ttu-id="bc34f-118">이렇게 하려면 분산 응용 프로그램의 모든 모듈보다 더 높은 용량의 하드웨어가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-118">This may require higher-capability hardware than any module in a distributed application would need.</span></span> <span data-ttu-id="bc34f-119">또한 앱의 일부가 병목 현상이 발생하면 확장하려면 전체 응용 프로그램을 추가 컴퓨터 노드에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-119">Also, if any part of the app becomes a bottleneck, the entire application must be deployed to additional machine nodes in order to scale out.</span></span>

### <a name="environment"></a><span data-ttu-id="bc34f-120">Environment</span><span class="sxs-lookup"><span data-stu-id="bc34f-120">Environment</span></span>

<span data-ttu-id="bc34f-121">모놀리식 응용 프로그램은 일반적으로 기존 호스팅 환경(운영 체제, 설치된 프레임워크 등)에 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-121">Monolithic applications are typically deployed into an existing hosting environment (operating system, installed frameworks, etc.).</span></span> <span data-ttu-id="bc34f-122">이 환경은 응용 프로그램이 개발되거나 테스트된 환경과 일치하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-122">This environment may not match the environment in which the application was developed or tested.</span></span> <span data-ttu-id="bc34f-123">응용 프로그램 환경의 불일치는 모놀리식 배포에 대한 일반적인 문제의 원인입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-123">Inconsistencies in the application's environment are a common source of problems for monolithic deployments.</span></span>

### <a name="coupling"></a><span data-ttu-id="bc34f-124">커플링</span><span class="sxs-lookup"><span data-stu-id="bc34f-124">Coupling</span></span>

<span data-ttu-id="bc34f-125">모놀리식 응용 프로그램은 응용 프로그램의 다른 부분과 응용 프로그램과 해당 환경 간에 많은 커플링을 가질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-125">Monolithic applications are likely to have a great deal of coupling between different parts of the application, and between the application and its environment.</span></span> <span data-ttu-id="bc34f-126">따라서 확장성을 높이거나 대체 구현에서 스왑을 하기 위해 나중에 특정 서비스 나 우려 사항을 고려하기가 어려울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-126">This can make it difficult to factor out a particular service or concern later, in order to increase its scalability or swap in an alternative implementation.</span></span> <span data-ttu-id="bc34f-127">또한 이러한 결합은 시스템 변경에 대한 잠재적 영향을 훨씬 더 크게 유발하므로 대규모 응용 프로그램에서 광범위한 테스트를 받아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-127">This coupling also leads to much larger potential impacts for changes to the system, requiring extensive testing in larger applications.</span></span>

### <a name="technology-choice"></a><span data-ttu-id="bc34f-128">기술 선택</span><span class="sxs-lookup"><span data-stu-id="bc34f-128">Technology choice</span></span>

<span data-ttu-id="bc34f-129">모놀리식 응용 프로그램은 단위로 빌드되고 배포됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-129">Monolithic applications are built and deployed as a unit.</span></span> <span data-ttu-id="bc34f-130">이는 단순성과 균일성을 제공하지만 혁신의 장벽이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-130">This offers simplicity and uniformity but can be a barrier to innovation.</span></span> <span data-ttu-id="bc34f-131">시스템의 새로운 기능이나 모듈이 보다 현대적인 플랫폼이나 프레임워크에 더 적합할 수 있지만 일관성과 개발 및 배포의 용이성을 위해 응용 프로그램의 현재 접근 방식을 사용하여 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-131">Although a new feature or module in the system might be better-suited to a more modern platform or framework, it's likely to be built using the application's current approach for the sake of consistency as well as ease of development and deployment.</span></span>

## <a name="what-are-the-benefits-of-containers-and-orchestrators"></a><span data-ttu-id="bc34f-132">컨테이너 및 오케스트레이터의 이점은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bc34f-132">What are the benefits of containers and orchestrators?</span></span>

<span data-ttu-id="bc34f-133">Docker는 가장 인기 있는 컨테이너 관리 및 이미징 플랫폼이며 Linux 및 Windows에서 컨테이너로 빠르게 작업할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-133">Docker is the most popular container management and imaging platform and allows you to quickly work with containers on Linux and Windows.</span></span> <span data-ttu-id="bc34f-134">컨테이너는 모든 시스템에서 동일한 방식으로 실행되는 별도의 재현 가능한 응용 프로그램 환경을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-134">Containers provide separate but reproducible application environments that run the same way on any system.</span></span> <span data-ttu-id="bc34f-135">따라서 클라우드 네이티브 응용 프로그램에서 응용 프로그램 및 앱 구성 요소를 개발하고 호스팅하는 데 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-135">This makes them perfect for developing and hosting applications and app components in cloud-native applications.</span></span> <span data-ttu-id="bc34f-136">컨테이너는 서로 격리되므로 동일한 호스트 하드웨어에 있는 두 개의 컨테이너는 충돌을 유발하는 종속성 없이 서로 다른 버전의 소프트웨어와 운영 체제를 설치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-136">Containers are isolated from one another, so two containers on the same host hardware can have different versions of software and even operating system installed, without the dependencies causing conflicts.</span></span>

<span data-ttu-id="bc34f-137">또한 컨테이너는 소스 제어에 체크 인할 수 있는 간단한 파일로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-137">What's more, containers are defined by simple files that can be checked into source control.</span></span> <span data-ttu-id="bc34f-138">전체 서버와 달리 업데이트를 적용하거나 추가 서비스를 설치하기 위해 수동 작업이 자주 필요한 가상 시스템도 컨테이너 인프라를 쉽게 버전 제어할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-138">Unlike full servers, even virtual machines, which frequently require manual work to apply updates or install additional services, container infrastructure can easily be version-controlled.</span></span> <span data-ttu-id="bc34f-139">따라서 컨테이너에서 실행되도록 빌드된 앱을 빌드 파이프라인의 일부로 자동화된 도구를 사용하여 개발, 테스트 및 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-139">Thus, apps built to run in containers can be developed, tested, and deployed using automated tools as part of a build pipeline.</span></span>

<span data-ttu-id="bc34f-140">컨테이너는 변경할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-140">Containers are immutable.</span></span> <span data-ttu-id="bc34f-141">컨테이너의 정의가 있으면 해당 컨테이너를 다시 만들 수 있으며 동일한 방식으로 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-141">Once you have the definition of a container, you can recreate that container and it will run exactly the same way.</span></span> <span data-ttu-id="bc34f-142">이 불변성은 구성 요소 기반 설계에 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-142">This immutability lends itself to component-based design.</span></span> <span data-ttu-id="bc34f-143">응용 프로그램의 일부가 다른 부분만큼 자주 변경되지 않는 경우 가장 자주 변경되는 부분을 배포할 수 있을 때 전체 앱을 다시 배포해야 하는 이유는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bc34f-143">If some parts of an application don't change as often as others, why redeploy the entire app when you can just deploy the parts that change most frequently?</span></span> <span data-ttu-id="bc34f-144">앱의 다양한 기능과 교차 절단 문제는 별도의 단위로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-144">Different features and cross-cutting concerns of an app can be broken up into separate units.</span></span> <span data-ttu-id="bc34f-145">그림 3-2는 모놀리식 앱이 특정 기능 이나 기능을 위임 하여 컨테이너 및 마이크로 서비스를 활용할 수 있는 방법을 보여 주다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-145">Figure 3-2 shows how a monolithic app can take advantage of containers and microservices by delegating certain features or functionality.</span></span> <span data-ttu-id="bc34f-146">앱 자체의 나머지 기능도 컨테이너화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-146">The remaining functionality in the app itself has also been containerized.</span></span>

<span data-ttu-id="bc34f-147">![백 엔드에서 마이크로 서비스를 사용하는 모놀리식 응용 프로그램을 분리합니다. ](./media/breaking-up-monolith-with-backend-microservices.png)
 **그림 3-2**.</span><span class="sxs-lookup"><span data-stu-id="bc34f-147">![Breaking up a monolithic app to use microservices in the back end.](./media/breaking-up-monolith-with-backend-microservices.png)
**Figure 3-2**.</span></span> <span data-ttu-id="bc34f-148">백 엔드에서 마이크로 서비스를 사용하는 모놀리식 응용 프로그램을 분리합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-148">Breaking up a monolithic app to use microservices in the back end.</span></span>

<span data-ttu-id="bc34f-149">별도의 컨테이너를 사용하여 빌드된 클라우드 네이티브 앱은 필요에 따라 응용 프로그램을 최대한 또는 적게 배포할 수 있는 이점을 누릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-149">Cloud-native apps built using separate containers benefit from the ability to deploy as much or as little of an application as needed.</span></span> <span data-ttu-id="bc34f-150">개별 서비스는 각 서비스에 적합한 리소스가 있는 노드에서 호스팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-150">Individual services can be hosted on nodes with resources appropriate to each service.</span></span> <span data-ttu-id="bc34f-151">각 서비스가 실행되는 환경은 변경할 수 없으며 개발, 테스트 및 프로덕션 간에 공유할 수 있으며 쉽게 버전이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-151">The environment each service runs in is immutable, can be shared between dev, test, and production, and can easily be versioned.</span></span> <span data-ttu-id="bc34f-152">응용 프로그램의 다른 영역 간의 결합은 모놀리스 내의 컴파일 타임 종속성이 아니라 서비스 간의 호출 또는 메시지로 명시적으로 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-152">Coupling between different areas of the application occurs explicitly as calls or messages between services, not compile-time dependencies within the monolith.</span></span> <span data-ttu-id="bc34f-153">그리고 전체 앱의 모든 특정 부분은 응용 프로그램의 나머지 부분을 변경하지 않고 해당 기능이나 기능에 가장 적합한 기술을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-153">And any given part of the overall app can choose the technology that makes the most sense for that feature or capability without requiring changes to the rest of the app.</span></span>

## <a name="what-are-the-scaling-benefits"></a><span data-ttu-id="bc34f-154">확장 이점은 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bc34f-154">What are the scaling benefits?</span></span>

<span data-ttu-id="bc34f-155">컨테이너에 구축된 서비스는 Kubernetes와 같은 오케스트레이션 도구에서 제공하는 확장 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-155">Services built on containers can leverage scaling benefits provided by orchestration tools like Kubernetes.</span></span> <span data-ttu-id="bc34f-156">디자인 컨테이너는 자신에 대해서만 알고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-156">By design containers only know about themselves.</span></span> <span data-ttu-id="bc34f-157">함께 작업해야 하는 여러 컨테이너를 갖기 시작하면 더 높은 수준에서 컨테이너를 구성하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-157">Once you start to have multiple containers that need to work together, it can be worthwhile to organize them at a higher level.</span></span> <span data-ttu-id="bc34f-158">많은 수의 컨테이너와 네트워크 구성과 같은 공유 종속성을 구성하는 것은 오케스트레이션 도구가 들어와 하루를 절약하는 곳입니다!</span><span class="sxs-lookup"><span data-stu-id="bc34f-158">Organizing large numbers of containers and their shared dependencies, such as network configuration, is where orchestration tools come in to save the day!</span></span> <span data-ttu-id="bc34f-159">Kubernetes는 컨테이너화된 응용 프로그램의 배포, 크기 조정 및 관리를 자동화하도록 설계된 컨테이너 오케스트레이션 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-159">Kubernetes is a container orchestration platform designed to automate deployment, scaling, and management of containerized applications.</span></span> <span data-ttu-id="bc34f-160">컨테이너 그룹 위에 추상화 레이어를 만들고 *이를 포드로 구성합니다.*</span><span class="sxs-lookup"><span data-stu-id="bc34f-160">It creates an abstraction layer on top of groups of containers and organizes them into *pods*.</span></span> <span data-ttu-id="bc34f-161">포드는 노드라고 하는 작업자 컴퓨터에서 *실행됩니다.*</span><span class="sxs-lookup"><span data-stu-id="bc34f-161">Pods run on worker machines referred to as *nodes*.</span></span> <span data-ttu-id="bc34f-162">전체 구성된 그룹을 *클러스터라고*합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-162">The whole organized group is referred to as a *cluster*.</span></span> <span data-ttu-id="bc34f-163">그림 3-3은 Kubernetes 클러스터의 다양한 구성 요소를 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-163">Figure 3-3 shows the different components of a Kubernetes cluster.</span></span>

<span data-ttu-id="bc34f-164">![Kubernetes 클러스터 구성 요소입니다. ](./media/kubernetes-cluster-components.png)
 **그림 3-3 .**</span><span class="sxs-lookup"><span data-stu-id="bc34f-164">![Kubernetes cluster components.](./media/kubernetes-cluster-components.png)
**Figure 3-3**.</span></span> <span data-ttu-id="bc34f-165">Kubernetes 클러스터 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-165">Kubernetes cluster components.</span></span>

<span data-ttu-id="bc34f-166">Kubernetes는 수요를 충족하기 위해 클러스터를 확장하는 데 대한 기본 지원을 제공했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-166">Kubernetes has built-in support for scaling clusters to meet demand.</span></span> <span data-ttu-id="bc34f-167">컨테이너화된 마이크로 서비스와 결합하여 클라우드 네이티브 애플리케이션에 필요할 때 언제 어디서나 추가 리소스를 통해 수요 급증에 신속하고 효율적으로 대응할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-167">Combined with containerized micro-services, this provides cloud-native applications with the ability to quickly and efficiently respond to spikes in demand with additional resources when and where they're needed.</span></span>

### <a name="declarative-versus-imperative"></a><span data-ttu-id="bc34f-168">선언적 대 명령적</span><span class="sxs-lookup"><span data-stu-id="bc34f-168">Declarative versus imperative</span></span>

<span data-ttu-id="bc34f-169">Kubernetes는 선언적 개체 구성과 명령적 개체 구성을 모두 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-169">Kubernetes supports both declarative and imperative object configuration.</span></span> <span data-ttu-id="bc34f-170">명령적 접근 방식은 Kubernetes에게 각 단계를 수행하는 작업을 알려주는 다양한 명령을 실행하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-170">The imperative approach involves running various commands that tell Kubernetes what to do each step of the way.</span></span> <span data-ttu-id="bc34f-171">이 이미지를 *실행합니다.*</span><span class="sxs-lookup"><span data-stu-id="bc34f-171">*Run* this image.</span></span> <span data-ttu-id="bc34f-172">이 창을 *삭제합니다.*</span><span class="sxs-lookup"><span data-stu-id="bc34f-172">*Delete* this pod.</span></span> <span data-ttu-id="bc34f-173">이 포트를 *노출합니다.*</span><span class="sxs-lookup"><span data-stu-id="bc34f-173">*Expose* this port.</span></span> <span data-ttu-id="bc34f-174">선언적 접근 방식을 사용하면 *수행할 작업을* 수행하는 대신 *원하는 작업을* 설명하는 구성 파일을 사용하고 Kubernetes는 원하는 최종 상태를 달성하기 위해 수행할 작업을 파악합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-174">With the declarative approach, you use a configuration file that describes *what you want* instead of *what to do* and Kubernetes figures out what to do to achieve the desired end state.</span></span> <span data-ttu-id="bc34f-175">명령명령을 사용하여 클러스터를 이미 구성한 경우 을 사용하여 `kubectl get svc SERVICENAME -o yaml > service.yaml`선언적 매니페스트를 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-175">If you've already configured your cluster using imperative commands, you can export a declarative manifest by using `kubectl get svc SERVICENAME -o yaml > service.yaml`.</span></span> <span data-ttu-id="bc34f-176">이렇게 하면 다음과 같은 매니페스트 파일이 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-176">This will produce a manifest file like this one:</span></span>

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

<span data-ttu-id="bc34f-177">선언적 구성을 사용하는 경우 구성 파일이 있는 폴더에 `kubectl diff -f FOLDERNAME` 대해 사용하여 커밋하기 전에 수행할 변경 내용을 미리 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-177">When using declarative configuration, you can preview the changes that will be made before committing them by using `kubectl diff -f FOLDERNAME` against the folder where your configuration files are located.</span></span> <span data-ttu-id="bc34f-178">변경 내용을 적용하려는 경우 을 실행합니다. `kubectl apply -f FOLDERNAME`</span><span class="sxs-lookup"><span data-stu-id="bc34f-178">Once you're sure you want to apply the changes, run `kubectl apply -f FOLDERNAME`.</span></span> <span data-ttu-id="bc34f-179">폴더 `-R` 계층 구조를 재귀적으로 처리하기 위해 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-179">Add `-R` to recursively process a folder hierarchy.</span></span>

<span data-ttu-id="bc34f-180">서비스 외에도 배포와 같은 다른 Kubernetes 기능에 선언적 *구성을*사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-180">In addition to services, you can use declarative configuration for other Kubernetes features, such as *deployments*.</span></span> <span data-ttu-id="bc34f-181">선언적 배포는 배포 컨트롤러에서 클러스터 리소스를 업데이트하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-181">Declarative deployments are used by deployment controllers to update cluster resources.</span></span> <span data-ttu-id="bc34f-182">배포는 새 변경 내용을 롤아웃하거나, 더 많은 부하를 지원하도록 확장하거나, 이전 개정으로 롤백하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-182">Deployments are used to roll out new changes, scale up to support more load, or roll back to a previous revision.</span></span> <span data-ttu-id="bc34f-183">클러스터가 불안정한 경우 선언적 배포는 클러스터를 원하는 상태로 자동으로 되돌리는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-183">If a cluster is unstable, declarative deployments provide a mechanism for automatically bringing the cluster back to a desired state.</span></span>

<span data-ttu-id="bc34f-184">선언적 구성을 사용하면 인프라를 응용 프로그램 코드와 함께 체크 인하고 버전이 지정할 수 있는 코드로 나타낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-184">Using declarative configuration allows infrastructure to be represented as code that can be checked in and versioned alongside the application code.</span></span> <span data-ttu-id="bc34f-185">이렇게 하면 소스 제어 변경에 연결된 빌드 및 배포 파이프라인을 사용하여 변경 제어가 향상되고 지속적인 배포에 대한 지원이 향상됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-185">This provides improved change control and better support for continuous deployment using a build and deploy pipeline tied to source control changes.</span></span>

## <a name="what-scenarios-are-ideal-for-containers-and-orchestrators"></a><span data-ttu-id="bc34f-186">컨테이너 및 오케스트레이터에 적합한 시나리오는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="bc34f-186">What scenarios are ideal for containers and orchestrators?</span></span>

<span data-ttu-id="bc34f-187">다음 시나리오는 컨테이너 및 오케스트레이터를 사용하는 데 이상적입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-187">The following scenarios are ideal for using containers and orchestrators.</span></span>

### <a name="applications-requiring-high-uptime-and-scalability"></a><span data-ttu-id="bc34f-188">높은 가동 시간과 확장성이 필요한 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="bc34f-188">Applications requiring high uptime and scalability</span></span>

<span data-ttu-id="bc34f-189">가동 시간 및 확장성 요구 사항이 높은 개별 응용 프로그램은 마이크로 서비스, 컨테이너 및 오케스트레이터를 사용하는 클라우드 네이티브 아키텍처에 이상적인 후보입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-189">Individual applications that have high uptime and scalability requirements are ideal candidates for cloud-native architectures using microservices, containers, and orchestrators.</span></span> <span data-ttu-id="bc34f-190">이러한 애플리케이션은 버전이 적용된 환경을 사용하는 컨테이너에서 개발할 수 있으며, 프로덕션 환경에 가기 전에 광범위하게 테스트할 수 있으며 가동 중지 시간이 없는 프로덕션 환경에 배포할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-190">These applications can be developed in containers using versioned environments, can be extensively tested before going to production, and can be deployed to production with zero downtime.</span></span> <span data-ttu-id="bc34f-191">Kubernetes 클러스터를 사용하면 이러한 앱이 필요에 따라 확장하고 노드 오류로부터 자동으로 복구할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-191">The use of Kubernetes clusters ensures such apps can also scale on demand and recover automatically from node failures.</span></span>

### <a name="large-numbers-of-applications"></a><span data-ttu-id="bc34f-192">많은 수의 응용 프로그램</span><span class="sxs-lookup"><span data-stu-id="bc34f-192">Large numbers of applications</span></span>

<span data-ttu-id="bc34f-193">배포하고 이후에 많은 수의 응용 프로그램을 유지 관리해야 하는 조직은 컨테이너 및 오케스트레이터의 이점을 활용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-193">Organizations that deploy and must subsequently maintain large numbers of applications benefit from containers and orchestrators.</span></span> <span data-ttu-id="bc34f-194">컨테이너화된 환경과 Kubernetes 클러스터를 설정하는 선행 노력은 주로 고정 된 비용입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-194">The up front effort of setting up containerized environments and Kubernetes clusters is primarily a fixed cost.</span></span> <span data-ttu-id="bc34f-195">개별 응용 프로그램을 배포, 유지 관리 및 업데이트하면 유지 관리해야 하는 응용 프로그램 수에 따라 비용이 달라집니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-195">Deploying, maintaining, and updating individual applications has a cost that varies with the number of applications that must be maintained.</span></span> <span data-ttu-id="bc34f-196">특정 상당히 적은 수의 응용 프로그램을 넘어서는 사용자 지정 응용 프로그램을 수동으로 유지 관리하는 복잡성은 컨테이너 및 오케스트레이터를 사용하여 솔루션을 구현하는 비용을 초과합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-196">Beyond a certain fairly small number of applications, the complexity of maintaining custom applications manually exceeds the cost of implementing a solution using containers and orchestrators.</span></span>

## <a name="when-should-you-avoid-using-containers-and-orchestrators"></a><span data-ttu-id="bc34f-197">컨테이너 및 오케스트레이터사용을 언제 피해야 합니까?</span><span class="sxs-lookup"><span data-stu-id="bc34f-197">When should you avoid using containers and orchestrators?</span></span>

<span data-ttu-id="bc34f-198">12단계 앱 원칙에 따라 응용 프로그램을 빌드할 의사가 없거나 빌드할 수 없는 경우 컨테이너 및 오케스트레이터를 피하는 것이 더 나을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-198">If you're unwilling or unable to build your application following Twelve-Factor App principles, you'll probably be better off avoiding containers and orchestrators.</span></span> <span data-ttu-id="bc34f-199">이러한 경우 VM 기반 호스팅 플랫폼또는 특정 기능을 별도의 컨테이너 또는 서버리스 기능으로 분리할 수 있는 하이브리드 시스템으로 진행하는 것이 가장 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-199">In these cases, it may be best to move forward with a VM-based hosting platform, or possibly some hybrid system in which you can spin off certain pieces of functionality into separate containers or even serverless functions.</span></span>

## <a name="development-resources"></a><span data-ttu-id="bc34f-200">개발 리소스</span><span class="sxs-lookup"><span data-stu-id="bc34f-200">Development resources</span></span>

<span data-ttu-id="bc34f-201">이 섹션에서는 다음 응용 프로그램에 대한 컨테이너 및 오케스트레이터 사용을 시작하는 데 도움이 될 수 있는 개발 리소스의 짧은 목록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-201">This section shows a short list of development resources that may help you get started using containers and orchestrators for your next application.</span></span> <span data-ttu-id="bc34f-202">클라우드 네이티브 마이크로 서비스 아키텍처 앱을 디자인하는 방법에 대한 지침을 찾고 있다면 이 설명서의 동반자인 [.NET 마이크로 서비스: 컨테이너화된 .NET 응용 프로그램에 대한 아키텍처를](https://aka.ms/microservicesebook)읽어보십시오.</span><span class="sxs-lookup"><span data-stu-id="bc34f-202">If you're looking for guidance on how to design your cloud-native microservices architecture app, read this book's companion, [.NET Microservices: Architecture for Containerized .NET Applications](https://aka.ms/microservicesebook).</span></span>

### <a name="local-kubernetes-development"></a><span data-ttu-id="bc34f-203">지역 쿠베르네테스 개발</span><span class="sxs-lookup"><span data-stu-id="bc34f-203">Local Kubernetes Development</span></span>

<span data-ttu-id="bc34f-204">Kubernetes 배포는 프로덕션 환경에서 뛰어난 가치를 제공하지만 로컬에서도 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-204">Kubernetes deployments provide great value in production environments, but you can also run them locally.</span></span> <span data-ttu-id="bc34f-205">대부분의 경우 개별 앱이나 마이크로 서비스에서 독립적으로 작업하는 것이 좋지만 프로덕션에 배포할 때 실행되는 것처럼 전체 시스템을 로컬로 실행할 수 있는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-205">Although much of the time it's good to be able to work on individual apps or microservices independently, sometimes it's good to be able to run the whole system locally just as it will run when deployed to production.</span></span> <span data-ttu-id="bc34f-206">이 작업을 달성 하는 몇 가지 방법이 있습니다., 그 중 두 미니 쿠베와 Docker 데스크톱.</span><span class="sxs-lookup"><span data-stu-id="bc34f-206">There are several ways to achieve this, two of which are Minikube and Docker Desktop.</span></span> <span data-ttu-id="bc34f-207">또한 Visual Studio는 Docker 개발을 위한 툴링도 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-207">Visual Studio also provides tooling for Docker development.</span></span>

### <a name="minikube"></a><span data-ttu-id="bc34f-208">Minikube</span><span class="sxs-lookup"><span data-stu-id="bc34f-208">Minikube</span></span>

<span data-ttu-id="bc34f-209">미니쿠베란?</span><span class="sxs-lookup"><span data-stu-id="bc34f-209">What is Minikube?</span></span> <span data-ttu-id="bc34f-210">미니쿠베 프로젝트는 "미니쿠베는 macOS, 리눅스, 윈도우에서 로컬 Kubernetes 클러스터를 구현한다"고 말합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-210">The Minikube project says "Minikube implements a local Kubernetes cluster on macOS, Linux, and Windows."</span></span> <span data-ttu-id="bc34f-211">주요 목표는 "로컬 Kubernetes 응용 프로그램 개발을 위한 최상의 도구가 되고 적합한 모든 Kubernetes 기능을 지원하는 것"입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-211">Its primary goals are "to be the best tool for local Kubernetes application development and to support all Kubernetes features that fit."</span></span> <span data-ttu-id="bc34f-212">미니쿠베 설치는 Docker와 는 별개이지만, 미니큐브는 Docker 데스크톱이 지원하는 것과 는 다른 하이퍼바이저를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-212">Installing Minikube is separate from Docker, but Minikube supports different hypervisors than Docker Desktop supports.</span></span> <span data-ttu-id="bc34f-213">다음 Kubernetes 기능은 현재 Minikube에서 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-213">The following Kubernetes features are currently supported by Minikube:</span></span>

- <span data-ttu-id="bc34f-214">DNS</span><span class="sxs-lookup"><span data-stu-id="bc34f-214">DNS</span></span>
- <span data-ttu-id="bc34f-215">노드 포트</span><span class="sxs-lookup"><span data-stu-id="bc34f-215">NodePorts</span></span>
- <span data-ttu-id="bc34f-216">구성지도 및 비밀</span><span class="sxs-lookup"><span data-stu-id="bc34f-216">ConfigMaps and secrets</span></span>
- <span data-ttu-id="bc34f-217">대시보드</span><span class="sxs-lookup"><span data-stu-id="bc34f-217">Dashboards</span></span>
- <span data-ttu-id="bc34f-218">컨테이너 런타임: 도커, rkt, CRI-O 및 컨테이너</span><span class="sxs-lookup"><span data-stu-id="bc34f-218">Container runtimes: Docker, rkt, CRI-O, and containerd</span></span>
- <span data-ttu-id="bc34f-219">컨테이너 네트워크 인터페이스(CNI) 사용</span><span class="sxs-lookup"><span data-stu-id="bc34f-219">Enabling Container Network Interface (CNI)</span></span>
- <span data-ttu-id="bc34f-220">수신</span><span class="sxs-lookup"><span data-stu-id="bc34f-220">Ingress</span></span>

<span data-ttu-id="bc34f-221">Minikube를 설치한 후 이미지를 다운로드하고 로컬 `minikube start` Kubernetes 클러스터를 시작하는 명령을 실행하여 빠르게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-221">After installing Minikube, you can quickly start using it by running the `minikube start` command, which downloads an image and start the local Kubernetes cluster.</span></span> <span data-ttu-id="bc34f-222">클러스터가 시작되면 표준 Kubernetes `kubectl` 명령을 사용하여 클러스터와 상호 작용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-222">Once the cluster is started, you interact with it using the standard Kubernetes `kubectl` commands.</span></span>

### <a name="docker-desktop"></a><span data-ttu-id="bc34f-223">Docker Desktop</span><span class="sxs-lookup"><span data-stu-id="bc34f-223">Docker Desktop</span></span>

<span data-ttu-id="bc34f-224">또한 Windows의 Docker 데스크톱에서 직접 Kubernetes로 작업할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-224">You can also work with Kubernetes directly from Docker Desktop on Windows.</span></span> <span data-ttu-id="bc34f-225">Windows 컨테이너를 사용하는 경우 이 옵션만 사용할 수 있으며 Windows가 아닌 컨테이너에도 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-225">This is your only option if you're using Windows Containers, and is a great choice for non-Windows containers as well.</span></span> <span data-ttu-id="bc34f-226">표준 Docker 데스크톱 구성 응용 프로그램은 Docker 데스크톱에서 실행 중인 Kubernetes를 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-226">The standard Docker Desktop configuration app is used to configure Kubernetes running from Docker Desktop.</span></span>

![Docker 데스크톱에서 쿠버넷 구성](./media/docker-desktop-kubernetes.png)

<span data-ttu-id="bc34f-228">**그림 3-4 .**</span><span class="sxs-lookup"><span data-stu-id="bc34f-228">**Figure 3-4**.</span></span> <span data-ttu-id="bc34f-229">Docker 데스크톱에서 Kubernetes 구성.</span><span class="sxs-lookup"><span data-stu-id="bc34f-229">Configuring Kubernetes in Docker Desktop.</span></span>

<span data-ttu-id="bc34f-230">Docker Desktop은 이미 컨테이너화된 앱을 로컬로 구성하고 실행하기 위한 가장 인기 있는 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-230">Docker Desktop is already the most popular tool for configuring and running containerized apps locally.</span></span> <span data-ttu-id="bc34f-231">Docker Desktop으로 작업하는 경우 프로덕션에 배포할 동일한 Docker 컨테이너 이미지 집합에 대해 로컬로 개발할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-231">When you work with Docker Desktop, you can develop locally against the exact same set of Docker container images that you'll deploy to production.</span></span> <span data-ttu-id="bc34f-232">Docker Desktop은 컨테이너화된 앱을 로컬로 "빌드, 테스트 및 제공"하도록 설계되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-232">Docker Desktop is designed to "build, test, and ship" containerized apps locally.</span></span> <span data-ttu-id="bc34f-233">이미지가 Azure 컨테이너 레지스트리 또는 Docker Hub와 같은 이미지 레지스트리로 제공되면 AKS(Azure Kubernetes Service)와 같은 서비스가 프로덕션 환경에서 응용 프로그램을 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-233">Once the images have been shipped to an image registry like Azure Container Registry or Docker Hub, then services like Azure Kubernetes Service (AKS) manage the application in production.</span></span>

### <a name="visual-studio-docker-tooling"></a><span data-ttu-id="bc34f-234">비주얼 스튜디오 도커 툴링</span><span class="sxs-lookup"><span data-stu-id="bc34f-234">Visual Studio Docker Tooling</span></span>

<span data-ttu-id="bc34f-235">Visual Studio는 웹 응용 프로그램에 대한 Docker 개발을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-235">Visual Studio supports Docker development for web applications.</span></span> <span data-ttu-id="bc34f-236">새 ASP.NET Core 응용 프로그램을 만들 때 그림 3-5와 같이 프로젝트 만들기 프로세스의 일부로 Docker 지원으로 구성할 수 있는 옵션이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-236">When you create a new ASP.NET Core application, you're given the option to configure it with Docker support as part of the project creation process, as shown in Figure 3-5.</span></span>

![비주얼 스튜디오, Docker 지원 지원 지원](./media/visual-studio-enable-docker-support.png)

<span data-ttu-id="bc34f-238">**그림 3-5 .**</span><span class="sxs-lookup"><span data-stu-id="bc34f-238">**Figure 3-5**.</span></span> <span data-ttu-id="bc34f-239">비주얼 스튜디오, Docker 지원 지원 지원</span><span class="sxs-lookup"><span data-stu-id="bc34f-239">Visual Studio Enable Docker Support</span></span>

<span data-ttu-id="bc34f-240">이 옵션을 선택하면 프로젝트가 루트에 있는 `Dockerfile` 것으로 만들어지며, 이 루트는 Docker 컨테이너에서 앱을 빌드하고 호스팅하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-240">When this option is selected, the project is created with a `Dockerfile` in its root, which can be used to build and host the app in a Docker container.</span></span> <span data-ttu-id="bc34f-241">도커파일의 예는 그림 3-6에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-241">An example Dockerfile is shown in Figure 3-6.</span></span>

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

<span data-ttu-id="bc34f-242">**그림 3-6**.</span><span class="sxs-lookup"><span data-stu-id="bc34f-242">**Figure 3-6**.</span></span> <span data-ttu-id="bc34f-243">비주얼 스튜디오 생성 도커 파일</span><span class="sxs-lookup"><span data-stu-id="bc34f-243">Visual Studio generated Dockerfile</span></span>

<span data-ttu-id="bc34f-244">앱이 실행될 때의 기본 동작은 Docker도 사용하도록 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-244">The default behavior when the app runs is configured to use Docker as well.</span></span> <span data-ttu-id="bc34f-245">그림 3-7은 Docker 지원이 추가된 것으로 만든 새로운 ASP.NET Core 프로젝트에서 사용할 수 있는 다양한 실행 옵션을 보여 주며 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-245">Figure 3-7 shows the different run options available from a new ASP.NET Core project created with Docker support added.</span></span>

![비주얼 스튜디오 도커 실행 옵션](./media/visual-studio-docker-run-options.png)

<span data-ttu-id="bc34f-247">**그림 3-7**.</span><span class="sxs-lookup"><span data-stu-id="bc34f-247">**Figure 3-7**.</span></span> <span data-ttu-id="bc34f-248">비주얼 스튜디오 도커 실행 옵션</span><span class="sxs-lookup"><span data-stu-id="bc34f-248">Visual Studio Docker Run Options</span></span>

<span data-ttu-id="bc34f-249">[Azure 개발자 공간은](https://docs.microsoft.com/azure/dev-spaces/) 로컬 개발 외에도 여러 개발자가 Azure 내에서 자체 Kubernetes 구성으로 작업할 수 있는 편리한 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-249">In addition to local development, [Azure Dev Spaces](https://docs.microsoft.com/azure/dev-spaces/) provides a convenient way for multiple developers to work with their own Kubernetes configurations within Azure.</span></span> <span data-ttu-id="bc34f-250">그림 3-7에서 볼 수 있듯이 Azure 개발자 공간에서 응용 프로그램을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-250">As you can see in Figure 3-7, you can also run the application in Azure Dev Spaces.</span></span>

<span data-ttu-id="bc34f-251">ASP.NET Core 응용 프로그램에 Docker 지원을 추가하지 않으면 나중에 언제든지 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-251">If you don't add Docker support to your ASP.NET Core application when you create it, you can always add it later.</span></span> <span data-ttu-id="bc34f-252">시각적 스튜디오 솔루션 탐색기에서 프로젝트를 마우스 오른쪽 버튼으로 클릭하고 그림 3-8과 같이**Docker 지원** **추가를** > 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-252">From the Visual Studio Solution Explorer, right click on the project and select **Add** > **Docker Support**, as shown in Figure 3-8.</span></span>

![비주얼 스튜디오 도커 지원 추가](./media/visual-studio-add-docker-support.png)

<span data-ttu-id="bc34f-254">**그림 3-8**.</span><span class="sxs-lookup"><span data-stu-id="bc34f-254">**Figure 3-8**.</span></span> <span data-ttu-id="bc34f-255">비주얼 스튜디오 도커 지원 추가</span><span class="sxs-lookup"><span data-stu-id="bc34f-255">Visual Studio Add Docker Support</span></span>

<span data-ttu-id="bc34f-256">Docker 지원 외에도 그림 3-8에 표시된 컨테이너 오케스트레이션 지원을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-256">In addition to Docker support, you can also add Container Orchestration Support, also shown in Figure 3-8.</span></span> <span data-ttu-id="bc34f-257">기본적으로 오케스트레이터는 Kubernetes와 Helm을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-257">By default, the orchestrator uses Kubernetes and Helm.</span></span> <span data-ttu-id="bc34f-258">오케스트레이터를 선택하면 `azds.yaml` 파일이 프로젝트 루트에 추가되고 `charts` Kubernetes에 응용 프로그램을 구성하고 배포하는 데 사용되는 Helm 차트가 포함된 폴더가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-258">Once you've chosen the orchestrator, a `azds.yaml` file is added to the project root and a `charts` folder is added containing the Helm charts used to configure and deploy the application to Kubernetes.</span></span> <span data-ttu-id="bc34f-259">그림 3-9는 새 프로젝트의 결과 파일을 보여 주다.</span><span class="sxs-lookup"><span data-stu-id="bc34f-259">Figure 3-9 shows the resulting files in a new project.</span></span>

![비주얼 스튜디오 오케스트레이터 지원 추가](./media/visual-studio-add-orchestrator-support.png)

<span data-ttu-id="bc34f-261">**그림 3-9**.</span><span class="sxs-lookup"><span data-stu-id="bc34f-261">**Figure 3-9**.</span></span> <span data-ttu-id="bc34f-262">비주얼 스튜디오 오케스트레이터 지원 추가</span><span class="sxs-lookup"><span data-stu-id="bc34f-262">Visual Studio Add Orchestrator Support</span></span>

## <a name="references"></a><span data-ttu-id="bc34f-263">참조</span><span class="sxs-lookup"><span data-stu-id="bc34f-263">References</span></span>

- [<span data-ttu-id="bc34f-264">Kubernetes란?</span><span class="sxs-lookup"><span data-stu-id="bc34f-264">What is Kubernetes?</span></span>](https://blog.newrelic.com/engineering/what-is-kubernetes/)
- [<span data-ttu-id="bc34f-265">미니쿠베로 쿠베르네츠 설치</span><span class="sxs-lookup"><span data-stu-id="bc34f-265">Installing Kubernetes with Minikube</span></span>](https://kubernetes.io/docs/setup/learning-environment/minikube/)
- [<span data-ttu-id="bc34f-266">미니쿠베 vs 도커 데스크탑</span><span class="sxs-lookup"><span data-stu-id="bc34f-266">MiniKube vs Docker Desktop</span></span>](https://medium.com/containers-101/local-kubernetes-for-windows-minikube-vs-docker-desktop-25a1c6d3b766)
- [<span data-ttu-id="bc34f-267">Docker용 Visual Studio Tools</span><span class="sxs-lookup"><span data-stu-id="bc34f-267">Visual Studio Tools for Docker</span></span>](https://docs.microsoft.com/dotnet/standard/containerized-lifecycle-architecture/design-develop-containerized-apps/visual-studio-tools-for-docker)

>[!div class="step-by-step"]
><span data-ttu-id="bc34f-268">[이전](scale-applications.md)
>[다음](leverage-serverless-functions.md)</span><span class="sxs-lookup"><span data-stu-id="bc34f-268">[Previous](scale-applications.md)
[Next](leverage-serverless-functions.md)</span></span>
