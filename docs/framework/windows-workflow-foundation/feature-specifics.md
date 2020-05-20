---
title: Windows Workflow Foundation 기능 특성
description: 이 문서에서는 .NET Framework 4에서 Windows Workflow Foundation에 추가 하 고 기능이 유용할 수 있는 시나리오에 대해 설명 합니다.
ms.date: 03/30/2017
ms.assetid: e84d12da-a055-45f6-b4d1-878d127b46b6
ms.openlocfilehash: fb490b3dd368710bf2ed98f7c53b7b184fa15b0b
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83419956"
---
# <a name="windows-workflow-foundation-feature-specifics"></a><span data-ttu-id="85fde-103">Windows Workflow Foundation 기능 특성</span><span class="sxs-lookup"><span data-stu-id="85fde-103">Windows Workflow Foundation Feature Specifics</span></span>

<span data-ttu-id="85fde-104">.NET Framework 4는 Windows Workflow Foundation에 많은 기능을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-104">.NET Framework 4 adds a number of features to Windows Workflow Foundation.</span></span> <span data-ttu-id="85fde-105">이 문서에서는 여러 새로운 기능을 설명하고 이러한 기능이 유용할 수 있는 시나리오에 대한 세부 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-105">This document describes a number of the new features, and gives details about scenarios in which they may be useful.</span></span>

## <a name="messaging-activities"></a><span data-ttu-id="85fde-106">메시징 활동</span><span class="sxs-lookup"><span data-stu-id="85fde-106">Messaging Activities</span></span>

<span data-ttu-id="85fde-107">메시징 활동 ( <xref:System.ServiceModel.Activities.Receive> , <xref:System.ServiceModel.Activities.SendReply> , <xref:System.ServiceModel.Activities.Send> , <xref:System.ServiceModel.Activities.ReceiveReply> )은 워크플로에서 WCF 메시지를 보내고 받는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-107">The messaging activities (<xref:System.ServiceModel.Activities.Receive>, <xref:System.ServiceModel.Activities.SendReply>, <xref:System.ServiceModel.Activities.Send>, <xref:System.ServiceModel.Activities.ReceiveReply>) are used to send and receive WCF messages from your workflow.</span></span> <span data-ttu-id="85fde-108"><xref:System.ServiceModel.Activities.Receive>및 <xref:System.ServiceModel.Activities.SendReply> 활동은 표준 wcf 웹 서비스와 마찬가지로 WSDL을 통해 노출 되는 wcf (Windows Communication Foundation) 서비스 작업을 구성 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-108"><xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> activities are used to form a Windows Communication Foundation (WCF) service operation that is exposed via WSDL just like standard WCF web services.</span></span> <span data-ttu-id="85fde-109"><xref:System.ServiceModel.Activities.Send>및 <xref:System.ServiceModel.Activities.ReceiveReply> 는 WCF와 유사한 웹 서비스를 사용 하는 데 사용 됩니다. <xref:System.ServiceModel.ChannelFactory> 미리 구성 된 작업을 생성 하는 Workflow Foundation에 대 한 **서비스 참조 추가** 환경이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-109"><xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply> are used to consume a web service similar to a WCF <xref:System.ServiceModel.ChannelFactory>; an **Add Service Reference** experience also exists for Workflow Foundation that generates pre-configured activities.</span></span>

### <a name="getting-started-with-messaging-activities"></a><span data-ttu-id="85fde-110">메시징 작업 시작</span><span class="sxs-lookup"><span data-stu-id="85fde-110">Getting Started with Messaging Activities</span></span>

- <span data-ttu-id="85fde-111">Visual Studio 2012에서 WCF 워크플로 서비스 응용 프로그램 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-111">In Visual Studio 2012, create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="85fde-112"><xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 쌍이 캔버스에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-112">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas.</span></span>

- <span data-ttu-id="85fde-113">프로젝트를 마우스 오른쪽 단추로 클릭 하 고 **서비스 참조 추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-113">Right-click on the project and select **Add Service Reference**.</span></span> <span data-ttu-id="85fde-114">기존 웹 서비스 WSDL을 가리키고 **확인**을 클릭 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-114">Point to an existing web service WSDL and click **OK**.</span></span> <span data-ttu-id="85fde-115">프로젝트를 빌드하여 도구 상자에 생성 된 작업 (및를 사용 하 여 구현 됨)을 표시 <xref:System.ServiceModel.Activities.Send> <xref:System.ServiceModel.Activities.ReceiveReply> 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-115">Build your project to show the generated activities (implemented using <xref:System.ServiceModel.Activities.Send> and <xref:System.ServiceModel.Activities.ReceiveReply>) in your toolbox.</span></span>

- [<span data-ttu-id="85fde-116">워크플로 서비스 설명서</span><span class="sxs-lookup"><span data-stu-id="85fde-116">Workflow services documentation</span></span>](../wcf/feature-details/workflow-services.md)

### <a name="messaging-activities-example-scenario"></a><span data-ttu-id="85fde-117">메시징 작업 예제 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-117">Messaging Activities Example Scenario</span></span>

<span data-ttu-id="85fde-118">`BestPriceFinder`서비스는 여러 항공편 서비스를 호출 하 여 특정 경로에 대 한 최상의 티켓 가격을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-118">A `BestPriceFinder` service calls out to multiple airline services to find the best ticket price for a particular route.</span></span> <span data-ttu-id="85fde-119">이 시나리오를 구현 하려면 메시지 활동을 사용 하 여 가격 요청을 받고, 백 엔드 서비스에서 가격을 검색 하 고, 최상의 가격으로 가격 요청에 회신 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-119">Implementing this scenario would require you to use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span> <span data-ttu-id="85fde-120">또한 다른 기본 작업을 사용 하 여 최상의 가격을 계산 하는 비즈니스 논리를 만들어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-120">It would also require you to use other out-of-box activities to create the business logic for calculating the best price.</span></span>

## <a name="workflowservicehost"></a><span data-ttu-id="85fde-121">WorkflowServiceHost</span><span class="sxs-lookup"><span data-stu-id="85fde-121">WorkflowServiceHost</span></span>

<span data-ttu-id="85fde-122">는 <xref:System.ServiceModel.WorkflowServiceHost> 여러 인스턴스, 구성 및 WCF 메시징을 지 원하는 기본 워크플로 호스트입니다 (워크플로는 호스팅을 위해 메시징을 사용할 필요가 없음).</span><span class="sxs-lookup"><span data-stu-id="85fde-122">The <xref:System.ServiceModel.WorkflowServiceHost> is the out-of-box workflow host that supports multiple instances, configuration, and WCF messaging (although the workflows aren't required to use messaging in order to be hosted).</span></span> <span data-ttu-id="85fde-123">서비스 동작의 집합을 통해 지속성, 추적 및 인스턴스 제어와 통합됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-123">It also integrates with persistence, tracking, and instance control through a set of service behaviors.</span></span> <span data-ttu-id="85fde-124">WCF의와 마찬가지로 <xref:System.ServiceModel.ServiceHost> 는 <xref:System.ServiceModel.WorkflowServiceHost> IIS 또는 WAS에서 Console/WINFORMS/WPF 응용 프로그램 또는 Windows 서비스 또는 웹 호스팅 (.xamlx 파일로)에서 자체 호스팅될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-124">Just like WCF's <xref:System.ServiceModel.ServiceHost>, the <xref:System.ServiceModel.WorkflowServiceHost> can be self-hosted in a console/WinForms/WPF application or Windows service, or web-hosted (as a .xamlx file) in IIS or WAS.</span></span>

### <a name="getting-started-with-workflow-service-host"></a><span data-ttu-id="85fde-125">워크플로 서비스 호스트 시작</span><span class="sxs-lookup"><span data-stu-id="85fde-125">Getting Started with Workflow Service Host</span></span>

- <span data-ttu-id="85fde-126">Visual Studio 2010에서 WCF 워크플로 서비스 응용 프로그램 프로젝트를 만듭니다 .이 프로젝트는 <xref:System.ServiceModel.WorkflowServiceHost> 웹 호스트 환경에서 사용 하도록 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-126">In Visual Studio 2010, create a WCF Workflow Service Application project: this project will be set up to use <xref:System.ServiceModel.WorkflowServiceHost> in a web-host environment.</span></span>

- <span data-ttu-id="85fde-127">메시징이 아닌 워크플로를 호스트하려면 메시지를 기반으로 하는 인스턴스를 만들 사용자 지정 <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-127">In order to host a non-messaging workflow, add a custom <xref:System.ServiceModel.Activities.WorkflowHostingEndpoint> that will create the instance based on a message.</span></span>

- <span data-ttu-id="85fde-128"><xref:System.ServiceModel.Activities.WorkflowControlEndpoint>에 <xref:System.ServiceModel.WorkflowServiceHost>를 추가한 다음 <xref:System.ServiceModel.Activities.WorkflowControlClient>를 사용하여 워크플로 인스턴스를 제어(예: 일시 중단 또는 종료)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-128">Workflow instances can be controlled (e.g. suspended or terminated) by adding a <xref:System.ServiceModel.Activities.WorkflowControlEndpoint> to the <xref:System.ServiceModel.WorkflowServiceHost> and then using a <xref:System.ServiceModel.Activities.WorkflowControlClient>.</span></span>

- <span data-ttu-id="85fde-129"><xref:System.ServiceModel.WorkflowServiceHost>에 대한 샘플은 다음 단원에서 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-129">Samples for the <xref:System.ServiceModel.WorkflowServiceHost> can be found in the following sections:</span></span>

  - [<span data-ttu-id="85fde-130">실행</span><span class="sxs-lookup"><span data-stu-id="85fde-130">Execution</span></span>](./samples/execution.md)

  - <span data-ttu-id="85fde-131">응용 프로그램: [일시 중단 된 인스턴스 관리](./samples/suspended-instance-management.md)</span><span class="sxs-lookup"><span data-stu-id="85fde-131">Application: [Suspended Instance Management](./samples/suspended-instance-management.md)</span></span>

- [<span data-ttu-id="85fde-132">워크플로 서비스 호스팅 개요</span><span class="sxs-lookup"><span data-stu-id="85fde-132">Hosting Workflow services overview</span></span>](../wcf/feature-details/hosting-workflow-services-overview.md)

### <a name="workflowservicehost-scenario"></a><span data-ttu-id="85fde-133">WorkflowServiceHost 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-133">WorkflowServiceHost Scenario</span></span>

<span data-ttu-id="85fde-134">BestPriceFinder 서비스는 여러 항공편 서비스를 호출 하 여 특정 경로에 대 한 최상의 티켓 가격을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-134">A BestPriceFinder service calls out to multiple airline services to find the best ticket price for a particular route.</span></span> <span data-ttu-id="85fde-135">이 시나리오를 구현 하려면에서 워크플로를 호스트 해야 <xref:System.ServiceModel.WorkflowServiceHost> 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-135">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost>.</span></span> <span data-ttu-id="85fde-136">또한 메시지 활동을 사용 하 여 가격 요청을 받고, 백 엔드 서비스에서 가격을 검색 하 고, 최상의 가격으로 가격 요청에 회신 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-136">It would also use the message activities to receive the price request, retrieve the prices from the back-end services, and reply to the price request with the best price.</span></span>

## <a name="correlation"></a><span data-ttu-id="85fde-137">Correlation</span><span class="sxs-lookup"><span data-stu-id="85fde-137">Correlation</span></span>

<span data-ttu-id="85fde-138">상관 관계는 다음 두 가지 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-138">A correlation is one of two things:</span></span>

- <span data-ttu-id="85fde-139">메시지를 그룹화하는 방법(즉, 요청 메시지와 회신 간의 관계)</span><span class="sxs-lookup"><span data-stu-id="85fde-139">A way of grouping messages together; that is, the relationship between a request message and its reply.</span></span>

- <span data-ttu-id="85fde-140">데이터를 서비스 인스턴스에 매핑하는 방법</span><span class="sxs-lookup"><span data-stu-id="85fde-140">A way of mapping a piece of data to a service instance</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-141">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-141">Getting Started</span></span>

- <span data-ttu-id="85fde-142">상관 관계를 시작하려면 Visual Studio에서 새 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-142">To get started with correlation, create a new project in Visual Studio.</span></span> <span data-ttu-id="85fde-143"><xref:System.ServiceModel.Activities.CorrelationHandle> 형식의 변수를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-143">Create a variable of type <xref:System.ServiceModel.Activities.CorrelationHandle>.</span></span>

- <span data-ttu-id="85fde-144">메시지를 그룹화하는 데 사용되는 상관 관계의 예로 메시지를 그룹화하는 요청-회신 상관 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-144">An example of correlation used to group messages together is a Request-Reply correlation that groups messages together.</span></span>

  - <span data-ttu-id="85fde-145">활동에서 <xref:System.ServiceModel.Activities.Receive> 속성을 클릭 하 <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> 고 <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> 위의 첫 번째 단계에서 만든 CorrelationHandle를 사용 하 여를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-145">On a <xref:System.ServiceModel.Activities.Receive> activity, click on the <xref:System.ServiceModel.Activities.Receive.CorrelationInitializers%2A> property and add a <xref:System.ServiceModel.Activities.RequestReplyCorrelationInitializer> using the CorrelationHandle created in the first step above.</span></span>

  - <span data-ttu-id="85fde-146"><xref:System.ServiceModel.Activities.SendReply>를 마우스 오른쪽 단추로 클릭 하 <xref:System.ServiceModel.Activities.Receive> 고 "SendReply 만들기"를 클릭 하 여 활동을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-146">Create a <xref:System.ServiceModel.Activities.SendReply> activity by right-clicking on the <xref:System.ServiceModel.Activities.Receive> and clicking "Create SendReply".</span></span> <span data-ttu-id="85fde-147">워크플로에서 <xref:System.ServiceModel.Activities.Receive> 작업 뒤에 이 작업을 붙여 넣습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-147">Paste it into your workflow after the <xref:System.ServiceModel.Activities.Receive> activity.</span></span>

- <span data-ttu-id="85fde-148">데이터를 서비스 인스턴스에 매핑하는 예로 데이터(예: 주문 ID)를 특정 워크플로 인스턴스에 매핑하는 콘텐츠 기반 상관 관계가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-148">An example of mapping a piece of data to a service instance is content-based correlation which maps a piece of data (for example, an order ID) to a particular workflow instance.</span></span>

  - <span data-ttu-id="85fde-149">아무 메시징 작업에서나 `CorrelationInitializers` 속성을 클릭하고 위에서 만든 <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> 변수를 사용하여 <xref:System.ServiceModel.Activities.CorrelationHandle>를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-149">On any messaging activity, click on the `CorrelationInitializers` property and add a <xref:System.ServiceModel.Activities.QueryCorrelationInitializer> using the <xref:System.ServiceModel.Activities.CorrelationHandle> variable created above.</span></span> <span data-ttu-id="85fde-150">드롭다운 메뉴에서 원하는 메시지 속성(예: OrderID)을 두 번 클릭합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-150">Double-click on the desired property on the message (e.g. OrderID) from the drop-down menu.</span></span> <span data-ttu-id="85fde-151">`CorrelatesWith` 속성을 위에서 사용한 <xref:System.ServiceModel.Activities.CorrelationHandle> 변수로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-151">Set the `CorrelatesWith` property to the <xref:System.ServiceModel.Activities.CorrelationHandle> variable used above.</span></span>

- [<span data-ttu-id="85fde-152">상관 관계 개념 설명서</span><span class="sxs-lookup"><span data-stu-id="85fde-152">Correlation Conceptual Documentation</span></span>](../wcf/feature-details/correlation.md)

### <a name="correlation-scenario"></a><span data-ttu-id="85fde-153">상관 관계 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-153">Correlation Scenario</span></span>

<span data-ttu-id="85fde-154">주문 처리 워크플로는 새 주문 만들기를 처리 하 고 처리 중인 기존 주문을 업데이트 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-154">An order-processing workflow is used to handle new order creation and updating existing orders that are in process.</span></span> <span data-ttu-id="85fde-155">이 시나리오를 구현 하려면에서 워크플로를 호스트 하 <xref:System.ServiceModel.WorkflowServiceHost> 고 메시징 작업을 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-155">Implementing this scenario would require you to host the workflow in <xref:System.ServiceModel.WorkflowServiceHost> and use the messaging activities.</span></span> <span data-ttu-id="85fde-156">또한 `orderId` 올바른 워크플로가 업데이트 되도록 하기 위해를 기반으로 하는 상관 관계가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-156">It would also require correlation based on the `orderId` to ensure that updates are made to the correct workflow.</span></span>

## <a name="simplified-configuration"></a><span data-ttu-id="85fde-157">단순화된 구성</span><span class="sxs-lookup"><span data-stu-id="85fde-157">Simplified Configuration</span></span>

<span data-ttu-id="85fde-158">WCF 구성 스키마는 복잡 하며 사용자에 게 다양 한 기능을 찾을 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-158">The WCF configuration schema is complex and provides users with many hard to find features.</span></span> <span data-ttu-id="85fde-159">에서는 [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)] WCF 사용자가 다음과 같은 기능을 사용 하 여 서비스를 구성 하는 데 중점을 두었습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-159">In [!INCLUDE[netfx_current_short](../../../includes/netfx-current-short-md.md)], we have focused on helping WCF users configure their services with the following features:</span></span>

- <span data-ttu-id="85fde-160">서비스별 명시적 구성의 필요성을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-160">Removing the need for explicit per-service configuration.</span></span> <span data-ttu-id="85fde-161">서비스 \< 에 대 한 서비스> 요소를 구성 하지 않고 서비스에서 프로그래밍 방식으로 끝점을 정의 하지 않는 경우 서비스 기준 주소와 서비스에 의해 구현 되는 계약 당 하나씩, 끝점 집합이 서비스에 자동으로 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-161">If you do not configure any \<service> elements for your service, and your service does not define programmatically any endpoint, then a set of endpoints will be automatically added to your service, one per service base address and per contract implemented by your service.</span></span>

- <span data-ttu-id="85fde-162">사용자가 명시적 구성 없이 서비스에 적용될 WCF 바인딩 및 동작의 기본값을 정의할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-162">Enables the user to define default values for WCF bindings and behaviors, which will be applied to services with no explicit configuration.</span></span>

- <span data-ttu-id="85fde-163">표준 엔드포인트는 하나 이상의 엔드포인트 속성(주소, 바인딩 및 계약)에 대한 고정 값이 있는 미리 구성된 다시 사용 가능 엔드포인트를 정의하며 사용자 지정 속성 정의를 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-163">Standard endpoints define reusable preconfigured endpoints, which have fixed values for one or more of the endpoint properties (address, binding and contract), and allow defining custom properties.</span></span>

- <span data-ttu-id="85fde-164">마지막으로,를 <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> 사용 하면 응용 프로그램 도메인 로드 시간 후에 구성을 선택 하거나 변경 하는 시나리오에서 유용한 WCF 클라이언트 구성의 중앙 관리를 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-164">Finally, the <xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601> allows you to do central management of WCF client configuration, useful in scenarios in which configuration is selected or changed after the application domain load time.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-165">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-165">Getting Started</span></span>

- <span data-ttu-id="85fde-166">[WCF 4.0 개발자 가이드](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))</span><span class="sxs-lookup"><span data-stu-id="85fde-166">[A Developer's Guide to WCF 4.0](https://docs.microsoft.com/previous-versions/dotnet/articles/ee354381(v=msdn.10))</span></span>

- [<span data-ttu-id="85fde-167">구성 채널 팩터리</span><span class="sxs-lookup"><span data-stu-id="85fde-167">Configuration Channel Factory</span></span>](xref:System.ServiceModel.Configuration.ConfigurationChannelFactory%601)

- [<span data-ttu-id="85fde-168">표준 엔드포인트 요소</span><span class="sxs-lookup"><span data-stu-id="85fde-168">Standard Endpoint Element</span></span>](xref:System.ServiceModel.Configuration.StandardEndpointElement)

- [<span data-ttu-id="85fde-169">.NET Framework 4의 서비스 구성 개선</span><span class="sxs-lookup"><span data-stu-id="85fde-169">Service configuration improvements in .NET Framework 4</span></span>](https://docs.microsoft.com/archive/blogs/endpoint/service-configuration-improvements-in-net-4)

- [<span data-ttu-id="85fde-170">.NET 4의 일반적인 사용자 오류: WF/WCF 서비스 구성 이름의 잘못된 입력</span><span class="sxs-lookup"><span data-stu-id="85fde-170">Common User Mistake in .NET 4: Mistyping the WF/WCF Service Configuration Name</span></span>](https://docs.microsoft.com/archive/blogs/endpoint/common-user-mistake-in-net-4-mistyping-the-wfwcf-service-configuration-name)

### <a name="simplified-configuration-scenarios"></a><span data-ttu-id="85fde-171">단순화된 구성 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-171">Simplified Configuration Scenarios</span></span>

- <span data-ttu-id="85fde-172">숙련 된 ASMX 개발자가 WCF 사용을 시작 하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-172">An experienced ASMX developer wants to start using WCF.</span></span> <span data-ttu-id="85fde-173">그러나 WCF는 너무 복잡 한 것 같습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-173">However, WCF seems way too complicated!</span></span> <span data-ttu-id="85fde-174">구성 파일을 작성하는 데 필요한 모든 정보는 무엇입니까?</span><span class="sxs-lookup"><span data-stu-id="85fde-174">What is all that information that I need to write in a configuration file?</span></span> <span data-ttu-id="85fde-175">.NET 4에서는 구성 파일을 전혀 사용하지 않을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-175">In .NET 4, you can even decide to not have a configuration file at all.</span></span>

- <span data-ttu-id="85fde-176">기존의 WCF 서비스 집합은 구성 및 유지 관리가 매우 어려웠습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-176">An existing set of WCF services are very difficult to configure and maintain.</span></span> <span data-ttu-id="85fde-177">구성 파일에는 수천 줄의 XML 코드가 있으며 수정하는 것이 매우 위험합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-177">The configuration file has thousands of lines of XML code that are extremely dangerous to touch.</span></span> <span data-ttu-id="85fde-178">관리하기 쉽도록 코드 양을 줄이기 위한 도움이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-178">Help is needed to reduce that amount of code to something more manageable.</span></span>

## <a name="data-contract-resolver"></a><span data-ttu-id="85fde-179">데이터 계약 확인자</span><span class="sxs-lookup"><span data-stu-id="85fde-179">Data Contract Resolver</span></span>

<span data-ttu-id="85fde-180">.NET 3.5의 알려진 형식 디자인에는 몇 가지 제한이 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-180">In .NET 3.5, there were a few limitations in the design of known types:</span></span>

- <span data-ttu-id="85fde-181">serialization 및 deserialization 중에 알려진 형식을 동적으로 추가할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-181">Adding known types dynamically, during serialization or deserialization, was not possible.</span></span>

- <span data-ttu-id="85fde-182">직렬 변환기에서 알 수 없는 xsi:type 정보를 처리할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-182">Serializers could not deal with unknown xsi:type information.</span></span>

- <span data-ttu-id="85fde-183">사용자가 회선의 serialization 인스턴스 크기를 더 작게 만들기 위해 회선에 표시할 xsi:type을 지정할 수 없었습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-183">It was not possible for users to specify what xsi:type they would like to have appear on the wire to, for instance, make the size of a serialization instance on the wire smaller.</span></span>

<span data-ttu-id="85fde-184">[DataContractResolver](../wcf/samples/datacontractresolver.md) 는 .net 4.5에서 이러한 문제를 해결 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-184">The [DataContractResolver](../wcf/samples/datacontractresolver.md) solves these issues in .NET 4.5.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-185">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-185">Getting Started</span></span>

- [<span data-ttu-id="85fde-186">데이터 계약 확인자 API 설명서</span><span class="sxs-lookup"><span data-stu-id="85fde-186">Data Contract Resolver API documentation</span></span>](xref:System.Runtime.Serialization.DataContractResolver)

- [<span data-ttu-id="85fde-187">데이터 계약 확인자 소개</span><span class="sxs-lookup"><span data-stu-id="85fde-187">Introducing the Data Contract Resolver</span></span>](https://docs.microsoft.com/archive/blogs/youssefm/configuring-known-types-dynamically-introducing-the-datacontractresolver)

- <span data-ttu-id="85fde-188">샘플:</span><span class="sxs-lookup"><span data-stu-id="85fde-188">Samples:</span></span>

  - [<span data-ttu-id="85fde-189">DataContractResolver</span><span class="sxs-lookup"><span data-stu-id="85fde-189">DataContractResolver</span></span>](../wcf/samples/datacontractresolver.md)

  - [<span data-ttu-id="85fde-190">KnownAssemblyAttribute</span><span class="sxs-lookup"><span data-stu-id="85fde-190">KnownAssemblyAttribute</span></span>](../wcf/samples/knownassemblyattribute.md)

### <a name="data-contract-resolver-scenarios"></a><span data-ttu-id="85fde-191">데이터 계약 확인자 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-191">Data Contract Resolver Scenarios</span></span>

- <span data-ttu-id="85fde-192">서비스에서 수십 개의 <xref:System.Runtime.Serialization.KnownTypeAttribute> 개체를 선언할 필요가 없도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-192">Avoiding having to declare tens of <xref:System.Runtime.Serialization.KnownTypeAttribute> objects in a service.</span></span>

- <span data-ttu-id="85fde-193">XML blob의 크기를 줄입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-193">Reducing the size of the XML blob.</span></span>

## <a name="flowchart"></a><span data-ttu-id="85fde-194">Flowchart</span><span class="sxs-lookup"><span data-stu-id="85fde-194">Flowchart</span></span>

<span data-ttu-id="85fde-195">순서도는 도메인 문제를 시각적으로 나타내는 잘 알려진 패러다임입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-195">Flowchart is a well-known paradigm to visually represent domain problems.</span></span> <span data-ttu-id="85fde-196">.NET 4에서 도입 하는 새로운 제어 흐름 스타일입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-196">It is a new control flow style we're introducing in .NET 4.</span></span> <span data-ttu-id="85fde-197">순서도의 핵심 특성은 주어진 시간에 항상 작업 한 개만 실행된다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-197">A core characteristic of Flowchart is that only one activity is executed at any given time.</span></span> <span data-ttu-id="85fde-198">순서도는 루프 및 대체 결과를 표현할 수 있지만 여러 노드의 동시 실행은 기본적으로 표현할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-198">Flowcharts can express loops and alternative outcomes, but cannot natively express concurrent execution of multiple nodes.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-199">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-199">Getting Started</span></span>

- <span data-ttu-id="85fde-200">Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-200">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="85fde-201">워크플로 디자이너에서 순서도를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-201">Add a Flowchart in the workflow designer.</span></span>

- <span data-ttu-id="85fde-202">순서도 기능은 다음 클래스를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-202">The flowchart feature uses the following classes:</span></span>

  - <xref:System.Activities.Statements.Flowchart>

  - <xref:System.Activities.Statements.FlowNode>

  - <xref:System.Activities.Statements.FlowDecision>

  - <xref:System.Activities.Statements.FlowStep>

  - <xref:System.Activities.Statements.FlowSwitch%601>

- <span data-ttu-id="85fde-203">샘플:</span><span class="sxs-lookup"><span data-stu-id="85fde-203">Samples:</span></span>

  - [<span data-ttu-id="85fde-204">Flowchart 활동에서 TryCatch를 사용하여 오류 처리</span><span class="sxs-lookup"><span data-stu-id="85fde-204">Fault Handling in a Flowchart Activity Using TryCatch</span></span>](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)

  - [<span data-ttu-id="85fde-205">채용 프로세스</span><span class="sxs-lookup"><span data-stu-id="85fde-205">Hiring Process</span></span>](./samples/hiring-process.md)

- <span data-ttu-id="85fde-206">디자이너 설명서:</span><span class="sxs-lookup"><span data-stu-id="85fde-206">Designer Documentation:</span></span>

  - [<span data-ttu-id="85fde-207">Flowchart 활동 디자이너</span><span class="sxs-lookup"><span data-stu-id="85fde-207">Flowchart Activity Designers</span></span>](/visualstudio/workflow-designer/flowchart-activity-designers)

### <a name="flowchart-scenarios"></a><span data-ttu-id="85fde-208">순서도 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-208">Flowchart Scenarios</span></span>

<span data-ttu-id="85fde-209">순서도 작업을 사용하여 추측 게임을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-209">A flowchart activity can be used to implement a guessing game.</span></span> <span data-ttu-id="85fde-210">추측 게임은 매우 단순합니다. 컴퓨터가 임의 숫자를 선택하고 플레이어가 해당 숫자를 추측해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-210">The guessing game is very simple: the computer selects a random number and the player has to guess that number.</span></span> <span data-ttu-id="85fde-211">플레이어가 각 추측을 제출 하면 컴퓨터에서 힌트 (예: "적은 수로 시도")를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-211">When the player submits each guess, the computer shows them a hint (i.e. "try a lower number").</span></span> <span data-ttu-id="85fde-212">플레이어가 7 회 미만의 시도에서 숫자를 찾으면 컴퓨터에서 특수 한 축 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-212">If the player finds the number in less than 7 attempts, they receive a special congratulation from the computer.</span></span> <span data-ttu-id="85fde-213">다음 절차 작업의 조합을 통해 이 게임을 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-213">This game can be implemented with a combination of the following procedural activities:</span></span>

- <xref:System.Activities.Statements.Sequence>

- <xref:System.Activities.Statements.While>

- <xref:System.Activities.Statements.Switch%601>

- <xref:System.Activities.Statements.TryCatch>

- <xref:System.Activities.Statements.Assign%601>

- <xref:System.Activities.Statements.If>

## <a name="procedural-activities-sequence-if-foreach-switch-assign-dowhile-while"></a><span data-ttu-id="85fde-214">절차 작업(Sequence, If, ForEach, Switch, Assign, DoWhile, While)</span><span class="sxs-lookup"><span data-stu-id="85fde-214">Procedural activities (Sequence, If, ForEach, Switch, Assign, DoWhile, While)</span></span>

<span data-ttu-id="85fde-215">절차 작업은 프로그래머에게 익숙한 개념을 사용하여 순차 제어 흐름을 모델링하는 메커니즘을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-215">Procedural activities provide a mechanism to model sequential control flow using concepts that are familiar to programmers.</span></span> <span data-ttu-id="85fde-216">이러한 활동은 일반적으로 구조화 된 프로그래밍 언어 구문을 사용 하며, 해당 하는 경우 c # 및 Visual Basic 같은 일반적인 절차 언어와 언어 패리티를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-216">These activities enable traditionally structured programming language constructs and, when appropriate, provide language parity with common procedural languages such as C# and Visual Basic.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-217">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-217">Getting Started</span></span>

- <span data-ttu-id="85fde-218">Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-218">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="85fde-219">Workflow Designer에서 절차 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-219">Add procedural activities in the workflow designer.</span></span>

- <span data-ttu-id="85fde-220">샘플:</span><span class="sxs-lookup"><span data-stu-id="85fde-220">Samples:</span></span>

  - [<span data-ttu-id="85fde-221">채용 프로세스</span><span class="sxs-lookup"><span data-stu-id="85fde-221">Hiring Process</span></span>](./samples/hiring-process.md)

  - [<span data-ttu-id="85fde-222">기업 구매 프로세스</span><span class="sxs-lookup"><span data-stu-id="85fde-222">Corporate Purchase Process</span></span>](./samples/corporate-purchase-process.md)

- <span data-ttu-id="85fde-223">디자이너 설명서:</span><span class="sxs-lookup"><span data-stu-id="85fde-223">Designer Documentation:</span></span>

  - [<span data-ttu-id="85fde-224">Parallel 활동 디자이너</span><span class="sxs-lookup"><span data-stu-id="85fde-224">Parallel Activity Designer</span></span>](/visualstudio/workflow-designer/parallel-activity-designer)

  - [<span data-ttu-id="85fde-225">ParallelForEach \< T> Activity Designer</span><span class="sxs-lookup"><span data-stu-id="85fde-225">ParallelForEach\<T> Activity Designer</span></span>](/visualstudio/workflow-designer/parallelforeach-t-activity-designer)

### <a name="procedural-activity-scenarios"></a><span data-ttu-id="85fde-226">절차 작업 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-226">Procedural Activity Scenarios</span></span>

- <span data-ttu-id="85fde-227"><xref:System.Activities.Statements.Parallel>: 인트라넷 문서 관리 시스템에 문서 승인 워크플로가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-227"><xref:System.Activities.Statements.Parallel>: An intranet document management system has a document approval workflow.</span></span> <span data-ttu-id="85fde-228">여러 부서의 사용자가 문서를 승인해야 인트라넷에 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-228">Documents need to be approved by people in several departments before they can be published to the intranet.</span></span> <span data-ttu-id="85fde-229">승인에 대해 설정 된 순서는 없습니다. 문서는 "승인 보류 중" 단계에 있는 동안 언제 든 지 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-229">There isn't an established order for the approvals; they can occur at any time while the document is in the "approval pending" phase.</span></span> <span data-ttu-id="85fde-230">사용자가 검토를 위해 문서를 제출 하면 해당 문서는 직접 관리자, 인트라넷 관리자 및 내부 통신 관리자에 의해 승인 되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-230">When a user submits a document for review, it must be approved by their direct manager, the intranet administrator, and the internal communications manager.</span></span>

- <span data-ttu-id="85fde-231"><xref:System.Activities.Statements.ParallelForEach%601>: WF 애플리케이션이 대기업 내의 회사 구매를 관리합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-231"><xref:System.Activities.Statements.ParallelForEach%601>: A WF application manages corporate buys within a large company.</span></span> <span data-ttu-id="85fde-232">회사 규칙은 모든 구매 작업을 계획하기 전에 3개 공급업체를 평가하도록 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-232">The corporate rules dictate that before planning any purchase operation, the valuations of three different vendors is required.</span></span> <span data-ttu-id="85fde-233">구매 부서의 직원은 회사의 공급 업체 목록에서 세 공급 업체를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-233">An employee from the buying department selects three vendors from the company's vendor list.</span></span> <span data-ttu-id="85fde-234">공급업체를 선택하고 알린 후 회사는 합리적 제안서를 기다립니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-234">After these vendors have been selected and notified, the company will wait for their economic proposals.</span></span> <span data-ttu-id="85fde-235">제안서는 임의 순서로 도착할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-235">The proposals can come in any order.</span></span> <span data-ttu-id="85fde-236">WF에서 이 시나리오를 구현하기 위해 공급업체 컬렉션을 반복하고 합리적 제안서를 요청하는 <xref:System.Activities.Statements.ParallelForEach%601>를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-236">To implement this scenario in WF, we use a <xref:System.Activities.Statements.ParallelForEach%601> that will iterate through our collection of vendors and ask for their economic proposals.</span></span> <span data-ttu-id="85fde-237">모든 제안이 수집된 후 최상의 제안이 선택되고 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-237">After all offers are gathered, the best one is selected and displayed.</span></span>

## <a name="invokemethod"></a><span data-ttu-id="85fde-238">InvokeMethod</span><span class="sxs-lookup"><span data-stu-id="85fde-238">InvokeMethod</span></span>

<span data-ttu-id="85fde-239"><xref:System.Activities.Statements.InvokeMethod> 작업을 사용하면 범위 내의 개체나 형식에서 공용 메서드를 호출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-239">The <xref:System.Activities.Statements.InvokeMethod> activity allows invoking public methods in objects or types in scope.</span></span> <span data-ttu-id="85fde-240">이 작업은 매개 변수(매개 변수 배열 포함)를 사용하거나 사용하지 않는 인스턴스 및 정적 메서드 호출과 제네릭 메서드 호출을 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-240">It supports invoking instance and static methods with or without parameters (including parameter arrays), and generic methods.</span></span> <span data-ttu-id="85fde-241">동기 및 비동기로 메서드를 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-241">It also allows executing method synchronously and asynchronously.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-242">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-242">Getting Started</span></span>

- <span data-ttu-id="85fde-243">Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-243">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="85fde-244">워크플로 디자이너에서 <xref:System.Activities.Statements.InvokeMethod> 작업을 추가하고 정적 및 인스턴스 메서드를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-244">Add an <xref:System.Activities.Statements.InvokeMethod> activity in the workflow designer, and configure static and instance methods on it.</span></span>

- <span data-ttu-id="85fde-245">디자이너 설명서: [InvokeMethod Activity Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="85fde-245">Designer Documentation: [InvokeMethod Activity Designer](/visualstudio/workflow-designer/invokemethod-activity-designer)</span></span>

### <a name="invokemethod-scenarios"></a><span data-ttu-id="85fde-246">InvokeMethod 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-246">InvokeMethod Scenarios</span></span>

- <span data-ttu-id="85fde-247">범위 내의 개체에서 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-247">A method in an object in scope needs to be invoked.</span></span> <span data-ttu-id="85fde-248">예를 들어, 사전에 값을 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-248">For example, a value needs to be added to a dictionary.</span></span> <span data-ttu-id="85fde-249">사전 인스턴스의 Add 메서드가 호출되고 키와 값이 제공됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-249">The Add method of the instance of the dictionary is invoked, and the key and value are provided.</span></span>

- <span data-ttu-id="85fde-250">레거시 CLR 개체에서 메서드를 호출해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-250">A method needs to be invoked on a legacy CLR object.</span></span> <span data-ttu-id="85fde-251">레거시 클래스 호출을 래핑할 사용자 지정 작업을 만드는 대신 워크플로 실행 중에 범위 내에 있는 경우 <xref:System.Activities.Statements.InvokeMethod>를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-251">Instead of creating a custom activity to wrap the call to that legacy class, if it is in scope during the workflow execution, <xref:System.Activities.Statements.InvokeMethod> can be used.</span></span>

## <a name="error-handling-activities"></a><span data-ttu-id="85fde-252">오류 처리 작업</span><span class="sxs-lookup"><span data-stu-id="85fde-252">Error handling activities</span></span>

<span data-ttu-id="85fde-253"><xref:System.Activities.Statements.TryCatch>활동은 포함 된 활동 집합을 실행 하는 동안 발생 하는 예외를 catch 하는 메커니즘을 제공 합니다 (c #의 Try/Catch 구문 및 Visual Basic).</span><span class="sxs-lookup"><span data-stu-id="85fde-253">The <xref:System.Activities.Statements.TryCatch> activity provides a mechanism for catching exceptions that occur during the execution of a set of contained activities (similar to the Try/Catch construct in C# and Visual Basic).</span></span> <span data-ttu-id="85fde-254"><xref:System.Activities.Statements.TryCatch>는 워크플로 수준에서 예외 처리를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-254"><xref:System.Activities.Statements.TryCatch> provides exception handling at the workflow level.</span></span> <span data-ttu-id="85fde-255">처리 되지 않은 예외가 throw 되 면 워크플로가 중단 되 고 Finally 블록이 실행 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-255">When an unhandled exception is thrown, the workflow is aborted and the Finally block won't be executed.</span></span> <span data-ttu-id="85fde-256">이 동작은 C#과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-256">This behavior is consistent with C#.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-257">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-257">Getting Started</span></span>

- <span data-ttu-id="85fde-258">Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-258">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="85fde-259">Workflow Designer에서 <xref:System.Activities.Statements.TryCatch> 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-259">Add a <xref:System.Activities.Statements.TryCatch> activity in the workflow designer.</span></span>

- <span data-ttu-id="85fde-260">샘플: [TryCatch를 사용 하 여 Flowchart 활동의 오류 처리](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)</span><span class="sxs-lookup"><span data-stu-id="85fde-260">Sample: [Fault Handling in a Flowchart Activity Using TryCatch](./samples/fault-handling-in-a-flowchart-activity-using-trycatch.md)</span></span>

- <span data-ttu-id="85fde-261">디자이너 설명서: [오류 처리 활동 디자이너](/visualstudio/workflow-designer/error-handling-activity-designers)</span><span class="sxs-lookup"><span data-stu-id="85fde-261">Designer Documentation: [Error Handling Activity Designers](/visualstudio/workflow-designer/error-handling-activity-designers)</span></span>

### <a name="error-handling-scenarios"></a><span data-ttu-id="85fde-262">오류 처리 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-262">Error handling scenarios</span></span>

<span data-ttu-id="85fde-263">일련의 작업을 실행해야 하며, 오류가 발생할 경우 특정 논리를 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-263">A set of activities needs to be executed, and specific logic needs to be executed when an error occurs.</span></span> <span data-ttu-id="85fde-264">오류 처리 논리 중에 오류를 복구할 수 없다는 것이 발견되면 예외가 다시 throw되고 부모 작업(또는 호스트)이 문제를 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-264">If during that error handling logic it is found that the error is not recoverable, the exception will be rethrown, and the parent activity (or the host) will deal with the problem.</span></span>

## <a name="pick-activity"></a><span data-ttu-id="85fde-265">Pick 작업</span><span class="sxs-lookup"><span data-stu-id="85fde-265">Pick activity</span></span>

<span data-ttu-id="85fde-266"><xref:System.Activities.Statements.Pick> 작업은 WF에서 이벤트 기반 제어 흐름 모델링을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-266">The <xref:System.Activities.Statements.Pick> Activity provides event-based control flow modeling in WF.</span></span> <span data-ttu-id="85fde-267"><xref:System.Activities.Statements.Pick>에는 각 분기가 실행되기 전에 특정 이벤트의 발생을 기다리는 많은 분기가 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-267"><xref:System.Activities.Statements.Pick> contains many branches where each branch waits for a particular event to occur before running.</span></span> <span data-ttu-id="85fde-268">이 설치에서 <xref:System.Activities.Statements.Pick>은 작업이 수신 대기 중인 이벤트 집합 중 하나만 실행하는 <xref:System.Activities.Statements.Switch%601>와 유사하게 동작합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-268">In this setup, a <xref:System.Activities.Statements.Pick> behaves similar to a <xref:System.Activities.Statements.Switch%601> to which the Activity will execute only one of the set of events it is listening.</span></span> <span data-ttu-id="85fde-269">각 분기는 이벤트 구동 방식이며 처음 발생하는 이벤트는 해당 분기를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-269">Each branch is event driven and the event that occurs runs the corresponding branch first.</span></span> <span data-ttu-id="85fde-270">다른 분기는 모두 이벤트 수신 대기를 취소하고 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-270">All other branches cancel and stop listening for events.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-271">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-271">Getting Started</span></span>

- <span data-ttu-id="85fde-272">Visual Studio 2012에서 워크플로 콘솔 응용 프로그램을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-272">In Visual Studio 2012, create a workflow console application.</span></span> <span data-ttu-id="85fde-273">Workflow Designer에서 <xref:System.Activities.Statements.Pick> 작업을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-273">Add a <xref:System.Activities.Statements.Pick> activity in the workflow designer.</span></span>

- <span data-ttu-id="85fde-274">샘플: [Pick 활동 사용](./samples/using-the-pick-activity.md)</span><span class="sxs-lookup"><span data-stu-id="85fde-274">Sample: [Using the Pick Activity](./samples/using-the-pick-activity.md)</span></span>

- <span data-ttu-id="85fde-275">디자이너 설명서: [Pick 활동 디자이너](/visualstudio/workflow-designer/pick-activity-designer)</span><span class="sxs-lookup"><span data-stu-id="85fde-275">Designer documentation: [Pick Activity Designer](/visualstudio/workflow-designer/pick-activity-designer)</span></span>

### <a name="pick-scenario"></a><span data-ttu-id="85fde-276">Pick 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-276">Pick Scenario</span></span>

<span data-ttu-id="85fde-277">사용자에게 입력을 요청하는 메시지를 표시해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-277">A user needs to be prompted for input.</span></span> <span data-ttu-id="85fde-278">정상적인 상황에서 개발자는와 같은 메서드 호출을 사용 <xref:System.Console.ReadLine%2A> 하 여 사용자 입력을 묻는 메시지를 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-278">Under normal circumstances, the developer would use a method call like <xref:System.Console.ReadLine%2A> to prompt for a user's input.</span></span> <span data-ttu-id="85fde-279">이 설치와 관련된 문제는 사용자가 입력할 때까지 프로그램이 기다린다는 것입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-279">The problem with this setup is that the program waits until the user enters something.</span></span> <span data-ttu-id="85fde-280">이 시나리오에서는 차단 작업의 차단을 해제하기 위해 시간 제한이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-280">In this scenario, a time-out is needed to unblock a blocking activity.</span></span> <span data-ttu-id="85fde-281">일반적인 시나리오에서는 지정된 기간 내에 작업을 완료해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-281">A common scenario is one that requires a task to be completed within a given time duration.</span></span> <span data-ttu-id="85fde-282">차단 작업 시간 초과는 Pick에서 많은 값을 추가하는 시나리오입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-282">Timing out a blocking activity is a scenario where Pick adds a lot of value.</span></span>

## <a name="wcf-routing-service"></a><span data-ttu-id="85fde-283">WCF 라우팅 서비스</span><span class="sxs-lookup"><span data-stu-id="85fde-283">WCF Routing Service</span></span>

<span data-ttu-id="85fde-284">라우팅 서비스는 클라이언트와 서비스 간에 WCF 메시지가 전달 되는 방식을 제어할 수 있는 일반 소프트웨어 라우터로 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-284">The Routing Service is designed to be a generic software Router that allows you to control how WCF messages flow in between your clients and services.</span></span> <span data-ttu-id="85fde-285">라우팅 서비스를 사용 하면 서비스에서 클라이언트를 분리할 수 있습니다. 그러면 지원할 수 있는 구성과 서비스를 호스트 하는 방법을 고려할 때 유연성을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-285">The Routing Service allows you to decouple your clients from your services, which gives you much more freedom in terms of the configurations that you can support and the flexibility you have when considering how to host your services.</span></span> <span data-ttu-id="85fde-286">.NET 3.5에서 클라이언트와 서비스는 긴밀 하 게 결합 되어 있습니다. 클라이언트는 통신 하는 데 필요한 모든 서비스와 해당 위치에 대해 알고 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-286">In .NET 3.5, clients and services were tightly coupled; a client had to know about all of the services it needed to talk to and where they were located.</span></span> <span data-ttu-id="85fde-287">또한 .NET Framework 3.5의 WCF에는 다음과 같은 제한 사항이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-287">In addition, WCF in .NET Framework 3.5 had the following limitations:</span></span>

- <span data-ttu-id="85fde-288">이 논리를 클라이언트 프로그램에 하드 코딩해야 했으므로 오류 처리가 복잡했습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-288">Error handling was complex, as this logic had to be hard-coded into the client.</span></span>

- <span data-ttu-id="85fde-289">클라이언트와 서비스에서 항상 동일한 바인딩을 사용해야 했습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-289">Clients and services had to always use the same bindings.</span></span>

- <span data-ttu-id="85fde-290">서비스가 제대로 팩터링되지 않았습니다. 클라이언트가 여러 서비스 중에서 선택하는 대신 모든 기능을 구현하는 서비스 하나에 통신하도록 하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-290">Services were rarely well factored: it is easier to have the client talk to one service which implements everything, rather than needing to choose between multiple services.</span></span>

<span data-ttu-id="85fde-291">.NET 4의 라우팅 서비스는 이러한 문제를 보다 쉽게 해결할 수 있도록 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-291">The routing service in .NET 4 is designed to make these problems easier to solve.</span></span> <span data-ttu-id="85fde-292">새 라우팅 서비스에는 다음과 같은 기능이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-292">The new routing service has the following features:</span></span>

1. <span data-ttu-id="85fde-293">콘텐츠 기반 라우팅(<xref:System.ServiceModel.Dispatcher.MessageFilter> 개체가 메시지를 검사하여 보낼 위치를 결정함)</span><span class="sxs-lookup"><span data-stu-id="85fde-293">Content based routing (<xref:System.ServiceModel.Dispatcher.MessageFilter> objects examine a message to determine where it should be sent.)</span></span>

2. <span data-ttu-id="85fde-294">프로토콜 브리징 (전송 & 메시지)</span><span class="sxs-lookup"><span data-stu-id="85fde-294">Protocol bridging (transport & message)</span></span>

3. <span data-ttu-id="85fde-295">오류 처리(라우터가 통신 예외를 catch하고 백업 엔드포인트로 장애 조치됨)</span><span class="sxs-lookup"><span data-stu-id="85fde-295">Error handling (the router catches communication exceptions and fails over to backup endpoints)</span></span>

4. <span data-ttu-id="85fde-296"><xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> 및 라우팅 구성의 동적(메모리 내) 업데이트</span><span class="sxs-lookup"><span data-stu-id="85fde-296">Dynamic (in memory) update of <xref:System.ServiceModel.Dispatcher.MessageFilterTable%601> and Routing Configuration.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-297">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-297">Getting Started</span></span>

1. <span data-ttu-id="85fde-298">설명서: [라우팅](../wcf/feature-details/routing.md)</span><span class="sxs-lookup"><span data-stu-id="85fde-298">Documentation: [Routing](../wcf/feature-details/routing.md)</span></span>

2. <span data-ttu-id="85fde-299">샘플: [라우팅 서비스 &#91;WCF 샘플&#93;](../wcf/samples/routing-services.md)</span><span class="sxs-lookup"><span data-stu-id="85fde-299">Samples: [Routing Services &#91;WCF Samples&#93;](../wcf/samples/routing-services.md)</span></span>

3. <span data-ttu-id="85fde-300">블로그: [라우팅 규칙](https://docs.microsoft.com/archive/blogs/RoutingRules/)</span><span class="sxs-lookup"><span data-stu-id="85fde-300">Blog: [Routing Rules!](https://docs.microsoft.com/archive/blogs/RoutingRules/)</span></span>

### <a name="routing-scenarios"></a><span data-ttu-id="85fde-301">라우팅 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-301">Routing Scenarios</span></span>

<span data-ttu-id="85fde-302">라우팅 서비스는 다음과 같은 시나리오에서 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-302">The routing service is useful in the following scenarios:</span></span>

- <span data-ttu-id="85fde-303">클라이언트가 직접 주소를 모두 지정하지 않고 여러 서비스에 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-303">Clients can talk to multiple services without having to address them all directly.</span></span>

- <span data-ttu-id="85fde-304">클라이언트가 클라이언트 요청에서 추가 논리를 수행하여 라우팅 위치를 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-304">Clients can perform additional logic on a client request to determine where to route it</span></span>

- <span data-ttu-id="85fde-305">클라이언트를 리팩터링하지 않고 클라이언트가 수행하는 작업을 여러 서비스 구현으로 분해합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-305">Decompose the operations a client performs into multiple service implementations without refactoring the client.</span></span>

- <span data-ttu-id="85fde-306">클라이언트와 서비스가 서로 다른 보안 설정으로 서로 다른 바인딩을 통신할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-306">Clients and services can speak different bindings with different security settings.</span></span>

- <span data-ttu-id="85fde-307">클라이언트가 서비스를 사용할 수 없는 경우나 오류에 대해 보다 강력하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-307">Clients can be enabled to be more robust against failure or the unavailability of services.</span></span>

## <a name="wcf-discovery"></a><span data-ttu-id="85fde-308">WCF 검색</span><span class="sxs-lookup"><span data-stu-id="85fde-308">WCF Discovery</span></span>

<span data-ttu-id="85fde-309">WCF Discovery는 응용 프로그램 인프라에 검색 메커니즘을 통합 하는 데 사용할 수 있는 프레임 워크 기술입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-309">WCF Discovery is a framework technology that allows you to incorporate a discovery mechanism to your application infrastructure.</span></span> <span data-ttu-id="85fde-310">이 기술을 사용하여 서비스를 검색 가능하게 만들고 서비스를 검색하도록 클라이언트를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-310">You can use this to make your service discoverable, and configure your clients to search for services.</span></span> <span data-ttu-id="85fde-311">엔드포인트를 사용하여 클라이언트를 더 이상 하드 코딩할 필요가 없으므로 애플리케이션의 견고성과 내결함성이 강화됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-311">Clients no longer need to be hard coded with endpoint, making your application more robust and fault tolerant.</span></span> <span data-ttu-id="85fde-312">Discovery는 자동 구성 기능을 애플리케이션에 빌드하는 완벽한 플랫폼입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-312">Discovery is the perfect platform to build auto-configuration capabilities into your application.</span></span>

<span data-ttu-id="85fde-313">이 제품은 WS-Discovery 표준을 기반으로 하며</span><span class="sxs-lookup"><span data-stu-id="85fde-313">The product is built on top of the WS-Discovery standard.</span></span> <span data-ttu-id="85fde-314">상호 운용 가능 하 고 확장 가능 하며 제네릭으로 설계 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-314">It's designed to be interoperable, extensible, and generic.</span></span> <span data-ttu-id="85fde-315">이 제품에서는 다음 두 가지 작업 모드가 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-315">The product supports two modes of operation:</span></span>

1. <span data-ttu-id="85fde-316">관리: 네트워크에 기존 서비스에 대해 알고 있는 엔터티가 있는 경우 클라이언트가 직접 정보를 쿼리합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-316">Managed: where there is an entity on the network knowledgeable about existing services, clients query it directly for information.</span></span> <span data-ttu-id="85fde-317">이것은 Active Directory와 유사합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-317">This is analogous to Active Directory.</span></span>

2. <span data-ttu-id="85fde-318">임시: 클라이언트가 멀티캐스트 메시지를 사용하여 서비스를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-318">Ad-hoc: where clients use multicast messages to locate services.</span></span>

<span data-ttu-id="85fde-319">또한 검색 메시지는 네트워크 프로토콜에 관계없이 작동하므로 모드 요구 사항을 지원하는 모든 프로토콜에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-319">Furthermore, discovery messages are network protocol agnostic; you can use them on top any protocol that supports the mode requirements.</span></span> <span data-ttu-id="85fde-320">예를 들어 UDP 채널 또는 멀티 캐스트 메시징을 지 원하는 다른 네트워크를 통해 검색 멀티 캐스트 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-320">For example, discovery multicast messages can be sent over the UDP channel or any other network that supports multicast messaging.</span></span> <span data-ttu-id="85fde-321">기능 유연성과 결합 된 이러한 디자인 요소를 사용 하면 솔루션에 맞게 검색을 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-321">These design points, combined with feature flexibility, allow you to adapt the discovery specifically to your solution.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-322">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-322">Getting Started</span></span>

- <span data-ttu-id="85fde-323">설명서: [WCF 검색](../wcf/feature-details/wcf-discovery.md)</span><span class="sxs-lookup"><span data-stu-id="85fde-323">Documentation: [WCF Discovery](../wcf/feature-details/wcf-discovery.md)</span></span>

- <span data-ttu-id="85fde-324">샘플: [검색 (샘플)](../wcf/samples/discovery-samples.md)</span><span class="sxs-lookup"><span data-stu-id="85fde-324">Samples: [Discovery (Samples)](../wcf/samples/discovery-samples.md)</span></span>

### <a name="discovery-scenarios"></a><span data-ttu-id="85fde-325">Discovery 시나리오</span><span class="sxs-lookup"><span data-stu-id="85fde-325">Discovery Scenarios</span></span>

<span data-ttu-id="85fde-326">서비스를 사용할 수 있게 될 시기를 알 수 없기 때문에 개발자가 엔드포인트를 하드 코딩하는 대신</span><span class="sxs-lookup"><span data-stu-id="85fde-326">A developer doesn't want to hard code endpoints, since it is unknown when my service will be available.</span></span> <span data-ttu-id="85fde-327">런타임에 서비스를 선택하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-327">Instead, the developer wants to choose a service at runtime.</span></span> <span data-ttu-id="85fde-328">애플리케이션 구성 요소 간에 분리, 견고성 및 자동 구성이 더 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-328">More decoupling, robustness, and auto-configuration is needed between the components in the application.</span></span>

## <a name="tracking"></a><span data-ttu-id="85fde-329">추적</span><span class="sxs-lookup"><span data-stu-id="85fde-329">Tracking</span></span>

<span data-ttu-id="85fde-330">워크플로 추적을 통해 워크플로 인스턴스 실행에 대 한 통찰력을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-330">Workflow tracking provides insight into the execution of a workflow instance.</span></span> <span data-ttu-id="85fde-331">워크플로 인스턴스 수준에서 워크플로 및 워크플로 내의 활동이 실행 될 때 추적 이벤트를 내보냅니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-331">The tracking events are emitted from a workflow at the workflow instance level and when activities within the workflow execute.</span></span> <span data-ttu-id="85fde-332">추적 레코드를 구독하려면 워크플로 추적 참가자를 워크플로 호스트에 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-332">A workflow tracking participant needs to be added to the workflow host to subscribe to tracking records.</span></span> <span data-ttu-id="85fde-333">추적 레코드는 추적 프로필을 사용하여 필터링됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-333">The tracking records are filtered using a tracking profile.</span></span> <span data-ttu-id="85fde-334">.NET Framework는 ETW (ETW(Windows용 이벤트 추적)) 추적 참가자를 제공 하며, 기본 프로필은 machine.config 파일에 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-334">The .NET Framework provides an ETW (Event Tracing for Windows) tracking participant, and a basic profile is installed in the machine.config file.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-335">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-335">Getting Started</span></span>

1. <span data-ttu-id="85fde-336">Visual Studio 2010에서 WCF 워크플로 서비스 애플리케이션 프로젝트를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-336">In Visual Studio 2010, create a WCF Workflow Service Application project.</span></span> <span data-ttu-id="85fde-337">먼저 <xref:System.ServiceModel.Activities.Receive> 및 <xref:System.ServiceModel.Activities.SendReply> 쌍이 캔버스에 배치됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-337">A <xref:System.ServiceModel.Activities.Receive> and <xref:System.ServiceModel.Activities.SendReply> pair will be placed on your canvas to start.</span></span>

2. <span data-ttu-id="85fde-338">web.config를 열고 프로필 없이 ETW 추적 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-338">Open the web.config and add an ETW tracking behavior with no profile.</span></span>

    1. <span data-ttu-id="85fde-339">기본 프로필이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-339">The default profile is used.</span></span>

    2. <span data-ttu-id="85fde-340">이벤트 뷰어를 열고 **이벤트 뷰어**, **응용 프로그램 및 서비스 로그**, **Microsoft**, **Windows**, **응용 프로그램 서버-응용**프로그램 노드에서 분석 채널을 사용 하도록 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-340">Open event viewer and enable the analytic channel in the following node: **Event Viewer**, **Applications and Services Logs**, **Microsoft**, **Windows**, **Application Server-Applications**.</span></span> <span data-ttu-id="85fde-341">**분석** 을 마우스 오른쪽 단추로 클릭 하 고 **로그 사용**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-341">Right-click **Analytic** and select **Enable Log**.</span></span>

    3. <span data-ttu-id="85fde-342">워크플로 서비스를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-342">Run the workflow service.</span></span>

    4. <span data-ttu-id="85fde-343">이벤트 뷰어에서 워크플로 추적 이벤트를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-343">Observe the workflow tracking events in event viewer.</span></span>

3. <span data-ttu-id="85fde-344">샘플: [추적](./samples/tracking.md)</span><span class="sxs-lookup"><span data-stu-id="85fde-344">Samples: [Tracking](./samples/tracking.md)</span></span>

4. <span data-ttu-id="85fde-345">개념 설명서: [워크플로 추적 및 추적](workflow-tracking-and-tracing.md)</span><span class="sxs-lookup"><span data-stu-id="85fde-345">Conceptual documentation: [Workflow Tracking and Tracing](workflow-tracking-and-tracing.md)</span></span>

## <a name="sql-workflow-instance-store"></a><span data-ttu-id="85fde-346">SQL 워크플로 인스턴스 저장소</span><span class="sxs-lookup"><span data-stu-id="85fde-346">SQL Workflow Instance Store</span></span>

<span data-ttu-id="85fde-347"><xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore>는 인스턴스 저장소의 SQL Server 기반 구현입니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-347">The <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> is a SQL Server-based implementation of an instance store.</span></span> <span data-ttu-id="85fde-348">인스턴스 저장소는 해당 인스턴스를 로드하고 다시 시작하는 데 필요한 모든 데이터와 함께 실행 중인 인스턴스의 상태를 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-348">An instance store stores the state of a running instance together with all data necessary to load and resume that instance.</span></span> <span data-ttu-id="85fde-349">서비스 호스트는 워크플로가 유지되는 경우 인스턴스 상태를 저장하도록 인스턴스 저장소에 지시하고, 해당 인스턴스에 대한 메시지가 도착하거나 지연 작업이 만료되면 인스턴스 상태를 로드하도록 인스턴스 저장소에 지시합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-349">The service host instructs the instance store to save the instance state if the workflow persists, and it instructs the instance store to load the instance state when a message arrives for that instance or a delay activity expires.</span></span>

### <a name="getting-started"></a><span data-ttu-id="85fde-350">시작하기</span><span class="sxs-lookup"><span data-stu-id="85fde-350">Getting Started</span></span>

1. <span data-ttu-id="85fde-351">Visual Studio 2012에서 암시적 또는 명시적 작업을 포함 하는 워크플로를 만듭니다 <xref:System.Activities.Statements.Persist> .</span><span class="sxs-lookup"><span data-stu-id="85fde-351">In Visual Studio 2012, create a Workflow that contains an implicit or explicit <xref:System.Activities.Statements.Persist> activity.</span></span> <span data-ttu-id="85fde-352">워크플로 서비스 호스트에 <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> 동작을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-352">Add the <xref:System.Activities.DurableInstancing.SqlWorkflowInstanceStore> behavior to your workflow service host.</span></span> <span data-ttu-id="85fde-353">이 작업은 코드나 애플리케이션 구성 파일에서 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="85fde-353">This can be done in code or in the application configuration file.</span></span>

2. <span data-ttu-id="85fde-354">샘플: [지 속성](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))</span><span class="sxs-lookup"><span data-stu-id="85fde-354">Samples: [Persistence](/previous-versions/dotnet/netframework-4.0/dd699769(v%3dvs.100))</span></span>

3. <span data-ttu-id="85fde-355">개념 설명서: [SQL 워크플로 인스턴스 저장소](sql-workflow-instance-store.md).</span><span class="sxs-lookup"><span data-stu-id="85fde-355">Conceptual documentation: [SQL Workflow Instance Store](sql-workflow-instance-store.md).</span></span>
