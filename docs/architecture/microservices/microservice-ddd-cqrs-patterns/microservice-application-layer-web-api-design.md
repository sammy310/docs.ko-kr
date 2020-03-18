---
title: 마이크로 서비스 애플리케이션 레이어 및 웹 API 설계
description: 컨테이너화된 .NET 애플리케이션을 위한 .NET 마이크로 서비스 아키텍처 | 애플리케이션 계층 설계를 위한 SOLID 원칙의 간략한 설명
ms.date: 10/08/2018
ms.openlocfilehash: 3c3b9f74e76e01deafa1f97de5d3250d57716014
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "68676520"
---
# <a name="design-the-microservice-application-layer-and-web-api"></a><span data-ttu-id="692bc-103">마이크로 서비스 애플리케이션 계층 및 웹 API 설계하기</span><span class="sxs-lookup"><span data-stu-id="692bc-103">Design the microservice application layer and Web API</span></span>

## <a name="use-solid-principles-and-dependency-injection"></a><span data-ttu-id="692bc-104">SOLID 원칙 및 종속성 주입 사용하기</span><span class="sxs-lookup"><span data-stu-id="692bc-104">Use SOLID principles and Dependency Injection</span></span>

<span data-ttu-id="692bc-105">SOLID 원칙은 DDD 패턴을 통한 마이크로 서비스 개발처럼 현대적인 필수 애플리케이션에서 사용되는 중요한 기법입니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-105">SOLID principles are critical techniques to be used in any modern and mission-critical application, such as developing a microservice with DDD patterns.</span></span> <span data-ttu-id="692bc-106">SOLID는 5가지 기본 원칙을 묶은 머리글자어입니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-106">SOLID is an acronym that groups five fundamental principles:</span></span>

- <span data-ttu-id="692bc-107">Single Responsibility(단일 책임) 원칙</span><span class="sxs-lookup"><span data-stu-id="692bc-107">Single Responsibility principle</span></span>

- <span data-ttu-id="692bc-108">Open/closed(개방/폐쇄) 원칙</span><span class="sxs-lookup"><span data-stu-id="692bc-108">Open/closed principle</span></span>

- <span data-ttu-id="692bc-109">Liskov 대체 원칙</span><span class="sxs-lookup"><span data-stu-id="692bc-109">Liskov substitution principle</span></span>

- <span data-ttu-id="692bc-110">Interface Segregation(인터페이스 분리) 원칙</span><span class="sxs-lookup"><span data-stu-id="692bc-110">Interface Segregation principle</span></span>

- <span data-ttu-id="692bc-111">Dependency Inversion(종속성 반전) 원칙</span><span class="sxs-lookup"><span data-stu-id="692bc-111">Dependency Inversion principle</span></span>

<span data-ttu-id="692bc-112">SOLID는 애플리케이션 또는 마이크로 서비스 내부 계층을 설계하는 방식과 계층 간의 종속성을 분리하는 방법에 관한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-112">SOLID is more about how you design your application or microservice internal layers and about decoupling dependencies between them.</span></span> <span data-ttu-id="692bc-113">도메인이 아니라 애플리케이션의 기술적 설계와 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-113">It is not related to the domain, but to the application’s technical design.</span></span> <span data-ttu-id="692bc-114">마지막 원칙인 종속성 반전 원칙에서는 인프라 계층을 나머지 계층과 분리하여 DDD 계층의 분리 구현을 향상할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-114">The final principle, the Dependency Inversion principle, allows you to decouple the infrastructure layer from the rest of the layers, which allows a better decoupled implementation of the DDD layers.</span></span>

<span data-ttu-id="692bc-115">DI(종속성 주입)는 종속성 반전 원칙을 구현하는 한 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-115">Dependency Injection (DI) is one way to implement the Dependency Inversion principle.</span></span> <span data-ttu-id="692bc-116">개체와 그 종속성 간의 느슨한 결합을 실현하기 위한 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-116">It is a technique for achieving loose coupling between objects and their dependencies.</span></span> <span data-ttu-id="692bc-117">협력자를 직접 인스턴스화하거나 고정 참조를 사용(즉, 새로 만들기 사용)하는 대신 클래스가 해당 작업을 수행하기 위해 필요한 개체를 클래스에 제공(또는 "주입")합니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-117">Rather than directly instantiating collaborators, or using static references (that is, using new…), the objects that a class needs in order to perform its actions are provided to (or "injected into") the class.</span></span> <span data-ttu-id="692bc-118">대부분의 경우 클래스는 해당 생성자를 통해 해당 종속성을 선언하게 되며 명시적 종속성 원칙을 따르도록 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-118">Most often, classes will declare their dependencies via their constructor, allowing them to follow the Explicit Dependencies principle.</span></span> <span data-ttu-id="692bc-119">종속성 주입은 일반적으로 특정 IoC(Inversion of Control) 컨테이너를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-119">Dependency Injection is usually based on specific Inversion of Control (IoC) containers.</span></span> <span data-ttu-id="692bc-120">ASP.NET Core에는 간단한 기본 제공 IoC가 있지만 Autofac 또는 Ninject처럼 사용자가 원하는 IoC 컨테이너를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-120">ASP.NET Core provides a simple built-in IoC container, but you can also use your favorite IoC container, like Autofac or Ninject.</span></span>

<span data-ttu-id="692bc-121">SOLID 원칙에 따르면 클래스는 당연히 작고 잘 구성되며 쉽게 테스트됩니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-121">By following the SOLID principles, your classes will tend naturally to be small, well-factored, and easily tested.</span></span> <span data-ttu-id="692bc-122">그러나 클래스에 너무 많은 종속성이 주입된 것을 어떻게 알 수 있을까요?</span><span class="sxs-lookup"><span data-stu-id="692bc-122">But how can you know if too many dependencies are being injected into your classes?</span></span> <span data-ttu-id="692bc-123">생성자를 통해 DI를 사용할 경우 생성자에 대한 매개 변수 수를 살피기만 해도 이를 쉽게 감지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-123">If you use DI through the constructor, it will be easy to detect that by just looking at the number of parameters for your constructor.</span></span> <span data-ttu-id="692bc-124">종속성이 너무 많은 경우 이는 일반적으로 클래스가 너무 많은 작업을 시도하고 있으며 아마도 SRP([단일 책임 원칙](https://deviq.com/code-smells/))를 위반하고 있다는 신호입니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-124">If there are too many dependencies, this is generally a sign (a [code smell](https://deviq.com/code-smells/)) that your class is trying to do too much, and is probably violating the Single Responsibility principle.</span></span>

<span data-ttu-id="692bc-125">SOLID에 대해서는 다른 가이드에서 자세히 다룰 것입니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-125">It would take another guide to cover SOLID in detail.</span></span> <span data-ttu-id="692bc-126">따라서 이 가이드에서는 이 항목에 대한 최소한의 지식만 요구합니다.</span><span class="sxs-lookup"><span data-stu-id="692bc-126">Therefore, this guide requires you to have only a minimum knowledge of these topics.</span></span>

#### <a name="additional-resources"></a><span data-ttu-id="692bc-127">추가 자료</span><span class="sxs-lookup"><span data-stu-id="692bc-127">Additional resources</span></span>

- <span data-ttu-id="692bc-128">**SOLID: 기본 OOP 원칙** </span><span class="sxs-lookup"><span data-stu-id="692bc-128">**SOLID: Fundamental OOP Principles** </span></span>\
  <https://deviq.com/solid/>

- <span data-ttu-id="692bc-129">**Inversion of Control 컨테이너 및 종속성 주입 패턴** </span><span class="sxs-lookup"><span data-stu-id="692bc-129">**Inversion of Control Containers and the Dependency Injection pattern** </span></span>\
  <https://martinfowler.com/articles/injection.html>

- <span data-ttu-id="692bc-130">**Steve Smith. 새 항목은 붙이기 입니다** </span><span class="sxs-lookup"><span data-stu-id="692bc-130">**Steve Smith. New is Glue** </span></span>\
  <https://ardalis.com/new-is-glue>

> [!div class="step-by-step"]
> <span data-ttu-id="692bc-131">[이전](nosql-database-persistence-infrastructure.md)
> [다음](microservice-application-layer-implementation-web-api.md)</span><span class="sxs-lookup"><span data-stu-id="692bc-131">[Previous](nosql-database-persistence-infrastructure.md)
[Next](microservice-application-layer-implementation-web-api.md)</span></span>
