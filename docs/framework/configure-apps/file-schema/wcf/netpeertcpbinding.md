---
description: 다음에 대해 자세히 알아보세요. <netPeerTcpBinding>
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 11f1618236c7219143225e2535e272254af6b81d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99683907"
---
# \<netPeerTcpBinding>

<span data-ttu-id="def3a-102">피어 채널 전용 TCP 메시징의 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-102">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netPeerTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="def3a-103">구문</span><span class="sxs-lookup"><span data-stu-id="def3a-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="def3a-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="def3a-104">Attributes and Elements</span></span>  

 <span data-ttu-id="def3a-105">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-105">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="def3a-106">특성</span><span class="sxs-lookup"><span data-stu-id="def3a-106">Attributes</span></span>  
  
|<span data-ttu-id="def3a-107">attribute</span><span class="sxs-lookup"><span data-stu-id="def3a-107">Attribute</span></span>|<span data-ttu-id="def3a-108">설명</span><span class="sxs-lookup"><span data-stu-id="def3a-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="def3a-109">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="def3a-109">closeTimeout</span></span>|<span data-ttu-id="def3a-110">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-110">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="def3a-111">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-111">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="def3a-112">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-112">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="def3a-113">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="def3a-113">listenIPAddress</span></span>|<span data-ttu-id="def3a-114">피어 노드가 TCP 메시지를 수신하는 IP 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-114">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="def3a-115">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-115">The default is `null`.</span></span>|  
|<span data-ttu-id="def3a-116">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="def3a-116">maxBufferPoolSize</span></span>|<span data-ttu-id="def3a-117">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-117">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="def3a-118">기본값은 524,288바이트(512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-118">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="def3a-119">WCF(Windows Communication Foundation)의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-119">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="def3a-120">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-120">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="def3a-121">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-121">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="def3a-122">따라서 버퍼를 만들고 제거하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-122">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="def3a-123">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="def3a-123">maxReceivedMessageSize</span></span>|<span data-ttu-id="def3a-124">헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-124">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="def3a-125">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-125">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="def3a-126">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-126">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="def3a-127">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-127">The default is 65536.</span></span>|  
|<span data-ttu-id="def3a-128">name</span><span class="sxs-lookup"><span data-stu-id="def3a-128">name</span></span>|<span data-ttu-id="def3a-129">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-129">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="def3a-130">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-130">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="def3a-131">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-131">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="def3a-132">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="def3a-132">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="def3a-133">openTimeout</span><span class="sxs-lookup"><span data-stu-id="def3a-133">openTimeout</span></span>|<span data-ttu-id="def3a-134">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-134">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="def3a-135">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-135">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="def3a-136">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-136">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="def3a-137">포트</span><span class="sxs-lookup"><span data-stu-id="def3a-137">port</span></span>|<span data-ttu-id="def3a-138">이 바인딩이 피어 채널 TCP 메시지를 처리할 네트워크 인터페이스 포트를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-138">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="def3a-139">이 값은 <xref:System.Net.IPEndPoint.MinPort>와 <xref:System.Net.IPEndPoint.MaxPort> 사이의 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-139">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="def3a-140">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-140">The default is 0.</span></span>|  
|<span data-ttu-id="def3a-141">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="def3a-141">receiveTimeout</span></span>|<span data-ttu-id="def3a-142">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-142">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="def3a-143">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-143">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="def3a-144">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-144">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="def3a-145">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="def3a-145">sendTimeout</span></span>|<span data-ttu-id="def3a-146">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-146">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="def3a-147">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-147">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="def3a-148">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-148">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="def3a-149">자식 요소</span><span class="sxs-lookup"><span data-stu-id="def3a-149">Child Elements</span></span>  
  
|<span data-ttu-id="def3a-150">요소</span><span class="sxs-lookup"><span data-stu-id="def3a-150">Element</span></span>|<span data-ttu-id="def3a-151">설명</span><span class="sxs-lookup"><span data-stu-id="def3a-151">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="def3a-152">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-152">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="def3a-153">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-153">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<resolver>](resolver.md)|<span data-ttu-id="def3a-154">피어 메시 내에서 노드의 엔드포인트 IP 주소에 대해 피어 메시 ID를 확인하기 위해 이 바인딩에서 사용하는 피어 확인자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-154">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="def3a-155">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-155">Defines the security settings for the message.</span></span> <span data-ttu-id="def3a-156">이 요소는 <xref:System.ServiceModel.Configuration.PeerSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-156">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="def3a-157">부모 요소</span><span class="sxs-lookup"><span data-stu-id="def3a-157">Parent Elements</span></span>  
  
|<span data-ttu-id="def3a-158">요소</span><span class="sxs-lookup"><span data-stu-id="def3a-158">Element</span></span>|<span data-ttu-id="def3a-159">설명</span><span class="sxs-lookup"><span data-stu-id="def3a-159">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="def3a-160">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-160">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="def3a-161">설명</span><span class="sxs-lookup"><span data-stu-id="def3a-161">Remarks</span></span>  

 <span data-ttu-id="def3a-162">이 바인딩은 TCP를 통한 피어 전송을 사용하여 피어 투 피어 다자 간 애플리케이션을 만들 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-162">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="def3a-163">각 피어 노드는 이 바인딩 형식으로 정의된 여러 피어 채널을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-163">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="def3a-164">예제</span><span class="sxs-lookup"><span data-stu-id="def3a-164">Example</span></span>  

 <span data-ttu-id="def3a-165">다음 예제에서는 피어 채널을 사용하여 여러 상대방과의 통신을 제공하는 NetPeerTcpBinding binding 바인딩 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="def3a-165">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="def3a-166">이 바인딩을 사용 하는 자세한 시나리오는 [Net 피어 TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="def3a-166">For a detailed scenario of using this binding, see [Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="def3a-167">참고 항목</span><span class="sxs-lookup"><span data-stu-id="def3a-167">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="def3a-168">바인딩</span><span class="sxs-lookup"><span data-stu-id="def3a-168">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="def3a-169">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="def3a-169">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="def3a-170">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="def3a-170">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- <span data-ttu-id="def3a-171">[Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="def3a-171">[Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="def3a-172">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="def3a-172">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
