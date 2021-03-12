---
title: Dapr이 배포되어 있습니다.
description: D 4의 용도, 수행 하는 방법 및 작동 방식에 대 한 개략적인 개요입니다.
author: robvet
ms.date: 02/07/2021
ms.openlocfilehash: f0efb4652aaa35961d59979cb561941e5280a575
ms.sourcegitcommit: 46cfed35d79d70e08c313b9c664c7e76babab39e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/10/2021
ms.locfileid: "102604751"
---
# <a name="dapr-at-20000-feet"></a><span data-ttu-id="6d41e-103">Dapr이 배포되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-103">Dapr at 20,000 feet</span></span>

<span data-ttu-id="6d41e-104">1 장에서는 분산 마이크로 서비스 응용 프로그램에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-104">In chapter 1, we discussed the appeal of distributed microservice applications.</span></span> <span data-ttu-id="6d41e-105">그러나 아키텍처와 운영 복잡성이 크게 증가 한다는 것을 지적 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-105">But, we also pointed out that they dramatically increase architectural and operational complexity.</span></span> <span data-ttu-id="6d41e-106">이를 염두에 두면이 질문은 어떻게 "케이크를 사용 하 고 있나요?"를 어떻게 할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="6d41e-106">With that in mind, the question becomes, how can you "have your cake" and "eat it too?".</span></span> <span data-ttu-id="6d41e-107">즉, 분산 아키텍처의 민첩성을 활용 하 고 복잡성을 최소화 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="6d41e-107">That is, how can you take advantage of the agility of distributed architecture, and minimize its complexity?</span></span>

<span data-ttu-id="6d41e-108">Eapr 또는 *Distributed Application Runtime* 은 최신 분산 응용 프로그램을 빌드하는 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-108">Dapr, or *Distributed Application Runtime*, is a new way to build modern distributed applications.</span></span>

<span data-ttu-id="6d41e-109">프로토타입에서 시작 되는 항목은 매우 성공적인 오픈 소스 프로젝트로 발전 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-109">What started as a prototype has evolved into a highly successful open-source project.</span></span> <span data-ttu-id="6d41e-110">Microsoft의 스폰서는 고객 및 오픈 소스 커뮤니티와 긴밀 하 게 협력 하 여 Eapr를 설계 하 고 구축 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-110">Its sponsor, Microsoft, has closely partnered with customers and the open-source community to design and build Dapr.</span></span> <span data-ttu-id="6d41e-111">이 프로젝트는 모든 배경에서 개발자를 함께 제공 하 여 분산 응용 프로그램 개발의 가장 어려운 문제 중 일부를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-111">The Dapr project brings together developers from all backgrounds to solve some of the toughest challenges of developing distributed applications.</span></span>

<span data-ttu-id="6d41e-112">이 책에서는 .NET 개발자의 관점에서부터부터 4 번째를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-112">This book looks at Dapr from the viewpoint of a .NET developer.</span></span> <span data-ttu-id="6d41e-113">이 장에서는 Eapr 및 작동 방식에 대 한 개념적인 이해를 구축 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-113">In this chapter, you'll build a conceptual understanding of Dapr and how it works.</span></span> <span data-ttu-id="6d41e-114">나중에 응용 프로그램에서 d 4를 사용 하는 방법에 대 한 실용적인 실습 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-114">Later on, we present practical, hands-on instruction on how you can use Dapr in your applications.</span></span>

<span data-ttu-id="6d41e-115">Jet에서 2만 피트로 비행을 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="6d41e-115">Imagine flying in a jet at 20,000 feet.</span></span> <span data-ttu-id="6d41e-116">창을 확인 하 고 광범위 한 관점에서 아래 가로를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-116">You look out the window and see the landscape below from a wide perspective.</span></span> <span data-ttu-id="6d41e-117">D Apr에 대해 동일한 작업을 수행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-117">Let's do the same for Dapr.</span></span> <span data-ttu-id="6d41e-118">2만 피트에서 A4에서 직접 비행을 시각화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-118">Visualize yourself flying over Dapr at 20,000 feet.</span></span> <span data-ttu-id="6d41e-119">표시 되는 내용</span><span class="sxs-lookup"><span data-stu-id="6d41e-119">What would you see?</span></span>

## <a name="dapr-and-the-problem-it-solves"></a><span data-ttu-id="6d41e-120">6apr 및 해결 된 문제</span><span class="sxs-lookup"><span data-stu-id="6d41e-120">Dapr and the problem it solves</span></span>

<span data-ttu-id="6d41e-121">D 4는 최신 분산 응용 프로그램: **복잡성** 에 내재 된 큰 과제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-121">Dapr addresses a large challenge inherent in modern distributed applications: **Complexity**.</span></span>

<span data-ttu-id="6d41e-122">플러그형 구성 요소의 아키텍처를 통해, d 4는 분산 응용 프로그램의 기반이 되는 것을 크게 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-122">Through an architecture of pluggable components, Dapr greatly simplifies the plumbing behind distributed applications.</span></span> <span data-ttu-id="6d41e-123">이 클래스는 응용 프로그램을 Capr 런타임의 인프라 기능과 바인딩하는 **동적 붙이기를** 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-123">It provides a **dynamic glue** that binds your application with infrastructure capabilities from the Dapr runtime.</span></span> <span data-ttu-id="6d41e-124">예를 들어 응용 프로그램에 상태 저장소가 필요할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-124">For example, your application may require a state store.</span></span> <span data-ttu-id="6d41e-125">Redis Cache 대상으로 지정 하는 사용자 지정 코드를 작성 하 여 런타임에 서비스에 삽입할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-125">You could write custom code to target Redis Cache and inject it into your service at runtime.</span></span> <span data-ttu-id="6d41e-126">그러나 기본 제공 되는 분산 캐시 기능을 제공 하 여 사용자 환경을 단순화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-126">However, Dapr simplifies your experience by providing a distributed cache capability out-of-the-box.</span></span> <span data-ttu-id="6d41e-127">서비스는 Eapr **구성** 을 통해 Redis Cache **구성 요소** 에 동적으로 바인딩하는 eapr **빌딩 블록** 을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-127">Your service invokes a Dapr **building block** that dynamically binds to Redis Cache **component** via a Dapr **configuration**.</span></span> <span data-ttu-id="6d41e-128">이 모델을 사용 하면 서비스는 사용자를 대신해 서 Redis를 호출 하는 Eapr에 호출을 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-128">With this model, your service delegates the call to Dapr, which calls Redis on your behalf.</span></span> <span data-ttu-id="6d41e-129">서비스에 SDK, 라이브러리 또는 Redis에 대 한 직접 참조가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-129">Your service has no SDK, library, or direct reference to Redis.</span></span> <span data-ttu-id="6d41e-130">Redis Cache API가 아닌 일반적인 Eapr 상태 관리 API에 대해 코딩 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-130">You code against the common Dapr state management API, not the Redis Cache API.</span></span>

<span data-ttu-id="6d41e-131">그림 2-1에는 2만 피트의 44가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-131">Figure 2-1 shows Dapr from 20,000 feet.</span></span>

<span data-ttu-id="6d41e-132">![2만 피트 피트 ](./media/dapr-at-20000-feet/dapr-high-level.png)
 **그림 2-1**</span><span class="sxs-lookup"><span data-stu-id="6d41e-132">![Dapr at 20,000 feet](./media/dapr-at-20000-feet/dapr-high-level.png)
**Figure 2-1**.</span></span> <span data-ttu-id="6d41e-133">2만 피트</span><span class="sxs-lookup"><span data-stu-id="6d41e-133">Dapr at 20,000 feet.</span></span>

<span data-ttu-id="6d41e-134">그림의 맨 위 행에서 d 4는 인기 있는 개발 플랫폼에 대 한 언어별 Sdk를 제공 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-134">In the top row of the figure, note how Dapr provides language-specific SDKs for popular development platforms.</span></span> <span data-ttu-id="6d41e-135">1.0는 Go, Node.js, Python, .NET, Java 및 JavaScript를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-135">Dapr v 1.0 includes supports Go, Node.js, Python, .NET, Java, and JavaScript.</span></span> <span data-ttu-id="6d41e-136">이 책에서는 ASP.NET Core 통합에 대 한 직접적인 지원도 제공 하는 Dapr .NET SDK에 대해 집중적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-136">This book focuses on the Dapr .NET SDK, which also provides direct support for ASP.NET Core integration.</span></span>

<span data-ttu-id="6d41e-137">언어별 Sdk는 개발자 환경을 개선 하는 반면, d 4 월은 플랫폼에 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-137">While language-specific SDKs enhance the developer experience, Dapr is platform agnostic.</span></span> <span data-ttu-id="6d41e-138">내부적으로, 4, 4의 프로그래밍 모델은 표준 HTTP/gRPC 통신 프로토콜을 통해 기능을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-138">Under the hood, Dapr's programming model exposes capabilities through standard HTTP/gRPC communication protocols.</span></span> <span data-ttu-id="6d41e-139">모든 프로그래밍 플랫폼은 네이티브 HTTP 및 gRPC Api를 통해 6Apr를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-139">Any programming platform can call Dapr via its native HTTP and gRPC APIs.</span></span>  

<span data-ttu-id="6d41e-140">그림의 가운데에 있는 파란색 상자는 4 번째 빌딩 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-140">The blue boxes across the center of the figure represent the Dapr building blocks.</span></span> <span data-ttu-id="6d41e-141">각는 응용 프로그램에서 사용할 수 있는 배포 응용 프로그램 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-141">Each exposes a distributed application capability that your application can consume.</span></span>

<span data-ttu-id="6d41e-142">아래쪽 행에는 Eapr 및 실행할 수 있는 다양 한 환경에 대 한 이식성이 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-142">The bottom row highlights the portability of Dapr and the diverse environments across which it can run.</span></span>

## <a name="dapr-architecture"></a><span data-ttu-id="6d41e-143">4 월 아키텍처</span><span class="sxs-lookup"><span data-stu-id="6d41e-143">Dapr architecture</span></span>

<span data-ttu-id="6d41e-144">이 시점에서 jet는 계속 해 서 a를 기준으로 하는 Eapr를 전환 하 고 다시 포기 하 여,의 작업 방식에 대해 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-144">At this point, the jet turns around and flies back over Dapr, descending in altitude, giving you a closer look at how Dapr works.</span></span>

### <a name="building-blocks"></a><span data-ttu-id="6d41e-145">구성 요소</span><span class="sxs-lookup"><span data-stu-id="6d41e-145">Building blocks</span></span>

<span data-ttu-id="6d41e-146">새로운 관점에서 볼 때에는 보다 자세한 정보를 볼 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="6d41e-146">From the new perspective, you see a more detailed view of the Dapr **building blocks**.</span></span>

<span data-ttu-id="6d41e-147">빌딩 블록은 분산 인프라 기능을 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-147">A building block encapsulates a distributed infrastructure capability.</span></span> <span data-ttu-id="6d41e-148">HTTP 또는 gRPC Api를 통해 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-148">You can access the functionality through the HTTP or gRPC APIs.</span></span> <span data-ttu-id="6d41e-149">그림 2-2에서는 Eapr v 1.0에 사용할 수 있는 블록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-149">Figure 2-2 shows the available blocks for Dapr v 1.0.</span></span>

![4apr 빌딩 블록](./media/dapr-at-20000-feet/building-blocks.png)

<span data-ttu-id="6d41e-151">**그림 2-2**.</span><span class="sxs-lookup"><span data-stu-id="6d41e-151">**Figure 2-2**.</span></span> <span data-ttu-id="6d41e-152">4apr 빌딩 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-152">Dapr building blocks.</span></span>

<span data-ttu-id="6d41e-153">다음 표에서는 각 블록에서 제공 하는 인프라 서비스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-153">The following table describes the infrastructure services provided by each block.</span></span>

| <span data-ttu-id="6d41e-154">구성 요소</span><span class="sxs-lookup"><span data-stu-id="6d41e-154">Building block</span></span> | <span data-ttu-id="6d41e-155">설명</span><span class="sxs-lookup"><span data-stu-id="6d41e-155">Description</span></span> |
|----------------|-------------|
| [<span data-ttu-id="6d41e-156">상태 관리</span><span class="sxs-lookup"><span data-stu-id="6d41e-156">State management</span></span>](state-management.md) | <span data-ttu-id="6d41e-157">장기 실행 상태 저장 서비스에 대 한 컨텍스트 정보를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-157">Support contextual information for long running stateful services.</span></span> |
| [<span data-ttu-id="6d41e-158">서비스 호출</span><span class="sxs-lookup"><span data-stu-id="6d41e-158">Service invocation</span></span>](service-invocation.md) | <span data-ttu-id="6d41e-159">플랫폼을 알 수 없는 프로토콜 및 잘 알려진 끝점을 사용 하 여 직접, 보안 서비스 간 호출을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-159">Invoke direct, secure service-to-service calls using platform agnostic protocols and well-known endpoints.</span></span> |
| [<span data-ttu-id="6d41e-160">게시 및 구독</span><span class="sxs-lookup"><span data-stu-id="6d41e-160">Publish and subscribe</span></span>](publish-subscribe.md) | <span data-ttu-id="6d41e-161">서비스 간에 안전 하 고 확장 가능한 게시/서브 메시징을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-161">Implement secure, scalable pub/sub messaging between services.</span></span> |
| [<span data-ttu-id="6d41e-162">바인딩</span><span class="sxs-lookup"><span data-stu-id="6d41e-162">Bindings</span></span>](bindings.md) | <span data-ttu-id="6d41e-163">양방향 통신을 사용 하 여 외부 리소스에 의해 발생 한 이벤트에서 코드를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-163">Trigger code from events raised by external resources with bi-directional communication.</span></span> |
| [<span data-ttu-id="6d41e-164">가시성</span><span class="sxs-lookup"><span data-stu-id="6d41e-164">Observability</span></span>](observability.md) | <span data-ttu-id="6d41e-165">네트워크 서비스에서 메시지 호출을 모니터링 하 고 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-165">Monitor and measure message calls across networked services.</span></span> |
| [<span data-ttu-id="6d41e-166">비밀</span><span class="sxs-lookup"><span data-stu-id="6d41e-166">Secrets</span></span>](secrets.md) | <span data-ttu-id="6d41e-167">외부 암호 저장소에 안전 하 게 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-167">Securely access external secret stores.</span></span> |
| <span data-ttu-id="6d41e-168">행위자</span><span class="sxs-lookup"><span data-stu-id="6d41e-168">Actors</span></span> | <span data-ttu-id="6d41e-169">다시 사용할 수 있는 행위자 개체에 논리와 데이터를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-169">Encapsulate logic and data in reusable actor objects.</span></span> |

<span data-ttu-id="6d41e-170">구성 요소는 서비스에서 분산 응용 프로그램 기능의 구현을 추상화 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-170">Building blocks abstract the implementation of distributed application capabilities from your services.</span></span> <span data-ttu-id="6d41e-171">그림 2-3에서는 이러한 상호 작용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-171">Figure 2-3 shows this interaction.</span></span>

![4apr 빌딩 블록 통합](./media/dapr-at-20000-feet/building-blocks-integration.png)

<span data-ttu-id="6d41e-173">**그림 2-3**.</span><span class="sxs-lookup"><span data-stu-id="6d41e-173">**Figure 2-3**.</span></span> <span data-ttu-id="6d41e-174">4apr 빌딩 블록 통합.</span><span class="sxs-lookup"><span data-stu-id="6d41e-174">Dapr building block integration.</span></span>

<span data-ttu-id="6d41e-175">빌딩 블록은 각 리소스에 대 한 구체적인 구현을 제공 하는 4 월 구성 요소를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-175">Building blocks invoke Dapr components that provide the concrete implementation for each resource.</span></span> <span data-ttu-id="6d41e-176">서비스에 대 한 코드는 빌딩 블록만 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-176">The code for your service is only aware of the building block.</span></span> <span data-ttu-id="6d41e-177">외부 Sdk 나 라이브러리에 대 한 종속성을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-177">It takes no dependencies on external SDKs or libraries - Dapr handles the plumbing for you.</span></span> <span data-ttu-id="6d41e-178">각 빌딩 블록은 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-178">Each building block is independent.</span></span> <span data-ttu-id="6d41e-179">응용 프로그램에서 하나, 일부 또는 모두를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-179">You can use one, some, or all of them in your application.</span></span> <span data-ttu-id="6d41e-180">값 추가로, 종합적인 관찰성을 비롯 한 업계 모범 사례에서 굽기 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-180">As a value-add, Dapr building blocks bake in industry best practices including comprehensive observability.</span></span>

<span data-ttu-id="6d41e-181">이후 장에서 각 4Apr 빌딩 블록에 대 한 자세한 설명 및 코드 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-181">We provide detailed explanation and code samples for each Dapr building block in the upcoming chapters.</span></span> <span data-ttu-id="6d41e-182">이 시점에서 jet는 훨씬 더 계층이 이어집니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-182">At this point, the jet descends even more.</span></span> <span data-ttu-id="6d41e-183">이제 새로운 관점에서 볼 때에는 이제는 Eapr 구성 요소 계층에 대해 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-183">From the new perspective, you now have a closer look at the Dapr components layer.</span></span>

### <a name="components"></a><span data-ttu-id="6d41e-184">구성 요소</span><span class="sxs-lookup"><span data-stu-id="6d41e-184">Components</span></span>

<span data-ttu-id="6d41e-185">빌드 블록은 배포 응용 프로그램 기능을 호출 하는 API를 노출 하지만, Capr 구성 요소는 구체적 구현을 제공 하 여이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-185">While building blocks expose an API to invoke distributed application capabilities, Dapr components provide the concrete implementation to make it happen.</span></span>

<span data-ttu-id="6d41e-186">예를 들어, Wapr **상태 저장소** 구성 요소를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-186">Consider, the Dapr **state store** component.</span></span> <span data-ttu-id="6d41e-187">CRUD 작업에 대 한 상태를 관리 하는 일관 된 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-187">It provides a uniform way to manage state for CRUD operations.</span></span> <span data-ttu-id="6d41e-188">서비스 코드를 변경 하지 않으면 다음의 모든 작업 구성 요소 중 하나를 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-188">Without any change to your service code, you could switch between any of the following Dapr state components:</span></span>

- <span data-ttu-id="6d41e-189">AWS DynamoDB</span><span class="sxs-lookup"><span data-stu-id="6d41e-189">AWS DynamoDB</span></span>
- <span data-ttu-id="6d41e-190">Aerospike</span><span class="sxs-lookup"><span data-stu-id="6d41e-190">Aerospike</span></span>
- <span data-ttu-id="6d41e-191">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="6d41e-191">Azure Blob Storage</span></span>
- <span data-ttu-id="6d41e-192">Azure CosmosDB</span><span class="sxs-lookup"><span data-stu-id="6d41e-192">Azure CosmosDB</span></span>
- <span data-ttu-id="6d41e-193">Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="6d41e-193">Azure Table Storage</span></span>
- <span data-ttu-id="6d41e-194">Cassandra</span><span class="sxs-lookup"><span data-stu-id="6d41e-194">Cassandra</span></span>
- <span data-ttu-id="6d41e-195">클라우드 Firestore (데이터 저장소 모드)</span><span class="sxs-lookup"><span data-stu-id="6d41e-195">Cloud Firestore (Datastore mode)</span></span>
- <span data-ttu-id="6d41e-196">CloudState</span><span class="sxs-lookup"><span data-stu-id="6d41e-196">CloudState</span></span>
- <span data-ttu-id="6d41e-197">Couchbase</span><span class="sxs-lookup"><span data-stu-id="6d41e-197">Couchbase</span></span>
- <span data-ttu-id="6d41e-198">Etcd</span><span class="sxs-lookup"><span data-stu-id="6d41e-198">Etcd</span></span>
- <span data-ttu-id="6d41e-199">HashiCorp Consul</span><span class="sxs-lookup"><span data-stu-id="6d41e-199">HashiCorp Consul</span></span>
- <span data-ttu-id="6d41e-200">Hazelcast</span><span class="sxs-lookup"><span data-stu-id="6d41e-200">Hazelcast</span></span>
- <span data-ttu-id="6d41e-201">Memcached</span><span class="sxs-lookup"><span data-stu-id="6d41e-201">Memcached</span></span>
- <span data-ttu-id="6d41e-202">MongoDB</span><span class="sxs-lookup"><span data-stu-id="6d41e-202">MongoDB</span></span>
- <span data-ttu-id="6d41e-203">PostgreSQL</span><span class="sxs-lookup"><span data-stu-id="6d41e-203">PostgreSQL</span></span>
- <span data-ttu-id="6d41e-204">Redis</span><span class="sxs-lookup"><span data-stu-id="6d41e-204">Redis</span></span>
- <span data-ttu-id="6d41e-205">RethinkDB</span><span class="sxs-lookup"><span data-stu-id="6d41e-205">RethinkDB</span></span>
- <span data-ttu-id="6d41e-206">SQL Server</span><span class="sxs-lookup"><span data-stu-id="6d41e-206">SQL Server</span></span>
- <span data-ttu-id="6d41e-207">Zookeeper</span><span class="sxs-lookup"><span data-stu-id="6d41e-207">Zookeeper</span></span>

<span data-ttu-id="6d41e-208">각 구성 요소는 일반적인 상태 관리 인터페이스를 통해 필요한 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-208">Each component provides the necessary implementation through a common state management interface:</span></span>

```go
 type Store interface {
   Init(metadata Metadata) error
   Delete(req *DeleteRequest) error
   BulkDelete(req []DeleteRequest) error
   Get(req *GetRequest) (*GetResponse, error)
   Set(req *SetRequest) error
   BulkSet(req []SetRequest) error
}
```

> [!TIP]
> <span data-ttu-id="6d41e-209">Golang 또는 Go 언어로 작성 된 모든의 4 가지 구성 요소 뿐만 아니라,</span><span class="sxs-lookup"><span data-stu-id="6d41e-209">The Dapr runtime as well as all of the Dapr components have been written in the Golang, or Go, language.</span></span> <span data-ttu-id="6d41e-210">Go는 오픈 소스 커뮤니티에서 널리 사용 되는 언어로, 입증의 플랫폼 간 약정을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-210">Go is a popular language across the open source community and attests to cross-platform commitment of Dapr.</span></span>

<span data-ttu-id="6d41e-211">Azure Redis Cache에서 상태 저장소로 시작 하는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-211">Perhaps you start with Azure Redis Cache as your state store.</span></span> <span data-ttu-id="6d41e-212">다음 구성을 사용 하 여 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-212">You specify it with the following configuration:</span></span>

 ```yaml
 apiVersion: dapr.io/v1alpha1
 kind: Component
 metadata:
   name: statestore
   namespace: default
 spec:
   type: state.redis
   version: v1
   metadata:
   - name: redisHost
     value: <HOST>
   - name: redisPassword
     value: <PASSWORD>
   - name: enableTLS
     value: <bool> # Optional. Allowed: true, false.
   - name: failover
     value: <bool> # Optional. Allowed: true, false.
 ```

<span data-ttu-id="6d41e-213">**사양** 섹션에서 상태 관리에 대 한 Redis Cache를 사용 하도록 6apr를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-213">In the **spec** section, you configure Dapr to use the Redis Cache for state management.</span></span> <span data-ttu-id="6d41e-214">또한이 섹션에서는 구성 요소별 메타 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-214">The section also contains component-specific metadata.</span></span> <span data-ttu-id="6d41e-215">이 경우 추가 Redis 설정을 구성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-215">In this case, you can use it to configure additional Redis settings.</span></span>

<span data-ttu-id="6d41e-216">나중에 응용 프로그램을 프로덕션 환경으로 이동할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-216">At a later time, the application is ready to go to production.</span></span> <span data-ttu-id="6d41e-217">프로덕션 환경의 경우 상태 관리를 Azure Table Storage로 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-217">For the production environment, you may want to change your state management to Azure Table Storage.</span></span> <span data-ttu-id="6d41e-218">Azure Table Storage는 경제적이 고 내구성이 뛰어난 상태 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-218">Azure Table Storage provides state management capabilities that are affordable and highly durable.</span></span>

<span data-ttu-id="6d41e-219">이 문서를 작성할 당시에는 다음과 같은 구성 요소 유형을 d 4에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-219">At the time of this writing, the following component types are provided by Dapr:</span></span>

| <span data-ttu-id="6d41e-220">구성 요소</span><span class="sxs-lookup"><span data-stu-id="6d41e-220">Component</span></span> | <span data-ttu-id="6d41e-221">설명</span><span class="sxs-lookup"><span data-stu-id="6d41e-221">Description</span></span> |
|-----------|-------------|
| [<span data-ttu-id="6d41e-222">서비스 검색</span><span class="sxs-lookup"><span data-stu-id="6d41e-222">Service discovery</span></span>](https://github.com/dapr/components-contrib/tree/master/nameresolution) | <span data-ttu-id="6d41e-223">서비스 간 검색을 제공 하기 위해 호스팅 환경과 통합 하는 서비스 호출 구성 요소에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-223">Used by the service invocation building block to integrate with the hosting environment to provide service-to-service discovery.</span></span> |
| [<span data-ttu-id="6d41e-224">State</span><span class="sxs-lookup"><span data-stu-id="6d41e-224">State</span></span>](https://github.com/dapr/components-contrib/tree/master/state) | <span data-ttu-id="6d41e-225">다양 한 상태 저장소 구현과 상호 작용 하기 위한 균일 한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-225">Provides a uniform interface to interact with a wide variety of state store implementations.</span></span> |
| [<span data-ttu-id="6d41e-226">Pub/sub</span><span class="sxs-lookup"><span data-stu-id="6d41e-226">Pub/sub</span></span>](https://github.com/dapr/components-contrib/tree/master/pubsub) | <span data-ttu-id="6d41e-227">다양 한 메시지 버스 구현과 상호 작용 하기 위한 균일 한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-227">Provides a uniform interface to interact with a wide variety of message bus implementations.</span></span> |
| [<span data-ttu-id="6d41e-228">바인딩</span><span class="sxs-lookup"><span data-stu-id="6d41e-228">Bindings</span></span>](https://github.com/dapr/components-contrib/tree/master/bindings) | <span data-ttu-id="6d41e-229">외부 시스템에서 응용 프로그램 이벤트를 트리거하고 선택적 데이터 페이로드가 있는 외부 시스템을 호출 하는 일관 된 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-229">Provides a uniform interface to trigger application events from external systems and invoke external systems with optional data payloads.</span></span> |
| [<span data-ttu-id="6d41e-230">미들웨어</span><span class="sxs-lookup"><span data-stu-id="6d41e-230">Middleware</span></span>](https://github.com/dapr/components-contrib/tree/master/middleware) | <span data-ttu-id="6d41e-231">사용자 지정 미들웨어가 요청 처리 파이프라인에 연결 하 고 요청 또는 응답에 대 한 추가 작업을 호출할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-231">Allows custom middleware to plug into the request processing pipeline and invoke additional actions on a request or response.</span></span> |
| [<span data-ttu-id="6d41e-232">비밀 저장소</span><span class="sxs-lookup"><span data-stu-id="6d41e-232">Secret stores</span></span>](https://github.com/dapr/components-contrib/tree/master/secretstores) | <span data-ttu-id="6d41e-233">클라우드,에 지, 상용, 오픈 소스 서비스를 비롯 하 여 외부 암호 저장소와 상호 작용 하는 일관 된 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-233">Provides a uniform interface to interact with external secret stores, including cloud, edge, commercial, open-source services.</span></span> |

<span data-ttu-id="6d41e-234">Jet가 d 4의 즉석에서 날아오기를 완료 하는 경우에는 나중에 다시 연결 하 여 함께 연결 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-234">As the jet completes its fly over of Dapr, you look back once more and can see how it connects together.</span></span>

### <a name="sidecar-architecture"></a><span data-ttu-id="6d41e-235">사이드카 아키텍처</span><span class="sxs-lookup"><span data-stu-id="6d41e-235">Sidecar architecture</span></span>

<span data-ttu-id="6d41e-236">[사이드카 아키텍처](/azure/architecture/patterns/sidecar)를 통해 구성 요소 및 구성 요소를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-236">Dapr exposes its building blocks and components through a [sidecar architecture](/azure/architecture/patterns/sidecar).</span></span> <span data-ttu-id="6d41e-237">사이드카를 사용 하면 다른 메모리 프로세스에서 또는 서비스와 함께 별도의 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-237">A sidecar enables Dapr to run in a separate memory process or separate container alongside your service.</span></span> <span data-ttu-id="6d41e-238">사이드카는 서비스에 포함 되지 않고 연결 된 격리 및 캡슐화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-238">Sidecars provide isolation and encapsulation as they aren't part of the service, but connected to it.</span></span> <span data-ttu-id="6d41e-239">이러한 분리를 통해 각각 고유한 런타임 환경을 보유 하 고 다양 한 프로그래밍 플랫폼을 기반으로 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-239">This separation enables each to have its own runtime environment and be built upon different programming platforms.</span></span> <span data-ttu-id="6d41e-240">그림 2-4에서는 사이드카 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-240">Figure 2-4 shows a sidecar pattern.</span></span>

![사이드카 아키텍처](./media/dapr-at-20000-feet/sidecar-generic.png)

<span data-ttu-id="6d41e-242">**그림 2-4**.</span><span class="sxs-lookup"><span data-stu-id="6d41e-242">**Figure 2-4**.</span></span> <span data-ttu-id="6d41e-243">사이드카 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="6d41e-243">Sidecar architecture.</span></span>

<span data-ttu-id="6d41e-244">이 패턴은 오토바이에 연결된 사이드카와 유사하므로 사이드카라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-244">This pattern is named Sidecar because it resembles a sidecar attached to a motorcycle.</span></span> <span data-ttu-id="6d41e-245">위의 그림에서 배포 응용 프로그램 기능을 제공 하기 위해 사이드카이 서비스에 연결 되는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-245">In the previous figure, note how the Dapr sidecar is attached to your service to provide distributed application capabilities.</span></span>

### <a name="hosting-environments"></a><span data-ttu-id="6d41e-246">호스팅 환경</span><span class="sxs-lookup"><span data-stu-id="6d41e-246">Hosting environments</span></span>

<span data-ttu-id="6d41e-247">D apr는 플랫폼 간 지원을 제공 하며 다양 한 환경에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-247">Dapr has cross-platform support and can run in many different environments.</span></span> <span data-ttu-id="6d41e-248">이러한 환경에는 Kubernetes, Vm 그룹 또는 Azure IoT Edge와 같은에 지 환경이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-248">These environments include Kubernetes, a group of VMs, or edge environments such as Azure IoT Edge.</span></span>

<span data-ttu-id="6d41e-249">로컬 개발의 경우 시작 하는 가장 쉬운 방법은 [자체 호스팅 모드](https://docs.dapr.io/concepts/overview/#self-hosted)를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-249">For local development, the easiest way to get started is with [self-hosted mode](https://docs.dapr.io/concepts/overview/#self-hosted).</span></span> <span data-ttu-id="6d41e-250">자체 호스팅 모드에서 마이크로 서비스와 사이드카는 Kubernetes와 같은 컨테이너 orchestrator 없이 별도의 로컬 프로세스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-250">In self-hosted mode, the microservices and Dapr sidecars run in separate local processes without a container orchestrator such as Kubernetes.</span></span> <span data-ttu-id="6d41e-251">자세한 내용은 [Eapr CLI 다운로드 및 설치](https://docs.dapr.io/getting-started/install-dapr/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6d41e-251">For more information, see [download and install the Dapr CLI](https://docs.dapr.io/getting-started/install-dapr/).</span></span>

<span data-ttu-id="6d41e-252">그림 2-5에서는 HTTP 또는 gRPC를 통해 통신 하는 두 개의 별도 메모리 프로세스에서 호스팅되는 응용 프로그램 및 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-252">Figure 2-5 shows an application and Dapr hosted in two separate memory processes communicating via HTTP or gRPC.</span></span>

![자체 호스팅 사이드카 아키텍처](./media/dapr-at-20000-feet/self-hosted-dapr-sidecar.png)

<span data-ttu-id="6d41e-254">**그림 2-5**.</span><span class="sxs-lookup"><span data-stu-id="6d41e-254">**Figure 2-5**.</span></span> <span data-ttu-id="6d41e-255">자체 호스팅 사이드카.</span><span class="sxs-lookup"><span data-stu-id="6d41e-255">Self-hosted Dapr sidecar.</span></span>

<span data-ttu-id="6d41e-256">기본적으로 Redis 및 Zipkin에 대 한 Docker 컨테이너를 설치 하 여 기본 상태 관리 및 관찰성를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-256">By default, Dapr installs Docker containers for Redis and Zipkin to provide default state management and observability.</span></span> <span data-ttu-id="6d41e-257">로컬 컴퓨터에 Docker를 설치 하지 않으려면 [docker 컨테이너 없이도 자체 호스팅 모드에서](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/)docker를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-257">If you don't want to install Docker on your local machine, you can even [run Dapr in self-hosted mode without any Docker containers](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/).</span></span> <span data-ttu-id="6d41e-258">그러나 상태 관리 및 pub/sub에 대해 Redis 같은 기본 구성 요소를 수동으로 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-258">However, you must install default components such as Redis for state management and pub/sub manually.</span></span>

<span data-ttu-id="6d41e-259">또한 컨테이너 화 된는 Kubernetes와 같은 [환경](https://docs.dapr.io/concepts/overview/#kubernetes-hosted)에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-259">Dapr also runs in [containerized environments](https://docs.dapr.io/concepts/overview/#kubernetes-hosted), such as Kubernetes.</span></span> <span data-ttu-id="6d41e-260">그림 2-6에는 동일한 Kubernetes pod의 응용 프로그램 컨테이너와 함께 별도의 측면과 자동차 컨테이너에서 실행 되는 4 개의가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-260">Figure 2-6 shows Dapr running in a separate side-car container along with the application container in the same Kubernetes pod.</span></span>

![Kubernetes-호스팅된 사이드카 아키텍처](./media/dapr-at-20000-feet/kubernetes-hosted-dapr-sidecar.png)

<span data-ttu-id="6d41e-262">**그림 2-6**.</span><span class="sxs-lookup"><span data-stu-id="6d41e-262">**Figure 2-6**.</span></span> <span data-ttu-id="6d41e-263">Kubernetes-호스 티 드 사이드카.</span><span class="sxs-lookup"><span data-stu-id="6d41e-263">Kubernetes-hosted Dapr sidecar.</span></span>

## <a name="dapr-performance-considerations"></a><span data-ttu-id="6d41e-264">4 월 성능 고려 사항</span><span class="sxs-lookup"><span data-stu-id="6d41e-264">Dapr performance considerations</span></span>

<span data-ttu-id="6d41e-265">앞서 살펴본 것 처럼 사이드카 아키텍처를 노출 하 여 응용 프로그램을 분산 응용 프로그램 기능에서 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-265">As you've seen, Dapr exposes a sidecar architecture to decouple your application from distributed application capabilities.</span></span> <span data-ttu-id="6d41e-266">Eapr 작업을 호출 하려면 적어도 하나 이상의 out-of-process 네트워크 호출이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-266">Invoking a Dapr operation requires at least one out-of-process network call.</span></span> <span data-ttu-id="6d41e-267">그림 2-7에는 4Apr 트래픽 패턴의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-267">Figure 2-7 presents an example of a Dapr traffic pattern.</span></span>

![4apr 트래픽 패턴](./media/dapr-at-20000-feet/dapr-traffic-patterns.png)

<span data-ttu-id="6d41e-269">**그림 2-7**.</span><span class="sxs-lookup"><span data-stu-id="6d41e-269">**Figure 2-7**.</span></span> <span data-ttu-id="6d41e-270">4apr 트래픽 패턴.</span><span class="sxs-lookup"><span data-stu-id="6d41e-270">Dapr traffic patterns.</span></span>

<span data-ttu-id="6d41e-271">위의 그림을 보면 각 호출에 대해 발생 하는 대기 시간 및 오버 헤드를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-271">Looking at the previous figure, one might question the latency and overhead incurred for each call.</span></span>  

<span data-ttu-id="6d41e-272">4Apr 팀은 성능에 많은 투자를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-272">The Dapr team has invested heavily in performance.</span></span> <span data-ttu-id="6d41e-273">엄청난 규모의 엔지니어링 노력으로 인해 4 월 효율적으로 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-273">A tremendous amount of engineering effort has gone into making Dapr efficient.</span></span> <span data-ttu-id="6d41e-274">Eapr 사이드카 간의 호출은 항상 높은 성능과 작은 이진 페이로드를 제공 하는 gRPC를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-274">Calls between Dapr sidecars are always made with gRPC, which delivers high performance and small binary payloads.</span></span> <span data-ttu-id="6d41e-275">대부분의 경우 추가 오버 헤드는 하위 밀리초 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-275">In most cases, the additional overhead should be sub-millisecond.</span></span>

<span data-ttu-id="6d41e-276">개발자는 성능을 향상 시키기 위해 gRPC를 사용 하 여 4Apr 빌딩 블록을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-276">To increase performance, developers can call the Dapr building blocks with gRPC.</span></span>

<span data-ttu-id="6d41e-277">gRPC는 오래 된 [원격 프로시저 호출 (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) 프로토콜을 진화 하는 현대적인 고성능 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-277">gRPC is a modern, high-performance framework that evolves the age-old [remote procedure call (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) protocol.</span></span> <span data-ttu-id="6d41e-278">gRPC는 전송 프로토콜에 대해 HTTP/2를 사용 하며, 다음을 포함 하 여 HTTP RESTFul 서비스 보다 상당한 성능 향상을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-278">gRPC uses HTTP/2 for its transport protocol, which provides significant performance enhancements over HTTP RESTFul service, including:</span></span>

- <span data-ttu-id="6d41e-279">동일한 연결을 통해 여러 병렬 요청을 보내기 위한 멀티플렉싱 지원-HTTP 1.1는 한 번에 하나의 요청/응답 메시지로 처리를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-279">Multiplexing support for sending multiple parallel requests over the same connection - HTTP 1.1 limits processing to one request/response message at a time.</span></span>
- <span data-ttu-id="6d41e-280">클라이언트 요청과 서버 응답을 동시에 전송 하기 위한 양방향 전이중 통신입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-280">Bidirectional full-duplex communication for sending both client requests and server responses simultaneously.</span></span>
- <span data-ttu-id="6d41e-281">대량 데이터 집합을 비동기적으로 스트림 하는 요청 및 응답을 설정 하는 기본 제공 스트리밍입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-281">Built-in streaming enabling requests and responses to asynchronously stream large data sets.</span></span>

## <a name="dapr-and-service-meshes"></a><span data-ttu-id="6d41e-282">4apr 및 서비스 메시</span><span class="sxs-lookup"><span data-stu-id="6d41e-282">Dapr and service meshes</span></span>

<span data-ttu-id="6d41e-283">서비스 메시는 분산 응용 프로그램에 대 한 또 다른 빠르게 진화 하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-283">Service mesh is another rapidly evolving technology for distributed applications.</span></span>

<span data-ttu-id="6d41e-284">서비스 메시는 서비스 간 통신, 복원 력, 부하 분산 및 원격 분석 캡처를 처리 하는 기본 제공 기능이 포함 된 구성 가능한 인프라 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-284">A service mesh is a configurable infrastructure layer with built-in capabilities to handle service-to-service communication, resiliency, load balancing, and telemetry capture.</span></span> <span data-ttu-id="6d41e-285">서비스 및 서비스 메시 계층으로 이러한 문제에 대 한 책임을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-285">It moves the responsibility for these concerns out of the services and into the service mesh layer.</span></span> <span data-ttu-id="6d41e-286">Eapr와 마찬가지로 서비스 메시도 사이드카 아키텍처를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-286">Like Dapr, a service mesh also follows a sidecar architecture.</span></span>

<span data-ttu-id="6d41e-287">그림 2-8에서는 서비스 메시 기술을 구현 하는 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-287">Figure 2-8 shows an application that implements service mesh technology.</span></span>

![서비스 메시](./media/dapr-at-20000-feet/service-mesh-with-side-car.png)

<span data-ttu-id="6d41e-289">**그림 2-8**.</span><span class="sxs-lookup"><span data-stu-id="6d41e-289">**Figure 2-8**.</span></span> <span data-ttu-id="6d41e-290">측 자동차를 사용 하는 서비스 메시.</span><span class="sxs-lookup"><span data-stu-id="6d41e-290">Service mesh with a side car.</span></span>

<span data-ttu-id="6d41e-291">위의 그림은 각 서비스와 함께 실행 되는 프록시가 메시지를 가로채는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-291">The previous figure shows how messages are intercepted by a proxy that runs alongside each service.</span></span> <span data-ttu-id="6d41e-292">각 프록시는 서비스와 관련 된 트래픽 규칙으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-292">Each proxy can be configured with traffic rules specific to the service.</span></span> <span data-ttu-id="6d41e-293">메시지를 이해 하 고 서비스와 외부 세계에서 메시지를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-293">It understands messages and can route them across your services and the outside world.</span></span>

<span data-ttu-id="6d41e-294">따라서 "서비스 메시는 ' 서비스 메시 인가요?" 라는 질문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-294">So the question becomes, "Is Dapr a service mesh?".</span></span>

<span data-ttu-id="6d41e-295">둘 다 사이드카 아키텍처를 사용 하는 반면 각 기술은 다른 용도로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-295">While both use a sidecar architecture, each technology has a different purpose.</span></span> <span data-ttu-id="6d41e-296">D 4는 배포 응용 프로그램 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-296">Dapr provides distributed application features.</span></span> <span data-ttu-id="6d41e-297">서비스 메시는 전용 네트워크 인프라 계층을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-297">A service mesh provides a dedicated network infrastructure layer.</span></span>

<span data-ttu-id="6d41e-298">서로 다른 수준에서 작동 하는 경우 모두 동일한 응용 프로그램에서 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-298">As each works at a different level, both can work together in the same application.</span></span> <span data-ttu-id="6d41e-299">예를 들어 서비스 메시는 서비스 간에 네트워킹 통신을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-299">For example, a service mesh could provide networking communication between services.</span></span> <span data-ttu-id="6d41e-300">6apr는 상태 관리 또는 행위자 서비스와 같은 응용 프로그램 서비스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-300">Dapr could provide application services such as state management or actor services.</span></span>

<span data-ttu-id="6d41e-301">그림 2-9에서는 Eapr 및 service 메시 기술을 모두 구현 하는 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-301">Figure 2-9 shows an application that implements both Dapr and service mesh technology.</span></span>

![D apr 및 서비스 메시 함께](./media/dapr-at-20000-feet/dapr-and-service-mesh.png)

<span data-ttu-id="6d41e-303">**그림 2-9**.</span><span class="sxs-lookup"><span data-stu-id="6d41e-303">**Figure 2-9**.</span></span> <span data-ttu-id="6d41e-304">D apr 및 서비스 메시를 함께 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-304">Dapr and service mesh together.</span></span>

<span data-ttu-id="6d41e-305">책에서는 Haishi Bai 및 Yaron Schneider를 [학습](https://www.amazon.com/Learning-Dapr-Building-Distributed-Applications/dp/1492072427/ref=sr_1_1?dchild=1&keywords=dapr&qid=1604794794&sr=8-1)하는 방법에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-305">In the book, [Learning Dapr](https://www.amazon.com/Learning-Dapr-Building-Distributed-Applications/dp/1492072427/ref=sr_1_1?dchild=1&keywords=dapr&qid=1604794794&sr=8-1), authors Haishi Bai and Yaron Schneider, cover the integration of Dapr and service mesh.</span></span>

## <a name="summary"></a><span data-ttu-id="6d41e-306">요약</span><span class="sxs-lookup"><span data-stu-id="6d41e-306">Summary</span></span>

<span data-ttu-id="6d41e-307">이 장에서는 배포 응용 프로그램 런타임 (4 월)을 소개 했습니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-307">This chapter introduced you to Dapr, a Distributed Application Runtime.</span></span>

<span data-ttu-id="6d41e-308">6apr는 고객과 오픈 소스 커뮤니티의 긴밀 한 공동 작업으로 Microsoft에서 후원 한 오픈 소스 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-308">Dapr is an open-source project sponsored by Microsoft with close collaboration from customers and the open-source community.</span></span>

<span data-ttu-id="6d41e-309">코어는 코어에서 분산 마이크로 서비스 응용 프로그램의 내재 된 복잡성을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-309">At its core, Dapr helps reduce the inherent complexity of distributed microservice applications.</span></span> <span data-ttu-id="6d41e-310">블록 Api를 빌드하는 개념을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-310">It's built upon a concept of building block APIs.</span></span> <span data-ttu-id="6d41e-311">다단계 빌딩 블록은 상태 관리, 서비스 간 호출 및 pub/sub 메시징과 같은 일반적인 분산 응용 프로그램 기능을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-311">Dapr building blocks expose common distributed application capabilities, such as state management, service-to-service invocation, and pub/sub messaging.</span></span> <span data-ttu-id="6d41e-312">4 월 구성 요소는 빌딩 블록 아래에 있으며 각 기능에 대 한 구체적인 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-312">Dapr components lie beneath the building blocks and provide the concrete implementation for each capability.</span></span> <span data-ttu-id="6d41e-313">응용 프로그램은 구성 파일을 통해 다양 한 구성 요소에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-313">Applications bind to various components through configuration files.</span></span>

<span data-ttu-id="6d41e-314">다음 장에서는 응용 프로그램에서 d 4를 사용 하는 방법에 대 한 실용적인 실습 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="6d41e-314">In the next chapters, we present practical, hands-on instruction on how to use Dapr in your applications.</span></span>

### <a name="references"></a><span data-ttu-id="6d41e-315">참조</span><span class="sxs-lookup"><span data-stu-id="6d41e-315">References</span></span>

- [<span data-ttu-id="6d41e-316">4apr 설명서</span><span class="sxs-lookup"><span data-stu-id="6d41e-316">Dapr documentation</span></span>](https://dapr.io/)
- [<span data-ttu-id="6d41e-317">66Apr 학습</span><span class="sxs-lookup"><span data-stu-id="6d41e-317">Learning Dapr</span></span>](https://www.amazon.com/Learning-Dapr-Building-Distributed-Applications/dp/1492072427/ref=sr_1_1?dchild=1&keywords=dapr&qid=1604794794&sr=8-1)
- [<span data-ttu-id="6d41e-318">.NET 마이크로 서비스: 컨테이너 화 된 .NET 응용 프로그램에 대 한 아키텍처</span><span class="sxs-lookup"><span data-stu-id="6d41e-318">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)
- [<span data-ttu-id="6d41e-319">Azure 용 Cloud-Native .NET 앱 설계</span><span class="sxs-lookup"><span data-stu-id="6d41e-319">Architecting Cloud-Native .NET Apps for Azure</span></span>](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf)

> [!div class="step-by-step"]
> <span data-ttu-id="6d41e-320">[이전](the-world-is-distributed.md)
> [다음](getting-started.md)</span><span class="sxs-lookup"><span data-stu-id="6d41e-320">[Previous](the-world-is-distributed.md)
[Next](getting-started.md)</span></span>
