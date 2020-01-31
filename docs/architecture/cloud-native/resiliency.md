---
title: 클라우드 네이티브 복원력
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 클라우드 기본 복원 력
ms.date: 06/30/2019
ms.openlocfilehash: 427405d95534c4467ab519c2188fe88e2f18e2b2
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/28/2020
ms.locfileid: "76781080"
---
# <a name="cloud-native-resiliency"></a><span data-ttu-id="98b5e-103">클라우드 네이티브 복원력</span><span class="sxs-lookup"><span data-stu-id="98b5e-103">Cloud-native resiliency</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="98b5e-104">복원 력은 시스템에서 오류에 대응 하 여 계속 작동 하는 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-104">Resiliency is the ability of your system to react to failure and still remain functional.</span></span> <span data-ttu-id="98b5e-105">실패를 방지 하는 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-105">It isn't about avoiding failure.</span></span> <span data-ttu-id="98b5e-106">그러나 이러한 오류는 클라우드 기반 시스템에서 피할 수 있으며 응용 프로그램을 구축 하 여 응답 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-106">But it's about accepting that failure is inevitable in cloud-based systems and building your application to respond to it.</span></span> <span data-ttu-id="98b5e-107">복원 력의 최종 목표는 오류 발생 후 응용 프로그램을 완전히 작동 하는 상태로 되돌리는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-107">The end-goal of resiliency is to return the application to a fully functioning state after a failure.</span></span>

<span data-ttu-id="98b5e-108">단일 프로세스에서 모든 항목을 함께 실행 하는 기존 모놀리식 응용 프로그램과 달리 클라우드 네이티브 시스템은 그림 6-1에 표시 된 것 처럼 분산 아키텍처를 수용 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-108">Unlike traditional monolithic applications, where everything runs together in a single process, cloud-native systems embrace distributed architecture as shown in Figure 6-1:</span></span>

![분산 클라우드-기본 환경](./media/distributed-cloud-native-environment.png)

<span data-ttu-id="98b5e-110">**그림 6-1.**</span><span class="sxs-lookup"><span data-stu-id="98b5e-110">**Figure 6-1.**</span></span> <span data-ttu-id="98b5e-111">분산 클라우드-기본 환경</span><span class="sxs-lookup"><span data-stu-id="98b5e-111">Distributed cloud-native environment</span></span>

<span data-ttu-id="98b5e-112">위의 그림에서 각 클라이언트, 마이크로 서비스 및 클라우드 기반 [지원 서비스](https://12factor.net/backing-services) 는 서로 다른 서버에서 실행 되는 별도의 프로세스로 실행 되 고, 모두 네트워크 기반 호출을 통해 통신 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-112">In the previous figure, note how each client, microservice, and cloud-based [backing service](https://12factor.net/backing-services) executes as a separate process, running across different servers, all communicating via network-based calls.</span></span>

<span data-ttu-id="98b5e-113">그렇다면 무엇이 잘못 되었나요?</span><span class="sxs-lookup"><span data-stu-id="98b5e-113">So, what could go wrong?</span></span>

- <span data-ttu-id="98b5e-114">예기치 않은 [네트워크 대기 시간](https://www.techopedia.com/definition/8553/network-latency)입니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-114">Unexpected [network latency](https://www.techopedia.com/definition/8553/network-latency).</span></span>
- <span data-ttu-id="98b5e-115">[일시적인 오류](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (임시 네트워크 연결 오류).</span><span class="sxs-lookup"><span data-stu-id="98b5e-115">[Transient faults](https://docs.microsoft.com/azure/architecture/best-practices/transient-faults) (temporary network connectivity errors).</span></span>
- <span data-ttu-id="98b5e-116">장기 실행 동기 작업에서 차단</span><span class="sxs-lookup"><span data-stu-id="98b5e-116">Blocking by a long-running synchronous operation.</span></span>
- <span data-ttu-id="98b5e-117">작동이 중단 되 고 다시 시작 되거나 이동 중인 호스트 프로세스입니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-117">A host process that has crashed and is being restarted or moved.</span></span>
- <span data-ttu-id="98b5e-118">짧은 시간 동안 응답할 수 없는 오버 로드 된 마이크로 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-118">An overloaded microservice that can't respond for a short time.</span></span>
- <span data-ttu-id="98b5e-119">업데이트 또는 크기 조정 작업과 같은 진행 중인 DevOps 작업</span><span class="sxs-lookup"><span data-stu-id="98b5e-119">An in-flight DevOps operation such as an update or scaling operation.</span></span>
- <span data-ttu-id="98b5e-120">한 노드에서 다른 노드로 서비스를 이동 하는 등의 오 케 스트레이 터 작업</span><span class="sxs-lookup"><span data-stu-id="98b5e-120">An Orchestrator operation such as moving a service from one node to another.</span></span>
- <span data-ttu-id="98b5e-121">상용 하드웨어의 하드웨어 오류입니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-121">Hardware failures from commodity hardware.</span></span>

<span data-ttu-id="98b5e-122">클라우드 기반 인프라에 배포 된 서비스를 배포 하는 경우에는 이전 목록의 요소가 매우 실제적이 고이를 처리 하는 defensively을 설계 하 고 개발 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-122">When deploying distributed services into cloud-based infrastructure, the factors from the previous list become very real and you must architect and develop defensively to deal with them.</span></span>

<span data-ttu-id="98b5e-123">소규모 분산 시스템에서는 오류가 자주 발생 하지 않지만 시스템이 확장 되거나 축소 되 면 부분 오류가 정상적인 작업이 되는 지점에 이러한 문제를 더 많이 경험할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-123">In a small-scale distributed system, failure will be less frequent, but as a system scales up and out, you can expect to experience more of these issues to a point where partial failure becomes normal operation.</span></span>

<span data-ttu-id="98b5e-124">따라서 응용 프로그램 및 인프라는 복원 력이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-124">Therefore, your application and infrastructure must be resilient.</span></span> <span data-ttu-id="98b5e-125">다음 섹션에서는 응용 프로그램에 추가할 수 있는 방어 기법 및 사용자 환경을 쉽게 확인할 수 있도록 활용할 수 있는 기본 제공 클라우드 기능을 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="98b5e-125">In the following sections, we'll explore defensive techniques that you can add to your application and built-in cloud features that you can leverage to help bullet-proof your user's experience.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="98b5e-126">[이전](elastic-search-in-azure.md)
>[다음](application-resiliency-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="98b5e-126">[Previous](elastic-search-in-azure.md)
[Next](application-resiliency-patterns.md)</span></span>
