---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: fc1930889235805d68d88aa8080f8f9fb3235612
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69933036"
---
# <a name="netpeertcpbinding"></a><span data-ttu-id="616b1-101">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="616b1-101">\<netPeerTcpBinding></span></span>
<span data-ttu-id="616b1-102">피어 채널 전용 TCP 메시징의 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
 <span data-ttu-id="616b1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="616b1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="616b1-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="616b1-104">\<bindings></span></span>  
<span data-ttu-id="616b1-105">\<netPeerTcpBinding></span><span class="sxs-lookup"><span data-stu-id="616b1-105">\<netPeerTcpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="616b1-106">구문</span><span class="sxs-lookup"><span data-stu-id="616b1-106">Syntax</span></span>  
  
```xml  
<netPeerBinding>
  <binding name="string"
           closeTimeout="TimeSpan"
           openTimeout="TimeSpan"
           receiveTimeout="TimeSpan"
           sendTimeout="TimeSpan"
           listenIPAddress="String"
           maxBufferPoolSize="integer"
           maxReceiveMessageSize="Integer"
           port="Integer">
    <security mode="None/Transport/Message/TransportWithMessageCredential">
      <transport credentialType="Certificate/Password" />
    </security>
  </binding>
</netPeerBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="616b1-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="616b1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="616b1-108">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-108">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="616b1-109">특성</span><span class="sxs-lookup"><span data-stu-id="616b1-109">Attributes</span></span>  
  
|<span data-ttu-id="616b1-110">특성</span><span class="sxs-lookup"><span data-stu-id="616b1-110">Attribute</span></span>|<span data-ttu-id="616b1-111">설명</span><span class="sxs-lookup"><span data-stu-id="616b1-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="616b1-112">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="616b1-112">closeTimeout</span></span>|<span data-ttu-id="616b1-113">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-113">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="616b1-114">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-114">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="616b1-115">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-115">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="616b1-116">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="616b1-116">listenIPAddress</span></span>|<span data-ttu-id="616b1-117">피어 노드가 TCP 메시지를 수신하는 IP 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-117">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="616b1-118">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-118">The default is `null`.</span></span>|  
|<span data-ttu-id="616b1-119">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="616b1-119">maxBufferPoolSize</span></span>|<span data-ttu-id="616b1-120">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-120">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="616b1-121">기본값은 524,288바이트(512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-121">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="616b1-122">WCF(Windows Communication Foundation)의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-122">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="616b1-123">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-123">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="616b1-124">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-124">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="616b1-125">따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-125">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="616b1-126">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="616b1-126">maxReceivedMessageSize</span></span>|<span data-ttu-id="616b1-127">헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-127">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="616b1-128">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-128">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="616b1-129">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-129">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="616b1-130">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-130">The default is 65536.</span></span>|  
|<span data-ttu-id="616b1-131">name</span><span class="sxs-lookup"><span data-stu-id="616b1-131">name</span></span>|<span data-ttu-id="616b1-132">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-132">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="616b1-133">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-133">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="616b1-134">[!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)]부터는 바인딩 및 동작에 이름이 필요하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-134">Starting with [!INCLUDE[netfx40_short](../../../../../includes/netfx40-short-md.md)], bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="616b1-135">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="616b1-135">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="616b1-136">openTimeout</span><span class="sxs-lookup"><span data-stu-id="616b1-136">openTimeout</span></span>|<span data-ttu-id="616b1-137">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-137">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="616b1-138">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-138">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="616b1-139">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-139">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="616b1-140">포트</span><span class="sxs-lookup"><span data-stu-id="616b1-140">port</span></span>|<span data-ttu-id="616b1-141">이 바인딩이 피어 채널 TCP 메시지를 처리할 네트워크 인터페이스 포트를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-141">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="616b1-142">이 값은 <xref:System.Net.IPEndPoint.MinPort>와 <xref:System.Net.IPEndPoint.MaxPort> 사이의 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-142">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="616b1-143">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-143">The default is 0.</span></span>|  
|<span data-ttu-id="616b1-144">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="616b1-144">receiveTimeout</span></span>|<span data-ttu-id="616b1-145">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="616b1-146">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="616b1-147">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-147">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="616b1-148">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="616b1-148">sendTimeout</span></span>|<span data-ttu-id="616b1-149">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-149">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="616b1-150">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-150">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="616b1-151">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-151">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="616b1-152">자식 요소</span><span class="sxs-lookup"><span data-stu-id="616b1-152">Child Elements</span></span>  
  
|<span data-ttu-id="616b1-153">요소</span><span class="sxs-lookup"><span data-stu-id="616b1-153">Element</span></span>|<span data-ttu-id="616b1-154">설명</span><span class="sxs-lookup"><span data-stu-id="616b1-154">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="616b1-155">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="616b1-155">[\<readerQuotas>](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))</span></span>|<span data-ttu-id="616b1-156">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-156">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="616b1-157">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-157">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[<span data-ttu-id="616b1-158">\<resolver></span><span class="sxs-lookup"><span data-stu-id="616b1-158">\<resolver></span></span>](resolver.md)|<span data-ttu-id="616b1-159">피어 메시 내에서 노드의 엔드포인트 IP 주소에 대해 피어 메시 ID를 확인하기 위해 이 바인딩에서 사용하는 피어 확인자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-159">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[<span data-ttu-id="616b1-160">\<security></span><span class="sxs-lookup"><span data-stu-id="616b1-160">\<security></span></span>](security-of-netpeerbinding.md)|<span data-ttu-id="616b1-161">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-161">Defines the security settings for the message.</span></span> <span data-ttu-id="616b1-162">이 요소는 <xref:System.ServiceModel.Configuration.PeerSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-162">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="616b1-163">부모 요소</span><span class="sxs-lookup"><span data-stu-id="616b1-163">Parent Elements</span></span>  
  
|<span data-ttu-id="616b1-164">요소</span><span class="sxs-lookup"><span data-stu-id="616b1-164">Element</span></span>|<span data-ttu-id="616b1-165">설명</span><span class="sxs-lookup"><span data-stu-id="616b1-165">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="616b1-166">\<bindings></span><span class="sxs-lookup"><span data-stu-id="616b1-166">\<bindings></span></span>](bindings.md)|<span data-ttu-id="616b1-167">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-167">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="616b1-168">설명</span><span class="sxs-lookup"><span data-stu-id="616b1-168">Remarks</span></span>  
 <span data-ttu-id="616b1-169">이 바인딩은 TCP를 통한 피어 전송을 사용하여 피어 투 피어 다자 간 애플리케이션을 만들 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-169">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="616b1-170">각 피어 노드는 이 바인딩 형식으로 정의된 여러 피어 채널을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-170">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="616b1-171">예제</span><span class="sxs-lookup"><span data-stu-id="616b1-171">Example</span></span>  
 <span data-ttu-id="616b1-172">다음 예제에서는 피어 채널을 사용하여 여러 상대방과의 통신을 제공하는 NetPeerTcpBinding binding 바인딩 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="616b1-172">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="616b1-173">이 바인딩을 사용 하는 자세한 시나리오는 [Net 피어 TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="616b1-173">For a detailed scenario of using this binding, see [Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
```xml  
<configuration>
  <system.ServiceModel>
    <bindings>
      <netPeerBinding>
        <binding closeTimeout="00:00:10"
                 openTimeout="00:00:20"
                 receiveTimeout="00:00:30"
                 sendTimeout="00:00:40"
                 maxBufferSize="1001"
                 maxConnections="123"
                 maxReceiveMessageSize="1000">
          <reliableSession ordered="false"
                           inactivityTimeout="00:02:00"
                           enabled="true" />
          <security mode="TransportWithMessageCredential">
            <message clientCredentialType="CardSpace" />
          </security>
        </binding>
      </netPeerBinding>
    </bindings>
  </system.ServiceModel>
</configuration>
```  
  
## <a name="see-also"></a><span data-ttu-id="616b1-174">참고자료</span><span class="sxs-lookup"><span data-stu-id="616b1-174">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="616b1-175">바인딩</span><span class="sxs-lookup"><span data-stu-id="616b1-175">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="616b1-176">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="616b1-176">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="616b1-177">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="616b1-177">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="616b1-178">\<binding></span><span class="sxs-lookup"><span data-stu-id="616b1-178">\<binding></span></span>](../../../misc/binding.md)
- <span data-ttu-id="616b1-179">[Net 피어 TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="616b1-179">[Net Peer TCP](https://docs.microsoft.com/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="616b1-180">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="616b1-180">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
