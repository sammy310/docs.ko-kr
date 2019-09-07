---
title: <connectionPoolSettings>
ms.date: 03/30/2017
ms.assetid: 6fa7fa65-2c6e-4eab-b8cf-7690112c0be5
ms.openlocfilehash: 842173c7bd9673a1e08c93d5ed650a42b9d979e5
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400477"
---
# <a name="connectionpoolsettings"></a><span data-ttu-id="6e690-101">\<connectionPoolSettings></span><span class="sxs-lookup"><span data-stu-id="6e690-101">\<connectionPoolSettings></span></span>
<span data-ttu-id="6e690-102">명명된 파이프 바인딩의 추가 연결 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-102">Specifies additional connection pool settings for a Named Pipe binding.</span></span>  
  
<span data-ttu-id="6e690-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="6e690-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="6e690-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="6e690-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="6e690-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="6e690-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="6e690-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="6e690-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="6e690-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="6e690-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="6e690-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<namedPipeTransport >** ](namedpipetransport.md)</span><span class="sxs-lookup"><span data-stu-id="6e690-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<namedPipeTransport>**](namedpipetransport.md)</span></span>\
<span data-ttu-id="6e690-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<connectionPoolSettings >**</span><span class="sxs-lookup"><span data-stu-id="6e690-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<connectionPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6e690-110">구문</span><span class="sxs-lookup"><span data-stu-id="6e690-110">Syntax</span></span>  
  
```xml  
<connectionPoolSettings groupName="String"
                        idleTimeout="TimeSpan"
                        maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="6e690-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="6e690-111">Attributes and Elements</span></span>  
 <span data-ttu-id="6e690-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="6e690-113">특성</span><span class="sxs-lookup"><span data-stu-id="6e690-113">Attributes</span></span>  
  
|<span data-ttu-id="6e690-114">특성</span><span class="sxs-lookup"><span data-stu-id="6e690-114">Attribute</span></span>|<span data-ttu-id="6e690-115">설명</span><span class="sxs-lookup"><span data-stu-id="6e690-115">Description</span></span>|  
|---------------|-----------------|  
|`groupName`|<span data-ttu-id="6e690-116">나가는 채널에 사용되는 연결 풀의 이름을 정의하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-116">A string that defines the name of the connection pool used for outgoing channels.</span></span> <span data-ttu-id="6e690-117">스트리밍 모드에서는 연결이 공유되지 않습니다. 즉 연결 풀링이 사용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-117">In streamed mode, connections are not shared, meaning that connection pooling is disabled.</span></span> <span data-ttu-id="6e690-118">기본값은 "default" 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-118">The default is a "default" string.</span></span> <span data-ttu-id="6e690-119">이 값을 수정하여 특정 클라이언트의 연결을 별도의 그룹으로 격리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-119">You can modify this value to isolate the connections for a particular client into separate groups.</span></span>|  
|`idleTimeout`|<span data-ttu-id="6e690-120">연결이 끊어지기 전에 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-120">A positive <xref:System.TimeSpan> that specifies the maximum time the connection can be idle before being disconnected.</span></span> <span data-ttu-id="6e690-121">기본값은 00:02:00입니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-121">The default is 00:02:00.</span></span>|  
|`maxOutboundConnectionsPerEndpoint`|<span data-ttu-id="6e690-122">서비스에서 시작된 원격 엔드포인트와의 최대 연결 수를 지정하는 양의 정수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-122">A positive integer that specifies the maximum number of connections to a remote endpoint initiated by the service.</span></span> <span data-ttu-id="6e690-123">이 제한을 초과하는 연결은 채널 수가 제한 아래로 내려갈 때까지 큐에 대기됩니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-123">Connections in excess of the limit are queued until a space below the limit becomes available.</span></span> <span data-ttu-id="6e690-124">`idleTimeout`은 예외가 throw되기 전에 연결이 큐에 대기할 수 있는 시간을 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-124">The `idleTimeout` limits the duration in which connections remain queued before an exception is thrown.</span></span> <span data-ttu-id="6e690-125">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-125">The default is 10.</span></span><br /><br /> <span data-ttu-id="6e690-126">이 특성은 클라이언트에서 특정 서비스 엔드포인트로의 동시 활성 연결 수를 제한합니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-126">This attribute limits the number of simultaneous active connections from the client to a particular service endpoint.</span></span> <span data-ttu-id="6e690-127">활성 클라이언트 연결 수가 이 값을 초과할 경우 해당 서비스가 클라이언트에 응답하지 않는 것처럼 보일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-127">If this value is exceeded by having more active client connections, the service may appear unresponsive to the client.</span></span> <span data-ttu-id="6e690-128">이러한 경우 이 값을 특정 엔드포인트에 대해 예상되는 동시 클라이언트 최대 연결 수보다 크게 조정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-128">In this case, this value should be adjusted to exceed the maximum number of expected simultaneous client connections to a specific endpoint.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="6e690-129">자식 요소</span><span class="sxs-lookup"><span data-stu-id="6e690-129">Child Elements</span></span>  
 <span data-ttu-id="6e690-130">없음</span><span class="sxs-lookup"><span data-stu-id="6e690-130">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="6e690-131">부모 요소</span><span class="sxs-lookup"><span data-stu-id="6e690-131">Parent Elements</span></span>  
  
|<span data-ttu-id="6e690-132">요소</span><span class="sxs-lookup"><span data-stu-id="6e690-132">Element</span></span>|<span data-ttu-id="6e690-133">Description</span><span class="sxs-lookup"><span data-stu-id="6e690-133">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="6e690-134">\<namedPipeTransport></span><span class="sxs-lookup"><span data-stu-id="6e690-134">\<namedPipeTransport></span></span>](namedpipetransport.md)|<span data-ttu-id="6e690-135">채널이 명명된 파이프를 사용하여 메시지를 전송하게 하는 전송을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="6e690-135">Defines a transport that causes a channel to transfer messages using named pipes.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="6e690-136">참고자료</span><span class="sxs-lookup"><span data-stu-id="6e690-136">See also</span></span>

- <xref:System.ServiceModel.Configuration.NamedPipeConnectionPoolSettingsElement>
- <xref:System.ServiceModel.Channels.NamedPipeTransportBindingElement.ConnectionPoolSettings%2A>
- <xref:System.ServiceModel.Channels.NamedPipeConnectionPoolSettings>
- <xref:System.ServiceModel.Channels.TransportBindingElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="6e690-137">전송</span><span class="sxs-lookup"><span data-stu-id="6e690-137">Transports</span></span>](../../../wcf/feature-details/transports.md)
- [<span data-ttu-id="6e690-138">전송 선택</span><span class="sxs-lookup"><span data-stu-id="6e690-138">Choosing a Transport</span></span>](../../../wcf/feature-details/choosing-a-transport.md)
- [<span data-ttu-id="6e690-139">바인딩</span><span class="sxs-lookup"><span data-stu-id="6e690-139">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="6e690-140">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="6e690-140">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="6e690-141">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="6e690-141">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="6e690-142">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="6e690-142">\<customBinding></span></span>](custombinding.md)
