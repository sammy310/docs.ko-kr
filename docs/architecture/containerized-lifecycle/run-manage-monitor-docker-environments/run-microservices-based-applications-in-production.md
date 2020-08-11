---
title: 프로덕션 환경에서 구성된 마이크로서비스 기반 애플리케이션 실행
description: 프로덕션 환경에서 컨테이너 기반 애플리케이션을 실행하기 위한 주요 구성 요소를 알아봅니다.
ms.date: 08/06/2020
ms.openlocfilehash: a045804e2e40dcf401a697d3e58b13f05ca61b94
ms.sourcegitcommit: ef50c99928183a0bba75e07b9f22895cd4c480f8
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/07/2020
ms.locfileid: "87915051"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a><span data-ttu-id="d6c63-103">프로덕션 환경에서 구성된 마이크로서비스 기반 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="d6c63-103">Run composed and microservices-based applications in production environments</span></span>

<span data-ttu-id="d6c63-104">여러 마이크로서비스로 구성된 애플리케이션은 배포의 복잡성을 줄이고 IT 관점에서 실현 가능하도록 오케스트레이터 클러스터에 배포해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-104">Applications composed by multiple microservices do need to be deployed into orchestrator clusters in order to simplify the complexity of deployment and make it viable from an IT point of view.</span></span> <span data-ttu-id="d6c63-105">오케스트레이터 클러스터가 없으면 복잡한 마이크로서비스 애플리케이션을 배포하고 확장하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-105">Without an orchestrator cluster, it would be difficult to deploy and scale out a complex microservices application.</span></span>

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a><span data-ttu-id="d6c63-106">오케스트레이터, 스케줄러 및 컨테이너 클러스터 소개</span><span class="sxs-lookup"><span data-stu-id="d6c63-106">Introduction to orchestrators, schedulers, and container clusters</span></span>

<span data-ttu-id="d6c63-107">이 eBook의 앞부분에서 소프트웨어 아키텍처와 개발에 대해 알아보면서 *클러스터* 및 *스케줄러*를 소개했습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-107">Earlier in this e-book, *clusters* and *schedulers* were introduced as part of the discussion on software architecture and development.</span></span> <span data-ttu-id="d6c63-108">Kubernetes 및 Service Fabric은 Docker 클러스터의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-108">Kubernetes and Service Fabric are examples of Docker clusters.</span></span> <span data-ttu-id="d6c63-109">두 오케스트레이터 모두 Microsoft Azure Kubernetes Service에서 제공하는 인프라의 일부로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-109">Both of these orchestrators can run as a part of the infrastructure provided by Microsoft Azure Kubernetes Service.</span></span>

<span data-ttu-id="d6c63-110">애플리케이션을 다중 호스트 시스템으로 확장하면 각 호스트 시스템을 관리하고 기본 플랫폼의 복잡성을 추상화하는 기능이 필요하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-110">When applications are scaled-out across multiple host systems, the ability to manage each host system and abstract away the complexity of the underlying platform becomes attractive.</span></span> <span data-ttu-id="d6c63-111">이 기능을 제공하는 것이 바로 오케스트레이터와 스케줄러입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-111">That's precisely what orchestrators and schedulers provide.</span></span> <span data-ttu-id="d6c63-112">이 둘에 대해 간략하게 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-112">Let's take a brief look at them here:</span></span>

- <span data-ttu-id="d6c63-113">**스케줄러**</span><span class="sxs-lookup"><span data-stu-id="d6c63-113">**Schedulers**.</span></span><span data-ttu-id="d6c63-114"> "일정 예약"이란 관리자가 특정 컨테이너를 실행하는 방법을 설정하는 호스트 시스템에 서비스 파일을 로드하는 기능을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-114"> "Scheduling" refers to the ability for an administrator to load a service file onto a host system that establishes how to run a specific container.</span></span> <span data-ttu-id="d6c63-115">Docker 클러스터에서 컨테이너를 시작하는 것을 일정 예약이라고 하는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-115">Launching containers in a Docker cluster tends to be known as scheduling.</span></span> <span data-ttu-id="d6c63-116">일정 예약은 서비스 정의를 로드하는 특정 작업을 의미하지만, 일반적으로 스케줄러는 필요한 용량이 얼마가 됐든 호스트의 init 시스템에 연결하여 서비스를 관리하는 일을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-116">Although scheduling refers to the specific act of loading the service definition, in a more general sense, schedulers are responsible for hooking into a host's init system to manage services in whatever capacity needed.</span></span>

   <span data-ttu-id="d6c63-117">클러스터 스케줄러의 목표는 클러스터 리소스의 효율적 사용, 사용자가 제공한 배치 제약 조건 사용, 애플리케이션이 보류 중 상태가 되지 않도록 신속하게 애플리케이션 일정 예약, 일정 수준의 "공정성" 확보, 내결함성 확보, 고가용성 확보 등 여러 가지가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-117">A cluster scheduler has multiple goals: using the cluster's resources efficiently, working with user-supplied placement constraints, scheduling applications rapidly to not leave them in a pending state, having a degree of "fairness," being robust to errors, and always be available.</span></span>

- <span data-ttu-id="d6c63-118">**오케스트레이터**.</span><span class="sxs-lookup"><span data-stu-id="d6c63-118">**Orchestrators**.</span></span><span data-ttu-id="d6c63-119"> 플랫폼은 수명 주기 관리 기능을 호스트 클러스터에 배포되는 복잡한 다중 컨테이너 워크로드로 확장합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-119"> Platforms extend life-cycle management capabilities to complex, multi-container workloads deployed on a cluster of hosts.</span></span> <span data-ttu-id="d6c63-120">오케스트레이션 도구는 호스트 인프라를 추상화하여 사용자에게 전체 클러스터를 단일 배포 대상으로 처리하는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-120">By abstracting the host infrastructure, orchestration tools give users a way to treat the entire cluster as a single deployment target.</span></span>

   <span data-ttu-id="d6c63-121">오케스트레이션 프로세스에는 컨테이너별 초기 배치 또는 배포부터 호스트 상태 또는 성능에 따라 컨테이너를 다른 호스트로 이동, 업데이트의 버전 관리 및 출시, 크기 조정 및 장애 조치(failover)를 지원하는 상태 모니터링 함수까지 모든 애플리케이션 관리 업무를 자동화할 수 있는 도구와 플랫폼이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-121">The process of orchestration involves tooling and a platform that can automate all aspects of application management from initial placement or deployment per container; moving containers to different hosts depending on its host's health or performance; versioning and rolling updates and health monitoring functions that support scaling and failover; and many more.</span></span>

   <span data-ttu-id="d6c63-122">오케스트레이션은 컨테이너 일정 예약, 클러스터 관리 및 가능한 추가 호스트 프로비저닝을 의미하는 광범위한 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-122">Orchestration is a broad term that refers to container scheduling, cluster management, and possibly the provisioning of additional hosts.</span></span>

<span data-ttu-id="d6c63-123">오케스트레이터와 스케줄러에서 제공하는 기능을 처음부터 새로 개발하고 만들려면 매우 복잡하기 때문에 공급업체에서 제공하는 오케스트레이션 솔루션을 사용하는 것이 일반적입니다.</span><span class="sxs-lookup"><span data-stu-id="d6c63-123">The capabilities provided by orchestrators and schedulers are complex to develop and create from scratch, therefore you usually would want to use orchestration solutions offered by vendors.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="d6c63-124">[이전](index.md)
>[다음](manage-production-docker-environments.md)</span><span class="sxs-lookup"><span data-stu-id="d6c63-124">[Previous](index.md)
[Next](manage-production-docker-environments.md)</span></span>
