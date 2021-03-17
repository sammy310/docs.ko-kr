---
title: Eapr 관찰성 빌딩 블록
description: 관찰성 빌딩 블록에 대 한 설명, 해당 기능, 이점 및 적용 방법
author: edwinvw
ms.date: 02/17/2021
ms.reviewer: robvet
ms.openlocfilehash: 745b9c07c31cc3ee11d5df945f2ccb87d0c9c2ed
ms.sourcegitcommit: d623f686701b94bef905ec5e93d8b55d031c5d6f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/17/2021
ms.locfileid: "103623982"
---
# <a name="the-dapr-observability-building-block"></a><span data-ttu-id="b1bfc-103">Eapr 관찰성 빌딩 블록</span><span class="sxs-lookup"><span data-stu-id="b1bfc-103">The Dapr observability building block</span></span>

<span data-ttu-id="b1bfc-104">최신 분산 시스템은 복잡 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-104">Modern distributed systems are complex.</span></span> <span data-ttu-id="b1bfc-105">느슨하게 결합 되 고 독립적으로 배포 가능한 작은 서비스로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-105">You start with small, loosely coupled, independently deployable services.</span></span> <span data-ttu-id="b1bfc-106">이러한 서비스는 프로세스 및 서버 경계를 교차 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-106">These services cross process and server boundaries.</span></span> <span data-ttu-id="b1bfc-107">그런 다음 다른 종류의 인프라 지원 서비스 (데이터베이스, 메시지 브로커, 키 자격 증명 모음)를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-107">They then consume different kinds of infrastructure backing services (databases, message brokers, key vaults).</span></span> <span data-ttu-id="b1bfc-108">마지막으로 이러한 개별 요소를 함께 구성 하 여 응용 프로그램을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-108">Finally, these disparate pieces compose together to form an application.</span></span>

<span data-ttu-id="b1bfc-109">서로 다른 여러 부분으로 이동 하는 경우 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="b1bfc-109">With so many separate, moving parts, how do you make sense of what is going on?</span></span> <span data-ttu-id="b1bfc-110">불행 하 게도 과거의 레거시 모니터링 접근 방식이 충분 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-110">Unfortunately, legacy monitoring approaches from the past aren't enough.</span></span> <span data-ttu-id="b1bfc-111">대신 시스템은 종단 간에서 **관찰** 가능 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-111">Instead, the system must be **observable** from end-to-end.</span></span> <span data-ttu-id="b1bfc-112">최신 [관찰성](../cloud-native/observability-patterns.md) 사례는 응용 프로그램의 상태에 대 한 가시성과 통찰력을 항상 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-112">Modern [observability](../cloud-native/observability-patterns.md) practices provide visibility and insight into the health of the application at all times.</span></span> <span data-ttu-id="b1bfc-113">이를 통해 출력을 관찰 하 여 내부 상태를 유추할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-113">They enable you to infer the internal state by observing the output.</span></span> <span data-ttu-id="b1bfc-114">관찰성는 분산 응용 프로그램 모니터링 및 문제 해결에 필수적입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-114">Observability is mandatory for monitoring and troubleshooting distributed applications.</span></span>

<span data-ttu-id="b1bfc-115">관찰성를 얻는 데 사용 되는 시스템 정보를 **원격 분석** 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-115">The system information used to gain observability is referred to as **telemetry**.</span></span> <span data-ttu-id="b1bfc-116">다음 네 가지 광범위 한 범주로 나눌 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-116">It can be divided into four broad categories:</span></span>

1. <span data-ttu-id="b1bfc-117">**분산 추적은** 분산 트랜잭션과 관련 된 서비스와 서비스 간의 트래픽에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-117">**Distributed tracing** provides insight into the traffic between services and services involved in distributed transactions.</span></span>
1. <span data-ttu-id="b1bfc-118">**메트릭은** 서비스 성능 및 해당 리소스 소비에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-118">**Metrics** provides insight into the performance of a service and its resource consumption.</span></span>
1. <span data-ttu-id="b1bfc-119">**로깅은** 코드가 실행 되는 방법 및 오류가 발생 한 경우에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-119">**Logging** provides insight into how the code is executing and if errors have occurred.</span></span>
1. <span data-ttu-id="b1bfc-120">**상태** 끝점은 서비스의 가용성에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-120">**Health** endpoints provide insight into the availability of a service.</span></span>

<span data-ttu-id="b1bfc-121">원격 분석의 깊이는 응용 프로그램 플랫폼의 관찰성 기능에 의해 결정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-121">The depth of telemetry is determined by the observability features of an application platform.</span></span> <span data-ttu-id="b1bfc-122">Azure cloud를 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-122">Consider the Azure cloud.</span></span> <span data-ttu-id="b1bfc-123">모든 원격 분석 범주를 포함 하는 다양 한 원격 분석 환경을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-123">It provides a rich telemetry experience that includes all of the telemetry categories.</span></span> <span data-ttu-id="b1bfc-124">구성 없이 대부분의 Azure IaaS 및 PaaS 서비스는 [Azure 애플리케이션 Insights](/azure/azure-monitor/app/app-insights-overview) 서비스에 원격 분석을 전파 하 고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-124">Without any configuration, most Azure IaaS and PaaS services propagate and publish telemetry to the [Azure Application Insights](/azure/azure-monitor/app/app-insights-overview) service.</span></span> <span data-ttu-id="b1bfc-125">Application Insights은 시각적 대시보드가 매우 많은 시스템 로깅, 추적 및 문제 영역을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-125">Application Insights presents system logging, tracing, and problem areas with highly visual dashboards.</span></span> <span data-ttu-id="b1bfc-126">통신을 기반으로 하는 서비스 간의 종속성을 보여 주는 다이어그램도 렌더링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-126">It can even render a diagram showing the dependencies between services based on their communication.</span></span>

<span data-ttu-id="b1bfc-127">그러나 응용 프로그램에서 Azure PaaS 및 IaaS 리소스를 사용할 수 없는 경우는 어떻게 되나요?</span><span class="sxs-lookup"><span data-stu-id="b1bfc-127">However, what if an application can't use Azure PaaS and IaaS resources?</span></span> <span data-ttu-id="b1bfc-128">Application Insights의 다양 한 원격 분석 환경을 활용할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b1bfc-128">Is it still possible to take advantage of the rich telemetry experience of Application Insights?</span></span> <span data-ttu-id="b1bfc-129">대답은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-129">The answer is yes.</span></span> <span data-ttu-id="b1bfc-130">비 Azure 응용 프로그램은 라이브러리를 가져오고, 구성을 추가 하 고, 코드를 계측 하 여 원격 분석을 Azure 애플리케이션 Insights로 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-130">A non-Azure application can import libraries, add configuration, and instrument code to emit telemetry to Azure Application Insights.</span></span> <span data-ttu-id="b1bfc-131">그러나이 방법은 응용 프로그램을 Application Insights에 긴밀 하 게 **결합** .</span><span class="sxs-lookup"><span data-stu-id="b1bfc-131">However, this approach **tightly couples** the application to Application Insights.</span></span> <span data-ttu-id="b1bfc-132">앱을 다른 모니터링 플랫폼으로 이동 하는 것은 비용이 많이 드는 리팩터링을 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-132">Moving the app to a different monitoring platform could involve expensive refactoring.</span></span> <span data-ttu-id="b1bfc-133">코드 외부에서 관찰성를 사용 하 고 결합 하는 것을 방지 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-133">Wouldn't it be great to avoid tight coupling and consume observability outside of the code?</span></span>

<span data-ttu-id="b1bfc-134">Eapr를 사용 하면 가능 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-134">With Dapr, you can.</span></span> <span data-ttu-id="b1bfc-135">관찰성가 배포 응용 프로그램에를 추가할 수 있는 방법을 살펴보겠습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-135">Let's look at how Dapr can add observability to our distributed applications.</span></span>

## <a name="what-it-solves"></a><span data-ttu-id="b1bfc-136">해결 방법</span><span class="sxs-lookup"><span data-stu-id="b1bfc-136">What it solves</span></span>

<span data-ttu-id="b1bfc-137">응용 프로그램에서의 관찰성 분리 관찰성 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-137">The Dapr observability building block decouples observability from the application.</span></span> <span data-ttu-id="b1bfc-138">이 도구는 사이드카에서 생성 하는 트래픽을 자동으로 캡처합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-138">It automatically captures traffic generated by Dapr sidecars and Dapr system services that make up the Dapr control plane.</span></span> <span data-ttu-id="b1bfc-139">블록은 여러 서비스에 걸쳐 있는 단일 작업의 트래픽을 연관 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-139">The block correlates traffic from a single operation that spans multiple services.</span></span> <span data-ttu-id="b1bfc-140">또한 성능 메트릭, 리소스 사용률 및 시스템 상태를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-140">It also exposes performance metrics, resource utilization, and the health of the system.</span></span> <span data-ttu-id="b1bfc-141">원격 분석은 선택의 모니터링 백 엔드에 정보를 공급할 수 있도록 하는 오픈 표준 형식으로 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-141">Telemetry is published in open-standard formats enabling information to be fed into your monitoring back end of choice.</span></span> <span data-ttu-id="b1bfc-142">여기에서 정보를 시각화, 쿼리 및 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-142">There, the information can be visualized, queried, and analyzed.</span></span>

<span data-ttu-id="b1bfc-143">관찰성를 추상화 하는 경우 응용 프로그램은 구현 방법을 인식 하지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-143">As Dapr abstracts away the plumbing, the application is unaware of how observability is implemented.</span></span> <span data-ttu-id="b1bfc-144">라이브러리를 참조 하거나 사용자 지정 계측 코드를 구현할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-144">There's no need to reference libraries or implement custom instrumentation code.</span></span> <span data-ttu-id="b1bfc-145">관찰성는 개발자가 비즈니스 논리를 구축 하는 데 집중할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-145">Dapr allows the developer to focus on building business logic and not observability plumbing.</span></span> <span data-ttu-id="b1bfc-146">관찰성는 다른 팀에서 만들고 다른 기술 스택을 사용 하 여 구축 된 경우에도 수준에서 구성 되 고 서비스 간에 일관 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-146">Observability is configured at the Dapr level and is consistent across services, even when created by different teams, and built with different technology stacks.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="b1bfc-147">작동 방식</span><span class="sxs-lookup"><span data-stu-id="b1bfc-147">How it works</span></span>

<span data-ttu-id="b1bfc-148">[사이드카 아키텍처](dapr-at-20000-feet.md#sidecar-architecture) 는 기본 제공 관찰성 기능을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-148">Dapr's [sidecar architecture](dapr-at-20000-feet.md#sidecar-architecture) enables built-in observability features.</span></span> <span data-ttu-id="b1bfc-149">서비스가 통신할 때, 사이드카는 트래픽을 가로채서 추적, 메트릭 및 로깅 정보를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-149">As services communicate, Dapr sidecars intercept the traffic and extract tracing, metrics, and logging information.</span></span> <span data-ttu-id="b1bfc-150">원격 분석은 개방형 표준 형식으로 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-150">Telemetry is published in an open standards format.</span></span> <span data-ttu-id="b1bfc-151">기본적으로 [OpenTelemetry](https://opentelemetry.io/) 및 [Zipkin](https://zipkin.io/)를 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-151">By default, Dapr supports [OpenTelemetry](https://opentelemetry.io/) and [Zipkin](https://zipkin.io/).</span></span>

<span data-ttu-id="b1bfc-152">D 4는 다른 백 엔드 모니터링 도구에 원격 분석을 게시할 수 있는 [수집기](https://docs.dapr.io/operations/monitoring/tracing/open-telemetry-collector/) 를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-152">Dapr provides [collectors](https://docs.dapr.io/operations/monitoring/tracing/open-telemetry-collector/) that can publish telemetry to different back-end monitoring tools.</span></span> <span data-ttu-id="b1bfc-153">이러한 도구는 분석 및 쿼리를 위한 4Apr 원격 분석을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-153">These tools present Dapr telemetry for analysis and querying.</span></span> <span data-ttu-id="b1bfc-154">그림 9-1은 Eapr 관찰성 아키텍처를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-154">Figure 9-1 shows the Dapr observability architecture:</span></span>

![Eapr 관찰성 아키텍처](media/observability/observability-architecture.png)

<span data-ttu-id="b1bfc-156">**그림 9-1**.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-156">**Figure 9-1**.</span></span> <span data-ttu-id="b1bfc-157">관찰성 아키텍처.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-157">Dapr observability architecture.</span></span>

1. <span data-ttu-id="b1bfc-158">서비스 A는 서비스 B에 대 한 작업을 호출 합니다. 호출은 서비스 A에 대 한 사이드카에서 서비스 B에 대 한 사이드카로 라우팅됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-158">Service A calls an operation on Service B. The call is routed from a Dapr sidecar for Service A to a sidecar for Service B.</span></span>
1. <span data-ttu-id="b1bfc-159">서비스 B가 작업을 완료 하면 사이드카를 통해 서비스 A에 응답을 다시 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-159">When Service B completes the operation, a response is sent back to Service A through the Dapr sidecars.</span></span> <span data-ttu-id="b1bfc-160">모든 요청 및 응답에 대해 사용 가능한 모든 원격 분석을 수집 하 고 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-160">They gather and publish all available telemetry for every request and response.</span></span>
1. <span data-ttu-id="b1bfc-161">구성 된 수집기는 원격 분석을 수집 모니터링 백 엔드에 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-161">The configured collector ingests the telemetry and sends it to the monitoring back end.</span></span>  

<span data-ttu-id="b1bfc-162">개발자는 관찰성를 추가 하는 것이 pub/sub 또는 state management와 같은 다른 이상의 구성 요소 구성과 다르다는 점에 유의 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-162">As a developer, keep in mind that adding observability is different from configuring other Dapr building blocks, like pub/sub or state management.</span></span> <span data-ttu-id="b1bfc-163">빌딩 블록을 참조 하는 대신 수집기 및 모니터링 백 엔드를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-163">Instead of referencing a building block, you add a collector and a monitoring back end.</span></span> <span data-ttu-id="b1bfc-164">그림 9-1에서는 여러 다른 모니터링 백 엔드와 통합 되는 여러 수집기를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-164">Figure 9-1 shows it's possible to configure multiple collectors that integrate with different monitoring back ends.</span></span>

<span data-ttu-id="b1bfc-165">이 챕터의 시작 부분에서 4 개의 원격 분석 범주가 식별 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-165">At the beginning of this chapter, four categories of telemetry were identified.</span></span> <span data-ttu-id="b1bfc-166">다음 섹션에서는 각 범주에 대 한 세부 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-166">The following sections will provide detail for each category.</span></span> <span data-ttu-id="b1bfc-167">여기에는 인기 있는 모니터링 백 엔드와 통합 되는 수집기를 구성 하는 방법에 대 한 지침이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-167">They'll include instruction on how to configure collectors that integrate with popular monitoring back ends.</span></span>

### <a name="distributed-tracing"></a><span data-ttu-id="b1bfc-168">분산 추적</span><span class="sxs-lookup"><span data-stu-id="b1bfc-168">Distributed tracing</span></span>

<span data-ttu-id="b1bfc-169">분산 추적은 분산 응용 프로그램의 서비스 간에 흐르는 트래픽에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-169">Distributed tracing provides insight into the traffic that flows across services in a distributed application.</span></span> <span data-ttu-id="b1bfc-170">교환 된 요청 및 응답 메시지의 로그는 문제 해결을 위한 중요 한 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-170">The log of exchanged request and response messages is an invaluable source of information for troubleshooting issues.</span></span> <span data-ttu-id="b1bfc-171">하드 파트는 동일한 작업에서 발생 하는 *메시지의 상관* 관계를 말합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-171">The hard part is *correlating messages* that originate from the same operation.</span></span>

<span data-ttu-id="b1bfc-172">D 4에서 [W3C 추적 컨텍스트](https://www.w3.org/TR/trace-context) 를 사용 하 여 관련 메시지를 상호 연결 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-172">Dapr uses the [W3C Trace Context](https://www.w3.org/TR/trace-context) to correlate related messages.</span></span> <span data-ttu-id="b1bfc-173">또한 고유한 작업을 구성 하는 요청 및 응답에 동일한 컨텍스트 정보를 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-173">It injects the same context information into requests and responses that form a unique operation.</span></span> <span data-ttu-id="b1bfc-174">그림 9-2에서는 상관 관계의 작동 방식을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-174">Figure 9-2 shows how correlation works:</span></span>

![W3C 추적 컨텍스트 예제](media/observability/w3c-trace-context.png)

<span data-ttu-id="b1bfc-176">**그림9-2**</span><span class="sxs-lookup"><span data-stu-id="b1bfc-176">**Figure 9-2**.</span></span> <span data-ttu-id="b1bfc-177">W3C 추적 컨텍스트 예제입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-177">W3C Trace Context example.</span></span>

1. <span data-ttu-id="b1bfc-178">서비스 A는 서비스 B에 대 한 작업을 호출 합니다. 서비스 A가 호출을 시작 하면, Capr에서 고유한 추적 컨텍스트를 만들어 요청에 삽입 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-178">Service A invokes an operation on Service B. As Service A starts the call, Dapr creates a unique trace context and injects it into the request.</span></span>
1. <span data-ttu-id="b1bfc-179">서비스 B에서 요청을 수신 하 고 서비스 C에 대 한 작업을 호출 합니다. d C 4는 들어오는 요청이 추적 컨텍스트를 포함 하 고 있는 것을 검색 하 고이를 서비스 C로 보내는 요청에 삽입 하 여 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-179">Service B receives the request and invokes an operation on Service C. Dapr detects that the incoming request contains a trace context and propagates it by injecting it into the outgoing request to Service C.</span></span>  
1. <span data-ttu-id="b1bfc-180">서비스 C에서 요청을 수신 하 고 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-180">Service C receives the request and handles it.</span></span> <span data-ttu-id="b1bfc-181">T 4는 들어오는 요청이 추적 컨텍스트를 포함 하는 것을 감지 하 고 서비스 B에 대 한 나가는 응답에 다시 삽입 하 여 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-181">Dapr detects that the incoming request contains a trace context and propagates it by injecting it into the outgoing response back to Service B.</span></span>
1. <span data-ttu-id="b1bfc-182">서비스 B는 응답을 수신 하 고 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-182">Service B receives the response and handles it.</span></span> <span data-ttu-id="b1bfc-183">그런 다음 새 응답을 만들고 서비스 A에 대 한 나가는 응답에 다시 삽입 하 여 추적 컨텍스트를 전파 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-183">It then creates a new response and propagates the trace context by injecting it into the outgoing response back to Service A.</span></span>

<span data-ttu-id="b1bfc-184">함께 포함 되는 요청 및 응답 집합을 *추적* 이라고 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-184">A set of requests and responses that belong together is called a *trace*.</span></span> <span data-ttu-id="b1bfc-185">그림 9-3에서는 추적을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-185">Figure 9-3 shows a trace:</span></span>

![추적 및 범위](media/observability/traces-spans.png)

<span data-ttu-id="b1bfc-187">**그림 9-3**</span><span class="sxs-lookup"><span data-stu-id="b1bfc-187">**Figure 9-3**.</span></span> <span data-ttu-id="b1bfc-188">추적 및 범위.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-188">Traces and spans.</span></span>

<span data-ttu-id="b1bfc-189">그림에서 추적은 여러 서비스에서 발생 하는 고유한 응용 프로그램 트랜잭션을 나타내는 방법을 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-189">In the figure, note how the trace represents a unique application transaction that takes place across many services.</span></span> <span data-ttu-id="b1bfc-190">추적은 *범위의* 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-190">A trace is a collection of *spans*.</span></span> <span data-ttu-id="b1bfc-191">각 범위는 단일 작업이 나 추적 내에서 수행 되는 작업 단위를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-191">Each span represents a single operation or unit of work done within the trace.</span></span> <span data-ttu-id="b1bfc-192">범위는 고유한 트랜잭션을 구현 하는 서비스 간에 전송 되는 요청 및 응답입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-192">Spans are the requests and responses that are sent between services that implement the unique transaction.</span></span>

<span data-ttu-id="b1bfc-193">다음 섹션에서는 모니터링 백 엔드에 게시 하 여 추적 원격 분석을 검사 하는 방법을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-193">The next sections discuss how to inspect tracing telemetry by publishing it to a monitoring back end.</span></span>

#### <a name="use-a-zipkin-monitoring-back-end"></a><span data-ttu-id="b1bfc-194">Zipkin 모니터링 백 엔드 사용</span><span class="sxs-lookup"><span data-stu-id="b1bfc-194">Use a Zipkin monitoring back end</span></span>

<span data-ttu-id="b1bfc-195">[Zipkin](https://zipkin.io/) 은 오픈 소스 분산 추적 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-195">[Zipkin](https://zipkin.io/) is an open-source distributed tracing system.</span></span> <span data-ttu-id="b1bfc-196">원격 분석 데이터를 수집 하 고 시각화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-196">It can ingest and visualize telemetry data.</span></span> <span data-ttu-id="b1bfc-197">Zipkin에 대 한 기본 지원을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-197">Dapr offers default support for Zipkin.</span></span> <span data-ttu-id="b1bfc-198">다음 예에서는 Zipkin를 구성 하 여 4Apr 원격 분석을 시각화 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-198">The following example demonstrates how to configure Zipkin to visualize Dapr telemetry.</span></span>

##### <a name="enable-and-configure-tracing"></a><span data-ttu-id="b1bfc-199">추적 사용 및 구성</span><span class="sxs-lookup"><span data-stu-id="b1bfc-199">Enable and configure tracing</span></span>

<span data-ttu-id="b1bfc-200">시작 하려면 4apr 런타임에 구성 파일을 사용 하 여 추적을 사용 하도록 설정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-200">To start, tracing must be enabled for the Dapr runtime using a Dapr configuration file.</span></span> <span data-ttu-id="b1bfc-201">다음은 이라는 구성 파일의 예입니다 `tracing-config.yaml` .</span><span class="sxs-lookup"><span data-stu-id="b1bfc-201">Here's an example of a configuration file named `tracing-config.yaml`:</span></span>  

```yaml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: tracing-config
  namespace: default
spec:
  tracing:
    samplingRate: "1"
    zipkin:
      endpointAddress: "http://zipkin.default.svc.cluster.local:9411/api/v2/spans"
```

<span data-ttu-id="b1bfc-202">`samplingRate`특성은 추적을 게시 하는 데 사용 되는 간격을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-202">The `samplingRate` attribute specifies the interval used for publishing traces.</span></span> <span data-ttu-id="b1bfc-203">값은 `0` (추적 사용 안 함) 사이 여야 하며 `1` (모든 추적이 게시 됨)</span><span class="sxs-lookup"><span data-stu-id="b1bfc-203">The value must be between `0` (tracing disabled) and `1` (every trace is published).</span></span> <span data-ttu-id="b1bfc-204">예를 들어 값이 이면 `0.5` 다른 모든 추적이 게시 되 고 게시 된 트래픽이 크게 줄어듭니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-204">With a value of `0.5`, for example, every other trace is published, significantly reducing published traffic.</span></span> <span data-ttu-id="b1bfc-205">는 `endpointAddress` Kubernetes 클러스터에서 실행 되는 Zipkin 서버의 끝점을 가리킵니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-205">The `endpointAddress` points to an endpoint on a Zipkin server running in a Kubernetes cluster.</span></span> <span data-ttu-id="b1bfc-206">Zipkin에 대 한 기본 포트는 `9411` 입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-206">The default port for Zipkin is `9411`.</span></span> <span data-ttu-id="b1bfc-207">Kubernetes CLI를 사용 하 여 Kubernetes 클러스터에 구성을 적용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-207">The configuration must be applied to the Kubernetes cluster using the Kubernetes CLI:</span></span>

```console
kubectl apply -f tracing-config.yaml
```

##### <a name="install-the-zipkin-server"></a><span data-ttu-id="b1bfc-208">Zipkin 서버 설치</span><span class="sxs-lookup"><span data-stu-id="b1bfc-208">Install the Zipkin server</span></span>

<span data-ttu-id="b1bfc-209">자체 호스팅 모드에서 Zipkin 서버를 설치 하는 경우에는 Windows의 또는에 있는 기본 구성 파일에서 자동으로 설치 되 고 추적 기능이 사용 하도록 설정 됩니다 `$HOME/.dapr/config.yaml` `%USERPROFILE%\.dapr\config.yaml` .</span><span class="sxs-lookup"><span data-stu-id="b1bfc-209">When installing Dapr in self-hosted mode, a Zipkin server is automatically installed and tracing is enabled in the default configuration file located in `$HOME/.dapr/config.yaml` or `%USERPROFILE%\.dapr\config.yaml` on Windows.</span></span>

<span data-ttu-id="b1bfc-210">Kubernetes 클러스터에는 Zipkin를 설치 하지만 기본적으로는 추가 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-210">When installing Dapr on a Kubernetes cluster though, Zipkin isn't added by default.</span></span> <span data-ttu-id="b1bfc-211">이라는 다음 Kubernetes 매니페스트 파일은 `zipkin.yaml` 표준 Zipkin 서버를 클러스터에 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-211">The following Kubernetes manifest file named `zipkin.yaml`, deploys a standard Zipkin server to the cluster:</span></span>

```yaml
kind: Deployment
apiVersion: apps/v1
metadata:
  name: zipkin
  namespace: eshop
  labels:
    service: zipkin
spec:
  replicas: 1
  selector:
    matchLabels:
      service: zipkin
  template:
    metadata:
      labels:
        service: zipkin
    spec:
      containers:
        - name: zipkin
          image: openzipkin/zipkin-slim
          imagePullPolicy: IfNotPresent
          ports:
            - name: http
              containerPort: 9411
              protocol: TCP

---

kind: Service
apiVersion: v1
metadata:
  name: zipkin
  namespace: eshop
  labels:
    service: zipkin
spec:
  type: NodePort
  ports:
    - port: 9411
      targetPort: 9411
      nodePort: 32411
      protocol: TCP
      name: zipkin
  selector:
    service: zipkin

```

<span data-ttu-id="b1bfc-212">배포에서는 표준 컨테이너 이미지를 사용 합니다 `openzipkin/zipkin-slim` .</span><span class="sxs-lookup"><span data-stu-id="b1bfc-212">The deployment uses the standard `openzipkin/zipkin-slim` container image.</span></span> <span data-ttu-id="b1bfc-213">Zipkin 서비스는 포트에서 원격 분석을 보는 데 사용할 수 있는 Zipkin 웹 프런트 엔드를 노출 합니다 `32411` .</span><span class="sxs-lookup"><span data-stu-id="b1bfc-213">The Zipkin service exposes the Zipkin web front end, which you can use to view the telemetry on port `32411`.</span></span> <span data-ttu-id="b1bfc-214">Kubernetes CLI를 사용 하 여 Zipkin 매니페스트 파일을 Kubernetes 클러스터에 적용 하 고 Zipkin 서버를 배포 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-214">Use the Kubernetes CLI to apply the Zipkin manifest file to the Kubernetes cluster and deploy the Zipkin server:</span></span>

```console
kubectl apply -f zipkin.yaml
```

##### <a name="configure-the-services-to-use-the-tracing-configuration"></a><span data-ttu-id="b1bfc-215">추적 구성을 사용 하도록 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="b1bfc-215">Configure the services to use the tracing configuration</span></span>

<span data-ttu-id="b1bfc-216">이제 모든 것이 올바르게 설정 되어 원격 분석 게시를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-216">Now everything is set up correctly to start publishing telemetry.</span></span> <span data-ttu-id="b1bfc-217">응용 프로그램의 일부로 배포 된 모든 6Apr 사이드카를 시작할 때 원격 분석을 내보내도록 지시 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-217">Every Dapr sidecar that is deployed as part of the application must be instructed to emit telemetry when started.</span></span> <span data-ttu-id="b1bfc-218">이렇게 하려면 `dapr.io/config` 구성을 참조 하는 주석을 `tracing-config` 각 서비스의 배포에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-218">To do that, add a `dapr.io/config` annotation that references the `tracing-config` configuration to the deployment of each service.</span></span> <span data-ttu-id="b1bfc-219">다음은 주석이 포함 된 eShop 주문 API 서비스의 매니페스트 파일의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-219">Here's an example of the eShop ordering API service's manifest file containing the annotation:</span></span>

```yaml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: ordering-api
  namespace: eshop
  labels:
    app: eshop
spec:
  replicas: 1
  selector:
    matchLabels:
      app: eshop
  template:
    metadata:
      labels:
        app: simulation
      annotations:
        dapr.io/enabled: "true"
        dapr.io/app-id: "ordering-api"
        dapr.io/config: "tracing-config"
    spec:
      containers:
      - name: simulation
        image: eshop/ordering.api:linux-latest
```

##### <a name="inspect-the-telemetry-in-zipkin"></a><span data-ttu-id="b1bfc-220">Zipkin에서 원격 분석 검사</span><span class="sxs-lookup"><span data-stu-id="b1bfc-220">Inspect the telemetry in Zipkin</span></span>

<span data-ttu-id="b1bfc-221">응용 프로그램이 시작 되 면 사이드카는 Zipkin 서버에 원격 분석을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-221">Once the application is started, the Dapr sidecars will emit telemetry to the Zipkin server.</span></span> <span data-ttu-id="b1bfc-222">이 원격 분석을 검사 하려면 웹 브라우저를로 가리킵니다 <http://localhost:32411> .</span><span class="sxs-lookup"><span data-stu-id="b1bfc-222">To inspect this telemetry, point a web-browser to <http://localhost:32411>.</span></span> <span data-ttu-id="b1bfc-223">Zipkin 웹 프런트 엔드가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-223">You'll see the Zipkin web front end:</span></span>

![Zipkin 시작 페이지](media/observability/zipkin.png)

<span data-ttu-id="b1bfc-225">*추적 찾기* 탭에서 추적을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-225">On the *Find a trace* tab, you can query traces.</span></span> <span data-ttu-id="b1bfc-226">제한을 지정 하지 않고 *쿼리 실행* 단추를 누르면 수집 *추적이* 모두 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-226">Pressing the *RUN QUERY* button without specifying any restrictions will show all the ingested *traces*:</span></span>

![추적 목록](media/observability/zipkin-traces-overview.png)

<span data-ttu-id="b1bfc-228">특정 추적 옆의 *표시* 단추를 클릭 하면 해당 추적에 대 한 세부 정보가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-228">Clicking the *SHOW* button next to a specific trace, will show the details of that trace:</span></span>

![추적 세부 정보](media/observability/zipkin-trace-details.png)

<span data-ttu-id="b1bfc-230">세부 정보 페이지의 각 항목은 선택한 추적의 일부인 요청을 나타내는 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-230">Each item on the details page, is a span that represents a request that is part of the selected trace.</span></span>

##### <a name="inspect-the-dependencies-between-services"></a><span data-ttu-id="b1bfc-231">서비스 간 종속성 검사</span><span class="sxs-lookup"><span data-stu-id="b1bfc-231">Inspect the dependencies between services</span></span>

<span data-ttu-id="b1bfc-232">사이드카는 서비스 간의 트래픽을 처리 하므로 Zipkin는 추적 정보를 사용 하 여 서비스 간의 종속성을 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-232">Because Dapr sidecars handle traffic between services, Zipkin can use the trace information to determine the dependencies between the services.</span></span> <span data-ttu-id="b1bfc-233">작동 하는지 확인 하려면 Zipkin 웹 페이지의 *종속성* 탭으로 이동 하 고 돋보기 모양의 단추를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-233">To see it in action, go to the *Dependencies* tab on the Zipkin web page and select the button with the magnifying glass.</span></span> <span data-ttu-id="b1bfc-234">Zipkin는 서비스 및 해당 종속성에 대 한 개요를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-234">Zipkin will show an overview of the services and their dependencies:</span></span>

![Zipkin의 종속성 그래프](media/observability/zipkin-dependencies.png)

<span data-ttu-id="b1bfc-236">서비스 간의 줄에서 적용 되는 점은 요청을 나타내고 원본에서 대상으로 이동 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-236">The animated dots on the lines between the services represent requests and move from source to destination.</span></span> <span data-ttu-id="b1bfc-237">빨간색 점은 실패 한 요청을 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-237">Red dots indicate a failed request.</span></span>

#### <a name="use-a-jaeger-or-new-relic-monitoring-back-end"></a><span data-ttu-id="b1bfc-238">Jaeger 또는 새 유물 모니터링 백 엔드 사용</span><span class="sxs-lookup"><span data-stu-id="b1bfc-238">Use a Jaeger or New Relic monitoring back end</span></span>

<span data-ttu-id="b1bfc-239">Zipkin 외에도 다른 모니터링 백 엔드 소프트웨어는 Zipkin 형식을 사용 하 여 수집 원격 분석을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-239">Beyond Zipkin itself, other monitoring back-end software also supports ingesting telemetry using the Zipkin format.</span></span> <span data-ttu-id="b1bfc-240">[Jaeger](https://www.jaegertracing.io/) 는 Uber 기술로 만든 오픈 소스 추적 시스템입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-240">[Jaeger](https://www.jaegertracing.io/) is an open source tracing system created by Uber Technologies.</span></span> <span data-ttu-id="b1bfc-241">분산 서비스 간의 트랜잭션을 추적 하 고 복잡 한 마이크로 서비스 환경의 문제를 해결 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-241">It's used to trace transactions between distributed services and troubleshoot complex microservices environments.</span></span> <span data-ttu-id="b1bfc-242">[새 유물](https://newrelic.com/) 은 *전체 스택* 관찰성 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-242">[New Relic](https://newrelic.com/) is a *full-stack* observability platform.</span></span> <span data-ttu-id="b1bfc-243">분산 응용 프로그램의 관련 데이터를 연결 하 여 시스템에 대 한 전체 그림을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-243">It links relevant data from a distributed application to provide a complete picture of your system.</span></span> <span data-ttu-id="b1bfc-244">이를 수행 하려면 `endpointAddress` Jaeger 또는 새 유물 서버를 가리키는를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-244">To try them out, specify an `endpointAddress` pointing to either a Jaeger or New Relic server in the Dapr configuration file.</span></span> <span data-ttu-id="b1bfc-245">Jaeger 서버에 원격 분석을 보내도록 Aapr를 구성 하는 구성 파일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-245">Here's an example of a configuration file that configures Dapr to send telemetry to a Jaeger server.</span></span> <span data-ttu-id="b1bfc-246">Jaeger의 URL은 Zipkin에 대 한 URL과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-246">The URL for Jaeger is identical to the URL for the Zipkin.</span></span> <span data-ttu-id="b1bfc-247">유일한 차이점은 서버를 실행 하는 포트입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-247">The only difference is the port on which the server runs:</span></span>

 ```yaml
 apiVersion: dapr.io/v1alpha1
 kind: Configuration
 metadata:
   name: tracing-config
   namespace: default
 spec:
   tracing:
     samplingRate: "1"
     zipkin:
       endpointAddress: "http://localhost:9415/api/v2/spans"
 ```

<span data-ttu-id="b1bfc-248">새 유물을 사용해 보려면 새 유물 API의 끝점을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-248">To try out New Relic, specify the endpoint of the New Relic API.</span></span> <span data-ttu-id="b1bfc-249">새 유물에 대 한 구성 파일의 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-249">Here's an example of a configuration file for New Relic:</span></span>

 ```yaml
apiVersion: dapr.io/v1alpha1
 kind: Configuration
 metadata:
   name: tracing-config
   namespace: default
 spec:
   tracing:
     samplingRate: "1"
     zipkin:
       endpointAddress: "https://trace-api.newrelic.com/trace/v1?Api-Key=<NR-API-KEY>&Data-Format=zipkin&Data-Format-Version=2"
 ```

<span data-ttu-id="b1bfc-250">사용 방법에 대 한 자세한 내용은 Jaeger 및 새 유물 웹 사이트를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-250">Check out the Jaeger and New Relic websites for more information on how to use them.</span></span>

### <a name="metrics"></a><span data-ttu-id="b1bfc-251">메트릭</span><span class="sxs-lookup"><span data-stu-id="b1bfc-251">Metrics</span></span>

<span data-ttu-id="b1bfc-252">메트릭은 성능 및 리소스 소비에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-252">Metrics provide insight into performance and resource consumption.</span></span> <span data-ttu-id="b1bfc-253">내부적으로, A4는 광범위 한 시스템 및 런타임 메트릭의 컬렉션을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-253">Under the hood, Dapr emits a wide collection of system and runtime metrics.</span></span> <span data-ttu-id="b1bfc-254">6apr는 [프로메테우스](https://prometheus.io/) 를 메트릭 표준으로 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-254">Dapr uses [Prometheus](https://prometheus.io/) as a metric standard.</span></span> <span data-ttu-id="b1bfc-255">사이드카 및 시스템 서비스는 포트에서 메트릭 끝점을 노출 `9090` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-255">Dapr sidecars and system services, expose a metrics endpoint on port `9090`.</span></span> <span data-ttu-id="b1bfc-256">*프로메테우스 scraper* 는 미리 정의 된 간격으로이 끝점을 호출 하 여 메트릭을 수집 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-256">A *Prometheus scraper* calls this endpoint at a predefined interval to collect metrics.</span></span> <span data-ttu-id="b1bfc-257">Scraper는 모니터링 백 엔드에 메트릭 값을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-257">The scraper sends metric values to a monitoring back end.</span></span> <span data-ttu-id="b1bfc-258">그림 9-4에서는 스크랩 프로세스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-258">Figure 9-4 shows the scraping process:</span></span>

![스크랩 프로메테우스 메트릭](media/observability/prometheus-scraper.png)

<span data-ttu-id="b1bfc-260">**그림 9-4**.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-260">**Figure 9-4**.</span></span> <span data-ttu-id="b1bfc-261">스크랩 프로메테우스 메트릭입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-261">Scraping Prometheus metrics.</span></span>

<span data-ttu-id="b1bfc-262">위의 그림에서 각 사이드카 및 시스템 서비스는 포트 9090에서 수신 대기 하는 메트릭 끝점을 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-262">In the above figure, each sidecar and system service exposes a metric endpoint that listens on port 9090.</span></span> <span data-ttu-id="b1bfc-263">Scrapper는 각 끝점에서 메트릭을 캡처하고 모니터링 백 엔드에 정보를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-263">The Prometheus Metrics Scrapper captures metrics from each endpoint and published the information to the monitoring back end.</span></span>  

#### <a name="service-discovery"></a><span data-ttu-id="b1bfc-264">서비스 검색</span><span class="sxs-lookup"><span data-stu-id="b1bfc-264">Service discovery</span></span>

<span data-ttu-id="b1bfc-265">메트릭 scraper에서 메트릭을 수집할 위치를 어떻게 알 수 있는지 궁금할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-265">You might wonder how the metrics scraper knows where to collect metrics.</span></span> <span data-ttu-id="b1bfc-266">프로메테우스는 대상 배포 환경에 기본 제공 되는 검색 메커니즘과 통합할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-266">Prometheus can integrate with discovery mechanisms built into target deployment environments.</span></span> <span data-ttu-id="b1bfc-267">예를 들어 Kubernetes에서 실행 하는 경우 Kubernetes API와 통합 하 여 환경에서 실행 중인 사용 가능한 모든 Kubernetes 리소스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-267">For example, when running in Kubernetes, Prometheus can integrate with the Kubernetes API to find all available Kubernetes resources running in the environment.</span></span>

#### <a name="metrics-list"></a><span data-ttu-id="b1bfc-268">메트릭 목록</span><span class="sxs-lookup"><span data-stu-id="b1bfc-268">Metrics list</span></span>

<span data-ttu-id="b1bfc-269">6apr는 cccsystem 서비스 및 해당 런타임에 대 한 많은 메트릭을 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-269">Dapr generates a large set of metrics for Dapr system services and its runtime.</span></span> <span data-ttu-id="b1bfc-270">일부 사례:</span><span class="sxs-lookup"><span data-stu-id="b1bfc-270">Some examples include:</span></span>

| <span data-ttu-id="b1bfc-271">메트릭</span><span class="sxs-lookup"><span data-stu-id="b1bfc-271">Metric</span></span>                                         | <span data-ttu-id="b1bfc-272">원본</span><span class="sxs-lookup"><span data-stu-id="b1bfc-272">Source</span></span> | <span data-ttu-id="b1bfc-273">Description</span><span class="sxs-lookup"><span data-stu-id="b1bfc-273">Description</span></span>                                                  |
| ---------------------------------------------- | :----: | ------------------------------------------------------------ |
| <span data-ttu-id="b1bfc-274">dapr_operator_service_created_total</span><span class="sxs-lookup"><span data-stu-id="b1bfc-274">dapr_operator_service_created_total</span></span>            | <span data-ttu-id="b1bfc-275">시스템</span><span class="sxs-lookup"><span data-stu-id="b1bfc-275">System</span></span> | <span data-ttu-id="b1bfc-276">Eapr 운영자 서비스에서 만든 총 Capr 서비스 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-276">The total number of Dapr services created by the Dapr Operator service.</span></span> |
| <span data-ttu-id="b1bfc-277">dapr_injector_sidecar_injection/requests_total</span><span class="sxs-lookup"><span data-stu-id="b1bfc-277">dapr_injector_sidecar_injection/requests_total</span></span> | <span data-ttu-id="b1bfc-278">시스템</span><span class="sxs-lookup"><span data-stu-id="b1bfc-278">System</span></span> | <span data-ttu-id="b1bfc-279">Sidecar-Injector service에서 받은 총 사이드카 주입 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-279">The total number of sidecar injection requests received by the Dapr Sidecar-Injector service.</span></span> |
| <span data-ttu-id="b1bfc-280">dapr_placement_runtimes_total</span><span class="sxs-lookup"><span data-stu-id="b1bfc-280">dapr_placement_runtimes_total</span></span>                  | <span data-ttu-id="b1bfc-281">시스템</span><span class="sxs-lookup"><span data-stu-id="b1bfc-281">System</span></span> | <span data-ttu-id="b1bfc-282">6Apr 배치 서비스에 보고 된 총 호스트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-282">The total number of hosts reported to the Dapr Placement service.</span></span> |
| <span data-ttu-id="b1bfc-283">dapr_sentry_cert_sign_request_received_total</span><span class="sxs-lookup"><span data-stu-id="b1bfc-283">dapr_sentry_cert_sign_request_received_total</span></span>   | <span data-ttu-id="b1bfc-284">시스템</span><span class="sxs-lookup"><span data-stu-id="b1bfc-284">System</span></span> | <span data-ttu-id="b1bfc-285">Eapr Sentry 서비스에서 받은 CRSs (인증서 서명 요청) 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-285">The number of certificate signing requests (CRSs) received by the Dapr Sentry service.</span></span> |
| <span data-ttu-id="b1bfc-286">dapr_runtime_component_loaded</span><span class="sxs-lookup"><span data-stu-id="b1bfc-286">dapr_runtime_component_loaded</span></span>      | <span data-ttu-id="b1bfc-287">런타임</span><span class="sxs-lookup"><span data-stu-id="b1bfc-287">Runtime</span></span> | <span data-ttu-id="b1bfc-288">성공적으로 로드 된 Capr 구성 요소 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-288">The number of successfully loaded Dapr components.</span></span>           |
| <span data-ttu-id="b1bfc-289">dapr_grpc_io_server_completed_rpcs</span><span class="sxs-lookup"><span data-stu-id="b1bfc-289">dapr_grpc_io_server_completed_rpcs</span></span> | <span data-ttu-id="b1bfc-290">런타임</span><span class="sxs-lookup"><span data-stu-id="b1bfc-290">Runtime</span></span> | <span data-ttu-id="b1bfc-291">메서드 및 상태별 gRPC 호출 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-291">Count of gRPC calls by method and status.</span></span>                    |
| <span data-ttu-id="b1bfc-292">dapr_http_server_request_count</span><span class="sxs-lookup"><span data-stu-id="b1bfc-292">dapr_http_server_request_count</span></span>     | <span data-ttu-id="b1bfc-293">런타임</span><span class="sxs-lookup"><span data-stu-id="b1bfc-293">Runtime</span></span> | <span data-ttu-id="b1bfc-294">HTTP 서버에서 시작 된 HTTP 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-294">Number of HTTP requests started in an HTTP server.</span></span>           |
| <span data-ttu-id="b1bfc-295">dapr_http/client/sent_bytes</span><span class="sxs-lookup"><span data-stu-id="b1bfc-295">dapr_http/client/sent_bytes</span></span>        | <span data-ttu-id="b1bfc-296">런타임</span><span class="sxs-lookup"><span data-stu-id="b1bfc-296">Runtime</span></span> | <span data-ttu-id="b1bfc-297">HTTP 클라이언트에서 요청 본문 (헤더 포함 안 함)으로 보낸 총 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-297">Total bytes sent in request body (not including headers) by an HTTP client.</span></span> |

<span data-ttu-id="b1bfc-298">사용 가능한 메트릭에 대 한 자세한 내용은 참조는 [64 메트릭 설명서](https://docs.dapr.io/operations/monitoring/metrics/)입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-298">For more information on available metrics, see the [Dapr metrics documentation](https://docs.dapr.io/operations/monitoring/metrics/).</span></span>

#### <a name="configure-dapr-metrics"></a><span data-ttu-id="b1bfc-299">= 4 월 메트릭 구성</span><span class="sxs-lookup"><span data-stu-id="b1bfc-299">Configure Dapr metrics</span></span>

<span data-ttu-id="b1bfc-300">런타임에는 `--enable-metrics=false` Eapr 명령에 인수를 포함 하 여 메트릭 컬렉션 끝점을 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-300">At runtime, you can disable the metrics collection endpoint by including the `--enable-metrics=false` argument in the Dapr command.</span></span> <span data-ttu-id="b1bfc-301">또는 인수를 사용 하 여 끝점에 대 한 기본 포트를 변경할 수도 있습니다 `--metrics-port 9090` .</span><span class="sxs-lookup"><span data-stu-id="b1bfc-301">Or, you can also change the default port for the endpoint with the `--metrics-port 9090` argument.</span></span>

<span data-ttu-id="b1bfc-302">또한, Cc4 구성 파일을 사용 하 여 런타임 메트릭 수집을 정적으로 사용 하거나 사용 하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-302">You can also use a Dapr configuration file to statically enable or disable runtime metrics collection:</span></span>

```yaml
apiVersion: dapr.io/v1alpha1
kind: Configuration
metadata:
  name: dapr-config
  namespace: eshop
spec:
  tracing:
    samplingRate: "1"
  metric:
    enabled: false
```

#### <a name="visualize-dapr-metrics"></a><span data-ttu-id="b1bfc-303">Aapr 메트릭 시각화</span><span class="sxs-lookup"><span data-stu-id="b1bfc-303">Visualize Dapr metrics</span></span>

<span data-ttu-id="b1bfc-304">프로메테우스 scraper 모니터링 백 엔드에 메트릭을 수집 하 고 게시 하는 경우 원시 데이터를 어떻게 이해할 수 있나요?</span><span class="sxs-lookup"><span data-stu-id="b1bfc-304">With the Prometheus scraper collecting and publishing metrics into the monitoring back end, how do you make sense of the raw data?</span></span> <span data-ttu-id="b1bfc-305">메트릭을 분석 하기 위한 인기 있는 시각화 도구는 [Grafana](https://grafana.com/grafana/)입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-305">A popular visualization tool for analyzing metrics is [Grafana](https://grafana.com/grafana/).</span></span> <span data-ttu-id="b1bfc-306">Grafana를 사용 하 여 사용 가능한 메트릭에 대 한 대시보드를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-306">With Grafana, you can create dashboards from the available metrics.</span></span> <span data-ttu-id="b1bfc-307">다음은 4 가지 시스템 서비스 메트릭을 표시 하는 대시보드의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-307">Here's an example of a dashboard displaying Dapr system services metrics:</span></span>

![Grafana 시스템 서비스 메트릭을 표시 하는 대시보드](media/observability/grafana-sample.png)

<span data-ttu-id="b1bfc-309">이 문서에는 [프로메테우스 및 Grafana을 설치 하는 방법에 대 한 자습서](https://docs.dapr.io/operations/monitoring/metrics/grafana/)가 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-309">The Dapr documentation includes a [tutorial for installing Prometheus and Grafana](https://docs.dapr.io/operations/monitoring/metrics/grafana/).</span></span>

### <a name="logging"></a><span data-ttu-id="b1bfc-310">로깅</span><span class="sxs-lookup"><span data-stu-id="b1bfc-310">Logging</span></span>

<span data-ttu-id="b1bfc-311">로깅은 런타임에 서비스에서 발생 하는 상황에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-311">Logging provides insight into what is happening with a service at runtime.</span></span> <span data-ttu-id="b1bfc-312">응용 프로그램을 실행 하는 경우, 사이드카는 d 4에서 자동으로 로그 항목을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-312">When running an application, Dapr automatically emits log entries from Dapr sidecars and Dapr system services.</span></span> <span data-ttu-id="b1bfc-313">그러나 응용 프로그램 코드에 계측 된 로깅 항목이 자동으로 포함 **되지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="b1bfc-313">However, logging entries instrumented in your application code **aren't** automatically included.</span></span> <span data-ttu-id="b1bfc-314">응용 프로그램 코드에서 로깅을 내보내려면 [.net 용 OPENTELEMETRY sdk](https://opentelemetry.io/docs/net/)와 같은 특정 SDK를 가져올 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-314">To emit logging from application code, you can import a specific SDK like [OpenTelemetry SDK for .NET](https://opentelemetry.io/docs/net/).</span></span> <span data-ttu-id="b1bfc-315">응용 프로그램 코드를 로깅하는 방법에 대 한 내용은이 장의 뒷부분에 있는 *Dapr .NET SDK 사용* 섹션에서 다룹니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-315">Logging application code is covered later in this chapter in the section *Using the Dapr .NET SDK*.</span></span>  

#### <a name="log-entry-structure"></a><span data-ttu-id="b1bfc-316">로그 항목 구조</span><span class="sxs-lookup"><span data-stu-id="b1bfc-316">Log entry structure</span></span>

<span data-ttu-id="b1bfc-317">D 4에서 구조적 로깅을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-317">Dapr emits structured logging.</span></span> <span data-ttu-id="b1bfc-318">각 로그 항목의 형식은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-318">Each log entry has the following format:</span></span>

| <span data-ttu-id="b1bfc-319">필드</span><span class="sxs-lookup"><span data-stu-id="b1bfc-319">Field</span></span>    | <span data-ttu-id="b1bfc-320">Description</span><span class="sxs-lookup"><span data-stu-id="b1bfc-320">Description</span></span>                                          | <span data-ttu-id="b1bfc-321">예제</span><span class="sxs-lookup"><span data-stu-id="b1bfc-321">Example</span></span>                             |
| -------- | ---------------------------------------------------- | ----------------------------------- |
| <span data-ttu-id="b1bfc-322">time</span><span class="sxs-lookup"><span data-stu-id="b1bfc-322">time</span></span>     | <span data-ttu-id="b1bfc-323">ISO8601 형식이 지정 된 타임 스탬프</span><span class="sxs-lookup"><span data-stu-id="b1bfc-323">ISO8601 formatted timestamp</span></span>                          | `2021-01-10T14:19:31.000Z`          |
| <span data-ttu-id="b1bfc-324">수준</span><span class="sxs-lookup"><span data-stu-id="b1bfc-324">level</span></span>    | <span data-ttu-id="b1bfc-325">항목의 수준 ( `debug` \| `info` \| `warn` \| `error` )  </span><span class="sxs-lookup"><span data-stu-id="b1bfc-325">Level of the entry (`debug` \| `info` \| `warn`  \| `error`)</span></span> | `info`                              |
| <span data-ttu-id="b1bfc-326">형식</span><span class="sxs-lookup"><span data-stu-id="b1bfc-326">type</span></span>     | <span data-ttu-id="b1bfc-327">로그 형식</span><span class="sxs-lookup"><span data-stu-id="b1bfc-327">Log Type</span></span>                                             | `log`                               |
| <span data-ttu-id="b1bfc-328">msg</span><span class="sxs-lookup"><span data-stu-id="b1bfc-328">msg</span></span>      | <span data-ttu-id="b1bfc-329">로그 메시지</span><span class="sxs-lookup"><span data-stu-id="b1bfc-329">Log Message</span></span>                                          | `metrics server started on :62408/` |
| <span data-ttu-id="b1bfc-330">scope</span><span class="sxs-lookup"><span data-stu-id="b1bfc-330">scope</span></span>    | <span data-ttu-id="b1bfc-331">로깅 범위</span><span class="sxs-lookup"><span data-stu-id="b1bfc-331">Logging Scope</span></span>                                        | `dapr.runtime`                      |
| <span data-ttu-id="b1bfc-332">인스턴스</span><span class="sxs-lookup"><span data-stu-id="b1bfc-332">instance</span></span> | <span data-ttu-id="b1bfc-333">D 4가 실행 되는 호스트 이름</span><span class="sxs-lookup"><span data-stu-id="b1bfc-333">Hostname where Dapr runs</span></span>                             | <span data-ttu-id="b1bfc-334">TSTSRV01</span><span class="sxs-lookup"><span data-stu-id="b1bfc-334">TSTSRV01</span></span>                            |
| <span data-ttu-id="b1bfc-335">app_id</span><span class="sxs-lookup"><span data-stu-id="b1bfc-335">app_id</span></span>   | <span data-ttu-id="b1bfc-336">4apr 앱 ID</span><span class="sxs-lookup"><span data-stu-id="b1bfc-336">Dapr App ID</span></span>                                          | <span data-ttu-id="b1bfc-337">ordering-api</span><span class="sxs-lookup"><span data-stu-id="b1bfc-337">ordering-api</span></span>                        |
| <span data-ttu-id="b1bfc-338">ver</span><span class="sxs-lookup"><span data-stu-id="b1bfc-338">ver</span></span>      | <span data-ttu-id="b1bfc-339">4apr 런타임 버전</span><span class="sxs-lookup"><span data-stu-id="b1bfc-339">Dapr Runtime Version</span></span>                                 | <span data-ttu-id="b1bfc-340">`1.0.0`-rc. 2</span><span class="sxs-lookup"><span data-stu-id="b1bfc-340">`1.0.0`-rc.2</span></span>                        |

<span data-ttu-id="b1bfc-341">문제 해결 시나리오에서 로깅 항목을 검색 하는 경우 `time` 및 `level` 필드가 특히 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-341">When searching through logging entries in a troubleshooting scenario, the `time` and `level` fields are especially helpful.</span></span> <span data-ttu-id="b1bfc-342">시간 필드는 특정 기간을 정확 하 게 확인할 수 있도록 로그 항목을 정렬 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-342">The time field orders log entries so that you can pinpoint specific time periods.</span></span> <span data-ttu-id="b1bfc-343">문제를 해결할 때 *디버그 수준의* 로그 항목은 코드의 동작에 대 한 자세한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-343">When troubleshooting, log entries at the *debug level* provide more information on the behavior of the code.</span></span>

#### <a name="plain-text-versus-json-format"></a><span data-ttu-id="b1bfc-344">일반 텍스트와 JSON 형식 비교</span><span class="sxs-lookup"><span data-stu-id="b1bfc-344">Plain text versus JSON format</span></span>

<span data-ttu-id="b1bfc-345">기본적으로, d 4는 구조적 로깅을 일반 텍스트 형식으로 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-345">By default, Dapr emits structured logging in plain-text format.</span></span> <span data-ttu-id="b1bfc-346">모든 로그 항목의 형식은 키/값 쌍이 포함 된 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-346">Every log entry is formatted as a string containing key/value pairs.</span></span> <span data-ttu-id="b1bfc-347">일반 텍스트로 기록 하는 예는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-347">Here's an example of logging in plain text:</span></span>

```text
== DAPR == time="2021-01-12T16:11:39.4669323+01:00" level=info msg="starting Dapr Runtime -- version 1.0.0-rc.2 -- commit 196483d" app_id=ordering-api instance=TSTSRV03 scope=dapr.runtime type=log ver=1.0.0-rc.2
== DAPR == time="2021-01-12T16:11:39.467933+01:00" level=info msg="log level set to: info" app_id=ordering-api instance=TSTSRV03 scope=dapr.runtime type=log ver=1.0.0-rc.2
== DAPR == time="2021-01-12T16:11:39.467933+01:00" level=info msg="metrics server started on :62408/" app_id=ordering-api instance=TSTSRV03 scope=dapr.metrics type=log ver=1.0.0-rc.2
```

<span data-ttu-id="b1bfc-348">단순 하지만이 형식은 구문 분석 하기가 어렵습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-348">While simple, this format is difficult to parse.</span></span> <span data-ttu-id="b1bfc-349">모니터링 도구를 사용 하 여 로그 항목을 보는 경우 JSON 형식의 로깅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-349">If viewing log entries with a monitoring tool, you'll want to enable JSON formatted logging.</span></span> <span data-ttu-id="b1bfc-350">JSON 항목을 사용 하 여 모니터링 도구는 개별 필드를 인덱싱하고 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-350">With JSON entries, a monitoring tool can index and query individual fields.</span></span> <span data-ttu-id="b1bfc-351">JSON 형식의 동일한 로그 항목은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-351">Here's the same log entries in JSON format:</span></span>

```json
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "starting Dapr Runtime -- version 1.0.0-rc.2 -- commit 196483d", "scope": "dapr.runtime", "time": "2021-01-12T16:11:39.4669323+01:00", "type": "log", "ver": "1.0.0-rc.2"}
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "log level set to: info", "scope": "dapr.runtime", "type": "log", "time": "2021-01-12T16:11:39.467933+01:00", "ver": "1.0.0-rc.2"}
{"app_id": "ordering-api", "instance": "TSTSRV03", "level": "info", "msg": "metrics server started on :62408/", "scope": "dapr.metrics", "type": "log", "time": "2021-01-12T16:11:39.467933+01:00", "ver": "1.0.0-rc.2"}
```

<span data-ttu-id="b1bfc-352">JSON 서식 지정을 사용 하도록 설정 하려면 각 사이드카를 구성 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-352">To enable JSON formatting, you need to configure each Dapr sidecar.</span></span> <span data-ttu-id="b1bfc-353">자체 호스팅 모드에서는 명령줄에 플래그를 지정할 수 있습니다 `--log-as-json` .</span><span class="sxs-lookup"><span data-stu-id="b1bfc-353">In self-hosted mode, you can specify the flag `--log-as-json` on the command line:</span></span>

```console
dapr run --app-id ordering-api --log-level info --log-as-json dotnet run
```

<span data-ttu-id="b1bfc-354">Kubernetes에서는 `dapr.io/log-as-json` 응용 프로그램에 대 한 각 배포에 주석을 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-354">In Kubernetes, you can add a `dapr.io/log-as-json` annotation to each deployment for the application:</span></span>

```yaml
annotations:
   dapr.io/enabled: "true"
   dapr.io/app-id: "ordering-api"
   dapr.io/app-port: "80"
   dapr.io/config: "dapr-config"
   dapr.io/log-as-json: "true"
```

<span data-ttu-id="b1bfc-355">투구를 사용 하 여 Kubernetes 클러스터에 d 4를 설치 하는 경우 모든 Eapr 시스템 서비스에 대해 JSON 형식의 로깅을 사용 하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-355">When you install Dapr in a Kubernetes cluster using Helm, you can enable JSON formatted logging for all the Dapr system services:</span></span>

```console
helm repo add dapr https://dapr.github.io/helm-charts/
helm repo update
kubectl create namespace dapr-system
helm install dapr dapr/dapr --namespace dapr-system --set global.logAsJson=true
```

#### <a name="collect-logs"></a><span data-ttu-id="b1bfc-356">로그 수집</span><span class="sxs-lookup"><span data-stu-id="b1bfc-356">Collect logs</span></span>

<span data-ttu-id="b1bfc-357">Analysis에 대 한 모니터링 백 엔드에는 4Apr에서 내보낸 로그를 공급할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-357">The logs emitted by Dapr can be fed into a monitoring back end for analysis.</span></span> <span data-ttu-id="b1bfc-358">로그 수집기는 시스템에서 로그를 수집 하 여 모니터링 백 엔드에 전송 하는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-358">A log collector is a component that collects logs from a system and sends them to a monitoring back end.</span></span> <span data-ttu-id="b1bfc-359">인기 있는 로그 수집기는 [Fluentd](https://www.fluentd.org/)입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-359">A popular log collector is [Fluentd](https://www.fluentd.org/).</span></span> <span data-ttu-id="b1bfc-360">자세한 내용은 [Fluentd에서 How to: Set Up, 탄력적 검색 및 Kibana in The Kubernetes in](https://docs.dapr.io/operations/monitoring/logging/fluentd/) The eapr 설명서를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-360">Check out the [How-To: Set up Fluentd, Elastic search and Kibana in Kubernetes](https://docs.dapr.io/operations/monitoring/logging/fluentd/) in the Dapr documentation.</span></span> <span data-ttu-id="b1bfc-361">이 문서에는 Fluentd as 로그 수집기 및 [Elk Stack](https://www.elastic.co/elastic-stack) (탄력적 검색 및 Kibana)을 모니터링 백 엔드로 설정 하기 위한 지침이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-361">This article contains instructions for setting up Fluentd as log collector and the [ELK Stack](https://www.elastic.co/elastic-stack) (Elastic Search and Kibana) as a monitoring back end.</span></span>

### <a name="health-status"></a><span data-ttu-id="b1bfc-362">상태</span><span class="sxs-lookup"><span data-stu-id="b1bfc-362">Health status</span></span>

<span data-ttu-id="b1bfc-363">서비스의 상태는 가용성에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-363">The health status of a service provides insight into its availability.</span></span> <span data-ttu-id="b1bfc-364">각 6Apr 사이드카는 호스팅 환경에서 사이드카 상태를 확인 하는 데 사용할 수 있는 상태 API를 노출 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-364">Each Dapr sidecar exposes a health API that can be used by the hosting environment to determine the health of the sidecar.</span></span> <span data-ttu-id="b1bfc-365">API에는 하나의 작업이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-365">The API has one operation:</span></span>

```console
GET http://localhost:3500/v1.0/healthz
```

<span data-ttu-id="b1bfc-366">작업은 두 개의 HTTP 상태 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-366">The operation returns two HTTP status codes:</span></span>

- <span data-ttu-id="b1bfc-367">204: 사이드카 정상적인 경우</span><span class="sxs-lookup"><span data-stu-id="b1bfc-367">204: When the sidecar is healthy</span></span>
- <span data-ttu-id="b1bfc-368">500: 사이드카 비정상 인 경우</span><span class="sxs-lookup"><span data-stu-id="b1bfc-368">500: when the sidecar isn't healthy</span></span>

<span data-ttu-id="b1bfc-369">자체 호스팅 모드로 실행 하는 경우 상태 API가 자동으로 호출 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-369">When running in self-hosted mode, the health API isn't automatically invoked.</span></span> <span data-ttu-id="b1bfc-370">응용 프로그램 코드 또는 상태 모니터링 도구를 통해 API를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-370">You can invoke the API though from application code or a health monitoring tool.</span></span>

<span data-ttu-id="b1bfc-371">Kubernetes에서 실행 하는 경우 사이드카 인젝터는 자동으로 Kubernetes를 구성 하 여 *선거의 프로브* 및 *준비 프로브* 를 실행 하는 상태 API를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-371">When running in Kubernetes, the Dapr sidecar-injector automatically configures Kubernetes to use the health API for executing *liveness probes* and *readiness probes*.</span></span>

<span data-ttu-id="b1bfc-372">Kubernetes는 선거의 프로브를 사용 하 여 컨테이너가 실행 중인지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-372">Kubernetes uses liveness probes to determine whether a container is up and running.</span></span> <span data-ttu-id="b1bfc-373">선거의 프로브에서 오류 코드를 반환 하는 경우 Kubernetes은 컨테이너가 비활성 이라고 가정 하 고 자동으로 다시 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-373">If a liveness probe returns a failure code, Kubernetes will assume the container is dead and automatically restart it.</span></span> <span data-ttu-id="b1bfc-374">이 기능은 응용 프로그램의 전반적인 가용성을 높입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-374">This feature increases the overall availability of your application.</span></span>

<span data-ttu-id="b1bfc-375">Kubernetes는 준비 프로브를 사용 하 여 컨테이너가 트래픽 수락을 시작할 준비가 되었는지 여부를 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-375">Kubernetes uses readiness probes to determine whether a container is ready to start accepting traffic.</span></span> <span data-ttu-id="b1bfc-376">모든 컨테이너가 준비 되 면 pod가 준비 된 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-376">A pod is considered ready when all of its containers are ready.</span></span> <span data-ttu-id="b1bfc-377">준비는 부하 분산 시나리오에서 Kubernetes 서비스가 pod로 트래픽을 보낼 수 있는지 여부를 결정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-377">Readiness determines whether a Kubernetes service can direct traffic to a pod in a load-balancing scenario.</span></span> <span data-ttu-id="b1bfc-378">준비 되지 않은 pod는 부하 분산 장치에서 자동으로 제거 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-378">Pods that aren't ready are automatically removed from the load-balancer.</span></span>

<span data-ttu-id="b1bfc-379">선거의 및 준비 프로브에는 몇 가지 구성 가능한 매개 변수가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-379">Liveness and readiness probes have several configurable parameters.</span></span> <span data-ttu-id="b1bfc-380">둘 다 pod 매니페스트 파일의 컨테이너 사양 섹션에서 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-380">Both are configured in the container spec section of a pod's manifest file.</span></span> <span data-ttu-id="b1bfc-381">기본적으로, 사이드카는 각 컨테이너에 대해 다음과 같은 구성을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-381">By default, Dapr uses the following configuration for each sidecar container:</span></span>

```yaml
livenessProbe:
      httpGet:
        path: v1.0/healthz
        port: 3500
      initialDelaySeconds: 5
      periodSeconds: 10
      timeoutSeconds : 5
      failureThreshold : 3
readinessProbe:
      httpGet:
        path: v1.0/healthz
        port: 3500
      initialDelaySeconds: 5
      periodSeconds: 10
      timeoutSeconds : 5
      failureThreshold: 3
```

 <span data-ttu-id="b1bfc-382">프로브에 사용할 수 있는 매개 변수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-382">The following parameters are available for the probes:</span></span>

- <span data-ttu-id="b1bfc-383">는 `path` Eapr 상태 API 끝점을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-383">The `path` specifies the Dapr health API endpoint.</span></span>
- <span data-ttu-id="b1bfc-384">는 `port` Eapr 상태 API 포트를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-384">The `port` specifies the Dapr health API port.</span></span>
- <span data-ttu-id="b1bfc-385">는 `initialDelaySeconds` 컨테이너를 처음 검색 하기 시작 하기 전에 Kubernetes가 대기 하는 시간 (초)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-385">The `initialDelaySeconds`specifies the number of seconds Kubernetes will wait before it starts probing a container for the first time.</span></span>
- <span data-ttu-id="b1bfc-386">`periodSeconds`Kubernetes 각 프로브 사이에 대기 하는 시간 (초)을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-386">The `periodSeconds` specifies the number of seconds Kubernetes will wait between each probe.</span></span>
- <span data-ttu-id="b1bfc-387">는 `timeoutSeconds` 제한 시간이 초과 되기 전에 Kubernetes가 API의 응답을 대기 하는 시간 (초)을 지정 합니다. 제한 시간은 실패로 해석 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-387">The `timeoutSeconds` specifies the number of seconds Kubernetes will wait on a response from the API before timing out. A timeout is interpreted as a failure.</span></span>
- <span data-ttu-id="b1bfc-388">는 `failureThreshold` 컨테이너를 연결 하지 않거나 준비 되지 않은 것으로 간주 하기 전에 Kubernetes에서 허용 하는 실패 상태 코드의 수를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-388">The `failureThreshold`specifies the number of failed status code Kubernetes will accept before considering the container not alive or not ready.</span></span>

### <a name="dapr-dashboard"></a><span data-ttu-id="b1bfc-389">4 월 대시보드</span><span class="sxs-lookup"><span data-stu-id="b1bfc-389">Dapr dashboard</span></span>

<span data-ttu-id="b1bfc-390">6apr는 응용 프로그램, 구성 요소 및 구성에 대 한 상태 정보를 제공 하는 대시보드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-390">Dapr offers a dashboard that presents status information on Dapr applications, components, and configurations.</span></span> <span data-ttu-id="b1bfc-391">App-v CLI를 사용 하 여 포트 8080에서 로컬 컴퓨터의 웹 응용 프로그램으로 대시보드를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-391">Use the Dapr CLI to start the dashboard as a web-application on the local machine on port 8080:</span></span>

```console
dapr dashboard
```

<span data-ttu-id="b1bfc-392">Kubernetes에서 실행 되는 Eapr 응용 프로그램의 경우 다음 명령을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-392">For Dapr application running in Kubernetes, use the following command:</span></span>

```console
dapr dashboard -k
```

<span data-ttu-id="b1bfc-393">응용 프로그램에서 사이드카가 있는 모든 서비스에 대 한 개요를 포함 하는 대시보드가 열립니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-393">The dashboard opens with an overview of all services in your application that have a Dapr sidecar.</span></span> <span data-ttu-id="b1bfc-394">다음 스크린샷은 Kubernetes에서 실행 되는 eShopOnDapr 응용 프로그램에 대 한 4 월 대시보드를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-394">The following screenshot shows the Dapr dashboard for the eShopOnDapr application running in Kubernetes:</span></span>

![6apr 대시보드 개요 페이지](media/observability/dapr-dashboard-overview.png)

<span data-ttu-id="b1bfc-396">4Apr 대시보드는 응용 프로그램의 문제를 해결할 때 매우 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-396">The Dapr dashboard is invaluable when troubleshooting a Dapr application.</span></span> <span data-ttu-id="b1bfc-397">이는 사이드카 및 시스템 서비스에 대 한 정보를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-397">It provides information about Dapr sidecars and system services.</span></span> <span data-ttu-id="b1bfc-398">로깅 항목을 포함 하 여 각 서비스의 구성으로 드릴 다운할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-398">You can drill down into the configuration of each service, including the logging entries.</span></span>

<span data-ttu-id="b1bfc-399">또한 대시보드는 응용 프로그램에 대해 구성 된 구성 요소 및 구성 요소를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-399">The dashboard also shows the configured components (and their configuration) for your application:</span></span>

![4apr 대시보드 구성 요소 페이지](media/observability/dapr-dashboard-components.png)

<span data-ttu-id="b1bfc-401">대시보드를 통해 사용할 수 있는 많은 양의 정보가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-401">There's a large amount of information available through the dashboard.</span></span> <span data-ttu-id="b1bfc-402">응용 프로그램을 검색 하 고, 응용 프로그램을 검색 하 고, 대시보드를 찾아볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-402">You can discover it by running a Dapr application and browsing the dashboard.</span></span> <span data-ttu-id="b1bfc-403">함께 제공 되는 eShopOnDapr 응용 프로그램을 사용 하 여를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-403">You can use the accompanying eShopOnDapr application to start.</span></span>

<span data-ttu-id="b1bfc-404">Eapr 대시보드 명령에 대 한 자세한 내용은이 문서에서 eapr [대시보드 CLI 명령 참조](https://docs.dapr.io/reference/cli/dapr-dashboard/) 를 확인 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-404">Check out the [Dapr dashboard CLI command reference](https://docs.dapr.io/reference/cli/dapr-dashboard/) in the Dapr docs for more information on the Dapr dashboard commands.</span></span>

## <a name="use-the-dapr-net-sdk"></a><span data-ttu-id="b1bfc-405">Dapr .NET SDK 사용</span><span class="sxs-lookup"><span data-stu-id="b1bfc-405">Use the Dapr .NET SDK</span></span>

<span data-ttu-id="b1bfc-406">Dapr .NET SDK는 특정 관찰성 기능을 포함 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-406">The Dapr .NET SDK doesn't contain any specific observability features.</span></span> <span data-ttu-id="b1bfc-407">모든 관찰성 기능은 Aapr 수준에서 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-407">All observability features are offered at the Dapr level.</span></span>

<span data-ttu-id="b1bfc-408">.NET 응용 프로그램 코드에서 원격 분석을 내보내려는 경우 [.net 용 OPENTELEMETRY SDK](https://opentelemetry.io/docs/net/)를 고려해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-408">If you want to emit telemetry from your .NET application code, you should consider the [OpenTelemetry SDK for .NET](https://opentelemetry.io/docs/net/).</span></span> <span data-ttu-id="b1bfc-409">개방형 원격 분석 프로젝트는 플랫폼 간, 오픈 소스 및 공급 업체에 관계 없이 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-409">The Open Telemetry project is cross-platform, open source, and vendor agnostic.</span></span> <span data-ttu-id="b1bfc-410">원격 분석 데이터를 생성, 내보내기, 수집, 처리 및 내보내는 종단 간 구현을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-410">It provides an end-to-end implementation to generate, emit, collect, process, and export telemetry data.</span></span> <span data-ttu-id="b1bfc-411">자동 및 수동 계측을 지 원하는 언어 마다 단일 계측 라이브러리가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-411">There's a single instrumentation library per language that supports automatic and manual instrumentation.</span></span> <span data-ttu-id="b1bfc-412">원격 분석은 오픈 원격 분석 표준을 사용 하 여 게시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-412">Telemetry is published using the Open Telemetry standard.</span></span> <span data-ttu-id="b1bfc-413">이 프로젝트에는 클라우드 공급자, 공급 업체 및 최종 사용자의 광범위 한 업계 지원 및 채택이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-413">The project has broad industry support and adoption from cloud providers, vendors, and end users.</span></span>

## <a name="reference-application-eshopondapr"></a><span data-ttu-id="b1bfc-414">참조 응용 프로그램: eShopOnDapr</span><span class="sxs-lookup"><span data-stu-id="b1bfc-414">Reference application: eShopOnDapr</span></span>

<span data-ttu-id="b1bfc-415">함께 제공 되는 eShopOnDapr reference 응용 프로그램의 관찰성는 여러 부분으로 구성 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-415">Observability in accompanying eShopOnDapr reference application consists of several parts.</span></span> <span data-ttu-id="b1bfc-416">모든 사이드카의 원격 분석이 캡처됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-416">Telemetry from all of the sidecars is captured.</span></span> <span data-ttu-id="b1bfc-417">또한 이전 eShopOnContainers 샘플에서 상속 된 다른 관찰성 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-417">Additionally, there are other observability features inherited from the earlier eShopOnContainers sample.</span></span>

### <a name="custom-health-dashboard"></a><span data-ttu-id="b1bfc-418">사용자 지정 상태 대시보드</span><span class="sxs-lookup"><span data-stu-id="b1bfc-418">Custom health dashboard</span></span>

<span data-ttu-id="b1bfc-419">EShopOnDapr의 **Webstatus** 프로젝트는 eShop 서비스의 상태에 대 한 통찰력을 제공 하는 사용자 지정 상태 대시보드입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-419">The **WebStatus** project in eShopOnDapr is a custom health dashboard that gives insight into the health of the eShop services.</span></span> <span data-ttu-id="b1bfc-420">이 대시보드는 Eapr 상태 API를 사용 하지 않지만 ASP.NET Core의 기본 제공 [상태 검사 메커니즘](/aspnet/core/host-and-deploy/health-checks) 을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-420">This dashboard doesn't use the Dapr health API but uses the built-in [health checks mechanism](/aspnet/core/host-and-deploy/health-checks) of ASP.NET Core.</span></span> <span data-ttu-id="b1bfc-421">대시보드는 서비스의 상태 뿐만 아니라 서비스의 종속성 상태를 제공할 뿐입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-421">The dashboard not only provides the health status of the services, but also the health of the dependencies of the services.</span></span> <span data-ttu-id="b1bfc-422">예를 들어 데이터베이스를 사용 하는 서비스는 다음 스크린샷에 표시 된 것 처럼이 데이터베이스의 상태를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-422">For example, a service that uses a database also provides the health status of this database as shown in the following screenshot:</span></span>

![eShopOnDapr 사용자 지정 상태 대시보드](media/observability/eshop-health-dashboard.png)

### <a name="seq-log-aggregator"></a><span data-ttu-id="b1bfc-424">Seq 로그 집계</span><span class="sxs-lookup"><span data-stu-id="b1bfc-424">Seq log aggregator</span></span>

<span data-ttu-id="b1bfc-425">[Seq](https://datalust.co/seq) 는 eShopOnDapr에서 로그를 집계 하는 데 사용 되는 인기 있는 로그 집계 서버입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-425">[Seq](https://datalust.co/seq) is a popular log aggregator server that is used in eShopOnDapr to aggregate logs.</span></span> <span data-ttu-id="b1bfc-426">Seq 수집는 응용 프로그램 서비스에서 로깅하는 반면, Eapr 시스템 서비스 또는 사이드카에서는 로깅 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-426">Seq ingests logging from application services, but not from Dapr system services or sidecars.</span></span> <span data-ttu-id="b1bfc-427">Seq 인덱스 응용 프로그램은 로그를 분석 하 고 쿼리 하는 웹 프런트 엔드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-427">Seq indexes application logging and offers a web front end for analyzing and querying the logs.</span></span> <span data-ttu-id="b1bfc-428">또한 모니터링 대시보드를 빌드하기 위한 기능도 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-428">It also offers functionality for building monitoring dashboards.</span></span>

<span data-ttu-id="b1bfc-429">EShopOnDapr 응용 프로그램 서비스는 [SeriLog](https://serilog.net/) 로깅 라이브러리를 사용 하 여 구조적 로깅을 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-429">The eShopOnDapr application services emit structured logging using the [SeriLog](https://serilog.net/) logging library.</span></span> <span data-ttu-id="b1bfc-430">Serilog는 **싱크** 라는 구문에 로그 이벤트를 게시 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-430">Serilog publishes log events to a construct called a **sink**.</span></span> <span data-ttu-id="b1bfc-431">싱크는 Serilog에서 로깅 이벤트를 작성 하는 대상 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-431">A sink is simply a target platform to which Serilog writes its logging events.</span></span> <span data-ttu-id="b1bfc-432">Seq 용 하나를 포함 하 여 [많은 Serilog 싱크를 사용할 수](https://github.com/serilog/serilog/wiki/Provided-Sinks)있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-432">[Many Serilog sinks are available](https://github.com/serilog/serilog/wiki/Provided-Sinks), including one for Seq.</span></span> <span data-ttu-id="b1bfc-433">Seq는 eShopOnDapr에서 사용 되는 Serilog 싱크입니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-433">Seq is the Serilog sink used in eShopOnDapr.</span></span>

### <a name="application-insights"></a><span data-ttu-id="b1bfc-434">Application Insights</span><span class="sxs-lookup"><span data-stu-id="b1bfc-434">Application Insights</span></span>

<span data-ttu-id="b1bfc-435">eShopOnDapr services는 .NET Core 용 Microsoft Application Insights SDK를 사용 하 여 Azure 애플리케이션 Insights에 직접 원격 분석을 보냅니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-435">eShopOnDapr services also send telemetry directly to Azure Application Insights using the Microsoft Application Insights SDK for .NET Core.</span></span> <span data-ttu-id="b1bfc-436">자세한 내용은 Microsoft 문서에서 [ASP.NET Core 응용 프로그램에 대 한 Azure 애플리케이션 정보](/azure/azure-monitor/app/asp-net-core) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-436">For more information, see [Azure Application Insights for ASP.NET Core applications](/azure/azure-monitor/app/asp-net-core) in the Microsoft docs.</span></span>

## <a name="summary"></a><span data-ttu-id="b1bfc-437">요약</span><span class="sxs-lookup"><span data-stu-id="b1bfc-437">Summary</span></span>

<span data-ttu-id="b1bfc-438">프로덕션 환경에서 분산 시스템을 실행할 때는 좋은 관찰성 중요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-438">Good observability is crucial when running a distributed system in production.</span></span>

<span data-ttu-id="b1bfc-439">D 4는 분산 추적, 로깅, 메트릭 및 상태를 포함 하 여 다양 한 유형의 원격 분석을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-439">Dapr provides different types of telemetry, including distributed tracing, logging, metrics, and health status.</span></span>

<span data-ttu-id="b1bfc-440">D 4는 사이드카 시스템 서비스 및에 대 한 원격 분석만 생성 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-440">Dapr only produces telemetry for the Dapr system services and sidecars.</span></span> <span data-ttu-id="b1bfc-441">응용 프로그램 코드에서 원격 분석은 자동으로 포함 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-441">Telemetry from your application code isn't automatically included.</span></span> <span data-ttu-id="b1bfc-442">그러나 .NET 용 OpenTelemetry SDK와 같은 특정 SDK를 사용 하 여 응용 프로그램 코드에서 원격 분석을 내보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-442">You can however use a specific SDK like the OpenTelemetry SDK for .NET to emit telemetry from your application code.</span></span>

<span data-ttu-id="b1bfc-443">4apr 원격 분석은 오픈 표준 기반 형식으로 생성 되므로 사용 가능한 다양 한 모니터링 도구 집합으로 수집 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-443">Dapr telemetry is produced in an open-standards based format so it can be ingested by a large set of available monitoring tools.</span></span> <span data-ttu-id="b1bfc-444">몇 가지 예로는 Zipkin, Azure 애플리케이션 Insights, ELK Stack, New 유물, Grafana 등이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-444">Some examples are: Zipkin, Azure Application Insights, the ELK Stack, New Relic, and Grafana.</span></span> <span data-ttu-id="b1bfc-445">특정 모니터링 백 엔드를 사용 하 여 응용 프로그램을 모니터링 하는 방법에 대 한 자습서는 6Apr 설명서에서 [응용 프로그램 모니터링](https://docs.dapr.io/operations/monitoring/) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-445">See [Monitor your application with Dapr](https://docs.dapr.io/operations/monitoring/) in the Dapr documentation for tutorials on how to monitor your Dapr applications with specific monitoring back ends.</span></span>

<span data-ttu-id="b1bfc-446">원격 분석을 수집 하 고 모니터링 백 엔드에 게시 하는 원격 분석 scraper 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-446">You'll need a telemetry scraper that ingests telemetry and publishes it to the monitoring back end.</span></span>

<span data-ttu-id="b1bfc-447">구조적 로깅을 내보내도록 capr를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-447">Dapr can be configured to emit structured logging.</span></span> <span data-ttu-id="b1bfc-448">구조적 로깅은 백 엔드 모니터링 도구를 통해 인덱싱될 수 있으므로 선호 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-448">Structured logging is favored as it can be indexed by back-end monitoring tools.</span></span> <span data-ttu-id="b1bfc-449">인덱싱된 로깅은 사용자가 로깅을 검색할 때 풍부한 쿼리를 실행할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-449">Indexed logging enables users to execute rich queries when searching through the logging.</span></span>

<span data-ttu-id="b1bfc-450">6apr는 단일 서비스 및 구성에 대 한 정보를 제공 하는 대시보드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1bfc-450">Dapr offers a dashboard that presents information about the Dapr services and configuration.</span></span>

## <a name="references"></a><span data-ttu-id="b1bfc-451">참조</span><span class="sxs-lookup"><span data-stu-id="b1bfc-451">References</span></span>

- [<span data-ttu-id="b1bfc-452">Azure Application Insights</span><span class="sxs-lookup"><span data-stu-id="b1bfc-452">Azure Application Insights</span></span>](/azure/azure-monitor/app/app-insights-overview/)
- [<span data-ttu-id="b1bfc-453">원격 분석 열기</span><span class="sxs-lookup"><span data-stu-id="b1bfc-453">Open Telemetry</span></span>](https://opentelemetry.io/)
- [<span data-ttu-id="b1bfc-454">Zipkin</span><span class="sxs-lookup"><span data-stu-id="b1bfc-454">Zipkin</span></span>](https://zipkin.io/)
- [<span data-ttu-id="b1bfc-455">W3C 추적 컨텍스트</span><span class="sxs-lookup"><span data-stu-id="b1bfc-455">W3C Trace Context</span></span>](https://www.w3.org/TR/trace-context/)
- [<span data-ttu-id="b1bfc-456">Jaeger</span><span class="sxs-lookup"><span data-stu-id="b1bfc-456">Jaeger</span></span>](https://www.jaegertracing.io/)
- [<span data-ttu-id="b1bfc-457">New Relic</span><span class="sxs-lookup"><span data-stu-id="b1bfc-457">New Relic</span></span>](https://newrelic.com/)
- [<span data-ttu-id="b1bfc-458">Prometheus</span><span class="sxs-lookup"><span data-stu-id="b1bfc-458">Prometheus</span></span>](https://prometheus.io/)
- [<span data-ttu-id="b1bfc-459">Grafana</span><span class="sxs-lookup"><span data-stu-id="b1bfc-459">Grafana</span></span>](https://grafana.com/grafana/)
- [<span data-ttu-id="b1bfc-460">.NET 용 원격 분석 SDK 열기</span><span class="sxs-lookup"><span data-stu-id="b1bfc-460">Open Telemetry SDK for .NET</span></span>](https://opentelemetry.io/docs/net/)
- [<span data-ttu-id="b1bfc-461">Fluentd</span><span class="sxs-lookup"><span data-stu-id="b1bfc-461">Fluentd</span></span>](https://www.fluentd.org/)
- [<span data-ttu-id="b1bfc-462">ELK 스택</span><span class="sxs-lookup"><span data-stu-id="b1bfc-462">ELK stack</span></span>](https://www.elastic.co/elastic-stack)
- [<span data-ttu-id="b1bfc-463">차이가</span><span class="sxs-lookup"><span data-stu-id="b1bfc-463">Seq</span></span>](https://datalust.co/seq)
- [<span data-ttu-id="b1bfc-464">Serilog</span><span class="sxs-lookup"><span data-stu-id="b1bfc-464">Serilog</span></span>](https://serilog.net/)

> [!div class="step-by-step"]
> <span data-ttu-id="b1bfc-465">[이전](bindings.md)
> [다음](secrets.md)</span><span class="sxs-lookup"><span data-stu-id="b1bfc-465">[Previous](bindings.md)
[Next](secrets.md)</span></span>
