---
description: '다음에 대 한 자세한 정보:: <connectionPoolSettings><tcpTransport>'
title: <tcpTransport>의 <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 2fbc3aa7-fcc9-4193-99a3-85d31d60d3f7
ms.openlocfilehash: 065d3529740714ffd740c2cec71832a7b386b4a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99698390"
---
# <a name="connectionpoolsettings-of-tcptransport"></a><span data-ttu-id="f5271-103">\<tcpTransport>의 \<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="f5271-103">\<connectionPoolSettings> of \<tcpTransport></span></span>

<span data-ttu-id="f5271-104">TCP 전송에 대한 추가 연결 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-104">Specifies additional connection pool settings for a TCP transport.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<tcpTransport>**](tcptransport.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="f5271-105">구문</span><span class="sxs-lookup"><span data-stu-id="f5271-105">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        leaseTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f5271-106">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f5271-106">Attributes and Elements</span></span>  

 <span data-ttu-id="f5271-107">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-107">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f5271-108">특성</span><span class="sxs-lookup"><span data-stu-id="f5271-108">Attributes</span></span>  
  
|<span data-ttu-id="f5271-109">attribute</span><span class="sxs-lookup"><span data-stu-id="f5271-109">Attribute</span></span>|<span data-ttu-id="f5271-110">설명</span><span class="sxs-lookup"><span data-stu-id="f5271-110">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="f5271-111">나가는 채널에 사용되는 연결 풀의 이름을 정의하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-111">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="f5271-112">스트리밍 모드에서는 연결이 공유되지 않습니다. 즉 연결 풀링이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-112">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="f5271-113">기본값은 "default" 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-113">The default is a "default" string.</span></span> <span data-ttu-id="f5271-114">이 값을 수정하여 특정 클라이언트의 연결을 별도의 그룹으로 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-114">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="f5271-115">연결이 끊어지기 전에 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-115">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="f5271-116">기본값은 00:02:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="f5271-117">활성 연결이 종료되는 유휴 시간을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-117">A <xref:System.TimeSpan> that specifies the time after which an active connection is closed.</span></span> <span data-ttu-id="f5271-118">기본값은 00:05:00입니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-118">The default is 00:05:00.</span></span><br /><br /> <span data-ttu-id="f5271-119">활성 전송 중이 아니라 연결 캐시로 돌아온 후에 연결이 닫힙니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-119">A connection is closed after it has been returned to the connection cache and not during active transmission.</span></span> <span data-ttu-id="f5271-120">TCP 전송에 사용되는 연결 캐시는 `maxOutboundConnectionsPerEndpoint.`로 설정된 캐시 제한까지 각 엔드포인트에 필요한 새 연결을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-120">The connection cache used by the TCP transport creates new connections as required for each endpoint, up to the cache limit that is set by `maxOutboundConnectionsPerEndpoint.`</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="f5271-121">서비스에서 시작된 원격 엔드포인트와의 최대 연결 수를 지정하는 양의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-121">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="f5271-122">이 제한을 초과하는 연결은 채널 수가 제한 아래로 내려갈 때까지 큐에 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-122">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="f5271-123">`idleTimeout`은 예외가 throw되기 전에 연결이 큐에 대기할 수 있는 시간을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-123">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="f5271-124">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-124">The default is 10.</span></span><br /><br /> <span data-ttu-id="f5271-125">이 특성은 클라이언트에서 특정 서비스 엔드포인트로의 동시 활성 연결 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-125">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="f5271-126">활성 클라이언트 연결 수가 이 값을 초과할 경우 해당 서비스가 클라이언트에 응답하지 않는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-126">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="f5271-127">이러한 경우 이 값을 특정 엔드포인트에 대해 예상되는 동시 클라이언트 최대 연결 수보다 크게 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-127">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f5271-128">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f5271-128">Child Elements</span></span>  

 <span data-ttu-id="f5271-129">없음</span><span class="sxs-lookup"><span data-stu-id="f5271-129">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f5271-130">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f5271-130">Parent Elements</span></span>  
  
|<span data-ttu-id="f5271-131">요소</span><span class="sxs-lookup"><span data-stu-id="f5271-131">Element</span></span>|<span data-ttu-id="f5271-132">설명</span><span class="sxs-lookup"><span data-stu-id="f5271-132">Description</span></span>|  
|-------------|-----------------|  
|[\<namedPipeTransport>](namedpipetransport.md)|<span data-ttu-id="f5271-133">채널이 명명된 파이프를 사용하여 메시지를 전송하게 하는 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f5271-133">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="f5271-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f5271-134">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.TcpConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f5271-135">전송</span><span class="sxs-lookup"><span data-stu-id="f5271-135">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="f5271-136">전송 선택</span><span class="sxs-lookup"><span data-stu-id="f5271-136">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="f5271-137">바인딩</span><span class="sxs-lookup"><span data-stu-id="f5271-137">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f5271-138">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="f5271-138">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f5271-139">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="f5271-139">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
