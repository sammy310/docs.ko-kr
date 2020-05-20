---
title: 모니터링 및 상태
description: 모니터링 및 상태
ms.date: 05/13/2020
ms.openlocfilehash: 28e98bbdb39a68d8961d4f3ab48cde5a07a4762b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83613800"
---
# <a name="monitoring-and-health"></a><span data-ttu-id="fc2a0-103">모니터링 및 상태</span><span class="sxs-lookup"><span data-stu-id="fc2a0-103">Monitoring and health</span></span>

<span data-ttu-id="fc2a0-104">마이크로 서비스와 클라우드 네이티브 응용 프로그램은 좋은 DevOps 방법으로 직접 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2a0-104">Microservices and cloud-native applications go hand in hand with good DevOps practices.</span></span> <span data-ttu-id="fc2a0-105">DevOps는 많은 사람들에 게 많은 것이 있지만 더 나은 정의 중 하나는 클라우드 대표 및 DevOps 전도사 Donovan 갈색에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fc2a0-105">DevOps is many things to many people but perhaps one of the better definitions comes from cloud advocate and DevOps evangelist Donovan Brown:</span></span>

<span data-ttu-id="fc2a0-106">"DevOps는 최종 사용자에 게 가치를 지속적으로 제공할 수 있는 사람, 프로세스 및 제품의 합집합입니다."</span><span class="sxs-lookup"><span data-stu-id="fc2a0-106">"DevOps is the union of people, process, and products to enable continuous delivery of value to our end users."</span></span>

<span data-ttu-id="fc2a0-107">아쉽게도 간결한 정의를 사용 하 여 더 많은 작업을 수행할 수 있는 공간이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fc2a0-107">Unfortunately, with terse definitions, there's always room to say more things.</span></span> <span data-ttu-id="fc2a0-108">DevOps의 주요 구성 요소 중 하나는 프로덕션 환경에서 실행 되는 응용 프로그램이 올바르고 효율적으로 작동 하 고 있는지 확인 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2a0-108">One of the key components of DevOps is ensuring that the applications running in production are functioning properly and efficiently.</span></span> <span data-ttu-id="fc2a0-109">프로덕션 환경에서 응용 프로그램의 상태를 측정 하려면 서버, 호스트 및 응용 프로그램에서 생성 되는 다양 한 로그 및 메트릭을 모니터링 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="fc2a0-109">To gauge the health of the application in production, it's necessary to monitor the various logs and metrics being produced from the servers, hosts, and the application proper.</span></span> <span data-ttu-id="fc2a0-110">클라우드 네이티브 응용 프로그램을 지원 하기 위해 실행 되는 다양 한 서비스의 수를 통해 개별 구성 요소 및 응용 프로그램의 상태를 모니터링 하는 것이 중요 한 문제입니다.</span><span class="sxs-lookup"><span data-stu-id="fc2a0-110">The number of different services running in support of a cloud-native application makes monitoring the health of individual components and the application as a whole a critical challenge.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="fc2a0-111">[이전](resilient-communications.md)
>[다음](observability-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="fc2a0-111">[Previous](resilient-communications.md)
[Next](observability-patterns.md)</span></span>
