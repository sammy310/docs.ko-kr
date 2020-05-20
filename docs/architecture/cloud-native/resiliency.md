---
title: 클라우드 네이티브 복원력
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 클라우드 기본 복원 력
author: robvet
ms.date: 05/13/2020
ms.openlocfilehash: f3aa89e3ae21b13a31f65013b59636b3f931553c
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613774"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="4fc2e-103">클라우드 네이티브 복원력</span><span class="sxs-lookup"><span data-stu-id="4fc2e-103">Cloud-native resiliency</span></span>

<span data-ttu-id="4fc2e-104">복원 력은 시스템에서 오류에 대응 하 여 계속 작동 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="4fc2e-105">오류를 방지 하는 것은 아니지만 실패를 수락 하 고 클라우드-원시 서비스를 구성 하 여 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-105">It's not about avoiding failure, but accepting failure and constructing your cloud-native services to respond to it.</span></span> <span data-ttu-id="4fc2e-106">가능 하면 신속 하 게 작동 하는 상태로 돌아갈 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-106">You want to return to a fully functioning state quickly as possible.</span></span>

<span data-ttu-id="4fc2e-107">단일 프로세스에서 모든 항목을 함께 실행 하는 기존 모놀리식 응용 프로그램과 달리 클라우드 네이티브 시스템은 그림 6-1에 표시 된 것 처럼 분산 아키텍처를 수용 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-107">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace a distributed architecture as shown in Figure 6-1:</span></span>

![분산 클라우드-기본 환경](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="4fc2e-109">**그림 6-1.**</span><span class="sxs-lookup"><span data-stu-id="4fc2e-109">**Figure 6-1.**</span></span> <span data-ttu-id="4fc2e-110">분산 클라우드-기본 환경</span><span class="sxs-lookup"><span data-stu-id="4fc2e-110">Distributed cloud-native environment</span></span>

<span data-ttu-id="4fc2e-111">위의 그림에서 각 마이크로 서비스 및 클라우드 기반 [지원 서비스](https://12factor.net/backing-services) 는 서버 인프라 전체에서 네트워크 기반 호출을 통해 통신 하는 별도의 프로세스로 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-111">In the previous figure, each microservice and cloud-based [backing service](https://12factor.net/backing-services) execute in a separate process, across server infrastructure, communicating via network-based calls.</span></span>

<span data-ttu-id="4fc2e-112">이 환경에서 작동 하는 서비스는 다양 한 문제를 해결 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-112">Operating in this environment, a service must be sensitive to many different challenges:</span></span>

- <span data-ttu-id="4fc2e-113">예기치 않은 네트워크 대기 시간-서비스 요청이 수신기로 이동 하는 시간입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-113">Unexpected network latency - the time for a service request to travel to the receiver and back.</span></span>

- <span data-ttu-id="4fc2e-114">[일시적인 오류](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) -수명이 짧은 네트워크 연결 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-114">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) - short-lived network connectivity errors.</span></span>

- <span data-ttu-id="4fc2e-115">장기 실행 동기 작업으로 차단을.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-115">Blockage by a long-running synchronous operation.</span></span>

- <span data-ttu-id="4fc2e-116">작동이 중단 되 고 다시 시작 되거나 이동 중인 호스트 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-116">A host process that has crashed and is being restarted or moved.</span></span>

- <span data-ttu-id="4fc2e-117">짧은 시간 동안 응답할 수 없는 오버 로드 된 마이크로 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-117">An overloaded microservice that can't respond for a short time.</span></span>

- <span data-ttu-id="4fc2e-118">롤링 업그레이드 또는 한 노드에서 다른 노드로 서비스 이동과 같은 진행 중인 orchestrator 작업</span><span class="sxs-lookup"><span data-stu-id="4fc2e-118">An in-flight orchestrator operation such as a rolling upgrade or moving a service from one node to another.</span></span>

- <span data-ttu-id="4fc2e-119">하드웨어 오류.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-119">Hardware failures.</span></span>

<span data-ttu-id="4fc2e-120">클라우드 플랫폼은 이러한 많은 인프라 문제를 감지 하 고 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-120">Cloud platforms can detect and mitigate many of these infrastructure issues.</span></span> <span data-ttu-id="4fc2e-121">다시 시작 하 고, 규모를 확장 하 고, 서비스를 다른 노드로 재배포할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-121">It may restart, scale out, and even redistribute your service to a different node.</span></span>  <span data-ttu-id="4fc2e-122">그러나이 기본 제공 보호 기능을 최대한 활용 하려면이 동적 환경에서 it 및 올립니다에 대응할 수 있도록 서비스를 설계 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-122">However, to take full advantage of this built-in protection, you must design your services to react to it and thrive in this dynamic environment.</span></span>

<span data-ttu-id="4fc2e-123">다음 섹션에서는 가동 중지 시간 및 중단을 최소화 하기 위해 서비스 및 관리 되는 클라우드 리소스가 활용할 수 있는 방어 기법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="4fc2e-123">In the following sections, we'll explore defensive techniques that your service and managed cloud resources can leverage to minimize downtime and disruption.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="4fc2e-124">[이전](elastic-search-in-azure.md)
>[다음](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="4fc2e-124">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
