---
title: DDD 및 CQRS 패턴을 사용하여 마이크로 서비스에서 비즈니스 복잡성 처리
description: 컨테이너화된 .NET 애플리케이션을 위한 .NET 마이크로 서비스 아키텍처 | DDD 및 CQRS 패턴을 적용하여 복잡한 비즈니스 시나리오를 처리하는 방법 이해
ms.date: 10/08/2018
ms.openlocfilehash: 88b105b68307c8587f877bb9ddf370e143d8539b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2019
ms.locfileid: "73739832"
---
# <a name="tackle-business-complexity-in-a-microservice-with-ddd-and-cqrs-patterns"></a><span data-ttu-id="02dcb-103">DDD 및 CQRS 패턴을 사용하여 마이크로 서비스에서 비즈니스 복잡성 처리</span><span class="sxs-lookup"><span data-stu-id="02dcb-103">Tackle Business Complexity in a Microservice with DDD and CQRS Patterns</span></span>

<span data-ttu-id="02dcb-104">*비즈니스 도메인에 대한 이해를 반영하는 각 마이크로 서비스 또는 제한된 컨텍스트를 위한 도메인 모델을 디자인하세요.*</span><span class="sxs-lookup"><span data-stu-id="02dcb-104">*Design a domain model for each microservice or Bounded Context that reflects understanding of the business domain.*</span></span>

<span data-ttu-id="02dcb-105">이 섹션에서는 복잡한 하위 시스템 또는 끊임없이 변화하는 비즈니스 규칙을 사용하는 도메인 전문가의 지식에서 파생된 마이크로 서비스를 처리해야 할 때 구현하는 고급 마이크로 서비스에 중점을 둡니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-105">This section focuses on more advanced microservices that you implement when you need to tackle complex subsystems, or microservices derived from the knowledge of domain experts with ever-changing business rules.</span></span> <span data-ttu-id="02dcb-106">이 섹션에서 사용된 아키텍처 패턴은 그림 7-1에 나와 있는 것처럼 DDD(도메인 기반 디자인) 및 CQRS(명령과 쿼리의 역할 분리) 접근 방식을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-106">The architecture patterns used in this section are based on domain-driven design (DDD) and Command and Query Responsibility Segregation (CQRS) approaches, as illustrated in Figure 7-1.</span></span>

<span data-ttu-id="02dcb-107">:::image type="complex" source="./media/index/internal-versus-external-architecture.png" alt-text="외부 및 내부 아키텍처 패턴을 비교하는 다이어그램입니다.":::</span><span class="sxs-lookup"><span data-stu-id="02dcb-107">:::image type="complex" source="./media/index/internal-versus-external-architecture.png" alt-text="Diagram comparing external and internal architecture patterns.":::</span></span>
<span data-ttu-id="02dcb-108">마이크로 서비스 패턴, API 게이트웨이, 복원력 있는 통신, 게시자/구독자 등의 외부 아키텍처와 데이터 기반/CRUD, DDD 패턴, 종속성 삽입, 여러 라이브러리 등의 내부 아키텍처 간 차이입니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-108">Difference between external architecture: microservice patterns, API gateways, resilient communications, pub/sub, etc., and internal architecture: data driven/CRUD, DDD patterns, dependency injection, multiple libraries, etc.</span></span>
:::image-end:::

<span data-ttu-id="02dcb-109">**그림 7-1**.</span><span class="sxs-lookup"><span data-stu-id="02dcb-109">**Figure 7-1**.</span></span> <span data-ttu-id="02dcb-110">각 마이크로 서비스에 대한 외부 마이크로 서비스 아키텍처 및 내부 아키텍처 패턴</span><span class="sxs-lookup"><span data-stu-id="02dcb-110">External microservice architecture versus internal architecture patterns for each microservice</span></span>

<span data-ttu-id="02dcb-111">그러나 ASP.NET Core Web API 서비스를 구현하는 방법 또는 Swashbuckle 또는 NSwag를 사용하여 Swagger 메타데이터를 표시하는 방법과 같은 대부분의 데이터 기반 마이크로 서비스 기술은 DDD 패턴을 사용하여 내부적으로 구현된 고급 마이크로 서비스에도 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-111">However, most of the techniques for data driven microservices, such as how to implement an ASP.NET Core Web API service or how to expose Swagger metadata with Swashbuckle or NSwag, are also applicable to the more advanced microservices implemented internally with DDD patterns.</span></span> <span data-ttu-id="02dcb-112">이 섹션은 이전 섹션의 확장입니다. 이전에 설명한 대부분의 방법이 여기 또는 모든 종류의 마이크로 서비스에도 적용되기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-112">This section is an extension of the previous sections, because most of the practices explained earlier also apply here or for any kind of microservice.</span></span>

<span data-ttu-id="02dcb-113">이 섹션에서는 먼저 eShopOnContainers 참조 애플리케이션에 사용되는 간소화된 CQRS 패턴에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-113">This section first provides details on the simplified CQRS patterns used in the eShopOnContainers reference application.</span></span> <span data-ttu-id="02dcb-114">이후에는 애플리케이션에서 다시 사용할 수 있는 일반적인 패턴을 찾을 수 있도록 지원하는 DDD 기술에 대해 간략히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-114">Later, you will get an overview of the DDD techniques that enable you to find common patterns that you can reuse in your applications.</span></span>

<span data-ttu-id="02dcb-115">DDD는 다양한 학습 리소스 집합이 있는 큰 주제입니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-115">DDD is a large topic with a rich set of resources for learning.</span></span> <span data-ttu-id="02dcb-116">Eric Evans의 [Domain-Driven Design](https://domainlanguage.com/ddd/)과 같은 서적 및 Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard와 그 밖의 여러 DDD/CQRS 전문가의 추가 자료로 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-116">You can start with books like [Domain-Driven Design](https://domainlanguage.com/ddd/) by Eric Evans and additional materials from Vaughn Vernon, Jimmy Nilsson, Greg Young, Udi Dahan, Jimmy Bogard, and many other DDD/CQRS experts.</span></span> <span data-ttu-id="02dcb-117">그러나 무엇보다도 구체적인 비즈니스 도메인 전문가와 함께 하는 대화, 화이트 보드 및 도메인 모델링 세션에서 DDD 기술을 적용하는 방법을 알아보려고 노력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02dcb-117">But most of all you need to try to learn how to apply DDD techniques from the conversations, whiteboarding, and domain modeling sessions with the experts in your concrete business domain.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="02dcb-118">추가 자료</span><span class="sxs-lookup"><span data-stu-id="02dcb-118">Additional resources</span></span>

##### <a name="ddd-domain-driven-design"></a><span data-ttu-id="02dcb-119">DDD(도메인 기반 디자인)</span><span class="sxs-lookup"><span data-stu-id="02dcb-119">DDD (Domain-Driven Design)</span></span>

- <span data-ttu-id="02dcb-120">**Eric Evans. 도메인 언어** </span><span class="sxs-lookup"><span data-stu-id="02dcb-120">**Eric Evans. Domain Language** </span></span>\
  <https://domainlanguage.com/>

- <span data-ttu-id="02dcb-121">**Martin Fowler. 도메인 기반 디자인** </span><span class="sxs-lookup"><span data-stu-id="02dcb-121">**Martin Fowler. Domain-Driven Design** </span></span>\
  <https://martinfowler.com/tags/domain%20driven%20design.html>

- <span data-ttu-id="02dcb-122">**Jimmy Bogard. 도메인 강화: 입문** </span><span class="sxs-lookup"><span data-stu-id="02dcb-122">**Jimmy Bogard. Strengthening your domain: a primer** </span></span>\
  <https://lostechies.com/jimmybogard/2010/02/04/strengthening-your-domain-a-primer/>

##### <a name="ddd-books"></a><span data-ttu-id="02dcb-123">DDD 서적</span><span class="sxs-lookup"><span data-stu-id="02dcb-123">DDD books</span></span>

- <span data-ttu-id="02dcb-124">**Eric Evans. 도메인 기반 디자인: 소프트웨어 핵심에서 복잡성 처리** </span><span class="sxs-lookup"><span data-stu-id="02dcb-124">**Eric Evans. Domain-Driven Design: Tackling Complexity in the Heart of Software** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Tackling-Complexity-Software/dp/0321125215/>

- <span data-ttu-id="02dcb-125">**Eric Evans. 도메인 기반 디자인 참조: 정의 및 패턴 요약** </span><span class="sxs-lookup"><span data-stu-id="02dcb-125">**Eric Evans. Domain-Driven Design Reference: Definitions and Pattern Summaries** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Reference-Definitions-2014-09-22/dp/B01N8YB4ZO/>

- <span data-ttu-id="02dcb-126">**Vaughn Vernon. 도메인 기반 디자인 구현** </span><span class="sxs-lookup"><span data-stu-id="02dcb-126">**Vaughn Vernon. Implementing Domain-Driven Design** </span></span>\
  <https://www.amazon.com/Implementing-Domain-Driven-Design-Vaughn-Vernon/dp/0321834577/>

- <span data-ttu-id="02dcb-127">**Vaughn Vernon. 도메인 기반 디자인 핵심 정리** </span><span class="sxs-lookup"><span data-stu-id="02dcb-127">**Vaughn Vernon. Domain-Driven Design Distilled** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Distilled-Vaughn-Vernon/dp/0134434420/>

- <span data-ttu-id="02dcb-128">**Jimmy Nilsson. 도메인 기반 디자인 및 패턴 적용** </span><span class="sxs-lookup"><span data-stu-id="02dcb-128">**Jimmy Nilsson. Applying Domain-Driven Design and Patterns** </span></span>\
  <https://www.amazon.com/Applying-Domain-Driven-Design-Patterns-Examples/dp/0321268202/>

- <span data-ttu-id="02dcb-129">**Cesar de la Torre. .NET을 사용한 N-레이어 도메인 지향 아키텍처 가이드** </span><span class="sxs-lookup"><span data-stu-id="02dcb-129">**Cesar de la Torre. N-Layered Domain-Oriented Architecture Guide with .NET** </span></span>\
  <https://www.amazon.com/N-Layered-Domain-Oriented-Architecture-Guide-NET/dp/8493903612/>

- <span data-ttu-id="02dcb-130">**Abel Avram 및 Floyd Marinescu. 신속한 도메인 기반 디자인** </span><span class="sxs-lookup"><span data-stu-id="02dcb-130">**Abel Avram and Floyd Marinescu. Domain-Driven Design Quickly** </span></span>\
  <https://www.amazon.com/Domain-Driven-Design-Quickly-Abel-Avram/dp/1411609255/>

- <span data-ttu-id="02dcb-131">**Scott Millett, Nick Tune - 도메인 기반 디자인의 패턴, 원칙 및 사례** </span><span class="sxs-lookup"><span data-stu-id="02dcb-131">**Scott Millett, Nick Tune - Patterns, Principles, and Practices of Domain-Driven Design** </span></span>\
  <http://www.wrox.com/WileyCDA/WroxTitle/Patterns-Principles-and-Practices-of-Domain-Driven-Design.productCd-1118714709.html>

##### <a name="ddd-training"></a><span data-ttu-id="02dcb-132">DDD 교육</span><span class="sxs-lookup"><span data-stu-id="02dcb-132">DDD training</span></span>

- <span data-ttu-id="02dcb-133">**Julie Lerman 및 Steve Smith. 도메인 기반 디자인 기본 사항** </span><span class="sxs-lookup"><span data-stu-id="02dcb-133">**Julie Lerman and Steve Smith. Domain-Driven Design Fundamentals** </span></span>\
  <https://bit.ly/PS-DDD>

>[!div class="step-by-step"]
><span data-ttu-id="02dcb-134">[이전](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
>[다음](apply-simplified-microservice-cqrs-ddd-patterns.md)</span><span class="sxs-lookup"><span data-stu-id="02dcb-134">[Previous](../multi-container-microservice-net-applications/implement-api-gateways-with-ocelot.md)
[Next](apply-simplified-microservice-cqrs-ddd-patterns.md)</span></span>
