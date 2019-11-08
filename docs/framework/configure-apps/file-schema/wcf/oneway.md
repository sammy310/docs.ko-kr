---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: a5c773ea91de882920775ac8dc0ecc1da68a6c9f
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738794"
---
# <a name="oneway"></a><span data-ttu-id="1e0ee-101">\<oneWay ></span><span class="sxs-lookup"><span data-stu-id="1e0ee-101">\<oneWay></span></span>
<span data-ttu-id="1e0ee-102">사용자 지정 바인딩에 대한 패킷 라우팅 및 단방향 메서드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-102">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
<span data-ttu-id="1e0ee-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="1e0ee-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="1e0ee-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="1e0ee-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="1e0ee-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="1e0ee-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="1e0ee-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<customBinding >** ](custombinding.md)</span><span class="sxs-lookup"><span data-stu-id="1e0ee-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)</span></span>\
<span data-ttu-id="1e0ee-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="1e0ee-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="1e0ee-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**oneWay >**</span><span class="sxs-lookup"><span data-stu-id="1e0ee-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e0ee-109">구문</span><span class="sxs-lookup"><span data-stu-id="1e0ee-109">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="1e0ee-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="1e0ee-110">Attributes and Elements</span></span>  
 <span data-ttu-id="1e0ee-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="1e0ee-112">특성</span><span class="sxs-lookup"><span data-stu-id="1e0ee-112">Attributes</span></span>  
  
|<span data-ttu-id="1e0ee-113">특성</span><span class="sxs-lookup"><span data-stu-id="1e0ee-113">Attribute</span></span>|<span data-ttu-id="1e0ee-114">설명</span><span class="sxs-lookup"><span data-stu-id="1e0ee-114">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="1e0ee-115">패킷 라우팅 활성화 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-115">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="1e0ee-116">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-116">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="1e0ee-117">수락할 수 있는 최대 채널 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-117">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="1e0ee-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="1e0ee-118">Child Elements</span></span>  
  
|<span data-ttu-id="1e0ee-119">요소</span><span class="sxs-lookup"><span data-stu-id="1e0ee-119">Element</span></span>|<span data-ttu-id="1e0ee-120">설명</span><span class="sxs-lookup"><span data-stu-id="1e0ee-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e0ee-121">\<channelPoolSettings ></span><span class="sxs-lookup"><span data-stu-id="1e0ee-121">\<channelPoolSettings></span></span>](channelpoolsettings.md)|<span data-ttu-id="1e0ee-122">현재 채널의 채널 풀 속성을 포함하는 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-122">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="1e0ee-123">부모 요소</span><span class="sxs-lookup"><span data-stu-id="1e0ee-123">Parent Elements</span></span>  
  
|<span data-ttu-id="1e0ee-124">요소</span><span class="sxs-lookup"><span data-stu-id="1e0ee-124">Element</span></span>|<span data-ttu-id="1e0ee-125">설명</span><span class="sxs-lookup"><span data-stu-id="1e0ee-125">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="1e0ee-126">\<binding ></span><span class="sxs-lookup"><span data-stu-id="1e0ee-126">\<binding></span></span>](bindings.md)|<span data-ttu-id="1e0ee-127">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-127">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1e0ee-128">주의</span><span class="sxs-lookup"><span data-stu-id="1e0ee-128">Remarks</span></span>  
 <span data-ttu-id="1e0ee-129">패킷 라우팅을 사용하려면 이 요소에서 제공하는 단방향 변환 계층이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-129">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="1e0ee-130">사용자는 세션 인식 또는 요청-회신 전송에 대해이 바인딩을 계층으로 지정 하 여 패킷을 라우팅할 수 있도록 하는 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-130">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="1e0ee-131">이 요소는 원래의 방식으로 단방향 메서드를 노출하려는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-131">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="1e0ee-132">복합 이중 및 안정적인 메시징과 같이이 계층에 더 많은 변환을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e0ee-132">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e0ee-133">참조</span><span class="sxs-lookup"><span data-stu-id="1e0ee-133">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="1e0ee-134">바인딩</span><span class="sxs-lookup"><span data-stu-id="1e0ee-134">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="1e0ee-135">바인딩 확장</span><span class="sxs-lookup"><span data-stu-id="1e0ee-135">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="1e0ee-136">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="1e0ee-136">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [<span data-ttu-id="1e0ee-137">\<customBinding ></span><span class="sxs-lookup"><span data-stu-id="1e0ee-137">\<customBinding></span></span>](custombinding.md)
