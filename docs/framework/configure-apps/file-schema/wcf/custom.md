---
description: 다음에 대해 자세히 알아보세요. <custom>
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 327a5d7ff1bab88a1633d7a10095e708e6b1a533
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99725911"
---
# \<custom>

<span data-ttu-id="9f5bc-102">사용자 지정 피어 확인자 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-102">Specifies settings for a custom peer resolver service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a><span data-ttu-id="9f5bc-103">구문</span><span class="sxs-lookup"><span data-stu-id="9f5bc-103">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="9f5bc-104">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="9f5bc-104">Attributes and Elements</span></span>  

 <span data-ttu-id="9f5bc-105">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-105">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="9f5bc-106">특성</span><span class="sxs-lookup"><span data-stu-id="9f5bc-106">Attributes</span></span>  
  
|<span data-ttu-id="9f5bc-107">attribute</span><span class="sxs-lookup"><span data-stu-id="9f5bc-107">Attribute</span></span>|<span data-ttu-id="9f5bc-108">설명</span><span class="sxs-lookup"><span data-stu-id="9f5bc-108">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="9f5bc-109">사용자 지정 피어 확인자 서비스를 호스트하는 피어 노드의 엔드포인트 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-109">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="9f5bc-110">사용자 지정 피어 확인자 서비스의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-110">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="9f5bc-111">자식 요소</span><span class="sxs-lookup"><span data-stu-id="9f5bc-111">Child Elements</span></span>  
  
|<span data-ttu-id="9f5bc-112">요소</span><span class="sxs-lookup"><span data-stu-id="9f5bc-112">Element</span></span>|<span data-ttu-id="9f5bc-113">설명</span><span class="sxs-lookup"><span data-stu-id="9f5bc-113">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="9f5bc-114">이 요소로 구성된 사용자 지정 피어 확인자의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-114">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="9f5bc-115">이 요소는 <xref:System.ServiceModel.Configuration.IdentityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-115">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="9f5bc-116">사용자 지정 피어 확인자에서 처리하는 SOAP 메시지에 사용되는 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-116">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="9f5bc-117">부모 요소</span><span class="sxs-lookup"><span data-stu-id="9f5bc-117">Parent Elements</span></span>  
  
|<span data-ttu-id="9f5bc-118">요소</span><span class="sxs-lookup"><span data-stu-id="9f5bc-118">Element</span></span>|<span data-ttu-id="9f5bc-119">설명</span><span class="sxs-lookup"><span data-stu-id="9f5bc-119">Description</span></span>|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|<span data-ttu-id="9f5bc-120">메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 대한 피어 메시 ID를 확인하는 데 사용되는 피어 확인자입니다.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-120">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f5bc-121">설명</span><span class="sxs-lookup"><span data-stu-id="9f5bc-121">Remarks</span></span>  

 <span data-ttu-id="9f5bc-122">이 요소는 서비스를 호스트하는 피어의 엔드포인트 주소 및 모든 특정 바인딩 설정을 포함하여 사용자 지정 피어 확인자 서비스에 대한 기본 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-122">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="9f5bc-123">사용자 지정 해결 프로그램을 만드는 방법에 대 한 자세한 내용은 [PeerChannel 응용 프로그램에 사용자 지정 해결 프로그램 추가](/previous-versions/ms730105(v=vs.90))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="9f5bc-123">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f5bc-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9f5bc-124">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="9f5bc-125">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="9f5bc-125">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="9f5bc-126">[PeerChannel 응용 프로그램에 사용자 지정 확인자 추가](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="9f5bc-126">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
