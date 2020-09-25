---
title: <channelPoolSettings>
ms.date: 03/30/2017
ms.assetid: 4755f3d3-4213-4c68-ae7f-45b67d744459
ms.openlocfilehash: 8638d56ccb4aaa1c5ac735aa268823af2b1fbc6d
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91176073"
---
# \<channelPoolSettings>

<span data-ttu-id="40a5d-101">사용자 지정 바인딩의 채널 풀 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-101">Specifies the channel pool settings for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<oneWay>**](oneway.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<channelPoolSettings>**  
  
## <a name="syntax"></a><span data-ttu-id="40a5d-102">구문</span><span class="sxs-lookup"><span data-stu-id="40a5d-102">Syntax</span></span>  
  
```xml  
<channelPoolSettings idleTimeout="TimeSpan"
                     leaseTimeout="TimeSpan"
                     maxOutboundConnectionsPerEndpoint="Integer" />
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="40a5d-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="40a5d-103">Attributes and Elements</span></span>  

 <span data-ttu-id="40a5d-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="40a5d-105">특성</span><span class="sxs-lookup"><span data-stu-id="40a5d-105">Attributes</span></span>  
  
|<span data-ttu-id="40a5d-106">attribute</span><span class="sxs-lookup"><span data-stu-id="40a5d-106">Attribute</span></span>|<span data-ttu-id="40a5d-107">설명</span><span class="sxs-lookup"><span data-stu-id="40a5d-107">Description</span></span>|  
|---------------|-----------------|  
|`idleTimeout`|<span data-ttu-id="40a5d-108">연결이 끊어지기 전에 풀의 채널이 유휴 상태를 유지할 수 있는 최대 시간을 지정하는 <xref:System.TimeSpan>(양수)입니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-108">A positive <xref:System.TimeSpan> that specifies the maximum time the channels in the pool can be idle before being disconnected.</span></span> <span data-ttu-id="40a5d-109">기본값은 00:02:00입니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-109">The default is 00:02:00.</span></span>|  
|`leaseTimeout`|<span data-ttu-id="40a5d-110">채널이 풀에 반환될 때 해당 기간이 경과하면 채널이 닫히는 시간 간격을 지정하는 <xref:System.TimeSpan>입니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-110">A <xref:System.TimeSpan> that specifies the interval of time after which a channel, when returned to the pool, is closed.</span></span> <span data-ttu-id="40a5d-111">기본값은 00:10:00입니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-111">The default is 00:10:00.</span></span>|  
|`maxOutboundChannelsPerEndpoint`|<span data-ttu-id="40a5d-112">각 원격 엔드포인트에 대해 풀에 저장할 수 있는 최대 채널 수를 지정하는 양의 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-112">A positive integer that specifies the maximum number of channels that can be stored in the pool for each remote endpoint.</span></span> <span data-ttu-id="40a5d-113">기본값은 10입니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-113">The default is 10.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="40a5d-114">자식 요소</span><span class="sxs-lookup"><span data-stu-id="40a5d-114">Child Elements</span></span>  

 <span data-ttu-id="40a5d-115">없음</span><span class="sxs-lookup"><span data-stu-id="40a5d-115">None.</span></span>  
  
### <a name="parent-elements"></a><span data-ttu-id="40a5d-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="40a5d-116">Parent Elements</span></span>  
  
|<span data-ttu-id="40a5d-117">요소</span><span class="sxs-lookup"><span data-stu-id="40a5d-117">Element</span></span>|<span data-ttu-id="40a5d-118">설명</span><span class="sxs-lookup"><span data-stu-id="40a5d-118">Description</span></span>|  
|-------------|-----------------|  
|[\<oneWay>](oneway.md)|<span data-ttu-id="40a5d-119">사용자 지정 바인딩에 대한 패킷 라우팅을 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-119">Enables packet routing for a custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="40a5d-120">설명</span><span class="sxs-lookup"><span data-stu-id="40a5d-120">Remarks</span></span>  

 <span data-ttu-id="40a5d-121">할당량은 과도한 리소스 소비를 방지하기 위한 정책 메커니즘으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-121">Quotas are used as a policy mechanism to prevent the consumption of excessive resources.</span></span> <span data-ttu-id="40a5d-122">할당량은 악의적이거나 의도하지 않은 DOS(서비스 거부) 공격을 방지합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-122">They prevent Denial of Service (DOS) attacks that are either malicious or unintentional.</span></span> <span data-ttu-id="40a5d-123">사용자 지정 채널에서 채널 할당량을 설정할 때 이 요소를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-123">Use this element when setting channel quotas on a custom channel.</span></span>  
  
 <span data-ttu-id="40a5d-124">`ChannelPoolSettings`는 다음 세 가지 할당량을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-124">`ChannelPoolSettings` specifies three quotas:</span></span>  
  
- <span data-ttu-id="40a5d-125">`idleTimeout` 할당량을 사용하면 장기간 동안 제한된 리소스를 사용하는 서버에 대한 DOS(서비스 거부) 공격을 줄일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-125">The `idleTimeout` quota is used to mitigate Denial of Service (DOS) attacks on the server that rely on tying up resources for an extended period of time.</span></span> <span data-ttu-id="40a5d-126">클라이언트에서 정확한 값을 설정하면 서비스 연결 안정성을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-126">On the client, setting the correct value can increase the reliability of connecting with the service.</span></span> <span data-ttu-id="40a5d-127">기본값은 신중하고 적당한 리소스 할당을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-127">The default value is based on a conservatively modest allocation of resources.</span></span> <span data-ttu-id="40a5d-128">이 값은 개발 환경 및 소규모 설치 시나리오에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-128">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="40a5d-129">설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-129">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="40a5d-130">`leaseTimeout` 할당량을 사용하면 부하 균형 도구와 통합되어 안정성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-130">The `leaseTimeout` quota is used to for integration with load balancers and for improving reliability.</span></span> <span data-ttu-id="40a5d-131">기본값은 신중한 리소스 할당을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-131">The default value is based on a conservative allocation of resources.</span></span> <span data-ttu-id="40a5d-132">이 값은 개발 환경 및 소규모 설치 시나리오에 적합합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-132">It is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="40a5d-133">설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-133">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
- <span data-ttu-id="40a5d-134">`maxOutboundChannelsPerEndpoint` 할당량은 서버와 클라이언트 양쪽에 캐시 제한을 설정하며 이를 사용하여 안정성을 향상시킬 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-134">The `maxOutboundChannelsPerEndpoint` quota sets cache limits on both the server and the client and is used to improve reliability.</span></span> <span data-ttu-id="40a5d-135">기본값은 개발 환경 및 소규모 설치 시나리오에 적합한 신중하고 적당한 리소스 할당을 기준으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-135">The default value is based on a conservatively modest allocation of resources that is suitable for a development environment and small installation scenarios.</span></span> <span data-ttu-id="40a5d-136">설치로 인해 리소스가 부족해지거나 추가 리소스를 사용할 수 있더라도 연결이 제한되는 경우 서비스 관리자는 이 값을 검토해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="40a5d-136">Service administrators should review the value if an installation is running out of resources or if connections are being limited despite the availability of additional resources.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="40a5d-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="40a5d-137">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Channels.ChannelPoolSettings>
- <xref:System.ServiceModel.Configuration.OneWayElement.ChannelPoolSettings%2A>
- <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [\<oneWay>](oneway.md)
- [<span data-ttu-id="40a5d-138">바인딩하</span><span class="sxs-lookup"><span data-stu-id="40a5d-138">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="40a5d-139">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="40a5d-139">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="40a5d-140">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="40a5d-140">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
