---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 598b341e8b09acd11ba215e6add3adf9e44b2b81
ms.sourcegitcommit: 093571de904fc7979e85ef3c048547d0accb1d8a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/06/2019
ms.locfileid: "70400462"
---
# <a name="custom"></a><span data-ttu-id="9fb80-101">\<custom></span><span class="sxs-lookup"><span data-stu-id="9fb80-101">\<custom></span></span>
<span data-ttu-id="9fb80-102">사용자 지정 피어 확인자 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb80-102">Specifies settings for a custom peer resolver service.</span></span>  
  
<span data-ttu-id="9fb80-103">[ **\<configuration>** ](../configuration-element.md)</span><span class="sxs-lookup"><span data-stu-id="9fb80-103">[**\<configuration>**](../configuration-element.md)</span></span>\
<span data-ttu-id="9fb80-104">&nbsp;&nbsp;[ **\<System.servicemodel >** ](system-servicemodel.md)</span><span class="sxs-lookup"><span data-stu-id="9fb80-104">&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)</span></span>\
<span data-ttu-id="9fb80-105">&nbsp;&nbsp;&nbsp;&nbsp;[ **\<바인딩 >** ](bindings.md)</span><span class="sxs-lookup"><span data-stu-id="9fb80-105">&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)</span></span>\
<span data-ttu-id="9fb80-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<netPeerTcpBinding >** ](netpeertcpbinding.md)</span><span class="sxs-lookup"><span data-stu-id="9fb80-106">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)</span></span>\
<span data-ttu-id="9fb80-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<바인딩 >** </span><span class="sxs-lookup"><span data-stu-id="9fb80-107">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**</span></span>\
<span data-ttu-id="9fb80-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[ **\<해결 프로그램 >** ](resolver.md)</span><span class="sxs-lookup"><span data-stu-id="9fb80-108">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)</span></span>\
<span data-ttu-id="9fb80-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp; **\<사용자 지정 >**</span><span class="sxs-lookup"><span data-stu-id="9fb80-109">&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9fb80-110">구문</span><span class="sxs-lookup"><span data-stu-id="9fb80-110">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9fb80-111">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9fb80-111">Attributes and Elements</span></span>  
 <span data-ttu-id="9fb80-112">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb80-112">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9fb80-113">특성</span><span class="sxs-lookup"><span data-stu-id="9fb80-113">Attributes</span></span>  
  
|<span data-ttu-id="9fb80-114">특성</span><span class="sxs-lookup"><span data-stu-id="9fb80-114">Attribute</span></span>|<span data-ttu-id="9fb80-115">설명</span><span class="sxs-lookup"><span data-stu-id="9fb80-115">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="9fb80-116">사용자 지정 피어 확인자 서비스를 호스트하는 피어 노드의 엔드포인트 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb80-116">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="9fb80-117">사용자 지정 피어 확인자 서비스의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb80-117">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9fb80-118">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9fb80-118">Child Elements</span></span>  
  
|<span data-ttu-id="9fb80-119">요소</span><span class="sxs-lookup"><span data-stu-id="9fb80-119">Element</span></span>|<span data-ttu-id="9fb80-120">Description</span><span class="sxs-lookup"><span data-stu-id="9fb80-120">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fb80-121">\<identity></span><span class="sxs-lookup"><span data-stu-id="9fb80-121">\<identity></span></span>](identity.md)|<span data-ttu-id="9fb80-122">이 요소로 구성된 사용자 지정 피어 확인자의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb80-122">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="9fb80-123">이 요소는 <xref:System.ServiceModel.Configuration.IdentityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb80-123">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[<span data-ttu-id="9fb80-124">\<headers></span><span class="sxs-lookup"><span data-stu-id="9fb80-124">\<headers></span></span>](headers-element.md)|<span data-ttu-id="9fb80-125">사용자 지정 피어 확인자에서 처리하는 SOAP 메시지에 사용되는 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb80-125">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9fb80-126">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9fb80-126">Parent Elements</span></span>  
  
|<span data-ttu-id="9fb80-127">요소</span><span class="sxs-lookup"><span data-stu-id="9fb80-127">Element</span></span>|<span data-ttu-id="9fb80-128">Description</span><span class="sxs-lookup"><span data-stu-id="9fb80-128">Description</span></span>|  
|-------------|-----------------|  
|[<span data-ttu-id="9fb80-129">\<resolver></span><span class="sxs-lookup"><span data-stu-id="9fb80-129">\<resolver></span></span>](resolver.md)|<span data-ttu-id="9fb80-130">메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 대한 피어 메시 ID를 확인하는 데 사용되는 피어 확인자입니다.</span><span class="sxs-lookup"><span data-stu-id="9fb80-130">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9fb80-131">설명</span><span class="sxs-lookup"><span data-stu-id="9fb80-131">Remarks</span></span>  
 <span data-ttu-id="9fb80-132">이 요소는 서비스를 호스트하는 피어의 엔드포인트 주소 및 모든 특정 바인딩 설정을 포함하여 사용자 지정 피어 확인자 서비스에 대한 기본 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9fb80-132">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="9fb80-133">사용자 지정 해결 프로그램을 만드는 방법에 대 한 자세한 내용은 [PeerChannel 응용 프로그램에 사용자 지정 해결 프로그램 추가](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9fb80-133">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9fb80-134">참고자료</span><span class="sxs-lookup"><span data-stu-id="9fb80-134">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="9fb80-135">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="9fb80-135">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="9fb80-136">[PeerChannel 응용 프로그램에 사용자 지정 해결 프로그램 추가](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9fb80-136">[Adding a Custom Resolver to a PeerChannel Application](https://docs.microsoft.com/previous-versions/ms730105(v=vs.90))</span></span>
