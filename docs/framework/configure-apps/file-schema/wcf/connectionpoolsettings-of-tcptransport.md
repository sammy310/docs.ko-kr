---
title: <tcpTransport>의 <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: f9b0fff741c32c1a3d6f9461f478e89acc18114e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398092"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="36eae-102">\<connectionPoolSettings> of \<tcpTransport></span><span class="sxs-lookup"><span data-stu-id="36eae-102">\<connectionPoolSettings> of \<tcpTransport></span></span>
<span data-ttu-id="36eae-103">TCP 전송에 대한 추가 연결 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-103">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
<span data-ttu-id="36eae-104">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="36eae-104">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="36eae-105">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="36eae-105">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="36eae-106">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="36eae-106">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="36eae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="36eae-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="36eae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="36eae-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="36eae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<tcpTransport >** ](tcptransport.md)</span><span class="sxs-lookup"><span data-stu-id="36eae-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)</span></span>\
<span data-ttu-id="36eae-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<connectionPoolSettings >**</span><span class="sxs-lookup"><span data-stu-id="36eae-110">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36eae-111">구문</span><span class="sxs-lookup"><span data-stu-id="36eae-111">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="36eae-112">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="36eae-112">Attributes and Elements</span></span>  
 <span data-ttu-id="36eae-113">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-113">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="36eae-114">특성</span><span class="sxs-lookup"><span data-stu-id="36eae-114">Attributes</span></span>  
  
|<span data-ttu-id="36eae-115">특성</span><span class="sxs-lookup"><span data-stu-id="36eae-115">Attribute</span></span>|<span data-ttu-id="36eae-116">Description</span><span class="sxs-lookup"><span data-stu-id="36eae-116">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="36eae-117">나가는 채널에 사용되는 연결 풀의 이름을 정의하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-117">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="36eae-118">스트리밍 모드에서는 연결이 공유되지 않습니다. 즉 연결 풀링이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-118">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="36eae-119">기본값은 "default" 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-119">The default is a "default" string.</span></span> <span data-ttu-id="36eae-120">이 값을 수정하여 특정 클라이언트의 연결을 별도의 그룹으로 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-120">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="36eae-121">연결이 끊어지기 전에 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-121">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="36eae-122">기본값은 00:02:00입니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-122">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="36eae-123">활성 연결이 종료되는 유휴 시간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-123">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="36eae-124">기본값은 00:05:00입니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-124">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="36eae-125">활성 전송 중이 아니라 연결 캐시로 돌아온 후에 연결이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-125">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="36eae-126">TCP 전송에 사용되는 연결 캐시는 `maxOutboundConnectionsPerEndpoint.`로 설정된 캐시 제한까지 각 엔드포인트에 필요한 새 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-126">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="36eae-127">서비스에서 시작된 원격 엔드포인트와의 최대 연결 수를 지정하는 양의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-127">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="36eae-128">이 제한을 초과하는 연결은 채널 수가 제한 아래로 내려갈 때까지 큐에 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-128">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="36eae-129">`idleTimeout`은 예외가 throw되기 전에 연결이 큐에 대기할 수 있는 시간을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-129">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="36eae-130">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-130">The default is 10.</span></span><br /><br /> <span data-ttu-id="36eae-131">이 특성은 클라이언트에서 특정 서비스 엔드포인트로의 동시 활성 연결 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-131">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="36eae-132">활성 클라이언트 연결 수가 이 값을 초과할 경우 해당 서비스가 클라이언트에 응답하지 않는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-132">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="36eae-133">이러한 경우 이 값을 특정 엔드포인트에 대해 예상되는 동시 클라이언트 최대 연결 수보다 크게 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-133">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="36eae-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="36eae-134">Child Elements</span></span>  
 <span data-ttu-id="36eae-135">없음</span><span class="sxs-lookup"><span data-stu-id="36eae-135">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="36eae-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="36eae-136">Parent Elements</span></span>  
  
|<span data-ttu-id="36eae-137">요소</span><span class="sxs-lookup"><span data-stu-id="36eae-137">Element</span></span>|<span data-ttu-id="36eae-138">Description</span><span class="sxs-lookup"><span data-stu-id="36eae-138">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="36eae-139">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="36eae-139">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="36eae-140">채널이 명명된 파이프를 사용하여 메시지를 전송하게 하는 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="36eae-140">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="36eae-141">참고자료</span><span class="sxs-lookup"><span data-stu-id="36eae-141">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="36eae-142">전송</span><span class="sxs-lookup"><span data-stu-id="36eae-142">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="36eae-143">전송 선택</span><span class="sxs-lookup"><span data-stu-id="36eae-143">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="36eae-144">바인딩</span><span class="sxs-lookup"><span data-stu-id="36eae-144">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="36eae-145">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="36eae-145">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="36eae-146">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="36eae-146">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="36eae-147">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="36eae-147">\<customBinding></span></span>](custombinding.md)
