---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: 22be09204266253d45ece46f51cc6f080f2b3fd6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2019
ms.locfileid: "73738735"
---
# <a name="resolver"></a><span data-ttu-id="2a555-101">\<해결 프로그램 ></span><span class="sxs-lookup"><span data-stu-id="2a555-101">\<resolver></span></span>
<span data-ttu-id="2a555-102">피어 메시 ID를 확인하는 데 사용되는 피어 확인자를 메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-102">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
<span data-ttu-id="2a555-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="2a555-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="2a555-104">[ **\<system serviceModel >** ](system-servicemodel.md) &nbsp; &nbsp; </span><span class="sxs-lookup"><span data-stu-id="2a555-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="2a555-105">&nbsp;&nbsp;&nbsp;&nbsp;\<[**바인딩**](bindings.md) ></span><span class="sxs-lookup"><span data-stu-id="2a555-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\</span></span>
<span data-ttu-id="2a555-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="2a555-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="2a555-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="2a555-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="2a555-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;\<**해결 프로그램 >**</span><span class="sxs-lookup"><span data-stu-id="2a555-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a555-109">구문</span><span class="sxs-lookup"><span data-stu-id="2a555-109">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="2a555-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="2a555-110">Attributes and Elements</span></span>  
 <span data-ttu-id="2a555-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="2a555-112">특성</span><span class="sxs-lookup"><span data-stu-id="2a555-112">Attributes</span></span>  
  
|<span data-ttu-id="2a555-113">특성</span><span class="sxs-lookup"><span data-stu-id="2a555-113">Attribute</span></span>|<span data-ttu-id="2a555-114">설명</span><span class="sxs-lookup"><span data-stu-id="2a555-114">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="2a555-115">이 서비스와 연결된 피어 확인자 인스턴스가 PNRP 관련 사용자 지정 확인자인지 아니면 자동으로 결정되는지 여부를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-115">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="2a555-116">이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-116">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="2a555-117">피어 간에 조회를 공유하는 방법을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-117">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="2a555-118">이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-118">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="2a555-119">자식 요소</span><span class="sxs-lookup"><span data-stu-id="2a555-119">Child Elements</span></span>  
  
|<span data-ttu-id="2a555-120">요소</span><span class="sxs-lookup"><span data-stu-id="2a555-120">Element</span></span>|<span data-ttu-id="2a555-121">설명</span><span class="sxs-lookup"><span data-stu-id="2a555-121">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a555-122">\<헤더 ></span><span class="sxs-lookup"><span data-stu-id="2a555-122">\<headers></span></span>](headers.md)|<span data-ttu-id="2a555-123">사용자 지정 피어 확인자 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-123">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="2a555-124">부모 요소</span><span class="sxs-lookup"><span data-stu-id="2a555-124">Parent Elements</span></span>  
  
|<span data-ttu-id="2a555-125">요소</span><span class="sxs-lookup"><span data-stu-id="2a555-125">Element</span></span>|<span data-ttu-id="2a555-126">설명</span><span class="sxs-lookup"><span data-stu-id="2a555-126">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="2a555-127">\<binding ></span><span class="sxs-lookup"><span data-stu-id="2a555-127">\<binding></span></span>](bindings.md)|<span data-ttu-id="2a555-128">[\<netPeerTcpBinding >](netpeertcpbinding.md)의 모든 바인딩 기능을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-128">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2a555-129">주의</span><span class="sxs-lookup"><span data-stu-id="2a555-129">Remarks</span></span>  
 <span data-ttu-id="2a555-130">피어 이름 확인자는 피어 메시에 참여하는 피어 노드를 찾기 위해 피어 채널에서 사용하는 검색 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-130">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="2a555-131">피어 메시를 사용 하 여 노드를 "등록" 하는 데도 사용 됩니다 .이 메커니즘은 피어 노드가 알려지고 피어 메시에 서 사용할 수 있게 되는 메커니즘입니다.</span><span class="sxs-lookup"><span data-stu-id="2a555-131">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="2a555-132">피어 확인자에 대 한 자세한 내용은 [피어 확인자](../../../wcf/feature-details/peer-resolvers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2a555-132">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a555-133">참조</span><span class="sxs-lookup"><span data-stu-id="2a555-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="2a555-134">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="2a555-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="2a555-135">[PeerChannel 응용 프로그램에 사용자 지정 해결 프로그램 추가](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="2a555-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
