---
title: <netPeerTcpBinding>
ms.date: 03/30/2017
helpviewer_keywords:
- netPeerBinding element
ms.assetid: 2dd77ada-a176-47c7-a740-900b279f1aad
ms.openlocfilehash: 5fe221c5ec6c51afb199b2c66eab9d72cdfd750b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90556143"
---
# \<netPeerTcpBinding>
<span data-ttu-id="2f85d-101">피어 채널 전용 TCP 메시징의 바인딩을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-101">Defines a binding for peer channel specific TCP messaging.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<netPeerTcpBinding>**  
  
## <a name="syntax"></a><span data-ttu-id="2f85d-102">구문</span><span class="sxs-lookup"><span data-stu-id="2f85d-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2f85d-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2f85d-103">Attributes and Elements</span></span>  
 <span data-ttu-id="2f85d-104">다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-104">The following sections describe attributes, child elements, and parent elements</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2f85d-105">특성</span><span class="sxs-lookup"><span data-stu-id="2f85d-105">Attributes</span></span>  
  
|<span data-ttu-id="2f85d-106">attribute</span><span class="sxs-lookup"><span data-stu-id="2f85d-106">Attribute</span></span>|<span data-ttu-id="2f85d-107">Description</span><span class="sxs-lookup"><span data-stu-id="2f85d-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="2f85d-108">closeTimeout</span><span class="sxs-lookup"><span data-stu-id="2f85d-108">closeTimeout</span></span>|<span data-ttu-id="2f85d-109">닫기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-109">A <xref:System.TimeSpan> value that specifies the interval of time provided for a close operation to complete.</span></span> <span data-ttu-id="2f85d-110">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-110">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2f85d-111">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-111">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="2f85d-112">listenIPAddress</span><span class="sxs-lookup"><span data-stu-id="2f85d-112">listenIPAddress</span></span>|<span data-ttu-id="2f85d-113">피어 노드가 TCP 메시지를 수신하는 IP 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-113">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="2f85d-114">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-114">The default is `null`.</span></span>|  
|<span data-ttu-id="2f85d-115">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="2f85d-115">maxBufferPoolSize</span></span>|<span data-ttu-id="2f85d-116">이 바인딩의 최대 버퍼 풀 크기를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-116">An integer that specifies the maximum buffer pool size for this binding.</span></span> <span data-ttu-id="2f85d-117">기본값은 524,288바이트(512 \* 1024)입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-117">The default is 524,288 bytes (512 \* 1024).</span></span> <span data-ttu-id="2f85d-118">WCF(Windows Communication Foundation)의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-118">Many parts of Windows Communication Foundation (WCF) use buffers.</span></span> <span data-ttu-id="2f85d-119">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-119">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="2f85d-120">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-120">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="2f85d-121">따라서 버퍼를 만들고 제거하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-121">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="2f85d-122">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="2f85d-122">maxReceivedMessageSize</span></span>|<span data-ttu-id="2f85d-123">헤더를 비롯하여 이 바인딩으로 구성된 채널에서 받을 수 있는 최대 메시지 크기(바이트)를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-123">A positive integer that specifies the maximum message size, in bytes, including headers, that can be received on a channel configured with this binding.</span></span> <span data-ttu-id="2f85d-124">이 한도를 초과하는 메시지를 보낸 사람은 SOAP 오류를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-124">The sender of a message exceeding this limit will receive a SOAP fault.</span></span> <span data-ttu-id="2f85d-125">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-125">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="2f85d-126">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-126">The default is 65536.</span></span>|  
|<span data-ttu-id="2f85d-127">name</span><span class="sxs-lookup"><span data-stu-id="2f85d-127">name</span></span>|<span data-ttu-id="2f85d-128">바인딩의 구성 이름을 포함하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-128">A string that contains the configuration name of the binding.</span></span> <span data-ttu-id="2f85d-129">이 값은 바인딩의 ID로 사용되므로 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-129">This value should be unique because it is used as an identification for the binding.</span></span> <span data-ttu-id="2f85d-130">.NET Framework 4부터 바인딩과 동작은 이름을 가질 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-130">Starting with .NET Framework 4, bindings and behaviors are not required to have a name.</span></span> <span data-ttu-id="2f85d-131">기본 구성 및 이름이 없는 바인딩 및 동작에 대 한 자세한 내용은 [WCF 서비스에 대 한](../../../wcf/samples/simplified-configuration-for-wcf-services.md) [간소화 된 구성](../../../wcf/simplified-configuration.md) 및 단순화 된 구성을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2f85d-131">For more information about default configuration and nameless bindings and behaviors, see [Simplified Configuration](../../../wcf/simplified-configuration.md) and [Simplified Configuration for WCF Services](../../../wcf/samples/simplified-configuration-for-wcf-services.md).</span></span>|  
|<span data-ttu-id="2f85d-132">openTimeout</span><span class="sxs-lookup"><span data-stu-id="2f85d-132">openTimeout</span></span>|<span data-ttu-id="2f85d-133">열기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-133">A <xref:System.TimeSpan> value that specifies the interval of time provided for an open operation to complete.</span></span> <span data-ttu-id="2f85d-134">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-134">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2f85d-135">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-135">The default is 00:01:00.</span></span>|  
|<span data-ttu-id="2f85d-136">포트</span><span class="sxs-lookup"><span data-stu-id="2f85d-136">port</span></span>|<span data-ttu-id="2f85d-137">이 바인딩이 피어 채널 TCP 메시지를 처리할 네트워크 인터페이스 포트를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-137">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="2f85d-138">이 값은 <xref:System.Net.IPEndPoint.MinPort>와 <xref:System.Net.IPEndPoint.MaxPort> 사이의 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-138">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="2f85d-139">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-139">The default is 0.</span></span>|  
|<span data-ttu-id="2f85d-140">receiveTimeout</span><span class="sxs-lookup"><span data-stu-id="2f85d-140">receiveTimeout</span></span>|<span data-ttu-id="2f85d-141">받기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-141">A <xref:System.TimeSpan> value that specifies the interval of time provided for a receive operation to complete.</span></span> <span data-ttu-id="2f85d-142">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-142">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2f85d-143">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-143">The default is 00:10:00.</span></span>|  
|<span data-ttu-id="2f85d-144">sendTimeout</span><span class="sxs-lookup"><span data-stu-id="2f85d-144">sendTimeout</span></span>|<span data-ttu-id="2f85d-145">보내기 작업을 완료하기 위해 제공된 시간 간격을 지정하는 <xref:System.TimeSpan> 값입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-145">A <xref:System.TimeSpan> value that specifies the interval of time provided for a send operation to complete.</span></span> <span data-ttu-id="2f85d-146">이 값은 <xref:System.TimeSpan.Zero>보다 크거나 같아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-146">This value should be greater than or equal to <xref:System.TimeSpan.Zero>.</span></span> <span data-ttu-id="2f85d-147">기본값은 00:01:00입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-147">The default is 00:01:00.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2f85d-148">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2f85d-148">Child Elements</span></span>  
  
|<span data-ttu-id="2f85d-149">요소</span><span class="sxs-lookup"><span data-stu-id="2f85d-149">Element</span></span>|<span data-ttu-id="2f85d-150">Description</span><span class="sxs-lookup"><span data-stu-id="2f85d-150">Description</span></span>|  
|-------------|-----------------|  
|[\<readerQuotas>](/previous-versions/dotnet/netframework-4.0/ms731325(v=vs.100))|<span data-ttu-id="2f85d-151">이 바인딩으로 구성된 엔드포인트에서 처리할 수 있는 SOAP 메시지의 복잡성에 대한 제약 조건을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-151">Defines the constraints on the complexity of SOAP messages that can be processed by endpoints configured with this binding.</span></span> <span data-ttu-id="2f85d-152">이 요소는 <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-152">This element is of type <xref:System.ServiceModel.Configuration.XmlDictionaryReaderQuotasElement>.</span></span>|  
|[\<resolver>](resolver.md)|<span data-ttu-id="2f85d-153">피어 메시 내에서 노드의 엔드포인트 IP 주소에 대해 피어 메시 ID를 확인하기 위해 이 바인딩에서 사용하는 피어 확인자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-153">Specifies a peer resolver used by this binding to resolve a peer mesh ID to the endpoint IP addresses of nodes within the peer mesh.</span></span>|  
|[\<security>](security-of-netpeerbinding.md)|<span data-ttu-id="2f85d-154">메시지에 대한 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-154">Defines the security settings for the message.</span></span> <span data-ttu-id="2f85d-155">이 요소는 <xref:System.ServiceModel.Configuration.PeerSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-155">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2f85d-156">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2f85d-156">Parent Elements</span></span>  
  
|<span data-ttu-id="2f85d-157">요소</span><span class="sxs-lookup"><span data-stu-id="2f85d-157">Element</span></span>|<span data-ttu-id="2f85d-158">Description</span><span class="sxs-lookup"><span data-stu-id="2f85d-158">Description</span></span>|  
|-------------|-----------------|  
|[\<bindings>](bindings.md)|<span data-ttu-id="2f85d-159">이 요소는 표준 및 사용자 지정 바인딩의 컬렉션을 보유합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-159">This element holds a collection of standard and custom bindings.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2f85d-160">설명</span><span class="sxs-lookup"><span data-stu-id="2f85d-160">Remarks</span></span>  
 <span data-ttu-id="2f85d-161">이 바인딩은 TCP를 통한 피어 전송을 사용하여 피어 투 피어 다자 간 애플리케이션을 만들 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-161">This binding provides support for the creation of peer-to-peer or multiparty applications using peer transport over TCP.</span></span> <span data-ttu-id="2f85d-162">각 피어 노드는 이 바인딩 형식으로 정의된 여러 피어 채널을 호스트할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-162">Each peer node can host multiple peer channels defined with this binding type.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2f85d-163">예</span><span class="sxs-lookup"><span data-stu-id="2f85d-163">Example</span></span>  
 <span data-ttu-id="2f85d-164">다음 예제에서는 피어 채널을 사용하여 여러 상대방과의 통신을 제공하는 NetPeerTcpBinding binding 바인딩 사용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="2f85d-164">The following example demonstrates using the NetPeerTcpBinding binding, which provides multiparty communication using a peer channel.</span></span> <span data-ttu-id="2f85d-165">이 바인딩을 사용 하는 자세한 시나리오는 [Net 피어 TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))를 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="2f85d-165">For a detailed scenario of using this binding, see [Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90)).</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="2f85d-166">추가 정보</span><span class="sxs-lookup"><span data-stu-id="2f85d-166">See also</span></span>

- <xref:System.ServiceModel.NetPeerTcpBinding>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement>
- [<span data-ttu-id="2f85d-167">바인딩</span><span class="sxs-lookup"><span data-stu-id="2f85d-167">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="2f85d-168">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="2f85d-168">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="2f85d-169">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="2f85d-169">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
- <span data-ttu-id="2f85d-170">[Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2f85d-170">[Net Peer TCP](/previous-versions/dotnet/netframework-3.5/ms751426(v=vs.90))</span></span>
- [<span data-ttu-id="2f85d-171">피어 투 피어 네트워킹</span><span class="sxs-lookup"><span data-stu-id="2f85d-171">Peer-to-Peer Networking</span></span>](../../../wcf/feature-details/peer-to-peer-networking.md)
