---
title: <webSocketSettings>
ms.date: 03/30/2017
ms.assetid: bbf97e02-8dd1-4922-acac-3cd33397b249
ms.openlocfilehash: 6cfddfb9ebfc7c3447af977e14738baabebc8fe9
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91177853"
---
# \<webSocketSettings>

<span data-ttu-id="0d737-101">WebSocket 설정을 지정하는 데 사용되는 구성 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-101">A configuration element used to specify Web Socket settings.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netHttpBinding>**](nethttpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<webSocketSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="0d737-102">구문</span><span class="sxs-lookup"><span data-stu-id="0d737-102">Syntax</span></span>  
  
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
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0d737-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0d737-103">Attributes and Elements</span></span>  

 <span data-ttu-id="0d737-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0d737-105">특성</span><span class="sxs-lookup"><span data-stu-id="0d737-105">Attributes</span></span>  
  
|<span data-ttu-id="0d737-106">attribute</span><span class="sxs-lookup"><span data-stu-id="0d737-106">Attribute</span></span>|<span data-ttu-id="0d737-107">설명</span><span class="sxs-lookup"><span data-stu-id="0d737-107">Description</span></span>|  
|---------------|-----------------|  
|<span data-ttu-id="0d737-108">createNotificationOnConnection</span><span class="sxs-lookup"><span data-stu-id="0d737-108">createNotificationOnConnection</span></span>|<span data-ttu-id="0d737-109">연결 시 알림이 보내지는지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-109">Specifies whether a notification is sent upon connection.</span></span>|  
|<span data-ttu-id="0d737-110">disablePayloadMasking</span><span class="sxs-lookup"><span data-stu-id="0d737-110">disablePayloadMasking</span></span>|<span data-ttu-id="0d737-111">WebSocket 마스킹을 사용하지 않도록 설정할지 여부를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-111">Specifies whether Web Socket masking is disabled.</span></span>|  
|<span data-ttu-id="0d737-112">keepAliveInterval</span><span class="sxs-lookup"><span data-stu-id="0d737-112">keepAliveInterval</span></span>|<span data-ttu-id="0d737-113">상태 유지 간격을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-113">Specifies the keep alive interval.</span></span>|  
|<span data-ttu-id="0d737-114">maxPendingConnections</span><span class="sxs-lookup"><span data-stu-id="0d737-114">maxPendingConnections</span></span>|<span data-ttu-id="0d737-115">서비스에서 디스패치를 대기하는 최대 연결 수를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-115">Specifies the maximum number of connections awaiting dispatch on the service.</span></span>|  
|<span data-ttu-id="0d737-116">receiveBufferSize</span><span class="sxs-lookup"><span data-stu-id="0d737-116">receiveBufferSize</span></span>|<span data-ttu-id="0d737-117">수신 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-117">Specifies the size of the receive buffer.</span></span>|  
|<span data-ttu-id="0d737-118">sendBufferSize</span><span class="sxs-lookup"><span data-stu-id="0d737-118">sendBufferSize</span></span>|<span data-ttu-id="0d737-119">전송 버퍼의 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-119">Specifies the size of the send buffer.</span></span>|  
|<span data-ttu-id="0d737-120">subProtocol</span><span class="sxs-lookup"><span data-stu-id="0d737-120">subProtocol</span></span>|<span data-ttu-id="0d737-121">WebSocket 하위 프로토콜을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-121">Specifies the Web Socket subprotocol.</span></span>|  
|<span data-ttu-id="0d737-122">transportUsage</span><span class="sxs-lookup"><span data-stu-id="0d737-122">transportUsage</span></span>|<span data-ttu-id="0d737-123">WebSocket을 사용할 시기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-123">Specifies when to use Web Sockets.</span></span>|  
  
## <a name="transportusage-attribute"></a><span data-ttu-id="0d737-124">transportUsage 특성</span><span class="sxs-lookup"><span data-stu-id="0d737-124">transportUsage Attribute</span></span>  
  
|<span data-ttu-id="0d737-125">Value</span><span class="sxs-lookup"><span data-stu-id="0d737-125">Value</span></span>|<span data-ttu-id="0d737-126">설명</span><span class="sxs-lookup"><span data-stu-id="0d737-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="0d737-127">WhenDuplex</span><span class="sxs-lookup"><span data-stu-id="0d737-127">WhenDuplex</span></span>|<span data-ttu-id="0d737-128">이중 계약인 경우 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-128">Use the Web Socket protocol when the contract is duplex.</span></span>|  
|<span data-ttu-id="0d737-129">항상</span><span class="sxs-lookup"><span data-stu-id="0d737-129">Always</span></span>|<span data-ttu-id="0d737-130">계약과 관계없이 항상 WebSocket 프로토콜을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-130">Always use the Web Socket protocol regardless of the contract.</span></span>|  
|<span data-ttu-id="0d737-131">안 함</span><span class="sxs-lookup"><span data-stu-id="0d737-131">Never</span></span>|<span data-ttu-id="0d737-132">WebSocket 프로토콜을 사용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-132">Never use the Web Socket protocol.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0d737-133">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0d737-133">Child Elements</span></span>  

 <span data-ttu-id="0d737-134">없음</span><span class="sxs-lookup"><span data-stu-id="0d737-134">None</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="0d737-135">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0d737-135">Parent Elements</span></span>  
  
|<span data-ttu-id="0d737-136">요소</span><span class="sxs-lookup"><span data-stu-id="0d737-136">Element</span></span>|<span data-ttu-id="0d737-137">설명</span><span class="sxs-lookup"><span data-stu-id="0d737-137">Description</span></span>|  
|-------------|-----------------|  
|\<netHttpBinding>|<span data-ttu-id="0d737-138">NetHttpBinding을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-138">Specifies the NetHttpBinding</span></span>|  
  
## <a name="example"></a><span data-ttu-id="0d737-139">예제</span><span class="sxs-lookup"><span data-stu-id="0d737-139">Example</span></span>  

 <span data-ttu-id="0d737-140">다음 예제에서는 \<webSocketSettings> 요소를 사용하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="0d737-140">The following example shows how to use the \<webSocketSettings> element.</span></span>  
  
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
  
## <a name="see-also"></a><span data-ttu-id="0d737-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0d737-141">See also</span></span>

- <xref:System.ServiceModel.Channels.Binding>
- <xref:System.ServiceModel.Channels.BindingElement>
- <xref:System.ServiceModel.BasicHttpBinding>
- <xref:System.ServiceModel.Configuration.BasicHttpBindingElement>
- [<span data-ttu-id="0d737-142">바인딩하</span><span class="sxs-lookup"><span data-stu-id="0d737-142">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="0d737-143">시스템 제공 바인딩 구성</span><span class="sxs-lookup"><span data-stu-id="0d737-143">Configuring System-Provided Bindings</span></span>](../../../wcf/feature-details/configuring-system-provided-bindings.md)
- [<span data-ttu-id="0d737-144">바인딩을 사용하여 서비스 및 클라이언트 구성</span><span class="sxs-lookup"><span data-stu-id="0d737-144">Using Bindings to Configure Services and Clients</span></span>](../../../wcf/using-bindings-to-configure-services-and-clients.md)
- [\<binding>](bindings.md)
