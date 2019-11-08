---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73732559"
---
# <a name="websocketsettings"></a><span data-ttu-id="7b778-101">\<webSocketSettings ></span><span class="sxs-lookup"><span data-stu-id="7b778-101">\<webSocketSettings></span></span>
<span data-ttu-id="7b778-102">WebSocket 설정을 지정하는 데 사용되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-102">A configuration element used to specify Web Socket settings.</span></span>  
  
<span data-ttu-id="7b778-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="7b778-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="7b778-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="7b778-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="7b778-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="7b778-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="7b778-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netHttpBinding >** ](nethttpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="7b778-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)</span></span>\
<span data-ttu-id="7b778-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="7b778-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="7b778-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**webSocketSettings >**</span><span class="sxs-lookup"><span data-stu-id="7b778-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7b778-109">구문</span><span class="sxs-lookup"><span data-stu-id="7b778-109">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="7b778-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="7b778-110">Attributes and Elements</span></span>  
 <span data-ttu-id="7b778-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="7b778-112">특성</span><span class="sxs-lookup"><span data-stu-id="7b778-112">Attributes</span></span>  
  
|<span data-ttu-id="7b778-113">특성</span><span class="sxs-lookup"><span data-stu-id="7b778-113">Attribute</span></span>|<span data-ttu-id="7b778-114">설명</span><span class="sxs-lookup"><span data-stu-id="7b778-114">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="7b778-115">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="7b778-115">createNotificationOnConnection</span></span>|<span data-ttu-id="7b778-116">연결 시 알림이 보내지는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-116">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="7b778-117">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="7b778-117">disablePayloadMasking</span></span>|<span data-ttu-id="7b778-118">WebSocket 마스킹을 사용하지 않도록 설정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-118">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="7b778-119">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="7b778-119">keepAliveInterval</span></span>|<span data-ttu-id="7b778-120">상태 유지 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-120">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="7b778-121">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="7b778-121">maxPendingConnections</span></span>|<span data-ttu-id="7b778-122">서비스에서 디스패치를 대기하는 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-122">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="7b778-123">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="7b778-123">receiveBufferSize</span></span>|<span data-ttu-id="7b778-124">수신 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-124">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="7b778-125">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="7b778-125">sendBufferSize</span></span>|<span data-ttu-id="7b778-126">전송 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-126">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="7b778-127">subProtocol</span><span class="sxs-lookup"><span data-stu-id="7b778-127">subProtocol</span></span>|<span data-ttu-id="7b778-128">WebSocket 하위 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-128">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="7b778-129">transportUsage</span><span class="sxs-lookup"><span data-stu-id="7b778-129">transportUsage</span></span>|<span data-ttu-id="7b778-130">WebSocket을 사용할 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-130">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="7b778-131">transportUsage 특성</span><span class="sxs-lookup"><span data-stu-id="7b778-131">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="7b778-132">값</span><span class="sxs-lookup"><span data-stu-id="7b778-132">Value</span></span>|<span data-ttu-id="7b778-133">설명</span><span class="sxs-lookup"><span data-stu-id="7b778-133">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="7b778-134">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="7b778-134">WhenDuplex</span></span>|<span data-ttu-id="7b778-135">이중 계약인 경우 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-135">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="7b778-136">항상</span><span class="sxs-lookup"><span data-stu-id="7b778-136">Always</span></span>|<span data-ttu-id="7b778-137">계약과 관계없이 항상 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-137">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="7b778-138">Never</span><span class="sxs-lookup"><span data-stu-id="7b778-138">Never</span></span>|<span data-ttu-id="7b778-139">WebSocket 프로토콜을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-139">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="7b778-140">자식 요소</span><span class="sxs-lookup"><span data-stu-id="7b778-140">Child Elements</span></span>  
 <span data-ttu-id="7b778-141">없음</span><span class="sxs-lookup"><span data-stu-id="7b778-141">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="7b778-142">부모 요소</span><span class="sxs-lookup"><span data-stu-id="7b778-142">Parent Elements</span></span>  
  
|<span data-ttu-id="7b778-143">요소</span><span class="sxs-lookup"><span data-stu-id="7b778-143">Element</span></span>|<span data-ttu-id="7b778-144">설명</span><span class="sxs-lookup"><span data-stu-id="7b778-144">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="7b778-145">\<netHttpBinding ></span><span class="sxs-lookup"><span data-stu-id="7b778-145">\<netHttpBinding></span></span>|<span data-ttu-id="7b778-146">NetHttpBinding을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-146">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="7b778-147">예제</span><span class="sxs-lookup"><span data-stu-id="7b778-147">Example</span></span>  
 <span data-ttu-id="7b778-148">다음 예제에서는 \<webSocketSettings > 요소를 사용 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7b778-148">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="7b778-149">참조</span><span class="sxs-lookup"><span data-stu-id="7b778-149">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="7b778-150">바인딩</span><span class="sxs-lookup"><span data-stu-id="7b778-150">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="7b778-151">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="7b778-151">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="7b778-152">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="7b778-152">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [<span data-ttu-id="7b778-153">\<binding ></span><span class="sxs-lookup"><span data-stu-id="7b778-153">\<binding></span></span>](bindings.md)
