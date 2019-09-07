---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 26537980a6be5c0fe12661d93a6ba5fe862ceb4e
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70398167"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="de962-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="de962-101">\<channelPoolSettings></span></span>
<span data-ttu-id="de962-102">사용자 지정 바인딩의 채널 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
<span data-ttu-id="de962-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="de962-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="de962-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="de962-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="de962-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="de962-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="de962-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="de962-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="de962-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="de962-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="de962-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<oneWay >** ](oneway.md)</span><span class="sxs-lookup"><span data-stu-id="de962-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)</span></span>\
<span data-ttu-id="de962-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<channelPoolSettings >**</span><span class="sxs-lookup"><span data-stu-id="de962-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de962-110">구문</span><span class="sxs-lookup"><span data-stu-id="de962-110">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="de962-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="de962-111">Attributes and Elements</span></span>  
 <span data-ttu-id="de962-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="de962-113">특성</span><span class="sxs-lookup"><span data-stu-id="de962-113">Attributes</span></span>  
  
|<span data-ttu-id="de962-114">특성</span><span class="sxs-lookup"><span data-stu-id="de962-114">Attribute</span></span>|<span data-ttu-id="de962-115">설명</span><span class="sxs-lookup"><span data-stu-id="de962-115">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="de962-116">연결이 끊어지기 전에 풀의 채널이 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="de962-116">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="de962-117">기본값은 00:02:00입니다.</span><span class="sxs-lookup"><span data-stu-id="de962-117">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="de962-118">채널이 풀에 반환될 때 해당 기간이 경과하면 채널이 닫히는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="de962-118">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="de962-119">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="de962-119">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="de962-120">각 원격 엔드포인트에 대해 풀에 저장할 수 있는 최대 채널 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="de962-120">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="de962-121">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="de962-121">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="de962-122">자식 요소</span><span class="sxs-lookup"><span data-stu-id="de962-122">Child Elements</span></span>  
 <span data-ttu-id="de962-123">없음</span><span class="sxs-lookup"><span data-stu-id="de962-123">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="de962-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="de962-124">Parent Elements</span></span>  
  
|<span data-ttu-id="de962-125">요소</span><span class="sxs-lookup"><span data-stu-id="de962-125">Element</span></span>|<span data-ttu-id="de962-126">Description</span><span class="sxs-lookup"><span data-stu-id="de962-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="de962-127">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="de962-127">\<oneWay></span></span>](oneway.md)|<span data-ttu-id="de962-128">사용자 지정 바인딩에 대한 패킷 라우팅을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-128">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="de962-129">설명</span><span class="sxs-lookup"><span data-stu-id="de962-129">Remarks</span></span>  
 <span data-ttu-id="de962-130">할당량은 과도한 리소스 소비를 방지하기 위한 정책 메커니즘으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="de962-130">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="de962-131">할당량은 악의적이거나 의도하지 않은 DOS(서비스 거부) 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-131">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="de962-132">사용자 지정 채널에서 채널 할당량을 설정할 때 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-132">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="de962-133">`ChannelPoolSettings`는 다음 세 가지 할당량을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-133">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="de962-134">`idleTimeout` 할당량을 사용하면 장기간 동안 제한된 리소스를 사용하는 서버에 대한 DOS(서비스 거부) 공격을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de962-134">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="de962-135">클라이언트에서 정확한 값을 설정하면 서비스 연결 안정성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de962-135">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="de962-136">기본값은 신중하고 적당한 리소스 할당을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-136">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="de962-137">이 값은 개발 환경 및 소규모 설치 시나리오에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-137">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="de962-138">설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-138">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="de962-139">`leaseTimeout` 할당량을 사용하면 부하 균형 도구와 통합되어 안정성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de962-139">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="de962-140">기본값은 신중한 리소스 할당을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-140">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="de962-141">이 값은 개발 환경 및 소규모 설치 시나리오에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-141">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="de962-142">설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-142">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="de962-143">`maxOutboundChannelsPerEndpoint` 할당량은 서버와 클라이언트 양쪽에 캐시 제한을 설정하며 이를 사용하여 안정성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de962-143">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="de962-144">기본값은 개발 환경 및 소규모 설치 시나리오에 적합한 신중하고 적당한 리소스 할당을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-144">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="de962-145">설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de962-145">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de962-146">참고자료</span><span class="sxs-lookup"><span data-stu-id="de962-146">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="de962-147">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="de962-147">\<oneWay></span></span>](oneway.md)
- [<span data-ttu-id="de962-148">바인딩</span><span class="sxs-lookup"><span data-stu-id="de962-148">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="de962-149">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="de962-149">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="de962-150">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="de962-150">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="de962-151">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="de962-151">\<customBinding></span></span>](custombinding.md)
