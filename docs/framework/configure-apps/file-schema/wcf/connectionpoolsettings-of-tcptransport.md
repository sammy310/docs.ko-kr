---
title: <tcpTransport>의 <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 93363c5ff1753ff02956404da7697780078c9839
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61673240"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="c723b-102">\<connectionPoolSettings> of \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="c723b-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="c723b-103">TCP 전송에 대한 추가 연결 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
 <span data-ttu-id="c723b-104">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="c723b-104">\<system.serviceModel></span></span>  
<span data-ttu-id="c723b-105">\<bindings></span><span class="sxs-lookup"><span data-stu-id="c723b-105">\<bindings></span></span>  
<span data-ttu-id="c723b-106">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c723b-106">\<customBinding></span></span>  
<span data-ttu-id="c723b-107">\<binding></span><span class="sxs-lookup"><span data-stu-id="c723b-107">\<binding></span></span>  
<span data-ttu-id="c723b-108">\<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="c723b-108">\<tcpTransport></span></span>  
<span data-ttu-id="c723b-109">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="c723b-109">\<connectionPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c723b-110">구문</span><span class="sxs-lookup"><span data-stu-id="c723b-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpopint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="c723b-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="c723b-111">Attributes and Elements</span></span>  
 <span data-ttu-id="c723b-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="c723b-113">특성</span><span class="sxs-lookup"><span data-stu-id="c723b-113">Attributes</span></span>  
  
|<span data-ttu-id="c723b-114">특성</span><span class="sxs-lookup"><span data-stu-id="c723b-114">Attribute</span></span>|<span data-ttu-id="c723b-115">설명</span><span class="sxs-lookup"><span data-stu-id="c723b-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="c723b-116">나가는 채널에 사용되는 연결 풀의 이름을 정의하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="c723b-117">스트리밍 모드에서는 연결이 공유되지 않습니다. 즉 연결 풀링이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="c723b-118">기본값은 "default" 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-118">The default is a "default" string.</span></span> <span data-ttu-id="c723b-119">이 값을 수정하여 특정 클라이언트의 연결을 별도의 그룹으로 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="c723b-120">연결이 끊어지기 전에 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="c723b-121">기본값은 00:02:00입니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-121">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="c723b-122">활성 연결이 종료되는 유휴 시간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-122">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="c723b-123">기본값은 00:05:00입니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-123">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="c723b-124">활성 전송 중이 아니라 연결 캐시로 돌아온 후에 연결이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-124">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="c723b-125">TCP 전송에 사용되는 연결 캐시는 `maxOutboundConnectionsPerEndpoint.`로 설정된 캐시 제한까지 각 엔드포인트에 필요한 새 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-125">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="c723b-126">서비스에서 시작된 원격 엔드포인트와의 최대 연결 수를 지정하는 양의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-126">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="c723b-127">이 제한을 초과하는 연결은 채널 수가 제한 아래로 내려갈 때까지 큐에 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-127">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="c723b-128">`idleTimeout`은 예외가 throw되기 전에 연결이 큐에 대기할 수 있는 시간을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-128">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="c723b-129">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-129">The default is 10.</span></span><br /><br /> <span data-ttu-id="c723b-130">이 특성은 클라이언트에서 특정 서비스 엔드포인트로의 동시 활성 연결 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-130">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="c723b-131">활성 클라이언트 연결 수가 이 값을 초과할 경우 해당 서비스가 클라이언트에 응답하지 않는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-131">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="c723b-132">이러한 경우 이 값을 특정 엔드포인트에 대해 예상되는 동시 클라이언트 최대 연결 수보다 크게 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-132">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="c723b-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="c723b-133">Child Elements</span></span>  
 <span data-ttu-id="c723b-134">없음</span><span class="sxs-lookup"><span data-stu-id="c723b-134">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="c723b-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="c723b-135">Parent Elements</span></span>  
  
|<span data-ttu-id="c723b-136">요소</span><span class="sxs-lookup"><span data-stu-id="c723b-136">Element</span></span>|<span data-ttu-id="c723b-137">설명</span><span class="sxs-lookup"><span data-stu-id="c723b-137">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="c723b-138">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="c723b-138">\<namedPipeTransport></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/namedpipetransport.md)|<span data-ttu-id="c723b-139">채널이 명명된 파이프를 사용하여 메시지를 전송하게 하는 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="c723b-139">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="c723b-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="c723b-140">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="c723b-141">전송</span><span class="sxs-lookup"><span data-stu-id="c723b-141">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="c723b-142">전송 선택</span><span class="sxs-lookup"><span data-stu-id="c723b-142">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="c723b-143">바인딩</span><span class="sxs-lookup"><span data-stu-id="c723b-143">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="c723b-144">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="c723b-144">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="c723b-145">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="c723b-145">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="c723b-146">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="c723b-146">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
