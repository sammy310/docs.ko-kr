---
title: <peerTransport>
ms.date: 03/30/2017
ms.assetid: c1a5013a-9dd4-4a27-b114-795b8b323177
ms.openlocfilehash: 6765259f290047a4199a422b4ad0cced2ffee9ae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59179831"
---
# <a name="peertransport"></a><span data-ttu-id="02797-101">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="02797-101">\<peerTransport></span></span>
<span data-ttu-id="02797-102">사용자 지정 바인딩에 대한 피어 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="02797-102">Defines a peer transport for a custom binding.</span></span>  
  
 <span data-ttu-id="02797-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="02797-103">\<system.serviceModel></span></span>  
<span data-ttu-id="02797-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="02797-104">\<bindings></span></span>  
<span data-ttu-id="02797-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="02797-105">\<customBinding></span></span>  
<span data-ttu-id="02797-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="02797-106">\<binding></span></span>  
<span data-ttu-id="02797-107">\<peerTransport></span><span class="sxs-lookup"><span data-stu-id="02797-107">\<peerTransport></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02797-108">구문</span><span class="sxs-lookup"><span data-stu-id="02797-108">Syntax</span></span>  
  
```xml  
<peerTransport listenIpAddress="String"
               maxBufferPoolSize="Integer"
               maxReceivedMessageSize="Integer"
               port="Integer">
  <security>
  </security>
</peerTransport>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="02797-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="02797-109">Attributes and Elements</span></span>  
 <span data-ttu-id="02797-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="02797-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="02797-111">특성</span><span class="sxs-lookup"><span data-stu-id="02797-111">Attributes</span></span>  
  
|<span data-ttu-id="02797-112">특성</span><span class="sxs-lookup"><span data-stu-id="02797-112">Attribute</span></span>|<span data-ttu-id="02797-113">설명</span><span class="sxs-lookup"><span data-stu-id="02797-113">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="02797-114">listenIpAddress</span><span class="sxs-lookup"><span data-stu-id="02797-114">listenIpAddress</span></span>|<span data-ttu-id="02797-115">피어 노드가 TCP 메시지를 수신하는 IP 주소를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="02797-115">A string that specifies an IP address on which the peer node will listen for TCP messages.</span></span> <span data-ttu-id="02797-116">기본값은 `null`입니다.</span><span class="sxs-lookup"><span data-stu-id="02797-116">The default is `null`.</span></span>|  
|<span data-ttu-id="02797-117">maxBufferPoolSize</span><span class="sxs-lookup"><span data-stu-id="02797-117">maxBufferPoolSize</span></span>|<span data-ttu-id="02797-118">버퍼 풀의 최대 크기를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="02797-118">A positive integer that specifies the maximum size of the buffer pool.</span></span> <span data-ttu-id="02797-119">기본값은 524288입니다.</span><span class="sxs-lookup"><span data-stu-id="02797-119">The default is 524288.</span></span><br /><br /> <span data-ttu-id="02797-120">WCF의 많은 부분에서 버퍼를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="02797-120">Many parts of WCF use buffers.</span></span> <span data-ttu-id="02797-121">버퍼를 사용할 때마다 만들고 삭제하면 비용이 많이 들며, 버퍼에 대한 가비지 수집 역시 비용이 많이 듭니다.</span><span class="sxs-lookup"><span data-stu-id="02797-121">Creating and destroying buffers each time they are used is expensive, and garbage collection for buffers is also expensive.</span></span> <span data-ttu-id="02797-122">버퍼 풀이 있으면 이 풀로부터 버퍼를 가져와 사용한 다음 다시 풀로 반환할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02797-122">With buffer pools, you can take a buffer from the pool, use it, and return it to the pool once you are done.</span></span> <span data-ttu-id="02797-123">따라서 버퍼를 만들고 삭제하는 데 오버헤드를 피할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="02797-123">Thus the overhead in creating and destroying buffers is avoided.</span></span>|  
|<span data-ttu-id="02797-124">maxReceivedMessageSize</span><span class="sxs-lookup"><span data-stu-id="02797-124">maxReceivedMessageSize</span></span>|<span data-ttu-id="02797-125">헤더를 포함하는 최대 메시지 크기(바이트)를 정의하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="02797-125">A positive integer that defines the maximum message size in bytes including headers.</span></span> <span data-ttu-id="02797-126">수신자에게 너무 큰 메시지를 보내면 메시지의 발신자에게 SOAP 오류가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="02797-126">The sender of a message receives a SOAP fault when the message is too large for the receiver.</span></span> <span data-ttu-id="02797-127">수신자는 메시지를 삭제하고 추적 로그에 이벤트 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="02797-127">The receiver drops the message and creates an entry of the event in the trace log.</span></span> <span data-ttu-id="02797-128">기본값은 65536입니다.</span><span class="sxs-lookup"><span data-stu-id="02797-128">The default is 65536.</span></span>|  
|<span data-ttu-id="02797-129">포트</span><span class="sxs-lookup"><span data-stu-id="02797-129">port</span></span>|<span data-ttu-id="02797-130">이 바인딩이 피어 채널 TCP 메시지를 처리할 네트워크 인터페이스 포트를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="02797-130">An integer that specifies the network interface port on which this binding will process peer channel TCP messages.</span></span> <span data-ttu-id="02797-131">이 값은 <xref:System.Net.IPEndPoint.MinPort>와 <xref:System.Net.IPEndPoint.MaxPort> 사이의 값이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="02797-131">This value must be between <xref:System.Net.IPEndPoint.MinPort> and <xref:System.Net.IPEndPoint.MaxPort>.</span></span> <span data-ttu-id="02797-132">기본값은 0입니다.</span><span class="sxs-lookup"><span data-stu-id="02797-132">The default is 0.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="02797-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="02797-133">Child Elements</span></span>  
  
|<span data-ttu-id="02797-134">요소</span><span class="sxs-lookup"><span data-stu-id="02797-134">Element</span></span>|<span data-ttu-id="02797-135">설명</span><span class="sxs-lookup"><span data-stu-id="02797-135">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02797-136">\<security></span><span class="sxs-lookup"><span data-stu-id="02797-136">\<security></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/security-of-peertransport.md)|<span data-ttu-id="02797-137">이 전송의 보안 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="02797-137">Defines the security settings for this transport.</span></span> <span data-ttu-id="02797-138">이 요소는 <xref:System.ServiceModel.Configuration.PeerSecurityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="02797-138">This element is of type <xref:System.ServiceModel.Configuration.PeerSecurityElement>.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="02797-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="02797-139">Parent Elements</span></span>  
  
|<span data-ttu-id="02797-140">요소</span><span class="sxs-lookup"><span data-stu-id="02797-140">Element</span></span>|<span data-ttu-id="02797-141">설명</span><span class="sxs-lookup"><span data-stu-id="02797-141">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="02797-142">\<binding></span><span class="sxs-lookup"><span data-stu-id="02797-142">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="02797-143">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="02797-143">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="02797-144">설명</span><span class="sxs-lookup"><span data-stu-id="02797-144">Remarks</span></span>  
 <span data-ttu-id="02797-145">request/reply 작업이 있는 계약에서는 이 전송을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="02797-145">This transport cannot be used with contracts that have request/reply operations.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02797-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="02797-146">See also</span></span>

- <xref:System.ServiceModel.Configuration.PeerTransportElement>
- <xref:System.ServiceModel.Channels.PeerTransportBindingElement>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="02797-147">전송</span><span class="sxs-lookup"><span data-stu-id="02797-147">Transports</span></span>](../../../../../docs/framework/wcf/feature-details/transports.md)
- [<span data-ttu-id="02797-148">전송 선택</span><span class="sxs-lookup"><span data-stu-id="02797-148">Choosing a Transport</span></span>](../../../../../docs/framework/wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="02797-149">바인딩</span><span class="sxs-lookup"><span data-stu-id="02797-149">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="02797-150">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="02797-150">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="02797-151">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="02797-151">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="02797-152">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="02797-152">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
