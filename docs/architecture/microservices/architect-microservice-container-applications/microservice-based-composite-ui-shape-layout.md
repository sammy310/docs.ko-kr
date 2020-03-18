---
title: 마이크로 서비스 기반 복합 UI 만들기
description: 마이크로 서비스 아키텍처 백 엔드에 대해서만은 아닙니다. 프런트 엔드에서 사용하는 Peek 뷰를 가져옵니다.
ms.date: 09/20/2018
ms.openlocfilehash: 1861d3bb6e5d4a0226aa8f3f72a2e0d3e83be56f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "72275732"
---
# <a name="creating-composite-ui-based-on-microservices"></a><span data-ttu-id="ae3ee-104">마이크로 서비스 기반 복합 UI 만들기</span><span class="sxs-lookup"><span data-stu-id="ae3ee-104">Creating composite UI based on microservices</span></span>

<span data-ttu-id="ae3ee-105">마이크로 서비스 아키텍처는 서버 쪽에서 데이터 및 논리를 처리하기 시작하지만, 많은 경우 UI는 여전히 모놀리식으로 처리됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-105">Microservices architecture often starts with the server-side handling data and logic, but, in many cases, the UI is still handled as a monolith.</span></span> <span data-ttu-id="ae3ee-106">그러나 [마이크로 프런트 엔드](https://martinfowler.com/articles/micro-frontends.html)라는 고급 방법은 마이크로 서비스에 따라 애플리케이션 UI를 디자인하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-106">However, a more advanced approach, called [micro frontends](https://martinfowler.com/articles/micro-frontends.html), is to design your application UI based on microservices as well.</span></span> <span data-ttu-id="ae3ee-107">즉, 서버에 마이크로 서비스를 배치하고 모놀리식 클라이언트 앱이 마이크로 서비스를 사용하는 대신 마이크로 서비스에서 생성되는 복합 UI가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-107">That means having a composite UI produced by the microservices, instead of having microservices on the server and just a monolithic client app consuming the microservices.</span></span> <span data-ttu-id="ae3ee-108">이 방법으로 마이크로 서비스는 논리 및 시각적 표현 모두를 사용하여 완료될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-108">With this approach, the microservices you build can be complete with both logic and visual representation.</span></span>

<span data-ttu-id="ae3ee-109">그림 4-20에서는 모놀리식 클라이언트 애플리케이션에서 마이크로 서비스를 사용하는 간단한 방법을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-109">Figure 4-20 shows the simpler approach of just consuming microservices from a monolithic client application.</span></span> <span data-ttu-id="ae3ee-110">물론 HTML 및 JavaScript를 생성하면 ASP.NET MVC 서비스가 생성될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-110">Of course, you could have an ASP.NET MVC service in between producing the HTML and JavaScript.</span></span> <span data-ttu-id="ae3ee-111">그림은 마이크로 서비스를 사용하는 단일(모놀리식) 클라이언트 UI가 있음을 간단히 강조 표시합니다. 여기서는 UI 셰이프(HTML 및 JavaScript)가 아니라 논리 및 데이터에만 집중합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-111">The figure is a simplification that highlights that you have a single (monolithic) client UI consuming the microservices, which just focus on logic and data and not on the UI shape (HTML and JavaScript).</span></span>

![마이크로 서비스에 연결하는 모놀리식 UI 앱의 다이어그램입니다.](./media/microservice-based-composite-ui-shape-layout/monolith-ui-consume-microservices.png)

<span data-ttu-id="ae3ee-113">**그림 4-20**.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-113">**Figure 4-20**.</span></span> <span data-ttu-id="ae3ee-114">백 엔드 마이크로 서비스를 소비하는 모놀리식 UI 애플리케이션</span><span class="sxs-lookup"><span data-stu-id="ae3ee-114">A monolithic UI application consuming back-end microservices</span></span>

<span data-ttu-id="ae3ee-115">반면, 복합 UI는 정확하게 마이크로 서비스 자체에서 생성하고 구성했습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-115">In contrast, a composite UI is precisely generated and composed by the microservices themselves.</span></span> <span data-ttu-id="ae3ee-116">일부 마이크로 서비스는 UI 특정 영역의 시각적 셰이프를 제어합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-116">Some of the microservices drive the visual shape of specific areas of the UI.</span></span> <span data-ttu-id="ae3ee-117">주요 차이는 템플릿에 기반한 클라이언트 UI 구성 요소(예: TypeScript 클래스)가 있으며 해당 템플릿에 대한 data-shaping-UI ViewModel이 각 마이크로 서비스에서 제공된다는 점입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-117">The key difference is that you have client UI components (TypeScript classes, for example) based on templates, and the data-shaping-UI ViewModel for those templates comes from each microservice.</span></span>

<span data-ttu-id="ae3ee-118">클라이언트 애플리케이션 시작 시 클라이언트 UI 구성 요소(예: TypeScript 클래스)는 각각 지정된 시나리오에 ViewModels를 제공하는 인프라 마이크로 서비스를 사용하여 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-118">At client application start-up time, each of the client UI components (TypeScript classes, for example) registers itself with an infrastructure microservice capable of providing ViewModels for a given scenario.</span></span> <span data-ttu-id="ae3ee-119">마이크로 서비스가 모양을 변경하면 UI도 변경됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-119">If the microservice changes the shape, the UI changes also.</span></span>

<span data-ttu-id="ae3ee-120">그림 4-21은 복합 UI 방법의 버전을 보여줍니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-120">Figure 4-21 shows a version of this composite UI approach.</span></span> <span data-ttu-id="ae3ee-121">다양한 기법을 기반으로 세분화된 부분을 집계하는 다른 마이크로 서비스가 있기 때문에 이러한 작업이 간소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-121">This is simplified because you might have other microservices that are aggregating granular parts that are based on different techniques.</span></span> <span data-ttu-id="ae3ee-122">기존 웹 접근 방식(ASP.NET MVC) 또는 SPA(단일 페이지 애플리케이션)를 빌드하는 여부에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-122">It depends on whether you're building a traditional web approach (ASP.NET MVC) or an SPA (Single Page Application).</span></span>

![많은 뷰 모델로 구성된 복합 UI의 다이어그램입니다.](./media/microservice-based-composite-ui-shape-layout/microservice-generate-composite-ui.png)

<span data-ttu-id="ae3ee-124">**그림 4-21**.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-124">**Figure 4-21**.</span></span> <span data-ttu-id="ae3ee-125">백 엔드 마이크로 서비스에서 셰이프된 복합 UI 애플리케이션 예제</span><span class="sxs-lookup"><span data-stu-id="ae3ee-125">Example of a composite UI application shaped by back-end microservices</span></span>

<span data-ttu-id="ae3ee-126">해당 UI 컴퍼지션 마이크로 서비스는 각각 작은 API 게이트웨이와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-126">Each of those UI composition microservices would be similar to a small API Gateway.</span></span> <span data-ttu-id="ae3ee-127">그러나 이 경우에는 각각은 작은 UI 영역을 담당합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-127">But in this case, each one is responsible for a small UI area.</span></span>

<span data-ttu-id="ae3ee-128">따라서 마이크로 서비스에서 제어하는 복합 UI 방법은 사용중인 UI 기술에 따라 더 어렵거나 쉬워질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-128">A composite UI approach that's driven by microservices can be more challenging or less so, depending on what UI technologies you're using.</span></span> <span data-ttu-id="ae3ee-129">예를 들어, SPA 혹은 네이티브 모바일 앱을 빌드하기 위해 기존 웹 애플리케이션을 빌드하는 동일한 기술을 사용하지 않습니다(Xamarin 앱을 개발하는 경우 마찬가지로 이 방법이 좀 더 어려울 수 있음).</span><span class="sxs-lookup"><span data-stu-id="ae3ee-129">For instance, you won't use the same techniques for building a traditional web application that you use for building an SPA or for native mobile app (as when developing Xamarin apps, which can be more challenging for this approach).</span></span>

<span data-ttu-id="ae3ee-130">[eShopOnContainers](https://aka.ms/MicroservicesArchitecture) 애플리케이션 예제는 여러 가지 이유로 모놀리식 UI 방법을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-130">The [eShopOnContainers](https://aka.ms/MicroservicesArchitecture) sample application uses the monolithic UI approach for multiple reasons.</span></span> <span data-ttu-id="ae3ee-131">먼저 마이크로 서비스 및 컨테이너에 대한 소개입니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-131">First, it's an introduction to microservices and containers.</span></span> <span data-ttu-id="ae3ee-132">UI를 디자인하고 개발하는 경우 복합 UI를 사용하는 것이 고급 기능이지만 더 복잡합니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-132">A composite UI is more advanced but also requires further complexity when designing and developing the UI.</span></span> <span data-ttu-id="ae3ee-133">다음으로 eShopOnContainers는 Xamarin에 기반한 기본 모바일 앱을 제공합니다. 그러면 클라이언트 C\#에서 더 복잡해 집니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-133">Second, eShopOnContainers also provides a native mobile app based on Xamarin, which would make it more complex on the client C\# side.</span></span>

<span data-ttu-id="ae3ee-134">그러나 다음 참조를 사용하여 마이크로 서비스를 기반으로 하는 복합 UI에 대해 자세히 알아봅니다.</span><span class="sxs-lookup"><span data-stu-id="ae3ee-134">However, we encourage you to use the following references to learn more about composite UI based on microservices.</span></span>

## <a name="additional-resources"></a><span data-ttu-id="ae3ee-135">추가 자료</span><span class="sxs-lookup"><span data-stu-id="ae3ee-135">Additional resources</span></span>

- <span data-ttu-id="ae3ee-136">**마이크로 프런트 엔드(Martin Fowler의 블로그)**</span><span class="sxs-lookup"><span data-stu-id="ae3ee-136">**Micro Frontends (Martin Fowler's blog)**</span></span>  
  <https://martinfowler.com/articles/micro-frontends.html>
  
- <span data-ttu-id="ae3ee-137">**마이크로 프런트 엔드(Michael Geers 사이트)**</span><span class="sxs-lookup"><span data-stu-id="ae3ee-137">**Micro Frontends (Michael Geers site)**</span></span>  
  <https://micro-frontends.org/>
  
- <span data-ttu-id="ae3ee-138">**ASP.NET을 사용한 복합 UI(특정 워크샵)**</span><span class="sxs-lookup"><span data-stu-id="ae3ee-138">**Composite UI using ASP.NET (Particular's Workshop)**</span></span>  
  <https://github.com/Particular/Workshop/tree/master/demos/asp-net-core>

- <span data-ttu-id="ae3ee-139">**Ruben Oostinga 마이크로 서비스 아키텍처의 모놀리식 프런트 엔드**</span><span class="sxs-lookup"><span data-stu-id="ae3ee-139">**Ruben Oostinga. The Monolithic Frontend in the Microservices Architecture**</span></span>  
  <https://xebia.com/blog/the-monolithic-frontend-in-the-microservices-architecture/>

- <span data-ttu-id="ae3ee-140">**Mauro Servienti 뛰어난 UI 구성의 비밀**</span><span class="sxs-lookup"><span data-stu-id="ae3ee-140">**Mauro Servienti. The secret of better UI composition**</span></span>  
  <https://particular.net/blog/secret-of-better-ui-composition>

- <span data-ttu-id="ae3ee-141">**Viktor Farcic 마이크로 서비스에 프런트 엔드 웹 구성 요소 포함하기**</span><span class="sxs-lookup"><span data-stu-id="ae3ee-141">**Viktor Farcic. Including Front-End Web Components Into Microservices**</span></span>  
  <https://technologyconversations.com/2015/08/09/including-front-end-web-components-into-microservices/>

- <span data-ttu-id="ae3ee-142">**마이크로 서비스 아키텍처에서 프런트 엔드 관리**</span><span class="sxs-lookup"><span data-stu-id="ae3ee-142">**Managing Frontend in the Microservices Architecture**</span></span>  
  <https://allegro.tech/2016/03/Managing-Frontend-in-the-microservices-architecture.html>

>[!div class="step-by-step"]
><span data-ttu-id="ae3ee-143">[이전](microservices-addressability-service-registry.md)
>[다음](resilient-high-availability-microservices.md)</span><span class="sxs-lookup"><span data-stu-id="ae3ee-143">[Previous](microservices-addressability-service-registry.md)
[Next](resilient-high-availability-microservices.md)</span></span>
