---
title: <resolver>
ms.date: 03/30/2017
ms.assetid: 0c00200c-f135-4e5c-a024-76b72bcbc021
ms.openlocfilehash: 0dc667f392595d895bd4f2773ab69777d7369446
ms.sourcegitcommit: b16c00371ea06398859ecd157defc81301c9070f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2020
ms.locfileid: "73738735"
---
# \<resolver>
<span data-ttu-id="0a8f5-101">피어 메시 ID를 확인하는 데 사용되는 피어 확인자를 메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-101">Specifies a peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<resolver>**  
  
## <a name="syntax"></a><span data-ttu-id="0a8f5-102">구문</span><span class="sxs-lookup"><span data-stu-id="0a8f5-102">Syntax</span></span>  
  
```xml  
<resolver mode="Auto/Custom/Pnrp"
          referralPolicy="DoNotShare/Service/Share">
</resolver>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="0a8f5-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="0a8f5-103">Attributes and Elements</span></span>  
 <span data-ttu-id="0a8f5-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="0a8f5-105">특성</span><span class="sxs-lookup"><span data-stu-id="0a8f5-105">Attributes</span></span>  
  
|<span data-ttu-id="0a8f5-106">attribute</span><span class="sxs-lookup"><span data-stu-id="0a8f5-106">Attribute</span></span>|<span data-ttu-id="0a8f5-107">Description</span><span class="sxs-lookup"><span data-stu-id="0a8f5-107">Description</span></span>|  
|---------------|-----------------|  
|`mode`|<span data-ttu-id="0a8f5-108">이 서비스와 연결된 피어 확인자 인스턴스가 PNRP 관련 사용자 지정 확인자인지 아니면 자동으로 결정되는지 여부를 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-108">A string that specifies whether the peer resolver instance associated with this service is either PNRP-specific, a custom resolver, or automatically determined.</span></span> <span data-ttu-id="0a8f5-109">이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerResolverMode> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-109">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerResolverMode>.</span></span>|  
|`referralPolicy`|<span data-ttu-id="0a8f5-110">피어 간에 조회를 공유하는 방법을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-110">A string that specifies the way referrals are shared among peers.</span></span> <span data-ttu-id="0a8f5-111">이 특성은 <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-111">This attribute is of type <xref:System.ServiceModel.PeerResolvers.PeerReferralPolicy>.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="0a8f5-112">자식 요소</span><span class="sxs-lookup"><span data-stu-id="0a8f5-112">Child Elements</span></span>  
  
|<span data-ttu-id="0a8f5-113">요소</span><span class="sxs-lookup"><span data-stu-id="0a8f5-113">Element</span></span>|<span data-ttu-id="0a8f5-114">Description</span><span class="sxs-lookup"><span data-stu-id="0a8f5-114">Description</span></span>|  
|-------------|-----------------|  
|[\<headers>](headers.md)|<span data-ttu-id="0a8f5-115">사용자 지정 피어 확인자 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-115">Specifies settings for a custom peer resolver service.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="0a8f5-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="0a8f5-116">Parent Elements</span></span>  
  
|<span data-ttu-id="0a8f5-117">요소</span><span class="sxs-lookup"><span data-stu-id="0a8f5-117">Element</span></span>|<span data-ttu-id="0a8f5-118">Description</span><span class="sxs-lookup"><span data-stu-id="0a8f5-118">Description</span></span>|  
|-------------|-----------------|  
|[\<binding>](bindings.md)|<span data-ttu-id="0a8f5-119">의 모든 바인딩 기능을 정의 [\<netPeerTcpBinding>](netpeertcpbinding.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-119">Defines all binding capabilities of the [\<netPeerTcpBinding>](netpeertcpbinding.md).</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0a8f5-120">설명</span><span class="sxs-lookup"><span data-stu-id="0a8f5-120">Remarks</span></span>  
 <span data-ttu-id="0a8f5-121">피어 이름 확인자는 피어 메시에 참여하는 피어 노드를 찾기 위해 피어 채널에서 사용하는 검색 서비스입니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-121">A peer name resolver is a discovery service used by peer channels to find peer nodes that participate in a peer mesh.</span></span> <span data-ttu-id="0a8f5-122">또한 이 확인자는 피어 노드가 알려지고 피어 메시에서 사용할 수 있게 되는 메커니즘인 피어 메시를 통해 노드를 "등록"하는 데에도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-122">It is also used to "register" a node with a peer mesh, the mechanism by which the peer node becomes known and available from the peer mesh.</span></span> <span data-ttu-id="0a8f5-123">피어 확인자에 대 한 자세한 내용은 [피어 확인자](../../../wcf/feature-details/peer-resolvers.md)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="0a8f5-123">For more information on peer resolvers, see [Peer Resolvers](../../../wcf/feature-details/peer-resolvers.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a8f5-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a8f5-124">See also</span></span>

- <xref:System.ServiceModel.PeerResolver>
- <xref:System.ServiceModel.PeerResolvers.PeerResolverSettings>
- <xref:System.ServiceModel.NetPeerTcpBinding.Resolver%2A>
- <xref:System.ServiceModel.Configuration.NetPeerTcpBindingElement.Resolver%2A>
- <xref:System.ServiceModel.Configuration.PeerResolverElement>
- [<span data-ttu-id="0a8f5-125">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="0a8f5-125">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="0a8f5-126">[PeerChannel 응용 프로그램에 사용자 지정 확인자 추가](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="0a8f5-126">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
