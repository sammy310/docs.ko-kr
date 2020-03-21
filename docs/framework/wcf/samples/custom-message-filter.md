---
title: 사용자 지정 메시지 필터
ms.date: 03/30/2017
ms.assetid: 98dd0af8-fce6-4255-ac32-42eb547eea67
ms.openlocfilehash: 896407a218073eba53676baa4bcbd125593c80ca
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79183880"
---
# <a name="custom-message-filter"></a><span data-ttu-id="57322-102">사용자 지정 메시지 필터</span><span class="sxs-lookup"><span data-stu-id="57322-102">Custom Message Filter</span></span>
<span data-ttu-id="57322-103">이 샘플에서는 WCF(Windows 통신 재단)가 종료점에 메시지를 디스패치하는 데 사용하는 메시지 필터를 대체하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="57322-103">This sample demonstrates how to replace the message filters that Windows Communication Foundation (WCF) uses to dispatch messages to endpoints.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="57322-104">이 샘플의 설치 절차 및 빌드 지침은 이 항목의 끝부분에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57322-104">The setup procedure and build instructions for this sample are located at the end of this topic.</span></span>  
  
 <span data-ttu-id="57322-105">채널의 첫 번째 메시지가 서버에 도착하면 서버에서는 해당 URI에 연결된 엔드포인트 중에서 해당 메시지를 받을 엔드포인트(있는 경우)를 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-105">When the first message on a channel arrives at the server, the server must determine which (if any) of the endpoints associated with that URI should receive the message.</span></span> <span data-ttu-id="57322-106">이 프로세스는 <xref:System.ServiceModel.Dispatcher.MessageFilter>에 연결된 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> 개체에 의해 제어됩니다.</span><span class="sxs-lookup"><span data-stu-id="57322-106">This process is controlled by the <xref:System.ServiceModel.Dispatcher.MessageFilter> objects attached to the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span>  
  
 <span data-ttu-id="57322-107">서비스의 각 엔드포인트에는 단일 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57322-107">Each endpoint of a service has a single <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>.</span></span> <span data-ttu-id="57322-108"><xref:System.ServiceModel.Dispatcher.EndpointDispatcher>에는 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>와 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>가 모두 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57322-108">The <xref:System.ServiceModel.Dispatcher.EndpointDispatcher> has both an <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and a <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>.</span></span> <span data-ttu-id="57322-109">이러한 두 필터를 결합하면 해당 엔드포인트에 사용된 메시지 필터가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="57322-109">The union of these two filters is the message filter used for that endpoint.</span></span>  
  
 <span data-ttu-id="57322-110">기본적으로 엔드포인트에 대한 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>는 서비스 엔드포인트의 <xref:System.ServiceModel.EndpointAddress>와 일치하는 주소로 해당 주소가 지정된 모든 메시지와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-110">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> for an endpoint matches any message that is addressed to an address that matches the service endpoint's <xref:System.ServiceModel.EndpointAddress>.</span></span> <span data-ttu-id="57322-111">기본적으로 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> for 는 들어오는 메시지의 작업을 검사하고 서비스 끝점 계약의 작업 중 하나에 해당하는 작업과 모든 메시지를 일치시다(작업만 `IsInitiating` = `true` 고려).</span><span class="sxs-lookup"><span data-stu-id="57322-111">By default, the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> for an endpoint inspects the action of the incoming message and matches any message with an action that corresponds to one of the actions of the service endpoint contract's operations (only `IsInitiating`=`true` actions are considered).</span></span> <span data-ttu-id="57322-112">따라서 기본적으로 엔드포인트에 대한 필터는 두 메시지의 받는 사람 헤더가 엔드포인트의 <xref:System.ServiceModel.EndpointAddress>인 경우에만 일치하고 메시지의 동작은 엔드포인트 작업의 동작 중 하나와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-112">As a result, by default, the filter for an endpoint only matches if both the message's To header is the <xref:System.ServiceModel.EndpointAddress> of the endpoint and the message's action matches one of the endpoint operation's actions.</span></span>  
  
 <span data-ttu-id="57322-113">이러한 필터는 동작을 사용하여 변경할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57322-113">These filters can be changed using a behavior.</span></span> <span data-ttu-id="57322-114">이 샘플에서 서비스는 <xref:System.ServiceModel.Description.IEndpointBehavior>의 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A>와 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A>를 대체하는 <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57322-114">In the sample, the service creates an <xref:System.ServiceModel.Description.IEndpointBehavior> that replaces the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.AddressFilter%2A> and <xref:System.ServiceModel.Dispatcher.EndpointDispatcher.ContractFilter%2A> on the <xref:System.ServiceModel.Dispatcher.EndpointDispatcher>:</span></span>  
  
```csharp
class FilteringEndpointBehavior : IEndpointBehavior
{
    //...
}
```  
  
 <span data-ttu-id="57322-115">다음과 같이 두 개의 주소 필터가 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="57322-115">Two address filters are defined:</span></span>  
  
```csharp
// Matches any message whose To address contains the letter 'e'  
class MatchEAddressFilter : MessageFilter { }
// Matches any message whose To address does not contain the letter 'e'  
class MatchNoEAddressFilter : MessageFilter { }  
```  
  
 <span data-ttu-id="57322-116">`FilteringEndpointBehavior`는 구성 가능하며 두 가지 다른 변형에 대해 허용됩니다.</span><span class="sxs-lookup"><span data-stu-id="57322-116">The `FilteringEndpointBehavior` is made configurable and allows for two different variations.</span></span>  
  
```csharp
public class FilteringEndpointBehaviorExtension : BehaviorExtensionElement { }
```  
  
 <span data-ttu-id="57322-117">변형 1에서는 'e'를 포함하지만 동작이 있는 주소만 일치하고 변형 2에서는 'e'가 없는 주소만 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-117">Variation 1 matches only addresses that contain an 'e' (but that have any Action) whereas Variation 2 matches only addresses that lack an 'e':</span></span>  
  
```csharp
if (Variation == 1)  
    return new FilteringEndpointBehavior(  
        new MatchEAddressFilter(), new MatchAllMessageFilter());  
else  
    return new FilteringEndpointBehavior(  
        new MatchNoEAddressFilter(), new MatchAllMessageFilter());  
```  
  
 <span data-ttu-id="57322-118">구성 파일에서 서비스는 새 동작을 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-118">In the configuration file, the service registers the new behavior:</span></span>  
  
```xml  
<extensions>  
    <behaviorExtensions>  
        <add name="filteringEndpointBehavior" type="Microsoft.ServiceModel.Samples.FilteringEndpointBehaviorExtension, service" />  
    </behaviorExtensions>  
</extensions>
```  
  
 <span data-ttu-id="57322-119">그런 다음 서비스에서는 각 변형에 대한 `endpointBehavior` 구성을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="57322-119">Then the service creates `endpointBehavior` configurations for each variation:</span></span>  
  
```xml  
<endpointBehaviors>  
    <behavior name="endpoint1">  
        <filteringEndpointBehavior variation="1" />  
    </behavior>  
    <behavior name="endpoint2">  
        <filteringEndpointBehavior variation="2" />  
    </behavior>  
</endpointBehaviors>  
```  
  
 <span data-ttu-id="57322-120">마지막으로 서비스의 엔드포인트는 `behaviorConfigurations` 중 하나를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-120">Finally, the service's endpoint references one of the `behaviorConfigurations`:</span></span>  
  
```xml  
<endpoint address=""  
        bindingConfiguration="ws"  
        listenUri=""
        binding="wsHttpBinding"  
        contract="Microsoft.ServiceModel.Samples.IHello"
        behaviorConfiguration="endpoint2" />  
```  
  
 <span data-ttu-id="57322-121">클라이언트 애플리케이션의 구현은 간단합니다. 이 구현에서는 서비스의 URI에 대한 채널 두 개를 만들고 해당 값을 두 번째 `via` 매개 변수로 <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29>에 전달함으로써 각 채널에서 단일 메시지를 보냅니다. 그러나 각각 다른 엔드포인트 주소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-121">The implementation of the client application is straightforward; it creates two channels to the service's URI (by passing in that value as the second (`via`) parameter to <xref:System.ServiceModel.Channels.IChannelFactory%601.CreateChannel%28System.ServiceModel.EndpointAddress%29> and sends a single message on each channel, but it uses different endpoint addresses for each.</span></span> <span data-ttu-id="57322-122">따라서 클라이언트의 아웃바운드 메시지에는 다른 받는 사람이 지정되고 클라이언트의 출력에 표시된 대로 서버는 그에 따라 응답합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-122">As a result, the outbound messages from the client have different To designations, and the server responds accordingly, as demonstrated by the client's output:</span></span>  
  
```console  
Sending message to urn:e...  
Exception: The message with To 'urn:e' cannot be processed at the receiver, due to an AddressFilter mismatch at the EndpointDispatcher.  Check that the sender and receiver's EndpointAddresses agree.  
  
Sending message to urn:a...  
Hello  
```  
  
 <span data-ttu-id="57322-123">서버의 구성 파일에서 변형을 전환하면 필터가 대체되고 클라이언트에 반대 동작이 표시됩니다. 즉, `urn:e`에 대한 메시지는 성공하고 `urn:a`에 대한 메시지는 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-123">Switching the variation in the server's configuration file causes the filter to be swapped and the client sees the opposite behavior (the message to `urn:e` succeeds, whereas the message to `urn:a` fails).</span></span>  
  
```xml  
<endpoint address=""  
          bindingConfiguration="ws"  
          listenUri=""
          binding="wsHttpBinding"  
          contract="Microsoft.ServiceModel.Samples.IHello"
          behaviorConfiguration="endpoint1" />  
```  
  
> [!IMPORTANT]
> <span data-ttu-id="57322-124">컴퓨터에 이 샘플이 이미 설치되어 있을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57322-124">The samples may already be installed on your machine.</span></span> <span data-ttu-id="57322-125">계속하기 전에 다음(기본) 디렉터리를 확인하세요.</span><span class="sxs-lookup"><span data-stu-id="57322-125">Check for the following (default) directory before continuing.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples`  
>
> <span data-ttu-id="57322-126">이 디렉터리가 없는 경우 [.NET Framework 4에 대한 WCF(Windows 통신 재단) 및 WF(Windows 워크플로우 재단) 샘플로](https://www.microsoft.com/download/details.aspx?id=21459) 이동하여 모든 WCF(Windows 통신 재단) 및 [!INCLUDE[wf1](../../../../includes/wf1-md.md)] 샘플을 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="57322-126">If this directory does not exist, go to [Windows Communication Foundation (WCF) and Windows Workflow Foundation (WF) Samples for .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459) to download all Windows Communication Foundation (WCF) and [!INCLUDE[wf1](../../../../includes/wf1-md.md)] samples.</span></span> <span data-ttu-id="57322-127">이 샘플은 다음 디렉터리에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="57322-127">This sample is located in the following directory.</span></span>  
>
> `<InstallDrive>:\WF_WCF_Samples\WCF\Extensibility\MessageFilter`  
  
### <a name="to-set-up-build-and-run-the-sample"></a><span data-ttu-id="57322-128">샘플을 설치, 빌드 및 실행하려면</span><span class="sxs-lookup"><span data-stu-id="57322-128">To set up, build, and run the sample</span></span>  
  
1. <span data-ttu-id="57322-129">솔루션을 빌드하려면 Windows 통신 [기초 샘플 빌드의 지침을 따르십시오.](../../../../docs/framework/wcf/samples/building-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="57322-129">To build the solution, follow the instructions in [Building the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/building-the-samples.md).</span></span>  
  
2. <span data-ttu-id="57322-130">단일 컴퓨터 구성에서 샘플을 실행하려면 Windows 통신 기반 샘플 실행의 지침을 [따릅니다.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="57322-130">To run the sample in a single-machine configuration, follow the instructions in [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md).</span></span>  
  
3. <span data-ttu-id="57322-131">컴퓨터 간 구성에서 샘플을 실행하려면 Windows 통신 기반 샘플 실행의 지침을 따르고 Client.cs 다음 줄을 [변경합니다.](../../../../docs/framework/wcf/samples/running-the-samples.md)</span><span class="sxs-lookup"><span data-stu-id="57322-131">To run the sample in a cross-machine configuration, follow the instructions at [Running the Windows Communication Foundation Samples](../../../../docs/framework/wcf/samples/running-the-samples.md) and change the following line in Client.cs.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://localhost/ServiceModelSamples/service.svc");  
    ```  
  
     <span data-ttu-id="57322-132">localhost를 서버 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="57322-132">Replace localhost with the name of server.</span></span>  
  
    ```csharp
    Uri serviceVia = new Uri("http://servermachinename/ServiceModelSamples/service.svc");  
    ```  
