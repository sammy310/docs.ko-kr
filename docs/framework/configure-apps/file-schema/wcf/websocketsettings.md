---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 5c9dbec13dd0d71ba1b92ea971d067540013b6f9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69940313"
---
# <a name="websocketsettings"></a><span data-ttu-id="d11f1-101">\<webSocketSettings></span><span class="sxs-lookup"><span data-stu-id="d11f1-101">\<webSocketSettings></span></span>
<span data-ttu-id="d11f1-102">WebSocket 설정을 지정하는 데 사용되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="d11f1-103">\<system.ServiceModel></span><span class="sxs-lookup"><span data-stu-id="d11f1-103">\<system.ServiceModel></span></span>  
<span data-ttu-id="d11f1-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="d11f1-104">\<bindings></span></span>  
<span data-ttu-id="d11f1-105">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d11f1-105">\<netHttpBinding></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d11f1-106">구문</span><span class="sxs-lookup"><span data-stu-id="d11f1-106">Syntax</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="Boolean"
                       disablePayloadMasking="Boolean"
                       keepAliveInterval="TimeSpan"
                       maxPendingConnections="Integer"
                       receiveBufferSize="Integer"
                       sendBufferSize="Integer"
                       subProtocol="String"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="d11f1-107">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="d11f1-107">Attributes and Elements</span></span>  
 <span data-ttu-id="d11f1-108">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-108">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="d11f1-109">특성</span><span class="sxs-lookup"><span data-stu-id="d11f1-109">Attributes</span></span>  
  
|<span data-ttu-id="d11f1-110">특성</span><span class="sxs-lookup"><span data-stu-id="d11f1-110">Attribute</span></span>|<span data-ttu-id="d11f1-111">설명</span><span class="sxs-lookup"><span data-stu-id="d11f1-111">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="d11f1-112">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="d11f1-112">createNotificationOnConnection</span></span>|<span data-ttu-id="d11f1-113">연결 시 알림이 보내지는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-113">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="d11f1-114">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="d11f1-114">disablePayloadMasking</span></span>|<span data-ttu-id="d11f1-115">WebSocket 마스킹을 사용하지 않도록 설정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-115">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="d11f1-116">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="d11f1-116">keepAliveInterval</span></span>|<span data-ttu-id="d11f1-117">상태 유지 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-117">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="d11f1-118">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="d11f1-118">maxPendingConnections</span></span>|<span data-ttu-id="d11f1-119">서비스에서 디스패치를 대기하는 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-119">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="d11f1-120">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="d11f1-120">receiveBufferSize</span></span>|<span data-ttu-id="d11f1-121">수신 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-121">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="d11f1-122">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="d11f1-122">sendBufferSize</span></span>|<span data-ttu-id="d11f1-123">전송 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-123">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="d11f1-124">subProtocol</span><span class="sxs-lookup"><span data-stu-id="d11f1-124">subProtocol</span></span>|<span data-ttu-id="d11f1-125">WebSocket 하위 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-125">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="d11f1-126">transportUsage</span><span class="sxs-lookup"><span data-stu-id="d11f1-126">transportUsage</span></span>|<span data-ttu-id="d11f1-127">WebSocket을 사용할 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-127">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="d11f1-128">transportUsage 특성</span><span class="sxs-lookup"><span data-stu-id="d11f1-128">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="d11f1-129">값</span><span class="sxs-lookup"><span data-stu-id="d11f1-129">Value</span></span>|<span data-ttu-id="d11f1-130">설명</span><span class="sxs-lookup"><span data-stu-id="d11f1-130">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="d11f1-131">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="d11f1-131">WhenDuplex</span></span>|<span data-ttu-id="d11f1-132">이중 계약인 경우 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-132">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="d11f1-133">항상</span><span class="sxs-lookup"><span data-stu-id="d11f1-133">Always</span></span>|<span data-ttu-id="d11f1-134">계약과 관계없이 항상 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-134">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="d11f1-135">Never</span><span class="sxs-lookup"><span data-stu-id="d11f1-135">Never</span></span>|<span data-ttu-id="d11f1-136">WebSocket 프로토콜을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-136">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="d11f1-137">자식 요소</span><span class="sxs-lookup"><span data-stu-id="d11f1-137">Child Elements</span></span>  
 <span data-ttu-id="d11f1-138">없음</span><span class="sxs-lookup"><span data-stu-id="d11f1-138">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="d11f1-139">부모 요소</span><span class="sxs-lookup"><span data-stu-id="d11f1-139">Parent Elements</span></span>  
  
|<span data-ttu-id="d11f1-140">요소</span><span class="sxs-lookup"><span data-stu-id="d11f1-140">Element</span></span>|<span data-ttu-id="d11f1-141">Description</span><span class="sxs-lookup"><span data-stu-id="d11f1-141">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d11f1-142">\<netHttpBinding></span><span class="sxs-lookup"><span data-stu-id="d11f1-142">\<netHttpBinding></span></span>|<span data-ttu-id="d11f1-143">NetHttpBinding을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-143">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d11f1-144">예제</span><span class="sxs-lookup"><span data-stu-id="d11f1-144">Example</span></span>  
 <span data-ttu-id="d11f1-145">다음 예제에서는 \<webSocketSettings > 요소를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="d11f1-145">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
```xml  
<netHttpBinding>
  <binding>
    <webSocketSettings createNotificationOnConnection="true"
                       disablePayloadMasking="false"
                       keepAliveInterval="00:10:00"
                       maxPendingConnections="100"
                       receiveBufferSize="1000"
                       sendBufferSize="1000"
                       subProtocol="Soap"
                       transportUsage="WhenDuplex/Always/Never" />
  </binding>
</netHttpBinding>
```  
  
## <a name="see-also"></a><span data-ttu-id="d11f1-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="d11f1-146">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="d11f1-147">바인딩</span><span class="sxs-lookup"><span data-stu-id="d11f1-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="d11f1-148">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="d11f1-148">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="d11f1-149">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="d11f1-149">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="d11f1-150">\<binding></span><span class="sxs-lookup"><span data-stu-id="d11f1-150">\<binding></span></span>](../../../misc/binding.md)
