---
title: SOA 애플리케이션
description: 컨테이너는 SOA 애플리케이션을 배포하는 유용한 옵션이기도 합니다.
ms.date: 02/15/2019
ms.openlocfilehash: aa56ada7b14a465fb3dafd02b03b815782ac765b
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "68672360"
---
# <a name="service-oriented-applications"></a><span data-ttu-id="70d7a-103">서비스 지향 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="70d7a-103">Service-oriented applications</span></span>

<span data-ttu-id="70d7a-104">SOA(서비스 지향 아키텍처)라는 용어는 사람들 사이에서 여러 의미로 남용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="70d7a-104">Service-Oriented Architecture (SOA) was an overused term that meant many different things to different people.</span></span> <span data-ttu-id="70d7a-105">하지만 한 가지 공통 분모가 있으니, SOA는 애플리케이션을 하위 시스템 또는 계층 같은 다양한 유형으로 분류할 수 있는 여러 서비스(가장 일반적인 것은 HTTP 서비스)로 분해하여 애플리케이션 아키텍처를 만든다는 것을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="70d7a-105">But as a common denominator, SOA means that you structure the architecture of your application by decomposing it into several services (most commonly as HTTP services) that can be classified in different types like subsystems or, in other cases, as tiers.</span></span>

<span data-ttu-id="70d7a-106">현재는 이러한 서비스를 Docker 컨테이너로 배포할 수 있으며, 따라서 모든 종속성이 컨테이너 이미지에 포함되므로 배포 관련 이슈가 해결됩니다.</span><span class="sxs-lookup"><span data-stu-id="70d7a-106">Today, you can deploy those services as Docker containers, which solve deployment-related issues because all of the dependencies are included in the container image.</span></span> <span data-ttu-id="70d7a-107">그러나 SOA를 확장해야 하는데 단일 인스턴스를 기반으로 배포하려는 경우 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d7a-107">However, when you need to scale out SOAs, you might encounter challenges if you're deploying based on single instances.</span></span> <span data-ttu-id="70d7a-108">이 문제는 Docker 클러스터링 소프트웨어 또는 오케스트레이터를 사용하여 해결할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d7a-108">This challenge can be handled using Docker clustering software or an orchestrator.</span></span> <span data-ttu-id="70d7a-109">다음 섹션에서 마이크로서비스 접근 방식을 살펴볼 때 오케스트레이터에 대해 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="70d7a-109">We'll look at orchestrators in greater detail in the next section, when we explore microservices approaches.</span></span>

<span data-ttu-id="70d7a-110">Docker 컨테이너는 기존의 서비스 지향 아키텍처와 보다 발전된 마이크로 서비스 아키텍처 모두에 유용합니다(하지만 필수는 아님).</span><span class="sxs-lookup"><span data-stu-id="70d7a-110">Docker containers are useful (but not required) for both traditional service-oriented architectures and the more advanced microservices architectures.</span></span>

<span data-ttu-id="70d7a-111">결국 가장 중요한 것은, 컨테이너 클러스터링 솔루션은 기존의 SOA 아키텍처와 각 마이크로서비스가 자체 데이터 모델을 소유하는 고급 마이크로서비스 아키텍처 둘 다에 유용하다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="70d7a-111">At the end of the day, the container clustering solutions are useful for both a traditional SOA architecture and for a more advanced microservices architecture in which each microservice owns its data model.</span></span> <span data-ttu-id="70d7a-112">또한 여러 데이터베이스가 있기 때문에 SOA 서비스에서 공유하는 모놀리식 데이터베이스를 사용하는 대신 데이터 계층을 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70d7a-112">And thanks to multiple databases, you also can scale out the data tier instead of working with monolithic databases shared by the SOA services.</span></span> <span data-ttu-id="70d7a-113">하지만 데이터 분할에 대한 내용은 순전히 아키텍처와 디자인에 대해서만 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="70d7a-113">However, the discussion about splitting the data is purely about architecture and design.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="70d7a-114">[이전](state-and-data-in-docker-applications.md)
>[다음](orchestrate-high-scalability-availability.md)</span><span class="sxs-lookup"><span data-stu-id="70d7a-114">[Previous](state-and-data-in-docker-applications.md)
[Next](orchestrate-high-scalability-availability.md)</span></span>
