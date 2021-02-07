---
description: '자세히 알아보기: NetHttpBinding 사용'
title: NetHttpBinding 사용
ms.date: 03/30/2017
ms.assetid: fe134acf-ceca-49de-84a9-05a37e3841f1
ms.openlocfilehash: 3964c3c3e563d143df1edfcd1f98d3250301c209
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99756047"
---
# <a name="using-the-nethttpbinding"></a><span data-ttu-id="21fa0-103">NetHttpBinding 사용</span><span class="sxs-lookup"><span data-stu-id="21fa0-103">Using the NetHttpBinding</span></span>

<span data-ttu-id="21fa0-104"><xref:System.ServiceModel.NetHttpBinding> 는 HTTP 또는 WebSocket 서비스를 사용 하도록 디자인 된 바인딩이 며 기본적으로 이진 인코딩을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-104"><xref:System.ServiceModel.NetHttpBinding> is a binding designed for consuming HTTP or WebSocket services and uses binary encoding by default.</span></span> <span data-ttu-id="21fa0-105"><xref:System.ServiceModel.NetHttpBinding>은 해당 바인딩이 HTTP 요청-회신 계약에 사용되는지 이중 계약에 사용되는지를 검색하고 그에 맞게 동작을 변경합니다. 요청-회신 계약에는 HTTP가 사용되고 이중 계약에는 WebSocket이 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-105"><xref:System.ServiceModel.NetHttpBinding> will detect whether it is used with a request-reply contract or duplex contract and change its behavior to match - it will use HTTP for request-reply contracts and WebSockets for duplex contracts.</span></span> <span data-ttu-id="21fa0-106"><xref:System.ServiceModel.Channels.WebSocketTransportUsage> 설정을 사용하여 이 동작을 재정의할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-106">This behavior can be overridden using the <xref:System.ServiceModel.Channels.WebSocketTransportUsage> setting:</span></span>  
  
1. <span data-ttu-id="21fa0-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> -이렇게 하면 Websocket이 요청-회신 계약에도 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-107"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Always> - This forces WebSockets to be used even for request-reply contracts.</span></span>  
  
2. <span data-ttu-id="21fa0-108"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> -이렇게 하면 Websocket이 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-108"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.Never> - This prevents WebSockets from being used.</span></span> <span data-ttu-id="21fa0-109">이 설정으로 이중 계약을 사용 하려고 하면 예외가 발생 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-109">Attempting to use a duplex contract with this setting will result in an exception.</span></span>  
  
3. <span data-ttu-id="21fa0-110"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> -이 값은 기본값이 며 위에 설명 된 대로 동작 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-110"><xref:System.ServiceModel.Channels.WebSocketTransportUsage.WhenDuplex> - This is the default value and behaves as described above.</span></span>  
  
 <span data-ttu-id="21fa0-111"><xref:System.ServiceModel.NetHttpBinding> 는 HTTP 모드 및 WebSocket 모드에서 신뢰할 수 있는 세션을 지원 합니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-111"><xref:System.ServiceModel.NetHttpBinding> supports reliable sessions in both HTTP mode and WebSocket mode.</span></span> <span data-ttu-id="21fa0-112">WebSocket 모드에서 세션은 전송에 의해 제공 됩니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-112">In WebSocket mode sessions are provided by the transport.</span></span>  
  
> [!WARNING]
> <span data-ttu-id="21fa0-113"><xref:System.ServiceModel.NetHttpBinding>이 사용되고 바인딩의 TransferMode가 TransferMode.Streamed로 설정된 경우 큰 스트림으로 인해 교착 상태가 발생하고 호출이 시간 초과될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-113">When using the <xref:System.ServiceModel.NetHttpBinding> and the binding’s TransferMode is set to TransferMode.Streamed, large streams may cause a deadlock and the call will timeout.</span></span> <span data-ttu-id="21fa0-114">이 문제를 해결하려면 보다 작은 메시지를 보내거나 TransferMode.Buffered를 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="21fa0-114">To work around this issue send smaller messages or use TransferMode.Buffered.</span></span>  
  
## <a name="configuring-a-service-to-use-nethttpbinding"></a><span data-ttu-id="21fa0-115">NetHttpBinding을 사용하도록 서비스 구성</span><span class="sxs-lookup"><span data-stu-id="21fa0-115">Configuring a Service to use NetHttpBinding</span></span>  

 <span data-ttu-id="21fa0-116">다른 바인딩과 동일하게 <xref:System.ServiceModel.NetHttpBinding>을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-116">The <xref:System.ServiceModel.NetHttpBinding> can be configured the same as any other binding.</span></span> <span data-ttu-id="21fa0-117">다음 구성 조각에서는 <xref:System.ServiceModel.NetHttpBinding>을 사용하여 WCF 서비스를 구성하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-117">The following configuration snippet illustrates how to configure a WCF service with <xref:System.ServiceModel.NetHttpBinding>.</span></span>  
  
```xml  
<system.serviceModel>  
    <services>  
      <service name="WcfService1.Service1">  
        <endpoint address=""  
                  binding="netHttpBinding"  
                  contract="WcfService1.IService1"/>  
        <endpoint address="mex"  
                  binding="mexHttpBinding"  
                  contract="IMetadataExchange"/>  
      </service>  
    </services>  
    <bindings>  
      <netHttpBinding>  
        <binding name="My_NetHttpBindingConfig">  
          <webSocketSettings transportUsage="WhenDuplex"/>  
        </binding>  
      </netHttpBinding>  
    </bindings>  
    ...
  </system.serviceModel>  
```  
  
 <span data-ttu-id="21fa0-118">다음 코드 조각에서는 코드로 <xref:System.ServiceModel.NetHttpBinding>을 추가하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="21fa0-118">The following code snippet shows how to add the <xref:System.ServiceModel.NetHttpBinding> in code.</span></span>  
  
```csharp  
ServiceHost svchost = new ServiceHost(typeof(Service1), baseAddress);  
            NetHttpBinding binding = new NetHttpBinding();  
            svchost.AddServiceEndpoint(typeof(IService1), binding, address);
        }  
```  
  
## <a name="see-also"></a><span data-ttu-id="21fa0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="21fa0-119">See also</span></span>

- [<span data-ttu-id="21fa0-120">서비스에 대한 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="21fa0-120">Configuring Bindings for Services</span></span>](../configuring-bindings-for-wcf-services.md)
- [<span data-ttu-id="21fa0-121">바인딩</span><span class="sxs-lookup"><span data-stu-id="21fa0-121">Bindings</span></span>](bindings.md)
- [<span data-ttu-id="21fa0-122">시스템 제공 바인딩</span><span class="sxs-lookup"><span data-stu-id="21fa0-122">System-Provided Bindings</span></span>](../system-provided-bindings.md)
- [<span data-ttu-id="21fa0-123">이중 서비스</span><span class="sxs-lookup"><span data-stu-id="21fa0-123">Duplex Services</span></span>](duplex-services.md)
