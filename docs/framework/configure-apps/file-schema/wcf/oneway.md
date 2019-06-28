---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 2458cdd4d593637c2025047d5dd510f0f89b2a0f
ms.sourcegitcommit: 9b1ac36b6c80176fd4e20eb5bfcbd9d56c3264cf
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/28/2019
ms.locfileid: "67423081"
---
# <a name="oneway"></a><span data-ttu-id="e9217-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="e9217-101">\<oneWay></span></span>
<span data-ttu-id="e9217-102">사용자 지정 바인딩에 대한 패킷 라우팅 및 단방향 메서드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="e9217-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="e9217-103">\<system.serviceModel></span></span>  
<span data-ttu-id="e9217-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="e9217-104">\<bindings></span></span>  
<span data-ttu-id="e9217-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e9217-105">\<customBinding></span></span>  
<span data-ttu-id="e9217-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="e9217-106">\<binding></span></span>  
<span data-ttu-id="e9217-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="e9217-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e9217-108">구문</span><span class="sxs-lookup"><span data-stu-id="e9217-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="e9217-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="e9217-109">Attributes and Elements</span></span>  
 <span data-ttu-id="e9217-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="e9217-111">특성</span><span class="sxs-lookup"><span data-stu-id="e9217-111">Attributes</span></span>  
  
|<span data-ttu-id="e9217-112">특성</span><span class="sxs-lookup"><span data-stu-id="e9217-112">Attribute</span></span>|<span data-ttu-id="e9217-113">설명</span><span class="sxs-lookup"><span data-stu-id="e9217-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="e9217-114">패킷 라우팅 활성화 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="e9217-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="e9217-116">수락할 수 있는 최대 채널 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="e9217-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="e9217-117">Child Elements</span></span>  
  
|<span data-ttu-id="e9217-118">요소</span><span class="sxs-lookup"><span data-stu-id="e9217-118">Element</span></span>|<span data-ttu-id="e9217-119">설명</span><span class="sxs-lookup"><span data-stu-id="e9217-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9217-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="e9217-120">\<channelPoolSettings></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/channelpoolsettings.md)|<span data-ttu-id="e9217-121">현재 채널의 채널 풀 속성을 포함하는 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="e9217-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="e9217-122">Parent Elements</span></span>  
  
|<span data-ttu-id="e9217-123">요소</span><span class="sxs-lookup"><span data-stu-id="e9217-123">Element</span></span>|<span data-ttu-id="e9217-124">설명</span><span class="sxs-lookup"><span data-stu-id="e9217-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="e9217-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="e9217-125">\<binding></span></span>](../../../../../docs/framework/misc/binding.md)|<span data-ttu-id="e9217-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e9217-127">설명</span><span class="sxs-lookup"><span data-stu-id="e9217-127">Remarks</span></span>  
 <span data-ttu-id="e9217-128">패킷 라우팅을 사용하려면 이 요소에서 제공하는 단방향 변환 계층이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="e9217-129">사용자는 세션 인식 또는 요청-회신 전송을 통해 이 바인딩을 계층화하여 패킷 라우팅이 가능한 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="e9217-130">이 요소는 원래의 방식으로 단방향 메서드를 노출하려는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="e9217-131">복합 이중, 신뢰할 수 있는 메시징 등과 같은 많은 변형을 이 계층에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e9217-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e9217-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="e9217-132">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="e9217-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="e9217-133">Bindings</span></span>](../../../../../docs/framework/wcf/bindings.md)
- [<span data-ttu-id="e9217-134">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="e9217-134">Extending Bindings</span></span>](../../../../../docs/framework/wcf/extending/extending-bindings.md)
- [<span data-ttu-id="e9217-135">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="e9217-135">Custom Bindings</span></span>](../../../../../docs/framework/wcf/extending/custom-bindings.md)
- [<span data-ttu-id="e9217-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="e9217-136">\<customBinding></span></span>](../../../../../docs/framework/configure-apps/file-schema/wcf/custombinding.md)
