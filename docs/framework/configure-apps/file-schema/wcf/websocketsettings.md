---
description: 다음에 대해 자세히 알아보세요. <webSocketSettings>
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: a0b67a0088491c73ed0214191283ae5292a654b0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99682490"
---
# \<webSocketSettings>

<span data-ttu-id="fed49-102">WebSocket 설정을 지정하는 데 사용되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-102">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="fed49-103">구문</span><span class="sxs-lookup"><span data-stu-id="fed49-103">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="fed49-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="fed49-104">Attributes and Elements</span></span>  

 <span data-ttu-id="fed49-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="fed49-106">특성</span><span class="sxs-lookup"><span data-stu-id="fed49-106">Attributes</span></span>  
  
|<span data-ttu-id="fed49-107">attribute</span><span class="sxs-lookup"><span data-stu-id="fed49-107">Attribute</span></span>|<span data-ttu-id="fed49-108">설명</span><span class="sxs-lookup"><span data-stu-id="fed49-108">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="fed49-109">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="fed49-109">createNotificationOnConnection</span></span>|<span data-ttu-id="fed49-110">연결 시 알림이 보내지는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-110">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="fed49-111">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="fed49-111">disablePayloadMasking</span></span>|<span data-ttu-id="fed49-112">WebSocket 마스킹을 사용하지 않도록 설정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-112">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="fed49-113">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="fed49-113">keepAliveInterval</span></span>|<span data-ttu-id="fed49-114">상태 유지 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-114">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="fed49-115">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="fed49-115">maxPendingConnections</span></span>|<span data-ttu-id="fed49-116">서비스에서 디스패치를 대기하는 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-116">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="fed49-117">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="fed49-117">receiveBufferSize</span></span>|<span data-ttu-id="fed49-118">수신 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-118">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="fed49-119">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="fed49-119">sendBufferSize</span></span>|<span data-ttu-id="fed49-120">전송 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-120">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="fed49-121">subProtocol</span><span class="sxs-lookup"><span data-stu-id="fed49-121">subProtocol</span></span>|<span data-ttu-id="fed49-122">WebSocket 하위 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-122">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="fed49-123">transportUsage</span><span class="sxs-lookup"><span data-stu-id="fed49-123">transportUsage</span></span>|<span data-ttu-id="fed49-124">WebSocket을 사용할 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-124">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="fed49-125">transportUsage 특성</span><span class="sxs-lookup"><span data-stu-id="fed49-125">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="fed49-126">값</span><span class="sxs-lookup"><span data-stu-id="fed49-126">Value</span></span>|<span data-ttu-id="fed49-127">설명</span><span class="sxs-lookup"><span data-stu-id="fed49-127">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="fed49-128">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="fed49-128">WhenDuplex</span></span>|<span data-ttu-id="fed49-129">이중 계약인 경우 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-129">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="fed49-130">항상</span><span class="sxs-lookup"><span data-stu-id="fed49-130">Always</span></span>|<span data-ttu-id="fed49-131">계약과 관계없이 항상 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-131">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="fed49-132">안 함</span><span class="sxs-lookup"><span data-stu-id="fed49-132">Never</span></span>|<span data-ttu-id="fed49-133">WebSocket 프로토콜을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-133">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="fed49-134">자식 요소</span><span class="sxs-lookup"><span data-stu-id="fed49-134">Child Elements</span></span>  

 <span data-ttu-id="fed49-135">없음</span><span class="sxs-lookup"><span data-stu-id="fed49-135">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="fed49-136">부모 요소</span><span class="sxs-lookup"><span data-stu-id="fed49-136">Parent Elements</span></span>  
  
|<span data-ttu-id="fed49-137">요소</span><span class="sxs-lookup"><span data-stu-id="fed49-137">Element</span></span>|<span data-ttu-id="fed49-138">설명</span><span class="sxs-lookup"><span data-stu-id="fed49-138">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="fed49-139">NetHttpBinding을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-139">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="fed49-140">예제</span><span class="sxs-lookup"><span data-stu-id="fed49-140">Example</span></span>  

 <span data-ttu-id="fed49-141">다음 예제에서는 \<webSocketSettings> 요소를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="fed49-141">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="fed49-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fed49-142">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="fed49-143">바인딩</span><span class="sxs-lookup"><span data-stu-id="fed49-143">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="fed49-144">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="fed49-144">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="fed49-145">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="fed49-145">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
