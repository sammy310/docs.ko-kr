---
title: 알림 샘플
ms.date: 03/30/2017
ms.assetid: 954a75e4-9a97-41d6-94fc-43765d4205a9
ms.openlocfilehash: 57b61dbd82338aafd248285c9cb11ecdf58d25bb
ms.sourcegitcommit: 5fb5b6520b06d7f5e6131ec2ad854da302a28f2e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/03/2019
ms.locfileid: "74716144"
---
# <a name="announcements-sample"></a><span data-ttu-id="6006f-102">알림 샘플</span><span class="sxs-lookup"><span data-stu-id="6006f-102">Announcements Sample</span></span>

<span data-ttu-id="6006f-103">이 샘플에서는 검색 기능의 알림 기능을 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-103">This sample shows how to use the Announcement functionality of the Discovery feature.</span></span> <span data-ttu-id="6006f-104">서비스에서는 알림을 사용하여 서비스에 대한 메타데이터가 들어 있는 알림 메시지를 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-104">Announcements allow services to send out announcement messages that contain metadata about the service.</span></span> <span data-ttu-id="6006f-105">기본적으로 서비스가 시작될 때는 Hello 알림이 보내지고 서비스가 종료될 때는 Bye 알림이 보내집니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-105">By default a hello announcement is sent when the service starts up and a bye announcement is sent when the service shuts down.</span></span> <span data-ttu-id="6006f-106">이러한 알림은 멀티캐스트하거나 지점 간에 보낼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-106">These announcements can be multicast or they can be sent point-to-point.</span></span> <span data-ttu-id="6006f-107">이 샘플은 서비스와 클라이언트에 해당하는 두 개의 프로젝트로 구성되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-107">This sample consists of two projects service and client.</span></span>

## <a name="service"></a><span data-ttu-id="6006f-108">서비스</span><span class="sxs-lookup"><span data-stu-id="6006f-108">Service</span></span>

<span data-ttu-id="6006f-109">이 프로젝트에는 자체 호스팅 계산기 서비스가 들어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-109">This project contains a self-hosted calculator service.</span></span> <span data-ttu-id="6006f-110">ph x="1" /&gt; 메서드에서는 서비스 호스트가 만들어지고 이 서비스 호스트에 서비스 엔드포인트가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-110">In the `Main` method, a service host is created and a service endpoint is added to it.</span></span> <span data-ttu-id="6006f-111">그런 다음 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>가 만들어집니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-111">Next, a <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior> is created.</span></span> <span data-ttu-id="6006f-112">알림을 사용하도록 설정하려면 <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>에 알림 엔드포인트를 추가해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-112">To enable announcements, an announcement endpoint must be added to the <xref:System.ServiceModel.Discovery.ServiceDiscoveryBehavior>.</span></span> <span data-ttu-id="6006f-113">이 경우 UDP 멀티캐스트를 사용하는 표준 엔드포인트가 알림 엔드포인트로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-113">In this case a standard endpoint, using UDP multicast is added as the announcement endpoint.</span></span> <span data-ttu-id="6006f-114">이 끝점에서는 잘 알려진 UDP 주소를 통해 알림을 브로드캐스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-114">This broadcasts the announcements over a well-known UDP address.</span></span>

```csharp
Uri baseAddress = new Uri("http://localhost:8000/" + Guid.NewGuid().ToString());

// Create a ServiceHost for the CalculatorService type.
using (ServiceHost serviceHost = new ServiceHost(typeof(CalculatorService), baseAddress))
{
     serviceHost.AddServiceEndpoint(typeof(ICalculatorService), new WSHttpBinding(), String.Empty);

     ServiceDiscoveryBehavior serviceDiscoveryBehavior = new ServiceDiscoveryBehavior();

     // Announce the availability of the service over UDP multicast
    serviceDiscoveryBehavior.AnnouncementEndpoints.Add(new UdpAnnouncementEndpoint());

    // Make the service discoverable over UDP multicast.
    serviceHost.Description.Behaviors.Add(serviceDiscoveryBehavior);
    serviceHost.AddServiceEndpoint(new UdpDiscoveryEndpoint());
    serviceHost.Open();
    // ...
}
```

## <a name="client"></a><span data-ttu-id="6006f-115">Client</span><span class="sxs-lookup"><span data-stu-id="6006f-115">Client</span></span>

<span data-ttu-id="6006f-116">이 프로젝트에서는 클라이언트가 <xref:System.ServiceModel.Discovery.AnnouncementService>를 호스팅합니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-116">In this project, note that the client hosts an <xref:System.ServiceModel.Discovery.AnnouncementService>.</span></span> <span data-ttu-id="6006f-117">또한 두 개의 대리자가 이벤트에 등록됩니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-117">Furthermore, two delegates are registered with events.</span></span> <span data-ttu-id="6006f-118">이러한 이벤트는 온라인 및 오프라인 알림을 받을 때 클라이언트에서 수행하는 작업을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-118">These events dictate what the client does when online and offline announcements are received.</span></span>

```csharp
// Create an AnnouncementService instance
AnnouncementService announcementService = new AnnouncementService();

// Subscribe the announcement events
announcementService.OnlineAnnouncementReceived += OnOnlineEvent;
announcementService.OfflineAnnouncementReceived += OnOfflineEvent;
```

<span data-ttu-id="6006f-119">`OnOnlineEvent` 및 `OnOfflineEvent` 메서드는 각각 Hello 알림과 Bye 알림을 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-119">The `OnOnlineEvent` and `OnOfflineEvent` methods handle the hello and bye announcement messages respectively.</span></span>

```csharp
static void OnOnlineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an online announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}

static void OnOfflineEvent(object sender, AnnouncementEventArgs e)
{
    Console.WriteLine();
    Console.WriteLine("Received an offline announcement from {0}:", e.AnnouncementMessage.EndpointDiscoveryMetadata.Address);
            PrintEndpointDiscoveryMetadata(e.AnnouncementMessage.EndpointDiscoveryMetadata);
}
```

#### <a name="to-use-this-sample"></a><span data-ttu-id="6006f-120">이 샘플을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="6006f-120">To use this sample</span></span>

1. <span data-ttu-id="6006f-121">이 샘플에서는 HTTP 끝점을 사용 하며이 샘플을 실행 하려면 적절 한 URL Acl을 추가 해야 합니다. 자세한 내용은 [http 및 HTTPS 구성](https://go.microsoft.com/fwlink/?LinkId=70353) 을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="6006f-121">This sample uses HTTP endpoints and to run this sample, proper URL ACLs must be added see [Configuring HTTP and HTTPS](https://go.microsoft.com/fwlink/?LinkId=70353) for details.</span></span> <span data-ttu-id="6006f-122">높은 권한으로 다음 명령을 실행하면 적절한 ACL이 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-122">Executing the following command at an elevated privilege should add the appropriate ACLs.</span></span> <span data-ttu-id="6006f-123">명령이 지정한 대로 작동하지 않는 경우 다음 인수의 도메인과 사용자 이름을 대체할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-123">You may want to substitute your Domain and Username for the following arguments if the command does not work as is.</span></span> `netsh http add urlacl url=http://+:8000/ user=%DOMAIN%\%UserName%`

2. <span data-ttu-id="6006f-124">솔루션을 빌드합니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-124">Build the solution.</span></span>

3. <span data-ttu-id="6006f-125">client.exe 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-125">Run the client.exe application.</span></span>

4. <span data-ttu-id="6006f-126">service.exe 애플리케이션을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-126">Run the service.exe application.</span></span> <span data-ttu-id="6006f-127">그러면 클라이언트에서는 온라인 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-127">Note the client receives an online announcement.</span></span>

5. <span data-ttu-id="6006f-128">service.exe 애플리케이션을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-128">Close the service.exe application.</span></span> <span data-ttu-id="6006f-129">그러면 클라이언트에서는 오프라인 알림을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-129">Note the client receives an offline announcement.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6006f-130">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-130">The samples may already be installed on your machine.</span></span> <span data-ttu-id="6006f-131">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="6006f-131">Check for the following (default) directory before continuing.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples`
>
> <span data-ttu-id="6006f-132">이 디렉터리가 없으면 [.NET Framework 4에 대 한 Windows Communication Foundation (wcf) 및 Windows Workflow Foundation (WF) 샘플](https://www.microsoft.com/download/details.aspx?id=21459) 로 이동 하 여 모든 WINDOWS COMMUNICATION FOUNDATION (wcf) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-132">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="6006f-133">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6006f-133">This sample is located in the following directory.</span></span>
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Basic\Discovery\Announcements`
