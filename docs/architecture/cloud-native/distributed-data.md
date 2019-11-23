---
title: 분산 데이터
description: Azure 용 클라우드 네이티브 .NET 앱 설계 | 클라우드 네이티브 앱에 대 한 분산 데이터
ms.date: 06/30/2019
ms.openlocfilehash: b715ae5203264a023bc9f911aa74ee222afe3d68
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73841812"
---
# <a name="distributed-data-for-cloud-native-apps"></a><span data-ttu-id="86c8c-103">클라우드 네이티브 앱에 대 한 분산 데이터</span><span class="sxs-lookup"><span data-stu-id="86c8c-103">Distributed data for cloud-native apps</span></span>

[!INCLUDE [book-preview](../../../includes/book-preview.md)]

<span data-ttu-id="86c8c-104">많은 독립적인 마이크로 서비스로 구성 된 클라우드 네이티브 시스템을 구성할 때 데이터 저장소 변경에 대해 생각 하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-104">When constructing a cloud-native system that consists of many independent microservices, the way you think about data storage changes.</span></span>

<span data-ttu-id="86c8c-105">기존 모놀리식 응용 프로그램은 그림 5-1에 나와 있는 중앙 집중화 된 데이터 저장소를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-105">Traditional monolithic applications favor a centralized data store shown in Figure 5-1.</span></span>

![단일 모놀리식 데이터베이스](./media/single-monolithic-database.png)

<span data-ttu-id="86c8c-107">**그림 5-1**.</span><span class="sxs-lookup"><span data-stu-id="86c8c-107">**Figure 5-1**.</span></span> <span data-ttu-id="86c8c-108">단일 모놀리식 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="86c8c-108">Single monolithic database</span></span>

<span data-ttu-id="86c8c-109">위의 그림에서는 모든 응용 프로그램 구성 요소가 단일 관계형 데이터베이스를 사용 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-109">Note in the previous figure how all of the application components consume a single relational database.</span></span>

<span data-ttu-id="86c8c-110">이 방법에는 여러 가지 이점이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-110">There are many benefits to this approach.</span></span> <span data-ttu-id="86c8c-111">여러 테이블에 분산 된 데이터를 쿼리 하는 것은 간단 하며 데이터 일관성을 보장 하는 [ACID 트랜잭션을](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) 구현 하는 것이 간단 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-111">It's straightforward to query data spread across  multiple tables, and it's straightforward to implement [ACID transactions](https://docs.microsoft.com/windows/desktop/cossdk/acid-properties) that ensure data consistency.</span></span> <span data-ttu-id="86c8c-112">항상 *즉시 일관성을 유지*합니다. 모든 데이터 업데이트 또는 모든 데이터 업데이트 중 하나가 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-112">You always end up with *immediate consistency*: either all your data updates or none of it does.</span></span>

<span data-ttu-id="86c8c-113">클라우드 기본 시스템은 각 마이크로 서비스 자신의 데이터를 소유 하 고 캡슐화 하는 그림 5-2에 표시 된 데이터 아키텍처를 선호 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-113">Cloud-native systems favor a data architecture shown in Figure 5-2 in which each microservice owns and encapsulates its own data.</span></span>

![마이크로 서비스에서 여러 데이터베이스](./media/data-across-microservices.png)

<span data-ttu-id="86c8c-115">**그림 5-2**.</span><span class="sxs-lookup"><span data-stu-id="86c8c-115">**Figure 5-2**.</span></span> <span data-ttu-id="86c8c-116">마이크로 서비스에서 여러 데이터베이스</span><span class="sxs-lookup"><span data-stu-id="86c8c-116">Multiple databases across microservices</span></span>

<span data-ttu-id="86c8c-117">위의 그림에서 각 마이크로 서비스는 it 데이터 저장소를 소유 및 캡슐화 하 고 공용 API에서 외부 지역에만 데이터를 노출 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-117">Note how in the previous figure each microservice owns and encapsulates it data store and only exposes data to the outside world from its public API.</span></span>

<span data-ttu-id="86c8c-118">이 모델을 사용 하면 다른 마이크로 서비스와 데이터 스키마 변경을 조정 하지 않고도 각 마이크로 서비스이 독립적으로 발전할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-118">This model enables each microservice to evolve independently without having to coordinate data schema changes with other microservices.</span></span> <span data-ttu-id="86c8c-119">각 마이크로 서비스는 요구 사항에 가장 부합 하는 데이터 저장소 (관계형 데이터베이스, 문서 데이터베이스, 키-값 저장소) 형식을 자유롭게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-119">Each microservice is free to implement the data store (relational database, document database, key-value store) type that best matches its needs.</span></span> <span data-ttu-id="86c8c-120">런타임에 각 마이크로 서비스는 해당 데이터를 적절 하 게 확장할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-120">At runtime, each microservice can scale its data accordingly.</span></span> <span data-ttu-id="86c8c-121">이는 그림 5-3에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-121">This is shown in Figure 5-3:</span></span>

![Polyglot 데이터 지 속성](./media/polyglot-data-persistence.png)

<span data-ttu-id="86c8c-123">**그림 5-3**.</span><span class="sxs-lookup"><span data-stu-id="86c8c-123">**Figure 5-3**.</span></span> <span data-ttu-id="86c8c-124">Polyglot 데이터 지 속성</span><span class="sxs-lookup"><span data-stu-id="86c8c-124">Polyglot data persistence</span></span>

<span data-ttu-id="86c8c-125">이전 그림에서 제품 카탈로그 및 인벤토리 마이크로 서비스는 관계형 데이터베이스, 주문 마이크로 서비스, NoSql 문서 데이터베이스, 쇼핑 카트 마이크로 서비스 (외부 키-값 저장소)를 채택 하는 방법에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="86c8c-125">Note how in the previous figure the product catalog and inventory microservices adopt relational databases, the ordering microservice, a NoSql document database, and the shopping cart microservice, which is an external key-value store.</span></span> <span data-ttu-id="86c8c-126">관계형 데이터베이스는 복잡 한 데이터를 포함 하는 마이크로 서비스에 대 한 관련성을 유지 하지만 NoSQL 데이터베이스는 뛰어난 인기를 제공 하 여 적응성, 빠른 조회 및 고가용성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-126">While relational databases remain relevant for microservices with complex data, NoSQL databases have gained considerable popularity, providing adaptability, fast lookup, and high availability.</span></span> <span data-ttu-id="86c8c-127">이러한 특성을 사용 하면 개발자는 형식화 된 데이터 클래스의 아키텍처에서 벗어나 서 비용이 많이 들고 시간이 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="86c8c-127">Their schemaless nature allows developers to move away from an architecture of typed data classes and ORMs that make change expensive and time-consuming.</span></span>

>[!div class="step-by-step"]
><span data-ttu-id="86c8c-128">[이전](service-mesh-communication-infrastructure.md)
>[다음](data-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="86c8c-128">[Previous](service-mesh-communication-infrastructure.md)
[Next](data-patterns.md)</span></span>
