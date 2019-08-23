---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: b5cc522604fa7aca8ca6eae787520265b36fef6f
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/22/2019
ms.locfileid: "69925948"
---
# <a name="custom"></a><span data-ttu-id="35120-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="35120-101">\<custom></span></span>
<span data-ttu-id="35120-102">사용자 지정 피어 확인자 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="35120-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="35120-103">\<system.serviceModel></span><span class="sxs-lookup"><span data-stu-id="35120-103">\<system.serviceModel></span></span>  
<span data-ttu-id="35120-104">\<bindings></span><span class="sxs-lookup"><span data-stu-id="35120-104">\<bindings></span></span>  
<span data-ttu-id="35120-105">\<netPeerBinding></span><span class="sxs-lookup"><span data-stu-id="35120-105">\<netPeerBinding></span></span>  
<span data-ttu-id="35120-106">\<binding></span><span class="sxs-lookup"><span data-stu-id="35120-106">\<binding></span></span>  
<span data-ttu-id="35120-107">\<resolver></span><span class="sxs-lookup"><span data-stu-id="35120-107">\<resolver></span></span>  
<span data-ttu-id="35120-108">\<custom></span><span class="sxs-lookup"><span data-stu-id="35120-108">\<custom></span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35120-109">구문</span><span class="sxs-lookup"><span data-stu-id="35120-109">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="35120-110">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="35120-110">Attributes and Elements</span></span>  
 <span data-ttu-id="35120-111">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="35120-111">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="35120-112">특성</span><span class="sxs-lookup"><span data-stu-id="35120-112">Attributes</span></span>  
  
|<span data-ttu-id="35120-113">특성</span><span class="sxs-lookup"><span data-stu-id="35120-113">Attribute</span></span>|<span data-ttu-id="35120-114">Description</span><span class="sxs-lookup"><span data-stu-id="35120-114">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="35120-115">사용자 지정 피어 확인자 서비스를 호스트하는 피어 노드의 엔드포인트 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="35120-115">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="35120-116">사용자 지정 피어 확인자 서비스의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="35120-116">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="35120-117">자식 요소</span><span class="sxs-lookup"><span data-stu-id="35120-117">Child Elements</span></span>  
  
|<span data-ttu-id="35120-118">요소</span><span class="sxs-lookup"><span data-stu-id="35120-118">Element</span></span>|<span data-ttu-id="35120-119">Description</span><span class="sxs-lookup"><span data-stu-id="35120-119">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35120-120">\<identity></span><span class="sxs-lookup"><span data-stu-id="35120-120">\<identity></span></span>](identity.md)|<span data-ttu-id="35120-121">이 요소로 구성된 사용자 지정 피어 확인자의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="35120-121">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="35120-122">이 요소는 <xref:System.ServiceModel.Configuration.IdentityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="35120-122">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="35120-123">\<headers></span><span class="sxs-lookup"><span data-stu-id="35120-123">\<headers></span></span>](headers-element.md)|<span data-ttu-id="35120-124">사용자 지정 피어 확인자에서 처리하는 SOAP 메시지에 사용되는 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="35120-124">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="35120-125">부모 요소</span><span class="sxs-lookup"><span data-stu-id="35120-125">Parent Elements</span></span>  
  
|<span data-ttu-id="35120-126">요소</span><span class="sxs-lookup"><span data-stu-id="35120-126">Element</span></span>|<span data-ttu-id="35120-127">Description</span><span class="sxs-lookup"><span data-stu-id="35120-127">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="35120-128">\<resolver></span><span class="sxs-lookup"><span data-stu-id="35120-128">\<resolver></span></span>](resolver.md)|<span data-ttu-id="35120-129">메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 대한 피어 메시 ID를 확인하는 데 사용되는 피어 확인자입니다.</span><span class="sxs-lookup"><span data-stu-id="35120-129">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35120-130">설명</span><span class="sxs-lookup"><span data-stu-id="35120-130">Remarks</span></span>  
 <span data-ttu-id="35120-131">이 요소는 서비스를 호스트하는 피어의 엔드포인트 주소 및 모든 특정 바인딩 설정을 포함하여 사용자 지정 피어 확인자 서비스에 대한 기본 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="35120-131">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="35120-132">사용자 지정 해결 프로그램을 만드는 방법에 대 한 자세한 내용은 [PeerChannel 응용 프로그램에 사용자 지정 해결 프로그램 추가](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="35120-132">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35120-133">참고자료</span><span class="sxs-lookup"><span data-stu-id="35120-133">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="35120-134">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="35120-134">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="35120-135">[PeerChannel 응용 프로그램에 사용자 지정 해결 프로그램 추가](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="35120-135">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
