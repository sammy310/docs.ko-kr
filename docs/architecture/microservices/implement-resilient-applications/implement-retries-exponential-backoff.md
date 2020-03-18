---
title: 지수 백오프를 사용하여 다시 시도 구현
description: 지수 백오프를 사용하여 다시 시도를 구현하는 방법을 알아봅니다.
ms.date: 10/16/2018
ms.openlocfilehash: 1b948e399495eeb12016006442ac08d2b04f2e69
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "68674540"
---
# <a name="implement-retries-with-exponential-backoff"></a><span data-ttu-id="c68c9-103">지수 백오프를 사용하여 다시 시도 구현</span><span class="sxs-lookup"><span data-stu-id="c68c9-103">Implement retries with exponential backoff</span></span>

<span data-ttu-id="c68c9-104">[‘지수 백오프를 사용하여 다시 시도’](/azure/architecture/patterns/retry)는 최대 다시 시도 횟수에 도달할 때까지 대기 시간이 기하급수적으로 증가하면서 작업을 다시 시도하는 기술입니다([지수 백오프](https://en.wikipedia.org/wiki/Exponential_backoff)). </span><span class="sxs-lookup"><span data-stu-id="c68c9-104">[*Retries with exponential backoff*](/azure/architecture/patterns/retry) is a technique that retries an operation, with an exponentially increasing wait time, up to a maximum retry count has been reached (the [exponential backoff](https://en.wikipedia.org/wiki/Exponential_backoff)).</span></span> <span data-ttu-id="c68c9-105">이 기술은 클라우드 리소스가 어떤 이유로든 몇 초간 일시적으로 사용할 수 없다는 팩트를 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="c68c9-105">This technique embraces the fact that cloud resources might intermittently be unavailable for more than a few seconds for any reason.</span></span> <span data-ttu-id="c68c9-106">예를 들어 오케스트레이터는 클러스터에서 부하 분산을 위해 컨테이너를 다른 노드로 이동할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c68c9-106">For example, an orchestrator might be moving a container to another node in a cluster for load balancing.</span></span> <span data-ttu-id="c68c9-107">이 시간 동안 일부 요청이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c68c9-107">During that time, some requests might fail.</span></span> <span data-ttu-id="c68c9-108">또 다른 예로 SQL Azure와 같은 데이터베이스를 들 수 있습니다. SQL Azure에서는 부하 분산을 위해 데이터베이스를 다른 서버로 옮길 수 있으므로 데이터베이스를 몇 초간 사용할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c68c9-108">Another example could be a database like SQL Azure, where a database can be moved to another server for load balancing, causing the database to be unavailable for a few seconds.</span></span>

<span data-ttu-id="c68c9-109">지수 백오프를 사용하여 다시 시도 논리를 구현하는 많은 방법이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c68c9-109">There are many approaches to implement retries logic with exponential backoff.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="c68c9-110">[이전](partial-failure-strategies.md)
>[다음](implement-resilient-entity-framework-core-sql-connections.md)</span><span class="sxs-lookup"><span data-stu-id="c68c9-110">[Previous](partial-failure-strategies.md)
[Next](implement-resilient-entity-framework-core-sql-connections.md)</span></span>
