---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: f4a9422f4385e37a61ec85d680fcf7743a57bc0c
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69932938"
---
# <a name="oneway"></a><span data-ttu-id="062a4-101">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="062a4-101">\<oneWay></span></span>
<span data-ttu-id="062a4-102">사용자 지정 바인딩에 대한 패킷 라우팅 및 단방향 메서드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
 <span data-ttu-id="062a4-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="062a4-103">\<system.serviceModel></span></span>  
<span data-ttu-id="062a4-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="062a4-104">\<bindings></span></span>  
<span data-ttu-id="062a4-105">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="062a4-105">\<customBinding></span></span>  
<span data-ttu-id="062a4-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="062a4-106">\<binding></span></span>  
<span data-ttu-id="062a4-107">\<oneWay></span><span class="sxs-lookup"><span data-stu-id="062a4-107">\<oneWay></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="062a4-108">구문</span><span class="sxs-lookup"><span data-stu-id="062a4-108">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="062a4-109">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="062a4-109">Attributes and Elements</span></span>  
 <span data-ttu-id="062a4-110">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-110">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="062a4-111">특성</span><span class="sxs-lookup"><span data-stu-id="062a4-111">Attributes</span></span>  
  
|<span data-ttu-id="062a4-112">특성</span><span class="sxs-lookup"><span data-stu-id="062a4-112">Attribute</span></span>|<span data-ttu-id="062a4-113">Description</span><span class="sxs-lookup"><span data-stu-id="062a4-113">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="062a4-114">패킷 라우팅 활성화 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-114">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="062a4-115">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-115">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="062a4-116">수락할 수 있는 최대 채널 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-116">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="062a4-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="062a4-117">Child Elements</span></span>  
  
|<span data-ttu-id="062a4-118">요소</span><span class="sxs-lookup"><span data-stu-id="062a4-118">Element</span></span>|<span data-ttu-id="062a4-119">Description</span><span class="sxs-lookup"><span data-stu-id="062a4-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="062a4-120">\<channelPoolSettings></span><span class="sxs-lookup"><span data-stu-id="062a4-120">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="062a4-121">현재 채널의 채널 풀 속성을 포함하는 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-121">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="062a4-122">부모 요소</span><span class="sxs-lookup"><span data-stu-id="062a4-122">Parent Elements</span></span>  
  
|<span data-ttu-id="062a4-123">요소</span><span class="sxs-lookup"><span data-stu-id="062a4-123">Element</span></span>|<span data-ttu-id="062a4-124">설명</span><span class="sxs-lookup"><span data-stu-id="062a4-124">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="062a4-125">\<binding></span><span class="sxs-lookup"><span data-stu-id="062a4-125">\<binding></span></span>](../../../misc/binding.md)|<span data-ttu-id="062a4-126">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-126">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="062a4-127">설명</span><span class="sxs-lookup"><span data-stu-id="062a4-127">Remarks</span></span>  
 <span data-ttu-id="062a4-128">패킷 라우팅을 사용하려면 이 요소에서 제공하는 단방향 변환 계층이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-128">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="062a4-129">사용자는 세션 인식 또는 요청-회신 전송을 통해 이 바인딩을 계층화하여 패킷 라우팅이 가능한 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-129">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="062a4-130">이 요소는 원래의 방식으로 단방향 메서드를 노출하려는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-130">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="062a4-131">복합 이중, 신뢰할 수 있는 메시징 등과 같은 많은 변형을 이 계층에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="062a4-131">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="062a4-132">참고자료</span><span class="sxs-lookup"><span data-stu-id="062a4-132">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="062a4-133">바인딩</span><span class="sxs-lookup"><span data-stu-id="062a4-133">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="062a4-134">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="062a4-134">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="062a4-135">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="062a4-135">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="062a4-136">\<customBinding></span><span class="sxs-lookup"><span data-stu-id="062a4-136">\<customBinding></span></span>](custombinding.md)
