---
title: 프로덕션 환경에서 구성된 마이크로서비스 기반 애플리케이션 실행
description: 프로덕션 환경에서 컨테이너 기반 응용 프로그램을 실행 하는 주요 구성 요소에 알아봅니다
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 02/15/2019
ms.openlocfilehash: 52cf273194bff10192b06d236bda7c1cbea1abd8
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921591"
---
# <a name="run-composed-and-microservices-based-applications-in-production-environments"></a><span data-ttu-id="8a363-103">프로덕션 환경에서 구성된 마이크로서비스 기반 애플리케이션 실행</span><span class="sxs-lookup"><span data-stu-id="8a363-103">Run composed and microservices-based applications in production environments</span></span>

<span data-ttu-id="8a363-104">여러 마이크로 서비스에서 구성 된 응용 프로그램 배포의 복잡성을 단순화 하 고는 IT 관점에서 실행 가능한 있도록 오 케 스트레이 터 클러스터로 배포할 필요가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-104">Applications composed by multiple microservices do need to be deployed into orchestrator clusters in order to simplify the complexity of deployment and make it viable from an IT point of view.</span></span> <span data-ttu-id="8a363-105">없이 오 케 스트레이 터 클러스터를 배포 하 고 복잡 한 마이크로 서비스 응용 프로그램을 확장 하기 어려울 것.</span><span class="sxs-lookup"><span data-stu-id="8a363-105">Without an orchestrator cluster, it would be difficult to deploy and scale out a complex microservices application.</span></span>

## <a name="introduction-to-orchestrators-schedulers-and-container-clusters"></a><span data-ttu-id="8a363-106">오 케 스트레이 터, 스케줄러 및 컨테이너 클러스터에 대 한 소개</span><span class="sxs-lookup"><span data-stu-id="8a363-106">Introduction to orchestrators, schedulers, and container clusters</span></span>

<span data-ttu-id="8a363-107">이 전자책의 앞부분에 나오는 *클러스터* 하 고 *스케줄러* 소프트웨어 아키텍처 및 개발에 대 한 논의의 일부로 도입 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-107">Earlier in this e-book, *clusters* and *schedulers* were introduced as part of the discussion on software architecture and development.</span></span> <span data-ttu-id="8a363-108">Kubernetes 및 Service Fabric은 Docker 클러스터의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-108">Kubernetes and Service Fabric are examples of Docker clusters.</span></span> <span data-ttu-id="8a363-109">이러한 오 케 스트레이이 터의 두 가지 모두 Microsoft Azure Kubernetes Service에서 제공 하는 인프라의 일부로 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-109">Both of these orchestrators can run as a part of the infrastructure provided by Microsoft Azure Kubernetes Service.</span></span>

<span data-ttu-id="8a363-110">응용 프로그램은 확장 된 여러 호스트 시스템에서 각각의 호스트 시스템을 관리 하 고 기본 플랫폼의 복잡성을 추상화 하는 기능 면 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-110">When applications are scaled-out across multiple host systems, the ability to manage each host system and abstract away the complexity of the underlying platform becomes attractive.</span></span> <span data-ttu-id="8a363-111">정확 하 게는 새로운 오 케 스트레이 터 및 스케줄러를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-111">That's precisely what orchestrators and schedulers provide.</span></span> <span data-ttu-id="8a363-112">여기에 해당에 대해 간략하게를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-112">Let's take a brief look at them here:</span></span>

- <span data-ttu-id="8a363-113">**스케줄러**</span><span class="sxs-lookup"><span data-stu-id="8a363-113">**Schedulers**.</span></span><span data-ttu-id="8a363-114"> "일정" 특정 컨테이너를 실행 하는 방법을 설정 하는 호스트 시스템에 서비스 파일을 로드 하는 관리자에 대 한 기능을 말합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-114"> "Scheduling" refers to the ability for an administrator to load a service file onto a host system that establishes how to run a specific container.</span></span> <span data-ttu-id="8a363-115">Docker 클러스터에서 컨테이너 시작 예약 이라고 하는 경향이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-115">Launching containers in a Docker cluster tends to be known as scheduling.</span></span> <span data-ttu-id="8a363-116">예약 보다 일반적인 관점에서 서비스 정의 로드 하는 특정 작업을 의미 하지만 스케줄러는 호스트의 필요한 모든 용량에서 서비스를 관리 하는 init 시스템에 연결 하는 일을 담당 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-116">Although scheduling refers to the specific act of loading the service definition, in a more general sense, schedulers are responsible for hooking into a host's init system to manage services in whatever capacity needed.</span></span>

   <span data-ttu-id="8a363-117">클러스터 스케줄러에는 여러 목표: 클러스터의 리소스를 효율적으로 사용, 예약 응용 프로그램 신속 하 게 하지 보류 중 상태에서 그대로 "공정성," 오류 강력한 중 어느 정도 있는 사용자가 제공한 배치 제약 조건, 작업 및 항상 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-117">A cluster scheduler has multiple goals: using the cluster's resources efficiently, working with user-supplied placement constraints, scheduling applications rapidly to not leave them in a pending state, having a degree of "fairness," being robust to errors, and always be available.</span></span>

- <span data-ttu-id="8a363-118">**오 케 스트레이 터**합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-118">**Orchestrators**.</span></span><span data-ttu-id="8a363-119"> 호스트 클러스터에 배포 하는 복잡 하 고 다중 컨테이너 워크 로드에 수명 주기 관리 기능을 확장 하는 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-119"> Platforms extend life-cycle management capabilities to complex, multi-container workloads deployed on a cluster of hosts.</span></span> <span data-ttu-id="8a363-120">호스트 인프라를 추상화 하 여 오케스트레이션 도구 전체 클러스터는 단일 배포 대상으로 처리 하는 방법을 사용자에 게를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-120">By abstracting the host infrastructure, orchestration tools give users a way to treat the entire cluster as a single deployment target.</span></span>

   <span data-ttu-id="8a363-121">오케스트레이션 과정 초기 배치 또는 컨테이너 당 배포에서 응용 프로그램 관리의 모든 측면을 자동화할 수 있는 플랫폼 및 도구 컨테이너는 호스트의 상태 또는 성능을 따라 서로 다른 호스트 이동 버전 관리 및 롤링 업데이트 및 크기 조정 및 장애 조치를 지 원하는 함수를 모니터링 하는 상태 기타 등등</span><span class="sxs-lookup"><span data-stu-id="8a363-121">The process of orchestration involves tooling and a platform that can automate all aspects of application management from initial placement or deployment per container; moving containers to different hosts depending on its host's health or performance; versioning and rolling updates and health monitoring functions that support scaling and failover; and many more.</span></span>

   <span data-ttu-id="8a363-122">오케스트레이션은 컨테이너 예약, 클러스터 관리 및 가능한 경우 프로 비전 추가 호스트를 참조 하는 광범위 한 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-122">Orchestration is a broad term that refers to container scheduling, cluster management, and possibly the provisioning of additional hosts.</span></span>

<span data-ttu-id="8a363-123">개발 하 고 처음부터 새로 만드는 복잡 한 오 케 스트레이 터 및 스케줄러에서 제공 하는 기능을 따라서 일반적으로 하려는 공급 업체에서 제공 하는 오케스트레이션 솔루션을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8a363-123">The capabilities provided by orchestrators and schedulers are complex to develop and create from scratch, therefore you usually would want to use orchestration solutions offered by vendors.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="8a363-124">[이전](index.md)
>[다음](manage-production-docker-environments.md)</span><span class="sxs-lookup"><span data-stu-id="8a363-124">[Previous](index.md)
[Next](manage-production-docker-environments.md)</span></span>
