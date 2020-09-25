---
title: <oneWay>
ms.date: 03/30/2017
ms.assetid: 00e67e0e-77c0-4695-9138-c0997b0e5f3c
ms.openlocfilehash: 92cd6b280305c223ee125a45724691c5205ce3c1
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2020
ms.locfileid: "91195014"
---
# \<oneWay>

<span data-ttu-id="a7432-101">사용자 지정 바인딩에 대한 패킷 라우팅 및 단방향 메서드를 사용하도록 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-101">Enables packet routing and the use of one-way methods for a custom binding.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<customBinding>**](custombinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<oneWay>**  
  
## <a name="syntax"></a><span data-ttu-id="a7432-102">구문</span><span class="sxs-lookup"><span data-stu-id="a7432-102">Syntax</span></span>  
  
```xml  
<oneWay packetRoutable="Boolean">
  <channelPoolSettings idleTimeout="TimeSpan"
                       leaseTimeout="TimeSpan"
                       maxOutboundConnectionsPerEndpoint="Integer" />
</oneWay>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="a7432-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="a7432-103">Attributes and Elements</span></span>  

 <span data-ttu-id="a7432-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="a7432-105">특성</span><span class="sxs-lookup"><span data-stu-id="a7432-105">Attributes</span></span>  
  
|<span data-ttu-id="a7432-106">attribute</span><span class="sxs-lookup"><span data-stu-id="a7432-106">Attribute</span></span>|<span data-ttu-id="a7432-107">설명</span><span class="sxs-lookup"><span data-stu-id="a7432-107">Description</span></span>|  
|---------------|-----------------|  
|`packetRoutable`|<span data-ttu-id="a7432-108">패킷 라우팅 활성화 여부를 나타내는 부울 값입니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-108">A Boolean value that specifies whether packet routing is enabled.</span></span> <span data-ttu-id="a7432-109">기본값은 `false`입니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-109">The default is `false`.</span></span>|  
|`MaxAcceptedChannels`|<span data-ttu-id="a7432-110">수락할 수 있는 최대 채널 수를 지정하는 정수입니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-110">An integer that specifies the maximum number of channels that can be accepted.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="a7432-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="a7432-111">Child Elements</span></span>  
  
|<span data-ttu-id="a7432-112">요소</span><span class="sxs-lookup"><span data-stu-id="a7432-112">Element</span></span>|<span data-ttu-id="a7432-113">설명</span><span class="sxs-lookup"><span data-stu-id="a7432-113">Description</span></span>|  
|-------------|-----------------|  
|[\<channelPoolSettings>](channelpoolsettings.md)|<span data-ttu-id="a7432-114">현재 채널의 채널 풀 속성을 포함하는 <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-114">A <xref:System.ServiceModel.Configuration.ChannelPoolSettingsElement> object that contains properties of the channel pool for the current channel.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="a7432-115">부모 요소</span><span class="sxs-lookup"><span data-stu-id="a7432-115">Parent Elements</span></span>  
  
|<span data-ttu-id="a7432-116">요소</span><span class="sxs-lookup"><span data-stu-id="a7432-116">Element</span></span>|<span data-ttu-id="a7432-117">설명</span><span class="sxs-lookup"><span data-stu-id="a7432-117">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="a7432-118">사용자 지정 바인딩의 모든 바인딩 기능을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-118">Defines all binding capabilities of the custom binding.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a7432-119">설명</span><span class="sxs-lookup"><span data-stu-id="a7432-119">Remarks</span></span>  

 <span data-ttu-id="a7432-120">패킷 라우팅을 사용하려면 이 요소에서 제공하는 단방향 변환 계층이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-120">To enable packet routing, a one-way conversion layer is required, which this element provides.</span></span> <span data-ttu-id="a7432-121">사용자는 세션 인식 또는 요청-회신 전송을 통해 이 바인딩을 계층화하여 패킷 라우팅이 가능한 사용자 지정 바인딩을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-121">A user can create a custom binding that layers this binding over a session-aware or request-reply transport to make it packet routable.</span></span> <span data-ttu-id="a7432-122">이 요소는 원래의 방식으로 단방향 메서드를 노출하려는 경우에도 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-122">This element is also useful when you want to expose one-way methods in a more native fashion.</span></span> <span data-ttu-id="a7432-123">복합 이중, 신뢰할 수 있는 메시징 등과 같은 많은 변형을 이 계층에서 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7432-123">More transformations can be applied over this layer, such as Composite Duplex and Reliable Messaging.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7432-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7432-124">See also</span></span>

- <xref:System.ServiceModel.Channels.OneWayBindingElement>
- <xref:System.ServiceModel.Configuration.OneWayElement>
- <xref:System.ServiceModel.Channels.CustomBinding>
- [<span data-ttu-id="a7432-125">바인딩하</span><span class="sxs-lookup"><span data-stu-id="a7432-125">Bindings</span></span>](../../../wcf/bindings.md)
- [<span data-ttu-id="a7432-126">바인딩 확장명</span><span class="sxs-lookup"><span data-stu-id="a7432-126">Extending Bindings</span></span>](../../../wcf/extending/extending-bindings.md)
- [<span data-ttu-id="a7432-127">사용자 지정 바인딩</span><span class="sxs-lookup"><span data-stu-id="a7432-127">Custom Bindings</span></span>](../../../wcf/extending/custom-bindings.md)
- [\<customBinding>](custombinding.md)
