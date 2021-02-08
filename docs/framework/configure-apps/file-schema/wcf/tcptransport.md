---
description: 다음에 대해 자세히 알아보세요. <tcpTransport>
title: <tcpTransport>
ms.date: 03/30/2017
ms.assetid: 8fcd18c1-9958-42e7-b442-7903f7bdb563
ms.openlocfilehash: b660443ac58e8ed72d70adb5bf9e9e87b060e3af
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99786618"
---
# \<tcpTransport>

<span data-ttu-id="f3585-102">사용자 지정 바인딩에 대한 메시지를 전송하기 위해 채널이 사용할 수 있는 TCP 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-102">Defines a TCP transport that can be used by a channel to transfers messages for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<tcpTransport>**  
  
## <a name="syntax"></a><span data-ttu-id="f3585-103">구문</span><span class="sxs-lookup"><span data-stu-id="f3585-103">Syntax</span></span>  
  
```xml  
<tcpTransport channelInitializationTimeout="TimeSpan"
              connectionBufferSize="Integer"
              hostNameComparisonMode="StrongWildcard/Exact/WeakWildcard"
              listenBacklog="Integer"
              manualAddressing="Boolean"
              maxBufferPoolSize="Integer"
              maxBufferSize="Integer"
              maxOutputDelay="TimeSpan"
              maxPendingAccepts="Integer"
              maxPendingConnections="Integer"
              maxReceivedMessageSize="Integer"
              portSharingEnabled="Boolean"
              teredoEnabled="Boolean"
              transferMode="Buffered/Streamed/StreamedRequest/StreamedResponse" >
  <connectionPoolSettings groupName="String"
                          idleTimeout="TimeSpan"
                          leaseTimeout="TimeSpan"
                          maxOutboundConnectionsPerEndpoint="Integer" />
</tcpTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="f3585-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="f3585-104">Attributes and Elements</span></span>  

 <span data-ttu-id="f3585-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="f3585-106">특성</span><span class="sxs-lookup"><span data-stu-id="f3585-106">Attributes</span></span>  
  
|<span data-ttu-id="f3585-107">attribute</span><span class="sxs-lookup"><span data-stu-id="f3585-107">Attribute</span></span>|<span data-ttu-id="f3585-108">설명</span><span class="sxs-lookup"><span data-stu-id="f3585-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="f3585-109">channelInitializationTimeout</span><span class="sxs-lookup"><span data-stu-id="f3585-109">channelInitializationTimeout</span></span>|<span data-ttu-id="f3585-110">수락할 채널을 초기화하기 위한 시간 제한을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-110">Gets or sets the time limit for initializing a channel to be accepted.</span></span>  <span data-ttu-id="f3585-111">연결이 끊어지기 전에 채널이 초기화 상태를 유지할 수 있는 최대 시간(초)입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-111">The maximum time a channel can be in the initialization state before being disconnected in seconds.</span></span> <span data-ttu-id="f3585-112">이 할당량에는 TCP 연결이 .NET 메시지 프레이밍 프로토콜을 사용 하 여 자신을 인증 하는 데 사용할 수 있는 시간이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-112">This quota includes the time a TCP connection can take to authenticate itself using the .NET Message Framing protocol.</span></span> <span data-ttu-id="f3585-113">서버가 인증을 수행하는 데 충분한 정보를 가지려면 클라이언트가 몇 가지 초기 데이터를 보내야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-113">A client needs to send some initial data before the server has enough information to perform authentication.</span></span> <span data-ttu-id="f3585-114">기본값은 30초입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-114">The default is 30 seconds.</span></span>|  
|<span data-ttu-id="f3585-115">connectionBufferSize</span><span class="sxs-lookup"><span data-stu-id="f3585-115">connectionBufferSize</span></span>|<span data-ttu-id="f3585-116">통신 중에 클라이언트나 서비스로부터 serialize된 메시지 청크를 전송할 때 사용되는 버퍼의 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-116">Gets or sets the size of the buffer used to transmit a chunk of the serialized message on the wire from the client or service.</span></span>|  
|<span data-ttu-id="f3585-117">hostNameComparisonMode</span><span class="sxs-lookup"><span data-stu-id="f3585-117">hostNameComparisonMode</span></span>|<span data-ttu-id="f3585-118">URI 비교 시 서비스에 액세스하는 데 호스트 이름이 사용되는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-118">Gets or sets a value that indicates whether the hostname is used to reach the service when matching on the URI.</span></span>|  
|<span data-ttu-id="f3585-119">listenBacklog</span><span class="sxs-lookup"><span data-stu-id="f3585-119">listenBacklog</span></span>|<span data-ttu-id="f3585-120">웹 서비스에 대해 보류할 수 있는 최대 대기 중인 연결 요청 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-120">The maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="f3585-121">`connectionLeaseTimeout` 특성은 연결 예외가 throw되기 전에 클라이언트가 연결을 대기하는 시간을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-121">The `connectionLeaseTimeout` attribute limits the duration the client will wait to be connected before throwing a connection exception.</span></span> <span data-ttu-id="f3585-122">웹 서비스에 대해 보류할 수 있는 최대 대기 중인 연결 요청 수를 제어하는 소켓 수준 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-122">This is a socket level property which controls the maximum number of queued connection requests that can be pending for a Web service.</span></span> <span data-ttu-id="f3585-123">ListenBacklog이 너무 낮으면 WCF는 요청 수락을 중지 하므로 서버에서 대기 중인 기존 연결 중 일부를 승인할 때까지 새 연결을 삭제 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-123">When ListenBacklog is too low, WCF will stop accepting requests and therefore drop new connections until the server acknowledges some of the existing queued connections.</span></span> <span data-ttu-id="f3585-124">기본값은 16 \* 프로세서 수입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-124">The default is 16 \* number of processors.</span></span>|  
|<span data-ttu-id="f3585-125">manualAddressing</span><span class="sxs-lookup"><span data-stu-id="f3585-125">manualAddressing</span></span>|<span data-ttu-id="f3585-126">메시지의 주소를 수동으로 지정해야 하는지 여부를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-126">Gets or sets a value that indicates whether manual addressing of the message is required.</span></span>|  
|<span data-ttu-id="f3585-127">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="f3585-127">maxBufferPoolSize</span></span>|<span data-ttu-id="f3585-128">전송에 사용되는 최대 버퍼 풀 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-128">Gets or sets the maximum size of any buffer pools used by the transport.</span></span>|  
|<span data-ttu-id="f3585-129">maxBufferSize</span><span class="sxs-lookup"><span data-stu-id="f3585-129">maxBufferSize</span></span>|<span data-ttu-id="f3585-130">사용할 버퍼의 최대 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-130">Gets or sets the maximum size of the buffer to use.</span></span> <span data-ttu-id="f3585-131">스트리밍된 메시지의 경우 이 값은 버퍼링된 모드에서 읽어오는 메시지 헤더의 최대 예상 크기 이상이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-131">For streamed messages, this value should be at least the maximum possible size of the message headers, which are read in buffered mode.</span></span>|  
|<span data-ttu-id="f3585-132">maxOutputDelay</span><span class="sxs-lookup"><span data-stu-id="f3585-132">maxOutputDelay</span></span>|<span data-ttu-id="f3585-133">메시지 청크 또는 전체 메시지를 보내기 전에 메모리에 버퍼링된 상태로 유지할 수 있는 최대 시간 간격을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-133">Gets or sets the maximum interval of time that a chunk of a message or a full message can remain buffered in memory before being sent out.</span></span>|  
|<span data-ttu-id="f3585-134">maxPendingAccepts</span><span class="sxs-lookup"><span data-stu-id="f3585-134">maxPendingAccepts</span></span>|<span data-ttu-id="f3585-135">서비스에 들어오는 연결을 처리하는 데 사용할 수 있는 보류 중인 최대 비동기 수락 작업 수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-135">Gets or sets the maximum number of pending asynchronous accept operations that are available for processing incoming connections to the service.</span></span>|  
|<span data-ttu-id="f3585-136">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="f3585-136">maxPendingConnections</span></span>|<span data-ttu-id="f3585-137">서비스에서 디스패치를 대기하는 최대 연결 수를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-137">Gets or sets the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="f3585-138">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="f3585-138">maxReceivedMessageSize</span></span>|<span data-ttu-id="f3585-139">받을 수 있는 최대 메시지 크기를 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-139">Gets and sets the maximum allowable message size that can be received.</span></span>|  
|<span data-ttu-id="f3585-140">portSharingEnabled</span><span class="sxs-lookup"><span data-stu-id="f3585-140">portSharingEnabled</span></span>|<span data-ttu-id="f3585-141">이 연결에서 TCP 포트 공유를 사용하는지를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-141">A Boolean value that specifies if TCP port sharing is enabled for this connection.</span></span> <span data-ttu-id="f3585-142">이 값이 `false`이면 바인딩마다 자체 단독 포트가 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-142">If this is `false`, each binding will use its own exclusive port.</span></span> <span data-ttu-id="f3585-143">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-143">The default is `false`.</span></span><br /><br /> <span data-ttu-id="f3585-144">이 설정은 서비스에만 적용되며,</span><span class="sxs-lookup"><span data-stu-id="f3585-144">This setting is relevant only to services.</span></span> <span data-ttu-id="f3585-145">클라이언트는 영향을 받지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-145">Clients are not affected.</span></span><br /><br /> <span data-ttu-id="f3585-146">이 설정을 사용하려면 WCF(Windows Communication Foundation) TCP 포트 공유 서비스의 시작 유형을 수동 또는 자동으로 변경하여 서비스를 사용하도록 설정해야 합니다</span><span class="sxs-lookup"><span data-stu-id="f3585-146">Using this setting requires enabling the Windows Communication Foundation (WCF) TCP Port Sharing Service by changing its Startup Type to Manual or Automatic</span></span>|  
|<span data-ttu-id="f3585-147">teredoEnabled</span><span class="sxs-lookup"><span data-stu-id="f3585-147">teredoEnabled</span></span>|<span data-ttu-id="f3585-148">Teredo(방화벽으로 보호되는 클라이언트의 주소를 지정하는 기술)의 사용 여부를 지정하는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-148">A Boolean value that specifies whether Teredo (a technology for addressing clients that are behind firewalls) is enabled.</span></span> <span data-ttu-id="f3585-149">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-149">The default is `false`.</span></span><br /><br /> <span data-ttu-id="f3585-150">이 속성은 내부 TCP 소켓에 대해 Teredo를 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-150">This property enables Teredo for the underlying TCP socket.</span></span> <span data-ttu-id="f3585-151">자세한 내용은 [Teredo 개요](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10))합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-151">For more information, see [Teredo Overview](/previous-versions/windows/it-pro/windows-xp/bb457011(v=technet.10)).</span></span><br /><br /> <span data-ttu-id="f3585-152">이 속성은 Windows XP SP2 및 Windows Server 2003에만 적용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-152">This property is applicable only on Windows XP SP2 and Windows Server 2003.</span></span> <span data-ttu-id="f3585-153">Windows Vista에는 Teredo 용 시스템 수준의 구성 옵션이 있으므로 Vista를 실행할 때이 속성이 무시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-153">Windows Vista has a machine-wide configuration option for Teredo, so when running Vista, this property is ignored.</span></span> <span data-ttu-id="f3585-154">Teredo를 사용할 경우 클라이언트와 서비스 시스템 모두에 Microsoft IPv6 스택을 설치하고 Teredo 사용에 적합하도록 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-154">Teredo requires that the client and service machines both have the Microsoft IPv6 stack installed and correctly configured for Teredo usage.</span></span>|  
|<span data-ttu-id="f3585-155">transferMode</span><span class="sxs-lookup"><span data-stu-id="f3585-155">transferMode</span></span>|<span data-ttu-id="f3585-156">메시지가 연결 지향 전송을 사용하여 버퍼링되는지 아니면 스트리밍되는지를 나타내는 값을 가져오거나 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-156">Gets or sets a value that indicates whether the messages are buffered or streamed with the connection-oriented transport.</span></span>|  
|<span data-ttu-id="f3585-157">connectionPoolSettings</span><span class="sxs-lookup"><span data-stu-id="f3585-157">connectionPoolSettings</span></span>|<span data-ttu-id="f3585-158">명명된 파이프 바인딩의 추가 연결 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-158">Specifies additional connection pool settings for a Named Pipe binding.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="f3585-159">자식 요소</span><span class="sxs-lookup"><span data-stu-id="f3585-159">Child Elements</span></span>  

 <span data-ttu-id="f3585-160">없음</span><span class="sxs-lookup"><span data-stu-id="f3585-160">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="f3585-161">부모 요소</span><span class="sxs-lookup"><span data-stu-id="f3585-161">Parent Elements</span></span>  
  
|<span data-ttu-id="f3585-162">요소</span><span class="sxs-lookup"><span data-stu-id="f3585-162">Element</span></span>|<span data-ttu-id="f3585-163">설명</span><span class="sxs-lookup"><span data-stu-id="f3585-163">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="f3585-164">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-164">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3585-165">설명</span><span class="sxs-lookup"><span data-stu-id="f3585-165">Remarks</span></span>  

 <span data-ttu-id="f3585-166">이 전송은 "net.tcp://hostname:port/path" 형식의 URI를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-166">This transport uses URIs of the form "net.tcp://hostname:port/path".</span></span> <span data-ttu-id="f3585-167">다른 URI 구성 요소는 선택적입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-167">Other URI components are optional.</span></span>  
  
 <span data-ttu-id="f3585-168">`tcpTransport` 요소는 TCP 전송 프로토콜을 구현하는 사용자 지정 바인딩을 만들기 위한 시작점입니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-168">The `tcpTransport` element is the starting point for creating a custom binding that implements the TCP transport protocol.</span></span> <span data-ttu-id="f3585-169">이 전송은 WCF와 WCF 사이의 통신을 위해 최적화됩니다.</span><span class="sxs-lookup"><span data-stu-id="f3585-169">This transport is optimized for WCF-to-WCF communication.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3585-170">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f3585-170">See also</span></span>

- <xref:System.ServiceModel.Configuration.TcpTransportElement>
- <xref:System.ServiceModel.Channels.TcpTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="f3585-171">전송</span><span class="sxs-lookup"><span data-stu-id="f3585-171">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="f3585-172">전송 선택</span><span class="sxs-lookup"><span data-stu-id="f3585-172">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="f3585-173">바인딩</span><span class="sxs-lookup"><span data-stu-id="f3585-173">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="f3585-174">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="f3585-174">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="f3585-175">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="f3585-175">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
