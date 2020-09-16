---
title: <custom>
ms.date: 03/30/2017
ms.assetid: a6f65a00-bd1a-4d4a-955a-fe009ec02ab8
ms.openlocfilehash: 4077aacab1c1c4594db76cc6663bfc0245d345d7
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90555499"
---
# \<custom>
<span data-ttu-id="66fd6-101">사용자 지정 피어 확인자 서비스의 설정을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66fd6-101">Specifies settings for a custom peer resolver service.</span></span>  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.serviceModel>**](system-servicemodel.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<bindings>**](bindings.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<netPeerTcpBinding>**](netpeertcpbinding.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<binding>**\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<resolver>**](resolver.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<custom>**  
  
## <a name="syntax"></a><span data-ttu-id="66fd6-102">구문</span><span class="sxs-lookup"><span data-stu-id="66fd6-102">Syntax</span></span>  
  
```xml  
<custom address="Uri"
        resolverType="String">
  <headers/>
  <identity/>
</custom>
```  
  
## <a name="attributes-and-elements"></a><span data-ttu-id="66fd6-103">특성 및 요소</span><span class="sxs-lookup"><span data-stu-id="66fd6-103">Attributes and Elements</span></span>  
 <span data-ttu-id="66fd6-104">다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="66fd6-104">The following sections describe attributes, child elements, and parent elements.</span></span>  
  
### <a name="attributes"></a><span data-ttu-id="66fd6-105">특성</span><span class="sxs-lookup"><span data-stu-id="66fd6-105">Attributes</span></span>  
  
|<span data-ttu-id="66fd6-106">attribute</span><span class="sxs-lookup"><span data-stu-id="66fd6-106">Attribute</span></span>|<span data-ttu-id="66fd6-107">Description</span><span class="sxs-lookup"><span data-stu-id="66fd6-107">Description</span></span>|  
|---------------|-----------------|  
|`address`|<span data-ttu-id="66fd6-108">사용자 지정 피어 확인자 서비스를 호스트하는 피어 노드의 엔드포인트 주소를 지정하는 URI입니다.</span><span class="sxs-lookup"><span data-stu-id="66fd6-108">A URI that specifies the endpoint address of the peer node that hosts the custom peer resolver service.</span></span>|  
|`resolverType`|<span data-ttu-id="66fd6-109">사용자 지정 피어 확인자 서비스의 형식을 지정하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="66fd6-109">A string that specifies the type of the custom peer resolver service.</span></span>|  
  
### <a name="child-elements"></a><span data-ttu-id="66fd6-110">자식 요소</span><span class="sxs-lookup"><span data-stu-id="66fd6-110">Child Elements</span></span>  
  
|<span data-ttu-id="66fd6-111">요소</span><span class="sxs-lookup"><span data-stu-id="66fd6-111">Element</span></span>|<span data-ttu-id="66fd6-112">Description</span><span class="sxs-lookup"><span data-stu-id="66fd6-112">Description</span></span>|  
|-------------|-----------------|  
|[\<identity>](identity.md)|<span data-ttu-id="66fd6-113">이 요소로 구성된 사용자 지정 피어 확인자의 ID를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="66fd6-113">Specifies the identity for custom peer resolvers configured with this element.</span></span> <span data-ttu-id="66fd6-114">이 요소는 <xref:System.ServiceModel.Configuration.IdentityElement> 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="66fd6-114">This element is of type <xref:System.ServiceModel.Configuration.IdentityElement>.</span></span>|  
|[\<headers>](headers-element.md)|<span data-ttu-id="66fd6-115">사용자 지정 피어 확인자에서 처리하는 SOAP 메시지에 사용되는 주소 헤더 컬렉션입니다.</span><span class="sxs-lookup"><span data-stu-id="66fd6-115">A collection of address header used for SOAP messages handled by the custom peer resolver.</span></span>|  
  
### <a name="parent-elements"></a><span data-ttu-id="66fd6-116">부모 요소</span><span class="sxs-lookup"><span data-stu-id="66fd6-116">Parent Elements</span></span>  
  
|<span data-ttu-id="66fd6-117">요소</span><span class="sxs-lookup"><span data-stu-id="66fd6-117">Element</span></span>|<span data-ttu-id="66fd6-118">Description</span><span class="sxs-lookup"><span data-stu-id="66fd6-118">Description</span></span>|  
|-------------|-----------------|  
|[\<resolver>](resolver.md)|<span data-ttu-id="66fd6-119">메시에 참여하는 몇 개의 노드를 나타내는 피어 노드 주소 집합에 대한 피어 메시 ID를 확인하는 데 사용되는 피어 확인자입니다.</span><span class="sxs-lookup"><span data-stu-id="66fd6-119">A peer resolver that is used to resolve a peer mesh ID to a set of peer node addresses that represents several nodes that participate in the mesh.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="66fd6-120">설명</span><span class="sxs-lookup"><span data-stu-id="66fd6-120">Remarks</span></span>  
 <span data-ttu-id="66fd6-121">이 요소는 서비스를 호스트하는 피어의 엔드포인트 주소 및 모든 특정 바인딩 설정을 포함하여 사용자 지정 피어 확인자 서비스에 대한 기본 설정을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="66fd6-121">This element defines the basic settings for a custom peer resolver service, including the endpoint address of the peer hosting the service and any specific binding settings.</span></span> <span data-ttu-id="66fd6-122">사용자 지정 해결 프로그램을 만드는 방법에 대 한 자세한 내용은 [PeerChannel 응용 프로그램에 사용자 지정 해결 프로그램 추가](/previous-versions/ms730105(v=vs.90))를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="66fd6-122">For more information on creating a custom resolver, see [Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90)).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="66fd6-123">추가 정보</span><span class="sxs-lookup"><span data-stu-id="66fd6-123">See also</span></span>

- <xref:System.ServiceModel.PeerResolvers.CustomPeerResolverService>
- <xref:System.ServiceModel.PeerResolvers.PeerCustomResolverSettings>
- <xref:System.ServiceModel.Configuration.PeerResolverElement.Custom%2A>
- <xref:System.ServiceModel.Configuration.PeerCustomResolverElement>
- [<span data-ttu-id="66fd6-124">피어 확인자</span><span class="sxs-lookup"><span data-stu-id="66fd6-124">Peer Resolvers</span></span>](../../../wcf/feature-details/peer-resolvers.md)
- <span data-ttu-id="66fd6-125">[PeerChannel 응용 프로그램에 사용자 지정 확인자 추가](/previous-versions/ms730105(v=vs.90))</span><span class="sxs-lookup"><span data-stu-id="66fd6-125">[Adding a Custom Resolver to a PeerChannel Application](/previous-versions/ms730105(v=vs.90))</span></span>
