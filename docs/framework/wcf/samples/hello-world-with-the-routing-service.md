---
description: '다음에 대 한 자세한 정보: 라우팅 서비스와 헬로 월드'
title: Hello World 라우팅 서비스
ms.date: 03/30/2017
ms.assetid: 0f4b0d5b-6522-4ad5-9f3a-baa78316d7d1
ms.openlocfilehash: 1741c7d1f1e474864d66220fd160633997744876
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99631972"
---
# <a name="hello-world-with-the-routing-service"></a><span data-ttu-id="bfbb0-103">Hello World 라우팅 서비스</span><span class="sxs-lookup"><span data-stu-id="bfbb0-103">Hello World with the Routing Service</span></span>

<span data-ttu-id="bfbb0-104">이 샘플에서는 WCF (Windows Communication Foundation) 라우팅 서비스를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-104">This sample demonstrates the Windows Communication Foundation (WCF) Routing Service.</span></span> <span data-ttu-id="bfbb0-105">라우팅 서비스는 응용 프로그램에 콘텐츠 기반 라우터를 쉽게 포함할 수 있도록 하는 WCF 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-105">The Routing Service is a WCF component that makes it easy to include a content-based router in your application.</span></span> <span data-ttu-id="bfbb0-106">이 샘플에서는 라우팅 서비스를 사용 하 여 통신 하도록 표준 WCF 계산기 샘플을 조정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-106">This sample adapts the standard WCF Calculator Sample to communicate using the Routing Service.</span></span> <span data-ttu-id="bfbb0-107">이 샘플에서 계산기 클라이언트는 라우터에 의해 노출된 엔드포인트로 메시지를 보내도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-107">In this sample, the Calculator client is configured to send messages to an endpoint exposed by the router.</span></span> <span data-ttu-id="bfbb0-108">라우팅 서비스는 전송된 모든 메시지를 승인하고 이를 계산기 서비스에 해당하는 엔드포인트에 전달하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-108">The Routing Service is configured to accept all messages sent to it and to forward them to an endpoint that corresponds to the Calculator service.</span></span> <span data-ttu-id="bfbb0-109">따라서 클라이언트에서 보내는 메시지는 라우터가 받아 실제 계산기 서비스로 다시 라우트합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-109">Thus messages sent from the client are received by the router and re-routed to the actual Calculator service.</span></span> <span data-ttu-id="bfbb0-110">계산기 서비스에서 보내는 메시지는 다시 라우터로 전송되고 라우터는 이를 다시 계산기 클라이언트에 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-110">Messages from the Calculator service are sent back to the router, which in turn passes them back to the Calculator client.</span></span>

### <a name="to-use-this-sample"></a><span data-ttu-id="bfbb0-111">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="bfbb0-111">To use this sample</span></span>

1. <span data-ttu-id="bfbb0-112">Visual Studio 2012을 사용 하 여 HelloRoutingService를 엽니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-112">Using Visual Studio 2012, open HelloRoutingService.sln.</span></span>

2. <span data-ttu-id="bfbb0-113">F5 또는 Ctrl+Shift+B를 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-113">Press F5 or CTRL+SHIFT+B.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bfbb0-114">F5 키를 누르면 계산기 클라이언트가 자동으로 시작됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-114">If you press F5, the Calculator Client automatically starts.</span></span> <span data-ttu-id="bfbb0-115">Ctrl+Shift+B(빌드)를 누를 경우에는 다음 애플리케이션을 직접 시작해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-115">If you press CTRL+SHIFT+B (build), you must start following applications yourself.</span></span>
    >
    > 1. <span data-ttu-id="bfbb0-116">계산기 클라이언트(./CalculatorClient/bin/client.exe)</span><span class="sxs-lookup"><span data-stu-id="bfbb0-116">Calculator client (./CalculatorClient/bin/client.exe</span></span>
    > 2. <span data-ttu-id="bfbb0-117">계산기 서비스(./CalculatorService/bin/service.exe)</span><span class="sxs-lookup"><span data-stu-id="bfbb0-117">Calculator service (./CalculatorService/bin/service.exe)</span></span>
    > 3. <span data-ttu-id="bfbb0-118">라우팅 서비스(./RoutingService/bin/RoutingService.exe)</span><span class="sxs-lookup"><span data-stu-id="bfbb0-118">Routing service (./RoutingService/bin/RoutingService.exe)</span></span>

3. <span data-ttu-id="bfbb0-119">Enter 키를 눌러 클라이언트를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-119">Press ENTER to start the client.</span></span>

     <span data-ttu-id="bfbb0-120">다음 출력이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-120">You should see the following output:</span></span>

    ```console
     Add(100,15.99) = 115.99

     Subtract(145,76.54) = 68.46

     Multiply(9,81.25) = 731.25

     Divide(22,7) = 3.14285714285714
    ```

## <a name="configurable-via-code-or-appconfig"></a><span data-ttu-id="bfbb0-121">코드 또는 App.Config를 통해 구성 가능</span><span class="sxs-lookup"><span data-stu-id="bfbb0-121">Configurable via Code or App.Config</span></span>

 <span data-ttu-id="bfbb0-122">이 샘플은 App.config 파일을 사용하여 라우터 동작을 정의하도록 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-122">The sample ships configured to use an App.config file to define the router’s behavior.</span></span> <span data-ttu-id="bfbb0-123">App.config 파일이 인식되지 않도록 이 파일의 이름을 다른 이름으로 바꾸고 ConfigureRouterViaCode() 메서드 호출의 주석 처리를 제거할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-123">You can also change the name of the App.config file to something else so that it is not recognized and uncomment the method call to ConfigureRouterViaCode().</span></span> <span data-ttu-id="bfbb0-124">어떤 방법을 사용하든 라우터 동작은 동일합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-124">Either method results in the same behavior from the router.</span></span>

### <a name="scenario"></a><span data-ttu-id="bfbb0-125">시나리오</span><span class="sxs-lookup"><span data-stu-id="bfbb0-125">Scenario</span></span>

 <span data-ttu-id="bfbb0-126">이 샘플에서는 기본 메시지 펌프 역할을 하는 라우터를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-126">This sample demonstrates the router acting as a basic message pump.</span></span> <span data-ttu-id="bfbb0-127">라우팅 서비스는 미리 구성된 대상 엔드포인트 집합에 직접 메시지를 전달하도록 구성된 투명 프록시 노드 역할을 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-127">The routing service acts as a transparent proxy node configured to pass messages directly to a preconfigured set of destination endpoints.</span></span>

### <a name="real-world-scenario"></a><span data-ttu-id="bfbb0-128">실제 시나리오</span><span class="sxs-lookup"><span data-stu-id="bfbb0-128">Real World Scenario</span></span>

 <span data-ttu-id="bfbb0-129">Contoso에서는 서비스의 명명, 주소 지정, 구성 및 보안과 관련하여 유연성을 향상시키려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-129">Contoso wants to increase the flexibility it has in the naming, addressing, configuration, and security of its services.</span></span> <span data-ttu-id="bfbb0-130">이를 위해 Contoso에서는 공개 엔드포인트 역할을 할 서비스 앞에 기본 메시지 펌프를 배치합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-130">To do this, they place a basic message pump in front of their services to act as a public facing endpoint.</span></span> <span data-ttu-id="bfbb0-131">이렇게 하면 실제 서비스 앞에 추가 보안 기능을 배치할 수 있으며 나중에 확장된 솔루션이나 서비스 버전 관리를 보다 쉽게 구현할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-131">This allows them to place additional security in front of their actual services and make it easier to implement scaled out solutions or service versioning at a later date.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="bfbb0-132">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-132">The samples may already be installed on your computer.</span></span> <span data-ttu-id="bfbb0-133">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-133">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="bfbb0-134">이 디렉터리가 없는 경우 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 샘플을 다운로드 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 합니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-134">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="bfbb0-135">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bfbb0-135">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\RoutingServices\HelloRoutingService`  
  
## <a name="see-also"></a><span data-ttu-id="bfbb0-136">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bfbb0-136">See also</span></span>

- <span data-ttu-id="bfbb0-137">[AppFabric 호스팅 및 지속성 샘플](/previous-versions/appfabric/ff383418(v=azure.10))</span><span class="sxs-lookup"><span data-stu-id="bfbb0-137">[AppFabric Hosting and Persistence Samples](/previous-versions/appfabric/ff383418(v=azure.10))</span></span>
