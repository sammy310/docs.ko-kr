---
title: Dapr이 배포되어 있습니다.
description: D 4의 용도, 수행 하는 방법 및 작동 방식에 대 한 개략적인 개요입니다.
author: robvet
ms.date: 02/17/2021
ms.openlocfilehash: 6e5d73f8c49ecb3eec518986e2af60c68195c0ab
ms.sourcegitcommit: 5ce37699c2a51ed173171813be68ef7577b1aba5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "104881083"
---
# <a name="dapr-at-20000-feet"></a><span data-ttu-id="bc75b-103">Dapr이 배포되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-103">Dapr at 20,000 feet</span></span>

<span data-ttu-id="bc75b-104">1 장에서는 분산 마이크로 서비스 응용 프로그램에 대해 설명 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-104">In chapter 1, we discussed the appeal of distributed microservice applications.</span></span> <span data-ttu-id="bc75b-105">그러나 아키텍처와 운영 복잡성이 크게 증가 한다는 것을 지적 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-105">But, we also pointed out that they dramatically increase architectural and operational complexity.</span></span> <span data-ttu-id="bc75b-106">이를 염두에 두면이 질문은 어떻게 "케이크를 사용 하 고 있나요?"를 어떻게 할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="bc75b-106">With that in mind, the question becomes, how can you "have your cake" and "eat it too?".</span></span> <span data-ttu-id="bc75b-107">즉, 분산 아키텍처의 민첩성을 활용 하 고 복잡성을 최소화 하려면 어떻게 해야 하나요?</span><span class="sxs-lookup"><span data-stu-id="bc75b-107">That is, how can you take advantage of the agility of distributed architecture, and minimize its complexity?</span></span>

<span data-ttu-id="bc75b-108">Eapr 또는 *Distributed Application Runtime* 은 최신 분산 응용 프로그램을 빌드하는 새로운 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-108">Dapr, or *Distributed Application Runtime*, is a new way to build modern distributed applications.</span></span>

<span data-ttu-id="bc75b-109">프로토타입에서 시작 되는 항목은 매우 성공적인 오픈 소스 프로젝트로 발전 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-109">What started as a prototype has evolved into a highly successful open-source project.</span></span> <span data-ttu-id="bc75b-110">Microsoft의 스폰서는 고객 및 오픈 소스 커뮤니티와 긴밀 하 게 협력 하 여 Eapr를 설계 하 고 구축 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-110">Its sponsor, Microsoft, has closely partnered with customers and the open-source community to design and build Dapr.</span></span> <span data-ttu-id="bc75b-111">이 프로젝트는 모든 배경에서 개발자를 함께 제공 하 여 분산 응용 프로그램 개발의 가장 어려운 문제 중 일부를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-111">The Dapr project brings together developers from all backgrounds to solve some of the toughest challenges of developing distributed applications.</span></span>

<span data-ttu-id="bc75b-112">이 책에서는 .NET 개발자의 관점에서부터부터 4 번째를 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-112">This book looks at Dapr from the viewpoint of a .NET developer.</span></span> <span data-ttu-id="bc75b-113">이 장에서는 Eapr 및 작동 방식에 대 한 개념적인 이해를 구축 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-113">In this chapter, you'll build a conceptual understanding of Dapr and how it works.</span></span> <span data-ttu-id="bc75b-114">나중에 응용 프로그램에서 d 4를 사용 하는 방법에 대 한 실용적인 실습 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-114">Later on, we present practical, hands-on instruction on how you can use Dapr in your applications.</span></span>

<span data-ttu-id="bc75b-115">Jet에서 2만 피트로 비행을 생각해 보세요.</span><span class="sxs-lookup"><span data-stu-id="bc75b-115">Imagine flying in a jet at 20,000 feet.</span></span> <span data-ttu-id="bc75b-116">창을 확인 하 고 광범위 한 관점에서 아래 가로를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-116">You look out the window and see the landscape below from a wide perspective.</span></span> <span data-ttu-id="bc75b-117">D Apr에 대해 동일한 작업을 수행해 보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-117">Let's do the same for Dapr.</span></span> <span data-ttu-id="bc75b-118">2만 피트에서 A4에서 직접 비행을 시각화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-118">Visualize yourself flying over Dapr at 20,000 feet.</span></span> <span data-ttu-id="bc75b-119">표시 되는 내용</span><span class="sxs-lookup"><span data-stu-id="bc75b-119">What would you see?</span></span>

## <a name="dapr-and-the-problem-it-solves"></a><span data-ttu-id="bc75b-120">6apr 및 해결 된 문제</span><span class="sxs-lookup"><span data-stu-id="bc75b-120">Dapr and the problem it solves</span></span>

<span data-ttu-id="bc75b-121">D 4는 최신 분산 응용 프로그램: **복잡성** 에 내재 된 큰 과제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-121">Dapr addresses a large challenge inherent in modern distributed applications: **Complexity**.</span></span>

<span data-ttu-id="bc75b-122">플러그형 구성 요소의 아키텍처를 통해, d 4는 분산 응용 프로그램의 기반이 되는 것을 크게 간소화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-122">Through an architecture of pluggable components, Dapr greatly simplifies the plumbing behind distributed applications.</span></span> <span data-ttu-id="bc75b-123">이 클래스는 응용 프로그램을 Capr 런타임의 인프라 기능과 바인딩하는 **동적 붙이기를** 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-123">It provides a **dynamic glue** that binds your application with infrastructure capabilities from the Dapr runtime.</span></span>

<span data-ttu-id="bc75b-124">서비스의 상태를 변경 하는 데 필요한 요구 사항을 고려 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc75b-124">Consider a requirement to make one of your services stateful?</span></span> <span data-ttu-id="bc75b-125">디자인은 무엇 인가요?</span><span class="sxs-lookup"><span data-stu-id="bc75b-125">What would be your design.</span></span> <span data-ttu-id="bc75b-126">Redis Cache와 같은 상태 저장소를 대상으로 하는 사용자 지정 코드를 작성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-126">You could write custom code that targets a state store such as Redis Cache.</span></span> <span data-ttu-id="bc75b-127">그러나 6Apr는 상태 관리 기능을 기본 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-127">However, Dapr provides state management capabilities out-of-the-box.</span></span> <span data-ttu-id="bc75b-128">서비스는 Capr 구성 **요소 구성** yaml 파일을 통해 상태 저장소 **구성 요소** 에 동적으로 바인딩하는 eapr 상태 관리 **빌딩 블록** 을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-128">Your service invokes the Dapr state management **building block** that dynamically binds to a state store **component** via a Dapr **component configuration** yaml file.</span></span> <span data-ttu-id="bc75b-129">Redis를 포함 하 여 몇 가지 미리 작성 된 상태 저장소 구성 요소가 포함 된 capr.</span><span class="sxs-lookup"><span data-stu-id="bc75b-129">Dapr ships with several pre-built state store components, including Redis.</span></span> <span data-ttu-id="bc75b-130">이 모델을 사용 하면 서비스에서 상태 관리를 Capr 런타임에 위임 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-130">With this model, your service delegates state management to the Dapr runtime.</span></span> <span data-ttu-id="bc75b-131">서비스에 SDK, 라이브러리 또는 기본 구성 요소에 대 한 직접 참조가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-131">Your service has no SDK, library, or direct reference to the underlying component.</span></span> <span data-ttu-id="bc75b-132">코드를 변경 하지 않고도 Redis에서 MySQL 또는 Cassandra로 상태 저장소를 변경할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-132">You can even change state stores, say, from Redis to MySQL or Cassandra, with no code changes.</span></span>

<span data-ttu-id="bc75b-133">그림 2-1에는 2만 피트의 44가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-133">Figure 2-1 shows Dapr from 20,000 feet.</span></span>

<span data-ttu-id="bc75b-134">![2만 피트 피트 ](./media/dapr-at-20000-feet/dapr-high-level.png)
 **그림 2-1**</span><span class="sxs-lookup"><span data-stu-id="bc75b-134">![Dapr at 20,000 feet](./media/dapr-at-20000-feet/dapr-high-level.png)
**Figure 2-1**.</span></span> <span data-ttu-id="bc75b-135">2만 피트</span><span class="sxs-lookup"><span data-stu-id="bc75b-135">Dapr at 20,000 feet.</span></span>

<span data-ttu-id="bc75b-136">그림의 맨 위 행에서 d 4는 인기 있는 개발 플랫폼에 대 한 언어별 Sdk를 제공 하는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-136">In the top row of the figure, note how Dapr provides language-specific SDKs for popular development platforms.</span></span> <span data-ttu-id="bc75b-137">1.0는 Go, Node.js, Python, .NET, Java 및 JavaScript를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-137">Dapr v 1.0 includes supports Go, Node.js, Python, .NET, Java, and JavaScript.</span></span> <span data-ttu-id="bc75b-138">이 책에서는 ASP.NET Core 통합에 대 한 직접적인 지원도 제공 하는 Dapr .NET SDK에 대해 집중적으로 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-138">This book focuses on the Dapr .NET SDK, which also provides direct support for ASP.NET Core integration.</span></span>

<span data-ttu-id="bc75b-139">언어별 Sdk는 개발자 환경을 개선 하는 반면, d 4 월은 플랫폼에 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-139">While language-specific SDKs enhance the developer experience, Dapr is platform agnostic.</span></span> <span data-ttu-id="bc75b-140">내부적으로, 4, 4의 프로그래밍 모델은 표준 HTTP/gRPC 통신 프로토콜을 통해 기능을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-140">Under the hood, Dapr's programming model exposes capabilities through standard HTTP/gRPC communication protocols.</span></span> <span data-ttu-id="bc75b-141">모든 프로그래밍 플랫폼은 네이티브 HTTP 및 gRPC Api를 통해 6Apr를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-141">Any programming platform can call Dapr via its native HTTP and gRPC APIs.</span></span>  

<span data-ttu-id="bc75b-142">그림의 가운데에 있는 파란색 상자는 4 번째 빌딩 블록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-142">The blue boxes across the center of the figure represent the Dapr building blocks.</span></span> <span data-ttu-id="bc75b-143">각는 응용 프로그램에서 사용할 수 있는 배포 응용 프로그램 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-143">Each exposes a distributed application capability that your application can consume.</span></span>

<span data-ttu-id="bc75b-144">아래쪽 행에는 Eapr 및 실행할 수 있는 다양 한 환경에 대 한 이식성이 강조 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-144">The bottom row highlights the portability of Dapr and the diverse environments across which it can run.</span></span>

## <a name="dapr-architecture"></a><span data-ttu-id="bc75b-145">4 월 아키텍처</span><span class="sxs-lookup"><span data-stu-id="bc75b-145">Dapr architecture</span></span>

<span data-ttu-id="bc75b-146">이 시점에서 jet는 계속 해 서 a를 기준으로 하는 Eapr를 전환 하 고 다시 포기 하 여,의 작업 방식에 대해 자세히 살펴봅니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-146">At this point, the jet turns around and flies back over Dapr, descending in altitude, giving you a closer look at how Dapr works.</span></span>

### <a name="building-blocks"></a><span data-ttu-id="bc75b-147">구성 요소</span><span class="sxs-lookup"><span data-stu-id="bc75b-147">Building blocks</span></span>

<span data-ttu-id="bc75b-148">새로운 관점에서 볼 때에는 보다 자세한 정보를 볼 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="bc75b-148">From the new perspective, you see a more detailed view of the Dapr **building blocks**.</span></span>

<span data-ttu-id="bc75b-149">빌딩 블록은 분산 인프라 기능을 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-149">A building block encapsulates a distributed infrastructure capability.</span></span> <span data-ttu-id="bc75b-150">HTTP 또는 gRPC Api를 통해 기능에 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-150">You can access the functionality through the HTTP or gRPC APIs.</span></span> <span data-ttu-id="bc75b-151">그림 2-2에서는 Eapr v 1.0에 사용할 수 있는 블록을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-151">Figure 2-2 shows the available blocks for Dapr v 1.0.</span></span>

![4apr 빌딩 블록](./media/dapr-at-20000-feet/building-blocks.png)

<span data-ttu-id="bc75b-153">**그림 2-2**.</span><span class="sxs-lookup"><span data-stu-id="bc75b-153">**Figure 2-2**.</span></span> <span data-ttu-id="bc75b-154">4apr 빌딩 블록입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-154">Dapr building blocks.</span></span>

<span data-ttu-id="bc75b-155">다음 표에서는 각 블록에서 제공 하는 인프라 서비스에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-155">The following table describes the infrastructure services provided by each block.</span></span>

| <span data-ttu-id="bc75b-156">구성 요소</span><span class="sxs-lookup"><span data-stu-id="bc75b-156">Building block</span></span> | <span data-ttu-id="bc75b-157">Description</span><span class="sxs-lookup"><span data-stu-id="bc75b-157">Description</span></span> |
|----------------|-------------|
| [<span data-ttu-id="bc75b-158">상태 관리</span><span class="sxs-lookup"><span data-stu-id="bc75b-158">State management</span></span>](state-management.md) | <span data-ttu-id="bc75b-159">장기 실행 상태 저장 서비스에 대 한 컨텍스트 정보를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-159">Support contextual information for long running stateful services.</span></span> |
| [<span data-ttu-id="bc75b-160">서비스 호출</span><span class="sxs-lookup"><span data-stu-id="bc75b-160">Service invocation</span></span>](service-invocation.md) | <span data-ttu-id="bc75b-161">플랫폼을 알 수 없는 프로토콜 및 잘 알려진 끝점을 사용 하 여 직접, 보안 서비스 간 호출을 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-161">Invoke direct, secure service-to-service calls using platform agnostic protocols and well-known endpoints.</span></span> |
| [<span data-ttu-id="bc75b-162">게시 및 구독</span><span class="sxs-lookup"><span data-stu-id="bc75b-162">Publish and subscribe</span></span>](publish-subscribe.md) | <span data-ttu-id="bc75b-163">서비스 간에 안전 하 고 확장 가능한 게시/서브 메시징을 구현 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-163">Implement secure, scalable pub/sub messaging between services.</span></span> |
| [<span data-ttu-id="bc75b-164">바인딩</span><span class="sxs-lookup"><span data-stu-id="bc75b-164">Bindings</span></span>](bindings.md) | <span data-ttu-id="bc75b-165">양방향 통신을 사용 하 여 외부 리소스에 의해 발생 한 이벤트에서 코드를 트리거합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-165">Trigger code from events raised by external resources with bi-directional communication.</span></span> |
| [<span data-ttu-id="bc75b-166">가시성</span><span class="sxs-lookup"><span data-stu-id="bc75b-166">Observability</span></span>](observability.md) | <span data-ttu-id="bc75b-167">네트워크 서비스에서 메시지 호출을 모니터링 하 고 측정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-167">Monitor and measure message calls across networked services.</span></span> |
| [<span data-ttu-id="bc75b-168">비밀</span><span class="sxs-lookup"><span data-stu-id="bc75b-168">Secrets</span></span>](secrets.md) | <span data-ttu-id="bc75b-169">외부 암호 저장소에 안전 하 게 액세스 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-169">Securely access external secret stores.</span></span> |
| <span data-ttu-id="bc75b-170">행위자</span><span class="sxs-lookup"><span data-stu-id="bc75b-170">Actors</span></span> | <span data-ttu-id="bc75b-171">다시 사용할 수 있는 행위자 개체에 논리와 데이터를 캡슐화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-171">Encapsulate logic and data in reusable actor objects.</span></span> |

<span data-ttu-id="bc75b-172">구성 요소는 서비스에서 분산 응용 프로그램 기능의 구현을 추상화 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-172">Building blocks abstract the implementation of distributed application capabilities from your services.</span></span> <span data-ttu-id="bc75b-173">그림 2-3에서는 이러한 상호 작용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-173">Figure 2-3 shows this interaction.</span></span>

![4apr 빌딩 블록 통합](./media/dapr-at-20000-feet/building-blocks-integration.png)

<span data-ttu-id="bc75b-175">**그림 2-3**.</span><span class="sxs-lookup"><span data-stu-id="bc75b-175">**Figure 2-3**.</span></span> <span data-ttu-id="bc75b-176">4apr 빌딩 블록 통합.</span><span class="sxs-lookup"><span data-stu-id="bc75b-176">Dapr building block integration.</span></span>

<span data-ttu-id="bc75b-177">빌딩 블록은 각 리소스에 대 한 구체적인 구현을 제공 하는 4 월 구성 요소를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-177">Building blocks invoke Dapr components that provide the concrete implementation for each resource.</span></span> <span data-ttu-id="bc75b-178">서비스에 대 한 코드는 빌딩 블록만 인식 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-178">The code for your service is only aware of the building block.</span></span> <span data-ttu-id="bc75b-179">외부 Sdk 나 라이브러리에 대 한 종속성을 사용 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-179">It takes no dependencies on external SDKs or libraries - Dapr handles the plumbing for you.</span></span> <span data-ttu-id="bc75b-180">각 빌딩 블록은 독립적입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-180">Each building block is independent.</span></span> <span data-ttu-id="bc75b-181">응용 프로그램에서 하나, 일부 또는 모두를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-181">You can use one, some, or all of them in your application.</span></span> <span data-ttu-id="bc75b-182">값 추가로, 종합적인 관찰성을 비롯 한 업계 모범 사례에서 굽기 구성 요소를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-182">As a value-add, Dapr building blocks bake in industry best practices including comprehensive observability.</span></span>

<span data-ttu-id="bc75b-183">이후 장에서 각 4Apr 빌딩 블록에 대 한 자세한 설명 및 코드 샘플을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-183">We provide detailed explanation and code samples for each Dapr building block in the upcoming chapters.</span></span> <span data-ttu-id="bc75b-184">이 시점에서 jet는 훨씬 더 계층이 이어집니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-184">At this point, the jet descends even more.</span></span> <span data-ttu-id="bc75b-185">이제 새로운 관점에서 볼 때에는 이제는 Eapr 구성 요소 계층에 대해 자세히 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-185">From the new perspective, you now have a closer look at the Dapr components layer.</span></span>

### <a name="components"></a><span data-ttu-id="bc75b-186">구성 요소</span><span class="sxs-lookup"><span data-stu-id="bc75b-186">Components</span></span>

<span data-ttu-id="bc75b-187">빌드 블록은 배포 응용 프로그램 기능을 호출 하는 API를 노출 하지만, Capr 구성 요소는 구체적 구현을 제공 하 여이를 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-187">While building blocks expose an API to invoke distributed application capabilities, Dapr components provide the concrete implementation to make it happen.</span></span>

<span data-ttu-id="bc75b-188">예를 들어, Wapr **상태 저장소** 구성 요소를 고려 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-188">Consider, the Dapr **state store** component.</span></span> <span data-ttu-id="bc75b-189">CRUD 작업에 대 한 상태를 관리 하는 일관 된 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-189">It provides a uniform way to manage state for CRUD operations.</span></span> <span data-ttu-id="bc75b-190">서비스 코드를 변경 하지 않으면 다음의 모든 작업 구성 요소 중 하나를 전환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-190">Without any change to your service code, you could switch between any of the following Dapr state components:</span></span>

- <span data-ttu-id="bc75b-191">AWS DynamoDB</span><span class="sxs-lookup"><span data-stu-id="bc75b-191">AWS DynamoDB</span></span>
- <span data-ttu-id="bc75b-192">Aerospike</span><span class="sxs-lookup"><span data-stu-id="bc75b-192">Aerospike</span></span>
- <span data-ttu-id="bc75b-193">Azure Blob Storage</span><span class="sxs-lookup"><span data-stu-id="bc75b-193">Azure Blob Storage</span></span>
- <span data-ttu-id="bc75b-194">Azure CosmosDB</span><span class="sxs-lookup"><span data-stu-id="bc75b-194">Azure CosmosDB</span></span>
- <span data-ttu-id="bc75b-195">Azure Table Storage</span><span class="sxs-lookup"><span data-stu-id="bc75b-195">Azure Table Storage</span></span>
- <span data-ttu-id="bc75b-196">Cassandra</span><span class="sxs-lookup"><span data-stu-id="bc75b-196">Cassandra</span></span>
- <span data-ttu-id="bc75b-197">클라우드 Firestore (데이터 저장소 모드)</span><span class="sxs-lookup"><span data-stu-id="bc75b-197">Cloud Firestore (Datastore mode)</span></span>
- <span data-ttu-id="bc75b-198">CloudState</span><span class="sxs-lookup"><span data-stu-id="bc75b-198">CloudState</span></span>
- <span data-ttu-id="bc75b-199">Couchbase</span><span class="sxs-lookup"><span data-stu-id="bc75b-199">Couchbase</span></span>
- <span data-ttu-id="bc75b-200">Etcd</span><span class="sxs-lookup"><span data-stu-id="bc75b-200">Etcd</span></span>
- <span data-ttu-id="bc75b-201">HashiCorp Consul</span><span class="sxs-lookup"><span data-stu-id="bc75b-201">HashiCorp Consul</span></span>
- <span data-ttu-id="bc75b-202">Hazelcast</span><span class="sxs-lookup"><span data-stu-id="bc75b-202">Hazelcast</span></span>
- <span data-ttu-id="bc75b-203">Memcached</span><span class="sxs-lookup"><span data-stu-id="bc75b-203">Memcached</span></span>
- <span data-ttu-id="bc75b-204">MongoDB</span><span class="sxs-lookup"><span data-stu-id="bc75b-204">MongoDB</span></span>
- <span data-ttu-id="bc75b-205">PostgreSQL</span><span class="sxs-lookup"><span data-stu-id="bc75b-205">PostgreSQL</span></span>
- <span data-ttu-id="bc75b-206">Redis</span><span class="sxs-lookup"><span data-stu-id="bc75b-206">Redis</span></span>
- <span data-ttu-id="bc75b-207">RethinkDB</span><span class="sxs-lookup"><span data-stu-id="bc75b-207">RethinkDB</span></span>
- <span data-ttu-id="bc75b-208">SQL Server</span><span class="sxs-lookup"><span data-stu-id="bc75b-208">SQL Server</span></span>
- <span data-ttu-id="bc75b-209">Zookeeper</span><span class="sxs-lookup"><span data-stu-id="bc75b-209">Zookeeper</span></span>

<span data-ttu-id="bc75b-210">각 구성 요소는 일반적인 상태 관리 인터페이스를 통해 필요한 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-210">Each component provides the necessary implementation through a common state management interface:</span></span>

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
> <span data-ttu-id="bc75b-211">Golang 또는 Go 언어로 작성 된 모든의 4 가지 구성 요소 뿐만 아니라,</span><span class="sxs-lookup"><span data-stu-id="bc75b-211">The Dapr runtime as well as all of the Dapr components have been written in the Golang, or Go, language.</span></span> <span data-ttu-id="bc75b-212">Go는 오픈 소스 커뮤니티에서 널리 사용 되는 언어로, 입증의 플랫폼 간 약정을 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-212">Go is a popular language across the open source community and attests to cross-platform commitment of Dapr.</span></span>

<span data-ttu-id="bc75b-213">Azure Redis Cache에서 상태 저장소로 시작 하는 것일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-213">Perhaps you start with Azure Redis Cache as your state store.</span></span> <span data-ttu-id="bc75b-214">다음 구성을 사용 하 여 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-214">You specify it with the following configuration:</span></span>

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

<span data-ttu-id="bc75b-215">**사양** 섹션에서 상태 관리에 대 한 Redis Cache를 사용 하도록 6apr를 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-215">In the **spec** section, you configure Dapr to use the Redis Cache for state management.</span></span> <span data-ttu-id="bc75b-216">또한이 섹션에서는 구성 요소별 메타 데이터를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-216">The section also contains component-specific metadata.</span></span> <span data-ttu-id="bc75b-217">이 경우 추가 Redis 설정을 구성 하는 데 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-217">In this case, you can use it to configure additional Redis settings.</span></span>

<span data-ttu-id="bc75b-218">나중에 응용 프로그램을 프로덕션 환경으로 이동할 준비가 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-218">At a later time, the application is ready to go to production.</span></span> <span data-ttu-id="bc75b-219">프로덕션 환경의 경우 상태 관리를 Azure Table Storage로 변경 해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-219">For the production environment, you may want to change your state management to Azure Table Storage.</span></span> <span data-ttu-id="bc75b-220">Azure Table Storage는 경제적이 고 내구성이 뛰어난 상태 관리 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-220">Azure Table Storage provides state management capabilities that are affordable and highly durable.</span></span>

<span data-ttu-id="bc75b-221">이 문서를 작성할 당시에는 다음과 같은 구성 요소 유형을 d 4에서 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-221">At the time of this writing, the following component types are provided by Dapr:</span></span>

| <span data-ttu-id="bc75b-222">구성 요소</span><span class="sxs-lookup"><span data-stu-id="bc75b-222">Component</span></span> | <span data-ttu-id="bc75b-223">Description</span><span class="sxs-lookup"><span data-stu-id="bc75b-223">Description</span></span> |
|-----------|-------------|
| [<span data-ttu-id="bc75b-224">서비스 검색</span><span class="sxs-lookup"><span data-stu-id="bc75b-224">Service discovery</span></span>](https://github.com/dapr/components-contrib/tree/master/nameresolution) | <span data-ttu-id="bc75b-225">서비스 간 검색을 제공 하기 위해 호스팅 환경과 통합 하는 서비스 호출 구성 요소에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-225">Used by the service invocation building block to integrate with the hosting environment to provide service-to-service discovery.</span></span> |
| [<span data-ttu-id="bc75b-226">State</span><span class="sxs-lookup"><span data-stu-id="bc75b-226">State</span></span>](https://github.com/dapr/components-contrib/tree/master/state) | <span data-ttu-id="bc75b-227">다양 한 상태 저장소 구현과 상호 작용 하기 위한 균일 한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-227">Provides a uniform interface to interact with a wide variety of state store implementations.</span></span> |
| [<span data-ttu-id="bc75b-228">Pub/sub</span><span class="sxs-lookup"><span data-stu-id="bc75b-228">Pub/sub</span></span>](https://github.com/dapr/components-contrib/tree/master/pubsub) | <span data-ttu-id="bc75b-229">다양 한 메시지 버스 구현과 상호 작용 하기 위한 균일 한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-229">Provides a uniform interface to interact with a wide variety of message bus implementations.</span></span> |
| [<span data-ttu-id="bc75b-230">바인딩</span><span class="sxs-lookup"><span data-stu-id="bc75b-230">Bindings</span></span>](https://github.com/dapr/components-contrib/tree/master/bindings) | <span data-ttu-id="bc75b-231">외부 시스템에서 응용 프로그램 이벤트를 트리거하고 선택적 데이터 페이로드가 있는 외부 시스템을 호출 하는 일관 된 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-231">Provides a uniform interface to trigger application events from external systems and invoke external systems with optional data payloads.</span></span> |
| [<span data-ttu-id="bc75b-232">미들웨어</span><span class="sxs-lookup"><span data-stu-id="bc75b-232">Middleware</span></span>](https://github.com/dapr/components-contrib/tree/master/middleware) | <span data-ttu-id="bc75b-233">사용자 지정 미들웨어가 요청 처리 파이프라인에 연결 하 고 요청 또는 응답에 대 한 추가 작업을 호출할 수 있도록 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-233">Allows custom middleware to plug into the request processing pipeline and invoke additional actions on a request or response.</span></span> |
| [<span data-ttu-id="bc75b-234">비밀 저장소</span><span class="sxs-lookup"><span data-stu-id="bc75b-234">Secret stores</span></span>](https://github.com/dapr/components-contrib/tree/master/secretstores) | <span data-ttu-id="bc75b-235">클라우드,에 지, 상용, 오픈 소스 서비스를 비롯 하 여 외부 암호 저장소와 상호 작용 하는 일관 된 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-235">Provides a uniform interface to interact with external secret stores, including cloud, edge, commercial, open-source services.</span></span> |

<span data-ttu-id="bc75b-236">Jet가 d 4의 즉석에서 날아오기를 완료 하는 경우에는 나중에 다시 연결 하 여 함께 연결 하는 방법을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-236">As the jet completes its fly over of Dapr, you look back once more and can see how it connects together.</span></span>

### <a name="sidecar-architecture"></a><span data-ttu-id="bc75b-237">사이드카 아키텍처</span><span class="sxs-lookup"><span data-stu-id="bc75b-237">Sidecar architecture</span></span>

<span data-ttu-id="bc75b-238">[사이드카 아키텍처](/azure/architecture/patterns/sidecar)를 통해 구성 요소 및 구성 요소를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-238">Dapr exposes its building blocks and components through a [sidecar architecture](/azure/architecture/patterns/sidecar).</span></span> <span data-ttu-id="bc75b-239">사이드카를 사용 하면 다른 메모리 프로세스에서 또는 서비스와 함께 별도의 컨테이너에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-239">A sidecar enables Dapr to run in a separate memory process or separate container alongside your service.</span></span> <span data-ttu-id="bc75b-240">사이드카는 서비스에 포함 되지 않고 연결 된 격리 및 캡슐화를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-240">Sidecars provide isolation and encapsulation as they aren't part of the service, but connected to it.</span></span> <span data-ttu-id="bc75b-241">이러한 분리를 통해 각각 고유한 런타임 환경을 보유 하 고 다양 한 프로그래밍 플랫폼을 기반으로 빌드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-241">This separation enables each to have its own runtime environment and be built upon different programming platforms.</span></span> <span data-ttu-id="bc75b-242">그림 2-4에서는 사이드카 패턴을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-242">Figure 2-4 shows a sidecar pattern.</span></span>

![사이드카 아키텍처](./media/dapr-at-20000-feet/sidecar-generic.png)

<span data-ttu-id="bc75b-244">**그림 2-4**.</span><span class="sxs-lookup"><span data-stu-id="bc75b-244">**Figure 2-4**.</span></span> <span data-ttu-id="bc75b-245">사이드카 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="bc75b-245">Sidecar architecture.</span></span>

<span data-ttu-id="bc75b-246">이 패턴은 오토바이에 연결된 사이드카와 유사하므로 사이드카라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-246">This pattern is named Sidecar because it resembles a sidecar attached to a motorcycle.</span></span> <span data-ttu-id="bc75b-247">위의 그림에서 배포 응용 프로그램 기능을 제공 하기 위해 사이드카이 서비스에 연결 되는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-247">In the previous figure, note how the Dapr sidecar is attached to your service to provide distributed application capabilities.</span></span>

### <a name="hosting-environments"></a><span data-ttu-id="bc75b-248">호스팅 환경</span><span class="sxs-lookup"><span data-stu-id="bc75b-248">Hosting environments</span></span>

<span data-ttu-id="bc75b-249">D apr는 플랫폼 간 지원을 제공 하며 다양 한 환경에서 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-249">Dapr has cross-platform support and can run in many different environments.</span></span> <span data-ttu-id="bc75b-250">이러한 환경에는 Kubernetes, Vm 그룹 또는 Azure IoT Edge와 같은에 지 환경이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-250">These environments include Kubernetes, a group of VMs, or edge environments such as Azure IoT Edge.</span></span>

<span data-ttu-id="bc75b-251">로컬 개발의 경우 시작 하는 가장 쉬운 방법은 [자체 호스팅 모드](https://docs.dapr.io/concepts/overview/#self-hosted)를 사용 하는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-251">For local development, the easiest way to get started is with [self-hosted mode](https://docs.dapr.io/concepts/overview/#self-hosted).</span></span> <span data-ttu-id="bc75b-252">자체 호스팅 모드에서 마이크로 서비스와 사이드카는 Kubernetes와 같은 컨테이너 orchestrator 없이 별도의 로컬 프로세스에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-252">In self-hosted mode, the microservices and Dapr sidecars run in separate local processes without a container orchestrator such as Kubernetes.</span></span> <span data-ttu-id="bc75b-253">자세한 내용은 [Eapr CLI 다운로드 및 설치](https://docs.dapr.io/getting-started/install-dapr/)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc75b-253">For more information, see [download and install the Dapr CLI](https://docs.dapr.io/getting-started/install-dapr/).</span></span>

<span data-ttu-id="bc75b-254">그림 2-5에서는 HTTP 또는 gRPC를 통해 통신 하는 두 개의 별도 메모리 프로세스에서 호스팅되는 응용 프로그램 및 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-254">Figure 2-5 shows an application and Dapr hosted in two separate memory processes communicating via HTTP or gRPC.</span></span>

![자체 호스팅 사이드카 아키텍처](./media/dapr-at-20000-feet/self-hosted-dapr-sidecar.png)

<span data-ttu-id="bc75b-256">**그림 2-5**.</span><span class="sxs-lookup"><span data-stu-id="bc75b-256">**Figure 2-5**.</span></span> <span data-ttu-id="bc75b-257">자체 호스팅 사이드카.</span><span class="sxs-lookup"><span data-stu-id="bc75b-257">Self-hosted Dapr sidecar.</span></span>

<span data-ttu-id="bc75b-258">기본적으로 Redis 및 Zipkin에 대 한 Docker 컨테이너를 설치 하 여 기본 상태 관리 및 관찰성를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-258">By default, Dapr installs Docker containers for Redis and Zipkin to provide default state management and observability.</span></span> <span data-ttu-id="bc75b-259">로컬 컴퓨터에 Docker를 설치 하지 않으려면 [docker 컨테이너 없이도 자체 호스팅 모드에서](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/)docker를 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-259">If you don't want to install Docker on your local machine, you can even [run Dapr in self-hosted mode without any Docker containers](https://docs.dapr.io/operations/hosting/self-hosted/self-hosted-no-docker/).</span></span> <span data-ttu-id="bc75b-260">그러나 상태 관리 및 pub/sub에 대해 Redis 같은 기본 구성 요소를 수동으로 설치 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-260">However, you must install default components such as Redis for state management and pub/sub manually.</span></span>

<span data-ttu-id="bc75b-261">또한 컨테이너 화 된는 Kubernetes와 같은 [환경](https://docs.dapr.io/concepts/overview/#kubernetes-hosted)에서 실행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-261">Dapr also runs in [containerized environments](https://docs.dapr.io/concepts/overview/#kubernetes-hosted), such as Kubernetes.</span></span> <span data-ttu-id="bc75b-262">그림 2-6에는 동일한 Kubernetes pod의 응용 프로그램 컨테이너와 함께 별도의 측면과 자동차 컨테이너에서 실행 되는 4 개의가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-262">Figure 2-6 shows Dapr running in a separate side-car container along with the application container in the same Kubernetes pod.</span></span>

![Kubernetes-호스팅된 사이드카 아키텍처](./media/dapr-at-20000-feet/kubernetes-hosted-dapr-sidecar.png)

<span data-ttu-id="bc75b-264">**그림 2-6**.</span><span class="sxs-lookup"><span data-stu-id="bc75b-264">**Figure 2-6**.</span></span> <span data-ttu-id="bc75b-265">Kubernetes-호스 티 드 사이드카.</span><span class="sxs-lookup"><span data-stu-id="bc75b-265">Kubernetes-hosted Dapr sidecar.</span></span>

## <a name="dapr-performance-considerations"></a><span data-ttu-id="bc75b-266">4 월 성능 고려 사항</span><span class="sxs-lookup"><span data-stu-id="bc75b-266">Dapr performance considerations</span></span>

<span data-ttu-id="bc75b-267">앞서 살펴본 것 처럼 사이드카 아키텍처를 노출 하 여 응용 프로그램을 분산 응용 프로그램 기능에서 분리 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-267">As you've seen, Dapr exposes a sidecar architecture to decouple your application from distributed application capabilities.</span></span> <span data-ttu-id="bc75b-268">Eapr 작업을 호출 하려면 적어도 하나 이상의 out-of-process 네트워크 호출이 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-268">Invoking a Dapr operation requires at least one out-of-process network call.</span></span> <span data-ttu-id="bc75b-269">그림 2-7에는 4Apr 트래픽 패턴의 예가 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-269">Figure 2-7 presents an example of a Dapr traffic pattern.</span></span>

![4apr 트래픽 패턴](./media/dapr-at-20000-feet/dapr-traffic-patterns.png)

<span data-ttu-id="bc75b-271">**그림 2-7**.</span><span class="sxs-lookup"><span data-stu-id="bc75b-271">**Figure 2-7**.</span></span> <span data-ttu-id="bc75b-272">4apr 트래픽 패턴.</span><span class="sxs-lookup"><span data-stu-id="bc75b-272">Dapr traffic patterns.</span></span>

<span data-ttu-id="bc75b-273">위의 그림을 보면 각 호출에 대해 발생 하는 대기 시간 및 오버 헤드를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-273">Looking at the previous figure, one might question the latency and overhead incurred for each call.</span></span>  

<span data-ttu-id="bc75b-274">4Apr 팀은 성능에 많은 투자를 받았습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-274">The Dapr team has invested heavily in performance.</span></span> <span data-ttu-id="bc75b-275">엄청난 규모의 엔지니어링 노력으로 인해 4 월 효율적으로 작성 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-275">A tremendous amount of engineering effort has gone into making Dapr efficient.</span></span> <span data-ttu-id="bc75b-276">Eapr 사이드카 간의 호출은 항상 높은 성능과 작은 이진 페이로드를 제공 하는 gRPC를 사용 하 여 수행 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-276">Calls between Dapr sidecars are always made with gRPC, which delivers high performance and small binary payloads.</span></span> <span data-ttu-id="bc75b-277">대부분의 경우 추가 오버 헤드는 하위 밀리초 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-277">In most cases, the additional overhead should be sub-millisecond.</span></span>

<span data-ttu-id="bc75b-278">개발자는 성능을 향상 시키기 위해 gRPC를 사용 하 여 4Apr 빌딩 블록을 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-278">To increase performance, developers can call the Dapr building blocks with gRPC.</span></span>

<span data-ttu-id="bc75b-279">gRPC는 오래 된 [원격 프로시저 호출 (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) 프로토콜을 진화 하는 현대적인 고성능 프레임 워크입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-279">gRPC is a modern, high-performance framework that evolves the age-old [remote procedure call (RPC)](https://en.wikipedia.org/wiki/Remote_procedure_call) protocol.</span></span> <span data-ttu-id="bc75b-280">gRPC는 전송 프로토콜에 대해 HTTP/2를 사용 하며, 다음을 포함 하 여 HTTP RESTFul 서비스 보다 상당한 성능 향상을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-280">gRPC uses HTTP/2 for its transport protocol, which provides significant performance enhancements over HTTP RESTFul service, including:</span></span>

- <span data-ttu-id="bc75b-281">동일한 연결을 통해 여러 병렬 요청을 보내기 위한 멀티플렉싱 지원-HTTP 1.1는 한 번에 하나의 요청/응답 메시지로 처리를 제한 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-281">Multiplexing support for sending multiple parallel requests over the same connection - HTTP 1.1 limits processing to one request/response message at a time.</span></span>
- <span data-ttu-id="bc75b-282">클라이언트 요청과 서버 응답을 동시에 전송 하기 위한 양방향 전이중 통신입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-282">Bidirectional full-duplex communication for sending both client requests and server responses simultaneously.</span></span>
- <span data-ttu-id="bc75b-283">대량 데이터 집합을 비동기적으로 스트림 하는 요청 및 응답을 설정 하는 기본 제공 스트리밍입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-283">Built-in streaming enabling requests and responses to asynchronously stream large data sets.</span></span>

<span data-ttu-id="bc75b-284">자세한 내용은 [Azure 전자책에 대 한 .Net 앱 설계 Cloud-Native](../cloud-native/index.md) 에서 [grpc 개요](../cloud-native/grpc.md#what-is-grpc) 를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc75b-284">To learn more, check out the [gRPC overview](../cloud-native/grpc.md#what-is-grpc) from the [Architecting Cloud-Native .NET Apps for Azure](../cloud-native/index.md) eBook.</span></span>  

## <a name="dapr-and-service-meshes"></a><span data-ttu-id="bc75b-285">4apr 및 서비스 메시</span><span class="sxs-lookup"><span data-stu-id="bc75b-285">Dapr and service meshes</span></span>

<span data-ttu-id="bc75b-286">서비스 메시는 분산 응용 프로그램에 대 한 또 다른 빠르게 진화 하는 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-286">Service mesh is another rapidly evolving technology for distributed applications.</span></span>

<span data-ttu-id="bc75b-287">서비스 메시는 서비스 간 통신, 복원 력, 부하 분산 및 원격 분석 캡처를 처리 하는 기본 제공 기능이 포함 된 구성 가능한 인프라 계층입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-287">A service mesh is a configurable infrastructure layer with built-in capabilities to handle service-to-service communication, resiliency, load balancing, and telemetry capture.</span></span> <span data-ttu-id="bc75b-288">서비스 및 서비스 메시 계층으로 이러한 문제에 대 한 책임을 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-288">It moves the responsibility for these concerns out of the services and into the service mesh layer.</span></span> <span data-ttu-id="bc75b-289">Eapr와 마찬가지로 서비스 메시도 사이드카 아키텍처를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-289">Like Dapr, a service mesh also follows a sidecar architecture.</span></span>

<span data-ttu-id="bc75b-290">그림 2-8에서는 서비스 메시 기술을 구현 하는 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-290">Figure 2-8 shows an application that implements service mesh technology.</span></span>

![서비스 메시](./media/dapr-at-20000-feet/service-mesh-with-side-car.png)

<span data-ttu-id="bc75b-292">**그림 2-8**.</span><span class="sxs-lookup"><span data-stu-id="bc75b-292">**Figure 2-8**.</span></span> <span data-ttu-id="bc75b-293">측 자동차를 사용 하는 서비스 메시.</span><span class="sxs-lookup"><span data-stu-id="bc75b-293">Service mesh with a side car.</span></span>

<span data-ttu-id="bc75b-294">위의 그림은 각 서비스와 함께 실행 되는 사이드카 프록시가 메시지를 가로채는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-294">The previous figure shows how messages are intercepted by a sidecar proxy that runs alongside each service.</span></span> <span data-ttu-id="bc75b-295">각 프록시는 서비스와 관련 된 트래픽 규칙으로 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-295">Each proxy can be configured with traffic rules specific to the service.</span></span> <span data-ttu-id="bc75b-296">메시지를 이해 하 고 서비스와 외부 세계에서 메시지를 라우팅할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-296">It understands messages and can route them across your services and the outside world.</span></span>

<span data-ttu-id="bc75b-297">따라서 "서비스 메시는 ' 서비스 메시 인가요?" 라는 질문이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-297">So the question becomes, "Is Dapr a service mesh?".</span></span>

<span data-ttu-id="bc75b-298">둘 다 사이드카 아키텍처를 사용 하는 반면 각 기술은 다른 용도로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-298">While both use a sidecar architecture, each technology has a different purpose.</span></span> <span data-ttu-id="bc75b-299">D 4는 배포 응용 프로그램 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-299">Dapr provides distributed application features.</span></span> <span data-ttu-id="bc75b-300">서비스 메시는 전용 네트워크 인프라 계층을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-300">A service mesh provides a dedicated network infrastructure layer.</span></span>

<span data-ttu-id="bc75b-301">서로 다른 수준에서 작동 하는 경우 모두 동일한 응용 프로그램에서 함께 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-301">As each works at a different level, both can work together in the same application.</span></span> <span data-ttu-id="bc75b-302">예를 들어 서비스 메시는 서비스 간에 네트워킹 통신을 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-302">For example, a service mesh could provide networking communication between services.</span></span> <span data-ttu-id="bc75b-303">6apr는 상태 관리 또는 행위자 서비스와 같은 응용 프로그램 서비스를 제공할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-303">Dapr could provide application services such as state management or actor services.</span></span>

<span data-ttu-id="bc75b-304">그림 2-9에서는 Eapr 및 service 메시 기술을 모두 구현 하는 응용 프로그램을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-304">Figure 2-9 shows an application that implements both Dapr and service mesh technology.</span></span>

![D apr 및 서비스 메시 함께](./media/dapr-at-20000-feet/dapr-and-service-mesh.png)

<span data-ttu-id="bc75b-306">**그림 2-9**.</span><span class="sxs-lookup"><span data-stu-id="bc75b-306">**Figure 2-9**.</span></span> <span data-ttu-id="bc75b-307">D apr 및 서비스 메시를 함께 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-307">Dapr and service mesh together.</span></span>

<span data-ttu-id="bc75b-308">D [apr 온라인 설명서](https://docs.dapr.io/concepts/faq/#networking-and-service-meshes) 에는 eapr 및 service 메시 통합이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-308">The [Dapr online documentation](https://docs.dapr.io/concepts/faq/#networking-and-service-meshes) cover Dapr and service mesh integration.</span></span>

## <a name="summary"></a><span data-ttu-id="bc75b-309">요약</span><span class="sxs-lookup"><span data-stu-id="bc75b-309">Summary</span></span>

<span data-ttu-id="bc75b-310">이 장에서는 배포 응용 프로그램 런타임 (4 월)을 소개 했습니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-310">This chapter introduced you to Dapr, a Distributed Application Runtime.</span></span>

<span data-ttu-id="bc75b-311">6apr는 고객과 오픈 소스 커뮤니티의 긴밀 한 공동 작업으로 Microsoft에서 후원 한 오픈 소스 프로젝트입니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-311">Dapr is an open-source project sponsored by Microsoft with close collaboration from customers and the open-source community.</span></span>

<span data-ttu-id="bc75b-312">코어는 코어에서 분산 마이크로 서비스 응용 프로그램의 내재 된 복잡성을 줄이는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-312">At its core, Dapr helps reduce the inherent complexity of distributed microservice applications.</span></span> <span data-ttu-id="bc75b-313">블록 Api를 빌드하는 개념을 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-313">It's built upon a concept of building block APIs.</span></span> <span data-ttu-id="bc75b-314">다단계 빌딩 블록은 상태 관리, 서비스 간 호출 및 pub/sub 메시징과 같은 일반적인 분산 응용 프로그램 기능을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-314">Dapr building blocks expose common distributed application capabilities, such as state management, service-to-service invocation, and pub/sub messaging.</span></span> <span data-ttu-id="bc75b-315">4 월 구성 요소는 빌딩 블록 아래에 있으며 각 기능에 대 한 구체적인 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-315">Dapr components lie beneath the building blocks and provide the concrete implementation for each capability.</span></span> <span data-ttu-id="bc75b-316">응용 프로그램은 구성 파일을 통해 다양 한 구성 요소에 바인딩됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-316">Applications bind to various components through configuration files.</span></span>

<span data-ttu-id="bc75b-317">다음 장에서는 응용 프로그램에서 d 4를 사용 하는 방법에 대 한 실용적인 실습 지침을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc75b-317">In the next chapters, we present practical, hands-on instruction on how to use Dapr in your applications.</span></span>

### <a name="references"></a><span data-ttu-id="bc75b-318">참조</span><span class="sxs-lookup"><span data-stu-id="bc75b-318">References</span></span>

- [<span data-ttu-id="bc75b-319">4apr 설명서</span><span class="sxs-lookup"><span data-stu-id="bc75b-319">Dapr documentation</span></span>](https://dapr.io/)
- [<span data-ttu-id="bc75b-320">66Apr 학습</span><span class="sxs-lookup"><span data-stu-id="bc75b-320">Learning Dapr</span></span>](https://www.amazon.com/Learning-Dapr-Building-Distributed-Applications/dp/1492072427/ref=sr_1_1?dchild=1&keywords=dapr&qid=1604794794&sr=8-1)
- [<span data-ttu-id="bc75b-321">.NET 마이크로 서비스: 컨테이너 화 된 .NET 응용 프로그램에 대 한 아키텍처</span><span class="sxs-lookup"><span data-stu-id="bc75b-321">.NET Microservices: Architecture for Containerized .NET applications</span></span>](https://dotnet.microsoft.com/download/thank-you/microservices-architecture-ebook)
- [<span data-ttu-id="bc75b-322">Azure 용 Cloud-Native .NET 앱 설계</span><span class="sxs-lookup"><span data-stu-id="bc75b-322">Architecting Cloud-Native .NET Apps for Azure</span></span>](https://dotnet.microsoft.com/download/e-book/cloud-native-azure/pdf)

> [!div class="step-by-step"]
> <span data-ttu-id="bc75b-323">[이전](the-world-is-distributed.md)
> [다음](getting-started.md)</span><span class="sxs-lookup"><span data-stu-id="bc75b-323">[Previous](the-world-is-distributed.md)
[Next](getting-started.md)</span></span>
