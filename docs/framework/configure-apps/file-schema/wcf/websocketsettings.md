---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: fa87a1b0961425d6a9bc84769bef6e87cbc2ce96
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73732559"
---
# \<webSocketSettings>
<span data-ttu-id="5367f-101">WebSocket 설정을 지정하는 데 사용되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="5367f-102">구문</span><span class="sxs-lookup"><span data-stu-id="5367f-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5367f-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5367f-103">Attributes and Elements</span></span>  
 <span data-ttu-id="5367f-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5367f-105">특성</span><span class="sxs-lookup"><span data-stu-id="5367f-105">Attributes</span></span>  
  
|<span data-ttu-id="5367f-106">attribute</span><span class="sxs-lookup"><span data-stu-id="5367f-106">Attribute</span></span>|<span data-ttu-id="5367f-107">Description</span><span class="sxs-lookup"><span data-stu-id="5367f-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="5367f-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="5367f-108">createNotificationOnConnection</span></span>|<span data-ttu-id="5367f-109">연결 시 알림이 보내지는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="5367f-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="5367f-110">disablePayloadMasking</span></span>|<span data-ttu-id="5367f-111">WebSocket 마스킹을 사용하지 않도록 설정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="5367f-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="5367f-112">keepAliveInterval</span></span>|<span data-ttu-id="5367f-113">상태 유지 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="5367f-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="5367f-114">maxPendingConnections</span></span>|<span data-ttu-id="5367f-115">서비스에서 디스패치를 대기하는 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="5367f-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="5367f-116">receiveBufferSize</span></span>|<span data-ttu-id="5367f-117">수신 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="5367f-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="5367f-118">sendBufferSize</span></span>|<span data-ttu-id="5367f-119">전송 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="5367f-120">subProtocol</span><span class="sxs-lookup"><span data-stu-id="5367f-120">subProtocol</span></span>|<span data-ttu-id="5367f-121">WebSocket 하위 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="5367f-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="5367f-122">transportUsage</span></span>|<span data-ttu-id="5367f-123">WebSocket을 사용할 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="5367f-124">transportUsage 특성</span><span class="sxs-lookup"><span data-stu-id="5367f-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="5367f-125">값</span><span class="sxs-lookup"><span data-stu-id="5367f-125">Value</span></span>|<span data-ttu-id="5367f-126">Description</span><span class="sxs-lookup"><span data-stu-id="5367f-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="5367f-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="5367f-127">WhenDuplex</span></span>|<span data-ttu-id="5367f-128">이중 계약인 경우 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="5367f-129">항상</span><span class="sxs-lookup"><span data-stu-id="5367f-129">Always</span></span>|<span data-ttu-id="5367f-130">계약과 관계없이 항상 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="5367f-131">안 함</span><span class="sxs-lookup"><span data-stu-id="5367f-131">Never</span></span>|<span data-ttu-id="5367f-132">WebSocket 프로토콜을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5367f-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5367f-133">Child Elements</span></span>  
 <span data-ttu-id="5367f-134">None</span><span class="sxs-lookup"><span data-stu-id="5367f-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5367f-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5367f-135">Parent Elements</span></span>  
  
|<span data-ttu-id="5367f-136">요소</span><span class="sxs-lookup"><span data-stu-id="5367f-136">Element</span></span>|<span data-ttu-id="5367f-137">Description</span><span class="sxs-lookup"><span data-stu-id="5367f-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="5367f-138">NetHttpBinding을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="5367f-139">예제</span><span class="sxs-lookup"><span data-stu-id="5367f-139">Example</span></span>  
 <span data-ttu-id="5367f-140">다음 예제에서는 \<webSocketSettings> 요소를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="5367f-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="5367f-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="5367f-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="5367f-142">바인딩</span><span class="sxs-lookup"><span data-stu-id="5367f-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5367f-143">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="5367f-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="5367f-144">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="5367f-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
