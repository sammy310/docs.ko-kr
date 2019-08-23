---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: dd81821c74678cae8602458fe796a72bf5d379e4
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69919552"
---
# <a name="channelpoolsettings"></a><span data-ttu-id="5d89a-101">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="5d89a-101">\<channelPoolSettings></span></span>
<span data-ttu-id="5d89a-102">사용자 지정 바인딩의 채널 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-102">Specifies the channel pool settings for a custom binding.</span></span>  
  
 <span data-ttu-id="5d89a-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="5d89a-103">\<system.serviceModel></span></span>  
<span data-ttu-id="5d89a-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="5d89a-104">\<bindings></span></span>  
<span data-ttu-id="5d89a-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5d89a-105">\<customBinding></span></span>  
<span data-ttu-id="5d89a-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="5d89a-106">\<binding></span></span>  
<span data-ttu-id="5d89a-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="5d89a-107">\<oneWay></span></span>  
<span data-ttu-id="5d89a-108">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="5d89a-108">\<channelPoolSettings></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5d89a-109">구문</span><span class="sxs-lookup"><span data-stu-id="5d89a-109">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="5d89a-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="5d89a-110">Attributes and Elements</span></span>  
 <span data-ttu-id="5d89a-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="5d89a-112">특성</span><span class="sxs-lookup"><span data-stu-id="5d89a-112">Attributes</span></span>  
  
|<span data-ttu-id="5d89a-113">특성</span><span class="sxs-lookup"><span data-stu-id="5d89a-113">Attribute</span></span>|<span data-ttu-id="5d89a-114">Description</span><span class="sxs-lookup"><span data-stu-id="5d89a-114">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="5d89a-115">연결이 끊어지기 전에 풀의 채널이 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-115">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="5d89a-116">기본값은 00:02:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-116">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="5d89a-117">채널이 풀에 반환될 때 해당 기간이 경과하면 채널이 닫히는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-117">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="5d89a-118">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-118">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="5d89a-119">각 원격 엔드포인트에 대해 풀에 저장할 수 있는 최대 채널 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-119">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="5d89a-120">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-120">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="5d89a-121">자식 요소</span><span class="sxs-lookup"><span data-stu-id="5d89a-121">Child Elements</span></span>  
 <span data-ttu-id="5d89a-122">없음</span><span class="sxs-lookup"><span data-stu-id="5d89a-122">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="5d89a-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="5d89a-123">Parent Elements</span></span>  
  
|<span data-ttu-id="5d89a-124">요소</span><span class="sxs-lookup"><span data-stu-id="5d89a-124">Element</span></span>|<span data-ttu-id="5d89a-125">Description</span><span class="sxs-lookup"><span data-stu-id="5d89a-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="5d89a-126">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="5d89a-126">\<oneWay></span></span>](oneway.md)|<span data-ttu-id="5d89a-127">사용자 지정 바인딩에 대한 패킷 라우팅을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-127">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5d89a-128">설명</span><span class="sxs-lookup"><span data-stu-id="5d89a-128">Remarks</span></span>  
 <span data-ttu-id="5d89a-129">할당량은 과도한 리소스 소비를 방지하기 위한 정책 메커니즘으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-129">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="5d89a-130">할당량은 악의적이거나 의도하지 않은 DOS(서비스 거부) 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-130">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="5d89a-131">사용자 지정 채널에서 채널 할당량을 설정할 때 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-131">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="5d89a-132">`ChannelPoolSettings`는 다음 세 가지 할당량을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-132">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="5d89a-133">`idleTimeout` 할당량을 사용하면 장기간 동안 제한된 리소스를 사용하는 서버에 대한 DOS(서비스 거부) 공격을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-133">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="5d89a-134">클라이언트에서 정확한 값을 설정하면 서비스 연결 안정성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-134">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="5d89a-135">기본값은 신중하고 적당한 리소스 할당을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-135">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="5d89a-136">이 값은 개발 환경 및 소규모 설치 시나리오에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-136">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="5d89a-137">설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-137">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="5d89a-138">`leaseTimeout` 할당량을 사용하면 부하 균형 도구와 통합되어 안정성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-138">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="5d89a-139">기본값은 신중한 리소스 할당을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-139">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="5d89a-140">이 값은 개발 환경 및 소규모 설치 시나리오에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-140">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="5d89a-141">설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-141">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="5d89a-142">`maxOutboundChannelsPerEndpoint` 할당량은 서버와 클라이언트 양쪽에 캐시 제한을 설정하며 이를 사용하여 안정성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-142">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="5d89a-143">기본값은 개발 환경 및 소규모 설치 시나리오에 적합한 신중하고 적당한 리소스 할당을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-143">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="5d89a-144">설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5d89a-144">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5d89a-145">참고자료</span><span class="sxs-lookup"><span data-stu-id="5d89a-145">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="5d89a-146">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="5d89a-146">\<oneWay></span></span>](oneway.md)
- [<span data-ttu-id="5d89a-147">바인딩</span><span class="sxs-lookup"><span data-stu-id="5d89a-147">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="5d89a-148">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="5d89a-148">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="5d89a-149">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="5d89a-149">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="5d89a-150">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="5d89a-150">\<customBinding></span></span>](custombinding.md)
